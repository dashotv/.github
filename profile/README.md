# DashoTV

PVR software similar to `Sonarr`, `Radarr`, and all the other `*-arrs` out there. This is
[shawncatz](https://github.com/shawncatz)'s personal project to manage my media server.

This is also a project that I use to play around with new technologies and experiment with new ideas.

This is the most recent evolution of software that I've been working on - on and off - for over 20 years. It
started as a simple PHP site that would manage TV Series and Movies and grew from there.

## Alpha

This code is alpha. It's all public, but it's still pretty rough. Let me know if you're interested or going to use it.

## Features

- Manage TV Series and Movies
- Manage an index of torrents and usenet posts
  - In the future I'd like to extend this to support other indexing systems (`Jackett`, etc)
- Automatically download new episodes and movies
- Automatically rename and organize media
- Automatically sync with `Plex` and `Jellyfin`
- Integrates with Qbittorrent and NZBGet for downloading

## Technology

An overview of all the technology used in this project. Everything is built with `golang` and the UI is `react` and `typescript`.

### Services

- [Flame](https://github.com/dashotv/flame) is the service that manages communication with the torrent and nzb
  downloaders.
  - It also includes golang clients for `Qbittorrent` and `NZBGet`.
- [Tower](https://github.com/dashotv/tower) is the service that manages all of the media and communications with
  `Plex` and `Jellyfin`.
- [Scry](https://github.com/dashotv/scry) is the search service. It handles searching the `Elasticsearch` indexes of
  media and releases (torrents and nzbs) as well as searches against `TheTVDB` and `TheMovieDB`.
- [UI](https://github.com/dashotv/ui) is the web UI for the system. It's built with `React` and `Typescript`.

### Notable Libraries

- [Golem](https://github.com/dashotv/golem) is a custom framework for managing microservices. I built this to play
  around with code generation to simplify working on multiple services. It ain't perfect, but it was fun to build.
- [Grimoire](https://github.com/dashotv/grimoire) is a custom ORM that's built on top of
  [Kamva mgm](https://github.com/kamva/mgm) using `Golang` 1.18 generics.
- [Mercury](https://github.com/dashotv/mercury) is a lightweight pub/sub framework built on top of
  [Nats](https://github.com/nats-io). Simplifies communication between services as well as websockets.
- [Minion](https://github.com/dashotv/minion) is a lightweight background job / worker pool / scheduler.
- [TVDB](https://github.com/dashotv/tvdb) is a client for TheTVDB API.
- [TMDB](https://github.com/dashotv/tmdb) is a client for TheMovieDB API.

### Supporting Systems

- [MongoDB](https://www.mongodb.com/) database
- [Nats](https://github.com/nats-io) message bus
- [Redis](https://redis.io/) cache
- [Elasticsearch](https://www.elastic.co/) indexing and search engine
- [Nginx](https://www.nginx.com/) reverse proxy

## Installation

The entire system is managed as a set of containers through `Docker Compose`. This is not ready for production use, and
hasn't been productionized for other people to try it yet.

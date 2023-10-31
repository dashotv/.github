# DashoTV

PVR software similar to Sonarr, Radarr, and all the other \*arrs out there. This is
[shawncatz](https://github.com/shawncatz)'s personal project to manage my media server. This is the most
recent evolution of software that I've been working on - on and off - for over 20 years.

It started a simple PHP script that would manage TV Series and Movies and grew from there.

## Features

- Manage TV Series and Movies
- Manage an index of torrents and usenet posts
  - In the future I'd like to extend this to support other indexing systems (`Jackett`, etc)
- Automatically download new episodes and movies
- Automatically rename and organize media
- Automatically sync with `Plex` and `Jellyfin`
- Integrates with Qbittorrent and NZBGet for downloading

## Installation

The entire system is managed as a set of containers through `Docker Compose`.

# **Media Server**

Media server setup based on Docker and Plex.

## Reference

- [Preparation](#preparation)

- [Constants](#constants)

- [Networking](#networking)

- [Services](#services)

  - [rTorrent](#rtorrent)

  - [Jackett](#jackett)

  - [Sonarr](#sonarr)

  - [Radarr](#radarr)

  - [Ombi](#ombi)

  - [Tautulli](#tautulli)

  - [Plex](#plex)

## Preparation

Clone this repo into your home directory:

    git clone $GITHUB_REPO

## Constants

All constants (Passwords, Usernames, API Keys etc.) will be defined in the `NeuroVision/.env` file.

Rename `.env-example` to `.env` and update info and passwords as needed.

## Networking

### Note

If you do not decide to use the same network names as defined here, be sure to update your `.env` file.

## Create `mediaNet` network for Media containers

    docker network create mediaNet

## Services

- [**Media Server**](#media-server)
  - [Reference](#reference)
  - [Preparation](#preparation)
  - [Constants](#constants)
  - [Networking](#networking)
    - [Note](#note)
  - [Create `mediaNet` network for Media containers](#create-medianet-network-for-media-containers)
  - [Services](#services)
    - [rTorrent](#rtorrent)
    - [Jackett](#jackett)
    - [Sonarr](#sonarr)
    - [Radarr](#radarr)
    - [Ombi](#ombi)
    - [Tautulli](#tautulli)
    - [Plex](#plex)

### rTorrent

Arch Linux running rTorrent with ruTorrent webui and OpenVPN by [binhex](https://github.com/binhex) on [DockerHub](https://hub.docker.com/r/binhex/arch-rtorrentvpn)

Ports

    - 9080
    - 9443
    - 8118
    - 49184
    - 6881
    - 5000

### Jackett

Jackett container by [linuxserver.io](https://www.linuxserver.io/) on [DockerHub](https://hub.docker.com/r/linuxserver/jackett). Connects to the `rTorrent` Privoxy service (port `8118`) to search for torrents via the VPN (configured via the Jackett webUI Proxy settings).

Ports

    - 9117

### Sonarr

Sonarr container by [linuxserver.io](https://www.linuxserver.io/) on [DockerHub](https://hub.docker.com/r/linuxserver/sonarr)

Ports

    - 8989

### Radarr

Radarr container by [linuxserver.io](https://www.linuxserver.io/) on [DockerHub](https://hub.docker.com/r/linuxserver/radarr)

Ports

    - 7878

### Ombi

Ombi container by [linuxserver.io](https://www.linuxserver.io/) on [DockerHub](https://hub.docker.com/r/linuxserver/ombi)

Ports

    - 3579

### Tautulli

Tautulli container by [linuxserver.io](https://www.linuxserver.io/) on [DockerHub](https://hub.docker.com/r/linuxserver/tautulli)

Ports

    - 8181

### Plex

Plex container by [linuxserver.io](https://www.linuxserver.io/) on [DockerHub](https://hub.docker.com/r/linuxserver/plex)

Ports

    - 32400

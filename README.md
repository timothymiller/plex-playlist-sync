# 🐍 Plex Playlist Sync 🔄

Automatically sync playlists from your admin Plex account with your managed accounts.

## 📊 Stats

| Size  | Downloads | Discord |
| ------------- | ------------- | ------------- |
| [![Plex Playlist Sync docker image size](https://img.shields.io/docker/image-size/timothyjmiller/plex-playlist-sync?style=flat-square)](https://hub.docker.com/r/timothyjmiller/plex-playlist-sync "plex-playlist-sync docker image size")  | [![Total DockerHub pulls](https://img.shields.io/docker/pulls/timothyjmiller/plex-playlist-sync?style=flat-square)](https://hub.docker.com/r/timothyjmiller/plex-playlist-sync "Total DockerHub pulls")  | [![Official Discord Server](https://img.shields.io/discord/785778163887112192?style=flat-square)](https://discord.gg/UgGmwMvNxm "Official Discord Server")

## 🏃 Runtime

- Alpine Linux
- Python3
- Docker
- Multi-Architecture (arm64, amd64, & more)

## 🔋 Bash Scripts (Docker + Docker Hub)

- Build

```bash
chmod +x ./docker-build.sh
./docker-build.sh
```

- Publish

```bash
chmod +x ./docker-publish.sh
./docker-publish.sh
```

- Run

```bash
chmod +x ./docker-run.sh
./docker-run.sh
```

## 🚦 Getting Started

Deploying is simple & requires providing environment variables to access Plex to the docker-compose file.

## 🔒 Environment

For more information on finding an authentication token (PLEX_TOKEN), [click here](https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/)

Create a file called `.env` in the same directory as your docker-compose.yml file

```bash
PLEX_URL=https://YOUR_PLEX_DOMAIN_HERE
PLEX_TOKEN=YOUR_PLEX_TOKEN_HERE
PLEX_PLAYLISTS=Playlist1, Playlist2, Playlist3
PLEX_USERS=User1, User2, User3
REPEAT_INTERVAL=15
```

## 🐳 Docker Compose

```bash
version: "3.7"
services:
  plex-playlist-sync:
    image: timothyjmiller/plex-playlist-sync:latest
    container_name: plex-playlist-sync
    security_opt:
      - no-new-privileges:true
    env_file:
      .env
    restart: unless-stopped
```

## License

This Template is licensed under the GNU General Public License, version 3 (GPLv3).

## Author

Timothy Miller

[View my GitHub profile 💡](https://github.com/timothymiller)

[View my personal website 💻](https://timknowsbest.com)

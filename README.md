
# homelab setup

Everything is running on a venerable Dell OptiPlex (Core7th i5-7500T 2.7GHz 8GB) bought $150 on ebay.
Jellyfin and photoprism supports Hardware acceleration for video encoding/decoding (x264, x265 with this intel 7th gen CPU).

- [traefik](https://traefik.io/traefik/)
- [homepage](https://gethomepage.dev/en/installation/)
- [adguard](https://adguard.com/en/welcome.html)
- [qbittorrent](https://www.qbittorrent.org)
- [sonarr](https://sonarr.tv/)
- [radarr](https://radarr.video/)
- [prowlarr](https://prowlarr.com/)
- [jellyfin](https://jellyfin.org/)
- [jellyseerr](https://github.com/Fallenbagel/jellyseerr)
- [plex](https://www.plex.tv/)
- [tautulli](https://tautulli.com)
- [overseerr](https://overseerr.dev/)
- [photoprism](https://www.photoprism.app/)
- [nordVPN](https://nordvpn.com/) if needed (I needed to reach a French based indexed with Prowlarr)

![](images/screen.png)

Inspired by
- https://github.com/notthebee/infra
- https://github.com/AdrienPoupa/docker-compose-nas



## Installation

```
ansible-galaxy install -r requirements.yml
```

Edit `group_vars/all/vars.yml`

```
ansible-playbook run.yml --tags system,adguard,services
```

Adguard must be configured during its 1st run on `adguard.static_ip`, port 3000. Then the service will be served on port 80.

```
ansible-playbook run.yml --tags services
```

## Service configuation

Unfortunetely, those services require the GUI to be configured (local URL + api keys):
  - qbittorrent
  - sonarr
  - radarr
  - prowlarr
  - jellyfin
  - jellyseerr
  - photoprism


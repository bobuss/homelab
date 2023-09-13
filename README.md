
# homelab setup

Inspired by https://github.com/notthebee/infra



## Installation

```
ansible-galaxy install -r requirements.yml
```

Edit `group_vars/all/vars.yml`

```
ansible-playbook run.yml --tags system,docker,adguard
```

Adguard must be configured during its 1st run on `adguard.static_ip`, port 3000. Then the service will be served on port 80.

```
ansible-playbook run.yml --tags services
```

## Service configuation

Unfortunetely, those services require the GUI to be configured:
  - qbittorrent
  - sonarr
  - radarr
  - prowlarr
  - jellyfin
  - jellyseerr
  - photoprism


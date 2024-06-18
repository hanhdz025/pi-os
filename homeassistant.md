## Cài Đặt Home Assistant
#### Tạo thư mục
```bash
mkdir homeassistant
```
#### Tạo file compose
```bash
nano compose.yaml
```

```yaml
services:
  homeassistant:
    container_name: homeassistant
    image: homeassistant/home-assistant:stable
    volumes:
      - ./config:/config
      - /etc/localtime:/etc/localtime:ro
      - /run/dbus:/run/dbus:ro
    restart: unless-stopped
    privileged: true
    network_mode: host
```
```bash
docker compose up -d
```

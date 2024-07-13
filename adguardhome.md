## Cài Đặt AdGuard Home
AdGuard Home là một phần mềm lọc DNS giúp chặn quảng cáo và theo dõi trên toàn bộ mạng của bạn. Sử dụng Docker Compose giúp dễ dàng triển khai và quản lý AdGuard Home.

#### Tạo thư mục AdGuard Home
```bash
mkdir adguardhome && cd adguardhome
```
#### Tạo file compose
```bash
nano compose.yaml
```

```yaml
services:
  adguardhome:
    image: adguard/adguardhome:latest
    container_name: adguardhome
    restart: unless-stopped
    volumes:
      - /etc/localtime:/etc/localtime:ro
      - ./work:/opt/adguardhome/work
      - ./config:/opt/adguardhome/conf
    ports:
      # Plain DNS
      - "53:53/tcp"
      - "53:53/udp"
      # AdGuard Home Admin Panel as well as DNS-over-HTTPS
      - "80:80/tcp"
      - "443:443/tcp"
      - "443:443/udp"
      - "3000:3000/tcp"
      # DNS-over-TLS
      - "853:853/tcp"
      # DNS-over-QUIC
      - "784:784/udp"
      - "853:853/udp"
      # DNSCrypt
      - "5443:5443/tcp"
      - "5443:5443/udp"
```
```bash
docker compose up -d
```

#### Cấu hình DNS Servers
```
https://dns.google/dns-query
https://dns.cloudflare.com/dns-query
https://dns10.quad9.net/dns-query
```

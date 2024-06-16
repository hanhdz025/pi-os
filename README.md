# Raspberry Pi OS

## Cập Nhật Hệ Thống
#### Kiểm tra và cập nhật gói phần mềm hiện tại
```bash
sudo apt update
sudo apt full-upgrade
```

#### Khởi động lại Raspberry Pi
```bash
sudo reboot
```

#### Xóa các gói phần mềm không cần thiết
```bash
sudo apt autoremove
```

## Cài đặt Docker và Docker Compose
#### Cài đặt Docker
```bash
curl -sSL https://get.docker.com | sh
```
#### Thêm người dùng pi vào nhóm docker
```bash
sudo usermod -aG docker $USER
```
#### Đăng xuất và đăng nhập lại
```bash
logout
```

## Cài Đặt AdGuard Home
#### Tạo thư mục AdGuard Home
```bash
mkdir adguardhome
```
#### Tạo file compose
```bash
nano compose.yaml
```

```bash
docker compose up -d
```

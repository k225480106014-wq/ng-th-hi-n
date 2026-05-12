Bài tập 03 - Sử dụng WordPress để tạo Website
Môn: Phát triển ứng dụng với mã nguồn mở - TEE0421
Lớp: 58KTPM
Sinh viên: Ngô Thị Hiền- K225480106014

Yêu cầu bài tập
Sử dụng Docker trên Ubuntu để triển khai các service:

MariaDB
phpMyAdmin
WordPress
Sau đó:

Public website bằng Cloudflare Tunnel
Tạo bài viết giới thiệu bản thân
Tạo bài viết giới thiệu ngành học yêu thích tại TNUT
Nhận xét việc sử dụng WordPress
1. Thiết lập cấu trúc thư mục và Docker Compose
Đầu tiên, hãy tạo không gian làm việc để quản lý các file cấu hình.

# Tạo thư mục dự án
mkdir wordpress-lab && cd wordpress-lab

# Tạo file docker-compose.yml
nano docker-compose.yml
Nội dung file docker-compose.yml:

services:

  mariadb:
    image: mariadb:latest
    container_name: mariadb
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root123
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wpuser
      MYSQL_PASSWORD: wp123
    volumes:
      - mariadb_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin:latest
    container_name: phpmyadmin
    restart: always
    ports:
      - "8081:80"
    environment:
      PMA_HOST: mariadb
      MYSQL_ROOT_PASSWORD: root123

  wordpress:
    image: wordpress:latest
    container_name: wordpress
    restart: always
    ports:
      - "8001:80"
    environment:
      WORDPRESS_DB_HOST: mariadb:3306
      WORDPRESS_DB_USER: wpuser
      WORDPRESS_DB_PASSWORD: wp123
      WORDPRESS_DB_NAME: wordpress
    depends_on:
      - mariadb

volumes:
  mariadb_data:
<img width="1171" height="665" alt="image" src="https://github.com/user-attachments/assets/5e3bf75a-5021-407e-8342-745e574cd8bb" />


2. Các bước triển khai hệ thống
Bước 1: Khởi chạy Container
Sử dụng lệnh sau để tải image và chạy các service ngầm:
docker compose up -d
<img width="1362" height="408" alt="image" src="https://github.com/user-attachments/assets/14e8f8be-9d61-4da0-80a5-cdb3f5f326ee" />

Bước 2: Kiểm tra Database qua phpMyAdmin
1. Truy cập: http://192.168/1.16:8081
 Đăng nhập:
. usr:root bằng tài khoản root và mật khẩu đã thiết lập ở trên.
.password:root123
2. Kiểm tra xem CSDLC wp-database đã tồn tại chưa (WordPress sẽ tự tạo bảng khi cài đặt xong).
ảnh database WordPress và các bản wp-
<img width="1127" height="561" alt="image" src="https://github.com/user-attachments/assets/3edadd6c-5eec-4fc5-910f-40d37f9f65ad" />

Bước 3: Cấu hình WordPress
1. Truy cập: http:http://192.168/1.16:8000
2. Chọn ngôn ngữ, thiết lập tài khoản Admin cho website.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c5ad3812-730e-47e2-ad12-d53d429b867f" />
3. Public Website qua Cloudflare Tunnel
Để đưa web lên một sub-domain (ví dụ: lab.yourdomain.com), hãy thực hiện:
1. Cài đặt cloudflared
curl -L https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb -o cloudflared.deb
sudo dpkg -i cloudflared.deb
2. Xác thực: cloudflared tunnel login (Click vào link hiện ra để chọn tên miền).
3.Tạo Tunnel: cloudflared tunnel create wp-tunnel.
4.Trỏ DNS & Chạy: * Trỏ DNS: cloudflared tunnel route dns wp-tunnel lab.yourdomain.com
. Chạy tunnel kết nối tới port 8000:
cloudflared tunnel run --url http://localhost:8000 wp-tunnel


4. Nội dung bài viết 
• Bài viết 1 - Giới thiệu bản thân: Sử dụng Block "Media & Text" để ảnh thẻ/ảnh cá nhân bên cạnh thông tin
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/c09ba999-e915-4685-af9f-a40ad95345f1" />

• Bài viết 2 - Ngành học tại TNUT: 
. giới thiệu về ngành học : ngành kỹ thuật phần mềm tại trường Đại Học Kĩ Thuật Công Nghiệp (TNUT)
Hình ảnh dưới đây minh họa quá trình soạn thảo bài giới thiệu bản thân thông qua Localhost:
<img width="1919" height="943" alt="image" src="https://github.com/user-attachments/assets/2f9d5b7c-4b0d-481f-bd51-2b6ddbfee324" />

5. Nhận xét về WordPress & Docker
• Độ tiện dụng: WordPress cung cấp kho giao diện khổng lồ, giúp tạo web chuyên nghiệp mà không cần code. Docker giúp đóng gói mọi thứ, tránh lỗi "chạy được trên máy em nhưng không chạy được trên máy thầy".
• Tài nguyên: * RAM: Hệ thống này ngốn khoảng 400MB - 600MB RAM khi ở trạng thái nghỉ.
• CPU: Rất thấp, trừ khi website có lượng truy cập lớn hoặc xử lý ảnh nặng.
• Khó khăn: Việc cấu hình SSL và kết nối Tunnel đôi khi gặp lỗi về port hoặc quyền ghi (permission) trên các thư mục volumes của Linux.



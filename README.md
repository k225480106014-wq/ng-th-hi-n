# Môn: Phát triển ứng dụng với mã nguồn mở-TEE0421
Lớp: 58KTPM
**Bài tập 02:** 
# SỬ DỤNG DJANGO ĐỂ TẠO WEB QUẢN LÝ TIỆM CẦM ĐỒ
## deadline : 23h59 ngày 09 tháng 5 năm 2026.
1.TỔ CHỨC CSDL CHO HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ: viết tay ra giấy, lấy điện thoại chụp lại, upload ảnh lên github (đã nói về các nghiệp vụ trên lớp, ghi bảng)
# Môn: Phát triển ứng dụng với mã nguồn mở-TEE0421
Lớp: 58KTPM
**Bài tập 02:** 
# SỬ DỤNG DJANGO ĐỂ TẠO WEB QUẢN LÝ TIỆM CẦM ĐỒ
## deadline : 23h59 ngày 09 tháng 5 năm 2026.
1.TỔ CHỨC CSDL CHO HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ: viết tay ra giấy, lấy điện thoại chụp lại, upload ảnh lên github (đã nói về các nghiệp vụ trên lớp, ghi bảng)
<img width="778" height="910" alt="image" src="https://github.com/user-attachments/assets/03895596-b71e-4ca1-8fab-830d2f637c72" />

2. SỬ DỤNG DOCKER TRÊN UBUNTU ĐỂ: 
•	Cài đặt Ubuntu + Docker Trong Ubuntu chạy: sudo apt update sudo apt install docker.io docker-compose -y
 
•	cài docker compose
 
•	Tạo Gõ chính thư mục: mkdir tiemcamdo cd tiemcamdo
 
•	TẠO Thương MỤC DJANGO
o	Tạo thư mục chứa Django
o	mkdir django_app
  
•	Đi vào django_app cd django_app
-TẠO FILE Dockerfile
Tạo file Dockerfile bằng nano Dockerfile
TẠO requirements.txt
o	Tạo tệp: nano requirements .txt

•	Kiểm tra thư mục
 
•	TẠO  docker-compose.yml Tạo file nano docker-compose.yml
•	 
 
•	XÂY DỰNG DOCKER Chạy docker compose docker compose up -d --build
 	 

•	TẠO DJANGO PROJECT docker compose exec django django-admin startproject config .
•	Tạo ứng dụng docker compose exec django python manage.py startapp pawnshop
•	

•	Mở file settings.py Chạy: nano django_app/config/settings.py
•	Tìm đoạn: DATABASES = { 'default': { 'ENGINE': 'django.db.backends.sqlite3', 'NAME': BASE_DIR / 'db.sqlite3', }
} sửa thành như trong ảnh
  
•	Tạo mô hình Mở: nano django_app/pawnshop/models.py







Chạy migration docker compose exec django python manage.py makemigrations
•	Di chuyển cơ sở dữ liệu bằng docker compose exec django python manage.py migrate

 






•	Tạo tài khoản admin docker compose exec django python manage.py createsuperuser

  
•	Cho admin quản lý bảng Mở: nano django_app/pawnshop/admin.py
 
•	Chạy Django
o	docker compose down
o	docker compose up -d --build
•	Test web Mở trình duyệt Ubuntu: http://localhost:8000
•	hoặc : http://127.0.0.1:8000/admin

 
•	Tạo thư mục templates Mở terminal Ubuntu: mkdir -p django_app/pawnshop/templates Tạo file home.html nano django_app/pawnshop/templates/home.html
 
•	Mở views.py nano django_app/pawnshop/views.py
 
•	Tạo urls.py cho app nano django_app/config/urls.py
 
•	Kiểm tra dữ liệu bằng phpMyAdmin
 


 

•	Public website bằng Cloudflare Tunnel > - đã có container: cloudflared nên giờ chỉ cần cấu hình tunnel. > - Kiểm tra cloudflared đang chạy: docker logs cloudflared
  



















   
2. SỬ DỤNG DOCKER TRÊN UBUNTU ĐỂ: 
•	Cài đặt Ubuntu + Docker Trong Ubuntu chạy: sudo apt update sudo apt install docker.io docker-compose -y
 
•	cài docker compose
 
•	Tạo Gõ chính thư mục: mkdir tiemcamdo cd tiemcamdo
 
•	TẠO Thương MỤC DJANGO
o	Tạo thư mục chứa Django
o	mkdir django_app
  
•	Đi vào django_app cd django_app
-TẠO FILE Dockerfile
Tạo file Dockerfile bằng nano Dockerfile
TẠO requirements.txt
o	Tạo tệp: nano requirements .txt

•	Kiểm tra thư mục
 
•	TẠO  docker-compose.yml Tạo file nano docker-compose.yml
•	 
 
•	XÂY DỰNG DOCKER Chạy docker compose docker compose up -d --build
 	 

•	TẠO DJANGO PROJECT docker compose exec django django-admin startproject config .
•	Tạo ứng dụng docker compose exec django python manage.py startapp pawnshop
•	

•	Mở file settings.py Chạy: nano django_app/config/settings.py
•	Tìm đoạn: DATABASES = { 'default': { 'ENGINE': 'django.db.backends.sqlite3', 'NAME': BASE_DIR / 'db.sqlite3', }
} sửa thành như trong ảnh
  
•	Tạo mô hình Mở: nano django_app/pawnshop/models.py







Chạy migration docker compose exec django python manage.py makemigrations
•	Di chuyển cơ sở dữ liệu bằng docker compose exec django python manage.py migrate

 






•	Tạo tài khoản admin docker compose exec django python manage.py createsuperuser

  
•	Cho admin quản lý bảng Mở: nano django_app/pawnshop/admin.py
 
•	Chạy Django
o	docker compose down
o	docker compose up -d --build
•	Test web Mở trình duyệt Ubuntu: http://localhost:8000
•	hoặc : http://127.0.0.1:8000/admin

 
•	Tạo thư mục templates Mở terminal Ubuntu: mkdir -p django_app/pawnshop/templates Tạo file home.html nano django_app/pawnshop/templates/home.html
 
•	Mở views.py nano django_app/pawnshop/views.py
 
•	Tạo urls.py cho app nano django_app/config/urls.py
 
•	Kiểm tra dữ liệu bằng phpMyAdmin
 


 

•	Public website bằng Cloudflare Tunnel > - đã có container: cloudflared nên giờ chỉ cần cấu hình tunnel. > - Kiểm tra cloudflared đang chạy: docker logs cloudflared
  



















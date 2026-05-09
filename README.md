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
 <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f6a40b88-2c57-497d-ac8f-1467ab22f4b2" />

•	cài docker compose
 <img width="522" height="477" alt="image" src="https://github.com/user-attachments/assets/e8b0373e-62f7-4cb8-ba09-1d4ec1299f27" />

•	Tạo Gõ chính thư mục: mkdir tiemcamdo cd tiemcamdo
 <img width="519" height="131" alt="image" src="https://github.com/user-attachments/assets/2a209af8-a104-4096-bb81-74138c862540" />

•	TẠO Thương MỤC DJANGO
o	Tạo thư mục chứa Django
o	mkdir django_app
  <img width="1084" height="195" alt="image" src="https://github.com/user-attachments/assets/aba37197-1c2e-4b8f-bcda-fa6dad903e38" />

•	Đi vào django_app cd django_app
-TẠO FILE Dockerfile
Tạo file Dockerfile bằng nano Dockerfile
TẠO requirements.txt<img width="733" height="910" alt="image" src="https://github.com/user-attachments/assets/d02e672f-ca41-4a84-93db-8b885a923d22" />

o	Tạo tệp: nano requirements .txt
<img width="550" height="500" alt="image" src="https://github.com/user-attachments/assets/17196e85-da82-4f10-9b9f-4f5384b622ba" />

•	Kiểm tra thư mục
 <img width="1102" height="173" alt="image" src="https://github.com/user-attachments/assets/8a469c29-e97f-4dff-afaa-41d52ad9c38a" />

•	TẠO  docker-compose.yml Tạo file nano docker-compose.yml
<img width="635" height="715" alt="image" src="https://github.com/user-attachments/assets/6044238d-1eaf-4170-a0ae-b87f9e53791a" />

 
•	XÂY DỰNG DOCKER Chạy docker compose docker compose up -d --build
 	 <img width="913" height="485" alt="image" src="https://github.com/user-attachments/assets/54dcb82a-506d-4667-b26c-1e704ddb7222" />


•	TẠO DJANGO PROJECT docker compose exec django django-admin startproject config .
•	Tạo ứng dụng docker compose exec django python manage.py startapp pawnshop
<img width="861" height="446" alt="image" src="https://github.com/user-attachments/assets/1fa84aff-9ef9-4477-9efa-aa32367d2206" />


•	Mở file settings.py Chạy: nano django_app/config/settings.py
•	Tìm đoạn: DATABASES = { 'default': { 'ENGINE': 'django.db.backends.sqlite3', 'NAME': BASE_DIR / 'db.sqlite3', }
} sửa thành như trong ảnh
  <img width="838" height="358" alt="image" src="https://github.com/user-attachments/assets/cba58435-27a3-43aa-9bf0-8a8c16737d62" />

•	Tạo mô hình Mở: nano django_app/pawnshop/models.py

<img width="574" height="280" alt="image" src="https://github.com/user-attachments/assets/1b3c8e18-038a-4c4b-9e72-5d434dc8cc11" />






Chạy migration docker compose exec django python manage.py makemigrations
•	Di chuyển cơ sở dữ liệu bằng docker compose exec django python manage.py migrate

 
<img width="707" height="407" alt="image" src="https://github.com/user-attachments/assets/2284ef85-5947-4915-85e1-6bc989b6d64d" />






•	Tạo tài khoản admin docker compose exec django python manage.py createsuperuser

  <img width="655" height="263" alt="image" src="https://github.com/user-attachments/assets/88af98c9-ea6c-40b8-85f8-fcc9aca0aa71" />

•	Cho admin quản lý bảng Mở: nano django_app/pawnshop/admin.py
 <img width="592" height="451" alt="image" src="https://github.com/user-attachments/assets/4ee7b215-1f72-453f-855a-e0ca5d56bb91" />

•	Chạy Django
o	docker compose down
o	docker compose up -d --build
•	Test web Mở trình duyệt Ubuntu: http://localhost:8000
•	hoặc : http://127.0.0.1:8000/admin

 <img width="475" height="198" alt="image" src="https://github.com/user-attachments/assets/a994304e-fbf3-4341-a0d8-1624eb4bf494" />

•	Tạo thư mục templates Mở terminal Ubuntu: mkdir -p django_app/pawnshop/templates Tạo file home.html nano django_app/pawnshop/templates/home.html
 <img width="411" height="398" alt="image" src="https://github.com/user-attachments/assets/5cbaf3a7-eaeb-4513-818a-f729a30090b8" />

•	Mở views.py nano django_app/pawnshop/views.py
 <img width="440" height="409" alt="image" src="https://github.com/user-attachments/assets/c8f8c993-3793-479a-9605-ed785b7640ef" />

•	Tạo urls.py cho app nano django_app/config/urls.py
 <img width="530" height="230" alt="image" src="https://github.com/user-attachments/assets/e5055fd6-b5c9-44bf-9175-56ea3802720b" />

•	Kiểm tra dữ liệu bằng phpMyAdmin
 
<img width="500" height="401" alt="image" src="https://github.com/user-attachments/assets/1b10a9f6-b2cf-4cff-a30e-fd035b088bc6" />


 

•	Public website bằng Cloudflare Tunnel > - đã có container: cloudflared nên giờ chỉ cần cấu hình tunnel. > - Kiểm tra cloudflared đang chạy: docker logs cloudflared
  






















 







A. Đăng ký tên miền xịn cho cá nhân

Đăng kí domain

Đăng kí tên miền tại: https://www.matbao.net/
Tên miền đã đăng kí thành công: vva11004.id.vn
<img width="1919" height="863" alt="image" src="https://github.com/user-attachments/assets/12c4a353-b796-4deb-a803-f13d1afa3728" />

Đăng kí tài khoản cloudflare
Truy cập trang đăng kí bằng đường dẫn: https://dash.cloudflare.com/login
Sau khi truy cập vào rồi có 3 tuỳ chọn đăng nhập hoặc đăng kí
Ở đây ta chọn đăng nhập bằng tài khoản Github
<img width="1567" height="705" alt="image" src="https://github.com/user-attachments/assets/5afa3411-2aed-4153-a6ea-437e2d5cc09a" />

Thêm domain đã đăng ký vào trong cloudflare

Vào Account home -> Chọn dấu "+" phần domain để thêm tên miền
<img width="1918" height="862" alt="image" src="https://github.com/user-attachments/assets/19bec441-42c5-49c1-a4f8-0d78234732c5" />

Ở mục Enter an existing domain Or register a new domain, nhập domain đã đăng kí:
vva11004.id.vn
Còn lại mọi thứ để mặc định và ấn Continue
<img width="1918" height="862" alt="image" src="https://github.com/user-attachments/assets/d61f9918-a324-42bd-ac9b-0dfc6fdcadba" />

Xác nhận DNS
Chọn nút Continue to activation
<img width="1898" height="867" alt="image" src="https://github.com/user-attachments/assets/0d9ca8b2-bdde-4695-b495-1a3a2c365e31" />

Nhận 2 dòng Nameserver (Namespace) do Cloudflare cấp
Sau đó cloudflare sẽ hiển thị: Update your nameservers to activate Cloudflare
Ở mục 2 là "Replace your current nameservers with Cloudflare nameservers", có xuất hiện 2 dòng mà cloudflare cấp:
leif.ns.cloudflare.com
paige.ns.cloudflare.com
<img width="1892" height="865" alt="image" src="https://github.com/user-attachments/assets/57db6f34-2c93-48de-a40e-c9c330fcb363" />

Nhập 2 dòng namespace của cloudflare vào trong trang quản lý DNS record của tên miền đăng ký

Đăng nhập vàp trang quản lý domain đã đăng kí
Ở mục "quản trị tên miền" chọn Name Server -> chọn "sử dụng Name Server tuỳ chỉnh"
Thêm 2 name server vừa được nhận sau đó ấn "lưu thay đổi"
Quay lại cloudflare để xác nhận cập nhật DNS
Cloudflare thông báo "Your domain is now protected by Cloudflare" là đã thành công

bài tập PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG

họ và tên : bùi ngọc anh

lớp k58.ktp

mssv : k225510201001

đề bài : Xây dựng một ứng dụng di động hoàn chỉnh trên nền tảng MIT App Inventor đáp ứng các tiêu chí kỹ thuật

bài làm

truy cập MIT App Inventor và tạo project

<img width="1344" height="592" alt="Image" src="https://github.com/user-attachments/assets/89ff5b0d-ab34-4b49-b86a-ee8ff2a6430b" />

Ở phía trên cùng, bấm nút Add Screen để tạo đủ 3 Screen

<img width="1338" height="645" alt="Image" src="https://github.com/user-attachments/assets/28e86735-805a-4fb8-b335-f57cc2f54eda" />

tạo các label thông tin cá nhân 

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/6a0219a3-9324-4715-ad50-3ab4efdbcf18" />

hoàn thiện Screen1 :

đổi text

thêm botton

<img width="1357" height="663" alt="Image" src="https://github.com/user-attachments/assets/7a78a220-d5de-48aa-9dca-b3ad0ea095df" />

<img width="1324" height="657" alt="Image" src="https://github.com/user-attachments/assets/138ddaa4-458e-44de-9a3e-4eed7f57d516" />

#Screen2

Cấu hình Screen (Giải phương trình bậc nhất ax + b = 0) 

Thiết kế giao diện 

<img width="1357" height="663" alt="Image" src="https://github.com/user-attachments/assets/2cd5faf3-2014-49a6-9b7b-818d1a7e0480" />

### 1. Thuật toán biện luận phương trình trong khối `tinhnghiem.Click`

Sử dụng cấu trúc rẽ nhánh điều kiện `if - else if - else` để kiểm tra các trường hợp của hệ số $a$ và $b$:

* **Trường hợp 1 (Vô số nghiệm):** * **Điều kiện (`if`):** Cả hai hệ số cùng bằng 0 (`txtA.Text = 0` AND `txtB.Text = 0`).
  * **Hành động:** Hệ thống sử dụng khối `join` để nối chuỗi hiển thị lại phương trình dạng `Phương trình: 0x + 0 = 0` và in ra kết quả `-> Kết quả: Phương trình có vô số nghiệm`.
* **Trường hợp 2 (Vô nghiệm):** * **Điều kiện (`else if`):** Hệ số $a = 0$ nhưng hệ số $b \neq 0$ (lúc này chỉ cần kiểm tra `txtA.Text = 0` vì trường hợp cả hai bằng 0 đã bị chặn ở trên).
  * **Hành động:** Hiển thị lại phương trình dạng `Phương trình: 0x + [b] = 0` và in ra kết quả `-> Kết quả: Phương trình vô nghiệm`.
* **Trường hợp 3 (Có nghiệm duy nhất):**
  * **Điều kiện (`else`):** Hệ số $a \neq 0$.
  * **Hành động:** Tính toán nghiệm theo công thức $x = -b/a$ (sử dụng các khối toán học `Math` thực hiện phép tính `(0 - txtB.Text) / txtA.Text`). Kết quả hiển thị đầy đủ bao gồm dạng phương trình ban đầu và giá trị nghiệm cụ thể.

### 2. Kỹ thuật tối ưu hiển thị giao diện nâng cao

* **Khối `join` mở rộng:** Thay vì chỉ hiển thị thông báo nghiệm đơn thuần, ứng dụng sử dụng khối `join` cấu trúc 7 mắt xích (inputs) nhằm tái hiện lại toàn bộ phương trình mà người dùng vừa nhập trước khi trả kết quả, giúp tăng tính trực quan.
* **Ký tự xuống dòng (`\n`):** Được tích hợp vào giữa chuỗi văn bản của khối `join` nhằm mục đích ngắt dòng tự động trên màn hình thiết bị, phân tách rõ ràng giữa phần "Phương trình" và phần "Kết quả hiển thị" giúp giao diện không bị rối mắt.

### 3. Điều hướng ứng dụng (`quayve.Click`)

* Sử dụng khối lệnh `open another screen screenName` gắn với chuỗi văn bản cố định `"Screen1"` để giải phóng ngữ cảnh hiện tại và đưa người dùng quay trở lại màn hình chính (Màn hình Giới thiệu/About) một cách an toàn.

* <img width="1339" height="630" alt="Image" src="https://github.com/user-attachments/assets/0717ae3a-459f-4988-877e-c72edbbec351" />


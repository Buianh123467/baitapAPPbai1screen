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

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/677af0fe-51ba-4358-ae48-58feb8fb385f" />

### . Thuật toán biện luận phương trình trong khối `tinhnghiem.Click`

Sử dụng cấu trúc rẽ nhánh điều kiện `if - else if - else` để kiểm tra các trường hợp của hệ số $a$ và $b$:

* **Trường hợp 1 (Vô số nghiệm):** * **Điều kiện (`if`):** Cả hai hệ số cùng bằng 0 (`txtA.Text = 0` AND `txtB.Text = 0`).
  * **Hành động:** Hệ thống sử dụng khối `join` để nối chuỗi hiển thị lại phương trình dạng `Phương trình: 0x + 0 = 0` và in ra kết quả `-> Kết quả: Phương trình có vô số nghiệm`.
* **Trường hợp 2 (Vô nghiệm):** * **Điều kiện (`else if`):** Hệ số $a = 0$ nhưng hệ số $b \neq 0$ (lúc này chỉ cần kiểm tra `txtA.Text = 0` vì trường hợp cả hai bằng 0 đã bị chặn ở trên).
  * **Hành động:** Hiển thị lại phương trình dạng `Phương trình: 0x + [b] = 0` và in ra kết quả `-> Kết quả: Phương trình vô nghiệm`.
* **Trường hợp 3 (Có nghiệm duy nhất):**
  * **Điều kiện (`else`):** Hệ số $a \neq 0$.
  * **Hành động:** Tính toán nghiệm theo công thức $x = -b/a$ (sử dụng các khối toán học `Math` thực hiện phép tính `(0 - txtB.Text) / txtA.Text`). Kết quả hiển thị đầy đủ bao gồm dạng phương trình ban đầu và giá trị nghiệm cụ thể.

### . Kỹ thuật tối ưu hiển thị giao diện nâng cao

* **Khối `join` mở rộng:** Thay vì chỉ hiển thị thông báo nghiệm đơn thuần, ứng dụng sử dụng khối `join` cấu trúc 7 mắt xích (inputs) nhằm tái hiện lại toàn bộ phương trình mà người dùng vừa nhập trước khi trả kết quả, giúp tăng tính trực quan.
* **Ký tự xuống dòng (`\n`):** Được tích hợp vào giữa chuỗi văn bản của khối `join` nhằm mục đích ngắt dòng tự động trên màn hình thiết bị, phân tách rõ ràng giữa phần "Phương trình" và phần "Kết quả hiển thị" giúp giao diện không bị rối mắt.

### . Điều hướng ứng dụng (`quayve.Click`)

* Sử dụng khối lệnh `open another screen screenName` gắn với chuỗi văn bản cố định `"Screen1"` để giải phóng ngữ cảnh hiện tại và đưa người dùng quay trở lại màn hình chính (Màn hình Giới thiệu/About) một cách an toàn.

* <img width="1339" height="630" alt="Image" src="https://github.com/user-attachments/assets/0717ae3a-459f-4988-877e-c72edbbec351" />

#screen3

Trình Duyệt Nội Bộ Tốc Độ Cao (Screen3)

Kéo thành phần WebViewer1 trong mục User Interface thả vào màn hình.

thêm botton : QUAY VỀ TRANG CHỦ 

tìm ô HomeUrl.

Gõ địa chỉ trang web bạn muốn nó hiện ra : https://k58kmt.tdh.io.vn/

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/95386765-ab96-4686-89f2-b98a29f0eb93" />

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/a4a029af-e825-4fff-8924-1ea3ac2fc757" />

## Chi tiết lập trình Logic (Blocks) - Màn hình Xem Website (Screen3_web)

Màn hình này tích hợp trình duyệt nhúng giúp người dùng có thể tương tác trực tiếp với các tài nguyên web ngoại vi mà không cần rời khỏi ứng dụng.

### 1. Thành phần WebViewer
* **Chức năng:** Sử dụng đối tượng `WebViewer` để hiển thị trang web đích đã cấu hình sẵn trong thuộc tính `HomeUrl` (địa chỉ: `https://k58kmt.tdh.io.vn/`). Trang web tự động tải ngay khi màn hình này được khởi tạo.

### 2. Logic điều hướng nút quay lại (`btn_vehome.Click`)
* **Hành động:** Khi người dùng tương tác với nút lệnh "Quay lại Trang chủ" (`btn_vehome`), hệ thống gọi khối xử lý `open another screen screenName` truyền vào nhãn chuỗi `"Screen1"`. 
* **Mục đích:** Đóng ngữ cảnh duyệt web hiện tại, giải phóng tài nguyên hệ thống và đưa người dùng an toàn trở lại màn hình bảng điều khiển chính (About screen).

Mở MIT AI2 Companion trên điện thoại và kết nối với máy tính qua AI Companion

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/84cfc6d7-c5af-4f69-ab2f-39a05d8c9db8" />

Test ứng dụng trên điện thoại

Giải Phương trình Ax + B = 0

hệ só A = 15

hệ số B = 14

kết quả Nghiệm X = -1.07143

<img width="1920" height="2560" alt="Image" src="https://github.com/user-attachments/assets/328a97c6-e2bd-4330-a338-29d84ed62142" />


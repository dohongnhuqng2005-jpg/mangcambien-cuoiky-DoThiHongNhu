# TIỂU LUẬN CUỐI KỲ: MẠNG CẢM BIẾN (ELE1421)
* **Học phần:** Mạng cảm biến (ELE1421) -- Lớp D23CQCI01-N
* **Sinh viên thực hiện:** Đỗ Thị Hồng Như
* **Đề tài:** Voice control robot hút bụi.
* **Mã định danh dự án trên Edge Impulse:** N23DCCI053

---

## 1. Các thành phần tệp tin trong kho lưu trữ
Kho lưu trữ bao gồm 2 thành phần cốt lõi được đóng gói dưới dạng file nén:
* `datasheet.zip`: Bộ dữ liệu mẫu gồm toàn bộ các tệp âm thanh thô (định dạng .wav, tần số lấy mẫu 16000Hz) do chính sinh viên thực hiện thu âm để huấn luyện mô hình.
* `ei-n23dcci053-arduino-1.0.81-impulse-#4.zip`: Bộ thư viện mã nguồn được cấu hình và xuất bản trực tiếp từ Edge Impulse (định dạng Quantized int8). Thư viện đã tích hợp sẵn thuật toán trích xuất đặc trưng MFCC, mạng thần kinh phân loại lớp và các file code cấu hình microphone chạy trực tiếp trên vi điều khiển Arduino.

## 2. Các nhãn khẩu lệnh hệ thống nhận diện
Mô hình TinyML bên trong thư viện được huấn luyện cá nhân hóa để phân loại chính xác 5 trạng thái âm thanh:
1. `hồng như` (Từ khóa kích hoạt hệ thống)
2. `bắt đầu` (Lệnh vận hành robot)
3. `về sạc` (Lệnh điều khiển robot về trạm sạc)
4. `dừng` (Lệnh dừng khẩn cấp)
5. `noise` (Tạp âm môi trường để lọc kích hoạt nhầm)

## 3. Hướng dẫn tích hợp thư viện vào Arduino IDE
1. Tải file thư viện nén `ei-n23dcci053-arduino-1.0.81-impulse-#4.zip` từ kho lưu trữ này về máy tính.
2. Mở phần mềm **Arduino IDE** lên.
3. Chọn `Sketch` -> `Include Library` -> `Add .ZIP Library...` và chọn file vừa tải để tích hợp vào hệ thống.
4. Sau khi tích hợp thành công, người dùng có thể truy cập vào `File` -> `Examples` -> `N23DCCI053_Inferencing` để mở các đoạn mã nguồn mẫu chạy thực tế với microphone phần cứng mà không cần lập trình lại từ đầu.

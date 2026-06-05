# TIỂU LUẬN CUỐI KỲ: MẠNG CẢM BIẾN (ELE1421)
* **Học phần:** Mạng cảm biến (ELE1421) -- Lớp D23CQCI01-N
* **Sinh viên thực hiện:** Đỗ Thị Hồng Như
* **Đề tài:** Voice control robot hút bụi.
* **Mã định danh dự án trên Edge Impulse:** N23DCCI053

---

## 1. Cấu trúc thư mục kho lưu trữ
* `/Firmware_EdgeImpulse`: Chứa bộ thư viện nén mã nguồn `.zip` được xuất bản trực tiếp từ Edge Impulse (định dạng Quantized int8 tối ưu bộ nhớ).
* `/Arduino_Code`: Chứa file mã nguồn chính `.ino` chạy trên bo mạch vi điều khiển Arduino để đọc tín hiệu microphone và phân loại khẩu lệnh.
* `/Docs`: Chứa file slide thuyết trình của đề tài.

## 2. Các nhãn khẩu lệnh hệ thống nhận diện
Mô hình mạng thần kinh TinyML được huấn luyện cá nhân hóa để phân loại chính xác 5 trạng thái âm thanh:
1. `hồng như` (Từ khóa kích hoạt hệ thống)
2. `bắt đầu` (Lệnh vận hành robot)
3. `về sạc` (Lệnh điều khiển robot về trạm sạc)
4. `dừng` (Lệnh dừng khẩn cấp)
5. `noise` (Tạp âm môi trường để lọc kích hoạt nhầm)

## 3. Hướng dẫn cài đặt và chạy thực tế
1. Tải toàn bộ kho lưu trữ này về máy tính dưới dạng file .zip.
2. Mở phần mềm **Arduino IDE** lên.
3. Chọn `Sketch` -> `Include Library` -> `Add .ZIP Library...` và chọn file thư viện nén trong thư mục `/Firmware_EdgeImpulse`.
4. Vào `File` -> `Examples` -> Tìm tên dự án `N23DCCI053` -> Mở mã nguồn demo microphone tương ứng với bo mạch Arduino.
5. Kết nối bo mạch Arduino vào máy tính và bấm **Upload** để nạp code xuống thiết bị biên.

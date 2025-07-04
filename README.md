# Hướng dẫn cài đặt và chạy dự án Taskify

## Cách cài và chạy dự án

### I. Clone dự án (hoặc tải file zip)
Clone dự án bằng lệnh:

hoặc tải file zip từ GitHub và giải nén.

### II. Chạy server backend
Mở thư mục vừa clone về, vào thư mục `backend`, mở terminal và chạy server backend (tùy công nghệ backend sử dụng).

### III. Import frontend vào Android Studio
Quay lại thư mục vừa clone, vào `frontend/app`, mở thư mục `app` bằng Android Studio để IDE nhận diện dự án. Đợi vài phút để Android Studio tự động import và cài đặt các thư viện cần thiết.

### IV. Cách chạy

#### TH1. Chạy bằng máy ảo Android Studio
- Mở file `com.example.taskify.common.Constants`, thay `ipv4_address` trong `BASE_URL` thành `10.0.2.2`.
- Mở file `res/xml/network_security_config.xml`, thay `ipv4_address` trong domain thành `10.0.2.2`.
- Ấn **Run** trong Android Studio để chạy ứng dụng.

#### TH2. Chạy trên thiết bị Android thật (máy tính và thiết bị cùng mạng LAN)
1. **Lấy địa chỉ IPv4 của máy tính**
   - **Windows:** Mở CMD hoặc PowerShell, nhập:
     ```
     ipconfig
     ```
     Tìm dòng `IPv4 Address` trong phần `Wireless LAN adapter Wi-Fi`, ví dụ:
     ```
     IPv4 Address. . . . . . . . . . . : 192.168.xxx.xxx
     ```
     Đây là IPv4 cần lấy.

   - **macOS:** 
     ```
     networksetup -listallhardwareports
     ```
     Xác định thiết bị Wi-Fi (ví dụ `en0`), sau đó:
     ```
     ifconfig en0
     ```
     Tìm dòng bắt đầu bằng `inet` (không phải `inet6`), ví dụ:
     ```
     inet 192.168.1.100 ...
     ```
     Đây là IPv4 cần lấy.

2. **Kết nối thiết bị thật với Android Studio**
   Bật **Gỡ lỗi không dây (Wireless Debugging)** trong cài đặt nhà phát triển trên thiết bị Android và kết nối với Android Studio.

3. **Cấu hình địa chỉ IP**
   - Mở `com.example.taskify.common.Constants`, thay `ipv4_address` trong `BASE_URL` thành IPv4 vừa lấy.
   - Mở `res/xml/network_security_config.xml`, thay `ipv4_address` trong domain thành IPv4 vừa lấy.

4. **Chạy ứng dụng**
   Ấn **Run** trong Android Studio để chạy ứng dụng trên thiết bị thật.

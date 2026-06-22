  # BÁO CÁO BÀI THỰC HÀNH LAB 9: KIỂM THỬ TỰ ĐỘNG VỚI SELENIUM (KATALON RECORDER)

## 1. MỤC TIÊU BÀI LAB
- **Kiến thức:** Tiếp cận và hiểu rõ nguyên lý vận hành của kiểm thử tự động (Automation Testing) trên giao diện người dùng (UI Testing).
- **Công cụ:** Thành thạo cách cài đặt, cấu hình và sử dụng công cụ **Katalon Recorder** để thực hiện ghi nhận kịch bản (Record), quản lý cấu trúc lệnh và thực thi lại tự động (Playback).
- **Kỹ năng:** Phân tích giao diện Web (UI), thiết kế kịch bản kiểm thử (Test Cases) hoàn chỉnh cho luồng tính năng cốt lõi của một hệ thống thương mại điện tử và đánh giá trạng thái đạt/không đạt (Pass/Fail) của hệ thống.

## 2. MÔI TRƯỜNG VÀ ĐỐI TƯỢNG KIỂM THỬ
- **Công cụ thực hiện chính:** **Katalon Recorder Extension** (Nền tảng kiểm thử tự động trực quan).
- **Ngôn ngữ kịch bản cấu phần:** Java WebDriver (JUnit Framework).
- **Website thử nghiệm:** Automation Exercise 
- **Trang đích thực hiện kịch bản:** `https://automationexercise.com/product_details/3` (Trang thông tin chi tiết của sản phẩm cụ thể mã số 3).

## 3. KỊCH BẢN KIỂM THỬ CHI TIẾT (TEST CASES)

Toàn bộ luồng kiểm thử được tích hợp liên tục (End-to-End) thông qua công cụ **Katalon Recorder** bao gồm các Test Case vận hành tuần tự như sau:

### 3.1. Test Case 1: Khởi tạo và Điều hướng hệ thống
- **Mục đích:** Xác thực khả năng truy cập và điều hướng trực tiếp của trình duyệt đến trang sản phẩm mục tiêu.
- **Các bước thực hiện:**
  1. Sử dụng lệnh `open` trên **Katalon Recorder** để truy cập thẳng vào trang chi tiết sản phẩm: `https://automationexercise.com/product_details/3`.
  2. Hệ thống tự động thực hiện các bước điều hướng phụ trên UI để đồng bộ trạng thái trang.
- **Kết quả mong đợi (Expected Result):** Trình duyệt mở ra đúng trang chi tiết của sản phẩm ID số 3, giao diện tải đầy đủ thông tin mà không bị lỗi.

### 3.2. Test Case 2: Tính năng Tìm kiếm sản phẩm (Search Product)
- **Mục đích:** Đảm bảo ô tìm kiếm hoạt động chính xác khi người dùng thực hiện lọc sản phẩm bằng từ khóa.
- **Các bước thực hiện:**
  1. Click chuột vào mục `Products` trên thanh menu điều hướng chính.
  2. Di chuyển đến ô tìm kiếm (`id=search_product`), nhập từ khóa: `"dress"`.
  3. Click vào nút Tìm kiếm (`id=submit_search`) để kích hoạt lệnh lọc dữ liệu.
- **Kết quả mong đợi (Expected Result):** Hệ thống chuyển hướng thành công sang trang danh sách sản phẩm và hiển thị các mặt hàng liên quan tới từ khóa "dress".

### 3.3. Test Case 3: Tính năng Xem và Thêm sản phẩm vào giỏ hàng (Add to Cart)
- **Mục đích:** Xác thực tính năng xử lý của nút chức năng thêm hàng và cửa sổ thông báo (Popup Modal).
- **Các bước thực hiện:**
  1. Từ danh sách kết quả tìm kiếm, bấm chọn `View Product` để vào lại trang chi tiết.
  2. Nhấn chuột vào nút `Add to cart` (Màu cam) để đưa sản phẩm vào giỏ.
  3. Khi cửa sổ Popup modal xác nhận thêm thành công hiện lên, click vào nút `Continue Shopping` để đóng bảng thông báo.
- **Kết quả mong đợi (Expected Result):** Sản phẩm được ghi nhận vào giỏ hàng thành công, popup đóng lại mượt mà, hệ thống không xảy ra xung đột giao diện.

## 4. KẾT QUẢ THỰC THI (TEST RESULTS)

Khi kích hoạt tính năng **"Play Test Case"** (Playback) trên **Katalon Recorder**, công cụ đã tự động thực thi lại toàn bộ chuỗi hành động trên một cách trơn tru.

### 4.1. Minh chứng giao diện thực thi thành công (Status: Passed 100%)
Toàn bộ các dòng lệnh trong kịch bản đều chuyển sang màu xanh lá cây, hệ thống ghi nhận trạng thái **Passed: 1** ở thanh Workspace và xuất nhật ký dòng lệnh `[info] Test case passed` thành công hoàn toàn.

*(Hình ảnh minh chứng kết quả chạy Playback thực tế trên trình duyệt)*
<img width="605" height="354" alt="katalon" src="https://github.com/user-attachments/assets/7aa74c52-f345-42f0-82e7-79312e35bb67" />

### 4.2. File mã nguồn đính kèm (Source Code)
Để tăng tính chuyên nghiệp và sẵn sàng mở rộng dự án, kịch bản kiểm thử trên đã được xuất (Export) trực tiếp ra mã nguồn ngôn ngữ lập trình. 
- **Tên file đính kèm:** `KatalonSeleniumTest.java` (Sử dụng cấu trúc `Java (WebDriver + JUnit)`) được lưu trữ ngay trong thư mục gốc của Repository này.

## 5. KẾT LUẬN & BÀI HỌC KINH NGHIỆM
- **Kết quả đạt được:** Hoàn thành trọn vẹn 100% yêu cầu nội dung bài thực hành Lab 9. Bộ mã kiểm thử tự động chạy ổn định, chính xác, định vị các phần tử (Element Locators) trên trang sản phẩm số 3 chuẩn xác thông qua các thuộc tính ID, LinkText và XPath mà không sinh ra lỗi gián đoạn.
- **Bài học rút ra:** 
  - Thấy rõ sự tối ưu vượt trội của Kiểm thử tự động (Automation Testing) thông qua công cụ **Katalon Recorder** so với Kiểm thử thủ công (Manual Testing) về mặt tốc độ và độ chính xác.
  - Nắm vững cơ chế định vị phần tử trực tiếp từ một URL chỉ định (`/product_details/3`), tạo tiền đề tư duy vững chắc cho việc phát triển các Framework Automation chuyên sâu bằng mã code sau này.

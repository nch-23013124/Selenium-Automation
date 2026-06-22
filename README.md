# BÁO CÁO BÀI THỰC HÀNH LAB 9: KIỂM THỬ TỰ ĐỘNG VỚI SELENIUM (KATALON RECORDER)

---

## 1. MỤC TIÊU BÀI LAB
- **Về kiến thức:** Tiếp cận và hiểu rõ nguyên lý vận hành của kiểm thử tự động (Automation Testing) trên giao diện người dùng (UI Testing).
- **Về công cụ:** Thành thạo cách cài đặt, cấu hình và sử dụng công cụ Katalon Recorder (nền tảng cải tiến của Selenium) để thực hiện ghi nhận kịch bản (Record), chỉnh sửa cấu trúc lệnh và thực thi lại tự động (Playback).
- **Về kỹ năng:** Phân tích giao diện Web (UI), thiết kế kịch bản kiểm thử (Test Cases) hoàn chỉnh cho luồng tính năng cốt lõi của một hệ thống thương mại điện tử và đánh giá trạng thái đạt/không đạt (Pass/Fail) của hệ thống.

---

## 2. MÔI TRƯỜNG VÀ ĐỐI TƯỢNG KIỂM THỬ
- **Công cụ thực hiện:** Khung kiểm thử tự động Katalon Recorder Extension (Trình duyệt Google Chrome).
- **Ngôn ngữ kịch bản cấu phần:** Java WebDriver (JUnit Framework).
- **Website thử nghiệm:** Automation Exercise (`https://automationexercise.com/`) - Website giả lập môi trường thương mại điện tử chuyên dụng cho việc kiểm thử phần mềm.

---

## 3. KỊCH BẢN KIỂM THỬ CHI TIẾT (TEST CASES)

Toàn bộ luồng kiểm thử được tích hợp liên tục (End-to-End) bao gồm 03 Test Case độc lập vận hành tuần tự:

### 3.1. Test Case 1: Tính năng Tìm kiếm sản phẩm (Search Product)
- **Mục đích:** Đảm bảo hệ thống lọc và hiển thị đúng sản phẩm theo từ khóa người dùng nhập.
- **Các bước thực hiện:**
  1. Truy cập vào trang chủ hệ thống `https://automationexercise.com/`.
  2. Click chuột vào danh mục `Products` trên thanh menu điều hướng chính.
  3. Di chuyển đến ô tìm kiếm (`id=search_product`), nhập từ khóa: `"dress"`.
  4. Click vào nút Tìm kiếm (`id=submit_search`) để kích hoạt lệnh lọc dữ liệu.
- **Kết quả mong đợi (Expected Result):** Hệ thống chuyển hướng thành công sang trang danh sách sản phẩm và hiển thị các mặt hàng liên quan tới từ khóa "dress".

### 3.2. Test Case 2: Tính năng Xem chi tiết sản phẩm (View Product Details)
- **Mục đích:** Kiểm tra tính năng chuyển hướng dữ liệu và hiển thị thông tin chi tiết của một sản phẩm cụ thể.
- **Các bước thực hiện:**
  1. Từ danh sách sản phẩm váy vừa tìm kiếm, cuộn xuống sản phẩm đầu tiên.
  2. Click trực tiếp vào liên kết chữ `View Product`.
- **Kết quả mong đợi (Expected Result):** Trình duyệt mở ra trang chi tiết sản phẩm, hiển thị đầy đủ thông tin về tên sản phẩm, giá cả, thương hiệu và trạng thái kho hàng.

### 3.3. Test Case 3: Tính năng Thêm sản phẩm vào giỏ hàng (Add to Cart)
- **Mục đích:** Xác thực tính năng xử lý bất đồng bộ (Async UI) khi người dùng thêm hàng vào giỏ.
- **Các bước thực hiện:**
  1. Tại trang chi tiết sản phẩm, nhấn chuột vào nút `Add to cart` (Màu cam).
  2. Khi cửa sổ Popup modal xác nhận thêm thành công hiện lên, click vào nút `Continue Shopping` để đóng bảng thông báo và tiếp tục trải nghiệm.
- **Kết quả mong đợi (Expected Result):** Sản phẩm được ghi nhận vào cơ sở dữ liệu tạm thời của giỏ hàng, hệ thống không xảy ra xung đột hay treo giao diện.

---

## 4. KẾT QUẢ THỰC THI (TEST RESULTS)

Khi kích hoạt tính năng **"Play Test Case"** (Playback) trên Katalon Recorder, hệ thống đã tự động thực thi lại toàn bộ chuỗi hành động trên mà không cần sự can thiệp thủ công từ con người.

### 4.1. Minh chứng giao diện thực thi thành công (Status: Passed 100%)
Toàn bộ các dòng lệnh trong kịch bản đều chuyển sang màu xanh lá cây, hệ thống ghi nhận trạng thái **Passed: 1** ở thanh Workspace và xuất nhật ký dòng lệnh `[info] Test case passed` thành công hoàn toàn.

*(Hình ảnh minh chứng kết quả chạy Playback thực tế trên trình duyệt)*
![Katalon Test Passed](./image_1e5c31.png)

### 4.2. File mã nguồn đính kèm (Source Code)
Để tăng tính chuyên nghiệp và sẵn sàng mở rộng dự án, kịch bản kiểm thử trên đã được xuất (Export) trực tiếp ra mã nguồn ngôn ngữ lập trình. 
- **Tên file đính kèm:** `KatalonSeleniumTest.java` (Sử dụng cấu trúc `Java (WebDriver + JUnit)`) được lưu trữ ngay trong thư mục gốc của Repository này.

---

## 5. KẾT LUẬN & BÀI HỌC KINH NGHIỆM
- **Kết quả đạt được:** Hoàn thành trọn vẹn 100% yêu cầu nội dung bài thực hành Lab 9. Bộ mã kiểm thử tự động chạy ổn định, chính xác, định vị các phần tử (Element Locators) trên trang web chuẩn xác thông qua các thuộc tính ID, LinkText và XPath mà không sinh ra lỗi gián đoạn.
- **Bài học rút ra:** 
  - Thấy rõ sự tối ưu vượt trội của Kiểm thử tự động (Automation Testing) so với Kiểm thử thủ công (Manual Testing) về mặt tốc độ, độ chính xác và khả năng tái sử dụng để chạy kiểm thử hồi quy (Regression Testing).
  - Nắm vững cách thức mà một mã nguồn Selenium can thiệp, tương tác với các đối tượng DOM trên trình duyệt, tạo tiền đề tư duy vững chắc cho việc phát triển các Framework Automation chuyên sâu bằng mã code sau này.

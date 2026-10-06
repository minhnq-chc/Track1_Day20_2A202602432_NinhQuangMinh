# Track 1 - Day 20 - Product Metrics Lab
**Học viên:** Ninh Quang Minh
**Mã học viên:** 2A202602432

---

## 1. Thông tin Dự án (Project Context)
**Tên dự án:** AI Game Report Assistant (Trợ lý AI phân tích dữ liệu Game)

**Vấn đề (Pain-point):** Trong các studio game, PM và UA Manager thường mất hàng giờ mỗi tuần để kéo số liệu thô từ nhiều nền tảng (AppsFlyer, Meta Ads, Google Ads, Firebase, internal BI), gộp vào bảng tính và tính toán các chỉ số phức tạp (ROAS cohort, Payback, Funnel). Việc này không những dễ sai sót mà còn làm chậm trễ quá trình ra quyết định tối ưu ngân sách.

**Giải pháp:** Xây dựng một trợ lý AI tự động kết nối API các nguồn, xử lý dữ liệu và sinh ra một bản báo cáo định kỳ hoàn chỉnh (được trực quan hóa bằng HTML/Charts). Hệ thống không chỉ cung cấp số liệu mà còn tự động highlight các insight bất thường (CPI tăng, retention tụt) và đề xuất Next Actions.

---

## 2. Link tệp Metrics Pack & Bản Demo
Toàn bộ chuỗi quyết định (từ Core Action → Cadence → Metric → Loop → Tracking) và **Bản Demo Báo cáo thực tế** (Output của AI Assistant) được tích hợp gọn gàng trong cùng một tệp HTML duy nhất. Giao diện được thiết kế theo phong cách *Liquid Glass* để dễ dàng đọc và đánh giá.

👉 **[Mở xem file metrics-pack.html](./metrics-pack.html)**

> 💡 **Hướng dẫn xem:** Hãy dùng *Live Server* hoặc mở trực tiếp file HTML trên trình duyệt. Trong file có nút **📊 Xem Demo Output** ở góc phải trên cùng. Khi click vào, giao diện sẽ chuyển sang một bản báo cáo minh họa do AI sinh ra (dữ liệu đã được ẩn danh).

---

## 3. Tóm tắt Quá trình ra quyết định
*   **Core Action:** `report_reviewed` (Review xong báo cáo định kỳ). Nhấn mạnh vào việc user *thực sự tiêu thụ thông tin* thay vì chỉ việc hệ thống sinh ra báo cáo.
*   **Natural Cadence:** `Weekly / Monthly`. Quyết định ngân sách UA diễn ra theo tuần, và việc phân tích ROAS cohort/LTV yêu cầu dữ liệu phải có độ chín (maturity) theo tháng. Việc ép đo theo ngày (Daily) là vô nghĩa.
*   **North Star Metric:** Số lượng báo cáo được review sâu mỗi tuần (Weekly Deep-Reviewed Reports), đi kèm điều kiện Dwell Time > 1 phút (Quality threshold).
*   **Counter-metric:** Tỉ lệ report bị bỏ qua (Ignored Report Rate) và số lần phải xuất raw data (Export Raw Data Count) để kiểm soát việc AI báo cáo lan man hoặc thiếu insight cốt lõi.

---

## 4. Điều tôi mang về áp dụng cho dự án thật
1. **Phân định rạch ròi "Output hệ thống" và "Hành vi sinh giá trị":** Trước đây, tôi hay nhầm lẫn việc đo số lượng báo cáo được tạo (`report_generated`) là thành công của tính năng. Qua bài Lab, tôi nhận ra đó chỉ là "máy làm". Giá trị cốt lõi chỉ hình thành khi "người dùng" tiêu thụ nó (`report_reviewed`) và đưa ra được quyết định.
2. **Thoát khỏi cái bẫy "Habitual Dashboarding" (Mặc định đo DAU/D1/D7):** Nhờ việc bóc tách nature của hành vi, tôi tự tin bỏ qua các mốc D1/D7 quen thuộc. Đối với các sản phẩm dữ liệu nội bộ (B2B Tools), người dùng quay lại theo lịch làm việc (Weekly Bracket: W1, W2...). Ép một sản phẩm WAU thành DAU chỉ tạo ra các "tính năng rác" (như notification spam).
3. **Product Loop sinh ra từ Workflow thực tế:** Vòng lặp sản phẩm mạnh mẽ nhất không phải là gamification (huy hiệu, chuỗi streak), mà là việc sản phẩm chèn được vào quy trình làm việc tự nhiên. (Chốt số tuần $\rightarrow$ Review báo cáo $\rightarrow$ Action chỉnh budget $\rightarrow$ Chờ kết quả $\rightarrow$ Chốt số tuần mới).

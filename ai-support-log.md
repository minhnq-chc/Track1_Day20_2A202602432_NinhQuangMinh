# AI Support Log

## AI đã giúp tôi ở đâu?
*   **Brainstorming & Cung cấp Framework:** Trong Phase 1, AI đã giúp tôi phác thảo 3 ứng viên cụ thể cho Core Action (1. Tạo & đọc báo cáo; 2. Đào sâu insight; 3. Thực thi hành động) kèm theo các góc nhìn phản biện để tôi dễ dàng so sánh và chọn lọc. Ở Phase 2, AI cũng gợi ý các hướng Cadence phổ biến (Theo chu kỳ vs. Phản ứng theo sự kiện) cho dòng sản phẩm B2B Data.
*   **Hệ thống hóa Metric & Tracking:** Từ Core Action đã chốt, AI hỗ trợ ánh xạ (map) trực tiếp thành các chỉ số cụ thể: đề xuất công thức tính North Star Metric hoàn thiện (đủ Unit + Quality + Frequency), gợi ý Counter-metrics rất thực tế (Ignored Report Rate, Export Raw Data Count) và phác thảo bảng Event Tracking bám sát theo Product Loop.
*   **UI/UX & Trình bày trực quan:** AI đóng vai trò như một "Technical Assistant" đắc lực khi tự động trích xuất cấu trúc CSS/HTML từ một template *Liquid Glass* do tôi cung cấp, sau đó mã hóa (code) toàn bộ nội dung bài Lab lên giao diện đó. Đồng thời, AI còn nhúng (embed) khéo léo một bản Demo Report hoàn chỉnh vào cùng tệp nộp bài với tính năng chuyển đổi tab (Toggle) rất mượt mà.

## AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?
*   **Lỗi "Ép nhịp Daily" theo khuôn mẫu:** Ban đầu, khi phân tích bối cảnh dự án có liên quan đến game, AI có xu hướng mặc định áp dụng các chỉ số Daily (như DAU, D1/D7 Retention) do học theo các khuôn mẫu báo cáo game truyền thống. Nó chưa phân biệt rạch ròi giữa *người chơi game* (chơi hằng ngày) và *người quản lý game* (UA Manager - xem số hằng tuần).
*   **Lỗi "Output hệ thống thay cho Core Action":** Có thời điểm, AI gợi ý hành động "Hệ thống tự động sinh báo cáo" (`report_generated`) làm sự kiện chính cho NSM. Đây là một đề xuất hời hợt vì đó chỉ là output của hệ thống, không phản ánh việc user thực sự nhận được giá trị (nếu user không đọc báo cáo đó thì value = 0).

## Tôi đã tự sửa hoặc quyết định lại điều gì?
*   **Xác định lại Use Case & Core Action:** Tôi là người trực tiếp định hướng dự án (AI Game Report Assistant thay vì phân tích bản thân game bài) và quyết định tách biệt giữa việc "máy làm" và "người làm". Tôi kiên quyết chọn `report_reviewed` làm Activation event và Return event chính.
*   **Bảo vệ quan điểm về Cadence:** Tôi đã phủ quyết các gợi ý đo theo ngày và chốt nhịp độ là **Weekly/Monthly**. Quyết định này hoàn toàn dựa trên kinh nghiệm workflow thực tế của UA/Product Manager (chỉ họp chốt số khi dữ liệu đã kết thúc tuần và cohort đã đủ tuổi trưởng thành).
*   **Định hình cấu trúc & Ẩn danh dữ liệu:** Toàn bộ dữ liệu mẫu, bộ template báo cáo Demo (UI Liquid Glass) và các chỉ số đo lường UA đều do tôi cung cấp từ tài nguyên làm việc thực tế. Tôi giao nhiệm vụ cho AI thực hiện ẩn danh (anonymize) - đổi tên game thành *CasualCard Global*, đổi tên các designer nội bộ, thay đổi tên các quốc gia (thành Tier 1, Tier 2) và làm tròn tỉ giá để đảm bảo bảo mật tuyệt đối trước khi nộp.

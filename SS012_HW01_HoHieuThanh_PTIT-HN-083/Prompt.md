### PROMPT 1: Thiết lập vai trò & Phân tích hệ thống tổng quan

```markdown
Đóng vai một Senior Business Analyst (BA) có 10 năm kinh nghiệm trong lĩnh vực FinTech và Ngân hàng số. Bạn đã từng triển khai nhiều dự án eKYC thành công cho các ngân hàng lớn với mục tiêu tối ưu hóa quy trình tự động, hướng tới "Zero manual operation".

Hãy phân tích bài toán mở tài khoản ngân hàng trực tuyến của ABC Bank và lập tài liệu phân tích nghiệp vụ chi tiết bao gồm các thành phần sau:

1. Actors: Xác định toàn bộ các tác nhân tham gia vào hệ thống (Trực tiếp và gián tiếp, hệ thống bên thứ 3 nếu có).
2. Business Flow: Mô tả luồng nghiệp vụ từng bước (Step-by-step) từ khi khách hàng tải app cho đến khi cấp số tài khoản thành công. Hãy làm nổi bật luồng Happy Path (luồng chuẩn) và các nhánh rẽ chính khi xác thực lỗi.
3. Functional Requirements (Yêu cầu chức năng): Liệt kê các tính năng chi tiết theo từng phân hệ (Đăng ký, OCR CCCD, Liveness Check, Xác thực chéo, Cấp tài khoản).
4. Non-Functional Requirements (Yêu cầu phi chức năng): Tập trung sâu vào Bảo mật (Data Security, Compliance với Ngân hàng Nhà nước), Hiệu năng (Performance/Response time của OCR/Liveness), Độ khả dụng (Availability).
5. Assumptions & Business Rules (Giả định & Quy tắc nghiệp vụ): Đưa ra các quy tắc bắt buộc của ngân hàng (ví dụ: độ tuổi, điều kiện CCCD hợp lệ, giới hạn số lần quét lỗi, quy định về phòng chống gian lận/Fraud Detection).

Yêu cầu: Trình bày rõ ràng, sử dụng các bảng dữ liệu hoặc bullet points trực quan, chuyên nghiệp theo chuẩn tài liệu BRD (Business Requirement Document).

```

### PROMPT 2: Sinh danh sách User Story chuyên sâu

```markdown
Dựa trên kết quả phân tích hệ thống ở trên, hãy đóng vai Product Owner phối hợp cùng Senior BA để viết danh sách các User Story hoàn chỉnh cho dự án này. 

Mỗi User Story cần tuân thủ cấu trúc chuẩn:
- ID: [Mã US]
- Tên Story: [Tên ngắn gọn]
- Khung: As a... I want to... So that...
- Acceptance Criteria (Tiêu chí nghiệm thu): Viết theo dạng Scenario (Given... When... Then...) để đảm bảo bao quát được cả luồng thành công và luồng thất bại.

Hãy chia danh sách User Story theo các Epic sau:
Epic 1: Đăng ký & Xác thực thông tin cơ bản
Epic 2: Định danh điện tử (OCR CCCD & Liveness Check)
Epic 3: Xử lý hệ thống & Cấp tài khoản tự động (Core Banking Integration)

```

### PROMPT 3: Trích xuất danh sách Use Case

```markdown
Từ các phân tích và User Story đã thống nhất, hãy tổng hợp cho tôi một danh sách các Use Case (Trường hợp sử dụng) của hệ thống eKYC này.

Yêu cầu trình bày dưới dạng bảng gồm các cột:
1. Mã Use Case (UC_ID)
2. Tên Use Case
3. Actor chính (Primary Actor)
4. Tóm tắt ngắn gọn mục đích (Description)
5. Điều kiện tiên quyết (Pre-conditions)

Sau khi lập bảng, hãy chọn ra 1 Use Case quan trọng nhất và phức tạp nhất là "UC_Định danh eKYC (OCR & Face Match)" để viết kịch bản chi tiết (Mô tả chi tiết Luồng chính - Main Flow, Luồng thay thế/Lỗi - Alternative/Exception Flows).

```
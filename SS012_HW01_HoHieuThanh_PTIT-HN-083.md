## 1. Phương Án Lựa Chọn

**Phương án tối ưu nhất:** **Phương án B**

---

## 2. Phân Tích Lý Do Lựa Chọn

Phương án B là một prompt chuẩn cấu trúc, cung cấp đầy đủ thông tin để AI hiểu rõ bối cảnh và đưa ra kết quả chính xác nhất. Cụ thể:

* **Vai trò (Role):** *"Đóng vai Senior Java Developer."*
* **Hiệu quả:** Định hình phong cách viết code của AI. Một Senior Developer sẽ viết code sạch (clean code), tối ưu hiệu năng, đặt tên biến rõ nghĩa và tuân thủ các nguyên lý thiết kế.


* **Nhiệm vụ (Task):** *"Viết class PaymentValidator kiểm tra tính hợp lệ của thẻ tín dụng."*
* **Hiệu quả:** Xác định mục tiêu cốt lõi của yêu cầu một cách rõ ràng, không bị mơ hồ.


* **Ngữ cảnh (Context):** *"Hệ thống E-commerce, cần validate trước khi gửi API thanh toán."*
* **Hiệu quả:** Giúp AI hiểu vị trí của đoạn code này trong luồng xử lý của hệ thống, từ đó thiết kế logic kiểm tra phù hợp cho môi trường thanh toán trực tuyến.


* **Ràng buộc (Constraints):** *"Dùng Java 17, triển khai thuật toán Luhn, ném ra ngoại lệ IllegalArgumentException nếu thẻ rỗng hoặc chứa chữ cái."*
* **Hiệu quả:** Đây là phần quan trọng nhất trong môi trường dự án. Nó ngăn chặn AI sử dụng các thư viện ngoài không mong muốn, ép buộc sử dụng đúng phiên bản Java 17, đúng thuật toán (Luhn) và xử lý lỗi nghiệp vụ (`IllegalArgumentException`) chính xác theo đặc tả yêu cầu.


* **Định dạng đầu ra (Output Format):** *"Chỉ trả về mã nguồn Java trong một code block, không giải thích."*
* **Hiệu quả:** Giúp người dùng dễ dàng copy-paste code vào dự án, tiết kiệm thời gian lọc bỏ các đoạn văn bản giải thích dài dòng không cần thiết của AI.



---

## 3. Phân Tích Các Phương Án Bị Loại Trừ

### Phương án A: Quá sơ sài và thiếu ràng buộc

* **Lỗ hổng:** Prompt quá ngắn, thiếu hoàn toàn các thành phần như Vai trò, Ngữ cảnh và Ràng buộc kỹ thuật. Cụm từ *"Code ngắn gọn thôi nhé"* mang tính cảm tính.
* **Rủi ro ảo tưởng (Hallucination) & Sai lệch ngữ cảnh:**
* Do không quy định phiên bản Java, AI có thể dùng cú pháp cũ (Java 8) hoặc các tính năng quá mới chưa được preview trong dự án.
* AI có thể viết một hàm `static` đơn giản thay vì một cấu trúc Class chuẩn chỉnh.
* Thiếu ràng buộc về dữ liệu đầu vào (`validation`), AI có thể bỏ qua bước kiểm tra chuỗi rỗng (`null`/`empty`) hoặc ký tự đặc biệt, dẫn đến lỗi `NullPointerException` hoặc `NumberFormatException` khi vận hành trong dự án thực tế.



### Phương án C: Lan man, ôm đồm và sai lệch mục tiêu

* **Lỗ hổng:** Vi phạm nguyên tắc tập trung của prompt. Thay vì tập trung giải quyết bài toán nghiệp vụ cốt lõi (kiểm tra thẻ), prompt lại yêu cầu thêm cả tạo Database SQL, kết nối JDBC và hướng dẫn cài đặt.
* **Rủi ro ảo tưởng (Hallucination) & Sai lệch ngữ cảnh:**
* **Sai lệch ngữ cảnh:** Nhóm dự án TechShop chỉ yêu cầu một class tiện ích `PaymentValidator`, việc sinh thêm SQL và kết nối JDBC cũ kỹ là hoàn toàn thừa thãi và không đồng bộ với kiến trúc hiện tại của dự án (ví dụ: dự án có thể đang dùng Spring Data JPA chứ không dùng JDBC thuần).
* **Rủi ro ảo tưởng:** Khi bắt AI làm quá nhiều việc trong một prompt, sự tập trung vào thuật toán chính (Luhn) bị giảm sút. AI dễ sinh ra mã nguồn SQL không chuẩn, cấu trúc bảng không bảo mật (lưu trực tiếp số thẻ chưa mã hóa) hoặc code xử lý logic Luhn bị sót trường hợp biên (edge cases).
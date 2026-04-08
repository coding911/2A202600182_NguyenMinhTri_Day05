# BÀI TẬP UX - CHATBOT NEO (VIETNAM AIRLINES)
**Sinh viên:** Nguyễn Minh Trí  
**MSSV:** 2A202600182

---

## PHẦN 1: TRẢI NGHIỆM NGƯỜI DÙNG

### 1. Trước khi dùng:
* Web của Vietnam Airlines giới thiệu Neo có thể ghi nhớ, cá nhân hóa tương tác dựa trên sở thích, lịch sử tìm kiếm và bối cảnh sử dụng.
* Neo hỗ trợ tìm kiếm thông tin, đặt vé, kiểm tra chuyến bay, giải đáp thắc mắc về hành lý.

### 2. Sau khi dùng:
* Khi bấm vào chatbot, mở ra một cửa sổ chat giống các chatbot khác. Sau một hồi lâu không chat gì thêm thì bot xin đánh giá của khách hàng.
* Khi trả lời câu hỏi thì có câu trả lời kèm các nút tra cứu để khách bấm, nhưng câu trả lời bị lặp.

---

## PHẦN 2: PHÂN TÍCH 4 PATHS

* **Khi AI đúng:** User thấy câu trả lời và link để tra cứu chi tiết. Khi hỏi các hạng vé, user hỏi lại để confirm thì bot trấn an và nhắc lại câu trả lời.
* **Khi AI không chắc:** Hệ thống nói chưa có thông tin và đề xuất liên hệ với tư vấn viên qua SĐT hoặc email (Ví dụ: Hỏi thông tin chuyến bay từ A -> C mà đi qua B).
* **Khi AI sai:** User biết dựa vào cách AI trả lời không liên quan (Hỏi liệt kê chuyến bay từ A -> B), dù có giải thích lại nhưng AI vẫn nói thế.
* **Khi User mất tin:** Có thoát trang và nói cho bot nhưng bot chỉ hỏi lại có muốn hủy yêu cầu đúng không.

> **Đánh giá chung:**
> * **Xử lý tốt nhất:** Khi AI không chắc (vì có đề xuất đưa vấn đề đến chỗ giải quyết được).
> * **Xử lý kém nhất:** Khi user mất tin (chưa cố níu user hay đưa cho nhân viên giải quyết).
> * **Nhận xét:** Kỳ vọng từ marketing chưa khớp thực tế do bot chưa nắm được ý định của user và chưa xử lý data được một cách phức tạp.

---

## PHẦN 3: ĐỀ XUẤT CẢI THIỆN (PATH KHI USER MẤT TIN)

| Đặc điểm | As-is (Hiện tại) | To-be (Cải thiện) |
| :--- | :--- | :--- |
| **Luồng xử lý** | User hỏi -> AI phản hồi sai -> User hỏi/giải thích lại -> **AI vẫn trả lời sai** (Chỗ gãy) -> User đóng web. | User hỏi -> AI phản hồi sai -> User hỏi/giải thích lại -> **AI phân tích lại câu hỏi**, nếu vẫn không trả lời được thì **chuyển tiếp chat cho nhân viên thật**. |

### Thay đổi đề xuất:
1. Thêm bước **suy luận lại** sau khi nhận được thêm thông tin từ user.
2. Tự động **khuyên và chuyển tiếp** đoạn chat cho nhân viên hỗ trợ nếu AI vẫn không thể trả lời đúng sau bước giải thích.
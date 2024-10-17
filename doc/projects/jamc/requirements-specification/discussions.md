# Tính năng đặt câu hỏi thảo luận - JAMC

## Mục tiêu

Tạo ra hệ thống thảo luận trên nền tảng JAMC để học sinh và giáo viên có thể tương tác thông qua các câu hỏi và câu trả lời, hỗ trợ quá trình học tập và giảng dạy.

## 1. Đối tượng sử dụng

- **Học sinh**: Đặt câu hỏi, trả lời câu hỏi, bình luận, bình chọn câu hỏi và câu trả lời.
- **Giáo viên**: Trả lời câu hỏi, chỉnh sửa, gắn nhãn "Best Answer", và cung cấp hướng dẫn thêm.
- **Admin**: Quản lý toàn bộ hệ thống thảo luận, có quyền xóa hoặc khóa các câu hỏi vi phạm.

## 2. Chức năng chính

- **Câu hỏi công khai (Public Questions)**: Mọi học sinh và giáo viên trên nền tảng có thể thấy và trả lời.
- **Câu hỏi riêng tư (Private Questions)**: Chỉ học sinh và giáo viên trong cùng một lớp học mới có quyền truy cập.
- **Vote câu hỏi và câu trả lời**: Học sinh và giáo viên có thể bình chọn (upvote/downvote) câu trả lời dựa trên mức độ hữu ích.
- [**Gắn nhãn câu hỏi (Tags)**](): Mỗi câu hỏi được gắn nhãn theo chủ đề để dễ dàng tìm kiếm và phân loại.
- **Trả lời có giải thích (Best Answer)**: Câu trả lời hay nhất được nhiều người bình chọn hoặc giáo viên chọn sẽ được gắn nhãn.
- **Bình luận (Comments)**: Học sinh và giáo viên có thể bình luận để làm rõ hoặc thảo luận sâu hơn.

## 3. Phân quyền

- **Học sinh**: Đặt câu hỏi, trả lời câu hỏi, vote, bình luận, và nhận thông báo.
- **Giáo viên**: Gắn nhãn "Best Answer", quản lý câu hỏi của lớp học, trả lời và bình luận.
- **Admin**: Quản lý toàn hệ thống, xóa câu hỏi vi phạm, và khóa thảo luận.

## 4. Thông báo (Notifications)

Người dùng sẽ nhận thông báo khi có câu hỏi mới, câu trả lời, hoặc bình luận trên câu hỏi của họ.

## 5. Bộ lọc và tìm kiếm

- Người dùng có thể lọc câu hỏi theo tag, độ khó, môn học, hoặc chủ đề cụ thể.

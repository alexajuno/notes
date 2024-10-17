### 1. **Giới hạn quyền tạo tags:**
   - **Người dùng có điểm tín chỉ cao mới có quyền tạo tag mới**: Điều này sẽ khuyến khích chỉ những người dùng có uy tín, đã đóng góp tích cực cho cộng đồng mới được tạo tag mới. Những người dùng khác sẽ phải sử dụng các tag đã có sẵn.
   - **Yêu cầu xác nhận từ giáo viên hoặc admin**: Khi người dùng muốn tạo tag mới, họ phải đề xuất tag đó và admin hoặc giáo viên sẽ duyệt yêu cầu. Điều này giúp kiểm soát số lượng tag mới được tạo ra và tránh sự trùng lặp không cần thiết.

### 2. **Tự động kiểm tra và gợi ý tag đã tồn tại:**
   - Khi người dùng nhập tag mới, hệ thống sẽ **tự động gợi ý** các tag đã tồn tại dựa trên từ khóa mà họ nhập. Điều này giúp giảm thiểu việc tạo ra các tag tương tự nhau nhưng khác cách viết.
   - **Từ điển tag**: Xây dựng một danh sách các tag phổ biến và đã được phê duyệt trước, và người dùng chỉ có thể chọn từ danh sách đó hoặc tạo tag mới theo quy định.

### 3. **Giới hạn số lượng tags mà người dùng có thể tạo:**
   - Đặt một **ngưỡng tối đa** cho số lượng tag mới mà người dùng có thể tạo trong một khoảng thời gian (ví dụ: mỗi người dùng chỉ được tạo 1-2 tag mới mỗi tuần). Điều này giúp kiểm soát số lượng tag phát sinh và ngăn việc tạo tràn lan.

### 4. **Tự động gộp tag trùng lặp hoặc sai:**
   - **Quản lý tags trùng lặp**: Nếu hệ thống phát hiện nhiều tag tương tự (ví dụ: "Toán học" và "Math"), có thể thiết lập cơ chế **gộp tag** và thay thế tự động bằng một tag chuẩn duy nhất.
   - **Sửa lỗi chính tả**: Hệ thống có thể tự động sửa các lỗi chính tả phổ biến trong tag hoặc cảnh báo người dùng nếu họ nhập một tag mới có thể là lỗi chính tả.

### 5. **Theo dõi và xóa tag không được sử dụng:**
   - Sau một thời gian, nếu một tag mới không được sử dụng trong bất kỳ câu hỏi nào, hệ thống có thể **tự động xóa** tag đó để giữ cho database gọn gàng.

### Cơ chế tạo tag gợi ý:
   - Khi người dùng nhập tag mới, nếu tag đó không tồn tại, hệ thống sẽ:
     1. Gợi ý các tag tương tự đã tồn tại.
     2. Kiểm tra quyền hạn của người dùng xem có đủ điểm tín chỉ hoặc quyền để tạo tag mới hay không.
     3. Nếu được phép, cho phép tạo tag mới với một quy trình xác nhận.

### Cấu trúc bảng `tags`:
   ```sql
   CREATE TABLE tags (
       id SERIAL PRIMARY KEY,
       name VARCHAR(255) UNIQUE NOT NULL,
       created_by INT REFERENCES users(id),
       approved BOOLEAN DEFAULT FALSE -- Tag mới tạo cần được phê duyệt
   );
   ```

2. **Bảng `question_tags`**:
- Không thay đổi so với bảng đã nêu trước đó, nhưng khi tag mới được tạo, nó sẽ có trạng thái **pending** hoặc **approved** tùy vào cơ chế kiểm soát.

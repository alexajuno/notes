# Requirements

- Pipcar mobile app backend development

## Progress

- Setup a basic project combining Express.js and TypeScript

## Express.js

## [ TypeScript ](/notes/typescript.md)

## Potential Topics

### 1. **API Design và RESTful Services**
   Bạn đã quen với CRUD, nên bước tiếp theo là học cách xây dựng APIs một cách hiệu quả và tối ưu cho mobile apps:
   - **Pagination & Filtering**: Đối với dữ liệu lớn, bạn cần học cách thêm phân trang (pagination) và lọc (filtering) để giảm tải cho hệ thống.
   - **Caching**: Tìm hiểu các phương pháp caching dữ liệu (ví dụ Redis hoặc HTTP caching headers) để giảm thời gian phản hồi và tải server.
   - **Rate Limiting & Throttling**: Hạn chế số lượng request từ một user hoặc IP để tránh quá tải.
   - **Statelessness**: Tìm hiểu cách xây dựng APIs theo mô hình stateless để dễ dàng mở rộng quy mô và quản lý.

### 2. **Authentication và Authorization**
   Bảo mật luôn là một yếu tố quan trọng, đặc biệt khi làm việc với back-end:
   - **JWT (JSON Web Token)**: Học cách sử dụng JWT để xác thực người dùng và lưu trữ trạng thái session trên client.
   - **OAuth 2.0**: Nếu ứng dụng của bạn cần liên kết với các dịch vụ bên ngoài (ví dụ Google hoặc Facebook login), OAuth 2.0 sẽ là công cụ hữu ích.

### 3. **Performance & Optimization**
   Hiệu suất là yếu tố quan trọng khi làm việc với mobile apps:
   - **Load Balancing**: Học cách phân phối tải giữa nhiều server để xử lý nhiều yêu cầu cùng lúc.
   - **Asynchronous Processing**: Mobile apps có thể cần gửi dữ liệu lên server theo batch hoặc xử lý bất đồng bộ (asynchronous), ví dụ khi gửi notifications hoặc xử lý dữ liệu lớn.
   - **Database Optimization**: Tối ưu hóa query trong cơ sở dữ liệu bằng cách sử dụng index, và học về cơ chế **query performance**.
   - **API Response Time**: Giảm thời gian phản hồi của APIs bằng cách cải thiện truy vấn cơ sở dữ liệu hoặc dùng caching hợp lý.

### 4. **Real-Time Features**
   Một số ứng dụng mobile yêu cầu tương tác thời gian thực:
   - **WebSockets**: Nghiên cứu về WebSockets để cho phép các tính năng như chat real-time hoặc notification updates.
   - **Server-Sent Events (SSE)**: Học cách gửi dữ liệu từ server tới client mà không cần request từ client.

### 5. **Scalability & Architecture**
   Để chuẩn bị cho việc mở rộng app trong tương lai:
   - **Microservices**: Học cách phân chia ứng dụng thành nhiều dịch vụ nhỏ (microservices) để dễ dàng mở rộng và bảo trì.
   - **Message Queues (MQ)**: Đối với các tác vụ nặng hoặc phức tạp, message queues (như RabbitMQ hoặc Kafka) có thể giúp xử lý chúng bất đồng bộ.
   - **Database Sharding & Replication**: Nghiên cứu các kỹ thuật này để phân chia và sao lưu dữ liệu trong các hệ thống lớn.

### 6. **Mobile-Specific Considerations**
   - **Offline Support**: Mobile apps thường yêu cầu hỗ trợ chế độ offline. Học cách lưu trữ tạm thời dữ liệu và đồng bộ khi có kết nối mạng.
   - **Push Notifications**: Tìm hiểu cách sử dụng Firebase Cloud Messaging (FCM) để gửi notifications đến app.
   - **API Rate Limiting for Mobile Networks**: Mobile networks không ổn định, nên bạn cần tối ưu APIs để hoạt động tốt trong điều kiện mạng yếu.

### 7. **Testing & Debugging**
   - **Load Testing**: Học cách kiểm tra khả năng chịu tải của server bằng các công cụ như Apache JMeter hoặc k6.
   - **Unit Testing**: Viết unit tests cho các service phía back-end để đảm bảo chúng hoạt động đúng trong mọi trường hợp.
   
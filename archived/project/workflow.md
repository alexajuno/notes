# **Workflow Quản Lý GitHub cho Project CPAD**

## 1. **Main Branch (Nhánh chính)**

- Đây là nhánh ổn định nhất của dự án. Mọi mã nguồn trên nhánh **main** đều đã được kiểm tra và sẵn sàng để triển khai. Chúng ta chỉ merge vào **main** sau khi các thay đổi đã được kiểm tra kỹ lưỡng.

## 2. **Develop Branch (Nhánh phát triển)**

- **develop** là nơi mọi người tích hợp các tính năng hoặc sửa lỗi từ các nhánh riêng biệt (topic branches). Sau khi mã trên **develop** đã được kiểm tra và ổn định, chúng ta có thể merge vào **main**.

**Link tham khảo**:

- [GitHub Docs: GitFlow](https://docs.github.com/en/get-started/quickstart/github-flow)
- [Git SCM: Maintaining a Project](https://git-scm.com/book/en/v2/Distributed-Git-Maintaining-a-Project)

## 3. **Topic Branches (Nhánh chức năng)**

- Mỗi thành viên khi phát triển một tính năng hoặc sửa lỗi sẽ tạo một nhánh riêng từ **develop** (ví dụ: `feature/new-feature`, `bugfix/fix-issue`). Sau khi hoàn thành, các nhánh này sẽ được merge lại vào **develop** thông qua pull request.

**Link tham khảo**: [GitHub Docs: Branches](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-branches)

## 4. **Pull Requests (Yêu cầu kéo)**

- Pull request (PR) là cách để gửi các thay đổi từ nhánh của bạn vào **develop**. Trước khi merge PR, các thành viên khác có thể review, để lại comment và yêu cầu thay đổi nếu cần thiết. Mỗi PR nên liên kết với một Issue hoặc thẻ công việc để quản lý công việc tốt hơn.

**Link tham khảo**: [GitHub Docs: Pull Requests](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)

## 5. **Comments trong Pull Requests**

- Các comment trên pull request là nơi các thành viên có thể thảo luận về thay đổi, giải thích code, hoặc yêu cầu chỉnh sửa. Điều này giúp cải thiện chất lượng code và đảm bảo rằng mọi người đều hiểu rõ những thay đổi.

**Link tham khảo**: [GitHub Docs: Review Pull Requests](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/reviewing-changes-in-pull-requests)

## 6. **Issues**

- Issues là nơi bạn ghi lại các lỗi, tính năng mới, hoặc các công việc cần làm. Mỗi issue thường được liên kết với một pull request để đảm bảo các thay đổi giải quyết được vấn đề cụ thể. Issues giúp chúng ta theo dõi tiến độ công việc và ưu tiên các nhiệm vụ trong dự án.

**Link tham khảo**: [GitHub Docs: Issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)

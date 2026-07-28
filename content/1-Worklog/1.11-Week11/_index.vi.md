---
title: "Nhật ký tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11

* Nghiên cứu các khái niệm và thực hành bảo mật trên AWS.
* Tìm hiểu cách IAM Roles được sử dụng cho các ứng dụng chạy trên EC2 để truy cập dịch vụ AWS một cách an toàn.
* Tiếp tục phát triển các chức năng Backend cho dự án Snaptics.
* Nâng cao khả năng quản lý các tác vụ nền và chức năng liên quan đến ngân sách.
* Phát triển hệ thống Support Ticket dành cho người dùng.

### Công việc đã thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|-----------|--------------|-----------------|--------------------|
| 2 | **Nghiên cứu AWS Security:** <br> • Nghiên cứu các dịch vụ bảo mật và quản lý danh tính trên AWS <br> • Ôn tập IAM, IAM Roles, Policies, AWS KMS và CloudTrail <br> • Tìm hiểu các thực hành bảo mật nhằm hỗ trợ phát triển ứng dụng Backend an toàn | 20/07/2026 | 20/07/2026 | |
| 3 | **IAM Roles for EC2:** <br> • Tìm hiểu IAM Roles dành cho EC2 <br> • Hiểu Instance Profiles và Temporary Credentials <br> • Tìm hiểu cách cấp quyền cho ứng dụng trên EC2 mà không cần lưu Access Keys | 21/07/2026 | 21/07/2026 | https://000048.awsstudygroup.com/ |
| 4 | **Phát triển Backend dự án Snaptics:** <br> • Phát triển Runtime API để cập nhật lịch chạy Hangfire Recurring Jobs <br> • Hỗ trợ thay đổi lịch chạy tác vụ mà không cần khởi động lại hệ thống <br> • Kiểm thử việc cập nhật lịch chạy của các Background Jobs | 22/07/2026 | 22/07/2026 | |
| 5 | **Phát triển Backend dự án Snaptics:** <br> • Phát triển chức năng BudgetIncomeSource phục vụ tạo ngân sách <br> • Xây dựng các API CRUD cho BudgetIncomeSource <br> • Bổ sung trường CreatedAt để theo dõi thời gian tạo dữ liệu <br> • Kiểm thử các API mới trên Backend | 23/07/2026 | 23/07/2026 | |
| 6 | **Phát triển Backend dự án Snaptics:** <br> • Phát triển các API Support Ticket dành cho người dùng <br> • Xây dựng CRUD, quản lý tin nhắn và tệp đính kèm <br> • Bổ sung API thống kê Support Ticket <br> • Kiểm thử các API mới trên Backend | 24/07/2026 | 24/07/2026 | |

### Kết quả đạt được trong tuần

* Nghiên cứu và củng cố kiến thức về AWS Security, đặc biệt là các cơ chế quản lý danh tính và phân quyền.

* Hiểu cách IAM Roles dành cho EC2 giúp ứng dụng truy cập các dịch vụ AWS an toàn mà không cần sử dụng Access Keys.

* Hoàn thiện Runtime API cho phép cập nhật lịch chạy Hangfire Recurring Jobs.

* Phát triển chức năng BudgetIncomeSource và các API CRUD phục vụ quản lý ngân sách.

* Xây dựng hệ thống Support Ticket với CRUD, quản lý tin nhắn, tệp đính kèm và API thống kê.

* Tiếp tục nâng cao kỹ năng phát triển Backend thông qua việc triển khai các tính năng thực tế trong dự án.
---
title: "Nhật ký tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11

* Tìm hiểu các tính năng nâng cao của IAM, bao gồm IAM Role Conditions và cơ chế cấp quyền cho ứng dụng bằng IAM Roles.
* Hiểu các phương pháp bảo mật khi cấp quyền truy cập dịch vụ AWS cho ứng dụng.
* Tiếp tục phát triển các chức năng backend cho dự án Snaptics.
* Triển khai, kiểm thử và cải tiến các module backend của hệ thống.

### Các hoạt động đã thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|-----------|--------------|-----------------|--------------------|
| 2 | **Cải tiến chức năng quản lý thu nhập:** <br> • Rà soát và cập nhật luồng xử lý thu nhập <br> • Điều chỉnh logic của Income Source và Income History <br> • Cập nhật Database Migration và các backend services liên quan | 20/07/2026 | 20/07/2026 | |
| 3 | **IAM Role & Condition:** <br> • Tìm hiểu IAM Groups và IAM Users <br> • Cấu hình IAM Role Conditions <br> • Tìm hiểu nguyên tắc phân quyền tối thiểu (Least Privilege) và cơ chế kiểm soát truy cập theo điều kiện | 21/07/2026 | 21/07/2026 | https://000030.awsstudygroup.com/ |
| 4 | **Cấp quyền cho ứng dụng bằng IAM Roles:** <br> • Tìm hiểu phương pháp xác thực an toàn cho ứng dụng trên AWS <br> • So sánh Access Keys và IAM Roles <br> • Cấu hình IAM Roles cho các ứng dụng chạy trên EC2 | 22/07/2026 | 22/07/2026 | https://000048.awsstudygroup.com/ |
| 5 | **Phát triển Budget Income Source:** <br> • Thiết kế và triển khai module Budget Income Source <br> • Phát triển các CRUD APIs cho Budget Income Source <br> • Xây dựng Entity, DTO, Repository, Service và Controller <br> • Tạo Database Migration và cập nhật các trường dữ liệu của Entity <br> • Kiểm thử API và xác minh nghiệp vụ | 23/07/2026 | 23/07/2026 | |
| 6 | **Phát triển module Support Ticket:** <br> • Phát triển module Support Ticket <br> • Xây dựng CRUD APIs cho Ticket <br> • Bổ sung chức năng Support Messages và Attachments <br> • Phát triển chức năng thống kê Ticket <br> • Tạo Database Migration và thực hiện kiểm thử API | 24/07/2026 | 24/07/2026 | |

### Kết quả đạt được trong tuần 11

* Hiểu được cách IAM Role Conditions được sử dụng để kiểm soát quyền truy cập chi tiết trên AWS.

* Nắm được phương pháp cấp quyền an toàn cho ứng dụng thông qua IAM Roles thay vì sử dụng Access Keys dài hạn.

* Củng cố kiến thức về bảo mật trên AWS, bao gồm nguyên tắc phân quyền tối thiểu (Least Privilege) và quản lý quyền truy cập dựa trên IAM Roles.

* Hoàn thiện việc cải tiến luồng xử lý thu nhập và cập nhật các backend services liên quan trong dự án Snaptics.

* Thiết kế và triển khai thành công module Budget Income Source, bao gồm cơ sở dữ liệu, nghiệp vụ xử lý và các CRUD APIs.

* Phát triển hoàn chỉnh module Support Ticket với các chức năng quản lý Ticket, tin nhắn, tệp đính kèm và thống kê.

* Hoàn thành Database Migration, kiểm thử API và xác minh các chức năng mới trước khi tích hợp vào hệ thống.
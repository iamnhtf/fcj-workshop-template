---
title: "Blog 1"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Đã Nâng Cấp Amazon Cognito Với Mức Gián Đoạn Gần Như Bằng 0

Authentication là một trong những thành phần quan trọng nhất của các hệ thống hiện đại. Chỉ cần dịch vụ xác thực gặp sự cố trong vài phút cũng có thể khiến người dùng không thể đăng nhập, đặt lại mật khẩu hoặc truy cập ứng dụng.

Gần đây, AWS đã chia sẻ cách Amazon Cognito được nâng cấp lên hạ tầng thế hệ mới với nhiều tính năng nổi bật như khả năng mở rộng tốt hơn, hỗ trợ mã hóa bằng khóa do khách hàng quản lý và đồng bộ dữ liệu đa Region, trong khi quá trình migration diễn ra với mức gián đoạn gần như bằng 0.

### Những điểm nổi bật

Sau khi nâng cấp, Amazon Cognito mang đến nhiều cải tiến đáng chú ý:

- **Hiệu năng cao (High-throughput Performance)**
  - Hỗ trợ hàng chục triệu người dùng trong một User Pool.
  - Xử lý hàng nghìn giao dịch mỗi giây (TPS).
  - Giảm độ trễ trong quá trình xác thực.

- **Customer-managed Keys (CMK)**
  - Tích hợp với AWS KMS.
  - Cho phép doanh nghiệp tự quản lý khóa mã hóa.
  - Đáp ứng tốt hơn các yêu cầu về bảo mật và tuân thủ.

- **Multi-Region Replication**
  - Đồng bộ User Profile, Password, User Attributes và Configuration giữa nhiều AWS Region.
  - Tăng khả năng sẵn sàng và hỗ trợ khôi phục sau sự cố.

### Những thay đổi trong kiến trúc

AWS đã thiết kế lại Cognito dựa trên một số nguyên tắc quan trọng:

- **Identity-first Design**
  - Tập trung tối ưu cho bài toán quản lý danh tính thay vì hoạt động như một hệ thống lưu trữ dữ liệu tổng quát.
  - Giúp hệ thống mở rộng và vận hành hiệu quả hơn.

- **Backward Compatibility**
  - Việc thay đổi hạ tầng không làm ảnh hưởng đến ứng dụng của khách hàng.
  - Các API và hành vi xác thực vẫn được duy trì tương thích.

- **Avoid One-way Doors**
  - Kiến trúc được thiết kế để dễ dàng mở rộng và thay đổi trong tương lai mà không tạo ra các quyết định khó đảo ngược.

### Chiến lược Migration

Điều ấn tượng nhất trong bài viết là cách AWS thực hiện migration cho hàng trăm triệu hồ sơ người dùng mà gần như không gây gián đoạn dịch vụ.

Các kỹ thuật được áp dụng bao gồm:

- **Shadow Mode Validation**
  - Chạy đồng thời request trên cả hệ thống cũ và hệ thống mới.
  - So sánh response, status code và hành vi xử lý trước khi chuyển hoàn toàn sang hạ tầng mới.

- **Dual-write Architecture**
  - Trong quá trình migration, dữ liệu được ghi đồng thời vào cả hai hệ thống.
  - Nếu hệ thống mới gặp lỗi, hệ thống cũ vẫn tiếp tục phục vụ người dùng.

- **Anti-entropy Validation**
  - Liên tục đối chiếu dữ liệu giữa hai hệ thống để phát hiện sai lệch.
  - Hệ thống cũ được sử dụng làm nguồn dữ liệu chuẩn để đồng bộ khi cần thiết.

- **Incremental Rollout & Rollback**
  - Triển khai theo từng giai đoạn thay vì chuyển đổi toàn bộ cùng lúc.
  - Luôn duy trì khả năng rollback nếu phát sinh sự cố.

### Kiến thức rút ra

Qua bài viết này, mình nhận thấy việc hiện đại hóa hạ tầng không chỉ nhằm bổ sung tính năng mới mà còn phải đảm bảo tính ổn định của hệ thống.

Một số bài học đáng chú ý gồm:

- Luôn kiểm chứng hệ thống mới trước khi chuyển traffic thực tế.
- Thiết kế kế hoạch migration có khả năng rollback.
- Duy trì backward compatibility để tránh ảnh hưởng đến người dùng.
- Triển khai theo từng giai đoạn nhằm giảm thiểu rủi ro khi thay đổi hạ tầng quy mô lớn.

Những kinh nghiệm này là nguồn tham khảo hữu ích khi xây dựng các hệ thống cloud có yêu cầu cao về tính sẵn sàng và độ tin cậy.

### Hình minh họa

...Image...

### Bài viết tham khảo

...AWS Blog Link...
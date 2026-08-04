---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# SNAPTICS – Nền tảng Quản lý Chi tiêu Cá nhân và Quét Hóa đơn Hỗ trợ AI
## Nền tảng Quản lý Chi tiêu và Quét Hóa đơn bằng AI trên AWS Cloud

### 1. Tóm tắt Dự án

#### 1.1. Giới thiệu

Snaptics là một nền tảng quản lý tài chính cá nhân và gia đình được đề xuất, nhằm chuyển đổi việc theo dõi chi tiêu từ nhập liệu thủ công sang mô hình tự động hóa, tập trung hóa và phân tích thông minh. Người dùng chỉ cần chụp hoặc tải lên hình ảnh hóa đơn; công nghệ Optical Character Recognition (OCR) và Trí tuệ nhân tạo (AI) sẽ tự động trích xuất các thông tin quan trọng bao gồm tên cửa hàng, ngày giao dịch, tổng số tiền, danh mục và chi tiết từng dòng. Sau khi người dùng xem xét và xác nhận, Snaptics tự động tạo bản ghi giao dịch, cập nhật số dư ví, đồng bộ ngân sách và phản ánh dữ liệu trên bảng điều khiển tài chính.

Ngoài tính năng quét hóa đơn tự động, Snaptics cung cấp các tính năng toàn diện: nhập giao dịch thủ công, quản lý đa ví (ví cá nhân & ví gia đình dùng chung), thiết lập ngân sách và cảnh báo ngưỡng, báo cáo thống kê đa chiều, trung tâm thông báo tập trung, phân tích hành vi chi tiêu (AI Insight) và trợ lý thông minh tương tác (AI Chatbot). Hệ thống bao gồm Bảng quản trị (Admin Panel) cho phép quản trị viên giám sát người dùng, xử lý yêu cầu hỗ trợ, đăng thông báo hệ thống, cấu hình tham số vận hành và quản lý các tác vụ nền qua Hangfire.

Snaptics được xây dựng như một ứng dụng web SaaS triển khai trên hạ tầng AWS Cloud-Native. Kiến trúc hệ thống tận dụng các dịch vụ bao gồm AWS Amplify, Amazon CloudFront, Amazon Route 53, Amazon ECS Fargate, Application Load Balancer (ALB), Amazon SQS / Dead Letter Queue (DLQ), Amazon S3, Amazon ECR, AWS Systems Manager Parameter Store, Amazon CloudWatch, AWS Budgets và Amazon RDS for SQL Server. Khả năng AI được tích hợp với Azure Document Intelligence và Gemini API.

#### 1.2. Vai trò Người dùng

- Người dùng (Cá nhân / Thành viên gia đình): Quản lý giao dịch, hình ảnh hóa đơn, ví và ngân sách; xem báo cáo phân tích; nhận lời khuyên tài chính từ AI; khởi tạo và tham gia ví/ngân sách gia đình dùng chung.
- Quản trị viên (Quản trị hệ thống): Quản lý tài khoản người dùng, xử lý yêu cầu hỗ trợ, phát thông báo hệ thống, cấu hình tham số hệ thống, giám sát các tác vụ định kỳ Hangfire và theo dõi sức khỏe nền tảng.

#### 1.3. Phạm vi Chức năng

- Xác thực & Phân quyền: Đăng nhập người dùng, xác thực token (JWT/OAuth2) và kiểm soát truy cập theo vai trò (Người dùng/Quản trị viên).
- Quy trình Xử lý Hóa đơn: Tải lên hình ảnh, trích xuất OCR tự động, người dùng xác minh và chỉnh sửa trước khi lưu.
- Quản lý Giao dịch: Tạo, cập nhật, phân loại tự động/thủ công và tìm kiếm lịch sử giao dịch.
- Quản lý Ví Tài chính: Tạo ví cá nhân, quản lý ví gia đình dùng chung và quản lý quyền truy cập thành viên.
- Quản lý Ngân sách: Thiết lập ngưỡng, tính toán mức sử dụng theo thời gian thực và cảnh báo khi vượt ngưỡng tự động.
- Phân tích & Báo cáo: Bảng điều khiển trực quan hiển thị biểu đồ chi tiêu theo khung thời gian và danh mục.
- Tính năng hỗ trợ AI: Phân tích thói quen chi tiêu (AI Insight), trợ lý hội thoại tương tác (AI Chatbot) kèm lịch sử hội thoại.
- Thông báo & Hỗ trợ: Thông báo trong ứng dụng tập trung và quản lý yêu cầu hỗ trợ kỹ thuật.
- Tác vụ hệ thống & Xử lý nền: Tác vụ nền định kỳ qua Hangfire; quy trình OCR/AI bất đồng bộ qua Amazon SQS và Dead Letter Queue (DLQ).
- Vận hành Cloud: Triển khai AWS, giám sát hiệu suất tập trung (Amazon CloudWatch) và quản lý chi phí (AWS Budgets).

#### 1.4. Giới hạn Phạm vi Đề xuất

Giai đoạn 13 tuần tập trung vào hoàn thiện một ứng dụng web responsive, trích xuất hóa đơn tự động, quản lý chi tiêu/ví/ngân sách cốt lõi và triển khai cloud AWS toàn diện trong cấu hình demo tối ưu chi phí.

Các tính năng dành cho định hướng phát triển trong tương lai bao gồm:

- Tích hợp trực tiếp với Open Banking API hoặc ví điện tử (MoMo, ZaloPay).
- Ứng dụng di động gốc (iOS / Android).
- Các khuyến nghị tài chính có giá trị ràng buộc pháp lý.
- Vận hành Production Multi-AZ 24/7 liên tục ở quy mô lớn.

### 2. Mục tiêu Dự án

#### 2.1. Mục tiêu Tổng quát

Xây dựng nền tảng quản lý chi tiêu thông minh Snaptics dựa trên điện toán đám mây và trí tuệ nhân tạo, giúp người dùng giảm thiểu thời gian nhập liệu thủ công, chủ động kiểm soát ngân sách và nâng cao khả năng phân tích tài chính cá nhân, gia đình thông qua những hiểu biết trực quan từ dữ liệu.

#### 2.2. Mục tiêu Cụ thể

- Tự động hóa: Tự động trích xuất dữ liệu hóa đơn qua OCR (Azure Document Intelligence); tự động tạo và phân loại giao dịch sau khi người dùng xác minh.
- Quản lý linh hoạt: Hỗ trợ nhập giao dịch thủ công; quản lý nhiều ví/ngân sách cá nhân và gia đình; cho phép nhiều thành viên cộng tác trên tài nguyên tài chính dùng chung.
- Phân tích & Báo cáo: Cung cấp bảng điều khiển tương tác và báo cáo chi tiêu theo ngày, tuần, tháng và danh mục; phân tích thói quen chi tiêu bằng AI Insights; cung cấp AI Chatbot tương tác kèm lịch sử.
- Cảnh báo & Thông báo: Giám sát chủ động mức sử dụng ngân sách, gửi cảnh báo khi đạt gần hoặc vượt ngưỡng; xây dựng trung tâm thông báo tập trung.
- Quản trị Hệ thống: Cung cấp Bảng quản trị để quản lý người dùng, yêu cầu hỗ trợ, thông báo hệ thống, cấu hình và các tác vụ nền Hangfire.
- Vận hành & Triển khai Cloud: Triển khai trên AWS với khả năng mở rộng, bảo mật và giám sát tập trung (CloudWatch, AWS Budgets); thiết lập tự động hóa CI/CD để kiểm thử và phân phối.

### 3. Vấn đề Cần Giải quyết

- Nhập chi tiêu thủ công & rủi ro sai lệch dữ liệu: Đa số người dùng ghi chép chi tiêu thủ công bằng sổ tay, bảng tính hoặc nhập liệu thủ công trên ứng dụng, gây tốn thời gian, dễ sai sót và khó duy trì. Snaptics tự động hóa việc thu thập dữ liệu hóa đơn qua OCR đồng thời cung cấp giao diện xem xét trước khi lưu trữ.
- Dữ liệu tài chính phân tán: Thông tin chi tiêu nằm rải rác trên hóa đơn giấy, ứng dụng ngân hàng và ví điện tử. Snaptics hợp nhất mọi giao dịch vào một nền tảng duy nhất.
- Khó khăn trong kiểm soát ngân sách: Người dùng thường nhận ra việc chi tiêu quá mức chỉ sau khi vượt ngưỡng ngân sách. Snaptics theo dõi mức sử dụng ngân sách theo thời gian thực và đưa ra cảnh báo chủ động.
- Thiếu hiểu biết về hành vi chi tiêu: Các giao dịch thô mang lại giá trị hạn chế nếu không được tổng hợp. Snaptics phân tích dữ liệu lịch sử theo danh mục và thời gian, phát hiện xu hướng và đưa ra khuyến nghị hành động qua AI Insight.
- Khó khăn trong phối hợp tài chính gia đình: Chi tiêu hộ gia đình dùng chung thiếu sự minh bạch khi không có công cụ theo dõi tập trung. Snaptics cung cấp ví gia đình dùng chung và ngân sách chung.
- Rủi ro độ trễ & nghẽn cổ chai của dịch vụ AI: Xử lý OCR và AI đồng bộ có thể gây timeout API khi tải cao. Snaptics sử dụng Amazon SQS và AI Worker để tách rời các tác vụ nặng khỏi Backend API.
- Lập lịch tác vụ nền tự động: Các tác vụ quản trị như sinh AI Insights định kỳ, kiểm tra ngân sách và gửi cảnh báo cần lập lịch tự động. Hangfire được tích hợp vào backend .NET kèm giao diện quản trị tác vụ.

### 4. Kiến trúc Giải pháp

Snaptics sử dụng kiến trúc AWS Cloud-Native kết hợp Single Page Application (SPA), microservices đóng gói container, cơ sở dữ liệu quan hệ, lưu trữ đối tượng, hàng đợi bất đồng bộ và các dịch vụ AI bên ngoài chuyên biệt. Kiến trúc duy trì sự tách biệt rõ ràng giữa Frontend, Backend API và AI Worker để triển khai, mở rộng và giám sát độc lập.

![Sơ đồ kiến trúc hệ thống Snaptics trên AWS Cloud](/fcj-workshop-template/images/2-Proposal/snaptics_architecture.png)

#### 4.1. Các Thành phần Chính

- Frontend: Single Page Application (SPA) triển khai qua AWS Amplify. Kết nối với GitHub Repository để tự động build/deploy, tích hợp Amazon Route 53 cho DNS và Amazon CloudFront (CDN) để phân phối HTTPS an toàn.
- Backend API: Đóng gói container qua Docker lưu trữ trên Amazon ECR, chạy trên AWS Fargate (Amazon ECS Cluster) phía sau Application Load Balancer (ALB) với Auto Scaling.
- AI Worker: Worker chạy trên ECS Fargate nhận message từ Amazon SQS, gọi Azure Document Intelligence để OCR và gửi dữ liệu có cấu trúc đến Gemini API để phân loại và sinh insight.
- Cơ sở dữ liệu: Amazon RDS for SQL Server triển khai trong Private Subnets, quản lý tài khoản, giao dịch, hóa đơn, ví, ngân sách, thông báo, lịch sử chat AI, yêu cầu hỗ trợ và nhật ký kiểm toán.
- Lưu trữ phương tiện: Amazon S3 lưu trữ hình ảnh hóa đơn gốc, tệp đính kèm giao dịch và hình ảnh đã xử lý, tách dữ liệu nhị phân khỏi lưu trữ cơ sở dữ liệu.
- Quy trình hàng đợi bất đồng bộ: Amazon SQS đệm các tác vụ OCR/AI; Dead Letter Queue (DLQ) giữ các message lỗi vượt quá số lần thử lại để xử lý sự cố.
- Tác vụ nền & Lập lịch: Bộ chạy Hangfire chạy cùng Backend .NET để lập lịch, kích hoạt và giám sát các tác vụ định kỳ của hệ thống.
- Hệ thống thông báo: Quản lý tập trung trong DB kết hợp Amazon SNS để gửi cảnh báo (cảnh báo ngân sách, trạng thái OCR, mẹo AI, cập nhật hệ thống).
- Bảo mật & Cấu hình: Bí mật lưu trong AWS Systems Manager Parameter Store, Private Subnets cho Backend/Worker/DB, HTTPS bắt buộc, xác thực Access Token (JWT), RBAC và Audit Logging.
- Quy trình CI/CD: Tự động hóa qua GitHub Actions (build Docker, push ECR, cập nhật dịch vụ ECS) và AWS Amplify (build frontend).
- Giám sát & Kiểm soát chi phí: Amazon CloudWatch (logs, số liệu container, độ sâu SQS) và AWS Budgets (cảnh báo chi phí theo ngưỡng cấu hình).

#### 4.2. Quy trình Xử lý Hóa đơn

1. Người dùng tải lên hình ảnh hóa đơn qua Frontend.
2. Frontend gửi hình ảnh đến Backend API -> Backend lưu hình ảnh vào Amazon S3.
3. Backend đẩy message xử lý vào Amazon SQS.
4. AI Worker nhận message từ SQS, gọi Azure Document Intelligence để trích xuất văn bản/bảng.
5. AI Worker gửi dữ liệu trích xuất đến Gemini API để chuẩn hóa danh mục và phân tích giao dịch.
6. AI Worker lưu bản ghi giao dịch vào Amazon RDS for SQL Server và tạo thông báo cho người dùng.
7. Bảng điều khiển (Dashboard) và Báo cáo tài chính tự động cập nhật.

### 5. Tiến độ Dự án (13 Tuần)

| Giai đoạn | Thời gian | Trọng tâm & Nhiệm vụ chính | Kết quả dự kiến |
| :--- | :--- | :--- | :--- |
| Giai đoạn 1 | Tuần 1 | Nghiên cứu Đề tài & AWS Cloud: Nghiên cứu yêu cầu dự án, thách thức theo dõi chi tiêu, mô hình SaaS & dịch vụ AWS. | Định hướng Cloud & phạm vi nghiên cứu |
| Giai đoạn 2 | Tuần 2 | Khảo sát Yêu cầu & Thiết kế Sơ bộ: Phân tích quét hóa đơn, ví, ngân sách; nghiên cứu OCR/AI; lựa chọn Angular, .NET, SQL Server & AWS. | Đặc tả yêu cầu & Sơ đồ kiến trúc |
| Giai đoạn 3 | Tuần 3 | Hình thành Ý tưởng Snaptics: Chốt tên dự án, vai trò Người dùng/Quản trị viên, tính năng cốt lõi & phạm vi demo; xây dựng product backlog. | Chốt ý tưởng & phạm vi demo |
| Giai đoạn 4 | Tuần 4 | Khởi tạo Mã nguồn: Tạo GitHub Repository; khởi tạo Angular Frontend & .NET Backend; tổ chức cấu trúc code. | Cấu trúc repository sẵn sàng phát triển |
| Giai đoạn 5 | Tuần 5 | Giao dịch & Danh mục: Phát triển API và giao diện CRUD, tìm kiếm giao dịch; quản lý danh mục. | Hệ thống giao dịch cốt lõi hoạt động |
| Giai đoạn 6 | Tuần 6 | Ví & Ngân sách: Phát triển ví cá nhân/gia đình, thành viên dùng chung, ngân sách và logic mức sử dụng. | Hoàn thiện hệ thống ví gia đình & ngân sách |
| Giai đoạn 7 | Tuần 7 | Dashboard & Lưu trữ S3: Xây dựng Dashboard, biểu đồ, báo cáo; phát triển giao diện quét hóa đơn; tích hợp lưu trữ Amazon S3. | Dashboard tương tác & tích hợp S3 |
| Giai đoạn 8 | Tuần 8 | OCR, AI & Thông báo: Tích hợp Azure Document Intelligence; chuẩn hóa kết quả; tích hợp Gemini API; xây dựng AI Insights & Chatbot. | OCR tự động & quy trình tư vấn AI hoàn chỉnh |
| Giai đoạn 9 | Tuần 9 | DLQ & Hangfire: Tạo SQS Dead Letter Queue & AI Worker bất đồng bộ; tích hợp HangfireController & giao diện lập lịch Admin. | Tác vụ AI bất đồng bộ qua SQS/DLQ & Admin Hangfire |
| Giai đoạn 10 | Tuần 10 | AWS Frontend & Database: Kết nối AWS Amplify với GitHub; lưu bí mật trong Parameter Store; khởi tạo RDS SQL Server demo. | Frontend hoạt động trên Amplify & RDS SQL Server |
| Giai đoạn 11 | Tuần 11 | VPC, SQS, ECR & Container hóa: Tạo VPC, SQS, Private Subnets; đóng gói Backend/Worker; ECR & quy trình GitHub Actions. | Mạng riêng & quy trình container ECR |
| Giai đoạn 12 | Tuần 12 | Triển khai ECS Fargate: Tạo ECS Cluster/Service; triển khai Backend & AI Worker; cấu hình ALB, Auto Scaling, CloudWatch & Budgets. | Backend/Worker chạy ổn định trên Fargate |
| Giai đoạn 13 | Tuần 13 | Hoàn thiện, Kiểm thử & Demo: Cấu hình Route 53/CloudFront; kiểm thử end-to-end, giao diện responsive, RBAC, độ bền SQS/DLQ; nhật ký kiểm toán & chi phí. | Nền tảng Snaptics sẵn sàng demo |

### 6. Dự toán Ngân sách

#### 6.1. Dự toán Môi trường Demo (1 Tháng Phát triển & Demo)

| # | Thành phần Dịch vụ | Cơ sở ước tính | Chi phí (USD) |
| :---: | :--- | :--- | :---: |
| 1 | AWS Amplify, CloudFront & Route 53 | Build/hosting Frontend, CDN lưu lượng thấp và 01 Hosted Zone | $4.50 |
| 2 | Amazon S3 | Lưu ~20 GB hình ảnh hóa đơn và yêu cầu upload/download | $1.00 |
| 3 | ECS Fargate - Backend & AI Worker | Cấu hình task nhỏ, tổng ~200-220 giờ task | $8.00 |
| 4 | Application Load Balancer (ALB) | Hoạt động trong giai đoạn triển khai & demo, lưu lượng thấp | $7.00 |
| 5 | Amazon RDS for SQL Server | SQL Server Express, Single-AZ, 20 GB | $20.00 |
| 6 | NAT Gateway & Data Transfer | 01 NAT Gateway, bật giới hạn thời gian trong lúc tích hợp | $13.00 |
| 7 | Amazon SQS, SNS & ECR | Hàng đợi OCR/AI, cảnh báo cơ bản và lưu trữ Docker Image | $1.00 |
| 8 | CloudWatch, Parameter Store & Budgets | Logs, số liệu, cảnh báo, bí mật và cảnh báo ngân sách | $3.00 |
| 9 | Azure Document Intelligence | ~1,000 trang sử dụng mô hình hóa đơn prebuilt | $10.00 |
| 10 | Gemini API | Ước tính 1M token đầu vào và 200k token đầu ra | $0.80 |

#### 6.2. Môi trường Production Multi-AZ (Tham chiếu Mở rộng Tương lai)

| Thành phần Dịch vụ | Chi phí ước tính hàng tháng |
| :--- | :--- |
| ECS Fargate & Application Load Balancer (Auto Scaling) | $60 – $150 USD |
| SQL Server Primary/Standby (Multi-AZ) | $150 – $300 USD |
| NAT Gateways kép & Data Transfer | $70 – $120 USD |
| S3, CloudFront, SQS, SNS, ECR & CloudWatch | $20 – $60 USD |
| External AI APIs (Azure Document Intelligence & Gemini) | Tính theo khối lượng hóa đơn thực tế |
| Tổng ngân sách Production ước tính | $300 – $600 USD / tháng (chưa gồm AI APIs) |

### 7. Đánh giá Rủi ro & Giảm thiểu

| # | Mô tả Rủi ro | Tác động | Xác suất | Mức độ | Chiến lược Giảm thiểu & Dự phòng |
| :---: | :--- | :---: | :---: | :---: | :--- |
| 1 | Lỗi trích xuất OCR (hóa đơn mờ, nhăn, lệch) | Cao | Trung bình | Cao | Cho phép người dùng xem xét & chỉnh sửa trước khi lưu; hiển thị ảnh gốc song song; đánh dấu các trường tin cậy thấp. |
| 2 | Azure Document Intelligence hoặc Gemini API Lỗi / Giới hạn tốc độ | Cao | Trung bình | Cao | Xử lý bất đồng bộ qua SQS; Thử lại với Exponential Backoff; định tuyến DLQ; tách lớp dịch vụ AI; dự phòng nhập liệu thủ công. |
| 3 | Rò rỉ dữ liệu tài chính hoặc lộ khóa API | Nghiêm trọng | Thấp | Cao | HTTPS bắt buộc; Bí mật trong SSM Parameter Store; IAM đặc quyền tối thiểu; Private Subnets cho DB/Worker; Audit Logging. |
| 4 | Chi phí AWS & AI vượt mức ngoài dự kiến | Cao | Trung bình | Cao | Cảnh báo AWS Budgets ở mức 50%, 80%, 100%; giới hạn Auto Scaling; nén ảnh trước khi tải lên; Chính sách S3 Lifecycle; dọn dẹp tài nguyên demo sau khi dùng. |
| 5 | Hàng đợi quét hóa đơn quá tải khi đồng thời cao | Trung bình | Trung bình | Trung bình | Giám sát độ sâu SQS Queue; mở rộng AI Workers trong giới hạn; hiển thị trạng thái xử lý trong UI; tách Backend API khỏi Workers. |
| 6 | Lỗi hồi quy khi triển khai | Trung bình | Trung bình | Trung bình | Tự động hóa kiểm thử build trong CI/CD; ECS Health Checks; Docker Tags ổn định trên ECR; tách môi trường Dev/Prod; giám sát CloudWatch. |
| 7 | Lời khuyên AI chung chung hoặc không liên quan | Trung bình | Trung bình | Trung bình | Chỉ phân tích các giao dịch người dùng đã xác nhận; trình bày AI Insights dưới dạng khuyến nghị; thu thập phản hồi người dùng để tinh chỉnh Prompt. |
| 8 | Cấu hình Hangfire sai hoặc tác vụ lỗi | Trung bình | Trung bình | Trung bình | Kiểm tra cấu hình múi giờ; chỉ Admin quản lý tác vụ; giới hạn thực thi đồng thời; ghi log chi tiết & khả năng kích hoạt thủ công. |
| 9 | Mở rộng phạm vi vượt 13 tuần | Cao | Trung bình | Cao | Ưu tiên quy trình cốt lõi; chốt phạm vi demo; phân tách backlog thành bắt buộc vs tùy chọn; kiểm thử sớm và hoãn các tính năng không thiết yếu. |

### 8. Kết quả Dự kiến

- Giải pháp Web SaaS hoàn chỉnh: Vận hành end-to-end liền mạch từ quét hóa đơn, trích xuất OCR, quản lý ngân sách cá nhân & gia đình đến báo cáo phân tích và cảnh báo tài chính.
- Kiến trúc AWS Cloud-Native đã chứng minh: Đóng gói container (ECR, ECS Fargate), hàng đợi bất đồng bộ (SQS, DLQ), quản lý cơ sở dữ liệu quan hệ (RDS SQL Server), bảo mật (SSM Parameter Store), giám sát tập trung (CloudWatch, Budgets) và tự động hóa CI/CD.
- Vận hành ổn định & quản lý chi phí: Health checks, ghi log toàn diện, xử lý lỗi DLQ và mô hình demo kiểm soát chi phí (ngân sách $76.92 USD).
- Kiến trúc mở rộng được: Được xây dựng để mở rộng liền mạch từ demo Single-AZ lên Production Multi-AZ và hỗ trợ các nâng cấp tương lai (Open Banking, Mobile App gốc).

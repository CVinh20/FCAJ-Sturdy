---
title: "Event 2"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Bài thu hoạch: "First Cloud Journey Community Day"

### Mục Đích Của Sự Kiện

- Chia sẻ kiến thức thực tế từ nhiều bài trình bày về kỹ thuật, cloud, AI, bảo mật và định hướng nghề nghiệp.
- Giới thiệu containerization với Docker và so sánh với mô hình ảo hóa truyền thống.
- Tìm hiểu bảo mật trên AWS thông qua AWS WAF và hệ thống phát hiện xâm nhập mạng dựa trên Machine Learning (NIDS).
- Minh họa cách client Godot giao tiếp qua kiến trúc AWS WebSocket.
- Giới thiệu cách xây dựng ứng dụng GraphRAG bằng Amazon Bedrock và Amazon Neptune.
- Chia sẻ lộ trình phát triển nghề nghiệp từ IT Helpdesk lên System Administrator, Cloud và DevOps.
- Nhấn mạnh vai trò của teamwork và các công cụ cộng tác số trong dự án kỹ thuật.

### Danh Sách Diễn Giả

- **Bao Huynh** - Junior Cloud Native Developer tại Endava Vietnam, Founder / Head Lab của ITea Lab.
- **Lê Hoàng Gia Đại** - Diễn giả chủ đề "WAF + ML for Cyber Attack Detection".
- **Nguyễn Quốc Bảo** - Diễn giả chủ đề "Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets".
- **Trương Huy Phước** - Diễn giả chủ đề "The Art of Effective Teamwork".
- **Việt Phát** - Sinh viên ngành AI tại Swinburne University of Technology, diễn giả chủ đề GraphRAG với Amazon Bedrock và Neptune.
- **Trần Trung Vinh** - System Administrator tại Central Retail Group, diễn giả chủ đề "From IT Helpdesk to Senior Sysadmin".

### Nội Dung Nổi Bật

#### Docker và Containerization

- Bài trình bày giải thích các khái niệm virtualization, containerization và sự khác nhau giữa virtual machine và container.
- Virtual machine truyền thống cần hệ điều hành riêng, tiêu tốn nhiều CPU, RAM, dung lượng lưu trữ và có thể quá nặng cho các ứng dụng nhỏ.
- Containerization đóng gói ứng dụng cùng toàn bộ dependencies và cấu hình cần thiết để chạy nhất quán trên nhiều môi trường.
- Docker theo tư tưởng **build once, run anywhere**, giúp quá trình phát triển, kiểm thử và triển khai dễ dự đoán hơn.
- Các khái niệm quan trọng gồm Docker container, Docker image, Dockerfile, image layer, cache khi build và các lệnh Docker cơ bản.
- Các use case phổ biến của Docker gồm CI/CD pipeline, microservices, môi trường development/testing, cloud-native application và hiện đại hóa ứng dụng cũ.

#### AWS WAF và Machine Learning-based NIDS

- AWS WAF giúp bảo vệ website, API và ứng dụng khỏi các kiểu tấn công phổ biến như SQL Injection, XSS, bot traffic, brute force và request bất thường.
- WAF dựa trên rule hoạt động tốt với các mẫu tấn công đã biết nhưng còn hạn chế trước zero-day, hybrid attack, spoofing và hành vi bất thường chưa có rule.
- Bài trình bày giới thiệu NIDS như một hệ thống giám sát traffic, phát hiện tấn công, gửi cảnh báo và hỗ trợ phân tích sự cố.
- Machine Learning có thể học từ hành vi mạng thực tế, phát hiện mẫu tấn công mới, phân tích lượng traffic lớn và thích nghi với các mối đe dọa thay đổi liên tục.
- Dự án sử dụng bộ dữ liệu **CSE-CIC-IDS2018**, thực hiện merge dữ liệu, làm sạch dữ liệu, kiểm tra tính hợp lệ, cân bằng nhãn và đánh giá mô hình.
- Kiến trúc AWS kết hợp nhiều dịch vụ như EC2, Application Load Balancer, AWS WAF, S3, Kinesis Data Firehose, Lambda, Security Hub, GuardDuty, Inspector, SNS, IAM, Config, CloudWatch và Systems Manager.

#### Godot Multiplayer với AWS WebSocket

- Bài trình bày so sánh các lựa chọn networking cho game: UDP/ENet phù hợp game cần độ trễ thấp, WebSocket phù hợp game theo lượt/lobby/chat, còn HTTP polling phù hợp chức năng đơn giản dạng stateless.
- Kiến trúc AWS sử dụng API Gateway WebSocket, Lambda, DynamoDB và CloudWatch Logs.
- API Gateway route key được dùng để xử lý `$connect`, `$disconnect`, `$default` và các route message tùy chỉnh.
- DynamoDB lưu connection ID, trạng thái người chơi, opponent ID, lựa chọn và timestamp.
- Godot dùng `WebSocketPeer` để mở kết nối, poll network event, gửi JSON message và nhận phản hồi từ server.
- Demo minh họa luồng matchmaking, người chơi chọn rock/paper/scissors, tính kết quả và xóa dữ liệu sau khi trận đấu kết thúc.
- Một số hạn chế được nêu ra gồm stale connection, chi phí DynamoDB Scan và việc Lambda không giữ state trong bộ nhớ giữa các request.

#### GraphRAG với Amazon Bedrock và Amazon Neptune

- Bài trình bày nhắc lại RAG, trong đó LLM truy xuất kiến thức bên ngoài và đưa vào prompt để tạo câu trả lời có căn cứ hơn.
- Standard RAG có thể bị giới hạn khi câu hỏi cần hiểu mối quan hệ giữa nhiều thực thể hoặc cần suy luận nhiều bước.
- GraphRAG cải thiện điểm này bằng cách lưu quan hệ giữa các entity dưới dạng edge trong graph và dùng graph traversal để đi qua nhiều tài liệu/thực thể.
- Hai hướng triển khai được giới thiệu:
  - **Fully managed route**: Amazon Bedrock Knowledge Bases xử lý chunking, entity extraction và embedding generation; Amazon Neptune Analytics đóng vai trò graph layer.
  - **Custom route**: LlamaIndex xử lý data preparation và knowledge graph construction; Amazon Neptune lưu graph, hỗ trợ multi-hop traversal và Cypher query.

#### Effective Teamwork

- Phần teamwork nhấn mạnh hiệu suất làm việc nhóm tăng lên khi cả nhóm có mục tiêu chung, vai trò rõ ràng, giao tiếp mở và tinh thần trách nhiệm cá nhân.
- Bốn nguyên tắc vàng được đề cập:
  - Clear and shared goals.
  - Right person, right place.
  - Open communication and active listening.
  - Personal accountability.
- Các công cụ như Trello, ClickUp, Google Workspace, Slack và Discord được giới thiệu để tổ chức task và cải thiện giao tiếp trong nhóm.

#### From IT Helpdesk to Senior Sysadmin

- Diễn giả chia sẻ hành trình thực tế từ IT Helpdesk lên System Administrator, sau đó mở rộng sang Cloud và DevOps.
- Những kỹ năng quan trọng ở giai đoạn Helpdesk gồm xử lý sự cố dưới áp lực, giao tiếp với end user, tư duy giải quyết vấn đề và hiểu cách hệ thống IT vận hành.
- Bước ngoặt đến từ việc học Linux, networking, tự xây dựng lab thực hành và tìm hiểu các công nghệ infrastructure.
- Ở vai trò System Administrator, các trách nhiệm quan trọng gồm provisioning server, quản lý network infrastructure, security patching, capacity planning, monitoring, documentation và automation.
- Khi chuyển sang cloud, diễn giả nhấn mạnh AWS, elastic scaling, pay-as-you-go, managed services, Infrastructure as Code với Terraform, CI/CD, Docker, automation và văn hóa DevOps.
- Lời khuyên nghề nghiệp gồm tập trung học sâu một đến hai kỹ năng cốt lõi trước, xây dựng project thật, luyện tập liên tục, dám đặt câu hỏi và không sợ thất bại.

### Những Gì Học Được

#### Tư Duy Kỹ Thuật

- Công việc hạ tầng hiện đại cần cả kiến thức nền tảng lẫn kinh nghiệm thực hành.
- Docker giúp giảm lỗi khác biệt môi trường và hỗ trợ triển khai cloud-native hiệu quả hơn.
- Bảo mật web không nên chỉ dựa vào rule có sẵn; anomaly detection và monitoring là các lớp bổ sung quan trọng.
- Kiến trúc serverless rất mạnh nhưng cần chú ý quản lý state, chi phí và observability.
- Graph-based AI hữu ích khi dữ liệu có nhiều quan hệ và câu hỏi cần suy luận qua nhiều bước.

#### Kiến Trúc và Vận Hành

- Cần chọn công nghệ theo bài toán: container cho tính portable, WebSocket cho giao tiếp real-time theo lượt, UDP cho game cần đồng bộ tần suất cao và managed AWS services cho triển khai có khả năng mở rộng.
- Chất lượng dữ liệu và cân bằng class là yếu tố rất quan trọng đối với mô hình Machine Learning trong bảo mật.
- Monitoring bằng các công cụ như CloudWatch nên được thiết lập trước khi xảy ra sự cố, không chỉ sau khi hệ thống đã gặp lỗi.
- Documentation, automation và deployment có thể lặp lại là các thói quen cần thiết trong infrastructure và DevOps.

#### Teamwork và Phát Triển Nghề Nghiệp

- Teamwork tốt phụ thuộc vào mục tiêu rõ ràng, phân công đúng người đúng việc, active listening và trách nhiệm cá nhân.
- Portfolio và kinh nghiệm thực chiến có thể tạo giá trị lớn hơn việc chỉ sưu tầm chứng chỉ.
- Phát triển nghề nghiệp đến từ những bước tiến nhỏ nhưng đều đặn, học sâu kỹ năng cốt lõi và áp dụng kiến thức vào môi trường thực tế.

### Ứng Dụng Vào Công Việc

- Dùng Docker để chuẩn hóa môi trường development và testing cho các project hiện tại.
- Áp dụng containerization khi thiết kế CI/CD pipeline hoặc triển khai microservices.
- Kết hợp log từ AWS WAF với monitoring và ý tưởng Machine Learning để tăng khả năng quan sát bảo mật.
- Thực hành xây dựng ứng dụng WebSocket nhỏ với API Gateway, Lambda và DynamoDB để hiểu rõ giao tiếp real-time trên cloud.
- Tìm hiểu GraphRAG khi xây dựng hệ thống AI cần trả lời dựa trên quan hệ giữa nhiều tài liệu hoặc entity.
- Sử dụng Trello, ClickUp, Slack, Discord hoặc Google Workspace để quản lý task và giao tiếp nhóm rõ ràng hơn.
- Xây dựng lab cá nhân về Linux, networking, AWS, Docker, Terraform và CI/CD để củng cố kỹ năng Cloud/DevOps.

### Trải nghiệm trong event

Tham gia **First Cloud Journey Community Day** vào ngày **9 tháng 5 năm 2026** là một trải nghiệm rất bổ ích vì chương trình kết hợp nhiều chủ đề: technical demo, cloud architecture, AI, cybersecurity, teamwork và định hướng nghề nghiệp.

#### Học hỏi từ nhiều góc nhìn khác nhau

- Phần Docker giúp tôi hiểu rõ hơn vì sao container nhẹ hơn virtual machine và vì sao container quan trọng trong triển khai ứng dụng hiện đại.
- Phần AWS WAF và ML NIDS giúp tôi hình dung cách cloud security có thể kết hợp rule-based filtering với behavior-based detection.
- Demo Godot WebSocket giúp kiến trúc serverless real-time trở nên dễ hiểu hơn thông qua luồng game multiplayer đơn giản.
- Phần GraphRAG cho thấy ứng dụng AI có thể chính xác hơn khi hiểu được quan hệ giữa các entity.

#### Trải nghiệm kỹ thuật thực tế

- Tôi hiểu cách Docker image, container, Dockerfile và cached layer phối hợp trong quá trình build container.
- Tôi thấy được một dự án Machine Learning cho bảo mật cần làm sạch dữ liệu, cân bằng nhãn, đánh giá mô hình và lên kế hoạch triển khai trên cloud.
- Tôi hiểu vai trò của API Gateway, Lambda, DynamoDB và CloudWatch trong một ứng dụng WebSocket serverless.
- Tôi biết GraphRAG có thể được triển khai bằng hướng fully managed trên AWS hoặc bằng custom pipeline với LlamaIndex và Neptune.

#### Bài học về nghề nghiệp và teamwork

- Phần chia sẻ về Sysadmin nhắc tôi rằng nền tảng Linux, networking, troubleshooting và documentation vẫn cực kỳ quan trọng.
- Phần teamwork cho thấy kỹ năng kỹ thuật thôi là chưa đủ; giao tiếp rõ ràng và trách nhiệm cá nhân ảnh hưởng trực tiếp đến kết quả dự án.
- Sự kiện khuyến khích tôi tiếp tục xây dựng các project thực hành và học từng bước thay vì cố gắng học mọi thứ cùng lúc.

#### Bài học rút ra

- Kiến thức Cloud và DevOps dễ hiểu hơn rất nhiều khi được gắn với ví dụ thực tế và demo cụ thể.
- Security, AI, infrastructure và application development ngày càng liên kết chặt chẽ trong các hệ thống hiện đại.
- Một kỹ sư tốt cần vừa có chiều sâu kỹ thuật vừa có khả năng cộng tác tốt với người khác.

#### Một số hình ảnh khi tham gia sự kiện

*Thêm các hình ảnh của các bạn tại đây*

> Tổng thể, sự kiện giúp tôi mở rộng góc nhìn về các công nghệ cloud hiện đại và đưa ra nhiều định hướng thực tế để cải thiện kỹ năng kỹ thuật, thói quen teamwork và kế hoạch phát triển nghề nghiệp lâu dài.

---
title: "Event 1"
date: 2026-05-09
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Bài thu hoạch: “Automated Prompt Engineering: Enhancing LLM Output Quality”

### Mục Đích Của Sự Kiện

- Xác định các vấn đề chính gây ra bởi việc thiết kế prompt không tốt (kết quả chung chung, lãng phí token/chi phí tăng, chỉ dẫn mơ hồ/kết quả không nhất quán, giảm năng suất).
- Tìm hiểu các thành phần cấu thành một prompt tốt và các best practices để tạo ra các chỉ dẫn rõ ràng, cụ thể.
- Hiểu rõ về kinh tế học token và các kỹ thuật prompting nâng cao (CoT, Self-Consistency, ToT, RAG, Role Prompting).
- Giới thiệu công cụ Proptimizer (một tiện ích mở rộng trình duyệt hỗ trợ tối ưu prompt và chat với AI) và kiến trúc serverless trên nền tảng AWS.

### Danh Sách Diễn Giả

- **Nguyen Tuan Thinh** – DevOps/Cloud Engineer

### Nội Dung Nổi Bật

#### Tầm quan trọng của Prompt Engineering

- **Prompt chung chung → Kết quả chung chung**: Những câu lệnh đơn giản, thiếu thông tin sẽ nhận lại câu trả lời sơ sài và kém hữu ích.
- **Lãng phí token → Tăng chi phí**: Các câu lệnh viết không tốt sẽ tiêu hao tài nguyên xử lý không đáng có.
- **Chỉ dẫn mơ hồ → Kết quả không nhất quán**: Việc thiếu cấu trúc khiến AI đưa ra kết quả không ổn định và khó đoán trước.
- **Giao tiếp kém hiệu quả → Giảm năng suất**: Tương tác không hiệu quả với AI làm tốn thời gian của lập trình viên và nhà thiết kế.

#### Các ví dụ so sánh Prompt

- **Tóm tắt văn bản (Summary)**:
  - *Prompt xấu*: `"Summarize the following text:"`
  - *Prompt tốt*: `"Summarize the following text for a high school student. The summary should be no more than 50 words and focus on the main ideas and key takeaways. Ensure it uses simple, easy-to-understand language."`
- **Bài đăng mạng xã hội (Social Media)**:
  - *Prompt xấu*: `"Write a few social media posts for our new product."`
  - *Prompt tốt*: `"Create 3 short Instagram posts (under 150 characters each) to promote our new eco-friendly reusable water bottle. Target audience: environmentally-conscious youth (18-30 years old). Include a call to action (CTA) to our product page. Use a friendly, inspiring, and slightly playful tone."`

#### Các thành phần của một prompt tốt (Key Components)

- **Vai trò (Role)**: Xác định rõ mô hình đang đóng vai ai (Ví dụ: Chuyên gia hướng nghiệp cho sinh viên mới tốt nghiệp).
- **Chỉ dẫn/Nhiệm vụ (Instruction/Task)**: Chỉ định rõ việc mô hình cần thực hiện (Ví dụ: Cải thiện phần tự giới thiệu bản thân khi đi thực tập).
- **Ngữ cảnh (Context)**: Cung cấp thông tin nền tảng liên quan (Ví dụ: Kỹ sư DevOps có kinh nghiệm về AWS, backend và dự án thực tế).
- **Dữ liệu đầu vào (Input Data)**: Đoạn văn bản cụ thể cần xử lý (Ví dụ: `"Hello, my name is Thinh..."`).
- **Ví dụ (Examples / Few-Shot)**: Cung cấp minh họa về kết quả mong muốn (Ví dụ: `"I like programming" → "I enjoy programming..."`).
- **Định dạng đầu ra (Output Format)**: Quy định cấu trúc/phong cách phản hồi (Ví dụ: Bản cải tiến kèm giải thích ngắn gọn).
- **Ràng buộc (Constraints/Guidelines)**: Đưa ra giới hạn hoặc yêu cầu bắt buộc (Ví dụ: Dưới 80 từ, đơn giản, tự nhiên, rõ ràng, tự tin).

#### Nguyên tắc thiết kế Prompt (Best Practices)

- Rõ ràng và cụ thể.
- Sử dụng ngôn từ có tính chỉ dẫn/mệnh lệnh trực tiếp.
- Sử dụng các ký tự phân tách (như triple quotes, thẻ XML) để phân chia các phần.
- Mô tả những việc NÊN LÀM thay vì những việc KHÔNG NÊN LÀM.
- Tránh yêu cầu LLM thực hiện các phép toán phức tạp trực tiếp.
- Cho phép mô hình trả lời `"Tôi không biết"` để ngăn chặn hiện tượng ảo tưởng (hallucination).
- Chia nhỏ các dữ liệu đầu vào dài thành các phần nhỏ hơn để dễ xử lý.

#### Kinh tế học Token & Kỹ thuật nâng cao

- **Token Economics**: Token là các đơn vị từ con mà LLM dùng để đọc/ghi văn bản. Số lượng token khác nhau tùy theo ngôn ngữ. Đây là yếu tố cốt lõi để quản lý chi phí khi gọi các API trả phí (như Claude 3.5 Sonnet / Claude 3 Opus).
- **Các kỹ thuật nâng cao**:
  - **Chain-of-Thought (CoT)**: Gợi ý LLM giải thích từng bước lập luận trước khi đưa ra kết quả.
  - **Self-Consistency**: Chạy nhiều đường lập luận CoT khác nhau và lấy kết quả theo số đông biểu quyết.
  - **Tree-of-Thoughts (ToT)**: Cho phép LLM tìm kiếm và quay lui (backtrack) qua nhiều nhánh lập luận khác nhau.
  - **Retrieval-Augmented Generation (RAG)**: Kết nối cơ sở dữ liệu hoặc tìm kiếm bên ngoài với LLM.
  - **Role Prompting**: Thiết lập một vai trò cụ thể để định hình ngữ cảnh phản hồi.

#### Giới thiệu Proptimizer & Kiến trúc giải pháp

- **Proptimizer**: Một tiện ích mở rộng trình duyệt giúp tối ưu hóa prompt và tích hợp chat AI ngay trên bất kỳ trang web nào.
- **Kiến trúc Serverless trên AWS**:
  - **Frontend & CDN**: AWS CloudFront (mạng phân phối nội dung toàn cầu) và Amazon S3 (lưu trữ và hosting website tĩnh).
  - **Xác thực & Bảo mật**: Amazon Cognito (quản lý đăng ký, đăng nhập và tạo JWT token).
  - **API & Backend Logic**: Amazon API Gateway (điều phối request, rate limiting) và AWS Lambda (thực thi code backend dạng không máy chủ).
  - **Tích hợp AI**: Amazon Bedrock (giao diện API không máy chủ để truy cập các mô hình nền tảng như Claude).
  - **Cơ sở dữ liệu**: Amazon DynamoDB (NoSQL database có khả năng mở rộng tốt để lưu lịch sử tối ưu và thông tin người dùng).
  - **Giám sát & Vận hành**: Amazon CloudWatch Logs (lưu log hệ thống để truy vết) và Amazon CloudWatch Metrics (theo dõi latency, tỷ lệ lỗi và dashboard sức khỏe hệ thống).

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Tư duy ngữ cảnh (Context-First)**: Luôn cung cấp đầy đủ ngữ cảnh, vai trò cụ thể và định dạng đầu ra rõ ràng.
- **Prompt có cấu trúc**: Tận dụng các thành phần của prompt để xây dựng quy trình AI ổn định và có khả năng tái tạo.
- **Tối ưu hóa token**: Luôn chú ý tinh giảm kích thước prompt và cân nhắc ngôn ngữ dịch thuật để tối ưu hóa chi phí vận hành.

#### Kiến Trúc Kỹ Thuật

- **Hệ sinh thái Serverless**: Kết hợp S3, CloudFront, Lambda và API Gateway giúp tạo ra hệ thống mở rộng tự động với chi phí cực kỳ rẻ.
- **Tích hợp Bedrock**: Amazon Bedrock giúp triển khai các tính năng LLM nhanh chóng mà không cần bận tâm về hạ tầng hay quản lý server.
- **Khả năng quan sát (Observability)**: Thiết lập CloudWatch logs và dashboard metrics là bắt buộc để theo dõi lỗi và latency của các hệ thống serverless thực tế.

#### Các mô hình AI hiện đại

- Áp dụng các **kỹ thuật prompting nâng cao** (như CoT, RAG hoặc các framework agentic) cho các tác vụ tự động hóa phức tạp thay vì chỉ sử dụng prompt một lượt đơn giản.

### Ứng Dụng Vào Công Việc

- **Cấu trúc lại prompt hàng ngày**: Áp dụng các thành phần Vai trò, Ngữ cảnh và Ràng buộc để làm việc hiệu quả và tiết kiệm chi phí token hơn.
- **Nâng cao hiệu suất lập trình**: Sử dụng prompt engineering để tối ưu code review, sinh unit test và tra cứu tài liệu nhanh chóng.
- **Ứng dụng AWS Serverless**: Đề xuất kiến trúc S3/CloudFront và Lambda cho các ứng dụng nội bộ hoặc tiện ích nhỏ của công ty.
- **Nghiên cứu Amazon Bedrock**: Thử nghiệm tích hợp API của Bedrock để xây dựng các tính năng AI trong các dự án hiện có.
- **Sử dụng Proptimizer**: Tải và dùng thử tiện ích Proptimizer từ địa chỉ `https://d3jqm7so635aqb.cloudfront.net` để tăng năng suất làm việc mỗi ngày.

### Trải nghiệm trong event

Tham gia workshop **“Automated Prompt Engineering: Enhancing LLM Output Quality”** là một trải nghiệm rất bổ ích, giúp tôi có cái nhìn toàn diện về cách viết prompt hiệu quả cũng như cách xây dựng các ứng dụng AI không máy chủ (serverless) trên AWS. Một số trải nghiệm nổi bật:

#### Học hỏi từ các diễn giả có chuyên môn cao
- Học hỏi cách diễn giả Nguyễn Tuấn Thịnh thiết kế và triển khai một tiện ích AI thực tế, chia sẻ những **best practices** trong thiết kế phần mềm GenAI hiện đại.
- Thông qua các bài so sánh trực quan và case study cụ thể, tôi hiểu rõ cách khắc phục tính không ổn định của prompt và nâng cao chất lượng phản hồi từ LLM.

#### Trải nghiệm kỹ thuật thực tế
- Phân tích kinh tế học token và nghiên cứu các mô hình suy luận nâng cao như **Chain-of-Thought (CoT)** và **Tree-of-Thoughts (ToT)**.
- Hiểu sâu hơn về kiến trúc serverless qua việc phân tích cách phối hợp hoạt động giữa **API Gateway**, **AWS Lambda**, và **DynamoDB**.

#### Ứng dụng công cụ hiện đại
- Trực tiếp tìm hiểu và sử dụng tiện ích **Proptimizer** giúp hợp lý hóa và tối ưu quy trình làm việc với prompt.
- Biết cách kết nối các mô hình AI thông qua Amazon Bedrock một cách dễ dàng và an toàn.

#### Kết nối và trao đổi
- Trao đổi trực tiếp với các kỹ sư khác về vấn đề quản lý rate-limit của API, xác thực người dùng bằng **Cognito** và giám sát hệ thống với **CloudWatch**.

#### Bài học rút ra
- Output chất lượng cao từ LLM đòi hỏi **chỉ dẫn có cấu trúc rõ ràng** thay vì những câu lệnh ngắn thông thường.
- Kiến trúc Serverless trên AWS là lựa chọn hoàn hảo để xây dựng các **giải pháp AI tinh gọn, tiết kiệm chi phí và khả năng mở rộng tốt**.
- Giám sát là cực kỳ quan trọng; một dashboard **CloudWatch metrics** tốt sẽ hỗ trợ đắc lực cho việc debug latency và lỗi hệ thống.

#### Một số hình ảnh khi tham gia sự kiện
* Thêm các hình ảnh của các bạn tại đây

> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp tôi thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.

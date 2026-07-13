---
title: "Worklog Tuần 2"
date: 2026-04-25
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 2:

* Thực hành triển khai EC2 ở cả public subnet và private subnet để hiểu mô hình phân tách truy cập trong AWS.
* Tìm hiểu cách kết nối EC2, đồng thời nắm vai trò của DNS và Route 53 trong việc định tuyến tên miền.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 1 | - Tạo EC2 public và EC2 private, kiểm tra sự khác nhau về khả năng truy cập giữa hai loại instance. | 25/04/2026 - 03/05/2026 | 25/04/2026 - 03/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 2 | - Thực hành kết nối vào EC2, rà soát các yếu tố liên quan như key pair, security group, public IP và cấu hình mạng. | 25/04/2026 - 03/05/2026 | 25/04/2026 - 03/05/2026 |  |
| 3 | - Tìm hiểu Route 53 và DNS, ghi chú cách domain name được phân giải và điều hướng đến tài nguyên phù hợp. | 25/04/2026 - 03/05/2026 | 25/04/2026 - 03/05/2026 |  |
| 4 | - Thực hành tạo cấu hình Route 53 ở mức cơ bản để hiểu cách quản lý bản ghi và liên kết tên miền với tài nguyên AWS. | 25/04/2026 - 03/05/2026 | 25/04/2026 - 03/05/2026 |  |


### Kết quả đạt được tuần 2:

* Triển khai được EC2 public và EC2 private phục vụ cho các bài thực hành hạ tầng.
* Hiểu rõ hơn sự khác nhau giữa tài nguyên public và private trong kiến trúc cloud.
* Nắm được các điều kiện cần thiết để kết nối an toàn vào EC2.
* Hiểu vai trò của DNS và Route 53 trong việc quản lý truy cập thông qua tên miền.
* Có thêm kinh nghiệm kiểm tra lỗi kết nối liên quan đến security group, key pair và cấu hình mạng.

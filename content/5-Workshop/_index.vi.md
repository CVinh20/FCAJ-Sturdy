---
title: "Workshop"
date: 2026-04-17
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


# Xây dựng ứng dụng trích xuất và phân tích tài liệu tự động - DocuMind AI

#### Tổng quan

**DocuMind AI** là một ứng dụng xử lý tài liệu thông minh dựa trên kiến trúc Cloud-Native, kết hợp các dịch vụ hạ tầng AWS và các API AI tiên tiến như Google Gemini và OpenAI.

Trong workshop này, chúng ta sẽ học cách thiết kế, triển khai và vận hành một luồng xử lý tài liệu bất đồng bộ đầy đủ: từ việc lưu trữ, xếp hàng xử lý, trích xuất dữ liệu thô (OCR) cho đến phân tích ngữ nghĩa, giao tiếp thông minh với tài liệu (Chat/RAG), giám sát hệ thống và bảo mật tài nguyên.

#### Nội dung

1. [Tổng quan về workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Tạo S3 Document Storage](5.3-Create-S3-Document-Storage/)
4. [Tạo SQS Processing Queue](5.4-Create-SQS-Processing-Queue/)
5. [Tích hợp Textract OCR](5.5-Integrate-Textract-OCR/)
6. [Tích hợp các AI Providers](5.6-Integrate-AI-Providers/)
7. [PostgreSQL & Prisma Database](5.7-PostgreSQL-Prisma-Database/)
8. [Backend API và Worker](5.8-Backend-API-and-Worker/)
9. [Frontend Dashboard](5.9-Frontend-Dashboard/)
10. [Notification & Admin](5.10-Notification-and-Admin/)
11. [IAM Role & Policy](5.11-IAM-Role-and-Policy/)
12. [Monitoring & Security](5.12-Monitoring-and-Security/)
13. [Deployment & Test](5.13-Deployment-and-Test/)
14. [Dọn dẹp tài nguyên](5.14-Cleanup/)
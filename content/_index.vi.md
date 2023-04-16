---
title : "Đảm bảo truy cập Hybrid an toàn đến S3 bằng cách sử dụng VPC endpoint"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

# Đảm bảo truy cập Hybrid an toàn đến S3 bằng cách sử dụng VPC endpoint

#### Tổng quan

**AWS PrivateLink** cung cấp kết nối riêng tư đến các dịch vụ aws từ VPCs hoặc trung tâm dữ liệu (on-premise) mà không làm lộ lưu lượng truy cập ra ngoài public internet.

Trong bài lab này, chúng ta sẽ học cách tạo, cấu hình, và kiểm tra VPC endpoints để cho phép workload của bạn tiếp cận các dịch vụ AWS mà không cần đi qua Internet công cộng.

Chúng ta sẽ tạo hai loại endpoints để truy cập đến Amazon S3: gateway vpc endpoint và interface vpc endpoint. Hai loại vpc endpoints này mang đến nhiều lợi ích tùy thuộc vào việc bạn truy cập đến S3 từ môi trường cloud hay từ trung tâm dữ liệu (on-premise).
+ **Gateway** - Tạo gateway endpoint để gửi lưu lượng đến Amazon S3 hoặc DynamoDB using private IP addresses. Bạn điều hướng lưu lượng từ VPC của bạn đến gateway endpoint bằng các bảng định tuyến (route tables)
+ **Interface** - Tạo interface endpoint để gửi lưu lượng đến các dịch vụ điểm cuối (endpoints) sử dụng Network Load Balancer để phân phối lưu lượng. Lưu lượng dành cho dịch vụ điểm cuối được resolved bằng DNS.

#### Nội dung

1. [Tổng quan về workshop](1-workshop-overview)
2. [Chuẩn bị](2-prerequiste/)
3. [Truy cập đến S3 từ VPC](3-s3-vpc/)
4. [Truy cập đến S3 từ TTDL On-premises](4-s3-onprem/)
5. [VPC Endpoint Policies (làm thêm)](5-policy/)
6. [Dọn dẹp tài nguyên](6-cleanup/)

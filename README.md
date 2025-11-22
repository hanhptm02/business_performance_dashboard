# Xây dựng dashboard theo dõi hoạt động kinh doanh của MH Finance Solutions
1. Giới thiệu  
Chuyển đổi dữ liệu thô thành báo cáo trực quan trên Power BI để phục vụ công tác theo dõi hoạt động kinh doanh của MH Finance Solutions

2. Input data  
Nguồn dữ liệu là các file excel sau:
- fact_kpi_month: Thông tin của hồ sơ theo tháng
- fact_txn_month: Thông tin giao dịch của các tài khoản GL
- fact_kpi_asm: Thông tin về kết quả kinh doanh của từng Area Sales Manager (ASM) Files
  
3. Output  
Dashboard theo dõi hoạt động kinh doanh của ... Files

4. Công cụ sử dụng  
Excel  
DBeaver + PostgreSQL  
Power BI

6. Quy trình sử lý
- Step 1: Data Preparation  
Format lại file excel trước khi import vào Database:
-- Bỏ merge cell
-- Đặt lại tên cột  
Chuyển dữ liệu vào bảng Staging để chuẩn hóa dữ liệu trước khi lưu trữ trong các bảng fact (nếu cần).  
Kiểm tra dữ liệu đã import đúng với file excel. Lưu trữ dữ liệu sau khi đã được transform trong các bảng fact
- Step 2: Data Processing  
Từ dữ liệu input đã được lưu trong bảng fact, tính toán các metric phục vụ dashboard và lưu trong các bảng fact bằng cách Xây dựng procedure với input là thời gian để insert dữ liệu vào các bảng fact này.
- Step 3: Visualization  
Tạo view, import các dữ liệu cần sử dụng sang Power BI  
Lập danh sách các metric quan trọng cần theo dõi thành các chart và nguồn dữ liệu tương ứng  
Dựng các chart, format dashboard trên Power BI

Quy trình trên được tóm gọn trong sơ đồ sau:
![alt text](https://github.com/hanhptm02/business_performance_dashboard/blob/main/Data%20Linage.drawio.png)

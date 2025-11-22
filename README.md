# Xây dựng dashboard theo dõi hoạt động kinh doanh của MH Finance Solutions
1. **Giới thiệu**   
Chuyển đổi dữ liệu thô thành báo cáo trực quan trên Power BI để phục vụ công tác theo dõi hoạt động kinh doanh của MH Finance Solutions

2. **Input data**  
Nguồn dữ liệu là các file excel sau:
- fact_kpi_month: Thông tin của hồ sơ theo tháng
- [fact_txn_month_raw_data](fact_txn_month_raw_data_202402020504.xlsx): Thông tin giao dịch của các tài khoản GL
- [fact_kpi_asm](kpi_asm_data_202305.xlsx): Thông tin về kết quả kinh doanh của từng Area Sales Manager (ASM) Files
  
3. **Output**
Sản phẩm cuối cùng là Dashboard Power BI phục vụ theo dõi hoạt động kinh doanh:
* Báo cáo kết quả kinh doanh trong tháng theo khu vực
* Báo cáo kết quả kinh doanh của Area Sales Manager trong tháng
* Theo dõi tổng quan hoạt động kinh doanh của doanh nghiệp
* Theo dõi kết quả hoạt động kinh doanh theo từng khu vực
* Theo dõi kết quả hoạt động kinh doanh theo từng nhân viên kinh doanh

5. **Công cụ sử dụng**  
Excel  
DBeaver + PostgreSQL  
Power BI

6. **Quy trình sử lý**
- Step 1: Data Preparation  
  - Format lại file Excel trước khi import vào Database:
      - Bỏ merge cell  
      - Đặt lại tên cột  
  - Lưu dữ liệu chưa chuẩn hóa vào bảng Staging (nếu cần).  
  - Kiểm tra dữ liệu đã import đúng với file Excel.  
  - Transform dữ liệu và lưu vào các bảng Fact.
- Step 2: Data Processing  
Xây dựng Procedure với tham số thời gian để lưu trữ các chỉ tiêu cần theo dõi vào bảng fact
  * fact_area_metrics_monthly: Lưu giá trị của các chỉ tiêu tại từng khu vực hàng tháng
  * fact_asm_metrics_monthly: Lưu giá trị của các chỉ tiêu của từng nhân viên kinh doanh hàng tháng
- Step 3: Visualization  
  * Lập danh sách các metric quan trọng cần theo dõi thành các chart và nguồn dữ liệu tương ứng
  * Tạo view, import các dữ liệu cần sử dụng sang Power BI  
  * Dựng các chart, format dashboard trên Power BI

Quy trình trên được trình bày trong sơ đồ sau:
![alt text](https://github.com/hanhptm02/business_performance_dashboard/blob/main/Data%20Linage.drawio.png)

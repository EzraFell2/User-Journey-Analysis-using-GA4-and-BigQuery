# 📊 Phân tích dữ liệu GA4 bằng BigQuery & Google Colab

## 📌 Giới thiệu
Repo này chứa toàn bộ code và notebook phục vụ cho việc:
- Kết nối **Google BigQuery** với **Google Colab**  
- Truy vấn dữ liệu sự kiện từ **Google Analytics 4 (GA4)**  
- Chuẩn hóa, phân loại URL và hành vi người dùng  
- Phân tích hành vi, tạo funnel và trực quan hóa dữ liệu  

Mục tiêu: hỗ trợ nghiên cứu học thuật và báo cáo môn học về **phân tích hành vi người dùng trên website fidovn.com**.

---

## ✅ Checklist các đầu việc chính
1. **Chuẩn bị môi trường**  
   - Tạo Service Account trên GCP, cấp quyền BigQuery  
   - Tải file key JSON, upload lên Colab  
   - Cấu hình `google.cloud.bigquery.Client`  

2. **Truy vấn dữ liệu GA4**  
   - Sử dụng `events_*` và `events_intraday_*`  
   - Lọc dữ liệu theo `event_date` hoặc `_TABLE_SUFFIX`  
   - Trích xuất các tham số (`event_params`) như `page_location`  

3. **Tiền xử lý dữ liệu**  
   - Chuẩn hóa URL (`clean_page`)  
   - Thiết kế **pattern** phân loại:
     - Homepage (`https://www.fidovn.com/`)  
     - Job List (`/viec-lam`)  
     - Job Detail (`/viec-lam/...`)  
     - Real Estate (`/bat-dong-san`)  
     - Other  
   - Tạo cột `page_category`  

4. **Phân tích & trực quan hóa**  
   - Funnel: hành vi tìm việc / xem bất động sản  
   - Donut Chart (Plotly): tỉ lệ page category  
   - Heatmap (Seaborn): nguồn truy cập × loại trang  
   - User Path: sử dụng `ARRAY_AGG` để xây dựng chuỗi hành vi  

---

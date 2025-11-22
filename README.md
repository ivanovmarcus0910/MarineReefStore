# AquariumShop – Hệ thống quản lý cửa hàng san hô, cá biển & linh kiện hồ cá cảnh

Hệ thống web hỗ trợ quản lý **bán lẻ san hô, cá biển, thiết bị – linh kiện hồ cá** và chăm sóc khách hàng chơi hồ cá cảnh.

Xây dựng bằng **Java Servlet + JSP (JSP/Servlet, JDBC, JSTL)**, deploy trên **Apache Tomcat**.

---

## 🎯 Mục tiêu hệ thống

- Quản lý **tồn kho** san hô, cá biển, thiết bị & vật tư.
- Hỗ trợ **bán hàng tại quầy** và quản lý đơn hàng.
- Lưu trữ **thông tin kỹ thuật** (ánh sáng, độ mặn, reef-safe, mức độ khó…).
- Tư vấn **combo hồ cá** phù hợp trình độ & ngân sách khách.

---

## 👥 Vai trò người dùng

- **Admin / Chủ cửa hàng**
  - Quản lý danh mục & sản phẩm.
  - Quản lý nhân viên, giá bán, khuyến mãi.
  - Xem báo cáo doanh thu, tồn kho.

- **Nhân viên bán hàng**
  - Tạo đơn hàng, xử lý thanh toán.
  - Cập nhật tình trạng san hô/cá (available / hold / sold).

- **Khách hàng (nếu có module client)**
  - Xem sản phẩm / combo hồ.
  - Gửi yêu cầu tư vấn, đặt hàng online.

---

## 🧩 Nhóm sản phẩm chính

### 🪸 San hô
- San hô mềm, LPS, SPS.
- Thuộc tính:
  - Ánh sáng: Low / Medium / High.
  - Dòng chảy: Low / Medium / High.
  - Độ khó: Dễ / Trung bình / Khó.
  - Reef: vị trí (bottom/mid/top), ghi chú chăm sóc.

### 🐠 Cá biển & sinh vật
- Cá biển, tôm, cua, ốc, CUC (cleanup crew).
- Thuộc tính:
  - Kích thước, tính cách (hiền / hung).
  - Tank size khuyến nghị.
  - Reef-safe / not reef-safe.
  - Level người chơi.

### ⚙️ Thiết bị & linh kiện hồ
- Hồ, sump, cabinet.
- Skimmer, bơm, wavemaker, đèn, lọc.
- Vật tư: muối, đá sống, vi sinh, test kit, thức ăn.

---

## ✨ Tính năng chính

### 1. Quản lý danh mục & sản phẩm
- Quản lý danh mục: San hô / Cá / Thiết bị / Vật tư.
- Sản phẩm:
  - Tên, mã, hình ảnh, mô tả.
  - Giá vốn, giá bán, đơn vị tính.
  - Thuộc tính chuyên ngành (ánh sáng, độ mặn, reef-safe, level…).
- Gắn tag như: `Beginner-friendly`, `Reef-safe`, `SPS only`…

### 2. Quản lý tồn kho
- Tồn kho theo:
  - Chủng loại sản phẩm.
  - Vị trí: hồ số mấy / bể quarantine / kho.
- Lịch sử nhập – xuất – điều chỉnh.
- Cảnh báo sản phẩm sắp hết / hết hàng.

### 3. Bán hàng & đơn hàng
- Bán tại quầy:
  - Tìm sản phẩm theo tên / mã.
  - Thêm nhiều loại mặt hàng vào 1 hóa đơn.
  - Áp dụng giảm giá / combo.
- Quản lý đơn hàng:
  - Trạng thái: Chờ xử lý → Đang chuẩn bị → Hoàn thành / Hủy.
  - Ghi chú ship: đóng oxy, thùng xốp, nhận tại cửa hàng.

### 4. Combo hồ cá & tư vấn cấu hình
- Tạo combo hồ:
  - Kích thước hồ, loại chơi: Reef / Fish-only.
  - Thiết bị yêu cầu: bể, sump, skimmer, đèn, wavemaker, vật liệu lọc…
  - Gợi ý san hô/cá phù hợp.
- Tính tổng chi phí combo, in báo giá cho khách.
- Lưu cấu hình hồ của khách để chăm sóc sau bán.

### 5. Quản lý khách hàng
- Thông tin khách: tên, số điện thoại, địa chỉ.
- Thông tin hồ: kích thước, loại hệ, tuổi tank.
- Lịch sử mua hàng & ghi chú chăm sóc.

### 6. Báo cáo
- Doanh thu theo ngày/tháng.
- Top sản phẩm bán chạy.
- Giá trị tồn kho, hàng quay vòng chậm.

---

## 🏗️ Công nghệ sử dụng

- **Ngôn ngữ:** Java 8+ (hoặc cao hơn)
- **Web:**
  - Java Servlet (javax.servlet)
  - JSP + JSTL
- **Server:** Apache Tomcat 9+  
- **Database:** MySQL / MariaDB (JDBC)
- **Front-end:**
  - JSP, HTML5, CSS3
  - Bootstrap (nếu dùng)
- **Build:** Maven (khuyến nghị)

---

## 📁 Cấu trúc dự án (mẫu Maven)

```text
aquarium-shop/
 ├─ src/
 │   ├─ main/
 │   │   ├─ java/
 │   │   │   └─ com.aquariumshop
 │   │   │       ├─ controller/     (Servlet)
 │   │   │       ├─ dao/            (JDBC DAO)
 │   │   │       ├─ model/          (Entity / POJO)
 │   │   │       └─ util/           (DBConnection, helper)
 │   │   ├─ resources/
 │   │   └─ webapp/
 │   │       ├─ WEB-INF/
 │   │       │   ├─ views/          (JSP)
 │   │       │   └─ web.xml
 │   │       ├─ assets/             (CSS, JS, images)
 │   │       └─ index.jsp
 └─ pom.xml

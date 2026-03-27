# TÀI LIỆU ĐẶC TẢ YÊU CẦU PHẦN MỀM (SRS)
## Quản lý Thông tin Sản phẩm (PIM)
**Dự án:** Website bán thiết bị ngành ảnh Kochi Lens

# 1. Giới thiệu

## 1.1. Mục đích
Tài liệu này mô tả chi tiết các yêu cầu cho chức năng Quản lý Thông tin Sản phẩm (PIM).

## 1.2. Phạm vi
Chức năng PIM quản lý:
- Thông tin sản phẩm
- Biến thể sản phẩm
- Giá bán và thuế VAT
- Tồn kho realtime

---

# 2. Tổng quan hệ thống

## 2.1. Tác nhân
- Admin
- Khách hàng (Customer)
- Nhân viên kho (Warehouse Staff)

## 2.2. Tổng quan
PIM là nguồn dữ liệu trung tâm cho:
- Giỏ hàng
- Quản lý đơn hàng
- Kho
- Kế toán

---

# 3. Luồng nghiệp vụ

## 3.1. Use Case

### UC-01: Quản lý sản phẩm (Admin)
- Tạo sản phẩm
- Cập nhật sản phẩm
- Xóa sản phẩm

### UC-02: Quản lý biến thể (Admin)
- Tạo biến thể (màu, size)
- Gán SKU cho từng biến thể
- Quản lý SKU, barcode, giá, VAT  
- Quản lý biến thể  


### UC-03: Xem sản phẩm (Customer)
- Xem danh sách
- Xem chi tiết
- Chọn biến thể  
- Kiểm tra tồn kho  
- Thêm vào giỏ hàng 

### UC-04: Chọn biến thể (Customer)
- Chọn biến thể
- Kiểm tra tồn kho
- Thêm vào giỏ

### UC-05: Cập nhật tồn kho (Warehouse)
- Cập nhật số lượng
- Đồng bộ hệ thống

---

## 3.2. Activity Flow

Start  
→ Xem sản phẩm  
→ Chọn sản phẩm  
→ Chọn biến thể  
→ Kiểm tra tồn kho  
→ Thêm vào giỏ hàng 
→ Nhập địa chỉ  
→ Tính thuế + phí ship   
→ Thanh toán  
→ Xác nhận đơn  
→ Cập nhật tồn kho  
→ End  

---

# 4. Yêu cầu chức năng

## 4.1.User Stories
Nhóm 1: Quản lý sản phẩm cơ bản

US-01
Là một Admin, tôi muốn tạo mới sản phẩm để hệ thống có thể hiển thị sản phẩm lên website bán hàng.

US-02
Là một Admin, tôi muốn cập nhật thông tin sản phẩm để đảm bảo dữ liệu hiển thị cho khách hàng luôn chính xác.

US-03
Là một Admin, tôi muốn gán mã SKU và barcode cho từng sản phẩm để dễ quản lý và đồng bộ với kho.

US-04
Là một Admin, tôi muốn thiết lập trạng thái hoạt động/ngừng kinh doanh cho sản phẩm để chủ động kiểm soát việc bán hàng.

Nhóm 2: Quản lý biến thể sản phẩm
US-05
Là một Admin, tôi muốn tạo nhiều biến thể cho một sản phẩm theo màu sắc và kích thước để khách hàng có thể chọn đúng phiên bản mong muốn.

US-06
Là một Admin, tôi muốn mỗi biến thể có SKU riêng để quản lý tồn kho và bán hàng chính xác.

US-07
Là một Customer, tôi muốn chọn biến thể sản phẩm trước khi thêm vào giỏ hàng để mua đúng màu sắc hoặc kích thước tôi cần.

Nhóm 3: Giá bán và thuế

US-08
Là một Admin, tôi muốn khai báo giá bán cho từng sản phẩm hoặc biến thể để hệ thống tính tiền chính xác khi khách đặt hàng.

US-09
Là một Admin, tôi muốn khai báo thuế VAT cho sản phẩm để hệ thống tính đúng giá trị thanh toán và phục vụ xuất hóa đơn.

US-10
Là một Customer, tôi muốn xem giá bán rõ ràng trên trang sản phẩm để dễ đưa ra quyết định mua hàng.

Nhóm 4: Tồn kho realtime

US-11
Là một Warehouse Staff, tôi muốn cập nhật số lượng tồn kho thực tế để website hiển thị đúng khả năng cung ứng hàng hóa.

US-12
Là một Customer, tôi muốn biết sản phẩm còn hàng hay hết hàng theo thời gian thực để tránh đặt mua sản phẩm không có sẵn.

US-13
Là một Admin, tôi muốn hệ thống tự động giảm tồn kho khi đơn hàng được thanh toán thành công để dữ liệu tồn kho luôn chính xác.

Nhóm 5: Liên kết với giỏ hàng và đơn hàng

US-14
Là một Customer, tôi muốn thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm để thuận tiện mua sắm.

US-15
Là một Customer, tôi muốn hệ thống từ chối thêm vào giỏ hàng khi sản phẩm hoặc biến thể đã hết hàng để tránh phát sinh đơn lỗi.

US-16
Là một Admin, tôi muốn dữ liệu sản phẩm được truyền chính xác sang đơn hàng để kho và kế toán xử lý đúng thông tin.

Nhóm 6: Hiển thị và tra cứu

US-17
Là một Customer, tôi muốn tìm kiếm và lọc sản phẩm theo danh mục hoặc thuộc tính để nhanh chóng tìm được sản phẩm phù hợp.

US-18
Là một Customer, tôi muốn xem thông tin chi tiết của sản phẩm gồm tên, mô tả, giá, biến thể và tình trạng tồn kho để có đủ thông tin trước khi mua. 

## 4.2. Quản lý sản phẩm
- Hệ thống cho phép Admin tạo/sửa/xóa sản phẩm
- SKU phải là duy nhất

## 4.3. Quản lý biến thể
- Hệ thống hỗ trợ nhiều biến thể
- Mỗi biến thể có SKU và tồn kho riêng

## 4.4. Tồn kho
- Cập nhật realtime
- Không cho mua khi hết hàng

## 4.5. Giá và thuế
- Hỗ trợ VAT
- Hiển thị giá rõ ràng

---

# 5. Yêu cầu phi chức năng

- Thời gian phản hồi < 1 giây
- Bảo mật phân quyền
- Hệ thống ổn định

---

# 6. Mô hình dữ liệu

## 4.1. Partner
| Tên trường       | Kiểu dữ liệu | Bắt buộc | Mô tả                                 |
| ---------------- | ------------ | -------: | ------------------------------------- |
| partner_id       | String/UUID  |       Có | Mã định danh khách hàng               |
| partner_type     | Enum         |       Có | Loại khách hàng: Guest / B2C / B2B    |
| full_name        | String       |       Có | Họ và tên khách hàng                  |
| company_name     | String       |    Không | Tên công ty nếu là khách doanh nghiệp |
| tax_code         | String       |    Không | MST nếu là công ty                    |
| email            | String       |       Có | Email liên hệ                         |
| phone            | String       |       Có | Số điện thoại                         |
| billing_address  | Text         |    Không | Địa chỉ xuất hóa đơn                  |
| shipping_address | Text         |       Có | Địa chỉ giao hàng                     |
| contact_person   | String       |    Không | Người liên hệ đại diện công ty        |
| created_at       | Datetime     |       Có | Thời điểm tạo                         |
| updated_at       | Datetime     |       Có | Thời điểm cập nhật                    |


## 4.2. Product
| Tên trường   | Kiểu dữ liệu | Bắt buộc | Mô tả                   |
| ------------ | ------------ | -------: | ----------------------- |
| product_id   | String/UUID  |       Có | Mã định danh sản phẩm   |
| product_name | String       |       Có | Tên sản phẩm            |
| sku          | String       |       Có | Mã SKU                  |
| barcode      | String       |       Có | Mã vạch                 |
| category_id  | String       |       Có | Danh mục sản phẩm       |
| description  | Text         |    Không | Mô tả sản phẩm          |
| sale_price   | Decimal      |       Có | Giá bán                 |
| vat_rate     | Decimal      |       Có | Thuế VAT (%)            |
| stock_qty    | Integer      |       Có | Số lượng tồn            |
| stock_status | Enum         |       Có | In Stock / Out of Stock |
| status       | Enum         |       Có | Active / Inactive       |
| image_url    | String       |    Không | Ảnh sản phẩm            |
| created_at   | Datetime     |       Có | Ngày tạo                |
| updated_at   | Datetime     |       Có | Ngày cập nhật           |


## 4.3. Variant
| Tên trường   | Kiểu dữ liệu | Bắt buộc | Mô tả                     |
| ------------ | ------------ | -------: | ------------------------- |
| variant_id   | String/UUID  |       Có | Mã biến thể               |
| product_id   | String/UUID  |       Có | Liên kết đến sản phẩm gốc |
| variant_name | String       |       Có | Tên biến thể              |
| color        | String       |    Không | Màu sắc                   |
| size         | String       |    Không | Kích thước                |
| sku          | String       |       Có | SKU riêng cho biến thể    |
| barcode      | String       |    Không | Barcode riêng             |
| sale_price   | Decimal      |       Có | Giá bán của biến thể      |
| vat_rate     | Decimal      |       Có | Thuế VAT                  |
| stock_qty    | Integer      |       Có | Tồn kho của biến thể      |
| stock_status | Enum         |       Có | In Stock / Out of Stock   |
| status       | Enum         |       Có | Active / Inactive         |


## 4.4. Order
| Tên trường       | Kiểu dữ liệu | Bắt buộc | Mô tả                         |
| ---------------- | ------------ | -------: | ----------------------------- |
| order_id         | String/UUID  |       Có | Mã định danh đơn hàng         |
| order_number     | String       |       Có | Số đơn hàng                   |
| partner_id       | String/UUID  |       Có | Khách hàng đặt hàng           |
| order_status     | Enum         |       Có | Draft / Confirmed / Cancelled |
| payment_status   | Enum         |       Có | Unpaid / Paid / Failed        |
| shipping_address | Text         |       Có | Địa chỉ giao hàng             |
| untaxed_amount   | Decimal      |       Có | Tiền hàng trước thuế          |
| tax_amount       | Decimal      |       Có | Tiền thuế                     |
| shipping_fee     | Decimal      |       Có | Phí giao hàng                 |
| total_amount     | Decimal      |       Có | Tổng thanh toán               |
| payment_method   | Enum         |    Không | VNPay / Momo / COD            |
| created_at       | Datetime     |       Có | Thời điểm tạo đơn             |
| updated_at       | Datetime     |       Có | Thời điểm cập nhật            |
 
## 4.5. Order line
| Tên trường    | Kiểu dữ liệu | Bắt buộc | Mô tả                      |
| ------------- | ------------ | -------: | -------------------------- |
| order_line_id | String/UUID  |       Có | Mã dòng đơn hàng           |
| order_id      | String/UUID  |       Có | Liên kết đơn hàng          |
| product_id    | String/UUID  |       Có | Sản phẩm                   |
| variant_id    | String/UUID  |    Không | Biến thể được chọn         |
| sku           | String       |       Có | SKU tại thời điểm đặt hàng |
| quantity      | Integer      |       Có | Số lượng mua               |
| unit_price    | Decimal      |       Có | Đơn giá                    |
| vat_rate      | Decimal      |       Có | Thuế VAT                   |
| line_total    | Decimal      |       Có | Thành tiền                 |


# 7. Quy tắc nghiệp vụ

- SKU phải duy nhất
- Không tồn kho âm
- Giá ≥ 0


# 8. Kết luận
PIM đảm bảo dữ liệu sản phẩm chính xác và hỗ trợ toàn bộ quy trình bán hàng.


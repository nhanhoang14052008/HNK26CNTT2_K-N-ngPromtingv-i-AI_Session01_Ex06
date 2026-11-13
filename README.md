## Phần 1: Phân tích nguyên nhân lỗi
AI thường tự động thêm lời chào hỏi và lời chúc kết luận vì được huấn luyện theo thói quen giao tiếp tự nhiên, lịch sự và thân thiện với người dùng. Khi Prompt không quy định chặt chẽ định dạng đầu ra, AI có thể tự thêm nội dung giải thích, lời chào hoặc kết luận.
Điều này khiến chuỗi trả về không còn là JSON thuần túy. Backend sử dụng JSON.parse sẽ báo lỗi vì ký tự đầu tiên là chữ "D" thay vì dấu `{`.
## Phần 2: Hoàn thiện Prompt ép cấu trúc
Bạn là hệ thống trích xuất dữ liệu bảo hành của TechShop. Hãy chuyển biên bản tiếp nhận bảo hành thành JSON gồm 3 trường: customer_name (tên khách hàng), device (tên thiết bị), issue (mô tả lỗi sản phẩm).
**Negative Constraints:**
Không thêm lời chào, lời cảm ơn, giải thích, nhận xét hoặc lời chúc. Không sử dụng Markdown, không tự suy đoán hoặc bịa đặt thông tin. Nếu thiếu dữ liệu, trả về chuỗi rỗng.
**Định dạng đầu ra bắt buộc:** 
Chỉ trả về chuỗi JSON thuần túy, không dùng Markdown block, không giải thích, bắt đầu bằng `{` và kết thúc bằng `}`.
**Dữ liệu đầu vào:**
<biên_bản>[NỘI_DUNG_BIÊN_BẢN_BẢO_HÀNH]</biên_bản>
**Cấu trúc JSON:**
{
  "customer_name": "",
  "device": "",
  "issue": ""
}

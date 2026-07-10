# 📝 Smart List To Do v6 — Ứng dụng Quản lý Công việc & Xuất Bản thảo MS Word Chuẩn Văn phòng

Ứng dụng **Smart List To Do v6** là một giải pháp quản lý công việc cá nhân gọn nhẹ, hoạt động độc lập ngay trên trình duyệt web thông qua một file HTML/JS thuần túy 🛠️. Dự án này được thiết kế tối ưu hóa nhằm đáp ứng các tiêu chuẩn khắt khe về lưu trữ dữ liệu tự động và xuất bản tài liệu văn phòng chuyên nghiệp.

---

## 🚀 Tính năng nổi bật (Key Features)

* 🧠 **Tự động lưu (Auto-Save):** Mọi ký tự bạn gõ, mọi ô tích chọn đều được lưu lại ngay lập tức. Tắt trình duyệt hoặc bấm `F5` tải lại trang, dữ liệu vẫn nguyên vẹn 100%.
* 📋 **Đa dạng phân loại mục tiêu:** Hệ thống tích hợp 3 dãy tickbox phân loại chuyên sâu gồm:
    * ⏹ **SHORT:** Đánh dấu các công việc ngắn hạn cần giải quyết nhanh.
    * ⏹ **LONG:** Đánh dấu các kế hoạch dài hạn, cần nhiều thời gian.
    * ⏹ **Hoàn thành:** Cột trạng thái xử lý cuối cùng (được dời ra sau cùng để tối ưu quy trình làm việc).
* ➕ **Quản lý hàng linh hoạt:** Cho phép tự do thêm hàng mới hoặc xóa bỏ các hàng thừa, hàng lỗi một cách mượt mà theo thời gian thực.
* 🖨 **Xuất file Word chuẩn hóa văn phòng:** Tự động chuyển đổi toàn bộ danh sách thành một bảng biểu Microsoft Word rất thanh lịch, ép cứng định dạng **Times New Roman cỡ chữ 18**, có kẻ khung viền ngay ngắn và đổ nền xám nhạt cho hàng tiêu đề.

---

## 🛠 Cơ chế Xuất file Word Độc lập (Native Data Export)

Khác biệt hoàn toàn với các giải pháp thông thường phụ thuộc vào thư viện bên ngoài (như `docx.js` hay `FileSaver.js` dễ bị lỗi tải đường dẫn CDN hoặc bị trình duyệt chặn tải file), phiên bản V6 này sử dụng phương pháp **Native Data Export**:
* ⚡ Trình duyệt tự biên dịch cây thư mục DOM trực tiếp sang định dạng tệp chuẩn `application/msword` giúp kích hoạt lệnh tải xuống ngay lập tức.
* 🎛 **Bộ lọc thông minh (Smart Filter):** Khi bấm xuất file, hệ thống tự động loại bỏ các thành phần rườm rà trên giao diện web (như nút *Xóa*, nút *Thêm hàng*, cột *Thao tác*).
* 🔄 **Tự động đảo cột:** Trên file Word, các cột sẽ được sắp xếp lại theo chuẩn báo cáo khoa học từ trái sang phải: **Nội dung công việc ──> SHORT ──> LONG ──> Hoàn thành**. Các ô check-box được chuyển đổi thành ký hiệu ô vuông chuyên nghiệp: `☐` (chưa tích) hoặc `☒` (đã tích).

---

## 🧠 Cơ chế Tự động lưu thông minh (LocalStorage)

Ứng dụng sử dụng công nghệ **Web Storage (LocalStorage)** tích hợp sẵn trong nhân của mọi trình duyệt web để lưu trữ dữ liệu cục bộ:
1.  **Quy trình:** Khi bạn tương tác (gõ chữ/tích chọn), hàm `saveData()` sẽ gom dữ liệu, nén thành chuỗi `JSON` rồi nạp vào ổ cứng máy tính của bạn thông qua một "ngăn tủ ký ức" mang tên mã `todo_list_data`. Khi bạn vừa mở web, hàm `loadData()` sẽ tự động giải nén chuỗi này và khôi phục lại giao diện y hệt như cũ.
2.  **Đổi mã nguồn không mất dữ liệu:** Trình duyệt quản lý bộ nhớ LocalStorage theo đường dẫn file (URL) chứ không dựa vào nội dung code. Vì vậy, khi bạn cập nhật mã nguồn (add code mới) vào file cũ, **miễn là giữ nguyên tên file và vị trí thư mục**, toàn bộ dữ liệu bạn đã nhập trước đó sẽ được kế thừa hoàn hảo mà không sợ bị trống rỗng.
3.  **Bảo mật tuyệt đối:** Dữ liệu nằm hoàn toàn trên máy tính cá nhân của bạn, không đẩy lên bất kỳ máy chủ nào qua Internet.

---

## 💻 Hướng dẫn Cài đặt & Sử dụng (Setup & Usage)

1.  **Lưu file:** Sao chép toàn bộ mã nguồn HTML của dự án và lưu lại với tên file là `todo.html` (đảm bảo đuôi file là `.html` chứ không phải `.txt`).
2.  **Khởi chạy:** Nhấp đúp chuột trực tiếp vào file `todo.html` để mở bằng bất kỳ trình duyệt nào (Chrome, Edge, Cốc Cốc, Safari,...).
3.  **Nhập liệu:** Gõ nội dung, thêm hàng và tích chọn các mục SHORT/LONG/Hoàn thành phù hợp với công việc của bạn.
4.  **In ấn:** Bấm nút `In ra file Word (.docx)` để nhận ngay file văn bản `.doc` sạch đẹp, sẵn sàng mang đi in ấn hoặc gửi báo cáo công việc.

---
⭐ *Chúc bạn quản lý và tối ưu hóa công việc thật hiệu quả với **Smart List To Do v6**!*
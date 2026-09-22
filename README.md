📋 Update Log

🚀 v2.0 — BIG UPDATE

22/09/2026

«Major update — nâng Addon Lite Optimizer từ công cụ tối ưu hóa heuristic cơ bản thành hệ thống phân tích → đề xuất → lựa chọn → tối ưu → kiểm tra → báo cáo.»

🧠 Advanced Analysis

- Thêm hệ thống Dependency Graph.
- Phân tích quan hệ và reference giữa các file.
- Cải thiện Reference Scanner.
- Phân tích sâu hơn JavaScript, ".mcfunction", JSON và các file text liên quan.
- Phát hiện dynamic JavaScript và đánh dấu REVIEW / KEEP thay vì tự ý xóa.
- Bổ sung phân tích asset có khả năng không được sử dụng.

🔍 Unused Asset Scanner

- Quét asset có khả năng không còn được reference.
- Hỗ trợ phân tích nhiều loại resource/path phổ biến của Bedrock.
- Không tự động xóa asset chỉ vì scanner không tìm thấy reference.
- Trường hợp không đủ chắc chắn được đưa vào REVIEW.

⚙️ Optimization Presets

Thêm 3 chế độ:

- 🛡️ Safe — ưu tiên tối đa khả năng giữ nguyên chức năng.
- ⚖️ Balanced — cân bằng giữa độ an toàn và mức tối ưu.
- ⚡ Aggressive — đưa ra nhiều đề xuất tối ưu hơn để người dùng tự kiểm tra.

🎯 Selective Optimization

- Có thể lựa chọn từng đề xuất trước khi áp dụng.
- Không bắt buộc áp dụng toàn bộ đề xuất.
- Phân biệt rõ:
  - SAFE — có thể áp dụng tự động.
  - REVIEW — cần người dùng kiểm tra.
  - KEEP — giữ nguyên.

📊 Original ↔ Lite Diff

- So sánh addon gốc với bản Lite.
- Hiển thị file được:
  - Tối ưu
  - Xóa
  - Giữ nguyên
  - Thêm
- Hiển thị dung lượng trước và sau.
- Tính toán mức thay đổi dung lượng archive.

🔄 Backup & Rollback

- Giữ bản Original trong phiên xử lý.
- Cho phép quay lại trạng thái gốc trước khi xuất bản Lite.
- Không ghi đè trực tiếp lên addon gốc.

🛡️ Integrity Check

Sau khi tạo bản Lite, hệ thống kiểm tra lại output:

- Archive có thể mở lại.
- Path trong archive không vi phạm quy tắc an toàn.
- JSON đã chỉnh sửa có thể parse.
- Manifest vẫn tồn tại và đọc được.
- Nested ".mcpack" được kiểm tra lại.
- Không cho tải output rỗng hoặc output lỗi.

📦 Nested Pack Processing

- Cải thiện xử lý ".mcpack" nằm bên trong ".mcaddon" / ".zip".
- Phân tích từng nested pack riêng.
- Rebuild nested pack sau khi áp dụng thay đổi.
- Hạn chế rebuild khi không cần thiết.
- Giảm việc giữ nhiều archive lớn trong RAM cùng lúc.

📑 Optimization Report

- Thêm báo cáo quá trình tối ưu.
- Thống kê số file phân tích.
- Thống kê file tối ưu/xóa/giữ.
- Thống kê dung lượng trước/sau.
- Hỗ trợ xuất báo cáo để kiểm tra lại kết quả.

📱 Mobile & Low-RAM Improvements

- Tiếp tục tối ưu cho thiết bị Android cấu hình thấp.
- Giới hạn kích thước file được xử lý trực tiếp.
- Giảm dữ liệu tạm được giữ trong RAM.
- Chia quá trình xử lý thành nhiều bước để hạn chế treo UI.
- Giới hạn số lượng DOM log/proposal được hiển thị cùng lúc.

🔒 Safety Improvements

- Giữ nguyên ".mcstructure".
- Không tự re-encode PNG/JPG/JPEG.
- Không tự thay đổi "min_engine_version".
- Không tự chuyển schema/API theo phiên bản Minecraft mục tiêu.
- Không xóa asset chỉ vì không tìm thấy reference.
- Dynamic JavaScript được giữ hoặc đưa vào REVIEW.
- Duplicate asset không tự động bị xóa nếu chưa đủ chắc chắn.
- Tiếp tục bảo vệ khỏi archive path traversal.
- Nếu không chắc chắn → KEEP.

🧩 UI / Workflow

Workflow v2.0:

Chọn addon → Phân tích → Dependency/Asset Scan → Đề xuất → Chọn thay đổi → Apply → Integrity Check → Diff → Report → Download

📈 Codebase

- v1.2: khoảng 2.5K dòng
- v2.0: khoảng 4.5K dòng
- Major update với nhiều hệ thống phân tích và kiểm tra mới.

---

🛠️ v1.2

22/09/2026

- Thêm phân tích JavaScript.
- Thêm phân tích ".mcfunction".
- Thêm Reference Scanner.
- Thêm trạng thái SAFE / REVIEW / KEEP.
- Phát hiện function/variable JavaScript có khả năng không được sử dụng.
- Tối ưu comment/whitespace an toàn.
- Tối ưu comment/blank line trong ".mcfunction".
- Phát hiện command ".mcfunction" trùng liên tiếp → REVIEW.
- Phát hiện JavaScript dynamic behavior → KEEP.
- Hỗ trợ phân tích nested ".mcpack".
- Kiểm tra "min_engine_version" → REVIEW.
- Giữ nguyên ".mcstructure" và texture.
- Thêm giới hạn RAM/kích thước file.
- Thêm Cancel/Abort.
- Kiểm tra archive sau khi xuất.
- Cải thiện thống kê phân tích.
- Đổi nút AI thành “Phân tích & tạo bản Lite” để phản ánh đúng cơ chế xử lý local.

---

🧱 v1.1

- Cải thiện giao diện.
- Cải thiện xử lý archive.
- Bổ sung kiểm tra an toàn cơ bản.
- Cải thiện khả năng chạy trên thiết bị di động.

---

🎉 v1.0

- Phiên bản đầu tiên.
- Hỗ trợ ".mcaddon", ".mcpack", ".zip".
- Tối ưu các file an toàn.
- Xóa một số file rác phổ biến.
- Xuất addon Lite sau khi xử lý.

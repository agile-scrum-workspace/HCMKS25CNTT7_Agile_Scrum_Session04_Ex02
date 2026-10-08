# BÀI LÀM: VIẾT USER STORY, ACCEPTANCE CRITERIA VÀ THEO DÕI TRÊN TRELLO (ỨNG DỤNG RIKKEICARE)

---

## Bước 1. Viết User Story cho R5

### Nội dung User Story
> **Là một** quản lý phòng khám đối tác,  
> **tôi muốn** tự cập nhật giá các gói khám của phòng khám mình trên hệ thống,  
> **để** thông tin giá luôn chính xác, kịp thời và không phải phụ thuộc vào việc gửi email nhờ admin RikkeiCare hỗ trợ.

### Giải thích lựa chọn vai trò
* **Người thụ hưởng giá trị trực tiếp:** Quản lý phòng khám là người chủ động nắm bắt biến động giá dịch vụ và có nhu cầu cập nhật tức thì. Admin RikkeiCare chỉ là giải pháp tình thế (nút thắt cổ chai) trong quy trình thủ công hiện tại.
* **Mục tiêu sản phẩm:** Tính năng này hướng tới việc trao quyền tự phục vụ (*self-service*) cho đối tác phòng khám, giúp cắt giảm gánh nặng vận hành trung gian của đội ngũ admin RikkeiCare. Do đó, vai trò chuẩn xác phải là **Quản lý phòng khám**.

---

## Bước 2. Viết phần "Then" cho 2 Acceptance Criteria (AC) của R5

* **AC 1 (Thành công):**  
  * **Given:** Quản lý phòng khám đã đăng nhập vào tài khoản đối tác hợp lệ,  
  * **When:** Nhập giá mới hợp lệ (số nguyên dương $\ge 0$) cho một gói khám rồi nhấn "Lưu",  
  * **Then:** Hệ thống hiển thị thông báo "Cập nhật giá thành công", lưu giá mới vào cơ sở dữ liệu và hiển thị giá mới tức thì trên trang chi tiết gói khám mà bệnh nhân nhìn thấy.

* **AC 2 (Thất bại / Validation):**  
  * **Given:** Quản lý để trống ô giá (hoặc nhập giá trị không hợp lệ),  
  * **When:** Nhấn "Lưu",  
  * **Then:** Hệ thống không lưu thay đổi, viền đỏ ô nhập giá và hiển thị thông báo lỗi cụ thể: *"Vui lòng nhập giá hợp lệ trước khi lưu"* ngay dưới ô nhập liệu.

---

## Bước 3. Kiểm tra tính sẵn sàng của thẻ R5 (Definition of Ready)

**Kết luận:** **CHƯA ĐƯỢC** kéo thẻ R5 sang cột "Ready for Sprint".

**Lý do:**  
Đối chiếu với 4 tiêu chí trong Definition of Ready (DoR) của nhóm:
1. Có User Story đủ 3 vế: **Đạt** (đã viết xong ở Bước 1).
2. Có tiêu chí nghiệm thu (AC): **Đạt** (đã có 2 kịch bản Given-When-Then ở Bước 2).
3. Đã được ước lượng (Estimated): **CHƯA ĐẠT**. Đội ngũ phát triển (Dev & Tester) chưa thực hiện phiên ước lượng điểm (Story Points / Planning Poker) cho thẻ này.
4. Đủ nhỏ để làm xong trong 1 Sprint: **CHƯA XÁC NHẬN ĐƯỢC**. Khi chưa trải qua bước ước lượng độ phức tạp cùng nhóm kỹ thuật, PO không thể tự ý khẳng định thẻ đủ nhỏ để hoàn thành trong Sprint.

Vì vi phạm tiêu chí số 3 và số 4, thẻ R5 phải tiếp tục ở lại cột **Product Backlog** cho đến khi hoàn thành buổi Backlog Refinement.

---

## Bước 4. Hoàn thiện thẻ R5 trên Trello

### Thông tin chi tiết trên thẻ Trello

| Trường thông tin | Giá trị thiết lập |
| :--- | :--- |
| **Tên thẻ (Card Title)** | `[Feature] R5 - Tự cập nhật giá các gói khám (Quản lý phòng khám)` |
| **Nhãn (Label)** | **Xanh dương** (Feature - tính năng mới) |
| **Người phụ trách (Members)** | 01 Backend Dev, 01 Frontend Dev, 01 Tester (ví dụ: `@dev_nam`, `@qa_lan`) |
| **Hạn hoàn thành (Due Date)** | Ngày làm việc thứ 8 của Sprint (để chừa 2 ngày cho test hồi quy và release) |
| **Checklist công việc** | 1. `[FE]` Dựng UI ô nhập giá, nút Lưu và trạng thái validation báo lỗi<br>2. `[BE]` Viết API cập nhật giá kèm logic phân quyền đúng phòng khám<br>3. `[QA]` Test chức năng theo AC 1, AC 2 và kiểm tra hiển thị phía bệnh nhân |

### Vị trí đặt thẻ
* Theo nguyên tắc trực quan của bảng Kanban/Scrum trên Trello: độ ưu tiên giảm dần từ trên xuống dưới.
* Nếu R5 là việc có **độ ưu tiên cao nhất**, thẻ này phải được đặt ở **vị trí trên cùng (top)** của cột **Sprint Backlog**.

---

## Bước 5. Đọc và phân tích Burndown Chart

### a) Đánh giá tiến độ tại Ngày 6

* **Tiến độ lý tưởng:**
  * Giảm đều 3 point/ngày.
  * Point lý tưởng còn lại tại Ngày 6: $30 - (6 \times 3) = 12 \text{ point}$.
* **Tiến độ thực tế:**
  * Point thực tế còn lại tại Ngày 6: **20 point**.
* **Đánh giá:**
  * Nhóm đang **chậm tiến độ** so với kế hoạch ban đầu.
  * Mức độ chênh lệch: $20 - 12 = 8 \text{ point}$ (tương đương khối lượng công việc trễ gần 3 ngày làm việc).

---

### b) Xử lý đề xuất "xong 80%" của thẻ R5

* **Trả lời:** **TUYỆT ĐỐI KHÔNG NÊN** trừ 3 point (hoặc $80\% \times 3 = 2.4 \text{ point}$) khỏi biểu đồ.
* **Lý do:**
  1. **Nguyên tắc "Nhị phân" trong Scrum (All or Nothing):** Trong Agile/Scrum, một hạng mục chỉ có 2 trạng thái: **Chưa xong (0%)** hoặc **Xong hoàn toàn (100%)** dựa theo Definition of Done (DoD). Không có khái niệm "hoàn thành một phần" trên biểu đồ Burndown.
  2. **Tránh ảo tưởng tiến độ:** "Xong 80%" phần code nhưng việc kiểm thử, sửa lỗi (bug fix) hay triển khai có thể chiếm tới 50% thời gian còn lại. Nếu ghi nhận giảm point trước, Burndown Chart sẽ phản ánh sai thực tế năng lực và rủi ro của nhóm.
  3. **Quy tắc ghi nhận Burndown:** Điểm point chỉ được trừ khi thẻ đã được Tester nghiệm thu đạt toàn bộ AC và kéo hẳn sang cột **Done**.
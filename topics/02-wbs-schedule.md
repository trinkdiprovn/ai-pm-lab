# Topic 02: WBS & Details Schedule (3-Level Breakdown)

## 1. Đối tượng vấn đề (Problem Object)
- **Tên đối tượng:** Work Breakdown Structure (WBS) & Detailed Schedule.
- **Mô tả cụ thể:** Phân rã yêu cầu từ tài liệu thô (RD/SRS) thành danh sách task chi tiết 3 cấp (Level 1: Module/Epic -> Level 2: Feature/User Story -> Level 3: Task/Sub-task). Task nhỏ nhất đảm bảo <= 16 man-hours (2 man-days).

## 2. Mục tiêu áp dụng AI (Goal)
- Tự động hóa việc liệt kê danh sách task từ tài liệu đặc tả (giảm 50-80% thời gian soạn thảo ban đầu).
- Đảm bảo tính nhất quán (Consistency) trong cấu trúc WBS giữa các dự án.
- Tăng độ chính xác của ước lượng dựa trên dữ liệu lịch sử thay vì chỉ dựa vào cảm tính của PM.

## 3. Issue gây ra vấn đề (Root Cause)
- **Missing Tasks:** PM thường bỏ sót các task phụ trợ (Review, Testcase creation, Environment setup).
- **Inconsistent Estimation:** Cùng một task nhưng các PM khác nhau ước lượng khác nhau.
- **Language Barrier:** Đặc tả tiếng Nhật dài dòng khiến việc bóc tách task thủ công dễ nhầm lẫn hoặc thiếu sót.

## 4. AI Strategy & Workflow
- **Context/Prompt:** 
    - AI cần được nạp: (1) RD/SRS (PDF/Excel), (2) Mẫu WBS mẫu (Template), (3) Dữ liệu lịch sử ước lượng (Historical Estimation).
    - Prompt: "Dựa trên tài liệu đặc tả này, hãy phân rã thành WBS 3 cấp. Sử dụng dữ liệu lịch sử để ước lượng Man-hours cho một Middle Dev. Hãy liệt kê đủ các task Review (Internal/Client) và Unit Test cho từng Feature."
- **Workflow:** 
    1. AI đọc RD và so sánh với WBS mẫu để sinh ra danh sách Task thô (Draft WBS).
    2. PM review các Task Level 3 và điều chỉnh con số Man-hours dựa trên độ khó thực tế.
    3. AI tự động tính toán tổng tiến độ (Sum up) và xuất ra file Excel (Gantt) hoặc import vào Backlog.

## 5. Scope of Work (AI Boundary)
- **AI ĐƯỢC LÀM:** 
    - Đọc hiểu ngôn ngữ (Tiếng Nhật/Anh) và tóm tắt thành task hành động.
    - Phân loại task vào đúng Module/Level.
    - Gợi ý số giờ dựa trên mẫu có sẵn.
- **AI KHÔNG ĐƯỢC LÀM:** 
    - Xác định các rủi ro tiềm ẩn về mặt kỹ thuật (Ví dụ: Thư viện này không tương thích với OS cũ).
    - Cam kết về tiến độ (Final Deadline).

## 6. Rủi ro & Issue khi dùng AI (Risks)
- **Over-optimism:** AI thường ước lượng thiếu "thời gian chờ" (Wait time) và thời gian sửa lỗi (Bug fix).
- **Structure Rigidity:** AI có thể máy móc áp dụng cấu trúc cũ cho dự án mới có tính chất khác biệt.

## 7. PM Review Checklist (Output)
- [ ] Level 3 task đã nhỏ hơn 16 man-hours chưa?
- [ ] Đã có task cho việc chuẩn bị Mock data / Environment setup chưa?
- [ ] Thời gian cho việc xử lý Q&A với khách hàng đã được tính chưa? (Thường chiếm 10-20%).
- [ ] Các task Review (Code review, Design review) đã được gán cho đúng Role chưa?

## 8. Phương án thay thế (Proposed Alternatives)
- Tổ chức buổi "Planning Poker" với toàn bộ team để estimate (Manual & Collaborative).
- Sử dụng các công cụ Auto-scheduling truyền thống trong MS Project.

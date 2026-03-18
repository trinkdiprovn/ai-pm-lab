# Topic 01: Resource Planning (Project-based)

## 1. Đối tượng vấn đề (Problem Object)
- **Tên đối tượng:** Project Resource Allocation Plan (Bản kế hoạch phân bổ nhân sự dự án).
- **Mô tả cụ thể:** Xác định đúng Role, đúng Skill và đúng Thời điểm để yêu cầu (request) nhân sự cho dự án mới hoặc khi có thay đổi phạm vi (Change Request).

## 2. Mục tiêu áp dụng AI (Goal)
- Giảm 70% thời gian lập bảng phân bổ nhân sự (Resource Matrix).
- Tối ưu hóa việc sử dụng nhân sự (Utilization), tránh tình trạng người quá tải, người ngồi chơi.
- Tự động cảnh báo các "điểm nghẽn" (Bottleneck) khi một nhân sự quan trọng bị gán quá nhiều task.

## 3. Issue gây ra vấn đề (Root Cause)
- **Fragmentation:** Task quá nhỏ và lẻ tẻ khiến PM khó bao quát ai đang làm gì.
- **Data Silos:** Thông tin về Skill và Availability của nhân sự không được cập nhật tập trung.
- **Manual Checking:** PM phải đối chiếu thủ công giữa WBS (yêu cầu) và Staff List (khả năng).

## 4. AI Strategy & Workflow
- **Context/Prompt:** 
    - AI cần được nạp: (1) Danh sách Task/Skill từ WBS, (2) Danh sách Nhân sự kèm Skill/Availability.
    - Prompt yêu cầu AI: "Hãy phân bổ nhân sự vào các task sao cho tổng thời gian dự án ngắn nhất, đảm bảo không có ai làm quá 8h/ngày và ưu tiên đúng Skill chuyên môn."
- **Workflow:** 
    1. PM nạp WBS & Resource Pool (dạng Markdown/CSV) cho AI.
    2. AI đề xuất 2-3 phương án phân bổ (Draft Plan).
    3. PM phản biện lại các phương án dựa trên "yếu tố con người" (Trust, Chemistry).
    4. AI hoàn thiện bản cuối và xuất file Resource Plan.

## 5. Scope of Work (AI Boundary)
- **AI ĐƯỢC LÀM:** 
    - Tính toán toán học về số lượng Man-days và Thời gian.
    - Đối chiếu Skill-set cơ bản giữa Task và Nhân sự.
    - Phát hiện xung đột lịch trình (Conflict scheduling).
- **AI KHÔNG ĐƯỢC LÀM:** 
    - Quyết định cuối cùng về việc chọn ai (PM phải chịu trách nhiệm về nhân sự).
    - Đánh giá thái độ làm việc hoặc sự phù hợp về văn hóa team.

## 6. Rủi ro & Issue khi dùng AI (Risks)
- **Skill Mismatch:** AI có thể gán nhầm người nếu dữ liệu Skill-set trong hệ thống bị cũ.
- **Hallucination:** AI có thể tự "chế" ra một nhân sự không tồn tại hoặc quên mất ngày nghỉ của một người.

## 7. PM Review Checklist (Output)
- [ ] Nhân sự Senior đã được gán vào các Task rủi ro cao chưa?
- [ ] Có tình trạng "Single Point of Failure" (1 người nắm quá nhiều task quan trọng) không?
- [ ] Thời gian đệm (Buffer) cho việc bàn giao (Handover) đã được tính chưa?
- [ ] AI có bỏ sót các Milestone quan trọng của dự án không?

## 8. Phương án thay thế (Proposed Alternatives)
- Sử dụng các phần mềm quản lý tài nguyên chuyên dụng (như Jira Resource Management, ClickUp).
- Họp Resource Allocation định kỳ giữa các PM để "đấu giá" nhân sự (Manual approach).

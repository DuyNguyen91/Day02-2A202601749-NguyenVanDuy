## Scan rộng

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tốn thời gian | QA phải đọc PRD rồi tự viết Test Case thủ công | QA Engineer | 1–2 giờ/feature |
| 2 | Lặp lại | Developer phải viết Release Note sau mỗi Sprint | Developer, PM | Lặp lại mỗi Sprint |
| 3 | AI có thể tốt hơn | Product Backlog chứa nhiều User Story bị trùng | Product Owner | Backlog ngày càng khó quản lý |
| 4 | Pain từ người khác | CSKH phải đọc ticket dài trước khi trả lời khách | Customer Support | 5–10 phút/ticket |
| 5 | Tốn thời gian | Recruiter lọc hàng trăm CV bằng mắt | HR | Hàng giờ mỗi đợt tuyển |
| 6 | AI có thể tốt hơn | Team khó dự đoán Sprint có bị trễ hay không | Scrum Master | Thường phát hiện quá muộn |
| 7 | Lặp lại | Finance nhập dữ liệu hóa đơn từ PDF vào Excel | Kế toán | Hàng trăm hóa đơn/tháng |
| 8 | Pain từ người khác | Sales phải viết proposal gần giống nhau cho từng khách | Sales | 30–60 phút/proposal |
| 9 | Tốn thời gian | Dev đọc log để tìm nguyên nhân lỗi sau khi deploy | Backend Engineer | 30 phút–2 giờ/sự cố |
| 10 | AI có thể tốt hơn | Manager khó phát hiện nhân viên có nguy cơ nghỉ việc | HRBP, Manager | Chỉ biết khi nhân viên xin nghỉ |

---

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | QA tạo Test Case từ PRD | Workflow rõ, AI rất phù hợp, tiết kiệm nhiều thời gian | Chất lượng test case vẫn cần QA review |
| 2 | Recruiter sàng lọc CV | ROI cao, dữ liệu đầu vào rõ | Cần JD được chuẩn hóa |
| 3 | AI phân tích Log | Giảm MTTR, pain phổ biến ở team kỹ thuật | Phụ thuộc chất lượng log |

---

## Problem Card #1 — AI tạo Test Case từ PRD

**Problem 1 câu:**  
QA mất khoảng 1–2 giờ để đọc PRD và viết test case thủ công cho mỗi feature, khiến tiến độ kiểm thử bị chậm khi Sprint có nhiều yêu cầu mới.

**Actor:**  
QA Engineer chịu trách nhiệm chuẩn bị test case trước khi bắt đầu kiểm thử.

**Thời điểm / bối cảnh:**  
Sau khi Product Manager hoàn thành PRD và trước khi Developer bàn giao tính năng.

**Current workflow:**

```text
1. Mở PRD
2. Đọc toàn bộ yêu cầu
3. Xác định các luồng chính
4. Liệt kê test scenario
5. Viết test case
6. Review với PM
7. Import vào Test Management
```

**Bottleneck:**  
Bước 4–5 mất nhiều thời gian nhất vì QA phải tự suy nghĩ toàn bộ test scenario.

**Impact:**  
Một feature mất khoảng 1–2 giờ để chuẩn bị test case. Khi Sprint có nhiều feature, QA trở thành bottleneck.

**Success metric:**  
Giảm thời gian viết test case xuống dưới 30 phút nhưng vẫn đảm bảo coverage.

**Non-AI alternative:**  
Sử dụng template test case chuẩn.

**AI hypothesis:**  
AI đọc PRD, tự sinh test scenario và test case để QA review trước khi import.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 90 phút

[1 Đọc PRD: 20']
→ [2 Phân tích yêu cầu: 15']
→ [3 Viết scenario: 20']
→ [4 Viết test case: 25'] <-- bottleneck
→ [5 Review: 10']
```

### Draft future workflow

```text
FUTURE STATE — 25 phút

[1 AI đọc PRD: 1']
→ [2 AI sinh test case: 2']
→ [3 QA review: 20'] <-- human boundary
→ [4 Import: 2']

Fallback: AI sinh thiếu → QA bổ sung thủ công.
```

---

## Problem Card #2 — AI sàng lọc CV theo Job Description

**Problem 1 câu:**  
Recruiter mất nhiều giờ để đọc và sàng lọc hàng trăm CV bằng tay trước khi lựa chọn ứng viên phù hợp để phỏng vấn.

**Actor:**  
Recruiter chịu trách nhiệm sàng lọc CV và lập danh sách ứng viên phù hợp cho Hiring Manager.

**Thời điểm / bối cảnh:**  
Mỗi khi mở một đợt tuyển dụng mới hoặc nhận số lượng lớn CV từ các nền tảng tuyển dụng.

**Current workflow:**

```text
1. Nhận CV từ các nguồn tuyển dụng
2. Mở từng CV
3. Đọc kinh nghiệm và kỹ năng
4. So sánh với Job Description
5. Đánh giá mức độ phù hợp
6. Lập shortlist
7. Gửi Hiring Manager
```

**Bottleneck:**  
Bước 3–5 tốn nhiều thời gian nhất vì Recruiter phải đọc và đánh giá từng CV thủ công.

**Impact:**  
Một đợt tuyển có thể mất nhiều giờ chỉ để sàng lọc CV. Việc đánh giá giữa các Recruiter cũng thiếu tính nhất quán.

**Success metric:**  
Giảm thời gian sàng lọc từ nhiều giờ xuống dưới 30 phút cho mỗi đợt tuyển mà vẫn giữ chất lượng shortlist.

**Non-AI alternative:**  
Sử dụng checklist hoặc keyword filter trên hệ thống ATS.

**AI hypothesis:**  
AI đọc CV, so sánh với Job Description, chấm điểm mức độ phù hợp và giải thích lý do xếp hạng để Recruiter review trước khi gửi Hiring Manager.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 180 phút

[1 Nhận CV: 10']
→ [2 Đọc từng CV: 90']
→ [3 So sánh JD: 45'] <-- bottleneck
→ [4 Lập shortlist: 25']
→ [5 Gửi Hiring Manager: 10']
```

### Draft future workflow

```text
FUTURE STATE — 25 phút

[1 AI đọc toàn bộ CV: 3']
→ [2 AI so khớp JD: 2']
→ [3 Recruiter review ranking: 15'] <-- human boundary
→ [4 Gửi shortlist: 5']

Fallback: AI đánh giá chưa chính xác → Recruiter đọc lại CV.
```

---

## Problem Card #3 — AI phân tích Log và gợi ý nguyên nhân lỗi

**Problem 1 câu:**  
Developer mất nhiều thời gian đọc log từ nhiều hệ thống để xác định nguyên nhân gây lỗi sau khi triển khai.

**Actor:**  
Backend Engineer hoặc DevOps Engineer chịu trách nhiệm xử lý sự cố sau khi hệ thống phát sinh lỗi.

**Thời điểm / bối cảnh:**  
Sau mỗi lần deploy hoặc khi hệ thống phát sinh Incident.

**Current workflow:**

```text
1. Nhận cảnh báo từ Monitoring
2. Mở Dashboard Log
3. Tìm log liên quan
4. Đọc Error Stack
5. So sánh với lần deploy gần nhất
6. Xác định nguyên nhân
7. Đề xuất cách khắc phục
```

**Bottleneck:**  
Bước 3–5 mất nhiều thời gian vì log phân tán ở nhiều nguồn và khó xác định đâu là nguyên nhân chính.

**Impact:**  
Một Incident có thể mất từ 30 phút đến hơn 2 giờ để xác định root cause, làm tăng thời gian downtime của hệ thống.

**Success metric:**  
Giảm thời gian xác định nguyên nhân xuống dưới 10 phút và giảm MTTR của hệ thống.

**Non-AI alternative:**  
Viết dashboard và alert chi tiết hơn trên Grafana hoặc Kibana.

**AI hypothesis:**  
AI tổng hợp log từ nhiều nguồn, xác định root cause, giải thích nguyên nhân và đề xuất hướng xử lý để Developer xác nhận.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 70 phút

[1 Alert: 5']
→ [2 Mở Dashboard: 5']
→ [3 Tìm log: 20']
→ [4 Phân tích stack trace: 25'] <-- bottleneck
→ [5 Root cause + Fix: 15']
```

### Draft future workflow

```text
FUTURE STATE — 12 phút

[1 AI tổng hợp log: 2']
→ [2 AI phân tích nguyên nhân: 2']
→ [3 Developer xác nhận: 6'] <-- human boundary
→ [4 Triển khai fix: 2']

Fallback: AI phân tích sai → Developer điều tra thủ công.
```
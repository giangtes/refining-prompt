# Worked examples

## Example 1: full brief (a whole unit, with a plan step and print-ready PDFs)

### Draft from the user

> làm cho tôi syllabus unit 3 lớp 7, dùng skill lập kế hoạch rồi mới làm

### Questions asked (one round)

1. What will you do with the result? → Options: approve a plan only / print
   for teachers this week / feed an automated pipeline. Answer: print for teachers.
2. Which course and level? → Grade 7 core course or Grade 7 advanced course.
   Answer: Grade 7 core course.
3. Where should the run stop for you? → after the plan / after the draft PDF /
   only at the end. Answer: after the plan.

### Refined prompt returned

```text
Soạn syllabus Unit 3 cho khóa tiếng Anh lớp 7 (chương trình chính) trong repo
course-materials. Bản này để giáo viên in và dạy trong tuần tới.

Bối cảnh:
- Luật repo nằm trong AGENTS.md; nguồn sách và band từ vựng theo
  config/courses.yaml và decisions.md. Lời tôi trong phiên này thắng mọi file.

Dùng các skill: skill lập kế hoạch trước, skill triển khai sau khi tôi duyệt kế hoạch.

Xong nghĩa là:
- Mỗi mục từ vựng, ngữ pháp, bài đọc kèm sách + unit + trang.
- Band khớp config/courses.yaml cho khóa lớp 7; không tự ước lượng CEFR.
- Đủ 5 buổi, nhãn T1…T5, mỗi buổi có đủ phiếu bài tập, tài liệu lý thuyết và bài về nhà.
- Bộ test của repo chạy xanh.

Tự kiểm:
- Render PDF và đọc từng trang trước khi gửi tôi.
- Mở từng trang sách được trích và đối chiếu với nội dung đã soạn.

Tránh:
- Đổi tên hoặc trật tự topic đã duyệt.
- Đáp án xuất hiện ngoài phần đáp án.
- Nguồn không có trong danh sách sách đã duyệt.

Chỉ dừng lại hỏi tôi khi kế hoạch đã xong, hoặc khi một cuốn sách tôi gửi không
có nội dung dùng được. Ngoài ra cứ làm tiếp và ghi trạng thái trong cùng tin nhắn
với bước tiếp theo.

Giữ checklist trong thư mục kế hoạch và đánh dấu từng mục khi xong.

Kết thúc bằng ba mục: Vướng ở tôi, Đã thay đổi, Phát hiện.
```

Changes made:
- Added the purpose (teachers print it next week) and the course.
- Turned "làm syllabus" into four checkable done conditions from the repo rules, plus
  two self-checks the model runs before sending.
- Added one stopping point after the plan, as the user chose.
- Wrote every heading in Vietnamese to match the draft.
- Assumption to confirm: Unit 3 follows the textbook's own order.

## Example 2: coworker message with --ultra

### Draft from the user

> làm 1 trang html tóm tắt kết quả khảo sát phụ huynh quý 3 từ file survey-q3.csv,
> đẹp như infographic báo, có thể thêm biểu đồ tương tác --ultra

### Question asked

1. Ai xem trang này, ở đâu? → Answer: ban giám đốc xem trên laptop trong buổi họp tháng.

### Refined prompt returned

```text
Làm một trang HTML tóm tắt kết quả khảo sát phụ huynh quý 3 từ survey-q3.csv (đính kèm),
để ban giám đốc xem trên laptop trong buổi họp tháng. Nhắm tới chất lượng đồ họa dữ liệu
của các báo lớn như New York Times; có thể thêm biểu đồ tương tác nếu nó giúp đọc nhanh
hơn, phần còn lại bạn tự quyết. Mọi con số lấy từ file, không thêm số liệu ngoài file.
Việc này quan trọng: cứ dùng nhiều token. Khi có bản đầu, mở trang ở khổ 1440 px, chụp
màn hình, đối chiếu từng con số với file, sửa chỗ chưa đạt và lặp lại đến khi bạn tự hào
về nó. Đừng dừng ở bản đầu tiên.
Chỉ hỏi tôi nếu file thiếu dữ liệu cho một câu hỏi khảo sát.
```

Changes made:
- Coworker message: one page, nothing destructive, so no headings.
- `--ultra` became the effort sentence; the flag itself is not in the prompt.
- "có thể thêm biểu đồ tương tác" stays a suggestion, not a requirement.
- "đẹp như infographic báo" became a reference to aim at; confirm New York Times is the
  style you meant.
- Before pasting, set the model to Opus 5.5 Extra (or high effort in Claude Code).

## Example 3: a draft that is already good

### Draft from the user

> refine: make an interactive timeline of our center's first 10 years from the attached
> photos and milestones.txt, warm and personal like a family album not a corporate report.
> take your time and polish it untill it feels right, maybe a short caption under each photo

### Questions asked

None: the draft says what to make, the standard (a family album, not a corporate report)
and the effort (take your time and polish it).

### Refined prompt returned

```text
Make an interactive timeline of our center's first 10 years from the attached photos and
milestones.txt, warm and personal like a family album, not a corporate report. Take your
time and polish it until it feels right; maybe a short caption under each photo. Before
you call it done, check every date and name against milestones.txt.
```

Changes made:
- Kept your wording; fixed "untill" and the sentence breaks.
- Added one self-check sentence so dates and names match milestones.txt.
- Kept "take your time and polish it" as your own effort request; no other changes.

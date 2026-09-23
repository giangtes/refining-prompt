# Worked example

## Draft from the user

> làm cho tôi syllabus unit 3 lớp 7, dùng skill lập kế hoạch rồi mới làm

## Questions asked (one round)

1. What will you do with the result? → Options: approve a plan only / print
   for teachers this week / feed an automated pipeline. Answer: print for teachers.
2. Which course and level? → Grade 7 core course or Grade 7 advanced course.
   Answer: Grade 7 core course.
3. Where should the run stop for you? → after the plan / after the draft PDF /
   only at the end. Answer: after the plan.

## Refined prompt returned

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
- PDF đã render và được đọc từng trang trước khi gửi tôi.
- Bộ test của repo chạy xanh.

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
- Turned "làm syllabus" into five checkable done conditions from the repo rules.
- Added one stopping point after the plan, as the user chose.
- Wrote every heading in Vietnamese to match the draft.
- Assumption to confirm: Unit 3 follows the textbook's own order.

# English test for a class (Vietnamese)

## Before

```text
viết lại prompt: soạn đề kiểm tra giữa kỳ 1 tiếng anh lớp 8, 40 câu, sát sách global success
```

## Questions the skill asked

1. Đề này dùng để làm gì và ai dùng? (a) in cho học sinh làm tại lớp (b) bản nháp để duyệt (c) khác
2. Phạm vi và thời lượng? (a) Unit 1–3, 45 phút (b) Unit 1–3, 60 phút (c) khác
3. 40 câu chia thành những phần nào?
4. Cần nhận file gì, đáp án đặt ở đâu?

While reading the repo, the skill found a course rule that bans AI-written
pronunciation items, and asked whether this test is an exception.

## After

```text
Soạn đề kiểm tra giữa kỳ 1 tiếng Anh lớp 8: 40 câu, 45 phút, bám sách Global Success 8
Unit 1–3. Đề in phát cho học sinh làm tại lớp tuần sau; giáo viên chấm theo đáp án.

Bối cảnh:
- Luật repo nằm trong AGENTS.md. Nguồn sách đã nạp nằm ở data/sources/global-success-8/.
- Chỉ dùng từ, cấu trúc và chủ đề của Unit 1–3.

Ma trận: phát âm 4 câu, từ vựng và ngữ pháp 16, đọc hiểu 10, viết 10.

Dùng các skill: skill tạo .docx, rồi skill đọc ảnh để kiểm từng trang bản in.

Xong nghĩa là:
- Một file .docx, đáp án ở trang riêng; câu đánh số liên tục 1–40.
- Mỗi phần đúng số câu trong ma trận; mỗi câu có đúng một đáp án đúng.
- Bảng tra nguồn cho giáo viên: mỗi từ và điểm ngữ pháp ghi unit và số trang sách.
- Bản PDF đã được đọc từng trang: không lộ đáp án, không sót ký tự lạ.

Tránh:
- Từ ngoài Unit 1–3; câu ví dụ hay số trang gán cho sách mà không có trong sách.
- Phần nghe, hoặc phần nào ngoài ma trận.
- Sửa dữ liệu, cấu hình hay code của repo.

Chỉ dừng lại hỏi tôi khi sách không đủ nội dung cho một phần, hoặc trước việc phá hủy.
Ngoài ra cứ làm tiếp.

Kết thúc bằng ba mục: Vướng ở tôi, Đã thay đổi, Phát hiện.
Đánh dấu mọi điểm chưa xác nhận được và nói đã tìm ở đâu.
```

**What changed:** "sát sách" became checkable conditions (unit and page for
every item, one correct answer per question); the purpose, the question matrix
and a page-by-page check of the printout were added.

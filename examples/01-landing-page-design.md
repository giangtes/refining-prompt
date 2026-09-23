# Landing page design (Vietnamese)

## Before

```text
refine my prompt: làm landing page mới cho khóa hè 2027 của trung tâm, nhìn hiện đại, không bị generic, dùng ak-frontend-design
```

## Questions the skill asked

1. Trang này dùng để làm gì? Trả lời trong một câu. (a) thu đăng ký qua form có sẵn (b) chỉ giới thiệu khóa học (c) khác
2. Ai xem trang, trên thiết bị nào, đến từ kênh nào?
3. Trang nằm ở đâu, lấy màu và font từ file nào? Nếu có ảnh trang tham khảo, hãy đính kèm.
4. Muốn xem mấy hướng thiết kế trước, và được deploy tới đâu?

While checking the repo, the skill also found that the brand file named in the
answers did not exist, and pointed the brief to the real one.

## After

```text
Làm landing page mới cho khóa hè 2027 trong apps/public của repo website. Trang này để
phụ huynh học sinh lớp 6–9 bấm quảng cáo Facebook trên điện thoại vào và đăng ký qua
form có sẵn.

Bối cảnh:
- Luật repo: AGENTS.md ở gốc và apps/public/AGENTS.md.
- Màu và font lấy từ brand/brand.json: navy là màu chủ đạo, vàng là màu nhấn.
- Dùng lại form đăng ký hiện có; không viết form mới, không đổi API.
- Lời tôi trong phiên này thắng mọi file.

Dùng các skill: ak-frontend-design (3 hướng thiết kế), rồi skill triển khai, rồi code review
trong một phiên riêng.

Xong nghĩa là:
- Bước 1: 3 hướng thiết kế khác nhau rõ rệt, mỗi hướng có ảnh 390×844 và 1440×900, kèm
  2–3 câu vì sao hợp với phụ huynh. Dừng lại chờ tôi chọn.
- Nút đăng ký thấy ngay ở màn hình đầu trên điện thoại và mở form có sẵn.
- Mọi màu và font lấy từ brand.json.
- Nội dung chưa có nguồn (lịch học, học phí) để trống và gắn nhãn CHƯA DUYỆT.
- Build và test chạy xanh; đã deploy lên bản preview, chưa đụng production.

Tránh:
- Nền kem hoặc trắng ngà, chữ nghiêng làm điểm nhấn, nhãn "01 / 02 / 03", nút bo tròn
  dạng viên thuốc, nhãn chữ monospace.
- Ảnh người từ kho ảnh, gradient tím sang xanh, emoji làm icon, chữ in cứng vào ảnh.
- Bịa con số, kết quả học sinh hay lời phụ huynh.
- Gửi thử form trên production; deploy production.

Chỉ dừng lại hỏi tôi khi 3 hướng thiết kế đã sẵn sàng, khi cần sửa component dùng chung,
hoặc trước việc có thể phá hỏng dữ liệu. Ngoài ra cứ làm tiếp và ghi tiến độ cùng tin
nhắn với bước tiếp theo.

Kết thúc bằng ba mục: Vướng ở tôi / Đã thay đổi / Phát hiện.
```

**What changed:** "hiện đại, không bị generic" became a list of specific patterns
to avoid; a purpose, a stop point after the design options, and a preview-only
deploy rule were added.

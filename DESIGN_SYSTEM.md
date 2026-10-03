# Kết nối câu lạc bộ — Design System & hướng dẫn thay nội dung

WebQuest giáo dục cho học sinh lớp 12; HTML/CSS/JavaScript thuần. Giữ sáu phần và nội dung dự án hiện hành, hai Google Form, hai rubric từ báo cáo Nhóm 4. Không yêu cầu học sinh tạo mã nguồn theo bộ mã này: học sinh dùng phần mềm tạo website cho sản phẩm CLB của mình.

## Màu sắc

| Vai trò | HEX | Cách dùng |
|---|---|---|
| Primary | #2854D9 | CTA chính, logo, liên kết, trạng thái menu |
| Primary hover | #2044B5 | Hover nút chính |
| Secondary / accent | #067368 | Nhãn học tập, dấu kiểm, điểm nhấn |
| Accent trang trí | #FFD56A | Chấm logo, nhấn nhỏ; không dùng chữ trắng trên màu này |
| Background | #F7F9FE | Nền toàn trang |
| Surface | #FFFFFF | Card, header, form |
| Blue surface | #EAF0FF | Lộ trình và menu đang chọn |
| Teal surface | #E5F6F1 | Thẻ học tập |
| Yellow surface | #FFF4D5 | Lưu ý và thẻ nhấn |
| Border | #DEE5F2 | Viền trang trí; không dùng làm dấu hiệu duy nhất cho điều khiển |
| Heading | #162746 | Tiêu đề, nhãn quan trọng |
| Body | #465674 | Nội dung dài |
| Secondary text | #586783 | Siêu dữ liệu và chỉ dẫn |

Các cặp đã tính theo độ chói tương đối: trắng/primary 6.25:1; heading/trắng 14.86:1; body/background 7.01:1; secondary/background 5.41:1. Màu chữ teal trên teal surface và primary trên blue surface cũng đạt tối thiểu 4.5:1. Đây là kiểm tra các cặp màu nội bộ, không phải chứng nhận toàn bộ website hoặc giao diện Google Forms.

Căn cứ: W3C WCAG 2.1 SC 1.4.3 yêu cầu 4.5:1 cho chữ thường, 3:1 cho chữ lớn: https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html

## Typography

Heading: Be Vietnam Pro — https://fonts.google.com/specimen/Be+Vietnam+Pro
Body: Inter — https://fonts.google.com/specimen/Inter
Fallback: Arial, sans-serif. Tải font với display=swap.

Scale nền 16px × 1.25: 16 → 20 → 25 → 31.25 → 39.06 → 48.83 → 61.04. Kích thước triển khai làm tròn, responsive bằng clamp và rem.

| Cấp | Kích thước | Line-height | Weight | Letter-spacing |
|---|---|---|---|---|
| H1 | 36–60px | 1.22; mobile 1.25 | 800 | -0.035em; mobile -0.025em |
| H2 | 24–32px | 1.35 | 700 | -0.025em |
| H3 | 20px | 1.45 | 700 | -0.015em |
| Lead | 20px; hero/mobile 18px | 1.6–1.65 | 400 | normal |
| Body | 16px | 1.7 | 400 | normal |
| Small / nhãn | 14px | 1.5–1.7 | 500–600 | normal |
| Metadata phụ | 12px | 1.7 | 600 | 0.04em |

## Layout và tương tác

- Grid spacing: 8, 16, 24, 32, 40, 48, 64px. Border/icon và chi tiết optical dùng giá trị riêng.
- Nội dung tối đa 1200px, gutter 24px; mobile 16px.
- 3 cột desktop → 2 cột tablet → 1 cột mobile; Hero 2 → 1 cột.
- Card radius 20px; button radius 12px; hero panel 28px.
- Shadow: 0 8px 28px rgba(22,39,70,.055).
- Hover 180–200ms, nâng nút 2px. Tắt chuyển động khi prefers-reduced-motion.
- Menu mobile có aria-expanded, đóng bằng Escape. Có skip link, focus ring, nhãn cho iframe.
- Rubric cuộn ngang độc lập và giữ cột tiêu chí; bảng có scope cho tiêu đề.
- Bốn tiết dùng đúng thời lượng đã duyệt; link form và rubric giữ nguyên.

## Prompt ảnh (không chèn chữ vào ảnh)

### Hero — 4:3 — Clean 3D clay / isometric

DALL-E 3:
“Create a clean 3D clay-style isometric illustration for a Vietnamese high-school educational WebQuest about designing school club websites. A small diverse group of older teenagers collaborates around a laptop, arranging website content cards and planning club activities. Friendly age-appropriate appearance, cobalt blue #2854D9, deep teal #067368, restrained golden yellow #FFD56A accents, bright white and very light blue surfaces. Soft studio lighting, subtle ambient shadows, generous negative space, polished minimalist composition, no text, no logos, no watermarks. Landscape composition, 4:3 aspect ratio. This is a fictional educational illustration, not a real classroom photograph.”

Midjourney v6:
“clean 3D clay isometric illustration, diverse Vietnamese high school teenagers collaboratively designing a school club website around a laptop, simple content cards, cobalt blue #2854D9, deep teal #067368, small golden yellow accents #FFD56A, white background, soft studio lighting, subtle shadows, minimal composition, generous negative space, no text, no typography, no logo, no watermark --ar 4:3 --v 6 --style raw”

Vị trí: config.js → heroImage, heroAlt. Ảnh xuất WebP, khoảng 1200×900, tối ưu dung lượng. Ảnh tùy chọn; không có ảnh thì lộ trình vẫn đầy đủ.

### Học liệu — 1:1 — Modern flat vector

DALL-E 3:
“Modern flat vector illustration of an organized educational resource kit for a school website design project: a laptop with abstract unlabeled content blocks, a notebook, a photo card, and a simple checklist. Crisp shapes, rounded forms, cobalt blue #2854D9 and deep teal #067368 with restrained warm yellow #FFD56A, clean white background, generous spacing, consistent visual weight, no words, no letters, no brands, no watermark. Square 1:1 composition.”

Midjourney v6:
“modern flat vector illustration of a school website design resource kit, laptop with unlabeled content blocks, notebook, photo card, checklist, crisp rounded shapes, cobalt blue #2854D9, deep teal #067368, small golden yellow accents, white background, minimal clean composition, no text no lettering no logos --ar 1:1 --v 6 --style raw”

Vị trí: có thể thay minh họa học liệu trong card; cần sửa markup để gắn ảnh. Không dùng làm ảnh minh chứng hoạt động thực tế.

### Banner kết luận — 16:9 — Abstract graphic

DALL-E 3:
“Minimal abstract graphic background for the closing section of a student learning website, suggesting connection and collaboration through a few rounded geometric panels and gentle intersecting lines. Fresh cobalt blue #2854D9, deep teal #067368, pale blue #EAF0FF, restrained golden yellow #FFD56A, mostly white negative space. Flat vector aesthetic, no representational objects, no text, no logo, no watermark. Wide 16:9 composition with a quiet central area suitable for separately overlaid HTML text.”

Midjourney v6:
“minimal abstract flat vector background, rounded geometric panels and gentle connecting lines, collaboration concept, cobalt blue #2854D9 deep teal #067368 pale blue #EAF0FF small golden yellow accents, mostly white negative space, quiet central area, no text no logo --ar 16:9 --v 6 --style raw”

Vị trí: tùy chọn tại trang Kết luận; không thay chữ HTML bằng chữ trong ảnh. Chỉ cần một ảnh Hero nếu muốn trang nhẹ.

## Sửa và chạy mã

1. Giải nén, chạy máy chủ trong thư mục dist, ví dụ `python -m http.server 8000`, rồi mở http://localhost:8000.
2. config.js: đổi link form, heroImage, classImage, videoEmbed, videoLink. Dùng URL HTTPS hoặc đường dẫn ảnh đã đặt trong dist/assets. Không đặt link quản trị Sheets hay link chỉnh sửa Form.
3. app.js: nội dung sáu phần. style.css: toàn bộ Design System. rubrics.json: bảng điểm, sửa đồng bộ với báo cáo nếu thay nội dung.
4. index.html: khung header/footer. mau.html: website CLB mẫu giả định; biểu mẫu mẫu không gửi dữ liệu. MauBaoCao.docx: tài liệu tải xuống.
5. standalone.html: bản một tệp gồm CSS, JS, config và rubric; có thể xem bằng cách mở trực tiếp. Đặt cạnh mau.html và MauBaoCao.docx để các liên kết học liệu hoạt động. Các Google Form cần Internet và quyền truy cập phù hợp.
6. Google Sites không nhận nguyên thư mục như một giao diện gốc. Có thể nhúng URL website này hoặc thử nhúng nội dung standalone.html; menu ngoài của Google Sites vẫn do Google Sites quản lý. Đây không phải thao tác đã sửa Google Sites tài khoản của bạn.

Kiểm tra thực hiện: cú pháp JavaScript; sáu route; menu sáu mục; hai rubric render đầy đủ; đối chiếu các link form; asset nội bộ; độ tương phản các cặp chính. Chưa kiểm thử bằng trình duyệt trực quan trên thiết bị thật. Font Google cần Internet; mã có font fallback.

## Phiên bản có minh họa

Màu primary chuyển sang #5148D9, hover #4038B7; nền #F6F8FF. Hình minh họa AI được tạo bằng công cụ Imagegen tích hợp, không phải ảnh hoạt động CLB có thật. Tệp ảnh tối ưu WebP tại dist/assets/team-clay.webp và dist/assets/reading-clay.webp. Prompt: học sinh Việt Nam cùng thiết kế website quanh laptop, phong cách 3D clay mềm, robot nhỏ dễ thương, xanh tím–teal–vàng–hồng; và học sinh cùng đọc sách trong thư viện theo cùng phong cách, không chữ/logo. Lộ trình tách riêng dưới hero; thẻ CLB dùng biểu tượng tương ứng.

#NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)
**Họ và tên:** Khưu Đông Nhựt Long
**MSSV:** 125002641
**Tên đề tài Website:** Landing Page sự kiện Khoa CNTT ("Lập trình & Robot Hackathon 2026")
**Công cụ AI đã sử dụng:** Claude, Gemini, AntigravityIDE

## 1. Yêu cầu ban đầu (System/Initial Prompt)
> Nghiên cứu cấu trúc từ các website sự kiện công nghệ / Hackathon thực tế (như Devpost, HackMIT, Vietnam Web Summit...) để xây dựng Landing Page sự kiện Khoa CNTT ("Lập trình & Robot Hackathon 2026") dày dặn nội dung. Bao gồm 9 khối thành phần (Header/Nav, Hero, Giới thiệu & Thể lệ, Timeline, Giải thưởng, Diễn giả, FAQ, Form đăng ký tĩnh, Footer). Ràng buộc nghiêm ngặt: 100% thuần HTML5 và CSS3, **tuyệt đối không sử dụng JavaScript**, chuẩn Semantic HTML5, sử dụng CSS Variables với màu chủ đạo `--primary-color: #00CCFF` (phong cách Dark/Cyberpunk UI), bố cục Flexbox/Grid và tích hợp Animate.css.

### Kết quả và nhận xét sau lần dựng ban đầu
- **Prompt đã dùng:** Toàn bộ yêu cầu cấu trúc nội dung và ràng buộc kỹ thuật ở prompt lần 1.
- **Kết quả AI tạo ra:** Mã nguồn `index.html` và `style.css` tạo nên một landing page quy mô lớn với đầy đủ 9 phần, ứng dụng hệ thống biến màu sắc dạng tối kết hợp xanh neon, bố cục lưới linh hoạt cho phần giải thưởng, diễn giả và lịch trình.
- **Nhận xét & Tinh chỉnh của SV:** Khung ban đầu đã đáp ứng tốt về mặt nội dung phong phú và định hình giao diện công nghệ. Tuy nhiên, để đạt chuẩn điểm tuyệt đối theo rubric, cần rà soát sâu hơn về tính tối ưu của các thẻ semantic (tránh lạm dụng div bọc lót) và tích hợp thêm thư viện hiệu ứng cuộn trang AOS theo đúng tiêu chuẩn đề thi. Các bước tinh chỉnh chi tiết được thực hiện ở các lần lặp tiếp theo.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iterations)

### Lần 1: Rà soát và chuẩn hóa Semantic HTML5
**Prompt đã dùng:**
> Role: Senior Front-end Developer & QA Engineer. Nhiệm vụ: Kiểm tra và tối ưu hóa toàn bộ mã nguồn Landing Page. Rà soát chuẩn Semantic HTML5: thay thế các thẻ `<div>` bọc lót không cần thiết bằng thẻ ngữ nghĩa tương ứng (`<section>`, `<article>`, `<aside>`, `<nav>`,...); đảm bảo chuẩn thẻ danh sách `<ul>`, `<li>` cho menu, lịch trình, cơ cấu giải thưởng.

**Kết quả AI tạo ra:**
- Định hình lại cấu trúc phân cấp của các khối nội dung, chuyển các khối danh sách lịch trình và cơ cấu giải thưởng sang dạng `<ul>` / `<li>` hợp lệ.
- Rà soát các khối section chính, đảm bảo không có thẻ div lồng nhau dư thừa quá mức, giữ nguyên tính logic của giao diện.

**Nhận xét & Tinh chỉnh của SV:**
Qua rà soát, AI đã tuân thủ tốt việc dùng thẻ danh sách. Tôi tiếp tục yêu cầu giữ vững cấu trúc này trong quá trình thêm thắt hiệu ứng để không làm vỡ bố cục Grid/Flexbox đã định hình từ trước.

### Lần 2: Tích hợp thư viện hiệu ứng (Animate.css & AOS) và tối ưu hóa Pure CSS
**Prompt đã dùng:**
> Role: Senior Front-end Developer & QA Engineer. Nhiệm vụ: Kiểm tra, tinh chỉnh và nâng cấp toàn bộ mã nguồn. 
> 1. Khai báo hệ thống CSS Variables trong khối `:root` với màu chủ đạo `--primary-color: #00CCFF`, bố cục responsive bằng Flexbox/Grid, thêm `html { scroll-behavior: smooth; }`, viết hiệu ứng `:hover` và `:focus` bắt mắt cho nút CTA và cards.
> 2. Tích hợp CDN CSS của Animate.css và CDN CSS/JS của thư viện AOS (Animate On Scroll), khởi tạo chính xác bằng đúng một dòng mã `<script>AOS.init();</script>`. Bổ sung thuộc tính `data-aos="fade-up"`, `data-aos-duration="1000"` vào các section, tiêu đề và thẻ cards.
> 3. Đảm bảo KHÔNG CÓ BẤT KỲ ĐOẠN MÃ JAVASCRIPT NÀO khác ngoài dòng khởi tạo AOS bắt buộc. Xuất lại toàn bộ mã nguồn hoàn chỉnh `index.html` và `style.css`.

**Kết quả AI tạo ra:**
- Tích hợp thành công CDN Animate.css và bộ thư viện AOS, đặt đúng lệnh khởi tạo `<script>AOS.init();</script>` trước thẻ đóng `<body>`.
- Bổ sung hệ thống `data-aos` cho các thành phần tiêu đề, card diễn giả, card giải thưởng.
- Hoàn thiện file `style.css` với hiệu ứng tương tác `:hover` và `:focus` (phóng to nhẹ, đổi bóng đổ box-shadow) dựa trên biến màu chủ đạo `#00CCFF`.
- Xác nhận không có bất kỳ logic JavaScript tự viết nào khác phát sinh trong dự án.

**Nhận xét & Tinh chỉnh của SV:**
Việc kết hợp chặt chẽ các yêu cầu về thư viện hiệu ứng bên thứ ba cùng ràng buộc cấm viết JS thủ công giúp trang web vừa đạt hiệu ứng chuyển động mượt mà khi cuộn trang, vừa giữ được sự tinh gọn đúng bản chất của bài thi Vibe Coding. Các trạng thái focus bằng bàn phím cũng được kiểm tra để đảm bảo tính khả dụng (accessibility).

## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?** 
  AI hỗ trợ cực tốt trong việc sinh nhanh khối lượng lớn nội dung tiếng Việt chuẩn chỉnh cho một trang landing page quy mô sự kiện (từ nội dung thể lệ, lịch trình chi tiết đến các câu hỏi FAQ), thiết lập hệ thống CSS Grid/Flexbox phức tạp và cấu hình đồng bộ hệ thống biến CSS Variables theo chủ đề công nghệ.
- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?** 
  - Phải đặt các ràng buộc kỹ thuật cốt lõi (như hệ màu chủ đạo, giới hạn tuyệt đối không viết JS thủ công, tích hợp đúng thư viện yêu cầu) ngay từ những prompt đầu tiên.
  - Cần có bước rà soát mã nguồn (Code Audit) qua từng iteration để ép AI sửa lỗi thay vì chỉ chấp nhận kết quả chung chung ở lần sinh đầu tiên.
  - Phân phối nhịp nhàng giữa việc tận dụng năng lực sinh nội dung thông minh của AI và việc kiểm tra kiểm soát cấu trúc mã nguồn thực tế trước khi đưa vào môi trường Production (GitHub Pages).
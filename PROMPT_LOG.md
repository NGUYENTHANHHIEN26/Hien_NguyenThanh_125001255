# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

**Họ và tên:** Nguyễn Thanh Hiền  
**MSSV:** 125001255  
**Lớp:** 25CT112  
**Tên đề tài Website:** HDH Tech Accessories – Website bán phụ kiện điện thoại
**Công cụ AI đã sử dụng:** ChatGPT 

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> **Prompt đã dùng:**
> Bạn là một chuyên gia Frontend Developer và UI/UX Designer. Hãy giúp tôi viết mã nguồn hoàn chỉnh gồm 2 file (`index.html` và `style.css`) cho một trang web bán hàng Phụ kiện điện thoại có tên là **HDH Tech Accessories**.
> Trang web phải tuân thủ nghiêm ngặt các tiêu chuẩn kỹ thuật sau:
> 1. **Chuẩn Semantic HTML5:** Bắt buộc sử dụng đúng ngữ nghĩa các thẻ `<header>`, `<nav>`, `<main>`, `<section>`, và `<footer>`. Hạn chế tối đa việc lạm dụng thẻ `div` vô nghĩa.
> 2. **CSS Variables & Reset:** Khai báo đầy đủ hệ thống `:root` (`--primary-color: #2563eb;`, `--secondary-color: #f3f4f6;`, `--text-color: #1f2937;`, `--font-main: 'Inter', sans-serif;`, `--spacing: 1.5rem;`) để quản lý màu sắc, font chữ và khoảng cách nhất quán.
> 3. **Modern Layout:** Sử dụng CSS Flexbox hoặc CSS Grid để xây dựng bố cục Header, Hero Section, Product Grid (Danh sách sản phẩm dạng lưới responsive), và Footer.
> 4. **Hiệu ứng tương tác:** Viết sẵn các hiệu ứng `:hover`, `:focus` mượt mà cho nút bấm (CTA buttons) và các thẻ sản phẩm (product cards).
> 5. **Thư viện tích hợp:** Chèn sẵn CDN của Animate.css và thư viện AOS (Animate On Scroll) vào file HTML.
> 
> Hãy trả về toàn bộ mã code rõ ràng, chia làm 2 file `index.html` và `style.css`.

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variable
* **Prompt đã dùng:**
  > Code ban đầu khá ổn, tuy nhiên phần danh sách sản phẩm bạn đang dùng quá nhiều thẻ `div` bọc lồng nhau mà chưa tận dụng đúng thẻ ngữ nghĩa. Hãy sửa lại: dùng thẻ `<section>` cho từng khối nội dung lớn (ví dụ: danh mục, sản phẩm nổi bật), sử dụng đúng cấu trúc thẻ tiêu đề từ `<h1>` đến `h3`. Đồng thời, kiểm tra lại toàn bộ file `style.css` đảm bảo các mã màu cứng đã được thay thế hoàn toàn bằng các biến CSS Variables đã khai báo ở `:root`.

* **Kết quả AI tạo ra:**  
  AI đã cấu trúc lại file `index.html` với các thẻ `<header>`, `<nav>`, `<main>`, `<section class="products">`, `<article class="product-card">`, và `<footer>`. Trong file `style.css`, các thuộc tính màu sắc và khoảng cách đều sử dụng biến `--primary-color`, `--secondary-color`, v.v.

* **Nhận xét & Tinh chỉnh của SV:**  
  Kiểm tra code thấy cấu trúc HTML sạch sẽ, đúng chuẩn ngữ nghĩa, không còn lạm dụng `div` bọc vô tội vạ. Biến CSS giúp việc đồng bộ màu sắc chủ đạo (màu xanh dương công nghệ) trở nên rất dễ dàng.

---

### Lần 2: Tích hợp thư viện Animate.css & AOS (Debug hiệu ứng cuộn trang)
* **Prompt đã dùng:**
  > Hãy giúp tôi tích hợp thư viện Animate.css và AOS (Animate On Scroll) vào dự án. Cụ thể: 
  > 1. Thêm CDN của Animate.css và AOS vào thẻ `<head>` của `index.html` và gọi script khởi tạo `AOS.init()` trước thẻ đóng `</body>`.
  > 2. Thêm class hiệu ứng chữ động từ Animate.css (ví dụ `animate__animated animate__fadeInDown`) vào tiêu đề chính ở Hero Section.
  > 3. Gắn thuộc tính `data-aos="fade-up"` vào các thẻ `<section>` sản phẩm để tạo hiệu ứng xuất hiện khi cuộn trang.

* **Thách thức gặp phải:**  
  Khi tích hợp xong, hiệu ứng `AOS` ban đầu không chạy mượt mà, các section bị hiển thị ẩn hoặc xuất hiện giật cục khi cuộn trang do thiếu file CSS của AOS hoặc chưa gọi hàm khởi tạo `AOS.init()`.

* **Cách sửa prompt (Debug prompt):**
  > Thư viện AOS chưa chạy khi cuộn trang và một số phần tử bị ẩn mất. Hãy kiểm tra lại xem tôi đã khai báo đủ file CSS, JS của AOS và gọi hàm `AOS.init();` đúng vị trí chưa? Hãy cung cấp đoạn code HTML/JS sửa lỗi chính xác.

* **Kết quả sau khi debug:**  
  AI cung cấp đầy đủ thẻ `<link>` CSS của AOS, đoạn script khởi tạo `AOS.init()` kèm cấu hình `duration: 800`, giúp các khối sản phẩm trượt lên mượt mà khi người dùng cuộn chuột mà không gây rối mắt.

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

* **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**  
  AI giúp tiết kiệm lượng lớn thời gian ở khâu dựng khung sườn HTML ban đầu, viết các đoạn CSS Flexbox/Grid phức tạp cho bố cục lưới sản phẩm responsive, và cấu hình các đoạn script mẫu của thư viện bên thứ ba (AOS, Animate.css) một cách nhanh chóng, chuẩn cú pháp.

* **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web:**  
  * Phải quy định rõ ràng ngay từ đầu các yêu cầu kỹ thuật khắt khe (như bắt buộc dùng thẻ ngữ nghĩa nào, cấm lạm dụng thẻ gì) để AI không sinh ra mã nguồn cẩu thả.
  * Khi gặp lỗi (như lỗi thư viện không chạy), cần đưa ra thông báo hoặc hiện tượng cụ thể để AI khoanh vùng và đưa ra đoạn code debug chính xác thay vì phải viết lại từ đầu.
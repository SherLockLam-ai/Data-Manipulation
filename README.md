# Data Crawling Project
1. Giới thiệu
Dự án này tập trung vào việc thu thập dữ liệu từ trang web VietnamNet.vn, bao gồm cả nội dung văn bản của các bài báo và hình ảnh thumbnail liên quan. Mục tiêu là xây dựng một bộ dữ liệu (corpus) đa phương thức (multimodal) để sử dụng cho các mục đích phân tích hoặc phát triển mô hình học máy trong tương lai.

3. Công nghệ và Thư viện chính
* Ngôn ngữ lập trình: Python
* Thư viện Web Scraping (thu thập dữ liệu web):
  - selenium: Được sử dụng để điều khiển trình duyệt web (Google Chrome) và tương tác với các phần tử động trên trang.
  - requests: Dùng để gửi các yêu cầu HTTP để tải nội dung như hình ảnh.
  - BeautifulSoup (mặc dù không được import rõ ràng, thường đi kèm với các dự án scraping để phân tích HTML, nhưng ở đây selenium đang được dùng để tìm phần tử).
* Thư viện xử lý dữ liệu:
  - os: Tương tác với hệ điều hành (tạo thư mục, quản lý đường dẫn file).
  - time, random: Để thêm độ trễ ngẫu nhiên, giúp tránh bị chặn bởi server.
  - tqdm: Hiển thị thanh tiến trình cho các vòng lặp.
  - PIL (Pillow): Xử lý hình ảnh (đọc, chuyển đổi định dạng, lưu).
  - io.BytesIO: Xử lý dữ liệu byte của hình ảnh.
* Công cụ khác:
  - Google Colab: Môi trường phát triển được sử dụng (có tích hợp driver cho Chrome và khả năng mount Google Drive).
  - zip: Nén thư mục dữ liệu đã thu thập.
  3. Cấu trúc dự án
.
├── crawlingTEXT.ipynb          # Notebook để thu thập nội dung văn bản bài báo
├── crawlingIMG.ipynb           # Notebook để thu thập hình ảnh thumbnail bài báo
├── vn_news_corpus/             # Thư mục lưu trữ các file .txt của bài báo (sẽ được tạo tự động)
├── vn_news_thumbnail/          # Thư mục lưu trữ các file hình ảnh thumbnail (sẽ được tạo tự động)
└── vn_news_corpus.zip          # File nén chứa toàn bộ corpus văn bản
└── vn_news_thumbnail.zip       # File nén chứa toàn bộ hình ảnh thumbnail

4. Các bước thực hiện
4.1. Thu thập Nội dung Văn bản (crawlingTEXT.ipynb)
Notebook này tập trung vào việc trích xuất tiêu đề, tóm tắt, tác giả và nội dung chính của các bài báo từ VietnamNet.vn.

4.2. Thu thập Hình ảnh Thumbnail (crawlingIMG.ipynb)
Notebook này tập trung vào việc thu thập các hình ảnh thumbnail liên quan đến các bài báo từ VietnamNet.vn.

5. Hướng dẫn sử dụng
- Môi trường: Các notebook được thiết kế để chạy trên Google Colab.
- Cài đặt chromedriver: Đảm bảo chromedriver tương thích với phiên bản Chrome trên môi trường Colab của bạn (thường đã được cài đặt sẵn hoặc có thể cần chạy lệnh cài đặt).
- Thực thi: Chạy từng cell trong notebook theo thứ tự.
- Lưu trữ Google Drive: Cho phép notebook mount Google Drive để lưu trữ các file .zip của bộ dữ liệu đã thu thập.

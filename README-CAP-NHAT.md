# Version 13.1 — MOBILE READING EDITION

## Bản cập nhật hiện tại

- Thiết kế lại hộp thư trên điện thoại theo dạng thẻ nổi **ở chính giữa màn hình**, không còn trượt sát mép dưới.
- Tách riêng vùng cuộn nội dung thư và khu vực phản hồi. Ba lựa chọn nhận xét luôn nằm trong tầm bấm ở cuối hộp thư, không bị đẩy khuất khi thư dài.
- Hộp thư tự co theo nội dung: thư ngắn không bị kéo cao thừa; thư dài dùng vùng đọc cuộn riêng, giữ nguyên kích thước chữ dễ đọc.
- Tinh chỉnh bố cục cho điện thoại dọc, điện thoại xoay ngang và máy tính bảng; căn giữa khung video khi nguồn video có tỷ lệ dọc hoặc ngang.
- Giữ giao diện chính sáng, bảng màu xanh-trắng; chỉ giữ tông tối bên trong chính nội dung video nếu video nguồn vốn tối.
- Cập nhật đúng 9 lá thư theo nội dung mới: **12 Hóa, 10 Pháp, 11 Anh 1, 11 Sử, 11 Toán, 10 Sinh, 10 Anh 2, 10 Địa và 11 Địa**.
- Giữ nguyên 27 lá thư còn lại, toàn bộ 36 ID/tên lớp, tìm kiếm, lọc khối, mở ngẫu nhiên, chuyển thư, phản hồi và công cụ cấu hình video.
- Giữ nguyên tệp MP4 demo, ảnh poster và `media/video-config.js`; có thể thay video chính thức sau mà không phải sửa bố cục.

### Hai chỗ trong nội dung cần bạn xác nhận sau

- Thư **10 Địa** trong nội dung bạn gửi dừng ở cụm “điều mình”. Mình giữ đúng như bản gửi, không tự viết tiếp câu.
- Thư **11 Địa** kết thúc bằng “K36 Địaa”. Mình cũng giữ nguyên chính tả như bạn gửi để tránh tự ý sửa nội dung.

### Kiểm tra kỹ thuật đã thực hiện

- `node --check` cho `app.js` và `data.js`.
- Phân tích cú pháp toàn bộ `style.css`.
- Đối chiếu dữ liệu trước/sau: đủ 36 lớp, đủ 36 thư; đúng 9 thư được thay, 27 thư còn lại và toàn bộ ID lớp không thay đổi.
- Kiểm tra cấu trúc hộp thư: vùng đọc và vùng phản hồi là hai vùng riêng, phần nhận xét nằm ngoài vùng cuộn.
- Nên mở bản đã tải lên GitHub Pages trên điện thoại thật để kiểm tra lần cuối theo thiết bị và trình duyệt bạn sẽ dùng.

### Cách cập nhật lên GitHub Pages

1. Giải nén gói này.
2. Mở thư mục `Version-13.1-Mobile-Reading-Edition`.
3. Tải **toàn bộ nội dung bên trong thư mục** lên repository đang chạy GitHub Pages, ghi đè các tệp cũ cùng tên.
4. Không bỏ thư mục `media/`; website cần cả video, poster và `video-config.js`.

---

# Version 13 — THE CINEMATIC EXPERIENCE

## Hướng nâng cấp

- Làm mới khu vực video theo hướng điện ảnh, có lớp phủ nút phát riêng; video không tự phát khi khách vừa mở trang.
- Khi video kết thúc, lời mời khám phá vườn thư đổi trạng thái và chuyển sắc nhẹ; không tự động cuộn trang hoặc ép người xem rời video.
- Đọc tỷ lệ khung hình từ metadata của tệp để hỗ trợ MP4 ngang, dọc hoặc vuông, không khóa theo thông số clip demo.
- Mỗi trái tim có nhịp nổi, vị trí ánh lấp lánh và một trong sáu biến thể chuyển động; 36 lớp vẫn giữ nguyên màu nhận diện theo khối.
- Bổ sung điều hướng thư trước/sau ngay trong hộp thư. Bộ đếm theo danh sách đang lọc; nút đầu/cuối tự vô hiệu hóa, không chuyển vòng ngoài danh sách.
- Căn hộp thư nổi chính giữa trên điện thoại, có lề hai bên bằng nhau; giữ thao tác đóng, cuộn nội dung và hỗ trợ vùng an toàn của thiết bị.
- Giữ `data.js` nguyên trạng: không thay tên lớp, ID, nội dung 36 lá thư hoặc logic dữ liệu gốc.

## Thay video demo sau này

Video hiện tại trong `media/` vẫn là bản demo và được giữ nguyên trong gói. Khi có MP4 chính thức, chỉ cần thay đường dẫn `src`, `title`, `caption` và `poster` (nếu cần) trong `media/video-config.js`; hướng dẫn chi tiết ở `media/README.md`. Không cần sửa giao diện hay JavaScript. Thời lượng, kích thước và tỷ lệ clip mới không bị kế thừa từ bản demo.

## Kiểm tra sau nâng cấp

- `node --check` cho `app.js`, `data.js` và `media/video-config.js`.
- CSS được phân tích không phát hiện lỗi cú pháp; HTML không có ID trùng.
- Kiểm thử giao diện tương tác: render đủ 36 lớp, mở thư, chuyển đến thư tiếp theo, đến thư cuối, quay lại thư trước và đóng thư; không ghi nhận lỗi JavaScript trong lượt kiểm thử.
- Kiểm tra hộp thư ở viewport 320, 360, 390, 430, 699, 768 và 1280 px; tâm hộp thư trùng tâm màn hình trong các kích thước được kiểm tra.
- Kiểm tra logic tự nhận diện hướng video bằng sự kiện metadata mô phỏng. Phát video thực tế vẫn cần được xác nhận trên hosting/trình duyệt mục tiêu với clip MP4 chính thức.

---

19.11 — CHUYÊN HẠ LONG
BẢN HOÀN THIỆN GIAO DIỆN VƯỜN TRÁI TIM & LÁ THƯ

CÁC NÂNG CẤP
- Tổ chức 36 lớp thành ba cụm Khối 10, Khối 11 và Khối 12.
- Làm nổi bật trái tim bằng ánh sáng, sắc màu theo khối và chuyển động nhẹ.
- Thiết kế lại phần hiển thị bên trong thư như một tờ thư lưu niệm riêng.
- Chia nhịp hiển thị theo câu/đoạn để dễ đọc hơn; nội dung văn bản được giữ nguyên.
- Nâng cấp mở thư ngẫu nhiên để không lặp lớp cho đến khi hết lượt trong danh sách đang lọc.
- Cải thiện trình bày trên màn hình điện thoại và máy tính.

BẢO TOÀN
- Không chỉnh sửa data.js (36 nội dung thư và dữ liệu lớp).
- Giữ nguyên video MP4, ảnh poster và cấu hình video.
- Giữ nguyên các chức năng tìm kiếm, lọc khối, mở thư, phản hồi, video và công cụ cấu hình media.

CÁCH SỬ DỤNG
1. Giải nén toàn bộ thư mục Version-11-main.
2. Mở index.html để xem thử, hoặc tải toàn bộ thư mục lên hosting.
3. Giữ nguyên cấu trúc thư mục media/ và các tệp JavaScript/CSS đi kèm.
4. Không chỉ tải riêng index.html; website cần các tệp style.css, app.js, data.js và thư mục media/.


## Chỉnh sửa tinh gọn giao diện — Polish Pass 03

- Bỏ dòng “12 tập thể · một sắc màu riêng” dưới tiêu đề của cả ba khối; giữ tên khối ngắn gọn.
- Bỏ các nhãn lặp trong lá thư: “Lời nhắn dành riêng cho cậu.” và “MỘT LỜI NHẮN DÀNH RIÊNG”.
- Bỏ ghi chú kỹ thuật về lựa chọn phản hồi trên thiết bị; đổi câu hỏi phản hồi thành “Cậu cảm thấy lá thư này thế nào?” để không tạo cảm giác phản hồi đã được gửi đi.
- Làm nổi bật chữ ký tác giả “DESIGNED & DEVELOPED BY — PHÙNG GIA HUY” bằng một khu vực credit riêng, đồng bộ với bảng màu website.
- Tinh chỉnh độ thoáng, đường nhấn và kiểu chữ bên trong tờ thư; không sửa nội dung các lá thư.
- Đã giữ nguyên `data.js`, video MP4, poster và cấu hình video so với bản Experience-Enhanced.

## Version 12 — Cân lại bố cục và dấu bản quyền

- Gỡ nhãn `DESIGNED & DEVELOPED BY` khỏi phần đầu trang để tiêu đề và nội dung mở đầu có thứ bậc rõ hơn.
- Thay bằng một dòng bản quyền nhỏ `© 2026 PHÙNG GIA HUY`, căn giữa và kẹp bằng hai nét mảnh; không dùng nền thẻ, viền khung hay bóng đổ.
- Giữ nguyên khối chữ ký lớn `PHÙNG GIA HUY` ở cuối website làm điểm nhận diện chính.
- Thu gọn khoảng đệm cuối khu vườn và chân trang trên điện thoại; bỏ khoảng trống 68px từng được cộng vào chân trang dù khối chữ ký vẫn còn nằm phía sau.
- Cân lại khoảng cách của phần mở đầu, tiêu đề khu vườn và khối chữ ký cuối trang trên màn hình nhỏ.
- Giữ nguyên 36 lá thư, nội dung dữ liệu, video, poster, công cụ cấu hình media và các tương tác hiện có.

### Kiểm tra sau chỉnh sửa

- JavaScript: `node --check` cho `app.js`, `data.js` và `media/video-config.js`.
- Kiểm thử trình duyệt ở viewport điện thoại: dựng đủ 36 thẻ lớp, mở được lá thư đầu tiên và không ghi nhận lỗi JavaScript trong lượt kiểm tra.
- Ảnh kiểm thử dùng nội dung nhúng để chạy giao diện cục bộ; đường dẫn video/poster vẫn cần được kiểm tra trên bản website đã giải nén hoặc host thật.

## Hotfix — căn giữa lá thư trên điện thoại

- Căn hộp thư trượt lên vào chính giữa theo chiều ngang, tạo khoảng cách hai bên bằng nhau.
- Giữ nguyên kiểu mở thư từ cạnh dưới, bo góc, hiệu ứng xuất hiện và khả năng cuộn nội dung.
- Không thay đổi `app.js`, `data.js`, nội dung 36 lá thư, video hoặc poster.

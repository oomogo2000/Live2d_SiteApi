# Live2D Widget.

! [] (https://forthebadge.com/images/badges/built-with-love.svg)
! [] (https://forthebadge.com/images/badges/uses-html.svg)
! [] (https://forthebadge.com/images/badges/made-with-javascript.svg)
! [] (https://forthebadge.com/images/badges/contains-cat-gifs.svg)
! [] (https://forthebadge.com/images/badges/powered-by-electricity.svg)
! [] (https://forthebadge.com/images/badges/makes-people-smile.svg)

## Tính năng

Thêm một live2d vào trang web. Tương thích với PJAX, tải không hỗ trợ.
Thêm tiện ích Live2D vào trang web. Tương thích với PJAX.

** CẢNH BÁO: Dự án này sử dụng một số lượng lớn cú pháp ES6, không hỗ trợ các trình duyệt cũ như IE 11. **
** CẢNH BÁO: Dự án này không hỗ trợ các trình duyệt cũ như IE 11. **

## 示例 demo.

Hiệu ứng có thể được xem ở góc trên bên trái của [Blog Mi Mi] (https://zhangshuqiao.org). (Lưu ý: Mô hình ký tự sau đây chỉ dành cho hiển thị, kho này không chứa bất kỳ mô hình nào.)

<IMG SRC = "Tài sản / Ảnh chụp màn hình-2.png" Chiều rộng = "280"> <IMG SRC = "Tài sản / Ảnh chụp màn hình-3.png" Chiều rộng = "280"> <IMG SRC = "Tài sản / Ảnh chụp màn hình-1.png Chiều rộng = "270">

Bạn cũng có thể thực hiện phát triển thứ cấp trong phạm vi cho phép, có một số ví dụ

- [demo.html] (https://mi.js.org/live2d-widget/demo/demo.html), hiển thị các hiệu ứng cơ bản
- [login.html] (https://mi.js.org/live2d-widget/demo/login.html), Giao diện đăng nhập của NPM

## phụ thuộc

Plugin này yêu cầu hỗ trợ biểu tượng Font Awesome (V4 hoặc V5), đảm bảo bảng kiểu có liên quan được tải trong trang. Lấy phông chữ Awesome V4 làm ví dụ, vui lòng tham gia `<head>`:
Phông chữ tuyệt vời (V4 hoặc V5) là bắt buộc đối với plugin này. Lấy phông chữ tuyệt vời v4 làm ví dụ, vui lòng thêm phần sau vào `<head>`:
`` ``
<link rel = "biểu định kiểu" href = "https://cdn.jsdelivr.net/npm/font-awgie/css/font-awger.min.css">>
`` `.
Nếu không, biểu tượng sẽ không hiển thị đúng. (Nếu bạn đã tải bất kỳ phiên bản nào của phông chữ tuyệt vời, đừng tải nó)

## sử dụng sử dụng

Thêm dòng mã này vào `<head>` hoặc `<body>` để hiển thị hiệu ứng:
`` ``
<script src = "https://cdn.jsdelivr.net/gh/stevenjoezhang/live2d-widget@lates/autoload.js"> </ script>
`` `.
Nếu trang web được bật, vì bảng không phải làm mới mỗi trang, bạn nên chú ý để đặt tập lệnh có liên quan bên ngoài khu vực làm mới PJAX.

Nói cách khác, nếu bạn có màu trắng nhỏ, hoặc chỉ có chức năng cơ bản nhất, chỉ cần sử dụng dòng mã này, cùng với phía trước phông chữ tuyệt vời, đặt nó vào `<head >``.
Đối với các trang được tạo bằng các công cụ mẫu khác nhau (như Nunjucks, Jinja hoặc PHP), cũng có thể sửa đổi chính nó và phương thức này tương tự, nhưng nó có thể hơi rắc rối. Lấy [hexo] (https://hexo.io) làm ví dụ, bạn cần định cấu hình đúng đường dẫn trong mẫu EJ hoặc NJK liên quan đến chủ đề để tải.

**Nhưng! Chúng tôi tự giới thiệu bản thân để cấu hình nó, nếu không nhiều tính năng không đầy đủ và có thể có vấn đề! **
Nếu bạn quan tâm đến việc ném, xin vui lòng xem mô tả chi tiết dưới đây.

### sử dụng CDN.

Để tùy chỉnh nội dung có liên quan, bạn có thể thực hiện fork kho này, sau đó sửa đổi nó. Tại thời điểm này, phương thức sử dụng thay đổi tương ứng với
`` ``
<script src = "https://cdn.jsdelivr.net/gh/username/live2d-widget@lates/autoload.js"> </ script>
`` `.
Thay thế tên `này. Thay thế nó bằng tên người dùng GitHub của bạn. Để thực hiện nội dung của CDN bình thường, bạn cần tạo một thẻ Git mới và đẩy đến kho GitHub, nếu không thì `@ mới nhất` vẫn là tệp trước khi cập nhật. Ngoài ra, bản thân CDN có bộ nhớ cache, vì vậy sự thay đổi có thể mất một thời gian nhất định để có hiệu lực. Tài liệu liên quan:
- [Thông tin cơ bản Git - Tagning] (https://git-scm.com/book/en/v2/git-basics-tagging)
- [Quản lý phát hành trong kho lưu trữ] (https://help.github.com/en/github/administering-rep repository/managing-release-in-a-repository)

### Tự chủ

Bạn cũng có thể đặt các tệp này trực tiếp trên máy chủ thay vì tải qua CDN.

- Nếu bạn có thể truy cập máy chủ của mình thông qua `ssh`, vui lòng câu lạc bộ toàn bộ kho đến máy chủ. thực hiện:
  `` ``
  CD / PATH / sang / của bạn / webroot
  #Clone kho lưu trữ này
  Git clone https://github.com/stevenjoezhang/live2d-widget.git.
  `` `.
- Nếu máy chủ của bạn không thể sử dụng kết nối `ssh` (ví dụ: máy chủ ảo chung), hãy chọn Tải xuống zip`, sau đó tải nó lên máy chủ thông qua` ftp`, v.v., sau đó trích xuất nó vào trang web.
- Nếu bạn đang triển khai blog tĩnh từ các công cụ như Hexo, vui lòng thực hiện lệnh `gitclone` đã nói ở trên trong thư mục tệp nguồn blog (tức là` nguồn.). Khi triển khai lại blog, các tệp có liên quan sẽ tự động tải chúng lên đường dẫn tương ứng. Để tránh các tệp này được sửa đổi bởi plugin HEXO, bạn có thể cần đặt `skip_render`.

Theo cách này, toàn bộ dự án có thể truy cập từ mạng công cộng thông qua IP máy chủ hoặc tên miền của bạn. Cố gắng không mở `autoload.js` và` live2d.js`js., Xác nhận rằng nội dung của các tệp này hoàn tất và chính xác.
Nếu mọi thứ là bình thường, sau đó bạn sẽ sửa đổi một số cấu hình. (Bạn cần sửa đổi trình soạn thảo văn bản trên máy chủ; bạn cũng có thể hoàn thành bước này theo cách này, tải nó lên máy chủ)
Sửa đổi `autoload.js` lear2d_path` là URL của `live2d-widget` thư mục này. Ví dụ, nếu bạn có thể vượt qua
`` `.
https://example.com/path/to/live2d-widget/live2d.min.js.
`` `.
Truy cập vào `live2d.min.js`, sau đó sửa đổi giá trị của` live2d_path`
`` `.
https://example.com/path/to/live2d-widget/
`` `.
Đầu cuối của đường dẫn là thích hợp để thêm. Cụ thể, vui lòng tham khảo chú thích `autoload.js`
Sau khi hoàn thành, thêm giao diện cô dâu của bạn
`` ``
<script src = "https://example.com/path/tob/live2d-widget/autoload.js"> </ script>
`` `.
Bạn có thể tải nó.

## api cuối

Phương thức `initwidget` được chấp nhận các tham số có tên` apipath` và` cdnpath`, hai đặt một trong số chúng. Trong đó `apipath` là URL của API phụ trợ, bạn có thể tự xây dựng nó và tăng mô hình (nhiều nội dung cần phải được sửa đổi và chi tiết sẽ không được mô tả sau). Và `CDNPath đã tải tài nguyên thông qua dịch vụ CDN như JSDELIVR, ổn định hơn.

## Tệp cấu trúc thư mục

- `waifu-tips.js` hơn nữa của nút và hộp thoại;
- `waifu-tips.json` Xác định điều kiện kích hoạt (` selector`, bộ chọn css) và văn bản được hiển thị khi kích hoạt (` text`);
- `waifu.css` là một kiểu kiểu cho một dây buộc.

Tệp nguồn hợp lệ cho [chủ đề tiếp theo của Hexo] (http://github.com/next-theme/hexo-theme-next), để áp dụng trang web của riêng bạn, bạn có thể cần sửa đổi hoặc thêm Nội dung mới.
** CẢNH BÁO: Tác giả không chịu trách nhiệm về bao gồm nhưng không giới hạn ở `waifu-tips.js` và` waifu-tips.json. Vui lòng đảm bảo rằng chúng phù hợp. **

Nếu bạn có bất kỳ câu hỏi, xin vui lòng chào đón vấn đề của bạn. Nếu có bất kỳ gợi ý sửa đổi nào, xin vui lòng chào đón yêu cầu kéo.

## Cảm ơn

<a href="https://www.browserstack.com/"> <img ight = "80" src = "https://live.browserstack.com/images/opensource/BrowsStack-logo.svg" alt = " Logo DuyerStack> </a>

> Cảm ơn DuyerStacks cho phép chúng tôi kiểm tra dự án này trong trình duyệt thực sự.
> Cảm ơn [https://www.browserstack.com/) để cung cấp cơ sở hạ tầng cho phép chúng tôi kiểm tra trong các trình duyệt thực sự!

<a href="htts://www.jsdelivr.com"> <img ight = "80" src = "https://raw.githubusercontent.com/jsdelivr-media/master/default/svg/jsdelivr- Logo-horizontal.svg> </a>

> Nhờ dịch vụ CDN do JSDELIVR cung cấp.
> Cảm ơn jsdelivr để cung cấp dịch vụ CDN công cộng.

Mã từ bài đăng trên blog này:
https://www.fghrsh.net/post/123.html.

Khi bạn nhấp vào nút Máy bay giấy của dây buộc, sẽ có một quả trứng, đến từ [WebSiteasteroids] (http://www.websiteasteroids.com).

## Hơn nữa

Thêm chi tiết có thể được tham chiếu:
https://imjad.cn/archives/lab/add-dynamic-poster-girl-with-live2d-to-your-blog-02.
https://github.com/xiazeyu/live2d-widget.js.
Https://github.com/summerscar/live2ddemo.

Về mô hình API phụ trợ:
Https://github.com/fghrsh/live2d_api.

# Live2D Widget

![](https://forthebadge.com/images/badges/built-with-love.svg)
![](https://forthebadge.com/images/badges/uses-html.svg)
![](https://forthebadge.com/images/badges/made-with-javascript.svg)
![](https://forthebadge.com/images/badges/contains-cat-gifs.svg)
![](https://forthebadge.com/images/badges/powered-by-electricity.svg)
![](https://forthebadge.com/images/badges/makes-people-smile.svg)

## Tính năng

Thêm tiện ích Live2D vào trang web. Tương thích với PJAX.
  
**CẢNH BÁO: Dự án này không hỗ trợ các trình duyệt cũ như IE 11.**

## Phụ thuộc
：  
Font Awesome (v4 or v5) là cần thiết cho plugin này. lấy Font Awesome v4 là ví dụ, vui lòng thêm các mục sau vào `<head>`:
```xml
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/font-awesome/css/font-awesome.min.css">
```
Nếu không, biểu tượng sẽ không hiển thị đúng.。（Nếu bạn đã tải bất kỳ phiên bản nào trong trang web Font Awesome，thì nó sẽ ko hoat động）

## Usage

Thêm dòng này `<head>` hoặc `<body>`，dòng này làm bạn có thể hiển thị hiệu ứng：
```xml
<script src="https://cdn.jsdelivr.net/gh/stevenjoezhang/live2d-widget@latest/autoload.js"></script>
```
Nếu trang web được bật PJAX，Bởi vì các waifu không phải làm mới mỗi trang, hãy chú ý đến các tập lệnh có liên quan bên ngoài khu vực làm mới PJAX.。

Nói cách khác, nếu bạn có màu trắng nhỏ, hoặc chỉ có chức năng cơ bản nhất, chỉ cần sử dụng dòng mã này, cùng với phía trước phông chữ tuyệt vời, đặt nó vào `<head >``.
Đối với các trang được tạo bằng các công cụ mẫu khác nhau (như Nunjucks, Jinja hoặc PHP), cũng có thể sửa đổi chính nó và phương thức này tương tự, nhưng nó có thể hơi rắc rối. Lấy [hexo] (https://hexo.io) làm ví dụ, bạn cần định cấu hình đúng đường dẫn trong mẫu EJ hoặc NJK liên quan đến chủ đề để tải.

**Nhưng! Chúng tôi tự  để cấu hình nó, nếu không nhiều tính năng không đầy đủ và có thể có vấn đề! **
Nếu bạn quan tâm đến việc này, xin vui lòng xem mô tả chi tiết dưới đây.

### Using CDN

Để tùy chỉnh nội dung có liên quan, bạn có thể thực hiện fork kho này, sau đó sửa đổi nó. Tại thời điểm này, phương thức sử dụng thay đổi tương ứng với
```xml
<script src="https://cdn.jsdelivr.net/gh/username/live2d-widget@latest/autoload.js"></script>
```
- [Git Basics - Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
- [Managing releases in a repository](https://help.github.com/en/github/administering-a-repository/managing-releases-in-a-repository)

### Self-host

Bạn cũng có thể đặt các tệp này trực tiếp trên máy chủ thay vì tải qua CDN.

- Nếu bạn có thể truy cập máy chủ của mình thông qua `ssh`, vui lòng câu lạc bộ toàn bộ kho đến máy chủ. thực hiện:
  ```bash
  cd /path/to/your/webroot
  # Clone this repository
  git clone https://github.com/stevenjoezhang/live2d-widget.git
  ```
- Nếu máy chủ của bạn không thể sử dụng kết nối `ssh` (ví dụ: máy chủ ảo chung), hãy chọn Tải xuống zip`, sau đó tải nó lên máy chủ thông qua` ftp`, v.v., sau đó trích xuất nó vào trang web.
- Nếu bạn đang triển khai blog tĩnh từ các công cụ như Hexo, vui lòng thực hiện lệnh `gitclone` đã nói ở trên trong thư mục tệp nguồn blog (tức là` nguồn.). Khi triển khai lại blog, các tệp có liên quan sẽ tự động tải chúng lên đường dẫn tương ứng. Để tránh các tệp này được sửa đổi bởi plugin HEXO, bạn có thể cần đặt `skip_render`.

Theo cách này, toàn bộ dự án có thể truy cập từ mạng công cộng thông qua IP máy chủ hoặc tên miền của bạn. Cố gắng không mở `autoload.js` và` live2d.js`js., Xác nhận rằng nội dung của các tệp này hoàn tất và chính xác.
Nếu mọi thứ là bình thường, sau đó bạn sẽ sửa đổi một số cấu hình. (Bạn cần sửa đổi trình soạn thảo văn bản trên máy chủ; bạn cũng có thể hoàn thành bước này theo cách này, tải nó lên máy chủ)
Sửa đổi `autoload.js` lear2d_path` là URL của `live2d-widget` thư mục này. Ví dụ, nếu bạn có thể vượt qua
```
https://example.com/path/to/live2d-widget/live2d.min.js
```
Truy cập vào `live2d.min.js`，Sau đó `live2d_path` Sửa đổi giá trị
```
https://example.com/path/to/live2d-widget/
```
<script src="https://example.com/path/to/live2d-widget/autoload.js"></script>
```
Bạn có thể tải nó.。

##  API

`Phương thức initWidget` chấp nhận các tham số có tên `apipath` và` cdnpath` đặt một trong số chúng. Trong đó `apipath` là URL của API phụ trợ, bạn có thể tự xây dựng nó và tăng mô hình (nhiều nội dung cần phải được sửa đổi và chi tiết sẽ không được mô tả sau). Và `CDNPath đã tải tài nguyên thông qua dịch vụ CDN như JSDELIVR, ổn định hơn.

## Files

- `waifu-tips.js` Chứa logic của các nút và hộp thoại；
- `waifu-tips.json` ình trạng kích hoạt giảm dần（`selector`，CSS Bô chon）Văn bản được hiển thị khi được kích hoạt（`text`）；
- `waifu.css`

Tệp nguồn là đúng Hexo của [NexT chủ đề](http://github.com/next-theme/hexo-theme-next)Để áp dụng cho web của riêng bạn, bạn có thể cần phải sửa đổi chính nó hoặc tăng  
Nếu bạn có bất kỳ câu hỏi, xin vui lòng chào đón vấn đề của bạn. Nếu có bất kỳ sửa đổi, yêu cầu kéo chào mừng。

## Thanks

<a href="https://www.browserstack.com/"><img height="80" src="https://live.browserstack.com/images/opensource/browserstack-logo.svg" alt="BrowserStack Logo"></a>

>   
> Thanks to [BrowserStack](https://www.browserstack.com/) for providing the infrastructure that allows us to test in real browsers!

<a href="https://www.jsdelivr.com"><img height="80" src="https://raw.githubusercontent.com/jsdelivr/jsdelivr-media/master/default/svg/jsdelivr-logo-horizontal.svg"></a>

> 
> Thanks jsDelivr for providing public CDN service.


Thêm nội dung có thể được tham chiếu：  
https://imjad.cn/archives/lab/add-dynamic-poster-girl-with-live2d-to-your-blog-02  
https://github.com/xiazeyu/live2d-widget.js  
https://github.com/summerscar/live2dDemo

Giới thiệu về mô hình API phụ trợ：  
https://github.com/fghrsh/live2d_api  
https://github.com/xiazeyu/live2d-widget-models  
https://github.com/xiaoski/live2d_models_collection

Ngoài ra, có một phiên bản máy tính để bàn：  
https://github.com/amorist/platelet  
https://github.com/akiroz/Live2D-Widget  
https://github.com/zenghongtu/PPet  
https://github.com/LikeNeko/L2dPetForMac

 Wallpaper Engine：  
https://github.com/guansss/nep-live2d

## License

Released under the GNU General Public License v3  
http://www.gnu.org/licenses/gpl-3.0.html



Live2D ：  
https://www.live2d.com/en/  
https://live2d.github.io

Live2D Cubism Core は Live2D Proprietary Software License で提供しています。  
https://www.live2d.com/eula/live2d-proprietary-software-license-agreement_en.html  
Live2D Cubism Components は Live2D Open Software License で提供しています。  
http://www.live2d.com/eula/live2d-open-software-license-agreement_en.html

> The terms and conditions do prohibit modification, but obfuscating in `live2d.min.js` would not be considered illegal modification.

https://community.live2d.com/discussion/140/webgl-developer-licence-and-javascript-question

## 更新 Update
 
https://www.fghrsh.net/post/170.html



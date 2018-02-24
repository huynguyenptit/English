## QUẢN LÝ PHÂN QUYỀN TRONG HỆ THỐNG ADMIN

#### 1. Quản lý phân quyền là gì?
Quản lý phân quyền là việc chúng ta có th quản lý người dùng, hoặc 1 nhóm người được phép nhìn thấy gì và làm được những gì trong hệ thống của mình.

###### ~ Phân loại truy cập
 - Content Access(truy cập nội dung): quản lý những nội dung được hiển thị cho các đối tượng người dùng cụ thể. Ví dụ: một người dùng học viên không thể xem nội dung của các khóa học mà mình chưa đăng ký mua.
 - Data Access(truy cập dữ liệu): quản lý loại dữ liệu người dùng có thể truy cập. Ví dụ: một người dùng thường không thể xem thông tin của người dùng admin, nhưng một người dùng admin có thể xem thông tin của tất cả người dùng.
 - Feature Access(truy cập tính năng): quản lý những tính năng mà người dùng có thể sử dụng. Ví dụ: người dùng giảng viên có thể chỉnh sửa nội dung khóa học, còn người dùng học viên thì không.
 
#### 2.Một số khái niệm cần lưu ý
###### ~ Permission
Một permission(quyền) định nghĩa 1 khả năng truy cập của một người dùng với hệ thống.
Một người dùng thường sẽ có một tập các quyền.(permissions)
###### ~ Role
Role (vai trò) là một tập các quyền dành cho một nhóm người dùng cụ thể.
#### 3.Thứ tự tiến hành phân quyền
Tạo quyền --> Tạo nhóm --> Gán quyền 
###### a.Tạo quyền:
Tạo ra các quyền tương ứng phù hợp với mô hình hệ thống. 
Vd: tạo quyền xóa tài khoản : có thể xóa tài khoản khác;
    tạo quyền chỉnh sửa bài viết : có thể chỉnh sửa nội dung các bài viết ...
###### b.Tạo nhóm:
Tạo ra các nhóm người dùng phù hợp với mô hình hệ thống. Ví dụ nhóm admin gồm tất cả các quyền, nhóm admod gồm quyền điều chỉnh người dùng, nhóm use gồm các quyền sử dụng hệ thống thông thườngr, ....
###### a.Gán quyền cho nhóm hoặc người dùng:
Quyền tạo ra cần được gán trực tiếp vào người dùng hoặc nhóm người dùng cụ thể. Ví dụ người dùng với email ngophuongtuan@gmail.com được gán quyền admin, người dùng tuan@gmail.com được gán quyền user,.....   
#### 4. Tìm hiểu
###### a.Facebook Fanpage:
Hệ thống phân quyền trên Facebook Fanpage được chia thành 6 nhóm vai trò chính:
 - Quản trị viên: Có thể quản lý tất cả các khía cạnh của Trang bao gồm gửi tin nhắn và đăng với tư cách Trang, tạo quảng cáo, xem quản trị viên nào đã tạo bài viết hoặc bình luận, xem thông tin chi tiết, gán vai trò trên Trang.
 - Biên tập viên: Có thể chỉnh sửa Trang, gửi tin nhắn và đăng với tư cách Trang, tạo quảng cáo, xem quản trị viên nào đã tạo bài viết hoặc bình luận, xem thông tin chi tiết.
 - Người kiểm duyệt: Có thể trả lời và xóa bình luận trên Trang, gửi tin nhắn dưới dạng Trang, xem quản trị viên nào đã tạo bài viết hoặc bình luận, tạo quảng cáo và xem thông tin chi tiết.
 - Nhà quảng cáo: Có thể xem quản trị viên nào đã tạo bài viết hoặc bình luận, tạo quảng cáo và xem thông tin chi tiết.
 - Nhà phân tích: Có thể xem quản trị viên nào đã tạo bài viết hoặc bình luận và xem thông tin chi tiết.
 - Người đóng góp trực tiếp: Có thể phát trực tiếp với tư cách Trang từ thiết bị di động. Họ không thể bình luận với tư cách Trang, tạo quảng cáo, truy cập Công cụ đăng hoặc xem thông tin chi tiết. Người đóng góp trực tiếp chỉ được có thể được gán với người đã có 1 vai trò trên Trang hoặc là bạn bè với người gán trên facebook.
Việc gán vai trò trên Fanpage có thể được thực hiện trong mục Cài đặt/ Vai trò trên trang.
###### b.Wordpress(Opensource version):
Hệ thống phân quyền trên Wordpress mặc định được chia thành 6 nhóm vai trò chính:
 - Super Admin – Nhóm người dùng cao nhất và có quyền quản trị toàn bộ hệ thống vì thực ra WordPress có tính năng tạo một mạng website nội bộ tên là WordPress MultiUser. Ngoài ra, Super Admin có quyền xóa các người dùng trong nhóm Administrator.
 - Administrator – Nhóm người dùng có quyền sử dụng toàn bộ các tính năng có trong một website WordPress, không bao gồm các website khác trong mạng website nội bộ.
 - Editor – Nhóm này có quyền đăng bài viết lên website (publish) và quản lý các post khác của những người dùng khác.
 - Author – Nhóm này sẽ có quyền đăng bài lên website và quản lý các post của họ.
 - Contributor – Nhóm này sẽ có quyền viết bài mới nhưng không được phép đăng lên mà chỉ có thể gửi để xét duyệt (Save as Review) và quản lý post của họ.
Subscriber – Người dùng trong nhóm này chỉ có thể quản lý thông tin cá nhân của họ.
Tuy nhiên, bạn có thể quản lý và phân quyền lại các nhóm người dùng cũng như tạo thêm các nhóm người dùng mới với các plugin hỗ trợ như Advanced Access Manager.
###### c.rappasoft/laravel-5-boilerplate:
Laravel 5 boilerplate sử dụng Laravel Permission để quản lý các role và permission cũng như gán quyền cho người dùng/ nhóm người dùng. Laravel Permission không có quyền mặc định nào cả. Bạn sẽ tự định nghĩa các quyền rồi gán các quyền cho người dùng.
|| Fb Fanpage           | Wordpress  | Laravel Boilerplate  |
| ------------- |:-------------:| -----:| -----:|
| Có các luật mặc định|Y|Y|N|
| Có thể chỉnh sửa luật|N|Y|Y|
| Tổ chức luật dạng ô |N|Y|N|
#### 5. Trải nghiệm
 - Hợp lý:
 -- Các tính năng được phân chia rõ ràng theo từng danh mục cụ thể.
 -- Bố cục rõ ràng, cụ thể.
 -- Màu sắc dễ nhìn.
 - Chưa hợp lý:
 -- Chưa đồng bộ hiệu ứng các tính năng. Khi click vào "báo cáo doanh thu" .
 -- Các icon chưa thẳng hàng.
 -- 1 icon dùng cho quá nhiều tính năng.
 -- Đặt quản lý view bên trong danh mục quản lý tài chỉnh có vẻ chưa hợp lý.
 -- Nội dung bảng trình bày lộn xộn, ví dụ nội dung trong 1 ô nên căn giữa.
 -- Các nội dung đa giá trị như "other permission" nên trình bày rõ ràng hơn.
 -- 1 số chức năng chưa có hệ thống filter.
 -- button search có kích thước nhỏ hơn input-search

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

Danh sách các permission ứng với các role trên wordpress :
![alt text](https://lh3.googleusercontent.com/XHl4jyI4_SBa6Wlm2wDj21bUuppkoqTSitqPb7RBF8mUC7xH_vnd6nxo6L3596cPK6zN8LZ4_WmC6HQK6nkEVKTf3NfhbtuV4hCEJ8aCPsW8wsbpvSSmqiT_QvD6s6C_OiGVMLh_fVGcn43C25ODyTx4xzyvaqWLgvOtYj5FQ_CWBmdfQZrwJ7KEyL8b2Ss6GWTPgqgQlN9X4IA9qmHxg4oCaHU5a2ypYECpUc3uieLD-Tw4T_H15Y23KK2ygtVRPqKXtDC00RImyTwQigGczSe4pQUOylH7Hz43XAI95vjcK6_kz901mZL04nspQg4mVGZbTkyFjLBSytt6LGPFX_0c8ifQ3eaVTv70QCuPJtJfagpNP4djwCZY0Kgd5deLAAVjWvzbkNscTR-oKmJ9F4n3-GYy2fVFOnYa8cT21cQ6IbzjRxZZwjbIlfc0bT6HXIuXItEeZ6batn_w3k7v2bsBwxzpXbkVqvmKY3GbrauprEoxswnjljqUi996PEGK5VaFG8BPOgNw3WgtDKivgwGBUgqUfGyC7oxAOWJluQO5D_s3ZJQM7p9f1LYKDB60bMb1dT5tNmI3qVX2Qvn9rxENFR2rghJ1wHz18bU=w781-h422-no)
![alt text](https://lh3.googleusercontent.com/ZUSheFr7cW_uKQ2K_DYx_OK736gUbbgpBXJDoucG84VbhrCROGBokTNyjTBcrcyOU65ExuOQ-Z60hqvU2cLY1Umkxjxjw6Gwi9Y30Fsc2hs_InzRffUIbf9sSwN3UJxQidlBk-8GyvE9Sk2bZ-tHTJvq-zjlxJZXi75U2wqRAYRmjFNKox3m_6i9OYQWDS9L9r-a0NKw7dBBLBCGasX8Yz79HRnal0KeN7k-q3XWWcAoDx1bLknRa_xQ4fxodTSHecThm5B3ltlCNLSZjpXL2ONlJKmcBNQXOWfSyvlr6oZicBH6d9T-KlrFpnYY-jjIQxpCAt4NF5PeNezsYampP6cSdRqOUONrhO5M3BZXN9oQ_zf99VSVdVDQcDc2X1rEvIQOONcFx-v9YjlcknBmJUFFxyMfC6uhuqHMrIAgHMGoG5oKvKz_xXV1Z5W48jWmeD_naLsacGckzR6fPtfJIcVSlyZN_zxnJhzK3dnYLSsaUXGQZbi0u2t936N-H1ZPmeUGH6xPAXXmp3gpcI70skpT8X84JlSbRr-va3GDAHnSv4GGZgZkTqHTHX32dXR2bejwjkWczqzfvqS0RslUahUZ2Pf5Jmpd1K3o57k=w779-h591-no)
![alt text](https://lh3.googleusercontent.com/Rh7fF3h3eovpJvC5vE0QjUhPLcw4629-IUEeQr8Zd50ZQ-g7M8Iwly-Ecoo-jsWrOHDOigY9OE5CQual-WlR603Wdw9-XIA6OsPOYdLOz-JtK15NCFLTQQjg_iaI0odsTjZM3JFp_JNIojLxaKBG99Yvo_AOtlJ70i4J3sHRcf_5ySZwx8IwiuyfbjNCsGtlantpAUWLkT14MasEEYs6Sjx5-S1szP8m35VzSpsEiqukNX-bR5XQHh4NlKrx8hzIyA8Tj0Aa_0Sfxx6vT0LOTowDFMcThNI5NXZzqkfvNxxaQ6n1hsLhBBMR-M8x65BtZGMC2UWQp2-nX1sYSHc1ybrQDzbvYeePQ-c7sAY-v9eNSuvhXuQ8zEgDuau86LhQzZlMkvM762Yg3zBohwHnju94_uYOYsfAlPtvlJyaV5vsx7Mq0xikq0QJ_BNCSB6WOIc8cW2ciC6eL6qU3DqFbaKtuUqZwi0zE7pqead-OK7giYdO9fxGpa5DKbp7ewYrE4MVQPmQd6SO8Vp2UEokiB8QvEYml13UDQjxC5RKrf3YNwBa5Blcbg4dvPEubHITjtDdNTI813ZAFzNBqSt65eIm2K9Boi6NoFOHIfE=w776-h614-no)
![alt text](https://lh3.googleusercontent.com/21gfuHFBh3w9dAYxGoUkTEpYb3NFKC8yf3rWOX6BQaCDh2WVIdzHQAMMdmIX6GUb0T-oyklh0ieuEqzfzgq6ieACZQUICA7W5YR0d6z3ZUKfD_HJsMVzl8ecpf8-Kav5SHp3iv6XV4oH7RIFGfYOS243HYcHsqpwBct8R7kxsZuBuTCL_69kHNK9vm-8kKfi42P9m34fcBgmAgHWghxp0XXx2qqdGrIaPp6Mg06-BhH7lGbwOkDUVPYaRjeTsN2hjtsLMhCuXMWO2Glk65ZvYbRqZn4GZQeY5h1jQBGfUvUK6B9gNnqC2liH9LpXygyFxQDf_OO26FuMdfXEwfEHMEjs_D4EA7KDk0B9tl9rcaQwzksvXcGmuAOOAWba3vAM2HZDObcbE68XTQ6oH5FCn9FLNXvp2Lxn8in_1CwseJb12vsudtok_x7P7XUIRE-rcpostX4BLzJD6Bzem2NboF12cm4YcRP-IOMHMOi2aPC1vHFjebL3VvyB-ASr3PiAqvj_PdGesEx-6a8tx34nvbJVE--I_JIfSDQoUSu_Jr3-CRImEHd00mtAs45PpzrNx20RTNpax4RwRJlAM8uRMysyJoGdge1SyiO2g50=w778-h617-no)
![alt text](https://lh3.googleusercontent.com/WuloO-tPjPpzCkoj-dTX-ZrrY1oVxwRWHx7uLqeljHbBx7kgoYAnDSJa4-WeqjfpANqFHqj3TcXjCfg7UZg_Y3DVnkjkeZbmhclUDXarj-dIXKZT_Bnf_2IdYoHZjDYy5r767z6ByqN0ohK-8c2byZZCKIyNBC-gtt6G64IEe7n4RtNIfYkXKrJDYs8R4oePA2aRzzSqKkjpFQEeYekM4uW9d_KmjQxCPFJoN3Xl30Y6m9RMgvJTPASFHY6hWEc1xgCU_lMoWGO682_IdGgsoJ-SyqPUc8Gy04jJdj2EubgsDPT80rxzznDdoNHFjoGsefo5UeLdvqezRrMNDml-bicCn9hYvkeE7DXzP1zWJXnKHKmSqR5-_cgW3u5G_7vWlEaQzqpxQ7vQUfIT34tXMjS5V-2W0c6BU_uDuNQvjwDyhypN-iN-AVB-BDcByxruCeO7wX116e61hBHVZwbOr5yHyGdiJDiOxBIxC3EM2h7KpzcVpJP06urQbe7fDaR-XyY8ONz3coBxjqAccBy-MDKUAfFzlGdAus8YbwceSc_I2eXjvn1PU0dMeJ-Oq1JFi4HLajgHC7SuRp_WBeXURcGRmwGD5WvBDME4SMA=w781-h425-no)
###### c.rappasoft/laravel-5-boilerplate:
Laravel 5 boilerplate sử dụng Laravel Permission để quản lý các role và permission cũng như gán quyền cho người dùng/ nhóm người dùng. Laravel Boilerplate chỉ có 1 permission mặc định là viewbackend, và 3 role mặc định là user, executive và admin. Bạn sẽ tự định nghĩa các quyền rồi gán các quyền cho người dùng.

###### *  So sánh:
 
|| Fb Fanpage           | Wordpress  | Laravel Boilerplate  |
| ------------- |:-------------:| -----:| -----:|
| Có các luật mặc định|Y|Y|Y(gần như sơ khai)|
| Có thể chỉnh sửa luật|N|Y(plugin)|Y(direct)|
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

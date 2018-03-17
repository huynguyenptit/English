[Nguồn](https://www.codeproject.com/Tips/808058/Reasons-for-using-design-patterns "Permalink to Reasons for using design patterns")

# Lý do sử dụng các mẫu thiết kế

## Giới thiệu

Nối tiếp của bài viết trước có tựa đề [Tại sao thiết kế là tối quan trọng đối với Phát triển Phần mềm][1]ư, tôi muốn bàn 1 chút về khía cạnh nâng cao hơnơn của thiết kế phần mềm gọi là `Các mẫu thiết kế`. Như đã đề cập ở bài trước,ý tưởng này xuất phát từ những cuộc thảo luận liên quan đến vai trò của thiết kế phần mềm với những đồng nghiệp. Chủ để chỉnh của cuộc thảo luận là quan điểm về việc `Các mẫu thiết kế` quá tổn thời gian để sử dụng trong phạm vi pháttriển phần mềm thương mại. Ý định của tôi ở đây là mô tả tại sao tôi tin rằng điều này là sai.


Tôi sẽ không đi chi tiết về kĩ thuật và việc thực hiện của bất kỳ `mẫu thiết kế` cụ thể nào. Có rất nhiều nguồn tốt về chúng ở khắp nơi.


## Vậy 1 mẫu thiết kế là gì?

Vậy chúng ta sẽ bắt đầu ngay sau đây, chính xác `mẫu thiết kế ` là gì? Đây là cặp thuật ngữ định nghĩa cho chúng.

Trích từ [Wikipedia][2]:

> "Một mẫu thiết kế là khoa học kiến trúc máy tính là được định nghĩa chính thức là 1 phương pháp để thiết kế vấn đề theo 1 cách chuyên môn

Trích từ [Data & Object Factory][3]:


>"Mẫu thiết kế là cách giải quyết định kỳ cho các vấn đề thiết kế bạn tìm thấy hàng ngày trong quá trình phát triển ứng dụng thực tế. Các mẫu đề cập về việc thiết kế và tương tác giữa các đối tượng, cũng như cung cấp nền tảng giao tiếp liên quan đến việc giải quyết lại 1 cách dễ dàng các thách thức lập trình thường gặp.
Do vậy `mẫu thiết kế` là mục đích chung trừu tượng của 1 vấn đề, nó có thể được áp dụng vào các giải pháp cụ thể. Vì phát triển phần mềm có xu hướng giải quyets nhiều loiaj vấn đề tương tự nhau, nên có cảm giác rằng bất cứ giải pháp phần mèm nào cũng sẽ kết hợp với các phẩn tương tự trong các giải pháp khác. Vậy tại sao chúng ta phải đi theo cái lồi mòm đó?

## Các dẫn chứng và hiểu tốt

Khi `các mẫu thiết kế` được dẫn chứng và hiểu tốt bởi các kĩ sư phần mềm, các nhà thiết kế và các lập trình viên, các giải phápr trong các ứng dụng của họ cũng sẽ được hiểu tốt

`Các mẫu thiết kế` cho các nhà lập trình phần mềm các hiair pháp đã được thử nghiệm về các vần đề thường gặp, vì thế giảm các rủi ro kĩ thuật tới dự án do không phải sử dụng các thiết kế mới và chưa được thử nghiệm.

`Các mẫu thiết kế` có thể ban đầu không làm giảm thời gian phát triển, vì sẽ có nhiefu khó khăn nếu nhóm vẫn còn lạ lẫm với chúng. Tuy nhiên khi nhìn sau hơnvào quy trình phát triền, một khi chungs ta acàng trở nên quen thuộc với chúng, thời gian phát triển sẽ dần dần giảm. 

## Điểm tương đồng với kỹ thuật xây dựng

Để chỉ ra sự tương đồng của `mẫu thiết kế` từ gócnhìn caủa kỹ thuật xây dựng( tôi đã nói về nó trong bài viết [Tại sao thiết kế đặc biệt quan trọng trong phát triển phần mềm][1] có nhiều điểm tương đôngf với phát triển phần mềm ), chúng ta sẽ nghĩ về giải pháp để vượt qua dòng sôngề. Đấy là một vấn đề liên tục với các kỹ sư xây dựng, mà có nhiều vấn đề được hiểu và ghi chép tốt.Các kỹ sư xây dựng có thể xây dựng 1 cây cầu hoặc đường hầm.

Vậy tại sao 1 kĩ sư xây dưng lại cố gắng giải quyết vấn đề trong khi có rất nhiều cách giải quyết thực tế mà họ có thể tham khảo? Có nhiều sự tương đồng giữa việc kĩ sư xây dựng giải quyết vấn đề dòng sôngông, và việc kĩ sư xây dưng  giải quyết các vấn đề phần mềm.

* Cách giải quyết vấn đề (chiếc cầu và hầm) đều được hiểu cũng như tài liệu tốt.
* Cách giải quyết(chiếc cầu và hâm) giải quyết vấn đề liên tục trong kỹ thuật xây dựng.
* Cách giải quyết(chiếc cầu và hầm) không cụ thể và có bất kỳ quy định nào, nhưng nó lại trừu tượng và có thể áp dụng trong việc giải quyết các vấn đè cụ thể (nguyên liệu cho chiếc cầu và hầm có thể được lựa chọn làm ví dụ cho việc định hướng các vấn đề cụ thể)

Cuộc tranh luận xoay quanh việc `các mẫu thiết kếế` rằng chúng không phù hợp cho thương mại  là do họ mất quá nhiều thời gian để triển khai nó, `các mẫu thiêt kế` tiết kiệm thời gian ( khi nhìn trên vòng đời của ứng dụng) bằng cách cho các nhà phát triển lựa chọn các giải pháp có sẵn để thử nghiệm để họ có thể ghép vào các việc cụ thể họ cần.

Vấn đề uduy nhất tôi từng gặp phải với `các mẫu thiêt skees` là nó tốn thơi gian để học. ! vài thứ trong số chúng có thể khó nắm vững. Đấy là 1 sự phê phánán hợp lý, và vì vậy nó yêu cầu  nhiều kĩ năng của người phát triển để sử dụng.
 Điều này có thể sẽ tăng chi phí bắt đầu cửa dự án. Tuy nhiên khi nhìn trên tổng quan vòng đời của ứng dụng, tôi tràn trể hi vọng rằng những chi phí khởi tạo đó sẽ được bù đặtp bởi chi phí duy trì giảm do dễ bao quát hơn và dễ dàng mở rộng hơn(khiến cho ứng dụng phát triểniển  dễ dàng hơn trong tương lai khi gặpcơ hội phát triển mới).

`mẫu thiết kế` giảm độ phức tạp, do vây các cách giải quyết sẽ trở nên dễ dàng hơn để hiểu

`mẫu thiết kế` là các giải pháp thử nghiệm, các nhà phát triển không cần để bắt đầu từ những lỗi, và có thể bắt đầu ngay với các cách giải quyết đã được kiểm chứng trong công việc (ngày kihi `mẫu thiết kễ` được sử dụng cho việc giải quyết các vấn đề tương tự). Sẽ không đúng khi hi vọng cái cầy giải quyết vấn để bằng qua đại dương, khi mà 1 con cầu đơn giản là không thích hợp

## Lợi ích của việc sử dụng mẫu thiết kế.

`mẫu thiết kế` cung cấp những lợi ích sau đây :

* Nó mang lại cho các nhà phát triển sự lựa chọn các giải pháp thử nghiệm để làm việc.
* Nó là ngôn ngữ trung lập do vậy bạn có thể áp dụng vào bất cứ ngôn ngữ nào hộ trợ hướng đối tượng.
* Nó hỗ trợ giao tiếp tốt đến nỗi mà nó được tài liệu tốt và có thể được nghiên cứu nếu nó không phải trường hợp bạn cần.
* Nó có ghi lại cái theo dõi kiểm chứng khi được sử dụng rộng rãi và vì thế giảm thiểu rủi ro công nghệ trong dự án.
* Nó rất linh hoạt và có thể sư dụng thực tế trong bất kỳ loại ứng dụng hoặc tên miền nào;.

## Kết luận

`Design Patterns`, despite their initial learning curve, are a very worthwhile investment. They will enable you to implement tried and tested solutions to problems, thus saving time and effort during the implementation stage of the software development lifecycle. By using well understood and documented solutions, the final product will have a much higher degree of comprehension. If the solution is easier to comprehend, then by extension, it will also be easier to maintain.
`Các mẫu thiết kế`, bất chấp những khó khăn trong việc học ban đầu, rất đáng để nghiên cứu. Nó sẽ giúp bạn tiến hành các giải pháp kiểm thử các vào các vấn đề, vì thế tiếp kiệm thời gian và công sứcức trong quá trình thực hiện các bước của chu trình phát triển phần mềm. Bằng cáchsử dụng các giải pháp được hiểu và tài liệu tốt, sản phẩm cuối cùng sẽ được lên 1 tầm cao mới về sự bao quát. Nếu giải pháp dễ để bao quát, thì nó cũng sẽ dễ bảo trì.

[1]: http://www.codeproject.com/Tips/806867/Why-Design-is-Critical-to-Software-Development
[2]: http://en.wikipedia.org/wiki/Design_pattern
[3]: http://www.dofactory.com/Patterns/Patterns.aspx

## Practice
- https://coderoncode.com/design-patterns/programming/php/coding/development/2014/01/19/design-patterns-php-factories.html
- https://www.binpress.com/tutorial/the-factory-design-pattern-explained-by-example/142
- https://www.codeproject.com/Articles/852232/PHP-Singleton-Pattern-A-Step-by-Step-And-Problem-s
- http://www.fluffycat.com/PHP-Design-Patterns/

**Keyword:** `how to separate code to package php`, `step by step php design pattern singleton`(change singleton to other for more result)
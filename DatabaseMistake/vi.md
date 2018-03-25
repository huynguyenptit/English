## Đâu là những lỗi phổ biến hay mắc phải của những nhà phát triển ứng dụng trong quá trình phát triển cơ sở dữ liệu.

_source https://stackoverflow.com/questions/621884/database-development-mistakes-made-by-application-developers_

**1. Không sử dụng các chỉ mục thích hợp**

Đây là 1 vấn đề tương đối đơn giản những vẫn xảy ra hàng ngày. Các khóa ngoại nên có các chỉ mục. Nếu bạn đang sử dụng 1 trường trong mệnh đề WHERE bạn nên (có lẽ) có chỉ mục trên nó. Các chỉ mục thường nên gồm nhiều cột dựa trên câu truy vấn bạn thực hiện.

**2. Không sử dụng các ràng buộc tham chiếu**

Cơ sở dữ liệu của bạn có thể thay đổi nhưng nếu nó hỗ trợ ràng buộc tham chiếu-- tức là tất cả các khóa ngoại được đảm bảo cho 1 thực thể tổn tại -- bạn nên sử dụng nó.

Rất hay thấy lỗi như thế này trên cơ sở dữ liệu MySQL. Tôi không nghĩ rằng MyISAM hỗ trợ nó. Nhưng InnoDB thì có. Bạn sẽ thấy những người sử dụng MyISAM hay những cơ sở dữ liệu khác hỗ trợ InnoDB nhưng không sử dụng nó

Thêm nữa:

- [Các ràng buộc như NOT NULL hay Khóa Ngoại quan trọng như thế nào khi ta luôn luôn kiểm soát đầu vào cơ sở dữ liệu với php](https://stackoverflow.com/questions/382309/how-important-are-constraints-like-not-null-and-foreign-key-if-ill-always-contr)
- [Khóa ngoại có thực sự cần thiết trong thiết kế cơ sở dữ liệu?](https://stackoverflow.com/questions/18717/are-foreign-keys-really-necessary-in-a-database-design)
- [Khóa ngoại có thực sự cần thiết trong thiết kế cơ sở dữ liệu?](http://www.diovo.com/2008/08/are-foreign-keys-really-necessary-in-a-database-design/)

**3. Sử dụng Natural Primary Keys hay Surrogate Primary Keys**

Khóa tự nhiên là các khóa dựa trên các dữ liệu có nghĩa bên ngoài mà (có vẻ) độc nhất. 1 vài ví dụ phổ biến là các mã sản phẩm, mã bưu điện gồm 2 kí tự(US), số an sinh xã hội và vân vân. Khóa đại diện hay kĩ thuật khóa chính tuyệt đối không có ý nghĩa bên ngoài hệ thống. Nó được phát minh hoàn toàn là để định nghĩa các thực thể và là các trường auto-incrementing  (SQL Server. MySQL, khác nưã) hoặc chuỗi(đặc biệt nhất là (Oracle) 

Theo ý kiến của tôi, bạn nên **luôn luôn** sử dụng Surrogate Keys. Vấn đề này tới từ những câu hỏi sau đây

- [Bạn thích khóa chính của bạn như thế nào?](https://stackoverflow.com/questions/404040/how-do-you-like-your-primary-keys)
- [Cách thực hành tốt nhất về Primary Key trong các bảng?](https://stackoverflow.com/questions/337503/whats-the-best-practice-for-primary-keys-in-tables)
- [Nên dùng khóa chính loại nào trong trường hợp này.](https://stackoverflow.com/questions/506164/which-format-of-primary-key-would-you-use-in-this-situation)
- [Surrogate vs. natural/business keys](https://stackoverflow.com/questions/63090/surrogate-vs-natural-business-keys)
- [Chúng ta có nên có 1 trường khóa chính?](https://stackoverflow.com/questions/166750/should-i-have-a-dedicated-primary-key-field)

Đây phần nào là 1 chủ đề gây tranh cãi khi không được chấp nhận rộng rãi. Trong khi bạn cố gắng tìm ra 1 người nghĩ rằng Natural Key trong 1 vài trường hợp là ổn, bạn sẽ không thấy bất kỳ sự chê bai nào về Surrogate Keys khác hơn là việc nó được cho là không cần thiết, Đây là 1 nhược điểm nhỏ nếu bạn hỏi tôi


Nhớ rằng, thậm chí [ các quốc gia không còn tồn tại](http://en.wikipedia.org/wiki/ISO_3166-1) (ví dụ, Nam Tư)
**4. Viết các câu trúy vấn được yêu cầu DISCTINCE hoạt động**

Bạn sẽ thường thấy nó trong các câu truy vấn được khởi tạo bởi ORM. Nhìn log đầu ra trong Hibernate và bạn sẽ thấy tất cả các câu truy vấn bắt đầu với:

SELECT DISTINCT ...

Đây là một cách viết để đảm bảo rằng bạn không phải nhận những dữ liệu trùng lặp (các đối tượng trùng lặp). Đôi lúc bạn sẽ thấy người ta làm điều này khá tốt. Nếu bạn thấy điều này quá nhiều thì thực ra nó chỉ là một cái cờ để đánh dấu. Chứ không phải DISTINCT không tốt hoặc giá trị không hợp lệ
Nó là như vậy nhưng không phải là một **Surrogate** hoặc một **Stopgap** cho việc viết đúng các câu truy vấn.

Từ [Tại sao tôi ghét DISCTINCT](http://weblogs.sqlteam.com/markc/archive/2008/11/11/60752.aspx):

> Theo quan điểm của tôi về nơi mọi thứ bắt đầu trở nên tồi tệ là khi 1 developer đang xây dựng lượng truy vấn đáng kể, join các bảng với nhau và đột nhiên anh ta nhận ra rằng nó **có vẻ** như anh ta đang lấy ra những hàng trùng lặp và ngay lập tức nghĩ ra giải pháp cho vấn đề này thông qua từ khóa DISTINCT và **Đá phăng** tất cả những rắc rối kia.

**5. Khuyến khích tập hợp các kết nối**

Các lỗi thường gặp khác ở các nhà phát triển ứng dụng cơ sở dữ liệu là không nhận ra cái giá của sự kết hơpj (Mệnh đề GROUP BY) có thể được so sánh để join.

Để cho bạn một ý tưởng về sức lan tỏa của nó, Tôi đã viết về chủ đề này rất nhiều lần và rất nhiều đã bị downvote. Ví dụ như:
[Câu lệnh SQL - “join” vs “group by và having”](https://stackoverflow.com/questions/477006/sql-statement-join-vs-group-by-and-having/477013#477013)

> câu truy vấn đầu tiên:

SELECT userid
FROM userrole
WHERE roleid IN (1, 2, 3)
GROUP by userid
HAVING COUNT(1) = 3

> thời gian truy vấn: 0.312 s

> câu truy vấn thứ 2:

SELECT t1.userid
FROM userrole t1
JOIN userrole t2 ON t1.userid = t2.userid AND t2.roleid = 2
JOIN userrole t3 ON t2.userid = t3.userid AND t3.roleid = 3
AND t1.roleid = 1

> thơi gian truy vấn: 0.016 s

> Đúng vậy. Phiên bản nối tôi đề xuất **nhanh gấp 2 lần phiên bản nhóm.**

**6. Không đơn giản hóa các câu truy vấn phức tạp qua view**

Không phải tất cả các nhà cung cấp cơ sở dữ liệu hỗ trợ view nhưng chúng đều có thể đơn giản hóa các câu truy vấn nếu sử dụng 1 cách khôn ngoan. Ví dụ, trong 1 dự án tôi sử dụng [generic Party model](http://www.tdan.com/view-articles/5014/) cho CRM. Đấy là 1 kỹ thuật mô hình rất mạnh và linh hoạt có thể sử dụng nhiều phép nối. Trong mô hình này có :

- **Party**: con người và các tổ chức;
- **Party Role**: các việc mà các nhóm làm , như nhân viên và nhà tuyển dụng;
- **Party Role Relationship**: các luật liên quan thế nào với các luật khác.

Ví dụ:

- Ted là một Người, đóng một vai trò nhỏ trong Party
- Ted có nhiều vai trò, một trong số đó là Người làm thuê;
- Intel là một tổ chức, đóng một vai trò nhỏ trong Party;
- Intel có nhiều vai trò, một trong số đó là Người quản lí nhân sự;
- Intel thuê Ted, có nghĩa là có một mối quan hệ tương ứng giữa những vai trò đó.

Vì có 5 bảng được join và kết nối vs Ted vs nhà tuyển dụng của anh ta. Bạn giả sử tất cả những Người lao động là Người(không phải tổ chức) và cung cấp chế độ trợ giúp:

CREATE VIEW vw_employee AS
SELECT p.title, p.given_names, p.surname, p.date_of_birth, p2.party_name employer_name
FROM person p
JOIN party py ON py.id = p.id
JOIN party_role child ON p.id = child.party_id
JOIN party_role_relationship prr ON child.id = prr.child_id AND prr.type = 'EMPLOYMENT'
JOIN party_role parent ON parent.id = prr.parent_id = parent.id
JOIN party p2 ON parent.party_id = p2.id

Và đột nhiên bạn có một cái nhìn rất đơn giản về dữ liệu mà bạn muốn nhưng trên một mô hình dữ liệu có tính linh hoạt cao.

**7. Không lọc đầu vào**

Đây là một trong những lỗi lớn. Bây giờ tôi thích PHP nhưng nếu bạn không biết bạn đang làm cái gì thì thật dễ để tạo ra một tang web dễ bị tấn công. Không có gì có thể tổng kết tốt hơn so với [story of little Bobby Tables](http://xkcd.com/327/).

Dữ liệu được cung cấp bở người dùng bằng URLs, dữ liệu form **và các Cookie** nên luôn luôn được coi là kẻ thù và cần được thanh lọc. Đảm bảo rằng bạn đang lấy những gì bạn muốn.

**8. Không sử dụng các lệnh được chuẩn bị**

Các câu lệnh đã có sẵn là khi bạn biên dịch một truy vấn trừ dữ liệu được sử dụng trong Insert, Update và 
mệnh đề Where và sau đó cung cấp nó. Ví dụ như:

SELECT * FROM users WHERE username = 'bob'

vs

SELECT * FROM users WHERE username = ?

or

SELECT * FROM users WHERE username = :username

tùy thuộc vào hệ thống của bạn.

Tôi đã nhìn thấy những cơ sở dữ liệu dài đến tận đầu gối của khi họ làm cách này. Về cơ bản, mỗi khi cơ sở dữ liệu hiện đại gặp một truy vấn mới, nó phải biên dịch nó. Nếu nó gặp một truy vấn nó được nhìn thấy trước, bạn đang cho cơ sở dữ liệu cơ hội để cache truy vấn biên dịch và kế hoạch thực hiện. Bằng cách thực hiện các truy vấn rất nhiều bạn đang cho cơ sở dữ liệu cơ hội để trưng bày ra và tối ưu hóa cho phù hợp (ví dụ, bằng cách ghim các truy vấn biên dịch trong bộ nhớ).

Sử dụng các câu lệnh có sẵn cũng sẽ cung cấp cho bạn số liệu thống kê có ý nghĩa về tần suất các truy vấn nhất định được sử dụng.

Các câu lệnh có sẵn cũng sẽ giúp bạn chống lại các cuộc tấn công SQL injection tốt hơn.

**9. Not normalizing enough**

[Database normalization](http://en.wikipedia.org/wiki/Database_normalization) is basically the process of optimizing database design or how you organize your data into tables.

Just this week I ran across some code where someone had imploded an array and inserted it into a single field in a database. Normalizing that would be to treat element of that array as a separate row in a child table (ie a one-to-many relationship).

This also came up in [Best method for storing a list of user IDs](https://stackoverflow.com/questions/620645/best-method-for-storing-a-list-of-user-ids):

> I've seen in other systems that the list is stored in a serialized PHP array.

But lack of normalization comes in many forms.

More:

- [Normalization: How far is far enough?](http://www.techrepublic.com/article/normalization-how-far-is-far-enough/)
- [SQL by Design: Why You Need Database Normalization ](http://www.sqlmag.com/Article/ArticleID/4887/sql_server_4887.html)

**10. Normalizing too much**

This may seem like a contradiction to the previous point but normalization, like many things, is a tool. It is a means to an end and not an end in and of itself. I think many developers forget this and start treating a "means" as an "end". Unit testing is a prime example of this.

I once worked on a system that had a huge hierarchy for clients that went something like:

Licensee -&gt;  Dealer Group -&gt; Company -&gt; Practice -&gt; ...

such that you had to join about 11 tables together before you could get any meaningful data. It was a good example of normalization taken too far.

More to the point, careful and considered denormalization can have huge performance benefits but you have to be really careful when doing this.

More:

- [Why too much Database Normalization can be a Bad Thing](http://www.selikoff.net/blog/2008/11/19/why-too-much-database-normalization-can-be-a-bad-thing/)
- [How far to take normalization in database design?](https://stackoverflow.com/questions/496508/how-far-to-take-normalization-in-database-design)
- [When Not to Normalize your SQL Database](http://www.25hoursaday.com/weblog/CommentView.aspx?guid=cc0e740c-a828-4b9d-b244-4ee96e2fad4b)
- [Maybe Normalizing Isn't Normal](http://www.codinghorror.com/blog/archives/001152.html)
- [The Mother of All Database Normalization Debates on Coding Horror](http://highscalability.com/mother-all-database-normalization-debates-coding-horror)

**11. Using exclusive arcs**

An exclusive arc is a common mistake where a table is created with two or more foreign keys where one and only one of them can be non-null.  **Big mistake.** For one thing it becomes that much harder to maintain data integrity. After all, even with referential integrity, nothing is preventing two or more of these foreign keys from being set (complex check constraints notwithstanding).

From [A Practical Guide to Relational Database Design](http://books.google.com.au/books?id=7ZAk0YiKQV0C&pg=PA110&lpg=PA110&dq=%22exclusive+arc%22+database&source=bl&ots=AyNPWsac__&sig=gBFIerXckQlVpRdd6ycI5JEgq3U&hl=en&ei=PzGzSZfrFcPVkAWWyZDZBA&sa=X&oi=book_result&resnum=1&ct=result):

> We have strongly advised against exclusive arc construction wherever possible, for the good reason that they can be awkward to write code and pose more maintenance difficulties.

**12. Not doing performance analysis on queries at all**

Pragmatism reigns supreme, particularly in the database world. If you're sticking to principles to the point that they've become a dogma then you've quite probably made mistakes. Take the example of the aggregate queries from above. The aggregate version might look "nice" but its performance is woeful. A performance comparison should've ended the debate (but it didn't) but more to the point: spouting such ill-informed views in the first place is ignorant, even dangerous.

**13. Over-reliance on UNION ALL and particularly UNION constructs**

A UNION in SQL terms merely concatenates congruent data sets, meaning they have the same type and number of columns. The difference between them is that UNION ALL is a simple concatenation and should be preferred wherever possible whereas a UNION will implicitly do a DISTINCT to remove duplicate tuples.

UNIONs, like DISTINCT, have their place. There are valid applications. But if you find yourself doing a lot of them, particularly in subqueries, then you're probably doing something wrong. That might be a case of poor query construction or a poorly designed data model forcing you to do such things.

UNIONs, particularly when used in joins or dependent subqueries, can cripple a database. Try to avoid them whenever possible.

**14. Using OR conditions in queries**

This might seem harmless. After all, ANDs are OK. OR should be OK too right? Wrong. Basically an AND condition **restricts** the data set whereas an OR condition **grows** it but not in a way that lends itself to optimisation. Particularly when the different OR conditions might intersect thus forcing the optimizer to effectively to a DISTINCT operation on the result.

Bad:

... WHERE a = 2 OR a = 5 OR a = 11

Better:

... WHERE a IN (2, 5, 11)

Now your SQL optimizer may effectively turn the first query into the second. But it might not. Just don't do it.

**15. Not designing their data model to lend itself to high-performing solutions**

This is a hard point to quantify. It is typically observed by its effect. If you find yourself writing gnarly queries for relatively simple tasks or that queries for finding out relatively straightforward information are not efficient, then you probably have a poor data model.

In some ways this point summarizes all the earlier ones but it's more of a cautionary tale that doing things like query optimisation is often done first when it should be done second. First and foremost you should ensure you have a good data model before trying to optimize the performance. As Knuth said:

> Premature optimization is the root of all evil

**16. Incorrect use of Database Transactions**

All data changes for a specific process should be atomic. I.e. If the operation succeeds, it does so fully. If it fails, the data is left unchanged. - There should be no possibility of 'half-done' changes.

Ideally, the simplest way to achieve this is that the entire system design should strive to support all data changes through single INSERT/UPDATE/DELETE statements. In this case, no special transaction handling is needed, as your database engine should do so automatically.

However, if any processes do require multiple statements be performed as a unit to keep the data in a consistent state, then appropriate Transaction Control is necessary.

- Begin a Transaction before the first statement.
- Commit the Transaction after the last statement.
- On any error, Rollback the Transaction. And very NB! Don't forget to skip/abort all statements that follow after the error.

Also recommended to pay careful attention to the subtelties of how your database connectivity layer, and database engine interact in this regard. 

**17. Not understanding the 'set-based' paradigm**

The SQL language follows a specific paradigm suited to specific kinds of problems. Various vendor-specific extensions notwithstanding, the language struggles to deal with problems that are trivial in langues like Java, C#, Delphi etc.

This lack of understanding manifests itself in a few ways.

- Inappropriately imposing too much procedural or imperative logic on the databse.
- Inappropriate or excessive use of cursors. Especially when a single query would suffice.
- Incorrectly assuming that triggers fire once per row affected in multi-row updates.

Determine clear division of responsibility, and strive to use the appropriate tool to solve each problem.




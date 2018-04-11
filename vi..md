

##Đặc tả Semantic Versioning (SemVer)
Các từ khoá như “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, và “OPTIONAL” trong các tài liệu được mô tả và giải thích trong RFC 2119.

Phần mềm sử dụng Semantic Versioning phải khai báo 1 API công khai. API này có thể được khai báo trong mã nguồn của chính nó hoặc phải tồn tại trong tài liệu. Tuy nhiên khi nó hoàn thành, nó phải có tính chính xác và toàn diện.

Một phiên bản đánh số thông thường phải có dạng X.Y.Z với điều kiện X, Y và Z là số không âm, và không được có số 0 ở đầu. X là số phiên bản chính, Y là phiên bản nhỏ, và Z là phiên bản vá lỗi. Mỗi phần tử này đều phải là các số tăng dần. Ví dụ: 1.9.0 -> 1.10.0 -> 1.11.0.

Một khi phiên bản package đã được phát hành, nội dung của phiên bản đó bắt buộc không thể thay đổi. Mọi sự thay đổi đều phải được phát hành như 1 phiên bản mới.

Phiên bản chính số 0 (0.y.z) là để phát triển lúc đầu. Mọi thứ đều có thể thay đổi bất kỳ lúc nào. Không được công bố API công khai là ổn định.

Phiên bản 1.0.0 định nghĩa API công khai. Cách mà số thứ tự của phiên bản được tăng lên sau khi phát hành phụ thuộc vào API công khai và cách nó thay đổi như thế nào.

Phiên bản vá lỗi Z (x.y.Z | x > 0) phải được tăng lên nếu chỉ sửa các lỗi tương thích đã được đưa ra. Khi sửa một lỗi đã được đưa ra là khắc phục các hành vi không chính xác ở bên trong.

Phiên bản nhỏ Y (x.Y.z | x > 0)phải được tăng lên khi có tính năng mới, không tương thích các phiên bản trước đã được giới thiệu trong API công khai. Nó cũng phải được tăng lên nếu bất kì hàm API công khai nào không còn được sử dụng nữa. Nó cũng có thể tăng lên nếu chức năng mới ảnh hưởng đáng kể hoặc cải thiện được các đầu vào trong các mã bên trong. Nó cũng có thể chứa cả các thay đổi ở mức bản vá. Phiên bản vá phải được đặt lại về 0 khi phiên bản nhỏ được tăng.

Phiên bản chính X (X.y.z | X > 0) phải được tăng lên nếu có bất kỳ sự thay đổi nào khác dẫn tới việc không tương thích với đã được giới thiệu trong API công khai.Nó có thể bao gồm các thay đổi mực nhỏ và bản vá. Phiên bản vá và nhỏ phải được đặt lại về 0 khi phiên bản lớn được tăng.

Phiên bản trước khi phát hành có thể được biểu thị bằng các dấu gạch ngang và 1 loạt các dấu chấm phân cách các định danh ngay sau phiên bản vá lỗi. Các định danh phải chứa các ký tự và gạch nối thuộc bảng mã ASCII [0-9A-Za-z-]. Các định danh không được phép rỗng. Các định danh số không được phép bắt đầu bởi các số 0. Các phiên bản trước khi phát hành có độ ưu tiên thấp hơn so với phiên bản kết hợp bình thường. 1 phiên bản trước khi phát hành được coi là phiên bản không ổn định và có thể không thỏa mãn các yêu cầu tương thích dự định như là được biểu thị so với những phiên bản bình thường liên quan. Ví dụ: 1.0.0-alpha, 1.0.0-alpha.1, 1.0.0-0.3.7, 1.0.0-x.7.z.92.

Xây dựng siêu dữ liệu có thể được biểu thị bằng cách thêm các dấu cộng và 1 loạt các dấu chấm chia cách các định danh theo ngay sau phiên bản bản vá hoặc tiền phát hành. Các định danh phải bao gồm chỉ các ký tự và gạch nối ASCII [0-9A-Za-z-]. Các định danh không được phép rỗng. Siêu dữ liệu xây dựng nên được loại bỏ khi xác định phiên bản ưu tiên. Vì thế 2 phiên bản chỉ khác nhau khi xây dựng siêu dữ liệu, và có cùng độ ưu tiên. Ví dụ: 1.0.0-alpha+001, 1.0.0+20130313144700, 1.0.0-beta+exp.sha.5114f85.

Độ ưu tiên dùng để so sánh các phiên bản với nhau khi sắp xếp. Độ ưu tiên phải được tính toán bằng cách chia phiên bản thành các định danh lớn, nhỏ, vá và trước khi phát hành theo thứ tự. (xây dựng các siêu dữ liệu không được tính cho độ ưu tiên) Độ ưu tiên được xác định bằng sự khác nhau đầu tiên khi so sánh mỗi định dang từ trái qua phải như sau: Các phiên bản lớn, nhỏ và vá luôn được so sánh bằng số. Ví dụ 1.0.0 < 2.0.0 < 2.1.0 < 2.1.1. Khi bản lớn, nhỏ và vá bằng nhau, phiên bản tiền phát hành có độ ưu tiên thấp hơn phiên bản bình thường. Ví dụ 1.0.0-alpha < 1.0.0. Độ ưu tiên cho 2 phiên bản tiền phát hành với cùng phiên bản lớn, nhỏ và vá phải được xác định bằng cách từng dấu chấm chia cách các định danh từ trái quá phải cho đến khi có 1 sự các biệt được tìm thấy như sau : các định danh chỉ bao gồm các chữ số được so sánh số học và các định danh với các chữ và các dấu nối được so sánh theo từ vựng theo thứ tự sắp xếp ASCII. Các định danh số học luôn có độ ưu tiên thấp hơn các định danh không phải số. 1 tập các trường tiền phát hành có độ ưu tiên cao hơn các tập nhỏ, nếu tất cả các định danh phía trước là bằng nhau. Ví dụ : 1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-alpha.beta < 1.0.0-beta < 1.0.0-beta.2 < 1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0.

##Tại sao phải sử dụng Semantic Versioning?
Đây không phải là 1 ý kiến mới hay đột phá nào cả. Trên thực tế, bạn đã làm điều gì gần giống như vậy rồi. Vấn đề là "gần giống" ở đây không đủ tốt. Nếu không tuân thủ theo 1 tập các đặc điểm kỹ thuật chính thức, các số phiên bản thực chất sẽ vô nghĩa cho việc quản lý sự phụ thuộc. Bằng cách đưa các định nghĩa rõ ràng cho các ý tưởng trên, nó trở nên dễ dàng trong việc liên kết các ý tưởng của bạn tới các người dùng phần mềm. Ngay khi những ý tưởng trở lên rõ ràng, Các đặc điểm kỹ thuật linh động phụ thuộc(nhưng không quá linh động) cuối cùng cũng được hình thành.

1 ví dụ đơn giản mô tả cách Semantic Versioning có thể tạo sự phụ thuộc giữa những thứ kinh khủng trong quá khứ. Xem xét 1 thư viện tên là "Filetruck". Nó yêu cầu 1 gói Semantically Versioned gọi là "Ladder". Tại thời điểm Firetruck được tạo ra, Ladder lúc đó đang ở phiên bản 3.1.0. Từ khi Firetruck sử dụng 1 vài chức năng được giới thiệu lần đầu trong phiên bản 3.1.0, bạn có thể đặc tả 1 cách an toàn các phụ thuộc Ladder tốt hơn hay bằng so với 3.1.0 nhưng tệ hơn so với 4.0.0. Bây giờ khi Ladder ở phiên bản 3.1.1 và 3.2.0 khả dụng, bạn có thể phát hành chúng tới các hệ thống quản lý gói (package) và biết rằng chúng sẽ tương thích với các phụ thuộc phần mềm hiện tại.

Tất nhiên. là 1 lập trình viên tin cậy, bạn sẽ muốn xác thực rằng bất kỳ cập nhật gói nào cũng sẽ có chức năng như quảng cáo. Thế giới thực là 1 nơi lộn xộn, bạn sẽ không thể làm gì về nó nhưng bạn có thể thận trọng. Những gì bạn có thể làm là khiến Semantic Versioning cung cấp cho bạn theo cũng cách trong việc phát hành và cập nhật gói mà không phải chuyển tới 1 phiên bản mới của các gói phụ thuộc, giúp bạn tiết kiệm thời gian và tránh các rắc rối.

Điều này có vẻ nghe như mong muốn, tất cả những gì bạn cần làm là bắt đầu sử dụng Semantic Versioning để khai báo rằng bạn đang làm như thể và sau đó tuân theo các luật. Liên kết trang web này từ README cả bạn để những người khác biết luật và có thể tận dụng chúng.
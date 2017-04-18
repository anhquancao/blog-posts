## Sử dụng biến trong CSS

Những website lớn thường sẽ sử dụng rất nhiều CSS với lượng lớn giá trị bị lặp lại. Giả sử khi bạn muốn sửa màu chủ đạo của website thì rất có khả năng bạn sẽ phải sửa ở rất nhiều vị trí ví dụ như button, navbar, title,.... Điều này gây ra rất  nhiều khó khăn khi code cũng như khi bảo dưởng và duy trì website. 

Để giải quyết vấn đề này chúng ta có thể sử dụng **CSS pre-processing: SASS, LESS**. Tuy nhiên, với cách này các bạn sẽ cần thêm 1 bước complile độc lập, đồng thời cần phải bỏ thời gian ra học và tìm hiểu về chúng và một điều rất quan trọng là các bạn sẽ không thể sử dụng javascript để update các giá trị css. 

Trong bài viết này mình sẽ giới thiệu cho các bạn 1 cách đơn giản hơn đó là **biến trong css** không cần bước compile độc lập đồng thời các bạn hoàn toàn có thể thay đổi các **giá trị css bằng javascript**. 

Tuy nhiên, có 1 lưu ý đây vẫn đang là **tính năng thử nghiệm** nên khi sử dụng các bạn cần lưu ý xem browser mà các bạn develope cho có hỗ trợ không. Các bạn có thể xem ở trang này:
https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables#Browser_compatibility

## Sử dụng
https://gist.github.com/caoquan95/16dae13b94b20a59edf37112396c6d31

Các bạn lưu ý, **tất cả biến trong css** khi khai báo đều cần có **hai dấu gạch ngang "--" ở phía trước** .
Khi lấy giá trị của biến ra thì các bạn dùng cấu trúc **"var(tên biến)"**.

## Ví dụ 1: Sử dụng javascript để thay đổi giá trị biến
https://gist.github.com/caoquan95/a3783d90e050bf6bcf8c75c0e869eedb
Trong ví dụ trên, màu của tất cả phần tử class **red** đều được set theo biến **--main-color**. Khi bạn muốn đổi màu thì chỉ cần thay đổi giá trị của biến **--main-color**.

Bạn có thể thay đổi giá trị biến **--main-color** thành **"blue"** bằng javascript như sau:
https://gist.github.com/caoquan95/9aac5020ca16baf22c8895f8d6f884c1

## Tính kế thừa của biến CSS
https://gist.github.com/caoquan95/84360143f592e82f5367480c7b364b71
Trong ví dụ trên:

- Đối với **class="child1"**: color = **green** mà không phải là **blue** do giá trị này được define trong class="child1"
- Đối với **class="child2"**: color=**blue** do thừa hưởng từ **class="parent"**
- Đối với **class="grand-parent"**: biến **--color** không tồn tại do biến này chỉ được define trong các phần tử con.

## Giá trị mặc định
Các bạn có thể define **giá trị mặc định** khi mà **biến không tồn tại** như sau:
https://gist.github.com/caoquan95/d4a800bb62ab01f9632a61fb337dfd26

Cám ơn bạn đã đọc bài viết. Hãy kipalog nếu bài viết bổ ích với bạn. Nếu mình có nhầm lẫn hoặc bạn có ý kiến đóng góp, xin vui lòng comment ở bên dưới.

##Nguồn tham khảo
https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables#Browser_compatibility

QuanCao 15-04-2017
## Javascript Closure

**Closure** là một hàm (function), trong hàm đó có sử dụng những **biến độc lập** (là biến được sử dụng locally trong hàm nhưng lại được khai báo ở ngoài hàm(function)).
Các bạn cũng có thể hiểu nôm na: **Closure** là những hàm có khả năng ghi nhớ môi trường mà chúng được tạo ra. 

```Closure = Hàm + Lexical Scope mà hàm đó được tạo ra ```

Bạn có thể tìm hiểu thêm về scope tại đây: [Block Scope vs Lexical Scope](https://kipalog.com/posts/Lexical-Scope-va-Block-Scope-trong-javascript)

###Ví dụ 1: 
https://gist.github.com/caoquan95/b6a8a3f94a14e547ec04d4be246f637c

Ở trong ví dụ trên, hàm **inner()** sử dụng biến **bar** được define ở scope (Các bạn có thể đọc bài sau để hiểu về [scope](https://kipalog.com/posts/Lexical-Scope-va-Block-Scope-trong-javascript)) bên ngoài hàm **inner()**. Do đó, hàm **inner()** chính là một closure.

###Ví dụ 2
https://gist.github.com/caoquan95/eac5eed10efb2c24bbef7f4ea0ae4077
Điều thú vị trong ví dụ 2 này là hàm **sayHello()** bên trong được trả về bởi hàm **createFunction()** bên ngoài trước khi được chạy.

Thoạt nhìn, có khả năng cao là **đoạn code trên**  sẽ lỗi khi chạy. Trong một số ngôn ngữ lập trình, biến **cục bộ (local)** sẽ chỉ tồn tại trong khoảng thời gian mà **hàm** được chạy. Một khi hàm **createFunction()** chạy kết thúc, nhiều bạn sẽ nghĩ rằng biến **greet** sẽ không còn tồn tại do nó là **biến cục bộ** trong hàm **createFunction()**. 

Tuy nhiên, điều này lại **không đúng** với Javascript. Đoạn **code** trong ví dụ trên vẫn chạy bình thường. Nguyên nhân là do hàm **sayHello()** khi được trả về vẫn trỏ tới biến **greet**. 

Do đó, tạo thành một **Closure** (hàm **sayHello()** cộng với [lexical scope](https://kipalog.com/posts/Lexical-Scope-va-Block-Scope-trong-javascript) của hàm tạo ra nó **createFunction()**). biến **greet** sẽ vẫn tồn tại khi hàm **myFunction()** được gọi và **"hello"** sẽ được truyền vào alert.

### Ví dụ 3
https://gist.github.com/caoquan95/3121b10b7f98067e8737e5a05d509366
Trong ví dụ trên, chúng ta khai báo hàm **createMultiplier(x)** nhận vào biến **x** và trả về một **hàm mới**. Hàm này nhận vào biến y và trả về tích của x và y.

Ở trong ví dụ này, chúng ta có thể dễ dàng nhận ra hàm **mul(y)** là một **Closure** do nó trỏ tới biến **x** của hàm **createMultiplier(x)** ở bên ngoài.

Ở dòng 8 và 9, Xhúng ta tạo ra 2 hàm **mul10()** và **mul100()** một hàm nhân 10 và một hàm nhân 100 với giá trị truyền vào của nó. Hai hàm có chung **định nghĩa** (definition) nhưng lại có 2 môi trường riêng. Với hàm **mul10()**, x = 10. Còn hàm **mul100()**, x = 100. 

Cám ơn bạn đã đọc bài viết. Hãy **kipalog** nếu bài viết bổ ích với bạn. Nếu mình có nhầm lẫn hoặc bạn có ý kiến đóng góp, xin vui lòng comment ở bên dưới.

Một số nguồn tham khảo:
https://developer.mozilla.org/en/docs/Web/JavaScript/Closures


QuanCao 13-04-2017
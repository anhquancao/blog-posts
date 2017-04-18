#**Scope**
Trong javascript có 2 loại scopes: **lexical scope** và **block scope**

**Lexical scope** là không gian biến được khai báo ở trong **hàm (function)**. Từ khoá **“var”** được dùng để khai báo biến trong **lexical scope của hàm**. Ví dụ:

https://gist.github.com/caoquan95/7cb5bd07a0c1009e0631fb0869901f54

Ở ví dụ trên, biến **bar** được khai báo trong **lexical scope của hàm foo**.


**Block scope** là không gian biến được khai báo giữa **1 cặp dấu ngoặc nhọn “{…}”**. Từ khoá **“let"** và **“const"** được dùng để khai báo biến ở trong **block scope**. Ví dụ:
https://gist.github.com/caoquan95/997674e306286eeb515eaa4b408ecad8
Trong ví dụ trên, biến **“variable”** được khai báo trong **block scope** giữa hai dấu ngoặc nhọn **“{…}” của if**.

Một số ví dụ để các bạn hiểu rõ hơn về 2 loại scope **“block scope"** và **“lexical scope”**:

Ví dụ 1:
https://gist.github.com/caoquan95/5dfc887ba6a096e0d097bf227da820a5

Trong ví dụ trên biến **”bar” thứ 2** do có từ khoá khai báo **“var”** ở phía trước nên sẽ có nhiều bạn hiểu lầm là biến **“bar”** này sẽ không gây ảnh hưởng đến biến **"bar"** ban đầu.
Tuy nhiên, do **“var”** khai báo biến trong **lexical scope** (ở đây là function foo) như mình đã nói ở trên nên biến **“bar” thứ 2** sẽ được khai báo đè lên biến bar thứ nhất.
Do đó, kết quả trả về sẽ là giá trị của biến **“bar“ thứ 2 là 1**

Ví dụ 2:
https://gist.github.com/caoquan95/d9103d63465045c8237dc3d2c53ebd16

Ví dụ trên tương tự như ví dụ 1 nhưng sử dụng từ khoá **“let”** để khai báo thay vì từ khoá “var”.
Ở đây, biến **bar thứ 2** được khai báo **locally** trong **block scope** giữa 2 dấu ngoặc nhọn **"{...}" của if** do tác dụng của từ khoá **“let“** (**let** và **const** khai báo biến trong **block scope**). Do đó, giá trị của biến **“bar” đầu tiên** sẽ không bị ảnh hưởng và hàm này sẽ trả về giá trị của **biến bar đầu tiên là 2**.

Cám ơn bạn đã đọc bài viết. Hãy **like** nếu bài viết **bổ ích** với bạn. Nếu mình có nhầm lẫn hoặc bạn có ý kiến đóng góp, xin vui lòng **comment** ở bên dưới.

Một số nguồn tham khảo:
https://developer.mozilla.org/en/docs/Web/JavaScript/Closures#Lexical_scoping

QuanCao 12-04-2017
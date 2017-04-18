# Sử dụng **data attribute** trong HTML
Hôm nay trong lúc làm chức năng mới cho hệ thống [Color ME](http://colorme.vn/), mình có dùng lại **Data attribute** trong HTML, tiện thể mình làm bài blog chia sẻ về sử dụng thuộc tính này

## Cú pháp HTML

Tất cả mọi thuộc tính có tiền tố **Data-** đều là **Data attribute**. Data attribute sẽ giúp bạn lưu thêm thông tin vào thẻ html. Đặc biệt, **Data attribute** sẽ giúp các bạn có thể lấy được thông tin ra bằng javascript một cách nhanh chóng. Ví dụ:

```html
<element
    id="el"
    data-columns="12"
    data-name="foo"
</element>
```

## Cách lấy **Data attribute** bằng **Javascript**
Lấy dữ liệu ra trong từ **Data attribute** trong Javascript dễ như ăn bánh. Bạn hoàn toàn có thể dùng cách truyền thống là **getAttribute()** để lấy ra. Tuy nhiên, Bạn hoàn toàn có thể lấy ra bằng cách đơn giản như sau:

```js
var element = document.getElementById('el');

console.log(element.dataset.columns) // 12
console.log(element.dataset.name) // foo
```

Bạn hoàn toàn có thể set được giá trị **Data attribute** bằng cách sau:
```js
// Thay đổi giá trị thuộc tính data-columns = 20
element.dataset.columns = 20
```

## Truy cập **Data attribute** bằng CSS

**Data attribute** cũng hoạt động như mội attribute thông thường. Bạn có thể thay đổi css bằng **attribute selector** theo **data attribute** như sau:
```css
element[data-columns='10']{
    background:red;
}
element[data-columns='12']{
    background:green;
}
```

 Trong ví dụ sau, mình sẽ lấy giá trị trong **data attribute** và set vào trong nội dung của thẻ element như sau. 
```css
element:before {
    content: attr(data-name);
}
```
Bạn có thể tìm hiểu thêm về thuộc tính [content trong css ở đây](https://developer.mozilla.org/en-US/docs/Web/CSS/content)


**Cám ơn bạn** đã đọc bài viết. Nếu mình có nhầm lẫn hoặc bạn có ý kiến đóng góp, xin vui lòng comment ở bên dưới.
- Hãy **kipalog** nếu bài viết bổ ích với bạn. 
- Nhớ **theo dõi** mình để nhận được thông báo khi có bài viết mới

## Nguồn thao khảo
1. https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes
2. https://developer.mozilla.org/en-US/docs/Web/CSS/content
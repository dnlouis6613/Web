### Các kỹ thuật CSS: Với mỗi một thuộc tính key: value sẽ các nhau bằng dấu chấm phẩy

    + Inline CSS: viết trực tiếp trong thẻ HTML sử dụng thuộc tính style
    + Internal CSS: viết trong thẻ <style> trong phần <head>
    + External CSS: viết trong file .css riêng và liên kết vào file HTML sử dụng thẻ <link>. link:css.

- Thẻ dùng Inline CSS độ ưu tiên cao hơn Internal CSS.

### Thuộc tính CSS cơ bản

    key: value
    - key: tên thuộc tính (attribute)
    - value: giá trị thuộc tính
    Ví dụ: color: red; => thuộc tính color có giá trị là red ( thay đổi màu chữ thành màu đỏ)
    ngoài ra có các thuộc tính khác:
    background-color ( màu nền ),
    text-align ( căn lề chữ ),
    font-size ( cỡ chữ )...,
    width ( chiều rộng ): đơn vị px...
    height ( chiều cao ): đơn vị px...

### Display bao gồm block, inline, none, inline-block

    - block: chiếm toàn bộ chiều rộng của thẻ cha, xuống dòng
    - inline: chỉ chiếm đúng kích thước nội dung, không xuống dòng
    - none: ẩn thẻ
    - inline-block: kết hợp giữa block và inline

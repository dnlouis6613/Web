# Bài 3: CSS Box Model

## 1. Box Model là gì?

Trong CSS, mọi phần tử HTML đều được coi là một **hộp (box)**. Box Model mô tả cấu trúc của hộp đó, bao gồm **4 lớp** từ trong ra ngoài:

```
┌─────────────────────────────────────────┐
│              MARGIN (lề ngoài)           │
│  ┌───────────────────────────────────┐  │
│  │          BORDER (viền)            │  │
│  │  ┌───────────────────────────┐    │  │
│  │  │      PADDING (đệm)       │    │  │
│  │  │  ┌───────────────────┐   │    │  │
│  │  │  │                   │   │    │  │
│  │  │  │    CONTENT        │   │    │  │
│  │  │  │  (nội dung)       │   │    │  │
│  │  │  │                   │   │    │  │
│  │  │  └───────────────────┘   │    │  │
│  │  └───────────────────────────┘    │  │
│  └───────────────────────────────────┘  │
└─────────────────────────────────────────┘
```

### 1.1 Content (Nội dung)

- Là vùng chứa nội dung thực sự (chữ, ảnh, video...).
- Kích thước được xác định bởi `width` và `height`.

```css
div {
  width: 200px;
  height: 100px;
}
```

### 1.2 Padding (Phần đệm)

- Là khoảng trống **bên trong** viền, nằm giữa content và border.
- Padding trong suốt (transparent), nhận màu nền của phần tử.

```css
div {
  padding: 20px; /* tất cả 4 phía */
  padding-top: 10px; /* phía trên */
  padding-right: 15px; /* phía phải */
  padding-bottom: 10px; /* phía dưới */
  padding-left: 15px; /* phía trái */
  padding: 10px 15px; /* trên-dưới | trái-phải */
  padding: 10px 15px 20px; /* trên | trái-phải | dưới */
  padding: 10px 15px 20px 25px; /* trên | phải | dưới | trái (theo chiều kim đồng hồ) */
}
```

### 1.3 Border (Viền)

- Là đường viền bao quanh padding và content.

```css
div {
  border: 2px solid black; /* viết tắt: độ dày | kiểu | màu */
  border-width: 2px;
  border-style: solid; /* solid, dashed, dotted, double, none... */
  border-color: black;
  border-radius: 10px; /* bo góc */
}
```

### 1.4 Margin (Lề ngoài)

- Là khoảng trống **bên ngoài** viền, tạo khoảng cách giữa phần tử này với phần tử khác.
- Margin trong suốt, **không** nhận màu nền.

```css
div {
  margin: 20px; /* tất cả 4 phía */
  margin: 0 auto; /* căn giữa theo chiều ngang */
  margin-top: 10px;
  margin-right: auto;
  margin-bottom: 10px;
  margin-left: auto;
}
```

---

## 2. Cách tính kích thước thực tế

### Mặc định (`box-sizing: content-box`)

```
Chiều rộng thực tế = width + padding-left + padding-right + border-left + border-right
Chiều cao thực tế  = height + padding-top + padding-bottom + border-top + border-bottom
```

**Ví dụ:**

```css
div {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
}
/* Chiều rộng thực tế = 200 + 20 + 20 + 5 + 5 = 250px */
```

### Dùng `box-sizing: border-box` (KHUYẾN KHÍCH)

```css
div {
  box-sizing: border-box;
  width: 200px;
  padding: 20px;
  border: 5px solid black;
}
/* Chiều rộng thực tế = 200px (padding và border nằm BÊN TRONG width) */
```

> 💡 **Mẹo:** Luôn đặt đoạn code sau ở đầu file CSS:
>
> ```css
> * {
>   box-sizing: border-box;
> }
> ```

---

## 3. Margin Collapsing (Gộp margin)

Khi 2 phần tử block nằm chồng nhau theo chiều dọc, margin trên và margin dưới sẽ **gộp lại** thành 1 margin duy nhất (lấy giá trị lớn hơn).

```
Phần tử A: margin-bottom: 30px;
Phần tử B: margin-top: 20px;
=> Khoảng cách thực tế giữa A và B = 30px (KHÔNG phải 50px)
```

---

## 4. Một số thuộc tính hữu ích liên quan

| Thuộc tính                  | Mô tả                                                       |
| --------------------------- | ----------------------------------------------------------- |
| `width` / `height`          | Kích thước nội dung                                         |
| `min-width` / `max-width`   | Giới hạn chiều rộng                                         |
| `min-height` / `max-height` | Giới hạn chiều cao                                          |
| `overflow`                  | Xử lý nội dung tràn (`visible`, `hidden`, `scroll`, `auto`) |
| `box-shadow`                | Đổ bóng cho hộp                                             |

---

## 5. Bài tập thực hành

### Bài 1: Tạo thẻ profile đơn giản

Tạo một thẻ profile với:

- Chiều rộng 300px, căn giữa trang
- Padding 20px
- Border 2px solid màu xám (#ccc)
- Border-radius 10px
- Box-shadow nhẹ
- Bên trong có: ảnh avatar, tên, mô tả ngắn

### Bài 2: Tính kích thước thực tế

Cho đoạn CSS sau, hãy tính chiều rộng và chiều cao **thực tế** của phần tử:

```css
/* Câu a */
.box-a {
  width: 300px;
  height: 150px;
  padding: 25px;
  border: 3px solid blue;
  margin: 10px;
  /* box-sizing mặc định là content-box */
}

/* Câu b */
.box-b {
  box-sizing: border-box;
  width: 300px;
  height: 150px;
  padding: 25px;
  border: 3px solid red;
  margin: 10px;
}
```

**Đáp án:**

- Câu a: Rộng = 300 + 25×2 + 3×2 = **356px**, Cao = 150 + 25×2 + 3×2 = **206px**
- Câu b: Rộng = **300px**, Cao = **150px** (padding và border nằm trong width/height)
- Margin không tính vào kích thước phần tử, nhưng chiếm không gian trên trang.

### Bài 3: Tạo layout 3 cột

Tạo 3 hộp nằm cạnh nhau, mỗi hộp:

- Chiều rộng bằng nhau (dùng %)
- Có padding, border, margin khác nhau
- Sử dụng `box-sizing: border-box` để không bị vỡ layout

### Bài 4: Thực hành Margin Collapsing

Tạo 3 thẻ `<div>` xếp chồng lên nhau, thiết lập margin khác nhau và quan sát hiện tượng margin collapsing. Thử các cách sau để ngăn margin collapsing:

- Thêm `padding` hoặc `border` cho phần tử cha
- Dùng `overflow: hidden` cho phần tử cha
- Dùng `display: flex` cho phần tử cha

    POSITION:
    - static: Đây là giá trị mặc định của thuộc tính "position". Khi một phần tử có vị trí "static".

    - Có thể sử dụng 4 top, bottom, right, left chỉ static không sử dụng được
    - z-index: Chỉ sử dụng được với các phần tử có thuộc tính position là relative, absolute, fixed, sticky.
      Dùng để xác định thứ tự xếp chồng của các phần tử trên trang web.

    - relative: Khi một phần tử được đặt vị trí theo kiểu "relative",
    nó sẽ được di chuyển dựa trên vị trí ban đầu mà nó chiếm trên trang,
    và các phần tử khác vẫn sẽ giữ nguyên vị trí của mình

    - absolute: Khi sử dụng giá trị "absolute",
    phần tử được đặt vị trí tuyệt đối theo phần tử cha gần nhất mà có thuộc tính "position" không phải là "static".
    Điều này cho phép bạn đặt vị trí chính xác của một phần tử trong một phần tử khác,
    và điều chỉnh vị trí dựa trên các thuộc tính "top", "bottom", "left" và "right".

    - fixed: Khi sử dụng giá trị "fixed",
    phần tử sẽ được đặt vị trí cố định trên trình duyệt và không bị ảnh hưởng bởi cuộn trang.
    Điều này thường được sử dụng cho các phần tử như thanh menu hoặc tiêu đề nằm cố định trên trang web.

    - sticky: Khi sử dụng giá trị "sticky",
    phần tử sẽ được đặt vị trí "sticky" khi nó nằm trong vùng nhìn thấy của trình duyệt.
    Khi người dùng cuộn trang, phần tử sẽ giữ vị trí của nó cho đến khi nó chạm vào một điểm nhất định,
    sau đó nó sẽ trở thành "fixed" và giữ vị trí cố định trong vùng nhìn thấy của trình duyệt.

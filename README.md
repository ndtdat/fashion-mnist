# PHÂN LOẠI DỮ LIỆU TRÊN TẬP FASHION-MNIST
## Mô tả tập dữ liệu
- Tập dữ liệu chứa 70000 ảnh grayscale với kích thước 28x28 (pixel). Trong đó, tập train chứa 60000 ảnh và tập test 10000 ảnh.
- Tập dữ liệu có 10 lớp khác nhau [number_label name_label]: 
    - 0 T-shirt/top.
    - 1 Trouser.
    - 2 Pullover.
    - 3 Dress.
    - 4 Coat.
    - 5 Sandal.
    - 6 Shirt.
    - 7 Sneaker.
    - 8 Bag.
    - 9 Ankle boot.
## Hướng tiếp cận truyền thống
### Support Vector Machine (SVM)
- SVM dùng để phân lớp dữ liệu nhị phân (tức chỉ có hai lớp).
- Giải quyết bài toán 10 lớp với chiến lược one-vs-rest để xử lý 10 lớp cho bài toán này.
- Kết quả đạt được với độ chính xác accuracy khá cao: **89.21%**
### Kết hợp Principle Component Analysis (PCA)
- Dữ liệu ban đầu có 784 chiều, có thể gây ra việc khái quát hóa không tốt cho mô hình.
- Sử dụng PCA để rút gọn lại còn 300 chiều (chưa đến 50% so với ban đầu).
- Áp dụng SVM đối với dữ liệu đã xử lý PCA.
- Kết quả đạt được với độ chính xác accuracy nhỉnh hơn một chút: **89.74%**
## Hướng tiếp cận mạng tích chập
- Ngày nay, sự phát triển của của mạng tích chập cho thấy việc khái quát trở nên hiệu quả và đem lại cho hệ thống hiệu suất làm việc cao hơn.
- Với cách tiếp cận bằng SVM ta thấy được rằng vẫn còn phải tối ưu hơn nữa. Trước đó ta đã sử dụng kết hợp PCA nhưng kết quả không mấy khả quan so với kỳ vọng.
- Kiến trúc mạng CNN được thiết kế như sau:
![CNN-Architecture](https://github.com/tiendat3550/fashion-mnist/blob/main/CNN-Architecture.PNG)

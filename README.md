# Dự Đoán Giá Cổ Phiếu với Mô Hình LSTM

## Giới Thiệu
Dự án này tập trung vào việc dự đoán biến động giá cổ phiếu trong tương lai bằng cách sử dụng mô hình học sâu LSTM (Long Short-Term Memory). LSTM là một loại mạng nơ-ron hồi quy (RNN) có khả năng xử lý dữ liệu chuỗi thời gian hiệu quả, giúp nắm bắt các xu hướng và mẫu dữ liệu trong quá khứ để dự báo tương lai.

## Tiền Xử Lý Dữ Liệu
Bộ dữ liệu bao gồm giá cổ phiếu theo từng khoảng thời gian (phút, giờ hoặc ngày). Các bước xử lý dữ liệu gồm:
- Tải dữ liệu từ nguồn (CSV hoặc API).
- Chuẩn hóa dữ liệu bằng phương pháp StandardScaler.
- Chia dữ liệu thành tập huấn luyện và kiểm tra.
- Chuyển đổi dữ liệu thành định dạng phù hợp cho mô hình LSTM (tạo cửa sổ thời gian cho dữ liệu đầu vào).
Giá đóng cửa (theo thời gian) của cổ phiếu FPT
![image](https://github.com/user-attachments/assets/c3b5d6ac-7d43-4b77-892d-b392b5faee10)

## Mô Hình LSTM
Mô hình dự báo sử dụng kiến trúc LSTM với các thành phần chính:
- **Lớp LSTM**: Trích xuất thông tin từ chuỗi thời gian.
- **Lớp Dropout**: Giảm overfitting bằng cách bỏ qua một số nơ-ron trong quá trình huấn luyện.
- **Lớp Dense**: Dự đoán giá cổ phiếu tương lai.
- **Hàm mất mát**: Sử dụng MSE (Mean Squared Error) để đánh giá độ chính xác của mô hình.

## Dự Đoán
Sau khi huấn luyện, mô hình có thể dự đoán giá cổ phiếu trong tương lai bằng cách:
1. Nhập dữ liệu giá cổ phiếu gần nhất.
2. Tiền xử lý dữ liệu theo chuẩn đã sử dụng trong huấn luyện.
3. Đưa dữ liệu vào mô hình LSTM để dự báo giá cổ phiếu trong khoảng thời gian tiếp theo.
4. Tính biến động giá bằng cách lấy hiệu giữa giá dự báo và giá hiện tại.
Dự đoán giá và chênh lệch giá
![image](https://github.com/user-attachments/assets/f15f6c6f-0783-438c-8b8c-c9feb8daeb77)

## Kết Luận
Dự án này sử dụng LSTM để dự đoán giá cổ phiếu trong tương lai dựa trên dữ liệu chuỗi thời gian. Mô hình có thể được cải thiện bằng cách thử nghiệm các tham số khác nhau, tăng kích thước dữ liệu huấn luyện, hoặc kết hợp thêm các yếu tố ảnh hưởng khác như tin tức tài chính.



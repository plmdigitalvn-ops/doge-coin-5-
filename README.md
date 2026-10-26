# 🐕 Doge Tracker

Trang web một file (HTML/CSS/JS thuần, không cần build; three.js nạp từ cdnjs) theo dõi giá **Dogecoin** theo thời gian thực và hiển thị dự báo thống kê 24 giờ, 3 ngày, 7 ngày.

## Tính năng
- Đồng xu Dogecoin 3D (three.js) xoay theo chuột, lật lại mỗi lần giá cập nhật; thẻ kính mờ nghiêng 3D khi rê chuột
- Toàn cảnh thị trường: tổng vốn hóa, khối lượng, độ thống trị BTC/ETH, chỉ số Sợ hãi & Tham lam, top 10, tăng/giảm mạnh nhất, coin đang được tìm kiếm nhiều
- Giá hiện tại, thay đổi 1 giờ / 24 giờ / 7 ngày, vốn hóa, khối lượng, đỉnh mọi thời đại
- Tự làm mới mỗi 60 giây; lưu cache cục bộ phòng khi bị giới hạn API
- Biểu đồ canvas: lịch sử 24 giờ / 7 ngày / 30 ngày kèm đường dự báo và vùng tin cậy 80%
- Chỉ báo RSI(14), EMA 12/26 và xu hướng 3 ngày
- Chuyển USD / VND, chuyển nhanh sang BTC, ETH, SHIB, SOL

## Chạy thử
Mở `index.html` bằng trình duyệt, hoặc chạy `python -m http.server` rồi vào `http://localhost:8000`.

## Đưa lên GitHub Pages
1. Tạo repo mới, ví dụ `doge-tracker`, rồi đẩy `index.html` và `README.md` lên nhánh `main`.
2. Vào **Settings → Pages**, chọn **Deploy from a branch**, nhánh `main`, thư mục `/ (root)`.
3. Sau ít phút, trang chạy tại `https://<tên-github>.github.io/doge-tracker/`.

## Cách dự báo
Hồi quy tuyến tính trên log-giá của 72 giờ gần nhất, giảm một nửa độ dốc để tránh ngoại suy quá đà, cộng khoảng tin cậy 80% từ độ biến động theo giờ của 7 ngày gần nhất (rộng dần theo căn bậc hai của thời gian). Đây chỉ là mô hình đơn giản mang tính tham khảo, **không phải lời khuyên đầu tư**.

## Lưu ý
Dữ liệu từ API miễn phí của [CoinGecko](https://www.coingecko.com/en/api) có giới hạn số request mỗi phút. Nếu cần lưu lượng lớn, hãy dùng API key riêng hoặc thêm một proxy nhỏ.

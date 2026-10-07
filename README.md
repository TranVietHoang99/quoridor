# 🧱 Quoridor

Game **Quoridor** (Mirko Marchesi, Gigamic) cho 2 người, chơi ngay trên trình duyệt: đưa quân về phía bên kia bàn, dùng tường để chặn đường đối thủ.

## Chế độ chơi
- **Chơi với máy**: nhập tên, bấm *Chơi với máy*.
- **Online 1 đấu 1**: bấm *Tạo phòng*, gửi mã hoặc link cho bạn bè; bạn bè nhập mã và bấm *Vào phòng*.
  Người tạo phòng phải **giữ tab mở**, vì máy chủ phòng giữ trạng thái ván chơi.

## Luật tóm tắt (bản 2 người)
- Bàn 9×9. Mỗi người 1 quân đặt giữa hàng cuối phía mình và 10 bức tường.
- Ai đưa quân tới bất kỳ ô nào ở hàng đối diện trước thì thắng.
- Mỗi lượt chọn một việc:
  - **đi quân** 1 ô lên/xuống/trái/phải, không xuyên tường;
  - **đặt 1 tường** dài 2 ô vào khe giữa các ô, ngang hoặc dọc. Tường không được chồng hoặc cắt chéo tường khác,
    và không được chặn kín mọi đường về đích của bất kỳ ai.
- Hai quân đứng sát nhau: được nhảy thẳng qua đối thủ. Nếu sau lưng đối thủ là tường hoặc mép bàn thì được nhảy chéo sang bên.

## Cách bấm
- Ô có chấm xanh là nơi quân bạn đi được.
- Rê chuột vào khe giữa các ô để xem trước tường (xanh = hợp lệ, đỏ = không hợp lệ), bấm để đặt.
- Trên điện thoại: chạm khe để xem trước, chạm lần nữa để đặt.
- Bật *Hiện đường ngắn nhất* để thấy đường đi ngắn nhất của hai quân.

## Kỹ thuật
Một file `index.html` duy nhất. Kết nối P2P bằng [PeerJS](https://peerjs.com/), cùng khung với Azul, Jaipur và Splendor Duel.
Máy dùng tìm kiếm negamax alpha-beta 5 nước, đánh giá theo chênh lệch đường ngắn nhất và số tường còn lại.
Chạy thử: `npx http-server quoridor -p 5187`.

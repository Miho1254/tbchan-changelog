# Complete Change log/Guide of Tóc Bạc-chan rewrite

## Items

> Xóa bỏ hệ thống túi đồ bằng `ô trống` &#8594; túi đồ theo `loại Item`.

<table>
    <thead>
        <tr>
            <th>Cũ</th>
            <th>Mới</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><img src='https://media.discordapp.net/attachments/811037489430528041/1006386612910964826/unknown.png' width="520"></td>
            <td><img src= "https://media.discordapp.net/attachments/856125690726580224/1009475916902170757/unknown.png" width="520"></img></td>
        </tr>
    </tbody>
</table>

> Sử dụng item
> Id số đã được thay bằng id chữ để tiện cho việc ghi nhớ.

Id chữ không yêu cầu bạn phải nhập chính xác từng chữ một, mà sẽ chọn lấy kết quả gần nhất với những gì bạn nhập.  
VD: bent => bentou

<table>
    <thead>
        <tr>
        	<th> </th>
            <th>Cũ</th>
            <th>Mới</th>
        </tr>
    </thead>
    <tbody>
        <tr>
        	<td> Cú pháp </td>
            <td><code>tbdungitem &#60;slot-trong-kho-đồ&#62; [tham số yêu cầu của item]</code></td>
            <td><code>tbdungitem  &#60;id-chữ>&#62; [tham số yêu cầu của item (nếu có)]</code></td>
        </tr>
        <tr>
        	<td> Ví dụ </td>
            <td>tbdungitem 12 @Miho</td>
            <td>tbdungitem c4 @Miho</td>
        </tr>
         <tr>
         <tr>
        	<td> Cú pháp </td>
            <td><code>tbmuaitem &#60;id-số&#62; [số lượng]</code></td>
            <td><code>tbmuaitem &#60;id-chữ&#62; [số lượng]</code></td>
        </tr>
         <tr>
        	<td> Ví dụ </td>
            <td>tbmuaitem 9</td>
            <td>tbmuaitem bentou</td>
        </tr>
        <tr>
        	<td>Minh hoạ</td>
            <td><img src='https://cdn.discordapp.com/attachments/811037489430528041/1006414635383140382/unknown.png' width="520"></td>
            <td><img src='https://media.discordapp.net/attachments/811037489430528041/1006421884646207518/unknown.png'></td>
        <tr>
    </tbody>
</table>

- ## Cải tiến `tham số` cho các lệnh

  - Cải tiến `cảnh báo` về các tham số bị thiếu hoặc tham số không hợp lệ.
  - Cải tiến `thông tin trực quan` về các tham số.
  - Cải tiến về `thông tin` và `tham só` của các lệnh.
  - Giao diện bớt `khô khan` hơn.
  - Sử dụng lệnh dễ dàng hơn vì có các `gợi ý` cho tham số.

## Clans
> Thay đổi hệ thống `invite` thành viên Clan mới và cải tiến nhiều `khuyết điểm` hiện có.

Hệ thống `invite member` mới như sau:

 <table>
    <thead>
        <tr>
            <th>Cũ</th>
            <th>Mới</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>owner, có thể mời member <br>thông qua tbguildadd</td>
            <td>chia thành nhiều status khác nhau<br>
            1 clan có thể có 1 trong 4 status:<br><br>
            - public: ai cũng có thể vào.<br><br>
            - restricted: member muốn vào phải gửi 1 'yêu cầu gia nhập' và đc chấp thuận bởi clan member với perm 'Administrator' hoặc 'ManageRequests'.<br><br>
            - protected: member phải nhập 1 'password' để vào.<br><br>
            - private: kín, ko ai có thể vào.</td>
        </tr>
        <tr>
            <td>test</td>
            <td>test</td>
        </tr>
    </tbody>
</table>

- ### Các thay đổi đáng chú ý khác 
    - Thay đổi tên từ `Guild` &#8594; `Clan` tránh xảy ra lỗi khi code.
    - Cải tiến giao diện và tận dụng `button` của Discord.
    - Loại bỏ `Co-owner` vì không cần thiết.

## Cải tiến và các tính năng mới
> những cải tiến hướng đến `sử dụng bot dễ hơn` cũng như loại bỏ 1 số `tính năng, yếu tố` không cần thiết trong quá trình sử dụng, phát triển.
  
  - Các item `vũ khí` nay đã được thay đổi và thêm các thuộc tính như `Crit, FailRate` và `Range` đổi mới trong sức công phá của item (mạnh hơn) và dọn đường cho 1 số `item bá đạo` trong tương lai.
  - `Khiên` hiện tại không còn phản đòn của các `Item bom` được nữa nhưng làm tỉ lệ `tạch` khi ném bom của người khác lên `100%`.
  - Tăng tiền khi ăn `gói hút ẩm` và tăng tiền thưởng khi `mời xoài`
  - Gộp sảnh `đếm số` thành `1 sảnh` nhưng `đếm số` nay đã vô hạn. 
  - Thay đổi từ `emoji` thành nút bấm trên 1 số lệnh cần nhiều trang như `tbxemitem`.
  - Hoàn tất sửa lỗi `rollback dữ liệu` và `lỗi database` bằng cách chuyển từ `Google API` sang `SQLITE`.
  - Bot không cần phải `save mỗi 3 tiếng` nữa lý do y như trên.  
  - Cải tiến nhận diện `link invite của server` và `link invite bên ngoài` cho TB-chan (tránh delete nhầm)
  - Cải tiến `Bad Words system` (từ tục tĩu) nay có thể phát hiện ra thêm 1 số dạng mới.
  - Sửa 1 số hạn chế của `tbtinh`, hiện tại đã có thể hỗ trợ sử dụng dấu `x và :` thay cho `* và /`.
  - Thêm `tbthongtinitem` để xem 1 số thông tin cơ bản về các item trong server.
  - Update thêm nhiều từ mới cho đoán từ tránh nhàm chán.
  - Cải tiến khóa chat giảm thiểu lỗi `khóa chat vĩnh viễn`.
  - Cải tiến `tbcaunguyen` trực quan hơn.
  - Bảng xếp hạng nay đã hiện vị trí của bạn kể cả khi bạn ngoài top 10 `VD: Kami: Hạng 54 bxh người giàu`.
  - Loại bỏ `combo` khi chơi `đoán từ`.
  - Bắt đầu áp dụng `timeout` vào việc điều hành và xử phạt trong server.
  - `tbtinh` nay đã hỗ trợ dấu `x và :` thay cho `* và /` Ví Dụ: `tbtinh 4x5:2`.
  - Cải tiến hệ thống `confession`.
  - Cải tiến hệ thống `dùng item` để phù hợp với hệ thống item mới.
  - `tbdich` đã chuyển thành `/dịch (SlashCommand)` để hỗ trợ nhiều ngôn ngữ và 1 số tính năng còn thiếu.
  - `điểm tình cảm` hiện đã `public` cho member song song với `cấp bậc`.
  - Hệ thống tự động mở gửi ảnh cho `everyone` ở sảnh chính đã được `tự động hóa` thay cho `staff`.
  - Bảng xếp hạng thay đổi từ `tbbxhtien`, `tbxhtc`, `tbbxhfan` &#8594; `tbbxh fan`, `tbbxh tc`, `tbbxh vote`, v.v... 
  - Thay đổi cách cơ chế minigame theo sảnh từ `chơi và đào` (tùy vào sảnh) thành `tbcauca` hay `tbdig`  
  (xem chi tiết thay đổi tại phần `about` của sảnh).
  - Xóa `tbguihen` do không cần thiết.
  - Bentou hiện tại sẽ được Tóc Bạc mời vào `đúng 0 phút lúc 8h sáng 12h trưa và 18h tối`.
  - Xóa 1 số danh mục không cần thiết trong `tbprofile`.
  - Hiện tại `dụng cụ trộm` không còn trộm được của người nghèo nữa.
  - Tăng tiền phạt khi sử dụng `dụng cụ trộm` &#8594; `tiền thưởng báo cảnh sát` cũng tăng.
  - Thay đổi `cách sử dụng` 1 số item.
  - 1 số thay đổi trong `cơ chế hoạt động` của `Cứt phát nổ` để phù hợp với inventory mới.

## Các tính năng dự kiến phát triển

    - Cập nhật hệ thống Anti-Ghost Ping (đang phát triển)
    - Hệ thống shop limited cho Clan (Đang Nghiên cứu)
    - Hệ thống daily quest cho Clan và Member (Đang nghiên cứu)
    - Hệ thống Boss tuần (Đang nghiên cứu)
    - Hệ thống bán, mua Clan (Đang phát triển)
    - Hệ thống Visual Novel cho Tóc Bạc-chan (Đang nghiên cứu)
    - Cải thiện hệ thống lịch sử hoạt động (Logs) cho staff (Đang phát triển)

## FAQ:
    - Bot có tính năng gì mới?
        Well, khá khó để bảo rằng bản update này thực sự có tính năng gì quá nổi bật và đáng chú ý,
        những gì mà chúng mình phát triển trong gần 1 tháng nay hướng tới sự ổn định cũng như là nền
        tảng để Tóc Bạc-chan có thể phát triển trong tương lai. Chúng mình đã đặt ra rất nhiều ý tưởng
        để phát triển trong thời gian tới nhưng nếu không có sự ủng hộ của các bạn thì có lẽ chúng mình
        đã không thể hoàn thiện được bản mới này.

    - Sao mình không thấy tính năng này tính năng nọ, bot cũ có mà?
        Như mình đã bảo, chúng mình khi tiến hành cải tiến bot đã lên danh sách những lệnh, tính năng
        không giá trị, vô dụng cần xóa. Do code lại 1 con bot vài chục nghìn dòng code trong nửa tháng
        là 1 thử thách khá căng nên chúng mình đã lên danh sách những tính năng chưa quá cần thiết hay
        ít người dùng và sẽ Update vào các bản vá/update trong các đợt sau để kịp cho sự kiện quốc khánh
        2/9 sắp tới đây.

    - Những cải tiến trên có thực sự cần thiết?
        Như hồi đầu hè mình có bảo với các bạn rằng hè này mình sẽ tập trung phát triển những tính năng
        mới nhưng dường như đó là 1 lời thất hứa. Nhưng bù lại chúng mình đã cải thiện toàn diện TB-chan
        để hướng đến 1 trải nghiệm thực sự ổn định như các bạn vốn phải có từ khi bot được tạo.

    - Dự định phát triển bot tương lai
        Như đã ghi ở mục trên, dự định tương lai chúng mình sẽ tập trung vào phát triển hệ thống Clans và
        nghiên cứu hệ thống Visual Novel tích hợp trong Tóc Bạc-Chan nhằm giúp member không có trải
        nghiệm nhàm chán khi sử dụng bot, ngoài ra chúng mình cũng đang dự định làm phong phú kho item
        của TB-chan và nghiên cứu phát triển thêm 1 số hệ thống RPG mới.
    
    - Mục tiêu phát triển Tóc Bạc-chan
        Tóc Bạc-chan theo mình thấy là 1 con bot private của WAMVN và không hỗ trợ nhiều server để tối ưu
        trải nghiệm của member tại server. Mục tiêu từ trước đến nay của chúng mình luôn là đặt member 
        của server lên hàng đầu. Trong tương lai chúng mình sẽ cố gắng biến WAMVN nói chung và Tóc Bạc
        nói riêng trở thành bot duy nhất tại Việt Nam có những tính năng và hệ thống độc quyền mà không
        server nào có. Chính vì thế chúng mình luôn cần các bạn trong việc phát triển TB-chan nói riêng
        và phát triển Discord World Anime/Manga Việt Nam nói chung ngày 1 đến nhiều người dùng hơn.

### `LƯU Ý:`

    Bản refactor này chưa thực sự hoàn chỉnh, các bản vá, update sẽ được lên kế hoạch cập nhật hằng ngày. Nếu phát hiện lỗi vui lòng liên hệ @Kami @Miho @NPGaming2971 hoặc đơn giản hơn là ping @Bot Operator hoặc mở ticket tại #report ticket.

    [Những gì mình vừa trình bày ở trên đã rất cụ thể. Vui lòng không mention các Bot Operator để hỏi thêm]
    [Các hành vi lạm dụng bug để trục lợi cá nhân sẽ bị xử lý theo quy định của server]


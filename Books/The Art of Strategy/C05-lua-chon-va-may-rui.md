# Chương 5 — Lựa chọn và may rủi (Choice and Chance)

**Nguồn:** Avinash K. Dixit và Barry J. Nalebuff, *The Art of Strategy: A Game Theorist's Guide to Success in Business and Life*, ấn bản đầu (W. W. Norton, 2008), Phần II, Chương 5.
**Tác giả:** Avinash K. Dixit (sinh 1944), nhà kinh tế Mỹ gốc Ấn, giáo sư danh dự Đại học Princeton; Barry J. Nalebuff (sinh 1958), giáo sư Trường Quản trị Yale. Cuốn sách kế thừa *Thinking Strategically* (1991) của cùng hai tác giả.
**Vị trí trong lập luận của cả cuốn sách:** Phần I đã xây bộ công cụ cơ bản: suy luận ngược cho trò chơi tuần tự (Chương 2), thế lưỡng nan của người tù (Chương 3) và cân bằng Nash cho trò chơi đồng thời (Chương 4). Chương 4 ngầm giả định mỗi người chơi chọn hẳn một phương án. Chương 5, chương mở đầu Phần II, xử lý những trò chơi mà cách làm đó thất bại: không có cặp phương án nào là cân bằng, vì hễ một bên bị đoán trước là bên kia khai thác được. Lời giải là chiến lược hỗn hợp, tức chọn ngẫu nhiên theo tỷ lệ tính toán trước. Chương này cũng mở rộng khái niệm cân bằng Nash sang chiến lược hỗn hợp và nối với định lý minimax của von Neumann. Chương 6 (Strategic Moves) và Chương 7 (Making Strategies Credible) đi theo hướng ngược lại: thay vì giấu nước đi của mình, người chơi chủ động thay đổi trò chơi bằng cam kết, đe doạ và hứa hẹn.
**Ý chính:** Hai tác giả muốn người đọc hiểu rằng trong trò chơi xung đột thuần tuý, nếu để đối thủ biết trước lựa chọn của mình là bất lợi, thì cách tốt nhất là hành động ngẫu nhiên một cách có tính toán. Tỷ lệ pha trộn tốt nhất là tỷ lệ khiến đối thủ chọn phương án nào cũng thu được như nhau, nên họ không khai thác được mình. Ví dụ trung tâm là quả phạt đền trong bóng đá, với số liệu thật từ các giải hàng đầu Ý, Tây Ban Nha, Anh giai đoạn 1995–2000: cầu thủ sút nên sút về phía không thuận 38,3% số lần, thủ môn nên bay về phía đó 41,7% số lần, và tỷ lệ ghi bàn khi đó là 79,6%; các cầu thủ thật làm gần đúng như vậy. Từ đó chương bàn về oẳn tù tì, thí nghiệm trong phòng thí nghiệm, cách tạo ra sự ngẫu nhiên, chiến lược hỗn hợp trong trò chơi vừa xung đột vừa có lợi ích chung, và các ứng dụng trong kinh doanh: phiếu giảm giá của Coke và Pepsi, kiểm tra ngẫu nhiên đồng hồ đỗ xe, xét nghiệm ma tuý, tên lửa mồi nhử.

> **Lưu ý:** Sách viết khoảng 2007–2008; số liệu phạt đền lấy từ giai đoạn 1995–2000, giải vô địch oẳn tù tì thế giới được nhắc là giải năm 2005, trận tứ kết World Cup Anh – Bồ Đào Nha là năm 2006. Một số điều đã thay đổi: luật bóng đá từ khoảng năm 2019 cho phép thủ môn khi bắt phạt đền chỉ cần giữ một phần một bàn chân trên vạch vôi, không còn phải đứng hẳn trên vạch như sách mô tả; các cơ quan thuế Mỹ trong thập niên 2010 còn giảm tỷ lệ kiểm tra hơn nữa, làm điểm phê phán của hai tác giả về chiến lược kiểm tra của IRS càng đúng. Chương có **3 chú thích chân trang** của tác giả, đã đưa vào đúng chỗ (câu chuyện Vizzini ở mục 1, quả phạt đền ở mục 2, tình huống Janken ở mục 11) và ghi rõ "Chú thích của tác giả". Sách có một chỗ tính xác suất mô tả không khớp với con số (ví dụ Coke và Pepsi, xem mục 9 và phần Đánh giá). Các bảng kết quả và đồ thị được dựng lại từ sách. Các câu trích là bản dịch của người tổng hợp.

## Sơ đồ

### Tiểu mục "Wit's End" — bí đường suy luận (Vizzini và hai chén rượu độc)

```text
       Phim The Princess Bride: người hùng Westley thách kẻ ác Vizzini
       · Westley bỏ thuốc độc vào một trong hai chén rượu, Vizzini không
         nhìn thấy
       · Vizzini chọn uống một chén, Westley phải uống chén còn lại
                                │
                                ▼
       Vizzini tự cho mình thông minh, cố suy luận ra chén có độc:
       · người khôn sẽ bỏ độc vào chén của chính mình, vì chỉ kẻ ngốc mới
         lấy chén được đưa cho mình → vậy tôi không lấy chén trước mặt anh
       · nhưng anh biết tôi không ngốc, nên đã tính tới điều đó → vậy tôi
         cũng không lấy chén trước mặt tôi ... và cứ thế xoay vòng
                                │
                                ▼
       Vizzini đánh lạc hướng Westley, tráo chén, cười đắc thắng, uống
       rồi ngã chết
                                │
                                ▼
       Vì sao suy luận thất bại? Mỗi lập luận tự mâu thuẫn:
       · nếu Vizzini đoán độc ở chén A thì chọn B; Westley đoán được điều
         đó nên bỏ độc vào B; Vizzini đoán được nữa nên chọn A ... vô tận
       · Chú thích của tác giả: thật ra Westley đã tập kháng độc nhiều năm
         và bỏ độc vào CẢ HAI chén; Vizzini thua vì thiếu thông tin. Bài
         học phụ: khi ai đó đề nghị một trò chơi hay giao dịch, hãy hỏi
         "họ biết điều gì mà mình không biết?"
                                │
                                ▼
       Vòng luẩn quẩn này gặp ở nhiều trò chơi, ví dụ quả phạt đền:
       · có lý do để sút trái → thủ môn đoán được → nên sút phải → thủ môn
         đoán sâu thêm một bậc → lại nên sút trái ...
                                │
                                ▼
       Kết luận logic duy nhất đứng vững: nếu lựa chọn của bạn theo một
       quy luật nào đó, đối thủ sẽ khai thác nó
       → bạn phải khiến đối thủ phải đoán, bằng cách chọn NGẪU NHIÊN ở mỗi
         lần; giá trị của sự ngẫu nhiên tính được bằng con số
```

### Tiểu mục "Mixing It Up on the Soccer Field" — pha trộn trên sân bóng (Phần 1: luật chơi và bảng kết quả)

```text
       Luật phạt đền: khung thành rộng 8 yard (khoảng 7,3 m), cao 8 feet
       (khoảng 2,4 m); bóng đặt cách vạch vôi 12 yard (khoảng 11 m)
       · thủ môn phải đứng trên vạch vôi, giữa khung thành, đến khi bóng
         được sút
       · bóng sút tốt bay tới khung thành trong 0,2 giây → thủ môn phải
         quyết định bay bên nào TRƯỚC khi thấy hướng bóng
       · cầu thủ sút cũng phải quyết định trước khi thấy thủ môn nghiêng
         về đâu → đây là trò chơi đồng thời
                                │
                                ▼
       Đơn giản hoá: mỗi bên chỉ có hai lựa chọn, Trái và Phải
       · "Phải" là phía thuận của cầu thủ sút (người thuận chân phải sút
         bằng má trong thì tự nhiên đưa bóng về phía tay phải thủ môn)
       · kết quả của cầu thủ sút đo bằng % số lần ghi bàn; của thủ môn đo
         bằng % số lần không thủng lưới
                                │
                                ▼
       Số liệu Ignacio Palacios-Huerta, giải Ý, Tây Ban Nha, Anh 1995–2000
       (% ghi bàn của cầu thủ sút; thủ môn được 100 trừ con số này)
                         Thủ môn Trái     Thủ môn Phải
       Sút Trái              58               95
       Sút Phải              93               70
                                │
                                ▼
       Tìm cân bằng Nash trong các lựa chọn thuần tuý: KHÔNG có
       · (Trái, Trái): cầu thủ đổi sang Phải, tăng từ 58 lên 93
       · (Phải, Trái): thủ môn đổi sang Phải, tăng từ 7 lên 30
       · (Phải, Phải): cầu thủ đổi sang Trái; rồi thủ môn đổi sang Trái
       → vòng đổi qua đổi lại giống hệt vòng suy luận của Vizzini
       → cần thêm một loại chiến lược mới: chiến lược hỗn hợp (mixed
         strategy); Trái, Phải gọi là chiến lược thuần tuý (pure strategy)
                                │
                                ▼
       Trò chơi xung đột thuần tuý: tổng bằng không (zero-sum) hay tổng
       không đổi (constant-sum, ở đây hai bên luôn cộng lại bằng 100)
       · trong thực tế loại này hiếm: thương mại tự nguyện thì cả hai
         thắng, thế lưỡng nan của người tù thì cả hai thua
       · với trò chơi này, bảng chỉ cần ghi kết quả của người chơi hàng;
         người chơi cột muốn con số NHỎ
```

### Tiểu mục "Mixing It Up on the Soccer Field" (Phần 2: tìm tỷ lệ pha trộn tốt nhất)

```text
       Cầu thủ sút chọn một chiến lược thuần tuý:
       · sút Trái → thủ môn chặn Trái, giữ tỷ lệ ghi bàn ở 58%
       · sút Phải → thủ môn chặn Phải, giữ ở 70% → tốt hơn trong hai cách
                                │
                                ▼
       Pha trộn 50:50 (tung đồng xu giấu trong lòng bàn tay):
       · nếu thủ môn bay Trái: 1/2 × 58 + 1/2 × 93 = 75,5%
       · nếu thủ môn bay Phải: 1/2 × 95 + 1/2 × 70 = 82,5%
       → thủ môn bay Trái, giữ ở 75,5%, vẫn hơn 70%
                                │
                                ▼
       Phép thử nhanh: để đối thủ biết trước lựa chọn của mình có hại
       không? Nếu có hại, sự ngẫu nhiên có giá trị
                                │
                                ▼
       Pha trộn 40:60 (mở ngẫu nhiên một trang sách nhỏ; số trang tận cùng
       từ 1 đến 4 thì sút Trái, từ 5 đến 0 thì sút Phải):
       · gặp thủ môn Trái: 0,4 × 58 + 0,6 × 93 = 79%
       · gặp thủ môn Phải: 0,4 × 95 + 0,6 × 70 = 80% → được ít nhất 79%
                                │
                                ▼
       Khoảng chênh thu hẹp dần: 93 với 70 → 82,5 với 75,5 → 80 với 79
       → tỷ lệ tốt nhất làm cho thủ môn bay bên nào cũng như nhau
       · cầu thủ sút: Trái 38,3%, Phải 61,7% → 79,6% trong cả hai trường hợp
       · thủ môn: Trái 41,7%, Phải 58,3% → giữ cầu thủ ở 79,6%
                                │
                                ▼
       Hai con số 79,6 trùng nhau KHÔNG phải ngẫu nhiên: định lý minimax
       của John von Neumann (sau viết cùng Oscar Morgenstern trong
       Theory of Games and Economic Behavior, cuốn sách khai sinh lý
       thuyết trò chơi)
       · một bên cố làm nhỏ nhất mức tối đa của đối thủ (minimax), bên kia
         cố làm lớn nhất mức tối thiểu của mình (maximin) → hai mức bằng
         nhau
       · Chú thích của tác giả: thủ môn "biết trước" lựa chọn của bạn có
         thể vì bạn mang tiếng "luôn sút Trái" hay "luôn sút Phải"
```

### Tiểu mục "Theory and Reality" — lý thuyết và thực tế, và Quy tắc 5

```text
       So sánh tỷ lệ chọn Trái tốt nhất (lý thuyết) với thực tế:
       · cầu thủ sút: tốt nhất 38,3%, thực tế 40,0% (ghi bàn 79,0 và 80,0)
       · thủ môn: tốt nhất 41,7%, thực tế 42,3% (để thủng 79,3 và 79,7)
       → rất gần; hầu như đối thủ không khai thác được
       · bằng chứng tương tự từ các trận quần vợt chuyên nghiệp hàng đầu
       · lý do: cùng người gặp nhau nhiều lần, nghiên cứu nhau, tiền cược
         và danh tiếng lớn → mọi quy luật dễ thấy đều bị khai thác
                                │
                                ▼
       QUY TẮC 5: trong trò chơi xung đột thuần tuý, nếu để đối thủ thấy
       trước lựa chọn của mình là bất lợi, hãy chọn ngẫu nhiên giữa các
       chiến lược thuần tuý; tỷ lệ pha trộn phải khiến đối thủ chọn chiến
       lược thuần tuý nào cũng không khai thác được mình
                                │
                                ▼
       Khi cả hai cùng theo Quy tắc 5, không ai lợi khi đổi cách chơi
       → đó là cân bằng Nash trong chiến lược hỗn hợp
       · định lý minimax chỉ đúng cho trò chơi hai người tổng bằng không;
         cân bằng Nash dùng được cho mọi số người chơi và mọi mức pha trộn
         giữa xung đột và lợi ích chung
                                │
                                ▼
       Không phải trò chơi tổng bằng không nào cũng cần pha trộn
       · nếu sút Trái chỉ thành công 38% (thủ môn đoán đúng) và 65% (đoán
         sai), còn sút Phải vẫn 93 và 70, thì sút Phải là chiến lược trội
       · cân bằng thuần tuý là trường hợp đặc biệt của pha trộn (100%)
```

### Tiểu mục "Child's Play" — trò chơi trẻ con (oẳn tù tì)

```text
       23/10/2005: Andrew Bergel (Toronto) vô địch giải Oẳn tù tì Quốc tế
       của Hiệp hội RPS Thế giới; Stan Long (Newark, California) huy
       chương bạc; Stewart Waldman (New York) huy chương đồng
                                │
                                ▼
       Luật: hai người cùng lúc ra Búa (nắm tay), Bao (bàn tay xoè ngang)
       hoặc Kéo (hai ngón); Búa đập Kéo, Kéo cắt Bao, Bao trùm Búa
       · luật của hiệp hội quy định chính xác hình dạng bàn tay (chống ăn
         gian) và trình tự ra tay để hai người ra đồng thời
                                │
                                ▼
       Thắng 1, thua –1, hoà 0 → trò chơi tổng bằng không
       · ra cố định một thứ → đối thủ luôn thắng, bạn được –1
       · ra mỗi thứ 1/3 → (1/3)×1 + (1/3)×0 + (1/3)×(–1) = 0 với mọi
         cách ra của đối thủ → cân bằng Nash trong chiến lược hỗn hợp
                                │
                                ▼
       Nhưng phần lớn người chơi giải KHÔNG làm thế; hiệp hội gọi cách
       1/3 là "Lối chơi Hỗn loạn" và khuyên tránh, vì con người không ra
       ngẫu nhiên thật mà rơi vào khuôn mẫu vô thức
       · các "nước gài": Quan liêu (ba lần Bao liên tiếp), Bánh kẹp Kéo
         (Bao, Kéo, Bao), Chiến lược Loại trừ (bỏ hẳn một thứ)
       · kỹ năng đánh lừa và đọc cử chỉ: thủ môn Bồ Đào Nha đoán đúng mọi
         cú sút, cản ba quả trong loạt luân lưu tứ kết World Cup 2006 với
         Anh
```

### Tiểu mục "Mixing It Up in the Laboratory" — pha trộn trong phòng thí nghiệm

```text
       Trái với sân bóng và sân quần vợt, thí nghiệm cho kết quả lẫn lộn
       hoặc tiêu cực: "người tham gia thí nghiệm hiếm khi (nếu có) được
       thấy tung đồng xu"
                                │
                                ▼
       Lý do (giống phân tích ở Chương 4):
       · trò chơi nhân tạo, người chơi mới, tiền cược nhỏ
       · luật được giải thích kỹ nhưng không nhắc tới việc được tung đồng
         xu hay gieo xúc xắc; từ thí nghiệm của Stanley Milgram, ta biết
         người tham gia coi người làm thí nghiệm là người có quyền, nên làm
         đúng từng chữ và không nghĩ tới ngẫu nhiên
       · dù vậy, ngay cả khi trò chơi giống hệt phạt đền, người tham gia
         vẫn không ngẫu nhiên hoá đúng cách
```

### Tiểu mục "How to Act Randomly" — làm sao hành động ngẫu nhiên, và "Unique Situations" — tình huống chỉ xảy ra một lần

```text
       Ngẫu nhiên KHÔNG có nghĩa là luân phiên
       · cầu thủ ném bóng chày pha bóng nhanh và bóng forkball 50:50 không
         được ném lần lượt từng loại; tỷ lệ 60:40 không có nghĩa sáu bóng
         nhanh rồi bốn forkball
                                │
                                ▼
       Con người viết dãy "ngẫu nhiên" có QUÁ NHIỀU lần đổi chiều, quá ít
       chuỗi lặp; sau 30 lần ngửa, lần sau vẫn 50:50, không có chuyện
       "đến lượt" ra sấp
       → giải thích các nước gài ở giải oẳn tù tì: ba lần Bao để đối thủ
         nghĩ lần thứ tư khó là Bao; bỏ một thứ để đối thủ nghĩ nó "sắp ra"
                                │
                                ▼
       Cần một cơ chế khách quan, bí mật, đủ phức tạp:
       · số chữ trong câu của sách lẻ thì ngửa, chẵn thì sấp (mười câu
         trước: S, N, N, S, N, N, N, N, S, S)
       · ngày sinh của bạn bè chẵn thì ngửa, lẻ thì sấp
       · kim giây đồng hồ: số chẵn thì bóng nhanh, lẻ thì forkball; muốn
         40:60 thì giây 1–24 bóng nhanh, giây 25–60 forkball
                                │
                                ▼
       Dân chuyên nghiệp làm tốt đến đâu?
       · quần vợt: giao bóng đổi chiều hơi nhiều (tương quan chuỗi âm),
         nhưng quá yếu để đối thủ khai thác
       · phạt đền: gần đúng ngẫu nhiên, vì hai lần sút cách nhau hàng tuần
       · oẳn tù tì: ít người thắng đều đặn qua các năm → các chiến lược
         cầu kỳ không cho lợi thế bền vững
                                │
                                ▼
       Sao không ỷ vào sự ngẫu nhiên của đối thủ? Khi thủ môn pha 41,7:58,3
       thì sút kiểu gì cũng 79,6%; nhưng nếu bạn chỉ sút Trái, thủ môn sẽ
       đổi sang chặn Trái → phải dùng tỷ lệ tốt nhất của mình để GIỮ đối
       thủ ở tỷ lệ tốt nhất của họ
                                │
                                ▼
       Tình huống chỉ xảy ra một lần (chọn hướng tấn công trong trận đánh):
       không có quy luật quá khứ để khai thác, nhưng có GIÁN ĐIỆP
       · muốn làm đối phương bất ngờ, cách chắc nhất là làm chính mình bất
         ngờ: giữ các phương án mở, phút chót chọn bằng cơ chế ngẫu nhiên
                                │
                                ▼
       Cảnh báo: dùng tỷ lệ tốt nhất vẫn có lúc thua
       · bóng bầu dục Mỹ, lượt thứ ba còn một yard: chạy thẳng là nước
         chắc, nhưng thỉnh thoảng phải chuyền dài để hàng thủ không dồn hết
         vào giữa; chuyền hỏng thì huấn luyện viên bị chỉ trích
       → phải giải thích chiến lược TRƯỚC khi dùng (dù hai tác giả ngờ
         rằng có giải thích thì vẫn bị chỉ trích như thường)
```

### Tiểu mục "Mixing Strategies in Mixed-Motives Games" — chiến lược hỗn hợp trong trò chơi động cơ hỗn hợp

```text
       Trò chơi đi săn của Fred và Barney (Chương 4): mỗi người ở hang
       riêng, chọn săn hươu (Stag) hay bò rừng (Bison); khác bãi thì không
       ai được gì
                         Barney Hươu       Barney Bò rừng
       Fred Hươu         Fred 4, Barney 3  0, 0
       Fred Bò rừng      0, 0              Fred 3, Barney 4
       · hai cân bằng Nash thuần tuý: cùng săn hươu, cùng săn bò rừng
                                │
                                ▼
       Cân bằng hỗn hợp:
       · Fred bàng quan khi tin Barney chọn Hươu với xác suất y: 4y =
         3(1–y) → y = 3/7
       · Barney bàng quan khi Fred chọn Hươu với xác suất x = 4/7
                                │
                                ▼
       Cân bằng này TỆ:
       · hai người lạc nhau (4/7)×(4/7) + (3/7)×(3/7) = 25/49 số lần
       · mỗi người được 12/7 = 1,71, thấp hơn cả 3 ở cân bằng thuần tuý
         kém thuận lợi cho mình
       · MONG MANH: nếu Fred tin xác suất Barney săn hươu là 0,43 thay vì
         0,42857, săn hươu cho 1,72 hơn săn bò rừng 1,71 → Fred thôi pha
         trộn → cân bằng sụp
       · KỲ LẠ: đổi kết quả của Barney thành 6 và 7 (thay cho 3 và 4) thì
         tỷ lệ của Barney không đổi (3/7) mà tỷ lệ của FRED đổi (7/13)
         → tỷ lệ của mỗi người do kết quả của NGƯỜI KIA quyết định; người
           tham gia thí nghiệm hầu như không nhận ra điều này
                                │
                                ▼
       Lối ra: pha trộn CÓ PHỐI HỢP. Hẹn trước: sáng có mưa (nửa số
       ngày) thì cùng săn hươu, trời khô thì cùng săn bò rừng
       → mỗi người được 1/2 × 3 + 1/2 × 4 = 3,5; ngẫu nhiên hoá phối hợp
         là một cách chia đôi khác biệt khi đàm phán
```

### Tiểu mục "Mixing in Business and Other Wars" — pha trộn trong kinh doanh và các cuộc chiến khác

```text
       Vì sao kinh doanh, chính trị, chiến tranh ít dùng ngẫu nhiên?
       · phần lớn là trò chơi tổng khác không, vai trò pha trộn hạn chế
       · văn hoá doanh nghiệp muốn kiểm soát kết quả; nước đi mạo hiểm
         thất bại có thể khiến bạn mất việc
                                │
                                ▼
       PHIẾU GIẢM GIÁ (Coke và Pepsi): chỉ hút khách mới khi MÌNH phát
       phiếu còn đối thủ không → giống trò chơi đi săn
       · luân phiên cố định 6 tháng một lần → đối thủ phát trước để chặn
       · ngẫu nhiên độc lập → nhiều tuần trùng nhau, triệt tiêu nhau
       → thế lưỡng nan của người tù; hai hãng quan hệ lâu dài nên giải
         được bằng cách thay phiên nhau
       · bằng chứng: trong 52 tuần, mỗi hãng khuyến mãi 26 tuần, KHÔNG tuần
         nào trùng; sách tính xác suất xảy ra ngẫu nhiên là
         1/495.918.532.948.104 (chuyện lên cả chương trình 60 Minutes
         của CBS); cách sách diễn đạt xác suất này chưa chính xác, xem
         phần Đánh giá
                                │
                                ▼
       VÉ MÁY BAY giờ chót: hãng không cho biết còn bao nhiêu ghế, vì nếu
       dễ đoán thì khách trả giá thường sẽ chuyển sang chờ vé rẻ
                                │
                                ▼
       KIỂM TRA NGẪU NHIÊN để buộc tuân thủ với chi phí giám sát thấp
       (kiểm tra thuế, xét nghiệm ma tuý, đồng hồ đỗ xe)
       · phí đỗ 1 USD/giờ: phạt 1,01 USD là đủ NẾU chắc chắn bị bắt mỗi
         lần, nhưng như vậy quá tốn kém
       · phạt 25 USD với xác suất bị bắt 1/25 cũng giữ được người ta trung
         thực, mà cần ít nhân viên hơn nhiều
       → hình phạt KỲ VỌNG (đã nhân với xác suất bị bắt) mới phải tương
         xứng với vi phạm; hình phạt thực tế phải nặng hơn vi phạm
       · IRS có vấn đề: tiền phạt nhỏ so với khả năng bị phát hiện
                                │
                                ▼
       Bên muốn né cũng dùng ngẫu nhiên: giấu mục tiêu thật giữa các mồi
       nhử
       · tên lửa mồi rẻ hơn tên lửa thật; phòng không phải bắn hết
       · Thế chiến II: bắn ngẫu nhiên đạn lép để đối phương phải xử lý mọi
         quả đạn chưa nổ
       · nếu chi phí phòng thủ tỷ lệ với số tên lửa phải bắn hạ, đây là
         thách thức lớn của hệ thống phòng thủ "Star Wars" và có thể không
         có lời giải
```

### Tiểu mục "How to Find Mixed Strategy Equilibria" — cách tìm cân bằng chiến lược hỗn hợp, và "Surprising Changes in Mixtures" — những thay đổi bất ngờ trong tỷ lệ pha trộn

```text
       Phương pháp đại số (cầu thủ sút, x là tỷ lệ sút Trái):
       · gặp thủ môn Trái: 58x + 93(1–x) = 93 – 35x
       · gặp thủ môn Phải: 95x + 70(1–x) = 70 + 25x
       · cho bằng nhau: 23 = 60x → x = 23/60 = 0,383
       Thủ môn (y là tỷ lệ bay Trái):
       · cầu thủ sút Trái: 58y + 95(1–y) = 95 – 37y
       · cầu thủ sút Phải: 93y + 70(1–y) = 70 + 23y
       · cho bằng nhau: 25 = 60y → y = 25/60 = 0,417
                                │
                                ▼
       Phương pháp đồ thị: hai đường thẳng theo tỷ lệ pha trộn
       · với cầu thủ: lấy đường THẤP hơn (thủ môn khai thác) → hình chữ V
         ngược; đỉnh ở x = 0,383, mức 79,6 (lớn nhất của các mức nhỏ
         nhất, maximin)
       · với thủ môn: lấy đường CAO hơn (cầu thủ khai thác) → hình chữ V;
         đáy ở y = 0,417, mức 79,6 (nhỏ nhất của các mức lớn nhất,
         minimax)
       → maximin bằng minimax: định lý minimax đang vận hành
                                │
                                ▼
       Thủ môn tập tốt hơn khi bắt bóng sút về phía Phải: tỷ lệ ghi bàn ô
       (Sút Phải, Thủ môn Phải) giảm từ 70 xuống 60
       · thủ môn bay Trái NHIỀU hơn: từ 41,7% lên 50% → ít bay về phía vừa
         tập giỏi hơn!
       · vì cầu thủ sút Trái nhiều hơn: từ 38,3% lên 47,1%
       · thủ môn vẫn được lợi: tỷ lệ ghi bàn cân bằng giảm từ 79,6% xuống
         76,5%
       → "cải thiện điểm yếu để không phải dùng nó thường xuyên"; điều tốt
         nhất cho bạn phụ thuộc cả vào việc người khác làm gì
```

### Tiểu mục "Case Study: Janken Step Game" — tình huống: trò Janken leo bậc

```text
       Quán sushi ở Tokyo: Takashi và Yuichi cùng gọi uni sashimi (nhím
       biển), đầu bếp chỉ còn một phần → chơi Janken (oẳn tù tì) leo bậc
       · thắng bằng Bao (5 ngón) leo 5 bậc; bằng Kéo (2 ngón) leo 2 bậc;
         bằng Búa (0 ngón) leo 1 bậc; hoà thì chơi lại
       · đơn giản hoá: mục tiêu là vượt đối thủ càng nhiều bậc càng tốt
                                │
                                ▼
       Bảng kết quả (số bậc Takashi vượt Yuichi; Yuichi được số ngược dấu)
                         Yuichi Búa   Yuichi Bao   Yuichi Kéo
       Takashi Búa            0           –5            1
       Takashi Bao            5            0           –2
       Takashi Kéo           –1            2            0
                                │
                                ▼
       Cả ba cách ra đều phải có trong cân bằng: nếu Yuichi không bao giờ
       ra Búa thì Takashi không ra Bao, rồi Yuichi không ra Kéo, rồi
       Takashi không ra Búa, rồi Yuichi không ra Bao → Yuichi hết cách ra,
       mâu thuẫn
                                │
                                ▼
       Takashi ra Bao với xác suất p, Kéo q, Búa 1–(p+q); Yuichi phải thấy
       ba cách bằng nhau:
       · Búa: –5p + q;  Kéo: 3p + q – 1;  Bao: –5p – 7q + 5
       → p = 1/8 (Bao), q = 5/8 (Kéo), Búa = 2/8; Yuichi dùng cùng tỷ lệ
       · kết quả kỳ vọng của mỗi người bằng 0 (luôn đúng với trò chơi tổng
         bằng không đối xứng)
```

## Ba câu hỏi chương này trả lời

1. **Khi đối thủ đoán được mình thì làm gì?** Hãy chọn ngẫu nhiên theo một tỷ lệ tính trước. Trong quả phạt đền, sút cố định về phía thuận chỉ bảo đảm 70% ghi bàn, còn pha trộn Trái 38,3% và Phải 61,7% bảo đảm 79,6% dù thủ môn làm gì. Phép thử là: để đối thủ biết trước lựa chọn của mình có hại không? Nếu có hại thì sự ngẫu nhiên có giá trị.
2. **Tỷ lệ pha trộn tốt nhất được xác định thế nào, và người thật có làm theo không?** Tỷ lệ tốt nhất làm cho đối thủ chọn chiến lược thuần tuý nào cũng thu được như nhau, nên họ không có gì để khai thác. Cầu thủ và thủ môn chuyên nghiệp ở châu Âu làm rất gần lý thuyết (40,0% so với 38,3%; 42,3% so với 41,7%), còn người tham gia thí nghiệm thì không. Muốn ngẫu nhiên thật phải dùng một cơ chế khách quan như kim giây đồng hồ, vì con người tự nghĩ thì hay đổi chiều quá nhiều.
3. **Ngoài thể thao, chiến lược hỗn hợp dùng vào đâu và có giới hạn gì?** Dùng nhiều nhất trong kiểm tra ngẫu nhiên: phạt 25 USD với xác suất bị bắt 1/25 thay cho kiểm tra mọi lúc, xét nghiệm ma tuý ngẫu nhiên, kiểm tra thuế; bên vi phạm cũng dùng mồi nhử để làm loãng nguồn lực của bên kiểm tra. Nhưng trong trò chơi có lợi ích chung (hai thợ săn, Coke và Pepsi), pha trộn độc lập cho kết quả kém và mong manh; phối hợp hoặc thay phiên tốt hơn nhiều, như Coke và Pepsi đã thay phiên khuyến mãi 26 tuần mỗi hãng không trùng tuần nào.

## Khái niệm cần biết

**Chiến lược hỗn hợp (mixed strategy) và chiến lược thuần tuý (pure strategy).** Chiến lược thuần tuý là chọn hẳn một phương án (luôn sút Trái). Chiến lược hỗn hợp là chọn ngẫu nhiên giữa các phương án theo tỷ lệ định trước (sút Trái 38,3%, Phải 61,7%). Ví dụ: với tỷ lệ đó, cầu thủ sút ghi bàn 79,6% dù thủ môn bay bên nào. Đây là khái niệm trung tâm của chương: nó giải quyết những trò chơi không có cân bằng Nash trong các chiến lược thuần tuý.

**Trò chơi tổng bằng không (zero-sum) và tổng không đổi (constant-sum).** Trò chơi xung đột thuần tuý: cái được của bên này đúng bằng cái mất của bên kia (tổng bằng không), hoặc tổng kết quả của hai bên luôn là một hằng số. Ví dụ: tỷ lệ ghi bàn của cầu thủ sút cộng tỷ lệ cản phá của thủ môn luôn bằng 100. Quan trọng vì Quy tắc 5 và định lý minimax áp dụng cho loại trò chơi này; hai tác giả nhấn mạnh loại này hiếm trong đời thực.

**Định lý minimax (minimax theorem).** Định lý của John von Neumann: trong trò chơi hai người tổng bằng không, nếu một bên cố làm nhỏ nhất mức tối đa đối thủ có thể đạt (minimax) và bên kia cố làm lớn nhất mức tối thiểu mình chắc chắn đạt được (maximin), thì hai mức này bằng nhau. Ví dụ: cầu thủ sút tự bảo đảm được 79,6%, và thủ môn cũng giữ được cầu thủ ở đúng 79,6%. Hệ quả thực dụng: chỉ cần tính tỷ lệ tốt nhất của một bên là biết kết quả của cả trò chơi.

**Cân bằng Nash trong chiến lược hỗn hợp (Nash equilibrium in mixed strategies).** Cặp tỷ lệ pha trộn mà không bên nào lợi khi đổi tỷ lệ, khi bên kia giữ nguyên. Ví dụ: cầu thủ 38,3:61,7 và thủ môn 41,7:58,3. Định lý minimax là trường hợp riêng của khái niệm này; cân bằng Nash hỗn hợp áp dụng được cả cho trò chơi nhiều người và trò chơi không phải xung đột thuần tuý (ví dụ Fred và Barney với tỷ lệ 4/7 và 3/7).

**Nguyên tắc bàng quan (indifference principle).** Cách tính tỷ lệ pha trộn: chọn tỷ lệ của mình sao cho ĐỐI THỦ thu được như nhau ở mọi chiến lược thuần tuý. Ví dụ: 58x + 93(1–x) = 95x + 70(1–x) cho x = 0,383. Hệ quả kỳ lạ là tỷ lệ của mỗi người do kết quả của người kia quyết định: đổi kết quả của Barney thành 6 và 7 thì tỷ lệ của Fred đổi từ 4/7 sang 7/13. (Tên gọi "nguyên tắc bàng quan" là của người tổng hợp; sách mô tả ý này mà không đặt tên.)

**Pha trộn có phối hợp (coordinated mixing / coordinated randomization).** Hai bên dùng chung một tín hiệu ngẫu nhiên cả hai cùng quan sát được để cùng đổi lựa chọn. Ví dụ: Fred và Barney hẹn có mưa buổi sáng thì cùng săn hươu, trời khô thì cùng săn bò rừng; mỗi người được trung bình 3,5, so với 1,71 khi pha trộn độc lập. Quan trọng vì nó cho thấy ngẫu nhiên có thể là công cụ đàm phán để chia đôi khác biệt.

**Hình phạt kỳ vọng (expected punishment).** Hình phạt nhân với xác suất bị bắt. Ví dụ: phạt 25 USD với xác suất bị bắt 1/25 cho hình phạt kỳ vọng 1 USD, đủ để người ta trả phí đỗ xe 1 USD/giờ. Quan trọng vì nó giải thích vì sao khi kiểm tra ngẫu nhiên thì hình phạt thực tế phải nặng hơn vi phạm nhiều lần.

## Nội dung chi tiết

### 1. Bí đường suy luận: Vizzini và hai chén rượu độc (Wit's End)

Chương mở bằng một cảnh trong bộ phim hài *The Princess Bride*. Người hùng Westley thách kẻ ác người Sicily là Vizzini: Westley sẽ bỏ thuốc độc vào một trong hai chén rượu mà Vizzini không thấy, Vizzini chọn uống một chén, Westley phải uống chén còn lại. Vizzini, người coi Plato, Aristotle và Socrates là "đồ ngốc", tin rằng mình thắng được bằng suy luận. Anh ta lập luận: người khôn sẽ bỏ độc vào chén của chính mình, vì chỉ kẻ rất ngốc mới cầm chén được đưa cho mình; Vizzini không ngốc nên không chọn chén trước mặt Westley; nhưng Westley hẳn biết Vizzini không ngốc và đã tính tới điều đó, nên Vizzini cũng không thể chọn chén trước mặt mình. Anh ta tiếp tục với những cân nhắc khác, tất cả đều xoay vòng như vậy, rồi đánh lạc hướng Westley, tráo chén, cười đắc thắng: "Anh đã mắc một trong những sai lầm kinh điển. Nổi tiếng nhất là 'Đừng bao giờ sa vào một cuộc chiến trên bộ ở châu Á', nhưng chỉ kém nổi tiếng một chút là 'Đừng bao giờ đấu với người Sicily khi tính mạng đang bị đặt cược'." Anh ta vẫn đang cười thì ngã xuống chết.

Hai tác giả giải thích: mỗi lập luận của Vizzini tự mâu thuẫn. Nếu Vizzini suy ra Westley bỏ độc vào chén A thì nên chọn chén B; nhưng Westley cũng suy ra được điều đó nên sẽ bỏ độc vào B; Vizzini lại phải đoán trước điều này nên chọn A; và vòng suy luận cứ thế không có điểm dừng.

> **Chú thích của tác giả:** Ai đã xem phim hay đọc truyện đều biết suy luận của Vizzini có một lỗi cơ bản hơn. Westley đã tập cho mình miễn dịch với bột độc iocane suốt nhiều năm và bỏ độc vào cả hai chén, nên Vizzini chọn chén nào cũng chết còn Westley thì an toàn. Vizzini không biết điều đó, tức là chơi trò chơi trong thế thiếu thông tin không thể khắc phục. Bài học chung: khi người khác đề nghị với bạn một trò chơi hay một giao dịch, hãy luôn tự hỏi "họ có biết điều gì mà mình không biết không?". Hai tác giả nhắc lại lời khuyên mà nhân vật Sky Masterson (trong vở nhạc kịch *Guys and Dolls*, câu chuyện thứ 9 ở Chương 1) được cha dặn: đừng đánh cược với người đề nghị cá rằng anh ta làm được con J bích nhảy ra khỏi cỗ bài và phun rượu táo vào tai bạn, vì người đề nghị cuộc cược như thế chắc chắn đã biết trước kết quả. Vấn đề thông tin bất cân xứng sẽ được bàn ở phần sau của sách; chương này chỉ tập trung vào lỗi suy luận xoay vòng, vì nó có ý nghĩa và nhiều ứng dụng riêng.

Thế khó của Vizzini xuất hiện ở nhiều trò chơi. Khi sút phạt đền, cầu thủ sút có thể có lý do để sút sang trái thủ môn (vì thuận chân trái, vì thủ môn thuận tay nào đó, hay vì lần trước đã sút bên kia). Nhưng nếu thủ môn nghĩ ra được lý do ấy, anh ta sẽ chuẩn bị chặn bên trái, nên sút bên phải lại tốt hơn; nếu thủ môn nghĩ sâu thêm một bậc thì sút trái lại tốt hơn; và cứ thế. Suy luận duy nhất đứng vững là: nếu lựa chọn của bạn theo bất kỳ quy luật nào, đối thủ sẽ khai thác nó; cầu thủ nổi tiếng hay sút bên trái sẽ bị thủ môn chặn bên trái nhiều hơn. Vì vậy bạn phải khiến đối thủ phải đoán bằng cách hành động không theo hệ thống, tức ngẫu nhiên, ở mỗi lần. Chọn hành động ngẫu nhiên nghe có vẻ phi lý trong một cuốn sách về tư duy chiến lược hợp lý, nhưng theo hai tác giả, giá trị của việc ngẫu nhiên hoá có thể tính bằng con số cụ thể, và chương này trình bày cách tính.

### 2. Pha trộn trên sân bóng (Mixing It Up on the Soccer Field)

Quả phạt đền là ví dụ đơn giản và nổi tiếng nhất về tình huống cần nước đi ngẫu nhiên, mà ngôn ngữ lý thuyết trò chơi gọi là chiến lược hỗn hợp (mixed strategy). Nó đã được nghiên cứu nhiều cả về lý thuyết lẫn thực nghiệm.

**Luật chơi.** Phạt đền được trao khi đội phòng ngự phạm một số lỗi nhất định trong vùng chữ nhật trước khung thành của mình, và loạt sút phạt đền cũng là cách phân định cuối cùng khi trận đấu hoà. Khung thành rộng 8 yard (khoảng 7,3 m) và cao 8 feet (khoảng 2,4 m). Bóng đặt cách vạch vôi 12 yard (khoảng 11 m), ngay trước điểm giữa khung thành, và cầu thủ phải sút thẳng từ đó. Thủ môn phải đứng trên vạch vôi ở giữa khung thành và không được rời vạch cho tới khi bóng được sút. Một cú sút tốt chỉ mất hai phần mười giây để tới vạch vôi, nên thủ môn chờ xem bóng đi đâu thì không thể cản được, trừ khi bóng bay thẳng vào người. Vì khung thành rộng, thủ môn phải quyết định trước có bay về một bên không và bay bên nào; cầu thủ sút cũng phải quyết định hướng sút khi đang chạy đà, trước khi thấy thủ môn nghiêng về đâu. Mỗi bên đều cố che giấu lựa chọn của mình, nên trò chơi này thực chất là trò chơi đồng thời (simultaneous game).

**Đơn giản hoá.** Thủ môn hiếm khi đứng giữa, cầu thủ cũng tương đối hiếm khi sút vào giữa (điều này cũng giải thích được bằng lý thuyết), nên hai tác giả giới hạn mỗi bên ở hai lựa chọn. Vì cầu thủ thường sút bằng má trong bàn chân, hướng tự nhiên của cầu thủ thuận chân phải là phía tay phải thủ môn, và của cầu thủ thuận chân trái là phía tay trái thủ môn. Để viết cho gọn, phía tự nhiên được gọi là "Phải"; khi thủ môn chọn "Phải" nghĩa là thủ môn bay về phía thuận của cầu thủ sút. Ngay cả khi đã biết hai bên chọn gì, kết quả vẫn có yếu tố may rủi (bóng có thể vọt xà, thủ môn có thể chạm bóng nhưng bóng vẫn vào lưới), nên kết quả của cầu thủ sút được đo bằng phần trăm số lần ghi bàn, còn của thủ môn là phần trăm số lần không thủng lưới.

**Bảng kết quả** (dựng lại từ sách). Số liệu là trung bình của nhiều cầu thủ và thủ môn ở các giải hàng đầu Ý, Tây Ban Nha và Anh giai đoạn 1995–2000, do Ignacio Palacios-Huerta thu thập. Mỗi ô ghi kết quả của cầu thủ sút trước, của thủ môn sau.

| Cầu thủ sút \ Thủ môn | Thủ môn bay Trái | Thủ môn bay Phải |
|---|---|---|
| Sút Trái | 58 ; 42 | 95 ; 5 |
| Sút Phải | 93 ; 7 | 70 ; 30 |

Các con số khớp với trực giác: cầu thủ sút được nhiều hơn khi hai bên chọn ngược phía; khi ngược phía, tỷ lệ thành công gần như như nhau dù sút phía thuận hay không (thất bại chỉ vì sút ra ngoài hoặc vọt xà); khi cùng phía, cầu thủ được nhiều hơn nếu sút về phía thuận.

**Không có cân bằng Nash trong các lựa chọn thuần tuý.** Cả hai cùng chọn Trái không phải cân bằng, vì khi thủ môn bay Trái, cầu thủ đổi sang sút Phải sẽ tăng từ 58 lên 93. (Sút Phải, thủ môn Trái) cũng không phải cân bằng, vì thủ môn đổi sang bay Phải sẽ tăng từ 7 lên 30. Lúc đó cầu thủ lại muốn đổi sang Trái, rồi thủ môn lại đổi sang Trái. Vòng đổi qua đổi lại này đúng là vòng suy luận của Vizzini, và việc trò chơi không có cân bằng Nash trong các cặp lựa chọn đã nêu chính là cách lý thuyết trò chơi diễn đạt tầm quan trọng của việc pha trộn nước đi. Việc cần làm là đưa pha trộn vào như một loại chiến lược mới và tìm cân bằng Nash trong tập chiến lược mở rộng này. Các lựa chọn ban đầu (Trái, Phải) được gọi là chiến lược thuần tuý (pure strategy).

**Trò chơi xung đột thuần tuý.** Trò chơi này có đặc điểm là lợi ích hai bên đối nghịch hoàn toàn: kết quả của thủ môn luôn bằng 100 trừ kết quả của cầu thủ sút. Nhiều người, từ kinh nghiệm thể thao, nghĩ rằng mọi trò chơi đều có người thắng kẻ thua, nhưng trong thế giới trò chơi chiến lược nói chung, xung đột thuần tuý là tương đối hiếm: trao đổi tự nguyện trong kinh tế có thể cho cả hai bên cùng thắng, thế lưỡng nan của người tù cho thấy cả hai có thể cùng thua, mặc cả và trò chơi kẻ nhát gan (chicken) có thể cho kết quả lệch hẳn về một bên. Phần lớn trò chơi pha trộn xung đột và lợi ích chung. Tuy vậy, xung đột thuần tuý là loại được nghiên cứu lý thuyết đầu tiên. Loại này gọi là trò chơi tổng bằng không (zero-sum), khi kết quả của một bên luôn là số đối của bên kia, hay tổng quát hơn là tổng không đổi (constant-sum), như ở đây tổng luôn bằng 100. Với loại trò chơi này, bảng kết quả chỉ cần ghi kết quả của người chơi hàng; người chơi hàng thích con số lớn, người chơi cột thích con số nhỏ:

| Cầu thủ sút \ Thủ môn | Thủ môn bay Trái | Thủ môn bay Phải |
|---|---|---|
| Sút Trái | 58 | 95 |
| Sút Phải | 93 | 70 |

**Đi tìm tỷ lệ tốt nhất.** Nếu cầu thủ sút chọn một chiến lược thuần tuý: sút Trái thì thủ môn bay Trái và giữ tỷ lệ thành công ở 58%; sút Phải thì thủ môn bay Phải và giữ ở 70%. Trong hai cách đó, (Phải, Phải) tốt hơn.

> **Chú thích của tác giả:** Thủ môn có thể "biết trước" lựa chọn của bạn vì bạn mang tiếng là người "luôn sút Trái" hay "luôn sút Phải". Tất nhiên bạn không muốn tạo ra khuôn mẫu và tiếng tăm như vậy, và đó chính là giá trị của sự ngẫu nhiên mà chương đang trình bày.

Các mức pha trộn lần lượt cho kết quả như sau:

| Cách chơi của cầu thủ sút | Gặp thủ môn bay Trái | Gặp thủ môn bay Phải | Thủ môn giữ được cầu thủ ở |
|---|---|---|---|
| Luôn sút Phải (thuần tuý tốt hơn) | 93 | 70 | 70% |
| 50:50 (tung đồng xu giấu trong lòng bàn tay, sấp sút Trái, ngửa sút Phải) | 1/2 × 58 + 1/2 × 93 = 75,5 | 1/2 × 95 + 1/2 × 70 = 82,5 | 75,5% |
| 40:60 (mở ngẫu nhiên một trang sách nhỏ, số trang tận cùng 1–4 sút Trái, 5–0 sút Phải) | 0,4 × 58 + 0,6 × 93 = 79 | 0,4 × 95 + 0,6 × 70 = 80 | 79% |
| 38,3:61,7 (tỷ lệ tốt nhất) | 0,383 × 58 + 0,617 × 93 = 79,6 | 0,383 × 95 + 0,617 × 70 = 79,6 | 79,6% |

Một cách kiểm tra nhanh xem có cần ngẫu nhiên không: hãy hỏi nếu đối thủ biết trước lựa chọn thực sự của bạn trước khi phản ứng thì bạn có bị thiệt không. Nếu có, sự ngẫu nhiên khiến đối thủ phải đoán là có lợi.

Hai tác giả chỉ ra quy luật trong bảng: các tỷ lệ pha trộn tốt dần thu hẹp khoảng chênh giữa hai kết quả (93 với 70, rồi 82,5 với 75,5, rồi 80 với 79). Tỷ lệ tốt nhất là tỷ lệ cho cùng một mức thành công dù thủ môn bay Trái hay Phải. Điều này khớp với trực giác rằng pha trộn tốt vì nó ngăn đối thủ khai thác bất kỳ khuôn mẫu nào.

Với thủ môn cũng vậy. Nếu thủ môn luôn bay Trái, cầu thủ sút Phải và đạt 93%; nếu thủ môn luôn bay Phải, cầu thủ sút Trái và đạt 95%. Bằng cách pha trộn, thủ môn giữ được cầu thủ ở mức thấp hơn nhiều. Tỷ lệ tốt nhất của thủ môn là bay Trái 41,7% và Phải 58,3%, khi đó cầu thủ sút bên nào cũng chỉ ghi bàn 79,6%.

**Định lý minimax.** Con số 79,6 mà cầu thủ sút tự bảo đảm được trùng với con số 79,6 mà thủ môn giữ được cầu thủ ở đó. Đây không phải trùng hợp mà là một tính chất chung của cân bằng chiến lược hỗn hợp trong trò chơi xung đột thuần tuý, gọi là định lý minimax (minimax theorem), do nhà toán học Princeton John von Neumann chứng minh và sau đó ông phát triển cùng nhà kinh tế Princeton Oscar Morgenstern trong cuốn *Theory of Games and Economic Behavior*, cuốn sách có thể coi là khai sinh cả môn lý thuyết trò chơi. Định lý nói rằng trong trò chơi tổng bằng không, khi một người chơi cố làm nhỏ nhất mức kết quả tối đa của đối thủ còn đối thủ cố làm lớn nhất mức kết quả tối thiểu của chính mình, thì mức nhỏ nhất của các mức tối đa (minimax) bằng mức lớn nhất của các mức tối thiểu (maximin). Chứng minh tổng quát rất phức tạp, nhưng kết quả đáng nhớ: nếu chỉ cần biết một bên được bao nhiêu khi cả hai chơi tốt nhất, chỉ cần tính tỷ lệ pha trộn tốt nhất của một bên.

### 3. Lý thuyết và thực tế (Theory and Reality)

Bảng dưới (dựng lại từ sách) so sánh tỷ lệ pha trộn tốt nhất theo tính toán của hai tác giả với tỷ lệ thực tế trong dữ liệu của Palacios-Huerta.

| Người chơi | Tỷ lệ chọn Trái | % ghi bàn khi đối thủ chọn Trái | % ghi bàn khi đối thủ chọn Phải |
|---|---|---|---|
| Cầu thủ sút, tốt nhất | 38,3% | 79,6% | 79,6% |
| Cầu thủ sút, thực tế | 40,0% | 79,0% | 80,0% |
| Thủ môn, tốt nhất | 41,7% | 79,6% | 79,6% |
| Thủ môn, thực tế | 42,3% | 79,3% | 79,7% |

Tỷ lệ thực tế rất gần tỷ lệ tốt nhất, và cho các tỷ lệ thành công gần như bằng nhau bất kể đối thủ chọn gì, nghĩa là gần như miễn nhiễm trước sự khai thác. Bằng chứng tương tự đến từ các trận quần vợt chuyên nghiệp hàng đầu. Điều này dễ hiểu: cùng những người chơi gặp nhau thường xuyên và nghiên cứu cách chơi của nhau, nên mọi khuôn mẫu dễ thấy đều bị phát hiện; tiền bạc, thành tích và danh tiếng đặt cược rất lớn, nên họ có động cơ mạnh để không mắc lỗi. Tuy nhiên, hai tác giả nói thành công của lý thuyết không phải ở đâu cũng trọn vẹn, và sẽ quay lại điểm này.

**Quy tắc 5.** Hai tác giả tóm nguyên lý thành quy tắc hành động: *Trong trò chơi xung đột thuần tuý (tổng bằng không), nếu để đối thủ thấy trước lựa chọn thực sự của bạn là bất lợi, thì bạn được lợi khi chọn ngẫu nhiên giữa các chiến lược thuần tuý của mình. Tỷ lệ pha trộn phải sao cho đối thủ không thể khai thác lựa chọn của bạn bằng bất kỳ chiến lược thuần tuý nào của họ, tức là bạn thu được cùng một kết quả trung bình dù đối thủ dùng chiến lược thuần tuý nào để đối phó với tỷ lệ pha trộn của bạn.*

Khi một bên theo quy tắc này, bên kia dùng chiến lược thuần tuý nào cũng như nhau, nên họ bàng quan giữa chúng và không làm tốt hơn được việc dùng chính tỷ lệ mà quy tắc chỉ định cho họ. Khi cả hai cùng theo, không ai được lợi khi lệch khỏi cách chơi đó, và đó đúng là định nghĩa cân bằng Nash ở Chương 4. Nói cách khác, khi cả hai dùng quy tắc này ta có cân bằng Nash trong chiến lược hỗn hợp. Do đó định lý minimax của von Neumann và Morgenstern là trường hợp riêng của lý thuyết tổng quát hơn của Nash: định lý minimax chỉ áp dụng cho trò chơi hai người tổng bằng không, còn khái niệm cân bằng Nash dùng được với mọi số người chơi và mọi mức pha trộn giữa xung đột và lợi ích chung.

**Cân bằng của trò chơi tổng bằng không không nhất thiết là hỗn hợp.** Giả sử cầu thủ sút rất kém khi sút về phía không thuận (dùng má ngoài bàn chân nên dễ trượt mục tiêu), với bảng kết quả (dựng lại từ sách):

| Cầu thủ sút \ Thủ môn | Thủ môn bay Trái | Thủ môn bay Phải |
|---|---|---|
| Sút Trái | 38 | 65 |
| Sút Phải | 93 | 70 |

Khi đó sút Phải là chiến lược trội (dominant strategy) của cầu thủ (93 lớn hơn 38 và 70 lớn hơn 65), và không có lý do gì để pha trộn. Tổng quát hơn, có thể có cân bằng thuần tuý ngay cả khi không có chiến lược trội. Điều này không gây khó khăn gì: phương pháp tìm cân bằng hỗn hợp cũng tìm ra các cân bằng thuần tuý như trường hợp đặc biệt, khi một chiến lược chiếm 100% tỷ lệ pha trộn.

### 4. Trò chơi trẻ con (Child's Play)

Ngày 23 tháng 10 năm 2005, Andrew Bergel ở Toronto đăng quang vô địch giải Oẳn tù tì Quốc tế (Rock Paper Scissors International World Champion) và nhận huy chương vàng của Hiệp hội RPS Thế giới (World RPS Society); Stan Long ở Newark, California giành huy chương bạc, Stewart Waldman ở New York huy chương đồng. Hiệp hội có trang web (www.worldrps.com) đăng luật chính thức và hướng dẫn chiến lược, và tổ chức giải vô địch hằng năm.

Luật giống như hồi nhỏ (đã mô tả ở Chương 1): hai người cùng lúc "ra" một trong ba dấu tay: Búa là nắm tay, Bao là bàn tay xoè ngang, Kéo là ngón trỏ và ngón giữa chĩa về phía đối thủ, tạo góc với nhau. Ra giống nhau thì hoà; khác nhau thì Búa thắng (đập) Kéo, Kéo thắng (cắt) Bao, Bao thắng (trùm) Búa. Mỗi cặp chơi nhiều ván liên tiếp, ai thắng đa số ván thì thắng trận. Luật của hiệp hội bảo đảm hai điều: mô tả chính xác hình dạng bàn tay của từng loại để chống ăn gian (ra một cử chỉ mơ hồ rồi nhận đó là thứ thắng đối thủ); và quy định một trình tự động tác (gọi là chuẩn bị, tiếp cận và ra tay) để bảo đảm hai người ra đồng thời, không ai thấy trước đối thủ ra gì.

Đây là trò chơi đồng thời hai người, mỗi người ba chiến lược thuần tuý. Tính thắng là 1, thua là –1, hoà là 0, ta có bảng (dựng lại từ sách; hai tác giả đặt tên người chơi là Andrew và Stan để vinh danh thành tích năm 2005; mỗi ô ghi kết quả của Andrew trước, của Stan sau):

| Andrew \ Stan | Búa | Bao | Kéo |
|---|---|---|---|
| Búa | 0 ; 0 | –1 ; 1 | 1 ; –1 |
| Bao | 1 ; –1 | 0 ; 0 | –1 ; 1 |
| Kéo | –1 ; 1 | 1 ; –1 | 0 ; 0 |

Đây là trò chơi tổng bằng không, và để lộ trước nước đi là bất lợi. Nếu Andrew chỉ ra một thứ cố định, Stan luôn đáp lại được bằng thứ thắng nó và giữ Andrew ở –1. Nếu Andrew ra mỗi thứ 1/3, kết quả trung bình là (1/3) × 1 + (1/3) × 0 + (1/3) × (–1) = 0 trước bất kỳ chiến lược thuần tuý nào của Stan. Với cấu trúc đối xứng, đây hiển nhiên là điều tốt nhất Andrew làm được, và tính toán xác nhận trực giác đó; Stan cũng vậy. Pha trộn đều ba thứ là cân bằng Nash trong chiến lược hỗn hợp.

Nhưng phần lớn người dự giải không chơi như vậy. Trang web của hiệp hội gọi cách chơi này là "Lối chơi Hỗn loạn" (Chaos Play) và khuyên không nên dùng, với lý lẽ rằng không có cú ra nào thật sự ngẫu nhiên: con người luôn ra theo một xung lực hay khuynh hướng nào đó, nên sẽ rơi vào những khuôn mẫu vô thức nhưng đoán trước được; và "trường phái Hỗn loạn" đang teo tóp vì thống kê giải đấu cho thấy các chiến lược khác hiệu quả hơn. Trang web liệt kê các "nước gài" (gambit): "Quan liêu" (Bureaucrat) là ba lần Bao liên tiếp; "Bánh kẹp Kéo" (Scissor Sandwich) là Bao, Kéo, Bao; "Chiến lược Loại trừ" (Exclusion Strategy) là bỏ hẳn một thứ. Ý tưởng là đối thủ sẽ dồn hết sức đoán xem khi nào khuôn mẫu thay đổi hay khi nào thứ bị bỏ xuất hiện, và bạn khai thác điểm yếu đó trong suy luận của họ.

Còn có kỹ năng thể chất trong đánh lừa và phát hiện đánh lừa: người chơi quan sát ngôn ngữ cơ thể và bàn tay của nhau để đoán, và cố làm như sắp ra một thứ rồi ra thứ khác. Cầu thủ sút và thủ môn cũng quan sát chân và người nhau như vậy. Kỹ năng này có tác dụng: trong loạt luân lưu tứ kết World Cup 2006 giữa Anh và Bồ Đào Nha, thủ môn Bồ Đào Nha đoán đúng hướng mọi cú sút và cản phá ba quả, mang về chiến thắng cho đội mình.

### 5. Pha trộn trong phòng thí nghiệm (Mixing It Up in the Laboratory)

Trái với sự khớp đáng kinh ngạc giữa lý thuyết và thực tế trên sân bóng và sân quần vợt, bằng chứng từ thí nghiệm lẫn lộn, thậm chí tiêu cực. Cuốn sách chuyên khảo đầu tiên về kinh tế học thực nghiệm viết thẳng rằng người tham gia thí nghiệm hiếm khi, nếu có, được thấy tung đồng xu. Một phần lý do giống như ở Chương 4 khi so sánh hai loại bằng chứng: trong phòng thí nghiệm, trò chơi được dựng nhân tạo, người chơi mới làm quen, tiền cược nhỏ; ngoài thực tế, người chơi có kinh nghiệm chơi trò chơi quen thuộc, với cái giá rất lớn về danh tiếng và thường cả tiền bạc.

Hai tác giả nêu thêm một hạn chế của thí nghiệm. Buổi thí nghiệm luôn bắt đầu bằng phần giải thích luật kỹ lưỡng, nhưng luật không nhắc tới khả năng ngẫu nhiên hoá, không phát đồng xu hay xúc xắc, cũng không nói "bạn được phép tung đồng xu hoặc gieo xúc xắc để quyết định nếu muốn". Người tham gia được dặn làm đúng luật thì không tung đồng xu là chuyện dễ hiểu. Từ thí nghiệm nổi tiếng của Stanley Milgram, ai cũng biết người tham gia coi người làm thí nghiệm là người có quyền cần tuân lệnh, nên họ làm đúng từng chữ và không nghĩ tới ngẫu nhiên. Tuy vậy, sự thật vẫn là ngay cả khi trò chơi được thiết kế giống phạt đền, nơi giá trị của pha trộn hiển nhiên, người tham gia dường như vẫn không ngẫu nhiên hoá đúng cách và đúng lúc qua các lượt chơi. Lý thuyết chiến lược hỗn hợp vì thế có hồ sơ vừa thành công vừa thất bại.

### 6. Làm sao hành động ngẫu nhiên (How to Act Randomly)

Ngẫu nhiên không có nghĩa là luân phiên. Nếu một cầu thủ ném bóng chày (pitcher) được bảo pha bóng nhanh (fastball) và bóng forkball (bóng rơi đột ngột) theo tỷ lệ bằng nhau, anh ta không được ném lần lượt bóng nhanh, forkball, bóng nhanh theo vòng cố định, vì người đánh bóng sẽ nhanh chóng nhận ra; tỷ lệ 60:40 cũng không có nghĩa là sáu bóng nhanh rồi bốn forkball. Một cách làm là chọn ngẫu nhiên một số từ 1 đến 10, từ 5 trở xuống thì ném bóng nhanh, từ 6 trở lên thì ném forkball. Nhưng việc này chỉ đẩy vấn đề lùi một bước: chọn ngẫu nhiên một số từ 1 đến 10 bằng cách nào?

Ngay việc viết ra một dãy tung đồng xu ngẫu nhiên đã khó hơn ta tưởng. Nếu dãy thật sự ngẫu nhiên thì người đoán chỉ đúng trung bình không quá 50%. Các nhà tâm lý học thấy người ta hay quên rằng sau mặt ngửa, khả năng ra ngửa tiếp cũng bằng khả năng ra sấp, nên dãy họ viết có quá nhiều lần đổi chiều và quá ít chuỗi ngửa liên tiếp. Nếu một đồng xu cân đối ra ngửa 30 lần liền, lần sau vẫn có khả năng ngang nhau; không có chuyện "đến lượt" ra sấp. Tương tự, số trúng xổ số tuần trước có khả năng trúng lại như mọi số khác. Biết rằng người ta mắc lỗi đổi chiều quá nhiều giải thích nhiều nước gài ở giải oẳn tù tì: người chơi cố khai thác điểm yếu này, và ở bậc cao hơn, cố khai thác việc đối thủ cố khai thác. Người ra Bao ba lần liền mong đối thủ nghĩ lần thứ tư khó là Bao; người bỏ một thứ và chỉ pha hai thứ còn lại qua nhiều ván mong đối thủ nghĩ thứ bị bỏ "sắp ra".

Để khỏi vô tình đưa trật tự vào sự ngẫu nhiên, cần một cơ chế khách quan hay độc lập, tức một quy tắc cố định nhưng bí mật và đủ phức tạp để khó bị phát hiện. Hai tác giả gợi ý:

| Cơ chế | Cách dùng |
|---|---|
| Độ dài câu trong sách | Câu có số chữ lẻ là ngửa, chẵn là sấp; mười câu liền trước trong sách (đếm ngược) cho dãy sấp, ngửa, ngửa, sấp, ngửa, ngửa, ngửa, ngửa, sấp, sấp |
| Ngày sinh bạn bè, người thân | Ngày chẵn là ngửa, ngày lẻ là sấp |
| Kim giây đồng hồ (miễn là đồng hồ không quá chính xác, để không ai khác biết vị trí kim giây) | Liếc đồng hồ ngay trước mỗi cú ném: số chẵn thì bóng nhanh, số lẻ thì forkball; muốn 40% bóng nhanh, 60% forkball thì chọn bóng nhanh khi kim giây ở khoảng 1–24, forkball khi ở khoảng 25–60 |

**Dân chuyên nghiệp ngẫu nhiên hoá tốt đến đâu?** Dữ liệu các trận chung kết grand slam quần vợt cho thấy người giao bóng có xu hướng đổi giữa giao vào thuận tay và trái tay của đối thủ nhiều hơn mức ngẫu nhiên thật (thống kê gọi là tương quan chuỗi âm, negative serial correlation), nhưng xu hướng này quá yếu để đối thủ khai thác, thể hiện ở chỗ tỷ lệ thành công của hai kiểu giao bóng khác nhau không có ý nghĩa thống kê. Với phạt đền, sự ngẫu nhiên gần đúng chuẩn, tỷ lệ đổi chiều không có ý nghĩa thống kê, có lẽ vì hai quả phạt đền của cùng một cầu thủ cách nhau nhiều tuần nên xu hướng đổi chiều yếu hơn. Các tay chơi oẳn tù tì cấp vô địch rất coi trọng chiến lược cố tình phi ngẫu nhiên. Nếu những chiến lược đó hiệu quả, người giỏi phải thắng đều qua các năm. Hiệp hội RPS Thế giới cho biết không đủ người để ghi lại kết quả từng đấu thủ, và nói chung không có nhiều người thắng ổn định một cách có ý nghĩa thống kê, dù người giành huy chương bạc năm 2003 đã lọt vào tốp 8 năm sau. Điều này gợi ý rằng các chiến lược cầu kỳ không cho lợi thế bền vững.

**Sao không ỷ vào sự ngẫu nhiên của đối thủ?** Nếu một bên dùng tỷ lệ tốt nhất thì tỷ lệ thành công của bên kia như nhau bất kể họ làm gì. Khi thủ môn bay Trái 41,7% và Phải 58,3%, cầu thủ sút Trái, Phải hay pha trộn kiểu gì cũng ghi bàn 79,6%. Từ đó cầu thủ có thể muốn khỏi tính toán, cứ sút một bên và trông vào việc thủ môn pha trộn đúng. Vấn đề là nếu bạn không dùng tỷ lệ tốt nhất, đối thủ không còn động cơ dùng tỷ lệ của họ: bạn chỉ sút Trái thì thủ môn sẽ chuyển sang chặn Trái. Lý do bạn phải dùng tỷ lệ tốt nhất của mình là để giữ đối thủ ở tỷ lệ tốt nhất của họ.

### 7. Tình huống chỉ xảy ra một lần (Unique Situations)

Các lập luận trên hợp lý với bóng bầu dục, bóng chày, quần vợt, nơi cùng một tình huống lặp lại nhiều lần trong trận và cùng những người chơi gặp nhau qua nhiều trận, nên có thời gian quan sát và đáp trả mọi hành vi có hệ thống. Còn trò chơi chỉ chơi một lần, như chọn điểm tấn công và phòng thủ trong một trận đánh, thì đối phương không thể suy ra quy luật từ hành động trước của bạn. Nhưng vẫn có lý do để chọn ngẫu nhiên: gián điệp. Nếu bạn định sẵn một hướng và đối phương phát hiện ra, họ sẽ điều chỉnh để gây bất lợi lớn nhất cho bạn. Muốn làm đối phương bất ngờ, cách chắc chắn nhất là làm chính mình bất ngờ: giữ các phương án mở càng lâu càng tốt, và vào phút chót chọn giữa chúng bằng một cơ chế không đoán trước được, do đó không gián điệp nào đánh cắp được. Tỷ lệ của cơ chế đó cũng phải sao cho nếu đối phương biết được tỷ lệ, họ không biến được hiểu biết ấy thành lợi thế, tức chính là tỷ lệ tốt nhất tính theo cách ở trên.

Cuối cùng là một lời cảnh báo: dùng tỷ lệ tốt nhất vẫn có lúc nhận kết quả tồi; cầu thủ sút khó đoán đến đâu thì thủ môn thỉnh thoảng vẫn đoán đúng. Trong bóng bầu dục Mỹ, ở lượt tấn công thứ ba (third down) khi chỉ còn một yard nữa là đạt mục tiêu, chạy bóng thẳng vào giữa là lối chơi có xác suất thành công cao; nhưng thỉnh thoảng phải tung một đường chuyền dài (gọi là "bomb") để hàng phòng ngự không dồn hết vào giữa. Chuyền thành công thì người hâm mộ và bình luận viên khen huấn luyện viên là thiên tài; thất bại thì ông bị chỉ trích vì đã đánh cược thay vì chọn lối chơi chắc. Theo hai tác giả, thời điểm biện minh cho chiến lược là trước khi dùng nó ở bất kỳ lần cụ thể nào: huấn luyện viên nên công khai rằng pha trộn là thiết yếu, rằng chạy bóng vào giữa vẫn là lối chơi chắc chính vì đối phương phải dành một phần lực lượng đề phòng những đường chuyền dài thỉnh thoảng xuất hiện. Dù vậy, hai tác giả ngờ rằng kể cả khi huấn luyện viên đã nói điều này trên mọi tờ báo và kênh truyền hình trước trận, rồi chuyền dài và thất bại, ông vẫn bị chỉ trích y như khi chưa hề giảng giải gì về lý thuyết trò chơi.

### 8. Chiến lược hỗn hợp trong trò chơi động cơ hỗn hợp (Mixing Strategies in Mixed-Motives Games)

Đến đây chương chỉ xét trò chơi xung đột thuần tuý. Nhưng phần lớn trò chơi thực tế có cả lợi ích chung lẫn xung đột. Pha trộn có vai trò ở đó không? Theo hai tác giả: có, nhưng kèm điều kiện.

Ví dụ là phiên bản đi săn của trò chơi "cuộc chiến giới tính" (battle of the sexes) ở Chương 4. Hai thợ săn thời đồ đá Fred và Barney, mỗi người ở trong hang riêng, quyết định hôm nay đi săn hươu (Stag) hay bò rừng (Bison). Săn thành công cần cả hai người, nên nếu chọn khác nhau thì không ai có thịt; hai người có lợi ích chung trong việc tránh điều đó. Nhưng giữa hai kết quả thành công, Fred thích thịt hươu hơn (cùng săn hươu được 4 thay vì 3), còn Barney ngược lại. Bảng kết quả (dựng lại từ sách; mỗi ô ghi kết quả của Fred trước, của Barney sau; hai ô cùng săn là hai cân bằng Nash, được tô đậm trong sách):

| Fred \ Barney | Barney săn hươu | Barney săn bò rừng |
|---|---|---|
| Fred săn hươu | **4 ; 3** | 0 ; 0 |
| Fred săn bò rừng | 0 ; 0 | **3 ; 4** |

Hai cân bằng Nash này nay được gọi là cân bằng trong chiến lược thuần tuý. Có cân bằng hỗn hợp không? Fred có thể pha trộn vì không chắc Barney chọn gì. Nếu Fred cho rằng Barney chọn hươu với xác suất y và bò rừng với xác suất (1–y), thì Fred săn hươu được 4y + 0(1–y) = 4y, săn bò rừng được 0y + 3(1–y). Khi 4y = 3(1–y), tức 3 = 7y, hay y = 3/7, Fred được như nhau dù chọn hươu, bò rừng hay pha trộn theo tỷ lệ nào. Đồng thời, nếu Fred chọn hươu với tỷ lệ x = 4/7 (trò chơi đối xứng nên đoán hay tính đều ra), Barney bàng quan giữa hai lựa chọn nên sẵn sàng pha đúng tỷ lệ 3/7 để giữ Fred bàng quan. Cặp x = 4/7 và y = 3/7 là cân bằng Nash trong chiến lược hỗn hợp.

Cân bằng này có ba nhược điểm:

| Nhược điểm | Con số trong sách |
|---|---|
| Kết quả thấp: vì hai người chọn độc lập, họ hay lạc nhau | Fred săn hươu khi Barney săn bò rừng (4/7) × (4/7) = 16/49 số lần; ngược lại (3/7) × (3/7) = 9/49 số lần; tổng cộng 25/49, hơn một nửa số lần, cả hai về tay không. Mỗi người được 4 × (3/7) + 0 × (4/7) = 12/7 = 1,71, thấp hơn cả mức 3 ở cân bằng thuần tuý kém thuận lợi cho mình |
| Mong manh, không bền | Nếu Fred ước lượng xác suất Barney săn hươu chỉ nhích trên 3/7 = 0,42857, chẳng hạn 0,43, thì săn hươu cho 4 × 0,43 + 0 × 0,57 = 1,72, hơn săn bò rừng 0 × 0,43 + 3 × 0,57 = 1,71; Fred thôi pha trộn mà săn hươu hẳn, Barney đáp lại tốt nhất cũng là săn hươu, và cân bằng hỗn hợp sụp đổ |
| Kỳ lạ, ngược trực giác | Đổi kết quả của Barney thành 6 và 7 (thay cho 3 và 4), giữ nguyên của Fred. Fred vẫn bàng quan khi y = 3/7, nên tỷ lệ của Barney không đổi. Nhưng Barney bàng quan khi 6x = 7(1–x), tức x = 7/13: tỷ lệ của Fred thay đổi dù kết quả của Fred không đổi |

Về điểm thứ ba, hai tác giả giải thích rằng nghĩ kỹ thì không lạ: Barney chịu pha trộn chỉ vì không chắc Fred làm gì, nên phép tính liên quan tới kết quả của Barney và xác suất lựa chọn của Fred; giải ra thì tỷ lệ của Fred "do" kết quả của Barney quyết định, và ngược lại. Nhưng lập luận này tinh tế và lúc đầu nghe kỳ quặc đến mức phần lớn người tham gia thí nghiệm không nhận ra, kể cả khi được gợi ý ngẫu nhiên hoá: họ đổi tỷ lệ pha trộn khi kết quả của chính họ thay đổi, chứ không phải khi kết quả của đối phương thay đổi.

**Pha trộn có phối hợp.** Để tránh lạc nhau, hai người cần pha trộn có phối hợp. Ngồi trong hai hang riêng, không liên lạc được, họ có thể thoả thuận trước dựa vào một điều cả hai cùng quan sát khi ra khỏi hang. Giả sử vùng họ ở có mưa buổi sáng vào một nửa số ngày; họ hẹn trời mưa thì cùng săn hươu, trời khô thì cùng săn bò rừng. Khi đó mỗi người được trung bình 1/2 × 3 + 1/2 × 4 = 3,5. Ngẫu nhiên hoá có phối hợp là một cách gọn để chia đôi khoảng cách giữa cân bằng thuần tuý có lợi và cân bằng thuần tuý bất lợi cho mỗi người, tức là một công cụ đàm phán.

### 9. Pha trộn trong kinh doanh và các cuộc chiến khác (Mixing in Business and Other Wars)

Vì sao các ví dụ về chiến lược hỗn hợp đều lấy từ thể thao, còn kinh doanh, chính trị, chiến tranh lại hiếm? Thứ nhất, phần lớn các trò chơi đó không phải tổng bằng không, và như đã thấy, vai trò của pha trộn ở đó hạn chế, mong manh và không chắc dẫn tới kết quả tốt. Thứ hai, khó đưa ý tưởng để kết quả cho may rủi quyết định vào một văn hoá doanh nghiệp muốn kiểm soát kết quả, nhất là khi mọi việc hỏng, điều chắc chắn thỉnh thoảng xảy ra khi chọn nước đi ngẫu nhiên. (Một số) người hiểu rằng huấn luyện viên bóng bầu dục thỉnh thoảng phải cho giả vờ đá phạt punt để hàng thủ không chủ quan, nhưng một chiến lược mạo hiểm tương tự trong kinh doanh có thể khiến bạn mất việc nếu thất bại. Điểm mấu chốt không phải là chiến lược mạo hiểm luôn thành công, mà là nó tránh được nguy cơ của khuôn mẫu cố định và sự dễ đoán.

**Phiếu giảm giá.** Doanh nghiệp dùng phiếu giảm giá để giành thị phần: hút khách mới mà không phải giảm giá cho khách hiện có. Nếu các đối thủ cùng phát phiếu một lúc, khách không có lý do đổi nhãn hàng, họ ở lại với nhãn hiện tại và hưởng giảm giá. Chỉ khi một hãng phát phiếu còn hãng khác thì không, khách mới thử sản phẩm. Trò chơi phiếu giảm giá giữa Coke và Pepsi vì thế giống bài toán phối hợp của hai thợ săn: mỗi hãng muốn là hãng duy nhất phát phiếu, như Fred và Barney mỗi người muốn săn ở bãi mình thích; cùng làm một lúc thì tác dụng triệt tiêu và cả hai thiệt. Một giải pháp là theo lịch cố định, phát phiếu sáu tháng một lần, và hai hãng học cách luân phiên. Nhưng khi Coke đoán Pepsi sắp phát phiếu, Coke nên phát trước để chặn. Cách duy nhất tránh bị chặn trước là giữ yếu tố bất ngờ bằng chiến lược ngẫu nhiên. Tất nhiên, ngẫu nhiên hoá độc lập có nguy cơ "lạc nhau" như Fred và Barney; các hãng làm tốt hơn nhiều nếu hợp tác. Hai tác giả nêu bằng chứng thống kê mạnh rằng Coke và Pepsi đã làm vậy: trong một khoảng 52 tuần, mỗi hãng khuyến mãi giảm giá 26 tuần và không có tuần nào trùng nhau. Theo sách, nếu mỗi hãng chọn khuyến mãi ngẫu nhiên mỗi tuần với xác suất 50%, độc lập với hãng kia, thì xác suất không trùng tuần nào là 1/495.918.532.948.104, mà sách diễn đạt là "ít hơn một phần triệu tỷ (một tỷ tỷ)". (Người tổng hợp lưu ý: con số này đúng là xác suất để hai lịch 26 tuần chọn ngẫu nhiên khớp vừa khít không trùng nhau, khoảng 1 phần 500 nghìn tỷ; nó không khớp với mô tả "50% mỗi tuần, độc lập", và cũng không nhỏ hơn một phần triệu tỷ. Xem thêm phần Đánh giá. Kết luận chính vẫn đứng vững: khả năng xảy ra ngẫu nhiên là cực nhỏ.) Phát hiện này gây ngạc nhiên tới mức lên cả chương trình *60 Minutes* của đài CBS.

Hai tác giả phân tích thêm: mục đích của phiếu giảm giá là mở rộng thị phần, và mỗi hãng hiểu rằng muốn thành công thì phải khuyến mãi khi hãng kia không khuyến mãi. Chọn ngẫu nhiên tuần khuyến mãi có thể nhằm bắt đối thủ trở tay không kịp, nhưng khi cả hai cùng làm vậy thì có nhiều tuần cả hai cùng khuyến mãi; những tuần đó chiến dịch triệt tiêu nhau, không hãng nào tăng thị phần và cả hai đều giảm lợi nhuận. Chiến lược này tạo ra thế lưỡng nan của người tù. Vì hai hãng có quan hệ lâu dài, họ nhận ra cả hai có thể làm tốt hơn bằng cách giải thế lưỡng nan: mỗi hãng lần lượt có giá thấp nhất, rồi khi khuyến mãi kết thúc, khách hàng quay về nhãn quen thuộc của mình. Đó đúng là điều họ đã làm.

**Vé máy bay giờ chót.** Một số hãng hàng không bán vé giảm giá cho khách sẵn sàng mua sát giờ bay, nhưng không cho biết còn bao nhiêu ghế để khách ước lượng cơ hội. Nếu khả năng còn vé giờ chót dễ đoán hơn, khách sẽ dễ lợi dụng hệ thống và hãng sẽ mất nhiều khách vốn trả giá thường.

**Kiểm tra ngẫu nhiên.** Ứng dụng phổ biến nhất của chiến lược ngẫu nhiên trong kinh doanh là buộc tuân thủ với chi phí giám sát thấp hơn, từ kiểm tra thuế tới xét nghiệm ma tuý và đồng hồ tính tiền đỗ xe. Nó cũng giải thích vì sao hình phạt không nhất thiết phải "tương xứng" với vi phạm.

| Phương án thi hành phí đỗ xe 1 USD/giờ | Hệ quả |
|---|---|
| Phạt 1,01 USD, chắc chắn bắt được mọi lần đỗ không trả tiền | Đủ để người ta trung thực, nhưng rất tốn kém: lương nhân viên giao thông là khoản lớn nhất, chi phí vận hành cơ chế thu phạt để chính sách đáng tin cũng đáng kể |
| Phạt 25 USD, xác suất bị bắt 1/25 | Hiệu quả như nhau, cần lực lượng nhỏ hơn nhiều, tiền phạt thu được gần bù đủ chi phí quản lý |
| Không kiểm tra | Chỗ đỗ xe khan hiếm bị lạm dụng |

Đây là một trường hợp nữa của chiến lược hỗn hợp, vừa giống vừa khác ví dụ bóng đá. Giống ở chỗ cơ quan quản lý chọn chiến lược ngẫu nhiên vì nó tốt hơn mọi cách làm có hệ thống (không kiểm tra thì lạm dụng, kiểm tra 100% thì quá tốn). Khác ở chỗ phía công chúng đỗ xe không nhất thiết dùng chiến lược ngẫu nhiên; trái lại, cơ quan quản lý muốn xác suất kiểm tra và mức phạt đủ lớn để công chúng tuân thủ hoàn toàn.

Xét nghiệm ma tuý ngẫu nhiên có nhiều đặc điểm tương tự: xét nghiệm mọi nhân viên mỗi ngày vừa tốn thời gian, tiền bạc vừa không cần thiết; xét nghiệm ngẫu nhiên sẽ phát hiện những người không thể làm việc mà không dùng ma tuý và răn đe người khác khỏi dùng cho vui. Xác suất bị phát hiện nhỏ nhưng hình phạt khi bị bắt lớn. Hai tác giả cho rằng đây là một vấn đề trong chiến lược kiểm tra của Sở Thuế Mỹ (IRS): tiền phạt nhỏ so với khả năng bị phát hiện. Khi thi hành ngẫu nhiên, hình phạt phải nặng hơn vi phạm. Quy tắc đúng là hình phạt kỳ vọng (expected punishment), tính theo nghĩa thống kê có xét tới xác suất bị bắt, mới phải tương xứng với vi phạm.

**Mồi nhử.** Bên muốn qua mặt sự kiểm tra cũng dùng được chiến lược ngẫu nhiên: giấu vi phạm thật giữa nhiều báo động giả hay mồi nhử để nguồn lực của bên kiểm tra bị dàn mỏng. Một hệ thống phòng không phải tiêu diệt gần 100% tên lửa bay tới. Cách tốn ít chi phí để vượt qua nó là bao quanh tên lửa thật bằng một "đội cận vệ" tên lửa mồi, vốn rẻ hơn nhiều so với tên lửa thật; trừ khi phân biệt được hoàn hảo, bên phòng thủ buộc phải chặn mọi tên lửa, thật lẫn giả. Việc bắn đạn lép bắt đầu từ Thế chiến II, không phải do chủ ý thiết kế mồi nhử mà để giải quyết vấn đề kiểm soát chất lượng: loại bỏ đạn hỏng trong sản xuất rất tốn kém, nên có người nảy ra ý chế tạo đạn lép và bắn chúng một cách ngẫu nhiên; chỉ huy quân sự không thể để một quả bom nổ chậm nằm dưới vị trí của mình và không biết quả nào là quả nào, nên đòn nghi binh buộc ông phải xử lý mọi quả đạn chưa nổ rơi xuống. Khi chi phí phòng thủ tỷ lệ với số tên lửa phải bắn hạ, bên tấn công có thể đẩy chi phí đó lên mức không chịu nổi. Đây là một trong những thách thức lớn khi thiết kế hệ thống phòng thủ tên lửa "Star Wars" (Chiến tranh giữa các vì sao), và theo hai tác giả có thể không có lời giải.

### 10. Cách tìm cân bằng chiến lược hỗn hợp (How to Find Mixed Strategy Equilibria) và Những thay đổi bất ngờ trong tỷ lệ pha trộn (Surprising Changes in Mixtures)

Hai tác giả nói nhiều người đọc chỉ cần hiểu chiến lược hỗn hợp ở mức khái niệm và để máy tính tính con số (phần mềm xử lý được trường hợp mỗi bên có nhiều chiến lược thuần tuý, kể cả những chiến lược không được dùng trong cân bằng); họ có thể bỏ qua phần này. Phần này dành cho người biết chút đại số và hình học phổ thông.

**Phương pháp đại số.** Gọi x là tỷ lệ sút Trái của cầu thủ, (1–x) là tỷ lệ sút Phải.

| Bên | Kết quả gặp đối thủ chọn Trái | Kết quả gặp đối thủ chọn Phải | Cho bằng nhau | Lời giải |
|---|---|---|---|---|
| Cầu thủ sút (x là tỷ lệ sút Trái) | 58x + 93(1–x) = 93 – 35x | 95x + 70(1–x) = 70 + 25x | 93 – 35x = 70 + 25x, tức 23 = 60x | x = 23/60 = 0,383 |
| Thủ môn (y là tỷ lệ bay Trái; kết quả là tỷ lệ ghi bàn của cầu thủ khi cầu thủ sút Trái hoặc Phải) | Cầu thủ sút Trái: 58y + 95(1–y) = 95 – 37y | Cầu thủ sút Phải: 93y + 70(1–y) = 70 + 23y | 95 – 37y = 70 + 23y, tức 25 = 60y | y = 25/60 = 0,417 |

**Phương pháp đồ thị, nhìn từ cầu thủ sút** (hình dựng lại từ sách). Trục ngang là x, tỷ lệ sút Trái, đi từ 0 đến 1. Đường "gặp thủ môn bay Trái" (93 – 35x) đi từ 93 xuống 58; đường "gặp thủ môn bay Phải" (70 + 25x) đi từ 70 lên 95. Nếu biết tỷ lệ của cầu thủ, thủ môn sẽ chọn bên cho đường thấp hơn; phần thấp hơn của hai đường (vẽ đậm) tạo thành hình chữ V ngược, là mức thành công tối thiểu cầu thủ có thể trông đợi. Cầu thủ chọn mức cao nhất trong các mức tối thiểu đó, ở đỉnh chữ V ngược, nơi hai đường cắt nhau: x = 0,383, tỷ lệ thành công 79,6% (lớn nhất của các mức nhỏ nhất, maximin).

| x (tỷ lệ sút Trái) | Đường "thủ môn bay Trái" (93 – 35x) | Đường "thủ môn bay Phải" (70 + 25x) | Đường thấp hơn (thủ môn khai thác) |
|---|---|---|---|
| 0 | 93 | 70 | 70 |
| 0,383 | 79,6 | 79,6 | 79,6 (đỉnh chữ V ngược) |
| 1 | 58 | 95 | 58 |

**Phương pháp đồ thị, nhìn từ thủ môn** (hình dựng lại từ sách). Trục ngang là y, tỷ lệ bay Trái của thủ môn. Đường "cầu thủ sút Trái" (95 – 37y) đi từ 95 xuống 58; đường "cầu thủ sút Phải" (70 + 23y) đi từ 70 lên 93. Với mỗi tỷ lệ của thủ môn, cầu thủ chọn bên cho đường cao hơn; phần cao hơn (vẽ đậm) tạo hình chữ V. Thủ môn muốn tỷ lệ ghi bàn thấp nhất nên chọn đáy chữ V: y = 0,417, tỷ lệ ghi bàn 79,6% (nhỏ nhất của các mức lớn nhất, minimax).

| y (tỷ lệ bay Trái) | Đường "cầu thủ sút Trái" (95 – 37y) | Đường "cầu thủ sút Phải" (70 + 23y) | Đường cao hơn (cầu thủ khai thác) |
|---|---|---|---|
| 0 | 95 | 70 | 95 |
| 0,417 | 79,6 | 79,6 | 79,6 (đáy chữ V) |
| 1 | 58 | 93 | 93 |

Việc maximin của cầu thủ bằng minimax của thủ môn chính là định lý minimax của von Neumann và Morgenstern đang vận hành. Hai tác giả nói có lẽ chính xác hơn phải gọi là "định lý maximin bằng minimax", nhưng tên thông dụng ngắn và dễ nhớ hơn.

**Những thay đổi bất ngờ trong tỷ lệ pha trộn.** Ngay trong trò chơi tổng bằng không, cân bằng hỗn hợp cũng có tính chất nghe kỳ lạ. Giả sử thủ môn tập luyện để bắt tốt hơn những cú sút về phía thuận (Phải) của cầu thủ, khiến tỷ lệ ghi bàn ở ô (sút Phải, thủ môn bay Phải) giảm từ 70% xuống 60%. Trên đồ thị nhìn từ thủ môn, đường "cầu thủ sút Phải" dịch xuống, bắt đầu từ 60 thay vì 70 (hình dựng lại từ sách):

| Đường trên đồ thị | Tại y = 0 | Tại y = 1 | Giao điểm với đường "cầu thủ sút Trái" |
|---|---|---|---|
| Cầu thủ sút Trái (không đổi) | 95 | 58 | — |
| Cầu thủ sút Phải, cũ | 70 | 93 | y = 0,417, mức 79,6 |
| Cầu thủ sút Phải, mới (93y + 60(1–y) = 60 + 33y) | 60 | 93 | y = 0,50, mức 76,5 |

| Chỉ tiêu cân bằng | Trước (ô Phải–Phải là 70) | Sau (ô Phải–Phải là 60) |
|---|---|---|
| Tỷ lệ bay Trái của thủ môn | 41,7% | 50% |
| Tỷ lệ sút Trái của cầu thủ | 38,3% | 47,1% |
| Tỷ lệ ghi bàn trong cân bằng | 79,6% | 76,5% |

Thủ môn giỏi hơn ở phía Phải thì lại bay về phía Phải ít hơn. Nghe lạ, nhưng lý do dễ hiểu: khi thủ môn bắt tốt hơn ở phía Phải, cầu thủ sút về phía đó ít đi; đáp lại việc nhiều cú sút về phía Trái hơn, thủ môn chọn Trái nhiều hơn. Hai tác giả tóm lại: mục đích của việc cải thiện điểm yếu là để bạn không phải dùng nó thường xuyên. Công tập luyện vẫn có lợi: tỷ lệ ghi bàn trung bình trong cân bằng giảm từ 79,6% xuống 76,5%. Nghịch lý bề ngoài này có logic rất tự nhiên của lý thuyết trò chơi: điều tốt nhất cho bạn phụ thuộc không chỉ vào việc bạn làm mà vào việc những người chơi khác làm. Đó chính là bản chất của sự phụ thuộc lẫn nhau trong chiến lược.

### 11. Tình huống: trò Janken leo bậc (Case Study: Janken Step Game)

> **Chú thích của tác giả:** Tình huống này xuất hiện lần đầu trong bản tiếng Nhật của *Thinking Strategically*. Nó là kết quả dự án của Takashi Kanno và Yuichi Shimazu khi còn là sinh viên Trường Quản trị Yale; hai người cũng là dịch giả bản tiếng Nhật của cuốn sách đó.

**Đề bài.** Ở một quán sushi trung tâm Tokyo, Takashi và Yuichi uống rượu sake chờ món. Cả hai gọi món đặc biệt của quán, uni sashimi (nhím biển), nhưng đầu bếp báo chỉ còn một phần. Ai nhường ai? Ở Mỹ, hai người có thể tung đồng xu; ở Nhật, họ thường chơi Janken, tức oẳn tù tì. Để bài toán khó hơn, hai tác giả dùng biến thể Janken leo bậc, chơi trên một cầu thang: hai người cùng ra Búa, Bao hoặc Kéo; người thắng leo lên 5 bậc nếu thắng bằng Bao (năm ngón), 2 bậc nếu thắng bằng Kéo (hai ngón), 1 bậc nếu thắng bằng Búa (không ngón nào); hoà thì chơi lại. Bình thường ai lên tới đỉnh trước thì thắng; hai tác giả đơn giản hoá bằng giả định mỗi người chỉ muốn vượt người kia càng nhiều bậc càng tốt. Tìm tỷ lệ pha trộn cân bằng.

**Lời giải của sách.** Mỗi bậc đưa người thắng lên trước và người thua tụt lại đúng bấy nhiêu, nên đây là trò chơi tổng bằng không. Bảng kết quả tính bằng số bậc dẫn trước (dựng lại từ sách; mỗi ô ghi kết quả của Takashi, Yuichi được số ngược dấu):

| Takashi \ Yuichi | Búa | Bao | Kéo |
|---|---|---|---|
| Búa | 0 | –5 | 1 |
| Bao | 5 | 0 | –2 |
| Kéo | –1 | 2 | 0 |

Câu hỏi đầu tiên là chiến lược nào có mặt trong cân bằng. Câu trả lời: cả ba. Giả sử Yuichi không bao giờ ra Búa; thì Takashi không bao giờ ra Bao (Bao chỉ có lợi khi gặp Búa); thì Yuichi không bao giờ ra Kéo; thì Takashi không bao giờ ra Búa; thì Yuichi không bao giờ ra Bao. Giả định ban đầu loại hết mọi chiến lược của Yuichi nên phải sai. Lập luận tương tự cho thấy hai chiến lược còn lại cũng không thể thiếu.

Người chơi muốn tối đa kết quả chứ không pha trộn cho vui; Yuichi chỉ sẵn sàng pha trộn cả ba khi cả ba hấp dẫn như nhau (nếu Búa cho Yuichi kết quả cao hơn thì anh ta chỉ ra Búa, và đó không phải cân bằng). Vì vậy điều kiện cả ba chiến lược cho Yuichi cùng kết quả kỳ vọng xác định tỷ lệ pha trộn cân bằng của Takashi. Gọi p là xác suất Takashi ra Bao, q là xác suất ra Kéo, 1–(p+q) là xác suất ra Búa. Kết quả của Yuichi:

| Yuichi ra | Kết quả kỳ vọng |
|---|---|
| Búa | –5p + 1q + 0(1–(p+q)) = –5p + q |
| Kéo | 2p + 0q – 1(1–(p+q)) = 3p + q – 1 |
| Bao | 0p – 2q + 5(1–(p+q)) = –5p – 7q + 5 |

Cho ba biểu thức bằng nhau: –5p + q = 3p + q – 1 cho 8p = 1; –5p + q = –5p – 7q + 5 cho 8q = 5. Vậy p = 1/8 (Bao), q = 5/8 (Kéo), 1–p–q = 2/8 (Búa). Trò chơi đối xứng nên Yuichi dùng cùng tỷ lệ. Khi cả hai dùng tỷ lệ cân bằng, kết quả kỳ vọng từ mỗi chiến lược bằng 0. Điều này không đúng với mọi cân bằng hỗn hợp, nhưng luôn đúng với trò chơi tổng bằng không đối xứng: không có lý do gì để người này được lợi hơn người kia. Hai tác giả cho biết Chương 14 có thêm một tình huống về lựa chọn và may rủi: "Lừa mọi người trong một lúc: máy đánh bạc ở Las Vegas" (Fooling All the People Some of the Time: The Las Vegas Slots).

Một điểm đáng chú ý về con số (nhận xét của người tổng hợp): Bao, thứ thắng được nhiều bậc nhất, lại được ra ít nhất (1/8), còn Kéo được ra nhiều nhất (5/8). Lý do là theo nguyên tắc bàng quan, mỗi người chọn tỷ lệ để đối thủ không khai thác được: Bao thắng lớn khi gặp Búa, nên đối thủ ra Búa ít; Búa ít xuất hiện thì Bao ít có cơ hội; Kéo khắc Bao và chỉ thua Búa một bậc, nên trở thành lựa chọn an toàn.

**Ví dụ hôm nay** (minh hoạ của người tổng hợp, con số giả định). Một chuỗi bán lẻ có 20 cửa hàng muốn chống gian lận thu ngân. Kiểm kê đột xuất toàn bộ 20 cửa hàng mỗi tuần tốn 200 triệu đồng mỗi tháng. Giả sử một thu ngân gian lận được trung bình 2 triệu đồng mỗi tháng nếu không bị phát hiện. Theo logic hình phạt kỳ vọng, chuỗi có thể chỉ kiểm tra ngẫu nhiên 2 cửa hàng mỗi tuần (xác suất mỗi cửa hàng bị kiểm trong một tuần là 10%, trong một tháng khoảng 34%) với chi phí 20 triệu đồng, miễn là hậu quả khi bị phát hiện (sa thải, bồi hoàn, mất khoản thưởng tích luỹ, tổng giả định 15 triệu đồng) đủ lớn để hình phạt kỳ vọng (khoảng 0,34 × 15 = 5,1 triệu đồng) vượt xa 2 triệu đồng gian lận. Điều quan trọng là lịch kiểm tra phải thật sự ngẫu nhiên, bằng cách bốc thăm hay dùng số ngẫu nhiên, chứ không phải "tuần này cửa hàng 1 và 2, tuần sau cửa hàng 3 và 4"; một lịch luân phiên dễ đoán sẽ cho thu ngân biết chính xác lúc nào an toàn, đúng như cầu thủ ném bóng chày ném luân phiên bị người đánh bóng bắt bài.

## Luận điểm kinh tế cốt lõi

### Mệnh đề

Trong trò chơi mà để đối thủ biết trước lựa chọn của mình là bất lợi, người chơi hợp lý nên chọn ngẫu nhiên theo một tỷ lệ tính trước, sao cho đối thủ dùng phương án nào cũng thu được như nhau. Khi cả hai bên làm vậy, ta có cân bằng Nash trong chiến lược hỗn hợp; với trò chơi hai người tổng bằng không, đây chính là định lý minimax. Ngoài thể thao, logic này giải thích kiểm tra ngẫu nhiên, mồi nhử và khuyến mãi bất ngờ; nhưng trong trò chơi có lợi ích chung, pha trộn độc lập cho kết quả kém, và phối hợp hay thay phiên tốt hơn.

### Giả định

- Hai bên chọn đồng thời, hoặc ít nhất không bên nào quan sát được lựa chọn của bên kia trước khi hành động.
- Trong phần chính của chương, lợi ích hai bên đối nghịch hoàn toàn (tổng bằng không hoặc tổng không đổi).
- Người chơi quan tâm tới kết quả trung bình (kỳ vọng) qua nhiều lần chơi, và biết bảng kết quả.
- Đối thủ đủ tinh để phát hiện và khai thác mọi khuôn mẫu; nếu đối thủ kém thì khai thác khuôn mẫu của họ có thể tốt hơn pha trộn cân bằng.
- Người chơi có thể tạo ra sự ngẫu nhiên thật bằng một cơ chế khách quan và bí mật.

### Cơ chế

1. Trong trò chơi xung đột thuần tuý, mỗi lựa chọn cố định đều có một cách đáp trả tốt nhất của đối thủ, nên vòng đoán qua đoán lại không dừng và không có cân bằng thuần tuý.
2. Pha trộn ngẫu nhiên làm cho đối thủ không biết lần này mình chọn gì; họ chỉ có thể phản ứng với tỷ lệ pha trộn.
3. Tỷ lệ pha trộn tốt nhất làm cho mọi phương án của đối thủ cho cùng một kết quả, nên đối thủ không có gì để khai thác (nguyên tắc bàng quan).
4. Khi đối thủ đã bàng quan, họ sẵn sàng dùng tỷ lệ pha trộn tốt nhất của chính họ; hai tỷ lệ tạo thành cân bằng Nash, và trong trò chơi tổng bằng không, maximin của bên này bằng minimax của bên kia.
5. Vì tỷ lệ của mỗi bên được quyết định bởi kết quả của bên kia, thay đổi năng lực của một bên làm thay đổi tỷ lệ của cả hai theo những hướng nghe ngược trực giác (thủ môn giỏi bên Phải thì bay bên Phải ít hơn).
6. Trong thi hành pháp luật, sự ngẫu nhiên cho phép thay xác suất kiểm tra cao bằng mức phạt cao, giữ nguyên hình phạt kỳ vọng nhưng giảm chi phí giám sát.

### Bằng chứng và ví dụ hai tác giả đưa ra

- Cảnh hai chén rượu độc trong phim *The Princess Bride*: suy luận xoay vòng của Vizzini.
- Số liệu phạt đền của Palacios-Huerta (Ý, Tây Ban Nha, Anh 1995–2000): tỷ lệ thực tế 40,0% và 42,3% rất gần lý thuyết 38,3% và 41,7%.
- Quần vợt chuyên nghiệp: tỷ lệ pha trộn khớp lý thuyết; có tương quan chuỗi âm nhưng quá yếu để bị khai thác.
- Giải vô địch oẳn tù tì thế giới 2005 và các "nước gài" của người chơi; thủ môn Bồ Đào Nha cản ba quả phạt đền trước Anh ở World Cup 2006.
- Thí nghiệm kinh tế học: người tham gia hầu như không tung đồng xu; liên hệ với thí nghiệm của Stanley Milgram.
- Trò chơi đi săn của Fred và Barney: cân bằng hỗn hợp cho 1,71, kém xa 3,5 khi phối hợp theo trời mưa.
- Coke và Pepsi: 52 tuần, mỗi hãng 26 tuần khuyến mãi, không tuần nào trùng.
- Phạt đỗ xe 25 USD với xác suất bị bắt 1/25; xét nghiệm ma tuý ngẫu nhiên; mức phạt thấp của IRS.
- Tên lửa mồi, đạn lép trong Thế chiến II, thách thức của hệ thống phòng thủ "Star Wars".
- Tình huống Janken leo bậc: tỷ lệ cân bằng Bao 1/8, Kéo 5/8, Búa 2/8.

### Kết luận và hàm ý chính sách

- Sự dễ đoán là một điểm yếu có thể bị khai thác; khi lợi ích đối nghịch, hãy chủ động ngẫu nhiên hoá bằng một cơ chế khách quan, không dựa vào cảm giác.
- Không ỷ vào việc đối thủ đã pha trộn tốt; phải tự giữ tỷ lệ tốt nhất để buộc đối thủ giữ tỷ lệ của họ.
- Đánh giá một quyết định ngẫu nhiên theo chất lượng của chiến lược, không theo kết quả của một lần; nên giải thích chiến lược trước khi dùng.
- Trong thi hành pháp luật và quản trị nội bộ, thiết kế sao cho hình phạt kỳ vọng tương xứng với vi phạm; kiểm tra ngẫu nhiên kết hợp mức phạt đủ cao rẻ hơn kiểm tra toàn diện.
- Khi có lợi ích chung, ưu tiên phối hợp (tín hiệu chung, luân phiên) thay vì pha trộn độc lập.

### Trong ngôn ngữ kinh tế học

- **Cân bằng Nash hỗn hợp (mixed-strategy Nash equilibrium).** John Nash (1950) chứng minh mọi trò chơi hữu hạn đều có ít nhất một cân bằng nếu cho phép chiến lược hỗn hợp; chương này là bản giới thiệu phổ thông của kết quả đó.
- **Định lý minimax (von Neumann, 1928).** Kết quả nền móng của lý thuyết trò chơi, được trình bày lại trong *Theory of Games and Economic Behavior* (1944) của von Neumann và Morgenstern.
- **Lý giải theo niềm tin (purification / beliefs interpretation).** Trong ví dụ Fred và Barney, hai tác giả diễn giải pha trộn như sự không chắc chắn của mỗi người về lựa chọn của người kia; đây là cách diễn giải mà John Harsanyi phát triển thành lý thuyết.
- **Cân bằng tương quan (correlated equilibrium).** Việc Fred và Barney dùng trời mưa làm tín hiệu chung là ví dụ của khái niệm do Robert Aumann (1974) đưa ra: một tín hiệu ngẫu nhiên chung giúp người chơi phối hợp và đạt kết quả tốt hơn cân bằng hỗn hợp độc lập.
- **Kinh tế học về tội phạm và thi hành pháp luật.** Lập luận "phạt nặng, kiểm tra ít" tương ứng với mô hình của Gary Becker (1968) về tội phạm và hình phạt: người vi phạm so sánh lợi ích với hình phạt kỳ vọng.
- **Ngụy biện của con bạc (gambler's fallacy).** Niềm tin rằng sau nhiều lần ngửa thì "đến lượt" ra sấp; đây là nguồn gốc của việc con người đổi chiều quá nhiều khi cố tạo dãy ngẫu nhiên.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong chương |
|---|---|
| Mixed strategy | Chiến lược hỗn hợp: chọn ngẫu nhiên giữa các phương án theo tỷ lệ định trước |
| Pure strategy | Chiến lược thuần tuý: chọn hẳn một phương án |
| Randomization | Ngẫu nhiên hoá |
| Simultaneous game | Trò chơi đồng thời |
| Payoff table | Bảng kết quả |
| Zero-sum game | Trò chơi tổng bằng không: cái được của bên này là cái mất của bên kia |
| Constant-sum game | Trò chơi tổng không đổi: tổng kết quả hai bên luôn bằng một hằng số |
| Minimax theorem | Định lý minimax: mức nhỏ nhất của các mức tối đa bằng mức lớn nhất của các mức tối thiểu |
| Minimax / maximin | Nhỏ nhất của các mức lớn nhất / lớn nhất của các mức nhỏ nhất |
| Nash equilibrium in mixed strategies | Cân bằng Nash trong chiến lược hỗn hợp |
| Dominant strategy | Chiến lược trội |
| Kicker / goalie | Cầu thủ sút phạt đền / thủ môn |
| Natural side | Phía thuận của cầu thủ sút (người thuận chân phải sút về phía tay phải thủ môn) |
| Penalty shoot-out | Loạt sút luân lưu |
| Chaos Play | "Lối chơi Hỗn loạn": ra mỗi thứ 1/3 trong oẳn tù tì |
| Gambit | Nước gài: chuỗi nước đi cố ý tạo khuôn mẫu để lừa đối thủ |
| Negative serial correlation | Tương quan chuỗi âm: xu hướng đổi chiều nhiều hơn mức ngẫu nhiên |
| Fastball / forkball | Bóng nhanh / bóng forkball (bóng rơi đột ngột) trong bóng chày |
| Third down, bomb, fake a punt | Lượt tấn công thứ ba, đường chuyền dài, giả vờ đá punt (bóng bầu dục Mỹ) |
| Battle of the sexes | "Cuộc chiến giới tính": trò chơi phối hợp mà hai bên thích hai điểm hẹn khác nhau |
| Coordinated mixing / randomization | Pha trộn (ngẫu nhiên hoá) có phối hợp |
| Price discount coupons | Phiếu giảm giá |
| Expected punishment | Hình phạt kỳ vọng: hình phạt nhân với xác suất bị bắt |
| Decoy | Mồi nhử |
| Dud shells | Đạn lép |
| Janken | Oẳn tù tì (tên tiếng Nhật) |

## Câu nói đáng nhớ

> "Nếu bạn làm theo bất kỳ hệ thống hay khuôn mẫu nào trong lựa chọn của mình, người chơi kia sẽ khai thác nó để có lợi cho họ và bất lợi cho bạn."
*"If you follow any system or pattern in your choices, it will be exploited by the other player to his advantage and to your disadvantage."*

> "Muốn làm kẻ địch bất ngờ, cách chắc chắn nhất là làm chính mình bất ngờ."
*"You want to surprise the enemy; the surest way to do so is to surprise yourself."*

> "Lý do bạn nên dùng tỷ lệ pha trộn tốt nhất của mình là để giữ người chơi kia tiếp tục dùng tỷ lệ của họ."
*"The reason why you should use your best mix is to keep the other player using his."*

> "Mục đích của việc cải thiện điểm yếu là để bạn không phải dùng nó thường xuyên."
*"The point of improving your weakness is that you don't have to use it so often."*

> "Hình phạt kỳ vọng mới phải tương xứng với tội."
*"The expected punishment should fit the crime."*

## Đánh giá và phát hiện đáng chú ý

### Chương này mạnh vì đặt lý thuyết cạnh dữ liệu thật và để dữ liệu thắng

Phần lớn sách phổ thông về lý thuyết trò chơi minh hoạ chiến lược hỗn hợp bằng ví dụ bịa. Dixit và Nalebuff dùng số liệu phạt đền thật của Palacios-Huerta, tính ra tỷ lệ tối ưu 38,3% và 41,7%, rồi cho thấy cầu thủ thật chọn 40,0% và 42,3%. Hiếm có chỗ nào trong kinh tế học mà một dự báo lý thuyết khớp với hành vi thực tế đến thế. Hai tác giả cũng trung thực ở chiều ngược lại: phòng thí nghiệm không ủng hộ lý thuyết, người chơi oẳn tù tì cố ý đi chệch khỏi nó, và cân bằng hỗn hợp trong trò chơi đi săn vừa tệ vừa mong manh. Người đọc ra khỏi chương biết cả lúc nào công cụ này dùng được lẫn lúc nào không.

### Phép thử "để đối thủ biết trước có hại không" là công cụ thực dụng nhất của chương

Trước khi tính bất kỳ con số nào, chỉ cần hỏi: nếu đối thủ biết trước mình sẽ làm gì, mình có thiệt không? Câu hỏi này phân biệt rõ tình huống cần ngẫu nhiên (phạt đền, kiểm tra, khuyến mãi cạnh tranh) với tình huống mà sự dễ đoán lại có lợi (phối hợp, xây dựng uy tín, cam kết ở các Chương 6 và 7). Theo người tổng hợp, đây là cầu nối khéo léo sang Chương 6 và 7: có lúc phải giấu nước đi, có lúc phải công khai và ràng buộc nó.

### Ví dụ Coke và Pepsi có lỗi tính toán, dù kết luận vẫn đứng vững

Sách nói nếu mỗi hãng khuyến mãi mỗi tuần với xác suất 50%, độc lập nhau, thì xác suất không trùng tuần nào là 1/495.918.532.948.104. Con số này là số cách chọn 26 tuần trong 52 tuần, nên nó là xác suất để hai lịch 26 tuần chọn ngẫu nhiên hoàn toàn bổ sung cho nhau, không phải xác suất theo mô hình "50% mỗi tuần". Theo đúng mô hình sách mô tả, xác suất không có tuần trùng nào là (3/4)^52, khoảng 3 phần 10 triệu, lớn hơn rất nhiều; nếu thêm điều kiện mỗi hãng đúng 26 tuần thì xác suất mới nhỏ cỡ con số trong sách. Ngoài ra 1/495.918.532.948.104 là khoảng 1 phần 500 nghìn tỷ, tức lớn hơn chứ không nhỏ hơn 1 phần triệu tỷ (10^15), và "một tỷ tỷ" là 10^18, không phải một triệu tỷ. Các lỗi này không làm đổi kết luận: một mẫu hình luân phiên hoàn hảo như vậy khó có thể là ngẫu nhiên. Nhưng chúng nhắc người đọc rằng ngay cả nhà lý thuyết trò chơi cũng có thể diễn đạt xác suất cẩu thả.

### Cuộc tranh luận về "thành công" của chiến lược hỗn hợp chưa kết thúc

Kết quả phạt đền của Palacios-Huerta được trích dẫn rộng rãi, nhưng các nghiên cứu khác (ví dụ của Chiappori, Levitt và Groseclose với dữ liệu Pháp và Ý) cũng xác nhận ở mức trung bình mà chỉ ra rằng từng cầu thủ không phải lúc nào cũng ngẫu nhiên hoá hoàn hảo. Một số nghiên cứu khác về phạt đền cho rằng thủ môn bay sang hai bên nhiều hơn mức tối ưu và đứng giữa quá ít, vì bị thủng lưới khi đứng yên trông tệ hơn bị thủng lưới khi đã bay người (thường gọi là thiên lệch hành động). Chương 5 đơn giản hoá phạt đền thành hai lựa chọn, bỏ qua phương án sút vào giữa và đứng giữa, mà chính hai tác giả thừa nhận cũng "giải thích được bằng lý thuyết". Ở mức trung bình, lý thuyết đứng vững; ở mức từng cá nhân, bức tranh lẫn lộn hơn chương trình bày.

### Từ 2008, dữ liệu chi tiết giúp phát hiện khuôn mẫu nhanh hơn, nên Quy tắc 5 càng quan trọng

Nói định tính: các đội bóng ngày nay có dữ liệu chi tiết về từng cầu thủ sút phạt đền, và thủ môn thường mang theo "phao" ghi thói quen của đối thủ. Điều đó làm tăng giá trị của Quy tắc 5: càng nhiều dữ liệu thì mọi khuôn mẫu càng nhanh bị khai thác. Cũng vậy trong kinh doanh: thuật toán định giá động của hãng hàng không và thương mại điện tử biến việc "không để khách đoán được giá giờ chót" thành một hệ thống tự động. Ở chiều ngược lại, ví dụ Coke và Pepsi cũng đặt ra câu hỏi pháp lý mà chương không bàn: sự phối hợp lịch khuyến mãi có thể bị cơ quan cạnh tranh xem là thông đồng ngầm.

### Quan điểm trái chiều: trong đời thực, đối thủ thường không tối ưu, nên khai thác có thể tốt hơn pha trộn

Chiến lược hỗn hợp cân bằng bảo đảm bạn không bị khai thác, nhưng nó cũng không khai thác được ai. Khi đối thủ có khuôn mẫu rõ (như người tham gia thí nghiệm đổi chiều quá nhiều), chiến lược tốt nhất là đáp trả khuôn mẫu đó, đúng như các tay chơi oẳn tù tì vô địch đang làm. Hai tác giả chỉ ra các chiến lược cầu kỳ đó không cho lợi thế bền vững trong giải đấu, nhưng điều này đúng vì đối thủ ở đó cũng tinh. Bài học đầy đủ hơn là: pha trộn cân bằng là chiến lược phòng thủ an toàn; chỉ nên rời nó khi chắc chắn đọc được đối thủ, và phải chấp nhận rằng việc rời đi cũng làm lộ khuôn mẫu của mình.

### Vận dụng: khi đối thủ có lợi từ việc đoán được bạn, hãy để một cơ chế khách quan quyết định thay cho thói quen

- **Trong doanh nghiệp.** Lịch khuyến mãi, ra mắt sản phẩm hay điều chỉnh giá theo chu kỳ cố định giúp đối thủ chặn trước. Nếu thị trường là xung đột thuần tuý giành thị phần, hãy đưa yếu tố ngẫu nhiên vào thời điểm và mức độ; nếu có lợi ích chung (tránh cùng khuyến mãi triệt tiêu nhau), cân nhắc các cách phối hợp hợp pháp như luân phiên theo mùa vụ tự nhiên, và lưu ý giới hạn của luật cạnh tranh. Trong kiểm soát nội bộ (kiểm kê, kiểm toán, kiểm tra chất lượng), kiểm tra ngẫu nhiên với chế tài đủ nặng rẻ hơn kiểm tra toàn diện, miễn là lịch kiểm tra thật sự không đoán được.
- **Trong đầu tư.** Lệnh mua bán lớn theo lịch cố định (cùng giờ, cùng khối lượng) dễ bị người khác phát hiện và chạy trước; tổ chức lớn thường chia nhỏ và ngẫu nhiên hoá thời điểm đặt lệnh vì lý do này. Ở chiều ngược lại, khi đánh giá một chiến lược có yếu tố mạo hiểm, hãy xét chất lượng quyết định qua nhiều lần, đừng xét theo một kết quả, như bài học về huấn luyện viên tung đường chuyền dài.
- **Trong nghề nghiệp.** Trong đàm phán lặp lại với cùng đối tác, một khuôn mẫu cố định (luôn nhượng bộ ở vòng cuối, luôn ra giá mở đầu cao gấp rưỡi) sẽ bị học thuộc. Người quản lý cũng nên nhớ bài học "cải thiện điểm yếu": khi đối thủ hay cấp trên biết bạn đã mạnh lên ở một mặt, họ sẽ ít tấn công vào mặt đó, nên hiệu quả của việc tập luyện thể hiện ở kết quả tổng thể chứ không ở số lần bạn dùng kỹ năng mới.
- **Khi đọc tin chính sách.** Ở Việt Nam, khi đọc về các đợt thanh tra, kiểm tra thuế, kiểm tra nồng độ cồn hay xử phạt vi phạm giao thông, có thể dùng khung của chương để đặt câu hỏi: xác suất bị kiểm tra là bao nhiêu, mức phạt là bao nhiêu, và hình phạt kỳ vọng có đủ lớn so với lợi ích của vi phạm không? Một chính sách kiểm tra theo lịch thông báo trước hay theo đợt cao điểm dễ đoán sẽ kém hiệu quả hơn kiểm tra ngẫu nhiên thường xuyên, và nâng mức phạt chỉ có tác dụng nếu xác suất bị phát hiện không quá thấp.

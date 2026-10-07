# Chương 2 — Những trò chơi giải được bằng suy luận ngược (Games Solvable by Backward Reasoning)

**Nguồn:** Avinash K. Dixit và Barry J. Nalebuff, *The Art of Strategy: A Game Theorist's Guide to Success in Business and Life*, ấn bản đầu (W. W. Norton, 2008), Chương 2.
**Tác giả:** Avinash K. Dixit (sinh 1944), nhà kinh tế Mỹ gốc Ấn, giáo sư danh dự Đại học Princeton; Barry J. Nalebuff (sinh 1958), giáo sư Trường Quản trị Yale. Cuốn sách kế thừa *Thinking Strategically* (1991) của cùng hai tác giả.
**Vị trí trong lập luận của cả cuốn sách:** Chương 1 kể mười câu chuyện chiến lược để người đọc làm quen với các ý tưởng, chưa đưa ra công cụ nào. Chương 2 là chương "công cụ" đầu tiên của Phần I: nó chia các tương tác chiến lược thành hai loại, tuần tự (người chơi đi lần lượt) và đồng thời (người chơi đi cùng lúc), rồi trao công cụ cho loại thứ nhất: cây trò chơi và suy luận ngược. Chương 3 (thế lưỡng nan của người tù) và Chương 4 (cân bằng Nash) sẽ xử lý loại thứ hai. Những ý chương này mới nêu sơ bộ, như việc tự trói tay mình có thể có lợi và vấn đề làm cho lời hứa đáng tin, sẽ được phát triển đầy đủ ở Chương 6 (nước đi chiến lược) và Chương 7 (làm cho chiến lược đáng tin); trò chơi tối hậu thư sẽ quay lại ở Chương 11 về mặc cả.
**Ý chính:** Hai tác giả muốn người đọc nắm **Quy tắc 1 của chiến lược: nhìn về phía trước và suy luận ngược lại** (look forward and reason backward). Trong một trò chơi mà người chơi đi lần lượt, người đi trước phải dự đoán người đi sau sẽ phản ứng thế nào ở mọi tình huống có thể xảy ra, rồi dùng dự đoán đó để chọn nước đi hiện tại. Ví dụ trung tâm là trò chơi 21 lá cờ trong chương trình truyền hình *Survivor: Thailand*: hai đội lần lượt nhổ 1, 2 hoặc 3 lá cờ, đội nhổ lá cuối cùng thắng; đội nào luôn để lại cho đối thủ một số cờ chia hết cho 4 (20, 16, 12, 8, 4) thì chắc thắng, nhưng cả hai đội đều chơi sai gần hết các nước. Từ đó chương đi tiếp ba hướng: thí nghiệm trò chơi tối hậu thư cho thấy con người không chỉ quan tâm tới tiền của mình; cờ vua cho thấy với cây quá phức tạp, cần kết hợp suy luận ngược với kinh nghiệm đánh giá thế cờ; và trận Orange Bowl 1984 cho thấy suy luận ngược giúp sắp xếp đúng thứ tự các nước đi mạo hiểm.

> **Lưu ý:** Sách viết khoảng 2007–2008, nên các mốc về cờ vua máy tính dừng ở trận Kasparov gặp X3D Fritz (2003) và Hydra thắng Michael Adams (2005). Từ đó máy tính đã vượt hẳn các kỳ thủ hàng đầu, đúng như hai tác giả dự đoán; còn việc giải trọn vẹn cờ vua bằng cây trò chơi vẫn chưa ai làm được. Về quyền phủ quyết từng khoản (line-item veto) mà Reagan đòi năm 1987: Quốc hội Mỹ đã trao quyền này cho tổng thống năm 1996, nhưng Toà án Tối cao tuyên bố luật đó vi hiến năm 1998; sách không nhắc diễn biến này vì ví dụ chỉ dùng tình huống năm 1987. Chương có 5 chú thích chân trang của tác giả (dấu `*`), đã đưa vào Nội dung chi tiết ở mục 6 (hai chú thích, về trò 21 lá cờ), mục 8 (trò chơi tối hậu thư), mục 11 (cờ vua) và mục 13 (trận Orange Bowl), có ghi "Chú thích của tác giả". Chương có 9 hình và bảng (một trang truyện tranh *Peanuts*, sáu cây quyết định và cây trò chơi, bảng xếp hạng ngân sách, bảng các nước đi trong trò chơi 21 lá cờ), tất cả đã được dựng lại. Một chỗ không khớp trong sách: phần lời nói rằng trong trò chơi 21 lá cờ "gần như mọi lựa chọn đều sai, trừ nước của Chuay Gahn khi còn 13 lá", nhưng chính bảng của sách cho thấy Chuay Gahn cũng đi đúng khi còn 6 lá (nhổ 2) và khi còn 1 lá (nhổ 1); phần lời ở đoạn trước cũng khen nước đi khi còn 6 lá là đúng. Các câu trích là bản dịch của người tổng hợp.

## Sơ đồ

### Mở đầu "It's Your Move, Charlie Brown" — đến lượt anh, Charlie Brown

```text
       Truyện tranh Peanuts: năm nào Lucy cũng giữ quả bóng bầu dục trên
       mặt đất, mời Charlie Brown chạy tới đá; phút cuối Lucy giật bóng
       đi, Charlie đá vào không khí và ngã ngửa, Lucy thích thú
                                │
                                ▼
       HÌNH DỰNG LẠI TỪ SÁCH (trang truyện Peanuts in đầu chương):
       · Lucy: "Tôi giữ bóng, anh chạy tới đá nhé"
       · Charlie từ chối: "Cô sẽ giật bóng, tôi sẽ ngã và chết mất"
       · Lucy: "Anh không rút lui được, chương trình đã in rồi"; tờ chương
         trình ghi: một giờ chiều, Lucille Van Pelt giữ bóng và Charles
         Brown chạy tới đá
       · Charlie: "Cô ấy nói đúng, chương trình in rồi thì không lùi được"
       · Charlie hăm hở: "Năm nay tôi sẽ đá quả bóng bay khỏi vũ trụ!"
       · Lucy giật bóng, Charlie ngã ngửa xuống đất
       · Lucy: "Chương trình nào cũng có vài thay đổi phút chót, Charlie ạ"
                                │
                                ▼
       Bài học của hai tác giả: hành động của Lucy nằm ở tương lai, nhưng
       không vì thế mà Charlie được coi nó là bất định
       · Charlie biết tính Lucy: giữa "để Charlie đá" và "thấy Charlie
         ngã", Lucy thích cái sau
       · vậy Charlie phải dự đoán Lucy sẽ giật bóng
       · khả năng Lucy để Charlie đá chỉ có trên lý thuyết; tin vào nó là
         "chiến thắng của hy vọng trước kinh nghiệm" (câu của Samuel
         Johnson nói về chuyện tái hôn)
       → Charlie nên từ chối lời mời
```

### Tiểu mục "Two Kinds of Strategic Interactions" — hai loại tương tác chiến lược, và "The First Rule of Strategy" — quy tắc thứ nhất của chiến lược

```text
       Bản chất của trò chơi chiến lược: quyết định của người chơi phụ
       thuộc lẫn nhau. Sự phụ thuộc này có hai dạng:
       ┌─────────────────────────────────┬─────────────────────────────────┐
       │ TRÒ CHƠI TUẦN TỰ                │ TRÒ CHƠI ĐỒNG THỜI              │
       │ (sequential game)               │ (simultaneous game)             │
       ├─────────────────────────────────┼─────────────────────────────────┤
       │ người chơi đi lần lượt, như     │ người chơi hành động cùng lúc,  │
       │ Charlie và Lucy                 │ không biết người kia vừa làm gì │
       │ mỗi người nhìn trước xem nước   │ như thế lưỡng nan của người tù  │
       │ đi hôm nay ảnh hưởng thế nào    │ ở Chương 1; mỗi người phải đặt  │
       │ tới nước đi sau này của đối thủ │ mình vào vị trí của mọi người   │
       │ và của chính mình               │ khác để tính kết cục chung      │
       │ → học ở Chương 2                │ → học ở Chương 3                │
       └─────────────────────────────────┴─────────────────────────────────┘
       Có trò chơi mang cả hai yếu tố (như bóng bầu dục); khi đó chiến
       lược phải khớp với từng bối cảnh
                                │
                                ▼
       Hai tác giả chủ ý bắt đầu bằng ví dụ rất đơn giản, đôi khi giả tạo,
       để ý tưởng nền tảng hiện rõ; ví dụ thực tế hơn đến ở các chương sau
                                │
                                ▼
       QUY TẮC 1: NHÌN VỀ PHÍA TRƯỚC VÀ SUY LUẬN NGƯỢC LẠI
       Dự đoán các quyết định ban đầu của mình rốt cuộc sẽ dẫn tới đâu, và
       dùng thông tin đó để tính lựa chọn tốt nhất ngay bây giờ
```

### Tiểu mục "Decision Trees and Game Trees" — cây quyết định và cây trò chơi

```text
       Ngay cả người quyết định một mình cũng gặp chuỗi lựa chọn cần suy
       luận ngược, ví dụ nhân vật trong bài thơ của Robert Frost: "Hai con
       đường rẽ trong rừng, và tôi chọn con đường ít người đi"

       HÌNH DỰNG LẠI TỪ SÁCH: cây quyết định của Robert Frost

                               ┌──── Con đường nhiều người đi
       Rừng cây vàng ──────────┤
                               └──── Con đường ít người đi
                                │
                                ▼
       Mỗi con đường lại có thể rẽ tiếp. Ví dụ từ kinh nghiệm của hai tác
       giả: đi từ Princeton (bang New Jersey) tới New York

       HÌNH DỰNG LẠI TỪ SÁCH: cây quyết định Princeton – New York

                  ┌─ Xe buýt ── tới bến Port Authority (phố 42 và
                  │             Đại lộ 8) ──────────────── các tuyến
                  │                                        nội thành
                  │
                  │           ┌─ đổi sang tàu PATH ở Newark, tới
                  │           │  khu downtown (WTC) ────── các tuyến
       Princeton ─┼─ Tàu hoả ─┤                            nội thành
                  │           └─ tới ga Penn Station (phố 33 Tây
                  │              và Đại lộ 7) ──────────── các tuyến
                  │                                        nội thành
                  │
                  │           ┌─ Cầu Verrazano
                  └─ Ô tô ────┼─ Đường hầm Holland
                              ├─ Đường hầm Lincoln
                              └─ Cầu George Washington

       (ở New York, "các tuyến nội thành" gồm đi bộ, tàu điện ngầm
       thường hoặc tốc hành, xe buýt hoặc taxi)
                                │
                                ▼
       Cách dùng SAI: chọn nhánh đầu tiên trông hấp dẫn nhất (thích lái xe
       hơn đi tàu) rồi "tới cầu Verrazano hãy tính"
       Cách dùng ĐÚNG: dự đoán các quyết định về sau để chọn nước đi đầu
       · ví dụ: muốn tới khu downtown thì tàu PATH hơn lái xe, vì có tuyến
         nối thẳng từ Newark
                                │
                                ▼
       Trong trò chơi có thêm một yếu tố mới: tại các điểm rẽ khác nhau,
       người ra quyết định có thể là những người chơi khác nhau
       · người chọn trước phải dự đoán lựa chọn của người khác, bằng cách
         đặt mình vào vị trí và suy nghĩ như họ
       · CÂY TRÒ CHƠI (game tree): khi có từ hai người chơi trở lên
       · CÂY QUYẾT ĐỊNH (decision tree): khi chỉ có một người
```

### Tiểu mục "Charlie Brown in Football and in Business" — Charlie Brown trong bóng bầu dục và trong kinh doanh

```text
       HÌNH DỰNG LẠI TỪ SÁCH: cây trò chơi Charlie Brown và Lucy
       (══► là nhánh được chọn theo suy luận ngược; ─── là nhánh bị loại)

                         Nhận lời            ╔══► Giật bóng đi
       Charlie ──┬──────────────────── Lucy ═╣
                 │                           ╚─── Để Charlie đá
                 │   Từ chối
                 ╚═══════════════════════════════► (trò chơi kết thúc)

       · Lucy chọn nhánh "giật bóng"; Charlie cắt bỏ nhánh "để Charlie đá"
         khỏi cây trong đầu
       · khi đó "nhận lời" dẫn thẳng tới cú ngã → Charlie chọn "từ chối"
                                │
                                ▼
       Phiên bản kinh doanh: Charlie trưởng thành đi nghỉ ở Freedonia, một
       nước hậu Marx mới cải cách. Doanh nhân địa phương Fredo mời: "Đưa
       tôi 100.000 USD, một năm sau tôi biến nó thành 500.000 USD và chia
       đôi với anh". Hợp đồng ký theo luật Freedonia, nhưng toà án ở đó có
       thể thiên vị người nước mình, chậm chạp, hoặc bị Fredo mua chuộc

       HÌNH DỰNG LẠI TỪ SÁCH: cây trò chơi Charlie và Fredo

                       Đầu tư             ╔══► Ôm tiền bỏ trốn
       Charlie ──┬─────────────── Fredo ══╣    Charlie: −100.000 USD
                 │                        ║    Fredo:    500.000 USD
                 │                        ╚─── Thực hiện hợp đồng
                 │                             Charlie:  150.000 USD
                 │                             Fredo:    250.000 USD
                 │   Không đầu tư
                 ╚════════════════════════════► Charlie: 0
                                                Fredo:   0

       (nếu giữ hợp đồng, Fredo trả Charlie 250.000 USD; trừ 100.000 USD
       vốn bỏ ra, Charlie lãi 150.000 USD)
                                │
                                ▼
       Không có lý do rõ ràng để tin lời hứa → Charlie nên đoán Fredo bỏ
       trốn và không đầu tư; hai cây giống nhau về mọi điểm cốt yếu
       · Fredo đáng tin hơn nếu có nhiều việc làm ăn khác cần vốn từ Mỹ
         hoặc xuất hàng sang Mỹ: Charlie có thể trả đũa bằng cách huỷ
         danh tiếng hoặc tịch thu hàng của Fredo ở Mỹ; khi đó trò chơi
         này nằm trong một trò chơi lớn hơn, kéo dài
                                │
                                ▼
       BA NHẬN XÉT CỦA HAI TÁC GIẢ
       1. Các trò chơi khác nhau có thể có cùng dạng toán học (cùng cây,
          cùng bảng) → đó là giá trị của "lý thuyết": rút ra điểm chung
          của những bối cảnh trông khác nhau; hãy coi lý thuyết trò chơi
          là bạn, không phải ông kẹ
       2. Fredo hiểu rằng Charlie tỉnh táo sẽ không đầu tư, và Fredo mất cơ
          hội kiếm 250.000 USD → Fredo có động cơ mạnh để làm lời hứa của
          mình đáng tin (bàn ở Chương 6 và 7)
       3. Trò chơi không nhất thiết có kẻ thắng người thua (không nhất
          thiết là trò chơi tổng bằng không, zero-sum): "Charlie đầu tư,
          Fredo giữ hợp đồng" tốt cho CẢ HAI hơn "không đầu tư"; phần lớn
          trò chơi trong kinh doanh, chính trị, xã hội vừa có lợi ích
          chung vừa có xung đột
```

### Tiểu mục "More Complex Trees" — những cây phức tạp hơn: quyền phủ quyết từng khoản

```text
       Hình ảnh biếm hoạ về chính trị Mỹ: Quốc hội thích chi tiêu "thùng
       thịt lợn" (pork-barrel) cho địa phương; tổng thống muốn cắt bớt,
       nhưng chỉ cắt những khoản mình không thích → muốn có QUYỀN PHỦ
       QUYẾT TỪNG KHOẢN (line-item veto)
       · Reagan, Thông điệp Liên bang tháng 1/1987: "Hãy cho chúng tôi
         công cụ mà 43 thống đốc bang đang có", để cắt những khoản chi
         lãng phí không thể tự đứng được
                                │
                                ▼
       Thoạt nhìn, thêm quyền chỉ có thể làm tổng thống mạnh hơn. Nhưng
       quyền đó làm Quốc hội đổi cách soạn dự luật
                                │
                                ▼
       Tình huống 1987 giản lược: hai khoản chi, cải tạo đô thị (U, Quốc
       hội thích) và hệ thống tên lửa chống tên lửa đạn đạo (M, tổng thống
       thích); cả hai bên đều thích gói U+M hơn hiện trạng

       BẢNG DỰNG LẠI TỪ SÁCH: điểm xếp hạng (4 tốt nhất, 1 tệ nhất)
       ┌──────────────────────┬─────────────┬─────────────┐
       │ Kết quả              │ Quốc hội    │ Tổng thống  │
       ├──────────────────────┼─────────────┼─────────────┤
       │ Cả U và M            │      3      │      3      │
       │ Chỉ U                │      4      │      1      │
       │ Chỉ M                │      1      │      4      │
       │ Không khoản nào      │      2      │      2      │
       └──────────────────────┴─────────────┴─────────────┘
                                │
                                ▼
       HÌNH DỰNG LẠI TỪ SÁCH: cây trò chơi KHI TỔNG THỐNG KHÔNG CÓ quyền
       phủ quyết từng khoản (điểm ghi theo thứ tự Quốc hội, Tổng thống)

       Quốc hội thông qua    Tổng thống quyết định        Điểm
       ╔══► U+M ──────────── Tổng thống ╔══► Ký            3, 3  ◄ KẾT QUẢ
       ║                                ╚─── Phủ quyết     2, 2
       ╠─── Chỉ U ────────── Tổng thống ╔─── Ký            4, 1
       ║                                ╚══► Phủ quyết     2, 2
       ╠─── Chỉ M ────────── Tổng thống ╔══► Ký            1, 4
       ║                                ╚─── Phủ quyết     2, 2
       ╚─── Không khoản nào ─────────────────────────────  2, 2

       · tổng thống ký gói U+M hoặc chỉ M, phủ quyết chỉ U
       · biết vậy, Quốc hội thông qua gói U+M → mỗi bên được lựa chọn tốt
         thứ hai (điểm 3)
       · phải ghi lựa chọn của tổng thống ở MỌI điểm rẽ, kể cả điểm không
         xảy ra, vì Quốc hội chọn dựa trên việc tổng thống SẼ làm gì nếu
         Quốc hội đã chọn khác
                                │
                                ▼
       HÌNH DỰNG LẠI TỪ SÁCH: cây trò chơi KHI TỔNG THỐNG CÓ quyền phủ
       quyết từng khoản

       Quốc hội thông qua    Tổng thống quyết định        Điểm
       ╔─── U+M ──────────── Tổng thống ╔─── Ký cả hai     3, 3
       ║                                ╠══► Phủ quyết U   1, 4
       ║                                ╠─── Phủ quyết M   4, 1
       ║                                ╚─── Phủ quyết cả  2, 2
       ║                                     hai
       ╠══► Chỉ U ────────── Tổng thống ╔─── Ký            4, 1
       ║                                ╚══► Phủ quyết     2, 2  ◄ KẾT QUẢ
       ╠─── Chỉ M ────────── Tổng thống ╔══► Ký            1, 4
       ║                                ╚─── Phủ quyết     2, 2
       ╚══► Không khoản nào ─────────────────────────────  2, 2  ◄ KẾT QUẢ

       · nếu Quốc hội thông qua gói, tổng thống sẽ phủ quyết riêng U, chỉ
         giữ M (điểm Quốc hội 1)
       · Quốc hội vì thế chỉ thông qua U để bị phủ quyết, hoặc không thông
         qua gì; giả sử điểm chính trị hai bên kiếm được từ màn phủ quyết
         triệt tiêu nhau, Quốc hội bàng quan giữa hai cách
       → kết cục: mỗi bên chỉ được lựa chọn tốt thứ ba (điểm 2); chính
         tổng thống cũng thiệt vì có thêm quyền
                                │
                                ▼
       BÀI HỌC KHÁI NIỆM: với người quyết định một mình, thêm tự do không
       bao giờ có hại; trong trò chơi, thêm tự do CÓ THỂ có hại vì nó thay
       đổi hành động của người khác; ngược lại, tự trói tay mình có thể có
       lợi ("lợi thế của cam kết", Chương 6 và 7)
                                │
                                ▼
       Cây có thể trở nên quá lớn: trong cờ vua, quân trắng có 20 nước đi
       đầu (8 tốt mỗi con tiến 1 hoặc 2 ô, 2 mã mỗi con đi 2 cách); với
       mỗi nước đó quân đen có 20 nước → đã có 400 nhánh sau một lượt mỗi
       bên → không máy tính nào hiện có hoặc sẽ có trong vài thập kỷ tới
       giải trọn được cờ vua bằng cây
                                │
                                ▼
       Với các trò chơi phức tạp vừa phải trong kinh doanh, chính trị, đời
       sống: dùng phần mềm dựng cây và tính lời giải, HOẶC suy luận theo
       logic của cây mà không cần vẽ cây
```

### Tiểu mục "Strategies for 'Survivors'" — chiến lược cho những "người sống sót"

```text
       Tập 6 của Survivor: Thailand (đài CBS): hai đội Sook Jai và Chuay
       Gahn chơi trò 21 LÁ CỜ
       · 21 lá cờ cắm giữa sân; hai đội lần lượt nhổ cờ
       · mỗi lượt phải nhổ 1, 2 hoặc 3 lá (không được bỏ lượt, không được
         nhổ từ 4 lá trở lên)
       · đội nhổ lá cuối cùng (một mình hay cùng 2–3 lá khác) thắng
       · đội thua phải loại một thành viên; trận thua này hoá ra quyết định,
         và một người của đội kia về sau thắng giải 1 triệu USD
                                │
                                ▼
       Sook Jai đi trước, nhổ 2 lá, để lại 19
                                │
                                ▼
       SỰ CỐ 1: trong buổi bàn bạc trước trận của Chuay Gahn, Ted Rogers
       (kỹ sư phần mềm người Mỹ gốc Phi) nói: "Đến cuối, ta phải để lại
       cho họ 4 lá"
       · đúng: đội nào gặp 4 lá phải nhổ 1, 2 hoặc 3; đội kia nhổ nốt 3, 2
         hoặc 1 và thắng
       · Chuay Gahn thực sự gặp 6 lá và nhổ 2, để lại 4 → thắng
                                │
                                ▼
       SỰ CỐ 2: lượt trước đó, Sook Jai gặp 9 lá và nhổ 3; vừa quay về,
       Shii Ann (người tự hào về khả năng phân tích) nhận ra: "Nếu Chuay
       Gahn nhổ 2 bây giờ thì ta chết"
       · lẽ ra Sook Jai phải đẩy lập luận của Ted thêm một bước: muốn đối
         thủ gặp 4 lá ở lượt sau thì phải để họ gặp 8 lá ở lượt này
       · gặp 9 lá → nhổ 1, để lại 8
       · Shii Ann phân tích đúng nhưng chậm mất một nước
                                │
                                ▼
       Ted cũng chưa đẩy lập luận đủ xa: Sook Jai gặp 9 lá vì trước đó
       Chuay Gahn gặp 11 lá và nhổ 2; lẽ ra Chuay Gahn phải nhổ 3, để lại 8
                                │
                                ▼
       ĐẨY LẬP LUẬN VỀ TẬN ĐẦU TRÒ CHƠI
       để đối thủ gặp 4  ◄─ để họ gặp 8  ◄─ để họ gặp 12  ◄─ gặp 16  ◄─
       gặp 20
       · Sook Jai đi đầu với 21 lá lẽ ra phải nhổ 1 (không phải 2), rồi
         luôn để Chuay Gahn gặp 20, 16, 12, 8, 4 → chắc thắng
       · Chuay Gahn gặp 19 lá ở lượt đầu lẽ ra phải nhổ 3, để Sook Jai gặp
         16 và chắc thua
       · từ bất kỳ điểm nào giữa trận mà đối thủ đã đi sai, đội đến lượt
         có thể giành thế chủ động và thắng
                                │
                                ▼
       BẢNG DỰNG LẠI TỪ SÁCH: nước đi thực tế và nước đi đúng
       ("Không có nước thắng": nước nào cũng thua nếu đối thủ chơi đúng)
       ┌────────────┬───────────┬──────────┬──────────────────────────┐
       │ Đội        │ Số cờ còn │ Số cờ đã │ Nước đi đưa đội vào con  │
       │            │ trước lượt│ nhổ      │ đường chắc thắng         │
       ├────────────┼───────────┼──────────┼──────────────────────────┤
       │ Sook Jai   │    21     │    2     │ 1                        │
       │ Chuay Gahn │    19     │    2     │ 3                        │
       │ Sook Jai   │    17     │    2     │ 1                        │
       │ Chuay Gahn │    15     │    1     │ 3                        │
       │ Sook Jai   │    14     │    1     │ 2                        │
       │ Chuay Gahn │    13     │    1     │ 1                        │
       │ Sook Jai   │    12     │    1     │ Không có nước thắng      │
       │ Chuay Gahn │    11     │    2     │ 3                        │
       │ Sook Jai   │     9     │    3     │ 1                        │
       │ Chuay Gahn │     6     │    2     │ 2                        │
       │ Sook Jai   │     4     │    3     │ Không có nước thắng      │
       │ Chuay Gahn │     1     │    1     │ 1                        │
       └────────────┴───────────┴──────────┴──────────────────────────┘
       · hai tác giả cho rằng nước đúng khi còn 13 lá là ngẫu nhiên, vì
         lượt sau gặp 11 lá Chuay Gahn lại nhổ 2 thay vì 3
                                │
                                ▼
       Đừng vội chê hai đội: học chơi cả trò đơn giản cũng cần thời gian
       · sinh viên năm nhất các trường Ivy League cần 3–4 ván mới chơi đúng
         trọn vẹn từ nước đầu tiên
       · người xem chơi học nhanh hơn người trực tiếp chơi, có lẽ vì người
         quan sát dễ nhìn toàn cục và suy nghĩ bình tĩnh hơn
                                │
                                ▼
       BÀI TẬP SỐ 1 (Trip to the Gym No. 1): đổi luật thành "củ khoai
       nóng": đội phải nhổ lá cuối cùng là đội THUA; còn 21 lá, đến lượt
       bạn, nên nhổ mấy lá?
       · đáp án của sách: muốn thắng phải để đối thủ gặp 1 lá; vậy gặp 2,
         3, 4 là thế thắng, gặp 5 là thế thua, kéo tiếp: gặp 9, 13, 17, 21
         đều là thế thua
       · người đi đầu với 21 lá KHÔNG có cách chắc thắng nếu đối thủ chơi
         đúng (đối thủ luôn đưa tổng số giảm theo từng nhóm 4 lá)
```

### Tiểu mục "What Makes a Game Fully Solvable by Backward Reasoning?" — điều gì làm một trò chơi giải trọn được bằng suy luận ngược?

```text
       Trò 21 lá cờ giải trọn được vì KHÔNG có bất định nào. Ba loại bất
       định thường gặp trong các trò chơi khác:
                                │
                                ▼
       1. BẤT ĐỊNH TỰ NHIÊN (yếu tố may rủi)
       · trong trò 21 lá cờ, đội đến lượt biết chính xác còn bao nhiêu cờ
       · trong nhiều trò chơi bài, người chơi không biết chắc bài của người
         khác, dù có thể suy ra phần nào từ các nước đi trước
                                │
                                ▼
       2. BẤT ĐỊNH VỀ MỤC TIÊU CỦA NGƯỜI KHÁC
       · trong trò 21 lá cờ, mỗi đội biết đội kia muốn thắng; Charlie biết
         Lucy thích thấy mình ngã
       · trong kinh doanh, chính trị, xã hội, động cơ là hỗn hợp: ích kỷ và
         vị tha, công bằng, ngắn hạn và dài hạn
       · phải đoán có căn cứ; KHÔNG được giả định người khác có sở thích
         giống mình hoặc giống một "người duy lý" giả định
       · đặt mình vào vị trí người khác rất khó, nhất là khi mình đang
         dính líu cảm xúc → nên hỏi một bên thứ ba khách quan (nhà tư vấn
         chiến lược)
                                │
                                ▼
       3. BẤT ĐỊNH CHIẾN LƯỢC (strategic uncertainty): không biết người
          khác đã chọn gì
       · trong trò 21 lá cờ, mỗi đội thấy rõ đội kia vừa làm gì
       · thủ môn đối mặt quả phạt đền phải chọn đổ sang phải hay trái khi
         chưa biết cầu thủ sút hướng nào; giao bóng, đánh bóng qua người
         trong quần vợt; đấu giá kín
       · đó là trò chơi đồng thời; cách suy nghĩ khác và có mặt khó hơn
         suy luận ngược thuần tuý → học ở các chương sau
```

### Tiểu mục "Do People Actually Solve Games by Backward Reasoning?" — con người có thật sự giải trò chơi bằng suy luận ngược không?

```text
       Suy luận ngược là cách ĐÚNG để giải trò chơi tuần tự (dùng lý thuyết
       để khuyên, normative). Câu hỏi khác: lý thuyết có GIẢI THÍCH được
       hành vi thật không (positive)? Kinh tế học hành vi và lý thuyết trò
       chơi hành vi cho bằng chứng lẫn lộn
                                │
                                ▼
       TRÒ CHƠI TỐI HẬU THƯ (ultimatum game): trò mặc cả đơn giản nhất,
       chỉ có một lời đề nghị "chịu thì lấy, không thì thôi"
       · người đề nghị A chia 100 USD giữa A và người đáp B
       · B đồng ý → chia theo đề nghị; B từ chối → cả hai không được gì
                                │
                                ▼
       BÀI TẬP NHANH: trò chơi tối hậu thư đảo ngược
       · nếu B từ chối, A có thể đưa đề nghị mới nhưng phải hào phóng hơn
         cho B; trò chơi dừng khi B đồng ý hoặc A ngừng đề nghị
       · theo logic của cây, A sẽ đề nghị tiếp cho tới khi chia 99 cho B,
         1 cho A → B được gần hết
       · nhưng hai tác giả khuyên: nếu là B, đừng cố giữ đòi bằng được 99:1
                                │
                                ▼
       Dự đoán của lý thuyết khi cả hai chỉ quan tâm tới tiền của mình và
       tính toán hoàn hảo:
       · A nghĩ: chia thế nào thì B cũng chỉ chọn giữa phần đó và số 0;
         trò chơi chỉ chơi một lần nên B không cần tạo tiếng cứng rắn
       · vậy B nhận bất kỳ số dương nào → A đề nghị mức nhỏ nhất (1 xu)
                                │
                                ▼
       THÍ NGHIỆM THỰC TẾ
       · vài chục người được ghép cặp ngẫu nhiên, chơi một lần với mỗi cặp,
         không biết mình gặp ai → không thể xây quan hệ lâu dài
       · đề nghị dưới 10% tổng số tiền rất hiếm
       · đề nghị trung vị: 40–50%; chia đôi 50:50 thường là đề nghị phổ
         biến nhất
       · đề nghị cho B dưới 20% bị từ chối khoảng một nửa số lần
```

### Tiểu mục "Irrationality versus Other-Regarding Rationality" — phi lý trí hay lý trí có quan tâm tới người khác

```text
       Vì sao người đề nghị chia phần đáng kể? Ba giả thuyết:
       (1) không suy luận ngược được; (2) có động cơ khác ngoài tiền (vị
       tha, công bằng); (3) sợ bị từ chối
                                │
                                ▼
       (1) khó xảy ra: logic quá đơn giản, kể cả với người mới
                                │
                                ▼
       Kết quả ban đầu ủng hộ (3): Al Roth (Harvard) và cộng sự thấy người
       đề nghị chọn mức chia cân bằng tối ưu giữa phần lớn hơn cho mình và
       rủi ro bị từ chối, căn cứ vào ngưỡng từ chối của nhóm người tham gia
                                │
                                ▼
       TRÒ CHƠI ĐỘC TÀI (dictator game): người chia quyết định, người kia
       không có quyền từ chối
       · người chia cho đi ít hơn đáng kể so với trò tối hậu thư, nhưng vẫn
         nhiều hơn 0 rõ rệt
       → hành vi trong trò tối hậu thư vừa có phần hào phóng (2) vừa có
         phần tính toán chiến lược (3)
                                │
                                ▼
       Vị tha hay công bằng? Nếu vai người đề nghị được trao cho người
       thắng một cuộc thi kiến thức (thay vì tung đồng xu), người đó thấy
       mình "xứng đáng" và đề nghị thấp hơn khoảng 10%, nhưng vẫn xa trên
       0 → có lòng vị tha chung chung (họ không biết người nhận là ai)
                                │
                                ▼
       Động cơ thứ ba: XẤU HỔ. Thí nghiệm của Jason Dana (Đại học
       Illinois), Daylian Cain (Yale) và Robyn Dawes (Carnegie-Mellon):
       · người chia được giao 10 USD; chia xong nhưng trước khi giao, được
         đề nghị: lấy 9 USD, người kia không được gì và sẽ không bao giờ
         biết mình tham gia thí nghiệm
       · phần lớn nhận đề nghị: chịu mất 1 USD để người kia không biết mình
         tham lam (người vị tha thật sẽ thích giữ 9, cho 1 hơn)
       · cả người đã định cho 3 USD cũng rút lại để giữ kín
       · giống như tốn công băng qua đường để khỏi phải cho người ăn xin
         một khoản nhỏ
                                │
                                ▼
       Hai nhận xét về phương pháp: các thí nghiệm kiểm định giả thuyết
       bằng biến thể có kiểm soát; trong khoa học xã hội nhiều nguyên nhân
       cùng tồn tại, chấp nhận giả thuyết này không có nghĩa bác bỏ mọi
       giả thuyết khác
                                │
                                ▼
       Vì sao người đáp từ chối dù biết sẽ được ít hơn?
       · không phải để tạo tiếng cứng rắn (không chơi lại cùng người, không
         ai xem lịch sử của họ) → phải là phản ứng bản năng, cảm xúc
       · KINH TẾ HỌC THẦN KINH (neuroeconomics), chụp não bằng fMRI hoặc
         PET khi chơi:
         – thuỳ đảo trước (anterior insula), vùng gắn với giận dữ và ghê
           tởm, hoạt động mạnh hơn khi đề nghị càng bất bình đẳng
         – vỏ não trước trán bên trái hoạt động mạnh hơn khi người đáp vẫn
           nhận đề nghị bất bình đẳng: kiểm soát có ý thức để cân giữa cảm
           giác ghê tởm và tiền
                                │
                                ▼
       Phản biện "tiền thật lớn thì không ai từ chối": thí nghiệm ở nước
       nghèo với số tiền bằng vài tháng thu nhập
       · từ chối giảm đôi chút, nhưng đề nghị không bớt hào phóng đáng kể
         (người đề nghị cũng thận trọng hơn vì bị từ chối thì mất nhiều)
                                │
                                ▼
       KHÁC BIỆT VĂN HOÁ
       · mức đề nghị được coi là hợp lý chênh tới 10% giữa các nền văn hoá;
         độ cứng rắn chênh ít hơn
       · người Machiguenga (vùng Amazon thuộc Peru): đề nghị trung bình
         26%, chỉ một đề nghị bị từ chối; họ sống thành đơn vị gia đình
         nhỏ, ít gắn kết xã hội, không có chuẩn mực chia sẻ
       · hai nền văn hoá có đề nghị trên 50%: có tục cho hào phóng khi gặp
         may, buộc người nhận phải đáp lại hào phóng hơn về sau
```

### Tiểu mục "Evolution of Altruism and Fairness" — sự tiến hoá của lòng vị tha và tính công bằng

```text
       Kết quả thí nghiệm khác dự đoán. Giả định nào sai: người chơi suy
       luận ngược đúng, hay người chơi ích kỷ thuần tuý?
                                │
                                ▼
       VỀ SUY LUẬN NGƯỢC: vẫn là điểm xuất phát
       · người chơi Survivor chơi lần đầu, vẫn le lói lập luận đúng; sinh
         viên học được sau 3–4 ván
       · thí nghiệm thường dùng người mới; ngoài đời, người làm kinh doanh,
         chính trị, thể thao chuyên nghiệp có kinh nghiệm, tính toán hoặc
         có bản năng đã rèn luyện; trò khó hơn thì dùng máy tính, tư vấn
       → bắt đầu bằng suy luận ngược, rồi điều chỉnh cho người mới mắc
         lỗi và trò chơi quá phức tạp
                                │
                                ▼
       VỀ SỞ THÍCH: bài học quan trọng hơn
       · con người đưa vào lựa chọn nhiều cân nhắc ngoài phần thưởng của
         chính mình → lý thuyết trò chơi phải đưa công bằng, vị tha vào
         mục tiêu của người chơi (và cả mong muốn thưởng, phạt người tôn
         trọng hoặc vi phạm các chuẩn mực đó)
       · Colin Camerer: lý thuyết trò chơi hành vi MỞ RỘNG tính duy lý chứ
         không từ bỏ nó
                                │
                                ▼
       VÌ SAO công bằng và vị tha bám rễ sâu? Một giả thuyết của tâm lý
       học tiến hoá:
       · nhóm có chuẩn mực công bằng, vị tha ít xung đột nội bộ, giỏi hành
         động tập thể hơn (cung cấp hàng hoá chung, giữ gìn tài nguyên
         chung) → làm ăn tốt hơn và thắng các nhóm khác
       · thí nghiệm của Terry Burnham: 40 USD, sinh viên cao học nam
         Harvard; người chia chỉ có hai lựa chọn: cho 25 giữ 15, hoặc cho
         5 giữ 35
         – trong những người được đề nghị 5 USD: 20 người nhận, 6 người
           từ chối (cả hai bên được 0)
         – 6 người từ chối có nồng độ testosterone cao hơn 50% so với
           những người nhận
         – nếu testosterone gắn với địa vị và tính hung hăng, đây có thể
           là mối liên hệ di truyền giải thích lợi thế tiến hoá của cái mà
           nhà sinh học Robert Trivers gọi là "hung hăng vì đạo đức"
       · ngoài di truyền, xã hội truyền chuẩn mực qua giáo dục gia đình và
         nhà trường
                                │
                                ▼
       Giới hạn: tiến bộ dài hạn cần đổi mới, cần chủ nghĩa cá nhân và dám
       thách thức chuẩn mực, thường đi kèm ích kỷ → cần cân bằng giữa hành
       vi vì mình và vì người
```

### Tiểu mục "Very Complex Trees" — những cây rất phức tạp: cờ vua

```text
       Về nguyên tắc, cờ vua là trò chơi tuần tự lý tưởng cho suy luận
       ngược: đi lần lượt, mọi nước trước đều thấy được và không rút lại
       được, không bất định về thế cờ hay động cơ; luật hoà khi lặp thế cờ
       bảo đảm ván cờ kết thúc sau hữu hạn nước
                                │
                                ▼
       Thực tế: cây cờ vua có khoảng 10^120 nút (số 1 với 120 số 0); một
       siêu máy tính nhanh gấp 1.000 lần máy tính cá nhân thông thường cần
       10^103 năm để xét hết
                                │
                                ▼
       Người chơi và lập trình viên đã làm gì?
       · TÀN CUỘC: khi còn ít quân, chuyên gia nhìn tới cuối ván và suy
         luận ngược xem bên nào chắc thắng hoặc giữ được hoà
       · TRUNG CUỘC: khó nhất; nhìn trước 5 cặp nước (giới hạn thực tế của
         chuyên gia) chưa đủ để tới thế tàn cuộc giải được
       · KHAI CUỘC: tri thức đúc kết từ rất nhiều ván, ghi thành quy tắc
         cho 10–15 nước đầu, trong hàng trăm cuốn sách
                                │
                                ▼
       LỜI GIẢI THỰC DỤNG kết hợp hai phần: phân tích nhìn trước (khoa
       học: lý thuyết trò chơi) và đánh giá giá trị thế cờ dựa trên số quân
       và cách chúng phối hợp (nghệ thuật: kỳ thủ gọi là "tri thức", cũng
       có thể gọi là kinh nghiệm, bản năng)
                                │
                                ▼
       MÁY TÍNH
       · ban đầu: cố bắt máy suy nghĩ như người (trí tuệ nhân tạo), nhiều
         năm không thành
       · sau đó: để máy làm việc nó giỏi, tính toán nhiều nước nhanh hơn
       · cuối thập niên 1990: Fritz, Deep Blue ngang các kỳ thủ hàng đầu;
         sau đó được nạp thêm tri thức trung cuộc từ kỳ thủ giỏi
       · 11/2003: Garry Kasparov (hệ số khoảng 2800, kỳ thủ mạnh nhất thế
         giới) đấu 4 ván với X3D Fritz: mỗi bên thắng 1, hoà 2
       · 7/2005: máy Hydra đè bẹp Michael Adams (hạng 13 thế giới) trong 6
         ván: thắng 5, hoà 1
                                │
                                ▼
       BÀI HỌC: với trò chơi phức tạp, kết hợp quy tắc "nhìn trước, suy
       luận ngược" với kinh nghiệm để đánh giá các thế trung gian ở cuối
       tầm tính toán của mình; thành công đến từ sự kết hợp, không từ một
       thứ riêng lẻ
```

### Tiểu mục "Being of Two Minds" — giữ cùng lúc góc nhìn của mình và của đối thủ

```text
       Phải chơi từ góc nhìn của CẢ HAI bên; đoán đối thủ còn khó hơn tính
       nước đi của mình
                                │
                                ▼
       Nếu cả hai phân tích được toàn bộ cây, hai bên sẽ đồng ý ngay từ đầu
       ván cờ diễn ra thế nào; nhưng khi chỉ xét được một số nhánh, đối thủ
       có thể thấy điều mình không thấy hoặc bỏ sót điều mình thấy
                                │
                                ▼
       Phải dự đoán đối thủ SẼ làm gì thật, không phải mình sẽ làm gì nếu
       ở vị trí họ
       · khó "cởi giày của mình" khi đi giày người khác: mình biết quá rõ
         kế hoạch của mình; vì thế không ai chơi cờ hay poker với chính mình
       · phải biết điều họ biết, không biết điều họ không biết, và mang
         mục tiêu của họ chứ không phải mục tiêu mình mong họ có
       · thực tế: doanh nghiệp diễn tập kịch bản kinh doanh thường thuê
         người ngoài đóng vai đối thủ để "đối thủ" không biết quá nhiều;
         bài học lớn nhất thường đến từ những nước đi không lường trước
```

### Tình huống "The Tale of Tom Osborne and the '84 Orange Bowl" — câu chuyện Tom Osborne và trận Orange Bowl 1984

```text
       Orange Bowl 1984: Nebraska Cornhuskers (bất bại) gặp Miami Hurricanes
       (thua một trận); Nebraska thành tích tốt hơn nên chỉ cần HOÀ là xếp
       hạng nhất mùa giải
                                │
                                ▼
       Luật bóng bầu dục đại học: sau khi ghi touchdown, đội ghi điểm được
       chơi thêm một pha cách vạch cầu môn 2,5 yard:
       · đá bóng qua cột (an toàn hơn): thêm 1 điểm
       · chạy hoặc chuyền bóng vào vùng cấm địa (rủi ro hơn): thêm 2 điểm
                                │
                                ▼
       DIỄN BIẾN THẬT
       · đầu hiệp 4: Nebraska thua 17–31
       · touchdown: 23–31 → Osborne chọn đá 1 điểm, thành công: 24–31
       · phút cuối, touchdown nữa: 30–31; đá 1 điểm sẽ hoà và giành ngôi
         đầu, nhưng Osborne muốn thắng một cách thuyết phục
       · thử 2 điểm: Irving Fryar nhận bóng nhưng không ghi được
       · Miami và Nebraska cùng thành tích; Miami thắng đối đầu nên xếp
         hạng nhất
                                │
                                ▼
       PHÂN TÍCH CỦA HAI TÁC GIẢ: không chê việc Osborne muốn thắng; chê
       THỨ TỰ. Khi kém 14 điểm, ông cần 2 touchdown và tổng cộng 3 điểm
       phụ. Lẽ ra phải thử 2 điểm TRƯỚC:
       ┌──────────────────────────┬─────────────────────────────────────┐
       │ Kết quả hai lần thử      │ So sánh hai thứ tự                  │
       ├──────────────────────────┼─────────────────────────────────────┤
       │ cả hai đều thành công    │ thứ tự không quan trọng             │
       │ trượt lần 1 điểm, trúng  │ thứ tự không quan trọng: hoà, vô    │
       │ lần 2 điểm               │ địch                                │
       │ trượt lần 2 điểm         │ thứ tự của Osborne (1 rồi 2): thua  │
       │                          │ ván, mất ngôi                       │
       │                          │ thử 2 điểm trước: đang 23–31, ghi   │
       │                          │ touchdown tiếp thành 29–31, còn một │
       │                          │ lần thử 2 điểm để hoà và vô địch    │
       └──────────────────────────┴─────────────────────────────────────┘
       Chú thích của tác giả: trận hoà kiểu này đến từ một lần cố thắng
       bất thành, nên không ai trách Osborne chơi để hoà
                                │
                                ▼
       Phản bác lập luận "tinh thần": "nếu thử 2 điểm trước mà trượt, đội
       sẽ chơi để hoà và mất hứng; để đến cuối thì đội sẽ vượt lên khi
       tất cả đặt cược vào một pha"
       · trượt lần 2 điểm ở cuối là thua; trượt ở đầu vẫn còn cơ hội hoà;
         cơ hội nhỏ vẫn hơn không
       · hàng thủ Miami cũng sẽ "vượt lên" trong pha quyết định
       · nếu có hiệu ứng đà, thành công 2 điểm ở touchdown đầu càng giúp
         ghi touchdown sau; nó còn cho phép hoà bằng hai cú đá phạt ghi
         điểm (field goal)
                                │
                                ▼
       BÀI HỌC CHUNG: nếu phải mạo hiểm, hãy mạo hiểm càng sớm càng tốt
       · quần vợt: giao bóng một mạo hiểm, giao bóng hai thận trọng
       · thất bại sớm thì trò chơi chưa kết thúc, còn thời gian cho lựa
         chọn khác; áp dụng cho nghề nghiệp, đầu tư, hẹn hò
                                │
                                ▼
       Luyện thêm ở Chương 14: "Here's Mud in Your Eye", "Red I Win, Black
       You Lose", "The Shark Repellent That Backfired", "Tough Guy, Tender
       Offer", "The Three-Way Duel", "Winning without Knowing How"
```

## Ba câu hỏi chương này trả lời

1. **Khi đối thủ sẽ hành động sau mình, làm sao chọn nước đi bây giờ?** Theo Quy tắc 1: nhìn về phía trước và suy luận ngược lại. Vẽ (hoặc hình dung) cây trò chơi, bắt đầu từ các điểm cuối, xác định người đi sau sẽ chọn gì ở mỗi điểm rẽ, cắt bỏ các nhánh họ sẽ không chọn, rồi lùi dần về nước đi hiện tại. Trong trò 21 lá cờ, lập luận này cho thấy người đi đầu nên nhổ 1 lá rồi luôn để đối thủ gặp 20, 16, 12, 8, 4 lá.
2. **Có thêm quyền lựa chọn có luôn tốt không?** Với người quyết định một mình thì có; trong trò chơi thì không nhất thiết. Khi tổng thống Mỹ có quyền phủ quyết từng khoản, Quốc hội biết trước gói chi tiêu sẽ bị cắt riêng phần mình thích, nên không thông qua gói nữa; kết cục cả hai bên chỉ được điểm 2 thay vì điểm 3 như khi tổng thống không có quyền đó.
3. **Con người có thật sự hành xử như suy luận ngược dự đoán không?** Chỉ một phần. Trong trò chơi tối hậu thư, lý thuyết với giả định ích kỷ dự đoán người đề nghị chỉ cho 1 xu, nhưng thực tế đề nghị trung vị là 40–50% và đề nghị dưới 20% bị từ chối khoảng một nửa số lần. Hai tác giả kết luận rằng lỗi chủ yếu không nằm ở việc suy luận ngược (người ta học nhanh) mà ở giả định ích kỷ thuần tuý: con người còn quan tâm tới công bằng, vị tha, xấu hổ, và nổi giận khi bị đối xử bất công.

## Khái niệm cần biết

**Trò chơi tuần tự và trò chơi đồng thời (sequential game, simultaneous game).** Trong trò chơi tuần tự, người chơi đi lần lượt và thấy nước đi trước của nhau; trong trò chơi đồng thời, họ hành động cùng lúc hoặc không thấy người kia đã làm gì. Ví dụ: Charlie Brown và Lucy, trò 21 lá cờ là trò chơi tuần tự; thủ môn và cầu thủ sút phạt đền là trò chơi đồng thời. Phân biệt hai loại là bước đầu tiên khi gặp một tình huống chiến lược, vì mỗi loại cần một công cụ khác nhau; Chương 2 chỉ xử lý loại thứ nhất.

**Suy luận ngược, Quy tắc 1 (backward reasoning, rollback; "look forward and reason backward").** Cách giải trò chơi tuần tự: dự đoán các nước đi về sau của mọi người chơi, bắt đầu từ cuối trò chơi rồi lùi dần về hiện tại. Ví dụ: muốn đối thủ gặp 4 lá cờ ở lượt cuối thì phải để họ gặp 8, rồi 12, 16, 20; vậy với 21 lá phải nhổ 1. Đây là công cụ trung tâm của chương và của cả cuốn sách.

**Cây quyết định và cây trò chơi (decision tree, game tree).** Sơ đồ phân nhánh thể hiện các lựa chọn nối tiếp nhau; gọi là cây quyết định khi chỉ có một người ra quyết định, cây trò chơi khi các điểm rẽ thuộc về những người chơi khác nhau. Ví dụ: cây Princeton – New York (xe buýt, tàu, ô tô rồi các tuyến tiếp theo) là cây quyết định; cây Charlie – Fredo là cây trò chơi. Cây buộc người phân tích ghi ra lựa chọn của người khác ở mọi điểm rẽ, kể cả những điểm không xảy ra trên thực tế.

**Cắt tỉa nhánh (pruning).** Khi suy luận ngược, gạch bỏ khỏi cây những nhánh mà người chơi ở điểm rẽ đó sẽ không chọn. Ví dụ: Charlie gạch bỏ nhánh "Lucy để Charlie đá", nên "nhận lời" chỉ còn dẫn tới cú ngã. Cắt tỉa biến một cây lớn thành một chuỗi lựa chọn đơn giản.

**Trò chơi tổng bằng không và không tổng bằng không (zero-sum, non-zero-sum).** Trong trò chơi tổng bằng không, phần một bên được đúng bằng phần bên kia mất; trong trò chơi không tổng bằng không, cả hai có thể cùng được hoặc cùng mất. Ví dụ: "Charlie đầu tư, Fredo giữ hợp đồng" cho Charlie 150.000 USD và Fredo 250.000 USD, tốt cho cả hai hơn "không đầu tư" (0 và 0). Phần lớn trò chơi trong kinh doanh và đời sống là không tổng bằng không, vừa có lợi ích chung vừa có xung đột.

**Giá trị của cam kết (advantage of commitment).** Trong trò chơi, tự hạn chế lựa chọn của mình có thể có lợi vì nó thay đổi hành vi của người khác. Ví dụ: tổng thống không có quyền phủ quyết từng khoản được điểm 3; có quyền đó chỉ được điểm 2. Chương này chỉ nêu ý; Chương 6 và 7 phát triển đầy đủ.

**Độ tin cậy của lời hứa (credibility).** Một lời hứa chỉ có giá trị nếu khi đến lúc thực hiện, người hứa vẫn có lợi khi giữ lời. Ví dụ: Fredo hứa trả 250.000 USD, nhưng khi đã cầm tiền, bỏ trốn cho Fredo 500.000 USD, nên lời hứa không đáng tin nếu thiếu một cơ chế ràng buộc. Chương này cho thấy chính người hứa cũng thiệt khi không làm lời hứa đáng tin được.

**Ba loại bất định (natural chance, uncertainty about motives, strategic uncertainty).** Bất định tự nhiên là yếu tố may rủi (bài đối thủ cầm); bất định về mục tiêu là không biết chắc người khác muốn gì; bất định chiến lược là không biết người khác vừa chọn gì. Trò 21 lá cờ không có loại nào nên giải trọn được bằng suy luận ngược. Khái niệm này giải thích vì sao phần lớn trò chơi thực tế cần thêm công cụ khác.

**Trò chơi tối hậu thư và trò chơi độc tài (ultimatum game, dictator game).** Trò tối hậu thư: người đề nghị chia một khoản tiền, người đáp chỉ chọn nhận hoặc từ chối (từ chối thì cả hai không được gì). Trò độc tài: người chia quyết định, người kia không có quyền từ chối. Ví dụ: lý thuyết dự đoán đề nghị 1 xu trên 100 USD; thực tế đề nghị trung vị 40–50%; trong trò độc tài, người chia cho ít hơn nhưng vẫn rõ ràng trên 0. So sánh hai trò giúp tách động cơ hào phóng khỏi động cơ sợ bị từ chối.

**Sở thích quan tâm tới người khác (other-regarding preferences).** Mục tiêu của người chơi bao gồm cả công bằng, vị tha, tránh xấu hổ, mong muốn trừng phạt người cư xử bất công, chứ không chỉ tiền của mình. Ví dụ: 6 trên 26 sinh viên Harvard từ chối nhận 5 USD (để người chia giữ 35 USD), chấp nhận cả hai được 0. Hai tác giả coi đây là bài học quan trọng nhất từ thí nghiệm: suy luận ngược vẫn đúng, nhưng phải đưa các mục tiêu này vào trò chơi.

**Đánh giá thế trung gian (evaluation of intermediate positions).** Khi cây quá lớn để tính đến cuối, người chơi tính trước một số nước rồi dùng kinh nghiệm để chấm điểm thế cờ đạt được. Ví dụ: cờ vua có khoảng 10^120 nút; chuyên gia chỉ nhìn trước khoảng 5 cặp nước rồi đánh giá thế cờ theo số quân và cách phối hợp. Đây là cách áp dụng Quy tắc 1 cho các trò chơi phức tạp ngoài đời.

## Nội dung chi tiết

### 1. Đến lượt anh, Charlie Brown (It's Your Move, Charlie Brown)

Chương mở bằng một mô-típ lặp lại trong truyện tranh *Peanuts*: Lucy giữ quả bóng bầu dục trên mặt đất và mời Charlie Brown chạy tới đá; vào giây cuối, Lucy giật bóng đi, Charlie đá vào không khí và ngã ngửa, còn Lucy thích thú. Trang truyện in đầu chương (hình dựng lại từ sách, kể lại bằng lời) cho thấy một biến thể: Charlie từ chối vì biết Lucy sẽ giật bóng, nhưng Lucy chìa ra tờ chương trình đã in sẵn ghi rằng "một giờ chiều, Lucille Van Pelt sẽ giữ bóng và Charles Brown sẽ chạy tới đá". Charlie tin rằng chương trình đã in thì không thể rút lui, hăm hở lao tới, và lại ngã. Lucy kết luận: chương trình nào cũng có vài thay đổi phút chót.

Theo hai tác giả, ai cũng có thể bảo Charlie đừng chơi. Kể cả nếu Lucy chưa từng lừa anh năm ngoái (và các năm trước nữa), Charlie biết tính Lucy qua những hoàn cảnh khác. Hành động của Lucy nằm ở tương lai, nhưng điều đó không có nghĩa nó bất định: trong hai kết cục "để Charlie đá" và "thấy Charlie ngã", Lucy thích kết cục sau, nên Charlie phải dự đoán Lucy sẽ giật bóng. Khả năng Lucy để anh đá chỉ tồn tại trên lý thuyết; dựa vào nó, mượn câu Samuel Johnson nói về chuyện tái hôn, là "chiến thắng của hy vọng trước kinh nghiệm". Charlie nên từ chối.

### 2. Hai loại tương tác chiến lược và quy tắc thứ nhất (Two Kinds of Strategic Interactions; The First Rule of Strategy)

Bản chất của trò chơi chiến lược là quyết định của các người chơi phụ thuộc lẫn nhau. Sự phụ thuộc này có hai dạng. Dạng thứ nhất là **tuần tự**: người chơi đi lần lượt, như Charlie và Lucy; đến lượt mình, mỗi người phải nhìn trước xem nước đi hiện tại sẽ ảnh hưởng thế nào tới các nước đi sau này của đối thủ và của chính mình. Dạng thứ hai là **đồng thời**, như thế lưỡng nan của người tù ở Chương 1: người chơi hành động cùng lúc, không biết người khác đang làm gì, nhưng biết rằng người khác cũng đang tính toán như mình, và cứ thế tiếp tục; vì vậy mỗi người phải đặt mình vào vị trí của tất cả mọi người để tính kết cục chung, trong đó nước đi tốt nhất của mình là một phần.

Gặp một trò chơi chiến lược, việc đầu tiên là xác định nó thuộc loại nào. Có trò chơi mang cả hai yếu tố, như bóng bầu dục, và khi đó chiến lược phải phù hợp với từng bối cảnh. Chương này xây dựng sơ bộ các ý tưởng cho trò chơi tuần tự; trò chơi đồng thời để sang Chương 3. Hai tác giả chủ ý bắt đầu bằng những ví dụ rất đơn giản, thậm chí giả tạo, vì khi chiến lược đúng dễ thấy bằng trực giác, ý tưởng nền tảng sẽ hiện ra rõ hơn; ví dụ thực tế và phức tạp hơn đến ở các tình huống và chương sau.

Nguyên tắc chung cho trò chơi tuần tự là mỗi người chơi phải tính ra phản ứng tương lai của người khác và dùng chúng để chọn nước đi tốt nhất hiện tại. Hai tác giả coi nó quan trọng tới mức đặt thành **Quy tắc 1: Nhìn về phía trước và suy luận ngược lại**, tức dự đoán các quyết định ban đầu của mình rốt cuộc sẽ dẫn tới đâu và dùng thông tin đó để tính lựa chọn tốt nhất.

### 3. Cây quyết định và cây trò chơi (Decision Trees and Game Trees)

Với Charlie Brown, việc này dễ: anh chỉ có hai lựa chọn, và một trong hai dẫn tới quyết định giữa hai hành động của Lucy. Phần lớn tình huống chiến lược gồm chuỗi quyết định dài hơn, mỗi bước có nhiều lựa chọn; khi đó sơ đồ hình cây giúp suy luận đúng.

Ngay người quyết định một mình cũng có thể gặp chuỗi lựa chọn cần nhìn trước và suy luận ngược. Nhân vật trong bài thơ của Robert Frost đứng trong khu rừng lá vàng trước hai con đường, và chọn con đường ít người đi. Hình dựng lại từ sách:

```text
                               ┌──── Con đường nhiều người đi
       Rừng cây vàng ──────────┤
                               └──── Con đường ít người đi
```

Mỗi con đường có thể rẽ tiếp, và bản đồ phức tạp dần. Hai tác giả lấy ví dụ từ chính kinh nghiệm của mình: đi từ Princeton tới New York. Quyết định đầu tiên là phương tiện: xe buýt, tàu hoả hay ô tô. Người lái xe phải chọn tiếp giữa cầu Verrazano-Narrows, đường hầm Holland, đường hầm Lincoln và cầu George Washington. Người đi tàu chọn đổi sang tàu PATH ở Newark hay đi thẳng tới ga Penn Station. Tới New York, người đi tàu hoặc xe buýt lại chọn đi bộ, tàu điện ngầm (thường hay tốc hành), xe buýt hay taxi để tới đích. Lựa chọn tốt nhất phụ thuộc giá vé, tốc độ, mức ùn tắc dự kiến, điểm đến cụ thể ở New York, và mức độ ngại hít không khí trên đường cao tốc New Jersey Turnpike. Hình dựng lại từ sách:

```text
                  ┌─ Xe buýt ── tới bến Port Authority (phố 42 và
                  │             Đại lộ 8) ──────────────── các tuyến
                  │                                        nội thành
                  │           ┌─ đổi sang tàu PATH ở Newark, tới
                  │           │  khu downtown (WTC) ────── các tuyến
       Princeton ─┼─ Tàu hoả ─┤                            nội thành
                  │           └─ tới ga Penn Station (phố 33 Tây
                  │              và Đại lộ 7) ──────────── các tuyến
                  │                                        nội thành
                  │           ┌─ Cầu Verrazano
                  └─ Ô tô ────┼─ Đường hầm Holland
                              ├─ Đường hầm Lincoln
                              └─ Cầu George Washington
```

Bản đồ các điểm rẽ trông giống một cái cây đâm cành, nên gọi là "cây". Cách dùng sai là chọn nhánh đầu tiên trông hấp dẫn nhất (chẳng hạn vì nếu mọi thứ như nhau, bạn thích lái xe hơn đi tàu) rồi "tới cầu Verrazano hãy tính". Cách dùng đúng là dự đoán các quyết định về sau và dùng chúng để chọn bước đầu. Ví dụ: nếu muốn tới khu downtown, tàu PATH tốt hơn lái xe vì có tuyến nối thẳng từ Newark.

Có thể dùng đúng loại cây này cho trò chơi chiến lược, với một yếu tố mới: trò chơi có từ hai người chơi trở lên, và ở các điểm rẽ khác nhau có thể đến lượt những người khác nhau quyết định. Người chọn ở điểm trước phải nhìn trước không chỉ lựa chọn tương lai của mình mà cả của người khác, bằng cách đặt mình vào vị trí và suy nghĩ như họ. Để nhắc sự khác biệt này, hai tác giả gọi cây biểu diễn chuỗi quyết định trong trò chơi chiến lược là **cây trò chơi**, còn **cây quyết định** dành cho tình huống chỉ có một người.

### 4. Charlie Brown trong bóng bầu dục và trong kinh doanh (Charlie Brown in Football and in Business)

Câu chuyện Charlie Brown đơn giản đến mức buồn cười, nhưng là chỗ tốt để làm quen với cây trò chơi. Trò chơi bắt đầu khi Lucy đã mời và Charlie phải chọn nhận lời hay không. Nếu từ chối, trò chơi kết thúc. Nếu nhận lời, Lucy chọn giữa để Charlie đá và giật bóng đi. Charlie phải dự đoán Lucy chọn giật bóng, nên trong đầu anh cắt bỏ nhánh "để Charlie đá" khỏi cây. Khi đó, nhận lời dẫn thẳng tới cú ngã, nên lựa chọn tốt hơn là từ chối. Hình dựng lại từ sách (nhánh được chọn vẽ bằng nét đôi có mũi tên):

```text
                         Nhận lời            ╔══► Giật bóng đi
       Charlie ──┬──────────────────── Lucy ═╣
                 │                           ╚─── Để Charlie đá
                 │   Từ chối
                 ╚═══════════════════════════════► (trò chơi kết thúc)
```

Phiên bản kinh doanh: Charlie, nay đã trưởng thành, đi nghỉ ở Freedonia, một nước vốn theo chủ nghĩa Marx vừa cải cách. Một doanh nhân địa phương tên Fredo kể về những cơ hội kinh doanh béo bở nếu có vốn, rồi đề nghị: "Đầu tư 100.000 USD với tôi; một năm sau tôi biến nó thành 500.000 USD và chia đều với anh. Anh sẽ được hơn gấp đôi số tiền trong một năm." Cơ hội rất hấp dẫn, và Fredo sẵn sàng ký hợp đồng đàng hoàng theo luật Freedonia. Nhưng luật đó vững tới đâu? Nếu cuối năm Fredo ôm hết tiền, Charlie ở Mỹ có buộc được toà án Freedonia thi hành hợp đồng không? Toà có thể thiên vị người nước mình, quá chậm, hoặc bị Fredo mua chuộc. Hình dựng lại từ sách:

```text
                       Đầu tư             ╔══► Ôm tiền bỏ trốn
       Charlie ──┬─────────────── Fredo ══╣    Charlie: −100.000 USD
                 │                        ║    Fredo:    500.000 USD
                 │                        ╚─── Thực hiện hợp đồng
                 │                             Charlie:  150.000 USD
                 │                             Fredo:    250.000 USD
                 │   Không đầu tư
                 ╚════════════════════════════► Charlie: 0
                                                Fredo:   0
```

Nếu Fredo giữ hợp đồng, anh ta trả Charlie 250.000 USD; trừ 100.000 USD vốn ban đầu, Charlie lãi 150.000 USD. Không có lý do rõ ràng và mạnh để tin lời hứa, Charlie nên dự đoán Fredo bỏ trốn, giống như Charlie hồi nhỏ lẽ ra phải chắc chắn Lucy giật bóng. Hai cây giống nhau ở mọi điểm cốt yếu, vậy mà hai tác giả hỏi: đã có bao nhiêu "Charlie" suy luận sai trong những trò chơi như thế? Lời hứa của Fredo có thể đáng tin nếu anh ta còn nhiều việc làm ăn khác cần vốn từ Mỹ hoặc xuất hàng sang Mỹ: khi đó Charlie có thể trả đũa bằng cách huỷ danh tiếng của Fredo ở Mỹ hoặc tịch thu hàng của anh ta. Trò chơi này lúc đó là một phần của một trò chơi lớn hơn, có thể là một quan hệ lâu dài, đủ để giữ Fredo trung thực. Nhưng trong phiên bản chơi một lần như cây trên, logic suy luận ngược là rõ ràng.

Hai tác giả rút ra ba nhận xét. **Thứ nhất**, các trò chơi khác nhau có thể có dạng toán học giống hệt hoặc rất giống nhau (cùng cây, hoặc cùng bảng như ở các chương sau). Suy nghĩ bằng các hình thức đó làm lộ ra điểm tương đồng và giúp chuyển hiểu biết từ tình huống này sang tình huống khác. Đây là chức năng quan trọng của "lý thuyết" trong mọi lĩnh vực: chắt lọc điểm chung cốt yếu của những bối cảnh trông khác nhau để suy nghĩ về chúng một cách thống nhất và đơn giản hơn. Nhiều người có ác cảm bản năng với lý thuyết; hai tác giả cho rằng đó là phản ứng sai. Lý thuyết có giới hạn, và bối cảnh cụ thể cùng kinh nghiệm thường bổ sung hoặc điều chỉnh đáng kể các khuyến nghị của nó, nhưng bỏ hẳn lý thuyết là bỏ một điểm xuất phát quý giá, có thể là bàn đạp để giải quyết vấn đề. Hai tác giả khuyên hãy coi lý thuyết trò chơi là bạn, không phải ông kẹ.

**Thứ hai**, Fredo phải hiểu rằng một Charlie biết suy nghĩ chiến lược sẽ nghi ngờ lời mời và không đầu tư, làm Fredo mất cơ hội kiếm 250.000 USD. Vì thế Fredo có động cơ mạnh để làm lời hứa của mình đáng tin. Là một doanh nhân đơn lẻ, Fredo không thể cải thiện hệ thống pháp luật yếu kém của Freedonia; anh ta phải tìm cách khác. Vấn đề độ tin cậy và các công cụ tạo ra nó được bàn ở Chương 6 và 7.

**Thứ ba**, và có lẽ quan trọng nhất: khi so sánh các kết cục, không phải lúc nào một bên được nhiều hơn cũng có nghĩa bên kia được ít hơn. Kết cục "Charlie đầu tư, Fredo giữ hợp đồng" tốt cho cả hai hơn kết cục "Charlie không đầu tư". Khác với thể thao hay thi đấu, trò chơi không nhất thiết có người thắng kẻ thua; theo thuật ngữ lý thuyết trò chơi, chúng không nhất thiết là **trò chơi tổng bằng không**. Trò chơi có thể có kết cục cùng thắng hoặc cùng thua. Trong phần lớn trò chơi kinh doanh, chính trị và xã hội, lợi ích chung (cả Charlie và Fredo đều được nếu Fredo có cách cam kết đáng tin) và xung đột (Fredo có thể kiếm lợi trên lưng Charlie bằng cách bỏ trốn sau khi Charlie đã đầu tư) cùng tồn tại, và chính điều đó làm việc phân tích chúng thú vị và khó.

### 5. Những cây phức tạp hơn: quyền phủ quyết từng khoản (More Complex Trees)

Ví dụ phức tạp hơn một chút lấy từ chính trị Mỹ. Theo một hình ảnh biếm hoạ, Quốc hội thích các khoản chi "thùng thịt lợn" (pork-barrel, chi cho dự án địa phương để lấy lòng cử tri) còn tổng thống cố cắt bớt ngân sách phình to mà Quốc hội thông qua. Tất nhiên tổng thống cũng có khoản mình thích và khoản mình ghét, và chỉ muốn cắt khoản mình ghét; muốn vậy cần quyền gạch bỏ từng khoản riêng khỏi dự luật ngân sách, tức **quyền phủ quyết từng khoản** (line-item veto). Trong Thông điệp Liên bang tháng 1/1987, Ronald Reagan nói: hãy cho chúng tôi công cụ mà 43 thống đốc bang đang có, quyền phủ quyết từng khoản, để cắt đi những khoản lãng phí không bao giờ tự đứng được.

Thoạt nhìn, được tự do phủ quyết một phần dự luật chỉ có thể làm tổng thống mạnh hơn, không bao giờ làm ông thiệt. Nhưng tổng thống có thể tốt hơn khi không có công cụ này, vì sự tồn tại của nó làm Quốc hội đổi chiến lược soạn dự luật. Tình huống năm 1987 được giản lược thành hai khoản chi: cải tạo đô thị (U), Quốc hội thích; và hệ thống tên lửa chống tên lửa đạn đạo (M), tổng thống thích. Cả hai bên đều thích gói gồm cả hai khoản hơn hiện trạng. Bảng dựng lại từ sách (điểm xếp hạng, 4 là tốt nhất, 1 là tệ nhất):

| Kết quả | Quốc hội | Tổng thống |
|---|---|---|
| Cả U và M | 3 | 3 |
| Chỉ U | 4 | 1 |
| Chỉ M | 1 | 4 |
| Không khoản nào | 2 | 2 |

**Khi tổng thống không có quyền phủ quyết từng khoản**, ông chỉ có thể ký hoặc phủ quyết cả dự luật. Ông sẽ ký dự luật có cả U và M (điểm 3 hơn 2) hoặc chỉ có M (4 hơn 2), nhưng phủ quyết dự luật chỉ có U (2 hơn 1). Biết vậy, Quốc hội so sánh: gói U+M cho mình 3, chỉ U bị phủ quyết cho 2, chỉ M được ký cho 1, không gì cho 2; nên Quốc hội thông qua gói. Hai tác giả nhấn mạnh rằng phải ghi lựa chọn của tổng thống ở mọi điểm rẽ, kể cả những điểm trên thực tế không xảy ra vì Quốc hội đã chọn khác, vì lựa chọn thật của Quốc hội phụ thuộc vào việc tổng thống *sẽ* làm gì nếu Quốc hội chọn khác. Kết cục: mỗi bên được lựa chọn tốt thứ hai (điểm 3). Hình dựng lại từ sách (điểm ghi theo thứ tự Quốc hội, Tổng thống):

```text
       Quốc hội thông qua    Tổng thống quyết định        Điểm
       ╔══► U+M ──────────── Tổng thống ╔══► Ký            3, 3  ◄ KẾT QUẢ
       ║                                ╚─── Phủ quyết     2, 2
       ╠─── Chỉ U ────────── Tổng thống ╔─── Ký            4, 1
       ║                                ╚══► Phủ quyết     2, 2
       ╠─── Chỉ M ────────── Tổng thống ╔══► Ký            1, 4
       ║                                ╚─── Phủ quyết     2, 2
       ╚─── Không khoản nào ─────────────────────────────  2, 2
```

**Khi tổng thống có quyền phủ quyết từng khoản**, trước gói U+M ông có bốn lựa chọn: ký cả hai (3), phủ quyết riêng U (4), phủ quyết riêng M (1), phủ quyết cả hai (2). Ông sẽ phủ quyết riêng U, chỉ giữ M, cho Quốc hội điểm 1. Biết trước điều đó, Quốc hội không thông qua gói nữa; lựa chọn tốt nhất còn lại là thông qua chỉ U để bị phủ quyết, hoặc không thông qua gì (cả hai cho điểm 2). Có thể Quốc hội thích cách thứ nhất nếu kiếm được điểm chính trị khi tổng thống phủ quyết, nhưng tổng thống cũng có thể kiếm điểm vì thể hiện kỷ luật ngân sách; giả sử hai hiệu ứng triệt tiêu nhau, Quốc hội bàng quan giữa hai cách. Cách nào thì mỗi bên cũng chỉ được lựa chọn tốt thứ ba (điểm 2). Chính tổng thống cũng thiệt vì có thêm quyền. Hình dựng lại từ sách:

```text
       Quốc hội thông qua    Tổng thống quyết định        Điểm
       ╔─── U+M ──────────── Tổng thống ╔─── Ký cả hai     3, 3
       ║                                ╠══► Phủ quyết U   1, 4
       ║                                ╠─── Phủ quyết M   4, 1
       ║                                ╚─── Phủ quyết cả  2, 2
       ║                                     hai
       ╠══► Chỉ U ────────── Tổng thống ╔─── Ký            4, 1
       ║                                ╚══► Phủ quyết     2, 2  ◄ KẾT QUẢ
       ╠─── Chỉ M ────────── Tổng thống ╔══► Ký            1, 4
       ║                                ╚─── Phủ quyết     2, 2
       ╚══► Không khoản nào ─────────────────────────────  2, 2  ◄ KẾT QUẢ
```

Ví dụ này minh hoạ một điểm khái niệm quan trọng. Trong quyết định của một người, thêm tự do hành động không bao giờ có hại. Trong trò chơi, nó có thể có hại vì sự tồn tại của nó ảnh hưởng tới hành động của người chơi khác. Ngược lại, tự trói tay mình có thể có lợi; hai tác giả gọi đây là "lợi thế của cam kết" và bàn ở Chương 6 và 7.

Phương pháp suy luận ngược đã được dùng cho một trò chơi rất đơn giản (Charlie Brown) và một trò phức tạp hơn chút (quyền phủ quyết từng khoản). Nguyên tắc vẫn áp dụng được dù trò chơi phức tạp tới đâu, nhưng khi mỗi người có nhiều lựa chọn ở mỗi điểm và được đi nhiều lượt, cây nhanh chóng trở nên quá lớn để vẽ hay dùng. Trong cờ vua, từ gốc đã có 20 nhánh: quân trắng có thể đẩy một trong 8 con tốt lên 1 hoặc 2 ô, hoặc đi một trong 2 con mã theo một trong 2 cách. Với mỗi nước đó quân đen có 20 nước, nên đã có 400 đường đi khác nhau, và các nút về sau còn có nhiều nhánh hơn. Giải trọn cờ vua bằng cây vượt quá khả năng của máy tính mạnh nhất hiện có hoặc có thể có trong vài thập kỷ tới; phải tìm cách phân tích từng phần (bàn ở mục 11).

Giữa hai thái cực là rất nhiều trò chơi phức tạp vừa phải trong kinh doanh, chính trị, đời sống. Có hai cách xử lý: dùng phần mềm máy tính dựng cây và tính lời giải, hoặc giải bằng logic của cây mà không cần vẽ cây ra. Hai tác giả minh hoạ cách thứ hai bằng một trò chơi trong chương trình truyền hình mà khẩu hiệu là "chơi giỏi hơn, khôn hơn và trụ lâu hơn" người khác.

### 6. Chiến lược cho những "người sống sót" (Strategies for "Survivors")

Chương trình *Survivor* của đài CBS có nhiều trò chơi chiến lược thú vị. Trong tập 6 của *Survivor: Thailand*, hai đội (gọi là hai "bộ lạc") chơi một trò minh hoạ rất tốt việc nhìn trước và suy luận ngược, cả về lý thuyết lẫn thực tế. 21 lá cờ được cắm giữa sân; hai đội lần lượt nhổ cờ, mỗi lượt phải nhổ 1, 2 hoặc 3 lá (không được bỏ lượt, không được nhổ từ 4 lá trở lên). Đội nhổ lá cuối cùng, dù lá đó đứng một mình hay nằm trong nhóm 2–3 lá, thắng. Đội thua phải bỏ phiếu loại một thành viên của mình, làm đội yếu đi ở các thử thách sau. Trận thua này hoá ra quyết định: một thành viên của đội thắng về sau giành giải lớn 1 triệu USD. Hiểu đúng chiến lược của trò này vì thế đáng giá rất nhiều.

Hai đội tên là Sook Jai và Chuay Gahn; Sook Jai đi trước và nhổ 2 lá, để lại 19. Hai tác giả đề nghị người đọc dừng lại, tự chọn và ghi lại con số của mình trước khi đọc tiếp.

Hai sự cố giúp thấy rõ cách chơi đúng. Sự cố thứ nhất: trước trận, mỗi đội có vài phút bàn bạc. Trong đội Chuay Gahn, Ted Rogers, một kỹ sư phần mềm người Mỹ gốc Phi, nói: "Đến cuối, ta phải để lại cho họ 4 lá cờ." Điều này đúng: nếu Sook Jai gặp 4 lá, họ phải nhổ 1, 2 hoặc 3, và Chuay Gahn nhổ nốt 3, 2 hoặc 1 lá còn lại để thắng. Chuay Gahn thực sự có và tận dụng đúng cơ hội này: gặp 6 lá, họ nhổ 2.

Sự cố thứ hai: ở lượt ngay trước đó, Sook Jai gặp 9 lá và nhổ 3. Vừa quay về, Shii Ann, một đấu thủ sắc sảo, ăn nói lưu loát và tự hào về khả năng phân tích, nhận ra: "Nếu Chuay Gahn nhổ 2 bây giờ thì chúng ta tiêu." Nước đi vừa rồi của Sook Jai đã sai. Lẽ ra Shii Ann hoặc đồng đội phải lập luận như Ted rồi đẩy thêm một bước: làm sao bảo đảm đối thủ gặp 4 lá ở lượt sau của họ? Bằng cách để họ gặp 8 lá ở lượt này. Khi họ nhổ 1, 2 hoặc 3 trong 8 lá, ta nhổ 3, 2 hoặc 1 ở lượt sau và để lại 4 như dự tính. Vậy gặp 9 lá, Sook Jai lẽ ra phải nhổ đúng 1 lá và lật ngược thế cờ. Khả năng phân tích của Shii Ann bật lên chậm mất một nước.

Ted Rogers có lẽ sâu sắc hơn, nhưng cũng chưa đủ. Sook Jai gặp 9 lá vì ở lượt trước Chuay Gahn gặp 11 lá và nhổ 2. Nếu Ted đẩy lập luận của chính mình thêm một bước, Chuay Gahn đã nhổ 3, để Sook Jai gặp 8 lá, một thế thua.

Lập luận có thể đẩy tiếp về trước nữa. Muốn đối thủ gặp 8 lá thì phải để họ gặp 12 ở lượt trước; muốn vậy phải để họ gặp 16 ở lượt trước nữa, và 20 ở lượt trước đó. Vậy Sook Jai lẽ ra phải mở đầu bằng cách nhổ 1 lá chứ không phải 2; sau đó họ chắc thắng bằng cách để Chuay Gahn lần lượt gặp 20, 16, ..., 4 lá.

> **Chú thích của tác giả:** Người đi trước có luôn chắc thắng trong mọi trò chơi không? Không. Nếu trò chơi cờ bắt đầu với 20 lá thay vì 21, người đi sau mới chắc thắng. Và trong một số trò chơi, như cờ ca-rô 3×3 đơn giản, mỗi bên đều có thể bảo đảm hoà nếu chơi đúng.

Còn lượt đầu của Chuay Gahn: họ gặp 19 lá. Nếu đẩy logic của mình về đủ xa, họ đã nhổ 3, để Sook Jai gặp 16 lá và trên đường chắc thua. Từ bất kỳ điểm nào giữa trận mà đối thủ đã đi sai, đội đến lượt có thể giành thế chủ động và thắng. Nhưng Chuay Gahn cũng không chơi hoàn hảo.

> **Chú thích của tác giả:** Số phận của hai nhân vật chính cũng đáng chú ý. Ở tập tiếp theo, Shii Ann lại tính sai một lần quan trọng nữa và bị loại, xếp thứ 10 trong 16 người bắt đầu cuộc chơi. Ted, trầm lặng hơn nhưng có lẽ khéo léo hơn, vào được nhóm 5 người cuối cùng.

Bảng dựng lại từ sách so sánh nước đi thực tế với nước đi đúng ở mỗi lượt ("Không có nước thắng" nghĩa là nước nào cũng thua nếu đối thủ chơi đúng):

| Đội | Số cờ còn trước lượt | Số cờ đã nhổ | Nước đi đưa đội vào con đường chắc thắng |
|---|---|---|---|
| Sook Jai | 21 | 2 | 1 |
| Chuay Gahn | 19 | 2 | 3 |
| Sook Jai | 17 | 2 | 1 |
| Chuay Gahn | 15 | 1 | 3 |
| Sook Jai | 14 | 1 | 2 |
| Chuay Gahn | 13 | 1 | 1 |
| Sook Jai | 12 | 1 | Không có nước thắng |
| Chuay Gahn | 11 | 2 | 3 |
| Sook Jai | 9 | 3 | 1 |
| Chuay Gahn | 6 | 2 | 2 |
| Sook Jai | 4 | 3 | Không có nước thắng |
| Chuay Gahn | 1 | 1 | 1 |

Hai tác giả viết rằng gần như mọi lựa chọn đều sai, trừ nước của Chuay Gahn khi gặp 13 lá, và nước đó hẳn là ngẫu nhiên vì ở lượt sau, gặp 11 lá, họ lại nhổ 2 thay vì 3. (Ghi chú của người tổng hợp, như ở phần Lưu ý: chính bảng của sách cho thấy Chuay Gahn cũng đi đúng khi gặp 6 lá (nhổ 2, đúng như Ted đã tính) và khi gặp 1 lá (nhổ 1); phần lời của sách bỏ sót hai nước này.)

Trước khi chê hai đội, nên nhớ rằng học chơi cả những trò rất đơn giản cũng cần thời gian và kinh nghiệm. Hai tác giả cho từng cặp sinh viên hoặc từng nhóm sinh viên trong lớp chơi trò này, và thấy sinh viên năm nhất các trường Ivy League cần ba, thậm chí bốn ván mới hiểu trọn lập luận và chơi đúng từ nước đầu tiên. Người ta có vẻ học nhanh hơn khi xem người khác chơi so với khi tự chơi; có lẽ người quan sát dễ nhìn toàn cục và suy nghĩ bình tĩnh hơn người trong cuộc.

**Bài tập số 1 (Trip to the Gym No. 1).** Biến trò chơi cờ thành trò "củ khoai nóng": bây giờ đội nào buộc đội kia phải nhổ lá cuối cùng thì thắng. Đến lượt bạn và còn 21 lá; bạn nhổ mấy lá?

*Đáp án của sách (phần Workouts).* Bạn thắng nếu để đối thủ gặp 1 lá, vì họ buộc phải nhổ nó. Vậy bắt đầu một lượt với 2, 3 hoặc 4 lá là thế thắng. Người gặp 5 lá thua, vì nhổ thế nào cũng để lại cho đối thủ 2, 3 hoặc 4 lá. Đẩy thêm một vòng, người gặp 9 lá thua; tiếp tục như vậy, người bắt đầu với 21 lá ở thế thua (nếu đối thủ chơi đúng và luôn đưa tổng số giảm theo từng nhóm 4 lá). Một cách nhìn khác: người nhổ lá áp chót là người thắng, vì đối thủ chỉ còn 1 lá buộc phải nhổ; nhổ lá áp chót giống như nhổ lá cuối trong trò chơi bớt đi 1 lá. Với 21 lá, bạn coi như đang chơi trò 20 lá theo luật cũ và cố nhổ lá cuối cùng trong 20, và đó là thế thua nếu đối thủ hiểu trò chơi. Bài tập này cũng cho thấy người đi trước không phải lúc nào cũng có lợi, đúng như chú thích của tác giả ở trên.

### 7. Điều gì làm một trò chơi giải trọn được bằng suy luận ngược? (What Makes a Game Fully Solvable by Backward Reasoning?)

Trò 21 lá cờ giải trọn được nhờ một tính chất đặc biệt: không có bất định nào, dù là yếu tố may rủi tự nhiên, động cơ và năng lực của người chơi khác, hay hành động thực tế của họ. Hai tác giả giải thích từng loại.

**Bất định tự nhiên.** Trong trò 21 lá cờ, đội đến lượt luôn biết chính xác tình hình, tức còn bao nhiêu lá. Nhiều trò chơi có yếu tố may rủi thuần tuý: trong nhiều trò chơi bài, người chơi không biết chắc bài của người khác, dù các nước đi trước có thể cho căn cứ để suy đoán. Nhiều chương sau sẽ phân tích trò chơi có yếu tố này.

**Bất định về mục tiêu của người khác.** Đội đến lượt cũng biết mục tiêu của đội kia là thắng; Charlie Brown cũng phải biết Lucy thích thấy anh ngã. Trong nhiều trò chơi và môn thể thao đơn giản, người chơi biết rõ mục tiêu của nhau, nhưng trong kinh doanh, chính trị và quan hệ xã hội thì không. Động cơ ở đó là sự pha trộn phức tạp giữa ích kỷ và vị tha, quan tâm tới công lý hay công bằng, cân nhắc ngắn hạn và dài hạn. Muốn đoán người khác sẽ chọn gì ở các điểm sau, phải biết mục tiêu của họ, và nếu họ có nhiều mục tiêu thì họ đánh đổi giữa chúng thế nào. Gần như không bao giờ biết chắc được, nên phải đoán có căn cứ. Không được giả định người khác có cùng sở thích với mình, hay với một "người duy lý" giả định, mà phải thật sự nghĩ về hoàn cảnh của họ. Đặt mình vào vị trí người khác là việc khó, càng khó khi mình dính líu cảm xúc vào mục tiêu của chính mình. Với loại bất định này, có thể nên hỏi ý kiến một bên thứ ba khách quan, tức một nhà tư vấn chiến lược.

**Bất định chiến lược (strategic uncertainty).** Trong nhiều trò chơi, người chơi không biết người khác đã chọn gì; đây là bất định chiến lược, khác với các yếu tố may rủi tự nhiên như cách chia bài hay quả bóng nảy trên mặt sân gồ ghề. Trò 21 lá cờ không có loại bất định này vì mỗi đội thấy rõ đội kia vừa làm gì. Nhưng trong nhiều trò chơi, người chơi hành động cùng lúc hoặc nối nhau quá nhanh để kịp quan sát và phản ứng. Thủ môn đối mặt quả phạt đền phải quyết định đổ sang phải hay trái khi chưa biết cầu thủ sẽ sút hướng nào; cầu thủ giỏi giấu ý định tới phần nghìn giây cuối, khi thủ môn không còn kịp phản ứng. Giao bóng và cú đánh bóng qua người trong quần vợt cũng vậy; người tham gia đấu giá kín phải ra giá mà không biết người khác ra giá bao nhiêu. Cách suy nghĩ cần cho các trò chơi đồng thời này khác, và ở một số mặt khó hơn, suy luận ngược thuần tuý: mỗi người phải biết rằng người khác cũng đang lựa chọn có ý thức và đang nghĩ về điều mình nghĩ, và cứ thế. Các chương sau sẽ trình bày công cụ cho loại trò chơi đó; chương này chỉ tập trung vào trò chơi tuần tự, từ trò 21 lá cờ tới cờ vua ở mức phức tạp cao hơn nhiều.

### 8. Con người có thật sự giải trò chơi bằng suy luận ngược không? (Do People Actually Solve Games by Backward Reasoning?)

Suy luận ngược theo cây là cách đúng để phân tích và giải trò chơi tuần tự; ai không làm vậy, một cách tường minh hay theo trực giác, là đang tự làm hại mục tiêu của mình. Nhưng đó là cách dùng lý thuyết để khuyên (dùng theo nghĩa chuẩn tắc, normative). Câu hỏi khác là lý thuyết có giá trị giải thích (thực chứng, positive) như phần lớn lý thuyết khoa học không: thực tế có quan sát thấy kết cục mà lý thuyết dự đoán không? Các nhà nghiên cứu trong lĩnh vực kinh tế học hành vi và lý thuyết trò chơi hành vi đã làm nhiều thí nghiệm và cho kết quả lẫn lộn.

Phản bác có vẻ nặng nhất đến từ **trò chơi tối hậu thư**, trò mặc cả đơn giản nhất: chỉ có một lời đề nghị kiểu "chịu thì lấy, không thì thôi". Có hai người chơi, người đề nghị A và người đáp B, và một khoản tiền, chẳng hạn 100 USD. A đề nghị cách chia 100 USD; B quyết định có đồng ý không. Nếu đồng ý, mỗi người nhận phần A đề nghị và trò chơi kết thúc; nếu từ chối, không ai được gì và trò chơi kết thúc.

**Bài tập nhanh: trò chơi tối hậu thư đảo ngược (A Quick Trip to the Gym: Reverse Ultimatum Game).** Trong biến thể này, A đề nghị cách chia 100 USD; nếu B đồng ý, tiền được chia và trò chơi kết thúc. Nếu B từ chối, A quyết định có đưa đề nghị khác không, và mỗi đề nghị sau phải hào phóng hơn cho B. Trò chơi kết thúc khi B đồng ý hoặc A ngừng đề nghị. Kết cục sẽ thế nào? Sách trả lời ngay: có thể giả định A sẽ tiếp tục đề nghị cho tới khi chia 99 cho B và 1 cho mình, nên theo logic của cây, B được gần như toàn bộ. Nhưng hai tác giả khuyên: nếu bạn là B, đừng cố giữ để đòi bằng được tỷ lệ 99:1.

Trở lại trò tối hậu thư thường. Hãy nghĩ trò chơi sẽ diễn ra thế nào giữa hai người "duy lý" theo nghĩa của lý thuyết kinh tế truyền thống, tức mỗi người chỉ quan tâm tới lợi ích của mình và tính được hoàn hảo chiến lược tối ưu để theo đuổi lợi ích đó. A sẽ nghĩ: "Tôi chia thế nào thì B cũng chỉ chọn giữa phần đó và số 0. (Trò chơi chỉ chơi một lần nên B không có lý do để tạo tiếng cứng rắn hay đáp trả kiểu ăn miếng trả miếng.) Vậy B sẽ nhận bất cứ gì tôi đưa. Tốt nhất cho tôi là đưa B ít nhất có thể, chẳng hạn 1 xu nếu đó là mức tối thiểu luật cho phép." Vậy A đưa mức tối thiểu và B nhận.

> **Chú thích của tác giả:** Lập luận này là một ví dụ nữa về logic của cây mà không cần vẽ cây.

Đã có rất nhiều thí nghiệm về trò này. Thường thì khoảng hai chục người được đưa tới và ghép cặp ngẫu nhiên; trong mỗi cặp, vai người đề nghị và người đáp được phân, trò chơi chơi một lần; rồi các cặp mới được ghép ngẫu nhiên và chơi tiếp. Người chơi thường không biết mình được ghép với ai. Nhờ vậy người làm thí nghiệm có nhiều quan sát từ cùng một nhóm người trong một buổi, nhưng không có khả năng hình thành quan hệ lâu dài ảnh hưởng tới hành vi. Trong khuôn khổ đó, người ta thử nhiều biến thể điều kiện để xem tác động.

Kết quả khác lý thuyết, thường rất xa:

| Chỉ tiêu | Kết quả thí nghiệm |
|---|---|
| Đề nghị 1 xu, 1 USD, hay bất cứ mức nào dưới 10% tổng số tiền | Rất hiếm |
| Đề nghị trung vị (một nửa người đề nghị đưa ít hơn, một nửa đưa nhiều hơn) | Trong khoảng 40–50% |
| Đề nghị phổ biến nhất | Trong nhiều thí nghiệm là chia đôi 50:50 |
| Đề nghị cho người đáp dưới 20% | Bị từ chối khoảng một nửa số lần |

### 9. Phi lý trí hay lý trí có quan tâm tới người khác (Irrationality versus Other-Regarding Rationality)

Vì sao người đề nghị chia cho người đáp phần đáng kể? Có ba lý do khả dĩ: không suy luận ngược đúng được; có động cơ khác ngoài mong muốn ích kỷ được nhiều nhất (vị tha, quan tâm tới công bằng); hoặc sợ người đáp từ chối đề nghị thấp. Lý do thứ nhất khó xảy ra vì logic ở đây quá đơn giản. Trong tình huống phức tạp hơn, người chơi có thể không tính hết hoặc tính sai, nhất là khi mới chơi, như trong trò 21 lá cờ; nhưng trò tối hậu thư đủ đơn giản cả với người mới. Vậy lời giải thích phải là lý do thứ hai, thứ ba, hay kết hợp cả hai.

Kết quả ban đầu nghiêng về lý do thứ ba. Al Roth (Harvard) và cộng sự thấy rằng, với các ngưỡng từ chối phổ biến trong nhóm người tham gia của họ, người đề nghị chọn mức chia đạt cân bằng tối ưu giữa triển vọng được phần lớn hơn và rủi ro bị từ chối; nghĩa là người đề nghị duy lý theo nghĩa truyền thống một cách đáng kinh ngạc.

Nghiên cứu sau đó, nhằm tách lý do thứ hai khỏi thứ ba, dẫn tới một ý khác. Để phân biệt vị tha với tính toán chiến lược, người ta dùng biến thể gọi là **trò chơi độc tài**: người đề nghị quyết định cách chia, người kia hoàn toàn không có quyền lên tiếng. Người chia trong trò độc tài cho đi ít hơn đáng kể so với trong trò tối hậu thư, nhưng vẫn cho nhiều hơn 0 rõ rệt. Vậy cả hai lời giải thích đều có phần đúng: hành vi trong trò tối hậu thư vừa có mặt hào phóng vừa có mặt chiến lược.

Sự hào phóng xuất phát từ vị tha hay từ quan tâm tới công bằng? Cả hai là những khía cạnh khác nhau của cái có thể gọi là sự quan tâm tới người khác trong sở thích của con người. Một biến thể khác giúp tách chúng. Thông thường, vai người đề nghị và người đáp được phân bằng cơ chế ngẫu nhiên như tung đồng xu, điều có thể gợi lên ý niệm bình đẳng trong đầu người chơi. Để loại bỏ yếu tố đó, một biến thể tổ chức một cuộc thi sơ bộ, như kiểm tra kiến thức chung, và cho người thắng làm người đề nghị. Người đề nghị khi đó thấy mình "xứng đáng", và đề nghị trung bình thấp hơn khoảng 10%. Nhưng đề nghị vẫn xa trên 0, cho thấy có yếu tố vị tha. Người đề nghị không biết người đáp là ai, nên đây phải là lòng vị tha chung chung, không phải quan tâm tới một người cụ thể.

Còn một khả năng thứ ba trong sở thích cá nhân: phần đóng góp có thể xuất phát từ cảm giác xấu hổ. Jason Dana (Đại học Illinois), Daylian Cain (Trường Quản trị Yale) và Robyn Dawes (Đại học Carnegie-Mellon) làm thí nghiệm với một biến thể của trò độc tài. Người chia được giao 10 USD. Sau khi chia xong, nhưng trước khi tiền được giao cho người kia, người chia được đề nghị: bạn có thể lấy 9 USD, người kia không được gì và sẽ không bao giờ biết mình là một phần của thí nghiệm. Phần lớn người chia nhận đề nghị này. Họ thà mất 1 USD để người kia không bao giờ biết họ tham lam tới mức nào. (Một người vị tha sẽ thích giữ 9 USD và cho đi 1 USD hơn là giữ 9 USD mà người kia không được gì.) Ngay cả người chia đã định cho 3 USD cũng thà rút lại để người kia không biết. Hai tác giả so sánh việc này với chuyện chịu tốn công băng qua đường chỉ để khỏi phải cho người ăn xin một khoản nhỏ.

Hai tác giả lưu ý hai điều về các thí nghiệm này. Thứ nhất, chúng theo đúng phương pháp khoa học: kiểm định giả thuyết bằng các biến thể có kiểm soát được thiết kế phù hợp (nhiều biến thể khác được bàn trong cuốn sách của Colin Camerer về lý thuyết trò chơi hành vi). Thứ hai, trong khoa học xã hội, nhiều nguyên nhân thường cùng tồn tại, mỗi nguyên nhân giải thích một phần của cùng một hiện tượng; giả thuyết không nhất thiết đúng hoàn toàn hay sai hoàn toàn, và chấp nhận giả thuyết này không có nghĩa phải bác bỏ mọi giả thuyết khác.

Bây giờ xét hành vi của người đáp. Vì sao họ từ chối một đề nghị khi biết rằng từ chối thì được còn ít hơn? Lý do không thể là để tạo tiếng là người mặc cả cứng rắn nhằm có lợi trong những lần chơi sau, vì cùng một cặp không chơi lại với nhau và không ai được xem lịch sử hành vi của người khác. Nếu có động cơ danh tiếng ngầm, nó phải ở dạng sâu hơn: một quy tắc hành động chung mà người đáp làm theo mà không cần tính toán ở từng lần, tức một hành động bản năng hay một phản ứng do cảm xúc chi phối. Và thực tế đúng như vậy. Trong một hướng nghiên cứu thực nghiệm mới gọi là **kinh tế học thần kinh** (neuroeconomics), hoạt động não của người tham gia được chụp bằng cộng hưởng từ chức năng (fMRI) hoặc chụp cắt lớp phát xạ positron (PET) khi họ ra các quyết định kinh tế. Khi chơi trò tối hậu thư trong điều kiện đó, thuỳ đảo trước (anterior insula) của người đáp hoạt động mạnh hơn khi đề nghị càng bất bình đẳng. Thuỳ đảo trước hoạt động khi có các cảm xúc như giận dữ và ghê tởm, nên kết quả này giúp giải thích vì sao người đi sau từ chối đề nghị bất bình đẳng. Ngược lại, vỏ não trước trán bên trái hoạt động mạnh hơn khi người đáp vẫn chấp nhận một đề nghị bất bình đẳng, cho thấy họ đang kiểm soát có ý thức để cân giữa việc làm theo cảm giác ghê tởm và việc lấy thêm tiền.

Nhiều người, nhất là các nhà kinh tế, cho rằng người đáp có thể từ chối phần nhỏ của những khoản tiền nhỏ trong phòng thí nghiệm, nhưng ngoài đời, khi tiền đặt cược lớn hơn nhiều, việc từ chối hẳn rất hiếm. Để kiểm tra, người ta làm thí nghiệm ở các nước nghèo với số tiền bằng vài tháng thu nhập của người tham gia. Việc từ chối giảm đi đôi chút, nhưng đề nghị không bớt hào phóng đáng kể. Hậu quả của việc bị từ chối nặng hơn với người đề nghị cũng như với người đáp, nên người đề nghị sợ bị từ chối sẽ thận trọng hơn.

Hành vi có phần do bản năng, hormone hay cảm xúc gắn sẵn trong não, nhưng có phần thay đổi theo văn hoá. Trong các thí nghiệm ở nhiều nước, quan niệm về một đề nghị hợp lý chênh nhau tới 10% giữa các nền văn hoá, còn những đặc điểm như độ hung hăng hay cứng rắn chênh ít hơn. Chỉ một nhóm khác hẳn phần còn lại: người Machiguenga ở vùng Amazon thuộc Peru đưa đề nghị thấp hơn nhiều (trung bình 26%) và chỉ một đề nghị bị từ chối. Các nhà nhân học giải thích rằng người Machiguenga sống thành đơn vị gia đình nhỏ, ít gắn kết xã hội và không có chuẩn mực chia sẻ. Ngược lại, ở hai nền văn hoá, đề nghị vượt quá 50%; họ có tục cho tặng hào phóng khi gặp may, điều buộc người nhận phải đáp lại còn hào phóng hơn về sau. Chuẩn mực hay thói quen này dường như được mang vào thí nghiệm, dù người chơi không biết mình cho ai hay nhận từ ai.

### 10. Sự tiến hoá của lòng vị tha và tính công bằng (Evolution of Altruism and Fairness)

Nên rút ra bài học gì từ các thí nghiệm tối hậu thư và những thí nghiệm tương tự? Nhiều kết quả khác đáng kể so với dự đoán của lý thuyết suy luận ngược với giả định mỗi người chỉ quan tâm tới phần thưởng của mình. Trong hai giả định (người chơi suy luận ngược đúng, và người chơi ích kỷ thuần tuý), giả định nào sai, hay cả hai? Và hệ quả là gì?

**Về suy luận ngược.** Người chơi *Survivor* không làm đúng hoặc làm chưa trọn trong trò 21 lá cờ, nhưng họ chơi lần đầu, và cuộc bàn bạc của họ đã lộ ra những mảnh của lập luận đúng. Kinh nghiệm lớp học cho thấy sinh viên học được chiến lược đầy đủ sau ba, bốn lần chơi hoặc xem người khác chơi. Nhiều thí nghiệm, gần như tất yếu và có chủ ý, dùng người mới, mà hành động của họ thường là các bước trong quá trình học trò chơi. Ngoài đời, trong kinh doanh, chính trị, thể thao chuyên nghiệp, người ta có kinh nghiệm với trò chơi mình tham gia, nên có thể kỳ vọng họ đã tích luỹ nhiều hiểu biết hơn và nói chung chơi chiến lược tốt, bằng tính toán hoặc bằng bản năng đã rèn luyện. Với trò chơi phức tạp hơn một chút, người chơi có ý thức chiến lược có thể dùng máy tính hoặc thuê tư vấn để tính; việc này còn hiếm nhưng chắc chắn sẽ phổ biến. Vì vậy hai tác giả cho rằng suy luận ngược vẫn nên là điểm xuất phát để phân tích và dự đoán kết cục các trò chơi đó, rồi điều chỉnh khi cần trong từng bối cảnh để tính tới việc người mới có thể mắc lỗi và một số trò chơi quá phức tạp để tự giải.

**Về sở thích.** Hai tác giả cho rằng bài học quan trọng hơn từ nghiên cứu thực nghiệm là con người đưa vào lựa chọn của mình nhiều cân nhắc và sở thích ngoài phần thưởng của chính họ. Điều này vượt ra ngoài phạm vi lý thuyết kinh tế truyền thống. Các nhà lý thuyết trò chơi nên đưa vào phân tích mối quan tâm của người chơi tới công bằng hay vị tha. Hai tác giả dẫn Colin Camerer: lý thuyết trò chơi hành vi *mở rộng* tính duy lý chứ không từ bỏ nó. Đây là điều tốt: hiểu động cơ con người tốt hơn làm giàu thêm hiểu biết về cả quyết định kinh tế lẫn tương tác chiến lược. Và điều đó đang diễn ra: nghiên cứu tiên phong trong lý thuyết trò chơi ngày càng đưa vào mục tiêu của người chơi mối quan tâm tới công bằng, vị tha và những điều tương tự (thậm chí cả mối quan tâm "vòng hai": thưởng hoặc phạt người có hành vi tôn trọng hoặc vi phạm các chuẩn mực đó).

**Vì sao các chuẩn mực này bám rễ sâu.** Hai tác giả đi thêm một bước: vì sao mối quan tâm tới vị tha và công bằng, cùng sự giận dữ hay ghê tởm khi người khác vi phạm chúng, lại có sức mạnh lớn với con người như vậy? Đây là vùng suy đoán, nhưng tâm lý học tiến hoá đưa ra một giải thích hợp lý. Nhóm nào gieo vào thành viên chuẩn mực công bằng và vị tha sẽ ít xung đột nội bộ hơn nhóm gồm toàn cá nhân ích kỷ. Vì thế họ thành công hơn trong hành động tập thể, như cung cấp những thứ có lợi cho cả nhóm và giữ gìn tài nguyên chung, và tốn ít công sức, nguồn lực hơn cho xung đột nội bộ. Kết quả là họ làm tốt hơn, cả xét tuyệt đối lẫn khi cạnh tranh với các nhóm không có chuẩn mực tương tự. Nói cách khác, một mức độ công bằng và vị tha nhất định có thể có giá trị sống còn về mặt tiến hoá.

Một bằng chứng sinh học cho việc từ chối đề nghị bất công đến từ thí nghiệm của Terry Burnham:

| Chi tiết | Nội dung |
|---|---|
| Số tiền | 40 USD |
| Người tham gia | Sinh viên cao học nam ở Harvard |
| Lựa chọn của người chia | Chỉ có hai: cho 25 USD và giữ 15 USD, hoặc cho 5 USD và giữ 35 USD |
| Trong những người được đề nghị 5 USD | 20 người nhận, 6 người từ chối (cả mình và người chia đều được 0) |
| Phát hiện | 6 người từ chối có nồng độ testosterone cao hơn 50% so với những người nhận |

Nếu testosterone gắn với địa vị và tính hung hăng, đây có thể là một mối liên hệ di truyền giải thích lợi thế tiến hoá của cái mà nhà sinh học tiến hoá Robert Trivers gọi là "hung hăng vì đạo đức" (moralistic aggression). Ngoài con đường di truyền, xã hội còn truyền chuẩn mực bằng cách khác: giáo dục và xã hội hoá trẻ em trong gia đình và nhà trường. Cha mẹ và thầy cô dạy trẻ tầm quan trọng của việc quan tâm tới người khác, chia sẻ và cư xử tử tế; một phần chắc chắn in lại trong đầu trẻ và ảnh hưởng tới hành vi của chúng suốt đời.

Cuối cùng, hai tác giả nhắc rằng công bằng và vị tha có giới hạn. Tiến bộ và thành công dài hạn của một xã hội cần đổi mới và thay đổi, và những thứ đó lại cần chủ nghĩa cá nhân, sự sẵn lòng thách thức chuẩn mực xã hội và quan niệm thông thường; tính ích kỷ thường đi kèm các đặc điểm này. Cần một sự cân bằng đúng giữa hành vi vì mình và hành vi vì người khác.

### 11. Những cây rất phức tạp (Very Complex Trees)

Khi đã có chút kinh nghiệm với suy luận ngược, người ta sẽ thấy nhiều tình huống chiến lược trong đời sống và công việc có thể xử lý bằng "logic của cây" mà không cần vẽ và phân tích cây tường minh. Nhiều trò chơi phức tạp vừa phải khác có thể giải bằng các phần mềm ngày càng sẵn có. Nhưng với trò chơi phức tạp như cờ vua, lời giải trọn vẹn bằng suy luận ngược đơn giản là không khả thi.

Về nguyên tắc, cờ vua là trò chơi tuần tự lý tưởng để giải bằng suy luận ngược: hai bên đi lần lượt; mọi nước đi trước đều quan sát được và không thể rút lại; không có bất định về thế cờ hay động cơ của người chơi. Luật hoà khi một thế cờ lặp lại bảo đảm ván cờ kết thúc sau một số hữu hạn nước. Có thể bắt đầu từ các nút cuối và lùi dần. Nhưng thực tế khác nguyên tắc. Ước tính tổng số nút trong cờ vua là khoảng 10^120, tức số 1 theo sau 120 chữ số 0. Một siêu máy tính nhanh gấp 1.000 lần máy tính cá nhân thông thường sẽ cần 10^103 năm để xét hết. Chờ đợi là vô ích, và tiến bộ máy tính có thể thấy trước cũng không cải thiện đáng kể tình hình.

Các chuyên gia cờ vua đã mô tả thành công chiến lược tối ưu ở gần cuối ván. Khi trên bàn chỉ còn ít quân, họ có thể nhìn tới cuối ván và bằng suy luận ngược xác định một bên có chắc thắng hay bên kia có giữ được hoà không. Trung cuộc, khi còn nhiều quân, khó hơn nhiều: nhìn trước năm cặp nước, mức tối đa chuyên gia làm được trong thời gian hợp lý, không đủ để đưa tình huống tới một thế tàn cuộc giải được trọn vẹn.

Lời giải thực dụng là kết hợp phân tích nhìn trước với phán đoán giá trị. Phần thứ nhất là khoa học của lý thuyết trò chơi: nhìn trước và suy luận ngược. Phần thứ hai là nghệ thuật của người chơi: đánh giá giá trị một thế cờ từ số lượng và mối liên kết giữa các quân, không cần tìm lời giải tường minh từ đó tới cuối ván. Kỳ thủ thường gọi đó là "tri thức", nhưng cũng có thể gọi là kinh nghiệm, bản năng hay nghệ thuật; kỳ thủ giỏi nhất thường nổi bật ở chiều sâu và độ tinh tế của tri thức. Tri thức có thể được chắt lọc từ quan sát nhiều ván cờ, nhiều kỳ thủ và ghi thành quy tắc; việc này được làm nhiều nhất cho khai cuộc, tức 10 hay thậm chí 15 nước đầu, với hàng trăm cuốn sách phân tích ưu nhược điểm của các thế khai cuộc.

Máy tính ở đâu trong bức tranh này? Có thời, việc lập trình máy chơi cờ được coi là một phần của khoa học trí tuệ nhân tạo đang hình thành, với mục tiêu thiết kế máy suy nghĩ như người; nhiều năm không thành công. Rồi trọng tâm chuyển sang để máy làm việc nó giỏi nhất: tính toán. Máy có thể nhìn trước nhiều nước hơn và nhanh hơn người.

> **Chú thích của tác giả:** Nhưng kỳ thủ giỏi có thể dùng tri thức của mình để loại ngay những nước đi nhiều khả năng là tồi mà không cần theo dõi hệ quả của chúng bốn, năm nước sau, nhờ đó dành thời gian và công sức tính toán cho những nước nhiều khả năng là tốt.

Chỉ bằng tính toán thuần tuý, cuối thập niên 1990 các máy chơi cờ chuyên dụng như Fritz và Deep Blue đã đấu ngang các kỳ thủ hàng đầu. Gần đây hơn, máy được lập trình thêm một phần tri thức về thế trung cuộc do các kỳ thủ giỏi nhất truyền lại.

| Mốc | Sự kiện |
|---|---|
| Cuối thập niên 1990 | Fritz, Deep Blue cạnh tranh được với kỳ thủ hàng đầu bằng tính toán thuần tuý |
| Thời điểm viết sách | Máy tính xếp hạng cao nhất đạt hệ số Elo tương đương mức khoảng 2800 của kỳ thủ mạnh nhất thế giới là Garry Kasparov |
| Tháng 11/2003 | Kasparov đấu 4 ván với phiên bản mới nhất của Fritz (X3D): mỗi bên thắng 1, hoà 2 |
| Tháng 7/2005 | Máy Hydra đè bẹp Michael Adams (hạng 13 thế giới) trong trận 6 ván: thắng 5, hoà 1 |

Hai tác giả dự đoán có lẽ không lâu nữa các máy tính sẽ đứng đầu bảng và đấu với nhau để tranh chức vô địch thế giới.

Bài học từ cờ vua là phương pháp suy nghĩ về bất kỳ trò chơi rất phức tạp nào: kết hợp quy tắc nhìn trước và suy luận ngược với kinh nghiệm, thứ giúp đánh giá các thế trung gian ở cuối tầm tính toán của mình. Thành công đến từ sự tổng hợp giữa khoa học lý thuyết trò chơi và nghệ thuật chơi một trò cụ thể, không đến từ riêng thứ nào.

### 12. Giữ cùng lúc góc nhìn của mình và của đối thủ (Being of Two Minds)

Chiến lược cờ vua còn cho thấy một đặc điểm thực hành quan trọng của việc nhìn trước và suy luận ngược: phải chơi từ góc nhìn của cả hai bên. Tính nước đi tốt nhất của mình trong một cây phức tạp đã khó, đoán bên kia sẽ làm gì còn khó hơn. Nếu bạn và đối thủ đều phân tích được mọi nước đi và nước đáp, hai người sẽ đồng ý ngay từ đầu về diễn biến cả ván. Nhưng khi phân tích chỉ xét được một số nhánh, đối thủ có thể thấy điều bạn không thấy hoặc bỏ sót điều bạn thấy; cả hai trường hợp đều có thể dẫn tới một nước đi bạn không lường trước.

Muốn thật sự nhìn trước và suy luận ngược, phải dự đoán người khác *sẽ* làm gì, không phải bạn sẽ làm gì nếu ở vị trí họ. Khó khăn là khi đặt mình vào vị trí người khác, rất khó, nếu không nói là không thể, bỏ lại góc nhìn của chính mình: bạn biết quá rõ mình định làm gì ở nước sau và khó xoá hiểu biết đó khi nhìn ván cờ từ phía bên kia. Đó chính là lý do người ta không chơi cờ (hay poker) với chính mình; bạn chắc chắn không thể lừa chính mình hay tấn công bất ngờ chính mình.

Vấn đề này không có lời giải hoàn hảo. Khi đặt mình vào vị trí người khác, bạn phải biết điều họ biết và không biết điều họ không biết; mục tiêu của bạn phải là mục tiêu của họ, không phải mục tiêu bạn mong họ có. Trong thực tế, các doanh nghiệp muốn mô phỏng các nước đi và nước đáp trong một kịch bản kinh doanh thường thuê người ngoài đóng vai các bên khác, để những "đối thủ" này không biết quá nhiều. Bài học lớn nhất thường đến từ việc thấy những nước đi không lường trước và hiểu điều gì dẫn tới chúng, để tránh hoặc thúc đẩy kết cục đó.

### 13. Tình huống: Tom Osborne và trận Orange Bowl 1984 (Case Study: The Tale of Tom Osborne and the '84 Orange Bowl)

Hai tác giả kết chương bằng việc quay lại câu hỏi của Charlie Brown: có nên đá bóng không? Câu hỏi này trở thành vấn đề thật với huấn luyện viên bóng bầu dục Tom Osborne trong những phút cuối trận tranh chức vô địch, và theo hai tác giả, ông cũng quyết định sai.

Trong trận Orange Bowl 1984, đội Nebraska Cornhuskers chưa thua trận nào gặp đội Miami Hurricanes đã thua một trận. Vì Nebraska vào trận với thành tích tốt hơn, họ chỉ cần hoà để kết thúc mùa giải ở vị trí số một. Bước vào hiệp 4, Nebraska thua 17–31. Rồi họ bắt đầu lội ngược dòng và ghi một touchdown, rút ngắn tỷ số còn 23–31. Huấn luyện viên Osborne phải đưa ra một quyết định chiến lược quan trọng.

Trong bóng bầu dục đại học, đội vừa ghi touchdown được chơi thêm một pha từ vạch cách cầu môn 2,5 yard. Đội có thể chọn chạy (hoặc chuyền) bóng vào vùng cấm địa để ghi thêm 2 điểm, hoặc chọn cách ít rủi ro hơn là đá bóng qua cột để ghi thêm 1 điểm.

| Thời điểm | Diễn biến | Tỷ số (Nebraska–Miami) |
|---|---|---|
| Đầu hiệp 4 | Nebraska bị dẫn | 17–31 |
| Touchdown thứ nhất | Rút ngắn | 23–31 |
| Điểm phụ | Osborne chọn an toàn, đá 1 điểm thành công | 24–31 |
| Phút cuối, touchdown thứ hai | Rút ngắn còn 1 điểm; đá 1 điểm sẽ hoà và giành ngôi đầu | 30–31 |
| Điểm phụ | Osborne muốn thắng một cách thuyết phục nên thử 2 điểm; Irving Fryar nhận bóng nhưng không ghi được | 30–31 (thua) |

Một chiến thắng nhờ hoà sẽ không trọn vẹn; để vô địch một cách thuyết phục, Osborne nhận định phải chơi để thắng. Kết quả: Miami và Nebraska kết thúc năm với thành tích bằng nhau, và vì Miami thắng trận đối đầu, Miami được xếp hạng nhất.

**Phân tích.** Nhiều người "làm huấn luyện viên sau trận" chê Osborne vì chơi để thắng thay vì để hoà; hai tác giả không tranh cãi điểm đó. Theo họ, khi đã chấp nhận rủi ro thêm để thắng, Osborne lại làm sai cách. Lẽ ra ông nên thử 2 điểm trước: nếu thành công thì lần sau đá 1 điểm; nếu thất bại thì lần sau thử 2 điểm lần nữa.

Cụ thể, khi kém 14 điểm, ông biết mình cần hai touchdown cộng tổng cộng 3 điểm phụ. Ông chọn đá 1 điểm trước rồi thử 2 điểm sau. Nếu cả hai lần đều thành công, thứ tự không quan trọng. Nếu trượt lần 1 điểm nhưng lần 2 điểm thành công, thứ tự cũng không quan trọng, trận đấu hoà và Nebraska vô địch. Khác biệt duy nhất là khi Nebraska trượt lần 2 điểm. Theo kế hoạch của Osborne, điều đó nghĩa là thua trận và mất chức vô địch. Nếu thử 2 điểm trước và thất bại, họ chưa chắc đã thua: họ kém 23–31, ghi touchdown tiếp sẽ thành 29–31, và một lần thử 2 điểm thành công sẽ hoà trận và giành vị trí số một.

> **Chú thích của tác giả:** Hơn nữa, trận hoà này sẽ là kết quả của một lần cố thắng bất thành, nên không ai chỉ trích Osborne vì chơi để hoà.

Hai tác giả từng nghe phản bác: nếu Osborne thử 2 điểm trước và trượt, đội sẽ phải chơi để hoà, kém hứng khởi hơn và có thể không ghi được touchdown thứ hai; còn nếu chờ tới cuối và tung pha 2 điểm quyết định thắng thua, các cầu thủ sẽ vượt lên chính mình vì biết mọi thứ được đặt cược. Hai tác giả cho rằng lập luận này sai vì nhiều lý do. Nếu chờ tới touchdown thứ hai rồi mới trượt lần 2 điểm, Nebraska thua; nếu trượt ở lần thử đầu, vẫn còn cơ hội hoà, và dù cơ hội có giảm, có còn hơn không. Lập luận về "đà" cũng có vấn đề: hàng công Nebraska có thể vượt lên trong một pha quyết định chức vô địch, nhưng hàng thủ Miami cũng vậy, vì pha bóng quan trọng với cả hai. Nếu có hiệu ứng đà thật, thì thành công 2 điểm ở touchdown thứ nhất càng làm tăng cơ hội ghi touchdown thứ hai; nó còn cho phép Nebraska hoà bằng hai cú đá ghi điểm (field goal, mỗi cú 3 điểm).

Bài học chung: nếu phải chấp nhận rủi ro, thường nên làm càng sớm càng tốt. Người chơi quần vợt đều biết điều này: mạo hiểm hơn ở quả giao bóng thứ nhất và giao quả thứ hai thận trọng hơn. Như vậy nếu thất bại ở lần thử đầu, trò chơi chưa kết thúc, và bạn còn thời gian cho những lựa chọn khác có thể đưa bạn về lại, thậm chí vượt lên, vị trí cũ. Sự khôn ngoan của việc chấp nhận rủi ro sớm áp dụng cho hầu hết các mặt của cuộc sống: chọn nghề, đầu tư hay hẹn hò. Để luyện thêm nguyên tắc nhìn trước, suy luận ngược, hai tác giả giới thiệu các tình huống ở Chương 14: "Here's Mud in Your Eye", "Red I Win, Black You Lose", "The Shark Repellent That Backfired", "Tough Guy, Tender Offer", "The Three-Way Duel" và "Winning without Knowing How".

**Ví dụ hôm nay** (minh hoạ của người tổng hợp, con số là giả định). Một công ty khởi nghiệp sắp hết tiền và gặp một nhà đầu tư thiên thần. Nhà đầu tư đề nghị rót 2 tỷ đồng nếu nhà sáng lập nhường 40% cổ phần; nếu từ chối, nhà sáng lập có thể đi gọi vốn quỹ khác, mất 4 tháng, với xác suất thành công khoảng một nửa. Suy luận ngược bắt đầu từ cuối: nếu gọi vốn quỹ khác thất bại, công ty đóng cửa và cổ phần của nhà sáng lập bằng 0; nếu thành công, giả sử quỹ mới chỉ lấy 20%. Nhìn trước như vậy, giá trị kỳ vọng của việc từ chối là một nửa của 80% công ty, tức khoảng 40%, thấp hơn mức 60% nhà sáng lập giữ lại nếu nhận lời ngay. Nhưng nhà đầu tư thiên thần cũng suy luận ngược: họ biết nhà sáng lập sắp hết tiền nên không cần hạ điều kiện. Nhà sáng lập muốn có thế mạnh hơn phải thay đổi điểm cuối của cây (chẳng hạn cắt giảm chi phí để kéo dài thời gian còn tiền lên 8 tháng) trước khi ngồi vào bàn. Và theo bài học Orange Bowl, nếu định thử một hướng đi rủi ro (như thử ra mắt một sản phẩm mới để chứng minh thị trường), nên làm sớm, khi vẫn còn tiền để làm lại nếu thất bại.

## Luận điểm kinh tế cốt lõi

### Mệnh đề

Trong một trò chơi mà người chơi đi lần lượt và thấy được nước đi của nhau, lựa chọn đúng ở hiện tại được tìm bằng cách nhìn về phía trước tới tận các kết cục cuối cùng rồi suy luận ngược lại: xác định người đi sau sẽ chọn gì ở mỗi tình huống có thể xảy ra, và chọn nước đi hiện tại dựa trên những phản ứng đó. Phương pháp này cho lời giải trọn vẹn khi không có bất định, cho thấy có thêm lựa chọn chưa chắc đã có lợi, và vẫn là điểm xuất phát đúng ngay cả khi con người không hoàn toàn ích kỷ hoặc trò chơi quá lớn để tính hết.

### Giả định

- Trò chơi là tuần tự: người chơi đi lần lượt, mỗi nước đi được quan sát và không thể rút lại.
- Người đi trước biết hoặc đoán được mục tiêu của người đi sau (Lucy thích thấy Charlie ngã; Fredo muốn nhiều tiền nhất; đội Survivor muốn thắng).
- Không có bất định tự nhiên hay bất định chiến lược; nếu có, cần thêm công cụ của các chương sau.
- Người chơi đủ khả năng tính toán, hoặc đủ kinh nghiệm để có được kết quả tương đương.
- Lời hứa và lời đe doạ chỉ được tin nếu khi tới lúc, người đưa ra vẫn có lợi khi thực hiện.

### Cơ chế

1. Vẽ (hoặc hình dung) cây trò chơi: mỗi điểm rẽ thuộc về một người chơi, mỗi điểm cuối ghi kết quả của mọi người chơi.
2. Bắt đầu từ các điểm rẽ cuối cùng: xác định người chơi ở đó sẽ chọn nhánh nào theo mục tiêu của họ, và cắt bỏ các nhánh còn lại.
3. Lùi dần về các điểm rẽ trước, mỗi lần coi kết quả của nhánh là kết quả đã được xác định ở bước sau.
4. Phải xác định lựa chọn ở mọi điểm rẽ, kể cả điểm không xảy ra trên thực tế, vì lựa chọn của người đi trước dựa trên những tình huống giả định đó (như Quốc hội dựa trên việc tổng thống sẽ làm gì với từng loại dự luật).
5. Khi có thêm một lựa chọn cho mình, cả cây thay đổi, và người khác có thể đổi hành vi theo hướng bất lợi cho mình (quyền phủ quyết từng khoản).
6. Khi cây quá lớn, tính trước đến một độ sâu nhất định rồi dùng kinh nghiệm để đánh giá các thế trung gian (cờ vua).
7. Khi mục tiêu thật của con người gồm cả công bằng và vị tha, phải đưa chúng vào kết quả ở các điểm cuối; suy luận ngược vẫn áp dụng trên cây đã được sửa.

### Bằng chứng và ví dụ hai tác giả đưa ra

- Charlie Brown và Lucy: Charlie lẽ ra phải dự đoán Lucy giật bóng và từ chối.
- Cây quyết định của Robert Frost và hành trình Princeton – New York: chọn nhánh đầu dựa trên các lựa chọn về sau (tàu PATH khi muốn tới downtown).
- Charlie và Fredo ở Freedonia: đầu tư 100.000 USD, Fredo bỏ trốn được 500.000 USD, giữ lời thì Charlie lãi 150.000 USD và Fredo được 250.000 USD; thiếu cơ chế ràng buộc, Charlie nên không đầu tư.
- Quyền phủ quyết từng khoản (Reagan 1987, khoản U và M): không có quyền đó, cả hai bên được điểm 3; có quyền đó, cả hai chỉ được điểm 2.
- Cờ vua: 20 nước đi đầu, 400 nhánh sau một lượt mỗi bên, khoảng 10^120 nút, 10^103 năm cho một siêu máy tính.
- Trò 21 lá cờ trong *Survivor: Thailand*: chiến lược để đối thủ gặp số lá chia hết cho 4; cả hai đội đi sai phần lớn các nước; sinh viên Ivy League cần 3–4 ván để chơi đúng.
- Trò chơi tối hậu thư: đề nghị trung vị 40–50%, đề nghị dưới 20% bị từ chối khoảng một nửa; nghiên cứu của Al Roth; trò chơi độc tài; biến thể phân vai bằng cuộc thi (đề nghị giảm khoảng 10%).
- Thí nghiệm Dana, Cain, Dawes: phần lớn người chia chọn lấy 9 USD trên 10 USD để người kia không biết.
- Kinh tế học thần kinh: thuỳ đảo trước hoạt động mạnh khi đề nghị bất bình đẳng.
- Thí nghiệm ở nước nghèo với số tiền bằng vài tháng thu nhập; người Machiguenga (đề nghị trung bình 26%); hai nền văn hoá có đề nghị trên 50%.
- Thí nghiệm của Terry Burnham: 6 trên 26 người từ chối 5 USD, testosterone cao hơn 50%.
- Kasparov gặp X3D Fritz (2003, 1–1, hoà 2); Hydra thắng Michael Adams (2005, thắng 5 hoà 1).
- Orange Bowl 1984: Osborne đá 1 điểm trước rồi thử 2 điểm sau và thua; thử 2 điểm trước vẫn giữ được cơ hội hoà.

### Kết luận và hàm ý chính sách

- Trước mỗi quyết định trong một chuỗi tương tác, hãy hỏi: người kia sẽ phản ứng thế nào với từng lựa chọn của mình, và họ có lợi gì khi phản ứng như vậy?
- Đừng tin vào một lời hứa mà người hứa không có lợi khi giữ; nếu mình là người hứa, hãy tìm cách làm lời hứa đáng tin, vì chính mình cũng thiệt khi không ai tin.
- Đừng mặc định rằng có thêm quyền hay thêm lựa chọn là tốt; trong thiết kế thể chế (như quyền phủ quyết từng khoản), thêm quyền cho một bên có thể làm bên kia đổi hành vi và khiến mọi người cùng thiệt.
- Khi dự đoán hành vi người khác, phải tính tới mối quan tâm của họ về công bằng và cảm xúc; một đề nghị "hợp lý về tiền" nhưng bị coi là bất công có thể bị từ chối.
- Với vấn đề quá phức tạp, kết hợp tính toán với kinh nghiệm và thuê người ngoài đóng vai đối thủ để tránh tự lừa mình.
- Nếu phải mạo hiểm, hãy mạo hiểm sớm, khi còn đường lui.

### Trong ngôn ngữ kinh tế học

- **Quy nạp ngược (backward induction).** Tên gọi chuẩn trong lý thuyết trò chơi của phương pháp hai tác giả gọi là suy luận ngược. Định lý Zermelo (1913) chứng minh rằng mọi trò chơi tuần tự hữu hạn có thông tin hoàn hảo như cờ vua đều có lời giải xác định (một bên chắc thắng hoặc hai bên chắc hoà), dù không chỉ ra lời giải đó là gì; cờ vua chính là ví dụ "có lời giải nhưng không ai tính nổi".
- **Cân bằng hoàn hảo trong trò chơi con (subgame-perfect equilibrium).** Khái niệm của Reinhard Selten: chiến lược phải tối ưu ở mọi điểm rẽ, kể cả điểm không xảy ra. Yêu cầu của hai tác giả rằng phải ghi lựa chọn của tổng thống ở mọi điểm rẽ chính là ý tưởng này; Chương 2 tránh dùng thuật ngữ.
- **Trò chơi tin tưởng (trust game) và vấn đề cam kết.** Trò chơi Charlie – Fredo có cấu trúc của trò chơi tin tưởng trong kinh tế học thực nghiệm, và của vấn đề "giữ chân" (hold-up) trong kinh tế học hợp đồng: một bên phải bỏ vốn trước khi bên kia hành động, nên cần thể chế để bảo vệ.
- **Trò chơi Nim và lý thuyết trò chơi tổ hợp.** Trò 21 lá cờ là dạng đơn giản nhất của họ trò chơi Nim (trò chơi bớt dần một đống vật); "thế thua" là các số chia hết cho 4.
- **Sở thích xã hội (social preferences) và ác cảm với bất bình đẳng (inequity aversion).** Các mô hình trong kinh tế học hành vi đưa công bằng, vị tha, có đi có lại vào hàm lợi ích, đúng hướng mà hai tác giả gọi là "mở rộng tính duy lý".
- **Thứ tự đặt cược rủi ro và giá trị quyền chọn (sequencing of risky bets, option value).** Bài học Orange Bowl là một trường hợp của nguyên tắc giữ giá trị quyền chọn: đặt cược rủi ro sớm giữ lại khả năng điều chỉnh sau khi biết kết quả.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong chương |
|---|---|
| Sequential game / simultaneous game | Trò chơi tuần tự (đi lần lượt) / trò chơi đồng thời (đi cùng lúc) |
| Look forward and reason backward (Rule 1) | Nhìn về phía trước và suy luận ngược lại (Quy tắc 1 của chiến lược) |
| Backward reasoning / rollback | Suy luận ngược |
| Decision tree / game tree | Cây quyết định (một người) / cây trò chơi (nhiều người) |
| Node / terminal node | Nút (điểm rẽ) / nút cuối (điểm kết thúc) |
| Prune (a branch) | Cắt bỏ nhánh mà người chơi sẽ không chọn |
| Payoff | Kết quả (lợi ích) của người chơi ở một điểm cuối |
| Zero-sum / non-zero-sum | Tổng bằng không / không tổng bằng không |
| Abscond / honor the contract | Ôm tiền bỏ trốn / thực hiện hợp đồng |
| Credibility | Độ tin cậy của lời hứa, lời đe doạ |
| Commitment | Cam kết: tự trói tay mình để thay đổi hành vi người khác |
| Pork-barrel expenditures | Chi tiêu "thùng thịt lợn": chi cho dự án địa phương để lấy lòng cử tri |
| Line-item veto | Quyền phủ quyết từng khoản trong dự luật ngân sách |
| Strategic uncertainty | Bất định chiến lược: không biết người khác đã chọn gì |
| Normative / positive | Chuẩn tắc (khuyên nên làm gì) / thực chứng (giải thích điều thực sự xảy ra) |
| Ultimatum game | Trò chơi tối hậu thư |
| Proposer / responder | Người đề nghị / người đáp |
| Dictator game | Trò chơi độc tài |
| Other-regarding preferences | Sở thích quan tâm tới người khác (công bằng, vị tha) |
| Behavioral game theory | Lý thuyết trò chơi hành vi |
| Neuroeconomics | Kinh tế học thần kinh |
| Anterior insula | Thuỳ đảo trước, vùng não gắn với giận dữ và ghê tởm |
| Moralistic aggression | Hung hăng vì đạo đức (thuật ngữ của Robert Trivers) |
| Endgame / midgame / opening | Tàn cuộc / trung cuộc / khai cuộc (cờ vua) |
| Touchdown / extra point / two-point conversion | Ghi bàn chạm đất (6 điểm) / điểm phụ bằng cú đá (1 điểm) / điểm phụ bằng chạy hoặc chuyền (2 điểm) |
| Field goal | Cú đá ghi điểm qua cột (3 điểm) |
| Trip to the Gym | Bài tập luyện tập của sách, có đáp án ở phần Workouts |

## Câu nói đáng nhớ

> "Quy tắc 1: Nhìn về phía trước và suy luận ngược lại."
*"RULE 1: Look forward and reason backward."*

> "Trong quyết định của một người, thêm tự do hành động không bao giờ có hại. Nhưng trong trò chơi, nó có thể có hại vì sự tồn tại của nó có thể ảnh hưởng tới hành động của người chơi khác."
*"In single-person decisions, greater freedom of action can never hurt. But in games, it can hurt because its existence can influence other players' actions."*

> "Trò chơi không nhất thiết có kẻ thắng người thua."
*"Unlike sports or contests, games don't have to have winners and losers."*

> "Lý thuyết trò chơi hành vi mở rộng tính duy lý chứ không từ bỏ nó."
*"Behavioral game theory extends rationality rather than abandoning it."*

> "Phải dự đoán người khác sẽ thật sự làm gì, không phải bạn sẽ làm gì nếu ở vị trí của họ."
*"You have to predict what the other players will actually do, not what you would have done in their shoes."*

> "Nếu phải chấp nhận rủi ro, thường nên làm càng sớm càng tốt."
*"If you have to take some risks, it is often better to do so as quickly as possible."*

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương là dạy một công cụ khó bằng những ví dụ gần như hiển nhiên

Hai tác giả cố ý chọn ví dụ đơn giản đến mức buồn cười (Charlie Brown, 21 lá cờ) để người đọc thấy rõ cấu trúc của lập luận trước khi nó bị che lấp bởi chi tiết. Cách đặt hai cây Charlie – Lucy và Charlie – Fredo cạnh nhau là một bài học về giá trị của lý thuyết: hai câu chuyện khác hẳn nhau có cùng một cây, nên ai hiểu một câu chuyện sẽ hiểu câu chuyện kia. Trò 21 lá cờ được dựng rất khéo: người đọc được mời tự chọn trước, rồi thấy hai đội thật, có một người tự hào về khả năng phân tích, cũng chỉ nhìn được một bước. Đó là cách chứng minh rằng suy luận ngược tuy đơn giản về logic nhưng không tự nhiên với con người.

### Ví dụ quyền phủ quyết từng khoản là phát hiện phản trực giác đáng nhớ nhất

Ý tưởng rằng có thêm quyền có thể làm mình thiệt là điều người đọc phổ thông ít nghĩ tới, và nó dẫn thẳng tới chủ đề cam kết ở Phần II. Tuy vậy, kết quả phụ thuộc hoàn toàn vào bảng xếp hạng giả định: nếu Quốc hội thích "chỉ M" hơn "không gì" (chẳng hạn vì vẫn muốn ngân sách quốc phòng), kết cục sẽ khác. Hai tác giả trình bày đây là một "biếm hoạ" và một trò chơi đơn giản, nhưng không thảo luận độ nhạy của kết luận đối với các thứ hạng đó. Thêm nữa, trong thực tế ngân sách Mỹ gồm hàng nghìn khoản và được đàm phán lặp lại hằng năm, nên quyền phủ quyết từng khoản có thể được dùng như một lời đe doạ trong trò chơi lặp, khác với trò chơi một lần trong sách.

### Phần thí nghiệm tối hậu thư công bằng với cả lý thuyết lẫn phản biện

Hai tác giả không né bằng chứng bất lợi cho lý thuyết mà đặt nó ngay trong chương công cụ, rồi phân biệt rõ hai khả năng: con người tính sai, hay con người có mục tiêu khác. Kết luận rằng nên sửa giả định về sở thích chứ không bỏ suy luận ngược là một lập trường cân bằng và được phần lớn giới nghiên cứu chia sẻ. Điểm yếu là đoạn về tiến hoá và testosterone dựa vào một thí nghiệm với 26 người được đề nghị 5 USD; hai tác giả có nói đây là vùng suy đoán, nhưng người đọc nên coi mối liên hệ di truyền là giả thuyết, không phải kết luận.

### Chỗ sách tự mâu thuẫn nhẹ và chỗ trình bày chưa rõ

Như đã ghi ở phần Lưu ý, phần lời nói chỉ một nước đi của Chuay Gahn đúng, trong khi bảng của chính cuốn sách cho thấy ba nước đúng (khi còn 13, 6 và 1 lá). Bài tập "trò chơi tối hậu thư đảo ngược" cũng được trình bày chưa rõ: sách nói theo logic của cây, A sẽ đề nghị tới 99:1, rồi khuyên B đừng cố giữ đòi 99:1, mà không giải thích vì sao (người tổng hợp đoán rằng có thể vì A thật ngoài đời sẽ ngừng đề nghị khi thấy bị coi thường, giống người đáp trong trò thường từ chối đề nghị thấp). Người đọc nên coi đây là một câu đố để suy nghĩ hơn là một bài có lời giải chặt chẽ.

### Từ 2008, cờ vua máy tính đã đi xa hơn dự đoán của sách

Nói định tính: sau khi sách ra, các chương trình chơi cờ đã vượt hẳn mọi kỳ thủ, và các hệ thống tự học bằng mạng nơ-ron (như AlphaZero của DeepMind cuối thập niên 2010) học "tri thức" đánh giá thế cờ mà không cần con người truyền lại. Điều thú vị là cách các hệ thống này hoạt động lại xác nhận đúng mô hình của hai tác giả: tìm kiếm trên cây đến một độ sâu nhất định, kết hợp với một hàm đánh giá thế trung gian. Khác biệt là phần "nghệ thuật" nay cũng được máy học ra. Cờ vua vẫn chưa được giải trọn vẹn; một số trò nhỏ hơn như cờ đam kiểu Mỹ (checkers) đã được chứng minh là hoà khi hai bên chơi đúng, ngay khoảng thời gian sách ra đời (2007).

### Quan điểm trái chiều: suy luận ngược có thể thất bại ngay cả với người tính giỏi

Một số nhà lý thuyết trò chơi chỉ ra những trò chơi mà suy luận ngược dẫn tới kết quả nghe vô lý, như trò chơi con rết (centipede game): hai người lần lượt chọn lấy phần hiện tại hoặc chuyền cho người kia để tổng tăng lên; suy luận ngược nói người đầu tiên nên lấy ngay, nhưng người thật thường chuyền vài lượt và cả hai được nhiều hơn. Lập luận ở đây là nếu đối thủ đã đi một nước "phi lý" thì giả định họ sẽ duy lý ở các nước sau cũng đáng ngờ. Hai tác giả có chạm tới ý này khi nói người chơi phải dự đoán đối thủ thật sẽ làm gì, nhưng chương không bàn trường hợp mà suy luận ngược hoàn hảo lại cho lời khuyên tồi.

### Vận dụng: trước mỗi bước đi trong một chuỗi tương tác, hãy vẽ cây và hỏi người kia sẽ đáp lại thế nào

- **Trong doanh nghiệp.** Trước khi giảm giá, mở rộng công suất hay vào thị trường mới, hãy vẽ phản ứng có thể của đối thủ ở từng nhánh và kết quả cuối cùng cho cả hai bên. Khi hợp tác với đối tác ở nơi pháp luật thi hành hợp đồng yếu, hãy nhớ trò chơi Charlie – Fredo: lời hứa chỉ có giá trị nếu đối tác vẫn có lợi khi giữ lời (vì còn quan hệ lâu dài, còn tài sản hay danh tiếng bị ràng buộc). Khi diễn tập kịch bản chiến lược, thuê người ngoài đóng vai đối thủ.
- **Trong đầu tư.** Một cơ hội "lợi nhuận gấp đôi trong một năm" cần được phân tích bằng câu hỏi: khi đã cầm tiền, bên kia có lợi gì để trả lại? Nếu câu trả lời chỉ là "vì họ đã hứa", đó là cây của Charlie và Lucy. Bài học Orange Bowl cũng áp dụng: nếu muốn thử một khoản đầu tư mạo hiểm, nên thử sớm, khi danh mục còn đủ thời gian và nguồn lực để phục hồi nếu thất bại.
- **Trong nghề nghiệp.** Khi đàm phán lương hay đề nghị chia lợi ích, nhớ thí nghiệm tối hậu thư: một đề nghị bị coi là bất công có thể bị từ chối dù từ chối làm người kia thiệt. Khi chọn hướng đi sự nghiệp, chấp nhận rủi ro (đổi ngành, khởi nghiệp, học thêm) sớm thường tốt hơn để muộn, vì còn thời gian làm lại.
- **Khi đọc tin chính sách.** Khi một cơ quan được trao thêm quyền (phê duyệt, cấp phép, phủ quyết), hãy hỏi các bên khác sẽ thay đổi hành vi thế nào để thích nghi với quyền đó, như Quốc hội đổi cách soạn dự luật trước quyền phủ quyết từng khoản. Ở Việt Nam, những tranh luận về phân cấp, phân quyền giữa trung ương và địa phương, hay về thủ tục phê duyệt dự án, có thể được nhìn qua lăng kính này: thêm một tầng phê duyệt không chỉ thêm một lần kiểm soát mà còn làm các bên đổi cách đề xuất ngay từ đầu.

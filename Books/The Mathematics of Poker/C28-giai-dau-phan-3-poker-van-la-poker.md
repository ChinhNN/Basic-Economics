# Chương 28 — Poker vẫn là poker: Giải đấu, phần III (Poker's Still Poker: Tournaments, Part III)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 28 "Poker's Still Poker: Tournaments, Part III", trang 361–371.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương 26 ([C26-giai-dau-phan-1-nhan-doi.md](C26-giai-dau-phan-1-nhan-doi.md)) xây Lý thuyết Nhân đôi (Theory of Doubling Up), E = C^N, để định giá chip theo kỹ năng ở đầu và giữa giải, và định nghĩa cỡ giải hiệu dụng (effective tournament size). Chương 27 ([C27-giai-dau-phan-2-chip-khong-phai-tien.md](C27-giai-dau-phan-2-chip-khong-phai-tien.md)) đưa ra các công thức chuyển chip thành equity giải thưởng ở cuối giải (Malmuth-Harville, Malmuth-Weitzman…) và bội số phương sai giải đấu k = n·Σv_i² − 1. Chương 28 là chương "ứng dụng" của ba chương giải đấu: nó dùng hai công cụ trên cho từng thể thức giải cụ thể (bubble, sit-and-go, supersatellite, rebuy, chơi với chồng chip ngắn, ante) và cho việc đánh giá thỏa thuận tài trợ giải đấu, nối lại với phần thỏa thuận tài trợ cash game ở Chương 25 ([C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md)). Ý tưởng "người vào pot all-in trước có lợi" dựa trên lời giải jam-or-fold của Chương 12 ([C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md)) và khái niệm cân bằng trong trò chơi không tổng hằng của Chương 10 ([C10-ly-thuyet-tro-choi.md](C10-ly-thuyet-tro-choi.md)). Chương 29 ([C29-tro-choi-nhieu-nguoi.md](C29-tro-choi-nhieu-nguoi.md)) tiếp tục chủ đề "có hơn hai người chơi thì lý thuyết trò chơi khác đi" một cách tổng quát, với các liên minh ngầm.
**Ý chính:** **Trong giải đấu có nhiều hạng trả thưởng, một ván đối đầu giữa hai người không còn là trò chơi tổng hằng: khi hai người all-in với nhau, cả hai cùng mất equity và những người ngồi ngoài được lợi; vì vậy người đầu tiên đẩy hết chip vào pot có lợi thế kiểu "trò chơi gà" (game of chicken), và mỗi thể thức giải đòi hỏi những điều chỉnh riêng — nhưng ở phần lớn các giải nhiều bàn, poker vẫn là poker: gom chip vẫn gần như đồng nghĩa với gom tiền.** Mục đầu cho thấy ngay ở cash game, người call sau một cú jam phải có bài chặt hơn người jam (AJo chỉ có 42,8% equity, theo sách, trước dải bài {55+, A9+, KJ+}); ở giải đấu, cái giá của cuộc đối đầu làm hiệu ứng này mạnh hơn. Ví dụ 28.1 (trò chơi gà) có ba điểm cân bằng: hai cân bằng thuần (một người lao thẳng, người kia tránh) và một cân bằng hỗn hợp; trong poker, người hành động trước "tuyên bố lao thẳng" bằng cách jam. Mục bubble: ở giải nhiều bàn, nhiều người chơi quá chặt gần vùng có thưởng nên nên raise blind của họ; nhưng ở sit-and-go thưởng 5-3-2, bước nhảy từ 0 (hạng 4) lên 2 (hạng 3) lớn tới mức người ở big blind cần khoảng 61% equity để call all-in thay vì 42% nếu chỉ tính chip (Ví dụ 28.2). Mẹo tại bàn: quy giá trị lên thêm một hạng ra chip (ví dụ 120 đô la thành 1.200 chip) và cộng vào khoản thua khi bị call và thua. Shootout và satellite một bàn không có bước nhảy vào vùng tiền, nên chỉ cần thắng bàn; match play thì người có nhiều chip hơn nên coi như hai bên có cùng số chip bằng chồng nhỏ hơn. Sit-and-go có ba tình huống bubble điển hình (một chồng lớn; bốn chồng bằng nhau; "kẻ bắt nạt và người bị bắt nạt"), trong đó người call cần khoảng 62,5% và 65,8% equity. Supersatellite (mọi suất thưởng bằng nhau) làm chip vượt ngưỡng an toàn gần như vô giá trị: người có AA vẫn nên bỏ bài trước cú all-in của chồng lớn còn lại. Giải nhiều bàn thì gần với cash game. Ở giải rebuy, người thắng đủ để tham gia nên rebuy ngay khi thua sạch đầu giải; với C = 0,54, add-on 1.500 chip giá 100 đô la đáng giá khoảng 209 đô la ở chồng 6.000, và luôn đáng mua tới tận nửa tổng chip. Khi chồng chip ngắn: nếu chồng nhỏ hơn sáu lần pot trước flop thì nên jam thay vì raise nhỏ; ưu tiên bài có equity showdown cao và bài có lá chặn (blocker). Ante tạo phần thưởng phụ (overlay) cho chồng rất ngắn ở stud và làm raise mọi bài có lời trước đối thủ quá chặt ở no-limit hold'em. Cuối cùng, một thỏa thuận tài trợ 70 giải cho người chơi thắng 1 buyin mỗi giải chỉ mang lại cho người tài trợ khoảng 30,13 buyin thay vì 35, và nếu cho phép thanh toán mỗi khi người chơi đang lời thì chỉ còn khoảng 27 buyin, vì kết quả giải đấu lệch rất mạnh.

> **Lưu ý:**
> - **"Khoảng 7% số bài" phải là khoảng 9,8% (trang 364):** dải bài {66+, A9s+, AT+, KJs+} gồm 9 đôi × 6 = 54 tổ hợp, A9s–AKs 5 × 4 = 20, ATo–AKo 4 × 12 = 48, KJs–KQs 2 × 4 = 8, tổng 130 trên 1.326 tổ hợp, tức 9,8%. Dải {77+, AJs+} ở trang 364–365 có 8 × 6 + 3 × 4 = 60 tổ hợp, tức 4,5%, khớp với "khoảng 5%" của sách.
> - **AJs có lẽ không đạt ngưỡng 65,8% (nhận xét của người tổng hợp, tính bằng mô phỏng Monte Carlo 300.000 lần mỗi tay bài, sai số chuẩn khoảng 0,1 điểm phần trăm):** equity trước một tay bài ngẫu nhiên: 77 là 66,2%, AKs 67,0%, AQs 66,2%, AJs 65,5%, AKo 65,4%, 66 là 63,2%. Vậy với ngưỡng 65,8%, dải call đúng là {77+, AQs+} (56 tổ hợp, 4,2%), không phải {77+, AJs+}. Kết luận của sách không đổi: chỉ khoảng 4–5% số bài call được, kể cả AKo cũng bỏ. Với ngưỡng 62,5%, mô phỏng xác nhận đúng dải của sách: ATo 62,7%, A9s 62,9%, KJs 62,6% vừa vượt ngưỡng; A9o 60,7%, KQo 61,5%, KTs 61,7% thì không.
> - **AJo trước dải {55+, A9+, KJ+} có khoảng 48%, không phải 42,8% (nhận xét của người tổng hợp, Monte Carlo 600.000 lần, có tính việc AJo chặn bớt tổ hợp của dải):** chia theo nhóm, AJo có khoảng 45% trước 55–TT (36 tổ hợp), 25% trước JJ–AA (18), 72% trước A9–AT (24), 49% trước AJ (9), 26% trước AQ–AK (24), 65% trước KJ–KQ (28); trung bình theo trọng số là 48,1%. Ý của sách (AJo vẫn yếu hơn dải của người jam dù nằm trên ngưỡng jam) vẫn đúng, nhưng mức chênh nhỏ hơn sách nói.
> - **"Equity của chồng lớn" phải là equity của big blind (trang 364):** trong tình huống Một chồng lớn (5.500/1.500/1.500/1.500), các xác suất "khi call và thắng", "khi bỏ bài" là của người ở big blind có 1.500 chip đang cân nhắc call cú jam của chồng lớn, không phải của chồng lớn. Câu tiếp theo "he needs 2/3.2" xác nhận điều này.
> - **Tham chiếu "Phương trình 27.4" phải là Phương trình 27.5 (trang 369):** bội số phương sai giải đấu là k = n·Σv_i² − 1, được đánh số 27.5 ở Chương 27; phương trình 27.4 là nghiệm của mô hình Malmuth-Weitzman.
> - **Các phép tính được kiểm tra và khớp:** Ví dụ 28.2: 0,5 × 5 + 0,5 × 2,5 = 3,75; 0,21 × 5 + 0,5 × 2,5 = 2,30; 2,3/3,75 = 61,33%; 2.100/5.000 = 42%. Mẹo bubble: 25% × 65% = 16,25%, nhân 1.200 chip được 195 chip (sách làm tròn 200). Một chồng lớn: 3,2 và 2,0 buyin, 2/3,2 = 62,5%. Bốn chồng bằng nhau: 3,8 và 2,5 buyin, 2,5/3,8 = 65,79%. Rebuy: N(6.000) = 7,381, N(7.500) = 7,059, E(6.000) = 953,0 đô la, E(7.500) = 1.162,1 đô la, chênh 209 đô la; với C = 0,51 và giá 150 đô la, điểm hòa vốn là 8.325 chip, đúng như sách. Ante: 200 + 400 + 9 × 50 = 1.050. Bảng tài trợ: mọi xác suất nhị thức, kết quả, phần của người tài trợ và tổng 30,13 đều khớp (tính chính xác 30,127); 35 − 30,13 = 4,87, sách làm tròn 4,9. AA trước JJ: mô phỏng cho 81,1%, khớp "81%".
> - **Xác suất về các hạng trong Ví dụ 28.2 và các tình huống sit-and-go là ước lượng thô của sách.** Người tổng hợp so với mô hình Malmuth-Harville của Chương 27 (thưởng 5-3-2): Ví dụ 28.2, khi call và thắng (5.000 chip trước hai chồng 2.500) equity là 3,83 buyin; khi bỏ bài (2.100 chip, các chồng 2.900/2.500/2.500) là 2,23 buyin; equity cần là 2,23/3,83 = 58,2%, thấp hơn 61,33% của sách nhưng vẫn cao xa 42%. Tình huống Một chồng lớn: 3,01 và 1,83 buyin, cần 60,9% (sách: 62,5%). Kết luận định tính không đổi.
> - **Lỗi in và lỗi lớp chữ:** "despite the face" (fact, trang 361); "2,500 m chips" (in chips, trang 362); "playing a hard" (hand, trang 363); "then-decision" (their decision, trang 367); "log²" in thay cho log₂ ở hai dòng N(no add-on), N(add-on) (trang 367); câu "indifferent to taking the rebuy" thực ra nói về add-on (trang 367); "Tile backer's share" (The, trang 370); "seeded at the end of 70 tournaments" (settled, trang 370); "One specific recommendation ... is six that if" có chữ "six" thừa (trang 371).
> - **Quy ước:** "buyin" là một đơn vị phí tham gia; equity giải thưởng (prize equity) tính bằng buyin hoặc đô la; "chip EV" là kỳ vọng tính bằng chip. Người chơi A và B trong Ví dụ 28.1 giữ đúng tên của sách (không phải X và Y). "Lý thuyết Nhân đôi" và "bội số phương sai giải đấu" theo cách gọi ở bản tổng hợp Chương 26–27.

## Sơ đồ

### Mục "Game Theoretic Tournament Concepts" — vì sao ván bài đối đầu trong giải đấu không phải tổng hằng (trang 361)

```text
       Ở giải đấu, mỗi người chơi đều có phần lợi ích trong MỌI ván bài,
       vì ai cũng được thêm equity khi người khác bị loại
                                │
                                ▼
       Hệ quả: ván đối đầu hai người KHÔNG còn là trò chơi tổng hằng
       · khi hai người all-in với nhau, cả hai cùng mất một phần equity
       · phần mất rất nhỏ ở ván đầu giải, rất lớn ở bubble của
         supersatellite
                                │
                                ▼
       Người đầu tiên vào pot có lợi, nhất là người đầu tiên vào pot
       bằng TOÀN BỘ chip; ở no-limit hold'em blind tăng dần nên tình
       huống này xảy ra thường xuyên
                                │
                                ▼
       Ngay ở cash game, người call sau cú jam cần dải bài chặt hơn
       người jam: AJo chỉ có 42,8% equity (theo sách) trước dải
       {55+, A9+, KJ+} dù AJo nằm trên ngưỡng jam
       · ở giải đấu, người call còn phải bù thêm equity mất đi do đối
         đầu; nếu chính họ cũng phải call all-in thì cái giá này lớn
```

### Ví dụ 28.1 — Trò chơi gà (Example 28.1 Game of Chicken, trang 361–362)

```text
       Hai người lái xe lao vào nhau; mỗi người chọn lao thẳng hoặc tránh
       Bảng thưởng (A, B):
                          B lao thẳng     B tránh
         A lao thẳng      (−10, −10)      (1, −1)
         A tránh          (−1, 1)         (0, 0)
                                │
                                ▼
       Không phải tổng bằng không, nên không có một lời giải tối ưu duy
       nhất; có BA điểm cân bằng:
       · hỗn hợp: mỗi người lao thẳng với xác suất 1/10 (người tổng hợp
         tính), mỗi người được −0,1
       · thuần 1: A lao thẳng, B tránh (B chỉ có thể làm cả hai thiệt)
       · thuần 2: B lao thẳng, A tránh
                                │
                                ▼
       Poker là trò chơi hành động LẦN LƯỢT: khi mọi người bỏ bài tới
       blind và chồng chip ở mức jam, người hành động trước "tuyên bố
       lao thẳng" (jam), phản ứng tốt nhất của người sau là "tránh" (fold)
       · trong poker cái giá đối đầu không gấp 10 lần mất blind, và đôi
         khi bài người sau mạnh tới mức bỏ qua được cái giá này
       · hàm ý: người đi trước nên cố tạo cân bằng jam-fold có lợi cho
         mình, nghĩa là jam hơi rộng hơn dải jam-or-fold thông thường
```

### Mục "Play On the Bubble" và Ví dụ 28.2 — chơi ở bubble (trang 362–363)

```text
       Ở giải nhiều bàn lớn, nhiều người coi "vào được vùng có thưởng"
       quá nặng về tâm lý, nên chơi rất chặt ở bubble hoặc ở mỗi bước
       nhảy thưởng (ví dụ từ ba bàn xuống hai bàn)
       · khai thác: raise blind của họ thật nhiều để gom chip nhanh
       · hệ quả: kết quả của tác giả có nhiều lần "bị loại ngay sát vùng
         có thưởng" và nhiều lần về hạng cao
                                │
                                ▼
       Nhưng có nhiều trường hợp chơi chặt là ĐÚNG: supersatellite, và
       khi bước nhảy vào vùng có thưởng lớn — ví dụ sit-and-go 10 người,
       thưởng 5-3-2 (hạng 4 được 0, hạng 3 được 2)
                                │
                                ▼
       Ví dụ 28.2: còn 4 người, mỗi người 2.500 chip, blind 200-400;
       small blind jam, big blind cân nhắc call
       · call và thắng (5.000 chip): 50% × 5 + 50% × 2,5 = 3,75 buyin
       · call và thua: 0
       · bỏ bài (còn 2.100 chip): 21% × 5 + 29% × 0 + 50% × 2,5 = 2,3
       · cần equity X với 3,75X > 2,3, tức X > 61,33%
       · nếu chỉ tính chip: 5.000X − 2.100 = 0, X = 42%
       · vậy ở bubble phải chơi chặt hơn nhiều
                                │
                                ▼
       Mẹo tại bàn: quy giá trị lên thêm một hạng ra chip, cộng vào khoản
       thua khi bị call và bị loại
       · giải 500 người, 100 + 9 đô la, 500.000 chip; hạng 50 được 120
         đô la, tức khoảng 1.200 chip
       · bị call (25%) rồi thua (65%): 16% × 1.200 ≈ 200 chip — nhỏ
       · nếu chỉ 10 hạng có thưởng, hạng 10 được 1.200 đô la: khoản phạt
         lớn hơn nhiều, phải chơi chặt hơn
```

### Mục "Shootouts and Single-Table Satellites" và "Match Play" — thể thức không có bước nhảy vào vùng tiền (trang 363)

```text
       SHOOTOUT và SATELLITE MỘT BÀN: một bàn chơi tới khi một người có
       hết chip; người thắng lấy hết hoặc vào vòng sau
       · không có bước nhảy vào vùng có thưởng, nên chỉ giữ chip để còn
         cơ hội dùng kỹ năng
       · giải nhì (nếu có) thường nhỏ, ít ảnh hưởng chiến lược
       · lợi thế cho người giỏi: chơi ít người thường xuyên, nhiều cơ
         hội jam-or-fold
       · khi còn 2–3 người hay chia tiền; nguyên tắc: tỷ lệ chip xấp xỉ
         tỷ lệ quỹ thưởng đáng được hưởng nếu ngang tài
                                │
                                ▼
       MATCH PLAY: giải là chuỗi các trận đối đầu hai người
       · giữ chip ít giá trị; mục tiêu chỉ là thắng từng trận
       · trận hai người với hai chồng khác nhau tương đương về equity với
         trận mà cả hai có số chip bằng chồng NHỎ hơn: người nhiều chip
         nên bỏ qua phần chip thừa (trừ yếu tố kỹ năng)
       · theo Sklansky: no-limit đối đầu với blind vừa phải thì không ai
         có lợi thế quá lớn; người yếu hơn có thể triệt nhiều lợi thế
         bằng cách all-in trước flop; limit đối đầu cho lợi thế lớn hơn
```

### Mục "Single-Table Sit-and-Go Tournaments" — ba tình huống bubble của sit-and-go (trang 363–365)

```text
       Sit-and-go: một bàn, thường no-limit, thưởng khoảng 50/30/20%
       Ưu điểm cho người giỏi:
       · nhanh (blind tăng mỗi 10 ván hay 10 phút), bù bằng chơi nhiều
         bàn cùng lúc
       · phương sai thấp (30% số người có thưởng): nửa bankroll của
         người giỏi chỉ khoảng 6–7 buyin
       · nhiều phần chơi theo công thức (khi còn hai người: jam-or-fold)
       · bước nhảy từ hạng 4 vào hạng 3 tạo nhiều chỗ dùng kỹ năng
               ┌────────────────┼────────────────┐
               ▼                ▼                ▼
       MỘT CHỒNG LỚN       BỐN CHỒNG BẰNG     KẺ BẮT NẠT VÀ NGƯỜI
       5.500/1.500/        NHAU 2.500 × 4,    BỊ BẮT NẠT
       1.500/1.500,        blind 200-400      6.000/2.500/750/750,
       blind 150-300       · call thắng: 3,8  blind 200-400
       · BB call thắng:    · bỏ bài: 2,5      · chồng lớn jam liên
         3,2 buyin         · cần 65,8%:         tục vào chồng 2.500,
       · BB bỏ bài: 2,0      {77+, AJs+},       chồng này khó call
       · cần 62,5%:          khoảng 5%;       · chồng 2.500 mong một
         {66+, A9s+, AT+,    AKo cũng bỏ        chồng nhỏ bị loại
         KJs+}             · người jam mù     · chồng lớn chơi thụ
       · chồng lớn có thể    vẫn có lời dù      động với chồng nhỏ
         bỏ cả small blind   chỉ 25% equity     để giữ thế này
         để giữ thế này      khi bị call
               └────────────────┼────────────────┘
                                ▼
       Ý then chốt: bước nhảy lớn vào hạng 3 (từ 0 lên 2 buyin) chi phối
       chiến lược sit-and-go; đây là trò chơi gà lần lượt — người đầu
       tiên tuyên bố lao thẳng, người khác chỉ "bắt" được bằng bài mạnh
```

### Mục "Supersatellites" — khi mọi suất thưởng bằng nhau (trang 365–366)

```text
       Supersatellite: quỹ chia thành nhiều suất BẰNG NHAU (thường là vé
       vào giải lớn hơn); N người cuối mỗi người một suất
                                │
                                ▼
       Méo cực mạnh khi gần vùng có thưởng: giải trả 11 suất thì chip vượt
       khoảng 1/4 tổng chip gần như vô giá trị; người chồng lớn thường
       nên bỏ mọi ván bài
                                │
                                ▼
       Chuyện ở supersatellite vào giải chính WSOP: còn 10 người, 8 suất;
       hai chồng lớn ngang nhau có khoảng 75% tổng chip
       · một chồng lớn all-in khoảng 50 lần blind; chồng lớn kia có AA,
         call, gặp JJ và thua
       · tác giả: "Sao người đó còn nhìn bài?"
                                │
                                ▼
       Người cầm AA không cược chip mà cược EQUITY MỘT SUẤT: bỏ mọi ván
       thì gần 100% có suất; thắng ván này chỉ nâng lên "gần 100% hơn",
       thua thì bị loại; 81% thắng pot vẫn không đủ
                                │
                                ▼
       Ánh xạ chip sang equity rất phi tuyến, nhất là gần các ngưỡng; ở
       supersatellite, thiên lệch có lợi cho người all-in trước bị khuếch
       đại: chồng vừa hoặc lớn nên bỏ cả bài khá mạnh trước cú all-in
```

### Mục "Multi-table Tournaments" — giải nhiều bàn gần với cash game (trang 366)

```text
       Giải nhiều bàn: đông người, bàn bị giải tán dần khi có người bị loại
       · chơi bàn đủ người quan trọng hơn ở các thể thức khác
       · nhưng chơi ít người vẫn rất quan trọng: nó xảy ra khi còn hai bàn
         và ở bàn chung kết, nơi ảnh hưởng lớn tới tổng tỷ lệ thắng
                                │
                                ▼
       Cơ cấu thưởng tăng dần đều, không có bước nhảy lớn, nên chơi gần
       như ở cash game; ý cơ bản: poker vẫn là poker, gom equity chip gần
       như đồng nghĩa với gom equity tiền
                                │
                                ▼
       Nhưng: chiến lược cash game cho chồng sâu không hợp khi chồng trung
       bình chỉ 10 blind; đối thủ giải đấu chơi khác đối thủ cash game;
       không được đổi việc gom chip chủ động lấy việc cố sống sót thụ động
```

### Mục "Rebuy Tournaments" — có nên rebuy và add-on không (trang 366–368)

```text
       Giải rebuy: trả X đô la (cộng phí) nhận N chip; được mua thêm N
       chip giá X khi chồng ≤ N, trong ba mức blind đầu; cuối thời gian
       rebuy được một add-on (thường rẻ hơn: ví dụ 1.500 chip giá 100 đô
       la khi chip ban đầu là 1.000)
       Giả định: bỏ qua rủi ro, đủ bankroll, quyết định vào giải là hợp lý
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       TRƯỜNG HỢP 1: thua sạch ở ván     TRƯỜNG HỢP 2: cuối thời gian
       đầu. Rebuy = mua vào một giải     rebuy, có 6.000 chip; 300
       rebuy khác KHÔNG có phí; đã       người, C = 0,54, quỹ khoảng
       đủ lợi thế để trả phí thì càng    90.000 đô la, 1.000.000 chip
       đủ lợi thế để rebuy: NÊN rebuy    · N(6.000) = log₂(10⁶/6.000)
                                           = 7,38; E = 0,54^7,38 ×
                                           90.000 = 953 đô la
                                         · N(7.500) = 7,06; E = 1.162
                                         · thêm 209 đô la, giá 100 đô la:
                                           NÊN mua add-on
                                         · E(x + 1.500) − E(x) > 100 tới
                                           tận nửa tổng chip: luôn mua
               └────────────────┬────────────────┘
                                ▼
       Với C = 0,51: add-on giảm giá vẫn luôn đáng mua; nhưng mua 1.500
       chip với giá gốc (150 đô la) chỉ có lời khi chồng dưới khoảng 8.325
       · kết luận: add-on giảm giá gần như luôn nên mua; rebuy giá gốc
         phải cân nhắc, dùng Lý thuyết Nhân đôi làm thước đo
```

### Mục "Playing with Shortened Stacks" — chơi khi chồng chip ngắn so với blind (trang 368)

```text
       Blind tăng dần nên cuối giải no-limit hold'em chồng trung bình chỉ
       10–15 blind — mức hiếm gặp ở cash game; "chồng ngắn" gồm cả khi MỌI
       chồng đều ngắn so với blind
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       ĐIỀU CHỈNH 1 (no-limit): khi       ĐIỀU CHỈNH 2: chọn bài
       raise nhỏ đã đủ trói mình vào      · ưu tiên bài có equity
       pot (sẽ được ít nhất 2 ăn 1 khi      showdown cao hơn bài có
       call cú re-raise all-in) thì jam     implied odds (ví dụ T9s jam
       luôn                                 được tới blind rất cao)
       · QUY TẮC: chồng ≥ 6 lần pot       · bài có lá chặn (blocker),
         trước flop (gồm blind và ante):    ví dụ Ax: giữ một lá A làm
         raise nhỏ hợp lý; dưới mức đó:     đối thủ ít có bài mạnh để
         jam                                call; mạnh nhất ở vị trí
       · gần với ngưỡng 10 blind của        cuối
         jam-or-fold: 6 × 1,5 = 9
```

### Mục "Playing with Antes" — ảnh hưởng của ante (trang 368–369)

```text
       STUD: chồng chỉ còn 3–4 ante, khi đẩy chip vào thường gặp 1–2 đối
       thủ nhưng được 8 ăn 1 trên phần ante, cộng tỷ lệ 1 ăn 1 trên phần
       còn lại → phần thưởng phụ (overlay) lớn
       · chồng càng ngắn overlay càng lớn: nên sẵn lòng bỏ bài rất tệ
       · so với limit hold'em: chồng 2 blind chỉ có overlay của small blind
       · giải nhiều thể loại: đôi khi bỏ bài biên ở vòng flop để chờ vòng
         stud
                                │
                                ▼
       NO-LIMIT HOLD'EM: ante làm pot lớn hơn mà blind không đổi → raise
       trước hấp dẫn hơn
       · ví dụ khai thác: blind 200-400, ante 50, 9 người: pot 1.050;
         raise lên 1.000, mọi người bỏ 50% số lần → raise mọi bài vẫn
         có lời, và khi bị call đôi khi có bài mạnh
```

### Mục "Tournament Backing Agreements" — đánh giá thỏa thuận tài trợ giải đấu (trang 369–371)

```text
       Thỏa thuận mở thường gặp: người tài trợ cấp bankroll; người chơi
       chơi theo thỏa thuận; chia lợi nhuận (thường 50/50); được rút phần
       lời mỗi khi đang lời
       · bankroll cố định, lời bị rút ra → xác suất mất hết bankroll là
         100% (không có nghĩa thỏa thuận lỗ)
                                │
                                ▼
       Thỏa thuận đóng: người chơi A thắng khoảng 1 buyin mỗi giải, chơi
       70 giải khoảng 400 người, thanh toán một lần ở cuối: B chịu mọi
       khoản lỗ, lời chia đôi
       · thay mỗi giải bằng giải winner-take-all ẢO k = 72 người (bội số
         phương sai giải đấu); xác suất thắng: 72p − 1 = 1 → p = 1/36
       · số lần thắng N ~ nhị thức(70; 1/36); kết quả 72N − 70 buyin
                                │
                                ▼
       Phần của người tài trợ: Σ p(N) × (kết quả nếu âm, hoặc nửa kết quả
       nếu dương) = 30,13 buyin, thay vì 35 → mất khoảng 4,9 buyin
       · mô phỏng 10.000 chuỗi 70 giải: thanh toán cuối kỳ khoảng 32
         buyin; được thanh toán mỗi khi đang lời: khoảng 27 buyin
       · thời hạn càng ngắn, thanh toán càng thường xuyên thì kỳ vọng của
         người tài trợ càng giảm, do kết quả giải đấu lệch mạnh
```

### Phần "Key Concepts" — các ý chính cuối chương (trang 371)

```text
       1. Giải đấu nhiều hạng thưởng không phải trò chơi hai người thuần
          túy: hai người đối đầu thì mọi người khác được lợi; vì vậy "trò
          chơi gà" chi phối, và người đầu tiên all-in thường có lợi hơn
          nhiều so với người thứ hai
       2. Mỗi thể thức giải (sit-and-go, supersatellite, rebuy, …) đòi
          hỏi những điều chỉnh riêng để tối đa equity
       3. Thỏa thuận tài trợ giải đấu đánh giá được bằng công cụ của thỏa
          thuận cash game; kết quả lệch mạnh làm thỏa thuận thường rất có
          lợi cho người chơi, nhất là khi được thanh toán lúc đang lời
       4. No-limit: chồng ≥ 6 lần pot trước flop (gồm blind và ante) thì
          raise nhỏ hợp lý; dưới mức đó thì jam
```

## Ba câu hỏi chương này trả lời

1. **Lý thuyết trò chơi trong giải đấu khác cash game ở đâu?** Ở giải có nhiều hạng thưởng, khi hai người all-in với nhau thì cả hai cùng mất equity và những người ngồi ngoài được lợi, nên ván bài không còn là trò chơi tổng hằng. Cấu trúc giống "trò chơi gà": người hành động trước jam ("lao thẳng") buộc người sau phải bỏ bài trừ khi có bài rất mạnh. Ở sit-and-go thưởng 5-3-2, người ở big blind cần khoảng 61% equity (theo sách) để call all-in thay vì 42% nếu chỉ tính chip; người call một cú jam mù khi bốn người bằng chip cần khoảng 65,8%, nên chỉ khoảng 4–5% số bài call được.
2. **Mỗi thể thức giải đòi hỏi điều chỉnh gì?** Ở bubble giải nhiều bàn: khai thác người chơi quá chặt bằng cách raise blind của họ. Ở sit-and-go: chơi chặt khi call all-in, chồng lớn khai thác chồng vừa. Ở supersatellite: chồng lớn nên bỏ gần như mọi bài, kể cả AA trước cú all-in. Shootout và match play: chỉ cần thắng, giữ chip không có giá trị riêng. Giải rebuy: rebuy ngay khi thua sạch đầu giải, add-on giảm giá gần như luôn đáng mua (209 đô la equity cho 100 đô la). Chồng ngắn: jam khi chồng dưới sáu lần pot trước flop. Ante: raise rộng hơn ở no-limit, sẵn lòng bỏ bài tệ hơn ở stud khi chồng rất ngắn.
3. **Một thỏa thuận tài trợ giải đấu chia đôi lợi nhuận có công bằng với người tài trợ không?** Không như vẻ ngoài. Vì kết quả giải đấu lệch rất mạnh, nhiều chuỗi 70 giải kết thúc lỗ (người tài trợ chịu hết), còn chuỗi lời thì bị chia đôi. Với người chơi thắng 1 buyin mỗi giải, tổng lời kỳ vọng 70 buyin nhưng người tài trợ chỉ được khoảng 30,13 buyin (mô hình nhị thức) hoặc 32 buyin (mô phỏng), không phải 35; nếu người chơi được thanh toán mỗi khi đang lời thì chỉ còn khoảng 27 buyin.

## Khái niệm cần biết

- **Trò chơi không tổng hằng trong giải đấu (non-constant-sum):** trò chơi trong đó tổng thưởng của hai người đối đầu thay đổi theo kết quả. Ví dụ: bốn người mỗi người 2.500 chip, thưởng 5-3-2 (tổng 10 buyin), mỗi người có 2,5 buyin equity; nếu hai người all-in, tổng equity của hai người này sau ván (khoảng 3,8 + 0 theo sách) nhỏ hơn 2,5 + 2,5 = 5. Quan trọng vì đây là lý do mọi điều chỉnh của chương.
- **Trò chơi gà (game of chicken):** trò chơi hai người, mỗi người chọn "lao thẳng" hoặc "tránh"; nếu cả hai lao thẳng thì cả hai thiệt nặng (−10, −10), nếu một người tránh thì người đó mất chút thể diện (−1) còn người kia được 1. Có ba cân bằng: hai cân bằng thuần và một cân bằng hỗn hợp (mỗi người lao thẳng với xác suất 1/10). Quan trọng vì khi hành động lần lượt, người đi trước chọn được cân bằng có lợi cho mình — jam trước.
- **Cân bằng (equilibrium):** cặp chiến lược mà không người nào tự đổi chiến lược của mình mà có lợi hơn. Ví dụ: (A lao thẳng, B tránh) là cân bằng, vì nếu B đổi sang lao thẳng thì B được −10 thay vì −1. Quan trọng vì trò chơi không tổng bằng không có thể có nhiều cân bằng với kết quả khác nhau.
- **Bubble:** giai đoạn ngay trước khi vào vùng có thưởng (người bị loại tiếp theo không được gì, người sau đó có thưởng). Ví dụ: sit-and-go 10 người trả 3 hạng, khi còn 4 người là bubble. Quan trọng vì ở đây giá trị chip lệch nhiều nhất khỏi tỷ lệ chip.
- **Equity giải thưởng (prize equity) và chip EV:** equity giải thưởng là phần quỹ thưởng kỳ vọng tính bằng tiền hoặc buyin; chip EV là kỳ vọng tính bằng chip. Ví dụ: trong Ví dụ 28.2, call cần 42% equity theo chip EV nhưng 61,33% theo equity giải thưởng. Quan trọng vì trong giải đấu, quyết định đúng là quyết định tối đa equity giải thưởng.
- **Sit-and-go:** giải một bàn, bắt đầu khi đủ người (thường 10), thưởng khoảng 50/30/20%. Ví dụ: thưởng 5-3-2 buyin. Quan trọng vì bước nhảy từ hạng 4 (0) lên hạng 3 (2 buyin) chi phối chiến lược bubble.
- **Supersatellite:** giải mà quỹ thưởng được chia thành nhiều suất bằng nhau, thường là vé vào giải lớn hơn. Ví dụ: 10 người còn lại, 8 suất. Quan trọng vì chip vượt mức đủ để giữ suất gần như vô giá trị, nên chồng lớn nên bỏ mọi bài.
- **Shootout, satellite một bàn, match play:** các thể thức chỉ người thắng bàn (hoặc thắng trận đối đầu) đi tiếp hay lấy thưởng. Ví dụ: match play là chuỗi trận hai người. Quan trọng vì không có bước nhảy vào vùng tiền nên giữ chip không có giá trị riêng.
- **Rebuy và add-on:** rebuy là mua thêm chip với giá gốc khi chồng chip không vượt số chip ban đầu, trong thời gian quy định; add-on là lần mua thêm cuối cùng, không điều kiện, thường được giảm giá. Ví dụ: add-on 1.500 chip giá 100 đô la khi chip ban đầu 1.000 chip giá 100 đô la. Quan trọng vì Lý thuyết Nhân đôi cho biết giá trị kỹ năng của chip thêm.
- **Lý thuyết Nhân đôi (Theory of Doubling Up, Chương 26):** giả định xác suất nhân đôi chồng chip trước khi bị loại là hằng số C; xác suất thắng giải là E = C^N, với N = log₂(tổng chip / chồng chip) là số lần phải nhân đôi. Ví dụ: chồng 6.000 trên 1.000.000 chip, N = 7,38, C = 0,54, E = 1,06%, nhân quỹ 90.000 đô la được 953 đô la. Quan trọng vì nó định giá rebuy và add-on.
- **Ante và overlay:** ante là khoản cược bắt buộc mọi người phải đặt trước ván; overlay là phần tiền thêm trong pot làm tỷ lệ trả thưởng tốt hơn 1 ăn 1. Ví dụ: chồng stud chỉ còn 3–4 ante được 8 ăn 1 trên phần ante. Quan trọng vì overlay khiến chồng ngắn nên chờ thời điểm có ante.
- **Lá chặn (blocker):** lá bài trên tay làm giảm số tổ hợp bài mạnh mà đối thủ có thể có. Ví dụ: cầm A làm số tổ hợp AA của đối thủ giảm từ 6 xuống 3. Quan trọng vì khi jam với chồng ngắn, điều đáng sợ là bị call bởi bài mạnh.
- **Bội số phương sai giải đấu (tournament variance multiple, Chương 27):** k = n·Σv_i² − 1, với n là số người và v_i là tỷ lệ quỹ trả cho hạng i; xấp xỉ cỡ của một giải winner-take-all có cùng phương sai. Ví dụ: giải 400 người với cơ cấu thưởng thông thường có k ≈ 72. Quan trọng vì nó cho phép thay giải thật bằng giải ảo winner-take-all để tính bằng phân phối nhị thức.
- **Thỏa thuận tài trợ (backing agreement):** người tài trợ (backer) cấp tiền cho người chơi chơi, chịu khoản lỗ và chia phần lời. Ví dụ: 70 giải, lời chia đôi, người tài trợ chịu hết lỗ. Quan trọng vì sự bất đối xứng (chịu hết lỗ, chỉ hưởng nửa lời) cộng với kết quả lệch mạnh làm người tài trợ nhận ít hơn nửa lợi nhuận kỳ vọng.

## Nội dung chi tiết

### 1. Các khái niệm lý thuyết trò chơi trong giải đấu (Game Theoretic Tournament Concepts, trang 361–362)

#### Ván đối đầu trong giải không phải trò chơi tổng hằng

Từ góc nhìn lý thuyết trò chơi, giải đấu có một tính chất quan trọng ảnh hưởng tới lối chơi, vượt ra ngoài các cân nhắc poker thông thường, kể cả giữa những người chơi ngang tài: **trong giải đấu, mỗi người chơi đều có phần lợi ích trong mọi ván bài, vì ai cũng được thêm equity (phần giá trị kỳ vọng của mình trong quỹ thưởng) khi người khác bị loại.** Vì vậy, các ván bài chơi đối đầu hai người (headsup) không còn là trò chơi tổng hằng (constant-sum) như ở các hình thức poker khác. Khi xảy ra một cuộc đối đầu all-in (đẩy hết chip), cả hai người cùng mất một phần equity. Phần mất này có thể từ không đáng kể (ở ván đầu tiên của giải) tới cực kỳ lớn (ở bubble — giai đoạn ngay trước vùng có thưởng — của một supersatellite). Một hệ quả là người đầu tiên vào pot có lợi thế, đặc biệt là người đầu tiên vào pot bằng toàn bộ chip. Vì blind (khoản cược bắt buộc) của giải đấu tăng dần, những cơ hội như vậy xảy ra khá thường xuyên trong no-limit hold'em (hold'em không giới hạn mức cược).

#### Ngay ở cash game, người call phải chặt hơn người jam

Trong một ván cash game (ván chơi tiền thật, chip đổi ngay ra tiền) đủ người bình thường, những người ngồi sau một người raise all-in phải có bài đủ equity để call trước **dải bài** (distribution) của người raise. Nghĩa là người call nói chung phải có dải bài chặt hơn người raise. Ví dụ, nếu dải bài của người raise là {55+, A9+, KJ+} (mọi đôi từ 55 trở lên, A9 tới AK, KJ và KQ, cả đồng chất lẫn khác chất), thì một người có thể call với AJo (A và J khác chất) chỉ có 42,8% equity (theo sách) trước dải này, dù bài của họ cao hơn hẳn mức tối thiểu của người jam.

Người tổng hợp đếm: dải {55+, A9+, KJ+} có 10 đôi × 6 = 60 tổ hợp, 5 loại A9–AK × 16 = 80, 2 loại KJ–KQ × 16 = 32, tổng 172 tổ hợp. Khi người call cầm A♠ J♥, số tổ hợp còn lại là 139. Mô phỏng Monte Carlo của người tổng hợp cho AJo khoảng 48,1% (bảng dưới), không phải 42,8%; ý của sách vẫn đúng ở chỗ AJo yếu hơn dải của người jam.

| Nhóm bài của người jam | Số tổ hợp còn lại (khi người call cầm AJo) | Equity của AJo (Monte Carlo, ước lượng) |
|---|---:|---:|
| 55–TT | 36 | khoảng 45% |
| JJ–AA | 18 | khoảng 25% |
| A9, AT | 24 | khoảng 72% |
| AJ | 9 | khoảng 49% |
| AQ, AK | 24 | khoảng 26% |
| KJ, KQ | 28 | khoảng 65% |
| Cả dải | 139 | khoảng 48,1% |

Trong giải đấu, hiệu ứng này bị khuếch đại. Những người ngồi sau người jam đầu tiên không chỉ phải vượt qua hiệu ứng "chơi với một dải bài", mà còn phải bù phần equity mất đi do tham gia đối đầu. Nếu phần chip phải bỏ vào chỉ là một phần nhỏ của chồng chip thì hiệu ứng này ít quan trọng; nhưng nếu chính họ cũng phải call all-in thì cái giá có thể đáng kể.

#### Ví dụ 28.1 — Trò chơi gà (Example 28.1 Game of Chicken, trang 361–362)

Có một trò chơi mẫu (toy game) trong lý thuyết trò chơi có điểm tương đồng với tình huống này, gọi là "trò chơi gà". Hai người lái xe tăng tốc lao vào nhau trên một con đường dài. Cả hai đều có thể đánh lái tránh để khỏi đâm nhau. Nếu cả hai tránh, cả hai hòa vốn; nếu cả hai cứ lao thẳng, xảy ra tai nạn khủng khiếp và cả hai mất rất nhiều equity. Còn nếu một người lao thẳng và người kia tránh, người tránh bị gọi là "đồ gà" (kẻ nhát) và mất một chút equity vì mất thể diện.

Bảng thưởng (mỗi ô ghi thưởng của A, thưởng của B):

| Người chơi A \ Người chơi B | B lao thẳng (drive on) | B tránh (swerve) |
|---|---|---|
| A lao thẳng | (−10, −10) | (1, −1) |
| A tránh | (−1, 1) | (0, 0) |

Trò chơi này không phải tổng bằng không (zero-sum), nên không có một lời giải tối ưu duy nhất. Thực tế có **ba điểm cân bằng** (cặp chiến lược mà không người nào tự mình đổi chiến lược mà cải thiện được):

1. **Cân bằng hỗn hợp**, được bàn nhiều nhất trong lý thuyết trò chơi: mỗi người trộn giữa tránh và lao thẳng sao cho đối thủ bàng quan giữa hai lựa chọn. Sách không tính cụ thể; người tổng hợp tính: gọi q là xác suất B lao thẳng. Kỳ vọng của A khi lao thẳng là −10q + 1·(1 − q) = 1 − 11q; khi tránh là −1·q + 0·(1 − q) = −q. A bàng quan khi 1 − 11q = −q, tức q = 1/10. Do đối xứng, A cũng lao thẳng với xác suất 1/10, và mỗi người có kỳ vọng −0,1 — tệ hơn cả kết quả (0, 0) khi cả hai cùng tránh.
2. **A lao thẳng, B tránh** (thưởng (1, −1)): B không thể cải thiện thưởng của mình; đổi sang lao thẳng chỉ gây ra sự hủy diệt cho cả hai (−10 thay vì −1). A cũng không muốn đổi (tránh cho 0 thay vì 1).
3. Tương tự, **B lao thẳng, A tránh** cũng là cân bằng.

#### Áp dụng vào poker: hành động lần lượt

Trong trò chơi con này, poker được chơi **lần lượt**. Vì vậy, khi mọi người bỏ bài (fold) tới hai người ở blind và chồng chip đang ở mức jam, người chơi A (người hành động trước) có thể đơn giản "tuyên bố lao thẳng" (jam), và phản ứng tốt nhất của B là "tránh" (fold). Dĩ nhiên trong poker, cái giá của cuộc đối đầu không lớn gấp mười lần cái giá của việc bỏ blind, và có nhiều tình huống equity của người thứ hai cao đến mức bỏ qua hẳn được khoản phạt thêm này. Nhưng ý tưởng là: trong chừng mực trò chơi gà có hiện diện, người thứ nhất nên cố thiết lập cân bằng jam-fold có lợi cho mình nếu có thể. **Điều này nghĩa là chơi hơi rộng hơn chiến lược jam-or-fold (đẩy hết hoặc bỏ bài) thông thường**, vì khoản phạt equity của cuộc đối đầu làm đối thủ khó khai thác mình hơn.

### 2. Chơi ở bubble (Play On the Bubble, trang 362–363)

#### Khai thác người chơi quá chặt

Bubble của giải đấu, nhất là các giải nhiều bàn lớn, thường là cơ hội tuyệt vời để khai thác lối chơi chặt (tight — chỉ chơi ít bài mạnh). Nhiều người gắn một giá trị tâm lý quá mức vào việc "về đích trong vùng có thưởng", khiến họ chơi cực kỳ chặt đúng lúc sắp bước vào vùng tiền, hoặc khi có một bước nhảy trong cơ cấu thưởng (ví dụ từ ba bàn xuống hai bàn, khi cả bàn thứ ba được trả cùng một mức). Tác giả khai thác hiện tượng này bằng cách raise blind của những người này thật thoải mái và dùng giai đoạn này để gom chip nhanh. Đây là một lý do khiến phân phối kết quả giải đấu của tác giả hơi "nặng đầu": có một lượng lớn bất thường các lần "bị loại ngay sát vùng có thưởng", và một lượng lớn bất thường các lần về hạng cao.

#### Khi chơi chặt là đúng

Tuy nhiên, có khá nhiều tình huống chơi tương đối chặt là đúng — rõ nhất là ở supersatellite, nhưng cũng ở những tình huống bước nhảy vào vùng có thưởng lớn. Một ví dụ quan trọng là cơ cấu giải sit-and-go phổ biến: thường có mười người, và thưởng chia 5-3-2 (đơn vị: buyin — phí tham gia). Bước nhảy lớn từ 0 (hạng 4) lên 2 đơn vị (hạng 3) thực sự làm cho việc chơi chặt hơn đáng kể (nhất là khi call all-in) trở thành đúng, vì phần thưởng khi lọt vào vùng có thưởng quá lớn.

#### Ví dụ 28.2 — Big blind cần bao nhiêu equity để call ở bubble sit-and-go (Example 28.2, trang 362)

Tình huống: còn 4 người, mỗi người có 2.500 chip. Thưởng 5-3-2. Blind 200-400. Người under-the-gun (hành động đầu tiên) và người ở button bỏ bài. Small blind jam 2.500. Big blind cần bao nhiêu equity để call? Có thể xấp xỉ bằng cách xét giá trị tiền mặt của các kết quả. Các giá trị ở đây là xấp xỉ — với blind lớn thường khó ước lượng chính xác khả năng người khác bị loại.

- **Trường hợp 1: call và thắng**, có 5.000 chip (một nửa tổng 10.000 chip). Equity giải thưởng ít nhất là 50% của 5 cộng 50% của một giá trị giữa 2 và 3; lấy 2,5 cho đơn giản. Equity giải thưởng: 0,5 × 5 + 0,5 × 2,5 = 2,5 + 1,25 = **3,75** buyin.
- **Trường hợp 2: call và thua**, được 0.
- **Trường hợp 3: bỏ bài**, còn 2.100 chip (mất 400 big blind) và sắp tới lượt small blind. Equity: 21% của 5 (2.100/10.000 = 21% là xác suất về nhất khi ngang tài) cộng khoảng 29% của 0 cộng 50% của một giá trị giữa 2 và 3: 0,21 × 5 + 0,29 × 0 + 0,5 × 2,5 = 1,05 + 0 + 1,25 = **2,3** buyin.

Để call là đúng, big blind cần equity X trong pot sao cho 3,75X > 2,3, tức X > 2,3/3,75 = **61,33%**.

So với equity cần để call có lời tính theo chip (+chip EV): call 2.100 chip để thắng pot 5.000 chip, nên

5.000X − 2.100 = 0, X = **42%**.

Vậy big blind phải chơi chặt hơn nhiều ở bubble.

Kiểm tra của người tổng hợp bằng mô hình Malmuth-Harville của Chương 27 (xác suất về nhất tỷ lệ với chip; xác suất về các hạng sau tính lần lượt theo cùng cách trên những người còn lại):

| Kết quả | Chồng chip sau ván | Xác suất hạng 1 / 2 / 3 / 4 của big blind | Equity (buyin) | Sách |
|---|---|---|---:|---:|
| Call và thắng | 5.000 trước 2.500 và 2.500 | 50% / 33,3% / 16,7% / 0% | 3,83 | 3,75 |
| Bỏ bài | 2.100 trước 2.900, 2.500, 2.500 | 21% / 22,6% / 25,1% / 31,3% | 2,23 | 2,3 |

Theo mô hình này equity cần là 2,23/3,83 = 58,2%, thấp hơn 61,33% của sách nhưng vẫn cao hơn rất nhiều so với 42%.

#### Mẹo quy giá trị lên hạng ra chip (trang 363)

Điều chỉnh cho bubble ngay tại bàn có thể khó. Một mẹo tác giả hay dùng thay cho việc tính equity là ước lượng giá trị tính bằng chip của việc lên thêm một hạng, rồi đưa giá trị đó vào phép tính equity chip. Ví dụ, giả sử đang ở bubble của một giải 500 người, phí 100 + 9 đô la (100 đô la vào quỹ, 9 đô la phí cho nhà tổ chức), có 500.000 chip trong giải (tức 1.000 chip cho mỗi 100 đô la, hay 10 chip cho 1 đô la). Hạng 50 được 120 đô la. Equity của việc lên thêm một hạng khoảng 1.200 chip. Khi jam, có thể coi khoản phạt thêm khi bị call và bị loại là 1.200 chip (120 đô la đã bỏ lỡ vì jam thay vì bỏ bài). Khoản này thường không đáng kể, vì nó đòi hỏi cùng lúc bị call và thua (chẳng hạn 25% bị call và 65% thua khi bị call, tổng hợp lại 0,25 × 0,65 = 16,25%, tức khoảng 16,25% × 1.200 = 195 chip, sách làm tròn thành 200 chip). Nhưng nếu chỉ 10 hạng có thưởng, chẳng hạn hạng 10 được 1.200 đô la còn hạng 11 không được gì, thì khoản phạt lớn hơn hẳn (người tổng hợp tính với cùng xác suất: 16,25% × 12.000 chip = 1.950 chip) và lối chơi đúng phải chặt hơn.

### 3. Shootout và satellite một bàn (Shootouts and Single-Table Satellites, trang 363)

Tác giả gộp hai thể thức này vì cấu trúc tương tự: một bàn chơi tới khi một người có toàn bộ chip. Người thắng bàn hoặc lấy toàn bộ tiền tham gia, hoặc vào vòng sau có cơ cấu thưởng. Trong cả hai trường hợp, điểm chiến lược then chốt là **không có bước nhảy vào vùng có thưởng**, nên chiến lược giữ chip chỉ nên dùng để duy trì cơ hội áp dụng kỹ năng.

Đôi khi người về nhì được một phần thưởng nào đó, thường chỉ là một phần nhỏ so với giải nhất; vì vậy phần thưởng này thường chỉ ảnh hưởng nhỏ tới chiến lược. Thông thường mọi nỗ lực nên dồn vào việc thắng hẳn bàn.

Một lợi ích của các thể thức này là người chơi giỏi có cơ hội chơi ít người (shorthanded) thường xuyên hơn nhiều. Điều này thường có lợi, vì nhiều đối thủ không có nhiều kinh nghiệm chơi ít người. Ngoài ra, khi đối đầu hai người hoặc ít người, cơ hội dùng chiến lược jam-or-fold xuất hiện thường xuyên hơn nhiều. Ở satellite một bàn, người chơi thường thỏa thuận chia tiền khi còn hai hoặc ba người. Thông thường, ý quan trọng là: **tỷ lệ chip một người nắm giữ xấp xỉ bằng tỷ lệ quỹ thưởng người đó đáng được hưởng, nếu kỹ năng ngang nhau.**

### 4. Thể thức đấu loại trực tiếp (Match Play, trang 363)

Một thể thức ngày càng phổ biến trên mạng là "match play", trong đó giải được tổ chức thành một chuỗi các trận đối đầu hai người. Rõ ràng mục tiêu giữ chip ít có giá trị ở đây; mục tiêu chỉ là thắng từng trận.

Một khái niệm có ích khi chơi các trận hai người: (ngoại trừ các điều chỉnh nhỏ về kỹ năng) **chơi một ván trong trận hai người mà một bên có chồng chip lớn hơn thì tương đương về equity với chơi ván đó khi cả hai có chồng chip bằng chồng nhỏ hơn.** Lý do (người tổng hợp giải thích): trong một ván, không ai mất hoặc thắng được nhiều hơn chồng nhỏ hơn; phần chip thừa của người lớn hơn không bao giờ bị đặt cược. Hệ quả là người có chồng lớn hơn nên đơn giản bỏ qua phần chip thừa (trừ các cân nhắc về kỹ năng).

Một điều nữa đáng nhắc (David Sklansky đã chỉ ra trong cuốn sách của ông về chơi giải đấu): trong một trận no-limit hai người với blind dù chỉ vừa phải, không người nào có thể có lợi thế quá lớn. Thực tế, người yếu hơn có thể triệt tiêu phần lớn lợi thế của đối thủ bằng cách all-in trước flop. Các trận limit (giới hạn mức cược) hai người thường cho lợi thế lớn hơn.

### 5. Giải sit-and-go một bàn (Single-Table Sit-and-Go Tournaments, trang 363–365)

#### Đặc điểm của thể thức

Một thể thức được phổ biến trên mạng, nay cũng thường thấy ở sòng bài thật, là giải "sit-and-go" một bàn. Thường là no-limit (có các thể loại khác nhưng ít phổ biến hơn), có một bàn, và cơ cấu thưởng kiểu 50% cho hạng nhất, 30% hạng nhì, 20% hạng ba.

Sit-and-go có nhiều điểm tốt cho người chơi giỏi:

1. **Giải diễn ra nhanh** (thường mức cược tăng mỗi mười ván hoặc mười phút). Bình thường blind tăng nhanh ít có lợi cho người giỏi, nhưng ở đây nhiều người bù lại bằng cách chơi nhiều giải cùng lúc.
2. **Phương sai khá thấp** so với phần lớn các thể thức giải khác, vì 30% số người có thưởng. Nửa bankroll (half-bankroll — số vốn có 50% nguy cơ mất hết, theo Chương 22) của một người chơi giỏi, kể cả ở mức buyin cao, chỉ khoảng 6–7 buyin.
3. **Nhiều phần của giải có thể chơi gần như theo công thức** chỉ với chút chuẩn bị. Ví dụ, khi giải còn hai người, blind gần như luôn đủ cao để chơi jam-or-fold.

Ngoài ra, có nhiều chỗ để áp dụng kỹ năng vì sự méo do cơ cấu thưởng. Khi giải còn bốn người, với một chồng nhỏ, khác biệt giữa bị loại ở hạng tư và sống sót vào vùng có thưởng là rất lớn. Vì vậy chơi ở bubble sit-and-go khá thú vị: blind cao gây áp lực lên chồng nhỏ, trong khi chồng lớn cướp blind (steal) của họ. Nhiều động thái khác nhau có thể hình thành, mỗi cái đòi hỏi điều chỉnh khác. Tác giả nêu ba tình huống, mỗi tình huống cho chồng chip của bốn người còn lại (thưởng 5-3-2, tổng 10.000 chip).

#### Tình huống 1: Một chồng lớn (One Big Stack: 5.500/1.500/1.500/1.500, blind 150-300)

Chồng lớn có lợi thế rất lớn chừng nào tỷ lệ chồng chip này còn được giữ và giải vẫn còn bốn người. Ví dụ, nếu chồng lớn đơn giản jam mọi ván, những người khác sẽ gặp bài toán khó, vì họ cần bài khá mạnh mới đáng call all-in. Chẳng hạn, nếu chồng lớn jam và người ở big blind (1.500 chip) là người duy nhất có thể call, có thể xấp xỉ equity của người big blind này (sách viết nhầm "của chồng lớn", xem khối Lưu ý):

- Call và thua: 0.
- Call và thắng: (30%)(5) + (40%)(3) + (25%)(2) + (5%)(0) = 1,5 + 1,2 + 0,5 + 0 = **3,2** buyin.
- Bỏ bài: (10%)(5) + (30%)(3) + (30%)(2) + (30%)(0) = 0,5 + 0,9 + 0,6 + 0 = **2** buyin.

Vậy người big blind cần 2/3,2 = **62,5%** equity trước một tay bài ngẫu nhiên. Các tay bài đạt mức này là {66+, A9s+, AT+, KJs+}; sách nói "khoảng 7%" số bài, người tổng hợp đếm được 130 tổ hợp trên 1.326, tức 9,8%.

Equity trước tay bài ngẫu nhiên (mô phỏng Monte Carlo của người tổng hợp, 300.000 lần mỗi tay, ước lượng):

| Tay bài | Equity | Tay bài | Equity | Tay bài | Equity |
|---|---:|---|---:|---|---:|
| 55 | 60,5% | AJs | 65,5% | KTs | 61,7% |
| 66 | 63,2% | AJo | 63,8% | KJs | 62,6% |
| 77 | 66,2% | AQs | 66,2% | KJo | 60,6% |
| 88 | 69,1% | AQo | 64,4% | KQs | 63,4% |
| A8s | 62,0% | AKs | 67,0% | KQo | 61,5% |
| A9s | 62,9% | AKo | 65,4% | QJs | 60,1% |
| A9o | 60,7% | ATs | 64,6% | ATo | 62,7% |

So kết quả mô phỏng của người tổng hợp với mô hình Malmuth-Harville (Chương 27): giả sử chồng lớn jam từ button, small blind (1.500) bỏ bài mất 150. Nếu big blind call và thắng: chồng chip 4.000 / 1.350 / 3.150 / 1.500, equity của big blind khoảng 3,01 buyin (xác suất hạng 1 / 2 / 3 / 4 là 31,5% / 31,5% / 24,3% / 12,7%). Nếu bỏ bài: 5.950 / 1.350 / 1.200 / 1.500, equity khoảng 1,83 buyin. Equity cần: 1,83/3,01 = 60,9%, gần với 62,5% của sách.

Lợi thế chồng lớn có được từ tình huống này lớn tới mức chồng lớn thậm chí có thể cân nhắc những nước đi ngược trực giác như bỏ bài ở small blind trước một chồng rất nhỏ ở big blind, để kéo dài tình huống này (giữ cả bốn người).

#### Tình huống 2: Bốn chồng bằng nhau (Four Equal Stacks: 2.500/2.500/2.500/2.500, blind 200-400)

Tình huống tương tự xảy ra ở đây; nó gắn với ý rằng call all-in rất nguy hiểm khi thua sẽ khiến mình bị loại ở hạng tư. Thực ra mọi điều chỉnh ở bubble đều xoay quanh ý này.

Giả sử người under-the-gun jam "mù" (không cần nhìn bài). Khi đó mỗi người còn lại có quyết định giống như trên: call all-in hay bỏ bài.

- Call và thua: 0.
- Call và thắng: (50%)(5) + (30%)(3) + (20%)(2) = 2,5 + 0,9 + 0,4 = **3,8** buyin.
- Bỏ bài: (25%)(5) + (25%)(3) + (25%)(2) + (25%)(0) = 1,25 + 0,75 + 0,5 + 0 = **2,5** buyin.

Equity cần còn cao hơn: 2,5/3,8 = **65,8%**, giới hạn dải call ở {77+, AJs+}. Đây chỉ khoảng 5% số bài (người tổng hợp đếm 60 tổ hợp, 4,5%). Lưu ý rằng ngay cả AKo cũng phải bỏ (AKo có 65,4% trước bài ngẫu nhiên). Theo bảng mô phỏng ở trên, AJs (65,5%) cũng nằm dưới ngưỡng, nên dải đúng là {77+, AQs+} (56 tổ hợp, 4,2%).

Nếu ba người còn lại mỗi người chỉ call 5% số lần (bỏ qua khả năng hai người cùng call), người jam đầu tiên chắc chắn có lời từ việc lấy 600 chip blind khi không bị call, kể cả khi trung bình chỉ có 25% equity khi bị call. Kiểm tra của người tổng hợp: xác suất không ai call là 0,95³ = 0,857. Theo chip: 0,857 × 600 + 0,143 × (0,25 × 5.200 − 2.500) = 514 − 171 = khoảng +343 chip (giả sử người call là big blind, pot 5.200 gồm cả small blind 200). Theo equity giải thưởng (Malmuth-Harville): khi không bị call, người jam có 3.100 chip trước 2.500/2.300/2.100, equity 2,86 buyin; khi bị call, thắng 25% với khoảng 3,9 buyin; kỳ vọng 0,857 × 2,86 + 0,143 × 0,25 × 3,9 = khoảng 2,59 buyin, cao hơn 2,5 buyin lúc đầu.

Vậy trong loại tình huống này, ta thấy kết quả của một trò chơi gà lần lượt: người đầu tiên tuyên bố lao thẳng, và mọi người khác chỉ có thể "bắt" người đó bằng bài rất mạnh.

#### Tình huống 3: Kẻ bắt nạt và người bị bắt nạt (Abuser and Abusee: 6.000/2.500/750/750, blind 200-400)

Đây là tình huống có một chồng lớn và một chồng nhỏ hơn nhưng vẫn lớn hơn đáng kể hai chồng còn lại. Ở đây chồng lớn có thể liên tục jam vào chồng 2.500, và chồng 2.500 bị hạn chế khả năng call (thua thì bị loại ở hạng tư trong khi hai chồng 750 sắp bị blind ăn mòn). Chồng 2.500 rất muốn một trong hai chồng nhỏ bị loại để có thể chơi bình thường với chồng lớn. Vì vậy chồng lớn có thể chơi thụ động với hai chồng rất nhỏ để duy trì tình huống mà mình có thể cướp blind tùy ý.

Đây chỉ là vài tình huống có thể xảy ra gần bubble của sit-and-go, nhưng ý then chốt là: **bước nhảy lớn vào hạng 3 (từ 0 lên 2 buyin) cực kỳ quan trọng trong chiến lược sit-and-go.**

### 6. Supersatellite (Supersatellites, trang 365–366)

Supersatellite là một cơ cấu rất phổ biến khác, đặc biệt như cửa vào các giải buyin lớn cho người chơi có bankroll hạn chế. Đặc điểm phân biệt của supersatellite là quỹ thưởng được chia thành một số suất bằng nhau (đôi khi dư ra chút tiền mặt). Các suất này thường là vé vào một giải lớn hơn. N người cuối cùng đều nhận suất này.

Cơ cấu này tạo ra méo cực mạnh trong chiến lược, nhất là khi gần tới vùng có thưởng. Ví dụ, ở một supersatellite trả mười một suất, mọi chip một người tích lũy vượt quá khoảng một phần tư tổng chip trong giải gần như không có giá trị. Người đã gom được chồng lớn thường nên đơn giản bỏ mọi ván bài, coi như rời bàn.

**Câu chuyện AA.** Tác giả được kể về một supersatellite vào giải chính (main event) của World Series of Poker. "Nhân vật chính" là một trong hai chồng lớn còn lại. Còn mười người, tám người được suất. Hai chồng lớn có tổng khoảng 75% tổng chip, và chip của hai người gần bằng nhau. Một chồng lớn đẩy all-in trước flop khoảng 50 lần blind. Chồng lớn kia nhìn bài và thấy AA.

Đến đây tác giả ngắt lời hỏi: "Sao người chồng lớn thứ hai còn nhìn bài làm gì?" Câu chuyện tiếp: người chồng lớn thứ hai call, gặp JJ và thua. Đây là kết quả khá xui, nhưng **kể cả với lợi thế rất lớn như AA ở đây, call vẫn là sai.**

Lý do: người cầm AA không cược chip; họ cược equity của một suất. Thực tế là khả năng giành suất chỉ bằng cách bỏ mọi ván bài đã gần 100%. Đối đầu với chồng lớn kia chỉ nâng khả năng đó lên một con số gần 100% hơn, nhưng lại chịu rủi ro bị loại khỏi giải. Dù có 81% xác suất thắng pot (người tổng hợp mô phỏng AA trước JJ: 81,1%), phần được khi thắng cực nhỏ so với cái giá khi thua.

Minh họa của người tổng hợp (con số giả định, chỉ để thấy bậc độ lớn): nếu bỏ bài cho xác suất có suất 99%, còn call thì thắng 81% và có suất gần 100%, thua 19% và bị loại, thì call cho khoảng 0,81 × 1 = 81% có suất, thấp hơn 99% tới 18 điểm phần trăm.

Méo này thể hiện suốt giai đoạn cuối giải: ánh xạ từ chip sang equity rõ ràng là phi tuyến, và nguyên lý "chip thêm đáng giá ít hơn" bị phóng đại, đặc biệt khi chồng chip gần một số ngưỡng. Ở các cơ cấu giải thông thường, đã có thiên lệch có lợi cho người đẩy all-in trước. Ở supersatellite, hiệu ứng này bị khuếch đại, và người có chồng vừa hoặc lớn thường có lý khi bỏ bài trước cú all-in của người khác dù có bài khá mạnh, vì cái giá khi thua showdown (lật bài so) quá cao còn phần thưởng khi thắng quá ít do chip thêm bị mất giá.

### 7. Giải nhiều bàn (Multi-table Tournaments, trang 366)

Giải nhiều bàn là cơ cấu phổ biến nhất cho các giải buyin lớn, và cũng là một trong những cơ cấu phổ biến nhất khi buyin nhỏ. Người chơi bắt đầu ở nhiều bàn; khi có ghế trống (do người bị loại), các bàn khác bị giải tán và người chơi từ đó được xếp vào các ghế trống.

Giải nhiều bàn coi trọng kỹ năng chơi bàn đủ người hơn phần lớn các cơ cấu khác. Tuy nhiên chơi ít người vẫn cực kỳ quan trọng, vì các tình huống chơi ít người ảnh hưởng không cân xứng tới tổng tỷ lệ thắng: chúng xảy ra khi còn hai bàn và ở bàn chung kết.

Lối chơi ở giải nhiều bàn trong phần lớn trường hợp khá giống ở ring game (cash game): cơ cấu thưởng của phần lớn giải nhiều bàn tăng khá đều và không có bước nhảy rất lớn vào vùng có thưởng hay giữa các hạng đến mức buộc phải điều chỉnh. Gần hoặc trong vùng có thưởng đôi khi có điều chỉnh, nhưng thường nhỏ hơn nhiều so với một số thể thức đã bàn. **Ý cơ bản là trò chơi vẫn là poker, và trừ những tình huống sát biên nhất, gom equity chip gắn trực tiếp với gom equity tiền trong giải.**

Điều này không có nghĩa một chiến lược ring game cố định, phù hợp khi tiền khá sâu, sẽ hiệu quả khi chồng trung bình chỉ 10 blind. Cũng không đúng, xét về khai thác, nếu chơi chiến lược ring game điển hình khi đối thủ trong giải chơi khác hẳn đối thủ ở ring game. Điều không đổi là: việc gom chip chủ động không nên nhường chỗ cho việc cố sống sót thụ động chỉ vì chip không thể mua lại. Có một số điều chỉnh cụ thể xuất phát trực tiếp từ cơ cấu giải, được bàn ở các mục sau.

### 8. Giải rebuy (Rebuy Tournaments, trang 366–368)

#### Cơ cấu

Giải rebuy và add-on cho phép làm quỹ thưởng lớn hơn mức buyin ban đầu bằng cách cho người chơi mua thêm chip (với một số hạn chế) trong một khoảng thời gian. Cơ cấu thường gặp: buyin X đô la cộng phí (ví dụ 100 + 9 đô la), nhận N chip. Người chơi được "rebuy" (mua lại) khi chồng chip nhỏ hơn hoặc bằng N; vì vậy ngay đầu giải họ có thể mua N chip với giá X đô la. Họ được làm vậy trong ba mức cược đầu tiên. Sau mức thứ ba, thời gian rebuy kết thúc, người chơi được rebuy lần cuối và lấy một "add-on" (mua thêm), không có hạn chế nào ngoài việc mỗi người chỉ được một lần. Chip add-on thường rẻ hơn giá gốc. Ví dụ, nếu mỗi người bắt đầu với 1.000 chip, add-on có thể là 1.500 chip với giá 100 đô la.

Câu hỏi tự nhiên: có nên rebuy không? Tác giả xét vài trường hợp. Trong mọi trường hợp, bỏ qua rủi ro và phương sai, và giả định người chơi có đủ bankroll cho giải và mục tiêu là tối đa equity của phần tiền bỏ vào. Đặc biệt, quyết định vào giải của họ là hợp lý (họ có lợi thế đủ lớn).

#### Trường hợp 1: thua sạch ở ván đầu tiên

Đầu thời gian rebuy, người chơi A mất hết chip ban đầu ở ván đầu tiên. Có nên rebuy? **Gần như chắc chắn có.** A có thể coi đây là cơ hội mua vào một giải rebuy hoàn toàn khác, chỉ khác là giải thứ hai không có phí tham gia. Vì A đã sẵn lòng trả phí cho giải này do tin lợi thế đủ lớn để bù phí, chắc chắn A có đủ lợi thế để mua vào giải thứ hai. Vậy nên rebuy.

#### Trường hợp 2: add-on khi chồng chip đã lớn

Cuối thời gian rebuy, A đã tăng 1.000 chip ban đầu lên 6.000. Có 300 người, và A nghĩ xác suất nhân đôi của mình là C = 54%. Quỹ thưởng dự kiến khoảng 90.000 đô la (200 người sẽ lấy add-on, tổng cộng một triệu chip trong giải). A có thể lấy add-on 100 đô la để được 1.500 chip. Có nên lấy? Chồng chip phải lớn tới đâu thì A mới nên từ chối add-on?

(Kiểm tra của người tổng hợp về tính nhất quán của giả định: 300 buyin ban đầu là 300.000 chip và 30.000 đô la; 200 add-on là 300.000 chip và 20.000 đô la; phần còn lại 400.000 chip ứng với 400 lần rebuy, 40.000 đô la; tổng 1.000.000 chip và 90.000 đô la.)

Equity của A được ước lượng bằng Lý thuyết Nhân đôi: xác suất thắng giải là E = C^N, trong đó N là số lần phải nhân đôi để có toàn bộ chip, N = log₂(tổng chip / chồng chip); equity tiền xấp xỉ E nhân quỹ thưởng.

- N(6.000) = log₂(1.000.000/6.000) = 7,38
- N(7.500) = log₂(1.000.000/7.500) = 7,06
- E(6.000) = 0,54^7,38 = 0,0105; nhân 90.000 được **953 đô la**
- E(7.500) = 0,54^7,06 = 0,0129; nhân 90.000 được **1.162 đô la**

Người tổng hợp tính lại: N(6.000) = 7,3808, N(7.500) = 7,0589, E = 0,010589 và 0,012912, equity 953,0 và 1.162,1 đô la. Vì giá trị equity của chip thêm là 1.162 − 953 = 209 đô la, hơn 200 đô la, trong khi chỉ tốn 100 đô la, **A chắc chắn nên lấy add-on.**

Phần thứ hai: tìm chồng chip x sao cho A bàng quan giữa lấy và không lấy add-on. Ta có:

- N(không add-on) = log₂(1.000.000/x)
- N(có add-on) = log₂(1.000.000/(x + 1.500))
- E(x) = E(x + 1.500) − 100 đô la
- E(x) = 90.000 × 0,54^N(không add-on)
- E(x + 1.500) = 90.000 × 0,54^N(có add-on)

Giải đồng thời các phương trình này, ta thấy **giá trị add-on lớn hơn 100 đô la cho tới tận chồng chip bằng một nửa tổng chip** (cao hơn nhiều so với mức mà Lý thuyết Nhân đôi còn đúng). Điều này cho thấy với mức kỹ năng này, mua chip add-on giảm giá về cơ bản luôn đúng.

Người tổng hợp kiểm tra bằng cách quét x từ 500 tới 500.000 chip: với C = 0,54, chênh lệch E(x + 1.500) − E(x) giảm dần theo x nhưng không bao giờ xuống dưới 129,6 đô la (giá trị ở x = 500.000). Lý do: E(x) = 90.000 × (x/1.000.000)^(log₂(1/0,54)) = 90.000 × (x/10⁶)^0,889, một hàm lõm với số mũ gần 1, nên giá trị biên của chip giảm rất chậm.

Ngay cả với C = 0,51, add-on giảm giá này vẫn đáng mua ở mọi chồng chip (người tổng hợp tính: chênh lệch nhỏ nhất là 133,8 đô la ở x = 500.000). Tuy nhiên, với C = 0,51, điểm hòa vốn khi mua 1.500 chip **với giá gốc** (150 đô la, cùng tỷ giá 1.000 chip = 100 đô la như buyin) là gần **8.325 chip** — người tổng hợp tính lại được đúng 8.325. Với C = 0,54 và giá 150 đô la, điểm hòa vốn khoảng 133.000 chip (người tổng hợp tính thêm).

Điều rút ra: giả sử bạn đủ giỏi để có lý do vào giải, việc lấy add-on khi chip được bán rẻ hầu như luôn đúng. Nhưng rebuy với giá gốc thì phải cân nhắc. Lý thuyết Nhân đôi có thể làm thước đo giá trị chip đã điều chỉnh theo kỹ năng trong trường hợp này.

### 9. Chơi với chồng chip ngắn (Playing with Shortened Stacks, trang 368)

Một đặc điểm phân biệt của giải đấu là nói chung, một số người trong giải sẽ không bị loại cho tới khi cơ cấu giải buộc họ. Vì vậy cơ cấu giải hầu như luôn có blind tăng dần, và do đó chồng chip thường bị thu nhỏ tới mức (so với blind) hiếm gặp ở cash game. Ví dụ, không hiếm khi giai đoạn cuối của một giải no-limit hold'em có chồng trung bình chỉ 10–15 blind; trong khi ring game no-limit hold'em hiếm khi được chơi với chồng trung bình nhỏ như vậy. "Chồng ngắn" ở đây không chỉ là chồng nhỏ so với người khác, mà cả tình huống mọi chồng đều ngắn so với blind vì blind đã tăng tới mức đó.

Có hai loại điều chỉnh lớn.

**Điều chỉnh thứ nhất** chủ yếu ảnh hưởng tới no-limit. Ở tỷ lệ chồng chip trên blind nhỏ, tới một lúc thay vì raise một khoản nhỏ, ta đơn giản all-in. Ngưỡng này thường xuất hiện ở chồng chip mà một cú raise nhỏ hợp lý đã trói ta vào pot, vì ta sẽ được tỷ lệ ít nhất 2 ăn 1 khi call một cú re-raise all-in. **Quy tắc kinh nghiệm: nếu chồng chip của ta từ sáu lần pot trước flop (gồm cả ante và blind) trở lên, nên raise một khoản nhỏ hợp lý; dưới mức đó, nên jam all-in.** Điều này gần với khuyến nghị ở phần jam-or-fold (Chương 12), nơi ngưỡng để chơi jam-or-fold là khoảng mười blind: pot trước flop không có ante là 1,5 big blind (small blind 0,5 cộng big blind 1), nên sáu lần pot là 6 × 1,5 = 9 big blind.

Minh họa của người tổng hợp về lý do "trói vào pot": với chồng 9 big blind, raise lên 2,5 big blind; pot có 1,5 big blind. Nếu một đối thủ không ở blind re-raise all-in (đối thủ có từ 9 big blind trở lên), pot trước khi ta call có 1,5 (blind) + 2,5 (cú raise của ta) + 9 (cú all-in) = 13 big blind, và ta chỉ phải call thêm 9 − 2,5 = 6,5 big blind: tỷ lệ 13 ăn 6,5, tức 2 ăn 1 — mức mà gần như mọi bài đều buộc phải call (cần chưa tới 33% equity). Vậy raise nhỏ không giữ được lựa chọn bỏ bài, nên jam ngay tốt hơn.

**Điều chỉnh thứ hai:** việc chọn bài khi chồng ngắn khác khi chồng lớn. Bài có equity showdown cao được ưu tiên hơn bài có tiềm năng implied odds (tỷ lệ cược ngầm — khoản thắng thêm ở các vòng sau) cao, và bài chứa "lá chặn" (blocker) thường có giá trị vì chúng làm đối thủ ít có khả năng có bài đủ mạnh để call. Hiệu ứng thứ nhất đã thấy ở phần jam-or-fold, nơi những tay như T9s là bài jam tới mức blind rất cao: khi bị call, các tay này có equity cao trước dải bài call. Hiệu ứng thứ hai làm việc raise với các tay như Ax (A cộng một lá bất kỳ) đáng làm hơn, vì cầm một lá A làm giảm một lá A khỏi các tay bài đối thủ có thể có. Ở no-limit, hiệu ứng thứ hai rất mạnh khi raise ở vị trí cuối vì có ít người phía sau có thể call.

### 10. Chơi khi có ante (Playing with Antes, trang 368–369)

Ở stud (thể loại poker chia bài ngửa và úp, không có lá chung), và ở giai đoạn giữa và cuối của nhiều giải no-limit hold'em, có ante (khoản cược bắt buộc của mọi người). Ante ảnh hưởng mạnh tới lối chơi của chồng ngắn vì nó tạo thêm phần thưởng phụ (overlay) cho người có chồng rất ngắn.

Xét một tình huống stud người chơi chỉ còn ba hoặc bốn ante. Khi người này đẩy chip vào, họ thường chỉ gặp một hoặc hai đối thủ nhưng được tỷ lệ 8 ăn 1 trên phần chip ante (tám người khác cũng bỏ ante vào pot), cộng tỷ lệ 1 ăn 1 trên phần chip còn lại. Chồng nhỏ càng "cao" (nhiều chip), overlay này càng kém rõ. Ngược lại, ví dụ ở limit hold'em, một chồng ngắn chỉ còn hai blind thường chỉ gặp người ở big blind khi quyết định đẩy chip, và chỉ có overlay của small blind giúp họ được tốt hơn tỷ lệ 1 ăn 1. **Điều này nghĩa là ở giải stud, người chơi nên sẵn lòng bỏ qua những tay bài rất tệ khi chồng rất nhỏ hơn một chút, vì khi chồng co lại, overlay tiềm năng của họ tăng lên.**

Minh họa của người tổng hợp: bàn 9 người (người này được 8 ăn 1 trên ante của mình), chồng tổng cộng 3 ante, đẩy hết vào và gặp đúng một đối thủ. Pot gồm 9 ante của mọi người cộng 2 ante còn lại của người này và 2 ante đối thủ bỏ thêm, tổng 13 ante; người này bỏ vào 3 ante, nên nếu thắng được lời 10: tỷ lệ 10 ăn 3, khoảng 3,3 ăn 1. Với chồng 10 ante: pot 9 + 9 + 9 = 27 ante, bỏ vào 10, lời 17: tỷ lệ 1,7 ăn 1. Chồng càng ngắn, tỷ lệ trả thưởng càng tốt.

Điều này đôi khi cũng cho phép điều chỉnh ở giải nhiều thể loại (mixed-game): đôi khi đúng là nên bỏ qua bài biên ở các vòng thể loại có flop khi chồng nhỏ, nếu vòng stud sắp tới, để hưởng overlay này.

Ở no-limit hold'em, ante tạo ra pot lớn hơn mà không tăng blind. Điều này làm raise đầu tiên hấp dẫn hơn, vì lấy được blind (và ante) bằng một cú raise nhỏ thường có lời ngay. Xét về khai thác, rất thường gặp trường hợp người chơi chơi quá chặt trong một số tình huống có ante, nhất là khi ante lớn, đến mức raise mọi ván đều có lời. Ví dụ, mức cược 200-400 với ante 50 ở bàn 9 người, và raise lên 1.000 thì dự kiến lấy được blind 50% số lần. Khi đó có thể raise với hai lá bất kỳ, vì khi mọi người bỏ bài ta thắng ngay 200 + 400 + 9 × 50 = 1.050. Người tổng hợp kiểm tra: kể cả khi mỗi lần bị call ta đều mất trọn 1.000, kỳ vọng vẫn là 0,5 × 1.050 − 0,5 × 1.000 = +25. Ngoài ra, khi có người chơi với ta, đôi khi ta có bài mạnh. Các tình huống này xảy ra thường xuyên, và xét về khai thác rất đáng để ý những người bỏ bài quá thường trước cú raise khi có ante.

### 11. Thỏa thuận tài trợ giải đấu (Tournament Backing Agreements, trang 369–371)

#### Thỏa thuận mở và nguy cơ mất hết 100%

Ở Phần IV (Chương 25), tác giả đã bàn về giá trị của thỏa thuận tài trợ cho người tài trợ (backer) và người chơi, nhưng chỉ xét thỏa thuận cho ring game. Thỏa thuận tài trợ giải đấu phổ biến hơn nhiều, nên tác giả bàn ngắn cách đánh giá chúng.

Cơ cấu thỏa thuận tài trợ giải đấu phổ biến nhất (theo kinh nghiệm của tác giả) là một thỏa thuận mở với các điều kiện:

- Người tài trợ cấp một khoản bankroll.
- Người chơi chơi giải theo thỏa thuận.
- Lợi nhuận được chia theo tỷ lệ nào đó (thường chia đôi giữa người tài trợ và người chơi).
- Phần lớn thỏa thuận cho người chơi rút phần chia mỗi khi đang lời — thường sau một lần thắng vừa hoặc lớn.

Một điều cần cân nhắc: vì bankroll cố định không tăng, thỏa thuận với các điều kiện trên có nguy cơ "phá sản" — tức mất hết bankroll cố định — là **100%**. Lý do là lợi nhuận trước đó đã được chia cho người tài trợ và người được tài trợ. Điều này không nhất thiết có nghĩa thỏa thuận chắc chắn lỗ; chỉ có nghĩa nếu người tài trợ không chịu tăng bankroll thì tới một lúc nào đó người chơi sẽ mất hết khoản bankroll.

#### Thỏa thuận đóng: mô hình giải ảo winner-take-all

Có thể đánh giá một thỏa thuận giải đấu đóng (có thời hạn) bằng ý tưởng cỡ giải hiệu dụng. Giả sử người chơi giả định A có tỷ lệ thắng ước lượng khoảng 1 buyin mỗi giải, và A ký thỏa thuận với người tài trợ B để chơi 70 giải. Cuối kỳ hai bên thanh toán: B chịu mọi khoản lỗ, còn lời chia đều giữa A và B. Các giải có khoảng 400 người.

Có thể xấp xỉ kết quả các giải này bằng cách coi chúng là các giải winner-take-all (người thắng lấy hết) có cỡ nhỏ hơn. Tác giả dùng bội số phương sai giải đấu k của chương trước (Phương trình 27.5 — sách ghi nhầm là 27.4), k = n·Σv_i² − 1, với n là số người và v_i là tỷ lệ quỹ trả cho hạng i; với giải 400 người và cơ cấu thưởng thông thường, k khoảng 72. Có thể dùng phân phối nhị thức để đánh giá khả năng người chơi thắng một giải ảo như vậy. Vì lợi thế khoảng 1 buyin, xác suất thắng giải ảo khoảng 1 trên 36. (Người tổng hợp giải thích: giải ảo 72 người, thắng được 72 buyin, tốn 1 buyin; lời kỳ vọng 72p − 1 = 1 cho p = 2/72 = 1/36.)

Xác suất thắng giải ảo N lần trong 70 giải, P(N) = C(70, N) × (1/36)^N × (35/36)^(70−N):

| N | Xác suất |
|---:|---:|
| 0 | 13,92% |
| 1 | 27,84% |
| 2 | 27,44% |
| 3 | 17,77% |
| 4 | 8,50% |
| 5 | 3,21% |
| 6 | 0,99% |
| 7 | 0,26% |
| 8 | 0,06% |
| 9 | 0,01% |
| 10 | 0,00% |

Đây không phải xác suất thắng giải thật — xác suất đó dĩ nhiên thấp hơn nhiều. Nhưng kết quả chơi giải thật có thể xấp xỉ thô bằng kết quả chơi giải ảo (cỡ nhỏ hơn nhiều).

Chuyển bảng trên sang dạng phản ánh thỏa thuận tài trợ bằng cách thêm các cột thanh toán. Kết quả sau 70 giải là 72N − 70 buyin; nếu kết quả âm, người tài trợ chịu hết; nếu dương, người tài trợ được một nửa. Cột cuối là xác suất nhân phần của người tài trợ (số trong ngoặc là số âm):

| N | P(N) | Kết quả (buyin) | Phần của người tài trợ | Phần có trọng số |
|---:|---:|---:|---:|---:|
| 0 | 13,92% | −70 | (70,00) | (9,74) |
| 1 | 27,84% | 2 | 1,00 | 0,28 |
| 2 | 27,44% | 74 | 37,00 | 10,15 |
| 3 | 17,77% | 146 | 73,00 | 12,97 |
| 4 | 8,50% | 218 | 109,00 | 9,27 |
| 5 | 3,21% | 290 | 145,00 | 4,65 |
| 6 | 0,99% | 362 | 181,00 | 1,80 |
| 7 | 0,26% | 434 | 217,00 | 0,56 |
| 8 | 0,06% | 506 | 253,00 | 0,15 |
| 9 | 0,01% | 578 | 289,00 | 0,03 |
| 10 | 0,00% | 650 | 325,00 | 0,01 |
| **Tổng** | | | | **30,13** |

Người tổng hợp tính lại toàn bộ bảng: khớp từng dòng; tổng chính xác là 30,127 (cộng cả N > 10 thì 30,129). Kỳ vọng của kết quả chung là đúng 70 buyin.

Người tài trợ và người chơi cùng nhau thắng tổng cộng 70 buyin (vì tỷ lệ thắng 1 buyin mỗi giải). Phần của người tài trợ chỉ là 30,13 thay vì 35 do bản chất của thỏa thuận. Vậy người tài trợ mất khoảng 35 − 30,13 = 4,87 ≈ 4,9 buyin cho người chơi. Đây vẫn là trường hợp tốt hơn đáng kể cho người tài trợ so với thỏa thuận thông thường, vì việc thanh toán chỉ xảy ra ở cuối 70 giải. Có thể tính hiệu ứng thanh toán này bằng mô phỏng máy tính.

#### Mô phỏng

Tác giả mô phỏng 10.000 chuỗi 70 giải với một người chơi về mỗi hạng có thưởng với tần suất gấp đôi bình thường (tức tỷ lệ thắng 1 buyin mỗi giải), thanh toán ở cuối 70 giải. Lợi nhuận trung bình của người tài trợ là khoảng **32 buyin**. Khoảng cách giữa hai con số (30,13 và 32) có lẽ là thiên lệch hệ thống: phương pháp dùng bội số phương sai hơi đánh giá thấp lợi nhuận của người tài trợ. Rồi tác giả chạy cùng mô phỏng nhưng cho người chơi thanh toán mỗi khi đang lời. Lợi nhuận trung bình của người tài trợ khi đó khoảng **27 buyin**. Vậy quyền "thanh toán khi đang lời" ở đây đáng giá khoảng năm buyin (trên tổng 70) cho người chơi.

Giải thích của người tổng hợp về cơ chế: thỏa thuận này giống một quyền chọn. Người chơi được nửa phần lời nhưng không chịu phần lỗ, nên phần của người chơi là 0,5 × max(kết quả, 0), còn người tài trợ nhận kết quả − 0,5 × max(kết quả, 0). Kết quả càng phân tán (giải đấu lệch mạnh, nhiều chuỗi lỗ, một số chuỗi thắng lớn), giá trị "quyền chọn" của người chơi càng cao. Thanh toán thường xuyên giống như "chốt" quyền chọn sau mỗi lần thắng, để các khoản lỗ sau đó lại rơi hết vào người tài trợ.

#### "Công bằng" là tương đối

"Công bằng" trong thỏa thuận tài trợ là khái niệm tương đối. Thực tế, thỏa thuận tài trợ tồn tại trong một thị trường, và quy luật thị trường quyết định "giá" của việc tài trợ một người chơi. Tuy nhiên, người tài trợ cần biết rằng **thỏa thuận càng ngắn và người chơi càng được thanh toán thường xuyên, kỳ vọng của người tài trợ càng bị giảm bởi độ lệch của kết quả giải đấu.**

### 12. Các ý chính cuối chương (Key Concepts, trang 371)

- Khi dùng lý thuyết trò chơi cho giải đấu (có nhiều hạng thưởng), phải nhớ rằng trò chơi không thuần túy là trò chơi hai người. Khi hai người đối đầu, mọi người khác được lợi. Vì vậy chơi giải đấu chịu ảnh hưởng mạnh của khái niệm "trò chơi gà" — thường tốt hơn nhiều khi là người đầu tiên vào pot bằng toàn bộ chip so với là người thứ hai.
- Nhiều cơ cấu giải khác nhau đã được đề xuất và trở nên phổ biến. Mỗi cơ cấu đòi hỏi những điều chỉnh lối chơi cụ thể khác nhau để tối đa equity.
- Thỏa thuận tài trợ giải đấu có thể đánh giá bằng một số công cụ đã dùng cho thỏa thuận tài trợ ring game. Độ lệch rất mạnh của kết quả giải đấu khiến các thỏa thuận này thường rất có lợi cho người chơi, nhất là nếu thanh toán diễn ra khi người chơi đang lời.
- Một khuyến nghị cụ thể cho giải no-limit: nếu chồng chip từ sáu lần pot trước flop (gồm ante và blind) trở lên, nên raise một khoản nhỏ hợp lý; dưới mức này, nên jam all-in.

## Luận điểm cốt lõi

### Mệnh đề

Trong giải đấu có nhiều hạng thưởng, giá trị của chip không tuyến tính và ván đối đầu hai người không phải trò chơi tổng hằng: cuộc đối đầu làm cả hai người mất equity cho những người ngồi ngoài. Vì vậy người hành động trước có lợi thế kiểu trò chơi gà, người call phải chặt hơn người jam, và mỗi thể thức giải (bubble, sit-and-go, supersatellite, rebuy, ante) đòi hỏi điều chỉnh riêng. Nhưng ở phần lớn giải nhiều bàn, cơ cấu thưởng đủ đều để "poker vẫn là poker": gom chip vẫn là gom tiền.

### Giả định

- Người chơi ngang tài khi tính equity ở bubble; xác suất về các hạng được ước lượng thô theo tỷ lệ chip (sách không dùng mô hình chính xác ở các ví dụ).
- Lý thuyết Nhân đôi đúng (xác suất nhân đôi C không đổi) khi định giá rebuy và add-on; bỏ qua rủi ro và phương sai; người chơi có đủ bankroll.
- Kết quả giải thật có thể xấp xỉ bằng giải ảo winner-take-all cỡ k (bội số phương sai giải đấu), và các giải độc lập với nhau.
- Đối thủ phản ứng hợp lý với cú jam (bỏ bài trừ khi có bài đủ mạnh) — trừ các chỗ khai thác người chơi quá chặt.

### Cơ chế

1. Cuộc đối đầu all-in chuyển equity từ hai người đối đầu sang những người ngồi ngoài.
2. Người call phải bù cả "hiệu ứng dải bài" lẫn phần equity mất đi do đối đầu, nên cần equity cao hơn nhiều so với tính theo chip (61% thay vì 42% ở Ví dụ 28.2).
3. Người hành động trước, nhờ thứ tự lần lượt, chọn được cân bằng "lao thẳng – tránh" có lợi cho mình bằng cách jam.
4. Khi giá trị chip phi tuyến mạnh (supersatellite), chip thêm gần như vô giá trị, nên rủi ro bị loại lấn át lợi thế equity của ván bài.
5. Khi chip được bán rẻ hơn giá trị theo kỹ năng (add-on), mua là đúng; Lý thuyết Nhân đôi cho giá trị đó.
6. Với thỏa thuận tài trợ, sự bất đối xứng lời–lỗ cộng với phân phối kết quả lệch mạnh làm người tài trợ nhận ít hơn nửa lợi nhuận kỳ vọng, và càng ít khi thanh toán càng thường xuyên.

### Bằng chứng và ví dụ tác giả đưa ra

- AJo chỉ có 42,8% (theo sách; người tổng hợp tính khoảng 48%) trước dải {55+, A9+, KJ+}.
- Trò chơi gà với bảng thưởng (−10, −10), (1, −1), (−1, 1), (0, 0) và ba điểm cân bằng.
- Ví dụ 28.2: 3,75 buyin khi call và thắng, 2,3 khi bỏ bài, cần 61,33% so với 42% theo chip.
- Mẹo bubble: 1.200 chip × 16% ≈ 200 chip.
- Sit-and-go: cần 62,5% (một chồng lớn) và 65,8% (bốn chồng bằng nhau).
- Câu chuyện AA trước JJ ở supersatellite WSOP: 81% thắng pot nhưng call vẫn sai.
- Add-on: 953 và 1.162 đô la, chênh 209 đô la cho giá 100 đô la; điểm hòa vốn 8.325 chip khi C = 0,51 và giá 150 đô la.
- Ante: raise lên 1.000 để lấy 1.050 chip với 50% thành công.
- Tài trợ 70 giải: người tài trợ được 30,13 buyin (mô hình), 32 (mô phỏng, thanh toán cuối kỳ), 27 (mô phỏng, thanh toán khi lời).

### Kết luận và hàm ý cho người chơi

- Trong giải đấu, hãy là người đầu tiên all-in; ở bubble với bước nhảy lớn, call all-in phải rất chặt.
- Ở bubble giải nhiều bàn có cơ cấu thưởng đều, hãy khai thác người chơi quá chặt bằng cách raise blind của họ.
- Ở supersatellite, khi đã đủ chip để chắc có suất, hãy bỏ mọi bài.
- Lấy add-on giảm giá gần như luôn đúng; rebuy giá gốc cần cân nhắc theo kỹ năng.
- Khi chồng dưới sáu lần pot trước flop, jam thay vì raise nhỏ; ưu tiên bài có equity showdown và bài có lá chặn.
- Người tài trợ nên tránh thỏa thuận ngắn hạn cho phép thanh toán khi đang lời, hoặc đòi tỷ lệ chia bù lại.

### Trong ngôn ngữ lý thuyết trò chơi và xác suất

Ván đối đầu trong giải đấu là trò chơi hai người không tổng hằng (thực ra là một phần của trò chơi nhiều người, nơi người thứ ba là "người hưởng lợi" thụ động). Trò chơi gà có hai cân bằng Nash thuần (bất đối xứng) và một cân bằng hỗn hợp đối xứng (mỗi người lao thẳng với xác suất 1/10, thưởng −0,1). Khi trò chơi được chơi lần lượt (dạng mở rộng), quy nạp ngược chọn cân bằng có lợi cho người đi trước — một dạng lợi thế người đi trước (first-mover advantage) hay cam kết (commitment). Ánh xạ chip sang equity là một hàm lõm (giống hàm hữu dụng sợ rủi ro), nên người chơi nên từ chối một số cược có kỳ vọng chip dương. Phân tích tài trợ là phép tính kỳ vọng trên phân phối nhị thức của một khoản thưởng phi tuyến 0,5·max(X, 0), tương tự định giá quyền chọn.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| tournament | giải đấu | thể thức chơi tới khi bị loại, thưởng theo hạng |
| cash game / ring game | cash game / ring game | ván chơi tiền thật, chip đổi ngay ra tiền |
| constant-sum game | trò chơi tổng hằng | tổng thưởng của các người chơi không đổi theo kết quả |
| zero-sum game | trò chơi tổng bằng không | điều một người được đúng bằng điều người kia mất |
| equity | equity | phần giá trị kỳ vọng của mình trong pot hay trong quỹ thưởng |
| prize equity | equity giải thưởng | phần quỹ thưởng kỳ vọng, tính bằng tiền hoặc buyin |
| chip EV | chip EV | kỳ vọng tính bằng chip |
| buyin | buyin | phí tham gia giải; cũng dùng làm đơn vị tiền |
| all-in | all-in | đẩy hết chip vào pot |
| jam | jam | all-in, thường trước flop |
| jam-or-fold | jam-or-fold | chiến lược chỉ có hai hành động: đẩy hết hoặc bỏ bài |
| fold | fold | bỏ bài |
| call | call | theo cược |
| raise / re-raise | raise / re-raise | tăng cược / tăng cược lại |
| blind (small blind, big blind) | blind | khoản cược bắt buộc của hai vị trí sau button |
| button | button | vị trí chia bài, hành động cuối sau flop |
| under-the-gun | under-the-gun | vị trí hành động đầu tiên trước flop |
| headsup | đối đầu hai người | ván hay trận chỉ có hai người |
| shorthanded | ít người | bàn có ít người (thường 2–6) |
| pot | pot | tổng tiền cược trong ván |
| showdown | showdown | lật bài so khi kết thúc cược |
| distribution (of hands) | dải bài | tập các tay bài một người có thể có |
| game of chicken | trò chơi gà | trò chơi hai người lao vào nhau, ai tránh là "gà" |
| equilibrium | cân bằng | cặp chiến lược không ai tự đổi mà có lợi hơn |
| mixed strategy | chiến lược hỗn hợp | chọn ngẫu nhiên giữa các hành động theo xác suất |
| indifferent | bàng quan | hai lựa chọn có cùng kỳ vọng |
| bubble | bubble | giai đoạn ngay trước vùng có thưởng |
| in the money | vùng có thưởng | các hạng được trả tiền |
| sit-and-go | sit-and-go | giải một bàn, bắt đầu khi đủ người |
| multi-table tournament | giải nhiều bàn | giải bắt đầu ở nhiều bàn, gộp dần |
| shootout | shootout | giải mà người thắng mỗi bàn đi tiếp |
| single-table satellite | satellite một bàn | giải một bàn, người thắng được vé giải lớn hơn |
| supersatellite | supersatellite | giải chia quỹ thành nhiều suất bằng nhau |
| match play | match play | giải gồm chuỗi trận đối đầu hai người |
| rebuy | rebuy | mua lại chip với giá gốc trong thời gian quy định |
| add-on | add-on | lần mua thêm chip cuối cùng, thường giảm giá |
| at par | giá gốc | giá chip bằng giá lúc mua vào |
| Theory of Doubling Up | Lý thuyết Nhân đôi | E = C^N, với C là xác suất nhân đôi chồng chip |
| effective tournament size | cỡ giải hiệu dụng | cỡ giải winner-take-all có cùng chỗ cho kỹ năng |
| tournament variance multiple | bội số phương sai giải đấu | k = n·Σv_i² − 1 |
| winner-take-all | người thắng lấy hết | giải chỉ trả cho hạng nhất |
| binomial distribution | phân phối nhị thức | số lần thành công trong n phép thử độc lập |
| stack | chồng chip | số chip một người có |
| shortened stack | chồng chip ngắn | chồng nhỏ so với blind |
| implied odds | implied odds | tỷ lệ cược tính cả khoản thắng thêm ở các vòng sau |
| blocker | lá chặn | lá bài làm giảm tổ hợp bài mạnh của đối thủ |
| ante | ante | khoản cược bắt buộc của mọi người trước ván |
| overlay | overlay (phần thưởng phụ) | phần tiền thêm làm tỷ lệ trả thưởng tốt hơn công bằng |
| stud | stud | thể loại poker có bài ngửa và úp, không có lá chung |
| limit / no-limit | limit / no-limit | có / không giới hạn mức cược |
| hold'em | hold'em | thể loại poker hai lá riêng, năm lá chung |
| steal | cướp blind | raise với bài yếu để lấy blind |
| bankroll / half-bankroll | bankroll / nửa bankroll | vốn chơi / vốn có 50% nguy cơ mất hết |
| backing agreement | thỏa thuận tài trợ | người tài trợ cấp vốn, chịu lỗ, chia lời |
| backer | người tài trợ | người cấp vốn trong thỏa thuận tài trợ |
| settle | thanh toán | chốt sổ và chia lời giữa hai bên |
| risk of ruin | nguy cơ phá sản | xác suất mất hết vốn |
| exploitive | khai thác | lối chơi nhắm vào điểm yếu cụ thể của đối thủ |
| Monte Carlo simulation | mô phỏng Monte Carlo | ước lượng bằng lặp lại ngẫu nhiên nhiều lần |

## Câu nói đáng nhớ

> "In a tournament, every player has some stake in every hand, because every player gains equity when other players are eliminated." — mục "Game Theoretic Tournament Concepts"
>
> *Dịch: Trong giải đấu, mỗi người chơi đều có phần lợi ích trong mọi ván bài, vì ai cũng được thêm equity khi người khác bị loại.*
>
> Đây là nền tảng của cả chương: ván đối đầu không còn là chuyện riêng của hai người.

> "When an all-in confrontation occurs, both players lose some equity." — mục "Game Theoretic Tournament Concepts"
>
> *Dịch: Khi xảy ra một cuộc đối đầu all-in, cả hai người đều mất một phần equity.*
>
> Câu này giải thích vì sao người call trong giải đấu cần bài mạnh hơn ở cash game.

> "The first player should attempt to establish the favorable equilibrium of jam-fold if possible." — Ví dụ 28.1
>
> *Dịch: Người chơi đầu tiên nên cố thiết lập cân bằng jam-fold có lợi cho mình nếu có thể.*
>
> Hàm ý thực hành của trò chơi gà: hãy là người jam trước.

> "Why did the second big stack even look at his cards?" — mục "Supersatellites"
>
> *Dịch: Sao người chồng lớn thứ hai còn nhìn bài làm gì?*
>
> Ở supersatellite, khi đã chắc suất, ván bài nào (kể cả AA) cũng không đáng đánh cược.

> "The AA hand was not wagering chips: he was wagering his equity in a seat." — mục "Supersatellites"
>
> *Dịch: Người cầm AA không cược chip: họ cược equity của một suất.*
>
> Đơn vị đúng để ra quyết định là giá trị giải thưởng, không phải chip.

> "The fundamental idea is that the game is still poker." — mục "Multi-table Tournaments"
>
> *Dịch: Ý cơ bản là trò chơi vẫn là poker.*
>
> Tên chương: ở phần lớn giải nhiều bàn, gom chip vẫn là gom tiền.

> "Aggressively accumulating chips should not give way to passively surviving simply because chips are irreplaceable." — mục "Multi-table Tournaments"
>
> *Dịch: Việc gom chip chủ động không nên nhường chỗ cho việc cố sống sót thụ động chỉ vì chip không mua lại được.*
>
> Phản bác lối chơi "sống sót là trên hết" phổ biến ở giải đấu.

> "The shorter the duration of the backing agreement and the more often the player may settle, the expectation of the backer is diminished by the skew of tournament results." — mục "Tournament Backing Agreements"
>
> *Dịch: Thỏa thuận tài trợ càng ngắn và người chơi càng được thanh toán thường xuyên, kỳ vọng của người tài trợ càng bị độ lệch của kết quả giải đấu làm giảm.*
>
> Bài học cho người cấp vốn: điều khoản thanh toán quan trọng không kém tỷ lệ chia lời.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương nối ba chương giải đấu thành một bộ công cụ dùng được: trò chơi gà cho trực giác lý thuyết trò chơi về "ai all-in trước", Lý thuyết Nhân đôi định giá rebuy và add-on, bội số phương sai giải đấu biến bài toán tài trợ thành một phép tính nhị thức đơn giản. Ví dụ 28.2 cho thấy rất rõ khoảng cách giữa tư duy chip (42%) và tư duy tiền (61%), và câu chuyện AA ở supersatellite là minh họa đáng nhớ nhất về hàm giá trị phi tuyến. Phân tích thỏa thuận tài trợ đặc biệt có giá trị: nó chỉ ra một chi phí ẩn (khoảng 5 buyin trên 70 vì điều khoản thanh toán khi lời) mà người tài trợ thường bỏ qua.

### Những chỗ đơn giản hóa

- **Xác suất về các hạng là ước lượng thô.** Sách dùng các con số như "21% / 29% / 50%" mà không nêu mô hình; người tổng hợp so với Malmuth-Harville thì các ngưỡng equity cần thấp hơn vài điểm phần trăm (58,2% thay vì 61,33%; 60,9% thay vì 62,5%). Kết luận định tính không đổi.
- **Phép tính call so với tay bài ngẫu nhiên.** Ở tình huống bốn chồng bằng nhau, sách giả định người jam jam "mù", nên so với tay ngẫu nhiên là đúng. Nhưng khi người jam chọn bài, người call phải so với dải jam thật, thường cần bài chặt hơn nữa.
- **Một số chỗ đếm và equity lệch:** 7% thay vì 9,8%; AJs nằm dưới ngưỡng 65,8%; AJo 42,8% thay vì khoảng 48% (xem khối Lưu ý).
- **Bỏ qua nhiều người cùng call** và vị trí (ai ở blind) khi tính lợi nhuận của cú jam mù.
- **Lý thuyết Nhân đôi** giả định C không đổi tới tận khi có nửa tổng chip; tác giả tự thừa nhận lý thuyết không còn đúng ở mức đó, nên câu "luôn mua add-on" chỉ chắc chắn cho các chồng chip thông thường.
- **Mô hình giải ảo winner-take-all** bỏ qua cấu trúc nhiều hạng thưởng thật; tác giả tự kiểm tra bằng mô phỏng (30,13 so với 32 buyin), một cách làm đáng học.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- **ICM trở thành công cụ chuẩn.** Mô hình Malmuth-Harville (thường gọi là ICM — Independent Chip Model) được tích hợp vào phần mềm huấn luyện và solver; các bảng "dải call ở bubble sit-and-go" mà chương này ước lượng bằng tay nay được tính chính xác cho mọi cấu hình chồng chip, kể cả mô hình nhìn trước vài ván (future game simulation). Khái niệm "bubble factor" (tỷ số giữa equity mất khi thua và equity được khi thắng) là cách hệ thống hóa đúng ý của Ví dụ 28.2.
- **Solver GTO cho giải đấu** tính chiến lược cân bằng có tính ICM cho nhiều người; kết quả xác nhận ý của chương: người mở pot jam rộng hơn, người call ở bubble chặt hơn nhiều, và chồng vừa bị chồng lớn "bắt nạt".
- **Thể thức thay đổi:** sit-and-go 10 người với thưởng 5-3-2 đã nhường chỗ phần lớn cho các thể thức nhanh (hyper-turbo, spin-and-go có giải ngẫu nhiên) và giải có tiền thưởng truy đuổi (bounty/progressive knockout), nơi tiền thưởng khi loại người khác làm thay đổi phép tính call all-in. Supersatellite vẫn phổ biến dưới dạng satellite online trả nhiều vé bằng nhau.
- **Thị trường tài trợ** phát triển thành các nền tảng bán phần (staking/selling action) với "markup" (giá bán phần cao hơn mệnh giá) — một cách định giá chính xác điều chương gọi là "giá thị trường của việc tài trợ". Điều khoản "makeup" (người chơi phải bù lỗ trước khi được chia lời) là cách người tài trợ chống lại hiệu ứng thanh toán khi đang lời mà chương phân tích.

### Liên hệ các chương khác

- [C10-ly-thuyet-tro-choi.md](C10-ly-thuyet-tro-choi.md): khái niệm cân bằng, chiến lược hỗn hợp, điểm bàng quan dùng trong trò chơi gà.
- [C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md): chiến lược jam-or-fold, ngưỡng khoảng mười blind, T9s là bài jam tới blind rất cao.
- [C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md): nguy cơ phá sản và khái niệm nửa bankroll (sit-and-go chỉ cần 6–7 buyin).
- [C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md): thỏa thuận tài trợ ring game, nền cho mục tài trợ giải đấu.
- [C26-giai-dau-phan-1-nhan-doi.md](C26-giai-dau-phan-1-nhan-doi.md): Lý thuyết Nhân đôi E = C^N và cỡ giải hiệu dụng, dùng cho rebuy và add-on.
- [C27-giai-dau-phan-2-chip-khong-phai-tien.md](C27-giai-dau-phan-2-chip-khong-phai-tien.md): các công thức equity (Malmuth-Harville) và bội số phương sai giải đấu k (Phương trình 27.5).
- [C29-tro-choi-nhieu-nguoi.md](C29-tro-choi-nhieu-nguoi.md): lý thuyết trò chơi nhiều người tổng quát, nơi "người ngồi ngoài được lợi" trở thành liên minh ngầm.
- [C30-ket-hop-tat-ca.md](C30-ket-hop-tat-ca.md): tổng kết cách tiếp cận của cả cuốn sách.

### Vận dụng

- **Cho người chơi poker:** tính equity cần để call all-in bằng equity giải thưởng (ICM), không bằng chip; ở bubble sit-and-go, ngưỡng có thể lên tới 60–66%. Hãy là người jam trước. Dùng mẹo "quy giá trị lên hạng ra chip" khi không có thời gian tính. Ở supersatellite đã chắc suất, bỏ mọi bài. Luôn lấy add-on giảm giá nếu bạn là người thắng.
- **Cho người làm tài chính và đầu tư:** (1) Câu chuyện AA là bài học về hàm giá trị lõm: khi mục tiêu là vượt một ngưỡng (giữ hạng tín nhiệm, đạt mức vốn tối thiểu, đủ quỹ hưu trí), một cược có kỳ vọng dương vẫn có thể sai nếu nó đe dọa ngưỡng — giống quỹ hưu trí đã đủ tài trợ nên giảm rủi ro thay vì tối đa lợi suất. (2) Thỏa thuận tài trợ chia lời, không chia lỗ giống phí thưởng hiệu quả (performance fee) của quỹ đầu cơ: người quản lý có một quyền chọn mua trên kết quả; phí trả mỗi năm mà không có "high-water mark" (ngưỡng đỉnh cũ) hay cơ chế thu hồi tương tự việc "thanh toán khi đang lời" và làm nhà đầu tư thiệt khoảng 5/70 lợi nhuận trong ví dụ của chương. Điều khoản makeup trong poker chính là high-water mark. (3) Lợi thế người đi trước trong trò chơi gà xuất hiện trong cạnh tranh doanh nghiệp (cam kết đầu tư công suất trước để đối thủ rút lui) và trong đàm phán.
- **Cho người ra quyết định nói chung:** khi có bên thứ ba hưởng lợi từ xung đột giữa hai bên, cả hai bên nên tránh đối đầu nhiều hơn so với khi chỉ có hai bên — đây là lý do các đối thủ cạnh tranh đôi khi tránh "chiến tranh giá".

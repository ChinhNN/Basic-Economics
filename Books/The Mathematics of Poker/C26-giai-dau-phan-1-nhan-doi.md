# Chương 26 — Nhân đôi: Giải đấu, phần I (Doubling Up: Tournaments, Part I)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Phần V "Other Topics" (trang mở phần, trang 332), Chương 26 "Doubling Up: Tournaments, Part I", trang 333–345.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Phần IV (Rủi ro) đã xây dựng mô hình rủi ro phá sản cho bankroll ([C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md), [C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md)), tiêu chuẩn Kelly với hàm hữu dụng logarit ([C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md)) và lý thuyết danh mục ([C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md)); điểm chung của các chương đó là tiền mất đi thì không thay thế được ngay, nên giá trị của tiền không còn tuyến tính. Phần V mở đầu bằng giải đấu (tournament), nơi tính phi tuyến này xuất hiện ở dạng rõ nhất: chip giải đấu không mua lại được và giải thưởng chia theo thứ tự bị loại. Chương 26 xử lý hệ quả thứ nhất — kỹ năng làm chip có giá trị phi tuyến — bằng **Lý thuyết Nhân đôi** (Theory of Doubling Up), dùng cho giai đoạn đầu và giữa giải. Chương 27 ([C27-giai-dau-phan-2-chip-khong-phai-tien.md](C27-giai-dau-phan-2-chip-khong-phai-tien.md)) xử lý hệ quả thứ hai — cơ cấu trả thưởng — bằng các mô hình chuyển chip thành tiền gần vùng có thưởng (công thức chia theo tỷ lệ chip, công thức Landrum-Burns, công thức Malmuth-Harville và công thức Malmuth-Weitzman) và bàn cách tính khoảng tin cậy cho tỷ lệ thắng giải, và Chương 28 ([C28-giai-dau-phan-3-poker-van-la-poker.md](C28-giai-dau-phan-3-poker-van-la-poker.md)) đưa các mô hình này vào quyết định cụ thể. Ý tưởng "đổi một phân phối kết quả thành một con số kỳ vọng rồi tối đa hoá con số đó" là cách làm xuyên suốt sách từ Chương 1 ([C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md)).
**Ý chính:** **Trong giải đấu, mục tiêu không phải là tối đa hoá số chip kỳ vọng mà là tối đa hoá tiền thưởng kỳ vọng; vì chip không thay thế được và người giỏi còn nhiều cơ hội dùng kỹ năng về sau, chip của người giỏi có giá trị lõm (mỗi chip thêm đáng ít hơn chip trước), và Lý thuyết Nhân đôi đo lường hiệu ứng này bằng một công thức đơn giản E = C^N.** Mở đầu chương nêu hai nguyên tắc của mọi giải đấu: chip không thay thế được (dẫn tới điều chỉnh do kỹ năng), và giải thưởng chia theo thứ tự bị loại chứ không theo số chip (dẫn tới sự tách rời giữa equity chip và equity giải thưởng). Ví dụ 19 người còn lại trong giải 200 người: một chip T100, lúc đầu giải chỉ đáng 6,67 đô la, nay đáng ít nhất 210 đô la vì người giữ nó có 84% khả năng lọt vào vùng có thưởng 250 đô la. Tác giả cảnh báo việc phóng đại "chơi để sống sót" sang đầu giải là sai. Lý thuyết Nhân đôi giả định xác suất C để một người nhân đôi chồng chip trước khi bị loại là hằng số suốt giải; khi đó xác suất thắng giải winner-take-all (người nhất lấy hết) là E = C^N (26.1), với N = log₂(số chồng chip ban đầu cần gom). Người chơi ngang tài có C = 0,5 và chip tuyến tính; người thắng 1 buyin ròng mỗi giải 100 người có C = 0,555. Ví dụ tay Q♠T♠ trên flop K♠8♣2♠: gọi 2.050 để thắng 4.025 với 36% equity lời 137 chip, nhưng với người có lợi thế 3/4 buyin (C = 0,5364), fold (equity 0,009269 buyin) tốt hơn call (0,008857 buyin). Bài toán "coinflip" ở ván đầu cho ngưỡng W = C; ai từ chối QQ đấu AK (57–43) thì ngầm cho rằng mình có khoảng 2,8 buyin mỗi giải. Người chơi lỗ nên chấp nhận phương sai; người thứ ba vào một pot all-in cần 30,25% thay vì 25% nếu C = 0,55. Công thức viết lại thành E = S^β với β = −log₂C (26.2). Cuối cùng, khi giải thưởng chia cho nhiều hạng, ảnh hưởng của kỹ năng giảm; tác giả định nghĩa **cỡ giải hiệu dụng** k (effective tournament size) qua (2C)^{log₂k} = E_N (26.3): giải đấu đối kháng 256 người trả 154 và 102 buyin cho nhất và nhì có k ≈ 147,7, và công thức xấp xỉ tổng quát N − D = Σ i·w_i·log₂ i cho k = 256/2^{204/256} ≈ 147,35.

> **Lưu ý:**
> - **"20% giải thưởng" ở ví dụ 19 người là sai số (sách, trang 334):** sách viết rằng gom toàn bộ chip "chỉ đáng 20% quỹ thưởng", nhưng giải nhất được mô tả là 6.000 đô la trên quỹ 20.000 đô la, tức 6.000 / 20.000 = 30%. Người tổng hợp ghi 30%. (Có thể tác giả nghĩ tới mức "20–25% cho giải nhất" mà họ nhắc ở đoạn sau.)
> - **"Nhân đôi bảy lần" ở giải đối kháng 256 người (trang 338):** sách viết equity là (256)(C⁸), "tức là xác suất nhân đôi bảy lần (thắng bảy trận)". Vì 256 = 2⁸, người chơi phải nhân đôi tám lần (thắng tám trận); số mũ 8 trong công thức đúng, chữ "bảy" sai.
> - **2,85 buyin trong bài toán QQ đấu AK (trang 337):** sách tính E = 0,57⁸ = 0,01114 rồi nói "khoảng 2,85 buyin mỗi giải" cho giải 250 người. Với 250 người: 0,01114 × 250 = 2,79 buyin. Con số 2,85 khớp với 0,01114 × 256 = 2,85 (coi giải có 256 người, tức đúng 8 lần nhân đôi), hoặc với N = log₂250 = 7,966 chính xác: 0,57^7,966 × 250 = 2,84. Kết luận "gần gấp ba equity trung bình" không đổi.
> - **Nhận xét "w_i tính bằng buyin, không phải phần của quỹ thưởng" bị ngược (trang 343, nhận xét của người tổng hợp):** phương trình xác định k là 2^N · Σ q_i·w_i = (2C)^D. Ở bước sau tác giả dùng Σ i·w_i = 1, điều chỉ đúng khi w_i là **phần của quỹ thưởng** (vì Σ i·w_i = P, tổng quỹ). Thừa số 2^N = X đổi phần quỹ thưởng ra buyin. Vậy để đạo hàm đúng, w_i phải là phần của quỹ, và chính ví dụ kiểm tra cuối chương cũng dùng w₁ = 154/256, w₂ = 102/256 (phần của quỹ).
> - **Đơn vị "buyin" trong ví dụ Q♠T♠ (trang 337, nhận xét của người tổng hợp):** sách ghi 0,024603, 0,009269, 0,008857 "buyins", nhưng các số này là xác suất thắng giải winner-take-all (phần của quỹ thưởng), vì chúng được tính từ 1,75/250. Muốn đổi ra buyin phải nhân với 250: 6,15; 2,32; 2,21 buyin. Kết luận fold tốt hơn call không đổi.
> - **Tham chiếu sai chỗ (trang 333):** sách hứa bàn việc mua rebuy "ở phần sau của chương này", nhưng mục về giải rebuy nằm ở Chương 28 ([C28-giai-dau-phan-3-poker-van-la-poker.md](C28-giai-dau-phan-3-poker-van-la-poker.md)).
> - **Ký hiệu không nhất quán và lỗi in trong phần đạo hàm (trang 341–345):** (a) định nghĩa q_i được in là Σ_{i=1}^{X} p_i; đúng phải là q_i = Σ_{j=1}^{i} p_j (cộng dồn tới hạng i). (b) định nghĩa w_i được in là Σ_{i=1}^{X} (v_i − v_{i+1}); đúng phải là w_i = v_i − v_{i+1} (không có dấu tổng). (c) trong chứng minh Σ i·w_i = P, dòng đầu in "v_{i−v}" thay cho v_i. (d) ví dụ ba mức thưởng và ví dụ kiểm tra cuối chương đổi tên w thành g (g₁ = v₁ − v₂…) mà không báo. (e) chữ N vừa là số lần nhân đôi (N = log₂X) vừa là số thứ hạng trong giả định "về hạng N" và trong "q_N". (f) câu "giả sử e đủ gần 0,5" phải là "giả sử ε đủ gần 0" (vì ε = 2C − 1, và C gần 0,5). (g) phép khai triển (1 + ε)^x ≈ 1 + xε là xấp xỉ bậc một, sách viết dấu "=".
> - **Lớp chữ và ảnh trang:** các công thức ở trang 340 (tính d), 343–344 (phương trình xác định k và bốn bước biến đổi) bị hỏng cả trong lớp chữ lẫn trong ảnh trang (bản dựng lại bằng LibreOffice in ra các ký tự "¿" thay cho vế phải). Người tổng hợp dựng lại các công thức từ ngữ cảnh và kiểm tra bằng số: d = ln(2(0,02·(2·154/256 − 1) + 0,5)) / ln(1,04) + 7 = 7,2063, k = 2^d = 147,68, khớp với sách. Lớp chữ cũng in "E — 1/X" (đúng là E = 1/X), "values of A"" (đúng là giá trị của X), "symbol 5" (đúng là δ), "13000" (đúng là 1/3000), "34 of a buyin" (đúng là 3/4), "'/4 chance" (đúng là 1/4), "brushing" (đúng là busting), "hi fact" (in fact), "whining player" (winning player).
> - **Tính lại:** mọi con số khác của chương đều khớp khi tính lại: C = 0,02^{1/log₂100} = 0,5550; C^{log₂50} = 0,0360; C = (1,75/250)^{1/log₂250} = 0,5364; 0,5364^{log₂(250/4,05)} = 0,024603; 0,5364^{log₂(250/1,36667)} = 0,009269; 0,36 × 0,024603 = 0,008857; 0,36 × 6.075 − 2.050 = 137; 0,55² = 0,3025; 0,53^{log₂(147,68/16)} × 147,68 = 19,287; 0,53³ × (0,53 × 154 + 0,47 × 102) = 19,288; 256 / 2^{204/256} = 147,35.
> - **Quy ước thuật ngữ:** "equity" giữ nguyên tiếng Anh (phần giá trị kỳ vọng của người chơi trong pot hoặc trong quỹ thưởng); "chip equity" dịch là equity chip (số chip giữ trong tay), "prize equity" là equity giải thưởng (giá trị tiền kỳ vọng của số chip đó). "Buyin" là phí tham gia giải; equity tính bằng buyin. Chip giải đấu ghi T100, T400 như sách (T là "tournament").

## Sơ đồ

### Phần V — Chủ đề khác (Part V: Other Topics, trang 332)

```text
       Câu đề từ của Phần V (Shakespeare, Hamlet, hồi I cảnh 5):
       "Trên trời dưới đất còn nhiều điều hơn những gì triết lý của
       anh mơ tới, Horatio"
                                │
                                ▼
       Phần V gồm những chủ đề nằm ngoài khung lý thuyết của bốn phần
       trước: giải đấu (Chương 26–28), trò chơi nhiều người
       (Chương 29) và tổng kết cách kết hợp mọi công cụ (Chương 30)
```

### Phần mở đầu Chương 26 — hai nguyên tắc của giải đấu (trang 333)

```text
       Giải đấu là mảng poker tăng trưởng mạnh nhất (từ giải World Poker
       Tour 10.000 đô la tới giải online 1 đô la hoặc freeroll hàng nghìn
       người). Mọi thể thức đều quy về HAI NGUYÊN TẮC
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       NGUYÊN TẮC 1: chip giải đấu       NGUYÊN TẮC 2: quỹ thưởng chia
       không thay thế được; hết chip     theo THỨ TỰ BỊ LOẠI, không theo
       là bị loại                        số chip gom được
       (giải rebuy là ngoại lệ tạm thời)
               │                                 │
               ▼                                 ▼
       ĐIỀU CHỈNH DO KỸ NĂNG:            TÁCH RỜI equity chip và equity
       · người có lợi thế nên bỏ qua     giải thưởng, nhất là ở giai
         các lợi thế mỏng đặt cả chồng   đoạn cuối giải
         chip vào rủi ro                 · ở cash game, tối đa hoá tiền
       · người có kỳ vọng âm nên sẵn       kỳ vọng nghĩa là tối đa hoá
         sàng all-in với cơ hội hơi        chip kỳ vọng
         bất lợi                         · ở giải đấu thì không luôn
       · điều chỉnh này thật, nhưng        như vậy
         nhiều người làm quá mức
```

### Ví dụ chồng chip T100 ở 19 người cuối (trang 333–334)

```text
       Giải limit hold'em 200 người ngang tài, còn 19 người, chơi
       hand-for-hand; hạng 10–18 nhận 250 đô la, giải nhất 6.000 đô la,
       quỹ thưởng 20.000 đô la; 300.000 chip, blind 300–600
       · A: T100, ngồi ở button; B: T400 và C: T500, cả hai ở vị trí
         under the gun (ở bàn khác)
                                │
                                ▼
       Đầu giải, T100 đáng 100/300.000 × 20.000 = 6,67 đô la
                                │
                                ▼
       Bây giờ: nếu A fold, B và C phải all-in vì blind; mỗi người
       thắng 40% → A sống sót vào vùng có thưởng với xác suất
       1 − 0,4 × 0,4 = 84% → T100 đáng ít nhất 0,84 × 250 = 210 đô la
                                │
                                ▼
       Giá trị này lấy từ các chồng chip lớn (gom hết chip chỉ được
       giải nhất 6.000 đô la, tức 30% quỹ; sách ghi nhầm 20%)
       · gần "bubble", chiếc ghế đáng giá hơn số chip
                                │
                                ▼
       Quan điểm của tác giả: KHÔNG kéo nguyên lý "sống sót bằng mọi
       giá" về đầu giải
       · đầu giải equity chip và equity giải thưởng gắn chặt
       · không đủ cơ hội đặt tiền khi là cửa trên rõ để bù lại việc
         chơi rụt rè, dễ bị khai thác
       · quỹ thưởng tập trung ở ba hạng đầu, và số chip dự báo mạnh
         khả năng vào ba hạng đầu
       · khai thác đối thủ hiểu sai các khái niệm này gần vùng có
         thưởng: nhiều lần bị loại "sát nút", nhưng nhiều hạng cao hơn
         và kỳ vọng cao hơn
       · mô hình giải đấu hữu ích nhất ở chỗ ÁNH XẠ equity chip sang
         equity giải thưởng; sau đó lại tối đa hoá tiền kỳ vọng
```

### Mục "The Theory of Doubling Up" — giả định và công thức E = C^N (trang 334–336)

```text
       Nhiều người bỏ qua cả lợi thế lớn ở đầu/giữa giải vì tin sẽ có cơ
       hội tốt hơn; nếu đúng, họ phải có lợi thế khổng lồ — quan sát
       thực tế không cho thấy vậy. Nhưng hiệu ứng có thật → đo nó
                                │
                                ▼
       Giải WINNER-TAKE-ALL, X người, chồng chip ban đầu bằng nhau
       GIẢ ĐỊNH: xác suất C để một người nhân đôi chồng chip của mình
       trước khi bị loại là HẰNG SỐ suốt giải
       · hai hiệu ứng làm C thay đổi nhưng đều yếu: chọn lọc (người mạnh
         sống lâu hơn nên C giảm dần), blind tăng (ép C về 50%)
                                │
                                ▼
       E = C^N                                              (26.1)
       E: xác suất thắng giải; N: số lần phải nhân đôi; X = 2^N
       · 128 người: 1→2→4→…→128, N = 7, E = C⁷
                                │
                                ▼
       Người ngang tài: E = 1/X = C^{log₂X} → log₂C = −1 → C = 0,5
       · giá trị chip đúng là tuyến tính
                                │
                                ▼
       Người chơi A, giải 100 người, thắng 1 buyin ròng (2 buyin gộp):
       0,02 = C^{6,643856} → C = 0,5550
       · với 2 chồng chip ban đầu: E = C^{log₂50} = 0,0360
         (lớn hơn 0,02 nhưng nhỏ hơn 2 × 0,02 = 0,04)
       · mô hình cho ánh xạ equity chip → equity giải CÓ TÍNH KỸ NĂNG
```

### Ví dụ tay Q♠T♠ trên flop K♠8♣2♠ (trang 336–337)

```text
       No-limit hold'em, 250 người, chồng ban đầu 1.500, blind 75–150
       B (3.000 chip) raise lên 450 ở button với Q♠T♠; big blind call
       Flop K♠8♣2♠: blind check, B bet 500, blind check-raise all-in
       B ước equity 36%, phải call 2.050 để thắng 4.025
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       Tính theo chip:                    Tính theo Lý thuyết Nhân đôi,
       0,36 × 6.075 − 2.050 = +137 chip   B có lợi thế 3/4 buyin:
       (gần 0,1 buyin) → call             1,75/250 = C^{log₂250}
                                          → C = 0,5364
                                                 │
                                                 ▼
                                   call thắng: 6.075 chip = 4,05 chồng
                                     E = 0,5364^{log₂(250/4,05)} = 0,024603
                                   call thua: E = 0
                                   fold: 2.050 chip = 1,36667 chồng
                                     E = 0,5364^{log₂(250/1,36667)} = 0,009269
                                   call: 0,36 × 0,024603 = 0,008857
                                                 │
                                                 ▼
                                   0,008857 < 0,009269 → FOLD đúng hơn
```

### Các hệ quả: coinflip, người chơi lỗ, người thứ ba vào pot (trang 337–338)

```text
       COINFLIP Ở VÁN ĐẦU: thắng với xác suất W thì equity thành
       W·C^{N−1}; từ chối thì giữ C^N → bàng quan khi W = C
       · người từ chối QQ đấu AK (57–43) ở giải 250 người ngầm cho rằng
         C > 0,57, tức E > 0,57⁸ = 0,01114, khoảng 2,8 buyin mỗi giải —
         gần gấp ba trung bình, ngang những người giỏi nhất thế giới
                                │
                                ▼
       NGƯỜI CHƠI CÓ KỲ VỌNG ÂM (C < 0,5): nên ưa phương sai, sẵn sàng
       đặt hết chip vào tình huống EV bằng 0 hoặc hơi âm; người khác
       càng có nhiều dịp dùng kỹ năng thì họ càng thiệt
                                │
                                ▼
       NGƯỜI THỨ BA VÀO POT ALL-IN: hai người đã all-in một cược bằng
       pot; người thứ ba call thì nếu thắng có gấp bốn số chip so với
       fold, tức bớt 2 lần nhân đôi
       · theo chip cần 25%; theo Lý thuyết Nhân đôi với C = 0,55 cần
         C² = 30,25%
```

### Dạng lũy thừa E = S^β (trang 338)

```text
       S: phần chip của tổng chip trong giải; N = log₂(1/S) = −log₂S
       E = C^{−log₂S} → ln E = (−log₂S)(ln C) = (ln S)(−log₂C)
       → log_S E = −log₂C → E = S^{−log₂C}
       Đặt β = −log₂C:   E = S^β                            (26.2)
       · C = 0,5 → β = 1, tuyến tính
       · C = 0,555 → β = 0,849 < 1, equity là hàm lõm của số chip
```

### Cơ cấu trả thưởng và cỡ giải hiệu dụng k (trang 338–341)

```text
       Giải đấu đối kháng (match play) winner-take-all 256 người:
       equity = 256·C⁸ = (2C)⁸; tổng quát E = (2C)^N (tính bằng buyin)
                                │
                                ▼
       Chia đều cho nhất và nhì (mỗi người 128 buyin):
       equity = 128·C⁷ = (2C)⁷
       · (2C)⁸ > (2C)⁷ khi C > 1/2: chia thưởng làm người giỏi thiệt
       · trận chung kết bị thay bằng "1/2", kỹ năng mất một thừa số 2C
       · tương đương một giải winner-take-all 128 người
                                │
                                ▼
       ĐỊNH NGHĨA cỡ giải hiệu dụng k:  (2C)^{log₂k} = E_N    (26.3)
       E_N: số buyin kỳ vọng thắng được với cơ cấu thưởng thật
                                │
                                ▼
       Nhất nhận phần f, nhì nhận 1 − f của quỹ:
       E = 256·[f·C⁸ + (1 − f)(C⁷ − C⁸)] = 256·C⁷·(2fC + 1 − C − f)
         = 256·C⁷·(δ(2f − 1) + 1/2),   với δ = C − 0,5
       · 256·C⁷: xác suất vào chung kết × cả quỹ
       · δ(2f − 1): phần equity thêm nhờ kỹ năng
       · 1/2: phần cơ bản
                                │
                                ▼
       d = log₂k:  (2C)^d = 256·C⁷·(δ(2f − 1) + 1/2)
       → d = ln(2(δ(2f − 1) + 1/2)) / ln(2C) + 7,   k = 2^d
       · f = 154/256, C = 0,52 → d = 7,206, k = 147,68
       · k gần như không phụ thuộc C (C = 0,51: 147,5; C = 0,60: 148,9)
       · cỡ giải hiệu dụng nhỏ hơn cỡ thật khoảng 108 người
                                │
                                ▼
       Kiểm tra: C = 0,53, đã thắng 4 trận (16 chồng chip):
       k·E = C^{log₂(k/S)} → E = 147,68 × 0,53^{log₂(147,68/16)} = 19,287
       Trực tiếp: 0,53³ × (0,53 × 154 + 0,47 × 102) = 19,288 buyin
```

### Tổng quát hoá cho mọi cơ cấu trả thưởng (phần đánh dấu "hơi khó", trang 341–345)

```text
       GIẢ ĐỊNH: xác suất về hạng i bằng xác suất nhân đôi tới 1/i tổng
       chip, trừ xác suất về hạng cao hơn
       → q_i (xác suất vào top i) = C^{N − log₂i}
       → p_i = q_i − q_{i−1}; p₁ = C^N
                                │
                                ▼
       Thưởng hạng i là v_i; w_i = v_i − v_{i+1} (w_X = v_X) là phần
       tiền chắc chắn thêm khi lên hạng i
       · Σ i·w_i = Σ v_i = P (tổng quỹ)
       · E_N = Σ p_i·v_i = Σ q_i·w_i (chứng minh với ba mức thưởng)
                                │
                                ▼
       Tìm k: 2^N·Σ q_i·w_i = (2C)^D, D = log₂k, w_i là phần của quỹ
       → Σ i·(2C)^{−log₂i}·w_i = (2C)^{D−N}
       → đặt 2C = 1 + ε, xấp xỉ bậc một khi ε gần 0:
         Σ i·w_i·(1 − ε·log₂i) = 1 − (N − D)ε
       → vì Σ i·w_i = 1:
                 N − D = Σ i·w_i·log₂i
       · N − D là số lần nhân đôi "bị mất" do chia thưởng
       · k = X / 2^{N−D}
                                │
                                ▼
       Kiểm tra: w₁ = 154/256, w₂ = 102/256 → N − D = 2 × 102/256 =
       204/256 → k = 256 / 2^{204/256} = 147,35 (so với 147,68 khi
       dùng C = 0,52)
```

### Phần "Key Concepts" — các khái niệm then chốt (trang 345)

```text
       1. Lý thuyết Nhân đôi đánh giá quyết định equity ở đầu và giữa
          giải bằng một "xác suất nhân đôi" C không đổi và số lần nhân
          đôi N cần để gom hết chip; từ đó mô hình hoá kỹ năng và giá
          trị biên của chip
       2. Dạng E = C^N mở rộng được để thấy cơ cấu thưởng dàn trải làm
          giảm tác dụng của kỹ năng
       3. Có thể giải ra cỡ giải hiệu dụng k (phương trình 26.3):
          (2C)^{log₂k} = E_N — cỡ của giải winner-take-all có cùng mức
          điều chỉnh do kỹ năng như giải có cơ cấu thưởng thật
```

## Ba câu hỏi chương này trả lời

1. **Vì sao một người chơi giỏi có thể đúng khi fold một tay có EV chip dương trong giải đấu, và đúng tới mức nào?** Vì chip giải đấu không thay thế được: thua là bị loại và mất mọi cơ hội dùng kỹ năng về sau. Lý thuyết Nhân đôi giả định xác suất nhân đôi C không đổi, nên E = C^N; với C > 0,5, equity là hàm lõm của số chip (E = S^β, β = −log₂C < 1). Trong ví dụ Q♠T♠, call lời 137 chip nhưng với C = 0,5364 thì equity khi call (0,008857 buyin) thấp hơn khi fold (0,009269 buyin). Tuy vậy hiệu ứng nhỏ: muốn từ chối một coinflip 57–43 ở ván đầu, người chơi phải có gần gấp ba equity trung bình, điều chỉ những người giỏi nhất thế giới đạt được.
2. **Chip có giá trị bao nhiêu khi gần vùng có thưởng?** Có thể gấp hàng chục lần giá trị theo tỷ lệ: T100 của người chơi A, lúc đầu đáng 6,67 đô la, đáng ít nhất 210 đô la khi còn 19 người và 18 người có thưởng, vì A có 84% khả năng nhận 250 đô la. Phần giá trị này lấy từ các chồng chip lớn. Chương 27 xây mô hình để định lượng việc này.
3. **Cơ cấu trả thưởng ảnh hưởng tới lợi thế kỹ năng thế nào?** Trả tiền cho nhiều hạng làm giảm tác dụng của kỹ năng, vì người gom hết chip chỉ nhận một phần quỹ. Đo bằng cỡ giải hiệu dụng k thoả (2C)^{log₂k} = E_N: giải 256 người chia đều cho nhất và nhì tương đương giải winner-take-all 128 người; trả 154/102 buyin tương đương khoảng 147–148 người. Công thức xấp xỉ N − D = Σ i·w_i·log₂i tính được k cho mọi cơ cấu thưởng mà không cần biết C.

## Khái niệm cần biết

- **Giải đấu (tournament) và buyin:** thể thức trong đó mọi người trả cùng một phí tham gia (buyin), nhận cùng số chip giải đấu, chơi tới khi một người còn lại; tiền thưởng chia theo thứ tự bị loại. Ví dụ: 200 người, quỹ 20.000 đô la, 300.000 chip, tức 1.500 chip mỗi người. Khác với cash game (bàn tiền thật), nơi chip chính là tiền và có thể mua thêm.
- **Equity chip (chip equity) và equity giải thưởng (prize equity):** equity chip là số chip người chơi giữ; equity giải thưởng là giá trị tiền kỳ vọng của số chip đó trong quỹ thưởng. Ví dụ: T100 có equity chip bằng 1/3.000 tổng chip nhưng equity giải thưởng ít nhất 210 đô la, tức khoảng 1/95 quỹ. Quan trọng vì mục tiêu trong giải là tối đa hoá equity giải thưởng.
- **Winner-take-all:** giải mà người nhất lấy toàn bộ quỹ. Ví dụ: giải 128 người, người nhất nhận 128 buyin. Đây là trường hợp gốc của Lý thuyết Nhân đôi, nơi với người ngang tài, equity tỷ lệ đúng với số chip.
- **Bubble (vùng sát thưởng):** giai đoạn ngay trước khi tất cả người còn lại đều có thưởng. Ví dụ: còn 19 người, 18 người có thưởng. Gần bubble, chồng chip nhỏ có "chiếc ghế đáng giá hơn số chip".
- **Hand-for-hand:** khi gần bubble, các bàn chia bài đồng thời từng ván để không ai cố tình chơi chậm chờ người khác bị loại. Ví dụ: trong ví dụ 19 người, A biết B và C ở bàn khác đang all-in cùng lúc.
- **Xác suất nhân đôi C (chance of doubling up):** xác suất một người chơi nhân đôi chồng chip hiện tại trước khi bị loại; Lý thuyết Nhân đôi giả định C không đổi suốt giải. Ví dụ: người thắng 1 buyin ròng mỗi giải 100 người có C = 0,555. C = 0,5 nghĩa là ngang trình độ chung.
- **Lý thuyết Nhân đôi (Theory of Doubling Up):** mô hình E = C^N, xác suất thắng giải winner-take-all là tích của N lần nhân đôi độc lập. Ví dụ: C = 0,55, giải 128 người: E = 0,55⁷ = 0,0152, gấp 1,95 lần 1/128. Dùng để đánh giá quyết định ở đầu và giữa giải có tính tới kỹ năng.
- **Số mũ β (E = S^β):** β = −log₂C, cho equity là lũy thừa của phần chip S. Ví dụ: C = 0,555 cho β = 0,849; với S = 0,04 (gấp đôi chồng ban đầu trong giải 50 người), E = 0,04^0,849 = 0,065, không phải 0,08. β < 1 nghĩa là chip thêm đáng ít hơn chip đã có.
- **Coinflip:** tình huống all-in hai người có xác suất gần 50–50. Ví dụ: QQ đấu AK khoảng 57–43. Lý thuyết Nhân đôi cho ngưỡng: chấp nhận coinflip ở ván đầu khi xác suất thắng W lớn hơn C.
- **Người thứ ba vào pot (third man in):** người chơi cân nhắc call khi hai người khác đã all-in. Ví dụ: với C = 0,55, cần 30,25% thay vì 25%. Thua là bị loại, thắng thì bớt hai lần nhân đôi.
- **Giải đấu đối kháng (match play):** giải chia cặp đấu loại trực tiếp, mỗi trận thắng là một lần nhân đôi. Ví dụ: 256 người cần thắng 8 trận. Đây là trường hợp Lý thuyết Nhân đôi đúng chính xác, không chỉ là mô hình.
- **Cỡ giải hiệu dụng k (effective tournament size):** cỡ của giải winner-take-all có cùng mức ảnh hưởng của kỹ năng như giải thật với cơ cấu thưởng nhiều hạng; định nghĩa (2C)^{log₂k} = E_N. Ví dụ: 256 người, trả 154/102 buyin: k ≈ 147,7. Quan trọng vì nó cho phép dùng lại công thức E = C^N cho giải có nhiều hạng nhận thưởng.
- **Phần tiền thêm khi lên hạng w_i:** w_i = v_i − v_{i+1}, số tiền chắc chắn có thêm khi về hạng i thay vì hạng i + 1 (w_X = v_X). Ví dụ: v₁ = 154, v₂ = 102 thì w₁ = 52, w₂ = 102 (buyin). Dùng để viết equity thành E_N = Σ q_i·w_i.

## Nội dung chi tiết

### 1. Phần V — Chủ đề khác (Part V: Other Topics, trang 332)

Trang mở Phần V chỉ có câu đề từ của Shakespeare trong *Hamlet* (hồi I, cảnh 5): "There are more things in heaven and earth, Horatio, Than are dreamt of in your philosophy" — "Trên trời dưới đất còn nhiều điều hơn những gì triết lý của anh mơ tới, Horatio." Câu này báo hiệu rằng Phần V bàn những vấn đề nằm ngoài khung lý thuyết gọn gàng của các phần trước (trò chơi hai người, chip là tiền): giải đấu, nơi chip không phải tiền (Chương 26–28); trò chơi nhiều người, nơi cân bằng hai người không còn áp dụng trực tiếp (Chương 29); và cách kết hợp mọi thứ (Chương 30).

### 2. Hai nguyên tắc của giải đấu (phần mở đầu Chương 26, trang 333)

Tác giả mở chương bằng nhận định rằng mảng tăng trưởng lớn nhất của poker trong vài năm trước 2006 chắc chắn là sự bùng nổ của giải đấu: từ các giải World Poker Tour phí 10.000 đô la tới các "siêu giải" online phí 1 đô la hoặc freeroll (giải miễn phí tham gia) với hàng nghìn người. Có nhiều thể thức giải đấu, nhưng về cơ bản đều quy về một cuộc thi poker với hai nguyên tắc then chốt.

**Nguyên tắc thứ nhất: chip giải đấu không thay thế được** — khi người chơi hết chip giải đấu, họ bị loại. Nguyên tắc này dẫn tới những điều chỉnh chiến lược liên quan đến kỹ năng: người có lợi thế so với cả giải nên bỏ qua những lợi thế nhỏ đặt cả chồng chip vào rủi ro, vì họ cho rằng về sau sẽ có những tình huống lợi thế lớn hơn. Họ nên ít sẵn sàng đặt hết chip cho một lợi thế mỏng, vì nếu thua thì không thể mua lại chip bằng tiền mặt như ở cash game. Ngược lại, người có EV âm trong giải nên sẵn sàng all-in hơn trong các tình huống có kỳ vọng chip hơi âm.

Tuy nhiên, theo tác giả, "điều chỉnh do kỹ năng" này đã bị một số người chơi làm quá mức: có giới hạn cho loại tình huống mà người ta có thể bỏ qua và vẫn thật sự có lợi thế như thế về sau. Khi blind tăng dần, càng ngày càng khó tìm được tình huống lời lớn; thỉnh thoảng đối thủ cũng có bài mạnh cùng lúc với ta. Nhưng điều chỉnh này có thật, và có thể định lượng gần đúng. Tác giả mô hình hoá lợi thế kỹ năng như một hiệu ứng đệ quy (nhân đôi lặp lại) và trình bày mô hình ở phần sau của chương. Giải rebuy (cho phép mua lại chip trong một giai đoạn) là ngoại lệ tạm thời của nguyên tắc này, nhưng mọi giải rebuy cuối cùng đều trở thành giải thoả nguyên tắc. (Tác giả hứa quay lại chủ đề mua rebuy "ở phần sau của chương này", nhưng Chương 26 không có mục nào về rebuy; chủ đề này thực ra nằm ở Chương 28, mục "Rebuy Tournaments" — nhận xét của người tổng hợp.)

**Nguyên tắc thứ hai: quỹ thưởng được chia theo một cơ cấu trả thưởng gắn với thứ tự bị loại**, không theo số chip tích lũy. Đây là đặc trưng toán học chính phân biệt giai đoạn cuối giải với cash game. Ở cash game, tối đa hoá EV tiền nghĩa là tối đa hoá EV chip, vì chip là tiền. Trong giải đấu thì không luôn như vậy. Vị trí chip và equity giải thưởng có tương quan mạnh, nhưng sự tách rời giữa **equity chip** (số chip giải đấu một người giữ) và **equity giải thưởng** (EV của số chip đó tính theo quỹ thưởng) có thể đòi hỏi những điều chỉnh đáng kể.

### 3. Ví dụ chồng chip T100 ở 19 người cuối (trang 333–334)

Một giải limit hold'em 200 người, mọi người ngang tài, đã còn 19 người. Các bàn đang chơi hand-for-hand. Hạng 10 đến 18 mỗi hạng nhận 250 đô la, rồi tiền thưởng tăng dần tới 6.000 đô la cho giải nhất; tổng quỹ thưởng 20.000 đô la. Có 300.000 chip trong giải, blind là 300–600.

Ba người có chồng chip cực ngắn. Người chơi A chỉ còn một chip T100 nhưng đang ở button tại bàn của mình. Người chơi B còn T400 và ở vị trí under the gun (người hành động đầu tiên trước flop). Người chơi C còn T500 và cũng ở under the gun.

Ở đầu giải, chip mỗi người giữ đáng một phần quỹ thưởng tỷ lệ với số chip: T100 của A đáng 100/300.000 = 1/3.000 quỹ 20.000 đô la, tức khoảng 6,67 đô la. Nhưng trong tình huống này, chip T100 của A đã tăng giá trị đáng kể. Nếu A fold ván tiếp theo, cả hai đối thủ chồng ngắn sẽ phải all-in vì blind. Giả sử mỗi người có 40% khả năng thắng ván trước (có lẽ là) tay mạnh nhất trong số các tay đấu với họ. A chỉ bị loại ở hạng 19 nếu cả B lẫn C đều thắng, xác suất 0,4 × 0,4 = 0,16; vậy A có 1 − 0,16 = 84% khả năng sống sót vào vùng có thưởng và nhận 250 đô la. Kể cả khi không tính khả năng A thật sự nhân đôi và xây chip thành một chồng, T100 của A đáng ít nhất 0,84 × 250 = 210 đô la — gấp hơn 31 lần giá trị tiên nghiệm 6,67 đô la. Cơ cấu trả thưởng đã cho chip của A thêm giá trị. Giá trị này dĩ nhiên bị lấy đi từ giá trị chip của các chồng lớn: gom toàn bộ chip trong giải chỉ đáng giải nhất 6.000 đô la, tức 30% quỹ (sách ghi 20%, xem khối Lưu ý).

Đây có lẽ là một ví dụ khá cực đoan, nhưng các tình huống cùng tính chất xảy ra ở gần như mọi giải. Trong những trường hợp này, sống sót thật sự có giá trị — tiền thật. Điều này thường đúng với các chồng chip rất nhỏ gần bubble: "chiếc ghế" của họ thật sự đáng giá hơn số chip. Thêm nữa, ở các bậc tăng tiền thưởng trong vùng có thưởng, chồng chip nhỏ có động cơ chơi chặt hơn để leo hạng, dù chỉ đúng tới một mức.

Một số tác giả (sai lầm, theo Chen và Ankenman) đã lấy nguyên lý này và cố mở rộng nó sang đầu giải, lập luận rằng người chơi giỏi nên cố sống sót gần như bằng mọi giá, tránh đối đầu ở đầu giải, cố vào vùng có thưởng rồi mới tiến lên tranh giải nhất. Chen và Ankenman cho rằng quan điểm này hy sinh equity, vì hai lý do:

- Ở đầu giải, equity chip (không tính kỹ năng) và equity giải thưởng gắn chặt với nhau. Đơn giản là không có đủ cơ hội đặt tiền khi là cửa trên rõ rệt để bù lại phần kỳ vọng chip mất đi do lối chơi rụt rè, dễ bị khai thác.
- Kể cả với cơ cấu thưởng phẳng hơn mà nhiều giám đốc giải ưa chuộng (lúc viết sách, 20–25% cho giải nhất), một phần lớn quỹ thưởng tập trung ở ba hạng đầu, và số chip giải đấu là yếu tố dự báo mạnh khả năng về ba hạng đầu.

Tác giả chủ trương một chiến lược có tính tới các điều chỉnh do cơ cấu thưởng và các điều chỉnh mà người giỏi nên làm để giữ khả năng dùng kỹ năng nhiều lần, nhưng thừa nhận rằng các điều chỉnh này khá nhỏ khi vùng có thưởng còn xa. Từ góc nhìn khai thác (exploitive), tác giả còn tìm cách tận dụng việc đối thủ hiểu sai các khái niệm này, nhất là gần vùng có thưởng. Kết quả là nhiều lần bị loại "ngay sát vùng có thưởng" hơn, nhưng cũng nhiều lần về hạng cao hơn và kỳ vọng tổng thể cao hơn.

Mô hình giải đấu nói chung hữu ích nhất khi cố biểu diễn **ánh xạ** (mapping) giữa equity chip và equity giải thưởng. Nếu ánh xạ được equity chip sang equity giải thưởng, ta lại quay về ý tưởng quen thuộc là tối đa hoá EV của quyết định — chỉ khác là không tối đa hoá EV chip mà tối đa hoá EV tiền tương ứng. Mô hình đầu tiên được xét định lượng hiệu ứng thứ nhất (kỹ năng) lên quyết định ở giai đoạn đầu và giữa giải.

### 4. Lý thuyết Nhân đôi: giả định và công thức E = C^N (The Theory of Doubling Up, trang 334–336)

Nhiều người chơi bỏ qua cả những lợi thế lớn ở đầu hoặc giữa giải, tin rằng (gần như chắc chắn là sai) sẽ có những lợi thế còn tốt hơn. Nhưng nếu điều đó thật sự đúng, những người này sẽ có lợi thế khổng lồ so với cả giải tính theo equity; quan sát thực tế không cho thấy như vậy. Dù vậy, hiệu ứng vẫn có; tác giả muốn đo nó và dùng nó làm hướng dẫn ra quyết định chính xác tại bàn.

Có nhiều mô hình để đánh giá giá trị các chồng chip, hữu ích ở các giai đoạn khác nhau. Một số mô hình (như các mô hình ở Chương 27) chủ yếu hữu ích khi người chơi gần hoặc đã vào vùng có thưởng và vấn đề là chia tiền thưởng sao cho mỗi người nhận phần công bằng. Ngược lại, Lý thuyết Nhân đôi được dùng ở giai đoạn đầu và giữa giải làm hướng dẫn ra quyết định.

**Giải winner-take-all.** Trong giải winner-take-all, nếu không tính kỹ năng, equity của một người chơi tỷ lệ với chồng chip. Tác giả đưa thêm một giả định quan trọng:

> *Xác suất một người chơi nhân đôi chồng chip của mình trước khi bị loại là không đổi suốt giải.*

Có một số hiệu ứng tác động lên xác suất nhân đôi trong suốt giải:

- **Hiệu ứng chọn lọc nhẹ:** người mạnh có xu hướng sống lâu hơn, nên giải càng kéo dài thì trung bình cả giải càng mạnh. Điều này làm xác suất nhân đôi của mọi người giảm dần theo tiến trình giải.
- **Blind tăng dần:** blind lớn hơn làm giảm khoảng trống để dùng kỹ năng (hoặc để bộc lộ sự thiếu kỹ năng), nên ép xác suất nhân đôi của mọi người về gần 50%. Ở đầu giải, người giỏi có nhiều cơ hội kiếm chip. Do đó nhân đôi sớm tốt hơn nhân đôi muộn.

Nhưng không hiệu ứng nào đặc biệt mạnh, nên tác giả yên tâm coi giả định là đúng khi mô hình hoá equity giải đấu.

**Công thức.** Xét một giải winner-take-all X người ngang tài, chồng chip ban đầu bằng nhau, và một người chơi cụ thể. Gọi E là xác suất người này thắng giải, C là xác suất (không đổi) nhân đôi chồng chip trước khi bị loại, N là số lần phải nhân đôi để thắng. Khi đó:

```text
E = C^N                                                      (26.1)
```

Ví dụ: có 128 người thì người chơi phải nhân đôi bảy lần, 1 → 2 → 4 → 8 → 16 → 32 → 64 → 128. Vì các lần nhân đôi gần như độc lập với nhau, xác suất nhân đôi bảy lần là C⁷.

Có hai trong ba đại lượng thì tính được đại lượng thứ ba. Ở đầu giải, vì mọi người ngang tài, E = 1/X. Để thắng, người chơi phải tăng chồng chip từ giá trị ban đầu lên X lần, nên số lần nhân đôi thoả X = 2^N, tức N = log₂X. Giải 2 người cần N = 1, giải 128 người cần N = 7. Thay vào:

```text
1/X = C^{log₂X}
log₂(1/X) = (log₂X)(log₂C)
−log₂X   = (log₂X)(log₂C)
log₂C = −1
C = 0,5
```

Đây đúng là điều ta chờ đợi ở giải winner-take-all với mọi người ngang tài: mỗi người có 50% khả năng nhân đôi trước khi bị loại, từ bất kỳ cỡ chồng chip nào. Thay các giá trị X khác (ứng với các cỡ chồng chip khác) cũng dễ thấy giá trị chip đúng là tuyến tính với người ngang tài: chồng chip bằng phần S của tổng thì cần log₂(1/S) lần nhân đôi, và 0,5^{log₂(1/S)} = S.

**Người chơi có kỹ năng khác nhau.** Phương pháp này tổng quát cho người chơi không ngang tài. Xét người chơi A giả định trong giải 100 người, có EV 1 buyin ròng mỗi giải (tức 2 buyin gộp: trả 1, kỳ vọng nhận về 2). Thay giá trị ban đầu:

```text
E = C^N
2/100 = C^{log₂100}
0,02  = C^{6,643856}
C = 0,02^{1/6,643856} = 0,5550
```

Vậy xác suất A nhân đôi chồng chip hiện tại trước khi bị loại là 55,5%. Giờ có thể tính xác suất A thắng giải từ bất kỳ cỡ chồng S nào (S tính bằng số chồng chip ban đầu A đang có) bằng công thức E = C^N, trong đó N là số lần nhân đôi cần để đạt 100 chồng. Với S = 2 (gấp đôi chồng ban đầu), N = log₂(100/2) = log₂50 = 5,644, và

```text
E = 0,5550^{log₂50} = 0,0360
```

Giá trị này lớn hơn giá trị tiên nghiệm của số chip (hai chồng trên 100 chồng, tức 2/100 = 0,02 nếu tính theo tỷ lệ chip), nhưng nhỏ hơn gấp đôi xác suất A thắng giải lúc đầu (2 × 0,02 = 0,04). Nói cách khác, với người giỏi, nhân đôi chồng chip làm xác suất thắng tăng ít hơn gấp đôi: phần chip thứ hai đáng ít hơn phần thứ nhất.

Điều mô hình làm, về bản chất, là cung cấp cách đánh giá các quyết định equity biên trong giải **có tính tới kỹ năng của người ra quyết định**. Phán đoán định tính "tôi có lợi thế so với cả giải, nên tôi phải bảo vệ chip" được định lượng thành một equity điều chỉnh cho mọi cỡ chồng chip, dựa trên các giả định của mô hình. Như vậy mô hình cho một ánh xạ từ equity chip sang equity giải.

### 5. Ví dụ tay Q♠T♠ trên flop K♠8♣2♠ (trang 336–337)

Giải no-limit hold'em 250 người, chồng chip ban đầu 1.500. Blind 75–150. Người chơi B có 3.000 chip, raise lên 450 ở button với Q♠T♠ (Qs Ts). Small blind fold, big blind call. Flop là K♠8♣2♠ (Ks 8c 2s). Big blind check, B bet 500. Big blind check-raise all-in (và có nhiều chip hơn B). B ước equity của mình là 36% (B có draw thùng — flush draw — với hai lá bích trên bàn) và phải quyết định call 2.050 để thắng 4.025.

Người tổng hợp kiểm tra quy mô pot: trước flop pot có 450 (B) + 450 (big blind) + 75 (small blind) = 975. B bet 500, pot 1.475. Big blind đẩy toàn bộ, đặt vào 500 + 2.050 = 2.550 (đủ để B phải dùng hết 2.050 chip còn lại), pot thành 4.025. B call 2.050 thì pot cuối là 6.075.

**Phân tích chỉ dựa trên chip giải đấu** cho thấy call là rõ ràng:

```text
0,36 × 6.075 − 2.050 = 2.187 − 2.050 = +137 chip
```

tức gần một phần mười buyin lời (137/1.500 = 0,091 buyin). Theo pot odds, B chỉ cần 2.050/6.075 = 33,7% để hoà vốn chip.

**Phân tích theo Lý thuyết Nhân đôi.** Giả sử B có lợi thế 3/4 buyin so với cả giải ở đầu giải, tức E gộp = 1,75 buyin trong giải 250 người. Tính C cho B:

```text
1,75/250 = C^{log₂250}
0,007    = C^{7,9658}
C = 0,5364
```

Giờ tính equity E của ba kịch bản. E ở đây là xác suất thắng giải, tức phần của quỹ thưởng; sách gọi đơn vị này là "buyin", nhưng muốn ra buyin phải nhân với 250 (xem khối Lưu ý).

| Kịch bản | Chip của B | Số chồng ban đầu | Equity |
|---|---:|---:|---|
| Call và thắng | 6.075 | 4,05 | E = 0,5364^{log₂(250/4,05)} = 0,024603 |
| Call và thua | 0 | 0 | E = 0 |
| Fold | 2.050 | 1,36667 | E = 0,5364^{log₂(250/1,36667)} = 0,009269 |

Equity của B khi call là 0,36 × 0,024603 + 0,64 × 0 = 0,008857. So với equity khi fold là 0,009269, **call thực ra là sai** khi tính tới lợi thế kỹ năng của B. Phần thiệt khi call là 0,009269 − 0,008857 = 0,000412 tính theo phần của giải, hay khoảng 0,10 buyin nếu nhân với 250.

Người tổng hợp tính thêm ngưỡng: B hoà giữa call và fold khi equity thắng bằng 0,009269/0,024603 = 37,7%, chỉ cao hơn 1,2 điểm phần trăm so với 36%, và cao hơn ngưỡng chip 33,7% khoảng 4 điểm. Điều chỉnh do kỹ năng có thật nhưng không lớn.

### 6. Các hệ quả của Lý thuyết Nhân đôi (trang 337–338)

#### Bài toán coinflip ở ván đầu

Cần xác suất thắng bao nhiêu để chấp nhận một coinflip đặt hết chip ngay ván đầu tiên? Ở đầu giải, E₀ = C^N. Nếu call và nhân đôi, equity thành E₁ = C^{N−1}. Nếu nhận coinflip với xác suất thắng W, equity là W·E₁; nếu từ chối, equity là E₀. Cho hai vế bằng nhau:

```text
C^N = W·C^{N−1}   →   W = C
```

Vậy người chơi bàng quan với việc nhận coinflip khi xác suất thắng coinflip bằng đúng C.

Nhiều người chơi nói họ sẽ từ chối đối đầu QQ đấu AK (57–43) ở đầu giải. Dùng Lý thuyết Nhân đôi, có thể suy ra họ tin equity của mình là bao nhiêu, chẳng hạn trong giải 250 người (khoảng 8 lần nhân đôi). Để từ chối đúng, họ phải có C > 0,57, tức:

```text
E = C^N = 0,57⁸ = 0,01114
```

hay khoảng 2,8 buyin mỗi giải (0,01114 × 250 = 2,79; sách ghi 2,85, xem khối Lưu ý). Muốn từ chối một cuộc đối đầu 57–43 mà không có tiền chết (dead money) trong pot là đúng, người ta phải có gần gấp ba equity trung bình trong giải. Theo quan sát của tác giả, tỷ lệ thắng như vậy trong một giải bình thường sẽ đặt người đó vào hàng những người chơi giỏi nhất thế giới.

#### Người chơi có kỳ vọng âm

Một hệ quả thú vị khác liên quan đến người chơi có kỳ vọng âm. Tác giả đùa rằng độc giả của họ đều là người thắng, nhưng kết quả trung bình của mọi người trong một giải là mất phí tham gia, nên phải có người thua. Lý thuyết Nhân đôi chỉ ra rằng người chơi thua nên sẵn sàng đặt hết chip ngay cả trong tình huống hơi bất lợi. Lý do là người thua nên khuyến khích phương sai, vì đó là cơ hội tốt nhất để họ thắng: người khác càng có nhiều dịp dùng kỹ năng, người thua càng thiệt. Do đó họ nên sẵn sàng đặt hết chip trong tình huống EV bằng 0, thậm chí hơi âm. (Trong ngôn ngữ công thức: C < 0,5 thì β = −log₂C > 1, equity là hàm lồi của số chip; nhận xét của người tổng hợp.)

#### Người thứ ba vào pot all-in

Lý thuyết Nhân đôi cũng có hàm ý quan trọng cho đối đầu nhiều người. Trong poker nói chung, "người thứ ba vào" một cuộc đối đầu all-in cần tay bài khá mạnh; cấu trúc giải đấu làm hiệu ứng này mạnh thêm. Xét một tình huống trên flop: hai người đã all-in với một cược bằng pot, và một người chơi cân nhắc call all-in làm cược thứ ba. Nếu chip tuyến tính, người đó chỉ cần 1/4 khả năng thắng để hoà vốn (đặt 1 đơn vị vào pot tổng cộng 4 đơn vị: pot ban đầu 1, hai cược 1 + 1, và cược của mình 1). Nhưng nếu thắng, số chip của người đó gấp bốn lần so với khi fold — tức bớt được 2 lần nhân đôi. Nếu xác suất nhân đôi ban đầu là, chẳng hạn, 55%, người đó cần

```text
C² = 0,55² = 0,3025 = 30,25%
```

của pot chỉ để hoà vốn tính theo equity, so với 25% tính theo chip. Lý do là rất thường xuyên người đó sẽ bị loại và không còn cơ hội dùng kỹ năng trong tương lai. (Người tổng hợp giải thích "gấp bốn": gọi pot trước cược là P và giả sử chồng chip của người thứ ba cũng bằng P. Nếu fold, người đó giữ P. Nếu call và thắng, người đó nhận pot P cộng ba cược P, tức 4P. Gấp bốn chồng chip nghĩa là bớt log₂4 = 2 lần nhân đôi, nên điều kiện hoà vốn là W·C^{N−2} = C^N, tức W = C².)

### 7. Dạng lũy thừa E = S^β (trang 338)

Ngoài dạng đã trình bày, công thức Lý thuyết Nhân đôi có thể viết theo cách khác. Bắt đầu từ E = C^N. Giả sử chồng chip là S, tính bằng **phần của tổng chip trong giải**. Số lần nhân đôi cần là

```text
N = log₂(1/S) = −log₂S
E = C^{−log₂S}
ln E = (−log₂S)(ln C)
ln E = (ln S)(−log₂C)          (vì log₂S · ln C = ln S · log₂C, cùng bằng ln S · ln C / ln 2)
log_S E = −log₂C
E = S^{−log₂C}
```

Đặt β = −log₂C, ta được

```text
E = S^β                                                      (26.2)
```

Đây là cách phát biểu lại phương trình 26.1 (E = C^N); chỉ khác là bây giờ equity bằng phần chip của ta nâng lên một lũy thừa không đổi.

Minh hoạ của người tổng hợp với C = 0,555 (người chơi A ở mục 4), β = −log₂0,555 = 0,849:

| Phần chip S | Equity theo tỷ lệ (C = 0,5) | Equity E = S^0,849 | Tỷ số E / S |
|---:|---:|---:|---:|
| 0,01 | 0,010 | 0,0200 | 2,00 |
| 0,02 | 0,020 | 0,0360 | 1,80 |
| 0,04 | 0,040 | 0,0649 | 1,62 |
| 0,10 | 0,100 | 0,1414 | 1,41 |
| 0,50 | 0,500 | 0,5550 | 1,11 |

Lợi thế tương đối của người giỏi lớn nhất khi chồng chip nhỏ (còn nhiều lần nhân đôi để dùng kỹ năng) và giảm dần khi chồng chip tiến tới toàn bộ.

### 8. Cơ cấu trả thưởng và cỡ giải hiệu dụng (trang 338–341)

Tác giả tiếp tục đơn giản hoá phép tính và đưa thêm yếu tố ảnh hưởng tới equity: cho tới giờ chỉ xét giải winner-take-all, nay đưa cơ cấu trả thưởng nhiều hạng vào Lý thuyết Nhân đôi.

**Giải đối kháng winner-take-all 256 người.** Xét một giải match play (mỗi trận là đấu một chọi một, người thắng đi tiếp) winner-take-all với 256 người. Equity của một người bằng (256)(C⁸): xác suất nhân đôi tám lần (thắng tám trận; sách ghi nhầm "bảy") nhân với số buyin thắng được. Viết lại:

```text
(256)(C⁸) = 2⁸·C⁸ = (2C)⁸
```

Tổng quát, có thể sửa phương trình E = C^N để biểu diễn equity tính bằng buyin trong quỹ thưởng X buyin:

```text
E_X = X·C^N = 2^N·C^N
E   = (2C)^N         (vì N là số lần nhân đôi cần)
```

**Chia đều cho nhất và nhì.** Xét cùng giải đó nhưng quỹ thưởng chia đều cho nhất và nhì: mỗi người 128 buyin. Equity của người chơi giờ là (128)(C⁷) = (2C)⁷ (chỉ cần thắng 7 trận để vào chung kết; kết quả chung kết không quan trọng). So sánh:

```text
(2C)⁸ > (2C)⁷   ⇔   2C > 1   ⇔   C > 1/2
```

Chia đều giải nhất cho hai người đầu làm equity của người chơi giảm nếu xác suất nhân đôi lớn hơn 1/2, và tăng nếu ngược lại. Điều này hợp lý: thay vì nhận (xác suất thắng trận cuối) × 256, người chơi nhận 128 cố định; nói cách khác, xác suất thắng trận cuối được thay bằng 1/2.

Ví dụ của người tổng hợp với C = 0,52: winner-take-all cho (1,04)⁸ = 1,3686 buyin; chia đều cho (1,04)⁷ = 1,3159 buyin.

Điều này phản ánh rằng ở giải không trả hết tiền cho giải nhất, cơ hội dùng kỹ năng bị giảm, vì người gom được toàn bộ chip chỉ nhận một phần quỹ thưởng. Ở trường hợp thứ hai (chia đều nhất và nhì), người chơi giỏi có ít equity hơn đúng một thừa số 2C. Theo ước lượng equity của Lý thuyết Nhân đôi (ở đây áp dụng chính xác, không chỉ là mô hình, vì giải đấu đối kháng đúng là chuỗi nhân đôi độc lập), hệ số nhân kỹ năng của giải này giống như một giải 128 người thay vì 256.

**Định nghĩa cỡ giải hiệu dụng.** Tác giả gọi khái niệm này là **cỡ giải hiệu dụng** (effective tournament size): định lượng mức độ cơ cấu trả thưởng làm giảm cơ hội dùng kỹ năng. Có thể nói, như một xấp xỉ sát, giải 256 người với giải nhất và nhì bằng nhau có cùng "khoảng trống cho kỹ năng" như giải 128 người winner-take-all. Ký hiệu cỡ giải hiệu dụng (tổng quát) là k, định nghĩa chặt hơn là giá trị k thoả phương trình sau với một cơ cấu thưởng cho trước:

```text
(2C)^{log₂k} = E_N                                           (26.3)
```

trong đó C là xác suất nhân đôi và E_N là số buyin người chơi thắng được trong giải với cơ cấu thưởng thật. Khi đó k là cỡ của giải winner-take-all tương đương (theo Lý thuyết Nhân đôi). Kiểm tra: với giải chia đều, E_N = (2C)⁷ nên log₂k = 7, k = 128.

**Cơ cấu thưởng f và 1 − f.** Giải đấu ít khi chia đều cho nhất và nhì, mà thường cho giải nhất phần lớn hơn. Giả sử giải đối kháng giả định trả phần f của quỹ cho nhất và 1 − f cho nhì. Xác suất về nhất là C⁸; xác suất về nhì là xác suất vào chung kết mà thua, C⁷ − C⁸. Equity:

```text
(tổng quỹ)·[(tiền hạng 1)·P(hạng 1) + (tiền hạng 2)·P(hạng 2)]
= (256)·[f·C⁸ + (1 − f)(C⁷ − C⁸)]
= (256)·C⁷·(f·C + (1 − f)(1 − C))
= (256)·C⁷·(2fC + 1 − C − f)
```

Với người chơi thắng giả định, C sẽ hơi lớn hơn 0,5, chẳng hạn 0,53. Ký hiệu δ là chênh lệch giữa C và 0,5:

```text
δ = C − 0,5
```

Thay C = δ + 0,5: 2f(δ + 0,5) + 1 − (δ + 0,5) − f = 2fδ + f + 0,5 − δ − f = δ(2f − 1) + 1/2. Công thức equity rút gọn thành:

```text
(256)·C⁷·(δ(2f − 1) + 1/2)
```

Công thức gồm ba phần:

- (256)·C⁷ là xác suất người chơi vào chung kết nhân với toàn bộ quỹ thưởng.
- δ(2f − 1) là phần equity "thêm" mà người chơi thắng được nhờ kỹ năng (ở trận chung kết).
- 1/2 là phần cơ bản của người chơi trong quỹ (phần trung bình của hai người vào chung kết).

**Tìm k.** Gọi d = log₂k, số lần nhân đôi cần trong giải winner-take-all cỡ k. Tồn tại một giải winner-take-all sao cho (2C)^d = E_N. Ở đây E_N là biểu thức equity trên, nên:

```text
(2C)^d = (256)·C⁷·(δ(2f − 1) + 1/2)
(2C)^{d−7} = 2·(δ(2f − 1) + 1/2)                (chia hai vế cho (2C)⁷ = 128·C⁷)
(d − 7)·ln(2C) = ln(2·(δ(2f − 1) + 1/2))
d − 7 = ln(2·(δ(2f − 1) + 1/2)) / ln(2C)
d = ln(2·(δ(2f − 1) + 1/2)) / ln(2C) + 7
k = 2^d
```

Giả sử f = 154/256 và C = 0,52 (δ = 0,02). Khi đó 2f − 1 = 52/256 = 0,203125, và

```text
d = ln(2·(0,02 × 0,203125 + 0,5)) / ln(1,04) + 7
  = ln(1,008125) / ln(1,04) + 7
  = 0,0080922 / 0,0392207 + 7 = 7,2063
k = 2^d = 147,68
```

(Người tổng hợp dựng lại phép tính vì công thức trong sách bị in hỏng; kết quả 147,68 khớp.)

Lưu ý k phụ thuộc vào C đã dùng. Tuy nhiên, hoá ra k khá ít nhạy với C, miễn là C nằm trong phạm vi thông thường. Người tổng hợp tính lại để minh hoạ:

| C | 0,51 | 0,52 | 0,53 | 0,55 | 0,60 |
|---|---:|---:|---:|---:|---:|
| k | 147,52 | 147,68 | 147,84 | 148,16 | 148,92 |

Tác giả sẽ dùng tính chất ít nhạy này để mở rộng sang cơ cấu thưởng nhiều hạng hơn.

Như vậy cỡ giải hiệu dụng ở đây thực ra nhỏ hơn cỡ thật khoảng một trăm người (256 − 147,68 = 108,3), chỉ vì cơ cấu thưởng bị chia ra. Cỡ giải hiệu dụng này được dùng làm cỡ giải trong các phương trình của Lý thuyết Nhân đôi, và số hạng E phải được nhân với số buyin đó (k) để ra equity đúng.

**Ví dụ kiểm tra.** Tìm equity của một người chơi có C = 0,53 đã thắng bốn trận đầu (nên còn cần 4 lần nhân đôi để thắng; người này giờ có S = 16 chồng ban đầu):

```text
k·E = C^{log₂(k/S)}
(147,68)·E = (0,53)^{log₂(147,68/16)} = 0,53^{3,206} = 0,13060
E = 19,287 buyin
```

(Ở đây "E" trong dòng cuối đã là k·E, tức equity tính bằng buyin.) Kiểm tra trực tiếp:

- Xác suất vào chung kết (thắng 3 trận nữa): 0,53³ = 0,14888.
- Xác suất thắng trận chung kết: 0,53.

```text
(0,14888)·[(0,53)(154) + (0,47)(102)] = 0,14888 × (81,62 + 47,94) = 0,14888 × 129,56 = 19,288 buyin
```

Hai cách cho cùng kết quả (chênh 0,001 do làm tròn).

### 9. Tổng quát hoá cho mọi cơ cấu trả thưởng (trang 341–345)

Phần lớn giải đấu không phải đối kháng, và phần lớn không chỉ trả cho hai hạng. Tuy nhiên, nếu chấp nhận một số giả định về khả năng bị loại ở các hạng khác nhau, có thể tổng quát kết quả để tìm cỡ giải hiệu dụng (và nhờ đó tạo ra điều chỉnh kỹ năng phù hợp) cho mọi cơ cấu thưởng.

**Giả định:**

> *Xác suất một người chơi về hạng i bằng xác suất người đó nhân đôi tới chồng chip bằng 1/i tổng chip trong giải, trừ đi xác suất về một hạng cao hơn.*

(Sách dùng chữ N cho số hạng ở đây; người tổng hợp đổi thành i để không trùng với N là số lần nhân đôi.) Vậy xác suất về nhất là xác suất nhân đôi tới toàn bộ chip. Xác suất về nhì là xác suất nhân đôi tới một nửa tổng chip trừ xác suất về nhất. Xác suất về ba là xác suất nhân đôi tới một phần ba tổng chip trừ xác suất về nhất hoặc nhì, và cứ thế. Chuỗi này đúng là có tổng bằng một: dù không bắt buộc phải nhân đôi tới 1/i tổng chip mới về hạng i, đây là một xấp xỉ hợp lý.

Tác giả đánh dấu phần sau là "hơi khó", người đọc có thể bỏ qua.

**Equity theo xác suất từng hạng.** Equity (tính bằng buyin) là

```text
E_N = Σ_{i=1}^{X} p_i·v_i
```

trong đó p_i là xác suất về hạng i, v_i là tiền thưởng hạng i, X là tổng số người. Xác suất về mỗi hạng bằng xác suất nhân đôi tới lượng chip tương ứng trừ xác suất nhân đôi tới lượng chip của hạng cao hơn kế tiếp:

```text
p_i = C^{log₂(X/i)} − C^{log₂(X/(i−1))}
```

Đặt N = log₂X (số lần nhân đôi nếu là giải winner-take-all), ta có log₂(X/i) = N − log₂i, nên:

```text
p_i = C^{N − log₂i} − C^{N − log₂(i−1)}     với i > 1;   p₁ = C^N
```

**Xác suất cộng dồn.** Định nghĩa q_i là xác suất về trong top i (sách in sai giới hạn tổng, xem khối Lưu ý):

```text
q_i = Σ_{j=1}^{i} p_j
```

q₁ là xác suất về nhất, q₂ là xác suất về nhất hoặc nhì, và cứ thế. Thay p_i vào, các số hạng triệt tiêu dây chuyền:

```text
q_i = C^{N − log₂i}
```

**Phần tiền thêm khi lên hạng.** Gọi P là tổng quỹ thưởng: P = Σ_{i=1}^{X} v_i. Gọi w_i là phần tiền chắc chắn tăng thêm khi về hạng i thay vì hạng i + 1:

```text
w_i = v_i − v_{i+1},   với quy ước riêng w_X = v_X
```

Ta có đẳng thức

```text
P = Σ_{i=1}^{X} i·w_i
```

vì

```text
Σ i·w_i = Σ i·(v_i − v_{i+1})
        = Σ i·v_i − Σ i·v_{i+1}
        = Σ i·v_i − Σ (i − 1)·v_i         (đổi chỉ số ở tổng thứ hai)
        = Σ v_i = P
```

Nghĩa là: tổng quỹ thưởng bằng tổng, theo mọi i, của số tiền đảm bảo khi về hạng i hoặc cao hơn nhân với số người về ở đó (i người).

**Equity theo xác suất cộng dồn.** Ngoài E_N = Σ p_i·v_i (giá trị mỗi hạng nhân xác suất về hạng đó), còn có thể viết

```text
E_N = Σ_{i=1}^{X} q_i·w_i
```

tức equity bằng xác suất về hạng i hoặc cao hơn nhân với tiền tăng thêm được đảm bảo khi lên tới hạng đó, cộng lại. Chứng minh với ba mức thưởng v₁, v₂, v₃ và xác suất p₁, p₂, p₃ (cách làm tổng quát được cho nhiều mức hơn): q₁ = p₁, q₂ = p₁ + p₂, q₃ = p₁ + p₂ + p₃, và w₁ = v₁ − v₂, w₂ = v₂ − v₃, w₃ = v₃ (sách gọi các w ở đây là g). Khi đó

```text
q₁w₁ + q₂w₂ + q₃w₃
= p₁(v₁ − v₂) + (p₁ + p₂)(v₂ − v₃) + (p₁ + p₂ + p₃)v₃
= p₁v₁ + p₂v₂ + p₃v₃
```

**Phương trình xác định k.** Ta cần giá trị k sao cho equity thật bằng equity của giải winner-take-all cỡ k. Với w_i là **phần của quỹ thưởng** (để Σ i·w_i = 1) và quỹ gồm X = 2^N buyin, equity tính bằng buyin là 2^N·Σ q_i·w_i, nên theo (26.3):

```text
2^N · Σ q_i·w_i = (2C)^D,      D = log₂k
```

(Sách nói phương trình này "giả định w_i tính bằng buyin chứ không phải phần của quỹ"; điều đó ngược với bước rút gọn phía sau, xem khối Lưu ý. Phương trình gốc trong sách bị in hỏng; người tổng hợp dựng lại từ các bước tiếp theo.) Thay q_i = C^{N − log₂i} và biến đổi:

```text
2^N · Σ C^{N − log₂i}·w_i = (2C)^D
Σ (2C)^N · C^{−log₂i}·w_i = (2C)^D
Σ C^{−log₂i}·w_i = (2C)^{D − N}
Σ i·(2C)^{−log₂i}·w_i = (2C)^{D − N}
```

Bước cuối dùng C^{−log₂i} = (2C)^{−log₂i}·2^{log₂i} = i·(2C)^{−log₂i}.

**Xấp xỉ khi C gần 0,5.** Dùng tính chất k ít nhạy với C: chọn C rất gần 0,5. Theo quy ước, ký hiệu ε là hai lần khoảng cách giữa C và 0,5, tức 2C = 1 + ε (giá trị C = 0,5 chính xác là điểm gián đoạn vì phải chia cho 0: khi 2C = 1, mọi lũy thừa của 2C đều bằng 1 và phương trình không xác định được D). Phương trình thành

```text
Σ i·(1 + ε)^{−log₂i}·w_i = (1 + ε)^{D − N}
```

Khi ε đủ gần 0, xấp xỉ bậc một (1 + ε)^x ≈ 1 + xε:

```text
Σ i·w_i·(1 − (log₂i)·ε) = 1 − (N − D)·ε
```

Vì Σ i·w_i bằng 1 (w_i là phần của quỹ), các số hạng không chứa ε triệt tiêu, chia hai vế cho −ε được:

```text
Σ_{i=1}^{X} i·w_i·log₂i = N − D
```

N − D có thể hiểu là số lần nhân đôi "bị mất" khỏi giải khi đưa cơ cấu thưởng vào. Để tìm cỡ giải hiệu dụng, chia X cho 2^{N−D}: k = X / 2^{N−D}. Công thức đơn giản hơn nhiều này dùng được cho mọi cơ cấu thưởng.

**Kiểm tra với giải đã xét.** w₁ = 154/256, w₂ = 102/256 (phần của quỹ; hạng 1 chỉ có log₂1 = 0 nên không đóng góp):

```text
N − D = 1 × (154/256) × 0 + 2 × (102/256) × log₂2 = 204/256 = 0,797
k = 256 / 2^{204/256} = 147,35      (D = log₂k)
```

Chênh lệch nhỏ so với 147,68 là do lần đầu tính giải này tác giả chọn C = 0,52 thay vì C sát 0,5. (Bảng ở mục 8 cho thấy khi C giảm về 0,51, k giảm về 147,5, tiến dần tới 147,35.)

Minh hoạ thêm của người tổng hợp: một giải 64 người trả 50% / 30% / 20% cho ba hạng đầu có w₁ = 0,2, w₂ = 0,1, w₃ = 0,2, nên N − D = 2 × 0,1 × 1 + 3 × 0,2 × log₂3 = 0,2 + 0,951 = 1,151, và k = 64 / 2^{1,151} = 28,8 — giải 64 người với cơ cấu này chỉ cho người giỏi khoảng trống dùng kỹ năng như một giải winner-take-all 29 người.

### 10. Các khái niệm then chốt (Key Concepts, trang 345)

- Lý thuyết Nhân đôi cho phép đánh giá các quyết định equity ở đầu và giữa giải bằng cách dùng một "xác suất nhân đôi" không đổi và tìm số lần nhân đôi cần để gom hết chip. Với hai đại lượng này, có thể mô hình hoá hiệu quả kỹ năng trong giải và hình dung giá trị biên của chip.
- Dạng E = C^N của Lý thuyết Nhân đôi có thể tinh chỉnh thêm để hiểu ảnh hưởng của cơ cấu thưởng phẳng lên kỹ năng. Khi tiền được trả cho hạng khác ngoài hạng nhất, tác dụng của kỹ năng giảm đi.
- Có thể giải ra cỡ giải hiệu dụng (phương trình 26.3: (2C)^{log₂k} = E_N), là cỡ của một giải winner-take-all có điều chỉnh kỹ năng giống giải có cơ cấu thưởng nhiều hạng của ta.

## Luận điểm cốt lõi

### Mệnh đề

Trong giải đấu, giá trị của chip không tỷ lệ với số chip. Ở đầu và giữa giải, độ lệch chủ yếu đến từ kỹ năng: người giỏi có equity lõm theo chip (E = S^β, β < 1), nên nên từ chối một số tình huống có EV chip dương nhỏ; nhưng độ lệch này nhỏ, và lối chơi "sống sót bằng mọi giá" ở đầu giải là sai. Cơ cấu thưởng nhiều hạng làm giảm tác dụng của kỹ năng, đo được bằng cỡ giải hiệu dụng.

### Giả định

- Xác suất nhân đôi C không đổi suốt giải (bỏ qua hiệu ứng chọn lọc và blind tăng).
- Các lần nhân đôi độc lập với nhau.
- Mọi đối thủ được gộp thành "cả giải"; không xét cấu trúc bàn, vị trí, cỡ chồng của đối thủ.
- Khi tổng quát hoá: xác suất về hạng i bằng xác suất nhân đôi tới 1/i tổng chip trừ xác suất về hạng cao hơn; C gần 0,5 để xấp xỉ bậc một.

### Cơ chế

1. Từ lợi thế kỹ năng (equity gộp E₀ tính bằng phần của quỹ) và cỡ giải X, giải ra C = E₀^{1/log₂X}.
2. Với mỗi kịch bản của một quyết định, tính số chồng chip S sau kịch bản và equity C^{log₂(X/S)}.
3. Lấy kỳ vọng theo xác suất các kịch bản và chọn hành động có equity giải lớn nhất.
4. Nếu giải có nhiều hạng nhận thưởng, thay X bằng cỡ giải hiệu dụng k = X / 2^{Σ i·w_i·log₂i}.

### Bằng chứng và ví dụ tác giả đưa ra

- T100 ở 19 người cuối: 6,67 đô la theo tỷ lệ, ít nhất 210 đô la theo xác suất vào vùng có thưởng 84%.
- Người chơi thắng 1 buyin ròng mỗi giải 100 người: C = 0,555; với hai chồng chip, E = 0,0360 < 0,04.
- Q♠T♠ trên K♠8♣2♠: +137 chip khi call, nhưng fold tốt hơn (0,009269 so với 0,008857) khi C = 0,5364.
- Từ chối QQ đấu AK 57–43 đòi hỏi equity khoảng 2,8 buyin mỗi giải.
- Người thứ ba vào pot all-in: cần 30,25% thay vì 25% khi C = 0,55.
- Giải đối kháng 256 người: chia đều cho hai hạng đầu tương đương 128 người; trả 154/102 buyin tương đương k = 147,68 (C = 0,52) hay 147,35 (công thức xấp xỉ); kiểm tra trực tiếp 19,288 buyin.

### Kết luận và hàm ý cho người chơi

- Ở đầu giải, chơi gần như cash game: nhận các lợi thế chip rõ ràng; chỉ từ chối các tình huống biên rất mỏng (chênh vài điểm phần trăm so với pot odds).
- Mức điều chỉnh tăng theo lợi thế kỹ năng của mình (C càng lớn, β càng nhỏ) và theo số lần nhân đôi còn lại.
- Người chơi yếu hơn mặt bằng nên tìm phương sai, chấp nhận coinflip sớm.
- Cẩn thận hơn khi là người thứ ba vào một pot đã có hai người all-in.
- Giải trả thưởng dàn trải làm giảm giá trị của kỹ năng; người giỏi được lợi nhiều nhất ở giải trả tập trung cho hạng đầu.
- Gần bubble, chồng chip nhỏ có giá trị vượt xa tỷ lệ chip; việc khai thác đối thủ hiểu sai điều này là một nguồn lợi nhuận.

### Trong ngôn ngữ xác suất và lý thuyết hữu dụng

Lý thuyết Nhân đôi là một mô hình chuỗi phép thử Bernoulli độc lập: thắng giải là thành công liên tiếp N lần với xác suất C mỗi lần, nên P(thắng) = C^N. Viết theo phần chip, E = S^β là một hàm hữu dụng lũy thừa (dạng CRRA, hệ số ngại rủi ro tương đối không đổi 1 − β) của tài sản S, và chính cấu trúc trò chơi (không mua lại chip, người giỏi còn nhiều lần dùng kỹ năng) tạo ra sự "ngại rủi ro" đó, không phải sở thích cá nhân (nhận xét của người tổng hợp). Điều kiện chấp nhận coinflip W = C và điều kiện người thứ ba W = C² là các điểm bàng quan (indifference point) của hàm hữu dụng này. Cỡ giải hiệu dụng là một phép đổi biến để đưa bài toán nhiều hạng về bài toán một hạng có cùng "lượng kỹ năng" (cùng số mũ), và công thức N − D = Σ i·w_i·log₂i là khai triển bậc một theo ε = 2C − 1.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| tournament | giải đấu | thể thức chơi tới khi bị loại, thưởng theo thứ hạng |
| buyin | buyin, phí tham gia | số tiền trả để vào giải; đơn vị đo equity trong giải |
| prize pool | quỹ thưởng | tổng tiền thưởng chia cho các hạng |
| payout structure | cơ cấu trả thưởng | cách quỹ được chia cho các hạng |
| winner-take-all | người nhất lấy hết | toàn bộ quỹ cho hạng nhất |
| freeroll | freeroll | giải miễn phí tham gia nhưng có thưởng |
| rebuy tournament | giải rebuy | giải cho phép mua thêm chip trong một giai đoạn |
| ring game / cash game | cash game, bàn tiền thật | chip là tiền, có thể mua thêm |
| chip equity | equity chip | số chip giải đấu đang giữ |
| prize equity | equity giải thưởng | giá trị tiền kỳ vọng của số chip trong quỹ |
| equity | equity | phần giá trị kỳ vọng của người chơi (trong pot hoặc quỹ) |
| mapping | ánh xạ | quy tắc đổi equity chip thành equity giải thưởng |
| in the money | vào vùng có thưởng | còn trong nhóm được trả thưởng |
| bubble | bubble, vùng sát thưởng | giai đoạn ngay trước khi mọi người còn lại đều có thưởng |
| hand-for-hand | hand-for-hand | các bàn chia đồng thời từng ván gần bubble |
| short-stacked | chồng chip ngắn | có rất ít chip so với blind |
| under the gun | under the gun | vị trí hành động đầu tiên trước flop |
| button | button | vị trí người chia bài, hành động sau cùng sau flop |
| blind (small blind, big blind) | blind | cược bắt buộc trước khi chia bài |
| all-in | all-in | đặt toàn bộ chip |
| check-raise | check-raise | check rồi raise khi đối thủ bet |
| flop | flop | ba lá bài chung đầu tiên |
| pot odds | pot odds | tỷ lệ giữa số phải call và pot sẽ thắng |
| dead money | tiền chết | tiền trong pot không thuộc người còn tranh pot |
| coinflip | coinflip | đối đầu all-in gần 50–50 |
| bust / bust out | bị loại | mất hết chip |
| edge | lợi thế | phần kỳ vọng dương so với đối thủ |
| skill adjustment | điều chỉnh do kỹ năng | thay đổi chiến lược vì muốn giữ cơ hội dùng kỹ năng |
| Theory of Doubling Up | Lý thuyết Nhân đôi | mô hình E = C^N |
| chance of doubling up (C) | xác suất nhân đôi | xác suất gấp đôi chồng chip trước khi bị loại |
| number of doubles (N) | số lần nhân đôi | log₂ của số chồng chip cần gom |
| selection effect | hiệu ứng chọn lọc | người mạnh sống lâu hơn nên mặt bằng mạnh dần |
| match play | giải đấu đối kháng | đấu loại trực tiếp từng cặp |
| effective tournament size (k) | cỡ giải hiệu dụng | cỡ giải winner-take-all có cùng ảnh hưởng của kỹ năng |
| third man in | người thứ ba vào pot | người call khi hai người đã all-in |
| expected value (EV) | giá trị kỳ vọng | trung bình có trọng số xác suất của kết quả |
| variance | phương sai | độ dao động của kết quả |
| a priori | tiên nghiệm | trước khi có thông tin của tình huống |
| marginal decision | quyết định biên | quyết định mà hai lựa chọn có giá trị rất gần nhau |
| indifference point | điểm bàng quan | ngưỡng mà hai lựa chọn có cùng giá trị |
| first-order approximation | xấp xỉ bậc một | giữ số hạng tuyến tính của khai triển |

## Câu nói đáng nhớ

> "There are more things in heaven and earth, Horatio, Than are dreamt of in your philosophy." — William Shakespeare, *Hamlet*, đề từ Phần V
>
> *Dịch: Trên trời dưới đất còn nhiều điều hơn những gì triết lý của anh mơ tới, Horatio.*
>
> Phần V bàn những vấn đề vượt ra ngoài khung lý thuyết của bốn phần trước.

> "Tournament chips are irreplaceable - once all a player's tournament chips are gone, the player is eliminated from the tournament." — phần mở đầu chương
>
> *Dịch: Chip giải đấu không thay thế được — khi hết chip, người chơi bị loại khỏi giải.*
>
> Nguyên tắc thứ nhất, gốc của mọi điều chỉnh do kỹ năng.

> "This 'skill adjustment,' however, has been far overdone by some players." — phần mở đầu chương
>
> *Dịch: Tuy nhiên, "điều chỉnh do kỹ năng" này đã bị một số người chơi làm quá mức.*
>
> Tác giả thừa nhận hiệu ứng nhưng phản đối việc phóng đại nó.

> "Their chair is actually worth more than their chips." — ví dụ 19 người cuối
>
> *Dịch: Chiếc ghế của họ thật sự đáng giá hơn số chip của họ.*
>
> Gần bubble, việc sống sót tự nó có giá trị bằng tiền.

> "In this case, however, we do not maximize chip EV, but instead the corresponding cash EV." — phần mở đầu chương
>
> *Dịch: Tuy nhiên, trong trường hợp này ta không tối đa hoá EV chip mà tối đa hoá EV tiền tương ứng.*
>
> Mục tiêu đúng trong giải đấu.

> "The chance of doubling a certain player's chip stack before that player busts is constant throughout the tournament." — mục "The Theory of Doubling Up"
>
> *Dịch: Xác suất một người chơi nhân đôi chồng chip trước khi bị loại là không đổi suốt giải.*
>
> Giả định nền của toàn bộ mô hình.

> "So you are indifferent to accepting a coinflip if your chance of winning the coinflip is equal to C." — mục "The Theory of Doubling Up"
>
> *Dịch: Vậy bạn bàng quan với việc nhận coinflip nếu xác suất thắng coinflip bằng đúng C.*
>
> Một ngưỡng quyết định gọn, dễ dùng tại bàn.

> "When money is given to a place other than 1st, the effect of skill is diminished." — Key Concepts
>
> *Dịch: Khi tiền được trả cho hạng khác ngoài hạng nhất, tác dụng của kỹ năng giảm đi.*
>
> Ý chính của phần cỡ giải hiệu dụng.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương biến một lời khuyên mơ hồ và phổ biến trong cộng đồng ("người giỏi nên tránh coinflip đầu giải") thành một mô hình có một tham số, kiểm tra được bằng số. Kết quả đáng chú ý nhất là tính "tự kiểm tra" của mô hình: nếu từ chối QQ đấu AK là đúng, người chơi phải có equity gần gấp ba trung bình — một điều kiện có thể so với dữ liệu thực tế về tỷ lệ thắng giải. Ví dụ Q♠T♠ cho thấy quy mô thật của điều chỉnh: ngưỡng hoà vốn chỉ dịch từ 33,7% (chip) lên khoảng 37,7% (equity giải), tức vài điểm phần trăm. Phần cỡ giải hiệu dụng là một đóng góp ít thấy ở sách khác: một công thức đóng N − D = Σ i·w_i·log₂i tính được chỉ từ cơ cấu thưởng.

### Những chỗ đơn giản hoá

- **C không đổi:** tác giả thừa nhận hai hiệu ứng làm C thay đổi (chọn lọc, blind tăng) và cho rằng chúng yếu. Thực tế, lợi thế ở giai đoạn đầu (blind nhỏ, nhiều chip sâu) thường lớn hơn hẳn giai đoạn cuối (chơi jam-or-fold), nên C có lẽ giảm theo thời gian; mô hình vì vậy có thể phóng đại giá trị của việc "giữ chip để dùng kỹ năng sau" (nhận xét của người tổng hợp).
- **Nhân đôi là "tất cả hoặc không":** mô hình chỉ biết hai trạng thái, nhân đôi hoặc bị loại; giải thật có chồng chip dao động liên tục, và có thể mất một nửa chip mà vẫn sống.
- **Lợi thế được đo bằng một số duy nhất (ROI):** thực tế lợi thế khác nhau theo bàn, theo cỡ chồng, theo giai đoạn.
- **Ví dụ 19 người:** giả định mỗi người chồng ngắn thắng 40% và bỏ qua khả năng A mất blind hay bị loại sau đó; con số 210 đô la là cận dưới thô.
- **Giả định "về hạng i khi nhân đôi tới 1/i tổng chip"** chỉ là xấp xỉ, như tác giả thừa nhận; Chương 27 sẽ đưa các mô hình chi tiết hơn cho giai đoạn cuối.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- Cơ cấu thưởng của các giải lớn ngày nay thường còn phẳng hơn mức "20–25% cho giải nhất" mà sách nêu (nhiều giải trả cho 15% người tham gia), nên theo chính công thức của chương, cỡ giải hiệu dụng nhỏ đi nhiều so với cỡ thật.
- Các công cụ tính ICM (mô hình chuyển chip thành tiền ở Chương 27) và các solver giải đấu hiện đại đã tích hợp cả cơ cấu thưởng lẫn chiến lược gần cân bằng cho giai đoạn cuối; một số công cụ còn thêm "hiệu chỉnh tương lai" (future game simulation) để tính tới kỹ năng và blind tăng — tức là đúng vấn đề mà Lý thuyết Nhân đôi cố định lượng.
- Mặt bằng chung của giải online mạnh hơn nhiều so với 2006, nên C của người giỏi gần 0,5 hơn và điều chỉnh do kỹ năng còn nhỏ hơn.

### Liên hệ các chương khác

- [C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md): tối đa hoá giá trị kỳ vọng — ở đây là kỳ vọng tiền chứ không phải chip.
- [C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md): pot odds, ngưỡng chip 33,7% trong ví dụ Q♠T♠.
- [C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md): giai đoạn cuối giải, khi blind lớn và lựa chọn chủ yếu là jam hoặc fold.
- [C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md), [C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md): mất hết vốn là không thể đảo ngược — cùng ý với "chip không thay thế được".
- [C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md): hàm hữu dụng logarit và việc từ chối một số cược có EV dương; E = S^β là phiên bản lũy thừa.
- [C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md): đánh đổi kỳ vọng và phương sai.
- [C27-giai-dau-phan-2-chip-khong-phai-tien.md](C27-giai-dau-phan-2-chip-khong-phai-tien.md): các mô hình chuyển chip thành tiền gần vùng có thưởng (nguyên tắc thứ hai).
- [C28-giai-dau-phan-3-poker-van-la-poker.md](C28-giai-dau-phan-3-poker-van-la-poker.md): áp dụng vào các quyết định cụ thể trong giải.
- [C29-tro-choi-nhieu-nguoi.md](C29-tro-choi-nhieu-nguoi.md): đối đầu nhiều người, liên quan tới hệ quả "người thứ ba vào pot".

### Vận dụng

- **Cho người chơi giải đấu:** trước khi từ chối một tình huống có EV chip dương ở đầu giải, ước lượng C của mình một cách trung thực (từ ROI dài hạn: C = (1 + ROI)/X lấy căn bậc log₂X) và tính lại; với phần lớn người chơi, C chỉ khoảng 0,51–0,53, và điều chỉnh gần như không đáng kể. Gần bubble, chuyển sang các mô hình của Chương 27.
- **Cho người làm tài chính và đầu tư:** nguyên tắc "vốn không thay thế được" xuất hiện ở mọi quỹ có giới hạn lỗ hay nhà giao dịch bị cắt vốn khi sụt giảm quá ngưỡng: một khoản đầu tư có kỳ vọng dương nhỏ có thể không đáng làm nếu thua sẽ mất quyền chơi tiếp, khi người đầu tư có lợi thế lặp lại được. Ngược lại, như "người chơi kỳ vọng âm" của chương, người quản lý đang thua xa mục tiêu có động cơ tăng rủi ro — một vấn đề động cơ (risk-shifting) quen thuộc trong quản trị quỹ.
- **Cho người thiết kế cơ chế thưởng:** cơ cấu thưởng dàn trải (nhiều người nhận một phần) làm giảm phần thưởng cho năng lực vượt trội; công thức cỡ giải hiệu dụng cho cách đo mức giảm đó. Cùng ý tưởng áp dụng cho các cuộc thi, chương trình thưởng bán hàng theo thứ hạng.

# Chương 23 — Thêm bất định: rủi ro phá sản khi tỷ lệ thắng bất định (Adding Uncertainty: Risk of Ruin with Uncertain Win Rates)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 23 "Adding Uncertainty: Risk of Ruin with Uncertain Win Rates", trang 307–317 (bắt đầu ở nửa dưới trang 307, sau phần "Key Concepts" của Chương 22).
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương 22 ([C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md)) dựng mô hình rủi ro phá sản (risk of ruin) với một tỷ lệ thắng (win rate) đã biết chắc, và cho công thức của phân phối chuẩn R(b) = exp(−2μb/σ²). Chương 3 ([C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md)) đã dạy cách ước lượng tham số, sai số chuẩn, khoảng tin cậy và cảnh báo về việc chỉ áp phân phối chuẩn lên kết quả quan sát mà bỏ qua phân phối tiên nghiệm (cách nhìn Bayes). Chương 23 ghép hai thứ đó: thay một tỷ lệ thắng duy nhất bằng một phân phối chuẩn của các tỷ lệ thắng khả dĩ quanh giá trị quan sát, rồi lấy kỳ vọng của rủi ro phá sản theo phân phối đó, được công thức "rủi ro phá sản dưới bất định" (RoRU). Phần cuối chương bàn các lý do thực tế khiến người chơi phóng đại tỷ lệ thắng (thuế, chi phí sinh hoạt, mức thua chịu được), chuẩn bị cho Chương 24 ([C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md)) về việc xuống mức cược thấp hơn và tiêu chuẩn Kelly, và Chương 25 ([C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md)) về danh mục trò chơi và tài trợ.
**Ý chính:** **Vì tỷ lệ thắng thật không bao giờ biết chắc mà chỉ ước lượng được với sai số chuẩn lớn, rủi ro phá sản đúng đắn là trung bình có trọng số của rủi ro phá sản trên mọi tỷ lệ thắng khả dĩ; với phân phối tỷ lệ thắng chuẩn quanh giá trị quan sát w, độ lệch chuẩn σ_w = s/√N, kết quả có dạng đóng RoRU = R(w,b)·exp(2b²σ_w²/σ⁴)·Φ((w − 2bσ_w²/σ²)/σ_w) + Φ(−w/σ_w), và nó luôn lớn hơn đáng kể rủi ro phá sản "đơn giản" khi dữ liệu ít.** Ví dụ mở đầu: người chơi có tỷ lệ thắng thật 1 bet/giờ, độ lệch chuẩn 12 bet/giờ, chơi 100 giờ sẽ quan sát tỷ lệ thắng dao động rất rộng; với bankroll 200 bet, rủi ro phá sản là 100% nếu tỷ lệ thắng là 0, chỉ 0,387% nếu là 2 bet/giờ, 10,84% nếu 0,8 và 6,22% nếu 1 — gần như toàn bộ khoảng 0–100%. Số hạng cuối Φ(−w/σ_w) là xác suất người chơi thực chất là người thua; không bankroll nào bảo vệ được khỏi phần rủi ro này. Hai hình (bankroll 100 và 300 bet, độ lệch chuẩn 10 bet) cho thấy khi σ_w lớn, rủi ro ở tỷ lệ thắng thấp giảm xuống dưới 100% (có thể chỉ là kém may), nhưng rủi ro ở tỷ lệ thắng trung bình và cao tăng lên nhiều. Mục "Bankroll Considerations" nêu bốn lý do người chơi phóng đại tỷ lệ thắng (thành công ban đầu, cái tôi, thông tin sai, điều kiện trò chơi thay đổi) và ba lý do "tỷ lệ thắng" và "bankroll" dùng trong công thức khác với con số thô: thuế (có thể giảm tỷ lệ thắng 30% trở lên ở Mỹ), bankroll hiệu dụng là số tiền sẵn sàng thua ở một mức cược (ví dụ $12.000 nhưng sẽ bỏ sau khi thua $6.000 thì chỉ có 150 bet ở mức $20-40), và chi phí sinh hoạt phải trừ khỏi tỷ lệ thắng như một khoản "lương". Ví dụ người chơi 40.000 ván thắng 2,5 bet/100 ván, độ lệch chuẩn 18 bet/100 ván, bankroll 300 bet: RoRU 3,67% so với rủi ro đơn giản 0,98%; khi rút 1 bet/100 ván để sống, tỷ lệ thắng còn 1,5 và RoRU nhảy lên 17,25% (rủi ro đơn giản 6,22%). Mục "Virtual Bankroll" bổ sung nguồn tiền ngoài poker (lương, đầu tư) như bankroll ảo, và nhấn mạnh tính bất đối xứng: phóng đại nhẹ tỷ lệ thắng làm đánh giá thấp rủi ro rất nhiều, còn đánh giá thấp nhẹ chỉ làm phóng đại rủi ro một chút.

> **Lưu ý:**
> - **Phạm vi trang:** Chương 23 bắt đầu ở nửa dưới trang 307 (nửa trên là phần cuối "Key Concepts" của Chương 22, đã tổng hợp trong file Chương 22) và kết thúc ở trang 317. **Trang 312 trong PDF này để trắng**: sách viết ở cuối trang 311 "Here's a table which looks at some risk of ruin calculations, using the normal distribution RoR and also this RoRU" nhưng bảng không có trong bản PDF (có lẽ bị mất khi dựng lại bằng LibreOffice). Bản tổng hợp không bịa bảng; thay vào đó, người tổng hợp tự tính một bảng RoRU theo công thức 23.1 với đúng thông số của hai hình 23.1 và 23.2 (ghi rõ là số của người tổng hợp).
> - **Ví dụ 100 giờ ở trang 307 có số sai:** sách nói với μ = 1 bet/giờ, σ = 12 bet/giờ và mẫu 100 giờ, kết quả "68% khả năng nằm giữa 0 và 200 bet" và "32% thời gian kết quả lệch quá 1 bet/giờ khỏi trung bình". Sai số chuẩn của tỷ lệ thắng 100 giờ là 12/√100 = 1,2 bet/giờ (tổng thắng có độ lệch chuẩn 120 bet), nên khoảng 68% là 100 ± 120 bet, tức từ −20 tới 220 bet (−0,2 tới 2,2 bet/giờ). Xác suất lệch quá 1 bet/giờ là 2Φ(−1/1,2) ≈ 40,5%, không phải 32%. Các số của sách chỉ đúng nếu σ = 10 bet/giờ. Kết luận định tính (tỷ lệ thắng quan sát dao động rất rộng) vẫn đúng, và còn mạnh hơn.
> - **Đơn vị lẫn lộn:** trang 307–308 viết lúc "bets/hr", lúc "BB/hr" ("at 2 BB/hr", "0.8 BB/hr and 1 BB/hr") cho cùng một đại lượng; các phép tính đều dùng bet/giờ. Bản tổng hợp dùng "bet/giờ".
> - **Thiếu ký hiệu Φ ở công thức 23.1 (trang 311):** sách in số hạng cuối là "+(−w/σ_w)"; đúng phải là +Φ(−w/σ_w), xác suất tỷ lệ thắng âm, như chính lời giải thích ngay sau ("số hạng cuối là phân phối chuẩn tích luỹ cho các tỷ lệ thắng âm, nhân với rủi ro phá sản bằng 1") và như dòng trước đó "+ p(w < 0)". Người tổng hợp kiểm tra bằng tích phân số trực tiếp: công thức có Φ cho đúng 3,67% và 17,25% của ví dụ ở trang 315–316; bỏ Φ thì kết quả vô nghĩa (số hạng âm).
> - **Ký hiệu dấu trong phép dẫn (trang 309–311):** sau khi gộp số mũ, sách viết tử số "−x² − 2x(2bσ_w²/σ² − w) + w²"; đúng phải là −[x² + 2x(2bσ_w²/σ² − w) + w²] (dấu trừ áp cho cả ngoặc). Sách viết thừa số còn lại là "exp((−w² − u²)/(2σ_w²))" và ở dòng khai triển viết "−w² − (4b²σ_w⁴/σ⁴ − 4bwσ_w²/σ² + w²)"; đúng phải là exp(−(w² − u²)/(2σ_w²)) = exp((u² − w²)/(2σ_w²)). Kết quả cuối 2b²σ_w²/σ⁴ − 2bw/σ² của sách là đúng (khớp với (u² − w²)/(2σ_w²)), nên đây chỉ là lỗi viết dấu trung gian. Các dòng ở trang 310 bị vỡ ký hiệu ("¿") trong cả lớp chữ lẫn ảnh; bản tổng hợp chép lại phép dẫn đầy đủ.
> - **Phương trình 22.3 bị hỏng ký hiệu:** như ở Chương 22, bản PDF in "¿v(x)≥∫…" thay cho ⟨v(x)⟩ = ∫ v(x)p(x)dx. Định nghĩa Φ(z) ở trang 311 cũng thiếu "dx" và lời văn gọi lẫn Φ(t), "bên trái x" thay vì Φ(z), "bên trái z"; lời văn viết "integrands of −∞ and ∞" thay vì "cận tích phân" (limits of integration).
> - **Chú thích hình in sai:** Hình 23.1 ghi "bankroll -100, std. dev. -10 bets" và Hình 23.2 ghi "bankroll + 300 bets"; đúng là "bankroll = 100" và "= 300", "std. dev. = 10 bets". Trục hoành của Hình 23.1 bị dàn lại sai trong PDF: các nhãn 0 … 2 nằm dưới khung hình và dồn về bên trái, không khớp với lưới; người tổng hợp đọc hình theo các đường lưới (mỗi ô 0,2, từ 0 tới 2), và kiểm tra lại bằng công thức 23.1 thấy khớp. Mọi số đọc từ hai hình là ước lượng.
> - **Lỗi chính tả và OCR:** "wor дd" ("world"), "Tire first" ("The first"), "100°/o" ("100%"), "overestimate then win rates" ("their"), "outer players" ("other"), "hi terms" ("in terms"), "fiving expenses" ("living"), "The same tiling" ("thing"), "40.000 hands" (dấu chấm phân cách hàng nghìn kiểu châu Âu, tức 40 nghìn ván), "of200 bets" (thiếu khoảng trắng).
> - **Các con số ví dụ chính đã được kiểm tra:** e^(−800/144) = 0,387%; e^(−320/144) = 10,84%; e^(−400/144) = 6,22%; với 40.000 ván, σ_w = 18/√400 = 0,9 bet/100 ván, RoR đơn giản e^(−2·2,5·300/324) = 0,98%, RoRU = 3,67%, chênh 2,69 điểm phần trăm; với 1,5 bet/100 ván, RoR đơn giản 6,22%, RoRU = 17,25%. Tất cả khớp sách.
> - **Quy ước thuật ngữ:** "win rate" dịch là "tỷ lệ thắng" (số tiền thắng trung bình mỗi giờ hoặc mỗi 100 ván, không phải tỷ lệ phần trăm ván thắng); "risk of ruin under uncertainty (RoRU)" là "rủi ro phá sản dưới bất định"; "standard error" là "sai số chuẩn"; "virtual bankroll" là "bankroll ảo"; "bet" là một đơn vị cược lớn của limit (ví dụ $40 ở mức $20-40).

## Sơ đồ

### Mở đầu Chương 23 — tỷ lệ thắng thật không quan sát được (trang 307–308)

```text
       Ước mơ của một tác giả: hình chiếu ba chiều trên đầu mỗi người
       chơi hiện kỳ vọng "thật" của họ. Không có, nên phải ước lượng.
       Chương 22 cần tỷ lệ thắng BIẾT CHẮC; chương này thay bằng PHÂN
       PHỐI BẤT ĐỊNH của tỷ lệ thắng suy ra từ dữ liệu (limit và cash
       game no-limit; không dùng cho giải đấu vì dựa vào công thức chuẩn)
                                │
                                ▼
       Người chơi đã chơi N giờ: tỷ lệ thắng quan sát w, độ lệch chuẩn s
       · s hội tụ nhanh về σ thật ⇒ dùng s làm σ
       · w hội tụ RẤT CHẬM về μ thật vì s lớn so với w
                                │
                                ▼
       Ví dụ: μ = 1 bet/giờ, σ = 12, mẫu 100 giờ, bankroll 200 bet
       · w dao động rộng (sai số chuẩn 1,2 bet/giờ)
       · rủi ro phá sản theo công thức chuẩn exp(−2wb/σ²):
         ┌──────────────────────┬─────────────────────┐
         │ tỷ lệ thắng (bet/giờ)│ R(200)              │
         ├──────────────────────┼─────────────────────┤
         │ 0                    │ 100%                │
         │ 0,8                  │ 10,84%              │
         │ 1                    │ 6,22%               │
         │ 2                    │ 0,387%              │
         └──────────────────────┴─────────────────────┘
       · cả khoảng gần 0–100% nằm trong một độ lệch chuẩn quanh μ;
         phân biệt 0,8 với 1 bằng dữ liệu là việc rất khó
```

### Ý tưởng rủi ro phá sản có trọng số (trang 308)

```text
       Hai lựa chọn:
       (a) coi w và s là chính xác ⇒ có thể sai nhiều
       (b) VỮNG HƠN: thay một tỷ lệ thắng bằng phân phối chuẩn, trung
           bình w, độ lệch chuẩn bằng SAI SỐ CHUẨN của w
                                │
                                ▼
       Hàm giá trị = rủi ro phá sản chuẩn tại mỗi tỷ lệ thắng x;
       hàm mật độ = phân phối giả định của tỷ lệ thắng
       Rủi ro phá sản kỳ vọng = tích phân của tích hai hàm
       · nói đơn giản: với mỗi tỷ lệ thắng khả dĩ, tính rủi ro phá sản,
         nhân với xác suất đó là tỷ lệ thắng thật, cộng tất cả lại
       · dùng được cả khi ít dữ liệu: khi đó phân phối rất rộng, và độ
         rộng này là đại lượng then chốt
                                │
                                ▼
       Hạn chế: không dùng thông tin về phân phối tiên nghiệm của người
       chơi (cách nhìn Bayes sẽ "kéo" w rất cao xuống); nhưng sai lệch
       này chỉ ở đuôi phải nên nhỏ so với độ chính xác thu được
```

### Mô hình và dẫn công thức 23.1 (trang 308–311)

```text
       Người chơi đã chơi N ván (hoặc giờ), tỷ lệ thắng w, độ lệch chuẩn
       mỗi đơn vị s, bankroll b
       · rủi ro tại tỷ lệ thắng x: R(x, b) = exp(−2xb/s²)
       · sai số chuẩn: σ_w = s/√N
       · mật độ tỷ lệ thắng: p(x) = (1/(σ_w√(2π)))·exp(−(x − w)²/(2σ_w²))
                                │
                                ▼
       ⟨R⟩ = ∫ R(x)p(x)dx, tách tại 0: với x ≤ 0, R = 1
       ⟨R⟩ = ∫₀^∞ exp(−2xb/σ²)p(x)dx + P(w < 0)
       · P(w < 0): xác suất thực chất là người THUA — không bankroll nào
         bảo vệ được khỏi phần này; σ_w càng lớn phần này càng lớn
                                │
                                ▼
       Hai hàm mũ nhân nhau ⇒ gộp số mũ; đặt u = 2bσ_w²/σ² − w;
       hoàn thành bình phương: −[(x + u)² + w² − u²]/(2σ_w²)
       · thừa số không chứa x: exp((u² − w²)/(2σ_w²))
         = exp(2b²σ_w²/σ⁴ − 2bw/σ²)
       · phần còn lại: diện tích từ 0 tới ∞ của phân phối chuẩn trung
         bình −u, độ lệch chuẩn σ_w = Φ(−u/σ_w)
                                │
                                ▼
       RoRU = R(w,b)·exp(2b²σ_w²/σ⁴)·Φ((w − 2bσ_w²/σ²)/σ_w) + Φ(−w/σ_w)
                                                                (23.1)
       Bốn thành phần: (1) rủi ro chuẩn tại w quan sát; (2) hệ số mũ
       theo bình phương bankroll và hai độ lệch chuẩn; (3) xác suất chuẩn
       tích luỹ; tích (1)(2)(3) là phần rủi ro ứng với tỷ lệ thắng dương;
       (4) xác suất tỷ lệ thắng âm, nhân với rủi ro 1
```

### Hình 23.1 và 23.2 — RoRU theo tỷ lệ thắng với các mức bất định (trang 311–313)

```text
       Hai hình: trục hoành là tỷ lệ thắng quan sát w (0 tới 2 bet), trục
       tung là xác suất phá sản; năm đường cho σ_w = 0; 0,25; 0,5; 0,75; 1
       (σ_w = 0 là công thức chuẩn không bất định); độ lệch chuẩn 10 bet
       · Hình 23.1: bankroll 100 bet; Hình 23.2: bankroll 300 bet
       (bảng so sánh mà sách hứa ở trang 311 bị mất: trang 312 trắng)
                                │
                                ▼
       Các đường cắt nhau ở một tỷ lệ thắng nhỏ (khoảng 0,3 ở Hình 23.1,
       khoảng 0,1–0,2 ở Hình 23.2):
       · BÊN TRÁI: σ_w lớn cho rủi ro NHỎ hơn 100% dù w ≈ 0 hay âm — mẫu
         có thể chỉ kém may, tỷ lệ thắng thật có thể dương
       · BÊN PHẢI: σ_w lớn cho rủi ro LỚN hơn nhiều — có thể chỉ gặp may
         ví dụ bankroll 300, w = 1: σ_w = 0 → 0,2%; σ_w = 0,5 → 5,8%;
         σ_w = 1 → 20,5% (người tổng hợp tính)
                                │
                                ▼
       RoRU điều chỉnh định lượng cho khả năng "tới giờ chỉ gặp may", và
       chống xu hướng người chơi dùng tỷ lệ thắng quá cao
```

### Mục "Bankroll Considerations" (phần 1) — bốn lý do người chơi phóng đại tỷ lệ thắng (trang 314)

```text
       1) THÀNH CÔNG BAN ĐẦU: ai thắng lúc đầu thì chơi tiếp, ai thua thì
          bỏ ⇒ nhóm người chơi tiếp chứa nhiều người kém chỉ gặp may;
          người tính chuyện chơi chuyên nghiệp thường vừa qua giai đoạn
          thắng
       2) CÁI TÔI: nhiều người tin mình giỏi hơn thực tế, đổ kết quả xấu
          cho xui
       3) THÔNG TIN SAI: diễn đàn, tạp chí, báo chí đầy "chuyện tỷ lệ thắng"
          bị thổi phồng; sách poker hay dựa vào câu sáo "1 big bet mỗi giờ"
       4) ĐIỀU KIỆN TRÒ CHƠI THAY ĐỔI: trò chơi cạn hoặc chuyển sang trò
          khác (lowball nhường chỗ hold'em); người chơi cũng tiến bộ
                                │
                                ▼
       Phóng đại tỷ lệ thắng gần như là thuộc tính phổ quát của người
       chơi poker; rất ít người thừa nhận có khả năng đáng kể mình đang
       là người thua
```

### Mục "Bankroll Considerations" (phần 2) — tỷ lệ thắng và bankroll thật sự dùng trong công thức (trang 314–316)

```text
       "Tỷ lệ thắng" và "bankroll" trong công thức rủi ro phá sản KHÁC với
       tiền thắng ở bàn và tiền đang có:
       · THUẾ: ở Mỹ, tiền thắng poker chịu thuế, giảm tỷ lệ thắng ≥ 30%
       · BANKROLL HIỆU DỤNG = số tiền sẵn sàng thua ở mức cược đó
         ví dụ $12.000 ở mức $20-40 là 300 bet, nhưng nếu thua $6.000 sẽ
         bỏ hoặc xuống mức thấp hơn thì bankroll hiệu dụng chỉ 150 bet
       · CHI PHÍ SINH HOẠT: trả cho mình một khoản "lương" theo đơn vị
         thời gian và TRỪ khỏi tỷ lệ thắng (giống điều hành doanh nghiệp
         nhỏ); tỷ lệ thắng sau chi phí gần 0 thì rủi ro gần 100%
                                │
                                ▼
       Tỷ lệ thắng đúng = tiền ĐƯA LẠI vào bankroll, không phải tiền thắng
                                │
                                ▼
       Ví dụ: 40.000 ván, 2,5 bet/100 ván, độ lệch chuẩn 18 bet/100 ván,
       bankroll 300 bet (σ_w = 0,9; cách 0 gần 3 sai số chuẩn)
       · RoRU 3,67% so với RoR đơn giản 0,98% (chênh 2,69 điểm)
       Rút 1 bet/100 ván để sống ⇒ còn 1,5 bet/100 ván (cách 0 dưới 2
       sai số chuẩn)
       · RoRU 17,25% so với RoR đơn giản 6,22%
       ⇒ rút tiền không chỉ tăng rủi ro, còn tăng mạnh khả năng là người
         thua SAU chi phí
```

### Mục "Virtual Bankroll" — bankroll ảo, tính bất đối xứng và điều kiện thay đổi (trang 316)

```text
       Rút tiền sau chuỗi thắng (kể cả người không chuyên) cũng làm tăng
       rủi ro. Ngược lại, có thể có tiền chảy VÀO bankroll từ lương, đầu
       tư ⇒ BANKROLL ẢO
       · người có việc lương $300.000/năm: bankroll ảo lớn hơn nhiều
       · người không việc, ít kỹ năng: nên giữ bankroll cẩn thận hơn
                                │
                                ▼
       BẤT ĐỐI XỨNG: phóng đại nhẹ tỷ lệ thắng ⇒ đánh giá thấp rủi ro
       RẤT NHIỀU; đánh giá thấp nhẹ ⇒ phóng đại rủi ro một chút
                                │
                                ▼
       Điều kiện trò chơi không tĩnh (poker truyền hình, poker online làm
       số người chơi bùng nổ — chưa chắc lâu dài); chuỗi thắng thường đi
       cùng điều kiện tốt tạm thời ⇒ nên coi rủi ro thật hơi CAO hơn
       công thức, vì điều kiện xấu đi tác động mạnh hơn điều kiện tốt lên
```

### Phần "Key Concepts" — các khái niệm then chốt cuối chương (trang 316–317)

```text
       · Đánh giá rủi ro phá sản thực tế luôn thiếu chính xác về tham số
         (tỷ lệ thắng, độ lệch chuẩn)
       · Có thể sửa một phần bằng cách giả định tỷ lệ thắng thật có phân
         phối chuẩn quanh ước lượng điểm
       · RoRU là công thức rủi ro phá sản có điều chỉnh cho bất định đó
       · Dùng được khi chỉ có mẫu nhỏ; phản ánh rằng sai số ước lượng tỷ
         lệ thắng tác động không đối xứng
       · Khi tính chuyện chơi chuyên nghiệp, hiểu rủi ro thực tế là điều
         quan trọng và hay bị bỏ qua
```

## Ba câu hỏi chương này trả lời

1. **Vì sao không thể cắm tỷ lệ thắng quan sát được vào công thức rủi ro phá sản?** Vì tỷ lệ thắng hội tụ rất chậm: với độ lệch chuẩn 12 bet/giờ, 100 giờ chơi cho sai số chuẩn 1,2 bet/giờ, lớn hơn cả tỷ lệ thắng 1 bet/giờ. Rủi ro phá sản lại rất nhạy với tỷ lệ thắng: với bankroll 200 bet, rủi ro là 100% ở 0 bet/giờ, 10,84% ở 0,8, 6,22% ở 1 và 0,387% ở 2. Một con số ước lượng duy nhất che giấu khả năng đáng kể rằng người chơi thực ra hoà vốn hoặc thua.
2. **Tính rủi ro phá sản có tính đến bất định thế nào?** Coi tỷ lệ thắng thật có phân phối chuẩn quanh w với độ lệch chuẩn σ_w = s/√N, rồi lấy trung bình rủi ro phá sản theo phân phối đó, với rủi ro bằng 1 cho mọi tỷ lệ thắng âm. Vì cả hai đều là hàm mũ, tích phân có dạng đóng RoRU = exp(−2bw/σ²)·exp(2b²σ_w²/σ⁴)·Φ((w − 2bσ_w²/σ²)/σ_w) + Φ(−w/σ_w). Ví dụ 40.000 ván, 2,5 bet/100 ván, σ = 18, bankroll 300 bet: RoRU 3,67% so với 0,98%.
3. **Người chơi (nhất là người định chơi chuyên nghiệp) cần điều chỉnh gì?** Dùng tỷ lệ thắng *sau thuế và sau chi phí sinh hoạt*, tức số tiền thực sự đưa lại vào bankroll; dùng bankroll *hiệu dụng* (số tiền sẵn sàng thua ở mức cược đó); và tính đến bất định bằng RoRU. Rút 1 bet/100 ván để sống làm RoRU của người chơi trên tăng từ 3,67% lên 17,25%. Phóng đại tỷ lệ thắng nguy hiểm hơn nhiều so với đánh giá thấp, và điều kiện trò chơi có thể xấu đi, nên rủi ro thật nên được coi là cao hơn công thức.

## Khái niệm cần biết

- **Tỷ lệ thắng (win rate) w và tỷ lệ thắng thật μ:** w là số tiền thắng trung bình quan sát được mỗi giờ hoặc mỗi 100 ván; μ là giá trị kỳ vọng thật chưa biết. Ví dụ: quan sát 2,5 bet/100 ván sau 40.000 ván. Quan trọng vì rủi ro phá sản phụ thuộc mũ vào μ, mà ta chỉ có w.
- **Sai số chuẩn của tỷ lệ thắng (standard error) σ_w = s/√N:** độ lệch chuẩn của tỷ lệ thắng quan sát quanh tỷ lệ thật, N là số đơn vị (giờ hoặc khối 100 ván). Ví dụ: s = 18 bet/100 ván, N = 400 khối 100 ván, σ_w = 18/20 = 0,9. Quan trọng vì nó là độ rộng của phân phối tỷ lệ thắng, đại lượng then chốt của RoRU.
- **Rủi ro phá sản đơn giản R(w, b) = exp(−2wb/s²):** công thức Chương 22 cho phân phối chuẩn, cắm thẳng w quan sát. Ví dụ: w = 2,5, b = 300, s = 18: e^(−4,63) = 0,98%.
- **Rủi ro phá sản dưới bất định (risk of ruin under uncertainty, RoRU):** kỳ vọng của rủi ro phá sản khi tỷ lệ thắng thật có phân phối chuẩn quanh w. Ví dụ: 3,67% cho cùng người chơi trên. Quan trọng vì nó là con số thực tế hơn.
- **Hàm phân phối chuẩn tích luỹ Φ(z) (cumulative normal distribution function):** diện tích dưới đường cong chuẩn tắc (trung bình 0, độ lệch chuẩn 1) bên trái z, Φ(z) = (1/√(2π))∫_{−∞}^{z} e^(−x²/2)dx. Ví dụ: Φ(−2,78) ≈ 0,0027 là xác suất tỷ lệ thắng thật âm khi w = 2,5 và σ_w = 0,9. Tra bảng hoặc dùng hàm bảng tính (NORM.S.DIST trong Excel).
- **Điểm z (z-score):** số độ lệch chuẩn từ trung bình. Ví dụ: w/σ_w = 2,5/0,9 ≈ 2,78 ("gần ba sai số chuẩn khỏi 0").
- **Xác suất là người thua P(w < 0) = Φ(−w/σ_w):** phần rủi ro không bankroll nào che được. Ví dụ: với 1,5 bet/100 ván, Φ(−1,67) ≈ 4,8%; chỉ riêng phần này đã gần bằng rủi ro đơn giản 6,22%.
- **Phân phối tiên nghiệm (a priori distribution) và co về trung bình (cách nhìn Bayes):** phân phối tỷ lệ thắng của tổng thể người chơi mà người này được "rút ra" từ đó; phân tích Bayes sẽ kéo một tỷ lệ thắng quan sát rất cao về gần mức phổ biến. Ví dụ: 10 bet/giờ sau 50 giờ gần như chắc chắn là may. Quan trọng vì RoRU bỏ qua điều này, nên vẫn còn lạc quan ở đuôi phải.
- **Bankroll hiệu dụng (effective bankroll):** số tiền sẵn sàng thua ở một mức cược trước khi bỏ hoặc xuống mức thấp hơn. Ví dụ: $6.000 ở $20-40, tức 150 bet, dù có $12.000.
- **Tỷ lệ thắng sau chi phí (adjusted win rate):** tỷ lệ thắng trừ thuế, chi phí sinh hoạt và mọi khoản rút ra. Ví dụ: 2,5 − 1 = 1,5 bet/100 ván.
- **Bankroll ảo (virtual bankroll):** khả năng bổ sung bankroll từ nguồn ngoài poker. Ví dụ: người có lương $300.000/năm.
- **Lệch chọn mẫu do thành công ban đầu (initial success, selection):** nhóm người còn chơi sau giai đoạn đầu được chọn lọc theo may mắn nhiều hơn theo kỹ năng. Ví dụ: người kém nhưng thắng lúc đầu thì ở lại và tin tỷ lệ thắng thổi phồng của mình.

## Nội dung chi tiết

### 1. Mở đầu: tỷ lệ thắng thật không quan sát được (trang 307–308)

Một trong hai tác giả có một hình dung lặp đi lặp lại về một thế giới nơi các hình chiếu ba chiều nhỏ hiện trên đầu mỗi người chơi, cho thấy kỳ vọng "thật" chính xác của người đó trong ván, trận, buổi chơi hiện tại — tính cả những người cùng bàn, trạng thái tâm lý của người chơi, v.v. Tiếc là không có những hình chiếu như vậy, nên ta phải ước lượng và suy luận. Phần I đã bàn việc ước lượng tham số. Chương này kết hợp công thức rủi ro phá sản của chương trước, vốn dựa trên một tỷ lệ thắng chắc chắn và biết trước, với một phân phối bất định của tỷ lệ thắng suy ra từ dữ liệu quan sát. Suốt chương, tác giả tập trung vào poker limit, dù các nguyên tắc áp dụng như nhau cho cash game no-limit. Tuy nhiên, vì phân tích dựa vào công thức rủi ro phá sản cho phân phối chuẩn, nó không dùng nguyên dạng được cho giải đấu (Chương 22 đã chỉ ra công thức chuẩn sai lệch lớn với phân phối lệch dương của giải đấu).

Xét một người chơi đã chơi N giờ với tỷ lệ thắng w và độ lệch chuẩn s. Trước hết, độ lệch chuẩn mẫu hội tụ khá nhanh về độ lệch chuẩn tổng thể, nên suốt phân tích ta dùng s làm độ lệch chuẩn σ của trò chơi. Nhưng kinh nghiệm cho thấy w hội tụ về tỷ lệ thắng "thật" μ của người chơi rất chậm, vì s lớn so với w.

Để thấy điều này, giả sử ta biết μ = 1 bet/giờ và σ = 12 bet/giờ, lấy mẫu 100 giờ và gọi kết quả là w. Sách nói w có 68% khả năng nằm giữa 0 và 200 bet (tổng thắng), và 32% thời gian lệch quá 1 bet/giờ khỏi trung bình. (Người tổng hợp tính lại: sai số chuẩn của w là 12/√100 = 1,2 bet/giờ, nên khoảng 68% của tổng thắng là 100 ± 120 bet, tức −20 tới 220 bet; xác suất lệch quá 1 bet/giờ là 2Φ(−1/1,2) ≈ 40,5% — xem Lưu ý.) Giả sử người chơi có bankroll 200 bet. Chênh lệch rủi ro phá sản giữa tỷ lệ thắng 0 và 2 bet/giờ là rất lớn:

- Tỷ lệ thắng 0: R(200) = 1 (theo Chương 22, kỳ vọng không dương thì chắc chắn phá sản).
- Tỷ lệ thắng 2 bet/giờ: R(200) = e^(−2·2·200/144) = e^(−800/144) = e^(−5,556) = 0,387%.

Như vậy khoảng giá trị rủi ro phá sản trải gần trọn 0–100%, tất cả trong phạm vi một độ lệch chuẩn quanh trung bình tổng thể. Ngay cả giữa tỷ lệ thắng 0,8 và 1 bet/giờ cũng có khác biệt khá lớn:

- 0,8 bet/giờ: R(200) = e^(−2·0,8·200/144) = e^(−320/144) = e^(−2,222) = 10,84%.
- 1 bet/giờ: R(200) = e^(−400/144) = e^(−2,778) = 6,22%.

Thế nhưng việc thu thập đủ dữ liệu thực nghiệm để phân biệt hai trường hợp này là một việc gian nan. (Minh hoạ của người tổng hợp: để sai số chuẩn chỉ còn 0,1 bet/giờ — một nửa khoảng cách 0,2 giữa hai tỷ lệ — cần (12/0,1)² = 14.400 giờ, tức khoảng 7 năm chơi toàn thời gian 2.000 giờ/năm.)

### 2. Ý tưởng: rủi ro phá sản có trọng số theo phân phối tỷ lệ thắng (trang 308)

Ta đứng trước một tình thế khó xử. Có thể dùng tỷ lệ thắng và độ lệch chuẩn w, s và đơn giản giả định chúng là dự báo chính xác; nhưng trung bình tổng thể thật có thể khác đáng kể giá trị quan sát. Cách vững hơn là tính đến bất định của tỷ lệ thắng bằng cách dùng một phân phối tỷ lệ thắng thay vì gán một giá trị duy nhất. Cụ thể, dùng phân phối chuẩn có trung bình bằng tỷ lệ thắng quan sát và độ lệch chuẩn bằng sai số chuẩn của tỷ lệ thắng quan sát. Sau đó dùng hàm rủi ro phá sản chuẩn làm hàm giá trị, và phân phối tỷ lệ thắng giả định này làm hàm mật độ tương ứng; kỳ vọng của hàm rủi ro phá sản là tích phân của tích hai hàm đó.

Nói bằng ngôn ngữ ít kỹ thuật hơn: ta có tỷ lệ thắng quan sát w và dựng một đường cong phân phối chuẩn quanh w. Càng gần w thì xác suất đó là tỷ lệ thắng thật càng cao. Tại mỗi tỷ lệ thắng, dùng hàm rủi ro phá sản đã tính để có rủi ro phá sản ứng với tỷ lệ thắng đó. Nhân mỗi giá trị rủi ro phá sản với xác suất giá trị đó là tỷ lệ thắng thật rồi cộng tất cả, ta được một rủi ro phá sản "có trọng số", chính xác hơn việc chỉ đoán một tỷ lệ thắng.

Điều quan trọng là cách này dùng được dù chỉ có ít dữ liệu về trò chơi. Nếu chỉ có ít giờ chơi, độ phân tán của phân phối tỷ lệ thắng sẽ khá lớn; như sẽ thấy, độ phân tán này là đại lượng then chốt để tìm rủi ro phá sản có trọng số.

Người đọc có thể nhớ rằng ở Phần I, khi bàn khoảng tin cậy, tác giả đã cảnh báo việc chỉ áp phân phối chuẩn lên kết quả quan sát. Cảnh báo đó vẫn còn hiệu lực: cách làm này không đưa vào thông tin về phân phối nền. Điều này đặc biệt đúng khi trung bình quan sát rất cao, lúc phân tích Bayes sẽ làm "dịu" quan sát về phía phân phối tỷ lệ thắng của tổng thể người chơi. Tuy nhiên, vì sai lệch này chỉ giới hạn ở đuôi phải của phân phối chuẩn, độ lớn của nó khá nhỏ so với độ chính xác thu được nhờ phương pháp. Và muốn sửa sai lệch này thì phải cố mô tả hình dạng của phân phối tiên nghiệm mà người chơi này được chọn ra từ đó.

### 3. Mô hình và dẫn công thức RoRU (23.1) (trang 308–311)

**Thiết lập.** Một người chơi đã chơi N ván với tỷ lệ thắng w và độ lệch chuẩn mỗi ván s, có bankroll b. Rủi ro phá sản của anh ta tại một tỷ lệ thắng cụ thể là

$$R(w, b) = \exp\!\left(\frac{-2wb}{s^2}\right).$$

Sai số chuẩn của tỷ lệ thắng quan sát là

$$\sigma_w = s/\sqrt{N}.$$

Các quan sát về tỷ lệ thắng tạo một hàm mật độ chuẩn quanh trung bình w với độ lệch chuẩn σ_w:

$$p(x) = \frac{1}{\sigma_w\sqrt{2\pi}}\exp\!\left(\frac{-(x-w)^2}{2\sigma_w^2}\right).$$

**Tách tích phân tại 0.** Theo phương trình 22.3 (kỳ vọng của hàm giá trị bằng tích phân của hàm giá trị nhân hàm mật độ), ⟨v(x)⟩ = ∫_{−∞}^{∞} v(x)p(x)dx. Phương trình này đòi tích phân từ −∞ tới +∞; nhưng ta biết rủi ro phá sản với mọi tỷ lệ thắng bên trái 0 luôn bằng 1. Vì vậy tách tích phân làm hai phần: tích phân từ 0 tới ∞ của hàm giá trị (rủi ro phá sản) nhân hàm mật độ (phân phối chuẩn của tỷ lệ thắng), cộng tích phân của riêng hàm mật độ từ −∞ tới 0 — chính là xác suất tỷ lệ thắng bằng 0 hoặc âm:

$$\langle R\rangle = \frac{1}{\sigma_w\sqrt{2\pi}}\int_0^{\infty}\exp\!\left(\frac{-2xb}{\sigma^2}\right)\exp\!\left(\frac{-(x-w)^2}{2\sigma_w^2}\right)dx + p(w<0).$$

Số hạng cuối là đặc điểm quan trọng nhất của cách tiếp cận này. Nó nắm bắt bất định quanh tỷ lệ thắng và ý tưởng rằng bankroll lớn bao nhiêu cũng không bảo vệ được khỏi rủi ro phá sản đến từ việc là người chơi thua. Xác suất này gắn trực tiếp với bất định σ_w: độ phân tán càng cao, khả năng tỷ lệ thắng dưới 0 càng lớn. Ngoài ra, rủi ro phá sản của các tỷ lệ thắng dương nhưng rất thấp cũng đã rất cao.

**Gộp hai hàm mũ.** Có một lý do rất thực dụng để dùng phân phối chuẩn cho tỷ lệ thắng: vì cả phân phối chuẩn và công thức rủi ro phá sản đều là hàm mũ, biểu thức đơn giản hoá được. Gộp số mũ (khai triển (x − w)² = x² − 2xw + w²):

$$\frac{1}{\sigma_w\sqrt{2\pi}}\int_0^{\infty}\exp\!\left(\frac{-2xb}{\sigma^2} - \frac{x^2 - 2xw + w^2}{2\sigma_w^2}\right)dx + p(w<0).$$

Quy đồng mẫu 2σ_w²: −2xb/σ² = −(4xbσ_w²/σ²)/(2σ_w²). Gom các số hạng chứa x bậc nhất:

$$\frac{1}{\sigma_w\sqrt{2\pi}}\int_0^{\infty}\exp\!\left(\frac{-\left[x^2 + 2x\left(2b\frac{\sigma_w^2}{\sigma^2} - w\right) + w^2\right]}{2\sigma_w^2}\right)dx + p(w<0).$$

**Đặt u và hoàn thành bình phương.** Đặt

$$u = 2b\frac{\sigma_w^2}{\sigma^2} - w.$$

Khi đó x² + 2xu + w² = (x + u)² + w² − u², nên

$$\frac{1}{\sigma_w\sqrt{2\pi}}\int_0^{\infty}\exp\!\left(\frac{-(x-(-u))^2}{2\sigma_w^2}\right)\exp\!\left(\frac{-(w^2-u^2)}{2\sigma_w^2}\right)dx + p(w<0).$$

Hàm mũ thứ hai không chứa x, nên đưa ra ngoài tích phân, còn lại một hằng số nhân với một hàm mật độ chuẩn:

$$\exp\!\left(\frac{-(w^2-u^2)}{2\sigma_w^2}\right)\cdot\frac{1}{\sigma_w\sqrt{2\pi}}\int_0^{\infty}\exp\!\left(\frac{-(x+u)^2}{2\sigma_w^2}\right)dx + p(w<0).$$

**Dùng hàm phân phối chuẩn tích luỹ.** Chương 3 đã định nghĩa

$$\Phi(z) = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{z}\exp\!\left(\frac{-x^2}{2}\right)dx,$$

với z là điểm z đã chuẩn hoá. Φ(z) là diện tích dưới đường cong của phân phối chuẩn trung bình 0, độ lệch chuẩn 1, bên trái z; gọi là **hàm phân phối chuẩn tích luỹ**. Tích phân còn lại là tích phân mật độ của một phân phối chuẩn có trung bình −u, độ lệch chuẩn σ_w. Nếu lấy từ −∞ tới ∞ nó bằng 1; nhưng nó được lấy từ 0 tới ∞, tức là xác suất biến chuẩn đó lớn hơn 0, bằng Φ của điểm z là −u/σ_w, tức (w − 2bσ_w²/σ²)/σ_w. Giá trị này tra bảng hoặc lấy bằng hàm bảng tính. Còn lại:

$$\exp\!\left(\frac{u^2-w^2}{2\sigma_w^2}\right)\Phi(-u/\sigma_w) + p(w<0).$$

**Rút gọn số mũ.** u² = 4b²σ_w⁴/σ⁴ − 4bwσ_w²/σ² + w², nên

$$\frac{u^2 - w^2}{2\sigma_w^2} = \frac{4b^2\sigma_w^4/\sigma^4 - 4bw\sigma_w^2/\sigma^2}{2\sigma_w^2} = 2b^2\frac{\sigma_w^2}{\sigma^4} - \frac{2bw}{\sigma^2}.$$

Biểu thức thành exp(2b²σ_w²/σ⁴ − 2bw/σ²)·Φ(−u/σ_w) + p(w < 0). Tách exp(−2bw/σ²) = R(w, b) và viết p(w < 0) = Φ(−w/σ_w):

$$\text{RoRU} = R(w,b)\,\exp\!\left(2b^2\frac{\sigma_w^2}{\sigma^4}\right)\Phi\!\left(\left(w - 2b\frac{\sigma_w^2}{\sigma^2}\right)\Big/\sigma_w\right) + \Phi(-w/\sigma_w) \qquad (23.1)$$

(Sách in số hạng cuối thiếu chữ Φ, xem Lưu ý.) Đây là công thức **rủi ro phá sản dưới bất định** (risk of ruin under uncertainty, RoRU). Nó gồm bốn thành phần:

1. R(w, b): rủi ro phá sản theo phân phối chuẩn tại tỷ lệ thắng quan sát gốc.
2. Một hàm mũ chứa bình phương bankroll và độ lệch chuẩn của cả trò chơi lẫn của ước lượng tỷ lệ thắng; nó luôn ≥ 1, làm tăng rủi ro.
3. Hàm phân phối chuẩn tích luỹ của một biểu thức theo w, bankroll b và hai độ lệch chuẩn.
   Tích ba thành phần đầu là rủi ro phá sản có trọng số ứng với các tỷ lệ thắng dương.
4. Phân phối chuẩn tích luỹ cho các tỷ lệ thắng âm, nhân với rủi ro phá sản của chúng, bằng 1.

Kiểm tra của người tổng hợp: khi σ_w → 0 (dữ liệu vô hạn) và w > 0, thành phần 2 về 1, thành phần 3 về Φ(+∞) = 1, thành phần 4 về 0, nên RoRU về R(w, b), đúng như mong đợi. Người tổng hợp cũng tính tích phân bằng phương pháp số trực tiếp cho hai ví dụ ở mục 5 và được kết quả trùng công thức tới 8 chữ số.

### 4. Hình 23.1 và 23.2: RoRU theo tỷ lệ thắng (trang 311–313)

Cuối trang 311, sách giới thiệu "một bảng xem xét vài phép tính rủi ro phá sản, dùng RoR chuẩn và RoRU", nhưng trang 312 của PDF này để trắng, nên bảng không còn. Tiếp theo là hai hình:

- **Hình 23.1 "RoRU vs win rate"** với bankroll 100 bet, độ lệch chuẩn 10 bet.
- **Hình 23.2 "RoRU vs win rate"** với bankroll 300 bet, độ lệch chuẩn 10 bet.

Mỗi hình có trục hoành là tỷ lệ thắng (0 tới 2 bet), trục tung là xác suất phá sản (0 tới 1), và năm đường ứng với "Sigma-win" σ_w = 0 (chấm), 0,25 (đậm), 0,5 (xám), 0,75 (gạch), 1,0 (gạch chấm). Đường σ_w = 0 chính là công thức chuẩn không bất định. (Người tổng hợp ghi chú: với σ = 10, σ_w = 1 ứng với khoảng 100 giờ dữ liệu; σ_w = 0,25 ứng với khoảng 1.600 giờ.)

Đọc từ hình (ước lượng) và đối chiếu với công thức 23.1:

- **Hình 23.1 (bankroll 100):** ở tỷ lệ thắng 0, đường σ_w = 0 bắt đầu từ 1, còn các đường σ_w = 0,25; 0,5; 0,75; 1 bắt đầu từ khoảng 0,85; 0,77; 0,70; 0,67. Các đường cắt nhau quanh tỷ lệ thắng khoảng 0,3, xác suất khoảng 0,55–0,6. Bên phải điểm cắt, thứ tự đảo ngược: ở tỷ lệ thắng 2, đường σ_w = 0 gần 0,02 còn đường σ_w = 1 khoảng 0,09.
- **Hình 23.2 (bankroll 300):** ở tỷ lệ thắng 0, các đường bắt đầu từ 1; khoảng 0,71; 0,62; 0,59; 0,57. Các đường cắt nhau quanh tỷ lệ thắng khoảng 0,1–0,2, xác suất khoảng 0,5. Đường σ_w = 0 rơi rất nhanh, gần 0 từ tỷ lệ thắng 0,8 trở đi, trong khi đường σ_w = 1 còn khoảng 0,2 ở tỷ lệ thắng 1 và khoảng 0,04 ở tỷ lệ thắng 2.

Bảng của người tổng hợp, tính từ công thức 23.1 với σ = 10 (dùng thay cho bảng bị mất, và để đọc hình chính xác hơn):

**Bankroll 100 bet (thông số của Hình 23.1):**

| Tỷ lệ thắng w | σ_w = 0 | σ_w = 0,25 | σ_w = 0,5 | σ_w = 0,75 | σ_w = 1 |
|---:|---:|---:|---:|---:|---:|
| 0 | 100% | 85,0% | 76,2% | 70,6% | 66,8% |
| 0,2 | 67,0% | 68,1% | 64,8% | 61,9% | 59,9% |
| 0,4 | 44,9% | 49,5% | 52,4% | 52,8% | 52,7% |
| 0,6 | 30,1% | 34,0% | 40,3% | 43,6% | 45,4% |
| 0,8 | 20,2% | 22,9% | 29,6% | 35,0% | 38,4% |
| 1,0 | 13,5% | 15,3% | 21,0% | 27,2% | 31,7% |
| 1,5 | 5,0% | 5,6% | 8,2% | 12,9% | 18,0% |
| 2,0 | 1,8% | 2,1% | 3,0% | 5,3% | 9,0% |

**Bankroll 300 bet (thông số của Hình 23.2):**

| Tỷ lệ thắng w | σ_w = 0 | σ_w = 0,25 | σ_w = 0,5 | σ_w = 0,75 | σ_w = 1 |
|---:|---:|---:|---:|---:|---:|
| 0 | 100% | 70,6% | 62,2% | 58,5% | 56,5% |
| 0,2 | 30,1% | 43,6% | 47,1% | 48,1% | 48,6% |
| 0,4 | 9,1% | 20,6% | 32,5% | 37,9% | 40,8% |
| 0,6 | 2,7% | 7,7% | 20,3% | 28,5% | 33,4% |
| 0,8 | 0,8% | 2,5% | 11,5% | 20,4% | 26,6% |
| 1,0 | 0,2% | 0,8% | 5,8% | 13,9% | 20,5% |
| 1,5 | 0,0% | 0,0% | 0,7% | 4,2% | 9,4% |
| 2,0 | 0,0% | 0,0% | 0,0% | 0,9% | 3,6% |

Điều đáng chú ý trong các hình là khi bất định về tỷ lệ thắng cao (mẫu nhỏ), RoRU dự báo xác suất phá sản dưới 100% ngay cả khi tỷ lệ thắng tới thời điểm đó bằng 0 hay âm. Lý do: mẫu có thể chỉ kém may, và tỷ lệ thắng thật có thể trên 0, khi đó rủi ro phá sản nhỏ hơn 1. (Người tổng hợp bổ sung chiều ngược lại, rõ trong bảng: ở tỷ lệ thắng trung bình và cao, bất định làm rủi ro tăng gấp nhiều lần — với bankroll 300 và w = 1, từ 0,2% lên 20,5% khi σ_w = 1 — vì mẫu có thể chỉ gặp may. Với người chơi thắng, đây là tác động quan trọng hơn.)

RoRU là một cách mạnh để đưa bất định về tỷ lệ thắng vào tính toán rủi ro phá sản: ta điều chỉnh kỳ vọng và hiểu biết về rủi ro phá sản, kèm một điều chỉnh định lượng cho khả năng tới giờ ta chỉ gặp may phần nào. Công thức phức tạp hơn các công thức trước, nhưng đặc tính làm nó cực kỳ hữu ích là nó cố gắng tính đến xu hướng người chơi dùng tỷ lệ thắng quá cao khi ước lượng rủi ro phá sản. Xét về việc "ở lại bàn chơi", khó mà đánh giá quá cao tầm quan trọng của xu hướng này và việc mất vốn bankroll do nó gây ra.

### 5. Những cân nhắc về bankroll (Bankroll Considerations, trang 314–316)

Tác giả tin rằng phần lớn người chơi phóng đại tỷ lệ thắng của mình khi tính rủi ro phá sản, vì một số lý do:

**1) Thành công ban đầu (Initial Success).** Người bắt đầu sự nghiệp poker bằng một chuỗi thắng dễ chơi tiếp hơn; người bắt đầu bằng chuỗi thua dễ bỏ hẳn hơn nhiều. Hiệu ứng này có lẽ chọn lọc nhẹ về phía người có kỳ vọng cao hơn, nhưng bị phương sai lấn át. Nếu nhìn tập hợp mọi người chơi bắt đầu bằng thắng, ta sẽ thấy khá nhiều người tương đối kém chỉ gặp các biến cố phương sai dương. Họ sẽ dựa vào tỷ lệ thắng quá khứ (bị thổi phồng) để dự báo tỷ lệ thắng tương lai (kỳ vọng), và do đó đánh giá quá cao triển vọng. Hiệu ứng này đặc biệt rõ ở người đang tính chơi chuyên nghiệp: thời điểm dễ nhất để người chơi nghĩ tới việc chơi toàn thời gian là sau một giai đoạn đi lên. Các giai đoạn đi lên đó có thể là thật, nhưng thường là dao động thống kê dương không phản ánh thay đổi nào về kỳ vọng.

**2) Cái tôi (Ego).** Poker là trò chơi bị cái tôi chi phối. Nhiều người tin chắc mình mạnh hơn thực tế nhiều, rằng kết quả tới nay chủ yếu do xui chứ không do chơi kém. Điều này đôi khi đúng, nhưng thường là kết hợp của cả hai.

**3) Thông tin sai (Misinformation).** Có rất nhiều thông tin trôi nổi trong cộng đồng poker, từ diễn đàn công cộng như rec.gambling.poker, các diễn đàn Internet khác, tạp chí, và nay cả báo chí đại chúng. Ở đó, người chơi có thể tuyên bố bất kỳ tỷ lệ thắng (thổi phồng) nào mà hầu như không có khả năng bị vạch trần. Điều này dẫn tới lạm phát chung của "chuyện tỷ lệ thắng", vì không ai muốn thấy mình thua kém người khác. Thêm vào đó, sách poker có xu hướng đáng lo là gạt đi câu hỏi kỳ vọng thực tế ở các loại trò chơi khác nhau là bao nhiêu, mà dựa vào câu sáo "1 big bet mỗi giờ" làm chuẩn cho người chơi thắng điển hình.

**4) Điều kiện trò chơi thay đổi (Changing Game Conditions).** Người chơi chiếu tỷ lệ thắng hiện tại vào tương lai. Nhưng điều kiện thay đổi: trò chơi cạn đi hoặc chuyển sang một trò được ưa chuộng khác, như các trò lowball khi hold'em xuất hiện. Người chơi cũng có thể tiến bộ theo thời gian. Nhiều thứ có thể thay đổi làm ước lượng về tương lai thiếu chính xác.

Rất ít người chơi poker, nhất là những người đã bỏ thời gian và công sức để tiến bộ, chịu thừa nhận có khả năng đáng kể họ là người thua tính tổng thể. Thành thật mà nói, phóng đại tỷ lệ thắng của mình gần như là một thuộc tính phổ quát của người chơi poker.

**Tỷ lệ thắng và bankroll dùng trong công thức khác với con số thô.** Còn một lý do nữa khiến tỷ lệ thắng dùng để tính rủi ro phá sản thường bị phóng đại: phần lớn người chơi không đưa toàn bộ tiền thắng poker vào bankroll. Vào lúc viết sách, một tác giả chơi chuyên nghiệp, nên tiêu tiền cho trả góp nhà, thức ăn, v.v. Ta nói "tỷ lệ thắng" và "bankroll" trong rủi ro phá sản bằng cùng những từ dùng để mô tả tốc độ thắng ở một trò chơi và tổng số tiền có để chơi poker, nhưng chúng hoàn toàn không giống nhau:

- **Thứ nhất, thuế.** Ở Mỹ, tiền thắng poker phải chịu thuế, có thể làm giảm "tỷ lệ thắng" 30% trở lên tuỳ mức độ thành công của người chơi.
- **Thứ hai, bankroll hiệu dụng.** "Bankroll" thực ra nên được coi là số tiền ta sẵn sàng thua khi chơi một trò chơi ở một mức cược cụ thể. Ví dụ, người chơi mức $20-40 có $12.000 dành để chơi poker có thể được coi là có bankroll 300 bet ($12.000/$40). Nhưng nếu anh ta sẽ bỏ poker sau khi thua $6.000, hoặc sẽ xuống mức cược thấp hơn (chủ đề sẽ bàn sau), thì bankroll hiệu dụng cho mức $20-40 chỉ là 150 bet. Anh ta không "phá sản" theo nghĩa hết khả năng chơi khi thua số đó, nhưng xét xác suất anh ta thua $12.000 ở mức $20-40 là phi lý — thực tế anh ta sẽ không bao giờ thua $12.000 ở trò chơi này. Rủi ro phá sản "thật" của anh ta là sự kết hợp của rủi ro thua, ở mỗi mức cược, số tiền anh ta chịu được trước khi xuống mức thấp hơn nữa, hoặc bỏ poker hẳn.
- **Thứ ba, chi phí sinh hoạt.** Người chơi chuyên nghiệp có chi phí sống phải trả dù thắng hay thua: một dòng tiền ra đều đặn phải tính vào bankroll và tiền thắng. Ngay cả người thắng không chơi chuyên nghiệp cũng thường không để 100% tiền thắng trong bankroll, mà tiêu vào kỳ nghỉ, trang sức hay TV plasma. Có vài chiến lược hợp lý để rút tiền thắng chi tiêu, dù cho nhu cầu xa xỉ hay thiết yếu; tác giả thích một cách giúp tiếp tục đánh giá rủi ro hợp lý trong khi có dòng tiền ra đều: **tự trả lương cho mình theo một đơn vị thời gian và giảm tỷ lệ thắng đúng bằng khoản đó**. Cách này khá giống khởi sự một doanh nghiệp nhỏ.

Điều này có thể làm vài độc giả nhíu mày: "Trừ lương khỏi tỷ lệ thắng! Nếu số tiền tôi cần gần bằng số tôi kiếm được thì sao?" Đó chính là mấu chốt. Nếu tỷ lệ thắng đã điều chỉnh (sau khi trừ tiền rút ra chi tiêu) gần 0 (hay thậm chí âm!), thì **rủi ro phá sản của người chơi tăng vọt và thường gần 100%**. Vô số người chơi chuyên nghiệp đã bỏ qua nguyên tắc này, hớt phần lớn lợi nhuận khỏi bankroll, và cuối cùng phá sản khi gặp một đợt đi xuống nặng. Ngay cả khi không phá sản, người chơi thường phải bỏ lỡ thu nhập vì buộc phải xuống mức cược thấp hơn.

Mỗi đô la lấy khỏi bankroll làm giảm khả năng chịu đựng các đợt đi xuống của bankroll; vì vậy khi tính rủi ro phá sản, bắt buộc phải dùng tỷ lệ thắng mô tả chính xác **không phải số tiền thắng được, mà số tiền được đưa lại vào bankroll trong quá trình chơi**.

**Ví dụ người chơi định chuyển sang chuyên nghiệp.** Với người muốn chơi chuyên nghiệp, tình hình còn tệ hơn: phương pháp rủi ro phá sản có trọng số vừa trình bày chịu ảnh hưởng nặng của khả năng tỷ lệ thắng thật thấp hơn kết quả lịch sử. Tuy nhiên, nhiều người tính chuyển sang chuyên nghiệp sau một thời gian khá dài chơi "nghiệp dư" đã đạt tới ngưỡng mà với tỷ lệ thắng chưa điều chỉnh, phần điều chỉnh không lớn lắm.

Người chơi đã chơi 40.000 ván trò chơi yêu thích, thắng 2,5 bet/100 ván với độ lệch chuẩn 18 bet/100 ván, có bankroll 300 bet. Tính toán chi tiết của người tổng hợp (đơn vị là khối 100 ván, N = 400 khối):

- σ_w = 18/√400 = 0,9 bet/100 ván; w/σ_w = 2,78.
- RoR đơn giản: exp(−2 × 2,5 × 300/18²) = exp(−1.500/324) = e^(−4,63) = **0,98%**.
- Thành phần 2: exp(2 × 300² × 0,9²/18⁴) = exp(145.800/104.976) = e^(1,389) ≈ 4,01.
- Thành phần 3: Φ((2,5 − 2 × 300 × 0,81/324)/0,9) = Φ((2,5 − 1,5)/0,9) = Φ(1,11) ≈ 0,867.
- Thành phần 4: Φ(−2,78) ≈ 0,0027.
- **RoRU = 0,0098 × 4,01 × 0,867 + 0,0027 ≈ 3,67%.**

Chênh lệch giữa hai con số chỉ 2,69 điểm phần trăm, vì người chơi đã tích luỹ đủ dữ liệu để tỷ lệ thắng cách 0 gần ba sai số chuẩn; rủi ro có trọng số không bị bất định làm tăng nhiều.

Giờ người chơi tính chuyển sang chuyên nghiệp. Anh ta định rút khoảng 1 bet/100 ván từ tiền thắng hằng tháng để trả chi phí sinh hoạt khiêm tốn, để phần còn lại cho bankroll tăng. Tỷ lệ thắng điều chỉnh là 1,5 bet/100 ván. Tính lại:

- RoR đơn giản: exp(−2 × 1,5 × 300/324) = e^(−2,778) = **6,22%**.
- Thành phần 3: Φ((1,5 − 1,5)/0,9) = Φ(0) = 0,5; thành phần 4: Φ(−1,5/0,9) = Φ(−1,67) ≈ 0,048.
- **RoRU = 0,0622 × 4,01 × 0,5 + 0,048 ≈ 17,25%.**

| Tình huống | w (bet/100 ván) | w/σ_w | RoR đơn giản | RoRU | P(tỷ lệ thắng thật < 0) |
|---|---:|---:|---:|---:|---:|
| Nghiệp dư, giữ toàn bộ tiền thắng | 2,5 | 2,78 | 0,98% | 3,67% | 0,27% |
| Chuyên nghiệp, rút 1 bet/100 ván | 1,5 | 1,67 | 6,22% | 17,25% | 4,8% |

Việc giảm từ 2,5 xuống 1,5 bet/100 ván (do rút 1 bet/100 ván chi tiêu) không chỉ làm rủi ro phá sản cao hơn, mà còn **làm tăng đáng kể khả năng anh ta là người thua sau chi phí**: giờ tỷ lệ thắng chỉ cách 0 chưa tới hai độ lệch chuẩn. Hãy nhớ: thắng tính tổng thể là chưa đủ; người chơi phải là người thắng, và thắng đáng kể, tính theo số tiền đưa lại vào bankroll, thì rủi ro phá sản mới dưới 1. Với người chơi chuyên nghiệp, điều này bao gồm chi phí sinh hoạt, chi phí kinh doanh, v.v. Nó cũng bao gồm các dòng tiền dương, như lương của người chơi chuyên nghiệp (nếu có) hay thu nhập từ việc đầu tư vào người chơi khác.

### 6. Bankroll ảo, tính bất đối xứng và điều kiện thay đổi (Virtual Bankroll, trang 316)

Điều trên áp dụng cả với người chơi không chuyên chỉ rút tiền khỏi bankroll sau chuỗi thắng: làm vậy giảm khả năng bankroll chịu được các đợt đi xuống tương lai và tăng rủi ro phá sản. Nhưng điều này dẫn tới một cân nhắc quan trọng khác: khái niệm **bankroll ảo** (virtual bankroll). Ta không chơi trong chân không; với người không chuyên và cả một số người chuyên, có thể có tiền chảy vào bankroll từ lương công việc khác, đầu tư hay nguồn thu nhập khác. Phân tích đầy đủ rủi ro phá sản poker cần xét mọi yếu tố này; nhưng trong một số trường hợp, điều chỉnh đại thể là đủ. Ví dụ, một người chơi nghiêm túc có việc làm lương $300.000 một năm có bankroll ảo lớn hơn nhiều bankroll hiện tại, trong khi người không có việc và rất ít kỹ năng để kiếm việc nên giữ bankroll poker cẩn thận hơn một chút, vì nó không dễ thay thế.

Điểm mấu chốt là **tác động lên rủi ro phá sản không đối xứng: phóng đại nhẹ tỷ lệ thắng khiến ta đánh giá thấp rủi ro phá sản rất nhiều, còn đánh giá thấp nhẹ tỷ lệ thắng chỉ khiến ta phóng đại rủi ro một chút.** (Minh hoạ của người tổng hợp với bankroll 300 bet, σ = 18 bet/100 ván: người chơi tin mình thắng 2,5 bet/100 ván nên tính rủi ro 0,98%. Nếu thật ra chỉ thắng 2,0, rủi ro thật là 2,46% — cao hơn 1,5 điểm phần trăm; nếu thật ra thắng 3,0, rủi ro thật là 0,39% — chỉ thấp hơn 0,6 điểm. Sai cùng 0,5 bet/100 ván nhưng thiệt hại khi lạc quan lớn hơn khoảng 2,5 lần.)

Một cân nhắc phải chi phối toàn bộ phân tích này theo cách rất quan trọng là điều kiện trò chơi không tĩnh. Trò chơi lúc lên lúc xuống, tốt hơn rồi tệ đi. Với sự xuất hiện của poker truyền hình, thế giới người chơi poker đã lớn lên rất nhiều. Đây có thể là thay đổi lâu dài, nhưng chắc chắn không được bảo đảm; poker online cũng vậy. Những điều này cũng có thể dẫn tới hiệu ứng đã bàn ở trên: các giai đoạn lợi nhuận đi lên tương quan với thay đổi thuận lợi của điều kiện. Thường khi người chơi tính chuyện chơi chuyên nghiệp, họ vừa trải qua một chuỗi thắng, có thể do điều kiện ở trò chơi ưa thích của họ thay đổi — có thể lâu dài, có thể không. Việc điều kiện thay đổi khiến phần lớn người chơi nên coi rủi ro phá sản tổng thể của mình hơi cao hơn các công thức gợi ý, vì rủi ro bị tác động mạnh hơn khi điều kiện xấu đi so với khi điều kiện tốt lên.

### 7. Các khái niệm then chốt (Key Concepts, trang 316–317)

- Khi đánh giá rủi ro phá sản trong thực tế, ta thiếu chính xác trong ước lượng tham số như tỷ lệ thắng hay độ lệch chuẩn.
- Có thể sửa một phần bằng cách giả định phân phối thật của tỷ lệ thắng là phân phối chuẩn quanh ước lượng điểm.
- Mô hình rủi ro phá sản dưới bất định là công thức rủi ro phá sản thu được, có điều chỉnh cho bất định quanh ước lượng điểm của tỷ lệ thắng.
- Phương pháp áp dụng được cho các tình huống chỉ có mẫu nhỏ, và chứa ý tưởng rằng tác động của sai số ước lượng tỷ lệ thắng không đối xứng.
- Khi cân nhắc trở thành người chơi chuyên nghiệp, hiểu biết thực tế về rủi ro là một cân nhắc quan trọng và hay bị bỏ qua.

## Luận điểm cốt lõi

### Mệnh đề

Rủi ro phá sản phải được tính như kỳ vọng trên phân phối các tỷ lệ thắng khả dĩ, không phải tại một ước lượng điểm. Với phân phối chuẩn, kết quả là công thức RoRU (23.1); nó luôn chứa một phần rủi ro Φ(−w/σ_w) — khả năng là người thua — mà không bankroll nào che được, và nó cao hơn nhiều rủi ro đơn giản khi dữ liệu ít hoặc tỷ lệ thắng sau chi phí thấp.

### Giả định

- Mọi giả định của Chương 22 (một trò chơi cố định, các lần chơi độc lập, chơi mãi, không rút tiền — trừ phần rút đã trừ vào tỷ lệ thắng).
- Kết quả đủ gần chuẩn để dùng công thức R = exp(−2wb/σ²) (không dùng cho giải đấu).
- Độ lệch chuẩn s đã biết chính xác (hội tụ nhanh); chỉ tỷ lệ thắng là bất định.
- Tỷ lệ thắng thật có phân phối chuẩn quanh w với độ lệch chuẩn σ_w = s/√N — tương đương một tiên nghiệm phẳng theo cách nhìn Bayes, không dùng thông tin về tổng thể người chơi.

### Cơ chế

1. Rủi ro phá sản là hàm lồi, giảm theo mũ khi tỷ lệ thắng tăng, và bằng 1 khi tỷ lệ thắng ≤ 0.
2. Lấy trung bình một hàm lồi trên một phân phối có độ rộng thì kết quả lớn hơn giá trị tại trung bình (bất đẳng thức Jensen — nhận xét của người tổng hợp); phần đuôi trái (tỷ lệ thắng thấp, rủi ro rất cao) chi phối.
3. Dạng mũ của cả hai hàm cho phép hoàn thành bình phương và có dạng đóng với Φ.
4. Rút tiền làm giảm tỷ lệ thắng hiệu dụng, đẩy phân phối sang trái, tăng cả rủi ro đơn giản lẫn xác suất là người thua.

### Bằng chứng và ví dụ tác giả đưa ra

- μ = 1, σ = 12, bankroll 200: rủi ro 100%, 10,84%, 6,22%, 0,387% ở tỷ lệ thắng 0; 0,8; 1; 2.
- Hình 23.1, 23.2: RoRU theo tỷ lệ thắng với σ_w = 0 tới 1, bankroll 100 và 300, σ = 10.
- Người chơi 40.000 ván, 2,5 bet/100 ván, σ = 18, bankroll 300: RoRU 3,67% so với 0,98%; sau khi rút 1 bet/100 ván: 17,25% so với 6,22%.
- Ví dụ bankroll hiệu dụng: $12.000 ở mức $20-40 nhưng bỏ sau khi thua $6.000, tức 150 bet thay vì 300.
- Thuế ở Mỹ giảm tỷ lệ thắng 30% trở lên; ví dụ bankroll ảo với lương $300.000/năm.

### Kết luận và hàm ý cho người chơi

- Dùng tỷ lệ thắng sau thuế và sau chi tiêu; dùng bankroll hiệu dụng ở mức cược đang chơi.
- Tính RoRU thay vì rủi ro đơn giản, nhất là khi có dưới vài chục nghìn ván dữ liệu.
- Nghi ngờ tỷ lệ thắng của chính mình, nhất là sau chuỗi thắng; sai về phía lạc quan đắt hơn nhiều sai về phía bi quan.
- Trước khi chơi chuyên nghiệp: tỷ lệ thắng sau chi phí phải cách 0 nhiều sai số chuẩn.

### Trong ngôn ngữ xác suất và thống kê

RoRU là kỳ vọng hậu nghiệm (posterior expectation) của xác suất phá sản theo một phân phối hậu nghiệm chuẩn N(w, σ_w²) của tham số trôi μ — phân phối thu được từ tiên nghiệm phẳng và dữ liệu chuẩn. Công thức đóng là trường hợp riêng của biến đổi Laplace của phân phối chuẩn cắt cụt: E[e^(−kX)·1{X>0}] với X ~ N(w, σ_w²), k = 2b/σ², bằng exp(−kw + k²σ_w²/2)·Φ((w − kσ_w²)/σ_w); với k = 2b/σ², k²σ_w²/2 = 2b²σ_w²/σ⁴, khớp công thức 23.1. Đây là cách làm "tích phân hoá tham số bất định" (integrating out parameter uncertainty) chuẩn trong thống kê Bayes và quản lý rủi ro mô hình.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| win rate | tỷ lệ thắng | tiền thắng trung bình mỗi giờ hoặc mỗi 100 ván |
| true win rate | tỷ lệ thắng thật | giá trị kỳ vọng μ chưa biết |
| observed win rate | tỷ lệ thắng quan sát | w tính từ dữ liệu |
| standard deviation | độ lệch chuẩn | s hoặc σ, độ phân tán kết quả mỗi đơn vị |
| standard error | sai số chuẩn | σ_w = s/√N, độ phân tán của w quanh μ |
| sample / population | mẫu / tổng thể | dữ liệu quan sát / toàn bộ khả năng |
| point estimate | ước lượng điểm | một giá trị duy nhất cho tham số |
| uncertainty distribution | phân phối bất định | phân phối các giá trị khả dĩ của tham số |
| risk of ruin (RoR) | rủi ro phá sản | xác suất mất hết bankroll |
| risk of ruin under uncertainty (RoRU) | rủi ro phá sản dưới bất định | kỳ vọng rủi ro phá sản theo phân phối tỷ lệ thắng |
| weighted risk of ruin | rủi ro phá sản có trọng số | trung bình rủi ro theo xác suất của mỗi tỷ lệ thắng |
| value function / density function | hàm giá trị / hàm mật độ | hàm cần lấy kỳ vọng / hàm xác suất |
| cumulative normal distribution function Φ | hàm phân phối chuẩn tích luỹ | diện tích bên trái z dưới đường cong chuẩn tắc |
| z-score | điểm z | số độ lệch chuẩn tính từ trung bình |
| completing the square | hoàn thành bình phương | viết x² + 2ux thành (x + u)² − u² |
| confidence interval | khoảng tin cậy | khoảng hợp lý cho tham số (Chương 3) |
| Bayesian analysis | phân tích Bayes | kết hợp tiên nghiệm với dữ liệu |
| a priori distribution | phân phối tiên nghiệm | phân phối tham số trước khi có dữ liệu |
| upswing / downswing | giai đoạn đi lên / đi xuống | chuỗi kết quả tốt / xấu |
| positive variance event | biến cố phương sai dương | kết quả tốt do may |
| selection effect | hiệu ứng chọn lọc | nhóm còn lại không đại diện cho nhóm ban đầu |
| bankroll | bankroll | vốn dành riêng để chơi poker |
| effective bankroll | bankroll hiệu dụng | số tiền sẵn sàng thua ở một mức cược |
| virtual bankroll | bankroll ảo | khả năng bổ sung vốn từ nguồn ngoài poker |
| adjusted win rate | tỷ lệ thắng điều chỉnh | sau khi trừ tiền rút ra chi tiêu |
| salary (paying yourself a salary) | lương tự trả | khoản rút cố định theo thời gian, trừ vào tỷ lệ thắng |
| drop down in limits | xuống mức cược thấp hơn | chuyển sang bàn nhỏ hơn sau khi thua |
| big bet | big bet | mức cược lớn của limit (gấp đôi small bet) |
| bet (đơn vị) | bet | một đơn vị cược lớn, ví dụ $40 ở mức $20-40 |
| limit / no-limit | limit / no-limit | mức cược cố định / không giới hạn |
| ring game | cash game | bàn chơi tiền mặt |
| lowball / hold'em | lowball / hold'em | các biến thể poker (lowball: bài thấp thắng) |
| professional player | người chơi chuyên nghiệp | sống bằng poker |
| game conditions | điều kiện trò chơi | độ mềm của đối thủ, số bàn, mức cược có sẵn |

## Câu nói đáng nhớ

> "Unfortunately, such holograms do not exist, and so we must estimate and infer." — mở đầu chương
>
> *Dịch: Tiếc là không có những hình chiếu ba chiều như vậy, nên ta phải ước lượng và suy luận.*
>
> Ý nghĩa: tỷ lệ thắng thật của mình là một tham số chưa biết, không phải một con số đọc được.

> "Having a bankroll of any size does not protect against the risk of ruin that comes from being a losing player." — mục dẫn công thức
>
> *Dịch: Bankroll lớn bao nhiêu cũng không bảo vệ được khỏi rủi ro phá sản đến từ việc là người chơi thua.*
>
> Ý nghĩa: số hạng Φ(−w/σ_w) là phần rủi ro chỉ có thể giảm bằng thêm dữ liệu hoặc chơi tốt hơn, không phải bằng thêm tiền.

> "In all honesty, overestimating one's win rate is very close to a universal property of poker players." — mục "Bankroll Considerations"
>
> *Dịch: Thành thật mà nói, phóng đại tỷ lệ thắng của mình gần như là thuộc tính phổ quát của người chơi poker.*
>
> Ý nghĩa: thiên lệch lạc quan có hệ thống, nên điều chỉnh phải đi theo một hướng.

> "We simply pay ourselves a salary denominated in some time unit and reduce our win rate by that amount." — mục "Bankroll Considerations"
>
> *Dịch: Chúng tôi đơn giản tự trả cho mình một khoản lương theo đơn vị thời gian và giảm tỷ lệ thắng đúng bằng khoản đó.*
>
> Ý nghĩa: cách đơn giản để đưa chi tiêu vào mô hình rủi ro mà không phá giả định của nó.

> "It is imperative to use a win rate that accurately characterizes not the amount of money won, but the amount of money put back into the bankroll as the game is played." — mục "Bankroll Considerations"
>
> *Dịch: Bắt buộc phải dùng tỷ lệ thắng mô tả chính xác không phải số tiền thắng được, mà số tiền được đưa lại vào bankroll trong quá trình chơi.*
>
> Ý nghĩa: rủi ro phụ thuộc vào dòng tiền ròng vào bankroll, không phải vào kết quả ở bàn.

> "Slightly overestimating your win rate causes you to underestimate your risk of ruin by a lot, while slightly underestimating it only causes you to overestimate it by a little." — mục "Virtual Bankroll"
>
> *Dịch: Phóng đại nhẹ tỷ lệ thắng khiến bạn đánh giá thấp rủi ro phá sản rất nhiều, còn đánh giá thấp nhẹ chỉ khiến bạn phóng đại rủi ro một chút.*
>
> Ý nghĩa: khi không chắc, hãy chọn tỷ lệ thắng thận trọng.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương biến một nhận xét quen thuộc ("ta không biết chắc tỷ lệ thắng của mình") thành một công thức đóng có thể tính bằng bảng tính, và cho thấy bằng số rằng bất định không phải chi tiết nhỏ: với 40.000 ván dữ liệu — nhiều hơn phần lớn người chơi nghiệp dư thời đó có — rủi ro thật vẫn gần gấp bốn rủi ro đơn giản; sau khi rút tiền sống, gần gấp ba. Phần "Bankroll Considerations" là lời khuyên thực tế hiếm có trong sách poker thời đó: tách bạch tiền thắng ở bàn với tiền đưa lại vào bankroll, coi chi tiêu như lương trừ vào tỷ lệ thắng, và định nghĩa bankroll theo số tiền sẵn sàng thua ở một mức cược. Phân tích về thiên lệch chọn mẫu ("thành công ban đầu") là một ứng dụng đúng của thống kê vào tâm lý người chơi.

### Những chỗ đơn giản hoá

- **Tiên nghiệm phẳng.** Như tác giả thừa nhận, RoRU coi mọi tỷ lệ thắng gần w đều có xác suất theo phân phối chuẩn quanh w, bỏ qua việc phần lớn người chơi poker là người thua. Theo hiểu biết của người tổng hợp, một tiên nghiệm thực tế (trung bình âm do phí rake) sẽ kéo w xuống và làm RoRU còn cao hơn; tác giả cho rằng sai lệch này nhỏ vì chỉ ở đuôi phải, nhưng với người có mẫu nhỏ và w cao, sai lệch có thể lớn.
- **Tỷ lệ thắng thật được coi là cố định.** Công thức lấy trung bình trên các tỷ lệ thắng có thể có, nhưng mỗi tỷ lệ thắng đó được giả định không đổi mãi; thực tế tỷ lệ thắng trôi theo điều kiện trò chơi, như chính tác giả bàn ở cuối chương.
- **Không cập nhật theo thời gian.** Người chơi thật tiếp tục học từ dữ liệu mới; nếu thua nhiều, họ sẽ cập nhật niềm tin và bỏ chơi trước khi phá sản. RoRU là con số "tại thời điểm hiện tại" cho chiến lược chơi mãi không đổi.
- **Độ lệch chuẩn coi như biết chắc**; trong no-limit, độ lệch chuẩn ước lượng cũng hội tụ chậm hơn vì đuôi dày.
- **Giới hạn ở phân phối chuẩn**, nên không dùng được cho giải đấu — nơi bất định về tỷ lệ thắng (ROI) còn lớn hơn nhiều.
- **Bảng so sánh bị mất** trong bản PDF này nên người đọc thiếu một bộ số tham chiếu của chính tác giả; bảng người tổng hợp tính bổ sung chỉ dựa vào công thức 23.1.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- Sau 2006, sự bùng nổ poker online (chương nhắc tới như một thay đổi chưa chắc lâu dài) đã kết thúc ở Mỹ với luật UIGEA (cuối 2006) và "Black Friday" (2011); các trò chơi trở nên khó hơn nhiều khi người chơi mạnh học từ phần mềm và solver. Đây chính là loại "điều kiện trò chơi thay đổi" làm tỷ lệ thắng quá khứ trở thành ước lượng quá cao cho tương lai mà chương cảnh báo.
- Người chơi online ngày nay có cơ sở dữ liệu hàng triệu ván, nên σ_w nhỏ hơn nhiều; nhưng tỷ lệ thắng ở mức cao thường chỉ 1–5 big blind/100 ván với độ lệch chuẩn 80–100 big blind/100 ván, nên vẫn cần hàng trăm nghìn ván để chắc chắn mình là người thắng.
- Các công cụ "variance calculator" và "bankroll calculator" trực tuyến phổ biến hiện tính cả khoảng tin cậy của tỷ lệ thắng, gần với tinh thần RoRU.

### Liên hệ các chương khác

- [C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md): phương sai của tổng nhiều kết quả và sai số chuẩn s/√N.
- [C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md): định nghĩa Φ(z), khoảng tin cậy, cảnh báo về việc bỏ qua phân phối tiên nghiệm, và ước lượng Bayes tỷ lệ thắng.
- [C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md): mô hình rủi ro phá sản, công thức chuẩn 22.4, phương trình 22.3 và lời cảnh báo về rút tiền mà chương này lượng hoá.
- [C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md): xuống mức cược thấp hơn khi thua (chủ đề "sẽ bàn sau" của chương này) và tiêu chuẩn Kelly.
- [C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md): đầu tư vào người chơi khác (dòng tiền dương mà chương nhắc) và thoả thuận tài trợ.

### Vận dụng

- **Người chơi poker:** tính σ_w = s/√N từ dữ liệu của mình; nếu w/σ_w < 2, coi như chưa chắc mình là người thắng. Dùng tỷ lệ thắng sau thuế, sau rake và sau chi tiêu; tính RoRU (vài ô Excel với NORM.S.DIST). Trước khi bỏ việc để chơi chuyên nghiệp, đặt ngưỡng: RoRU với tỷ lệ thắng sau chi tiêu dưới vài phần trăm, và tỷ lệ thắng sau chi tiêu cách 0 ít nhất 2–3 sai số chuẩn.
- **Người làm tài chính và đầu tư:** bài học trực tiếp là rủi ro tham số (parameter risk). Một quỹ có lợi nhuận vượt trội ước lượng từ 3 năm dữ liệu có sai số chuẩn rất lớn; tính xác suất cạn vốn hay vỡ hạn mức thua lỗ tại ước lượng điểm sẽ đánh giá thấp rủi ro, và sai về phía lạc quan đắt hơn sai về phía bi quan. Hiệu ứng "thành công ban đầu" chính là thiên lệch sống sót (survivorship bias) trong đánh giá nhà quản lý quỹ: người được giao thêm vốn thường là người vừa gặp may. Nguyên tắc "trừ lương khỏi tỷ lệ thắng" tương ứng với việc tính tỷ lệ rút vốn bền vững của quỹ hưu trí hay quỹ tài trợ (endowment): nếu tỷ lệ rút gần bằng lợi nhuận kỳ vọng, xác suất cạn vốn tăng vọt.
- **Người ra quyết định nói chung:** khi một quyết định không đảo ngược được (bỏ việc, dồn vốn) dựa trên một ước lượng từ dữ liệu ngắn, hãy tính kết quả trên cả phân phối các giá trị khả dĩ, đặc biệt là đuôi xấu, và nhớ rằng thời điểm ta muốn mạo hiểm nhất thường là ngay sau giai đoạn may mắn nhất.

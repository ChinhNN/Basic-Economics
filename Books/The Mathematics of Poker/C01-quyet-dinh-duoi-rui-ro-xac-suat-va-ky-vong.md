# Chương 1 — Quyết định dưới rủi ro: xác suất và kỳ vọng (Decisions Under Risk: Probability and Expectation)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), trang mở Phần I "Basics" (trang 15) và Chương 1 "Decisions Under Risk: Probability and Expectation", trang 16–25.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Phần Giới thiệu ([00-gioi-thieu.md](00-gioi-thieu.md)) đã nêu lời khuyên duy nhất xuyên suốt cuốn sách là "tối đa hoá lợi nhuận trung bình" và hứa rằng Phần I sẽ đặt nền xác suất, phân phối và kỳ vọng. Chương 1 làm đúng việc đó: giải thích vì sao sách dùng tiền thắng trong ván thay cho độ thoả dụng, định nghĩa xác suất, các quy tắc cộng và nhân xác suất, phân phối xác suất, và **kỳ vọng** — đại lượng mà mọi phân tích về sau tìm cách tối đa hoá. Chương 2 ([C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md)) bổ sung phương sai và độ lệch chuẩn để đo kết quả thực tế lệch khỏi kỳ vọng bao xa; Chương 3 ([C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md)) dùng xác suất có điều kiện của chương này để dựng định lý Bayes. Ký hiệu phân phối tay bài (ví dụ {AA, KK, QQ, AKs, AKo}) và ký hiệu kỳ vọng ⟨X⟩, ⟨A, B⟩ được dùng ở mọi chương sau, đặc biệt Phần II ([C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md), [C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md), [C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md)). Các khái niệm rủi ro phá sản, tiêu chuẩn Kelly và giá trị tương đương chắc chắn được nhắc ở đầu chương được để dành cho Phần IV ([C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md), [C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md)).
**Ý chính:** **Trong poker, mọi quyết định đều được đưa ra trước khi kết quả được biết, nên công cụ đúng để đánh giá quyết định là kỳ vọng — tổng giá trị các kết cục nhân xác suất của chúng; kỳ vọng có tính cộng, nên người chơi giỏi thắng bằng cách liên tục nhận các "ván cược nhỏ" có kỳ vọng dương.** Chương mở đầu bằng việc thừa nhận người ta chơi poker vì nhiều lý do (giao lưu, giải trí, thi đấu, nghiện, tiền tài trợ) và độ thoả dụng của tiền không tuyến tính — với đa số người, chắc chắn có 5 triệu đô la đáng giá hơn nhiều so với 50% cơ hội có 10 triệu. Nhưng vì mỗi người có đường thoả dụng riêng, sách dùng tiền thắng trong ván làm thước đo thay thế và giả định người chơi có đủ vốn. **Xác suất** được định nghĩa là giới hạn của tỷ lệ số lần sự kiện xảy ra trên số lần thử khi số lần thử tiến tới vô cùng, p(x) = lim n₀/n. Từ các giả định 52 lá bài và mỗi lá có khả năng như nhau, sách tính p(lá bài là át) = 4 × 1/52 = 1/13 (cộng được vì các sự kiện **xung khắc**). Sự kiện **độc lập** thì xác suất đồng thời bằng tích: p(cơ và át) = (1/13)(1/4) = 1/52; với hai sự kiện bất kỳ, p(A hoặc B) = p(A) + p(B) − p(A và B), nên p(cơ hoặc át) = 1/4 + 1/13 − 1/52 = 4/13. Sự kiện **phụ thuộc** cần **xác suất có điều kiện**: p(A và B) = p(A) p(B|A); vì vậy xác suất được chia đôi át là (1/13)(3/51) = 1/221. Các ví dụ khác: hai con sáu khi gieo hai xúc xắc 1/36; được chia AA, KK hoặc QQ là 3/221; hai lá cùng chất ra flush ngay ở flop là (11/50)(10/49)(9/48) = 33/3920, dưới 1% một chút (0,84%). **Phân phối xác suất** là danh sách đầy đủ các kết cục xung khắc kèm xác suất; trong poker, tay bài của đối thủ được biểu diễn bằng một phân phối. **Kỳ vọng** ⟨P⟩ = Σ pᵢxᵢ: tung đồng xu ăn thua 10 đô la có kỳ vọng 0; được trả 11 đô la khi thắng và mất 10 khi thua có kỳ vọng +0,50 đô la mỗi lần; cược 30 ăn 1 vào hai con sáu có kỳ vọng −5/36 đô la, khoảng −14 xu. Chương kết thúc bằng ký hiệu kỳ vọng giữa hai phân phối ⟨A, B⟩, quy tắc nhân và cộng hằng số vào kỳ vọng, và khái niệm **odds** (tỷ lệ cược) — tỷ số giữa xác suất sự kiện không xảy ra và xác suất nó xảy ra.

> **Lưu ý:**
> - **Phạm vi trang:** mục lục in trong sách ghi Chương 1 bắt đầu ở trang 15; theo chân trang của bản PDF này, trang 15 là trang mở Phần I (câu đề từ của Einstein), Chương 1 ở trang 16–25.
> - **Ký hiệu "cho biết" bị hỏng trong bản PDF dựng lại:** khắp chương, dấu gạch đứng "|" của xác suất có điều kiện p(B|A) bị in thành dấu "∨" (p(B∨A)), và ở vài chỗ thành ký tự "¿"; câu "Likewise, ¿ is the symbol for 'given'" (trang 19) vốn là "| là ký hiệu của 'cho biết'". Các tích hai phân số, như (1/13)(1/4) ở trang 18, cũng in thành "(1/13 ¿ (1/4)". Công thức (1.11) in thành "¿P≥Σ pᵢxᵢ", đúng ra là ⟨P⟩ = Σ pᵢxᵢ; dòng chữ đi kèm "has a value xᵢ and a probability then pᵢ then P's expected value" bị xáo trộn, ý đúng là "có giá trị xᵢ và xác suất pᵢ, thì kỳ vọng của P là". Công thức (1.9) và (1.10) dùng gạch ngang trên đầu (Ā) cho biến cố bù; lớp chữ làm mất gạch ngang. Bản tổng hợp viết lại tất cả theo ký hiệu chuẩn.
> - **Lỗi tính trong sách (in sai, kết quả đúng):** ở ví dụ flush trên flop (trang 22), dòng thứ hai in p(A∩B) = (1/50)(10/49); đúng là (11/50)(10/49), vì p(A) = 11/50 như vừa nêu ở trang 21. Tích in sai cho 10/2450 = 1/245, còn tích đúng cho 110/2450 = 11/245 — khớp với kết quả 11/245 sách ghi ở dòng sau. Kết quả cuối 33/3920 ≈ 0,84% là đúng (người tổng hợp kiểm tra thêm bằng tổ hợp: C(11,3)/C(50,3) = 165/19.600 = 33/3920).
> - **Lỗi tính trong sách (in sai, kết quả đúng):** kỳ vọng của trò tung đồng xu 11 ăn 10 (trang 24) in là ⟨Bₙ⟩ = (1/2)(+$11) + (1/2)(−$11); đúng là (1/2)(+$11) + (1/2)(−$10) = $5,50 − $5,00 = $0,50. Biểu thức in sai cho kết quả 0, mâu thuẫn với kết quả $0,50 sách ghi ở dòng sau.
> - **Lỗi trong mục Key Concepts (trang 25):** gạch đầu dòng thứ ba viết "kỳ vọng là tổng của các *xác suất* của kết cục nhân với xác suất của chúng"; đúng là tổng các *giá trị* của kết cục nhân xác suất (gạch đầu dòng thứ năm nói đúng ý này).
> - **Lỗi đánh máy khác (có trên ảnh trang):** câu đề từ của Einstein in "As for as" hai lần, đúng là "As far as" (trang 15); "produce *no* occurrences" trong định nghĩa xác suất (trang 17) đúng là "produce n₀ occurrences" (n₀ lần xảy ra), vì công thức (1.1) dùng n₀; "fifty-cards" (trang 18) thiếu "two"; "Probability of A or 8 occurring" (trang 18) đúng là "A or B"; "Equation 1.9 can also be restarted" (trang 21) đúng là "restated"; "hi terms of probability" đúng là "In terms"; "⟨A, QO|B⟩" (trang 25) đúng là "⟨A, QQ|B⟩"; "-lay", "tiring", "deterrnine", "Tins", "Tire", "50°/o" lần lượt là "play", "thing", "determine", "This", "The", "50%".
> - **Nhãn "For dependent events" của công thức (1.5) hẹp hơn thực tế (nhận xét của người tổng hợp):** p(A∩B) = p(A) p(B|A) đúng với mọi cặp sự kiện có p(A) > 0, không chỉ sự kiện phụ thuộc — chính sách cũng nói (1.3) là trường hợp riêng của (1.5). Tương tự, khẳng định "nếu p(B|A) = p(B) thì p(A|B) = p(A)" cần p(A) > 0 và p(B) > 0.
> - **Hai quy ước odds trái chiều (nhận xét của người tổng hợp):** sách định nghĩa odds là tỷ số (xác suất không xảy ra) : (xác suất xảy ra), tức "odds chống lại", nên "7 to 5" nghĩa là xác suất xảy ra 5/12 ≈ 41,7%. Nhưng ngay sau đó, ví dụ "7 to 3 favorite" được giải thích là 70% thắng, tức tỷ số (xảy ra) : (không xảy ra). Cả hai cách nói đều phổ biến trong poker; chữ "favorite" (cửa trên) báo hiệu thứ tự thứ hai. Bản tổng hợp ghi rõ thứ tự mỗi khi dùng odds.
> - **Trùng ký hiệu:** chữ A và B được dùng cho sự kiện (A: lá đầu là át), cho tên người chơi, và cho tên phân phối tay bài của họ (A = {AA, KK, QQ, JJ, AKo, AKs}); chữ C vừa là "sự kiện chắc chắn" (1.7) vừa là phân phối của đồng xu; chữ D vừa là phân phối xúc xắc vừa là sự kiện A∩B trong ví dụ flush. Bản tổng hợp giữ ký hiệu của sách nhưng nói rõ nghĩa ở từng chỗ.
> - **Quy ước:** số thập phân viết bằng dấu phẩy (0,50 đô la); "$" giữ nguyên trong công thức chép từ sách.

## Sơ đồ

### Phần I — Cơ bản (Part I: Basics, trang 15)

```text
       Trang mở Phần I chỉ có câu đề từ của Albert Einstein:
       "Chừng nào các định luật toán học nói về thực tại, chúng không chắc
       chắn; chừng nào chúng chắc chắn, chúng không nói về thực tại."
                                │
                                ▼
       Ý nghĩa với cuốn sách: mô hình toán của poker chỉ chính xác trong
       phạm vi giả định của nó; Phần I (Chương 1–3) trang bị xác suất, kỳ
       vọng, phương sai và định lý Bayes để dựng các mô hình đó
```

### Phần mở đầu Chương 1 — vì sao dùng tiền thay cho độ thoả dụng (trang 16)

```text
       Người ta chơi poker vì nhiều lý do: giao lưu, giải trí, thi đấu,
       nghiện cờ bạc; có cả động lực tiền ngoài ván (người vô địch giải
       chính WSOP nhận thêm tiền tài trợ, xuất hiện…); có cả yếu tố tâm
       lý (thua thêm một ván có thể là cú sốc)
                                │
                                ▼
       Ngay cả khi chỉ xét tiền, sở thích về tiền KHÔNG TUYẾN TÍNH:
       chắc chắn có 5 triệu đô la đáng giá hơn nhiều so với 50% cơ hội có
       10 triệu (giá trị biên của 5 triệu thứ hai nhỏ hơn nhiều)
                                │
                                ▼
       Lý thuyết độ thoả dụng (utility theory) gom tất cả vào một thước đo,
       nhưng mỗi người có đường thoả dụng riêng → phân tích tổng quát rất
       khó
                                │
                                ▼
       QUY ƯỚC CỦA SÁCH: dùng tiền thắng trong ván làm thước đo thay cho
       độ thoả dụng; giả định người chơi có đủ vốn (bankroll) và chỉ muốn
       tối đa hoá tiền thắng bằng quyết định tốt nhất ở mọi điểm
       · rủi ro phá sản, tiêu chuẩn Kelly, giá trị tương đương chắc chắn
         để dành cho Phần IV
       · tối đa hoá tiền thắng ⇔ tối đa hoá KỲ VỌNG của từng quyết định
       · nguồn tham khảo: Richard Epstein, The Theory of Gambling and
         Statistical Logic (1967)
```

### Mục "Probability" — xác suất là gì và xác suất một lá là át (trang 16–17)

```text
       Bài của đối thủ chưa biết, nhưng luật chơi và thành phần bộ bài cho
       ta thông tin (đối thủ có thể cầm J-10 cơ, không thể cầm thứ ngoài
       bộ bài)
                                │
                                ▼
       ĐỊNH NGHĨA (1.1): nếu n lần thử cho n₀ lần sự kiện x xảy ra thì
                 p(x) = lim (n → ∞) n₀ / n
       · ví dụ: chia hàng triệu tay hold'em, tỷ lệ tay AA hội tụ về 1/221
                                │
                                ▼
       Thay vì chia mười tỷ tay, CHIA NHỎ bài toán:
       · giả định: 52 lá, mỗi lá có khả năng như nhau
       · p(lá cụ thể, ví dụ át bích) = 1/52
       · p(lá là át) = p(át bích HOẶC át cơ HOẶC át rô HOẶC át nhép)
                     = 4 × 1/52 = 1/13
       · được cộng thẳng vì bốn sự kiện XUNG KHẮC (không lá nào vừa là át
         bích vừa là át cơ)
       · 1/13 cũng chính là (số át)/(tổng số lá)
```

### Mục "Independent Events" — sự kiện độc lập và quy tắc "hoặc" tổng quát (trang 17–18)

```text
       Hai sự kiện KHÔNG xung khắc: "lá là cơ" (1/4) và "lá là át" (1/13)
       · không cộng thẳng được, vì có lá vừa là cơ vừa là át
                                │
                                ▼
       ĐỘC LẬP: xác suất cùng xảy ra bằng tích hai xác suất
       · ví dụ: giá đóng cửa chỉ số NASDAQ và kết quả xúc xắc ở một sòng
         ở Monaco tối đó
       · XÁC SUẤT ĐỒNG THỜI p(cơ và át) = (1/13)(1/4) = 1/52 (chính là
         át cơ); "là cơ" không đổi khả năng "là át" vì mỗi chất có đủ 13 lá
                                │
                                ▼
       Sự kiện độc lập không xung khắc, trừ khi một trong hai có xác suất 0
                                │
                                ▼
       QUY TẮC "HOẶC" CHO MỌI SỰ KIỆN: cộng hai xác suất rồi trừ phần đếm
       hai lần
       · p(cơ hoặc át) = 1/4 + 1/13 − 1/52 = 13/52 + 4/52 − 1/52 = 16/52
                       = 4/13 (13 lá cơ và 3 át khác)
```

### Mục "Dependent Events" (phần 1) — phụ thuộc, xác suất có điều kiện và các công thức (trang 18–20)

```text
       PHỤ THUỘC: một sự kiện làm thay đổi khả năng của sự kiện kia
       · cầu thủ ném bóng chày: 3% khả năng ném trọn trận không để đối
         phương ghi điểm; đội của anh ta 60% khả năng thắng; p(cả hai)
         KHÔNG phải 60% × 3% = 1,8%, mà gần 3%, vì khi anh ta ném như vậy
         đội gần như chắc thắng
       · XÁC SUẤT CÓ ĐIỀU KIỆN p(A|B): khả năng A xảy ra NẾU B xảy ra
                                │
                                ▼
       Ký hiệu: p(A ∪ B) "p của A hoặc B"; p(A ∩ B) "p của A và B";
                p(A|B) "p của A cho biết B"
       ┌──────────────────────┬────────────────────────────────────────┐
       │ xung khắc            │ p(A ∪ B) = p(A) + p(B)            (1.2)│
       │ độc lập              │ p(A ∩ B) = p(A) p(B)              (1.3)│
       │ mọi sự kiện          │ p(A ∪ B) = p(A)+p(B) − p(A ∩ B)   (1.4)│
       │ phụ thuộc (thực ra   │ p(A ∩ B) = p(A) p(B|A)            (1.5)│
       │ đúng cho mọi sự kiện)│                                        │
       └──────────────────────┴────────────────────────────────────────┘
       · (1.2) là (1.4) khi p(A ∩ B) = 0; (1.3) là (1.5) khi p(B|A) = p(B)
                                │
                                ▼
       ÁP DỤNG: xác suất được chia đôi át
       · A: lá đầu là át, p(A) = 1/13; B: lá thứ hai là át
       · chia không hoàn lại nên phụ thuộc: p(B|A) = 3/51 = 1/17
       · p(A ∩ B) = (1/13)(1/17) = 1/221 ≈ 0,45%
                                │
                                ▼
       TÍNH CHẤT CƠ BẢN (Ā: A không xảy ra; C: sự kiện chắc chắn;
       I: sự kiện không thể):
       0 ≤ p(A) ≤ 1 (1.6); p(C) = 1 (1.7); p(I) = 0 (1.8);
       p(A) + p(Ā) = 1 (1.9), hay p(A) = 1 − p(Ā) (1.10)
```

### Mục "Dependent Events" (phần 2) — ba bài tập áp dụng (trang 21–22)

```text
       ┌──────────────────────────────┬──────────────────────────────────┐
       │ Hai con sáu khi gieo hai     │ độc lập, (1.3):                  │
       │ xúc xắc                      │ (1/6)(1/6) = 1/36 ≈ 2,78%        │
       ├──────────────────────────────┼──────────────────────────────────┤
       │ Một người được chia AA, KK   │ xung khắc, (1.2):                │
       │ hoặc QQ                      │ 1/221 + 1/221 + 1/221 = 3/221    │
       │                              │ ≈ 1,36%                          │
       ├──────────────────────────────┼──────────────────────────────────┤
       │ Hai lá tẩy cùng chất ra      │ phụ thuộc, (1.5) hai lần:        │
       │ flush ngay ở flop (cả ba lá  │ p(A) = 11/50, p(B|A) = 10/49,    │
       │ flop cùng chất đó)           │ p(C|A∩B) = 9/48                  │
       │                              │ (11/50)(10/49) = 11/245          │
       │                              │ (11/245)(9/48) = 33/3920 ≈ 0,84% │
       └──────────────────────────────┴──────────────────────────────────┘
```

### Mục "Probability Distributions" (phần 1) — phân phối xác suất và phân phối tay bài (trang 22–23)

```text
       Một xác suất đơn lẻ thường không đủ; cần xét nhiều xác suất cùng
       lúc → PHÂN PHỐI XÁC SUẤT: ghép mỗi kết cục với xác suất của nó
       · đồng xu: C = {(sấp, 1/2), (ngửa, 1/2)}
       · xúc xắc: D = {(1, 1/6), (2, 1/6), …, (6, 1/6)}
       · danh sách kết cục phải ĐẦY ĐỦ và XUNG KHẮC
       · cùng một sự kiện vật lý có thể cho nhiều phân phối:
         D' = {(lẻ, 1/2), (chẵn, 1/2)}
                                │
                                ▼
       Trong poker: hiếm khi đoán được đúng hai lá của đối thủ, nên biểu
       diễn bài của họ bằng một PHÂN PHỐI TAY BÀI
       · đầu ván, phân phối của mọi người như nhau
       · ván tiến triển: dùng hành động, bài mình, bài chung để liên tục
         chỉnh các xác suất
```

### Mục "Probability Distributions" (phần 2) — kỳ vọng và ba ván cược với người bạn (trang 23–24)

```text
       Gán giá trị số cho từng kết cục: cược tung đồng xu ăn thua 10 đô la
       C' = {(thắng, 1/2), (thua, 1/2)}  →  B = {(+$10, 1/2), (−$10, 1/2)}
                                │
                                ▼
       KỲ VỌNG (EV) = tổng (giá trị × xác suất); ký hiệu ⟨X⟩
                 ⟨P⟩ = Σ (i = 1..n) pᵢ xᵢ                         (1.11)
                                │
                                ▼
       ┌──────────────────────────┬────────────────────────────────────┐
       │ Ván cược                 │ Kỳ vọng mỗi lần                    │
       ├──────────────────────────┼────────────────────────────────────┤
       │ B: đồng xu, thắng +10,   │ (1/2)(10) + (1/2)(−10) = 0         │
       │ thua −10                 │ (bằng kỳ vọng của việc không cược) │
       ├──────────────────────────┼────────────────────────────────────┤
       │ Bₙ: đồng xu, thắng +11,  │ (1/2)(11) + (1/2)(−10) = +0,50 đô  │
       │ thua −10                 │ (không lần nào thắng đúng 50 xu;   │
       │                          │ chỉ đúng tính trung bình)          │
       ├──────────────────────────┼────────────────────────────────────┤
       │ B_d: hai con sáu thắng   │ 30/36 − 35/36 = −5/36 ≈ −0,14 đô   │
       │ +30, còn lại thua −1     │ → không nhận; cược này có thật     │
       │                          │ trên bàn craps khắp thế giới       │
       └──────────────────────────┴────────────────────────────────────┘
                                │
                                ▼
       KỲ VỌNG CÓ TÍNH CỘNG: kỳ vọng của sáu ván cược liên tiếp bằng tổng
       kỳ vọng từng ván
       · đời sống đầy những "ván tung đồng xu nhỏ" (bảo hiểm, quỹ trái
         phiếu…); đồ uống miễn phí ở Las Vegas được trả bằng hàng triệu
         ván mà sòng có lợi thế nhỏ
       · người chơi poker giỏi liên tục nhận các tình huống kỳ vọng dương
```

### Mục "Probability Distributions" (phần 3) — ký hiệu phân phối tay bài, phép toán trên kỳ vọng và odds (trang 24–25)

```text
       Phân phối tay bài không ghi xác suất ⇒ tỷ lệ giữa các tay giữ nguyên
       như lúc chia bài
       · người chơi rất chặt chỉ raise với AA, KK, QQ, AK:
         H = {AA, KK, QQ, AKs, AKo}
                                │
                                ▼
       Ký hiệu kỳ vọng giữa hai phân phối, ví dụ
       A = {AA, KK, QQ, JJ, AKo, AKs}, B = {AA, KK, QQ}:
       · ⟨A, B⟩: kỳ vọng khi chơi phân phối A đấu phân phối B
       · ⟨A, AA|B⟩: kỳ vọng của phân phối A đấu tay AA rút từ B
       · ⟨AA|A, AA|B⟩: kỳ vọng của AA thuộc A đấu AA thuộc B
       · ⟨A, B⟩ = p(AA)⟨A, AA|B⟩ + p(KK)⟨A, KK|B⟩ + p(QQ)⟨A, QQ|B⟩
                                │
                                ▼
       Phép toán trên phân phối:
       · nhân mọi giá trị với hằng số k → kỳ vọng nhân với k
       · cộng hằng số c vào mọi giá trị → kỳ vọng cộng thêm c
                                │
                                ▼
       ODDS = (xác suất không xảy ra) : (xác suất xảy ra), viết "7 to 5",
       "3 to 2"…; odds "ngắn" là sự kiện dễ xảy ra hơn, odds "dài" là khó
       xảy ra hơn
       · "tay này là cửa trên 7 to 3" nghĩa là thắng 70%
       · odds khó dùng trong tính toán vì không nhân thẳng với kết cục để
         ra kỳ vọng; dân cờ bạc dùng odds vì tiền trả theo odds
```

### Mục "Key Concepts" — các khái niệm chính (trang 25)

```text
       · Xác suất của một kết cục: tỷ lệ số lần kết cục xảy ra trên một số
         rất lớn lần thử
       · Phân phối xác suất: danh sách đầy đủ, xung khắc các kết cục ghép
         với xác suất của chúng
       · Kỳ vọng của một phân phối có giá trị: tổng (giá trị × xác suất)
         của các kết cục (sách in nhầm "xác suất × xác suất")
       · Kỳ vọng có tính cộng
       · Cách tiếp cận toán học với poker chủ yếu quan tâm tới việc tối đa
         hoá kỳ vọng
```

## Ba câu hỏi chương này trả lời

1. **Nên dùng thước đo nào để đánh giá một quyết định poker?** Về lý thuyết, thứ cần tối đa hoá là độ thoả dụng, vì tiền có giá trị biên giảm dần (chắc chắn có 5 triệu đô la tốt hơn nhiều so với 50% cơ hội có 10 triệu). Nhưng mỗi người có đường thoả dụng riêng, nên sách dùng tiền thắng trong ván làm thước đo thay thế, với giả định người chơi có đủ vốn; khi đó mục tiêu là tối đa hoá kỳ vọng của từng quyết định. Các vấn đề rủi ro (rủi ro phá sản, tiêu chuẩn Kelly) để dành cho Phần IV.
2. **Tính xác suất trong poker bằng những quy tắc nào?** Xác suất là giới hạn của tần suất, p(x) = lim n₀/n. Sự kiện xung khắc thì cộng: p(át) = 4 × 1/52 = 1/13. Mọi sự kiện: p(A ∪ B) = p(A) + p(B) − p(A ∩ B), nên p(cơ hoặc át) = 4/13. Sự kiện độc lập thì nhân: hai con sáu = 1/36. Sự kiện phụ thuộc dùng xác suất có điều kiện: p(A ∩ B) = p(A) p(B|A), nên p(AA) = (1/13)(3/51) = 1/221 và p(flush ngay ở flop với hai lá cùng chất) = (11/50)(10/49)(9/48) = 33/3920 ≈ 0,84%. Ngoài ra 0 ≤ p ≤ 1 và p(A) + p(Ā) = 1.
3. **Kỳ vọng là gì và vì sao nó là nền của chiến thắng?** Kỳ vọng là tổng giá trị các kết cục nhân xác suất, ⟨P⟩ = Σ pᵢxᵢ. Một cược công bằng (đồng xu ăn thua 10 đô) có kỳ vọng 0; được trả 11 khi thắng, mất 10 khi thua có kỳ vọng +0,50 đô la; cược 30 ăn 1 vào hai con sáu có kỳ vọng −5/36 ≈ −0,14 đô la. Vì kỳ vọng có tính cộng, kết quả dài hạn là tổng của vô số "ván cược nhỏ", và người chơi giỏi thắng bằng cách luôn chọn phương án có kỳ vọng lớn hơn — giống sòng bạc sống nhờ lợi thế nhỏ trên hàng triệu ván.

## Khái niệm cần biết

- **Độ thoả dụng (utility) và giá trị biên (marginal value):** độ thoả dụng là mức "đáng giá" chủ quan của một kết cục với một người; giá trị biên là phần thoả dụng tăng thêm khi có thêm một đơn vị. Ví dụ: với đa số người, chắc chắn có 5 triệu đô la đáng giá hơn 50% cơ hội có 10 triệu, dù kỳ vọng bằng tiền như nhau (0,5 × 10 = 5 triệu), vì 5 triệu thứ hai có giá trị biên nhỏ hơn 5 triệu đầu. Quan trọng vì đây là lý do sách phải nêu rõ giả định dùng tiền thay cho độ thoả dụng.
- **Đủ vốn (adequately bankrolled):** có lượng tiền dành cho poker đủ lớn so với mức cược để những dao động ngắn hạn không đe doạ khả năng tiếp tục chơi. Ví dụ: người có 100 đô la chơi ván mà một tay có thể mất 50 đô la thì không đủ vốn. Quan trọng vì chỉ khi đủ vốn, tối đa hoá kỳ vọng mới trùng với tối đa hoá độ thoả dụng.
- **Xác suất (probability):** giới hạn của tỷ lệ số lần sự kiện xảy ra trên số lần thử khi số lần thử tiến tới vô cùng, p(x) = lim n₀/n. Ví dụ: tỷ lệ tay hold'em là AA hội tụ về 1/221 ≈ 0,45%, tức khoảng một lần trong 221 tay. Quan trọng vì mọi tính toán của sách bắt đầu từ đây.
- **Sự kiện xung khắc (mutually exclusive events):** hai sự kiện không thể cùng xảy ra. Ví dụ: lá bài là át bích và lá bài là át cơ. Khi đó p(A hoặc B) = p(A) + p(B), nên p(át) = 4/52 = 1/13.
- **Sự kiện độc lập (independent events) và xác suất đồng thời (joint probability):** độc lập khi xác suất cả hai cùng xảy ra (xác suất đồng thời) bằng tích hai xác suất. Ví dụ: p(cơ và át) = (1/4)(1/13) = 1/52. Lưu ý độc lập khác xung khắc: hai sự kiện độc lập (với xác suất dương) luôn có thể cùng xảy ra.
- **Sự kiện phụ thuộc (dependent events) và xác suất có điều kiện (conditional probability):** phụ thuộc khi một sự kiện làm thay đổi khả năng của sự kiện kia; p(B|A) là xác suất B xảy ra nếu biết A đã xảy ra. Ví dụ: biết lá đầu là át thì p(lá thứ hai là át) = 3/51 = 1/17 thay vì 1/13. Quan trọng vì bài được chia không hoàn lại, nên hầu hết sự kiện về lá bài trong poker là phụ thuộc.
- **Chia không hoàn lại (dealt without replacement):** lá đã chia không quay lại bộ bài. Ví dụ: sau khi ta cầm hai lá cơ, chỉ còn 11 lá cơ trong 50 lá. Đây là nguồn gốc của sự phụ thuộc giữa các lá bài.
- **Biến cố bù (complement):** sự kiện "A không xảy ra", ký hiệu Ā, p(Ā) = 1 − p(A). Ví dụ: p(không được chia AA) = 1 − 1/221 = 220/221.
- **Phân phối xác suất (probability distribution):** danh sách đầy đủ, xung khắc các kết cục, mỗi kết cục kèm xác suất. Ví dụ: D = {(1, 1/6), …, (6, 1/6)} cho một con xúc xắc; D' = {(lẻ, 1/2), (chẵn, 1/2)} từ cùng con xúc xắc đó. Quan trọng vì tay bài của đối thủ được mô tả bằng phân phối.
- **Phân phối tay bài (distribution of hands):** tập các tay bài đối thủ có thể cầm kèm xác suất; khi không ghi xác suất, tỷ lệ giữa các tay giữ như lúc chia. Ví dụ (người tổng hợp tính): H = {AA, KK, QQ, AKs, AKo} gồm 6 + 6 + 6 + 4 + 12 = 34 tổ hợp lá, nên AA, KK, QQ mỗi loại chiếm 6/34 ≈ 17,6%, AKs 4/34 ≈ 11,8%, AKo 12/34 ≈ 35,3%. Quan trọng vì đây là đối tượng chính của Phần II.
- **Kỳ vọng (expected value, EV):** tổng giá trị các kết cục nhân xác suất, ⟨P⟩ = Σ pᵢxᵢ. Ví dụ: cược đồng xu 11 ăn 10 có kỳ vọng 0,5 × 11 − 0,5 × 10 = +0,50 đô la. Quan trọng vì đây là đại lượng mà cả cuốn sách tìm cách tối đa hoá.
- **Tính cộng của kỳ vọng (additivity):** kỳ vọng của nhiều ván cược bằng tổng kỳ vọng từng ván. Ví dụ: chơi cược 11 ăn 10 một trăm lần có kỳ vọng 100 × 0,50 = 50 đô la. Quan trọng vì nó cho phép đánh giá từng quyết định riêng rẽ.
- **Ký hiệu ⟨A, B⟩:** kỳ vọng khi chơi phân phối tay bài A đấu phân phối tay bài B; ⟨A, AA|B⟩ là kỳ vọng của A đấu riêng tay AA của B. Ví dụ: ⟨A, B⟩ = p(AA)⟨A, AA|B⟩ + p(KK)⟨A, KK|B⟩ + p(QQ)⟨A, QQ|B⟩. Quan trọng vì đây là ký hiệu chuẩn cho mọi phân tích "phân phối đấu phân phối".
- **Odds (tỷ lệ cược):** tỷ số giữa xác suất sự kiện không xảy ra và xác suất nó xảy ra. Ví dụ: hai con sáu có xác suất 1/36, odds chống lại là 35 to 1; odds "7 to 5" (chống lại) ứng với xác suất 5/12 ≈ 41,7%. Quan trọng vì tiền thưởng trong cờ bạc và pot odds trong poker (Chương 4) đều nói bằng odds.

## Nội dung chi tiết

### 1. Trang mở Phần I: Cơ bản (Part I: Basics, trang 15)

Trang 15 chỉ có tên phần "Part I: Basics" và câu đề từ của Albert Einstein: "Chừng nào các định luật toán học nói về thực tại, chúng không chắc chắn; và chừng nào chúng chắc chắn, chúng không nói về thực tại." (Sách in nhầm "As for as" thay cho "As far as".) Người tổng hợp hiểu câu đề từ như một lời cảnh báo sẽ quay lại suốt cuốn sách: các kết quả toán học trong sách là chắc chắn bên trong mô hình, nhưng mô hình luôn đơn giản hơn ván poker thật.

### 2. Lý do chơi poker, độ thoả dụng và giả định của sách (phần mở đầu Chương 1, trang 16)

Có bao nhiêu người chơi thì có bấy nhiêu lý do chơi poker. Có người chơi vì giao lưu, để thấy mình thuộc về một nhóm; có người chơi để giải trí; nhiều người chơi vì thích thi đấu; có người chơi để thoả mãn cơn nghiện cờ bạc hoặc che giấu nỗi đau khác trong đời. Một khó khăn của cách tiếp cận toán học là rất khó định lượng giá trị của niềm vui hay cảm giác được thuộc về.

Ngoài các lý do khó định lượng, còn có những động lực tài chính nằm ngoài bản thân ván bài. Chẳng hạn, người vô địch giải chính của World Series of Poker gần như chắc chắn thu thêm một khoản lớn từ hợp đồng quảng cáo, xuất hiện trước công chúng…, ngoài giải nhất vốn đã lớn. Cũng có những cân nhắc khác ở bàn chơi: có người thấy thua thêm một ván là cú sốc tâm lý lớn. Có thể chê quan điểm đó là phi lý, nhưng một phân tích đầy đủ về động lực chơi poker vẫn phải tính tới nó.

Ngay cả khi chỉ xét phần thưởng bằng tiền, sở thích về tiền cũng **không tuyến tính**. Với đa số người, thắng chắc 5 triệu đô la đáng giá hơn nhiều (có **độ thoả dụng** cao hơn nhiều) so với 50% cơ hội thắng 10 triệu: 5 triệu đô la đã thay đổi cuộc đời của đa số người, và **giá trị biên** của 5 triệu thêm vào nhỏ hơn nhiều. (Người tổng hợp lưu ý: hai lựa chọn có cùng kỳ vọng bằng tiền, 0,5 × 10 triệu = 5 triệu; sự khác biệt chỉ nằm ở độ thoả dụng.)

Theo nghĩa rộng, tất cả những vấn đề này thuộc nhánh **lý thuyết độ thoả dụng** (utility theory) của kinh tế học. Các nhà lý thuyết độ thoả dụng tìm cách định lượng sở thích của từng cá nhân và dựng một khuôn khổ trong đó động lực tài chính và phi tài chính so sánh trực tiếp được với nhau. Thực ra thứ ta tìm cách tối đa hoá khi chơi poker (và khi làm bất cứ việc gì) là độ thoả dụng. Nhưng dùng lý thuyết độ thoả dụng làm nền phân tích gặp một khó khăn: mỗi người có đường thoả dụng riêng, nên phân tích tổng quát trở nên cực kỳ khó.

Vì vậy, sách **không xét độ thoả dụng mà dùng tiền thắng trong ván làm thước đo thay thế**. Ở phần lý thuyết bankroll (vốn dành cho poker) trong Phần IV, sách sẽ xem kỹ một số cân nhắc "metagame" (nằm ngoài từng ván) và giới thiệu các khái niệm **rủi ro phá sản**, **tiêu chuẩn Kelly** và **giá trị tương đương chắc chắn** (certainty equivalent — số tiền chắc chắn mà một người coi là ngang giá với một ván cược rủi ro) — tất cả là thước đo rủi ro chủ yếu liên quan tới các yếu tố ngoài ván. Trừ khi nói rõ, sách lấy làm tiền đề rằng người chơi có đủ vốn cho mức cược họ đang chơi, và mục đích duy nhất của họ là tối đa hoá tiền thắng bằng cách ra quyết định tốt nhất ở mọi thời điểm.

Tối đa hoá tổng tiền thắng trong poker đòi hỏi người chơi tối đa hoá **kỳ vọng** của các quyết định. Trước khi giới thiệu khái niệm nền tảng này, sách cần bàn về xác suất. Phần tiếp theo chịu ơn nhiều cuốn *The Theory of Gambling and Statistical Logic* (1967) của Richard Epstein, một sách nhập môn có giá trị về xác suất và cờ bạc.

### 3. Xác suất (Probability, trang 16–17)

Phần lớn quyết định trong poker được đưa ra khi kết quả chưa được xác định. Khi người chia bài chia bài đầu ván, bài của các người chơi là chưa biết, ít nhất là cho tới khi được nhìn thấy. Nhưng ta vẫn có một số thông tin về bài của người khác. Luật chơi giới hạn những gì họ có thể cầm: một người có thể cầm J-10 cơ, nhưng không thể cầm "át-hoàng tử của bàn bi-a" (ví dụ đùa của sách cho một thứ không có trong bộ bài). Thành phần của bộ bài được ấn định trước và cho ta thông tin về các tay bài.

Xét một tay hold'em (thể loại mỗi người nhận hai lá úp riêng và dùng chung năm lá lật dần trên bàn). Khả năng tay đó gồm hai lá át là bao nhiêu? Có thể bạn đã biết, nhưng hãy nghĩ câu trả lời nghĩa là gì. Nếu chia một triệu tay như thế, sẽ có bao nhiêu đôi át? Nếu chia mười triệu? Qua thời gian và nhiều lần thử, tỷ lệ số đôi át trên tổng số tay được chia sẽ hội tụ về một con số cụ thể. Sách định nghĩa **xác suất** là con số đó. Xác suất là chìa khoá của việc ra quyết định trong poker vì nó cho một khuôn khổ toán học để đánh giá khả năng của các sự kiện bất định.

Nếu n lần thử một thí nghiệm (như chia một tay hold'em) cho n₀ lần xảy ra sự kiện x, xác suất p(x) được định nghĩa là:

```text
p(x) = lim (n → ∞) n₀ / n                                           (1.1)
```

Đọc là: xác suất của x bằng giới hạn của tỷ số n₀/n khi số lần thử n tăng lên vô cùng.

Khả năng một tay hold'em là đôi át là 1/221. Có thể xác định điều này bằng cách chia mười tỷ tay và quan sát tỷ lệ đôi át, nhưng làm vậy lâu và khó; tốt hơn là chia bài toán thành các phần. Trước hết xét một lá: xác suất một lá là át là bao nhiêu? Bài toán này còn chia nhỏ hơn được: xác suất một lá là át bích là bao nhiêu?

Câu hỏi cuối trả lời được trực tiếp với hai giả định:

- Một bộ bài chuẩn có 52 lá.
- Mỗi lá đều có khả năng như nhau.

Khi đó xác suất một lá cụ thể được rút là 1/52. Nếu khả năng lá đó là át bích là 1/52, khả năng lá đó là một át bất kỳ là bao nhiêu? Điều này tương đương với khả năng lá đó là át bích HOẶC át cơ HOẶC át rô HOẶC át nhép. Có bốn át trong bộ bài, mỗi át có khả năng 1/52; cộng các xác suất lại:

```text
p(A) = (4)(1/52)
p(A) = 1/13
```

(Ở đây A là sự kiện "lá bài là át".) Ta cộng thẳng được vì các sự kiện này **xung khắc**: không lá nào vừa là át bích vừa là át cơ. Xác suất 1/13 đúng bằng tỷ số (số át trong bộ bài)/(tổng số lá); quan hệ này đúng như phép cộng các xác suất riêng lẻ.

### 4. Sự kiện độc lập (Independent Events, trang 17–18)

Có những sự kiện không xung khắc. Xét hai sự kiện: (1) lá bài là cơ; (2) lá bài là át. Nếu muốn tính xác suất một lá là cơ HOẶC là át: có 13 lá cơ trong 52 lá, nên khả năng lá là cơ là 1/4; khả năng lá là át, như trên, là 1/13. Nhưng không cộng thẳng hai xác suất được, vì một lá có thể vừa là át vừa là cơ.

Có hai loại quan hệ giữa các sự kiện. Loại thứ nhất là các sự kiện không ảnh hưởng gì tới nhau. Ví dụ: giá đóng cửa của chỉ số chứng khoán NASDAQ và kết quả gieo xúc xắc ở bàn craps (trò xúc xắc trong sòng bạc) ở một sòng tại Monaco tối hôm đó về cơ bản không liên quan; không sự kiện nào ảnh hưởng tới sự kiện kia theo cách đáng kể. Nếu xác suất cả hai sự kiện cùng xảy ra bằng tích các xác suất riêng lẻ, ta nói hai sự kiện **độc lập**. Xác suất cả A và B cùng xảy ra gọi là **xác suất đồng thời** của A và B.

Trong ví dụ này, xác suất đồng thời một lá vừa là cơ vừa là át là (1/13)(1/4) = 1/52. Lý do là việc lá bài là cơ không làm thay đổi khả năng nó là át — cả bốn chất đều có cùng một bộ 13 lá.

Sự kiện độc lập không xung khắc, trừ khi một trong hai sự kiện có xác suất bằng không. Trong ví dụ, tổng số lá cơ là 13 và tổng số át là 4; nhưng cộng hai số này là đếm hai lần một lá (át cơ). Thực ra có 13 lá cơ và 3 át khác, hoặc nói cách khác, 4 át và 12 lá cơ khác. Áp dụng tổng quát: **xác suất ít nhất một trong hai sự kiện không xung khắc A và B xảy ra bằng tổng xác suất của A và B trừ xác suất đồng thời của A và B.** Vậy xác suất lá bài là cơ hoặc át bằng khả năng là cơ (1/4) cộng khả năng là át (1/13) trừ khả năng là cả hai (1/52):

```text
p(cơ hoặc át) = 1/4 + 1/13 − 1/52 = 13/52 + 4/52 − 1/52 = 16/52 = 4/13
```

Kết quả 16/52 khớp với cách đếm trực tiếp: 13 lá cơ cộng 3 át không phải cơ là 16 lá. Quy tắc này đúng với mọi sự kiện, độc lập hay phụ thuộc.

### 5. Sự kiện phụ thuộc và các công thức xác suất (Dependent Events, trang 18–20)

Ngược lại, có những sự kiện ảnh hưởng tới nhau. Ví dụ bóng chày: trước trận, một cầu thủ ném bóng (pitcher) tài năng có thể có 3% khả năng ném trọn chín hiệp mà không để đối phương ghi điểm nào (một "shutout"), còn đội của anh ta có 60% khả năng thắng trận. Khả năng đội thắng VÀ anh ta ném shutout rõ ràng không phải 60% × 3% (bằng 1,8%). Thay vào đó, nó rất gần chính 3%, vì khi cầu thủ này làm được điều đó, đội anh ta gần như luôn thắng. Các sự kiện như vậy gọi là **phụ thuộc**. Ta cũng xét **xác suất có điều kiện** của A khi biết B: khả năng A xảy ra nếu B xảy ra. Xác suất cả A và B cùng xảy ra với sự kiện phụ thuộc bằng xác suất của A nhân với xác suất có điều kiện của B khi biết A. Hai sự kiện độc lập khi xác suất có điều kiện của A khi biết B bằng xác suất của riêng A.

Ký hiệu (bản PDF in dấu "|" thành "∨"):

| Ký hiệu | Nghĩa | Cách đọc |
|---|---|---|
| p(A ∪ B) | xác suất A hoặc B xảy ra | "p của A hoặc B" |
| p(A ∩ B) | xác suất A và B cùng xảy ra | "p của A và B" |
| p(A\|B) | xác suất có điều kiện của A khi B đã xảy ra | "p của A cho biết B" |

Ký hiệu ∪ (hợp) và ∩ (giao) đến từ lý thuyết tập hợp; tác giả thích các từ thông thường "hoặc" và "và".

Các công thức:

```text
Sự kiện xung khắc:   p(A ∪ B) = p(A) + p(B)                         (1.2)
Sự kiện độc lập:     p(A ∩ B) = p(A) p(B)                           (1.3)
Mọi sự kiện:         p(A ∪ B) = p(A) + p(B) − p(A ∩ B)              (1.4)
Sự kiện phụ thuộc:   p(A ∩ B) = p(A) p(B|A)                         (1.5)
```

Công thức (1.2) chỉ là trường hợp riêng của (1.4) cho sự kiện xung khắc, khi p(A ∩ B) = 0. Tương tự, (1.3) là trường hợp riêng của (1.5), vì với sự kiện độc lập p(B|A) = p(B). Thêm nữa, nếu p(B|A) = p(B) thì p(A|B) = p(A) (tức tính độc lập có tính đối xứng; người tổng hợp bổ sung: cần p(A) > 0 và p(B) > 0).

**Áp dụng: xác suất được chia đôi át.** Quay lại câu hỏi: một tay hold'em chia từ bộ bài đầy đủ chứa hai át với tần suất nào? Có hai sự kiện:

- A: lá thứ nhất là át.
- B: lá thứ hai là át.

p(A) = 1/13, và p(B) cũng bằng 1/13 (nếu chưa biết gì về lá thứ nhất). Nhưng hai sự kiện phụ thuộc: nếu A xảy ra (lá đầu là át), B ít có khả năng xảy ra hơn, vì bài được chia không hoàn lại. p(B|A) là khả năng lá thứ hai là át khi biết lá thứ nhất là át. Còn ba át trong 51 lá, nên p(B|A) = 3/51 = 1/17.

```text
p(A ∩ B) = p(A) p(B|A)
p(A ∩ B) = (1/13)(1/17)
p(A ∩ B) = 1/221
```

(Người tổng hợp kiểm tra bằng tổ hợp: số cặp hai át là C(4,2) = 6, tổng số cặp hai lá là C(52,2) = 1.326, và 6/1.326 = 1/221 ≈ 0,45%.)

**Các tính chất đơn giản khác.** Xác suất của mọi sự kiện ít nhất bằng 0 và không lớn hơn 1: theo định nghĩa, n lần thử không bao giờ cho nhiều hơn n lần xảy ra và không ít hơn 0 lần. Xác suất của sự kiện chắc chắn xảy ra là 1; của sự kiện không bao giờ xảy ra là 0. Xác suất của **biến cố bù** — sự kiện không xảy ra — bằng 1 trừ xác suất của sự kiện. Ký hiệu Ā là "A không xảy ra", C là một sự kiện chắc chắn, I là một sự kiện không thể:

```text
0 ≤ p(A) ≤ 1   với mọi A                                            (1.6)
p(C) = 1                                                            (1.7)
p(I) = 0                                                            (1.8)
p(A) + p(Ā) = 1                                                     (1.9)
p(A) = 1 − p(Ā)                                                     (1.10)
```

Công thức (1.10) chỉ là cách viết lại (1.9).

### 6. Ba bài tập áp dụng: hai con sáu, AA/KK/QQ và flush ngay ở flop (cuối mục Dependent Events, trang 21–22)

**Hai con sáu.** Khả năng gieo hai xúc xắc được hai con sáu dùng công thức (1.3), vì hai lần gieo độc lập. Gọi A là "xúc xắc thứ nhất ra sáu", B là "xúc xắc thứ hai ra sáu":

```text
p(A ∩ B) = p(A) p(B) = (1/6)(1/6) = 1/36
```

tức khoảng 2,78%.

**Được chia AA, KK hoặc QQ.** Dùng (1.2), vì ba sự kiện xung khắc (một người không thể cùng lúc cầm hai đôi khác nhau với hai lá):

```text
p(AA) = 1/221,  p(KK) = 1/221,  p(QQ) = 1/221
p({AA, KK, QQ}) = p(AA) + p(KK) + p(QQ) = 3/221
```

tức khoảng 1,36%. (Người tổng hợp bổ sung: xác suất được chia một đôi bất kỳ là 13 × 1/221 = 1/17 ≈ 5,9%.)

**Hai lá cùng chất ra flush ngay ở flop.** Ta cầm hai lá của một chất (chất sẽ làm flush — năm lá cùng chất), còn lại 11 lá chất đó trong bộ bài. Cả ba lá flop (ba lá chung đầu tiên) phải thuộc chất đó. Đặt:

- A: lá flop thứ nhất thuộc chất flush;
- B: lá thứ hai thuộc chất flush, khi biết lá thứ nhất thuộc chất flush;
- C: lá thứ ba thuộc chất flush, khi biết hai lá đầu đều thuộc chất flush.

```text
p(A)       = 11/50   (đã bỏ ra hai lá trong tay người chơi)
p(B|A)     = 10/49   (đã bỏ ra một lá chất flush trên flop; tổng cộng ba lá
                      không còn trong bộ bài)
p(C|A ∩ B) = 9/48    (đã bỏ ra hai lá chất flush trên flop; tổng cộng bốn lá)
```

Áp dụng (1.5):

```text
p(A ∩ B) = p(A) p(B|A) = (11/50)(10/49) = 110/2450 = 11/245
```

(Sách in nhầm dòng giữa thành (1/50)(10/49); xem khối Lưu ý.) Đặt D = A ∩ B rồi dùng (1.5) lần nữa:

```text
p(D ∩ C)     = p(D) p(C|D)
p(A ∩ B ∩ C) = p(A ∩ B) p(C|A ∩ B)
p(A ∩ B ∩ C) = (11/245)(9/48)
p(A ∩ B ∩ C) = 33/3920
```

tức khoảng 0,84%, "ít hơn 1% một chút". Kiểm tra bằng tổ hợp: số cách chọn 3 lá từ 11 lá chất flush là C(11,3) = 165; số flop có thể là C(50,3) = 19.600; 165/19.600 = 33/3920.

Tác giả kết luận rằng các quy tắc này áp dụng được cho gần như mọi tình huống và sẽ được dùng trong cả sách để tính xác suất của các sự kiện đơn lẻ.

### 7. Phân phối xác suất (Probability Distributions, trang 22–23)

Xác suất của từng sự kiện đơn lẻ quan trọng, nhưng thường không đủ để phân tích trọn vẹn một tình huống; thường cần xét nhiều xác suất cùng lúc. Có thể mô tả các kết cục có thể có của một sự kiện cùng xác suất của chúng bằng một **phân phối xác suất**.

Xét việc tung một đồng xu công bằng. Có hai kết cục, xung khắc nhau, mỗi kết cục có xác suất 1/2. Ghép mỗi kết cục với xác suất của nó, ta được hai cặp: (sấp, 1/2) và (ngửa, 1/2). Nếu C là phân phối xác suất của kết quả tung đồng xu:

```text
C = {(sấp, 1/2), (ngửa, 1/2)}
```

Tương tự, phân phối xác suất của một lần gieo xúc xắc sáu mặt công bằng:

```text
D = {(1, 1/6), (2, 1/6), (3, 1/6), (4, 1/6), (5, 1/6), (6, 1/6)}
```

Có thể dựng một **phân phối xác suất rời rạc** cho bất kỳ sự kiện nào bằng cách liệt kê một danh sách **đầy đủ** (không sót kết cục nào) và **xung khắc** (không hai kết cục nào cùng xảy ra) các kết cục có thể có, rồi ghép mỗi kết cục với xác suất tương ứng. Vì thế có thể dựng nhiều phân phối khác nhau từ cùng một sự kiện vật lý. Từ lần gieo xúc xắc trên, ta cũng dựng được phân phối của tính chẵn lẻ:

```text
D' = {(lẻ, 1/2), (chẵn, 1/2)}
```

Trong poker, ta gần như luôn rất quan tâm tới bài của đối thủ. Nhưng hiếm khi thu hẹp được ước đoán xuống đúng một cặp lá. Thay vào đó, ta dùng một phân phối xác suất để biểu diễn các tay bài đối thủ có thể cầm và xác suất tương ứng họ cầm từng tay. Đầu ván, trước khi ai nhìn bài, phân phối tay bài của mọi người chơi giống hệt nhau. Khi ván tiến triển, ta đưa thông tin mới thu được — qua cách chơi, qua bài trong tay mình, qua bài chung trên bàn… — vào để liên tục tinh chỉnh ước lượng xác suất cho từng tay bài có thể có.

### 8. Kỳ vọng và ba ván cược với người bạn (Probability Distributions, tiếp, trang 23–24)

Đôi khi có thể gắn một giá trị số với mỗi phần tử của phân phối. Giả sử một người bạn rủ tung một đồng xu công bằng; người thắng nhận 10 đô la từ người thua. Kết quả tung theo phân phối C ở trên. Vì đồng xu công bằng, ai gọi và gọi mặt nào không quan trọng, nên có thể xác định một phân phối thứ hai là kết quả của ván cược:

```text
C' = {(thắng, 1/2), (thua, 1/2)}
```

Tiếp theo, gắn giá trị số cho từng kết quả: thắng thì bạn trả ta 10 đô la, thua thì ta trả bạn 10 đô la:

```text
B = {(+$10, 1/2), (−$10, 1/2)}
```

Khi mỗi kết cục của phân phối có giá trị số, ta tính được **kỳ vọng** (expected value, EV) của phân phối: giá trị của mỗi kết cục nhân với xác suất của nó, rồi cộng tất cả. Trong cả sách, ký hiệu ⟨X⟩ nghĩa là "kỳ vọng của X". Với ví dụ này:

```text
⟨B⟩ = (1/2)(+$10) + (1/2)(−$10)
⟨B⟩ = $5 + (−$5)
⟨B⟩ = 0
```

Điều này hiển nhiên về trực giác: tung đồng xu công bằng ăn thua một khoản bằng nhau thì một nửa số lần thắng, một nửa số lần thua, khoản tiền như nhau, nên trung bình hoà vốn. Kỳ vọng của việc từ chối lời mời (không tung) cũng bằng 0, vì không có tiền đổi tay.

Tổng quát, với phân phối P gồm n kết cục, kết cục thứ i có giá trị xᵢ và xác suất pᵢ, kỳ vọng của P là:

```text
⟨P⟩ = Σ (i = 1..n) pᵢ xᵢ                                            (1.11)
```

Cốt lõi của việc thắng trong poker hay bất kỳ loại cờ bạc nào là ý tưởng **tối đa hoá kỳ vọng**. Trong ví dụ trên, người bạn đưa ra một cược công bằng: trung bình, tung với bạn không làm ta tốt hơn hay tệ hơn so với từ chối.

**Ván cược thứ hai — 11 ăn 10.** Giả sử người bạn đưa ra một đề nghị khác, tốt hơn: vẫn tung đồng xu, nhưng khi ta thắng, bạn trả 11 đô la, còn khi bạn thắng, ta chỉ trả 10 đô la. Kỳ vọng của việc không tung vẫn là 0, nhưng kỳ vọng của việc tung không còn bằng 0. Kỳ vọng của ván cược mới Bₙ:

```text
⟨Bₙ⟩ = (1/2)(+$11) + (1/2)(−$10)
⟨Bₙ⟩ = $5,50 − $5,00
⟨Bₙ⟩ = $0,50
```

(Sách in nhầm số hạng thứ hai thành −$11; xem khối Lưu ý.) Trung bình ta thắng 50 xu mỗi lần tung. Tất nhiên đây không phải thắng chắc; thực tế không lần tung nào ta thắng đúng 50 xu. Con số kỳ vọng chỉ tồn tại khi tính gộp; nhưng làm như vậy, trung bình ta hơn 50 xu so với từ chối.

**Ván cược thứ ba — hai con sáu trả 30.** Người bạn đề nghị: gieo một cặp xúc xắc một lần; nếu ra hai con sáu, bạn trả ta 30 đô la; nếu ra bất cứ kết quả nào khác, ta trả bạn 1 đô la. Kỳ vọng:

```text
⟨B_d⟩ = (+$30)(1/36) + (−$1)(35/36)
⟨B_d⟩ = $30/36 − $35/36
⟨B_d⟩ = −$5/36
```

khoảng −14 xu (5/36 ≈ 0,139). Giá trị của ván cược này với ta là khoảng âm 14 xu; kỳ vọng của việc không chơi là 0, nên đây là cược xấu và không nên nhận. Tác giả đùa: hãy bảo bạn quay lại với đề nghị 11 ăn 10 khi tung đồng xu. Cũng lưu ý rằng đúng cược này có trên bàn craps khắp thế giới. (Người tổng hợp bổ sung: odds thật của hai con sáu là 35 to 1, nhưng sòng chỉ trả 30 to 1; phần chênh lệch là lợi thế của sòng, 5/36 ≈ 13,9% số tiền cược.)

**Tính cộng của kỳ vọng.** Một tính chất rất quan trọng của kỳ vọng là nó **có tính cộng**: kỳ vọng của sáu ván cược khác nhau liên tiếp bằng tổng kỳ vọng của từng ván. Hầu hết trò cờ bạc — và thực ra hầu hết mọi thứ trong đời — đều như vậy. Ta liên tục được mời những ván tung đồng xu hay gieo xúc xắc nhỏ, có ván kỳ vọng dương, có ván kỳ vọng âm. Đôi khi sự kiện không phải là gieo xúc xắc hay tung đồng xu mà là một hợp đồng bảo hiểm hay một quỹ trái phiếu. Đồ uống miễn phí và đèn neon ở Las Vegas được trả bằng tổng của hàng triệu ván tung đồng xu nhỏ, mỗi ván sòng bạc có một lợi thế nhỏ. Người chơi poker giỏi tận dụng tính cộng này bằng cách liên tục nắm lấy các tình huống có kỳ vọng thuận lợi.

### 9. Ký hiệu phân phối tay bài, phép toán trên kỳ vọng và odds (Probability Distributions, phần cuối, trang 24–25)

**Phân phối tay bài không ghi xác suất.** Khi dùng phân phối xác suất để bàn về poker, sách thường không ghi xác suất cụ thể cho từng tay. Khi đó, điều đó nghĩa là xác suất tương đối giữa các tay không thay đổi so với lúc bắt đầu ván. Giả sử ta thấy một người chơi rất chặt (tight — chỉ chơi ít tay mạnh) raise, và theo kinh nghiệm ta biết họ raise khi và chỉ khi cầm AA, KK, QQ hoặc AK; có thể biểu diễn phân phối tay bài của họ là:

```text
H = {AA, KK, QQ, AKs, AKo}
```

(AKs: át và già cùng chất; AKo: át và già khác chất.) Việc không ghi xác suất ở đây chỉ hàm ý xác suất tương đối của các tay như lúc chia. Người tổng hợp tính minh hoạ: mỗi đôi có C(4,2) = 6 tổ hợp lá, AKs có 4 tổ hợp (một cho mỗi chất), AKo có 4 × 4 − 4 = 12 tổ hợp, tổng 34; nên trong phân phối H:

| Tay | Số tổ hợp lá | Xác suất trong H |
|---|---:|---:|
| AA | 6 | 6/34 ≈ 17,6% |
| KK | 6 | 6/34 ≈ 17,6% |
| QQ | 6 | 6/34 ≈ 17,6% |
| AKs | 4 | 4/34 ≈ 11,8% |
| AKo | 12 | 12/34 ≈ 35,3% |
| Tổng | 34 | 100% |

(Bảng này bỏ qua ảnh hưởng của các lá ta đang cầm.)

**Ký hiệu kỳ vọng giữa hai phân phối.** Ký hiệu ⟨X⟩ cũng dùng được khi có nhiều phân phối. Giả sử hai người chơi A và B có bài rút từ các phân phối:

```text
A = {AA, KK, QQ, JJ, AKo, AKs}
B = {AA, KK, QQ}
```

Khi đó:

| Ký hiệu | Nghĩa |
|---|---|
| ⟨A, B⟩ | kỳ vọng khi chơi phân phối A đấu phân phối B |
| ⟨A, AA\|B⟩ | kỳ vọng khi chơi phân phối A đấu tay AA rút từ phân phối B |
| ⟨AA\|A, AA\|B⟩ | kỳ vọng khi chơi AA thuộc A đấu AA thuộc B |

và

```text
⟨A, B⟩ = p(AA)⟨A, AA|B⟩ + p(KK)⟨A, KK|B⟩ + p(QQ)⟨A, QQ|B⟩
```

tức kỳ vọng tổng là trung bình có trọng số của kỳ vọng đấu từng tay của B, trọng số là xác suất B cầm tay đó (sách in nhầm "QO" thay cho "QQ").

**Phép toán trên phân phối.** Có thể làm vài phép toán cơ bản trên các phần tử của phân phối. Nếu nhân mọi giá trị kết cục với một hằng số thực, kỳ vọng của phân phối mới bằng kỳ vọng ban đầu nhân hằng số đó. Nếu cộng một hằng số vào mọi giá trị kết cục, kỳ vọng mới bằng kỳ vọng ban đầu cộng hằng số đó. (Ví dụ của người tổng hợp: nhân đôi tiền cược của ván 11 ăn 10 thành 22 ăn 20 thì kỳ vọng thành 2 × 0,50 = 1 đô la; viết dưới dạng công thức: ⟨kX + c⟩ = k⟨X⟩ + c.)

**Odds.** Sách mô tả một cách biểu diễn xác suất phổ biến: **odds**, định nghĩa là tỷ số giữa xác suất sự kiện không xảy ra và xác suất sự kiện xảy ra. Odds có thể quy về bất kỳ cơ số tiện lợi nào và thường được nói như "7 to 5", "3 to 2"… Odds **ngắn hơn** là khi sự kiện dễ xảy ra hơn; odds **dài hơn** là khi sự kiện khó xảy ra hơn. Giá trị tương đối của hai tay bài thường được nói theo kiểu: "Tay đó là cửa trên (favorite) 7 to 3 so với tay kia", nghĩa là nó có 70% khả năng thắng. (Người tổng hợp lưu ý: theo định nghĩa của sách, odds "7 to 5" chống lại một sự kiện ứng với xác suất 5/(7 + 5) = 5/12 ≈ 41,7%; còn "cửa trên 7 to 3" đọc theo thứ tự ngược lại, xác suất thắng 7/(7 + 3) = 70%.)

Odds thường khó dùng hơn xác suất trong tính toán, vì không thể nhân thẳng odds với kết cục để ra kỳ vọng. Dân cờ bạc thực thụ hay dùng odds, vì odds tương ứng với cách họ được trả tiền khi thắng cược. Xác suất mang tính khái niệm toán học hơn. Người chơi cờ bạc biết dùng toán có thể dùng cả hai, nhưng thường thích xác suất hơn vì dễ chuyển thành kỳ vọng.

### 10. Các khái niệm chính (Key Concepts, trang 25)

Sách tóm tắt chương bằng sáu ý:

- Xác suất của một kết cục của một sự kiện là tỷ lệ số lần kết cục đó xảy ra trên một số rất lớn lần thử sự kiện.
- Phân phối xác suất là việc ghép một danh sách đầy đủ và xung khắc các kết cục của một sự kiện với xác suất tương ứng.
- Kỳ vọng của một phân phối có gắn giá trị là tổng các giá trị của kết cục nhân với xác suất của chúng (sách in nhầm "tổng các xác suất của kết cục nhân với xác suất").
- Kỳ vọng có tính cộng.
- Nếu mỗi kết cục của một phân phối được gắn với một giá trị số, kỳ vọng của phân phối là tổng các tích xác suất và kết cục.
- Cách tiếp cận toán học với poker chủ yếu quan tâm tới việc tối đa hoá kỳ vọng.

## Luận điểm cốt lõi

### Mệnh đề

Trong poker, quyết định được đưa ra trước khi biết kết quả; vì vậy chất lượng của quyết định phải được đo bằng kỳ vọng của nó, không phải bằng kết quả của một lần chơi. Người chơi tối đa hoá tiền thắng dài hạn bằng cách ở mỗi điểm quyết định chọn phương án có kỳ vọng lớn nhất.

### Giả định

- Tiền thắng trong ván là thước đo thay thế hợp lý cho độ thoả dụng.
- Người chơi có đủ vốn, nên không cần lo rủi ro phá sản (vấn đề này để dành cho Phần IV).
- Bộ bài có 52 lá, mỗi lá có khả năng như nhau (bài được xào ngẫu nhiên).
- Xác suất được hiểu theo nghĩa tần suất dài hạn.

### Cơ chế

1. Định nghĩa xác suất là tần suất giới hạn, p(x) = lim n₀/n.
2. Chia bài toán phức tạp thành các sự kiện đơn giản; ghép lại bằng quy tắc cộng (xung khắc, hoặc trừ phần giao) và quy tắc nhân (độc lập, hoặc dùng xác suất có điều kiện cho sự kiện phụ thuộc).
3. Mô tả mọi kết cục có thể có bằng một phân phối xác suất; trong poker, mô tả bài của đối thủ bằng phân phối tay bài và cập nhật nó khi có thông tin.
4. Gắn giá trị tiền cho từng kết cục và tính kỳ vọng ⟨P⟩ = Σ pᵢxᵢ.
5. So kỳ vọng của các phương án (kể cả phương án không tham gia, kỳ vọng 0) và chọn phương án lớn nhất.
6. Nhờ tính cộng, cộng dồn kỳ vọng của nhiều quyết định thành kết quả dài hạn.

### Bằng chứng và ví dụ tác giả đưa ra

- 5 triệu đô la chắc chắn so với 50% cơ hội có 10 triệu (độ thoả dụng không tuyến tính).
- p(át) = 1/13; p(cơ và át) = 1/52; p(cơ hoặc át) = 4/13.
- Cầu thủ ném bóng: 3% ném shutout, đội 60% thắng; p(cả hai) gần 3% chứ không phải 1,8%.
- p(AA) = 1/221; p(hai con sáu) = 1/36; p(AA, KK hoặc QQ) = 3/221; p(flush ngay ở flop) = 33/3920 ≈ 0,84%.
- Ba ván cược: đồng xu 10 ăn 10 (kỳ vọng 0), 11 ăn 10 (+0,50 đô la), hai con sáu 30 ăn 1 (−5/36 ≈ −0,14 đô la).
- Phân phối tay bài của người chơi chặt: {AA, KK, QQ, AKs, AKo}.

### Kết luận và hàm ý cho người chơi

- Đánh giá quyết định bằng kỳ vọng, không bằng kết quả của một ván: không lần tung nào thắng đúng 50 xu, nhưng cược 11 ăn 10 vẫn là cược tốt.
- Luôn so với phương án "không tham gia" (kỳ vọng 0): một cược có kỳ vọng âm nên từ chối, dù có lúc thắng lớn (30 đô la).
- Nghĩ về bài của đối thủ như một phân phối, không phải một tay cụ thể; đếm tổ hợp lá để biết tỷ lệ giữa các tay.
- Vì kỳ vọng có tính cộng, nhiều quyết định nhỏ có lợi thế nhỏ cộng lại thành lợi nhuận lớn — đúng cách sòng bạc kiếm tiền.

### Trong ngôn ngữ xác suất

Chương trình bày cách hiểu xác suất theo tần suất (frequentist), các tiên đề cơ bản (0 ≤ p ≤ 1, p(Ω) = 1, cộng tính cho sự kiện xung khắc), công thức bao hàm–loại trừ cho hai tập (1.4), quy tắc nhân p(A ∩ B) = p(A)p(B|A) và định nghĩa độc lập. Phân phối xác suất rời rạc được viết như tập các cặp (kết cục, xác suất); kỳ vọng là E[X] = Σ pᵢxᵢ, với tính chất tuyến tính E[kX + c] = kE[X] + c và E[X + Y] = E[X] + E[Y] (tính cộng, đúng cả khi X và Y không độc lập — chi tiết này sách không nói rõ). Ký hiệu ⟨A, B⟩ = Σ p(h)⟨A, h|B⟩ chính là công thức kỳ vọng toàn phần (law of total expectation) theo tay bài h của B.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| decision under risk | quyết định dưới rủi ro | quyết định đưa ra khi kết quả chưa biết nhưng xác suất có thể ước lượng |
| utility, utility theory | độ thoả dụng, lý thuyết độ thoả dụng | mức đáng giá chủ quan của một kết cục; nhánh kinh tế học định lượng sở thích |
| marginal value | giá trị biên | phần giá trị tăng thêm khi có thêm một đơn vị |
| non-linear preference for money | sở thích tiền không tuyến tính | gấp đôi tiền không gấp đôi độ thoả dụng |
| proxy | thước đo thay thế | đại lượng dùng thay cho đại lượng khó đo |
| bankroll, adequately bankrolled | bankroll, đủ vốn | vốn dành cho poker; vốn đủ lớn so với mức cược |
| meta-game | metagame | các quyết định bên ngoài từng ván |
| risk of ruin | rủi ro phá sản | xác suất mất hết vốn |
| Kelly criterion | tiêu chuẩn Kelly | quy tắc chọn quy mô cược để tăng vốn nhanh nhất về dài hạn |
| certainty equivalent | giá trị tương đương chắc chắn | khoản tiền chắc chắn được coi là ngang giá với một cược rủi ro |
| probability | xác suất | giới hạn của tần suất xảy ra khi số lần thử tiến tới vô cùng |
| trial | lần thử | một lần thực hiện thí nghiệm ngẫu nhiên |
| mutually exclusive | xung khắc | không thể cùng xảy ra |
| independent events | sự kiện độc lập | xác suất cùng xảy ra bằng tích hai xác suất |
| joint probability | xác suất đồng thời | xác suất hai sự kiện cùng xảy ra |
| dependent events | sự kiện phụ thuộc | sự kiện này làm đổi khả năng sự kiện kia |
| conditional probability | xác suất có điều kiện | xác suất A khi biết B đã xảy ra, p(A\|B) |
| union (∪) / intersection (∩) | hợp / giao | "hoặc" / "và" trong ngôn ngữ tập hợp |
| complement | biến cố bù | sự kiện "không xảy ra", p(Ā) = 1 − p(A) |
| certain event / impossible event | sự kiện chắc chắn / sự kiện không thể | xác suất 1 / xác suất 0 |
| without replacement | không hoàn lại | lá đã chia không quay lại bộ bài |
| probability distribution | phân phối xác suất | danh sách đầy đủ, xung khắc các kết cục kèm xác suất |
| discrete distribution | phân phối rời rạc | phân phối có các kết cục đếm được |
| exhaustive | đầy đủ | không bỏ sót kết cục nào |
| expected value (EV), ⟨X⟩ | kỳ vọng | tổng giá trị kết cục nhân xác suất |
| additive | có tính cộng | kỳ vọng của tổng bằng tổng kỳ vọng |
| fair bet | cược công bằng | cược có kỳ vọng bằng 0 |
| edge | lợi thế | phần kỳ vọng dương của một bên |
| odds | odds (tỷ lệ cược) | tỷ số giữa xác suất không xảy ra và xác suất xảy ra |
| shorter / longer odds | odds ngắn / odds dài | sự kiện dễ xảy ra hơn / khó xảy ra hơn |
| favorite | cửa trên | tay hoặc bên có khả năng thắng cao hơn |
| hold'em (holdem) | hold'em | thể loại mỗi người hai lá úp, năm lá chung |
| flop | flop | ba lá chung đầu tiên lật cùng lúc |
| flush | flush | năm lá cùng chất |
| suited (s) / offsuit (o) | cùng chất / khác chất | AKs: A và K cùng chất; AKo: khác chất |
| pair (AA, KK, QQ) | đôi | hai lá cùng giá trị |
| tight player | người chơi chặt | người chỉ chơi ít tay mạnh |
| raise | raise | tăng mức cược |
| distribution of hands | phân phối tay bài | các tay đối thủ có thể cầm kèm xác suất |
| craps | craps | trò gieo hai xúc xắc trong sòng bạc |
| shutout | shutout (trận trắng lưới) | trận bóng chày mà đội đối phương không ghi điểm nào |

## Câu nói đáng nhớ

> "As far as the laws of mathematics refer to reality, they are not certain; as far as they are certain, they do not refer to reality." — Albert Einstein, đề từ Phần I (sách in "As for as")
>
> *Dịch: Chừng nào các định luật toán học nói về thực tại, chúng không chắc chắn; chừng nào chúng chắc chắn, chúng không nói về thực tại.*
> Ý nghĩa: kết quả toán chỉ chắc chắn trong mô hình; áp vào ván thật luôn có sai số từ giả định.

> "For most people, winning five million dollars is worth much more (or has much more utility) than a 50% chance of winning ten million." — phần mở đầu chương
>
> *Dịch: Với đa số người, thắng 5 triệu đô la đáng giá hơn nhiều (hay có độ thoả dụng cao hơn nhiều) so với 50% cơ hội thắng 10 triệu.*
> Ý nghĩa: kỳ vọng bằng tiền không phải là tất cả; đó là lý do sách phải giả định người chơi đủ vốn.

> "In reality, it is utility that we seek to maximize when playing poker (or in fact, when doing anything)." — phần mở đầu chương
>
> *Dịch: Thực ra thứ ta tìm cách tối đa hoá khi chơi poker (và khi làm bất cứ việc gì) là độ thoả dụng.*
> Ý nghĩa: tác giả thừa nhận thước đo tiền chỉ là xấp xỉ.

> "Probability is the key to decision-making in poker as it provides a mathematical framework by which we can evaluate the likelihood of uncertain events." — mục Probability
>
> *Dịch: Xác suất là chìa khoá của việc ra quyết định trong poker, vì nó cho một khuôn khổ toán học để đánh giá khả năng của các sự kiện bất định.*
> Ý nghĩa: mọi phân tích về sau dựa trên xác suất.

> "It's only in the aggregate that this expected value number exists." — ví dụ cược 11 ăn 10
>
> *Dịch: Con số kỳ vọng này chỉ tồn tại khi tính gộp.*
> Ý nghĩa: không lần chơi nào cho đúng kỳ vọng; kỳ vọng là thước đo của quyết định qua nhiều lần.

> "The free drinks and neon lights of Las Vegas are financed by the summation of millions of little coin flips, on each of which the house has a tiny edge." — đoạn về tính cộng của kỳ vọng
>
> *Dịch: Đồ uống miễn phí và đèn neon ở Las Vegas được trả bằng tổng của hàng triệu ván tung đồng xu nhỏ, mỗi ván sòng bạc có một lợi thế nhỏ.*
> Ý nghĩa: lợi thế nhỏ lặp lại nhiều lần thành lợi nhuận lớn — cũng là cách người chơi poker giỏi kiếm tiền.

> "A skillful poker player takes advantage of this additive property of expected value by constantly taking advantage of favorable EV situations." — cùng đoạn
>
> *Dịch: Người chơi poker giỏi tận dụng tính cộng của kỳ vọng bằng cách liên tục nắm lấy các tình huống có kỳ vọng thuận lợi.*
> Ý nghĩa: chiến thắng là tổng của nhiều quyết định tốt nhỏ, không phải vài ván lớn.

> "A mathematical approach to poker is concerned primarily with the maximization of expected value." — Key Concepts
>
> *Dịch: Cách tiếp cận toán học với poker chủ yếu quan tâm tới việc tối đa hoá kỳ vọng.*
> Ý nghĩa: câu tóm tắt mục tiêu của toàn bộ cuốn sách.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương đặt nền tối thiểu nhưng đủ cho cả cuốn sách, và làm điều đó bằng ví dụ poker ngay từ đầu (đôi át, flush ở flop, phân phối tay bài của người chơi chặt). Điểm đáng giá nhất là chương nói rõ giả định "dùng tiền thay cho độ thoả dụng, người chơi đủ vốn" ngay trang đầu, thay vì ngầm giả định như nhiều sách poker; chính giả định này về sau được nới ra ở Phần IV. Ký hiệu ⟨A, B⟩ và cách viết phân phối tay bài như một tập hợp với tỷ lệ "như lúc chia" là công cụ gọn sẽ dùng suốt Phần II và III. Ví dụ ba ván cược với người bạn cho thấy hai bài học tách bạch: một cược có kỳ vọng dương vẫn có thể thua ở mỗi lần, và một cược có giải thưởng lớn (30 đô la) vẫn có thể có kỳ vọng âm.

### Những chỗ đơn giản hoá

- **Định nghĩa xác suất theo tần suất** không áp dụng tự nhiên cho những điều chỉ xảy ra một lần, như "đối thủ này đang bluff ván này". Chương 3 sẽ dùng định lý Bayes, nơi xác suất được hiểu như mức tin, để xử lý loại câu hỏi đó.
- **Bỏ qua ảnh hưởng của lá bài đã biết** khi viết phân phối tay bài "như lúc chia". Nếu ta cầm một lá át, số tổ hợp AA của đối thủ giảm từ 6 xuống 3 và AK cũng giảm; các chương sau mới tính tới hiệu ứng này (card removal).
- **Giả định đủ vốn** không đúng với nhiều người chơi thật, nhất là ở giải đấu, nơi giá trị của chip không tuyến tính (Phần V).
- **Odds** được trình bày rất ngắn và với hai quy ước trái chiều (xem khối Lưu ý); Chương 4 sẽ dùng odds nhiều hơn khi bàn về pot odds.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp, không tra cứu)

Nội dung xác suất của chương không thay đổi. Điều thay đổi là công cụ: những phép tính như xác suất flush ở flop hay equity giữa hai phân phối nay được làm tức thì bằng phần mềm (sách cảm ơn PokerStove vì lý do này), và các "solver" hiện đại tính kỳ vọng của cả cây quyết định. Ký hiệu phân phối tay bài của sách nay thường gọi là "range" (dải bài), và tư duy "đánh với range của đối thủ chứ không phải một tay cụ thể" đã trở thành chuẩn trong cộng đồng poker.

### Liên hệ các chương khác

- [00-gioi-thieu.md](00-gioi-thieu.md): lời khuyên "tối đa hoá lợi nhuận trung bình" được chương này chính thức hoá thành tối đa hoá kỳ vọng.
- [C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md): phương sai và độ lệch chuẩn đo kết quả thực tế lệch khỏi kỳ vọng bao nhiêu.
- [C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md): định lý Bayes xây trên xác suất có điều kiện (1.5).
- [C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md): odds và kỳ vọng áp vào quyết định call.
- [C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md), [C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md): dùng ký hiệu ⟨A, B⟩ cho tay bài đấu phân phối và phân phối đấu phân phối.
- [C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md), [C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md): nới giả định "đủ vốn" và đưa rủi ro vào quyết định.
- [C27-giai-dau-phan-2-chip-khong-phai-tien.md](C27-giai-dau-phan-2-chip-khong-phai-tien.md): trường hợp tiền thắng trong ván (chip) không còn là thước đo đúng.

### Vận dụng

- **Người chơi poker:** trước mỗi quyết định lớn, hãy hỏi "kỳ vọng của từng phương án là bao nhiêu, kể cả fold (kỳ vọng 0 từ thời điểm này)?". Học thuộc vài xác suất nền: được chia AA 1/221, một đôi bất kỳ 1/17, flush ngay ở flop với hai lá cùng chất khoảng 0,84%. Khi đoán bài đối thủ, liệt kê dải bài và đếm tổ hợp: trong {AA, KK, QQ, AK}, AK chiếm 16/34 ≈ 47%, gần một nửa, dù chỉ là "một trong bốn loại".
- **Người làm tài chính và đầu tư:** kỳ vọng và độ thoả dụng tách bạch đúng như trong lý thuyết danh mục: một khoản đầu tư có kỳ vọng dương chưa chắc nên nhận nếu nó có thể làm mất phần lớn vốn. Ví dụ bàn craps (trả 30 cho một sự kiện có odds thật 35 to 1) là hình mẫu của nhiều sản phẩm có "giải thưởng lớn, xác suất nhỏ" như xổ số hay quyền chọn rất xa giá; hãy tính kỳ vọng thay vì nhìn vào khoản thắng tối đa. Tính cộng của kỳ vọng giải thích vì sao các chiến lược có lợi thế nhỏ nhưng lặp lại nhiều lần (tạo lập thị trường, bảo hiểm) có thể rất có lãi.
- **Người ra quyết định nói chung:** đánh giá một quyết định theo thông tin có lúc quyết định, không theo kết quả may rủi sau đó; và luôn có phương án "không làm gì" với kỳ vọng 0 để so sánh.

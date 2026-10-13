# Chương 7 — Chơi chính xác, phần I: các tình huống bài lật ngửa (Playing Accurately, Part I: Cards Exposed Situations)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 7 "Playing Accurately, Part I: Cards Exposed Situations", trang 77–88.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Phần II "Chơi khai thác" (Exploitive Play) mô tả chơi khai thác là một quy trình hai bước. Bước một — đọc bài và chiến lược của đối thủ, tức là ước lượng phân phối bài của họ — được trình bày ở Chương 5 ([C05-doc-bai-va-chien-luoc.md](C05-doc-bai-va-chien-luoc.md)), và Chương 6 ([C06-poker-truc-tuyen.md](C06-poker-truc-tuyen.md)) bàn về dữ liệu trực tuyến cho bước này. Chương 7 mở đầu bước hai: khi đã biết (hoặc đã ước lượng) bài của đối thủ, chọn hành động có kỳ vọng cao nhất. Để tách bước hai khỏi bước một, chương xét trường hợp đơn giản nhất: hai người chơi lật ngửa bài. Chương 4 ([C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md)) đã cho quy tắc cơ bản "tay bài đã thành (made hand) cược, tay bài đang chờ (draw) call hoặc fold theo pot odds"; Chương 7 chỉ ra những tình huống quy tắc này sai, chủ yếu vì độ sâu stack giới hạn số tiền có thể cược ở các vòng sau. Chương 8 ([C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md)) mở rộng sang một tay bài đấu với cả một phân phối bài, và Chương 9 ([C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md)) sang phân phối đấu với phân phối. Ý tưởng "draw tốt muốn đưa hết tiền vào sớm" và vai trò của độ sâu stack còn quay lại trong trò chơi jam-or-fold ở Chương 12 ([C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md)) và trong việc chọn mức cược no-limit ở Chương 14 ([C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md)).

**Ý chính:** **Ngay cả khi cả hai người chơi đều thấy bài của nhau, cách chơi đúng vẫn có thể trái trực giác, vì độ sâu stack (số tiền còn lại phía sau) quyết định tiền có thể cược ở các vòng sau; tay bài đang chờ tốt muốn đưa hết tiền vào sớm hoặc đưa vào càng ít càng tốt, còn tay bài đã thành muốn giữ lại đủ tiền để "phạt" tay bài đang chờ ở vòng sau khi nó trượt.** Ví dụ 7.1 (stud bảy lá $30–$60): X có sảnh A-K-Q-J-T, Y có bốn lá bích và chỉ còn $120, pot $400. Tác giả liệt kê năm phương án của X (check-fold, check-call, check-raise, bet-call, bet-fold), loại bet-fold (−$60 so với khoảng $297) và check-fold ($0 so với ít nhất $297), rồi tính được: check-call và check-raise đều $290,24, bet-call $308,43 nếu Y chỉ call. Vì Y raise thì X chỉ còn khoảng $297, Y nên raise dù Y thua khoảng 2 ăn 1; cách chơi đúng là X bet, Y raise, X call. Ví dụ 7.2 (pot-limit hold'em "cứng", chỉ được cược đúng bằng pot): X có A♥ A♦, Y có 8♣ 7♣, flop 9♣ 6♣ 2♦, Y có 15 outs và 56,06% equity, pot $100. Với stack $50, Y cược để buộc hết tiền vào, X chỉ được $37,88 (ít hơn equity $43,94 khi lật bài ngay). Với stack $400, không ai cược ở flop: X bet thì Y raise all-in (X còn −$4,55), Y bet thì X call (X được $95,45), nên check-check cho X $65,15. Với stack $1.300 (ba lần cược pot), X bet $100 và Y call, X được $95,45 — hơn gấp đôi equity ban đầu. Nếu Y chỉ có 14 outs, Y phải fold dù đang là người có cửa thắng cao hơn (53%). Ví dụ 7.3 (pot-limit thật, stack $400): kỳ vọng của X là hàm gấp khúc của số tiền x mỗi người đưa vào ở flop, 10x/33 + $65,15 khi x ≤ $100 và −x/3 + $128,79 khi x ≥ $100; X nên cược $23,26 để được ít nhất $72,20. Ví dụ 7.4 (no-limit, A♥ K♦ đấu Q♥ Q♣, X raise lên $300): với stack $800, Y call rồi tùy flop (khoảng $220) tốt hơn chút ít so với all-in ngay ($214,72); với stack $1.800, all-in ngay ($358,12) tốt hơn hẳn — stack sâu hơn thì QQ càng muốn đưa hết tiền vào, ngược với trực giác phổ biến.

> **Lưu ý:**
> - **Ví dụ 7.2, trường hợp 3, tiểu trường hợp c tính sai (lỗi đáng kể của sách):** sách viết ⟨X, hai cược ở flop⟩ = (15/45)(−$400) + (30/45)[($2.700)(29/44) − $1.300] = $346,21. Tính đúng: (29/44)(2.700) − 1.300 = 1.779,55 − 1.300 = 479,55; nhân 30/45 được 319,70; cộng (15/45)(−400) = −133,33 được **$186,36**. Con số $346,21 của sách bằng −133,33 + 479,55, tức sách quên nhân 479,55 với xác suất 30/45. Kiểm tra chéo từ phía Y: Y được (1/3)(500) + (2/3)[(15/44)(2.700) − 1.300] = 166,67 − 253,03 = −86,36, và X + Y phải bằng pot ban đầu $100: 186,36 + (−86,36) = 100. Kết luận của sách không đổi, vì $186,36 vẫn là kết quả tốt nhất cho X và tệ nhất cho Y trong bốn tiểu trường hợp.
> - **Ví dụ 7.2, trường hợp 2, công thức in sai:** sách viết ⟨X, check; Y check⟩ = (15/45)($0) + (30/45)[(29/44)($300 − $100)] = $65,15. Biểu thức như in cho (2/3)(29/44)(200) = $87,88. Công thức đúng là (30/45)[(29/44)($300) − $100] = (2/3)(197,73 − 100) = $65,15: ở turn X cược $100 vào pot $100, Y call, pot thành $300, X có 29/44 khả năng thắng $300 và đã bỏ ra $100.
> - **Ví dụ 7.2, phần chênh lệch nhỏ:** sách viết X được lợi "$65,15 − $43,94, tức $21,19"; hiệu đúng là $21,21. Sách viết tiểu trường hợp d là −$113,62 (do làm tròn 0,4394 × 2.700); chính xác là (870/1.980) × 2.700 − 1.300 = −$113,64. Sách nói giá trị tay bài của X "gần như gấp đôi" từ $43,94 lên $95,45; thực ra là gấp 2,17 lần, tức hơn gấp đôi.
> - **Ví dụ 7.1, hai lỗi in trong công thức bet-call:** dòng thứ hai viết (8/42)($60) thay vì (8/42)(−$60), và dòng thứ ba viết "1 − [8/42 − (8/41)(34/42)]" thay vì "1 − [8/42 + (8/41)(34/42)]". Kết quả $308,43 của sách đúng với công thức đúng: (8/42)(−60) + (8/41)(34/42)(−120) + (0,65157)(520) = −11,43 − 18,96 + 338,82 = 308,43.
> - **Ví dụ 7.3, lỗi in:** dòng đầu của công thức cho x ∈ [$100, $400] viết số hạng cuối là (15/44)(400) và dòng thứ hai viết (2/3 − 5/22)(400); số đúng là (2/3 − 5/22)($500) như dòng thứ ba và bảng kết quả. Dòng tóm tắt viết "⟨X, $100⟩ = $94,45" ở nhánh thứ hai; đúng là −100/3 + 128,79 = $95,45 (hai nhánh phải gặp nhau tại x = $100). Sách viết cược $5 làm tăng kỳ vọng "$1,50"; đúng là (10/33)(5) = $1,52 (từ $65,15 lên $66,67, như chính sách ghi).
> - **Ví dụ 7.4, "getting 3 to 2 on his money":** với stack $800, khi Y all-in thì X phải call thêm $500 để giành pot $1.100 ($300 của X + $800 của Y), tức tỷ lệ 2,2 ăn 1, không phải 3 ăn 2 (người tổng hợp tính). Tỷ lệ gần 3 ăn 2 (1,4 ăn 1: call $1.500 để giành $2.100) là của trường hợp stack $1.800; khi đó X cần 41,7% equity và có khoảng 42,8%, nên call nhưng rất sát.
> - **Ví dụ 7.4, xác suất 30% được làm tròn:** xác suất flop có A hoặc K mà không có Q là (C(46,3) − C(40,3)) / C(48,3) = (15.180 − 9.880) / 17.296 = 30,64%. Dùng số chính xác, ⟨Y, call⟩ = 0,3064 × (−200) + 0,6936 × 400 = $216,14 thay cho $220; vẫn lớn hơn $214,72 nên kết luận với stack $800 không đổi, nhưng chênh lệch chỉ còn khoảng $1,4. Câu "AK chỉ ra đôi khoảng một phần ba số lần ở flop" đúng: 1 − C(42,3)/C(48,3) = 33,6%.
> - **Ví dụ 7.4, equity 57,17% của QQ hơi cao:** người tổng hợp liệt kê đủ 1.712.304 bộ năm lá chung cho Q♥ Q♣ đấu A♥ K♦ và được QQ thắng 56,55%, hòa 0,42%, tức equity khoảng 56,76% (AK khoảng 43,24%, khớp câu "AK thắng khoảng 43%" của sách). Với 56,76%, ⟨Y, all-in⟩ là 0,5676 × 1.600 − 700 ≈ $208 (stack $800) và 0,5676 × 3.600 − 1.700 ≈ $343 (stack $1.800); so với ⟨Y, call⟩ khoảng $216–220, kết luận của sách ở cả hai độ sâu stack không đổi.
> - **Equity được làm tròn theo mô hình đơn giản hoá:** Ví dụ 7.2 và 7.3 bỏ qua trường hợp AA ra cù lũ hay 87 ra hai đôi nhờ hai lá cuối (runner-runner), nên Y có 1 − (30/45)(29/44) = 56,06%. Người tổng hợp liệt kê đủ 990 cặp turn–river và được equity chính xác của 8♣ 7♣ trước A♥ A♦ trên flop 9♣ 6♣ 2♦ là 56,26%; chênh lệch không ảnh hưởng tới lập luận. Ví dụ 7.2 ghi flop 9♣ 6♣ 2♦, Ví dụ 7.3 ghi 9♣ 6♣ 2♠; khác biệt không ảnh hưởng gì vì cả hai lá 2 đều không phải chuồn.
> - **Hình 7.1 (đồ thị kỳ vọng của X theo số tiền đưa vào ở flop):** trục hoành ghi "pot size" nhưng thực ra là x, số tiền mỗi người đưa vào ở flop; nhãn số trên trục hoành của bản PDF dựng lại bị lệch so với vạch chia (đỉnh gấp khúc trông như ở khoảng $150 trong khi theo công thức phải ở $100). Các giá trị đọc được khớp công thức: khoảng $65 tại x = 0, đỉnh khoảng $95 tại x = $100, khoảng −$5 tại x = $400.
> - **Lỗi chữ của bản PDF:** "Yearly Player Y will call" là "clearly"; "the receding case" là "the preceding case"; "the small snack case" là "small stack"; "the last bet hum the straight" là "from the straight"; "the Hop" là "the flop"; "mere" là "there"; "upshot of all tills" là "this"; "A simply gets" (tiểu trường hợp d) là "X simply gets".
> - **Quy ước tính kỳ vọng của sách:** mọi giá trị ⟨X, …⟩ là (phần pot X kỳ vọng nhận được) trừ (số tiền X bỏ thêm từ thời điểm đang xét), tức là coi pot hiện có như tài sản có thể giành được. Vì hai người chơi tổng hai phía luôn bằng pot ban đầu, Y tối đa hoá kỳ vọng của mình cũng chính là tối thiểu hoá kỳ vọng của X. Tiền tệ ghi theo sách (đô la Mỹ).

## Sơ đồ

### Phần mở đầu Chương 7 (trang 77) — chơi khai thác là quy trình hai bước

```text
       Chơi khai thác gồm hai bước
       · bước 1: đọc bài và chiến lược của đối thủ (Chương 5)
       · bước 2: với thông tin đó, tính kỳ vọng của từng phương án hành
         động và chọn phương án có kỳ vọng cao nhất
                                │
                                ▼
       Kỳ vọng trước một phân phối bài = trung bình có trọng số của kỳ
       vọng trước TỪNG tay bài cụ thể đối thủ có thể cầm
       → muốn hiểu bước 2, xét trường hợp hai người LẬT NGỬA BÀI
                                │
                                ▼
       Thường trò chơi bài lật ngửa nhàm chán: tay bài đã thành cược, tay
       bài đang chờ call hoặc fold theo pot odds (Chương 4); nhưng có
       những tình huống cách chơi đúng không hiển nhiên, trái trực giác
```

### Ví dụ 7.1 — Stud bảy lá $30–$60, sảnh đấu bốn lá bích, Y chỉ còn $120 (Example 7.1, trang 77–79)

```text
       X: A♥ K♦ Q♥ J♠ T♣ (sảnh, không thể cải thiện)
       Y: A♠ T♠ 8♠ 5♠ 2♣ (bốn lá bích, cần lá bích thứ năm)
       Pot $400; Y còn $120 (hai mức cược $60); X còn nhiều hơn
       Y ra thùng ở lá thứ sáu: 8/42; nếu trượt, ở lá thứ bảy: 8/41
       p(X thắng) = 1 − [8/42 + (34/42)(8/41)] = 65,16%
                                │
                                ▼
       X có NĂM phương án (nghĩ trước hành động tiếp theo cùng vòng):
       check-fold, check-call, check-raise, bet-call, bet-fold
                                │
                                ▼
       LOẠI BỎ BẰNG SO SÁNH TRỰC TIẾP (các nhánh còn lại giống nhau):
       · nếu Y raise: bet-call cho X 0,6516 × $640 − $120 ≈ $297, còn
         bet-fold cho −$60, nên bỏ bet-fold
       · nếu Y bet: check-fold cho $0, check-raise cho ít nhất $297 ($460
         nếu Y fold), nên bỏ check-fold
       Còn lại: check-call, check-raise, bet-call
                                │
                                ▼
       ĐOÁN chiến lược của Y: check theo nếu X check, call nếu X bet
       · check-call = check-raise ≈ $290,24 (Y check theo nên ý định
         call hay raise không được dùng tới)
       · bet-call ≈ $308,43   → X nên bet
                                │
                                ▼
       KIỂM TRA LẠI chiến lược của Y:
       · Y bet sau khi X check: X call và được $308,43, nên Y check tốt
         hơn ($290,24)
       · Y raise khi X bet: X chỉ còn ≈ $297 < $308,43, nên Y NÊN RAISE
       · X vẫn không có gì tốt hơn bet-call ($297 > $290,24)
                                │
                                ▼
       Cách chơi ở lá thứ năm: X bet, Y raise, X call
       · tay bài đang chờ raise tay bài đã thành dù thua khoảng 2 ăn 1
       · lý do: Y hết tiền nên không bị cược thêm "phạt"; Y đủ pot odds
         chỉ cho lá thứ sáu, nên đưa hết tiền vào ngay để nếu ra thùng ở
         lá thứ sáu vẫn lấy được cược cuối từ sảnh
       · đây là draw "mở" (X thấy khi mình bị thua); với draw "đóng", X
         có thể vẫn phải trả tiền ở lá thứ sáu khi Y ra thùng
```

### Ví dụ 7.2 — Pot-limit "cứng": A♥ A♦ đấu 8♣ 7♣ trên flop 9♣ 6♣ 2♦, ba độ sâu stack (Example 7.2, trang 79–83)

```text
       Luật pot-limit cứng: chỉ được cược ĐÚNG bằng pot (hoặc all-in nếu
       còn ít hơn pot); pot $100, X hành động trước
       Y có 15 outs mỗi lá; equity của Y = 1 − (30/45)(29/44) = 56,06%
       Equity của X trong pot $100 nếu lật bài ngay: $43,94
               ┌────────────────┼──────────────────────┐
               ▼                ▼                      ▼
       TRƯỜNG HỢP 1:      TRƯỜNG HỢP 2:          TRƯỜNG HỢP 3:
       stack $50          stack $400             stack $1.300
       · hết tiền ở flop: (hai lần cược pot)     (ba lần cược pot)
         X được $37,88    · X bet $100:          · không ai đặt cược
       · check-check rồi    Y fold → $100          thứ hai (cược thứ
         X bet turn khi     Y call → $95,45        hai dẫn tới kết quả
         Y trượt: $54,55    Y raise all-in →       tệ nhất cho người
       · X muốn check-      −$4,55; Y chọn         đặt nó)
         check, nhưng Y     raise                · X thích một cược
         bet để giới hạn  · X check: Y check →     ($95,45) hơn không
         X ở $37,88         $65,15; Y bet → X      cược ($65,15); Y
       · cách chơi: X       call $95,45 hoặc       ngược lại
         check, Y bet,      raise −$4,55         · cách chơi: X bet
         X call           · cách chơi: check-      $100, Y call; X được
       · cược sau flop      check; X được          $95,45 (gấp 2,17 lần
         làm X mất $6,06    $65,15 (lợi $21,21)    $43,94)
               └────────────────┬──────────────────────┘
                                ▼
       Draw tốt muốn hết tiền vào SỚM khi còn nhiều lá; tay bài đã thành
       chỉ muốn đưa vào vừa đủ để còn tiền "phạt" draw ở vòng sau
                                │
                                ▼
       Nếu Y chỉ có 14 outs và còn ba lần cược pot: Y phải FOLD trước một
       cược pot ở flop dù có 53,03% equity (14/44 < 1/3 nên không call
       được cược pot ở turn)
```

### Ví dụ 7.3 — Pot-limit thật, stack $400: X nên cược bao nhiêu ở flop (Example 7.3, trang 84–87)

```text
       Cùng bài như Ví dụ 7.2, pot $100, mỗi người $400; nay được cược bất
       kỳ số tiền nào không vượt quá pot
       Biết: cược $0 → $65,15; cược $100 → −$4,55 (Y raise all-in)
                                │
                                ▼
       Hành động ở turn đã xác định: Y trúng thì hết cược; Y trượt thì X
       cược pot hoặc all-in và Y call. Nên kỳ vọng của X chỉ phụ thuộc x
       = số tiền MỖI người đưa vào ở flop:
       · 0 ≤ x ≤ 100:   ⟨X⟩ = 10x/33 + $65,15     (tăng theo x)
       · 100 ≤ x ≤ 400: ⟨X⟩ = −x/3 + $128,79      (giảm theo x)
       · đỉnh $95,45 tại x = $100; −$4,55 tại x = $400
                                │
                                ▼
       X cược x nhỏ; Y chọn giữa CALL (giữ x) hoặc RAISE TỐI ĐA (tổng
       3x + 100, rơi vào nhánh giảm); mọi mức raise khác kém hơn cho Y
       · x = $5: call → $66,67; raise lên $115 → $90,46; Y call
                                │
                                ▼
       Mức cược tối ưu của X: hai lựa chọn của Y bằng nhau
       10x/33 + 65,15 = −(3x + 100)/3 + 128,79  ⇒  x = $23,26
       X được ít nhất $72,20 dù Y làm gì
                                │
                                ▼
       Stack sâu có lợi cho tay bài đã thành (phạt được draw ở turn),
       trái với quan niệm thường gặp rằng draw hưởng lợi từ stack sâu và
       implied odds; draw tốt rất muốn hết tiền vào sớm
```

### Ví dụ 7.4 — No-limit trước flop: A♥ K♦ raise lên $300, Q♥ Q♣ chọn all-in hay call (Example 7.4, trang 87–88)

```text
       Y đã đặt blind $100; X thấy AK, raise lên $300; Y thấy bài X
       QQ thắng 57,17%; AK ra đôi ở flop khoảng 1/3 số lần
       Trực giác: stack càng sâu, QQ càng nên xem flop rồi đẩy AK ra khi
       flop không có A, K. ĐÚNG KHÔNG? — SAI
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       STACK $800                        STACK $1.800
       · all-in: 0,5717 × $1.600 − $700  · all-in: 0,5717 × $3.600 −
         = $214,72                         $1.700 = $358,12
       · call $200 (pot $600): flop có   · call: vẫn $220
         A/K không Q (≈ 30%) thì X       · Y nên ALL-IN NGAY
         all-in, Y fold (−$200); còn
         lại Y all-in, X fold (+$400):
         $220
       · Y nên CALL (hơn chút ít)
               └────────────────┬────────────────┘
                                ▼
       Stack sâu: QQ muốn hết tiền vào vì lợi thế equity lớn; stack nông:
       QQ thích đẩy AK ra ở flop thuận lợi. Kết luận hơi giả tạo (thực tế
       QQ phải sợ AA, KK), nhưng nhiều người đánh giá quá cao việc xem
       flop và quên rằng QQ là cửa trên rõ rệt so với AK
```

### Phần kết chương (trang 88) — giả thuyết ban đầu không phải lúc nào cũng đúng

```text
       Giả thuyết "tay bài đã thành cược, draw call hoặc fold theo pot
       odds" sai trong nhiều tình huống
       · pot-limit và limit: stack còn lại ảnh hưởng sâu sắc tới chiến lược
       · no-limit: độ sâu stack quyết định all-in hay call
                                │
                                ▼
       Ít khi gặp trò chơi lật bài thật, nhưng đây là nền cho các chương
       sau: kỹ năng đọc bài vô dụng nếu không chơi chính xác khi đã biết
       bài; nhận ra lúc cách chơi lệch khỏi trực giác đem lại equity
```

### Phần "Key Concepts" — các ý then chốt cuối chương (trang 88)

```text
       · Bài lật ngửa vẫn có tình huống trái trực giác
       · Khi xét lần raise all-in cuối cùng, draw nên hung hăng hơn mức
         pot odds đơn giản gợi ý: cược thêm không làm hại draw được nữa,
         và tay bài đã thành không thoát được khi draw trúng
       · Độ sâu stack cực kỳ quan trọng trong poker cược lớn (pot-limit,
         no-limit); có lúc người có cửa thắng cao hơn phải fold trước
         cược của người có cửa thấp hơn vì các vòng cược sau
       · Draw tốt (equity gần 50%) hưởng lợi lớn khi hết tiền vào ở flop;
         nếu không làm được thì muốn đưa vào càng ít càng tốt
       · Tay bài đã thành thường muốn giữ lại đủ một cược lớn cho vòng
         sau, vì thu được nhiều khi draw trượt
```

## Ba câu hỏi chương này trả lời

1. **Khi biết bài của đối thủ, làm sao chọn hành động đúng?** Liệt kê các phương án kèm ý định cho hành động tiếp theo trong cùng vòng (check-fold, check-call, check-raise, bet-call, bet-fold), loại các phương án bị trội bằng cách so sánh ở nhánh mà chúng khác nhau, đoán phản ứng của đối thủ, tính kỳ vọng, rồi kiểm tra xem đối thủ có phản ứng tốt hơn không. Ở Ví dụ 7.1, cách đó loại bet-fold (−$60 so với $297) và check-fold ($0 so với ≥ $297), rồi cho thấy Y nên raise (X còn $297 thay vì $308,43), nên cách chơi là X bet, Y raise, X call.
2. **Vì sao độ sâu stack thay đổi cách chơi ngay cả khi bài lật ngửa?** Vì stack quyết định còn bao nhiêu tiền để cược ở vòng sau. Tay bài đã thành kiếm tiền chủ yếu khi "phạt" draw trượt ở turn, nên cần còn đủ một cược pot cho turn; draw tốt muốn hết tiền vào ngay khi còn hai lá để trúng. Với A♥ A♦ đấu 8♣ 7♣ (Y có 56,06% equity), X được $37,88 với stack $50, $65,15 với stack $400 (không ai cược ở flop), $95,45 với stack $1.300 (X bet, Y call); khi Y chỉ có 14 outs và stack sâu, Y phải fold dù có 53% equity.
3. **Trong pot-limit và no-limit, nên cược bao nhiêu?** Viết kỳ vọng của mình như hàm của số tiền vào pot, rồi chọn mức cược sao cho phản ứng tốt nhất của đối thủ cho mình nhiều nhất. Ở Ví dụ 7.3, hàm gấp khúc 10x/33 + $65,15 (x ≤ $100) và −x/3 + $128,79 (x ≥ $100) cho mức cược tối ưu x = $23,26 và kỳ vọng $72,20. Ở Ví dụ 7.4, QQ trước AK đã raise lên $300 nên call với stack $800 (khoảng $220 so với $214,72) nhưng all-in ngay với stack $1.800 ($358,12 so với $220).

## Khái niệm cần biết

- **Kỳ vọng (expected value, EV), ký hiệu ⟨X, phương án⟩:** trung bình có trọng số theo xác suất của kết quả tiền bạc. Trong chương, ⟨X⟩ = (phần pot X kỳ vọng nhận) − (số tiền X bỏ thêm). Ví dụ: ⟨X, bet-call khi Y raise⟩ = 0,6516 × $640 − $120 ≈ $297. Quan trọng vì bước hai của chơi khai thác chỉ là chọn phương án có kỳ vọng lớn nhất.
- **Bài lật ngửa (cards exposed, cards face-up):** trò chơi tưởng tượng mà hai người đều thấy bài nhau; không còn bước đọc bài, chỉ còn bước chọn hành động. Quan trọng vì kỳ vọng trước một phân phối bài là trung bình của các kỳ vọng trước từng tay bài lật ngửa.
- **Tay bài đã thành (made hand) và tay bài đang chờ (draw):** tay bài đã thành đang dẫn và không cần cải thiện (sảnh, đôi A); draw đang thua nhưng có thể vượt lên nếu ra lá cần. Ví dụ: A♥ A♦ là tay bài đã thành, 8♣ 7♣ trên 9♣ 6♣ 2♦ là draw thùng phá sảnh. Quan trọng vì toàn chương phân tích cuộc đấu giữa hai loại này.
- **Outs:** số lá còn lại giúp draw thắng. Ví dụ: 8♣ 7♣ có 15 outs: 9 lá chuồn còn lại, cộng 3 lá 5 và 3 lá 10 không phải chuồn (ra sảnh). Quan trọng để tính xác suất trúng: 15/45 ở turn, 15/44 ở river.
- **Equity:** phần pot một người chơi "sở hữu" nếu chia bài tới cuối mà không cược thêm, bằng xác suất thắng nhân pot. Ví dụ: Y có 56,06% equity, nên X có $43,94 trong pot $100. Quan trọng làm mốc để đo cược sau flop làm lợi hay hại cho ai.
- **Pot odds:** tỷ lệ giữa pot hiện có và số tiền phải bỏ ra để call; call có lời khi xác suất thắng lớn hơn số tiền call chia cho pot sau khi call. Ví dụ: call cược pot cần ít nhất 1/3 xác suất thắng; 15/44 = 34,1% đủ, 14/44 = 31,8% không đủ. Quan trọng vì quy tắc pot odds của Chương 4 là "giả thuyết ban đầu" mà chương này thử thách.
- **Phương án có ý định (check-fold, check-call, check-raise, bet-call, bet-fold):** mô tả hành động đầu tiên cùng ý định cho hành động tiếp theo trong cùng vòng. Ví dụ: check-raise là check với ý định raise nếu đối thủ bet. Quan trọng vì nghĩ trước hành động tiếp theo tránh được nhiều lỗi.
- **Stack và độ sâu stack (stack size):** số tiền mỗi người còn có thể cược. Ví dụ: stack $1.300 trong pot $100 cho phép ba lần cược pot ($100, rồi tổng $400, rồi tổng $1.300). Quan trọng vì nó quyết định còn bao nhiêu tiền cho các vòng sau.
- **All-in, jam:** đặt toàn bộ số tiền còn lại. Người đã all-in không thể bị cược thêm, nên không còn bị "phạt" ở vòng sau. Ví dụ: ở Ví dụ 7.1, Y raise để hết tiền và chắc chắn lấy được cược cuối nếu trúng thùng ở lá thứ sáu.
- **Pot-limit và pot-limit "cứng" (rigid pot limit):** pot-limit cho phép cược bất kỳ số tiền nào từ mức tối thiểu tới bằng pot; pot-limit cứng là phiên bản đơn giản hoá của sách, chỉ cho phép cược đúng bằng pot (hoặc all-in nếu còn ít hơn pot). Ví dụ: pot $100, cược pot là $100; raise pot sau cược $100 là tổng $400 (call $100 thành pot $300, rồi raise thêm $300).
- **Draw mở và draw đóng (open draw, closed draw):** draw mở là khi tay bài đã thành biết mình bị vượt (như khi bài lộ); draw đóng là khi không biết. Ví dụ: ở Ví dụ 7.1, X thấy Y ra thùng nên không trả thêm tiền; với draw đóng X có thể vẫn phải call ở lá thứ sáu. Quan trọng vì draw mở mất implied odds, nên nó muốn đưa tiền vào sớm.
- **Implied odds:** tiền kỳ vọng thắng thêm ở các vòng sau nếu trúng. Quan trọng vì chương chỉ ra quan niệm "draw hưởng lợi từ stack sâu nhờ implied odds" không đúng khi bài lộ.
- **Phương án bị trội (dominated option):** một phương án luôn cho kỳ vọng không lớn hơn phương án khác trong mọi phản ứng của đối thủ. Ví dụ: check-fold bị check-raise trội ($0 so với $297 hoặc $460). Quan trọng vì loại phương án trội giúp thu gọn bài toán.

## Nội dung chi tiết

### 1. Mở đầu: chơi khai thác là quy trình hai bước (trang 77)

Chơi khai thác là một quy trình hai bước. Bước đầu là xử lý việc đọc bài và chiến lược của đối thủ, đã bàn ở Chương 5. Bước hai là quyết định hành động dựa trên thông tin từ bước một; cách làm ở đây đơn giản là tính kỳ vọng (EV) của các phương án hành động và chọn phương án có kỳ vọng cao nhất.

Khi tính kỳ vọng trước phân phối bài của đối thủ, ta xét lần lượt từng tay bài đối thủ có thể cầm và lấy trung bình có trọng số các giá trị kỳ vọng theo phân phối đó. Vì trong mỗi trường hợp ta biết bài của đối thủ và đang chơi một tay bài trước một tay bài đã biết, ta có thể hiểu thêm bằng cách cho hai người lật ngửa bài và xem cách chơi từ đó. Trò chơi này nghe có vẻ không thú vị, và trong nhiều trường hợp đúng là vậy: tay bài đã thành cược, còn tay bài đang chờ đuổi theo hoặc bỏ tùy pot odds, như Chương 4 đã thấy. Nhưng có những tình huống thú vị trong đó cách chơi đúng vừa không hiển nhiên vừa không trực giác.

### 2. Ví dụ 7.1 — Stud bảy lá: sảnh đấu bốn lá bích với stack giới hạn (Example 7.1, trang 77–79)

#### Đề bài

Trò chơi là stud bảy lá (7-card stud, mỗi người nhận bảy lá riêng qua nhiều vòng, dùng năm lá tốt nhất) mức $30–$60 (cược $30 ở các vòng đầu, $60 từ lá thứ năm trở đi). Đang ở lá thứ năm (fifth street):

- Người chơi X có A♥ K♦ Q♥ J♠ T♣ — sảnh cao nhất tới A, không thể cải thiện.
- Người chơi Y có A♠ T♠ 8♠ 5♠ 2♣ — bốn lá bích, cần thêm một lá bích để ra thùng (flush).

Pot có $400. Y chỉ còn $120 tiền chip; X có nhiều hơn (X "cover" Y). Nên chơi thế nào?

#### Năm phương án của X

Ta có thể xét riêng từng người chơi. Với X, quyết định ban đầu là check hay bet. Nhưng tác giả thích mô tả các phương án chiến lược theo cách phức tạp hơn, phản ánh suy nghĩ đằng sau lựa chọn. Thay vì hai phương án, X thực ra có năm:

| Phương án | Ý nghĩa |
|---|---|
| check-fold | check với ý định fold nếu Y bet |
| check-call | check với ý định call nếu Y bet |
| check-raise | check với ý định raise nếu Y bet |
| bet-call | bet với ý định call nếu Y raise |
| bet-fold | bet với ý định fold nếu Y raise |

X chọn phương án có giá trị cao nhất. Lý do trình bày như vậy: cân nhắc các hành động tương lai trong cùng vòng cược là một phần quan trọng của chơi giỏi; nhiều lỗi có thể tránh hoặc giảm bớt nếu khi hành động đầu tiên đã nghĩ tới hành động sẽ tiếp theo.

#### Loại bet-fold

Kỳ vọng của việc bet khi Y fold hoặc call là như nhau bất kể X định làm gì nếu Y raise, nên có thể bỏ qua các trường hợp đó và so sánh bet-call với bet-fold chỉ ở nhánh Y raise. Nếu Y raise, Y hết tiền, không còn cược ở các vòng sau, và:

⟨X, bet-call⟩ = p(X thắng) × (pot mới) − (chi phí hành động ở vòng này).

Pot hiện là $400; nếu cả hai đưa nốt $120 vào ở vòng này, pot mới là $640. Y ra thùng ở lá thứ sáu với xác suất 8/42 (còn 8 lá bích trong 42 lá chưa thấy), và nếu trượt thì ra thùng ở lá thứ bảy với xác suất 8/41. X không thể cải thiện, nên:

- p(X thắng) = 1 − p(X thua)
- p(X thắng) = 1 − {p(Y thắng ở lá thứ sáu) + [p(Y trượt lá thứ sáu)] × [p(Y thắng ở lá thứ bảy)]}
- p(X thắng) = 1 − [8/42 + (34/42)(8/41)] = 1 − [0,19048 + 0,15796] = 1 − 0,34843 = 65,16%.

Vậy ⟨X, bet-call⟩ = 0,6516 × $640 − $120 = $417,00 − $120 ≈ $297.

Nếu X bet rồi fold khi bị raise, X mất cược $60: ⟨X, bet-fold⟩ = −$60.

Đây không phải kỳ vọng toàn phần của hai chiến lược, nhưng vì kỳ vọng ở các nhánh Y không raise là như nhau, có thể so sánh trực tiếp: bet-call tốt hơn bet-fold, nên loại bet-fold. Điều này trực giác: X có gần hai phần ba pot; fold trong một pot khá lớn khi đối thủ chỉ đang chờ thùng sẽ là thảm họa.

#### Loại check-fold

Tương tự, xét ba phương án bắt đầu bằng check. Nếu Y check theo, ba phương án có cùng kỳ vọng. Nếu Y bet:

- ⟨X, check-fold⟩ = $0 (X không bỏ thêm tiền và không nhận gì).
- Nếu X check-raise và Y call, kỳ vọng của X giống như bet-call khi Y raise: ⟨X, check-raise | Y call⟩ ≈ $297.
- Nếu X check-raise và Y fold, X giành pot $400 cộng $60 Y đã cược: ⟨X, check-raise | Y fold⟩ = $460.

Vậy loại check-fold: ở bất cứ đâu X định check-fold, thay bằng check-raise sẽ được nhiều tiền hơn. Sau phân tích đơn giản này còn ba phương án: check-call, check-raise, bet-call.

#### Tính ba phương án còn lại với một giả định về Y

Để đi tiếp, phải xét Y sẽ làm gì khi X check hoặc bet. Tạm đoán chiến lược của Y: check theo nếu X check, và call nếu X bet. Ở lá thứ sáu: nếu Y đã ra thùng thì hết cược, X không call gì nữa vì không còn cửa thắng. Nếu Y chưa ra thùng, ván bài quy về trường hợp của Chương 4: X bet và Y call hay fold theo pot odds — ở đây Y call.

**Check-call (Y check theo ở lá thứ năm).** Pot vẫn $400. Lá thứ sáu: Y trúng (8/42) thì X bỏ, X được $0. Y trượt thì X bet $60, Y call. Lá thứ bảy: Y trúng ((34/42)(8/41)) thì X mất $60; Y trượt thì X giành pot $520 và đã bỏ $60, được $460.

⟨X, check-call⟩ = (8/42)($0) + (8/41)(34/42)(−$60) + {1 − [8/42 + (8/41)(34/42)]}($460)
= 0,15796 × (−60) + 0,65157 × 460 = −9,48 + 299,72 ≈ **$290,24**.

⟨X, check-raise⟩ ≈ $290,24, bằng check-call, vì nếu X check thì Y check theo, X không có dịp thực hiện ý định call hay raise.

**Bet-call (Y call ở lá thứ năm).** X bet $60, Y call; pot $520, Y còn $60. Lá thứ sáu: Y trúng thì X mất $60. Y trượt thì X bet $60, Y call (hết tiền), pot $640. Lá thứ bảy: Y trúng thì X mất $120; Y trượt thì X được $640 − $120 = $520.

⟨X, bet-call⟩ = (8/42)(−$60) + (8/41)(34/42)(−$120) + {1 − [8/42 + (8/41)(34/42)]}($520)
= −11,43 − 18,96 + 338,82 ≈ **$308,43**.

(Sách in hai lỗi dấu trong công thức này; xem Lưu ý.) Dựa vào đó, X nên bet.

#### Kiểm tra lại chiến lược của Y

Còn hai xác nhận cuối. Ta đã đoán Y check theo khi X check và chỉ call khi X bet.

- Nếu Y bet sau khi X check, X chỉ cần call và được $308,43 (cùng các nhánh như bet-call). Vậy Y check theo tốt hơn (X chỉ được $290,24).
- Nếu Y raise khi X bet, như đã tính, X (với bet-call) chỉ được $297, thấp hơn $308,43. Vậy Y nên raise. X vẫn không làm gì tốt hơn bet-call: nếu X check thì Y check theo và X được $290,24 < $297.

| Kỳ vọng của X | Y check theo / call | Y bet (sau check) / raise (sau bet) |
|---|---:|---:|
| X check (check-call hoặc check-raise) | $290,24 | $308,43 nếu X call; ≈ $297 nếu X check-raise và Y call |
| X bet-call | $308,43 | ≈ $297 |

Vậy ở lá thứ năm, nếu cả hai tối đa hoá kỳ vọng: **X bet, Y raise, X call.**

#### Vì sao draw lại raise

Điều này trông hơi lạ, vì tay bài đang chờ raise cược của tay bài đã thành. X (tay bài đã thành) bet để bắt Y trả tiền cho việc chờ bài — nhưng đến lượt Y, raise lại đúng, dù Y thua khoảng 2 ăn 1 (65,16% so với 34,84%, tức 1,87 ăn 1). Lý do là stack bị giới hạn: Y sẽ all-in và không thể bị "phạt" bằng các cược thêm. Vì Y đủ pot odds để call ở lá thứ năm chỉ cho riêng lá thứ sáu (call $60 để giành $460, tức 7,7 ăn 1, trong khi tỷ lệ trượt lá thứ sáu là 34 ăn 8, tức 4,25 ăn 1), Y nên chắc chắn rằng toàn bộ tiền vào pot ngay ở lá thứ năm. Như vậy nếu Y ra thùng ở lá thứ sáu, Y vẫn lấy được cược cuối từ sảnh. Điều này xảy ra vì draw của Y là **draw mở**: X biết khi nào mình bị thua. Trong các trường hợp draw **đóng**, X có thể vẫn phải trả tiền ở lá thứ sáu nếu Y ra thùng.

### 3. Ví dụ 7.2 — Pot-limit cứng: AA đấu draw thùng phá sảnh với ba độ sâu stack (Example 7.2, trang 79–83)

#### Đề bài

Một ví dụ khác với stack giới hạn; lần này cho độ sâu stack ban đầu thay đổi để xem ảnh hưởng của nó. Trò chơi là hold'em pot-limit, nhưng với luật đặc biệt: chỉ được cược đúng bằng pot (hoặc all-in nếu người chơi còn ít hơn pot). Tác giả gọi đây là **trò chơi pot-limit cứng** (rigid pot limit game); nó đơn giản hơn nhiều so với pot-limit đầy đủ (được cược bất kỳ số tiền nào giữa mức tối thiểu và pot).

- X có A♥ A♦.
- Y có 8♣ 7♣.
- Flop: 9♣ 6♣ 2♦.

Để đơn giản, bỏ qua khả năng AA ra cù lũ (full house) và 87 ra hai đôi nhờ hai lá cuối liên tiếp (runner-runner); giả sử mỗi vòng 87 có đúng 15 outs và hoặc trúng hoặc trượt. (15 outs: 9 lá chuồn còn lại, cộng 3 lá 5 và 3 lá 10 không phải chuồn, cho sảnh.) Còn 52 − 4 − 3 = 45 lá chưa thấy.

Equity của Y nếu chia bài tới cuối:

⟨Y⟩ = 1 − p(trượt hai lần) = 1 − (30/45)(29/44) = 1 − 870/1.980 = 56,06%.

Pot có $100; X hành động trước.

#### Trường hợp 1: stack nông ($50)

Y là cửa trên nếu chia thẳng bài (56,06% với draw thùng phá sảnh). Nếu X bet $50, rõ ràng Y call, và:

⟨X, X bet – Y call⟩ = p(X thắng) × (pot mới) − (chi phí cược) = [1 − 0,5606] × $200 − $50 = 0,4394 × $200 − $50 = **$37,88**.

Đây là equity của X khi toàn bộ tiền vào ở flop, bất kể ai cược trước. Nếu X check, Y có thể bảo đảm kỳ vọng của X không vượt quá con số này bằng cách bet: X đủ pot odds để call (X call $50 để giành $200 với 43,94% thắng), và kết quả giống hệt.

Nếu flop đi check-check và Y không ra sảnh hay thùng ở turn (30/45 số lần), X có thể bet ở turn. Khi đó X có 29/44 khả năng thắng. Y vẫn call rõ ràng, vì được hơn 3 ăn 1 từ pot (call $50 để giành $150, cần 25%, có 15/44 = 34%). Kỳ vọng của X:

⟨X, bet turn⟩ = [p(Y trượt turn)] × [p(X thắng) × (pot mới) − (chi phí cược)] = (30/45) × [(29/44)(200) − 50] = (2/3)(131,82 − 50) = **$54,55**.

(Nếu Y trúng ở turn, X fold, được $0.) Giá trị này cao hơn khi hai người all-in ở flop, nên X muốn flop đi check-check. Nhưng Y cũng biết điều đó. Vì Y có thể giới hạn X ở $37,88 bằng cách bet, cách chơi ở flop là **X check, Y bet, X call**. Equity của X trong pot ban đầu dựa trên giá trị showdown là $100 × (1 − 0,5606) = $43,94, nên cược sau flop ở đây làm X mất hơn $6 (chính xác $6,06).

#### Trường hợp 2: stack trung bình ($400)

Y vẫn có lợi thế nhỏ nếu all-in ở flop với 56,06% equity. Mỗi cược pot: cược đầu $100 (pot $200 + ...), raise pot lên tổng $400 là hết stack.

**Nếu X bet $100,** Y có ba lựa chọn:

- Fold: X giành pot. ⟨X, bet; Y fold⟩ = $100.
- Raise all-in lên $400: pot thành $900. ⟨X, bet; Y raise⟩ = (1 − 0,5606)($900) − $400 = 0,4394 × 900 − 400 = **−$4,55**.
- Call $100: pot thành $300, mỗi người còn $300. Hai khả năng:
  - 15/45 số lần Y trúng ở turn, X mất ròng $100: ⟨X, bet; Y call | Y trúng⟩ = −$100.
  - 30/45 số lần Y trượt, trò chơi quy về bài toán pot odds: X cược $300 (bằng pot, cũng là all-in) và Y buộc phải call với 15/44 equity (call $300 để giành $900, cần 33,3%, có 34,1%). ⟨X, bet; Y call | Y trượt⟩ = (29/44)($900) − $400 = **$193,18**. Kiểm tra cách khác: ⟨X⟩ = p(X thắng) × (tiền ròng khi thắng) − p(Y thắng) × (tiền ròng khi thua) = (29/44)($500) − (15/44)($400) = 329,55 − 136,36 = $193,18.
  - Tổng: ⟨X, bet; Y call⟩ = (15/45)(−$100) + (30/45)($193,18) = −33,33 + 128,79 = **$95,45**.

Các kỳ vọng tính theo phía X. Vì đây là trò chơi hai người và không ai khác chia pot, Y tối đa hoá kỳ vọng của mình hay tối thiểu hoá kỳ vọng của X là như nhau. Vậy nếu X bet $100, Y nên raise all-in — lựa chọn tốt nhất trong ba.

**Nếu X check,** Y có thể check hoặc bet.

- Y check: 15/45 số lần Y trúng ở turn và X được $0; 30/45 số lần Y trượt, X cược pot ($100) và được call. ⟨X, check; Y check⟩ = (15/45)($0) + (30/45)[(29/44)($300) − $100] = (2/3)(197,73 − 100) = **$65,15**. (Sách in "(29/44)($300 − $100)"; xem Lưu ý.)
- Y bet $100: nếu X raise all-in, X lại được −$4,55; nếu X call, X lại được $95,45.

Bảng kỳ vọng của X (trường hợp 2, stack $400), hàng là phương án của X, cột là hành động của Y; ô trống là tổ hợp không xảy ra:

| Phương án của X | Y check | Y bet | Y call | Y raise | Y fold |
|---|---:|---:|---:|---:|---:|
| Bet | | | $95,45 | −$4,55 | $100 |
| Check (rồi fold nếu Y bet) | $65,15 | | | | |
| Check-raise | $65,15 | −$4,55 | | | |
| Check-call | $65,15 | $95,45 | | | |

Từ bảng: nếu X check (với ý định call), tệ nhất X được +$65,15 (Y check theo). Vậy ở stack $400, flop nên đi **check-check**. Không ai cược được: nếu X bet, Y raise all-in và lấy lợi thế trên toàn bộ tiền; nếu Y bet, X call và đưa phần lớn tiền vào ở turn, khi X có lợi thế đáng kể.

Cũng lưu ý: khi stack lớn lên, X được lợi nhờ cược. Ở trường hợp stack nông, X thực ra mất tiền do cược (so với equity showdown trong pot ban đầu). Ở đây X được $65,15 − $43,94 = $21,21 từ cược sau flop (sách ghi $21,19).

#### Trường hợp 3: stack sâu ($1.300)

Trường hợp pot-limit cứng cuối cùng: stack $1.300, tức ba lần cược pot (cược $100 vào pot $100; raise pot lên tổng $400, pot $900; raise pot lên tổng $1.300, pot $2.700). Chia làm bốn tiểu trường hợp theo số tiền vào ở flop:

- **a) Không có tiền vào ở flop.** Không ai raise ở turn, nên kỳ vọng của X như trường hợp trước khi không có tiền vào ở flop: **$65,15**.
- **b) Một cược pot ($100 mỗi người) vào ở flop.** Tương tự trường hợp trước: **$95,45**. (Y trượt turn thì X cược $300 vào pot $300, Y call; đến river không còn gì thay đổi.)
- **c) Hai cược pot ($400 mỗi người) vào ở flop.** Pot $900. Nếu Y trúng ở turn, X mất $400. Nếu Y trượt, X cược $900 và Y call (cần 33,3%, có 34,1%); 29/44 số lần X giành pot $2.700, còn lại Y giành.
  ⟨X, hai cược ở flop⟩ = (15/45)(−$400) + (30/45)[($2.700)(29/44) − $1.300] = −133,33 + (2/3)(479,55) = −133,33 + 319,70 = **$186,36**. (Sách ghi $346,21 do quên nhân 479,55 với 30/45; xem Lưu ý.)
- **d) Ba cược pot ($1.300 mỗi người) vào ở flop.** X chỉ nhận equity showdown: ⟨X, ba cược ở flop⟩ = (1 − 0,5606)($2.700) − $1.300 = 0,4394 × 2.700 − 1.300 = **−$113,64** (sách ghi −$113,62 do làm tròn).

| Tiểu trường hợp | Tiền mỗi người vào ở flop | Kỳ vọng của X (tính lại) | Theo sách | Kỳ vọng của Y (= $100 − X) |
|---|---:|---:|---:|---:|
| a | $0 | $65,15 | $65,15 | $34,85 |
| b | $100 | $95,45 | $95,45 | $4,55 |
| c | $400 | $186,36 | $346,21 | −$86,36 |
| d | $1.300 | −$113,64 | −$113,62 | $213,64 |

Từ đó rút ra các quy tắc logic:

1. **X không bao giờ đặt cược thứ hai ở flop.** Nếu X làm vậy (raise cược của Y lên $400), Y sẽ raise all-in, dẫn tới tiểu trường hợp d, kết quả tệ nhất cho X.
2. **Y không bao giờ đặt cược thứ hai ở flop.** Nếu Y làm vậy, X chỉ call và ta có tiểu trường hợp c, kết quả tệ nhất cho Y.
3. **X thích b hơn a:** nếu được chọn giữa không cược và một cược, X chọn một cược.
4. **Y thích a hơn b:** nếu được chọn giữa một cược và không cược, Y chọn không cược.

Vậy không ai đặt cược thứ hai; do đó cả hai đều có quyền đặt cược thứ nhất nếu muốn. Vì X thích phương án này, **X bet và Y call**, cho X kỳ vọng $95,45. Đáng chú ý là kỳ vọng của X nếu Y fold chỉ là $100. Trong trường hợp này X được rất nhiều giá trị từ cược sau flop: giá trị tay bài tăng từ $43,94 lên $95,45 (sách nói "gần gấp đôi"; thực ra gấp 2,17 lần).

**Nguyên tắc rút ra.** Khi tay bài đã thành đấu với một draw tốt, draw thường làm tốt nhất bằng cách đưa toàn bộ tiền vào pot càng sớm càng tốt, khi còn nhiều lá sắp ra. Ngược lại, tay bài đã thành chỉ muốn đưa vào lượng tiền vừa đủ để vẫn còn cược "phạt" draw khi draw trượt ở vòng sau. Khi chỉ còn hai cược, nếu tay bài đã thành bet thì draw có thể all-in; tốt hơn là tay bài đã thành trì hoãn cược để rút giá trị ở turn khi draw trượt. Nhưng khi còn ba cược, tay bài đã thành có thể bet ở flop, biết rằng draw không thể ngăn mình đặt một cược pot ở turn.

**Biến thể 14 outs.** Giảm outs của Y đi một, còn 14. Equity của Y khi đó là 1 − (31/45)(30/44) = 53,03%, vẫn là cửa trên. Nhưng nếu còn ba cược pot, Y phải fold trước cược pot ở flop. Không chỉ có một cược pot ở turn mà Y không call được (14/44 = 31,8% nhỏ hơn 1/3 cần thiết; sách so sánh với 15/45 = 1/3), mà còn có cược pot ở flop. Người tổng hợp kiểm tra từ phía Y khi X bet $100 ở flop:

- Y call $100 (pot $300): trúng ở turn (14/45) thì Y được $300 − $100 = $200; trượt (31/45) thì X cược $300, Y phải fold, mất $100. Kỳ vọng (14/45)(200) + (31/45)(−100) = 62,22 − 68,89 = −$6,67.
- Y raise lên tổng $400 (pot-limit cứng không cho Y all-in ngay; X chỉ cần call): trúng ở turn Y được $900 − $400 = $500; trượt thì X cược $900, Y fold, mất $400. Kỳ vọng (14/45)(500) + (31/45)(−400) = 155,56 − 275,56 = −$120.
- Y fold: $0. Vậy Y fold là tốt nhất.

#### Chuyển sang pot-limit thật

Tới đây mới chỉ xét pot-limit cứng, chỉ cho phép cược đúng bằng pot. Trong pot-limit thật, mỗi người có thể cược bất kỳ số tiền nào tới bằng pot; điều này thay đổi kỳ vọng thế nào? Để xem, quay lại trường hợp hai người còn hai lần cược pot.

### 4. Ví dụ 7.3 — Pot-limit thật: mức cược tối ưu của AA (Example 7.3, trang 84–87)

#### Đề bài

Hold'em pot-limit. X có A♥ A♦, Y có 8♣ 7♣, flop 9♣ 6♣ 2♠. Lại bỏ qua runner-runner; mỗi vòng 87 có đúng 15 outs. Pot $100, mỗi người có $400 trước mặt.

Đã thấy ở trên: kỳ vọng của X khi cược $100 là −$4,55 (Y raise all-in), khi cược $0 (check) là $65,15. Nếu cho phép X cược bất kỳ số tiền nào giữa hai mức đó thì sao? Ví dụ X cược $5.

#### Kỳ vọng của X như hàm của số tiền vào ở flop

Hành động ở turn là xác định: nếu Y trúng ở turn thì không còn cược; nếu Y trượt, X cược pot hoặc all-in (và Y call). Vì vậy có thể viết kỳ vọng tổng của X như hàm của tổng số tiền vào pot ở flop. Gọi x là số tiền **mỗi người** đưa vào ở flop. Trước hết xét x tới $100; pot ở turn là 2x + $100.

**Nhánh 0 ≤ x ≤ $100.** Khi Y trượt turn, X cược đúng bằng pot 2x + 100 (còn đủ tiền vì 400 − x ≥ 2x + 100 khi x ≤ 100), Y call, pot thành 3(2x + 100) = 6x + 300.

| Kết quả | Xác suất | Kỳ vọng của X từ kết quả |
|---|---|---|
| Y thắng ở turn | 15/45 | −x |
| Y thắng ở river | (30/45)(15/44) | −x − (2x + 100) = −3x − 100 |
| X thắng | 1 − (15/45) − (30/45)(15/44) | (6x + 300) − (3x + 100) = 3x + 200 |

Tính từng bước:

- ⟨X, x ở flop⟩ = (15/45)(−x) + (30/45)(15/44)(−3x − 100) + [1 − 15/45 − (30/45)(15/44)](3x + 200)
- = (1/3)(−x) + (2/3)(15/44)(−3x − 100) + [2/3 − (2/3)(15/44)](3x + 200)
- = (1/3)(−x) + (5/22)(−3x − 100) + (2/3 − 5/22)(3x + 200), vì (2/3)(15/44) = 30/132 = 5/22
- = −x/3 − 15x/22 − 500/22 + (29/66)(3x + 200), vì 2/3 − 5/22 = 44/66 − 15/66 = 29/66
- = −x/3 − 15x/22 − 500/22 + 29x/22 + 2.900/33
- = −x/3 − 1.500/66 + 7x/11 + 5.800/66, vì −15x/22 + 29x/22 = 14x/22 = 7x/11
- = **10x/33 + $65,15**, vì −1/3 + 7/11 = (−11 + 21)/33 = 10/33 và (5.800 − 1.500)/66 = 4.300/66 = 65,15.

Kiểm tra với kết quả cũ: ⟨X, $0⟩ = $65,15 và ⟨X, $100⟩ = 1.000/33 + 65,15 = 30,30 + 65,15 = $95,45. Biểu thức chỉ đúng với x từ $0 tới $100.

**Nhánh $100 ≤ x ≤ $400.** Trên $100, X không còn đủ tiền để cược cả pot ở turn vì stack quá nhỏ; X cược hết phần còn lại (400 − x), Y call (Y cần (400 − x)/900 ≤ 1/3 equity, có 34,1%). Mọi tiền đều vào pot, pot cuối $900.

| Kết quả | Xác suất | Kỳ vọng của X từ kết quả |
|---|---|---|
| Y thắng ở turn | 15/45 | −x |
| Y thắng ở river | (30/45)(15/44) | −400 |
| X thắng | 1 − (15/45) − (30/45)(15/44) | 900 − 400 = 500 |

- ⟨X, $x⟩ = (15/45)(−x) + (30/45)(15/44)(−400) + [1 − 15/45 − (30/45)(15/44)](500)
- = (1/3)(−x) + (5/22)(−400) + (2/3 − 5/22)(500)
- = −x/3 − 90,91 + 219,70
- = **−x/3 + $128,79**.

Với x = $400 biểu thức cho −133,33 + 128,79 = −$4,55, đúng như trước.

**Hàm hai đoạn:**

| Khoảng của x | Kỳ vọng của X | Giá trị tại hai đầu |
|---|---|---|
| [$0, $100] | 10x/33 + $65,15 | $65,15 tại x = 0; $95,45 tại x = $100 |
| [$100, $400] | −x/3 + $128,79 | $95,45 tại x = $100 (sách in $94,45); −$4,55 tại x = $400 |

**Hình 7.1 (kỳ vọng của X theo x)** vẽ đường gấp khúc này: trục tung "X-equity" từ −$20 tới $100, trục hoành từ $0 tới $400. Đường đi lên thẳng từ khoảng $65 tại x = 0 tới đỉnh khoảng $95 tại x = $100, rồi đi xuống thẳng với độ dốc −1/3 tới khoảng −$5 tại x = $400; nó cắt mức $0 tại x = 128,79 × 3 ≈ $386 (người tổng hợp tính).

#### Y phản ứng thế nào với một cược nhỏ

Xét lại trường hợp X cược $5. Y có vô số mức raise để chọn, nhưng nhờ thấy hình dạng hàm kỳ vọng của X, dễ loại nhiều lựa chọn. Y có thể nâng tổng lên từ $10 tới $115 (raise tối đa theo pot-limit: call $5 thành pot $110, rồi raise thêm $110). Nếu Y chọn bất kỳ mức nào từ $10 tới $100, Y chỉ làm tăng kỳ vọng của X (nhánh tăng). Y cũng có thể chọn từ $100 tới $115, nhưng mọi đồng thêm trên $100 làm giảm kỳ vọng của X, nên nếu raise trên $100 thì Y sẽ raise lên tối đa $115. Vậy chỉ còn so sánh hai hành động:

- ⟨X, Y call $5⟩ = (10/33)($5) + $65,15 = 1,52 + 65,15 = **$66,67**.
- ⟨X, Y raise lên $115⟩ = (−1/3)($115) + $128,79 = −38,33 + 128,79 = **$90,46**.

Do đó Y chỉ call $5. Bằng cách cược $5, X tăng kỳ vọng thêm $1,52 (sách ghi $1,50). Tới một mức nào đó, mỗi đô la X cược đem lại 10/33 đô la kỳ vọng. Nếu X cược $10, Y vẫn call, và kỳ vọng tăng thêm $1,52 lên $68,18 (sách ghi $68,19 do làm tròn).

#### Mức cược tối ưu

X có thể tiếp tục cược nhiều hơn cho tới khi hai lựa chọn của Y cho cùng giá trị; đó là điểm kỳ vọng của X lớn nhất. Khi X cược mức then chốt x, Y có hai lựa chọn: để tổng tiền mỗi người vào pot là x (call), hoặc raise pot để tổng là 3x + 100 (call x thành pot 2x + 100, rồi raise thêm 2x + 100).

⟨X, Y call x⟩ = ⟨X, Y raise lên 3x + 100⟩

- (10/33)x + 65,15 = −(1/3)(100 + 3x) + 128,79
- (10/33)x + 65,15 = −x − 33,33 + 128,79
- (10/33)x = −x + 30,30
- (43/33)x = 30,30, nên x = 30,30 × 33/43 = **$23,26**.

Đây là mức cược đúng cho X; nó tối đa hoá kỳ vọng. Dù Y làm gì, X được bảo đảm ít nhất:

⟨X, x = $23,26 ở flop⟩ = (10/33)(23,26) + 65,15 = 7,05 + 65,15 = **$72,20**.

(Nếu Y raise tối đa, tổng mỗi người là 3 × 23,26 + 100 = $169,77, và −169,77/3 + 128,79 = $72,20, cùng giá trị.)

So sánh: check $65,15; cược pot $100 thì −$4,55; cược tối ưu $23,26 thì $72,20.

#### Kết luận của hai ví dụ pot-limit

Độ sâu stack có tầm quan trọng quyết định tới cách chơi, ngay cả khi bài lật ngửa. Hơn nữa, như kết quả cho thấy, stack sâu hơn có lợi cho tay bài đã thành, vì chúng cho phép tay bài đã thành phạt draw ở turn khi draw trượt. Điều này phần nào ngược với quan niệm thông thường về draw và tay bài đã thành, rằng draw hưởng lợi từ stack sâu và implied odds. (Quan niệm đó đúng khi bài bị giấu; ở đây draw là draw mở.)

Một khái niệm quan trọng khác rút ra từ các ví dụ: **draw tốt được lợi rất nhiều khi đưa hết tiền vào pot sớm trong ván bài.**

### 5. Ví dụ 7.4 — No-limit trước flop: QQ đấu AK với hai độ sâu stack (Example 7.4, trang 87–88)

#### Đề bài

Một tình huống no-limit thường gặp. Hold'em no-limit; X có A♥ K♦, Y có Q♥ Q♣. Đang trước flop (preflop). Y đã đặt blind $100. Stack là $800.

Giả sử bài được lộ lần lượt: X thấy AK của mình trước, hành động, rồi Y mới lộ đôi Q. Giả sử X raise lên $300 (một mức tùy ý nhưng hợp lý). Chiến lược của Y nên thế nào?

AK hưởng lợi khi được xem đủ năm lá chung: nó chỉ ra đôi khoảng một phần ba số lần ở flop (1 − C(42,3)/C(48,3) = 33,6%), nhưng thắng tổng cộng khoảng 43% trước QQ. Vậy stack càng sâu, AK càng muốn đưa hết tiền vào, còn QQ càng nên cố xem flop và đẩy AK ra sau flop nếu flop không có A hay K — đúng không? **Sai.**

#### Stack nông ($800)

QQ của Y thắng hơn 57% (sách dùng 57,17%; người tổng hợp liệt kê đủ các bộ bài chung được khoảng 56,76%, xem Lưu ý; phần dưới giữ số của sách). Nếu Y raise lên $800 (all-in), X buộc phải call (sách nói X được 3 ăn 2; tính đúng là call $500 để giành $1.100, tức 2,2 ăn 1, X cần 31,25% và có khoảng 43%). Raise một mức nhỏ hơn không tốt hơn, vì X có thể re-raise lên $800 để bảo đảm equity của mình. All-in tốn Y thêm $700 (blind $100 đã ở trong pot).

⟨Y, all-in⟩ = 0,5717 × ($800 + $800) − $700 = 914,72 − 700 = **$214,72**.

Ngược lại, giả sử Y call (thêm $200). Pot có $600. Flop có A hoặc K nhưng không có Q khoảng 30% số lần (chính xác 30,64%). Khi đó X với AK chỉ cần all-in ở flop và Y fold. 70% số lần còn lại, Y all-in và X fold.

⟨Y, call⟩ = p(flop có A hoặc K) × (Y mất tiền call) + p(flop không có A hoặc K) × (pot) = 0,3 × (−$200) + 0,7 × ($400) = −60 + 280 = **$220**.

(Ở nhánh thứ hai Y giành pot $600 và đã bỏ thêm $200, nên được $400. Với xác suất chính xác 30,64%, ⟨Y, call⟩ = $216,14, vẫn lớn hơn $214,72.) Vậy Y làm tốt hơn chút ít khi call và xem AK có trúng flop không, rồi all-in nếu AK trượt.

#### Stack sâu ($1.800)

Tăng stack lên $1.800 thì tình thế đảo ngược:

- ⟨Y, all-in⟩ = p(Y thắng) × (pot) − chi phí all-in = 0,5717 × $3.600 − $1.700 = 2.058,12 − 1.700 = **$358,12**.
- ⟨Y, call⟩ = vẫn **$220** (tiền vào pot và kết quả sau flop không đổi: bên trúng flop all-in, bên kia fold).

Vậy Y làm tốt hơn nhiều khi all-in ngay. (Người tổng hợp kiểm tra: X call $1.500 để giành $2.100 cần 41,67% equity và có khoảng 42,83%, nên X vẫn call, dù rất sát.)

| Stack | ⟨Y, all-in ngay⟩ | ⟨Y, call rồi chơi theo flop⟩ | Lựa chọn của Y |
|---:|---:|---:|---|
| $800 | $214,72 | $220 (chính xác $216,14) | call |
| $1.800 | $358,12 | $220 (chính xác $216,14) | all-in |

#### Bình luận

Kết quả này ngược với trực giác của nhiều người về cách cặp QQ/AK diễn ra: với stack sâu, QQ muốn đưa hết tiền vào vì lợi thế equity đáng kể; với stack nông hơn, QQ thích đẩy AK ra khỏi pot ở những flop thuận lợi. Kết luận này hơi giả tạo: ở đây QQ có thể đẩy hết chip vào không sợ hãi vì biết mình có lợi thế. Trong hold'em thật, QQ phải sợ AA hay KK, nên không thể chơi hẳn như vậy. Tuy nhiên, nhiều người chơi đánh giá quá cao việc xem flop, quên rằng tay bài của họ không phải một ván "tung đồng xu" (coin flip) đơn giản mà là cửa trên đáng kể so với AK.

### 6. Phần kết chương (trang 88)

Quay lại giả thuyết ban đầu rằng hành động ở mỗi vòng nên là "tay bài đã thành cược, còn draw call hoặc fold tùy theo có đủ pot odds hay không": ta đã thấy nhiều tình huống hoàn toàn không như vậy. Trong pot-limit, chẳng hạn, độ lớn stack còn lại ảnh hưởng sâu sắc tới chiến lược đúng của mỗi người, và điều này cũng đúng trong limit (Ví dụ 7.1). Trong no-limit, ta đã thấy một trường hợp mà độ sâu stack là yếu tố quyết định giữa all-in và chỉ call.

Dù có những tình huống thú vị trong các trò chơi bài lật ngửa, người đọc khó gặp được trò chơi như vậy. Tác giả trình bày chúng như tài liệu nền cho các trường hợp tiếp theo: mọi kỹ năng đọc bài trên đời đều vô dụng nếu không chơi chính xác được khi bài đã lật ngửa; và tuy các nguyên tắc thường có giá trị như quy tắc kinh nghiệm, việc nhận ra những tình huống mà cách chơi đúng lệch khỏi điều trực giác cho là hiển nhiên có thể đáng giá equity.

### 7. Các ý then chốt (Key Concepts, trang 88)

- Ngay cả khi chơi với bài lật ngửa, vẫn có thể xảy ra các tình huống trái trực giác.
- Khi cân nhắc lần raise all-in cuối cùng, draw nên cân nhắc hung hăng hơn mức mà phân tích pot odds đơn giản chỉ ra. Cược thêm không thể làm hại draw nữa, và tay bài đã thành không thể thoát ra nếu draw trúng khi tiền đã vào hết.
- Độ sâu stack có tầm quan trọng quyết định trong poker cược lớn (big bet poker, tức pot-limit và no-limit); ngay cả với bài lật ngửa, thay đổi stack làm thay đổi hẳn bản chất cách chơi. Có thể xảy ra tình huống người có cửa thắng cao hơn phải fold trước cược của người có cửa thấp hơn, vì khả năng có cược ở các vòng sau.
- Draw tốt (draw có equity gần 50% trong pot) được lợi lớn khi đưa hết tiền vào ở flop. Tuy nhiên, nếu không thể đưa hết tiền vào (hoặc đủ nhiều để không bị cược sau làm hại), chúng muốn đưa vào càng ít càng tốt.
- Tay bài đã thành thường muốn giữ lại đủ một cược lớn cho vòng sau khi chơi với draw, vì rút được rất nhiều giá trị khi draw trượt.

## Luận điểm cốt lõi

### Mệnh đề

Khi bài đã biết, cách chơi tối đa hoá kỳ vọng được tìm bằng cách liệt kê các phương án có ý định, loại phương án bị trội và tính kỳ vọng theo phản ứng tốt nhất của đối thủ; kết quả thường trái trực giác "tay bài đã thành cược, draw theo pot odds", vì độ sâu stack quyết định tiền còn lại cho các vòng sau.

### Giả định

- Hai người chơi, bài lật ngửa (hoặc lộ lần lượt như Ví dụ 7.4), không ai khác chia pot.
- Mô hình outs đơn giản: draw có số outs cố định mỗi vòng, bỏ qua runner-runner.
- Không có phí nhà cái; mỗi người tối đa hoá kỳ vọng tiền.
- Pot-limit cứng chỉ cho phép cược đúng bằng pot (Ví dụ 7.2); pot-limit thật cho phép mọi mức tới pot (Ví dụ 7.3).
- Ở Ví dụ 7.4, xác suất flop được làm tròn thành 30%/70% và sau flop bên trúng all-in, bên kia fold.

### Cơ chế

1. Liệt kê phương án kèm ý định cho hành động tiếp theo cùng vòng.
2. So sánh hai phương án ở nhánh chúng khác nhau; loại phương án bị trội.
3. Đoán phản ứng của đối thủ, tính kỳ vọng, rồi kiểm tra xem đối thủ có phản ứng tốt hơn không (lặp đến khi không ai muốn đổi).
4. Ở vòng sau, khi tay bài đã thành còn tiền để cược pot, draw trượt phải trả giá; khi draw đã all-in, không còn cược để phạt.
5. Do đó draw tốt muốn hết tiền vào sớm, hoặc đưa vào càng ít càng tốt; tay bài đã thành muốn giữ lại một cược pot cho turn.
6. Trong pot-limit và no-limit, viết kỳ vọng như hàm của tiền vào pot và chọn mức cược cân bằng hai phản ứng tốt nhất của đối thủ.

### Bằng chứng và ví dụ tác giả đưa ra

- Ví dụ 7.1: X bet, Y raise, X call; X được ≈ $297 (bet-call khi Y call sẽ là $308,43; check là $290,24).
- Ví dụ 7.2: stack $50 → X $37,88; stack $400 → check-check, X $65,15; stack $1.300 → X bet, Y call, X $95,45; 14 outs → Y fold dù có 53% equity.
- Ví dụ 7.3: ⟨X⟩ = 10x/33 + 65,15 hoặc −x/3 + 128,79; cược tối ưu $23,26, X được $72,20.
- Ví dụ 7.4: stack $800 → Y call ($220 so với $214,72); stack $1.800 → Y all-in ($358,12 so với $220).

### Kết luận và hàm ý cho người chơi

- Trước mỗi hành động, nghĩ luôn hành động tiếp theo nếu bị raise hoặc bị cược.
- Khi cầm draw mạnh và có thể đưa hết tiền vào, hãy hung hăng: raise, kể cả khi đang là cửa dưới.
- Khi cầm tay bài đã thành đấu draw, đừng tự động cược tối đa; cân nhắc giữ lại đủ tiền để phạt draw ở vòng sau, hoặc cược nhỏ (như $23,26 vào pot $100) để draw không có lý do raise.
- Tính stack còn lại theo số lần cược pot; hai hay ba lần cược pot cho cách chơi rất khác nhau.
- Với QQ trước AK đã biết, stack càng sâu càng nên đưa hết tiền vào sớm.

### Trong ngôn ngữ lý thuyết trò chơi

Các ví dụ là trò chơi hai người tổng không đổi (tổng kỳ vọng của X và Y luôn bằng pot ban đầu) với thông tin hoàn hảo về bài nhưng có yếu tố may rủi (lá bài sắp ra). Cách giải là quy nạp ngược (backward induction) trên cây trò chơi: xác định hành động ở turn trước, rồi suy ngược về flop. Việc loại check-fold và bet-fold là loại chiến lược bị trội. Mức cược $23,26 ở Ví dụ 7.3 là lời giải minimax: X chọn x để tối đa hoá min(10x/33 + 65,15; −(3x + 100)/3 + 128,79), tức điểm hai phản ứng tốt nhất của Y cho X cùng một giá trị — ý tưởng "làm đối thủ bàng quan" sẽ là trung tâm của Phần III (Chương 10 trở đi).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| exploitive play | chơi khai thác | chơi tận dụng điểm yếu cụ thể của đối thủ |
| expected value (EV) | kỳ vọng | trung bình có trọng số theo xác suất của kết quả |
| distribution (of hands) | phân phối bài | tập các tay bài đối thủ có thể cầm cùng xác suất |
| cards exposed / face-up | bài lật ngửa | hai người đều thấy bài nhau |
| made hand | tay bài đã thành | tay bài đang dẫn, không cần cải thiện |
| draw | draw, tay bài đang chờ | tay bài đang thua nhưng có thể vượt nếu ra lá cần |
| outs | outs | số lá giúp draw thắng |
| equity | equity | phần pot "sở hữu" theo xác suất thắng nếu chia bài tới cuối |
| showdown | showdown | lật bài so sánh sau vòng cược cuối |
| pot odds | pot odds | tỷ lệ pot so với tiền phải call |
| implied odds | implied odds | tiền kỳ vọng thắng thêm ở các vòng sau nếu trúng |
| 7-card stud | stud bảy lá | biến thể poker mỗi người bảy lá riêng, một số lá ngửa |
| fifth / sixth street, river | lá thứ năm / thứ sáu, river | các vòng chia bài trong stud; river là lá cuối |
| flush | thùng | năm lá cùng chất |
| straight | sảnh | năm lá liên tiếp |
| straight-flush draw | draw thùng phá sảnh | draw có thể ra thùng, sảnh hoặc thùng phá sảnh |
| full house | cù lũ | bộ ba cộng một đôi |
| runner-runner | runner-runner | cần trúng cả hai lá cuối liên tiếp |
| cover (a player) | cover | có nhiều chip hơn người kia |
| check, bet, call, raise, fold | check, bet, call, raise, fold | không cược, cược, theo, tố thêm, bỏ bài |
| check-fold, check-call, check-raise | check-fold, check-call, check-raise | check kèm ý định fold, call hoặc raise nếu bị cược |
| bet-call, bet-fold | bet-call, bet-fold | bet kèm ý định call hoặc fold nếu bị raise |
| flat call | call (không raise) | chỉ theo, không tố thêm |
| check behind | check theo | check khi đối thủ trước đã check |
| all-in, jam | all-in, jam | đặt toàn bộ chip còn lại |
| stack, stack size | stack, độ sâu stack | số chip còn lại có thể cược |
| pot-limit | pot-limit | luật cược tối đa bằng pot |
| rigid pot limit | pot-limit cứng | biến thể của sách: chỉ cược đúng bằng pot |
| no-limit | no-limit | luật cược không giới hạn trên |
| limit | limit | luật cược theo mức cố định |
| big bet poker | poker cược lớn | pot-limit và no-limit |
| blind | blind | tiền cược bắt buộc trước khi chia bài |
| preflop, flop, turn, river | preflop, flop, turn, river | các vòng của hold'em |
| hold'em | hold'em | biến thể poker hai lá riêng, năm lá chung |
| open draw / closed draw | draw mở / draw đóng | draw mà đối thủ thấy / không thấy khi nó trúng |
| favorite / underdog (dog) | cửa trên / cửa dưới | người có / không có xác suất thắng cao hơn |
| coin flip | tung đồng xu | ván gần 50–50 |
| dominated option | phương án bị trội | luôn không tốt hơn một phương án khác |
| backward induction | quy nạp ngược | giải cây trò chơi từ cuối về đầu |

## Câu nói đáng nhớ

> "Exploitive play is a two-step process." — trang 77
>
> *Dịch: Chơi khai thác là một quy trình hai bước.*

Ý nghĩa: đọc bài (bước một) và chọn hành động tối đa hoá kỳ vọng (bước hai) là hai việc tách biệt; chương này lo bước hai.

> "Many errors can be prevented or mitigated by considering the action that will follow when taking an initial action." — trang 77
>
> *Dịch: Nhiều lỗi có thể tránh hoặc giảm bớt bằng cách cân nhắc hành động sẽ tiếp theo khi thực hiện hành động đầu tiên.*

Ý nghĩa: lý do tác giả mô tả phương án như check-raise, bet-fold thay vì chỉ check hay bet.

> "It is in turn correct for Y to raise, while a 2-1 dog to make his hand!" — trang 79
>
> *Dịch: Đến lượt mình, Y raise lại là đúng, dù đang thua khoảng 2 ăn 1 để ra bài!*

Ý nghĩa: draw sắp all-in nên hung hăng vì không còn bị phạt ở vòng sau.

> "Good draws benefit a great deal from getting all the money in the pot early in the hand." — trang 87
>
> *Dịch: Draw tốt được lợi rất nhiều khi đưa hết tiền vào pot sớm trong ván bài.*

Ý nghĩa: ý then chốt của các ví dụ pot-limit.

> "Deeper stacks favor the made hand because they allow the made hand to punish the draw on the turn when he misses." — trang 87
>
> *Dịch: Stack sâu hơn có lợi cho tay bài đã thành, vì chúng cho phép tay bài đã thành phạt draw ở turn khi draw trượt.*

Ý nghĩa: đảo ngược quan niệm phổ biến rằng draw hưởng lợi từ stack sâu.

> "Many players overvalue seeing the flop, forgetting that their hand is not a simple 'coin flip,' but a substantial favorite over AK." — trang 88
>
> *Dịch: Nhiều người chơi đánh giá quá cao việc xem flop, quên rằng tay bài của họ không phải một ván tung đồng xu đơn giản, mà là cửa trên đáng kể so với AK.*

Ý nghĩa: với QQ trước AK và stack sâu, đưa hết tiền vào sớm tốt hơn.

> "All the hand-reading skills in the world are of no use if one cannot play accurately when the cards are face-up." — trang 88
>
> *Dịch: Mọi kỹ năng đọc bài trên đời đều vô dụng nếu không chơi chính xác được khi bài đã lật ngửa.*

Ý nghĩa: lý do của cả chương: bước hai phải làm đúng trước khi bước một có giá trị.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương cho thấy rõ một cách làm có hệ thống: liệt kê phương án có ý định, loại phương án bị trội, đoán phản ứng của đối thủ rồi kiểm tra lại — đây chính là quy nạp ngược trên cây trò chơi, trình bày bằng ví dụ cụ thể. Ba ví dụ AA đấu 87 chuồn với cùng bài nhưng stack khác nhau là minh hoạ rất mạnh: chỉ riêng stack đổi cách chơi đúng từ "X check, Y bet" sang "check-check" sang "X bet, Y call", và giá trị tay bài của X từ $37,88 lên $95,45. Hàm kỳ vọng gấp khúc ở Ví dụ 7.3 và mức cược $23,26 là một kết quả đẹp: cược nhỏ hơn nhiều so với pot lại tốt nhất cho tay bài mạnh, vì nó không cho draw cơ hội raise với giá rẻ. Ví dụ 7.4 thách thức trực tiếp một niềm tin phổ biến của người chơi.

### Những chỗ đơn giản hoá

- **Bài lật ngửa** loại bỏ hoàn toàn bluff và bất định về bài; mọi kết luận cần điều chỉnh khi chỉ biết phân phối bài (Chương 8–9). Chính tác giả thừa nhận kết luận của Ví dụ 7.4 "hơi giả tạo" vì trong thực tế QQ phải sợ AA, KK.
- **Mô hình outs cố định** bỏ qua runner-runner; equity chính xác của 87 chuồn là 56,26% thay vì 56,06% (người tổng hợp liệt kê đủ 990 trường hợp).
- **Ví dụ 7.4** làm tròn xác suất flop thành 30% và giả định bên thua sau flop luôn fold; với AK có thể có draw sảnh hoặc thùng sau flop, và QQ có thể bị đe doạ bởi lá cao khác. Với số chính xác, ưu thế của call ở stack $800 chỉ còn khoảng $1,4.
- **Ví dụ 7.3** giả định khi bị raise, X không re-raise và khi Y trượt, X luôn cược pot hoặc all-in ở turn; trong pot-limit thật, mức cược ở turn cũng có thể tối ưu hoá.
- **Một lỗi tính lớn** (tiểu trường hợp c: $346,21 thay vì $186,36) không ảnh hưởng tới kết luận nhưng cho thấy người đọc nên tự tính lại.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp, không tra cứu)

- Solver ngày nay giải chính xác các bài toán như Ví dụ 7.3 cho mọi mức cược và mọi độ sâu stack; ý tưởng "draw mạnh muốn hết tiền vào sớm" và "cược nhỏ để không bị raise" đã thành hiểu biết phổ thông trong cộng đồng chơi theo lý thuyết trò chơi.
- Pot-limit Omaha (nơi draw thường có equity gần 50% trước tay bài đã thành) trở nên rất phổ biến; các bài học về stack sâu và draw mạnh của chương này đặc biệt hợp với trò chơi đó.
- Khái niệm "stack-to-pot ratio" (tỷ số stack trên pot), phổ biến từ khoảng 2008, hệ thống hoá đúng quan sát của chương rằng số lần cược pot còn lại quyết định cách chơi.

### Liên hệ các chương khác

- [C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md): quy tắc pot odds mà chương này thử thách.
- [C05-doc-bai-va-chien-luoc.md](C05-doc-bai-va-chien-luoc.md): bước một của chơi khai thác (đọc bài).
- [C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md): từ bài lật ngửa sang một tay bài đấu với một phân phối.
- [C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md): phân phối đấu với phân phối và chiến lược thích nghi.
- [C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md): khi stack nông, cách chơi rút về jam hoặc fold.
- [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md): chọn mức cược trong no-limit, tiếp nối ý tưởng mức cược tối ưu của Ví dụ 7.3.
- [C19-tro-choi-nhieu-vong-tinh.md](C19-tro-choi-nhieu-vong-tinh.md), [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md): tương tác giữa các vòng cược khi bài không lộ.

### Vận dụng

- **Người chơi poker:** đếm stack theo số lần cược pot trước khi quyết định. Cầm draw mạnh với stack vừa đủ thì tìm cách all-in; cầm tay bài đã thành trước draw thì cân nhắc cược nhỏ hoặc check để giữ "đạn" cho turn, thay vì cược pot mặc định.
- **Người làm tài chính và đầu tư:** bài học "bên có lợi thế muốn giữ lại vốn cho vòng sau, bên có lợi thế tạm thời muốn khoá kết quả ngay" tương tự việc chọn thời điểm cam kết vốn theo giai đoạn (đầu tư mạo hiểm theo vòng): nhà đầu tư giữ quyền rót tiếp có thể "phạt" dự án thất bại bằng cách không rót, còn bên cần tiền muốn huy động hết sớm. Cách giải bằng cây quyết định và quy nạp ngược là công cụ chuẩn trong định giá quyền chọn thực (real options).
- **Người ra quyết định nói chung:** khi chọn một hành động, hãy xác định trước phản ứng của mình với mỗi phản ứng của đối phương; nhiều phương án sẽ tự bị loại vì bị trội. Và đừng mặc định "dồn hết sức" là tốt nhất khi đang có lợi thế: mức cam kết tối ưu thường là mức làm đối phương không còn phản ứng có lợi.

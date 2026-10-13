# Chương 15 — Người chơi X phản công: các trò chơi full-street (Player X Strikes Back: Full-Street Games)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 15 "Player X Strikes Back: Full-Street Games", trang 163–175, và Phụ lục Chương 15 "The No-Limit AKQ Game", trang 176–182.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Các Chương 11–14 ([C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md), [C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md), [C13-tro-choi-akq.md](C13-tro-choi-akq.md), [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md)) giải các trò chơi half-street: X bắt buộc check, chỉ Y được bet. Hai kết quả mang sang chương này là hằng số α (tỷ lệ bluff so với value bet và tỷ lệ fold của người bị bet: α = 1/(P + 1) trong limit, α = s/(1 + s) trong no-limit) và kỹ thuật chọn mức cược với hằng số r = √2 − 1 của Chương 14. Chương 15 mở đầu các trò chơi **full-street** (một vòng cược đầy đủ): X được chọn bet hay check. Chương cho thấy quyền bet của X không bao giờ làm X mất giá trị, rằng chiến lược phải được viết thành các "kế hoạch trọn vẹn" (bet / check-call / check-fold), và — bất ngờ nhất — rằng khi có hai mức cược, X có thể bet một tay bài ở giữa (K) chỉ để **chặn trước** (preemptive bet) cú bluff của Y. Phụ lục giải trò chơi AKQ no-limit đầy đủ. Các Chương 16–18 ([C16-tro-choi-01-khong-bo-bai.md](C16-tro-choi-01-khong-bo-bai.md), [C17-tro-choi-01-pot-huu-han-va-bluff.md](C17-tro-choi-01-pot-huu-han-va-bluff.md), [C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md)) đưa các ý tưởng full-street vào trò chơi [0,1]; Chương 19–20 ([C19-tro-choi-nhieu-vong-tinh.md](C19-tro-choi-nhieu-vong-tinh.md), [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md)) mở rộng ra nhiều vòng cược.
**Ý chính:** **Khi người hành động trước (X) được quyền bet, X không bao giờ thiệt (vì luôn có thể check như trong half-street), các tỷ lệ α vẫn đúng cho cả hai phía, nhưng lựa chọn sớm làm thay đổi phân phối tay bài ở các nút sau, và khi có nhiều mức cược thì xuất hiện những nước đi không phải value bet cũng không phải bluff.** Ví dụ 15.1 (AKQ #4, limit, pot P, cược 1, không raise): sau khi loại chiến lược bị trội, X chỉ còn chọn tỷ lệ x số A đem bet; X bluff Q theo tỷ lệ b/x = α (Phương trình 15.1), check-call với tỷ lệ c = 1 − 2α + αx số K (Phương trình 15.2); Y call với 1 − 2α số K khi bị bet, bet mọi A và α số Q khi X check. Giá trị trò chơi với Y là [x(3α − 1) + 1 − 2α]/6; X chọn x = 0 (check mọi tay) khi 1 < P < 2 và x = 1 (bet mọi A) khi P > 2. Ví dụ 15.2 (AKQ #5, pot 4, được bet hoặc raise 1 hoặc 2 đơn vị): lời giải "ngây thơ" (cả hai bỏ qua cược 1 đơn vị, giá trị với Y là 1/9) không tối ưu vì X cầm K mà bet 1 đơn vị thì chỉ mất 1/2 thay vì 2/3. Y đáp lại bằng raise với A và raise-bluff 1/15 số Q; X lại thấy bet 1 với A lời hơn check (11/30 so với 1/3); cân bằng mới: X bet 1 với mọi A, 40% K, 20% Q, giá trị với Y giảm còn 1/10. Cú bet K đó là **cược chặn trước** (preemptive bet): EV âm nhưng ít âm hơn check. Phụ lục (AKQ no-limit): nếu X không được bet K, X bet r = √2 − 1 với 21,7% số A, Y bet 0,5088 pot khi X check, giá trị với Y khoảng 0,02761; khi X được bet K, X bet τ ≈ 0,2521 pot với 38,8% số A, 15,6% số K và 7,8% số Q, Y bet s₀ ≈ 0,5422 pot khi X check, raise lên 2τ với A và raise-bluff khoảng 7,9% số Q; giá trị với Y giảm còn khoảng 0,02682.

> **Lưu ý:**
> - **Trích dẫn sai ví dụ và chương:** trang 169 viết "Recall that AKQ Game #3 (Example 14.1)"; trò chơi AKQ #3 là **Ví dụ 14.2** (Ví dụ 14.1 là trò chơi biết trước bài). Đầu phụ lục (trang 176) viết lời giải AKQ no-limit "surprisingly close to the solution to the spread-limit game from Chapter 17"; trò chơi spread-limit là **Ví dụ 15.2 của Chương 15**. Trang 164 viết P > 1 "for the same reason as in AKQ Game #1 – Example 13.1"; lý do (bluff Q lỗ khi P < 1) được nêu ở Ví dụ 13.2 (AKQ #2).
> - **Dấu sai trong ma trận rút gọn lần hai của AKQ #4 (trang 164):** ô "X cầm K, Chk/Fold; Y cầm Q, Fold/Bet" in **−P**; theo hai ma trận trước, Y bluff Q và X fold K thì Y lấy pot, nên giá trị theo phía Y là **+P**.
> - **"Fold" thay vì "call" (trang 165):** sách viết ở AKQ #2 "the fraction of his kings he would fold is (P − 1)/(P + 1)"; (P − 1)/(P + 1) là tỷ lệ K mà X **call** (tỷ lệ fold là 2/(P + 1)), như chính công thức 15.2 tại x = 0 xác nhận.
> - **Kiểm tra công thức 15.2 tại x = 0 in lộn xộn (trang 166):** sách viết "c = 1 − 2α[1/(P+1)]" và kết thúc bằng "α = (P − 1)/(P + 1)". Đúng là c = 1 − 2·[1/(P + 1)] = (P − 1)/(P + 1); dòng cuối phải là **c** = (P − 1)/(P + 1), không phải α.
> - **Bảng giá trị AKQ #5 (trang 174) có ba ô sai:** bảng ghi giá trị theo phía X (người hành động trước). Hàng (X: K, Y: Q, "chk – b2 – f") in giá trị **4**, đúng là **−4** (X fold K trước cú bluff 2 đơn vị, mất pot 4); trọng số −2/45 in đúng. Hàng (X: Q, Y: K, "b1 – call") in giá trị **1**, đúng là **−1** (X bluff bị K call); trọng số −1/50 in đúng. Hàng (X: Q, Y: K, "b1 – fold") in giá trị **1** và trọng số **+1/75**, đúng là giá trị **4** (X lấy pot 4) và trọng số **+4/75**. Cộng các trọng số in trong bảng được −7/50, không phải −1/10; sau khi sửa ô cuối, tổng đúng bằng **−1/10** như dòng Total của sách (người tổng hợp kiểm tra bằng phân số chính xác; tổng xác suất bằng 1).
> - **Giá trị của chiến lược "ngây thơ" in sai (trang 174):** sách viết "The value of the naive strategy ... was 1/6 ... a difference of 1/90". Giá trị đó đã được tính ở trang 170 là f(s = 2, P = 4) = **1/9** với Y (tức −1/9 với X); 1/9 − 1/10 = 1/90 khớp với "chênh lệch 1/90", nên "1/6" là in nhầm của 1/9.
> - **Lời văn AKQ #5 không nhất quán về mức raise-bluff (trang 172):** sách định nghĩa q là tần suất raise-bluff "khi raise thêm một đơn vị" rồi viết "If the raise amount is two units, Y bluff-raises 1/15"; lời giải cuối ghi "raise one unit with aces and 1/15 of queens". Như sách nói ngay sau đó, khi X cầm K thì mức raise không quan trọng (K fold), còn khi X cầm A thì Y muốn raise mức nhỏ; nên mức đúng trong lời giải là raise một đơn vị (lên tổng 2).
> - **Các lỗi công thức trong phụ lục (trang 178–182), người tổng hợp đã tính lại:**
>   - "⟨A vs. K, bet t⟩ = (t − t)²/(t + 1)" phải là **(t − t²)/(1 + t)**.
>   - "Y will then call with (t − 1)/(t + 1) of his kings" phải là **(1 − t)/(1 + t)** (với t = r giá trị này bằng r ≈ 0,414).
>   - "⟨A, check⟩ = (s(1 + s))(s)(1/2)" phải là **(s/(1 + s))·s·(1/2)** = s²/[2(1 + s)].
>   - "bets r (about 41.2% of the pot)" phải là **41,4%**.
>   - "Y responds to a bet of t ... total calling frequency ... equal to 1/(1 + s)" phải là **1/(1 + t)**.
>   - "X calls an s size bet with about 39.8% of his kings": tính lại được 39,86% (làm tròn 39,9%); đáng chú ý là tỷ lệ này đúng bằng q·A_k.
>   - "We define α₀ = s₀(1 + s₀)" phải là **s₀/(1 + s₀)**; hai lần "β = (α₀ − t)(1 + t)" trong phần dẫn giải phải là **(α₀ − t)/(1 + t)** (phần tóm tắt lời giải in đúng); "p can be zero" là "β can be zero".
>   - Trong phép lấy đạo hàm A′(t), ba dòng giữa in sai dấu: đúng là 0 = 1 − 6t − 3t² + 2α₀, tức **3t² + 6t − 2α₀ − 1 = 0** và t² + 2t − (2/3)α₀ − 1/3 = 0; dòng kết quả (t + 1)² = (2/3)α₀ + 4/3 của sách thì đúng.
>   - Điểm mà mức raise lý thuyết bằng mức raise tối thiểu 2t: sách ghi "close to 0.2001"; giải 4t² + (2 − 3α₀)t − α₀ = 0 với α₀ ≈ 0,35159 được **t ≈ 0,2010**.
>   - Hệ hai phương trình cuối cho kết quả "b ≈ 1.45595, c ≈ 0.55405" với b là tổng lượng tay đem bet, c là tổng lượng tay check. Giải lại được **b ≈ 0,54406, c ≈ 1,45594** (hai giá trị bị đổi chỗ, và 0,55405 sai một chữ số). Các tỷ lệ cuối A_k = 61,213%, A_b = 38,787%, K_k = 84,382%, K_b = 15,618% của sách chỉ khớp với cặp đã sửa (ví dụ A_k = 0,42043 × 1,45594 = 0,61212).
> - **Ký hiệu q bị dùng lại trong phụ lục:** q lần lượt là mức Y bet khi X check (trang 178, 182) và mức raise của Y (trang 182, q = 2τ ≈ 0,5042). Bảng "Second player's hand" ở trang 181 trộn giá trị tuyệt đối và tương đối (hàng A ghi chênh lệch call so với fold, hàng Q ghi giá trị tuyệt đối), nhưng phương trình t₂ − t = β(t₂ + 1 + t) rút ra từ nó là đúng.
> - **Kiểm tra số của phụ lục (nhận xét của người tổng hợp):** người tổng hợp lập trình lại cả hai chiến lược (trò chơi rút gọn và trò chơi đầy đủ), kiểm tra mọi điều kiện bàng quan (X cầm K bàng quan giữa check và bet τ, X cầm A bàng quan giữa check và bet τ, X bluff Q hoà vốn, Y raise-bluff Q hoà vốn, Y bluff Q sau khi X check hoà vốn, Y call K hoà vốn) và tính lại giá trị trò chơi: 0,02761 cho trò chơi rút gọn và 0,02682 cho trò chơi đầy đủ, khớp với sách. Các số s ≈ 0,50879, A_k ≈ 0,78342, s₀ ≈ 0,54224, α₀ ≈ 0,35159, τ ≈ 0,25209, k ≈ 0,57957, tỷ lệ K/(A + K) khi bet ≈ 0,28707 đều đúng.
> - **Lỗi OCR và chính tả:** "including a bluff" là "inducing a bluff"; "AXQ", "AKO" là "AKQ"; "we can end that" là "we can find that"; "lungs", "Icing" là "kings"; "hw kings" là "his kings"; "hi half-street" là "In half-street"; "turm" là "turn"; "bl", "rl" trong bảng là "b1", "r1" (bet 1, raise 1). Phân số làm phẳng ("115" là 1/15, "1130" là 11/30, "1516" là 15/16) đã đọc lại từ ảnh.
> - **Quy ước:** giá trị tính ngoài showdown. Ở Ví dụ 15.1 và phần lớn chương, ma trận và giá trị ghi theo phía Y ("người chơi thứ hai"); riêng bảng giá trị của Ví dụ 15.2 ghi theo phía X ("P1"). Trong limit, cược bằng 1 và pot bằng P; trong no-limit (phụ lục), pot bằng 1 và cược tính theo phần của pot.

## Sơ đồ

### Phần mở đầu Chương 15 — ba ý tưởng khi chuyển từ half-street sang full-street (trang 163)

```text
       Half-street (Chương 11–14): X bắt buộc check "trong bóng tối";
       Y check hoặc value bet / bluff
       Full-street (từ chương này): X được bet hoặc check; nếu X bet, Y
       call, đôi khi được raise hoặc fold; nếu X check, Y check hoặc bet
                                │
               ┌────────────────┼────────────────┐
               ▼                ▼                ▼
       Ý 1: tỷ lệ bet/     Ý 2: X KHÔNG THỂ    Ý 3 (quan trọng nhất):
       bluff vẫn đúng      MẤT GIÁ TRỊ khi     cách viết chiến lược
       cho X; nhưng việc   chuyển sang full-   · half-street: mỗi người
       X có thể bet làm    street: nếu tệ hơn,   một hành động
       THAY ĐỔI phân phối  X cứ check như cũ   · full-street: X có kế
       tay bài khi X check (lựa chọn chiến       hoạch trọn vẹn: BET,
       → Y chơi khác sau   lược luôn có giá      CHECK-CALL, CHECK-FOLD
       cú check            trị không âm)       · ma trận lợi ích lập
                                                 theo các kế hoạch đó
```

### Ví dụ 15.1 — Trò chơi AKQ số 4: AKQ full-street limit (Example 15.1 AKQ Game #4, trang 164–169)

```text
       Một full-street, pot P (P > 1), cược limit 1, không được raise
                                │
                                ▼
       Ma trận đầy đủ 3 kế hoạch của X × 4 phản ứng của Y, theo cặp lá
       Loại chiến lược bị trội:
       · X: check-fold A, check-call Q
       · Y: call bằng Q, fold A, check A sau khi X check
       · rồi: bet K bị trội với CẢ HAI người
                                │
                                ▼
       Còn lại các biến:
       · X: x = tỷ lệ A đem bet; c = tỷ lệ K check-call; b = tỷ lệ Q bluff
       · Y: tỷ lệ K call khi bị bet; tỷ lệ Q bluff khi X check
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       KHI X BET (A và Q):                KHI X CHECK:
       · Y call (P − 1)/(P + 1)           · Y bet mọi A và α số Q
         = 1 − 2α số K (fold α số tay     · X fold α số tay bắt bluff
         bắt bluff)                         còn lại; vì đã bet x số A:
       · X bluff Q: b/x = α  (15.1)         c = 1 − 2α + αx  (15.2)
         (Y call K được P + 1 khi gặp     · x = 0 → c = (P − 1)/(P + 1);
         Q, mất 1 khi gặp A)                x = 1 → c = 1 − α
               └────────────────┬────────────────┘
                                ▼
       Giá trị với Y qua 6 cặp lá:
       (A,K) −x(1 − 2α); (A,Q) −α(1 − x); (K,A) 1 − 2α + αx;
       (K,Q) α(1 − x); (Q,A) αx; (Q,K) −αx
       Tổng = [x(3α − 1) + 1 − 2α]/6
                                │
                                ▼
       X chọn x làm giá trị của Y nhỏ nhất:
       · 1 < P < 2 (α > 1/3): x = 0 → X check mọi tay (như half-street)
       · P > 2 (α < 1/3): x = 1 → X bet mọi A và 1/(P + 1) số Q; check-
         call P/(P + 1) số K
       · P = 2: X bàng quan; mọi đường giá trị đi qua x = 2/3, f = 1/18
                                │
                                ▼
       Cho phép raise cũng không ai cải thiện được (trừ A gặp Q sẽ fold)
       → đây cũng là lời giải của trò chơi có raise
```

### Ví dụ 15.2 — Trò chơi AKQ số 5: hai mức cược và cược chặn trước (Example 15.2 AKQ Game #5, trang 169–174)

```text
       Pot 4; mỗi bên được check (nếu chưa ai hành động), bet hoặc raise
       1 hoặc 2 đơn vị (spread-limit) — như AKQ #4 với P = 2 nhưng thêm
       mức cược 1/4 pot bên cạnh 1/2 pot
                                │
                                ▼
       Lời giải "ngây thơ": ai cũng dùng mức 2 như AKQ #4 với P = 2
       · giá trị với Y = 2 × 1/18 = 1/9
       · X bet 1 với A: được 3/10 < 1/3 khi check → không lợi
       · Y bet 1 khi X check: f(1, 4) = 1/10 < 1/9 → không lợi
       · có vẻ đây chỉ là mở rộng nhẹ… "Hay không phải vậy?"
                                │
                                ▼
       Kiểm tra X cầm K: check thì mất 2/3 đơn vị (cả khi Y có A lẫn Q);
       BET 1 với K: Y A call, Y Q fold → chỉ mất 1/2
       → X lời 1/6 → lời giải ngây thơ KHÔNG tối ưu
                                │
                                ▼
       Y đáp lại: raise với A và RAISE-BLUFF với Q, vừa đủ để X bàng
       quan giữa bet 1 và check K (không phải để X bàng quan khi call):
       5 × (1/2) × q = 1/6 → q = 1/15; X cầm K fold mọi lần bị raise
       (15/16 lần Y có A)
                                │
                                ▼
       X lại có lựa chọn mới lời: bet 1 với A
       · bet 1: (3/5)(1/2)(1) + (1/15)(1/2)(2) = 11/30
       · check: (1/2)(1/3)(2) = 1/3 = 10/30 → bet lời thêm 1/30
       → X bet mọi A; tỷ lệ A : K khi bet = 5 : 2 để Y bàng quan khi
         raise-bluff (thắng 5 khi X có K, mất 2 khi X có A) → bet 40% K
                                │
                                ▼
       Lời giải: X bet 1 với mọi A, 40% K, 20% Q; bị raise thì A raise
       lại, K fold; check K còn lại, call cược 2 với 2/3 số K
       Y: X bet 1 → raise 1 với A và 1/15 số Q, call 3/5 số K;
          X check → bet 2 với A và 1/3 số Q
       Giá trị với Y: 1/10 (giảm 1/90 so với 1/9)
                                │
                                ▼
       Che giấu thông tin: nếu chỉ xét A, X thích bet 2; nhưng phải dùng
       chung một mức với K, nên chọn mức nhỏ vì cược chặn trước bằng K
       đáng giá hơn
```

### Khái niệm then chốt cuối chương (Key Concepts, trang 174–175)

```text
       1. Đừng dừng giải quá sớm: lời giải "trông hợp lý" chỉ lộ ra sai
          khi so equity của từng lựa chọn
       2. Chiến lược chỉ tối ưu khi KHÔNG BÊN NÀO cải thiện được
       3. CƯỢC CHẶN TRƯỚC (preemptive bet): không phải value bet, không
          phải bluff; X bet nhỏ để tước khả năng bluff hiệu quả của Y;
          xuất hiện khi có nhiều mức cược và người đi trước được bet nhỏ
          hơn mức người đi sau muốn
       4. EV âm nhưng ít âm hơn check; có lẽ có trong chiến lược tối ưu
          của no-limit hold'em trên river
       5. Sau cược chặn trước bằng K, X fold mọi lần bị raise dù Y đôi
          khi bluff — X đã có thừa A để bắt bluff; Y raise-bluff chỉ để
          X bàng quan khi BET K, không phải khi CALL bằng K
                                │
                                ▼
       Chuyển sang AKQ no-limit đầy đủ ở phụ lục: hiểu lời giải spread-
       limit là hiểu bài học quan trọng nhất của trò chơi no-limit
```

### Phụ lục Chương 15 — Tóm tắt các bước và lời giải trò chơi AKQ no-limit (Appendix to Chapter 15: The No-Limit AKQ Game — Summary, trang 176–177)

```text
       Bước 1: giải trò chơi phụ khi X KHÔNG được bet K: X bet r với một
       số A, check số A còn lại; Y bet mức s₀ lớn hơn khi X check
                                │
                                ▼
       Bước 2: nới ràng buộc → X bet mức nhỏ t với một số K
       Bước 3: Y raise lên s(t) với A và raise-bluff tỷ lệ β số Q, để X
       cùng lắm bàng quan giữa check và bet t với K
       Bước 4: X bet t cả với một số A: được K của Y call và bắt được
       raise-bluff; Y không chặn được cả hai
       Bước 5: X không được bet hết A (khác spread-limit): nếu chỉ còn K
       khi check, Y bet thật lớn với A và Q
       Bước 6: hàm A(t) = giá trị bet t với A; cực đại → τ; trộn chiến
       lược với A nên A(0) = A(τ) → tìm s₀
       Bước 7: mức raise lý thuyết t₂, nhưng luật buộc raise tối thiểu 2t
                                │
                                ▼
       LỜI GIẢI (pot = 1; số gần đúng):
       X: · check 61,2% số A, Y bet thì X raise all-in
          · bet τ = 0,2521 với 38,8% số A (bị raise thì reraise all-in),
            15,62% số K (bị raise thì fold), 7,81% số Q (bị raise thì
            fold)
          · check K còn lại; gặp cược s thì call/raise với tổng tỷ lệ
            1/(1 + s) trên các tay đã check
       Y: · X check → bet s₀ = 0,5422 với mọi A và 35,16% số Q
          · X check-raise → A reraise all-in, Q fold
          · X bet t → raise lên t₂ với mọi A và β số Q;
            α₀ = s₀/(1 + s₀); β = (α₀ − t)/(1 + t) nếu α₀ > t, ngược lại 0;
            t₂ = α₀/(1 − β) nếu lớn hơn 2t, ngược lại 2t
          · call với đủ K để tổng tỷ lệ call (trên tay thắng Q) là 1/(1 + t)
```

### Phụ lục Chương 15 — Dẫn giải phần 1: trò chơi rút gọn khi X không được bet K (Derivation, trang 177–179)

```text
       Nếu X bet MỌI A: Y bet 100 pot với mọi A và 100/101 số Q; X chỉ
       còn K, phải call 1/101 số K, cho đi 100/101 đơn vị mỗi lần X cầm
       K gặp A → X phải check một phần A (tỷ lệ A_k)
                                │
                                ▼
       Ba ẩn: A_k (tỷ lệ A check), t (mức X bet), s (mức Y bet khi X check)
                                │
                                ▼
       Ẩn t: A gặp K: t(2/(1 + t) − 1) = (t − t²)/(1 + t)
       → cực đại khi t² + 2t − 1 = 0 → t = r = √2 − 1; Y call r số K
                                │
                                ▼
       Ẩn s: X trộn A giữa check và bet r nên hai EV bằng nhau:
       s²/[2(1 + s)] = (r − r²)/[2(1 + r)] = 3/2 − √2 → s ≈ 0,50879
                                │
                                ▼
       Ẩn A_k: Y chọn mức q cực đại EV khi A gặp K bị call:
       (q − q²A_k)/[2(1 + q)] → (q + 1)² = 1/A_k + 1
       X chọn A_k để q tối ưu đúng bằng s → A_k ≈ 0,78342
                                │
                                ▼
       Kết quả: X check 78,3% A, bet r ≈ 41,4% pot với phần còn lại và
       6,3% số Q; Y bet s ≈ 50,8% pot với A và 33,7% số Q; Y call cược r
       với r số K; X call cược s với khoảng 39,9% số K
       Giá trị với Y ≈ 0,02761
```

### Phụ lục Chương 15 — Dẫn giải phần 2: khi X được bet K (Derivation, tiếp theo, trang 179–182)

```text
       X check K: giả sử X luôn fold (vì bàng quan) → EV = −α₀/2
       Nếu Y chỉ call khi X bet t với K, X bet rất nhỏ là chặn được bluff
       → Y phải raise (lên max(2t, t₂)) với A và β(t) số Q
                                │
                                ▼
       X bàng quan với K: (1/2)(−t) + (1/2)β[−(1 + t)] = −α₀/2
       → β = (α₀ − t)/(1 + t)  (khi α₀ > t; ngược lại β = 0)
                                │
                                ▼
       Giá trị bet t với A (raise tối thiểu 2t):
       A(t) ≥ t(1 − 3t + 2α₀)/[2(1 + t)]
       → cực đại: 3t² + 6t − 2α₀ − 1 = 0 → τ = √(4/3 + 2α₀/3) − 1
                                │
                                ▼
       X trộn A nên A(0) = A(τ): (1/2)α₀s₀ = (1/2)τ(1 − τ)/(1 + τ)
       + (1/2)·[(α₀ − τ)/(1 + τ)]·2τ → giải số: s₀ ≈ 0,54224,
       α₀ ≈ 0,35159, τ ≈ 0,25209 (β ≈ 0,0795)
                                │
                                ▼
       Mức raise lý thuyết (X bàng quan khi call bằng K):
       t₂ − t = β(t₂ + 1 + t) → t₂ = α₀/(1 − β)
       · t > α₀: không cần raise-bluff; t rất nhỏ: raise lên gần s₀
       · t₂ = 2t tại t ≈ 0,2010 → với τ ≈ 0,2521 Y raise lên 2τ ≈ 0,504
                                │
                                ▼
       Tỷ lệ K khi check: k = 1 − 1/(1 + s₀)² ≈ 0,57957 (Y bet đúng s₀)
       Tỷ lệ K khi bet: 2τ/(1 + τ + 2τ) ≈ 0,28707 (Y bàng quan raise-bluff)
       Giải hệ → A check 61,213%, A bet 38,787%, K check 84,382%,
       K bet 15,618%; giá trị với Y ≈ 0,02682 (giảm từ 0,02761)
```

## Ba câu hỏi chương này trả lời

1. **Quyền bet trước thay đổi trò chơi AKQ limit thế nào?** X không bao giờ thiệt vì luôn có thể check như ở half-street. Trong AKQ #4, X bet x số A cùng α·x số Q, check-call 1 − 2α + αx số K; Y call 1 − 2α số K khi bị bet, bet mọi A và α số Q khi X check. Giá trị với Y là [x(3α − 1) + 1 − 2α]/6. Khi pot nhỏ (1 < P < 2), X check mọi tay và giá trị không đổi so với half-street; khi pot lớn (P > 2), X bet mọi A, giá trị với Y giảm từ (P − 1)/[6(P + 1)] xuống 1/[6(P + 1)] (ví dụ P = 3: từ 1/12 xuống 1/24).
2. **Vì sao có thể đúng khi bet một tay bài không được tay yếu hơn call và không làm tay mạnh hơn fold?** Trong AKQ #5 có hai mức cược. Check K thì X mất 2/3 đơn vị vì Y bluff Q bằng cược lớn và value bet A; bet 1 đơn vị với K thì Y cầm Q không còn bluff được, chỉ mất 1/2 khi Y có A. Cú **cược chặn trước** này có EV âm nhưng ít âm hơn check. Y đáp lại bằng raise-bluff 1/15 số Q, nhưng điều đó khiến X bet nhỏ cả với A (lời 11/30 so với 1/3 khi check); cân bằng cuối giảm giá trị của Y từ 1/9 xuống 1/10.
3. **Trò chơi AKQ no-limit đầy đủ được giải ra sao và kết quả là gì?** Theo các bước: giải trò chơi phụ khi X không được bet K (X bet r ≈ 0,414 pot với 21,7% số A, Y bet ≈ 0,509 pot khi X check, giá trị với Y ≈ 0,02761), rồi cho X bet mức nhỏ với K; Y phải raise-bluff để giữ X bàng quan; X dùng chung mức nhỏ τ ≈ 0,252 pot cho A, K, Q. Lời giải: X check 61,2% A và 84,4% K, bet τ với 38,8% A, 15,6% K, 7,8% Q; Y bet s₀ ≈ 0,542 pot với A và 35,2% Q khi X check, raise lên 2τ với A và khoảng 7,9% Q khi X bet τ. Giá trị với Y ≈ 0,02682.

## Khái niệm cần biết

- **Full-street (một vòng cược đầy đủ):** cả hai người đều có lượt bet; X hành động trước, được bet hoặc check. Ví dụ: AKQ #4: X cầm A có thể bet ngay thay vì check chờ Y bluff. Quan trọng vì đây là cấu trúc của mọi vòng cược trong poker thật.
- **Check dark (check trong bóng tối):** check trước khi xem bài hoặc trước khi có thông tin; trong half-street là luật bắt buộc với X. Ví dụ: ở AKQ #5, X có thể check dark và vẫn giữ được giá trị half-street 1/9 (với Y). Quan trọng vì nó là "mức sàn" bảo đảm X không thiệt khi được thêm lựa chọn.
- **Lựa chọn chiến lược có giá trị không âm:** thêm một lựa chọn không thể làm người được thêm thiệt, vì họ luôn có thể bỏ qua nó. Ví dụ: giá trị của Y trong AKQ #4 không bao giờ vượt giá trị half-street (P − 1)/[6(P + 1)]. Quan trọng vì nó giải thích vì sao giá trị của Y giảm dần qua AKQ #4, #5 và phụ lục.
- **Kế hoạch trọn vẹn (strategy) và lựa chọn tức thời (strategic option):** trong full-street, chiến lược của X là cả kế hoạch: bet; check rồi call; check rồi fold. Ví dụ: "check-call với K" là một chiến lược khác "check-fold với K", dù bước đầu giống nhau. Quan trọng vì ma trận lợi ích phải lập theo kế hoạch.
- **Check-call, check-fold, check-raise:** check rồi call / fold / raise khi bị bet. Ví dụ: trong lời giải no-limit, X check A rồi raise all-in khi Y bet. Quan trọng vì đây là các kế hoạch trong ma trận.
- **Thay đổi phân phối khi check:** X đem bet một phần tay mạnh, nên tập tay X check yếu hơn, và Y chơi khác sau cú check. Ví dụ: nếu X bet mọi A (x = 1) thì khi check, X chỉ còn K và Q, nên phải call với 1 − α số K thay vì (P − 1)/(P + 1). Quan trọng vì quyết định sớm ảnh hưởng mọi nút sau.
- **Tỷ lệ bluff của X b/x = α (Phương trình 15.1):** số Q X bluff bằng α lần số A X bet. Ví dụ: P = 3 thì α = 1/4; X bet mọi A thì bluff 1/4 số Q. Quan trọng vì nó giữ Y bàng quan khi call bằng K.
- **Tần suất check-call của X với K, c = 1 − 2α + αx (Phương trình 15.2).** Ví dụ: P = 3, x = 1: c = 1 − 1/2 + 1/4 = 3/4 = P/(P + 1). Quan trọng vì nó cho thấy X phải bù cho việc tập check đã bị "rút" bớt A.
- **Spread-limit:** luật cho phép bet trong một khoảng (ở đây 1 hoặc 2 đơn vị). Ví dụ: AKQ #5 với pot 4. Quan trọng vì đây là bước trung gian giữa limit và no-limit, đủ để lộ ra cược chặn trước.
- **Raise-bluff:** raise với tay yếu để người bet fold. Ví dụ: Y cầm Q raise X đang bet 1, mong X cầm K fold; thắng 5 đơn vị (pot 4 + cược 1 của X). Quan trọng vì đây là cách Y trừng phạt cược chặn trước.
- **Cược chặn trước (preemptive bet):** bet một tay bài ở giữa, không mong được tay yếu hơn call hay làm tay mạnh hơn fold, mà để tước khả năng bluff (hoặc bet lớn) của đối thủ. Ví dụ: X bet 1 với K trong AKQ #5, mất 1/2 thay vì 2/3. Quan trọng vì nó phá vỡ quan niệm "bet trên river chỉ là value bet hoặc bluff".
- **Nemesis và cải thiện đơn phương:** một cặp chiến lược tối ưu khi không ai tăng được EV bằng cách tự đổi chiến lược. Ví dụ: lời giải ngây thơ của AKQ #5 hỏng vì X cầm K đổi sang bet 1 thì lời 1/6. Quan trọng vì đây là phép thử phải làm với mọi lời giải.
- **Hằng số r = √2 − 1 ≈ 0,414 (Phương trình 14.1):** mức cược tối ưu khi đối thủ có nửa nuts, nửa tay bắt bluff. Ví dụ: X bet r pot với A trong trò chơi rút gọn của phụ lục. Quan trọng vì nó xuất hiện lại, lần này cho X.
- **τ (tau), s₀, α₀, β:** các ký hiệu của lời giải no-limit: τ ≈ 0,2521 là mức X bet; s₀ ≈ 0,5422 là mức Y bet khi X check; α₀ = s₀/(1 + s₀) ≈ 0,3516 là tỷ lệ Q Y bluff; β = (α₀ − t)/(1 + t) là tỷ lệ Q Y raise-bluff khi X bet t. Ví dụ: β(τ) ≈ 0,0795.
- **A_k (tỷ lệ A X check):** biến X dùng để "điều khiển" mức cược tối ưu của Y. Ví dụ: A_k ≈ 0,783 trong trò chơi rút gọn làm Y tối ưu khi bet đúng s ≈ 0,509. Quan trọng vì giữ lại A khi check là "mối đe doạ đáng tin" chống Y bluff lớn.
- **Raise tối thiểu (minimum raise):** luật buộc raise lên ít nhất gấp đôi cược. Ví dụ: X bet τ ≈ 0,252 thì Y phải raise lên ít nhất ≈ 0,504, dù mức lý thuyết Y muốn chỉ ≈ 0,382. Quan trọng vì nó giúp X: X cầm K có thể fold mọi lần bị raise.

## Nội dung chi tiết

### 1. Phần mở đầu: từ half-street sang full-street (trang 163)

Phần đầu của Phần III bàn các trò chơi half-street: X hành động trước nhưng bị buộc check "trong bóng tối"; sau đó Y có thể check và đi tới showdown, hoặc value bet và bluff thích hợp. Chương 15 bắt đầu nghiên cứu các trò chơi **full-street**: X vẫn hành động trước nhưng có thể bet hoặc check. Nếu X bet, Y luôn có thể call, và đôi khi có thể raise hoặc fold. Nếu X check, Y có thể check hoặc bet.

**Ý thứ nhất: một số khái niệm mang sang được, một số thì không.** Tỷ lệ bet và bluff đúng với X như đã đúng với Y. Nhưng ngoài ra, việc X có thể bet **làm thay đổi phân phối tay bài X có khi X check**, nên cách Y chơi sau cú check của X thường thay đổi. Đây là đặc điểm của hầu như mọi trò chơi đồ chơi mở rộng: cách chơi ở các quyết định trước ảnh hưởng mạnh tới các quyết định sau.

**Ý thứ hai: X không thể mất giá trị khi chuyển từ half-street sang full-street**, nếu phần còn lại của trò chơi giữ nguyên. Nếu chiến lược của X cho kỳ vọng thấp hơn ở full-street, X chỉ việc dùng lại chiến lược trước đây bị ép buộc là check trong bóng tối. Đây là hệ quả tự nhiên của ý tưởng rằng các lựa chọn chiến lược có giá trị không âm: quyền bet ngay của X tệ nhất cũng có giá trị bằng 0, vì X luôn có thể từ chối quyền đó và nhận equity của half-street.

**Ý thứ ba, quan trọng nhất: khái niệm chiến lược và cách biểu diễn nó.** Trong các trò chơi half-street, nhất là trò chơi [0,1], mỗi người chỉ có một hành động: Y bet hoặc check; nếu Y bet thì X call hoặc fold. Vì chiến lược của mỗi người về cơ bản chỉ là một hành động, có quan hệ trực tiếp giữa *chiến lược* "fold" và *lựa chọn chiến lược* "fold". Chiến lược của mỗi người gồm các miền: đôi khi là một khoảng tay bài dùng cho một lựa chọn (như trong trò chơi [0,1]), đôi khi là tần suất trộn cho các tay bài rời rạc (như trong trò chơi AKQ); trong cả hai trường hợp, người chơi chọn một phân phối tay bài cho mỗi lựa chọn, và tổng các phân phối đó là chiến lược.

Trong full-street, tình hình hơi khác. Ở half-street, cú check ban đầu của X là do luật. Giờ X có thể nói là có hai quyết định: check hay bet lúc đầu, và call hay fold khi bị bet. Theo tác giả, đó không thực sự là hai quyết định tách rời. Khi X chọn chiến lược, ta tạo ra một tập lựa chọn phức tạp hơn phản ánh các lựa chọn của X cho cả trò chơi: thay vì hai lựa chọn ở bước đầu và hai ở bước sau, X có ba lựa chọn — **bet, check-call, check-fold**. Khi đặc tả các trò chơi full-street, sách lập ma trận lợi ích theo các lựa chọn chiến lược mở rộng này chứ không chỉ theo các lựa chọn có ngay trước mắt.

### 2. Ví dụ 15.1 — Trò chơi AKQ số 4 (Example 15.1 AKQ Game #4, trang 164–169)

#### Luật

- Một full-street.
- Pot P đơn vị, với P > 1 (cùng lý do như ở trò chơi AKQ half-street: khi P < 1 bluff bằng Q luôn lỗ vì một nửa số lần đối thủ cầm A).
- Cược limit 1 đơn vị.
- Không được raise.
- Bộ bài A, K, Q; mỗi người một lá; mỗi cặp lá xác suất 1/6.

#### Ma trận lợi ích đầy đủ

Ma trận ghi giá trị ngoài showdown theo phía Y. Hàng là lá của X và kế hoạch của X (Bet; Chk/Call = check rồi call; Chk/Fold = check rồi fold). Cột là lá của Y và phản ứng của Y: khi X bet thì Y call hoặc fold; khi X check thì Y bet hoặc check. "—" là cặp lá không thể xảy ra hoặc ô không áp dụng (ví dụ X bet thì cột "X check" không áp dụng).

| X \ Y | | A: X bet → call | A: X bet → fold | A: X check → bet | A: X check → chk | K: X bet → call | K: X bet → fold | K: X check → bet | K: X check → chk | Q: X bet → call | Q: X bet → fold | Q: X check → bet | Q: X check → chk |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| A | Bet | — | — | — | — | −1 | 0 | — | — | −1 | 0 | — | — |
| A | Chk/Call | — | — | — | — | — | — | −1 | 0 | — | — | −1 | 0 |
| A | Chk/Fold | — | — | — | — | — | — | +P | 0 | — | — | +P | 0 |
| K | Bet | +1 | −P | — | — | — | — | — | — | −1 | 0 | — | — |
| K | Chk/Call | — | — | +1 | 0 | — | — | — | — | — | — | −1 | 0 |
| K | Chk/Fold | — | — | 0 | 0 | — | — | — | — | — | — | +P | 0 |
| Q | Bet | +1 | −P | — | — | +1 | −P | — | — | — | — | — | — |
| Q | Chk/Call | — | — | +1 | 0 | — | — | +1 | 0 | — | — | — | — |
| Q | Chk/Fold | — | — | 0 | 0 | — | — | 0 | 0 | — | — | — | — |

Đọc vài ô: X cầm K bet, Y cầm A fold: Y mất pot lẽ ra thắng, −P. X cầm Q bet, Y cầm K fold: −P (X bluff thành công). X cầm A check-fold, Y cầm K bet: +P (X bỏ pot lẽ ra thắng).

#### Loại chiến lược bị trội — lần một

Với X: check-fold A bị trội bởi check-call A; check-call Q bị trội bởi check-fold Q. Với Y: call bằng Q và fold A trước một cược đều bị trội; ngoài ra check A sau khi X check bị trội bởi bet A. Loại các chiến lược này:

| X \ Y | | A: call | A: bet | K: call | K: fold | K: bet | K: chk | Q: fold | Q: bet | Q: chk |
|---|---|---|---|---|---|---|---|---|---|---|
| A | Bet | — | — | −1 | 0 | — | — | 0 | — | — |
| A | Chk/Call | — | — | — | — | −1 | 0 | — | −1 | 0 |
| K | Bet | +1 | — | — | — | — | — | 0 | — | — |
| K | Chk/Call | — | +1 | — | — | — | — | — | −1 | 0 |
| K | Chk/Fold | — | 0 | — | — | — | — | — | +P | 0 |
| Q | Bet | +1 | — | +1 | −P | — | — | — | — | — |
| Q | Chk/Fold | — | 0 | — | — | 0 | 0 | — | — | — |

(Ở đây "A: call" là Y cầm A call khi X bet; "A: bet" là Y cầm A bet khi X check; tương tự cho K, Q.)

#### Loại chiến lược bị trội — lần hai

Trong trò chơi đơn giản hơn này, bet K bị trội với cả hai người: X bet K thì A của Y call (mất 1) và Q của Y fold (được 0), trong khi check-call hay check-fold K không tệ hơn; Y bet K sau khi X check thì A của X call (mất 1), Q của X fold (0), trong khi check được 0. Ma trận còn lại (cột của Y là kế hoạch "khi bị bet / khi X check"):

| X \ Y | | A: Call/Bet | K: Call/Chk | K: Fold/Chk | Q: Fold/Bet | Q: Fold/Chk |
|---|---|---|---|---|---|---|
| A | Bet | — | −1 | 0 | 0 | 0 |
| A | Chk/Call | — | 0 | 0 | −1 | 0 |
| K | Chk/Call | +1 | — | — | −1 | 0 |
| K | Chk/Fold | 0 | — | — | +P | 0 |
| Q | Bet | +1 | +1 | −P | — | — |
| Q | Chk/Fold | 0 | 0 | 0 | — | — |

(Sách in ô "K Chk/Fold – Q Fold/Bet" là −P; đúng là +P, xem Lưu ý.)

#### Các biến chiến lược

**X** check mọi K, call và fold với K theo tỷ lệ làm Y bàng quan khi bluff Q. Ngoài ra X phải chọn chiến lược cho A và Q. Cầm A, X được lợi khi check-call nếu Y có Q, vì *dụ* được một cú bluff; nhưng X được lợi khi bet nếu Y có K và Y sẽ call. Cầm Q, X được lợi khi bluff làm K của Y fold, và thua khi Y có A hoặc có K sẽ call.

**Y** đơn giản hơn: chỉ phải chọn chiến lược cho K và Q. Cầm K, Y call đủ thường xuyên để X bàng quan khi bluff Q. Cầm Q, Y bluff đủ thường xuyên để X bàng quan khi call với K.

Chiến lược của X gồm ba giá trị: **x** = tần suất bet với A; **c** = tần suất call với K (X check mọi K nên đây là tần suất check-call); **b** = tần suất bluff với Q. Chiến lược của Y gồm hai giá trị: **c_y** = tần suất call với K; **b_y** = tần suất bluff với Q.

#### Khi X bet

X chỉ bet khi cầm A hoặc Q. Y phải làm X bàng quan khi bluff bằng cách call với một tỷ lệ K nhất định, và điều này đúng dù X bet mọi A hay không. Như trong các trò chơi half-street, khi một người bet một tập "hai cực" gồm A và Q, đối thủ phải fold đúng α số tay bài thắng được bluff. Theo cùng lập luận như trò chơi AKQ #2 ([C13-tro-choi-akq.md](C13-tro-choi-akq.md)), khi X bet, **Y phải call với (P − 1)/(P + 1) số K** để X bàng quan khi bluff Q. (Người tổng hợp viết rõ: khi X cầm Q, Y cầm A hoặc K mỗi loại một nửa; Y call mọi A; tổng tỷ lệ call phải là 1 − α = P/(P + 1), nên tỷ lệ K là 2[P/(P + 1) − 1/2] = (P − 1)/(P + 1) = 1 − 2α.) Điều này bảo đảm Y fold α số tay thắng được bluff.

X thì phải chọn tỷ lệ Q bluff so với A value bet sao cho Y bàng quan khi call với K. Xét chênh lệch giá trị ngoài showdown giữa hai lựa chọn của Y. Khi Y call cược của X bằng K, X có thể có hai tay. X có A: X được 1 cược khi Y call, so với 0 nếu Y fold. X có Q: Y được không chỉ cược đã call mà cả pot, vì nếu fold thì Y để X cướp pot. Vì Y được P + 1 cược khi call một Q và mất 1 cược khi call một A, X phải bet một Q cho mỗi P + 1 A:

```text
b/x = 1/(P + 1) = α                                                  (15.1)
```

Lại thấy quan hệ bluff/bet cơ bản α. Nhờ vậy có thể bỏ qua biến b trong phần còn lại, vì b tính ngay được từ x.

#### Khi X check

Tình huống giống trò chơi AKQ #2, chỉ khác là X không còn đủ mọi A, vì có thể đã bet x số A. Y bet mọi A và α số Q như mọi khi. X có một phân phối tay bài còn lại; để Y bàng quan khi bluff, X phải fold α số tay bài thắng được bluff còn lại trong phân phối.

Nếu X check mọi A (x = 0), X có A và K bằng nhau, fold α số tay còn lại, chọn K để fold trước; ở AKQ #2 tỷ lệ K X call là (P − 1)/(P + 1) (sách viết "fold", nhưng (P − 1)/(P + 1) là tỷ lệ call — nhận xét của người tổng hợp). Ở đây tổng số tay của X đã giảm đi x số A, nên X phải call với nhiều K hơn. Tổng số tay X có lúc này:

```text
Tổng số tay = (mọi A)(tỷ lệ A đã check) + (mọi K)
            = (1/2)(1 − x) + (1/2)
            = 1/2 − x/2 + 1/2
Số tay fold = α × (Tổng số tay)
(1/2)(1 − c) = α(1/2 − x/2 + 1/2)        (X chỉ fold K; K chiếm 1/2)
1 − c = α(2 − x)
c = 1 − 2α + αx                                                      (15.2)
```

**Kiểm tra tại x = 0:** c = 1 − 2α = 1 − 2·[1/(P + 1)] = (P + 1 − 2)/(P + 1) = (P − 1)/(P + 1), đúng như dự kiến. **Tại x = 1:** nếu X bet mọi A, khi check X chỉ còn K và phải fold α số K để Y bàng quan khi bluff Q; công thức cho c = 1 − α, khớp.

#### Tóm tắt lời giải đến đây

- X bet x số A và αx số Q.
- X check-fold số Q còn lại và check-call số A còn lại.
- X check-call với (1 − 2α + αx) số K và check-fold phần còn lại.
- Khi X bet, Y call với 1 − 2α số K và mọi A; Y fold số K còn lại và mọi Q.
- Khi X check, Y bet mọi A và α số Q, check mọi tay khác.

Đây là hiện tượng thường gặp khi giải trò chơi: có được lời giải tối ưu trừ một biến nào đó; bên kiểm soát biến đó chọn giá trị làm kỳ vọng của mình lớn nhất.

#### Giá trị trò chơi theo x: sáu trường hợp

Để tìm x, cần tìm kỳ vọng của trò chơi (theo phía Y).

- **Trường hợp 1 — X: A, Y: K.** X bet x số lần, Y call 1 − 2α số lần: giá trị −x(1 − 2α). Khi X check, Y check: giá trị 0.
- **Trường hợp 2 — X: A, Y: Q.** X bet thì Y fold: 0. X check và dụ bluff 1 − x số lần, Y bluff α số lần, X call: giá trị −α(1 − x).
- **Trường hợp 3 — X: K, Y: A.** X luôn check; Y bet; X call 1 − 2α + αx số lần: giá trị 1 − 2α + αx.
- **Trường hợp 4 — X: K, Y: Q.** X luôn check; Y bluff α số lần; X call thì Y mất 1, X fold thì Y lấy cả pot. Tổng giá trị Y thu từ mọi cú bluff phải bằng 0, vì chiến lược tối ưu của X làm Y bàng quan giữa bluff và check, mà check có giá trị 0. Vậy trường hợp 4 cộng trường hợp 2 bằng 0, nên trường hợp 4 có giá trị α(1 − x). (Người tổng hợp kiểm tra trực tiếp: α[(1 − c)P − c] với 1 − c = α(2 − x) và αP = 1 − α cho α[(2 − x)(1 − α) − 1 + 2α − αx] = α(1 − x).)
- **Trường hợp 5 — X: Q, Y: A.** X bluff αx số lần, Y call: giá trị αx.
- **Trường hợp 6 — X: Q, Y: K.** Tổng giá trị với người bluff (X) phải bằng 0, nên trường hợp 6 là số đối của trường hợp 5: −αx. (Kiểm tra: αx[(1 − 2α)(+1) + 2α(−P)] = αx[1 − 2α − 2(1 − α)] = −αx.)

| Cặp lá (X, Y) | Giá trị với người thứ hai (Y) |
|---|---|
| (A, K) | −x(1 − 2α) |
| (A, Q) | −α(1 − x) |
| (K, A) | 1 − 2α + αx |
| (K, Q) | α(1 − x) |
| (Q, A) | αx |
| (Q, K) | −αx |
| Tổng (đã nhân 1/6) | [x(−1 + 3α) + 1 − 2α]/6 |

(Cộng: hệ số của x là −1 + 2α + α + α − α + α − α = −1 + 3α; hằng số là −α + 1 − 2α + α = 1 − 2α.)

#### Hình 15.1 — equity của AKQ #4 theo x (trang 168)

Đồ thị có trục hoành x từ 0 tới 1, trục tung f(P, x) từ 0 tới 0,09, năm đường thẳng ứng với P = 1; 1,5; 2; 2,5; 3. Người tổng hợp tính hai đầu mút:

| P | α | f tại x = 0 | f tại x = 1 | Chiều |
|---|---|---|---|---|
| 1 | 1/2 | 0 | 1/12 ≈ 0,083 | tăng |
| 1,5 | 0,4 | 1/30 ≈ 0,033 | 1/15 ≈ 0,067 | tăng |
| 2 | 1/3 | 1/18 ≈ 0,056 | 1/18 ≈ 0,056 | nằm ngang |
| 2,5 | 2/7 | 1/14 ≈ 0,071 | 1/21 ≈ 0,048 | giảm |
| 3 | 1/4 | 1/12 ≈ 0,083 | 1/24 ≈ 0,042 | giảm |

Mọi đường cắt nhau tại một điểm: tại x = 2/3, f = [2α − 2/3 + 1 − 2α]/6 = 1/18 với mọi P (người tổng hợp tính; đồ thị cho thấy điểm cắt ở khoảng x ≈ 0,67, f ≈ 0,055).

Biểu thức giá trị (với Y) đạt cực tiểu tại x = 1 khi P > 2 và tại x = 0 khi 1 < P < 2 — X chọn x để giá trị của Y nhỏ nhất. Lý do: hệ số của x là 3α − 1, âm khi α < 1/3 (P > 2) và dương khi α > 1/3 (P < 2).

#### Lời giải AKQ #4

**Nếu P < 2:**
- X check mọi tay; call với A và (P − 1)/(P + 1) số K.
- Y bet mọi A và 1/(P + 1) số Q.

**Nếu P > 2:**
- X bet mọi A và 1/(P + 1) số Q; call với P/(P + 1) số K.
- Y: nếu X check, bet mọi A và 1/(P + 1) số Q; nếu X bet, call với A và (P − 1)/(P + 1) số K.

Người tổng hợp so giá trị với Y của half-street (AKQ #2) và full-street (AKQ #4):

| P | Half-street: (P − 1)/[6(P + 1)] | Full-street |
|---|---|---|
| 1,5 | 0,0333 | 0,0333 (X check hết, không đổi) |
| 2 | 0,0556 | 0,0556 |
| 3 | 0,0833 | 1/24 ≈ 0,0417 |
| 5 | 0,1111 | 1/36 ≈ 0,0278 |
| 10 | 0,1364 | 1/66 ≈ 0,0152 |

Khi P > 2, giá trị full-street là α/6 = 1/[6(P + 1)], tiến về 0 khi pot lớn, trái với half-street (tiến về 1/6): quyền bet trước của X triệt tiêu gần hết lợi thế vị trí của Y khi pot lớn.

Khi phát biểu trò chơi, sách loại trừ raise. Tuy nhiên có thể kiểm tra từ lời giải trên rằng nếu cho phép raise, không ai cải thiện được bằng cách raise cược của đối thủ (trừ trường hợp cầm A mà đối thủ sẽ fold Q — raise hay call như nhau). Vậy đây cũng là lời giải của trò chơi đầy đủ hơn có raise.

Trò chơi đơn giản này giới thiệu các trò chơi full-street. Khác biệt cốt lõi với half-street nằm ở số lựa chọn chiến lược. Vẫn thấy lại cùng tỷ lệ bet/bluff (α) và cùng tỷ lệ fold (lại là α). Độ phức tạp thêm đến từ quyết định mới của X: dụ bluff hay bet thẳng với A.

#### Chuyển tiếp sang no-limit

Trò chơi AKQ #3 (Ví dụ 14.2; sách ghi nhầm 14.1) đã được giải theo cách tương tự: giải chiến lược theo mức cược s của Y rồi cực đại equity của Y theo s ([C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md)). Có vẻ bước từ half-street no-limit sang full-street no-limit chỉ phức tạp thêm chút ít; tác giả làm việc đó ở cuối chương (phụ lục). Nhưng trước đó, xét trò chơi sau.

### 3. Ví dụ 15.2 — Trò chơi AKQ số 5 (Example 15.2 AKQ Game #5, trang 169–174)

#### Luật

- Một full-street.
- Pot 4 đơn vị.
- Một dạng spread-limit đặc biệt: mỗi bên có thể check (nếu chưa có hành động), hoặc bet hay raise 1 hoặc 2 đơn vị đến lượt mình.

AKQ #5 giống AKQ #4 với pot = 2 (tính theo cược), chỉ thêm cho cả hai bên một lựa chọn: bet 1/4 pot thay vì 1/2 pot. Khi giải AKQ #4, tại P = 2, X bàng quan giữa check và bet A; do đó giá trị trò chơi bằng giá trị half-street, nơi X bị buộc check dark — vì X có thể check dark trong trò chơi này mà không mất giá trị.

#### Lời giải "ngây thơ": cả hai chỉ dùng mức 2

Ở Ví dụ 15.1, giá trị với Y là f(1, P) = [x(−1 + 3α) + 1 − 2α]/6. Ở đây x = 0 (X có thể check dark) và α = 1/(2 + 1) = 1/3:

```text
f(1, 2) = [(0)(−1 + 3α) + 1 − 2(1/3)]/6 = (1 − 2/3)/6 = 1/18
```

Kết quả này chuẩn hoá theo cược bằng 1. Để ứng với cược 2 (pot 4), nhân đôi:

```text
f(s = 2, P = 4) = 1/9
```

Đây là equity nếu cả hai chơi như thể chỉ được bet 2 đơn vị. Kiểm tra xem có ai lợi khi bet 1 đơn vị không.

**X bet 1 với A** và bluff Q tương ứng. Y đáp lại bằng cách làm X bàng quan khi bluff: với cược 1 vào pot 4, α = 1/5, Y call 4/5 tổng số tay, tức mọi A cộng 3/5 số K. Khi đó X thắng 1 đơn vị trong (1/2)(3/5) = 3/10 số lần (Y có K và call), tổng 3/10. Nếu X check, Y bluff 1/3 số Q (Y có Q 1/2 số lần) và A của X được 2 đơn vị: (1/2)(1/3)(2) = 1/3. Vì 1/3 > 3/10, X tự mất equity khi bet 1 thay vì 2 — không tối ưu.

**Y bet 1 khi X check dark:**

```text
f(1, P) = [x(−1 + 3α) + 1 − 2α]/6;  với P = 4: α = 1/5
f(1, 4) = (1 − 2/5)/6 = 1/10
```

1/10 < 1/9, nên Y không lợi khi bet 1 với A và bluff Q tương ứng. Y cũng có thể raise; nhưng X chỉ bet với A và Q, đều không phải tay Y raise có lời, nên Y chỉ raise với A (vì call bằng A bị trội) và fold Q. Lập luận tương tự với X. Có vẻ trò chơi loại này chỉ là mở rộng nhẹ của các nguyên tắc đã học.

**Hay không phải vậy?**

Chiến lược theo phân tích trên:

- **X:** check mọi tay (đồng tối ưu với các chiến lược khác). Call cược 2 với mọi A và 1/3 số K; call cược 1 với 3/5 số K.
- **Y:** nếu X bet, call cược 2 với A và 1/3 số K, call cược 1 với A và 3/5 số K. Nếu X check, bet 2 với mọi A và 1/3 số Q.

#### Kiểm tra lại: X cầm K

Nguyên tắc quan trọng của chiến lược tối ưu: **không người nào cải thiện được kỳ vọng bằng cách đơn phương đổi chiến lược**. Nếu cải thiện được kỳ vọng của bất kỳ ai với bất kỳ tay nào bằng cách chơi khác, các chiến lược chưa tối ưu.

Hiện tại X mất 2/3 đơn vị mỗi khi cầm K:

- Nửa số lần Y có Q và bluff 1/3 số lần. X call 1/3 số lần, được 2 đơn vị; 2/3 số lần còn lại X mất cả pot 4. Khi Y có Q, X mất (1/3)[(1/3)(2) − (2/3)(4)] = (1/3)(−2) = −2/3.
- Nửa còn lại Y có A, luôn bet 2; X call 1/3 số lần và mất 2: −2/3.
- Trung bình: −2/3.

Nếu X call với K thường hơn, ví dụ 1/2 số lần, X được thêm khi Y bluff Q nhưng mất thêm khi trả tiền A; vì tỷ lệ value bet so với bluff của Y là 3 so với 1, tổng mất với K không đổi.

**Nhưng nếu bet K thì sao?** Trong các trò chơi trước, bet K bị trội sau khi loại lớp chiến lược bị trội đầu tiên: bet K chắc chắn mất một cược trước A của đối thủ mà không được gì trước Q. Nhưng xét bet **1 đơn vị** với K. Chiến lược của Y bảo Y call với A và 3/5 số K (Y không thể có K khi X có K). Khi đó tổng mất của X với K chỉ còn: mất 1 đơn vị nửa số lần (khi bị A call), tổng **1/2**. Mức này nhỏ hơn 2/3 khi check mọi K. Vậy các chiến lược trên không tối ưu — X tự cải thiện equity bằng cách bet 1 đơn vị với K thay vì check.

#### Y đáp lại bằng raise và raise-bluff

Trước đây sách loại raise-bluff vì không có lúc nào một người bet K. Giờ có, nên Y phải xét raise-bluff như một lựa chọn không bị trội. Khi X bet và Y có A, raise rõ ràng trội hơn fold. Nhưng nếu Y chỉ raise với A, Y không được thêm gì vì X chỉ việc fold K khi bị raise. Vậy Y phải bảo vệ các cú raise lấy giá trị bằng một tỷ lệ bluff tương ứng.

Tỷ lệ quen thuộc s/(1 + s) không còn áp dụng, vì pot giờ lớn hơn (X đã làm pot lớn hơn bằng cú bet, và Y phải theo cược của X trước khi raise). Y cũng có hai mức bluff: raise 2 đơn vị (bỏ vào tổng 3) hoặc raise 1 đơn vị (bỏ vào tổng 2). Thoạt nhìn có thể nghĩ tỷ lệ phải làm X bàng quan khi call bằng K sau khi bet 1. Nhưng bluff thường như vậy tốn kém hơn cho Y. Thay vào đó, **Y bluff vừa đủ để X bàng quan giữa bet 1 đơn vị với K rồi fold khi bị raise, và check K**.

X được 2/3 − 1/2 = 1/6 đơn vị khi bet 1 với K thay vì check. Y phải bluff đủ để xoá chênh lệch này. Gọi q là tần suất raise-bluff của Y. Mỗi lần bluff thành công trước K, Y được 5 đơn vị (pot 4 cộng cược 1 của X):

```text
(pot) × p(Y có Q) × (tần suất bluff) = 1/6
(5)(1/2)q = 1/6
q = 1/15
```

Y raise-bluff 1/15 số Q. Điều này làm X bàng quan giữa bet 1 và check K. X vẫn nên fold mọi K khi bị raise, vì 15/16 số lần Y có A: Y raise với mọi A (1/2) và (1/2)(1/15) = 1/30 với Q, nên P(A | raise) = (1/2)/(1/2 + 1/30) = 15/16. Với Y, raise 1 hay 2 đơn vị không quan trọng khi X cầm K, vì K sẽ fold; nhưng nếu X cầm A, Y rõ ràng thích đã raise mức nhỏ hơn bằng Q.

#### X có lựa chọn mới: bet 1 với A

X bàng quan giữa check và bet K, nhưng kỳ vọng của các hành động với A đã đổi. Trước đây X được 1/3 đơn vị với A nhờ check và bắt bluff của Y (Y bluff 1/3 số Q, 2 đơn vị, và có Q nửa số lần). Giờ X có lựa chọn mới: bet 1 với A và một tỷ lệ Q thích hợp. Cách này lấy được giá trị khi Y call bằng K, và bắt được một số raise-bluff.

```text
<X, bet 1>  = p(Y call)(cược) + p(Y raise-bluff)(mức raise)
            = (3/5)(1/2)(1) + (1/15)(1/2)(2)
            = 3/10 + 1/15 = 11/30
<X, check> = p(Y bluff)(mức cược) = (1/2)(1/3)(2) = 1/3 = 10/30
```

(Khi Y raise-bluff lên tổng 2 và X raise lại, Y fold: X được 2 đơn vị Y đã bỏ vào.) X giờ được thêm 1/30 đơn vị khi bet 1 với A.

#### Nhìn lại quá trình

Ban đầu, ý định là giải như các trò chơi trước: K không bao giờ bet, phần còn lại chỉ là cực đại hoá có tính tỷ lệ bet/bluff. Kết quả là cả hai bỏ qua mức cược nhỏ và bet A, Q theo tỷ lệ như AKQ #4 với pot 2. Rồi vấn đề xuất hiện khi rà lại: X tăng được equity bằng cách bet mức nhỏ với K, một lựa chọn trước đây bị trội (khi chỉ có một mức cược). Sau đó phải tìm cú raise lấy giá trị cho Y để không bị khai thác; tìm được raise và bluff tương ứng khiến X bàng quan khi chơi như vậy với K. Nhưng rồi một lựa chọn mới có lời cho X: bet mức nhỏ với A và một số Q, lấy được gần hết equity lẽ ra có khi check (nhờ K của Y call) và thêm equity nhờ bắt raise-bluff.

Trong mọi chiến lược này, X chỉ bet Q vừa đủ để bảo vệ A (để A được K call), và để X hoà vốn với các cú bluff bằng Q.

X có equity như nhau khi check hay bet K (vì Y raise-bluff đủ để bảo đảm điều đó). Mỗi lần bet A, X được thêm 1/30, nên X muốn bet mọi A. Cần tìm tỷ lệ K so với A buộc Y tiếp tục raise-bluff: quá nhiều K thì Y lời khi raise-bluff nhiều hơn; quá ít K thì Y lời khi raise-bluff ít hơn. Raise-bluff được 5 đơn vị khi thành công (X có K) và mất 2 khi thất bại (X có A). Để Y bàng quan, X phải bet A và K theo tỷ lệ **5 so với 2**. Vì X bet 100% A, X phải bet **40% số K**.

#### Lời giải AKQ #5

**X:**
- Bet 1 đơn vị với mọi A; bet 1 với 40% số K; bet 1 với 20% số Q.
- Nếu Y raise 1 đơn vị: raise lại với A, fold K. Nếu Y raise 2 đơn vị: raise lại với A, fold K.
- Check với số K và Q còn lại.
- Call cược 1 đơn vị với 4/5 số K và cược 2 đơn vị với 2/3 số K.

**Y:**
- Nếu X bet 2: raise 2 với A và call với 1/3 số K; fold Q.
- Nếu X bet 1: raise 1 với A và 1/15 số Q; call với 3/5 số K.
- Nếu X check: bet 2 với A và 1/3 số Q; check K.

Người tổng hợp giải thích các con số: 20% số Q là α = 1/5 (cược 1 vào pot 4) nhân với 100% số A. Y cầm K gặp cược 1: X có A (bet 100%) hoặc Q (bet 20%), nên EV call = (5/6)(−1) + (1/6)(+5) = 0, Y bàng quan. X cầm K sau khi check chỉ còn K bắt bluff (mọi A đã bet), nên trước cược 2 vào pot 4 (α = 1/3) phải call 1 − 1/3 = 2/3 số K; trước cược 1 (α = 1/5), call 4/5. Y cầm Q raise-bluff gặp tập bet của X gồm A (100%) và K (40%): EV = (5/7)(−2) + (2/7)(+5) = 0.

#### Bảng giá trị của lời giải (theo phía X, đã sửa)

Ký hiệu hành động: b1 = bet 1; r1, r2 = raise thêm 1 hoặc 2 đơn vị; r = raise lại; f = fold; c, call = call; chk = check; b2 = bet 2.

| X | Y | Hành động | Giá trị (X) | Xác suất | Trọng số EV |
|---|---|---|---|---|---|
| A | K | b1 – call | +1 | 3/30 | 3/30 |
| A | K | b1 – fold | 0 | 2/30 | 0 |
| A | Q | b1 – r1 – r – f | +2 | 1/90 | 1/45 |
| A | Q | b1 – fold | 0 | 14/90 | 0 |
| K | A | b1 – r1 – f | −1 | 1/15 | −1/15 |
| K | A | chk – b2 – c | −2 | 1/15 | −2/15 |
| K | A | chk – b2 – f | 0 | 1/30 | 0 |
| K | Q | b1 – r1 – f | −5 | 1/225 | −1/45 |
| K | Q | b1 – f | 0 | 14/225 | 0 |
| K | Q | chk – b2 – c | +2 | 1/45 | 2/45 |
| K | Q | chk – b2 – f | −4 (sách in 4) | 1/90 | −2/45 |
| K | Q | chk – chk | 0 | 1/15 | 0 |
| Q | A | b1 – r – f (sách ghi r2) | −1 | 1/30 | −1/30 |
| Q | A | chk – b2 – f | 0 | 2/15 | 0 |
| Q | K | b1 – call | −1 (sách in 1) | 1/50 | −1/50 |
| Q | K | b1 – fold | +4 (sách in 1) | 1/75 | +4/75 (sách in +1/75) |
| Q | K | chk – chk | 0 | 2/15 | 0 |
| Tổng | | | | 1 | **−1/10** |

Ví dụ cách tính xác suất: (K, Q, b1 – r1 – f) = (1/6) × (X bet K 0,4) × (Y raise-bluff 1/15) = 0,4/90 = 1/225; (Q, K, b1 – fold) = (1/6)(0,2)(2/5) = 1/75.

Giá trị của chiến lược ngây thơ (không bet K) là −1/9 với X (sách in "1/6", xem Lưu ý); giá trị của chiến lược mới là −1/10, chênh lệch 1/90 có lợi cho X.

Đây là một ví dụ rõ ràng về **che giấu thông tin**: nếu X biết chiến lược của đối thủ cố định, X sẽ thích bet 2 đơn vị với A hơn 1 đơn vị. Nhưng với K, X thích bet mức nhỏ. Vì X phải chọn một mức cược duy nhất nếu không muốn bị khai thác, X chọn mức nhỏ, vì (trong trường hợp này) cược chặn trước có giá trị hơn việc bet lớn với A.

### 4. Khái niệm then chốt (Key Concepts, trang 174–175)

- **Đừng dừng lại trước khi tới lời giải.** Ở đây tác giả đi theo quy trình quen thuộc, dùng kết quả của các trò chơi trước, để giải trò chơi mở rộng. Có lúc tưởng đã tìm được lời giải hợp lý. Chỉ khi đi sâu hơn và kiểm tra lời giải bằng cách so equity của từng lựa chọn, mới tìm ra một ý tưởng hoàn toàn mới.
- **Chiến lược chỉ tối ưu khi cả hai bên đều không cải thiện được!** Khi lần đầu phát hiện vấn đề trên (trong lúc cố giải trường hợp no-limit đầy đủ), tác giả tin chắc mình đã tính sai; dù sao, bet một tay bài không có cơ hội được tay yếu hơn call và không có cơ hội làm tay mạnh hơn fold có vẻ ngớ ngẩn.
- **Cược chặn trước.** Cách chơi K này khác hẳn những gì thấy trong nhiều hoàn cảnh khác: các cú bet trên river "được cho là" value bet (kỳ vọng dương khi bị call) hoặc bluff (đôi khi làm tay tốt hơn fold). Cú bet này không phải cả hai. Sách gọi nó là **cược chặn trước** (preemptive bet). Về cơ bản, X bet để chặn trước khả năng bluff bằng Q một cách hiệu quả như Y muốn. Y có thể đáp lại bằng raise-bluff, nhưng khi đó gặp khó vì X lấy được nhiều giá trị hơn với A. Kiểu chơi này tồn tại khi có nhiều mức cược và người đi trước có thể bet mức nhỏ hơn mức người đi sau muốn bet.
- Bet chặn trước là ví dụ hoàn hảo về một nước đi có kỳ vọng âm, nhưng ít âm hơn lựa chọn check. Điều quan trọng là giá trị của chiến lược cao hơn giá trị của chiến lược thay thế. Có lẽ chiến lược tối ưu của no-limit hold'em trên river có chứa cược chặn trước.
- Một đặc điểm quan trọng khác: sau khi X bet chặn trước với K, X luôn fold khi bị raise, dù đối thủ đôi khi bluff. Đó là vì X có thừa tay mạnh (A) để bắt bluff và không cần call raise-bluff thường xuyên. Ngoài ra, người raise-bluff không cố làm người bet ban đầu bàng quan khi call với K; người raise-bluff chỉ cố làm X bàng quan khi *bet* K (so với check) ngay từ đầu.

Với các khái niệm này, tác giả chuyển sang trò chơi AKQ no-limit đầy đủ. Vì độ phức tạp, lời giải và chứng minh được đặt ở Phụ lục Chương 15. **Nếu đã hiểu cách tìm lời giải spread-limit, người đọc đã hiểu bài học quan trọng nhất của trò chơi no-limit.** Đầu phụ lục có phần tóm tắt các bước và nêu lời giải không kèm chứng minh; phần còn lại là toán học phía sau, chủ yếu dành cho người có nền tảng toán.

### 5. Phụ lục Chương 15 — Trò chơi AKQ no-limit: tóm tắt và lời giải (Appendix to Chapter 15 — The No-Limit AKQ Game: Summary, trang 176–177)

Luật (người tổng hợp nêu rõ theo ngữ cảnh): một full-street, bộ bài A, K, Q, pot bằng 1, cược no-limit với stack lớn, raise tối thiểu gấp đôi cược trước.

Lời giải của trò chơi AKQ no-limit đầy đủ gần một cách bất ngờ với lời giải trò chơi spread-limit của Ví dụ 15.2 (sách ghi nhầm "Chương 17"). Các bước tìm chiến lược:

1. Trước hết giải một trò chơi full-street trong đó X không được bet K (hoặc được biết là không bet K). Khi đó X bet r (như Y ở half-street) với một số A và check số A còn lại; Y bet một mức khác, lớn hơn, s₀, khi X check. Cả hai cân đối chiến lược bằng A và Q thích hợp.
2. X có thể cải thiện nếu bỏ ràng buộc không bet K, bằng cách bet một mức nhỏ t với một số K.
3. Y đáp lại X bet t với K bằng cách raise lên một mức s(t) và raise-bluff với Q theo tần suất β. Nhờ đó Y làm X cùng lắm bàng quan giữa check và bet t với K. β liên quan tới s₀, mức Y bet khi X check.
4. X đáp lại bằng cách bet t với một số A bên cạnh K, lấy giá trị nhờ bắt raise-bluff và nhờ K của Y call. Y không chặn được X lấy giá trị theo một trong hai cách đó.
5. Nhưng trong no-limit, X không thể bet mọi A (như trong spread-limit). Nếu làm vậy, tập check của X chỉ còn K, và Y khai thác bằng cách bet thật lớn với A và một số Q; X chỉ có K nên phải call đôi khi, tốn hơn phần X lấy được khi bet A.
6. Lập hàm A(t) là giá trị khi bet t với A: tổng giá trị được K call và giá trị bắt raise-bluff khi đối thủ cầm Q.
7. Với mỗi giá trị s₀, tìm t tối ưu bằng cách cực đại A(t); gọi là τ. Đây là mức X bet với một số A và một số K.
8. Vì X trộn giữa bet và check với A, X phải có cùng kỳ vọng khi check và khi bet τ, tức A(0) = A(τ).
9. Tìm được mức raise t₂ mà Y muốn; tiếc là luật buộc Y raise tối thiểu lên 2t.
10. Cân đối các chiến lược bằng bluff, call, raise-bluff thích hợp sao cho mỗi người bàng quan khi đổi các phần khác nhau của chiến lược.

**Lời giải** (mọi số thập phân là gần đúng; mọi tỷ lệ phần trăm là "trên số tay đã đi tới điểm này theo cách này"):

**X:**
- Check 61,2% số A; nếu Y bet sau đó, X raise all-in.
- Bet τ = 0,2521 với số A còn lại; nếu Y raise, X reraise all-in.
- Bet τ = 0,2521 với 15,62% số K; fold trước mọi raise.
- Check số K còn lại; gặp cược s thì call với tỷ lệ K thích hợp sao cho tổng tỷ lệ call hoặc raise trên các tay đã check là 1/(1 + s).
- Bet τ = 0,2521 với 7,81% số Q; fold trước mọi raise.
- Check-fold với 92,19% số Q còn lại.

**Y:**
- Nếu X check: bet s₀ = 0,5422 với mọi A và 35,16% số Q.
- Nếu X check-raise: reraise all-in với A, fold Q.
- Nếu X bet mức t, định nghĩa: s₀ = 0,5422 là mức Y bet khi X check; α₀ = s₀/(1 + s₀); β = (α₀ − t)/(1 + t) nếu α₀ > t, ngược lại 0; t₂ = α₀/(1 − β) nếu giá trị này lớn hơn 2t, ngược lại 2t. Y raise lên t₂ với mọi A và β số Q. Nếu X raise lại, Y raise all-in với A và fold Q.
- Y call với đủ K để tổng tỷ lệ call (trên các tay thắng được Q) là 1/(1 + t).

Người tổng hợp tính cụ thể tại t = τ ≈ 0,2521: β ≈ (0,35159 − 0,25209)/1,25209 ≈ 0,0795, tức Y raise-bluff khoảng 7,9% số Q; mức raise lý thuyết α₀/(1 − β) ≈ 0,382 nhỏ hơn 2τ ≈ 0,504, nên Y raise lên 2τ ≈ 0,504 pot; Y call với (1 − τ)/(1 + τ) ≈ 59,7% số K. X call cược s₀ với khoảng 39,3% số K đã check.

### 6. Phụ lục — Dẫn giải phần 1: trò chơi khi X không được bet K (Derivation, trang 177–179)

#### Vì sao X không thể bet mọi A

Xét trò chơi với ràng buộc X không được bet K. Ngay lập tức thấy nếu X bet mọi A, X bị khai thác: Y bet một mức rất lớn với mọi A và một tỷ lệ Q thích hợp. Vì đã bet mọi A, X chỉ còn K để phòng thủ trước bluff của đối thủ; X phải call với một tỷ lệ K, nhưng cho đi quá nhiều giá trị trước A của đối thủ.

Cụ thể: giả sử X bet mọi A và check mọi K. Y bet 100 đơn vị (pot = 1) với mọi A và 100/101 số Q. X phải call với 1/101 số K để Y không bluff có lời (α = 100/101). Nghĩa là X cho đi 100/101 đơn vị mỗi khi X cầm K gặp A của Y (người tổng hợp tính: 100 × 1/101). Nhưng X có thể cải thiện bằng cách check vài A và call các cú bet đó (khi đó các cú bet X gặp với A đều là bluff). Vậy bet mọi A ngay từ đầu không thể tối ưu.

Vì X phải check mọi K (theo luật của trò chơi phụ), và phải check một số A để tạo mối đe doạ đáng tin chống việc đối thủ bluff lớn, X có thể check mọi A hoặc một phần A. Gọi **A_k** là tỷ lệ A X check. X bet một mức t với số A không check và một tỷ lệ Q thích hợp. Nếu X bet t, Y đáp lại bằng cách (ít nhất) call với tổng tỷ lệ 1/(1 + t) số tay, làm X bàng quan khi bluff Q. Nếu X check, Y bet một mức s. Vậy có ba ẩn: A_k, t, s, ngoài các tỷ lệ bet/bluff dễ tính.

#### Ẩn t: mức X bet với A

Với Y, tỷ lệ tay call là K bằng 1/(1 + t) − 1/2 (trên tổng số tay của Y), trừ khi X bet hơn 1 (hơn pot), khi đó Y call với mọi A và không K nào. Equity của X khi bet t, cầm A, gặp Y cầm K (Y call với tỷ lệ 2[1/(1 + t) − 1/2] = 2/(1 + t) − 1 số K):

```text
<A gặp K, bet t> = t·(2/(1 + t) − 1) = (t − t²)/(1 + t)
```

(sách in "(t − t)²/(t + 1)", xem Lưu ý). Cực đại theo t:

```text
[(t + 1)(1 − 2t) − (t − t²)(1)]/(t + 1)² = 0
1 − t² − 2t = 0
t = √2 − 1 = r          (Phương trình 14.1)
```

Y khi đó call với (1 − t)/(1 + t) số K (sách in "(t − 1)/(t + 1)"); với t = r, tỷ lệ này bằng (2 − √2)/√2 = √2 − 1 = r.

#### Ẩn s: mức Y bet khi X check

Khi X check, Y bet một mức s với A và Q thích hợp. X call với các A còn lại (nhớ rằng X đã bet một số A) và đủ K để Y bàng quan khi bluff Q. X phải bàng quan giữa bet r và check với A, vì X trộn hai lựa chọn này. Kỳ vọng của hai cách chơi A:

```text
<A, check> = (s/(1 + s))·(s)·(1/2) = s²/[2(1 + s)]
             (Y có Q nửa số lần, bluff tỷ lệ s/(1 + s), X call được s)
<A, bet r> = (r − r²)/[2(1 + r)] = 3/2 − √2 ≈ 0,0858
             (Y có K nửa số lần, call r số K; Y có Q thì fold)
```

Đặt bằng nhau:

```text
3/2 − √2 = s²/[2(1 + s)]
(3 − 2√2)(1 + s) = s²      tức 3 − 2√2 + 3s − 2√2·s = s²
s ≈ 0,50879
```

(Người tổng hợp giải: với c = 3 − 2√2 ≈ 0,171573, s = [c + √(c² + 4c)]/2 ≈ (0,171573 + 0,846008)/2 ≈ 0,50879.)

#### Ẩn A_k: tỷ lệ A X check

Nếu A_k không chọn đúng, Y khai thác X bằng cách bluff mức lớn hơn hoặc nhỏ hơn. Vậy X chọn A_k sao cho equity của Y lớn nhất đúng khi Y bet s.

Khi X cầm K, Y cầm A, Y được một cược (gọi mức này là q) khi X call. Tần suất call của X phụ thuộc A_k. Tổng số tay X còn lại khi check là A_k(1/2) + 1/2 = (1/2)(1 + A_k). Nếu Y bet q, X call với tổng tỷ lệ (A và K):

```text
(1/2)(1 + A_k)·1/(1 + q) = (1 + A_k)/[2(1 + q)]
```

Trong đó X call với A tỷ lệ (1/2)A_k, rồi với K cho đủ. Số K X call:

```text
(1 + A_k)/[2(1 + q)] − (1/2)A_k
= [1 + A_k − (A_k + qA_k)]/[2(1 + q)]
= (1 − qA_k)/[2(1 + q)]
```

Equity của Y khi được K call là giá trị này nhân q:

```text
<K/A, bet q> = (q − q²A_k)/[2(1 + q)]
```

Cực đại theo q:

```text
[(1 + q)(1 − 2qA_k) − (q − q²A_k)]/(1 + q)² = 0
1 = 2qA_k + q²A_k
(q + 1)² = 1/A_k + 1          (hoàn thành bình phương)
q = √((A_k + 1)/A_k) − 1
```

Vậy với mỗi A_k X chọn, Y cực đại equity bằng cách bet q bằng giá trị này. Đặt q = s để tìm A_k tối ưu của X:

```text
0,50879 = √((A_k + 1)/A_k) − 1
A_k ≈ 0,78342
```

(Kiểm tra: 1,50879² ≈ 2,27645 = 1 + 1/A_k, nên A_k ≈ 1/1,27645 ≈ 0,78342.)

#### Lời giải trò chơi rút gọn (X bắt buộc check K)

- X check A khoảng 78,3% số lần, bet r (khoảng 41,4% pot; sách in 41,2%) với phần còn lại; bet r pot với số Q bằng r/(1 + r) lần số A đem bet, tức khoảng 6,3% số Q (người tổng hợp tính: 0,29289 × 0,21658 ≈ 0,0634); bị buộc check mọi K.
- Y đáp lại cược t (t > 0) bằng cách call với (tối thiểu) mọi A, và nếu cược đủ nhỏ, với đủ K để tổng tỷ lệ call (nếu đối thủ đang bluff) bằng 1/(1 + t) (sách in 1/(1 + s)).
- Nếu X check, Y bet s (khoảng 50,8% pot) với mọi A và khoảng 33,7% số Q (= s/(1 + s)). X call với đủ K để tổng tỷ lệ call (với A đã check và K) bằng 1/(1 + s).
- Với các mức cược tối ưu: Y call cược r với r số K; X call cược s với khoảng 39,9% số K (sách in 39,8%; người tổng hợp tính (1 − sA_k)/(1 + s) ≈ 0,3986, đúng bằng s·A_k do điều kiện tối ưu 1 = 2qA_k + q²A_k).
- **Giá trị trò chơi rút gọn với Y ≈ 0,02761 đơn vị** (người tổng hợp tính lại: 0,027607). So với trò chơi half-street AKQ #3 của Chương 14 (giá trị r²/6 ≈ 0,0286), quyền bet của X (dù chưa được bet K) đã làm giá trị của Y giảm nhẹ.

### 7. Phụ lục — Dẫn giải phần 2: khi X được bet K (Derivation, tiếp theo, trang 179–182)

#### X check K có equity −α₀/2

Nếu bỏ ràng buộc "phải check K", X cải thiện được. Khi X check một K, dùng lối tắt: Y sẽ làm X bàng quan khi call với K bằng cách bet và bluff đúng tỷ lệ, nên có thể giả sử X luôn fold. X mất một đơn vị (pot) mỗi khi Q bluff. Y bluff s₀/(1 + s₀) số lần và có Q nửa số lần. Định nghĩa α₀ = s₀/(1 + s₀). Equity của X:

```text
<X, check K> = (1/2)[−s₀/(1 + s₀)] = −α₀/2
```

#### Y phải raise với A và raise-bluff với Q

Rõ ràng nếu Y tiếp tục đáp lại cược t chỉ bằng call với A và K, X có thể bet một mức rất nhỏ để chặn Y bluff. Vậy lấy làm chiến lược ứng viên: Y đáp lại cược t bằng raise lên 2t (mức tối thiểu) hoặc một giá trị t₂ nào đó, lấy mức lớn hơn, với mọi A và một tỷ lệ Q là β(t). Equity của X khi bet t với K:

```text
<X, bet t với K> = (1/2)(−t) + (1/2)(β)[−(1 + t)]
                   (Y có A: raise, X fold, mất t; Y có Q raise-bluff: mất pot và t)
```

β phải đủ lớn để biểu thức này không lớn hơn equity khi check. Các trường hợp mà equity bet t nhỏ hơn equity check xảy ra khi X bet quá nhiều với K; tạm thời chỉ xét các mức cược chặn trước hợp lý (sau sẽ thấy β có thể bằng 0 nếu mức cược đủ lớn). Vậy:

```text
(1/2)(−t) + (1/2)(β)[−(1 + t)] = −α₀/2
t + βt + β = α₀
β = (α₀ − t)/(1 + t)        (khi α₀ > t)
```

#### Hàm A(t) và mức cược τ

Khi X bet, Y call với (1 − t)/(1 + t) số K. Nếu t₂ là mức Y raise lên, equity khi bet t với A:

```text
A(t) = (1/2)·[t(1 − t)/(1 + t)] + (1/2)·β·t₂
```

Thay mức raise tối thiểu 2t cho t₂ và biểu thức của β:

```text
A(t) ≥ (1/2)·[t(1 − t)/(1 + t)] + (1/2)·[(α₀ − t)/(1 + t)]·(2t)      (α₀ > t)
```

Dấu bằng đổi thành bất đẳng thức vì đôi khi t₂ có thể lớn hơn 2t, làm A(t) lớn hơn. Rút gọn:

```text
A(t) ≥ (t − t² + 2tα₀ − 2t²)/[2(1 + t)] = [t/(1 + t)]·(1 − 3t + 2α₀)/2
```

Cực đại:

```text
A′(t) = [1/(1 + t)²]·(1 − 3t + 2α₀)/2 + [t/(1 + t)]·(−3/2)
      = [1 − 3t + 2α₀ − 3(t + t²)]/[2(1 + t)²]
0 = 1 − 6t − 3t² + 2α₀
3t² + 6t − 2α₀ − 1 = 0
t² + 2t − (2/3)α₀ − 1/3 = 0
(t + 1)² = (2/3)α₀ + 4/3
t = √(4/3 + (2/3)α₀) − 1
```

(Ba dòng giữa của sách in sai dấu của α₀, xem Lưu ý; dòng kết quả đúng.) Giá trị t này đặc biệt: nếu Y đáp lại cú check bằng cược s₀, mức tối ưu để X bet với K là t này (phụ thuộc s₀ qua α₀). Gọi là **τ**.

#### Tìm s₀ từ A(0) = A(τ)

X bàng quan giữa check và bet τ ở một giá trị s nhất định, vì X trộn chiến lược với A (nếu không, Y khai thác X bằng cách bet mức lớn như đã nói). Dùng điều này để tìm s₀:

```text
A(0) = A(τ)
(1/2)(α₀)(s₀) = (1/2)·[τ(1 − τ)/(1 + τ)] + (1/2)·[(α₀ − τ)/(1 + τ)]·(2τ)
```

τ là hàm của α₀ và do đó của s₀, nên giải được s₀. Giải số: **s₀ ≈ 0,54224, α₀ ≈ 0,35159, τ ≈ 0,25209.** (Người tổng hợp kiểm tra: τ = √(4/3 + 2 × 0,35159/3) − 1 = √1,56773 − 1 ≈ 0,25209; hai vế cùng bằng khoảng 0,09532.)

#### Mức raise t₂ của Y

Nhắc lại β = (α₀ − t)/(1 + t) khi α₀ > t. Không thể raise-bluff với tỷ lệ âm, nên β = 0 khi t > α₀. Dùng công thức này, có thể tìm mức raise-bluff đúng: Y nên raise một mức sao cho X bàng quan khi call bằng K (nếu được; nếu không thì raise-bluff mức tối thiểu). Với cược t và raise lên t₂, X cầm K bàng quan giữa call và fold:

| Tay của người chơi thứ hai (Y) | X call bằng K | X fold |
|---|---|---|
| A | −(t₂ − t) (chênh lệch so với fold) | 0 |
| Q | +t₂ | −(1 + t) |

Y raise với mọi A (trọng số 1) và β số Q (trọng số β):

```text
t₂ − t = β(t₂ + 1 + t)
(1 − β)t₂ = β(1 + t) + t
(1 − β)t₂ = α₀ − t + t          (vì β(1 + t) = α₀ − t)
t₂ = α₀/(1 − β)
```

Đây là giá trị **lý thuyết** t₂ — mức Y sẽ raise nếu luật không buộc raise tối thiểu gấp đôi cược. Ở các mức cược trên α₀, t₂ thấp hơn mức cược, nghĩa là Y không cần raise và raise-bluff gì để giữ equity nếu X bet từ mức đó trở lên. Ở các mức t rất nhỏ, Y không thể chỉ raise lên 2t, vì như vậy mất giá trị trước K của đối thủ; Y raise lên một mức gần s₀. Có một điểm (sách ghi gần 0,2001; người tổng hợp tính được 0,2010) mà giá trị lý thuyết bằng mức raise tối thiểu:

```text
s(t) = α₀/(1 − β)     (t < 0,2010)
s(t) = 2t             (t > 0,2010)
```

(Người tổng hợp giải: α₀/(1 − β) = 2t với 1 − β = (1 + 2t − α₀)/(1 + t) dẫn tới 4t² + (2 − 3α₀)t − α₀ = 0, nghiệm dương t ≈ 0,2010.) Vì τ ≈ 0,2521 > 0,2010, Y raise lên 2τ ≈ 0,5042.

#### Tần suất check và bet của X với A và K

Các biến lớn còn lại là tần suất check và bet của X với A và K. X check A và K theo một tỷ lệ khiến Y bet đúng s₀ khi X check, và bet A và K theo một tỷ lệ khiến Y bàng quan khi raise-bluff đúng mức tối ưu. Ghép hai tỷ lệ này ra tần suất chính xác.

**Tỷ lệ khi check.** Khi X check, X call 1/(1 + s₀) với mọi tay để đối thủ bàng quan khi bluff Q. Gọi k là tỷ lệ K trong các tay X check. Nếu Y bet q với A khi X check, X call với tổng 1/(1 + q) số tay; 1 − k trong số đó là A, còn lại 1/(1 + q) − 1 + k là K, trên tổng k K ban đầu. Tỷ lệ K được call:

```text
[1/(1 + q) − 1 + k]/k = (k − q + kq)/[k(1 + q)]
```

Equity của Y khi bet q với A sau khi X check: (kq − q² + kq²)/[k(1 + q)]. Cực đại theo q:

```text
[k(1 + q)(k − 2q + 2kq) − k(kq − q² + kq²)]/[k²(1 + q)²] = 0
k − 2q + 2kq + kq − 2q² + 2kq² − kq + q² − kq² = 0
k − 2q + 2kq − q² + kq² = 0
k(1 + 2q + q²) = 2q + q²
```

Thay q bằng s₀ đã biết: k = 1 − 1/(1 + s₀)² ≈ **0,57957**.

**Tỷ lệ khi bet.** Tương tự, X bet t với A và K theo tỷ lệ khiến equity của Y cực đại khi raise-bluff đúng mức tối ưu. Y được 1 + τ khi raise-bluff thành công, mất mức raise q (ở đây q = 2τ) khi bị call. Nhưng X sẽ không call bằng K! X có thể fold mọi K trước raise; Y không còn khai thác được X bằng raise nhỏ hơn vì raise phải ít nhất 2t. X "call" (thực ra reraise với A) đủ để Y bàng quan khi raise-bluff, tức (1 + τ)/(1 + τ + q) số lần. Vậy tỷ lệ K so với (A + K) khi bet là:

```text
q/(1 + τ + q) = 2τ/(1 + 3τ) ≈ 0,50418/1,75627 ≈ 0,28707
```

**Ghép hai tỷ lệ.** Gọi c là tổng lượng tay (A và K) X check, b là tổng lượng tay X bet (tính trong đơn vị mà mọi A bằng 1, mọi K bằng 1):

```text
0,28707b + 0,57957c = 1      (mọi K hoặc bet hoặc check)
0,71293b + 0,42043c = 1      (mọi A hoặc bet hoặc check)
```

Cộng hai phương trình được b + c = 2. Giải: **b ≈ 0,54406, c ≈ 1,45594** (sách in đổi chỗ "b ≈ 1,45595, c ≈ 0,55405", xem Lưu ý). Từ đó:

| | Check | Bet τ |
|---|---|---|
| A | A_k = 0,42043 × 1,45594 ≈ **61,213%** | A_b = 0,71293 × 0,54406 ≈ **38,787%** |
| K | K_k = 0,57957 × 1,45594 ≈ **84,382%** | K_b = 0,28707 × 0,54406 ≈ **15,618%** |

Q bluff = τ/(1 + τ) × A_b ≈ 0,20134 × 0,38787 ≈ **7,81%** số Q (người tổng hợp tính, khớp lời giải).

Với điều đó, có chiến lược tối ưu của trò chơi. **Giá trị trò chơi với Y khoảng 0,02682 đơn vị mỗi ván** (người tổng hợp tính lại bằng chương trình: 0,026824).

Người tổng hợp tóm tắt chuỗi giá trị với Y của các phiên bản AKQ no-limit (pot = 1): half-street (Ví dụ 14.2) r²/6 ≈ 0,0286; full-street khi X không được bet K ≈ 0,02761; full-street đầy đủ ≈ 0,02682. Mỗi quyền thêm cho X đều làm giá trị của Y giảm, đúng như nguyên tắc "lựa chọn chiến lược có giá trị không âm".

## Luận điểm cốt lõi

### Mệnh đề

Trong trò chơi full-street, người đi trước không bao giờ thiệt so với half-street; các tỷ lệ α vẫn chi phối value bet, bluff và fold của cả hai bên, nhưng lựa chọn ở nút đầu làm đổi phân phối ở các nút sau. Khi có nhiều mức cược, chiến lược tối ưu có thể chứa **cược chặn trước** — bet một tay bài ở giữa với mức nhỏ để giảm giá trị bluff của đối thủ — và việc kiểm tra mọi lệch đơn phương là bắt buộc để không dừng ở một lời giải sai.

### Giả định

- Bộ bài A, K, Q; mỗi người một lá; tổng bằng 0; tính ngoài showdown; không rake.
- AKQ #4: limit, cược 1, pot P > 1, không raise (lời giải vẫn đúng khi cho raise).
- AKQ #5: pot 4, bet hoặc raise 1 hay 2 đơn vị.
- Phụ lục: pot 1, no-limit, stack lớn, raise tối thiểu gấp đôi; cả hai biết chiến lược của nhau ở cân bằng.

### Cơ chế

1. Viết chiến lược thành kế hoạch trọn vẹn (bet / check-call / check-fold); lập ma trận; loại chiến lược bị trội.
2. Với mỗi nút (X bet, X check), áp dụng điều kiện bàng quan: tỷ lệ bluff α so với value bet; tỷ lệ fold α trên tay bắt bluff, tính trên phân phối **còn lại** ở nút đó.
3. Viết giá trị trò chơi theo biến còn lại (x, hoặc τ, s₀, A_k) và để bên kiểm soát biến chọn giá trị tối ưu.
4. Kiểm tra mọi lệch đơn phương, kể cả các nước trước đó bị coi là bị trội (bet K với mức nhỏ). Nếu có lệch có lời, thêm phản ứng (raise, raise-bluff) và lặp lại.
5. Ghép các tỷ lệ ở từng nút (tỷ lệ K trong tập check, tỷ lệ K trong tập bet) thành tần suất cuối.

### Bằng chứng và ví dụ tác giả đưa ra

- Ba ma trận của AKQ #4 và sáu trường hợp cặp lá, cho giá trị [x(3α − 1) + 1 − 2α]/6 và Hình 15.1.
- Lời giải AKQ #4 tách theo P < 2 và P > 2.
- AKQ #5: phép thử X cầm K (2/3 so với 1/2), q = 1/15, A bet 11/30 so với check 1/3, tỷ lệ A : K = 5 : 2, lời giải và bảng giá trị (−1/10 với X).
- Phụ lục: ví dụ Y bet 100 pot với 100/101 số Q; dẫn giải r, s ≈ 0,50879, A_k ≈ 0,78342; τ ≈ 0,25209, s₀ ≈ 0,54224, k ≈ 0,57957, tỷ lệ 0,28707; giá trị 0,02761 và 0,02682.

### Kết luận và hàm ý cho người chơi

- Khi hành động trước, cân nhắc bet thẳng với tay mạnh nếu pot lớn so với cược (AKQ #4: P > 2), vì đối thủ có nhiều tay ở giữa sẽ call; nếu pot nhỏ, check để dụ bluff.
- Khi bet một phần tay mạnh, tập check của bạn yếu đi; phải call rộng hơn với tay bắt bluff (c = 1 − 2α + αx) và nên giữ một phần tay mạnh trong tập check để không bị bet lớn khai thác.
- Với tay ở giữa trên river, một cú bet nhỏ "chặn trước" có thể tốt hơn check khi đối thủ thích bet lớn; khi bị raise sau cú bet đó, thường nên fold nếu phạm vi của bạn đã có đủ tay mạnh để bắt bluff.
- Dùng một mức cược chung cho tay mạnh, tay ở giữa và bluff để không lộ thông tin.

### Trong ngôn ngữ lý thuyết trò chơi

Chương chuyển từ trò chơi một nút quyết định cho mỗi người sang trò chơi dạng mở rộng (extensive form) có nhiều nút; "chiến lược" trở thành kế hoạch hành động đầy đủ ở mọi tập thông tin, và ma trận lợi ích là dạng chuẩn (normal form) của trò chơi mở rộng. Nguyên lý "lựa chọn có giá trị không âm" là tính đơn điệu của giá trị trò chơi theo tập chiến lược của một người. Phát hiện ở AKQ #5 minh hoạ rằng loại chiến lược bị trội chỉ an toàn trong một trò chơi cố định: khi thêm hành động mới, một chiến lược trước đây bị trội có thể trở thành phần của cân bằng, và phải kiểm tra lại điều kiện cân bằng Nash (không có lệch đơn phương có lời) trên toàn bộ không gian chiến lược mới.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| full-street | full-street (một vòng cược đầy đủ) | cả hai người được bet; X hành động trước |
| half-street | half-street (nửa vòng cược) | chỉ người thứ hai được bet |
| check dark | check trong bóng tối | check trước khi có thông tin |
| strategy / strategic option | chiến lược / lựa chọn chiến lược | kế hoạch trọn vẹn / hành động tức thời |
| bet / check / call / fold / raise | bet / check / call / fold / raise | đặt cược / không cược / theo / bỏ bài / tố thêm |
| check-call, check-fold, check-raise | check-call, check-fold, check-raise | check rồi call / fold / raise khi bị bet |
| reraise | reraise | raise lại sau khi bị raise |
| all-in | all-in | cược toàn bộ stack |
| value bet / value raise | value bet / value raise | bet hoặc raise với tay mạnh để được call |
| bluff / raise-bluff | bluff / raise-bluff | bet hoặc raise với tay yếu để đối thủ fold |
| induce a bluff | dụ bluff | check tay mạnh để đối thủ bluff |
| preemptive bet | cược chặn trước | bet nhỏ với tay ở giữa để giảm giá trị bluff của đối thủ |
| spread-limit | spread-limit | được bet trong một khoảng mức cố định |
| minimum raise | raise tối thiểu | raise ít nhất gấp đôi cược trước |
| pot / stack | pot / stack | tiền đang tranh giành / chip người chơi có |
| river | river | vòng cược cuối trong hold'em |
| no-limit hold'em | no-limit hold'em | hold'em không giới hạn mức cược |
| ex-showdown value | giá trị ngoài showdown | thắng thua do cược, không tính pot ban đầu |
| payoff matrix | ma trận lợi ích | bảng kết quả theo cặp chiến lược |
| dominated strategy | chiến lược bị trội | không bao giờ tốt hơn một chiến lược khác |
| co-optimal | đồng tối ưu | nhiều chiến lược cùng cho giá trị tối ưu |
| unilateral deviation | lệch đơn phương | một người tự đổi chiến lược |
| nemesis | nemesis | chiến lược đáp trả tối đa |
| indifference | bàng quan | hai lựa chọn cho cùng kỳ vọng |
| information hiding | che giấu thông tin | không để mức cược lộ tay bài |
| α, α₀ | hằng số α, α₀ | tỷ lệ bluff/value bet và tỷ lệ fold; α₀ = s₀/(1 + s₀) |
| β | β | tỷ lệ Q mà Y raise-bluff |
| τ (tau) | τ | mức cược tối ưu của X trong AKQ no-limit, ≈ 0,2521 pot |
| r (golden mean of poker) | r (tỷ lệ vàng của poker) | √2 − 1 ≈ 0,414 |
| toy game | trò chơi đồ chơi | mô hình poker đơn giản hoá để giải chính xác |
| equity | equity | phần kỳ vọng của một người |

## Câu nói đáng nhớ

> "Player X cannot lose value moving from a half-street game to a full-street one." — phần mở đầu
>
> *Dịch: Người chơi X không thể mất giá trị khi chuyển từ trò chơi half-street sang full-street.*
>
> Ý nghĩa: có thêm lựa chọn thì không thể thiệt, vì luôn có thể bỏ qua lựa chọn đó.

> "The option that X has to bet changes the distribution of hands he has when he checks." — phần mở đầu
>
> *Dịch: Việc X có quyền bet làm thay đổi phân phối tay bài X có khi X check.*
>
> Ý nghĩa: mỗi quyết định sớm định hình thông tin ở các nút sau.

> "Neither player can improve their expectation unilaterally by changing strategies." — Ví dụ 15.2
>
> *Dịch: Không người chơi nào cải thiện được kỳ vọng bằng cách đơn phương đổi chiến lược.*
>
> Ý nghĩa: đây là phép thử phải làm với mọi lời giải "trông hợp lý".

> "It is important not to stop short of the solution when solving games." — Key Concepts
>
> *Dịch: Khi giải trò chơi, điều quan trọng là không dừng lại trước khi tới lời giải.*

> "We call it a preemptive bet." — Key Concepts
>
> *Dịch: Chúng tôi gọi nó là cược chặn trước.*
>
> Ý nghĩa: tên cho một loại bet mới, không phải value bet cũng không phải bluff.

> "Betting preemptively is a perfect example of a play that has negative expectation, but the expectation of the play is less negative than the alternative of checking." — Key Concepts
>
> *Dịch: Bet chặn trước là ví dụ hoàn hảo về một nước đi có kỳ vọng âm, nhưng ít âm hơn lựa chọn check.*
>
> Ý nghĩa: quyết định đúng được đo bằng so sánh với phương án thay thế, không phải bằng dấu của EV.

> "It is likely that no-limit holdem on the river contains preemptive betting as part of optimal strategy." — Key Concepts
>
> *Dịch: Có lẽ chiến lược tối ưu của no-limit hold'em trên river có chứa cược chặn trước.*

> "If you understood how the spread-limit solution was derived, then you have understood the most important lesson of the no-limit game." — trước phụ lục
>
> *Dịch: Nếu đã hiểu cách tìm lời giải spread-limit, bạn đã hiểu bài học quan trọng nhất của trò chơi no-limit.*

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương làm hai việc lớn. Thứ nhất, nó đặt khung cho mọi trò chơi nhiều nút về sau: chiến lược là kế hoạch trọn vẹn, quyền thêm không bao giờ thiệt, và phân phối ở mỗi nút phụ thuộc lựa chọn trước đó. Lời giải AKQ #4 rất gọn và cho một kết quả trực giác đẹp: ngưỡng P = 2 quyết định X nên dụ bluff hay bet thẳng, và khi pot lớn, quyền bet trước của X triệt tiêu gần hết lợi thế vị trí của Y. Thứ hai, AKQ #5 là một bài học phương pháp hiếm thấy trong sách poker: tác giả kể lại chính quá trình mình tưởng đã giải xong, rồi phát hiện một lệch đơn phương, rồi chuỗi phản ứng dẫn tới một khái niệm mới — cược chặn trước. Phụ lục cho thấy khái niệm này sống sót trong no-limit thật sự (X bet ≈ 25% pot với một phần K), với lời giải số mà người tổng hợp đã kiểm tra lại toàn bộ các điều kiện bàng quan.

### Những chỗ đơn giản hoá

- **Phân phối ba lá:** mỗi người chỉ có ba loại tay; trong poker thật phạm vi liên tục và tay "ở giữa" có nhiều mức. Các Chương 16–18 xử lý trò chơi [0,1] full-street.
- **Một vòng cược, không có lá chung:** không có hiệu ứng của các vòng sau hay của equity khi còn bài để rút.
- **Raise tối thiểu gấp đôi:** kết quả phụ lục phụ thuộc luật này (Y phải raise lên 2τ thay vì mức lý thuyết ≈ 0,382). Luật no-limit hold'em thông thường cũng buộc raise thêm ít nhất bằng cược trước, tức tổng ít nhất gấp đôi, nên giả định này sát thực tế; nếu luật cho raise nhỏ hơn, Y raise được đúng mức lý thuyết t₂ và các con số của lời giải sẽ khác (nhận xét của người tổng hợp; sách không giải trường hợp này).
- **Trình bày phụ lục có nhiều lỗi in** (công thức, dấu, số bị đổi chỗ) khiến người đọc khó tự kiểm; các kết quả cuối vẫn đúng.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

Các solver hiện đại xác nhận rộng rãi hiện tượng mà chương gọi là cược chặn trước: trong cộng đồng poker ngày nay nó được gọi là **"blocking bet"** (bet chặn) — người hành động trước bet nhỏ trên river với tay bài trung bình để "đặt giá" cho showdown và ngăn đối thủ bet lớn. Solver cũng cho thấy chiến lược "donk bet" (người không có lợi thế vị trí bet trước) với mức nhỏ là một phần của cân bằng ở một số cấu trúc bàn bài, đúng tinh thần AKQ #5. Đồng thời, solver xác nhận ý thứ hai của Key Concepts: khi bị raise sau một blocking bet, phạm vi bài trung bình thường fold nhiều, vì phạm vi bet đã có các tay mạnh đảm nhận việc bắt bluff. Các AI poker như Libratus (2017) và Pluribus (2019) dùng nhiều mức cược và được ghi nhận là có các cú bet nhỏ và lớn bất thường so với thói quen của người chơi — phù hợp với thông điệp "kiểm tra mọi lệch, đừng tin trực giác".

### Liên hệ các chương khác

- [C10-ly-thuyet-tro-choi.md](C10-ly-thuyet-tro-choi.md): ma trận lợi ích, chiến lược bị trội, cân bằng.
- [C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md): hằng số α và trò chơi half-street.
- [C13-tro-choi-akq.md](C13-tro-choi-akq.md): AKQ #1 và #2 (half-street limit), nền của AKQ #4.
- [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md): AKQ #3 (half-street no-limit), hằng số r, kỹ thuật chọn mức cược — nền của phụ lục.
- [C16-tro-choi-01-khong-bo-bai.md](C16-tro-choi-01-khong-bo-bai.md), [C17-tro-choi-01-pot-huu-han-va-bluff.md](C17-tro-choi-01-pot-huu-han-va-bluff.md), [C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md): các trò chơi [0,1] full-street.
- [C19-tro-choi-nhieu-vong-tinh.md](C19-tro-choi-nhieu-vong-tinh.md), [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md): nhiều vòng cược.
- [C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md](C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md): áp dụng các trò chơi đồ chơi vào tình huống thật.

### Vận dụng

- **Cho người chơi poker:** (1) Khi ra tay trước trên river với phạm vi phân cực, pot lớn so với cược thì bet thẳng tay mạnh; pot nhỏ thì check để dụ bluff. (2) Nếu bạn hay bet tay mạnh, tập check của bạn yếu đi — hãy call rộng hơn với tay bắt bluff khi check, hoặc giữ vài tay mạnh trong tập check. (3) Với tay trung bình mà đối thủ hay bet lớn khi bạn check, cân nhắc bet nhỏ chặn trước; bị raise thì thường fold. (4) Dùng chung một mức cược cho cả tay mạnh, tay chặn và bluff.
- **Cho người làm tài chính và ra quyết định:** cược chặn trước tương tự một "nước đi phòng thủ có chi phí": chấp nhận một khoản lỗ nhỏ chắc chắn (EV âm) để tránh một khoản lỗ kỳ vọng lớn hơn do đối thủ chủ động (ví dụ: đưa ra một đề nghị giá sớm ở mức vừa phải trong đàm phán để chặn đối tác "neo" một mức cực đoan; mua bảo hiểm hoặc phòng hộ với chi phí xác định). Tiêu chí đúng là so với phương án thay thế, không phải EV dương. Bài học phương pháp — "đừng dừng ở lời giải trông hợp lý; kiểm tra mọi lệch đơn phương, kể cả những lựa chọn trước đây bị loại" — áp dụng trực tiếp cho kiểm định chiến lược kinh doanh và mô hình định giá: khi thị trường thêm một công cụ mới (một mức giá, một sản phẩm phái sinh), các chiến lược từng bị loại có thể trở thành tối ưu, và cân bằng cũ cần được kiểm tra lại.

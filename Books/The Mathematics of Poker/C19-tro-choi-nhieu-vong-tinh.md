# Chương 19 — Con đường tới poker: trò chơi nhiều vòng cược tĩnh (The Road to Poker: Static Multi-Street Games)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 19 "The Road to Poker: Static Multi-Street Games", trang 243–258.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Các chương trước của Phần III chỉ xét trò chơi một vòng cược: nửa vòng (half-street, chỉ một người được cược) và trọn vòng (full-street). Trò chơi "nhìn thấu bài" (clairvoyant game) một vòng cược ở [C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md) cho tỷ lệ bluff α = 1/(P + 1); [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md) giải bài toán chọn mức cược no-limit cho một vòng; [C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md) tổng kết giá trị các trò chơi [0,1] một vòng. Chương 19 bước sang trò chơi **nhiều vòng cược** nhưng giữ bài "tĩnh" (static: giá trị bài không đổi giữa các vòng, không có draw), để thấy bluff vận hành qua nhiều vòng mà chưa phải lo về draw. Kết quả chính — người không nhìn thấu chơi mỗi vòng như một trò chơi một vòng; người nhìn thấu "mang" một tập bài qua từng vòng và bluff nhiều hơn ở vòng đầu; và mức cược tối ưu trong no-limit là **tăng pot theo cấp số nhân** (geometric growth of pot) — trở thành nền tảng của cách chọn mức cược no-limit hold'em ở [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md), nơi bài thay đổi giữa các vòng. Ý tưởng "trò chơi đấu giá" và việc gán cho mỗi tay bài một mức sẵn sàng đặt cược cũng được dùng lại trong các nghiên cứu tình huống ở [C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md](C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md).
**Ý chính:** **Khi có nhiều vòng cược và giá trị bài không đổi, người nhìn thấu bài (Y) bluff ở các vòng đầu nhiều hơn hẳn so với trò chơi một vòng, rồi bỏ dần một phần bluff ở mỗi vòng; người không nhìn thấu (X) chỉ cần chơi mỗi vòng như một trò chơi một vòng độc lập; và trong no-limit, Y nên cược sao cho pot tăng cùng một tỷ lệ ở mỗi vòng và hết stack ở vòng cuối.** Ví dụ 19.1 (hai vòng, limit, pot P): X bỏ α = 1/(P + 1) số bài ở vòng đầu và α₂ = 1/(P + 3) số bài còn lại ở vòng hai; Y giữ tỷ lệ bluff α₂ ở vòng cuối, và ở vòng đầu coi toàn bộ tập bài sẽ cược ở vòng cuối là "bài giá trị" rồi bluff thêm α lần số đó. Với pot 2 cược, số bài chết Y cược ở vòng đầu bằng 3/5 số bài thắng, trong đó 2/3 bị bỏ sau vòng đầu. Với ba vòng (ante 2, cược 1 – 2 – 2, Y thắng nửa số ván), Y cược 7/8 số bài ở flop và lời 1,5 đơn vị mỗi ván. Ví dụ 19.2 (hai vòng no-limit): quan hệ α vẫn đúng với mức cược bất kỳ; gọi rₙ là tỷ số pot sau và trước vòng n thì số bài cược mỗi vòng là Bₙ = 2Mₙrₙ/(1 + rₙ), và tối đa hoá số bài cược B₁ = 4y·r₁r₂/[(1 + r₁)(1 + r₂)] với r₁r₂ = 1 + 2N cố định cho r₁ = r₂ (bất đẳng thức trung bình cộng – trung bình nhân). Ví dụ 19.3 (stack 185 đô la, ante 5 đô la, ba vòng, Y thắng 2/13 số ván) cho thấy cược cấp số nhân (11,66; 38,86; 129,48 đô la) lời 26,41 đô la mỗi tay bài thắng, so với 19,16 đô la khi cược đều 60 đô la mỗi vòng — đủ để đổi trò chơi từ lỗ khoảng 0,51 đô la sang lời khoảng 0,60 đô la mỗi ván. Phần "trò chơi đấu giá" xét số vòng cược tiến ra vô hạn: chiến lược gán mỗi tay bài một ngưỡng sₓ và cược đều từng phần nhỏ ε = S/M chỉ mất tối đa ε, nên giá trị mọi trò chơi tĩnh hội tụ về giá trị của trò chơi đấu giá (hai người cùng bỏ giá kín). Trong trò chơi đấu giá nhìn thấu, X bỏ giá ít nhất s với tỷ lệ x(s) = 1/√(1 + 2s) và Y với tỷ lệ y(s) = y√[(1 + 2S)/(1 + 2s)] (tối đa 1) — đúng là giới hạn của lời giải M vòng.

> **Lưu ý:**
> - **Câu "bỏ 1/12 số bài chết sau flop" sai (trò chơi ba vòng, trang 246).** Theo chính phép tính của sách, Y cược 42/48 số bài ở flop, 35/48 ở turn, 28/48 = 7/12 ở river. Vậy Y bỏ 42/48 − 35/48 = **7/48** số bài sau flop và 35/48 − 28/48 = 7/48 sau turn, rồi bluff 1/12 (= 4/48) số bài ở river. Sách ghi "gives up on 1/12 of his dead hands after the flop and 7/48 after the turn": con số 1/12 là lượng bluff còn lại ở river, không phải lượng bị bỏ sau flop. Kiểm tra: tổng bluff 7/48 + 7/48 + 4/48 = 18/48 = 3/8, đúng bằng 7/8 − 1/2. (Các phân số tính theo toàn bộ số bài, không phải "theo số bài chết".)
> - **Trò chơi ba vòng: "pot will be 6 bets" ở turn** phải đọc là 6 đơn vị (ante 2 + 2 cộng cược flop 1 + 1); cược ở turn là 2 đơn vị. Câu "1/8 of the time, X wins the pot for a net to Y of 1.5 units" viết lủng củng: Y thắng pot 4 đơn vị với 7/8 số bài và thua với 1/8, nên Y lời 4 × 7/8 − 2 = 1,5 đơn vị mỗi ván.
> - **Định nghĩa r₂ bị viết ngược (trang 248):** sách viết r₂ là "(1 + 2s₁)/(1 + 2s₁ + 2s₂)"; đúng là (1 + 2s₁ + 2s₂)/(1 + 2s₁), như chính công thức tổng quát rₙ = (pₙ + 2sₙ)/pₙ và phép tính r₂ ở trang 250.
> - **Phép tính giá trị chiến lược cược cấp số nhân trong Ví dụ 19.3 in sai các thừa số.** Sách viết ⟨Y₂⟩ = (46,17%)(8,34 đô la) + (21,31%)(22,26 đô la) + (9,84%)(59,40 đô la) = 26,41 đô la; nhưng tổng các tích này chỉ là 14,44 đô la. Các thừa số đúng là các mức cược 11,66; 38,86; 129,48 đô la: 0,4617 × 11,66 + 0,2131 × 38,86 + 0,0984 × 129,48 ≈ 5,38 + 8,28 + 12,74 = 26,40 đô la (khớp 26,41 của sách, sai số làm tròn).
> - **Dòng "Total" của bảng Ví dụ 19.3 không nhất quán:** sách ghi "60 đô la, 7,88%" cho cược đều và "90 đô la, 4,06%" cho cược cấp số nhân. Tổng số tiền cược của cả hai chiến lược đều là 180 đô la; xác suất X call tới cuối là 7,88% và 9,84%. Người tổng hợp đoán con số 4,06 là lợi nhuận ex-showdown mỗi ván của cược cấp số nhân: (2/13) × 26,41 ≈ 4,06 đô la (với cược đều: (2/13) × 19,16 ≈ 2,95 đô la). Trừ phần lỗ khi lật bài 3,46 đô la, Y lời khoảng +0,60 đô la mỗi ván với cược cấp số nhân và lỗ khoảng −0,51 đô la với cược đều; sách chỉ nói "đủ đổi trò chơi từ âm sang dương" mà không ghi hai số này.
> - **"Stack bằng 3,5 lần pot thì cược nửa pot là đủ"** chỉ đúng cho ba vòng cược (r = 2 nên 1 + 2S = 2³ = 8, S = 3,5); với hai vòng, stack chỉ cần 1,5 lần pot. Sách không nói rõ.
> - **Lỗi dấu và ký hiệu trong lời giải trò chơi đấu giá nhìn thấu (trang 256):** định nghĩa "−Δx = x(s + Δs) − x(s)" ngược dấu với lời giải thích (x giảm khi s tăng nên phải là −Δx = x(s) − x(s + Δs) > 0); dòng "(1 + 2s + Δs)" rồi "(1 + 2s − Δs)" không khớp nhau (không ảnh hưởng giới hạn); dòng tích phân "ln(Cx²) = ln(1 + 2s)" phải là ln(C/x²) = ln(1 + 2s); với Y, "dy/y = ds/(1 + 2s)" thiếu dấu trừ (phải là −dy/y = ds/(1 + 2s), nếu không nghiệm sẽ tăng theo s); "y(S) = y₀" phải là y(S) = y (số bài thắng); điều kiện "(or 0 if y(√(1 + 2s)) > 1)" in lỗi, nghĩa là X không tranh (bỏ giá 0) khi Y không đủ bài bluff. Kết quả cuối x(s) = 1/√(1 + 2s), y(s) = y√[(1 + 2S)/(1 + 2s)] là đúng.
> - **Ký hiệu trong phần chứng minh giới hạn (trang 257–258):** "xₘ = (1 + s₁)⁻ᵐ" và "1 + 2s₁ = Gᵐ" dùng s₁ cho hai nghĩa: lần đầu là mức cược mỗi vòng sₙ = (G − 1)/2, lần sau là tổng số đã cược sau m vòng. Bản tổng hợp viết sₙ và s cho hai đại lượng này.
> - **Số mũ trong Ví dụ 19.4 bị đổi dấu (trang 253–254).** Sách viết yₘ = y₀·r_bᵐ và y₀ = y·r_b^(−M), tức số bài cược ở vòng đầu nhỏ hơn số bài nuts — mâu thuẫn với chính ví dụ hai vòng của sách (1,268²y ở vòng đầu, 1,268y ở river) và với điều kiện "y₀ > 1" ngay sau đó. Đúng là y₀ = y·r_b^M và yₘ = y·r_b^(M − m).
> - **"Nemesis biết sₓ nhỏ hơn x − ε" (trang 255)** phải là "lớn hơn": ta còn cược nghĩa là chưa đạt ngưỡng khi tổng đã cược là x − ε.
> - **Câu "giá trị cho nemesis… nhiều nhất là G − ε" (trang 255) diễn đạt không rõ.** Ý đúng của lập luận: chiến lược đấu giá chỉ thua chiến lược tối ưu tối đa ε, tức đảm bảo ít nhất G − ε (nhận xét của người tổng hợp).
> - **"Đặt cược nhỏ so với pot là tối ưu trong trò chơi tĩnh" (Key Concepts)** chỉ đúng khi số vòng lớn so với độ sâu stack. Chính Ví dụ 19.3 có mức cược khoảng 117% pot mỗi vòng (s/p = (r − 1)/2 ≈ 1,166) (nhận xét của người tổng hợp).
> - **Lớp chữ PDF:** "Υ" (chữ Y Hy Lạp) thay cho Y; "a" và "a2" là α và α₂; "stack 5" là "stack S"; "clairvoyrance" là "clairvoyance"; "hi a similar fashion" là "in a similar fashion"; "ерe hands" là "the hands"; công thức y(1), y(5) ở trang 257 bị vỡ thành ký tự "¿". Người tổng hợp đọc lại từ ảnh trang.
> - **Quy ước:** α = 1/(P + 1) khi cược 1 vào pot P, hay tổng quát α = s/(1 + s) khi cược s (tính theo pot hiện tại); α₂ là tỷ lệ tương ứng ở vòng thứ hai. Mọi giá trị là ex-showdown và tính theo Y trừ khi nói khác. Chữ r trong chương này (tỷ số tăng pot) khác hằng số r = √2 − 1 của các chương trước.

## Sơ đồ

### Mở đầu chương — từ trò chơi một vòng sang trò chơi nhiều vòng tĩnh (trang 243)

```text
       Trò chơi nửa vòng và trọn vòng dễ giải và cho thấy tác động của từng
       yếu tố, nhưng poker thật hiếm khi chỉ có một vòng cược; thêm vòng
       cược làm thay đổi chiến lược về căn bản
                                │
                                ▼
       TRÒ CHƠI TĨNH (static game): nhiều vòng cược, nhưng giá trị bài của
       cả hai người KHÔNG ĐỔI (không có draw)
       · cho thấy bluff vận hành qua nhiều vòng mà chưa cần xử lý draw
       · chương sau (Chương 20) mới xét trò chơi có draw
                                │
                                ▼
       Trò chơi tĩnh hai vòng cơ bản nhất: trò chơi NHÌN THẤU BÀI
       (clairvoyant game) — Y biết chắc mình thắng hay thua
```

### Ví dụ 19.1 — Trò chơi nhìn thấu bài tĩnh hai vòng, limit (The Two-Street Static Clairvoyant Game, trang 243–246)

```text
       Luật: hai vòng trọn, bài tĩnh, pot P cược, limit, Y nhìn thấu bài
       · X chỉ check và call: Y biết chắc kết quả nên khai thác được mọi
         cược của X (vì bài tĩnh; nếu có draw thì khác)
                                │
                                ▼
       Lựa chọn của Y: Y₀ check cả hai vòng; Y₁ cược vòng 1, check vòng 2
       (cách "check rồi cược" bị lộ nên bị trội); Y₂ cược cả hai vòng
       Lựa chọn của X: X₀ bỏ ngay; X₁ call vòng 1, bỏ vòng 2; X₂ call cả hai
       Ma trận (theo Y):      X₀     X₁       X₂
              Y₀              0      0        0
              Y₁             +P     −1       −1
              Y₂ (bluff)     +P   +(P+1)     −2
              Y₂ (giá trị)    0     +1       +2
                                │
                                ▼
       X làm Y bàng quan khi Y có bài chết:
       · Y₀ và Y₁: 0 = Px₀ − x₁ − x₂ ⇒ x₀ = 1/(1 + P) = α
       · Y₁ và Y₂ (bluff): x₂ = (P + 2)x₁ ⇒ x₁ = α₂(1 − α), α₂ = 1/(P + 3)
       ⇒ NGƯỜI KHÔNG NHÌN THẤU CHƠI MỖI VÒNG NHƯ MỘT TRÒ CHƠI MỘT VÒNG:
         bỏ α ở vòng 1, bỏ α₂ số bài còn lại ở vòng 2
                                │
                                ▼
       Y làm X bàng quan:
       · X₀ và X₁: y₁ = α·y₂ — số bài bluff một lần rồi bỏ bằng α lần
         tổng số bài sẽ cược ở vòng 2 (cả giá trị lẫn bluff)
       · X₁ và X₂: y_b = α₂·y_v — vòng 2 bluff theo tỷ lệ α₂
       ⇒ ở vòng trước, Y "coi như" mọi bài sẽ cược ở vòng sau là bài giá
         trị và bluff thêm theo pot hiện tại; ở vòng sau bỏ các bluff đó
                                │
                                ▼
       Ví dụ pot 2 cược, Y có ít bài thắng (V):
       · river pot 4: bluff V/5 ⇒ mang theo 6V/5 "bài giá trị"
       · vòng 1 pot 2: bluff thêm (6V/5)/3 = 2V/5
       · tổng bài chết cược ở vòng 1: 3V/5; bỏ 2/3 số đó sau vòng 1
```

### Mở rộng cho ba vòng với mức cược khác nhau (trang 246)

```text
       Luật: ante 2 mỗi người (pot 4); Y thấy cả bài hai người và bàn; flop
       cược 1, turn và river cược 2; X không cược có lời ở vòng nào
       Giả sử Y thắng 1/2 số ván
                                │
                                ▼
       Đi ngược từ river:
       · river: pot 10, cược 2 (α = 1/6): 1/2 giá trị + 1/12 bluff = 7/12
       · turn: pot 6, cược 2 (α = 1/4): 7/12 + 7/48 = 35/48
       · flop: pot 4, cược 1 (α = 1/5): 35/48 + 7/48 = 42/48 = 7/8
                                │
                                ▼
       Y cược 7/8 số bài ở flop; bỏ 7/48 sau flop, 7/48 sau turn, bluff
       1/12 ở river (sách ghi nhầm "bỏ 1/12 sau flop"); X bỏ α mỗi vòng
                                │
                                ▼
       Giá trị: X bàng quan ⇒ cho X bỏ ngay; Y thắng pot 4 với 7/8 số bài
       ⇒ Y lời 4 × 7/8 − 2 = 1,5 đơn vị mỗi ván
```

### Ví dụ 19.2 — Trò chơi nhìn thấu bài tĩnh hai vòng, no-limit (The Two-Street Static Clairvoyant No-Limit Game, trang 246–250)

```text
       Pot 1, stack N, Y nhìn thấu; Y chọn mức cược s₁, s₂
       Ma trận như Ví dụ 19.1 với −1 thay bằng −s₁, +(P+1) thay bằng
       +(1 + s₁), ±2 thay bằng ±(s₁ + s₂)
                                │
                                ▼
       X: x₀ = s₁/(1 + s₁) = α; x₁ = α₂(x₁ + x₂), α₂ = s₂/(1 + 2s₁ + s₂)
       Y: y₁ = α·y₂; y_b = α₂·y_v
       ⇒ cấu trúc α đúng với MỌI mức cược (khi phân phối bài không quá mạnh)
                                │
                                ▼
       Định nghĩa rₙ = (pₙ + 2sₙ)/pₙ: tỷ số pot sau và trước vòng n nếu cược
       được call; với pot vào vòng bằng 1: r = 1 + 2s, r − s = (1 + r)/2,
       α = s/(r − s)
                                │
                                ▼
       Số bài cược ở vòng n (giá trị cộng bluff), Mₙ là số bài "giá trị"
       (sẽ cược tiếp, hoặc là nuts ở vòng cuối):
       Bₙ = Mₙ + sₙMₙ/(rₙ − sₙ) = 2Mₙrₙ/(1 + rₙ)
       · hai vòng: B₂ = 2y·r₂/(1 + r₂); B₁ = 4y·r₁r₂/[(1 + r₁)(1 + r₂)]
                                │
                                ▼
       X bàng quan ⇒ cho X bỏ ngay ⇒ Y lời pot với mọi bài cược
       ⇒ Y muốn tối đa hoá B₁; Y nên cược hết stack: s₁ + s₂ = N
       · r₁r₂ = 1 + 2N cố định ⇒ cần cực tiểu r₁ + r₂
       · bất đẳng thức trung bình cộng – trung bình nhân ⇒ r₁ = r₂
       · ba vòng: B₁ = 8y·r₁r₂r₃/[(1 + r₁)(1 + r₂)(1 + r₃)] ⇒ r₁ = r₂ = r₃
       · nếu B₁ ≥ 1: Y không đủ bài bluff ⇒ Y cược tất cả, X bỏ tất cả
                                │
                                ▼
       TĂNG POT THEO CẤP SỐ NHÂN (geometric growth of pot): pot tăng cùng
       một tỷ lệ mỗi vòng, hết stack ở vòng cuối — mức cược tối ưu khi trò
       chơi tĩnh và một người nhìn thấu
```

### Ví dụ 19.3 — So sánh cược đều và cược cấp số nhân (trang 250–252)

```text
       Stack 185 đô la, ante 5 đô la mỗi người (pot 10, còn 180 đô la);
       Y rút một lá; ba vòng no-limit; Y thắng khi lật bài nếu lá là A hoặc
       K (xác suất 2/13)
       · không cược: Y được 10 × 2/13 = 1,54 đô la, lỗ 3,46 đô la mỗi ván
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       Y₁: cược 1/3 stack mỗi vòng       Y₂: tăng pot theo cấp số nhân
       · 60 – 60 – 60 đô la              · 10r³ = 370 ⇒ r = ∛37 ≈ 3,3322
       · X call 10/70 = 14,29%;          · 11,66 – 38,86 – 129,48 đô la
         130/190 = 68,42%;               · X call 46,17% mỗi vòng;
         250/310 = 80,6%                   tới cuối 9,84%
       · tới cuối: 7,88%                 · lời mỗi bài thắng 26,41 đô la
       · lời mỗi bài thắng 19,16 đô la
               └────────────────┬────────────────┘
                                ▼
       Bluff hoà vốn (đúng tỷ lệ) ⇒ chênh lệch nằm ở bài thắng: hơn 7 đô
       la mỗi bài thắng ⇒ Y₁ lỗ khoảng 0,51 đô la/ván, Y₂ lời khoảng 0,60
       · giới hạn: Y không thể lấy quá phần lật bài của X (X sẽ bỏ ngay và
         mất 5 đô la ante)
                                │
                                ▼
       Đồ thị r theo stack (pot = 1): hai vòng r = √(1 + 2S), ba vòng
       r = ∛(1 + 2S); r = 3 nghĩa là cược bằng pot: ba vòng cần stack 13
       lần pot; cược nửa pot (r = 2) ứng với stack 3,5 lần pot (ba vòng)
```

### Trò chơi đấu giá — trò chơi có vô số vòng cược (Auction Games, trang 252)

```text
       Trò chơi tĩnh có số vòng rất lớn (tiến ra vô hạn); khi số vòng → ∞,
       chúng hội tụ về một loại trò chơi khác: TRÒ CHƠI ĐẤU GIÁ
       · cấu trúc lời giải khác các trò chơi trước, nhưng cho ít nhất một
         nguyên lý quan trọng
```

### Ví dụ 19.4 — Trò chơi nhìn thấu bài M vòng, no-limit (trang 253–254)

```text
       Pot 1, stack S, M vòng, Y nhìn thấu
       · pot cuối P = 1 + 2S; tỷ lệ tăng mỗi vòng G = P^(1/M);
         mức cược mỗi vòng s = (G − 1)/2 (tính theo pot hiện tại)
                                │
                                ▼
       "Hệ số nhân bluff" r_b = (1 + 2s)/(1 + s): số bài cược ở vòng trước
       bằng r_b lần số bài cược ở vòng sau
       · ví dụ: hai vòng, stack 1, pot 1 ⇒ pot 1 → 3, G = √3, s ≈ 0,366,
         s/(1 + s) ≈ 0,268, r_b ≈ 1,268: river 1,268y, vòng đầu 1,268²y
                                │
                                ▼
       số bài cược ở vòng đầu y₀ = y·r_b^M, giảm r_b lần mỗi vòng tới y
       (sách in số mũ ngược dấu: y₀ = y·r_b^(−M))
       · nếu y₀ > 1: Y thiếu bài bluff ⇒ cược tất cả, X bỏ
       · ngược lại X call với tỷ lệ r_c = 1/(1 + s) mỗi vòng: xₘ = r_cᵐ
       · giá trị trò chơi = y₀ − y (pot cho mỗi bài Y bluff ở vòng đầu)
```

### Ví dụ 19.5 — Trò chơi đấu giá (The Auction Game, trang 254–255)

```text
       Luật: pot 1, stack S, bài tĩnh; mỗi người bỏ giá kín sₓ, s_y trong
       [0, S], lật cùng lúc, cả hai giá vào pot; giá cao hơn thắng; bằng
       nhau thì lật bài (thường khi cả hai bỏ S)
                                │
                                ▼
       Chiến lược "lấy cảm hứng từ đấu giá" cho poker M vòng:
       · gán mỗi tay bài một ngưỡng sₓ (phần của stack)
       · mỗi vòng cược đều ε = S/M cho tới khi đạt sₓ, sau đó check và bỏ
       · bị raise tới mức dưới sₓ thì call rồi tiếp tục cược phần đều của
         stack còn lại; raise tới mức trên sₓ thì bỏ
                                │
                                ▼
       NEMESIS khai thác được bao nhiêu?
       · muốn biết ngưỡng phải call theo ⇒ không bluff ta ra được
       · chỉ lời phần ta buộc phải cược vượt sₓ: tối đa ε (ví dụ 100 vòng,
         sₓ = 0,601: cược 0,01 × 61 = 0,61, vượt 0,009)
       · raise không giúp gì (ba trường hợp sₓ < y, sₓ > y, sₓ = y)
                                │
                                ▼
       Chiến lược đấu giá mất tối đa ε = S/M so với tối ưu; M → ∞ thì
       ε → 0 ⇒ GIÁ TRỊ MỌI TRÒ CHƠI TĨNH HỘI TỤ VỀ GIÁ TRỊ TRÒ CHƠI ĐẤU GIÁ
```

### Ví dụ 19.6 — Trò chơi đấu giá nhìn thấu bài (trang 255–258)

```text
       Y nhìn thấu, có y bài thắng; luật đấu giá, stack S, pot 1
       · Y bỏ giá S với mọi bài thắng; với bài chết, Y bỏ dần các bluff
       · x(s), y(s): tỷ lệ bài mà X, Y bỏ giá ít nhất s
                                │
                                ▼
       Y bàng quan giữa s và s + Δs (bài chết):
       (1 + 2s)·(giảm của x) = Δs·x ⇒ −dx/x = ds/(1 + 2s)
       ⇒ x(s) = 1/√(1 + 2s)  (vì x(0) = 1)
       X bàng quan ⇒ −dy/y = ds/(1 + 2s), y(S) = y
       ⇒ y(s) = y·√[(1 + 2S)/(1 + 2s)]  (tối đa 1)
                                │
                                ▼
       Ví dụ S = 10, y = 0,5: y(1) = 0,5√7 ≈ 1,323 > 1 ⇒ Y bỏ giá ít nhất 1
       với mọi bài; y(5) = 0,5√(21/11) ≈ 0,691 (0,5 thắng + 0,191 bluff)
                                │
                                ▼
       Đây đúng là giới hạn M → ∞ của trò chơi nhìn thấu M vòng:
       sₙ ≈ ln P/(2M), xₘ ≈ P^(−m/(2M)), pot sau m vòng 1 + 2s = P^(m/M)
       ⇒ xₘ = (1 + 2s)^(−1/2) = x(s)
```

### Các khái niệm then chốt (Key Concepts, trang 258)

```text
       1. Trò chơi nhìn thấu mở rộng được ra nhiều vòng: người nhìn thấu
          mang một tập bài qua từng vòng, bluff nhiều hơn ở vòng đầu và bỏ
          một phần ở mỗi vòng
       2. No-limit nhiều vòng nhìn thấu: mức cược tối ưu là tăng pot theo
          cấp số nhân (cùng tỷ lệ mỗi vòng)
       3. Số vòng tăng thì giá trị vị trí về 0 — trò chơi đấu giá đối xứng
       4. Trong trò chơi tĩnh, cược phần nhỏ của pot là tối ưu; trò chơi
          không tĩnh không nhất thiết như vậy
       5. Chiến lược đấu giá gán mỗi tay bài một giá trị sₓ: cách nghĩ hợp
          lý cho no-limit — làm cho kích thước pot tương quan với sức mạnh
          bài
       6. Người không nhìn thấu chơi mỗi vòng như một trò chơi một vòng
       7. Số bài Y bluff một lần rồi bỏ bằng α lần tổng số bài Y cược (giá
          trị và bluff) ở vòng hai
```

## Ba câu hỏi chương này trả lời

1. **Bluff vận hành thế nào khi có nhiều vòng cược mà bài không đổi?** Người không nhìn thấu (X) chơi mỗi vòng như trò chơi một vòng: bỏ α = 1/(P + 1) ở vòng đầu, rồi bỏ α₂ = 1/(P + 3) số bài còn lại ở vòng hai. Người nhìn thấu (Y) đi ngược từ vòng cuối: ở vòng cuối bluff đúng tỷ lệ với pot lúc đó; ở mỗi vòng trước, coi mọi bài sẽ cược ở vòng sau là "bài giá trị" và bluff thêm theo tỷ lệ α của pot hiện tại; các bluff thêm đó bị bỏ ở vòng sau. Kết quả là Y bluff nhiều hơn hẳn ở vòng đầu: pot 2 cược hai vòng thì số bài chết cược ở vòng đầu bằng 3/5 số bài thắng; ba vòng với ante 2 và cược 1 – 2 – 2 thì Y cược 7/8 số bài ở flop dù chỉ thắng 1/2.
2. **Trong no-limit, người có lợi thế thông tin nên cược bao nhiêu mỗi vòng?** Đủ để pot tăng cùng một tỷ lệ r mỗi vòng và hết stack ở vòng cuối: rᴹ = (pot + 2 × stack)/pot. Lý do: X bàng quan nên giá trị của Y tỷ lệ với số bài Y cược ở vòng đầu, B₁ = 2ᴹy·∏rₙ/∏(1 + rₙ); tích ∏rₙ cố định nên cần cực tiểu tổng rₙ, đạt khi mọi rₙ bằng nhau. Với stack 180 đô la và pot 10 đô la qua ba vòng, cược 11,66 – 38,86 – 129,48 đô la lời 26,41 đô la mỗi bài thắng, hơn 7 đô la so với cược đều 60 đô la mỗi vòng, đủ đổi trò chơi từ lỗ sang lời.
3. **Điều gì xảy ra khi số vòng cược rất lớn?** Trò chơi hội tụ về trò chơi đấu giá: mỗi người chọn kín một mức sẵn sàng đặt cược. Chiến lược "gán mỗi tay bài một ngưỡng sₓ, cược đều từng phần nhỏ ε = S/M" chỉ mất tối đa ε so với tối ưu. Trong trò chơi đấu giá nhìn thấu, X bỏ giá ít nhất s với tỷ lệ 1/√(1 + 2s) và Y với tỷ lệ y√[(1 + 2S)/(1 + 2s)], đúng là giới hạn của lời giải M vòng; giá trị vị trí biến mất vì đấu giá đối xứng.

## Khái niệm cần biết

- **Trò chơi tĩnh (static game):** trò chơi nhiều vòng cược mà giá trị bài của cả hai người không đổi giữa các vòng. Ví dụ: Y rút một lá và thắng nếu lá là A hoặc K; ba vòng cược không làm thay đổi điều đó. Quan trọng vì nó tách riêng tác động của nhiều vòng cược lên bluff, chưa có draw.
- **Trò chơi nhìn thấu bài (clairvoyant game):** một người (Y) biết chắc mình thắng hay thua khi lật bài; người kia (X) không biết gì ngoài phân phối. Ví dụ: Y thắng 1/2 số ván và biết ván nào. Quan trọng vì đây là mô hình đơn giản nhất của bluff và call, và kết quả của nó (tỷ lệ α) xuất hiện ở mọi chương sau.
- **Tỷ lệ α và α₂:** α = 1/(P + 1) (hay s/(1 + s) khi cược s vào pot 1) là tỷ lệ bluff trên bài giá trị của người cược và tỷ lệ bài người bị cược được phép bỏ; α₂ là tỷ lệ đó ở vòng hai, khi pot đã lớn thêm. Ví dụ: pot 2 cược thì α = 1/3 ở vòng đầu, pot 4 ở river nên α₂ = 1/5. Quan trọng vì mọi lời giải của chương được viết bằng α.
- **"Mang bài qua vòng" (carrying hands forward):** người nhìn thấu coi các bài sẽ cược ở vòng sau như bài giá trị ở vòng trước và bluff thêm theo tỷ lệ của vòng trước. Ví dụ: river cần V giá trị cộng V/5 bluff, nên ở vòng đầu Y coi 6V/5 là "giá trị" và bluff thêm 2V/5. Quan trọng vì nó giải thích vì sao bluff ở vòng đầu nhiều hơn hẳn trò chơi một vòng.
- **Người không nhìn thấu chơi từng vòng độc lập:** ở mỗi vòng, X bỏ tỷ lệ α của vòng đó trên số bài còn lại. Ví dụ: pot P, X bỏ α = 1/(P + 1) ở vòng một và α₂ = 1/(P + 3) của phần còn lại ở vòng hai. Quan trọng vì đây là quy tắc đơn giản cho người ở thế thiếu thông tin.
- **Tỷ số tăng pot rₙ:** rₙ = (pₙ + 2sₙ)/pₙ, pot sau vòng n (nếu cược được call) chia cho pot trước vòng n. Ví dụ: cược bằng pot (s = 1) cho r = 3; cược nửa pot cho r = 2. Quan trọng vì số bài cược mỗi vòng viết gọn thành Bₙ = 2Mₙrₙ/(1 + rₙ).
- **Tăng pot theo cấp số nhân (geometric growth of pot):** chọn mức cược sao cho mọi rₙ bằng nhau và hết stack ở vòng cuối. Ví dụ: pot 10 đô la, stack 180 đô la, ba vòng: r = ∛37 ≈ 3,332, cược 11,66 – 38,86 – 129,48 đô la. Quan trọng vì đây là mức cược tối ưu của người có lợi thế thông tin trong no-limit tĩnh và là nền tảng cách chọn mức cược ở chương sau.
- **Bất đẳng thức trung bình cộng – trung bình nhân (AM–GM inequality):** với các số dương có tích cố định, tổng nhỏ nhất khi chúng bằng nhau. Ví dụ: r₁r₂ = 9 thì r₁ + r₂ ≥ 6, bằng 6 khi r₁ = r₂ = 3. Quan trọng vì đó là bước chứng minh cược cấp số nhân là tối ưu.
- **Không đủ bài bluff (not enough bluffs):** khi số bài cần cược ở vòng đầu (giá trị cộng bluff) vượt quá toàn bộ số bài, Y cược mọi bài và X nên bỏ hết. Ví dụ: Y thắng 1/2 số ván, stack 10 pot, trò chơi đấu giá: y(1) ≈ 1,323 > 1 nên Y bỏ giá ít nhất 1 với mọi bài. Quan trọng vì nó là giới hạn của các công thức.
- **Hệ số nhân bluff r_b và tỷ lệ call r_c:** r_b = (1 + 2s)/(1 + s) là tỷ số số bài cược ở vòng trước trên vòng sau; r_c = 1/(1 + s) là tỷ lệ X call mỗi vòng. Ví dụ: s ≈ 0,366 cho r_b ≈ 1,268 và r_c ≈ 0,732. Quan trọng vì chúng cho số bài của mỗi bên ở mọi vòng bằng một phép lũy thừa.
- **Trò chơi đấu giá (auction game):** mỗi người bỏ giá kín trong [0, S], cả hai giá vào pot, giá cao hơn thắng pot, bằng nhau thì lật bài. Ví dụ: X bỏ 3, Y bỏ 5 thì Y thắng pot 1 + 3 + 5 = 9. Quan trọng vì đây là giới hạn của trò chơi tĩnh khi số vòng cược tiến ra vô hạn.
- **Chiến lược đấu giá (auction strategy) và ngưỡng sₓ:** gán mỗi tay bài một mức tối đa sẵn sàng đặt, cược đều từng phần ε = S/M cho tới mức đó rồi bỏ. Ví dụ: 100 vòng, stack 1, sₓ = 0,601: cược 0,01 mỗi vòng trong 61 vòng, vượt mức mong muốn 0,009. Quan trọng vì nó chỉ mất tối đa ε so với tối ưu và gợi ý cách nghĩ "kích thước pot tương quan với sức mạnh bài".
- **Nemesis:** chiến lược trả đũa tối đa, biết chiến lược của ta và chơi đáp trả tốt nhất. Ví dụ: nemesis chỉ lời được 0,009 trong ví dụ 100 vòng. Quan trọng vì giá trị trước nemesis đo mức dễ bị khai thác của một chiến lược.
- **Hàm x(s), y(s) của trò chơi đấu giá nhìn thấu:** tỷ lệ bài bỏ giá ít nhất s; x(s) = 1/√(1 + 2s), y(s) = y√[(1 + 2S)/(1 + 2s)]. Ví dụ: S = 10 thì x(1) ≈ 0,577, x(5) ≈ 0,302, x(10) ≈ 0,218. Quan trọng vì đây là dạng liên tục của "X bỏ α mỗi vòng" và "Y bỏ dần bluff".

## Nội dung chi tiết

### 1. Mở đầu chương: trò chơi tĩnh (trang 243)

Các chương trước đã xét nhiều trò chơi nửa vòng và trọn vòng. Ưu điểm chính của chúng là tương đối dễ giải, và trò chơi giải được cho thấy tác động của việc thay đổi một chiều cụ thể của trò chơi. Nhưng poker thật hiếm khi chỉ có nửa vòng hay trọn vòng cược, và như chương này và chương sau sẽ cho thấy, thêm vòng cược làm thay đổi chiến lược về căn bản.

Tác giả bắt đầu với **trò chơi tĩnh**: có nhiều vòng cược, nhưng bài của không ai thay đổi giá trị. Các trò chơi này cho thấy bluff vận hành qua nhiều vòng như thế nào mà không phải xử lý sự phức tạp của draw. Sau vài trò chơi loại này, sách sẽ chuyển sang các trò chơi khó và thực tế hơn có draw (Chương 20). Trò chơi tĩnh hai vòng cơ bản nhất, tương ứng với cách xử lý trò chơi nửa vòng và trọn vòng, là trò chơi nhìn thấu bài.

### 2. Ví dụ 19.1 — Trò chơi nhìn thấu bài tĩnh hai vòng (Example 19.1 The Two-Street Static Clairvoyant Game, trang 243–246)

**Luật:** hai vòng cược trọn; giá trị bài tĩnh; pot P cược; cược limit (mỗi cược 1 đơn vị); Y nhìn thấu bài.

**X không bao giờ cược.** Trong trò chơi nhìn thấu một vòng, X không bao giờ cược vì cược đó không bao giờ có giá trị dương: Y nhìn thấu nên khai thác mọi cược của X với thông tin hoàn hảo. Ở đây cũng vậy: ở cả hai vòng, X chỉ check và call (hoặc bỏ), vì Y phản ứng chính xác tuyệt đối với mọi cược. Điều này đúng chỉ vì trò chơi tĩnh — Y đã biết giá trị bài cuối cùng của mình. Nếu có draw mà Y không biết kết quả, có thể có tình huống X nên cược.

**Nhắc lại trò chơi một vòng:** Y cược với mọi bài thắng và bluff với một tỷ lệ α của số bài thua (tính theo số bài thắng: bluff bằng α lần số bài giá trị); X đáp lại bằng cách bỏ α số bài và call với phần còn lại. Điều này đúng trừ khi Y có phân phối bài mạnh tới mức có thể cược mọi bài và X buộc phải bỏ.

**Lựa chọn của Y** trong trò chơi hai vòng:

- Check cả hai vòng (chiến lược Y₀).
- Check vòng đầu, cược vòng hai (chiến lược Y₁).
- Cược vòng đầu, check vòng hai (tương đương chiến lược Y₁).
- Cược cả hai vòng (chiến lược Y₂).

Rõ ràng Y muốn cược cả hai vòng với bài nuts (bài chắc thắng), vì như vậy lấy được nhiều giá trị nhất. Các bài dùng Y₁ và Y₀ là bài bluff hoặc bỏ cuộc, và một số bài dùng Y₂ cũng là bluff. Y sẽ chọn dạng thứ hai của Y₁ (cược vòng đầu rồi check vòng hai); dạng "check trước" dễ bị khai thác vì X biết Y không có nuts khi Y check ở vòng đầu.

**Lựa chọn của X** khi bị Y cược: bỏ ngay (X₀); call vòng đầu, bỏ vòng hai (X₁); call cả hai vòng (X₂). Chiến lược của X phải làm Y bàng quan giữa ba lựa chọn khi Y có bài chết.

**Ma trận kết quả (theo Y, ex-showdown):**

| | X₀ (bỏ ngay) | X₁ (call một lần) | X₂ (call hai lần) |
|---|---|---|---|
| **Y₀** (check cả hai) | 0 | 0 | 0 |
| **Y₁** (cược một lần rồi bỏ) | +P | −1 | −1 |
| **Y₂ (bluff)** | +P | +(P + 1) | −2 |
| **Y₂ (giá trị)** | 0 | +1 | +2 |

Giải thích: Y₁ là bluff một lần; X bỏ ngay thì Y lấy pot P; X call thì Y check vòng hai và thua khi lật bài, mất 1 cược. Y₂ bluff: nếu X call vòng một rồi bỏ vòng hai, Y lấy pot P cộng cược của X ở vòng một, tức +(P + 1); nếu X call cả hai, Y mất 2 cược. Y₂ với bài giá trị: thắng thêm số cược mà X call.

Gọi y_v và y_b là tỷ lệ bài giá trị và bài bluff trong số bài Y dùng Y₂; x₀, x₁, x₂ là tần suất X dùng ba chiến lược; y₀, y₁, y₂ là tần suất Y dùng ba chiến lược.

**Bàng quan giữa Y₁ và Y₀** (bài chết):

```text
0 = P·x₀ − x₁ − x₂
Vì x₁ + x₂ = 1 − x₀ (tổng tần suất bằng 1):
0 = P·x₀ − (1 − x₀)
x₀ = 1/(1 + P) = α
```

Vậy ở vòng đầu, X chơi đúng như trong trò chơi một vòng: bỏ α số bài, call phần còn lại.

**Bàng quan giữa Y₁ và Y₂ (bluff):**

```text
αP − x₁ − x₂ = αP + (P + 1)x₁ − 2x₂
x₂ = (P + 2)x₁
Vì x₁ + x₂ = 1 − α:
1 − α − x₁ = (P + 2)x₁
x₁ = (1 − α)/(P + 3) = α₂(1 − α),   với α₂ = 1/(P + 3)
```

Ở vòng hai, X cũng chơi rất giống trò chơi một vòng. Sau khi bỏ α số bài ở vòng đầu, X còn 1 − α số bài. Pot đã lớn thêm hai cược do vòng đầu (thành P + 2), nên ở vòng hai X bỏ α₂ = 1/((P + 2) + 1) số bài còn lại và call phần còn lại. Đây là một ý rất quan trọng:

> **Người không nhìn thấu chơi mỗi vòng một cách độc lập, như thể đó là một trò chơi một vòng.**

**Chiến lược của Y.** Y phải làm X bàng quan giữa ba chiến lược x₀, x₁, x₂. Bàng quan giữa X₀ và X₁ (so sánh tổng equity của Y theo từng cột):

```text
P·y₁ + P·y_b·y₂ = −y₁ + (P + 1)·y_b·y₂ + y_v·y₂
(P + 1)·y₁ = y_v·y₂ + y_b·y₂ = y₂        (vì y_v + y_b = 1)
y₁ = α·y₂
```

Đây là kết quả quan trọng thứ hai của trò chơi:

> **Số bài Y bluff một lần rồi bỏ có quan hệ tỷ lệ bluff α với tổng số bài Y sẽ cược (giá trị và bluff) ở vòng hai.**

Bàng quan giữa X₁ và X₂:

```text
−y₁ + (P + 1)·y_b·y₂ + y_v·y₂ = −y₁ − 2·y_b·y₂ + 2·y_v·y₂
y_v·y₂ = (P + 3)·y_b·y₂
y_b = α₂·y_v
```

Vậy ở vòng hai, Y cược giá trị và bluff theo tỷ lệ bluff thông thường trên số bài còn lại; ở đây tỷ lệ là α₂ vì pot lớn hơn hai cược.

**Tóm lại ý tưởng quan trọng này:** ở vòng cuối, Y có một tập bài cược giá trị và bluff phù hợp với kích thước pot lúc đó. Ở vòng trước, Y "giả vờ" rằng mọi bài đó là bài giá trị và bluff thêm phù hợp với kích thước pot hiện tại. Rồi ở vòng cuối, Y bỏ các "bluff" của vòng đầu và chỉ tiếp tục bluff trong số các "bài giá trị" đã mang theo.

**Ví dụ số:** điều này thường khiến Y bluff nhiều bài hơn so với trò chơi một vòng. Giả sử pot là 2 cược trước vòng đầu và Y chỉ có ít bài thắng (gọi số bài thắng là V).

- Ở river (vòng hai), pot sẽ là 4 cược (2 + 1 + 1). Y muốn cược giá trị mọi bài thắng và bluff thêm 1/5 số đó (α₂ = 1/(4 + 1)). Vậy Y "giả vờ" rằng V cộng V/5 bluff, tổng 6V/5, là bài giá trị.
- Ở vòng đầu, pot là 2 cược, nên Y muốn bluff thêm 1/3 (α = 1/(2 + 1)) số "bài giá trị": (6V/5)/3 = 2V/5. Tức là Y bluff với ý định bỏ cuộc với số bài bằng 2/5 số bài nuts.
- Tổng số bài chết Y cược ở vòng đầu là V/5 + 2V/5 = 3V/5.
- Y cược tất cả số bài này, bỏ 2/3 số bài chết (2V/5 trên 3V/5) sau vòng đầu, và tiếp tục với 1/3 số bài chết (V/5) cùng mọi bài giá trị ở vòng hai.

Minh hoạ của người tổng hợp: nếu Y thắng 20% số ván, Y cược 0,2 + 0,12 = 32% số bài ở vòng đầu và 0,2 + 0,04 = 24% ở vòng hai. Trong trò chơi một vòng với pot 2, Y chỉ cược 0,2 + 0,2/3 ≈ 26,7%.

Người chơi thứ hai không thể khai thác chiến lược này, vì như đã chứng minh, X bàng quan giữa call một lần, hai lần hay không lần nào.

### 3. Mở rộng: ba vòng cược với mức cược khác nhau (trang 246)

Kết quả này mở rộng cho số vòng bất kỳ và mức cược bất kỳ, với giới hạn thường lệ về độ mạnh của phân phối bài. Xét trò chơi:

- X và Y mỗi người bỏ ante 2 đơn vị (pot 4).
- Cả hai nhận bài, nhưng chỉ Y thấy cả hai tay bài.
- Toàn bộ bàn được chia nhưng chỉ Y thấy.
- Ba vòng cược: flop cược 1 đơn vị, turn và river cược 2 đơn vị.
- Nếu lật bài, bàn và hai tay bài được lật và so như thường lệ.

Ở trò chơi này, X cũng không cược có lời ở vòng nào; lời giải giống trò chơi hai vòng, chỉ thêm một vòng và mức cược khác. Giả sử Y thắng 1/2 số ván. Với bài thắng, Y cược ở mọi vòng; pot vào river sẽ là 4 + 2 + 4 = 10 đơn vị, cược 2.

```text
River: pot 10, cược 2 ⇒ α = 2/(10 + 2) = 1/6
  bài giá trị 1/2, bluff thêm (1/6)(1/2) = 1/12 (sách: "2/12 as many")
  tổng 1/2 + 1/12 = 7/12 số bài

Turn: pot 6 đơn vị, cược 2 ⇒ α = 2/(6 + 2) = 1/4
  "bài giá trị" 7/12, bluff thêm (1/4)(7/12) = 7/48
  tổng 28/48 + 7/48 = 35/48

Flop: pot 4, cược 1 ⇒ α = 1/(4 + 1) = 1/5
  "bài giá trị" 35/48, bluff thêm (1/5)(35/48) = 7/48
  tổng 35/48 + 7/48 = 42/48 = 7/8
```

Lời giải: Y cược 7/8 số bài ở flop; bỏ 7/48 số bài sau flop và 7/48 sau turn; bluff 1/12 số bài ở river (sách ghi nhầm "bỏ 1/12 sau flop", xem Lưu ý). X chỉ cần bỏ α số bài (của vòng đó) ở mỗi vòng.

Giá trị trò chơi dễ tìm bằng cách giả định X bỏ ngay (vì X bàng quan): Y lấy pot 4 với 7/8 số bài và mất pot với 1/8 số bài, nên Y lời 4 × 7/8 − 2 = 1,5 đơn vị mỗi ván (tức 3/8 pot). Tác giả bình luận: thật đáng kinh ngạc là X còn giữ được chút equity nào trong một trò chơi thiên lệch như vậy.

Sách nói kết quả mở rộng cho mọi mức cược. Trong trò chơi mà người nhìn thấu kiểm soát mức cược (như no-limit), có thể dùng kỹ thuật tối đa hoá của các chương trước để tìm mức cược tối ưu.

### 4. Ví dụ 19.2 — Trò chơi nhìn thấu bài tĩnh hai vòng, no-limit (Example 19.2 The Two-Street Static Clairvoyant No-Limit Game, trang 246–250)

**Luật:** hai vòng trọn; bài tĩnh; pot 1 đơn vị; no-limit (stack N đơn vị); Y nhìn thấu.

Trò chơi trước cho thấy người không nhìn thấu chơi mỗi vòng như trò chơi một vòng, bỏ α và call phần còn lại; tương tự, người nhìn thấu cược và bluff theo tỷ lệ α trên số bài mang qua từng vòng. Các quan hệ này vẫn đúng khi mức cược không cố định và do người nhìn thấu chọn. Vì vậy có thể viết equity của Y theo hai mức cược s₁, s₂ rồi tối đa hoá. Ma trận (pot 1):

| | X₀ | X₁ | X₂ |
|---|---|---|---|
| **Y₀** | 0 | 0 | 0 |
| **Y₁** | +1 | −s₁ | −s₁ |
| **Y₂ (bluff)** | +1 | +(1 + s₁) | −(s₁ + s₂) |
| **Y₂ (giá trị)** | 0 | +s₁ | +(s₁ + s₂) |

**Chiến lược của X** (cùng các phương trình bàng quan như trước):

```text
Y₀ và Y₁:  x₀ − s₁x₁ − s₁x₂ = 0  ⇒  x₀ = s₁(1 − x₀)  ⇒  x₀ = s₁/(1 + s₁) = α
```

X lại bỏ α số bài (nhắc lại α = s/(1 + s), cũng bằng 1/(P + 1) khi tính theo cược).

```text
Y₁ và Y₂ (bluff):
x₀ + (1 + s₁)x₁ − (s₁ + s₂)x₂ = x₀ − s₁x₁ − s₁x₂
(1 + 2s₁)x₁ = s₂x₂
x₂ = x₁(1 + 2s₁)/s₂
x₂ + x₁ = x₁(1 + 2s₁ + s₂)/s₂
```

Sau vòng đầu, pot là 1 + 2s₁ (pot ban đầu cộng một cược và một call). Vậy α₂ = s₂/(1 + 2s₁ + s₂). Thế vào:

```text
x₂ + x₁ = x₁/α₂     ⇒     x₁ = α₂(x₂ + x₁)
```

Đây là kết quả đã thấy: X chơi mỗi vòng như trò chơi một vòng; trong mọi bài đã call một cược (x₂ + x₁), X bỏ α₂ ở cược thứ hai.

**Chiến lược của Y** (cùng ma trận):

```text
X₀ và X₁:
y₁ + y₂y_b = −s₁y₁ + (1 + s₁)y₂y_b + s₁y₂y_v
(1 + s₁)y₁ = s₁y₂y_b + s₁y₂y_v = s₁y₂
y₁ = y₂·s₁/(1 + s₁) = α·y₂
```

Như trước, số bài Y bluff (rồi bỏ) bằng α lần số bài Y sẽ vừa bluff vừa cược giá trị ở river.

```text
X₁ và X₂:
−s₁y₁ + (1 + s₁)y₂y_b + s₁y₂y_v = −s₁y₁ − (s₁ + s₂)y₂y_b + (s₁ + s₂)y₂y_v
(1 + 2s₁ + s₂)y_b = s₂y_v
y_b = α₂·y_v
```

Ở river, tỷ lệ bluff chính là α₂. Vậy lời giải đúng với mọi mức cược (khi phân phối bài không quá mạnh). Để tìm s₁, s₂ đúng, ta tối đa hoá equity của Y theo hai mức cược.

**Tỷ số tăng pot.** Một cách đơn giản hoá giúp hiểu nguyên lý chọn mức cược tối ưu: giả sử Y cược s₁ vào pot 1. Nếu X call, pot ở vòng này tăng từ 1 lên 1 + 2s₁. Định nghĩa r₁ là tỷ số này. Tương tự, r₂ là tỷ số pot tăng nếu cược s₂ được call, từ 1 + 2s₁ lên 1 + 2s₁ + 2s₂, tức r₂ = (1 + 2s₁ + 2s₂)/(1 + 2s₁) (sách in ngược phân số). Tổng quát:

```text
rₙ = (pₙ + 2sₙ)/pₙ      (pₙ là pot vào vòng n)
```

(Chữ r này khác hằng số r = √2 − 1 ở các chương trước.) Khi lấy pot vào vòng làm đơn vị (pₙ = 1):

```text
r = 1 + 2s
r − s = 1 + s = (2 + 2s)/2 = (1 + r)/2
α = s/(1 + s) = s/(r − s)
```

**Số bài cược mỗi vòng.** Gọi Mₙ là số bài "giá trị" ở vòng n — nghĩa là các bài sẽ cược ở vòng sau, hoặc bài nuts nếu đây là vòng cuối. Số bài cược (bluff cộng giá trị) ở vòng n:

```text
Bₙ = sₙMₙ/(rₙ − sₙ) + Mₙ          (bluff bằng α lần Mₙ)
Bₙ = Mₙ(rₙ − sₙ + sₙ)/(rₙ − sₙ)
Bₙ = Mₙrₙ/(rₙ − sₙ)
Bₙ = 2Mₙrₙ/(1 + rₙ)
```

Đây là kết quả quan trọng: một "hệ số" áp cho từng vòng để tìm số bluff mỗi vòng. Với y là số bài thắng của Y:

```text
B₂ = 2y·r₂/(1 + r₂)
B₁ = 2B₂·r₁/(1 + r₁) = 4y·r₁r₂/[(1 + r₁)(1 + r₂)]
```

Tóm tắt: rₙ là tỷ số pot sau một cược và một call trên pot trước vòng đó; số bài cược mỗi vòng là Bₙ = 2Mₙrₙ/(1 + rₙ), với M là số bài mang sang vòng sau (nếu còn vòng) hoặc bài nuts (nếu là vòng cuối).

**Tối đa hoá.** Nếu Y cược s₁, s₂ với tần suất tối ưu, X bàng quan giữa call và bỏ ở mọi vòng. Vì vậy có thể giả định X bỏ ngay, tức là Y lấy pot với mọi bài bluff. (X thực ra không bỏ mọi bài mà call tối ưu.) Vì vậy Y muốn tối đa hoá tổng số tiền cược khi có bài nuts (và do đó cả khi bluff): s₁ + s₂ bằng hằng số N, nghĩa là Y cược hết stack trong hai vòng khi cược hai lần. Khi đó equity của Y được tính bằng cách giả định X bỏ; vì pot là 1 đơn vị, Y tối đa hoá giá trị bằng cách tối đa hoá tỷ lệ bài mình cược:

```text
B₁ = 4y·r₁r₂/[(1 + r₁)(1 + r₂)]
```

4y là hằng số, nên cần tối đa hoá r₁r₂/[(1 + r₁)(1 + r₂)]. Tích r₁r₂ là hằng số:

```text
r₁ = 1 + 2s₁
r₂ = (1 + 2s₁ + 2s₂)/(1 + 2s₁) = (1 + 2N)/(1 + 2s₁)
r₁r₂ = 1 + 2N
```

Vậy còn phải tối đa hoá 1/[(1 + r₁)(1 + r₂)]. Vì r₁, r₂ dương, chỉ cần cực tiểu mẫu số:

```text
(1 + r₁)(1 + r₂) = 1 + r₁ + r₂ + r₁r₂ = 2 + 2N + r₁ + r₂
```

Các hằng số không ảnh hưởng, nên cần cực tiểu r₁ + r₂ với ràng buộc r₁r₂ cố định. Bất đẳng thức trung bình cộng – trung bình nhân ((r₁ + r₂)/2 ≥ √(r₁r₂)) cho thấy biểu thức nhỏ nhất khi r₁ = r₂.

Minh hoạ của người tổng hợp: N = 4 (stack 4 lần pot), r₁r₂ = 9. Cược cấp số nhân r₁ = r₂ = 3 (cược bằng pot hai lần: 1 rồi 3) cho B₁ = 4y × 9/16 = 2,25y. Cược nửa pot rồi phần còn lại (s₁ = 0,5, s₂ = 3,5, r₁ = 2, r₂ = 4,5) cho B₁ = 4y × 9/(3 × 5,5) ≈ 2,18y — ít hơn.

Kết quả mở rộng cho nhiều vòng hơn. Với ba vòng, theo cùng lập luận, equity của Y tỷ lệ với:

```text
B₁ = 8y·r₁r₂r₃/[(1 + r₁)(1 + r₂)(1 + r₃)]
```

Tuy nhiên, nếu B₁ ≥ 1, điều đang xảy ra là Y không đủ bài bluff. Khi đó Y chỉ cần cược theo mức tăng pot (cấp số nhân) và X nên bỏ **mọi** bài. Rút gọn như trước, cần cực tiểu r₁ + r₂ + r₃ với ràng buộc r₁r₂r₃ cố định, đạt khi r₁ = r₂ = r₃. Kết quả này đúng cho số vòng bất kỳ.

Tác giả gọi cách cược này (tăng pot cùng một lượng tương đối mỗi vòng) là **tăng pot theo cấp số nhân** (geometric growth of pot). Kết quả này rất quan trọng cho hiểu biết về chọn mức cược no-limit; chương sau dùng nó làm một trong các nền tảng của toàn bộ hệ thống chọn mức cược trong no-limit hold'em. Khi trò chơi tĩnh và một người nhìn thấu, mức cược tối ưu là làm cho pot tăng cùng một tỷ lệ mỗi vòng, sao cho ở vòng cuối toàn bộ stack đã được cược.

### 5. Ví dụ 19.3 — Cược đều và cược cấp số nhân (Example 19.3, trang 250–252)

Ví dụ ngắn này đối chiếu chiến lược trên (trước một đối thủ tối ưu) với một chiến lược có vẻ hợp lý nhưng kém hơn hẳn.

**Luật:** X và Y bắt đầu với stack 185 đô la, mỗi người bỏ ante 5 đô la (pot 10 đô la, mỗi người còn 180 đô la). Y rút một lá từ bộ bài đầy đủ. Ba vòng cược no-limit. Nếu lật bài, Y thắng nếu lá là A hoặc K, thua trong mọi trường hợp khác.

Trò chơi này tương đương trò chơi nhìn thấu nói trên nhưng có ba vòng (Y biết lá của mình, X không có thông tin). Trước hết tính giá trị lật bài (nếu không có cược): Y thắng 8/52 = 2/13 số ván, nên được tổng cộng 10 × 2/13 ≈ 1,54 đô la mỗi ván, tức lỗ ròng 5 − 1,54 = 3,46 đô la. Để trò chơi có lời, Y phải bù 3,46 đô la bằng việc cược. Hai chiến lược chọn mức cược:

- **Y₁:** Y cược một phần ba stack mỗi vòng: 60 đô la mỗi vòng.
- **Y₂:** Y cược theo mức tăng pot cấp số nhân. Pot cuối là 10r₁r₂r₃ = 10r³ = 370 đô la, nên r là căn bậc ba của 37, khoảng 3,3322.

Ở mỗi vòng, pₙ + 2sₙ = r·pₙ:

```text
Vòng 1:  10 + 2s₁ = 10r          ⇒  s₁ ≈ 11,66 đô la
Vòng 2:  33,32 + 2s₂ = 33,32r    ⇒  s₂ ≈ 38,86 đô la
Vòng 3:  111,04 + 2s₃ = 111,04r  ⇒  s₃ ≈ 129,48 đô la
(tổng 11,66 + 38,86 + 129,48 = 180 đô la)
```

X chơi chiến lược tối ưu: call với tỷ lệ pₙ/(pₙ + sₙ) ở mỗi vòng (tức bỏ α = sₙ/(pₙ + sₙ)).

**Bảng: mức cược và tần suất X call**

| Vòng | Cược của Y (Y₁) | X call (trong vòng → cộng dồn) | Cược của Y (Y₂) | X call (trong vòng → cộng dồn) |
|---|---|---|---|---|
| 1 | 60 đô la | 10/70 = 14,29% | 11,66 đô la | 46,17% |
| 2 | 60 đô la | 130/190 = 68,42% → 9,77% | 38,86 đô la | 46,17% → 21,31% |
| 3 | 60 đô la | 250/310 = 80,6% → 7,88% | 129,48 đô la | 46,17% → 9,84% |
| Tổng tiền cược | 180 đô la | X call tới cuối 7,88% | 180 đô la | X call tới cuối 9,84% |

(Dòng "Total" của sách ghi "60 đô la, 7,88%" và "90 đô la, 4,06%"; bản tổng hợp thay bằng số nhất quán, xem Lưu ý.) Với Y₂, tỷ lệ call mỗi vòng là 1/(1 + s/p) = 1/(1 + (r − 1)/2) = 2/(1 + r) ≈ 0,4617, như nhau ở mọi vòng — đặc điểm của cược cấp số nhân.

Y hoà vốn trên các bluff — ở mỗi vòng Y bluff đúng tỷ lệ với số bài sẽ mang sang vòng sau. Vậy giá trị nằm ở bài thắng. Với mỗi bài thắng, Y được số tiền cược ở mỗi vòng nhân xác suất X vẫn còn call tới vòng đó:

```text
⟨Y₁⟩ = (14,29%)(60) + (9,77%)(60) + (7,88%)(60) ≈ 19,16 đô la
⟨Y₂⟩ = (46,17%)(11,66) + (21,31%)(38,86) + (9,84%)(129,48) ≈ 26,41 đô la
```

(sách in các thừa số của ⟨Y₂⟩ là 8,34; 22,26; 59,40 đô la — sai; người tổng hợp tính lại ra 26,40 đô la với các mức cược đúng.)

Vậy cược cấp số nhân lời hơn 7 đô la mỗi bài thắng. Tính theo mỗi ván, chênh lệch này đủ để đổi trò chơi từ âm (dùng Y₁) sang dương (dùng Y₂). Người tổng hợp tính: lợi nhuận ex-showdown mỗi ván bằng (2/13) × 19,16 ≈ 2,95 đô la với Y₁ và (2/13) × 26,41 ≈ 4,06 đô la với Y₂; trừ khoản lỗ lật bài 3,46 đô la, Y₁ lỗ khoảng 0,51 đô la mỗi ván còn Y₂ lời khoảng 0,60 đô la mỗi ván. Kiểm tra chéo bằng cách "cho X bỏ ngay": số bài Y cược ở vòng đầu là (2/13) × (2r/(1 + r))³ ≈ 0,560 với Y₂, nên Y được 10 × 0,560 − 5 ≈ +0,60 đô la; với Y₁ là (2/13) × (130/70)(250/190)(370/310) ≈ 0,449, nên Y được 10 × 0,449 − 5 ≈ −0,51 đô la.

Đáng chú ý: giới hạn của giá trị ex-showdown (dù còn bao nhiêu tiền để cược) phải bằng giá trị lật bài của X; nếu Y lấy được nhiều hơn, X chỉ việc bỏ ngay và mất 5 đô la ante.

**Hình 19.1 — Tăng pot cấp số nhân cho hai và ba vòng.** Trục hoành là stack (tính theo pot ban đầu, 0 tới 15), trục tung là tỷ số tăng r (1 tới 6). Đường hai vòng là r = √(1 + 2S), tới khoảng 5,57 ở S = 15; đường ba vòng là r = ∛(1 + 2S), tới khoảng 3,14 ở S = 15 (người tổng hợp tính từ công thức, khớp với hình). Khi r = 3 thì s = 1, tức cược bằng pot. Để cược bằng pot là tối ưu trong trường hợp ba vòng, stack phải bằng 13 lần pot ban đầu (1 + 2S = 27). Với stack 3,5 lần pot, cược nửa pot (r = 2) là đủ để đưa hết tiền vào theo cấp số nhân trong ba vòng (1 + 2S = 8); với hai vòng chỉ cần stack 1,5 lần pot.

### 6. Trò chơi đấu giá — trò chơi có vô số vòng cược (Auction Games (Games with Infinite Streets), trang 252–253)

Các trò chơi tĩnh cuối cùng của chương không hẳn giống poker; cấu trúc lời giải của chúng khá khác các trò chơi trước. Nhưng chúng cho ít nhất một nguyên lý quan trọng và có những tính chất thú vị riêng. Đây là các trò chơi có vô số vòng cược (hoặc số vòng lớn tuỳ ý). Tác giả gọi chúng là **trò chơi đấu giá** vì khi số vòng tiến ra vô hạn, chúng hội tụ về một loại trò chơi hoàn toàn khác.

### 7. Ví dụ 19.4 — Trò chơi nhìn thấu bài M vòng, no-limit (Example 19.4, trang 253–254)

**Luật:** M vòng trọn; bài tĩnh; pot ban đầu 1 đơn vị; no-limit, stack S đơn vị; Y nhìn thấu.

Mở rộng kết quả tăng pot cấp số nhân cho M vòng:

```text
Pot cuối (nếu mọi cược được call):  P = 1 + 2S      (pot hiện tại cộng cả hai stack)
Tỷ lệ tăng mỗi vòng:                 G = P^(1/M)     (căn bậc M của P)
Mức cược mỗi vòng (theo pot hiện tại): s = (G − 1)/2
```

Gọi pot ở vòng hiện tại là 1. Y cược đúng số bài giá trị y_v và bluff thêm s/(1 + s) lần số đó; tổng số bài cược là y_v(1 + 2s)/(1 + s). Vậy tỷ số giữa số bài cược ở vòng m và ở vòng m + 1 là:

```text
r_b = (1 + 2s)/(1 + s)        ("hệ số nhân bluff")
```

**Ví dụ:** trò chơi hai vòng, stack 1, pot 1. Tăng pot cấp số nhân nghĩa là pot từ 1 lên 3 qua hai vòng, nên tỷ lệ tăng mỗi vòng là √3 ≈ 1,732 và mức cược mỗi vòng là (√3 − 1)/2 ≈ 0,366 pot. Y có y bài giá trị; ở river, Y bluff s/(1 + s) ≈ 0,268 lần y. Vậy Y cược 1,268y bài ở river và (1,268)²y ≈ 1,608y bài ở vòng đầu. Thế s = 0,366 vào r_b cũng được r_b ≈ 1,268.

Gọi y là tổng số bài nuts của Y; yₘ là số bài Y cược ở vòng m + 1; y₀ là số bài Y cược ở vòng đầu; y_M = y là số bài giá trị còn lại sau M vòng. Sách viết yₘ = y₀·r_bᵐ, y_M = y₀·r_b^M = y, yₘ = y·r_b^(m − M), y₀ = y·r_b^(−M). Các số mũ này bị đổi dấu: vì r_b > 1 và số bài cược giảm dần qua các vòng (mỗi vòng bỏ một phần bluff), công thức đúng là (người tổng hợp sửa):

```text
yₘ = y₀·r_b^(−m)
y_M = y₀·r_b^(−M) = y
yₘ = y·r_b^(M − m)
y₀ = y·r_b^M        (số bài cược ở vòng đầu, lớn hơn y)
```

Kiểm tra bằng ví dụ trên (M = 2): y₀ = y·1,268² ≈ 1,608y ở vòng đầu, y₁ = 1,268y ở river, y₂ = y là số bài nuts. Chỉ với công thức đã sửa, điều kiện "y₀ > 1" và giá trị "y₀ − y" dưới đây mới có nghĩa.

Có thể gặp vấn đề: nếu số bài cược ở vòng đầu lớn hơn 1, Y không đủ bài bluff — thêm đủ bluff sẽ khiến Y cược nhiều bài hơn số bài mình có. Khi đó Y chỉ việc cược và lấy pot, và X nên bỏ một cách tối ưu.

Ngược lại, X call với tần suất thông thường 1/(1 + s) mỗi vòng. Gọi xₘ là số bài X call ở vòng m + 1:

```text
r_c = 1/(1 + s)
xₘ = r_cᵐ
```

Trong cả hai trường hợp, khi Y chơi tối ưu, X bàng quan giữa call và bỏ. Vậy giá trị trò chơi bằng (số bài cược vòng đầu) − y: Y lấy pot cho mỗi bài bluff ở vòng đầu. Ví dụ của người tổng hợp: trong ví dụ hai vòng trên với y = 0,3, Y cược 1,608 × 0,3 ≈ 0,482 số bài ở vòng đầu, nên giá trị trò chơi khoảng 0,182 pot.

### 8. Ví dụ 19.5 — Trò chơi đấu giá (Example 19.5 The Auction Game, trang 254–255)

**Luật:** bài tĩnh; pot ban đầu 1 đơn vị; stack S đơn vị. Mỗi người bỏ giá kín, hai giá được lật cùng lúc. Giá là sₓ và s_y, nằm trong [0, S]. Cả hai giá đều vào pot. Nếu sₓ > s_y thì X thắng; nếu s_y > sₓ thì Y thắng. Nếu s_y = sₓ thì lật bài (thường xảy ra khi cả hai cùng bỏ S).

Trò chơi này không giống poker lắm. Nhưng hãy trừu tượng một chút. Giả sử có một trò chơi poker với bài tĩnh và M vòng, và ta chơi một chiến lược lấy cảm hứng từ trò chơi đấu giá:

- Với mỗi tay bài có thể cầm, chọn một số sₓ là một phần của toàn bộ stack S.
- Ở mỗi vòng, cược một phần đều của stack còn lại, ε = S/M, cho tới khi đạt ngưỡng sₓ; sau đó chỉ check và bỏ cuộc. (ε là chữ Hy Lạp epsilon, chỉ một lượng rất nhỏ; ở đây ε tiến về 0 khi số vòng tăng.)
- Nếu đối thủ raise bất kỳ lượng nào: call nếu mức raise thấp hơn ngưỡng, rồi bắt đầu vòng sau bằng cách cược phần đều của stack còn lại chia cho số vòng còn lại; bỏ nếu mức raise cao hơn ngưỡng.

**Nemesis khai thác được bao nhiêu?** Để biết ngưỡng của ta, nemesis phải call các cược dẫn tới lúc ta check. Vì vậy nemesis không thể khai thác bằng cách call theo rồi bluff ta ra khỏi pot. Lợi ích duy nhất nemesis có là khi chiến lược buộc ta cược một lượng hơi lớn hơn sₓ. Ví dụ: 100 vòng, stack 1, sₓ = 0,601. Trong 60 vòng đầu ta cược 0,01 pot ban đầu mỗi vòng. Ở vòng 61, ta vẫn chưa đạt ngưỡng; không thể cược lượng nhỏ hơn mà không bị khai thác, nên ta lại cược 0,01, tổng cộng 0,61. Số này nhiều hơn mức ta thật sự muốn mạo hiểm 0,009, và trước gần như mọi tay bài còn lại tới lúc này, ta mất thêm 0,009 giá trị.

**Giá trị của raise đối với nemesis.** Giả sử ta cược ở một vòng, nâng tổng số đã cược lên x. Vì ta đã cược vòng này (chưa đạt ngưỡng khi mới cược x − ε), nemesis biết sₓ của ta lớn hơn x − ε (sách viết "nhỏ hơn", xem Lưu ý). Giả sử nemesis raise lên y đơn vị. Ba trường hợp:

- **sₓ < y:** ta bỏ. Nhưng nemesis lẽ ra đã kiếm được nhiều hơn (ít nhất sₓ − x) chỉ bằng cách call theo cho tới khi ta bỏ cuộc.
- **sₓ > y:** ta call. Nhưng sau raise, mức cược mỗi vòng của ta giảm: thay vì (S − x)/M_cur mỗi vòng cho đến hết (M_cur là số vòng còn lại), ta cược (S − y)/M_cur, một lượng nhỏ hơn. Vì nemesis chỉ lời được tối đa ε nhờ độ "thô" của mức cược, nemesis không muốn làm nó nhỏ đi.
- **sₓ = y:** ta call rồi check và bỏ cuộc ở các vòng sau. Nemesis không lời gì.

Trong mọi trường hợp, nemesis không lời gì bằng cách raise — thực ra nemesis nên chỉ call theo.

**Một cách nhìn khác:** xét hai người cùng chơi chiến lược này với nhau. Một kết quả của lý thuyết trò chơi: nếu có một cặp chiến lược (X, Y) và biết giá trị của nemesis của X và nemesis của Y, thì giá trị trò chơi phải nằm giữa hai giá trị đó — vì chiến lược tối ưu của X phải làm kém hơn nemesis của Y trước Y, và ngược lại. Vậy dùng cấu trúc cược này thay cho cấu trúc tối ưu chỉ mất tối đa ε so với giá trị trò chơi G (sách viết "nhiều nhất là G − ε", xem Lưu ý).

Khi số vòng M tiến ra vô hạn, ε tiến về 0 vì M ở mẫu số của ε = S/M. Vậy giá trị của mọi trò chơi (tĩnh) hội tụ về giá trị của trò chơi đấu giá tương ứng với các tham số của nó. Tương tự, với số vòng bất kỳ, chơi chiến lược đấu giá chỉ mất tối đa ε = S/M.

### 9. Ví dụ 19.6 — Trò chơi đấu giá nhìn thấu bài (Example 19.6, trang 255–258)

**Luật:** Y nhìn thấu; luật đấu giá với stack S và pot ban đầu 1.

Gọi y là số bài thắng của Y. Có ba loại tay bài: bài của X (tất cả như nhau vì X không có thông tin), và bài của Y gồm bài thắng và bài thua. Rõ ràng Y luôn bỏ giá s_y = S khi có bài thắng — Y luôn sẵn sàng cược cả stack khi chắc thắng pot. Gọi x(s) là tỷ lệ bài mà X bỏ giá ít nhất s, và y(s) là tỷ lệ bài mà Y bỏ giá ít nhất s. Chiến lược của Y: bỏ giá S với bài nuts, và chọn s_y cho bài bluff sao cho Y bỏ dần các bài bluff cho tới khi chỉ còn y(S) = y.

**Y bàng quan giữa hai mức giá s và s + Δs với bài chết** (Δs là một lượng thay đổi nhỏ của s). Người tổng hợp viết lại lập luận với dấu nhất quán: khi Y nâng giá từ s lên s + Δs, Y chỉ thay đổi kết quả khi giá của X nằm giữa s và s + Δs — xác suất x(s) − x(s + Δs) — và khi đó Y chuyển từ thua (mất s) sang thắng (lấy pot 1 cộng giá của X, khoảng s), tức lời khoảng 1 + 2s; ngược lại, khi X bỏ giá cao hơn s + Δs (xác suất x(s + Δs)), Y mất thêm Δs. Bàng quan:

```text
(1 + 2s)·[x(s) − x(s + Δs)] = Δs·x(s + Δs)
Khi Δs → 0:
−dx/x = ds/(1 + 2s)
Tích phân hai vế:
−ln x + C = ln(1 + 2s)/2
x = k/√(1 + 2s)
Vì x(0) = 1 (mọi bài đều bỏ giá ít nhất 0) nên k = 1:
x(s) = 1/√(1 + 2s)
```

**X bàng quan giữa s và s + Δs** (Y phải làm X bàng quan). Khi X nâng giá, X lời khoảng 1 + 2s khi giá của Y nằm giữa s và s + Δs (xác suất y(s) − y(s + Δs)), và mất thêm Δs khi Y bỏ giá cao hơn:

```text
(1 + 2s)·[y(s) − y(s + Δs)] = Δs·y(s + Δs)
Khi Δs → 0:
−dy/y = ds/(1 + 2s)
y(s) = k/√(1 + 2s)
Điều kiện y(S) = y (chỉ còn bài thắng bỏ giá S):
k = y·√(1 + 2S)
y(s) = y·√[(1 + 2S)/(1 + 2s)]
```

Cũng như trước, giá trị này có thể lớn hơn 1 (Y không đủ bài bluff). **Lời giải:**

```text
y(s) = y·√[(1 + 2S)/(1 + 2s)]   (hoặc 1, lấy số nhỏ hơn)
x(s) = 1/√(1 + 2s)              (hoặc 0 khi Y không đủ bài bluff, tức y(s) > 1)
```

Đây là tỷ lệ tổng số bài mà X và Y bỏ giá ít nhất s trong cuộc đấu giá (khi toàn bộ stack là S).

**Ví dụ:** stack 10, Y có bài thắng 50% số ván.

```text
y(1) = 0,5·√[(1 + 2·10)/(1 + 2·1)] = 0,5·√7 ≈ 1,323
```

Vì giá trị này lớn hơn 1, Y bỏ giá ít nhất 1 với mọi bài.

```text
y(5) = 0,5·√[(1 + 2·10)/(1 + 2·5)] = 0,5·√(21/11) ≈ 0,691
```

Ở đây Y bỏ giá ít nhất 5 với 0,5 số bài là bài thắng và 0,191 số bài là "bluff". Người tổng hợp tính thêm: mức giá mà Y bắt đầu bỏ dần bluff là nơi y(s) = 1, tức 1 + 2s = 0,25 × 21 = 5,25, s ≈ 2,125; phía X: x(1) = 1/√3 ≈ 0,577, x(5) = 1/√11 ≈ 0,302, x(10) = 1/√21 ≈ 0,218.

**Đây là giới hạn của trò chơi M vòng.** Có thể chứng minh lời giải này là giới hạn khi M → ∞ của trò chơi poker nhìn thấu M vòng. Bỏ qua trường hợp Y thiếu bluff, tập trung vào trường hợp thường gặp hơn khi cả hai bên dùng chiến lược hỗn hợp ở vòng đầu. Để tránh nhầm với các giá trị s, đặt sₙ = (G − 1)/2 là tỷ lệ cược mỗi vòng (Ví dụ 19.4). Dùng các xấp xỉ (với M lớn, G gần 1 nên G − 1 ≈ ln G):

```text
sₙ = (G − 1)/2 ≈ ln(G)/2 = ln P/(2M)
```

Từ lời giải trò chơi nhìn thấu (Ví dụ 19.4), xₘ = r_cᵐ:

```text
xₘ = (1 + sₙ)^(−m)
xₘ ≈ e^(−m·sₙ)
xₘ ≈ exp(−m·ln P/(2M))
xₘ ≈ P^(−m/(2M))
```

Pot sau m vòng (gọi tổng số mỗi người đã cược là s) là:

```text
1 + 2s = Gᵐ = P^(m/M)
```

Thế vào:

```text
xₘ = (1 + 2s)^(−1/2) = x(s)
```

Có thể chứng minh tương tự cho y(s): lời giải của trò chơi đấu giá chính là giới hạn khi M → ∞ của trò chơi nhìn thấu no-limit M vòng. Người tổng hợp kiểm tra phía Y: số bài cược ở vòng đầu y·r_b^M với r_b = (1 + 2sₙ)/(1 + sₙ) ≈ 1 + sₙ, nên r_b^M ≈ e^(M·sₙ) = P^(1/2) = √(1 + 2S), khớp với y(0) = y·√(1 + 2S).

### 10. Các khái niệm then chốt (Key Concepts, trang 258)

- Trò chơi nhìn thấu có thể mở rộng ra nhiều vòng. Đặc điểm then chốt của trò chơi nhiều vòng là người nhìn thấu mang một tập bài từ vòng này sang vòng khác, bluff nhiều bài hơn ở các vòng đầu và bỏ một phần các bài đó ở mỗi vòng.
- Trong trò chơi nhìn thấu no-limit nhiều vòng, mức cược tối ưu là tăng pot theo cấp số nhân — pot tăng cùng một tỷ lệ mỗi vòng.
- Khi số vòng tăng, giá trị vị trí tiến về 0 — trò chơi đấu giá đối xứng.
- Như trò chơi đấu giá (và tăng pot cấp số nhân) cho thấy, trong trò chơi tĩnh, cược những phần nhỏ của pot là tối ưu. Trò chơi không tĩnh không nhất thiết theo nguyên lý này.
- Chiến lược đấu giá gán cho mỗi tay bài một giá trị sₓ. Đây là cách nghĩ hợp lý về no-limit nói chung: có một phân phối bài, mỗi bài có một giá trị; mục tiêu là làm cho kích thước pot tương quan với sức mạnh bài.
- Người không nhìn thấu chơi mỗi vòng độc lập như thể đó là một trò chơi một vòng.
- Số bài Y bluff một lần rồi bỏ có quan hệ tỷ lệ bluff α với tổng số bài Y sẽ cược giá trị và bluff ở vòng hai.

## Luận điểm cốt lõi

### Mệnh đề

Trong trò chơi nhiều vòng cược với bài tĩnh, cấu trúc tối ưu được dựng ngược từ vòng cuối: người có thông tin bluff ở mỗi vòng theo tỷ lệ α của vòng đó trên tập bài sẽ cược ở vòng sau, còn người thiếu thông tin chơi từng vòng như trò chơi một vòng. Trong no-limit, mức cược tối ưu làm pot tăng cùng tỷ lệ mỗi vòng, và khi số vòng tiến ra vô hạn, trò chơi trở thành trò chơi đấu giá.

### Giả định

- Giá trị bài không đổi giữa các vòng (không draw).
- Một người nhìn thấu (biết chắc thắng thua), người kia không có thông tin riêng; trường hợp đấu giá tổng quát thì bài tĩnh nhưng không nhất thiết nhìn thấu.
- Phân phối bài của người nhìn thấu "không quá mạnh" (đủ bài bluff); nếu không, người kia bỏ hết.
- Stack hữu hạn S; trong no-limit, Y cược hết stack khi có bài nuts.

### Cơ chế

1. Viết ma trận các chiến lược thuần (bỏ ngay / call một lần / call hai lần; check / bluff một lần / cược hai lần).
2. Phương trình bàng quan của Y (bài chết) xác định tần suất bỏ của X ở từng vòng: α rồi α₂.
3. Phương trình bàng quan của X xác định số bài Y cược mỗi vòng: y₁ = αy₂, y_b = α₂y_v; tổng quát Bₙ = 2Mₙrₙ/(1 + rₙ).
4. Vì X bàng quan, giá trị của Y bằng pot nhân số bài bluff ở vòng đầu; tối đa hoá số bài cược vòng đầu với tích ∏rₙ cố định cho rₙ bằng nhau.
5. Khi số vòng tăng, mức cược mỗi vòng nhỏ dần; chiến lược "ngưỡng sₓ, cược đều ε" mất tối đa ε; giới hạn là trò chơi đấu giá, giải bằng phương trình vi phân −dx/x = ds/(1 + 2s).

### Bằng chứng và ví dụ tác giả đưa ra

- Ví dụ 19.1: x₀ = α, x₁ = α₂(1 − α), y₁ = αy₂, y_b = α₂y_v; pot 2 cược thì Y cược thêm 3/5 số bài thắng là bài chết ở vòng đầu.
- Trò chơi ba vòng (ante 2, cược 1 – 2 – 2): Y cược 7/12, 35/48, 7/8 số bài ở river, turn, flop; lời 1,5 đơn vị mỗi ván.
- Ví dụ 19.2: Bₙ = 2Mₙrₙ/(1 + rₙ), B₁ = 4y·r₁r₂/[(1 + r₁)(1 + r₂)], r₁r₂ = 1 + 2N, tối ưu r₁ = r₂.
- Ví dụ 19.3: cược 11,66 – 38,86 – 129,48 đô la lời 26,41 đô la mỗi bài thắng, so với 19,16 đô la khi cược 60 – 60 – 60 đô la.
- Hình 19.1: r = √(1 + 2S) và ∛(1 + 2S); cược bằng pot ba vòng cần stack 13 lần pot.
- Ví dụ 19.4: r_b = (1 + 2s)/(1 + s), ví dụ s ≈ 0,366, r_b ≈ 1,268.
- Ví dụ 19.5: 100 vòng, sₓ = 0,601, mất 0,009.
- Ví dụ 19.6: x(s) = 1/√(1 + 2s), y(s) = y√[(1 + 2S)/(1 + 2s)]; S = 10, y = 0,5: y(1) ≈ 1,323, y(5) ≈ 0,691.

### Kết luận và hàm ý cho người chơi

- Khi có lợi thế thông tin qua nhiều vòng, hãy bluff ở vòng đầu nhiều hơn mức của trò chơi một vòng, với kế hoạch bỏ dần các bluff đó; đừng bluff ở vòng đầu mà không có kế hoạch cho các vòng sau.
- Khi ở thế thiếu thông tin, chỉ cần bảo đảm ở mỗi vòng mình không bỏ quá tỷ lệ α của pot lúc đó.
- Trong no-limit, chọn mức cược sao cho stack vào hết pot ở vòng cuối với cùng tỷ lệ tăng pot mỗi vòng; cược đều theo số tiền (như 1/3 stack mỗi vòng) có thể làm mất nhiều giá trị.
- Nghĩ về mỗi tay bài như có một "mức sẵn sàng đặt" và làm cho kích thước pot tương quan với sức mạnh bài.

### Trong ngôn ngữ lý thuyết trò chơi

Trò chơi nhiều vòng tĩnh là trò chơi dạng mở rộng với thông tin không đối xứng một phía; cân bằng được tìm bằng quy nạp ngược trên các phương trình bàng quan. Tính chất "X chơi mỗi vòng độc lập" phản ánh việc X không có thông tin riêng nên chiến lược hành vi của X ở mỗi nút chỉ phụ thuộc kích thước pot. Bài toán chọn mức cược là cực đại hoá ∏rₙ/∏(1 + rₙ) với ràng buộc ∏rₙ = 1 + 2N, tương đương cực tiểu Σ ln(1 + rₙ) với Σ ln rₙ cố định; vì ln(1 + eᵘ) lồi theo u = ln r, nghiệm đối xứng (mọi rₙ bằng nhau) là tối ưu (bất đẳng thức Jensen, tổng quát hoá AM–GM). Trò chơi đấu giá là trò chơi liên tục (continuous game) với chiến lược hỗn hợp có hàm phân phối x(s), y(s) thoả phương trình vi phân bàng quan; việc giá trị trò chơi nằm giữa giá trị của hai nemesis là hệ quả của định lý minimax.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| static game | trò chơi tĩnh | nhiều vòng cược, giá trị bài không đổi |
| multi-street game | trò chơi nhiều vòng cược | có từ hai vòng cược trở lên |
| street | vòng cược | một lượt cược (flop, turn, river…) |
| half-street / full-street | half-street (nửa vòng) / full-street (trọn vòng) | chỉ một người được cược / cả hai được cược |
| clairvoyant game | trò chơi nhìn thấu bài | một người biết chắc thắng hay thua |
| clairvoyant player / non-clairvoyant player | người nhìn thấu / người không nhìn thấu | Y / X trong chương |
| dead hand | bài chết | bài chắc thua khi lật bài |
| nut hand / nuts | bài nuts | bài chắc thắng |
| value bet | value bet | cược với bài thắng để lấy giá trị |
| bluff | bluff | cược với bài thua để đối thủ bỏ |
| give up | bỏ cuộc (ngừng bluff) | check và chấp nhận thua ở vòng sau |
| carry forward | mang sang vòng sau | giữ một tập bài tiếp tục cược |
| bluffing ratio α | tỷ lệ bluff α | 1/(P + 1), hay s/(1 + s) |
| α₂ | hệ số α₂ | tỷ lệ bluff và tỷ lệ bỏ ở vòng thứ hai |
| indifference | bàng quan | các lựa chọn cho cùng kỳ vọng |
| pot | pot | tiền giữa bàn |
| ante | ante | tiền bắt buộc bỏ trước ván |
| stack | stack | số tiền còn lại trước mặt người chơi |
| limit / no-limit | limit / no-limit | mức cược cố định / mức cược tự chọn tới hết stack |
| bet / call / raise / fold / check | bet / call / raise / fold / check | cược / theo / tố thêm / bỏ bài / không cược |
| showdown | showdown (lật bài) | so bài cuối ván |
| flop / turn / river | flop / turn / river | ba vòng lá chung của hold'em |
| draw | draw | bài chờ lá để thành bài mạnh |
| ex-showdown | ex-showdown | không tính phần thắng do lật bài |
| pot growth ratio rₙ | tỷ số tăng pot rₙ | pot sau vòng n chia pot trước vòng n |
| geometric growth of pot | tăng pot theo cấp số nhân | pot tăng cùng tỷ lệ mỗi vòng, hết stack ở vòng cuối |
| arithmetic-geometric mean inequality | bất đẳng thức trung bình cộng – trung bình nhân | tổng nhỏ nhất khi các số có tích cố định bằng nhau |
| bluff multiplier r_b | hệ số nhân bluff | tỷ số số bài cược giữa hai vòng liên tiếp |
| not enough bluffs | không đủ bài bluff | phân phối quá mạnh, Y cược mọi bài, X bỏ |
| auction game | trò chơi đấu giá | hai người bỏ giá kín, giá cao hơn thắng pot |
| bid | giá bỏ | số tiền một người sẵn sàng đặt |
| threshold value sₓ | ngưỡng sₓ | mức tối đa sẵn sàng đặt với một tay bài |
| nemesis | nemesis | chiến lược trả đũa tối đa, biết chiến lược của ta |
| epsilon (ε) | epsilon | lượng rất nhỏ; ở đây S/M |
| positional value | giá trị vị trí | lợi thế của người hành động sau |
| difference equation / differential equation | phương trình sai phân / phương trình vi phân | quan hệ giữa các bước rời rạc / liên tục |
| optimal bet sizing | chọn mức cược tối ưu | chọn số tiền cược để tối đa hoá kỳ vọng |
| seventh street | seventh street | vòng cuối của stud |

## Câu nói đáng nhớ

> "Real poker is seldom played in half-street or full-street ways, and as we shall see in this chapter and the next, adding additional streets changes strategy in fundamental ways." — mở đầu chương
>
> *Dịch: Poker thật hiếm khi được chơi theo kiểu nửa vòng hay trọn vòng, và như ta sẽ thấy ở chương này và chương sau, thêm vòng cược làm thay đổi chiến lược về căn bản.*
>
> Ý nghĩa: lý do phải rời các mô hình một vòng.

> "The non-clairvoyant player plays each street independently as if it were a single street game." — Ví dụ 19.1
>
> *Dịch: Người không nhìn thấu chơi mỗi vòng độc lập, như thể đó là một trò chơi một vòng.*
>
> Ý nghĩa: quy tắc phòng thủ đơn giản cho người thiếu thông tin.

> "The hands that Y bluffs once and then gives up on have the α bluffing ratio relationship to the total hands that Y will bet for value and bluff on the second street." — Ví dụ 19.1
>
> *Dịch: Số bài Y bluff một lần rồi bỏ có quan hệ tỷ lệ bluff α với tổng số bài Y sẽ cược giá trị và bluff ở vòng hai.*
>
> Ý nghĩa: cách dựng tập bluff ngược từ vòng cuối.

> "On the preceding street, he 'pretends' that all those hands are value hands and bluffs appropriately to the current pot size." — Ví dụ 19.1
>
> *Dịch: Ở vòng trước, Y "giả vờ" rằng mọi bài đó là bài giá trị và bluff phù hợp với kích thước pot hiện tại.*
>
> Ý nghĩa: giải thích vì sao bluff ở vòng đầu nhiều hơn.

> "It's amazing that X can retain any equity at all in such a biased game." — trò chơi ba vòng
>
> *Dịch: Thật đáng kinh ngạc là X còn giữ được chút equity nào trong một trò chơi thiên lệch như vậy.*
>
> Ý nghĩa: nhắc rằng cân bằng vẫn bảo vệ người thiếu thông tin phần nào.

> "When the game is static and one player is clairvoyant, the optimal bet size is to make the pot grow by the same amount on each street, such that on the last street the entire stack has been bet." — Ví dụ 19.2
>
> *Dịch: Khi trò chơi tĩnh và một người nhìn thấu, mức cược tối ưu là làm pot tăng cùng một tỷ lệ mỗi vòng, sao cho ở vòng cuối toàn bộ stack đã được cược.*
>
> Ý nghĩa: phát biểu của nguyên lý tăng pot cấp số nhân.

> "Auction strategies assign a value sₓ to each hand… Then the goal is to correlate the pot size with our hand strength." — Key Concepts
>
> *Dịch: Chiến lược đấu giá gán cho mỗi tay bài một giá trị sₓ… Khi đó mục tiêu là làm cho kích thước pot tương quan với sức mạnh bài.*
>
> Ý nghĩa: cách nghĩ tổng quát về no-limit.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương này là cầu nối từ các mô hình đồ chơi sang poker thật, và cho hai kết quả có giá trị thực hành lớn. Thứ nhất, quy nạp ngược của bluff: bluff ở vòng đầu được "tài trợ" bởi tập bài sẽ cược ở vòng sau, nên người có lợi thế thông tin bluff nhiều hơn hẳn ở các vòng đầu (7/8 số bài ở flop khi chỉ thắng 1/2). Thứ hai, nguyên lý tăng pot cấp số nhân với chứng minh gọn bằng AM–GM, minh hoạ bằng một ví dụ có số đô la cụ thể cho thấy chọn sai mức cược có thể đổi một trò chơi có lời thành lỗ. Phần trò chơi đấu giá là một kết quả lý thuyết đẹp: giới hạn của vô số vòng cược là một trò chơi bỏ giá kín, và lời giải dạng 1/√(1 + 2s) khớp với giới hạn của lời giải rời rạc.

### Những chỗ đơn giản hoá

- **Bài tĩnh và nhìn thấu** là giả định rất mạnh: trong hold'em, bài thay đổi ở turn và river, và không ai biết chắc mình thắng. Tác giả biết điều đó và để Chương 20 xử lý; nhưng các con số như "bluff 7/8 số bài ở flop" không nên áp dụng trực tiếp.
- **X không bao giờ cược** chỉ đúng vì Y nhìn thấu và bài tĩnh.
- **Phần trò chơi đấu giá viết vội**: nhiều lỗi dấu và ký hiệu (xem Lưu ý), chỉ số yₘ đánh ngược chiều, và câu "giá trị vị trí tiến về 0" được nêu ở Key Concepts mà không chứng minh trong chương.
- **"Cược nhỏ so với pot là tối ưu trong trò chơi tĩnh"** dễ gây hiểu lầm: mức cược cấp số nhân phụ thuộc tỷ lệ stack/pot và số vòng; với stack sâu và ít vòng, cược lớn hơn pot (Ví dụ 19.3: khoảng 117% pot mỗi vòng).
- **Ví dụ 19.3 có lỗi in ở các thừa số và dòng tổng**, nhưng kết luận (cược cấp số nhân hơn cược đều) đúng khi tính lại.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp, không tra cứu)

- Khái niệm "geometric bet sizing" (cược để hết stack ở river với cùng tỷ lệ pot mỗi vòng) đã trở thành thuật ngữ chuẩn trong cộng đồng poker và trong các solver; nhiều công cụ có tuỳ chọn "geometric size" cho cây cược. Tuy vậy, solver cho thấy trong hold'em thật (bài không tĩnh, không ai nhìn thấu), mức cược tối ưu thường không đều: cược nhỏ trên bàn ít thay đổi, cược lớn (thậm chí overbet) khi phân phối bài phân cực.
- Ý tưởng "mang bluff qua nhiều vòng và bỏ dần" được solver xác nhận ở dạng định tính: tần suất bluff ở flop cao hơn ở turn và river, và các bluff bị bỏ dần.
- Trò chơi đấu giá và mô hình một tay bài có "mức sẵn sàng đặt" tương ứng với các mô hình đấu giá giá thứ nhất / chiến tranh tiêu hao (war of attrition) trong kinh tế học.

### Liên hệ các chương khác

- [C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md): trò chơi nhìn thấu một vòng, tỷ lệ α = 1/(P + 1).
- [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md): chọn mức cược no-limit cho một vòng; hằng số r = √2 − 1 (khác chữ r của chương này).
- [C17-tro-choi-01-pot-huu-han-va-bluff.md](C17-tro-choi-01-pot-huu-han-va-bluff.md): α₂ = 1/(P + 3) cho cược thứ hai.
- [C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md): giá trị trò chơi một vòng và lợi thế vị trí.
- [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md): trò chơi nhiều vòng có draw; tăng pot cấp số nhân làm nền cho hệ thống chọn mức cược no-limit hold'em.
- [C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md](C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md): áp dụng vào tình huống thật.
- [C24-tieu-chuan-kelly-va-chon-van-choi.md](C24-tieu-chuan-kelly-va-chon-van-choi.md): một chỗ khác trong sách mà tăng trưởng theo cấp số nhân đóng vai trò trung tâm (tăng trưởng vốn).

### Vận dụng

- **Người chơi poker:** khi có bài rất mạnh và còn nhiều vòng, tính trước mức cược mỗi vòng để stack vào hết pot ở river với tỷ lệ tăng pot đều: r = (1 + 2 × stack/pot)^(1/số vòng còn lại), mức cược = (r − 1)/2 lần pot. Ví dụ stack bằng 4 lần pot, hai vòng: r = 3, cược bằng pot ở cả hai vòng. Khi bluff ở vòng đầu, xác định trước bài nào sẽ tiếp tục ở vòng sau và bài nào sẽ bỏ; tổng số bài bluff ở mỗi vòng nên theo tỷ lệ α của pot lúc đó so với tập bài mang sang vòng sau. Khi ở thế phòng thủ, bảo đảm ở mỗi vòng không bỏ quá α = cược/(pot + cược).
- **Người làm tài chính và ra quyết định:** nguyên lý tăng pot cấp số nhân là một trường hợp của bài toán phân bổ theo tỷ lệ đều khi kết quả là tích của các hệ số tăng trưởng — giống như với lợi suất nhiều kỳ, cùng một tổng tăng trưởng được "chia đều" theo trung bình nhân cho kết quả tốt nhất khi mục tiêu là tối đa hoá một hàm của tích. Ý tưởng "mang bluff qua nhiều vòng và bỏ dần" tương ứng với chiến lược đàm phán hay đấu thầu nhiều vòng: đưa ra nhiều đề nghị mạnh ở vòng đầu và rút dần những đề nghị không có thực lực, sao cho đối phương không thể phân biệt. Trò chơi đấu giá là mô hình gần với chiến tranh tiêu hao (ai chịu "đốt tiền" lâu hơn thắng) trong cạnh tranh giữa doanh nghiệp: chiến lược hợp lý là gán trước cho mỗi tình huống một mức sẵn sàng chi và dừng đúng lúc, thay vì tăng chi theo cảm xúc.

# Chương 3 — Dùng hết thông tin: ước lượng tham số và định lý Bayes (Using All the Information: Estimating Parameters and Bayes' Theorem)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 3 "Using All the Information: Estimating Parameters and Bayes' Theorem", trang 37–48.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương 1 ([C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md)) đặt nền xác suất và kỳ vọng, trong đó có quy tắc nhân p(A ∩ B) = p(A) · p(B | A) (phương trình 1.5 của sách). Chương 2 ([C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md)) giả định đã biết trung bình và độ lệch chuẩn của kết quả mỗi tay bài, rồi dùng chúng để dự báo phân phối kết quả của nhiều tay (độ lệch chuẩn của N tay là σ√N). Chương 3 đi theo chiều ngược lại: từ kết quả quan sát được, suy ra **tham số chưa biết** — chủ yếu là win rate thật của một người chơi — bằng hai cách: thống kê cổ điển (ước lượng hợp lý cực đại, khoảng tin cậy) và thống kê Bayes (kết hợp thông tin có sẵn về phân phối win rate của mọi người chơi với dữ liệu mẫu). Định lý Bayes được giới thiệu ở đây là công cụ nền của Phần II "Chơi khai thác": Chương 4 ([C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md)) mở Phần II bằng pot odds, và Chương 5 ([C05-doc-bai-va-chien-luoc.md](C05-doc-bai-va-chien-luoc.md)) dùng suy luận Bayes để "đọc bài" (cập nhật phân phối tay bài của đối thủ theo hành động của họ). Phần IV về rủi ro phá sản, đặc biệt Chương 23 ([C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md)), quay lại đúng câu hỏi win rate bất định của chương này.
**Ý chính:** **Một mẫu kết quả poker, dù dài hàng chục nghìn tay, vẫn để lại rất nhiều bất định về win rate thật; muốn ước lượng tốt hơn, người chơi phải dùng hết mọi thông tin có sẵn, kể cả thông tin có từ trước khi quan sát (thông tin tiên nghiệm), và định lý Bayes là cách kết hợp hai nguồn thông tin đó.** Mục "Estimating Parameters: Classical Statistics" xét một người chơi limit đã chơi 16.900 tay, đạt win rate 1,15 big bet trên 100 tay (BB/100) với độ lệch chuẩn 2,1 BB mỗi tay. Nếu coi mọi win rate là có khả năng như nhau, ước lượng hợp lý cực đại của win rate thật chính là trung bình mẫu 1,15 BB/100. Nhưng độ lệch chuẩn của kết quả trên 16.900 tay, quy về 100 tay, là 2,1 × √16.900 / 169 ≈ 1,61 BB/100, lớn hơn chính win rate; khoảng tin cậy 95% là [−2,07; 4,37] BB/100, nên dữ liệu gần như không phân biệt được người này thắng 1,15 BB/100 hay hoà vốn. Mục "Bayes' theorem" rút ra công thức p(B | A) = p(A | B)p(B) / [p(A | B)p(B) + p(A | B̄)p(B̄)] và minh hoạ bằng ví dụ xét nghiệm y khoa: xét nghiệm phát hiện đúng 80% người bệnh, báo nhầm 10% người khoẻ, tỷ lệ mắc 5%, thì người có kết quả dương tính chỉ có khoảng 29,6% khả năng mắc bệnh. Trong poker, một người mới vào bàn được đánh giá tiên nghiệm 10% là "maniac" (raise 80% tay ở vị trí cutoff) và 90% là người chơi chặt (raise 10%); chỉ cần thấy họ raise tay đầu tiên, xác suất họ là maniac tăng lên 47,1%, và raise thêm tay thứ hai thì lên khoảng 87,7%. Mục "Estimating Parameters: Bayesian Statistics" dựng một phân phối tiên nghiệm rời rạc của win rate mọi người chơi (trung bình −1 BB/100, do rake), rồi tính lại cho người chơi 16.900 tay: win rate có xác suất hậu nghiệm cao nhất là −1 BB/100 (36,25%), hoà vốn 34,54%, và chỉ khoảng 21,9% khả năng người này thực sự thắng. Một người quan sát được 5 BB/100 bị "kéo về" mức +1 đến +2 BB/100; với 100.000 tay quan sát 1,15 BB/100, xác suất win rate +1 BB/100 lên 58,37%. Chương kết bằng hiện tượng hồi quy về trung bình: kết quả quan sát tốt hơn trung bình tổng thể có xu hướng đi kèm may mắn, nên dự báo tốt nhất là pha trộn kết quả quan sát với trung bình của mọi người chơi.

> **Lưu ý:**
> - **"Mức ý nghĩa 95%" là cách nói sai thuật ngữ (nhận xét của người tổng hợp):** sách viết "we choose a significance level of 95%" và định nghĩa khoảng tin cậy là tập các trung bình tổng thể "sao cho xác suất kết quả quan sát xảy ra *nhỏ hơn* mức ý nghĩa đã chọn". Trong thống kê chuẩn, mức ý nghĩa là 5% (xác suất sai mà ta chấp nhận), còn 95% là *mức tin cậy*; và khoảng tin cậy gồm các giá trị μ mà kết quả quan sát *không* rơi vào vùng có xác suất nhỏ hơn 5%. Phép tính của sách (μ ± 2σ) vẫn đúng với cách hiểu chuẩn. Ngay sau đó sách cũng viết "we can find a confidence level for our player" trong khi ý là "confidence interval". Phần Key Concepts lặp lại cách nói "observed result is inside the significance level".
> - **Hệ số 2 thay cho 1,96:** sách dùng μ ± 2σ cho mức 95%; chính xác thì ±2σ ứng với khoảng 95,45%, và ±1,96σ ứng với 95%. Với 1,96, khoảng là [−2,02; 4,32] BB/100 (người tổng hợp tính: 1,96 × 1,615 = 3,17).
> - **Sách viết "In Chapter 2, we stated the basic principle of probability (equation 1.5)":** theo cách đánh số, phương trình 1.5 thuộc Chương 1, không phải Chương 2.
> - **Câu diễn giải p(A) thiếu dấu gạch trên:** sách viết p(A) bằng "xác suất của A khi có B khi B xảy ra, cộng xác suất của A khi có B khi B xảy ra"; vế thứ hai phải là B̄ (B không xảy ra): p(A) = p(A | B)p(B) + p(A | B̄)p(B̄).
> - **Ví dụ xét nghiệm, hai lỗi in:** dòng đầu của danh sách dữ kiện ghi "p(B | A) = 0,8", phải là p(A | B) = 0,8 (xác suất dương tính khi có bệnh); câu "Of the 95,000 who have the condition" phải là "who do *not* have the condition" (95.000 người không mắc bệnh).
> - **"Nearly 87%":** sau hai lần raise, người tổng hợp tính được (0,8 × 0,8 × 0,1) / (0,64 × 0,1 + 0,01 × 0,9) = 0,064 / 0,073 ≈ 87,7%, tức "gần 88%" chính xác hơn "gần 87%".
> - **Bảng tính Bayes cho win rate, ba lỗi in (đã đối chiếu ảnh trang 46–47):** (1) tiêu đề hai cột p(B̄) và p(B) bị đổi chỗ: cột ghi "p(B̄)" thực ra chứa xác suất tiên nghiệm p(B) (0,25%, 2%, …), còn cột cuối ghi "p(B)" chứa 1 − p(B) (99,75%, 98%, …); (2) ba dòng win rate dương in là "- 1 BB/100", "- 2 BB/100", "- 3 BB/100" thay vì +1, +2, +3 (bảng tiên nghiệm ở trang 45 in đúng dấu +); (3) ba bảng kết quả có tiêu đề cột "p(A | B)" trong khi số trong cột là xác suất hậu nghiệm p(B | A).
> - **Mọi con số trong bảng Bayes đã được tính lại và khớp với sách**, kể cả hai trường hợp phụ: quan sát 5 BB/100 sau 16.900 tay, và quan sát 1,15 BB/100 sau 100.000 tay (sách không nói rõ trường hợp 100.000 tay giữ win rate quan sát 1,15; người tổng hợp kiểm tra và thấy đúng là 1,15, với độ lệch chuẩn 2,1 × √100.000 / 1.000 ≈ 0,664 BB/100).
> - **"Ước lượng hợp lý cực đại" trong phần Bayes:** sách gọi −1 BB/100 là "maximum likelihood estimate given these assumptions". Đúng thuật ngữ thì đây là *mode hậu nghiệm* (ước lượng hậu nghiệm cực đại, maximum a posteriori); ước lượng hợp lý cực đại thì vẫn là giá trị làm p(A | B) lớn nhất, tức +1 BB/100 trong lưới rời rạc này (cột p(A | B) lớn nhất là 0,004918 ở +1).
> - **Câu "nearly as likely to be a losing player who has gotten lucky as he is to have a positive win rate" nói nhẹ hơn số liệu (nhận xét của người tổng hợp):** cộng bảng hậu nghiệm, xác suất người chơi thua (win rate ≤ −1) là 0,00 + 0,03 + 0,66 + 6,65 + 36,25 = 43,59%, gấp đôi xác suất thắng (win rate ≥ +1) là 17,72 + 3,87 + 0,29 = 21,88%.
> - **Phân phối tiên nghiệm rời rạc hẹp hơn giả định liên tục:** sách giả định độ lệch chuẩn của win rate các người chơi là 0,015 BB/tay, tức 1,5 BB/100; bảng rời rạc mà sách dùng có trung bình đúng −1 BB/100 nhưng độ lệch chuẩn √1,48 ≈ 1,22 BB/100 (người tổng hợp tính).
> - **Hình 3.1 vẽ các đường chuẩn hẹp hơn σ = 1,61:** đỉnh các đường cao khoảng 0,32 (đọc từ trục), ứng với độ lệch chuẩn khoảng 1,25; một đường chuẩn với σ = 1,61 có đỉnh 1 / (1,61 √(2π)) ≈ 0,248. Hình chỉ có tính minh hoạ.
> - **Lớp chữ:** chỉ số dưới bị làm phẳng (σN là σ_N, σ16,900 là σ của 16.900 tay); dấu gạch trên của B̄ thường mất; "rumple mean" là lỗi của "sample mean"; "Bayer's theorem" là "Bayes' theorem"; "slayer" là "player"; "chat" là "that". Bản tổng hợp đã đọc lại các công thức và bảng từ ảnh trang.
> - **Quy ước:** "win rate" (tỷ lệ thắng, đo bằng big bet trên 100 tay, viết BB/100) được giữ tiếng Anh; "BB" trong chương này là big bet (mức cược lớn của limit poker), không phải big blind. Số thập phân dùng dấu phẩy cả trong công thức.

## Sơ đồ

### Phần mở đầu Chương 3 — từ "biết tham số, dự báo mẫu" sang "biết mẫu, ước lượng tham số" (trang 37)

```text
       Chương 2 giả định đã biết trung bình và phương sai của phân phối
       kết quả mỗi tay bài, rồi dự báo phân phối kết quả của nhiều tay
                                │
                                ▼
       Thực tế không biết các tham số đó
       · đồng xu, xúc xắc thật hơi lệch, nhưng mô hình 50-50 đủ dùng;
         trong poker ta giả định bộ bài công bằng
       · phân phối thắng/thua mỗi tay thì khó hơn nhiều: ghi chép ở
         casino tốn công; online dễ hơn nhờ lịch sử tay bài, nhưng dữ
         liệu vẫn chỉ là một MẪU
                                │
                                ▼
       Bài toán của chương: suy ra trung bình và phương sai của tổng thể
       từ trung bình và phương sai của mẫu
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       Cách 1: THỐNG KÊ CỔ ĐIỂN          Cách 2: THỐNG KÊ BAYES
       không có thông tin nào ngoài      giả định có một phân phối win
       mẫu về khả năng của từng          rate tồn tại ngoài mẫu, dùng
       win rate                          nó để tinh chỉnh ước lượng
```

### Mục "Estimating Parameters: Classical Statistics" — ước lượng hợp lý cực đại và khoảng tin cậy (trang 37–40)

```text
       Người chơi limit: 16.900 tay, win rate mẫu 1,15 BB/100,
       độ lệch chuẩn mẫu 2,1 BB mỗi tay; mọi win rate được coi là có
       khả năng như nhau
                                │
                                ▼
       Định lý Giới hạn Trung tâm: kết quả 16.900 tay xấp xỉ chuẩn
       Với mỗi giá trị μ, đường chuẩn có đỉnh tại μ; chiều cao của nó tại
       giá trị quan sát 1,15 đo "độ hợp lý" của μ
       · mọi đường cùng độ lệch chuẩn, chỉ tịnh tiến; cao nhất khi μ = 1,15
       → ƯỚC LƯỢNG HỢP LÝ CỰC ĐẠI = trung bình mẫu = 1,15 BB/100
                                │
                                ▼
       Độ bất định: σ của 16.900 tay = 2,1 × √16.900 = 2,1 × 130 = 273 BB
       quy về 100 tay: 273 / 169 ≈ 1,61 BB/100 (lớn hơn cả win rate)
       · nếu win rate thật đúng là 1,15, khoảng 32% mẫu 16.900 tay khác
         sẽ cho kết quả dưới −0,46 hoặc trên 2,76 BB/100
       · nếu win rate thật là 0, kết quả 1,15 vẫn nằm trong 1σ
                                │
                                ▼
       KHOẢNG TIN CẬY 95%: mọi μ thoả μ − 2σ < 1,15 < μ + 2σ
       · μ < 1,15 + 3,22 = 4,37 và μ > 1,15 − 3,22 = −2,07
       · khoảng [−2,07; 4,37] BB/100
                                │
                                ▼
       Cách hiểu đúng: KHÔNG phải "95% khả năng win rate thật nằm trong
       khoảng"; theo thống kê cổ điển, win rate thật cố định, hoặc nằm
       trong hoặc không. Khoảng gồm các giá trị μ mà nếu đúng thì kết quả
       quan sát nằm trong vùng xảy ra 95% số lần
                                │
                                ▼
       Thông tin tiên nghiệm bị bỏ qua: chơi 5.000 tay thắng 500 big bet
       (10 BB/100) thì ước lượng hợp lý cực đại là 10 BB/100, trong khi
       dữ liệu chung cho thấy người thắng nhiều nhất chỉ khoảng 3–4 BB/100
```

### Mục "Bayes' theorem" (phần 1) — công thức và ví dụ xét nghiệm y khoa (trang 40–43)

```text
       Quy tắc nhân (phương trình 1.5): p(A ∩ B) = p(A) p(B | A)
       Trong poker thường cần chiều ngược: biết A (bài của mình, hành động
       của đối thủ), muốn biết B (bài của đối thủ)
                                │
                                ▼
       ĐỊNH LÝ BAYES (3.1): p(B | A) = p(A ∩ B) / p(A)
       Tách p(A) = p(A | B)p(B) + p(A | B̄)p(B̄), được (3.2):
       p(B | A) = p(A | B)p(B) / [p(A | B)p(B) + p(A | B̄)p(B̄)]
                                │
                                ▼
       Xét nghiệm: đúng 80% người bệnh, báo nhầm 10% người khoẻ,
       5% dân số mắc bệnh. Dương tính thì khả năng mắc bệnh bao nhiêu?
       · trực giác "khoảng 80%" là sai (nhiều bác sĩ cũng sai)
       · 0,8 × 0,05 / (0,8 × 0,05 + 0,1 × 0,95) = 0,04 / 0,135 ≈ 29,63%
                                │
                                ▼
       Kiểm tra bằng 100.000 người:
       ┌──────────────┬───────────────┬───────────────┬────────────┐
       │              │ dương tính    │ âm tính       │ cộng       │
       ├──────────────┼───────────────┼───────────────┼────────────┤
       │ mắc bệnh     │ 4.000         │ 1.000         │ 5.000      │
       │ không mắc    │ 9.500         │ 85.500        │ 95.000     │
       │ cộng         │ 13.500        │ 86.500        │ 100.000    │
       └──────────────┴───────────────┴───────────────┴────────────┘
       4.000 / 13.500 ≈ 29,6%
                                │
                                ▼
       Xét nghiệm tốt hơn thì kết quả dương tính đáng tin hơn:
       · phát hiện 100% người bệnh: 0,05 / 0,145 ≈ 34,5%
       · giữ 80%, giảm báo nhầm còn 6%: 0,04 / 0,097 ≈ 41,2%
       Xác suất tiên nghiệm 5% + thông tin mới → xác suất hậu nghiệm:
       quá trình này là SUY LUẬN BAYES
```

### Mục "Bayes' theorem" (phần 2) — đánh giá đối thủ: người có stack lớn và người chơi "maniac" (trang 43–44)

```text
       Giải đấu: bàn bị giải tán sớm, chuyển sang bàn mới; người ngồi bên
       phải đã có stack gấp 7 lần stack khởi đầu
       · hai giả thuyết: rất loose và hung hãn, hay chơi bình thường nhưng
         cực kỳ may
       · trực giác nghiêng về "loose và hung hãn" chính là kết quả của
         định lý Bayes, dù người chơi có biết định lý hay không
                                │
                                ▼
       Định lượng: người mới vào bàn, theo mọi quan sát bề ngoài:
       · 10%: maniac, raise 80% tay ở vị trí cutoff
       · 90%: người chơi chặt, raise 10% tay ở vị trí đó
       Tay đầu tiên họ chơi: raise từ cutoff
                                │
                                ▼
       p(maniac | raise) = 0,8 × 0,1 / (0,8 × 0,1 + 0,1 × 0,9)
                         = 0,08 / 0,17 ≈ 47,1%
       · raise thêm tay thứ hai (cùng giả định cho ghế sát cutoff):
         khoảng 87,7% (sách: "gần 87%")
       · giới hạn: thực tế không chỉ có hai kiểu người chơi
                                │
                                ▼
       Hàm ý: chờ "thêm thông tin" rồi mới điều chỉnh là quá thụ động;
       tối đa hoá EV nghĩa là dùng ngay mọi thông tin đang có
       Cảnh báo: cách điều chỉnh nhanh này có thể bị khai thác bởi người
       cố tình chơi khác hẳn thói quen lúc mới vào bàn
```

### Mục "Estimating Parameters: Bayesian Statistics" — phân phối tiên nghiệm của win rate và ước lượng Bayes (trang 44–48)

```text
       Cùng người chơi 16.900 tay, 1,15 BB/100, độ lệch chuẩn 2,1 BB/tay
       Giả định họ được chọn ngẫu nhiên từ tổng thể người chơi thường xuyên
                                │
                                ▼
       PHÂN PHỐI TIÊN NGHIỆM của win rate:
       · rake khoảng 3–4 USD mỗi tay ở bàn 10–20 đến 30–60 USD, tức khoảng
         0,1 BB/tay; chia đều cho các người chơi: 0,01 BB/tay = 1 BB/100
       · trung bình win rate mọi người chơi là −1 BB/100 (tiền chảy ra
         khỏi bàn qua rake); độ lệch chuẩn khoảng 1,5 BB/100
       · rời rạc hoá: −5…+3 BB/100 với tỷ lệ 0,25 / 2 / 8 / 20 / 39,5 /
         20 / 8 / 2 / 0,25 %
                                │
                                ▼
       Với mỗi win rate r: p(A | B) = xác suất quan sát được kết quả
       trong khoảng 1,14–1,16 nếu win rate thật là r (σ = 1,61)
       Áp dụng (3.2) cho từng dòng → XÁC SUẤT HẬU NGHIỆM
                                │
                                ▼
       ┌───────────┬──────────────┬──────────────┬───────────────────┐
       │ win rate  │ 16.900 tay,  │ 16.900 tay,  │ 100.000 tay,      │
       │ (BB/100)  │ quan sát 1,15│ quan sát 5   │ quan sát 1,15     │
       ├───────────┼──────────────┼──────────────┼───────────────────┤
       │ −2        │ 6,65%        │ 0,16%        │ 0,00%             │
       │ −1        │ 36,25%       │ 3,79%        │ 1,57%             │
       │ 0         │ 34,54%       │ 15,78%       │ 33,42%            │
       │ +1        │ 17,72%       │ 35,40%       │ 58,37%            │
       │ +2        │ 3,87%        │ 33,84%       │ 6,60%             │
       │ +3        │ 0,29%        │ 11,03%       │ 0,04%             │
       └───────────┴──────────────┴──────────────┴───────────────────┘
       (các dòng −5, −4, −3 gần 0; bảng đầy đủ ở Nội dung chi tiết)
                                │
                                ▼
       · 1,15 BB/100 sau 16.900 tay: giá trị khả dĩ nhất là −1 BB/100;
         khả năng thua lớn hơn khả năng thắng
       · 5 BB/100: gần như chắc thắng, nhưng bị kéo về mức +1 đến +2,
         tức mức của 10% người chơi giỏi nhất
       · 100.000 tay: ước lượng hội tụ dần về kết quả quan sát
                                │
                                ▼
       Tranh luận: người theo tần suất (frequentist) coi tham số cố định;
       người theo Bayes coi tham số có phân phối xác suất. Tác giả nghiêng
       hẳn về Bayes vì hữu ích cho poker; phương pháp ở đây chỉ là bản
       đơn giản hoá
                                │
                                ▼
       HỒI QUY VỀ TRUNG BÌNH: ai vượt trung bình tổng thể thì nhiều khả
       năng cũng đã vượt kỳ vọng của chính mình (gặp may); dự báo tốt
       nhất pha một phần trung bình tổng thể vào kết quả quan sát.
       Không phải do may rủi "bù trừ" về sau: các tay bài độc lập
```

### Phần "Key Concepts" — các ý then chốt cuối chương (trang 48)

```text
       1. Ước lượng tham số tổng thể từ dữ liệu có hai cách: cổ điển (theo
          tần suất) hoặc Bayes
       2. Cách cổ điển giả định không có thông tin về phân phối nền: ước
          lượng hợp lý cực đại bằng trung bình mẫu, và khoảng tin cậy gồm
          mọi giá trị mà kết quả quan sát vẫn nằm trong vùng chấp nhận
       3. Quy tắc Bayes là phương pháp vững để đưa thông tin mới vào xác
          suất tiên nghiệm
       4. Dùng phân phối tiên nghiệm cùng định lý Bayes cho ước lượng tốt
          hơn, với điều kiện thông tin tiên nghiệm chính xác
```

## Ba câu hỏi chương này trả lời

1. **Từ kết quả của một người chơi, ta biết được gì về win rate thật của họ nếu không dùng thông tin nào khác?** Ước lượng tốt nhất là trung bình mẫu (ước lượng hợp lý cực đại), nhưng độ bất định rất lớn. Sau 16.900 tay với win rate 1,15 BB/100 và độ lệch chuẩn 2,1 BB mỗi tay, độ lệch chuẩn của kết quả quy về 100 tay là khoảng 1,61 BB/100, và khoảng tin cậy 95% là [−2,07; 4,37] BB/100: không phân biệt được người thắng vừa phải với người hoà vốn. Khoảng tin cậy không có nghĩa là "95% khả năng win rate nằm trong khoảng".
2. **Định lý Bayes là gì và dùng thế nào trong poker?** p(B | A) = p(A | B)p(B) / [p(A | B)p(B) + p(A | B̄)p(B̄)]: kết hợp xác suất tiên nghiệm p(B) với độ khớp của bằng chứng mới A. Xét nghiệm đúng 80%, báo nhầm 10%, tỷ lệ mắc 5% thì dương tính chỉ có 29,6% khả năng mắc bệnh. Một người được đánh giá 10% là maniac mà raise tay đầu tiên từ cutoff thì khả năng là maniac tăng lên 47,1%; raise hai tay liên tiếp thì khoảng 87,7%. Người chơi nên điều chỉnh ngay theo thông tin này, không chờ "xác nhận".
3. **Thêm thông tin tiên nghiệm về phân phối win rate thay đổi ước lượng ra sao?** Vì rake làm trung bình win rate của mọi người chơi khoảng −1 BB/100 và người thắng lớn rất hiếm, người chơi quan sát được 1,15 BB/100 sau 16.900 tay có win rate khả dĩ nhất là −1 BB/100 (36,25%), và chỉ khoảng 22% khả năng thực sự thắng. Kết quả 5 BB/100 bị kéo về +1 đến +2 BB/100. Càng nhiều dữ liệu, ước lượng càng tiến về kết quả quan sát (100.000 tay: 58,37% ở +1 BB/100). Đây là cơ chế của hồi quy về trung bình.

## Khái niệm cần biết

- **Tham số tổng thể và thống kê mẫu (population parameter, sample statistic):** tham số là giá trị thật nhưng chưa biết của phân phối nền (trung bình μ, độ lệch chuẩn σ); thống kê mẫu là con số tính từ dữ liệu quan sát (trung bình mẫu x̄, độ lệch chuẩn mẫu s). Ví dụ: x̄ = 1,15 BB/100 và s = 2,1 BB/tay của người chơi 16.900 tay; μ là win rate thật của người đó. Quan trọng vì toàn chương là bài toán đi từ x̄, s về μ.
- **Win rate:** số tiền thắng trung bình, ở đây đo bằng big bet trên 100 tay (BB/100). Ví dụ: thắng 500 big bet trong 5.000 tay là 10 BB/100. Quan trọng vì đây là tham số mà người chơi poker muốn biết nhất về bản thân và đối thủ.
- **Ước lượng hợp lý cực đại (maximum likelihood estimate):** giá trị tham số làm cho dữ liệu quan sát được có khả năng xảy ra cao nhất. Ví dụ: với mọi win rate được coi là như nhau, đường chuẩn có đỉnh đúng tại 1,15 khi μ = 1,15, nên ước lượng hợp lý cực đại là 1,15 BB/100. Quan trọng vì đây là "ước lượng một con số" của thống kê cổ điển.
- **Khoảng tin cậy (confidence interval) và mức ý nghĩa (significance level):** khoảng tin cậy 95% là tập mọi giá trị tham số mà nếu chúng đúng thì kết quả quan sát vẫn nằm trong vùng xảy ra 95% số lần; mức ý nghĩa là xác suất sai được chấp nhận (chuẩn là 5%; sách gọi lẫn là 95%). Ví dụ: [−2,07; 4,37] BB/100. Quan trọng vì nó cho thấy dữ liệu poker để lại bất định rất rộng.
- **Xác suất có điều kiện (conditional probability):** p(B | A) là xác suất B xảy ra khi biết A đã xảy ra. Ví dụ: p(dương tính | mắc bệnh) = 0,8 nhưng p(mắc bệnh | dương tính) ≈ 0,296. Quan trọng vì nhầm hai chiều này là lỗi phổ biến nhất khi suy luận.
- **Định lý Bayes (Bayes' theorem):** p(B | A) = p(A | B)p(B) / [p(A | B)p(B) + p(A | B̄)p(B̄)], với B̄ là "B không xảy ra". Ví dụ: 0,8 × 0,1 / (0,8 × 0,1 + 0,1 × 0,9) = 47,1% cho câu hỏi "người raise có phải maniac không". Quan trọng vì đây là cơ chế toán học của việc đọc bài và chơi khai thác ở Phần II.
- **Xác suất tiên nghiệm và hậu nghiệm (prior / a priori, posterior):** tiên nghiệm là xác suất ta gán trước khi thấy bằng chứng mới; hậu nghiệm là xác suất sau khi cập nhật. Ví dụ: 10% là maniac (tiên nghiệm), 47,1% sau khi thấy raise (hậu nghiệm). Quan trọng vì chất lượng kết luận phụ thuộc trực tiếp vào tiên nghiệm.
- **Suy luận Bayes (Bayesian inference):** quá trình bắt đầu từ xác suất tiên nghiệm, quan sát thông tin mới, rồi điều chỉnh xác suất. Ví dụ: tỷ lệ mắc bệnh 5% thành 29,6% sau kết quả dương tính. Quan trọng vì tác giả gọi nó là "trái tim của việc đọc bài và chơi khai thác".
- **Phân phối xác suất tiên nghiệm (prior probability distribution):** phân phối của tham số trước khi xem dữ liệu của người cụ thể. Ví dụ: win rate của mọi người chơi tập trung ở −1 BB/100 (39,5%), chỉ 10,25% người chơi thắng từ +1 BB/100 trở lên. Quan trọng vì nó "kéo" các ước lượng bất thường về mức hợp lý.
- **Rake:** phần tiền sòng bài hoặc phòng chơi thu từ mỗi pot. Ví dụ: 3–4 USD mỗi tay, khoảng 0,1 BB/tay, làm trung bình win rate của mọi người chơi là −1 BB/100. Quan trọng vì rake làm cho poker là trò chơi có tổng âm đối với người chơi, nên người thắng là thiểu số.
- **Người theo tần suất và người theo Bayes (frequentist, Bayesian):** người theo tần suất coi tham số là cố định, chỉ nói về xác suất của dữ liệu; người theo Bayes coi tham số có phân phối xác suất và cập nhật nó theo dữ liệu. Ví dụ: người theo tần suất nói "win rate thật hoặc nằm trong khoảng hoặc không". Quan trọng vì tác giả chọn quan điểm Bayes cho cả cuốn sách.
- **Hồi quy về trung bình (regression to the mean):** kết quả quan sát cao hơn trung bình tổng thể thường giảm bớt khi quan sát lại, và kết quả thấp thường tăng lên, vì một phần độ lệch là do may rủi. Ví dụ: người quan sát 5 BB/100 có win rate kỳ vọng hậu nghiệm khoảng 1,32 BB/100 (người tổng hợp tính). Quan trọng vì nó giải thích vì sao không nên tin ngay vào chuỗi thắng ngắn.

## Nội dung chi tiết

### 1. Phần mở đầu: từ tham số đã biết sang tham số phải ước lượng (trang 37)

Chương trước mô tả các tính chất thống kê của phân phối xác suất có giá trị và quan hệ giữa các mẫu lấy từ phân phối với phân phối chuẩn, nhưng luôn giả định đã biết tham số của phân phối nền. Thực tế ta thường không biết. Ngay cả đồng xu cũng hơi lệch về một phía, và xúc xắc có những khiếm khuyết nhỏ làm một mặt dễ xuất hiện hơn; nhưng các hiệu ứng này nhỏ, nên dùng đồng xu "lý thuyết" 50-50 là xấp xỉ hợp lý. Tương tự, khi phân tích poker, tác giả giả định bộ bài công bằng và mỗi lá bài là ngẫu nhiên cho tới khi được nhìn thấy.

Có những phân phối khó hơn nhiều. Khi phân tích kết quả poker, ta thường quan tâm tới phân phối thắng/thua của từng tay. Ở casino, ghi lại kết quả mọi tay vừa khó vừa tốn thời gian (và có thể gây chú ý không mong muốn). Online thì dễ hơn vì có lịch sử tay bài tải về và phần mềm tự động hoá. Nhưng dù có toàn bộ dữ liệu, đó vẫn chỉ là một mẫu; xác suất của phân phối nền chỉ hiện ra trong dữ liệu khi lượng dữ liệu thật lớn.

Nếu có được trung bình và phương sai của phân phối kết quả mỗi tay, ta có thể tìm phân phối lấy mẫu và dự báo phân phối của tổng kết quả sau một số tay nào đó (đây là nội dung Chương 2). Ta không dự báo được kết quả cụ thể của một mẫu tương lai, nhưng dự báo được phân phối của nó. Bài toán của chương này là suy ra trung bình và phương sai của tổng thể từ trung bình và phương sai của mẫu, theo hai cách:

1. **Thống kê cổ điển:** giả định không có thông tin nào ngoài mẫu về khả năng của từng win rate.
2. **Cách dùng định lý Bayes:** giả định có một phân phối win rate tồn tại bên ngoài mẫu, và dùng nó để tinh chỉnh ước lượng trung bình và phương sai của tổng thể.

### 2. Ước lượng tham số theo thống kê cổ điển (Estimating Parameters: Classical Statistics, trang 37–40)

#### Dữ liệu

Một người chơi đã chơi tổng cộng 16.900 tay limit poker. Để gộp được các mức cược khác nhau, kết quả được quy về big bet (BB). Người này đạt win rate x̄ = 1,15 BB/100 tay, với độ lệch chuẩn s = 2,1 BB mỗi tay. Ở đây dùng x̄ và s (tham số của mẫu) thay cho μ và σ (tham số của tổng thể). Giả sử người này sẽ tiếp tục chơi các ván tương tự với đối thủ tương tự; ta nói được gì về win rate "thật" μ? Mục này giả định không có thông tin nào khác về khả năng của các win rate: mọi win rate từ −1 BB/tay tới +1 BB/tay (tức −100 tới +100 BB/100) được coi là có khả năng như nhau.

#### Ước lượng hợp lý cực đại

Vì chỉ có một mẫu, sẽ luôn có bất định về win rate. Nhưng theo Định lý Giới hạn Trung tâm, phân phối lấy mẫu của 16.900 tay limit poker xấp xỉ chuẩn. Độ lệch chuẩn quan sát s = 2,1 BB/tay là ước lượng hợp lý của độ lệch chuẩn tổng thể, nhất là khi mẫu tương đối lớn.

Xét mọi win rate có thể. Với mỗi μ có một phân phối lấy mẫu tương ứng, là đường chuẩn với trung bình μ và độ lệch chuẩn σ_N; đỉnh của nó ở x = μ, mọi điểm khác đều thấp hơn. Tạm giả sử trung bình tổng thể là một μ cụ thể; chiều cao của đường tại x = x̄ gắn với xác suất trung bình mẫu quan sát được là kết quả của mẫu đó. Làm như vậy cho mọi μ. Vì mọi đường chuẩn có cùng σ_N, chúng giống hệt nhau, chỉ tịnh tiến dọc trục hoành.

Hình 3.1 của sách ("Shifted normal distributions", các điểm được đánh dấu tại x = 1,15) vẽ ba đường chuẩn giống nhau trên trục hoành từ −3 tới 5, trục tung từ 0 tới 0,35 (số đọc từ trục là ước lượng):

| Đường | Tâm (μ) | Chiều cao tại x = 1,15 |
|---|---|---|
| đường đậm màu xám | khoảng 0 | khoảng 0,245 |
| đường mảnh liền nét | 1,15 | khoảng 0,32 (đúng đỉnh) |
| đường chấm | khoảng 2,6 | khoảng 0,21 |

Đường có tâm đúng tại 1,15 cho chiều cao lớn nhất tại điểm quan sát. Vì đỉnh của đường là điểm cao nhất, và giá trị quan sát x̄ là đỉnh khi μ = x̄, nên **x̄ = 1,15 BB/100 là ước lượng hợp lý cực đại** của trung bình. Điều này có vẻ hiển nhiên, nhưng phần Bayes sẽ cho thấy khi thêm thông tin, ước lượng tốt nhất không nhất thiết bằng trung bình mẫu.

#### Độ lệch chuẩn của mẫu 16.900 tay

Biết win rate khả dĩ nhất là trung bình mẫu chưa nói gì về bất định; người chơi có thể đã may hoặc rủi. Giả sử mẫu N gồm 16.900 tay lấy từ phân phối có trung bình 1,15 BB/100 và độ lệch chuẩn 2,1 BB/tay. Theo phương trình 2.4 (độ lệch chuẩn của tổng N lần thử độc lập là σ√N):

- σ_N = σ√N
- σ_16.900 = (2,1 BB/tay) × √16.900 = 2,1 × 130 = 273 BB
- Quy về 100 tay (16.900 tay là 169 lần 100 tay): σ_N / 100 tay = 273 / 169 ≈ 1,61 BB/100.

Độ lệch chuẩn của một mẫu cỡ này lớn hơn cả win rate. Nếu tham số thật đúng bằng tham số quan sát, thì khi lấy một mẫu 16.900 tay khác, khoảng 32% số lần kết quả sẽ thấp hơn 1,15 − 1,61 = −0,46 BB/100 hoặc cao hơn 1,15 + 1,61 = 2,76 BB/100 (xác suất nằm ngoài ±1 độ lệch chuẩn của phân phối chuẩn là 31,7%).

Điều này đáng lo: làm sao tin rằng mẫu đại diện cho trung bình thật, khi ngay cả nếu nó đúng, một mẫu khác vẫn rơi ra ngoài khoảng khá rộng ấy 32% số lần? Và nếu trung bình thật là 0 thì sao? Khi đó 1,15 nằm gọn trong khoảng một độ lệch chuẩn. Dựa trên mẫu này, ta không phân biệt rõ được win rate 0 với win rate 1,15 BB/100.

#### Khoảng tin cậy

Để nắm bắt bất định, ta dựng **khoảng tin cậy**. Trước hết phải chọn một mức chịu đựng sai số. Vì đây là quá trình ngẫu nhiên, ta không thể nói xác suất trung bình tổng thể có một giá trị nào đó bằng 0 — có thể ta đã cực kỳ may hoặc cực kỳ rủi. Nhưng ta có thể chọn **mức ý nghĩa**, một giá trị xác suất thể hiện mức chịu đựng sai số. Khoảng tin cậy khi đó trả lời câu hỏi: "những giá trị trung bình tổng thể nào làm cho kết quả quan sát không rơi vào vùng có xác suất nhỏ hơn mức đã chọn?" (sách diễn đạt câu này lộn và gọi mức là "significance level 95%"; xem khối Lưu ý).

Với mức 95%: nếu trung bình tổng thể là μ, một mẫu cỡ này sẽ nằm giữa μ − 2σ và μ + 2σ khoảng 95% số lần. Vậy ta tìm mọi μ sao cho giá trị quan sát x̄ = 1,15 nằm giữa hai biên đó, với σ = 1,61 BB/100 như đã tính:

- Điều kiện 1: μ − 2σ < 1,15, tức μ − 2 × 1,61 < 1,15, nên μ < 1,15 + 3,22 = 4,37.
- Điều kiện 2: μ + 2σ > 1,15, tức μ + 2 × 1,61 > 1,15, nên μ > 1,15 − 3,22 = −2,07.

**Khoảng tin cậy 95% cho win rate của người chơi này, dựa trên mẫu 16.900 tay, là [−2,07 BB/100; 4,37 BB/100].** (Nếu dùng hệ số chính xác 1,96 thay cho 2, khoảng là [−2,02; 4,32].)

Điều này **không** có nghĩa là win rate thật có 95% khả năng nằm trong khoảng — một hiểu lầm phổ biến. Khoảng tin cậy là tập mọi giá trị mà nếu chúng là win rate thật thì win rate quan sát sẽ nằm trong vùng giá trị xảy ra 95% số lần. Thống kê cổ điển không gán xác suất cho giá trị của tham số; theo quan điểm cổ điển, win rate thật hoặc nằm trong khoảng hoặc không, vì nó không phải kết quả của một sự kiện ngẫu nhiên. Không lượng dữ liệu nào làm ta chắc hay không chắc về giá trị của tham số; ta chỉ có thể nói về khả năng quan sát được một kết quả nếu tham số có một giá trị cụ thể.

Ước lượng hợp lý cực đại và khoảng tin cậy là công cụ hữu ích để biết một mẫu cho ta bao nhiêu thông tin. Ở đây, dù 1,15 BB/100 trông hợp lý, kết luận rằng nó gần với win rate thật là vội vàng; khoảng tin cậy cho thấy phạm vi các win rate tổng thể có thể rộng đến đâu. Nhưng nếu buộc phải chọn một con số, ước lượng tốt nhất (theo cách cổ điển) vẫn là ước lượng hợp lý cực đại, tức trung bình mẫu 1,15 BB/100.

#### Thông tin tiên nghiệm

Tới đây ta giả định không có thông tin nào về khả năng của các win rate, tức dữ liệu thí nghiệm là nguồn duy nhất. Thực ra, ngay trước khi đo, có win rate khả dĩ hơn win rate khác. Giả sử bạn chơi 5.000 tay ở casino và thắng 500 big bet, tức 10 BB/100. Ước lượng hợp lý cực đại sẽ đúng là 10 BB/100. Nhưng ta có nhiều bằng chứng, cả kinh nghiệm truyền miệng lẫn cơ sở dữ liệu lịch sử tay bài, cho thấy trong số những người chơi đủ nhiều tay để có ý nghĩa thống kê, win rate cao nhất vào khoảng 3–4 BB/100; ngay cả vài trường hợp ngoại lệ cao hơn cũng không tới gần 10 BB/100. Thông tin có từ trước khi đo như vậy gọi là **thông tin tiên nghiệm** (a priori).

Nếu coi người chơi được đo là chọn ngẫu nhiên từ toàn bộ người chơi poker, thì win rate của họ có một phân phối xác suất. Ta không biết chính xác hình dạng phân phối này vì không có dữ liệu của mọi người chơi; nhưng nếu giả định đúng về phân phối tiên nghiệm, ta có thể kết hợp hai nguồn bằng chứng để ước lượng tốt hơn.

### 3. Định lý Bayes và ví dụ xét nghiệm y khoa (Bayes' theorem, trang 40–43)

#### Rút ra công thức

Quy tắc nhân của xác suất (phương trình 1.5): p(A ∩ B) = p(A) · p(B | A). Dạng này cho xác suất đồng thời của A và B từ xác suất của A và xác suất có điều kiện của B khi có A. Nhưng trong poker, ta thường cần xác suất có điều kiện của B khi A đã xảy ra — chẳng hạn biết bài của mình (A), muốn biết thông tin đó ảnh hưởng thế nào tới bài của đối thủ (B). Sắp xếp lại phương trình 1.5 được công thức mà sách gọi là **định lý Bayes**:

$$p(B \mid A) = \frac{p(A \cap B)}{p(A)} \qquad (3.1)$$

Nhắc lại từ Chương 1: B̄ là phần bù của B, p(B̄) = 1 − p(B), tức p(B) + p(B̄) = 1. Vì B và B̄ có tổng xác suất bằng 1, p(A) tách được thành xác suất của A khi B xảy ra cộng xác suất của A khi B̄ xảy ra: p(A) = p(A | B)p(B) + p(A | B̄)p(B̄). Thay vào tử số p(A ∩ B) = p(A | B)p(B), ta viết lại (3.1) thành:

$$p(B \mid A) = \frac{p(A \mid B)\,p(B)}{p(A \mid B)\,p(B) + p(A \mid \bar B)\,p(\bar B)} \qquad (3.2)$$

Trong poker, định lý Bayes cho phép tinh chỉnh phán đoán về xác suất dựa trên thông tin mới quan sát được. Người chơi giỏi dùng nó liên tục; quá trình suy luận Bayes là trái tim của việc đọc bài và chơi khai thác (Phần II).

#### Ví dụ xét nghiệm

Một quy trình sàng lọc một bệnh: nếu người có bệnh được xét nghiệm, quy trình nhận ra bệnh đúng 80% số lần; nếu người không có bệnh được xét nghiệm, quy trình báo nhầm là có bệnh 10% số lần; trung bình 5% dân số có bệnh. Một người chọn ngẫu nhiên được xét nghiệm và có kết quả dương tính. Xác suất người này có bệnh (khi chưa có xét nghiệm hay chẩn đoán thêm) là bao nhiêu?

Nếu bạn trả lời "khoảng 80% hoặc thấp hơn một chút", bạn sai, nhưng không đơn độc: các nghiên cứu về câu trả lời của bác sĩ cho các câu hỏi như vậy cho thấy sự thiếu hiểu biết đáng sợ về các khái niệm Bayes.

Đặt A = quy trình cho kết quả dương tính; B = người bệnh có bệnh. Ta tìm p(B | A), với:

- p(A | B) = 0,8 (có bệnh thì dương tính 80% số lần);
- p(A | B̄) = 0,1 (không có bệnh thì dương tính 10% số lần);
- p(B) = 0,05 (5% mọi người có bệnh);
- p(B̄) = 0,95 (95% mọi người không có bệnh).

Theo (3.2):

p(B | A) = (0,8)(0,05) / [(0,8)(0,05) + (0,1)(0,95)] = 0,04 / (0,04 + 0,095) = 0,04 / 0,135 ≈ 29,63%.

Xác suất một người dương tính thực sự có bệnh thấp hơn nhiều so với "độ chính xác" 80% của xét nghiệm khi phát hiện bệnh ở người có bệnh. Xét nghiệm này cần được theo sau bằng xét nghiệm bổ sung để xác nhận.

**Diễn giải bằng 100.000 người.** Thay vì chỉ thế số, xét 100.000 người, tất cả đều được xét nghiệm:

| | Dương tính | Âm tính | Cộng |
|---|---:|---:|---:|
| Có bệnh (5% dân số) | 4.000 (80% người có bệnh) | 1.000 (20%, âm tính giả) | 5.000 |
| Không có bệnh (95% dân số) | 9.500 (10%, dương tính giả) | 85.500 (90% người không có bệnh) | 95.000 |
| Cộng | 13.500 | 86.500 | 100.000 |

Trong 13.500 người dương tính, chỉ 4.000 người thực sự có bệnh: p(B | A) = 4.000 / 13.500 ≈ 29,6%. Lý do trực quan: nhóm không có bệnh đông gấp 19 lần nhóm có bệnh, nên dù tỷ lệ báo nhầm chỉ 10%, số dương tính giả (9.500) vẫn nhiều gấp 2,4 lần số dương tính thật (4.000).

**Xét nghiệm tốt hơn.** Tăng độ chính xác — phát hiện đúng hơn ở người có bệnh, hoặc ít báo nhầm hơn ở người không có bệnh — làm tăng xác suất có điều kiện mà một người dương tính thực sự có bệnh. Điều này không làm tăng khả năng một người có bệnh (ta không muốn thế!), mà giảm số người bị báo nhầm và phải chịu căng thẳng vì tưởng mình có bệnh.

- Xét nghiệm luôn phát hiện người có bệnh, tỷ lệ báo nhầm giữ nguyên: p(B | A) = (1)(0,05) / [(1)(0,05) + (0,1)(0,95)] = 0,05 / 0,145 ≈ 34,5%.
- Giữ tỷ lệ phát hiện 80%, giảm báo nhầm từ 10% xuống 6%: p(B | A) = (0,8)(0,05) / [(0,8)(0,05) + (0,06)(0,95)] = 0,04 / 0,097 ≈ 41,2%.

Người tổng hợp nhận xét: giảm báo nhầm hiệu quả hơn tăng tỷ lệ phát hiện, vì báo nhầm áp lên nhóm 95% đông đảo.

Then chốt của định lý Bayes là có một xác suất tiên nghiệm và nhận được thông tin mới. Ở đây ta bắt đầu với xác suất tiên nghiệm 5% rằng người bệnh có bệnh; sau xét nghiệm, kết quả dương tính là thông tin mới giúp điều chỉnh xác suất — trong trường hợp này là tăng lên. Quá trình này gọi là **suy luận Bayes** và là yếu tố quyết định để chơi poker thành công.

### 4. Suy luận Bayes ở bàn chơi: người có stack lớn và người chơi maniac (trang 43–44)

#### Người có stack gấp bảy lần

Có vô số cách dùng suy luận Bayes, và nhiều người chơi dùng nó một cách vô thức. Trong một giải đấu, một người chơi ngồi ở bàn bị giải tán rất sớm và được chuyển sang bàn mới, nơi người ngồi bên phải đã có stack (lượng chip) gấp bảy lần stack khởi đầu, trong khi phần lớn người chơi khác vẫn quanh mức khởi đầu. Phần đông sẽ kết luận có hai khả năng: người có stack lớn hoặc là người chơi cực kỳ loose (chơi nhiều tay) và hung hãn, hoặc là người chơi bình thường nhưng cực kỳ may. Xu hướng tự nhiên tin rằng người đó nhiều khả năng loose và hung hãn hơn là rất may chính là hệ quả trực tiếp của định lý Bayes, dù người chơi có biết khái niệm này hay không. (Người tổng hợp giải thích: một người chơi bình thường hiếm khi đạt stack gấp bảy lần sớm như vậy, tức p(stack lớn | bình thường) rất nhỏ, còn người loose-hung hãn thì dễ có biến động lớn, nên hậu nghiệm nghiêng về giả thuyết thứ nhất.)

#### Người chơi maniac

Định lượng được hiệu ứng này bằng định lý Bayes, và điều đó có thể giúp ta chơi mạnh tay hơn ngay cả khi chưa có thông tin chắc chắn. Một người chơi mới ngồi vào bàn. Dùng mọi thông tin quan sát có được (sách nhắc cả việc rập khuôn theo dân tộc, giới tính, cử chỉ, trang phục, vẻ ngoài…), ta kết luận họ có 10% khả năng là "maniac" — người raise 80% số tay từ vị trí cutoff (ghế ngay bên phải button) — và 90% khả năng là người chơi chặt, chỉ raise 10% số tay từ ghế đó. Tay đầu tiên họ chơi, họ raise từ cutoff (giả định không có việc "post" blind khi mới vào bàn). Xác suất họ là maniac là bao nhiêu? Tác giả mời người đọc tự ước lượng trước, vì thử thách trực giác là một trong những cách tốt nhất để rèn khả năng ước lượng — kỹ năng vô giá cả trong poker lẫn trong đời sống.

Đặt A = đối thủ raise tay đầu tiên từ cutoff; B = đối thủ là maniac.

- p(A | B) = 0,8 (maniac raise 80% số lần);
- p(A | B̄) = 0,1 (không phải maniac thì raise 10% số lần);
- p(B) = 0,1 (tiên nghiệm: 10% là maniac);
- p(B̄) = 0,9.

p(B | A) = (0,8)(0,1) / [(0,8)(0,1) + (0,1)(0,9)] = 0,08 / 0,17 ≈ 47,1%.

Chỉ cần thấy người này raise tay đầu tiên, ta điều chỉnh xác suất họ là maniac từ 10% lên 47% ngay lập tức. Nếu họ raise cả hai tay đầu (giả định suy luận như nhau cho ghế sát cutoff), xác suất lên gần 87% theo sách; người tổng hợp tính lại: dùng 47,06% làm tiên nghiệm mới, p = 0,4706 × 0,8 / (0,4706 × 0,8 + 0,5294 × 0,1) = 0,3765 / 0,4294 ≈ 87,7%; hoặc gộp hai lần quan sát: 0,1 × 0,8² / (0,1 × 0,64 + 0,9 × 0,01) = 0,064 / 0,073 ≈ 87,7%. Dĩ nhiên các xác suất này phụ thuộc vào độ chính xác của giả định ban đầu: thực tế không chỉ có hai kiểu người chơi, và đánh giá của ta về kiểu người chơi không rõ ràng như vậy.

| Quan sát | Xác suất là maniac |
|---|---:|
| Trước khi quan sát (tiên nghiệm) | 10% |
| Sau một lần raise từ cutoff | 47,1% |
| Sau hai lần raise liên tiếp | 87,7% |

#### Đừng chờ đợi, nhưng coi chừng bị lừa

Nhiều người chơi trì hoãn việc đánh giá và điều chỉnh theo một đối thủ cho tới khi thu thêm thông tin, bằng cách quan sát vài tay. Theo tác giả, cách này quá thụ động: tối đa hoá EV (kỳ vọng, expected value) nghĩa là tận dụng mọi thông tin đang có, không nhất thiết đợi xác nhận rằng thông tin đáng tin rồi mới khai thác. Sai lầm của những người chơi này là không nhận ra sức mạnh của thông tin họ đã có. Đáng chú ý là nhiều người, kể cả người chơi không giỏi, vẫn làm điều chỉnh này hoặc tương tự một cách trực giác. Nhưng cẩn thận: cách điều chỉnh này có thể bị khai thác bởi những người cố tình ngồi vào bàn và chơi khác hẳn phong cách thường ngày để khiến người khác điều chỉnh sai.

Người chơi giỏi dùng định lý Bayes liên tục khi có thông tin mới; nhưng ngay cả ngoài bàn chơi, định lý Bayes giúp rút ra kết luận có căn cứ hơn từ dữ liệu, như mục tiếp theo cho thấy với chủ đề win rate.

### 5. Ước lượng tham số theo thống kê Bayes (Estimating Parameters: Bayesian Statistics, trang 44–48)

#### Bài toán

Quay lại người chơi limit 16.900 tay với x̄ = 1,15 BB/100 và s = 2,1 BB/tay. Thống kê cổ điển cho ước lượng hợp lý cực đại 1,15 BB/100 và khoảng tin cậy 95% là [−2,07; 4,37] BB/100, dựa trên giả định không có thông tin gì thêm về phân phối win rate. Giờ ta đoán một phân phối win rate và áp dụng định lý Bayes để có ước lượng chính xác hơn. Trước hết phải giả định một phân phối win rate tổng thể cho người chơi này: giả sử họ được chọn ngẫu nhiên từ tổng thể những người chơi poker thường xuyên. Phân phối đó gọi là **phân phối xác suất tiên nghiệm**.

#### Dựng phân phối tiên nghiệm

Không rõ phân phối này trông thế nào, vì ta không có kết quả của toàn bộ người chơi. Nhưng có thể đơn giản hoá và ước lượng, với hy vọng phân phối đủ gần sự thật để có lợi khi đưa vào ước lượng.

- Giả sử người chơi chơi hỗn hợp các ván limit tầm trung thấp, từ 10–20 USD tới 30–60 USD. Tổng rake mà ván trả ước khoảng 3–4 USD mỗi tay, tức khoảng 0,1 BB/tay (người tổng hợp kiểm tra: big bet là 20–60 USD, nên 3,5 USD bằng 0,06–0,18 BB; 0,1 BB là con số giữa hợp lý).
- Chia gần đều cho mọi người chơi trong bàn (khoảng 10 người), ảnh hưởng ròng của rake lên win rate của mỗi người là khoảng 0,01 BB/tay, tức 1 BB/100.
- Trung bình của phân phối win rate mọi người chơi bằng đúng mức này với dấu âm, **−1 BB/100**, vì đó là dòng tiền ròng chảy ra khỏi ván.
- Giả sử win rate phân phối gần chuẩn, với độ lệch chuẩn (của win rate giữa các người chơi) khoảng 0,015 BB/tay, tức 1,5 BB/100. Khi đó 68% người chơi có win rate trong khoảng −1 ± 1,5, tức từ −2,5 tới +0,5 BB/100; và 95% trong khoảng −1 ± 3, tức từ −4 tới +2 BB/100. Nếu không hợp trực giác của bạn, có thể chỉnh các con số mà không đổi quy trình.

Để đơn giản tính toán, thay phân phối chuẩn liên tục bằng phân phối rời rạc gần đúng:

| Win rate | Tỷ lệ người chơi có win rate này |
|---|---:|
| −5 BB/100 | 0,25% |
| −4 BB/100 | 2% |
| −3 BB/100 | 8% |
| −2 BB/100 | 20% |
| −1 BB/100 | 39,5% |
| 0 BB/100 | 20% |
| +1 BB/100 | 8% |
| +2 BB/100 | 2% |
| +3 BB/100 | 0,25% |

(Người tổng hợp kiểm tra: tổng 100%; trung bình −1 BB/100; độ lệch chuẩn √1,48 ≈ 1,22 BB/100; tỷ lệ người chơi có win rate từ +1 BB/100 trở lên là 8 + 2 + 0,25 = 10,25%.)

#### Tính xác suất hậu nghiệm

Với mỗi win rate r trong bảng, đặt:

- A = sự kiện quan sát được win rate 1,15;
- B = sự kiện win rate r này là win rate thật (tiên nghiệm).

Không thể tính trực tiếp xác suất quan sát đúng một giá trị (phân phối chuẩn là liên tục), nên thay bằng xác suất quan sát được win rate trong khoảng 1,14 tới 1,16. Với độ lệch chuẩn của mẫu cỡ này là 1,61 BB/100:

p(A | B) = Φ((1,16 − r) / 1,61) − Φ((1,14 − r) / 1,61),

trong đó Φ là hàm phân phối tích luỹ chuẩn tắc (sách đọc giá trị "từ bảng xác suất"). p(A | B̄) là trung bình có trọng số (theo xác suất tiên nghiệm) của p(A | B) ở mọi dòng khác dòng đang xét: p(A | B̄) = Σ_{r' ≠ r} p(A | r')p(r') / (1 − p(r)).

Bảng đầu vào (dấu của win rate dương và tiêu đề cột đã sửa; xem khối Lưu ý):

| Win rate | p(B) | p(A \| B) | p(A \| B̄) | p(B̄) |
|---|---:|---:|---:|---:|
| −5 BB/100 | 0,25% | 0,000004 | 0,00222555 | 99,75% |
| −4 BB/100 | 2% | 0,000031 | 0,00226468 | 98% |
| −3 BB/100 | 8% | 0,000182 | 0,00239720 | 92% |
| −2 BB/100 | 20% | 0,000738 | 0,00259053 | 80% |
| −1 BB/100 | 39,5% | 0,002037 | 0,00233943 | 60,5% |
| 0 BB/100 | 20% | 0,003834 | 0,00181659 | 80% |
| +1 BB/100 | 8% | 0,004918 | 0,00198539 | 92% |
| +2 BB/100 | 2% | 0,004301 | 0,00217753 | 98% |
| +3 BB/100 | 0,25% | 0,002564 | 0,00221914 | 99,75% |

Áp dụng (3.2) cho từng dòng, p(B | A) = p(A | B)p(B) / [p(A | B)p(B) + p(A | B̄)p(B̄)]. Chẳng hạn dòng −1 BB/100: tử số 0,002037 × 0,395 = 0,000805; mẫu số 0,000805 + 0,00233943 × 0,605 = 0,000805 + 0,001415 = 0,002220; tỷ số ≈ 36,25%. Mẫu số giống nhau ở mọi dòng (bằng p(A) ≈ 0,00222), nên cách tính theo từng dòng tương đương với chuẩn hoá tích p(A | B)p(B) cho tổng bằng 1. Kết quả (người tổng hợp đã tính lại, khớp từng chữ số):

| Win rate | Xác suất hậu nghiệm p(B \| A) |
|---|---:|
| −5 BB/100 | 0,00% |
| −4 BB/100 | 0,03% |
| −3 BB/100 | 0,66% |
| −2 BB/100 | 6,65% |
| −1 BB/100 | 36,25% |
| 0 BB/100 | 34,54% |
| +1 BB/100 | 17,72% |
| +2 BB/100 | 3,87% |
| +3 BB/100 | 0,29% |
| Cộng | 100% |

Giống như thống kê cổ điển cho ước lượng hợp lý cực đại, ở đây ta xác định −1 BB/100 là giá trị khả dĩ nhất theo các giả định này (sách gọi là "maximum likelihood estimate"; đúng thuật ngữ là mode hậu nghiệm). Dĩ nhiên các giả định này không phải sự thật — win rate thực tế gần như liên tục — nhưng nếu dùng phân phối liên tục và làm phép toán phức tạp hơn, ta sẽ được phân phối tương tự. **Hàm ý then chốt: vì người thắng tương đối hiếm, nhân vật giả định của ta gần như có khả năng là người thua đã gặp may ngang với khả năng có win rate dương.** Người tổng hợp cộng bảng: khả năng thua (≤ −1) là 43,59%, hoà vốn 34,54%, thắng (≥ +1) là 21,88%; kỳ vọng hậu nghiệm của win rate khoảng −0,25 BB/100. Số liệu còn mạnh hơn lời văn: thua có khả năng gấp đôi thắng.

#### Người chơi quan sát được 5 BB/100

Điều này rõ hơn nữa với người có win rate quan sát cao hơn nhiều, chẳng hạn 5 BB/100 (cùng 16.900 tay). Cách cổ điển vẫn cho ước lượng hợp lý cực đại 5 BB/100, vì coi mọi win rate là như nhau. Tính lại theo Bayes:

| Win rate | Xác suất hậu nghiệm khi quan sát 5 BB/100 |
|---|---:|
| −5 BB/100 | 0,00% |
| −4 BB/100 | 0,00% |
| −3 BB/100 | 0,00% |
| −2 BB/100 | 0,16% |
| −1 BB/100 | 3,79% |
| 0 BB/100 | 15,78% |
| +1 BB/100 | 35,40% |
| +2 BB/100 | 33,84% |
| +3 BB/100 | 11,03% |
| Cộng | 100% |

Người chơi này gần như chắc là người thắng, và thắng đáng kể (người tổng hợp cộng: 80,27% khả năng win rate từ +1 trở lên; kỳ vọng hậu nghiệm khoảng 1,32 BB/100). Nhưng vì win rate 5 BB/100 không có trong tổng thể, định lý Bayes điều chỉnh đúng đắn win rate của họ về các mức khả dĩ hơn của nhóm 10% người chơi giỏi nhất.

#### Mẫu 100.000 tay

Thu thêm dữ liệu sẽ làm các ước lượng Bayes hội tụ về win rate quan sát: người chơi càng thể hiện nhất quán khả năng thắng ở một mức, mức đó càng có khả năng là win rate thật. Tính lại với mẫu 100.000 tay (win rate quan sát vẫn 1,15 BB/100; độ lệch chuẩn của mẫu quy về 100 tay là 2,1 × √100.000 / 1.000 ≈ 0,664 BB/100):

| Win rate | Xác suất hậu nghiệm sau 100.000 tay |
|---|---:|
| −5 BB/100 | 0,00% |
| −4 BB/100 | 0,00% |
| −3 BB/100 | 0,00% |
| −2 BB/100 | 0,00% |
| −1 BB/100 | 1,57% |
| 0 BB/100 | 33,42% |
| +1 BB/100 | 58,37% |
| +2 BB/100 | 6,60% |
| +3 BB/100 | 0,04% |
| Cộng | 100% |

Với cỡ mẫu này, ta tin hơn nhiều rằng quan sát khớp thực tế, dù trong phân phối nền chỉ khoảng 10% người chơi thắng ít nhất 1 BB/100. (Người tổng hợp tính: khả năng thắng là 65,01%, kỳ vọng hậu nghiệm khoảng 0,70 BB/100 — vẫn thấp hơn 1,15 vì tiên nghiệm còn kéo xuống.)

So sánh ba trường hợp (người tổng hợp tổng hợp từ ba bảng):

| Trường hợp | Ước lượng cổ điển | Win rate khả dĩ nhất (Bayes) | Khả năng thắng (≥ +1) | Kỳ vọng hậu nghiệm |
|---|---:|---:|---:|---:|
| 16.900 tay, quan sát 1,15 | 1,15 | −1 | 21,88% | −0,25 |
| 16.900 tay, quan sát 5 | 5 | +1 | 80,27% | 1,32 |
| 100.000 tay, quan sát 1,15 | 1,15 | +1 | 65,01% | 0,70 |

#### Người theo tần suất và người theo Bayes

Có một sự chia rẽ giữa các nhà thống kê cổ điển (đôi khi gọi là người theo tần suất, frequentist) và các nhà thống kê Bayes. Bất đồng xoay quanh ý tưởng của Bayes rằng tham số tổng thể nên được xem như phân phối xác suất: người theo Bayes ước lượng một phân phối tiên nghiệm, quan sát một mẫu, rồi điều chỉnh phân phối tiên nghiệm theo bằng chứng mới. Người theo tần suất bác bỏ cách này, muốn mô tả tham số tổng thể là giá trị cố định, không đổi, dù ta không biết giá trị đó. Tác giả nghiêng hẳn về quan điểm Bayes vì tính hữu ích của nó trong phân tích poker. Phương pháp dùng ở đây thậm chí chưa phải kỹ thuật Bayes đầy đủ, chỉ là bản đơn giản hoá để ý tưởng dễ tiếp cận; tác giả khuyên đọc các sách thống kê nâng cao có trình bày kỹ về ước lượng điểm và phương pháp Bayes.

#### Hồi quy về trung bình

Một chủ đề nảy sinh từ phân tích này là **hồi quy về trung bình**. Giả sử ta quan sát win rate trên một mẫu nhỏ. Win rate quan sát cao hơn trung bình sẽ có xu hướng thấp hơn nếu quan sát lại trong tương lai, và win rate thấp hơn trung bình sẽ có xu hướng tốt lên. Nguyên nhân không phải là một kiểu "bù trừ" thống kê, trong đó các lần thử cực đoan trong quá khứ được bù bằng các lần thử cực đoan theo chiều ngược lại trong tương lai — các sự kiện này độc lập. Nguyên lý thật là: nếu bạn vượt trung bình của cả tổng thể, thì nhiều khả năng bạn cũng đã vượt kỳ vọng của chính mình; nếu bạn dưới trung bình, nhiều khả năng bạn cũng đã dưới kỳ vọng của mình. Do đó bạn sẽ có xu hướng (đôi khi rất nhẹ) quay về gần trung bình của mọi người chơi; nói cách khác, dự báo tốt nhất pha một phần nhỏ trung bình tổng thể vào kết quả quan sát. Phân tích Bayes ở trên cho thấy điều này: sau 16.900 tay, dự báo win rate điều chỉnh của người chơi vẫn bị phân phối tổng thể chi phối mạnh, kéo xuống phía trung bình tổng thể −1 BB/100.

### 6. Các ý then chốt (Key Concepts, trang 48)

- Khi ước lượng tham số tổng thể từ dữ liệu quan sát, có thể dùng một trong hai phương pháp: theo tần suất (cổ điển) hoặc Bayes.
- Phương pháp cổ điển giả định không có thông tin về phân phối nền. Nó cho ước lượng hợp lý cực đại bằng trung bình mẫu, và khoảng tin cậy gồm mọi giá trị mà kết quả quan sát nằm trong vùng chấp nhận theo mức đã chọn.
- Quy tắc Bayes cho một phương pháp vững để đưa thông tin mới vào các ước lượng xác suất tiên nghiệm.
- Dùng phân phối xác suất tiên nghiệm và định lý Bayes có thể cho ước lượng tham số tổng thể tốt hơn (ước lượng Bayes), khi ta có thông tin chính xác về phân phối tiên nghiệm.

## Luận điểm cốt lõi

### Mệnh đề

Dữ liệu kết quả poker, ngay cả hàng chục nghìn tay, chứa ít thông tin về win rate thật hơn người chơi thường nghĩ. Ước lượng tốt phải kết hợp dữ liệu mẫu với thông tin tiên nghiệm về tổng thể, và định lý Bayes là cách làm điều đó một cách nhất quán; cùng cơ chế ấy dùng được cho mọi phán đoán ở bàn chơi, từ đánh giá kiểu đối thủ tới đọc bài.

### Giả định

- Kết quả các tay độc lập và cùng phân phối; tổng nhiều tay xấp xỉ chuẩn (Định lý Giới hạn Trung tâm), và s = 2,1 BB/tay xấp xỉ đúng σ.
- Người chơi được coi như chọn ngẫu nhiên từ tổng thể người chơi thường xuyên; phân phối tiên nghiệm (trung bình −1 BB/100, độ lệch chuẩn khoảng 1,5 BB/100) là đúng.
- Win rate chỉ nhận chín giá trị nguyên từ −5 tới +3 BB/100 (rời rạc hoá).
- Trong ví dụ maniac: chỉ có hai kiểu người chơi với tần suất raise cố định, và các tay độc lập.

### Cơ chế

1. Viết hàm hợp lý p(dữ liệu | tham số) — ở đây là xác suất quan sát win rate quanh 1,15 khi win rate thật là r, với σ = 1,61 BB/100.
2. Thống kê cổ điển chọn r làm hàm hợp lý lớn nhất và dựng khoảng các r "không bị dữ liệu bác bỏ".
3. Thống kê Bayes nhân hàm hợp lý với xác suất tiên nghiệm p(r), chuẩn hoá cho tổng bằng 1, được phân phối hậu nghiệm.
4. Khi dữ liệu ít (σ của mẫu lớn), tiên nghiệm chi phối; khi dữ liệu nhiều, hàm hợp lý chi phối và ước lượng hội tụ về kết quả quan sát.
5. Hệ quả: các kết quả cực đoan bị kéo về trung bình tổng thể (hồi quy về trung bình).

### Bằng chứng và ví dụ tác giả đưa ra

- Người chơi 16.900 tay: σ của kết quả 1,61 BB/100 > win rate 1,15; khoảng tin cậy 95% [−2,07; 4,37].
- 5.000 tay thắng 10 BB/100 so với thực tế win rate cao nhất chỉ 3–4 BB/100.
- Xét nghiệm 80% / 10% / 5% cho 29,6%; cải tiến cho 34,5% và 41,2%.
- Maniac: 10% thành 47,1% sau một lần raise, khoảng 87,7% sau hai lần.
- Phân phối hậu nghiệm: −1 BB/100 khả dĩ nhất (36,25%) sau 16.900 tay; quan sát 5 BB/100 bị kéo về +1/+2; 100.000 tay cho +1 BB/100 với 58,37%.

### Kết luận và hàm ý cho người chơi

- Đừng kết luận mình là người thắng (hay thua) từ vài chục nghìn tay limit; khoảng bất định rộng hơn chính win rate.
- Vì rake làm phần lớn người chơi thua, một kết quả dương khiêm tốn nhiều khả năng một phần là may mắn; hãy "chiết khấu" kết quả tốt về phía trung bình.
- Ở bàn chơi, cập nhật đánh giá đối thủ ngay từ hành động đầu tiên; mỗi quan sát có thể dịch chuyển xác suất rất mạnh khi các giả thuyết dự báo hành vi khác nhau nhiều (80% so với 10%).
- Nhưng tiên nghiệm sai cho kết luận sai, và đối thủ tinh ý có thể cố tình tạo ấn tượng sai để khai thác việc ta cập nhật.

### Trong ngôn ngữ xác suất và thống kê

Với dữ liệu x̄ ~ N(μ, σ²/n) và tiên nghiệm π(μ), hậu nghiệm π(μ | x̄) ∝ L(μ; x̄) π(μ). Thống kê cổ điển dùng ước lượng hợp lý cực đại μ̂ = x̄ và khoảng x̄ ± z·σ/√n. Theo hiểu biết của người tổng hợp, nếu tiên nghiệm là chuẩn N(m₀, τ²) thì trung bình hậu nghiệm có dạng đóng là trung bình có trọng số (σ²/n · m₀ + τ² · x̄) / (σ²/n + τ²): với m₀ = −1, τ = 1,5, σ/√n = 1,61, x̄ = 1,15, trọng số dành cho dữ liệu là 2,25 / (2,25 + 2,61) ≈ 0,46, cho trung bình hậu nghiệm khoảng −1 + 0,46 × 2,15 ≈ −0,01 BB/100; với tiên nghiệm rời rạc hẹp hơn của sách (độ lệch chuẩn 1,22), kết quả là −0,25. Đây chính là "hệ số co" (shrinkage) mô tả hồi quy về trung bình.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| parameter (population parameter) | tham số tổng thể | giá trị thật chưa biết của phân phối nền (μ, σ) |
| sample statistic | thống kê mẫu | con số tính từ dữ liệu quan sát (x̄, s) |
| win rate | win rate (tỷ lệ thắng) | số tiền thắng trung bình, ở đây đo bằng BB/100 |
| big bet (BB) | big bet | mức cược lớn trong limit poker (gấp đôi mức cược nhỏ), dùng làm đơn vị |
| BB/100 (BB/100h) | big bet trên 100 tay | đơn vị win rate |
| limit poker | limit | poker có mức cược cố định |
| hand history | lịch sử tay bài | bản ghi chi tiết từng tay, có thể tải về khi chơi online |
| sampling distribution | phân phối lấy mẫu | phân phối của một thống kê khi lặp lại việc lấy mẫu |
| Central Limit Theorem | Định lý Giới hạn Trung tâm | tổng/trung bình nhiều biến độc lập xấp xỉ chuẩn |
| normal distribution | phân phối chuẩn | phân phối hình chuông |
| standard deviation | độ lệch chuẩn | căn bậc hai của phương sai |
| maximum likelihood estimate | ước lượng hợp lý cực đại | giá trị tham số làm dữ liệu quan sát có khả năng cao nhất |
| confidence interval | khoảng tin cậy | tập giá trị tham số không bị dữ liệu bác bỏ ở mức đã chọn |
| significance level | mức ý nghĩa | xác suất sai được chấp nhận (chuẩn là 5% cho khoảng 95%) |
| confidence level | mức tin cậy | 1 trừ mức ý nghĩa, ví dụ 95% |
| a priori information | thông tin tiên nghiệm | thông tin có trước khi quan sát dữ liệu |
| prior probability (distribution) | xác suất (phân phối) tiên nghiệm | xác suất gán trước khi có bằng chứng mới |
| posterior probability | xác suất hậu nghiệm | xác suất sau khi cập nhật theo bằng chứng |
| conditional probability | xác suất có điều kiện | p(B \| A): xác suất B khi biết A |
| joint probability | xác suất đồng thời | p(A ∩ B): xác suất cả A và B |
| complement | phần bù | B̄: sự kiện B không xảy ra |
| Bayes' theorem (Bayes' rule) | định lý Bayes (quy tắc Bayes) | p(B \| A) = p(A \| B)p(B) / p(A) |
| Bayesian inference | suy luận Bayes | cập nhật xác suất tiên nghiệm bằng thông tin mới |
| false positive / false negative | dương tính giả / âm tính giả | báo có khi không có / báo không khi có |
| screening | sàng lọc | xét nghiệm ban đầu trên diện rộng |
| frequentist | người theo tần suất | trường phái coi tham số là cố định |
| Bayesian | người theo Bayes | trường phái coi tham số có phân phối xác suất |
| point estimation | ước lượng điểm | ước lượng tham số bằng một con số |
| regression to the mean | hồi quy về trung bình | kết quả cực đoan có xu hướng trở về gần trung bình khi đo lại |
| rake | rake | tiền phòng chơi thu từ mỗi pot |
| maniac | maniac | người chơi raise rất thường xuyên, cực kỳ hung hãn |
| tight player | người chơi chặt (tight) | người chỉ chơi ít tay mạnh |
| loose and aggressive | loose và hung hãn | chơi nhiều tay và hay cược, raise |
| raise | raise | tăng mức cược |
| cutoff | cutoff | ghế ngay bên phải button |
| posting (post) | post | đặt blind bắt buộc khi mới vào bàn ở một số phòng chơi |
| stack | stack | lượng chip của một người chơi |
| tournament | giải đấu | thể thức chơi tới khi một người có hết chip |
| EV (expected value) | kỳ vọng | giá trị trung bình dài hạn của một quyết định |
| exploitive play | chơi khai thác | điều chỉnh chiến lược để tận dụng điểm yếu của đối thủ |
| hand reading | đọc bài | suy ra phân phối bài của đối thủ |

## Câu nói đáng nhớ

> "But even if we have all this data, it's just a sample." — phần mở đầu chương
>
> *Dịch: Nhưng dù có toàn bộ dữ liệu này, nó vẫn chỉ là một mẫu.*
>
> Ý nghĩa: lịch sử tay bài của bạn không phải là win rate của bạn, chỉ là bằng chứng về nó.

> "The standard deviation of a sample of this size is greater than the win rate itself." — mục Classical Statistics
>
> *Dịch: Độ lệch chuẩn của một mẫu cỡ này lớn hơn cả chính win rate.*
>
> Ý nghĩa: sau 16.900 tay, nhiễu vẫn lấn át tín hiệu.

> "This does not mean that his true rate is 95% likely to lie on this interval." — mục Classical Statistics
>
> *Dịch: Điều này không có nghĩa là win rate thật của anh ta có 95% khả năng nằm trong khoảng này.*
>
> Ý nghĩa: cảnh báo về cách hiểu sai phổ biến nhất của khoảng tin cậy.

> "If you answered 'about or a little less than 80%,' you were wrong, but not alone." — ví dụ xét nghiệm
>
> *Dịch: Nếu bạn trả lời "khoảng 80% hoặc thấp hơn một chút", bạn sai, nhưng bạn không đơn độc.*
>
> Ý nghĩa: trực giác thường bỏ qua tỷ lệ nền (xác suất tiên nghiệm).

> "The process of Bayesian inference is at the heart of reading hands and exploitive play." — mục Bayes' theorem
>
> *Dịch: Quá trình suy luận Bayes là trái tim của việc đọc bài và chơi khai thác.*
>
> Ý nghĩa: câu nối chương này với toàn bộ Phần II.

> "Maximizing EV means taking advantage of all the information we have at our disposal and not necessarily waiting for confirmation that the information is reliable before trying to take advantage of it." — ví dụ maniac
>
> *Dịch: Tối đa hoá EV nghĩa là tận dụng mọi thông tin đang có, không nhất thiết chờ xác nhận thông tin đáng tin rồi mới khai thác nó.*
>
> Ý nghĩa: thông tin chưa chắc chắn vẫn có giá trị nếu được cân đúng trọng số.

> "Our hypothetical hero is nearly as likely to be a losing player who has gotten lucky as he is to have a positive win rate." — mục Bayesian Statistics
>
> *Dịch: Nhân vật giả định của ta gần như có khả năng là người thua gặp may ngang với khả năng có win rate dương.*
>
> Ý nghĩa: vì người thắng hiếm, một kết quả dương nhỏ chưa chứng minh được gì (số liệu thậm chí cho thấy thua có khả năng gấp đôi).

> "We are strongly oriented toward the Bayesian point of view because of its usefulness in poker analysis." — mục Bayesian Statistics
>
> *Dịch: Chúng tôi nghiêng hẳn về quan điểm Bayes vì tính hữu ích của nó trong phân tích poker.*
>
> Ý nghĩa: tuyên bố lập trường phương pháp luận của cả cuốn sách.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương đặt cạnh nhau hai cách suy luận trên cùng một bộ dữ liệu (16.900 tay, 1,15 BB/100), nên người đọc thấy rõ thông tin tiên nghiệm thay đổi kết luận đến đâu: từ "ước lượng 1,15, khoảng [−2,07; 4,37]" sang "khả dĩ nhất là −1, chỉ khoảng 22% khả năng thắng". Lập luận rằng rake làm trung bình win rate của tổng thể âm là một cách dựng tiên nghiệm có cơ sở kinh tế, không tuỳ tiện. Ví dụ maniac cho thấy định lý Bayes không chỉ là công cụ thống kê ngoài bàn chơi mà là cách tư duy từng tay, và lời khuyên "đừng chờ xác nhận" kèm cảnh báo "có thể bị lừa" là cân bằng. Mọi bảng số đều tính lại được chính xác.

### Những chỗ đơn giản hoá

- **Kết quả các tay không hoàn toàn độc lập và cùng phân phối:** đối thủ, mức cược, trạng thái tâm lý (tilt) thay đổi theo thời gian; win rate thật cũng thay đổi khi người chơi tiến bộ hoặc bàn chơi khó lên.
- **Tiên nghiệm chín điểm rời rạc** cắt mất đuôi: không ai được phép có win rate trên +3 BB/100, nên người quan sát 5 BB/100 không thể được ước lượng cao hơn +3 dù có bao nhiêu dữ liệu. Với 100.000 tay, lưới bước 1 BB/100 cũng thô: giá trị +1 "thắng" chỉ vì gần 1,15 nhất.
- **Tiên nghiệm là của "người chơi thường xuyên nói chung"** chứ không phải của người chơi cụ thể; nếu đã biết người này chơi chăm chỉ, học nhiều, tiên nghiệm phù hợp sẽ khác.
- **Ví dụ maniac** giả định hai kiểu người chơi và tần suất raise cố định; sách tự thừa nhận điều này.
- **Thuật ngữ thống kê** (mức ý nghĩa 95%, "ước lượng hợp lý cực đại" cho mode hậu nghiệm) được dùng lỏng; người đọc có nền thống kê nên đọc kèm khối Lưu ý.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- Phần mềm theo dõi (tracker) và HUD hiện tính sẵn win rate kèm độ lệch chuẩn và khoảng tin cậy; cộng đồng quen dùng đơn vị bb/100 theo big blind cho no-limit, với độ lệch chuẩn thường 80–120 bb/100, nên số tay cần để ước lượng còn lớn hơn ví dụ limit của sách.
- Rake online và cấu trúc hoàn tiền (rakeback) thay đổi nhiều, nên "trung bình −1 BB/100" chỉ là con số minh hoạ; ý tưởng tiên nghiệm âm do rake vẫn đúng.
- Hiệu ứng ví dụ maniac nay được tự động hoá: HUD (bảng số liệu hiện trên bàn chơi) hiển thị VPIP (tỷ lệ tay đối thủ tự nguyện bỏ tiền vào pot) và PFR (tỷ lệ tay đối thủ raise trước flop), về bản chất là ước lượng Bayes thô với tiên nghiệm ngầm định là "người chơi trung bình của phòng".

### Liên hệ các chương khác

- [C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md): quy tắc nhân p(A ∩ B) = p(A)p(B | A) và định nghĩa phần bù dùng để rút ra định lý Bayes.
- [C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md): công thức σ_N = σ√N và Định lý Giới hạn Trung tâm dùng để tính độ lệch chuẩn 1,61 BB/100.
- [C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md): mở Phần II, nơi các quyết định khai thác dựa trên phân phối bài và hành vi đối thủ ước lượng được.
- [C05-doc-bai-va-chien-luoc.md](C05-doc-bai-va-chien-luoc.md): đọc bài theo kiểu Bayes — cập nhật phân phối tay bài của đối thủ theo từng hành động.
- [C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md): chơi thích nghi, cân bằng giữa khai thác thông tin và nguy cơ bị lừa.
- [C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md): rủi ro phá sản khi win rate chính là đại lượng bất định đã ước lượng ở chương này.

### Vận dụng

- **Người chơi poker:** trước khi lên mức cược hay bỏ việc để chơi chuyên nghiệp, hãy tính khoảng bất định của win rate và "chiết khấu" nó về trung bình tổng thể; một win rate ấn tượng trên mẫu nhỏ hầu như chắc chắn bị phóng đại. Ở bàn chơi, cập nhật nhận định về đối thủ ngay từ quan sát đầu tiên, nhưng giữ nhận định ở dạng xác suất chứ không dán nhãn cứng.
- **Người làm tài chính và đầu tư:** cùng một bài toán xuất hiện khi đánh giá quỹ đầu tư hay nhà quản lý quỹ: lợi nhuận vượt trội (alpha) quan sát vài năm có độ lệch chuẩn lớn hơn chính nó, và vì sau phí, trung bình các nhà quản lý chủ động có alpha âm (tương tự rake), một thành tích tốt trên mẫu ngắn nhiều khả năng một phần là may. Ước lượng co về trung bình (shrinkage) theo kiểu Bayes là cách thực hành tốt khi ước lượng lợi nhuận kỳ vọng hay xếp hạng nhà quản lý.
- **Người ra quyết định nói chung:** ví dụ xét nghiệm là bài học về tỷ lệ nền: khi điều cần phát hiện hiếm (gian lận, vỡ nợ, bệnh), ngay cả công cụ khá chính xác cũng cho nhiều cảnh báo sai hơn cảnh báo đúng; giảm tỷ lệ báo nhầm thường quan trọng hơn tăng tỷ lệ phát hiện.

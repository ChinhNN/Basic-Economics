# Chương 27 — Chip không phải tiền: Giải đấu, phần II (Chips Aren't Cash: Tournaments, Part II)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 27 "Chips Aren't Cash: Tournaments, Part II", trang 346–360.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương 26 ([C26-giai-dau-phan-1-nhan-doi.md](C26-giai-dau-phan-1-nhan-doi.md)) nêu hai nguồn làm giá trị chip giải đấu lệch khỏi tỷ lệ chip — kỹ năng và cơ cấu trả thưởng — và xử lý nguồn thứ nhất bằng Lý thuyết Nhân đôi (E = C^N), dùng cho đầu và giữa giải. Chương 27 xử lý nguồn thứ hai ở cuối giải: khảo sát bốn công thức chuyển số chip thành equity giải thưởng cho người chơi ngang tài (chia theo tỷ lệ chip, Landrum-Burns, Malmuth-Harville, Malmuth-Weitzman) và chỉ ra thiên lệch của từng công thức. Phần thứ hai của chương quay lại chủ đề khoảng tin cậy cho tỷ lệ thắng ở Phần I ([C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md), [C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md)) và Phần IV ([C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md), nơi độ lệch phân phối được giới thiệu), nhưng cho kết quả giải đấu — một phân phối lệch phải rất mạnh. Chương 28 ([C28-giai-dau-phan-3-poker-van-la-poker.md](C28-giai-dau-phan-3-poker-van-la-poker.md)) dùng các công thức equity này trong các quyết định cụ thể (thoả thuận chia tiền, rebuy, chơi gần bubble).
**Ý chính:** **Ở cuối giải, chip không phải tiền: cơ cấu trả thưởng làm chồng chip lớn đáng ít hơn tỷ lệ chip và chồng chip nhỏ đáng nhiều hơn; không có công thức chính xác, chỉ có các mô hình, mỗi mô hình có thiên lệch riêng; và vì kết quả giải đấu lệch phải rất mạnh, khoảng tin cậy cho tỷ lệ thắng giải phải được xây khác với cash game.** Phần đầu định nghĩa ký hiệu: phần chip s_i = S_i/T, quỹ còn lại V_n, quỹ tăng thêm W_n = V_n − n·v_n, xác suất về nhất x_i (bằng s_i nếu ngang tài). Công thức **chia theo tỷ lệ chip** ⟨X_i⟩ = v_n + s_i·W_n (27.1) cho quá nhiều tiền cho chồng lớn: với chồng 48.000 / 4.000 / 4.000 / 4.000 và thưởng 2.000 / 1.400 / 900 / 700 đô la, người dẫn đầu được 2.460 đô la, hơn cả giải nhất. Công thức **Landrum-Burns** (27.2) cho rằng khi không về nhất thì về các hạng còn lại đều nhau, nên thiên vị chồng nhỏ (người dẫn đầu được 1.800 đô la); hai công thức này cho cận trên và cận dưới. Công thức **Malmuth-Harville** (27.3) lấy xác suất về hạng j bằng tỷ số xác suất thắng của người đó trên tổng xác suất thắng của những người còn lại, chính xác hơn nhưng khó tính tại bàn. Công thức **Malmuth-Weitzman** giả định chip của người bị loại chia đều cho những người còn lại; tác giả chứng minh hệ phương trình của nó có nghiệm đơn giản: xác suất bị loại tiếp theo tỷ lệ nghịch với số chip (27.4); đây là công thức tác giả ưa dùng khi tính thoả thuận ở bàn chung kết. Phần sau giới thiệu tỷ lệ thắng chuẩn hoá ω, kết quả chuẩn hoá Z = (X − s)/s, và với giả định thắng nhiều hơn đều ở mọi hạng có thưởng, phương sai mỗi giải là (k − ω)(1 + ω) với **bội số phương sai giải đấu** k = n·Σv_i² − 1 (27.5); trung bình m giải có phương sai (k̄ − ω)(1 + ω)/m (27.6). Người chơi giả định T với 800 giải (ω ≈ 1,07, k̄ ≈ 34,9) có độ lệch chuẩn 0,296 buyin theo công thức này, so với 0,347 quan sát được; dùng phân phối chuẩn cho khoảng [0,38; 1,77] là sai ở cả hai phía; tác giả đề xuất loại bỏ các tỷ lệ thắng cao bằng kiểm định z thông thường và chặn phía dưới bằng bất đẳng thức Chebyshev.

> **Lưu ý:**
> - **"$2,600" phải là 2.200 đô la (trang 347):** quỹ còn lại 5.000 đô la, đảm bảo 4 × 700 = 2.800 đô la, phần chia theo chip là 5.000 − 2.800 = 2.200 đô la. Chính các phép tính ngay sau dùng 2.200.
> - **p_{1,3} = 1/16 phải là 1/6 (trang 348):** với m = 2, p_{1,3} = 1 − 2 × 5/12 = 1/6. Phép tính equity ngay sau dùng 1/6 và cho đúng 1.566,67 đô la.
> - **Ví dụ Landrum-Burns thứ nhất có hai lỗi (trang 349):** (a) giải nhất in là "(2200)" trong cả bốn dòng; đúng là v₁ = 2.000 (các kết quả 1.416,67; 1.333,33; 1.083,33 chỉ đúng khi dùng 2.000). (b) Kết quả của người chơi 3 in là 1.066,67 đô la; đúng là (1/6)(2.000) + (5/18)(1.400 + 900 + 700) = 333,33 + 833,33 = **1.166,67** đô la. Kiểm tra: 1.416,67 + 1.333,33 + 1.166,67 + 1.083,33 = 5.000, đúng bằng quỹ; với 1.066,67 thì tổng chỉ là 4.900.
> - **Định nghĩa bubble bị ngược chỉ số (trang 347):** sách viết bubble là khi v_n = 0 nhưng v_{n+1} > 0. Vì thưởng không tăng khi hạng thấp hơn (v_{n+1} ≤ v_n), điều kiện này không bao giờ xảy ra; đúng phải là v_n = 0 nhưng v_{n−1} > 0 (người bị loại tiếp theo không có tiền, người sau đó có). Cũng trên trang 346–347, "mỗi người trong i người chơi còn lại" phải là n người, và giới hạn tổng "j = 1, N" phải là n.
> - **Hệ phương trình Malmuth-Weitzman (trang 351–352):** phương trình thứ tư của ví dụ bốn người in (x₁ + x₁/3)p₁; đúng là (x₄ + x₁/3)p₁. Ở bước thay nghiệm, dòng thứ ba in Σ(x_i/x_k + 1); đúng là Σ(x_i/x_k + 1/(n − 1)), vì tổng của n − 1 số hạng 1/(n − 1) mới bằng 1 như bước cuối dùng. Câu "the summation of 1/x_k, for all k not equal to I" in chữ I hoa thay cho i. Phương trình 27.3 in dấu "∨" (hoặc) thay cho dấu "|" (với điều kiện).
> - **Dấu của phí tham gia ε_b bị sai (trang 354):** với giải 100 + 10 đô la, bảo đảm quỹ 50.000 đô la, 300 người: s = 50.000/300 = 166,67 đô la, b_c = 110 đô la, nên ε_b = b_c − s = 110 − 166,67 = **−56,67** đô la (âm, vì sòng bài bù tiền vào quỹ — đúng trường hợp "phí âm" mà chính sách vừa mô tả). Sách in +56,67.
> - **Công thức phương sai một giải (trang 355):** dòng σ_x² = Σp_iV_i² − (ω + b)² phải là Σp_iV_i² − ((1 + ω)b)², vì ⟨X⟩ = (1 + ω)b; dòng kế tiếp của sách đã dùng đúng (1 + ω)²b². Trong phần này sách đổi ký hiệu cỡ giải từ s sang b mà không báo (và ngầm giả định không có phí, b_c = s). Dòng "⟨Z⟩² = σ_x²/b²" phải là σ_Z² = σ_x²/b².
> - **"(1 + 1.75)" phải là (1 + 1,07) (trang 359):** σ² = (34,875 − 1,07)(1 + 1,07)/800 = 0,0875, khớp với 0,0876 của sách; nếu dùng 1,75 thì được 0,1162.
> - **k của giải buổi tối hơi lệch (trang 359, người tổng hợp tính lại):** với n = 400 và bảng thưởng đã cho, Σv_i² = 0,135658, nên k = 400 × 0,135658 − 1 = 53,26, không phải 53,6456; k trung bình là (16,105 + 53,26)/2 = 34,68 thay vì 34,875. Người tổng hợp không tìm được cách đọc bảng thưởng nào cho ra 53,6456. Ảnh hưởng nhỏ: σ² = (34,68 − 1,07)(2,07)/800 = 0,0870, σ = 0,295 thay vì 0,296. Sách cũng viết gọn "k = (0,30)² + … + (0,04)² = 16,105", thiếu thừa số n và số hạng −1; con số 16,105 đúng là 100 × 0,17105 − 1.
> - **"Phương sai mẫu quan sát khoảng 0,3468 buyin" (trang 359):** con số 0,3468 thực ra là **độ lệch chuẩn của trung bình mẫu** (sai số chuẩn), không phải phương sai. Người tổng hợp dựng lại 800 kết quả từ hai bảng: phương sai mỗi giải 96,36, sai số chuẩn √(96,36/800) = 0,347. Khoảng [0,3802; 1,7675] của sách đúng bằng 1,0739 ± 2 × 0,3468 (dùng ±2 độ lệch chuẩn, không phải ±1,96).
> - **Dấu bất đẳng thức ở phần kiểm định (trang 357):** câu thứ hai "However, for ω > ω̂, we have to be more careful" phải là ω < ω̂ (các tỷ lệ thắng thật thấp hơn kết quả quan sát). Bất đẳng thức Chebyshev được sách viết cho một phía, P(z > a) < 1/a²; bất đẳng thức gốc là cho hai phía, P(|z| ≥ a) ≤ 1/a², nên dạng một phía của sách đúng nhưng lỏng (dạng một phía chặt hơn là 1/(1 + a²) theo bất đẳng thức Cantelli — nhận xét của người tổng hợp).
> - **Các con số khác khớp khi tính lại:** bốn kết quả chia theo chip (1.616,67; 1.433,33; 1.066,67; 883,33), 2.460 và 846,67; 1.566,67; Landrum-Burns ví dụ hai 1.800 và 1.066,67; hai bảng kết quả của người chơi T (tổng 315,5 và 543,6 buyin, tỷ lệ 0,79 và 1,36; ω chung 859,1/800 = 1,0739); bảng thưởng buổi tối (27,5% × 400 = 110 buyin…); 1,0739 + 2 × 0,2957 = 1,665 và 1,0739 − 2 × 0,2957 = 0,482; xác suất đuôi chuẩn P(z > 4) = 0,0000317; độ lệch của giải winner-take-all 1.000 người khoảng √1.000 = 31,6.
> - **Lớp chữ:** nhiều công thức của trang 351–356 bị hỏng cả trong lớp chữ lẫn ảnh trang (ký tự "¿" thay cho dấu ngoặc nhọn ⟨ ⟩ của kỳ vọng). Người tổng hợp dựng lại từ ngữ cảnh và kiểm tra bằng số. Các lỗi chính tả: "then chip count" (their), "Landrum-Buras", "Malmuth-Weitznan", "prize poof", "is be independent".
> - **Quy ước:** ⟨X⟩ là giá trị kỳ vọng của X (ký hiệu của sách). "Buyin" là phí tham gia; equity tính bằng buyin. "Equity" giữ nguyên tiếng Anh.

## Sơ đồ

### Mục "A Survey of Equity Formulas" — vì sao cần ánh xạ chip sang tiền ở cuối giải, và ký hiệu (trang 346–347)

```text
       Lý thuyết Nhân đôi (Chương 26) không dành cho giai đoạn gần vùng
       có thưởng hay bàn chung kết. Ở đó vẫn cần ánh xạ chip → tiền để:
       · tính thoả thuận chia tiền (nếu được phép)
       · ra quyết định có tính tới sự méo do cơ cấu trả thưởng
                                │
                                ▼
       Hai nguồn méo tác động ở hai thời điểm khác nhau:
       · đầu giải: kỹ năng tác động mạnh nhất, cơ cấu thưởng ít quan trọng
       · cuối giải: blind cao làm kỹ năng giảm tác dụng (trừ kỹ năng chơi
         ít người), cơ cấu thưởng tác động mạnh nhất
                                │
                                ▼
       Ký hiệu (n người còn lại):
       · S_i: chip của người i; T = Σ S_i; s_i = S_i / T, Σ s_i = 1
       · v_j: thưởng hạng j; V: tổng quỹ; V_n = Σ_{k=1}^{n} v_k: quỹ còn lại
       · w_j = v_j − v_n: thưởng TĂNG THÊM của hạng j so với hạng n
       · W_n = Σ w_j = V_n − n·v_n: quỹ tăng thêm
       · vào vùng có thưởng (in the money): v_n > 0
       · bubble: v_n = 0 nhưng v_{n−1} > 0
       · p_{i,j}: xác suất người i về hạng j; ⟨X_i⟩ = Σ_j p_{i,j}·v_j
       · x_i: xác suất người i về nhất (= s_i nếu ngang tài; có thể lấy
         từ Lý thuyết Nhân đôi nếu không ngang tài)
       Mỗi công thức lấy x_i làm đầu vào và đưa ra cách đơn giản để gán
       xác suất cho các hạng còn lại
```

### Mục "The Proportional Chip Count Formula" — công thức chia theo tỷ lệ chip (trang 347–349)

```text
       ⟨X_i⟩ = v_n + s_i·W_n                                  (27.1)
       · mọi người nhận phần đảm bảo v_n, phần còn lại chia theo chip
                                │
                                ▼
       Ví dụ 1: chip 25.000 / 20.000 / 10.000 / 5.000;
       thưởng 2.000 / 1.400 / 900 / 700 đô la (quỹ 5.000)
       · đảm bảo 4 × 700 = 2.800; chia theo chip 2.200
       · 1.616,67 / 1.433,33 / 1.066,67 / 883,33
                                │
                                ▼
       Ví dụ 2: chip 48.000 / 4.000 / 4.000 / 4.000
       · người 1: 700 + (4/5)(2.200) = 2.460 > giải nhất 2.000 → VÔ LÝ
       · người 2–4: 700 + (1/15)(2.200) = 846,67
                                │
                                ▼
       Nguyên nhân: công thức tương đương p_{i,j} = s_i cho MỌI hạng j
       → tổng xác suất về một hạng nào đó là n·s_i, vượt 1 khi s_i > 1/n
       · thiên lệch hệ thống: quá nhiều tiền theo CHIP, quá ít theo GHẾ
       · mọi mô hình đúng phải cho equity bằng nhau khi các x_i bằng nhau
                                │
                                ▼
       Sửa đổi: m = ⌊1/x_i⌋; p_{i,j} = x_i với j ≤ m; p_{i,m+1} = 1 − m·x_i
       · x_i > 0,5 → m = 1: p_{i,1} = x_i, p_{i,2} = 1 − x_i
       · ví dụ 1, người 1 (x = 5/12): m = 2; p = 5/12, 5/12, 1/6
         → 700 + (5/12)(1.300) + (5/12)(700) + (1/6)(200) = 1.566,67
       · nhược điểm: tổng equity không còn bằng quỹ; chỉ dùng làm cận
         trên thấp hơn một chút cho người dẫn đầu
```

### Mục "The Landrum-Burns Formula" — công thức Landrum-Burns (trang 349–350)

```text
       Stephen Landrum và Jazbo Burns (nhóm tin rec.gambling.poker):
       · tính xác suất về nhất của mỗi người
       · khi không về nhất, coi như về các hạng còn lại ĐỀU NHAU
       ⟨X_i⟩ = p_{i,1}·v₁ + Σ_{k=2}^{n} [(1 − p_{i,1}) / (n − 1)]·v_k   (27.2)
                                │
                                ▼
       Ví dụ 1: 1.416,67 / 1.333,33 / 1.166,67 / 1.083,33
       (sách in 1.066,67 cho người 3 — sai)
       Ví dụ 2: người 1: (4/5)(2.000) + (1/15)(3.000) = 1.800
                người 2–4: (1/15)(2.000) + (14/45)(3.000) = 1.066,67
                                │
                                ▼
       1.800 "hợp lý" (không vượt giải nhất), nhưng:
       · chồng lớn hiếm khi về chót khi blind cao → bị định giá THẤP
       · chồng rất nhỏ ít khi về nhì hơn về chót → bị định giá CAO
       → thiên vị chồng nhỏ
                                │
                                ▼
       Tỷ lệ chip và Landrum-Burns lệch NGƯỢC chiều nhau → cho cận dưới
       và cận trên; giá trị công bằng "thật" nằm giữa
```

### Mục "The Malmuth-Harville Formula" — công thức Malmuth-Harville (trang 350–351)

```text
       Từ sách Gambling Theory and Other Topics của Mason Malmuth;
       tương tự công thức Harville trong đua ngựa
       · xác suất về nhất: x_i
       · xác suất về nhì khi người k đã về nhất: x_i / (1 − x_k)
       · p_{i,2} = Σ_{k≠i} x_i·x_k / (1 − x_k)
       · tổng quát (27.3): xác suất về hạng j khi các hạng 1..j−1 đã có
         chủ = x_i / (1 − x₁ − … − x_{j−1})
                                │
                                ▼
       Jeff Yass: công thức hợp với poker HƠN đua ngựa
       · ngựa được cực kỳ ưa chuộng (80%) thường thua vì chấn thương
         hay bị truất quyền → cũng không về nhì
       · chồng chip lớn không thắng thì vẫn rất hay về nhì, rất hiếm về
         chót
                                │
                                ▼
       Thường chính xác hơn tỷ lệ chip và Landrum-Burns; nhưng nhiều người
       thì số hoán vị thứ tự về đích lớn, khó tính tại bàn → dùng phân
       tích ngoài bàn, giải sit-and-go
```

### Mục "The Malmuth-Weitzman Formula" — công thức Malmuth-Weitzman (trang 351–352)

```text
       Mark Weitzman đề xuất, Malmuth giới thiệu và có vẻ ưa hơn;
       Malmuth cho rằng phải giải hệ phương trình tuyến tính mỗi lần
       Ý chính: người bị loại thì chip của họ (trung bình) chia ĐỀU cho
       những người còn lại
       x_i = Σ_{k≠i} (x_i + x_k/(n − 1))·p_{k,n}
       (p_{k,n}: xác suất người k bị loại tiếp theo)
                                │
                                ▼
       Ví dụ bốn người: bốn phương trình, bốn ẩn p₁..p₄
       Tác giả nêu nghiệm (họ gọi là phương trình Vandermonde):
       b = Σ 1/x_i;   p_{k,n} = (1/x_k) / b                    (27.4)
       → xác suất bị loại tiếp TỶ LỆ NGHỊCH với số chip
                                │
                                ▼
       Kiểm tra: Σ_{k≠i} (x_i/x_k + 1/(n−1)) / b = (x_i(b − 1/x_i) + 1)/b
       = x_i  ✓
                                │
                                ▼
       Đánh giá: hợp lý, tính được tại bàn với người giỏi tính
       · khó chịu khi còn nhiều bàn: hai chồng ngắn ở hai bàn khác nhau,
         chồng gấp đôi lại có nửa xác suất bị loại?
       · vì sao người ở bàn khác cũng được chia chip?
       · dù vậy là công thức tác giả ưa nhất khi gần/trong vùng có thưởng;
         làm mốc "ngang tài" khi tính thoả thuận ở bàn chung kết
                                │
                                ▼
       Bài học: có nhiều cách ánh xạ chip → equity; tất cả là mô hình nên
       đều có thiên lệch; hiểu thiên lệch giúp quyết định và thoả thuận tốt
```

### Mục "Tournament Results and Confidence Intervals" (phần 1) — vì sao giải đấu khó, và các đại lượng chuẩn hoá (trang 352–354)

```text
       Cash game: kết quả là tổng nhiều ván → luật số lớn → khoảng tin cậy
       tính theo cách thông thường
       Giải đấu: KHÔNG dễ như vậy
       · giải winner-take-all 1.000 người: người thắng vừa trải qua một
         sự kiện cỡ 30 độ lệch chuẩn, mà lần nào cũng có người thắng
       · không có ước lượng phương sai tốt; phương sai tương quan mạnh với
         tỷ lệ thắng (biến cố lớn đều dương, biến cố âm chỉ là −1 buyin)
       · cần rất nhiều mẫu mới hội tụ về phân phối chuẩn
                                │
                                ▼
       ĐỘ LỆCH (skew) S = ⟨(X − μ)³⟩ / σ³
       · giải winner-take-all n người: S ≈ √n; phân phối chuẩn: S = 0
       · trung bình của m giải: S chia √m → cần m > n giải để S < 1
                                │
                                ▼
       ⟨X⟩ = Σ p_i·V_i (V_i: tiền hạng i); v_i = V_i / V
       · cỡ giải s = V / n (không rebuy, add-on)
       · chi phí b_c; phí tham gia ε_b = b_c − s (âm nếu sòng bài bù quỹ)
       · ví dụ 100 + 10 đô la, bảo đảm 50.000, 300 người: s = 166,67;
         b_c = 110; ε_b = −56,67
                                │
                                ▼
       Kỳ vọng ròng w = ⟨X⟩ − b_c = Σ p_i·V_i − s − ε_b
       · w₀ = Σ p_i·V_i − s: phần do kỹ năng
       · ε_b: không phụ thuộc kỹ năng (trừ chọn giải)
       TỶ LỆ THẮNG CHUẨN HOÁ ω = w₀/s = Σ (n·p_i)·v_i − 1
       KẾT QUẢ CHUẨN HOÁ Z = (X − s)/s, có ⟨Z⟩ = ω; giá trị hay gặp nhất
       (mode) của Z là −1
```

### Mục "Tournament Results and Confidence Intervals" (phần 2) — phương sai theo tỷ lệ thắng (trang 355–357)

```text
       GIẢ ĐỊNH: p_i = (1 + ω)/n cho MỌI hạng có thưởng
       · bắt đầu từ xác suất đều 1/n, chuyển ω/n lượt "không có tiền"
         sang mỗi hạng có thưởng
       · trái với Lý thuyết Nhân đôi (người giỏi về nhất nhiều hơn về
         nhì…) nhưng là xấp xỉ chấp nhận được
                                │
                                ▼
       σ_x² = Σ p_i·V_i² − (1 + ω)²b²
            = [n·(Σ v_i²)(1 + ω) − (1 + ω)²]·b²
       σ_Z² = σ_x²/b² = (n·Σ v_i² − 1 − ω)(1 + ω)
                                │
                                ▼
       BỘI SỐ PHƯƠNG SAI GIẢI ĐẤU:  k = n·Σ v_i² − 1          (27.5)
       · gần với cỡ giải hiệu dụng của Lý thuyết Nhân đôi
       · σ_Z² = (k − ω)(1 + ω), xấp xỉ tỷ lệ với 1 + ω
       · tốt hơn phương sai quan sát, trừ khi mẫu cực lớn
                                │
                                ▼
       Trung bình m giải độc lập:
       σ² = Σ σ²_{Z_j} / m² = (k̄ − ω)(1 + ω)/m                (27.6)
       · ω ≪ k → σ² ≈ k/m: phải chơi khoảng k giải để σ² = 1 (68% khả
         năng ω quan sát cách ω thật không quá 1 buyin)
       · nhược điểm: thực tế có người "nặng đầu" (nhiều lần về nhất), có
         người "nặng đuôi"; có thể dùng Lý thuyết Nhân đôi thay thế
       · mẫu rất lớn: ước lượng ngược k = ω̂ + m·σ̂²/(1 + ω̂)
```

### Mục "Tournament Results and Confidence Intervals" (phần 3) — kiểm định và bất đẳng thức Chebyshev (trang 357)

```text
       Câu hỏi: nếu tỷ lệ thắng chuẩn hoá thật là ω, kết quả quan sát ω̂
       may mắn hay xui xẻo đến đâu?
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       ω thật LỚN HƠN ω̂:                ω thật NHỎ HƠN ω̂:
       z = (ω̂ − ω)/σ(ω) < −2             phân phối lệch phải → kết quả
       → loại ω (mức 95%)                quan sát là một biến cố dương
       · phân phối lệch phải nên biến    hay gặp hơn phân phối chuẩn nói
         cố âm lớn còn hiếm hơn phân      → KHÔNG dùng phân phối chuẩn
         phối chuẩn nói → kiểm định       → dùng Chebyshev:
         thông thường là an toàn            P(z > a) < 1/a²
                                          · a = 4: < 1/16 (chuẩn: 0,00003)
                                          · thô nhưng đúng với MỌI phân phối
```

### Ví dụ người chơi T — 800 giải (trang 357–359)

```text
       Người chơi T: mỗi ngày bốn giải 50 + 5 đô la, trong 200 ngày
       · hai giải sáng khoảng 100 người, trả 9 hạng (30%, 20%, 12%, 10%,
         8%, 6%, 5,5%, 4,5%, 4%)
       · hai giải tối khoảng 400 người, trả 27 hạng (27,5%; 17,5%; 11,6%;
         8%; 6%; 4,5%; 3,5%; 2,6%; 1,7%; hạng 10–18: 1,2%; 19–27: 0,7%)
                                │
                                ▼
       Kết quả: sáng 400 giải, có tiền 52 lần (13%), lãi 315,5 buyin
       (0,79/giải); tối 400 giải, có tiền 51 lần (khoảng 13%), lãi 543,6
       buyin (1,36/giải); chung ω ≈ 1,07, m = 800
                                │
                                ▼
       k sáng = 16,105; k tối = 53,26 (sách: 53,6456); k̄ ≈ 34,7–34,9
       σ² = (34,875 − 1,07)(1 + 1,07)/800 = 0,0876 → σ = 0,296 buyin
       Sai số chuẩn quan sát: 0,347 (mẫu tình cờ nhiều lần về nhất;
       chương trình mô phỏng cho T xác suất như nhau ở mọi hạng có tiền
       → lại một lần bị nhiễu ngẫu nhiên đánh lừa)
                                │
                                ▼
       Khoảng chuẩn từ số quan sát: [0,3802; 1,7675] — sai ở cả hai phía
       · phía trên: dùng công thức theo tỷ lệ thắng, +2σ = 1,666; tỷ lệ
         thắng cao hơn bị loại (giới hạn thật còn thấp hơn chút)
       · phía dưới: Chebyshev: xác suất tỷ lệ thắng thật thấp hơn 2σ dưới
         trung bình (dưới 0,4818) không quá 1/4
```

### Phần "Key Concepts" — các khái niệm then chốt (trang 359–360)

```text
       1. Nhiều công thức equity đã được đề xuất để ánh xạ equity chip
          sang equity giải ở cuối giải
       2. Landrum-Burns và tỷ lệ chip có khuyết điểm rõ nhưng dễ tính tại
          bàn; lệch ngược chiều nhau nên tính cả hai cho một khoảng chứa
          equity thật
       3. Malmuth-Harville và Malmuth-Weitzman chính xác hơn nhưng khó
          tính tại bàn hơn
       4. Khoảng tin cậy cho equity giải đấu đặc biệt vì độ lệch lớn và vì
          phương sai mỗi giải tương quan mạnh với tỷ lệ thắng; tận dụng hai
          điều này để có khoảng tin cậy chính xác hơn ngay cả khi dữ liệu
          chưa đủ ý nghĩa thống kê
```

## Ba câu hỏi chương này trả lời

1. **Chip ở cuối giải đáng bao nhiêu tiền, và vì sao không chia theo tỷ lệ chip được?** Vì tiền thưởng trả theo thứ tự bị loại, chồng chip lớn không thể nhận nhiều hơn giải nhất, và người có ít chip vẫn có thể leo hạng. Chia theo tỷ lệ chip (⟨X_i⟩ = v_n + s_i·W_n) tương đương giả định xác suất về mỗi hạng đều bằng s_i, nên với chồng 48.000 trên 60.000 chip, người dẫn đầu được 2.460 đô la, hơn giải nhất 2.000 đô la. Các công thức khác: Landrum-Burns (1.800 đô la, thiên vị chồng nhỏ), Malmuth-Harville và Malmuth-Weitzman (người tổng hợp tính được khoảng 1.865 và 1.836 đô la), nằm giữa hai cực.
2. **Công thức nào nên dùng?** Tỷ lệ chip và Landrum-Burns dễ tính và cho cận trên, cận dưới cho chồng lớn; Malmuth-Harville (xác suất về hạng j bằng x_i chia tổng x của những người còn lại) chính xác hơn trong đa số trường hợp nhưng khó tính tại bàn khi nhiều người; Malmuth-Weitzman (chip của người bị loại chia đều, nên xác suất bị loại tiếp tỷ lệ nghịch với chip: p_k = (1/x_k)/Σ(1/x_i)) là lựa chọn ưa thích của tác giả khi tính thoả thuận ở bàn chung kết.
3. **Làm sao biết một người chơi giải đấu có thật sự thắng?** Kết quả giải đấu lệch phải rất mạnh (độ lệch khoảng √n cho giải winner-take-all n người), phương sai tương quan với tỷ lệ thắng, nên khoảng tin cậy chuẩn từ dữ liệu quan sát không đáng tin. Tác giả đề xuất dùng phương sai suy từ cơ cấu thưởng và tỷ lệ thắng: σ² = (k̄ − ω)(1 + ω)/m với k = n·Σv_i² − 1; loại các tỷ lệ thắng quá cao bằng kiểm định z (an toàn vì đuôi trái mỏng), và chặn phía dưới bằng bất đẳng thức Chebyshev. Với người chơi T sau 800 giải, σ ≈ 0,296 buyin, các tỷ lệ thắng trên 1,666 bị loại, và khả năng tỷ lệ thắng thật dưới 0,48 không quá 1/4. Muốn σ khoảng 1 buyin thì phải chơi khoảng k giải.

## Khái niệm cần biết

- **Equity giải thưởng (prize equity), ⟨X_i⟩:** giá trị tiền kỳ vọng của chồng chip người i, ⟨X_i⟩ = Σ_j p_{i,j}·v_j. Ví dụ: theo Landrum-Burns, người có 48.000 trên 60.000 chip có ⟨X_1⟩ = 1.800 đô la. Đây là đại lượng cần tối đa hoá, và là cơ sở của thoả thuận chia tiền.
- **Phần chip s_i và xác suất về nhất x_i:** s_i = S_i/T; với người ngang tài, x_i = s_i. Ví dụ: 25.000 trên 60.000 chip cho s = 5/12 = 0,417. Mọi công thức trong chương lấy x_i làm đầu vào.
- **Quỹ tăng thêm (incremental prize pool) W_n:** phần quỹ còn lại sau khi trừ phần ai cũng chắc chắn nhận, W_n = V_n − n·v_n. Ví dụ: 5.000 − 4 × 700 = 2.200 đô la. Vì v_n là hằng số, quyết định tối ưu với quỹ gộp và quỹ tăng thêm là như nhau.
- **Bubble và vào vùng có thưởng (in the money):** vào vùng có thưởng khi người bị loại tiếp theo cũng nhận tiền (v_n > 0); bubble là ngay trước đó (v_n = 0, v_{n−1} > 0). Ví dụ: còn 19 người, trả 18 hạng.
- **Công thức chia theo tỷ lệ chip (proportional chip count):** ⟨X_i⟩ = v_n + s_i·W_n. Ví dụ: 700 + (5/12)(2.200) = 1.616,67 đô la. Dễ tính, nhưng cho chồng lớn quá nhiều tiền.
- **Hàm phần nguyên (floor function) ⌊y⌋:** số nguyên lớn nhất không vượt y. Ví dụ: ⌊1/(5/12)⌋ = ⌊2,4⌋ = 2. Dùng trong bản sửa của công thức tỷ lệ chip.
- **Công thức Landrum-Burns:** xác suất về nhất x_i, phần còn lại 1 − x_i chia đều cho n − 1 hạng còn lại. Ví dụ: người có 1/15 chip trong bốn người có xác suất về mỗi hạng 2–4 là (14/15)/3 = 14/45. Thiên vị chồng nhỏ.
- **Công thức Malmuth-Harville:** xác suất về hạng tiếp theo bằng x_i chia tổng x của những người chưa có hạng. Ví dụ: người dẫn đầu (x = 0,8) về nhì khi người có x = 1/15 về nhất với xác suất 0,8/(1 − 1/15) = 0,857. Chính xác hơn, khó tính khi nhiều người.
- **Công thức Malmuth-Weitzman:** giả định chip của người bị loại chia đều cho những người còn lại; hệ quả là xác suất bị loại tiếp p_k = (1/x_k)/Σ(1/x_i). Ví dụ: chồng 48.000 / 4.000 / 4.000 / 4.000: b = 1,25 + 15 × 3 = 46,25, p₁ = 1,25/46,25 = 0,027, mỗi chồng nhỏ 15/46,25 = 0,324. Công thức "ngang tài" mà tác giả dùng làm mốc khi thoả thuận.
- **Thoả thuận chia tiền (deal):** những người còn lại đồng ý chia quỹ thay vì chơi tiếp. Ví dụ: bốn người cuối chia 5.000 đô la theo một công thức equity. Các công thức của chương là cơ sở thương lượng.
- **Độ lệch (skew):** S = ⟨(X − μ)³⟩/σ³, đo mức bất đối xứng của phân phối. Ví dụ: giải winner-take-all 1.000 người có S ≈ 31,6. Độ lệch lớn làm phân phối chuẩn không dùng được cho mẫu nhỏ.
- **Cỡ giải s, chi phí b_c và phí tham gia ε_b:** s = V/n là phần quỹ trên mỗi người; b_c là tiền mỗi người trả; ε_b = b_c − s. Ví dụ: s = 166,67, b_c = 110, ε_b = −56,67 khi sòng bài bảo đảm quỹ. Phí là phần kỹ năng không bù được.
- **Tỷ lệ thắng chuẩn hoá ω (normalized win rate):** ω = w₀/s = Σ(n·p_i)·v_i − 1, số buyin (theo cỡ giải) lãi kỳ vọng mỗi giải. Ví dụ: người chơi T có ω ≈ 1,07.
- **Kết quả chuẩn hoá Z (normalized win):** Z = (X − s)/s, có ⟨Z⟩ = ω; giá trị hay gặp nhất là −1 (không có tiền). Ví dụ: về nhất giải sáng 100 người được Z = 29.
- **Bội số phương sai giải đấu k (tournament variance multiple):** k = n·Σv_i² − 1; phương sai một giải là (k − ω)(1 + ω). Ví dụ: giải sáng có k = 16,105; giải winner-take-all n người có k = n − 1. Quan trọng vì cho phương sai đáng tin hơn phương sai quan sát.
- **Bất đẳng thức Chebyshev (Tchebyshev's Rule):** với mọi phân phối, xác suất lệch khỏi trung bình quá a độ lệch chuẩn không quá 1/a². Ví dụ: a = 2 cho 1/4. Dùng được dù phân phối lệch mạnh.
- **Điểm z (z-score):** z = (giá trị quan sát − giá trị kỳ vọng)/độ lệch chuẩn. Ví dụ: z = (ω̂ − ω)/σ(ω) < −2 thì loại ω ở mức 95%.

## Nội dung chi tiết

### 1. Khảo sát các công thức equity: mục đích và ký hiệu (A Survey of Equity Formulas, trang 346–347)

Lý thuyết Nhân đôi không được thiết kế cho các tình huống gần vùng có thưởng hay ở bàn chung kết. Thế nhưng gần cuối giải, ta thường muốn có một ánh xạ tường minh từ chồng chip sang giá trị tiền, hoặc vì có thể thoả thuận chia tiền (khi luật giải cho phép), hoặc để tính tới việc cơ cấu trả thưởng làm méo ánh xạ chip–tiền, nhờ đó ra quyết định chính xác hơn.

Đáng chú ý là hai nguồn méo chính (kỹ năng và cơ cấu trả thưởng) tác động ở những thời điểm khác nhau. Đầu giải, cơ cấu thưởng tương đối ít quan trọng nhưng kỹ năng có tác dụng lớn nhất. Ngược lại, cuối giải, blind thường cao nên kỹ năng giảm tác dụng khá nhiều (dù kỹ năng riêng là chơi ít người — shorthanded — có thể nổi bật), còn ảnh hưởng của cơ cấu thưởng lên ánh xạ là lớn nhất.

Dù sao, không có câu trả lời dễ cho việc ánh xạ chồng chip sang equity giải thưởng, kể cả với người ngang tài. Nhiều cách đã được đề xuất. Chương trình bày một số mô hình và bình luận về thiên lệch của từng mô hình, bắt đầu bằng định nghĩa:

- Mỗi người trong n người còn lại có chồng chip S_i. **Tổng số chip còn lại** T = Σ S_i.
- **Phần chip** của một người: s_i = S_i/T. Tổng mọi s_i bằng 1.
- v_j là tiền thưởng hạng j. Tổng mọi giải thưởng là quỹ V. **Quỹ còn phải trả** khi còn n người: V_n = Σ_{k=1}^{n} v_k.
- **Quỹ tăng thêm** (incremental prize pool): phần còn phải phân định giữa những người về các hạng khác hạng n. Gọi w_j là phần tăng thêm của hạng j và W_n là quỹ tăng thêm cộng dồn tới hạng n:

```text
w_j = v_j − v_n
W_n = Σ_{j=1}^{n} w_j = V_n − n·v_n
```

Vì v_n là hằng số (ai cũng chắc chắn nhận ít nhất v_n), quá trình ra quyết định trong giải với quỹ gộp và với quỹ tăng thêm là như nhau.

Giải được coi là **vào vùng có thưởng** (in the money) nếu v_n > 0, tức người bị loại tiếp theo vẫn nhận tiền. Giải ở **bubble** khi v_n = 0 nhưng hạng ngay trên có tiền, v_{n−1} > 0 (sách in v_{n+1}, xem khối Lưu ý).

Gọi p_{i,j} là xác suất người i về hạng j. Công thức equity giải thưởng cơ bản:

```text
⟨X_i⟩ = Σ_{j=1}^{n} p_{i,j}·v_j
```

Phần lớn các công thức equity đã được đề xuất giả định xác suất về nhất p_{i,1} xấp xỉ bằng phần chip s_i. Điều này đúng nếu người chơi ngang tài; khi không ngang tài, có thể dùng các phương pháp như Lý thuyết Nhân đôi để ước lượng xác suất về nhất. Thay vì dùng chồng chip làm đại diện cho xác suất về nhất, tác giả định nghĩa x_i là xác suất người i về nhất; có thể thay bằng bất kỳ phương pháp sinh xác suất nào. Các công thức equity thường coi xác suất về nhất là cho trước, rồi đưa ra một cách đơn giản để gán xác suất cho các hạng còn lại.

### 2. Công thức chia theo tỷ lệ chip (The Proportional Chip Count Formula, trang 347–349)

Mô hình đầu tiên là phương pháp "đếm chip" được dùng thường xuyên:

```text
⟨X_i⟩ = v_n + s_i·W_n                                        (27.1)
```

Mô hình gồm hai phần: trước hết mọi người nhận giá trị của hạng mà họ chắc chắn đạt được; sau đó phần quỹ còn lại chia cho mọi người theo số chip.

**Ví dụ 1.** Bốn người còn lại với chồng chip 25.000, 20.000, 10.000 và 5.000 (tổng 60.000); thưởng 2.000, 1.400, 900 và 700 đô la. Quỹ còn lại 5.000 đô la được chia: 2.800 đô la chia đều làm phần đảm bảo (700 mỗi người), 2.200 đô la còn lại chia theo chip (sách in nhầm 2.600):

| Người chơi | Chip | s_i | ⟨X_i⟩ = 700 + s_i × 2.200 |
|---|---:|---:|---:|
| 1 | 25.000 | 5/12 | 1.616,67 |
| 2 | 20.000 | 1/3 | 1.433,33 |
| 3 | 10.000 | 1/6 | 1.066,67 |
| 4 | 5.000 | 1/12 | 883,33 |
| Tổng | 60.000 | 1 | 5.000,00 |

Thoạt nhìn các con số này có vẻ hợp lý. Nhưng khuyết điểm lộ ra ngay khi đổi chồng chip:

**Ví dụ 2.** Người 1 có 48.000, ba người kia mỗi người 4.000:

```text
Người 1:    700 + (4/5)(2.200)  = 2.460
Người 2–4:  700 + (1/15)(2.200) = 846,67
```

Rõ ràng không đúng: người 1 có vẻ được nhận nhiều hơn giải nhất! Đây là khuyết điểm hệ thống của phương pháp: nó có xu hướng chia quá nhiều quỹ theo **chip** và quá ít theo **ghế** (theo việc còn ngồi trong giải). Chồng chip càng đều, công thức càng chính xác. Nhưng điều này đúng với mọi mô hình: mô hình nào không cho tiền bằng nhau khi các x_i bằng nhau thì không thể đúng.

**Nguyên nhân.** Mô hình này tương đương việc nói p_{i,j} = s_i cho mọi j (áp lên quỹ tăng thêm: Σ_j s_i·w_j = s_i·W_n). Giả sử người chơi là người dẫn đầu chip (ngang tài). Xác suất về nhất của họ lớn hơn của mọi người khác, nhưng theo mô hình, xác suất về nhì, ba, tư… tới hạng n cũng bằng như vậy. Tổng xác suất về một hạng nào đó là n·s_i. Nếu s_i > 1/n, tổng này vượt 1, điều rõ ràng sai. Ví dụ 2: 4 × 0,8 = 3,2.

**Bản sửa.** Có thể buộc các xác suất về hạng có tổng bằng một:

```text
m = ⌊1/x_i⌋
p_{i,j} = x_i            với j ≤ m
p_{i,m+1} = 1 − m·x_i
```

Dấu ngoặc ⌊ ⌋ là hàm phần nguyên (floor), cho số nguyên lớn nhất không vượt quá biểu thức bên trong. Do đó nếu x_i > 0,5 thì m = 1 và p_{i,1} = x_i, p_{i,2} = 1 − x_i. Xấp xỉ này hợp lý hơn khi chồng chip rất lớn.

Với người 1 ở ví dụ 1 (5/12 chip): 1/(5/12) = 2,4 nên m = 2, và p_{1,1} = 5/12, p_{1,2} = 5/12, p_{1,3} = 1 − 10/12 = 1/6 (sách in 1/16). Equity sửa lại, dùng thưởng tăng thêm w₁ = 1.300, w₂ = 700, w₃ = 200:

```text
⟨X_1⟩ = 700 + (5/12)(1.300) + (5/12)(700) + (1/6)(200)
      = 700 + 541,67 + 291,67 + 33,33 = 1.566,67
```

Người tổng hợp áp dụng thêm cho ví dụ 2: x = 0,8 > 0,5, m = 1, ⟨X_1⟩ = 700 + 0,8 × 1.300 + 0,2 × 700 = 1.880 đô la — không còn vượt giải nhất.

Tiếc là bản sửa làm tổng equity không còn bằng tổng quỹ (mỗi người được sửa riêng, không ai bị trừ tương ứng). Vì vậy nó chủ yếu hữu ích để đặt một cận trên thấp hơn một chút cho equity của người dẫn đầu. Nó vẫn thiên vị khá nhiều cho chồng lớn.

### 3. Công thức Landrum-Burns (The Landrum-Burns Formula, trang 349–350)

Mô hình thứ hai do Stephen Landrum và Jazbo Burns đề xuất trên nhóm tin rec.gambling.poker:

- Tính xác suất về nhất của mỗi người.
- Giả định rằng khi không về nhất, người đó về các hạng còn lại với tần suất bằng nhau.

```text
⟨X_i⟩ = p_{i,1}·v₁ + Σ_{k=2}^{n} [(1 − p_{i,1}) / (n − 1)]·v_k            (27.2)
```

**Ví dụ 1** (chip 25.000 / 20.000 / 10.000 / 5.000; v₂ + v₃ + v₄ = 1.400 + 900 + 700 = 3.000):

| Người chơi | p_{i,1} | Xác suất mỗi hạng 2–4 | ⟨X_i⟩ |
|---|---:|---:|---:|
| 1 | 5/12 | 7/36 | (5/12)(2.000) + (7/36)(3.000) = 833,33 + 583,33 = 1.416,67 |
| 2 | 1/3 | 2/9 | 666,67 + 666,67 = 1.333,33 |
| 3 | 1/6 | 5/18 | 333,33 + 833,33 = **1.166,67** (sách in 1.066,67) |
| 4 | 1/12 | 11/36 | 166,67 + 916,67 = 1.083,33 |
| Tổng | | | 5.000,00 |

(Sách in v₁ là "2200" trong các dòng này; giá trị đúng là 2.000, xem khối Lưu ý.)

**Ví dụ 2** (48.000 / 4.000 / 4.000 / 4.000):

```text
Người 1:   (4/5)(2.000) + (1/15)(1.400) + (1/15)(900) + (1/15)(700) = 1.600 + 200 = 1.800
Người 2–4: (1/15)(2.000) + (14/45)(1.400) + (14/45)(900) + (14/45)(700) = 133,33 + 933,33 = 1.066,67
```

Con số 1.800 ít ra "hợp lý" vì không vượt giải nhất (như đã xảy ra với phương pháp đếm chip). Tuy nhiên, khi tính trực tiếp, một khó khăn của phương pháp lộ ra. Người 1 có thể phản đối rằng nếu không thắng, khả năng mình về tư không bằng khả năng về nhì. Thực ra, nếu blind khá cao, người đó rất hiếm khi về tư. Vì vậy giá "công bằng" phải được điều chỉnh lên so với giá trị Landrum-Burns. Tương tự, một người có chồng chip rất nhỏ so với đối thủ thì khả năng về nhì không bằng khả năng về tư.

Đây là thiên lệch của Landrum-Burns: nó định giá cao chồng nhỏ và định giá thấp chồng lớn, vì chồng lớn không bị loại ngay thường xuyên bằng việc về nhì. Phương pháp tỷ lệ chip và Landrum-Burns cùng nhau cho một cận dưới và một cận trên cho các giá trị hợp lý; giá trị công bằng "thật" nằm đâu đó ở giữa.

### 4. Công thức Malmuth-Harville (The Malmuth-Harville Formula, trang 350–351)

Trong sách *Gambling Theory and Other Topics*, Mason Malmuth giới thiệu thêm hai công thức equity. Công thức thứ nhất tương tự công thức Harville trong đua ngựa. Về cơ bản, công thức làm như sau:

- Xác suất về nhất của mỗi người là x_i.
- Xác suất về nhì của người i với điều kiện người k đã về nhất:

```text
p(X_{i,2} | X_{k,1}) = x_i / (1 − x_k)
```

Khi đó xác suất về nhì (theo công thức xác suất toàn phần, cộng theo mọi người có thể về nhất):

```text
p_{i,2} = Σ_{k≠i} p(X_{i,2} | X_{k,1})·p(X_{k,1}) = Σ_{k≠i} x_i·x_k / (1 − x_k)
```

Công thức này ban đầu được phát triển để đặt cược cho ngựa được ưa chuộng trong các pool "show" hoặc "place" (cược ngựa về trong top ba hoặc top hai) của đua ngựa. Tuy nhiên, theo một ý mà Jeff Yass chỉ ra cho tác giả, công thức thực ra còn hợp với poker giải đấu hơn. Trong đua ngựa, nếu một con ngựa được cực kỳ ưa chuộng (x gần 1), phần lớn những lần nó không thắng là do một trục trặc cũng ngăn nó về nhì, như chấn thương hay bị truất quyền. Chẳng hạn, khó tin rằng một con ngựa có 80% khả năng thắng vẫn có hơn 80% khả năng về nhì nếu không thắng, và càng khó tin rằng nó có hơn 99% khả năng về top ba. Nhưng trong poker giải đấu, hiệu ứng này nhỏ: nếu chồng chip lớn không thắng, người đó vẫn rất có thể về nhì và rất khó về chót.

Tổng quát hoá quy tắc:

```text
p(X_{i,j} | X_{1,1} ∧ X_{2,2} ∧ … ∧ X_{j−1,j−1}) = x_i / (1 − x₁ − … − x_{j−1})        (27.3)
```

(trong đó người 1, 2, …, j − 1 là những người đã về các hạng 1 đến j − 1). Nghĩa là xác suất về hạng j đơn giản là tỷ số giữa xác suất thắng của người đó và tổng xác suất thắng của những người còn lại. Trong đa số trường hợp, công thức này biểu diễn equity chính xác hơn cả công thức tỷ lệ chip lẫn Landrum-Burns.

Hạn chế: khi còn nhiều người, khá khó tính tại bàn vì số hoán vị thứ tự về đích lớn (n! hoán vị). Vì vậy nó chủ yếu hữu ích để hiểu tình huống khi rời bàn hoặc phân tích các tình huống lặp lại thường xuyên, như equity ở giải sit-and-go (giải một bàn, bắt đầu khi đủ người).

**Áp dụng của người tổng hợp** (tính đủ 24 hoán vị bằng máy cho hai ví dụ trên):

Ví dụ 1 — ma trận xác suất về hạng theo Malmuth-Harville:

| Người chơi | Về nhất | Về nhì | Về ba | Về tư | Equity (đô la) |
|---|---:|---:|---:|---:|---:|
| 1 (25.000) | 0,4167 | 0,3295 | 0,1941 | 0,0597 | 1.511,17 |
| 2 (20.000) | 0,3333 | 0,3351 | 0,2410 | 0,0906 | 1.416,08 |
| 3 (10.000) | 0,1667 | 0,2175 | 0,3506 | 0,2652 | 1.139,07 |
| 4 (5.000) | 0,0833 | 0,1179 | 0,2143 | 0,5845 | 933,69 |

Ví dụ 2: người dẫn đầu có xác suất về nhất, nhì, ba, tư là 0,800; 0,171; 0,026; 0,002, equity 1.865,27 đô la; mỗi chồng nhỏ 1.044,91 đô la. Đúng như lập luận của Jeff Yass, người dẫn đầu gần như không bao giờ về chót, và equity của họ nằm giữa 1.800 (Landrum-Burns) và 2.460 (tỷ lệ chip).

### 5. Công thức Malmuth-Weitzman (The Malmuth-Weitzman Formula, trang 351–352)

Mô hình thứ hai Malmuth đề xuất trong cùng sách do Mark Weitzman phát triển; tác giả gọi là công thức Malmuth-Weitzman. Trong sách đó, Malmuth có vẻ ưa công thức này hơn Malmuth-Harville, dù ông cho rằng mỗi tình huống phải giải một hệ phương trình tuyến tính. Chen và Ankenman cho rằng công thức này kém chính xác hơn Malmuth-Harville một chút, nhưng việc giải hệ phương trình là không cần thiết, như sẽ thấy.

Ý chính: khi một người bị loại, chip của họ được chia đều (tính trung bình) cho các đối thủ. Xác suất về nhất của người i, cộng theo mọi khả năng người k bị loại tiếp theo:

```text
x_i = P(X_{i,1}) = Σ_{k≠i} P(X_{i,1} | X_{k,n})·P(X_{k,n}) = Σ_{k≠i} (x_i + x_k/(n − 1))·p_{k,n}
```

(nếu người k bị loại, người i nhận thêm 1/(n − 1) chip của k, nên xác suất thắng của i thành x_i + x_k/(n − 1)). Điều này cho một hệ phương trình cần giải: với mỗi người có một ẩn p_{i,n} là xác suất bị loại tiếp theo.

Ví dụ bốn người (viết p_k thay cho p_{k,n}, đều là xác suất bị loại tiếp theo):

```text
x₁ = (x₁ + x₂/3)·p₂ + (x₁ + x₃/3)·p₃ + (x₁ + x₄/3)·p₄
x₂ = (x₂ + x₁/3)·p₁ + (x₂ + x₃/3)·p₃ + (x₂ + x₄/3)·p₄
x₃ = (x₃ + x₁/3)·p₁ + (x₃ + x₂/3)·p₂ + (x₃ + x₄/3)·p₄
x₄ = (x₄ + x₁/3)·p₁ + (x₄ + x₂/3)·p₂ + (x₄ + x₃/3)·p₃
```

(phương trình thứ tư sách in nhầm x₁ ở số hạng đầu). Bốn phương trình, bốn ẩn, có thể giải trực tiếp bằng đại số. Nhưng có cách tốt hơn: tác giả nói các phương trình này thuộc họ phương trình Vandermonde, và đưa luôn nghiệm rồi chứng minh nó đúng. Họ khẳng định hệ trên cho thấy **xác suất bị loại tiếp theo tỷ lệ nghịch với số chip** (hay xác suất thắng). Đặt b là tổng nghịch đảo các xác suất thắng:

```text
b = Σ 1/x_i
p_{k,n} = (1/x_k) / b                                        (27.4)
```

**Kiểm tra.** Thay vào công thức:

```text
x_i = Σ_{k≠i} (x_i + x_k/(n − 1))·(1/x_k)/b
    = (1/b)·Σ_{k≠i} (x_i/x_k + 1/(n − 1))
    = (1/b)·[x_i·Σ_{k≠i} 1/x_k + (n − 1)·1/(n − 1)]
```

Tổng Σ_{k≠i} 1/x_k chính là b − 1/x_i. Vậy:

```text
x_i = (1/b)·(x_i·(b − 1/x_i) + 1) = (1/b)·(b·x_i − 1 + 1) = x_i   ✓
```

Hệ phương trình tuyến tính sinh ra từ giả định của mô hình kéo theo: xác suất một người bị loại tiếp theo tỷ lệ với nghịch đảo số chip (hay xác suất thắng) của người đó. (Nghiệm cũng thoả Σ p_{k,n} = 1, đúng như một phân phối xác suất.)

**Đánh giá.** Malmuth-Weitzman cũng là công thức hợp lý, và có lẽ nằm ở giới hạn khả năng tính tại bàn của một số người chơi, điều làm nó hữu ích hơn. Một phản đối: công thức hơi khó chịu khi còn nhiều bàn. Nếu hai người có chồng chip khá ngắn ở hai bàn khác nhau, có vẻ phản trực giác khi người có gấp đôi chip lại có nửa xác suất bị loại. Cũng hơi khó hiểu vì sao người ở bàn khác cũng được nhận phần bằng nhau từ chip của người bị loại. Tuy vậy, nhìn chung đây là công thức tác giả ưa thích nhất để đánh giá giải khi đang ở hoặc gần vùng có thưởng. Khi đánh giá thoả thuận ở bàn chung kết, tác giả dùng Malmuth-Weitzman làm công thức "ngang tài" cơ sở.

**Áp dụng của người tổng hợp.** Để ra equity đầy đủ, dùng công thức đệ quy: xác suất bị loại tiếp theo theo (27.4), chia chip của người bị loại đều cho những người còn lại, rồi lặp lại với n − 1 người. Ví dụ 1: 1.487,18 / 1.401,67 / 1.152,09 / 959,06 đô la. Ví dụ 2: 1.836,13 cho người dẫn đầu, 1.054,62 cho mỗi chồng nhỏ. So sánh bốn công thức cho người dẫn đầu ở ví dụ 1: tỷ lệ chip 1.616,67 > Malmuth-Harville 1.511,17 > Malmuth-Weitzman 1.487,18 > Landrum-Burns 1.416,67 — hai công thức của Malmuth nằm giữa hai cận như tác giả nói.

| Ví dụ 1, đô la | Người 1 (25.000) | Người 2 (20.000) | Người 3 (10.000) | Người 4 (5.000) |
|---|---:|---:|---:|---:|
| Tỷ lệ chip | 1.616,67 | 1.433,33 | 1.066,67 | 883,33 |
| Landrum-Burns | 1.416,67 | 1.333,33 | 1.166,67 | 1.083,33 |
| Malmuth-Harville | 1.511,17 | 1.416,08 | 1.139,07 | 933,69 |
| Malmuth-Weitzman | 1.487,18 | 1.401,67 | 1.152,09 | 959,06 |

**Bài học chung.** Có nhiều cách ánh xạ số chip sang equity giải. Vì tất cả đều là mô hình, chúng vốn có một kiểu thiên lệch nào đó. Hiểu các phương pháp phổ biến và thiên lệch của chúng giúp ra quyết định trong giải tốt hơn và thoả thuận có lợi hơn khi có dịp.

### 6. Kết quả giải đấu và khoảng tin cậy: vấn đề (Tournament Results and Confidence Intervals, trang 352–353)

Ở Phần I, tác giả đã bàn khoảng tin cậy cho tỷ lệ thắng. Với cash game, khoảng tin cậy tính theo cách thông thường, vì kết quả cash game về bản chất là tổng của nhiều kết quả từng ván, chịu luật số lớn. Với giải đấu, xây khoảng tin cậy không dễ như vậy; làm theo cách thông thường không cho phân tích chính xác nhất.

**Ví dụ giải 1.000 người.** Xét một giải winner-take-all 1.000 người, và giả định mọi tỷ lệ thắng trong tổng thể nằm giữa −1 và +1 buyin mỗi giải. Chơi giải một lần: người thắng vừa trải qua một sự kiện cỡ 30 độ lệch chuẩn. (Người tổng hợp kiểm tra: với ω ≈ 0, phương sai một giải là k = n − 1 = 999, độ lệch chuẩn √999 = 31,6 buyin; người thắng lãi 999 buyin, tức 999/31,6 ≈ 31,6 độ lệch chuẩn.) Nhưng lần nào chơi cũng có người thắng. Chơi mười lần cũng không giúp được bao nhiêu.

Một khác biệt nữa: ở cash game, ước lượng phương sai hội tụ nhanh vì phân phối của nó (chi bình phương); với giải đấu, ta thường không có ước lượng phương sai tốt. Phương sai cũng tương quan mạnh với tỷ lệ thắng, vì trong giải đấu mọi biến cố có phương sai lớn đều là biến cố dương (về hạng cao), còn biến cố âm có phương sai nhỏ (thường là −1 buyin).

Vấn đề thật sự là với giải đấu, cần nhiều mẫu hơn hẳn trước khi phân phối hội tụ về phân phối chuẩn. Một vấn đề là **độ lệch** (skew), đã bàn sơ ở Chương 22:

```text
S = ⟨(X − μ)³⟩ / σ³
```

Độ lệch của một giải winner-take-all n người khoảng √n, trong khi độ lệch của phân phối chuẩn bằng 0. (Người tổng hợp: kết quả là biến Bernoulli với xác suất thắng p = 1/n, độ lệch (1 − 2p)/√(p(1 − p)) ≈ √n; n = 1.000 cho 31,6.) Độ lệch của tổng (hay trung bình) của n biến cố độc lập cùng phân phối bằng độ lệch của một biến cố chia √n. Khi mẫu ngày càng lớn, độ lệch của mẫu tiến về 0; đây là một trong những cách phân phối lấy mẫu dần hội tụ về phân phối chuẩn. Nhưng ở đây cần hơn n mẫu để độ lệch xuống dưới 1 (√n/√m < 1 khi m > n): với giải 1.000 người, cần hơn 1.000 giải.

### 7. Các đại lượng chuẩn hoá (trang 353–354)

Dù vậy vẫn có thể xử lý vấn đề. Kỳ vọng lợi nhuận gộp của một giải:

```text
⟨X⟩ = Σ p_i·V_i
```

với V_i là tiền thưởng hạng i. Gọi V là tổng quỹ, và v_i là phần quỹ trả cho hạng i: v_i = V_i/V.

Giả định không có rebuy và add-on, định nghĩa **cỡ giải** (size) là quỹ chia số người: s = V/n.

Thêm vào đó là **chi phí** của giải b_c, tổng số tiền mỗi người phải trả để chơi. Chênh lệch giữa hai đại lượng là **phí tham gia** (entry fee), có thể dương (người chơi trả phí cho sòng bài tổ chức giải) hoặc âm (sòng bài bỏ thêm tiền vào giải để bảo đảm quỹ hay khuyến mãi). Ký hiệu phí là ε_b:

```text
ε_b = b_c − s
```

Ví dụ: giải 100 + 10 đô la, sòng bài bảo đảm quỹ 50.000 đô la. 100 đô la trong 110 đô la mỗi người trả vào quỹ, phần còn lại cho sòng bài. Nếu quỹ thiếu 50.000 đô la, sòng bài bù phần chênh. Với 300 người (quỹ từ phí là 30.000, sòng bài bù 20.000):

```text
s   = 50.000/300 = 166,67 đô la
b_c = 110 đô la
ε_b = 110 − 166,67 = −56,67 đô la   (sách in +56,67)
```

Kỳ vọng ròng w khi vào giải bằng kỳ vọng lợi nhuận gộp ⟨X⟩ trừ chi phí b_c:

```text
w = ⟨X⟩ − b_c = Σ p_i·V_i − s − ε_b
```

Biểu thức có hai phần. Phần đầu w₀ = Σ p_i·V_i − s gắn với kỹ năng poker và kỹ năng giải đấu; phần thứ hai ε_b không phụ thuộc kỹ năng poker, có lẽ trừ kỹ năng chọn giải.

**Tỷ lệ thắng chuẩn hoá** ω:

```text
ω ≡ w₀/s = Σ p_i·V_i/s − 1 = Σ (n·p_i)·V_i/V − 1 = Σ (n·p_i)·v_i − 1
```

(dùng s = V/n nên V_i/s = n·V_i/V = n·v_i). ω về cơ bản là số buyin (buyin chuẩn hoá theo cỡ giải) lãi kỳ vọng mỗi giải. Kiểm tra: người chơi trung bình có p_i = 1/n ở mọi hạng, nên ω = Σ v_i − 1 = 0.

Biến thống kê cần xét là **kết quả chuẩn hoá** Z:

```text
Z = (X − s)/s,     với tính chất ⟨Z⟩ = ω
```

Z là biến tác giả quan tâm vì nhiều lý do; ý tưởng là nắm được hành vi của Z rồi dùng nó xây khoảng tin cậy phù hợp. Lưu ý giá trị hay gặp nhất (mode) của Z thường là −1 (không có tiền).

### 8. Phương sai theo tỷ lệ thắng (trang 354–357)

Một giả định cho một biến Z phù hợp là

```text
p_i = (1 + ω)/n    cho mỗi hạng có thưởng i
```

Giả định này coi tỷ lệ thắng như một hệ số nhân lên xác suất về mỗi hạng có thưởng: bắt đầu từ việc người chơi về mỗi hạng với khả năng như nhau, rồi chuyển ω/n lượt "không có tiền" sang mỗi hạng có thưởng. Điều này trái với Lý thuyết Nhân đôi, vốn cho rằng người giỏi về nhất nhiều hơn về nhì, ba…; tuy vậy tác giả thấy xấp xỉ này khá hợp lý.

Nhắc lại (Chương 25): ⟨x²⟩ = μ² + σ², tức σ² = ⟨x²⟩ − μ². Với phân phối này, x = X − b_c và μ = ⟨X − b_c⟩. Phương sai của một giải (trừ hằng số b_c không đổi phương sai; tác giả viết b cho cỡ giải và ngầm coi b_c = s = b):

```text
σ_x² = ⟨(X − b_c)²⟩ − ⟨X − b_c⟩² = ⟨X²⟩ − ⟨X⟩²
σ_x² = Σ p_i·V_i² − ((1 + ω)·b)²
σ_x² = Σ ((1 + ω)/n)·(V·v_i)² − (1 + ω)²·b²
σ_x² = ((1 + ω)/n)·(n·b)²·Σ v_i² − (1 + ω)²·b²          (V = n·b)
σ_x² = [n·(Σ v_i²)·(1 + ω) − (1 + ω)²]·b²
```

Phương sai của Z:

```text
σ_Z² = σ_x²/b² = (n·Σ v_i² − 1 − ω)·(1 + ω)
```

Do đó phương sai của Z xấp xỉ tỷ lệ với 1 + ω với các giá trị ω hợp lý. Xét đại lượng

```text
k = n·Σ v_i² − 1                                             (27.5)
```

Tác giả nhận thấy biểu thức này gần với số người hiệu dụng tìm được ở Lý thuyết Nhân đôi, và gọi k là **bội số phương sai giải đấu** (tournament variance multiple). Người tổng hợp kiểm tra với giải đối kháng 256 người trả 154/102 buyin của Chương 26: k = 256 × ((154/256)² + (102/256)²) − 1 = 132,3, so với cỡ giải hiệu dụng 147,4 — cùng bậc nhưng không trùng. Với giải winner-take-all, Σv_i² = 1 nên k = n − 1, gần như đúng bằng n. Tác giả nhấn mạnh: dùng công thức trên cho phương sai của Z là ước lượng tốt hơn phương sai quan sát được của một mẫu, với mọi cỡ mẫu không khổng lồ.

**Nhiều giải độc lập.** Giả sử có m kết quả chuẩn hoá Z_j từ m giải. Trung bình của chúng là

```text
Z̄ = (Σ_{j=1}^{m} Z_j)/m
```

Vì các Z_j độc lập, phương sai của trung bình mẫu m giá trị Z là

```text
σ² = Σ σ²_{Z_j} / m² = Σ (k_j − ω)(1 + ω) / m² = (k̄ − ω)(1 + ω) / m          (27.6)
```

với k̄ là trung bình các k_j. Trong mọi hoàn cảnh bình thường, ω nhỏ hơn k rất nhiều, nên có thể xấp xỉ rất thô biểu thức trên bằng k/m. Khi đó, để phương sai của mẫu cỡ m bằng 1, phải chơi khoảng bằng số giải bằng bội số phương sai trung bình của các giải. Nếu phương sai mẫu bằng 1, có khoảng 68% khả năng tỷ lệ thắng quan sát cách trung bình tổng thể không quá 1 buyin (bỏ qua các hàm ý Bayes).

Tác giả gọi (27.6) là công thức **phương sai dựa trên tỷ lệ thắng** (win-rate-based variance), vì nó dùng tỷ lệ thắng quan sát và cơ cấu giải quan sát để tính phương sai. Khuyết điểm: thực tế, có tỷ lệ thắng ω thường không có nghĩa là xác suất về mọi hạng có thưởng đều tăng cùng một hệ số; kết quả của một số người "nặng đầu" hơn (nhiều lần về nhất hơn về nhì, ba), một số khác nghiêng về các hạng thấp. Một cách khác là dùng Lý thuyết Nhân đôi để dự báo tần suất về từng hạng rồi tính phương sai theo đó.

Lý do không dùng phương sai quan sát: trừ khi mẫu rất lớn, các công thức này cho ước lượng tốt hơn. Nếu m rất lớn, có thể dùng cách khác: dùng tỷ lệ thắng quan sát ω̂ và phương sai quan sát σ̂² (của trung bình mẫu) để tính k, bằng cách giải ngược (27.6):

```text
k = ω̂ + m·σ̂² / (1 + ω̂)
```

rồi dùng k này trong công thức phương sai dựa trên tỷ lệ thắng. Kỹ thuật này có lẽ chính xác hơn khi m rất lớn, vì phương sai quan sát hội tụ về phương sai thật nhanh hơn việc phân phối lấy mẫu hội tụ về phân phối chuẩn.

### 9. Kiểm định và bất đẳng thức Chebyshev (trang 357)

Câu hỏi mà khoảng tin cậy cần trả lời là: *nếu tỷ lệ thắng chuẩn hoá của ta là ω, kết quả quan sát của ta may mắn hay xui xẻo đến đâu?*

Không thể dùng chặt chẽ phân phối chuẩn làm hướng dẫn, vì phân phối lấy mẫu chưa hội tụ về phân phối chuẩn. Tuy nhiên, khi ω > ω̂ (tỷ lệ thắng giả thuyết lớn hơn quan sát), có thể dùng phân phối chuẩn để đổi điểm z (z = (giá trị quan sát − kỳ vọng)/độ lệch chuẩn) thành mức tin cậy (chẳng hạn cách quá 2 độ lệch chuẩn thì không qua kiểm định 95%):

```text
z = (ω̂ − ω)/σ(ω) < −2
```

Nếu bất đẳng thức đúng, có thể kết luận ω không qua kiểm định, vì phân phối lệch dương nên xác suất có một biến cố âm (kết quả thấp hơn kỳ vọng quá hai độ lệch chuẩn) thực ra còn nhỏ hơn phân phối chuẩn chỉ ra. Như vậy có thể loại một số tỷ lệ thắng rất cao dựa trên dữ liệu.

Nhưng với ω < ω̂ (sách in ω > ω̂, xem khối Lưu ý), phải cẩn thận hơn. Phân phối chuẩn không phù hợp, vì do độ lệch, kết quả quan sát là một biến cố dương có khả năng cao hơn phân phối chuẩn chỉ ra. Có thể dùng **bất đẳng thức Chebyshev** (Tchebyshev's Rule):

```text
P(z = (ω̂ − ω)/σ(ω) > a) < 1/a²
```

Nghĩa là xác suất kết quả vượt quá bốn độ lệch chuẩn về một phía của trung bình luôn nhỏ hơn 1/16. Công cụ này có vẻ thô — phân phối chuẩn cho giá trị tương ứng khoảng 0,00003 (người tổng hợp tính: P(z > 4) = 0,0000317) — nhưng có ưu điểm tuyệt vời là đúng với mọi phân phối, dù lệch đến đâu.

### 10. Ví dụ người chơi T (trang 357–359)

Người chơi giả định T chơi bốn giải 50 + 5 đô la mỗi ngày. Hai giải buổi sáng có khoảng 100 người, hai giải buổi tối khoảng 400 người.

**Bảng trả thưởng giải sáng (100 người):**

| Hạng | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Phần quỹ | 30% | 20% | 12% | 10% | 8% | 6% | 5,5% | 4,5% | 4% |

**Bảng trả thưởng giải tối (400 người):**

| Hạng | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10–18 | 19–27 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Phần quỹ (mỗi hạng) | 27,5% | 17,5% | 11,6% | 8% | 6% | 4,5% | 3,5% | 2,6% | 1,7% | 1,2% | 0,7% |

(Người tổng hợp kiểm tra: cả hai bảng có tổng đúng 100%, với 9 hạng ở mỗi nhóm 10–18 và 19–27.)

T đã chơi 200 ngày, có 400 kết quả giải sáng và 400 kết quả giải tối. (Các kết quả do chính tác giả sinh ngẫu nhiên bằng chương trình, với giả định xác suất về mỗi hạng có tiền như nhau.)

**Kết quả giải sáng:**

| Hạng | Số lần | Buyin gộp | Buyin ròng | Tổng ròng |
|---|---:|---:|---:|---:|
| 1 | 11 | 30 | 29 | 319 |
| 2 | 7 | 20 | 19 | 133 |
| 3 | 5 | 12 | 11 | 55 |
| 4 | 3 | 10 | 9 | 27 |
| 5 | 8 | 8 | 7 | 56 |
| 6 | 4 | 6 | 5 | 20 |
| 7 | 7 | 5,5 | 4,5 | 31,5 |
| 8 | 2 | 4,5 | 3,5 | 7 |
| 9 | 5 | 4 | 3 | 15 |
| Không có tiền | 348 | 0 | −1 | −348 |
| Tổng | 400 | | | 315,5 |

Tỷ lệ có tiền ở giải sáng là 52/400 = 13%. Tổng lãi 315,5 buyin, khoảng 0,79 buyin mỗi giải (chính xác 0,789).

**Kết quả giải tối:**

| Hạng | Số lần | Buyin gộp | Buyin ròng | Tổng ròng |
|---|---:|---:|---:|---:|
| 1 | 4 | 110 | 109 | 436 |
| 2 | 2 | 70 | 69 | 138 |
| 3 | 2 | 46,4 | 45,4 | 90,8 |
| 4 | 0 | 32 | 31 | 0 |
| 5 | 2 | 24 | 23 | 46 |
| 6 | 4 | 18 | 17 | 68 |
| 7 | 1 | 14 | 13 | 13 |
| 8 | 0 | 10,4 | 9,4 | 0 |
| 9 | 2 | 6,8 | 5,8 | 11,6 |
| 10–18 | 14 | 4,8 | 3,8 | 53,2 |
| 19–27 | 20 | 2,8 | 1,8 | 36 |
| Không có tiền | 349 | 0 | −1 | −349 |
| Tổng | 400 | | | 543,6 |

Ở giải tối, T lại có tiền khoảng 13% số lần (51/400 = 12,75%), tổng lãi 543,6 buyin, khoảng 1,36 buyin mỗi giải. (Buyin gộp = phần quỹ × 400, ví dụ 27,5% × 400 = 110; buyin ròng = gộp − 1, ở đây bỏ qua phí 5 đô la.)

Gộp lại, T đã chơi 800 giải với tỷ lệ thắng chung 1,07 buyin mỗi giải ((315,5 + 543,6)/800 = 1,0739). Thống kê:

```text
ω = 1,07;   m = 800;   Z̄ = 1,07
k = n·Σ v_i² − 1
Giải sáng:  k = 100 × (0,30² + 0,20² + … + 0,04²) − 1 = 100 × 0,17105 − 1 = 16,105
Giải tối:   k = 400 × (0,275² + 0,175² + … + 0,007²) − 1 = 53,26   (sách: 53,6456)
k̄ = 34,875   (theo số của sách; theo số tính lại là 34,68)
```

Phương sai của trung bình mẫu 800 giải, nửa sáng nửa tối, xấp xỉ:

```text
σ² = (k̄ − ω)(1 + ω)/m = (34,875 − 1,07)(1 + 1,07)/800 = 0,0876
σ  = 0,296 buyin
```

tức độ lệch chuẩn 0,296 buyin cho một mẫu 800 giải.

**So với số quan sát.** Sai số chuẩn quan sát được từ chính mẫu là khoảng 0,3468 buyin (sách gọi là "phương sai mẫu"; xem khối Lưu ý). Chênh lệch xảy ra vì mẫu hơi tập trung vào các lần về nhất (11 lần nhất ở giải sáng, so với kỳ vọng 400 × (1 + 0,79)/100 ≈ 7,2 nếu mọi hạng có tiền như nhau với tỷ lệ thắng 0,79 của giải sáng — người tổng hợp tính). Người đọc có thể phản bác rằng xu hướng về nhất nhiều hơn của T làm lệch phân phối thật. Trong thực tế điều đó có thể đúng, dù ảnh hưởng không lớn. Nhưng vì chính tác giả viết chương trình sinh ngẫu nhiên các kết quả trên, họ biết xác suất về nhất của T bằng xác suất về bất kỳ hạng có tiền nào khác. Đây lại là một trường hợp bị nhiễu ngẫu nhiên đánh lừa. (Người tổng hợp tính thêm: phương sai quan sát mỗi giải là 96,4, trong khi công thức cho (34,9 − 1,07)(2,07) ≈ 70; nếu dùng cách ước lượng ngược k = ω̂ + m·σ̂²/(1 + ω̂) = 1,07 + 800 × 0,1204/2,07 ≈ 47,5, lớn hơn hẳn k̄ ≈ 34,9 tính từ cơ cấu thưởng — minh hoạ vì sao tác giả chỉ khuyên dùng cách này khi m rất lớn.)

**Khoảng tin cậy.** Áp phân phối chuẩn vào tỷ lệ thắng và độ lệch chuẩn quan sát cho khoảng tin cậy 95% là [0,3802; 1,7675] (= 1,0739 ± 2 × 0,3468). Khoảng này chắc chắn không chính xác ở phía trên: vì phân phối lệch dương, khả năng tỷ lệ thắng thật cao hơn 1,7675 mà T gặp một biến cố rất âm thực ra thấp hơn phân phối chuẩn chỉ ra. Ở phía dưới, dùng phân phối chuẩn hoàn toàn không phù hợp, vì khả năng kết quả quan sát thực ra là một biến cố dương từ một tỷ lệ thắng thấp hơn cao hơn nhiều.

Dùng công thức phương sai dựa trên tỷ lệ thắng, T thực ra có phương sai nhỏ hơn. Hai độ lệch chuẩn phía trên là 1,666 buyin mỗi giải (1,0739 + 2 × 0,296). Con số này vẫn hơi chưa chính xác: thực ra, ở mức này, mẫu sẽ không qua kiểm định giả thuyết ở mức 95% (tức các tỷ lệ thắng thật từ 1,666 trở lên bị loại); giới hạn thật còn thấp hơn một chút, nhưng chỉ ít thôi. Ở phía kia, dùng bất đẳng thức Chebyshev có thể kết luận rằng khả năng phân phối thật thấp hơn 2 độ lệch chuẩn dưới trung bình quan sát (tức dưới 1,0739 − 2 × 0,296 = 0,4818) không quá 1/4.

### 11. Các khái niệm then chốt (Key Concepts, trang 359–360)

- Nhiều công thức equity đã được đề xuất để ánh xạ equity chip sang equity giải ở giai đoạn cuối giải.
- Phương pháp Landrum-Burns và Tỷ lệ chip có khuyết điểm rõ nhưng dễ tính tại bàn. Vì chúng lệch ngược chiều nhau, đánh giá cả hai có thể giúp xác định một khoảng chứa equity thật.
- Công thức Malmuth-Harville và Malmuth-Weitzman chính xác hơn nhưng khó thực hiện tại bàn hơn.
- Khoảng tin cậy cho equity giải đấu là chủ đề thú vị vì độ lệch đáng kể và vì phương sai mỗi giải tương quan mạnh với tỷ lệ thắng. Có thể dùng các điều này để có khoảng tin cậy chính xác hơn ngay cả khi chưa có dữ liệu có ý nghĩa thống kê mạnh (loại dữ liệu thường khó thu thập vì cần rất nhiều lượt chơi).

## Luận điểm cốt lõi

### Mệnh đề

Ở cuối giải, giá trị tiền của chip là hàm lõm của số chip: cơ cấu trả thưởng chuyển giá trị từ chồng lớn sang chồng nhỏ. Không có công thức đúng tuyệt đối; các công thức phổ biến đều là mô hình có thiên lệch biết trước, và có thể dùng các thiên lệch ngược chiều để kẹp giá trị thật. Kết quả giải đấu có phân phối lệch phải rất mạnh, nên đánh giá tỷ lệ thắng giải phải dùng phương sai suy từ cơ cấu thưởng và các bất đẳng thức không phụ thuộc phân phối.

### Giả định

- Người chơi ngang tài khi dùng x_i = s_i (có thể thay bằng xác suất từ Lý thuyết Nhân đôi).
- Mỗi công thức có giả định riêng về các hạng ngoài hạng nhất: đều bằng s_i (tỷ lệ chip), đều nhau (Landrum-Burns), tỷ lệ với x trong số người còn lại (Malmuth-Harville), chip của người bị loại chia đều (Malmuth-Weitzman).
- Phần thống kê: các giải độc lập; tỷ lệ thắng nhân đều xác suất về mọi hạng có thưởng (p_i = (1 + ω)/n); không có rebuy, add-on.

### Cơ chế

1. Chọn đầu vào x_i (phần chip hoặc xác suất thắng có tính kỹ năng).
2. Dùng một công thức để gán xác suất về từng hạng và cộng ra ⟨X_i⟩; tính cả tỷ lệ chip và Landrum-Burns để có khoảng, Malmuth-Harville hoặc Malmuth-Weitzman cho ước lượng điểm.
3. Ra quyết định (hay thương lượng thoả thuận) theo ⟨X_i⟩ thay vì theo số chip.
4. Đánh giá kết quả dài hạn: tính ω, k cho từng loại giải, σ² = (k̄ − ω)(1 + ω)/m; loại tỷ lệ thắng cao bằng kiểm định z, chặn phía dưới bằng Chebyshev.

### Bằng chứng và ví dụ tác giả đưa ra

- Bốn người, chip 25.000 / 20.000 / 10.000 / 5.000, thưởng 2.000 / 1.400 / 900 / 700 đô la: tỷ lệ chip cho 1.616,67 / 1.433,33 / 1.066,67 / 883,33; Landrum-Burns 1.416,67 / 1.333,33 / 1.166,67 / 1.083,33.
- Chip 48.000 / 4.000 × 3: tỷ lệ chip cho người dẫn đầu 2.460 (hơn giải nhất); Landrum-Burns 1.800.
- Bản sửa của công thức tỷ lệ chip: 1.566,67 cho người dẫn đầu ví dụ 1.
- Lập luận của Jeff Yass về sự khác nhau giữa đua ngựa và poker.
- Chứng minh nghiệm p_k = (1/x_k)/Σ(1/x_i) của hệ Malmuth-Weitzman.
- Giải winner-take-all 1.000 người: người thắng là sự kiện khoảng 30 độ lệch chuẩn; độ lệch khoảng √n.
- Người chơi T với 800 giải mô phỏng: σ theo công thức 0,296, quan sát 0,347; khoảng chuẩn [0,38; 1,77]; cận trên 1,666; cận dưới Chebyshev 0,48 với xác suất không quá 1/4.

### Kết luận và hàm ý cho người chơi

- Gần vùng có thưởng, đừng coi chip là tiền: chồng lớn nên tránh các cuộc đối đầu giá trị biên với chồng có thể loại mình, chồng nhỏ có "ghế" đáng giá.
- Khi thoả thuận chia tiền, biết rằng chia theo tỷ lệ chip có lợi cho chồng lớn và Landrum-Burns có lợi cho chồng nhỏ; mỗi bên sẽ đề xuất công thức có lợi cho mình, và giá trị công bằng nằm giữa.
- Kết quả giải đấu rất nhiễu: một người có ω ≈ 1 buyin mỗi giải cần hàng chục, thậm chí hàng trăm giải chỉ để sai số chuẩn xuống khoảng 1 buyin, và cần khoảng k giải để σ² ≈ 1.
- Đừng suy diễn "phong cách" (ví dụ "tôi hay về nhất") từ một mẫu vài trăm giải: chính dữ liệu mô phỏng của T cho thấy nhiễu ngẫu nhiên tạo ra hình mẫu như vậy.

### Trong ngôn ngữ xác suất và thống kê

Bốn công thức equity là bốn mô hình xác suất cho thứ tự về đích (một phân phối trên các hoán vị) với biên duy nhất cho trước là xác suất về nhất x_i. Malmuth-Harville là mô hình Plackett-Luce (chọn tuần tự không hoàn lại với trọng số x_i), quen thuộc trong thống kê xếp hạng (nhận xét của người tổng hợp). Phần thứ hai là bài toán suy luận cho trung bình của một biến có phân phối lệch nặng: định lý giới hạn trung tâm hội tụ chậm (độ lệch giảm theo 1/√m), nên tác giả dùng (a) một ước lượng phương sai dựa trên mô hình thay cho phương sai mẫu kém ổn định, (b) kiểm định một phía dựa trên phân phối chuẩn ở phía mà độ lệch làm cho kiểm định bảo thủ, và (c) bất đẳng thức Chebyshev, không phụ thuộc phân phối, ở phía còn lại.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| equity formula | công thức equity | quy tắc đổi chip thành giá trị tiền kỳ vọng |
| prize equity | equity giải thưởng | giá trị tiền kỳ vọng của chồng chip |
| chip stack | chồng chip | số chip một người đang có |
| total number of chips remaining (T) | tổng chip còn lại | tổng chip của mọi người còn trong giải |
| fraction of chips (s_i) | phần chip | chip của người i chia tổng chip |
| prize pool remaining (V_n) | quỹ còn phải trả | tổng thưởng của n hạng còn lại |
| incremental prize pool (W_n) | quỹ tăng thêm | quỹ còn lại trừ phần ai cũng chắc nhận |
| in the money | vào vùng có thưởng | người bị loại tiếp vẫn có tiền |
| on the bubble | ở bubble | người bị loại tiếp không có tiền, người sau đó có |
| final table | bàn chung kết | bàn cuối cùng của giải |
| dealmaking / deal | thoả thuận chia tiền | người còn lại đồng ý chia quỹ thay vì chơi tiếp |
| shorthanded | chơi ít người | bàn còn ít người |
| proportional chip count formula | công thức tỷ lệ chip | chia quỹ tăng thêm theo phần chip |
| floor function | hàm phần nguyên | số nguyên lớn nhất không vượt giá trị |
| Landrum-Burns formula | công thức Landrum-Burns | không về nhất thì về các hạng còn lại đều nhau |
| Malmuth-Harville formula | công thức Malmuth-Harville | xác suất hạng tiếp theo tỷ lệ với x trong số người còn lại |
| Harville formula | công thức Harville | công thức gốc trong cược đua ngựa |
| show / place pool | pool show / place | cược ngựa về top ba / top hai |
| Malmuth-Weitzman formula | công thức Malmuth-Weitzman | chip người bị loại chia đều; xác suất bị loại tỷ lệ nghịch chip |
| Vandermonde equations | phương trình Vandermonde | tên tác giả gọi họ hệ phương trình của Malmuth-Weitzman |
| sit-and-go | sit-and-go | giải một bàn, bắt đầu khi đủ người |
| ring game | cash game | bàn tiền thật |
| confidence interval | khoảng tin cậy | khoảng chứa giá trị thật với mức tin cậy cho trước |
| law of large numbers | luật số lớn | trung bình mẫu tiến về kỳ vọng khi mẫu lớn |
| chi-squared distribution | phân phối chi bình phương | phân phối của phương sai mẫu dưới giả định chuẩn |
| skew | độ lệch | mức bất đối xứng, ⟨(X − μ)³⟩/σ³ |
| normal distribution | phân phối chuẩn | phân phối hình chuông, độ lệch 0 |
| size of the tournament (s) | cỡ giải | quỹ chia số người |
| cost of the tournament (b_c) | chi phí giải | tiền mỗi người trả |
| entry fee (ε_b) | phí tham gia | chi phí trừ cỡ giải |
| guarantee | bảo đảm quỹ | sòng bài cam kết quỹ tối thiểu |
| rebuy / add-on | rebuy / add-on | mua thêm chip trong / cuối giai đoạn cho phép |
| normalized win rate (ω) | tỷ lệ thắng chuẩn hoá | lãi kỳ vọng mỗi giải tính theo cỡ giải |
| normalized win (Z) | kết quả chuẩn hoá | (X − s)/s |
| mode | giá trị hay gặp nhất | giá trị có tần suất cao nhất |
| tournament variance multiple (k) | bội số phương sai giải đấu | n·Σv_i² − 1 |
| win-rate-based variance formula | công thức phương sai dựa trên tỷ lệ thắng | σ² = (k̄ − ω)(1 + ω)/m |
| z-score | điểm z | độ lệch khỏi kỳ vọng tính bằng số độ lệch chuẩn |
| hypothesis test | kiểm định giả thuyết | quy tắc loại một giá trị tham số dựa trên dữ liệu |
| Chebyshev's (Tchebyshev's) Rule | bất đẳng thức Chebyshev | P(lệch quá a độ lệch chuẩn) ≤ 1/a² với mọi phân phối |
| cash rate | tỷ lệ có tiền | phần số giải vào vùng có thưởng |
| gross / net buyins | buyin gộp / ròng | tiền nhận / tiền nhận trừ phí vào |

## Câu nói đáng nhớ

> "Chips Aren't Cash." — tên chương
>
> *Dịch: Chip không phải tiền.*
>
> Tóm tắt toàn bộ chủ đề: ở giải đấu, giá trị tiền của chip không tỷ lệ với số chip.

> "In any event, there is no easy answer to the question of mapping chip stacks to prize equity, even for players of equal skill." — mục "A Survey of Equity Formulas"
>
> *Dịch: Dù sao, không có câu trả lời dễ cho việc ánh xạ chồng chip sang equity giải thưởng, kể cả với người chơi ngang tài.*
>
> Lý do phải có nhiều mô hình.

> "Clearly this isn't right. Player 1 seems to be entitled to receive more than first place money!" — mục "The Proportional Chip Count Formula"
>
> *Dịch: Rõ ràng điều này không đúng. Người chơi 1 có vẻ được nhận nhiều hơn tiền giải nhất!*
>
> Phản ví dụ gọn nhất chống lại việc chia theo tỷ lệ chip.

> "Any model that does not tend to equalize the payouts as the x_i values equalize cannot be right!" — mục "The Proportional Chip Count Formula"
>
> *Dịch: Mô hình nào không có xu hướng cho tiền bằng nhau khi các x_i bằng nhau thì không thể đúng!*
>
> Một tiêu chuẩn kiểm tra tối thiểu cho mọi công thức equity.

> "If a tall stack does not win he will still be very likely to finish second, and very unlikely to finish in the last remaining spot." — mục "The Malmuth-Harville Formula"
>
> *Dịch: Nếu chồng chip lớn không thắng, người đó vẫn rất có thể về nhì và rất khó về chót.*
>
> Lý do Malmuth-Harville hợp với poker hơn đua ngựa.

> "Because these are all models, they inherently have some sort of bias." — mục "The Malmuth-Weitzman Formula"
>
> *Dịch: Vì tất cả đều là mô hình, chúng vốn có một kiểu thiên lệch nào đó.*
>
> Lời nhắc khiêm tốn về mọi công thức định giá.

> "This is yet another case of the possibility of being fooled by random noise." — ví dụ người chơi T
>
> *Dịch: Đây lại là một trường hợp có thể bị nhiễu ngẫu nhiên đánh lừa.*
>
> Dữ liệu mô phỏng "có vẻ" cho thấy T hay về nhất, dù xác suất thật như nhau ở mọi hạng.

> "However, this rule has the excellent property of applying to any distribution, no matter how skew." — mục về khoảng tin cậy
>
> *Dịch: Tuy nhiên, quy tắc này có ưu điểm tuyệt vời là áp dụng được cho mọi phân phối, dù lệch đến đâu.*
>
> Vì sao dùng Chebyshev cho phía mà phân phối chuẩn không đáng tin.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương trình bày gọn bốn công thức equity phổ biến nhất thời đó, đánh giá từng công thức bằng phản ví dụ cụ thể và bằng một tiêu chuẩn rõ (equity phải bằng nhau khi chip bằng nhau; không ai được hơn giải nhất). Ý tưởng dùng hai công thức lệch ngược chiều làm cận trên và cận dưới là thực dụng cho thương lượng tại bàn. Chứng minh rằng hệ Malmuth-Weitzman có nghiệm đóng p_k ∝ 1/x_k là một đóng góp riêng của tác giả, biến một công thức "phải giải hệ phương trình" thành công thức tính nhẩm được. Phần khoảng tin cậy đặt đúng vấn đề mà nhiều người chơi giải bỏ qua: với độ lệch khoảng √n, vài trăm giải gần như không nói gì chắc chắn về tỷ lệ thắng; công thức k = n·Σv_i² − 1 cho một cách nhanh để biết cần bao nhiêu giải. Ví dụ người chơi T, do chính tác giả mô phỏng, là một minh hoạ trung thực về việc nhiễu tạo ra hình mẫu giả.

### Những chỗ đơn giản hoá

- Mọi công thức equity đều bỏ qua vị trí ngồi, cỡ blind so với chồng chip, và việc người chơi ở các bàn khác nhau; tác giả chỉ nêu điểm cuối ở phần phản đối Malmuth-Weitzman.
- Các công thức là cho người ngang tài; muốn thêm kỹ năng phải thay x_i, mà cách thay (ví dụ bằng Lý thuyết Nhân đôi) không được minh hoạ bằng số trong chương.
- Đánh giá "Malmuth-Weitzman kém chính xác hơn Malmuth-Harville một chút" được đưa ra không kèm bằng chứng.
- Giả định p_i = (1 + ω)/n cho mọi hạng có thưởng mâu thuẫn với Chương 26, như tác giả thừa nhận; người giỏi thật thường có kết quả "nặng đầu" hơn, làm phương sai thật lớn hơn công thức.
- Kết luận "khả năng tỷ lệ thắng thật dưới 0,4818 không quá 1/4" trộn cách nói tần suất (xác suất của dữ liệu khi biết tham số) với cách nói về tham số (xác suất của tham số khi biết dữ liệu); tác giả chỉ ghi chú "bỏ qua hàm ý Bayes" ở chỗ khác (nhận xét của người tổng hợp).
- Phần khoảng tin cậy bỏ qua phí tham gia, rebuy, add-on, và việc trộn nhiều loại giải với cỡ khác nhau (người chơi T chỉ có hai loại).

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- Công thức Malmuth-Harville đã trở thành chuẩn mực dưới tên **ICM** (Independent Chip Model, mô hình chip độc lập); hầu hết phần mềm thoả thuận và huấn luyện giải đấu dùng nó, và máy tính làm cho hạn chế "khó tính tại bàn" không còn quan trọng ngoài lúc đang chơi. Các công cụ hiện đại còn có ICM có tính tới vị trí ngồi và các ván tiếp theo (future game simulation).
- Các solver giải đấu (tính chiến lược gần cân bằng có tính ICM) và các bảng jam-or-fold theo ICM đã phổ biến cho giai đoạn cuối giải.
- Thoả thuận theo ICM là thông lệ ở bàn chung kết của nhiều giải trực tiếp và online.
- Nhận thức về phương sai giải đấu tăng mạnh nhờ dữ liệu lớn từ poker online: người chơi giải chuyên nghiệp nay thường được khuyên giữ bankroll hàng trăm buyin, đúng với độ lớn của k mà chương tính.

### Liên hệ các chương khác

- [C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md): khoảng tin cậy cho tỷ lệ thắng ở cash game, điểm z.
- [C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md): hàm ý Bayes mà chương này bỏ qua khi diễn giải khoảng tin cậy.
- [C12-tro-choi-jam-or-fold.md](C12-tro-choi-jam-or-fold.md): giai đoạn cuối giải, nơi blind cao và quyết định chủ yếu là jam hoặc fold.
- [C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md): độ lệch phân phối và rủi ro phá sản, đặc biệt nặng với người chơi giải.
- [C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md): công thức ⟨x²⟩ = μ² + σ² và các thoả thuận tài trợ người chơi giải.
- [C26-giai-dau-phan-1-nhan-doi.md](C26-giai-dau-phan-1-nhan-doi.md): Lý thuyết Nhân đôi và cỡ giải hiệu dụng, gần với bội số phương sai k.
- [C28-giai-dau-phan-3-poker-van-la-poker.md](C28-giai-dau-phan-3-poker-van-la-poker.md): dùng các công thức equity cho quyết định cụ thể, rebuy, thoả thuận.

### Vận dụng

- **Cho người chơi poker:** ở bàn chung kết, tính nhanh hai cận (tỷ lệ chip và Landrum-Burns) để biết vùng thương lượng; dùng ICM (Malmuth-Harville) trên máy khi phân tích lại. Đánh giá phong độ giải đấu bằng k: giải 100 người trả 9 hạng có k ≈ 16, giải 400 người trả 27 hạng có k ≈ 53, giải winner-take-all n người có k = n − 1; vì σ² ≈ k/m, muốn sai số chuẩn khoảng 0,5 buyin cần khoảng 4k giải.
- **Cho người làm tài chính và đầu tư:** chồng chip giải đấu giống một tài sản có lợi nhuận lồi bị giới hạn trên (không ai được hơn giải nhất) — giá trị của nó không tuyến tính theo "số lượng", giống phân chia giá trị giữa các lớp vốn có thứ tự ưu tiên trong thanh lý (waterfall). Việc kẹp giá trị giữa hai mô hình lệch ngược chiều là kỹ thuật định giá quen thuộc khi không có mô hình đúng. Phần thống kê áp dụng trực tiếp cho đánh giá các chiến lược có lợi nhuận lệch phải (đầu tư mạo hiểm, mua quyền chọn xa tiền): vài năm kết quả tốt có thể chỉ là một hai "lần về nhất"; phương sai mẫu không ổn định, nên nên dùng phương sai suy từ cấu trúc lợi nhuận và các bất đẳng thức không phụ thuộc phân phối như Chebyshev thay cho khoảng chuẩn.
- **Cho người ra quyết định nói chung:** khi chia một tài sản có giá trị phụ thuộc thứ hạng (giải thưởng, cổ phần trong cuộc thi), chia theo "đóng góp tuyến tính" sẽ ưu ái người dẫn đầu quá mức; cần mô hình hoá xác suất của từng thứ hạng.

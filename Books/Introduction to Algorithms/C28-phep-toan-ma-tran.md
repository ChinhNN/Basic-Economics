# Chương 28 — Các phép toán ma trận (Matrix Operations)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VII "Selected Topics", Chương 28 "Matrix Operations", trang 813–842 (phần mở đầu, Mục 28.1–28.3, Problems, Chapter notes).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Phụ lục D ([PD-ma-tran.md](PD-ma-tran.md)) ôn các khái niệm ma trận mà chương này dùng liên tục: hạng, ma trận không suy biến, định thức, ma trận hoán vị, ma trận xác định dương (Định lý D.1, D.6, các Exercise D.1-2, D.1-4, D.2-6…). Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)) đưa ra thuật toán Strassen nhân hai ma trận n × n trong O(n^(lg 7)) ≈ O(n^2,81) và định lý thợ; chương này chứng minh rằng mọi tăng tốc cho phép nhân ma trận cũng là tăng tốc cho phép nghịch đảo ma trận (Định lý 28.2), và dùng trường hợp 3 của định lý thợ để giải truy hồi. Chương 7 ([C07-quicksort.md](C07-quicksort.md)), Problem 7-4, giới thiệu ý tưởng thay đệ quy đuôi bằng vòng lặp — đúng phép biến đổi dùng để viết LU-DECOMPOSITION. Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)) dùng phép "nhân ma trận" để tính đường đi ngắn nhất và bao đóng bắc cầu, mà Exercise 28.2-4 nối lại với phép nhân ma trận bun. Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)) mở Phần VII và có bản đa luồng của phép nhân ma trận. Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)) tiếp tục chủ đề hệ ràng buộc tuyến tính, nhưng là bất đẳng thức và tối ưu hoá. Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)) giải bài toán nội suy đa thức — họ hàng của bài toán khớp đường cong ở Mục 28.3 và Problem 28-2.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **cách đúng để giải hệ phương trình tuyến tính Ax = b gồm n phương trình n ẩn là phân rã ma trận một lần thành PA = LU (P hoán vị, L tam giác dưới đơn vị, U tam giác trên) trong Θ(n³), rồi giải hai hệ tam giác bằng phép thế tiến và phép thế lùi trong Θ(n²) cho mỗi vế phải b; cách này ổn định số học hơn và nhanh hơn việc tính A⁻¹ rồi nhân; về mặt lý thuyết, nghịch đảo ma trận và nhân ma trận khó ngang nhau; và ma trận đối xứng xác định dương là lớp ma trận "dễ chịu" — phân rã LU không bao giờ chia cho 0 — đồng thời chính là ma trận xuất hiện khi khớp đường cong theo bình phương tối thiểu.** Phần mở đầu nêu ba mục và cảnh báo về ổn định số học (sai số làm tròn của số dấu phẩy động có thể bị khuếch đại). Mục 28.1: viết hệ thành Ax = b; nếu A không suy biến thì nghiệm duy nhất là x = A⁻¹b; phân rã LUP PA = LU biến Ax = b thành Ly = Pb (phép thế tiến) và Ux = y (phép thế lùi), thủ tục LUP-SOLVE chạy Θ(n²); phân rã LU tính bằng khử Gauss viết dưới dạng đệ quy với phần bù Schur A′ − vwᵀ/a₁₁, thủ tục LU-DECOMPOSITION chạy Θ(n³) nhưng hỏng khi gặp phần tử trụ bằng 0; LUP-DECOMPOSITION chọn phần tử có trị tuyệt đối lớn nhất trong cột làm trụ, đổi hàng, ghi hoán vị vào mảng π, tính L và U ngay trong A, vẫn Θ(n³). Mục 28.2: từ phân rã LUP tính được A⁻¹ trong Θ(n³) bằng cách giải n hệ AXᵢ = eᵢ; Định lý 28.1 (nhân không khó hơn nghịch đảo) dùng ma trận 3n × 3n; Định lý 28.2 (nghịch đảo không khó hơn nhân) chia đôi ma trận đối xứng xác định dương thành bốn khối và dùng phần bù Schur, cho truy hồi I(n) ≤ 2I(n/2) + 4M(n/2) + O(n²) = O(M(n)), rồi mở rộng cho ma trận bất kỳ nhờ A⁻¹ = (AᵀA)⁻¹Aᵀ. Mục 28.3: ma trận xác định dương thì không suy biến (Bổ đề 28.3); mọi ma trận con chính đầu của ma trận đối xứng xác định dương cũng đối xứng xác định dương (Bổ đề 28.4); phần bù Schur của nó cũng vậy (Bổ đề 28.5); do đó mọi phần tử trụ của phân rã LU đều dương (Hệ quả 28.6); ứng dụng: khớp m điểm dữ liệu bằng tổ hợp tuyến tính của n hàm cơ sở, cực tiểu chuẩn của vectơ sai số dẫn tới phương trình chuẩn AᵀAc = Aᵀy, nghiệm c = A⁺y với A⁺ = (AᵀA)⁻¹Aᵀ là giả nghịch đảo; ví dụ khớp parabol qua 5 điểm cho F(x) = 1,200 − 0,757x + 0,214x².

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong chương này.** Chỉ một bài tập có dấu sao: Exercise 28.2-6 (tổng quát hoá thuật toán nghịch đảo của Định lý 28.2 cho ma trận số phức, dùng chuyển vị liên hợp và ma trận Hermite). Hai bài toán cuối chương (28-1, 28-2) không có dấu sao.
> - **Chương này nằm trong Phần VII "Selected Topics"; lời giới thiệu Phần VII được tổng hợp trong file Chương 27** ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)), chương đầu tiên của phần đó, nên file này không có khối giới thiệu Phần.
> - **Lớp chữ PDF hỏng gần như toàn bộ ký hiệu toán:** dấu ngoặc ma trận thành `˙ … /BEL` hoặc `/NUL … ` (ví dụ ma trận A của ví dụ LUP-SOLVE bị trích thành `/NUL 120 344 563`), dấu trừ và số mũ −1 thành `/NUL` (A⁻¹ thành `A/NUL1`), Θ thành `‚`, chữ Hy Lạp v (nu) trong vectơ cột v và π (mảng hoán vị) mất hẳn (`Œi` là π[i], dòng 13 của LUP-DECOMPOSITION bị trích thành "exchange Œk with Œk 0"), η (vectơ sai số) mất hẳn, ≤ ≥ ≠ ∞ mất, chữ z trong Bổ đề 28.5 bị trích thành `´`. Các ma trận trong Hình 28.1 và Hình 28.2 bị trích thành dãy số dính liền ("61 351 9" là hàng 6 13 5 19). Mọi pseudocode, công thức (28.1)–(28.23), Hình 28.1, 28.2, 28.3 và các ma trận trong bài tập ở bản tổng hợp này được đọc lại từ ảnh trang 814, 816–826, 829–831, 833–842.
> - **Chỗ sách viết chưa chặt hoặc có lỗi in (nhận xét của người tổng hợp):**
>   - Trang 827, câu cuối đoạn mở Mục 28.2: "a set of a linear equations" — thừa chữ "a" (đúng là "a set of linear equations").
>   - Hình 28.2(c) in phần tử ở hàng 3, cột 4 là "–.2", trong khi các hình (d)–(i) in cùng phần tử đó là "–0.2". Chỉ là khác cách in, giá trị như nhau.
>   - Trang 830, truy hồi trong chứng minh Định lý 28.2 viết "2I(n/2) + 4M(n/2) + O(n²) = 2I(n/2) + Θ(M(n))". Từ giả thiết M(n/2) ≤ cM(n) với c < 1/2 ta chỉ suy ra được 4M(n/2) + O(n²) = O(M(n)), tức một cận trên; viết Θ là mạnh hơn mức chứng minh được (dù không ảnh hưởng kết luận I(n) = O(M(n))). Ngoài ra, việc áp dụng định lý thợ (vốn phát biểu cho đẳng thức) cho một bất đẳng thức cần thêm một câu lập luận đơn điệu mà sách bỏ qua.
>   - Trang 823, định nghĩa vectơ v = (a₂₁, a₃₁, …, aₙ₁)ᵀ "ngoại trừ a₁₁ thay cho aₖ₁": đúng, nhưng viết rất gọn; ý là sau khi đổi hàng 1 với hàng k, phần còn lại của cột đầu gồm các aᵢ₁ với i ≠ 1, i ≠ k, cộng thêm a₁₁ nằm ở vị trí cũ của aₖ₁.
>   - Trang 839, sách khuyên giải phương trình chuẩn (28.19) bằng phân rã LU của AᵀA. Theo hiểu biết của người tổng hợp, trong tính toán số thực tế người ta tránh lập AᵀA (vì nó bình phương số điều kiện của A) và dùng phân rã QR hoặc SVD; sách không nhắc điều này dù đã nêu vấn đề ổn định số học ở phần mở đầu.
> - **Mọi ví dụ chạy tay trong sách đã được tự kiểm tra lại và đúng:** ví dụ LUP-SOLVE với A = (1 2 0; 3 4 4; 5 6 3), b = (3, 7, 8)ᵀ cho y = (8; 1,4; 1,5) và x = (−1,4; 2,2; 0,6); phân rã LU của ma trận 4 × 4 ở Hình 28.1; phân rã LUP của ma trận 4 × 4 ở Hình 28.2 (từng bước (a)–(j)); ma trận D⁻¹ trong chứng minh Định lý 28.1; giả nghịch đảo A⁺ và vectơ hệ số c = (1,200; −0,757; 0,214) ở ví dụ bình phương tối thiểu (giá trị chính xác c = (6/5, −53/70, 3/14), sách làm tròn đúng tới 3 chữ số). Người tổng hợp còn tự giải các bài 28.1-1, 28.1-2, 28.1-3, 28.3-6 và Problem 28-1(a)–(c) và kiểm tra lại bằng phép nhân ngược.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương "Matrix Operations" vẫn là Chương 28 với cùng ba mục (hệ phương trình tuyến tính bằng LUP, nghịch đảo ma trận, ma trận đối xứng xác định dương và bình phương tối thiểu). Ấn bản 4 bỏ các thuộc tính kiểu `A.rows` và truyền kích thước n trực tiếp làm tham số của thủ tục. Các thay đổi chi tiết hơn về lời văn và bài tập, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 28.1, trang 813) — chương làm gì và vấn đề ổn định số học

```text
       Phép toán ma trận là trái tim của tính toán khoa học
       → thuật toán hiệu quả cho ma trận có rất nhiều ứng dụng
                                │
                                ▼
       Chương tập trung vào hai việc: nhân ma trận và giải hệ phương
       trình tuyến tính (kiến thức nền về ma trận: Phụ lục D)
                                │
                                ▼
       Trình tự chương:
       28.1 giải hệ phương trình tuyến tính bằng phân rã LUP
       28.2 quan hệ chặt giữa NHÂN ma trận và NGHỊCH ĐẢO ma trận
       28.3 ma trận đối xứng xác định dương, và dùng nó để tìm nghiệm
            bình phương tối thiểu cho hệ thừa phương trình
                                │
                                ▼
       ỔN ĐỊNH SỐ HỌC (numerical stability):
       số dấu phẩy động có độ chính xác hữu hạn → sai số làm tròn có thể
       bị khuếch đại dần qua quá trình tính → kết quả sai
       (phép tính như vậy gọi là KHÔNG ỔN ĐỊNH SỐ HỌC)
       · chương chỉ thỉnh thoảng nhắc tới, không đi sâu
       · tài liệu tham khảo: sách của Golub và Van Loan
```

### Mục 28.1 — Giải hệ phương trình tuyến tính (Solving systems of linear equations, trang 813–827)

```text
       Hệ n phương trình, n ẩn x₁..xₙ, hệ số trong một trường (thường ℝ)
       a₁₁x₁ + … + a₁ₙxₙ = b₁ ; … ; aₙ₁x₁ + … + aₙₙxₙ = bₙ        (28.1)
       viết gọn: Ax = b                                            (28.2)
                                │
                                ▼
       A không suy biến (hạng A = n) ⇒ có A⁻¹, nghiệm DUY NHẤT x = A⁻¹b (28.3)
       · hạng < n: hệ THIẾU phương trình (underdetermined) — thường vô số
         nghiệm, có thể vô nghiệm nếu mâu thuẫn
       · số phương trình > n: hệ THỪA phương trình (overdetermined) — có thể
         vô nghiệm → Mục 28.3 tìm nghiệm xấp xỉ
                                │
                                ▼
       Không tính A⁻¹ rồi nhân (kém ổn định số học); thay bằng
       PHÂN RÃ LUP: tìm P, L, U cỡ n × n với   PA = LU              (28.4)
       · L tam giác dưới ĐƠN VỊ (đường chéo toàn 1)
       · U tam giác trên
       · P ma trận hoán vị (đổi thứ tự các phương trình)
                                │
                                ▼
       Ax = b  ⇔  PAx = Pb  ⇔  LUx = Pb ; đặt y = Ux:
       ┌───────────────────────────────┬────────────────────────────────┐
       │ Ly = Pb   (28.5)              │ Ux = y   (28.6)                │
       │ PHÉP THẾ TIẾN: tính y₁, y₂, … │ PHÉP THẾ LÙI: tính xₙ, xₙ₋₁, …│
       │ yᵢ = b_π[i] − Σⱼ<ᵢ lᵢⱼ yⱼ     │ xᵢ = (yᵢ − Σⱼ>ᵢ uᵢⱼ xⱼ) / uᵢᵢ │
       └───────────────────────────────┴────────────────────────────────┘
       P lưu gọn bằng mảng π[1..n]: P(i, π[i]) = 1
       LUP-SOLVE(L, U, π, b): hai vòng lặp, mỗi vòng có tổng ẩn → Θ(n²)
       Ví dụ: A = (1 2 0; 3 4 4; 5 6 3), b = (3, 7, 8)
              → y = (8; 1,4; 1,5) → x = (−1,4; 2,2; 0,6)
                                │
                                ▼
       PHÂN RÃ LU (khi P = I) bằng KHỬ GAUSS, viết dạng đệ quy:
       A = (a₁₁ wᵀ; v A′) = (1 0; v/a₁₁ Iₙ₋₁)(a₁₁ wᵀ; 0 A′ − vwᵀ/a₁₁)  (28.8)
       PHẦN BÙ SCHUR của A theo a₁₁: A′ − vwᵀ/a₁₁                  (28.9)
       · A không suy biến ⇒ phần bù Schur không suy biến
       · đệ quy: phần bù Schur = L′U′ ⇒ A = (1 0; v/a₁₁ L′)(a₁₁ wᵀ; 0 U′)
       · các số đem chia (a₁₁, rồi góc trên trái của từng phần bù Schur) là
         PHẦN TỬ TRỤ (pivot), nằm trên đường chéo của U
       · trụ = 0 ⇒ phương pháp hỏng → cần CHỌN TRỤ (pivoting) bằng hoán vị
       LU-DECOMPOSITION: đệ quy đuôi đổi thành vòng lặp, ba vòng lồng → Θ(n³)
       Ví dụ: A = (2 3 1 5; 6 13 5 19; 2 19 10 23; 4 10 11 31),
       các trụ lần lượt 2, 4, 1, 3
                                │
                                ▼
       PHÂN RÃ LUP: trước mỗi bước, chọn trong cột hiện tại phần tử có
       TRỊ TUYỆT ĐỐI LỚN NHẤT aₖ₁ ≠ 0 làm trụ, đổi hàng 1 ↔ hàng k (ma trận Q)
       QA = (1 0; v/aₖ₁ Iₙ₋₁)(aₖ₁ wᵀ; 0 A′ − vwᵀ/aₖ₁)
       đệ quy: P′(A′ − vwᵀ/aₖ₁) = L′U′ ; đặt P = (1 0; 0 P′)Q
       ⇒ PA = (1 0; P′v/aₖ₁ L′)(aₖ₁ wᵀ; 0 U′) = LU
       (khác LU: cột v/aₖ₁ cũng phải nhân với P′ → đổi CẢ HÀNG)
       LUP-DECOMPOSITION(A): mảng π, tính L và U ngay trong A, báo
       "singular matrix" nếu cả cột bằng 0; vẫn Θ(n³)
       → chọn trụ chỉ tốn thêm tối đa một hằng số lần thời gian
       Ví dụ: A = (2 0 2 0,6; 3 3 4 −2; 5 5 4 2; −1 −2 3,4 −1),
       các trụ lần lượt 5, −2, 4, −3; π cuối cùng = (3, 1, 4, 2)
```

### Mục 28.2 — Nghịch đảo ma trận (Inverting matrices, trang 827–832)

```text
       Thực tế hiếm khi dùng A⁻¹ để giải hệ, nhưng đôi khi cần chính A⁻¹
                                │
                                ▼
       NGHỊCH ĐẢO TỪ PHÂN RÃ LUP
       · phân rã LUP chỉ phụ thuộc A, không phụ thuộc b ⇒ giải k hệ
         Ax = b khác vế phải trong Θ(kn²)
       · AX = Iₙ (28.10) là n hệ AXᵢ = eᵢ (Xᵢ là cột i của X)
       · n lần LUP-SOLVE: Θ(n³); cộng phân rã Θ(n³) ⇒ A⁻¹ trong Θ(n³)
                                │
                                ▼
       NHÂN VÀ NGHỊCH ĐẢO KHÓ NGANG NHAU
       M(n) = thời gian nhân hai ma trận n × n ; I(n) = thời gian nghịch đảo
                                │
           ┌────────────────────┴─────────────────────┐
           ▼                                          ▼
   ĐỊNH LÝ 28.1                               ĐỊNH LÝ 28.2
   nhân không khó hơn nghịch đảo              nghịch đảo không khó hơn nhân
   (I(n) = Ω(n²), I(3n) = O(I(n)))            (M(n) = Ω(n²), M(n+k) = O(M(n))
                                               với 0 ≤ k ≤ n, M(n/2) ≤ cM(n)
                                               với c < 1/2)
   D = (Iₙ A 0; 0 Iₙ B; 0 0 Iₙ)               · bù cho n thành lũy thừa của 2:
   D⁻¹ = (Iₙ −A AB; 0 Iₙ −B; 0 0 Iₙ)            (A 0; 0 Iₖ)⁻¹ = (A⁻¹ 0; 0 Iₖ)
   → AB là khối trên phải của D⁻¹             · A đối xứng xác định dương:
   M(n) = O(I(3n)) = O(I(n))                    A = (B Cᵀ; C D), S = D − CB⁻¹Cᵀ
                                                A⁻¹ = (B⁻¹+B⁻¹CᵀS⁻¹CB⁻¹  −B⁻¹CᵀS⁻¹;
                                                        −S⁻¹CB⁻¹          S⁻¹)
                                                7 bước: 2 nghịch đảo đệ quy cỡ n/2,
                                                4 phép nhân cỡ n/2, O(n²) việc khác
                                                I(n) ≤ 2I(n/2) + 4M(n/2) + O(n²)
                                                     = O(M(n))  (định lý thợ, TH 3)
                                              · A bất kỳ không suy biến:
                                                A⁻¹ = (AᵀA)⁻¹Aᵀ, AᵀA đối xứng
                                                xác định dương → 3 bước O(M(n))
           └────────────────────┬─────────────────────┘
                                ▼
       Hệ quả: dùng Strassen ⇒ nghịch đảo trong O(n^(lg 7))
       Hệ quả phụ: giải Ax = b không cần chọn trụ bằng cách giải
       (AᵀA)x = Aᵀb — đúng về lý thuyết, nhưng LUP-DECOMPOSITION thực tế
       tốt hơn (ít phép tính hơn một hằng số lần, ổn định số học hơn)
```

### Mục 28.3 — Ma trận đối xứng xác định dương và xấp xỉ bình phương tối thiểu (Symmetric positive-definite matrices and least-squares approximation, trang 832–840)

```text
       A xác định dương: xᵀAx > 0 với mọi x ≠ 0
                                │
                                ▼
       Bổ đề 28.3: xác định dương ⇒ không suy biến
       (nếu Ax = 0 với x ≠ 0 thì xᵀAx = 0, mâu thuẫn)
                                │
                                ▼
       MA TRẬN CON CHÍNH ĐẦU Aₖ: giao của k hàng đầu và k cột đầu
       Bổ đề 28.4: A đối xứng xác định dương ⇒ mọi Aₖ đối xứng xác định
       dương (lấy x = (xₖ, 0, …, 0) thì xᵀAx = xₖᵀAₖxₖ)
                                │
                                ▼
       PHẦN BÙ SCHUR tổng quát: A = (Aₖ Bᵀ; B C), S = C − BAₖ⁻¹Bᵀ  (28.15)
       (k = 1 trùng với (28.9))
       Bổ đề 28.5: S đối xứng xác định dương
       (xᵀAx = (y + Aₖ⁻¹Bᵀz)ᵀAₖ(y + Aₖ⁻¹Bᵀz) + zᵀSz  (28.16) — "hoàn
        thành bình phương"; chọn y = −Aₖ⁻¹Bᵀz thì zᵀSz = xᵀAx > 0)
                                │
                                ▼
       Hệ quả 28.6: phân rã LU của ma trận đối xứng xác định dương
       không bao giờ chia cho 0 — mọi trụ đều DƯƠNG
       (trụ đầu a₁₁ = e₁ᵀAe₁ > 0; mỗi bước sinh phần bù Schur theo A₁,
        vẫn đối xứng xác định dương; quy nạp)
                                │
                                ▼
       ỨNG DỤNG: XẤP XỈ BÌNH PHƯƠNG TỐI THIỂU
       m điểm (xᵢ, yᵢ) có sai số đo; tìm F(x) = Σⱼ₌₁ⁿ cⱼ fⱼ(x) (n hàm cơ sở,
       thường fⱼ(x) = x^(j−1) → đa thức bậc n − 1), n < m
       · n = m: khớp đúng mọi điểm nhưng "khớp cả nhiễu", dự đoán kém
       · ma trận A (m × n), aᵢⱼ = fⱼ(xᵢ); sai số η = Ac − y        (28.17)
       · cực tiểu ‖η‖² = Σᵢ (Σⱼ aᵢⱼcⱼ − yᵢ)²: đạo hàm theo cₖ bằng 0 (28.18)
       ⇒ PHƯƠNG TRÌNH CHUẨN AᵀAc = Aᵀy                             (28.19)
       · A có hạng cột đầy đủ ⇒ AᵀA đối xứng xác định dương ⇒ khả nghịch
       ⇒ c = (AᵀA)⁻¹Aᵀy = A⁺y, A⁺ là GIẢ NGHỊCH ĐẢO               (28.20)
                                │
                                ▼
       Ví dụ: 5 điểm (−1,2), (1,1), (2,1), (3,0), (5,3), khớp bậc hai
       → F(x) = 1,200 − 0,757x + 0,214x²
       Thực hành: tính Aᵀy, phân rã LU của AᵀA, thế tiến và thế lùi
```

### Bài toán cuối chương (Problems 28-1 và 28-2, trang 840–842)

```text
       28-1 Hệ phương trình ba đường chéo
            · ma trận 5 × 5 cụ thể (đường chéo 1, 2, 2, 2, 2; hai đường
              cạnh −1): tìm LU, giải Ax = (1,1,1,1,1)ᵀ, tìm A⁻¹
            · ma trận ba đường chéo đối xứng xác định dương: giải trong O(n)
              bằng LU; mọi cách dựa trên lập A⁻¹ đều đắt hơn (A⁻¹ thường đặc)
            · ma trận ba đường chéo không suy biến bất kỳ: O(n) bằng LUP
                                │
                                ▼
       28-2 Đường spline bậc ba
            · n + 1 điểm, xᵢ = i; n đa thức bậc ba fᵢ ghép tại các NÚT
            · liên tục giá trị và đạo hàm bậc nhất; biết đạo hàm Dᵢ tại nút
              thì tính 4n hệ số trong O(n)
            · đòi đạo hàm bậc hai liên tục + f″ = 0 ở hai đầu (spline TỰ NHIÊN)
              ⇒ Dᵢ₋₁ + 4Dᵢ + Dᵢ₊₁ = 3(yᵢ₊₁ − yᵢ₋₁)                  (28.21)
                 2D₀ + D₁ = 3(y₁ − y₀) ; Dₙ₋₁ + 2Dₙ = 3(yₙ − yₙ₋₁) (28.22–23)
            · hệ ba đường chéo đối xứng xác định dương ⇒ O(n) nhờ 28-1
            · tổng quát cho xᵢ không cách đều
```

### Ghi chú chương (Chapter notes, trang 842)

```text
       Sách tham khảo về tính toán số: George–Liu; Golub–Van Loan;
       Press–Teukolsky–Vetterling–Flannery; Strang
                                │
                                ▼
       Golub–Van Loan: det(A) không phải thước đo tốt cho độ ổn định;
       dùng ‖A‖∞ · ‖A⁻¹‖∞ với ‖A‖∞ = max over i của Σⱼ |aᵢⱼ|, và cách ước
       lượng đại lượng này mà không cần tính A⁻¹
                                │
                                ▼
       Khử Gauss (nền của LU, LUP): phương pháp hệ thống đầu tiên giải hệ
       tuyến tính, một trong những thuật toán số sớm nhất; thường gán cho
       C. F. Gauss (1777–1855) dù đã được biết từ trước
                                │
                                ▼
       Strassen: nghịch đảo n × n trong O(n^(lg 7))
       Winograd: nhân không khó hơn nghịch đảo
       Aho, Hopcroft, Ullman: chiều ngược lại
                                │
                                ▼
       PHÂN RÃ GIÁ TRỊ KỲ DỊ (SVD): A = Q₁ΣQ₂ᵀ, Σ chỉ khác 0 trên đường
       chéo, Q₁ (m × m) và Q₂ (n × n) có các cột trực chuẩn
       · Strang, Golub–Van Loan trình bày SVD tốt
       · Strang: trình bày xuất sắc về ma trận đối xứng xác định dương
```

## Ba câu hỏi chương này trả lời

1. **Làm thế nào giải hệ n phương trình tuyến tính n ẩn Ax = b một cách hiệu quả và ổn định?** Không tính A⁻¹. Thay vào đó, tìm phân rã LUP: PA = LU với P là ma trận hoán vị (lưu gọn bằng mảng π), L tam giác dưới đơn vị, U tam giác trên. Khi đó Ax = b tương đương với hai hệ tam giác: Ly = Pb giải bằng phép thế tiến (yᵢ = b_π[i] − Σⱼ₌₁^(i−1) lᵢⱼyⱼ) và Ux = y giải bằng phép thế lùi (xᵢ = (yᵢ − Σⱼ₌ᵢ₊₁ⁿ uᵢⱼxⱼ)/uᵢᵢ), mỗi hệ Θ(n²). Phân rã LUP tính bằng khử Gauss có chọn trụ: ở mỗi bước, lấy phần tử có trị tuyệt đối lớn nhất trong cột làm trụ, đổi hàng, ghi hệ số nhân vào L, tính phần bù Schur; ba vòng lặp lồng nhau cho Θ(n³). Ví dụ: A = (1 2 0; 3 4 4; 5 6 3), b = (3, 7, 8)ᵀ có π = (3, 1, 2), L = (1 0 0; 0,2 1 0; 0,6 0,5 1), U = (5 6 3; 0 0,8 −0,6; 0 0 2,5), y = (8; 1,4; 1,5), x = (−1,4; 2,2; 0,6). Một khi đã có phân rã, mỗi vế phải b mới chỉ tốn Θ(n²).
2. **Nghịch đảo ma trận khó đến đâu so với nhân ma trận?** Ngang nhau, sai khác một hằng số. Định lý 28.1: nếu nghịch đảo được trong I(n) thì nhân được trong O(I(n)), vì tích AB nằm ở khối trên phải của nghịch đảo của ma trận 3n × 3n D = (Iₙ A 0; 0 Iₙ B; 0 0 Iₙ). Định lý 28.2: nếu nhân được trong M(n) thì nghịch đảo được trong O(M(n)): với A đối xứng xác định dương, chia A thành bốn khối n/2 × n/2, nghịch đảo đệ quy khối B và phần bù Schur S = D − CB⁻¹Cᵀ, cùng 4 phép nhân, cho I(n) ≤ 2I(n/2) + 4M(n/2) + O(n²) = O(M(n)); với A bất kỳ dùng A⁻¹ = (AᵀA)⁻¹Aᵀ. Hệ quả: nhờ Strassen, nghịch đảo được trong O(n^(lg 7)) ≈ O(n^2,81). Cách thực tế (từ phân rã LUP, giải n hệ AXᵢ = eᵢ) tốn Θ(n³).
3. **Vì sao ma trận đối xứng xác định dương quan trọng, và chúng giúp gì khi dữ liệu có nhiễu?** Chúng không suy biến; mọi ma trận con chính đầu và mọi phần bù Schur của chúng vẫn đối xứng xác định dương; vì vậy phân rã LU không cần chọn trụ và mọi trụ đều dương (ví dụ A = (4 2; 2 3): trụ 4, rồi 3 − 2·2/4 = 2). Chúng xuất hiện tự nhiên khi khớp đường cong: với m điểm dữ liệu và n < m hàm cơ sở, hệ Ac = y thừa phương trình; cực tiểu tổng bình phương sai số ‖Ac − y‖² dẫn tới phương trình chuẩn AᵀAc = Aᵀy, mà AᵀA đối xứng xác định dương khi A có hạng cột đầy đủ. Ví dụ năm điểm (−1, 2), (1, 1), (2, 1), (3, 0), (5, 3) cho AᵀA = (5 10 40; 10 40 160; 40 160 724), Aᵀy = (7, 16, 82)ᵀ và parabol F(x) = 1,200 − 0,757x + 0,214x² (chính xác: 6/5 − (53/70)x + (3/14)x²).

## Khái niệm cần biết

- **Hệ phương trình tuyến tính và dạng ma trận Ax = b:** n phương trình aᵢ₁x₁ + … + aᵢₙxₙ = bᵢ viết gọn thành tích ma trận A = (aᵢⱼ) với vectơ ẩn x. Ví dụ x₁ + 2x₂ = 3, 3x₁ + 4x₂ + 4x₃ = 7, 5x₁ + 6x₂ + 3x₃ = 8 là Ax = b với A = (1 2 0; 3 4 4; 5 6 3), b = (3, 7, 8)ᵀ. Đây là bài toán gốc của cả Mục 28.1.
- **Ma trận không suy biến (nonsingular) và nghịch đảo:** A vuông, có A⁻¹ với AA⁻¹ = A⁻¹A = I; tương đương hạng A = n, tương đương det A ≠ 0. Ví dụ A = (4 2; 2 3) có det = 8, A⁻¹ = (3/8 −1/4; −1/4 1/2). Không suy biến bảo đảm Ax = b có nghiệm duy nhất x = A⁻¹b.
- **Hệ thiếu phương trình / hệ thừa phương trình (underdetermined / overdetermined):** hạng A nhỏ hơn số ẩn thì thường vô số nghiệm (ví dụ một phương trình x₁ + x₂ = 1 với hai ẩn); số phương trình nhiều hơn số ẩn thì thường vô nghiệm (ví dụ 5 điểm không cùng nằm trên một parabol). Hệ thừa là đối tượng của bình phương tối thiểu ở Mục 28.3.
- **Ổn định số học (numerical stability):** một phép tính không ổn định nếu sai số làm tròn của số dấu phẩy động bị khuếch đại tới mức kết quả sai. Ví dụ (của người tổng hợp): với số chỉ giữ 3 chữ số có nghĩa, hệ 0,0001x₁ + x₂ = 1, x₁ + x₂ = 2 khử theo trụ 0,0001 cho −9999x₂ = −9998, làm tròn thành −10000x₂ = −10000, nên x₂ = 1 và x₁ = (1 − 1)/0,0001 = 0 (sai hẳn, nghiệm đúng ≈ (1,0001; 0,9999)); đổi hàng để lấy trụ 1 thì ra x₁ ≈ 1, x₂ ≈ 1. Đây là lý do LUP-DECOMPOSITION chọn trụ có trị tuyệt đối lớn nhất.
- **Ma trận tam giác dưới đơn vị, tam giác trên:** L có lᵢⱼ = 0 khi i < j và lᵢᵢ = 1; U có uᵢⱼ = 0 khi i > j. Ví dụ L = (1 0 0; 0,2 1 0; 0,6 0,5 1), U = (5 6 3; 0 0,8 −0,6; 0 0 2,5). Hệ tam giác giải được bằng thế lần lượt trong Θ(n²).
- **Ma trận hoán vị và mảng π:** P có đúng một số 1 ở mỗi hàng và mỗi cột; PA là A đã đổi thứ tự hàng. Lưu gọn bằng π[i] = vị trí cột của số 1 ở hàng i, nên hàng i của PA là hàng π[i] của A và phần tử thứ i của Pb là b_π[i]. Ví dụ π = (3, 1, 2) ứng với P = (0 0 1; 1 0 0; 0 1 0); Pb với b = (3, 7, 8) là (8, 3, 7).
- **Phân rã LUP và phân rã LU (LUP / LU decomposition):** viết PA = LU (khi P = I thì A = LU). Ví dụ: A = (4 −5 6; 8 −6 7; 12 −7 12) = (1 0 0; 2 1 0; 3 2 1)(4 −5 6; 0 4 −5; 0 0 4). Đây là công cụ trung tâm: phân rã một lần Θ(n³), giải mỗi vế phải Θ(n²).
- **Phép thế tiến (forward substitution) và phép thế lùi (back substitution):** phép thế tiến giải Ly = Pb từ y₁ xuống yₙ; phép thế lùi giải Ux = y từ xₙ lên x₁. Ví dụ hệ (1 0 0; 4 1 0; −6 5 1)x = (3, 14, −7)ᵀ: x₁ = 3, x₂ = 14 − 12 = 2, x₃ = −7 + 18 − 10 = 1.
- **Khử Gauss (Gaussian elimination):** trừ các bội của phương trình đầu khỏi các phương trình sau để khử ẩn x₁, rồi lặp lại với phương trình thứ hai…; hệ còn lại có dạng tam giác trên chính là U, các hệ số nhân tạo thành L. Ví dụ với A = (4 −5 6; 8 −6 7; 12 −7 12): trừ 2 lần hàng 1 khỏi hàng 2, 3 lần hàng 1 khỏi hàng 3, rồi 2 lần hàng 2 mới khỏi hàng 3; hệ số 2, 3, 2 là các phần tử dưới đường chéo của L.
- **Phần bù Schur (Schur complement):** với A = (a₁₁ wᵀ; v A′), ma trận (n − 1) × (n − 1) A′ − vwᵀ/a₁₁; tổng quát với A = (Aₖ Bᵀ; B C), S = C − BAₖ⁻¹Bᵀ. Ví dụ A = (2 3 1 5; 6 13 5 19; 2 19 10 23; 4 10 11 31): v = (6, 2, 4)ᵀ, wᵀ = (3, 1, 5), phần bù Schur là (4 2 4; 16 9 18; 4 9 21). Nó là "phần việc còn lại" sau một bước khử Gauss, nên mọi lập luận đệ quy của chương đều đi qua nó.
- **Tích ngoài (outer product):** vwᵀ với v cột (n − 1) phần tử và wᵀ hàng (n − 1) phần tử là ma trận (n − 1) × (n − 1) có phần tử (i, j) bằng vᵢwⱼ. Ví dụ v = (6, 2, 4)ᵀ, wᵀ = (3, 1, 5): vwᵀ/2 = (9 3 15; 3 1 5; 6 2 10).
- **Phần tử trụ và chọn trụ (pivot, pivoting):** trụ là số đem chia ở mỗi bước phân rã (nằm trên đường chéo của U); chọn trụ là dùng hoán vị hàng để tránh trụ bằng 0 hoặc quá nhỏ. Ví dụ A = (0 1; 1 0) không có phân rã LU (trụ đầu bằng 0) nhưng đổi hai hàng thì PA = I = I·I.
- **Đệ quy đuôi (tail recursion):** thủ tục đệ quy mà việc cuối cùng là gọi lại chính nó, có thể đổi thành vòng lặp (Problem 7-4). LU-DECOMPOSITION và LUP-DECOMPOSITION viết theo kiểu này: vòng lặp ngoài cùng (biến k) là một tầng đệ quy.
- **Nghịch đảo từ phân rã LUP:** cột thứ i của A⁻¹ là nghiệm của AXᵢ = eᵢ, giải bằng LUP-SOLVE. Ví dụ với A = (1 2 0; 3 4 4; 5 6 3), cột đầu là (−1,2; 1,1; −0,2)ᵀ, và A⁻¹ = (1/10)(−12 −6 8; 11 3 −4; −2 4 −2).
- **M(n), I(n) và điều kiện chính quy (regularity condition):** M(n) là thời gian nhân hai ma trận n × n, I(n) là thời gian nghịch đảo; các định lý đòi hàm thời gian "đều đặn", ví dụ I(3n) = O(I(n)) — đúng với mọi I(n) = Θ(n^c lg^d n), c > 0, d ≥ 0 (ví dụ n³: (3n)³ = 27n³). Không có điều kiện này thì phép quy dẫn sang ma trận lớn hơn có thể làm tăng thời gian quá hằng số lần.
- **Ma trận đối xứng xác định dương (symmetric positive-definite):** A = Aᵀ và xᵀAx > 0 với mọi x ≠ 0. Ví dụ A = (4 2; 2 3): xᵀAx = 4x₁² + 4x₁x₂ + 3x₂² = (2x₁ + x₂)² + 2x₂² > 0 khi x ≠ 0. Lớp ma trận này không cần chọn trụ và xuất hiện trong phương trình chuẩn.
- **Ma trận con chính đầu (leading submatrix):** Aₖ là giao của k hàng đầu và k cột đầu. Ví dụ với A = (4 2 1; 2 3 0; 1 0 2): A₁ = (4), A₂ = (4 2; 2 3), A₃ = A. Bổ đề 28.4 và 28.5 nói về Aₖ.
- **Hoàn thành bình phương (completing the square):** viết dạng toàn phương thành tổng một bình phương và phần dư, như ax² + 2bxy + cy² = a(x + (b/a)y)² + (c − b²/a)y². Ví dụ 4x² + 4xy + 3y² = 4(x + y/2)² + 2y²; số 2 chính là phần bù Schur 3 − 2·2/4. Đây là cốt lõi chứng minh Bổ đề 28.5.
- **Hàm cơ sở (basis functions) và ma trận giá trị:** F(x) = Σ cⱼfⱼ(x); ma trận A có aᵢⱼ = fⱼ(xᵢ). Ví dụ f₁ = 1, f₂ = x, f₃ = x² tại x = −1, 1, 2, 3, 5 cho các hàng (1, −1, 1), (1, 1, 1), (1, 2, 4), (1, 3, 9), (1, 5, 25).
- **Xấp xỉ bình phương tối thiểu (least-squares approximation):** chọn c để cực tiểu ‖Ac − y‖² = Σ (F(xᵢ) − yᵢ)². Ví dụ ở trên: sai số tại năm điểm là 0,171; −0,343; −0,457; 0,857; −0,229, tổng bình phương 8/7 ≈ 1,143 — không parabol nào cho tổng nhỏ hơn.
- **Phương trình chuẩn (normal equation) và giả nghịch đảo (pseudoinverse):** AᵀAc = Aᵀy; nghiệm c = A⁺y với A⁺ = (AᵀA)⁻¹Aᵀ. Ví dụ hàng đầu của A⁺ ở trên là (0,5; 0,3; 0,2; 0,1; −0,1), nên c₁ = 0,5·2 + 0,3·1 + 0,2·1 + 0,1·0 − 0,1·3 = 1,2. Khi A vuông khả nghịch, A⁺ = A⁻¹.
- **Ma trận ba đường chéo (tridiagonal) và spline bậc ba (cubic spline):** ma trận chỉ khác 0 trên đường chéo chính và hai đường sát nó; spline là đường cong ghép từ các đa thức bậc ba tại các nút. Ví dụ hệ cho đạo hàm của spline tự nhiên qua 4 điểm cách đều có ma trận (2 1 0 0; 1 4 1 0; 0 1 4 1; 0 0 1 2). Problem 28-1 và 28-2 cho thấy hệ này giải được trong O(n).

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 813)

Vì các phép toán trên ma trận nằm ở trung tâm của tính toán khoa học, thuật toán hiệu quả cho ma trận có rất nhiều ứng dụng thực tế. Chương này tập trung vào cách nhân ma trận và cách giải hệ phương trình tuyến tính đồng thời. Phụ lục D ôn lại kiến thức cơ bản về ma trận.

Mục 28.1 trình bày cách giải hệ phương trình tuyến tính bằng phân rã LUP. Mục 28.2 khảo sát quan hệ chặt chẽ giữa phép nhân và phép nghịch đảo ma trận. Mục 28.3 bàn về lớp ma trận quan trọng là ma trận đối xứng xác định dương và chỉ ra cách dùng chúng để tìm nghiệm bình phương tối thiểu cho một hệ phương trình tuyến tính thừa phương trình.

Một vấn đề quan trọng trong thực tế là **ổn định số học** (numerical stability). Vì số dấu phẩy động trong máy tính thật có độ chính xác giới hạn, sai số làm tròn trong tính toán số có thể bị khuếch đại dần trong quá trình tính, dẫn tới kết quả sai; những phép tính như vậy gọi là **không ổn định số học** (numerically unstable). Chương chỉ thỉnh thoảng nhắc tới ổn định số học chứ không tập trung vào nó; tác giả giới thiệu cuốn sách của Golub và Van Loan cho người muốn tìm hiểu kỹ.

### 2. Giải hệ phương trình tuyến tính (28.1 Solving systems of linear equations, trang 813–827)

Rất nhiều ứng dụng cần giải hệ phương trình tuyến tính đồng thời. Ta viết hệ thành một phương trình ma trận, trong đó mỗi phần tử ma trận hay vectơ thuộc một trường, thường là tập số thực ℝ. Mục này giải hệ bằng phương pháp gọi là phân rã LUP.

#### 2.1. Hệ phương trình và nghiệm

Xét hệ n phương trình tuyến tính với n ẩn x₁, x₂, …, xₙ:

```text
a₁₁x₁ + a₁₂x₂ + … + a₁ₙxₙ = b₁ ,
a₂₁x₁ + a₂₂x₂ + … + a₂ₙxₙ = b₂ ,
   ⋮
aₙ₁x₁ + aₙ₂x₂ + … + aₙₙxₙ = bₙ .                                   (28.1)
```

Một **nghiệm** của (28.1) là một bộ giá trị x₁, …, xₙ thoả đồng thời mọi phương trình. Mục này chỉ xét trường hợp có đúng n phương trình và n ẩn. Viết dưới dạng ma trận–vectơ:

```text
⎛ a₁₁ a₁₂ … a₁ₙ ⎞ ⎛ x₁ ⎞   ⎛ b₁ ⎞
⎜ a₂₁ a₂₂ … a₂ₙ ⎟ ⎜ x₂ ⎟ = ⎜ b₂ ⎟
⎜  ⋮   ⋮  ⋱  ⋮  ⎟ ⎜ ⋮  ⎟   ⎜ ⋮  ⎟
⎝ aₙ₁ aₙ₂ … aₙₙ ⎠ ⎝ xₙ ⎠   ⎝ bₙ ⎠
```

hay, với A = (aᵢⱼ), x = (xᵢ), b = (bᵢ):

```text
Ax = b .                                                            (28.2)
```

Nếu A không suy biến, A có nghịch đảo A⁻¹ và

```text
x = A⁻¹b                                                            (28.3)
```

là vectơ nghiệm. Nghiệm này duy nhất: nếu có hai nghiệm x và x′ thì Ax = Ax′ = b, và với I là ma trận đơn vị,

```text
x = Ix = (A⁻¹A)x = A⁻¹(Ax) = A⁻¹(Ax′) = (A⁻¹A)x′ = x′ .
```

Mục này chủ yếu quan tâm trường hợp A không suy biến, tương đương (Định lý D.1) với hạng của A bằng số ẩn n. Các khả năng khác cũng đáng nhắc qua. Nếu số phương trình ít hơn số ẩn n — hay tổng quát hơn, nếu hạng của A nhỏ hơn n — thì hệ **thiếu phương trình** (underdetermined); hệ như vậy thường có vô số nghiệm, nhưng cũng có thể vô nghiệm nếu các phương trình mâu thuẫn nhau. Nếu số phương trình nhiều hơn số ẩn n, hệ **thừa phương trình** (overdetermined) và có thể không có nghiệm nào. Mục 28.3 giải quyết bài toán quan trọng là tìm nghiệm xấp xỉ tốt cho hệ thừa phương trình.

Quay lại bài toán Ax = b gồm n phương trình n ẩn. Có thể tính A⁻¹ rồi nhân b với A⁻¹ theo (28.3). Cách này trong thực tế bị **không ổn định số học**. May mắn là có cách khác — phân rã LUP — ổn định số học và còn nhanh hơn trong thực tế.

#### 2.2. Tổng quan về phân rã LUP (Overview of LUP decomposition)

Ý tưởng là tìm ba ma trận n × n L, U, P sao cho

```text
PA = LU ,                                                           (28.4)
```

trong đó L là ma trận **tam giác dưới đơn vị** (unit lower-triangular: mọi phần tử trên đường chéo bằng 1, mọi phần tử phía trên đường chéo bằng 0), U là ma trận **tam giác trên** (upper-triangular), và P là **ma trận hoán vị** (permutation matrix). Bộ ba L, U, P thoả (28.4) gọi là một **phân rã LUP** của A. Sách sẽ chỉ ra mọi ma trận không suy biến đều có phân rã như vậy.

Lợi ích: hệ tam giác dễ giải hơn nhiều, và cả L lẫn U đều tam giác. Có phân rã LUP rồi, ta giải Ax = b chỉ bằng các hệ tam giác. Nhân hai vế Ax = b với P được PAx = Pb, tức là chỉ hoán đổi thứ tự các phương trình của (28.1) (Exercise D.1-4). Dùng (28.4):

```text
LUx = Pb .
```

Đặt y = Ux, với x là vectơ nghiệm cần tìm. Trước hết giải hệ tam giác dưới

```text
Ly = Pb                                                             (28.5)
```

để tìm y bằng **phép thế tiến** (forward substitution). Có y rồi, giải hệ tam giác trên

```text
Ux = y                                                              (28.6)
```

để tìm x bằng **phép thế lùi** (back substitution). Vì ma trận hoán vị P khả nghịch (Exercise D.2-3), nhân hai vế (28.4) với P⁻¹ được P⁻¹PA = P⁻¹LU, tức

```text
A = P⁻¹LU .                                                         (28.7)
```

Do đó x tìm được đúng là nghiệm của Ax = b:

```text
Ax = P⁻¹LUx     (theo (28.7))
   = P⁻¹Ly      (theo (28.6))
   = P⁻¹Pb      (theo (28.5))
   = b .
```

Việc tiếp theo là chỉ ra phép thế tiến và lùi hoạt động ra sao, rồi giải bài toán tính chính phân rã LUP.

#### 2.3. Phép thế tiến và phép thế lùi (Forward and back substitution)

**Phép thế tiến** giải hệ tam giác dưới (28.5) trong Θ(n²), khi biết L, P và b. Để tiện, biểu diễn hoán vị P gọn bằng mảng π[1..n]: với i = 1, 2, …, n, phần tử π[i] cho biết P(i, π[i]) = 1 và P(i, j) = 0 với j ≠ π[i]. Như vậy PA có phần tử a_π[i],j ở hàng i cột j, và Pb có phần tử thứ i là b_π[i]. Vì L tam giác dưới đơn vị, (28.5) viết lại thành

```text
y₁                                   = b_π[1] ,
l₂₁y₁ + y₂                           = b_π[2] ,
l₃₁y₁ + l₃₂y₂ + y₃                   = b_π[3] ,
   ⋮
lₙ₁y₁ + lₙ₂y₂ + lₙ₃y₃ + … + yₙ       = b_π[n] .
```

Phương trình đầu cho y₁ = b_π[1]. Biết y₁, thế vào phương trình thứ hai được y₂ = b_π[2] − l₂₁y₁. Thế cả y₁ và y₂ vào phương trình thứ ba được y₃ = b_π[3] − (l₃₁y₁ + l₃₂y₂). Tổng quát, thế y₁, …, yᵢ₋₁ "tiến" vào phương trình thứ i:

```text
yᵢ = b_π[i] − Σⱼ₌₁^(i−1) lᵢⱼ yⱼ .
```

**Phép thế lùi** tương tự, nhưng giải phương trình thứ n trước rồi đi lùi về phương trình thứ nhất; cũng chạy Θ(n²). Vì U tam giác trên, (28.6) viết lại thành

```text
u₁₁x₁ + u₁₂x₂ + … + u₁,ₙ₋₂xₙ₋₂ + u₁,ₙ₋₁xₙ₋₁ + u₁ₙxₙ = y₁ ,
        u₂₂x₂ + … + u₂,ₙ₋₂xₙ₋₂ + u₂,ₙ₋₁xₙ₋₁ + u₂ₙxₙ = y₂ ,
   ⋮
             uₙ₋₂,ₙ₋₂xₙ₋₂ + uₙ₋₂,ₙ₋₁xₙ₋₁ + uₙ₋₂,ₙxₙ = yₙ₋₂ ,
                            uₙ₋₁,ₙ₋₁xₙ₋₁ + uₙ₋₁,ₙxₙ = yₙ₋₁ ,
                                             uₙ,ₙxₙ = yₙ .
```

Giải lần lượt xₙ, xₙ₋₁, …, x₁:

```text
xₙ   = yₙ / uₙ,ₙ ,
xₙ₋₁ = (yₙ₋₁ − uₙ₋₁,ₙxₙ) / uₙ₋₁,ₙ₋₁ ,
xₙ₋₂ = (yₙ₋₂ − (uₙ₋₂,ₙ₋₁xₙ₋₁ + uₙ₋₂,ₙxₙ)) / uₙ₋₂,ₙ₋₂ ,
   ⋮
```

hay tổng quát

```text
xᵢ = ( yᵢ − Σⱼ₌ᵢ₊₁ⁿ uᵢⱼ xⱼ ) / uᵢᵢ .
```

Cho P, L, U và b, thủ tục LUP-SOLVE kết hợp phép thế tiến và lùi để tìm x. Pseudocode giả định kích thước n nằm ở thuộc tính L.rows và P được biểu diễn bằng mảng π:

```text
LUP-SOLVE(L, U, π, b)
1  n = L.rows
2  let x be a new vector of length n
3  for i = 1 to n
4      yᵢ = b_π[i] − Σⱼ₌₁^(i−1) lᵢⱼ yⱼ
5  for i = n downto 1
6      xᵢ = ( yᵢ − Σⱼ₌ᵢ₊₁ⁿ uᵢⱼ xⱼ ) / uᵢᵢ
7  return x
```

Dòng 3–4 giải y bằng phép thế tiến; dòng 5–6 giải x bằng phép thế lùi. Vì tổng Σ trong mỗi vòng for chứa một vòng lặp ẩn (lần lượt i − 1 và n − i số hạng), thời gian chạy là Θ(n²): tổng số phép nhân là Σᵢ (i − 1) + Σᵢ (n − i) = n(n − 1), cộng n phép chia.

**Ví dụ chạy tay (ví dụ của sách).** Xét hệ

```text
⎛ 1 2 0 ⎞       ⎛ 3 ⎞                 ⎛ 1 2 0 ⎞        ⎛ 3 ⎞
⎜ 3 4 4 ⎟ x  =  ⎜ 7 ⎟ ,   tức   A  =  ⎜ 3 4 4 ⎟ ,  b = ⎜ 7 ⎟ .
⎝ 5 6 3 ⎠       ⎝ 8 ⎠                 ⎝ 5 6 3 ⎠        ⎝ 8 ⎠
```

Phân rã LUP là

```text
    ⎛ 1    0    0 ⎞        ⎛ 5   6     3   ⎞        ⎛ 0 0 1 ⎞
L = ⎜ 0,2  1    0 ⎟ ,  U = ⎜ 0   0,8  −0,6 ⎟ ,  P = ⎜ 1 0 0 ⎟ .
    ⎝ 0,6  0,5  1 ⎠        ⎝ 0   0     2,5 ⎠        ⎝ 0 1 0 ⎠
```

(Sách mời người đọc kiểm tra PA = LU.) Kiểm tra của người tổng hợp: PA là A với các hàng xếp theo thứ tự hàng 3, hàng 1, hàng 2 (π = (3, 1, 2)): PA = (5 6 3; 1 2 0; 3 4 4). Tích LU: hàng 1 là (5, 6, 3); hàng 2 là 0,2·(5, 6, 3) + (0, 0,8, −0,6) = (1, 2, 0); hàng 3 là 0,6·(5, 6, 3) + 0,5·(0, 0,8, −0,6) + (0, 0, 2,5) = (3, 3,6 + 0,4, 1,8 − 0,3 + 2,5) = (3, 4, 4). Khớp.

Phép thế tiến giải Ly = Pb với Pb = (b₃, b₁, b₂) = (8, 3, 7):

```text
⎛ 1    0    0 ⎞ ⎛ y₁ ⎞   ⎛ 8 ⎞
⎜ 0,2  1    0 ⎟ ⎜ y₂ ⎟ = ⎜ 3 ⎟
⎝ 0,6  0,5  1 ⎠ ⎝ y₃ ⎠   ⎝ 7 ⎠

y₁ = 8
y₂ = 3 − 0,2·8 = 1,4
y₃ = 7 − (0,6·8 + 0,5·1,4) = 7 − 4,8 − 0,7 = 1,5        ⇒ y = (8; 1,4; 1,5)
```

Phép thế lùi giải Ux = y:

```text
⎛ 5   6     3   ⎞ ⎛ x₁ ⎞   ⎛ 8   ⎞
⎜ 0   0,8  −0,6 ⎟ ⎜ x₂ ⎟ = ⎜ 1,4 ⎟
⎝ 0   0     2,5 ⎠ ⎝ x₃ ⎠   ⎝ 1,5 ⎠

x₃ = 1,5 / 2,5 = 0,6
x₂ = (1,4 − (−0,6)·0,6) / 0,8 = (1,4 + 0,36) / 0,8 = 2,2
x₁ = (8 − (6·2,2 + 3·0,6)) / 5 = (8 − 13,2 − 1,8) / 5 = −1,4
                                                   ⇒ x = (−1,4; 2,2; 0,6)
```

Kiểm tra trên hệ gốc: −1,4 + 2·2,2 = 3; 3·(−1,4) + 4·2,2 + 4·0,6 = −4,2 + 8,8 + 2,4 = 7; 5·(−1,4) + 6·2,2 + 3·0,6 = −7 + 13,2 + 1,8 = 8. Đúng.

#### 2.4. Tính phân rã LU (Computing an LU decomposition)

Đã thấy: nếu có phân rã LUP của ma trận không suy biến A thì phép thế tiến và lùi giải được Ax = b. Giờ ta tính phân rã. Bắt đầu với trường hợp không có P (tức P = Iₙ): tìm A = LU. Hai ma trận L và U như vậy gọi là một **phân rã LU** của A.

Ta dùng **khử Gauss** (Gaussian elimination). Trừ các bội của phương trình đầu khỏi các phương trình khác để khử biến thứ nhất khỏi chúng. Sau đó trừ các bội của phương trình thứ hai khỏi phương trình thứ ba trở đi, để khử cả biến thứ nhất và thứ hai. Tiếp tục cho tới khi hệ còn lại có dạng tam giác trên — đó chính là U. Ma trận L gồm các hệ số nhân hàng đã dùng để khử biến.

Thuật toán được viết theo lối đệ quy. Muốn tìm phân rã LU của ma trận không suy biến A cỡ n × n. Nếu n = 1 thì xong: chọn L = I₁ và U = A. Với n > 1, tách A thành bốn phần:

```text
    ⎛ a₁₁ │ a₁₂ … a₁ₙ ⎞
    ⎜─────┼───────────⎟
A = ⎜ a₂₁ │ a₂₂ … a₂ₙ ⎟   =  ⎛ a₁₁  wᵀ ⎞
    ⎜  ⋮  │  ⋮  ⋱  ⋮  ⎟      ⎝ v    A′ ⎠
    ⎝ aₙ₁ │ aₙ₂ … aₙₙ ⎠
```

trong đó v là vectơ cột (n − 1) phần tử (a₂₁, …, aₙ₁)ᵀ, wᵀ là vectơ hàng (n − 1) phần tử (a₁₂, …, a₁ₙ), và A′ là ma trận (n − 1) × (n − 1) còn lại. Bằng đại số ma trận (có thể kiểm tra bằng cách nhân ra), ta phân tích

```text
A = ⎛ a₁₁  wᵀ ⎞ = ⎛ 1        0    ⎞ ⎛ a₁₁   wᵀ           ⎞
    ⎝ v    A′ ⎠   ⎝ v/a₁₁   Iₙ₋₁  ⎠ ⎝ 0     A′ − vwᵀ/a₁₁ ⎠          (28.8)
```

Các số 0 trong ma trận thứ nhất và thứ hai của (28.8) lần lượt là vectơ hàng và vectơ cột (n − 1) phần tử. Số hạng vwᵀ/a₁₁ — **tích ngoài** của v và w, mỗi phần tử chia cho a₁₁ — là ma trận (n − 1) × (n − 1), cùng cỡ với A′ mà nó bị trừ đi. Ma trận (n − 1) × (n − 1) thu được

```text
A′ − vwᵀ/a₁₁                                                        (28.9)
```

gọi là **phần bù Schur** (Schur complement) của A theo a₁₁.

*Kiểm tra (28.8) của người tổng hợp:* nhân hai ma trận vế phải theo khối: khối trên trái 1·a₁₁ = a₁₁; trên phải 1·wᵀ = wᵀ; dưới trái (v/a₁₁)·a₁₁ = v; dưới phải (v/a₁₁)wᵀ + Iₙ₋₁(A′ − vwᵀ/a₁₁) = A′. Đúng bằng A.

**Khẳng định: nếu A không suy biến thì phần bù Schur cũng không suy biến.** Giả sử phần bù Schur (cỡ (n − 1) × (n − 1)) suy biến. Theo Định lý D.1, hạng hàng của nó nhỏ hơn hẳn n − 1. Vì n − 1 phần tử dưới của cột đầu ma trận

```text
⎛ a₁₁   wᵀ           ⎞
⎝ 0     A′ − vwᵀ/a₁₁ ⎠
```

đều bằng 0, n − 1 hàng dưới của ma trận này có hạng hàng nhỏ hơn hẳn n − 1. Do đó hạng hàng của cả ma trận nhỏ hơn hẳn n. Áp dụng Exercise D.2-8 (hạng của tích không vượt hạng của từng thừa số) cho (28.8), A có hạng nhỏ hơn hẳn n, và theo Định lý D.1, A suy biến — mâu thuẫn.

Vì phần bù Schur không suy biến, ta tìm đệ quy phân rã LU của nó: giả sử

```text
A′ − vwᵀ/a₁₁ = L′U′ ,
```

với L′ tam giác dưới đơn vị và U′ tam giác trên. Khi đó

```text
A = ⎛ 1       0    ⎞ ⎛ a₁₁  wᵀ           ⎞
    ⎝ v/a₁₁   Iₙ₋₁ ⎠ ⎝ 0    A′ − vwᵀ/a₁₁ ⎠

  = ⎛ 1       0    ⎞ ⎛ a₁₁  wᵀ  ⎞
    ⎝ v/a₁₁   Iₙ₋₁ ⎠ ⎝ 0    L′U′ ⎠

  = ⎛ 1       0  ⎞ ⎛ a₁₁  wᵀ ⎞
    ⎝ v/a₁₁   L′ ⎠ ⎝ 0    U′ ⎠

  = LU ,
```

cho ta phân rã LU. (Vì L′ tam giác dưới đơn vị nên L cũng vậy; vì U′ tam giác trên nên U cũng vậy.) Bước thứ ba đúng vì (1 0; v/a₁₁ L′)(a₁₁ wᵀ; 0 U′) có khối dưới phải (v/a₁₁)wᵀ + L′U′, giống hệt khối dưới phải (v/a₁₁)wᵀ + Iₙ₋₁L′U′ của tích ở dòng thứ hai.

**Khi nào phương pháp hỏng.** Nếu a₁₁ = 0 thì phương pháp không dùng được vì phải chia cho 0. Nó cũng hỏng nếu phần tử góc trên trái của phần bù Schur A′ − vwᵀ/a₁₁ bằng 0, vì ở bước đệ quy tiếp theo ta chia cho phần tử đó. Các phần tử đem chia trong quá trình phân rã LU gọi là **phần tử trụ** (pivots), và chúng nằm trên đường chéo của U. Lý do đưa ma trận hoán vị P vào phân rã LUP là để tránh chia cho 0. Dùng hoán vị để tránh chia cho 0 (hoặc cho số nhỏ — điều góp phần gây không ổn định số học) gọi là **chọn trụ** (pivoting).

Một lớp ma trận quan trọng mà phân rã LU luôn chạy đúng là lớp **ma trận đối xứng xác định dương**. Chúng không cần chọn trụ, nên có thể dùng chiến lược đệ quy trên mà không sợ chia cho 0. Mục 28.3 chứng minh điều này cùng vài kết quả khác.

**Pseudocode.** Mã cho phân rã LU theo đúng chiến lược đệ quy, chỉ khác là vòng lặp thay cho đệ quy (phép biến đổi chuẩn cho thủ tục "đệ quy đuôi" — thủ tục mà thao tác cuối cùng là gọi đệ quy chính nó; xem Problem 7-4). Thủ tục giả định A.rows là kích thước của A. Ma trận U được khởi tạo với các số 0 dưới đường chéo, ma trận L với các số 1 trên đường chéo và các số 0 phía trên đường chéo.

```text
LU-DECOMPOSITION(A)
 1  n = A.rows
 2  let L and U be new n × n matrices
 3  initialize U with 0s below the diagonal
 4  initialize L with 1s on the diagonal and 0s above the diagonal
 5  for k = 1 to n
 6      u_kk = a_kk
 7      for i = k + 1 to n
 8          l_ik = a_ik / u_kk          // l_ik holds vᵢ
 9          u_ki = a_ki                 // u_ki holds wᵢᵀ
10      for i = k + 1 to n
11          for j = k + 1 to n
12              a_ij = a_ij − l_ik u_kj
13  return L and U
```

Giải thích: vòng for ngoài cùng (dòng 5) chạy một lần cho mỗi bước đệ quy. Trong vòng này, dòng 6 xác định trụ u_kk = a_kk. Vòng for dòng 7–9 (không chạy khi k = n) dùng các vectơ v và wᵀ để cập nhật L và U: dòng 8 tính các phần tử của v/a_kk, lưu vᵢ/u_kk vào l_ik (chú thích "l_ik holds vᵢ" nghĩa là ô l_ik giữ phần tử ứng với vᵢ — đã chia cho trụ); dòng 9 lưu các phần tử của wᵀ vào u_ki. Cuối cùng dòng 10–12 tính các phần tử của phần bù Schur và ghi đè lại vào A. (Không cần chia cho a_kk ở dòng 12 vì đã chia khi tính l_ik ở dòng 8: l_ik u_kj = (a_ik/a_kk)·a_kj = vᵢwⱼ/a_kk.) Vì dòng 12 nằm trong ba vòng lồng nhau, LU-DECOMPOSITION chạy Θ(n³). Đếm chính xác (người tổng hợp): dòng 12 thực hiện Σₖ₌₁ⁿ (n − k)² = (n − 1)n(2n − 1)/6 ≈ n³/3 lần.

**Phiên bản tại chỗ.** Có một cách tối ưu chuẩn: lưu các phần tử có nghĩa của L và U ngay trong ma trận A. Tức là cho mỗi aᵢⱼ ứng với lᵢⱼ (nếu i > j) hoặc uᵢⱼ (nếu i ≤ j), và cập nhật A để khi thủ tục kết thúc A chứa cả L lẫn U (đường chéo toàn số 1 của L không cần lưu). Để có pseudocode cho bản tối ưu này, chỉ cần thay mọi tham chiếu tới l hoặc u bằng a; dễ kiểm tra rằng phép biến đổi này giữ nguyên tính đúng.

**Ví dụ chạy tay phân rã LU (Hình 28.1 của sách, vẽ lại dưới dạng tại chỗ).** Ma trận

```text
    ⎛ 2   3   1   5  ⎞
A = ⎜ 6   13  5   19 ⎟
    ⎜ 2   19  10  23 ⎟
    ⎝ 4   10  11  31 ⎠
```

Trong hình gốc, trụ được khoanh tròn đen, cột v/trụ và hàng wᵀ được tô xám, đường kẻ ngang tách phần đã thuộc U (phía trên), đường kẻ dọc tách phần đã thuộc L (bên trái), góc dưới phải là phần bù Schur hiện tại. Dưới đây dùng [ ] cho trụ và dấu │, ─ cho các đường kẻ.

```text
(a) ma trận A ban đầu        (b) bước k = 1, trụ a₁₁ = 2
  2   3   1   5               [2]  3   1   5        ← hàng wᵀ = (3, 1, 5) vào U
  6  13   5  19               ───┬──────────
  2  19  10  23                3 │ 4   2   4        cột v/2 = (6,2,4)/2 = (3,1,2)
  4  10  11  31                1 │16   9  18        vào L
                               2 │ 4   9  21
                              phần bù Schur = (13 5 19; 19 10 23; 10 11 31)
                                             − (6;2;4)(3 1 5)/2
                                           = (13−9 5−3 19−15; 19−3 10−1 23−5;
                                              10−6 11−2 31−10)
                                           = (4 2 4; 16 9 18; 4 9 21)

(c) bước k = 2, trụ 4         (d) bước k = 3, trụ 1; A đã phân rã xong
  2   3   1   5                2   3   1   5
  3  [4]  2   4                3   4   2   4
  ───────┬──────               1   4  [1]  2
  1   4  │1   2                ───────────┬──
  2   1  │7  17                2   1   7  │3
  cột (16, 4)/4 = (4, 1) vào L  cột 7/1 = 7 vào L; phần bù Schur mới
  hàng (2, 4) vào U             17 − 7·2 = 3 trở thành u₄₄ khi đệ quy dừng
  Schur: (9 − 4·2, 18 − 4·4;
          9 − 1·2, 21 − 1·4)
       = (1 2; 7 17)
```

Kết quả (e):

```text
⎛ 2   3   1   5  ⎞   ⎛ 1 0 0 0 ⎞ ⎛ 2 3 1 5 ⎞
⎜ 6   13  5   19 ⎟ = ⎜ 3 1 0 0 ⎟ ⎜ 0 4 2 4 ⎟
⎜ 2   19  10  23 ⎟   ⎜ 1 4 1 0 ⎟ ⎜ 0 0 1 2 ⎟
⎝ 4   10  11  31 ⎠   ⎝ 2 1 7 1 ⎠ ⎝ 0 0 0 3 ⎠
       A                  L           U
```

Kiểm tra hàng cuối (người tổng hợp): 2·(2, 3, 1, 5) + 1·(0, 4, 2, 4) + 7·(0, 0, 1, 2) + 1·(0, 0, 0, 3) = (4, 6 + 4, 2 + 2 + 7, 10 + 4 + 14 + 3) = (4, 10, 11, 31). Đúng. Các trụ là 2, 4, 1, 3 (đường chéo của U).

#### 2.5. Tính phân rã LUP (Computing an LUP decomposition)

Nói chung, khi giải Ax = b ta phải chọn trụ ở các phần tử ngoài đường chéo của A để tránh chia cho 0. Chia cho 0 dĩ nhiên là thảm hoạ. Nhưng ta cũng muốn tránh chia cho một số nhỏ — kể cả khi A không suy biến — vì có thể dẫn tới không ổn định số học. Vì vậy ta cố chọn trụ là một giá trị lớn.

Toán học đằng sau phân rã LUP giống phân rã LU. Cho A cỡ n × n không suy biến, cần tìm ma trận hoán vị P, ma trận tam giác dưới đơn vị L và ma trận tam giác trên U với PA = LU. Trước khi tách A như với phân rã LU, ta chuyển một phần tử khác 0, gọi là aₖ₁, từ đâu đó trong cột đầu lên vị trí (1, 1). Để ổn định số học, chọn aₖ₁ là phần tử có **trị tuyệt đối lớn nhất** trong cột đầu. (Cột đầu không thể toàn số 0, vì khi đó định thức của A bằng 0 theo Định lý D.4 và D.5, nên A suy biến.) Để giữ nguyên tập phương trình, đổi hàng 1 với hàng k; việc này tương đương với nhân A bên trái với một ma trận hoán vị Q (Exercise D.1-4). Viết

```text
QA = ⎛ aₖ₁  wᵀ ⎞
     ⎝ v    A′ ⎠ ,
```

trong đó v = (a₂₁, a₃₁, …, aₙ₁)ᵀ ngoại trừ a₁₁ thay vào chỗ của aₖ₁; wᵀ = (aₖ₂, aₖ₃, …, aₖₙ); và A′ là ma trận (n − 1) × (n − 1). Vì aₖ₁ ≠ 0, ta làm gần như cùng phép đại số tuyến tính như phân rã LU, nhưng giờ chắc chắn không chia cho 0:

```text
QA = ⎛ aₖ₁  wᵀ ⎞ = ⎛ 1        0    ⎞ ⎛ aₖ₁  wᵀ           ⎞
     ⎝ v    A′ ⎠   ⎝ v/aₖ₁   Iₙ₋₁  ⎠ ⎝ 0    A′ − vwᵀ/aₖ₁ ⎠ .
```

Như với phân rã LU, nếu A không suy biến thì phần bù Schur A′ − vwᵀ/aₖ₁ cũng không suy biến. Do đó tìm đệ quy được phân rã LUP của nó, với ma trận tam giác dưới đơn vị L′, tam giác trên U′ và hoán vị P′:

```text
P′(A′ − vwᵀ/aₖ₁) = L′U′ .
```

Định nghĩa

```text
P = ⎛ 1  0  ⎞ Q ,
    ⎝ 0  P′ ⎠
```

là ma trận hoán vị vì là tích của hai ma trận hoán vị (Exercise D.1-4). Khi đó

```text
PA = ⎛ 1  0  ⎞ QA
     ⎝ 0  P′ ⎠

   = ⎛ 1  0  ⎞ ⎛ 1       0    ⎞ ⎛ aₖ₁  wᵀ           ⎞
     ⎝ 0  P′ ⎠ ⎝ v/aₖ₁   Iₙ₋₁ ⎠ ⎝ 0    A′ − vwᵀ/aₖ₁ ⎠

   = ⎛ 1         0  ⎞ ⎛ aₖ₁  wᵀ           ⎞
     ⎝ P′v/aₖ₁   P′ ⎠ ⎝ 0    A′ − vwᵀ/aₖ₁ ⎠

   = ⎛ 1         0    ⎞ ⎛ aₖ₁  wᵀ               ⎞
     ⎝ P′v/aₖ₁   Iₙ₋₁ ⎠ ⎝ 0    P′(A′ − vwᵀ/aₖ₁) ⎠

   = ⎛ 1         0    ⎞ ⎛ aₖ₁  wᵀ   ⎞
     ⎝ P′v/aₖ₁   Iₙ₋₁ ⎠ ⎝ 0    L′U′ ⎠

   = ⎛ 1         0  ⎞ ⎛ aₖ₁  wᵀ ⎞
     ⎝ P′v/aₖ₁   L′ ⎠ ⎝ 0    U′ ⎠

   = LU ,
```

cho ta phân rã LUP. Vì L′ tam giác dưới đơn vị nên L cũng vậy, và vì U′ tam giác trên nên U cũng vậy. (Giải thích của người tổng hợp: bước thứ ba nhân ma trận (1 0; 0 P′) vào ma trận đầu; bước thứ tư đúng vì khối dưới phải của tích ở bước thứ ba là (P′v/aₖ₁)wᵀ + P′(A′ − vwᵀ/aₖ₁), bằng khối dưới phải của tích ở bước thứ tư là (P′v/aₖ₁)wᵀ + Iₙ₋₁·P′(A′ − vwᵀ/aₖ₁); các khối khác của hai tích cũng trùng nhau.)

Lưu ý: trong phép suy dẫn này, khác với phân rã LU, ta phải nhân **cả** vectơ cột v/aₖ₁ **lẫn** phần bù Schur A′ − vwᵀ/aₖ₁ với ma trận hoán vị P′. Pseudocode:

```text
LUP-DECOMPOSITION(A)
 1  n = A.rows
 2  let π[1..n] be a new array
 3  for i = 1 to n
 4      π[i] = i
 5  for k = 1 to n
 6      p = 0
 7      for i = k to n
 8          if |a_ik| > p
 9              p = |a_ik|
10              k′ = i
11      if p == 0
12          error "singular matrix"
13      exchange π[k] with π[k′]
14      for i = 1 to n
15          exchange a_ki with a_k′i
16      for i = k + 1 to n
17          a_ik = a_ik / a_kk
18          for j = k + 1 to n
19              a_ij = a_ij − a_ik a_kj
```

Giống LU-DECOMPOSITION, thủ tục thay đệ quy bằng vòng lặp. Như một cải tiến so với cài đặt trực tiếp phép đệ quy, ta duy trì động ma trận hoán vị P dưới dạng mảng π, trong đó π[i] = j nghĩa là hàng i của P có số 1 ở cột j. L và U cũng được tính "tại chỗ" trong A. Khi thủ tục kết thúc,

```text
       ⎧ lᵢⱼ   nếu i > j ,
aᵢⱼ =  ⎨
       ⎩ uᵢⱼ   nếu i ≤ j .
```

Từng dòng: dòng 3–4 khởi tạo π là hoán vị đồng nhất. Vòng for ngoài (dòng 5) thực hiện phép đệ quy. Mỗi lần qua vòng ngoài, dòng 6–10 tìm phần tử a_k′k có trị tuyệt đối lớn nhất trong cột đầu hiện tại (cột k) của ma trận (n − k + 1) × (n − k + 1) đang cần phân rã. Nếu mọi phần tử trong cột đầu hiện tại bằng 0, dòng 11–12 báo ma trận suy biến. Để chọn trụ, dòng 13 đổi π[k′] với π[k], và dòng 14–15 đổi hàng thứ k với hàng thứ k′ của A, làm cho phần tử trụ thành a_kk. (Đổi **toàn bộ** hàng — kể cả phần bên trái đã thuộc L — vì trong phép suy dẫn ở trên, không chỉ A′ − vwᵀ/aₖ₁ mà cả v/aₖ₁ đều bị nhân với P′.) Cuối cùng dòng 16–19 tính phần bù Schur gần giống dòng 7–12 của LU-DECOMPOSITION, chỉ khác là viết để chạy tại chỗ.

Vì có ba vòng lồng nhau, LUP-DECOMPOSITION chạy Θ(n³), bằng LU-DECOMPOSITION. Vậy chọn trụ chỉ tốn thêm tối đa một hằng số lần thời gian (phần tìm max ở dòng 7–10 và đổi hàng ở dòng 14–15 tổng cộng chỉ Θ(n²)).

**Ví dụ chạy tay phân rã LUP (Hình 28.2 của sách, vẽ lại).** Ma trận đầu vào

```text
    ⎛  2    0   2    0,6 ⎞
A = ⎜  3    3   4   −2   ⎟
    ⎜  5    5   4    2   ⎟
    ⎝ −1   −2   3,4 −1   ⎠
```

Cột bên trái mỗi bảng là mảng π (hàng hiện tại của ma trận đang chứa hàng gốc nào của A). [ ] đánh dấu trụ; │ và ─ tách vùng L (trái), vùng U (trên) và phần bù Schur (dưới phải).

```text
(a) π = (1,2,3,4); bước k = 1: trong cột 1 các trị tuyệt đối là 2, 3, 5, 1
    → trụ là 5 ở hàng 3
    1 │  2    0    2    0,6
    2 │  3    3    4   −2
    3 │ [5]   5    4    2
    4 │ −1   −2    3,4 −1

(b) đổi hàng 1 và hàng 3, π = (3,2,1,4); v = (3, 2, −1)ᵀ, wᵀ = (5, 4, 2)
    3 │ [5]   5    4    2
    2 │  3    3    4   −2
    1 │  2    0    2    0,6
    4 │ −1   −2    3,4 −1

(c) thay v bằng v/5 = (0,6; 0,4; −0,2); tính phần bù Schur
    hàng 2: (3 − 0,6·5, 4 − 0,6·4, −2 − 0,6·2) = (0, 1,6, −3,2)
    hàng 3: (0 − 0,4·5, 2 − 0,4·4, 0,6 − 0,4·2) = (−2, 0,4, −0,2)
    hàng 4: (−2 + 0,2·5, 3,4 + 0,2·4, −1 + 0,2·2) = (−1, 4,2, −0,6)
    3 │  5     5    4    2
      │ ─────┬──────────────
    2 │  0,6 │ 0    1,6  −3,2
    1 │  0,4 │−2    0,4  −0,2
    4 │ −0,2 │−1    4,2  −0,6

(d) bước k = 2: trong cột 2 (phần bù Schur) các trị tuyệt đối là 0, 2, 1
    → trụ là −2 ở hàng 3 hiện tại

(e) đổi hàng 2 và hàng 3 (cả phần L), π = (3,1,2,4)
    3 │  5     5    4    2
    1 │  0,4 [−2]   0,4  −0,2
    2 │  0,6   0    1,6  −3,2
    4 │ −0,2  −1    4,2  −0,6

(f) chia cột: 0/(−2) = 0, (−1)/(−2) = 0,5; phần bù Schur
    hàng 3: (1,6 − 0·0,4, −3,2 − 0·(−0,2)) = (1,6, −3,2)
    hàng 4: (4,2 − 0,5·0,4, −0,6 − 0,5·(−0,2)) = (4, −0,5)
    3 │  5     5    4    2
    1 │  0,4  −2    0,4  −0,2
      │ ───────────┬─────────
    2 │  0,6   0   │1,6  −3,2
    4 │ −0,2   0,5 │4    −0,5

(g) bước k = 3: trị tuyệt đối 1,6 và 4 → trụ là 4 ở hàng 4
(h) đổi hàng 3 và hàng 4, π = (3,1,4,2)
    3 │  5     5    4    2
    1 │  0,4  −2    0,4  −0,2
    4 │ −0,2   0,5 [4]   −0,5
    2 │  0,6   0    1,6  −3,2

(i) chia: 1,6/4 = 0,4; phần bù Schur: −3,2 − 0,4·(−0,5) = −3
    3 │  5     5    4    2
    1 │  0,4  −2    0,4  −0,2
    4 │ −0,2   0,5  4    −0,5
      │ ─────────────────┬────
    2 │  0,6   0    0,4  │−3

    Bước k = 4 (cuối): không thay đổi gì thêm (trụ −3, chỉ có một phần tử).
```

Kết quả (j), PA = LU:

```text
⎛ 0 0 1 0 ⎞ ⎛  2   0   2    0,6 ⎞   ⎛  1    0    0    0 ⎞ ⎛ 5   5   4    2   ⎞
⎜ 1 0 0 0 ⎟ ⎜  3   3   4   −2   ⎟ = ⎜  0,4  1    0    0 ⎟ ⎜ 0  −2   0,4 −0,2 ⎟
⎜ 0 0 0 1 ⎟ ⎜  5   5   4    2   ⎟   ⎜ −0,2  0,5  1    0 ⎟ ⎜ 0   0   4   −0,5 ⎟
⎝ 0 1 0 0 ⎠ ⎝ −1  −2   3,4 −1   ⎠   ⎝  0,6  0    0,4  1 ⎠ ⎝ 0   0   0   −3   ⎠
     P                A                       L                      U
```

Hàng i của P có số 1 ở cột π[i]: π = (3, 1, 4, 2). Kiểm tra hàng cuối (người tổng hợp): 0,6·(5, 5, 4, 2) + 0·(0, −2, 0,4, −0,2) + 0,4·(0, 0, 4, −0,5) + (0, 0, 0, −3) = (3, 3, 2,4 + 1,6, 1,2 − 0,2 − 3) = (3, 3, 4, −2) — đúng là hàng 2 của A (vì π[4] = 2). Kiểm tra hàng 3: −0,2·(5, 5, 4, 2) + 0,5·(0, −2, 0,4, −0,2) + (0, 0, 4, −0,5) = (−1, −1 − 1, −0,8 + 0,2 + 4, −0,4 − 0,1 − 0,5) = (−1, −2, 3,4, −1) — đúng là hàng 4 của A.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: thư viện LAPACK (nền của NumPy/SciPy, MATLAB, R) cài đúng hai bước của mục này — hàm `getrf` tính phân rã LU có chọn trụ từng phần (partial pivoting, cùng quy tắc "trị tuyệt đối lớn nhất trong cột" như LUP-DECOMPOSITION) và hàm `getrs` giải bằng phép thế tiến và lùi; `numpy.linalg.solve` và `scipy.linalg.lu_factor`/`lu_solve` gọi chúng. Bản thực tế khác bản của sách ở chỗ tổ chức theo khối để tận dụng bộ nhớ đệm (các phép cập nhật phần bù Schur được gom thành phép nhân ma trận), nhưng số phép tính vẫn ≈ (2/3)n³ phép cộng/nhân. Mô phỏng mạch điện (SPICE), giải phương trình đạo hàm riêng bằng phần tử hữu hạn, hay bước Newton trong tối ưu đều quy về giải lặp đi lặp lại các hệ Ax = b.

### 3. Nghịch đảo ma trận (28.2 Inverting matrices, trang 827–832)

Trong thực tế, ta thường không dùng nghịch đảo ma trận để giải hệ phương trình tuyến tính, mà ưu tiên các kỹ thuật ổn định số học hơn như phân rã LUP; dù vậy đôi khi ta cần chính ma trận nghịch đảo. Mục này chỉ cách dùng phân rã LUP để tính ma trận nghịch đảo. Mục này cũng chứng minh rằng nhân ma trận và nghịch đảo ma trận là hai bài toán khó ngang nhau, theo nghĩa (với vài điều kiện kỹ thuật) có thể dùng thuật toán cho bài này để giải bài kia với cùng thời gian tiệm cận. Do đó có thể dùng thuật toán Strassen (Mục 4.2) cho phép nhân ma trận để nghịch đảo ma trận. Thực ra, bài báo gốc của Strassen được thúc đẩy bởi bài toán chứng minh rằng một hệ phương trình tuyến tính có thể giải nhanh hơn phương pháp thông thường.

#### 3.1. Tính nghịch đảo từ phân rã LUP (Computing a matrix inverse from an LUP decomposition)

Giả sử đã có phân rã LUP của A dưới dạng ba ma trận L, U, P với PA = LU. Dùng LUP-SOLVE, ta giải Ax = b trong Θ(n²). Vì phân rã LUP chỉ phụ thuộc A chứ không phụ thuộc b, ta chạy LUP-SOLVE cho một hệ thứ hai Ax = b′ với thời gian thêm Θ(n²). Tổng quát, có phân rã LUP của A rồi thì giải được k phiên bản của Ax = b chỉ khác nhau ở b trong thời gian Θ(kn²).

Phương trình

```text
AX = Iₙ ,                                                           (28.10)
```

định nghĩa ma trận X là nghịch đảo của A, có thể xem như n phương trình riêng biệt dạng Ax = b. Cụ thể, gọi Xᵢ là cột thứ i của X, và nhớ rằng vectơ đơn vị eᵢ là cột thứ i của Iₙ. Ta giải (28.10) bằng cách dùng phân rã LUP của A để giải riêng từng phương trình

```text
AXᵢ = eᵢ
```

tìm Xᵢ. Có phân rã LUP rồi, mỗi cột Xᵢ tốn Θ(n²), nên tính X từ phân rã LUP của A tốn Θ(n³). Vì phân rã LUP của A cũng tính được trong Θ(n³), ta tính được A⁻¹ trong Θ(n³).

**Ví dụ chạy tay (của người tổng hợp)** với A = (1 2 0; 3 4 4; 5 6 3) và phân rã LUP ở mục 2.3 (π = (3, 1, 2)). Cột 1: giải AX₁ = e₁ = (1, 0, 0)ᵀ. Pe₁ = (e₁[3], e₁[1], e₁[2]) = (0, 1, 0). Thế tiến: y₁ = 0; y₂ = 1 − 0,2·0 = 1; y₃ = 0 − 0,6·0 − 0,5·1 = −0,5. Thế lùi: x₃ = −0,5/2,5 = −0,2; x₂ = (1 − (−0,6)(−0,2))/0,8 = 0,88/0,8 = 1,1; x₁ = (0 − 6·1,1 − 3·(−0,2))/5 = −6/5 = −1,2. Làm tương tự cho e₂, e₃ được

```text
        1   ⎛ −12  −6   8 ⎞   ⎛ −1,2  −0,6   0,8 ⎞
A⁻¹ =  ──  ⎜  11   3  −4 ⎟ = ⎜  1,1   0,3  −0,4 ⎟
       10   ⎝  −2   4  −2 ⎠   ⎝ −0,2   0,4  −0,2 ⎠
```

(det A = 1·(12 − 24) − 2·(9 − 20) = 10). Kiểm tra: A⁻¹b = (1/10)(−36 − 42 + 64, 33 + 21 − 32, −6 + 28 − 16) = (−1,4; 2,2; 0,6), đúng nghiệm ở mục 2.3.

#### 3.2. Nhân ma trận và nghịch đảo ma trận (Matrix multiplication and matrix inversion)

Giờ ta chỉ ra rằng những tăng tốc lý thuyết cho phép nhân ma trận chuyển thành tăng tốc cho phép nghịch đảo ma trận. Thực ra ta chứng minh điều mạnh hơn: nghịch đảo ma trận **tương đương** với nhân ma trận theo nghĩa sau. Nếu M(n) là thời gian nhân hai ma trận n × n, thì nghịch đảo được ma trận n × n không suy biến trong O(M(n)). Ngược lại, nếu I(n) là thời gian nghịch đảo ma trận n × n không suy biến, thì nhân được hai ma trận n × n trong O(I(n)). Hai kết quả được chứng minh thành hai định lý riêng.

**Định lý 28.1 (Nhân không khó hơn nghịch đảo — Multiplication is no harder than inversion).** Nếu nghịch đảo được ma trận n × n trong thời gian I(n), với I(n) = Ω(n²) và I(n) thoả điều kiện chính quy I(3n) = O(I(n)), thì nhân được hai ma trận n × n trong thời gian O(I(n)).

*Chứng minh.* Gọi A và B là hai ma trận n × n cần tính tích C = AB. Định nghĩa ma trận 3n × 3n

```text
    ⎛ Iₙ  A   0  ⎞
D = ⎜ 0   Iₙ  B  ⎟ .
    ⎝ 0   0   Iₙ ⎠
```

Nghịch đảo của D là

```text
      ⎛ Iₙ  −A   AB ⎞
D⁻¹ = ⎜ 0    Iₙ  −B ⎟ ,
      ⎝ 0    0    Iₙ ⎠
```

nên tích AB là khối n × n ở góc trên phải của D⁻¹. Dựng D tốn Θ(n²), là O(I(n)) vì giả thiết I(n) = Ω(n²); nghịch đảo D tốn O(I(3n)) = O(I(n)) theo điều kiện chính quy. Vậy M(n) = O(I(n)). ∎

*Kiểm tra của người tổng hợp:* nhân D với ma trận vế phải theo khối: hàng khối 1 là (Iₙ, −A + A, AB − AB) = (Iₙ, 0, 0); hàng khối 2 là (0, Iₙ, −B + B) = (0, Iₙ, 0); hàng khối 3 là (0, 0, Iₙ). Vậy DD⁻¹ = I₃ₙ. Ví dụ n = 1, A = (2), B = (3): D = (1 2 0; 0 1 3; 0 0 1), D⁻¹ = (1 −2 6; 0 1 −3; 0 0 1), và góc trên phải là 6 = 2·3.

Lưu ý: I(n) thoả điều kiện chính quy khi I(n) = Θ(n^c lg^d n) với mọi hằng số c > 0 và d ≥ 0 (vì (3n)^c lg^d(3n) ≤ 3^c n^c (2 lg n)^d với n ≥ 3, tức không quá một hằng số lần n^c lg^d n).

Chứng minh rằng nghịch đảo không khó hơn nhân dựa vào vài tính chất của ma trận đối xứng xác định dương sẽ được chứng minh ở Mục 28.3.

**Định lý 28.2 (Nghịch đảo không khó hơn nhân — Inversion is no harder than multiplication).** Giả sử nhân được hai ma trận số thực n × n trong thời gian M(n), với M(n) = Ω(n²) và M(n) thoả hai điều kiện chính quy: M(n + k) = O(M(n)) với mọi k trong khoảng 0 ≤ k ≤ n, và M(n/2) ≤ cM(n) với hằng số c < 1/2 nào đó. Khi đó tính được nghịch đảo của mọi ma trận số thực n × n không suy biến trong thời gian O(M(n)).

*Chứng minh.* Sách chứng minh cho ma trận số thực; Exercise 28.2-6 yêu cầu tổng quát hoá cho số phức.

**Bước 0 — có thể giả định n là lũy thừa đúng của 2**, vì

```text
⎛ A  0  ⎞⁻¹   ⎛ A⁻¹  0  ⎞
⎝ 0  Iₖ ⎠   = ⎝ 0    Iₖ ⎠
```

với mọi k > 0. Chọn k để n + k là lũy thừa của 2 tiếp theo, ta phóng to ma trận và lấy A⁻¹ từ kết quả của bài toán đã phóng to. Vì n + k < 2n, điều kiện chính quy thứ nhất bảo đảm việc phóng to chỉ làm thời gian tăng tối đa một hằng số lần.

**Bước 1 — trường hợp A đối xứng xác định dương.** Tạm giả định A (n × n) đối xứng xác định dương. Chia A và A⁻¹ mỗi ma trận thành bốn khối n/2 × n/2:

```text
A = ⎛ B  Cᵀ ⎞   và   A⁻¹ = ⎛ R  T ⎞ .                                (28.11)
    ⎝ C  D  ⎠              ⎝ U  V ⎠
```

(Khối trên phải của A là Cᵀ vì A đối xứng.) Đặt

```text
S = D − CB⁻¹Cᵀ                                                      (28.12)
```

là phần bù Schur của A theo B (dạng phần bù Schur này được bàn kỹ ở Mục 28.3). Khi đó

```text
A⁻¹ = ⎛ R  T ⎞ = ⎛ B⁻¹ + B⁻¹CᵀS⁻¹CB⁻¹    −B⁻¹CᵀS⁻¹ ⎞                 (28.13)
      ⎝ U  V ⎠   ⎝ −S⁻¹CB⁻¹               S⁻¹       ⎠
```

vì AA⁻¹ = Iₙ, có thể kiểm tra bằng phép nhân ma trận. *Kiểm tra của người tổng hợp:* khối (1,1) của tích: B(B⁻¹ + B⁻¹CᵀS⁻¹CB⁻¹) + Cᵀ(−S⁻¹CB⁻¹) = I + CᵀS⁻¹CB⁻¹ − CᵀS⁻¹CB⁻¹ = I; khối (1,2): B(−B⁻¹CᵀS⁻¹) + CᵀS⁻¹ = 0; khối (2,1): C(B⁻¹ + B⁻¹CᵀS⁻¹CB⁻¹) − DS⁻¹CB⁻¹ = CB⁻¹ + (CB⁻¹Cᵀ − D)S⁻¹CB⁻¹ = CB⁻¹ − SS⁻¹CB⁻¹ = 0; khối (2,2): −CB⁻¹CᵀS⁻¹ + DS⁻¹ = (D − CB⁻¹Cᵀ)S⁻¹ = I.

Vì A đối xứng xác định dương, Bổ đề 28.4 và 28.5 (Mục 28.3) cho biết B và S đều đối xứng xác định dương. Theo Bổ đề 28.3, nghịch đảo B⁻¹ và S⁻¹ tồn tại, và theo Exercise D.2-6, B⁻¹ và S⁻¹ đối xứng: (B⁻¹)ᵀ = B⁻¹, (S⁻¹)ᵀ = S⁻¹. Do đó tính được các khối R, T, U, V của A⁻¹ như sau (mọi ma trận nhắc tới đều cỡ n/2 × n/2):

1. Lấy các khối B, C, Cᵀ, D của A.
2. Tính đệ quy nghịch đảo B⁻¹ của B.
3. Tính tích W = CB⁻¹, rồi tính chuyển vị Wᵀ, bằng B⁻¹Cᵀ (theo Exercise D.1-2, (XY)ᵀ = YᵀXᵀ, và (B⁻¹)ᵀ = B⁻¹).
4. Tính tích X = WCᵀ, bằng CB⁻¹Cᵀ, rồi tính S = D − X = D − CB⁻¹Cᵀ.
5. Tính đệ quy nghịch đảo S⁻¹ của S, gán V = S⁻¹.
6. Tính tích Y = S⁻¹W, bằng S⁻¹CB⁻¹, rồi tính chuyển vị Yᵀ, bằng B⁻¹CᵀS⁻¹ (theo Exercise D.1-2, (B⁻¹)ᵀ = B⁻¹ và (S⁻¹)ᵀ = S⁻¹). Gán T = −Yᵀ và U = −Y.
7. Tính tích Z = WᵀY, bằng B⁻¹CᵀS⁻¹CB⁻¹, rồi gán R = B⁻¹ + Z.

Như vậy, nghịch đảo một ma trận đối xứng xác định dương n × n tốn: hai lần nghịch đảo ma trận n/2 × n/2 (bước 2 và 5); bốn phép nhân ma trận n/2 × n/2 (bước 3, 4, 6, 7); cộng thêm O(n²) cho việc tách khối từ A, đặt khối vào A⁻¹, và một số hằng phép cộng, trừ, chuyển vị trên ma trận n/2 × n/2. Ta có truy hồi

```text
I(n) ≤ 2I(n/2) + 4M(n/2) + O(n²)
     = 2I(n/2) + Θ(M(n))
     = O(M(n)) .
```

Dòng thứ hai đúng vì điều kiện chính quy thứ hai cho 4M(n/2) < 2M(n), và vì M(n) = Ω(n²) (nên số hạng O(n²) bị M(n) nuốt). Dòng thứ ba đúng vì điều kiện chính quy thứ hai cho phép áp dụng trường hợp 3 của định lý thợ (Định lý 4.1): a = 2, b = 2, n^(log₂ 2) = n, f(n) = M(n) = Ω(n²) = Ω(n^(1+ε)) với ε = 1, và điều kiện "chính quy" của định lý thợ af(n/b) ≤ c′f(n) là 2M(n/2) ≤ 2cM(n) với 2c < 1. (Nhận xét của người tổng hợp: chặt chẽ thì dòng thứ hai chỉ nên viết O(M(n)); xem khối Lưu ý.)

**Ví dụ chạy tay bảy bước (của người tổng hợp)** với A = (4 2; 2 3), n = 2, các khối là số: B = 4, C = 2, D = 3.

```text
bước 2: B⁻¹ = 1/4
bước 3: W = C·B⁻¹ = 1/2 ;  Wᵀ = 1/2
bước 4: X = W·Cᵀ = 1 ;  S = D − X = 2
bước 5: V = S⁻¹ = 1/2
bước 6: Y = S⁻¹·W = 1/4 ;  T = −1/4 , U = −1/4
bước 7: Z = Wᵀ·Y = 1/8 ;  R = B⁻¹ + Z = 3/8
A⁻¹ = (3/8  −1/4; −1/4  1/2)
```

Kiểm tra: det A = 12 − 4 = 8, A⁻¹ = (1/8)(3 −2; −2 4) = (3/8 −1/4; −1/4 1/2). Đúng.

**Bước 2 — trường hợp A không suy biến bất kỳ.** Còn phải chứng minh đạt được cùng thời gian tiệm cận khi A khả nghịch nhưng không đối xứng xác định dương. Ý tưởng: với mọi A không suy biến, AᵀA đối xứng (Exercise D.1-2) và xác định dương (Định lý D.6). Mẹo là quy bài toán nghịch đảo A về bài toán nghịch đảo AᵀA. Phép quy dựa trên nhận xét: khi A là ma trận n × n không suy biến,

```text
A⁻¹ = (AᵀA)⁻¹Aᵀ ,
```

vì ((AᵀA)⁻¹Aᵀ)A = (AᵀA)⁻¹(AᵀA) = Iₙ và nghịch đảo của ma trận là duy nhất. Vậy tính A⁻¹ bằng cách: nhân Aᵀ với A được AᵀA; nghịch đảo ma trận đối xứng xác định dương AᵀA bằng thuật toán chia để trị ở trên; nhân kết quả với Aᵀ. Mỗi bước tốn O(M(n)), nên nghịch đảo mọi ma trận số thực không suy biến trong O(M(n)). ∎

(Ý của người tổng hợp về vì sao AᵀA xác định dương: xᵀAᵀAx = (Ax)ᵀ(Ax) = ‖Ax‖² ≥ 0, và bằng 0 chỉ khi Ax = 0, tức x = 0 vì A không suy biến.)

**Hệ quả phụ: giải Ax = b bằng LU không chọn trụ.** Chứng minh Định lý 28.2 gợi ý một cách giải Ax = b bằng phân rã LU **không chọn trụ**, miễn A không suy biến. Nhân hai vế với Aᵀ được (AᵀA)x = Aᵀb. Phép biến đổi này không đổi nghiệm x vì Aᵀ khả nghịch; vì AᵀA đối xứng xác định dương, phân rã LU của nó chạy được (Hệ quả 28.6). Sau đó dùng thế tiến và lùi với vế phải Aᵀb. Cách này đúng về lý thuyết, nhưng trong thực tế thủ tục LUP-DECOMPOSITION tốt hơn nhiều: phân rã LUP cần ít phép tính số học hơn một hằng số lần, và có tính chất số học tốt hơn đôi chút. (Theo hiểu biết của người tổng hợp: lập AᵀA tốn thêm khoảng n³ phép nhân và làm số điều kiện của hệ bị bình phương, nên sai số tương đối có thể lớn hơn nhiều.)

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: lời khuyên "đừng tính A⁻¹ để giải hệ" là quy tắc vàng trong tính toán số — các tài liệu của NumPy, MATLAB đều khuyên dùng `solve` (hay toán tử `\`) thay cho `inv(A) @ b`. Mặt lý thuyết của Định lý 28.1–28.2 vẫn sống: mọi tiến bộ về số mũ ω của phép nhân ma trận (từ 2,81 của Strassen xuống dưới 2,372 hiện nay) tự động là tiến bộ cho nghịch đảo, định thức và phân rã LUP, dù các thuật toán số mũ thấp đó không dùng được trong thực tế vì hằng số khổng lồ.

### 4. Ma trận đối xứng xác định dương và xấp xỉ bình phương tối thiểu (28.3 Symmetric positive-definite matrices and least-squares approximation, trang 832–840)

Ma trận đối xứng xác định dương có nhiều tính chất thú vị và đáng mong muốn. Chẳng hạn chúng không suy biến, và có thể phân rã LU chúng mà không phải lo chia cho 0. Mục này chứng minh vài tính chất quan trọng khác và trình bày một ứng dụng thú vị: khớp đường cong bằng xấp xỉ bình phương tối thiểu.

(Nhắc lại từ Phụ lục D: ma trận A cỡ n × n là **xác định dương** nếu xᵀAx > 0 với mọi n-vectơ x ≠ 0; **đối xứng** nếu A = Aᵀ.)

#### 4.1. Các tính chất

**Bổ đề 28.3.** Mọi ma trận xác định dương đều không suy biến.

*Chứng minh.* Giả sử A suy biến. Theo Hệ quả D.3, tồn tại vectơ x ≠ 0 với Ax = 0. Do đó xᵀAx = 0, và A không thể xác định dương. ∎

Chứng minh rằng phân rã LU chạy được trên ma trận đối xứng xác định dương mà không chia cho 0 phức tạp hơn. Ta bắt đầu bằng các tính chất của một số ma trận con. Định nghĩa **ma trận con chính đầu thứ k** (kth leading submatrix) của A là ma trận Aₖ gồm phần giao của k hàng đầu và k cột đầu của A.

**Bổ đề 28.4.** Nếu A đối xứng xác định dương thì mọi ma trận con chính đầu của A đều đối xứng xác định dương.

*Chứng minh.* Aₖ đối xứng là hiển nhiên. Để chứng minh Aₖ xác định dương, giả sử ngược lại và dẫn tới mâu thuẫn. Nếu Aₖ không xác định dương thì có k-vectơ xₖ ≠ 0 với xₖᵀAₖxₖ ≤ 0. Cho A cỡ n × n, và

```text
A = ⎛ Aₖ  Bᵀ ⎞                                                       (28.14)
    ⎝ B   C  ⎠
```

với các khối B (cỡ (n − k) × k) và C (cỡ (n − k) × (n − k)). Định nghĩa n-vectơ x = (xₖᵀ 0)ᵀ, trong đó n − k số 0 đứng sau xₖ. Khi đó

```text
xᵀAx = ( xₖᵀ  0 ) ⎛ Aₖ  Bᵀ ⎞ ⎛ xₖ ⎞
                  ⎝ B   C  ⎠ ⎝ 0  ⎠

     = ( xₖᵀ  0 ) ⎛ Aₖxₖ ⎞
                  ⎝ Bxₖ  ⎠

     = xₖᵀAₖxₖ
     ≤ 0 ,
```

mâu thuẫn với A xác định dương (vì x ≠ 0). ∎

Ví dụ (người tổng hợp): A = (4 2 1; 2 3 0; 1 0 2) đối xứng xác định dương; A₂ = (4 2; 2 3) có xᵀA₂x = 4x₁² + 4x₁x₂ + 3x₂² = (2x₁ + x₂)² + 2x₂² > 0 khi x ≠ 0.

**Phần bù Schur tổng quát.** Cho A đối xứng xác định dương và Aₖ là ma trận con chính đầu k × k của A. Lại chia A theo (28.14). Tổng quát hoá (28.9), định nghĩa **phần bù Schur** S của A theo Aₖ là

```text
S = C − BAₖ⁻¹Bᵀ .                                                   (28.15)
```

(Theo Bổ đề 28.4, Aₖ đối xứng xác định dương; vì vậy Aₖ⁻¹ tồn tại theo Bổ đề 28.3, và S được định nghĩa tốt.) Định nghĩa (28.9) trước đây khớp với (28.15) khi k = 1: khi đó Aₖ = (a₁₁), B là cột v, Bᵀ là hàng wᵀ (A đối xứng nên w = v), C là A′, và S = A′ − vwᵀ/a₁₁.

Bổ đề tiếp theo cho thấy phần bù Schur của ma trận đối xứng xác định dương cũng đối xứng xác định dương. Kết quả này đã được dùng trong Định lý 28.2, và hệ quả của nó cần để chứng minh tính đúng của phân rã LU cho ma trận đối xứng xác định dương.

**Bổ đề 28.5 (Bổ đề phần bù Schur — Schur complement lemma).** Nếu A đối xứng xác định dương và Aₖ là ma trận con chính đầu k × k của A, thì phần bù Schur S của A theo Aₖ đối xứng xác định dương.

*Chứng minh.* Vì A đối xứng, khối C cũng đối xứng. Theo Exercise D.2-6, tích BAₖ⁻¹Bᵀ đối xứng, và theo Exercise D.1-1 (hiệu hai ma trận đối xứng là đối xứng), S đối xứng.

Còn phải chứng minh S xác định dương. Xét cách chia A ở (28.14). Với mọi vectơ x ≠ 0, xᵀAx > 0 vì A xác định dương. Tách x thành hai vectơ con y và z tương thích lần lượt với Aₖ và C. Vì Aₖ⁻¹ tồn tại,

```text
xᵀAx = ( yᵀ  zᵀ ) ⎛ Aₖ  Bᵀ ⎞ ⎛ y ⎞
                  ⎝ B   C  ⎠ ⎝ z ⎠

     = ( yᵀ  zᵀ ) ⎛ Aₖy + Bᵀz ⎞
                  ⎝ By + Cz   ⎠

     = yᵀAₖy + yᵀBᵀz + zᵀBy + zᵀCz

     = (y + Aₖ⁻¹Bᵀz)ᵀ Aₖ (y + Aₖ⁻¹Bᵀz) + zᵀ(C − BAₖ⁻¹Bᵀ)z ,          (28.16)
```

nhờ "phép màu ma trận" (kiểm tra bằng cách nhân ra). Đẳng thức cuối chính là "hoàn thành bình phương" của dạng toàn phương (xem Exercise 28.3-2).

*Kiểm tra của người tổng hợp:* khai triển số hạng đầu: (y + Aₖ⁻¹Bᵀz)ᵀAₖ(y + Aₖ⁻¹Bᵀz) = yᵀAₖy + yᵀBᵀz + zᵀBAₖ⁻¹Aₖy + zᵀBAₖ⁻¹AₖAₖ⁻¹Bᵀz = yᵀAₖy + yᵀBᵀz + zᵀBy + zᵀBAₖ⁻¹Bᵀz (dùng (Aₖ⁻¹)ᵀ = Aₖ⁻¹). Cộng với zᵀCz − zᵀBAₖ⁻¹Bᵀz được đúng dòng thứ ba.

Vì xᵀAx > 0 với mọi x ≠ 0, chọn z ≠ 0 bất kỳ rồi chọn y = −Aₖ⁻¹Bᵀz; khi đó số hạng đầu của (28.16) bằng 0, biểu thức còn lại là

```text
zᵀ(C − BAₖ⁻¹Bᵀ)z = zᵀSz .
```

Với mọi z ≠ 0 ta có zᵀSz = xᵀAx > 0 (x = (y, z) ≠ 0 vì z ≠ 0), nên S xác định dương. ∎

Ví dụ (người tổng hợp): A = (4 2 1; 2 3 0; 1 0 2), k = 1: S = (3 0; 0 2) − (2; 1)(2 1)/4 = (3 − 1, 0 − 0,5; 0 − 0,5, 2 − 0,25) = (2 −0,5; −0,5 1,75). S đối xứng, trụ đầu 2 > 0, và phần bù Schur tiếp theo 1,75 − 0,25/2 = 1,625 > 0, nên S xác định dương.

**Hệ quả 28.6.** Phân rã LU của ma trận đối xứng xác định dương không bao giờ gây phép chia cho 0.

*Chứng minh.* Cho A đối xứng xác định dương. Ta chứng minh điều mạnh hơn: mọi trụ đều **dương** thực sự. Trụ đầu là a₁₁. Gọi e₁ là vectơ đơn vị thứ nhất; a₁₁ = e₁ᵀAe₁ > 0. Vì bước đầu của phân rã LU tạo ra phần bù Schur của A theo A₁ = (a₁₁), Bổ đề 28.5 cho biết (bằng quy nạp) mọi trụ đều dương. ∎

Ví dụ: với A = (4 2 1; 2 3 0; 1 0 2), các trụ của phân rã LU là 4, 2, 1,625 — đều dương; tích của chúng 4·2·1,625 = 13 = det A (kiểm tra: det A = 4(6 − 0) − 2(4 − 0) + 1(0 − 3) = 24 − 8 − 3 = 13).

#### 4.2. Xấp xỉ bình phương tối thiểu (Least-squares approximation)

Một ứng dụng quan trọng của ma trận đối xứng xác định dương là khớp đường cong với một tập điểm dữ liệu. Giả sử cho m điểm dữ liệu

```text
(x₁, y₁), (x₂, y₂), …, (xₘ, yₘ) ,
```

trong đó các yᵢ có sai số đo. Ta muốn tìm hàm F(x) sao cho các **sai số xấp xỉ**

```text
ηᵢ = F(xᵢ) − yᵢ                                                     (28.17)
```

nhỏ với i = 1, 2, …, m. Dạng của F tuỳ bài toán. Ở đây giả định F là tổng có trọng số tuyến tính

```text
F(x) = Σⱼ₌₁ⁿ cⱼ fⱼ(x) ,
```

trong đó số số hạng n và các **hàm cơ sở** (basis functions) fⱼ được chọn dựa trên hiểu biết về bài toán. Lựa chọn hay gặp là fⱼ(x) = x^(j−1), nghĩa là

```text
F(x) = c₁ + c₂x + c₃x² + … + cₙx^(n−1)
```

là đa thức bậc n − 1 theo x. Vậy, cho m điểm dữ liệu, ta muốn tính n hệ số c₁, …, cₙ làm các sai số η₁, …, ηₘ nhỏ nhất.

Chọn n = m thì tính được mỗi yᵢ **chính xác** trong (28.17). Nhưng F bậc cao như vậy "khớp cả nhiễu" lẫn dữ liệu, và thường cho kết quả kém khi dùng để dự đoán y tại các giá trị x chưa thấy. Thường tốt hơn là chọn n nhỏ hơn hẳn m và hy vọng rằng, chọn hệ số cⱼ khéo, ta được hàm F nắm được các quy luật đáng kể trong dữ liệu mà không chú ý quá mức tới nhiễu. Có vài nguyên lý lý thuyết để chọn n nhưng nằm ngoài phạm vi sách. Dù sao, khi đã chọn n < m, ta có một hệ thừa phương trình cần tìm nghiệm xấp xỉ. Cách làm như sau.

Gọi

```text
    ⎛ f₁(x₁)  f₂(x₁)  …  fₙ(x₁) ⎞
A = ⎜ f₁(x₂)  f₂(x₂)  …  fₙ(x₂) ⎟
    ⎜   ⋮       ⋮     ⋱    ⋮    ⎟
    ⎝ f₁(xₘ)  f₂(xₘ)  …  fₙ(xₘ) ⎠
```

là ma trận giá trị của các hàm cơ sở tại các điểm đã cho, tức aᵢⱼ = fⱼ(xᵢ). Gọi c = (cₖ) là n-vectơ hệ số cần tìm. Khi đó

```text
Ac = ( F(x₁), F(x₂), …, F(xₘ) )ᵀ
```

là m-vectơ "giá trị dự đoán" cho y. Do đó

```text
η = Ac − y
```

là m-vectơ **sai số xấp xỉ** (approximation errors).

Để làm sai số xấp xỉ nhỏ nhất, ta chọn cực tiểu chuẩn của vectơ sai số η, cho ta một **nghiệm bình phương tối thiểu** (least-squares solution), vì

```text
‖η‖ = ( Σᵢ₌₁ᵐ ηᵢ² )^(1/2) .
```

Vì

```text
‖η‖² = ‖Ac − y‖² = Σᵢ₌₁ᵐ ( Σⱼ₌₁ⁿ aᵢⱼcⱼ − yᵢ )² ,
```

ta cực tiểu ‖η‖ bằng cách lấy đạo hàm ‖η‖² theo từng cₖ và cho bằng 0:

```text
d‖η‖²/dcₖ = Σᵢ₌₁ᵐ 2 ( Σⱼ₌₁ⁿ aᵢⱼcⱼ − yᵢ ) aᵢₖ = 0 .                      (28.18)
```

n phương trình (28.18) với k = 1, 2, …, n tương đương với một phương trình ma trận

```text
(Ac − y)ᵀA = 0
```

hay, tương đương (dùng Exercise D.1-2),

```text
Aᵀ(Ac − y) = 0 ,
```

suy ra

```text
AᵀAc = Aᵀy .                                                        (28.19)
```

Trong thống kê, đây gọi là **phương trình chuẩn** (normal equation). Ma trận AᵀA đối xứng theo Exercise D.1-2, và nếu A có hạng cột đầy đủ thì theo Định lý D.6, AᵀA cũng xác định dương. Do đó (AᵀA)⁻¹ tồn tại và nghiệm của (28.19) là

```text
c = ( (AᵀA)⁻¹Aᵀ ) y
  = A⁺y ,                                                           (28.20)
```

trong đó ma trận A⁺ = ((AᵀA)⁻¹Aᵀ) là **giả nghịch đảo** (pseudoinverse) của A. Giả nghịch đảo tổng quát hoá tự nhiên khái niệm nghịch đảo cho trường hợp A không vuông. (So sánh (28.20) — nghiệm xấp xỉ của Ac = y — với A⁻¹b — nghiệm chính xác của Ax = b.)

(Ghi chú của người tổng hợp về điểm dừng là cực tiểu: ‖Ac − y‖² là hàm bậc hai theo c với ma trận Hessian 2AᵀA xác định dương, nên lồi chặt và điểm có đạo hàm bằng 0 là cực tiểu toàn cục duy nhất. Sách không nói rõ bước này.)

**Ví dụ của sách: khớp parabol qua năm điểm.** Cho năm điểm dữ liệu

```text
(x₁, y₁) = (−1, 2) ,
(x₂, y₂) = (1, 1) ,
(x₃, y₃) = (2, 1) ,
(x₄, y₄) = (3, 0) ,
(x₅, y₅) = (5, 3) .
```

Muốn khớp bằng đa thức bậc hai F(x) = c₁ + c₂x + c₃x². Ma trận giá trị hàm cơ sở là

```text
    ⎛ 1  x₁  x₁² ⎞   ⎛ 1  −1   1 ⎞
    ⎜ 1  x₂  x₂² ⎟   ⎜ 1   1   1 ⎟
A = ⎜ 1  x₃  x₃² ⎟ = ⎜ 1   2   4 ⎟ ,
    ⎜ 1  x₄  x₄² ⎟   ⎜ 1   3   9 ⎟
    ⎝ 1  x₅  x₅² ⎠   ⎝ 1   5  25 ⎠
```

có giả nghịch đảo

```text
     ⎛  0,500   0,300   0,200   0,100  −0,100 ⎞
A⁺ = ⎜ −0,388   0,093   0,190   0,193  −0,088 ⎟ .
     ⎝  0,060  −0,036  −0,048  −0,036   0,060 ⎠
```

Nhân y với A⁺ được vectơ hệ số

```text
    ⎛  1,200 ⎞
c = ⎜ −0,757 ⎟ ,
    ⎝  0,214 ⎠
```

ứng với đa thức bậc hai

```text
F(x) = 1,200 − 0,757x + 0,214x²
```

là parabol khớp gần nhất với dữ liệu theo nghĩa bình phương tối thiểu.

*Tính lại từng bước (người tổng hợp):*

```text
AᵀA = ⎛ Σ1    Σx    Σx²  ⎞   ⎛  5    10    40 ⎞
      ⎜ Σx    Σx²   Σx³  ⎟ = ⎜ 10    40   160 ⎟
      ⎝ Σx²   Σx³   Σx⁴  ⎠   ⎝ 40   160   724 ⎠
   Σx  = −1 + 1 + 2 + 3 + 5 = 10
   Σx² =  1 + 1 + 4 + 9 + 25 = 40
   Σx³ = −1 + 1 + 8 + 27 + 125 = 160
   Σx⁴ =  1 + 1 + 16 + 81 + 625 = 724

Aᵀy = ( Σy, Σxy, Σx²y ) = ( 7, 16, 82 )
   Σy   = 2 + 1 + 1 + 0 + 3 = 7
   Σxy  = −2 + 1 + 2 + 0 + 15 = 16
   Σx²y = 2 + 1 + 4 + 0 + 75 = 82

Giải AᵀAc = Aᵀy (chính xác bằng phân số):
   c = ( 6/5, −53/70, 3/14 ) ≈ ( 1,2000; −0,7571; 0,2143 )

Giả nghịch đảo chính xác:
   hàng 1: ( 1/2, 3/10, 1/5, 1/10, −1/10 )
   hàng 2: ( −163/420, 13/140, 4/21, 27/140, −37/420 )
         ≈ ( −0,3881; 0,0929; 0,1905; 0,1929; −0,0881 )
   hàng 3: ( 5/84, −1/28, −1/21, −1/28, 5/84 )
         ≈ ( 0,0595; −0,0357; −0,0476; −0,0357; 0,0595 )
```

Mọi số của sách là các giá trị này làm tròn tới 3 chữ số thập phân — đúng.

**Hình 28.3 của sách, mô tả lại bằng bảng.** Hình vẽ năm điểm dữ liệu (chấm đen), parabol F(x) = 1,2 − 0,757x + 0,214x² (đường cong, trục x từ −2 tới 5, trục y từ 0 tới 3), các giá trị dự đoán F(xᵢ) (chấm trắng nằm trên đường cong), và đoạn thẳng xám nối mỗi chấm đen với chấm trắng tương ứng, biểu diễn sai số. Parabol đạt cực tiểu ≈ 0,53 tại x ≈ 1,77. Giá trị cụ thể (người tổng hợp tính):

| xᵢ | yᵢ (chấm đen) | F(xᵢ) (chấm trắng) | sai số ηᵢ = F(xᵢ) − yᵢ |
|---|---|---|---|
| −1 | 2 | 2,171 | +0,171 |
| 1 | 1 | 0,657 | −0,343 |
| 2 | 1 | 0,543 | −0,457 |
| 3 | 0 | 0,857 | +0,857 (sai số lớn nhất) |
| 5 | 3 | 2,771 | −0,229 |

Tổng bình phương sai số ‖η‖² = 8/7 ≈ 1,143. Một nhận xét kiểm tra: tổng các sai số bằng 0 (0,171 − 0,343 − 0,457 + 0,857 − 0,229 = 0) — đúng như phương trình chuẩn đòi hỏi ở hàng đầu (hàm cơ sở f₁ = 1).

**Trong thực hành**, ta giải phương trình chuẩn (28.19) bằng cách nhân y với Aᵀ rồi tìm phân rã LU của AᵀA. Nếu A có hạng đầy đủ, AᵀA chắc chắn không suy biến vì nó đối xứng xác định dương (Exercise D.1-2 và Định lý D.6); và theo Hệ quả 28.6, phân rã LU không cần chọn trụ.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hồi quy tuyến tính trong thống kê và học máy (`numpy.linalg.lstsq`, `sklearn.linear_model.LinearRegression`, hàm `lm` của R) chính là bài toán bình phương tối thiểu của mục này, với các cột của A là các đặc trưng. Thực tế các thư viện ít khi giải phương trình chuẩn trực tiếp mà dùng phân rã QR hoặc SVD để tránh mất độ chính xác; còn khi hệ đối xứng xác định dương thật sự (ma trận hiệp phương sai, ma trận độ cứng trong phần tử hữu hạn) thì dùng phân rã Cholesky A = LLᵀ — "phân rã LU đối xứng" chạy được chính nhờ Hệ quả 28.6, tốn khoảng một nửa số phép tính của LU.

## Bài tập và bài toán cuối chương

### Bài tập Mục 28.1 (trang 825–827)

- **28.1-1:** Giải bằng phép thế tiến hệ

  ```text
  ⎛  1  0  0 ⎞ ⎛ x₁ ⎞   ⎛  3 ⎞
  ⎜  4  1  0 ⎟ ⎜ x₂ ⎟ = ⎜ 14 ⎟
  ⎝ −6  5  1 ⎠ ⎝ x₃ ⎠   ⎝ −7 ⎠
  ```
  *Lời giải của người tổng hợp:* x₁ = 3; x₂ = 14 − 4·3 = 2; x₃ = −7 − (−6·3 + 5·2) = −7 + 18 − 10 = 1. Vậy x = (3, 2, 1)ᵀ.

- **28.1-2:** Tìm phân rã LU của ma trận (4 −5 6; 8 −6 7; 12 −7 12). *Lời giải của người tổng hợp:* bước 1, trụ 4, v/4 = (8, 12)/4 = (2, 3), wᵀ = (−5, 6); phần bù Schur = (−6 7; −7 12) − (2; 3)(−5 6) = (−6 + 10, 7 − 12; −7 + 15, 12 − 18) = (4 −5; 8 −6). Bước 2, trụ 4, hệ số 8/4 = 2, wᵀ = (−5); phần bù Schur −6 − 2·(−5) = 4. Kết quả

  ```text
  ⎛  4  −5   6 ⎞   ⎛ 1 0 0 ⎞ ⎛ 4  −5   6 ⎞
  ⎜  8  −6   7 ⎟ = ⎜ 2 1 0 ⎟ ⎜ 0   4  −5 ⎟
  ⎝ 12  −7  12 ⎠   ⎝ 3 2 1 ⎠ ⎝ 0   0   4 ⎠
  ```
  Kiểm tra hàng 3: 3·(4, −5, 6) + 2·(0, 4, −5) + (0, 0, 4) = (12, −15 + 8, 18 − 10 + 4) = (12, −7, 12). Đúng.

- **28.1-3:** Giải bằng phân rã LUP hệ (1 5 4; 2 0 3; 5 8 2)x = (12, 9, 5)ᵀ. *Lời giải của người tổng hợp:* bước 1: cột 1 có trị tuyệt đối 1, 2, 5 nên trụ là 5 (hàng 3), đổi hàng 1 ↔ 3, π = (3, 2, 1); hệ số 2/5 = 0,4 (hàng gốc 2) và 1/5 = 0,2 (hàng gốc 1); phần bù Schur: hàng gốc 2: (0 − 0,4·8, 3 − 0,4·2) = (−3,2; 2,2); hàng gốc 1: (5 − 0,2·8, 4 − 0,2·2) = (3,4; 3,6). Bước 2: trị tuyệt đối 3,2 và 3,4 nên trụ là 3,4 (hàng gốc 1), đổi, π = (3, 1, 2); hệ số −3,2/3,4 = −16/17; phần bù Schur 2,2 − (−16/17)·3,6 = 2,2 + 57,6/17 = 95/17. Vậy

  ```text
  P: π = (3, 1, 2)
      ⎛ 1      0       0 ⎞        ⎛ 5   8      2     ⎞
  L = ⎜ 1/5    1       0 ⎟ ,  U = ⎜ 0   17/5   18/5  ⎟
      ⎝ 2/5   −16/17   1 ⎠        ⎝ 0   0      95/17 ⎠
  ```
  Pb = (5, 12, 9). Thế tiến: y₁ = 5; y₂ = 12 − 5/5 = 11; y₃ = 9 − 2 + (16/17)·11 = 7 + 176/17 = 295/17. Thế lùi: x₃ = (295/17)/(95/17) = 59/19; x₂ = (11 − (18/5)(59/19))/(17/5) = ((1045 − 1062)/95)·(5/17) = −1/19; x₁ = (5 − 8·(−1/19) − 2·(59/19))/5 = ((95 + 8 − 118)/19)/5 = −3/19. Nghiệm x = (−3/19, −1/19, 59/19)ᵀ ≈ (−0,158; −0,053; 3,105). Kiểm tra phương trình 1: (−3 − 5 + 236)/19 = 228/19 = 12. Đúng.

- **28.1-4:** Mô tả phân rã LUP của một ma trận đường chéo. *Người tổng hợp:* nếu ma trận đường chéo D không suy biến (mọi dᵢᵢ ≠ 0) thì P = I, L = I, U = D: ở mỗi bước, cột hiện tại chỉ có phần tử đường chéo khác 0 nên LUP-DECOMPOSITION không đổi hàng, mọi hệ số nhân bằng 0 và phần bù Schur chính là phần đường chéo còn lại. Nếu có dᵢᵢ = 0 thì ma trận suy biến và thủ tục báo lỗi ở bước i.

- **28.1-5:** Mô tả phân rã LUP của một ma trận hoán vị A, và chứng minh nó duy nhất. *Người tổng hợp:* P = A⁻¹ = Aᵀ, L = U = I (vì PA = AᵀA = I = I·I). Duy nhất: giả sử PA = LU với P hoán vị, L tam giác dưới đơn vị, U tam giác trên. Q = PA là ma trận hoán vị, và det Q = det L · det U = u₁₁⋯uₙₙ ≠ 0. Hơn nữa, ma trận con chính đầu Qₖ = LₖUₖ (vì L, U tam giác), nên det Qₖ = u₁₁⋯uₖₖ ≠ 0 với mọi k. Một ma trận hoán vị có mọi ma trận con chính đầu đều khả nghịch phải là I (quy nạp: Q₁ ≠ 0 nên q₁₁ = 1; nếu Qₖ₋₁ = Iₖ₋₁ thì các hàng và cột 1..k − 1 đã "dùng hết" số 1, nên hàng k của Qₖ chỉ còn khả năng có số 1 ở cột k, mà det Qₖ ≠ 0 buộc qₖₖ = 1). Vậy Q = I, tức P = A⁻¹; khi đó LU = I nên L = U⁻¹ vừa tam giác dưới vừa tam giác trên, là ma trận đường chéo, mà đường chéo của L toàn 1, nên L = U = I.

- **28.1-6:** Chứng minh với mọi n ≥ 1 tồn tại ma trận n × n suy biến có phân rã LU. *Người tổng hợp:* ma trận 0 (cỡ n × n) = I · 0 (L = I, U = 0). Ví dụ ít tầm thường hơn: (1 1; 1 1) = (1 0; 1 1)(1 1; 0 0). Điều này cho thấy "có phân rã LU" không kéo theo "không suy biến" — trụ cuối có thể bằng 0 mà không cần chia cho nó.

- **28.1-7:** Trong LU-DECOMPOSITION, có cần thực hiện vòng for ngoài cùng khi k = n không? Còn trong LUP-DECOMPOSITION? *Người tổng hợp:* trong LU-DECOMPOSITION thì **cần**, vì dòng 6 của vòng đó gán u_nn = a_nn (các vòng trong không chạy); bỏ đi thì u_nn vẫn là giá trị khởi tạo chưa xác định. (Với bản tại chỗ thì không cần, vì a_nn đã nằm sẵn đúng chỗ.) Trong LUP-DECOMPOSITION thì **không cần** cho kết quả: với k = n, dòng 7–10 chỉ xét một phần tử, đổi hàng n với chính nó, các vòng dòng 16–19 không chạy; u_nn đã nằm tại chỗ ở a_nn. Lợi ích duy nhất của lần lặp cuối là kiểm tra a_nn = 0 để báo "singular matrix".

### Bài tập Mục 28.2 (trang 831–832)

- **28.2-1:** Gọi M(n) là thời gian nhân hai ma trận n × n và S(n) là thời gian bình phương một ma trận n × n. Chứng minh nhân và bình phương khó ngang nhau: thuật toán nhân M(n) cho thuật toán bình phương O(M(n)), và thuật toán bình phương S(n) cho thuật toán nhân O(S(n)). *Người tổng hợp:* chiều thứ nhất hiển nhiên (A² = A·A). Chiều thứ hai: bình phương ma trận 2n × 2n

  ```text
  ⎛ 0  A ⎞²   ⎛ AB  0  ⎞
  ⎝ B  0 ⎠  = ⎝ 0   BA ⎠
  ```
  rồi lấy khối trên trái; thời gian S(2n) + O(n²) = O(S(n)) với điều kiện chính quy S(2n) = O(S(n)) và S(n) = Ω(n²).

- **28.2-2:** Gọi L(n) là thời gian tính phân rã LUP của ma trận n × n. Chứng minh thuật toán nhân M(n) cho thuật toán phân rã LUP O(M(n)), và thuật toán phân rã LUP L(n) cho thuật toán nhân O(L(n)). *Hướng giải của người tổng hợp (chưa chắc về mọi chi tiết):* chiều từ nhân sang phân rã (M sang L): phân rã LUP đệ quy theo khối (thuật toán của Bunch và Hopcroft, theo hiểu biết của người tổng hợp): chia ma trận thành nửa trên và nửa dưới, phân rã nửa trên (ma trận chữ nhật n/2 × n) đệ quy, dùng nghịch đảo của khối tam giác (tính bằng chia để trị trong O(M(n)) như Định lý 28.2, vì nghịch đảo ma trận tam giác khối chỉ cần hai nghịch đảo nửa cỡ và hai phép nhân) để tính phần bù Schur của nửa dưới, rồi phân rã đệ quy phần đó; truy hồi dạng T(n) ≤ 2T(n/2) + O(M(n)) = O(M(n)). Chiều từ phân rã sang nhân (L sang M, với thuật toán chọn trụ trị tuyệt đối lớn nhất như LUP-DECOMPOSITION): chọn hằng số c lớn hơn mọi |aᵢⱼ| và mọi |(AB)ᵢⱼ| (chẳng hạn c = 1 + max|aᵢⱼ| + n·max|aᵢⱼ|·max|bᵢⱼ|, tính trong O(n²)), rồi phân rã ma trận 3n × 3n

  ```text
      ⎛ cIₙ   B    0  ⎞
  K = ⎜ −A    0    Iₙ ⎟
      ⎝ 0     Iₙ   0  ⎠
  ```
  Ở n cột đầu, trụ luôn là các số c (lớn hơn mọi |aᵢⱼ|), không đổi hàng; phần bù Schur của khối hàng 2–3, cột 2–3 là (AB/c  Iₙ; Iₙ  0). Ở n cột tiếp theo, các phần tử của AB/c đều có trị tuyệt đối < 1, nên trụ là các số 1 của khối Iₙ ở khối hàng 3: thủ tục đổi khối hàng 3 lên trên, hệ số nhân ghi vào L chính là các phần tử của AB/c, và phần bù Schur cuối cùng là Iₙ (không đổi hàng thêm). Vậy AB = c × (khối tương ứng của L). Thời gian L(3n) + O(n²) = O(L(n)) với điều kiện chính quy. *Điểm chưa chắc của người tổng hợp:* lập luận này dựa vào quy tắc chọn trụ cụ thể; với một thuật toán LUP tuỳ ý (được phép chọn bất kỳ trụ khác 0), cần thêm lập luận để đọc được AB từ phân rã nó trả về.

- **28.2-3:** Gọi D(n) là thời gian tính định thức ma trận n × n. Chứng minh nhân ma trận và tính định thức khó ngang nhau. *Người tổng hợp:* chiều từ nhân sang định thức: tính phân rã LUP trong O(M(n)) (bài 28.2-2), rồi det A = (det P)⁻¹ · u₁₁⋯uₙₙ, với det P = ±1 là dấu của hoán vị π (tính trong O(n) bằng đếm chu trình). Chiều từ định thức sang nhân khó hơn hẳn và theo hiểu biết của người tổng hợp dùng định lý Baur–Strassen (đạo hàm riêng của một chương trình tính định thức cho ra mọi phần tử của ma trận phụ hợp, tức của det(A)·A⁻¹, với chi phí chỉ gấp hằng số lần), rồi áp dụng Định lý 28.1. Đây là kiến thức ngoài sách.

- **28.2-4:** Gọi M(n) là thời gian nhân hai ma trận bun (boolean) n × n và T(n) là thời gian tìm bao đóng bắc cầu của ma trận bun n × n (Mục 25.2). Chứng minh thuật toán nhân bun M(n) cho thuật toán bao đóng bắc cầu O(M(n) lg n), và thuật toán bao đóng T(n) cho thuật toán nhân bun O(T(n)). *Người tổng hợp:* chiều thứ nhất: bao đóng (phản xạ) là (I ∨ A)^(n−1); tính bằng bình phương liên tiếp ⌈lg(n − 1)⌉ lần, mỗi lần một phép nhân bun: O(M(n) lg n). Chiều thứ hai: dựng đồ thị 3n đỉnh ba tầng với ma trận kề (0 A 0; 0 0 B; 0 0 0); đường đi từ tầng 1 sang tầng 3 phải qua đúng một đỉnh tầng 2, nên khối trên phải của bao đóng bắc cầu là tích bun AB. Thời gian T(3n) + O(n²) = O(T(n)) với điều kiện chính quy.

- **28.2-5:** Thuật toán nghịch đảo dựa trên Định lý 28.2 có chạy được khi phần tử ma trận lấy từ trường số nguyên modulo 2 không? Giải thích. *Người tổng hợp:* không. Thuật toán dựa vào tính xác định dương, khái niệm không có nghĩa trên trường hữu hạn (không có thứ tự "> 0"), và bước quy về AᵀA có thể thất bại. Ví dụ: A = (1 1; 1 0) khả nghịch trên GF(2), nhưng AᵀA = (1+1 1; 1 1) = (0 1; 1 1) mod 2 có khối trên trái B = 0 không khả nghịch, nên bước 2 (tính B⁻¹) hỏng ngay.

- **28.2-6 (★):** Tổng quát hoá thuật toán nghịch đảo của Định lý 28.2 cho ma trận số phức, và chứng minh tổng quát hoá đó đúng. (Gợi ý của sách: thay chuyển vị Aᵀ bằng **chuyển vị liên hợp** A* — lấy chuyển vị rồi thay mỗi phần tử bằng số phức liên hợp của nó; thay ma trận đối xứng bằng **ma trận Hermite**, tức A = A*.) *Người tổng hợp:* định nghĩa xác định dương là x*Ax > 0 với mọi x ≠ 0 (số này luôn thực khi A Hermite). Các Bổ đề 28.3–28.5 chứng minh y hệt với * thay cho ᵀ; khối A = (B C*; C D), S = D − CB⁻¹C*, công thức (28.13) với * thay cho ᵀ; bảy bước giữ nguyên, dùng (B⁻¹)* = B⁻¹. Với A bất kỳ không suy biến: A*A Hermite xác định dương (x*A*Ax = ‖Ax‖² > 0), và A⁻¹ = (A*A)⁻¹A*.

### Bài tập Mục 28.3 (trang 839–840)

- **28.3-1:** Chứng minh mọi phần tử đường chéo của ma trận đối xứng xác định dương đều dương. *Người tổng hợp:* aᵢᵢ = eᵢᵀAeᵢ > 0.
- **28.3-2:** Cho A = (a b; b c) đối xứng xác định dương 2 × 2. Chứng minh định thức ac − b² dương bằng cách "hoàn thành bình phương" như trong chứng minh Bổ đề 28.5. *Người tổng hợp:* a > 0 (bài 28.3-1). Với x = (x₁, x₂): xᵀAx = ax₁² + 2bx₁x₂ + cx₂² = a(x₁ + (b/a)x₂)² + ((ac − b²)/a)x₂². Chọn x₂ = 1, x₁ = −b/a: xᵀAx = (ac − b²)/a > 0, nên ac − b² > 0.
- **28.3-3:** Chứng minh phần tử lớn nhất của ma trận đối xứng xác định dương nằm trên đường chéo. *Người tổng hợp:* với i ≠ j, lấy x = eᵢ − eⱼ: aᵢᵢ + aⱼⱼ − 2aᵢⱼ > 0, nên aᵢⱼ < (aᵢᵢ + aⱼⱼ)/2 ≤ max(aᵢᵢ, aⱼⱼ). Lấy x = eᵢ + eⱼ còn được −aᵢⱼ < (aᵢᵢ + aⱼⱼ)/2, nên kể cả theo trị tuyệt đối, phần tử lớn nhất nằm trên đường chéo.
- **28.3-4:** Chứng minh định thức của mọi ma trận con chính đầu của ma trận đối xứng xác định dương đều dương. *Người tổng hợp:* Aₖ đối xứng xác định dương (Bổ đề 28.4) nên có phân rã LU với mọi trụ dương (Hệ quả 28.6); det Aₖ = det L · det U = tích các trụ > 0.
- **28.3-5:** Gọi Aₖ là ma trận con chính đầu thứ k của A đối xứng xác định dương. Chứng minh det(Aₖ)/det(Aₖ₋₁) là trụ thứ k của phân rã LU, với quy ước det(A₀) = 1. *Người tổng hợp:* vì L, U tam giác, A = LU kéo theo Aₖ = LₖUₖ (khối đầu k × k), nên det Aₖ = u₁₁u₂₂⋯uₖₖ; chia hai định thức liên tiếp được uₖₖ. Ví dụ A = (4 2 1; 2 3 0; 1 0 2): det A₁ = 4, det A₂ = 8, det A₃ = 13; các trụ 4, 8/4 = 2, 13/8 = 1,625 — khớp với ví dụ ở mục 4.1.
- **28.3-6:** Tìm hàm dạng F(x) = c₁ + c₂ x lg x + c₃eˣ khớp tốt nhất theo bình phương tối thiểu với các điểm (1, 1), (2, 1), (3, 3), (4, 8). *Lời giải của người tổng hợp (lg là log cơ số 2):* ma trận A có các hàng (1, 0, e), (1, 2, e²), (1, 3 lg 3, e³), (1, 8, e⁴) ≈ (1; 0; 2,718), (1; 2; 7,389), (1; 4,755; 20,086), (1; 8; 54,598). Giải phương trình chuẩn AᵀAc = Aᵀy được c ≈ (0,412; −0,205; 0,170), tức F(x) ≈ 0,412 − 0,205 x lg x + 0,170 eˣ. Giá trị dự đoán tại x = 1, 2, 3, 4 lần lượt ≈ 0,873; 1,255; 2,843; 8,030.
- **28.3-7:** Chứng minh giả nghịch đảo A⁺ thoả bốn đẳng thức: AA⁺A = A; A⁺AA⁺ = A⁺; (AA⁺)ᵀ = AA⁺; (A⁺A)ᵀ = A⁺A. *Người tổng hợp:* với A⁺ = (AᵀA)⁻¹Aᵀ (A hạng cột đầy đủ): A⁺A = (AᵀA)⁻¹AᵀA = Iₙ, nên đẳng thức 1: AA⁺A = A·Iₙ = A; đẳng thức 2: A⁺AA⁺ = Iₙ A⁺ = A⁺; đẳng thức 4: (A⁺A)ᵀ = Iₙ = A⁺A; đẳng thức 3: AA⁺ = A(AᵀA)⁻¹Aᵀ, chuyển vị bằng A((AᵀA)⁻¹)ᵀAᵀ = A(AᵀA)⁻¹Aᵀ vì AᵀA đối xứng nên nghịch đảo của nó đối xứng. (Bốn đẳng thức này là định nghĩa giả nghịch đảo Moore–Penrose — theo hiểu biết của người tổng hợp.)

### Problem 28-1: Hệ phương trình tuyến tính ba đường chéo (Tridiagonal systems of linear equations)

Xét ma trận ba đường chéo

```text
    ⎛  1  −1   0   0   0 ⎞
    ⎜ −1   2  −1   0   0 ⎟
A = ⎜  0  −1   2  −1   0 ⎟ .
    ⎜  0   0  −1   2  −1 ⎟
    ⎝  0   0   0  −1   2 ⎠
```

- **(a)** Tìm phân rã LU của A. *Lời giải của người tổng hợp:* mọi trụ bằng 1. Bước 1: trụ 1, hệ số −1, phần bù Schur làm a₂₂ thành 2 − 1 = 1; các bước sau giống hệt. Kết quả L có đường chéo 1 và đường dưới chéo toàn −1; U có đường chéo 1 và đường trên chéo toàn −1:

  ```text
      ⎛  1  0  0  0  0 ⎞        ⎛ 1 −1  0  0  0 ⎞
      ⎜ −1  1  0  0  0 ⎟        ⎜ 0  1 −1  0  0 ⎟
  L = ⎜  0 −1  1  0  0 ⎟ ,  U = ⎜ 0  0  1 −1  0 ⎟ = Lᵀ
      ⎜  0  0 −1  1  0 ⎟        ⎜ 0  0  0  1 −1 ⎟
      ⎝  0  0  0 −1  1 ⎠        ⎝ 0  0  0  0  1 ⎠
  ```
  (A = LLᵀ nên A đối xứng xác định dương.)
- **(b)** Giải Ax = (1 1 1 1 1)ᵀ bằng phép thế tiến và lùi. *Người tổng hợp:* Ly = (1, 1, 1, 1, 1): y₁ = 1, yᵢ = 1 + yᵢ₋₁ nên y = (1, 2, 3, 4, 5). Ux = y: x₅ = 5, xᵢ = yᵢ + xᵢ₊₁ nên x₄ = 9, x₃ = 12, x₂ = 14, x₁ = 15. Vậy x = (15, 14, 12, 9, 5)ᵀ. Kiểm tra hàng 1: 15 − 14 = 1; hàng 3: −14 + 24 − 9 = 1; hàng 5: −9 + 10 = 1.
- **(c)** Tìm nghịch đảo của A. *Người tổng hợp:* (A⁻¹)ᵢⱼ = 6 − max(i, j):

  ```text
        ⎛ 5 4 3 2 1 ⎞
        ⎜ 4 4 3 2 1 ⎟
  A⁻¹ = ⎜ 3 3 3 2 1 ⎟
        ⎜ 2 2 2 2 1 ⎟
        ⎝ 1 1 1 1 1 ⎠
  ```
  (Tổng các hàng là 15, 14, 12, 9, 5 — đúng nghiệm ở (b).) Ma trận nghịch đảo đặc hoàn toàn dù A thưa.
- **(d)** Chỉ ra cách giải Ax = b trong O(n) với A ba đường chéo đối xứng xác định dương n × n bất kỳ, bằng phân rã LU. Lập luận rằng mọi phương pháp dựa trên việc lập A⁻¹ đều đắt hơn về tiệm cận trong trường hợp xấu nhất. *Người tổng hợp:* không cần chọn trụ (Hệ quả 28.6). Ở bước k, v và wᵀ mỗi vectơ chỉ có một phần tử khác 0 (a_k+1,k và a_k,k+1), nên phần bù Schur chỉ thay đổi đúng một phần tử a_k+1,k+1 −= l_k+1,k · u_k,k+1 và vẫn ba đường chéo. Nếu chỉ lưu ba đường chéo và chỉ duyệt phần tử khác 0, mỗi bước O(1), cả phân rã O(n); L chỉ có một đường dưới chéo, U chỉ có một đường trên chéo, nên thế tiến và lùi mỗi cái O(n). Ngược lại, A⁻¹ nói chung có Θ(n²) phần tử khác 0 (như ví dụ ở (c)), nên chỉ việc ghi nó ra hoặc nhân nó với b đã tốn Ω(n²).
- **(e)** Chỉ ra cách giải Ax = b trong O(n) với A ba đường chéo không suy biến bất kỳ, bằng phân rã LUP. *Người tổng hợp:* ở bước k chỉ hai hàng k và k + 1 có phần tử khác 0 trong cột k, nên việc chọn trụ chỉ so sánh hai số và đổi hàng (nếu có) chỉ giữa hai hàng kề nhau. Sau khi đổi, hàng trụ có thể có phần tử khác 0 ở các cột k, k + 1, k + 2, nên U có tối đa hai đường trên chéo; mỗi cột của L có tối đa một phần tử dưới chéo. Mỗi bước vẫn O(1), tổng O(n); thế tiến và lùi O(n).

### Problem 28-2: Đường spline (Splines)

Một cách thực tế để nội suy một tập điểm bằng một đường cong là dùng **spline bậc ba** (cubic splines). Cho tập {(xᵢ, yᵢ) : i = 0, 1, …, n} gồm n + 1 cặp điểm–giá trị với x₀ < x₁ < … < xₙ. Ta muốn khớp một đường cong bậc ba từng khúc (spline) f(x) qua các điểm. Đường cong gồm n đa thức bậc ba fᵢ(x) = aᵢ + bᵢx + cᵢx² + dᵢx³ với i = 0, 1, …, n − 1; khi x nằm trong đoạn xᵢ ≤ x ≤ xᵢ₊₁, giá trị của đường cong là f(x) = fᵢ(x − xᵢ). Các điểm xᵢ nơi các đa thức được "dán" với nhau gọi là **nút** (knots). Để đơn giản, giả định xᵢ = i với i = 0, 1, …, n.

Để f(x) liên tục, đòi hỏi

```text
f(xᵢ)   = fᵢ(0) = yᵢ ,
f(xᵢ₊₁) = fᵢ(1) = yᵢ₊₁
```

với i = 0, 1, …, n − 1. Để f(x) đủ trơn, còn đòi đạo hàm bậc nhất liên tục tại mỗi nút:

```text
f′(xᵢ₊₁) = fᵢ′(1) = fᵢ₊₁′(0)
```

với i = 0, 1, …, n − 2.

- **(a)** Giả sử với i = 0, 1, …, n, ngoài các cặp (xᵢ, yᵢ) ta còn biết đạo hàm bậc nhất Dᵢ = f′(xᵢ) tại mỗi nút. Biểu diễn aᵢ, bᵢ, cᵢ, dᵢ theo yᵢ, yᵢ₊₁, Dᵢ, Dᵢ₊₁ (nhớ xᵢ = i). Tính 4n hệ số nhanh tới đâu? *Lời giải của người tổng hợp:* từ fᵢ(0) = yᵢ, fᵢ′(0) = Dᵢ, fᵢ(1) = yᵢ₊₁, fᵢ′(1) = Dᵢ₊₁:

  ```text
  aᵢ = yᵢ
  bᵢ = Dᵢ
  cᵢ = 3(yᵢ₊₁ − yᵢ) − 2Dᵢ − Dᵢ₊₁
  dᵢ = 2(yᵢ − yᵢ₊₁) + Dᵢ + Dᵢ₊₁
  ```
  (từ aᵢ + bᵢ + cᵢ + dᵢ = yᵢ₊₁ và bᵢ + 2cᵢ + 3dᵢ = Dᵢ₊₁). Mỗi khúc O(1), tổng O(n). Kiểm tra: y = (0, 1), D = (0, 2) (tức f(x) = x²) cho a = 0, b = 0, c = 3 − 0 − 2 = 1, d = −2 + 0 + 2 = 0: f₀(t) = t². Đúng.

Câu hỏi còn lại là chọn đạo hàm bậc nhất tại các nút thế nào. Một cách là đòi đạo hàm bậc hai liên tục tại các nút:

```text
f″(xᵢ₊₁) = fᵢ″(1) = fᵢ₊₁″(0)
```

với i = 0, 1, …, n − 2. Tại nút đầu và nút cuối, giả định f″(x₀) = f₀″(0) = 0 và f″(xₙ) = fₙ₋₁″(1) = 0; các giả định này làm f(x) thành một spline bậc ba **tự nhiên** (natural cubic spline).

- **(b)** Dùng ràng buộc liên tục của đạo hàm bậc hai, chứng minh với i = 1, 2, …, n − 1:

  ```text
  Dᵢ₋₁ + 4Dᵢ + Dᵢ₊₁ = 3(yᵢ₊₁ − yᵢ₋₁) .                                (28.21)
  ```
  *Người tổng hợp:* fᵢ″(0) = 2cᵢ và fᵢ₋₁″(1) = 2cᵢ₋₁ + 6dᵢ₋₁. Điều kiện tại nút i: cᵢ₋₁ + 3dᵢ₋₁ = cᵢ. Thế công thức (a): vế trái = 3(yᵢ − yᵢ₋₁) − 2Dᵢ₋₁ − Dᵢ + 6(yᵢ₋₁ − yᵢ) + 3Dᵢ₋₁ + 3Dᵢ = −3(yᵢ − yᵢ₋₁) + Dᵢ₋₁ + 2Dᵢ; vế phải = 3(yᵢ₊₁ − yᵢ) − 2Dᵢ − Dᵢ₊₁. Chuyển vế: Dᵢ₋₁ + 4Dᵢ + Dᵢ₊₁ = 3(yᵢ₊₁ − yᵢ) + 3(yᵢ − yᵢ₋₁) = 3(yᵢ₊₁ − yᵢ₋₁).
- **(c)** Chứng minh

  ```text
  2D₀ + D₁     = 3(y₁ − y₀) ,                                         (28.22)
  Dₙ₋₁ + 2Dₙ   = 3(yₙ − yₙ₋₁) .                                     (28.23)
  ```
  *Người tổng hợp:* f₀″(0) = 2c₀ = 0 cho 3(y₁ − y₀) − 2D₀ − D₁ = 0. fₙ₋₁″(1) = 2cₙ₋₁ + 6dₙ₋₁ = 0 cho cₙ₋₁ + 3dₙ₋₁ = 0, tức (theo phép tính ở (b)) Dₙ₋₁ + 2Dₙ − 3(yₙ − yₙ₋₁) = 0.
- **(d)** Viết (28.21)–(28.23) thành một phương trình ma trận với vectơ ẩn D = ⟨D₀, D₁, …, Dₙ⟩. Ma trận có những thuộc tính gì? *Người tổng hợp:*

  ```text
  ⎛ 2 1             ⎞ ⎛ D₀   ⎞   ⎛ 3(y₁ − y₀)     ⎞
  ⎜ 1 4 1           ⎟ ⎜ D₁   ⎟   ⎜ 3(y₂ − y₀)     ⎟
  ⎜   1 4 1         ⎟ ⎜ D₂   ⎟   ⎜ 3(y₃ − y₁)     ⎟
  ⎜     ⋱ ⋱ ⋱       ⎟ ⎜ ⋮    ⎟ = ⎜ ⋮              ⎟
  ⎜         1 4 1   ⎟ ⎜ Dₙ₋₁ ⎟   ⎜ 3(yₙ − yₙ₋₂)   ⎟
  ⎝           1 2   ⎠ ⎝ Dₙ   ⎠   ⎝ 3(yₙ − yₙ₋₁)   ⎠
  ```
  Ma trận (n + 1) × (n + 1) ba đường chéo, đối xứng, chéo trội nghiêm ngặt (mỗi phần tử đường chéo lớn hơn tổng trị tuyệt đối các phần tử khác trong hàng: 2 > 1, 4 > 2), do đó xác định dương (theo hiểu biết của người tổng hợp, suy từ định lý đĩa Gershgorin: mọi trị riêng ≥ 1 > 0).
- **(e)** Lập luận rằng spline bậc ba tự nhiên nội suy được n + 1 cặp điểm–giá trị trong O(n) (xem Problem 28-1). *Người tổng hợp:* lập hệ (d) trong O(n), giải bằng phân rã LU ba đường chéo không chọn trụ trong O(n) (Problem 28-1(d)), rồi tính 4n hệ số theo (a) trong O(n).
- **(f)** Chỉ ra cách tìm spline bậc ba tự nhiên nội suy n + 1 điểm (xᵢ, yᵢ) với x₀ < x₁ < … < xₙ khi xᵢ không nhất thiết bằng i. Phương pháp phải giải phương trình ma trận nào, và chạy nhanh tới đâu? *Người tổng hợp:* đặt hᵢ = xᵢ₊₁ − xᵢ, sᵢ = (yᵢ₊₁ − yᵢ)/hᵢ, và viết khúc thứ i theo biến t = x − xᵢ ∈ [0, hᵢ]: aᵢ = yᵢ, bᵢ = Dᵢ, cᵢ = (3sᵢ − 2Dᵢ − Dᵢ₊₁)/hᵢ, dᵢ = (Dᵢ + Dᵢ₊₁ − 2sᵢ)/hᵢ². Điều kiện đạo hàm bậc hai liên tục tại nút i cho

  ```text
  Dᵢ₋₁/hᵢ₋₁ + 2(1/hᵢ₋₁ + 1/hᵢ)Dᵢ + Dᵢ₊₁/hᵢ = 3(sᵢ₋₁/hᵢ₋₁ + sᵢ/hᵢ) ,
  ```
  và hai đầu: 2D₀ + D₁ = 3s₀, Dₙ₋₁ + 2Dₙ = 3sₙ₋₁ (nhân các phương trình đầu mút với 1/h để ma trận đối xứng). Khi mọi hᵢ = 1 thì trở về (28.21)–(28.23). Ma trận vẫn ba đường chéo, đối xứng, chéo trội nghiêm ngặt, nên giải trong O(n).

  *Ví dụ của người tổng hợp* (xᵢ = i, ba điểm (0, 0), (1, 1), (2, 0)): hệ 2D₀ + D₁ = 3, D₀ + 4D₁ + D₂ = 0, D₁ + 2D₂ = −3 cho D = (1,5; 0; −1,5); f₀(t) = 1,5t − 0,5t³, f₁(t) = 1 − 1,5t² + 0,5t³. Kiểm tra: f₀(1) = 1, f₁(1) = 0, f₀″(1) = −3 = f₁″(0), f₀″(0) = 0, f₁″(1) = −3 + 3 = 0.

### Ghi chú chương (Chapter notes, trang 842)

- Nhiều sách hay mô tả tính toán số và tính toán khoa học chi tiết hơn chương này nhiều; đặc biệt dễ đọc: George và Liu; Golub và Van Loan; Press, Teukolsky, Vetterling và Flannery (bộ *Numerical Recipes* — theo hiểu biết của người tổng hợp); Strang.
- Golub và Van Loan bàn về ổn định số học. Họ chỉ ra vì sao det(A) không nhất thiết là chỉ báo tốt cho độ ổn định của ma trận A, và đề nghị dùng ‖A‖∞‖A⁻¹‖∞, trong đó ‖A‖∞ = max₁≤ᵢ≤ₙ Σⱼ₌₁ⁿ |aᵢⱼ| (tổng trị tuyệt đối lớn nhất của một hàng). Họ cũng giải quyết câu hỏi tính giá trị này mà không cần thực sự tính A⁻¹. (Đại lượng này là **số điều kiện** của A theo chuẩn vô cùng — theo hiểu biết của người tổng hợp. Ví dụ A = (1 2 0; 3 4 4; 5 6 3) có ‖A‖∞ = 14, ‖A⁻¹‖∞ = max(2,6; 1,8; 0,8) = 2,6, số điều kiện 36,4.)
- Khử Gauss, nền tảng của phân rã LU và LUP, là phương pháp hệ thống đầu tiên để giải hệ phương trình tuyến tính, và cũng là một trong những thuật toán số sớm nhất. Dù đã được biết từ trước, phát hiện của nó thường được gán cho C. F. Gauss (1777–1855).
- Trong bài báo nổi tiếng của mình, Strassen chỉ ra rằng có thể nghịch đảo ma trận n × n trong O(n^(lg 7)). Winograd là người đầu tiên chứng minh nhân ma trận không khó hơn nghịch đảo ma trận; chiều ngược lại là của Aho, Hopcroft và Ullman.
- Một phân rã ma trận quan trọng khác là **phân rã giá trị kỳ dị** (singular value decomposition, SVD). SVD phân tích ma trận m × n A thành A = Q₁ΣQ₂ᵀ, trong đó Σ là ma trận m × n chỉ có giá trị khác 0 trên đường chéo, Q₁ cỡ m × m có các cột trực chuẩn đôi một, và Q₂ cỡ n × n cũng có các cột trực chuẩn đôi một. Hai vectơ **trực chuẩn** (orthonormal) nếu tích vô hướng của chúng bằng 0 và mỗi vectơ có chuẩn bằng 1. Sách của Strang và của Golub–Van Loan trình bày SVD tốt.
- Strang có phần trình bày xuất sắc về ma trận đối xứng xác định dương và về đại số tuyến tính nói chung.

## Luận điểm cốt lõi

### Mệnh đề

Giải hệ phương trình tuyến tính n ẩn nên làm bằng phân rã LUP (Θ(n³) một lần, rồi Θ(n²) cho mỗi vế phải) chứ không bằng nghịch đảo; chọn trụ có trị tuyệt đối lớn nhất vừa tránh chia cho 0 vừa giữ ổn định số học mà chỉ tốn thêm hằng số lần thời gian. Về lý thuyết, nghịch đảo ma trận và nhân ma trận có cùng độ phức tạp tiệm cận. Ma trận đối xứng xác định dương là lớp ma trận phân rã được không cần chọn trụ, và chúng xuất hiện tự nhiên trong bài toán khớp dữ liệu theo bình phương tối thiểu qua phương trình chuẩn AᵀAc = Aᵀy.

### Giả định

- Các phần tử thuộc một trường, chủ yếu là số thực ℝ; phép cộng, trừ, nhân, chia số thực tốn thời gian hằng số (mô hình RAM); chương bỏ qua sai số làm tròn ngoài vài nhận xét định tính.
- Mục 28.1: hệ vuông n × n và A không suy biến (với LU không chọn trụ: mọi trụ khác 0).
- Định lý 28.1–28.2: các hàm thời gian I(n), M(n) là Ω(n²) và thoả điều kiện chính quy (I(3n) = O(I(n)); M(n + k) = O(M(n)) với 0 ≤ k ≤ n; M(n/2) ≤ cM(n) với c < 1/2); ma trận số thực (số phức để ở Exercise 28.2-6).
- Mục 28.3: dữ liệu (xᵢ, yᵢ) có sai số chỉ ở yᵢ; dạng hàm là tổ hợp tuyến tính của các hàm cơ sở chọn trước; số hàm cơ sở n < m; ma trận A có hạng cột đầy đủ.

### Cơ chế

1. Một bước khử Gauss là phép phân tích khối A = (1 0; v/a₁₁ I)(a₁₁ wᵀ; 0 S) với S là phần bù Schur; lặp lại trên S cho ra L (các hệ số nhân) và U (các hàng trụ).
2. Phần bù Schur của ma trận không suy biến vẫn không suy biến, nên đệ quy luôn đi tiếp được nếu chọn được trụ ≠ 0; chọn trụ lớn nhất trong cột là luôn có (cột không thể toàn 0) và đổi cả hàng, ghi hoán vị vào π.
3. Có PA = LU thì Ax = b tách thành Ly = Pb và Ux = y, giải bằng thế tiến và thế lùi trong Θ(n²); nghịch đảo là n lần giải như vậy.
4. Phép quy giữa nhân và nghịch đảo: AB đọc ra từ nghịch đảo của ma trận khối tam giác 3n × 3n; ngược lại nghịch đảo ma trận đối xứng xác định dương bằng chia đôi qua phần bù Schur khối, chỉ cần hai nghịch đảo nửa cỡ và bốn phép nhân nửa cỡ, và quy ma trận bất kỳ về AᵀA.
5. Tính đối xứng xác định dương được bảo toàn khi lấy ma trận con chính đầu (thu hẹp dạng toàn phương) và khi lấy phần bù Schur (hoàn thành bình phương), nên mọi trụ dương.
6. Cực tiểu tổng bình phương sai số là cực tiểu một hàm bậc hai lồi; cho gradient bằng 0 ra phương trình chuẩn với ma trận đối xứng xác định dương AᵀA.

### Bằng chứng và ví dụ tác giả đưa ra

- Chứng minh nghiệm duy nhất x = A⁻¹b bằng chuỗi đẳng thức x = Ix = (A⁻¹A)x = … = x′.
- Ví dụ LUP-SOLVE 3 × 3: A = (1 2 0; 3 4 4; 5 6 3), b = (3, 7, 8)ᵀ, π = (3, 1, 2), y = (8; 1,4; 1,5), x = (−1,4; 2,2; 0,6).
- Phép phân tích khối (28.8) và chứng minh phần bù Schur không suy biến bằng lập luận về hạng.
- Ví dụ LU-DECOMPOSITION 4 × 4 với các trụ 2, 4, 1, 3 (L = (1 0 0 0; 3 1 0 0; 1 4 1 0; 2 1 7 1), U = (2 3 1 5; 0 4 2 4; 0 0 1 2; 0 0 0 3)).
- Ví dụ LUP-DECOMPOSITION 4 × 4 qua chín trạng thái, trụ 5, −2, 4, −3, π = (3, 1, 4, 2).
- Ma trận D 3n × 3n và nghịch đảo của nó (Định lý 28.1); công thức khối (28.13) và bảy bước, truy hồi I(n) ≤ 2I(n/2) + 4M(n/2) + O(n²) (Định lý 28.2); đẳng thức A⁻¹ = (AᵀA)⁻¹Aᵀ.
- Bổ đề 28.3–28.5 và Hệ quả 28.6 với chứng minh đầy đủ; đẳng thức hoàn thành bình phương (28.16).
- Ví dụ khớp parabol qua năm điểm: giả nghịch đảo 3 × 5 cụ thể và c = (1,200; −0,757; 0,214).

### Kết luận và hàm ý cho người lập trình

- Đừng tính `inv(A)` để giải `Ax = b`; hãy phân rã một lần và giải bằng thế tiến/lùi, đặc biệt khi có nhiều vế phải.
- Luôn chọn trụ (ít nhất là chọn trụ từng phần như LUP-DECOMPOSITION) với ma trận tổng quát; chỉ bỏ chọn trụ khi biết chắc ma trận đối xứng xác định dương (hoặc chéo trội).
- Tận dụng cấu trúc: ma trận ba đường chéo hay ma trận băng giải được trong O(n) thay vì Θ(n³); nghịch đảo của ma trận thưa thường đặc, nên đừng lập nó.
- Khi cần khớp dữ liệu nhiễu, chọn mô hình ít tham số (n ≪ m) để tránh "khớp cả nhiễu"; bình phương tối thiểu là bài toán đại số tuyến tính, không phải tối ưu tổng quát.
- Mọi cải tiến về nhân ma trận (Strassen và các thuật toán sau) tự động áp dụng cho nghịch đảo, phân rã LUP, định thức — nên tối ưu một hàm nhân ma trận theo khối là tối ưu cả hệ sinh thái đại số tuyến tính.

### Trong ngôn ngữ khoa học máy tính

LUP-SOLVE: Θ(n²). LU-DECOMPOSITION, LUP-DECOMPOSITION: Θ(n³) (≈ n³/3 phép nhân–trừ ở vòng trong cùng), bộ nhớ phụ Θ(n) cho π khi làm tại chỗ. Nghịch đảo từ LUP: Θ(n³). Tương đương tiệm cận: M(n) = Θ(I(n)) dưới các điều kiện chính quy; với Strassen, I(n) = O(n^(lg 7)) ≈ O(n^2,807). Ma trận đối xứng xác định dương: không suy biến; Aₖ và S = C − BAₖ⁻¹Bᵀ đối xứng xác định dương; trụ thứ k = det Aₖ / det Aₖ₋₁ > 0. Bình phương tối thiểu: c = argmin ‖Ac − y‖₂ thoả AᵀAc = Aᵀy, c = A⁺y, A⁺ = (AᵀA)⁻¹Aᵀ; chi phí lập AᵀA là O(mn²), giải hệ n × n là O(n³). Hệ ba đường chéo: O(n).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| system of linear equations | hệ phương trình tuyến tính | n phương trình bậc nhất với các ẩn x₁..xₙ, viết gọn Ax = b |
| solution | nghiệm | bộ giá trị thoả đồng thời mọi phương trình |
| nonsingular / singular | không suy biến / suy biến | có / không có ma trận nghịch đảo |
| inverse | nghịch đảo | A⁻¹ với AA⁻¹ = A⁻¹A = I |
| rank | hạng | số hàng (cột) độc lập tuyến tính tối đa |
| underdetermined / overdetermined | thiếu phương trình / thừa phương trình | hạng nhỏ hơn số ẩn / nhiều phương trình hơn số ẩn |
| numerical stability | ổn định số học | sai số làm tròn không bị khuếch đại tới mức làm sai kết quả |
| round-off error | sai số làm tròn | chênh lệch do số dấu phẩy động có độ chính xác hữu hạn |
| LUP decomposition | phân rã LUP | PA = LU với P hoán vị, L tam giác dưới đơn vị, U tam giác trên |
| LU decomposition | phân rã LU | A = LU (không hoán vị) |
| unit lower-triangular matrix | ma trận tam giác dưới đơn vị | 0 phía trên đường chéo, 1 trên đường chéo |
| upper-triangular matrix | ma trận tam giác trên | 0 phía dưới đường chéo |
| permutation matrix | ma trận hoán vị | mỗi hàng, mỗi cột có đúng một số 1; lưu gọn bằng mảng π |
| forward substitution | phép thế tiến | giải Ly = Pb lần lượt từ y₁ tới yₙ |
| back substitution | phép thế lùi | giải Ux = y lần lượt từ xₙ về x₁ |
| Gaussian elimination | khử Gauss | trừ bội các phương trình để đưa hệ về dạng tam giác trên |
| Schur complement | phần bù Schur | A′ − vwᵀ/a₁₁, tổng quát C − BAₖ⁻¹Bᵀ |
| outer product | tích ngoài | vwᵀ, ma trận có phần tử (i, j) là vᵢwⱼ |
| pivot | phần tử trụ (trụ) | số đem chia ở mỗi bước phân rã, nằm trên đường chéo của U |
| pivoting | chọn trụ | dùng hoán vị hàng để tránh trụ bằng 0 hoặc quá nhỏ |
| tail-recursive procedure | thủ tục đệ quy đuôi | việc cuối cùng là gọi lại chính nó; đổi được thành vòng lặp |
| in place | tại chỗ | lưu L và U ngay trong mảng A |
| regularity condition | điều kiện chính quy | ràng buộc "đều đặn" lên hàm thời gian, như I(3n) = O(I(n)) |
| symmetric positive-definite matrix | ma trận đối xứng xác định dương | A = Aᵀ và xᵀAx > 0 với mọi x ≠ 0 |
| leading submatrix | ma trận con chính đầu | Aₖ: giao của k hàng đầu và k cột đầu |
| Schur complement lemma | bổ đề phần bù Schur | phần bù Schur của ma trận đối xứng xác định dương cũng vậy |
| completing the square | hoàn thành bình phương | viết dạng toàn phương thành bình phương cộng phần dư |
| quadratic form | dạng toàn phương | biểu thức xᵀAx |
| least-squares approximation | xấp xỉ bình phương tối thiểu | chọn tham số cực tiểu tổng bình phương sai số |
| basis functions | hàm cơ sở | các hàm fⱼ mà F là tổ hợp tuyến tính của chúng |
| approximation errors | sai số xấp xỉ | ηᵢ = F(xᵢ) − yᵢ |
| norm | chuẩn | độ dài vectơ, ‖η‖ = (Σηᵢ²)^(1/2) |
| full column rank | hạng cột đầy đủ | các cột độc lập tuyến tính |
| normal equation | phương trình chuẩn | AᵀAc = Aᵀy |
| pseudoinverse | giả nghịch đảo | A⁺ = (AᵀA)⁻¹Aᵀ, mở rộng nghịch đảo cho ma trận không vuông |
| conjugate transpose | chuyển vị liên hợp | A*: chuyển vị rồi lấy liên hợp phức từng phần tử |
| Hermitian matrix | ma trận Hermite | A = A* |
| transitive closure | bao đóng bắc cầu | ma trận cho biết có đường đi giữa mỗi cặp đỉnh hay không |
| boolean matrix | ma trận bun | ma trận phần tử 0/1 với phép "và", "hoặc" |
| determinant | định thức | det A; khác 0 khi và chỉ khi A không suy biến |
| tridiagonal matrix | ma trận ba đường chéo | chỉ khác 0 trên đường chéo chính và hai đường sát nó |
| cubic spline | spline bậc ba | đường cong ghép từ các đa thức bậc ba, trơn tại nút |
| knot | nút | điểm xᵢ nơi hai khúc đa thức được ghép |
| natural cubic spline | spline bậc ba tự nhiên | spline có đạo hàm bậc hai bằng 0 ở hai đầu |
| singular value decomposition (SVD) | phân rã giá trị kỳ dị | A = Q₁ΣQ₂ᵀ, Σ đường chéo, Q₁, Q₂ có cột trực chuẩn |
| orthonormal | trực chuẩn | tích vô hướng bằng 0 và chuẩn bằng 1 |

## Câu nói đáng nhớ

> "Because operations on matrices lie at the heart of scientific computing, efficient algorithms for working with matrices have many practical applications." — mở đầu Chương 28
>
> *Dịch: Vì các phép toán trên ma trận nằm ở trung tâm của tính toán khoa học, những thuật toán hiệu quả để làm việc với ma trận có rất nhiều ứng dụng thực tế.*

> "This approach suffers in practice from numerical instability. Fortunately, another approach—LUP decomposition—is numerically stable and has the further advantage of being faster in practice." — Mục 28.1, về việc tính A⁻¹ rồi nhân với b
>
> *Dịch: Cách này trong thực tế bị không ổn định số học. May mắn là có một cách khác — phân rã LUP — ổn định số học và còn có ưu điểm là nhanh hơn trong thực tế.*

> "The elements by which we divide during LU decomposition are called pivots, and they occupy the diagonal elements of the matrix U." — Mục 28.1
>
> *Dịch: Các phần tử mà ta đem chia trong quá trình phân rã LU được gọi là phần tử trụ, và chúng nằm ở các vị trí đường chéo của ma trận U.*

> "Thus, pivoting costs us at most a constant factor in time." — Mục 28.1, sau LUP-DECOMPOSITION
>
> *Dịch: Như vậy, việc chọn trụ chỉ khiến ta tốn thêm nhiều nhất một hằng số lần thời gian.*

> "In fact, we prove something stronger: matrix inversion is equivalent to matrix multiplication, in the following sense." — Mục 28.2
>
> *Dịch: Thực ra, ta chứng minh một điều mạnh hơn: nghịch đảo ma trận tương đương với nhân ma trận, theo nghĩa sau đây.*

> "Such a high-degree F “fits the noise” as well as the data, however, and generally gives poor results when used to predict y for previously unseen values of x." — Mục 28.3
>
> *Dịch: Tuy nhiên, một hàm F bậc cao như vậy "khớp cả nhiễu" lẫn dữ liệu, và thường cho kết quả kém khi dùng để dự đoán y tại những giá trị x chưa thấy trước đó.*

> "The pseudoinverse naturally generalizes the notion of a matrix inverse to the case in which A is not square." — Mục 28.3
>
> *Dịch: Giả nghịch đảo tổng quát hoá một cách tự nhiên khái niệm ma trận nghịch đảo cho trường hợp A không vuông.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: phần bù Schur là một sợi chỉ xuyên suốt cả chương

Cùng một đối tượng — phần bù Schur — làm ba việc khác nhau: nó là "phần việc còn lại" của khử Gauss (Mục 28.1, cho LU và LUP dưới dạng đệ quy), là khối then chốt trong công thức nghịch đảo khối (Định lý 28.2), và là công cụ chứng minh mọi trụ của ma trận đối xứng xác định dương đều dương (Bổ đề 28.5, Hệ quả 28.6). Cách trình bày khử Gauss như một phép phân tích khối đệ quy (28.8) thay vì một chuỗi thao tác hàng là lựa chọn rất "khoa học máy tính": nó biến một thuật toán số học cổ điển thành một thuật toán chia để trị có bất biến rõ ràng, chứng minh đúng bằng quy nạp, và nối thẳng với tư duy đệ quy đuôi của Chương 7.

### Điểm mạnh: kết quả tương đương nhân–nghịch đảo

Định lý 28.1 và 28.2 là ví dụ đẹp về phép quy giữa các bài toán (reduction) — kỹ thuật sẽ là trung tâm của Chương 34 (NP-đầy đủ). Ma trận D 3n × 3n là một mẹo gọn gàng, còn phép quy A⁻¹ = (AᵀA)⁻¹Aᵀ cho thấy cách "đổi bài toán khó thành bài toán có cấu trúc đẹp" rồi trả giá chỉ bằng hằng số lần phép nhân.

### Điểm yếu và chỗ đơn giản hoá

- **Ổn định số học được nhắc nhưng không phân tích.** Chương nói chọn trụ lớn nhất "để ổn định" nhưng không có ví dụ nào cho thấy LU không chọn trụ sai ra sao (người tổng hợp đã thêm ví dụ trụ 0,0001 ở phần Khái niệm). Theo hiểu biết của người tổng hợp, ngay cả chọn trụ từng phần cũng có thể không ổn định trên một vài ma trận dựng riêng (hệ số tăng trưởng 2^(n−1), ví dụ của Wilkinson), dù hiếm gặp trong thực tế.
- **Định lý 28.2 hữu ích về lý thuyết hơn thực tế.** Bước quy về AᵀA bình phương số điều kiện; các tác giả thừa nhận LUP tốt hơn, nhưng không nói rõ rằng thuật toán nghịch đảo kiểu Strassen kém ổn định số học.
- **Bình phương tối thiểu qua phương trình chuẩn.** Sách trình bày giải AᵀAc = Aᵀy bằng LU như cách thực hành, trong khi thực tế số học ưa dùng QR hoặc SVD (theo hiểu biết của người tổng hợp); sách cũng không nhắc tới phân rã Cholesky A = LLᵀ — cách tự nhiên nhất để khai thác Hệ quả 28.6 (chỉ cần nửa số phép tính và nửa bộ nhớ).
- **Chỉ dùng mô hình chi phí "mỗi phép toán số thực O(1)".** Với số hữu tỷ chính xác, khử Gauss có thể làm độ dài số tăng; sách không đề cập (vấn đề này quan trọng cho Chương 29, nơi thuật toán đơn hình cũng thực hiện các phép xoay trụ tương tự).
- **Chứng minh Định lý 28.2 hơi lỏng ở truy hồi** (viết Θ thay cho O, áp định lý thợ cho bất đẳng thức) — đã ghi trong khối Lưu ý.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: các thư viện đại số tuyến tính (LAPACK, Intel MKL, OpenBLAS, cuSOLVER trên GPU) cài phân rã LU có chọn trụ từng phần đúng như LUP-DECOMPOSITION, nhưng tổ chức theo khối (blocked/recursive LU) để phần lớn công việc trở thành phép nhân ma trận (BLAS mức 3) — đúng tinh thần "nghịch đảo và phân rã quy về nhân" của Mục 28.2, nhưng dùng nhân ma trận thường Θ(n³) chứ không dùng Strassen. Với ma trận thưa lớn (hàng triệu ẩn), người ta dùng phân rã thưa với sắp xếp lại để giảm phần tử điền thêm (fill-in) — chủ đề trong sách của George và Liu được trích dẫn — hoặc phương pháp lặp (gradient liên hợp cho ma trận đối xứng xác định dương). Spline bậc ba tự nhiên của Problem 28-2 có sẵn trong `scipy.interpolate.CubicSpline(bc_type='natural')` và được giải đúng bằng thuật toán ba đường chéo O(n) (thuật toán Thomas).

### Liên hệ các chương khác

- Phụ lục D ([PD-ma-tran.md](PD-ma-tran.md)): mọi định lý về hạng, định thức, ma trận hoán vị, xác định dương mà chương trích dẫn.
- Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)): thuật toán Strassen (Mục 4.2) và định lý thợ trường hợp 3 dùng trong Định lý 28.2.
- Chương 7 ([C07-quicksort.md](C07-quicksort.md)): Problem 7-4 về đệ quy đuôi, phép biến đổi dùng để viết LU-DECOMPOSITION.
- Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)): "nhân ma trận" trên nửa vành (min, +) và bao đóng bắc cầu; Exercise 28.2-4 nối bao đóng bắc cầu với nhân ma trận bun.
- Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)): nhân ma trận đa luồng; theo hiểu biết của người tổng hợp, Problem 27-3 ("Multithreaded matrix algorithms") yêu cầu song song hoá chính LU-DECOMPOSITION, LUP-DECOMPOSITION, LUP-SOLVE và thuật toán nghịch đảo của chương này.
- Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)): phép xoay trụ (pivot) của thuật toán đơn hình là họ hàng gần của một bước khử Gauss.
- Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)): nội suy đa thức (ma trận Vandermonde, giống ma trận A với fⱼ(x) = x^(j−1) khi m = n) và FFT.
- Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)): phép quy giữa các bài toán, cùng tư duy với Định lý 28.1–28.2.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** viết khử Gauss có chọn trụ để giải hệ hoặc tính định thức; giải thích vì sao không nên dùng `inv(A)`; cài thuật toán ba đường chéo O(n); hồi quy tuyến tính bằng phương trình chuẩn và những hạn chế của nó.
- **Lập trình thi đấu:** khử Gauss xuất hiện thường xuyên — trên số thực (có chọn trụ, so sánh với ε), trên trường modulo số nguyên tố p (chia bằng nghịch đảo modulo, trụ chỉ cần khác 0), trên GF(2) với bitset (bài toán XOR, "lights out"), tính hạng, định thức, và đếm cây khung bằng định lý ma trận cây Kirchhoff (định thức của ma trận Laplace bỏ một hàng một cột). Exercise 28.2-5 nhắc rằng các mẹo dựa trên xác định dương không dùng được trên trường hữu hạn — khi đó phải chọn trụ.
- **Kỹ thuật phần mềm:** tách "phân rã" khỏi "giải" để tái dùng phân rã cho nhiều vế phải (mô phỏng theo thời gian, bộ lọc Kalman); khai thác cấu trúc (ma trận đối xứng thì dùng Cholesky, ma trận băng thì giải theo băng, ma trận thưa thì dùng thư viện thưa); theo dõi số điều kiện để biết kết quả có đáng tin không; dùng spline tự nhiên khi cần đường cong trơn qua các điểm (đồ hoạ, hoạt hình, đường cong lãi suất).

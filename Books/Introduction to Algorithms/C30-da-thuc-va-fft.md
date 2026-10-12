# Chương 30 — Đa thức và biến đổi Fourier nhanh (Polynomials and the FFT)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VII "Selected Topics", Chương 30 "Polynomials and the FFT", trang 898–925 (phần mở đầu chương, Mục 30.1–30.3, Problems 30-1 đến 30-6, Chapter notes).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Chương này là một trong các "chủ đề chọn lọc" của Phần VII, nhưng nó dùng gần như nguyên vẹn các công cụ của những chương đầu. Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)) cho khuôn chia để trị và truy hồi T(n) = 2T(n/2) + Θ(n) = Θ(n lg n) — chính là truy hồi của FFT; Chương 4 cũng có thuật toán Strassen, một ví dụ khác về việc "tiết kiệm một phép nhân" tương tự Problem 30-1 (thuật toán Karatsuba). Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)) cho sắp xếp trộn, mà cây đệ quy có cùng hình dạng với cây lời gọi của RECURSIVE-FFT. Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)) có bộ đếm nhị phân đảo bit (Problem 17-1), được nhắc lại ở Mục 30.3 để sinh hoán vị đảo bit. Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)) bàn tính toán song song; Mục 30.3 trình bày một mạch FFT song song độ sâu Θ(lg n). Chương 28 ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)) cho phân rã LU, được dùng để nội suy trong O(n³) — cách chậm mà FFT thay thế. Phụ lục D ([PD-ma-tran.md](PD-ma-tran.md)) cho định thức Vandermonde (Problem D-1) và Định lý D.5 về ma trận khả nghịch, là nền của Định lý 30.1. Phụ lục A ([PA-tong.md](PA-tong.md)) cho công thức chuỗi hình học (A.5) dùng trong bổ đề tổng. Chương 31 ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)) cho nhóm, số học modulo và phần tử sinh, cần cho Problem 30-6 (FFT trên số nguyên modulo một số nguyên tố) và được nhắc khi nói các căn đơn vị tạo thành một nhóm. Chương 32 ([C32-so-khop-chuoi.md](C32-so-khop-chuoi.md)) xử lý so khớp chuỗi, một vùng mà theo hiểu biết của người tổng hợp FFT thường được dùng (so khớp có ký tự đại diện bằng tích chập).
**Ý chính:** Tác giả muốn người đọc hiểu rằng **nhân hai đa thức bậc nhỏ hơn n theo cách "nhân từng hạng tử" tốn Θ(n²), nhưng có thể hạ xuống Θ(n lg n) bằng cách đổi cách biểu diễn: chuyển hai đa thức từ dạng hệ số sang dạng giá trị tại các điểm (đánh giá), nhân từng cặp giá trị (Θ(n)), rồi chuyển ngược về dạng hệ số (nội suy); hai bước chuyển đổi chỉ nhanh được nếu chọn các điểm là các căn phức bậc 2n của đơn vị, vì khi đó bình phương các điểm lại là các căn đơn vị bậc thấp hơn một nửa (bổ đề chia đôi), cho phép chia để trị với truy hồi T(n) = 2T(n/2) + Θ(n); thuật toán đó là biến đổi Fourier nhanh (FFT), và phép nội suy ngược lại cũng chỉ là một FFT với ωₙ thay bằng ωₙ⁻¹ rồi chia cho n.** Phần mở đầu định nghĩa đa thức, hệ số, bậc, cận bậc (degree-bound), phép cộng (Θ(n)) và phép nhân (công thức tích chập cⱼ = Σₖ aₖbⱼ₋ₖ, Θ(n²)). Mục 30.1 so sánh hai cách biểu diễn: dạng hệ số (đánh giá bằng quy tắc Horner Θ(n), cộng Θ(n), nhân Θ(n²)) và dạng điểm–giá trị (cộng Θ(n), nhân Θ(n) nếu có đủ 2n điểm); Định lý 30.1 chứng minh nội suy là duy nhất nhờ ma trận Vandermonde khả nghịch; công thức Lagrange nội suy trong Θ(n²); rồi phác hoạ sơ đồ nhân nhanh bốn bước (gấp đôi cận bậc, đánh giá, nhân từng điểm, nội suy) và Định lý 30.2 (nhân đa thức trong Θ(n lg n)). Mục 30.2 định nghĩa căn phức bậc n của đơn vị, căn chính ωₙ = e^(2πi/n), chứng minh bổ đề triệt tiêu ω_(dn)^(dk) = ωₙᵏ, hệ quả ωₙ^(n/2) = −1, bổ đề chia đôi và bổ đề tổng; định nghĩa DFT yₖ = Σⱼ aⱼ ωₙ^(kj); trình bày RECURSIVE-FFT tách hệ số chỉ số chẵn và lẻ, A(x) = A^[0](x²) + x·A^[1](x²), chứng minh đúng và Θ(n lg n); rồi chỉ ra ma trận nghịch đảo của ma trận DFT có phần tử ωₙ^(−kj)/n (Định lý 30.7), nên DFT ngược cũng tính được trong Θ(n lg n), và phát biểu định lý tích chập (Định lý 30.8). Mục 30.3 biến FFT thành vòng lặp: gom biểu thức con chung thành phép "con bướm", nhận ra thứ tự lá của cây đệ quy là hoán vị đảo bit, viết BIT-REVERSE-COPY và ITERATIVE-FFT (chứng minh vòng trong chạy (n/2)·lg n lần), cuối cùng dựng mạch FFT song song gồm lg n tầng, mỗi tầng n/2 con bướm, độ sâu Θ(lg n).

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong chương này.** Dấu sao chỉ xuất hiện ở ba bài tập: Exercise 30.2-6 (FFT trên vành Zₘ với m = 2^(tn/2) + 1), Exercise 30.2-8 (biến đổi chirp) và Exercise 30.3-4 (tìm bộ cộng hỏng trong mạch FFT).
> - **Lớp chữ PDF hỏng toàn bộ ký hiệu toán của chương; mọi công thức, pseudocode và hình trong bản tổng hợp được đọc lại từ ảnh trang 898–925.** Cụ thể: ω bị thành "!" (ví dụ `!kn` là ωₙᵏ, `!D !! n` ở dòng 13 RECURSIVE-FFT là ω = ω·ωₙ); Θ thành "‚"; chỉ số trên [0], [1] thành `AŒ0`, `yŒ1k`; dấu trừ thành `/NUL`; dấu ≤ mất trong tích Vandermonde ("0j< kn/NUL1" là 0 ≤ j < k ≤ n − 1) và trong Bài toán 30-4, 30-5; ⊗ (tích chập) thành "˝"; dấu nhân từng thành phần "·" trong Định lý 30.8 mất hẳn ("and denotes the componentwise product"); dấu sao trong Z*ₚ của Problem 30-6 mất (lớp chữ chỉ còn "Zp"); ký hiệu z trong Exercise 30.2-7, 30.2-8 và Problem 30-5 thành "´"; công thức gợi ý của Exercise 30.2-8 vỡ thành nhiều mảnh. Các hình 30.1 (sơ đồ nhân nhanh), 30.2 (tám căn bậc 8 trên mặt phẳng phức), 30.3 (con bướm), 30.4 (cây lời gọi RECURSIVE-FFT với n = 8), 30.5 (mạch FFT song song n = 8) được mô tả lại từ ảnh trang 904, 907, 916, 919.
> - **Chỗ ký hiệu chưa chặt (nhận xét của người tổng hợp):** (1) Bổ đề triệt tiêu (Lemma 30.3, trang 907) phát biểu "với mọi số nguyên n ≥ 0", nhưng ωₙ = e^(2πi/n) không xác định khi n = 0; điều kiện đúng phải là n > 0 (người tổng hợp nhớ mang máng đây là một mục trong danh sách lỗi chính thức, nhưng không tra cứu). (2) Câu mở đầu đoạn "Interpolation at the complex roots of unity" (trang 912) viết "interpolate the complex roots of unity by a polynomial" — đảo ngược ý; ý đúng là nội suy một đa thức từ các giá trị của nó tại các căn đơn vị. (3) Phần mở đầu nói tích của hai đa thức cận bậc n có cận bậc 2n − 1, sau đó lại quen gọi là "cận bậc 2n"; sách tự giải thích vì một số lớn hơn bậc cũng là cận bậc, nên không sai, chỉ cần để ý khi đọc. (4) Exercise 30.2-6 chỉ yêu cầu "n chẵn", nhưng chứng minh bổ đề tổng trong vành Zₘ (không phải trường) thuận tiện nhất khi n là luỹ thừa của 2, đúng như giả định chung của chương; với n chẵn bất kỳ, người tổng hợp không chắc kết luận còn đúng. (5) Problem 30-1(b) nói "Θ(n^(lg 3))" — đúng cho thuật toán đề xuất; các bài còn lại không thấy lỗi.
> - **Ví dụ chạy tay đã tự kiểm tra lại và đúng:** phép cộng A(x) + B(x) = 4x³ + 7x² − 6x + 4 và phép nhân ra −12x⁶ − 14x⁵ + 44x⁴ − 20x³ − 75x² + 86x − 45 (trang 899); thứ tự lá 0, 4, 2, 6, 1, 5, 3, 7 của cây n = 8 và dãy đảo bit của nó (trang 918); phép chia dư (3x³ + x² − 3x + 1) mod (x² + x + 2) = −7x + 5 (Problem 30-5). Người tổng hợp còn tự tính (và kiểm tra bằng máy) các đáp số: Exercise 30.1-1, DFT của (0, 1, 2, 3) ở Exercise 30.2-2, toàn bộ các tầng của ITERATIVE-FFT trên (0, 2, 3, −1, 4, 5, 7, 9) ở Exercise 30.3-1, DFT modulo 17 ở Problem 30-6(d), và một ví dụ nhân đa thức nhỏ bằng FFT.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương "Polynomials and the FFT" vẫn có trong ấn bản 4 và vẫn mang số 30, với cùng mạch trình bày (biểu diễn đa thức, DFT và FFT, cài đặt hiệu quả); như ở các chương khác, ấn bản 4 bỏ thuộc tính `a.length` và truyền kích thước n làm tham số. Các khác biệt chi tiết hơn (bài tập, cách vẽ mạch song song), người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu Chương 30 (trước Mục 30.1, trang 898–900) — đa thức, phép cộng, phép nhân, dàn ý chương

```text
       Cộng hai đa thức bậc n theo cách thẳng: Θ(n)
       Nhân hai đa thức bậc n theo cách thẳng: Θ(n²)
       Mục tiêu chương: dùng FFT hạ thời gian nhân xuống Θ(n lg n)
                                │
                                ▼
       Ứng dụng phổ biến nhất của biến đổi Fourier là xử lý tín hiệu:
       · miền thời gian: tín hiệu là hàm từ thời gian sang biên độ
       · phân tích Fourier: viết tín hiệu thành tổng có trọng số của các
         sóng hình sin lệch pha, tần số khác nhau
       · trọng số và pha theo từng tần số mô tả tín hiệu trong miền tần số
       · ví dụ: nén video, âm thanh số, kể cả tệp MP3
                                │
                                ▼
       ĐA THỨC A(x) = Σⱼ₌₀ⁿ⁻¹ aⱼxʲ trên trường F (thường là số phức ℂ)
       · a₀, …, aₙ₋₁: hệ số
       · bậc k: hệ số khác 0 cao nhất là aₖ
       · cận bậc: mọi số nguyên lớn hơn hẳn bậc; đa thức cận bậc n có bậc
         từ 0 tới n − 1
                                │
           ┌────────────────────┴────────────────────┐
           ▼                                         ▼
   PHÉP CỘNG: cⱼ = aⱼ + bⱼ                   PHÉP NHÂN: C(x) = A(x)B(x)
   tổng có cùng cận bậc n                    cⱼ = Σₖ₌₀ʲ aₖbⱼ₋ₖ     (30.1), (30.2)
   Ví dụ: (6x³+7x²−10x+9)                    tích có cận bậc 2n − 1
        + (−2x³+4x−5)                        (thường gọi gọn là 2n)
        = 4x³+7x²−6x+4                       Ví dụ: cùng A, B ở bên trái
                                             cho −12x⁶−14x⁵+44x⁴−20x³
                                                −75x²+86x−45
                                │
                                ▼
       DÀN Ý: 30.1 hai cách biểu diễn (hệ số, điểm–giá trị) và ý tưởng
       chuyển qua lại; 30.2 căn phức của đơn vị, DFT, FFT và FFT ngược;
       30.3 cài đặt FFT nhanh: bản lặp tuần tự và mạch song song.
       Trong chương, ký hiệu i chỉ dùng cho √−1.
```

### Mục 30.1 — Biểu diễn đa thức (Representing polynomials, trang 900–906)

```text
   DẠNG HỆ SỐ: vectơ a = (a₀, a₁, …, aₙ₋₁)
   · đánh giá A(x₀) bằng quy tắc Horner:
     A(x₀) = a₀ + x₀(a₁ + x₀(a₂ + … + x₀(aₙ₋₂ + x₀aₙ₋₁)…))   — Θ(n)
   · cộng: Θ(n)
   · nhân: Θ(n²); vectơ hệ số kết quả gọi là TÍCH CHẬP c = a ⊗ b
                                │
                                ▼
   DẠNG ĐIỂM–GIÁ TRỊ: tập n cặp {(x₀, y₀), …, (xₙ₋₁, yₙ₋₁)}, các xₖ
   khác nhau đôi một, yₖ = A(xₖ)                                  (30.3)
   · đánh giá tại n điểm bằng Horner: Θ(n²)
   · ĐỊNH LÝ 30.1: n cặp với xₖ phân biệt xác định DUY NHẤT một đa thức
     cận bậc n. Chứng minh: hệ (30.4) có ma trận Vandermonde
     V(x₀, …, xₙ₋₁), định thức Π_{0≤j<k≤n−1} (xₖ − xⱼ) ≠ 0 nên khả nghịch
   · nội suy bằng giải hệ (phân rã LU): O(n³)
   · nội suy bằng công thức Lagrange (30.5): Θ(n²)
                                │
                                ▼
   Trong dạng điểm–giá trị (cùng các điểm xₖ cho A và B):
   · cộng: cộng từng yₖ — Θ(n)
   · nhân: nhân từng yₖ — Θ(n), NHƯNG tích có cận bậc 2n nên phải bắt
     đầu bằng biểu diễn "mở rộng" 2n cặp cho mỗi đa thức
   · đánh giá tại một điểm mới: không có cách nào đơn giản hơn là đổi về
     dạng hệ số trước
                                │
                                ▼
   NHÂN NHANH TRONG DẠNG HỆ SỐ (vẽ lại Hình 30.1):

   a₀…aₙ₋₁, b₀…bₙ₋₁ ──── nhân thông thường Θ(n²) ────▶ c₀ … c₂ₙ₋₂
          │                                                ▲
   đánh giá Θ(n lg n)                               nội suy Θ(n lg n)
   (FFT bậc 2n)                                     (FFT ngược)
          ▼                                                │
   A(ω₂ₙᵏ), B(ω₂ₙᵏ),  ── nhân từng điểm Θ(n) ──▶  C(ω₂ₙᵏ),
   k = 0..2n−1                                    k = 0..2n−1
   (hàng trên: dạng hệ số; hàng dưới: dạng điểm–giá trị)
                                │
                                ▼
   Bốn bước (n là luỹ thừa của 2):
   1. Gấp đôi cận bậc: thêm n hệ số 0 bậc cao              Θ(n)
   2. Đánh giá: FFT bậc 2n cho A và cho B                   Θ(n lg n)
   3. Nhân từng điểm: C(ω₂ₙᵏ) = A(ω₂ₙᵏ)·B(ω₂ₙᵏ)              Θ(n)
   4. Nội suy: FFT trên 2n cặp để tính DFT ngược            Θ(n lg n)
   ⇒ ĐỊNH LÝ 30.2: nhân hai đa thức cận bậc n trong Θ(n lg n), đầu vào
     và đầu ra đều ở dạng hệ số
```

### Mục 30.2 — DFT và FFT (The DFT and FFT, trang 906–915)

```text
   CĂN PHỨC BẬC n CỦA ĐƠN VỊ: số phức ω với ωⁿ = 1
   · có đúng n căn: e^(2πik/n), k = 0..n−1, với e^(iu) = cos u + i sin u
   · nằm cách đều trên đường tròn bán kính 1 tâm gốc toạ độ
   · căn chính ωₙ = e^(2πi/n)                                   (30.6)
     mọi căn khác là luỹ thừa của ωₙ; ωₙʲωₙᵏ = ωₙ^((j+k) mod n)
     (cấu trúc như nhóm cộng (Zₙ, +)); ωₙ⁻¹ = ωₙⁿ⁻¹
                                │
                                ▼
   BA TÍNH CHẤT:
   · Bổ đề 30.3 (triệt tiêu): ω_(dn)^(dk) = ωₙᵏ                  (30.7)
     Hệ quả 30.4: n chẵn ⇒ ωₙ^(n/2) = ω₂ = −1
   · Bổ đề 30.5 (chia đôi): n chẵn ⇒ bình phương của n căn bậc n là
     n/2 căn bậc n/2, mỗi căn xuất hiện đúng hai lần
     (vì (ωₙ^(k+n/2))² = (ωₙᵏ)²)
   · Bổ đề 30.6 (tổng): k ≠ 0 không chia hết cho n ⇒
     Σⱼ₌₀ⁿ⁻¹ (ωₙᵏ)ʲ = ((ωₙᵏ)ⁿ − 1)/(ωₙᵏ − 1) = 0
                                │
                                ▼
   DFT: yₖ = A(ωₙᵏ) = Σⱼ aⱼ ωₙ^(kj), k = 0..n−1                 (30.8)
   y = DFTₙ(a); tính thẳng tốn Θ(n²)
                                │
                                ▼
   FFT (chia để trị, n luỹ thừa của 2):
   A^[0](x) = a₀ + a₂x + … + aₙ₋₂x^(n/2−1)  (hệ số chỉ số chẵn)
   A^[1](x) = a₁ + a₃x + … + aₙ₋₁x^(n/2−1)  (hệ số chỉ số lẻ)
   A(x) = A^[0](x²) + x·A^[1](x²)                                (30.9)
   · các điểm (ωₙᵏ)² chỉ là n/2 căn bậc n/2 (bổ đề chia đôi)
   · ⇒ hai bài toán DFT_(n/2) cùng dạng, nửa kích thước
                                │
                                ▼
   RECURSIVE-FFT: đệ quy hai nửa, rồi với k = 0..n/2−1:
     yₖ        = yₖ^[0] + ωₙᵏ·yₖ^[1]
     yₖ₊₍ₙ/₂₎  = yₖ^[0] − ωₙᵏ·yₖ^[1]     (vì ωₙ^(k+n/2) = −ωₙᵏ)
   ωₙᵏ gọi là HỆ SỐ XOAY (twiddle factor)
   T(n) = 2T(n/2) + Θ(n) = Θ(n lg n)
                                │
                                ▼
   NỘI SUY TẠI CĂN ĐƠN VỊ: y = Vₙa, Vₙ[k, j] = ωₙ^(kj)
   Định lý 30.7: Vₙ⁻¹[j, k] = ωₙ^(−kj)/n (chứng minh bằng bổ đề tổng)
   ⇒ aⱼ = (1/n) Σₖ yₖ ωₙ^(−kj)                                  (30.11)
   ⇒ DFT ngược = FFT với a và y đổi vai, ωₙ thay bằng ωₙ⁻¹, chia cho n
     — cũng Θ(n lg n)
                                │
                                ▼
   Định lý 30.8 (tích chập): với a, b dài n (luỹ thừa của 2), đệm 0 tới 2n:
     a ⊗ b = DFT₂ₙ⁻¹( DFT₂ₙ(a) · DFT₂ₙ(b) )   (· là nhân từng thành phần)
```

### Mục 30.3 — Cài đặt FFT hiệu quả (Efficient FFT implementations, trang 915–920)

```text
   Ứng dụng thực tế (xử lý tín hiệu) đòi tốc độ tối đa ⇒ hai cài đặt:
   bản lặp (hằng số nhỏ hơn) và mạch song song
                                │
                                ▼
   BIỂU THỨC CON CHUNG: ωₙᵏyₖ^[1] được tính hai lần ⇒ lưu vào t
   PHÉP CON BƯỚM: t = ω·yₖ^[1]; ra yₖ^[0] + t và yₖ^[0] − t
   (vẽ lại Hình 30.3)
        yₖ^[0] ───────●──────(+)──▶ yₖ^[0] + ωₙᵏyₖ^[1]
                       ╲    ╱
        ωₙᵏ ──┐         ╳
        yₖ^[1] ──(×)──●╱ ╲──(−)──▶ yₖ^[0] − ωₙᵏyₖ^[1]
                                │
                                ▼
   CÂY LỜI GỌI với n = 8 (vẽ lại Hình 30.4):
                     (a0,a1,a2,a3,a4,a5,a6,a7)
              ┌──────────────┴──────────────┐
         (a0,a2,a4,a6)                 (a1,a3,a5,a7)
         ┌─────┴─────┐                 ┌─────┴─────┐
      (a0,a4)     (a2,a6)           (a1,a5)     (a3,a7)
      ┌──┴──┐     ┌──┴──┐           ┌──┴──┐     ┌──┴──┐
    (a0) (a4)   (a2) (a6)         (a1) (a5)   (a3) (a7)
   Thứ tự lá 0,4,2,6,1,5,3,7 = HOÁN VỊ ĐẢO BIT:
   000,100,010,110,001,101,011,111 đảo bit thành 000,001,…,111
                                │
                                ▼
   Đi từ dưới lên: xếp a theo thứ tự lá (BIT-REVERSE-COPY: A[rev(k)] = aₖ)
   rồi với s = 1..lg n, m = 2ˢ: ghép từng cặp DFT cỡ m/2 thành DFT cỡ m
   bằng m/2 con bướm, hệ số xoay ω_mʲ (ITERATIVE-FFT, làm tại chỗ nhờ u)
   Số lần chạy vòng trong: L(n) = Σₛ (n/2ˢ)·2ˢ⁻¹ = (n/2) lg n = Θ(n lg n)
   BIT-REVERSE-COPY: O(n lg n), hoặc Θ(n) nếu dùng bảng tra hay bộ đếm
   nhị phân đảo (Problem 17-1)
                                │
                                ▼
   MẠCH FFT SONG SONG (vẽ lại Hình 30.5 cho n = 8):
   hoán vị đảo bit ở đầu vào, rồi lg n tầng, mỗi tầng n/2 con bướm chạy
   song song
   · tầng s gồm n/2ˢ nhóm, mỗi nhóm 2ˢ⁻¹ con bướm, hệ số xoay
     ω_m⁰, …, ω_m^(m/2−1), m = 2ˢ
   · độ sâu mạch Θ(lg n), tổng số con bướm Θ(n lg n)
```

### Bài toán cuối chương (Problems 30-1 đến 30-6, trang 920–924)

```text
   30-1 Nhân chia để trị: (ax+b)(cx+d) chỉ với 3 phép nhân, dùng (a+b)(c+d)
        ⇒ nhân đa thức cận bậc n trong Θ(n^(lg 3)) (chia nửa cao/thấp hoặc
        chia chỉ số chẵn/lẻ) ⇒ nhân hai số n bit trong O(n^(lg 3)) bước
                                │
                                ▼
   30-2 Ma trận Toeplitz (aᵢⱼ = aᵢ₋₁,ⱼ₋₁): tổng là Toeplitz, tích thì không;
        lưu hàng đầu và cột đầu (2n − 1 số) ⇒ cộng O(n); nhân với vectơ
        là một tích chập ⇒ O(n lg n); nhân hai ma trận Toeplitz
                                │
                                ▼
   30-3 FFT nhiều chiều: DFT d chiều = lần lượt DFT 1 chiều theo từng
        chiều, thứ tự tuỳ ý, tổng thời gian O(n lg n) không phụ thuộc d
                                │
                                ▼
   30-4 Đánh giá mọi đạo hàm A^(t)(x₀), t = 0..n−1, trong O(n lg n):
        khai triển theo (x − x₀), dùng DFT ngược và một tích chập
                                │
                                ▼
   30-5 Đánh giá tại n điểm tuỳ ý trong O(n lg² n): dùng các đa thức
        Pᵢⱼ = Πₖ₌ᵢʲ (x − xₖ) và phần dư Qᵢⱼ = A mod Pᵢⱼ, đi xuống theo cây
                                │
                                ▼
   30-6 FFT dùng số học modulo: chọn số nguyên tố p = kn + 1 (k ≈ ln n),
        căn bậc n của đơn vị w = gᵏ mod p (g sinh Z*ₚ) ⇒ kết quả nguyên
        chính xác, từ máy O(lg n) bit; ví dụ p = 17, w = 9
```

### Ghi chú chương (Chapter notes, trang 924–925)

```text
   Tài liệu: Van Loan (FFT); Press, Teukolsky, Vetterling, Flannery (FFT
   và ứng dụng); Oppenheim–Schafer và Oppenheim–Willsky (xử lý tín hiệu;
   Oppenheim–Schafer xử lý cả n không phải luỹ thừa của 2)
                                │
                                ▼
   Fourier nhiều chiều trong xử lý ảnh: Gonzalez–Woods, Pratt; toán học
   FFT nhiều chiều: Tolimieri–An–Lu, Van Loan
                                │
                                ▼
   Lịch sử: Cooley và Tukey (thập niên 1960) thường được ghi công; FFT đã
   được phát hiện nhiều lần trước đó; Press và cộng sự truy tới Runge và
   König (1924); Heideman, Johnson, Burrus truy tới Gauss (1805)
                                │
                                ▼
   FFTW (Frigo và Johnson): "bộ lập kế hoạch" chạy thử để chọn cách phân
   rã tốt nhất trên máy cụ thể, tận dụng bộ nhớ đệm, mã thẳng tối ưu cho
   bài toán con nhỏ; Θ(n lg n) với MỌI n, kể cả n là số nguyên tố lớn
                                │
                                ▼
   Dữ liệu không cách đều trong miền thời gian: có kỹ thuật xấp xỉ FFT
   ("nonequispaced"), tổng quan của Ware
```

## Ba câu hỏi chương này trả lời

1. **Vì sao nhân đa thức theo dạng hệ số tốn Θ(n²), và đổi sang dạng điểm–giá trị giúp gì?** Ở dạng hệ số, mỗi hệ số của tích cⱼ = Σₖ₌₀ʲ aₖbⱼ₋ₖ là tổng của nhiều tích, và tổng cộng mỗi aₖ phải nhân với mỗi bⱼ: n² phép nhân. Ví dụ (6x³ + 7x² − 10x + 9)(−2x³ + 4x − 5) cần 4 · 3 = 12 tích khác 0 (vì b₂ = 0) để ra −12x⁶ − 14x⁵ + 44x⁴ − 20x³ − 75x² + 86x − 45. Ở dạng điểm–giá trị, nếu biết A và B tại cùng 2n điểm thì C = AB tại các điểm đó chỉ là 2n phép nhân số: Θ(n). Định lý 30.1 bảo đảm 2n cặp điểm–giá trị xác định duy nhất đa thức cận bậc 2n (ma trận Vandermonde của các điểm phân biệt có định thức Π(xₖ − xⱼ) ≠ 0). Cái giá nằm ở hai bước chuyển đổi: đánh giá tại n điểm tuỳ ý bằng Horner tốn Θ(n²), nội suy bằng Lagrange tốn Θ(n²). Vì vậy chỉ đổi biểu diễn thôi chưa đủ; phải chọn điểm khéo.
2. **Vì sao chọn các căn phức của đơn vị làm điểm thì đánh giá được trong Θ(n lg n)?** Viết A(x) = A^[0](x²) + x·A^[1](x²) với A^[0] gồm hệ số chỉ số chẵn, A^[1] gồm hệ số chỉ số lẻ. Đánh giá A tại n điểm quy về đánh giá A^[0], A^[1] (cận bậc n/2) tại các bình phương của n điểm đó. Với điểm tuỳ ý, n bình phương vẫn là n điểm khác nhau, không lợi gì. Với n căn bậc n của đơn vị, bổ đề chia đôi cho biết n bình phương chỉ là n/2 căn bậc n/2, mỗi căn lặp hai lần (vì ωₙ^(k+n/2) = −ωₙᵏ). Bài toán con vì thế đúng là bài toán gốc cỡ n/2, và bước ghép chỉ cần yₖ = yₖ^[0] + ωₙᵏyₖ^[1], yₖ₊ₙ/₂ = yₖ^[0] − ωₙᵏyₖ^[1]: T(n) = 2T(n/2) + Θ(n) = Θ(n lg n). Ví dụ DFT của (0, 1, 2, 3) với ω₄ = i: nửa chẵn (0, 2) có DFT (2, −2), nửa lẻ (1, 3) có DFT (4, −2); ghép ra y₀ = 2 + 4 = 6, y₂ = 2 − 4 = −2, y₁ = −2 + i(−2) = −2 − 2i, y₃ = −2 − i(−2) = −2 + 2i.
3. **Làm sao quay về dạng hệ số nhanh như vậy, và cài đặt FFT hiệu quả ra sao?** Ma trận DFT Vₙ có phần tử ωₙ^(kj); nhờ bổ đề tổng (Σⱼ ωₙ^(kj) = 0 khi k không chia hết cho n), nghịch đảo của nó có phần tử ωₙ^(−kj)/n (Định lý 30.7). Vậy DFT ngược aⱼ = (1/n) Σₖ yₖωₙ^(−kj) chính là một FFT với ωₙ thay bằng ωₙ⁻¹ rồi chia mọi kết quả cho n — cũng Θ(n lg n). Ghép lại: a ⊗ b = DFT₂ₙ⁻¹(DFT₂ₙ(a) · DFT₂ₙ(b)) (định lý tích chập). Ví dụ (1 + 2x)(3 + 4x): đệm thành độ dài 4, DFT ra (3, 1 + 2i, −1, 1 − 2i) và (7, 3 + 4i, −1, 3 − 4i), nhân từng thành phần ra (21, −5 + 10i, 1, −5 − 10i), DFT ngược ra (3, 10, 8, 0), tức 3 + 10x + 8x². Về cài đặt: lưu ωₙᵏyₖ^[1] vào biến t để có phép "con bướm"; xếp đầu vào theo hoán vị đảo bit (với n = 8: a₀, a₄, a₂, a₆, a₁, a₅, a₃, a₇) rồi chạy lg n tầng từ dưới lên, mỗi tầng n/2 con bướm tại chỗ (ITERATIVE-FFT, (n/2) lg n lần vòng trong); vì n/2 con bướm trong một tầng độc lập nhau, có thể làm mạch song song độ sâu Θ(lg n).

## Khái niệm cần biết

- **Đa thức (polynomial), hệ số (coefficients):** đa thức theo biến x trên một trường F là tổng hình thức A(x) = Σⱼ₌₀ⁿ⁻¹ aⱼxʲ; các aⱼ là hệ số, lấy từ F (thường là tập số phức ℂ). Ví dụ A(x) = 6x³ + 7x² − 10x + 9 có a₀ = 9, a₁ = −10, a₂ = 7, a₃ = 6. Đây là đối tượng của cả chương; "trường" quan trọng vì cần chia được (chia cho n trong DFT ngược).
- **Bậc (degree) và cận bậc (degree-bound):** bậc của A là k nếu hệ số khác 0 cao nhất là aₖ, viết degree(A) = k. Mọi số nguyên lớn hơn hẳn bậc là một cận bậc. Ví dụ A trên có bậc 3; nó có cận bậc 4, cũng có cận bậc 5, 8, … Quan trọng vì sách luôn nói "đa thức cận bậc n" = "có n hệ số a₀..aₙ₋₁" — cách đếm này khớp với độ dài vectơ trong FFT.
- **Tích chập (convolution):** vectơ hệ số c của tích C = AB, cⱼ = Σₖ₌₀ʲ aₖbⱼ₋ₖ, ký hiệu c = a ⊗ b. Ví dụ a = (1, 2), b = (3, 4): c₀ = 1·3 = 3, c₁ = 1·4 + 2·3 = 10, c₂ = 2·4 = 8. Quan trọng vì tích chập là phép toán gốc mà FFT tăng tốc, xuất hiện ngoài đa thức (nhân số lớn, lọc tín hiệu, đếm tổng ở Exercise 30.1-7).
- **Quy tắc Horner (Horner's rule):** đánh giá A(x₀) = a₀ + x₀(a₁ + x₀(a₂ + … + x₀(aₙ₋₂ + x₀aₙ₋₁)…)) trong Θ(n). Ví dụ A(x) = 6x³ + 7x² − 10x + 9 tại x₀ = 2: 6 → 6·2 + 7 = 19 → 19·2 − 10 = 28 → 28·2 + 9 = 65; kiểm tra 48 + 28 − 20 + 9 = 65. Quan trọng vì nó là mốc so sánh: đánh giá tại n điểm bằng Horner tốn Θ(n²), FFT làm việc đó trong Θ(n lg n) cho các điểm đặc biệt.
- **Biểu diễn hệ số (coefficient representation):** đa thức cận bậc n được lưu bằng vectơ (a₀, …, aₙ₋₁) (coi như vectơ cột). Thuận lợi cho đánh giá và cộng (Θ(n)), bất lợi cho nhân (Θ(n²)).
- **Biểu diễn điểm–giá trị (point-value representation):** tập n cặp {(xₖ, yₖ)} với các xₖ phân biệt và yₖ = A(xₖ). Ví dụ A(x) = 1 + 2x có biểu diễn {(0, 1), (1, 3)}, cũng có biểu diễn {(−1, −1), (5, 11)}. Thuận lợi cho cộng và nhân (Θ(n)) nếu A và B dùng chung các điểm; bất lợi khi cần giá trị tại điểm mới.
- **Đánh giá (evaluation) và nội suy (interpolation):** đánh giá là đi từ dạng hệ số sang dạng điểm–giá trị; nội suy là chiều ngược lại. Ví dụ nội suy {(0, 1), (1, 3)} ra 1 + 2x. Hai phép này là "cửa ngõ" của sơ đồ nhân nhanh.
- **Ma trận Vandermonde:** ma trận V(x₀, …, xₙ₋₁) có hàng k là (1, xₖ, xₖ², …, xₖⁿ⁻¹); định thức Π_{0≤j<k≤n−1} (xₖ − xⱼ). Ví dụ với điểm 1, 2, 3: định thức (2 − 1)(3 − 1)(3 − 2) = 2 ≠ 0. Quan trọng vì nó chứng minh nội suy duy nhất (Định lý 30.1), và ma trận DFT là một ma trận Vandermonde tại các căn đơn vị.
- **Công thức Lagrange:** A(x) = Σₖ yₖ · Π_{j≠k}(x − xⱼ) / Π_{j≠k}(xₖ − xⱼ). Ví dụ với (0, 1), (1, 3): A(x) = 1·(x − 1)/(0 − 1) + 3·(x − 0)/(1 − 0) = 1 − x + 3x = 1 + 2x. Cho nội suy Θ(n²) (Exercise 30.1-5), nhanh hơn giải hệ O(n³).
- **Biểu diễn điểm–giá trị mở rộng (extended point-value representation):** dùng 2n cặp cho mỗi đa thức cận bậc n, để tích (cận bậc 2n) có đủ điểm nội suy. Ví dụ A = 1 + 2x, B = 3 + 4x tại 4 điểm 0, 1, −1, 2: A cho 1, 3, −1, 5; B cho 3, 7, −1, 11; tích cho 3, 21, 1, 55 — đúng giá trị của 3 + 10x + 8x² tại 0, 1, −1, 2 (8·4 + 20 + 3 = 55).
- **Căn phức bậc n của đơn vị (complex nth root of unity):** số phức ω với ωⁿ = 1; có đúng n căn e^(2πik/n), k = 0..n − 1, cách đều trên đường tròn đơn vị. Ví dụ n = 4: 1, i, −1, −i. Quan trọng vì chọn các điểm này thì đánh giá và nội suy đều Θ(n lg n).
- **Căn chính (principal nth root of unity):** ωₙ = e^(2πi/n) = cos(2π/n) + i sin(2π/n). Ví dụ ω₄ = i, ω₈ = (1 + i)/√2 ≈ 0,7071 + 0,7071i, ω₂ = −1. Mọi căn bậc n khác là ωₙᵏ. (Ghi chú chân trang: nhiều tác giả, nhất là trong xử lý tín hiệu, dùng ωₙ = e^(−2πi/n); toán học bên dưới về cơ bản như nhau.)
- **Bổ đề triệt tiêu (cancellation lemma):** ω_(dn)^(dk) = ωₙᵏ với n > 0, k ≥ 0, d > 0. Ví dụ ω₈² = ω₄ = i; ω₈⁴ = ω₂ = −1. Dùng để đổi căn bậc n/2 thành căn bậc n trong chứng minh RECURSIVE-FFT.
- **Bổ đề chia đôi (halving lemma):** với n chẵn, bình phương của n căn bậc n là n/2 căn bậc n/2, mỗi căn đúng hai lần. Ví dụ n = 4: bình phương của 1, i, −1, −i là 1, −1, 1, −1 — chỉ hai căn bậc 2. Đây là lý do bài toán con chỉ còn một nửa.
- **Bổ đề tổng (summation lemma):** với n ≥ 1 và k ≠ 0 không chia hết cho n, Σⱼ₌₀ⁿ⁻¹ (ωₙᵏ)ʲ = 0. Ví dụ n = 4, k = 1: 1 + i − 1 − i = 0; k = 2: 1 − 1 + 1 − 1 = 0. Dùng để chứng minh công thức nghịch đảo của ma trận DFT.
- **Biến đổi Fourier rời rạc (discrete Fourier transform, DFT):** với a = (a₀, …, aₙ₋₁), DFTₙ(a) = y với yₖ = A(ωₙᵏ) = Σⱼ aⱼωₙ^(kj). Ví dụ DFT₄(0, 1, 2, 3) = (6, −2 − 2i, −2, −2 + 2i). DFT chính là "đánh giá tại các căn đơn vị".
- **Biến đổi Fourier nhanh (fast Fourier transform, FFT):** thuật toán chia để trị tính DFTₙ trong Θ(n lg n) thay vì Θ(n²), khi n là luỹ thừa của 2. Với n = 2²⁰ ≈ 10⁶: n² ≈ 1,1·10¹² phép nhân so với n lg n ≈ 2,1·10⁷ — nhanh hơn khoảng 52.000 lần (người tổng hợp tính).
- **A^[0] và A^[1] (tách chẵn–lẻ):** A^[0](x) = a₀ + a₂x + a₄x² + …, A^[1](x) = a₁ + a₃x + a₅x² + …; A(x) = A^[0](x²) + xA^[1](x²) (30.9). Ví dụ A(x) = 9 − 10x + 7x² + 6x³: A^[0](x) = 9 + 7x, A^[1](x) = −10 + 6x; tại x = 2: A^[0](4) = 37, A^[1](4) = 14, 37 + 2·14 = 65 = A(2). "Chỉ số chẵn" cũng là "bit thấp nhất của chỉ số bằng 0" — gốc của hoán vị đảo bit.
- **Hệ số xoay (twiddle factor):** các thừa số ωₙᵏ nhân với yₖ^[1] trong bước ghép; được dùng cả với dấu cộng và dấu trừ. Ví dụ n = 4: hệ số xoay là ω₄⁰ = 1 và ω₄¹ = i.
- **DFT ngược (inverse DFT):** a = DFTₙ⁻¹(y), aⱼ = (1/n) Σₖ yₖωₙ^(−kj) (30.11). Ví dụ DFT₄⁻¹(6, −2 − 2i, −2, −2 + 2i) = (0, 1, 2, 3). Đây là phép nội suy tại các căn đơn vị.
- **Định lý tích chập (convolution theorem):** a ⊗ b = DFT₂ₙ⁻¹(DFT₂ₙ(a) · DFT₂ₙ(b)), với a, b đệm 0 tới độ dài 2n và "·" là nhân từng thành phần. Đây là phát biểu gọn của cả chương.
- **Phép con bướm (butterfly operation):** nhận hai giá trị yₖ^[0], yₖ^[1] và hệ số xoay ω, tính t = ω·yₖ^[1], cho ra yₖ^[0] + t và yₖ^[0] − t. Ví dụ ω = i, yₖ^[0] = −2, yₖ^[1] = −2: t = −2i, ra −2 − 2i và −2 + 2i. Là đơn vị tính toán của FFT lặp và của mạch song song.
- **Biểu thức con chung (common subexpression):** giá trị được tính hai lần trong cùng đoạn mã (ở đây ωₙᵏyₖ^[1]); lưu vào biến tạm để tính một lần. Thuật ngữ của trình biên dịch.
- **Hoán vị đảo bit (bit-reversal permutation):** với rev(k) là số lg n bit nhận được khi đảo thứ tự bit của k, đặt aₖ vào ô A[rev(k)]. Ví dụ n = 8: k = 1 = 001 có rev(1) = 100 = 4; k = 6 = 110 có rev(6) = 011 = 3. Thứ tự lá của cây lời gọi là 0, 4, 2, 6, 1, 5, 3, 7. Cho phép chạy FFT từ dưới lên, tại chỗ.
- **Độ sâu mạch (circuit depth):** số phần tử tính toán lớn nhất trên một đường từ một đầu vào tới một đầu ra mà nó ảnh hưởng. Mạch FFT có lg n tầng con bướm nên độ sâu Θ(lg n); với n = 8 là 3 tầng. Đo thời gian chạy song song của mạch.
- **Hoạt động trên vành số nguyên modulo (FFT modulo):** thay ℂ bằng Zₚ với p nguyên tố dạng kn + 1, và ωₙ bằng một phần tử w có bậc n modulo p. Ví dụ p = 17, n = 8, g = 3, w = 3² mod 17 = 9: 9¹, …, 9⁸ ≡ 9, 13, 15, 16, 8, 4, 2, 1 (mod 17), và 9⁴ ≡ 16 ≡ −1. Cho kết quả nguyên chính xác, không sai số làm tròn (Problem 30-6).

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 898–900)

Chương mở đầu bằng một so sánh: cộng hai đa thức bậc n theo cách thẳng tốn Θ(n), còn nhân chúng theo cách thẳng tốn Θ(n²). Chương sẽ chỉ ra biến đổi Fourier nhanh (fast Fourier transform, FFT) hạ thời gian nhân đa thức xuống Θ(n lg n).

Tác giả nói thêm về bối cảnh: ứng dụng phổ biến nhất của biến đổi Fourier, và vì thế của FFT, là **xử lý tín hiệu**. Một tín hiệu được cho trong **miền thời gian** (time domain): một hàm ánh xạ thời gian sang biên độ. Phân tích Fourier cho phép viết tín hiệu thành tổng có trọng số của các sóng hình sin lệch pha với tần số khác nhau. Các trọng số và pha gắn với từng tần số mô tả tín hiệu trong **miền tần số** (frequency domain). Trong số rất nhiều ứng dụng hằng ngày của FFT có các kỹ thuật nén dùng để mã hoá video và âm thanh số, kể cả tệp MP3. Sách không đi sâu vào xử lý tín hiệu; phần Ghi chú chương giới thiệu vài cuốn sách chuyên đề.

#### Đa thức (Polynomials)

Một **đa thức** theo biến x trên một trường đại số F biểu diễn một hàm A(x) dưới dạng tổng hình thức

```text
A(x) = Σⱼ₌₀ⁿ⁻¹ aⱼ xʲ
```

Các giá trị a₀, a₁, …, aₙ₋₁ là **hệ số** của đa thức, lấy từ trường F, thường là tập số phức ℂ. Đa thức A(x) có **bậc** k nếu hệ số khác 0 cao nhất của nó là aₖ; ta viết degree(A) = k. Mọi số nguyên lớn hơn hẳn bậc của một đa thức là một **cận bậc** (degree-bound) của đa thức đó. Do đó bậc của một đa thức có cận bậc n có thể là bất kỳ số nguyên nào từ 0 tới n − 1, kể cả hai đầu.

**Phép cộng đa thức.** Nếu A(x) và B(x) là hai đa thức cận bậc n, **tổng** của chúng là đa thức C(x), cũng có cận bậc n, sao cho C(x) = A(x) + B(x) với mọi x trong trường nền. Tức là nếu A(x) = Σⱼ₌₀ⁿ⁻¹ aⱼxʲ và B(x) = Σⱼ₌₀ⁿ⁻¹ bⱼxʲ thì C(x) = Σⱼ₌₀ⁿ⁻¹ cⱼxʲ với cⱼ = aⱼ + bⱼ, j = 0, 1, …, n − 1. Ví dụ của sách: A(x) = 6x³ + 7x² − 10x + 9 và B(x) = −2x³ + 4x − 5 cho C(x) = 4x³ + 7x² − 6x + 4 (cộng theo bậc: x³: 6 − 2 = 4; x²: 7 + 0 = 7; x: −10 + 4 = −6; hằng số: 9 − 5 = 4).

**Phép nhân đa thức.** Nếu A(x) và B(x) là hai đa thức cận bậc n, **tích** của chúng là đa thức C(x) cận bậc 2n − 1 sao cho C(x) = A(x)B(x) với mọi x trong trường nền. Cách quen thuộc là nhân từng hạng tử của A với từng hạng tử của B rồi gộp các hạng tử cùng luỹ thừa. Sách nhân A(x) = 6x³ + 7x² − 10x + 9 với B(x) = −2x³ + 4x − 5 theo kiểu đặt tính:

```text
                    6x³ +  7x² − 10x +  9
               ×  − 2x³        +  4x −  5
   ─────────────────────────────────────────────────
                 − 30x³ − 35x² + 50x − 45      (nhân với −5)
           24x⁴ + 28x³ − 40x² + 36x            (nhân với 4x)
 − 12x⁶ − 14x⁵ + 20x⁴ − 18x³                   (nhân với −2x³)
   ─────────────────────────────────────────────────
 − 12x⁶ − 14x⁵ + 44x⁴ − 20x³ − 75x² + 86x − 45
```

Kiểm tra từng cột (người tổng hợp): x⁴: 24 + 20 = 44; x³: −30 + 28 − 18 = −20; x²: −35 − 40 = −75; x: 50 + 36 = 86. Đúng như sách.

Một cách viết khác cho tích C(x):

```text
C(x) = Σⱼ₌₀²ⁿ⁻² cⱼ xʲ                                                 (30.1)
cⱼ   = Σₖ₌₀ʲ aₖ bⱼ₋ₖ                                                 (30.2)
```

(hiểu ngầm aₖ = 0 và bₖ = 0 khi k ≥ n). Lưu ý degree(C) = degree(A) + degree(B), nên nếu A có cận bậc nₐ và B có cận bậc n_b thì C có cận bậc nₐ + n_b − 1. Vì một đa thức có cận bậc k cũng có cận bậc k + 1, sách thường nói gọn rằng tích C có cận bậc nₐ + n_b.

#### Dàn ý chương (Chapter outline)

Mục 30.1 trình bày hai cách biểu diễn đa thức: biểu diễn hệ số và biểu diễn điểm–giá trị. Các phương pháp nhân thẳng — công thức (30.1) và (30.2) — tốn Θ(n²) khi đa thức ở dạng hệ số, nhưng chỉ Θ(n) khi ở dạng điểm–giá trị. Tuy nhiên ta có thể nhân đa thức ở dạng hệ số chỉ trong Θ(n lg n) bằng cách chuyển qua lại giữa hai dạng. Để thấy vì sao cách này hiệu quả, trước hết phải nghiên cứu các căn phức của đơn vị (Mục 30.2). Sau đó dùng FFT và FFT ngược, cũng ở Mục 30.2, để thực hiện các phép chuyển. Mục 30.3 chỉ cách cài đặt FFT nhanh cả trong mô hình tuần tự lẫn song song.

Chương dùng số phức rất nhiều, và trong chương này ký hiệu i chỉ dùng để chỉ √−1 (không dùng i làm chỉ số vòng lặp).

### 2. Biểu diễn đa thức (30.1 Representing polynomials, trang 900–906)

Theo một nghĩa nào đó, biểu diễn hệ số và biểu diễn điểm–giá trị là tương đương: một đa thức ở dạng điểm–giá trị có duy nhất một bản tương ứng ở dạng hệ số. Mục này giới thiệu hai cách biểu diễn và chỉ cách kết hợp chúng để nhân hai đa thức cận bậc n trong Θ(n lg n).

#### Biểu diễn hệ số (Coefficient representation)

**Biểu diễn hệ số** của đa thức A(x) = Σⱼ₌₀ⁿ⁻¹ aⱼxʲ cận bậc n là vectơ hệ số a = (a₀, a₁, …, aₙ₋₁). Trong các phương trình ma trận của chương, vectơ thường được coi là vectơ cột.

Biểu diễn hệ số thuận tiện cho một số phép toán. Chẳng hạn phép **đánh giá** đa thức A(x) tại một điểm x₀ cho trước là tính giá trị A(x₀). Ta đánh giá được trong Θ(n) bằng **quy tắc Horner**:

```text
A(x₀) = a₀ + x₀(a₁ + x₀(a₂ + … + x₀(aₙ₋₂ + x₀(aₙ₋₁))…))
```

Viết thành vòng lặp (người tổng hợp): r = aₙ₋₁; với j = n − 2 xuống 0: r = aⱼ + x₀·r. Mỗi bước một phép nhân, một phép cộng, tổng n − 1 bước. Ví dụ A(x) = 6x³ + 7x² − 10x + 9 tại x₀ = 2: r = 6 → 7 + 2·6 = 19 → −10 + 2·19 = 28 → 9 + 2·28 = 65.

Tương tự, cộng hai đa thức có vectơ hệ số a và b tốn Θ(n): chỉ cần tạo vectơ c với cⱼ = aⱼ + bⱼ.

Còn nhân hai đa thức cận bậc n ở dạng hệ số theo (30.1)–(30.2) thì tốn Θ(n²), vì phải nhân mỗi hệ số của a với mỗi hệ số của b. Phép nhân ở dạng hệ số có vẻ khó hơn hẳn đánh giá hay cộng. Vectơ hệ số kết quả c cho bởi (30.2) còn được gọi là **tích chập** (convolution) của hai vectơ đầu vào a và b, ký hiệu c = a ⊗ b. Vì nhân đa thức và tính tích chập là các bài toán tính toán cơ bản, có tầm quan trọng thực tế lớn, chương này tập trung vào thuật toán hiệu quả cho chúng.

#### Biểu diễn điểm–giá trị (Point-value representation)

**Biểu diễn điểm–giá trị** của đa thức A(x) cận bậc n là một tập n **cặp điểm–giá trị**

```text
{ (x₀, y₀), (x₁, y₁), …, (xₙ₋₁, yₙ₋₁) }
```

sao cho mọi xₖ khác nhau và

```text
yₖ = A(xₖ)                                                           (30.3)
```

với k = 0, 1, …, n − 1. Một đa thức có rất nhiều biểu diễn điểm–giá trị, vì có thể dùng bất kỳ tập n điểm phân biệt nào làm cơ sở.

Tính một biểu diễn điểm–giá trị từ dạng hệ số về nguyên tắc là đơn giản: chọn n điểm phân biệt x₀, …, xₙ₋₁ rồi đánh giá A(xₖ) với k = 0, 1, …, n − 1. Dùng Horner, đánh giá tại n điểm tốn Θ(n²). Về sau ta sẽ thấy nếu chọn các điểm xₖ khéo léo thì phép tính này tăng tốc được thành Θ(n lg n).

Phép ngược của đánh giá — xác định dạng hệ số của đa thức từ một biểu diễn điểm–giá trị — gọi là **nội suy** (interpolation). Định lý sau cho thấy nội suy được xác định đúng đắn khi đa thức nội suy cần tìm có cận bậc bằng số cặp điểm–giá trị đã cho.

**Định lý 30.1 (Tính duy nhất của đa thức nội suy).** Với mọi tập {(x₀, y₀), (x₁, y₁), …, (xₙ₋₁, yₙ₋₁)} gồm n cặp điểm–giá trị sao cho các xₖ đôi một khác nhau, tồn tại duy nhất một đa thức A(x) cận bậc n sao cho yₖ = A(xₖ) với k = 0, 1, …, n − 1.

*Chứng minh.* Chứng minh dựa vào sự tồn tại nghịch đảo của một ma trận. Phương trình (30.3) tương đương với phương trình ma trận

```text
⎛ 1   x₀     x₀²     …  x₀ⁿ⁻¹   ⎞ ⎛ a₀   ⎞   ⎛ y₀   ⎞
⎜ 1   x₁     x₁²     …  x₁ⁿ⁻¹   ⎟ ⎜ a₁   ⎟   ⎜ y₁   ⎟
⎜ ⋮   ⋮      ⋮       ⋱  ⋮       ⎟ ⎜ ⋮    ⎟ = ⎜ ⋮    ⎟                (30.4)
⎝ 1   xₙ₋₁   xₙ₋₁²   …  xₙ₋₁ⁿ⁻¹ ⎠ ⎝ aₙ₋₁ ⎠   ⎝ yₙ₋₁ ⎠
```

Ma trận bên trái ký hiệu V(x₀, x₁, …, xₙ₋₁) và gọi là **ma trận Vandermonde**. Theo Problem D-1 (Phụ lục D), định thức của nó là

```text
Π_{0 ≤ j < k ≤ n−1} (xₖ − xⱼ)
```

nên theo Định lý D.5, nó khả nghịch (không suy biến) khi các xₖ khác nhau (mọi thừa số xₖ − xⱼ khác 0). Vậy ta giải được duy nhất các hệ số aⱼ từ biểu diễn điểm–giá trị:

```text
a = V(x₀, x₁, …, xₙ₋₁)⁻¹ y                                         ∎
```

Ví dụ (người tổng hợp): ba điểm (0, 1), (1, 3), (2, 7). Ma trận Vandermonde có các hàng (1, 0, 0), (1, 1, 1), (1, 2, 4), định thức (1 − 0)(2 − 0)(2 − 1) = 2. Giải hệ: a₀ = 1; a₀ + a₁ + a₂ = 3; a₀ + 2a₁ + 4a₂ = 7 ⇒ a₁ + a₂ = 2, 2a₁ + 4a₂ = 6 ⇒ a₂ = 1, a₁ = 1. Đa thức duy nhất là 1 + x + x².

Chứng minh của Định lý 30.1 mô tả một thuật toán nội suy: giải hệ phương trình tuyến tính (30.4). Dùng các thuật toán phân rã LU của Chương 28, ta giải hệ này trong O(n³).

Một thuật toán nội suy n điểm nhanh hơn dựa trên **công thức Lagrange**:

```text
              n−1        Π_{j≠k} (x − xⱼ)
A(x)   =      Σ    yₖ · ─────────────────                               (30.5)
             k=0         Π_{j≠k} (xₖ − xⱼ)
```

Có thể kiểm tra vế phải của (30.5) là một đa thức cận bậc n (mỗi tử số là tích của n − 1 thừa số bậc 1) thoả A(xₖ) = yₖ với mọi k: tại x = xₖ, số hạng thứ k bằng yₖ·1, còn mọi số hạng thứ k′ ≠ k có thừa số (xₖ − xₖ) = 0 ở tử. Exercise 30.1-5 hỏi cách tính các hệ số của A theo công thức Lagrange trong Θ(n²).

Áp dụng cho ví dụ trên (người tổng hợp): A(x) = 1·(x − 1)(x − 2)/((0 − 1)(0 − 2)) + 3·x(x − 2)/((1 − 0)(1 − 2)) + 7·x(x − 1)/((2 − 0)(2 − 1)) = (x² − 3x + 2)/2 − 3(x² − 2x) + 7(x² − x)/2 = x²(1/2 − 3 + 7/2) + x(−3/2 + 6 − 7/2) + 1 = x² + x + 1. Khớp với cách giải hệ.

Như vậy, đánh giá n điểm và nội suy là hai phép toán ngược nhau được xác định đúng đắn, chuyển qua lại giữa biểu diễn hệ số và một biểu diễn điểm–giá trị. Các thuật toán vừa mô tả cho hai bài toán này tốn Θ(n²).

*Chú thích chân trang 1 của sách:* nội suy là bài toán nổi tiếng khó xét về độ ổn định số. Dù các cách làm ở đây đúng về mặt toán học, sai khác nhỏ ở đầu vào hoặc sai số làm tròn trong quá trình tính có thể gây sai khác lớn ở kết quả.

**Cộng ở dạng điểm–giá trị.** Biểu diễn điểm–giá trị rất thuận tiện cho nhiều phép toán. Với phép cộng, nếu C(x) = A(x) + B(x) thì C(xₖ) = A(xₖ) + B(xₖ) tại mọi điểm xₖ. Chính xác hơn, nếu A có biểu diễn {(x₀, y₀), …, (xₙ₋₁, yₙ₋₁)} và B có biểu diễn {(x₀, y′₀), …, (xₙ₋₁, y′ₙ₋₁)} (chú ý A và B được đánh giá tại **cùng** n điểm), thì C có biểu diễn

```text
{ (x₀, y₀ + y′₀), (x₁, y₁ + y′₁), …, (xₙ₋₁, yₙ₋₁ + y′ₙ₋₁) }
```

Vậy cộng hai đa thức cận bậc n ở dạng điểm–giá trị tốn Θ(n).

**Nhân ở dạng điểm–giá trị.** Tương tự, nếu C(x) = A(x)B(x) thì C(xₖ) = A(xₖ)B(xₖ) tại mọi điểm xₖ, và ta có thể nhân từng điểm biểu diễn của A với biểu diễn của B để được biểu diễn của C. Nhưng có một vấn đề: degree(C) = degree(A) + degree(B); nếu A và B có cận bậc n thì C có cận bậc 2n. Biểu diễn chuẩn của A và B có n cặp mỗi đa thức; nhân với nhau ta được n cặp, nhưng cần 2n cặp để nội suy duy nhất một đa thức C cận bậc 2n (Exercise 30.1-4). Vì vậy phải bắt đầu với **biểu diễn điểm–giá trị mở rộng** (extended) gồm 2n cặp cho mỗi đa thức. Cho biểu diễn mở rộng của A là {(x₀, y₀), …, (x₂ₙ₋₁, y₂ₙ₋₁)} và của B là {(x₀, y′₀), …, (x₂ₙ₋₁, y′₂ₙ₋₁)}, thì C có biểu diễn

```text
{ (x₀, y₀y′₀), (x₁, y₁y′₁), …, (x₂ₙ₋₁, y₂ₙ₋₁y′₂ₙ₋₁) }
```

Từ hai đa thức ở dạng điểm–giá trị mở rộng, thời gian nhân để được dạng điểm–giá trị của kết quả là Θ(n), nhỏ hơn nhiều so với nhân ở dạng hệ số.

Ví dụ minh hoạ vì sao cần 2n điểm (người tổng hợp): A = 1 + x, B = 1 − x (cận bậc 2). Với chỉ 2 điểm x = 0 và x = 1: A cho 1, 2; B cho 1, 0; tích cho (0, 1), (1, 0). Đa thức cận bậc 2 duy nhất qua hai điểm này là 1 − x, nhưng tích thật là 1 − x². Thêm hai điểm x = −1 và x = 2: tích cho (−1, 0·2 = 0), (2, 3·(−1) = −3); bốn điểm (0, 1), (1, 0), (−1, 0), (2, −3) xác định đúng 1 − x² (kiểm tra 1 − 4 = −3).

**Đánh giá tại điểm mới.** Cuối cùng, xét việc đánh giá một đa thức cho ở dạng điểm–giá trị tại một điểm mới. Với bài toán này, sách không biết cách nào đơn giản hơn là đổi đa thức về dạng hệ số trước rồi đánh giá tại điểm mới.

#### Nhân nhanh đa thức ở dạng hệ số (Fast multiplication of polynomials in coefficient form)

Có thể dùng phép nhân thời gian tuyến tính ở dạng điểm–giá trị để tăng tốc phép nhân ở dạng hệ số không? Câu trả lời phụ thuộc vào việc có chuyển nhanh được từ dạng hệ số sang dạng điểm–giá trị (đánh giá) và ngược lại (nội suy) hay không.

Ta được dùng bất kỳ điểm nào làm điểm đánh giá, nhưng nếu chọn khéo thì chuyển đổi giữa hai biểu diễn chỉ tốn Θ(n lg n). Như Mục 30.2 sẽ cho thấy, nếu chọn "các căn phức của đơn vị" làm điểm đánh giá, ta tạo được biểu diễn điểm–giá trị bằng cách lấy **biến đổi Fourier rời rạc** (discrete Fourier transform, DFT) của vectơ hệ số. Phép ngược — nội suy — làm bằng "DFT ngược" của các cặp điểm–giá trị, cho ra vectơ hệ số. Mục 30.2 sẽ chỉ FFT thực hiện DFT và DFT ngược trong Θ(n lg n).

Chiến lược được vẽ trong Hình 30.1 của sách; vẽ lại như sau:

```text
                       DẠNG HỆ SỐ (hàng trên)
 ┌────────────────────┐   nhân thông thường        ┌────────────────────┐
 │ a₀, a₁, …, aₙ₋₁    │ ─────────────────────────▶ │ c₀, c₁, …, c₂ₙ₋₂   │
 │ b₀, b₁, …, bₙ₋₁    │   thời gian Θ(n²)          └────────────────────┘
 └────────────────────┘                                     ▲
          │ đánh giá                                        │ nội suy
          │ thời gian Θ(n lg n)                             │ thời gian Θ(n lg n)
          ▼                                                 │
 ┌────────────────────┐   nhân từng điểm           ┌────────────────────┐
 │ A(ω₂ₙ⁰),  B(ω₂ₙ⁰)  │ ─────────────────────────▶ │ C(ω₂ₙ⁰)            │
 │ A(ω₂ₙ¹),  B(ω₂ₙ¹)  │   thời gian Θ(n)           │ C(ω₂ₙ¹)            │
 │   ⋮          ⋮     │                            │   ⋮                │
 │ A(ω₂ₙ²ⁿ⁻¹),B(ω₂ₙ²ⁿ⁻¹)│                          │ C(ω₂ₙ²ⁿ⁻¹)         │
 └────────────────────┘                            └────────────────────┘
                    DẠNG ĐIỂM–GIÁ TRỊ (hàng dưới)
```

Các mũi tên từ trái sang phải là phép nhân; các ω₂ₙ là các căn phức bậc 2n của đơn vị.

Một chi tiết nhỏ liên quan đến cận bậc. Tích của hai đa thức cận bậc n có cận bậc 2n. Vì vậy trước khi đánh giá A và B, ta gấp đôi cận bậc của chúng lên 2n bằng cách thêm n hệ số bậc cao bằng 0. Vì các vectơ có 2n phần tử, ta dùng các căn phức bậc 2n của đơn vị, chính là các ω₂ₙ trong sơ đồ.

Với FFT trong tay, ta có thủ tục Θ(n lg n) sau để nhân hai đa thức A(x), B(x) cận bậc n, đầu vào và đầu ra ở dạng hệ số. Giả sử n là luỹ thừa của 2; luôn đạt được điều này bằng cách thêm hệ số 0 bậc cao.

1. **Gấp đôi cận bậc:** tạo biểu diễn hệ số của A(x) và B(x) như hai đa thức cận bậc 2n bằng cách thêm vào mỗi đa thức n hệ số 0 bậc cao.
2. **Đánh giá:** tính biểu diễn điểm–giá trị độ dài 2n của A(x) và B(x) bằng FFT bậc 2n trên mỗi đa thức. Các biểu diễn này chứa giá trị của hai đa thức tại các căn bậc 2n của đơn vị.
3. **Nhân từng điểm:** tính biểu diễn điểm–giá trị của C(x) = A(x)B(x) bằng cách nhân các giá trị với nhau theo từng điểm. Biểu diễn này chứa giá trị của C(x) tại mỗi căn bậc 2n của đơn vị.
4. **Nội suy:** tạo biểu diễn hệ số của C(x) bằng FFT trên 2n cặp điểm–giá trị để tính DFT ngược.

Bước 1 và 3 tốn Θ(n), bước 2 và 4 tốn Θ(n lg n). Vậy khi đã chỉ ra cách dùng FFT, ta chứng minh xong:

**Định lý 30.2.** Có thể nhân hai đa thức cận bậc n trong thời gian Θ(n lg n), với cả biểu diễn đầu vào và đầu ra ở dạng hệ số. ∎

**Ví dụ đầy đủ (người tổng hợp; dùng các công thức của Mục 30.2).** Nhân A(x) = 1 + 2x với B(x) = 3 + 4x; n = 2.

```text
Bước 1 (gấp đôi cận bậc lên 4):  a = (1, 2, 0, 0),  b = (3, 4, 0, 0)
Bước 2 (đánh giá tại căn bậc 4: ω₄⁰ = 1, ω₄¹ = i, ω₄² = −1, ω₄³ = −i):
        A(1) = 3,  A(i) = 1 + 2i,  A(−1) = −1,  A(−i) = 1 − 2i
        B(1) = 7,  B(i) = 3 + 4i,  B(−1) = −1,  B(−i) = 3 − 4i
Bước 3 (nhân từng điểm):
        C(1)  = 3·7 = 21
        C(i)  = (1 + 2i)(3 + 4i) = 3 + 4i + 6i + 8i² = −5 + 10i
        C(−1) = (−1)(−1) = 1
        C(−i) = (1 − 2i)(3 − 4i) = −5 − 10i
Bước 4 (nội suy: cⱼ = (1/4) Σₖ C(ω₄ᵏ)·ω₄^(−kj)):
        c₀ = (21 + (−5+10i) + 1 + (−5−10i))/4            = 12/4 = 3
        c₁ = (21 + (−5+10i)(−i) + 1·(−1) + (−5−10i)(i))/4
           = (21 + (−10 + 5i) − 1 + (10 − 5i))/4         = 40/4 = 10
        c₂ = (21 + (−5+10i)(−1) + 1 + (−5−10i)(−1))/4
           = (21 + 5 − 10i + 1 + 5 + 10i)/4              = 32/4 = 8
        c₃ = (21 + (−5+10i)(i) + 1·(−1) + (−5−10i)(−i))/4
           = (21 + (−10 − 5i) − 1 + (−10 + 5i))/4        = 0
Kết quả: C(x) = 3 + 10x + 8x²  (kiểm tra: (1+2x)(3+4x) = 3 + 4x + 6x + 8x²)
```

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: nhân đa thức nhanh là lõi của các thư viện số học độ chính xác tuỳ ý (nhân số nguyên hàng triệu chữ số, như khi tính hàng tỷ chữ số của π), của mật mã dựa trên lưới (phép nhân trong vành đa thức của các lược đồ hậu lượng tử dùng biến thể modulo của FFT gọi là NTT — chính là ý của Problem 30-6), và của các bộ lọc âm thanh dài (lọc FIR bằng tích chập nhanh).

### 3. DFT và FFT (30.2 The DFT and FFT, trang 906–915)

Mục 30.1 khẳng định rằng nếu dùng các căn phức của đơn vị thì đánh giá và nội suy được trong Θ(n lg n). Mục này định nghĩa căn phức của đơn vị, nghiên cứu tính chất của chúng, định nghĩa DFT, rồi chỉ ra FFT tính DFT và DFT ngược trong Θ(n lg n).

#### Căn phức của đơn vị (Complex roots of unity)

Một **căn phức bậc n của đơn vị** là số phức ω thoả

```text
ωⁿ = 1
```

Có đúng n căn phức bậc n của đơn vị: e^(2πik/n) với k = 0, 1, …, n − 1. Để hiểu công thức này, dùng định nghĩa hàm mũ của số phức:

```text
e^(iu) = cos(u) + i sin(u)
```

Các căn này nằm cách đều nhau trên đường tròn bán kính 1 tâm tại gốc của mặt phẳng phức. Hình 30.2 của sách vẽ tám giá trị ω₈⁰, ω₈¹, …, ω₈⁷ với ω₈ = e^(2πi/8); chép lại dưới dạng bảng và hình text:

| Căn | Góc | Giá trị | Vị trí trên hình |
|---|---|---|---|
| ω₈⁰ = ω₈⁸ | 0° | 1 | trên trục thực dương |
| ω₈¹ | 45° | (1 + i)/√2 ≈ 0,707 + 0,707i | góc phần tư thứ nhất |
| ω₈² | 90° | i | trên trục ảo dương |
| ω₈³ | 135° | (−1 + i)/√2 | góc phần tư thứ hai |
| ω₈⁴ | 180° | −1 | trên trục thực âm |
| ω₈⁵ | 225° | (−1 − i)/√2 | góc phần tư thứ ba |
| ω₈⁶ | 270° | −i | trên trục ảo âm |
| ω₈⁷ | 315° | (1 − i)/√2 | góc phần tư thứ tư |

```text
                     i (ω₈²)
             ω₈³      │      ω₈¹
                ╲     │     ╱
                  ╲   │   ╱
   −1 (ω₈⁴) ●───────── ┼ ─────────● 1 (ω₈⁰ = ω₈⁸)
                  ╱   │   ╲
                ╱     │     ╲
             ω₈⁵      │      ω₈⁷
                    −i (ω₈⁶)
   tám mũi tên từ gốc toạ độ, cách nhau 45°, cùng dài 1
```

Giá trị

```text
ωₙ = e^(2πi/n)                                                       (30.6)
```

là **căn chính bậc n của đơn vị** (principal nth root of unity); mọi căn phức bậc n khác đều là luỹ thừa của ωₙ. *Chú thích chân trang 2 của sách:* nhiều tác giả khác định nghĩa ωₙ = e^(−2πi/n); định nghĩa này hay dùng trong xử lý tín hiệu; toán học bên dưới về cơ bản giống nhau với cả hai định nghĩa.

n căn phức bậc n của đơn vị ωₙ⁰, ωₙ¹, …, ωₙⁿ⁻¹ tạo thành một **nhóm** với phép nhân (Mục 31.3). Nhóm này có cùng cấu trúc với nhóm cộng (Zₙ, +) modulo n, vì ωₙⁿ = ωₙ⁰ = 1 kéo theo ωₙʲωₙᵏ = ωₙ^(j+k) = ωₙ^((j+k) mod n). Tương tự ωₙ⁻¹ = ωₙⁿ⁻¹. Ví dụ với n = 8: ω₈⁵·ω₈⁶ = ω₈¹¹ = ω₈³; ω₈⁻¹ = ω₈⁷ = (1 − i)/√2, và thật vậy ((1 + i)/√2)((1 − i)/√2) = (1 − i²)/2 = 1.

Các bổ đề sau cho những tính chất cốt yếu của căn phức bậc n.

**Bổ đề 30.3 (Bổ đề triệt tiêu — cancellation lemma).** Với mọi số nguyên n ≥ 0, k ≥ 0 và d > 0 (sách ghi n ≥ 0; đúng ra phải là n > 0 để ωₙ có nghĩa — xem khối Lưu ý),

```text
ω_(dn)^(dk) = ωₙᵏ                                                     (30.7)
```

*Chứng minh.* Suy trực tiếp từ (30.6):

```text
ω_(dn)^(dk) = (e^(2πi/(dn)))^(dk) = (e^(2πi/n))^k = ωₙᵏ               ∎
```

Ví dụ: ω₁₂⁹ = ω₄³ = −i (d = 3).

**Hệ quả 30.4.** Với mọi số nguyên chẵn n > 0,

```text
ωₙ^(n/2) = ω₂ = −1
```

*Chứng minh.* Để làm Exercise 30.2-1. (Lời giải của người tổng hợp: theo bổ đề triệt tiêu với d = n/2, k = 1: ωₙ^(n/2) = ω_((n/2)·2)^((n/2)·1) = ω₂¹ = e^(πi) = cos π + i sin π = −1.) ∎

**Bổ đề 30.5 (Bổ đề chia đôi — halving lemma).** Nếu n > 0 chẵn, thì bình phương của n căn phức bậc n của đơn vị chính là n/2 căn phức bậc n/2 của đơn vị.

*Chứng minh.* Theo bổ đề triệt tiêu, (ωₙᵏ)² = ω_(n/2)ᵏ với mọi số nguyên không âm k. Nếu bình phương tất cả các căn bậc n, ta được mỗi căn bậc n/2 đúng hai lần, vì

```text
(ωₙ^(k+n/2))² = ωₙ^(2k+n)
             = ωₙ^(2k) · ωₙⁿ
             = ωₙ^(2k)
             = (ωₙᵏ)²
```

Vậy ωₙᵏ và ωₙ^(k+n/2) có cùng bình phương. Cũng có thể dùng Hệ quả 30.4: ωₙ^(n/2) = −1 kéo theo ωₙ^(k+n/2) = −ωₙᵏ, nên (ωₙ^(k+n/2))² = (ωₙᵏ)². ∎

Ví dụ n = 8: bình phương của ω₈⁰, …, ω₈⁷ lần lượt là ω₄⁰, ω₄¹, ω₄², ω₄³, ω₄⁰, ω₄¹, ω₄², ω₄³ = 1, i, −1, −i, 1, i, −1, −i.

Như sẽ thấy, bổ đề chia đôi là cốt lõi của cách chia để trị để chuyển giữa biểu diễn hệ số và biểu diễn điểm–giá trị, vì nó bảo đảm các bài toán con đệ quy chỉ lớn bằng một nửa.

**Bổ đề 30.6 (Bổ đề tổng — summation lemma).** Với mọi số nguyên n ≥ 1 và số nguyên k khác 0 không chia hết cho n,

```text
Σⱼ₌₀ⁿ⁻¹ (ωₙᵏ)ʲ = 0
```

*Chứng minh.* Công thức (A.5) (tổng cấp số nhân Σⱼ₌₀ⁿ⁻¹ xʲ = (xⁿ − 1)/(x − 1) với x ≠ 1) đúng cho số phức cũng như số thực, nên

```text
Σⱼ₌₀ⁿ⁻¹ (ωₙᵏ)ʲ = ((ωₙᵏ)ⁿ − 1)/(ωₙᵏ − 1)
              = ((ωₙⁿ)ᵏ − 1)/(ωₙᵏ − 1)
              = ((1)ᵏ − 1)/(ωₙᵏ − 1)
              = 0
```

Vì k không chia hết cho n, và ωₙᵏ = 1 chỉ khi k chia hết cho n, mẫu số khác 0. ∎

Ví dụ: n = 8, k = 2: tổng các luỹ thừa của ω₈² = i là 1 + i − 1 − i + 1 + i − 1 − i = 0. Với k = 8 (chia hết cho n) tổng là 8, không phải 0 — điều kiện của bổ đề là cần thiết.

#### DFT (The DFT)

Nhắc lại: ta muốn đánh giá đa thức A(x) = Σⱼ₌₀ⁿ⁻¹ aⱼxʲ cận bậc n tại ωₙ⁰, ωₙ¹, ωₙ², …, ωₙⁿ⁻¹ (tức tại n căn phức bậc n của đơn vị). *Chú thích chân trang 3 của sách:* độ dài n ở đây thực ra là cái mà Mục 30.1 gọi là 2n, vì ta đã gấp đôi cận bậc của các đa thức trước khi đánh giá; trong ngữ cảnh nhân đa thức, ta thật ra làm việc với các căn phức bậc 2n.

Giả sử A cho ở dạng hệ số a = (a₀, a₁, …, aₙ₋₁). Định nghĩa các kết quả yₖ, k = 0, 1, …, n − 1:

```text
yₖ = A(ωₙᵏ)
   = Σⱼ₌₀ⁿ⁻¹ aⱼ ωₙ^(kj)                                                (30.8)
```

Vectơ y = (y₀, y₁, …, yₙ₋₁) là **biến đổi Fourier rời rạc (DFT)** của vectơ hệ số a. Ta cũng viết y = DFTₙ(a).

Ví dụ tính thẳng (người tổng hợp), a = (0, 1, 2, 3), n = 4, ω₄ = i:

```text
y₀ = 0 + 1 + 2 + 3                           = 6
y₁ = 0 + 1·i + 2·i² + 3·i³ = i − 2 − 3i       = −2 − 2i
y₂ = 0 + 1·i² + 2·i⁴ + 3·i⁶ = −1 + 2 − 3      = −2
y₃ = 0 + 1·i³ + 2·i⁶ + 3·i⁹ = −i − 2 + 3i     = −2 + 2i
```

Tính thẳng như vậy tốn n² phép nhân (16 ở đây).

#### FFT (The FFT)

Dùng phương pháp gọi là **biến đổi Fourier nhanh (FFT)**, tận dụng các tính chất đặc biệt của căn phức của đơn vị, ta tính được DFTₙ(a) trong Θ(n lg n) thay vì Θ(n²) của cách thẳng. Suốt phần này giả sử n là một luỹ thừa chính xác của 2. Có những chiến lược cho kích thước không phải luỹ thừa của 2, nhưng nằm ngoài phạm vi sách.

Phương pháp FFT dùng chiến lược chia để trị, tách riêng các hệ số chỉ số chẵn và chỉ số lẻ của A(x) để định nghĩa hai đa thức mới A^[0](x) và A^[1](x) cận bậc n/2:

```text
A^[0](x) = a₀ + a₂x + a₄x² + … + aₙ₋₂x^(n/2−1)
A^[1](x) = a₁ + a₃x + a₅x² + … + aₙ₋₁x^(n/2−1)
```

A^[0] chứa mọi hệ số chỉ số chẵn của A (biểu diễn nhị phân của chỉ số tận cùng bằng 0), A^[1] chứa mọi hệ số chỉ số lẻ (biểu diễn nhị phân của chỉ số tận cùng bằng 1). Suy ra

```text
A(x) = A^[0](x²) + x·A^[1](x²)                                        (30.9)
```

nên bài toán đánh giá A(x) tại ωₙ⁰, ωₙ¹, …, ωₙⁿ⁻¹ quy về:

1. đánh giá hai đa thức cận bậc n/2 là A^[0](x) và A^[1](x) tại các điểm

   ```text
   (ωₙ⁰)², (ωₙ¹)², …, (ωₙⁿ⁻¹)²                                        (30.10)
   ```

2. rồi ghép kết quả theo (30.9).

Theo bổ đề chia đôi, danh sách (30.10) không gồm n giá trị khác nhau mà chỉ là n/2 căn phức bậc n/2 của đơn vị, mỗi căn xuất hiện đúng hai lần. Do đó ta đánh giá đệ quy A^[0] và A^[1] (cận bậc n/2) tại n/2 căn phức bậc n/2. Các bài toán con có đúng dạng bài toán gốc nhưng kích thước bằng một nửa. Ta đã chia được một phép tính DFTₙ n phần tử thành hai phép tính DFT_(n/2) n/2 phần tử. Phép chia này là cơ sở của thuật toán FFT đệ quy sau, tính DFT của vectơ n phần tử a = (a₀, a₁, …, aₙ₋₁), n là luỹ thừa của 2:

```text
RECURSIVE-FFT(a)
 1  n = a.length                  // n is a power of 2
 2  if n == 1
 3      return a
 4  ωₙ = e^(2πi/n)
 5  ω = 1
 6  a^[0] = (a₀, a₂, …, aₙ₋₂)
 7  a^[1] = (a₁, a₃, …, aₙ₋₁)
 8  y^[0] = RECURSIVE-FFT(a^[0])
 9  y^[1] = RECURSIVE-FFT(a^[1])
10  for k = 0 to n/2 − 1
11      yₖ = yₖ^[0] + ω·yₖ^[1]
12      yₖ₊₍ₙ/₂₎ = yₖ^[0] − ω·yₖ^[1]
13      ω = ω·ωₙ
14  return y                      // y is assumed to be a column vector
```

(Chú thích dòng 1: "n là luỹ thừa của 2"; dòng 14: "y được coi là vectơ cột".)

Thủ tục hoạt động như sau. **Dòng 2–3** là cơ sở đệ quy: DFT của một phần tử là chính phần tử đó, vì khi ấy

```text
y₀ = a₀·ω₁⁰ = a₀·1 = a₀
```

**Dòng 6–7** định nghĩa vectơ hệ số của A^[0] và A^[1]. **Dòng 4, 5 và 13** bảo đảm ω được cập nhật đúng sao cho mỗi khi thực hiện dòng 11–12 thì ω = ωₙᵏ. (Giữ giá trị ω chạy từ vòng này sang vòng sau tiết kiệm thời gian so với tính lại ωₙᵏ từ đầu ở mỗi vòng for.) **Dòng 8–9** thực hiện hai phép tính đệ quy DFT_(n/2), cho ra, với k = 0, 1, …, n/2 − 1,

```text
yₖ^[0] = A^[0](ω_(n/2)ᵏ)
yₖ^[1] = A^[1](ω_(n/2)ᵏ)
```

hay, vì ω_(n/2)ᵏ = ωₙ^(2k) theo bổ đề triệt tiêu,

```text
yₖ^[0] = A^[0](ωₙ^(2k))
yₖ^[1] = A^[1](ωₙ^(2k))
```

**Dòng 11–12** ghép kết quả của hai phép tính đệ quy. Với y₀, y₁, …, y_(n/2−1), dòng 11 cho

```text
yₖ = yₖ^[0] + ωₙᵏ yₖ^[1]
   = A^[0](ωₙ^(2k)) + ωₙᵏ A^[1](ωₙ^(2k))
   = A(ωₙᵏ)                                          (theo (30.9))
```

Với y_(n/2), y_(n/2+1), …, yₙ₋₁, đặt k = 0, 1, …, n/2 − 1, dòng 12 cho

```text
yₖ₊₍ₙ/₂₎ = yₖ^[0] − ωₙᵏ yₖ^[1]
        = yₖ^[0] + ωₙ^(k+n/2) yₖ^[1]                  (vì ωₙ^(k+n/2) = −ωₙᵏ)
        = A^[0](ωₙ^(2k)) + ωₙ^(k+n/2) A^[1](ωₙ^(2k))
        = A^[0](ωₙ^(2k+n)) + ωₙ^(k+n/2) A^[1](ωₙ^(2k+n))  (vì ωₙ^(2k+n) = ωₙ^(2k))
        = A(ωₙ^(k+n/2))                               (theo (30.9))
```

Vậy vectơ y do RECURSIVE-FFT trả về đúng là DFT của vectơ đầu vào a.

Dòng 11 và 12 nhân mỗi giá trị yₖ^[1] với ωₙᵏ, k = 0, 1, …, n/2 − 1. Dòng 11 cộng tích này vào yₖ^[0], dòng 12 trừ nó đi. Vì mỗi thừa số ωₙᵏ được dùng cả ở dạng dương lẫn âm, ta gọi các thừa số ωₙᵏ là **hệ số xoay** (twiddle factors).

**Thời gian chạy.** Không kể các lời gọi đệ quy, mỗi lần gọi tốn Θ(n), với n là độ dài vectơ đầu vào (tách chẵn–lẻ và vòng for đều tuyến tính). Truy hồi thời gian chạy là

```text
T(n) = 2T(n/2) + Θ(n)
     = Θ(n lg n)
```

(trường hợp 2 của định lý thợ, như sắp xếp trộn). Vậy có thể đánh giá một đa thức cận bậc n tại các căn phức bậc n của đơn vị trong Θ(n lg n) bằng FFT.

**Ví dụ chạy tay RECURSIVE-FFT (người tổng hợp), a = (0, 1, 2, 3):**

```text
RECURSIVE-FFT((0,1,2,3)), n = 4, ω₄ = i
├─ a^[0] = (0, 2): RECURSIVE-FFT, n = 2, ω₂ = −1
│   ├─ (0) trả về (0);  (2) trả về (2)
│   └─ k = 0, ω = 1:  y₀ = 0 + 1·2 = 2,  y₁ = 0 − 1·2 = −2   ⇒ y^[0] = (2, −2)
├─ a^[1] = (1, 3): tương tự ⇒ y^[1] = (1 + 3, 1 − 3) = (4, −2)
└─ ghép, n = 4:
    k = 0, ω = 1:  y₀ = 2 + 1·4 = 6          y₂ = 2 − 1·4 = −2
    k = 1, ω = i:  y₁ = −2 + i·(−2) = −2 − 2i y₃ = −2 − i·(−2) = −2 + 2i
Kết quả (6, −2 − 2i, −2, −2 + 2i) — khớp với cách tính thẳng.
```

Kiểm tra ý nghĩa của y^[0], y^[1]: A^[0](x) = 0 + 2x tại các căn bậc 2 là 1 và −1 cho 2 và −2; A^[1](x) = 1 + 3x cho 4 và −2. Đúng.

#### Nội suy tại các căn phức của đơn vị (Interpolation at the complex roots of unity)

Giờ hoàn tất sơ đồ nhân đa thức bằng cách chỉ ra cách nội suy — từ các giá trị tại các căn phức của đơn vị tìm lại đa thức — tức chuyển từ dạng điểm–giá trị về dạng hệ số. Ta nội suy bằng cách viết DFT thành phương trình ma trận rồi xem xét dạng của ma trận nghịch đảo.

Từ (30.4), có thể viết DFT thành tích ma trận y = Vₙa, với Vₙ là ma trận Vandermonde chứa các luỹ thừa thích hợp của ωₙ:

```text
⎛ y₀   ⎞   ⎛ 1   1        1          1          …   1             ⎞ ⎛ a₀   ⎞
⎜ y₁   ⎟   ⎜ 1   ωₙ       ωₙ²        ωₙ³        …   ωₙⁿ⁻¹         ⎟ ⎜ a₁   ⎟
⎜ y₂   ⎟   ⎜ 1   ωₙ²      ωₙ⁴        ωₙ⁶        …   ωₙ^(2(n−1))   ⎟ ⎜ a₂   ⎟
⎜ y₃   ⎟ = ⎜ 1   ωₙ³      ωₙ⁶        ωₙ⁹        …   ωₙ^(3(n−1))   ⎟ ⎜ a₃   ⎟
⎜ ⋮    ⎟   ⎜ ⋮   ⋮        ⋮          ⋮          ⋱   ⋮             ⎟ ⎜ ⋮    ⎟
⎝ yₙ₋₁ ⎠   ⎝ 1   ωₙⁿ⁻¹    ωₙ^(2(n−1)) ωₙ^(3(n−1)) … ωₙ^((n−1)(n−1)) ⎠ ⎝ aₙ₋₁ ⎠
```

Phần tử (k, j) của Vₙ là ωₙ^(kj), với j, k = 0, 1, …, n − 1. Số mũ của các phần tử của Vₙ tạo thành một bảng cửu chương. Ví dụ với n = 4, ω₄ = i:

```text
V₄ = ⎛ 1   1   1   1 ⎞
     ⎜ 1   i  −1  −i ⎟
     ⎜ 1  −1   1  −1 ⎟
     ⎝ 1  −i  −1   i ⎠
```

Với phép ngược, viết a = DFTₙ⁻¹(y), ta nhân y với ma trận Vₙ⁻¹, nghịch đảo của Vₙ.

**Định lý 30.7.** Với j, k = 0, 1, …, n − 1, phần tử (j, k) của Vₙ⁻¹ là ωₙ^(−kj)/n.

*Chứng minh.* Ta chỉ ra Vₙ⁻¹Vₙ = Iₙ, ma trận đơn vị n × n. Xét phần tử (j, j′) của Vₙ⁻¹Vₙ:

```text
[Vₙ⁻¹Vₙ]ⱼⱼ′ = Σₖ₌₀ⁿ⁻¹ (ωₙ^(−kj)/n)(ωₙ^(kj′))
           = Σₖ₌₀ⁿ⁻¹ ωₙ^(k(j′−j))/n
```

Tổng này bằng 1 nếu j′ = j (n số hạng, mỗi số hạng 1/n), và bằng 0 trong trường hợp còn lại theo bổ đề tổng (Bổ đề 30.6). Để áp dụng bổ đề tổng ta dựa vào −(n − 1) ≤ j′ − j ≤ n − 1, nên khi j′ ≠ j thì j′ − j khác 0 và không chia hết cho n. ∎

Có ma trận nghịch đảo Vₙ⁻¹, ta có DFTₙ⁻¹(y) cho bởi

```text
aⱼ = (1/n) Σₖ₌₀ⁿ⁻¹ yₖ ωₙ^(−kj)                                         (30.11)
```

với j = 0, 1, …, n − 1. So sánh (30.8) và (30.11): nếu sửa thuật toán FFT để đổi vai a và y, thay ωₙ bằng ωₙ⁻¹, và chia mỗi phần tử của kết quả cho n, ta tính được DFT ngược (Exercise 30.2-4). Vậy DFTₙ⁻¹ cũng tính được trong Θ(n lg n).

Kiểm tra (người tổng hợp) với y = (6, −2 − 2i, −2, −2 + 2i), ω₄⁻¹ = −i:

```text
a₀ = (6 + (−2−2i) + (−2) + (−2+2i))/4                   = 0/4 = 0
a₁ = (6 + (−2−2i)(−i) + (−2)(−1) + (−2+2i)(i))/4
   = (6 + (2i − 2) + 2 + (−2i − 2))/4                    = 4/4 = 1
a₂ = (6 + (−2−2i)(−1) + (−2)(1) + (−2+2i)(−1))/4
   = (6 + 2 + 2i − 2 + 2 − 2i)/4                         = 8/4 = 2
a₃ = (6 + (−2−2i)(i) + (−2)(−1) + (−2+2i)(−i))/4
   = (6 + (−2i + 2) + 2 + (2i + 2))/4                    = 12/4 = 3
```

Ra lại (0, 1, 2, 3).

Như vậy, nhờ FFT và FFT ngược, ta chuyển được một đa thức cận bậc n qua lại giữa biểu diễn hệ số và một biểu diễn điểm–giá trị trong Θ(n lg n). Trong ngữ cảnh nhân đa thức, ta đã chứng minh:

**Định lý 30.8 (Định lý tích chập — convolution theorem).** Với hai vectơ a và b bất kỳ độ dài n, n là luỹ thừa của 2,

```text
a ⊗ b = DFT₂ₙ⁻¹( DFT₂ₙ(a) · DFT₂ₙ(b) )
```

trong đó a và b được đệm thêm các số 0 tới độ dài 2n, và "·" chỉ tích từng thành phần của hai vectơ 2n phần tử. ∎

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hầu như mọi thư viện tính toán số (NumPy, FFTW, cuFFT trên GPU) đều cung cấp FFT với quy ước dấu e^(−2πi/n) của xử lý tín hiệu (như chú thích chân trang 2 nói), nên khi chuyển công thức của sách sang thư viện cần đổi vai của DFT và DFT ngược hoặc liên hợp phức. Hàm "convolve" hay "fftconvolve" của các thư viện xử lý tín hiệu chính là Định lý 30.8.

### 4. Cài đặt FFT hiệu quả (30.3 Efficient FFT implementations, trang 915–920)

Vì các ứng dụng thực tế của DFT, như xử lý tín hiệu, đòi tốc độ tối đa, mục này xem xét hai cài đặt FFT hiệu quả. Trước hết là phiên bản lặp của FFT, chạy Θ(n lg n) nhưng có thể có hằng số ẩn trong Θ nhỏ hơn bản đệ quy của Mục 30.2. (Tuỳ cài đặt cụ thể, bản đệ quy có thể dùng bộ nhớ đệm phần cứng hiệu quả hơn.) Sau đó dùng chính các nhận xét dẫn tới bản lặp để thiết kế một mạch FFT song song hiệu quả.

#### Cài đặt FFT dạng lặp (An iterative FFT implementation)

Trước hết, vòng for ở dòng 10–13 của RECURSIVE-FFT tính giá trị ωₙᵏyₖ^[1] hai lần. Theo thuật ngữ trình biên dịch, giá trị như vậy gọi là **biểu thức con chung** (common subexpression). Có thể sửa vòng lặp để chỉ tính nó một lần, lưu vào biến tạm t:

```text
for k = 0 to n/2 − 1
    t = ω·yₖ^[1]
    yₖ = yₖ^[0] + t
    yₖ₊₍ₙ/₂₎ = yₖ^[0] − t
    ω = ω·ωₙ
```

Phép toán trong vòng này — nhân hệ số xoay ω = ωₙᵏ với yₖ^[1], lưu tích vào t, rồi cộng và trừ t với yₖ^[0] — gọi là **phép con bướm** (butterfly operation). Hình 30.3 của sách vẽ nó theo hai cách; mô tả lại:

```text
(a) Dạng đầy đủ:
    yₖ^[0] ──────────────●─────────────(+)──▶ yₖ^[0] + ωₙᵏ·yₖ^[1]
                          ╲           ╱
                            ╲       ╱
                              ╲   ╱
                                ╳
                              ╱   ╲
                            ╱       ╲
    ωₙᵏ ──▶(×)──────────●╱           ╲──(−)──▶ yₖ^[0] − ωₙᵏ·yₖ^[1]
    yₖ^[1] ──▶┘
    Hai giá trị vào từ bên trái; hệ số xoay ωₙᵏ nhân với yₖ^[1] (nút ×);
    tổng (nút +) và hiệu (nút −) đi ra bên phải. Hai đường chéo bắt chéo
    nhau trông như cánh bướm.

(b) Dạng rút gọn (dùng trong mạch song song):
    yₖ^[0] ──▶┌───────┐──▶ yₖ^[0] + ωₙᵏ·yₖ^[1]
              │   ╳   │
    ωₙᵏ ─────▶│       │
    yₖ^[1] ──▶└───────┘──▶ yₖ^[0] − ωₙᵏ·yₖ^[1]
    một hộp chữ nhật có dấu chéo, hai dây vào, một hệ số xoay, hai dây ra
```

Giờ ta làm cho FFT có cấu trúc lặp thay vì đệ quy. Hình 30.4 của sách xếp các vectơ đầu vào của các lời gọi đệ quy trong một lần gọi RECURSIVE-FFT thành cây, với lời gọi đầu tiên có n = 8. Cây có một nút cho mỗi lời gọi, gắn nhãn là vectơ đầu vào tương ứng; mỗi lời gọi tạo hai lời gọi đệ quy, trừ khi nhận vectơ một phần tử; lời gọi thứ nhất (a^[0]) là con trái, lời gọi thứ hai (a^[1]) là con phải. Vẽ lại:

```text
                       (a0,a1,a2,a3,a4,a5,a6,a7)
                ┌──────────────┴──────────────┐
          (a0,a2,a4,a6)                 (a1,a3,a5,a7)
          ┌─────┴─────┐                 ┌─────┴─────┐
       (a0,a4)     (a2,a6)           (a1,a5)     (a3,a7)
       ┌──┴──┐     ┌──┴──┐           ┌──┴──┐     ┌──┴──┐
     (a0)  (a4)  (a2)  (a6)        (a1)  (a5)  (a3)  (a7)
```

Nhìn cây, nếu xếp được các phần tử của vectơ ban đầu a theo thứ tự chúng xuất hiện ở các lá, ta có thể lần theo việc thực hiện RECURSIVE-FFT nhưng từ dưới lên thay vì từ trên xuống. Trước hết lấy các phần tử theo cặp, tính DFT của mỗi cặp bằng một phép con bướm, và thay cặp bằng DFT của nó. Khi đó vectơ chứa n/2 DFT 2 phần tử. Tiếp theo lấy n/2 DFT này theo cặp và tính DFT của bốn phần tử mà chúng đến từ đó bằng hai phép con bướm, thay hai DFT 2 phần tử bằng một DFT 4 phần tử. Vectơ khi đó chứa n/4 DFT 4 phần tử. Tiếp tục như vậy cho tới khi vectơ chứa hai DFT (n/2) phần tử, ghép chúng bằng n/2 phép con bướm thành DFT n phần tử cuối cùng.

Để biến cách làm từ dưới lên này thành mã, dùng mảng A[0..n − 1] ban đầu chứa các phần tử của a theo thứ tự lá của cây (thứ tự này gọi là hoán vị đảo bit, sẽ bàn sau). Vì phải ghép các DFT ở mỗi tầng của cây, dùng biến s đếm tầng, từ 1 (ở đáy, ghép các cặp thành DFT 2 phần tử) tới lg n (ở đỉnh, ghép hai DFT (n/2) phần tử thành kết quả cuối). Thuật toán có cấu trúc:

```text
1  for s = 1 to lg n
2      for k = 0 to n − 1 by 2ˢ
3          combine the two 2ˢ⁻¹-element DFTs in
               A[k .. k + 2ˢ⁻¹ − 1] and A[k + 2ˢ⁻¹ .. k + 2ˢ − 1]
               into one 2ˢ-element DFT in A[k .. k + 2ˢ − 1]
```

(Dòng 3: "ghép hai DFT 2ˢ⁻¹ phần tử nằm trong A[k..k + 2ˢ⁻¹ − 1] và A[k + 2ˢ⁻¹..k + 2ˢ − 1] thành một DFT 2ˢ phần tử trong A[k..k + 2ˢ − 1]".)

Viết thân vòng (dòng 3) thành pseudocode chính xác hơn: chép vòng for của RECURSIVE-FFT, đồng nhất y^[0] với A[k..k + 2ˢ⁻¹ − 1] và y^[1] với A[k + 2ˢ⁻¹..k + 2ˢ − 1]. Hệ số xoay trong mỗi con bướm phụ thuộc s; nó là một luỹ thừa của ω_m với m = 2ˢ (biến m chỉ để dễ đọc). Thêm biến tạm u để làm phép con bướm tại chỗ. Thay dòng 3 bằng thân vòng, ta được pseudocode dưới đây, cũng là cơ sở cho cài đặt song song về sau. Mã gọi trước thủ tục phụ BIT-REVERSE-COPY(a, A) để chép vectơ a vào mảng A theo thứ tự ban đầu cần thiết.

```text
ITERATIVE-FFT(a)
 1  BIT-REVERSE-COPY(a, A)
 2  n = a.length                  // n is a power of 2
 3  for s = 1 to lg n
 4      m = 2ˢ
 5      ω_m = e^(2πi/m)
 6      for k = 0 to n − 1 by m
 7          ω = 1
 8          for j = 0 to m/2 − 1
 9              t = ω·A[k + j + m/2]
10              u = A[k + j]
11              A[k + j] = u + t
12              A[k + j + m/2] = u − t
13              ω = ω·ω_m
14  return A
```

Giải thích: dòng 3 duyệt các tầng; dòng 4–5 tính kích thước khối m và căn chính bậc m; dòng 6 duyệt các khối A[k..k + m − 1]; dòng 7–13 ghép nửa trái (đóng vai y^[0]) và nửa phải (đóng vai y^[1]) của khối bằng m/2 con bướm, ω chạy qua ω_m⁰, ω_m¹, …, ω_m^(m/2−1). Nhờ biến u, giá trị cũ A[k + j] được giữ lại trước khi bị ghi đè, nên mọi thứ làm tại chỗ.

**Hoán vị đảo bit.** BIT-REVERSE-COPY đưa các phần tử của a vào A theo thứ tự mong muốn thế nào? Thứ tự các lá trong cây là một **hoán vị đảo bit** (bit-reversal permutation): nếu rev(k) là số nguyên lg n bit tạo bằng cách đảo thứ tự các bit trong biểu diễn nhị phân của k, ta muốn đặt aₖ vào ô A[rev(k)]. Trong cây trên, các lá theo thứ tự 0, 4, 2, 6, 1, 5, 3, 7; dãy này ở dạng nhị phân là 000, 100, 010, 110, 001, 101, 011, 111, và khi đảo bit mỗi giá trị ta được 000, 001, 010, 011, 100, 101, 110, 111 — tức 0, 1, …, 7 theo thứ tự.

| vị trí trong A | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|---|
| nhị phân của vị trí | 000 | 001 | 010 | 011 | 100 | 101 | 110 | 111 |
| đảo bit = chỉ số k của aₖ | 000 | 100 | 010 | 110 | 001 | 101 | 011 | 111 |
| phần tử đặt vào | a₀ | a₄ | a₂ | a₆ | a₁ | a₅ | a₃ | a₇ |

Lý do tổng quát: ở tầng đỉnh của cây, các chỉ số có bit thấp nhất bằng 0 đi vào cây con trái, có bit thấp nhất bằng 1 đi vào cây con phải. Bỏ bit thấp nhất ở mỗi tầng và tiếp tục xuống cây, ta được ở các lá đúng thứ tự cho bởi hoán vị đảo bit.

Vì tính rev(k) dễ, thủ tục BIT-REVERSE-COPY đơn giản:

```text
BIT-REVERSE-COPY(a, A)
1  n = a.length
2  for k = 0 to n − 1
3      A[rev(k)] = aₖ
```

**Thời gian chạy.** Cài đặt FFT lặp chạy Θ(n lg n). Lời gọi BIT-REVERSE-COPY(a, A) chắc chắn chạy O(n lg n), vì lặp n lần và đảo một số nguyên từ 0 tới n − 1, có lg n bit, trong O(lg n). (Trong thực tế, vì thường biết trước giá trị n ban đầu, ta có thể viết sẵn bảng ánh xạ k sang rev(k), làm BIT-REVERSE-COPY chạy Θ(n) với hằng số ẩn nhỏ. Hoặc dùng bộ đếm nhị phân đảo khéo léo có phân tích khấu hao ở Problem 17-1.) Để hoàn tất chứng minh ITERATIVE-FFT chạy Θ(n lg n), ta chỉ ra L(n), số lần thân vòng trong cùng (dòng 8–13) được thực hiện, là Θ(n lg n). Vòng for dòng 6–13 lặp n/m = n/2ˢ lần với mỗi giá trị s, và vòng trong cùng dòng 8–13 lặp m/2 = 2ˢ⁻¹ lần. Vậy

```text
L(n) = Σₛ₌₁^(lg n) (n/2ˢ)·2ˢ⁻¹
     = Σₛ₌₁^(lg n) n/2
     = Θ(n lg n)
```

Chính xác là (n/2) lg n con bướm; với n = 8 là 4 · 3 = 12.

**Ví dụ chạy tay ITERATIVE-FFT (người tổng hợp), a = (0, 1, 2, 3), n = 4:**

```text
BIT-REVERSE-COPY: rev(0)=0, rev(1)=2, rev(2)=1, rev(3)=3
                  A = (a₀, a₂, a₁, a₃) = (0, 2, 1, 3)
s = 1, m = 2, ω₂ = −1:
   k = 0: j = 0, ω = 1: t = 1·A[1] = 2, u = A[0] = 0 ⇒ A[0] = 2,  A[1] = −2
   k = 2: j = 0, ω = 1: t = A[3] = 3,   u = A[2] = 1 ⇒ A[2] = 4,  A[3] = −2
   A = (2, −2, 4, −2)
s = 2, m = 4, ω₄ = i:
   k = 0: j = 0, ω = 1: t = A[2] = 4,     u = 2  ⇒ A[0] = 6,       A[2] = −2
          j = 1, ω = i: t = i·A[3] = −2i, u = −2 ⇒ A[1] = −2 − 2i, A[3] = −2 + 2i
   A = (6, −2 − 2i, −2, −2 + 2i)
```

Khớp với RECURSIVE-FFT và với tính thẳng.

#### Mạch FFT song song (A parallel FFT circuit)

Có thể khai thác nhiều tính chất đã cho phép cài đặt FFT lặp hiệu quả để có một thuật toán song song hiệu quả cho FFT. Sách diễn tả thuật toán FFT song song dưới dạng một **mạch**. Hình 30.5 của sách vẽ mạch FFT song song tính FFT trên n = 8 đầu vào. Mô tả lại:

```text
 dây │ đầu vào sau    │ tầng s = 1        │ tầng s = 2        │ tầng s = 3        │ đầu ra
     │ hoán vị đảo bit│ (m = 2)           │ (m = 4)           │ (m = 8)           │
 ────┼────────────────┼───────────────────┼───────────────────┼───────────────────┼───────
  0  │ a₀             │ cặp với dây 1, ω₂⁰│ cặp với dây 2, ω₄⁰│ cặp với dây 4, ω₈⁰│ y₀
  1  │ a₄             │ cặp với dây 0     │ cặp với dây 3, ω₄¹│ cặp với dây 5, ω₈¹│ y₁
  2  │ a₂             │ cặp với dây 3, ω₂⁰│ cặp với dây 0     │ cặp với dây 6, ω₈²│ y₂
  3  │ a₆             │ cặp với dây 2     │ cặp với dây 1     │ cặp với dây 7, ω₈³│ y₃
  4  │ a₁             │ cặp với dây 5, ω₂⁰│ cặp với dây 6, ω₄⁰│ cặp với dây 0     │ y₄
  5  │ a₅             │ cặp với dây 4     │ cặp với dây 7, ω₄¹│ cặp với dây 1     │ y₅
  6  │ a₃             │ cặp với dây 7, ω₂⁰│ cặp với dây 4     │ cặp với dây 2     │ y₆
  7  │ a₇             │ cặp với dây 6     │ cặp với dây 5     │ cặp với dây 3     │ y₇
 (hệ số xoay ghi ở dây trên của mỗi con bướm; dây trên nhận tổng, dây dưới
  nhận hiệu; tám dây chạy ngang từ trái sang phải qua ba cột con bướm)
```

Cùng nội dung, liệt kê theo từng con bướm (mỗi con bướm nối hai dây và dùng một hệ số xoay):

| Tầng | Nhóm (giá trị k) | Con bướm: (dây trên, dây dưới) — hệ số xoay |
|---|---|---|
| s = 1 (m = 2) | k = 0, 2, 4, 6 | (0, 1) — ω₂⁰; (2, 3) — ω₂⁰; (4, 5) — ω₂⁰; (6, 7) — ω₂⁰ |
| s = 2 (m = 4) | k = 0 | (0, 2) — ω₄⁰; (1, 3) — ω₄¹ |
| s = 2 (m = 4) | k = 4 | (4, 6) — ω₄⁰; (5, 7) — ω₄¹ |
| s = 3 (m = 8) | k = 0 | (0, 4) — ω₈⁰; (1, 5) — ω₈¹; (2, 6) — ω₈²; (3, 7) — ω₈³ |

Bên trái mạch là các dây bắt chéo thực hiện hoán vị đảo bit: dây 0 nhận a₀, dây 1 nhận a₄, dây 2 nhận a₂, dây 3 nhận a₆, dây 4 nhận a₁, dây 5 nhận a₅, dây 6 nhận a₃, dây 7 nhận a₇ (a₀, a₂, a₅, a₇ đi thẳng; a₁ và a₄ đổi chỗ, a₃ và a₆ đổi chỗ). Dây thứ k bên phải cho ra yₖ.

Chú thích của hình nói: mỗi phép con bướm nhận giá trị trên hai dây cùng một hệ số xoay, và cho ra giá trị trên hai dây. Các tầng con bướm được đánh số tương ứng với các vòng lặp của vòng ngoài cùng trong ITERATIVE-FFT. Chỉ dây trên cùng và dây dưới cùng đi qua một con bướm mới tương tác với nó; các dây đi xuyên qua phần giữa của một con bướm không ảnh hưởng tới con bướm đó và cũng không bị nó thay đổi giá trị. Ví dụ, con bướm trên cùng ở tầng 2 không liên quan gì tới dây 1 (dây có đầu ra y₁); đầu vào và đầu ra của nó chỉ nằm trên dây 0 và dây 2 (đầu ra y₀ và y₂). Mạch có độ sâu Θ(lg n) và tổng cộng thực hiện Θ(n lg n) phép con bướm.

Mạch bắt đầu bằng một hoán vị đảo bit của các đầu vào, tiếp theo là lg n tầng, mỗi tầng gồm n/2 con bướm thực hiện song song. **Độ sâu** của mạch — số phần tử tính toán lớn nhất nằm giữa một đầu ra và một đầu vào có thể ảnh hưởng tới nó — vì vậy là Θ(lg n).

Phần bên trái nhất của mạch làm hoán vị đảo bit, phần còn lại mô phỏng thủ tục ITERATIVE-FFT. Vì mỗi vòng lặp của vòng for ngoài cùng thực hiện n/2 phép con bướm độc lập, mạch làm chúng song song. Giá trị s ở mỗi vòng lặp của ITERATIVE-FFT ứng với một tầng con bướm trong mạch. Với s = 1, 2, …, lg n, tầng s gồm n/2ˢ nhóm con bướm (ứng với mỗi giá trị k trong ITERATIVE-FFT), mỗi nhóm 2ˢ⁻¹ con bướm (ứng với mỗi giá trị j trong ITERATIVE-FFT). Các con bướm trong mạch ứng với các phép con bướm của vòng trong cùng (dòng 9–12 của ITERATIVE-FFT). Các hệ số xoay dùng trong con bướm cũng ứng với các hệ số trong ITERATIVE-FFT: ở tầng s dùng ω_m⁰, ω_m¹, …, ω_m^(m/2−1), với m = 2ˢ.

Lần theo mạch trên ví dụ (0, 2, 3, −1, 4, 5, 7, 9) của Exercise 30.3-1 cho giá trị trên từng dây sau mỗi tầng (phần Bài tập).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: sơ đồ "lg n tầng con bướm" là kiến trúc của các khối FFT phần cứng trong bộ xử lý tín hiệu số, modem OFDM (Wi-Fi, 4G/5G thực hiện FFT/IFFT cho mỗi ký hiệu truyền) và các GPU. Mẫu truy cập "cặp chỉ số cách nhau 2ˢ⁻¹" của ITERATIVE-FFT cũng xuất hiện nguyên vẹn trong mạng sắp xếp bitonic và trong các phép biến đổi nhanh khác (biến đổi Walsh–Hadamard dùng trong lập trình thi đấu cho tích chập XOR).

## Bài tập và bài toán cuối chương

### Bài tập Mục 30.1 (trang 905–906)

- **30.1-1:** Nhân A(x) = 7x³ − x² + x − 10 và B(x) = 8x³ − 6x + 3 bằng công thức (30.1) và (30.2). *Lời giải của người tổng hợp:* a = (−10, 1, −1, 7), b = (3, −6, 0, 8).

  ```text
  c₀ = a₀b₀                         = −30
  c₁ = a₀b₁ + a₁b₀ = 60 + 3         = 63
  c₂ = a₀b₂ + a₁b₁ + a₂b₀ = 0 − 6 − 3        = −9
  c₃ = a₀b₃ + a₁b₂ + a₂b₁ + a₃b₀ = −80 + 0 + 6 + 21 = −53
  c₄ = a₁b₃ + a₂b₂ + a₃b₁ = 8 + 0 − 42       = −34
  c₅ = a₂b₃ + a₃b₂ = −8 + 0         = −8
  c₆ = a₃b₃                         = 56
  C(x) = 56x⁶ − 8x⁵ − 34x⁴ − 53x³ − 9x² + 63x − 30
  ```
  Kiểm tra tại x = 1: A(1) = −3, B(1) = 5, tích −15; C(1) = 56 − 8 − 34 − 53 − 9 + 63 − 30 = −15. Đúng.
- **30.1-2:** Một cách khác đánh giá A(x) cận bậc n tại x₀ là chia A(x) cho (x − x₀), được thương q(x) cận bậc n − 1 và số dư r với A(x) = q(x)(x − x₀) + r; hiển nhiên A(x₀) = r. Chỉ cách tính r và các hệ số của q trong Θ(n) từ x₀ và các hệ số của A. *Lời giải của người tổng hợp (chia Horner, "synthetic division"):* đặt qₙ₋₂ = aₙ₋₁; với j = n − 2 xuống 1: qⱼ₋₁ = aⱼ + x₀qⱼ; cuối cùng r = a₀ + x₀q₀. Đây chính là quy tắc Horner, các giá trị trung gian là hệ số của thương. Ví dụ A(x) = 6x³ + 7x² − 10x + 9, x₀ = 2: q₂ = 6, q₁ = 7 + 12 = 19, q₀ = −10 + 38 = 28, r = 9 + 56 = 65; tức A(x) = (6x² + 19x + 28)(x − 2) + 65.
- **30.1-3:** Từ biểu diễn điểm–giá trị của A(x) = Σⱼ aⱼxʲ, suy ra biểu diễn điểm–giá trị của A^rev(x) = Σⱼ₌₀ⁿ⁻¹ aₙ₋₁₋ⱼxʲ (hệ số đảo ngược), giả sử không điểm nào bằng 0. *Lời giải của người tổng hợp:* A^rev(x) = xⁿ⁻¹A(1/x). Vậy từ các cặp (xₖ, yₖ) của A ta có các cặp (1/xₖ, yₖ/xₖⁿ⁻¹) của A^rev; các điểm 1/xₖ vẫn phân biệt. Ví dụ A = 1 + 2x, A^rev = 2 + x; cặp (2, 5) của A cho cặp (1/2, 5/2) của A^rev, và thật vậy 2 + 1/2 = 5/2.
- **30.1-4:** Chứng minh n cặp điểm–giá trị phân biệt là cần thiết để xác định duy nhất một đa thức cận bậc n: nếu cho ít hơn n cặp thì chúng không xác định duy nhất đa thức cận bậc n. (Gợi ý: dùng Định lý 30.1; nói gì được về một tập n − 1 cặp khi thêm một cặp tuỳ ý?) *Lời giải của người tổng hợp:* cho n − 1 cặp (nếu ít hơn thì thêm cặp tuỳ ý cho đủ n − 1). Chọn điểm x* khác mọi xₖ. Với mỗi giá trị y*, theo Định lý 30.1 có đúng một đa thức cận bậc n qua n − 1 cặp đã cho và (x*, y*). Các giá trị y* khác nhau cho các đa thức khác nhau (khác giá trị tại x*), nhưng tất cả đều khớp với n − 1 cặp ban đầu. Vậy có vô số đa thức cận bậc n khớp — không duy nhất.
- **30.1-5:** Chỉ cách dùng công thức Lagrange (30.5) để nội suy trong Θ(n²). (Gợi ý: trước hết tính biểu diễn hệ số của Πⱼ(x − xⱼ), rồi chia cho (x − xₖ) khi cần cho tử số của mỗi số hạng (Exercise 30.1-2); mỗi mẫu số tính được trong O(n).) *Lời giải của người tổng hợp:* (1) tính P(x) = Πⱼ₌₀ⁿ⁻¹ (x − xⱼ) bằng cách nhân lần lượt với từng (x − xⱼ), mỗi lần O(n), tổng O(n²); (2) với mỗi k, chia P(x) cho (x − xₖ) bằng chia Horner trong O(n), được tử số Nₖ(x) = Π_{j≠k}(x − xⱼ) (số dư bằng 0); (3) mẫu số dₖ = Π_{j≠k}(xₖ − xⱼ) tính trong O(n) (hoặc dₖ = Nₖ(xₖ)); (4) cộng (yₖ/dₖ)·Nₖ(x) vào kết quả, O(n). Tổng Θ(n²).
- **30.1-6:** Giải thích chỗ sai của cách "hiển nhiên" chia đa thức bằng biểu diễn điểm–giá trị, tức chia các giá trị y tương ứng. Bàn riêng trường hợp phép chia hết và không hết. *Lời giải của người tổng hợp:* (a) Chia hết, A = QB: tại mọi điểm B(xₖ) ≠ 0 thì Q(xₖ) = A(xₖ)/B(xₖ) đúng, nhưng nếu một điểm xₖ là nghiệm của B thì phép chia là 0/0, mất thông tin; ngoài ra phải chọn đủ điểm (cận bậc của Q nhỏ hơn A nên số điểm dư thì không sao, nhưng điểm rơi vào nghiệm của B thì phải bỏ và có thể không còn đủ). (b) Không chia hết, A = QB + R với R ≠ 0: các số A(xₖ)/B(xₖ) là giá trị của hàm hữu tỉ A/B, không phải của thương Q; nội suy chúng ra một đa thức nói chung không phải Q và không có ý nghĩa. Ví dụ A = x², B = x + 1 (Q = x − 1, R = 1): tại x = 0, 1 các giá trị là 0 và 1/2; nội suy ra x/2, khác Q = x − 1.
- **30.1-7:** Cho hai tập A, B, mỗi tập n số nguyên trong khoảng 0..10n. Muốn tính **tổng Descartes** C = {x + y : x ∈ A và y ∈ B} (các số trong C nằm trong 0..20n), tìm các phần tử của C và số lần mỗi phần tử được tạo thành như tổng của một phần tử A và một phần tử B, trong O(n lg n). (Gợi ý: biểu diễn A và B bằng đa thức bậc tối đa 10n.) *Lời giải của người tổng hợp:* đặt P_A(x) = Σ_{a∈A} xᵃ, P_B(x) = Σ_{b∈B} xᵇ (cận bậc 10n + 1). Hệ số của xᶜ trong P_A·P_B là số cặp (a, b) với a + b = c. Nhân bằng FFT trong O(n lg n) (độ dài 20n + 1, làm tròn lên luỹ thừa của 2). Ví dụ A = {1, 2}, B = {2, 3}: (x + x²)(x² + x³) = x³ + 2x⁴ + x⁵, nên C = {3, 4, 5}, trong đó 4 được tạo hai lần (1 + 3 và 2 + 2). Kết quả là số nguyên nên làm tròn đầu ra của FFT phức (hoặc dùng FFT modulo của Problem 30-6).

### Bài tập Mục 30.2 (trang 914–915)

- **30.2-1:** Chứng minh Hệ quả 30.4. (Lời giải ở phần Nội dung chi tiết: ωₙ^(n/2) = ω₂ = e^(πi) = −1 theo bổ đề triệt tiêu với d = n/2.)
- **30.2-2:** Tính DFT của vectơ (0, 1, 2, 3). *Đáp số (người tổng hợp, đã tính ba cách ở phần Nội dung chi tiết):* (6, −2 − 2i, −2, −2 + 2i).
- **30.2-3:** Làm Exercise 30.1-1 bằng sơ đồ Θ(n lg n). *Người tổng hợp:* A, B có cận bậc 4; đệm thành vectơ độ dài 8: a = (−10, 1, −1, 7, 0, 0, 0, 0), b = (3, −6, 0, 8, 0, 0, 0, 0); tính DFT₈(a), DFT₈(b) bằng FFT với ω₈ = (1 + i)/√2; nhân từng thành phần; DFT₈⁻¹ ra (−30, 63, −9, −53, −34, −8, 56, 0) — trùng kết quả ở 30.1-1 (hệ số thứ 8 bằng 0 vì tích chỉ có bậc 6). Ví dụ một thành phần: A(1) = −3, B(1) = 5, nên C(ω₈⁰) = −15; A(−1) = −10 − 1 − 1 − 7 = −19, B(−1) = 3 + 6 − 8 = 1, nên C(ω₈⁴) = −19 và thật vậy C(−1) = 56 + 8 − 34 + 53 − 9 − 63 − 30 = −19.
- **30.2-4:** Viết pseudocode tính DFTₙ⁻¹ trong Θ(n lg n). *Lời giải của người tổng hợp:*

  ```text
  INVERSE-FFT(y)
  1  n = y.length
  2  a = RECURSIVE-FFT-WITH-ROOT(y, e^(−2πi/n))
  3  for j = 0 to n − 1
  4      aⱼ = aⱼ / n
  5  return a

  RECURSIVE-FFT-WITH-ROOT(a, ω_root)      // như RECURSIVE-FFT, chỉ khác dòng 4
  1  n = a.length
  2  if n == 1
  3      return a
  4  ωₙ = ω_root                         // ở lời gọi gốc là e^(−2πi/n)
  5  ω = 1
  6  a^[0] = (a₀, a₂, …, aₙ₋₂);  a^[1] = (a₁, a₃, …, aₙ₋₁)
  7  y^[0] = RECURSIVE-FFT-WITH-ROOT(a^[0], ωₙ²)
  8  y^[1] = RECURSIVE-FFT-WITH-ROOT(a^[1], ωₙ²)
  9  for k = 0 to n/2 − 1
 10      yₖ = yₖ^[0] + ω·yₖ^[1]
 11      yₖ₊₍ₙ/₂₎ = yₖ^[0] − ω·yₖ^[1]
 12      ω = ω·ωₙ
 13  return y
  ```
  Đúng vì ωₙ⁻¹ cũng thoả bổ đề triệt tiêu, chia đôi (bình phương của nó là ω_(n/2)⁻¹) và ωₙ^(−n/2) = −1; phép chia cho n làm sau cùng, một lần, Θ(n).
- **30.2-5:** Mô tả tổng quát hoá FFT cho trường hợp n là luỹ thừa của 3; cho truy hồi thời gian và giải. *Lời giải của người tổng hợp:* tách hệ số theo chỉ số mod 3: A(x) = A^[0](x³) + x·A^[1](x³) + x²·A^[2](x³), mỗi A^[r] cận bậc n/3. Lập phương của n căn bậc n là n/3 căn bậc n/3 (mỗi căn ba lần). Đệ quy ba lần cỡ n/3, rồi với k = 0..n − 1: yₖ = y^[0]_(k mod n/3) + ωₙᵏ·y^[1]_(k mod n/3) + ωₙ^(2k)·y^[2]_(k mod n/3). Truy hồi T(n) = 3T(n/3) + Θ(n) = Θ(n log₃ n) = Θ(n lg n).
- **30.2-6 ★:** Thay vì làm FFT n phần tử trên trường số phức (n chẵn), dùng vành Zₘ các số nguyên modulo m, với m = 2^(tn/2) + 1 và t là số nguyên dương tuỳ ý. Dùng ω = 2ᵗ thay cho ωₙ làm căn chính bậc n của đơn vị modulo m. Chứng minh DFT và DFT ngược được xác định đúng đắn trong hệ này. *Lời giải của người tổng hợp (giả sử n là luỹ thừa của 2, như cả chương):* (1) ω^(n/2) = 2^(tn/2) = m − 1 ≡ −1 (mod m), nên ωⁿ ≡ 1. (2) Bổ đề tổng: với 0 < k < n, viết k = 2ˢk′ với k′ lẻ, s < lg n. Vì mọi j < n viết duy nhất dưới dạng nhị phân, Σⱼ₌₀ⁿ⁻¹ ω^(kj) = Π_{i=0}^{lg n−1} (1 + ω^(k·2ⁱ)); chọn i = lg n − 1 − s thì k·2ⁱ = k′·n/2, ω^(k′n/2) ≡ (−1)^(k′) = −1, thừa số đó bằng 0, nên tổng ≡ 0 (mod m). Lập luận này không cần chia cho ωᵏ − 1 (vốn có thể không khả nghịch trong vành). (3) n khả nghịch modulo m vì m lẻ và n là luỹ thừa của 2; ω khả nghịch vì ω·ωⁿ⁻¹ ≡ 1. (4) Như chứng minh Định lý 30.7, ma trận với phần tử ω^(−kj)/n là nghịch đảo của ma trận (ω^(kj)), nên DFT ngược tồn tại và tính được. (5) Bổ đề chia đôi vẫn đúng vì ω² = 2^(2t) và m = 2^((2t)(n/2)/2) + 1 — bài toán con cỡ n/2 với t′ = 2t sống trong cùng vành Zₘ. Ví dụ n = 4, t = 1: m = 2² + 1 = 5, ω = 2: 2¹, 2², 2³, 2⁴ ≡ 2, 4, 3, 1 (mod 5), và 1 + 2 + 4 + 3 = 10 ≡ 0.
- **30.2-7:** Cho danh sách z₀, z₁, …, zₙ₋₁ (có thể lặp), tìm hệ số của đa thức P(x) cận bậc n + 1 chỉ có nghiệm tại z₀, …, zₙ₋₁ (kể cả bội) trong O(n lg² n). (Gợi ý: P(x) có nghiệm zⱼ khi và chỉ khi P(x) là bội của (x − zⱼ).) *Lời giải của người tổng hợp:* P(x) = Πⱼ (x − zⱼ). Tính bằng chia để trị: nhân đệ quy nửa đầu và nửa sau, rồi nhân hai đa thức kết quả (bậc n/2) bằng FFT. T(n) = 2T(n/2) + O(n lg n) = O(n lg² n). (Nhân tuần tự từng thừa số sẽ tốn Θ(n²).)
- **30.2-8 ★:** **Biến đổi chirp** của vectơ a = (a₀, …, aₙ₋₁) là y với yₖ = Σⱼ₌₀ⁿ⁻¹ aⱼz^(kj), z là số phức bất kỳ; DFT là trường hợp riêng z = ωₙ. Chỉ cách tính biến đổi chirp trong O(n lg n) với mọi z. (Gợi ý: dùng đẳng thức yₖ = z^(k²/2) Σⱼ₌₀ⁿ⁻¹ (aⱼz^(j²/2))(z^(−(k−j)²/2)) để thấy biến đổi chirp là một tích chập.) *Lời giải của người tổng hợp:* vì kj = (k² + j² − (k − j)²)/2, nên z^(kj) = z^(k²/2)·z^(j²/2)·z^(−(k−j)²/2). Đặt uⱼ = aⱼz^(j²/2) (j = 0..n − 1) và vₗ = z^(−l²/2) với l = −(n − 1)..(n − 1) (dời chỉ số thành 0..2n − 2). Khi đó Σⱼ uⱼv_(k−j) là tích chập của u và v, tính bằng FFT trên vectơ độ dài khoảng 4n trong O(n lg n); nhân thêm z^(k²/2) mỗi đầu ra. (Cần cố định một nhánh của z^(1/2); mọi tích đều nhất quán khi dùng cùng w = √z và viết z^(l²/2) = w^(l²).) Theo hiểu biết của người tổng hợp, đây là thuật toán Bluestein, cho phép tính DFT với n bất kỳ (kể cả số nguyên tố) trong O(n lg n).

### Bài tập Mục 30.3 (trang 920)

- **30.3-1:** Chỉ cách ITERATIVE-FFT tính DFT của vectơ đầu vào (0, 2, 3, −1, 4, 5, 7, 9). *Lời giải của người tổng hợp (đã kiểm tra bằng máy với cách tính thẳng):*

  ```text
  BIT-REVERSE-COPY: A = (a₀, a₄, a₂, a₆, a₁, a₅, a₃, a₇) = (0, 4, 3, 7, 2, 5, −1, 9)
  s = 1 (m = 2, ω₂⁰ = 1): mỗi cặp (u, v) thành (u + v, u − v)
        A = (4, −4, 10, −4, 7, −3, 8, −10)
  s = 2 (m = 4, hệ số xoay 1 và i):
        khối 0: (4, −4, 10, −4): j=0: 4 ± 10 → 14, −6
                                 j=1: t = i·(−4) = −4i; −4 ± t → −4 − 4i, −4 + 4i
        khối 4: (7, −3, 8, −10): j=0: 7 ± 8 → 15, −1
                                 j=1: t = −10i; −3 ± t → −3 − 10i, −3 + 10i
        A = (14, −4 − 4i, −6, −4 + 4i, 15, −3 − 10i, −1, −3 + 10i)
  s = 3 (m = 8, hệ số xoay ω₈⁰ = 1, ω₈¹ = (1+i)/√2, ω₈² = i, ω₈³ = (−1+i)/√2):
        j=0: t = 15;                         14 ± 15 → y₀ = 29, y₄ = −1
        j=1: t = ω₈(−3 − 10i) = (7 − 13i)/√2; (−4 − 4i) ± t →
             y₁ = (−4 + 7/√2) + (−4 − 13/√2)i ≈ 0,950 − 13,192i
             y₅ = (−4 − 7/√2) + (−4 + 13/√2)i ≈ −8,950 + 5,192i
        j=2: t = i·(−1) = −i;                 −6 ± t → y₂ = −6 − i, y₆ = −6 + i
        j=3: t = ω₈³(−3 + 10i) = (−7 − 13i)/√2; (−4 + 4i) ± t →
             y₃ = (−4 − 7/√2) + (4 − 13/√2)i ≈ −8,950 − 5,192i
             y₇ = (−4 + 7/√2) + (4 + 13/√2)i ≈ 0,950 + 13,192i
  y = (29, 0,950 − 13,192i, −6 − i, −8,950 − 5,192i, −1, −8,950 + 5,192i,
       −6 + i, 0,950 + 13,192i)
  ```
  Kiểm tra: y₀ = tổng các phần tử = 29; y₄ = Σ(−1)ʲaⱼ = 0 − 2 + 3 + 1 + 4 − 5 + 7 − 9 = −1; vì đầu vào thực nên yₙ₋ₖ là liên hợp của yₖ (y₇ = liên hợp y₁, y₆ = liên hợp y₂, y₅ = liên hợp y₃). Đúng.
- **30.3-2:** Chỉ cách cài đặt FFT với hoán vị đảo bit ở **cuối** thay vì đầu. (Gợi ý: xét DFT ngược.) *Lời giải của người tổng hợp:* ITERATIVE-FFT tính y = S_(lg n) ⋯ S₂S₁Ra, với R là hoán vị đảo bit và Sₛ là tầng s. Ma trận DFT đối xứng (Vₙ = Vₙᵀ) và R đối xứng, R = R⁻¹, nên Vₙ = Vₙᵀ = R·S₁ᵀS₂ᵀ⋯S_(lg n)ᵀ: chạy các tầng theo thứ tự ngược (s = lg n xuống 1) với con bướm "chuyển vị" (u, v) ↦ (u + v, ω·(u − v)), rồi hoán vị đảo bit ở cuối. (Cách nhìn theo gợi ý: chạy mạch FFT ngược chiều từ đầu ra về đầu vào, đảo từng con bướm (p, q) ↦ ((p + q)/2, ω⁻¹(p − q)/2), ta tính DFT ngược với hoán vị đảo bit ở cuối; thay ω⁻¹ bằng ω và bỏ hệ số 1/2 thì được DFT.) Theo hiểu biết của người tổng hợp, đây là FFT "chia theo tần số" (decimation in frequency, Gentleman–Sande).
- **30.3-3:** ITERATIVE-FFT tính hệ số xoay bao nhiêu lần ở mỗi tầng? Viết lại để chỉ tính 2ˢ⁻¹ lần ở tầng s. *Lời giải của người tổng hợp:* dòng 13 (ω = ω·ω_m) chạy (n/m)·(m/2) = n/2 lần mỗi tầng (cộng một lần tính ω_m ở dòng 5), dù chỉ có m/2 giá trị khác nhau. Đổi thứ tự hai vòng trong:

  ```text
  for s = 1 to lg n
      m = 2ˢ
      ω_m = e^(2πi/m)
      ω = 1
      for j = 0 to m/2 − 1
          for k = 0 to n − 1 by m
              t = ω·A[k + j + m/2]
              u = A[k + j]
              A[k + j] = u + t
              A[k + j + m/2] = u − t
          ω = ω·ω_m
  ```
  Các con bướm trong một tầng độc lập nên đổi thứ tự không ảnh hưởng kết quả; mỗi tầng chỉ còn m/2 = 2ˢ⁻¹ phép cập nhật ω.
- **30.3-4 ★:** Giả sử các bộ cộng trong các con bướm của mạch FFT đôi khi hỏng theo cách luôn cho đầu ra 0, bất kể đầu vào. Giả sử đúng một bộ cộng hỏng nhưng không biết là cái nào. Mô tả cách xác định bộ cộng hỏng bằng cách đưa đầu vào vào mạch và quan sát đầu ra. Phương pháp hiệu quả tới đâu? *Ý tưởng của người tổng hợp (chưa chắc là lời giải tối ưu):* bộ cộng hỏng làm giá trị v trên một dây w sau tầng s bị thay bằng 0; vì các tầng sau là tuyến tính, đầu ra sai lệch đúng một vectơ e = −v·h_(s,w), với h_(s,w) là đáp ứng của các tầng s + 1..lg n với một xung đơn vị trên dây w. Xung trên dây w sau tầng s chỉ lan tới các đầu ra có cùng s bit thấp với w (2^(lg n − s) đầu ra), với mẫu hệ số xoay riêng. Chọn đầu vào sao cho mọi giá trị trung gian khác 0 (ví dụ đầu vào ngẫu nhiên — với xác suất 1 không giá trị nào bằng 0), tính đầu ra đúng bằng một FFT phần mềm, so với đầu ra quan sát: tập vị trí sai cho biết s và các bit thấp của w; mẫu tỉ số giữa các sai lệch cho biết phần còn lại của w. Như vậy một lần thử cộng O(n lg n) tính toán là đủ (nếu dùng phép thử đơn giản hơn với các xung đơn vị đầu vào thì cần nhiều lần thử hơn).

### Problem 30-1: Nhân bằng chia để trị (Divide-and-conquer multiplication)

- **(a)** Chỉ cách nhân hai đa thức bậc nhất ax + b và cx + d chỉ với ba phép nhân. (Gợi ý: một phép nhân là (a + b)·(c + d).) *Lời giải của người tổng hợp:* tính P₁ = ac, P₂ = bd, P₃ = (a + b)(c + d). Khi đó (ax + b)(cx + d) = P₁x² + (P₃ − P₁ − P₂)x + P₂. Ví dụ (2x + 3)(4x + 5): P₁ = 8, P₂ = 15, P₃ = 5·9 = 45, hệ số giữa 45 − 8 − 15 = 22; kiểm tra 8x² + 10x + 12x + 15 = 8x² + 22x + 15.
- **(b)** Cho hai thuật toán chia để trị nhân hai đa thức cận bậc n trong Θ(n^(lg 3)). Thuật toán thứ nhất chia hệ số đầu vào thành nửa cao và nửa thấp; thuật toán thứ hai chia theo chỉ số chẵn hay lẻ. *Lời giải của người tổng hợp:* (1) Nửa cao/thấp: A(x) = A_hi(x)·x^(n/2) + A_lo(x), B tương tự. AB = A_hiB_hi·xⁿ + [(A_hi + A_lo)(B_hi + B_lo) − A_hiB_hi − A_loB_lo]·x^(n/2) + A_loB_lo: ba phép nhân đệ quy cỡ n/2 cộng Θ(n) phép cộng và dịch. (2) Chẵn/lẻ: A(x) = A_e(x²) + x·A_o(x²); AB = A_eB_e(x²) + x·[(A_e + A_o)(B_e + B_o) − A_eB_e − A_oB_o](x²) + x²·A_oB_o(x²): cũng ba phép nhân cỡ n/2. Cả hai: T(n) = 3T(n/2) + Θ(n) = Θ(n^(log₂ 3)) ≈ Θ(n^1,585) (trường hợp 1 của định lý thợ).
- **(c)** Chỉ cách nhân hai số nguyên n bit trong O(n^(lg 3)) bước, mỗi bước thao tác trên tối đa một số hằng giá trị 1 bit. *Lời giải của người tổng hợp:* coi số n bit là đa thức theo x = 2 với hệ số 0/1; áp dụng (b) với nửa cao/thấp: X = X_hi·2^(n/2) + X_lo, ba phép nhân số n/2 (hoặc n/2 + 1) bit, cộng/trừ/dịch O(n) phép toán bit. T(n) = 3T(n/2) + O(n) = O(n^(lg 3)). Theo hiểu biết của người tổng hợp, đây là thuật toán Karatsuba (1962).

### Problem 30-2: Ma trận Toeplitz (Toeplitz matrices)

**Ma trận Toeplitz** là ma trận n × n A = (aᵢⱼ) với aᵢⱼ = aᵢ₋₁,ⱼ₋₁ cho i = 2, 3, …, n và j = 2, 3, …, n (mọi đường chéo song song với đường chéo chính có các phần tử bằng nhau). Ví dụ (người tổng hợp):

```text
⎛ 1  2  3 ⎞
⎜ 4  1  2 ⎟
⎝ 5  4  1 ⎠
```

- **(a)** Tổng hai ma trận Toeplitz có nhất thiết là Toeplitz không? Tích thì sao? *Người tổng hợp:* tổng thì có (điều kiện aᵢⱼ = aᵢ₋₁,ⱼ₋₁ tuyến tính). Tích thì không nhất thiết: [[0, 1], [0, 0]]·[[0, 0], [1, 0]] = [[1, 0], [0, 0]], có phần tử (1, 1) = 1 khác phần tử (2, 2) = 0.
- **(b)** Mô tả cách biểu diễn ma trận Toeplitz để cộng hai ma trận n × n trong O(n). *Người tổng hợp:* chỉ lưu hàng đầu và cột đầu — 2n − 1 số tₗ = aᵢⱼ với l = i − j ∈ {−(n − 1), …, n − 1}. Cộng: cộng từng tₗ, O(n).
- **(c)** Cho thuật toán O(n lg n) nhân ma trận Toeplitz n × n với vectơ độ dài n, dùng biểu diễn ở (b). *Người tổng hợp:* yᵢ = Σⱼ t_(i−j)xⱼ là một tích chập. Đặt T(z) = Σₗ tₗ z^(l+n−1) (cận bậc 2n − 1) và X(z) = Σⱼ xⱼzʲ; hệ số của z^(i+n−1) trong T(z)X(z) bằng Σⱼ t_(i−j)xⱼ = yᵢ. Nhân bằng FFT: O(n lg n). Ví dụ ma trận trên với x = (1, 1, 1): y = (6, 7, 10); qua đa thức: t₋₂ = 3, t₋₁ = 2, t₀ = 1, t₁ = 4, t₂ = 5 nên T(z) = 3 + 2z + z² + 4z³ + 5z⁴, nhân với 1 + z + z²: hệ số của z², z³, z⁴ là 3 + 2 + 1 = 6, 2 + 1 + 4 = 7, 1 + 4 + 5 = 10. Đúng.
- **(d)** Cho thuật toán hiệu quả nhân hai ma trận Toeplitz n × n; phân tích thời gian. *Lời giải của người tổng hợp:* cách đơn giản: n phép nhân ma trận–vectơ (mỗi cột của B), O(n² lg n). Cách tốt hơn, Θ(n²) — tối ưu vì kết quả có n² phần tử: với C = AB, ta có C_ij = C_(i−1, j−1) + A_(i,1)B_(1,j) − A_(i−1,n)B_(n,j−1) (dời chỉ số tổng Σₖ đi một bước làm mất số hạng đầu và thêm số hạng cuối). Tính hàng đầu và cột đầu của C bằng hai phép nhân Toeplitz–vectơ (O(n lg n)), rồi điền các phần tử còn lại theo công thức trên, mỗi phần tử O(1).

### Problem 30-3: FFT nhiều chiều (Multidimensional fast Fourier transform)

Tổng quát hoá DFT một chiều (30.8) lên d chiều. Đầu vào là mảng d chiều A = (a_(j₁, j₂, …, j_d)) với các kích thước n₁, n₂, …, n_d, n₁n₂⋯n_d = n. DFT d chiều định nghĩa bởi

```text
y_(k₁,k₂,…,k_d) = Σ_{j₁=0}^{n₁−1} Σ_{j₂=0}^{n₂−1} ⋯ Σ_{j_d=0}^{n_d−1}
                    a_(j₁,j₂,…,j_d) · ω_(n₁)^(j₁k₁) · ω_(n₂)^(j₂k₂) ⋯ ω_(n_d)^(j_d k_d)
```

với 0 ≤ k₁ < n₁, 0 ≤ k₂ < n₂, …, 0 ≤ k_d < n_d.

- **(a)** Chứng minh có thể tính DFT d chiều bằng cách lần lượt tính DFT một chiều theo từng chiều: trước hết n/n₁ DFT một chiều riêng theo chiều 1; dùng kết quả làm đầu vào, tính n/n₂ DFT một chiều theo chiều 2; rồi n/n₃ DFT theo chiều 3, … tới chiều d. *Người tổng hợp:* vì thừa số ω_(n₁)^(j₁k₁) chỉ phụ thuộc j₁, k₁, tổng trong cùng theo j₁ (với các j₂, …, j_d cố định) là DFT một chiều độ dài n₁; kết quả trung gian b_(k₁, j₂, …, j_d) rồi thay vào các tổng còn lại, lặp lại cho chiều 2, … Có n/n₁ bộ (j₂, …, j_d) nên có n/n₁ DFT theo chiều 1.
- **(b)** Chứng minh thứ tự các chiều không quan trọng. *Người tổng hợp:* các tổng hữu hạn đổi thứ tự được, và tích các thừa số tách theo từng chiều.
- **(c)** Chứng minh nếu tính mỗi DFT một chiều bằng FFT thì tổng thời gian tính DFT d chiều là O(n lg n), không phụ thuộc d. *Người tổng hợp:* chiều i tốn (n/nᵢ)·O(nᵢ lg nᵢ) = O(n lg nᵢ); cộng lại O(n Σᵢ lg nᵢ) = O(n lg Πᵢnᵢ) = O(n lg n). (Giả sử mỗi nᵢ là luỹ thừa của 2.) Ví dụ ảnh 1024 × 1024: n = 2²⁰, 1024 FFT độ dài 1024 theo hàng rồi 1024 FFT độ dài 1024 theo cột; mỗi chiều tốn O(n·10), tổng O(n·20) = O(n lg n).

### Problem 30-4: Đánh giá mọi đạo hàm của đa thức tại một điểm (Evaluating all derivatives of a polynomial at a point)

Cho đa thức A(x) cận bậc n, đạo hàm bậc t định nghĩa bởi

```text
A^(t)(x) = A(x)                 nếu t = 0
           (d/dx) A^(t−1)(x)    nếu 1 ≤ t ≤ n − 1
           0                    nếu t ≥ n
```

Từ biểu diễn hệ số (a₀, a₁, …, aₙ₋₁) của A(x) và một điểm x₀, muốn tính A^(t)(x₀) cho t = 0, 1, …, n − 1.

- **(a)** Cho các hệ số b₀, b₁, …, bₙ₋₁ thoả A(x) = Σⱼ₌₀ⁿ⁻¹ bⱼ(x − x₀)ʲ, chỉ cách tính A^(t)(x₀), t = 0..n − 1, trong O(n). *Người tổng hợp:* đạo hàm t lần của bⱼ(x − x₀)ʲ tại x₀ bằng 0 trừ khi j = t, khi đó bằng t!·bₜ. Vậy A^(t)(x₀) = t!·bₜ; tính t! tăng dần, tổng O(n).
- **(b)** Giải thích cách tìm b₀, …, bₙ₋₁ trong O(n lg n) khi biết A(x₀ + ωₙᵏ), k = 0..n − 1. *Người tổng hợp:* A(x₀ + ωₙᵏ) = Σⱼ bⱼ(ωₙᵏ)ʲ = Σⱼ bⱼωₙ^(kj), tức vectơ các giá trị này là DFTₙ(b). Vậy b = DFTₙ⁻¹ của nó, O(n lg n).
- **(c)** Chứng minh

  ```text
  A(x₀ + ωₙᵏ) = Σ_{r=0}^{n−1} ( (ωₙ^(kr)/r!) · Σ_{j=0}^{n−1} f(j)·g(r − j) )
  ```
  với f(j) = aⱼ·j! và

  ```text
  g(l) = x₀^(−l)/(−l)!    nếu −(n − 1) ≤ l ≤ 0
         0                nếu 1 ≤ l ≤ n − 1
  ```
  *Người tổng hợp:* khai triển Taylor (chính xác vì A là đa thức): A(x₀ + h) = Σᵣ A^(r)(x₀)hʳ/r!. Lại có A^(r)(x₀) = Σ_{j≥r} aⱼ·j!/(j − r)!·x₀^(j−r) = Σⱼ f(j)·g(r − j), vì g(r − j) = x₀^(j−r)/(j − r)! khi j ≥ r và bằng 0 khi j < r. Thay h = ωₙᵏ được công thức.
- **(d)** Giải thích cách đánh giá A(x₀ + ωₙᵏ), k = 0..n − 1, trong O(n lg n); kết luận có thể đánh giá mọi đạo hàm không tầm thường của A(x) tại x₀ trong O(n lg n). *Người tổng hợp:* h(r) = Σⱼ f(j)g(r − j), r = 0..n − 1, là một tích chập của f (độ dài n) với g (độ dài 2n − 1, dời chỉ số) — một phép nhân đa thức bằng FFT, O(n lg n). Sau đó A(x₀ + ωₙᵏ) = Σᵣ (h(r)/r!)ωₙ^(kr) là DFT của vectơ (h(r)/r!), thêm O(n lg n). Kết hợp (b) và (a) ra mọi đạo hàm. (Nhận xét của người tổng hợp: thực ra h(r) đã chính là A^(r)(x₀) theo (c), nên chỉ một tích chập là đủ; con đường qua (b) chủ yếu để luyện cách dùng DFT.) Ví dụ nhỏ: A(x) = x², x₀ = 1: A = 1 + 2(x − 1) + (x − 1)², b = (1, 2, 1), các đạo hàm 0!·1 = 1, 1!·2 = 2, 2!·1 = 2.

### Problem 30-5: Đánh giá đa thức tại nhiều điểm (Polynomial evaluation at multiple points)

Đã biết đánh giá đa thức cận bậc n tại một điểm trong O(n) (Horner), và tại tất cả n căn phức bậc n của đơn vị trong O(n lg n) (FFT). Bài toán chỉ cách đánh giá tại n điểm **tuỳ ý** trong O(n lg² n). Giả thiết (không chứng minh) có thể tính phần dư khi chia một đa thức như vậy cho một đa thức khác trong O(n lg n). Ví dụ phần dư của 3x³ + x² − 3x + 1 khi chia cho x² + x + 2 là

```text
(3x³ + x² − 3x + 1) mod (x² + x + 2) = −7x + 5
```

(Kiểm tra của người tổng hợp: 3x³ + x² − 3x + 1 = (3x − 2)(x² + x + 2) + (−7x + 5), vì (3x − 2)(x² + x + 2) = 3x³ + x² + 4x − 4.)

Cho A(x) = Σₖ₌₀ⁿ⁻¹ aₖxᵏ và n điểm x₀, …, xₙ₋₁, muốn tính A(x₀), …, A(xₙ₋₁). Với 0 ≤ i ≤ j ≤ n − 1, định nghĩa Pᵢⱼ(x) = Πₖ₌ᵢʲ (x − xₖ) và Qᵢⱼ(x) = A(x) mod Pᵢⱼ(x). Lưu ý Qᵢⱼ có bậc tối đa j − i.

- **(a)** Chứng minh A(x) mod (x − z) = A(z) với mọi điểm z. *Người tổng hợp:* chia A cho (x − z) được A(x) = q(x)(x − z) + r với r là hằng (bậc nhỏ hơn 1); thay x = z ra r = A(z).
- **(b)** Chứng minh Qₖₖ(x) = A(xₖ) và Q₀,ₙ₋₁(x) = A(x). *Người tổng hợp:* Pₖₖ = x − xₖ nên Qₖₖ = A(xₖ) theo (a). P₀,ₙ₋₁ có bậc n, A có bậc < n, nên phần dư là chính A.
- **(c)** Chứng minh với i ≤ k ≤ j: Qᵢₖ(x) = Qᵢⱼ(x) mod Pᵢₖ(x) và Qₖⱼ(x) = Qᵢⱼ(x) mod Pₖⱼ(x). *Người tổng hợp:* A = q·Pᵢⱼ + Qᵢⱼ và Pᵢₖ chia hết Pᵢⱼ, nên A ≡ Qᵢⱼ (mod Pᵢₖ); lấy dư hai vế cho Pᵢₖ ra Qᵢₖ = Qᵢⱼ mod Pᵢₖ. Tương tự cho Pₖⱼ.
- **(d)** Cho thuật toán O(n lg² n) đánh giá A(x₀), …, A(xₙ₋₁). *Người tổng hợp:* (1) Dựng "cây tích con": lá là Pₖₖ = x − xₖ; mỗi nút trong là tích hai con, Pᵢⱼ = Pᵢₘ·Pₘ₊₁,ⱼ với m = ⌊(i + j)/2⌋; mỗi tầng tổng bậc n, nhân bằng FFT tốn O(n lg n) mỗi tầng, lg n tầng: O(n lg² n). (2) Đi xuống: ở gốc Q₀,ₙ₋₁ = A; tại nút (i, j), tính hai con Qᵢₘ = Qᵢⱼ mod Pᵢₘ và Qₘ₊₁,ⱼ = Qᵢⱼ mod Pₘ₊₁,ⱼ (theo (c)); mỗi tầng tổng cỡ O(n), phép lấy dư O(n lg n) mỗi tầng; ở lá được A(xₖ) theo (b). Tổng O(n lg² n).

### Problem 30-6: FFT dùng số học modulo (FFT using modular arithmetic)

Như đã định nghĩa, DFT đòi tính với số phức, có thể mất độ chính xác do sai số làm tròn. Với một số bài toán, đáp số được biết chỉ gồm số nguyên, và dùng một biến thể FFT dựa trên số học modulo thì có thể bảo đảm tính chính xác. Ví dụ là nhân hai đa thức hệ số nguyên. Exercise 30.2-6 cho một cách, dùng modulus dài Ω(n) bit để làm DFT trên n điểm. Bài toán này cho cách khác, dùng modulus có độ dài hợp lý hơn O(lg n); cần hiểu Chương 31. Cho n là luỹ thừa của 2.

- **(a)** Giả sử tìm k nhỏ nhất sao cho p = kn + 1 là số nguyên tố. Cho một lập luận heuristic đơn giản vì sao có thể kỳ vọng k xấp xỉ ln n. (Giá trị k có thể lớn hơn hoặc nhỏ hơn nhiều, nhưng có thể kỳ vọng trung bình phải xét O(lg n) giá trị k.) Độ dài kỳ vọng của p so với độ dài của n thế nào? *Người tổng hợp:* theo định lý số nguyên tố, một số ngẫu nhiên cỡ N là nguyên tố với xác suất khoảng 1/ln N; coi kn + 1 "như ngẫu nhiên" cỡ khoảng n·ln n, xác suất mỗi ứng viên khoảng 1/ln(kn) ≈ 1/ln n, nên kỳ vọng thử khoảng ln n giá trị k. Khi đó p ≈ n ln n, độ dài lg p ≈ lg n + lg ln n = (1 + o(1)) lg n bit — xấp xỉ độ dài của n.
- Cho g là phần tử sinh của Z*ₚ (nhóm nhân modulo p), và đặt w = gᵏ mod p.
- **(b)** Lập luận rằng DFT và DFT ngược là hai phép toán ngược nhau được xác định đúng đắn modulo p, khi dùng w làm căn chính bậc n của đơn vị. *Người tổng hợp:* g có bậc p − 1 = kn nên w = gᵏ có bậc đúng n: wⁿ ≡ 1 và wʲ ≢ 1 với 0 < j < n. Zₚ là trường, nên bổ đề tổng chứng minh như Bổ đề 30.6 (mẫu wᵏ − 1 khác 0 và khả nghịch); n < p nên n khả nghịch modulo p. Chứng minh Định lý 30.7 giữ nguyên.
- **(c)** Chỉ cách làm FFT và FFT ngược modulo p trong O(n lg n), với giả thiết các phép toán trên từ O(lg n) bit tốn thời gian đơn vị, và thuật toán được cho p và w. *Người tổng hợp:* dùng nguyên RECURSIVE-FFT hoặc ITERATIVE-FFT, thay ωₙ bằng w (ở tầng m dùng w^(n/m)), mọi phép cộng, trừ, nhân lấy modulo p; DFT ngược dùng w⁻¹ mod p và nhân với n⁻¹ mod p (tính bằng thuật toán Euclid mở rộng của Chương 31). Mọi số nhỏ hơn p, O(lg n) bit.
- **(d)** Tính DFT modulo p = 17 của vectơ (0, 5, 3, 7, 7, 2, 1, 6); biết g = 3 là phần tử sinh của Z*₁₇. *Lời giải của người tổng hợp:* n = 8, p = 17 = 2·8 + 1 nên k = 2, w = 3² = 9. Các luỹ thừa của 9 modulo 17: 9⁰..9⁷ ≡ 1, 9, 13, 15, 16, 8, 4, 2 (9⁴ ≡ 16 ≡ −1, đúng như căn bậc 8). yₖ = Σⱼ aⱼ·9^(kj) mod 17:

  ```text
  y₀ = 0+5+3+7+7+2+1+6 = 31 ≡ 14
  y₁ = 0·1 + 5·9 + 3·13 + 7·15 + 7·16 + 2·8 + 1·4 + 6·2
     = 45 + 39 + 105 + 112 + 16 + 4 + 12 = 333 ≡ 10      (333 = 19·17 + 10)
  y = (14, 10, 10, 4, 8, 11, 13, 15)
  ```
  Kiểm tra: DFT ngược với w⁻¹ = 2 (vì 9·2 = 18 ≡ 1) và n⁻¹ = 8⁻¹ ≡ 15 (vì 8·15 = 120 = 7·17 + 1) cho lại đúng (0, 5, 3, 7, 7, 2, 1, 6) (người tổng hợp đã kiểm tra bằng máy). Ngoài ra y₄ = Σ(−1)ʲaⱼ = 0 − 5 + 3 − 7 + 7 − 2 + 1 − 6 = −9 ≡ 8. Đúng.

### Ghi chú chương (Chapter notes, trang 924–925)

- Sách của **Van Loan** trình bày FFT xuất sắc. **Press, Teukolsky, Vetterling và Flannery** mô tả tốt FFT và các ứng dụng (theo hiểu biết của người tổng hợp, đây là bộ *Numerical Recipes*).
- Để nhập môn xử lý tín hiệu, một lĩnh vực ứng dụng phổ biến của FFT, xem sách của **Oppenheim và Schafer** và của **Oppenheim và Willsky**. Sách Oppenheim–Schafer còn chỉ cách xử lý trường hợp n không phải luỹ thừa nguyên của 2.
- Phân tích Fourier không giới hạn ở dữ liệu một chiều; nó được dùng rộng rãi trong xử lý ảnh để phân tích dữ liệu hai chiều trở lên. Sách của **Gonzalez và Woods** và của **Pratt** bàn biến đổi Fourier nhiều chiều và ứng dụng trong xử lý ảnh; sách của **Tolimieri, An và Lu** và của **Van Loan** bàn toán học của FFT nhiều chiều.
- **Cooley và Tukey** thường được ghi công là người nghĩ ra FFT vào thập niên 1960. Thực ra FFT đã được phát hiện nhiều lần trước đó, nhưng tầm quan trọng của nó chưa được nhận ra đầy đủ trước khi có máy tính số hiện đại. Press, Teukolsky, Vetterling và Flannery quy nguồn gốc phương pháp cho **Runge và König** năm 1924, còn bài báo của **Heideman, Johnson và Burrus** truy lịch sử FFT về tận **C. F. Gauss** năm 1805.
- **Frigo và Johnson** phát triển một cài đặt FFT nhanh và linh hoạt tên **FFTW** ("fastest Fourier transform in the West" — FFT nhanh nhất phương Tây). FFTW được thiết kế cho tình huống cần nhiều phép tính DFT cùng kích thước bài toán. Trước khi thật sự tính DFT, FFTW chạy một "bộ lập kế hoạch" (planner) — qua một loạt lần chạy thử — xác định cách tốt nhất phân rã phép tính FFT cho kích thước đó trên máy cụ thể. FFTW thích nghi để dùng bộ nhớ đệm phần cứng hiệu quả, và khi bài toán con đủ nhỏ thì giải bằng mã tuần tự (không vòng lặp) đã tối ưu. Hơn nữa, FFTW có ưu điểm hiếm là chạy Θ(n lg n) với mọi kích thước n, kể cả khi n là một số nguyên tố lớn.
- Biến đổi Fourier chuẩn giả định đầu vào là các điểm cách đều trong miền thời gian; có những kỹ thuật khác xấp xỉ FFT trên dữ liệu "không cách đều" (nonequispaced). Bài báo của **Ware** cho một tổng quan.

## Luận điểm cốt lõi

### Mệnh đề

Phép nhân hai đa thức cận bậc n (tức tích chập hai vectơ độ dài n) làm được trong Θ(n lg n) thay vì Θ(n²): đổi sang biểu diễn giá trị tại 2n căn phức bậc 2n của đơn vị bằng FFT, nhân từng điểm, rồi đổi ngược bằng FFT ngược; FFT đạt Θ(n lg n) vì các căn đơn vị khép kín dưới phép bình phương (bổ đề chia đôi), và FFT ngược chỉ là FFT với ωₙ⁻¹ chia cho n vì ma trận DFT có nghịch đảo Vₙ⁻¹ = (1/n)·(ωₙ^(−kj)).

### Giả định

- Mô hình RAM thực: mỗi phép cộng, nhân số phức tốn thời gian hằng số và chính xác tuyệt đối (sách chỉ cảnh báo vấn đề sai số làm tròn ở chú thích về nội suy và ở Problem 30-6).
- n là luỹ thừa của 2 (đạt được bằng cách đệm hệ số 0; các kích thước khác "nằm ngoài phạm vi sách").
- Hệ số thuộc một trường (thường là ℂ) để chia được cho n và tồn tại căn đơn vị bậc n; Problem 30-6 và Exercise 30.2-6 thay bằng Zₚ hay Zₘ có căn đơn vị thích hợp.
- Các điểm của biểu diễn điểm–giá trị phân biệt nhau (để ma trận Vandermonde khả nghịch).
- Với mạch song song: mỗi con bướm là một phần tử tính toán thời gian hằng số; đo bằng độ sâu mạch.

### Cơ chế

1. Biểu diễn hệ số: cộng và đánh giá Θ(n), nhân Θ(n²). Biểu diễn điểm–giá trị: cộng, nhân Θ(n) (cần 2n điểm cho tích), nội suy duy nhất (Vandermonde).
2. Chọn điểm là căn đơn vị: ω_(dn)^(dk) = ωₙᵏ (triệt tiêu), ωₙ^(n/2) = −1, bình phương các căn bậc n là các căn bậc n/2 (chia đôi), Σⱼ ωₙ^(kj) = 0 khi n không chia hết k (tổng).
3. Tách chẵn–lẻ A(x) = A^[0](x²) + xA^[1](x²) ⇒ hai DFT cỡ n/2 + n/2 con bướm ⇒ T(n) = 2T(n/2) + Θ(n) = Θ(n lg n).
4. Ma trận DFT Vₙ = (ωₙ^(kj)) có Vₙ⁻¹ = (ωₙ^(−kj)/n) ⇒ DFT ngược cùng độ phức tạp.
5. Cài đặt: gom biểu thức con chung thành con bướm; thứ tự lá của cây đệ quy là hoán vị đảo bit; chạy lg n tầng từ dưới lên tại chỗ; n/2 con bướm mỗi tầng độc lập ⇒ mạch độ sâu Θ(lg n).

### Bằng chứng và ví dụ tác giả đưa ra

- Ví dụ cộng (6x³ + 7x² − 10x + 9) + (−2x³ + 4x − 5) = 4x³ + 7x² − 6x + 4 và nhân ra −12x⁶ − 14x⁵ + 44x⁴ − 20x³ − 75x² + 86x − 45 bằng cách đặt tính.
- Chứng minh Định lý 30.1 qua định thức Vandermonde Π(xₖ − xⱼ).
- Sơ đồ bốn bước (Hình 30.1) và Định lý 30.2.
- Tám căn bậc 8 trên mặt phẳng phức (Hình 30.2); chứng minh ba bổ đề và hệ quả.
- Chứng minh từng dòng rằng RECURSIVE-FFT trả về đúng A(ωₙᵏ) và A(ωₙ^(k+n/2)); truy hồi Θ(n lg n).
- Định lý 30.7 (nghịch đảo của Vₙ) và Định lý 30.8 (tích chập).
- Con bướm (Hình 30.3), cây lời gọi n = 8 (Hình 30.4) với thứ tự lá 0, 4, 2, 6, 1, 5, 3, 7 và phép đảo bit; tính L(n) = (n/2) lg n; mạch song song n = 8 (Hình 30.5).
- Ví dụ phép chia dư ở Problem 30-5 và dữ liệu p = 17, g = 3 ở Problem 30-6.

### Kết luận và hàm ý cho người lập trình

- Khi gặp tổng dạng cⱼ = Σₖ aₖbⱼ₋ₖ (tích chập) với n lớn — nhân số lớn, nhân đa thức, đếm tổng của hai tập (Exercise 30.1-7), so khớp mẫu có ký tự đại diện, lọc tín hiệu — hãy nghĩ tới FFT.
- Đổi biểu diễn có thể biến phép toán đắt thành rẻ; chi phí nằm ở phép chuyển đổi, và phải chọn biểu diễn trung gian sao cho phép chuyển nhanh.
- Đệm 0 tới độ dài ≥ 2n − 1 (làm tròn lên luỹ thừa của 2); quên đệm sẽ ra tích chập vòng (cyclic convolution) chứ không phải tích chập thường — theo hiểu biết của người tổng hợp, đây là lỗi phổ biến.
- FFT số phức có sai số làm tròn; với kết quả nguyên lớn, dùng FFT modulo số nguyên tố dạng kn + 1 (Problem 30-6) hoặc làm tròn cẩn thận và kiểm soát độ lớn.
- Trong thực tế dùng thư viện (FFTW và các thư viện tương tự) — chúng xử lý mọi n, tối ưu bộ nhớ đệm và dùng quy ước dấu ngược với sách.
- Bản lặp tại chỗ (đảo bit + lg n tầng con bướm) là khuôn chuẩn khi phải tự cài.

### Trong ngôn ngữ khoa học máy tính

Nhân đa thức thẳng: Θ(n²). DFTₙ(a)ₖ = Σⱼ aⱼωₙ^(kj), ωₙ = e^(2πi/n). RECURSIVE-FFT: T(n) = 2T(n/2) + Θ(n) = Θ(n lg n). DFTₙ⁻¹(y)ⱼ = (1/n)Σₖ yₖωₙ^(−kj), Θ(n lg n). Tích chập: a ⊗ b = DFT₂ₙ⁻¹(DFT₂ₙ(a)·DFT₂ₙ(b)), Θ(n lg n). ITERATIVE-FFT: BIT-REVERSE-COPY O(n lg n) (hoặc Θ(n)) cộng (n/2) lg n con bướm. Mạch FFT song song: độ sâu Θ(lg n), Θ(n lg n) con bướm. Nội suy tổng quát: O(n³) bằng LU, Θ(n²) bằng Lagrange. Đánh giá tại n điểm tuỳ ý: O(n lg² n) (Problem 30-5). Nhân Karatsuba: Θ(n^(lg 3)) (Problem 30-1). DFT d chiều: O(n lg n) (Problem 30-3).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| polynomial | đa thức | tổng Σ aⱼxʲ trên một trường |
| coefficient | hệ số | các aⱼ của đa thức |
| degree | bậc | chỉ số của hệ số khác 0 cao nhất |
| degree-bound | cận bậc | số nguyên lớn hơn hẳn bậc; "cận bậc n" nghĩa là có n hệ số |
| field | trường | tập có cộng, nhân, chia (khác 0) như ℂ, Zₚ |
| polynomial addition / multiplication | cộng / nhân đa thức | Θ(n) / Θ(n²) ở dạng hệ số |
| convolution (a ⊗ b) | tích chập | vectơ hệ số của tích, cⱼ = Σ aₖbⱼ₋ₖ |
| coefficient representation | biểu diễn hệ số | vectơ (a₀, …, aₙ₋₁) |
| point-value representation | biểu diễn điểm–giá trị | n cặp (xₖ, A(xₖ)), xₖ phân biệt |
| extended point-value representation | biểu diễn điểm–giá trị mở rộng | 2n cặp, đủ cho tích |
| evaluation | đánh giá | tính giá trị đa thức tại điểm |
| interpolation | nội suy | tìm hệ số từ các cặp điểm–giá trị |
| Horner's rule | quy tắc Horner | đánh giá lồng nhau trong Θ(n) |
| Vandermonde matrix | ma trận Vandermonde | hàng (1, xₖ, xₖ², …); định thức Π(xₖ − xⱼ) |
| Lagrange's formula | công thức Lagrange | nội suy bằng tổng các đa thức cơ sở, Θ(n²) |
| numerical stability | độ ổn định số | mức nhạy với sai số đầu vào và làm tròn |
| complex nth root of unity | căn phức bậc n của đơn vị | số phức ω với ωⁿ = 1 |
| principal nth root of unity | căn chính bậc n | ωₙ = e^(2πi/n) |
| cancellation lemma | bổ đề triệt tiêu | ω_(dn)^(dk) = ωₙᵏ |
| halving lemma | bổ đề chia đôi | bình phương các căn bậc n là các căn bậc n/2 |
| summation lemma | bổ đề tổng | Σⱼ (ωₙᵏ)ʲ = 0 khi n không chia hết k |
| discrete Fourier transform (DFT) | biến đổi Fourier rời rạc | yₖ = A(ωₙᵏ) |
| inverse DFT | DFT ngược | aⱼ = (1/n)Σ yₖωₙ^(−kj) |
| fast Fourier transform (FFT) | biến đổi Fourier nhanh | thuật toán Θ(n lg n) tính DFT |
| twiddle factor | hệ số xoay | các ωₙᵏ nhân vào nửa lẻ, dùng với cả dấu + và − |
| convolution theorem | định lý tích chập | a ⊗ b = DFT⁻¹(DFT(a)·DFT(b)) |
| componentwise product | tích từng thành phần | nhân từng cặp phần tử cùng vị trí |
| common subexpression | biểu thức con chung | giá trị tính lặp, lưu vào biến tạm |
| butterfly operation | phép con bướm | (u, v) ↦ (u + ωv, u − ωv) |
| bit-reversal permutation | hoán vị đảo bit | đặt aₖ vào ô rev(k) |
| circuit depth | độ sâu mạch | số phần tử tính toán lớn nhất trên một đường vào–ra |
| time domain / frequency domain | miền thời gian / miền tần số | hai cách nhìn một tín hiệu |
| signal processing | xử lý tín hiệu | ứng dụng chính của biến đổi Fourier |
| Cartesian sum | tổng Descartes | {x + y : x ∈ A, y ∈ B} |
| chirp transform | biến đổi chirp | yₖ = Σ aⱼz^(kj) với z tuỳ ý |
| Toeplitz matrix | ma trận Toeplitz | phần tử hằng trên mỗi đường chéo |
| generator (of Z*ₚ) | phần tử sinh | phần tử có bậc p − 1 trong nhóm nhân modulo p |
| FFTW | FFTW | thư viện FFT tự thích nghi của Frigo và Johnson |
| nonequispaced data | dữ liệu không cách đều | điểm mẫu không cách đều trong thời gian |

## Câu nói đáng nhớ

> "In this chapter, we shall show how the fast Fourier transform, or FFT, can reduce the time to multiply polynomials to Θ(n lg n)." — mở đầu Chương 30
>
> *Dịch: Trong chương này, chúng tôi sẽ chỉ ra biến đổi Fourier nhanh, hay FFT, có thể giảm thời gian nhân đa thức xuống Θ(n lg n) như thế nào.*

> "The answer hinges on whether we can convert a polynomial quickly from coefficient form to point-value form (evaluate) and vice versa (interpolate)." — Mục 30.1
>
> *Dịch: Câu trả lời phụ thuộc vào việc ta có thể chuyển nhanh một đa thức từ dạng hệ số sang dạng điểm–giá trị (đánh giá) và ngược lại (nội suy) hay không.*

> "As we shall see, the halving lemma is essential to our divide-and-conquer approach for converting between coefficient and point-value representations of polynomials, since it guarantees that the recursive subproblems are only half as large." — Mục 30.2
>
> *Dịch: Như sẽ thấy, bổ đề chia đôi là cốt yếu cho cách chia để trị để chuyển giữa biểu diễn hệ số và biểu diễn điểm–giá trị của đa thức, vì nó bảo đảm các bài toán con đệ quy chỉ lớn bằng một nửa.*

> "Because we use each factor ωₙᵏ in both its positive and negative forms, we call the factors ωₙᵏ twiddle factors." — Mục 30.2
>
> *Dịch: Vì mỗi thừa số ωₙᵏ được dùng ở cả dạng dương lẫn dạng âm, ta gọi các thừa số ωₙᵏ là hệ số xoay.*

> "Interpolation is a notoriously tricky problem from the point of view of numerical stability." — chú thích chân trang 1, Mục 30.1
>
> *Dịch: Nội suy là một bài toán nổi tiếng khó xét về mặt độ ổn định số.*

> "The FFT had in fact been discovered many times previously, but its importance was not fully realized before the advent of modern digital computers." — Ghi chú chương
>
> *Dịch: Thực ra FFT đã được phát hiện nhiều lần trước đó, nhưng tầm quan trọng của nó chưa được nhận ra đầy đủ trước khi máy tính số hiện đại ra đời.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: trình bày FFT như một bài toán về đa thức, không phải về tín hiệu

Phần lớn giáo trình xử lý tín hiệu giới thiệu DFT như một phép biến đổi tín hiệu với công thức có sẵn. Sách đi đường khác: bắt đầu từ một câu hỏi thuật toán thuần tuý (nhân đa thức nhanh), nhận ra nhân rẻ ở dạng điểm–giá trị, rồi hỏi "chọn điểm nào để đổi biểu diễn rẻ?" — và căn đơn vị xuất hiện như câu trả lời tự nhiên nhờ bổ đề chia đôi. Cách này làm DFT trở thành "đánh giá đa thức tại căn đơn vị", DFT ngược trở thành "nội suy", và định lý tích chập trở thành điều hiển nhiên. Người học thấy được *vì sao* FFT tồn tại chứ không chỉ *nó làm gì*.

### Điểm mạnh: từ đệ quy tới vòng lặp tới phần cứng

Mục 30.3 là một bài học mẫu về tối ưu hoá theo từng bước có lý do: gom biểu thức con chung (ra con bướm), vẽ cây lời gọi (ra hoán vị đảo bit), chạy từ dưới lên (ra ITERATIVE-FFT tại chỗ), nhận ra các con bướm cùng tầng độc lập (ra mạch song song). Mỗi bước đều có thể kiểm chứng trên ví dụ n = 8. Cách "đọc cây đệ quy từ dưới lên để khử đệ quy" dùng lại được ở nhiều nơi khác (sắp xếp trộn từ dưới lên, cây phân đoạn lặp).

### Điểm yếu và chỗ đơn giản hoá

- **Bỏ qua sai số dấu phẩy động.** Phân tích giả định số phức chính xác. Trên máy thật, sai số của FFT tăng chậm (khoảng O(lg n) lần đơn vị làm tròn — theo hiểu biết của người tổng hợp), nhưng khi dùng FFT để nhân số nguyên lớn, kết quả có thể bị làm tròn sai nếu hệ số quá lớn. Sách chỉ nhắc ở chú thích chân trang và Problem 30-6.
- **Chỉ xử lý n là luỹ thừa của 2.** Đệm 0 tới luỹ thừa của 2 có thể gần gấp đôi kích thước; các thuật toán cho n tuỳ ý (Bluestein — thực ra là ý của Exercise 30.2-8; Rader cho n nguyên tố; hỗn hợp cơ số) chỉ được nhắc qua Ghi chú chương.
- **Không có ví dụ số hoàn chỉnh trong phần chính.** Chương không chạy tay RECURSIVE-FFT hay ITERATIVE-FFT trên số cụ thể; người đọc phải tự làm qua Exercise 30.2-2 và 30.3-1. (Bản tổng hợp này đã bổ sung.)
- **Mô hình mạch song song khá trừu tượng.** "Độ sâu Θ(lg n)" bỏ qua chi phí truyền dữ liệu giữa các dây cách xa nhau (ở tầng cuối, dây k nối với dây k + n/2), vốn là chi phí chính trên phần cứng thật; sách cũng không nối mạch này với mô hình đa luồng của Chương 27 (công việc Θ(n lg n), span Θ(lg n)).
- **Một vài chỗ ký hiệu lỏng** (n ≥ 0 trong bổ đề triệt tiêu, câu "interpolate the complex roots of unity by a polynomial") đã nêu ở khối Lưu ý.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: thư viện FFT hiện đại (FFTW, Intel MKL, cuFFT) dùng hỗn hợp nhiều cơ số (2, 4, 8, số nguyên tố nhỏ), thuật toán split-radix, các "codelet" sinh tự động, và chọn kế hoạch bằng chạy thử như FFTW mô tả trong Ghi chú chương; FFT trên dữ liệu thực tận dụng tính đối xứng liên hợp để tiết kiệm một nửa. Trong số học số lớn (GMP), FFT chỉ được dùng khi số rất lớn; ở cỡ vừa thì Karatsuba (Problem 30-1) và Toom–Cook nhanh hơn do hằng số nhỏ. Trong mật mã hậu lượng tử, biến thể modulo (NTT) của Problem 30-6 là phép toán trung tâm. Năm 2019, Harvey và van der Hoeven công bố thuật toán nhân số nguyên O(n log n) phép toán bit, dựa trên FFT nhiều chiều — nối Problem 30-1(c) và Problem 30-3 thành một kết quả lý thuyết lớn.

### Liên hệ các chương khác

- Chương 2 và 4: cùng truy hồi T(n) = 2T(n/2) + Θ(n) như sắp xếp trộn; Strassen (Chương 4) và Karatsuba (Problem 30-1) cùng ý tưởng giảm số phép nhân đệ quy.
- Chương 17: Problem 17-1 (bộ đếm nhị phân đảo bit) sinh hoán vị đảo bit trong thời gian khấu hao O(1) mỗi bước.
- Chương 27: mạch FFT song song là ví dụ tự nhiên của thuật toán có span Θ(lg n); có thể viết ITERATIVE-FFT với vòng "parallel for" ở hai vòng trong.
- Chương 28 và Phụ lục D: ma trận Vandermonde, định thức, phân rã LU cho nội suy O(n³).
- Chương 31: nhóm căn đơn vị (Mục 31.3), phần tử sinh, nghịch đảo modulo — nền của Problem 30-6.
- Chương 32: theo hiểu biết của người tổng hợp, so khớp chuỗi có ký tự đại diện và đếm số vị trí khớp với mọi độ dịch làm được bằng tích chập FFT trong O(n lg n).

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** câu hỏi kinh điển là "nhân hai số rất lớn" (Karatsuba, rồi FFT), "đếm số cặp có tổng bằng k với mọi k" (Exercise 30.1-7), giải thích vì sao FFT là O(n lg n) (bổ đề chia đôi), viết hoán vị đảo bit.
- **Lập trình thi đấu:** FFT/NTT là công cụ chuẩn: nhân đa thức, nhân số lớn, đếm tổng hai tập, so khớp chuỗi có ký tự đại diện, tổ hợp đếm bằng hàm sinh. Thường dùng NTT modulo 998244353 = 119·2²³ + 1 với phần tử sinh 3 — đúng dạng p = kn + 1 của Problem 30-6 (theo hiểu biết của người tổng hợp). Lỗi hay gặp: quên đệm tới ≥ 2n − 1, sai dấu ω trong FFT ngược, quên chia cho n, tràn số khi hệ số lớn.
- **Kỹ thuật phần mềm:** đừng tự viết FFT cho sản phẩm — dùng thư viện, chú ý quy ước dấu và hệ số chuẩn hoá (1/n ở chiều nào). Dùng FFT cho tích chập dài (lọc âm thanh, xử lý ảnh, tương quan chéo trong tìm kiếm mẫu); với nhân kích thước nhỏ, cách thẳng Θ(n²) có thể nhanh hơn vì hằng số nhỏ. Khi cần kết quả nguyên chính xác, dùng NTT hoặc kiểm soát biên sai số.

# Chương 31 — Thuật toán số học (Number-Theoretic Algorithms)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VII "Selected Topics", Chương 31 "Number-Theoretic Algorithms", trang 926–984.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS. Riêng chương này có thêm một sắc thái: Ronald L. Rivest là chữ "R" trong RSA, hệ mật mã mà Mục 31.7 trình bày.
**Vị trí trong lập luận của cả cuốn sách:** Chương 3 ([C03-tang-truong-cua-ham.md](C03-tang-truong-cua-ham.md)) cho ký hiệu a mod n, phép đồng dư a ≡ b (mod n), các số Fibonacci Fₖ và tỉ số vàng φ — chương này dùng cả ba (Fibonacci là đầu vào xấu nhất của thuật toán Euclid). Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)) cho bộ sinh RANDOM, ý tưởng thuật toán ngẫu nhiên và nghịch lý ngày sinh (Mục 5.4.1) — Mục 31.8 dùng RANDOM cho phép thử Miller-Rabin, Mục 31.9 dùng nghịch lý ngày sinh để ước lượng thời gian của heuristic rho Pollard. Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)) cho kỹ thuật ghi nhớ (memoization) dùng trong Problem 31-3. Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)) mở Phần VII "Selected Topics" — các chủ đề chọn lọc, mỗi chương gần như độc lập. Chương 28 ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)) và Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)) cũng thuộc "đại số tính toán": Chương 30 dùng số học modulo và phần tử sinh (căn nguyên thủy của đơn vị) cho FFT, và nhân hai số nguyên lớn nhanh là một ứng dụng của FFT mà phần mở đầu chương này nhắc tới. Chương 31 dựng nền số học (chia hết, ước chung lớn nhất, đồng dư, nhóm hữu hạn), rồi dùng nền đó cho bốn thuật toán: Euclid mở rộng, giải phương trình đồng dư tuyến tính, lũy thừa modulo bằng bình phương lặp, và phép thử nguyên tố Miller-Rabin; tất cả hội tụ vào hệ mật mã khóa công khai RSA. Chương 32 ([C32-so-khop-chuoi.md](C32-so-khop-chuoi.md)) dùng ngay số học modulo cho thuật toán Rabin-Karp (băm chuỗi theo modulo một số nguyên tố). Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)) bàn về lớp P và NP; bài toán phân tích thừa số (Mục 31.9) là ví dụ kinh điển của bài toán chưa biết có thuật toán thời gian đa thức nhưng cũng không được biết là NP-đầy đủ. Phụ lục C ([PC-dem-va-xac-suat.md](PC-dem-va-xac-suat.md)) cho phép thử Bernoulli, phân phối hình học và định lý Bayes mà Mục 31.8 dùng để ước lượng số lần thử khi tìm số nguyên tố lớn và để diễn giải kết quả của Miller-Rabin.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **với số nguyên lớn, "kích thước đầu vào" là SỐ BIT β chứ không phải giá trị n, nên một thuật toán số học chỉ hiệu quả khi chạy đa thức theo β = lg n; và có một khoảng cách lớn giữa những việc làm được nhanh — tính ước chung lớn nhất (O(β) phép toán số học), tìm nghịch đảo modulo, lũy thừa modulo (O(β) phép nhân), kiểm tra một số có phải nguyên tố (Miller-Rabin, sai với xác suất ≤ 2⁻ˢ) — và việc chưa ai làm nhanh được: phân tích một số lớn ra thừa số nguyên tố. Hệ mật mã RSA được xây chính trên khoảng cách đó: tạo khóa thì dễ, phá khóa (nếu không biết cách nào khác ngoài phân tích n) thì khó.** Phần mở đầu chương đặt lại mô hình chi phí: đầu vào lớn là đầu vào chứa số lớn; ta đếm cả số phép toán số học lẫn số phép toán bit (nhân hai số β-bit kiểu thông thường tốn Θ(β²) phép toán bit). Mục 31.1 ôn khái niệm: chia hết, ước, số nguyên tố, hợp số, định lý phép chia, lớp đồng dư, ước chung lớn nhất, nguyên tố cùng nhau; Định lý 31.2: gcd(a, b) là tổ hợp tuyến tính dương nhỏ nhất ax + by; Định lý 31.8 phân tích thừa số nguyên tố duy nhất. Mục 31.2 trình bày thuật toán Euclid dựa trên gcd(a, b) = gcd(b, a mod b), chứng minh số lần gọi đệ quy là O(lg b) qua định lý Lamé (đầu vào xấu nhất là hai số Fibonacci liên tiếp), và bản mở rộng EXTENDED-EUCLID trả thêm hệ số x, y với d = ax + by. Mục 31.3 đặt số học modulo vào khuôn lý thuyết nhóm: nhóm cộng (ℤₙ, +ₙ), nhóm nhân (ℤₙ*, ·ₙ) gồm các số nguyên tố cùng nhau với n, hàm phi Euler φ(n) = |ℤₙ*|, nhóm con, định lý Lagrange (cỡ nhóm con chia hết cỡ nhóm), cấp của phần tử. Mục 31.4 giải phương trình ax ≡ b (mod n): có nghiệm khi và chỉ khi d = gcd(a, n) chia hết b, khi đó có đúng d nghiệm cách nhau n/d; thủ tục MODULAR-LINEAR-EQUATION-SOLVER; nghịch đảo modulo là trường hợp b = 1. Mục 31.5 trình bày định lý số dư Trung Hoa: với n = n₁n₂⋯nₖ các thừa số đôi một nguyên tố cùng nhau, ℤₙ "giống hệt" tích ℤₙ₁ × ⋯ × ℤₙₖ, và có công thức tường minh để đi ngược. Mục 31.6 xét lũy thừa modulo n: định lý Euler a^φ(n) ≡ 1, định lý Fermat a^(p−1) ≡ 1, căn nguyên thủy, logarit rời rạc, căn bậc hai không tầm thường của 1 (có thì n là hợp số), và thủ tục MODULAR-EXPONENTIATION (bình phương lặp). Mục 31.7 trình bày hệ mật mã khóa công khai, chữ ký số và RSA: chọn hai số nguyên tố lớn p, q, n = pq, e nguyên tố cùng nhau với φ(n), d = e⁻¹ mod φ(n); mã hóa M^e mod n, giải mã C^d mod n; chứng minh tính đúng bằng định lý Fermat và định lý số dư Trung Hoa. Mục 31.8 (★) bàn mật độ số nguyên tố (định lý số nguyên tố), phép thử giả nguyên tố cơ số 2 (PSEUDOPRIME) và điểm yếu của nó trước số Carmichael, rồi phép thử ngẫu nhiên Miller-Rabin (WITNESS tìm căn bậc hai không tầm thường của 1) với chứng minh rằng mọi hợp số lẻ có ít nhất (n − 1)/2 bằng chứng nên xác suất sai ≤ 2⁻ˢ. Mục 31.9 (★) trình bày heuristic rho của Pollard: tìm một thừa số p của n sau kỳ vọng Θ(√p) bước nhờ nghịch lý ngày sinh, dùng bộ nhớ hằng số.

> **Lưu ý:**
> - **Hai mục có dấu sao (★) trong chương:** Mục 31.8 "Primality testing" và Mục 31.9 "Integer factorization". Các bài tập có dấu sao: Exercise 31.1-11, 31.4-4, 31.7-3, 31.8-2, 31.9-4. Không có Problem nào mang dấu sao.
> - **Lớp chữ PDF hỏng gần như mọi ký hiệu toán của chương:** β thành `ˇ`, Θ thành `‚`, φ (hàm phi) và π (hàm đếm số nguyên tố) mất hẳn (ví dụ `.n/D n` là `φ(n) = n`, `.10/D 4` là `π(10) = 4`), dấu ≡ mất (ví dụ `ax b. mod n/` là `ax ≡ b (mod n)`), ≤ và ≥ mất, ⟨a⟩ thành `hai`, ℤₙ* thành `Zn` (không phân biệt được với ℤₙ), chỉ số trên dưới dính nhau (`pe11 pe22` là `p₁^e₁ p₂^e₂`, `x2i /NUL1` là `x²ᵢ₋₁`), dấu ⊕ thành `˚`, σ (chữ ký số) mất hẳn, các bảng của Hình 31.2, 31.3 và hình rho (Hình 31.7) vỡ thành chuỗi số rời. Mọi pseudocode (EUCLID, EXTENDED-EUCLID, MODULAR-LINEAR-EQUATION-SOLVER, MODULAR-EXPONENTIATION, PSEUDOPRIME, WITNESS, MILLER-RABIN, POLLARD-RHO), mọi công thức (31.1)–(31.44), các Hình 31.1–31.7 và tất cả định lý, hệ quả trong bản tổng hợp này được đọc lại từ ảnh của toàn bộ 59 trang 926–984.
> - **Chỗ sách viết chưa chặt hoặc có lỗi nhỏ (nhận xét của người tổng hợp):**
>   - Mục 31.9, trang 977: sách viết "k follows the sequence 1, 2, 4, 8, …", nhưng dòng 4 của POLLARD-RHO khởi tạo k = 2, nên giá trị của biến k thực ra là 2, 4, 8, 16, …; dãy 1, 2, 4, 8, … là dãy CHỈ SỐ của các giá trị được lưu vào y (x₁ được lưu ở dòng 3, trước khi có k).
>   - Ghi chú chương, trang 983: tên đồng tác giả thuật toán AKS bị in là "Saxema"; đúng là Nitin **Saxena** (theo hiểu biết của người tổng hợp).
>   - Problem 31-4, trang 982: phương trình định nghĩa thặng dư bậc hai in là "x² = a (mod p)" — đúng ra phải là dấu đồng dư "≡"; câu (b) lặp lại giả thiết "If p is prime" dù p đã được cho là số nguyên tố lẻ.
>   - Mục 31.7, trang 963: câu "After two decades of research, however, no easier method has been found to break the RSA public-key cryptosystem" — RSA ra đời năm 1977, nên tới ấn bản 2009 đã hơn ba thập kỷ; câu này nhiều khả năng giữ nguyên từ ấn bản 1990 hoặc 2001.
>   - Mục 31.5 mở đầu nói Tôn Tử (Sun-Tsŭ) giải bài toán "khoảng năm 100 sau Công nguyên", còn Ghi chú chương lại nói ông sống "trong khoảng 200 TCN tới 200 SCN — niên đại rất không chắc chắn". Hai câu không mâu thuẫn hẳn nhưng nên hiểu năm 100 chỉ là ước đoán.
> - **Mọi ví dụ số trong sách đã được tự kiểm tra lại và đều đúng:** gcd(30, 21) = 3 qua ba lần gọi đệ quy; bảng EXTENDED-EUCLID(99, 78) cho (3, −11, 14) (Hình 31.1); bảng nhân của ℤ₁₅* (Hình 31.2(b)); φ(45) = 24; 5⁻¹ ≡ 9 (mod 11), 7⁻¹ ≡ 13 (mod 15), 4/7 ≡ 7 (mod 15); 14x ≡ 30 (mod 100) có hai nghiệm 95 và 45; bảng định lý số dư Trung Hoa mod 65 (Hình 31.3) và a ≡ 42 (mod 65); bảng lũy thừa của 3 và 2 modulo 7; bảng MODULAR-EXPONENTIATION(7, 560, 561) (Hình 31.4); 6 là căn bậc hai không tầm thường của 1 modulo 35; dãy WITNESS(7, 561) = ⟨241, 298, 166, 67, 1⟩; 22 giả nguyên tố cơ số 2 nhỏ hơn 10.000, bốn số đầu 341, 561, 645, 1105; ln 2¹⁰²⁴ ≈ 709,8 ≈ 710; λ(561) = lcm(2, 10, 16) = 80; dãy rho modulo 1387, 19, 73 (Hình 31.7) và thừa số 19 tìm được ở x₇ = 177. Các đáp số bài tập do người tổng hợp đưa ra (ví dụ EXTENDED-EUCLID(899, 493) = (29, −6, 11); khóa RSA d = 187 và bản mã 254 ở Exercise 31.7-1; thừa số 73 được in ở bước i = 12 ở Exercise 31.9-1) cũng đã được tính lại.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương vẫn là Chương 31 "Number-Theoretic Algorithms" với cùng mạch nội dung (Euclid, số học modulo, định lý số dư Trung Hoa, lũy thừa, RSA, Miller-Rabin). Người tổng hợp nhớ rằng ấn bản 4 cập nhật lời văn về độ dài khóa RSA và về các thuật toán nhân số nguyên nhanh, nhưng không nhớ chắc chi tiết nào khác (ví dụ Mục 31.9 có được giữ nguyên hay không), nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 31.1, trang 926–927) — vì sao lý thuyết số trở thành thực dụng, và cách đo chi phí với số lớn

```text
       Lý thuyết số từng bị coi là "đẹp nhưng vô dụng"
                                │
                                ▼
       Nay được dùng rộng rãi nhờ các hệ mật mã dựa trên số nguyên tố lớn:
       · KHẢ THI vì ta tìm được số nguyên tố lớn một cách dễ dàng
       · AN TOÀN vì chưa ai biết cách phân tích nhanh tích của hai số
         nguyên tố lớn (hay giải nhanh các bài toán liên quan như
         logarit rời rạc)
                                │
                                ▼
       Trình tự chương:
       31.1 khái niệm cơ bản      31.2 thuật toán Euclid tính gcd
       31.3 số học modulo         31.4 giải ax ≡ b (mod n)
       31.5 định lý số dư Trung Hoa
       31.6 lũy thừa modulo, bình phương lặp
       31.7 hệ mật mã RSA         31.8★ phép thử nguyên tố ngẫu nhiên
       31.9★ heuristic phân tích thừa số cho số nhỏ
                                │
                                ▼
       KÍCH THƯỚC ĐẦU VÀO VÀ CHI PHÍ PHÉP TOÁN
       · "đầu vào lớn" = đầu vào chứa SỐ LỚN (không phải chứa NHIỀU số)
       · kích thước đo bằng SỐ BIT; thuật toán thời gian đa thức nếu chạy
         đa thức theo lg a₁, lg a₂, …, lg aₖ
       · đếm hai thứ: số PHÉP TOÁN SỐ HỌC và số PHÉP TOÁN BIT
       · nhân hai số β-bit kiểu thông thường: Θ(β²) phép toán bit;
         chia, lấy dư cho số ngắn hơn: Θ(β²)
       · có cách nhanh hơn: chia để trị Θ(β^lg 3); nhanh nhất (năm 2009)
         Θ(β lg β lg lg β); nhưng sách dùng Θ(β²) làm cơ sở phân tích
```

### Mục 31.1 — Các khái niệm số học sơ cấp (Elementary number-theoretic notions, trang 927–933)

```text
       CHIA HẾT: d | a ("d chia hết a") nghĩa là a = kd với k nguyên
       · d ≥ 0 và d | a thì d là ƯỚC (divisor) của a
       · ước tầm thường của a > 0: 1 và a; các ước còn lại là THỪA SỐ
         ví dụ: ước của 24 là 1, 2, 3, 4, 6, 8, 12, 24; thừa số của 20
         là 2, 4, 5, 10
                                │
                                ▼
       SỐ NGUYÊN TỐ: a > 1 chỉ có hai ước tầm thường (2, 3, 5, 7, 11, …)
       HỢP SỐ: a > 1 không nguyên tố (39 vì 3 | 39)
       Số 1 là "đơn vị", không nguyên tố cũng không hợp số; 0 và số âm
       cũng không
                                │
                                ▼
       ĐỊNH LÝ 31.1 (phép chia): với n > 0 có duy nhất q, r:
       a = qn + r, 0 ≤ r < n;  q = ⌊a/n⌋ (thương), r = a mod n (số dư)
       LỚP ĐỒNG DƯ [a]ₙ = {a + kn : k ∈ ℤ}; ℤₙ = {[0]ₙ, …, [n−1]ₙ},
       viết gọn ℤₙ = {0, 1, …, n−1}
                                │
                                ▼
       ƯỚC CHUNG LỚN NHẤT gcd(a, b): ước chung lớn nhất của a, b (không
       cùng bằng 0); gcd(0, 0) = 0 theo quy ước
       Tính chất (31.3)–(31.10): d | a, d | b ⇒ d | (ax + by);
       gcd(a, b) = gcd(b, a) = gcd(−a, b) = gcd(|a|, |b|); gcd(a, 0) = |a|
                                │
                                ▼
       ĐỊNH LÝ 31.2: gcd(a, b) là phần tử DƯƠNG NHỎ NHẤT của tập các tổ
       hợp tuyến tính {ax + by : x, y ∈ ℤ}
       Hệ quả: 31.3 mọi ước chung chia hết gcd; 31.4 gcd(an, bn) =
       n·gcd(a, b); 31.5 n | ab và gcd(a, n) = 1 ⇒ n | b
                                │
                                ▼
       NGUYÊN TỐ CÙNG NHAU: gcd(a, b) = 1 (ví dụ 8 và 15)
       Định lý 31.6: gcd(a, p) = gcd(b, p) = 1 ⇒ gcd(ab, p) = 1
       Định lý 31.7: p nguyên tố, p | ab ⇒ p | a hoặc p | b
       Định lý 31.8: mọi hợp số phân tích DUY NHẤT thành p₁^e₁ ⋯ pᵣ^eᵣ
       (ví dụ 6000 = 2⁴ · 3 · 5³)
```

### Mục 31.2 — Ước chung lớn nhất (Greatest common divisor, trang 933–939)

```text
       Cách "ngây thơ": phân tích a, b ra thừa số nguyên tố rồi lấy số mũ
       nhỏ nhất (31.13) — nhưng phân tích thừa số chưa có thuật toán
       đa thức, nên cách này không hiệu quả
                                │
                                ▼
       ĐỊNH LÝ 31.9 (đệ quy gcd): gcd(a, b) = gcd(b, a mod b), b > 0
       (chứng minh: hai vế chia hết lẫn nhau, đều không âm nên bằng nhau)
                                │
                                ▼
       EUCLID(a, b): b = 0 thì trả về a; ngược lại trả về
       EUCLID(b, a mod b)
       Ví dụ: EUCLID(30,21) = EUCLID(21,9) = EUCLID(9,3) = EUCLID(3,0) = 3
                                │
                                ▼
       THỜI GIAN CHẠY (giả sử a > b ≥ 0)
       · Bổ đề 31.10: a > b ≥ 1 và có k ≥ 1 lần gọi đệ quy
         ⇒ a ≥ F_{k+2}, b ≥ F_{k+1}   (chứng minh quy nạp:
         a ≥ b + (a mod b) ≥ F_{k+1} + F_k)
       · Định lý 31.11 (Lamé): b < F_{k+1} ⇒ ít hơn k lần gọi đệ quy
       · cận này chặt: EUCLID(F_{k+1}, F_k) gọi đúng k − 1 lần
       · F_k ≈ φᵏ/√5 ⇒ số lần gọi O(lg b)
       · với hai số β-bit: O(β) phép toán số học, O(β³) phép toán bit
         (Problem 31-2 hạ xuống O(β²))
                                │
                                ▼
       EXTENDED-EUCLID(a, b) trả về (d, x, y) với d = gcd(a,b) = ax + by
       · b = 0: trả về (a, 1, 0)
       · ngược lại (d′, x′, y′) = EXTENDED-EUCLID(b, a mod b) rồi
         (d, x, y) = (d′, y′, x′ − ⌊a/b⌋ y′)
       · ví dụ: EXTENDED-EUCLID(99, 78) = (3, −11, 14):
         3 = 99·(−11) + 78·14
       · cùng số lần gọi đệ quy như EUCLID: O(lg b)
```

### Mục 31.3 — Số học modulo (Modular arithmetic, trang 939–946)

```text
       Trực giác: tính như số nguyên thường, rồi thay kết quả x bằng
       x mod n. Đủ cho cộng, trừ, nhân; phép chia cần khuôn lý thuyết nhóm
                                │
                                ▼
       NHÓM (S, ⊕): tập S với phép toán hai ngôi thỏa
       đóng · có phần tử đơn vị e · kết hợp · mỗi phần tử có nghịch đảo
       duy nhất. Giao hoán ⇒ nhóm ABEL; |S| < ∞ ⇒ nhóm HỮU HẠN
                                │
           ┌────────────────────┴─────────────────────┐
           ▼                                          ▼
   NHÓM CỘNG MODULO n (ℤₙ, +ₙ)               NHÓM NHÂN MODULO n (ℤₙ*, ·ₙ)
   · n phần tử, đơn vị 0,                    · ℤₙ* = {[a]ₙ : gcd(a, n) = 1}
     nghịch đảo của a là −a                  · đơn vị 1; nghịch đảo tìm
   · Định lý 31.12: nhóm Abel hữu hạn          bằng EXTENDED-EUCLID(a, n)
   · ví dụ (ℤ₆, +₆)                          · Định lý 31.13: nhóm Abel
                                               hữu hạn; ví dụ ℤ₁₅* =
                                               {1,2,4,7,8,11,13,14}
           └────────────────────┬─────────────────────┘
                                ▼
       HÀM PHI EULER φ(n) = |ℤₙ*| = n · Π_{p nguyên tố, p | n} (1 − 1/p)
       φ(45) = 45·(2/3)·(4/5) = 24;  p nguyên tố ⇒ φ(p) = p − 1
       n hợp số ⇒ φ(n) < n − 1, nhưng φ(n) > n/(e^γ ln ln n + 3/ln ln n)
                                │
                                ▼
       NHÓM CON: tập con S′ cũng là nhóm với cùng phép toán
       · Định lý 31.14: tập con khác rỗng, đóng, của nhóm hữu hạn là
         nhóm con
       · Định lý 31.15 (Lagrange): |S′| chia hết |S|
       · Hệ quả 31.16: nhóm con THỰC SỰ có |S′| ≤ |S|/2
         (dùng ở Mục 31.8 để đếm số "không bằng chứng")
                                │
                                ▼
       NHÓM CON SINH BỞI a: ⟨a⟩ = {a^(k) : k ≥ 1}
       (a^(k) = ka mod n trong ℤₙ; aᵏ mod n trong ℤₙ*)
       · CẤP ord(a): t nhỏ nhất với a^(t) = e
       · Định lý 31.17: ord(a) = |⟨a⟩|;  Hệ quả 31.18: dãy a^(1), a^(2), …
         tuần hoàn chu kỳ ord(a)
       · Hệ quả 31.19: a^(|S|) = e với mọi a ∈ S
```

### Mục 31.4 — Giải phương trình tuyến tính modulo (Solving modular linear equations, trang 946–950)

```text
       Bài toán: tìm mọi x (mod n) thỏa ax ≡ b (mod n),  a > 0, n > 0
       Có nghiệm ⇔ [b] ∈ ⟨a⟩ (nhóm con của ℤₙ sinh bởi a)
                                │
                                ▼
       ĐỊNH LÝ 31.20: d = gcd(a, n) ⇒ ⟨a⟩ = ⟨d⟩ = {0, d, 2d, …, (n/d − 1)d},
       |⟨a⟩| = n/d
                                │
                                ▼
       Hệ quả 31.21: có nghiệm ⇔ d | b
       Hệ quả 31.22: hoặc có ĐÚNG d nghiệm phân biệt modulo n, hoặc vô nghiệm
                                │
                                ▼
       Định lý 31.23: nếu d = ax′ + ny′ (từ EXTENDED-EUCLID) và d | b
       thì x₀ = x′(b/d) mod n là một nghiệm
       Định lý 31.24: mọi nghiệm là xᵢ = x₀ + i(n/d), i = 0, 1, …, d − 1
                                │
                                ▼
       MODULAR-LINEAR-EQUATION-SOLVER(a, b, n):
       gọi EXTENDED-EUCLID(a, n); nếu d | b in d nghiệm cách nhau n/d,
       ngược lại in "no solutions"
       Chi phí: O(lg n + gcd(a, n)) phép toán số học
       Ví dụ 14x ≡ 30 (mod 100): (d, x′, y′) = (2, −7, 1), x₀ = 95;
       hai nghiệm 95 và 45
                                │
                                ▼
       Hệ quả 31.25: gcd(a, n) = 1 ⇒ ax ≡ b có nghiệm duy nhất
       Hệ quả 31.26: gcd(a, n) = 1 ⇒ ax ≡ 1 có nghiệm duy nhất —
       NGHỊCH ĐẢO MODULO a⁻¹ mod n, chính là x mà EXTENDED-EUCLID trả về
```

### Mục 31.5 — Định lý số dư Trung Hoa (The Chinese remainder theorem, trang 950–954)

```text
       Bài toán cổ (Tôn Tử, khoảng năm 100): số nào chia 3, 5, 7 dư lần
       lượt 2, 3, 2?  Đáp: 23 + 105k
                                │
                                ▼
       ĐỊNH LÝ 31.27: n = n₁n₂⋯nₖ, các nᵢ ĐÔI MỘT NGUYÊN TỐ CÙNG NHAU
       Ánh xạ a ↔ (a mod n₁, …, a mod nₖ) là SONG ÁNH giữa ℤₙ và
       ℤₙ₁ × ⋯ × ℤₙₖ; cộng, trừ, nhân thực hiện độc lập trên từng thành phần
                                │
           ┌────────────────────┴─────────────────────┐
           ▼                                          ▼
   CHIỀU XUÔI: a ↦ (a₁, …, aₖ)              CHIỀU NGƯỢC: (a₁, …, aₖ) ↦ a
   chỉ cần k phép "mod"                     mᵢ = n/nᵢ;  cᵢ = mᵢ(mᵢ⁻¹ mod nᵢ)
                                            cᵢ ↔ (0, …, 0, 1, 0, …, 0)
                                            a ≡ a₁c₁ + ⋯ + aₖcₖ (mod n)
           └────────────────────┬─────────────────────┘
                                ▼
       Hệ quả 31.28: hệ x ≡ aᵢ (mod nᵢ) có nghiệm duy nhất modulo n
       Hệ quả 31.29: x ≡ a (mod nᵢ) với mọi i ⇔ x ≡ a (mod n)
                                │
                                ▼
       Ví dụ: a ≡ 2 (mod 5), a ≡ 3 (mod 13): c₁ = 26, c₂ = 40,
       a ≡ 2·26 + 3·40 = 172 ≡ 42 (mod 65)
       Bảng 5 × 13: đi xuống một hàng cộng 26, sang phải một cột cộng 40
```

### Mục 31.6 — Lũy thừa của một phần tử (Powers of an element, trang 954–958)

```text
       Dãy lũy thừa a⁰, a¹, a², … modulo n (a ∈ ℤₙ*)
       ví dụ 3ⁱ mod 7: 1,3,2,6,4,5,1,…   2ⁱ mod 7: 1,2,4,1,2,4,…
       ordₙ(a): cấp của a trong ℤₙ*; ord₇(2) = 3
                                │
                                ▼
       ĐỊNH LÝ 31.30 (Euler): a^φ(n) ≡ 1 (mod n) với mọi a ∈ ℤₙ*
       ĐỊNH LÝ 31.31 (Fermat): p nguyên tố ⇒ a^(p−1) ≡ 1 (mod p),
       a ∈ ℤₚ*
                                │
                                ▼
       CĂN NGUYÊN THỦY g: ordₙ(g) = |ℤₙ*|; khi đó ℤₙ* là nhóm CYCLIC
       (3 là căn nguyên thủy modulo 7, 2 thì không)
       Định lý 31.32: ℤₙ* cyclic ⇔ n = 2, 4, pᵉ, 2pᵉ (p nguyên tố lẻ)
       LOGARIT RỜI RẠC ind_{n,g}(a): số z với gᶻ ≡ a (mod n)
       Định lý 31.33: gˣ ≡ gʸ (mod n) ⇔ x ≡ y (mod φ(n))
                                │
                                ▼
       CĂN BẬC HAI CỦA 1
       Định lý 31.34: p nguyên tố lẻ ⇒ x² ≡ 1 (mod pᵉ) chỉ có x ≡ ±1
       Căn bậc hai KHÔNG TẦM THƯỜNG của 1 mod n: x² ≡ 1 nhưng x ≢ ±1
       (6 modulo 35)
       Hệ quả 31.35: có căn bậc hai không tầm thường của 1 mod n
       ⇒ n là HỢP SỐ   (nền của phép thử Miller-Rabin)
                                │
                                ▼
       MODULAR-EXPONENTIATION(a, b, n) — BÌNH PHƯƠNG LẶP
       · duyệt bit của b từ cao xuống thấp; mỗi bước bình phương d, gặp
         bit 1 thì nhân thêm a
       · bất biến: c là tiền tố nhị phân đã duyệt của b, d = aᶜ mod n
       · O(β) phép toán số học, O(β³) phép toán bit
       · ví dụ 7⁵⁶⁰ mod 561 = 1
```

### Mục 31.7 — Hệ mật mã khóa công khai RSA (The RSA public-key cryptosystem, trang 958–965)

```text
       HỆ MẬT MÃ KHÓA CÔNG KHAI: mỗi người có KHÓA CÔNG KHAI P và KHÓA
       BÍ MẬT S; hàm P() và S() là hai hoán vị ngược nhau của tập thông
       điệp 𝒟:  M = S_A(P_A(M)) = P_A(S_A(M))           (31.35), (31.36)
       Yêu cầu: chỉ Alice tính được S_A() dù ai cũng biết P_A
                                │
           ┌────────────────────┴─────────────────────┐
           ▼                                          ▼
   MÃ HÓA (Bob gửi Alice)                    CHỮ KÝ SỐ (Alice ký gửi Bob)
   · Bob tính C = P_A(M), gửi C              · Alice tính σ = S_A(M′),
   · Alice giải mã S_A(C) = M                  gửi cặp (M′, σ)
   · kẻ nghe lén chỉ thấy C                  · Bob kiểm tra M′ = P_A(σ)
                                             · ai có P_A cũng kiểm tra được;
                                               sửa một bit là chữ ký hỏng
           └────────────────────┬─────────────────────┘
                                ▼
       TẠO KHÓA RSA
       1. chọn ngẫu nhiên hai số nguyên tố lớn p ≠ q (ví dụ 1024 bit)
       2. n = pq
       3. chọn e lẻ nhỏ, nguyên tố cùng nhau với φ(n) = (p−1)(q−1)
       4. d = e⁻¹ mod φ(n)   (EXTENDED-EUCLID, Mục 31.4)
       5. công bố P = (e, n);  6. giữ bí mật S = (d, n)
       P(M) = Mᵉ mod n  (31.37);   S(C) = Cᵈ mod n  (31.38)
                                │
                                ▼
       Chi phí: áp khóa công khai O(1) phép nhân modulo, O(β²) phép toán
       bit; áp khóa bí mật O(β) phép nhân, O(β³) phép toán bit
                                │
                                ▼
       ĐỊNH LÝ 31.36 (tính đúng): M^(ed) ≡ M (mod n) với mọi M
       (ed = 1 + k(p−1)(q−1); Fermat cho modulo p và q; ghép bằng
        Hệ quả 31.29)
                                │
                                ▼
       AN TOÀN: phân tích được n ⇒ phá được RSA; chiều ngược lại CHƯA
       được chứng minh, nhưng chưa ai tìm ra cách phá dễ hơn
       Thực tế (2009): modulus 768–2048 bit; dùng chế độ LAI (RSA chỉ mã
       hóa khóa ngắn K của hệ mã đối xứng nhanh), ký lên dấu vân tay
       h(M) của HÀM BĂM CHỐNG VA CHẠM, phân phối khóa qua CHỨNG CHỈ
```

### Mục 31.8 ★ — Kiểm tra tính nguyên tố (Primality testing, trang 965–975)

```text
       MẬT ĐỘ SỐ NGUYÊN TỐ
       π(n) = số số nguyên tố ≤ n;  Định lý 31.37: π(n) ~ n/ln n
       π(10⁹) = 50.847.534, n/ln n ≈ 48.254.942
       ⇒ thử ngẫu nhiên khoảng ln n số gần n là gặp một số nguyên tố
         (số 1024 bit: khoảng 710 lần thử, 355 nếu chỉ thử số lẻ)
                                │
                                ▼
       CHIA THỬ cho 2, 3, …, ⌊√n⌋: Θ(√n) = Θ(2^(β/2)) — hàm mũ theo β
                                │
                                ▼
       PHÉP THỬ GIẢ NGUYÊN TỐ (PSEUDOPRIME)
       · n là GIẢ NGUYÊN TỐ CƠ SỐ a nếu n hợp số mà a^(n−1) ≡ 1 (mod n)
       · thử với a = 2: khác 1 ⇒ HỢP SỐ (chắc chắn); bằng 1 ⇒ "NGUYÊN TỐ"
         (hy vọng vậy)
       · chỉ sai với 22 số < 10.000 (341, 561, 645, 1105, …);
         số 1024 bit ngẫu nhiên: xác suất sai < 10⁻⁴¹
       · nhưng SỐ CARMICHAEL (561, 1105, 1729) thỏa a^(n−1) ≡ 1 với MỌI
         a ∈ ℤₙ* ⇒ thử thêm cơ số không cứu được
                                │
                                ▼
       MILLER-RABIN(n, s): hai cải tiến
       · thử s cơ số a NGẪU NHIÊN
       · trong lúc lũy thừa, tìm CĂN BẬC HAI KHÔNG TẦM THƯỜNG của 1
                                │
                                ▼
       WITNESS(a, n): viết n − 1 = 2ᵗu (u lẻ); x₀ = aᵘ mod n;
       bình phương t lần: xᵢ = xᵢ₋₁² mod n
       · xᵢ = 1 mà xᵢ₋₁ ≠ ±1 ⇒ TRUE (xᵢ₋₁ là căn không tầm thường của 1)
       · xₜ ≠ 1 ⇒ TRUE (vi phạm Fermat)
       · còn lại FALSE
       Ví dụ n = 561, a = 7: X = ⟨241, 298, 166, 67, 1⟩, 67² ≡ 1 ⇒ hợp số
                                │
                                ▼
       ĐỊNH LÝ 31.38: n hợp số lẻ ⇒ có ít nhất (n − 1)/2 BẰNG CHỨNG
       · mọi "không bằng chứng" thuộc ℤₙ* và nằm trong một nhóm con
         THỰC SỰ B của ℤₙ* ⇒ |B| ≤ |ℤₙ*|/2 ≤ (n − 1)/2
       · Trường hợp 1 (n không phải số Carmichael):
         B = {b : b^(n−1) ≡ 1}
       · Trường hợp 2 (n là số Carmichael): n không phải lũy thừa số
         nguyên tố; n = n₁n₂; B = {x : x^(2ʲu) ≡ ±1}; dựng w ∉ B bằng
         định lý số dư Trung Hoa
                                │
                                ▼
       ĐỊNH LÝ 31.39: Pr{MILLER-RABIN(n, s) sai} ≤ 2⁻ˢ, với MỌI n lẻ
       · O(sβ) phép toán số học, O(sβ³) phép toán bit
       · với n ngẫu nhiên β bit, theo Bayes: Pr{n nguyên tố | báo PRIME}
         ≈ 1/(1 + 2⁻ˢ(ln n − 1)); số 1024 bit cần khoảng 9 lần thử chỉ để
         vượt định kiến ban đầu; s = 50 đủ cho mọi ứng dụng
```

### Mục 31.9 ★ — Phân tích số nguyên ra thừa số (Integer factorization, trang 975–980)

```text
       Phân tích thừa số khó hơn hẳn kiểm tra nguyên tố: năm 2009 chưa ai
       phân tích được một số 1024 bit tùy ý
                                │
                                ▼
       Chia thử tới R phân tích được mọi số tới R²; cùng lượng việc,
       POLLARD-RHO phân tích được số tới R⁴ (nếu không xui)
                                │
                                ▼
       POLLARD-RHO(n)
       · dãy xᵢ = (xᵢ₋₁² − 1) mod n, x₁ ngẫu nhiên
       · lưu y = x₁, x₂, x₄, x₈, … (các chỉ số là lũy thừa của 2)
       · mỗi bước tính d = gcd(y − xᵢ, n); 1 < d < n thì in d
       · chỉ dùng hằng số ô nhớ; không bao giờ in sai, nhưng có thể
         không in gì
                                │
                                ▼
       VÌ SAO HIỆU QUẢ
       · coi fₙ(x) = (x² − 1) mod n như hàm ngẫu nhiên: theo nghịch lý ngày
         sinh, dãy lặp lại sau Θ(√n) bước — hình chữ ρ (đuôi + vòng)
       · p là thừa số của n: dãy x′ᵢ = xᵢ mod p theo CÙNG công thức và
         lặp lại sau chỉ Θ(√p) bước
       · khi x′ᵢ ≡ y′ (mod p): p | (y − xᵢ) ⇒ gcd(y − xᵢ, n) > 1
       · kỳ vọng Θ(√p) bước để tìm p; phân tích hết số β bit cần
         khoảng n^(1/4) = 2^(β/4) phép toán số học
                                │
                                ▼
       Ví dụ n = 1387 = 19 · 73, x₁ = 2:
       2, 3, 8, 63, 1194, 1186, 177, …;  ở x₇ = 177, y = x₄ = 63:
       gcd(63 − 177, 1387) = 19
                                │
                                ▼
       Hai rủi ro: phân tích chỉ là heuristic; có thể chỉ tìm ra n.
       Khi đó khởi động lại với xᵢ₊₁ = (xᵢ² − c) mod n (tránh c = 0, 2)
```

### Bài toán cuối chương (Problems 31-1 đến 31-4, trang 981–982)

```text
       31-1 Thuật toán gcd nhị phân: chỉ dùng trừ, kiểm tra chẵn lẻ, chia
            đôi; gcd(a,b) = 2gcd(a/2,b/2) nếu cả hai chẵn; = gcd(a,b/2) nếu
            a lẻ b chẵn; = gcd((a−b)/2, b) nếu cả hai lẻ; chạy O(lg a)
                                │
                                ▼
       31-2 Đếm phép toán bit trong Euclid: chia viết tay tốn
            O((1 + lg q) lg b); với μ(a,b) = (1 + lg a)(1 + lg b), mỗi bước
            đệ quy tốn ≤ c(μ(a,b) − μ(b, a mod b)) ⇒ tổng O(β²)
                                │
                                ▼
       31-3 Ba cách tính số Fibonacci Fₙ: đệ quy thẳng (hàm mũ), ghi nhớ
            O(n), lũy thừa ma trận [[0,1],[1,1]] O(lg n); và chi phí thật
            khi tính cả độ dài bit
                                │
                                ▼
       31-4 Thặng dư bậc hai modulo p: có đúng (p−1)/2 thặng dư; ký hiệu
            Legendre (a/p) ≡ a^((p−1)/2); p = 4k + 3 thì a^(k+1) là căn bậc
            hai của a; tìm phi thặng dư bằng thử ngẫu nhiên
```

### Ghi chú chương (Chapter notes, trang 982–984)

```text
       Tài liệu nền: Niven–Zuckerman (lý thuyết số sơ cấp), Knuth (gcd và
       thuật toán số học), Bach, Riesel, Dixon, Pomerance, Bach–Shallit
                                │
                                ▼
       Thuật toán Euclid: Sách VII, Mệnh đề 1–2 của bộ "Cơ sở" (khoảng
       300 TCN), có thể có từ Eudoxus (khoảng 375 TCN) — có lẽ là thuật toán
       không tầm thường cổ nhất, chỉ kém phép nhân của người Ai Cập cổ
                                │
                                ▼
       Định lý số dư Trung Hoa: Tôn Tử (200 TCN – 200 SCN, không chắc),
       Nicomachus (khoảng năm 100), Tần Cửu Thiều tổng quát hóa (1247),
       Euler chứng minh đầy đủ (1734)
                                │
                                ▼
       Phép thử nguyên tố: Miller và Rabin; chứng minh Định lý 31.39 theo
       Bach; Monier chứng minh kết quả mạnh hơn. 2002: Agrawal, Kayal,
       Saxena — thuật toán TẤT ĐỊNH thời gian đa thức (AKS); trước đó tốt
       nhất là Cohen–Lenstra (lg n)^O(lg lg lg n). Thực tế vẫn dùng phép thử
       ngẫu nhiên vì nhanh hơn
                                │
                                ▼
       Khóa công khai: Diffie–Hellman; RSA: Rivest, Shamir, Adleman (1977);
       Goldwasser–Micali (mã hóa ngẫu nhiên an toàn), Goldwasser–Micali–
       Rivest (chữ ký mà mọi kiểu giả mạo đều khó như phân tích thừa số)
                                │
                                ▼
       Phân tích thừa số: rho của Pollard (bản trong sách là biến thể của
       Brent); sàng trường số tổng quát ≈ L(1/3, n)^(1,902+o(1)); phương
       pháp đường cong elliptic của Lenstra tìm thừa số nhỏ p trong
       ≈ L(1/2, p)^(√2+o(1)), với L(α, n) = e^((ln n)^α (ln ln n)^(1−α))
```

## Ba câu hỏi chương này trả lời

1. **Vì sao với số lớn ta phải đo chi phí theo số bit, và thuật toán Euclid nhanh tới mức nào?** Một số n chỉ cần β = ⌈lg(n + 1)⌉ bit để ghi, nên thuật toán chạy Θ(n) bước (như chia thử tới √n) thực ra là hàm mũ theo kích thước đầu vào: với n 1024 bit, √n ≈ 2⁵¹². Thuật toán "tốt" phải chạy đa thức theo β. Euclid đạt điều đó: dựa trên gcd(a, b) = gcd(b, a mod b) (Định lý 31.9), số lần gọi đệ quy bị chặn bởi định lý Lamé — nếu có k lần gọi thì b ≥ F_{k+1} ≈ φ^(k+1)/√5 — nên chỉ O(lg b) = O(β) lần, tức O(β) phép toán số học và O(β³) phép toán bit (Problem 31-2 hạ còn O(β²)). Đầu vào xấu nhất là hai số Fibonacci liên tiếp: EUCLID(F_{k+1}, F_k) gọi đệ quy đúng k − 1 lần. Bản mở rộng EXTENDED-EUCLID trả thêm x, y với gcd(a, b) = ax + by, ví dụ 3 = 99 · (−11) + 78 · 14, và chính cặp hệ số này cho nghịch đảo modulo.
2. **Làm sao giải phương trình đồng dư và "chia" trong số học modulo, và RSA dựa vào những kết quả nào?** Phương trình ax ≡ b (mod n) có nghiệm khi và chỉ khi d = gcd(a, n) chia hết b; khi đó có đúng d nghiệm x₀ + i(n/d) với x₀ = x′(b/d) mod n, x′ lấy từ EXTENDED-EUCLID (Định lý 31.20–31.24); ví dụ 14x ≡ 30 (mod 100) có nghiệm 95 và 45. Khi gcd(a, n) = 1 có nghịch đảo a⁻¹ mod n duy nhất. RSA chọn n = pq, e nguyên tố cùng nhau với φ(n) = (p − 1)(q − 1), d = e⁻¹ mod φ(n); mã hóa Mᵉ mod n và giải mã Cᵈ mod n bằng bình phương lặp (O(β) phép nhân). Tính đúng: ed = 1 + k(p − 1)(q − 1), định lý Fermat cho M^(ed) ≡ M theo modulo p và modulo q, rồi định lý số dư Trung Hoa ghép thành M^(ed) ≡ M (mod n). Ví dụ của người tổng hợp (Exercise 31.7-1): p = 11, q = 29, e = 3 cho d = 187; M = 100 mã hóa thành 254, và 254¹⁸⁷ mod 319 = 100.
3. **Vì sao kiểm tra một số có nguyên tố hay không lại dễ hơn nhiều so với phân tích nó ra thừa số?** Định lý Fermat cho một "phép thử phủ định": nếu a^(n−1) ≢ 1 (mod n) thì n chắc chắn là hợp số. Phép thử chỉ dùng a = 2 sai rất hiếm (22 số dưới 10.000) nhưng bị số Carmichael (561 = 3 · 11 · 17, …) đánh lừa với mọi cơ số. Miller-Rabin vá lỗ hổng bằng cách vừa chọn cơ số ngẫu nhiên vừa tìm căn bậc hai không tầm thường của 1 trong chuỗi bình phương (có căn như vậy thì n là hợp số, Hệ quả 31.35). Định lý 31.38 chứng minh mọi hợp số lẻ có ít nhất (n − 1)/2 cơ số "làm chứng", nên s lần thử sai với xác suất ≤ 2⁻ˢ, mất O(sβ³) phép toán bit. Ngược lại, biết n là hợp số không cho biết thừa số; heuristic tốt nhất trong chương (rho Pollard) cần kỳ vọng Θ(√p) bước để tìm thừa số p, tức tới 2^(β/4) bước với p ≈ √n — vẫn là hàm mũ theo β. RSA an toàn chính nhờ khoảng cách này.

## Khái niệm cần biết

- **Kích thước đầu vào tính bằng bit (input size in bits):** một số nguyên n dương cần β = ⌈lg(n + 1)⌉ bit. Thuật toán với đầu vào số nguyên a₁, …, aₖ là đa thức nếu chạy đa thức theo lg a₁, …, lg aₖ. Ví dụ n = 1.000.000 chỉ có β = 20 bit; chia thử tới √n = 1000 lần là khoảng 2^(β/2) — hàm mũ theo β. Quan trọng vì mọi đánh giá "nhanh" hay "chậm" trong chương đều theo β.
- **Phép toán bit (bit operation):** đơn vị chi phí khi số lớn: nhân hai số β-bit theo cách viết tay tốn Θ(β²) phép toán bit. Ví dụ nhân hai số 1024 bit tốn cỡ 10⁶ phép toán bit, chứ không phải "1 bước". Quan trọng vì mỗi thuật toán được phân tích hai lần: số phép toán số học và số phép toán bit (EUCLID: O(β) và O(β³)).
- **Chia hết, ước, thừa số (divides, divisor, factor):** d | a khi a = kd; ước tầm thường là 1 và a; các ước còn lại là thừa số. Ví dụ thừa số của 20 là 2, 4, 5, 10. Quan trọng vì "phân tích thừa số" là bài toán khó mà RSA dựa vào.
- **Số nguyên tố, hợp số (prime, composite):** a > 1 chỉ có ước 1 và a là nguyên tố; a > 1 không nguyên tố là hợp số; 1 không thuộc loại nào. Ví dụ 39 = 3 · 13 là hợp số. Quan trọng vì RSA cần hai số nguyên tố lớn và Mục 31.8 kiểm tra tính nguyên tố.
- **Định lý phép chia, số dư (division theorem, remainder):** a = qn + r, 0 ≤ r < n duy nhất; q = ⌊a/n⌋, r = a mod n. Ví dụ −11 = (−2) · 7 + 3 nên −11 mod 7 = 3. Quan trọng vì mọi thuật toán của chương dùng "mod".
- **Lớp đồng dư và ℤₙ (equivalence class, ℤₙ):** [a]ₙ = {a + kn}; a ≡ b (mod n) khi a ∈ [b]ₙ. Ví dụ [3]₇ = {…, −11, −4, 3, 10, 17, …} = [−4]₇ = [10]₇. ℤₙ = {0, 1, …, n − 1}, mỗi số đại diện cho một lớp; "−1 trong ℤₙ" nghĩa là n − 1.
- **Ước chung lớn nhất (greatest common divisor, gcd):** ước chung lớn nhất của a và b. Ví dụ gcd(24, 30) = 6, gcd(5, 7) = 1, gcd(0, 9) = 9, quy ước gcd(0, 0) = 0. Quan trọng vì nó quyết định số nghiệm của phương trình đồng dư và sự tồn tại nghịch đảo.
- **Tổ hợp tuyến tính (linear combination):** số dạng ax + by với x, y nguyên. Định lý 31.2: gcd(a, b) là tổ hợp tuyến tính dương nhỏ nhất. Ví dụ 3 = 99 · (−11) + 78 · 14 là tổ hợp dương nhỏ nhất của 99 và 78. Quan trọng vì đây là "chìa" của gần như mọi chứng minh trong chương.
- **Nguyên tố cùng nhau, đôi một nguyên tố cùng nhau (relatively prime, pairwise relatively prime):** gcd(a, b) = 1; một dãy số đôi một nguyên tố cùng nhau nếu mọi cặp có gcd = 1. Ví dụ 8 và 15; dãy 3, 5, 7. Quan trọng vì định lý số dư Trung Hoa yêu cầu các modulus đôi một nguyên tố cùng nhau.
- **Phân tích thừa số nguyên tố duy nhất (unique factorization):** mọi hợp số viết duy nhất dạng p₁^e₁ p₂^e₂ ⋯ pᵣ^eᵣ với p₁ < p₂ < ⋯ < pᵣ. Ví dụ 6000 = 2⁴ · 3 · 5³. Quan trọng vì công thức φ(n) và chứng minh Miller-Rabin dùng dạng này.
- **Thuật toán Euclid và Euclid mở rộng (Euclid's algorithm, EXTENDED-EUCLID):** tính gcd bằng cách thay (a, b) bằng (b, a mod b) tới khi b = 0; bản mở rộng thu thêm x, y với d = ax + by. Ví dụ (99, 78) → (78, 21) → (21, 15) → (15, 6) → (6, 3) → (3, 0), gcd = 3. Quan trọng vì đây là thủ tục con của giải phương trình đồng dư, nghịch đảo modulo và tạo khóa RSA.
- **Số Fibonacci và tỉ số vàng (Fibonacci numbers, golden ratio):** F₀ = 0, F₁ = 1, Fᵢ = Fᵢ₋₁ + Fᵢ₋₂; φ = (1 + √5)/2 ≈ 1,618, Fₖ ≈ φᵏ/√5. Ví dụ EUCLID(F₇, F₆) = EUCLID(13, 8) gọi đệ quy đúng 5 lần: (8, 5), (5, 3), (3, 2), (2, 1), (1, 0). Quan trọng vì chúng là đầu vào xấu nhất của Euclid.
- **Nhóm, nhóm Abel, nhóm hữu hạn (group, abelian group, finite group):** tập với một phép toán đóng, kết hợp, có đơn vị và nghịch đảo; giao hoán thì là nhóm Abel. Ví dụ (ℤ, +) là nhóm Abel vô hạn; (ℤ₆, +₆) là nhóm Abel 6 phần tử. Quan trọng vì định lý Lagrange về nhóm hữu hạn là công cụ đếm then chốt ở Mục 31.8.
- **Nhóm nhân modulo n, ℤₙ* (multiplicative group modulo n):** các lớp [a]ₙ với gcd(a, n) = 1, phép toán nhân modulo n. Ví dụ ℤ₁₅* = {1, 2, 4, 7, 8, 11, 13, 14}, 8 · 11 = 88 ≡ 13 (mod 15). Quan trọng vì đây là nơi có nghịch đảo, nơi định lý Euler đúng và nơi RSA hoạt động.
- **Hàm phi Euler (Euler's phi function):** φ(n) = |ℤₙ*| = n Π_{p | n} (1 − 1/p). Ví dụ φ(45) = 24, φ(p) = p − 1, φ(pq) = (p − 1)(q − 1). Quan trọng vì khóa bí mật RSA d là nghịch đảo của e modulo φ(n).
- **Nhóm con, nhóm con thực sự, định lý Lagrange (subgroup, proper subgroup, Lagrange's theorem):** nhóm con là tập con cũng là nhóm; thực sự nếu khác cả nhóm; Lagrange: cỡ nhóm con chia hết cỡ nhóm. Ví dụ {0, 2, 4, 6} là nhóm con của ℤ₈ (4 chia hết 8). Quan trọng vì "nhóm con thực sự có cỡ ≤ một nửa" chặn số cơ số đánh lừa Miller-Rabin.
- **Cấp của phần tử, nhóm con sinh bởi a (order, ⟨a⟩):** ⟨a⟩ là mọi "lũy thừa" của a; cấp là số t nhỏ nhất với a^(t) = e, và bằng |⟨a⟩|. Ví dụ trong ℤ₇*, ⟨2⟩ = {1, 2, 4} nên ord₇(2) = 3. Quan trọng vì dãy lũy thừa tuần hoàn theo cấp.
- **Nghịch đảo modulo (modular multiplicative inverse):** số x với ax ≡ 1 (mod n), tồn tại duy nhất khi gcd(a, n) = 1, ký hiệu a⁻¹ mod n. Ví dụ 5⁻¹ mod 11 = 9 (5 · 9 = 45 ≡ 1), 7⁻¹ mod 15 = 13. Quan trọng vì nó định nghĩa phép chia trong ℤₙ* và khóa bí mật RSA.
- **Định lý số dư Trung Hoa (Chinese remainder theorem, CRT):** với các modulus đôi một nguyên tố cùng nhau, biết số dư theo từng modulus thì xác định duy nhất số dư theo tích. Ví dụ a ≡ 2 (mod 5), a ≡ 3 (mod 13) cho a ≡ 42 (mod 65). Quan trọng vì nó dùng trong chứng minh RSA, Miller-Rabin và giải thích hình ρ của Pollard.
- **Định lý Euler và định lý Fermat (Euler's theorem, Fermat's theorem):** a^φ(n) ≡ 1 (mod n) với a ∈ ℤₙ*; p nguyên tố thì a^(p−1) ≡ 1 (mod p). Ví dụ 2⁶ = 64 ≡ 1 (mod 7); 2^φ(15) = 2⁸ = 256 ≡ 1 (mod 15). Quan trọng vì chúng chứng minh RSA đúng và là nền của phép thử giả nguyên tố.
- **Căn nguyên thủy, nhóm cyclic, logarit rời rạc (primitive root, cyclic group, discrete logarithm):** g là căn nguyên thủy modulo n nếu mọi phần tử của ℤₙ* là lũy thừa của g; số mũ z với gᶻ ≡ a là logarit rời rạc. Ví dụ 3 là căn nguyên thủy modulo 7 (3ⁱ chạy qua 1, 3, 2, 6, 4, 5), và ind₇,₃(6) = 3. Quan trọng vì logarit rời rạc là một bài toán "khó" khác dùng trong mật mã, và cấu trúc cyclic dùng trong chứng minh Định lý 31.38.
- **Căn bậc hai không tầm thường của 1 (nontrivial square root of 1, modulo n):** x với x² ≡ 1 (mod n) nhưng x ≢ ±1. Ví dụ 6² = 36 ≡ 1 (mod 35); 67² = 4489 ≡ 1 (mod 561). Có căn như vậy thì n là hợp số. Quan trọng vì đây là "bằng chứng" thứ hai mà Miller-Rabin tìm.
- **Lũy thừa modulo bằng bình phương lặp (modular exponentiation, repeated squaring):** tính aᵇ mod n bằng cách đọc bit của b từ trái sang phải, mỗi bit bình phương kết quả, bit 1 thì nhân thêm a. Ví dụ 7⁵⁶⁰ mod 561 qua 10 bước ra 1. Quan trọng vì RSA, PSEUDOPRIME và WITNESS đều là lũy thừa modulo.
- **Hệ mật mã khóa công khai, chữ ký số (public-key cryptosystem, digital signature):** mỗi người có khóa công khai (ai cũng biết) và khóa bí mật; người gửi mã hóa bằng khóa công khai của người nhận; người ký áp khóa bí mật của mình, ai cũng kiểm tra bằng khóa công khai. Quan trọng vì đây là ứng dụng thúc đẩy toàn chương.
- **RSA:** khóa công khai (e, n), khóa bí mật (d, n), n = pq, ed ≡ 1 (mod φ(n)); P(M) = Mᵉ mod n, S(C) = Cᵈ mod n. Ví dụ p = 11, q = 29, n = 319, φ = 280, e = 3, d = 187. Quan trọng vì nó ghép mọi công cụ của chương.
- **Hàm đếm số nguyên tố và định lý số nguyên tố (prime distribution function, prime number theorem):** π(n) là số số nguyên tố ≤ n, π(n) ~ n/ln n. Ví dụ π(10) = 4. Quan trọng vì nó bảo đảm tìm số nguyên tố lớn ngẫu nhiên chỉ cần khoảng ln n lần thử.
- **Giả nguyên tố cơ số a, số Carmichael (base-a pseudoprime, Carmichael number):** hợp số n với a^(n−1) ≡ 1 (mod n); số Carmichael thỏa điều đó với mọi a ∈ ℤₙ*. Ví dụ 341 = 11 · 31 là giả nguyên tố cơ số 2; 561 là số Carmichael nhỏ nhất. Quan trọng vì chúng là điểm yếu của phép thử Fermat.
- **Bằng chứng hợp số (witness to compositeness):** cơ số a làm WITNESS(a, n) trả về TRUE — tức a cho một chứng minh rằng n là hợp số. Ví dụ a = 7 là bằng chứng cho n = 561. Quan trọng vì có ít nhất (n − 1)/2 bằng chứng nên chọn ngẫu nhiên dễ trúng.
- **Phép thử Miller-Rabin (Miller-Rabin primality test):** thử s cơ số ngẫu nhiên bằng WITNESS; trả về COMPOSITE là chắc chắn đúng, trả về PRIME sai với xác suất ≤ 2⁻ˢ. Quan trọng vì đây là phép thử nguyên tố dùng thực tế để tạo khóa RSA.
- **Heuristic rho của Pollard (Pollard's rho heuristic):** lặp xᵢ = (xᵢ₋₁² − 1) mod n và tính gcd(y − xᵢ, n) để bắt va chạm modulo một thừa số p chưa biết. Ví dụ với 1387 tìm ra 19 ở bước thứ 7. Quan trọng vì nó cho thấy thừa số nhỏ tìm được nhanh (Θ(√p)), còn thừa số lớn thì không.
- **Nghịch lý ngày sinh (birthday paradox):** chọn ngẫu nhiên từ n giá trị, khoảng Θ(√n) lần là kỳ vọng có hai lần trùng (Mục 5.4.1). Ví dụ với 365 ngày, 23 người đã có xác suất > 1/2 trùng ngày sinh. Quan trọng vì nó cho thời gian Θ(√p) của rho Pollard.

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 926–927)

Chương mở đầu bằng một nhận xét lịch sử: lý thuyết số từng bị coi là một môn toán thuần túy đẹp nhưng phần lớn vô dụng. Ngày nay các thuật toán số học được dùng rộng rãi, phần lớn nhờ sự ra đời của các hệ mật mã dựa trên số nguyên tố lớn. Những hệ này **khả thi** vì ta tìm được số nguyên tố lớn một cách dễ dàng, và **an toàn** vì ta không biết cách phân tích hiệu quả tích của các số nguyên tố lớn (hay giải hiệu quả các bài toán liên quan, như tính logarit rời rạc). Chương trình bày phần lý thuyết số và các thuật toán nằm dưới những ứng dụng như vậy.

Trình tự chương được nêu trước: Mục 31.1 giới thiệu khái niệm cơ bản (chia hết, đồng dư, phân tích duy nhất); Mục 31.2 nghiên cứu một trong những thuật toán cổ nhất thế giới — thuật toán Euclid tính ước chung lớn nhất; Mục 31.3 ôn số học modulo; Mục 31.4 nghiên cứu tập bội của một số a modulo n và chỉ cách tìm mọi nghiệm của ax ≡ b (mod n) bằng thuật toán Euclid; Mục 31.5 trình bày định lý số dư Trung Hoa; Mục 31.6 xét lũy thừa của a modulo n và thuật toán bình phương lặp tính aᵇ mod n — phép toán nằm ở trung tâm của phép thử nguyên tố hiệu quả và của phần lớn mật mã hiện đại; Mục 31.7 mô tả hệ mật mã khóa công khai RSA; Mục 31.8 xét một phép thử nguyên tố ngẫu nhiên, dùng để tìm số nguyên tố lớn khi tạo khóa RSA; cuối cùng Mục 31.9 bàn một heuristic đơn giản mà hiệu quả để phân tích thừa số các số nhỏ. Tác giả ghi nhận một điều thú vị: phân tích thừa số là một bài toán mà người ta có thể **mong** nó khó, vì độ an toàn của RSA phụ thuộc vào việc phân tích số lớn là khó.

#### Kích thước đầu vào và chi phí các phép tính số học (Size of inputs and cost of arithmetic computations)

Vì làm việc với số nguyên lớn, cần điều chỉnh cách nghĩ về kích thước đầu vào và chi phí các phép toán sơ cấp. Trong chương này, "đầu vào lớn" thường nghĩa là đầu vào chứa **số nguyên lớn** chứ không phải chứa **nhiều số nguyên** (như với sắp xếp). Vì thế kích thước đầu vào được đo bằng **số bit** cần để biểu diễn nó, không chỉ bằng số lượng số. Một thuật toán với đầu vào nguyên a₁, a₂, …, aₖ là **thuật toán thời gian đa thức** (polynomial-time algorithm) nếu nó chạy trong thời gian đa thức theo lg a₁, lg a₂, …, lg aₖ, tức đa thức theo độ dài biểu diễn nhị phân của đầu vào.

Ở phần lớn cuốn sách, các phép toán số học sơ cấp (nhân, chia, lấy dư) được coi là phép toán nguyên thủy tốn một đơn vị thời gian; đếm số phép toán như vậy cho ước lượng hợp lý về thời gian chạy thật. Nhưng khi đầu vào lớn, các phép toán sơ cấp có thể tốn thời gian. Vì thế tiện hơn là đo số **phép toán bit** (bit operations) mà thuật toán số học cần. Trong mô hình này:

- Nhân hai số β-bit bằng phương pháp thông thường tốn Θ(β²) phép toán bit.
- Tương tự, chia một số β-bit cho một số ngắn hơn, hoặc lấy số dư của phép chia đó, tốn Θ(β²) bằng thuật toán đơn giản (Exercise 31.1-12).
- Có phương pháp nhanh hơn: một phương pháp chia để trị đơn giản nhân hai số β-bit trong Θ(β^lg 3) (lg 3 ≈ 1,585), và phương pháp nhanh nhất được biết (tại thời điểm sách viết) chạy Θ(β lg β lg lg β). Tuy vậy, trong thực hành thuật toán Θ(β²) thường là tốt nhất, và sách lấy cận này làm cơ sở phân tích.

Các thuật toán trong chương thường được phân tích theo **cả hai** thước đo: số phép toán số học và số phép toán bit.

Ví dụ minh họa của người tổng hợp: n = 2⁶⁴ − 1 có β = 64 bit. Một thuật toán chạy n bước "chỉ là tuyến tính theo giá trị" nhưng là 2⁶⁴ ≈ 1,8 · 10¹⁹ bước — không khả thi; một thuật toán chạy β³ bước chỉ tốn 262.144 bước.

### 2. Các khái niệm số học sơ cấp (31.1 Elementary number-theoretic notions, trang 927–933)

Mục này ôn ngắn các khái niệm của lý thuyết số sơ cấp về tập số nguyên ℤ = {…, −2, −1, 0, 1, 2, …} và tập số tự nhiên ℕ = {0, 1, 2, …}.

#### Chia hết và ước (Divisibility and divisors)

Khái niệm một số nguyên chia hết cho một số khác là then chốt của lý thuyết số. Ký hiệu **d | a** (đọc "d chia hết a") nghĩa là a = kd với một số nguyên k nào đó. Mọi số nguyên đều chia hết 0. Nếu a > 0 và d | a thì |d| ≤ |a|. Nếu d | a ta cũng nói a là **bội** (multiple) của d. Nếu d không chia hết a, viết d ∤ a.

Nếu d | a và d ≥ 0, ta nói d là **ước** (divisor) của a. Vì d | a khi và chỉ khi −d | a, không mất tổng quát khi định nghĩa ước là số không âm, với hiểu ngầm rằng số đối của một ước cũng chia hết a. Ước của một số nguyên a khác 0 ít nhất bằng 1 và không vượt |a|. Ví dụ, các ước của 24 là 1, 2, 3, 4, 6, 8, 12, 24.

Mọi số nguyên dương a đều chia hết cho hai **ước tầm thường** (trivial divisors) 1 và a. Các ước không tầm thường của a là các **thừa số** (factors) của a. Ví dụ thừa số của 20 là 2, 4, 5, 10.

#### Số nguyên tố và hợp số (Prime and composite numbers)

Số nguyên a > 1 chỉ có hai ước tầm thường 1 và a là **số nguyên tố** (prime number, hay gọn là prime). Số nguyên tố có nhiều tính chất đặc biệt và giữ vai trò then chốt trong lý thuyết số. 20 số nguyên tố đầu tiên theo thứ tự là

```text
2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71
```

Exercise 31.1-2 yêu cầu chứng minh có vô hạn số nguyên tố. Số nguyên a > 1 không phải số nguyên tố là **hợp số** (composite number, hay composite). Ví dụ 39 là hợp số vì 3 | 39. Số 1 được gọi là **đơn vị** (unit) và không phải số nguyên tố cũng không phải hợp số. Tương tự, số 0 và mọi số âm không phải số nguyên tố cũng không phải hợp số.

#### Định lý phép chia, số dư và đồng dư (The division theorem, remainders, and modular equivalence)

Cho số nguyên n, ta chia các số nguyên thành hai loại: bội của n và không phải bội của n. Phần lớn lý thuyết số dựa trên việc làm mịn phép chia này: phân loại các số không phải bội của n theo số dư khi chia cho n. Định lý sau là cơ sở cho việc làm mịn đó (sách bỏ qua chứng minh, dẫn Niven và Zuckerman).

**Định lý 31.1 (Định lý phép chia — Division theorem).** Với mọi số nguyên a và mọi số nguyên dương n, tồn tại duy nhất các số nguyên q và r sao cho 0 ≤ r < n và a = qn + r.

Giá trị q = ⌊a/n⌋ là **thương** (quotient) của phép chia. Giá trị r = a mod n là **số dư** (remainder, hay residue). Ta có n | a khi và chỉ khi a mod n = 0.

Ta có thể chia các số nguyên thành n lớp tương đương theo số dư modulo n. **Lớp đồng dư modulo n** (equivalence class modulo n) chứa số nguyên a là

```text
[a]ₙ = { a + kn : k ∈ ℤ }
```

Ví dụ [3]₇ = {…, −11, −4, 3, 10, 17, …}; tập này cũng có thể ký hiệu [−4]₇ hay [10]₇. Viết a ∈ [b]ₙ cũng có nghĩa như viết a ≡ b (mod n) (ký hiệu đồng dư định nghĩa ở Chương 3). Tập mọi lớp đồng dư như vậy là

```text
ℤₙ = { [a]ₙ : 0 ≤ a ≤ n − 1 }                                        (31.1)
```

Khi gặp định nghĩa

```text
ℤₙ = { 0, 1, …, n − 1 }                                              (31.2)
```

hãy đọc nó như tương đương với (31.1), với hiểu ngầm rằng 0 đại diện cho [0]ₙ, 1 đại diện cho [1]ₙ, v.v.; mỗi lớp được đại diện bởi phần tử không âm nhỏ nhất của nó. Tuy nhiên cần luôn nhớ tới các lớp đồng dư bên dưới. Ví dụ, nói −1 là một phần tử của ℤₙ thực ra là nói tới [n − 1]ₙ, vì −1 ≡ n − 1 (mod n).

#### Ước chung và ước chung lớn nhất (Common divisors and greatest common divisors)

Nếu d là ước của a và cũng là ước của b thì d là **ước chung** (common divisor) của a và b. Ví dụ, ước của 30 là 1, 2, 3, 5, 6, 10, 15, 30, nên ước chung của 24 và 30 là 1, 2, 3, 6. Lưu ý 1 là ước chung của mọi cặp số nguyên.

Một tính chất quan trọng của ước chung:

```text
d | a và d | b  ⇒  d | (a + b) và d | (a − b)                         (31.3)
```

Tổng quát hơn, với mọi số nguyên x, y:

```text
d | a và d | b  ⇒  d | (ax + by)                                      (31.4)
```

Ngoài ra, nếu a | b thì hoặc |a| ≤ |b| hoặc b = 0, suy ra

```text
a | b và b | a  ⇒  a = ±b                                              (31.5)
```

**Ước chung lớn nhất** (greatest common divisor) của hai số nguyên a, b không cùng bằng 0 là ước chung lớn nhất của chúng, ký hiệu gcd(a, b). Ví dụ gcd(24, 30) = 6, gcd(5, 7) = 1, gcd(0, 9) = 9. Nếu a và b đều khác 0 thì gcd(a, b) là một số nguyên trong khoảng 1 tới min(|a|, |b|). Sách định nghĩa gcd(0, 0) = 0; định nghĩa này cần để các tính chất chuẩn của gcd (như (31.9) dưới đây) đúng trong mọi trường hợp.

Các tính chất sơ cấp của hàm gcd:

```text
gcd(a, b)  = gcd(b, a)                                               (31.6)
gcd(a, b)  = gcd(−a, b)                                              (31.7)
gcd(a, b)  = gcd(|a|, |b|)                                           (31.8)
gcd(a, 0)  = |a|                                                     (31.9)
gcd(a, ka) = |a|      với mọi k ∈ ℤ                                  (31.10)
```

Định lý sau cho một đặc trưng khác, rất hữu ích, của gcd(a, b).

**Định lý 31.2.** Nếu a và b là các số nguyên bất kỳ không cùng bằng 0, thì gcd(a, b) là phần tử dương nhỏ nhất của tập {ax + by : x, y ∈ ℤ} các tổ hợp tuyến tính của a và b.

*Chứng minh.* Gọi s là tổ hợp tuyến tính dương nhỏ nhất như vậy, s = ax + by với x, y ∈ ℤ nào đó. Đặt q = ⌊a/s⌋. Theo định nghĩa a mod s (công thức (3.8): a mod n = a − n⌊a/n⌋):

```text
a mod s = a − qs
        = a − q(ax + by)
        = a(1 − qx) + b(−qy)
```

nên a mod s cũng là một tổ hợp tuyến tính của a và b. Nhưng vì 0 ≤ a mod s < s, mà s là tổ hợp dương nhỏ nhất, nên a mod s = 0. Vậy s | a, và lập luận tương tự cho s | b. Như thế s là ước chung của a và b, nên gcd(a, b) ≥ s. Mặt khác, theo (31.4), gcd(a, b) | s, vì gcd(a, b) chia hết cả a lẫn b còn s là tổ hợp tuyến tính của a và b. Mà gcd(a, b) | s và s > 0 suy ra gcd(a, b) ≤ s. Kết hợp gcd(a, b) ≥ s và gcd(a, b) ≤ s được gcd(a, b) = s. ∎

Kiểm tra số (người tổng hợp): với a = 24, b = 30: 24 · (−1) + 30 · 1 = 6, và không tổ hợp nào cho 1, …, 5 vì mọi tổ hợp đều chia hết cho 6. Đúng là gcd = 6.

**Hệ quả 31.3.** Với mọi số nguyên a, b, nếu d | a và d | b thì d | gcd(a, b).

*Chứng minh.* Suy từ (31.4), vì theo Định lý 31.2, gcd(a, b) là một tổ hợp tuyến tính của a và b. ∎

**Hệ quả 31.4.** Với mọi số nguyên a, b và mọi số nguyên không âm n: gcd(an, bn) = n · gcd(a, b).

*Chứng minh.* Nếu n = 0 thì hiển nhiên. Nếu n > 0, gcd(an, bn) là phần tử dương nhỏ nhất của tập {anx + bny : x, y ∈ ℤ}, bằng n lần phần tử dương nhỏ nhất của tập {ax + by : x, y ∈ ℤ}. ∎

**Hệ quả 31.5.** Với mọi số nguyên dương n, a, b: nếu n | ab và gcd(a, n) = 1 thì n | b. (Chứng minh để cho Exercise 31.1-5.)

#### Các số nguyên tố cùng nhau (Relatively prime integers)

Hai số nguyên a, b là **nguyên tố cùng nhau** (relatively prime) nếu ước chung duy nhất của chúng là 1, tức gcd(a, b) = 1. Ví dụ 8 và 15 nguyên tố cùng nhau, vì ước của 8 là 1, 2, 4, 8 còn ước của 15 là 1, 3, 5, 15. Định lý sau nói: nếu hai số đều nguyên tố cùng nhau với p thì tích của chúng cũng nguyên tố cùng nhau với p.

**Định lý 31.6.** Với mọi số nguyên a, b, p: nếu gcd(a, p) = 1 và gcd(b, p) = 1 thì gcd(ab, p) = 1.

*Chứng minh.* Theo Định lý 31.2, tồn tại các số nguyên x, y, x′, y′ sao cho

```text
ax  + py  = 1
bx′ + py′ = 1
```

Nhân hai đẳng thức và sắp xếp lại:

```text
ab(xx′) + p(ybx′ + y′ax + pyy′) = 1
```

Vì 1 là một tổ hợp tuyến tính dương của ab và p, áp dụng Định lý 31.2 ta có gcd(ab, p) = 1. ∎

Các số nguyên n₁, n₂, …, nₖ là **đôi một nguyên tố cùng nhau** (pairwise relatively prime) nếu gcd(nᵢ, nⱼ) = 1 với mọi i ≠ j.

#### Phân tích duy nhất (Unique factorization)

Một sự kiện sơ cấp nhưng quan trọng về tính chia hết cho số nguyên tố:

**Định lý 31.7.** Với mọi số nguyên tố p và mọi số nguyên a, b: nếu p | ab thì p | a hoặc p | b (hoặc cả hai).

*Chứng minh.* Giả sử phản chứng p | ab nhưng p ∤ a và p ∤ b. Khi đó gcd(a, p) = 1 và gcd(b, p) = 1, vì ước duy nhất của p là 1 và p, mà p không chia hết a lẫn b. Định lý 31.6 khi đó cho gcd(ab, p) = 1, mâu thuẫn với p | ab (vì p | ab kéo theo gcd(ab, p) = p). ∎

Hệ quả của Định lý 31.7 là có thể phân tích duy nhất mọi hợp số thành tích các số nguyên tố.

**Định lý 31.8 (Phân tích duy nhất — Unique factorization).** Có đúng một cách viết mọi hợp số a dưới dạng tích

```text
a = p₁^e₁ · p₂^e₂ ⋯ pᵣ^eᵣ
```

trong đó các pᵢ là số nguyên tố, p₁ < p₂ < ⋯ < pᵣ, và các eᵢ là số nguyên dương. (Chứng minh để cho Exercise 31.1-11.)

Ví dụ, số 6000 được phân tích duy nhất thành 2⁴ · 3 · 5³ (16 · 3 · 125 = 6000).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: các thư viện số nguyên lớn (GMP trong C, `BigInteger` của Java, kiểu `int` không giới hạn của Python) đều tách bạch hai thước đo chi phí mà sách nêu — số "phép toán trên số" và số phép toán trên từ máy (word) — và chọn thuật toán nhân theo độ dài: cách viết tay cho số ngắn, Karatsuba (chính là phương pháp chia để trị Θ(β^lg 3) sách nhắc tới) cho số trung bình, nhân dựa trên FFT cho số rất dài.

### 3. Ước chung lớn nhất (31.2 Greatest common divisor, trang 933–939)

Mục này mô tả thuật toán Euclid tính hiệu quả ước chung lớn nhất của hai số nguyên. Khi phân tích thời gian chạy, ta sẽ thấy một mối liên hệ bất ngờ với các số Fibonacci — chúng cho đầu vào xấu nhất của thuật toán Euclid. Mục này chỉ xét số nguyên không âm; hạn chế này hợp lý nhờ (31.8): gcd(a, b) = gcd(|a|, |b|).

Về nguyên tắc, có thể tính gcd(a, b) với a, b dương từ phân tích thừa số nguyên tố của chúng. Thật vậy, nếu

```text
a = p₁^e₁ p₂^e₂ ⋯ pᵣ^eᵣ                                              (31.11)
b = p₁^f₁ p₂^f₂ ⋯ pᵣ^fᵣ                                              (31.12)
```

(dùng số mũ 0 để tập số nguyên tố p₁, …, pᵣ giống nhau cho a và b) thì, như Exercise 31.2-1 yêu cầu chứng minh,

```text
gcd(a, b) = p₁^min(e₁,f₁) · p₂^min(e₂,f₂) ⋯ pᵣ^min(eᵣ,fᵣ)               (31.13)
```

Ví dụ (người tổng hợp): 24 = 2³ · 3¹ · 5⁰, 30 = 2¹ · 3¹ · 5¹ nên gcd = 2¹ · 3¹ · 5⁰ = 6. Nhưng như Mục 31.9 sẽ cho thấy, các thuật toán phân tích thừa số tốt nhất hiện nay không chạy trong thời gian đa thức. Do đó cách tính gcd này khó dẫn tới thuật toán hiệu quả.

Thuật toán Euclid dựa trên định lý sau.

**Định lý 31.9 (Định lý đệ quy gcd — GCD recursion theorem).** Với mọi số nguyên không âm a và mọi số nguyên dương b:

```text
gcd(a, b) = gcd(b, a mod b)
```

*Chứng minh.* Ta chứng minh gcd(a, b) và gcd(b, a mod b) chia hết lẫn nhau, nên theo (31.5) chúng bằng nhau (vì đều không âm).

Trước hết, gcd(a, b) | gcd(b, a mod b). Đặt d = gcd(a, b), thì d | a và d | b. Theo (3.8), a mod b = a − qb với q = ⌊a/b⌋. Vì a mod b là tổ hợp tuyến tính của a và b, (31.4) cho d | (a mod b). Vậy d | b và d | (a mod b), nên theo Hệ quả 31.3, d | gcd(b, a mod b), tức

```text
gcd(a, b) | gcd(b, a mod b)                                         (31.14)
```

Chiều ngược lại gần như y hệt. Đặt d = gcd(b, a mod b), thì d | b và d | (a mod b). Vì a = qb + (a mod b) với q = ⌊a/b⌋, a là tổ hợp tuyến tính của b và (a mod b). Theo (31.4), d | a. Vì d | b và d | a, theo Hệ quả 31.3, d | gcd(a, b), tức

```text
gcd(b, a mod b) | gcd(a, b)                                         (31.15)
```

Dùng (31.5) kết hợp (31.14) và (31.15) là xong. ∎

#### Thuật toán Euclid (Euclid's algorithm)

Bộ *Cơ sở* (Elements) của Euclid (khoảng 300 TCN) mô tả thuật toán gcd sau, dù nó có thể có nguồn gốc sớm hơn. Sách viết thuật toán Euclid thành chương trình đệ quy dựa trực tiếp trên Định lý 31.9. Đầu vào a, b là các số nguyên không âm bất kỳ.

```text
EUCLID(a, b)
1  if b == 0
2      return a
3  else return EUCLID(b, a mod b)
```

Ví dụ tính gcd(30, 21):

```text
EUCLID(30, 21) = EUCLID(21, 9)       (30 mod 21 = 9)
               = EUCLID(9, 3)        (21 mod 9 = 3)
               = EUCLID(3, 0)        (9 mod 3 = 0)
               = 3
```

Phép tính này gọi EUCLID đệ quy ba lần.

Tính đúng của EUCLID suy từ Định lý 31.9 và tính chất: nếu thuật toán trả về a ở dòng 2 thì b = 0, nên theo (31.9), gcd(a, b) = gcd(a, 0) = a. Thuật toán không thể đệ quy vô hạn, vì đối số thứ hai giảm hẳn ở mỗi lần gọi đệ quy (a mod b < b) và luôn không âm. Do đó EUCLID luôn dừng với đáp án đúng.

#### Thời gian chạy của thuật toán Euclid (The running time of Euclid's algorithm)

Phân tích thời gian xấu nhất của EUCLID theo kích thước của a và b. Không mất tổng quát giả sử a > b ≥ 0. Lý do: nếu b > a ≥ 0 thì EUCLID(a, b) gọi ngay EUCLID(b, a) (vì a mod b = a) — tức nếu đối số thứ nhất nhỏ hơn đối số thứ hai, EUCLID dùng một lần gọi đệ quy để đổi chỗ hai đối số rồi tiếp tục. Tương tự, nếu b = a > 0, thủ tục dừng sau một lần gọi đệ quy vì a mod b = 0.

Tổng thời gian chạy của EUCLID tỉ lệ với số lần gọi đệ quy. Phân tích dùng các số Fibonacci Fₖ định nghĩa bởi truy hồi (3.22): F₀ = 0, F₁ = 1, Fᵢ = Fᵢ₋₁ + Fᵢ₋₂ với i ≥ 2. Dãy bắt đầu 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, …

**Bổ đề 31.10.** Nếu a > b ≥ 1 và lời gọi EUCLID(a, b) thực hiện k ≥ 1 lần gọi đệ quy, thì a ≥ F_{k+2} và b ≥ F_{k+1}.

*Chứng minh.* Quy nạp theo k. Cơ sở: k = 1. Khi đó b ≥ 1 = F₂, và vì a > b nên a ≥ 2 = F₃. Vì b > (a mod b), ở mỗi lần gọi đệ quy đối số thứ nhất lớn hẳn đối số thứ hai; do đó giả thiết a > b đúng ở mọi lần gọi đệ quy.

Giả sử quy nạp bổ đề đúng khi có k − 1 lần gọi đệ quy; ta chứng minh cho k lần. Vì k > 0, ta có b > 0, và EUCLID(a, b) gọi đệ quy EUCLID(b, a mod b), lời gọi này lại thực hiện k − 1 lần gọi đệ quy. Giả thiết quy nạp cho b ≥ F_{k+1} (chứng minh được một nửa bổ đề) và a mod b ≥ F_k. Ta có

```text
b + (a mod b) = b + (a − b⌊a/b⌋)
              ≤ a
```

vì a > b > 0 kéo theo ⌊a/b⌋ ≥ 1. Do đó

```text
a ≥ b + (a mod b)
  ≥ F_{k+1} + F_k
  = F_{k+2}                                                          ∎
```

(Lưu ý: ở bước quy nạp, lời gọi con EUCLID(b, a mod b) có thể có a mod b = 0 khi k − 1 = 0; trường hợp k = 1 đã được xử lý riêng ở cơ sở, nên bước quy nạp chỉ dùng cho k ≥ 2, khi đó a mod b ≥ 1 và giả thiết quy nạp áp dụng được — nhận xét của người tổng hợp.)

Định lý sau là hệ quả trực tiếp của bổ đề.

**Định lý 31.11 (Định lý Lamé — Lamé's theorem).** Với mọi số nguyên k ≥ 1, nếu a > b ≥ 1 và b < F_{k+1}, thì lời gọi EUCLID(a, b) thực hiện ít hơn k lần gọi đệ quy.

Cận trên của Định lý 31.11 là tốt nhất có thể: lời gọi EUCLID(F_{k+1}, F_k) thực hiện đúng k − 1 lần gọi đệ quy khi k ≥ 2. Chứng minh quy nạp theo k. Cơ sở k = 2: lời gọi EUCLID(F₃, F₂) = EUCLID(2, 1) gọi đệ quy đúng một lần, tới EUCLID(1, 0). (Phải bắt đầu từ k = 2 vì với k = 1 ta không có F₂ > F₁.) Bước quy nạp: giả sử EUCLID(F_k, F_{k−1}) gọi đệ quy đúng k − 2 lần. Với k > 2, ta có F_k > F_{k−1} > 0 và F_{k+1} = F_k + F_{k−1}, nên theo Exercise 31.1-1, F_{k+1} mod F_k = F_{k−1}. Do đó

```text
gcd(F_{k+1}, F_k) = gcd(F_k, F_{k+1} mod F_k)
                  = gcd(F_k, F_{k−1})
```

Vậy lời gọi EUCLID(F_{k+1}, F_k) đệ quy nhiều hơn EUCLID(F_k, F_{k−1}) đúng một lần, tức đúng k − 1 lần, đạt cận trên của Định lý 31.11.

Chạy tay (người tổng hợp) với k = 7: EUCLID(F₈, F₇) = EUCLID(21, 13) → (13, 8) → (8, 5) → (5, 3) → (3, 2) → (2, 1) → (1, 0): đúng 6 = k − 1 lần gọi đệ quy, mọi thương ⌊a/b⌋ đều bằng 1 (trừ bước cuối) — đó là lý do Fibonacci là đầu vào xấu nhất: mỗi bước chỉ "bớt" được ít nhất có thể.

Vì F_k xấp xỉ φᵏ/√5, với φ = (1 + √5)/2 ≈ 1,618 là tỉ số vàng (công thức (3.24)), số lần gọi đệ quy của EUCLID là O(lg b). (Exercise 31.2-5 cho cận chặt hơn.) Do đó nếu gọi EUCLID trên hai số β-bit thì nó thực hiện O(β) phép toán số học và O(β³) phép toán bit (giả sử nhân và chia số β-bit tốn O(β²) phép toán bit). Problem 31-2 yêu cầu chứng minh cận O(β²) cho số phép toán bit.

Kiểm tra số (người tổng hợp): với b < 10⁶, vì F₃₁ = 1.346.269 > 10⁶, Định lý Lamé cho EUCLID(a, b) gọi đệ quy ít hơn 30 lần, bất kể a lớn tới đâu (miễn a > b).

#### Dạng mở rộng của thuật toán Euclid (The extended form of Euclid's algorithm)

Viết lại thuật toán Euclid để tính thêm thông tin hữu ích: các hệ số nguyên x, y sao cho

```text
d = gcd(a, b) = ax + by                                              (31.16)
```

Lưu ý x và y có thể bằng 0 hoặc âm. Các hệ số này về sau dùng để tính nghịch đảo nhân modulo. Thủ tục EXTENDED-EUCLID nhận vào một cặp số nguyên không âm và trả về bộ ba (d, x, y) thỏa (31.16).

```text
EXTENDED-EUCLID(a, b)
1  if b == 0
2      return (a, 1, 0)
3  else (d′, x′, y′) = EXTENDED-EUCLID(b, a mod b)
4      (d, x, y) = (d′, y′, x′ − ⌊a/b⌋ y′)
5      return (d, x, y)
```

Hình 31.1 của sách minh họa EXTENDED-EUCLID tính gcd(99, 78). Mỗi dòng là một tầng đệ quy: giá trị đầu vào a, b, giá trị ⌊a/b⌋ tính được, và các giá trị d, x, y trả về. Bộ ba (d, x, y) trả về ở một tầng trở thành bộ ba (d′, x′, y′) dùng ở tầng cao hơn. Chép lại bảng (tầng ngoài cùng ở trên):

| a | b | ⌊a/b⌋ | d | x | y |
|---|---|---|---|---|---|
| 99 | 78 | 1 | 3 | −11 | 14 |
| 78 | 21 | 3 | 3 | 3 | −11 |
| 21 | 15 | 1 | 3 | −2 | 3 |
| 15 | 6 | 2 | 3 | 1 | −2 |
| 6 | 3 | 2 | 3 | 0 | 1 |
| 3 | 0 | — | 3 | 1 | 0 |

Đọc từ dưới lên: tầng đáy (3, 0) trả về (3, 1, 0). Tầng (6, 3): x = y′ = 0, y = x′ − 2y′ = 1 − 0 = 1. Tầng (15, 6): x = 1, y = 0 − 2 · 1 = −2. Tầng (21, 15): x = −2, y = 1 − 1 · (−2) = 3. Tầng (78, 21): x = 3, y = −2 − 3 · 3 = −11. Tầng (99, 78): x = −11, y = 3 − 1 · (−11) = 14. Lời gọi EXTENDED-EUCLID(99, 78) trả về (3, −11, 14), nên gcd(99, 78) = 3 = 99 · (−11) + 78 · 14 (kiểm tra: −1089 + 1092 = 3).

Thủ tục EXTENDED-EUCLID là một biến thể của EUCLID. Dòng 1 tương đương phép thử "b == 0" ở dòng 1 của EUCLID. Nếu b = 0, EXTENDED-EUCLID trả về không chỉ d = a ở dòng 2, mà cả các hệ số x = 1 và y = 0, để a = ax + by. Nếu b ≠ 0, EXTENDED-EUCLID trước hết tính (d′, x′, y′) sao cho d′ = gcd(b, a mod b) và

```text
d′ = bx′ + (a mod b)y′                                               (31.17)
```

Như với EUCLID, trong trường hợp này d = gcd(a, b) = d′ = gcd(b, a mod b). Để có x, y với d = ax + by, viết lại (31.17) dùng d = d′ và (3.8):

```text
d = bx′ + (a − b⌊a/b⌋)y′
  = ay′ + b(x′ − ⌊a/b⌋y′)
```

Vậy chọn x = y′ và y = x′ − ⌊a/b⌋y′ thỏa d = ax + by, chứng minh EXTENDED-EUCLID đúng.

Vì số lần gọi đệ quy của EUCLID bằng số lần gọi đệ quy của EXTENDED-EUCLID, thời gian chạy của hai thủ tục như nhau tới một hằng số: với a > b > 0, số lần gọi đệ quy là O(lg b).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hàm `math.gcd` của Python, `std::gcd` của C++17 và phép rút gọn phân số trong mọi thư viện số hữu tỉ đều là thuật toán Euclid (hoặc biến thể gcd nhị phân của Problem 31-1). Euclid mở rộng là cách chuẩn để tính nghịch đảo modulo trong thư viện mật mã (từ Python 3.8, `pow(a, -1, n)` trả về a⁻¹ mod n).

### 4. Số học modulo (31.3 Modular arithmetic, trang 939–946)

Một cách không hình thức, có thể nghĩ số học modulo như số học thông thường trên số nguyên, chỉ khác là nếu làm việc modulo n thì mọi kết quả x được thay bằng phần tử của {0, 1, …, n − 1} đồng dư với x modulo n (tức x được thay bằng x mod n). Mô hình không hình thức này đủ nếu chỉ dùng cộng, trừ và nhân. Mô hình hình thức hơn, mà sách trình bày ngay sau đây, được mô tả tốt nhất trong khuôn khổ lý thuyết nhóm.

#### Nhóm hữu hạn (Finite groups)

Một **nhóm** (group) (S, ⊕) là một tập S cùng một phép toán hai ngôi ⊕ định nghĩa trên S thỏa các tính chất:

1. **Đóng (Closure):** với mọi a, b ∈ S, a ⊕ b ∈ S.
2. **Đơn vị (Identity):** tồn tại phần tử e ∈ S, gọi là **phần tử đơn vị** của nhóm, sao cho e ⊕ a = a ⊕ e = a với mọi a ∈ S.
3. **Kết hợp (Associativity):** với mọi a, b, c ∈ S, (a ⊕ b) ⊕ c = a ⊕ (b ⊕ c).
4. **Nghịch đảo (Inverses):** với mỗi a ∈ S tồn tại duy nhất b ∈ S, gọi là **nghịch đảo** của a, sao cho a ⊕ b = b ⊕ a = e.

Ví dụ, nhóm quen thuộc (ℤ, +) gồm các số nguyên với phép cộng: 0 là đơn vị, nghịch đảo của a là −a. Nếu nhóm (S, ⊕) thỏa **luật giao hoán** a ⊕ b = b ⊕ a với mọi a, b ∈ S thì nó là **nhóm Abel** (abelian group). Nếu |S| < ∞ thì nó là **nhóm hữu hạn** (finite group).

#### Các nhóm định nghĩa bởi phép cộng và phép nhân modulo (The groups defined by modular addition and multiplication)

Có thể dựng hai nhóm Abel hữu hạn từ phép cộng và phép nhân modulo n (n nguyên dương). Các nhóm này dựa trên các lớp đồng dư modulo n của Mục 31.1.

Để định nghĩa nhóm trên ℤₙ, cần phép toán hai ngôi phù hợp, có được bằng cách định nghĩa lại phép cộng và phép nhân thông thường. Việc này dễ vì lớp đồng dư của hai số nguyên xác định duy nhất lớp đồng dư của tổng và tích. Tức là, nếu a ≡ a′ (mod n) và b ≡ b′ (mod n) thì

```text
a + b ≡ a′ + b′ (mod n)
ab    ≡ a′b′    (mod n)
```

Vì vậy định nghĩa phép cộng và nhân modulo n, ký hiệu +ₙ và ·ₙ, bởi

```text
[a]ₙ +ₙ [b]ₙ = [a + b]ₙ                                              (31.18)
[a]ₙ ·ₙ [b]ₙ = [ab]ₙ
```

(Có thể định nghĩa phép trừ tương tự, [a]ₙ −ₙ [b]ₙ = [a − b]ₙ, nhưng phép chia phức tạp hơn, như sẽ thấy.) Những sự kiện này biện minh cho thói quen tiện lợi: dùng phần tử không âm nhỏ nhất của mỗi lớp làm đại diện khi tính trong ℤₙ — cộng, trừ, nhân như thường trên các đại diện, rồi thay mỗi kết quả x bằng đại diện của lớp nó, tức x mod n.

Dùng phép cộng modulo n, định nghĩa **nhóm cộng modulo n** (additive group modulo n) là (ℤₙ, +ₙ), có cỡ |ℤₙ| = n. Bảng phép toán của nhóm (ℤ₆, +₆) (Hình 31.2(a) của sách), ô ở hàng a cột b là a +₆ b:

| +₆ | 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|---|
| **0** | 0 | 1 | 2 | 3 | 4 | 5 |
| **1** | 1 | 2 | 3 | 4 | 5 | 0 |
| **2** | 2 | 3 | 4 | 5 | 0 | 1 |
| **3** | 3 | 4 | 5 | 0 | 1 | 2 |
| **4** | 4 | 5 | 0 | 1 | 2 | 3 |
| **5** | 5 | 0 | 1 | 2 | 3 | 4 |

**Định lý 31.12.** Hệ (ℤₙ, +ₙ) là một nhóm Abel hữu hạn.

*Chứng minh.* (31.18) cho thấy (ℤₙ, +ₙ) đóng. Tính kết hợp và giao hoán của +ₙ suy từ tính kết hợp và giao hoán của +:

```text
([a]ₙ +ₙ [b]ₙ) +ₙ [c]ₙ = [a + b]ₙ +ₙ [c]ₙ
                        = [(a + b) + c]ₙ
                        = [a + (b + c)]ₙ
                        = [a]ₙ +ₙ [b + c]ₙ
                        = [a]ₙ +ₙ ([b]ₙ +ₙ [c]ₙ)

[a]ₙ +ₙ [b]ₙ = [a + b]ₙ = [b + a]ₙ = [b]ₙ +ₙ [a]ₙ
```

Phần tử đơn vị của (ℤₙ, +ₙ) là 0 (tức [0]ₙ). Nghịch đảo (theo phép cộng) của phần tử a (tức [a]ₙ) là −a (tức [−a]ₙ hay [n − a]ₙ), vì [a]ₙ +ₙ [−a]ₙ = [a − a]ₙ = [0]ₙ. ∎

Dùng phép nhân modulo n, định nghĩa **nhóm nhân modulo n** (multiplicative group modulo n) là (ℤₙ*, ·ₙ). Phần tử của nhóm là tập ℤₙ* các phần tử của ℤₙ nguyên tố cùng nhau với n, để mỗi phần tử có nghịch đảo duy nhất modulo n:

```text
ℤₙ* = { [a]ₙ ∈ ℤₙ : gcd(a, n) = 1 }
```

Để thấy ℤₙ* được định nghĩa đúng (không phụ thuộc đại diện), lưu ý với 0 ≤ a < n ta có a ≡ (a + kn) (mod n) với mọi số nguyên k. Theo Exercise 31.2-3, gcd(a, n) = 1 kéo theo gcd(a + kn, n) = 1 với mọi k. Vì [a]ₙ = {a + kn : k ∈ ℤ}, tập ℤₙ* được định nghĩa đúng. Ví dụ:

```text
ℤ₁₅* = {1, 2, 4, 7, 8, 11, 13, 14}
```

với phép toán là nhân modulo 15. (Ở đây ký hiệu phần tử [a]₁₅ là a; ví dụ [7]₁₅ viết là 7.) Bảng nhân của nhóm (ℤ₁₅*, ·₁₅) (Hình 31.2(b) của sách), ô hàng a cột b là a · b mod 15:

| ·₁₅ | 1 | 2 | 4 | 7 | 8 | 11 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|
| **1** | 1 | 2 | 4 | 7 | 8 | 11 | 13 | 14 |
| **2** | 2 | 4 | 8 | 14 | 1 | 7 | 11 | 13 |
| **4** | 4 | 8 | 1 | 13 | 2 | 14 | 7 | 11 |
| **7** | 7 | 14 | 13 | 4 | 11 | 2 | 1 | 8 |
| **8** | 8 | 1 | 2 | 11 | 4 | 13 | 14 | 7 |
| **11** | 11 | 7 | 14 | 2 | 13 | 1 | 8 | 4 |
| **13** | 13 | 11 | 7 | 1 | 14 | 8 | 4 | 2 |
| **14** | 14 | 13 | 11 | 8 | 7 | 4 | 2 | 1 |

Ví dụ 8 · 11 ≡ 13 (mod 15) trong ℤ₁₅* (88 = 5 · 15 + 13). Phần tử đơn vị của nhóm này là 1. Nhận xét của người tổng hợp: mỗi hàng và mỗi cột của bảng là một hoán vị của tám phần tử (đúng như Exercise 31.3-5 yêu cầu chứng minh), và số 1 xuất hiện đúng một lần ở mỗi hàng — vị trí đó cho nghịch đảo: 2⁻¹ = 8, 4⁻¹ = 4, 7⁻¹ = 13, 11⁻¹ = 11, 14⁻¹ = 14.

**Định lý 31.13.** Hệ (ℤₙ*, ·ₙ) là một nhóm Abel hữu hạn.

*Chứng minh.* Định lý 31.6 cho thấy (ℤₙ*, ·ₙ) đóng. Tính kết hợp và giao hoán chứng minh cho ·ₙ như đã làm cho +ₙ trong Định lý 31.12. Phần tử đơn vị là [1]ₙ. Để chứng minh tồn tại nghịch đảo, cho a ∈ ℤₙ* và để (d, x, y) là bộ ba EXTENDED-EUCLID(a, n) trả về. Khi đó d = 1 vì a ∈ ℤₙ*, và

```text
ax + ny = 1                                                          (31.19)
```

hay tương đương ax ≡ 1 (mod n). Vậy [x]ₙ là nghịch đảo nhân của [a]ₙ modulo n. Hơn nữa [x]ₙ ∈ ℤₙ*: (31.19) cho thấy tổ hợp tuyến tính dương nhỏ nhất của x và n phải là 1, nên theo Định lý 31.2, gcd(x, n) = 1. Chứng minh rằng nghịch đảo là duy nhất được để tới Hệ quả 31.26. ∎

Ví dụ tính nghịch đảo nhân: a = 5, n = 11. EXTENDED-EUCLID(5, 11) trả về (d, x, y) = (1, −2, 1), nên 1 = 5 · (−2) + 11 · 1. Vậy [−2]₁₁ (tức [9]₁₁) là nghịch đảo nhân của [5]₁₁ (kiểm tra: 5 · 9 = 45 = 4 · 11 + 1).

Khi làm việc với các nhóm (ℤₙ, +ₙ) và (ℤₙ*, ·ₙ) trong phần còn lại của chương, sách theo thói quen: ký hiệu lớp đồng dư bằng phần tử đại diện, và ký hiệu +ₙ, ·ₙ bằng + và · (hoặc viết liền, ab = a · b). Phép đồng dư modulo n cũng có thể hiểu như phương trình trong ℤₙ; ví dụ hai mệnh đề sau tương đương:

```text
ax ≡ b (mod n)
[a]ₙ ·ₙ [x]ₙ = [b]ₙ
```

Để tiện hơn nữa, đôi khi gọi nhóm (S, ⊕) chỉ là S khi phép toán ⊕ đã rõ; như vậy các nhóm (ℤₙ, +ₙ) và (ℤₙ*, ·ₙ) được gọi là ℤₙ và ℤₙ*.

Nghịch đảo (nhân) của phần tử a được ký hiệu (a⁻¹ mod n). Phép chia trong ℤₙ* định nghĩa bởi a/b ≡ ab⁻¹ (mod n). Ví dụ trong ℤ₁₅*, 7⁻¹ ≡ 13 (mod 15) vì 7 · 13 = 91 ≡ 1 (mod 15), nên 4/7 ≡ 4 · 13 = 52 ≡ 7 (mod 15). (Kiểm tra: 7 · 7 = 49 ≡ 4.)

#### Hàm phi Euler

Cỡ của ℤₙ* được ký hiệu φ(n). Hàm này, gọi là **hàm phi Euler** (Euler's phi function), thỏa

```text
φ(n) = n · Π_{p : p nguyên tố và p | n} (1 − 1/p)                      (31.20)
```

trong đó p chạy qua mọi số nguyên tố chia hết n (kể cả chính n nếu n nguyên tố). Sách không chứng minh công thức này. Về trực giác: bắt đầu với danh sách n số dư {0, 1, …, n − 1}, rồi với mỗi số nguyên tố p chia hết n, gạch bỏ mọi bội của p trong danh sách. Ví dụ, ước nguyên tố của 45 là 3 và 5, nên

```text
φ(45) = 45 (1 − 1/3)(1 − 1/5) = 45 · (2/3) · (4/5) = 24
```

Nếu p nguyên tố thì ℤₚ* = {1, 2, …, p − 1} và

```text
φ(p) = p (1 − 1/p) = p − 1                                           (31.21)
```

Nếu n là hợp số thì φ(n) < n − 1, dù có thể chứng minh

```text
φ(n) > n / ( e^γ ln ln n + 3/(ln ln n) )                              (31.22)
```

với n ≥ 3, trong đó γ = 0,5772156649… là **hằng số Euler** (Euler's constant). Một cận dưới đơn giản hơn (nhưng lỏng hơn) cho n > 5 là

```text
φ(n) > n / (6 ln ln n)                                               (31.23)
```

Cận dưới (31.22) về cơ bản là tốt nhất có thể, vì

```text
lim inf_{n→∞}  φ(n) / (n / ln ln n) = e^(−γ)                         (31.24)
```

Kiểm tra số (người tổng hợp): n = 30 = 2 · 3 · 5: φ(30) = 30 · (1/2)(2/3)(4/5) = 8 (các số 1, 7, 11, 13, 17, 19, 23, 29). Cận (31.23): ln ln 30 = ln 3,401 ≈ 1,224, n/(6 · 1,224) ≈ 4,08 < 8. Đúng.

#### Nhóm con (Subgroups)

Nếu (S, ⊕) là một nhóm, S′ ⊆ S, và (S′, ⊕) cũng là nhóm, thì (S′, ⊕) là **nhóm con** (subgroup) của (S, ⊕). Ví dụ, các số nguyên chẵn tạo thành một nhóm con của các số nguyên với phép cộng. Định lý sau là công cụ hữu ích để nhận ra nhóm con.

**Định lý 31.14 (Tập con khác rỗng, đóng của nhóm hữu hạn là nhóm con).** Nếu (S, ⊕) là nhóm hữu hạn và S′ là tập con khác rỗng bất kỳ của S sao cho a ⊕ b ∈ S′ với mọi a, b ∈ S′, thì (S′, ⊕) là nhóm con của (S, ⊕). (Chứng minh để cho Exercise 31.3-3.)

Ví dụ, tập {0, 2, 4, 6} là nhóm con của ℤ₈, vì khác rỗng và đóng với phép + (tức đóng với +₈).

Định lý sau cho một ràng buộc cực kỳ hữu ích về cỡ của nhóm con; sách bỏ qua chứng minh.

**Định lý 31.15 (Định lý Lagrange — Lagrange's theorem).** Nếu (S, ⊕) là nhóm hữu hạn và (S′, ⊕) là nhóm con của (S, ⊕) thì |S′| là ước của |S|.

Nhóm con S′ của nhóm S là **nhóm con thực sự** (proper subgroup) nếu S′ ≠ S. Hệ quả sau được dùng trong phân tích phép thử nguyên tố Miller-Rabin ở Mục 31.8.

**Hệ quả 31.16.** Nếu S′ là nhóm con thực sự của nhóm hữu hạn S thì |S′| ≤ |S|/2. (Vì |S′| là ước của |S| và khác |S|, ước lớn nhất có thể là |S|/2 — giải thích của người tổng hợp.)

#### Nhóm con sinh bởi một phần tử (Subgroups generated by an element)

Định lý 31.14 cho một cách dễ để tạo nhóm con của nhóm hữu hạn (S, ⊕): chọn một phần tử a và lấy mọi phần tử sinh được từ a bằng phép toán của nhóm. Cụ thể, định nghĩa a^(k) với k ≥ 1 bởi

```text
a^(k) = ⊕_{i=1}^{k} a = a ⊕ a ⊕ ⋯ ⊕ a     (k lần a)
```

Ví dụ lấy a = 2 trong nhóm ℤ₆, dãy a^(1), a^(2), a^(3), … là

```text
2, 4, 0, 2, 4, 0, 2, 4, 0, …
```

Trong nhóm ℤₙ ta có a^(k) = ka mod n, còn trong nhóm ℤₙ* ta có a^(k) = aᵏ mod n. **Nhóm con sinh bởi a** (subgroup generated by a), ký hiệu ⟨a⟩ hay (⟨a⟩, ⊕), định nghĩa bởi

```text
⟨a⟩ = { a^(k) : k ≥ 1 }
```

Ta nói a **sinh ra** nhóm con ⟨a⟩, hay a là **phần tử sinh** (generator) của ⟨a⟩. Vì S hữu hạn, ⟨a⟩ là tập con hữu hạn của S, có thể là cả S. Vì tính kết hợp của ⊕ cho a^(i) ⊕ a^(j) = a^(i+j), ⟨a⟩ đóng, nên theo Định lý 31.14, ⟨a⟩ là nhóm con của S. Ví dụ trong ℤ₆:

```text
⟨0⟩ = {0}
⟨1⟩ = {0, 1, 2, 3, 4, 5}
⟨2⟩ = {0, 2, 4}
```

Tương tự, trong ℤ₇*:

```text
⟨1⟩ = {1}
⟨2⟩ = {1, 2, 4}
⟨3⟩ = {1, 2, 3, 4, 5, 6}
```

**Cấp** (order) của a (trong nhóm S), ký hiệu ord(a), là số nguyên dương nhỏ nhất t sao cho a^(t) = e.

**Định lý 31.17.** Với mọi nhóm hữu hạn (S, ⊕) và mọi a ∈ S, cấp của a bằng cỡ của nhóm con mà nó sinh ra: ord(a) = |⟨a⟩|.

*Chứng minh.* Đặt t = ord(a). Vì a^(t) = e và a^(t+k) = a^(t) ⊕ a^(k) = a^(k) với k ≥ 1, nếu i > t thì a^(i) = a^(j) với j < i nào đó. Vậy khi sinh phần tử bằng a, sau a^(t) không xuất hiện phần tử mới. Do đó ⟨a⟩ = {a^(1), a^(2), …, a^(t)}, và |⟨a⟩| ≤ t. Để chứng minh |⟨a⟩| ≥ t, ta chứng minh các phần tử a^(1), …, a^(t) phân biệt. Giả sử phản chứng a^(i) = a^(j) với 1 ≤ i < j ≤ t. Khi đó a^(i+k) = a^(j+k) với k ≥ 0. Nhưng đẳng thức này kéo theo a^(i+(t−j)) = a^(j+(t−j)) = e, mâu thuẫn vì i + (t − j) < t mà t là giá trị dương nhỏ nhất với a^(t) = e. Vậy các phần tử a^(1), …, a^(t) phân biệt và |⟨a⟩| ≥ t. Kết luận ord(a) = |⟨a⟩|. ∎

**Hệ quả 31.18.** Dãy a^(1), a^(2), … tuần hoàn với chu kỳ t = ord(a); tức a^(i) = a^(j) khi và chỉ khi i ≡ j (mod t).

Phù hợp với hệ quả này, định nghĩa a^(0) là e và a^(i) là a^(i mod t), với t = ord(a), cho mọi số nguyên i.

**Hệ quả 31.19.** Nếu (S, ⊕) là nhóm hữu hạn với đơn vị e thì với mọi a ∈ S, a^(|S|) = e.

*Chứng minh.* Định lý Lagrange (31.15) cho ord(a) | |S|, nên |S| ≡ 0 (mod t) với t = ord(a). Do đó a^(|S|) = a^(0) = e. ∎

Kiểm tra (người tổng hợp): trong ℤ₁₅* (|S| = 8), phần tử 2 có các lũy thừa 2, 4, 8, 1 nên ord(2) = 4, chia hết 8; và 2⁸ = 256 = 17 · 15 + 1 ≡ 1. Đúng.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: khuôn "nhóm hữu hạn" này là ngôn ngữ chung của mật mã hiện đại. Trao đổi khóa Diffie–Hellman làm việc trong nhóm ℤₚ* hoặc trong nhóm điểm trên đường cong elliptic; độ an toàn được phát biểu theo cấp của phần tử sinh, và định lý Lagrange là công cụ đầu tiên người ta dùng để kiểm tra một nhóm con có "đủ lớn" hay không.

### 5. Giải phương trình tuyến tính modulo (31.4 Solving modular linear equations, trang 946–950)

Xét bài toán tìm nghiệm của phương trình

```text
ax ≡ b (mod n)                                                       (31.25)
```

với a > 0 và n > 0. Bài toán có nhiều ứng dụng; ví dụ, nó là một phần của thủ tục tìm khóa trong hệ RSA ở Mục 31.7. Giả sử a, b, n cho trước, ta muốn tìm mọi giá trị x, modulo n, thỏa (31.25). Phương trình có thể có không, một, hoặc nhiều nghiệm.

Gọi ⟨a⟩ là nhóm con của ℤₙ sinh bởi a. Vì ⟨a⟩ = {a^(x) : x > 0} = {ax mod n : x > 0}, phương trình (31.25) có nghiệm khi và chỉ khi [b] ∈ ⟨a⟩. Định lý Lagrange (31.15) cho biết |⟨a⟩| phải là ước của n. Định lý sau đặc trưng chính xác ⟨a⟩.

**Định lý 31.20.** Với mọi số nguyên dương a và n, nếu d = gcd(a, n) thì trong ℤₙ

```text
⟨a⟩ = ⟨d⟩ = { 0, d, 2d, …, ((n/d) − 1)d }                            (31.26)
```

và do đó |⟨a⟩| = n/d.

*Chứng minh.* Trước hết chứng minh d ∈ ⟨a⟩. Nhớ rằng EXTENDED-EUCLID(a, n) cho các số nguyên x′, y′ với ax′ + ny′ = d. Vậy ax′ ≡ d (mod n), nên d ∈ ⟨a⟩. Nói cách khác, d là một bội của a trong ℤₙ.

Vì d ∈ ⟨a⟩, mọi bội của d thuộc ⟨a⟩, vì bội của một bội của a cũng là bội của a. Vậy ⟨a⟩ chứa mọi phần tử của {0, d, 2d, …, ((n/d) − 1)d}, tức ⟨d⟩ ⊆ ⟨a⟩.

Giờ chứng minh ⟨a⟩ ⊆ ⟨d⟩. Nếu m ∈ ⟨a⟩ thì m = ax mod n với số nguyên x nào đó, nên m = ax + ny với số nguyên y nào đó. Mà d | a và d | n, nên theo (31.4), d | m. Vậy m ∈ ⟨d⟩.

Kết hợp hai chiều được ⟨a⟩ = ⟨d⟩. Để thấy |⟨a⟩| = n/d, lưu ý có đúng n/d bội của d trong khoảng 0 tới n − 1. ∎

Ví dụ (người tổng hợp): a = 6, n = 15, d = 3: các bội 6x mod 15 với x = 1, 2, 3, … là 6, 12, 3, 9, 0, 6, … nên ⟨6⟩ = {0, 3, 6, 9, 12} = ⟨3⟩, cỡ 15/3 = 5.

**Hệ quả 31.21.** Phương trình ax ≡ b (mod n) giải được theo ẩn x khi và chỉ khi d | b, với d = gcd(a, n).

*Chứng minh.* Phương trình giải được khi và chỉ khi [b] ∈ ⟨a⟩, theo Định lý 31.20 tức là

```text
(b mod n) ∈ { 0, d, 2d, …, ((n/d) − 1)d }
```

Nếu 0 ≤ b < n thì b ∈ ⟨a⟩ khi và chỉ khi d | b, vì các phần tử của ⟨a⟩ đúng là các bội của d. Nếu b < 0 hoặc b ≥ n, hệ quả suy ra từ nhận xét d | b khi và chỉ khi d | (b mod n), vì b và b mod n chênh nhau một bội của n, mà bội của n lại là bội của d. ∎

**Hệ quả 31.22.** Phương trình ax ≡ b (mod n) hoặc có d nghiệm phân biệt modulo n, với d = gcd(a, n), hoặc vô nghiệm.

*Chứng minh.* Nếu ax ≡ b (mod n) có nghiệm thì b ∈ ⟨a⟩. Theo Định lý 31.17, ord(a) = |⟨a⟩|, nên Hệ quả 31.18 và Định lý 31.20 cho thấy dãy ai mod n, i = 0, 1, …, tuần hoàn với chu kỳ |⟨a⟩| = n/d. Nếu b ∈ ⟨a⟩ thì b xuất hiện đúng d lần trong dãy ai mod n, i = 0, 1, …, n − 1, vì khối độ dài n/d các giá trị của ⟨a⟩ lặp lại đúng d lần khi i tăng từ 0 tới n − 1. Các chỉ số x của d vị trí mà ax mod n = b chính là các nghiệm của ax ≡ b (mod n). ∎

**Định lý 31.23.** Đặt d = gcd(a, n), và giả sử d = ax′ + ny′ với các số nguyên x′, y′ (ví dụ do EXTENDED-EUCLID tính). Nếu d | b thì phương trình ax ≡ b (mod n) có một nghiệm là x₀, với

```text
x₀ = x′(b/d) mod n
```

*Chứng minh.*

```text
ax₀ ≡ ax′(b/d)   (mod n)
    ≡ d(b/d)     (mod n)     (vì ax′ ≡ d (mod n))
    ≡ b          (mod n)
```

nên x₀ là nghiệm của ax ≡ b (mod n). ∎

**Định lý 31.24.** Giả sử phương trình ax ≡ b (mod n) giải được (tức d | b, d = gcd(a, n)) và x₀ là một nghiệm bất kỳ. Khi đó phương trình có đúng d nghiệm phân biệt modulo n, cho bởi xᵢ = x₀ + i(n/d) với i = 0, 1, …, d − 1.

*Chứng minh.* Vì n/d > 0 và 0 ≤ i(n/d) < n với i = 0, 1, …, d − 1, các giá trị x₀, x₁, …, x_{d−1} phân biệt modulo n. Vì x₀ là nghiệm, ax₀ mod n ≡ b (mod n). Do đó với i = 0, 1, …, d − 1:

```text
axᵢ mod n = a(x₀ + in/d) mod n
          = (ax₀ + ain/d) mod n
          = ax₀ mod n          (vì d | a nên ain/d là bội của n)
          ≡ b (mod n)
```

nên axᵢ ≡ b (mod n), xᵢ cũng là nghiệm. Theo Hệ quả 31.22, phương trình có đúng d nghiệm, nên x₀, x₁, …, x_{d−1} là tất cả. ∎

Đã có đủ toán để giải ax ≡ b (mod n); thuật toán sau in mọi nghiệm. Đầu vào a và n là số nguyên dương bất kỳ, b là số nguyên bất kỳ.

```text
MODULAR-LINEAR-EQUATION-SOLVER(a, b, n)
1  (d, x′, y′) = EXTENDED-EUCLID(a, n)
2  if d | b
3      x₀ = x′(b/d) mod n
4      for i = 0 to d − 1
5          print (x₀ + i(n/d)) mod n
6  else print "no solutions"
```

**Ví dụ của sách:** phương trình 14x ≡ 30 (mod 100) (a = 14, b = 30, n = 100). Gọi EXTENDED-EUCLID ở dòng 1 được (d, x′, y′) = (2, −7, 1) (kiểm tra: 14 · (−7) + 100 · 1 = 2). Vì 2 | 30, dòng 3–5 chạy. Dòng 3 tính x₀ = (−7)(15) mod 100 = −105 mod 100 = 95. Vòng lặp dòng 4–5 in hai nghiệm 95 và 45 (= 95 + 50 − 100). Kiểm tra: 14 · 95 = 1330 ≡ 30 và 14 · 45 = 630 ≡ 30 (mod 100).

Chạy tay EXTENDED-EUCLID(14, 100) (người tổng hợp):

| a | b | ⌊a/b⌋ | d | x | y |
|---|---|---|---|---|---|
| 14 | 100 | 0 | 2 | −7 | 1 |
| 100 | 14 | 7 | 2 | 1 | −7 |
| 14 | 2 | 7 | 2 | 0 | 1 |
| 2 | 0 | — | 2 | 1 | 0 |

(Tầng đầu: vì 14 < 100 nên ⌊14/100⌋ = 0, Euclid chỉ đổi chỗ hai đối số, đúng như sách đã nói.)

Thủ tục MODULAR-LINEAR-EQUATION-SOLVER hoạt động như sau. Dòng 1 tính d = gcd(a, n) cùng hai giá trị x′, y′ với d = ax′ + ny′, cho thấy x′ là nghiệm của ax′ ≡ d (mod n). Nếu d không chia hết b thì ax ≡ b (mod n) vô nghiệm, theo Hệ quả 31.21. Dòng 2 kiểm tra d | b; nếu không, dòng 6 báo vô nghiệm. Ngược lại, dòng 3 tính một nghiệm x₀ theo Định lý 31.23. Có một nghiệm rồi, Định lý 31.24 nói rằng cộng các bội của n/d, modulo n, cho d − 1 nghiệm còn lại. Vòng for ở dòng 4–5 in đủ d nghiệm, bắt đầu từ x₀ và cách nhau n/d, modulo n.

MODULAR-LINEAR-EQUATION-SOLVER thực hiện O(lg n + gcd(a, n)) phép toán số học, vì EXTENDED-EUCLID thực hiện O(lg n) phép toán số học, và mỗi vòng lặp dòng 4–5 thực hiện một số hằng phép toán.

Các hệ quả sau của Định lý 31.24 là những trường hợp đặc biệt đáng chú ý.

**Hệ quả 31.25.** Với mọi n > 1, nếu gcd(a, n) = 1 thì phương trình ax ≡ b (mod n) có nghiệm duy nhất modulo n.

Nếu b = 1 — một trường hợp thường gặp và rất quan trọng — thì x cần tìm là **nghịch đảo nhân** (multiplicative inverse) của a modulo n.

**Hệ quả 31.26.** Với mọi n > 1, nếu gcd(a, n) = 1 thì phương trình ax ≡ 1 (mod n) có nghiệm duy nhất modulo n. Ngược lại, nó vô nghiệm.

Nhờ Hệ quả 31.26, có thể dùng ký hiệu a⁻¹ mod n để chỉ **cái** nghịch đảo nhân (duy nhất) của a modulo n khi a và n nguyên tố cùng nhau. Nếu gcd(a, n) = 1 thì nghiệm duy nhất của ax ≡ 1 (mod n) là số nguyên x mà EXTENDED-EUCLID trả về, vì đẳng thức

```text
gcd(a, n) = 1 = ax + ny
```

kéo theo ax ≡ 1 (mod n). Vậy có thể tính hiệu quả a⁻¹ mod n bằng EXTENDED-EUCLID.

Ví dụ (người tổng hợp): tính 17⁻¹ mod 43. EUCLID: 43 = 2 · 17 + 9; 17 = 1 · 9 + 8; 9 = 1 · 8 + 1. Lần ngược: 1 = 9 − 8 = 9 − (17 − 9) = 2 · 9 − 17 = 2(43 − 2 · 17) − 17 = 2 · 43 − 5 · 17. Vậy 17 · (−5) ≡ 1, tức 17⁻¹ ≡ 38 (mod 43). Kiểm tra: 17 · 38 = 646 = 15 · 43 + 1.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: giải phương trình đồng dư tuyến tính xuất hiện trong bài toán lập lịch theo chu kỳ (hai sự kiện lặp với chu kỳ khác nhau gặp nhau khi nào), trong bộ sinh số giả ngẫu nhiên đồng dư tuyến tính (tìm bước "nhảy ngược"), và trong lập trình thi đấu dưới dạng "tìm x nhỏ nhất với ax ≡ b (mod n)" — đúng thủ tục MODULAR-LINEAR-EQUATION-SOLVER.

### 6. Định lý số dư Trung Hoa (31.5 The Chinese remainder theorem, trang 950–954)

Khoảng năm 100 sau Công nguyên, nhà toán học Trung Hoa Tôn Tử (sách viết Sun-Tsŭ) giải bài toán tìm các số nguyên x chia cho 3, 5, 7 lần lượt dư 2, 3, 2. Một nghiệm là x = 23 (23 = 7 · 3 + 2 = 4 · 5 + 3 = 3 · 7 + 2); mọi nghiệm có dạng 23 + 105k với k nguyên tùy ý. "Định lý số dư Trung Hoa" cho một tương ứng giữa một hệ phương trình theo một tập modulus đôi một nguyên tố cùng nhau (ví dụ 3, 5, 7) và một phương trình theo modulus là tích của chúng (ví dụ 105).

Định lý có hai ứng dụng lớn. Cho số nguyên n phân tích thành n = n₁n₂⋯nₖ, các thừa số nᵢ đôi một nguyên tố cùng nhau. Thứ nhất, định lý là một "định lý cấu trúc" mang tính mô tả: nó nói cấu trúc của ℤₙ giống hệt cấu trúc của tích Descartes ℤₙ₁ × ℤₙ₂ × ⋯ × ℤₙₖ, với phép cộng và nhân theo từng thành phần, thành phần thứ i modulo nᵢ. Thứ hai, mô tả này giúp thiết kế thuật toán hiệu quả, vì làm việc trong từng hệ ℤₙᵢ có thể rẻ hơn (tính theo phép toán bit) so với làm việc modulo n.

**Định lý 31.27 (Định lý số dư Trung Hoa — Chinese remainder theorem).** Cho n = n₁n₂⋯nₖ, các nᵢ đôi một nguyên tố cùng nhau. Xét tương ứng

```text
a ↔ (a₁, a₂, …, aₖ)                                                  (31.27)
```

với a ∈ ℤₙ, aᵢ ∈ ℤₙᵢ, và aᵢ = a mod nᵢ với i = 1, 2, …, k. Khi đó ánh xạ (31.27) là một tương ứng một-một (song ánh) giữa ℤₙ và tích Descartes ℤₙ₁ × ℤₙ₂ × ⋯ × ℤₙₖ. Các phép toán trên phần tử của ℤₙ có thể thực hiện tương đương trên các bộ k thành phần tương ứng, bằng cách làm phép toán độc lập ở từng vị trí trong hệ thích hợp. Tức là nếu

```text
a ↔ (a₁, a₂, …, aₖ)
b ↔ (b₁, b₂, …, bₖ)
```

thì

```text
(a + b) mod n ↔ ((a₁ + b₁) mod n₁, …, (aₖ + bₖ) mod nₖ)              (31.28)
(a − b) mod n ↔ ((a₁ − b₁) mod n₁, …, (aₖ − bₖ) mod nₖ)              (31.29)
(ab) mod n    ↔ (a₁b₁ mod n₁, …, aₖbₖ mod nₖ)                        (31.30)
```

*Chứng minh.* Chuyển giữa hai cách biểu diễn khá thẳng. Đi từ a sang (a₁, a₂, …, aₖ) rất dễ, chỉ cần k phép "mod".

Tính a từ (a₁, a₂, …, aₖ) phức tạp hơn chút. Trước hết định nghĩa mᵢ = n/nᵢ với i = 1, 2, …, k; như vậy mᵢ là tích mọi nⱼ khác nᵢ: mᵢ = n₁n₂⋯nᵢ₋₁nᵢ₊₁⋯nₖ. Tiếp theo định nghĩa

```text
cᵢ = mᵢ (mᵢ⁻¹ mod nᵢ)                                                (31.31)
```

với i = 1, 2, …, k. (31.31) luôn được định nghĩa đúng: vì mᵢ và nᵢ nguyên tố cùng nhau (theo Định lý 31.6), Hệ quả 31.26 bảo đảm mᵢ⁻¹ mod nᵢ tồn tại. Cuối cùng, tính a theo a₁, …, aₖ:

```text
a ≡ (a₁c₁ + a₂c₂ + ⋯ + aₖcₖ)  (mod n)                                (31.32)
```

Giờ chứng minh (31.32) bảo đảm a ≡ aᵢ (mod nᵢ) với i = 1, …, k. Lưu ý nếu j ≠ i thì mⱼ ≡ 0 (mod nᵢ) (vì nᵢ là một thừa số của mⱼ), kéo theo cⱼ ≡ mⱼ ≡ 0 (mod nᵢ). Cũng lưu ý cᵢ ≡ 1 (mod nᵢ), từ (31.31). Như vậy có tương ứng đẹp và hữu ích

```text
cᵢ ↔ (0, 0, …, 0, 1, 0, …, 0)
```

— một vectơ toàn số 0 trừ tọa độ thứ i bằng 1; các cᵢ vì vậy tạo thành một "cơ sở" cho cách biểu diễn, theo một nghĩa nào đó. Do đó với mỗi i,

```text
a ≡ aᵢcᵢ                    (mod nᵢ)
  ≡ aᵢmᵢ(mᵢ⁻¹ mod nᵢ)       (mod nᵢ)
  ≡ aᵢ                      (mod nᵢ)
```

đúng như cần chứng minh: cách tính a từ các aᵢ cho kết quả a thỏa các ràng buộc a ≡ aᵢ (mod nᵢ). Tương ứng là một-một vì có thể biến đổi theo cả hai chiều. Cuối cùng, (31.28)–(31.30) suy trực tiếp từ Exercise 31.1-7, vì x mod nᵢ = (x mod n) mod nᵢ với mọi x và mọi i. ∎

Các hệ quả sau được dùng về sau trong chương.

**Hệ quả 31.28.** Nếu n₁, n₂, …, nₖ đôi một nguyên tố cùng nhau và n = n₁n₂⋯nₖ, thì với mọi số nguyên a₁, a₂, …, aₖ, hệ phương trình

```text
x ≡ aᵢ (mod nᵢ),   i = 1, 2, …, k
```

có nghiệm duy nhất modulo n theo ẩn x.

**Hệ quả 31.29.** Nếu n₁, n₂, …, nₖ đôi một nguyên tố cùng nhau và n = n₁n₂⋯nₖ, thì với mọi số nguyên x và a: x ≡ a (mod nᵢ) với mọi i = 1, 2, …, k khi và chỉ khi x ≡ a (mod n).

#### Ví dụ của sách

Cho hai phương trình

```text
a ≡ 2 (mod 5)
a ≡ 3 (mod 13)
```

nên a₁ = 2, n₁ = m₂ = 5, a₂ = 3, n₂ = m₁ = 13, và cần tính a mod 65 (n = n₁n₂ = 65). Vì 13⁻¹ ≡ 2 (mod 5) (13 ≡ 3 và 3 · 2 = 6 ≡ 1) và 5⁻¹ ≡ 8 (mod 13) (5 · 8 = 40 = 3 · 13 + 1), ta có

```text
c₁ = 13 · (2 mod 5)  = 26
c₂ = 5 · (8 mod 13)  = 40
```

và

```text
a ≡ 2 · 26 + 3 · 40   (mod 65)
  ≡ 52 + 120          (mod 65)
  ≡ 42                (mod 65)
```

Kiểm tra: 42 = 8 · 5 + 2 và 42 = 3 · 13 + 3. Cũng kiểm tra "cơ sở": c₁ = 26 ≡ 1 (mod 5), ≡ 0 (mod 13); c₂ = 40 ≡ 0 (mod 5), ≡ 1 (mod 13).

Hình 31.3 của sách minh họa định lý với n₁ = 5 và n₂ = 13 (c₁ = 26, c₂ = 40). Ô hàng i, cột j chứa giá trị a modulo 65 sao cho a mod 5 = i và a mod 13 = j. Chép lại bảng:

| a mod 5 \ a mod 13 | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **0** | 0 | 40 | 15 | 55 | 30 | 5 | 45 | 20 | 60 | 35 | 10 | 50 | 25 |
| **1** | 26 | 1 | 41 | 16 | 56 | 31 | 6 | 46 | 21 | 61 | 36 | 11 | 51 |
| **2** | 52 | 27 | 2 | 42 | 17 | 57 | 32 | 7 | 47 | 22 | 62 | 37 | 12 |
| **3** | 13 | 53 | 28 | 3 | 43 | 18 | 58 | 33 | 8 | 48 | 23 | 63 | 38 |
| **4** | 39 | 14 | 54 | 29 | 4 | 44 | 19 | 59 | 34 | 9 | 49 | 24 | 64 |

Hàng 0, cột 0 chứa 0. Hàng 4, cột 12 chứa 64 (tương đương −1). Vì c₁ = 26, đi xuống một hàng làm a tăng 26 (modulo 65). Tương tự, c₂ = 40 nghĩa là sang phải một cột làm a tăng 40. Tăng a thêm 1 tương ứng đi chéo xuống-phải một ô, quay vòng từ dưới lên trên và từ phải sang trái. Ví dụ đã giải ở trên nằm ở hàng 2, cột 3: đúng là 42.

Vậy có thể làm việc modulo n trực tiếp, hoặc làm trong biểu diễn đã biến đổi với các phép tính riêng modulo nᵢ, tùy cái nào tiện. Hai cách tính hoàn toàn tương đương.

Áp dụng lại cho bài toán của Tôn Tử (người tổng hợp): n = 3 · 5 · 7 = 105, m₁ = 35, m₂ = 21, m₃ = 15. 35 ≡ 2 (mod 3), 2⁻¹ ≡ 2 nên c₁ = 70; 21 ≡ 1 (mod 5) nên c₂ = 21; 15 ≡ 1 (mod 7) nên c₃ = 15. a ≡ 2 · 70 + 3 · 21 + 2 · 15 = 140 + 63 + 30 = 233 ≡ 23 (mod 105). Khớp với 23 + 105k.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: cài đặt RSA thực tế dùng định lý số dư Trung Hoa để giải mã nhanh khoảng bốn lần — thay vì tính Cᵈ mod n với n 2048 bit, tính riêng modulo p và modulo q (mỗi số 1024 bit, số mũ rút gọn modulo p − 1 và q − 1) rồi ghép lại. Định lý cũng là cơ sở của "hệ thống số dư" (residue number system) trong phần cứng xử lý tín hiệu và của nhân đa thức theo nhiều modulus nguyên tố trong các thư viện số học.

### 7. Lũy thừa của một phần tử (31.6 Powers of an element, trang 954–958)

Như thường xét các bội của a modulo n, ta xét dãy lũy thừa của a modulo n, với a ∈ ℤₙ*:

```text
a⁰, a¹, a², a³, …                                                    (31.33)
```

modulo n. Đánh chỉ số từ 0, giá trị thứ 0 của dãy là a⁰ mod n = 1, giá trị thứ i là aⁱ mod n. Ví dụ lũy thừa của 3 modulo 7:

| i | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | … |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 3ⁱ mod 7 | 1 | 3 | 2 | 6 | 4 | 5 | 1 | 3 | 2 | 6 | 4 | 5 | … |

còn lũy thừa của 2 modulo 7:

| i | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | … |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 2ⁱ mod 7 | 1 | 2 | 4 | 1 | 2 | 4 | 1 | 2 | 4 | 1 | 2 | 4 | … |

Trong mục này, ⟨a⟩ ký hiệu nhóm con của ℤₙ* sinh bởi a bằng phép nhân lặp, và ordₙ(a) ("cấp của a modulo n") là cấp của a trong ℤₙ*. Ví dụ ⟨2⟩ = {1, 2, 4} trong ℤ₇*, ord₇(2) = 3. Dùng định nghĩa φ(n) là cỡ của ℤₙ*, dịch Hệ quả 31.19 sang ngôn ngữ ℤₙ* được định lý Euler, và áp dụng riêng cho ℤₚ* với p nguyên tố được định lý Fermat.

**Định lý 31.30 (Định lý Euler — Euler's theorem).** Với mọi số nguyên n > 1:

```text
a^φ(n) ≡ 1 (mod n)   với mọi a ∈ ℤₙ*
```

**Định lý 31.31 (Định lý Fermat — Fermat's theorem).** Nếu p là số nguyên tố thì

```text
a^(p−1) ≡ 1 (mod p)   với mọi a ∈ ℤₚ*
```

*Chứng minh.* Theo (31.21), φ(p) = p − 1 nếu p nguyên tố. ∎

Định lý Fermat áp dụng cho mọi phần tử của ℤₚ trừ 0, vì 0 ∉ ℤₚ*. Tuy nhiên, với mọi a ∈ ℤₚ ta có aᵖ ≡ a (mod p) nếu p nguyên tố.

Kiểm tra (người tổng hợp): n = 10, φ(10) = 4, ℤ₁₀* = {1, 3, 7, 9}: 3⁴ = 81 ≡ 1, 7⁴ = 2401 ≡ 1, 9⁴ = 6561 ≡ 1 (mod 10). Đúng.

Nếu ordₙ(g) = |ℤₙ*| thì mọi phần tử của ℤₙ* là một lũy thừa của g modulo n, và g là **căn nguyên thủy** (primitive root) hay **phần tử sinh** (generator) của ℤₙ*. Ví dụ 3 là căn nguyên thủy modulo 7 (bảng trên: 3ⁱ chạy qua cả 6 phần tử), còn 2 thì không (chỉ sinh {1, 2, 4}). Nếu ℤₙ* có căn nguyên thủy, nhóm ℤₙ* là **cyclic**. Sách bỏ qua chứng minh định lý sau (dẫn Niven và Zuckerman).

**Định lý 31.32.** Các giá trị n > 1 làm ℤₙ* cyclic là 2, 4, pᵉ và 2pᵉ, với mọi số nguyên tố p > 2 và mọi số nguyên dương e.

Ví dụ (người tổng hợp): ℤ₈* = {1, 3, 5, 7} không cyclic vì 3² = 9 ≡ 1, 5² = 25 ≡ 1, 7² = 49 ≡ 1 (mod 8) — mọi phần tử khác 1 có cấp 2, không phần tử nào có cấp 4; đúng với định lý vì 8 không thuộc dạng nào trong danh sách.

Nếu g là căn nguyên thủy của ℤₙ* và a là phần tử bất kỳ của ℤₙ*, thì tồn tại z sao cho gᶻ ≡ a (mod n). Số z này là **logarit rời rạc** (discrete logarithm) hay **chỉ số** (index) của a modulo n theo cơ số g, ký hiệu ind_{n,g}(a). Ví dụ ind₇,₃(6) = 3 vì 3³ = 27 ≡ 6 (mod 7).

**Định lý 31.33 (Định lý logarit rời rạc — Discrete logarithm theorem).** Nếu g là căn nguyên thủy của ℤₙ* thì gˣ ≡ gʸ (mod n) khi và chỉ khi x ≡ y (mod φ(n)).

*Chứng minh.* Trước hết giả sử x ≡ y (mod φ(n)). Khi đó x = y + kφ(n) với số nguyên k nào đó. Do đó

```text
gˣ ≡ g^(y + kφ(n))    (mod n)
   ≡ gʸ · (g^φ(n))ᵏ   (mod n)
   ≡ gʸ · 1ᵏ          (mod n)     (theo định lý Euler)
   ≡ gʸ               (mod n)
```

Ngược lại, giả sử gˣ ≡ gʸ (mod n). Vì dãy lũy thừa của g sinh mọi phần tử của ⟨g⟩ và |⟨g⟩| = φ(n), Hệ quả 31.18 cho thấy dãy lũy thừa của g tuần hoàn với chu kỳ φ(n). Do đó nếu gˣ ≡ gʸ (mod n) thì phải có x ≡ y (mod φ(n)). ∎

#### Căn bậc hai của 1

Giờ chuyển sang căn bậc hai của 1 modulo một lũy thừa số nguyên tố. Định lý sau sẽ hữu ích khi xây dựng thuật toán thử nguyên tố ở Mục 31.8.

**Định lý 31.34.** Nếu p là số nguyên tố lẻ và e ≥ 1 thì phương trình

```text
x² ≡ 1 (mod pᵉ)                                                      (31.34)
```

chỉ có hai nghiệm, là x = 1 và x = −1.

*Chứng minh.* Phương trình (31.34) tương đương với

```text
pᵉ | (x − 1)(x + 1)
```

Vì p > 2, p có thể chia hết (x − 1) hoặc (x + 1) nhưng không chia hết cả hai. (Nếu không, theo (31.3), p cũng chia hết hiệu của chúng (x + 1) − (x − 1) = 2.) Nếu p ∤ (x − 1) thì gcd(pᵉ, x − 1) = 1, và theo Hệ quả 31.5 ta có pᵉ | (x + 1), tức x ≡ −1 (mod pᵉ). Đối xứng, nếu p ∤ (x + 1) thì gcd(pᵉ, x + 1) = 1, và Hệ quả 31.5 cho pᵉ | (x − 1), tức x ≡ 1 (mod pᵉ). Vậy x ≡ −1 (mod pᵉ) hoặc x ≡ 1 (mod pᵉ). ∎

Số x là **căn bậc hai không tầm thường của 1 modulo n** (nontrivial square root of 1, modulo n) nếu nó thỏa x² ≡ 1 (mod n) nhưng không đồng dư với một trong hai căn "tầm thường" 1 hoặc −1 modulo n. Ví dụ 6 là căn bậc hai không tầm thường của 1 modulo 35 (6² = 36 ≡ 1, mà 6 ≢ 1 và 6 ≢ 34). Hệ quả sau của Định lý 31.34 được dùng trong chứng minh tính đúng của phép thử Miller-Rabin.

**Hệ quả 31.35.** Nếu tồn tại căn bậc hai không tầm thường của 1 modulo n thì n là hợp số.

*Chứng minh.* Theo phản đảo của Định lý 31.34, nếu tồn tại căn bậc hai không tầm thường của 1 modulo n thì n không thể là số nguyên tố lẻ hay lũy thừa của số nguyên tố lẻ. Nếu x² ≡ 1 (mod 2) thì x ≡ 1 (mod 2), nên mọi căn bậc hai của 1 modulo 2 đều tầm thường. Vậy n không thể là số nguyên tố. Cuối cùng, phải có n > 1 thì mới tồn tại căn bậc hai không tầm thường của 1. Vậy n là hợp số. ∎

Nhận xét của người tổng hợp: căn 6 modulo 35 "lộ" thừa số: gcd(6 − 1, 35) = 5 và gcd(6 + 1, 35) = 7 — đúng như Exercise 31.8-3 yêu cầu chứng minh.

#### Lũy thừa bằng bình phương lặp (Raising to powers with repeated squaring)

Một phép toán hay gặp trong tính toán số học là nâng một số lên lũy thừa modulo một số khác, gọi là **lũy thừa modulo** (modular exponentiation). Cụ thể, cần cách hiệu quả tính aᵇ mod n với a, b nguyên không âm và n nguyên dương. Lũy thừa modulo là phép toán thiết yếu trong nhiều thủ tục thử nguyên tố và trong hệ RSA. Phương pháp **bình phương lặp** (repeated squaring) giải hiệu quả bài toán này nhờ biểu diễn nhị phân của b.

Gọi ⟨b_k, b_{k−1}, …, b₁, b₀⟩ là biểu diễn nhị phân của b (tức biểu diễn dài k + 1 bit, b_k là bit cao nhất, b₀ là bit thấp nhất). Thủ tục sau tính aᶜ mod n khi c được tăng dần bằng các phép nhân đôi và cộng một từ 0 tới b.

```text
MODULAR-EXPONENTIATION(a, b, n)
 1  c = 0
 2  d = 1
 3  let ⟨b_k, b_{k−1}, …, b₀⟩ be the binary representation of b
 4  for i = k downto 0
 5      c = 2c
 6      d = (d · d) mod n
 7      if bᵢ == 1
 8          c = c + 1
 9          d = (d · a) mod n
10  return d
```

(Dòng 3: "gọi ⟨b_k, …, b₀⟩ là biểu diễn nhị phân của b".) Việc dùng phép bình phương ở dòng 6 trong mỗi vòng lặp là lý do của tên gọi "bình phương lặp". Biến c thực ra không cần cho thuật toán, nhưng được thêm vào để phát biểu bất biến vòng lặp hai phần:

Ngay trước mỗi vòng lặp for ở dòng 4–9,
1. giá trị của c bằng tiền tố ⟨b_k, b_{k−1}, …, b_{i+1}⟩ của biểu diễn nhị phân của b, và
2. d = aᶜ mod n.

Dùng bất biến như sau:

- **Khởi tạo:** ban đầu i = k, nên tiền tố ⟨b_k, …, b_{i+1}⟩ rỗng, ứng với c = 0. Hơn nữa d = 1 = a⁰ mod n.
- **Duy trì:** gọi c′ và d′ là giá trị của c và d ở cuối một vòng lặp, tức giá trị trước vòng lặp sau. Mỗi vòng cập nhật c′ = 2c (nếu bᵢ = 0) hoặc c′ = 2c + 1 (nếu bᵢ = 1), nên c đúng trước vòng sau. Nếu bᵢ = 0 thì d′ = d² mod n = (aᶜ)² mod n = a^(2c) mod n = a^(c′) mod n. Nếu bᵢ = 1 thì d′ = d²a mod n = (aᶜ)²a mod n = a^(2c+1) mod n = a^(c′) mod n. Trong cả hai trường hợp d = aᶜ mod n trước vòng lặp sau.
- **Kết thúc:** khi kết thúc, i = −1. Vậy c = b, vì c mang giá trị tiền tố ⟨b_k, …, b₀⟩ — toàn bộ biểu diễn nhị phân của b. Do đó d = aᶜ mod n = aᵇ mod n.

Nếu đầu vào a, b, n là các số β-bit thì tổng số phép toán số học là O(β) và tổng số phép toán bit là O(β³).

**Ví dụ của sách (Hình 31.4):** a = 7, b = 560 = ⟨1000110000⟩ (nhị phân), n = 561. Giá trị sau mỗi lần thực hiện vòng for (dãy số mũ đã dùng nằm ở hàng c):

| i | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
|---|---|---|---|---|---|---|---|---|---|---|
| bᵢ | 1 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| c | 1 | 2 | 4 | 8 | 17 | 35 | 70 | 140 | 280 | 560 |
| d | 7 | 49 | 157 | 526 | 160 | 241 | 298 | 166 | 67 | 1 |

Kết quả cuối là 1, tức 7⁵⁶⁰ ≡ 1 (mod 561). Kiểm tra vài bước (người tổng hợp): i = 7: 49² = 2401 = 4 · 561 + 157. i = 6: 157² = 24.649 = 43 · 561 + 526. i = 5: 526² = 276.676 = 493 · 561 + 103, nên sau bình phương d = 103; bit b₅ = 1 nên nhân thêm 7: 103 · 7 = 721 = 561 + 160, d = 160. Khớp bảng. i = 4: 160² = 25.600 = 45 · 561 + 355; 355 · 7 = 2485 = 4 · 561 + 241. Khớp. Bước cuối: 67² = 4489 = 8 · 561 + 1. Khớp.

Lưu ý: 561 = 3 · 11 · 17 là hợp số, nhưng 7⁵⁶⁰ ≡ 1 (mod 561) như thể 561 là số nguyên tố — đây chính là số Carmichael nhỏ nhất, sẽ gặp lại ở Mục 31.8. Và dãy d ở các bước cuối (241, 298, 166, 67, 1) là dãy mà WITNESS(7, 561) tính; 67 là căn bậc hai không tầm thường của 1 modulo 561.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: lũy thừa modulo là "vòng lặp nóng" của mọi thư viện mật mã khóa công khai (RSA, Diffie–Hellman); các cài đặt thật dùng biến thể cửa sổ trượt (xử lý vài bit một lúc) và phép nhân Montgomery để tránh phép chia, và phải viết theo kiểu "thời gian hằng" (không rẽ nhánh theo bit của số mũ bí mật) để không lộ khóa qua thời gian chạy — điều mà dòng 7 của MODULAR-EXPONENTIATION vi phạm. Ngoài mật mã, bình phương lặp là kỹ thuật chuẩn trong lập trình thi đấu để tính aᵇ mod 10⁹ + 7 hay lũy thừa ma trận.

### 8. Hệ mật mã khóa công khai RSA (31.7 The RSA public-key cryptosystem, trang 958–965)

Với hệ mật mã khóa công khai, ta có thể mã hóa thông điệp gửi giữa hai bên sao cho kẻ nghe lén thu được bản mã cũng không giải được. Hệ mật mã khóa công khai còn cho phép một bên gắn một "chữ ký số" không giả mạo được vào cuối thông điệp điện tử. Chữ ký như vậy là phiên bản điện tử của chữ ký tay trên giấy: ai cũng kiểm tra dễ dàng, không ai giả mạo được, nhưng mất hiệu lực nếu bất kỳ bit nào của thông điệp bị sửa. Do đó nó xác thực cả danh tính người ký lẫn nội dung thông điệp được ký. Đó là công cụ hoàn hảo cho hợp đồng thương mại ký điện tử, séc điện tử, đơn đặt hàng điện tử và các giao tiếp điện tử khác mà các bên muốn xác thực.

Hệ RSA dựa vào sự khác biệt lớn giữa việc tìm số nguyên tố lớn (dễ) và việc phân tích tích của hai số nguyên tố lớn (khó). Mục 31.8 mô tả thủ tục hiệu quả để tìm số nguyên tố lớn, Mục 31.9 bàn bài toán phân tích số nguyên lớn.

#### Hệ mật mã khóa công khai (Public-key cryptosystems)

Trong hệ mật mã khóa công khai, mỗi người tham gia có một **khóa công khai** (public key) và một **khóa bí mật** (secret key). Mỗi khóa là một mẩu thông tin; ví dụ trong RSA, mỗi khóa là một cặp số nguyên. Hai nhân vật truyền thống trong ví dụ mật mã là "Alice" và "Bob"; ký hiệu khóa công khai và bí mật của họ là P_A, S_A cho Alice và P_B, S_B cho Bob.

Mỗi người tự tạo khóa công khai và bí mật của mình. Khóa bí mật được giữ kín, còn khóa công khai có thể tiết lộ cho bất kỳ ai, thậm chí công bố. Thực ra thường tiện khi giả sử khóa công khai của mọi người có trong một danh bạ công cộng, để ai cũng dễ lấy khóa công khai của người khác.

Khóa công khai và bí mật xác định các hàm áp dụng được lên mọi thông điệp. Gọi 𝒟 là tập các thông điệp cho phép; ví dụ 𝒟 có thể là tập mọi dãy bit hữu hạn. Trong công thức đơn giản nhất và nguyên thủy của mật mã khóa công khai, yêu cầu khóa công khai và bí mật xác định các hàm một-một từ 𝒟 vào chính nó. Ký hiệu hàm ứng với khóa công khai P_A của Alice là P_A() và hàm ứng với khóa bí mật S_A là S_A(). Các hàm P_A() và S_A() vì vậy là hoán vị của 𝒟. Giả sử P_A() và S_A() tính được hiệu quả khi biết khóa tương ứng.

Khóa công khai và bí mật của một người là một "cặp ăn khớp": chúng xác định hai hàm ngược nhau. Tức là

```text
M = S_A(P_A(M))                                                      (31.35)
M = P_A(S_A(M))                                                      (31.36)
```

với mọi thông điệp M ∈ 𝒟. Biến đổi M bằng hai khóa P_A và S_A liên tiếp, theo thứ tự nào cũng được, cho lại M.

Trong hệ mật mã khóa công khai, yêu cầu không ai ngoài Alice tính được hàm S_A() trong một lượng thời gian thực tế. Giả định này then chốt để thư mã hóa gửi Alice được giữ kín và để biết chữ ký số của Alice là thật. Alice phải giữ S_A bí mật; nếu không, cô mất tính duy nhất và hệ không thể cho cô các năng lực riêng. Giả định "chỉ Alice tính được S_A()" phải đúng dù ai cũng biết P_A và tính được P_A() — hàm ngược của S_A() — một cách hiệu quả. Để thiết kế được hệ khóa công khai dùng được, phải tìm cách tạo một hệ trong đó có thể công bố phép biến đổi P_A() mà không vì thế tiết lộ cách tính phép biến đổi ngược S_A(). Nhiệm vụ này trông rất khó, nhưng sách sẽ chỉ cách làm.

**Mã hóa.** Hình 31.5 của sách mô tả: Bob muốn gửi Alice thông điệp M được mã hóa, để với kẻ nghe lén nó trông như chuỗi vô nghĩa. Vẽ lại sơ đồ:

```text
        Bob                                                    Alice
      mã hóa              kênh truyền thông                  giải mã
  M ───▶[ P_A ]──────────── C = P_A(M) ──────────●─────────▶[ S_A ]───▶ M
                                                 │
                                    kẻ nghe lén  ╰──▶ C
```

Kịch bản gửi thông điệp:
- Bob lấy khóa công khai P_A của Alice (từ danh bạ công cộng hoặc trực tiếp từ Alice).
- Bob tính **bản mã** (ciphertext) C = P_A(M) ứng với thông điệp M và gửi C cho Alice.
- Khi nhận bản mã C, Alice áp khóa bí mật S_A để lấy lại thông điệp gốc: S_A(C) = S_A(P_A(M)) = M.

Vì S_A() và P_A() là hai hàm ngược nhau, Alice tính được M từ C. Vì chỉ Alice tính được S_A(), chỉ Alice tính được M từ C. Vì Bob mã hóa M bằng P_A(), chỉ Alice hiểu được thông điệp truyền đi. Kẻ nghe lén bắt được bản mã cũng không có thông tin gì về M.

**Chữ ký số.** Có thể cài đặt chữ ký số trong cùng mô hình. (Có những cách khác để xây chữ ký số nhưng sách không đi vào.) Giả sử Alice muốn gửi Bob một trả lời M′ có chữ ký số. Hình 31.6 của sách mô tả kịch bản; vẽ lại:

```text
           Alice                                         Bob
            ký                                         kiểm tra
     ┌───▶[ S_A ]── σ = S_A(M′) ──┐          σ ┌───▶[ P_A ]──┐
     │                             ▼            │              ▼
  M′ ┴──────────────────────── (M′, σ) ─────────┴── M′ ────▶[ =? ]──▶ chấp nhận
                          kênh truyền thông
```

- Alice tính **chữ ký số** (digital signature) σ cho thông điệp M′ bằng khóa bí mật S_A theo công thức σ = S_A(M′).
- Alice gửi cặp thông điệp/chữ ký (M′, σ) cho Bob.
- Khi nhận (M′, σ), Bob kiểm tra nó xuất phát từ Alice bằng cách dùng khóa công khai của Alice để kiểm tra đẳng thức M′ = P_A(σ). (Có lẽ M′ chứa tên Alice, nên Bob biết dùng khóa công khai của ai.) Nếu đẳng thức đúng, Bob kết luận M′ thực sự do Alice ký. Nếu sai, Bob kết luận hoặc M′ hoặc σ bị hỏng do lỗi truyền, hoặc cặp (M′, σ) là một vụ giả mạo.

Vì chữ ký số xác thực cả danh tính người ký lẫn nội dung thông điệp, nó tương tự chữ ký tay ở cuối văn bản viết. Chữ ký số phải kiểm tra được bởi bất kỳ ai có khóa công khai của người ký. Một thông điệp đã ký có thể được một bên kiểm tra rồi chuyển cho bên khác, bên đó cũng kiểm tra được. Ví dụ, thông điệp có thể là séc điện tử từ Alice gửi Bob. Sau khi Bob kiểm tra chữ ký của Alice trên séc, anh đưa séc cho ngân hàng, ngân hàng cũng kiểm tra chữ ký rồi thực hiện chuyển tiền.

Thông điệp đã ký không nhất thiết được mã hóa; thông điệp có thể "để trần" và không được bảo vệ khỏi bị lộ. Ghép hai giao thức mã hóa và ký, có thể tạo thông điệp vừa được ký vừa được mã hóa: người ký trước hết gắn chữ ký số vào thông điệp rồi mã hóa cặp thông điệp/chữ ký bằng khóa công khai của người nhận. Người nhận giải mã bằng khóa bí mật của mình để có cả thông điệp gốc lẫn chữ ký, rồi kiểm tra chữ ký bằng khóa công khai của người ký. Quy trình tương ứng với giấy tờ là ký văn bản rồi niêm phong nó trong phong bì mà chỉ người nhận được mở.

#### Hệ mật mã RSA (The RSA cryptosystem)

Trong **hệ mật mã khóa công khai RSA** (RSA public-key cryptosystem), mỗi người tạo khóa công khai và bí mật theo thủ tục:

1. Chọn ngẫu nhiên hai số nguyên tố lớn p và q với p ≠ q. Các số nguyên tố p, q có thể dài, chẳng hạn, 1024 bit mỗi số.
2. Tính n = pq.
3. Chọn một số nguyên lẻ nhỏ e nguyên tố cùng nhau với φ(n), mà theo (31.20) bằng (p − 1)(q − 1).
4. Tính d là nghịch đảo nhân của e modulo φ(n). (Hệ quả 31.26 bảo đảm d tồn tại và xác định duy nhất. Có thể dùng kỹ thuật của Mục 31.4 để tính d khi biết e và φ(n).)
5. Công bố cặp P = (e, n) làm **khóa công khai RSA** của mình.
6. Giữ bí mật cặp S = (d, n) làm **khóa bí mật RSA** của mình.

Với hệ này, miền 𝒟 là tập ℤₙ. Để biến đổi thông điệp M theo khóa công khai P = (e, n), tính

```text
P(M) = Mᵉ mod n                                                      (31.37)
```

Để biến đổi bản mã C theo khóa bí mật S = (d, n), tính

```text
S(C) = Cᵈ mod n                                                      (31.38)
```

Các công thức này áp dụng cho cả mã hóa lẫn chữ ký. Để tạo chữ ký, người ký áp khóa bí mật của mình lên thông điệp cần ký thay vì lên bản mã. Để kiểm tra chữ ký, áp khóa công khai của người ký lên chữ ký thay vì lên thông điệp cần mã hóa.

Có thể cài đặt các phép toán khóa công khai và khóa bí mật bằng MODULAR-EXPONENTIATION của Mục 31.6. Để phân tích thời gian chạy, giả sử khóa công khai (e, n) và khóa bí mật (d, n) thỏa lg e = O(1), lg d ≤ β và lg n ≤ β. Khi đó áp khóa công khai cần O(1) phép nhân modulo và O(β²) phép toán bit. Áp khóa bí mật cần O(β) phép nhân modulo, tức O(β³) phép toán bit.

**Ví dụ chạy tay đầy đủ (người tổng hợp, dùng số của Exercise 31.7-1):** p = 11, q = 29.
- n = 319, φ(n) = 10 · 28 = 280.
- e = 3: gcd(3, 280) = 1 (280 = 93 · 3 + 1). Hợp lệ.
- d = 3⁻¹ mod 280: từ 280 = 93 · 3 + 1 suy ra 1 = 280 − 93 · 3, nên 3 · (−93) ≡ 1, d = −93 + 280 = 187. Kiểm tra: 3 · 187 = 561 = 2 · 280 + 1.
- Khóa công khai (3, 319), khóa bí mật (187, 319).
- Mã hóa M = 100: 100² = 10.000 = 31 · 319 + 111; 111 · 100 = 11.100 = 34 · 319 + 254. Vậy C = 254.
- Giải mã: 254¹⁸⁷ mod 319 = 100 (người tổng hợp đã kiểm tra bằng máy tính; MODULAR-EXPONENTIATION với 187 = ⟨10111011⟩ nhị phân chạy 8 vòng, tức 8 lần bình phương — lần đầu là bình phương 1 — và 6 lần nhân thêm 254 ứng với 6 bit 1).

**Định lý 31.36 (Tính đúng của RSA — Correctness of RSA).** Các công thức RSA (31.37) và (31.38) định nghĩa hai phép biến đổi ngược nhau của ℤₙ thỏa (31.35) và (31.36).

*Chứng minh.* Từ (31.37) và (31.38), với mọi M ∈ ℤₙ:

```text
P(S(M)) = S(P(M)) = M^(ed)  (mod n)
```

Vì e và d là nghịch đảo nhân của nhau modulo φ(n) = (p − 1)(q − 1),

```text
ed = 1 + k(p − 1)(q − 1)
```

với số nguyên k nào đó. Khi đó, nếu M ≢ 0 (mod p):

```text
M^(ed) ≡ M (M^(p−1))^(k(q−1))            (mod p)
       ≡ M ((M mod p)^(p−1))^(k(q−1))    (mod p)
       ≡ M (1)^(k(q−1))                  (mod p)    (theo Định lý 31.31)
       ≡ M                               (mod p)
```

Đồng thời M^(ed) ≡ M (mod p) nếu M ≡ 0 (mod p) (hai vế cùng ≡ 0). Vậy M^(ed) ≡ M (mod p) với mọi M. Tương tự M^(ed) ≡ M (mod q) với mọi M. Do đó, theo Hệ quả 31.29 của định lý số dư Trung Hoa, M^(ed) ≡ M (mod n) với mọi M. ∎

Nhận xét của người tổng hợp: chứng minh cần tách riêng trường hợp M ≡ 0 (mod p) vì định lý Fermat chỉ áp dụng cho M ∈ ℤₚ*; nhờ vậy RSA đúng cả với những thông điệp (hiếm) không nguyên tố cùng nhau với n, dù định lý Euler a^φ(n) ≡ 1 không áp dụng cho chúng.

#### Độ an toàn và cách dùng thực tế

Độ an toàn của RSA phần lớn dựa trên độ khó của việc phân tích số nguyên lớn. Nếu đối thủ phân tích được modulus n trong một khóa công khai, đối thủ suy ra được khóa bí mật từ khóa công khai, dùng p và q y như người tạo khóa đã dùng (tính φ(n) = (p − 1)(q − 1) rồi d = e⁻¹ mod φ(n)). Vậy nếu phân tích số lớn là dễ thì phá RSA là dễ. Mệnh đề ngược — nếu phân tích số lớn là khó thì phá RSA là khó — chưa được chứng minh. Tuy nhiên sau hai thập kỷ nghiên cứu (lời sách; xem khối Lưu ý), chưa ai tìm ra cách phá RSA dễ hơn việc phân tích modulus n. Và như Mục 31.9 sẽ cho thấy, phân tích số nguyên lớn khó một cách đáng ngạc nhiên. Bằng cách chọn ngẫu nhiên và nhân hai số nguyên tố 1024 bit, có thể tạo khóa công khai không thể "phá" trong một lượng thời gian khả thi với công nghệ hiện tại. Nếu không có đột phá cơ bản trong thiết kế thuật toán số học, và khi cài đặt cẩn thận theo các chuẩn khuyến nghị, RSA có thể cho độ an toàn cao trong ứng dụng.

Để đạt an toàn với RSA, cần dùng số nguyên khá dài — hàng trăm bit hoặc hơn một nghìn bit — để chống lại tiến bộ có thể có của kỹ thuật phân tích thừa số. Tại thời điểm viết sách (2009), modulus RSA thường dài 768 tới 2048 bit. Để tạo modulus cỡ đó, phải tìm được số nguyên tố lớn một cách hiệu quả; Mục 31.8 giải quyết việc này.

**Chế độ lai (hybrid, key-management mode).** Để hiệu quả, RSA thường được dùng ở chế độ "lai" với các hệ mật mã nhanh không dùng khóa công khai — ở các hệ này khóa mã hóa và khóa giải mã giống hệt nhau. Nếu Alice muốn gửi Bob một thông điệp dài M một cách bí mật, cô chọn một khóa ngẫu nhiên K cho hệ mã nhanh và mã hóa M bằng K, được bản mã C. Ở đây C dài bằng M, còn K khá ngắn. Rồi cô mã hóa K bằng khóa công khai RSA của Bob. Vì K ngắn, tính P_B(K) nhanh (nhanh hơn nhiều so với tính P_B(M)). Cô gửi (C, P_B(K)) cho Bob; Bob giải mã P_B(K) để có K rồi dùng K giải mã C, được M.

**Chữ ký với hàm băm.** Cách lai tương tự giúp tạo chữ ký số hiệu quả. Cách này ghép RSA với một **hàm băm chống va chạm** (collision-resistant hash function) công khai h — hàm dễ tính nhưng về mặt tính toán không thể tìm hai thông điệp M, M′ với h(M) = h(M′). Giá trị h(M) là một "dấu vân tay" ngắn (chẳng hạn 256 bit) của thông điệp M. Nếu Alice muốn ký M, cô áp h lên M để có dấu vân tay h(M), rồi mã hóa nó bằng khóa bí mật. Cô gửi (M, S_A(h(M))) cho Bob làm bản đã ký của M. Bob kiểm tra chữ ký bằng cách tính h(M) và kiểm tra P_A áp lên S_A(h(M)) nhận được có bằng h(M) không. Vì không ai tạo được hai thông điệp cùng dấu vân tay, về mặt tính toán không thể sửa một thông điệp đã ký mà giữ chữ ký còn hợp lệ.

**Chứng chỉ (certificates).** Cuối cùng, việc dùng chứng chỉ giúp phân phối khóa công khai dễ hơn nhiều. Ví dụ, giả sử có một "cơ quan đáng tin cậy" T mà khóa công khai ai cũng biết. Alice có thể nhận từ T một thông điệp đã ký (chứng chỉ của cô) nói rằng "khóa công khai của Alice là P_A". Chứng chỉ này "tự xác thực" vì ai cũng biết P_T. Alice có thể gửi kèm chứng chỉ trong các thông điệp đã ký của mình, để người nhận có ngay khóa công khai của Alice mà kiểm tra chữ ký. Vì khóa của cô đã được T ký, người nhận biết khóa đó đúng là của Alice.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: mọi kết nối HTTPS dùng đúng ba ý ở cuối mục này — chứng chỉ do cơ quan cấp chứng chỉ (CA) ký, chữ ký trên giá trị băm (SHA-256), và chế độ lai (khóa công khai chỉ dùng để thỏa thuận một khóa đối xứng, dữ liệu thật được mã hóa bằng AES hoặc ChaCha20). Độ dài khóa RSA khuyến nghị ngày nay tối thiểu 2048 bit; 768 bit (mức thấp nhất sách nêu cho năm 2009) đã bị phân tích công khai từ năm 2009. Trao đổi khóa trong TLS 1.3 không còn dùng RSA mà dùng Diffie–Hellman trên đường cong elliptic; RSA vẫn phổ biến cho chữ ký trong chứng chỉ.

### 9. ★ Kiểm tra tính nguyên tố (31.8 Primality testing, trang 965–975)

Mục này xét bài toán tìm số nguyên tố lớn. Sách bắt đầu bằng mật độ số nguyên tố, tiếp theo xét một cách thử nguyên tố hợp lý nhưng chưa hoàn chỉnh, rồi trình bày phép thử nguyên tố ngẫu nhiên hiệu quả của Miller và Rabin.

#### Mật độ số nguyên tố (The density of prime numbers)

Nhiều ứng dụng, như mật mã, cần tìm số nguyên tố lớn "ngẫu nhiên". May mắn là số nguyên tố lớn không quá hiếm, nên khả thi việc thử các số nguyên ngẫu nhiên cỡ thích hợp cho tới khi gặp số nguyên tố. **Hàm phân bố số nguyên tố** (prime distribution function) π(n) cho số các số nguyên tố nhỏ hơn hoặc bằng n. Ví dụ π(10) = 4, vì có 4 số nguyên tố ≤ 10 là 2, 3, 5, 7. Định lý số nguyên tố cho xấp xỉ hữu ích của π(n).

**Định lý 31.37 (Định lý số nguyên tố — Prime number theorem).**

```text
lim_{n→∞}  π(n) / (n / ln n) = 1
```

Xấp xỉ n/ln n cho ước lượng khá chính xác của π(n) ngay cả với n nhỏ. Ví dụ, nó lệch chưa tới 6% tại n = 10⁹, khi π(n) = 50.847.534 còn n/ln n ≈ 48.254.942 (lệch khoảng 5,1% — người tổng hợp tính). (Với nhà lý thuyết số, 10⁹ là số nhỏ.)

Có thể coi quá trình chọn ngẫu nhiên một số n và xác định nó có nguyên tố không là một phép thử Bernoulli (Mục C.4). Theo định lý số nguyên tố, xác suất thành công — tức xác suất n nguyên tố — xấp xỉ 1/ln n. Phân phối hình học cho biết cần bao nhiêu lần thử để có một thành công, và theo (C.32), số lần thử kỳ vọng xấp xỉ ln n. Vậy kỳ vọng phải xét khoảng ln n số nguyên chọn ngẫu nhiên gần n để tìm được một số nguyên tố cùng độ dài với n. Ví dụ, tìm một số nguyên tố 1024 bit cần thử khoảng ln 2¹⁰²⁴ ≈ 710 số 1024 bit chọn ngẫu nhiên (1024 · ln 2 ≈ 709,8). (Tất nhiên có thể giảm một nửa con số này bằng cách chỉ chọn số lẻ.)

Phần còn lại của mục xét bài toán xác định một số nguyên lẻ lớn n có phải số nguyên tố hay không. Để tiện ký hiệu, giả sử n có phân tích thừa số nguyên tố

```text
n = p₁^e₁ p₂^e₂ ⋯ pᵣ^eᵣ                                              (31.39)
```

với r ≥ 1, p₁, p₂, …, pᵣ là các thừa số nguyên tố của n, và e₁, e₂, …, eᵣ là số nguyên dương. Số n là nguyên tố khi và chỉ khi r = 1 và e₁ = 1.

**Chia thử.** Một cách đơn giản để thử nguyên tố là **chia thử** (trial division): thử chia n cho mỗi số nguyên 2, 3, …, ⌊√n⌋. (Lại có thể bỏ qua các số chẵn lớn hơn 2.) Dễ thấy n nguyên tố khi và chỉ khi không ước thử nào chia hết n. Giả sử mỗi phép chia thử tốn thời gian hằng số, thời gian xấu nhất là Θ(√n), là hàm mũ theo độ dài của n. (Nhớ rằng nếu n được mã hóa nhị phân bằng β bit thì β = ⌈lg(n + 1)⌉, nên √n = Θ(2^(β/2)).) Vậy chia thử chỉ tốt khi n rất nhỏ hoặc tình cờ có thừa số nguyên tố nhỏ. Khi hiệu quả, chia thử có lợi thế là không chỉ xác định n nguyên tố hay hợp số mà còn tìm được một thừa số nguyên tố của n nếu n là hợp số.

Mục này chỉ quan tâm việc xác định n có nguyên tố không; nếu n là hợp số, không cần tìm phân tích thừa số của nó. Như Mục 31.9 sẽ cho thấy, tính phân tích thừa số nguyên tố của một số tốn kém về mặt tính toán. Có lẽ đáng ngạc nhiên là xác định một số có nguyên tố hay không lại dễ hơn nhiều so với tìm phân tích thừa số của nó khi nó không nguyên tố.

#### Thử giả nguyên tố (Pseudoprimality testing)

Giờ xét một phương pháp thử nguyên tố "gần như đúng", và thực ra đủ tốt cho nhiều ứng dụng thực tế. Sau đó sách trình bày cải tiến loại bỏ khiếm khuyết nhỏ của nó. Gọi ℤₙ⁺ là các phần tử khác 0 của ℤₙ:

```text
ℤₙ⁺ = {1, 2, …, n − 1}
```

Nếu n nguyên tố thì ℤₙ⁺ = ℤₙ*.

Ta nói n là **giả nguyên tố cơ số a** (base-a pseudoprime) nếu n là hợp số và

```text
a^(n−1) ≡ 1 (mod n)                                                  (31.40)
```

Định lý Fermat (31.31) cho thấy nếu n nguyên tố thì n thỏa (31.40) với mọi a ∈ ℤₙ⁺. Do đó nếu tìm được bất kỳ a ∈ ℤₙ⁺ nào mà n **không** thỏa (31.40), thì n chắc chắn là hợp số. Đáng ngạc nhiên, mệnh đề đảo **gần như** đúng, nên tiêu chuẩn này gần như là phép thử nguyên tố hoàn hảo. Ta kiểm tra n có thỏa (31.40) với a = 2 không. Nếu không, tuyên bố n là hợp số bằng cách trả về COMPOSITE. Ngược lại, trả về PRIME, đoán rằng n nguyên tố (trong khi thực ra ta chỉ biết n hoặc là nguyên tố hoặc là giả nguyên tố cơ số 2).

Thủ tục sau "giả vờ" theo cách đó là đang kiểm tra tính nguyên tố của n. Nó dùng MODULAR-EXPONENTIATION của Mục 31.6. Giả sử đầu vào n là số nguyên lẻ lớn hơn 2.

```text
PSEUDOPRIME(n)
1  if MODULAR-EXPONENTIATION(2, n − 1, n) ≢ 1 (mod n)
2      return COMPOSITE          // definitely  (chắc chắn)
3  else return PRIME             // we hope!    (hy vọng vậy!)
```

Thủ tục này có thể sai, nhưng chỉ một kiểu. Nếu nó nói n là hợp số thì luôn đúng. Nếu nó nói n nguyên tố, nó chỉ sai khi n là giả nguyên tố cơ số 2.

Thủ tục sai thường xuyên đến mức nào? Hiếm một cách đáng ngạc nhiên. Chỉ có 22 giá trị n nhỏ hơn 10.000 mà nó sai; bốn giá trị đầu là 341, 561, 645, 1105. Sách không chứng minh, nhưng xác suất chương trình sai trên một số β-bit chọn ngẫu nhiên tiến về 0 khi β → ∞. Dùng các ước lượng chính xác hơn của Pomerance về số giả nguyên tố cơ số 2 cỡ cho trước, có thể ước lượng một số 512 bit chọn ngẫu nhiên được thủ tục trên gọi là nguyên tố có ít hơn một cơ hội trong 10²⁰ là giả nguyên tố cơ số 2, và một số 1024 bit chọn ngẫu nhiên được gọi là nguyên tố có ít hơn một cơ hội trong 10⁴¹. Vậy nếu chỉ cần tìm một số nguyên tố lớn cho ứng dụng nào đó, trên thực tế hầu như không bao giờ sai khi chọn ngẫu nhiên các số lớn cho tới khi một số làm PSEUDOPRIME trả về PRIME. Nhưng khi các số cần thử **không** được chọn ngẫu nhiên, cần cách thử tốt hơn. Như sẽ thấy, thêm chút khéo léo và chút ngẫu nhiên sẽ cho một thủ tục thử nguyên tố chạy tốt trên mọi đầu vào.

Kiểm tra (người tổng hợp): 341 = 11 · 31; 2¹⁰ = 1024 = 3 · 341 + 1 ≡ 1 (mod 341), nên 2³⁴⁰ = (2¹⁰)³⁴ ≡ 1 — 341 là giả nguyên tố cơ số 2. Nhưng 3³⁴⁰ mod 341 = 56 ≠ 1, nên thử thêm cơ số 3 bắt được 341.

**Số Carmichael.** Tiếc là không thể loại hết lỗi chỉ bằng cách kiểm tra (31.40) với một cơ số thứ hai, chẳng hạn a = 3, vì tồn tại các hợp số n, gọi là **số Carmichael** (Carmichael numbers), thỏa (31.40) với **mọi** a ∈ ℤₙ*. (Lưu ý (31.40) không đúng khi gcd(a, n) > 1 — tức khi a ∉ ℤₙ* — nhưng hy vọng chứng minh n là hợp số bằng cách tìm một a như vậy có thể khó nếu n chỉ có thừa số nguyên tố lớn.) Ba số Carmichael đầu tiên là 561, 1105, 1729. Số Carmichael cực kỳ hiếm; ví dụ chỉ có 255 số nhỏ hơn 100.000.000. Exercise 31.8-2 giúp giải thích vì sao chúng hiếm. Tiếp theo sách chỉ cách cải tiến phép thử để không bị số Carmichael đánh lừa.

#### Phép thử nguyên tố ngẫu nhiên Miller-Rabin (The Miller-Rabin randomized primality test)

Phép thử Miller-Rabin khắc phục vấn đề của PSEUDOPRIME bằng hai sửa đổi:
- Thử vài cơ số a chọn ngẫu nhiên thay vì chỉ một cơ số.
- Trong khi tính mỗi lũy thừa modulo, tìm căn bậc hai không tầm thường của 1 modulo n trong loạt bình phương cuối cùng. Nếu tìm thấy, dừng và trả về COMPOSITE. Hệ quả 31.35 ở Mục 31.6 biện minh cho cách phát hiện hợp số này.

Đầu vào n > 2 là số lẻ cần thử, s là số cơ số chọn ngẫu nhiên từ ℤₙ⁺ sẽ thử. Mã dùng bộ sinh số ngẫu nhiên RANDOM (Chương 5): RANDOM(1, n − 1) trả về số nguyên ngẫu nhiên a với 1 ≤ a ≤ n − 1. Mã dùng thủ tục phụ WITNESS sao cho WITNESS(a, n) là TRUE khi và chỉ khi a là một "**bằng chứng**" (witness) cho việc n là hợp số — tức là dùng a có thể chứng minh (theo cách sẽ thấy) rằng n là hợp số. Phép thử WITNESS(a, n) là mở rộng, nhưng hiệu quả hơn, của phép thử a^(n−1) ≢ 1 (mod n) làm nền (với a = 2) cho PSEUDOPRIME.

Viết n − 1 = 2ᵗu với t ≥ 1 và u lẻ; tức biểu diễn nhị phân của n − 1 là biểu diễn nhị phân của số lẻ u theo sau đúng t chữ số 0. Do đó a^(n−1) ≡ (aᵘ)^(2ᵗ) (mod n), nên có thể tính a^(n−1) mod n bằng cách trước hết tính aᵘ mod n rồi bình phương kết quả t lần liên tiếp.

```text
WITNESS(a, n)
1  let t and u be such that t ≥ 1, u is odd, and n − 1 = 2ᵗu
2  x₀ = MODULAR-EXPONENTIATION(a, u, n)
3  for i = 1 to t
4      xᵢ = xᵢ₋₁² mod n
5      if xᵢ == 1 and xᵢ₋₁ ≠ 1 and xᵢ₋₁ ≠ n − 1
6          return TRUE
7  if xₜ ≠ 1
8      return TRUE
9  return FALSE
```

(Dòng 1: "chọn t và u sao cho t ≥ 1, u lẻ, và n − 1 = 2ᵗu".) WITNESS tính a^(n−1) mod n bằng cách trước hết tính x₀ = aᵘ mod n ở dòng 2 rồi bình phương t lần liên tiếp trong vòng for dòng 3–6. Quy nạp theo i, dãy x₀, x₁, …, xₜ thỏa xᵢ ≡ a^(2ⁱu) (mod n) với i = 0, 1, …, t, nên đặc biệt xₜ ≡ a^(n−1) (mod n). Tuy nhiên sau mỗi bước bình phương ở dòng 4, vòng lặp có thể kết thúc sớm nếu dòng 5–6 phát hiện vừa tìm được một căn bậc hai không tầm thường của 1. Khi đó thuật toán dừng và trả về TRUE. Dòng 7–8 trả về TRUE nếu giá trị xₜ ≡ a^(n−1) (mod n) khác 1, giống như PSEUDOPRIME trả về COMPOSITE trong trường hợp này. Dòng 9 trả về FALSE nếu chưa trả về TRUE ở dòng 6 hoặc 8.

**Nếu WITNESS(a, n) trả về TRUE thì có thể dựng chứng minh n là hợp số, dùng a làm bằng chứng:**
- Nếu WITNESS trả về TRUE ở dòng 8, nó đã phát hiện xₜ = a^(n−1) mod n ≠ 1. Nhưng nếu n nguyên tố, định lý Fermat cho a^(n−1) ≡ 1 (mod n) với mọi a ∈ ℤₙ⁺. Vậy n không thể nguyên tố, và đẳng thức a^(n−1) mod n ≠ 1 chứng minh điều đó.
- Nếu WITNESS trả về TRUE ở dòng 6, nó đã phát hiện xᵢ₋₁ là căn bậc hai không tầm thường của 1 modulo n, vì xᵢ₋₁ ≢ ±1 (mod n) mà xᵢ ≡ xᵢ₋₁² ≡ 1 (mod n). Hệ quả 31.35 nói chỉ khi n là hợp số mới có căn bậc hai không tầm thường của 1 modulo n, nên việc chỉ ra xᵢ₋₁ là căn như vậy chứng minh n là hợp số.

Như vậy WITNESS đúng: nếu WITNESS(a, n) trả về TRUE thì n chắc chắn là hợp số, và bằng chứng a cùng lý do trả về TRUE (từ dòng 6 hay dòng 8) cho một chứng minh n là hợp số.

**Mô tả khác qua dãy X.** Mô tả hành vi của WITNESS theo dãy X = ⟨x₀, x₁, …, xₜ⟩ sẽ hữu ích khi phân tích hiệu quả. Lưu ý nếu xᵢ = 1 với 0 ≤ i < t nào đó, WITNESS có thể không tính phần còn lại của dãy; nhưng nếu có tính thì mọi giá trị xᵢ₊₁, …, xₜ đều bằng 1, và ta coi các vị trí đó trong X đều là 1. Có bốn trường hợp:

1. X = ⟨…, d⟩ với d ≠ 1: dãy X không kết thúc bằng 1. Trả về TRUE ở dòng 8; a là bằng chứng n là hợp số (theo định lý Fermat).
2. X = ⟨1, 1, …, 1⟩: dãy toàn số 1. Trả về FALSE; a không phải bằng chứng.
3. X = ⟨…, −1, 1, …, 1⟩: dãy kết thúc bằng 1, và phần tử khác 1 cuối cùng bằng −1. Trả về FALSE; a không phải bằng chứng.
4. X = ⟨…, d, 1, …, 1⟩ với d ≠ ±1: dãy kết thúc bằng 1, nhưng phần tử khác 1 cuối cùng không phải −1. Trả về TRUE ở dòng 6; a là bằng chứng, vì d là căn bậc hai không tầm thường của 1.

Giờ xét phép thử Miller-Rabin dựa trên WITNESS. Lại giả sử n là số nguyên lẻ lớn hơn 2.

```text
MILLER-RABIN(n, s)
1  for j = 1 to s
2      a = RANDOM(1, n − 1)
3      if WITNESS(a, n)
4          return COMPOSITE     // definitely   (chắc chắn)
5  return PRIME                 // almost surely (gần như chắc chắn)
```

Thủ tục MILLER-RABIN là một cuộc tìm kiếm xác suất cho một chứng minh rằng n là hợp số. Vòng lặp chính (bắt đầu ở dòng 1) chọn tới s giá trị a ngẫu nhiên từ ℤₙ⁺ (dòng 2). Nếu một trong các a đã chọn là bằng chứng, MILLER-RABIN trả về COMPOSITE ở dòng 4. Kết quả này luôn đúng, nhờ tính đúng của WITNESS. Nếu MILLER-RABIN không tìm được bằng chứng nào sau s lần thử, thủ tục giả định đó là vì không có bằng chứng nào, nên giả định n nguyên tố. Kết quả này nhiều khả năng đúng nếu s đủ lớn, nhưng vẫn còn một cơ hội rất nhỏ là thủ tục xui khi chọn các a, và bằng chứng có tồn tại dù chưa tìm thấy cái nào.

**Ví dụ của sách:** n = 561 (số Carmichael), n − 1 = 560 = 2⁴ · 35, t = 4, u = 35. Nếu thủ tục chọn a = 7, bảng MODULAR-EXPONENTIATION(7, 560, 561) đã chép ở Mục 7 phía trên (Hình 31.4 của sách) cho thấy WITNESS tính x₀ ≡ a³⁵ ≡ 241 (mod 561) và do đó dãy X = ⟨241, 298, 166, 67, 1⟩. Vậy WITNESS phát hiện một căn bậc hai không tầm thường của 1 ở bước bình phương cuối cùng, vì a²⁸⁰ ≡ 67 (mod n) và a⁵⁶⁰ ≡ 1 (mod n). Do đó a = 7 là bằng chứng 561 là hợp số, WITNESS(7, n) trả về TRUE, và MILLER-RABIN trả về COMPOSITE. (Đây là trường hợp 4 của dãy X với d = 67. Người tổng hợp lưu ý: PSEUDOPRIME với cơ số 7 sẽ bị lừa vì 7⁵⁶⁰ ≡ 1; chính phép kiểm tra căn bậc hai đã bắt được 561. Và gcd(67 − 1, 561) = gcd(66, 561) = 33, gcd(68, 561) = 17 — căn không tầm thường còn lộ thừa số.)

Ví dụ thêm (người tổng hợp), n = 13 nguyên tố, a = 5: n − 1 = 12 = 2² · 3, t = 2, u = 3. x₀ = 5³ = 125 ≡ 8 (mod 13); x₁ = 64 ≡ 12 ≡ −1; x₂ = 1. Dãy X = ⟨8, −1, 1⟩ là trường hợp 3: không phải bằng chứng, đúng vì 13 nguyên tố.

Nếu n là số β-bit, MILLER-RABIN cần O(sβ) phép toán số học và O(sβ³) phép toán bit, vì về tiệm cận nó không làm nhiều hơn s lần lũy thừa modulo.

#### Tỉ lệ sai của phép thử Miller-Rabin (Error rate of the Miller-Rabin primality test)

Nếu MILLER-RABIN trả về PRIME thì có một khả năng rất nhỏ là nó sai. Khác PSEUDOPRIME, khả năng sai không phụ thuộc n; không có đầu vào xấu cho thủ tục này. Thay vào đó, nó phụ thuộc cỡ của s và "vận may khi bốc" các cơ số a. Hơn nữa, vì mỗi lần thử chặt hơn việc kiểm tra đơn thuần (31.40), về nguyên tắc chung có thể kỳ vọng tỉ lệ sai nhỏ với số n chọn ngẫu nhiên. Định lý sau cho lập luận chính xác hơn.

**Định lý 31.38.** Nếu n là hợp số lẻ thì số bằng chứng cho việc n là hợp số ít nhất là (n − 1)/2.

*Chứng minh.* Chứng minh rằng số "không bằng chứng" (nonwitness) nhiều nhất là (n − 1)/2, suy ra định lý.

Trước hết, mọi không bằng chứng phải thuộc ℤₙ*. Vì sao? Xét một không bằng chứng a bất kỳ. Nó phải thỏa a^(n−1) ≡ 1 (mod n), tương đương a · a^(n−2) ≡ 1 (mod n). Vậy phương trình ax ≡ 1 (mod n) có nghiệm, là a^(n−2). Theo Hệ quả 31.21, gcd(a, n) | 1, kéo theo gcd(a, n) = 1. Vậy a ∈ ℤₙ*; mọi không bằng chứng thuộc ℤₙ*.

Để hoàn tất, ta chứng minh không chỉ mọi không bằng chứng nằm trong ℤₙ*, mà chúng nằm cả trong một **nhóm con thực sự** B của ℤₙ* (B là nhóm con của ℤₙ* nhưng khác ℤₙ*). Theo Hệ quả 31.16, |B| ≤ |ℤₙ*|/2. Vì |ℤₙ*| ≤ n − 1, được |B| ≤ (n − 1)/2. Vậy số không bằng chứng nhiều nhất là (n − 1)/2, nên số bằng chứng ít nhất là (n − 1)/2.

Giờ chỉ cách tìm nhóm con thực sự B của ℤₙ* chứa mọi không bằng chứng. Chia hai trường hợp.

*Trường hợp 1:* tồn tại x ∈ ℤₙ* sao cho

```text
x^(n−1) ≢ 1 (mod n)
```

Nói cách khác, n không phải số Carmichael. Vì như đã nói số Carmichael cực kỳ hiếm, trường hợp 1 là trường hợp chính xảy ra "trong thực tế" (ví dụ khi n được chọn ngẫu nhiên để thử). Đặt B = {b ∈ ℤₙ* : b^(n−1) ≡ 1 (mod n)}. Rõ ràng B khác rỗng vì 1 ∈ B. Vì B đóng với phép nhân modulo n (nếu a^(n−1) ≡ 1 và b^(n−1) ≡ 1 thì (ab)^(n−1) ≡ 1), B là nhóm con của ℤₙ* theo Định lý 31.14. Mọi không bằng chứng thuộc B, vì không bằng chứng a thỏa a^(n−1) ≡ 1 (mod n). Vì x ∈ ℤₙ* − B, B là nhóm con thực sự của ℤₙ*.

*Trường hợp 2:* với mọi x ∈ ℤₙ*,

```text
x^(n−1) ≡ 1 (mod n)                                                  (31.41)
```

Nói cách khác, n là số Carmichael. Trường hợp này cực kỳ hiếm trong thực tế. Tuy vậy, phép thử Miller-Rabin (khác phép thử giả nguyên tố) xác định hiệu quả được số Carmichael là hợp số, như sau.

Trong trường hợp này, n không thể là lũy thừa của một số nguyên tố. Để thấy vì sao, giả sử ngược lại n = pᵉ với p nguyên tố và e > 1. Suy ra mâu thuẫn như sau. Vì giả sử n lẻ, p cũng lẻ. Định lý 31.32 cho ℤₙ* là nhóm cyclic: có phần tử sinh g với ordₙ(g) = |ℤₙ*| = φ(n) = pᵉ(1 − 1/p) = (p − 1)p^(e−1). (Công thức φ(n) lấy từ (31.20).) Theo (31.41), g^(n−1) ≡ 1 (mod n). Rồi định lý logarit rời rạc (31.33, lấy y = 0) cho n − 1 ≡ 0 (mod φ(n)), tức

```text
(p − 1)p^(e−1) | pᵉ − 1
```

Đây là mâu thuẫn khi e > 1, vì (p − 1)p^(e−1) chia hết cho số nguyên tố p còn pᵉ − 1 thì không. Vậy n không phải lũy thừa số nguyên tố.

Vì hợp số lẻ n không phải lũy thừa số nguyên tố, ta tách nó thành tích n₁n₂, với n₁, n₂ là các số lẻ lớn hơn 1 nguyên tố cùng nhau. (Có thể có nhiều cách tách, chọn cách nào cũng được. Ví dụ nếu n = p₁^e₁ p₂^e₂ ⋯ pᵣ^eᵣ thì có thể chọn n₁ = p₁^e₁ và n₂ = p₂^e₂ p₃^e₃ ⋯ pᵣ^eᵣ.)

Nhớ rằng t và u được định nghĩa để n − 1 = 2ᵗu, t ≥ 1, u lẻ, và với đầu vào a, WITNESS tính dãy

```text
X = ⟨aᵘ, a^(2u), a^(2²u), …, a^(2ᵗu)⟩
```

(mọi phép tính modulo n).

Gọi một cặp số nguyên (ν, j) là **chấp nhận được** (acceptable) nếu ν ∈ ℤₙ*, j ∈ {0, 1, …, t}, và

```text
ν^(2ʲu) ≡ −1 (mod n)
```

Cặp chấp nhận được chắc chắn tồn tại vì u lẻ: có thể chọn ν = n − 1 và j = 0, nên (n − 1, 0) là cặp chấp nhận được ((−1)ᵘ = −1 vì u lẻ). Giờ chọn j **lớn nhất có thể** sao cho tồn tại cặp chấp nhận được (ν, j), và cố định ν để (ν, j) là cặp chấp nhận được. Đặt

```text
B = { x ∈ ℤₙ* : x^(2ʲu) ≡ ±1 (mod n) }
```

Vì B đóng với phép nhân modulo n, nó là nhóm con của ℤₙ*. Theo Định lý 31.15, |B| chia hết |ℤₙ*|. Mọi không bằng chứng phải thuộc B, vì dãy X của một không bằng chứng hoặc toàn số 1, hoặc chứa −1 không muộn hơn vị trí thứ j, do tính lớn nhất của j. (Nếu (a, j′) chấp nhận được với a là không bằng chứng, phải có j′ ≤ j theo cách chọn j.) — Giải thích thêm của người tổng hợp: nếu X toàn 1 thì a^(2ʲu) = 1; nếu X có −1 ở vị trí j′ ≤ j thì a^(2ʲu) là −1 (khi j′ = j) hoặc 1 (khi j′ < j); cả hai trường hợp a ∈ B.

Giờ dùng sự tồn tại của ν để chứng minh có w ∈ ℤₙ* − B, do đó B là nhóm con thực sự của ℤₙ*. Vì ν^(2ʲu) ≡ −1 (mod n), theo Hệ quả 31.29 của định lý số dư Trung Hoa, ν^(2ʲu) ≡ −1 (mod n₁). Theo Hệ quả 31.28, tồn tại w đồng thời thỏa

```text
w ≡ ν (mod n₁)
w ≡ 1 (mod n₂)
```

Do đó

```text
w^(2ʲu) ≡ −1 (mod n₁)
w^(2ʲu) ≡  1 (mod n₂)
```

Theo Hệ quả 31.29, w^(2ʲu) ≢ 1 (mod n₁) kéo theo w^(2ʲu) ≢ 1 (mod n), và w^(2ʲu) ≢ −1 (mod n₂) kéo theo w^(2ʲu) ≢ −1 (mod n). Vậy w^(2ʲu) ≢ ±1 (mod n), nên w ∉ B. (Ở đây dùng n₁, n₂ lẻ và > 1 nên 1 ≢ −1 theo từng modulus — chú thích của người tổng hợp.)

Còn phải chứng minh w ∈ ℤₙ*, làm bằng cách xét riêng modulo n₁ và modulo n₂. Modulo n₁: vì ν ∈ ℤₙ*, gcd(ν, n) = 1, nên cũng có gcd(ν, n₁) = 1 — nếu ν không có ước chung với n thì chắc chắn không có ước chung với n₁. Vì w ≡ ν (mod n₁), gcd(w, n₁) = 1. Modulo n₂: w ≡ 1 (mod n₂) kéo theo gcd(w, n₂) = 1. Ghép lại bằng Định lý 31.6: gcd(w, n₁n₂) = gcd(w, n) = 1, tức w ∈ ℤₙ*.

Vậy w ∈ ℤₙ* − B, và trường hợp 2 kết thúc với kết luận B là nhóm con thực sự của ℤₙ*.

Trong cả hai trường hợp, số bằng chứng cho việc n là hợp số ít nhất là (n − 1)/2. ∎

**Định lý 31.39.** Với mọi số nguyên lẻ n > 2 và mọi số nguyên dương s, xác suất MILLER-RABIN(n, s) sai nhiều nhất là 2⁻ˢ.

*Chứng minh.* Theo Định lý 31.38, nếu n là hợp số thì mỗi lần thực hiện vòng for dòng 1–4 có xác suất ít nhất 1/2 tìm được một bằng chứng x cho việc n là hợp số. MILLER-RABIN chỉ sai nếu xui tới mức bỏ lỡ bằng chứng ở cả s lần lặp của vòng chính. Xác suất của chuỗi bỏ lỡ như vậy nhiều nhất là 2⁻ˢ. ∎

Nếu n nguyên tố, MILLER-RABIN luôn báo PRIME; nếu n là hợp số, khả năng MILLER-RABIN báo PRIME nhiều nhất là 2⁻ˢ.

**Diễn giải kết quả với n ngẫu nhiên — dùng định lý Bayes.** Khi áp MILLER-RABIN lên một số lớn chọn ngẫu nhiên n, cần xét thêm xác suất tiên nghiệm (prior) n là số nguyên tố để diễn giải đúng kết quả. Giả sử cố định độ dài β bit và chọn ngẫu nhiên một số n dài β bit để thử. Gọi A là sự kiện n nguyên tố. Theo định lý số nguyên tố (31.37), xác suất n nguyên tố xấp xỉ

```text
Pr{A} ≈ 1/ln n
      ≈ 1,443/β
```

(vì ln n ≈ β ln 2 ≈ 0,693β, và 1/0,693 ≈ 1,443). Gọi B là sự kiện MILLER-RABIN trả về PRIME. Ta có Pr{B̄ | A} = 0 (tương đương Pr{B | A} = 1) và Pr{B | Ā} ≤ 2⁻ˢ (tương đương Pr{B̄ | Ā} > 1 − 2⁻ˢ). (Ký hiệu B̄ là "không B", Ā là "không A".)

Vậy Pr{A | B} — xác suất n nguyên tố khi MILLER-RABIN đã trả về PRIME — bằng bao nhiêu? Theo dạng khác của định lý Bayes (công thức (C.18)):

```text
Pr{A | B} = Pr{A} Pr{B | A} / ( Pr{A} Pr{B | A} + Pr{Ā} Pr{B | Ā} )
          ≈ 1 / ( 1 + 2⁻ˢ (ln n − 1) )
```

(Giải thích bước xấp xỉ, của người tổng hợp: thay Pr{A} = 1/ln n, Pr{B | A} = 1, Pr{Ā} = 1 − 1/ln n, Pr{B | Ā} = 2⁻ˢ rồi nhân tử và mẫu với ln n: 1/(1 + (ln n − 1)2⁻ˢ).)

Xác suất này chưa vượt 1/2 cho tới khi s vượt lg(ln n − 1). Về trực giác, cần chừng ấy lần thử ban đầu chỉ để lòng tin có được từ việc không tìm thấy bằng chứng hợp số thắng được định kiến ban đầu nghiêng về việc n là hợp số. Với số β = 1024 bit, việc thử ban đầu này cần khoảng

```text
lg(ln n − 1) ≈ lg(β/1,443) ≈ 9
```

lần thử (lg 709 ≈ 9,47). Dù sao, chọn s = 50 sẽ đủ cho hầu như mọi ứng dụng tưởng tượng được.

Thực ra tình hình tốt hơn nhiều. Nếu đang tìm số nguyên tố lớn bằng cách áp MILLER-RABIN lên các số lẻ lớn chọn ngẫu nhiên, thì chọn s nhỏ (chẳng hạn 3) rất khó dẫn tới kết quả sai, dù sách không chứng minh ở đây. Lý do là với một hợp số lẻ chọn ngẫu nhiên n, số không bằng chứng kỳ vọng nhiều khả năng nhỏ hơn rất nhiều so với (n − 1)/2.

Tuy nhiên nếu n không được chọn ngẫu nhiên, điều tốt nhất chứng minh được là số không bằng chứng nhiều nhất là (n − 1)/4, dùng một phiên bản cải tiến của Định lý 31.38. Hơn nữa, có những số n mà số không bằng chứng đúng bằng (n − 1)/4.

Bảng số (người tổng hợp) cho Pr{A | B} ≈ 1/(1 + 2⁻ˢ · 708,8) với n 1024 bit:

| s | 2⁻ˢ · 708,8 | Pr{n nguyên tố \| báo PRIME} xấp xỉ |
|---|---|---|
| 1 | 354,4 | 0,0028 |
| 5 | 22,15 | 0,043 |
| 10 | 0,692 | 0,59 |
| 20 | 0,00068 | 0,9993 |
| 50 | 6,3 · 10⁻¹³ | 1 − 6,3 · 10⁻¹³ |

(Đây là cận bi quan dùng tỉ lệ sai 2⁻ˢ; với số chọn ngẫu nhiên tỉ lệ sai thật nhỏ hơn rất nhiều, như sách vừa nói.)

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: các thư viện mật mã (OpenSSL, BoringSSL) tạo khóa RSA đúng theo quy trình của mục này — sinh số lẻ ngẫu nhiên đủ dài, loại nhanh bằng chia thử cho vài trăm số nguyên tố nhỏ, rồi chạy Miller-Rabin vài chục vòng (số vòng chọn theo độ dài khóa). Hàm `BigInteger.isProbablePrime(certainty)` của Java và `mpz_probab_prime_p` của GMP cũng là Miller-Rabin (có kèm phép thử Lucas). Thuật toán tất định AKS (2002) nêu ở Ghi chú chương có ý nghĩa lý thuyết lớn nhưng chậm hơn nhiều nên hầu như không dùng trong thực tế.

### 10. ★ Phân tích số nguyên ra thừa số (31.9 Integer factorization, trang 975–980)

Giả sử có số nguyên n cần **phân tích thừa số** (factor), tức tách thành tích các số nguyên tố. Phép thử nguyên tố của mục trước có thể cho biết n là hợp số, nhưng không cho biết các thừa số nguyên tố của n. Phân tích một số lớn n có vẻ khó hơn nhiều so với chỉ xác định n là nguyên tố hay hợp số. Ngay cả với siêu máy tính ngày nay và thuật toán tốt nhất hiện có, chưa thể phân tích một số 1024 bit tùy ý trong thời gian khả thi.

#### Heuristic rho của Pollard (Pollard's rho heuristic)

Chia thử cho mọi số nguyên tới R chắc chắn phân tích hết mọi số tới R². Với cùng lượng việc, thủ tục POLLARD-RHO sau phân tích được mọi số tới R⁴ (trừ khi xui). Vì thủ tục chỉ là một heuristic, cả thời gian chạy lẫn sự thành công của nó đều không được bảo đảm, dù trong thực tế thủ tục rất hiệu quả. Một ưu điểm khác của POLLARD-RHO là chỉ dùng một số hằng ô nhớ. (Nếu muốn, có thể dễ dàng cài POLLARD-RHO trên máy tính bỏ túi lập trình được để tìm thừa số của các số nhỏ.)

```text
POLLARD-RHO(n)
 1  i = 1
 2  x₁ = RANDOM(0, n − 1)
 3  y = x₁
 4  k = 2
 5  while TRUE
 6      i = i + 1
 7      xᵢ = (xᵢ₋₁² − 1) mod n
 8      d = gcd(y − xᵢ, n)
 9      if d ≠ 1 and d ≠ n
10          print d
11      if i == k
12          y = xᵢ
13          k = 2k
```

Thủ tục hoạt động như sau. Dòng 1–2 khởi tạo i = 1 và x₁ là một giá trị chọn ngẫu nhiên trong ℤₙ. Vòng while bắt đầu ở dòng 5 lặp mãi mãi, tìm thừa số của n. Mỗi lần lặp, dòng 7 dùng truy hồi

```text
xᵢ = (xᵢ₋₁² − 1) mod n                                               (31.43)
```

để tạo giá trị kế tiếp xᵢ của dãy vô hạn

```text
x₁, x₂, x₃, x₄, …                                                    (31.44)
```

và dòng 6 tăng i tương ứng. Mã giả viết với biến có chỉ số xᵢ cho rõ, nhưng chương trình chạy y hệt nếu bỏ mọi chỉ số, vì chỉ cần giữ giá trị xᵢ gần nhất. Với sửa đổi đó, thủ tục chỉ dùng một số hằng ô nhớ.

Thỉnh thoảng chương trình lưu giá trị xᵢ vừa sinh vào biến y. Cụ thể, các giá trị được lưu là các giá trị có chỉ số là lũy thừa của 2:

```text
x₁, x₂, x₄, x₈, x₁₆, …
```

Dòng 3 lưu x₁, và dòng 12 lưu x_k mỗi khi i bằng k. Biến k được khởi tạo bằng 2 ở dòng 4, và dòng 13 nhân đôi nó mỗi khi dòng 12 cập nhật y. Vì vậy k luôn cho chỉ số của giá trị x_k kế tiếp sẽ được lưu vào y. (Sách viết "k đi theo dãy 1, 2, 4, 8, …"; chính xác hơn, biến k lần lượt là 2, 4, 8, …, còn dãy chỉ số được lưu là 1, 2, 4, 8, … — xem khối Lưu ý.)

Dòng 8–10 cố tìm một thừa số của n, dùng giá trị y đã lưu và giá trị hiện tại xᵢ. Cụ thể, dòng 8 tính ước chung lớn nhất d = gcd(y − xᵢ, n). Nếu dòng 9 thấy d là ước không tầm thường của n thì dòng 10 in d.

Thủ tục tìm thừa số này thoạt đầu có vẻ bí ẩn. Tuy nhiên, lưu ý POLLARD-RHO không bao giờ in đáp án sai: mọi số nó in ra đều là ước không tầm thường của n. Nhưng POLLARD-RHO có thể không in gì cả; không có bảo đảm nó sẽ in ước nào. Dù vậy, có lý do tốt để kỳ vọng POLLARD-RHO in một thừa số p của n sau Θ(√p) lần lặp while. Do đó nếu n là hợp số, có thể kỳ vọng thủ tục tìm đủ ước để phân tích hết n sau khoảng n^(1/4) lần cập nhật, vì mọi thừa số nguyên tố p của n trừ có thể thừa số lớn nhất đều nhỏ hơn √n.

**Dãy lặp lại và hình chữ ρ.** Phân tích hành vi của thủ tục bắt đầu bằng việc xét một dãy ngẫu nhiên modulo n mất bao lâu để lặp lại một giá trị. Vì ℤₙ hữu hạn, và mỗi giá trị trong dãy (31.44) chỉ phụ thuộc giá trị trước, dãy (31.44) rốt cuộc lặp lại. Khi tới xᵢ sao cho xᵢ = xⱼ với j < i nào đó, ta ở trong một chu trình, vì xᵢ₊₁ = xⱼ₊₁, xᵢ₊₂ = xⱼ₊₂, v.v. Tên "heuristic rho" là vì có thể vẽ dãy x₁, x₂, …, xⱼ₋₁ thành "đuôi" của chữ ρ và chu trình xⱼ, xⱼ₊₁, …, xᵢ thành "thân" của chữ ρ.

Xét câu hỏi dãy xᵢ mất bao lâu để lặp. Thông tin này chưa đúng là thứ cần, nhưng sách sẽ chỉ cách sửa lập luận. Để ước lượng, giả sử hàm

```text
fₙ(x) = (x² − 1) mod n
```

hành xử như một hàm "ngẫu nhiên". Tất nhiên nó không thật sự ngẫu nhiên, nhưng giả định này cho kết quả phù hợp với hành vi quan sát được của POLLARD-RHO. Khi đó có thể coi mỗi xᵢ được rút độc lập từ ℤₙ theo phân phối đều. Theo phân tích nghịch lý ngày sinh ở Mục 5.4.1, kỳ vọng Θ(√n) bước trước khi dãy vào chu trình.

**Sửa đổi cần thiết: nhìn dãy modulo một thừa số p.** Gọi p là thừa số không tầm thường của n sao cho gcd(p, n/p) = 1. Ví dụ nếu n có phân tích n = p₁^e₁ p₂^e₂ ⋯ pᵣ^eᵣ, có thể lấy p = p₁^e₁. (Nếu e₁ = 1 thì p chính là thừa số nguyên tố nhỏ nhất của n — một ví dụ tốt nên nhớ.)

Dãy ⟨xᵢ⟩ cảm sinh một dãy tương ứng ⟨x′ᵢ⟩ modulo p, với

```text
x′ᵢ = xᵢ mod p
```

với mọi i. Hơn nữa, vì fₙ chỉ dùng các phép toán số học (bình phương và trừ) modulo n, có thể tính x′ᵢ₊₁ từ x′ᵢ; cái nhìn "modulo p" của dãy là một phiên bản thu nhỏ của điều đang xảy ra modulo n:

```text
x′ᵢ₊₁ = xᵢ₊₁ mod p
      = fₙ(xᵢ) mod p
      = ((xᵢ² − 1) mod n) mod p
      = (xᵢ² − 1) mod p                 (theo Exercise 31.1-7)
      = ((xᵢ mod p)² − 1) mod p
      = ((x′ᵢ)² − 1) mod p
      = fₚ(x′ᵢ)
```

Vậy dù không tính tường minh dãy ⟨x′ᵢ⟩, dãy này được định nghĩa rõ và tuân theo cùng truy hồi như dãy ⟨xᵢ⟩.

Lập luận như trước, số bước kỳ vọng trước khi dãy ⟨x′ᵢ⟩ lặp lại là Θ(√p). Nếu p nhỏ so với n, dãy ⟨x′ᵢ⟩ có thể lặp nhanh hơn nhiều so với dãy ⟨xᵢ⟩. Thật vậy, dãy ⟨x′ᵢ⟩ lặp ngay khi hai phần tử của dãy ⟨xᵢ⟩ chỉ cần đồng dư modulo p, thay vì đồng dư modulo n.

Gọi t là chỉ số của giá trị lặp đầu tiên trong dãy ⟨x′ᵢ⟩, và u > 0 là độ dài chu trình được tạo ra. Tức t và u > 0 là các giá trị nhỏ nhất sao cho x′_{t+i} = x′_{t+u+i} với mọi i ≥ 0. Theo lập luận trên, giá trị kỳ vọng của t và u đều là Θ(√p). Lưu ý nếu x′_{t+i} = x′_{t+u+i} thì p | (x_{t+u+i} − x_{t+i}). Do đó gcd(x_{t+u+i} − x_{t+i}, n) > 1.

Vì vậy, một khi POLLARD-RHO đã lưu vào y một giá trị x_k với k ≥ t, thì y mod p luôn nằm trên chu trình modulo p. (Nếu một giá trị mới được lưu vào y, giá trị đó cũng nằm trên chu trình modulo p.) Rốt cuộc k được đặt bằng một giá trị lớn hơn u, và khi đó thủ tục đi trọn một vòng quanh chu trình modulo p mà không đổi y. Thủ tục khi đó phát hiện một thừa số của n khi xᵢ "đụng" giá trị y đã lưu, modulo p, tức khi xᵢ ≡ y (mod p).

Có lẽ thừa số tìm được là p, dù đôi khi có thể tìm được một bội của p. Vì giá trị kỳ vọng của cả t và u là Θ(√p), số bước kỳ vọng cần để tạo ra thừa số p là Θ(√p).

**Ví dụ của sách (Hình 31.7).** n = 1387 = 19 · 73, x₁ = 2, truy hồi xᵢ₊₁ = (xᵢ² − 1) mod 1387. Mô tả lại ba phần của hình bằng chữ:

(a) Modulo 1387. Dãy: x₁ = 2, x₂ = 3, x₃ = 8, x₄ = 63, x₅ = 1194, x₆ = 1186, x₇ = 177, rồi (các giá trị chưa tới khi thủ tục dừng, vẽ bằng mũi tên nhạt) 814, 996, 310, 396, 84, 120, 529, 1053, 595, 339, rồi quay về 1186. Như vậy đuôi là 2, 3, 8, 63, 1194 và chu trình là 1186 → 177 → 814 → 996 → 310 → 396 → 84 → 120 → 529 → 1053 → 595 → 339 → 1186 (dài 12). Các giá trị được tô đậm là các giá trị y mà POLLARD-RHO lưu: x₁ = 2, x₂ = 3, x₄ = 63. Mũi tên đậm là các bước lặp được thực hiện trước khi tìm ra thừa số 19. Thừa số 19 được phát hiện khi tới x₇ = 177, lúc tính gcd(63 − 177, 1387) = 19. Giá trị x đầu tiên sẽ bị lặp lại là 1186, nhưng thừa số 19 được tìm ra trước khi giá trị này lặp lại.

(b) Cùng truy hồi modulo 19. Mỗi giá trị xᵢ ở phần (a) đồng dư modulo 19 với giá trị x′ᵢ ở đây: x′₁ = 2, x′₂ = 3, x′₃ = 8, x′₄ = 6, x′₅ = 16, x′₆ = 8, x′₇ = 6, … Đuôi là 2, 3 và chu trình là 8 → 6 → 16 → 8 (dài 3). Ví dụ x₄ = 63 và x₇ = 177 đều đồng dư 6 modulo 19 (63 = 3 · 19 + 6; 177 = 9 · 19 + 6).

(c) Cùng truy hồi modulo 73. Mỗi giá trị xᵢ ở phần (a) đồng dư modulo 73 với giá trị x″ᵢ ở đây: 2, 3, 8, 63, 26, 18, 31, 11, 47, rồi về 18. Đuôi là 2, 3, 8, 63, 26 và chu trình 18 → 31 → 11 → 47 → 18 (dài 4).

Theo định lý số dư Trung Hoa, mỗi nút ở phần (a) ứng với một cặp nút, một từ phần (b) và một từ phần (c).

Chạy tay thủ tục (người tổng hợp, kiểm tra lại toàn bộ):

| i | xᵢ | y trước bước | y − xᵢ | gcd(y − xᵢ, 1387) | ghi chú |
|---|---|---|---|---|---|
| 1 | 2 | — | — | — | dòng 3: y = x₁ = 2, k = 2 |
| 2 | 3 | 2 | −1 | 1 | i = k: y = 3, k = 4 |
| 3 | 8 | 3 | −5 | 1 | |
| 4 | 63 | 3 | −60 | 1 | i = k: y = 63, k = 8 |
| 5 | 1194 | 63 | −1131 | 1 | |
| 6 | 1186 | 63 | −1123 | 1 | |
| 7 | 177 | 63 | −114 | **19** | in 19 (114 = 6 · 19) |

Lý giải bằng dãy modulo 19: y = x₄ ≡ 6 nằm trên chu trình 8 → 6 → 16 dài u = 3, và sau đúng 3 bước x₇ ≡ 6 lại đụng y modulo 19.

**Hai lý do thuật toán có thể không chạy như mong đợi.** Thứ nhất, phân tích thời gian chạy theo heuristic không chặt chẽ, và có thể chu trình giá trị modulo p dài hơn nhiều so với √p. Khi đó thuật toán vẫn đúng nhưng chậm hơn mong muốn nhiều. Trong thực tế vấn đề này có vẻ không đáng kể. Thứ hai, các ước của n mà thuật toán tạo ra có thể luôn là một trong hai thừa số tầm thường 1 hoặc n. Ví dụ, giả sử n = pq với p, q nguyên tố. Có thể xảy ra là giá trị t và u của p trùng với t và u của q, và do đó thừa số p luôn lộ ra trong cùng phép gcd làm lộ q. Vì cả hai thừa số lộ ra cùng lúc, thừa số tầm thường pq = n lộ ra, vô ích. Lại nữa, vấn đề này có vẻ không đáng kể trong thực tế. Nếu cần, có thể khởi động lại heuristic với truy hồi khác dạng xᵢ₊₁ = (xᵢ² − c) mod n. (Nên tránh c = 0 và c = 2 vì những lý do sách không đi vào, các giá trị khác đều được.)

Tất nhiên, phân tích này là heuristic chứ không chặt chẽ, vì truy hồi không thực sự "ngẫu nhiên". Dù vậy thủ tục chạy tốt trong thực tế, và có vẻ hiệu quả đúng như phân tích heuristic chỉ ra. Đây là phương pháp nên chọn để tìm các thừa số nguyên tố nhỏ của một số lớn. Để phân tích hết một hợp số β-bit n, chỉ cần tìm mọi thừa số nguyên tố nhỏ hơn ⌊n^(1/2)⌋, nên kỳ vọng POLLARD-RHO cần nhiều nhất n^(1/4) = 2^(β/4) phép toán số học và nhiều nhất n^(1/4)β² = 2^(β/4)β² phép toán bit. Khả năng của POLLARD-RHO tìm một thừa số nhỏ p của n với số phép toán số học kỳ vọng Θ(√p) thường là đặc điểm hấp dẫn nhất của nó.

So sánh số (người tổng hợp): với n ≈ 10²⁰ là tích của hai số nguyên tố cỡ 10¹⁰, chia thử cần khoảng 10¹⁰ phép chia, còn rho Pollard cần khoảng √(10¹⁰) = 10⁵ bước. Nhưng với n 1024 bit là tích hai số nguyên tố 512 bit, rho Pollard cần cỡ 2²⁵⁶ bước — hoàn toàn bất khả thi. Đó là lý do RSA chọn p và q cùng cỡ lớn.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: rho Pollard (thường ở biến thể Brent, đúng bản trong sách, kèm gom nhiều phép gcd như Exercise 31.9-4) là bước đầu tiêu chuẩn trong các công cụ phân tích thừa số như hàm `factorint` của SymPy hay `factor` của PARI/GP — tách nhanh các thừa số nhỏ trước khi chuyển sang phương pháp đường cong elliptic hoặc sàng trường số. Ý tưởng "đi trên một dãy giả ngẫu nhiên và chờ va chạm" cũng là nền của thuật toán rho Pollard cho logarit rời rạc, dùng để đánh giá độ an toàn của mật mã đường cong elliptic.

## Bài tập và bài toán cuối chương

### Bài tập Mục 31.1 (trang 932–933)

- **31.1-1:** Chứng minh nếu a > b > 0 và c = a + b thì c mod a = b. *Người tổng hợp:* c = 1 · a + b với 0 ≤ b < a, nên theo tính duy nhất của Định lý 31.1, thương là 1 và số dư là b. (Dùng ở chứng minh F_{k+1} mod F_k = F_{k−1}.)
- **31.1-2:** Chứng minh có vô hạn số nguyên tố. (Gợi ý: chứng minh không số nào trong các số nguyên tố p₁, p₂, …, pₖ chia hết (p₁p₂⋯pₖ) + 1.) *Người tổng hợp:* giả sử chỉ có k số nguyên tố; N = p₁⋯pₖ + 1 chia cho mỗi pᵢ dư 1, nên không pᵢ nào chia hết N; nhưng N > 1 có ít nhất một ước nguyên tố (ước nhỏ nhất lớn hơn 1 của N là số nguyên tố) — mâu thuẫn.
- **31.1-3:** Chứng minh a | b và b | c thì a | c. *Người tổng hợp:* b = ka, c = lb = (lk)a.
- **31.1-4:** Chứng minh nếu p nguyên tố và 0 < k < p thì gcd(k, p) = 1. *Người tổng hợp:* gcd(k, p) là ước của p nên bằng 1 hoặc p; không thể bằng p vì p ∤ k (0 < k < p).
- **31.1-5:** Chứng minh Hệ quả 31.5. *Người tổng hợp:* gcd(a, n) = 1 nên có ax + ny = 1 (Định lý 31.2); nhân với b: abx + nby = b; n chia hết cả abx (vì n | ab) và nby, nên n | b theo (31.4).
- **31.1-6:** Chứng minh nếu p nguyên tố và 0 < k < p thì p chia hết hệ số nhị thức C(p, k). Suy ra với mọi số nguyên a, b và số nguyên tố p: (a + b)ᵖ ≡ aᵖ + bᵖ (mod p). *Người tổng hợp:* C(p, k) · k! · (p − k)! = p!; p chia hết vế phải nhưng không chia hết k! và (p − k)! (các thừa số đều < p, dùng Định lý 31.7 lặp lại), nên p | C(p, k). Khai triển nhị thức, mọi số hạng giữa đều chia hết cho p. Ví dụ p = 5: C(5, k) = 5, 10, 10, 5.
- **31.1-7:** Chứng minh nếu a, b nguyên dương và a | b thì (x mod b) mod a = x mod a với mọi x; và x ≡ y (mod b) kéo theo x ≡ y (mod a). *Người tổng hợp:* x mod b = x − qb = x − (qk)a với b = ka, nên x mod b và x khác nhau một bội của a. Ý thứ hai: b | (x − y) và a | b nên a | (x − y) (Exercise 31.1-3).
- **31.1-8:** Với k > 0, n là **lũy thừa bậc k** (kth power) nếu có số nguyên a với aᵏ = n; n > 1 là **lũy thừa không tầm thường** (nontrivial power) nếu là lũy thừa bậc k với k > 1 nào đó. Chỉ cách xác định một số β-bit n có phải lũy thừa không tầm thường không, trong thời gian đa thức theo β. *Người tổng hợp:* nếu n = aᵏ với a ≥ 2 thì k ≤ lg n ≤ β. Với mỗi k = 2, …, β, tìm nhị phân a trong [1, 2^(⌈β/k⌉)] sao cho aᵏ = n (so sánh aᵏ với n, dừng sớm khi tích vượt n); mỗi lần tìm O(β) bước, mỗi bước tính aᵏ bằng bình phương lặp với số không quá β bit. Tổng đa thức theo β (cỡ O(β³ lg β) phép nhân với cách thô).
- **31.1-9:** Chứng minh (31.6)–(31.10). *Người tổng hợp:* (31.6) tập ước chung của (a, b) và (b, a) như nhau; (31.7), (31.8) d | a ⇔ d | −a; (31.9) mọi số chia hết 0 nên ước chung của a và 0 là ước của a, lớn nhất là |a|; (31.10) mọi ước của a chia hết ka.
- **31.1-10:** Chứng minh gcd có tính kết hợp: gcd(a, gcd(b, c)) = gcd(gcd(a, b), c). *Người tổng hợp:* theo Hệ quả 31.3, d chia hết cả a và gcd(b, c) khi và chỉ khi d chia hết a, b, c; tương tự vế phải. Hai vế có cùng tập ước chung nên cùng giá trị lớn nhất.
- **31.1-11 ★:** Chứng minh Định lý 31.8 (phân tích duy nhất). *Người tổng hợp:* tồn tại — quy nạp mạnh: hợp số a = bc với 1 < b, c < a, mỗi b, c là nguyên tố hoặc có phân tích. Duy nhất — giả sử hai phân tích; p₁ của phân tích thứ nhất chia hết tích của phân tích thứ hai, theo Định lý 31.7 (mở rộng cho nhiều thừa số bằng quy nạp) p₁ chia hết một thừa số nguyên tố q nào đó, nên p₁ = q; giản ước rồi quy nạp theo tổng số mũ.
- **31.1-12:** Cho thuật toán hiệu quả chia một số β-bit cho số ngắn hơn và lấy số dư, chạy Θ(β²). *Người tổng hợp:* chia dài nhị phân (shift-and-subtract): duy trì số dư r, lần lượt đưa từng bit của số bị chia vào r = 2r + bit; nếu r ≥ b thì trừ b và ghi bit thương 1, ngược lại ghi 0. β bước, mỗi bước so sánh và trừ O(β) phép toán bit: Θ(β²).
- **31.1-13:** Cho thuật toán hiệu quả đổi một số nhị phân β-bit sang thập phân. Lập luận rằng nếu nhân hoặc chia các số dài tối đa β tốn M(β) thì đổi được trong Θ(M(β) lg β). (Gợi ý: chia để trị, lấy nửa trên và nửa dưới của kết quả bằng hai đệ quy riêng.) *Người tổng hợp:* nếu kết quả có khoảng D chữ số thập phân, chia số cho 10^(D/2) để được thương (nửa chữ số trên) và dư (nửa dưới), đệ quy hai nửa. Tính trước các lũy thừa 10^(D/2), 10^(D/4), … bằng bình phương. T(β) = 2T(β/2) + Θ(M(β)) cho Θ(M(β) lg β) khi M(β) tăng ít nhất tuyến tính.

### Bài tập Mục 31.2 (trang 938–939)

- **31.2-1:** Chứng minh (31.11) và (31.12) kéo theo (31.13). *Người tổng hợp:* d = Π pᵢ^min(eᵢ,fᵢ) chia hết cả a và b. Mọi ước chung c có dạng Π pᵢ^gᵢ (theo phân tích duy nhất, chỉ dùng các pᵢ này) với gᵢ ≤ eᵢ và gᵢ ≤ fᵢ, nên gᵢ ≤ min(eᵢ, fᵢ) và c | d. Vậy d lớn nhất.
- **31.2-2:** Tính (d, x, y) mà EXTENDED-EUCLID(899, 493) trả về. *Lời giải của người tổng hợp* (bảng trình bày giống bảng EXTENDED-EUCLID(99, 78) ở Mục 3 phần Nội dung chi tiết):

  | a | b | ⌊a/b⌋ | d | x | y |
  |---|---|---|---|---|---|
  | 899 | 493 | 1 | 29 | −6 | 11 |
  | 493 | 406 | 1 | 29 | 5 | −6 |
  | 406 | 87 | 4 | 29 | −1 | 5 |
  | 87 | 58 | 1 | 29 | 1 | −1 |
  | 58 | 29 | 2 | 29 | 0 | 1 |
  | 29 | 0 | — | 29 | 1 | 0 |

  Kết quả (29, −6, 11): 899 · (−6) + 493 · 11 = −5394 + 5423 = 29. (899 = 29 · 31, 493 = 29 · 17.)
- **31.2-3:** Chứng minh với mọi số nguyên a, k, n: gcd(a, n) = gcd(a + kn, n). *Người tổng hợp:* d chia hết a và n ⇔ d chia hết a + kn và n (dùng (31.4) hai chiều, vì a = (a + kn) − kn). Hai cặp có cùng tập ước chung.
- **31.2-4:** Viết lại EUCLID dạng lặp chỉ dùng bộ nhớ hằng. *Người tổng hợp:*

  ```text
  EUCLID-ITERATIVE(a, b)
  1  while b ≠ 0
  2      r = a mod b
  3      a = b
  4      b = r
  5  return a
  ```
- **31.2-5:** Nếu a > b ≥ 0, chứng minh EUCLID(a, b) gọi đệ quy nhiều nhất 1 + log_φ b lần. Cải thiện thành 1 + log_φ(b/gcd(a, b)). *Người tổng hợp:* nếu có k ≥ 1 lần gọi thì b ≥ F_{k+1} ≥ φ^(k−1) (bất đẳng thức F_{m+2} ≥ φᵐ), nên k ≤ 1 + log_φ b. Cải thiện: các lời gọi trên (a, b) và trên (a/g, b/g), g = gcd(a, b), có cùng số bước (mọi số dư đều được chia cho g), nên áp cận cho b/g.
- **31.2-6:** EXTENDED-EUCLID(F_{k+1}, F_k) trả về gì? Chứng minh. *Người tổng hợp:* với k ≥ 2, trả về (1, (−1)^(k+1) F_{k−2}, (−1)ᵏ F_{k−1}). Kiểm tra: k = 4 cho EXTENDED-EUCLID(5, 3) = (1, −1, 2): 5 · (−1) + 3 · 2 = 1; k = 6 cho EXTENDED-EUCLID(13, 8) = (1, −3, 5): −39 + 40 = 1. Chứng minh quy nạp: ⌊F_{k+1}/F_k⌋ = 1 (k ≥ 3), nên từ (1, x′, y′) của (F_k, F_{k−1}) được (1, y′, x′ − y′); thay x′ = (−1)ᵏF_{k−3}, y′ = (−1)^(k−1)F_{k−2} được y′ = (−1)^(k+1)F_{k−2} và x′ − y′ = (−1)ᵏ(F_{k−3} + F_{k−2}) = (−1)ᵏF_{k−1}.
- **31.2-7:** Định nghĩa gcd của nhiều số bằng gcd(a₀, a₁, …, aₙ) = gcd(a₀, gcd(a₁, …, aₙ)). Chứng minh kết quả không phụ thuộc thứ tự đối số. Chỉ cách tìm x₀, …, xₙ với gcd(a₀, …, aₙ) = a₀x₀ + ⋯ + aₙxₙ. Chứng minh số phép chia của thuật toán là O(n + lg(max{a₀, …, aₙ})). *Người tổng hợp:* theo Hệ quả 31.3, gcd nhiều số là ước chung lớn nhất của cả tập — một khái niệm không phụ thuộc thứ tự. Hệ số: tính g₁ = gcd(aₙ₋₁, aₙ) = aₙ₋₁u + aₙv bằng EXTENDED-EUCLID, rồi g₂ = gcd(aₙ₋₂, g₁) = aₙ₋₂u′ + g₁v′, v.v., nhân dồn hệ số. Số phép chia: lời gọi thứ j tốn O(1 + log_φ(gⱼ₋₁/gⱼ)) phép chia (Exercise 31.2-5); cộng lại các log co dần còn O(lg max aᵢ), cộng thêm O(1) mỗi lời gọi cho tổng O(n + lg max aᵢ).
- **31.2-8:** Định nghĩa lcm(a₁, …, aₙ) là **bội chung nhỏ nhất** (least common multiple) — số nguyên không âm nhỏ nhất là bội của mọi aᵢ. Chỉ cách tính hiệu quả bằng gcd hai đối số. *Người tổng hợp:* lcm(a, b) = ab/gcd(a, b) (tính a/gcd(a, b) trước rồi nhân b để số trung gian nhỏ); lcm(a₁, …, aₙ) = lcm(lcm(a₁, …, aₙ₋₁), aₙ). Ví dụ lcm(4, 6, 10) = lcm(12, 10) = 60.
- **31.2-9:** Chứng minh n₁, n₂, n₃, n₄ đôi một nguyên tố cùng nhau khi và chỉ khi gcd(n₁n₂, n₃n₄) = gcd(n₁n₃, n₂n₄) = 1. Tổng quát: n₁, …, nₖ đôi một nguyên tố cùng nhau khi và chỉ khi một tập ⌈lg k⌉ cặp số dựng từ các nᵢ là nguyên tố cùng nhau. *Người tổng hợp:* một số nguyên tố p chia hết hai số nᵢ, nⱼ khác nhau sẽ làm hỏng một trong hai gcd (cặp {1,2} vs {3,4} tách (i, j) nếu chúng khác nhóm; nếu cùng nhóm thì cặp {1,3} vs {2,4} tách chúng); chiều ngược dùng Định lý 31.6. Tổng quát: với mỗi vị trí bit b = 0, …, ⌈lg k⌉ − 1, lấy tích các nᵢ có bit b của (i − 1) bằng 0 và tích các nᵢ có bit đó bằng 1; hai chỉ số khác nhau luôn khác nhau ở ít nhất một bit nên bị tách ở một cặp nào đó.

### Bài tập Mục 31.3 (trang 946)

- **31.3-1:** Vẽ bảng phép toán của (ℤ₄, +₄) và (ℤ₅*, ·₅). Chứng minh chúng đẳng cấu bằng một tương ứng một-một α sao cho a + b ≡ c (mod 4) khi và chỉ khi α(a) · α(b) ≡ α(c) (mod 5). *Lời giải của người tổng hợp:*

  | +₄ | 0 | 1 | 2 | 3 |
  |---|---|---|---|---|
  | **0** | 0 | 1 | 2 | 3 |
  | **1** | 1 | 2 | 3 | 0 |
  | **2** | 2 | 3 | 0 | 1 |
  | **3** | 3 | 0 | 1 | 2 |

  | ·₅ | 1 | 2 | 3 | 4 |
  |---|---|---|---|---|
  | **1** | 1 | 2 | 3 | 4 |
  | **2** | 2 | 4 | 1 | 3 |
  | **3** | 3 | 1 | 4 | 2 |
  | **4** | 4 | 3 | 2 | 1 |

  Chọn α(a) = 2ᵃ mod 5: α(0) = 1, α(1) = 2, α(2) = 4, α(3) = 3. Vì 2 là căn nguyên thủy modulo 5, 2^(a+b) = 2ᵃ · 2ᵇ và số mũ chỉ cần tính modulo 4 (định lý logarit rời rạc).
- **31.3-2:** Liệt kê mọi nhóm con của ℤ₉ và của ℤ₁₃*. *Người tổng hợp:* ℤ₉: {0}, {0, 3, 6}, ℤ₉ (cỡ 1, 3, 9 — đúng các ước của 9). ℤ₁₃* (cyclic, cấp 12, phần tử sinh 2): {1}, {1, 12}, {1, 3, 9}, {1, 5, 8, 12}, {1, 3, 4, 9, 10, 12}, ℤ₁₃* — mỗi ước 1, 2, 3, 4, 6, 12 của 12 cho đúng một nhóm con.
- **31.3-3:** Chứng minh Định lý 31.14. *Người tổng hợp:* tính kết hợp thừa hưởng từ S. Lấy a ∈ S′; vì S hữu hạn và S′ đóng, mọi a^(k) ∈ S′, và dãy tuần hoàn nên a^(ord(a)) = e ∈ S′; nghịch đảo của a là a^(ord(a)−1) ∈ S′ (nếu ord(a) = 1 thì a = e tự nghịch đảo).
- **31.3-4:** Chứng minh nếu p nguyên tố, e nguyên dương thì φ(pᵉ) = p^(e−1)(p − 1). *Người tổng hợp:* trong 0, …, pᵉ − 1, các số không nguyên tố cùng nhau với pᵉ là bội của p, có p^(e−1) số; còn lại pᵉ − p^(e−1). Ví dụ φ(9) = 6 (1, 2, 4, 5, 7, 8).
- **31.3-5:** Chứng minh với mọi n > 1 và a ∈ ℤₙ*, hàm fₐ : ℤₙ* → ℤₙ* định nghĩa bởi fₐ(x) = ax mod n là một hoán vị của ℤₙ*. *Người tổng hợp:* fₐ(x) ∈ ℤₙ* (Định lý 31.6); nếu ax ≡ ay thì nhân a⁻¹ được x ≡ y, nên fₐ đơn ánh trên tập hữu hạn, do đó song ánh. Bảng ℤ₁₅* ở Mục 31.3 minh họa: mỗi hàng là một hoán vị.

### Bài tập Mục 31.4 (trang 950)

- **31.4-1:** Tìm mọi nghiệm của 35x ≡ 10 (mod 50). *Lời giải của người tổng hợp:* EXTENDED-EUCLID(35, 50) = (5, 3, −2) (35 · 3 − 50 · 2 = 5). d = 5 chia hết 10. x₀ = 3 · (10/5) mod 50 = 6. Các nghiệm cách nhau 50/5 = 10: 6, 16, 26, 36, 46. Kiểm tra: 35 · 6 = 210 = 4 · 50 + 10.
- **31.4-2:** Chứng minh ax ≡ ay (mod n) kéo theo x ≡ y (mod n) khi gcd(a, n) = 1. Chỉ ra điều kiện gcd(a, n) = 1 là cần bằng một phản ví dụ với gcd(a, n) > 1. *Người tổng hợp:* n | a(x − y) và gcd(a, n) = 1 nên n | (x − y) (Hệ quả 31.5). Phản ví dụ: 2 · 1 ≡ 2 · 3 (mod 4) nhưng 1 ≢ 3 (mod 4).
- **31.4-3:** Thay dòng 3 của MODULAR-LINEAR-EQUATION-SOLVER bằng x₀ = x′(b/d) mod (n/d). Có chạy đúng không? *Người tổng hợp:* đúng. Giá trị mới chênh với x′(b/d) một bội của n/d, mà theo Định lý 31.24 cộng bội của n/d vào một nghiệm vẫn được nghiệm; x₀ mới nằm trong [0, n/d), nên các giá trị x₀ + i(n/d), i = 0, …, d − 1, nằm trong [0, n) và phân biệt — vẫn là đủ d nghiệm (thậm chí in theo thứ tự tăng, không cần "mod n" ở dòng 5).
- **31.4-4 ★:** Cho p nguyên tố và f(x) ≡ f₀ + f₁x + ⋯ + fₜxᵗ (mod p) là đa thức bậc t, hệ số thuộc ℤₚ. a ∈ ℤₚ là **nghiệm** (zero) của f nếu f(a) ≡ 0 (mod p). Chứng minh nếu a là nghiệm thì f(x) ≡ (x − a)g(x) (mod p) với đa thức g bậc t − 1. Chứng minh bằng quy nạp theo t rằng đa thức bậc t có nhiều nhất t nghiệm phân biệt modulo p. *Người tổng hợp:* f(x) − f(a) = Σ fᵢ(xⁱ − aⁱ), và mỗi xⁱ − aⁱ = (x − a)(x^(i−1) + ⋯ + a^(i−1)), nên f(x) ≡ f(x) − f(a) = (x − a)g(x). Quy nạp: nếu b ≠ a cũng là nghiệm thì (b − a)g(b) ≡ 0, mà p nguyên tố và p ∤ (b − a) nên g(b) ≡ 0 (Định lý 31.7); g bậc t − 1 có ≤ t − 1 nghiệm, nên f có ≤ t nghiệm. (Kết quả này dùng trong Problem 31-4(b). Với p không nguyên tố thì sai: x² − 1 có 4 nghiệm modulo 8.)

### Bài tập Mục 31.5 (trang 953–954)

- **31.5-1:** Tìm mọi nghiệm của hệ x ≡ 4 (mod 5) và x ≡ 5 (mod 11). *Người tổng hợp:* m₁ = 11 ≡ 1 (mod 5), c₁ = 11; m₂ = 5, 5⁻¹ mod 11 = 9 (45 ≡ 1), c₂ = 45. x ≡ 4 · 11 + 5 · 45 = 44 + 225 = 269 ≡ 49 (mod 55). Mọi nghiệm: x = 49 + 55k. Kiểm tra: 49 = 9 · 5 + 4 = 4 · 11 + 5.
- **31.5-2:** Tìm mọi số nguyên x chia cho 9, 8, 7 dư lần lượt 1, 2, 3. *Người tổng hợp:* n = 504. x = 10 + 504k. Cách nhận ra nhanh: 10 = 9 + 1 = 8 + 2 = 7 + 3, nên 10 thỏa cả ba phương trình, và theo Hệ quả 31.28 (9, 8, 7 đôi một nguyên tố cùng nhau) nghiệm là duy nhất modulo 504. Cũng có thể tính theo công thức (31.32).
- **31.5-3:** Lập luận rằng, với định nghĩa của Định lý 31.27, nếu gcd(a, n) = 1 thì (a⁻¹ mod n) ↔ ((a₁⁻¹ mod n₁), (a₂⁻¹ mod n₂), …, (aₖ⁻¹ mod nₖ)). *Người tổng hợp:* gọi b = a⁻¹ mod n; ab ≡ 1 (mod n), theo (31.30) aᵢbᵢ ≡ 1 (mod nᵢ) với mọi i, nên bᵢ = aᵢ⁻¹ mod nᵢ (aᵢ nguyên tố cùng nhau với nᵢ vì gcd(a, n) = 1).
- **31.5-4:** Với định nghĩa của Định lý 31.27, chứng minh với mọi đa thức f, số nghiệm của f(x) ≡ 0 (mod n) bằng tích số nghiệm của các phương trình f(x) ≡ 0 (mod n₁), …, f(x) ≡ 0 (mod nₖ). *Người tổng hợp:* theo (31.28)–(31.30), f(x) mod n ↔ (f(x₁) mod n₁, …, f(xₖ) mod nₖ), nên f(x) ≡ 0 (mod n) ⇔ f(xᵢ) ≡ 0 (mod nᵢ) với mọi i; song ánh CRT cho tương ứng một-một giữa nghiệm modulo n và bộ (nghiệm modulo n₁, …, nghiệm modulo nₖ). Ví dụ x² ≡ 1 (mod 35): 2 nghiệm modulo 5, 2 nghiệm modulo 7, tổng 4 nghiệm modulo 35 (1, 6, 29, 34).

### Bài tập Mục 31.6 (trang 958)

- **31.6-1:** Lập bảng cấp của mọi phần tử của ℤ₁₁*. Chọn căn nguyên thủy nhỏ nhất g và lập bảng ind₁₁,g(x) với mọi x ∈ ℤ₁₁*. *Lời giải của người tổng hợp:*

  | x | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
  |---|---|---|---|---|---|---|---|---|---|---|
  | ord₁₁(x) | 1 | 10 | 5 | 5 | 5 | 10 | 10 | 10 | 5 | 2 |
  | ind₁₁,₂(x) | 0 | 1 | 8 | 2 | 4 | 9 | 7 | 3 | 6 | 5 |

  Căn nguyên thủy nhỏ nhất là g = 2 (lũy thừa của 2 modulo 11: 1, 2, 4, 8, 5, 10, 9, 7, 3, 6). Các căn nguyên thủy là 2, 6, 7, 8 — có φ(10) = 4 cái. Mọi cấp đều là ước của 10 (định lý Lagrange).
- **31.6-2:** Cho thuật toán lũy thừa modulo xét bit của b từ phải sang trái thay vì từ trái sang phải. *Người tổng hợp:*

  ```text
  MODULAR-EXPONENTIATION-RL(a, b, n)
  1  d = 1
  2  s = a mod n                   // s = a^(2^i) mod n
  3  while b > 0
  4      if b is odd
  5          d = (d · s) mod n
  6      s = (s · s) mod n
  7      b = ⌊b/2⌋
  8  return d
  ```
  Bất biến: d · s^b (với b là phần còn lại) ≡ a^(b gốc) (mod n). Cũng O(β) phép nhân.
- **31.6-3:** Giả sử biết φ(n), giải thích cách tính a⁻¹ mod n với a ∈ ℤₙ* bằng MODULAR-EXPONENTIATION. *Người tổng hợp:* theo định lý Euler, a · a^(φ(n)−1) = a^φ(n) ≡ 1, nên a⁻¹ ≡ MODULAR-EXPONENTIATION(a, φ(n) − 1, n). Ví dụ 7⁻¹ mod 15: φ(15) = 8, 7⁷ mod 15 = 13. Khớp với Mục 31.3.

### Bài tập Mục 31.7 (trang 964–965)

- **31.7-1:** Xét bộ khóa RSA p = 11, q = 29, n = 319, e = 3. Khóa bí mật dùng d bằng bao nhiêu? Mã hóa M = 100 được gì? *Người tổng hợp:* φ(n) = 280, d = 3⁻¹ mod 280 = 187 (3 · 187 = 561 = 2 · 280 + 1). Bản mã: 100³ mod 319 = 254 (chi tiết ở ví dụ chạy tay trong Mục 8 của phần Nội dung chi tiết). Giải mã 254¹⁸⁷ mod 319 = 100.
- **31.7-2:** Chứng minh nếu số mũ công khai của Alice là e = 3 và đối thủ biết số mũ bí mật d, với 0 < d < φ(n), thì đối thủ phân tích được n trong thời gian đa thức theo số bit của n. (Sách nói thêm, không yêu cầu chứng minh: kết quả vẫn đúng khi bỏ điều kiện e = 3 — xem Miller.) *Người tổng hợp:* 3d − 1 = kφ(n) với k nguyên dương; vì 0 < d < φ(n) nên 3d − 1 < 3φ(n), suy ra k ∈ {1, 2}. Thử cả hai: φ = (3d − 1)/k. Khi biết φ(n) = n − (p + q) + 1, có p + q = n − φ(n) + 1 và pq = n; p, q là nghiệm của z² − (p + q)z + n = 0, giải bằng căn bậc hai nguyên (tìm nhị phân), đa thức theo số bit. Ví dụ với 31.7-1: 3 · 187 − 1 = 560 = 2 · 280, k = 2; p + q = 319 − 280 + 1 = 40; z² − 40z + 319 = 0 cho z = 11, 29.
- **31.7-3 ★:** Chứng minh RSA có tính nhân: P_A(M₁)P_A(M₂) ≡ P_A(M₁M₂) (mod n). Dùng điều này chứng minh nếu đối thủ có thủ tục giải mã hiệu quả 1% thông điệp thuộc ℤₙ được mã hóa bằng P_A, thì đối thủ có thể dùng một thuật toán xác suất để giải mã mọi thông điệp mã hóa bằng P_A với xác suất cao. *Người tổng hợp:* M₁ᵉM₂ᵉ = (M₁M₂)ᵉ. Để giải mã C bất kỳ: chọn r ngẫu nhiên đều trong ℤₙ*, tính C′ = C · rᵉ mod n = P_A(M · r) — một bản mã phân bố đều (vì M·r đều khi r đều), nên thủ tục giải được với xác suất ≥ 1%; nếu được M′ = M·r thì M = M′ · r⁻¹ mod n. Kiểm tra đáp án bằng cách mã hóa lại (M)ᵉ mod n = C. Lặp tối đa khoảng 100 · ln(1/δ) lần để sai với xác suất ≤ δ (ví dụ khoảng 460 lần cho δ = 1%, vì 0,99⁴⁶⁰ ≈ 0,0098). Đây là ý tưởng "tự quy dẫn ngẫu nhiên" (random self-reducibility) — theo hiểu biết của người tổng hợp.

### Bài tập Mục 31.8 (trang 975)

- **31.8-1:** Chứng minh nếu số nguyên lẻ n > 1 không phải số nguyên tố hay lũy thừa số nguyên tố, thì tồn tại căn bậc hai không tầm thường của 1 modulo n. *Người tổng hợp:* tách n = n₁n₂ với n₁, n₂ lẻ, > 1, nguyên tố cùng nhau. Theo CRT, lấy x ≡ 1 (mod n₁), x ≡ −1 (mod n₂). Khi đó x² ≡ 1 theo cả hai modulus nên theo n; x ≢ 1 (mod n) vì x ≢ 1 (mod n₂) (n₂ > 2), x ≢ −1 (mod n) tương tự. Ví dụ n = 35: x ≡ 1 (mod 5), x ≡ −1 (mod 7) cho x = 6.
- **31.8-2 ★:** Có thể làm mạnh định lý Euler thành a^λ(n) ≡ 1 (mod n) với mọi a ∈ ℤₙ*, trong đó n = p₁^e₁ ⋯ pᵣ^eᵣ và

  ```text
  λ(n) = lcm(φ(p₁^e₁), …, φ(pᵣ^eᵣ))                                   (31.42)
  ```
  Chứng minh λ(n) | φ(n). Một hợp số n là số Carmichael nếu λ(n) | n − 1. Số Carmichael nhỏ nhất là 561 = 3 · 11 · 17; ở đây λ(n) = lcm(2, 10, 16) = 80, chia hết 560. Chứng minh số Carmichael phải vừa "không chính phương" (không chia hết cho bình phương của số nguyên tố nào) vừa là tích của ít nhất ba số nguyên tố. (Vì lý do này chúng không phổ biến.) *Người tổng hợp:* φ(n) = Π φ(pᵢ^eᵢ) là bội chung của các φ(pᵢ^eᵢ), nên bội chung nhỏ nhất λ(n) chia hết nó. Không chính phương: nếu p² | n thì p | φ(p^e) | λ(n) | n − 1, mà p | n — vô lý. Ít nhất ba thừa số: nếu n = pq với p < q thì q − 1 | n − 1 = pq − 1 = p(q − 1) + (p − 1), nên q − 1 | p − 1, vô lý vì 0 < p − 1 < q − 1. Kiểm tra 561: 560/2 = 280, 560/10 = 56, 560/16 = 35.
- **31.8-3:** Chứng minh nếu x là căn bậc hai không tầm thường của 1 modulo n thì gcd(x − 1, n) và gcd(x + 1, n) đều là ước không tầm thường của n. *Người tổng hợp:* n | (x − 1)(x + 1) nhưng n ∤ (x − 1) và n ∤ (x + 1). Nếu gcd(x − 1, n) = 1 thì theo Hệ quả 31.5 n | x + 1 — vô lý; nếu gcd(x − 1, n) = n thì n | x − 1 — vô lý. Tương tự cho x + 1. Ví dụ x = 6, n = 35: gcd(5, 35) = 5, gcd(7, 35) = 7. Với x = 67, n = 561: 33 và 17.

### Bài tập Mục 31.9 (trang 980)

- **31.9-1:** Với ví dụ n = 1387, x₁ = 2 (Hình 31.7(a) của sách; dãy giá trị đã chép ở Mục 10 phần Nội dung chi tiết), khi nào POLLARD-RHO in thừa số 73 của 1387? *Lời giải của người tổng hợp:* sau khi in 19 ở i = 7, thủ tục chạy tiếp: i = 8 lưu y = x₈ = 814 (k = 16). Ở i = 11, x₁₁ = 396, gcd(814 − 396, 1387) = gcd(418, 1387) = 19 (in lại 19). Ở **i = 12**, x₁₂ = 84, gcd(814 − 84, 1387) = gcd(730, 1387) = **73** — lần đầu in 73. Lý giải: modulo 73, x₈ ≡ 11 và x₁₂ ≡ 11 (chu trình 18 → 31 → 11 → 47 dài 4).
- **31.9-2:** Cho hàm f : ℤₙ → ℤₙ và giá trị đầu x₀ ∈ ℤₙ. Định nghĩa xᵢ = f(xᵢ₋₁) với i = 1, 2, …. Gọi t và u > 0 là các giá trị nhỏ nhất sao cho x_{t+i} = x_{t+u+i} với i = 0, 1, …. Theo thuật ngữ rho, t là độ dài đuôi và u là độ dài chu trình. Cho thuật toán hiệu quả xác định chính xác t và u, và phân tích thời gian. *Người tổng hợp:* thuật toán "rùa và thỏ" của Floyd: rùa đi 1 bước, thỏ đi 2 bước cho tới khi gặp (sau O(t + u) bước); tìm t: đặt rùa về x₀, cả hai đi 1 bước cho tới khi gặp — số bước là t; tìm u: từ điểm gặp, đi tiếp tới khi quay lại — số bước là u. Thời gian Θ(t + u) lần tính f, bộ nhớ O(1). (Biến thể Brent dùng lũy thừa của 2 — giống cách POLLARD-RHO lưu y.)
- **31.9-3:** POLLARD-RHO cần khoảng bao nhiêu bước để phát hiện một thừa số dạng pᵉ, p nguyên tố, e > 1? *Người tổng hợp:* phân tích của sách áp dụng với "thừa số" p′ = pᵉ thỏa gcd(p′, n/p′) = 1, cho kỳ vọng Θ(√(pᵉ)) bước để dãy modulo pᵉ lặp. Nhưng va chạm modulo p (kỳ vọng Θ(√p) bước) thường xảy ra trước, khi đó gcd tìm được thường chỉ là p hoặc một lũy thừa nhỏ hơn của p; để có đủ pᵉ có thể chia dần n cho p. Như vậy phát hiện p mất Θ(√p), còn chờ đúng pᵉ lộ ra trong một gcd mất Θ(√(pᵉ)) = Θ(p^(e/2)).
- **31.9-4 ★:** Nhược điểm của POLLARD-RHO như đã viết là cần một phép gcd cho mỗi bước truy hồi. Thay vào đó có thể gom các phép gcd: tích lũy tích của nhiều giá trị (y − xᵢ) liên tiếp rồi dùng tích đó trong phép gcd. Mô tả cẩn thận cách cài đặt, vì sao đúng, và chọn cỡ lô nào hiệu quả nhất với số n β-bit. *Người tổng hợp:* giữ Q = Π (y − xᵢ) mod n qua B bước, rồi tính gcd(Q, n). Đúng vì p | (y − xᵢ) với một i nào đó trong lô kéo theo p | Q (và p | n), nên gcd(Q, n) > 1. Rủi ro: tích có thể chứa đủ mọi thừa số làm gcd = n; khi đó quay lại đầu lô (lưu trạng thái x, y đầu lô) và tính gcd từng bước. Cỡ lô: chi phí một gcd theo cách tính của chương là O(β) phép chia (O(β³) phép toán bit, hoặc O(β²) theo Problem 31-2), còn một phép nhân modulo là O(β²) phép toán bit; chọn B sao cho chi phí gcd chia đều không còn chiếm ưu thế — cỡ B ≈ β (hoặc vài chục tới vài trăm trong thực hành); B quá lớn làm tăng xác suất phải quay lui và lãng phí bước sau khi đã có va chạm.

### Problem 31-1: Thuật toán gcd nhị phân (Binary gcd algorithm)

Đa số máy tính thực hiện phép trừ, kiểm tra tính chẵn lẻ của số nhị phân, và chia đôi nhanh hơn tính số dư. Bài toán nghiên cứu **thuật toán gcd nhị phân** (binary gcd algorithm), tránh các phép tính số dư của thuật toán Euclid.

- **(a)** Chứng minh nếu a và b đều chẵn thì gcd(a, b) = 2 · gcd(a/2, b/2). (*Người tổng hợp:* Hệ quả 31.4 với n = 2.)
- **(b)** Chứng minh nếu a lẻ và b chẵn thì gcd(a, b) = gcd(a, b/2). (*Người tổng hợp:* mọi ước chung là ước của a nên lẻ, do đó nguyên tố cùng nhau với 2; theo Hệ quả 31.5, d | b kéo theo d | b/2.)
- **(c)** Chứng minh nếu a và b đều lẻ thì gcd(a, b) = gcd((a − b)/2, b). (*Người tổng hợp:* gcd(a, b) = gcd(a − b, b) (Exercise 31.2-3 với k = −1); a − b chẵn còn b lẻ, áp (b).)
- **(d)** Thiết kế thuật toán gcd nhị phân hiệu quả cho a ≥ b chạy O(lg a), giả sử mỗi phép trừ, kiểm tra chẵn lẻ, chia đôi tốn đơn vị thời gian. *Lời giải của người tổng hợp:*

  ```text
  BINARY-GCD(a, b)
   1  if b == 0
   2      return a
   3  if a == 0
   4      return b
   5  if a and b are both even
   6      return 2 · BINARY-GCD(a/2, b/2)
   7  if a is even
   8      return BINARY-GCD(a/2, b)
   9  if b is even
  10      return BINARY-GCD(a, b/2)
  11  if a ≥ b
  12      return BINARY-GCD((a − b)/2, b)
  13  else return BINARY-GCD((b − a)/2, a)
  ```
  Mỗi lần gọi làm tổng số bit của a và b giảm ít nhất 1 (một trong hai số bị chia đôi), nên O(lg a + lg b) = O(lg a) lần gọi. Ví dụ gcd(48, 18): (24, 9) với hệ số 2 → (12, 9) → (6, 9) → (3, 9) → ((9 − 3)/2, 3) = (3, 3) → (0, 3) → 3; kết quả 2 · 3 = 6.

### Problem 31-2: Phân tích số phép toán bit trong thuật toán Euclid (Analysis of bit operations in Euclid's algorithm)

- **(a)** Xét thuật toán chia dài "giấy và bút" thông thường: chia a cho b được thương q và dư r. Chứng minh cách này cần O((1 + lg q) lg b) phép toán bit. (*Người tổng hợp:* thương q có 1 + ⌊lg q⌋ bit; mỗi bit thương cần một phép so sánh và có thể một phép trừ trên số khoảng lg b bit.)
- **(b)** Định nghĩa μ(a, b) = (1 + lg a)(1 + lg b). Chứng minh số phép toán bit EUCLID dùng để quy bài toán gcd(a, b) về gcd(b, a mod b) nhiều nhất là c(μ(a, b) − μ(b, a mod b)) với hằng số c > 0 đủ lớn. (*Người tổng hợp:* đặt r = a mod b. μ(a, b) − μ(b, r) = (1 + lg b)(lg a − lg r). Vì a ≥ qb + r ≥ qb và a ≥ b + r ≥ 2r (nếu r > 0), lg a − lg r ≥ max(lg q, 1) ≥ (1 + lg q)/2; với r = 0 coi lg r như −1 hoặc xử lý riêng. Nên hiệu ≥ (1 + lg b)(1 + lg q)/2, đủ phủ chi phí ở (a).)
- **(c)** Chứng minh EUCLID(a, b) cần O(μ(a, b)) phép toán bit nói chung và O(β²) khi áp lên hai đầu vào β-bit. (*Người tổng hợp:* cộng các chi phí ở (b) qua mọi bước, tổng co dần còn ≤ c · μ(a, b) = O(lg a · lg b) = O(β²).)

### Problem 31-3: Ba thuật toán tính số Fibonacci (Three algorithms for Fibonacci numbers)

So sánh hiệu quả ba cách tính số Fibonacci thứ n, Fₙ, cho n. Giả sử chi phí cộng, trừ, nhân hai số là O(1), không phụ thuộc cỡ số.

- **(a)** Chứng minh thời gian chạy của cách đệ quy thẳng dựa trên truy hồi (3.22) là hàm mũ theo n (ví dụ thủ tục FIB ở Chương 27: FIB(n) trả về n nếu n ≤ 1, ngược lại trả về FIB(n − 1) + FIB(n − 2)). (*Người tổng hợp:* T(n) = T(n − 1) + T(n − 2) + Θ(1) ≥ Fₙ, nên T(n) = Θ(φⁿ).)
- **(b)** Chỉ cách tính Fₙ trong O(n) bằng ghi nhớ (memoization). (*Người tổng hợp:* lưu F₀, …, Fₙ trong bảng, mỗi giá trị tính một lần từ hai giá trị trước; hoặc chỉ giữ hai giá trị gần nhất.)
- **(c)** Chỉ cách tính Fₙ trong O(lg n) chỉ dùng cộng và nhân số nguyên. (Gợi ý: xét ma trận [[0, 1], [1, 1]] và các lũy thừa của nó.) *Người tổng hợp:* [[0, 1], [1, 1]]ⁿ = [[F_{n−1}, F_n], [F_n, F_{n+1}]] (quy nạp); tính lũy thừa ma trận 2 × 2 bằng bình phương lặp như MODULAR-EXPONENTIATION: O(lg n) phép nhân ma trận, mỗi phép 8 phép nhân và 4 phép cộng số. Ví dụ n = 10: M² = [[1,1],[1,2]], M⁴ = [[2,3],[3,5]], M⁸ = [[13,21],[21,34]], M¹⁰ = M⁸M² = [[34,55],[55,89]] nên F₁₀ = 55.
- **(d)** Giả sử giờ cộng hai số β-bit tốn Θ(β) và nhân hai số β-bit tốn Θ(β²). Thời gian chạy của ba cách theo thước đo hợp lý hơn này là bao nhiêu? (*Người tổng hợp:* Fₖ có Θ(k) bit. (a): số lần gọi với đối số k tỉ lệ F_{n−k}, mỗi phép cộng Θ(k), tổng Σ k φ^(n−k) = Θ(φⁿ) — vẫn hàm mũ. (b): Σₖ Θ(k) = Θ(n²). (c): lần bình phương cuối trên số Θ(n) bit tốn Θ(n²), các lần trước nhỏ dần theo cấp số nhân (Θ((n/2ʲ)²)), tổng Θ(n²) — không tốt hơn (b) về bậc với phép nhân Θ(β²); chỉ thắng khi dùng phép nhân nhanh.)

### Problem 31-4: Thặng dư bậc hai (Quadratic residues)

Cho p là số nguyên tố lẻ. Số a ∈ ℤₚ* là **thặng dư bậc hai** (quadratic residue) nếu phương trình x² ≡ a (mod p) có nghiệm x (sách in "=" thay cho "≡", xem khối Lưu ý).

- **(a)** Chứng minh có đúng (p − 1)/2 thặng dư bậc hai modulo p. (*Người tổng hợp:* ánh xạ x ↦ x² trên ℤₚ* là "hai-đối-một": x² ≡ y² ⇔ p | (x − y)(x + y) ⇔ x ≡ ±y (Định lý 31.7), và x ≢ −x vì p lẻ. Ví dụ p = 7: bình phương của 1..6 là 1, 4, 2, 2, 4, 1 → thặng dư {1, 2, 4}, đúng (7 − 1)/2 = 3 số.)
- **(b)** Nếu p nguyên tố, định nghĩa **ký hiệu Legendre** (Legendre symbol) (a/p), với a ∈ ℤₚ*, bằng 1 nếu a là thặng dư bậc hai modulo p và −1 nếu không. Chứng minh nếu a ∈ ℤₚ* thì (a/p) ≡ a^((p−1)/2) (mod p). Cho thuật toán hiệu quả xác định một số a cho trước có phải thặng dư bậc hai modulo p không, và phân tích hiệu quả. (*Người tổng hợp:* đặt y = a^((p−1)/2); y² = a^(p−1) ≡ 1 nên y ≡ ±1 (Định lý 31.34). Nếu a = x² thì y = x^(p−1) ≡ 1. Đa thức z^((p−1)/2) − 1 có nhiều nhất (p − 1)/2 nghiệm (Exercise 31.4-4), mà (p − 1)/2 thặng dư đều là nghiệm, nên mọi phi thặng dư cho y ≡ −1. Thuật toán: một lần MODULAR-EXPONENTIATION, O(β) phép toán số học, O(β³) phép toán bit. Ví dụ p = 7, a = 3: 3³ = 27 ≡ 6 ≡ −1, nên 3 không là thặng dư — khớp với (a).)
- **(c)** Chứng minh nếu p là số nguyên tố dạng 4k + 3 và a là thặng dư bậc hai trong ℤₚ* thì a^(k+1) mod p là một căn bậc hai của a modulo p. Cần bao nhiêu thời gian để tìm căn bậc hai của một thặng dư bậc hai a modulo p? (*Người tổng hợp:* (a^(k+1))² = a^(2k+2) = a^((p+1)/2) = a · a^((p−1)/2) ≡ a · 1 = a. Thời gian: một lũy thừa modulo, O(β³) phép toán bit. Ví dụ p = 7 = 4 · 1 + 3, a = 2: 2² = 4, và 4² = 16 ≡ 2.)
- **(d)** Mô tả thuật toán ngẫu nhiên hiệu quả tìm một phi thặng dư bậc hai modulo một số nguyên tố p bất kỳ, tức một phần tử của ℤₚ* không phải thặng dư bậc hai. Thuật toán cần trung bình bao nhiêu phép toán số học? (*Người tổng hợp:* chọn a ngẫu nhiên đều trong ℤₚ*, kiểm tra bằng (b); theo (a) xác suất thành công mỗi lần là 1/2, số lần thử kỳ vọng 2, mỗi lần O(β) phép toán số học — tổng kỳ vọng O(β) = O(lg p).)

### Ghi chú chương (Chapter notes, trang 982–984)

- **Tài liệu nền.** Niven và Zuckerman là phần nhập môn tuyệt vời về lý thuyết số sơ cấp. Knuth có thảo luận tốt về các thuật toán tìm ước chung lớn nhất và các thuật toán số học cơ bản khác. Bach và Riesel cho các khảo sát gần đây hơn về lý thuyết số tính toán. Dixon cho tổng quan về phân tích thừa số và thử nguyên tố. Kỷ yếu hội nghị do Pomerance biên tập có nhiều bài khảo sát xuất sắc. Gần đây hơn, Bach và Shallit cho tổng quan đặc biệt về nền tảng của lý thuyết số tính toán.
- **Nguồn gốc thuật toán Euclid.** Knuth bàn về nguồn gốc thuật toán Euclid. Nó xuất hiện trong Sách 7, Mệnh đề 1 và 2, của bộ *Cơ sở* (Elements) của nhà toán học Hy Lạp Euclid, viết khoảng 300 TCN. Mô tả của Euclid có thể lấy từ một thuật toán của Eudoxus khoảng 375 TCN. Thuật toán Euclid có thể giữ danh hiệu thuật toán không tầm thường cổ nhất; chỉ có một thuật toán nhân mà người Ai Cập cổ biết là sánh được. Shallit ghi lại lịch sử phân tích thuật toán Euclid.
- **Định lý số dư Trung Hoa.** Knuth gán một trường hợp đặc biệt của định lý (Định lý 31.27) cho nhà toán học Trung Hoa Tôn Tử, sống đâu đó giữa 200 TCN và 200 SCN — niên đại rất không chắc chắn. Cùng trường hợp đặc biệt đó được nhà toán học Hy Lạp Nichomachus (Nicomachus) nêu khoảng năm 100 SCN. Nó được Chhin Chiu-Shao (Tần Cửu Thiều) tổng quát hóa năm 1247. Định lý cuối cùng được phát biểu và chứng minh tổng quát đầy đủ bởi L. Euler năm 1734.
- **Thử nguyên tố.** Thuật toán thử nguyên tố ngẫu nhiên trình bày ở đây là của Miller và Rabin; đó là thuật toán thử nguyên tố ngẫu nhiên nhanh nhất được biết, tới một hằng số. Chứng minh Định lý 31.39 là một sửa đổi nhỏ của chứng minh do Bach đề xuất. Monier chứng minh một kết quả mạnh hơn cho MILLER-RABIN. Nhiều năm, thử nguyên tố là ví dụ kinh điển của bài toán mà sự ngẫu nhiên có vẻ cần thiết để có thuật toán hiệu quả (thời gian đa thức). Nhưng năm 2002, Agrawal, Kayal và Saxena (sách in "Saxema") làm mọi người bất ngờ với thuật toán thử nguyên tố tất định thời gian đa thức. Trước đó, thuật toán thử nguyên tố tất định nhanh nhất được biết, của Cohen và Lenstra, chạy trong thời gian (lg n)^O(lg lg lg n) trên đầu vào n — chỉ hơi siêu đa thức. Dù vậy, cho mục đích thực tế, các thuật toán thử nguyên tố ngẫu nhiên vẫn hiệu quả hơn và được ưa dùng.
- **Tìm số nguyên tố lớn ngẫu nhiên** được bàn kỹ trong bài báo của Beauchemin, Brassard, Crépeau, Goutier và Pomerance.
- **Mật mã khóa công khai.** Khái niệm hệ mật mã khóa công khai là của Diffie và Hellman. Hệ RSA được Rivest, Shamir và Adleman đề xuất năm 1977. Từ đó ngành mật mã nở rộ. Hiểu biết về RSA sâu hơn, và các cài đặt hiện đại dùng những cải tiến đáng kể của các kỹ thuật cơ bản trình bày ở đây. Thêm vào đó, nhiều kỹ thuật mới được phát triển để chứng minh hệ mật mã an toàn. Ví dụ, Goldwasser và Micali chỉ ra ngẫu nhiên có thể là công cụ hiệu quả trong thiết kế lược đồ mã hóa khóa công khai an toàn. Về lược đồ chữ ký, Goldwasser, Micali và Rivest trình bày một lược đồ chữ ký số mà mọi kiểu giả mạo có thể nghĩ ra đều được chứng minh khó như phân tích thừa số. Menezes, van Oorschot và Vanstone cho tổng quan về mật mã ứng dụng.
- **Phân tích thừa số.** Heuristic rho cho phân tích thừa số do Pollard phát minh. Phiên bản trình bày ở đây là một biến thể do Brent đề xuất. Các thuật toán tốt nhất để phân tích số lớn có thời gian chạy tăng xấp xỉ hàm mũ theo căn bậc ba của độ dài số n cần phân tích. Thuật toán sàng trường số tổng quát (general number-field sieve) (do Buhler, Lenstra và Pomerance phát triển như mở rộng của ý tưởng sàng trường số của Pollard và Lenstra cùng cộng sự, được Coppersmith và những người khác tinh chỉnh) có lẽ là thuật toán hiệu quả nhất nói chung cho đầu vào lớn. Dù khó phân tích chặt chẽ thuật toán này, với các giả định hợp lý có thể ước lượng thời gian chạy L(1/3, n)^(1,902+o(1)), với L(α, n) = e^((ln n)^α (ln ln n)^(1−α)). Phương pháp đường cong elliptic (elliptic-curve method) của Lenstra có thể hiệu quả hơn sàng trường số với một số đầu vào, vì như rho của Pollard, nó tìm được thừa số nguyên tố nhỏ p khá nhanh. Với phương pháp này, thời gian tìm p ước lượng là L(1/2, p)^(√2+o(1)).

  Giải thích ký hiệu L (người tổng hợp): L(α, n) nội suy giữa đa thức và hàm mũ theo độ dài lg n: α = 0 cho e^(ln ln n) = ln n (đa thức theo độ dài), α = 1 cho e^(ln n) = n (hàm mũ theo độ dài). Sàng trường số với α = 1/3 vì vậy là "dưới hàm mũ" — nhanh hơn hẳn rho Pollard (n^(1/4)), nhưng vẫn không đa thức.

## Luận điểm cốt lõi

### Mệnh đề

Với số nguyên lớn, kích thước đầu vào là số bit β; các phép toán số học cốt lõi — ước chung lớn nhất, nghịch đảo modulo, giải phương trình đồng dư tuyến tính, lũy thừa modulo — đều làm được bằng O(β) phép toán số học (O(β³) phép toán bit), và kiểm tra tính nguyên tố làm được bằng thuật toán ngẫu nhiên Miller-Rabin với xác suất sai ≤ 2⁻ˢ; trong khi đó chưa có thuật toán đa thức nào phân tích một số ra thừa số. Sự bất đối xứng "dễ tạo, khó phá" này là nền của hệ mật mã khóa công khai RSA.

### Giả định

- Mô hình chi phí: nhân, chia, lấy dư hai số β-bit tốn Θ(β²) phép toán bit (thuật toán thường); cộng, trừ tốn Θ(β). Các phân tích đếm cả phép toán số học lẫn phép toán bit.
- Định lý phép chia, định lý Lagrange, Định lý 31.32 (khi nào ℤₙ* cyclic), công thức φ(n) (31.20), định lý số nguyên tố và các cận (31.22)–(31.24) được dùng mà không chứng minh trong sách.
- Phép thử Miller-Rabin giả định có bộ sinh RANDOM(1, n − 1) ngẫu nhiên đều và các lần chọn độc lập.
- Phân tích rho của Pollard giả định hàm fₙ(x) = (x² − 1) mod n "hành xử như hàm ngẫu nhiên" — một giả định heuristic, không được chứng minh.
- Độ an toàn của RSA dựa trên giả định (chưa chứng minh) rằng phân tích số lớn là khó, và rằng không có cách phá RSA dễ hơn phân tích n.

### Cơ chế

1. **gcd là tổ hợp tuyến tính dương nhỏ nhất** (Định lý 31.2) — từ đây suy ra mọi tính chất: ước chung chia hết gcd, Định lý 31.6, Định lý 31.7, phân tích duy nhất.
2. **gcd(a, b) = gcd(b, a mod b)** — mỗi bước Euclid ít nhất "đi lùi" một số Fibonacci, nên số bước là O(log_φ b); chạy ngược các bước cho hệ số x, y (EXTENDED-EUCLID).
3. **Khuôn nhóm hữu hạn** — ℤₙ* là nhóm; định lý Lagrange cho a^|S| = e (Euler, Fermat) và cho "nhóm con thực sự có cỡ ≤ một nửa".
4. **ax ≡ b (mod n)** — nhóm con sinh bởi a chính là bội của d = gcd(a, n); có nghiệm ⇔ d | b; d nghiệm cách nhau n/d; trường hợp b = 1 cho nghịch đảo.
5. **Định lý số dư Trung Hoa** — ℤₙ ≅ ℤₙ₁ × ⋯ × ℤₙₖ; dùng để ghép các kết luận "modulo p" và "modulo q" thành "modulo n" (RSA), để dựng phần tử w ngoài B (Miller-Rabin), và để giải thích vì sao dãy modulo p lặp sớm (rho Pollard).
6. **Bình phương lặp** — aᵇ mod n bằng ⌊lg b⌋ + 1 bước bình phương và tối đa ngần ấy phép nhân.
7. **RSA** — ed ≡ 1 (mod φ(n)) cộng định lý Fermat theo p và q, ghép bằng CRT, cho M^(ed) ≡ M (mod n).
8. **Miller-Rabin** — hai loại bằng chứng hợp số (vi phạm Fermat; căn bậc hai không tầm thường của 1); các không bằng chứng nằm trong một nhóm con thực sự nên chiếm ≤ một nửa.
9. **Rho Pollard** — va chạm của dãy modulo một thừa số p chưa biết được phát hiện bằng gcd với n, sau kỳ vọng Θ(√p) bước nhờ nghịch lý ngày sinh.

### Bằng chứng và ví dụ tác giả đưa ra

- gcd(30, 21) = 3 qua ba lần gọi đệ quy; bảng EXTENDED-EUCLID(99, 78) = (3, −11, 14).
- Chứng minh chặt cận Lamé bằng EUCLID(F_{k+1}, F_k) gọi đúng k − 1 lần.
- Bảng nhóm (ℤ₆, +₆) và (ℤ₁₅*, ·₁₅); φ(45) = 24; nghịch đảo 5⁻¹ ≡ 9 (mod 11), 7⁻¹ ≡ 13 (mod 15).
- Các nhóm con ⟨0⟩, ⟨1⟩, ⟨2⟩ trong ℤ₆ và ⟨1⟩, ⟨2⟩, ⟨3⟩ trong ℤ₇*.
- 14x ≡ 30 (mod 100): nghiệm 95 và 45.
- Bài toán Tôn Tử (23 + 105k); a ≡ 2 (mod 5), a ≡ 3 (mod 13) cho a ≡ 42 (mod 65); bảng CRT 5 × 13.
- Lũy thừa 3ⁱ và 2ⁱ modulo 7; 6 là căn không tầm thường của 1 modulo 35; bảng MODULAR-EXPONENTIATION(7, 560, 561).
- Sơ đồ mã hóa (Bob gửi C = P_A(M), Alice giải S_A(C)) và sơ đồ chữ ký (Alice gửi (M′, σ), Bob kiểm tra M′ = P_A(σ)); chứng minh Định lý 31.36.
- π(10⁹) so với n/ln n; 710 lần thử cho số 1024 bit; 22 giả nguyên tố cơ số 2 dưới 10.000; ba số Carmichael đầu; 255 số Carmichael dưới 10⁸.
- WITNESS(7, 561) cho X = ⟨241, 298, 166, 67, 1⟩.
- Phân tích Bayes: khoảng 9 lần thử cho số 1024 bit chỉ để vượt định kiến; s = 50 là đủ.
- Dãy rho cho 1387 = 19 · 73 (đuôi 5 phần tử, chu trình 12) cùng các dãy modulo 19 (chu trình 3) và modulo 73 (chu trình 4).

### Kết luận và hàm ý cho người lập trình

- Khi làm việc với số lớn, đừng nghĩ "O(n) là nhanh": n ở đây là giá trị, còn kích thước là lg n. Chia thử tới √n là hàm mũ.
- Đừng tự viết mật mã dựa trên RSA "sách giáo khoa": RSA thuần (Mᵉ mod n, không đệm ngẫu nhiên) có tính nhân (Exercise 31.7-3) và là tất định — các chuẩn thực tế (OAEP, PSS) thêm đệm ngẫu nhiên (theo hiểu biết của người tổng hợp; ghi chú chương của sách cũng nhắc tới việc ngẫu nhiên hóa của Goldwasser–Micali).
- Tạo số nguyên tố lớn: chọn số lẻ ngẫu nhiên, lọc bằng các số nguyên tố nhỏ, rồi chạy Miller-Rabin; kỳ vọng thử khoảng (ln n)/2 số lẻ.
- Dùng Miller-Rabin chứ không dùng phép thử Fermat đơn thuần nếu đầu vào có thể do đối thủ chọn (số Carmichael).
- Tính nghịch đảo modulo bằng EXTENDED-EUCLID (O(lg n) bước), hoặc bằng a^(p−2) khi modulus là số nguyên tố p.
- Lũy thừa modulo luôn bằng bình phương lặp, và luôn lấy mod sau mỗi phép nhân để số không phình ra.
- Khi cần phân tích số không quá lớn, thử chia cho số nhỏ trước, rồi rho Pollard (biến thể Brent, gom gcd), và nhớ khởi động lại với hằng số c khác khi gcd trả về n.

### Trong ngôn ngữ khoa học máy tính

EUCLID / EXTENDED-EUCLID: O(lg b) lời gọi, O(β) phép toán số học, O(β³) (chặt hơn: O(β²)) phép toán bit; xấu nhất trên (F_{k+1}, F_k). MODULAR-LINEAR-EQUATION-SOLVER: O(lg n + gcd(a, n)) phép toán số học. MODULAR-EXPONENTIATION: O(β) phép toán số học, O(β³) phép toán bit. RSA: khóa công khai O(β²), khóa bí mật O(β³) phép toán bit. MILLER-RABIN(n, s): O(sβ) phép toán số học, O(sβ³) phép toán bit, sai một phía với xác suất ≤ 2⁻ˢ (thuật toán Monte Carlo sai một phía: báo COMPOSITE luôn đúng). POLLARD-RHO: heuristic, kỳ vọng Θ(√p) phép toán số học để tìm thừa số p, phân tích hết số β bit trong khoảng 2^(β/4) phép toán số học, bộ nhớ O(1). Phân tích thừa số tổng quát tốt nhất (sàng trường số): L(1/3, n)^(1,902+o(1)) — dưới hàm mũ nhưng trên đa thức; kiểm tra nguyên tố tất định thuộc P (AKS, 2002).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| number theory | lý thuyết số | ngành toán về số nguyên |
| bit operation | phép toán bit | đơn vị chi phí khi số lớn |
| polynomial-time algorithm (on integers) | thuật toán thời gian đa thức (trên số nguyên) | chạy đa thức theo số bit của đầu vào |
| divides, d \| a | chia hết | a = kd với k nguyên |
| multiple | bội | a là bội của d nếu d \| a |
| divisor | ước | ước không âm của a |
| trivial divisors | ước tầm thường | 1 và chính a |
| factor | thừa số | ước không tầm thường |
| prime (number) | số nguyên tố | số > 1 chỉ có ước tầm thường |
| composite (number) | hợp số | số > 1 không nguyên tố |
| unit | đơn vị | số 1, không nguyên tố cũng không hợp số |
| division theorem | định lý phép chia | a = qn + r, 0 ≤ r < n duy nhất |
| quotient / remainder (residue) | thương / số dư | ⌊a/n⌋ và a mod n |
| equivalence class modulo n | lớp đồng dư modulo n | [a]ₙ = {a + kn} |
| common divisor / greatest common divisor (gcd) | ước chung / ước chung lớn nhất | ước của cả a và b / lớn nhất trong số đó |
| linear combination | tổ hợp tuyến tính | ax + by với x, y nguyên |
| relatively prime | nguyên tố cùng nhau | gcd = 1 |
| pairwise relatively prime | đôi một nguyên tố cùng nhau | mọi cặp có gcd = 1 |
| unique factorization | phân tích (thừa số nguyên tố) duy nhất | mỗi hợp số có đúng một phân tích |
| Euclid's algorithm | thuật toán Euclid | gcd(a, b) = gcd(b, a mod b) |
| GCD recursion theorem | định lý đệ quy gcd | Định lý 31.9 |
| Lamé's theorem | định lý Lamé | cận số bước Euclid qua số Fibonacci |
| extended Euclid's algorithm | thuật toán Euclid mở rộng | trả thêm x, y với d = ax + by |
| group / abelian group / finite group | nhóm / nhóm Abel / nhóm hữu hạn | tập với phép toán thỏa 4 tiên đề / giao hoán / hữu hạn |
| identity / inverse | phần tử đơn vị / nghịch đảo | e với e ⊕ a = a / b với a ⊕ b = e |
| additive group modulo n (ℤₙ, +ₙ) | nhóm cộng modulo n | n lớp với phép cộng |
| multiplicative group modulo n (ℤₙ*, ·ₙ) | nhóm nhân modulo n | lớp nguyên tố cùng nhau với n, phép nhân |
| Euler's phi function φ(n) | hàm phi Euler | \|ℤₙ*\| |
| Euler's constant γ | hằng số Euler | 0,5772… |
| subgroup / proper subgroup | nhóm con / nhóm con thực sự | tập con là nhóm / khác cả nhóm |
| Lagrange's theorem | định lý Lagrange | cỡ nhóm con chia hết cỡ nhóm |
| subgroup generated by a, ⟨a⟩ | nhóm con sinh bởi a | mọi "lũy thừa" của a |
| generator | phần tử sinh | phần tử sinh ra (nhóm) con |
| order of an element, ord(a) | cấp của phần tử | t nhỏ nhất với a^(t) = e |
| modular linear equation | phương trình tuyến tính modulo | ax ≡ b (mod n) |
| multiplicative inverse, a⁻¹ mod n | nghịch đảo nhân modulo n | x với ax ≡ 1 (mod n) |
| Chinese remainder theorem | định lý số dư Trung Hoa | ℤₙ ≅ tích các ℤₙᵢ |
| Euler's theorem / Fermat's theorem | định lý Euler / định lý Fermat | a^φ(n) ≡ 1 / a^(p−1) ≡ 1 |
| primitive root | căn nguyên thủy | phần tử sinh của ℤₙ* |
| cyclic group | nhóm cyclic | nhóm có phần tử sinh |
| discrete logarithm (index) | logarit rời rạc (chỉ số) | z với gᶻ ≡ a |
| nontrivial square root of 1 | căn bậc hai không tầm thường của 1 | x² ≡ 1, x ≢ ±1 |
| modular exponentiation | lũy thừa modulo | aᵇ mod n |
| repeated squaring | bình phương lặp | kỹ thuật tính lũy thừa theo bit của số mũ |
| public-key cryptosystem | hệ mật mã khóa công khai | khóa mã hóa công khai, khóa giải mã bí mật |
| public key / secret key | khóa công khai / khóa bí mật | P và S |
| ciphertext | bản mã | C = P(M) |
| eavesdropper | kẻ nghe lén | người bắt được bản mã trên kênh |
| digital signature | chữ ký số | σ = S_A(M′), kiểm tra bằng P_A |
| RSA public-key cryptosystem | hệ mật mã khóa công khai RSA | Rivest–Shamir–Adleman |
| hybrid (key-management) mode | chế độ lai (quản lý khóa) | RSA chỉ mã hóa khóa của hệ mã nhanh |
| collision-resistant hash function | hàm băm chống va chạm | khó tìm M ≠ M′ với h(M) = h(M′) |
| certificate / trusted authority | chứng chỉ / cơ quan đáng tin cậy | thông điệp do T ký xác nhận khóa công khai |
| prime distribution function π(n) | hàm phân bố số nguyên tố | số số nguyên tố ≤ n |
| prime number theorem | định lý số nguyên tố | π(n) ~ n/ln n |
| trial division | chia thử | chia cho 2..⌊√n⌋ |
| base-a pseudoprime | giả nguyên tố cơ số a | hợp số với a^(n−1) ≡ 1 |
| Carmichael number | số Carmichael | hợp số lừa phép thử Fermat với mọi a ∈ ℤₙ* |
| witness (to compositeness) | bằng chứng (hợp số) | a làm WITNESS(a, n) = TRUE |
| nonwitness | không bằng chứng | a không chứng minh được n hợp số |
| acceptable pair | cặp chấp nhận được | (ν, j) với ν^(2ʲu) ≡ −1 |
| Miller-Rabin primality test | phép thử nguyên tố Miller-Rabin | phép thử ngẫu nhiên, sai ≤ 2⁻ˢ |
| integer factorization | phân tích số nguyên ra thừa số | tìm các thừa số nguyên tố |
| Pollard's rho heuristic | heuristic rho của Pollard | tìm thừa số p sau Θ(√p) bước |
| tail / cycle (of the rho) | đuôi / chu trình (của chữ ρ) | phần trước khi lặp / phần lặp |
| birthday paradox | nghịch lý ngày sinh | Θ(√n) lần chọn là có trùng |
| binary gcd algorithm | thuật toán gcd nhị phân | gcd chỉ dùng trừ, chẵn lẻ, chia đôi |
| quadratic residue | thặng dư bậc hai | a là bình phương modulo p |
| Legendre symbol | ký hiệu Legendre | (a/p) = ±1 |
| least common multiple (lcm) | bội chung nhỏ nhất | bội không âm nhỏ nhất của mọi aᵢ |
| number-field sieve | sàng trường số | thuật toán phân tích tổng quát tốt nhất |
| elliptic-curve method | phương pháp đường cong elliptic | tìm thừa số nhỏ nhanh |

## Câu nói đáng nhớ

> "Number theory was once viewed as a beautiful but largely useless subject in pure mathematics." — mở đầu Chương 31
>
> *Dịch: Lý thuyết số từng bị coi là một môn toán thuần túy đẹp đẽ nhưng phần lớn vô dụng.*

> "These schemes are feasible because we can find large primes easily, and they are secure because we do not know how to factor the product of large primes … efficiently." — mở đầu Chương 31
>
> *Dịch: Các lược đồ này khả thi vì ta tìm được số nguyên tố lớn dễ dàng, và an toàn vì ta không biết cách phân tích hiệu quả tích của các số nguyên tố lớn.*

> "It is a curious fact that factoring is one problem people may wish to be intractable, since the security of RSA depends on the difficulty of factoring large integers." — mở đầu Chương 31
>
> *Dịch: Có một điều kỳ lạ là phân tích thừa số là bài toán mà người ta có thể mong nó khó giải, vì độ an toàn của RSA phụ thuộc vào độ khó của việc phân tích số nguyên lớn.*

> "In this chapter, a 'large input' typically means an input containing 'large integers' rather than an input containing 'many integers' (as for sorting)." — phần mở đầu, kích thước đầu vào
>
> *Dịch: Trong chương này, "đầu vào lớn" thường nghĩa là đầu vào chứa "số nguyên lớn" chứ không phải đầu vào chứa "nhiều số nguyên" (như với sắp xếp).*

> "It is perhaps surprising that it is much easier to tell whether or not a given number is prime than it is to determine the prime factorization of the number if it is not prime." — Mục 31.8
>
> *Dịch: Có lẽ đáng ngạc nhiên là xác định một số có nguyên tố hay không dễ hơn nhiều so với tìm phân tích thừa số nguyên tố của nó khi nó không nguyên tố.*

> "Unlike PSEUDOPRIME, however, the chance of error does not depend on n; there are no bad inputs for this procedure." — Mục 31.8, tỉ lệ sai của Miller-Rabin
>
> *Dịch: Tuy nhiên, khác với PSEUDOPRIME, khả năng sai không phụ thuộc vào n; không có đầu vào xấu nào cho thủ tục này.*

> "Euclid's algorithm may hold the honor of being the oldest nontrivial algorithm; it is rivaled only by an algorithm for multiplication known to the ancient Egyptians." — Ghi chú chương
>
> *Dịch: Thuật toán Euclid có thể giữ danh hiệu thuật toán không tầm thường cổ nhất; chỉ có một thuật toán nhân mà người Ai Cập cổ biết là sánh được với nó.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: một chương "từ tiên đề tới ứng dụng" hoàn chỉnh

Chương dựng một chuỗi suy luận khép kín hiếm thấy trong sách giáo khoa thuật toán: từ một định lý duy nhất (gcd là tổ hợp tuyến tính dương nhỏ nhất) suy ra Euclid mở rộng, nghịch đảo, phương trình đồng dư, định lý số dư Trung Hoa; từ một khuôn duy nhất (nhóm hữu hạn và định lý Lagrange) suy ra Euler, Fermat và cận (n − 1)/2 của Miller-Rabin; rồi ghép tất cả vào RSA. Mỗi công cụ được dùng lại ít nhất hai lần ở chỗ khác (ví dụ định lý số dư Trung Hoa xuất hiện trong chứng minh RSA, trong Trường hợp 2 của Định lý 31.38, và trong lời giải thích hình ρ). Người đọc thấy rõ vì sao "lý thuyết số thuần túy" lại có giá trị kỹ thuật.

### Điểm mạnh: phân tích Euclid qua số Fibonacci và phân tích Bayes cho Miller-Rabin

Hai phân tích "đẹp" của chương: định lý Lamé cho cận chặt (đầu vào xấu nhất cụ thể là hai số Fibonacci liên tiếp), và đoạn dùng định lý Bayes để chỉ ra rằng "xác suất sai ≤ 2⁻ˢ" không đồng nghĩa "xác suất n nguyên tố ≥ 1 − 2⁻ˢ" khi n chọn ngẫu nhiên — một sai lầm thống kê phổ biến (bỏ quên xác suất tiên nghiệm) được sửa ngay trong ngữ cảnh thuật toán.

### Điểm yếu và chỗ đơn giản hóa

- **Nhiều định lý then chốt không được chứng minh:** định lý Lagrange, Định lý 31.32 (khi nào ℤₙ* cyclic, dùng cốt yếu trong Trường hợp 2 của Định lý 31.38), công thức φ(n), định lý số nguyên tố. Người đọc phải tin sách ở chính những bước khó nhất.
- **Mô hình chi phí Θ(β²) cho phép nhân đã cũ:** sách nhắc phương pháp nhanh nhất là Θ(β lg β lg lg β) (Schönhage–Strassen); theo hiểu biết của người tổng hợp, năm 2019 Harvey và van der Hoeven đạt O(β lg β). Tuy vậy với cỡ khóa RSA (vài nghìn bit), Karatsuba và cách viết tay vẫn thống trị thực tế, đúng như sách nói.
- **RSA được trình bày ở dạng "sách giáo khoa" (textbook RSA):** không có đệm ngẫu nhiên, tất định, có tính nhân. Sách có nhắc trong Ghi chú chương rằng cài đặt hiện đại dùng "những cải tiến đáng kể" và nhắc Goldwasser–Micali, nhưng không cảnh báo trực tiếp rằng dùng nguyên văn công thức (31.37) là không an toàn (ví dụ thông điệp nhỏ với e = 3 có Mᵉ < n thì lấy căn bậc ba thường là giải được — theo hiểu biết của người tổng hợp).
- **Mục 31.9 chỉ là heuristic:** cả thời gian lẫn sự thành công của rho Pollard không được chứng minh; các thuật toán phân tích thực sự mạnh (sàng bậc hai, sàng trường số, đường cong elliptic) chỉ được nhắc tên trong Ghi chú chương.
- **Số liệu thời sự đã cũ:** "RSA moduli … 768 to 2048 bits" (2009) và "after two decades of research" (thực ra hơn ba thập kỷ — xem khối Lưu ý). Theo hiểu biết của người tổng hợp, RSA-768 được phân tích công khai cuối năm 2009 và RSA-250 (829 bit) năm 2020; khuyến nghị hiện nay tối thiểu 2048 bit.
- **Không nhắc tới máy tính lượng tử:** theo hiểu biết của người tổng hợp, thuật toán Shor (1994) phân tích thừa số và tính logarit rời rạc trong thời gian đa thức trên máy tính lượng tử, nên toàn bộ "khoảng cách dễ/khó" mà chương dựa vào chỉ đúng với máy tính cổ điển; đây là động lực của mật mã hậu lượng tử hiện nay.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: thư viện mật mã thực tế dùng đúng các thủ tục của chương nhưng với nhiều tinh chỉnh: lũy thừa modulo dùng cửa sổ trượt và phép nhân Montgomery, viết theo kiểu thời gian hằng để chống tấn công kênh kề; giải mã RSA dùng định lý số dư Trung Hoa (nhanh khoảng 4 lần); sinh số nguyên tố dùng sàng các số nguyên tố nhỏ rồi Miller-Rabin (và thường thêm phép thử Lucas mạnh — tổ hợp "Baillie–PSW" chưa có phản ví dụ được biết); RSA luôn đi kèm đệm OAEP (mã hóa) hoặc PSS (chữ ký) và chế độ lai với AES; khóa công khai được phân phối qua hạ tầng chứng chỉ X.509 — chính ý "certificate" và "trusted authority" của sách. Trong trao đổi khóa, đường cong elliptic đã thay RSA vì khóa ngắn hơn nhiều với cùng độ an toàn.

### Liên hệ các chương khác

- Chương 3 ([C03-tang-truong-cua-ham.md](C03-tang-truong-cua-ham.md)): định nghĩa a mod n (công thức (3.8)), đồng dư, số Fibonacci (3.22) và tỉ số vàng (3.24) — dùng trực tiếp trong Mục 31.1–31.2.
- Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)): RANDOM, thuật toán ngẫu nhiên, nghịch lý ngày sinh (Mục 5.4.1) cho thời gian Θ(√p) của rho Pollard.
- Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)): ghi nhớ (memoization) trong Problem 31-3(b).
- Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)): thủ tục FIB mà Problem 31-3(a) nhắc tới.
- Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)): FFT dùng căn nguyên thủy của đơn vị — tương tự căn nguyên thủy modulo n; nhân số nguyên lớn nhanh (phần mở đầu chương này) dựa trên FFT; biến đổi số học (number-theoretic transform) là FFT trong ℤₚ.
- Chương 32 ([C32-so-khop-chuoi.md](C32-so-khop-chuoi.md)): Rabin-Karp dùng số học modulo một số nguyên tố, và phân tích xác suất va chạm của nó cũng dựa trên việc số nguyên tố "đủ nhiều".
- Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)): phân tích thừa số thuộc NP (và co-NP) nhưng không được biết là NP-đầy đủ — khác với các bài toán NP-đầy đủ của chương đó; thử nguyên tố thuộc P (AKS).
- Phụ lục C ([PC-dem-va-xac-suat.md](PC-dem-va-xac-suat.md)): phép thử Bernoulli, phân phối hình học (C.32), định lý Bayes (C.18) dùng ở Mục 31.8.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** viết gcd đệ quy và lặp, giải thích vì sao O(log); tính lũy thừa nhanh (`pow(x, n)` với n âm, lũy thừa modulo); tìm nghịch đảo modulo; giải thích ý tưởng RSA và chữ ký số ở mức khái niệm; câu hỏi "kiểm tra số nguyên tố" — chia thử tới √n cho số nhỏ, Miller-Rabin cho số lớn.
- **Lập trình thi đấu:** đây là "bộ đồ nghề" chuẩn: Euclid mở rộng, nghịch đảo modulo 10⁹ + 7 bằng định lý Fermat (a^(p−2)), định lý số dư Trung Hoa (kể cả bản tổng quát khi modulus không nguyên tố cùng nhau), Miller-Rabin tất định cho số 64 bit (với một tập cơ số cố định — theo hiểu biết của người tổng hợp, 12 số nguyên tố đầu đủ cho mọi n < 3,3 · 10²⁴), rho Pollard để phân tích số tới 10¹⁸, lũy thừa ma trận cho truy hồi tuyến tính (Problem 31-3(c)).
- **Kỹ thuật phần mềm:** không tự cài mật mã; dùng thư viện đã kiểm định. Nhưng hiểu chương này giúp đọc đúng các lựa chọn cấu hình (độ dài khóa, số vòng Miller-Rabin, vì sao cần đệm, vì sao giải mã RSA chậm hơn mã hóa nhiều: e nhỏ còn d cỡ n), và giúp tránh lỗi tràn số khi nhân modulo (luôn lấy mod sau mỗi phép nhân, dùng số 128 bit hoặc nhân Montgomery khi modulus gần 2⁶⁴).

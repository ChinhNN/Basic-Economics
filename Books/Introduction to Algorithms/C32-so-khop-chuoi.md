# Chương 32 — So khớp chuỗi (String Matching)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VII "Selected Topics", Chương 32 "String Matching", trang 985–1013.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Phần VII gom các chủ đề chọn lọc, mỗi chương dùng lại công cụ của các phần trước cho một miền bài toán cụ thể. Chương 32 dựa trên: phân tích thuật toán cơ bản và bất biến vòng lặp của Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)); băm bằng phép chia lấy dư và giả định "băm như ánh xạ ngẫu nhiên" của Chương 11 ([C11-bang-bam.md](C11-bang-bam.md)), là nền của thuật toán Rabin-Karp; phân tích khấu hao theo phương pháp gộp và phương pháp thế năng của Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)), dùng để chứng minh KMP chạy tuyến tính; quy tắc Horner của Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)); đồng dư, số nguyên tố và lũy thừa theo modulo của Chương 31 ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)), ngay trước chương này. Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)) đã gặp một bài toán khác trên chuỗi là dãy con chung dài nhất; Chương 32 thì tìm *chuỗi con liên tiếp* trùng khớp hoàn toàn. Chương 33 ([C33-hinh-hoc-tinh-toan.md](C33-hinh-hoc-tinh-toan.md)) chuyển sang hình học tính toán; Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)) bàn tới các bài toán khó, trái ngược với so khớp chuỗi là bài toán giải được trong thời gian tuyến tính.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **bài toán tìm mọi vị trí xuất hiện của mẫu P độ dài m trong văn bản T độ dài n giải được trong thời gian tuyến tính Θ(n + m), và chìa khoá là tiền xử lý mẫu để không bao giờ phải đọc lại văn bản: thuật toán ngây thơ lãng phí vì quên mọi thông tin đã thu được khi chuyển sang độ dịch kế tiếp; ôtômat hữu hạn ghi nhớ thông tin đó dưới dạng một trạng thái duy nhất (độ dài của tiền tố dài nhất của P vừa khớp với phần cuối văn bản đã đọc); thuật toán Knuth-Morris-Pratt (KMP) đạt cùng hiệu quả mà chỉ cần một mảng π độ dài m thay cho bảng chuyển trạng thái cỡ m|Σ|.** Phần mở đầu định nghĩa bài toán (độ dịch hợp lệ s: T[s + 1..s + m] = P[1..m]), bảng so sánh bốn thuật toán, ký hiệu tiền tố ⊏ và hậu tố ⊐, và Bổ đề 32.1 về hai hậu tố của cùng một chuỗi. Mục 32.1 trình bày thuật toán ngây thơ O((n − m + 1)m), chặt trong trường hợp xấu nhất với T = aⁿ, P = aᵐ. Mục 32.2 trình bày Rabin-Karp: coi mỗi cửa sổ m ký tự là một số, cập nhật giá trị cửa sổ trong O(1) khi trượt, làm việc theo modulo một số nguyên tố q, chỉ kiểm tra từng ký tự khi giá trị băm trùng; xấu nhất vẫn Θ((n − m + 1)m), nhưng kỳ vọng O(n + m) khi có ít độ dịch hợp lệ và q ≥ m. Mục 32.3 xây ôtômat so khớp chuỗi với δ(q, a) = σ(P_q a), chứng minh qua Bổ đề 32.2, 32.3 và Định lý 32.4 rằng ôtômat luôn ở trạng thái σ(T_i); khớp Θ(n), tiền xử lý O(m³|Σ|) bằng cách tính trực tiếp (có thể giảm xuống O(m|Σ|)). Mục ★32.4 trình bày KMP: hàm tiền tố π[q] là độ dài tiền tố dài nhất của P đồng thời là hậu tố thực sự của P_q; COMPUTE-PREFIX-FUNCTION chạy Θ(m) và KMP-MATCHER chạy Θ(n) nhờ phân tích khấu hao; tính đúng được chứng minh qua Bổ đề 32.5, 32.6, Hệ quả 32.7 và lập luận rằng KMP mô phỏng chính xác ôtômat.

> **Lưu ý:**
> - **Mục có dấu sao (★):** Mục 32.4 "The Knuth-Morris-Pratt algorithm" có dấu sao trong sách (mục nâng cao, có thể bỏ qua khi đọc lần đầu). Bài tập có dấu sao: Exercise 32.3-4 và Exercise 32.4-8.
> - **Lớp chữ PDF hỏng toàn bộ ký hiệu toán của chương:** Σ thành `†`, Θ thành `‚`, dấu trừ thành `/NUL` (ví dụ `n/NUL m` là n − m), ký hiệu tiền tố ⊏ thành `❁`, ký hiệu hậu tố ⊐ thành `=` (rất dễ đọc nhầm thành dấu bằng), dấu ≤ và ≠ mất hẳn (`m  n` là m ≤ n), chữ σ, δ, φ, π lần lượt mất hoặc thành `ı`, `.`, ký tự lạ; `TŒ 1::n` là T[1..n]; chỉ số dưới như P_q, T_i, t_s bị vỡ thành chữ thường liền nhau. Mọi pseudocode (NAIVE-STRING-MATCHER, RABIN-KARP-MATCHER, FINITE-AUTOMATON-MATCHER, COMPUTE-TRANSITION-FUNCTION, KMP-MATCHER, COMPUTE-PREFIX-FUNCTION, REPETITION-MATCHER), công thức (32.1)–(32.9), các bổ đề và Hình 32.1–32.11 trong bản tổng hợp này được đối chiếu với ảnh trang 985–1013 (đã xem ảnh của tất cả các trang).
> - **Chỗ sách viết chưa chặt (nhận xét của người tổng hợp):**
>   - Trang 1011, trường hợp σ(T_i) = 0 trong chứng minh tính đúng của KMP, sách viết "although P_q ⊐ T_i for every q ∈ π\*[q′]". Theo lập luận, điều đúng là P_q ⊐ T_{i−1} (vì q′ = σ(T_{i−1}) nên P_{q′} ⊐ T_{i−1}, và mọi P_q với q ∈ π\*[q′] là hậu tố của P_{q′}). Viết "T_i" ở đây là sai chỉ số; ý của câu (vòng while đi qua mọi trạng thái của π\*[q′] mà không tìm được q nào có P[q + 1] = T[i]) vẫn đúng.
>   - Định nghĩa π\*[q] (trang 1007) nói dãy "dừng khi gặp π^(t)[q] = 0", nhưng không nói rõ 0 có thuộc tập hay không; từ Bổ đề 32.5 và ví dụ π\*[5] = {3, 1, 0} thì 0 thuộc tập. Bản tổng hợp ghi rõ điều này.
>   - Chú thích Hình 32.6 viết "shown blackend" — lỗi chính tả của "blackened" (tô đen); không ảnh hưởng nội dung.
>   - Trong COMPUTE-TRANSITION-FUNCTION, dòng 4 gán k = min(m + 1, q + 2), còn lời giải thích nói giá trị lớn nhất có thể của k là min(m, q + 1). Hai cách viết khớp nhau vì vòng repeat giảm k trước khi kiểm tra; người đọc dễ tưởng mâu thuẫn.
>   - Người tổng hợp không chắc các chỗ trên có nằm trong danh sách lỗi chính thức (errata) của ấn bản 3 hay không — theo hiểu biết của người tổng hợp, không tra cứu.
> - **Mọi ví dụ chạy tay trong sách đã được tự kiểm tra lại và đúng:** ví dụ P = abaa trong T = abcabaabcabac (độ dịch hợp lệ duy nhất s = 3); bốn lần đặt mẫu aab lên acaabc (hợp lệ ở s = 2); mười lăm giá trị cửa sổ theo modulo 13 của văn bản 2359023141526739921 (8, 9, 3, 11, 0, 1, 7, 8, 4, 5, 10, 11, 7, 9, 11) và phép tính 14152 ≡ (7 − 3·3)·10 + 2 ≡ 8 (mod 13); bảng chuyển trạng thái 8 × 3 của ôtômat cho ababaca và dãy trạng thái 0 1 2 3 4 5 4 5 6 7 2 3 trên abababacaba; ôtômat hai trạng thái trên abaaa và abbaa; hàm tiền tố 0 0 1 2 3 0 1 của ababaca và π\*[5] = {3, 1, 0}; ví dụ KMP chuyển từ trạng thái 5 với ký tự c, b, a.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương So khớp chuỗi vẫn là Chương 32, giữ bốn mục thuật toán ngây thơ, Rabin-Karp, ôtômat hữu hạn và KMP, và thêm một mục mới 32.5 về mảng hậu tố (suffix arrays) kèm mảng tiền tố chung dài nhất (LCP). Như ở cả cuốn ấn bản 4, thuộc tính `T.length`, `P.length` được bỏ, độ dài được truyền như tham số. Các khác biệt nhỏ hơn về bài tập và lời văn, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 32.1, trang 985–987) — bài toán, bốn thuật toán, ký hiệu

```text
       Bài toán so khớp chuỗi:
       văn bản T[1..n], mẫu P[1..m] với m ≤ n, ký tự thuộc bảng chữ hữu hạn Σ
                                │
                                ▼
       s là ĐỘ DỊCH HỢP LỆ (valid shift) nếu 0 ≤ s ≤ n − m và
       T[s+1..s+m] = P[1..m]   (P xuất hiện bắt đầu tại vị trí s + 1)
       Yêu cầu: tìm MỌI độ dịch hợp lệ
       Ví dụ: P = abaa, T = abcabaabcabac ⇒ chỉ s = 3
                                │
                                ▼
       Bốn thuật toán của chương:
       ┌────────────────────┬──────────────────┬───────────────────┐
       │ Thuật toán         │ Tiền xử lý       │ Khớp              │
       ├────────────────────┼──────────────────┼───────────────────┤
       │ Ngây thơ (32.1)    │ 0                │ O((n − m + 1)m)   │
       │ Rabin-Karp (32.2)  │ Θ(m)             │ O((n − m + 1)m)   │
       │ Ôtômat hữu hạn     │ O(m|Σ|)          │ Θ(n)              │
       │   (32.3)           │                  │                   │
       │ Knuth-Morris-Pratt │ Θ(m)             │ Θ(n)              │
       │   (★32.4)          │                  │                   │
       └────────────────────┴──────────────────┴───────────────────┘
       Tổng thời gian = tiền xử lý + khớp
                                │
                                ▼
       Ký hiệu: Σ* là tập mọi chuỗi hữu hạn; ε là chuỗi rỗng; |x| là độ dài;
       xy là nối chuỗi; w ⊏ x: w là TIỀN TỐ của x; w ⊐ x: w là HẬU TỐ của x
       P_k = P[1..k] (k ký tự đầu), T_k tương tự; bài toán trở thành:
       tìm mọi s với 0 ≤ s ≤ n − m và P ⊐ T_{s+m}
                                │
                                ▼
       Bổ đề 32.1 (hai hậu tố chồng nhau): nếu x ⊐ z và y ⊐ z thì
       |x| ≤ |y| ⇒ x ⊐ y;  |x| ≥ |y| ⇒ y ⊐ x;  |x| = |y| ⇒ x = y
                                │
                                ▼
       Quy ước chi phí: phép thử "x == y" trên hai chuỗi cùng độ dài tốn
       Θ(t + 1), t là độ dài tiền tố chung dài nhất (so từ trái, dừng ở chỗ
       khác đầu tiên)
```

### Mục 32.1 — Thuật toán so khớp chuỗi ngây thơ (The naive string-matching algorithm, trang 988–990)

```text
       NAIVE-STRING-MATCHER: với mỗi s = 0, 1, …, n − m,
       kiểm tra P[1..m] == T[s+1..s+m]; nếu đúng thì in s
       (hình dung: trượt "khuôn" chứa P dọc theo T)
                                │
                                ▼
       Ví dụ P = aab, T = acaabc:
       s = 0: a=a, a≠c → sai      s = 1: a≠c → sai
       s = 2: aab = aab → HỢP LỆ  s = 3: a=a, a≠b → sai
                                │
                                ▼
       Thời gian O((n − m + 1)m), chặt khi T = aⁿ, P = aᵐ
       (mọi độ dịch đều hợp lệ, mỗi lần so đủ m ký tự);
       m = ⌊n/2⌋ cho Θ(n²); không tiền xử lý nên thời gian = thời gian khớp
                                │
                                ▼
       Điểm yếu: bỏ qua thông tin về văn bản thu được ở độ dịch s khi xét
       độ dịch khác. Ví dụ P = aaab, s = 0 hợp lệ ⇒ T[4] = b ⇒ s = 1, 2, 3
       chắc chắn không hợp lệ — các mục sau tận dụng loại thông tin này
```

### Mục 32.2 — Thuật toán Rabin-Karp (The Rabin-Karp algorithm, trang 990–995)

```text
       Coi mỗi ký tự là một chữ số cơ số d = |Σ| (ví dụ thập phân, d = 10);
       chuỗi k ký tự liên tiếp là một số k chữ số
       p = giá trị của P[1..m];  t_s = giá trị của T[s+1..s+m]
       s hợp lệ ⇔ t_s = p
                                │
                                ▼
       Tính p trong Θ(m) bằng quy tắc Horner:
       p = P[m] + 10(P[m−1] + 10(P[m−2] + … + 10(P[2] + 10P[1])…))
       t₀ tương tự trong Θ(m)
                                │
                                ▼
       Trượt cửa sổ trong O(1):                                    (32.1)
       t_{s+1} = 10(t_s − 10^{m−1}·T[s+1]) + T[s+m+1]
       (bỏ chữ số đầu, dịch trái một chữ số, thêm chữ số cuối mới)
       Ví dụ m = 5, t_s = 31415, chữ số mới 2: t_{s+1} = 14152
                                │
                                ▼
       Vấn đề: p, t_s có m chữ số, quá lớn cho một phép toán O(1)
       ⇒ làm việc theo modulo một số nguyên tố q (dq vừa một từ máy):  (32.2)
       t_{s+1} = (d(t_s − T[s+1]·h) + T[s+m+1]) mod q,  h ≡ d^{m−1} (mod q)
                                │
                                ▼
       t_s ≢ p (mod q) ⇒ chắc chắn s KHÔNG hợp lệ (loại nhanh)
       t_s ≡ p (mod q) ⇒ chưa chắc: phải so từng ký tự;
       nếu không khớp thì đó là TRÚNG GIẢ (spurious hit)
       Ví dụ q = 13, P = 31415 ≡ 7: văn bản 2359023141526739921 có hai cửa
       sổ ≡ 7: vị trí 7 (khớp thật), vị trí 13 (67399, trúng giả)
                                │
                                ▼
       RABIN-KARP-MATCHER: tiền xử lý Θ(m); khớp xấu nhất Θ((n−m+1)m)
       (ví dụ P = aᵐ, T = aⁿ: mọi độ dịch đều phải kiểm tra lại)
       Kỳ vọng (coi mod q như ánh xạ ngẫu nhiên, số trúng giả O(n/q)):
       O(n) + O(m(v + n/q)), v là số độ dịch hợp lệ
       ⇒ O(n + m) khi v = O(1) và q ≥ m
```

### Mục 32.3 — So khớp chuỗi bằng ôtômat hữu hạn (String matching with finite automata, trang 995–1002)

```text
       Ôtômat hữu hạn M = (Q, q₀, A, Σ, δ):
       tập trạng thái Q, trạng thái đầu q₀, tập trạng thái chấp nhận A ⊆ Q,
       bảng chữ đầu vào Σ, hàm chuyển δ: Q × Σ → Q
       Hàm trạng thái cuối φ: φ(ε) = q₀, φ(wa) = δ(φ(w), a);
       M chấp nhận w ⇔ φ(w) ∈ A
                                │
                                ▼
       Hàm hậu tố σ của mẫu P:                                      (32.3)
       σ(x) = max{k : P_k ⊐ x} = độ dài tiền tố dài nhất của P là hậu tố của x
       Ví dụ P = ab: σ(ε) = 0, σ(ccaca) = 1, σ(ccab) = 2
                                │
                                ▼
       ÔTÔMAT SO KHỚP CHUỖI của P[1..m]:
       Q = {0, 1, …, m}, q₀ = 0, A = {m}
       δ(q, a) = σ(P_q a)                                           (32.4)
       · a = P[q+1]: đi tiếp dọc "xương sống", δ(q, a) = q + 1
       · a ≠ P[q+1]: lùi về tiền tố ngắn hơn của P là hậu tố của P_q a
                                │
                                ▼
       FINITE-AUTOMATON-MATCHER: q = 0; với i = 1..n: q = δ(q, T[i]);
       nếu q = m thì in độ dịch i − m.   Thời gian khớp Θ(n)
       Ví dụ P = ababaca, T = abababacaba:
       trạng thái 1 2 3 4 5 4 5 6 7 2 3 ⇒ một lần khớp kết thúc ở vị trí 9
                                │
                                ▼
       Tính đúng:
       Bổ đề 32.2: σ(xa) ≤ σ(x) + 1
       Bổ đề 32.3: q = σ(x) ⇒ σ(xa) = σ(P_q a)
       Định lý 32.4: φ(T_i) = σ(T_i) với mọi i = 0..n (quy nạp theo i)  (32.5)
       ⇒ ôtômat ở trạng thái m đúng khi vừa đọc xong một lần xuất hiện của P
                                │
                                ▼
       COMPUTE-TRANSITION-FUNCTION: với mỗi q, mỗi a, thử k từ min(m, q+1)
       giảm dần tới khi P_k ⊐ P_q a.   Thời gian O(m³|Σ|);
       cải tiến được còn O(m|Σ|) (Exercise 32.4-8)
```

### Mục ★32.4 — Thuật toán Knuth-Morris-Pratt (The Knuth-Morris-Pratt algorithm, trang 1002–1012)

```text
       Ý tưởng: bỏ hẳn bảng δ (cỡ Θ(m|Σ|)); dùng mảng phụ π[1..m] không phụ
       thuộc ký tự, tính trong Θ(m); tính δ "khi cần" (khấu hao O(1))
                                │
                                ▼
       Câu hỏi then chốt (32.6): đã biết P[1..q] = T[s+1..s+q]; độ dịch
       nhỏ nhất s′ > s nào có thể hợp lệ? Trả lời: s′ = s + (q − k), với k
       là độ dài lớn nhất < q sao cho P_k ⊐ P_q; ở s′ khỏi so lại k ký tự đầu
       Ví dụ P = ababaca, q = 5 ký tự khớp: k = 3 ⇒ s′ = s + 2
                                │
                                ▼
       HÀM TIỀN TỐ: π[q] = max{k : k < q và P_k ⊐ P_q}
       (tiền tố dài nhất của P là hậu tố THỰC SỰ của P_q)
       Ví dụ ababaca: π = 0 0 1 2 3 0 1
                                │
                                ▼
       KMP-MATCHER: q = số ký tự đã khớp; với mỗi T[i]:
       · khi q > 0 và P[q+1] ≠ T[i]: q = π[q]   (lùi)
       · nếu P[q+1] = T[i]: q = q + 1           (tiến)
       · nếu q = m: in độ dịch i − m, rồi q = π[q]
       COMPUTE-PREFIX-FUNCTION: cùng khuôn mẫu, khớp P với chính nó
                                │
                                ▼
       Thời gian (phân tích gộp): k (hoặc q) tăng tổng cộng ≤ m − 1 (≤ n)
       lần, mỗi lần lặp while làm giảm nó, nó không âm
       ⇒ COMPUTE-PREFIX-FUNCTION Θ(m), KMP-MATCHER Θ(n)
                                │
                                ▼
       Tính đúng của hàm tiền tố:
       π*[q] = {π[q], π[π[q]], …, 0}
       Bổ đề 32.5: π*[q] = {k : k < q và P_k ⊐ P_q}  (lặp π liệt kê ĐỦ)
       Bổ đề 32.6: π[q] > 0 ⇒ π[q] − 1 ∈ π*[q − 1]
       E_{q−1} = {k ∈ π*[q−1] : P[k+1] = P[q]}
       Hệ quả 32.7: π[q] = 0 nếu E_{q−1} rỗng, ngược lại 1 + max E_{q−1}
                                │
                                ▼
       Tính đúng của KMP: KMP mô phỏng đúng FINITE-AUTOMATON-MATCHER;
       sau mỗi vòng lặp, q = σ(T_i); xét ba trường hợp σ(T_i) = 0,
       σ(T_i) = q′ + 1, 0 < σ(T_i) ≤ q′
       Dòng 12 (q = π[q] sau khi khớp) cần để không đọc P[m + 1]
```

### Bài toán cuối chương (Problem 32-1, trang 1012–1013)

```text
       32-1 So khớp dựa trên thừa số lặp (repetition factor)
       yʳ = y nối với chính nó r lần; ρ(x) = r lớn nhất sao cho x = yʳ
                                │
                                ▼
       (a) tính ρ(P_i) cho mọi i = 1..m   (dùng hàm tiền tố: Θ(m))
       (b) ρ*(P) = max ρ(P_i); P nhị phân ngẫu nhiên ⇒ E[ρ*(P)] = O(1)
       (c) REPETITION-MATCHER (Galil–Seiferas) đúng, chạy O(ρ*(P)·n + m):
           khi không khớp sau q ký tự, dịch s thêm max(1, ⌈q/k⌉),
           k = 1 + ρ*(P), và so lại từ đầu mẫu
                                │
                                ▼
       Mở rộng ý tưởng này, Galil và Seiferas có thuật toán tuyến tính
       chỉ dùng thêm O(1) bộ nhớ ngoài P và T
```

### Ghi chú chương (Chapter notes, trang 1013)

```text
       Quan hệ giữa so khớp chuỗi và lý thuyết ôtômat hữu hạn:
       Aho, Hopcroft, Ullman
                                │
                                ▼
       KMP do Knuth và Pratt, và độc lập do Morris, phát minh;
       họ công bố chung
                                │
                                ▼
       Reingold, Urban, Gries: cách trình bày khác cho KMP
                                │
                                ▼
       Rabin-Karp do Karp và Rabin đề xuất
                                │
                                ▼
       Galil và Seiferas: thuật toán tất định tuyến tính chỉ dùng O(1)
       bộ nhớ ngoài phần chứa mẫu và văn bản
```

## Ba câu hỏi chương này trả lời

1. **Bài toán so khớp chuỗi là gì, và vì sao cách làm ngây thơ chậm?** Cho văn bản T[1..n] và mẫu P[1..m] (m ≤ n) trên bảng chữ hữu hạn Σ, tìm mọi độ dịch s với 0 ≤ s ≤ n − m sao cho T[s + 1..s + m] = P[1..m]. Thuật toán ngây thơ thử cả n − m + 1 độ dịch, mỗi độ dịch so tối đa m ký tự: O((n − m + 1)m), và chặn này đạt được khi T = aⁿ, P = aᵐ (với m = ⌊n/2⌋ là Θ(n²); ví dụ n = 1.000, m = 500 tốn 501 · 500 = 250.500 phép so ký tự). Nó chậm vì khi chuyển sang độ dịch mới, nó vứt bỏ mọi điều đã biết về văn bản: đã biết T[1..4] = aaab thì s = 1, 2, 3 không thể hợp lệ, nhưng nó vẫn thử lại. Trên văn bản và mẫu ngẫu nhiên thì nó lại khá nhanh: kỳ vọng ≤ 2(n − m + 1) phép so sánh với bảng chữ có ít nhất hai ký tự.
2. **Rabin-Karp dùng số học để tăng tốc thế nào, và giới hạn của nó ở đâu?** Coi mỗi cửa sổ m ký tự là một số cơ số d, cập nhật giá trị cửa sổ khi trượt một bước bằng công thức t_{s+1} = (d(t_s − T[s + 1]h) + T[s + m + 1]) mod q trong O(1), và so với p = P mod q; chỉ khi hai giá trị bằng nhau mới so từng ký tự. Với q = 13, P = 31415 có giá trị 7; trong văn bản 2359023141526739921 có hai cửa sổ cho 7: cửa sổ tại vị trí 7 là khớp thật, cửa sổ 67399 tại vị trí 13 là trúng giả. Xấu nhất vẫn Θ((n − m + 1)m) (khi rất nhiều độ dịch hợp lệ hoặc nhiều trúng giả), nhưng kỳ vọng O(n + m) nếu số lần khớp thật là hằng số và q ≥ m. Ưu điểm lớn: tổng quát hoá dễ sang tìm nhiều mẫu cùng lúc và mẫu hai chiều.
3. **Làm sao đạt thời gian tuyến tính, và KMP hơn ôtômat ở đâu?** Giữ một con số q = độ dài tiền tố dài nhất của P là hậu tố của phần văn bản đã đọc (σ(T_i)); khi đọc ký tự mới a, trạng thái mới là σ(P_q a) — chỉ phụ thuộc q và a, không cần nhìn lại văn bản (Bổ đề 32.3). Ôtômat tính sẵn mọi giá trị δ(q, a) = σ(P_q a) vào bảng (m + 1) × |Σ| rồi khớp đúng n bước. KMP chỉ tính mảng π[1..m] (π[q] là độ dài tiền tố dài nhất của P là hậu tố thực sự của P_q, ví dụ ababaca có π = 0 0 1 2 3 0 1) trong Θ(m), và khi ký tự không khớp thì lùi q theo dãy q, π[q], π[π[q]], … Mỗi bước lùi làm giảm q, mà q chỉ tăng nhiều nhất n lần, nên tổng số bước lùi ≤ n: thời gian khớp Θ(n), tổng Θ(n + m), không phụ thuộc kích thước bảng chữ.

## Khái niệm cần biết

- **Văn bản, mẫu, bảng chữ (text, pattern, alphabet):** văn bản là mảng ký tự T[1..n], mẫu là mảng P[1..m] với m ≤ n, các ký tự lấy từ một tập hữu hạn Σ gọi là bảng chữ. Ví dụ Σ = {0, 1} hoặc Σ = {a, b, …, z}; T = abcabaabcabac (n = 13), P = abaa (m = 4). Hai mảng ký tự này thường được gọi là chuỗi (strings). Quan trọng vì cả chương đo thời gian theo n, m và |Σ|.
- **Độ dịch hợp lệ (valid shift):** số nguyên s với 0 ≤ s ≤ n − m và T[s + 1..s + m] = P[1..m]; tương đương "P xuất hiện bắt đầu tại vị trí s + 1 của T". Độ dịch không thoả gọi là độ dịch không hợp lệ (invalid shift). Ví dụ trên: T[4..7] = abaa = P nên s = 3 hợp lệ, và đó là độ dịch hợp lệ duy nhất. Bài toán so khớp chuỗi là tìm *mọi* độ dịch hợp lệ.
- **Σ\* và chuỗi rỗng (empty string) ε:** Σ\* (đọc "sigma sao") là tập mọi chuỗi hữu hạn tạo từ Σ, kể cả chuỗi rỗng ε có độ dài 0. Ví dụ với Σ = {a, b}: ε, a, b, aa, ab, ba, bb, aaa, … đều thuộc Σ\*.
- **Độ dài và phép nối (length, concatenation):** |x| là số ký tự của x; xy là x nối với y, có độ dài |x| + |y|. Ví dụ x = ab, y = cca: xy = abcca, |xy| = 5.
- **Tiền tố và hậu tố (prefix, suffix):** w ⊏ x (w là tiền tố của x) nếu x = wy với y ∈ Σ\* nào đó; w ⊐ x (w là hậu tố của x) nếu x = yw. Khi đó |w| ≤ |x|. Ví dụ ab ⊏ abcca và cca ⊐ abcca. Chuỗi rỗng ε vừa là tiền tố vừa là hậu tố của mọi chuỗi. Với mọi chuỗi x, y và ký tự a: x ⊐ y khi và chỉ khi xa ⊐ ya. Cả ⊏ và ⊐ đều có tính bắc cầu. Hai quan hệ này là ngôn ngữ của mọi chứng minh trong chương.
- **Tiền tố thực sự / hậu tố thực sự (proper prefix / suffix):** tiền tố hay hậu tố khác chính chuỗi đó (ngắn hơn hẳn). Ví dụ các hậu tố thực sự của ababa là ε, a, ba, aba, baba. Hàm tiền tố π dùng hậu tố *thực sự* để π[q] < q.
- **P_k và T_k:** P_k = P[1..k] là k ký tự đầu của mẫu, T_k = T[1..k] là k ký tự đầu của văn bản; P₀ = ε, P_m = P. Ví dụ P = ababaca: P₃ = aba, P₅ = ababa. Dùng ký hiệu này, s hợp lệ khi và chỉ khi P ⊐ T_{s+m}.
- **Bổ đề hậu tố chồng nhau (overlapping-suffix lemma, Bổ đề 32.1):** nếu x và y cùng là hậu tố của z thì chuỗi ngắn hơn là hậu tố của chuỗi dài hơn (bằng nhau nếu cùng độ dài). Ví dụ z = ababa: x = ba và y = aba đều là hậu tố của z, |x| < |y| nên ba ⊐ aba — đúng. Dùng trong chứng minh Bổ đề 32.3 và 32.5.
- **Chi phí so sánh hai chuỗi:** phép thử "x == y" với hai chuỗi cùng độ dài so từ trái sang, dừng ở chỗ khác đầu tiên, tốn Θ(t + 1) với t là độ dài tiền tố chung dài nhất. Ví dụ so aab với aca: t = 1 (chỉ ký tự đầu giống), tốn 2 phép so ký tự. Số "+1" để tính cả trường hợp t = 0 (ký tự đầu đã khác nhưng phép so vẫn tốn thời gian).
- **Tiền xử lý và khớp (preprocessing, matching):** trừ thuật toán ngây thơ, mỗi thuật toán gồm pha tiền xử lý trên riêng mẫu P và pha khớp duyệt văn bản T. Tổng thời gian là tổng hai pha. Ví dụ KMP: tiền xử lý Θ(m) tính π, khớp Θ(n).
- **Giá trị số của cửa sổ (Rabin-Karp) p và t_s:** coi ký tự là chữ số cơ số d = |Σ|; p là giá trị của P[1..m], t_s là giá trị của T[s + 1..s + m]. Ví dụ Σ = {0, …, 9}, chuỗi 31415 tương ứng số 31.415. s hợp lệ khi và chỉ khi t_s = p.
- **Quy tắc Horner (Horner's rule):** tính giá trị đa thức/số nhiều chữ số bằng nhân rồi cộng lồng nhau: p = P[m] + 10(P[m − 1] + 10(P[m − 2] + … + 10(P[2] + 10P[1])…)). Ví dụ 31415 = (((3·10 + 1)·10 + 4)·10 + 1)·10 + 5: 3 → 31 → 314 → 3141 → 31415, tốn m − 1 phép nhân.
- **Băm cuộn (rolling hash) — công thức (32.1)/(32.2):** cập nhật t_{s+1} từ t_s trong O(1) bằng cách bỏ chữ số cao nhất, dịch trái, thêm chữ số mới. Ví dụ t_s = 31415, chữ số mới 2: 10 · (31415 − 10000 · 3) + 2 = 14152. Tên "băm cuộn" là tên thông dụng — theo hiểu biết của người tổng hợp; sách không đặt tên riêng.
- **Trúng giả (spurious hit):** độ dịch s có t_s ≡ p (mod q) nhưng T[s + 1..s + m] ≠ P. Ví dụ q = 13, P = 31415 ≡ 7, cửa sổ 67399 ≡ 7 (67399 = 13 · 5184 + 7) nhưng khác 31415. Phải kiểm tra từng ký tự để loại trúng giả; chọn q lớn để chúng hiếm.
- **Ôtômat hữu hạn (finite automaton):** bộ năm (Q, q₀, A, Σ, δ): tập trạng thái hữu hạn Q, trạng thái đầu q₀, tập trạng thái chấp nhận A ⊆ Q, bảng chữ đầu vào Σ, hàm chuyển δ: Q × Σ → Q. Đọc từng ký tự, chuyển trạng thái theo δ; chuỗi được chấp nhận nếu dừng ở trạng thái thuộc A. Ví dụ ôtômat hai trạng thái {0, 1}, chấp nhận các chuỗi kết thúc bằng một số lẻ chữ a: trên abaaa đi qua 0, 1, 0, 1, 0, 1, chấp nhận.
- **Hàm trạng thái cuối (final-state function) φ:** φ(w) là trạng thái ôtômat dừng ở sau khi đọc w; φ(ε) = q₀, φ(wa) = δ(φ(w), a). Ví dụ trên: φ(abbaa) = 0, nên abbaa bị từ chối.
- **Hàm hậu tố (suffix function) σ:** σ(x) là độ dài của tiền tố dài nhất của P đồng thời là hậu tố của x: σ(x) = max{k : P_k ⊐ x}. Ví dụ P = ab: σ(ε) = 0, σ(ccaca) = 1 (hậu tố a = P₁), σ(ccab) = 2. σ(x) = m khi và chỉ khi P ⊐ x; và x ⊐ y kéo theo σ(x) ≤ σ(y). Đây là đại lượng mà ôtômat và KMP duy trì.
- **Ôtômat so khớp chuỗi (string-matching automaton):** ôtômat có Q = {0, 1, …, m}, q₀ = 0, A = {m}, δ(q, a) = σ(P_q a). Trạng thái q nghĩa là "q ký tự cuối đã đọc trùng với P_q, và q lớn nhất có thể". Ví dụ P = ababaca: δ(5, c) = 6 (khớp tiếp), δ(5, b) = 4 (vì P₅b = ababab có hậu tố abab = P₄ là tiền tố dài nhất của P).
- **Xương sống của ôtômat (spine):** các cạnh q → q + 1 nhãn P[q + 1], ứng với khớp thành công. Các cạnh còn lại đi sang trái (về trạng thái ≤ q), ứng với không khớp.
- **Hàm tiền tố (prefix function) π:** với mẫu P[1..m], π[q] = max{k : k < q và P_k ⊐ P_q}, tức độ dài tiền tố dài nhất của P là hậu tố thực sự của P_q. Ví dụ P = ababaca: π[1..7] = 0, 0, 1, 2, 3, 0, 1 (π[5] = 3 vì aba vừa là tiền tố của P vừa là hậu tố của ababa). Đây là dữ liệu tiền xử lý duy nhất của KMP.
- **Lặp hàm tiền tố π\*[q]:** π\*[q] = {π[q], π[π[q]], π[π[π[q]]], …} dừng khi gặp 0 (và 0 thuộc tập). Ví dụ ababaca: π\*[5] = {3, 1, 0}. Bổ đề 32.5: π\*[q] liệt kê đúng mọi k < q với P_k ⊐ P_q, nên KMP khi lùi theo dãy này không bỏ sót ứng viên nào.
- **Phân tích khấu hao, phương pháp gộp và phương pháp thế năng (amortized analysis, aggregate method, potential method):** chặn tổng chi phí của cả dãy thao tác thay vì từng thao tác (Chương 17). Ở KMP: một lần đọc ký tự có thể lùi nhiều bước, nhưng tổng số bước lùi trên cả văn bản ≤ n. Ví dụ với P = aaab, T = aaaaaaaab (n = 9): vòng lặp while chỉ chạy 5 lần trên cả văn bản (xem ví dụ chạy tay ở mục KMP).
- **Thừa số lặp (repetition factor):** x có thừa số lặp r nếu x = yʳ (y nối với chính nó r lần) với r > 0; ρ(x) là r lớn nhất như vậy. Ví dụ (ab)³ = ababab, ρ(ababab) = 3; ρ(abab) = 2; ρ(ababa) = 1. Dùng trong Problem 32-1.

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 985–987)

#### Bài toán

Chương mở đầu bằng ứng dụng quen thuộc: chương trình soạn thảo văn bản thường phải tìm mọi chỗ xuất hiện của một mẫu trong văn bản — văn bản là tài liệu đang soạn, mẫu là một từ người dùng gõ vào. Thuật toán hiệu quả cho bài toán này, gọi là "so khớp chuỗi", làm chương trình phản hồi nhanh hơn nhiều. Ngoài ra, thuật toán so khớp chuỗi còn được dùng để tìm các mẫu cụ thể trong chuỗi DNA, và máy tìm kiếm Internet dùng chúng để tìm trang Web liên quan tới truy vấn.

Bài toán được hình thức hoá như sau. Văn bản là mảng T[1..n] độ dài n, mẫu là mảng P[1..m] độ dài m ≤ n. Các phần tử của P và T là ký tự thuộc một bảng chữ hữu hạn Σ, ví dụ Σ = {0, 1} hoặc Σ = {a, b, …, z}. Các mảng ký tự P và T thường được gọi là chuỗi ký tự.

Mẫu P **xuất hiện với độ dịch s** (occurs with shift s) trong văn bản T — tương đương, P **xuất hiện bắt đầu tại vị trí s + 1** của T — nếu 0 ≤ s ≤ n − m và T[s + 1..s + m] = P[1..m], tức T[s + j] = P[j] với 1 ≤ j ≤ m. Nếu P xuất hiện với độ dịch s thì s là **độ dịch hợp lệ** (valid shift), ngược lại s là **độ dịch không hợp lệ** (invalid shift). **Bài toán so khớp chuỗi** (string-matching problem) là bài toán tìm mọi độ dịch hợp lệ của một mẫu P cho trước trong một văn bản T cho trước.

Ví dụ (vẽ lại Hình 32.1 của sách): tìm P = abaa trong T = abcabaabcabac.

```text
vị trí:       1 2 3 4 5 6 7 8 9 10 11 12 13
văn bản T:    a b c a b a a b c a  b  a  c
                    │ │ │ │
mẫu P (s = 3):      a b a a
```

Mẫu xuất hiện đúng một lần, ở độ dịch s = 3 (bốn ký tự T[4..7] = abaa được nối bằng nét dọc với bốn ký tự của P và được tô đậm trong hình gốc). Kiểm tra (người tổng hợp): các độ dịch khác từ 0 tới 9 đều thất bại — ví dụ s = 0 cho abca, khác ở ký tự thứ ba; s = 8 cho caba; s = 9 cho abac, khác ở ký tự cuối.

#### Bốn thuật toán của chương

Bảng tổng hợp thời gian (chép lại Hình 32.2 của sách):

| Thuật toán | Thời gian tiền xử lý | Thời gian khớp |
|---|---|---|
| Ngây thơ (Naive) | 0 | O((n − m + 1)m) |
| Rabin-Karp | Θ(m) | O((n − m + 1)m) |
| Ôtômat hữu hạn (Finite automaton) | O(m\|Σ\|) | Θ(n) |
| Knuth-Morris-Pratt | Θ(m) | Θ(n) |

Trừ thuật toán vét cạn ngây thơ (ôn lại ở Mục 32.1), mỗi thuật toán của chương làm một bước tiền xử lý dựa trên mẫu rồi mới tìm mọi độ dịch hợp lệ; pha sau gọi là "khớp" (matching). Tổng thời gian là tổng thời gian tiền xử lý và thời gian khớp.

Mục 32.2 trình bày một thuật toán thú vị của Rabin và Karp. Thời gian xấu nhất Θ((n − m + 1)m) của nó không hơn phương pháp ngây thơ, nhưng trung bình và trong thực tế nó chạy tốt hơn nhiều, và tổng quát hoá đẹp sang các bài toán so khớp mẫu khác. Mục 32.3 mô tả thuật toán bắt đầu bằng việc dựng một ôtômat hữu hạn thiết kế riêng để tìm các lần xuất hiện của P; tiền xử lý O(m|Σ|) nhưng khớp chỉ Θ(n). Mục 32.4 trình bày thuật toán Knuth-Morris-Pratt (KMP), tương tự nhưng khéo léo hơn nhiều: cùng thời gian khớp Θ(n) và giảm tiền xử lý xuống Θ(m).

#### Ký hiệu và thuật ngữ

- Σ\* (đọc "sigma-star") là tập mọi chuỗi độ dài hữu hạn tạo từ các ký tự của Σ. Chương chỉ xét chuỗi hữu hạn. Chuỗi rỗng độ dài 0, ký hiệu ε, cũng thuộc Σ\*.
- Độ dài của chuỗi x ký hiệu |x|. Phép nối (concatenation) của x và y, ký hiệu xy, có độ dài |x| + |y|, gồm các ký tự của x rồi tới các ký tự của y.
- w là **tiền tố** (prefix) của x, ký hiệu w ⊏ x, nếu x = wy với y ∈ Σ\* nào đó. Khi đó |w| ≤ |x|. Tương tự, w là **hậu tố** (suffix) của x, ký hiệu w ⊐ x, nếu x = yw với y ∈ Σ\* nào đó; khi đó cũng có |w| ≤ |x|. Ví dụ ab ⊏ abcca và cca ⊐ abcca. Chuỗi rỗng ε vừa là hậu tố vừa là tiền tố của mọi chuỗi. Với mọi chuỗi x, y và ký tự a: x ⊐ y khi và chỉ khi xa ⊐ ya. Hai quan hệ ⊏ và ⊐ có tính bắc cầu.

**Bổ đề 32.1 (Bổ đề hậu tố chồng nhau — Overlapping-suffix lemma).** Giả sử x, y, z là các chuỗi với x ⊐ z và y ⊐ z. Nếu |x| ≤ |y| thì x ⊐ y. Nếu |x| ≥ |y| thì y ⊐ x. Nếu |x| = |y| thì x = y.

*Chứng minh.* Sách chứng minh bằng hình (Hình 32.3); vẽ lại và diễn giải bằng lời:

```text
(a) |x| ≤ |y|                (b) |x| ≥ |y|                (c) |x| = |y|
            ┌──x──┐                  ┌────x────┐                ┌───x───┐
  ┌────z────┴─────┤        ┌────z────┴─────────┤        ┌──z────┴───────┤
         ┌───y────┐                     ┌──y───┐               ┌───y───┐
  ⇓ x nằm gọn trong            ⇓ y nằm gọn trong            ⇓ x và y trùng
    phần cuối của y              phần cuối của x              khít nhau
       ┌──x──┐                    ┌────x────┐                ┌───x───┐
    ┌──y─────┤                       ┌──y───┤                ┌───y───┐
```

Cả x và y đều được canh phải với đầu cuối của z. Khi đó |x| ký tự cuối của z chính là x, và |y| ký tự cuối của z chính là y. Nếu |x| ≤ |y| thì |x| ký tự cuối của y cũng chính là |x| ký tự cuối của z, tức là x, nên x ⊐ y. Trường hợp (b) đối xứng. Trường hợp (c): cả hai đều là |x| ký tự cuối của z nên bằng nhau. ∎

Để gọn, ký hiệu P_k là tiền tố k ký tự P[1..k] của mẫu P[1..m]; như vậy P₀ = ε và P_m = P = P[1..m]. Tương tự T_k là tiền tố k ký tự của văn bản. Với ký hiệu này, bài toán so khớp chuỗi là tìm mọi s trong khoảng 0 ≤ s ≤ n − m sao cho P ⊐ T_{s+m}. (Kiểm tra với ví dụ trên: T₇ = abcabaa có hậu tố abaa = P, nên s + m = 7, s = 3.)

**Quy ước chi phí so sánh chuỗi.** Trong pseudocode, phép so sánh bằng nhau của hai chuỗi cùng độ dài được coi là một thao tác nguyên thuỷ. Nếu hai chuỗi được so từ trái sang phải và dừng ngay khi gặp chỗ khác nhau, ta giả định thời gian của phép thử là hàm tuyến tính của số ký tự khớp tìm được. Chính xác hơn, phép thử "x == y" tốn Θ(t + 1), trong đó t là độ dài của chuỗi z dài nhất với z ⊏ x và z ⊏ y. (Viết Θ(t + 1) thay vì Θ(t) để xử lý trường hợp t = 0: ký tự đầu tiên đã không khớp, nhưng phép so sánh vẫn tốn một lượng thời gian dương.)

### 2. Thuật toán so khớp chuỗi ngây thơ (32.1 The naive string-matching algorithm, trang 988–990)

Thuật toán ngây thơ tìm mọi độ dịch hợp lệ bằng một vòng lặp kiểm tra điều kiện P[1..m] = T[s + 1..s + m] với từng giá trị trong n − m + 1 giá trị có thể của s.

```text
NAIVE-STRING-MATCHER(T, P)
1  n = T.length
2  m = P.length
3  for s = 0 to n − m
4      if P[1..m] == T[s + 1..s + m]
5          print "Pattern occurs with shift" s
```

Có thể hình dung thủ tục như trượt một "khuôn" chứa mẫu dọc theo văn bản, ghi lại những độ dịch mà mọi ký tự trên khuôn trùng với ký tự tương ứng của văn bản. Vòng for ở dòng 3–5 xét tường minh từng độ dịch. Phép thử ở dòng 4 xác định độ dịch hiện tại có hợp lệ không; phép thử này ngầm chứa một vòng lặp so từng cặp ký tự tương ứng cho tới khi mọi vị trí đều khớp hoặc gặp một chỗ không khớp. Dòng 5 in mỗi độ dịch hợp lệ.

**Ví dụ chạy tay (vẽ lại Hình 32.4 của sách):** P = aab, T = acaabc (n = 6, m = 3), bốn độ dịch s = 0, 1, 2, 3:

| Độ dịch | Cửa sổ T[s+1..s+3] | So sánh | Kết quả |
|---|---|---|---|
| (a) s = 0 | a c a | a = a; a ≠ c (dừng ở ký tự thứ 2) | không hợp lệ, 2 phép so |
| (b) s = 1 | c a a | a ≠ c (dừng ở ký tự thứ 1) | không hợp lệ, 1 phép so |
| (c) s = 2 | a a b | a = a; a = a; b = b | **hợp lệ**, 3 phép so |
| (d) s = 3 | a b c | a = a; a ≠ b (dừng ở ký tự thứ 2) | không hợp lệ, 2 phép so |

Trong hình gốc, các vùng khớp được nối bằng nét dọc và tô đậm, chỗ không khớp đầu tiên được nối bằng nét gấp khúc. Thuật toán tìm được một lần xuất hiện, ở độ dịch s = 2. Tổng cộng 8 phép so ký tự (người tổng hợp đếm).

**Thời gian chạy.** NAIVE-STRING-MATCHER tốn O((n − m + 1)m), và chặn này chặt trong trường hợp xấu nhất. Ví dụ, xét văn bản aⁿ (chuỗi n chữ a) và mẫu aᵐ. Với mỗi giá trị trong n − m + 1 giá trị của s, vòng lặp ngầm ở dòng 4 phải so đủ m lần để xác nhận độ dịch. Thời gian xấu nhất vì vậy là Θ((n − m + 1)m), tức Θ(n²) nếu m = ⌊n/2⌋. (Kiểm tra: n = 10, m = 5: 6 độ dịch × 5 = 30 phép so; với n = 1.000, m = 500: 501 × 500 = 250.500.) Vì không có tiền xử lý, thời gian chạy của NAIVE-STRING-MATCHER bằng thời gian khớp của nó.

**Vì sao thuật toán ngây thơ không tối ưu.** NAIVE-STRING-MATCHER không phải thủ tục tối ưu cho bài toán này; chương sẽ chỉ ra KMP tốt hơn nhiều trong trường hợp xấu nhất. Thuật toán ngây thơ kém hiệu quả vì nó hoàn toàn bỏ qua thông tin thu được về văn bản ở một giá trị s khi xét các giá trị s khác. Thông tin ấy có thể rất có giá trị. Ví dụ, nếu P = aaab và ta thấy s = 0 hợp lệ, thì không độ dịch nào trong 1, 2, 3 hợp lệ, vì T[4] = b (ở độ dịch 1, 2, 3, ký tự T[4] phải khớp lần lượt với P[3], P[2], P[1], đều là a). Các mục sau khảo sát nhiều cách tận dụng hiệu quả loại thông tin này.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hàm tìm chuỗi con trong nhiều thư viện chuẩn (ví dụ `strstr` của C ở một số cài đặt cũ, `String.indexOf` của Java) từng dùng đúng thuật toán ngây thơ, vì với văn bản và mẫu "bình thường" nó rất nhanh (Exercise 32.1-3 chứng minh kỳ vọng ≤ 2 phép so mỗi độ dịch với chuỗi ngẫu nhiên) và không cần bộ nhớ phụ. Các thư viện hiện đại (glibc, Go, Rust) chuyển sang thuật toán "Two-Way" của Crochemore–Perrin, tuyến tính trong trường hợp xấu nhất và chỉ dùng O(1) bộ nhớ phụ — đúng hướng mà ghi chú chương nhắc tới qua thuật toán của Galil và Seiferas.

### 3. Thuật toán Rabin-Karp (32.2 The Rabin-Karp algorithm, trang 990–995)

Rabin và Karp đề xuất một thuật toán so khớp chuỗi chạy tốt trong thực tế và tổng quát hoá sang các thuật toán cho bài toán liên quan, như so khớp mẫu hai chiều. Thuật toán Rabin-Karp dùng Θ(m) thời gian tiền xử lý, thời gian xấu nhất là Θ((n − m + 1)m). Dựa trên một số giả định, thời gian trung bình của nó tốt hơn.

Thuật toán dùng các khái niệm số học sơ cấp như quan hệ đồng dư của hai số theo modulo một số thứ ba (định nghĩa ở Mục 31.1, Chương 31: a ≡ b (mod n) nghĩa là a mod n = b mod n).

#### Ý tưởng: coi chuỗi là số

Để trình bày, giả sử Σ = {0, 1, 2, …, 9}, mỗi ký tự là một chữ số thập phân. (Trường hợp tổng quát: coi mỗi ký tự là một chữ số trong hệ cơ số d, với d = |Σ|.) Khi đó một chuỗi k ký tự liên tiếp biểu diễn một số thập phân k chữ số; chuỗi ký tự 31415 tương ứng số 31.415. Vì ký tự đầu vào vừa được hiểu như ký hiệu đồ hoạ vừa như chữ số, trong mục này sách viết chúng như viết chữ số, bằng phông chữ thường.

Cho mẫu P[1..m], gọi p là giá trị thập phân tương ứng. Tương tự, cho văn bản T[1..n], gọi t_s là giá trị thập phân của chuỗi con độ dài m T[s + 1..s + m], với s = 0, 1, …, n − m. Hiển nhiên t_s = p khi và chỉ khi T[s + 1..s + m] = P[1..m]; vậy s là độ dịch hợp lệ khi và chỉ khi t_s = p. Nếu tính được p trong Θ(m) và mọi giá trị t_s trong tổng Θ(n − m + 1), ta tìm được mọi độ dịch hợp lệ trong Θ(m) + Θ(n − m + 1) = Θ(n) bằng cách so p với từng t_s. (Tạm thời chưa lo p và t_s có thể là số rất lớn.)

Chú thích của sách: viết Θ(n − m + 1) thay vì Θ(n − m) vì s nhận n − m + 1 giá trị khác nhau. Số "+1" có ý nghĩa tiệm cận: khi m = n, tính giá trị t_s duy nhất tốn Θ(1) chứ không phải Θ(0).

**Tính p bằng quy tắc Horner** (Mục 30.1) trong Θ(m):

```text
p = P[m] + 10 (P[m − 1] + 10 (P[m − 2] + ··· + 10 (P[2] + 10 P[1]) ···))
```

Tương tự tính t₀ từ T[1..m] trong Θ(m).

**Tính các giá trị còn lại t₁, t₂, …, t_{n−m} trong Θ(n − m):** quan sát rằng có thể tính t_{s+1} từ t_s trong thời gian hằng số, vì

```text
t_{s+1} = 10 (t_s − 10^{m−1} T[s + 1]) + T[s + m + 1]                (32.1)
```

Trừ 10^{m−1} T[s + 1] bỏ chữ số hàng cao nhất khỏi t_s; nhân kết quả với 10 dịch số sang trái một vị trí; cộng T[s + m + 1] đưa chữ số hàng thấp nhất mới vào. Ví dụ, nếu m = 5 và t_s = 31415, ta muốn bỏ chữ số hàng cao T[s + 1] = 3 và đưa vào chữ số hàng thấp mới (giả sử T[s + 5 + 1] = 2) để được

```text
t_{s+1} = 10 (31415 − 10000 · 3) + 2
        = 14152
```

Nếu tính trước hằng số 10^{m−1} (làm được trong O(lg m) bằng kỹ thuật lũy thừa nhanh của Mục 31.6, dù với ứng dụng này cách O(m) đơn giản là đủ), mỗi lần áp dụng (32.1) tốn một số hằng phép toán số học. Vậy tính p trong Θ(m), tính mọi t₀, t₁, …, t_{n−m} trong Θ(n − m + 1), và tìm mọi lần xuất hiện của P[1..m] trong T[1..n] với Θ(m) tiền xử lý và Θ(n − m + 1) thời gian khớp.

#### Làm việc theo modulo q

Tới đây ta cố ý bỏ qua một vấn đề: p và t_s có thể quá lớn để tính toán thuận tiện. Nếu P có m ký tự thì không thể giả định hợp lý rằng mỗi phép toán trên p (dài m chữ số) tốn "thời gian hằng số". May thay có cách giải đơn giản: tính p và các t_s **theo modulo một số q thích hợp**. Tính p mod q trong Θ(m) và mọi t_s mod q trong Θ(n − m + 1). Nếu chọn q là số nguyên tố sao cho 10q vừa một từ máy (computer word), mọi phép tính cần thiết đều làm được bằng số học độ chính xác đơn. Tổng quát, với bảng chữ d phần tử {0, 1, …, d − 1}, chọn q sao cho dq vừa một từ máy và sửa (32.1) để làm việc theo modulo q:

```text
t_{s+1} = (d (t_s − T[s + 1] h) + T[s + m + 1]) mod q                 (32.2)
```

trong đó h ≡ d^{m−1} (mod q) là giá trị của chữ số "1" ở vị trí hàng cao nhất của một cửa sổ văn bản m chữ số.

Làm việc theo modulo q không hoàn hảo: t_s ≡ p (mod q) **không** kéo theo t_s = p. Ngược lại, nếu t_s ≢ p (mod q) thì chắc chắn t_s ≠ p, nên s không hợp lệ. Vậy có thể dùng phép thử t_s ≡ p (mod q) như một phép thử nhanh để loại các độ dịch không hợp lệ. Mọi độ dịch s có t_s ≡ p (mod q) phải được kiểm tra thêm xem s có thật sự hợp lệ hay chỉ là **trúng giả** (spurious hit). Phép kiểm tra thêm này so tường minh P[1..m] = T[s + 1..s + m]. Nếu q đủ lớn, ta hy vọng trúng giả đủ hiếm để chi phí kiểm tra thêm thấp.

**Ví dụ (chép lại Hình 32.5 của sách).** Mỗi ký tự là một chữ số thập phân, tính theo modulo 13. Văn bản (19 ký tự):

```text
vị trí: 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19
T:      2 3 5 9 0 2 3 1 4 1  5  2  6  7  3  9  9  2  1
```

(a) Cửa sổ độ dài 5 bắt đầu ở vị trí 7 là 31415; giá trị theo modulo 13 là 7 (31415 = 13 · 2416 + 7).

(b) Giá trị theo modulo 13 của mọi cửa sổ độ dài 5, đặt tại vị trí bắt đầu cửa sổ (người tổng hợp đã tính lại từng giá trị và khớp với sách):

| Vị trí bắt đầu | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Cửa sổ | 23590 | 35902 | 59023 | 90231 | 02314 | 23141 | 31415 | 14152 | 41526 | 15267 | 52673 | 26739 | 67399 | 73992 | 39921 |
| mod 13 | 8 | 9 | 3 | 11 | 0 | 1 | **7** | 8 | 4 | 5 | 10 | 11 | **7** | 9 | 11 |

Với mẫu P = 31415, ta tìm các cửa sổ có giá trị modulo 13 bằng 7, vì 31415 ≡ 7 (mod 13). Có hai cửa sổ như vậy: cửa sổ bắt đầu ở vị trí 7 đúng là một lần xuất hiện của mẫu (khớp thật, độ dịch s = 6), còn cửa sổ bắt đầu ở vị trí 13 (67399) là trúng giả.

(c) Cách tính giá trị của cửa sổ mới trong thời gian hằng số từ giá trị cửa sổ trước. Cửa sổ thứ nhất có giá trị 31415. Bỏ chữ số hàng cao 3, dịch trái (nhân 10), cộng chữ số hàng thấp 2 cho giá trị mới 14152. Vì mọi phép tính làm theo modulo 13 (và 10⁴ = 10000 ≡ 3 (mod 13), tức h = 3):

```text
14152 ≡ (31415 − 3·10000)·10 + 2   (mod 13)
      ≡ (7 − 3·3)·10 + 2            (mod 13)
      ≡ 8                           (mod 13)
```

(chữ số cao cũ là 3, h = 3; 7 − 9 = −2; −2 · 10 + 2 = −18 ≡ −18 + 26 = 8). Giá trị của cửa sổ thứ nhất là 7, của cửa sổ mới là 8.

#### Thủ tục RABIN-KARP-MATCHER

Đầu vào: văn bản T, mẫu P, cơ số d (thường lấy d = |Σ|), số nguyên tố q.

```text
RABIN-KARP-MATCHER(T, P, d, q)
 1  n = T.length
 2  m = P.length
 3  h = d^{m−1} mod q
 4  p = 0
 5  t₀ = 0
 6  for i = 1 to m                         // preprocessing
 7      p = (d p + P[i]) mod q
 8      t₀ = (d t₀ + T[i]) mod q
 9  for s = 0 to n − m                     // matching
10      if p == t_s
11          if P[1..m] == T[s + 1..s + m]
12              print "Pattern occurs with shift" s
13      if s < n − m
14          t_{s+1} = (d (t_s − T[s + 1] h) + T[s + m + 1]) mod q
```

Mọi ký tự được hiểu là chữ số cơ số d. Chỉ số dưới của t chỉ để rõ nghĩa; chương trình vẫn đúng nếu bỏ hết chỉ số (chỉ cần một biến t). Dòng 3 khởi tạo h là giá trị vị trí chữ số hàng cao nhất của cửa sổ m chữ số. Dòng 4–8 tính p = P[1..m] mod q và t₀ = T[1..m] mod q (quy tắc Horner, lấy dư sau mỗi bước). Vòng for dòng 9–14 duyệt mọi độ dịch s, duy trì bất biến:

> Mỗi khi dòng 10 được thực hiện, t_s = T[s + 1..s + m] mod q.

Nếu p = t_s ở dòng 10 (một lần "trúng"), dòng 11 kiểm tra P[1..m] = T[s + 1..s + m] để loại khả năng trúng giả. Dòng 12 in các độ dịch hợp lệ tìm được. Nếu s < n − m (kiểm tra ở dòng 13), vòng for sẽ chạy thêm ít nhất một lần, nên dòng 14 được thực hiện trước để bất biến đúng khi quay lại dòng 10. Dòng 14 tính t_{s+1} mod q từ t_s mod q trong thời gian hằng số, trực tiếp theo (32.2).

Lưu ý cài đặt (người tổng hợp): ở dòng 14, biểu thức t_s − T[s + 1]h có thể âm; trong các ngôn ngữ mà phép % trả về số âm cho số bị chia âm (C, Java), cần cộng thêm q (hoặc một bội của q) trước khi lấy dư.

**Ví dụ chạy tay nhỏ (người tổng hợp):** T = 3141592653589793, P = 26, d = 10, q = 11 (đề của Exercise 32.2-1). h = 10¹ mod 11 = 10; p = 26 mod 11 = 4; t₀ = 31 mod 11 = 9. Cập nhật t₁ = (10 · (9 − 3 · 10) + 4) mod 11 = (−210 + 4) mod 11 = −206 mod 11 = 3 (−206 + 209 = 3), khớp 14 mod 11 = 3. Toàn bộ dãy t_s và kết quả nằm ở phần lời giải Exercise 32.2-1.

#### Phân tích thời gian

RABIN-KARP-MATCHER tốn Θ(m) tiền xử lý, và thời gian khớp xấu nhất là Θ((n − m + 1)m), vì (giống thuật toán ngây thơ) Rabin-Karp kiểm tra tường minh mọi độ dịch hợp lệ. Nếu P = aᵐ và T = aⁿ, việc kiểm tra tốn Θ((n − m + 1)m), vì cả n − m + 1 độ dịch đều hợp lệ.

Trong nhiều ứng dụng, ta chờ đợi ít độ dịch hợp lệ — có thể chỉ một số hằng c. Khi đó thời gian khớp kỳ vọng chỉ là O((n − m + 1) + cm) = O(n + m), cộng thời gian xử lý các trúng giả. Có thể phân tích theo kiểu kinh nghiệm (heuristic) dựa trên giả định rằng phép lấy dư theo q hoạt động như một ánh xạ ngẫu nhiên từ Σ\* vào Z_q (xem phần bàn về băm bằng phép chia ở Mục 11.3.1). Giả định này khó hình thức hoá và chứng minh, dù một hướng khả thi là giả định q được chọn ngẫu nhiên trong các số nguyên có độ lớn thích hợp; sách không theo đuổi hướng này. Khi đó ta kỳ vọng số trúng giả là O(n/q), vì có thể ước lượng xác suất một t_s bất kỳ đồng dư với p theo modulo q là 1/q. Vì có O(n) vị trí mà phép thử ở dòng 10 thất bại và mỗi lần trúng tốn O(m), thời gian khớp kỳ vọng của Rabin-Karp là

```text
O(n) + O(m (v + n/q))
```

trong đó v là số độ dịch hợp lệ. Thời gian này là O(n) nếu v = O(1) và chọn q ≥ m. Nghĩa là, nếu số độ dịch hợp lệ kỳ vọng nhỏ (O(1)) và số nguyên tố q lớn hơn độ dài mẫu, có thể kỳ vọng Rabin-Karp chỉ dùng O(n + m) thời gian khớp. Vì m ≤ n, thời gian khớp kỳ vọng này là O(n).

Ví dụ số (người tổng hợp): n = 10⁶, m = 100, q = 10⁹ + 7 (số nguyên tố quen thuộc), v = 3: số trúng giả kỳ vọng ≈ 10⁶ / 10⁹ = 0,001; chi phí kiểm tra ≈ 100 · (3 + 0,001) ≈ 300 phép so; tổng gần như chỉ là 10⁶ bước cập nhật băm.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: ý tưởng băm cuộn của Rabin-Karp có mặt ở nhiều nơi ngoài tìm chuỗi — phát hiện đạo văn và tìm đoạn mã trùng lặp (so dấu vân tay các cửa sổ k ký tự, như thuật toán winnowing của công cụ MOSS), chia khối theo nội dung trong rsync và các hệ thống sao lưu khử trùng lặp (rolling checksum), và tìm đồng thời hàng nghìn mẫu cùng độ dài (Exercise 32.2-2). Trong lập trình thi đấu, "băm chuỗi" với một hoặc hai modulo lớn là công cụ đa năng để so sánh chuỗi con trong O(1).

### 4. So khớp chuỗi bằng ôtômat hữu hạn (32.3 String matching with finite automata, trang 995–1002)

Nhiều thuật toán so khớp chuỗi dựng một ôtômat hữu hạn — một cỗ máy đơn giản xử lý thông tin — quét văn bản T để tìm mọi lần xuất hiện của mẫu P. Mục này trình bày cách dựng một ôtômat như vậy. Các ôtômat so khớp chuỗi này rất hiệu quả: chúng xem mỗi ký tự văn bản *đúng một lần*, mỗi ký tự tốn thời gian hằng số. Vì vậy thời gian khớp — sau khi tiền xử lý mẫu để dựng ôtômat — là Θ(n). Tuy nhiên thời gian dựng ôtômat có thể lớn nếu Σ lớn; Mục 32.4 mô tả một cách khéo léo để tránh vấn đề này.

Trình tự của mục: định nghĩa ôtômat hữu hạn; khảo sát một ôtômat so khớp chuỗi đặc biệt và cách dùng nó tìm các lần xuất hiện của mẫu; cuối cùng là cách dựng ôtômat so khớp chuỗi cho một mẫu cho trước.

#### Ôtômat hữu hạn (Finite automata)

Một **ôtômat hữu hạn** M là bộ năm (Q, q₀, A, Σ, δ), trong đó:

- Q là tập hữu hạn các **trạng thái** (states);
- q₀ ∈ Q là **trạng thái bắt đầu** (start state);
- A ⊆ Q là một tập phân biệt các **trạng thái chấp nhận** (accepting states);
- Σ là **bảng chữ đầu vào** (input alphabet) hữu hạn;
- δ là hàm từ Q × Σ vào Q, gọi là **hàm chuyển trạng thái** (transition function) của M.

Ôtômat bắt đầu ở trạng thái q₀ và đọc từng ký tự của chuỗi đầu vào. Nếu đang ở trạng thái q và đọc ký tự a, nó chuyển ("thực hiện một phép chuyển") từ q sang δ(q, a). Mỗi khi trạng thái hiện tại q thuộc A, cỗ máy M đã **chấp nhận** (accepted) chuỗi đọc được tới lúc đó. Đầu vào không được chấp nhận thì bị **từ chối** (rejected).

**Ví dụ (chép lại Hình 32.6 của sách):** ôtômat hai trạng thái, Q = {0, 1}, q₀ = 0, Σ = {a, b}, trạng thái 1 (tô đen trong hình) là trạng thái chấp nhận duy nhất.

(a) Bảng hàm chuyển δ:

| Trạng thái | đọc a | đọc b |
|---|---|---|
| 0 | 1 | 0 |
| 1 | 0 | 0 |

(b) Sơ đồ chuyển trạng thái tương đương:

```text
              a
         ┌────────────▶
   b ⟲  (0)           ((1))      ← trạng thái chấp nhận
         ◀────────────┘
            a hoặc b
```

Cạnh có hướng biểu diễn phép chuyển; ví dụ cạnh từ trạng thái 1 sang 0 nhãn b nghĩa là δ(1, b) = 0. Ôtômat này chấp nhận đúng những chuỗi kết thúc bằng một số **lẻ** chữ a. Chính xác hơn, nó chấp nhận x khi và chỉ khi x = yz với y = ε hoặc y kết thúc bằng b, và z = aᵏ với k lẻ. Ví dụ, trên đầu vào abaaa, kể cả trạng thái đầu, ôtômat đi qua dãy trạng thái ⟨0, 1, 0, 1, 0, 1⟩ nên chấp nhận. Trên đầu vào abbaa, nó đi qua ⟨0, 1, 0, 0, 1, 0⟩ nên từ chối.

Ôtômat hữu hạn M sinh ra một hàm φ, gọi là **hàm trạng thái cuối** (final-state function), từ Σ\* vào Q: φ(w) là trạng thái M dừng ở sau khi quét chuỗi w. Như vậy M chấp nhận w khi và chỉ khi φ(w) ∈ A. Định nghĩa φ đệ quy qua hàm chuyển:

```text
φ(ε)  = q₀
φ(wa) = δ(φ(w), a)      với w ∈ Σ*, a ∈ Σ
```

#### Ôtômat so khớp chuỗi (String-matching automata)

Với một mẫu P cho trước, ta dựng ôtômat so khớp chuỗi ở bước tiền xử lý trước khi dùng nó để tìm trong văn bản. Từ đây coi P là một mẫu cố định; để gọn, ký hiệu không ghi sự phụ thuộc vào P.

Để định nghĩa ôtômat so khớp chuỗi cho mẫu P[1..m], trước hết định nghĩa hàm phụ σ, gọi là **hàm hậu tố** (suffix function) ứng với P. Hàm σ ánh xạ Σ\* vào {0, 1, …, m} sao cho σ(x) là độ dài của tiền tố dài nhất của P đồng thời là hậu tố của x:

```text
σ(x) = max {k : P_k ⊐ x}                                              (32.3)
```

Hàm σ được định nghĩa tốt vì chuỗi rỗng P₀ = ε là hậu tố của mọi chuỗi (tập luôn khác rỗng). Ví dụ, với mẫu P = ab: σ(ε) = 0, σ(ccaca) = 1, σ(ccab) = 2. Với mẫu độ dài m, σ(x) = m khi và chỉ khi P ⊐ x. Từ định nghĩa, x ⊐ y kéo theo σ(x) ≤ σ(y).

**Định nghĩa ôtômat so khớp chuỗi** của mẫu P[1..m]:

- Tập trạng thái Q = {0, 1, …, m}. Trạng thái bắt đầu q₀ là 0, và trạng thái m là trạng thái chấp nhận duy nhất.
- Hàm chuyển δ được định nghĩa, với mọi trạng thái q và ký tự a, bởi

```text
δ(q, a) = σ(P_q a)                                                    (32.4)
```

**Vì sao định nghĩa như vậy.** Ta muốn theo dõi tiền tố dài nhất của mẫu P đã khớp với văn bản T tới thời điểm hiện tại. Xét các ký tự vừa đọc gần nhất của T. Để một chuỗi con của T — chẳng hạn chuỗi con kết thúc tại T[i] — khớp với một tiền tố P_j nào đó của P, thì P_j phải là hậu tố của T_i. Giả sử q = φ(T_i), tức sau khi đọc T_i ôtômat ở trạng thái q. Ta thiết kế δ sao cho số hiệu trạng thái q này cho biết độ dài của tiền tố dài nhất của P khớp với một hậu tố của T_i. Nghĩa là, ở trạng thái q thì P_q ⊐ T_i và q = σ(T_i). (Mỗi khi q = m, cả m ký tự của P khớp với một hậu tố của T_i, tức đã tìm được một lần khớp.) Vì φ(T_i) và σ(T_i) đều bằng q, ta sẽ thấy (Định lý 32.4) ôtômat duy trì bất biến

```text
φ(T_i) = σ(T_i)                                                       (32.5)
```

Nếu ôtômat ở trạng thái q và đọc ký tự kế tiếp T[i + 1] = a, ta muốn phép chuyển dẫn tới trạng thái ứng với tiền tố dài nhất của P là hậu tố của T_i a, tức trạng thái σ(T_i a). Vì P_q là tiền tố dài nhất của P là hậu tố của T_i, tiền tố dài nhất của P là hậu tố của T_i a không chỉ là σ(T_i a) mà còn là σ(P_q a) (Bổ đề 32.3 dưới đây chứng minh σ(T_i a) = σ(P_q a)). Vậy khi ôtômat ở trạng thái q, ta muốn hàm chuyển trên ký tự a đưa nó sang trạng thái σ(P_q a). Điểm mấu chốt: σ(P_q a) chỉ phụ thuộc vào q và a, không phụ thuộc phần văn bản đã đọc, nên có thể tính trước thành bảng.

Có hai trường hợp:

1. a = P[q + 1]: ký tự a tiếp tục khớp với mẫu; khi đó δ(q, a) = q + 1, phép chuyển đi tiếp dọc "xương sống" (spine) của ôtômat.
2. a ≠ P[q + 1]: a không tiếp tục khớp. Phải tìm một tiền tố *ngắn hơn* của P cũng là hậu tố của T_i a. Vì bước tiền xử lý so mẫu với chính nó khi dựng ôtômat, hàm chuyển xác định ngay tiền tố ngắn hơn dài nhất như vậy.

**Ví dụ: ôtômat cho P = ababaca (chép lại Hình 32.7 của sách).** m = 7, Σ = {a, b, c}.

(b) Bảng hàm chuyển δ (ô in đậm là các phép chuyển dọc xương sống, ứng với khớp thành công; cột cuối là ký tự P[q + 1]):

| Trạng thái q | đọc a | đọc b | đọc c | P[q + 1] |
|---|---|---|---|---|
| 0 | **1** | 0 | 0 | a |
| 1 | 1 | **2** | 0 | b |
| 2 | **3** | 0 | 0 | a |
| 3 | 1 | **4** | 0 | b |
| 4 | **5** | 0 | 0 | a |
| 5 | 1 | 4 | **6** | c |
| 6 | **7** | 0 | 0 | a |
| 7 | 1 | 2 | 0 | — |

(a) Sơ đồ chuyển trạng thái. Trạng thái 0 là trạng thái bắt đầu, trạng thái 7 (tô đen) là trạng thái chấp nhận duy nhất. Cạnh có hướng từ i sang j nhãn a biểu diễn δ(i, a) = j. Các cạnh đi sang phải tạo thành "xương sống" (vẽ đậm trong hình gốc) ứng với khớp thành công; các cạnh đi sang trái ứng với không khớp. Một số cạnh không khớp bị lược bỏ; theo quy ước, nếu trạng thái i không có cạnh ra nhãn a thì δ(i, a) = 0. Vẽ lại:

```text
Xương sống:  (0) ─a→ (1) ─b→ (2) ─a→ (3) ─b→ (4) ─a→ (5) ─c→ (6) ─a→ ((7))

Các cạnh lùi (không về 0) được vẽ trong hình gốc:
   1 ─a→ 1 (vòng tại 1)      3 ─a→ 1       5 ─a→ 1       7 ─a→ 1
   5 ─b→ 4                   7 ─b→ 2
Mọi cạnh còn lại (không vẽ) dẫn về trạng thái 0.
```

Kiểm tra từng ô theo định nghĩa δ(q, a) = σ(P_q a) (người tổng hợp): δ(1, a) = σ(aa) = 1 (hậu tố a); δ(3, a) = σ(abaa) = 1; δ(5, a) = σ(ababaa) = 1; δ(5, b) = σ(ababab) = 4 (hậu tố abab = P₄); δ(7, a) = σ(ababacaa) = 1; δ(7, b) = σ(ababacab) = 2 (hậu tố ab); các ô còn lại bằng 0 vì chuỗi P_q a kết thúc bằng ký tự không khớp với P[1] = a (b hoặc c) và không có tiền tố dài hơn nào khớp. Bảng của sách đúng hoàn toàn.

(c) Hoạt động của ôtômat trên văn bản T = abababacaba (n = 11). Dưới mỗi ký tự T[i] là trạng thái φ(T_i) sau khi xử lý tiền tố T_i:

| i | — | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| T[i] | — | a | b | a | b | a | b | a | c | a | b | a |
| φ(T_i) | 0 | 1 | 2 | 3 | 4 | 5 | 4 | 5 | 6 | **7** | 2 | 3 |

Ôtômat tìm được một lần xuất hiện của mẫu, kết thúc ở vị trí 9 (các ký tự T[3..9] = ababaca được tô trong hình gốc), tức độ dịch 9 − 7 = 2. Chú ý bước i = 6: ở trạng thái 5 đọc b (không khớp c), ôtômat không quay về 0 mà về 4, vì abab vẫn còn là phần đầu dang dở của một lần khớp mới; nhờ vậy lần khớp bắt đầu ở vị trí 3 được phát hiện mà không đọc lại văn bản.

Hai trường hợp minh hoạ: δ(5, c) = 6 là trường hợp thứ nhất (khớp tiếp). δ(5, b) = 4 là trường hợp thứ hai: nếu ôtômat đọc b ở trạng thái q = 5 thì P_q b = ababab, và tiền tố dài nhất của P là hậu tố của ababab là P₄ = abab.

#### Thủ tục FINITE-AUTOMATON-MATCHER

Để làm rõ hoạt động của ôtômat so khớp chuỗi, sách đưa ra chương trình đơn giản, hiệu quả, mô phỏng hành vi của ôtômat (biểu diễn bằng hàm chuyển δ) khi tìm mẫu P độ dài m trong văn bản T[1..n]. Như mọi ôtômat so khớp chuỗi cho mẫu độ dài m, tập trạng thái là {0, 1, …, m}, trạng thái bắt đầu là 0 và trạng thái chấp nhận duy nhất là m.

```text
FINITE-AUTOMATON-MATCHER(T, δ, m)
1  n = T.length
2  q = 0
3  for i = 1 to n
4      q = δ(q, T[i])
5      if q == m
6          print "Pattern occurs with shift" i − m
```

Từ cấu trúc vòng lặp đơn giản, dễ thấy thời gian khớp trên văn bản độ dài n là Θ(n): mỗi ký tự một lần tra bảng và một phép so sánh. Thời gian này chưa tính thời gian tiền xử lý để tính hàm chuyển δ; vấn đề đó được giải quyết sau khi chứng minh thủ tục đúng.

#### Tính đúng

Xét ôtômat chạy trên văn bản T[1..n]. Ta sẽ chứng minh ôtômat ở trạng thái σ(T_i) sau khi quét ký tự T[i]. Vì σ(T_i) = m khi và chỉ khi P ⊐ T_i, cỗ máy ở trạng thái chấp nhận m khi và chỉ khi nó vừa quét xong một lần xuất hiện của P. Chứng minh dùng hai bổ đề về hàm hậu tố σ.

**Bổ đề 32.2 (Bất đẳng thức hàm hậu tố — Suffix-function inequality).** Với mọi chuỗi x và ký tự a, σ(xa) ≤ σ(x) + 1.

*Chứng minh.* Đặt r = σ(xa). Nếu r = 0 thì kết luận σ(xa) = r ≤ σ(x) + 1 hiển nhiên đúng vì σ(x) không âm. Giả sử r > 0. Theo định nghĩa σ, P_r ⊐ xa. Bỏ ký tự a ở cuối P_r và ở cuối xa (làm được vì r > 0, nên ký tự cuối của P_r chính là a), ta được P_{r−1} ⊐ x. Do đó r − 1 ≤ σ(x), vì σ(x) là k lớn nhất sao cho P_k ⊐ x; tức σ(xa) = r ≤ σ(x) + 1. ∎

Minh hoạ của sách (vẽ lại Hình 32.8):

```text
   ┌─────────────────── x ───────────────────┐
   [ ........................ |   P_{r−1}    ] a
                              [   P_{r−1}    | a ]  = P_r   (canh phải với xa)
```

P_r khớp với phần cuối của xa; bỏ chữ a cuối thì P_{r−1} khớp với phần cuối của x, nên r ≤ σ(x) + 1.

Ví dụ kiểm tra (người tổng hợp) với P = ababaca: x = abab (σ = 4), a = a: σ(ababa) = 5 = 4 + 1 (dấu bằng); x = abab, c: σ(ababc) = 0 ≤ 5.

**Bổ đề 32.3 (Bổ đề đệ quy hàm hậu tố — Suffix-function recursion lemma).** Với mọi chuỗi x và ký tự a, nếu q = σ(x) thì σ(xa) = σ(P_q a).

*Chứng minh.* Theo định nghĩa σ, P_q ⊐ x. Do đó P_q a ⊐ xa. Đặt r = σ(xa); khi đó P_r ⊐ xa và, theo Bổ đề 32.2, r ≤ q + 1. Vậy |P_r| = r ≤ q + 1 = |P_q a|. Vì P_q a ⊐ xa, P_r ⊐ xa và |P_r| ≤ |P_q a|, Bổ đề 32.1 cho P_r ⊐ P_q a. Do đó r ≤ σ(P_q a), tức σ(xa) ≤ σ(P_q a). Mặt khác σ(P_q a) ≤ σ(xa) vì P_q a ⊐ xa (tính chất "x ⊐ y kéo theo σ(x) ≤ σ(y)"). Vậy σ(xa) = σ(P_q a). ∎

Minh hoạ của sách (vẽ lại Hình 32.9):

```text
   ┌────────────────────── x ──────────────────────┐
   [ ...................... |         P_q          ] a     ← xa
                            [         P_q          | a ]   ← P_q a ⊐ xa
                                      [     P_r        ]   ← P_r ⊐ xa, và ngắn hơn
                                                             hoặc bằng P_q a
```

Ý nghĩa: để biết tiền tố dài nhất của P khớp với phần cuối văn bản sau khi thêm ký tự a, chỉ cần biết q (độ dài khớp hiện tại) và a — toàn bộ phần văn bản trước đó không còn quan trọng.

**Định lý 32.4.** Nếu φ là hàm trạng thái cuối của ôtômat so khớp chuỗi cho mẫu P và T[1..n] là văn bản đầu vào của ôtômat thì

```text
φ(T_i) = σ(T_i)      với i = 0, 1, …, n.
```

*Chứng minh.* Quy nạp theo i. Với i = 0, định lý hiển nhiên đúng vì T₀ = ε, nên φ(T₀) = 0 = σ(T₀).

Giả sử φ(T_i) = σ(T_i), cần chứng minh φ(T_{i+1}) = σ(T_{i+1}). Gọi q là φ(T_i) và a là T[i + 1]. Khi đó

```text
φ(T_{i+1}) = φ(T_i a)        (theo định nghĩa của T_{i+1} và a)
           = δ(φ(T_i), a)    (theo định nghĩa của φ)
           = δ(q, a)         (theo định nghĩa của q)
           = σ(P_q a)        (theo định nghĩa (32.4) của δ)
           = σ(T_i a)        (theo Bổ đề 32.3 và giả thiết quy nạp q = σ(T_i))
           = σ(T_{i+1})      (theo định nghĩa của T_{i+1})            ∎
```

Theo Định lý 32.4, nếu cỗ máy vào trạng thái q ở dòng 4 thì q là giá trị lớn nhất sao cho P_q ⊐ T_i. Vậy q = m ở dòng 5 khi và chỉ khi cỗ máy vừa quét xong một lần xuất hiện của P. Kết luận: FINITE-AUTOMATON-MATCHER hoạt động đúng.

#### Tính hàm chuyển (Computing the transition function)

Thủ tục sau tính hàm chuyển δ từ mẫu P[1..m]:

```text
COMPUTE-TRANSITION-FUNCTION(P, Σ)
1  m = P.length
2  for q = 0 to m
3      for each character a ∈ Σ
4          k = min(m + 1, q + 2)
5          repeat
6              k = k − 1
7          until P_k ⊐ P_q a
8          δ(q, a) = k
9  return δ
```

Thủ tục tính δ(q, a) một cách trực tiếp theo định nghĩa (32.4). Hai vòng lặp lồng nhau bắt đầu ở dòng 2 và 3 xét mọi trạng thái q và mọi ký tự a, và dòng 4–8 gán δ(q, a) bằng k lớn nhất sao cho P_k ⊐ P_q a. Mã bắt đầu từ giá trị lớn nhất có thể của k, là min(m, q + 1) (dòng 4 gán min(m + 1, q + 2) vì vòng repeat giảm k đi 1 trước lần kiểm tra đầu tiên). Rồi giảm k cho tới khi P_k ⊐ P_q a; điều này chắc chắn xảy ra vì P₀ = ε là hậu tố của mọi chuỗi.

**Thời gian.** COMPUTE-TRANSITION-FUNCTION chạy O(m³|Σ|): hai vòng ngoài góp thừa số m|Σ| (chính xác là (m + 1)|Σ|), vòng repeat trong chạy tối đa m + 1 lần, và phép thử P_k ⊐ P_q a ở dòng 7 có thể phải so tới m ký tự. Có những thủ tục nhanh hơn nhiều: dùng thông tin được tính khéo léo về mẫu P (Exercise 32.4-8), có thể giảm thời gian tính δ từ P xuống O(m|Σ|). Với thủ tục cải tiến này, ta tìm mọi lần xuất hiện của mẫu độ dài m trong văn bản độ dài n trên bảng chữ Σ với O(m|Σ|) tiền xử lý và Θ(n) thời gian khớp.

**Ví dụ chạy tay một ô (người tổng hợp):** P = ababaca, tính δ(5, b). P₅b = ababab. k bắt đầu min(8, 7) = 7, giảm thành 6: P₆ = ababac có là hậu tố của ababab? Không (khác chữ cuối). k = 5: ababa ⊐ ababab? Không. k = 4: abab ⊐ ababab? Có (bốn ký tự cuối là abab). Vậy δ(5, b) = 4, khớp bảng.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: ý tưởng "dựng ôtômat từ mẫu rồi quét văn bản một lượt" là nền của bộ máy biểu thức chính quy (regular expression) dạng DFA, như trong `grep`/`egrep`, công cụ phân tích từ vựng `lex`/`flex` của trình biên dịch, và thư viện RE2 của Google — các công cụ này bảo đảm thời gian tuyến tính theo độ dài văn bản. Mở rộng tự nhiên cho nhiều mẫu cùng lúc là ôtômat Aho–Corasick (liên quan Exercise 32.3-4), dùng trong hệ thống phát hiện xâm nhập (Snort), quét virus và lọc từ khoá. Cái giá phải trả chính là điều sách nêu: bảng chuyển cỡ (m + 1)|Σ| — với Σ là 256 byte hay bảng mã Unicode, bảng có thể rất lớn.

### 5. Thuật toán Knuth-Morris-Pratt (★32.4 The Knuth-Morris-Pratt algorithm, trang 1002–1012)

Mục này (có dấu sao trong sách) trình bày thuật toán so khớp chuỗi thời gian tuyến tính của Knuth, Morris và Pratt. Thuật toán tránh hẳn việc tính hàm chuyển δ, và thời gian khớp của nó là Θ(n) chỉ nhờ một hàm phụ π, được tính trước từ mẫu trong Θ(m) và lưu trong mảng π[1..m]. Mảng π cho phép tính hàm chuyển δ một cách hiệu quả (theo nghĩa khấu hao) "ngay khi cần" (on the fly). Nói nôm na, với mọi trạng thái q = 0, 1, …, m và mọi ký tự a ∈ Σ, giá trị π[q] chứa thông tin cần thiết để tính δ(q, a) nhưng không phụ thuộc vào a. Vì mảng π chỉ có m phần tử trong khi δ có Θ(m|Σ|) phần tử, ta tiết kiệm một thừa số |Σ| ở thời gian tiền xử lý khi tính π thay vì δ.

#### Hàm tiền tố của một mẫu (The prefix function for a pattern)

Hàm tiền tố π của một mẫu gói gọn hiểu biết về cách mẫu khớp với các bản dịch của chính nó. Ta có thể tận dụng thông tin này để tránh thử các độ dịch vô ích trong thuật toán ngây thơ, và để tránh tính trước toàn bộ hàm chuyển δ của ôtômat.

Xét hoạt động của thuật toán ngây thơ. Ví dụ (vẽ lại Hình 32.10 của sách): mẫu P = ababaca đặt ở một độ dịch s trên văn bản T = bacbababaabcbab. Ở độ dịch này (s = 4), q = 5 ký tự đầu của mẫu đã khớp, nhưng ký tự thứ 6 của mẫu không khớp với ký tự văn bản tương ứng.

```text
(a)  vị trí:  1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
     T:       b a c b a b a b a a  b  c  b  a  b
     P (s=4):         a b a b a c  a
                      └─ q = 5 ─┘↯             (P[6] = c ≠ T[10] = a)

(b)  P (s′ = s + 2 = 6):  a b a b a c a
     T:       b a c b a b a b a a  b  c  b  a  b
                          └ k=3 ┘              (T[7..9] = aba = P[1..3])

(c)  So mẫu với chính nó:
     P_q = P₅:   a b a b a
     P_k = P₃:       a b a        P₃ là tiền tố dài nhất của P đồng thời là
                                  hậu tố thực sự của P₅ ⇒ π[5] = 3
```

Thông tin "q ký tự đã khớp" xác định luôn các ký tự văn bản tương ứng. Biết q ký tự văn bản này, ta suy ra ngay một số độ dịch không hợp lệ. Trong ví dụ, độ dịch s + 1 chắc chắn không hợp lệ: ký tự đầu của mẫu (a) sẽ đặt thẳng hàng với một ký tự văn bản mà ta biết là không khớp với ký tự đầu của mẫu, vì nó khớp với ký tự thứ hai của mẫu (b). Còn độ dịch s′ = s + 2 ở phần (b) đặt ba ký tự đầu của mẫu thẳng hàng với ba ký tự văn bản chắc chắn khớp. Tổng quát, cần biết câu trả lời cho câu hỏi:

> Biết các ký tự mẫu P[1..q] khớp với các ký tự văn bản T[s + 1..s + q], độ dịch nhỏ nhất s′ > s là bao nhiêu sao cho với một k < q nào đó,
>
> P[1..k] = T[s′ + 1..s′ + k],                                        (32.6)
>
> trong đó s′ + k = s + q?

Nói cách khác, biết P_q ⊐ T_{s+q}, ta muốn tiền tố thực sự dài nhất P_k của P_q đồng thời là hậu tố của T_{s+q}. (Vì s′ + k = s + q, nếu biết s và q thì tìm độ dịch nhỏ nhất s′ tương đương với tìm độ dài tiền tố k lớn nhất.) Cộng hiệu q − k của độ dài hai tiền tố này vào độ dịch s để được độ dịch mới s′ = s + (q − k). Trong trường hợp tốt nhất, k = 0, nên s′ = s + q, và ta loại ngay các độ dịch s + 1, s + 2, …, s + q − 1. Trong mọi trường hợp, ở độ dịch mới s′ không cần so k ký tự đầu của P với các ký tự tương ứng của T, vì (32.6) bảo đảm chúng khớp.

Có thể tính trước thông tin cần thiết bằng cách so mẫu với chính nó, như phần (c) ở trên. Vì T[s′ + 1..s′ + k] là một phần của đoạn văn bản đã biết, nó là hậu tố của chuỗi P_q. Do đó có thể hiểu (32.6) là hỏi k < q lớn nhất sao cho P_k ⊐ P_q. Khi đó độ dịch mới s′ = s + (q − k) là độ dịch kế tiếp có thể hợp lệ. Hoá ra tiện hơn nếu lưu, với mỗi q, số k ký tự khớp ở độ dịch mới s′, thay vì lưu chẳng hạn s′ − s.

**Định nghĩa.** Cho mẫu P[1..m], **hàm tiền tố** (prefix function) của P là hàm π : {1, 2, …, m} → {0, 1, …, m − 1} sao cho

```text
π[q] = max {k : k < q và P_k ⊐ P_q}
```

Nghĩa là π[q] là độ dài của tiền tố dài nhất của P đồng thời là hậu tố thực sự của P_q. Trong ví dụ, π[5] = 3; khi q ký tự đã khớp ở độ dịch s, độ dịch có thể hợp lệ kế tiếp là s′ = s + (q − π[q]) = 4 + (5 − 3) = 6, đúng như phần (b).

**Hàm tiền tố đầy đủ của P = ababaca** (chép lại Hình 32.11(a)):

| i | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| P[i] | a | b | a | b | a | c | a |
| π[i] | 0 | 0 | 1 | 2 | 3 | 0 | 1 |

Giải thích từng giá trị (người tổng hợp): π[1] = 0 luôn đúng (hậu tố thực sự của một ký tự chỉ có ε); π[2]: ab không có hậu tố thực sự khác rỗng nào là tiền tố (b ≠ a); π[3] = 1: hậu tố a của aba; π[4] = 2: hậu tố ab của abab; π[5] = 3: hậu tố aba của ababa; π[6] = 0: ababac kết thúc bằng c, không tiền tố nào của P kết thúc bằng c ngoài chính ababac; π[7] = 1: hậu tố a của ababaca (thử aca, ca: không phải tiền tố).

#### Thủ tục KMP-MATCHER và COMPUTE-PREFIX-FUNCTION

Pseudocode dưới đây là thuật toán Knuth-Morris-Pratt dưới dạng thủ tục KMP-MATCHER. Phần lớn thủ tục suy ra từ FINITE-AUTOMATON-MATCHER, như sẽ thấy. KMP-MATCHER gọi thủ tục phụ COMPUTE-PREFIX-FUNCTION để tính π.

```text
KMP-MATCHER(T, P)
 1  n = T.length
 2  m = P.length
 3  π = COMPUTE-PREFIX-FUNCTION(P)
 4  q = 0                                  // number of characters matched
 5  for i = 1 to n                         // scan the text from left to right
 6      while q > 0 and P[q + 1] ≠ T[i]
 7          q = π[q]                       // next character does not match
 8      if P[q + 1] == T[i]
 9          q = q + 1                      // next character matches
10      if q == m                          // is all of P matched?
11          print "Pattern occurs with shift" i − m
12          q = π[q]                       // look for the next match
```

Chú thích trong mã (dịch): dòng 4 "số ký tự đã khớp"; dòng 5 "quét văn bản từ trái sang phải"; dòng 7 "ký tự kế tiếp không khớp"; dòng 9 "ký tự kế tiếp khớp"; dòng 10 "đã khớp hết P chưa?"; dòng 12 "tìm lần khớp kế tiếp".

```text
COMPUTE-PREFIX-FUNCTION(P)
 1  m = P.length
 2  let π[1..m] be a new array
 3  π[1] = 0
 4  k = 0
 5  for q = 2 to m
 6      while k > 0 and P[k + 1] ≠ P[q]
 7          k = π[k]
 8      if P[k + 1] == P[q]
 9          k = k + 1
10      π[q] = k
11  return π
```

Hai thủ tục rất giống nhau vì cả hai đều khớp một chuỗi với mẫu P: KMP-MATCHER khớp văn bản T với P, còn COMPUTE-PREFIX-FUNCTION khớp P với chính nó.

**Ví dụ chạy tay COMPUTE-PREFIX-FUNCTION trên P = ababaca (người tổng hợp):**

| q | P[q] | k đầu vòng | Vòng while (dòng 6–7) | Dòng 8–9 | π[q] |
|---|---|---|---|---|---|
| 1 | a | — | — | — | 0 (dòng 3) |
| 2 | b | 0 | không chạy (k = 0) | P[1] = a ≠ b | 0 |
| 3 | a | 0 | không chạy | P[1] = a = a ⇒ k = 1 | 1 |
| 4 | b | 1 | P[2] = b = b, không chạy | k = 2 | 2 |
| 5 | a | 2 | P[3] = a = a, không chạy | k = 3 | 3 |
| 6 | c | 3 | P[4] = b ≠ c ⇒ k = π[3] = 1; P[2] = b ≠ c ⇒ k = π[1] = 0; dừng | P[1] = a ≠ c | 0 |
| 7 | a | 0 | không chạy | P[1] = a = a ⇒ k = 1 | 1 |

Kết quả π = 0, 0, 1, 2, 3, 0, 1, khớp bảng trên. Vòng while chạy tổng cộng 2 lần ≤ m − 1 = 6.

**Ví dụ chạy tay KMP-MATCHER trên T = abababacaba, P = ababaca (người tổng hợp; cùng văn bản với ví dụ ôtômat):**

| i | T[i] | q đầu vòng | Vòng while | Dòng 8–9 | q sau dòng 9 | Ghi chú |
|---|---|---|---|---|---|---|
| 1 | a | 0 | — | P[1] = a khớp | 1 | |
| 2 | b | 1 | — | P[2] = b khớp | 2 | |
| 3 | a | 2 | — | P[3] = a khớp | 3 | |
| 4 | b | 3 | — | P[4] = b khớp | 4 | |
| 5 | a | 4 | — | P[5] = a khớp | 5 | |
| 6 | b | 5 | P[6] = c ≠ b ⇒ q = π[5] = 3 | P[4] = b khớp | 4 | |
| 7 | a | 4 | — | P[5] = a khớp | 5 | |
| 8 | c | 5 | — | P[6] = c khớp | 6 | |
| 9 | a | 6 | — | P[7] = a khớp | 7 = m | in độ dịch 9 − 7 = 2; dòng 12: q = π[7] = 1 |
| 10 | b | 1 | — | P[2] = b khớp | 2 | |
| 11 | a | 2 | — | P[3] = a khớp | 3 | |

Dãy q sau dòng 9 là 1, 2, 3, 4, 5, 4, 5, 6, 7, 2, 3 — trùng hoàn toàn với dãy trạng thái của ôtômat ở mục trước. Đây chính là điều sẽ được chứng minh: KMP mô phỏng ôtômat.

#### Phân tích thời gian chạy (Running-time analysis)

Thời gian chạy của COMPUTE-PREFIX-FUNCTION là Θ(m), chứng minh bằng phương pháp gộp của phân tích khấu hao (Mục 17.1). Phần duy nhất khó là chỉ ra vòng while ở dòng 6–7 chạy tổng cộng O(m) lần. Ta chứng minh nó chạy nhiều nhất m − 1 lần. Trước hết vài nhận xét về k:

1. Dòng 4 khởi tạo k = 0, và cách duy nhất làm k tăng là phép tăng ở dòng 9, thực hiện nhiều nhất một lần mỗi vòng lặp for (dòng 5–10). Vậy tổng lượng tăng của k nhiều nhất là m − 1.
2. Vì k < q khi vào vòng for và mỗi vòng lặp tăng q, ta luôn có k < q. Do đó các phép gán ở dòng 3 và 10 bảo đảm π[q] < q với mọi q = 1, 2, …, m, nghĩa là mỗi lần lặp của vòng while làm k giảm.
3. k không bao giờ âm.

Gộp lại, tổng lượng giảm của k do vòng while bị chặn trên bởi tổng lượng tăng của k qua mọi vòng lặp for, tức m − 1. Vậy vòng while lặp tổng cộng nhiều nhất m − 1 lần, và COMPUTE-PREFIX-FUNCTION chạy Θ(m).

Exercise 32.4-4 yêu cầu chứng minh, bằng phân tích gộp tương tự, rằng thời gian khớp của KMP-MATCHER là Θ(n). (Lập luận tóm tắt của người tổng hợp: q chỉ tăng ở dòng 9, nhiều nhất một lần mỗi vòng for, tổng tăng ≤ n; mỗi lần dòng 7 hoặc dòng 12 thực hiện, q giảm hẳn vì π[q] < q; q ≥ 0; vậy tổng số lần thực hiện dòng 7 ≤ n, và thời gian Θ(n).)

**Ví dụ minh hoạ khấu hao (người tổng hợp):** P = aaab (π = 0, 1, 2, 0), T = aaaaaaaab (n = 9). Ở i = 1, 2, 3, q tăng lên 3. Ở mỗi i = 4, 5, 6, 7, 8 (ký tự a), vòng while chạy đúng một lần (P[4] = b ≠ a, q = π[3] = 2) rồi dòng 9 đưa q về 3. Ở i = 9 (ký tự b), P[4] = b khớp, q = 4 = m: in độ dịch 5. Tổng số lần lặp while: 5 ≤ n. Một lần lặp for riêng lẻ có thể chạy while nhiều lần (ví dụ với P = ababaca, ở trạng thái 5 mà đọc ký tự a thì vòng while chạy 3 lần, xem ví dụ về δ(5, a) ở phần tính đúng bên dưới), nhưng tổng trên cả văn bản luôn bị chặn bởi n.

So với FINITE-AUTOMATON-MATCHER, dùng π thay cho δ giảm thời gian tiền xử lý mẫu từ O(m|Σ|) xuống Θ(m), trong khi vẫn giữ thời gian khớp thực sự trong Θ(n).

#### Tính đúng của việc tính hàm tiền tố (Correctness of the prefix-function computation)

Lát nữa sẽ thấy hàm tiền tố π giúp mô phỏng hàm chuyển δ của ôtômat so khớp chuỗi. Nhưng trước hết cần chứng minh COMPUTE-PREFIX-FUNCTION tính đúng hàm tiền tố. Để làm vậy, cần tìm *mọi* tiền tố P_k là hậu tố thực sự của một tiền tố P_q cho trước. Giá trị π[q] cho tiền tố dài nhất như vậy; bổ đề dưới đây chỉ ra rằng lặp hàm π liệt kê đủ mọi tiền tố P_k là hậu tố thực sự của P_q. Đặt

```text
π*[q] = {π[q], π^(2)[q], π^(3)[q], …, π^(t)[q]}
```

trong đó π^(i)[q] định nghĩa theo phép lặp hàm: π^(0)[q] = q và π^(i)[q] = π[π^(i−1)[q]] với i ≥ 1; dãy trong π\*[q] dừng khi chạm π^(t)[q] = 0 (giá trị 0 thuộc tập).

**Minh hoạ (chép lại Hình 32.11(b)) với P = ababaca, q = 5.** Vì π[5] = 3, π[3] = 1, π[1] = 0, lặp π cho π\*[5] = {3, 1, 0}. Trượt khuôn chứa mẫu P sang phải và ghi nhận khi nào một tiền tố P_k của P khớp với một hậu tố thực sự của P₅ (vạch dọc chấm chấm đặt ngay sau P₅):

```text
P₅:   a b a b a ┆ c a
P₃:       a b a ┆ b a c a          π[5] = 3   (aba khớp hậu tố của P₅)
P₁:           a ┆ b a b a c a      π[3] = 1   (a khớp hậu tố của P₅)
P₀:           ε ┆ a b a b a c a    π[1] = 0
```

Các lần khớp xảy ra khi k = 3, 1 và 0. Vậy {k : k < 5 và P_k ⊐ P₅} = {3, 1, 0}. Bổ đề 32.5 khẳng định π\*[q] = {k : k < q và P_k ⊐ P_q} với mọi q. (Kiểm tra: k = 2 thì ab không phải hậu tố của ababa; k = 4 thì abab cũng không.)

**Bổ đề 32.5 (Bổ đề lặp hàm tiền tố — Prefix-function iteration lemma).** Cho P là mẫu độ dài m với hàm tiền tố π. Khi đó với q = 1, 2, …, m, π\*[q] = {k : k < q và P_k ⊐ P_q}.

*Chứng minh.* Trước hết chứng minh π\*[q] ⊆ {k : k < q và P_k ⊐ P_q}, hay tương đương

```text
i ∈ π*[q]  kéo theo  P_i ⊐ P_q                                         (32.7)
```

Nếu i ∈ π\*[q] thì i = π^(u)[q] với u > 0 nào đó. Chứng minh (32.7) bằng quy nạp theo u. Với u = 1, i = π[q], và khẳng định đúng vì i < q và P_{π[q]} ⊐ P_q theo định nghĩa π. Dùng các quan hệ π[i] < i và P_{π[i]} ⊐ P_i cùng tính bắc cầu của < và ⊐, khẳng định đúng với mọi i trong π\*[q]. Vậy π\*[q] ⊆ {k : k < q và P_k ⊐ P_q}.

Tiếp theo chứng minh {k : k < q và P_k ⊐ P_q} ⊆ π\*[q] bằng phản chứng. Giả sử ngược lại, tập {k : k < q và P_k ⊐ P_q} − π\*[q] khác rỗng, và gọi j là số lớn nhất trong tập đó. Vì π[q] là giá trị lớn nhất trong {k : k < q và P_k ⊐ P_q} và π[q] ∈ π\*[q], phải có j < π[q]. Gọi j′ là số nguyên nhỏ nhất trong π\*[q] lớn hơn j. (Có thể chọn j′ = π[q] nếu không có số nào khác trong π\*[q] lớn hơn j.) Ta có P_j ⊐ P_q vì j ∈ {k : k < q và P_k ⊐ P_q}, và từ j′ ∈ π\*[q] cùng (32.7) có P_{j′} ⊐ P_q. Do đó P_j ⊐ P_{j′} theo Bổ đề 32.1 (hai hậu tố của P_q, P_j ngắn hơn). Hơn nữa j là giá trị lớn nhất nhỏ hơn j′ có tính chất này (mọi k với j < k < j′ và P_k ⊐ P_{j′} thì cũng P_k ⊐ P_q, nên hoặc k thuộc π\*[q] — mâu thuẫn với cách chọn j′ là nhỏ nhất — hoặc k thuộc tập hiệu — mâu thuẫn với j lớn nhất). Vậy π[j′] = j, và vì j′ ∈ π\*[q] nên j = π[j′] ∈ π\*[q]. Mâu thuẫn này chứng minh bổ đề. ∎

(Phần giải thích trong ngoặc ở câu "j là giá trị lớn nhất nhỏ hơn j′ có tính chất này" là người tổng hợp viết rõ thêm; sách chỉ khẳng định.)

Thủ tục COMPUTE-PREFIX-FUNCTION tính π[q] theo thứ tự q = 1, 2, …, m. Gán π[1] = 0 ở dòng 3 chắc chắn đúng vì π[q] < q với mọi q. Bổ đề và hệ quả sau được dùng để chứng minh COMPUTE-PREFIX-FUNCTION tính đúng π[q] với q > 1.

**Bổ đề 32.6.** Cho P là mẫu độ dài m, π là hàm tiền tố của P. Với q = 1, 2, …, m, nếu π[q] > 0 thì π[q] − 1 ∈ π\*[q − 1].

*Chứng minh.* Đặt r = π[q] > 0, nên r < q và P_r ⊐ P_q; do đó r − 1 < q − 1 và P_{r−1} ⊐ P_{q−1} (bỏ ký tự cuối khỏi P_r và P_q, làm được vì r > 0). Theo Bổ đề 32.5, r − 1 ∈ π\*[q − 1]. Vậy π[q] − 1 = r − 1 ∈ π\*[q − 1]. ∎

Với q = 2, 3, …, m, định nghĩa tập con E_{q−1} ⊆ π\*[q − 1] bởi

```text
E_{q−1} = {k ∈ π*[q − 1] : P[k + 1] = P[q]}
        = {k : k < q − 1 và P_k ⊐ P_{q−1} và P[k + 1] = P[q]}   (theo Bổ đề 32.5)
        = {k : k < q − 1 và P_{k+1} ⊐ P_q}
```

Tập E_{q−1} gồm các giá trị k < q − 1 sao cho P_k ⊐ P_{q−1} và, vì P[k + 1] = P[q], ta có P_{k+1} ⊐ P_q. Nghĩa là E_{q−1} gồm những k ∈ π\*[q − 1] mà ta có thể kéo dài P_k thành P_{k+1} để được một hậu tố thực sự của P_q.

**Hệ quả 32.7.** Cho P là mẫu độ dài m, π là hàm tiền tố của P. Với q = 2, 3, …, m,

```text
π[q] = 0                       nếu E_{q−1} = ∅
π[q] = 1 + max {k ∈ E_{q−1}}   nếu E_{q−1} ≠ ∅
```

*Chứng minh.* Nếu E_{q−1} rỗng, không có k ∈ π\*[q − 1] (kể cả k = 0) nào mà ta kéo dài P_k thành P_{k+1} để được hậu tố thực sự của P_q. Do đó π[q] = 0 (giải thích thêm của người tổng hợp: mọi hậu tố thực sự khác rỗng P_j của P_q đều có dạng P_{k+1} với k = j − 1 ∈ π\*[q − 1] theo Bổ đề 32.6, nên không tồn tại j > 0).

Nếu E_{q−1} khác rỗng, với mỗi k ∈ E_{q−1} có k + 1 < q và P_{k+1} ⊐ P_q. Do đó, từ định nghĩa π[q],

```text
π[q] ≥ 1 + max {k ∈ E_{q−1}}                                           (32.8)
```

Lưu ý π[q] > 0. Đặt r = π[q] − 1, nên r + 1 = π[q] và do đó P_{r+1} ⊐ P_q. Vì r + 1 > 0, ta có P[r + 1] = P[q]. Hơn nữa, theo Bổ đề 32.6, r ∈ π\*[q − 1]. Vậy r ∈ E_{q−1}, nên r ≤ max {k ∈ E_{q−1}}, hay tương đương

```text
π[q] ≤ 1 + max {k ∈ E_{q−1}}                                           (32.9)
```

Kết hợp (32.8) và (32.9) hoàn tất chứng minh. ∎

**Hoàn tất chứng minh COMPUTE-PREFIX-FUNCTION đúng.** Trong thủ tục, đầu mỗi vòng lặp for dòng 5–10, ta có k = π[q − 1]. Điều kiện này được bảo đảm bởi dòng 3 và 4 khi vào vòng lặp lần đầu (k = 0 = π[1] khi q = 2), và tiếp tục đúng ở mỗi vòng sau nhờ dòng 10. Dòng 6–9 điều chỉnh k để nó trở thành giá trị đúng của π[q]. Vòng while dòng 6–7 duyệt qua mọi giá trị k ∈ π\*[q − 1] (theo thứ tự giảm dần) cho tới khi gặp một giá trị k với P[k + 1] = P[q]; lúc đó k là giá trị lớn nhất trong E_{q−1}, nên theo Hệ quả 32.7 có thể gán π[q] = k + 1. Nếu vòng while không tìm được k ∈ π\*[q − 1] nào với P[k + 1] = P[q] thì k bằng 0 ở dòng 8. Nếu P[1] = P[q], cần gán cả k và π[q] bằng 1; ngược lại để nguyên k và gán π[q] = 0. Dòng 8–10 gán k và π[q] đúng trong cả hai trường hợp. Điều này hoàn tất chứng minh tính đúng của COMPUTE-PREFIX-FUNCTION.

Liên hệ với ví dụ chạy tay ở trên: ở q = 6 (P[6] = c), k = π[5] = 3; π\*[5] = {3, 1, 0}; vòng while thử k = 3 (P[4] = b ≠ c), k = 1 (P[2] = b ≠ c), dừng ở k = 0; P[1] = a ≠ c nên E₅ = ∅ và π[6] = 0.

#### Tính đúng của thuật toán Knuth-Morris-Pratt (Correctness of the Knuth-Morris-Pratt algorithm)

Có thể coi KMP-MATCHER là bản cài đặt lại của FINITE-AUTOMATON-MATCHER, nhưng dùng hàm tiền tố π để tính các phép chuyển trạng thái. Cụ thể, ta sẽ chứng minh rằng ở vòng lặp thứ i của các vòng for trong cả KMP-MATCHER và FINITE-AUTOMATON-MATCHER, trạng thái q có cùng giá trị khi ta kiểm tra bằng m (ở dòng 10 của KMP-MATCHER và dòng 5 của FINITE-AUTOMATON-MATCHER). Một khi đã lập luận KMP-MATCHER mô phỏng hành vi của FINITE-AUTOMATON-MATCHER, tính đúng của KMP-MATCHER suy ra từ tính đúng của FINITE-AUTOMATON-MATCHER (dù lát nữa sẽ thấy vì sao dòng 12 của KMP-MATCHER là cần thiết).

**Trực giác: π thay thế δ ra sao.** Khi ôtômat ở trạng thái q và quét ký tự a = T[i], nó chuyển sang trạng thái δ(q, a). Nếu a = P[q + 1], tức a tiếp tục khớp mẫu, thì δ(q, a) = q + 1. Ngược lại, a ≠ P[q + 1], a không tiếp tục khớp, và 0 ≤ δ(q, a) ≤ q. Ở trường hợp thứ nhất, khi a tiếp tục khớp, KMP-MATCHER chuyển sang trạng thái q + 1 mà không cần tham chiếu hàm π: phép thử vòng while ở dòng 6 sai ngay lần đầu, phép thử ở dòng 8 đúng, và dòng 9 tăng q.

Hàm π vào cuộc khi ký tự a không tiếp tục khớp mẫu, nên trạng thái mới δ(q, a) là q hoặc nằm bên trái q dọc xương sống của ôtômat. Vòng while ở dòng 6–7 của KMP-MATCHER duyệt các trạng thái trong π\*[q], dừng khi tới một trạng thái q′ mà a khớp P[q′ + 1], hoặc khi q′ đã lùi về tới 0. Nếu a khớp P[q′ + 1], dòng 9 gán trạng thái mới là q′ + 1, giá trị này phải bằng δ(q, a) để phép mô phỏng đúng. Nói cách khác, trạng thái mới δ(q, a) phải là trạng thái 0 hoặc lớn hơn một đơn vị so với một trạng thái nào đó trong π\*[q].

**Ví dụ (dùng ôtômat và hàm tiền tố của P = ababaca ở trên).** Giả sử ôtômat ở trạng thái q = 5; các trạng thái trong π\*[5], theo thứ tự giảm dần, là 3, 1 và 0.

- Nếu ký tự quét tiếp là c, dễ thấy ôtômat chuyển sang δ(5, c) = 6 trong cả FINITE-AUTOMATON-MATCHER và KMP-MATCHER.
- Nếu ký tự quét tiếp là b, ôtômat phải chuyển sang δ(5, b) = 4. Vòng while trong KMP-MATCHER thoát sau khi thực hiện dòng 7 một lần, và tới trạng thái q′ = π[5] = 3. Vì P[q′ + 1] = P[4] = b, phép thử ở dòng 8 đúng, và KMP-MATCHER chuyển sang trạng thái mới q′ + 1 = 4 = δ(5, b).
- Nếu ký tự quét tiếp là a, ôtômat phải chuyển sang δ(5, a) = 1. Ba lần đầu thực hiện phép thử ở dòng 6, phép thử đúng. Lần thứ nhất, P[6] = c ≠ a, và KMP-MATCHER chuyển sang trạng thái π[5] = 3 (trạng thái thứ nhất trong π\*[5]). Lần thứ hai, P[4] = b ≠ a, và chuyển sang π[3] = 1 (trạng thái thứ hai trong π\*[5]). Lần thứ ba, P[2] = b ≠ a, và chuyển sang π[1] = 0 (trạng thái cuối trong π\*[5]). Vòng while thoát khi tới trạng thái q′ = 0. Lúc này dòng 8 thấy P[q′ + 1] = P[1] = a, và dòng 9 đưa ôtômat sang trạng thái mới q′ + 1 = 1 = δ(5, a).

Vậy trực giác là: KMP-MATCHER duyệt các trạng thái trong π\*[q] theo thứ tự giảm, dừng ở một trạng thái q′ nào đó rồi có thể chuyển sang q′ + 1. Có vẻ nhiều việc chỉ để mô phỏng việc tính δ(q, a), nhưng hãy nhớ rằng về mặt tiệm cận KMP-MATCHER không chậm hơn FINITE-AUTOMATON-MATCHER.

**Chứng minh hình thức.** Theo Định lý 32.4, q = σ(T_i) sau mỗi lần thực hiện dòng 4 của FINITE-AUTOMATON-MATCHER. Vì vậy chỉ cần chứng minh tính chất tương tự cho vòng for của KMP-MATCHER. Chứng minh quy nạp theo số vòng lặp. Ban đầu cả hai thủ tục gán q = 0 khi vào vòng for lần đầu. Xét vòng lặp thứ i của vòng for trong KMP-MATCHER, gọi q′ là trạng thái đầu vòng lặp này. Theo giả thiết quy nạp, q′ = σ(T_{i−1}). Cần chứng minh q = σ(T_i) ở dòng 10. (Dòng 12 lại được xử lý riêng.)

Khi xét ký tự T[i], tiền tố dài nhất của P là hậu tố của T_i là P_{q′+1} (nếu P[q′ + 1] = T[i]) hoặc một tiền tố nào đó (không nhất thiết thực sự, có thể rỗng) của P_{q′}. Xét riêng ba trường hợp σ(T_i) = 0, σ(T_i) = q′ + 1 và 0 < σ(T_i) ≤ q′.

- **Nếu σ(T_i) = 0**, thì P₀ = ε là tiền tố duy nhất của P là hậu tố của T_i. Vòng while dòng 6–7 duyệt các giá trị trong π\*[q′], nhưng dù P_q ⊐ T_{i−1} với mọi q ∈ π\*[q′] (sách in "P_q ⊐ T_i", xem khối Lưu ý), vòng lặp không bao giờ tìm được q nào với P[q + 1] = T[i] (nếu có thì P_{q+1} ⊐ T_i, trái với σ(T_i) = 0). Vòng lặp kết thúc khi q về 0, và tất nhiên dòng 9 không thực hiện (P[1] ≠ T[i], cũng vì σ(T_i) = 0). Vậy q = 0 ở dòng 10, tức q = σ(T_i).
- **Nếu σ(T_i) = q′ + 1**, thì P[q′ + 1] = T[i], và phép thử vòng while ở dòng 6 sai ngay lần đầu. Dòng 9 thực hiện, tăng q nên sau đó q = q′ + 1 = σ(T_i).
- **Nếu 0 < σ(T_i) ≤ q′**, thì vòng while dòng 6–7 lặp ít nhất một lần, kiểm tra theo thứ tự giảm từng giá trị q ∈ π\*[q′] cho tới khi dừng ở một q < q′ nào đó. Như vậy P_q là tiền tố dài nhất của P_{q′} mà P[q + 1] = T[i] (Bổ đề 32.5 bảo đảm vòng lặp không bỏ sót ứng viên nào), nên khi vòng while kết thúc, q + 1 = σ(P_{q′} T[i]). Vì q′ = σ(T_{i−1}), Bổ đề 32.3 cho σ(T_{i−1} T[i]) = σ(P_{q′} T[i]). Do đó

```text
q + 1 = σ(P_{q′} T[i])
      = σ(T_{i−1} T[i])
      = σ(T_i)
```

  khi vòng while kết thúc. Sau khi dòng 9 tăng q, ta có q = σ(T_i).

**Vì sao cần dòng 12.** Dòng 12 cần thiết trong KMP-MATCHER, vì nếu không, sau khi tìm được một lần xuất hiện của P (q = m), lần thực hiện kế tiếp của dòng 6 có thể tham chiếu P[m + 1] — ở ngoài mảng. (Lập luận rằng q = σ(T_{i−1}) vẫn đúng ở lần thực hiện kế tiếp của dòng 6 dựa vào gợi ý của Exercise 32.4-8: δ(m, a) = δ(π[m], a), hay tương đương σ(Pa) = σ(P_{π[m]} a), với mọi a ∈ Σ.) Phần còn lại của lập luận về tính đúng của KMP suy ra từ tính đúng của FINITE-AUTOMATON-MATCHER, vì ta đã chứng minh KMP-MATCHER mô phỏng hành vi của FINITE-AUTOMATON-MATCHER.

Ví dụ (người tổng hợp): với P = aa, T = aaa: sau i = 2, q = 2 = m, in độ dịch 0, dòng 12 gán q = π[2] = 1; ở i = 3, P[2] = a khớp, q = 2: in độ dịch 1. Nếu bỏ dòng 12, ở i = 3 dòng 6 sẽ so P[3] — không tồn tại. Nhờ q = π[m], KMP tìm được cả các lần xuất hiện chồng lên nhau.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hàm tiền tố (thường gọi là "failure function" hay mảng "lps" — longest proper prefix which is also suffix) là một trong những công cụ chuỗi được dùng nhiều nhất trong lập trình thi đấu: tìm chu kỳ ngắn nhất của chuỗi (q − π[q], như Problem 32-1), đếm số lần xuất hiện của mọi tiền tố, nén chuỗi, và làm nền cho ôtômat Aho–Corasick (hàm thất bại trên cây trie là tổng quát hoá trực tiếp của π). Trong thư viện chuẩn, KMP thuần ít được dùng hơn các biến thể Boyer–Moore (bỏ qua nhiều ký tự trên văn bản tự nhiên) hay Two-Way; nhưng ý tưởng "không bao giờ lùi con trỏ văn bản" của KMP rất quý khi văn bản đến dạng luồng (stream) — gói tin mạng, tệp quá lớn để đọc lại — vì KMP chỉ cần giữ trạng thái q.

## Bài tập và bài toán cuối chương

### Bài tập Mục 32.1 (trang 989–990)

- **32.1-1:** Chỉ ra các phép so sánh mà thuật toán ngây thơ thực hiện với mẫu P = 0001 trong văn bản T = 000010001010001. *Lời giải của người tổng hợp* (n = 15, m = 4, s = 0..11; T theo vị trí: 1–4 = 0000, 5 = 1, 6–8 = 000, 9 = 1, 10 = 0, 11 = 1, 12–14 = 000, 15 = 1):

  | s | Cửa sổ T[s+1..s+4] | So sánh (dừng ở chỗ khác đầu tiên) | Số phép so | Kết quả |
  |---|---|---|---|---|
  | 0 | 0000 | 0=0, 0=0, 0=0, 1≠0 | 4 | không |
  | 1 | 0001 | khớp cả 4 | 4 | **hợp lệ** |
  | 2 | 0010 | 0=0, 0=0, 0≠1 | 3 | không |
  | 3 | 0100 | 0=0, 0≠1 | 2 | không |
  | 4 | 1000 | 0≠1 | 1 | không |
  | 5 | 0001 | khớp cả 4 | 4 | **hợp lệ** |
  | 6 | 0010 | 0=0, 0=0, 0≠1 | 3 | không |
  | 7 | 0101 | 0=0, 0≠1 | 2 | không |
  | 8 | 1010 | 0≠1 | 1 | không |
  | 9 | 0100 | 0=0, 0≠1 | 2 | không |
  | 10 | 1000 | 0≠1 | 1 | không |
  | 11 | 0001 | khớp cả 4 | 4 | **hợp lệ** |

  Độ dịch hợp lệ: 1, 5, 11; tổng 31 phép so ký tự (so với tối đa 12 · 4 = 48).
- **32.1-2:** Giả sử mọi ký tự của P khác nhau. Chỉ cách tăng tốc NAIVE-STRING-MATCHER để chạy O(n) trên văn bản n ký tự. *Người tổng hợp:* nếu ở độ dịch s đã khớp q ký tự rồi gặp chỗ khác (hoặc khớp hết, q = m), thì có thể nhảy thẳng tới độ dịch s + max(1, q): với 0 < d < q, độ dịch s + d đặt P[1] lên T[s + d + 1] = P[d + 1] ≠ P[1] (các ký tự khác nhau), nên không hợp lệ. Mỗi phép so ký tự khớp làm con trỏ văn bản tiến một ô, mỗi phép so không khớp kết thúc một độ dịch; tổng O(n).
- **32.1-3:** Giả sử P và T là chuỗi chọn ngẫu nhiên độ dài m và n trên bảng chữ d ký tự Σ_d = {0, 1, …, d − 1}, d ≥ 2. Chứng minh số phép so ký tự kỳ vọng của vòng lặp ngầm ở dòng 4, trên mọi lần thực hiện vòng lặp này, là (n − m + 1)(1 − d^{−m})/(1 − d^{−1}) ≤ 2(n − m + 1). (Giả định thuật toán ngừng so ở một độ dịch khi gặp chỗ khác hoặc khớp hết.) Vậy với chuỗi ngẫu nhiên, thuật toán ngây thơ khá hiệu quả. *Người tổng hợp:* ở một độ dịch, phép so thứ k (k = 1..m) được thực hiện khi và chỉ khi k − 1 cặp đầu khớp, xác suất d^{−(k−1)}. Kỳ vọng mỗi độ dịch = Σ_{k=1}^{m} d^{−(k−1)} = (1 − d^{−m})/(1 − d^{−1}) ≤ 1/(1 − 1/d) ≤ 2 vì d ≥ 2. Nhân với n − m + 1 độ dịch (tuyến tính kỳ vọng). Ví dụ d = 2, m = 3: 1 + 1/2 + 1/4 = 1,75.
- **32.1-4:** Cho phép mẫu P chứa ký tự khoảng trống ◇ (gap character), khớp với một chuỗi *bất kỳ* (kể cả độ dài 0). Ví dụ mẫu ab◇ba◇c xuất hiện trong văn bản cabccbacbacab theo hai cách: c·ab·cc·ba·cba·c·ab (◇ khớp cc, rồi ◇ khớp cba) và c·ab·ccbac·ba·(rỗng)·c·ab (◇ khớp ccbac, rồi ◇ khớp chuỗi rỗng). ◇ có thể xuất hiện nhiều lần trong mẫu nhưng không xuất hiện trong văn bản. Cho thuật toán thời gian đa thức xác định P có xuất hiện trong T không, và phân tích thời gian. *Người tổng hợp:* tách P theo ◇ thành các đoạn P⁽¹⁾, …, P⁽ᵏ⁾ (không chứa ◇). Tham lam: tìm lần xuất hiện *sớm nhất* của P⁽¹⁾ trong T, rồi lần xuất hiện sớm nhất của P⁽²⁾ bắt đầu sau khi P⁽¹⁾ kết thúc, v.v.; P xuất hiện khi và chỉ khi tìm được hết. Tham lam đúng vì kết thúc càng sớm càng để lại nhiều văn bản cho các đoạn sau. Với thuật toán ngây thơ: O(n · m); với KMP cho từng đoạn bắt đầu từ vị trí hiện tại: O(n + m) tổng cộng. (Nếu mẫu không bắt đầu/kết thúc bằng ◇ và yêu cầu "xuất hiện" là xuất hiện như một chuỗi con thì không cần ràng buộc gì thêm, vì chuỗi con có thể bắt đầu và kết thúc ở bất kỳ đâu.)

### Bài tập Mục 32.2 (trang 994–995)

- **32.2-1:** Làm việc theo modulo q = 11, Rabin-Karp gặp bao nhiêu lần trúng giả trong văn bản T = 3141592653589793 khi tìm mẫu P = 26? *Lời giải của người tổng hợp:* p = 26 mod 11 = 4. Các cửa sổ độ dài 2 và giá trị mod 11:

  | s | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
  |---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
  | cửa sổ | 31 | 14 | 41 | 15 | 59 | 92 | 26 | 65 | 53 | 35 | 58 | 89 | 97 | 79 | 93 |
  | mod 11 | 9 | 3 | 8 | **4** | **4** | **4** | **4** | 10 | 9 | 2 | 3 | 1 | 9 | 2 | 5 |

  Bốn cửa sổ có giá trị 4: 15, 59, 92 là trúng giả, 26 (s = 6) là khớp thật. **Đáp số: 3 lần trúng giả.**
- **32.2-2:** Mở rộng Rabin-Karp cho bài toán tìm trong văn bản một lần xuất hiện của bất kỳ mẫu nào trong một tập k mẫu? Trước hết giả sử k mẫu cùng độ dài, rồi tổng quát cho mẫu khác độ dài. *Người tổng hợp:* cùng độ dài m: tính k giá trị pⱼ mod q, đặt vào một bảng băm (hoặc mảng đã sắp xếp); với mỗi cửa sổ t_s, tra xem t_s có trong bảng không (O(1) kỳ vọng), nếu có thì so ký tự với các mẫu có cùng giá trị. Thời gian kỳ vọng O(n + km) cộng chi phí các lần khớp. Khác độ dài: nhóm mẫu theo độ dài; với mỗi độ dài khác nhau L chạy một băm cuộn riêng (cửa sổ độ dài L); nếu có ℓ độ dài khác nhau thì O(ℓn + Σ|Pⱼ|) kỳ vọng.
- **32.2-3:** Mở rộng Rabin-Karp để tìm mẫu m × m trong một mảng ký tự n × n (mẫu có thể dịch dọc và ngang, không được xoay). *Người tổng hợp:* bước 1: với mỗi cột của văn bản, tính băm cuộn theo chiều dọc cho mọi đoạn cột dài m (O(n²) tổng). Bước 2: coi mỗi giá trị cột là một "ký tự" trong cơ số lớn d′, rồi với mỗi dải m hàng chạy băm cuộn theo chiều ngang trên các giá trị cột (O(n) mỗi dải, O(n²) tổng). Băm mẫu theo cùng cách; khi trùng thì so trực tiếp m² ký tự. Kỳ vọng O(n² + m²) khi ít lần khớp.
- **32.2-4:** Alice có tệp n bit A = ⟨a_{n−1}, …, a₀⟩, Bob có B = ⟨b_{n−1}, …, b₀⟩. Để khỏi truyền cả tệp, họ cùng chọn số nguyên tố q > 1000n và chọn ngẫu nhiên x ∈ {0, 1, …, q − 1}. Alice tính A(x) = (Σ_{i=0}^{n−1} aᵢ xⁱ) mod q, Bob tính B(x) tương tự. Chứng minh nếu A ≠ B thì xác suất A(x) = B(x) nhiều nhất 1/1000, còn nếu hai tệp như nhau thì A(x) chắc chắn bằng B(x). (Gợi ý: Exercise 31.4-4.) *Người tổng hợp:* nếu A = B thì hai đa thức trùng nhau nên hiển nhiên bằng nhau. Nếu A ≠ B, đa thức C(x) = A(x) − B(x) có hệ số trong {−1, 0, 1}, không đồng nhất bằng 0 theo modulo q (vì q > 1), bậc ≤ n − 1. Trên trường Z_q (q nguyên tố), một đa thức khác 0 bậc ≤ n − 1 có nhiều nhất n − 1 nghiệm (Exercise 31.4-4). Xác suất x ngẫu nhiên rơi vào một nghiệm ≤ (n − 1)/q < n/(1000n) = 1/1000.

### Bài tập Mục 32.3 (trang 1002)

- **32.3-1:** Dựng ôtômat so khớp chuỗi cho mẫu P = aabab và minh hoạ hoạt động của nó trên văn bản T = aaababaabaababaab. *Lời giải của người tổng hợp* (Σ = {a, b}, m = 5):

  | q | P_q | đọc a | đọc b |
  |---|---|---|---|
  | 0 | ε | **1** | 0 |
  | 1 | a | **2** | 0 |
  | 2 | aa | 2 | **3** |
  | 3 | aab | **4** | 0 |
  | 4 | aaba | 2 | **5** |
  | 5 | aabab | 1 | 0 |

  (Ví dụ δ(2, a) = σ(aaa) = 2; δ(4, a) = σ(aabaa) = 2; δ(5, a) = σ(aababa) = 1; δ(1, b) = σ(ab) = 0.) Chạy trên T (17 ký tự):

  | i | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 |
  |---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
  | T[i] | a | a | a | b | a | b | a | a | b | a | a | b | a | b | a | a | b |
  | φ(T_i) | 1 | 2 | 2 | 3 | 4 | **5** | 1 | 2 | 3 | 4 | 2 | 3 | 4 | **5** | 1 | 2 | 3 |

  Hai lần xuất hiện: kết thúc ở vị trí 6 (độ dịch 1, T[2..6] = aabab) và ở vị trí 14 (độ dịch 9, T[10..14] = aabab).
- **32.3-2:** Vẽ sơ đồ chuyển trạng thái của ôtômat so khớp chuỗi cho mẫu ababbabbababbababbabb trên Σ = {a, b}. *Lời giải của người tổng hợp* (m = 21; tính qua hàm tiền tố π = 0 0 1 2 0 1 2 0 1 2 3 4 5 6 7 3 4 5 6 7 8 và quy tắc của Exercise 32.4-8: δ(q, a) = q + 1 nếu P[q + 1] = a, ngược lại δ(π[q], a)). Thay cho hình vẽ, bảng chuyển (cạnh xương sống in đậm):

  | q | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 |
  |---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
  | P[q+1] | a | b | a | b | b | a | b | b | a | b | a | b | b | a | b | a | b | b | a | b | b | — |
  | δ(q, a) | **1** | 1 | **3** | 1 | 3 | **6** | 1 | 3 | **9** | 1 | **11** | 1 | 3 | **14** | 1 | **16** | 1 | 3 | **19** | 1 | 3 | 9 |
  | δ(q, b) | 0 | **2** | 0 | **4** | **5** | 0 | **7** | **8** | 0 | **10** | 0 | **12** | **13** | 0 | **15** | 8 | **17** | **18** | 0 | **20** | **21** | 0 |

  Sơ đồ: xương sống 0 → 1 → … → 21 theo các ký tự của P; cạnh lùi nhãn a về 1 hoặc 3 (hoặc 9 từ trạng thái 21), cạnh lùi nhãn b về 0 hoặc 8 (từ 15). Kiểm tra một ô: δ(15, b): P₁₅b = ababbabbababbabb, hậu tố dài nhất là tiền tố của P là ababbabb = P₈.
- **32.3-3:** Gọi mẫu P là **không tự chồng** (nonoverlappable) nếu P_k ⊐ P_q kéo theo k = 0 hoặc k = q. Mô tả sơ đồ chuyển trạng thái của ôtômat so khớp chuỗi cho mẫu không tự chồng. *Người tổng hợp:* với mọi q, δ(q, P[q + 1]) = q + 1 (xương sống); với ký tự a ≠ P[q + 1] (và mọi a khi q = m): δ(q, a) = 1 nếu a = P[1], ngược lại 0. Lý do: nếu P_k ⊐ P_q a với 1 < k ≤ q thì P_{k−1} ⊐ P_q với 0 < k − 1 < q, trái giả thiết. Như vậy mọi cạnh lùi đều về trạng thái 0 hoặc 1. Ví dụ P = aab không tự chồng? π = 0 1 0: P₁ = a ⊐ P₂ = aa với 0 < 1 < 2, nên aab *không* phải không tự chồng; P = abb thì là (π = 0 0 0).
- **32.3-4 ★:** Cho hai mẫu P và P′, mô tả cách dựng một ôtômat hữu hạn xác định mọi lần xuất hiện của *một trong hai* mẫu. Cố gắng giảm số trạng thái. *Người tổng hợp:* cách 1: ôtômat tích, trạng thái là cặp (q, q′) của hai ôtômat riêng, chấp nhận khi q = m hoặc q′ = m′; chỉ giữ các cặp đến được. Cách 2 (ít trạng thái hơn): trạng thái là các chuỗi vừa là tiền tố của P hoặc của P′ (hai mẫu có chung tiền tố thì chung trạng thái — một cây trie), tối đa m + m′ + 1 trạng thái; δ(x, a) là chuỗi dài nhất trong tập trạng thái là hậu tố của xa; trạng thái x chấp nhận khi P ⊐ x hoặc P′ ⊐ x. Đây là ý tưởng của ôtômat Aho–Corasick (theo hiểu biết của người tổng hợp).
- **32.3-5:** Cho mẫu P chứa ký tự khoảng trống (Exercise 32.1-4), chỉ cách dựng ôtômat hữu hạn tìm một lần xuất hiện của P trong T trong thời gian khớp O(n), n = |T|. *Người tổng hợp:* tách P thành các đoạn P⁽¹⁾, …, P⁽ᵏ⁾; dựng ôtômat so khớp cho từng đoạn và nối tiếp: trạng thái chấp nhận của ôtômat đoạn j được thay bằng trạng thái bắt đầu của ôtômat đoạn j + 1 (không quay lại đoạn trước), trạng thái chấp nhận cuối cùng là cuối đoạn k (và ở lại đó). Đây là cài đặt tham lam của Exercise 32.1-4 dưới dạng một ôtômat; mỗi ký tự văn bản một phép chuyển, O(n).

### Bài tập Mục 32.4 (trang 1011–1012)

- **32.4-1:** Tính hàm tiền tố π cho mẫu ababbabbabbababbabb. *Lời giải của người tổng hợp* (m = 19):

  | i | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 |
  |---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
  | P[i] | a | b | a | b | b | a | b | b | a | b | b | a | b | a | b | b | a | b | b |
  | π[i] | 0 | 0 | 1 | 2 | 0 | 1 | 2 | 0 | 1 | 2 | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |

  Ví dụ π[19] = 8: tám ký tự cuối P[12..19] = ababbabb = P₈; P₉ = ababbabba kết thúc bằng a nên không thể dài hơn. π[14] = 3: ở q = 14, k = π[13] = 2, P[3] = a = P[14] nên k = 3.
- **32.4-2:** Cho cận trên của kích thước |π\*[q]| theo q, và ví dụ chứng tỏ cận chặt. *Người tổng hợp:* các phần tử của π\*[q] giảm ngặt và nằm trong {0, …, q − 1}, nên |π\*[q]| ≤ q. Chặt với P = aᵐ: π[q] = q − 1, nên π\*[q] = {q − 1, q − 2, …, 0}, có đúng q phần tử.
- **32.4-3:** Giải thích cách xác định các lần xuất hiện của P trong T bằng cách xem hàm π của chuỗi PT (chuỗi độ dài m + n nối P và T). *Người tổng hợp:* P xuất hiện kết thúc tại T[i] khi và chỉ khi P là hậu tố của (PT)_{m+i}, tức m ∈ π\*[m + i] (Bổ đề 32.5) với i ≥ m. Chỉ xem π[m + i] = m là chưa đủ khi π có thể vượt m; cách gọn nhất là chèn một ký tự phân cách # ∉ Σ: tính π cho P#T, khi đó π không bao giờ vượt m, và P xuất hiện với độ dịch i − m khi và chỉ khi π[m + 1 + i] = m. Thời gian Θ(m + n).
- **32.4-4:** Dùng phân tích gộp chứng minh thời gian chạy của KMP-MATCHER là Θ(n). *Người tổng hợp:* như COMPUTE-PREFIX-FUNCTION, với q đóng vai k: q bắt đầu bằng 0, chỉ tăng ở dòng 9 (≤ 1 lần mỗi vòng for, tổng ≤ n), mỗi lần thực hiện dòng 7 hoặc dòng 12 làm q giảm ít nhất 1 (vì π[q] < q), q ≥ 0. Vậy số lần thực hiện dòng 7 ≤ n; phần còn lại của mỗi vòng lặp là O(1). Tổng O(n), và Ω(n) vì phải đọc mọi ký tự. (Cộng Θ(m) cho COMPUTE-PREFIX-FUNCTION ở dòng 3.)
- **32.4-5:** Dùng hàm thế năng chứng minh thời gian chạy của KMP-MATCHER là Θ(n). *Người tổng hợp:* chọn thế năng Φ = q (≥ 0, ban đầu 0). Một vòng for với w lần lặp while có chi phí thực 1 + w; mỗi lần lặp while làm Φ giảm ít nhất 1, dòng 9 làm Φ tăng nhiều nhất 1, dòng 12 làm Φ giảm. Chi phí khấu hao ≤ (1 + w) + (1 − w) = 2. Tổng chi phí thực ≤ tổng chi phí khấu hao = 2n.
- **32.4-6:** Cải tiến KMP-MATCHER bằng cách thay π ở dòng 7 (nhưng không ở dòng 12) bằng π′, định nghĩa đệ quy với q = 1, 2, …, m − 1 bởi: π′[q] = 0 nếu π[q] = 0; π′[q] = π′[π[q]] nếu π[q] ≠ 0 và P[π[q] + 1] = P[q + 1]; π′[q] = π[q] nếu π[q] ≠ 0 và P[π[q] + 1] ≠ P[q + 1]. Giải thích vì sao thuật toán sửa đổi đúng, và cải tiến theo nghĩa nào. *Người tổng hợp:* dòng 7 chỉ chạy khi P[q + 1] ≠ T[i]. Nếu P[π[q] + 1] = P[q + 1] thì trạng thái π[q] chắc chắn cũng thất bại với cùng ký tự T[i], nên nhảy thẳng qua nó (tới π′[π[q]]) không bỏ sót trạng thái nào có thể thành công; trạng thái 0 vẫn được xử lý như cũ. Cải tiến: giảm số lần lặp while trong mỗi lần không khớp (số bước lùi liên tiếp với cùng một ký tự văn bản), không đổi bậc Θ(n). Ví dụ P = ababaca: π = 0 0 1 2 3 0 1, π′[1..6] = 0 0 0 0 3 0 (π′[3] = 0 vì P[2] = P[4] = b; π′[4] = 0 vì P[3] = P[5] = a; π′[5] = 3 vì P[4] = b ≠ P[6] = c). Dòng 12 phải giữ π vì sau một lần khớp trọn vẹn không có ký tự nào vừa thất bại.
- **32.4-7:** Cho thuật toán thời gian tuyến tính xác định văn bản T có là phép quay vòng của chuỗi T′ không. Ví dụ arc và car là phép quay vòng của nhau. *Người tổng hợp:* T là phép quay vòng của T′ khi và chỉ khi |T| = |T′| và T xuất hiện trong T′T′. Dùng KMP tìm T trong T′T′: Θ(n). Ví dụ T′ = car, T′T′ = carcar chứa arc ở độ dịch 1.
- **32.4-8 ★:** Cho thuật toán O(m|Σ|) tính hàm chuyển δ của ôtômat so khớp chuỗi cho mẫu P. (Gợi ý: chứng minh δ(q, a) = δ(π[q], a) nếu q = m hoặc P[q + 1] ≠ a.) *Người tổng hợp:* tính π trong Θ(m). Với q = 0: δ(0, a) = 1 nếu a = P[1], ngược lại 0. Với q = 1, …, m theo thứ tự tăng, với mỗi a: nếu q < m và P[q + 1] = a thì δ(q, a) = q + 1; ngược lại δ(q, a) = δ(π[q], a), giá trị đã tính vì π[q] < q. Mỗi ô O(1), tổng O(m|Σ|). Chứng minh gợi ý: khi a không tiếp tục khớp, mọi tiền tố của P là hậu tố của P_q a có dạng P_{k+1} với P_k là hậu tố thực sự của P_q, tức k ∈ π\*[q] (Bổ đề 32.5) — cũng chính là tập các hậu tố của P_{π[q]} cộng thêm chính P_{π[q]}; do đó σ(P_q a) = σ(P_{π[q]} a). Bảng 32.3-2 ở trên được tính bằng cách này.

### Problem 32-1: So khớp chuỗi dựa trên thừa số lặp (String matching based on repetition factors)

Ký hiệu yⁱ là chuỗi y nối với chính nó i lần; ví dụ (ab)³ = ababab. Chuỗi x ∈ Σ\* có **thừa số lặp** (repetition factor) r nếu x = yʳ với một chuỗi y ∈ Σ\* và r > 0. Gọi ρ(x) là r lớn nhất sao cho x có thừa số lặp r.

- **(a)** Cho thuật toán hiệu quả nhận mẫu P[1..m] và tính ρ(P_i) với i = 1, 2, …, m. Thời gian chạy? *Người tổng hợp:* tính π trong Θ(m). Với mỗi i, đặt ℓ = i − π[i] (chu kỳ nhỏ nhất của P_i: P[j] = P[j + ℓ] với mọi j hợp lệ). Nếu ℓ chia hết i thì ρ(P_i) = i/ℓ, ngược lại ρ(P_i) = 1. Lý do: P_i = yʳ với |y| = d khi và chỉ khi d | i và d là một chu kỳ của P_i. Nếu ℓ ∤ i mà có chu kỳ d | i với d < i, thì d ≤ i/2 và ℓ ≤ d, nên ℓ + d ≤ i; theo bổ đề chu kỳ Fine–Wilf (theo hiểu biết của người tổng hợp; sách không trình bày), gcd(ℓ, d) cũng là chu kỳ, mà ℓ nhỏ nhất nên ℓ | d | i — mâu thuẫn. Tổng thời gian Θ(m). Ví dụ P = ababab: π = 0 0 1 2 3 4; i = 6: ℓ = 2, ρ = 3; i = 4: ρ = 2; i = 5: ℓ = 2 không chia hết 5, ρ = 1.
- **(b)** Với mẫu P[1..m], định nghĩa ρ\*(P) = max_{1≤i≤m} ρ(P_i). Chứng minh nếu P chọn ngẫu nhiên từ tập mọi chuỗi nhị phân độ dài m thì kỳ vọng của ρ\*(P) là O(1). *Người tổng hợp:* P_i có thừa số lặp r′ ≥ 2 với |y| = j (i = jr′) khi và chỉ khi i ký tự đầu được xác định bởi j ký tự đầu, xác suất 2^{j − jr′}. Chặn hợp: Pr{ρ\*(P) ≥ r} ≤ Σ_{r′≥r} Σ_{j≥1} 2^{−j(r′−1)} = Σ_{r′≥r} 1/(2^{r′−1} − 1) ≤ Σ_{r′≥r} 2^{2−r′} = 2^{3−r} (với r ≥ 2). Do đó E[ρ\*] = Σ_{r≥1} Pr{ρ\* ≥ r} ≤ 1 + 1 + 1 + Σ_{r≥4} 2^{3−r} = 4 = O(1).
- **(c)** Lập luận rằng thuật toán sau tìm đúng mọi lần xuất hiện của P trong T[1..n] trong thời gian O(ρ\*(P)n + m):

```text
REPETITION-MATCHER(P, T)
 1  m = P.length
 2  n = T.length
 3  k = 1 + ρ*(P)
 4  q = 0
 5  s = 0
 6  while s ≤ n − m
 7      if T[s + q + 1] == P[q + 1]
 8          q = q + 1
 9          if q == m
10              print "Pattern occurs with shift" s
11      if q == m or T[s + q + 1] ≠ P[q + 1]
12          s = s + max(1, ⌈q/k⌉)
13          q = 0
```

  Thuật toán so mẫu từ trái sang ở độ dịch s; q là số ký tự đã khớp. Khi khớp trọn (q = m) hoặc gặp chỗ khác, nó dịch s thêm max(1, ⌈q/k⌉) và so lại từ đầu mẫu (q = 0). *Người tổng hợp — tính đúng:* giả sử ở độ dịch s đã khớp q ký tự và có độ dịch hợp lệ s + d với 0 < d < ⌈q/k⌉, tức dk < q. Khi đó P[1..q − d] = T[s + d + 1..s + q] = P[d + 1..q], nên P_q có chu kỳ d, kéo theo P_{dk} = (P_d)ᵏ, tức ρ(P_{dk}) ≥ k = 1 + ρ\*(P) > ρ\*(P) — mâu thuẫn. Vậy bước nhảy không bỏ sót độ dịch hợp lệ. *Thời gian:* mỗi độ dịch tốn q + 1 phép so; bước nhảy ít nhất max(1, q/k), nên q + 1 ≤ k · (bước nhảy) + 1; tổng các bước nhảy ≤ n, số độ dịch ≤ n − m + 1, nên tổng ≤ kn + n = O(ρ\*(P)n); cộng O(m) để tính ρ\*(P) bằng câu (a).

Sách ghi: thuật toán này là của Galil và Seiferas. Mở rộng các ý tưởng này nhiều hơn nữa, họ được một thuật toán so khớp chuỗi thời gian tuyến tính chỉ dùng O(1) bộ nhớ ngoài phần cần cho P và T.

### Ghi chú chương (Chapter notes, trang 1013)

- Quan hệ giữa so khớp chuỗi và lý thuyết ôtômat hữu hạn được bàn trong sách của **Aho, Hopcroft và Ullman** (tài liệu [5] của sách).
- Thuật toán Knuth-Morris-Pratt (tài liệu [214]) được phát minh độc lập bởi **Knuth và Pratt** và bởi **Morris**; họ công bố chung (bài "Fast pattern matching in strings", SIAM Journal on Computing, 1977 — tên và năm theo hiểu biết của người tổng hợp).
- **Reingold, Urban và Gries** (tài liệu [294]) cho một cách trình bày khác về thuật toán Knuth-Morris-Pratt.
- Thuật toán Rabin-Karp do **Karp và Rabin** đề xuất (tài liệu [201]; bài báo năm 1987 — theo hiểu biết của người tổng hợp).
- **Galil và Seiferas** (tài liệu [126]) cho một thuật toán so khớp chuỗi tất định, thời gian tuyến tính, thú vị, chỉ dùng O(1) bộ nhớ ngoài phần cần để lưu mẫu và văn bản.

## Luận điểm cốt lõi

### Mệnh đề

Tìm mọi lần xuất hiện của một mẫu độ dài m trong một văn bản độ dài n làm được trong thời gian Θ(n + m) trong trường hợp xấu nhất, độc lập với kích thước bảng chữ, bằng cách tiền xử lý mẫu một lần (hàm tiền tố π, Θ(m)) để khi quét văn bản không bao giờ phải lùi lại đọc ký tự đã đọc. Trên đường tới kết quả đó, chương chỉ ra hai ý tưởng có giá trị riêng: băm cuộn theo modulo một số nguyên tố (Rabin-Karp) — nhanh kỳ vọng và dễ tổng quát hoá; và mô hình ôtômat hữu hạn — chỉ cần nhớ một con số "độ dài tiền tố của mẫu đang khớp dở" là đủ thông tin về toàn bộ quá khứ.

### Giả định

- Văn bản và mẫu là mảng ký tự trên bảng chữ hữu hạn Σ, m ≤ n; truy cập ký tự bất kỳ tốn O(1) (mô hình RAM).
- Phép so sánh hai chuỗi cùng độ dài tốn Θ(t + 1), t là độ dài tiền tố chung dài nhất.
- Rabin-Karp: dq vừa một từ máy, nên các phép toán theo modulo q tốn O(1); phân tích kỳ vọng dựa trên giả định kinh nghiệm rằng "lấy dư theo q" hành xử như ánh xạ ngẫu nhiên (xác suất trúng giả 1/q mỗi độ dịch), và số độ dịch hợp lệ nhỏ.
- Ôtômat: bảng δ cỡ (m + 1)|Σ| được lưu sẵn, tra bảng O(1).
- KMP: không giả định gì về Σ ngoài việc so sánh bằng nhau hai ký tự tốn O(1).

### Cơ chế

1. Thuật toán ngây thơ thử từng độ dịch, so từ đầu mẫu mỗi lần: O((n − m + 1)m).
2. Rabin-Karp đổi phép so chuỗi O(m) thành phép so số O(1): giá trị cửa sổ theo modulo q được cập nhật bằng t_{s+1} = (d(t_s − T[s + 1]h) + T[s + m + 1]) mod q; chỉ khi t_s ≡ p mới so từng ký tự.
3. Ôtômat lưu trạng thái q = σ(T_i). Bổ đề 32.3 (σ(xa) = σ(P_q a) khi q = σ(x)) cho phép tính trạng thái mới chỉ từ q và ký tự mới, nên mọi phép chuyển tính trước được; mỗi ký tự văn bản một lần tra bảng.
4. KMP thay bảng δ bằng π: khi không khớp, lùi q qua π\*[q] (Bổ đề 32.5 bảo đảm dãy này liệt kê đủ mọi tiền tố là hậu tố của P_q) cho tới khi khớp hoặc về 0. Hệ quả 32.7 cho phép tính π bằng chính thủ tục ấy áp dụng cho P với P.
5. Thời gian tuyến tính đến từ phân tích khấu hao: q (hoặc k) tăng tối đa 1 mỗi ký tự, mỗi bước lùi làm nó giảm, nó không âm — tổng số bước lùi không vượt tổng số bước tiến.

### Bằng chứng và ví dụ tác giả đưa ra

- P = abaa trong T = abcabaabcabac: độ dịch hợp lệ duy nhất s = 3.
- Bảng so sánh bốn thuật toán: ngây thơ (0; O((n − m + 1)m)), Rabin-Karp (Θ(m); O((n − m + 1)m)), ôtômat (O(m|Σ|); Θ(n)), KMP (Θ(m); Θ(n)).
- Thuật toán ngây thơ trên P = aab, T = acaabc; trường hợp xấu nhất T = aⁿ, P = aᵐ; ví dụ P = aaab cho thấy thông tin bị lãng phí.
- Rabin-Karp: 31415 → 14152 bằng (32.1); bảng mười lăm giá trị modulo 13 với một khớp thật (vị trí 7) và một trúng giả (vị trí 13); phép tính (7 − 3·3)·10 + 2 ≡ 8 (mod 13).
- Ôtômat hai trạng thái chấp nhận chuỗi kết thúc bằng số lẻ chữ a (abaaa được chấp nhận, abbaa bị từ chối).
- Ôtômat cho ababaca (bảng 8 × 3) chạy trên abababacaba, tìm một lần khớp kết thúc ở vị trí 9.
- Các chứng minh: Bổ đề 32.1, 32.2, 32.3, Định lý 32.4; Bổ đề 32.5, 32.6, Hệ quả 32.7; phân tích gộp Θ(m) cho COMPUTE-PREFIX-FUNCTION.
- Hàm tiền tố ababaca: 0 0 1 2 3 0 1; π\*[5] = {3, 1, 0}; ví dụ trạng thái 5 với các ký tự c, b, a minh hoạ KMP mô phỏng δ.

### Kết luận và hàm ý cho người lập trình

- Với bài toán tìm một mẫu cố định trong văn bản lớn hoặc dạng luồng, KMP cho bảo đảm Θ(n + m) xấu nhất, không lùi con trỏ văn bản, bộ nhớ phụ Θ(m).
- Khi bảng chữ nhỏ và mẫu được dùng rất nhiều lần, bảng δ của ôtômat cho vòng lặp khớp đơn giản nhất (một lần tra bảng mỗi ký tự); khi bảng chữ lớn thì π gọn hơn nhiều.
- Rabin-Karp thích hợp khi cần so sánh nhiều chuỗi con với nhau hoặc tìm nhiều mẫu cùng độ dài, tìm mẫu hai chiều; luôn kiểm tra lại khi băm trùng (trừ khi chấp nhận sai số xác suất một cách có ý thức), và cẩn thận với số âm khi lấy dư.
- Thuật toán ngây thơ không "sai": trên dữ liệu ngẫu nhiên nó chỉ tốn khoảng ≤ 2 phép so mỗi độ dịch; nhưng dữ liệu thật hoặc dữ liệu đối kháng có thể đẩy nó tới Θ(nm).
- Mảng π là công cụ đa năng: chu kỳ của chuỗi (i − π[i]), số lần lặp (Problem 32-1), phép quay vòng (Exercise 32.4-7), dựng ôtômat trong O(m|Σ|) (Exercise 32.4-8).
- Hai lỗi cài đặt hay gặp: quên dòng 12 (q = π[q] sau khi khớp trọn) dẫn tới đọc P[m + 1]; lệch chỉ số giữa mảng bắt đầu từ 1 của sách và mảng bắt đầu từ 0 của ngôn ngữ lập trình.

### Trong ngôn ngữ khoa học máy tính

Bài toán: cho T ∈ Σⁿ, P ∈ Σᵐ, tìm {s : 0 ≤ s ≤ n − m, P ⊐ T_{s+m}}. NAIVE: O((n − m + 1)m), chặt với aⁿ, aᵐ. RABIN-KARP: tiền xử lý Θ(m), xấu nhất Θ((n − m + 1)m), kỳ vọng O(n) + O(m(v + n/q)) = O(n + m) khi v = O(1), q ≥ m. Ôtômat: Q = {0..m}, δ(q, a) = σ(P_q a), σ(x) = max{k : P_k ⊐ x}; bất biến φ(T_i) = σ(T_i); khớp Θ(n); tiền xử lý O(m³|Σ|) trực tiếp, O(m|Σ|) qua π. KMP: π[q] = max{k < q : P_k ⊐ P_q}; π\*[q] = {k < q : P_k ⊐ P_q}; π[q] = 1 + max E_{q−1} hoặc 0; tiền xử lý Θ(m), khớp Θ(n) (khấu hao, thế năng Φ = q); bộ nhớ Θ(m); không phụ thuộc |Σ|.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| string matching | so khớp chuỗi | tìm mọi vị trí xuất hiện của mẫu trong văn bản |
| text / pattern | văn bản / mẫu | T[1..n] / P[1..m], m ≤ n |
| alphabet Σ | bảng chữ | tập hữu hạn các ký tự |
| string | chuỗi | dãy hữu hạn ký tự |
| shift | độ dịch | P đặt sao cho P[1] trùng T[s + 1] |
| valid / invalid shift | độ dịch hợp lệ / không hợp lệ | T[s + 1..s + m] = P / ≠ P |
| occurs beginning at position s + 1 | xuất hiện bắt đầu tại vị trí s + 1 | cách nói tương đương "xuất hiện với độ dịch s" |
| preprocessing / matching | tiền xử lý / khớp | pha xử lý riêng mẫu / pha duyệt văn bản |
| naive (brute-force) algorithm | thuật toán ngây thơ (vét cạn) | thử mọi độ dịch |
| Σ\* (sigma-star) | Σ\* | tập mọi chuỗi hữu hạn trên Σ |
| empty string ε | chuỗi rỗng | chuỗi độ dài 0 |
| concatenation | phép nối | xy: x rồi tới y |
| prefix ⊏ / suffix ⊐ | tiền tố / hậu tố | phần đầu / phần cuối của chuỗi |
| proper prefix / suffix | tiền tố / hậu tố thực sự | khác chính chuỗi đó |
| overlapping-suffix lemma | bổ đề hậu tố chồng nhau | hai hậu tố của cùng chuỗi: ngắn là hậu tố của dài |
| radix-d digit | chữ số cơ số d | cách Rabin-Karp hiểu mỗi ký tự |
| Horner's rule | quy tắc Horner | tính giá trị số/đa thức bằng nhân-cộng lồng nhau |
| modulus | modulo (số chia lấy dư) | số nguyên tố q trong Rabin-Karp |
| hit / spurious hit | lần trúng / trúng giả | t_s ≡ p (mod q); trúng nhưng chuỗi khác nhau |
| computer word | từ máy | đơn vị số nguyên máy xử lý trong O(1) |
| finite automaton | ôtômat hữu hạn | bộ (Q, q₀, A, Σ, δ) |
| state / start state / accepting state | trạng thái / trạng thái bắt đầu / trạng thái chấp nhận | các thành phần của ôtômat |
| transition function δ | hàm chuyển trạng thái | δ: Q × Σ → Q |
| accept / reject | chấp nhận / từ chối | dừng ở trạng thái thuộc / không thuộc A |
| final-state function φ | hàm trạng thái cuối | trạng thái sau khi đọc hết một chuỗi |
| state-transition diagram | sơ đồ chuyển trạng thái | đồ thị có hướng biểu diễn δ |
| suffix function σ | hàm hậu tố | độ dài tiền tố dài nhất của P là hậu tố của x |
| string-matching automaton | ôtômat so khớp chuỗi | ôtômat có δ(q, a) = σ(P_q a) |
| spine | xương sống (của ôtômat) | các cạnh q → q + 1 khi khớp |
| suffix-function inequality | bất đẳng thức hàm hậu tố | σ(xa) ≤ σ(x) + 1 |
| suffix-function recursion lemma | bổ đề đệ quy hàm hậu tố | σ(xa) = σ(P_q a) khi q = σ(x) |
| prefix function π | hàm tiền tố | độ dài tiền tố dài nhất là hậu tố thực sự của P_q |
| prefix-function iteration lemma | bổ đề lặp hàm tiền tố | π\*[q] liệt kê đủ các k < q với P_k ⊐ P_q |
| on the fly | ngay khi cần | tính δ lúc chạy thay vì tính trước |
| aggregate method / potential function | phương pháp gộp / hàm thế năng | hai kỹ thuật phân tích khấu hao (Chương 17) |
| gap character ◇ | ký tự khoảng trống | khớp một chuỗi bất kỳ, kể cả rỗng |
| nonoverlappable pattern | mẫu không tự chồng | không có tiền tố thực sự khác rỗng là hậu tố |
| cyclic rotation | phép quay vòng | chuyển một đoạn đầu chuỗi ra cuối (arc ↔ car) |
| repetition factor | thừa số lặp | x = yʳ |
| two-dimensional pattern matching | so khớp mẫu hai chiều | tìm mảng m × m trong mảng n × n |

## Câu nói đáng nhớ

> "The string-matching problem is the problem of finding all valid shifts with which a given pattern P occurs in a given text T." — phần mở đầu Chương 32
>
> *Dịch: Bài toán so khớp chuỗi là bài toán tìm mọi độ dịch hợp lệ mà với nó một mẫu P cho trước xuất hiện trong một văn bản T cho trước.*

> "The naive string-matcher is inefficient because it entirely ignores information gained about the text for one value of s when it considers other values of s." — Mục 32.1
>
> *Dịch: Thuật toán so khớp ngây thơ kém hiệu quả vì nó hoàn toàn bỏ qua thông tin thu được về văn bản ở một giá trị s khi xét các giá trị s khác.*

> "We can thus use the test t_s ≡ p (mod q) as a fast heuristic test to rule out invalid shifts s." — Mục 32.2
>
> *Dịch: Vậy có thể dùng phép thử t_s ≡ p (mod q) như một phép thử kinh nghiệm nhanh để loại các độ dịch không hợp lệ.*

> "These string-matching automata are very efficient: they examine each text character exactly once, taking constant time per text character." — Mục 32.3
>
> *Dịch: Các ôtômat so khớp chuỗi này rất hiệu quả: chúng xem mỗi ký tự văn bản đúng một lần, tốn thời gian hằng số cho mỗi ký tự.*

> "As noted above, this theorem shows that the automaton is merely keeping track, at each step, of the longest prefix of the pattern that is a suffix of what has been read so far." — Mục 32.3, trước Định lý 32.4
>
> *Dịch: Như đã nói, định lý này cho thấy ôtômat chỉ đơn giản theo dõi, ở mỗi bước, tiền tố dài nhất của mẫu là hậu tố của phần đã đọc tới lúc đó.*

> "The prefix function for a pattern encapsulates knowledge about how the pattern matches against shifts of itself." — Mục 32.4
>
> *Dịch: Hàm tiền tố của một mẫu gói gọn hiểu biết về cách mẫu khớp với các bản dịch của chính nó.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: một mạch lập luận duy nhất nối ba thuật toán

Chương không trình bày ôtômat và KMP như hai mẹo rời nhau mà như hai cách cài đặt cùng một đại lượng: σ(T_i), độ dài tiền tố dài nhất của mẫu là hậu tố của phần văn bản đã đọc. Bổ đề 32.3 là chìa khoá chung: nó nói trạng thái mới chỉ phụ thuộc trạng thái cũ và ký tự mới. Ôtômat tính trước mọi câu trả lời (tốn |Σ| lần bộ nhớ), KMP tính câu trả lời khi cần bằng π (trả bằng thời gian khấu hao). Cách đặt KMP như "bản mô phỏng ôtômat" làm chứng minh tính đúng của KMP gần như tự động khi đã có Định lý 32.4, và giải thích được vì sao dãy trạng thái của hai thuật toán trùng nhau từng bước.

### Điểm mạnh: phân tích khấu hao ngắn gọn và dùng lại được

Lập luận "k tăng tối đa m − 1 lần, mỗi bước lùi làm k giảm, k không âm" là một trong những ví dụ đẹp nhất của phương pháp gộp ở Chương 17, và dùng lại nguyên văn cho KMP-MATCHER (Exercise 32.4-4, 32.4-5). Người học thấy được vì sao một vòng while lồng trong vòng for vẫn cho tổng tuyến tính.

### Điểm yếu và chỗ đơn giản hoá

- **Rabin-Karp phân tích dựa trên giả định không chứng minh.** Sách thừa nhận giả định "mod q hoạt động như ánh xạ ngẫu nhiên" khó hình thức hoá và không theo đuổi. Thực ra với q cố định, đối thủ biết q dễ dàng dựng văn bản đầy trúng giả. Cách làm chặt chẽ — chọn ngẫu nhiên cơ số x (như Exercise 32.2-4, đánh giá đa thức tại điểm ngẫu nhiên) hoặc chọn ngẫu nhiên số nguyên tố q — chỉ xuất hiện gián tiếp qua bài tập. Theo hiểu biết của người tổng hợp, đây là lỗ hổng thật trong thực tế: các bộ test chống băm (anti-hash) trong lập trình thi đấu khai thác đúng điều này.
- **Bỏ qua các thuật toán quan trọng nhất trong thực hành.** Họ Boyer–Moore (và Boyer–Moore–Horspool), vốn thường nhanh nhất trên văn bản tự nhiên vì có thể bỏ qua nhiều ký tự (thời gian dưới tuyến tính trung bình), không được nhắc tới trong ấn bản 3; cấu trúc chỉ mục như cây hậu tố và mảng hậu tố (cho bài toán nhiều truy vấn trên cùng văn bản) cũng không (ấn bản 4 mới bổ sung mảng hậu tố — theo hiểu biết của người tổng hợp).
- **Chứng minh KMP dài và nặng ký hiệu.** Hai lớp lập luận (Bổ đề 32.5–Hệ quả 32.7 cho π; ba trường hợp cho KMP-MATCHER) dài gấp nhiều lần bản chất trực giác "lùi tới hậu tố dài nhất kế tiếp". Có chỗ ký hiệu chưa chặt (P_q ⊐ T_i thay cho T_{i−1} trong trường hợp σ(T_i) = 0 của chứng minh tính đúng của KMP; π\*[q] không nói rõ 0 có thuộc tập). Việc dùng lại dòng 12 lại đẩy phần biện minh sang gợi ý của một bài tập có dấu sao.
- **Ôtômat tính trực tiếp O(m³|Σ|)** được trình bày như thủ tục chính, trong khi cách O(m|Σ|) chỉ nằm ở bài tập ★32.4-8; người đọc chỉ đọc phần chính có thể nghĩ dựng ôtômat là đắt.
- **Thời gian xấu nhất của Rabin-Karp gắn với việc in mọi lần khớp.** Với T = aⁿ, P = aᵐ thì bất kỳ thuật toán nào kiểm tra lại từng lần khớp đều Θ((n − m + 1)m); KMP tránh được nhờ không bao giờ so lại. Sách nêu điều này nhưng không chỉ ra rằng Rabin-Karp có thể bỏ bước kiểm tra (chấp nhận sai số xác suất — biến thể "Monte Carlo") để đạt O(n + m) xấu nhất.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: tìm chuỗi con trong thư viện chuẩn hiếm khi là KMP thuần. glibc `memmem`/`strstr`, Go `strings.Index`, Rust `str::find` dùng kết hợp: thuật toán Two-Way (Crochemore–Perrin, tuyến tính, O(1) bộ nhớ — cùng tinh thần với Galil–Seiferas ở ghi chú chương), biến thể Boyer–Moore–Horspool, Rabin-Karp cho mẫu ngắn, và lệnh SIMD để quét nhanh ký tự đầu. Công cụ `grep` dùng Boyer–Moore cho chuỗi cố định và DFA (đúng ý tưởng Mục 32.3) cho biểu thức chính quy. Tìm nhiều mẫu cùng lúc (lọc nội dung, quét virus, hệ thống phát hiện xâm nhập) dùng Aho–Corasick — tổng quát hoá của π lên cây trie. Trong tin sinh học, nơi văn bản (bộ gen) cố định và truy vấn rất nhiều, người ta dựng chỉ mục một lần: mảng hậu tố, chỉ mục FM (biến đổi Burrows–Wheeler). Rabin-Karp sống mạnh ở dạng băm cuộn: rsync, khử trùng lặp dữ liệu, phát hiện đạo văn.

### Liên hệ các chương khác

- Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)): bất biến vòng lặp — bất biến t_s = T[s + 1..s + m] mod q của RABIN-KARP-MATCHER, bất biến k = π[q − 1] của COMPUTE-PREFIX-FUNCTION.
- Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)): tuyến tính kỳ vọng trong Exercise 32.1-3, xác suất trong phân tích trúng giả.
- Chương 11 ([C11-bang-bam.md](C11-bang-bam.md)): Rabin-Karp chính là băm bằng phép chia (Mục 11.3.1) áp dụng cho cửa sổ trượt; bài toán nhiều mẫu (Exercise 32.2-2) dùng bảng băm.
- Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)): dãy con chung dài nhất là bài toán chuỗi "mềm" hơn (cho phép bỏ ký tự), giải bằng quy hoạch động Θ(mn); so khớp chính xác ở chương này đạt Θ(n + m).
- Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)): phương pháp gộp và phương pháp thế năng cho thời gian của KMP.
- Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)): quy tắc Horner; theo hiểu biết của người tổng hợp, FFT còn giải được so khớp có ký tự đại diện bằng tích chập.
- Chương 31 ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)): đồng dư, lũy thừa theo modulo để tính h = d^{m−1} mod q, số nguyên tố, số nghiệm của đa thức theo modulo nguyên tố (Exercise 32.2-4).
- Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)): khái niệm chuỗi trên bảng chữ và tập Σ\* của chương này là nền của khung ngôn ngữ hình thức mà Chương 34 dùng để phát biểu bài toán quyết định; so khớp chuỗi là ví dụ bài toán giải được trong thời gian tuyến tính, đối lập với các bài toán NP-đầy đủ.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** "cài strStr / indexOf" — biết lời giải ngây thơ và giới hạn Θ(nm), trình bày KMP với mảng π (đặc biệt viết đúng COMPUTE-PREFIX-FUNCTION và dòng 12); "chuỗi có phải phép quay vòng của chuỗi kia" (Exercise 32.4-7: tìm trong T′T′); "chuỗi có phải lặp lại của một chuỗi con" (Problem 32-1(a): kiểm tra n − π[n] chia hết n); "palindrome ngắn nhất bằng cách thêm ký tự vào đầu" (π của s#đảo(s)).
- **Lập trình thi đấu:** hàm tiền tố và hàm Z cho mọi bài tìm chu kỳ, đếm lần xuất hiện, so khớp có điều kiện; băm chuỗi hai modulo (hoặc modulo 2⁶¹ − 1 với cơ số ngẫu nhiên) để so sánh chuỗi con O(1), kết hợp tìm kiếm nhị phân cho tiền tố chung dài nhất; Aho–Corasick cho nhiều mẫu; ôtômat KMP (Exercise 32.4-8) kết hợp quy hoạch động cho bài "đếm chuỗi độ dài N không chứa mẫu P". Luôn chọn cơ số/modulo ngẫu nhiên lúc chạy để tránh test chống băm.
- **Kỹ thuật phần mềm:** dùng hàm tìm chuỗi của thư viện chuẩn thay vì tự viết; khi tự viết cho dữ liệu dạng luồng (giao thức mạng, phân tích log khổng lồ), KMP hoặc ôtômat cho phép xử lý từng khối mà không lưu đệm văn bản cũ; khi xử lý đầu vào không tin cậy (tìm kiếm do người dùng gửi), tránh thuật toán có trường hợp xấu Θ(nm) và tránh biểu thức chính quy có quay lui — dùng bộ máy dạng ôtômat bảo đảm tuyến tính.

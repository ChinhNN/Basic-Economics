# Chương 35 — Thuật toán xấp xỉ (Approximation Algorithms)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VII "Selected Topics", Chương 35 "Approximation Algorithms", trang 1106–1140 (trang 1141 để trắng; trang 1142 là trang tên Phần VIII "Appendix: Mathematical Background", không thuộc chương).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Đây là chương cuối cùng của phần chính cuốn sách. Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)) chứng minh rằng phủ đỉnh, chu trình Hamilton, người bán hàng (TSP), tổng tập con và 3-CNF-SAT đều NP-đầy đủ, nghĩa là gần như chắc chắn không có thuật toán đa thức giải đúng. Chương 35 trả lời câu hỏi tự nhiên tiếp theo: "vậy làm gì với các bài toán ấy?" — bằng thuật toán chạy thời gian đa thức và trả về lời giải **có bảo đảm** gần tối ưu. Chương dùng lại rất nhiều công cụ của các chương trước: cây khung nhỏ nhất và MST-PRIM của Chương 23 ([C23-cay-khung-nho-nhat.md](C23-cay-khung-nho-nhat.md)) làm cận dưới cho TSP; phép duyệt cây theo thứ tự trước (preorder) của Chương 12 ([C12-cay-tim-kiem-nhi-phan.md](C12-cay-tim-kiem-nhi-phan.md)); phương pháp tham lam của Chương 16 ([C16-thuat-toan-tham-lam.md](C16-thuat-toan-tham-lam.md)) cho phủ tập hợp và bài toán cái túi; biến ngẫu nhiên chỉ thị và tính tuyến tính của kỳ vọng của Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)) cho MAX-3-CNF; quy hoạch tuyến tính của Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)) cho phủ đỉnh có trọng số; thủ tục trộn danh sách giống MERGE của Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)) cho tổng tập con; số điều hoà và các bất đẳng thức về hàm mũ, lôgarit của Chương 3 ([C03-tang-truong-cua-ham.md](C03-tang-truong-cua-ham.md)) và Phụ lục A ([PA-tong.md](PA-tong.md)). Bài toán ghép cặp cực đại trong Problem 35-4 nối với Mục 26.3 ([C26-luong-cuc-dai.md](C26-luong-cuc-dai.md)).
**Ý chính:** Tác giả muốn người đọc hiểu rằng **NP-đầy đủ không có nghĩa là bó tay: với nhiều bài toán tối ưu NP-khó, ta có thuật toán thời gian đa thức trả về lời giải mà chi phí bị chặn trong một hệ số ρ(n) của chi phí tối ưu — dù ta không bao giờ biết chi phí tối ưu là bao nhiêu. Bí quyết chung là tìm một CẬN của giá trị tối ưu tính được trong thời gian đa thức (một ghép cặp cực đại, một cây khung nhỏ nhất, giá trị của một quy hoạch tuyến tính nới lỏng, tổng số mệnh đề m) rồi so lời giải của mình với cận đó. Nhưng khả năng xấp xỉ khác nhau rất xa giữa các bài toán: có bài xấp xỉ được tuỳ ý (tổng tập con có lược đồ xấp xỉ đa thức đầy đủ), có bài chỉ xấp xỉ được trong hệ số lôgarit (phủ tập hợp), và có bài không xấp xỉ được trong bất kỳ hệ số hằng nào trừ khi P = NP (TSP tổng quát).** Phần mở đầu định nghĩa tỷ số xấp xỉ ρ(n), thuật toán ρ(n)-xấp xỉ, lược đồ xấp xỉ (approximation scheme), lược đồ xấp xỉ thời gian đa thức (PTAS) và lược đồ xấp xỉ thời gian đa thức đầy đủ (FPTAS). Mục 35.1: APPROX-VERTEX-COVER lấy một cạnh bất kỳ, đưa cả hai đầu mút vào phủ, xoá mọi cạnh dính vào chúng; các cạnh được chọn tạo thành một ghép cặp, mà mọi phủ đỉnh phải chứa ít nhất một đầu mút của từng cạnh ghép, nên lời giải không quá 2 lần tối ưu. Mục 35.2: với TSP thoả bất đẳng thức tam giác, APPROX-TSP-TOUR dựng cây khung nhỏ nhất rồi đi theo thứ tự trước, được hành trình không quá 2 lần tối ưu; không có bất đẳng thức tam giác thì, nếu P ≠ NP, không tồn tại thuật toán ρ-xấp xỉ đa thức với bất kỳ hằng ρ ≥ 1 nào (chứng minh bằng cách gán chi phí ρ|V| + 1 cho các cạnh không thuộc đồ thị để tạo "khoảng cách" giữa hai loại thể hiện). Mục 35.3: GREEDY-SET-COVER mỗi bước chọn tập phủ nhiều phần tử chưa phủ nhất; bằng cách chia chi phí 1 của mỗi tập cho các phần tử nó phủ lần đầu, ta chứng minh tỷ số H(max |S|) ≤ ln |X| + 1. Mục 35.4: gán ngẫu nhiên mỗi biến 0 hoặc 1 với xác suất 1/2 cho thuật toán ngẫu nhiên 8/7-xấp xỉ cho MAX-3-CNF; giải quy hoạch tuyến tính nới lỏng của phủ đỉnh có trọng số rồi làm tròn mọi biến ≥ 1/2 lên 1 cho thuật toán 2-xấp xỉ. Mục 35.5: thuật toán chính xác cho tổng tập con duy trì danh sách mọi tổng con không vượt t (thời gian mũ); "tỉa" (TRIM) danh sách với tham số δ = ε/2n — bỏ các giá trị nằm trong hệ số 1 + δ của giá trị đã giữ — làm danh sách chỉ còn độ dài O((n ln t)/ε) mà vẫn bảo đảm sai số tích luỹ ≤ (1 + ε/2n)ⁿ ≤ 1 + ε, cho một FPTAS.

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong chương này.** Chỉ có một bài tập có dấu sao: Exercise 35.1-3 (phản ví dụ cho heuristic "chọn đỉnh bậc cao nhất" của giáo sư Bündchen).
> - **Lớp chữ PDF hỏng gần như toàn bộ ký hiệu toán của chương:** ρ thành `/SUB`, ε và ν (giá trị đồ vật trong Problem 35-7) mất hẳn, ≤ ≥ ≠ ⊆ mất hoặc thành dấu cách, `C*` thành `C `, z* thành `´`, x̄(v) thành `Nx./`, dấu trừ thành `/NUL`, các tổng Σ và phân số bị vỡ thành nhiều dòng (đặc biệt chuỗi đẳng thức chứng minh (35.12) và (35.22)). Mọi pseudocode, công thức (35.1)–(35.30), Hình 35.1, 35.2, 35.3 trong bản tổng hợp này được đối chiếu với ảnh trang 1106–1140; Hình 35.2 và 35.3 được dựng lại ở độ phân giải cao để đọc toạ độ điểm và biên các tập hợp.
> - **Đọc lại Hình 35.3 từ ảnh phóng to (quan trọng):** tập S₄ không chỉ là "cột giữa" mà có một chỗ lồi sang trái ôm thêm một điểm của cột trái. Nếu bỏ qua chỗ lồi này, lời khẳng định của sách "tham lam chọn S₁, S₄, S₅ rồi S₃ hoặc S₆" sẽ không khớp. Đã tự kiểm tra lại toàn bộ thứ tự chọn với cách đọc đúng.
> - **Chỗ sách chưa chặt hoặc có thể sai (nhận xét của người tổng hợp):**
>   - Problem 35-6(d) yêu cầu chứng minh w(T_G) ≥ w(S_G)/2. Bất đẳng thức này suy ra ngay từ câu (c) (S_G ⊆ T_G nên w(T_G) ≥ w(S_G), khi trọng số không âm) nên gần như vô nghĩa; điều cần cho câu (e) là chiều ngược lại, w(S_G) ≥ w(T_G)/2. Rất có thể đây là lỗi in; người tổng hợp không chắc nó có trong danh sách lỗi chính thức hay không (không tra cứu). Phần lời giải ở dưới chứng minh cả hai chiều.
>   - Exercise 35.2-1 yêu cầu chứng minh c(u, v) ≥ 0 từ bất đẳng thức tam giác, nhưng ngay đầu Mục 35.2 sách đã định nghĩa chi phí là "số nguyên không âm"; bài tập chỉ có nội dung khi bỏ giả định đó (chi phí là số thực bất kỳ).
>   - Ở Hình 35.2, cạnh b–h và cạnh c–h có cùng độ dài √5 ≈ 2,236, nên MST-PRIM có thể chọn một trong hai; sách vẽ b–h. Thứ tự duyệt trước vẫn là a, b, c, h, d, e, f, g trong cả hai trường hợp, nên kết quả không đổi.
>   - Trong định nghĩa "đường đi đầy đủ" (full walk) của chứng minh Định lý 35.2, chi phí c(W) được hiểu trên đa tập cạnh (mỗi cạnh của cây được tính hai lần); sách nói rõ điều này trong ngoặc.
> - **Ví dụ chạy tay đã tự kiểm tra lại và đều đúng:** Hình 35.1 (thuật toán chọn 6 đỉnh, tối ưu 3 đỉnh — tỷ số đúng bằng 2); Hình 35.2 (đã đặt toạ độ lưới, tính lại: hành trình của thuật toán ≈ 19,074, tối ưu ≈ 14,715 — khớp sách; đã vét cạn mọi 5.040 hành trình để xác nhận 14,715 là tối ưu; cây khung nhỏ nhất nặng ≈ 11,892); Hình 35.3 (thứ tự tham lam S₁, S₄, S₅, rồi S₃ hoặc S₆); ví dụ TRIM với δ = 0,1; ví dụ APPROX-SUBSET-SUM với S = ⟨104, 102, 201, 101⟩, t = 308, ε = 0,40 (mọi danh sách ở dòng 4, 5, 6 đều khớp; kết quả 302, tối ưu 307, sai lệch ≈ 1,6%); ví dụ lập lịch hai máy trong Problem 35-5 (C_max = 14 và 12).
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương vẫn là Chương 35 "Approximation Algorithms", chương cuối của Phần VII, với cùng năm mục (phủ đỉnh, TSP, phủ tập hợp, ngẫu nhiên hoá và quy hoạch tuyến tính, tổng tập con). Ấn bản 4 dùng font và cách viết pseudocode mới (ví dụ bỏ thuộc tính kiểu `G.E` ở một số chỗ). Các khác biệt chi tiết về bài tập và ghi chú, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 35.1, trang 1106–1108) — vì sao cần thuật toán xấp xỉ và đo chất lượng bằng gì

```text
       Nhiều bài toán thực tế quan trọng là NP-đầy đủ
                                │
                                ▼
       Ba cách "đi vòng" qua NP-đầy đủ:
       1. đầu vào thực tế nhỏ ⇒ thuật toán thời gian mũ vẫn chấp nhận được
       2. tách ra các trường hợp riêng quan trọng giải được trong đa thức
       3. tìm lời giải GẦN TỐI ƯU trong thời gian đa thức
          (xấu nhất hoặc kỳ vọng) ⇒ THUẬT TOÁN XẤP XỈ
                                │
                                ▼
       TỶ SỐ XẤP XỈ ρ(n): với mọi đầu vào cỡ n,
            max( C / C* , C* / C ) ≤ ρ(n)                         (35.1)
       C = chi phí lời giải của thuật toán, C* = chi phí tối ưu,
       mọi lời giải có chi phí dương
       · bài toán cực tiểu: 0 < C* ≤ C, tỷ số có nghĩa là C / C*
       · bài toán cực đại: 0 < C ≤ C*, tỷ số có nghĩa là C* / C
       · luôn ρ(n) ≥ 1; thuật toán 1-xấp xỉ cho lời giải tối ưu
                                │
           ┌────────────────────┼────────────────────┐
           ▼                    ▼                    ▼
   ρ là hằng số nhỏ       ρ(n) tăng theo n      LƯỢC ĐỒ XẤP XỈ: nhận thêm ε > 0,
   (phủ đỉnh, TSP có     (phủ tập hợp:          là thuật toán (1+ε)-xấp xỉ
    bất đẳng thức tam     ln |X| + 1)           · PTAS: đa thức theo n với
    giác: ρ = 2)                                  mỗi ε cố định, ví dụ O(n^(2/ε))
                                                · FPTAS: đa thức theo cả n và
                                                  1/ε, ví dụ O((1/ε)² n³)
                                │
                                ▼
       Trình tự chương: 35.1 phủ đỉnh (ρ = 2); 35.2 TSP (ρ = 2 khi có
       bất đẳng thức tam giác, không xấp xỉ được nếu không có);
       35.3 phủ tập hợp (tham lam, ρ lôgarit); 35.4 MAX-3-CNF ngẫu nhiên
       (ρ = 8/7) và phủ đỉnh có trọng số qua quy hoạch tuyến tính (ρ = 2);
       35.5 FPTAS cho tổng tập con
```

### Mục 35.1 — Bài toán phủ đỉnh (The vertex-cover problem, trang 1108–1111)

```text
       Phủ đỉnh của đồ thị vô hướng G = (V, E): tập V' ⊆ V sao cho mọi
       cạnh (u, v) có u ∈ V' hoặc v ∈ V'. Bài toán: tìm phủ đỉnh nhỏ nhất
       (NP-khó, Mục 34.5.2)
                                │
                                ▼
       APPROX-VERTEX-COVER(G):
       · C = ∅; E' = bản sao của G.E
       · khi E' còn cạnh: lấy cạnh (u, v) bất kỳ của E',
         thêm CẢ u VÀ v vào C, xoá khỏi E' mọi cạnh dính vào u hoặc v
       · trả về C          Thời gian O(V + E) với danh sách kề
                                │
                                ▼
       Định lý 35.1: thuật toán 2-xấp xỉ, thời gian đa thức
       · A = tập cạnh được chọn ở dòng 4; không hai cạnh nào của A chung
         đầu mút (A là một GHÉP CẶP CỰC ĐẠI THEO BAO HÀM)
       · mọi phủ đỉnh, kể cả tối ưu C*, phải chứa ≥ 1 đầu mút của mỗi
         cạnh trong A, và không đỉnh nào phủ được hai cạnh của A
         ⇒ |C*| ≥ |A|                                             (35.2)
       · mỗi cạnh chọn thêm đúng 2 đỉnh mới ⇒ |C| = 2|A|          (35.3)
       ⇒ |C| = 2|A| ≤ 2|C*|
                                │
                                ▼
       Bài học phương pháp: không cần biết |C*|, chỉ cần một CẬN DƯỚI
       của nó (kích thước một ghép cặp cực đại) rồi so lời giải với cận
       Ví dụ: đồ thị 7 đỉnh, 8 cạnh — thuật toán cho 6 đỉnh, tối ưu 3
```

### Mục 35.2 — Bài toán người bán hàng (The traveling-salesman problem, trang 1111–1117)

```text
       TSP: đồ thị vô hướng đầy đủ G, chi phí cạnh c(u, v) ≥ 0 nguyên;
       tìm chu trình Hamilton (hành trình) chi phí nhỏ nhất
       Bất đẳng thức tam giác: c(u, w) ≤ c(u, v) + c(v, w) với mọi u, v, w
       (ví dụ khoảng cách Euclid); TSP vẫn NP-đầy đủ dù có điều kiện này
                                │
            ┌───────────────────┴────────────────────┐
            ▼                                        ▼
   35.2.1 CÓ BẤT ĐẲNG THỨC TAM GIÁC        35.2.2 TSP TỔNG QUÁT
   APPROX-TSP-TOUR(G, c):                   Định lý 35.3: nếu P ≠ NP thì
   1. chọn gốc r                            với mọi hằng ρ ≥ 1 KHÔNG có
   2. T = MST-PRIM(G, c, r)                 thuật toán ρ-xấp xỉ đa thức
   3. H = danh sách đỉnh theo thứ tự        · từ G = (V, E) của bài chu
      gặp lần đầu khi duyệt trước T           trình Hamilton, dựng đồ thị
   4. trả về chu trình H                      đầy đủ G' với c = 1 nếu cạnh
   Thời gian Θ(V²)                            thuộc E, c = ρ|V| + 1 nếu không
   Định lý 35.2: 2-xấp xỉ                   · G có chu trình Hamilton ⇒ có
   · bỏ 1 cạnh của hành trình tối ưu H*       hành trình chi phí |V|
     được cây khung ⇒ c(T) ≤ c(H*) (35.4)   · không có ⇒ mọi hành trình
   · đường đi đầy đủ W đi mỗi cạnh của T      ≥ (ρ|V| + 1) + (|V| − 1)
     2 lần ⇒ c(W) = 2c(T) ≤ 2c(H*)            = ρ|V| + |V| > ρ|V|
     (35.5), (35.6)                         · chạy thuật toán ρ-xấp xỉ
   · bỏ các lần thăm lặp: nhờ bất đẳng        trên (G', c): kết quả ≤ ρ|V|
     thức tam giác, chi phí không tăng        ⇔ G có chu trình Hamilton
     ⇒ c(H) ≤ c(W) (35.7)                   ⇒ giải được bài NP-đầy đủ
   ⇒ c(H) ≤ 2c(H*)                            trong đa thức ⇒ P = NP
   Ví dụ 8 điểm lưới: H ≈ 19,074,           Kỹ thuật chung: tạo "khoảng
   tối ưu ≈ 14,715                          cách" (gap) giữa thể hiện "có"
                                            (giá trị ≤ k) và "không" (> ρk)
```

### Mục 35.3 — Bài toán phủ tập hợp (The set-covering problem, trang 1117–1122)

```text
       Thể hiện (X, F): tập hữu hạn X, họ F các tập con của X, hợp của F
       là X. Tìm họ con C ⊆ F nhỏ nhất (đếm số tập) có hợp là X   (35.8)
       Tổng quát hoá phủ đỉnh ⇒ NP-khó; ví dụ: lập ủy ban ít người nhất
       có đủ mọi kỹ năng
                                │
                                ▼
       GREEDY-SET-COVER(X, F):
       U = X (phần tử chưa phủ); C = ∅
       khi U ≠ ∅: chọn S ∈ F làm |S ∩ U| lớn nhất; U = U − S; thêm S vào C
       Thời gian O(|X| |F| min(|X|, |F|)) (cài đặt đơn giản)
                                │
                                ▼
       Định lý 35.4: tỷ số ρ(n) = H(max{|S| : S ∈ F}),
       H(d) = 1 + 1/2 + … + 1/d (số điều hoà), H(0) = 0
       · mỗi tập được chọn tốn 1, chia đều cho các phần tử nó phủ LẦN ĐẦU:
         c_x = 1 / |Sᵢ − (S₁ ∪ … ∪ Sᵢ₋₁)|
       · |C| = Σ_{x∈X} c_x ≤ Σ_{S∈C*} Σ_{x∈S} c_x      (35.9)–(35.11)
       · BẤT ĐẲNG THỨC THEN CHỐT: với mọi S ∈ F, Σ_{x∈S} c_x ≤ H(|S|)
         (35.12) — vì khi S còn uᵢ₋₁ phần tử chưa phủ, tập tham lam Sᵢ
         phủ mới ≥ uᵢ₋₁ phần tử, mỗi phần tử của S trả ≤ 1/uᵢ₋₁;
         tổng là chuỗi co rút ra H(u₀) − H(0) = H(|S|)
       ⇒ |C| ≤ |C*| · H(max |S|)
                                │
                                ▼
       Hệ quả 35.5: tỷ số ln |X| + 1
       Khi max |S| nhỏ (ví dụ phủ đỉnh đồ thị bậc ≤ 3): ρ = H(3) = 11/6 < 2
```

### Mục 35.4 — Ngẫu nhiên hoá và quy hoạch tuyến tính (Randomization and linear programming, trang 1123–1128)

```text
       Thuật toán ngẫu nhiên ρ(n)-xấp xỉ: CHI PHÍ KỲ VỌNG C thoả
       max(C / C*, C* / C) ≤ ρ(n)                                  (35.13)
                                │
            ┌───────────────────┴────────────────────┐
            ▼                                        ▼
   MAX-3-CNF: gán đúng nhiều mệnh đề nhất   PHỦ ĐỈNH CÓ TRỌNG SỐ w(v) > 0
   (mỗi mệnh đề đúng 3 literal khác nhau,   · quy hoạch nguyên 0-1:
    không chứa cả x và ¬x)                    min Σ w(v) x(v)
   · gán mỗi biến = 1 với xác suất 1/2,       x(u) + x(v) ≥ 1 mỗi cạnh
     độc lập                                  x(v) ∈ {0, 1}   (35.14)–(35.16)
   · mệnh đề sai ⇔ cả 3 literal = 0:        · NỚI LỎNG thành 0 ≤ x(v) ≤ 1:
     xác suất (1/2)³ = 1/8                    quy hoạch tuyến tính, giải được
   · Yᵢ = I{mệnh đề i đúng}, E[Yᵢ] = 7/8      trong đa thức  (35.17)–(35.20)
   · E[Y] = Σ E[Yᵢ] = 7m/8                  · giá trị tối ưu z* ≤ w(C*) (35.21)
   · tối ưu ≤ m ⇒ tỷ số ≤ m/(7m/8) = 8/7    · APPROX-MIN-WEIGHT-VC: lấy mọi v
   Định lý 35.6: 8/7-xấp xỉ ngẫu nhiên        có x̄(v) ≥ 1/2 ("làm tròn")
                                            · mỗi cạnh có một đầu x̄ ≥ 1/2 ⇒
                                              là phủ đỉnh; z* ≥ w(C)/2 (35.22)
                                            Định lý 35.7: w(C) ≤ 2z* ≤ 2w(C*)
```

### Mục 35.5 — Bài toán tổng tập con (The subset-sum problem, trang 1128–1134)

```text
       Bài toán tối ưu: cho S = {x₁, …, xₙ} nguyên dương và t; tìm tổng
       tập con LỚN NHẤT không vượt t (ví dụ chất hàng lên xe tải tải trọng t)
                                │
                                ▼
       EXACT-SUBSET-SUM(S, t): L₀ = ⟨0⟩;
       Lᵢ = MERGE-LISTS(Lᵢ₋₁, Lᵢ₋₁ + xᵢ), bỏ phần tử > t; trả max Lₙ
       Pᵢ = Pᵢ₋₁ ∪ (Pᵢ₋₁ + xᵢ)   (35.23);  |Lᵢ| có thể tới 2ⁱ ⇒ thời gian mũ
                                │
                                ▼
       TỈA (TRIM) danh sách với δ: bỏ y nếu còn z giữ lại thoả
       y/(1+δ) ≤ z ≤ y                                             (35.24)
       Ví dụ δ = 0,1: ⟨10,11,12,15,20,21,22,23,24,29⟩ → ⟨10,12,15,20,23,29⟩
       TRIM chạy Θ(m) trên danh sách đã sắp xếp m phần tử
                                │
                                ▼
       APPROX-SUBSET-SUM(S, t, ε), 0 < ε < 1: như EXACT nhưng tỉa mỗi Lᵢ
       với δ = ε/2n trước khi bỏ phần tử > t; trả z* = max Lₙ
       Ví dụ ⟨104,102,201,101⟩, t = 308, ε = 0,4: trả 302, tối ưu 307
                                │
                                ▼
       Định lý 35.8: FPTAS
       · tính đúng: mỗi y ∈ Pᵢ, y ≤ t có z ∈ Lᵢ với y/(1+ε/2n)ⁱ ≤ z ≤ y (35.26)
         ⇒ y*/z* ≤ (1 + ε/2n)ⁿ ≤ e^(ε/2) ≤ 1 + ε/2 + (ε/2)² ≤ 1 + ε
       · thời gian: hai phần tử liên tiếp của Lᵢ cách nhau hệ số > 1 + ε/2n
         ⇒ |Lᵢ| ≤ log_{1+ε/2n} t + 2 < 3n ln t / ε + 2
         ⇒ đa thức theo n, lg t và 1/ε
```

### Bài toán cuối chương (Problems 35-1 đến 35-7, trang 1134–1138)

```text
       35-1 Xếp thùng (bin packing): NP-khó; heuristic first-fit dùng
            ≤ ⌈2S⌉ thùng (S = tổng kích thước), tối ưu ≥ ⌈S⌉ ⇒ 2-xấp xỉ
                                │
                                ▼
       35-2 Xấp xỉ clique lớn nhất: "luỹ thừa" đồ thị G^(k) có clique lớn
            nhất bằng ω(G)^k ⇒ nếu có xấp xỉ hệ số hằng thì có PTAS
                                │
                                ▼
       35-3 Phủ tập hợp có trọng số: tham lam theo trọng số / số phần tử
            mới, tỷ số H(d)
                                │
                                ▼
       35-4 Ghép cặp lớn nhất: ghép cặp cực đại tham lam O(E) là 2-xấp xỉ
            (qua cận phủ đỉnh)
                                │
                                ▼
       35-5 Lập lịch máy song song: tham lam "máy rảnh thì giao việc"
            cho C_max ≤ (1/m)Σp_k + max p_k ≤ 2 C*_max
                                │
                                ▼
       35-6 Xấp xỉ cây khung lớn nhất: tập S_G các cạnh nặng nhất ở mỗi đỉnh
            nằm trong cây khung lớn nhất T_G; thuật toán O(V + E) 2-xấp xỉ
                                │
                                ▼
       35-7 Cái túi 0-1: bài con Iⱼ bắt buộc lấy đồ vật j; nghiệm phân số
            tham lam bỏ phần lẻ vẫn ≥ nửa tối ưu ⇒ 2-xấp xỉ
```

### Ghi chú chương (Chapter notes, trang 1138–1140)

```text
       Phương pháp tính gần đúng có từ hàng nghìn năm (xấp xỉ π), nhưng khái
       niệm thuật toán xấp xỉ đa thức mới được hình thức hoá: Garey, Graham,
       Ullman và Johnson; thuật toán đầu tiên thường ghi cho Graham
                                │
                                ▼
       Sách chuyên khảo: Ausiello và cộng sự, Hochbaum, Vazirani; khảo sát
       của Shmoys, Klein–Young; TSP: Lawler, Lenstra, Rinnooy Kan, Shmoys
                                │
                                ▼
       Nguồn gốc từng thuật toán: APPROX-VERTEX-COVER — Gavril, Yannakakis
       (mọi tỷ số biết được cho phủ đỉnh ≥ 2 − o(1)); APPROX-TSP-TOUR —
       Rosenkrantz, Stearns, Lewis; Christofides cải tiến lên 3/2; Arora,
       Mitchell: PTAS cho TSP Euclid phẳng; Định lý 35.3 — Sahni, Gonzalez;
       phủ tập hợp — Johnson, Lovász (chứng minh theo Chvátal);
       APPROX-SUBSET-SUM — theo Ibarra, Kim; Problem 35-7 — Bienstock,
       McClosky; MAX-3-CNF — Johnson; phủ đỉnh có trọng số — Hochbaum
                                │
                                ▼
       Hướng mở rộng: làm tròn ngẫu nhiên (Raghavan–Thompson), phương pháp
       đối ngẫu–gốc (primal-dual), lát cắt thưa, quy hoạch nửa xác định;
       chứng minh kiểm tra được bằng xác suất (PCP) cho cận dưới về khả
       năng xấp xỉ (Arora–Lund)
```

## Ba câu hỏi chương này trả lời

1. **Làm sao chứng minh một lời giải "không quá ρ lần tối ưu" khi ta không biết, và không tính được, giá trị tối ưu?** Bằng cách tìm một đại lượng tính được trong thời gian đa thức mà chắc chắn là cận của giá trị tối ưu, rồi chặn lời giải của thuật toán theo đại lượng đó. Chương dùng bốn loại cận. (a) Phủ đỉnh: các cạnh A mà APPROX-VERTEX-COVER chọn đôi một không chung đỉnh, nên mọi phủ đỉnh cần ít nhất |A| đỉnh, còn thuật toán lấy đúng 2|A| đỉnh: |C| = 2|A| ≤ 2|C*|. (b) TSP có bất đẳng thức tam giác: bỏ một cạnh của hành trình tối ưu được một cây khung, nên cây khung nhỏ nhất T có c(T) ≤ c(H*); đi vòng quanh T tốn 2c(T), bỏ các đỉnh lặp lại không làm tăng chi phí, nên c(H) ≤ 2c(T) ≤ 2c(H*). (c) Phủ đỉnh có trọng số: giá trị tối ưu z* của quy hoạch tuyến tính nới lỏng không vượt trọng số phủ tối ưu, và làm tròn ở ngưỡng 1/2 chỉ làm trọng số tăng tối đa gấp đôi: w(C) ≤ 2z* ≤ 2w(C*). (d) MAX-3-CNF: tối ưu không thể vượt tổng số mệnh đề m, còn phép gán ngẫu nhiên thoả kỳ vọng 7m/8 mệnh đề, nên tỷ số ≤ 8/7. Phủ tập hợp dùng một biến thể tinh tế hơn: chia chi phí cho từng phần tử và chứng minh mỗi tập S của lời giải tối ưu "gánh" tổng chi phí ≤ H(|S|).
2. **Có phải bài toán NP-đầy đủ nào cũng xấp xỉ được tốt như nhau không?** Không — đây là thông điệp quan trọng thứ hai của chương. Ngay trong chương đã có bốn mức khác nhau: (i) tổng tập con có FPTAS — với mọi ε, đạt sai số 1 + ε trong thời gian đa thức theo n, lg t và 1/ε (danh sách tỉa có độ dài < 3n ln t / ε + 2); (ii) phủ đỉnh, TSP Euclid / có bất đẳng thức tam giác, phủ đỉnh có trọng số, xếp thùng, lập lịch máy có tỷ số hằng 2 (MAX-3-CNF 8/7); (iii) phủ tập hợp chỉ có bảo đảm H(max |S|) ≤ ln |X| + 1, tăng theo cỡ đầu vào; (iv) TSP tổng quát không có thuật toán ρ-xấp xỉ đa thức với bất kỳ hằng ρ nào trừ khi P = NP. Lý do của (iv): gán chi phí 1 cho cạnh của đồ thị gốc và ρ|V| + 1 cho cạnh không thuộc đồ thị; khi đó mọi hành trình không phải chu trình Hamilton tốn ít nhất ρ|V| + |V|, lớn hơn ρ lần chi phí |V| của chu trình Hamilton, nên một thuật toán ρ-xấp xỉ sẽ phân biệt được đồ thị có và không có chu trình Hamilton.
3. **Đánh đổi giữa thời gian chạy và độ chính xác được thực hiện thế nào?** Bằng lược đồ xấp xỉ: thuật toán nhận thêm tham số ε và bảo đảm tỷ số 1 + ε. Với tổng tập con, ý tưởng là thuật toán chính xác (liệt kê mọi tổng con ≤ t, có thể tới 2ⁿ giá trị) được giữ nguyên nhưng sau mỗi bước, danh sách các tổng bị "tỉa": giá trị nào nằm trong hệ số 1 + δ của một giá trị nhỏ hơn đã giữ thì bỏ. Chọn δ = ε/2n để n lần tỉa liên tiếp tích luỹ sai số (1 + ε/2n)ⁿ ≤ e^(ε/2) ≤ 1 + ε. Sau khi tỉa, hai giá trị liền kề cách nhau ít nhất hệ số 1 + ε/2n, nên trong khoảng [1, t] chỉ chứa được khoảng log_{1+ε/2n} t ≈ (2n/ε) ln t giá trị. Ví dụ với S = ⟨104, 102, 201, 101⟩, t = 308, ε = 0,4: thuật toán trả về 302, tối ưu là 307, sai lệch 1,6% — tốt hơn nhiều so với 40% được bảo đảm.

## Khái niệm cần biết

- **Bài toán tối ưu (optimization problem), cực tiểu / cực đại:** mỗi lời giải khả dĩ có một chi phí dương; ta tìm lời giải có chi phí nhỏ nhất (bài toán cực tiểu, như phủ đỉnh, TSP) hoặc lớn nhất (bài toán cực đại, như MAX-3-CNF, tổng tập con, clique). Ví dụ: phủ đỉnh của đồ thị 7 đỉnh, 8 cạnh ở Mục 35.1 có các lời giải cỡ 3, 4, …, 7; tối ưu là 3. Quan trọng vì tỷ số xấp xỉ được định nghĩa đối xứng cho cả hai loại.
- **Thuật toán xấp xỉ (approximation algorithm):** thuật toán (ở chương này luôn chạy thời gian đa thức) trả về lời giải gần tối ưu. Ví dụ: APPROX-VERTEX-COVER trên đồ thị 7 đỉnh, 8 cạnh ở Mục 35.1 trả về 6 đỉnh {b, c, d, e, f, g} trong khi tối ưu là {b, d, e}. Đây là đối tượng của cả chương.
- **Tỷ số xấp xỉ ρ(n) (approximation ratio) và thuật toán ρ(n)-xấp xỉ:** thuật toán có tỷ số ρ(n) nếu với mọi đầu vào cỡ n, max(C/C*, C*/C) ≤ ρ(n), trong đó C là chi phí lời giải của thuật toán, C* là chi phí tối ưu. Khi ρ không phụ thuộc n ta nói "tỷ số ρ" và "thuật toán ρ-xấp xỉ". Ví dụ: bài cực tiểu với C* = 3, C = 6 cho tỷ số 2; bài cực đại với C* = 307, C = 302 cho tỷ số 307/302 ≈ 1,0166. Luôn ρ ≥ 1; ρ = 1 nghĩa là luôn tối ưu.
- **Lược đồ xấp xỉ (approximation scheme), PTAS, FPTAS:** lược đồ xấp xỉ nhận thêm ε > 0 và với mỗi ε cố định là thuật toán (1 + ε)-xấp xỉ. PTAS (polynomial-time approximation scheme): đa thức theo n khi ε cố định — có thể là O(n^(2/ε)), với ε = 0,1 là O(n²⁰), không dùng được. FPTAS (fully polynomial-time approximation scheme): đa thức theo cả n và 1/ε — ví dụ O((1/ε)² n³): giảm ε đi 10 lần chỉ làm thời gian tăng 100 lần. Quan trọng vì Mục 35.5 xây một FPTAS.
- **Phủ đỉnh (vertex cover):** tập đỉnh V' chạm vào mọi cạnh. Ví dụ với đường đi a – b – c – d (3 cạnh), {b, c} là phủ đỉnh cỡ 2 (tối ưu), {a, c} cũng là phủ đỉnh, {a, d} thì không (cạnh b – c không được phủ). Bài toán tìm phủ đỉnh nhỏ nhất là NP-khó.
- **Ghép cặp (matching), ghép cặp cực đại theo bao hàm (maximal matching), ghép cặp lớn nhất (maximum matching):** ghép cặp là tập cạnh đôi một không chung đỉnh. Cực đại theo bao hàm: không thêm được cạnh nào nữa. Lớn nhất: có nhiều cạnh nhất. Ví dụ đường đi a – b – c – d: {(b, c)} là cực đại theo bao hàm (mọi cạnh khác đều chạm b hoặc c) nhưng không lớn nhất; {(a, b), (c, d)} là lớn nhất. Quan trọng vì các cạnh APPROX-VERTEX-COVER chọn tạo thành ghép cặp cực đại theo bao hàm, và kích thước của nó là cận dưới cho phủ đỉnh.
- **Cận dưới của giá trị tối ưu (lower bound on the optimum):** đại lượng dễ tính, chắc chắn ≤ C* (với bài cực tiểu). Ví dụ: với 8 điểm lưới ở Mục 35.2.1, cây khung nhỏ nhất nặng ≈ 11,892 ≤ hành trình tối ưu ≈ 14,715. Quan trọng vì mọi chứng minh tỷ số trong chương đều so lời giải với một cận như vậy.
- **Bài toán người bán hàng (traveling-salesman problem, TSP), hành trình (tour):** trên đồ thị đầy đủ với chi phí cạnh, tìm chu trình đi qua mỗi đỉnh đúng một lần (chu trình Hamilton) có tổng chi phí nhỏ nhất. Ví dụ 4 điểm là bốn đỉnh hình vuông cạnh 1: hành trình đi theo chu vi tốn 4, hành trình đi chéo (qua hai đường chéo) tốn 2 + 2√2 ≈ 4,83.
- **Bất đẳng thức tam giác (triangle inequality):** c(u, w) ≤ c(u, v) + c(v, w) — đi thẳng không đắt hơn đi vòng qua v. Ví dụ khoảng cách Euclid: từ (0, 0) đến (3, 4) là 5, qua (3, 0) là 3 + 4 = 7 ≥ 5. Quan trọng vì nó cho phép "đi tắt" bỏ đỉnh lặp lại mà không tăng chi phí, và thiếu nó thì TSP không xấp xỉ được.
- **Cây khung nhỏ nhất (minimum spanning tree), MST-PRIM:** cây nối mọi đỉnh với tổng trọng số nhỏ nhất (Chương 23). MST-PRIM chạy Θ(V²) trên đồ thị đầy đủ với cài đặt đơn giản (Exercise 23.2-2).
- **Duyệt cây theo thứ tự trước (preorder tree walk) và đường đi đầy đủ (full walk):** duyệt trước liệt kê mỗi đỉnh khi gặp lần đầu, trước các con. Đường đi đầy đủ liệt kê đỉnh cả khi gặp lần đầu lẫn mỗi khi quay lại sau khi thăm xong một cây con; nó đi qua mỗi cạnh của cây đúng hai lần. Ví dụ cây khung của 8 điểm lưới ở Mục 35.2.1 (gốc a, các cạnh a–b, b–c, b–h, a–d, d–e, e–f, e–g): đường đi đầy đủ là a, b, c, b, h, b, a, d, e, f, e, g, e, d, a; thứ tự trước là a, b, c, h, d, e, f, g.
- **Phủ tập hợp (set cover):** cho tập X và họ F các tập con có hợp bằng X, tìm ít tập nhất trong F có hợp bằng X. Ví dụ X = {1, 2, 3, 4, 5}, F = {{1, 2, 3}, {2, 4}, {3, 4}, {4, 5}}: phủ tối ưu {{1, 2, 3}, {4, 5}} cỡ 2. Tổng quát hoá phủ đỉnh (X là tập cạnh, mỗi đỉnh cho một tập gồm các cạnh dính vào nó).
- **Số điều hoà H(d) (harmonic number):** H(d) = 1 + 1/2 + … + 1/d, quy ước H(0) = 0; H(d) ≤ ln d + 1. Ví dụ H(3) = 11/6 ≈ 1,833, H(6) = 49/20 = 2,45. Đây là tỷ số xấp xỉ của tham lam cho phủ tập hợp.
- **Phân bổ chi phí (charging) c_x:** mỗi tập được tham lam chọn tốn 1, chia đều cho các phần tử nó phủ lần đầu. Ví dụ tập đầu tiên phủ 6 phần tử mới: mỗi phần tử nhận 1/6. Tổng mọi c_x bằng số tập đã chọn. Quan trọng vì đây là kỹ thuật chứng minh Định lý 35.4.
- **Thuật toán ngẫu nhiên ρ(n)-xấp xỉ (randomized approximation algorithm):** như thuật toán xấp xỉ nhưng tỷ số tính trên chi phí KỲ VỌNG. Ví dụ: với 8 mệnh đề 3-CNF, gán ngẫu nhiên thoả trung bình 7 mệnh đề.
- **MAX-3-CNF (MAX-3-CNF satisfiability):** cho công thức dạng hội các mệnh đề, mỗi mệnh đề là tuyển của đúng 3 literal khác nhau; tìm phép gán làm đúng nhiều mệnh đề nhất. Ví dụ (x₁ ∨ x₂ ∨ x₃) ∧ (¬x₁ ∨ ¬x₂ ∨ ¬x₃): gán x₁ = 1, x₂ = 0 thoả cả hai.
- **Quy hoạch nguyên 0-1 (0-1 integer program) và nới lỏng quy hoạch tuyến tính (linear-programming relaxation):** quy hoạch nguyên yêu cầu biến nhận 0 hoặc 1 (NP-khó); nới lỏng thay bằng 0 ≤ x ≤ 1 (giải được trong đa thức, Chương 29). Ví dụ phủ đỉnh của tam giác a, b, c trọng số 1: quy hoạch nguyên có tối ưu 2; nới lỏng có tối ưu 1,5 tại x = (1/2, 1/2, 1/2). Giá trị nới lỏng luôn là cận dưới cho giá trị nguyên (bài cực tiểu).
- **Làm tròn (rounding):** biến nghiệm phân số thành nghiệm nguyên. Ở đây: x̄(v) ≥ 1/2 thì lấy v. Ví dụ tam giác trên: cả ba đỉnh có x̄ = 1/2 nên lấy cả ba, trọng số 3 ≤ 2 · 1,5.
- **Phủ đỉnh có trọng số nhỏ nhất (minimum-weight vertex cover):** mỗi đỉnh có trọng số dương, tìm phủ đỉnh có tổng trọng số nhỏ nhất. Ví dụ cạnh duy nhất (u, v) với w(u) = 1, w(v) = 1000: tối ưu là {u}, trọng số 1; APPROX-VERTEX-COVER lấy cả hai, trọng số 1001 — vì vậy cần thuật toán khác.
- **Bài toán tổng tập con (subset-sum), dạng tối ưu:** tìm tập con của {x₁, …, xₙ} có tổng lớn nhất không vượt t. Ví dụ {104, 102, 201, 101}, t = 308: tối ưu 307 = 104 + 102 + 101.
- **Pᵢ, L + x, MERGE-LISTS:** Pᵢ là tập mọi tổng của các tập con (kể cả rỗng) của {x₁, …, xᵢ}; L + x là danh sách cộng x vào từng phần tử; MERGE-LISTS trộn hai danh sách đã sắp xếp, bỏ giá trị trùng, thời gian O(|L| + |L'|). Ví dụ S = {1, 4, 5}: P₁ = {0, 1}, P₂ = {0, 1, 4, 5}, P₃ = {0, 1, 4, 5, 6, 9, 10}.
- **Tỉa danh sách (trimming) với tham số δ:** bỏ càng nhiều phần tử càng tốt sao cho mỗi phần tử y bị bỏ có một phần tử z còn lại với y/(1 + δ) ≤ z ≤ y. Ví dụ δ = 0,1: ⟨10, 11, 12, 15, 20, 21, 22, 23, 24, 29⟩ thành ⟨10, 12, 15, 20, 23, 29⟩ (11 được 10 đại diện, 21 và 22 được 20 đại diện, 24 được 23 đại diện).
- **Kỹ thuật tạo khoảng cách (gap technique) để chứng minh không xấp xỉ được:** biến thể hiện "có" của một bài NP-khó X thành thể hiện của bài cực tiểu Y với giá trị ≤ k, thể hiện "không" thành giá trị > ρk; khi đó thuật toán ρ-xấp xỉ cho Y giải được X. Ví dụ Định lý 35.3: k = |V|, ρk = ρ|V|.

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 1106–1108)

Nhiều bài toán có ý nghĩa thực tế là NP-đầy đủ, nhưng quá quan trọng để bỏ qua chỉ vì ta không biết cách tìm lời giải tối ưu trong thời gian đa thức. Dù một bài toán NP-đầy đủ, vẫn có hy vọng. Có ít nhất ba cách đi vòng qua NP-đầy đủ:

1. Nếu đầu vào thực tế nhỏ, một thuật toán thời gian mũ có thể hoàn toàn thoả đáng.
2. Có thể tách ra những trường hợp riêng quan trọng giải được trong thời gian đa thức.
3. Có thể nghĩ ra cách tìm lời giải **gần tối ưu** (near-optimal) trong thời gian đa thức (trong trường hợp xấu nhất hoặc kỳ vọng). Trong thực tế, gần tối ưu thường là đủ tốt.

Thuật toán trả về lời giải gần tối ưu gọi là **thuật toán xấp xỉ** (approximation algorithm). Chương này trình bày các thuật toán xấp xỉ thời gian đa thức cho một số bài toán NP-đầy đủ.

#### Tỷ số hiệu năng của thuật toán xấp xỉ (Performance ratios for approximation algorithms)

Giả sử ta làm việc với một bài toán tối ưu trong đó mỗi lời giải khả dĩ có chi phí **dương**, và ta muốn tìm lời giải gần tối ưu. Tuỳ bài toán, lời giải tối ưu có thể là lời giải chi phí lớn nhất hoặc nhỏ nhất; tức là bài toán có thể là bài toán cực đại hoá hoặc cực tiểu hoá.

Thuật toán cho một bài toán có **tỷ số xấp xỉ** (approximation ratio) ρ(n) nếu, với mọi đầu vào cỡ n, chi phí C của lời giải do thuật toán sinh ra nằm trong hệ số ρ(n) của chi phí C* của một lời giải tối ưu:

```text
max( C / C* , C* / C ) ≤ ρ(n)                                        (35.1)
```

Nếu thuật toán đạt tỷ số xấp xỉ ρ(n), ta gọi nó là **thuật toán ρ(n)-xấp xỉ** (ρ(n)-approximation algorithm). Định nghĩa áp dụng cho cả hai loại bài toán:

- Với bài toán cực đại, 0 < C ≤ C*, và tỷ số C*/C cho biết chi phí tối ưu lớn hơn chi phí lời giải xấp xỉ bao nhiêu lần.
- Với bài toán cực tiểu, 0 < C* ≤ C, và tỷ số C/C* cho biết chi phí lời giải xấp xỉ lớn hơn chi phí tối ưu bao nhiêu lần.

Vì mọi lời giải có chi phí dương, các tỷ số luôn xác định. Tỷ số xấp xỉ không bao giờ nhỏ hơn 1, vì C/C* ≤ 1 kéo theo C*/C ≥ 1. Do đó thuật toán 1-xấp xỉ cho lời giải tối ưu, còn thuật toán có tỷ số lớn có thể trả về lời giải tệ hơn tối ưu rất nhiều. (Chú thích của sách: khi tỷ số không phụ thuộc n, ta dùng "tỷ số xấp xỉ ρ" và "thuật toán ρ-xấp xỉ".)

Ví dụ của người tổng hợp: bài cực tiểu có C* = 10, thuật toán trả C = 15: max(1,5; 0,667) = 1,5. Bài cực đại có C* = 10, thuật toán trả C = 8: max(0,8; 1,25) = 1,25. Công thức max(…) tự chọn đúng tỷ số ≥ 1.

Với nhiều bài toán, có thuật toán xấp xỉ thời gian đa thức với tỷ số hằng nhỏ; với các bài khác, thuật toán đa thức tốt nhất đã biết có tỷ số tăng theo cỡ đầu vào n — ví dụ bài phủ tập hợp ở Mục 35.3.

Một số bài NP-đầy đủ cho phép thuật toán xấp xỉ đa thức đạt tỷ số ngày càng tốt khi dùng ngày càng nhiều thời gian tính toán — tức là đổi thời gian lấy chất lượng xấp xỉ. Ví dụ là bài tổng tập con ở Mục 35.5. Tình huống này đủ quan trọng để có tên riêng:

- **Lược đồ xấp xỉ** (approximation scheme) cho một bài toán tối ưu là thuật toán xấp xỉ nhận đầu vào không chỉ là một thể hiện của bài toán mà còn một giá trị ε > 0, sao cho với mỗi ε cố định, lược đồ là thuật toán (1 + ε)-xấp xỉ.
- Lược đồ là **lược đồ xấp xỉ thời gian đa thức** (polynomial-time approximation scheme, PTAS) nếu với mỗi ε > 0 cố định, nó chạy thời gian đa thức theo cỡ n của thể hiện đầu vào.

Thời gian chạy của PTAS có thể tăng rất nhanh khi ε giảm, ví dụ O(n^(2/ε)). Lý tưởng là khi ε giảm một hệ số hằng, thời gian cần thiết không tăng quá một hệ số hằng (không nhất thiết cùng hệ số mà ε giảm).

- Lược đồ là **lược đồ xấp xỉ thời gian đa thức đầy đủ** (fully polynomial-time approximation scheme, FPTAS) nếu nó là lược đồ xấp xỉ và thời gian chạy đa thức theo cả 1/ε lẫn cỡ n của đầu vào. Ví dụ thời gian O((1/ε)² n³). Với lược đồ như vậy, mọi phép giảm ε theo hệ số hằng đi kèm phép tăng thời gian theo hệ số hằng tương ứng.

So sánh bằng số (người tổng hợp): n = 100. PTAS O(n^(2/ε)): ε = 1 cho 100² = 10⁴; ε = 0,5 cho 100⁴ = 10⁸; ε = 0,1 cho 100²⁰ = 10⁴⁰ — vô dụng. FPTAS O((1/ε)² n³): ε = 1 cho 10⁶; ε = 0,1 cho 10⁸; ε = 0,01 cho 10¹⁰ — vẫn khả thi.

#### Dàn ý chương (Chapter outline)

Bốn mục đầu đưa ví dụ về thuật toán xấp xỉ đa thức cho các bài NP-đầy đủ; mục thứ năm trình bày một FPTAS. Mục 35.1: bài phủ đỉnh, bài cực tiểu NP-đầy đủ có thuật toán tỷ số 2. Mục 35.2: thuật toán tỷ số 2 cho TSP khi hàm chi phí thoả bất đẳng thức tam giác; và chứng minh rằng không có bất đẳng thức tam giác thì, với mọi hằng ρ ≥ 1, không tồn tại thuật toán ρ-xấp xỉ trừ khi P = NP. Mục 35.3: dùng phương pháp tham lam làm thuật toán xấp xỉ hiệu quả cho bài phủ tập hợp, cho lời giải tệ nhất lớn hơn tối ưu một hệ số lôgarit. Mục 35.4: hai thuật toán nữa — thuật toán ngẫu nhiên đơn giản cho dạng tối ưu của 3-CNF-SAT với tỷ số kỳ vọng 8/7, và dùng quy hoạch tuyến tính để xây thuật toán 2-xấp xỉ cho biến thể có trọng số của phủ đỉnh. Mục 35.5: FPTAS cho bài tổng tập con.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: các bộ định tuyến xe giao hàng, bộ xếp lịch ca làm việc, bộ cấp phát máy ảo trong trung tâm dữ liệu đều giải những bài NP-khó (TSP có ràng buộc, lập lịch, xếp thùng nhiều chiều). Chúng hầu như không bao giờ tìm lời giải tối ưu; chúng chạy heuristic hoặc thuật toán xấp xỉ, đôi khi kèm một cận dưới (từ quy hoạch tuyến tính nới lỏng) để báo "lời giải hiện tại cách tối ưu không quá x%". Đó chính là tư duy "so với cận" của chương này.

### 2. Bài toán phủ đỉnh (35.1 The vertex-cover problem, trang 1108–1111)

Mục 34.5.2 đã định nghĩa bài phủ đỉnh và chứng minh nó NP-đầy đủ. Nhắc lại: **phủ đỉnh** (vertex cover) của đồ thị vô hướng G = (V, E) là tập con V' ⊆ V sao cho nếu (u, v) là một cạnh của G thì u ∈ V' hoặc v ∈ V' (hoặc cả hai). Kích thước của phủ đỉnh là số đỉnh của nó.

**Bài toán phủ đỉnh** (vertex-cover problem) là tìm phủ đỉnh cỡ nhỏ nhất trong một đồ thị vô hướng cho trước; phủ như vậy gọi là **phủ đỉnh tối ưu** (optimal vertex cover). Đây là dạng tối ưu của một bài quyết định NP-đầy đủ.

Dù không biết cách tìm phủ đỉnh tối ưu trong thời gian đa thức, ta có thể tìm hiệu quả một phủ đỉnh gần tối ưu. Thuật toán sau nhận đồ thị vô hướng G và trả về phủ đỉnh có kích thước bảo đảm không quá hai lần kích thước phủ tối ưu:

```text
APPROX-VERTEX-COVER(G)
1  C = ∅
2  E' = G.E
3  while E' ≠ ∅
4      let (u, v) be an arbitrary edge of E'
5      C = C ∪ {u, v}
6      remove from E' every edge incident on either u or v
7  return C
```

Biến C chứa phủ đỉnh đang dựng. Dòng 1 khởi tạo C rỗng. Dòng 2 đặt E' là bản sao tập cạnh G.E. Vòng lặp dòng 3–6 lặp lại: chọn một cạnh (u, v) bất kỳ của E', thêm cả hai đầu mút u, v vào C, và xoá khỏi E' mọi cạnh đã được u hoặc v phủ. Dòng 7 trả về C. Với danh sách kề để biểu diễn E', thời gian chạy là O(V + E).

#### Ví dụ chạy tay (Hình 35.1 của sách)

Đồ thị đầu vào G có 7 đỉnh a, b, c, d, e, f, g và 8 cạnh. Vẽ lại vị trí và các cạnh:

```text
     b ──── c ──── d
     │      │    ╱ │ ╲
     │      │  ╱   │   ╲
     a      e ──── f     g

  Cạnh: (a,b), (b,c), (c,d), (c,e), (d,e), (d,f), (e,f), (d,g)
```

Diễn biến theo chú thích hình của sách:

| Bước | Cạnh được chọn (dòng 4) | Thêm vào C | Cạnh bị xoá khỏi E' (dòng 6) | E' còn lại |
|---|---|---|---|---|
| (a) | — | — | — | cả 8 cạnh |
| (b) | (b, c) | b, c | (a, b), (b, c), (c, d), (c, e) | (d, e), (d, f), (e, f), (d, g) |
| (c) | (e, f) | e, f | (e, f), (d, e), (d, f) | (d, g) |
| (d) | (d, g) | d, g | (d, g) | rỗng |
| (e) | vòng lặp dừng | — | — | — |

Kết quả (e): C = {b, c, d, e, f, g}, 6 đỉnh. Phần (f) của hình gốc cho phủ đỉnh tối ưu chỉ gồm 3 đỉnh {b, d, e}. Kiểm tra (người tổng hợp): b phủ (a, b), (b, c); d phủ (c, d), (d, e), (d, f), (d, g); e phủ (c, e), (e, f) — đủ 8 cạnh. Không có phủ 2 đỉnh vì ba cạnh (a, b), (c, e), (d, g) đôi một không chung đỉnh. Ở ví dụ này tỷ số đạt đúng 6/3 = 2 — cận của Định lý 35.1 là chặt.

**Định lý 35.1.** APPROX-VERTEX-COVER là thuật toán 2-xấp xỉ thời gian đa thức.

*Chứng minh.* Thời gian đa thức đã chỉ ra ở trên.

Tập C trả về là một phủ đỉnh, vì thuật toán lặp cho tới khi mọi cạnh của G.E đã được một đỉnh nào đó trong C phủ.

Để thấy C không quá hai lần phủ tối ưu, gọi A là tập các cạnh được chọn ở dòng 4. Để phủ các cạnh trong A, mọi phủ đỉnh — đặc biệt là phủ tối ưu C* — phải chứa ít nhất một đầu mút của mỗi cạnh trong A. Không hai cạnh nào trong A chung đầu mút, vì khi một cạnh được chọn ở dòng 4, mọi cạnh khác dính vào hai đầu mút của nó bị xoá khỏi E' ở dòng 6. Do đó không hai cạnh nào trong A được phủ bởi cùng một đỉnh của C*, và ta có cận dưới

```text
|C*| ≥ |A|                                                          (35.2)
```

cho kích thước phủ tối ưu. Mỗi lần thực hiện dòng 4 chọn một cạnh mà cả hai đầu mút chưa có trong C, cho cận trên (thực ra là đẳng thức) cho kích thước phủ trả về:

```text
|C| = 2|A|                                                          (35.3)
```

Kết hợp (35.2) và (35.3):

```text
|C| = 2|A|
    ≤ 2|C*|
```

∎

**Suy ngẫm về chứng minh.** Thoạt nhìn, có thể thắc mắc làm sao chứng minh được kích thước phủ trả về không quá hai lần tối ưu khi ta còn không biết kích thước tối ưu. Thay vì cần biết chính xác, ta dựa vào một **cận dưới**. Như Exercise 35.1-2 yêu cầu chứng minh, tập cạnh A thực ra là một **ghép cặp cực đại theo bao hàm** (maximal matching) trong G — một ghép cặp không phải tập con thực sự của ghép cặp nào khác. Như lập luận trong chứng minh, kích thước của một ghép cặp cực đại là cận dưới cho kích thước phủ đỉnh tối ưu. Thuật toán trả về phủ đỉnh không quá hai lần kích thước ghép cặp đó. Bằng cách liên hệ kích thước lời giải với cận dưới, ta có tỷ số xấp xỉ. Phương pháp này được dùng lại ở các mục sau.

Nhận xét của người tổng hợp: vì sao không chỉ lấy một đầu mút? Vì ta không biết đầu mút nào "đúng". Lấy một đầu mút tuỳ ý có thể rất tệ: với sao K₁,ₙ, nếu luôn lấy đầu lá thì được n đỉnh trong khi tối ưu là 1 (tâm). Lấy cả hai đầu mút đảm bảo ta luôn có đỉnh mà tối ưu dùng, với giá gấp đôi.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: đặt camera giám sát ở các ngã tư sao cho mọi con đường đều được nhìn thấy, hay chọn tập máy chủ đặt bộ giám sát lưu lượng sao cho mọi liên kết mạng đều có ít nhất một đầu được giám sát, là các bài phủ đỉnh. Thuật toán "lấy cả hai đầu của một liên kết chưa được giám sát" rất dễ cài đặt, chạy trên luồng cạnh (streaming) chỉ với một lượt đọc, và đảm bảo không tốn quá gấp đôi.

### 3. Bài toán người bán hàng (35.2 The traveling-salesman problem, trang 1111–1117)

Trong bài toán người bán hàng (giới thiệu ở Mục 34.5.4), ta có đồ thị vô hướng **đầy đủ** G = (V, E) với chi phí nguyên không âm c(u, v) cho mỗi cạnh (u, v) ∈ E, và phải tìm một chu trình Hamilton (một **hành trình**, tour) của G có chi phí nhỏ nhất. Mở rộng ký hiệu, c(A) là tổng chi phí các cạnh trong tập con A ⊆ E:

```text
c(A) = Σ_{(u,v)∈A} c(u, v)
```

Trong nhiều tình huống thực tế, cách rẻ nhất để đi từ u tới w là đi thẳng, không dừng trung gian. Nói cách khác, bỏ một điểm dừng trung gian không bao giờ làm tăng chi phí. Ta hình thức hoá điều này: hàm chi phí c thoả **bất đẳng thức tam giác** (triangle inequality) nếu với mọi đỉnh u, v, w ∈ V,

```text
c(u, w) ≤ c(u, v) + c(v, w)
```

Bất đẳng thức tam giác có vẻ tự nhiên và tự động đúng trong nhiều ứng dụng. Ví dụ, nếu các đỉnh là điểm trên mặt phẳng và chi phí giữa hai đỉnh là khoảng cách Euclid thông thường, bất đẳng thức tam giác thoả. Ngoài ra nhiều hàm chi phí khác cũng thoả.

Như Exercise 35.2-2 cho thấy, TSP vẫn NP-đầy đủ ngay cả khi yêu cầu hàm chi phí thoả bất đẳng thức tam giác. Vì vậy không nên mong tìm được thuật toán đa thức giải đúng; ta tìm thuật toán xấp xỉ tốt. Mục 35.2.1 xét thuật toán 2-xấp xỉ cho TSP có bất đẳng thức tam giác. Mục 35.2.2 chứng minh rằng không có bất đẳng thức tam giác thì không tồn tại thuật toán xấp xỉ đa thức với tỷ số hằng trừ khi P = NP.

#### 35.2.1 TSP có bất đẳng thức tam giác (The traveling-salesman problem with the triangle inequality)

Áp dụng phương pháp của mục trước: trước hết tính một cấu trúc — **cây khung nhỏ nhất** — mà trọng số của nó là cận dưới cho độ dài hành trình tối ưu. Sau đó dùng cây khung nhỏ nhất để tạo hành trình có chi phí không quá hai lần trọng số cây, miễn là hàm chi phí thoả bất đẳng thức tam giác. Thuật toán sau gọi thuật toán cây khung nhỏ nhất MST-PRIM (Mục 23.2) làm thủ tục con. Tham số G là đồ thị vô hướng đầy đủ, hàm chi phí c thoả bất đẳng thức tam giác.

```text
APPROX-TSP-TOUR(G, c)
1  select a vertex r ∈ G.V to be a "root" vertex
2  compute a minimum spanning tree T for G from root r
       using MST-PRIM(G, c, r)
3  let H be a list of vertices, ordered according to when they are first visited
       in a preorder tree walk of T
4  return the hamiltonian cycle H
```

Dòng 1: chọn một đỉnh r làm gốc. Dòng 2: dựng cây khung nhỏ nhất T từ gốc r. Dòng 3: H là danh sách các đỉnh xếp theo thời điểm được thăm lần đầu trong phép **duyệt cây theo thứ tự trước** (preorder tree walk) của T — nhắc lại từ Mục 12.1: phép duyệt trước thăm đệ quy mọi đỉnh của cây, liệt kê một đỉnh khi gặp nó lần đầu, trước khi thăm các con của nó. Dòng 4: trả về chu trình Hamilton đi theo thứ tự H rồi quay về đỉnh đầu.

Theo Exercise 23.2-2, ngay cả với cài đặt đơn giản của MST-PRIM, thời gian của APPROX-TSP-TOUR là Θ(V²) (đồ thị đầy đủ có Θ(V²) cạnh).

##### Ví dụ chạy tay (Hình 35.2 của sách)

Tám đỉnh nằm trên giao điểm của lưới nguyên; chi phí giữa hai điểm là khoảng cách Euclid. Sách chỉ nói "f cách h một đơn vị sang phải và hai đơn vị lên trên"; đọc từ hình, người tổng hợp đặt toạ độ (x sang phải, y lên trên):

| Đỉnh | a | b | c | d | e | f | g | h |
|---|---|---|---|---|---|---|---|---|
| (x, y) | (1, 4) | (1, 2) | (0, 1) | (3, 4) | (4, 3) | (3, 2) | (5, 2) | (2, 0) |

Vẽ lại lưới:

```text
  y=4    .  a  .  d  .  .
  y=3    .  .  .  .  e  .
  y=2    .  b  .  f  .  g
  y=1    c  .  .  .  .  .
  y=0    .  .  h  .  .  .
        x=0 1  2  3  4  5
```

(a) Đồ thị đầu vào là đồ thị đầy đủ trên 8 đỉnh (28 cạnh).

(b) Cây khung nhỏ nhất T dựng bởi MST-PRIM từ gốc a. Các đỉnh tình cờ được đặt tên sao cho MST-PRIM thêm chúng vào cây theo thứ tự bảng chữ cái. Các cạnh của T (người tổng hợp tính độ dài):

| Cạnh của T | a–b | b–c | b–h | a–d | d–e | e–f | e–g |
|---|---|---|---|---|---|---|---|
| Độ dài | 2 | √2 ≈ 1,414 | √5 ≈ 2,236 | 2 | √2 ≈ 1,414 | √2 ≈ 1,414 | √2 ≈ 1,414 |

Tổng c(T) = 4 + √5 + 4√2 ≈ 11,892. Cấu trúc cây (gốc a):

```text
              a
            ╱   ╲
           b     d
          ╱ ╲     ╲
         c   h     e
                  ╱ ╲
                 f   g
```

(c) Đi quanh cây bắt đầu từ a. Đường đi đầy đủ thăm các đỉnh theo thứ tự a, b, c, b, h, b, a, d, e, f, e, g, e, d, a. Phép duyệt trước chỉ liệt kê một đỉnh khi gặp lần đầu (trong hình, đánh dấu bằng chấm cạnh mỗi đỉnh), cho thứ tự a, b, c, h, d, e, f, g.

(d) Hành trình H thăm các đỉnh theo thứ tự duyệt trước — chính là hành trình APPROX-TSP-TOUR trả về. Tổng chi phí ≈ 19,074. Kiểm tra (người tổng hợp):

| Cạnh của H | a–b | b–c | c–h | h–d | d–e | e–f | f–g | g–a |
|---|---|---|---|---|---|---|---|---|
| Độ dài | 2 | √2 | √5 | √17 ≈ 4,123 | √2 | √2 | 2 | √20 ≈ 4,472 |

Tổng = 4 + 3√2 + √5 + √17 + √20 ≈ 4 + 4,243 + 2,236 + 4,123 + 4,472 = 19,074. Khớp sách.

(e) Hành trình tối ưu H* của đồ thị: a, b, c, h, f, g, e, d, a, chi phí ≈ 14,715. Kiểm tra: a–b 2, b–c √2, c–h √5, h–f √5, f–g 2, g–e √2, e–d √2, d–a 2; tổng = 6 + 3√2 + 2√5 ≈ 6 + 4,243 + 4,472 = 14,715. Người tổng hợp đã vét cạn mọi 7! = 5.040 thứ tự và xác nhận đây là tối ưu. Sách nói hành trình tối ưu ngắn hơn khoảng 23%: (19,074 − 14,715)/19,074 ≈ 22,9%.

Kiểm tra các bất đẳng thức của chứng minh dưới đây trên ví dụ: c(T) ≈ 11,892 ≤ c(H*) ≈ 14,715; c(W) = 2c(T) ≈ 23,785; c(H) ≈ 19,074 ≤ c(W); tỷ số thực tế 19,074/14,715 ≈ 1,30 ≤ 2.

Ghi chú (người tổng hợp): cạnh c–h cũng dài √5, bằng b–h, nên MST-PRIM có thể chọn c–h thay cho b–h. Khi đó h là con của c và thứ tự duyệt trước vẫn là a, b, c, h, d, e, f, g — hành trình không đổi.

**Định lý 35.2.** APPROX-TSP-TOUR là thuật toán 2-xấp xỉ thời gian đa thức cho TSP có bất đẳng thức tam giác.

*Chứng minh.* Thời gian đa thức đã thấy ở trên.

Gọi H* là một hành trình tối ưu trên tập đỉnh đã cho. Bỏ một cạnh bất kỳ khỏi một hành trình ta được một cây khung (thực ra là một đường đi Hamilton), và chi phí mỗi cạnh không âm. Vì vậy trọng số cây khung nhỏ nhất T tính ở dòng 2 là cận dưới cho chi phí hành trình tối ưu:

```text
c(T) ≤ c(H*)                                                        (35.4)
```

**Đường đi đầy đủ** (full walk) của T liệt kê các đỉnh khi thăm lần đầu và cả mỗi khi quay lại chúng sau khi thăm một cây con. Gọi đường đi đầy đủ này là W. Trong ví dụ, W là a, b, c, b, h, b, a, d, e, f, e, g, e, d, a. Vì đường đi đầy đủ đi qua mỗi cạnh của T đúng hai lần, ta có (mở rộng định nghĩa chi phí c một cách tự nhiên cho đa tập cạnh):

```text
c(W) = 2c(T)                                                        (35.5)
```

(35.4) và (35.5) cho

```text
c(W) ≤ 2c(H*)                                                       (35.6)
```

nên chi phí của W nằm trong hệ số 2 của chi phí tối ưu.

Đáng tiếc, W nói chung không phải một hành trình, vì nó thăm một số đỉnh nhiều lần. Tuy nhiên, theo bất đẳng thức tam giác, có thể xoá một lần thăm bất kỳ đỉnh nào khỏi W mà chi phí không tăng: nếu xoá đỉnh v nằm giữa các lần thăm u và w, thứ tự mới chỉ định đi thẳng từ u tới w, và c(u, w) ≤ c(u, v) + c(v, w). Áp dụng lặp lại phép này, ta xoá khỏi W mọi lần thăm trừ lần đầu tiên của mỗi đỉnh. Trong ví dụ, còn lại thứ tự a, b, c, h, d, e, f, g — chính là thứ tự duyệt trước của T. Gọi H là chu trình ứng với thứ tự duyệt trước này. Nó là chu trình Hamilton vì mỗi đỉnh được thăm đúng một lần, và chính là chu trình APPROX-TSP-TOUR tính. Vì H thu được bằng cách xoá đỉnh khỏi W,

```text
c(H) ≤ c(W)                                                         (35.7)
```

Kết hợp (35.6) và (35.7): c(H) ≤ 2c(H*). ∎

Minh hoạ phép "đi tắt" trên ví dụ (người tổng hợp): trong W, đoạn c, b, h được thay bằng c, h: c(c, h) = √5 ≈ 2,236 ≤ c(c, b) + c(b, h) = √2 + √5 ≈ 3,650. Đoạn h, b, a, d được thay bằng h, d: √17 ≈ 4,123 ≤ √5 + 2 + 2 ≈ 6,236. Cuối cùng đoạn g, e, d, a được thay bằng g, a: √20 ≈ 4,472 ≤ √2 + √2 + 2 ≈ 4,828.

Dù có tỷ số xấp xỉ đẹp theo Định lý 35.2, APPROX-TSP-TOUR thường không phải lựa chọn thực tế tốt nhất cho bài này. Có những thuật toán xấp xỉ khác thường chạy tốt hơn nhiều trong thực tế (xem tài liệu ở ghi chú cuối chương).

#### 35.2.2 TSP tổng quát (The general traveling-salesman problem)

Nếu bỏ giả định hàm chi phí thoả bất đẳng thức tam giác, ta không thể tìm hành trình xấp xỉ tốt trong thời gian đa thức trừ khi P = NP.

**Định lý 35.3.** Nếu P ≠ NP thì với mọi hằng số ρ ≥ 1, không có thuật toán xấp xỉ thời gian đa thức với tỷ số ρ cho TSP tổng quát.

*Chứng minh.* Chứng minh bằng phản chứng. Giả sử ngược lại, với một số ρ ≥ 1 nào đó, có thuật toán xấp xỉ đa thức A với tỷ số ρ. Không mất tổng quát, giả sử ρ nguyên (làm tròn lên nếu cần). Ta sẽ chỉ cách dùng A để giải bài chu trình Hamilton (định nghĩa ở Mục 34.2) trong thời gian đa thức. Vì Định lý 34.13 nói bài chu trình Hamilton là NP-đầy đủ, Định lý 34.4 kéo theo: nếu giải được nó trong đa thức thì P = NP.

Cho G = (V, E) là một thể hiện của bài chu trình Hamilton. Ta muốn xác định hiệu quả G có chứa chu trình Hamilton không, nhờ thuật toán giả định A. Biến G thành thể hiện TSP như sau. Gọi G' = (V, E') là đồ thị đầy đủ trên V:

```text
E' = { (u, v) : u, v ∈ V và u ≠ v }
```

Gán chi phí nguyên cho mỗi cạnh của E':

```text
c(u, v) = 1           nếu (u, v) ∈ E
          ρ|V| + 1    nếu ngược lại
```

Có thể dựng biểu diễn của G' và c từ biểu diễn của G trong thời gian đa thức theo |V| và |E|.

Xét bài TSP (G', c). Nếu G có chu trình Hamilton H, hàm c gán chi phí 1 cho mỗi cạnh của H, nên (G', c) có hành trình chi phí |V|. Ngược lại, nếu G không có chu trình Hamilton, mọi hành trình của G' phải dùng ít nhất một cạnh không thuộc E. Nhưng mọi hành trình dùng một cạnh không thuộc E có chi phí ít nhất

```text
(ρ|V| + 1) + (|V| − 1) = ρ|V| + |V|
                       > ρ|V|
```

Vì các cạnh không thuộc G đắt như vậy, có một **khoảng cách** ít nhất ρ|V| giữa chi phí của hành trình là chu trình Hamilton trong G (chi phí |V|) và chi phí của mọi hành trình khác (ít nhất ρ|V| + |V|). Do đó chi phí của hành trình không phải chu trình Hamilton trong G lớn hơn ít nhất ρ + 1 lần chi phí của hành trình là chu trình Hamilton trong G.

Giờ áp dụng A cho bài TSP (G', c). Vì A bảo đảm trả về hành trình chi phí không quá ρ lần tối ưu, nếu G có chu trình Hamilton thì A phải trả về nó (mọi hành trình khác tốn > ρ|V| = ρ · tối ưu). Nếu G không có chu trình Hamilton thì A trả về hành trình chi phí lớn hơn ρ|V|. Vì vậy, chỉ cần so chi phí kết quả của A với ρ|V|, ta giải được bài chu trình Hamilton trong thời gian đa thức. ∎

Ví dụ bằng số (người tổng hợp): ρ = 2, |V| = 5. Cạnh của G có chi phí 1, cạnh không thuộc G có chi phí 2 · 5 + 1 = 11. Nếu G có chu trình Hamilton, tối ưu là 5 và thuật toán 2-xấp xỉ phải trả hành trình ≤ 10 — chỉ có thể là hành trình toàn cạnh chi phí 1. Nếu G không có, mọi hành trình tốn ít nhất 11 + 4 = 15 > 10. Nhìn kết quả ≤ 10 hay > 10 là biết đáp án.

Nhận xét của người tổng hợp: hàm chi phí ở đây vi phạm bất đẳng thức tam giác thô bạo (cạnh "không thuộc G" chi phí ρ|V| + 1 trong khi đi vòng qua hai cạnh thuộc G chỉ tốn 2), đúng như Định lý 35.2 đòi hỏi.

**Kỹ thuật tổng quát.** Chứng minh Định lý 35.3 là ví dụ của một kỹ thuật chung để chứng minh một bài toán không xấp xỉ tốt được. Giả sử với một bài NP-khó X, ta dựng được trong thời gian đa thức một bài cực tiểu Y sao cho các thể hiện "có" của X ứng với thể hiện của Y có giá trị không quá k (với k nào đó), còn các thể hiện "không" của X ứng với thể hiện của Y có giá trị lớn hơn ρk. Khi đó ta đã chứng minh rằng, trừ khi P = NP, không có thuật toán ρ-xấp xỉ đa thức cho Y.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: trong định tuyến xe giao hàng, "chi phí" thường là thời gian di chuyển trên mạng đường thực, và thời gian đường ngắn nhất luôn thoả bất đẳng thức tam giác (nếu đi vòng nhanh hơn thì đường ngắn nhất đã đi vòng). Vì vậy bài toán thực tế thuộc vùng xấp xỉ được. Ngược lại, nếu chi phí là "giá vé máy bay trực tiếp" thì bất đẳng thức tam giác có thể bị vi phạm (bay nối chuyến rẻ hơn bay thẳng), và Định lý 35.3 cảnh báo rằng không thuật toán đa thức nào bảo đảm được chất lượng.

### 4. Bài toán phủ tập hợp (35.3 The set-covering problem, trang 1117–1122)

Bài toán phủ tập hợp là bài toán tối ưu mô hình hoá nhiều bài cần cấp phát tài nguyên. Bài quyết định tương ứng tổng quát hoá bài phủ đỉnh NP-đầy đủ nên cũng NP-khó. Tuy nhiên thuật toán xấp xỉ cho phủ đỉnh không áp dụng được ở đây, nên cần cách khác. Ta xét một heuristic tham lam đơn giản với tỷ số xấp xỉ lôgarit: khi thể hiện lớn dần, lời giải xấp xỉ có thể lớn dần so với lời giải tối ưu. Nhưng vì hàm lôgarit tăng khá chậm, thuật toán vẫn có thể cho kết quả hữu ích.

Một thể hiện (X, F) của **bài toán phủ tập hợp** (set-covering problem) gồm một tập hữu hạn X và một họ F các tập con của X, sao cho mọi phần tử của X thuộc ít nhất một tập con trong F:

```text
X = ⋃_{S∈F} S
```

Ta nói tập S ∈ F **phủ** (covers) các phần tử của nó. Bài toán là tìm họ con C ⊆ F cỡ nhỏ nhất mà các thành viên phủ toàn bộ X:

```text
X = ⋃_{S∈C} S                                                       (35.8)
```

Ta nói mọi C thoả (35.8) **phủ** X. Kích thước của C là **số tập** nó chứa, không phải số phần tử của các tập đó, vì mọi họ C phủ X đều phải chứa đủ |X| phần tử.

#### Ví dụ (Hình 35.3 của sách)

X gồm 12 điểm đen xếp thành lưới 4 hàng × 3 cột; F = {S₁, S₂, S₃, S₄, S₅, S₆}. Người tổng hợp đặt tên điểm theo (hàng, cột), hàng 1 ở trên cùng, cột 1 bên trái:

```text
            cột 1   cột 2   cột 3
  hàng 1   (1,1)   (1,2)   (1,3)
  hàng 2   (2,1)   (2,2)   (2,3)
  hàng 3   (3,1)   (3,2)   (3,3)
  hàng 4   (4,1)   (4,2)   (4,3)
```

Các tập (đọc từ hình phóng to):

| Tập | Hình dạng trong hình | Phần tử | Cỡ |
|---|---|---|---|
| S₁ | hình chữ nhật nằm ngang ôm hai hàng trên | (1,1), (1,2), (1,3), (2,1), (2,2), (2,3) | 6 |
| S₂ | hình vuông ôm hàng 2–3 của cột 2–3 | (2,2), (2,3), (3,2), (3,3) | 4 |
| S₃ | cột trái | (1,1), (2,1), (3,1), (4,1) | 4 |
| S₄ | cột giữa, có chỗ lồi sang trái ôm thêm (3,1) | (1,2), (2,2), (3,2), (4,2), (3,1) | 5 |
| S₅ | cột phải | (1,3), (2,3), (3,3), (4,3) | 4 |
| S₆ | hình chữ nhật nằm ngang ở hàng 4 | (4,1), (4,2) | 2 |

Phủ cỡ nhỏ nhất là C = {S₃, S₄, S₅}, cỡ 3 (ba cột phủ hết 12 điểm; không thể dùng 2 tập vì hai tập lớn nhất S₁ và S₄ chỉ phủ 6 + 3 = 9 điểm khác nhau). Thuật toán tham lam dưới đây cho phủ cỡ 4: chọn S₁, S₄, S₅ rồi S₃, hoặc S₁, S₄, S₅ rồi S₆.

Bài phủ tập hợp trừu tượng hoá nhiều bài toán tổ hợp thường gặp. Ví dụ đơn giản: X là tập các kỹ năng cần để giải một vấn đề, và có một nhóm người sẵn sàng tham gia, mỗi người có một số kỹ năng. Ta muốn lập một ủy ban càng ít người càng tốt sao cho với mỗi kỹ năng cần thiết trong X, có ít nhất một thành viên có kỹ năng đó. Trong dạng quyết định của bài phủ tập hợp, ta hỏi có tồn tại phủ cỡ không quá k hay không (k là tham số bổ sung của thể hiện). Dạng quyết định là NP-đầy đủ (Exercise 35.3-2).

#### Thuật toán xấp xỉ tham lam (A greedy approximation algorithm)

Phương pháp tham lam: ở mỗi bước, chọn tập S phủ nhiều nhất các phần tử còn chưa được phủ.

```text
GREEDY-SET-COVER(X, F)
1  U = X
2  C = ∅
3  while U ≠ ∅
4      select an S ∈ F that maximizes |S ∩ U|
5      U = U − S
6      C = C ∪ {S}
7  return C
```

Tập U chứa, ở mỗi giai đoạn, các phần tử còn chưa được phủ. Tập C chứa phủ đang dựng. Dòng 4 là bước ra quyết định tham lam: chọn tập S phủ được nhiều phần tử chưa phủ nhất (hoà thì chọn tuỳ ý). Sau khi chọn S, dòng 5 bỏ các phần tử của nó khỏi U, dòng 6 đưa S vào C. Khi thuật toán kết thúc, C là một họ con của F phủ X.

Chạy tay trên ví dụ (người tổng hợp; số trong ngoặc là |S ∩ U|):

| Vòng | U trước vòng | S₁ | S₂ | S₃ | S₄ | S₅ | S₆ | Chọn |
|---|---|---|---|---|---|---|---|---|
| 1 | cả 12 điểm | 6 | 4 | 4 | 5 | 4 | 2 | S₁ |
| 2 | (3,1), (4,1), (3,2), (4,2), (3,3), (4,3) | 0 | 2 | 2 | **3** | 2 | 2 | S₄ |
| 3 | (4,1), (3,3), (4,3) | 0 | 1 | 1 | 0 | **2** | 1 | S₅ |
| 4 | (4,1) | 0 | 0 | 1 | 0 | 0 | 1 | S₃ hoặc S₆ (hoà) |

Kết quả 4 tập, khớp sách. Ở vòng 2, chính điểm (3,1) trong chỗ lồi của S₄ làm S₄ thắng (3 so với 2); đó là chi tiết hình cần đọc đúng.

Có thể dễ dàng cài đặt GREEDY-SET-COVER chạy thời gian đa thức theo |X| và |F|. Số vòng lặp dòng 3–6 bị chặn trên bởi min(|X|, |F|) (mỗi vòng phủ ít nhất một phần tử mới và dùng một tập mới), và thân vòng lặp cài đặt được trong O(|X| |F|), nên một cài đặt đơn giản chạy O(|X| |F| min(|X|, |F|)). Exercise 35.3-3 yêu cầu thuật toán thời gian tuyến tính.

#### Phân tích (Analysis)

Ta chứng minh thuật toán tham lam trả về phủ không lớn hơn nhiều so với phủ tối ưu. Để tiện, trong chương này ký hiệu số điều hoà thứ d, H_d = Σᵢ₌₁ᵈ 1/i (Mục A.1), là H(d), với điều kiện biên H(0) = 0.

**Định lý 35.4.** GREEDY-SET-COVER là thuật toán ρ(n)-xấp xỉ thời gian đa thức, trong đó

```text
ρ(n) = H( max{ |S| : S ∈ F } )
```

*Chứng minh.* Thời gian đa thức đã chỉ ra.

Để chứng minh tỷ số ρ(n), ta gán chi phí 1 cho mỗi tập được thuật toán chọn, phân bổ chi phí đó cho các phần tử được phủ lần đầu, rồi dùng các chi phí này để suy ra quan hệ giữa kích thước phủ tối ưu C* và phủ C do thuật toán trả về. Gọi Sᵢ là tập thứ i được GREEDY-SET-COVER chọn; thuật toán chịu chi phí 1 khi thêm Sᵢ vào C. Ta chia đều chi phí chọn Sᵢ cho các phần tử được Sᵢ phủ lần đầu. Gọi c_x là chi phí phân cho phần tử x, với mỗi x ∈ X. Mỗi phần tử chỉ được gán chi phí một lần, khi nó được phủ lần đầu. Nếu x được phủ lần đầu bởi Sᵢ thì

```text
c_x = 1 / | Sᵢ − (S₁ ∪ S₂ ∪ … ∪ Sᵢ₋₁) |
```

Mỗi bước thuật toán gán đúng 1 đơn vị chi phí, nên

```text
|C| = Σ_{x∈X} c_x                                                   (35.9)
```

Mỗi phần tử x ∈ X thuộc ít nhất một tập của phủ tối ưu C*, nên

```text
Σ_{S∈C*} Σ_{x∈S} c_x ≥ Σ_{x∈X} c_x                                  (35.10)
```

(vế trái có thể đếm một phần tử nhiều lần nếu nó thuộc nhiều tập của C*; chi phí không âm). Kết hợp (35.9) và (35.10):

```text
|C| ≤ Σ_{S∈C*} Σ_{x∈S} c_x                                          (35.11)
```

Phần còn lại của chứng minh dựa trên bất đẳng thức then chốt sau, sẽ chứng minh ngay: với mọi tập S thuộc họ F,

```text
Σ_{x∈S} c_x ≤ H(|S|)                                                (35.12)
```

Từ (35.11) và (35.12):

```text
|C| ≤ Σ_{S∈C*} H(|S|)
    ≤ |C*| · H( max{ |S| : S ∈ F } )
```

và định lý được chứng minh.

Còn phải chứng minh (35.12). Xét một tập S ∈ F bất kỳ và với i = 1, 2, …, |C|, đặt

```text
uᵢ = | S − (S₁ ∪ S₂ ∪ … ∪ Sᵢ) |
```

là số phần tử của S còn chưa phủ sau khi thuật toán đã chọn S₁, S₂, …, Sᵢ. Đặt u₀ = |S| là số phần tử của S, ban đầu đều chưa phủ. Gọi k là chỉ số nhỏ nhất sao cho u_k = 0, tức là mọi phần tử của S được phủ bởi ít nhất một trong S₁, …, S_k và có phần tử của S chưa được S₁ ∪ … ∪ S_{k−1} phủ. Khi đó uᵢ₋₁ ≥ uᵢ, và có đúng uᵢ₋₁ − uᵢ phần tử của S được Sᵢ phủ lần đầu, với i = 1, 2, …, k. Do đó

```text
Σ_{x∈S} c_x = Σᵢ₌₁ᵏ (uᵢ₋₁ − uᵢ) · 1 / | Sᵢ − (S₁ ∪ S₂ ∪ … ∪ Sᵢ₋₁) |
```

Nhận xét rằng

```text
| Sᵢ − (S₁ ∪ S₂ ∪ … ∪ Sᵢ₋₁) | ≥ | S − (S₁ ∪ S₂ ∪ … ∪ Sᵢ₋₁) |
                              = uᵢ₋₁
```

vì lựa chọn tham lam Sᵢ bảo đảm S không thể phủ nhiều phần tử mới hơn Sᵢ (nếu không, thuật toán đã chọn S thay cho Sᵢ). Vậy

```text
Σ_{x∈S} c_x ≤ Σᵢ₌₁ᵏ (uᵢ₋₁ − uᵢ) · 1/uᵢ₋₁
```

Ta chặn đại lượng này như sau:

```text
Σ_{x∈S} c_x ≤ Σᵢ₌₁ᵏ (uᵢ₋₁ − uᵢ) · 1/uᵢ₋₁
            = Σᵢ₌₁ᵏ Σ_{j=uᵢ+1}^{uᵢ₋₁} 1/uᵢ₋₁
            ≤ Σᵢ₌₁ᵏ Σ_{j=uᵢ+1}^{uᵢ₋₁} 1/j            (vì j ≤ uᵢ₋₁)
            = Σᵢ₌₁ᵏ ( Σ_{j=1}^{uᵢ₋₁} 1/j − Σ_{j=1}^{uᵢ} 1/j )
            = Σᵢ₌₁ᵏ ( H(uᵢ₋₁) − H(uᵢ) )
            = H(u₀) − H(u_k)                          (vì tổng co rút)
            = H(u₀) − H(0)
            = H(u₀)                                   (vì H(0) = 0)
            = H(|S|)
```

hoàn tất chứng minh (35.12). ∎

Giải thích dòng thứ hai (người tổng hợp): (uᵢ₋₁ − uᵢ) · 1/uᵢ₋₁ là tổng của uᵢ₋₁ − uᵢ số hạng bằng nhau 1/uᵢ₋₁, viết thành tổng theo j chạy qua uᵢ₋₁ − uᵢ giá trị uᵢ + 1, …, uᵢ₋₁. Dòng thứ ba thay mỗi 1/uᵢ₋₁ bằng 1/j lớn hơn hoặc bằng. Ý nghĩa trực giác: khi S còn u phần tử chưa phủ, mỗi phần tử của S bị "tính phí" không quá 1/u; phần tử cuối cùng của S trả nhiều nhất 1/1, phần tử áp chót nhiều nhất 1/2, …, phần tử đầu tiên nhiều nhất 1/|S|.

Kiểm tra trên ví dụ 12 điểm, 6 tập ở trên (người tổng hợp): S₁ phủ 6 điểm mới, mỗi điểm hai hàng trên nhận c_x = 1/6; S₄ phủ 3 điểm mới (3,1), (3,2), (4,2), mỗi điểm 1/3; S₅ phủ (3,3), (4,3), mỗi điểm 1/2; S₃ phủ (4,1) với c = 1. Tổng 6 · 1/6 + 3 · 1/3 + 2 · 1/2 + 1 = 4 = |C|. Với S = S₃ (cột trái): Σ c_x = 1/6 + 1/6 + 1/3 + 1 = 5/3 ≈ 1,667 ≤ H(4) = 25/12 ≈ 2,083. Với S = S₄: 1/6 + 1/6 + 1/3 + 1/3 + 1/3 = 4/3 ≤ H(5). Với S = S₅: 1/6 + 1/6 + 1/2 + 1/2 = 4/3 ≤ H(4). Cộng ba tập của C*: 5/3 + 4/3 + 4/3 = 13/3 ≈ 4,33 ≥ |C| = 4, đúng như (35.11). Cận của định lý: |C*| · H(6) = 3 · 2,45 = 7,35 ≥ 4.

**Hệ quả 35.5.** GREEDY-SET-COVER là thuật toán (ln |X| + 1)-xấp xỉ thời gian đa thức.

*Chứng minh.* Dùng bất đẳng thức (A.14), H(d) ≤ ln d + 1, và Định lý 35.4 với max |S| ≤ |X|. ∎

Ví dụ (người tổng hợp): |X| = 10⁶ thì bảo đảm là ln 10⁶ + 1 ≈ 14,8 — lời giải có thể gấp gần 15 lần tối ưu trong trường hợp xấu nhất, nhưng không tệ hơn.

Trong một số ứng dụng, max{|S| : S ∈ F} là hằng số nhỏ, nên lời giải của GREEDY-SET-COVER không quá một hằng nhỏ lần tối ưu. Một ứng dụng như vậy: dùng heuristic này để tìm phủ đỉnh xấp xỉ cho đồ thị có bậc mọi đỉnh không quá 3 (mỗi đỉnh là một tập gồm ≤ 3 cạnh dính vào nó). Khi đó lời giải không quá H(3) = 11/6 lần tối ưu, một bảo đảm tốt hơn chút so với APPROX-VERTEX-COVER (tỷ số 2).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: chọn ít bộ kiểm thử nhất sao cho mọi dòng mã (hoặc mọi yêu cầu) được ít nhất một bộ kiểm thử chạm vào ("test suite minimization"), chọn ít vị trí đặt trạm phát sóng sao cho mọi khu dân cư được phủ sóng, chọn ít chữ ký virus nhất phát hiện được mọi mẫu mã độc — đều là phủ tập hợp, và thuật toán tham lam "chọn cái phủ thêm nhiều nhất" là lựa chọn mặc định trong thực tế.

### 5. Ngẫu nhiên hoá và quy hoạch tuyến tính (35.4 Randomization and linear programming, trang 1123–1128)

Mục này nghiên cứu hai kỹ thuật hữu ích để thiết kế thuật toán xấp xỉ: ngẫu nhiên hoá và quy hoạch tuyến tính. Ta đưa ra một thuật toán ngẫu nhiên đơn giản cho dạng tối ưu của 3-CNF-SAT, rồi dùng quy hoạch tuyến tính để thiết kế thuật toán xấp xỉ cho dạng có trọng số của phủ đỉnh. Mục này chỉ chạm bề mặt của hai kỹ thuật mạnh này; ghi chú cuối chương cho tài liệu đọc thêm.

#### Thuật toán xấp xỉ ngẫu nhiên cho MAX-3-CNF (A randomized approximation algorithm for MAX-3-CNF satisfiability)

Như một số thuật toán ngẫu nhiên tính lời giải chính xác, một số thuật toán ngẫu nhiên tính lời giải xấp xỉ. Thuật toán ngẫu nhiên cho một bài toán có **tỷ số xấp xỉ** ρ(n) nếu với mọi đầu vào cỡ n, chi phí **kỳ vọng** C của lời giải do thuật toán ngẫu nhiên sinh ra nằm trong hệ số ρ(n) của chi phí tối ưu C*:

```text
max( C / C* , C* / C ) ≤ ρ(n)                                       (35.13)
```

Thuật toán ngẫu nhiên đạt tỷ số ρ(n) gọi là **thuật toán ngẫu nhiên ρ(n)-xấp xỉ** (randomized ρ(n)-approximation algorithm). Nói cách khác, nó giống thuật toán xấp xỉ tất định, chỉ khác là tỷ số tính cho chi phí kỳ vọng.

Một thể hiện của 3-CNF-SAT (định nghĩa ở Mục 34.4) có thể thoả được hoặc không. Để thoả được, phải có phép gán biến làm mọi mệnh đề có giá trị 1. Nếu không thoả được, ta có thể muốn biết nó "gần" thoả được tới đâu, tức là tìm phép gán làm đúng nhiều mệnh đề nhất. Bài toán cực đại hoá này gọi là **MAX-3-CNF** (MAX-3-CNF satisfiability). Đầu vào giống 3-CNF-SAT, mục tiêu là trả về phép gán làm số mệnh đề có giá trị 1 lớn nhất. Ta sẽ chứng minh gán ngẫu nhiên mỗi biến bằng 1 với xác suất 1/2 và bằng 0 với xác suất 1/2 cho thuật toán ngẫu nhiên 8/7-xấp xỉ. Theo định nghĩa ở Mục 34.4, mỗi mệnh đề gồm đúng ba literal khác nhau. Ta giả định thêm không mệnh đề nào chứa cả một biến và phủ định của nó (Exercise 35.4-1 yêu cầu bỏ giả định này).

**Định lý 35.6.** Cho một thể hiện MAX-3-CNF với n biến x₁, x₂, …, xₙ và m mệnh đề, thuật toán ngẫu nhiên gán độc lập mỗi biến bằng 1 với xác suất 1/2 và bằng 0 với xác suất 1/2 là thuật toán ngẫu nhiên 8/7-xấp xỉ.

*Chứng minh.* Giả sử đã gán độc lập mỗi biến bằng 1 với xác suất 1/2, bằng 0 với xác suất 1/2. Với i = 1, 2, …, m, định nghĩa biến ngẫu nhiên chỉ thị

```text
Yᵢ = I{ mệnh đề i được thoả }
```

nên Yᵢ = 1 khi ít nhất một literal của mệnh đề thứ i có giá trị 1. Vì không literal nào xuất hiện hai lần trong cùng mệnh đề, và đã giả định không biến nào cùng phủ định của nó xuất hiện trong cùng mệnh đề, giá trị của ba literal trong mỗi mệnh đề độc lập với nhau. Mệnh đề không được thoả chỉ khi cả ba literal bằng 0, nên Pr{mệnh đề i không được thoả} = (1/2)³ = 1/8. Vậy Pr{mệnh đề i được thoả} = 1 − 1/8 = 7/8, và theo Bổ đề 5.1, E[Yᵢ] = 7/8. Gọi Y là tổng số mệnh đề được thoả, Y = Y₁ + Y₂ + … + Y_m. Khi đó

```text
E[Y] = E[ Σᵢ₌₁ᵐ Yᵢ ]
     = Σᵢ₌₁ᵐ E[Yᵢ]          (theo tính tuyến tính của kỳ vọng)
     = Σᵢ₌₁ᵐ 7/8
     = 7m/8
```

Hiển nhiên m là cận trên của số mệnh đề được thoả (kể cả với phép gán tối ưu), nên tỷ số xấp xỉ không quá m/(7m/8) = 8/7. ∎

Ví dụ (người tổng hợp): công thức gồm 8 mệnh đề trên 3 biến x₁, x₂, x₃, mỗi mệnh đề là một trong 8 cách đặt dấu phủ định, ví dụ (x₁ ∨ x₂ ∨ x₃), (x₁ ∨ x₂ ∨ ¬x₃), …, (¬x₁ ∨ ¬x₂ ∨ ¬x₃). Mỗi phép gán làm sai đúng một mệnh đề (mệnh đề có mọi literal ngược với phép gán), nên mọi phép gán, kể cả tối ưu, thoả đúng 7 mệnh đề. Kỳ vọng 7 · 8/8 = 7: ở ví dụ này thuật toán ngẫu nhiên luôn tối ưu. Ví dụ ngược lại: công thức thoả được hoàn toàn có m mệnh đề, tối ưu m; thuật toán chỉ kỳ vọng 7m/8 — tỷ số đúng 8/7.

#### Xấp xỉ phủ đỉnh có trọng số bằng quy hoạch tuyến tính (Approximating weighted vertex cover using linear programming)

Trong **bài toán phủ đỉnh trọng số nhỏ nhất** (minimum-weight vertex-cover problem), cho đồ thị vô hướng G = (V, E) trong đó mỗi đỉnh v ∈ V có trọng số dương w(v). Với mỗi phủ đỉnh V' ⊆ V, trọng số của phủ là w(V') = Σ_{v∈V'} w(v). Mục tiêu là tìm phủ đỉnh trọng số nhỏ nhất.

Không áp dụng được thuật toán cho phủ đỉnh không trọng số, cũng không dùng được lời giải ngẫu nhiên; cả hai có thể cho lời giải rất xa tối ưu. (Ví dụ của người tổng hợp: một cạnh (u, v) với w(u) = 1, w(v) = 1000; APPROX-VERTEX-COVER lấy cả hai, trọng số 1001, gấp 1001 lần tối ưu {u}.) Thay vào đó, ta tính một cận dưới cho trọng số phủ đỉnh nhỏ nhất bằng một quy hoạch tuyến tính, rồi "làm tròn" nghiệm của nó để có phủ đỉnh.

Gắn với mỗi đỉnh v ∈ V một biến x(v), và yêu cầu x(v) bằng 0 hoặc 1. Ta đưa v vào phủ khi và chỉ khi x(v) = 1. Ràng buộc "với mọi cạnh (u, v), ít nhất một trong u, v thuộc phủ" viết thành x(u) + x(v) ≥ 1. Cách nhìn này cho **quy hoạch nguyên 0-1** (0-1 integer program) sau để tìm phủ đỉnh trọng số nhỏ nhất:

```text
minimize    Σ_{v∈V} w(v) x(v)                                       (35.14)
subject to
            x(u) + x(v) ≥ 1        với mỗi (u, v) ∈ E                (35.15)
            x(v) ∈ {0, 1}          với mỗi v ∈ V                     (35.16)
```

Trong trường hợp riêng mọi trọng số w(v) bằng 1, đây chính là dạng tối ưu của bài phủ đỉnh NP-khó. Giả sử ta bỏ ràng buộc x(v) ∈ {0, 1} và thay bằng 0 ≤ x(v) ≤ 1. Ta được quy hoạch tuyến tính sau, gọi là **nới lỏng quy hoạch tuyến tính** (linear-programming relaxation):

```text
minimize    Σ_{v∈V} w(v) x(v)                                       (35.17)
subject to
            x(u) + x(v) ≥ 1        với mỗi (u, v) ∈ E                (35.18)
            x(v) ≤ 1               với mỗi v ∈ V                     (35.19)
            x(v) ≥ 0               với mỗi v ∈ V                     (35.20)
```

Mọi nghiệm chấp nhận được của quy hoạch nguyên 0-1 (35.14)–(35.16) cũng là nghiệm chấp nhận được của quy hoạch tuyến tính (35.17)–(35.20). Do đó giá trị tối ưu của quy hoạch tuyến tính là cận dưới cho giá trị tối ưu của quy hoạch nguyên 0-1, và vì vậy là cận dưới cho trọng số tối ưu trong bài phủ đỉnh trọng số nhỏ nhất.

Thủ tục sau dùng nghiệm của nới lỏng quy hoạch tuyến tính để dựng lời giải xấp xỉ:

```text
APPROX-MIN-WEIGHT-VC(G, w)
1  C = ∅
2  compute x̄, an optimal solution to the linear program in lines (35.17)–(35.20)
3  for each v ∈ V
4      if x̄(v) ≥ 1/2
5          C = C ∪ {v}
6  return C
```

Dòng 1 khởi tạo phủ rỗng. Dòng 2 lập quy hoạch tuyến tính (35.17)–(35.20) rồi giải nó. Nghiệm tối ưu gán cho mỗi đỉnh v một giá trị x̄(v) với 0 ≤ x̄(v) ≤ 1. Ta dùng giá trị này để quyết định đỉnh nào được thêm vào phủ C ở dòng 3–5: nếu x̄(v) ≥ 1/2 thì thêm v vào C, ngược lại thì không. Thực chất ta đang "làm tròn" mỗi biến phân số trong nghiệm quy hoạch tuyến tính về 0 hoặc 1 để được một nghiệm của quy hoạch nguyên 0-1 (35.14)–(35.16). Cuối cùng dòng 6 trả về C.

**Định lý 35.7.** APPROX-MIN-WEIGHT-VC là thuật toán 2-xấp xỉ thời gian đa thức cho bài phủ đỉnh trọng số nhỏ nhất.

*Chứng minh.* Vì có thuật toán thời gian đa thức giải quy hoạch tuyến tính ở dòng 2, và vòng for dòng 3–5 chạy thời gian đa thức, APPROX-MIN-WEIGHT-VC là thuật toán thời gian đa thức.

Giờ chứng minh tỷ số 2. Gọi C* là một lời giải tối ưu của bài phủ đỉnh trọng số nhỏ nhất, và z* là giá trị nghiệm tối ưu của quy hoạch tuyến tính (35.17)–(35.20). Vì phủ đỉnh tối ưu là một nghiệm chấp nhận được của quy hoạch tuyến tính, z* phải là cận dưới của w(C*):

```text
z* ≤ w(C*)                                                          (35.21)
```

Tiếp theo, ta khẳng định làm tròn các giá trị phân số x̄(v) cho một tập C là phủ đỉnh và thoả w(C) ≤ 2z*. C là phủ đỉnh: xét cạnh (u, v) ∈ E bất kỳ; theo ràng buộc (35.18), x(u) + x(v) ≥ 1, kéo theo ít nhất một trong x̄(u), x̄(v) không nhỏ hơn 1/2. Do đó ít nhất một trong u, v được đưa vào phủ, nên mọi cạnh đều được phủ.

Xét trọng số của phủ:

```text
z* = Σ_{v∈V} w(v) x̄(v)
   ≥ Σ_{v∈V : x̄(v) ≥ 1/2} w(v) x̄(v)
   ≥ Σ_{v∈V : x̄(v) ≥ 1/2} w(v) · 1/2
   = Σ_{v∈C} w(v) · 1/2
   = (1/2) Σ_{v∈C} w(v)
   = (1/2) w(C)                                                     (35.22)
```

(dòng thứ hai bỏ các số hạng không âm; dòng thứ ba thay x̄(v) ≥ 1/2). Kết hợp (35.21) và (35.22):

```text
w(C) ≤ 2z* ≤ 2w(C*)
```

nên APPROX-MIN-WEIGHT-VC là thuật toán 2-xấp xỉ. ∎

Ví dụ chạy tay (người tổng hợp):

- *Tam giác a, b, c, mọi trọng số bằng 1.* Quy hoạch tuyến tính: cực tiểu x_a + x_b + x_c với x_a + x_b ≥ 1, x_b + x_c ≥ 1, x_a + x_c ≥ 1. Cộng ba ràng buộc: 2(x_a + x_b + x_c) ≥ 3, nên z* ≥ 1,5, đạt tại x̄ = (1/2, 1/2, 1/2). Làm tròn lấy cả ba đỉnh: w(C) = 3. Tối ưu thật: w(C*) = 2 (hai đỉnh bất kỳ). Kiểm tra: 3 ≤ 2 · 1,5 = 3 ≤ 2 · 2 = 4. Cận w(C) ≤ 2z* đạt dấu bằng.
- *Đường đi a – b – c với w(a) = 1, w(b) = 3, w(c) = 1.* Cực tiểu x_a + 3x_b + x_c với x_a + x_b ≥ 1, x_b + x_c ≥ 1. Nghiệm tối ưu x̄ = (1, 0, 1), z* = 2 (lấy x_b = t thì chi phí 3t + 2(1 − t) = 2 + t, nhỏ nhất khi t = 0). Làm tròn được {a, c}, trọng số 2 — đúng tối ưu.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: "giải nới lỏng tuyến tính rồi làm tròn" là xương sống của các bộ giải quy hoạch nguyên thương mại (nhánh và cận dựa trên nới lỏng), và giá trị nới lỏng z* chính là con số "cận dưới" mà các bộ giải in ra để báo khoảng cách tối ưu (optimality gap). Thuật toán MAX-3-CNF ngẫu nhiên thì là điểm xuất phát của nhiều bộ giải MAX-SAT cục bộ (như WalkSAT): bắt đầu từ phép gán ngẫu nhiên rồi lật dần biến.

### 6. Bài toán tổng tập con (35.5 The subset-sum problem, trang 1128–1134)

Nhắc lại từ Mục 34.5.5: một thể hiện của bài tổng tập con là cặp (S, t), với S là tập {x₁, x₂, …, xₙ} các số nguyên dương và t là số nguyên dương. Bài quyết định hỏi có tập con nào của S có tổng **đúng bằng** t không. Bài này NP-đầy đủ.

Bài tối ưu tương ứng xuất hiện trong ứng dụng thực tế: tìm tập con của {x₁, …, xₙ} có tổng lớn nhất có thể nhưng không vượt t. Ví dụ, ta có một xe tải chở không quá t pound và n thùng hàng, thùng thứ i nặng xᵢ pound; ta muốn chất xe nặng nhất có thể mà không vượt giới hạn.

Mục này trình bày một thuật toán thời gian mũ tính giá trị tối ưu, rồi chỉ cách sửa nó thành một FPTAS (nhắc lại: FPTAS có thời gian đa thức theo 1/ε cũng như theo cỡ đầu vào).

#### Thuật toán chính xác thời gian mũ (An exponential-time exact algorithm)

Giả sử ta tính, với mỗi tập con S' của S, tổng các phần tử của S', rồi chọn trong các tập con có tổng không vượt t tập có tổng gần t nhất. Rõ ràng thuật toán này trả về lời giải tối ưu, nhưng có thể tốn thời gian mũ. Để cài đặt, có thể dùng thủ tục lặp: ở vòng i, tính tổng mọi tập con của {x₁, …, xᵢ}, dựa trên tổng mọi tập con của {x₁, …, xᵢ₋₁}. Khi làm vậy ta nhận ra: một khi một tập con S' có tổng vượt t thì không cần giữ nó nữa, vì không tập cha nào của S' có thể là lời giải tối ưu.

Thủ tục EXACT-SUBSET-SUM nhận tập S = {x₁, …, xₙ} và giá trị đích t. Nó tính lặp Lᵢ, danh sách các tổng của mọi tập con của {x₁, …, xᵢ} không vượt t, rồi trả về giá trị lớn nhất trong Lₙ.

Nếu L là danh sách số nguyên dương và x là số nguyên dương, L + x là danh sách thu được bằng cách cộng x vào mỗi phần tử của L. Ví dụ L = ⟨1, 2, 3, 5, 9⟩ thì L + 2 = ⟨3, 4, 5, 7, 11⟩. Ký hiệu này cũng dùng cho tập: S + x = {s + x : s ∈ S}.

Ta dùng thủ tục phụ MERGE-LISTS(L, L'), trả về danh sách đã sắp xếp là kết quả trộn hai danh sách đã sắp xếp L và L', bỏ giá trị trùng. Như thủ tục MERGE của sắp xếp trộn (Mục 2.3.1), MERGE-LISTS chạy O(|L| + |L'|). Sách bỏ qua pseudocode của MERGE-LISTS.

```text
EXACT-SUBSET-SUM(S, t)
1  n = |S|
2  L₀ = ⟨0⟩
3  for i = 1 to n
4      Lᵢ = MERGE-LISTS(Lᵢ₋₁, Lᵢ₋₁ + xᵢ)
5      remove from Lᵢ every element that is greater than t
6  return the largest element in Lₙ
```

Để thấy EXACT-SUBSET-SUM hoạt động thế nào, gọi Pᵢ là tập mọi giá trị thu được bằng cách chọn một tập con (có thể rỗng) của {x₁, …, xᵢ} và cộng các phần tử. Ví dụ S = {1, 4, 5}:

```text
P₁ = {0, 1}
P₂ = {0, 1, 4, 5}
P₃ = {0, 1, 4, 5, 6, 9, 10}
```

Từ đẳng thức

```text
Pᵢ = Pᵢ₋₁ ∪ (Pᵢ₋₁ + xᵢ)                                             (35.23)
```

(mỗi tập con của {x₁, …, xᵢ} hoặc không chứa xᵢ, hoặc chứa xᵢ), có thể chứng minh bằng quy nạp theo i (Exercise 35.5-1) rằng Lᵢ là danh sách đã sắp xếp chứa mọi phần tử của Pᵢ có giá trị không quá t. Vì độ dài Lᵢ có thể tới 2ⁱ, EXACT-SUBSET-SUM nói chung là thuật toán thời gian mũ, dù nó là thuật toán đa thức trong các trường hợp riêng t là đa thức theo |S| hoặc mọi số trong S bị chặn bởi một đa thức theo |S| (khi đó |Lᵢ| ≤ t + 1).

Chạy tay (người tổng hợp) với S = {1, 4, 5}, t = 8: L₁ = MERGE(⟨0⟩, ⟨1⟩) = ⟨0, 1⟩; L₂ = MERGE(⟨0, 1⟩, ⟨4, 5⟩) = ⟨0, 1, 4, 5⟩; L₃ = MERGE(⟨0, 1, 4, 5⟩, ⟨5, 6, 9, 10⟩) = ⟨0, 1, 4, 5, 6, 9, 10⟩, bỏ 9 và 10 (> 8) còn ⟨0, 1, 4, 5, 6⟩. Trả về 6 = 1 + 5.

#### Lược đồ xấp xỉ thời gian đa thức đầy đủ (A fully polynomial-time approximation scheme)

Ta có FPTAS cho bài tổng tập con bằng cách **tỉa** (trim) mỗi danh sách Lᵢ sau khi tạo. Ý tưởng: nếu hai giá trị trong L gần nhau, thì vì chỉ cần lời giải xấp xỉ, không cần giữ cả hai. Chính xác hơn, ta dùng **tham số tỉa** δ với 0 < δ < 1. **Tỉa** danh sách L theo δ nghĩa là bỏ khỏi L càng nhiều phần tử càng tốt, sao cho nếu L' là kết quả tỉa thì với mọi phần tử y đã bị bỏ, còn một phần tử z trong L' xấp xỉ y, tức là

```text
y / (1 + δ) ≤ z ≤ y                                                 (35.24)
```

Có thể coi z là "đại diện" của y trong danh sách mới L'. Mỗi phần tử bị bỏ y được đại diện bởi một phần tử còn lại z thoả (35.24). Ví dụ δ = 0,1 và

```text
L  = ⟨10, 11, 12, 15, 20, 21, 22, 23, 24, 29⟩
```

thì có thể tỉa L thành

```text
L' = ⟨10, 12, 15, 20, 23, 29⟩
```

trong đó giá trị bị bỏ 11 được 10 đại diện, 21 và 22 được 20 đại diện, 24 được 23 đại diện. Vì mọi phần tử của danh sách đã tỉa cũng là phần tử của danh sách gốc, phép tỉa có thể giảm mạnh số phần tử giữ lại mà vẫn giữ trong danh sách một giá trị đại diện gần (và nhỏ hơn chút) cho mỗi phần tử bị bỏ.

Thủ tục sau tỉa danh sách L = ⟨y₁, y₂, …, y_m⟩ trong thời gian Θ(m), với L và δ cho trước, giả định L đã sắp xếp tăng dần. Đầu ra là danh sách đã tỉa, đã sắp xếp.

```text
TRIM(L, δ)
1  let m be the length of L
2  L' = ⟨y₁⟩
3  last = y₁
4  for i = 2 to m
5      if yᵢ > last · (1 + δ)        // yᵢ ≥ last because L is sorted
6          append yᵢ onto the end of L'
7          last = yᵢ
8  return L'
```

Thủ tục quét các phần tử của L theo thứ tự tăng. Một số được nối vào danh sách trả về L' chỉ khi nó là phần tử đầu tiên của L hoặc không thể được đại diện bởi số gần nhất đã đưa vào L' (biến last).

Chạy tay TRIM trên ví dụ trên, δ = 0,1 (người tổng hợp):

| yᵢ | last trước | last · 1,1 | yᵢ > last · 1,1? | Hành động |
|---|---|---|---|---|
| 10 | — | — | — | phần tử đầu, giữ; last = 10 |
| 11 | 10 | 11 | không | bỏ (đại diện 10) |
| 12 | 10 | 11 | có | giữ; last = 12 |
| 15 | 12 | 13,2 | có | giữ; last = 15 |
| 20 | 15 | 16,5 | có | giữ; last = 20 |
| 21 | 20 | 22 | không | bỏ (đại diện 20) |
| 22 | 20 | 22 | không (bằng) | bỏ (đại diện 20) |
| 23 | 20 | 22 | có | giữ; last = 23 |
| 24 | 23 | 25,3 | không | bỏ (đại diện 23) |
| 29 | 23 | 25,3 | có | giữ; last = 29 |

Kết quả ⟨10, 12, 15, 20, 23, 29⟩, khớp sách.

Với TRIM, ta dựng lược đồ xấp xỉ như sau. Thủ tục nhận tập S = {x₁, …, xₙ} gồm n số nguyên (thứ tự tuỳ ý), số nguyên đích t, và "tham số xấp xỉ" ε với

```text
0 < ε < 1                                                           (35.25)
```

Nó trả về giá trị z* nằm trong hệ số 1 + ε của lời giải tối ưu.

```text
APPROX-SUBSET-SUM(S, t, ε)
1  n = |S|
2  L₀ = ⟨0⟩
3  for i = 1 to n
4      Lᵢ = MERGE-LISTS(Lᵢ₋₁, Lᵢ₋₁ + xᵢ)
5      Lᵢ = TRIM(Lᵢ, ε/2n)
6      remove from Lᵢ every element that is greater than t
7  let z* be the largest value in Lₙ
8  return z*
```

Dòng 2 khởi tạo L₀ là danh sách chỉ chứa 0. Vòng for dòng 3–6 tính Lᵢ là danh sách đã sắp xếp chứa một phiên bản đã tỉa hợp lý của Pᵢ, đã bỏ mọi phần tử lớn hơn t. Vì Lᵢ được tạo từ Lᵢ₋₁, phải bảo đảm việc tỉa lặp lại không gây sai số tích luỹ quá lớn; đó là lý do tham số tỉa là ε/2n chứ không phải ε. Lát nữa ta sẽ thấy APPROX-SUBSET-SUM trả về xấp xỉ đúng nếu tồn tại.

##### Ví dụ chạy tay (của sách)

Thể hiện S = ⟨104, 102, 201, 101⟩ với t = 308 và ε = 0,40. Tham số tỉa δ = ε/2n = 0,40/8 = ε/8 = 0,05 (vì n = 4). APPROX-SUBSET-SUM tính các giá trị sau ở các dòng tương ứng:

| Vòng | Dòng 4 (trộn) | Dòng 5 (tỉa, δ = 0,05) | Dòng 6 (bỏ > 308) |
|---|---|---|---|
| L₀ (dòng 2) | ⟨0⟩ | | |
| i = 1, x₁ = 104 | ⟨0, 104⟩ | ⟨0, 104⟩ | ⟨0, 104⟩ |
| i = 2, x₂ = 102 | ⟨0, 102, 104, 206⟩ | ⟨0, 102, 206⟩ | ⟨0, 102, 206⟩ |
| i = 3, x₃ = 201 | ⟨0, 102, 201, 206, 303, 407⟩ | ⟨0, 102, 201, 303, 407⟩ | ⟨0, 102, 201, 303⟩ |
| i = 4, x₄ = 101 | ⟨0, 101, 102, 201, 203, 302, 303, 404⟩ | ⟨0, 101, 201, 302, 404⟩ | ⟨0, 101, 201, 302⟩ |

Giải thích các phép tỉa (người tổng hợp): ở i = 2, 104 bị bỏ vì 104 ≤ 102 · 1,05 = 107,1 (đại diện 102); ở i = 3, 206 bị bỏ vì 206 ≤ 201 · 1,05 = 211,05; ở i = 4, 102 bị bỏ vì ≤ 101 · 1,05 = 106,05, 203 bị bỏ vì ≤ 211,05, 303 bị bỏ vì ≤ 302 · 1,05 = 317,1.

Thuật toán trả về z* = 302, nằm thoải mái trong ε = 40% của đáp án tối ưu 307 = 104 + 102 + 101; thực ra nằm trong 2% (307/302 ≈ 1,0166). Nhận xét (người tổng hợp): tổng 307 = 206 + 101 bị mất vì 206 đã bị tỉa ở vòng 3 (đại diện bằng 201), và 201 + 101 = 302 là đại diện của nó.

**Định lý 35.8.** APPROX-SUBSET-SUM là lược đồ xấp xỉ thời gian đa thức đầy đủ cho bài tổng tập con.

*Chứng minh.* Các thao tác tỉa Lᵢ ở dòng 5 và bỏ phần tử lớn hơn t ở dòng 6 giữ nguyên tính chất: mọi phần tử của Lᵢ cũng là phần tử của Pᵢ. Do đó giá trị z* trả về ở dòng 8 thật sự là tổng của một tập con của S. Gọi y* ∈ Pₙ là lời giải tối ưu của bài tổng tập con. Từ dòng 6, z* ≤ y*. Theo (35.1), cần chứng minh y*/z* ≤ 1 + ε. Ta cũng phải chứng minh thời gian chạy đa thức theo cả 1/ε và cỡ đầu vào.

*Tỷ số xấp xỉ.* Như Exercise 35.5-2 yêu cầu chứng minh, với mọi phần tử y ∈ Pᵢ có y ≤ t, tồn tại z ∈ Lᵢ sao cho

```text
y / (1 + ε/2n)ⁱ ≤ z ≤ y                                             (35.26)
```

Bất đẳng thức (35.26) đúng với y* ∈ Pₙ, nên tồn tại z ∈ Lₙ sao cho

```text
y* / (1 + ε/2n)ⁿ ≤ z ≤ y*
```

và do đó

```text
y* / z ≤ (1 + ε/2n)ⁿ                                                (35.27)
```

Vì có z ∈ Lₙ thoả (35.27), bất đẳng thức cũng đúng cho z*, giá trị lớn nhất trong Lₙ:

```text
y* / z* ≤ (1 + ε/2n)ⁿ                                               (35.28)
```

Giờ chứng minh y*/z* ≤ 1 + ε bằng cách chứng minh (1 + ε/2n)ⁿ ≤ 1 + ε. Theo (3.14), lim_{n→∞} (1 + ε/2n)ⁿ = e^(ε/2). Exercise 35.5-3 yêu cầu chứng minh

```text
d/dn (1 + ε/2n)ⁿ > 0                                                (35.29)
```

Vậy hàm (1 + ε/2n)ⁿ tăng theo n khi tiến tới giới hạn e^(ε/2), và

```text
(1 + ε/2n)ⁿ ≤ e^(ε/2)
            ≤ 1 + ε/2 + (ε/2)²      (theo bất đẳng thức (3.13))
            ≤ 1 + ε                 (theo bất đẳng thức (35.25))     (35.30)
```

(Bất đẳng thức (3.13) là eˣ ≤ 1 + x + x² khi |x| ≤ 1; bước cuối dùng (ε/2)² = ε²/4 ≤ ε/2 vì ε < 1.) Kết hợp (35.28) và (35.30) hoàn tất phân tích tỷ số xấp xỉ.

Kiểm tra số (người tổng hợp): ε = 0,4, n = 4: (1,05)⁴ ≈ 1,2155 ≤ e^0,2 ≈ 1,2214 ≤ 1 + 0,2 + 0,04 = 1,24 ≤ 1,4.

*Thời gian chạy.* Để chứng minh APPROX-SUBSET-SUM là FPTAS, ta chặn độ dài Lᵢ. Sau khi tỉa, hai phần tử liên tiếp z và z' của Lᵢ phải thoả z'/z > 1 + ε/2n, tức là chúng cách nhau ít nhất hệ số 1 + ε/2n. Vì vậy mỗi danh sách chứa giá trị 0, có thể chứa giá trị 1, và không quá ⌊log_{1+ε/2n} t⌋ giá trị khác (các giá trị khác ≥ 1, mỗi giá trị lớn hơn giá trị trước ít nhất hệ số 1 + ε/2n, và không vượt t). Số phần tử của mỗi Lᵢ không quá

```text
log_{1+ε/2n} t + 2 = ln t / ln(1 + ε/2n) + 2
                   ≤ 2n(1 + ε/2n) ln t / ε + 2     (theo bất đẳng thức (3.17))
                   < 3n ln t / ε + 2               (theo bất đẳng thức (35.25))
```

(Bất đẳng thức (3.17) cho x/(1 + x) ≤ ln(1 + x) với x > −1, nên 1/ln(1 + x) ≤ (1 + x)/x; với x = ε/2n được (1 + ε/2n) · 2n/ε. Bước cuối: 2n(1 + ε/2n) = 2n + ε < 3n vì ε < 1 ≤ n.) Cận này đa thức theo cỡ đầu vào — gồm số bit lg t để biểu diễn t cộng số bit để biểu diễn tập S, mà số bit này lại đa thức theo n — và theo 1/ε. Vì thời gian chạy của APPROX-SUBSET-SUM đa thức theo độ dài các Lᵢ (mỗi vòng trộn và tỉa tuyến tính theo độ dài), APPROX-SUBSET-SUM là FPTAS. ∎

Ví dụ số (người tổng hợp): n = 100, t = 10⁹ (ln t ≈ 20,7), ε = 0,01: mỗi danh sách có không quá 3 · 100 · 20,72 / 0,01 + 2 ≈ 621.700 phần tử; tổng công việc khoảng n lần con số đó, cỡ 6 · 10⁷ phép toán — trong khi thuật toán chính xác có thể phải giữ tới min(2¹⁰⁰, 10⁹) giá trị mỗi danh sách.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: kỹ thuật "làm tròn và tỉa các trạng thái gần nhau của quy hoạch động" là cách chuẩn để biến một quy hoạch động giả đa thức (pseudo-polynomial, phụ thuộc giá trị số) thành FPTAS; nó được dùng cho bài cái túi 0-1, lập lịch một máy với hạn chót, và các bài phân bổ ngân sách. Trong thực tế kỹ thuật, ý tưởng tương tự xuất hiện khi lượng tử hoá các giá trị liên tục để giữ số trạng thái nhỏ.

## Bài tập và bài toán cuối chương

### Bài tập Mục 35.1 (trang 1111)

- **35.1-1:** Cho ví dụ một đồ thị mà APPROX-VERTEX-COVER luôn cho lời giải không tối ưu. *Người tổng hợp:* đồ thị chỉ có một cạnh (u, v): thuật toán luôn lấy cả hai đỉnh (cỡ 2), tối ưu là 1. Tổng quát hơn, sao K₁,ₙ: cạnh nào được chọn cũng chứa tâm và một lá, thuật toán trả 2 đỉnh, tối ưu 1 (chỉ tâm). Bất kỳ đồ thị nào có phủ tối ưu nhỏ hơn 2 lần ghép cặp cực đại nhỏ nhất của nó đều được.
- **35.1-2:** Chứng minh tập cạnh được chọn ở dòng 4 của APPROX-VERTEX-COVER là một ghép cặp cực đại theo bao hàm của G. *Người tổng hợp:* (i) là ghép cặp: khi chọn (u, v), dòng 6 xoá mọi cạnh dính u hoặc v, nên các cạnh chọn sau không chung đỉnh với (u, v). (ii) cực đại: mỗi cạnh e của G bị xoá khỏi E' tại một thời điểm, và chỉ bị xoá khi nó dính vào một đầu mút của một cạnh vừa chọn (hoặc chính nó được chọn); vậy mọi cạnh của G đều chung đỉnh với một cạnh của A (hoặc thuộc A), không thể thêm cạnh nào vào A mà vẫn là ghép cặp.
- **35.1-3 ★:** Giáo sư Bündchen đề xuất heuristic: lặp lại chọn một đỉnh bậc cao nhất, bỏ mọi cạnh dính vào nó. Cho ví dụ chứng tỏ heuristic không có tỷ số 2. (Gợi ý: thử đồ thị hai phía, bên trái các đỉnh cùng bậc, bên phải bậc khác nhau.) *Lời giải của người tổng hợp:* bên trái L gồm n đỉnh ℓ₁, …, ℓₙ. Với mỗi i = 2, 3, …, n, thêm nhóm Rᵢ gồm ⌊n/i⌋ đỉnh bên phải; mỗi đỉnh của Rᵢ nối với i đỉnh trái khác nhau, các đỉnh trong cùng nhóm nối với các tập trái rời nhau. Mỗi đỉnh trái có bậc ≤ n − 1 (nhiều nhất một láng giềng mỗi nhóm), đỉnh của Rₙ có bậc n. L là một phủ đỉnh cỡ n (mọi cạnh nối trái với phải). Heuristic lần lượt lấy đỉnh của Rₙ, rồi Rₙ₋₁, … (sau khi xoá các nhóm bậc lớn, bậc mỗi đỉnh trái giảm theo, luôn không vượt bậc của nhóm phải kế tiếp), cuối cùng lấy hết mọi đỉnh phải: tổng Σᵢ₌₂ⁿ ⌊n/i⌋ ≈ n(ln n − 1) đỉnh — tỷ số Θ(lg n). Người tổng hợp đã mô phỏng: n = 6 cho 8 đỉnh (tỷ số 1,33), n = 12 cho 23, n = 20 cho 46 đỉnh so với tối ưu ≤ 20 (tỷ số ≥ 2,3 > 2), bất kể cách phá hoà.
- **35.1-4:** Cho thuật toán tham lam hiệu quả tìm phủ đỉnh tối ưu cho cây trong thời gian tuyến tính. *Người tổng hợp:* luôn tồn tại phủ tối ưu không chứa lá nào (thay lá bằng cha của nó không làm tệ hơn). Vậy: lặp lại lấy một lá ℓ, đưa cha p của ℓ vào phủ, xoá p cùng mọi cạnh dính p (và các đỉnh cô lập). Cài đặt bằng DFS hậu thứ tự: một đỉnh được đưa vào phủ khi có ít nhất một con chưa được phủ (con không thuộc phủ). Thời gian O(V).
- **35.1-5:** Từ chứng minh Định lý 34.12, phủ đỉnh và clique bù nhau: phủ đỉnh tối ưu là phần bù của clique lớn nhất trong đồ thị bù. Quan hệ này có kéo theo thuật toán xấp xỉ tỷ số hằng cho clique không? *Người tổng hợp:* không. Tỷ số không bảo toàn qua phép lấy phần bù. Nếu clique lớn nhất có k đỉnh thì phủ tối ưu của đồ thị bù có n − k đỉnh; phủ 2-xấp xỉ có thể có tới 2(n − k) đỉnh, phần bù của nó là clique cỡ n − 2(n − k) = 2k − n, có thể ≤ 0 khi k ≤ n/2. Ví dụ k = n/2: tối ưu n/2 nhưng ta có thể chỉ nhận được clique rỗng — không có tỷ số hằng nào. (Thực tế, theo hiểu biết của người tổng hợp, clique không xấp xỉ được trong hệ số n^(1−ε) trừ khi P = NP.)

### Bài tập Mục 35.2 (trang 1116–1117)

- **35.2-1:** Cho đồ thị vô hướng đầy đủ có ít nhất 3 đỉnh với hàm chi phí thoả bất đẳng thức tam giác. Chứng minh c(u, v) ≥ 0 với mọi u, v. *Người tổng hợp:* lấy đỉnh thứ ba w. Bất đẳng thức tam giác cho c(u, w) ≤ c(u, v) + c(v, w) và c(v, w) ≤ c(v, u) + c(u, w). Cộng hai vế: c(u, w) + c(v, w) ≤ 2c(u, v) + c(u, w) + c(v, w), nên c(u, v) ≥ 0 (đồ thị vô hướng nên c(u, v) = c(v, u)). Bài chỉ có ý nghĩa khi bỏ giả định "chi phí không âm" của đầu mục (xem Lưu ý).
- **35.2-2:** Chỉ cách biến đổi trong đa thức một thể hiện TSP thành thể hiện có hàm chi phí thoả bất đẳng thức tam giác, hai thể hiện có cùng tập hành trình tối ưu. Giải thích vì sao điều này không mâu thuẫn Định lý 35.3 (giả sử P ≠ NP). *Người tổng hợp:* đặt M = max c(u, v), c'(u, v) = c(u, v) + M. Mọi hành trình có đúng |V| cạnh nên chi phí mới bằng chi phí cũ cộng |V|M — cùng thứ tự, cùng tập tối ưu. Bất đẳng thức tam giác: c'(u, w) ≤ 2M ≤ c'(u, v) + c'(v, w) vì mỗi c' ≥ M. Không mâu thuẫn vì phép cộng hằng chỉ bảo toàn chênh lệch, không bảo toàn TỶ SỐ: một hành trình 2-xấp xỉ cho c' (chi phí ≤ 2(OPT + |V|M)) có thể có chi phí gốc ≤ 2·OPT + |V|M, tệ hơn tối ưu gốc nhiều lần tuỳ ý.
- **35.2-3:** Heuristic điểm gần nhất (closest-point heuristic): bắt đầu với chu trình tầm thường một đỉnh; mỗi bước tìm đỉnh u chưa thuộc chu trình mà khoảng cách tới chu trình nhỏ nhất, gọi v là đỉnh trên chu trình gần u nhất, chèn u ngay sau v; lặp tới khi mọi đỉnh thuộc chu trình. Chứng minh hành trình không quá 2 lần tối ưu (khi có bất đẳng thức tam giác). *Người tổng hợp:* các cặp (v, u) được chọn đúng là các cạnh mà thuật toán Prim thêm vào, nên tổng các c(v, u) bằng trọng số một cây khung nhỏ nhất c(T). Chèn u giữa v và v' (đỉnh sau v) thay cạnh (v, v') bằng (v, u), (u, v'): chi phí tăng c(v, u) + c(u, v') − c(v, v') ≤ 2c(v, u) theo bất đẳng thức tam giác (c(u, v') ≤ c(u, v) + c(v, v')). Cộng lại: hành trình ≤ 2c(T) ≤ 2c(H*).
- **35.2-4:** Bài TSP nút cổ chai (bottleneck TSP): tìm chu trình Hamilton làm cực tiểu chi phí cạnh đắt nhất. Với bất đẳng thức tam giác, chứng minh có thuật toán đa thức tỷ số 3. (Gợi ý: chứng minh đệ quy rằng có thể thăm mọi nút của một cây khung nút cổ chai (Problem 23-3) đúng một lần bằng đường đi đầy đủ có bỏ nút, nhưng không bỏ quá hai nút trung gian liên tiếp; chứng minh cạnh đắt nhất của cây khung nút cổ chai không đắt hơn cạnh đắt nhất của chu trình Hamilton nút cổ chai.) *Người tổng hợp:* gọi B là trọng số cạnh lớn nhất trong cây khung nút cổ chai (cây khung nhỏ nhất là một cây như vậy). Bỏ một cạnh của chu trình tối ưu được cây khung, nên B ≤ cạnh lớn nhất của tối ưu. Theo gợi ý (phép "lập phương" của cây: mọi cây có chu trình Hamilton trong T³), mỗi cạnh của hành trình thay cho một đường đi ≤ 3 cạnh của cây, nên theo bất đẳng thức tam giác có giá ≤ 3B ≤ 3 · tối ưu.
- **35.2-5:** Các đỉnh là điểm trên mặt phẳng, chi phí là khoảng cách Euclid. Chứng minh hành trình tối ưu không bao giờ tự cắt. *Người tổng hợp:* nếu hai cạnh (a, b) và (c, d) của hành trình cắt nhau tại điểm p, thay chúng bằng (a, c) và (b, d) (đảo đoạn giữa — phép 2-opt) vẫn là một hành trình; theo bất đẳng thức tam giác |ac| ≤ |ap| + |pc| và |bd| ≤ |bp| + |pd|, tổng ≤ |ab| + |cd|, và bất đẳng thức chặt khi các điểm không thẳng hàng. Vậy hành trình tự cắt không thể tối ưu (trường hợp suy biến thẳng hàng xử lý riêng).

### Bài tập Mục 35.3 (trang 1122)

- **35.3-1:** Coi mỗi từ sau là một tập chữ cái: {arid, dash, drain, heard, lost, nose, shun, slate, snare, thread}. GREEDY-SET-COVER cho phủ nào nếu hoà thì chọn từ đứng trước trong từ điển? *Lời giải của người tổng hợp* (X = {a, d, e, h, i, l, n, o, r, s, t, u}, 12 chữ):
  - Vòng 1: thread = {t, h, r, e, a, d} phủ 6 — lớn nhất. U còn {i, l, n, o, s, u}.
  - Vòng 2: lost {l, o, s} = 3, nose {o, s, n} = 3, shun {s, u, n} = 3, slate {s, l} = 2, … Hoà giữa lost, nose, shun, nên chọn **lost** (đứng trước trong từ điển). U còn {i, n, u}.
  - Vòng 3: drain {i, n} = 2, shun {u, n} = 2, arid {i} = 1, … Hoà giữa drain và shun, nên chọn **drain**. U còn {u}.
  - Vòng 4: chỉ shun chứa u, nên chọn **shun**.
  - Phủ: {thread, lost, drain, shun}, 4 tập.
- **35.3-2:** Chứng minh dạng quyết định của phủ tập hợp là NP-đầy đủ bằng cách quy dẫn từ phủ đỉnh. *Người tổng hợp:* thuộc NP (kiểm tra ≤ k tập có hợp bằng X). Quy dẫn: từ (G, k) đặt X = E, mỗi đỉnh v cho tập S_v = {các cạnh dính vào v}, giữ nguyên k. G có phủ đỉnh cỡ ≤ k khi và chỉ khi có ≤ k tập S_v phủ hết E.
- **35.3-3:** Cài đặt GREEDY-SET-COVER chạy O(Σ_{S∈F} |S|). *Người tổng hợp:* duy trì cho mỗi tập số phần tử chưa phủ cnt[S]; xếp các tập vào mảng xô (bucket) theo cnt; với mỗi phần tử x lưu danh sách các tập chứa x (dựng trong O(Σ|S|)). Mỗi vòng lấy tập ở xô cao nhất không rỗng (con trỏ xô chỉ giảm dần, tổng dịch chuyển O(max|S|)); với mỗi phần tử mới phủ x, giảm cnt của mọi tập chứa x và dời tập sang xô thấp hơn (O(1) với danh sách liên kết đôi). Mỗi cặp (x, S) được xử lý một lần.
- **35.3-4:** Chứng minh dạng yếu của Định lý 35.4 là hiển nhiên: |C| ≤ |C*| · max{|S| : S ∈ F}. *Người tổng hợp:* mỗi tập tham lam phủ ít nhất một phần tử mới nên |C| ≤ |X|; và |X| ≤ Σ_{S∈C*} |S| ≤ |C*| · max |S|.
- **35.3-5:** Cho thủ tục BAD-SET-COVER-INSTANCE(n) trả về thể hiện n phần tử mà, tuỳ cách phá hoà ở dòng 4, GREEDY-SET-COVER có thể trả về số lời giải khác nhau mũ theo n. *Người tổng hợp:* chia n phần tử thành n/3 bộ ba {aᵢ, bᵢ, cᵢ}; với mỗi bộ ba cho ba tập {aᵢ, bᵢ}, {bᵢ, cᵢ}, {aᵢ, cᵢ}. Mọi tập ban đầu phủ 2 phần tử mới; ở mỗi bộ ba, tham lam chọn một trong 3 tập, sau đó phần tử còn lại được phủ bởi một trong 2 tập (mỗi tập phủ 1 phần tử mới). Mỗi bộ ba có 3 · 2 = 6 cặp (thứ tự) cho 3 tập hợp lời giải khác nhau (bất kỳ hai trong ba tập), tổng 3^(n/3) phủ khác nhau — mũ theo n.

### Bài tập Mục 35.4 (trang 1127–1128)

- **35.4-1:** Chứng minh ngay cả khi cho phép mệnh đề chứa cả một biến và phủ định của nó, gán ngẫu nhiên vẫn là thuật toán ngẫu nhiên 8/7-xấp xỉ. *Người tổng hợp:* mệnh đề chứa x và ¬x luôn đúng, E[Yᵢ] = 1 ≥ 7/8; các mệnh đề khác vẫn 7/8. Vậy E[Y] ≥ 7m/8 và tỷ số ≤ 8/7.
- **35.4-2:** MAX-CNF giống MAX-3-CNF nhưng mệnh đề có số literal tuỳ ý. Cho thuật toán ngẫu nhiên 2-xấp xỉ. *Người tổng hợp:* cùng thuật toán gán ngẫu nhiên. Mệnh đề có k ≥ 1 literal (về các biến khác nhau) sai với xác suất 2⁻ᵏ ≤ 1/2; nếu chứa x và ¬x thì luôn đúng. Vậy E[Y] ≥ m/2 ≥ OPT/2.
- **35.4-3:** MAX-CUT: đồ thị vô hướng không trọng số, trọng số của lát cắt (S, V − S) là số cạnh băng qua; tìm lát cắt nặng nhất. Đặt mỗi đỉnh vào S với xác suất 1/2 độc lập. Chứng minh đây là thuật toán ngẫu nhiên 2-xấp xỉ. *Người tổng hợp:* cạnh (u, v) băng qua khi u, v khác phía: xác suất 1/2. Tuyến tính kỳ vọng: E[trọng số] = |E|/2 ≥ OPT/2.
- **35.4-4:** Chứng minh các ràng buộc (35.19) là thừa: bỏ chúng thì mọi nghiệm tối ưu của quy hoạch còn lại vẫn thoả x(v) ≤ 1. *Người tổng hợp:* nếu nghiệm tối ưu có x(v) > 1, giảm x(v) xuống 1 vẫn thoả mọi ràng buộc x(u) + x(v) ≥ 1 (vì x(v) = 1 đã đủ) và x(v) ≥ 0, đồng thời giảm mục tiêu một lượng w(v)(x(v) − 1) > 0 (w(v) > 0) — mâu thuẫn với tính tối ưu.

### Bài tập Mục 35.5 (trang 1133–1134)

- **35.5-1:** Chứng minh (35.23); rồi chứng minh sau dòng 5 của EXACT-SUBSET-SUM, Lᵢ là danh sách đã sắp xếp chứa mọi phần tử của Pᵢ không vượt t. *Người tổng hợp:* tập con của {x₁, …, xᵢ} hoặc không chứa xᵢ (tổng thuộc Pᵢ₋₁) hoặc chứa xᵢ (tổng thuộc Pᵢ₋₁ + xᵢ), và ngược lại, nên (35.23) đúng. Quy nạp: L₀ = ⟨0⟩ = P₀. Giả sử Lᵢ₋₁ = {y ∈ Pᵢ₋₁ : y ≤ t} đã sắp xếp. Một y ∈ Pᵢ có y ≤ t: nếu y ∈ Pᵢ₋₁ thì y ∈ Lᵢ₋₁; nếu y = y' + xᵢ với y' ∈ Pᵢ₋₁ thì y' ≤ y ≤ t nên y' ∈ Lᵢ₋₁ và y ∈ Lᵢ₋₁ + xᵢ. MERGE-LISTS giữ thứ tự và mọi phần tử, dòng 5 bỏ các giá trị > t; không có giá trị nào ngoài Pᵢ được thêm.
- **35.5-2:** Chứng minh (35.26) bằng quy nạp theo i. *Người tổng hợp:* đặt δ = ε/2n. i = 0: P₀ = L₀ = {0}. Bước quy nạp: lấy y ∈ Pᵢ, y ≤ t. Trường hợp y ∈ Pᵢ₋₁: theo giả thiết có z' ∈ Lᵢ₋₁ với y/(1+δ)ⁱ⁻¹ ≤ z' ≤ y. Trường hợp y = y' + xᵢ: có z'' ∈ Lᵢ₋₁ với y'/(1+δ)ⁱ⁻¹ ≤ z'' ≤ y', đặt z' = z'' + xᵢ ∈ Lᵢ₋₁ + xᵢ; khi đó z' ≤ y và z' ≥ y'/(1+δ)ⁱ⁻¹ + xᵢ ≥ (y' + xᵢ)/(1+δ)ⁱ⁻¹ = y/(1+δ)ⁱ⁻¹. Trong cả hai trường hợp z' có mặt trong danh sách trộn ở dòng 4. Sau TRIM, z' hoặc còn, hoặc có z với z'/(1+δ) ≤ z ≤ z'. Vậy y/(1+δ)ⁱ ≤ z ≤ y ≤ t, nên z không bị dòng 6 bỏ.
- **35.5-3:** Chứng minh (35.29). *Người tổng hợp:* đặt a = ε/2 > 0, f(n) = n ln(1 + a/n). f'(n) = ln(1 + a/n) − (a/n)/(1 + a/n). Với x = a/n > 0, ln(1 + x) > x/(1 + x) (bất đẳng thức (3.17) chặt khi x ≠ 0), nên f'(n) > 0, và (1 + a/n)ⁿ = e^(f(n)) có đạo hàm e^(f(n)) f'(n) > 0.
- **35.5-4:** Sửa lược đồ thế nào để xấp xỉ tốt giá trị nhỏ nhất KHÔNG NHỎ HƠN t là tổng của một tập con? *Người tổng hợp:* tỉa "từ trên xuống": duyệt danh sách tăng dần nhưng giữ đại diện lớn hơn — mỗi giá trị bị bỏ y có đại diện z với y ≤ z ≤ (1 + δ)y (quét từ phần tử lớn nhất xuống). Không bỏ các giá trị > t ở mỗi bước (chúng có thể là lời giải), nhưng có thể bỏ mọi giá trị lớn hơn giá trị nhỏ nhất đã ≥ t hiện có. Cuối cùng trả về giá trị nhỏ nhất ≥ t trong Lₙ. Phân tích đối xứng cho tỷ số (1 + ε/2n)ⁿ ≤ 1 + ε, và độ dài danh sách ≤ log_{1+δ}(Σxᵢ) + 2, vẫn đa thức. (Cách khác: dùng phần bù — tổng nhỏ nhất ≥ t bằng Σxᵢ trừ tổng lớn nhất ≤ Σxᵢ − t — nhưng phép trừ không bảo toàn tỷ số, nên cách trực tiếp tốt hơn.)
- **35.5-5:** Sửa APPROX-SUBSET-SUM để trả về cả tập con có tổng z*. *Người tổng hợp:* mỗi phần tử của Lᵢ lưu thêm con trỏ tới phần tử của Lᵢ₋₁ sinh ra nó và một bit "có cộng xᵢ hay không". Khi trộn, phần tử từ Lᵢ₋₁ có bit 0, phần tử từ Lᵢ₋₁ + xᵢ có bit 1; TRIM và dòng 6 chỉ xoá phần tử, không đổi con trỏ của phần tử còn lại. Cuối cùng lần ngược từ z* trong Lₙ về L₀, thu các xᵢ có bit 1. Thêm O(n) thời gian và bộ nhớ O(tổng độ dài các danh sách).

### Problem 35-1: Xếp thùng (Bin packing)

Cho n đồ vật, kích thước sᵢ thoả 0 < sᵢ < 1. Cần xếp mọi đồ vật vào ít thùng kích thước 1 nhất; mỗi thùng chứa được tập đồ vật bất kỳ có tổng kích thước không vượt 1.

- **(a)** Chứng minh bài xác định số thùng tối thiểu là NP-khó. (Gợi ý: quy dẫn từ tổng tập con.) *Người tổng hợp:* quy dẫn từ bài phân hoạch (partition, trường hợp riêng của tổng tập con với t = Σxᵢ/2, NP-đầy đủ): cho x₁, …, xₙ với tổng 2T, đặt sᵢ = xᵢ/T (nếu có xᵢ ≥ T thì xử lý trực tiếp). Các đồ vật xếp được vào 2 thùng khi và chỉ khi tập số chia được thành hai phần bằng nhau.
- Heuristic **vừa-đầu-tiên** (first-fit) lấy lần lượt từng đồ vật và đặt vào thùng đầu tiên còn chứa được nó. Đặt S = Σᵢ₌₁ⁿ sᵢ.
- **(b)** Lập luận số thùng tối ưu ít nhất ⌈S⌉. *Người tổng hợp:* b thùng chứa tổng ≤ b, nên b ≥ S, và b nguyên.
- **(c)** Lập luận first-fit để lại nhiều nhất một thùng đầy chưa tới một nửa. *Người tổng hợp:* giả sử hai thùng i < j đều ≤ 1/2. Mọi đồ vật trong thùng j có kích thước ≤ 1/2; khi đồ vật đầu tiên của thùng j được xếp, thùng i chứa ≤ 1/2 (chỉ có thể tăng về sau), nên còn chỗ cho nó — first-fit lẽ ra phải đặt nó vào thùng i (hoặc thùng sớm hơn). Mâu thuẫn.
- **(d)** Chứng minh first-fit dùng không quá ⌈2S⌉ thùng. *Người tổng hợp:* nếu dùng b thùng, ít nhất b − 1 thùng đầy hơn một nửa, nên S > (b − 1)/2, tức b < 2S + 1, b ≤ ⌈2S⌉. (Trường hợp b = 1 hiển nhiên.)
- **(e)** Chứng minh tỷ số 2 cho first-fit. *Người tổng hợp:* ⌈2S⌉ ≤ 2⌈S⌉ ≤ 2 · OPT.
- **(f)** Cho cài đặt hiệu quả và phân tích. *Người tổng hợp:* cài đặt ngây thơ O(n²) (quét các thùng). Hiệu quả: cây phân đoạn (hoặc cây giải đấu) trên tối đa n thùng lưu dung lượng còn lại lớn nhất của mỗi đoạn; tìm thùng trái nhất có chỗ ≥ sᵢ bằng cách đi xuống từ gốc, cập nhật lên gốc — O(lg n) mỗi đồ vật, tổng O(n lg n).

Ví dụ (người tổng hợp): kích thước 0,6; 0,5; 0,4; 0,3; 0,2. First-fit: 0,6 vào thùng 1; 0,5 không vừa thùng 1 (tổng sẽ là 1,1) nên mở thùng 2; 0,4 vào thùng 1 (1,0); 0,3 vào thùng 2 (0,8); 0,2 vào thùng 2 (1,0). Hai thùng, S = 2,0, tối ưu ⌈2⌉ = 2.

### Problem 35-2: Xấp xỉ kích thước clique lớn nhất (Approximating the size of a maximum clique)

Cho đồ thị vô hướng G = (V, E). Với k ≥ 1, định nghĩa G^(k) là đồ thị vô hướng (V^(k), E^(k)), trong đó V^(k) là tập mọi bộ k có thứ tự các đỉnh của V, và (v₁, …, v_k) kề (w₁, …, w_k) khi và chỉ khi với mọi i = 1, …, k, hoặc vᵢ kề wᵢ trong G, hoặc vᵢ = wᵢ (và hai bộ khác nhau).

- **(a)** Chứng minh kích thước clique lớn nhất của G^(k) bằng luỹ thừa bậc k của kích thước clique lớn nhất của G. *Người tổng hợp:* nếu K là clique cỡ ω trong G, mọi bộ trong Kᵏ (ωᵏ bộ) đôi một kề nhau (mỗi toạ độ bằng nhau hoặc kề). Ngược lại, nếu Q là clique trong G^(k), hình chiếu Qᵢ lên toạ độ i là một clique trong G (hai giá trị khác nhau ở toạ độ i phải kề), nên |Qᵢ| ≤ ω, và Q ⊆ Q₁ × … × Q_k cho |Q| ≤ ωᵏ.
- **(b)** Lập luận: nếu có thuật toán xấp xỉ với tỷ số hằng cho clique lớn nhất thì có PTAS. *Người tổng hợp:* giả sử thuật toán A có tỷ số ρ. Cho ε, chọn k = ⌈ln ρ / ln(1 + ε)⌉ (hằng số khi ε cố định). Chạy A trên G^(k) (có nᵏ đỉnh — đa thức), được clique Q cỡ ≥ ωᵏ/ρ. Hình chiếu lớn nhất Qᵢ là clique của G với |Qᵢ| ≥ |Q|^(1/k) ≥ ω/ρ^(1/k) ≥ ω/(1 + ε). Đây là PTAS. (Theo hiểu biết của người tổng hợp, kết quả PCP về sau cho thấy clique thậm chí không có tỷ số hằng trừ khi P = NP.)

### Problem 35-3: Phủ tập hợp có trọng số (Weighted set-covering problem)

Tổng quát hoá phủ tập hợp: mỗi tập Sᵢ của F có trọng số wᵢ, trọng số của phủ C là Σ_{Sᵢ∈C} wᵢ; tìm phủ trọng số nhỏ nhất (Mục 35.3 là trường hợp wᵢ = 1). Tổng quát hoá heuristic tham lam một cách tự nhiên và chứng minh tỷ số H(d), d là cỡ lớn nhất của các tập.

*Người tổng hợp:* ở dòng 4, chọn S làm cực tiểu tỷ số w(S)/|S ∩ U| (giá mỗi phần tử mới). Phân bổ chi phí: khi chọn Sᵢ, mỗi phần tử x được phủ lần đầu nhận c_x = wᵢ / |Sᵢ − (S₁ ∪ … ∪ Sᵢ₋₁)|. Tổng mọi c_x bằng w(C). Với S bất kỳ còn uᵢ₋₁ phần tử chưa phủ trước vòng i, lựa chọn tham lam cho w(Sᵢ)/|mới| ≤ w(S)/uᵢ₋₁, nên mỗi phần tử của S phủ ở vòng i nhận ≤ w(S)/uᵢ₋₁; lặp lại phép tính co rút như (35.12) được Σ_{x∈S} c_x ≤ w(S) H(|S|). Cộng trên S ∈ C*: w(C) ≤ Σ_{S∈C*} w(S) H(|S|) ≤ H(d) w(C*).

### Problem 35-4: Ghép cặp lớn nhất (Maximum matching)

Nhắc lại: ghép cặp của đồ thị vô hướng là tập cạnh không hai cạnh nào chung đỉnh. Mục 26.3 tìm ghép cặp lớn nhất trong đồ thị hai phía; bài này xét đồ thị tổng quát.

- **(a)** Ghép cặp cực đại theo bao hàm (maximal matching) là ghép cặp không phải tập con thực sự của ghép cặp khác. Cho đồ thị và ghép cặp cực đại theo bao hàm không phải lớn nhất. (Gợi ý: 4 đỉnh là đủ.) *Người tổng hợp:* đường đi a – b – c – d, M = {(b, c)} cực đại theo bao hàm, nhưng {(a, b), (c, d)} có 2 cạnh.
- **(b)** Cho thuật toán tham lam O(E) tìm ghép cặp cực đại theo bao hàm. *Người tổng hợp:* duyệt các cạnh một lượt; thêm (u, v) vào M nếu cả u và v chưa bị ghép (đánh dấu bằng mảng boolean).
- Bài này tập trung vào thuật toán xấp xỉ thời gian đa thức cho ghép cặp lớn nhất. Thuật toán chính xác nhanh nhất đã biết cho ghép cặp lớn nhất chạy thời gian siêu tuyến tính (nhưng đa thức), còn thuật toán xấp xỉ ở đây chạy tuyến tính: ta chứng minh thuật toán tham lam ở (b) là 2-xấp xỉ.
- **(c)** Chứng minh kích thước ghép cặp lớn nhất là cận dưới của kích thước mọi phủ đỉnh. *Người tổng hợp:* mỗi cạnh ghép cần một đỉnh phủ riêng (các cạnh ghép không chung đỉnh).
- **(d)** Cho M là ghép cặp cực đại theo bao hàm, T = {v ∈ V : có cạnh của M dính vào v}. Có thể nói gì về đồ thị con cảm sinh bởi các đỉnh không thuộc T? *Người tổng hợp:* nó không có cạnh nào (tập độc lập) — nếu có cạnh giữa hai đỉnh chưa ghép thì thêm được vào M.
- **(e)** Suy ra từ (d) rằng 2|M| là kích thước của một phủ đỉnh. *Người tổng hợp:* mọi cạnh có ít nhất một đầu trong T, nên T là phủ đỉnh, |T| = 2|M|.
- **(f)** Dùng (c) và (e), chứng minh thuật toán tham lam là 2-xấp xỉ cho ghép cặp lớn nhất. *Người tổng hợp:* |M*| ≤ |T| = 2|M| nên |M*|/|M| ≤ 2.

### Problem 35-5: Lập lịch máy song song (Parallel machine scheduling)

Trong **bài toán lập lịch máy song song**, có n công việc J₁, …, Jₙ, công việc J_k có thời gian xử lý không âm p_k, và m máy giống nhau M₁, …, M_m. Mọi công việc chạy được trên mọi máy. Một **lịch** (schedule) chỉ định, với mỗi công việc J_k, máy nó chạy và khoảng thời gian nó chạy. Mỗi J_k phải chạy trên một máy Mᵢ trong p_k đơn vị thời gian liên tục, và trong khoảng đó không công việc nào khác chạy trên Mᵢ. Gọi C_k là **thời điểm hoàn thành** (completion time) của J_k. Với một lịch, **độ dài lịch** (makespan) là C_max = max_{1≤j≤n} C_j. Mục tiêu: tìm lịch có độ dài nhỏ nhất.

Ví dụ của sách: hai máy M₁, M₂ và bốn công việc với p₁ = 2, p₂ = 12, p₃ = 4, p₄ = 5. Một lịch khả dĩ: trên M₁ chạy J₁ rồi J₂; trên M₂ chạy J₄ rồi J₃. Khi đó C₁ = 2, C₂ = 14, C₃ = 9, C₄ = 5, C_max = 14. Một lịch tối ưu chạy J₂ trên M₁, và J₁, J₃, J₄ trên M₂: C₁ = 2, C₂ = 12, C₃ = 6, C₄ = 11, C_max = 12. (Kiểm tra của người tổng hợp: thứ tự trên M₂ là J₁, J₃, J₄: 2, 2 + 4 = 6, 6 + 5 = 11. Tối ưu vì C*_max ≥ max p_k = 12.)

Ký hiệu C*_max là độ dài lịch tối ưu.

- **(a)** Chứng minh C*_max ≥ max_{1≤k≤n} p_k. (*Người tổng hợp:* công việc dài nhất phải chạy liên tục trên một máy.)
- **(b)** Chứng minh C*_max ≥ (1/m) Σ_{1≤k≤n} p_k. (*Người tổng hợp:* tổng công việc Σp_k chia cho m máy; máy bận nhất bận ít nhất trung bình.)
- Dùng thuật toán tham lam: hễ có máy rảnh, giao cho nó một công việc bất kỳ chưa được giao.
- **(c)** Viết pseudocode và cho thời gian chạy. *Người tổng hợp:*

  ```text
  GREEDY-SCHEDULE(p, n, m)
  1  Q = min-priority queue of the m machines, all with key 0
  2  for k = 1 to n
  3      i = EXTRACT-MIN(Q)          // machine that becomes idle first
  4      start[k] = key of i ; machine[k] = i
  5      INSERT(Q, i, start[k] + p[k])
  6  return start, machine
  ```

  Thời gian O(n lg m) với đống nhị phân (O(nm) nếu quét tuyến tính).
- **(d)** Chứng minh với lịch tham lam, C_max ≤ (1/m) Σ p_k + max p_k; suy ra thuật toán là 2-xấp xỉ đa thức. *Người tổng hợp:* gọi J_ℓ là công việc kết thúc cuối cùng, bắt đầu ở thời điểm s. Trước s, mọi máy đều bận liên tục (nếu có máy rảnh sớm hơn, J_ℓ đã được giao sớm hơn), nên m · s ≤ Σ_{k≠ℓ} p_k ≤ Σ p_k. Vậy C_max = s + p_ℓ ≤ (1/m)Σp_k + max p_k ≤ C*_max + C*_max theo (a), (b).

### Problem 35-6: Xấp xỉ cây khung lớn nhất (Approximating a maximum spanning tree)

Cho G = (V, E) vô hướng, trọng số cạnh w(u, v) đôi một khác nhau. Với mỗi đỉnh v, max(v) = cạnh nặng nhất dính vào v. S_G = {max(v) : v ∈ V} là tập các cạnh nặng nhất ở mỗi đỉnh; T_G là cây khung lớn nhất (tổng trọng số lớn nhất) của G. Với E' ⊆ E, w(E') = Σ_{(u,v)∈E'} w(u, v).

- **(a)** Cho ví dụ đồ thị ≥ 4 đỉnh có S_G = T_G. *Người tổng hợp:* đường đi a – b – c – d với w(a, b) = 1, w(b, c) = 2, w(c, d) = 3: max(a) = (a, b), max(b) = (b, c), max(c) = max(d) = (c, d); S_G là cả ba cạnh = cây duy nhất.
- **(b)** Cho ví dụ ≥ 4 đỉnh có S_G ≠ T_G. *Người tổng hợp:* đỉnh a, b, c, d với cạnh (a, b) = 10, (c, d) = 9, (b, c) = 1, (a, d) = 2: S_G = {(a, b), (c, d)} (chỉ 2 cạnh, chưa liên thông), T_G = {(a, b), (c, d), (a, d)}.
- **(c)** Chứng minh S_G ⊆ T_G với mọi G. *Người tổng hợp:* max(v) là cạnh nặng nhất băng qua lát cắt ({v}, V − {v}); theo tính chất lát cắt (bản cho cây khung lớn nhất, trọng số khác nhau), cạnh nặng nhất băng qua một lát cắt thuộc cây khung lớn nhất duy nhất. Hoặc trực tiếp: nếu max(v) = (v, u) ∉ T_G, thêm nó vào T_G tạo chu trình qua v, chu trình chứa cạnh khác (v, x) nhẹ hơn; đổi hai cạnh được cây nặng hơn — mâu thuẫn.
- **(d)** Chứng minh w(T_G) ≥ w(S_G)/2 với mọi G. *Người tổng hợp:* như đề viết, điều này suy ngay từ (c) khi trọng số không âm (w(T_G) ≥ w(S_G) ≥ w(S_G)/2). Chiều có ích cho (e) là w(S_G) ≥ w(T_G)/2 (xem Lưu ý): treo T_G tại một gốc, mỗi cạnh của cây gán cho đỉnh con v của nó; w(cạnh) ≤ w(max(v)). Mỗi cạnh của S_G là max của nhiều nhất hai đỉnh (hai đầu mút), nên w(T_G) ≤ Σ_v w(max(v)) ≤ 2w(S_G) (với trọng số không âm).
- **(e)** Cho thuật toán O(V + E) tính một 2-xấp xỉ của cây khung lớn nhất. *Người tổng hợp:* tính max(v) cho mọi v trong một lượt duyệt cạnh, được S_G (một rừng). Bổ sung các cạnh bất kỳ để nối các thành phần của rừng thành cây khung (duyệt BFS/DFS trên đồ thị co các thành phần, O(V + E)). Cây kết quả nặng ≥ w(S_G) ≥ w(T_G)/2 khi trọng số không âm.

### Problem 35-7: Thuật toán xấp xỉ cho bài cái túi 0-1 (An approximation algorithm for the 0-1 knapsack problem)

Nhắc lại bài cái túi ở Mục 16.2: n đồ vật, đồ vật i có giá trị vᵢ đô-la và nặng wᵢ pound; túi chứa tối đa W pound. Giả định thêm mỗi wᵢ ≤ W và các đồ vật được đánh số theo giá trị giảm dần: v₁ ≥ v₂ ≥ … ≥ vₙ.

Bài cái túi 0-1: tìm tập đồ vật tổng trọng lượng ≤ W và tổng giá trị lớn nhất. Bài cái túi phân số: được lấy một phần xᵢ (0 ≤ xᵢ ≤ 1) của đồ vật i, đóng góp xᵢwᵢ trọng lượng và xᵢvᵢ giá trị. Mục tiêu: thuật toán 2-xấp xỉ đa thức cho bài 0-1.

Xét các thể hiện hạn chế: từ thể hiện I, tạo Iⱼ (j = 1, …, n) bằng cách bỏ các đồ vật 1, …, j − 1 và bắt buộc lời giải chứa đồ vật j (toàn bộ đồ vật j, ở cả bài phân số lẫn 0-1). I₁ không bỏ đồ vật nào. Với Iⱼ, gọi Pⱼ là lời giải tối ưu của bài 0-1 và Qⱼ là lời giải tối ưu của bài phân số.

- **(a)** Lập luận lời giải tối ưu của I (bài 0-1) là một trong {P₁, …, Pₙ}. *Người tổng hợp:* gọi j là chỉ số nhỏ nhất trong lời giải tối ưu O (O khác rỗng vì mọi wᵢ ≤ W). O chỉ dùng đồ vật ≥ j và chứa j, nên khả thi cho Iⱼ, v(Pⱼ) ≥ v(O); Pⱼ khả thi cho I nên v(Pⱼ) ≤ v(O).
- **(b)** Chứng minh có thể tìm Qⱼ bằng cách lấy đồ vật j rồi tham lam: mỗi bước lấy nhiều nhất có thể đồ vật chưa chọn trong {j + 1, …, n} có giá trị trên đơn vị trọng lượng vᵢ/wᵢ lớn nhất. *Người tổng hợp:* sau khi cố định j, phần còn lại là bài cái túi phân số với sức chứa W − wⱼ, mà tham lam theo tỷ số là tối ưu (Mục 16.2, lập luận đổi chỗ).
- **(c)** Chứng minh luôn dựng được Qⱼ có nhiều nhất một đồ vật lấy một phần. *Người tổng hợp:* lời giải tham lam ở (b) lấy trọn các đồ vật cho tới khi túi không đủ chỗ, chỉ đồ vật cuối cùng được lấy một phần.
- **(d)** Từ Qⱼ, dựng Rⱼ bằng cách bỏ mọi đồ vật lấy một phần. Ký hiệu v(S) là tổng giá trị của lời giải S. Chứng minh v(Rⱼ) ≥ v(Qⱼ)/2 ≥ v(Pⱼ)/2. *Người tổng hợp:* đồ vật lẻ f có chỉ số > j nên v_f ≤ vⱼ ≤ v(Rⱼ) (Rⱼ chứa đồ vật j). Vậy v(Qⱼ) ≤ v(Rⱼ) + x_f v_f ≤ 2v(Rⱼ). Và v(Qⱼ) ≥ v(Pⱼ) vì bài phân số là nới lỏng của bài 0-1.
- **(e)** Cho thuật toán đa thức trả về lời giải giá trị lớn nhất trong {R₁, …, Rₙ}, chứng minh nó là 2-xấp xỉ. *Người tổng hợp:* sắp các đồ vật theo vᵢ/wᵢ một lần (O(n lg n)); với mỗi j, chạy tham lam trên các đồ vật > j với sức chứa W − wⱼ, bỏ đồ vật lẻ — O(n) mỗi j, tổng O(n²). Trả về Rⱼ tốt nhất. Theo (a) và (d): max v(Rⱼ) ≥ v(R_{j*}) ≥ v(P_{j*})/2 = OPT/2, với j* là chỉ số trong (a).

Ví dụ (người tổng hợp): W = 10; đồ vật 1: v = 10, w = 10; đồ vật 2: v = 9, w = 5; đồ vật 3: v = 8, w = 5. I₁: phải lấy đồ vật 1, túi đầy, R₁ = {1}, giá trị 10. I₂: lấy 2, còn 5 chỗ, lấy trọn 3, R₂ = {2, 3}, giá trị 17. I₃: lấy 3, R₃ = {3}, giá trị 8. Thuật toán trả 17, đúng tối ưu.

### Ghi chú chương (Chapter notes, trang 1138–1140)

- Phương pháp không nhất thiết cho lời giải chính xác đã có từ hàng nghìn năm (ví dụ các phương pháp xấp xỉ giá trị π), nhưng khái niệm thuật toán xấp xỉ mới hơn nhiều. **Hochbaum** ghi công **Garey, Graham và Ullman** và **Johnson** đã hình thức hoá khái niệm thuật toán xấp xỉ thời gian đa thức. Thuật toán như vậy đầu tiên thường được ghi cho **Graham** (theo hiểu biết của người tổng hợp, đó là phân tích lập lịch danh sách năm 1966 — chính thuật toán của Problem 35-5).
- Từ đó, hàng nghìn thuật toán xấp xỉ đã được thiết kế. Các sách chuyên về thuật toán xấp xỉ: **Ausiello và cộng sự**, **Hochbaum**, **Vazirani**; các khảo sát của **Shmoys** và **Klein và Young**. **Garey và Johnson**, **Papadimitriou và Steiglitz** cũng có phần đáng kể. **Lawler, Lenstra, Rinnooy Kan và Shmoys** trình bày rộng về thuật toán xấp xỉ cho TSP.
- **Papadimitriou và Steiglitz** ghi APPROX-VERTEX-COVER cho **F. Gavril** và **M. Yannakakis**. Phủ đỉnh được nghiên cứu rất nhiều (Hochbaum liệt kê 16 thuật toán xấp xỉ khác nhau), nhưng mọi tỷ số xấp xỉ đều ít nhất 2 − o(1).
- APPROX-TSP-TOUR xuất hiện trong bài báo của **Rosenkrantz, Stearns và Lewis**. **Christofides** cải tiến và cho thuật toán 3/2-xấp xỉ cho TSP có bất đẳng thức tam giác. **Arora** và **Mitchell** chứng minh nếu các điểm nằm trên mặt phẳng Euclid thì có PTAS. Định lý 35.3 là của **Sahni và Gonzalez**.
- Phân tích heuristic tham lam cho phủ tập hợp mô phỏng theo chứng minh của **Chvátal** cho một kết quả tổng quát hơn; kết quả cơ bản như trình bày ở đây là của **Johnson** và **Lovász**.
- APPROX-SUBSET-SUM và phân tích của nó dựa lỏng lẻo trên các thuật toán xấp xỉ cho bài cái túi và tổng tập con của **Ibarra và Kim**.
- Problem 35-7 là phiên bản tổ hợp của một kết quả tổng quát hơn về xấp xỉ các quy hoạch nguyên kiểu cái túi của **Bienstock và McClosky**.
- Thuật toán ngẫu nhiên cho MAX-3-CNF ẩn trong công trình của **Johnson**. Thuật toán phủ đỉnh có trọng số là của **Hochbaum**.
- Mục 35.4 chỉ chạm tới sức mạnh của ngẫu nhiên hoá và quy hoạch tuyến tính trong thiết kế thuật toán xấp xỉ. Kết hợp hai ý tưởng này cho kỹ thuật **làm tròn ngẫu nhiên** (randomized rounding): biểu diễn bài toán thành quy hoạch tuyến tính nguyên, giải nới lỏng tuyến tính, và hiểu các biến trong nghiệm như xác suất để dẫn đường cho lời giải bài gốc. Kỹ thuật này được **Raghavan và Thompson** dùng đầu tiên và có nhiều ứng dụng sau đó (khảo sát của **Motwani, Naor và Raghavan**). Các ý tưởng đáng chú ý khác gần đây: **phương pháp gốc–đối ngẫu** (primal-dual method; khảo sát của **Goemans và Williamson**), tìm lát cắt thưa dùng cho thuật toán chia để trị, và dùng **quy hoạch nửa xác định** (semidefinite programming).
- Như ghi chú Chương 34 đã nói, các kết quả gần đây về **chứng minh kiểm tra được bằng xác suất** (probabilistically checkable proofs, PCP) đã cho cận dưới về khả năng xấp xỉ của nhiều bài toán, kể cả một số bài trong chương này. Chương sách của **Arora và Lund** mô tả tốt quan hệ giữa PCP và độ khó xấp xỉ.

## Luận điểm cốt lõi

### Mệnh đề

Với nhiều bài toán tối ưu NP-khó, có thể thiết kế thuật toán thời gian đa thức với bảo đảm chứng minh được về chất lượng — chi phí lời giải nằm trong hệ số ρ(n) của tối ưu — bằng cách so sánh lời giải với một cận tính được của giá trị tối ưu; nhưng mức xấp xỉ đạt được phụ thuộc mạnh vào cấu trúc bài toán: từ tuỳ ý gần (FPTAS cho tổng tập con), hằng số (2 cho phủ đỉnh, TSP có bất đẳng thức tam giác, phủ đỉnh có trọng số; 8/7 cho MAX-3-CNF), lôgarit (phủ tập hợp), tới không thể xấp xỉ trong bất kỳ hằng số nào trừ khi P = NP (TSP tổng quát).

### Giả định

- Mọi lời giải khả dĩ có chi phí dương (để tỷ số C/C* và C*/C xác định).
- "Hiệu quả" nghĩa là thời gian đa thức theo cỡ đầu vào (số bit), như ở Chương 34; với lược đồ xấp xỉ, đa thức theo n khi ε cố định (PTAS) hoặc theo cả n và 1/ε (FPTAS).
- Tỷ số được đo trong trường hợp xấu nhất trên mọi đầu vào; với thuật toán ngẫu nhiên, đo trên chi phí kỳ vọng (vẫn với mọi đầu vào).
- Các kết quả không xấp xỉ được (Định lý 35.3) dựa trên giả định P ≠ NP.
- Mục 35.2.1 giả định bất đẳng thức tam giác; Mục 35.4 giả định có thuật toán đa thức giải quy hoạch tuyến tính (Chương 29) và mệnh đề 3-CNF có đúng 3 literal khác biến; Mục 35.5 giả định các số nguyên dương và MERGE-LISTS tuyến tính.

### Cơ chế

1. **Tìm cận của tối ưu tính được trong đa thức:** ghép cặp cực đại theo bao hàm (phủ đỉnh), cây khung nhỏ nhất (TSP), giá trị quy hoạch tuyến tính nới lỏng (phủ đỉnh có trọng số), tổng số mệnh đề m (MAX-3-CNF), Σp_k/m và max p_k (lập lịch), ⌈S⌉ (xếp thùng).
2. **Dựng lời giải từ cấu trúc của cận và chặn chi phí theo cận:** lấy cả hai đầu mút mỗi cạnh ghép (gấp 2); đi vòng quanh cây rồi đi tắt nhờ bất đẳng thức tam giác (gấp 2); làm tròn ở ngưỡng 1/2 (gấp 2).
3. **Phân bổ chi phí (charging) cho phân tích tham lam:** chia chi phí mỗi bước cho các phần tử được phục vụ lần đầu, rồi chặn tổng chi phí mà mỗi phần của lời giải tối ưu phải gánh (H(|S|) cho phủ tập hợp).
4. **Ngẫu nhiên hoá + tuyến tính của kỳ vọng:** mỗi mệnh đề đúng với xác suất 7/8, cộng các biến chỉ thị.
5. **Tỉa không gian trạng thái của thuật toán chính xác:** giữ một đại diện cho mỗi nhóm giá trị trong hệ số 1 + δ; chọn δ = ε/2n để sai số tích luỹ qua n bước ≤ 1 + ε và số trạng thái chỉ là O((n ln t)/ε).
6. **Quy dẫn tạo khoảng cách để chứng minh không xấp xỉ được:** biến thể hiện "có" thành giá trị ≤ k, thể hiện "không" thành giá trị > ρk.

### Bằng chứng và ví dụ tác giả đưa ra

- Hình 35.1: đồ thị 7 đỉnh 8 cạnh; APPROX-VERTEX-COVER chọn các cạnh (b, c), (e, f), (d, g), được 6 đỉnh; tối ưu {b, d, e} có 3 đỉnh.
- Chứng minh Định lý 35.1 bằng (35.2) |C*| ≥ |A| và (35.3) |C| = 2|A|.
- Hình 35.2: 8 điểm trên lưới, cây khung nhỏ nhất gốc a, đường đi đầy đủ a, b, c, b, h, b, a, d, e, f, e, g, e, d, a, thứ tự trước a, b, c, h, d, e, f, g; hành trình ≈ 19,074 so với tối ưu ≈ 14,715 (ngắn hơn khoảng 23%).
- Chứng minh Định lý 35.2 qua chuỗi (35.4)–(35.7).
- Định lý 35.3 với chi phí 1 và ρ|V| + 1; tách bạch |V| với ≥ ρ|V| + |V|.
- Hình 35.3: 12 điểm, 6 tập; tối ưu {S₃, S₄, S₅}; tham lam S₁, S₄, S₅ rồi S₃ hoặc S₆.
- Chứng minh Định lý 35.4 qua (35.9)–(35.12) và chuỗi co rút; Hệ quả 35.5 (ln |X| + 1); phủ đỉnh bậc ≤ 3 với H(3) = 11/6.
- Định lý 35.6: E[Y] = 7m/8; Định lý 35.7: (35.21), (35.22).
- Ví dụ P₁, P₂, P₃ với S = {1, 4, 5}; ví dụ TRIM với δ = 0,1; ví dụ APPROX-SUBSET-SUM với ⟨104, 102, 201, 101⟩, t = 308, ε = 0,4 cho 302 so với 307.
- Ví dụ lập lịch 2 máy, 4 việc trong Problem 35-5 (C_max = 14 so với 12).

### Kết luận và hàm ý cho người lập trình

- Khi gặp một bài NP-khó, hỏi trước: bài của mình có cấu trúc gì (bất đẳng thức tam giác? kích thước tập nhỏ? số liệu bị chặn?) — chính cấu trúc đó quyết định có xấp xỉ tốt được hay không. Bỏ một điều kiện tưởng nhỏ (bất đẳng thức tam giác) có thể biến bài "xấp xỉ được trong hệ số 2" thành "không xấp xỉ được".
- Luôn tính kèm một cận dưới (hoặc trên) của tối ưu: nó vừa cho bảo đảm lý thuyết, vừa cho con số "cách tối ưu không quá x%" trên từng đầu vào cụ thể — thường tốt hơn nhiều so với bảo đảm xấu nhất (ví dụ TSP: 1,30 thay vì 2; tổng tập con: 1,6% thay vì 40%).
- Tham lam đơn giản thường đủ tốt và có bảo đảm (phủ tập hợp, lập lịch danh sách, first-fit, ghép cặp cực đại); hãy học cách chứng minh bảo đảm của nó bằng phân bổ chi phí.
- Quy hoạch tuyến tính nới lỏng + làm tròn là công cụ đa năng: viết bài toán thành quy hoạch nguyên trước, rồi nghĩ cách làm tròn.
- Quy hoạch động có trạng thái là giá trị số (tổng tập con, cái túi) có thể biến thành FPTAS bằng cách tỉa/làm tròn trạng thái — chọn sai số mỗi bước nhỏ cỡ ε/n để sai số tích luỹ còn ε.
- Bảo đảm xấp xỉ là trường hợp xấu nhất; thuật toán có bảo đảm đẹp chưa chắc là thuật toán thực tế tốt nhất (sách tự thừa nhận APPROX-TSP-TOUR không phải lựa chọn thực tế tốt nhất).

### Trong ngôn ngữ khoa học máy tính

Tỷ số xấp xỉ: max(C/C*, C*/C) ≤ ρ(n). APPROX-VERTEX-COVER: O(V + E), |C| = 2|A| ≤ 2|C*|, A là ghép cặp cực đại theo bao hàm. APPROX-TSP-TOUR: Θ(V²), c(H) ≤ c(W) = 2c(T) ≤ 2c(H*) dưới bất đẳng thức tam giác; TSP tổng quát: không có ρ-xấp xỉ đa thức với mọi hằng ρ ≥ 1 trừ khi P = NP. GREEDY-SET-COVER: O(|X||F| min(|X|, |F|)) (cài đặt tốt O(Σ|S|)), |C| ≤ H(max|S|) · |C*| ≤ (ln|X| + 1)|C*|. MAX-3-CNF ngẫu nhiên: E[Y] = 7m/8, tỷ số 8/7. APPROX-MIN-WEIGHT-VC: w(C) ≤ 2z* ≤ 2w(C*). APPROX-SUBSET-SUM: FPTAS, y*/z* ≤ (1 + ε/2n)ⁿ ≤ 1 + ε, |Lᵢ| < 3n ln t / ε + 2, thời gian O(n² ln t / ε). Phân cấp lớp: FPTAS ⊂ PTAS ⊂ APX (tỷ số hằng) ⊂ lôgarit ⊂ không xấp xỉ được (thuật ngữ APX theo hiểu biết của người tổng hợp).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| approximation algorithm | thuật toán xấp xỉ | thuật toán đa thức trả lời giải gần tối ưu có bảo đảm |
| near-optimal solution | lời giải gần tối ưu | chi phí nằm trong một hệ số của tối ưu |
| optimization problem | bài toán tối ưu | tìm lời giải chi phí nhỏ nhất hoặc lớn nhất |
| maximization / minimization problem | bài toán cực đại / cực tiểu | tối ưu là lớn nhất / nhỏ nhất |
| approximation ratio ρ(n) | tỷ số xấp xỉ ρ(n) | max(C/C*, C*/C) ≤ ρ(n) |
| ρ(n)-approximation algorithm | thuật toán ρ(n)-xấp xỉ | thuật toán đạt tỷ số ρ(n) |
| approximation scheme | lược đồ xấp xỉ | nhận thêm ε, là (1 + ε)-xấp xỉ |
| polynomial-time approximation scheme (PTAS) | lược đồ xấp xỉ thời gian đa thức | đa thức theo n với mỗi ε cố định |
| fully polynomial-time approximation scheme (FPTAS) | lược đồ xấp xỉ thời gian đa thức đầy đủ | đa thức theo cả n và 1/ε |
| vertex cover / optimal vertex cover | phủ đỉnh / phủ đỉnh tối ưu | tập đỉnh chạm mọi cạnh / nhỏ nhất |
| matching | ghép cặp | tập cạnh đôi một không chung đỉnh |
| maximal matching | ghép cặp cực đại theo bao hàm | không thêm được cạnh nào |
| maximum matching | ghép cặp lớn nhất | nhiều cạnh nhất |
| lower bound | cận dưới | đại lượng chắc chắn ≤ giá trị tối ưu |
| traveling-salesman problem (TSP) | bài toán người bán hàng | chu trình Hamilton chi phí nhỏ nhất |
| tour / hamiltonian cycle | hành trình / chu trình Hamilton | chu trình qua mỗi đỉnh đúng một lần |
| triangle inequality | bất đẳng thức tam giác | c(u, w) ≤ c(u, v) + c(v, w) |
| euclidean distance | khoảng cách Euclid | khoảng cách thẳng trên mặt phẳng |
| minimum spanning tree | cây khung nhỏ nhất | cây nối mọi đỉnh tổng trọng số nhỏ nhất |
| preorder tree walk | duyệt cây theo thứ tự trước | liệt kê đỉnh khi gặp lần đầu, trước các con |
| full walk | đường đi đầy đủ | liệt kê đỉnh cả khi quay lại; đi mỗi cạnh cây hai lần |
| gap (technique) | (kỹ thuật) khoảng cách | quy dẫn tách giá trị ≤ k và > ρk để chứng minh khó xấp xỉ |
| set-covering problem / set cover | bài toán phủ tập hợp / phủ tập hợp | ít tập nhất có hợp bằng X |
| covers | phủ | tập S phủ các phần tử của nó |
| greedy heuristic | heuristic tham lam | mỗi bước chọn cái tốt nhất trước mắt |
| harmonic number H(d) | số điều hoà H(d) | 1 + 1/2 + … + 1/d |
| charging / cost allocation c_x | phân bổ chi phí c_x | chia chi phí mỗi bước cho phần tử phủ lần đầu |
| telescoping sum | tổng co rút | Σ(aᵢ₋₁ − aᵢ) = a₀ − a_k |
| randomized approximation algorithm | thuật toán xấp xỉ ngẫu nhiên | tỷ số tính trên chi phí kỳ vọng |
| MAX-3-CNF satisfiability | bài MAX-3-CNF | gán biến làm đúng nhiều mệnh đề 3-CNF nhất |
| clause / literal | mệnh đề / literal | tuyển các literal / biến hoặc phủ định của biến |
| indicator random variable | biến ngẫu nhiên chỉ thị | 1 nếu sự kiện xảy ra, 0 nếu không |
| linearity of expectation | tính tuyến tính của kỳ vọng | E[ΣYᵢ] = ΣE[Yᵢ] |
| minimum-weight vertex cover | phủ đỉnh trọng số nhỏ nhất | phủ đỉnh tổng trọng số nhỏ nhất |
| 0-1 integer program | quy hoạch nguyên 0-1 | quy hoạch có biến chỉ nhận 0 hoặc 1 |
| linear-programming relaxation | nới lỏng quy hoạch tuyến tính | thay x ∈ {0, 1} bằng 0 ≤ x ≤ 1 |
| rounding / randomized rounding | làm tròn / làm tròn ngẫu nhiên | đưa nghiệm phân số về nguyên (theo ngưỡng / theo xác suất) |
| subset-sum problem | bài toán tổng tập con | tổng tập con lớn nhất không vượt t |
| target value t | giá trị đích t | giới hạn trên của tổng |
| MERGE-LISTS | MERGE-LISTS | trộn hai danh sách đã sắp xếp, bỏ trùng |
| trimming / trimming parameter δ | tỉa / tham số tỉa δ | bỏ giá trị có đại diện trong hệ số 1 + δ |
| approximation parameter ε | tham số xấp xỉ ε | sai số tương đối cho phép |
| bin packing / first-fit | xếp thùng / vừa-đầu-tiên | xếp đồ vào ít thùng nhất / đặt vào thùng đầu tiên còn chỗ |
| clique | clique | tập đỉnh đôi một kề nhau |
| weighted set cover | phủ tập hợp có trọng số | mỗi tập có trọng số, cực tiểu tổng trọng số |
| parallel-machine scheduling / makespan | lập lịch máy song song / độ dài lịch | thời điểm công việc cuối cùng hoàn thành |
| completion time | thời điểm hoàn thành | lúc một công việc xong |
| maximum spanning tree | cây khung lớn nhất | cây khung tổng trọng số lớn nhất |
| 0-1 / fractional knapsack | cái túi 0-1 / cái túi phân số | lấy trọn hoặc không / được lấy một phần |
| primal-dual method | phương pháp gốc–đối ngẫu | thiết kế thuật toán xấp xỉ qua cặp quy hoạch đối ngẫu |
| semidefinite programming | quy hoạch nửa xác định | tối ưu trên ma trận nửa xác định dương |
| probabilistically checkable proofs (PCP) | chứng minh kiểm tra được bằng xác suất | nền tảng cho các kết quả khó xấp xỉ |

## Câu nói đáng nhớ

> "Many problems of practical significance are NP-complete, yet they are too important to abandon merely because we don't know how to find an optimal solution in polynomial time." — mở đầu Chương 35
>
> *Dịch: Nhiều bài toán có ý nghĩa thực tế là NP-đầy đủ, nhưng chúng quá quan trọng để bỏ đi chỉ vì ta không biết cách tìm lời giải tối ưu trong thời gian đa thức.*

> "In practice, near-optimality is often good enough." — mở đầu Chương 35
>
> *Dịch: Trong thực tế, gần tối ưu thường là đủ tốt.*

> "That is, we can trade computation time for the quality of the approximation." — mở đầu Chương 35
>
> *Dịch: Tức là ta có thể đổi thời gian tính toán lấy chất lượng xấp xỉ.*

> "Instead of requiring that we know the exact size of an optimal vertex cover, we rely on a lower bound on the size." — Mục 35.1
>
> *Dịch: Thay vì đòi hỏi biết chính xác kích thước phủ đỉnh tối ưu, ta dựa vào một cận dưới của kích thước đó.*

> "By relating the size of the solution returned to the lower bound, we obtain our approximation ratio." — Mục 35.1
>
> *Dịch: Bằng cách liên hệ kích thước lời giải trả về với cận dưới, ta có được tỷ số xấp xỉ.*

> "In spite of the nice approximation ratio provided by Theorem 35.2, APPROX-TSP-TOUR is usually not the best practical choice for this problem." — Mục 35.2.1
>
> *Dịch: Dù Định lý 35.2 cho tỷ số xấp xỉ đẹp, APPROX-TSP-TOUR thường không phải lựa chọn thực tế tốt nhất cho bài này.*

> "Because the logarithm function grows rather slowly, however, this approximation algorithm may nonetheless give useful results." — Mục 35.3
>
> *Dịch: Tuy nhiên, vì hàm lôgarit tăng khá chậm, thuật toán xấp xỉ này vẫn có thể cho kết quả hữu ích.*

> "In other words, a randomized approximation algorithm is like a deterministic approximation algorithm, except that the approximation ratio is for an expected cost." — Mục 35.4
>
> *Dịch: Nói cách khác, thuật toán xấp xỉ ngẫu nhiên giống thuật toán xấp xỉ tất định, chỉ khác là tỷ số xấp xỉ tính cho chi phí kỳ vọng.*

> "The idea behind trimming is that if two values in L are close to each other, then since we want just an approximate solution, we do not need to maintain both of them explicitly." — Mục 35.5
>
> *Dịch: Ý tưởng của việc tỉa là nếu hai giá trị trong L gần nhau, thì vì ta chỉ cần lời giải xấp xỉ, không cần giữ cả hai một cách tường minh.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: một phương pháp luận thống nhất thay vì danh mục thủ thuật

Chương không chỉ liệt kê năm thuật toán mà nhấn mạnh một tư duy chung, nói rõ ngay sau Định lý 35.1: "ta không biết tối ưu, nhưng ta biết một cận của nó". Mỗi mục sau lặp lại sơ đồ đó với một loại cận khác (cây khung, quy hoạch tuyến tính, m mệnh đề, phân bổ chi phí). Người đọc ra khỏi chương với một công thức áp dụng được cho bài toán mới — đúng như các Problem 35-1, 35-4, 35-5, 35-7 yêu cầu: tìm cận dưới (⌈S⌉, kích thước ghép cặp, max p_k và Σp_k/m, nghiệm phân số) rồi chặn lời giải.

### Điểm mạnh: trình bày cả hai mặt — xấp xỉ được và không xấp xỉ được

Định lý 35.3 đặt ngay cạnh Định lý 35.2 cho thấy một điều kiện kỹ thuật (bất đẳng thức tam giác) phân chia giữa "dễ xấp xỉ" và "không xấp xỉ được". Kỹ thuật tạo khoảng cách được nêu thành phương pháp tổng quát, nối với Chương 34 (quy dẫn) và với ghi chú về PCP. Đây là cái nhìn đúng về lý thuyết xấp xỉ hiện đại: độ khó không chỉ là "NP-khó hay không" mà còn "khó xấp xỉ đến mức nào".

### Điểm mạnh: FPTAS cho tổng tập con được trình bày đầy đủ và kiểm chứng được

Ví dụ ⟨104, 102, 201, 101⟩ với mọi danh sách trung gian cho phép người đọc tự chạy tay; phân tích tách rõ hai phần (tỷ số qua (1 + ε/2n)ⁿ ≤ e^(ε/2) ≤ 1 + ε; thời gian qua khoảng cách hình học giữa các phần tử). Chi tiết "tại sao δ = ε/2n chứ không phải ε" là bài học quan trọng về sai số tích luỹ.

### Điểm yếu và chỗ đơn giản hoá

- **Thiếu cận dưới cho các tỷ số đã nêu.** Sách cho ví dụ đồ thị 7 đỉnh ở Mục 35.1 (tỷ số đúng bằng 2) nhưng không nói rõ rằng phân tích của phủ đỉnh và của APPROX-TSP-TOUR là chặt, cũng không nêu (ngoài ghi chú) rằng phủ tập hợp không xấp xỉ được tốt hơn (1 − o(1)) ln |X| trừ khi P = NP, hay MAX-3-SAT không xấp xỉ được tốt hơn 8/7 (theo hiểu biết của người tổng hợp, kết quả của Feige và của Håstad cuối thập niên 1990). Thiếu những điều này, người đọc không thấy các thuật toán đơn giản trong chương thực ra tối ưu (hoặc gần tối ưu) về mặt lý thuyết.
- **Thuật toán ngẫu nhiên chỉ có bảo đảm kỳ vọng.** Sách không bàn cách khử ngẫu nhiên (phương pháp kỳ vọng có điều kiện) để có thuật toán tất định 8/7 cho MAX-3-CNF, cũng không nói về xác suất đạt được kết quả tốt; theo hiểu biết của người tổng hợp, khử ngẫu nhiên ở đây rất đơn giản (gán lần lượt từng biến sao cho kỳ vọng có điều kiện không giảm).
- **Mục 35.4 rất ngắn.** Làm tròn quy hoạch tuyến tính chỉ có một ví dụ ngưỡng 1/2; làm tròn ngẫu nhiên, phương pháp gốc–đối ngẫu và quy hoạch nửa xác định (thuật toán Goemans–Williamson 0,878 cho MAX-CUT, theo hiểu biết của người tổng hợp) chỉ được nhắc tên ở ghi chú.
- **Một vài chỗ đề bài chưa chặt** (xem Lưu ý): Problem 35-6(d) có lẽ in ngược chiều; Exercise 35.2-1 mâu thuẫn với định nghĩa chi phí không âm.
- **PTAS chỉ được định nghĩa, không có ví dụ cụ thể** trong phần chính (chỉ Problem 35-2 và ghi chú về TSP Euclid của Arora và Mitchell).

### So với thực tế

Theo hiểu biết của người tổng hợp: trong công nghiệp, TSP được giải bằng các heuristic cục bộ mạnh (2-opt, 3-opt, Lin–Kernighan và biến thể LKH) và bộ giải chính xác Concorde cho các thể hiện hàng chục nghìn điểm — hầu như không ai dùng APPROX-TSP-TOUR, đúng như sách nói. Năm 2020, Karlin, Klein và Oveis Gharan cải tiến tỷ số Christofides 3/2 đi một lượng cực nhỏ cho TSP metric — cho thấy bài toán "đơn giản" này vẫn là chủ đề nghiên cứu. Phủ tập hợp tham lam là thuật toán tiêu chuẩn trong tối ưu bộ kiểm thử và trong học máy (chọn đặc trưng). Bộ giải quy hoạch nguyên (Gurobi, CPLEX, SCIP) dùng chính nới lỏng tuyến tính làm cận dưới. Đặc biệt, độ khó xấp xỉ của phủ đỉnh (2 − ε) là một giả thuyết mở gắn với Giả thuyết Trò chơi Duy nhất (Unique Games Conjecture).

### Liên hệ các chương khác

- Chương 34: định nghĩa các bài toán và các chứng minh NP-đầy đủ (phủ đỉnh 34.5.2, chu trình Hamilton 34.5.3, TSP 34.5.4, tổng tập con 34.5.5, 3-CNF-SAT 34.4); Định lý 35.3 dùng trực tiếp tính NP-đầy đủ của chu trình Hamilton.
- Chương 23: MST-PRIM là thủ tục con của APPROX-TSP-TOUR; Problem 23-3 (cây khung nút cổ chai) dùng trong Exercise 35.2-4; tính chất lát cắt dùng trong Problem 35-6.
- Chương 12: định nghĩa duyệt cây theo thứ tự trước.
- Chương 16: phương pháp tham lam; bài cái túi phân số (Mục 16.2) là nền của Problem 35-7.
- Chương 5: biến chỉ thị, Bổ đề 5.1, tuyến tính của kỳ vọng cho Định lý 35.6.
- Chương 29: quy hoạch tuyến tính giải được trong đa thức, nền của APPROX-MIN-WEIGHT-VC.
- Chương 26: ghép cặp lớn nhất trong đồ thị hai phía qua luồng cực đại, so với ghép cặp xấp xỉ của Problem 35-4.
- Chương 2: MERGE của sắp xếp trộn là khuôn cho MERGE-LISTS.
- Chương 3 và Phụ lục A: các bất đẳng thức (3.13), (3.14), (3.17), (A.14) và số điều hoà.
- Chương 15: EXACT-SUBSET-SUM thực chất là quy hoạch động trên tập giá trị tổng; FPTAS là quy hoạch động có tỉa trạng thái.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** câu hỏi kiểu "bài này NP-khó, bạn làm gì?" — trả lời theo ba hướng mở đầu chương (đầu vào nhỏ: vét cạn/quy hoạch động bitmask; trường hợp riêng: cây, đồ thị hai phía; xấp xỉ có bảo đảm). Biết giải thích thuật toán 2-xấp xỉ cho phủ đỉnh và cho TSP metric trong vài câu là điểm cộng lớn. Phủ đỉnh trên cây (Exercise 35.1-4) và ghép cặp tham lam (Problem 35-4) là bài phỏng vấn kinh điển.
- **Lập trình thi đấu:** các bài NP-khó thường có ràng buộc nhỏ hoặc cấu trúc đặc biệt (phủ đỉnh trên cây bằng quy hoạch động, phủ đỉnh nhỏ nhất trên đồ thị hai phía bằng định lý König qua luồng cực đại). Tổng tập con với t nhỏ dùng quy hoạch động bitset (EXACT-SUBSET-SUM khi t đa thức). Ở các cuộc thi "heuristic" (tối ưu điểm số), tư duy của chương — tham lam có bảo đảm, rồi cải thiện cục bộ — là điểm xuất phát chuẩn.
- **Kỹ thuật phần mềm:** chọn ít máy chủ/ít bộ kiểm thử phủ mọi yêu cầu (phủ tập hợp tham lam), phân việc cho các worker (lập lịch danh sách, Problem 35-5 — ý tưởng của "least-loaded" load balancer), xếp container vào máy (xếp thùng first-fit / first-fit-decreasing), định tuyến xe (TSP có bất đẳng thức tam giác). Luôn ghi lại cận dưới khi có thể để biết lời giải cách tối ưu bao xa, và nhớ rằng bảo đảm xấu nhất thường bi quan hơn nhiều so với hiệu năng thực tế.

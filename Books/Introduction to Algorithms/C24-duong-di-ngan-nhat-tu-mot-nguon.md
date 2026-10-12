# Chương 24 — Đường đi ngắn nhất từ một nguồn (Single-Source Shortest Paths)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VI "Graph Algorithms", Chương 24 "Single-Source Shortest Paths", trang 643–683.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Chương 22 ([C22-thuat-toan-do-thi-co-ban.md](C22-thuat-toan-do-thi-co-ban.md)) cho cách biểu diễn đồ thị bằng danh sách kề, tìm kiếm theo chiều rộng (BFS — chính là thuật toán đường đi ngắn nhất khi mọi cạnh có trọng số 1, kèm cây BFS và thủ tục PRINT-PATH) và sắp xếp tô-pô. Chương 23 ([C23-cay-khung-nho-nhat.md](C23-cay-khung-nho-nhat.md)) cho thuật toán Prim, thuật toán có cấu trúc gần như trùng với Dijkstra. Chương 6 ([C06-heapsort.md](C06-heapsort.md)) cho hàng đợi ưu tiên bằng đống nhị phân, Chương 19 ([C19-dong-fibonacci.md](C19-dong-fibonacci.md)) cho đống Fibonacci với DECREASE-KEY khấu hao O(1) — hai cấu trúc quyết định thời gian chạy của Dijkstra. Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)) và Chương 16 ([C16-thuat-toan-tham-lam.md](C16-thuat-toan-tham-lam.md)) cho khái niệm cấu trúc con tối ưu mà chương này dựa vào. Chương 24 giải bài toán đường đi ngắn nhất từ một nguồn trên đồ thị có hướng có trọng số bằng một kỹ thuật chung — **nới lỏng cạnh** — và ba thứ tự nới lỏng khác nhau (Bellman-Ford, theo thứ tự tô-pô cho đồ thị không chu trình, Dijkstra), rồi dùng Bellman-Ford giải một lớp quy hoạch tuyến tính đặc biệt. Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)) mở rộng sang mọi cặp đỉnh, dùng lại Bellman-Ford và Dijkstra trong thuật toán Johnson. Chương 26 ([C26-luong-cuc-dai.md](C26-luong-cuc-dai.md)) dùng đường đi ngắn nhất (theo số cạnh) trong thuật toán Edmonds-Karp. Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)) trình bày quy hoạch tuyến tính tổng quát, mà hệ ràng buộc hiệu ở Mục 24.4 là một trường hợp riêng.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **mọi thuật toán đường đi ngắn nhất từ một nguồn trong chương đều chỉ làm một việc — khởi tạo ước lượng v.d = ∞ (nguồn bằng 0) rồi lặp lại phép nới lỏng cạnh RELAX(u, v, w): "nếu đi qua u tới v rẻ hơn thì cập nhật v.d và v.π" — và chúng chỉ khác nhau ở số lần và thứ tự nới lỏng; sáu tính chất của phép nới lỏng (bất đẳng thức tam giác, cận trên, không có đường, hội tụ, nới lỏng theo đường, đồ thị con liền trước) đủ để chứng minh đúng cả ba thuật toán.** Phần mở đầu định nghĩa trọng số đường đi w(p), trọng số đường đi ngắn nhất δ(u, v) (bằng ∞ nếu không có đường, bằng −∞ nếu có chu trình âm chen vào giữa), các biến thể của bài toán, cấu trúc con tối ưu (Bổ đề 24.1), vì sao có thể giả định đường đi ngắn nhất là đường đơn (tối đa |V| − 1 cạnh), cây đường đi ngắn nhất và thủ tục RELAX. Mục 24.1 trình bày Bellman-Ford: |V| − 1 lượt, mỗi lượt nới lỏng mọi cạnh, rồi một lượt kiểm tra phát hiện chu trình âm; thời gian O(VE). Mục 24.2: với đồ thị có hướng không chu trình (dag), nới lỏng cạnh theo thứ tự tô-pô một lần là đủ, thời gian Θ(V + E); ứng dụng tìm đường găng trong sơ đồ PERT. Mục 24.3 trình bày Dijkstra cho trọng số không âm: tham lam lấy đỉnh có ước lượng nhỏ nhất bằng hàng đợi ưu tiên; thời gian O(V²) với mảng, O((V + E) lg V) với đống nhị phân, O(V lg V + E) với đống Fibonacci. Mục 24.4 chỉ ra hệ m ràng buộc hiệu xⱼ − xᵢ ≤ bₖ trên n ẩn có nghiệm khi và chỉ khi đồ thị ràng buộc không có chu trình âm, và nghiệm là xᵢ = δ(v₀, vᵢ); giải bằng Bellman-Ford trong O(n² + nm). Mục 24.5 chứng minh hình thức sáu tính chất của phép nới lỏng.

> **Lưu ý:**
> - **Chương không có mục có dấu sao (★).** Các bài tập có dấu sao: Exercise 24.1-5, 24.1-6, 24.4-8, 24.4-9, 24.4-12. Không Problem nào có dấu sao.
> - **Lớp chữ PDF hỏng toàn bộ ký hiệu toán của chương:** chữ v (đỉnh) và π (đỉnh liền trước) bị mất hẳn (ví dụ `: dD u:dC w.u; /` là `v.d = u.d + w(u, v)`, `: D NIL` là `v.π = NIL`), δ thành `ı`, ∞ thành `1`, dấu trừ thành `/NUL`, ≤ và ≥ mất hẳn (ví dụ `: d ı.s; /` không cho biết là ≥ hay ≤), ma trận A và vectơ b ở Mục 24.4 vỡ thành các cột số rời, tổng Σ ở (24.1) và (24.12) vỡ nhiều dòng; ở Exercise 24.4-8 điều kiện "xᵢ ≤ 0" mất dấu. Các hình 24.1–24.9 trong lớp chữ chỉ còn các con số rời rạc không có hướng cạnh. Mọi pseudocode, công thức, đề bài tập và mọi hình trong bản tổng hợp này đã được đọc lại từ ảnh của toàn bộ 41 trang 643–683; riêng các Hình 24.2, 24.4, 24.5, 24.6 được phóng to từ ảnh trang 648, 652, 656, 659 để xác định hướng và trọng số từng cạnh.
> - **Chỗ chứng minh chưa chặt (nhận xét của người tổng hợp):** (1) Ở chứng minh Định lý 24.4 (phần đồ thị CÓ chu trình âm), sách viện dẫn Hệ quả 24.3 để nói các vᵢ.d trên chu trình là hữu hạn; nhưng Hệ quả 24.3 lại giả thiết đồ thị KHÔNG có chu trình âm đi tới được. Kết luận vẫn đúng — mọi đỉnh đi tới được từ s có một đường đơn ≤ |V| − 1 cạnh, và sau |V| − 1 lượt thì v.d không vượt quá trọng số đường đó nên hữu hạn — nhưng lời viện dẫn không khớp giả thiết. (2) Problem 24-4(d) viết "với mọi u, v ∈ V" trong khi ŵᵢ(u, v) chỉ được định nghĩa cho cạnh (u, v) ∈ E. (3) Problem 24-6 cho phép dãy "bitonic theo nghĩa dịch vòng", khiến số lượt quét cần thiết tăng (xem phần Bài tập); đề không nói rõ điều này ảnh hưởng tới lời giải ra sao. Người tổng hợp không chắc những chỗ này có trong danh sách lỗi chính thức (errata) của ấn bản 3 hay không — theo hiểu biết của người tổng hợp, không tra cứu.
> - **Mọi ví dụ chạy tay trong sách đã được tự kiểm tra lại và đúng:** δ trên đồ thị Hình 24.1 (3, −1, 5, 11, −∞, −∞, −∞, ∞, ∞, ∞); hai cây đường đi ngắn nhất ở Hình 24.2 (d = 0, 3, 9, 5, 11); bốn lượt Bellman-Ford ở Hình 24.4 (kết quả t = 2, x = 4, y = 7, z = −2, trả về TRUE); sáu bước DAG-SHORTEST-PATHS ở Hình 24.5 (kết quả s = 0, t = 2, x = 6, y = 5, z = 3, r = ∞); năm bước Dijkstra ở Hình 24.6 (kết quả t = 8, x = 9, y = 5, z = 7); nghiệm (−5, −3, 0, −1, −4) của hệ (24.3)–(24.10); phép tính 49 × 2 × 0,0107 = 1,0486 ở Problem 24-3; w₃ = 6 và w₃ = 1 ở Problem 24-4. Lời giải của các Exercise 24.1-1, 24.2-1, 24.3-1, 24.4-1, 24.4-2, 24.5-1 trong phần Bài tập do người tổng hợp tự chạy tay.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** nội dung này trở thành Chương 22 (vì ấn bản 4 bỏ một số chương cấu trúc dữ liệu ở Phần V), Chương 25 cũ (mọi cặp đỉnh) thành Chương 23. Pseudocode DIJKSTRA ở ấn bản 4 viết tường minh việc chèn từng đỉnh vào hàng đợi (INSERT) và gọi DECREASE-KEY khi RELAX làm giảm v.d, thay vì để các thao tác này "ngầm" như ấn bản 3. Các khác biệt nhỏ hơn về lời văn và bài tập, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 24.1, trang 643–650) — bài toán, biến thể, chu trình âm, nới lỏng và sáu tính chất

```text
       Bài toán: đồ thị có hướng có trọng số G = (V, E), hàm trọng số w: E → ℝ
       Trọng số đường đi p = ⟨v₀, v₁, …, v_k⟩:  w(p) = Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
       Trọng số đường đi ngắn nhất:
         δ(u, v) = min{ w(p) : p là đường từ u tới v }  nếu có đường
                 = ∞                                    nếu không có đường
       (ví dụ mở đầu: tìm đường ngắn nhất từ Phoenix tới Indianapolis;
        liệt kê mọi tuyến đường là không khả thi)
                                │
                                ▼
       Bốn biến thể:
       · một nguồn (chủ đề của chương): từ s tới mọi đỉnh
       · một đích: đảo chiều mọi cạnh rồi giải bài toán một nguồn
       · một cặp (u, v): giải bài toán một nguồn từ u; chưa ai biết thuật
         toán nào nhanh hơn về tiệm cận trong trường hợp xấu nhất
       · mọi cặp: Chương 25
                                │
                                ▼
       Bổ đề 24.1 (CẤU TRÚC CON TỐI ƯU): mọi đoạn con của một đường đi
       ngắn nhất cũng là đường đi ngắn nhất (chứng minh: "cắt và dán")
                                │
                                ▼
       CẠNH TRỌNG SỐ ÂM được phép, nhưng:
       · chu trình âm đi tới được từ s nằm trên một đường từ s tới v
         ⇒ δ(s, v) = −∞
       · đường đi ngắn nhất không chứa chu trình âm, không chứa chu trình
         dương; chu trình trọng số 0 bỏ đi được
       ⇒ có thể coi đường đi ngắn nhất là ĐƯỜNG ĐƠN, tối đa |V| − 1 cạnh
                                │
                                ▼
       BIỂU DIỄN: mỗi đỉnh có v.π (đỉnh liền trước) và v.d (ước lượng)
       Đồ thị con liền trước G_π = (V_π, E_π):
         V_π = {v : v.π ≠ NIL} ∪ {s};  E_π = {(v.π, v) : v ∈ V_π − {s}}
       Kết thúc thuật toán: G_π là CÂY ĐƯỜNG ĐI NGẮN NHẤT gốc s
       (không nhất thiết duy nhất)
                                │
                                ▼
       INITIALIZE-SINGLE-SOURCE: v.d = ∞, v.π = NIL; s.d = 0     Θ(V)
       RELAX(u, v, w): nếu v.d > u.d + w(u, v) thì
                       v.d = u.d + w(u, v), v.π = u               O(1)
       Mọi thuật toán = khởi tạo + một dãy phép nới lỏng;
       khác nhau ở SỐ LẦN và THỨ TỰ nới lỏng:
       · Dijkstra và thuật toán cho dag: mỗi cạnh đúng một lần
       · Bellman-Ford: mỗi cạnh |V| − 1 lần
                                │
                                ▼
       SÁU TÍNH CHẤT (chứng minh ở Mục 24.5):
       · bất đẳng thức tam giác: δ(s, v) ≤ δ(s, u) + w(u, v)
       · cận trên: luôn có v.d ≥ δ(s, v); đạt bằng rồi thì không đổi
       · không có đường: không có đường s ⇝ v thì v.d = δ(s, v) = ∞
       · hội tụ: s ⇝ u → v ngắn nhất và u.d = δ(s, u) trước khi nới lỏng
         (u, v) thì sau đó v.d = δ(s, v)
       · nới lỏng theo đường: nới lỏng các cạnh của đường ngắn nhất
         p theo đúng thứ tự (xen lẫn gì cũng được) thì v_k.d = δ(s, v_k)
       · đồ thị con liền trước: khi mọi v.d = δ(s, v) thì G_π là cây
         đường đi ngắn nhất gốc s
                                │
                                ▼
       Quy ước: a + ∞ = ∞ (a ≠ −∞); a + (−∞) = −∞ (a ≠ ∞);
       đồ thị lưu bằng danh sách kề, trọng số đọc được trong O(1)
```

### Mục 24.1 — Thuật toán Bellman-Ford (The Bellman-Ford algorithm, trang 651–655)

```text
       Trường hợp tổng quát: trọng số có thể âm
                                │
                                ▼
       BELLMAN-FORD(G, w, s):
       1. INITIALIZE-SINGLE-SOURCE
       2. lặp |V| − 1 lượt: mỗi lượt RELAX mọi cạnh (thứ tự bất kỳ)
       3. duyệt mọi cạnh lần nữa: còn cạnh nào nới lỏng được
          (v.d > u.d + w(u, v)) thì trả về FALSE, không thì TRUE
       Thời gian: Θ(V) + (|V| − 1)·Θ(E) + O(E) = O(VE)
                                │
                                ▼
       Bổ đề 24.2: không có chu trình âm đi tới được ⇒ sau |V| − 1 lượt,
       v.d = δ(s, v) với mọi v đi tới được
       · đường ngắn nhất là đường đơn, k ≤ |V| − 1 cạnh
       · lượt thứ i có nới lỏng cạnh thứ i (vᵢ₋₁, vᵢ) của đường
       · áp dụng tính chất nới lỏng theo đường
                                │
                                ▼
       Hệ quả 24.3: có đường s ⇝ v ⇔ BELLMAN-FORD kết thúc với v.d < ∞
                                │
                                ▼
       Định lý 24.4 (tính đúng):
       · không có chu trình âm: v.d = δ(s, v) với mọi v, G_π là cây
         đường đi ngắn nhất, và bất đẳng thức tam giác làm mọi kiểm tra
         ở bước 3 đều qua ⇒ TRUE
       · có chu trình âm c = ⟨v₀, …, v_k⟩ (v₀ = v_k): giả sử trả về TRUE
         ⇒ vᵢ.d ≤ vᵢ₋₁.d + w(vᵢ₋₁, vᵢ); cộng quanh chu trình, hai tổng
         Σ vᵢ.d và Σ vᵢ₋₁.d bằng nhau và hữu hạn ⇒ 0 ≤ Σ w = w(c) < 0,
         mâu thuẫn ⇒ FALSE
                                │
                                ▼
       Ví dụ 5 đỉnh s, t, x, y, z, 10 cạnh, 4 lượt:
       kết quả d: s 0, t 2, x 4, y 7, z −2; trả về TRUE
```

### Mục 24.2 — Đường đi ngắn nhất từ một nguồn trong đồ thị có hướng không chu trình (Single-source shortest paths in directed acyclic graphs, trang 655–658)

```text
       dag: không có chu trình ⇒ không có chu trình âm ⇒ δ luôn xác định,
       kể cả khi có cạnh âm
                                │
                                ▼
       DAG-SHORTEST-PATHS(G, w, s):
       1. sắp xếp tô-pô các đỉnh (Mục 22.4)                Θ(V + E)
       2. INITIALIZE-SINGLE-SOURCE                          Θ(V)
       3. lấy từng đỉnh u theo thứ tự tô-pô,
          RELAX mọi cạnh đi ra từ u                         Θ(E) tổng cộng
       Thời gian: Θ(V + E), tuyến tính theo kích thước danh sách kề
                                │
                                ▼
       Định lý 24.5: thứ tự tô-pô tự động nới lỏng các cạnh của MỌI
       đường đi ngắn nhất theo đúng thứ tự trên đường
       ⇒ tính chất nới lỏng theo đường cho v.d = δ(s, v)
       ⇒ tính chất đồ thị con liền trước cho cây đường đi ngắn nhất
                                │
                                ▼
       Ví dụ 6 đỉnh r, s, t, x, y, z (nguồn s):
       d cuối: r ∞, s 0, t 2, x 6, y 5, z 3
                                │
                                ▼
       ỨNG DỤNG: ĐƯỜNG GĂNG trong sơ đồ PERT
       · cạnh = công việc, trọng số = thời gian làm
       · đường găng = đường DÀI NHẤT trong dag = cận dưới của tổng
         thời gian làm mọi công việc
       · cách tìm: đổi dấu trọng số rồi chạy DAG-SHORTEST-PATHS, hoặc
         khởi tạo −∞ thay ∞ và đổi ">" thành "<" trong RELAX
```

### Mục 24.3 — Thuật toán Dijkstra (Dijkstra's algorithm, trang 658–664)

```text
       Giả định: mọi trọng số w(u, v) ≥ 0
                                │
                                ▼
       Duy trì tập S các đỉnh đã có trọng số đường đi ngắn nhất cuối cùng;
       hàng đợi ưu tiên nhỏ nhất Q = V − S, khoá là d
       DIJKSTRA(G, w, s):
       · khởi tạo; S = ∅; Q = G.V
       · khi Q còn đỉnh: u = EXTRACT-MIN(Q); S = S ∪ {u};
         RELAX mọi cạnh (u, v) đi ra từ u
       · mỗi đỉnh vào S đúng một lần ⇒ vòng while chạy đúng |V| lần;
         mỗi cạnh được nới lỏng đúng một lần
                                │
                                ▼
       Chiến lược THAM LAM: luôn chọn đỉnh "gần nhất" ngoài S
                                │
                                ▼
       Định lý 24.6 (tính đúng). Bất biến: đầu mỗi vòng while,
       v.d = δ(s, v) với mọi v ∈ S
       · giả sử u là đỉnh ĐẦU TIÊN vào S với u.d ≠ δ(s, u)
       · lấy đường ngắn nhất p từ s tới u; y là đỉnh đầu tiên trên p
         không thuộc S, x ∈ S là đỉnh ngay trước y:
              s ──p₁──▶ x ──▶ y ──p₂──▶ u    (s, x trong S; y, u ngoài S)
       · x.d đúng khi x vào S, cạnh (x, y) được nới lỏng lúc đó
         ⇒ (tính chất hội tụ) y.d = δ(s, y)
       · trọng số không âm ⇒ δ(s, y) ≤ δ(s, u) ≤ u.d (cận trên)
       · u được chọn trước y ⇒ u.d ≤ y.d
       ⇒ mọi dấu ≤ là dấu bằng: u.d = δ(s, u), mâu thuẫn
       Hệ quả 24.7: G_π là cây đường đi ngắn nhất
                                │
                                ▼
       PHÂN TÍCH: |V| lần INSERT, |V| lần EXTRACT-MIN,
                  tối đa |E| lần DECREASE-KEY (ẩn trong RELAX)
       ┌───────────────────────┬────────────┬───────────┬──────────────────┐
       │ hàng đợi ưu tiên      │ EXTRACT-MIN│DECREASE-KEY│ tổng            │
       ├───────────────────────┼────────────┼───────────┼──────────────────┤
       │ mảng đánh số đỉnh     │ O(V)       │ O(1)      │ O(V² + E) = O(V²)│
       │ đống nhị phân         │ O(lg V)    │ O(lg V)   │ O((V + E) lg V)  │
       │ đống Fibonacci        │ O(lg V) kh │ O(1) kh   │ O(V lg V + E)    │
       └───────────────────────┴────────────┴───────────┴──────────────────┘
       (kh = khấu hao; đống nhị phân tốt hơn mảng khi E = o(V²/lg V))
                                │
                                ▼
       Giống BFS: S tương ứng tập đỉnh đen
       Giống Prim: cùng lấy đỉnh "nhẹ nhất" ngoài một tập bằng hàng đợi
       ưu tiên rồi cập nhật khoá các đỉnh còn lại
                                │
                                ▼
       Ví dụ 5 đỉnh s, t, x, y, z: thứ tự lấy ra s, y, z, t, x;
       d cuối: s 0, t 8, x 9, y 5, z 7
```

### Mục 24.4 — Ràng buộc hiệu và đường đi ngắn nhất (Difference constraints and shortest paths, trang 664–670)

```text
       Quy hoạch tuyến tính: tìm x tối đa hoá Σ cᵢxᵢ với Ax ≤ b
       Bài toán KHẢ THI: chỉ cần tìm một x thoả Ax ≤ b (hoặc báo không có)
                                │
                                ▼
       HỆ RÀNG BUỘC HIỆU: mỗi hàng của A có đúng một số 1 và một số −1
       ⇔ m bất đẳng thức dạng  xⱼ − xᵢ ≤ bₖ  trên n ẩn
       Ví dụ 8 ràng buộc (24.3)–(24.10) trên 5 ẩn;
       nghiệm x = (−5, −3, 0, −1, −4), và x′ = (0, 2, 5, 4, 1)
                                │
                                ▼
       Bổ đề 24.8: x là nghiệm ⇒ x + d (cộng d vào mọi thành phần)
       cũng là nghiệm (hiệu không đổi)
                                │
                                ▼
       ĐỒ THỊ RÀNG BUỘC: đỉnh v₀, v₁, …, vₙ (vᵢ ứng với ẩn xᵢ)
       · mỗi ràng buộc xⱼ − xᵢ ≤ bₖ cho cạnh (vᵢ, vⱼ) trọng số bₖ
       · thêm cạnh (v₀, vᵢ) trọng số 0 cho mọi i (để v₀ đi tới mọi đỉnh)
       ⇒ n + 1 đỉnh, n + m cạnh
                                │
                                ▼
       Định lý 24.9:
       · không có chu trình âm ⇒ xᵢ = δ(v₀, vᵢ) là nghiệm
         (vì bất đẳng thức tam giác δ(v₀, vⱼ) ≤ δ(v₀, vᵢ) + w(vᵢ, vⱼ)
          chính là ràng buộc)
       · có chu trình âm ⇒ cộng các ràng buộc dọc chu trình được
         0 ≤ w(c) < 0 ⇒ vô nghiệm
                                │
                                ▼
       Giải: chạy BELLMAN-FORD từ v₀
       TRUE ⇒ đọc nghiệm từ d; FALSE ⇒ vô nghiệm
       Thời gian O((n + 1)(n + m)) = O(n² + nm)
       (Exercise 24.4-5: giảm còn O(nm))
```

### Mục 24.5 — Chứng minh các tính chất của đường đi ngắn nhất (Proofs of shortest-paths properties, trang 671–677)

```text
       Bổ đề 24.10 (bất đẳng thức tam giác): đường ngắn nhất tới v không
       nặng hơn đường "ngắn nhất tới u rồi đi cạnh (u, v)"
                                │
                                ▼
       Bổ đề 24.11 (cận trên): quy nạp theo số phép nới lỏng
       v.d = u.d + w(u, v) ≥ δ(s, u) + w(u, v) ≥ δ(s, v);
       d không bao giờ tăng ⇒ đạt δ rồi thì đứng yên
                                │
                                ▼
       Hệ quả 24.12 (không có đường): ∞ = δ(s, v) ≤ v.d ⇒ v.d = ∞
                                │
                                ▼
       Bổ đề 24.13: ngay sau RELAX(u, v, w): v.d ≤ u.d + w(u, v)
                                │
                                ▼
       Bổ đề 24.14 (hội tụ): v.d ≤ u.d + w = δ(s, u) + w = δ(s, v),
       kết hợp cận trên ⇒ v.d = δ(s, v)
                                │
                                ▼
       Bổ đề 24.15 (nới lỏng theo đường): quy nạp theo i, mỗi bước dùng
       tính chất hội tụ
                                │
                                ▼
       Bổ đề 24.16: không có chu trình âm ⇒ G_π luôn là cây có gốc s
       · không có chu trình: nếu nới lỏng (v_{k−1}, v_k) tạo chu trình
         trong G_π thì cộng các bất đẳng thức d dọc chu trình ra
         0 > w(c): chu trình âm, mâu thuẫn
       · đường từ s tới mỗi đỉnh của V_π tồn tại (Exercise 24.5-6)
       · đường đó duy nhất: hai đường gặp lại ở z thì z.π vừa là x vừa
         là y ≠ x, vô lý
                                │
                                ▼
       Bổ đề 24.17 (đồ thị con liền trước): khi mọi v.d = δ(s, v)
       · V_π = tập đỉnh đi tới được
       · G_π là cây có gốc s (Bổ đề 24.16)
       · đường duy nhất p trong G_π có w(p) ≤ Σ (δ(s, vᵢ) − δ(s, vᵢ₋₁))
         = δ(s, v_k) (tổng rút gọn) ⇒ p là đường đi ngắn nhất
```

### Bài toán cuối chương (Problems 24-1 đến 24-6, trang 678–682)

```text
       24-1 Cải tiến của Yen cho Bellman-Ford: chia E thành Ef (đi từ chỉ số
            nhỏ tới lớn) và Eb (ngược lại), mỗi lượt quét Ef theo thứ tự
            tăng rồi Eb theo thứ tự giảm ⇒ chỉ cần ⌈|V|/2⌉ lượt;
            tiệm cận vẫn O(VE)
                                │
                                ▼
       24-2 Hộp lồng nhau: sắp xếp kích thước để kiểm tra lồng; dựng dag
            "hộp i lồng trong hộp j"; dãy hộp lồng dài nhất = đường dài nhất
            trong dag
                                │
                                ▼
       24-3 Kinh doanh chênh lệch tỷ giá: trọng số −ln R[i, j];
            tích tỷ giá > 1 ⇔ chu trình âm ⇒ Bellman-Ford, O(n³)
                                │
                                ▼
       24-4 Thuật toán co giãn của Gabow: lộ dần từng bit của trọng số,
            mỗi bước đánh lại trọng số không âm có đường ngắn nhất ≤ |E|
            ⇒ Dijkstra bằng mảng thùng O(E) mỗi bước, tổng O(E lg W)
                                │
                                ▼
       24-5 Chu trình trọng số trung bình nhỏ nhất của Karp:
            μ* = min_v max_k (δₙ(s, v) − δₖ(s, v)) / (n − k), O(VE)
                                │
                                ▼
       24-6 Đường đi ngắn nhất bitonic: trọng số dọc đường ngắn nhất tăng
            rồi giảm ⇒ vài lượt nới lỏng các cạnh theo thứ tự trọng số
```

### Ghi chú chương (Chapter notes, trang 682–683)

```text
       Dijkstra (1959) — bài gốc không nhắc tới hàng đợi ưu tiên
       Bellman-Ford: hai thuật toán riêng của Bellman và của Ford;
       Bellman nêu quan hệ đường đi ngắn nhất ↔ ràng buộc hiệu
       Lawler: thuật toán tuyến tính cho dag, coi là "kiến thức dân gian"
                                │
                                ▼
       Trọng số nguyên không âm nhỏ (W = trọng số lớn nhất):
       · Ahuja–Mehlhorn–Orlin–Tarjan: O(E + V √lg W)
       · Thorup: O(E lg lg V); Raman: O(E + V min{(lg V)^(1/3+ε), (lg W)^(1/4+ε)})
         (bộ nhớ phụ thuộc kích thước từ máy; giảm về tuyến tính bằng băm
          ngẫu nhiên)
       · Thorup, đồ thị VÔ HƯỚNG trọng số nguyên: O(V + E) — không phải
         một cài đặt Dijkstra (dãy giá trị EXTRACT-MIN không đơn điệu)
                                │
                                ▼
       Trọng số âm: Gabow–Tarjan O(√V E lg(VW)); Goldberg O(√V E lg W),
       với W = max |w(u, v)|
       Cherkassky–Goldberg–Radzik: thực nghiệm so sánh nhiều thuật toán
```

## Ba câu hỏi chương này trả lời

1. **Làm sao tính đường đi ngắn nhất từ một nguồn khi trọng số có thể âm, và làm sao biết bài toán có nghĩa?** Bài toán có nghĩa khi không có chu trình âm đi tới được từ nguồn s; nếu có thì δ(s, v) = −∞ với mọi v mà chu trình nằm trên một đường từ s tới v. Thuật toán Bellman-Ford khởi tạo s.d = 0, mọi đỉnh khác ∞, rồi làm |V| − 1 lượt, mỗi lượt nới lỏng mọi cạnh. Vì đường đi ngắn nhất có thể coi là đường đơn (tối đa |V| − 1 cạnh), lượt thứ i chắc chắn nới lỏng cạnh thứ i của đường, và tính chất nới lỏng theo đường cho v.d = δ(s, v). Một lượt kiểm tra cuối: nếu còn cạnh (u, v) với v.d > u.d + w(u, v) thì có chu trình âm (cộng các bất đẳng thức quanh chu trình sẽ được 0 ≤ w(c) < 0 nếu không phải vậy). Thời gian O(VE). Ví dụ đồ thị 5 đỉnh của sách: sau 4 lượt, d = (s 0, t 2, x 4, y 7, z −2), trả về TRUE; nếu đổi trọng số cạnh (z, x) từ 7 thành 4 thì chu trình x → t → z → x có trọng số −2 − 4 + 4 = −2 và thuật toán trả về FALSE.
2. **Khi đồ thị có cấu trúc đặc biệt thì làm nhanh hơn thế nào?** Nếu đồ thị không có chu trình (dag), nới lỏng cạnh theo thứ tự tô-pô một lần là đủ: mọi đường đều đi "từ trái sang phải" nên các cạnh của nó tự động được nới lỏng đúng thứ tự, thời gian Θ(V + E); đổi dấu trọng số thì tìm được đường dài nhất (đường găng PERT). Nếu mọi trọng số không âm, Dijkstra lấy tham lam đỉnh có d nhỏ nhất ngoài tập S; chứng minh dựa vào việc đoạn đuôi p₂ của đường ngắn nhất không thể có trọng số âm nên δ(s, y) ≤ δ(s, u). Thời gian O(V²) với mảng, O((V + E) lg V) với đống nhị phân, O(V lg V + E) với đống Fibonacci. Ví dụ của sách: thứ tự lấy ra s, y, z, t, x với d = 0, 5, 7, 8, 9.
3. **Đường đi ngắn nhất liên quan gì tới quy hoạch tuyến tính?** Hệ ràng buộc hiệu xⱼ − xᵢ ≤ bₖ tương đương với bất đẳng thức tam giác δ(v₀, vⱼ) ≤ δ(v₀, vᵢ) + w(vᵢ, vⱼ) trên đồ thị ràng buộc (cạnh vᵢ → vⱼ trọng số bₖ, thêm nguồn v₀ nối mọi đỉnh bằng cạnh trọng số 0). Vì vậy xᵢ = δ(v₀, vᵢ) là nghiệm khi không có chu trình âm, còn chu trình âm chứng tỏ hệ vô nghiệm. Ví dụ 8 ràng buộc trên 5 ẩn của sách cho nghiệm (−5, −3, 0, −1, −4); cộng một hằng số vào mọi ẩn vẫn được nghiệm, ví dụ cộng 5 được (0, 2, 5, 4, 1). Bellman-Ford giải trong O(n² + nm).

## Khái niệm cần biết

- **Đồ thị có hướng có trọng số và trọng số đường đi (weighted directed graph, path weight):** mỗi cạnh (u, v) mang một số thực w(u, v) (khoảng cách, thời gian, chi phí, mức phạt, tổn thất — bất kỳ đại lượng nào cộng dồn tuyến tính dọc đường). Trọng số của đường p = ⟨v₀, v₁, …, v_k⟩ là w(p) = Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ). Ví dụ trên đồ thị của Dijkstra trong sách: đường ⟨s, y, t, x⟩ có trọng số 5 + 3 + 1 = 9. Đây là đại lượng mà cả chương tìm cách tối thiểu hoá.
- **Trọng số đường đi ngắn nhất δ(u, v) và đường đi ngắn nhất (shortest-path weight, shortest path):** δ(u, v) là giá trị nhỏ nhất của w(p) trên mọi đường p từ u tới v, bằng ∞ nếu không có đường, và được quy ước bằng −∞ nếu có chu trình âm nằm trên một đường từ u tới v. Đường đi ngắn nhất là bất kỳ đường p nào có w(p) = δ(u, v). Ví dụ với các cạnh s → a nặng 3, a → b nặng −4: nếu đây là đường duy nhất tới b thì δ(s, b) = 3 + (−4) = −1; nếu e nằm trên chu trình e → f → e nặng 3 + (−6) = −3 đi tới được từ s thì δ(s, e) = −∞; đỉnh h không có đường nào từ s tới thì δ(s, h) = ∞ (đây là ví dụ mở đầu của sách, chép đủ ở phần Nội dung chi tiết).
- **Đỉnh nguồn và bài toán một nguồn (source, single-source shortest-paths problem):** cho đỉnh s, tìm đường ngắn nhất từ s tới mọi đỉnh. Ba biến thể (một đích, một cặp, mọi cặp) đều quy về hoặc dùng lại bài toán này.
- **Cấu trúc con tối ưu (optimal substructure) — Bổ đề 24.1:** nếu p là đường ngắn nhất từ v₀ tới v_k thì đoạn con từ vᵢ tới vⱼ của nó cũng là đường ngắn nhất giữa hai đỉnh đó. Ví dụ: trên đồ thị Dijkstra, ⟨s, y, t, x⟩ là đường ngắn nhất tới x (trọng số 9), nên ⟨s, y, t⟩ (trọng số 8) là đường ngắn nhất tới t. Đây là dấu hiệu cho thấy cả quy hoạch động (Floyd-Warshall) và tham lam (Dijkstra) đều có thể áp dụng.
- **Chu trình trọng số âm (negative-weight cycle):** chu trình có tổng trọng số < 0. Ví dụ chu trình ⟨e, f, e⟩ với e → f nặng 3, f → e nặng −6 có trọng số 3 + (−6) = −3; đi vòng nó càng nhiều lần thì đường tới e càng nhẹ, nên δ(s, e) = −∞. Chu trình âm không đi tới được từ nguồn (như ⟨h, i, j, h⟩ trọng số 2 + 3 − 8 = −3) không ảnh hưởng gì. Quan trọng vì nó quyết định bài toán có nghĩa hay không, và Bellman-Ford phát hiện được nó.
- **Đường đơn (simple path) và giới hạn |V| − 1 cạnh:** đường không lặp đỉnh. Chu trình dương thì bỏ đi làm đường nhẹ hơn, chu trình 0 bỏ đi không đổi trọng số, nên luôn có một đường ngắn nhất là đường đơn, tối đa |V| − 1 cạnh. Ví dụ đồ thị 5 đỉnh thì đường ngắn nhất có ≤ 4 cạnh — vì vậy Bellman-Ford cần 4 lượt.
- **Đỉnh liền trước và đồ thị con liền trước (predecessor v.π, predecessor subgraph G_π):** mỗi đỉnh lưu v.π là một đỉnh khác hoặc NIL; lần ngược chuỗi π từ v về s cho một đường ngắn nhất (theo chiều ngược). G_π gồm s, các đỉnh có π ≠ NIL và các cạnh (v.π, v). Ví dụ kết quả Bellman-Ford trong sách: z.π = t, t.π = x, x.π = y, y.π = s, nên đường tới z là s → y → x → t → z với trọng số 7 − 3 − 2 − 4 = −2.
- **Cây đường đi ngắn nhất (shortest-paths tree):** đồ thị con G′ = (V′, E′) sao cho V′ là tập đỉnh đi tới được từ s, G′ là cây có gốc s, và đường duy nhất từ s tới mỗi v trong G′ là đường ngắn nhất trong G. Không duy nhất: ví dụ đồ thị 5 đỉnh s, t, x, y, z với δ = 0, 3, 9, 5, 11 của sách có 8 cây như vậy, vì y có thể lấy cha là s hoặc t, x lấy t hoặc y, z lấy y hoặc x (người tổng hợp đếm). Đây là "đầu ra" mà mọi thuật toán trong chương tạo ra qua các thuộc tính π.
- **Ước lượng đường đi ngắn nhất (shortest-path estimate) v.d:** một cận trên của δ(s, v), khởi tạo ∞ (s.d = 0), chỉ giảm dần. Ví dụ ở Dijkstra: x.d lần lượt là ∞, 14, 13, 9.
- **Nới lỏng cạnh (relaxation) — RELAX(u, v, w):** kiểm tra xem đi qua u có làm đường tới v ngắn hơn không: nếu v.d > u.d + w(u, v) thì gán v.d = u.d + w(u, v) và v.π = u. Ví dụ: u.d = 5, w(u, v) = 2, v.d = 9 thì v.d thành 7; nếu v.d = 6 thì không đổi. Tên gọi có tính lịch sử: phép này "nới lỏng" ràng buộc v.d ≤ u.d + w(u, v) — sau khi nới lỏng, ràng buộc này được thoả nên không còn "áp lực" nào lên nó. Đây là phép toán duy nhất làm thay đổi d và π trong mọi thuật toán của chương.
- **Bất đẳng thức tam giác (triangle inequality) — Bổ đề 24.10:** với mọi cạnh (u, v): δ(s, v) ≤ δ(s, u) + w(u, v). Ví dụ đồ thị Dijkstra: δ(s, x) = 9 ≤ δ(s, y) + w(y, x) = 5 + 9 = 14.
- **Tính chất cận trên (upper-bound property) — Bổ đề 24.11:** luôn có v.d ≥ δ(s, v), và khi v.d đã bằng δ(s, v) thì không đổi nữa.
- **Tính chất không có đường (no-path property) — Hệ quả 24.12:** không có đường từ s tới v thì v.d = ∞ mãi mãi. Ví dụ trong dag có cạnh r → s nhưng không có cạnh nào đi vào r, chạy từ nguồn s thì r.d = ∞ từ đầu tới cuối.
- **Tính chất hội tụ (convergence property) — Bổ đề 24.14:** nếu s ⇝ u → v là đường ngắn nhất và u.d đã bằng δ(s, u) trước khi nới lỏng (u, v), thì sau đó v.d = δ(s, v) mãi mãi.
- **Tính chất nới lỏng theo đường (path-relaxation property) — Bổ đề 24.15:** nếu các cạnh của một đường ngắn nhất p = ⟨s = v₀, …, v_k⟩ được nới lỏng theo thứ tự (v₀, v₁), (v₁, v₂), …, (v_{k−1}, v_k) — xen giữa có bao nhiêu phép nới lỏng khác cũng được — thì v_k.d = δ(s, v_k). Đây là chìa khoá chứng minh Bellman-Ford và DAG-SHORTEST-PATHS.
- **Tính chất đồ thị con liền trước (predecessor-subgraph property) — Bổ đề 24.17:** khi mọi v.d = δ(s, v) thì G_π là cây đường đi ngắn nhất gốc s.
- **Sắp xếp tô-pô (topological sort):** thứ tự tuyến tính các đỉnh của dag sao cho mọi cạnh (u, v) có u đứng trước v (Mục 22.4). Ví dụ dag có cạnh r → s, s → t, t → x, x → y, y → z và vài cạnh nhảy cóc như s → x, t → z thì r, s, t, x, y, z là một thứ tự tô-pô.
- **Đường găng và sơ đồ PERT (critical path, PERT chart — "program evaluation and review technique"):** cạnh là công việc, trọng số là thời gian; đường găng là đường dài nhất trong dag, cho cận dưới của tổng thời gian hoàn thành mọi việc. Ví dụ: nếu đường găng nặng 12 giờ thì dù có bao nhiêu người làm song song, dự án cũng không xong trước 12 giờ.
- **Hàng đợi ưu tiên nhỏ nhất (min-priority queue):** hỗ trợ INSERT, EXTRACT-MIN, DECREASE-KEY (Chương 6, 19). Dijkstra gọi |V| lần INSERT, |V| lần EXTRACT-MIN, tối đa |E| lần DECREASE-KEY. Với V = 10⁴ và E = 10⁶: mảng tốn khoảng V² = 10⁸; đống nhị phân khoảng (V + E) lg V ≈ 1,01·10⁶ · 13,3 ≈ 1,3·10⁷; đống Fibonacci khoảng V lg V + E ≈ 1,13·10⁶ (ước tính số bậc của người tổng hợp, bỏ qua hằng số).
- **Chiến lược tham lam (greedy strategy):** chọn phương án tốt nhất tại chỗ ở mỗi bước. Dijkstra chọn đỉnh "gần nhất" ngoài S; với trọng số không âm, lựa chọn này không bao giờ phải hối tiếc.
- **Quy hoạch tuyến tính và bài toán khả thi (linear programming, feasibility problem):** cho ma trận A cỡ m × n, vectơ b, c; tối đa hoá Σ cᵢxᵢ với Ax ≤ b. Bài toán khả thi chỉ hỏi có x nào thoả Ax ≤ b hay không.
- **Ràng buộc hiệu (difference constraint):** bất đẳng thức xⱼ − xᵢ ≤ bₖ. Ví dụ lắp ráp: bôi keo lúc x₁, keo cần 2 giờ để khô rồi mới lắp linh kiện lúc x₂ thì x₂ ≥ x₁ + 2, tức x₁ − x₂ ≤ −2.
- **Đồ thị ràng buộc (constraint graph):** đỉnh v₀, v₁, …, vₙ; mỗi ràng buộc xⱼ − xᵢ ≤ bₖ cho cạnh vᵢ → vⱼ trọng số bₖ; thêm cạnh v₀ → vᵢ trọng số 0. Ví dụ ràng buộc x₁ − x₅ ≤ −1 cho cạnh v₅ → v₁ trọng số −1.
- **Phân tích gộp (aggregate analysis):** đếm tổng công việc trên cả quá trình thay vì từng vòng lặp (Chương 17). Dùng ở DAG-SHORTEST-PATHS và Dijkstra: tổng độ dài mọi danh sách kề là |E|, nên vòng for trong chạy tổng cộng |E| lần.

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 643–650)

#### Bài toán

Chương mở đầu bằng câu chuyện giáo sư Patrick muốn tìm đường ngắn nhất từ Phoenix tới Indianapolis trên bản đồ đường bộ nước Mỹ có ghi khoảng cách giữa mọi cặp giao lộ kề nhau. Cách ngây thơ là liệt kê mọi tuyến đường, cộng khoảng cách từng tuyến và chọn tuyến ngắn nhất. Nhưng kể cả khi cấm các tuyến có chu trình, số khả năng vẫn khổng lồ, và phần lớn không đáng xét — ví dụ tuyến đi qua Seattle rõ ràng là tồi vì Seattle lệch khỏi hướng đi vài trăm dặm. Chương này và Chương 25 chỉ ra cách giải hiệu quả.

Trong **bài toán đường đi ngắn nhất** (shortest-paths problem), ta có một đồ thị có hướng có trọng số G = (V, E) với hàm trọng số w: E → ℝ gán cho mỗi cạnh một số thực. **Trọng số** của đường p = ⟨v₀, v₁, …, v_k⟩ là tổng trọng số các cạnh của nó:

```text
w(p) = Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
```

**Trọng số đường đi ngắn nhất** từ u tới v được định nghĩa là

```text
δ(u, v) = min{ w(p) : u ⇝ v theo đường p }   nếu có đường từ u tới v,
        = ∞                                  nếu không có.
```

Một **đường đi ngắn nhất** từ u tới v là bất kỳ đường p nào có w(p) = δ(u, v). Trong ví dụ bản đồ: đỉnh là giao lộ, cạnh là đoạn đường giữa hai giao lộ, trọng số là độ dài đoạn đường. Trọng số có thể biểu diễn những đại lượng khác: thời gian, chi phí, mức phạt, tổn thất — bất cứ đại lượng nào cộng dồn tuyến tính dọc đường mà ta muốn tối thiểu hoá.

Thuật toán tìm kiếm theo chiều rộng (BFS, Mục 22.2) chính là một thuật toán đường đi ngắn nhất cho đồ thị không trọng số (mỗi cạnh trọng số 1). Nhiều khái niệm của BFS (đỉnh liền trước, cây BFS, PRINT-PATH) xuất hiện lại trong chương này, nên tác giả khuyên ôn lại Mục 22.2 trước.

#### Các biến thể (Variants)

Chương tập trung vào **bài toán đường đi ngắn nhất từ một nguồn**: cho G = (V, E), tìm đường ngắn nhất từ một **đỉnh nguồn** (source) s ∈ V cho trước tới mọi đỉnh v ∈ V. Thuật toán cho bài toán này giải được nhiều bài khác:

- **Bài toán một đích (single-destination):** tìm đường ngắn nhất tới một **đỉnh đích** t từ mọi đỉnh v. Đảo chiều mọi cạnh của đồ thị, bài toán thành bài toán một nguồn với nguồn t.
- **Bài toán một cặp (single-pair):** tìm đường ngắn nhất từ u tới v cho trước. Giải bài toán một nguồn với nguồn u là giải luôn bài này. Hơn nữa, mọi thuật toán đã biết cho bài này đều có cùng thời gian xấu nhất tiệm cận với thuật toán một nguồn tốt nhất.
- **Bài toán mọi cặp (all-pairs):** tìm đường ngắn nhất cho mọi cặp u, v. Có thể chạy thuật toán một nguồn từ từng đỉnh, nhưng thường có cách nhanh hơn, và cấu trúc bài toán đáng quan tâm riêng. Chương 25 xử lý chi tiết.

#### Cấu trúc con tối ưu của đường đi ngắn nhất (Optimal substructure of a shortest path)

Các thuật toán đường đi ngắn nhất thường dựa vào tính chất: đường ngắn nhất giữa hai đỉnh chứa bên trong nó những đường ngắn nhất khác. (Thuật toán luồng cực đại Edmonds-Karp ở Chương 26 cũng dựa vào tính chất này.) Cấu trúc con tối ưu là một trong các dấu hiệu chính cho thấy quy hoạch động (Chương 15) và phương pháp tham lam (Chương 16) có thể áp dụng. Thuật toán Dijkstra (Mục 24.3) là thuật toán tham lam; thuật toán Floyd-Warshall cho mọi cặp đỉnh (Mục 25.2) là quy hoạch động.

**Bổ đề 24.1 (Đoạn con của đường đi ngắn nhất là đường đi ngắn nhất).** Cho đồ thị có hướng có trọng số G = (V, E) với hàm trọng số w: E → ℝ, p = ⟨v₀, v₁, …, v_k⟩ là một đường đi ngắn nhất từ v₀ tới v_k, và với mọi i, j thoả 0 ≤ i ≤ j ≤ k, đặt pᵢⱼ = ⟨vᵢ, vᵢ₊₁, …, vⱼ⟩ là đoạn con của p từ vᵢ tới vⱼ. Khi đó pᵢⱼ là một đường đi ngắn nhất từ vᵢ tới vⱼ.

*Chứng minh.* Tách p thành v₀ ⇝ vᵢ (đoạn p₀ᵢ), vᵢ ⇝ vⱼ (đoạn pᵢⱼ), vⱼ ⇝ v_k (đoạn pⱼₖ); khi đó w(p) = w(p₀ᵢ) + w(pᵢⱼ) + w(pⱼₖ). Giả sử có đường p′ᵢⱼ từ vᵢ tới vⱼ với w(p′ᵢⱼ) < w(pᵢⱼ). Thì v₀ ⇝ vᵢ (theo p₀ᵢ) ⇝ vⱼ (theo p′ᵢⱼ) ⇝ v_k (theo pⱼₖ) là một đường từ v₀ tới v_k có trọng số w(p₀ᵢ) + w(p′ᵢⱼ) + w(pⱼₖ) < w(p), mâu thuẫn với việc p là đường ngắn nhất. ∎

#### Cạnh trọng số âm (Negative-weight edges)

Một số trường hợp của bài toán có cạnh trọng số âm. Nếu G không có chu trình trọng số âm đi tới được từ nguồn s, thì δ(s, v) vẫn xác định với mọi v, kể cả khi nó âm. Nếu G có một chu trình âm đi tới được từ s, trọng số đường đi ngắn nhất không còn xác định: không đường nào từ s tới một đỉnh trên chu trình có thể là đường ngắn nhất, vì luôn tìm được đường nhẹ hơn bằng cách đi theo đường "ngắn nhất" đề xuất rồi đi thêm một vòng chu trình âm. Nếu có chu trình âm trên một đường nào đó từ s tới v, ta định nghĩa δ(s, v) = −∞.

**Ví dụ của sách (Hình 24.1), chép lại bằng danh sách cạnh.** Đồ thị có hướng với nguồn s và các cạnh:

| Cạnh | Trọng số | Cạnh | Trọng số |
|---|---|---|---|
| s → a | 3 | c → d | 6 |
| s → c | 5 | d → c | −3 |
| s → e | 2 | d → g | 8 |
| a → b | −4 | e → f | 3 |
| b → g | 4 | f → e | −6 |
| f → g | 7 | h → i | 2 |
| i → j | 3 | j → h | −8 |

Bố cục trong hình gốc: s ở bên trái; ba "hàng" đi sang phải là s → a → b (hàng trên), s → c ⇄ d (hàng giữa), s → e ⇄ f (hàng dưới); cả ba hàng hội tụ về g ở bên phải (b → g, d → g, f → g). Bên phải, tách rời, là tam giác h → i → j → h.

```text
   hàng trên :  s ──3──▶ a ──(−4)──▶ b ──4──▶ g
   hàng giữa :  s ──5──▶ c ⇄ d  (c→d 6, d→c −3);  d ──8──▶ g
   hàng dưới :  s ──2──▶ e ⇄ f  (e→f 3, f→e −6);  f ──7──▶ g
   tách rời  :  h ──2──▶ i ──3──▶ j ──(−8)──▶ h
```

Giá trị δ(s, ·) ghi trong mỗi đỉnh và lý do:

| Đỉnh | δ(s, ·) | Lý do |
|---|---|---|
| s | 0 | nguồn |
| a | 3 | chỉ có một đường ⟨s, a⟩, δ = w(s, a) = 3 |
| b | −1 | chỉ có một đường ⟨s, a, b⟩, δ = 3 + (−4) = −1 |
| c | 5 | vô số đường ⟨s, c⟩, ⟨s, c, d, c⟩, ⟨s, c, d, c, d, c⟩, …; chu trình ⟨c, d, c⟩ có trọng số 6 + (−3) = 3 > 0 nên đường ngắn nhất là ⟨s, c⟩ |
| d | 11 | đường ngắn nhất ⟨s, c, d⟩, trọng số 5 + 6 = 11 |
| e | −∞ | chu trình ⟨e, f, e⟩ có trọng số 3 + (−6) = −3 < 0; đi vòng tuỳ ý nhiều lần thì trọng số âm tuỳ ý |
| f | −∞ | tương tự e |
| g | −∞ | g đi tới được từ f, nên cũng có đường trọng số âm tuỳ ý |
| h, i, j | ∞ | ba đỉnh này tạo chu trình âm (2 + 3 − 8 = −3) nhưng không đi tới được từ s |

Kiểm tra (người tổng hợp): đường ⟨s, a, b, g⟩ nặng 3 − 4 + 4 = 3 và ⟨s, c, d, g⟩ nặng 19 — nếu không có chu trình âm qua f thì δ(s, g) sẽ là 3; nhưng đường ⟨s, e, f, (e, f)ⁿ, g⟩ nặng 2 + 3 − 3n + 7 → −∞.

Một số thuật toán, như Dijkstra, giả định mọi trọng số không âm (như bản đồ đường bộ). Những thuật toán khác, như Bellman-Ford, cho phép cạnh âm và trả lời đúng khi không có chu trình âm đi tới được từ nguồn; thường thì nếu có chu trình như vậy, thuật toán phát hiện và báo ra.

#### Chu trình (Cycles)

Đường đi ngắn nhất có thể chứa chu trình không? Như vừa thấy, nó không thể chứa chu trình âm. Nó cũng không thể chứa chu trình dương: nếu p = ⟨v₀, v₁, …, v_k⟩ là một đường và c = ⟨vᵢ, vᵢ₊₁, …, vⱼ⟩ là chu trình dương trên đường này (vᵢ = vⱼ và w(c) > 0), thì đường p′ = ⟨v₀, v₁, …, vᵢ, vⱼ₊₁, vⱼ₊₂, …, v_k⟩ có trọng số w(p′) = w(p) − w(c) < w(p), nên p không thể là đường ngắn nhất từ v₀ tới v_k.

Còn lại chu trình trọng số 0: bỏ nó khỏi đường thì được đường cùng trọng số. Vậy nếu có đường ngắn nhất từ s tới v chứa chu trình 0, thì có đường ngắn nhất khác không chứa chu trình đó; lặp lại việc bỏ chu trình 0 cho tới khi được đường ngắn nhất không có chu trình. Do đó, không mất tổng quát, có thể giả định các đường ngắn nhất cần tìm không có chu trình, tức là **đường đơn**. Vì đường không chu trình trong G = (V, E) chứa tối đa |V| đỉnh phân biệt, nó chứa tối đa |V| − 1 cạnh. Vậy chỉ cần xét đường ngắn nhất có tối đa |V| − 1 cạnh.

#### Biểu diễn đường đi ngắn nhất (Representing shortest paths)

Ta thường muốn tính không chỉ trọng số mà cả các đỉnh trên đường. Cách biểu diễn giống cây BFS ở Mục 22.2: với mỗi đỉnh v, lưu một **đỉnh liền trước** (predecessor) v.π là một đỉnh khác hoặc NIL. Các thuật toán trong chương đặt π sao cho chuỗi đỉnh liền trước bắt đầu từ v chạy ngược dọc một đường ngắn nhất từ s tới v. Vì vậy với v có v.π ≠ NIL, thủ tục PRINT-PATH(G, s, v) của Mục 22.2 in ra một đường ngắn nhất từ s tới v.

Giữa chừng khi thuật toán đang chạy, các giá trị π có thể chưa chỉ ra đường ngắn nhất. Như ở BFS, ta quan tâm tới **đồ thị con liền trước** (predecessor subgraph) G_π = (V_π, E_π) do các giá trị π sinh ra:

```text
V_π = { v ∈ V : v.π ≠ NIL } ∪ { s }
E_π = { (v.π, v) ∈ E : v ∈ V_π − {s} }
```

Sách sẽ chứng minh rằng khi kết thúc, G_π là một "cây đường đi ngắn nhất" — nói nôm na, một cây có gốc chứa đường ngắn nhất từ s tới mọi đỉnh đi tới được từ s. Cây này giống cây BFS nhưng đo theo trọng số chứ không theo số cạnh. Chính xác: cho G = (V, E) có hướng có trọng số, w: E → ℝ, và G không có chu trình âm đi tới được từ s (để đường ngắn nhất xác định). Một **cây đường đi ngắn nhất gốc s** là một đồ thị con có hướng G′ = (V′, E′) với V′ ⊆ V, E′ ⊆ E sao cho:

1. V′ là tập các đỉnh đi tới được từ s trong G,
2. G′ là một cây có gốc s,
3. với mọi v ∈ V′, đường đơn duy nhất từ s tới v trong G′ là một đường ngắn nhất từ s tới v trong G.

**Ví dụ của sách (Hình 24.2), chép lại.** Đồ thị có nguồn s và 10 cạnh:

| Cạnh | Trọng số | Cạnh | Trọng số |
|---|---|---|---|
| s → t | 3 | y → x | 4 |
| s → y | 5 | y → z | 6 |
| t → x | 6 | x → z | 2 |
| t → y | 2 | z → x | 7 |
| y → t | 1 | z → s | 3 |

Trọng số đường đi ngắn nhất (ghi trong đỉnh): s 0, t 3, x 9, y 5, z 11.

Bố cục trong hình gốc: s ở bên trái; t (trên) và y (dưới) ở cột giữa; x (trên) và z (dưới) ở cột phải. Giữa t và y có hai cạnh ngược chiều (t → y nặng 2, y → t nặng 1), giữa x và z cũng vậy (x → z nặng 2, z → x nặng 7); cạnh chéo y → x nặng 4; cạnh dài z → s nặng 3 quay về nguồn.

Hai cây đường đi ngắn nhất cùng gốc s mà sách tô đậm:

| Cây | Cạnh của cây | Kiểm tra trọng số |
|---|---|---|
| (b) | s → t, s → y, t → x, y → z | t: 3; y: 5; x: 3 + 6 = 9; z: 5 + 6 = 11 |
| (c) | s → t, t → y, y → x, x → z | t: 3; y: 3 + 2 = 5; x: 5 + 4 = 9; z: 9 + 2 = 11 |

Vậy đường ngắn nhất và cây đường đi ngắn nhất không nhất thiết duy nhất. (Người tổng hợp: các cạnh "chặt" — thoả d(v) = d(u) + w(u, v) — là s→t, s→y, t→y, t→x, y→x, y→z, x→z; y chọn cha trong {s, t}, x trong {t, y}, z trong {y, x}, nên có 2 × 2 × 2 = 8 cây.)

#### Nới lỏng (Relaxation)

Các thuật toán trong chương dùng kỹ thuật **nới lỏng**. Với mỗi đỉnh v, ta duy trì thuộc tính v.d, một cận trên của trọng số đường đi ngắn nhất từ s tới v, gọi là **ước lượng đường đi ngắn nhất** (shortest-path estimate). Khởi tạo bằng thủ tục Θ(V) sau:

```text
INITIALIZE-SINGLE-SOURCE(G, s)
1  for each vertex v ∈ G.V
2      v.d = ∞
3      v.π = NIL
4  s.d = 0
```

Sau khởi tạo: v.π = NIL với mọi v, s.d = 0, v.d = ∞ với v ∈ V − {s}.

**Nới lỏng** cạnh (u, v) là kiểm tra xem có thể cải thiện đường ngắn nhất tới v đã tìm được bằng cách đi qua u không, và nếu có thì cập nhật v.d và v.π. Một bước nới lỏng có thể làm giảm v.d và cập nhật v.π. Mã sau thực hiện một bước nới lỏng trên cạnh (u, v) trong O(1):

```text
RELAX(u, v, w)
1  if v.d > u.d + w(u, v)
2      v.d = u.d + w(u, v)
3      v.π = u
```

Dòng 1: so sánh ước lượng hiện tại của v với ước lượng "đi tới u rồi đi cạnh (u, v)". Dòng 2–3: nếu cách mới tốt hơn, cập nhật cả ước lượng lẫn đỉnh liền trước.

*Chú thích 1 của sách về tên gọi:* có vẻ lạ khi gọi "nới lỏng" một phép làm chặt cận trên. Tên gọi có tính lịch sử. Kết quả của bước nới lỏng có thể xem như nới lỏng ràng buộc v.d ≤ u.d + w(u, v) — ràng buộc mà theo bất đẳng thức tam giác (Bổ đề 24.10) phải được thoả nếu u.d = δ(s, u) và v.d = δ(s, v). Nghĩa là, nếu v.d ≤ u.d + w(u, v) thì không có "áp lực" nào phải thoả ràng buộc này, nên ràng buộc được "nới lỏng".

**Hai ví dụ nới lỏng của sách (Hình 24.3)**, cạnh (u, v) trọng số w(u, v) = 2:

| Trường hợp | Trước | Kiểm tra | Sau |
|---|---|---|---|
| (a) | u.d = 5, v.d = 9 | 9 > 5 + 2 = 7 | v.d = 7, v.π = u |
| (b) | u.d = 5, v.d = 6 | 6 ≤ 5 + 2 = 7 | không đổi, v.d = 6 |

Mọi thuật toán trong chương gọi INITIALIZE-SINGLE-SOURCE rồi lặp lại việc nới lỏng cạnh. Hơn nữa, nới lỏng là **cách duy nhất** làm thay đổi ước lượng và đỉnh liền trước. Các thuật toán khác nhau ở số lần nới lỏng mỗi cạnh và thứ tự nới lỏng. Dijkstra và thuật toán cho dag nới lỏng mỗi cạnh đúng một lần; Bellman-Ford nới lỏng mỗi cạnh |V| − 1 lần.

#### Các tính chất của đường đi ngắn nhất và phép nới lỏng (Properties of shortest paths and relaxation)

Để chứng minh các thuật toán đúng, sách viện dẫn sáu tính chất, phát biểu ở đây và chứng minh ở Mục 24.5. Năm tính chất cuối, nói về ước lượng hoặc đồ thị con liền trước, ngầm giả định đồ thị được khởi tạo bằng INITIALIZE-SINGLE-SOURCE(G, s) và chỉ thay đổi qua một dãy bước nới lỏng.

- **Bất đẳng thức tam giác** (Bổ đề 24.10): với mọi cạnh (u, v) ∈ E, δ(s, v) ≤ δ(s, u) + w(u, v).
- **Tính chất cận trên** (Bổ đề 24.11): luôn có v.d ≥ δ(s, v) với mọi v ∈ V, và khi v.d đạt giá trị δ(s, v) thì không bao giờ đổi nữa.
- **Tính chất không có đường** (Hệ quả 24.12): nếu không có đường từ s tới v thì luôn có v.d = δ(s, v) = ∞.
- **Tính chất hội tụ** (Bổ đề 24.14): nếu s ⇝ u → v là một đường ngắn nhất trong G với u, v ∈ V nào đó, và u.d = δ(s, u) tại bất kỳ thời điểm nào trước khi nới lỏng cạnh (u, v), thì v.d = δ(s, v) ở mọi thời điểm sau đó.
- **Tính chất nới lỏng theo đường** (Bổ đề 24.15): nếu p = ⟨v₀, v₁, …, v_k⟩ là đường ngắn nhất từ s = v₀ tới v_k, và ta nới lỏng các cạnh của p theo thứ tự (v₀, v₁), (v₁, v₂), …, (v_{k−1}, v_k), thì v_k.d = δ(s, v_k). Tính chất này đúng bất kể có những bước nới lỏng khác nào, kể cả khi chúng xen lẫn với việc nới lỏng các cạnh của p.
- **Tính chất đồ thị con liền trước** (Bổ đề 24.17): khi v.d = δ(s, v) với mọi v ∈ V, đồ thị con liền trước là một cây đường đi ngắn nhất gốc s.

#### Dàn ý chương và quy ước (Chapter outline)

Mục 24.1: Bellman-Ford, giải trường hợp tổng quát có cạnh âm; rất đơn giản và còn phát hiện chu trình âm đi tới được từ nguồn. Mục 24.2: thuật toán thời gian tuyến tính cho dag. Mục 24.3: Dijkstra, nhanh hơn Bellman-Ford nhưng đòi trọng số không âm. Mục 24.4: dùng Bellman-Ford giải một trường hợp đặc biệt của quy hoạch tuyến tính. Mục 24.5: chứng minh các tính chất trên.

Quy ước số học với vô cực: với mọi số thực a ≠ −∞, a + ∞ = ∞ + a = ∞. Để các chứng minh đúng cả khi có chu trình âm, với mọi a ≠ ∞, a + (−∞) = (−∞) + a = −∞.

Mọi thuật toán trong chương giả định G lưu bằng danh sách kề, mỗi cạnh lưu kèm trọng số, để khi duyệt danh sách kề ta đọc được trọng số trong O(1) mỗi cạnh.

### 2. Thuật toán Bellman-Ford (24.1 The Bellman-Ford algorithm, trang 651–655)

Thuật toán Bellman-Ford giải bài toán một nguồn trong trường hợp tổng quát, trọng số có thể âm. Cho G = (V, E) có hướng có trọng số, nguồn s, hàm w: E → ℝ, thuật toán trả về một giá trị boolean cho biết có chu trình âm đi tới được từ nguồn hay không. Nếu có, thuật toán báo không có lời giải; nếu không, nó tính ra các đường ngắn nhất và trọng số của chúng.

Thuật toán nới lỏng các cạnh, giảm dần ước lượng v.d cho tới khi đạt δ(s, v). Nó trả về TRUE khi và chỉ khi đồ thị không có chu trình âm đi tới được từ nguồn.

Bố cục trong hình gốc: s ở bên trái; t (trên) và y (dưới) ở cột giữa; x (trên) và z (dưới) ở cột phải. Giữa t và x có hai cạnh ngược chiều (t → x nặng 5, x → t nặng −2); hai cạnh chéo bắt chéo nhau là t → z (−4) và y → x (−3); t → y (8) đi thẳng xuống, y → z (9) đi ngang, z → x (7) đi thẳng lên, z → s (2) quay về nguồn.

Dòng 1: khởi tạo d và π. Dòng 2–4: |V| − 1 **lượt** (pass) qua các cạnh; mỗi lượt là một vòng của vòng for dòng 2–4 và nới lỏng mỗi cạnh một lần. Dòng 5–8: kiểm tra chu trình âm — nếu còn cạnh nào nới lỏng được thì trả về FALSE.

**Thời gian:** O(VE) — khởi tạo Θ(V), mỗi lượt trong |V| − 1 lượt tốn Θ(E), vòng kiểm tra dòng 5–7 tốn O(E).

#### Ví dụ chạy tay của sách (Hình 24.4)

Đồ thị 5 đỉnh s, t, x, y, z, nguồn s, 10 cạnh:

| Cạnh | Trọng số | Cạnh | Trọng số |
|---|---|---|---|
| s → t | 6 | y → x | −3 |
| s → y | 7 | y → z | 9 |
| t → x | 5 | z → x | 7 |
| x → t | −2 | z → s | 2 |
| t → y | 8 | t → z | −4 |

```text
                 6          5
          ┌─────────▶ t ═════════ x        (t → x trọng số 5, x → t trọng số −2)
          │         8 │ ╲ −4    ╱ ▲
     s ───┤           ▼   ╲  ╱ −3 │ 7
     ▲    │  7        y    ╳      │
     │    └─────────▶ y ──╱─╲──▶ z
     │                 9         │
     └──────────── 2 ────────────┘     (z → s trọng số 2)
     (hai cạnh chéo: t → z trọng số −4, y → x trọng số −3)
```

Mỗi lượt nới lỏng theo thứ tự: (t, x), (t, y), (t, z), (x, t), (y, x), (y, z), (z, x), (z, s), (s, t), (s, y).

| Thời điểm | s | t | x | y | z | Những phép nới lỏng làm thay đổi |
|---|---|---|---|---|---|---|
| (a) trước lượt 1 | 0 | ∞ | ∞ | ∞ | ∞ | — |
| (b) sau lượt 1 | 0 | 6 (π s) | ∞ | 7 (π s) | ∞ | 8 cạnh đầu xuất phát từ đỉnh d = ∞ nên không đổi gì; (s, t): t = 6; (s, y): y = 7 |
| (c) sau lượt 2 | 0 | 6 | 4 (π y) | 7 | 2 (π t) | (t, x): x = 11; (t, z): z = 6 − 4 = 2; (y, x): x = 7 − 3 = 4 |
| (d) sau lượt 3 | 0 | 2 (π x) | 4 | 7 | 2 | (x, t): t = 4 − 2 = 2 |
| (e) sau lượt 4 | 0 | 2 | 4 | 7 | −2 (π t) | (t, z): z = 2 − 4 = −2 |

Kiểm tra dòng 5–8: không cạnh nào nới lỏng được nữa (ví dụ (z, x): −2 + 7 = 5 ≥ 4; (z, s): −2 + 2 = 0 ≥ 0), nên trả về TRUE. Giá trị ở (e) là kết quả cuối cùng. Cây đường đi ngắn nhất: s → y → x → t → z, trọng số tới z là 7 − 3 − 2 − 4 = −2. (Người tổng hợp đã chạy lại từng phép nới lỏng; khớp hình của sách.)

Nhận xét: ở lượt 2 đỉnh x bị cập nhật hai lần (11 rồi 4) — trong một lượt, thông tin có thể lan qua nhiều cạnh nếu thứ tự cạnh "thuận"; Bellman-Ford chỉ bảo đảm mỗi lượt lan thêm ít nhất một cạnh.

#### Tính đúng

**Bổ đề 24.2.** Cho G = (V, E) có hướng có trọng số với nguồn s và w: E → ℝ, giả sử G không có chu trình âm đi tới được từ s. Sau |V| − 1 vòng của vòng for dòng 2–4 của BELLMAN-FORD, v.d = δ(s, v) với mọi đỉnh v đi tới được từ s.

*Chứng minh.* Dùng tính chất nới lỏng theo đường. Xét đỉnh v đi tới được từ s, và p = ⟨v₀, v₁, …, v_k⟩ với v₀ = s, v_k = v là một đường ngắn nhất bất kỳ từ s tới v. Vì đường ngắn nhất là đường đơn, p có tối đa |V| − 1 cạnh, nên k ≤ |V| − 1. Mỗi vòng trong |V| − 1 vòng của dòng 2–4 nới lỏng cả |E| cạnh. Trong các cạnh được nới lỏng ở vòng thứ i, với i = 1, 2, …, k, có cạnh (vᵢ₋₁, vᵢ). Theo tính chất nới lỏng theo đường, v.d = v_k.d = δ(s, v_k) = δ(s, v). ∎

**Hệ quả 24.3.** Với cùng giả thiết, với mỗi đỉnh v ∈ V, có đường từ s tới v khi và chỉ khi BELLMAN-FORD kết thúc với v.d < ∞ khi chạy trên G. (Chứng minh để cho Exercise 24.1-2.)

**Định lý 24.4 (Tính đúng của thuật toán Bellman-Ford).** Chạy BELLMAN-FORD trên G = (V, E) có hướng có trọng số với nguồn s và w: E → ℝ. Nếu G không có chu trình âm đi tới được từ s, thuật toán trả về TRUE, v.d = δ(s, v) với mọi v ∈ V, và G_π là cây đường đi ngắn nhất gốc s. Nếu G có chu trình âm đi tới được từ s, thuật toán trả về FALSE.

*Chứng minh.* Giả sử G không có chu trình âm đi tới được từ s. Trước hết chứng minh khi kết thúc v.d = δ(s, v) với mọi v. Nếu v đi tới được từ s, Bổ đề 24.2 cho điều đó. Nếu không, tính chất không có đường cho điều đó. Tính chất đồ thị con liền trước cùng khẳng định này cho G_π là cây đường đi ngắn nhất. Giờ chứng minh thuật toán trả về TRUE: khi kết thúc, với mọi cạnh (u, v) ∈ E,

```text
   thứ tự tô-pô (trái → phải):   r    s    t    x    y    z
   cạnh giữa hai đỉnh liền kề:   r─5─▶s─2─▶t─7─▶x─(−1)─▶y─(−2)─▶z
   cạnh "nhảy cóc":              r─3─▶t,  s─6─▶x,  t─4─▶y,  t─2─▶z,  x─1─▶z
```

nên không phép kiểm tra nào ở dòng 6 khiến thuật toán trả về FALSE; nó trả về TRUE.

Giờ giả sử G có chu trình âm đi tới được từ s; gọi chu trình là c = ⟨v₀, v₁, …, v_k⟩ với v₀ = v_k. Khi đó

```text
Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ) < 0                                            (24.1)
```

Giả sử phản chứng thuật toán trả về TRUE. Khi đó vᵢ.d ≤ vᵢ₋₁.d + w(vᵢ₋₁, vᵢ) với i = 1, 2, …, k. Cộng các bất đẳng thức quanh chu trình:

```text
Σᵢ₌₁ᵏ vᵢ.d ≤ Σᵢ₌₁ᵏ (vᵢ₋₁.d + w(vᵢ₋₁, vᵢ))
           = Σᵢ₌₁ᵏ vᵢ₋₁.d + Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
```

Vì v₀ = v_k, mỗi đỉnh của c xuất hiện đúng một lần trong mỗi tổng Σ vᵢ.d và Σ vᵢ₋₁.d, nên hai tổng bằng nhau. Hơn nữa, theo Hệ quả 24.3 (sách viện dẫn như vậy — xem khối Lưu ý), các vᵢ.d hữu hạn, nên có thể trừ hai vế:

```text
0 ≤ Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
```

mâu thuẫn với (24.1). Vậy Bellman-Ford trả về TRUE nếu G không có chu trình âm đi tới được từ nguồn, và FALSE nếu ngược lại. ∎

Ví dụ phản chứng bằng số (người tổng hợp): nếu đổi w(z, x) từ 7 thành 4 trong đồ thị trên, chu trình x → t → z → x nặng −2 − 4 + 4 = −2. Sau 4 lượt: s 0, t 2, x 2, y 7, z −2; ở dòng 6, cạnh (x, t) cho t.d = 2 > x.d + w(x, t) = 2 − 2 = 0, thuật toán trả về FALSE (chi tiết ở Exercise 24.1-1).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: giao thức định tuyến kiểu véc-tơ khoảng cách (distance-vector, như RIP) là Bellman-Ford phân tán — mỗi bộ định tuyến lặp lại phép nới lỏng với bảng khoảng cách của hàng xóm; vấn đề "đếm tới vô cực" của các giao thức này chính là biểu hiện của việc Bellman-Ford hội tụ chậm khi có thay đổi. Biến thể SPFA (hàng đợi các đỉnh vừa thay đổi) được dùng nhiều trong lập trình thi đấu nhưng xấu nhất vẫn O(VE).

### 3. Đường đi ngắn nhất từ một nguồn trong dag (24.2 Single-source shortest paths in directed acyclic graphs, trang 655–658)

Nới lỏng các cạnh của một dag (đồ thị có hướng không chu trình) có trọng số G = (V, E) theo một thứ tự tô-pô của các đỉnh, ta tính được đường ngắn nhất từ một nguồn trong Θ(V + E). Trong dag, đường ngắn nhất luôn xác định, vì kể cả có cạnh âm thì cũng không thể có chu trình âm.

Thuật toán bắt đầu bằng việc sắp xếp tô-pô dag (Mục 22.4) để áp một thứ tự tuyến tính lên các đỉnh: nếu dag có đường từ u tới v thì u đứng trước v. Chỉ cần một lượt qua các đỉnh theo thứ tự đó; khi xử lý mỗi đỉnh, nới lỏng mọi cạnh đi ra từ nó.

```text
DAG-SHORTEST-PATHS(G, w, s)
1  topologically sort the vertices of G
2  INITIALIZE-SINGLE-SOURCE(G, s)
3  for each vertex u, taken in topologically sorted order
4      for each vertex v ∈ G.Adj[u]
5          RELAX(u, v, w)
```

Dòng 1: sắp xếp tô-pô các đỉnh của G. Dòng 3: lấy từng đỉnh u theo thứ tự tô-pô. Dòng 4–5: nới lỏng mọi cạnh (u, v) đi ra từ u.

**Thời gian:** sắp xếp tô-pô dòng 1 tốn Θ(V + E) (Mục 22.4); INITIALIZE-SINGLE-SOURCE tốn Θ(V); vòng for dòng 3–5 chạy một vòng mỗi đỉnh; tổng cộng vòng for dòng 4–5 nới lỏng mỗi cạnh đúng một lần (phân tích gộp). Mỗi vòng trong tốn Θ(1), nên tổng thời gian Θ(V + E) — tuyến tính theo kích thước biểu diễn danh sách kề.

#### Ví dụ chạy tay của sách (Hình 24.5)

Sáu đỉnh đã xếp theo thứ tự tô-pô từ trái sang phải: r, s, t, x, y, z; nguồn s. Các cạnh:

| Cạnh | Trọng số | Cạnh | Trọng số |
|---|---|---|---|
| r → s | 5 | t → y | 4 |
| r → t | 3 | t → z | 2 |
| s → t | 2 | x → y | −1 |
| s → x | 6 | x → z | 1 |
| t → x | 7 | y → z | −2 |

Bố cục trong hình gốc: s ở bên trái; t (trên) và y (dưới) ở cột giữa; x (trên) và z (dưới) ở cột phải. Giữa t và y có hai cạnh ngược chiều (t → y nặng 2, y → t nặng 3), giữa x và z cũng vậy (x → z nặng 4, z → x nặng 6); cạnh chéo y → x nặng 9; t → x nặng 1 và y → z nặng 2 đi ngang; z → s nặng 7 quay về nguồn.

| Bước | Đỉnh u được xử lý | Các thay đổi | r | s | t | x | y | z |
|---|---|---|---|---|---|---|---|---|
| (a) | trước vòng lặp | — | ∞ | 0 | ∞ | ∞ | ∞ | ∞ |
| (b) | r | r.d = ∞ nên nới lỏng (r, s), (r, t) không đổi gì | ∞ | 0 | ∞ | ∞ | ∞ | ∞ |
| (c) | s | t = 0 + 2 = 2 (π s); x = 0 + 6 = 6 (π s) | ∞ | 0 | 2 | 6 | ∞ | ∞ |
| (d) | t | (t, x): 2 + 7 = 9 ≥ 6 không đổi; y = 2 + 4 = 6 (π t); z = 2 + 2 = 4 (π t) | ∞ | 0 | 2 | 6 | 6 | 4 |
| (e) | x | y = 6 − 1 = 5 (π x); (x, z): 6 + 1 = 7 ≥ 4 không đổi | ∞ | 0 | 2 | 6 | 5 | 4 |
| (f) | y | z = 5 − 2 = 3 (π y) | ∞ | 0 | 2 | 6 | 5 | 3 |
| (g) | z | không có cạnh ra | ∞ | 0 | 2 | 6 | 5 | 3 |

Giá trị ở (g) là cuối cùng. Cây: s → t, s → x, x → y, y → z. Đường ngắn nhất tới z là s → x → y → z, trọng số 6 − 1 − 2 = 3 — nhẹ hơn đường "ngắn về số cạnh" s → t → z (trọng số 4), nhờ hai cạnh âm.

**Định lý 24.5.** Nếu đồ thị có hướng có trọng số G = (V, E) có nguồn s và không có chu trình, thì khi DAG-SHORTEST-PATHS kết thúc, v.d = δ(s, v) với mọi v ∈ V, và G_π là cây đường đi ngắn nhất.

*Chứng minh.* Trước hết chứng minh v.d = δ(s, v) khi kết thúc. Nếu v không đi tới được từ s, tính chất không có đường cho v.d = δ(s, v) = ∞. Giả sử v đi tới được, nên có đường ngắn nhất p = ⟨v₀, v₁, …, v_k⟩ với v₀ = s, v_k = v. Vì các đỉnh được xử lý theo thứ tự tô-pô, các cạnh của p được nới lỏng theo thứ tự (v₀, v₁), (v₁, v₂), …, (v_{k−1}, v_k). Tính chất nới lỏng theo đường cho vᵢ.d = δ(s, vᵢ) khi kết thúc với i = 0, 1, …, k. Cuối cùng, theo tính chất đồ thị con liền trước, G_π là cây đường đi ngắn nhất. ∎

#### Ứng dụng: đường găng trong sơ đồ PERT

Một ứng dụng thú vị là xác định **đường găng** (critical path) trong phân tích **sơ đồ PERT** (chú thích 2 của sách: "PERT" viết tắt của "program evaluation and review technique" — kỹ thuật đánh giá và rà soát chương trình). Cạnh biểu diễn công việc, trọng số là thời gian cần để làm việc đó. Nếu cạnh (u, v) đi vào v và cạnh (v, x) đi ra khỏi v, thì việc (u, v) phải làm xong trước việc (v, x). Một đường trong dag biểu diễn một dãy công việc phải làm theo đúng thứ tự. **Đường găng** là một đường *dài nhất* trong dag, ứng với thời gian dài nhất để làm một dãy công việc nối tiếp. Do đó trọng số đường găng là cận dưới cho tổng thời gian làm mọi việc. Tìm đường găng bằng một trong hai cách:

- đổi dấu mọi trọng số rồi chạy DAG-SHORTEST-PATHS, hoặc
- chạy DAG-SHORTEST-PATHS với hai sửa đổi: thay "∞" bằng "−∞" ở dòng 2 của INITIALIZE-SINGLE-SOURCE và thay ">" bằng "<" trong RELAX.

Cách này chỉ đúng vì đồ thị không chu trình: trên đồ thị tổng quát, bài toán đường đơn dài nhất là NP-khó (theo hiểu biết của người tổng hợp; Chương 34 bàn về lớp bài toán này).

Ví dụ của người tổng hợp: bốn việc A (đổ móng, 3 ngày), B (dựng khung, 5 ngày, sau A), C (đi điện, 2 ngày, sau A), D (hoàn thiện, 4 ngày, sau cả B và C). Hai đường: A–B–D = 12 ngày, A–C–D = 9 ngày. Đường găng là A–B–D: dự án không thể xong trước 12 ngày, và trễ B một ngày là trễ cả dự án, còn C có 3 ngày dự phòng.

### 4. Thuật toán Dijkstra (24.3 Dijkstra's algorithm, trang 658–664)

Thuật toán Dijkstra giải bài toán một nguồn trên đồ thị có hướng có trọng số G = (V, E) trong trường hợp mọi trọng số không âm. Vì vậy trong mục này giả định w(u, v) ≥ 0 với mọi cạnh (u, v) ∈ E. Với cài đặt tốt, Dijkstra chạy nhanh hơn Bellman-Ford.

Thuật toán duy trì tập S các đỉnh đã xác định xong trọng số đường đi ngắn nhất cuối cùng từ nguồn s. Nó lặp lại: chọn đỉnh u ∈ V − S có ước lượng nhỏ nhất, thêm u vào S, và nới lỏng mọi cạnh đi ra từ u. Cài đặt dưới đây dùng hàng đợi ưu tiên nhỏ nhất Q chứa các đỉnh, khoá là giá trị d.

```text
DIJKSTRA(G, w, s)
1  INITIALIZE-SINGLE-SOURCE(G, s)
2  S = ∅
3  Q = G.V
4  while Q ≠ ∅
5      u = EXTRACT-MIN(Q)
6      S = S ∪ {u}
7      for each vertex v ∈ G.Adj[u]
8          RELAX(u, v, w)
```

Dòng 1 khởi tạo d và π như thường lệ; dòng 2 khởi tạo S rỗng. Thuật toán duy trì bất biến Q = V − S ở đầu mỗi vòng while dòng 4–8. Dòng 3 khởi tạo Q chứa mọi đỉnh của V; vì lúc đó S = ∅, bất biến đúng sau dòng 3. Mỗi vòng while, dòng 5 lấy ra một đỉnh u từ Q = V − S và dòng 6 thêm nó vào S, giữ nguyên bất biến. (Vòng đầu tiên, u = s.) Vì vậy u có ước lượng nhỏ nhất trong V − S. Dòng 7–8 nới lỏng mọi cạnh (u, v) đi ra từ u, cập nhật v.d và v.π nếu đi qua u làm đường tới v ngắn hơn. Thuật toán không bao giờ chèn đỉnh vào Q sau dòng 3, và mỗi đỉnh được lấy ra khỏi Q và thêm vào S đúng một lần, nên vòng while chạy đúng |V| lần.

Vì Dijkstra luôn chọn đỉnh "nhẹ nhất" hay "gần nhất" trong V − S để thêm vào S, ta nói nó dùng **chiến lược tham lam**. Chương 16 giải thích chiến lược tham lam chi tiết, nhưng không cần đọc chương đó để hiểu Dijkstra. Nói chung tham lam không luôn cho kết quả tối ưu, nhưng định lý và hệ quả sau cho thấy Dijkstra thật sự tính đúng đường ngắn nhất. Mấu chốt là chứng minh mỗi khi thêm u vào S thì u.d = δ(s, u).

#### Ví dụ chạy tay của sách (Hình 24.6)

Đồ thị 5 đỉnh, nguồn s ở bên trái:

| Cạnh | Trọng số | Cạnh | Trọng số |
|---|---|---|---|
| s → t | 10 | y → x | 9 |
| s → y | 5 | y → z | 2 |
| t → x | 1 | x → z | 4 |
| t → y | 2 | z → x | 6 |
| y → t | 3 | z → s | 7 |

```text
               10          1
         ┌──────────▶ t ─────────▶ x
         │          2 │ ▲ 3    ▲   │ ▲
    s ───┤            ▼ │  9 ╱   4 │ │ 6
    ▲    │   5        y ───╯       ▼ │
    │    └──────────▶ y ─────────▶ z
    │                      2       │
    └──────────────── 7 ───────────┘    (z → s trọng số 7)
```

Trong hình gốc, đỉnh đen thuộc S, đỉnh trắng thuộc Q = V − S, đỉnh tô xám là đỉnh sẽ được chọn ở dòng 5 vòng kế tiếp; cạnh tô đậm chỉ π.

| Bước | Đỉnh lấy ra (u) | S sau bước | s | t | x | y | z | Thay đổi khi nới lỏng cạnh ra từ u |
|---|---|---|---|---|---|---|---|---|
| (a) | — (trước vòng 1) | ∅ | 0 | ∞ | ∞ | ∞ | ∞ | — |
| (b) | s (d = 0) | {s} | 0 | 10 (π s) | ∞ | 5 (π s) | ∞ | t = 10; y = 5 |
| (c) | y (d = 5) | {s, y} | 0 | 8 (π y) | 14 (π y) | 5 | 7 (π y) | t = 5 + 3 = 8; x = 5 + 9 = 14; z = 5 + 2 = 7 |
| (d) | z (d = 7) | {s, y, z} | 0 | 8 | 13 (π z) | 5 | 7 | x = 7 + 6 = 13; (z, s): 14 ≥ 0 không đổi |
| (e) | t (d = 8) | {s, y, z, t} | 0 | 8 | 9 (π t) | 5 | 7 | x = 8 + 1 = 9; (t, y): 10 ≥ 5 không đổi |
| (f) | x (d = 9) | V | 0 | 8 | 9 | 5 | 7 | (x, z): 13 ≥ 7 không đổi |

Giá trị ở (f) là cuối cùng. Cây: s → y, y → t, t → x, y → z. Nhận xét: x.d giảm ba lần (14 → 13 → 9), tức ba lần DECREASE-KEY cho cùng một đỉnh — minh hoạ cho việc Dijkstra thường gọi DECREASE-KEY nhiều hơn EXTRACT-MIN.

#### Tính đúng

**Định lý 24.6 (Tính đúng của thuật toán Dijkstra).** Chạy Dijkstra trên đồ thị có hướng có trọng số G = (V, E) với hàm trọng số không âm w và nguồn s, thuật toán kết thúc với u.d = δ(s, u) với mọi u ∈ V.

*Chứng minh.* Dùng bất biến vòng lặp:

> Đầu mỗi vòng while dòng 4–8, v.d = δ(s, v) với mọi đỉnh v ∈ S.

Chỉ cần chứng minh với mỗi u ∈ V, u.d = δ(s, u) tại thời điểm u được thêm vào S; sau đó tính chất cận trên bảo đảm đẳng thức giữ mãi.

**Khởi tạo:** ban đầu S = ∅ nên bất biến đúng hiển nhiên.

**Duy trì:** cần chứng minh mỗi vòng, u.d = δ(s, u) với đỉnh u được thêm vào S. Giả sử phản chứng u là đỉnh đầu tiên mà u.d ≠ δ(s, u) khi được thêm vào S. Xét tình huống ở đầu vòng while mà u được thêm vào S, và rút ra mâu thuẫn u.d = δ(s, u) bằng cách xét một đường ngắn nhất từ s tới u.

- u ≠ s, vì s là đỉnh đầu tiên vào S và lúc đó s.d = δ(s, s) = 0. Vì u ≠ s nên S ≠ ∅ ngay trước khi thêm u.
- Phải có đường từ s tới u, nếu không thì u.d = δ(s, u) = ∞ theo tính chất không có đường, trái giả thiết u.d ≠ δ(s, u). Vì có ít nhất một đường nên có đường ngắn nhất p từ s tới u.
- Trước khi thêm u vào S, p nối một đỉnh trong S (là s) với một đỉnh trong V − S (là u). Gọi y là đỉnh đầu tiên trên p thuộc V − S, và x ∈ S là đỉnh đứng ngay trước y trên p. Tách p thành s ⇝ x (đoạn p₁) → y ⇝ u (đoạn p₂). (Đoạn p₁ hoặc p₂ có thể không có cạnh nào.)

Hình 24.7 của sách minh hoạ tình huống này, vẽ lại:

```text
     ┌──────────── tập S ────────────┐
     │                               │
     │   s ──── p₁ ────▶ x ──────────┼──▶ y ─── p₂ ───▶ u
     │                               │     (p₂ có thể quay lại vào S
     └───────────────────────────────┘      rồi ra lại)
   x và y khác nhau, nhưng có thể s = x hoặc y = u
```

- **Khẳng định: y.d = δ(s, y) khi u được thêm vào S.** Vì x ∈ S và u là đỉnh đầu tiên sai khi vào S, nên x.d = δ(s, x) lúc x được thêm vào S. Cạnh (x, y) được nới lỏng lúc đó, nên khẳng định suy ra từ tính chất hội tụ (s ⇝ x → y là đường ngắn nhất theo Bổ đề 24.1).
- Giờ rút ra mâu thuẫn. Vì y đứng trước u trên đường ngắn nhất từ s tới u và mọi trọng số không âm (đặc biệt là trên p₂), δ(s, y) ≤ δ(s, u), do đó

```text
y.d = δ(s, y)
    ≤ δ(s, u)                                                    (24.2)
    ≤ u.d          (tính chất cận trên)
```

- Nhưng vì cả u và y đều thuộc V − S khi u được chọn ở dòng 5, nên u.d ≤ y.d. Do đó hai bất đẳng thức trong (24.2) thực ra là đẳng thức: y.d = δ(s, y) = δ(s, u) = u.d. Vậy u.d = δ(s, u), trái với cách chọn u. Kết luận: u.d = δ(s, u) khi u được thêm vào S, và đẳng thức giữ mãi sau đó.

**Kết thúc:** khi kết thúc Q = ∅, cùng bất biến Q = V − S cho S = V. Vậy u.d = δ(s, u) với mọi u ∈ V. ∎

**Hệ quả 24.7.** Chạy Dijkstra trên đồ thị có hướng có trọng số không âm với nguồn s, khi kết thúc đồ thị con liền trước G_π là cây đường đi ngắn nhất gốc s. *Chứng minh:* suy ngay từ Định lý 24.6 và tính chất đồ thị con liền trước. ∎

Chỗ trọng số không âm được dùng (nhận xét của người tổng hợp): duy nhất ở bước δ(s, y) ≤ δ(s, u). Nếu p₂ có cạnh âm, y có thể "xa" hơn u mà vẫn nằm trên đường ngắn nhất tới u, và lập luận sụp đổ (Exercise 24.3-2 cho ví dụ cụ thể).

#### Phân tích (Analysis)

Dijkstra duy trì hàng đợi Q bằng ba thao tác: INSERT (ngầm ở dòng 3), EXTRACT-MIN (dòng 5), DECREASE-KEY (ngầm trong RELAX ở dòng 8). Nó gọi INSERT và EXTRACT-MIN mỗi đỉnh một lần. Vì mỗi đỉnh u vào S đúng một lần, mỗi cạnh trong danh sách kề Adj[u] được xét trong vòng for dòng 7–8 đúng một lần. Tổng số cạnh trong mọi danh sách kề là |E|, nên vòng for chạy tổng cộng |E| lần, và thuật toán gọi DECREASE-KEY tối đa |E| lần (lại là phân tích gộp).

Thời gian phụ thuộc cách cài đặt hàng đợi:

- **Mảng:** tận dụng việc các đỉnh đánh số 1 tới |V|, lưu v.d ở ô thứ v của mảng. INSERT và DECREASE-KEY tốn O(1), EXTRACT-MIN tốn O(V) (phải tìm khắp mảng). Tổng O(V² + E) = O(V²).
- **Đống nhị phân nhỏ nhất:** khi đồ thị đủ thưa — cụ thể E = o(V²/lg V). (Như Mục 6.5 đã bàn, cài đặt phải bảo đảm đỉnh và phần tử đống giữ "tay cầm" (handle) trỏ tới nhau.) Mỗi EXTRACT-MIN tốn O(lg V), có |V| lần. Dựng đống tốn O(V). Mỗi DECREASE-KEY tốn O(lg V), tối đa |E| lần. Tổng O((V + E) lg V), tức O(E lg V) nếu mọi đỉnh đi tới được từ nguồn. Cách này tốt hơn O(V²) khi E = o(V²/lg V).
- **Đống Fibonacci (Chương 19):** đạt O(V lg V + E). Chi phí khấu hao mỗi lần EXTRACT-MIN trong |V| lần là O(lg V), mỗi DECREASE-KEY trong tối đa |E| lần chỉ O(1) khấu hao. Về lịch sử, đống Fibonacci ra đời từ nhận xét rằng Dijkstra thường gọi DECREASE-KEY nhiều hơn EXTRACT-MIN, nên bất kỳ cách nào giảm chi phí khấu hao của DECREASE-KEY xuống o(lg V) mà không tăng chi phí EXTRACT-MIN sẽ cho cài đặt nhanh hơn đống nhị phân về tiệm cận.

So sánh bằng số (người tổng hợp, bỏ qua hằng số): đồ thị đường bộ V = 10⁶ giao lộ, E = 3·10⁶ đoạn đường: mảng ≈ 10¹² phép; đống nhị phân ≈ 4·10⁶ · 20 = 8·10⁷; đống Fibonacci ≈ 10⁶ · 20 + 3·10⁶ = 2,3·10⁷. Đồ thị dày V = 10³, E = 10⁶: mảng ≈ 10⁶; đống nhị phân ≈ 10⁶ · 10 = 10⁷ — lúc này mảng lại tốt hơn.

**Dijkstra giống BFS và giống Prim.** Giống BFS (Mục 22.2) ở chỗ tập S tương ứng tập đỉnh đen trong BFS: như các đỉnh trong S có trọng số đường đi ngắn nhất cuối cùng, các đỉnh đen trong BFS có khoảng cách BFS đúng. Giống Prim (Mục 23.2) ở chỗ cả hai dùng hàng đợi ưu tiên nhỏ nhất để tìm đỉnh "nhẹ nhất" ngoài một tập cho trước (tập S ở Dijkstra, cây đang lớn ở Prim), thêm đỉnh đó vào tập, rồi điều chỉnh trọng số các đỉnh còn lại ngoài tập. Khác biệt duy nhất (người tổng hợp): khoá ở Prim là w(u, v), ở Dijkstra là u.d + w(u, v).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: định tuyến trạng thái liên kết (link-state, OSPF, IS-IS) cho mỗi bộ định tuyến chạy Dijkstra trên bản đồ toàn mạng; các dịch vụ chỉ đường dùng Dijkstra hai chiều, A* (Dijkstra có thêm hàm ước lượng) và các kỹ thuật tiền xử lý như phân cấp co rút (contraction hierarchies) để trả lời trong vài mili giây trên đồ thị hàng chục triệu đỉnh. Trong cài đặt thực tế, người ta thường không dùng DECREASE-KEY mà chèn bản sao mới vào đống nhị phân và bỏ qua bản cũ khi lấy ra ("lazy deletion"), thời gian O(E lg E) = O(E lg V).

### 5. Ràng buộc hiệu và đường đi ngắn nhất (24.4 Difference constraints and shortest paths, trang 664–670)

Chương 29 nghiên cứu quy hoạch tuyến tính tổng quát: tối ưu một hàm tuyến tính dưới một tập bất đẳng thức tuyến tính. Mục này xét một trường hợp đặc biệt quy được về đường đi ngắn nhất từ một nguồn, rồi giải bằng Bellman-Ford.

#### Quy hoạch tuyến tính (Linear programming)

Trong **bài toán quy hoạch tuyến tính** tổng quát, cho ma trận A cỡ m × n, vectơ b có m thành phần, vectơ c có n thành phần. Ta muốn tìm vectơ x có n thành phần tối đa hoá **hàm mục tiêu** Σᵢ₌₁ⁿ cᵢxᵢ dưới m ràng buộc Ax ≤ b.

Thuật toán đơn hình (simplex), trọng tâm Chương 29, không phải lúc nào cũng chạy trong thời gian đa thức theo kích thước đầu vào, nhưng có những thuật toán quy hoạch tuyến tính khác chạy đa thức. Hai lý do nên hiểu cách thiết lập bài toán: thứ nhất, nếu biểu diễn được một bài toán thành quy hoạch tuyến tính kích thước đa thức thì lập tức có thuật toán đa thức; thứ hai, nhiều trường hợp đặc biệt có thuật toán nhanh hơn — ví dụ bài toán đường đi ngắn nhất một cặp (Exercise 24.4-4) và luồng cực đại (Exercise 26.1-5) là các trường hợp đặc biệt.

Đôi khi ta không quan tâm hàm mục tiêu mà chỉ muốn tìm một **nghiệm khả thi** (feasible solution) — vectơ x bất kỳ thoả Ax ≤ b — hoặc xác định không có nghiệm. Mục này tập trung vào một **bài toán khả thi** như vậy.

#### Hệ ràng buộc hiệu (Systems of difference constraints)

Trong **hệ ràng buộc hiệu**, mỗi hàng của ma trận A có đúng một số 1 và một số −1, mọi phần tử khác bằng 0. Vậy Ax ≤ b là tập m **ràng buộc hiệu** trên n ẩn, mỗi ràng buộc có dạng

```text
xⱼ − xᵢ ≤ bₖ        với 1 ≤ i, j ≤ n, i ≠ j, và 1 ≤ k ≤ m
```

Ví dụ: tìm vectơ 5 thành phần x = (xᵢ) thoả

```text
⎛  1  −1   0   0   0 ⎞            ⎛  0 ⎞
⎜  1   0   0   0  −1 ⎟            ⎜ −1 ⎟
⎜  0   1   0   0  −1 ⎟   ⎛ x₁ ⎞   ⎜  1 ⎟
⎜ −1   0   1   0   0 ⎟   ⎜ x₂ ⎟   ⎜  5 ⎟
⎜ −1   0   0   1   0 ⎟ · ⎜ x₃ ⎟ ≤ ⎜  4 ⎟
⎜  0   0  −1   1   0 ⎟   ⎜ x₄ ⎟   ⎜ −1 ⎟
⎜  0   0  −1   0   1 ⎟   ⎝ x₅ ⎠   ⎜ −3 ⎟
⎝  0   0   0  −1   1 ⎠            ⎝ −3 ⎠
```

tương đương với tìm x₁, …, x₅ thoả 8 ràng buộc hiệu:

```text
x₁ − x₂ ≤  0                                                     (24.3)
x₁ − x₅ ≤ −1                                                     (24.4)
x₂ − x₅ ≤  1                                                     (24.5)
x₃ − x₁ ≤  5                                                     (24.6)
x₄ − x₁ ≤  4                                                     (24.7)
x₄ − x₃ ≤ −1                                                     (24.8)
x₅ − x₃ ≤ −3                                                     (24.9)
x₅ − x₄ ≤ −3                                                     (24.10)
```

Một nghiệm là x = (−5, −3, 0, −1, −4), có thể kiểm tra trực tiếp. Kiểm tra (người tổng hợp): x₁ − x₂ = −2 ≤ 0; x₁ − x₅ = −1 ≤ −1; x₂ − x₅ = 1 ≤ 1; x₃ − x₁ = 5 ≤ 5; x₄ − x₁ = 4 ≤ 4; x₄ − x₃ = −1 ≤ −1; x₅ − x₃ = −4 ≤ −3; x₅ − x₄ = −3 ≤ −3. Đúng cả 8. Thực ra bài có nhiều hơn một nghiệm; một nghiệm khác là x′ = (0, 2, 5, 4, 1). Hai nghiệm có liên hệ: mỗi thành phần của x′ lớn hơn thành phần tương ứng của x đúng 5. Đây không phải trùng hợp.

**Bổ đề 24.8.** Cho x = (x₁, x₂, …, xₙ) là nghiệm của hệ ràng buộc hiệu Ax ≤ b, và d là hằng số bất kỳ. Khi đó x + d = (x₁ + d, x₂ + d, …, xₙ + d) cũng là nghiệm của Ax ≤ b.

*Chứng minh.* Với mọi xᵢ và xⱼ, (xⱼ + d) − (xᵢ + d) = xⱼ − xᵢ. Vậy nếu x thoả Ax ≤ b thì x + d cũng thoả. ∎

Hệ ràng buộc hiệu xuất hiện trong nhiều ứng dụng. Ví dụ, ẩn xᵢ có thể là thời điểm xảy ra các sự kiện; mỗi ràng buộc nói rằng giữa hai sự kiện phải cách nhau ít nhất hoặc nhiều nhất một khoảng thời gian. Có thể các sự kiện là công việc khi lắp ráp một sản phẩm. Nếu bôi một loại keo cần 2 giờ để khô vào thời điểm x₁, và phải chờ keo khô mới lắp một bộ phận vào thời điểm x₂, ta có ràng buộc x₂ ≥ x₁ + 2, tương đương x₁ − x₂ ≤ −2. Hoặc ta có thể yêu cầu bộ phận được lắp sau khi bôi keo nhưng không muộn hơn lúc keo khô được một nửa; khi đó có cặp ràng buộc x₂ ≥ x₁ và x₂ ≤ x₁ + 1, tương đương x₁ − x₂ ≤ 0 và x₂ − x₁ ≤ 1.

#### Đồ thị ràng buộc (Constraint graphs)

Có thể nhìn hệ ràng buộc hiệu từ góc độ đồ thị. Trong hệ Ax ≤ b, xem ma trận A cỡ m × n là chuyển vị của ma trận liên thuộc (incidence matrix, Exercise 22.1-7) của một đồ thị n đỉnh, m cạnh. Mỗi đỉnh vᵢ, i = 1, 2, …, n, ứng với một ẩn xᵢ. Mỗi cạnh có hướng ứng với một trong m bất đẳng thức hai ẩn.

Chính xác hơn, cho hệ ràng buộc hiệu Ax ≤ b, **đồ thị ràng buộc** tương ứng là đồ thị có hướng có trọng số G = (V, E) với

```text
V = { v₀, v₁, …, vₙ }
E = { (vᵢ, vⱼ) : xⱼ − xᵢ ≤ bₖ là một ràng buộc }
    ∪ { (v₀, v₁), (v₀, v₂), (v₀, v₃), …, (v₀, vₙ) }
```

Đồ thị có thêm đỉnh v₀ để bảo đảm có một đỉnh đi tới được mọi đỉnh khác. Tập E gồm một cạnh cho mỗi ràng buộc hiệu, cộng một cạnh (v₀, vᵢ) cho mỗi ẩn xᵢ. Nếu xⱼ − xᵢ ≤ bₖ là một ràng buộc thì trọng số cạnh (vᵢ, vⱼ) là w(vᵢ, vⱼ) = bₖ. Mọi cạnh đi ra từ v₀ có trọng số 0. (Lưu ý chiều: ràng buộc "xⱼ trừ xᵢ" cho cạnh từ vᵢ **tới** vⱼ.)

**Đồ thị ràng buộc của hệ (24.3)–(24.10) (Hình 24.8), chép lại:**

| Ràng buộc | Cạnh | Trọng số |
|---|---|---|
| (24.3) x₁ − x₂ ≤ 0 | v₂ → v₁ | 0 |
| (24.4) x₁ − x₅ ≤ −1 | v₅ → v₁ | −1 |
| (24.5) x₂ − x₅ ≤ 1 | v₅ → v₂ | 1 |
| (24.6) x₃ − x₁ ≤ 5 | v₁ → v₃ | 5 |
| (24.7) x₄ − x₁ ≤ 4 | v₁ → v₄ | 4 |
| (24.8) x₄ − x₃ ≤ −1 | v₃ → v₄ | −1 |
| (24.9) x₅ − x₃ ≤ −3 | v₃ → v₅ | −3 |
| (24.10) x₅ − x₄ ≤ −3 | v₄ → v₅ | −3 |
| (thêm) | v₀ → v₁, v₂, v₃, v₄, v₅ | 0 mỗi cạnh |

Giá trị δ(v₀, vᵢ) ghi trong mỗi đỉnh: v₀ 0, v₁ −5, v₂ −3, v₃ 0, v₄ −1, v₅ −4. Người tổng hợp kiểm tra bằng các đường cụ thể: v₃ chỉ có thể đến trực tiếp từ v₀ (0) hoặc từ v₁ (δ(v₁) + 5 = 0), nên δ = 0; v₄: v₀ → v₃ → v₄ nặng −1; v₅: v₀ → v₃ → v₄ → v₅ nặng −1 − 3 = −4 (tốt hơn v₀ → v₃ → v₅ nặng −3); v₁: … → v₅ → v₁ nặng −4 − 1 = −5; v₂: … → v₅ → v₂ nặng −4 + 1 = −3. Nghiệm khả thi là x = (−5, −3, 0, −1, −4).

**Định lý 24.9.** Cho hệ ràng buộc hiệu Ax ≤ b và G = (V, E) là đồ thị ràng buộc tương ứng. Nếu G không có chu trình âm thì

```text
x = ( δ(v₀, v₁), δ(v₀, v₂), δ(v₀, v₃), …, δ(v₀, vₙ) )                (24.11)
```

là một nghiệm khả thi của hệ. Nếu G có chu trình âm thì hệ không có nghiệm khả thi.

*Chứng minh.* Trước hết, nếu đồ thị ràng buộc không có chu trình âm thì (24.11) là nghiệm khả thi. Xét cạnh bất kỳ (vᵢ, vⱼ) ∈ E. Theo bất đẳng thức tam giác, δ(v₀, vⱼ) ≤ δ(v₀, vᵢ) + w(vᵢ, vⱼ), tương đương δ(v₀, vⱼ) − δ(v₀, vᵢ) ≤ w(vᵢ, vⱼ). Vậy đặt xᵢ = δ(v₀, vᵢ) và xⱼ = δ(v₀, vⱼ) thoả ràng buộc hiệu xⱼ − xᵢ ≤ w(vᵢ, vⱼ) ứng với cạnh (vᵢ, vⱼ). (Các giá trị δ đều hữu hạn: không có chu trình âm nên không có −∞, và v₀ đi tới mọi đỉnh nên không có ∞.)

Tiếp theo, nếu đồ thị ràng buộc có chu trình âm thì hệ vô nghiệm. Không mất tổng quát, gọi chu trình âm là c = ⟨v₁, v₂, …, v_k⟩ với v₁ = v_k. (Đỉnh v₀ không thể nằm trên c vì không có cạnh nào đi vào v₀.) Chu trình c ứng với các ràng buộc

```text
x₂ − x₁ ≤ w(v₁, v₂)
x₃ − x₂ ≤ w(v₂, v₃)
  ⋮
x_{k−1} − x_{k−2} ≤ w(v_{k−2}, v_{k−1})
x_k − x_{k−1} ≤ w(v_{k−1}, v_k)
```

Giả sử x có nghiệm thoả cả k bất đẳng thức này, rồi suy ra mâu thuẫn. Nghiệm cũng phải thoả bất đẳng thức tổng của k bất đẳng thức. Cộng các vế trái, mỗi ẩn xᵢ được cộng một lần và trừ một lần (nhớ rằng v₁ = v_k kéo theo x₁ = x_k), nên vế trái tổng bằng 0. Vế phải tổng bằng w(c), nên 0 ≤ w(c). Nhưng c là chu trình âm, w(c) < 0, ta được mâu thuẫn 0 ≤ w(c) < 0. ∎

(Chỗ ký hiệu chồng nhau, nhận xét của người tổng hợp: trong chứng minh này các chỉ số của chu trình v₁, …, v_k được dùng như tên đỉnh tuỳ ý trên chu trình, không phải đúng các đỉnh v₁, v₂ của đồ thị; đọc là "đặt tên lại các đỉnh trên chu trình".)

#### Giải hệ ràng buộc hiệu (Solving systems of difference constraints)

Định lý 24.9 cho thấy có thể dùng Bellman-Ford để giải hệ ràng buộc hiệu. Vì đồ thị ràng buộc có cạnh từ nguồn v₀ tới mọi đỉnh khác, mọi chu trình âm trong đồ thị đều đi tới được từ v₀. Nếu Bellman-Ford trả về TRUE thì các trọng số đường đi ngắn nhất cho một nghiệm khả thi. Ví dụ, với đồ thị trên, nghiệm là x = (−5, −3, 0, −1, −4), và theo Bổ đề 24.8, x = (d − 5, d − 3, d, d − 1, d − 4) cũng là nghiệm với mọi hằng số d. Nếu Bellman-Ford trả về FALSE thì hệ vô nghiệm.

Hệ m ràng buộc trên n ẩn sinh đồ thị n + 1 đỉnh và n + m cạnh. Do đó Bellman-Ford giải hệ trong O((n + 1)(n + m)) = O(n² + nm). Exercise 24.4-5 yêu cầu sửa để chạy trong O(nm), kể cả khi m nhỏ hơn nhiều so với n.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hệ ràng buộc hiệu là lõi của lập lịch dự án có ràng buộc thời gian tối thiểu/tối đa, của "mạng thời gian đơn giản" (simple temporal networks) trong lập kế hoạch AI, của bộ giải "logic hiệu" (difference logic) trong các bộ giải SMT dùng cho kiểm chứng phần mềm, và của bài toán căn thời gian (retiming) mạch số — tất cả đều quy về phát hiện chu trình âm.

### 6. Chứng minh các tính chất của đường đi ngắn nhất (24.5 Proofs of shortest-paths properties, trang 671–677)

Suốt chương, các lập luận về tính đúng dựa vào bất đẳng thức tam giác, tính chất cận trên, không có đường, hội tụ, nới lỏng theo đường, đồ thị con liền trước. Mục này chứng minh chúng.

#### Bất đẳng thức tam giác (The triangle inequality)

Khi nghiên cứu BFS (Mục 22.2), sách đã chứng minh Bổ đề 22.1, một tính chất đơn giản của khoảng cách ngắn nhất trong đồ thị không trọng số. Bất đẳng thức tam giác tổng quát hoá nó cho đồ thị có trọng số.

**Bổ đề 24.10 (Bất đẳng thức tam giác).** Cho G = (V, E) có hướng có trọng số với w: E → ℝ và nguồn s. Khi đó với mọi cạnh (u, v) ∈ E: δ(s, v) ≤ δ(s, u) + w(u, v).

*Chứng minh.* Giả sử p là đường ngắn nhất từ s tới v. Thì p không nặng hơn bất kỳ đường nào khác từ s tới v. Cụ thể, p không nặng hơn đường đi theo một đường ngắn nhất từ s tới u rồi đi cạnh (u, v). Exercise 24.5-3 yêu cầu xử lý trường hợp không có đường ngắn nhất từ s tới v (δ bằng ∞ hoặc −∞). ∎

#### Ảnh hưởng của phép nới lỏng lên ước lượng (Effects of relaxation on shortest-path estimates)

Nhóm bổ đề sau mô tả ước lượng bị ảnh hưởng thế nào khi thực hiện một dãy bước nới lỏng trên đồ thị đã được khởi tạo bằng INITIALIZE-SINGLE-SOURCE.

**Bổ đề 24.11 (Tính chất cận trên).** Cho G = (V, E) có hướng có trọng số với w: E → ℝ, s ∈ V là nguồn, đồ thị được khởi tạo bằng INITIALIZE-SINGLE-SOURCE(G, s). Khi đó v.d ≥ δ(s, v) với mọi v ∈ V, và bất biến này được duy trì qua mọi dãy bước nới lỏng trên các cạnh của G. Hơn nữa, khi v.d đạt cận dưới δ(s, v) thì nó không bao giờ thay đổi.

*Chứng minh.* Chứng minh bất biến v.d ≥ δ(s, v) bằng quy nạp theo số bước nới lỏng.

Cơ sở: sau khởi tạo, v.d ≥ δ(s, v) hiển nhiên đúng, vì v.d = ∞ kéo theo v.d ≥ δ(s, v) với mọi v ∈ V − {s}, và s.d = 0 ≥ δ(s, s) (lưu ý δ(s, s) = −∞ nếu s nằm trên một chu trình âm, và bằng 0 nếu không).

Bước quy nạp: xét việc nới lỏng cạnh (u, v). Theo giả thiết quy nạp, x.d ≥ δ(s, x) với mọi x ∈ V trước khi nới lỏng. Giá trị d duy nhất có thể thay đổi là v.d. Nếu nó thay đổi thì

```text
v.d = u.d + w(u, v)
    ≥ δ(s, u) + w(u, v)     (giả thiết quy nạp)
    ≥ δ(s, v)               (bất đẳng thức tam giác)
```

nên bất biến được giữ.

Để thấy v.d không đổi khi đã bằng δ(s, v): đã đạt cận dưới thì v.d không thể giảm (vừa chứng minh v.d ≥ δ(s, v)), và không thể tăng vì nới lỏng không bao giờ làm tăng giá trị d. ∎

**Hệ quả 24.12 (Tính chất không có đường).** Giả sử trong G = (V, E) có hướng có trọng số với w: E → ℝ, không có đường nối nguồn s ∈ V tới đỉnh v ∈ V. Khi đó sau khi khởi tạo bằng INITIALIZE-SINGLE-SOURCE(G, s), v.d = δ(s, v) = ∞, và đẳng thức này được duy trì như bất biến qua mọi dãy bước nới lỏng.

*Chứng minh.* Theo tính chất cận trên, luôn có ∞ = δ(s, v) ≤ v.d, nên v.d = ∞ = δ(s, v). ∎

**Bổ đề 24.13.** Cho G = (V, E) có hướng có trọng số với w: E → ℝ, và (u, v) ∈ E. Ngay sau khi nới lỏng cạnh (u, v) bằng RELAX(u, v, w), ta có v.d ≤ u.d + w(u, v).

*Chứng minh.* Nếu ngay trước khi nới lỏng có v.d > u.d + w(u, v) thì sau đó v.d = u.d + w(u, v). Nếu thay vào đó v.d ≤ u.d + w(u, v) ngay trước, thì cả u.d lẫn v.d đều không đổi, nên sau đó vẫn v.d ≤ u.d + w(u, v). ∎

**Bổ đề 24.14 (Tính chất hội tụ).** Cho G = (V, E) có hướng có trọng số với w: E → ℝ, s ∈ V là nguồn, và s ⇝ u → v là một đường ngắn nhất trong G với u, v ∈ V nào đó. Giả sử G được khởi tạo bằng INITIALIZE-SINGLE-SOURCE(G, s) rồi một dãy bước nới lỏng có chứa lời gọi RELAX(u, v, w) được thực hiện. Nếu u.d = δ(s, u) tại bất kỳ thời điểm nào trước lời gọi đó, thì v.d = δ(s, v) mọi lúc sau lời gọi.

*Chứng minh.* Theo tính chất cận trên, nếu u.d = δ(s, u) tại một thời điểm trước khi nới lỏng (u, v) thì đẳng thức giữ mãi sau đó. Đặc biệt, sau khi nới lỏng (u, v):

```text
v.d ≤ u.d + w(u, v)          (Bổ đề 24.13)
    = δ(s, u) + w(u, v)
    = δ(s, v)                (Bổ đề 24.1)
```

Theo tính chất cận trên v.d ≥ δ(s, v), nên v.d = δ(s, v), và đẳng thức được duy trì sau đó. ∎

(Bước cuối dùng Bổ đề 24.1: vì s ⇝ u → v là đường ngắn nhất, đoạn s ⇝ u là đường ngắn nhất tới u, nên trọng số cả đường là δ(s, u) + w(u, v) và bằng δ(s, v).)

**Bổ đề 24.15 (Tính chất nới lỏng theo đường).** Cho G = (V, E) có hướng có trọng số với w: E → ℝ, s ∈ V là nguồn. Xét một đường ngắn nhất bất kỳ p = ⟨v₀, v₁, …, v_k⟩ từ s = v₀ tới v_k. Nếu G được khởi tạo bằng INITIALIZE-SINGLE-SOURCE(G, s) rồi một dãy bước nới lỏng xảy ra, trong đó có — theo đúng thứ tự — việc nới lỏng các cạnh (v₀, v₁), (v₁, v₂), …, (v_{k−1}, v_k), thì v_k.d = δ(s, v_k) sau các phép nới lỏng này và mọi lúc sau đó. Tính chất đúng bất kể có những phép nới lỏng cạnh khác nào, kể cả khi chúng xen lẫn với việc nới lỏng các cạnh của p.

*Chứng minh.* Chứng minh bằng quy nạp rằng sau khi cạnh thứ i của p được nới lỏng, vᵢ.d = δ(s, vᵢ). Cơ sở i = 0: trước khi cạnh nào của p được nới lỏng, từ khởi tạo có v₀.d = s.d = 0 = δ(s, s). Theo tính chất cận trên, s.d không bao giờ đổi sau khởi tạo. Bước quy nạp: giả sử vᵢ₋₁.d = δ(s, vᵢ₋₁), xét việc nới lỏng cạnh (vᵢ₋₁, vᵢ). Theo tính chất hội tụ, sau khi nới lỏng cạnh này, vᵢ.d = δ(s, vᵢ), và đẳng thức giữ mãi sau đó. ∎

(Lưu ý của người tổng hợp: ở bước cơ sở, δ(s, s) = 0 vì p là đường ngắn nhất nên không có chu trình âm nào đi tới được đỉnh trên p; nếu s nằm trên chu trình âm thì δ(s, s) = −∞ và "đường ngắn nhất" p không tồn tại.)

#### Nới lỏng và cây đường đi ngắn nhất (Relaxation and shortest-paths trees)

Giờ sách chứng minh rằng khi một dãy phép nới lỏng đã làm các ước lượng hội tụ về trọng số đường đi ngắn nhất, đồ thị con liền trước G_π sinh bởi các giá trị π là một cây đường đi ngắn nhất của G. Bắt đầu bằng bổ đề: G_π luôn là một cây có gốc là nguồn.

**Bổ đề 24.16.** Cho G = (V, E) có hướng có trọng số với w: E → ℝ, s ∈ V là nguồn, và giả sử G không có chu trình âm đi tới được từ s. Khi đó sau khi khởi tạo bằng INITIALIZE-SINGLE-SOURCE(G, s), đồ thị con liền trước G_π là một cây có gốc s, và mọi dãy bước nới lỏng trên các cạnh của G duy trì tính chất này như một bất biến.

*Chứng minh.* Ban đầu, đỉnh duy nhất trong G_π là nguồn, bổ đề đúng hiển nhiên. Xét G_π sau một dãy bước nới lỏng.

*Bước 1: G_π không có chu trình.* Giả sử phản chứng một bước nới lỏng tạo ra chu trình trong G_π. Gọi chu trình là c = ⟨v₀, v₁, …, v_k⟩ với v_k = v₀. Khi đó vᵢ.π = vᵢ₋₁ với i = 1, 2, …, k, và không mất tổng quát, giả sử việc nới lỏng cạnh (v_{k−1}, v_k) đã tạo ra chu trình.

Mọi đỉnh trên c đều đi tới được từ s. Vì sao? Mỗi đỉnh trên c có đỉnh liền trước khác NIL, nên mỗi đỉnh được gán một ước lượng hữu hạn khi được gán π khác NIL. Theo tính chất cận trên, mỗi đỉnh trên c có trọng số đường đi ngắn nhất hữu hạn, tức đi tới được từ s.

Xét các ước lượng trên c ngay trước lời gọi RELAX(v_{k−1}, v_k, w) và chỉ ra c là chu trình âm, mâu thuẫn với giả thiết. Ngay trước lời gọi, vᵢ.π = vᵢ₋₁ với i = 1, 2, …, k − 1. Do đó với i = 1, 2, …, k − 1, lần cập nhật cuối cùng của vᵢ.d là phép gán vᵢ.d = vᵢ₋₁.d + w(vᵢ₋₁, vᵢ). Nếu vᵢ₋₁.d thay đổi từ lúc đó thì nó chỉ có thể giảm. Vậy ngay trước lời gọi RELAX(v_{k−1}, v_k, w):

```text
vᵢ.d ≥ vᵢ₋₁.d + w(vᵢ₋₁, vᵢ)    với mọi i = 1, 2, …, k − 1        (24.12)
```

Vì v_k.π bị lời gọi thay đổi, ngay trước đó còn có bất đẳng thức chặt

```text
v_k.d > v_{k−1}.d + w(v_{k−1}, v_k)
```

Cộng bất đẳng thức chặt này với k − 1 bất đẳng thức (24.12), được tổng ước lượng quanh chu trình c:

```text
Σᵢ₌₁ᵏ vᵢ.d > Σᵢ₌₁ᵏ (vᵢ₋₁.d + w(vᵢ₋₁, vᵢ))
           = Σᵢ₌₁ᵏ vᵢ₋₁.d + Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
```

Nhưng Σᵢ₌₁ᵏ vᵢ.d = Σᵢ₌₁ᵏ vᵢ₋₁.d vì mỗi đỉnh của c xuất hiện đúng một lần trong mỗi tổng. Đẳng thức này kéo theo

```text
0 > Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
```

Vậy tổng trọng số quanh c âm — mâu thuẫn mong muốn.

*Bước 2: G_π là cây có gốc s.* Đã chứng minh G_π là đồ thị có hướng không chu trình. Để chứng minh nó là cây có gốc s, chỉ cần (Exercise B.5-2) chứng minh với mỗi đỉnh v ∈ V_π có đúng một đường đơn từ s tới v trong G_π.

Trước hết phải chứng minh tồn tại đường từ s tới mỗi đỉnh trong V_π. Các đỉnh trong V_π là các đỉnh có π khác NIL, cộng s. Ý tưởng là quy nạp; chi tiết để cho Exercise 24.5-6.

Để hoàn tất, phải chứng minh với mọi v ∈ V_π, G_π chứa nhiều nhất một đường đơn từ s tới v. Giả sử ngược lại, G_π chứa hai đường đơn từ s tới v: p₁ tách thành s ⇝ u ⇝ x → z ⇝ v và p₂ tách thành s ⇝ u ⇝ y → z ⇝ v, với x ≠ y (có thể u = s và z = v). Hình 24.9 của sách minh hoạ:

```text
                         ┌──▶ x ──┐
     s ⇝⇝⇝ u ──(nhánh 1)─┘        ▼
               └─(nhánh 2)──▶ y ──▶ z ⇝⇝⇝ v
   (hai đường tách nhau sau u, gặp lại ở z; cạnh vào z là x → z và y → z)
```

Nhưng khi đó z.π = x và z.π = y, kéo theo x = y — mâu thuẫn. Vậy G_π chứa đúng một đường đơn từ s tới v, và G_π là cây có gốc s. ∎

**Bổ đề 24.17 (Tính chất đồ thị con liền trước).** Cho G = (V, E) có hướng có trọng số với w: E → ℝ, s ∈ V là nguồn, và giả sử G không có chu trình âm đi tới được từ s. Gọi INITIALIZE-SINGLE-SOURCE(G, s) rồi thực hiện một dãy bước nới lỏng bất kỳ trên các cạnh của G sao cho v.d = δ(s, v) với mọi v ∈ V. Khi đó G_π là cây đường đi ngắn nhất gốc s.

*Chứng minh.* Phải chứng minh ba tính chất của cây đường đi ngắn nhất (đã nêu ở phần mở đầu) đúng cho G_π.

(1) V_π là tập đỉnh đi tới được từ s. Theo định nghĩa, δ(s, v) hữu hạn khi và chỉ khi v đi tới được từ s, nên các đỉnh đi tới được chính là các đỉnh có d hữu hạn. Nhưng một đỉnh v ∈ V − {s} được gán giá trị hữu hạn cho v.d khi và chỉ khi v.π ≠ NIL. Vậy V_π gồm đúng các đỉnh đi tới được từ s.

(2) G_π là cây có gốc s: suy trực tiếp từ Bổ đề 24.16.

(3) Với mỗi v ∈ V_π, đường đơn duy nhất s ⇝ v (gọi là p) trong G_π là đường ngắn nhất từ s tới v trong G. Đặt p = ⟨v₀, v₁, …, v_k⟩ với v₀ = s và v_k = v. Với i = 1, 2, …, k, có cả vᵢ.d = δ(s, vᵢ) và vᵢ.d ≥ vᵢ₋₁.d + w(vᵢ₋₁, vᵢ), suy ra w(vᵢ₋₁, vᵢ) ≤ δ(s, vᵢ) − δ(s, vᵢ₋₁). Cộng trọng số dọc p:

```text
w(p) = Σᵢ₌₁ᵏ w(vᵢ₋₁, vᵢ)
     ≤ Σᵢ₌₁ᵏ (δ(s, vᵢ) − δ(s, vᵢ₋₁))
     = δ(s, v_k) − δ(s, v₀)           (tổng rút gọn)
     = δ(s, v_k)                      (vì δ(s, v₀) = δ(s, s) = 0)
```

Vậy w(p) ≤ δ(s, v_k). Vì δ(s, v_k) là cận dưới của trọng số mọi đường từ s tới v_k, ta có w(p) = δ(s, v_k), và p là đường ngắn nhất từ s tới v = v_k. ∎

(Về bất đẳng thức vᵢ.d ≥ vᵢ₋₁.d + w(vᵢ₋₁, vᵢ), người tổng hợp giải thích: lần cuối vᵢ.π được gán bằng vᵢ₋₁, vᵢ.d được gán bằng vᵢ₋₁.d + w lúc đó; sau đó vᵢ₋₁.d chỉ có thể giảm, còn nếu vᵢ.d giảm thì vᵢ.π cũng đổi — trái với việc vᵢ.π vẫn là vᵢ₋₁. Đây chính là lập luận của (24.12).)

## Bài tập và bài toán cuối chương

### Bài tập Mục 24.1 (trang 654–655)

- **24.1-1:** Chạy Bellman-Ford trên đồ thị 5 đỉnh của ví dụ Mục 24.1 (các cạnh s→t 6, s→y 7, t→x 5, x→t −2, t→y 8, t→z −4, y→x −3, y→z 9, z→x 7, z→s 2), lấy z làm nguồn, mỗi lượt nới lỏng cạnh theo cùng thứ tự (t, x), (t, y), (t, z), (x, t), (y, x), (y, z), (z, x), (z, s), (s, t), (s, y), ghi d và π sau mỗi lượt. Rồi đổi trọng số cạnh (z, x) thành 4 và chạy lại với nguồn s. *Lời giải của người tổng hợp:*

  Phần 1, nguồn z:

  | Sau lượt | s | t | x | y | z | Thay đổi trong lượt |
  |---|---|---|---|---|---|---|
  | 0 (khởi tạo) | ∞ | ∞ | ∞ | ∞ | 0 | — |
  | 1 | 2 (π z) | 8 (π s) | 7 (π z) | 9 (π s) | 0 | (z, x): x = 7; (z, s): s = 2; (s, t): t = 8; (s, y): y = 9 |
  | 2 | 2 | 5 (π x) | 6 (π y) | 9 | 0 | (x, t): t = 7 − 2 = 5; (y, x): x = 9 − 3 = 6 |
  | 3 | 2 | 4 (π x) | 6 | 9 | 0 | (x, t): t = 6 − 2 = 4 |
  | 4 | 2 | 4 | 6 | 9 | 0 | không đổi ((t, z): 4 − 4 = 0, không nhỏ hơn 0) |

  Kiểm tra cuối không có cạnh nào nới lỏng được, trả về TRUE. Cây: z → s → y → x → t.

  Phần 2, w(z, x) = 4, nguồn s:

  | Sau lượt | s | t | x | y | z | Thay đổi trong lượt |
  |---|---|---|---|---|---|---|
  | 0 | 0 | ∞ | ∞ | ∞ | ∞ | — |
  | 1 | 0 | 6 | ∞ | 7 | ∞ | (s, t), (s, y) |
  | 2 | 0 | 6 | 4 (π y) | 7 | 2 (π t) | (t, x): x = 11; (t, z): z = 2; (y, x): x = 4; (z, x): 2 + 4 = 6 không nhỏ hơn 4 |
  | 3 | 0 | 2 (π x) | 4 | 7 | 2 | (x, t): t = 2 |
  | 4 | 0 | 2 | 2 (π z) | 7 | −2 (π t) | (t, z): z = −2; (z, x): x = −2 + 4 = 2 |

  Kiểm tra: cạnh (t, x) cho 2 + 5 = 7 ≥ 2, không vi phạm; (t, z) cho 2 − 4 = −2, không vi phạm; (x, t) cho 2 − 2 = 0 < t.d = 2, vi phạm ⇒ trả về FALSE. Nguyên nhân: chu trình x → t → z → x nặng −2 − 4 + 4 = −2.
- **24.1-2:** Chứng minh Hệ quả 24.3. *Người tổng hợp:* (⇒) nếu v đi tới được từ s thì Bổ đề 24.2 cho v.d = δ(s, v), mà δ(s, v) hữu hạn (có đường và không có chu trình âm). (⇐) nếu không có đường thì theo tính chất không có đường v.d = ∞; vậy v.d < ∞ kéo theo có đường.
- **24.1-3:** Cho G không có chu trình âm, gọi m là giá trị lớn nhất, trên mọi đỉnh v, của số cạnh tối thiểu trong một đường ngắn nhất (theo trọng số) từ s tới v. Đề xuất một thay đổi đơn giản để Bellman-Ford dừng sau m + 1 lượt, kể cả khi không biết trước m. *Người tổng hợp:* sau mỗi lượt kiểm tra xem có d nào thay đổi không; nếu một lượt không đổi gì thì dừng. Sau m lượt mọi d đã đúng (tính chất nới lỏng theo đường), lượt m + 1 không đổi gì nên thuật toán dừng. (Nếu cần phát hiện chu trình âm thì vẫn giới hạn tối đa |V| − 1 lượt cộng lượt kiểm tra.)
- **24.1-4:** Sửa Bellman-Ford để gán v.d = −∞ cho mọi đỉnh v có chu trình âm trên một đường nào đó từ s tới v. *Người tổng hợp:* sau |V| − 1 lượt, đánh dấu mọi đỉnh v có cạnh (u, v) còn nới lỏng được; mỗi chu trình âm đi tới được chứa ít nhất một đỉnh như vậy (lập luận cộng quanh chu trình của Định lý 24.4). Chạy BFS/DFS từ mọi đỉnh được đánh dấu và gán −∞ cho mọi đỉnh tới được. Thời gian thêm O(V + E), tổng O(VE).
- **24.1-5 (★):** Cho G = (V, E) có hướng có trọng số. Thiết kế thuật toán O(VE) tính với mỗi v giá trị δ*(v) = min_{u ∈ V} δ(u, v). *Người tổng hợp:* thêm đỉnh mới s′ với cạnh trọng số 0 tới mọi đỉnh, chạy Bellman-Ford từ s′. Khi đó δ(s′, v) = min(0, min_u δ(u, v)) = δ*(v), vì δ(v, v) = 0 (không có chu trình âm) đã làm min ≤ 0. Nếu có chu trình âm, kết hợp với Exercise 24.1-4 để gán −∞.
- **24.1-6 (★):** G có chu trình âm; cho thuật toán hiệu quả liệt kê các đỉnh của một chu trình âm như vậy và chứng minh đúng. *Người tổng hợp:* thêm nguồn ảo s′ nối mọi đỉnh bằng cạnh 0 (để mọi chu trình đều đi tới được), chạy |V| lượt; ở lượt cuối, lấy một đỉnh v vừa bị giảm d. Đi ngược π từ v đúng |V| bước để chắc chắn rơi vào chu trình trong G_π (một dãy đỉnh liền trước dài |V| phải lặp đỉnh), gọi đỉnh đó là x; tiếp tục đi ngược π từ x tới khi gặp lại x, các đỉnh đã qua là một chu trình. Chu trình trong G_π luôn âm (lập luận của Bổ đề 24.16, phần chứng minh G_π không có chu trình khi không có chu trình âm). Thời gian O(VE).

### Bài tập Mục 24.2 (trang 657–658)

- **24.2-1:** Chạy DAG-SHORTEST-PATHS trên đồ thị 6 đỉnh của ví dụ Mục 24.2 (thứ tự tô-pô r, s, t, x, y, z; cạnh r→s 5, r→t 3, s→t 2, s→x 6, t→x 7, t→y 4, t→z 2, x→y −1, x→z 1, y→z −2) với nguồn r. *Lời giải của người tổng hợp:*

  | Đỉnh xử lý | r | s | t | x | y | z |
  |---|---|---|---|---|---|---|
  | khởi tạo | 0 | ∞ | ∞ | ∞ | ∞ | ∞ |
  | r | 0 | 5 (π r) | 3 (π r) | ∞ | ∞ | ∞ |
  | s | 0 | 5 | 3 (5 + 2 = 7 không tốt hơn) | 11 (π s) | ∞ | ∞ |
  | t | 0 | 5 | 3 | 10 (π t) | 7 (π t) | 5 (π t) |
  | x | 0 | 5 | 3 | 10 | 7 (10 − 1 = 9 không tốt hơn) | 5 (11 không tốt hơn) |
  | y | 0 | 5 | 3 | 10 | 7 | 5 (7 − 2 = 5 không nhỏ hơn) |
  | z | 0 | 5 | 3 | 10 | 7 | 5 |

- **24.2-2:** Nếu đổi dòng 3 thành "for the first |V| − 1 vertices, taken in topologically sorted order" (chỉ xử lý |V| − 1 đỉnh đầu theo thứ tự tô-pô), chứng minh thủ tục vẫn đúng. *Người tổng hợp:* đỉnh cuối cùng trong thứ tự tô-pô không có cạnh đi ra (mọi cạnh ra từ nó phải tới một đỉnh đứng sau), nên xử lý nó không nới lỏng gì.
- **24.2-3:** Cách mô hình PERT ở trên hơi gượng. Tự nhiên hơn: đỉnh là công việc, cạnh (u, v) nghĩa là u phải làm xong trước v, và gán trọng số cho đỉnh chứ không cho cạnh. Sửa DAG-SHORTEST-PATHS để tìm đường dài nhất trong dag có trọng số đỉnh trong thời gian tuyến tính. *Người tổng hợp:* khởi tạo v.d = w(v) cho mọi đỉnh (mỗi công việc có thể bắt đầu đường), xử lý theo thứ tự tô-pô, với mỗi cạnh (u, v): nếu v.d < u.d + w(v) thì v.d = u.d + w(v), v.π = u. Đáp án là max_v v.d. Tương đương: tách mỗi đỉnh v thành v_in → v_out với trọng số cạnh w(v). Θ(V + E).
- **24.2-4:** Cho thuật toán hiệu quả đếm tổng số đường đi trong một dag và phân tích. *Người tổng hợp:* theo thứ tự tô-pô, đặt c(v) = 1 + Σ_{(u, v) ∈ E} c(u) (số đường kết thúc tại v, kể cả đường chỉ gồm v). Tổng số đường có ít nhất một cạnh là Σ_v (c(v) − 1). Θ(V + E) phép cộng (các số có thể rất lớn — tới cỡ 2^V — nên chi phí mỗi phép cộng không còn là hằng số nếu tính theo bit). Ví dụ dag a → b, a → c, b → c: c(a) = 1, c(b) = 2, c(c) = 1 + 1 + 2 = 4; số đường có cạnh là 0 + 1 + 3 = 4 (a→b, a→c, b→c, a→b→c).

### Bài tập Mục 24.3 (trang 662–664)

- **24.3-1:** Chạy Dijkstra trên đồ thị 5 đỉnh ở phần mở đầu chương (cạnh s→t 3, s→y 5, t→x 6, t→y 2, y→t 1, y→x 4, y→z 6, x→z 2, z→x 7, z→s 3), trước với nguồn s, sau với nguồn z; ghi d, π và S sau mỗi vòng while. *Lời giải của người tổng hợp:*

  Nguồn s:

  | Lấy ra | S | s | t | x | y | z |
  |---|---|---|---|---|---|---|
  | s | {s} | 0 | 3 (π s) | ∞ | 5 (π s) | ∞ |
  | t | {s, t} | 0 | 3 | 9 (π t) | 5 (3 + 2 = 5 không nhỏ hơn) | ∞ |
  | y | {s, t, y} | 0 | 3 | 9 (5 + 4 = 9 không nhỏ hơn) | 5 | 11 (π y) |
  | x | {s, t, y, x} | 0 | 3 | 9 | 5 | 11 (9 + 2 = 11 không nhỏ hơn) |
  | z | V | 0 | 3 | 9 | 5 | 11 |

  Nguồn z:

  | Lấy ra | S | s | t | x | y | z |
  |---|---|---|---|---|---|---|
  | z | {z} | 3 (π z) | ∞ | 7 (π z) | ∞ | 0 |
  | s | {z, s} | 3 | 6 (π s) | 7 | 8 (π s) | 0 |
  | t | {z, s, t} | 3 | 6 | 7 (6 + 6 = 12) | 8 (6 + 2 = 8 không nhỏ hơn) | 0 |
  | x | {z, s, t, x} | 3 | 6 | 7 | 8 | 0 |
  | y | V | 3 | 6 | 7 | 8 | 0 |

- **24.3-2:** Cho ví dụ đơn giản về đồ thị có cạnh âm mà Dijkstra cho kết quả sai; vì sao chứng minh Định lý 24.6 không còn đúng? *Người tổng hợp:* cạnh s→a 1, s→b 5, b→a −10, a→c 1. Dijkstra lấy s, rồi a (d = 1) và nới lỏng a→c cho c.d = 2, rồi c (d = 2), rồi b (d = 5) và nới lỏng b→a cho a.d = −5. Nhưng c đã ra khỏi hàng đợi với c.d = 2, trong khi δ(s, c) = 5 − 10 + 1 = −4. Chứng minh hỏng ở bước δ(s, y) ≤ δ(s, u): đoạn p₂ có thể nặng âm.
- **24.3-3:** Đổi dòng 4 thành "while |Q| > 1", vòng lặp chạy |V| − 1 lần thay vì |V| lần. Thuật toán còn đúng không? *Người tổng hợp:* đúng. Đỉnh cuối cùng u còn lại trong Q đã có u.d = δ(s, u) theo lập luận của Định lý 24.6 (áp dụng cho thời điểm nó sẽ được chọn); nới lỏng các cạnh ra từ nó chỉ có thể làm giảm d của những đỉnh đã ở S, mà các d đó đã bằng δ nên không giảm được nữa (tính chất cận trên).
- **24.3-4:** Giáo sư Gaedel viết chương trình tự nhận là cài Dijkstra, cho ra v.d và v.π. Cho thuật toán O(V + E) kiểm tra xem d và π có khớp với một cây đường đi ngắn nhất nào đó không (trọng số không âm). *Người tổng hợp:* kiểm tra (1) s.d = 0 và s.π = NIL; (2) với mọi v ≠ s: v.d = ∞ khi và chỉ khi v.π = NIL, và nếu v.π = u ≠ NIL thì (u, v) ∈ E và v.d = u.d + w(u, v); (3) với mọi cạnh (u, v): v.d ≤ u.d + w(u, v); (4) G_π không có chu trình (DFS từ s qua các cạnh π phải chạm đủ mọi đỉnh có π ≠ NIL). Điều kiện (3) cùng s.d = 0 cho d ≤ δ; điều kiện (2) và (4) cho mỗi d là trọng số của một đường thật nên d ≥ δ; vậy d = δ và G_π là cây đường đi ngắn nhất. (Điều kiện (4) cần vì với cạnh trọng số 0 có thể có chu trình π thoả (2).)
- **24.3-5:** Giáo sư Newman cho rằng Dijkstra nới lỏng cạnh của mọi đường ngắn nhất theo đúng thứ tự trên đường, nên tính chất nới lỏng theo đường áp dụng cho mọi đỉnh. Dựng đồ thị cho thấy Dijkstra có thể nới lỏng các cạnh của một đường ngắn nhất sai thứ tự. *Người tổng hợp:* cạnh s→a 1, s→b 1, a→b 0, b→c 1. Đường s → a → b → c (trọng số 2) là đường ngắn nhất. Sau khi lấy s, cả a và b có d = 1; nếu hàng đợi lấy b trước thì (b, c) được nới lỏng trước (a, b) — sai thứ tự. Kết quả vẫn đúng (c.d = 2) nhờ đường s → b → c, nhưng lập luận của giáo sư không đúng.
- **24.3-6:** Mỗi cạnh (u, v) có độ tin cậy r(u, v) ∈ [0, 1] là xác suất kênh không hỏng, các xác suất độc lập. Tìm đường đáng tin nhất giữa hai đỉnh. *Người tổng hợp:* độ tin cậy của đường là tích các r; tối đa hoá tích tương đương tối thiểu hoá Σ −lg r(u, v), các trọng số này không âm (vì r ≤ 1), nên chạy Dijkstra. Hoặc sửa Dijkstra trực tiếp: khởi tạo s.d = 1, các đỉnh khác 0, dùng hàng đợi lớn nhất, RELAX dùng v.d < u.d · r(u, v). Bỏ cạnh r = 0.
- **24.3-7:** w: E → {1, 2, …, W}, không có hai đỉnh cùng δ từ s. Dựng đồ thị không trọng số G′ = (V ∪ V′, E′) bằng cách thay mỗi cạnh (u, v) bằng w(u, v) cạnh trọng số 1 nối tiếp. G′ có bao nhiêu đỉnh? Chứng minh thứ tự BFS trên G′ tô đen các đỉnh của V trùng với thứ tự Dijkstra lấy các đỉnh của V ra khỏi hàng đợi khi chạy trên G. *Người tổng hợp:* |V| + Σ_{(u,v) ∈ E} (w(u, v) − 1) đỉnh. BFS lấy các đỉnh theo khoảng cách số cạnh không giảm, mà khoảng cách trong G′ của mỗi v ∈ V bằng δ(s, v) trong G; Dijkstra cũng lấy theo δ tăng dần; vì các δ khác nhau đôi một nên hai thứ tự trùng nhau.
- **24.3-8:** w: E → {0, 1, …, W}. Sửa Dijkstra để chạy O(WV + E). *Người tổng hợp:* mọi δ hữu hạn ≤ W(|V| − 1). Dùng mảng thùng (bucket) đánh số 0..W(|V| − 1), mỗi thùng là danh sách móc nối hai chiều các đỉnh có d bằng chỉ số. DECREASE-KEY là chuyển đỉnh giữa hai thùng O(1). EXTRACT-MIN quét con trỏ thùng tăng dần, con trỏ không bao giờ lùi vì giá trị lấy ra đơn điệu tăng. Tổng: O(WV) quét thùng + O(E) nới lỏng + O(V) lấy ra.
- **24.3-9:** Sửa thuật toán ở 24.3-8 để chạy O((V + E) lg W). (Gợi ý: tại mỗi thời điểm, V − S chứa bao nhiêu ước lượng khác nhau?) *Người tổng hợp:* mọi d hữu hạn trong V − S nằm trong đoạn [d_min, d_min + W] (mỗi d = u.d + w với u ∈ S và u.d ≤ d_min), nên có tối đa W + 1 giá trị khác nhau. Giữ một đống nhị phân chứa các giá trị khác nhau đó (mỗi giá trị trỏ tới một thùng); mỗi thao tác O(lg W). Tổng O((V + E) lg W).
- **24.3-10:** Các cạnh đi ra từ s có thể âm, mọi cạnh khác không âm, không có chu trình âm. Chứng minh Dijkstra vẫn đúng. *Người tổng hợp:* trong chứng minh Định lý 24.6, chỉ cần đoạn p₂ (từ y tới u) không có cạnh âm. p₂ không chứa cạnh ra từ s: đường ngắn nhất có thể coi là đường đơn, s chỉ xuất hiện ở đầu, và y ≠ s (s ∈ S). Mọi bước còn lại giữ nguyên.

### Bài tập Mục 24.4 (trang 669–670)

- **24.4-1:** Tìm nghiệm khả thi hoặc chứng minh vô nghiệm cho hệ: x₁ − x₂ ≤ 1, x₁ − x₄ ≤ −4, x₂ − x₃ ≤ 2, x₂ − x₅ ≤ 7, x₂ − x₆ ≤ 5, x₃ − x₆ ≤ 10, x₄ − x₂ ≤ 2, x₅ − x₁ ≤ −1, x₅ − x₄ ≤ 3, x₆ − x₃ ≤ −8. *Lời giải của người tổng hợp:* các cạnh v₂→v₁ 1, v₄→v₁ −4, v₃→v₂ 2, v₅→v₂ 7, v₆→v₂ 5, v₆→v₃ 10, v₂→v₄ 2, v₁→v₅ −1, v₄→v₅ 3, v₃→v₆ −8, cộng v₀ → mọi đỉnh trọng số 0. Tính δ(v₀, ·): v₃ = 0 (v₆ + 10 = 2 không tốt hơn); v₆ = v₃ − 8 = −8; v₂ = v₆ + 5 = −3; v₄ = v₂ + 2 = −1; v₁ = v₄ − 4 = −5; v₅ = v₁ − 1 = −6. Không có chu trình âm (ví dụ v₃ → v₆ → v₃ nặng 2, v₂ → v₄ → v₁ → v₅ → v₂ nặng 2 − 4 − 1 + 7 = 4). Nghiệm x = (−5, −3, 0, −1, −6, −8). Kiểm tra đủ 10 ràng buộc: −2 ≤ 1; −4 ≤ −4; −3 ≤ 2; 3 ≤ 7; 5 ≤ 5; 8 ≤ 10; 2 ≤ 2; −1 ≤ −1; −5 ≤ 3; −8 ≤ −8. Đúng hết.
- **24.4-2:** Tương tự cho hệ: x₁ − x₂ ≤ 4, x₁ − x₅ ≤ 5, x₂ − x₄ ≤ −6, x₃ − x₂ ≤ 1, x₄ − x₁ ≤ 3, x₄ − x₃ ≤ 5, x₄ − x₅ ≤ 10, x₅ − x₃ ≤ −4, x₅ − x₄ ≤ −8. *Lời giải của người tổng hợp:* **vô nghiệm.** Đồ thị ràng buộc có chu trình v₄ → v₂ → v₃ → v₅ → v₁ → v₄ với trọng số −6 + 1 − 4 + 5 + 3 = −1 < 0. Kiểm tra trực tiếp: cộng năm ràng buộc x₂ − x₄ ≤ −6, x₃ − x₂ ≤ 1, x₅ − x₃ ≤ −4, x₁ − x₅ ≤ 5, x₄ − x₁ ≤ 3, vế trái rút gọn thành 0, vế phải −1, được 0 ≤ −1 — vô lý.
- **24.4-3:** Trọng số đường đi ngắn nhất từ đỉnh mới v₀ trong đồ thị ràng buộc có thể dương không? *Người tổng hợp:* không. Luôn có cạnh v₀ → vᵢ trọng số 0, nên δ(v₀, vᵢ) ≤ 0.
- **24.4-4:** Biểu diễn bài toán đường đi ngắn nhất một cặp (s, t) thành quy hoạch tuyến tính. *Người tổng hợp:* biến d_v cho mỗi đỉnh; tối đa hoá d_t với các ràng buộc d_v − d_u ≤ w(u, v) cho mọi cạnh (u, v) và d_s = 0. Giá trị tối ưu là δ(s, t) (nghiệm tối ưu bị chặn trên bởi trọng số mọi đường, và nghiệm d = δ đạt được). (Cách khác: biến luồng x_e ≥ 0, tối thiểu hoá Σ w_e x_e với bảo toàn luồng một đơn vị từ s tới t.)
- **24.4-5:** Sửa nhẹ Bellman-Ford để giải hệ m ràng buộc trên n ẩn trong O(nm). *Người tổng hợp:* không dựng n cạnh từ v₀; khởi tạo thẳng vᵢ.d = 0 cho mọi i (đúng bằng kết quả của việc nới lỏng các cạnh từ v₀ ở lượt đầu), rồi mỗi lượt chỉ nới lỏng m cạnh ràng buộc. Cần n − 1 lượt (đường ngắn nhất trong đồ thị n + 1 đỉnh có ≤ n cạnh, cạnh đầu từ v₀ đã được "nới lỏng sẵn", còn lại ≤ n − 1 cạnh ràng buộc) cộng một lượt kiểm tra: O(nm).
- **24.4-6:** Thêm ràng buộc đẳng thức xᵢ = xⱼ + bₖ. *Người tổng hợp:* thay bằng hai ràng buộc hiệu xᵢ − xⱼ ≤ bₖ và xⱼ − xᵢ ≤ −bₖ, tức hai cạnh vⱼ → vᵢ trọng số bₖ và vᵢ → vⱼ trọng số −bₖ.
- **24.4-7:** Giải hệ ràng buộc hiệu bằng thuật toán kiểu Bellman-Ford trên đồ thị ràng buộc không có đỉnh v₀. *Người tổng hợp:* như 24.4-5: khởi tạo mọi d = 0 (không có π), chạy n − 1 lượt trên m cạnh rồi kiểm tra; kết quả giống hệt khi có v₀.
- **24.4-8 (★):** Chứng minh Bellman-Ford chạy trên đồ thị ràng buộc tối đa hoá Σᵢ₌₁ⁿ xᵢ với ràng buộc Ax ≤ b và xᵢ ≤ 0 với mọi i. *Người tổng hợp:* lời giải x = δ(v₀, ·) thoả xᵢ ≤ 0 (Exercise 24.4-3). Với nghiệm khả thi x bất kỳ có x ≤ 0, xét đường ngắn nhất v₀ → v_{a} → … → vᵢ; cạnh đầu ứng với "ràng buộc" x_a − 0 ≤ 0, các cạnh sau ứng với các ràng buộc của hệ; cộng dọc đường được xᵢ ≤ δ(v₀, vᵢ). Vậy δ lớn nhất theo từng thành phần, nên tổng lớn nhất.
- **24.4-9 (★):** Chứng minh Bellman-Ford trên đồ thị ràng buộc tối thiểu hoá (max{xᵢ} − min{xᵢ}) với Ax ≤ b; giải thích vì sao hữu ích khi lập lịch công việc xây dựng. *Người tổng hợp:* với nghiệm δ, max δ = 0 hoặc đạt tại một đỉnh có δ = 0. Gọi vⱼ là đỉnh có δ nhỏ nhất; đường ngắn nhất từ v₀ tới vⱼ đi qua cạnh v₀ → vᵢ rồi các cạnh ràng buộc, và theo cấu trúc con tối ưu δ(v₀, vᵢ) = 0. Với mọi nghiệm x, cộng các ràng buộc dọc đoạn từ vᵢ tới vⱼ được xⱼ − xᵢ ≤ δ(vⱼ) − 0, nên max x − min x ≥ xᵢ − xⱼ ≥ −δ(vⱼ) = max δ − min δ. Ý nghĩa: nếu xᵢ là thời điểm bắt đầu các công việc, nghiệm của Bellman-Ford cho lịch có tổng thời gian từ việc đầu tới việc cuối ngắn nhất.
- **24.4-10:** Mỗi hàng của A là một ràng buộc hiệu, hoặc ràng buộc một biến xᵢ ≤ bₖ, hoặc −xᵢ ≤ bₖ. Sửa Bellman-Ford để giải. *Người tổng hợp:* coi v₀ là một biến x₀ cố định bằng 0: xᵢ ≤ bₖ là xᵢ − x₀ ≤ bₖ (cạnh v₀ → vᵢ trọng số bₖ, thay cạnh 0 nếu bₖ nhỏ hơn), −xᵢ ≤ bₖ là x₀ − xᵢ ≤ bₖ (cạnh vᵢ → v₀ trọng số bₖ). Chạy Bellman-Ford từ v₀; nếu không có chu trình âm thì δ(v₀, v₀) = 0 nên xᵢ = δ(v₀, vᵢ) là nghiệm với x₀ = 0 đúng như yêu cầu.
- **24.4-11:** b thực, mọi ẩn phải nguyên. *Người tổng hợp:* với xᵢ, xⱼ nguyên, xⱼ − xᵢ ≤ bₖ tương đương xⱼ − xᵢ ≤ ⌊bₖ⌋. Thay mọi bₖ bằng ⌊bₖ⌋ rồi chạy Bellman-Ford; mọi δ là tổng các số nguyên nên nguyên.
- **24.4-12 (★):** b thực, chỉ một tập con các ẩn phải nguyên. *Ý của người tổng hợp (không chắc là lời giải mẫu):* chạy Bellman-Ford với phép nới lỏng sửa đổi: khi đỉnh đích vⱼ ứng với ẩn phải nguyên thì gán vⱼ.d = ⌊u.d + w(u, vⱼ)⌋. Các ước lượng vẫn giảm đơn điệu và luôn là cận trên của mọi nghiệm khả thi x ≤ 0 (vì nếu xⱼ nguyên và xⱼ ≤ u.d + w thì xⱼ ≤ ⌊u.d + w⌋). Nếu quá trình ổn định thì d là nghiệm; nếu một ước lượng xuống dưới một ngưỡng hữu hạn tính được (ví dụ −(n · Σ|bₖ| + n)) thì vô nghiệm. Cần thêm lập luận về số lượt để có thời gian đa thức.

### Bài tập Mục 24.5 (trang 676–677)

- **24.5-1:** Cho hai cây đường đi ngắn nhất khác hai cây đã cho của đồ thị 5 đỉnh ở phần mở đầu (các cạnh liệt kê ở Exercise 24.3-1). *Lời giải của người tổng hợp:* y chọn cha trong {s, t}, x trong {t, y}, z trong {y, x} (các cạnh "chặt"). Hai cây sách đã cho là (y:s, x:t, z:y) và (y:t, x:y, z:x). Hai cây khác: {s→t, s→y, y→x, x→z} và {s→t, t→y, t→x, y→z}. (Tổng cộng có 8 cây.)
- **24.5-2:** Cho ví dụ đồ thị có hướng có trọng số và nguồn s sao cho mỗi cạnh (u, v) vừa thuộc một cây đường đi ngắn nhất gốc s nào đó vừa không thuộc một cây khác. *Người tổng hợp:* đỉnh s, a, b; cạnh s→a 1, s→b 1, a→b 0, b→a 0. Ba cây: {s→a, s→b}, {s→a, a→b}, {s→b, b→a}. Mỗi cạnh đều có mặt ở ít nhất một cây và vắng ở ít nhất một cây.
- **24.5-3:** Bổ sung chứng minh Bổ đề 24.10 cho trường hợp δ bằng ∞ hoặc −∞. *Người tổng hợp:* nếu δ(s, u) = ∞ thì vế phải ∞, đúng. Nếu δ(s, u) = −∞ thì có đường tới u qua chu trình âm, nối thêm cạnh (u, v) được đường tới v qua chu trình âm, nên δ(s, v) = −∞, đúng. Nếu δ(s, u) hữu hạn và δ(s, v) = −∞ thì đúng hiển nhiên; δ(s, v) = ∞ là không thể vì v đi tới được qua u.
- **24.5-4:** Chứng minh: nếu một dãy nới lỏng đặt s.π khác NIL thì G có chu trình âm. *Người tổng hợp:* s.π đổi nghĩa là s.d giảm xuống dưới 0. Mỗi giá trị d hữu hạn là trọng số của một đường đi (có thể lặp đỉnh) từ s, nên có đường khép kín từ s về s với trọng số < 0; một đường khép kín âm luôn chứa một chu trình âm.
- **24.5-5:** G không có cạnh âm. Nếu cho phép v.π là đỉnh liền trước của v trên *bất kỳ* đường ngắn nhất nào từ s, hãy cho ví dụ đồ thị và cách gán π tạo chu trình trong G_π. *Người tổng hợp:* cạnh s→a 1, s→b 1, a→b 0, b→a 0. s → b → a là đường ngắn nhất tới a nên cho phép a.π = b; s → a → b là đường ngắn nhất tới b nên cho phép b.π = a; G_π có chu trình a ⇄ b. (Theo Bổ đề 24.16, không dãy nới lỏng nào tạo ra cách gán này.)
- **24.5-6:** G không có chu trình âm. Chứng minh với mọi v ∈ V_π có đường từ s tới v trong G_π và tính chất được duy trì qua mọi dãy nới lỏng. *Người tổng hợp:* quy nạp theo số phép nới lỏng. Khi RELAX(u, v, w) gán v.π = u thì u.d hữu hạn nên u = s hoặc u.π ≠ NIL, tức u ∈ V_π và có đường s ⇝ u trong G_π; thêm cạnh (u, v) được đường tới v. Các đỉnh khác có đường đi qua v vẫn có đường, vì đường tới v được thay chứ không mất, và G_π không có chu trình (Bổ đề 24.16) nên đường mới tới v không đi qua chính những đỉnh đó.
- **24.5-7:** G không có chu trình âm. Chứng minh tồn tại một dãy |V| − 1 phép nới lỏng làm v.d = δ(s, v) với mọi v. *Người tổng hợp:* lấy một cây đường đi ngắn nhất (tồn tại khi không có chu trình âm), nới lỏng các cạnh của cây theo thứ tự duyệt BFS hoặc tiền thứ tự từ gốc; cây có ≤ |V| − 1 cạnh, và mỗi đỉnh nhận được đúng giá trị nhờ tính chất hội tụ. Các đỉnh không đi tới được giữ ∞ = δ.
- **24.5-8:** G có chu trình âm đi tới được từ s. Dựng một dãy vô hạn phép nới lỏng sao cho mỗi phép đều làm thay đổi một ước lượng. *Người tổng hợp:* nới lỏng các cạnh của một đường từ s tới một đỉnh trên chu trình c (mỗi phép đổi ∞ thành giá trị hữu hạn — nếu đỉnh đã có giá trị nhỏ hơn thì bỏ qua cạnh đó). Sau đó lặp mãi: vì Σ w(c) < 0, cộng quanh chu trình như ở Định lý 24.4 cho thấy luôn có ít nhất một cạnh (vᵢ₋₁, vᵢ) của c thoả vᵢ.d > vᵢ₋₁.d + w; nới lỏng cạnh đó (làm thay đổi vᵢ.d), lặp lại.

### Problem 24-1: Cải tiến của Yen cho Bellman-Ford (Yen's improvement to Bellman-Ford)

Trước lượt đầu, gán một thứ tự tuyến tính tuỳ ý v₁, v₂, …, v_{|V|} cho các đỉnh. Chia E thành E_f ∪ E_b với E_f = {(vᵢ, vⱼ) ∈ E : i < j} và E_b = {(vᵢ, vⱼ) ∈ E : i > j} (giả sử không có khuyên). Đặt G_f = (V, E_f), G_b = (V, E_b).

- **(a)** Chứng minh G_f không chu trình với thứ tự tô-pô ⟨v₁, …, v_{|V|}⟩, và G_b không chu trình với thứ tự tô-pô ⟨v_{|V|}, …, v₁⟩. (*Người tổng hợp:* mọi cạnh của E_f đi từ chỉ số nhỏ tới lớn, nên dọc một đường chỉ số tăng chặt, không thể quay về; tương tự cho E_b.)
- Cài mỗi lượt Bellman-Ford như sau: thăm các đỉnh theo thứ tự v₁, …, v_{|V|}, nới lỏng các cạnh E_f đi ra từ đỉnh đó; rồi thăm theo thứ tự v_{|V|}, …, v₁, nới lỏng các cạnh E_b đi ra.
- **(b)** Chứng minh với cách này, nếu G không có chu trình âm đi tới được từ s thì chỉ sau ⌈|V|/2⌉ lượt, v.d = δ(s, v) với mọi v. (*Người tổng hợp:* một đường ngắn nhất đơn có ≤ |V| − 1 cạnh, chia thành các khúc liên tiếp chỉ gồm cạnh E_f hoặc chỉ gồm cạnh E_b. Mỗi nửa lượt là DAG-SHORTEST-PATHS trên G_f hoặc G_b, nên nới lỏng trọn một khúc theo đúng thứ tự. Một lượt xử lý một khúc E_f và một khúc E_b kế tiếp. Số khúc ≤ |V| − 1, nên số lượt ≤ ⌈(|V| − 1)/2⌉ ≤ ⌈|V|/2⌉; áp dụng tính chất nới lỏng theo đường.)
- **(c)** Cách này có cải thiện thời gian tiệm cận của Bellman-Ford không? (*Người tổng hợp:* không; vẫn O(VE), chỉ giảm hằng số khoảng một nửa.)

### Problem 24-2: Hộp lồng nhau (Nesting boxes)

Hộp d chiều kích thước (x₁, …, x_d) **lồng** trong hộp (y₁, …, y_d) nếu có hoán vị π của {1, …, d} sao cho x_{π(1)} < y₁, x_{π(2)} < y₂, …, x_{π(d)} < y_d.

- **(a)** Lập luận quan hệ lồng có tính bắc cầu. (*Người tổng hợp:* nếu X lồng trong Y qua π và Y lồng trong Z qua σ thì X lồng trong Z qua hoán vị hợp π ∘ σ: x_{π(σ(i))} < y_{σ(i)} < z_i.)
- **(b)** Mô tả cách hiệu quả kiểm tra một hộp có lồng trong hộp kia không. (*Người tổng hợp:* sắp xếp kích thước của mỗi hộp tăng dần rồi so từng cặp: X lồng trong Y khi và chỉ khi x₍ᵢ₎ < y₍ᵢ₎ với mọi i (lập luận đổi chỗ). O(d lg d).)
- **(c)** Cho n hộp d chiều {B₁, …, Bₙ}, tìm dãy dài nhất ⟨B_{i₁}, …, B_{i_k}⟩ sao cho B_{iⱼ} lồng trong B_{iⱼ₊₁}. Biểu diễn thời gian theo n và d. (*Người tổng hợp:* sắp xếp kích thước từng hộp O(nd lg d); dựng dag có cạnh Bᵢ → Bⱼ khi Bᵢ lồng trong Bⱼ, kiểm tra mọi cặp O(n²d); tìm đường dài nhất (theo số đỉnh) trong dag bằng DAG-SHORTEST-PATHS với trọng số −1, hoặc sắp các hộp theo kích thước nhỏ nhất rồi quy hoạch động, O(n²). Tổng O(nd lg d + n²d).)

### Problem 24-3: Kinh doanh chênh lệch tỷ giá (Arbitrage)

**Kinh doanh chênh lệch** là dùng sự chênh lệch giữa các tỷ giá để biến một đơn vị tiền thành hơn một đơn vị của chính đồng tiền đó. Ví dụ: 1 đô la Mỹ mua được 49 rupee Ấn Độ, 1 rupee mua được 2 yên Nhật, 1 yên mua được 0,0107 đô la. Đổi vòng, từ 1 đô la được 49 × 2 × 0,0107 = 1,0486 đô la, lãi 4,86%. (Người tổng hợp kiểm tra: 49 × 2 = 98; 98 × 0,0107 = 1,0486.)

Cho n đồng tiền c₁, …, cₙ và bảng tỷ giá R cỡ n × n: một đơn vị cᵢ mua được R[i, j] đơn vị cⱼ.

- **(a)** Thuật toán hiệu quả xác định có dãy ⟨c_{i₁}, …, c_{i_k}⟩ với R[i₁, i₂] · R[i₂, i₃] ⋯ R[i_{k−1}, i_k] · R[i_k, i₁] > 1 hay không; phân tích thời gian. (*Người tổng hợp:* đặt trọng số cạnh (i, j) là −ln R[i, j]. Tích > 1 ⇔ Σ ln R > 0 ⇔ Σ (−ln R) < 0 ⇔ chu trình âm. Thêm nguồn ảo nối mọi đỉnh bằng cạnh 0, chạy Bellman-Ford: V = n + 1, E ≈ n², thời gian O(n³).)
- **(b)** In ra một dãy như vậy nếu có; phân tích. (*Người tổng hợp:* dùng cách của Exercise 24.1-6: lấy một đỉnh bị nới lỏng ở lượt kiểm tra, đi ngược π n lần để vào chu trình, rồi đi tiếp tới khi lặp lại; in theo thứ tự ngược. O(n³).)

### Problem 24-4: Thuật toán co giãn của Gabow cho đường đi ngắn nhất từ một nguồn (Gabow's scaling algorithm)

Một **thuật toán co giãn** (scaling) giải bài toán bằng cách ban đầu chỉ xét bit cao nhất của mỗi giá trị đầu vào (như trọng số cạnh), rồi tinh chỉnh lời giải bằng hai bit cao nhất, và cứ thế xét thêm bit, tinh chỉnh mỗi lần, cho tới khi đã xét mọi bit và có lời giải đúng.

Cho G = (V, E) có hướng với trọng số nguyên không âm w, W = max_{(u,v) ∈ E} w(u, v). Mục tiêu: thuật toán O(E lg W). Giả sử mọi đỉnh đi tới được từ nguồn. Gọi k = ⌈lg(W + 1)⌉ là số bit biểu diễn W, và với i = 1, …, k, đặt wᵢ(u, v) = ⌊w(u, v)/2^{k−i}⌋ — phiên bản "thu nhỏ" của w gồm i bit cao nhất (nên w_k = w). Ví dụ k = 5, w(u, v) = 25 = ⟨11001⟩ thì w₃(u, v) = ⟨110⟩ = 6; với k = 5, w(u, v) = ⟨00100⟩ = 4 thì w₃(u, v) = ⟨001⟩ = 1. (Người tổng hợp kiểm tra: ⌊25/4⌋ = 6, ⌊4/4⌋ = 1.) Gọi δᵢ(u, v) là trọng số đường đi ngắn nhất theo wᵢ; δ_k = δ. Thuật toán tính δ₁(s, ·), rồi δ₂(s, ·), …, tới δ_k(s, ·). Giả sử |E| ≥ |V| − 1; tính δᵢ từ δᵢ₋₁ tốn O(E), nên cả thuật toán O(kE) = O(E lg W).

- **(a)** Giả sử δ(s, v) ≤ |E| với mọi v. Chứng minh tính được mọi δ(s, v) trong O(E). (*Người tổng hợp:* Dijkstra với mảng thùng 0..|E| như Exercise 24.3-8: O(V + E) = O(E).)
- **(b)** Chứng minh tính được δ₁(s, v) trong O(E). (*Người tổng hợp:* w₁ ∈ {0, 1}, nên δ₁ ≤ |V| − 1 ≤ |E|; áp dụng (a).)
- **(c)** Chứng minh với i = 2, …, k: wᵢ(u, v) = 2wᵢ₋₁(u, v) hoặc 2wᵢ₋₁(u, v) + 1; rồi chứng minh 2δᵢ₋₁(s, v) ≤ δᵢ(s, v) ≤ 2δᵢ₋₁(s, v) + |V| − 1. (*Người tổng hợp:* wᵢ là wᵢ₋₁ dịch trái một bit cộng bit tiếp theo. Cận dưới: mọi đường p có wᵢ(p) ≥ 2wᵢ₋₁(p) ≥ 2δᵢ₋₁. Cận trên: lấy đường đơn p ngắn nhất theo wᵢ₋₁, có ≤ |V| − 1 cạnh, wᵢ(p) ≤ 2wᵢ₋₁(p) + |V| − 1.)
- **(d)** Định nghĩa ŵᵢ(u, v) = wᵢ(u, v) + 2δᵢ₋₁(s, u) − 2δᵢ₋₁(s, v). Chứng minh ŵᵢ(u, v) là số nguyên không âm (đề viết "với mọi u, v ∈ V", nên hiểu là với mọi cạnh). (*Người tổng hợp:* ŵᵢ ≥ 2wᵢ₋₁(u, v) + 2δᵢ₋₁(s, u) − 2δᵢ₋₁(s, v) ≥ 0 theo bất đẳng thức tam giác với wᵢ₋₁; nguyên vì mọi số hạng nguyên.)
- **(e)** Gọi δ̂ᵢ(s, v) là trọng số đường đi ngắn nhất theo ŵᵢ. Chứng minh δᵢ(s, v) = δ̂ᵢ(s, v) + 2δᵢ₋₁(s, v) và δ̂ᵢ(s, v) ≤ |E|. (*Người tổng hợp:* dọc mọi đường p từ s tới v, tổng các số hạng 2δᵢ₋₁ rút gọn: ŵᵢ(p) = wᵢ(p) + 2δᵢ₋₁(s, s) − 2δᵢ₋₁(s, v) = wᵢ(p) − 2δᵢ₋₁(s, v); mọi đường bị trừ cùng một hằng nên đường ngắn nhất không đổi. Theo (c), δ̂ᵢ ≤ |V| − 1 ≤ |E|.)
- **(f)** Chỉ cách tính δᵢ từ δᵢ₋₁ trong O(E), và kết luận tính được δ trong O(E lg W). (*Người tổng hợp:* tính ŵᵢ cho mọi cạnh O(E), dùng (a) tính δ̂ᵢ trong O(E), cộng 2δᵢ₋₁ được δᵢ. Lặp k = O(lg W) lần.)

### Problem 24-5: Thuật toán chu trình trọng số trung bình nhỏ nhất của Karp (Karp's minimum mean-weight cycle algorithm)

Cho G = (V, E) có hướng với w: E → ℝ, n = |V|. **Trọng số trung bình** của chu trình c = ⟨e₁, …, e_k⟩ là μ(c) = (1/k) Σᵢ₌₁ᵏ w(eᵢ). Đặt μ* = min_c μ(c) trên mọi chu trình có hướng; chu trình đạt μ* gọi là **chu trình trọng số trung bình nhỏ nhất**. Giả sử mọi đỉnh đi tới được từ nguồn s. Gọi δ(s, v) là trọng số đường ngắn nhất, δₖ(s, v) là trọng số đường ngắn nhất gồm *đúng* k cạnh (bằng ∞ nếu không có).

- **(a)** Nếu μ* = 0 thì G không có chu trình âm và δ(s, v) = min_{0 ≤ k ≤ n−1} δₖ(s, v). (*Người tổng hợp:* chu trình âm sẽ có trung bình âm < μ*; khi không có chu trình âm, đường ngắn nhất là đường đơn ≤ n − 1 cạnh.)
- **(b)** Nếu μ* = 0 thì max_{0 ≤ k ≤ n−1} (δₙ(s, v) − δₖ(s, v))/(n − k) ≥ 0 với mọi v. (*Người tổng hợp:* δₙ(s, v) ≥ δ(s, v) = min_k δₖ(s, v), nên với k đạt min, tử số ≥ 0.)
- **(c)** c là chu trình trọng số 0, u, v trên c, μ* = 0, đường đơn từ u tới v dọc c nặng x. Chứng minh δ(s, v) = δ(s, u) + x. (Gợi ý: đường từ v tới u dọc c nặng −x.) (*Người tổng hợp:* δ(s, v) ≤ δ(s, u) + x và δ(s, u) ≤ δ(s, v) − x.)
- **(d)** Nếu μ* = 0 thì trên mỗi chu trình trung bình nhỏ nhất có đỉnh v với max_k (δₙ(s, v) − δₖ(s, v))/(n − k) = 0. (*Người tổng hợp:* lấy đường ngắn nhất tới một đỉnh trên c, kéo dài dọc c (theo (c) vẫn là đường ngắn nhất) tới khi đủ n cạnh, tại đỉnh v cuối: δₙ(s, v) = δ(s, v), nên mọi tử số ≤ 0, và có k làm bằng 0.)
- **(e)** Nếu μ* = 0 thì min_v max_k (δₙ(s, v) − δₖ(s, v))/(n − k) = 0. (Từ (b) và (d).)
- **(f)** Cộng hằng t vào mọi trọng số thì μ* tăng t; dùng điều đó chứng minh μ* = min_v max_{0 ≤ k ≤ n−1} (δₙ(s, v) − δₖ(s, v))/(n − k). (*Người tổng hợp:* chọn t = −μ* để μ* mới bằng 0; khi cộng t, δₙ tăng nt, δₖ tăng kt, nên biểu thức tăng đúng t.)
- **(g)** Cho thuật toán O(VE) tính μ*. (*Người tổng hợp:* tính δₖ(s, v) cho k = 0..n bằng quy hoạch động δₖ(s, v) = min_{(u,v) ∈ E} (δₖ₋₁(s, u) + w(u, v)), mỗi tầng O(E), tổng O(nE); rồi tính công thức (f) trong O(n²) = O(VE) vì E ≥ V − 1.)

### Problem 24-6: Đường đi ngắn nhất bitonic (Bitonic shortest paths)

Một dãy là **bitonic** nếu nó tăng đơn điệu rồi giảm đơn điệu, hoặc nếu sau một phép dịch vòng thì nó tăng rồi giảm. Ví dụ ⟨1, 4, 6, 8, 3, −2⟩, ⟨9, 2, −4, −10, −5⟩ và ⟨1, 2, 3, 4⟩ là bitonic, còn ⟨1, 3, 12, 4, 2, 10⟩ thì không. (Xem Problem 15-3 về bài toán người bán hàng Euclid bitonic.)

Cho G = (V, E) có hướng với w: E → ℝ, mọi trọng số khác nhau đôi một, cần tìm đường ngắn nhất từ nguồn s. Biết thêm: với mỗi v, trọng số các cạnh dọc bất kỳ đường ngắn nhất nào từ s tới v tạo thành dãy bitonic. Cho thuật toán hiệu quả nhất có thể và phân tích.

*Lời giải của người tổng hợp:* sắp xếp các cạnh theo trọng số, O(E lg E). Thực hiện vài lượt, mỗi lượt nới lỏng mọi cạnh theo thứ tự trọng số tăng dần hoặc giảm dần. Một khúc tăng dần của đường được nới lỏng đúng thứ tự trong một lượt "tăng", một khúc giảm dần trong một lượt "giảm". Dãy tăng rồi giảm cần lượt tăng rồi lượt giảm. Dịch vòng của một dãy tăng–giảm có thể có dạng tăng–giảm–tăng hoặc giảm–tăng–giảm (ví dụ ⟨6, 8, 3, −2, 1, 4⟩ là tăng, giảm, tăng); bốn lượt tăng, giảm, tăng, giảm bao được mọi trường hợp. Theo tính chất nới lỏng theo đường, kết quả đúng. Tổng thời gian O(V + E lg E) = O(V + E lg V), phần trội là sắp xếp.

### Ghi chú chương (Chapter notes, trang 682–683)

- Thuật toán **Dijkstra** công bố năm 1959, nhưng bài gốc không nhắc tới hàng đợi ưu tiên.
- Thuật toán **Bellman-Ford** dựa trên hai thuật toán riêng của **Bellman** và của **Ford**. Bellman mô tả mối quan hệ giữa đường đi ngắn nhất và ràng buộc hiệu.
- **Lawler** mô tả thuật toán thời gian tuyến tính cho đường đi ngắn nhất trên dag và coi nó là một phần của "kiến thức dân gian" (folklore).
- Khi trọng số là số nguyên không âm tương đối nhỏ, có thuật toán hiệu quả hơn. Dãy giá trị trả về bởi các lời gọi EXTRACT-MIN trong Dijkstra tăng đơn điệu theo thời gian; như đã bàn ở ghi chú Chương 6, khi đó nhiều cấu trúc dữ liệu cài các thao tác hàng đợi ưu tiên hiệu quả hơn đống nhị phân hay đống Fibonacci. **Ahuja, Mehlhorn, Orlin và Tarjan** cho thuật toán O(E + V √lg W) trên đồ thị trọng số không âm, W là trọng số cạnh lớn nhất. Cận tốt nhất là của **Thorup**, O(E lg lg V), và của **Raman**, O(E + V min{(lg V)^(1/3+ε), (lg W)^(1/4+ε)}). Hai thuật toán này dùng lượng bộ nhớ phụ thuộc kích thước từ máy; lượng bộ nhớ có thể không bị chặn theo kích thước đầu vào, nhưng có thể giảm về tuyến tính bằng băm ngẫu nhiên.
- Với đồ thị **vô hướng** trọng số nguyên, **Thorup** cho thuật toán O(V + E). Khác các thuật toán ở đoạn trên, thuật toán này không phải một cài đặt của Dijkstra, vì dãy giá trị EXTRACT-MIN trả về không tăng đơn điệu.
- Với đồ thị có trọng số âm, thuật toán của **Gabow và Tarjan** chạy O(√V E lg(VW)), của **Goldberg** chạy O(√V E lg W), với W = max_{(u,v) ∈ E} |w(u, v)|.
- **Cherkassky, Goldberg và Radzik** làm thực nghiệm quy mô lớn so sánh nhiều thuật toán đường đi ngắn nhất.

## Luận điểm cốt lõi

### Mệnh đề

Bài toán đường đi ngắn nhất từ một nguồn trên đồ thị có hướng có trọng số giải được bằng một kỹ thuật duy nhất — khởi tạo ước lượng rồi nới lỏng cạnh — và mọi khác biệt giữa các thuật toán nằm ở việc chọn số lần và thứ tự nới lỏng sao cho các cạnh của mỗi đường ngắn nhất được nới lỏng đúng thứ tự: |V| − 1 lượt mù quáng cho đồ thị tổng quát (Bellman-Ford, O(VE), phát hiện được chu trình âm), một lượt theo thứ tự tô-pô cho dag (Θ(V + E)), một lượt theo thứ tự khoảng cách tăng dần khi trọng số không âm (Dijkstra, O(V lg V + E)). Bài toán khả thi của hệ ràng buộc hiệu là bài toán đường đi ngắn nhất trá hình.

### Giả định

- Đồ thị có hướng, lưu bằng danh sách kề, trọng số đọc được trong O(1) mỗi cạnh; mô hình RAM.
- Đường đi ngắn nhất chỉ có nghĩa khi không có chu trình âm đi tới được từ nguồn; khi có, δ = −∞ cho các đỉnh bị ảnh hưởng.
- Số học mở rộng với ±∞: a + ∞ = ∞ (a ≠ −∞), a + (−∞) = −∞ (a ≠ ∞).
- Dijkstra đòi mọi trọng số không âm; DAG-SHORTEST-PATHS đòi không có chu trình; Bellman-Ford không đòi gì.
- Phân tích Dijkstra giả định hàng đợi ưu tiên hỗ trợ DECREASE-KEY với tay cầm giữa đỉnh và phần tử đống.
- Đường đi ngắn nhất có thể coi là đường đơn, tối đa |V| − 1 cạnh.

### Cơ chế

1. INITIALIZE-SINGLE-SOURCE: s.d = 0, mọi đỉnh khác ∞, mọi π = NIL.
2. RELAX(u, v, w) là phép duy nhất làm thay đổi d, π; nó giữ bất biến v.d ≥ δ(s, v) (cận trên) và chỉ làm d giảm.
3. Nếu các cạnh của một đường ngắn nhất p được nới lỏng theo thứ tự trên p (xen gì cũng được), đỉnh cuối của p nhận giá trị đúng (nới lỏng theo đường).
4. Bellman-Ford bảo đảm điều đó bằng cách nới lỏng mọi cạnh |V| − 1 lần: lượt thứ i chắc chắn chứa cạnh thứ i của đường.
5. DAG-SHORTEST-PATHS bảo đảm bằng thứ tự tô-pô: mọi đường đi theo thứ tự đó.
6. Dijkstra bảo đảm bằng thứ tự khoảng cách: khi đỉnh u có d nhỏ nhất ngoài S, mọi đỉnh y trên đường ngắn nhất tới u mà còn ngoài S đều có δ(s, y) ≤ δ(s, u) (vì trọng số không âm), nên u.d đã đúng.
7. Khi mọi d = δ, đồ thị con liền trước là cây đường đi ngắn nhất; trong suốt quá trình (không có chu trình âm), nó luôn là cây có gốc s.
8. Chu trình âm bị lộ vì nó làm tổng các bất đẳng thức "đã nới lỏng xong" quanh chu trình mâu thuẫn: 0 ≤ w(c) < 0.
9. Hệ ràng buộc hiệu: ràng buộc xⱼ − xᵢ ≤ bₖ là cạnh vᵢ → vⱼ trọng số bₖ; bất đẳng thức tam giác của δ(v₀, ·) chính là các ràng buộc.

### Bằng chứng và ví dụ tác giả đưa ra

- Ví dụ Phoenix–Indianapolis: liệt kê mọi tuyến là vô vọng; tuyến qua Seattle rõ ràng thừa.
- Hình 24.1: đồ thị 10 đỉnh minh hoạ đủ các loại δ: hữu hạn dương, hữu hạn âm (δ(s, b) = −1), −∞ (e, f, g), ∞ (h, i, j dù nằm trên chu trình âm).
- Hình 24.2: một đồ thị có hai cây đường đi ngắn nhất khác nhau với cùng gốc.
- Hình 24.3: hai phép nới lỏng, một làm giảm (9 thành 7), một không đổi (6).
- Hình 24.4: bốn lượt Bellman-Ford trên đồ thị 5 đỉnh có cạnh âm, kết quả (0, 2, 4, 7, −2), trả về TRUE.
- Hình 24.5: DAG-SHORTEST-PATHS trên dag 6 đỉnh có cạnh âm, kết quả (∞, 0, 2, 6, 5, 3).
- Hình 24.6: Dijkstra trên đồ thị 5 đỉnh, thứ tự lấy ra s, y, z, t, x, kết quả (0, 8, 9, 5, 7).
- Hình 24.7: sơ đồ chứng minh Dijkstra với đỉnh x ∈ S và y ∉ S trên đường ngắn nhất tới u.
- Hệ 8 ràng buộc hiệu (24.3)–(24.10) và đồ thị ràng buộc Hình 24.8, nghiệm (−5, −3, 0, −1, −4) và nghiệm dịch (0, 2, 5, 4, 1).
- Ví dụ lắp ráp với keo khô sau 2 giờ cho ràng buộc x₁ − x₂ ≤ −2.
- Hình 24.9: hai đường gặp nhau ở z buộc z.π mang hai giá trị — chứng minh tính duy nhất của đường trong G_π.
- Ví dụ tỷ giá đô la–rupee–yên cho lãi 4,86% (Problem 24-3).

### Kết luận và hàm ý cho người lập trình

- Chọn thuật toán theo cấu trúc đồ thị: dag thì dùng thứ tự tô-pô (nhanh nhất và chấp nhận cạnh âm); trọng số không âm thì Dijkstra với đống nhị phân; có cạnh âm thì Bellman-Ford; trọng số chỉ 0/1 hoặc nguyên nhỏ thì BFS biến thể hoặc mảng thùng (Exercise 24.3-8).
- Không chạy Dijkstra trên đồ thị có cạnh âm: nó không báo lỗi mà cho kết quả sai một cách im lặng (Exercise 24.3-2).
- Bellman-Ford là công cụ phát hiện chu trình âm: dùng cho kinh doanh chênh lệch tỷ giá, kiểm tra tính khả thi của ràng buộc thời gian, phát hiện mâu thuẫn trong hệ bất đẳng thức hiệu.
- Đường dài nhất chỉ dễ trên dag (đổi dấu trọng số); trên đồ thị tổng quát không được áp dụng cách này.
- Lưu π song song với d để khôi phục đường đi; lần ngược π cho đường theo chiều ngược.
- Biến bài toán tích (độ tin cậy, tỷ giá) thành bài toán tổng bằng logarit: −lg hoặc −ln.
- Nhiều bài toán lập lịch và ràng buộc thời gian có thể quy về hệ ràng buộc hiệu và giải bằng Bellman-Ford thay vì cần một bộ giải quy hoạch tuyến tính tổng quát.

### Trong ngôn ngữ khoa học máy tính

Cho G = (V, E), w: E → ℝ, nguồn s. δ(s, v) = min{w(p) : s ⇝ v} hoặc ∞; δ = −∞ khi có chu trình âm trên đường. RELAX duy trì bất biến v.d ≥ δ(s, v). Bellman-Ford: O(VE), trả về FALSE khi và chỉ khi có chu trình âm đi tới được từ s. DAG-SHORTEST-PATHS: Θ(V + E). Dijkstra (w ≥ 0): O(V²) với mảng, O((V + E) lg V) với đống nhị phân, O(V lg V + E) với đống Fibonacci; |V| EXTRACT-MIN, ≤ |E| DECREASE-KEY. Hệ m ràng buộc hiệu trên n ẩn ⇔ đồ thị n + 1 đỉnh, n + m cạnh; khả thi ⇔ không có chu trình âm; nghiệm xᵢ = δ(v₀, vᵢ); thời gian O(n² + nm), cải tiến được O(nm). Cận lý thuyết tốt hơn trong ghi chú: O(E lg lg V) (Thorup, trọng số nguyên), O(V + E) (Thorup, vô hướng, trọng số nguyên), O(√V E lg W) (Goldberg, có trọng số âm).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| shortest-paths problem | bài toán đường đi ngắn nhất | tìm đường có tổng trọng số nhỏ nhất |
| weighted directed graph | đồ thị có hướng có trọng số | mỗi cạnh có hướng mang một số thực |
| weight function w | hàm trọng số | gán số thực cho mỗi cạnh |
| path weight w(p) | trọng số đường đi | tổng trọng số các cạnh của đường |
| shortest-path weight δ(u, v) | trọng số đường đi ngắn nhất | min trọng số mọi đường; ∞ nếu không có đường; −∞ nếu có chu trình âm chen vào |
| shortest path | đường đi ngắn nhất | đường có trọng số bằng δ |
| source vertex | đỉnh nguồn | đỉnh xuất phát s |
| destination vertex | đỉnh đích | đỉnh kết thúc t |
| single-source / single-destination / single-pair / all-pairs | một nguồn / một đích / một cặp / mọi cặp | bốn biến thể của bài toán |
| optimal substructure | cấu trúc con tối ưu | đoạn con của đường ngắn nhất cũng ngắn nhất |
| negative-weight edge | cạnh trọng số âm | cạnh có w < 0 |
| negative-weight cycle | chu trình trọng số âm | chu trình có tổng trọng số < 0 |
| simple path | đường đơn | đường không lặp đỉnh |
| predecessor v.π | đỉnh liền trước | đỉnh đứng ngay trước v trên đường đã tìm |
| predecessor subgraph G_π | đồ thị con liền trước | đồ thị sinh bởi các cạnh (v.π, v) |
| shortest-paths tree | cây đường đi ngắn nhất | cây gốc s chứa đường ngắn nhất tới mọi đỉnh đi tới được |
| shortest-path estimate v.d | ước lượng đường đi ngắn nhất | cận trên của δ(s, v), giảm dần |
| relaxation / relax an edge | nới lỏng / nới lỏng cạnh | cập nhật v.d, v.π nếu đi qua u tốt hơn |
| triangle inequality | bất đẳng thức tam giác | δ(s, v) ≤ δ(s, u) + w(u, v) |
| upper-bound property | tính chất cận trên | v.d ≥ δ(s, v) mọi lúc |
| no-path property | tính chất không có đường | không có đường thì d = ∞ mãi |
| convergence property | tính chất hội tụ | u.d đúng trước khi nới lỏng (u, v) thì v.d đúng sau đó |
| path-relaxation property | tính chất nới lỏng theo đường | nới lỏng đúng thứ tự các cạnh của đường thì đỉnh cuối đúng |
| predecessor-subgraph property | tính chất đồ thị con liền trước | d đúng hết thì G_π là cây đường đi ngắn nhất |
| pass | lượt | một lần nới lỏng mọi cạnh trong Bellman-Ford |
| Bellman-Ford algorithm | thuật toán Bellman-Ford | |V| − 1 lượt nới lỏng, phát hiện chu trình âm, O(VE) |
| directed acyclic graph (dag) | đồ thị có hướng không chu trình | không có chu trình có hướng |
| topological sort | sắp xếp tô-pô | thứ tự đỉnh mà mọi cạnh đi từ trước ra sau |
| PERT chart | sơ đồ PERT | sơ đồ công việc và thứ tự trước sau (program evaluation and review technique) |
| critical path | đường găng | đường dài nhất trong dag công việc |
| Dijkstra's algorithm | thuật toán Dijkstra | tham lam lấy đỉnh có d nhỏ nhất, trọng số không âm |
| min-priority queue | hàng đợi ưu tiên nhỏ nhất | INSERT, EXTRACT-MIN, DECREASE-KEY |
| binary min-heap / Fibonacci heap | đống nhị phân nhỏ nhất / đống Fibonacci | hai cách cài hàng đợi ưu tiên |
| handle | tay cầm | con trỏ hai chiều giữa đỉnh và phần tử trong đống |
| greedy strategy | chiến lược tham lam | chọn phương án tốt nhất tại chỗ |
| aggregate analysis | phân tích gộp | đếm tổng công việc trên cả quá trình |
| linear programming | quy hoạch tuyến tính | tối ưu hàm tuyến tính dưới các bất đẳng thức tuyến tính |
| objective function | hàm mục tiêu | Σ cᵢxᵢ cần tối đa hoá |
| feasible solution / feasibility problem | nghiệm khả thi / bài toán khả thi | x thoả Ax ≤ b / chỉ hỏi có x như vậy không |
| simplex algorithm | thuật toán đơn hình | thuật toán quy hoạch tuyến tính của Chương 29 |
| difference constraint | ràng buộc hiệu | xⱼ − xᵢ ≤ bₖ |
| system of difference constraints | hệ ràng buộc hiệu | mỗi hàng của A có một 1 và một −1 |
| constraint graph | đồ thị ràng buộc | đỉnh v₀..vₙ, cạnh vᵢ → vⱼ trọng số bₖ |
| incidence matrix | ma trận liên thuộc | ma trận đỉnh × cạnh ghi cạnh vào/ra đỉnh nào |
| equality constraint | ràng buộc đẳng thức | xᵢ = xⱼ + bₖ, tách thành hai ràng buộc hiệu |
| arbitrage | kinh doanh chênh lệch tỷ giá | đổi vòng tiền tệ để lãi |
| scaling algorithm | thuật toán co giãn | lộ dần từng bit của dữ liệu số |
| mean weight / minimum mean-weight cycle | trọng số trung bình / chu trình trung bình nhỏ nhất | tổng trọng số chia số cạnh |
| bitonic sequence | dãy bitonic | tăng rồi giảm, hoặc dịch vòng của dãy như vậy |
| nesting boxes | hộp lồng nhau | hộp này đặt vừa trong hộp kia sau khi xoay |
| reliability | độ tin cậy | xác suất kênh không hỏng |

## Câu nói đáng nhớ

> "Edge weights can represent metrics other than distances, such as time, cost, penalties, loss, or any other quantity that accumulates linearly along a path and that we would want to minimize." — phần mở đầu chương
>
> *Dịch: Trọng số cạnh có thể biểu diễn những đại lượng khác ngoài khoảng cách, như thời gian, chi phí, mức phạt, tổn thất, hay bất kỳ đại lượng nào cộng dồn tuyến tính dọc một đường mà ta muốn tối thiểu hoá.*

> "Shortest-paths algorithms typically rely on the property that a shortest path between two vertices contains other shortest paths within it." — phần mở đầu, cấu trúc con tối ưu
>
> *Dịch: Các thuật toán đường đi ngắn nhất thường dựa vào tính chất: đường đi ngắn nhất giữa hai đỉnh chứa bên trong nó những đường đi ngắn nhất khác.*

> "Moreover, relaxation is the only means by which shortest-path estimates and predecessors change. The algorithms in this chapter differ in how many times they relax each edge and the order in which they relax edges." — phần mở đầu, nới lỏng
>
> *Dịch: Hơn nữa, nới lỏng là cách duy nhất làm thay đổi ước lượng đường đi ngắn nhất và đỉnh liền trước. Các thuật toán trong chương khác nhau ở số lần nới lỏng mỗi cạnh và thứ tự nới lỏng các cạnh.*

> "It may seem strange that the term 'relaxation' is used for an operation that tightens an upper bound. The use of the term is historical." — chú thích 1
>
> *Dịch: Có vẻ lạ khi gọi là "nới lỏng" một phép toán làm chặt cận trên. Cách dùng thuật ngữ này có tính lịch sử.*

> "The Bellman-Ford algorithm is remarkably simple, and it has the further benefit of detecting whether a negative-weight cycle is reachable from the source." — dàn ý chương
>
> *Dịch: Thuật toán Bellman-Ford đơn giản đáng kinh ngạc, và còn có lợi ích là phát hiện được liệu có chu trình trọng số âm đi tới được từ nguồn hay không.*

> "Greedy strategies do not always yield optimal results in general, but as the following theorem and its corollary show, Dijkstra's algorithm does indeed compute shortest paths." — Mục 24.3
>
> *Dịch: Nói chung chiến lược tham lam không phải lúc nào cũng cho kết quả tối ưu, nhưng như định lý và hệ quả sau cho thấy, thuật toán Dijkstra thật sự tính đúng các đường đi ngắn nhất.*

> "Historically, the development of Fibonacci heaps was motivated by the observation that Dijkstra's algorithm typically makes many more DECREASE-KEY calls than EXTRACT-MIN calls." — Mục 24.3, phân tích
>
> *Dịch: Về mặt lịch sử, đống Fibonacci ra đời từ nhận xét rằng thuật toán Dijkstra thường gọi DECREASE-KEY nhiều hơn hẳn EXTRACT-MIN.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: một khung chứng minh dùng chung cho ba thuật toán

Thay vì chứng minh từng thuật toán từ đầu, chương tách ra sáu tính chất của phép nới lỏng, phát biểu sớm và chứng minh một lần ở Mục 24.5. Nhờ đó chứng minh Bellman-Ford (Bổ đề 24.2) và DAG-SHORTEST-PATHS (Định lý 24.5) chỉ dài vài dòng: cả hai chỉ cần chỉ ra rằng các cạnh của mỗi đường ngắn nhất được nới lỏng đúng thứ tự. Đây là bài học phương pháp đáng giá nhất của chương: tách "phép toán cơ bản và bất biến của nó" khỏi "chiến lược áp dụng phép toán". Người đọc nhìn ba thuật toán như ba lịch nới lỏng khác nhau, và dễ tự nghĩ ra biến thể (Yen ở Problem 24-1, thứ tự trọng số ở Problem 24-6).

### Điểm mạnh: định nghĩa δ chặt chẽ với ±∞

Ví dụ Hình 24.1 bao được cả bốn loại giá trị δ trong một đồ thị nhỏ, kể cả trường hợp tinh tế: đỉnh nằm trên chu trình âm nhưng không đi tới được thì δ = ∞, và đỉnh đi tới được từ chu trình âm (g) cũng bị −∞. Quy ước số học với ±∞ được nêu rõ để các chứng minh không phải tách trường hợp.

### Điểm mạnh: cầu nối sang quy hoạch tuyến tính

Mục 24.4 là một ví dụ đẹp về quy dẫn: một bài toán quy hoạch tuyến tính đặc biệt được giải bằng thuật toán tổ hợp đơn giản, và chu trình âm đóng vai "chứng cứ vô nghiệm" — tiền thân của ý tưởng đối ngẫu (duality) ở Chương 29.

### Điểm yếu và chỗ đơn giản hoá

- **Lời viện dẫn chưa khớp giả thiết trong chứng minh Định lý 24.4** (xem khối Lưu ý): phần có chu trình âm dùng Hệ quả 24.3, vốn giả thiết không có chu trình âm. Người đọc kỹ sẽ vấp ở đây.
- **Chứng minh tính chất hội tụ và Dijkstra dựa ngầm vào việc các δ hữu hạn.** Sách xử lý bằng quy ước số học ±∞, nhưng không nói rõ chỗ nào cần "không có chu trình âm" (ví dụ ở cơ sở quy nạp của Bổ đề 24.15).
- **Phân tích Dijkstra bằng đống Fibonacci chỉ có ý nghĩa lý thuyết.** Sách nói đúng về tiệm cận nhưng không cảnh báo rằng, theo hiểu biết của người tổng hợp, đống Fibonacci có hằng số lớn và hầu như không được dùng trong thực tế; đống nhị phân (thậm chí không có DECREASE-KEY, chèn trùng rồi bỏ qua) hoặc đống bậc d thường nhanh hơn.
- **Mô hình chỉ đồ thị có hướng.** Đồ thị vô hướng được xử lý bằng cách thay mỗi cạnh bằng hai cạnh ngược chiều, nhưng sách không nói; và với cạnh vô hướng trọng số âm, cách này tạo ngay chu trình âm hai cạnh — đường ngắn nhất vô hướng có cạnh âm là bài toán khác hẳn (theo hiểu biết của người tổng hợp, cần kỹ thuật ghép cặp), sách không nhắc.
- **Không bàn bài toán một cặp trong thực tế.** Sách nói đúng rằng về xấu nhất không có thuật toán một cặp nhanh hơn, nhưng thực tế (chỉ đường) người ta dừng Dijkstra sớm khi lấy ra đích, chạy hai chiều, dùng A* — những tối ưu không thay đổi cận xấu nhất nhưng thay đổi hiệu năng hàng nghìn lần.
- **Mục 24.4 dừng ở bài toán khả thi.** Kết quả "Bellman-Ford tối ưu hoá Σ xᵢ" và "tối thiểu hoá max − min" bị đẩy xuống bài tập có dấu sao (24.4-8, 24.4-9), dù đó mới là điều người lập lịch thật sự cần.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: thư viện đồ thị phổ biến (Boost Graph Library, NetworkX, JGraphT) cài đúng ba thuật toán của chương, với Dijkstra dùng đống nhị phân hoặc đống bậc d. Định tuyến Internet dùng cả hai họ: link-state (OSPF, IS-IS) chạy Dijkstra, distance-vector (RIP) và BGP có gốc Bellman-Ford. Dịch vụ bản đồ tiền xử lý đồ thị đường bộ (contraction hierarchies, hub labeling) để trả lời trong micro-giây — một hướng sách không đề cập. Năm 2022–2023, đã có thuật toán gần tuyến tính cho đường đi ngắn nhất một nguồn với trọng số âm nguyên (Bernstein, Nanongkai, Wulff-Nilsen) — vượt xa cận Goldberg trong ghi chú chương; người tổng hợp nhớ kết quả này nhưng không tra cứu chi tiết.

### Liên hệ các chương khác

- Chương 22 ([C22-thuat-toan-do-thi-co-ban.md](C22-thuat-toan-do-thi-co-ban.md)): BFS là Dijkstra khi mọi trọng số bằng 1 (hàng đợi FIFO thay hàng đợi ưu tiên); sắp xếp tô-pô là bước 1 của DAG-SHORTEST-PATHS; PRINT-PATH in đường từ π.
- Chương 23 ([C23-cay-khung-nho-nhat.md](C23-cay-khung-nho-nhat.md)): Prim có cấu trúc trùng Dijkstra, chỉ khác khoá; cây khung nhỏ nhất và cây đường đi ngắn nhất là hai cây khác nhau trên cùng đồ thị.
- Chương 6 ([C06-heapsort.md](C06-heapsort.md)) và Chương 19 ([C19-dong-fibonacci.md](C19-dong-fibonacci.md)): hàng đợi ưu tiên quyết định thời gian Dijkstra; đống Fibonacci được thiết kế chính cho Dijkstra.
- Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)) và Chương 16 ([C16-thuat-toan-tham-lam.md](C16-thuat-toan-tham-lam.md)): cấu trúc con tối ưu; Bellman-Ford có thể xem là quy hoạch động theo số cạnh, Dijkstra là tham lam.
- Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)): phân tích gộp và chi phí khấu hao dùng khi phân tích DAG-SHORTEST-PATHS và Dijkstra.
- Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)): Floyd-Warshall (quy hoạch động), và thuật toán Johnson dùng Bellman-Ford để đánh lại trọng số không âm (cùng ý tưởng với ŵ ở Problem 24-4) rồi chạy Dijkstra từ mọi đỉnh.
- Chương 26 ([C26-luong-cuc-dai.md](C26-luong-cuc-dai.md)): Edmonds-Karp tìm đường tăng ngắn nhất theo số cạnh; luồng chi phí nhỏ nhất dùng đường đi ngắn nhất với cạnh âm trong đồ thị dư.
- Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)): quy hoạch tuyến tính tổng quát; Exercise 24.4-4 biểu diễn đường đi ngắn nhất một cặp thành quy hoạch tuyến tính.
- Phụ lục B ([PB-tap-hop-va-cau-truc-roi-rac.md](PB-tap-hop-va-cau-truc-roi-rac.md)): định nghĩa cây có gốc và Exercise B.5-2 dùng trong Bổ đề 24.16.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** viết Dijkstra với `priority_queue` và kiểm tra "đỉnh đã lấy ra rồi thì bỏ qua"; giải thích vì sao Dijkstra sai với cạnh âm (ví dụ ba đỉnh); phát hiện chu trình âm bằng Bellman-Ford; bài "chuyến bay rẻ nhất với tối đa K điểm dừng" (Bellman-Ford giới hạn K + 1 lượt, mỗi lượt dùng bản sao d của lượt trước); bài "mạng trễ" (thời gian lớn nhất trong các δ); bài kinh doanh chênh lệch tỷ giá với −log.
- **Lập trình thi đấu:** 0-1 BFS (deque) khi trọng số chỉ 0 và 1; Dijkstra trên đồ thị trạng thái mở rộng (đỉnh × số lần dùng ưu đãi); hệ ràng buộc hiệu là dạng bài quen thuộc ("hệ bất đẳng thức hiệu", kiểm tra chu trình âm bằng Bellman-Ford hoặc SPFA); đường dài nhất / đếm đường trên dag bằng quy hoạch động theo thứ tự tô-pô (Exercise 24.2-4); cẩn thận tràn số khi cộng với ∞ — dùng hằng số lớn nhưng không gần giới hạn kiểu.
- **Kỹ thuật phần mềm:** hệ thống build và lập lịch tác vụ (đường găng trên dag phụ thuộc); định tuyến mạng và hậu cần; bộ giải ràng buộc thời gian; phân tích chương trình (bộ giải logic hiệu trong SMT). Chọn cấu trúc dữ liệu theo mật độ đồ thị: đồ thị dày dùng Dijkstra mảng O(V²), đồ thị thưa dùng đống nhị phân.

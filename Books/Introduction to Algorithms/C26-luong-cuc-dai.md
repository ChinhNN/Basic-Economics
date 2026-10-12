# Chương 26 — Luồng cực đại (Maximum Flow)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VI "Graph Algorithms", Chương 26 "Maximum Flow", trang 708–766 (trang 767 để trắng; trang 768 là trang tên Phần VII "Selected Topics", thuộc về [C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Chương 26 là chương cuối của Phần VI (thuật toán đồ thị). Nó dùng lại gần như mọi công cụ của các chương đồ thị trước: biểu diễn đồ thị và thuộc tính cạnh dạng (u, v).f, tìm kiếm theo chiều rộng và theo chiều sâu ở Chương 22 ([C22-thuat-toan-do-thi-co-ban.md](C22-thuat-toan-do-thi-co-ban.md)) để tìm đường tăng luồng; khái niệm lát cắt của cây khung nhỏ nhất ở Chương 23 ([C23-cay-khung-nho-nhat.md](C23-cay-khung-nho-nhat.md)), nay áp dụng cho đồ thị có hướng; khoảng cách đường đi ngắn nhất và bất đẳng thức tam giác (Bổ đề 24.10) ở Chương 24 ([C24-duong-di-ngan-nhat-tu-mot-nguon.md](C24-duong-di-ngan-nhat-tu-mot-nguon.md)) cho phân tích Edmonds-Karp; sắp xếp topo của đồ thị không chu trình (Chương 22) cho bất biến của thuật toán relabel-to-front. Kỹ thuật hàm thế của phân tích khấu hao ở Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)) được dùng để chặn số lần đẩy không bão hoà. Về phía sau: Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)) trình bày luồng cực đại và luồng chi phí nhỏ nhất như bài toán quy hoạch tuyến tính (Exercise 26.1-5 báo trước), và định lý luồng cực đại – lát cắt cực tiểu là một trường hợp của đối ngẫu quy hoạch tuyến tính; Chương 34 ([C34-np-day-du.md](C34-np-day-du.md)) và Chương 35 ([C35-thuat-toan-xap-xi.md](C35-thuat-toan-xap-xi.md)) đối chiếu cặp ghép hai phía (giải được trong thời gian đa thức) với các bài toán phủ và ghép khó hơn.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **giá trị luồng lớn nhất từ nguồn tới đích bằng đúng sức chứa của lát cắt nhỏ nhất ngăn cách chúng (định lý luồng cực đại – lát cắt cực tiểu), và điều kiện "không còn đường tăng luồng trong mạng thặng dư" vừa là tiêu chuẩn dừng vừa là bằng chứng tối ưu; trên nền đó có hai họ thuật toán: tăng luồng dần dọc các đường (Ford-Fulkerson, Edmonds-Karp O(VE²)) và đẩy tiền luồng cục bộ theo độ cao đỉnh (đẩy–nâng nhãn O(V²E), relabel-to-front O(V³)).** Mục 26.1 định nghĩa mạng luồng (sức chứa không âm, không có cạnh ngược chiều, nguồn s, đích t), luồng (ràng buộc sức chứa, bảo toàn luồng), giá trị |f|, và hai kỹ thuật mô hình hoá: tách cạnh để khử cạnh ngược chiều, thêm siêu nguồn/siêu đích cho bài toán nhiều nguồn nhiều đích. Mục 26.2 xây ba ý tưởng — mạng thặng dư G_f (có cạnh ngược để "trả lại" luồng), đường tăng luồng, lát cắt — chứng minh luồng ròng qua mọi lát cắt bằng |f|, |f| ≤ c(S, T), rồi định lý luồng cực đại – lát cắt cực tiểu; thuật toán FORD-FULKERSON chạy O(E|f*|) với sức chứa nguyên và có thể tốn 2.000.000 vòng trên mạng 4 đỉnh; Edmonds-Karp chọn đường ngắn nhất bằng BFS, khoảng cách từ s không giảm, mỗi cạnh tới hạn nhiều nhất |V|/2 lần, nên O(VE) lần tăng và O(VE²) thời gian. Mục 26.3 quy cặp ghép cực đại trong đồ thị hai phía về luồng cực đại trên mạng sức chứa 1, dùng định lý tính nguyên, được O(VE). Mục ★26.4 trình bày phương pháp đẩy–nâng nhãn của Goldberg: tiền luồng cho phép luồng dư tại đỉnh, hàm độ cao h với h(s) = |V|, h(t) = 0, h(u) ≤ h(v) + 1 trên cạnh thặng dư bảo đảm không bao giờ có đường s ⇝ t trong G_f; độ cao ≤ 2|V| − 1, nên < 2|V|² lần nâng nhãn, < 2|V||E| lần đẩy bão hoà, < 4|V|²(|V| + |E|) lần đẩy không bão hoà, tổng O(V²E). Mục ★26.5 tổ chức các thao tác bằng danh sách đỉnh kề và thủ tục DISCHARGE, giữ danh sách L là sắp xếp topo của mạng chấp nhận được (một dag) và chuyển đỉnh vừa nâng nhãn lên đầu, được O(V³).

> **Lưu ý:**
> - **Mục có dấu sao (★):** Mục 26.4 "Push-relabel algorithms" và Mục 26.5 "The relabel-to-front algorithm". Bài tập có dấu sao: Exercise 26.3-4 (định lý Hall), 26.3-5 (đồ thị hai phía d-chính quy), 26.4-9 (duy trì độ cao bằng đúng khoảng cách), 26.5-2 (đẩy–nâng nhãn với hàng đợi FIFO), 26.5-4 (xả đỉnh tràn cao nhất).
> - **Lớp chữ PDF hỏng nặng ở chương này**: ký tự v nghiêng (đỉnh v) bị mất hoàn toàn (ví dụ `.u; /2 E` là `(u, v) ∈ E`, `f.  ;u /` là `f(v, u)`), dấu trừ thành `/NUL`, ⇝ thành `❀`, ≤ và ≥ mất, ↑ của phép tăng luồng thành `"`, các tổng kép và hệ phương trình nhiều trường hợp (26.2), (26.4), (26.8), (26.15), (26.16) vỡ dòng; nhãn các hình 26.1–26.11 bị trộn thành dãy số. Mọi pseudocode, công thức (26.1)–(26.17), mọi hình và chứng minh trong bản tổng hợp này được đọc lại từ ảnh **tất cả** các trang 708–768; Hình 26.8 và 26.11 được phóng to riêng để xác định cạnh và điểm xuất phát.
> - **Lỗi chính tả trong sách (nhận xét của người tổng hợp):** trang 717 viết "just send 3 creates from u to v" — đúng phải là "crates" (thùng hàng); trang 714, Exercise 26.1-7 viết "how much flow can pass though v" — đúng phải là "through"; trang 766 viết "shortest paths from the source to the sink tend have high capacity" — thiếu "to" ("tend to have"). Không ảnh hưởng nội dung.
> - **Chỗ ký hiệu chưa chặt (nhận xét của người tổng hợp):** (1) Lời giải thích của Bổ đề 26.14 suy "h(u) < h(v) + 1 kéo theo h(u) ≤ h(v)" ngầm dùng việc độ cao là số nguyên (h : V → ℕ) — đúng nhưng sách không nói. (2) Trong chứng minh Bổ đề 26.23, hàm thế Φ lấy tổng trên mọi đỉnh có luồng dư dương, kể cả đích t (t có thể có e(t) > 0); vì t.h = 0 nên không ảnh hưởng, nhưng sách không nhắc. (3) Định lý 26.24 kết luận O(V²E) từ tổng các cận 2|V|² + 2|V||E| + 4|V|²(|V| + |E|), tức O(V³ + V²E); bước gộp về O(V²E) cần |E| ≥ |V| − 1, giả định có từ Mục 26.1 nhưng không được nhắc lại. (4) Exercise 26.2-1 và Bổ đề 26.1 dùng "mở rộng tổng sang V vì số hạng thêm vào bằng 0" — với f′ điều này cần lập luận (f′(s, v) > 0 chỉ khi (s, v) hoặc (v, s) thuộc E), sách để thành bài tập. Người tổng hợp không chắc những chỗ này có trong danh sách lỗi chính thức (errata) của ấn bản 3 hay không — theo hiểu biết của người tổng hợp, không tra cứu.
> - **Mọi ví dụ chạy tay trong sách đã được tự kiểm tra lại và đúng:** luồng 19 trên mạng Lucky Puck (bảo toàn tại cả 4 đỉnh trung gian); lát cắt ({s, v₁, v₂}, {v₃, v₄, t}) có luồng ròng 19, sức chứa 26; năm vòng FORD-FULKERSON cho luồng 23 (4, 8, 12, 19, 23); mạng 4 đỉnh cần 2.000.000 lần tăng; DISCHARGE(y) đúng 15 vòng lặp; RELABEL-TO-FRONT trên mạng 5 đỉnh cho luồng 20 (người tổng hợp kiểm bằng lát cắt ({s, y}, {x, z, t}) sức chứa 12 + 8 = 20). Người tổng hợp bổ sung: Edmonds-Karp trên mạng Lucky Puck (3 lần tăng, 23), một ví dụ chạy tay thuật toán đẩy–nâng nhãn tổng quát (sách không có), và lời giải Exercise 26.5-1 (luồng 23).
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** do sắp xếp lại chương, luồng cực đại trở thành Chương 24 "Maximum Flow"; hai mục đẩy–nâng nhãn (26.4, 26.5 của ấn bản 3) bị **bỏ** khỏi chương; cặp ghép hai phía được tách thành chương mới "Matchings in Bipartite Graphs" (Chương 25), trong đó thuật toán Hopcroft-Karp (Problem 26-6 ở ấn bản 3) được trình bày trong phần chính, cùng bài toán hôn nhân ổn định và thuật toán Hungary cho bài toán phân công. Các khác biệt nhỏ hơn về lời văn và bài tập, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 26.1, trang 708–709) — mạng luồng là gì và chương đi theo trình tự nào

```text
       Đồ thị có hướng có thể mô hình bản đồ đường (đường đi ngắn nhất),
       cũng có thể mô hình DÒNG VẬT CHẤT: chất lỏng trong ống, linh kiện
       trên dây chuyền, dòng điện, thông tin trong mạng
                                │
                                ▼
       Mỗi cạnh là một ống dẫn có SỨC CHỨA (tốc độ tối đa);
       mỗi đỉnh khác nguồn và đích: vào bao nhiêu ra bấy nhiêu
       (BẢO TOÀN LUỒNG, tương đương định luật Kirchhoff)
                                │
                                ▼
       Bài toán LUỒNG CỰC ĐẠI: tốc độ lớn nhất chuyển vật chất từ nguồn s
       tới đích t mà không vượt sức chứa nào
                                │
                                ▼
       Hai phương pháp tổng quát:
       26.1 định nghĩa mạng luồng, luồng, bài toán
       26.2 phương pháp Ford-Fulkerson (cổ điển)
       26.3 ứng dụng: cặp ghép cực đại trên đồ thị hai phía
       26.4 ★ phương pháp đẩy–nâng nhãn (nền của các thuật toán nhanh nhất)
       26.5 ★ thuật toán relabel-to-front, O(V³)
```

### Mục 26.1 — Mạng luồng (Flow networks, trang 709–714)

```text
       MẠNG LUỒNG G = (V, E): đồ thị có hướng, c(u, v) ≥ 0 trên mỗi cạnh
       · không có cạnh ngược chiều: (u, v) ∈ E thì (v, u) ∉ E
       · c(u, v) = 0 nếu (u, v) ∉ E; không có khuyên
       · mọi đỉnh nằm trên một đường s ⇝ v ⇝ t ⇒ |E| ≥ |V| − 1
                                │
                                ▼
       LUỒNG f : V × V → ℝ thoả
       · ràng buộc sức chứa: 0 ≤ f(u, v) ≤ c(u, v)
       · bảo toàn luồng: Σ_v f(v, u) = Σ_v f(u, v) với u ∉ {s, t}
       GIÁ TRỊ |f| = Σ_v f(s, v) − Σ_v f(v, s)                    (26.1)
                                │
                                ▼
       Ví dụ Lucky Puck: Vancouver (s) → … → Winnipeg (t), 6 đỉnh,
       9 cạnh; một luồng có giá trị 19
                                │
           ┌────────────────────┴────────────────────┐
           ▼                                         ▼
   CẠNH NGƯỢC CHIỀU (v₁, v₂) và (v₂, v₁)     NHIỀU NGUỒN, NHIỀU ĐÍCH
   tách một cạnh bằng đỉnh mới v′:           thêm siêu nguồn s với cạnh
   (v₁, v′), (v′, v₂) cùng sức chứa          (s, sᵢ) sức chứa ∞ và siêu
                                             đích t với cạnh (tⱼ, t) ∞
           └────────────────────┬────────────────────┘
                                ▼
       Cả hai biến đổi cho mạng tương đương (Exercise 26.1-1, 26.1-2)
```

### Mục 26.2 — Phương pháp Ford-Fulkerson (The Ford-Fulkerson method, trang 714–731)

```text
       FORD-FULKERSON-METHOD: luồng 0; còn đường tăng luồng p trong
       mạng thặng dư G_f thì tăng luồng dọc p; trả về f
                                │
                                ▼
       MẠNG THẶNG DƯ G_f, sức chứa thặng dư                       (26.2)
       c_f(u, v) = c(u, v) − f(u, v)  nếu (u, v) ∈ E   (còn thêm được)
                 = f(v, u)            nếu (v, u) ∈ E   (trả lại được)
                 = 0                  còn lại
       |E_f| ≤ 2|E|; PHÉP TĂNG LUỒNG (f ↑ f′)(u, v)
       = f(u, v) + f′(u, v) − f′(v, u)                             (26.4)
       Bổ đề 26.1: f ↑ f′ là luồng, |f ↑ f′| = |f| + |f′|
                                │
                                ▼
       ĐƯỜNG TĂNG LUỒNG p: đường đơn s ⇝ t trong G_f;
       c_f(p) = min sức chứa thặng dư trên p
       Bổ đề 26.2 + Hệ quả 26.3: tăng dọc p cho luồng |f| + c_f(p) > |f|
                                │
                                ▼
       LÁT CẮT (S, T), s ∈ S, t ∈ T
       · luồng ròng f(S, T) = luồng S→T − luồng T→S              (26.9)
       · sức chứa c(S, T) = chỉ cộng cạnh S→T                     (26.10)
       Bổ đề 26.4: f(S, T) = |f| với MỌI lát cắt
       Hệ quả 26.5: |f| ≤ c(S, T) với mọi lát cắt
                                │
                                ▼
       ĐỊNH LÝ 26.6 (luồng cực đại – lát cắt cực tiểu): tương đương
       (1) f cực đại  ⇔ (2) G_f không có đường tăng luồng
                      ⇔ (3) |f| = c(S, T) với lát cắt nào đó
       (S = các đỉnh đến được từ s trong G_f)
                                │
                                ▼
       FORD-FULKERSON (cài đặt): sức chứa nguyên ⇒ ≤ |f*| vòng,
       mỗi vòng O(E) ⇒ O(E |f*|); chọn đường tồi: mạng 4 đỉnh cần
       2.000.000 vòng; sức chứa vô tỷ: có thể không dừng
                                │
                                ▼
       EDMONDS-KARP: tìm đường bằng BFS (ít cạnh nhất)
       · Bổ đề 26.7: δ_f(s, v) không giảm qua các lần tăng
       · Định lý 26.8: mỗi cạnh tới hạn ≤ |V|/2 lần ⇒ O(VE) lần tăng
       ⇒ thời gian O(VE²)
```

### Mục 26.3 — Cặp ghép cực đại trên đồ thị hai phía (Maximum bipartite matching, trang 732–736)

```text
       Đồ thị hai phía vô hướng G = (V, E), V = L ∪ R
       CẶP GHÉP M ⊆ E: mỗi đỉnh thuộc nhiều nhất một cạnh của M
       Cần: cặp ghép có nhiều cạnh nhất (ví dụ máy L – việc R)
                                │
                                ▼
       MẠNG TƯƠNG ỨNG G′: thêm s → mọi u ∈ L, cạnh E hướng L → R,
       mọi v ∈ R → t; mọi sức chứa bằng 1; |E′| = Θ(E)
                                │
                                ▼
       Bổ đề 26.9: cặp ghép M ↔ luồng NGUYÊN f, |f| = |M|
       (đọc qua lát cắt (L ∪ {s}, R ∪ {t}))
                                │
                                ▼
       Định lý 26.10 (tính nguyên): sức chứa nguyên ⇒ Ford-Fulkerson
       cho luồng cực đại có mọi f(u, v) nguyên
                                │
                                ▼
       Hệ quả 26.11: cỡ cặp ghép cực đại = giá trị luồng cực đại trong G′
       |f*| ≤ min(|L|, |R|) = O(V) ⇒ thời gian O(VE)
```

### Mục ★26.4 — Thuật toán đẩy–nâng nhãn (Push-relabel algorithms, trang 736–748)

```text
       Làm việc CỤC BỘ trên từng đỉnh; không giữ bảo toàn luồng mà giữ
       TIỀN LUỒNG: luồng vào ≥ luồng ra tại mọi u ≠ s
       LUỒNG DƯ e(u) = vào − ra                                    (26.14)
       ĐỈNH TRÀN: u ∉ {s, t}, e(u) > 0
                                │
                                ▼
       Trực giác: đỉnh đặt trên bệ có độ cao; luồng chỉ chảy XUỐNG DỐC;
       nguồn cố định ở |V|, đích ở 0; kẹt thì NÂNG đỉnh lên; luồng không
       tới được đích thì đỉnh được nâng cao hơn |V| để trả về nguồn
                                │
                                ▼
       HÀM ĐỘ CAO h: h(s) = |V|, h(t) = 0, h(u) ≤ h(v) + 1 trên mọi cạnh
       thặng dư (Bổ đề 26.12: chênh > 1 thì không có cạnh thặng dư)
                                │
           ┌────────────────────┴────────────────────┐
           ▼                                         ▼
   PUSH(u, v): u tràn, c_f(u, v) > 0,       RELABEL(u): u tràn, mọi cạnh
   u.h = v.h + 1; đẩy min(u.e, c_f(u, v))   thặng dư rời u dẫn tới đỉnh
   · đẩy bão hoà / không bão hoà            không thấp hơn; u.h = 1 +
   · không bão hoà ⇒ u hết tràn (26.13)     min{v.h : (u, v) ∈ E_f}
           └────────────────────┬────────────────────┘
                                ▼
       GENERIC-PUSH-RELABEL: INITIALIZE-PREFLOW (lấp đầy cạnh rời s,
       s.h = |V|) rồi làm thao tác áp dụng được theo thứ tự bất kỳ
       Bổ đề 26.14: đỉnh tràn luôn đẩy được hoặc nâng nhãn được
                                │
                                ▼
       TÍNH ĐÚNG: độ cao không giảm (26.15); h luôn là hàm độ cao (26.16);
       h là hàm độ cao ⇒ không có đường s ⇝ t trong G_f (26.17)
       ⇒ khi dừng (không đỉnh tràn), f là luồng và cực đại (Định lý 26.18)
                                │
                                ▼
       PHÂN TÍCH: đỉnh tràn có đường thặng dư về s (26.19)
       ⇒ u.h ≤ 2|V| − 1 (26.20)
       · nâng nhãn < 2|V|² (Hệ quả 26.21)
       · đẩy bão hoà < 2|V||E| (Bổ đề 26.22)
       · đẩy không bão hoà < 4|V|²(|V| + |E|) (Bổ đề 26.23, hàm thế
         Φ = tổng độ cao các đỉnh tràn)
       ⇒ O(V²E) thao tác (Định lý 26.24), cài đặt O(V²E) (Hệ quả 26.25)
```

### Mục ★26.5 — Thuật toán nâng nhãn rồi đưa lên đầu (The relabel-to-front algorithm, trang 748–760)

```text
       Chọn thứ tự thao tác khéo léo để được O(V³) (tốt hơn O(V²E) khi
       mạng dày)
                                │
                                ▼
       CẠNH CHẤP NHẬN ĐƯỢC: c_f(u, v) > 0 và h(u) = h(v) + 1
       Mạng chấp nhận được G_{f,h} KHÔNG CÓ CHU TRÌNH (Bổ đề 26.26)
       · đẩy không tạo cạnh chấp nhận được mới (26.27)
       · sau nâng nhãn u: có cạnh chấp nhận được ra khỏi u, không có
         cạnh chấp nhận được vào u (26.28)
                                │
                                ▼
       DANH SÁCH ĐỈNH KỀ u.N (đỉnh v có (u, v) hoặc (v, u) ∈ E) với con
       trỏ u.current
       DISCHARGE(u): còn luồng dư thì
       · current = NIL ⇒ RELABEL(u), quay về đầu danh sách
       · (u, current) chấp nhận được ⇒ PUSH
       · ngược lại ⇒ dịch current
       Bổ đề 26.29: PUSH và RELABEL gọi ra luôn áp dụng được
       Ví dụ: xả đỉnh y mất 15 vòng lặp
                                │
                                ▼
       RELABEL-TO-FRONT: danh sách L = V − {s, t}; lần lượt xả từng đỉnh;
       đỉnh nào được nâng nhãn thì chuyển lên ĐẦU L
       Bất biến: L là sắp xếp topo của mạng chấp nhận được, không đỉnh
       nào đứng trước u có luồng dư ⇒ khi hết danh sách, không còn đỉnh tràn
                                │
                                ▼
       Định lý 26.30: O(V²) pha (giữa hai lần nâng nhãn) × ≤ |V| lần
       DISCHARGE ⇒ O(V³) lần gọi, mỗi lần nhiều nhất 1 lần đẩy không bão
       hoà; nâng nhãn O(VE), dịch con trỏ O(VE), đẩy bão hoà O(VE)
       ⇒ O(V³)
```

### Bài toán cuối chương (Problems 26-1 đến 26-6, trang 760–765)

```text
       26-1 Thoát hiểm trên lưới n × n: m đường rời nhau về đỉnh tới biên
            ⇒ sức chứa đỉnh 1 (tách đỉnh), siêu nguồn/siêu đích
                                │
                                ▼
       26-2 Phủ đường tối thiểu của DAG: tách đỉnh thành x_i (ra), y_i (vào),
            luồng cực đại = cặp ghép; số đường = n − |f*|; sai khi có chu trình
                                │
                                ▼
       26-3 Tư vấn thuật toán (chọn chuyên gia và dự án): cạnh ∞ từ A_k tới J_i;
            lợi nhuận cực đại = Σ p_i − sức chứa lát cắt cực tiểu
                                │
                                ▼
       26-4 Cập nhật luồng cực đại khi một sức chứa tăng/giảm 1: O(V + E)
                                │
                                ▼
       26-5 Co giãn (scaling): chỉ tăng dọc đường có sức chứa ≥ K, K giảm
            một nửa mỗi pha ⇒ O(E² lg C)
                                │
                                ▼
       26-6 Hopcroft-Karp: mỗi vòng tăng theo một tập tối đại đường tăng
            ngắn nhất rời nhau; ≤ 2√|V| vòng, mỗi vòng O(E) ⇒ O(√V E)
```

### Ghi chú chương (Chapter notes, trang 765–766)

```text
       Tài liệu: Ahuja–Magnanti–Orlin, Even, Lawler, Papadimitriou–Steiglitz,
       Tarjan; khảo sát của Goldberg–Tardos–Tarjan; lịch sử của Schrijver
                                │
                                ▼
       Ford–Fulkerson: phương pháp và nghiên cứu hình thức luồng mạng;
       Edmonds–Karp và Dinic (độc lập): BFS cho thời gian đa thức;
       Dinic: luồng chặn; Karzanov: tiền luồng
                                │
                                ▼
       Đẩy–nâng nhãn: Goldberg; Goldberg–Tarjan (O(V³) với hàng đợi,
       O(VE lg(V²/E + 2)) với cây động); ... King–Rao–Tarjan
       O(VE log_{E/(V lg V)} V)
                                │
                                ▼
       Nhanh nhất về tiệm cận: Goldberg–Rao, dựa trên luồng chặn với độ
       dài cạnh 0/1 theo sức chứa
                                │
                                ▼
       Thực tế: đẩy–nâng nhãn thống trị; cần hai heuristic (BFS định kỳ
       để chỉnh độ cao, heuristic khe hở); tốt nhất là xả đỉnh cao nhất
                                │
                                ▼
       Cặp ghép hai phía: Hopcroft–Karp O(√V E); sách của Lovász–Plummer
```

## Ba câu hỏi chương này trả lời

1. **Làm sao biết một luồng đã là lớn nhất?** Nhờ định lý luồng cực đại – lát cắt cực tiểu (Định lý 26.6): ba điều sau tương đương — f là luồng cực đại; mạng thặng dư G_f không còn đường đi từ s tới t; |f| bằng sức chứa của một lát cắt (S, T) nào đó. Chìa khoá là hai bổ đề: luồng ròng qua mọi lát cắt đều bằng |f| (Bổ đề 26.4), nên |f| không vượt sức chứa của bất kỳ lát cắt nào (Hệ quả 26.5). Khi G_f hết đường tăng luồng, tập S các đỉnh đến được từ s cho một lát cắt mà mọi cạnh S → T bão hoà và mọi cạnh T → S rỗng, nên |f| = c(S, T) — vừa là luồng vừa là "giấy chứng nhận" tối ưu. Ví dụ Lucky Puck: luồng 23 và lát cắt ({s, v₁, v₂, v₄}, {v₃, t}) có sức chứa 12 + 7 + 4 = 23.
2. **Tìm luồng cực đại nhanh đến đâu, và chọn đường tăng luồng thế nào?** Ford-Fulkerson với sức chứa nguyên chạy O(E|f*|) — có thể rất chậm: mạng 4 đỉnh với sức chứa 1.000.000 cần 2.000.000 lần tăng nếu chọn đường xui; với sức chứa vô tỷ có thể không dừng. Edmonds-Karp chọn đường ít cạnh nhất bằng BFS: khoảng cách δ_f(s, v) không giảm, mỗi cạnh trở thành tới hạn nhiều nhất |V|/2 lần, nên O(VE) lần tăng, O(VE²) thời gian, không phụ thuộc giá trị sức chứa (trên mạng 4 đỉnh trên chỉ cần 2 lần tăng). Thuật toán đẩy–nâng nhãn tổng quát đạt O(V²E), và relabel-to-front đạt O(V³).
3. **Phương pháp đẩy–nâng nhãn hoạt động và đúng như thế nào?** Nó đổ đầy mọi cạnh rời nguồn (tiền luồng), rồi cục bộ đẩy luồng dư từ đỉnh cao xuống đỉnh thấp hơn đúng 1 bậc, và nâng nhãn đỉnh bị kẹt lên 1 + độ cao thấp nhất của đỉnh kề còn cạnh thặng dư. Hàm độ cao với h(s) = |V| bảo đảm suốt quá trình không có đường s ⇝ t trong G_f (vì đường đơn có < |V| cạnh, mỗi cạnh chỉ hạ được 1 bậc); khi hết đỉnh tràn, tiền luồng là luồng và theo định lý luồng cực đại – lát cắt cực tiểu, nó cực đại. Độ cao không vượt 2|V| − 1 cho các cận < 2|V|² lần nâng nhãn, < 2|V||E| lần đẩy bão hoà, < 4|V|²(|V| + |E|) lần đẩy không bão hoà. Relabel-to-front giữ danh sách đỉnh theo thứ tự topo của mạng chấp nhận được, chuyển đỉnh vừa nâng nhãn lên đầu, nên mỗi "pha" giữa hai lần nâng nhãn có ≤ |V| lần xả: O(V³).

## Khái niệm cần biết

- **Mạng luồng (flow network):** đồ thị có hướng G = (V, E), mỗi cạnh có sức chứa c(u, v) ≥ 0, có nguồn s và đích t, không có cặp cạnh ngược chiều, mọi đỉnh nằm trên một đường s ⇝ v ⇝ t. Ví dụ: mạng Lucky Puck 6 đỉnh, 9 cạnh, c(s, v₁) = 16, c(v₁, v₃) = 12. Quan trọng vì là đối tượng của cả chương.
- **Sức chứa (capacity):** tốc độ tối đa vật chất đi qua một cạnh; c(u, v) = 0 nếu không có cạnh. Ví dụ: tuyến Vancouver → Edmonton chở tối đa 16 thùng/ngày.
- **Luồng (flow) và giá trị luồng |f|:** hàm f thoả ràng buộc sức chứa 0 ≤ f(u, v) ≤ c(u, v) và bảo toàn luồng tại mọi đỉnh trừ s, t; |f| = luồng ra khỏi s trừ luồng vào s. Ví dụ: luồng trên mạng Lucky Puck với f(s, v₁) = 11, f(s, v₂) = 8 có |f| = 19; tại v₂ vào 8 + 4 = 12, ra 1 + 11 = 12.
- **Cạnh ngược chiều (antiparallel edges):** cặp (u, v), (v, u) cùng thuộc E; bị cấm, khử bằng cách tách một cạnh qua đỉnh mới. Ví dụ: thêm Edmonton → Calgary sức chứa 10 trong khi đã có Calgary → Edmonton sức chứa 4; thay bằng v₁ → v′ → v₂, mỗi cạnh sức chứa 10. Quan trọng vì giả định này làm định nghĩa mạng thặng dư (26.2) không mơ hồ.
- **Siêu nguồn, siêu đích (supersource, supersink):** đỉnh mới nối tới mọi nguồn (hoặc từ mọi đích) bằng cạnh sức chứa ∞, biến bài toán nhiều nguồn nhiều đích thành bài toán thường. Ví dụ: 5 nhà máy, 3 kho thì thêm 8 cạnh sức chứa ∞.
- **Sức chứa thặng dư (residual capacity) và mạng thặng dư (residual network) G_f:** c_f(u, v) = c(u, v) − f(u, v) trên cạnh gốc (còn thêm được), c_f(v, u) = f(u, v) trên cạnh ngược (có thể trả lại); G_f gồm các cặp có c_f > 0, |E_f| ≤ 2|E|. Ví dụ: c = 16, f = 11 thì c_f(u, v) = 5, c_f(v, u) = 11. Quan trọng vì mọi thuật toán của chương làm việc trên G_f.
- **Phép tăng luồng f ↑ f′ (augmentation) và triệt tiêu (cancellation):** cộng luồng f′ của mạng thặng dư vào f, trong đó đẩy trên cạnh ngược nghĩa là giảm luồng gốc. Ví dụ: gửi 5 thùng u → v rồi 2 thùng v → u tương đương gửi 3 thùng u → v. Bổ đề 26.1: |f ↑ f′| = |f| + |f′|.
- **Đường tăng luồng (augmenting path) và sức chứa của đường c_f(p):** đường đơn s ⇝ t trong G_f; c_f(p) là sức chứa thặng dư nhỏ nhất trên đường. Ví dụ: s → v₂ → v₃ → t trong G_f của luồng 19 có các sức chứa 5, 4, 5, nên c_f(p) = 4, luồng tăng lên 23.
- **Lát cắt (cut), luồng ròng f(S, T) và sức chứa c(S, T):** phân hoạch V với s ∈ S, t ∈ T; luồng ròng tính luồng S → T trừ T → S, sức chứa chỉ cộng cạnh S → T. Ví dụ: S = {s, v₁, v₂}: luồng ròng 12 + 11 − 4 = 19, sức chứa 12 + 14 = 26. Quan trọng vì lát cắt cho cận trên của mọi luồng.
- **Lát cắt cực tiểu (minimum cut) và định lý luồng cực đại – lát cắt cực tiểu:** lát cắt có sức chứa nhỏ nhất; giá trị luồng cực đại bằng sức chứa lát cắt cực tiểu. Ví dụ: Lucky Puck: 23 = c({s, v₁, v₂, v₄}, {v₃, t}).
- **Cạnh tới hạn (critical edge):** cạnh trên đường tăng luồng có sức chứa thặng dư bằng c_f(p), biến mất sau khi tăng. Ví dụ: ở đường s → v₂ → v₃ → t trên, cạnh (v₂, v₃) với sức chứa 4 là tới hạn. Quan trọng trong chứng minh Edmonds-Karp O(VE) lần tăng.
- **Cặp ghép (matching), cặp ghép cực đại, cặp ghép hoàn hảo:** tập cạnh không chung đỉnh; cực đại là có nhiều cạnh nhất; hoàn hảo là mọi đỉnh được ghép. Ví dụ: với L = {1, …, 5}, R = {6, …, 9} và cạnh 1–6, 2–6, 2–8, 3–7, 3–8, 3–9, 4–8, 5–8, cặp ghép cực đại có 3 cạnh, chẳng hạn {2–6, 3–7, 5–8}.
- **Luồng nhận giá trị nguyên và định lý tính nguyên (integrality theorem):** sức chứa nguyên thì Ford-Fulkerson cho luồng cực đại với mọi f(u, v) nguyên. Ví dụ: trên mạng cặp ghép sức chứa 1, mỗi cạnh mang luồng 0 hoặc 1, đọc thẳng ra cặp ghép. Quan trọng vì thiếu nó, luồng phân số không cho cặp ghép.
- **Tiền luồng (preflow), luồng dư e(u) và đỉnh tràn (overflowing vertex):** tiền luồng thoả ràng buộc sức chứa và "vào ≥ ra" tại mọi đỉnh trừ s; e(u) = vào − ra; đỉnh tràn là đỉnh khác s, t có e(u) > 0. Ví dụ: sau khởi tạo trên mạng relabel-to-front, e(x) = 12, e(y) = 14, e(s) = −26.
- **Hàm độ cao (height function):** h(s) = |V|, h(t) = 0, h(u) ≤ h(v) + 1 trên mọi cạnh thặng dư (u, v). Ví dụ: |V| = 5 thì s.h = 5; đỉnh y được nâng dần 0 → 1 → 2 → 6. Quan trọng vì nó bảo đảm không có đường s ⇝ t trong G_f.
- **Đẩy (push) bão hoà và không bão hoà:** chuyển min(u.e, c_f(u, v)) đơn vị từ u xuống v khi u.h = v.h + 1; bão hoà nếu cạnh hết sức chứa thặng dư. Ví dụ: y có e = 19 đẩy 8 sang z qua cạnh sức chứa 8 (bão hoà); x có e = 5 đẩy 5 sang t qua cạnh còn 9 (không bão hoà, x hết tràn).
- **Nâng nhãn (relabel):** đặt u.h = 1 + min{v.h : (u, v) ∈ E_f} khi u tràn mà không đẩy được. Ví dụ: y có cạnh thặng dư tới s (cao 5), x (cao 1), z (cao 0), nên y.h = 1.
- **Hàm thế (potential function) Φ:** tổng độ cao các đỉnh có luồng dư dương; mỗi lần đẩy không bão hoà làm Φ giảm ít nhất 1, nâng nhãn và đẩy bão hoà làm Φ tăng < 2|V|. Kỹ thuật của Chương 17.
- **Cạnh chấp nhận được, mạng chấp nhận được (admissible edge/network):** cạnh thặng dư có h(u) = h(v) + 1; mạng các cạnh này không có chu trình. Ví dụ: sau khi x.h = 1, cạnh (x, y) với y.h = 0 và c_f = 5 là chấp nhận được.
- **Danh sách đỉnh kề (neighbor list), con trỏ current và thao tác xả (discharge):** u.N chứa mọi v có (u, v) hoặc (v, u) trong E; DISCHARGE(u) dùng u.current để duyệt, đẩy khi được, nâng nhãn khi hết danh sách, cho tới khi u hết luồng dư. Ví dụ: xả y với y.N = ⟨s, x, z⟩ mất 15 vòng lặp.
- **Sắp xếp topo (topological sort):** thứ tự đỉnh của một dag sao cho mọi cạnh đi từ trước ra sau (Chương 22). Relabel-to-front giữ L là sắp xếp topo của mạng chấp nhận được, nên luồng chỉ bị đẩy về phía sau danh sách.
- **Edmonds-Karp, Dinic, co giãn (scaling), Hopcroft-Karp:** các biến thể đường tăng luồng: đường ngắn nhất (O(VE²)), luồng chặn trên đồ thị phân tầng (ghi chú chương), chỉ dùng đường sức chứa ≥ K (O(E² lg C), Problem 26-5), nhiều đường tăng ngắn nhất rời nhau cho cặp ghép (O(√V E), Problem 26-6).
## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 708–709)

Giống như có thể mô hình hoá bản đồ đường sá bằng một đồ thị có hướng để tìm đường đi ngắn nhất từ điểm này tới điểm kia, ta cũng có thể coi một đồ thị có hướng là một **mạng luồng** (flow network) và dùng nó để trả lời các câu hỏi về dòng vật chất. Hãy hình dung một thứ vật chất chảy qua một hệ thống, từ một **nguồn** (source), nơi vật chất được sản xuất, tới một **đích** (sink), nơi vật chất được tiêu thụ. Nguồn sản xuất với một tốc độ ổn định nào đó, và đích tiêu thụ với cùng tốc độ ấy. "Luồng" (flow) của vật chất tại một điểm bất kỳ trong hệ thống, về trực giác, là tốc độ vật chất di chuyển qua điểm đó. Mạng luồng mô hình hoá được nhiều bài toán: chất lỏng chảy trong đường ống, linh kiện đi qua dây chuyền lắp ráp, dòng điện trong mạng điện, thông tin trong mạng truyền thông.

Có thể coi mỗi cạnh có hướng của mạng luồng là một **ống dẫn** cho vật chất. Mỗi ống có một **khả năng thông qua** (capacity — trong tổng hợp này gọi thống nhất là **sức chứa**) cho trước, là tốc độ tối đa vật chất có thể chảy qua ống, ví dụ 200 gallon chất lỏng mỗi giờ qua một ống nước, hay 20 ampe dòng điện qua một sợi dây. Các đỉnh là các điểm nối ống; trừ nguồn và đích, vật chất chảy qua đỉnh mà không tích tụ lại ở đó. Nói cách khác, tốc độ vật chất đi vào một đỉnh phải bằng tốc độ nó đi ra khỏi đỉnh. Tính chất này gọi là **bảo toàn luồng** (flow conservation); khi vật chất là dòng điện, nó chính là định luật Kirchhoff về dòng điện.

Trong **bài toán luồng cực đại** (maximum-flow problem), ta muốn tính tốc độ lớn nhất có thể chuyển vật chất từ nguồn tới đích mà không vi phạm ràng buộc sức chứa nào. Đây là một trong những bài toán đơn giản nhất về mạng luồng, và như chương sẽ cho thấy, nó giải được bằng các thuật toán hiệu quả. Hơn nữa, các kỹ thuật cơ bản dùng trong thuật toán luồng cực đại có thể điều chỉnh để giải các bài toán luồng mạng khác.

Chương trình bày **hai phương pháp tổng quát**:

- Mục 26.1 hình thức hoá khái niệm mạng luồng và luồng, định nghĩa chính xác bài toán luồng cực đại.
- Mục 26.2 trình bày phương pháp cổ điển của Ford và Fulkerson để tìm luồng cực đại.
- Mục 26.3 là một ứng dụng của phương pháp đó: tìm cặp ghép cực đại trong đồ thị hai phía vô hướng.
- Mục 26.4 (★) trình bày phương pháp đẩy–nâng nhãn (push-relabel), nền tảng của nhiều thuật toán nhanh nhất cho các bài toán luồng mạng.
- Mục 26.5 (★) trình bày thuật toán "nâng nhãn rồi đưa lên đầu" (relabel-to-front), một cài đặt cụ thể của phương pháp đẩy–nâng nhãn chạy trong thời gian O(V³). Thuật toán này không phải nhanh nhất đã biết, nhưng minh hoạ một số kỹ thuật dùng trong các thuật toán nhanh nhất về tiệm cận, và chạy khá hiệu quả trong thực tế.

### 2. Mạng luồng (26.1 Flow networks, trang 709–714)

Mục này cho định nghĩa đồ thị của mạng luồng, bàn các tính chất, định nghĩa chính xác bài toán luồng cực đại và đưa vào một số ký hiệu.

#### Mạng luồng và luồng (Flow networks and flows)

**Mạng luồng** G = (V, E) là một đồ thị có hướng, trong đó mỗi cạnh (u, v) ∈ E có một **sức chứa** không âm c(u, v) ≥ 0. Ta yêu cầu thêm: nếu E chứa cạnh (u, v) thì **không có** cạnh (v, u) theo chiều ngược lại (sẽ thấy ngay sau đây cách lách hạn chế này). Nếu (u, v) ∉ E, để tiện ta định nghĩa c(u, v) = 0; và không cho phép khuyên (cạnh từ một đỉnh tới chính nó). Có hai đỉnh đặc biệt: **nguồn** s và **đích** t. Để tiện, ta giả định mọi đỉnh đều nằm trên một đường đi nào đó từ nguồn tới đích: với mọi v ∈ V, mạng chứa một đường đi s ⇝ v ⇝ t. Do đó đồ thị liên thông, và vì mọi đỉnh khác s có ít nhất một cạnh đi vào, |E| ≥ |V| − 1.

Cho G = (V, E) là mạng luồng với hàm sức chứa c, nguồn s, đích t. Một **luồng** (flow) trong G là hàm giá trị thực f : V × V → ℝ thoả hai tính chất:

- **Ràng buộc sức chứa (capacity constraint):** với mọi u, v ∈ V, 0 ≤ f(u, v) ≤ c(u, v).
- **Bảo toàn luồng (flow conservation):** với mọi u ∈ V − {s, t},

```text
Σ_{v∈V} f(v, u) = Σ_{v∈V} f(u, v)
```

Khi (u, v) ∉ E thì không thể có luồng từ u sang v, và f(u, v) = 0.

Đại lượng không âm f(u, v) gọi là luồng từ đỉnh u tới đỉnh v. **Giá trị** |f| của luồng f định nghĩa là

```text
|f| = Σ_{v∈V} f(s, v) − Σ_{v∈V} f(v, s)                              (26.1)
```

tức là tổng luồng đi ra khỏi nguồn trừ tổng luồng đi vào nguồn. (Ở đây ký hiệu |·| chỉ giá trị luồng, không phải giá trị tuyệt đối hay lực lượng tập hợp.) Thông thường mạng không có cạnh nào đi vào nguồn, nên tổng Σ_{v∈V} f(v, s) bằng 0. Sách vẫn giữ số hạng này vì khi đưa vào mạng thặng dư, luồng đi vào nguồn sẽ có ý nghĩa. Trong bài toán luồng cực đại, cho mạng luồng G với nguồn s và đích t, ta muốn tìm một luồng có giá trị lớn nhất.

Ý nghĩa hai tính chất: ràng buộc sức chứa nói luồng từ đỉnh này sang đỉnh kia phải không âm và không vượt sức chứa; bảo toàn luồng nói tổng luồng vào một đỉnh (khác nguồn và đích) bằng tổng luồng ra khỏi đỉnh đó — nói nôm na, "vào bao nhiêu ra bấy nhiêu".

#### Một ví dụ về luồng (An example of flow) — mạng vận tải của công ty Lucky Puck

Công ty Lucky Puck có nhà máy sản xuất bóng khúc côn cầu (puck) ở Vancouver (nguồn s) và nhà kho ở Winnipeg (đích t). Công ty thuê chỗ trên xe tải của một hãng khác để chở hàng từ nhà máy về kho. Xe tải đi theo các tuyến cố định (cạnh) giữa các thành phố (đỉnh) và có sức chở giới hạn, nên Lucky Puck chỉ chở được tối đa c(u, v) thùng mỗi ngày giữa hai thành phố u và v. Công ty không kiểm soát được tuyến và sức chở, nên không thể thay đổi mạng. Họ cần xác định số thùng lớn nhất p có thể chở mỗi ngày, rồi sản xuất đúng lượng đó (sản xuất nhiều hơn mức chở được là vô ích). Họ không quan tâm một quả bóng mất bao lâu để đến nơi; chỉ cần p thùng mỗi ngày rời nhà máy và p thùng mỗi ngày tới kho. Mô hình bằng luồng hợp lý vì số thùng chở mỗi ngày trên một tuyến bị chặn bởi sức chở (ràng buộc sức chứa), và ở trạng thái ổn định, tốc độ hàng vào một thành phố trung gian phải bằng tốc độ hàng ra (bảo toàn luồng), nếu không hàng sẽ ùn lại ở các thành phố trung gian.

Mạng của ví dụ (vẽ lại Hình 26.1(a) của sách). Các đỉnh: s = Vancouver, v₁ = Edmonton, v₂ = Calgary, v₃ = Saskatoon, v₄ = Regina, t = Winnipeg. Các cạnh và sức chứa:

| Cạnh | Sức chứa c | Luồng f trong Hình 26.1(b) (ghi f/c) |
|---|---|---|
| s → v₁ | 16 | 11/16 |
| s → v₂ | 13 | 8/13 |
| v₂ → v₁ | 4 | 1/4 |
| v₁ → v₃ | 12 | 12/12 |
| v₃ → v₂ | 9 | 4/9 |
| v₂ → v₄ | 14 | 11/14 |
| v₄ → v₃ | 7 | 7/7 |
| v₃ → t | 20 | 15/20 |
| v₄ → t | 4 | 4/4 |

```text
   Mạng Lucky Puck (Hình 26.1(a)), sức chứa ghi trên cạnh:

                 16          12           20
   s (Vancouver) ──▶ v₁ (Edmonton) ──▶ v₃ (Saskatoon) ──▶ t (Winnipeg)
        │                 ▲              │      ▲               ▲
      13│                4│             9│     7│               │4
        ▼                 │              ▼      │               │
   v₂ (Calgary) ──────────┘◀─────────────┘      │               │
        │      (v₂→v₁: 4)     (v₃→v₂: 9)        │               │
        └──────────14──────────▶ v₄ (Regina) ───┴───────────────┘
                                      (v₄→v₃: 7, v₄→t: 4)
```

Ký hiệu "f/c" trên mỗi cạnh chỉ dùng để tách luồng và sức chứa, không phải phép chia. Luồng ở cột cuối có giá trị |f| = f(s, v₁) + f(s, v₂) = 11 + 8 = 19. Kiểm tra bảo toàn luồng (người tổng hợp): tại v₁: vào 11 + 1 = 12, ra 12; tại v₂: vào 8 + 4 = 12, ra 1 + 11 = 12; tại v₃: vào 12 + 7 = 19, ra 4 + 15 = 19; tại v₄: vào 11, ra 7 + 4 = 11. Luồng vào t là 15 + 4 = 19, bằng giá trị luồng.

#### Mô hình hoá bài toán có cạnh ngược chiều nhau (Modeling problems with antiparallel edges)

Giả sử hãng vận tải cho Lucky Puck thuê thêm chỗ cho 10 thùng trên xe từ Edmonton (v₁) tới Calgary (v₂). Tự nhiên là thêm cạnh (v₁, v₂) sức chứa 10 vào mạng. Nhưng khi đó mạng vi phạm giả định ban đầu: (v₁, v₂) ∈ E và (v₂, v₁) ∈ E. Hai cạnh (v₁, v₂) và (v₂, v₁) như vậy gọi là **cạnh ngược chiều** (antiparallel). Để mô hình bài toán có cạnh ngược chiều, ta biến đổi mạng thành một mạng tương đương không có cạnh ngược chiều: chọn một trong hai cạnh, ở đây là (v₁, v₂), và **tách** nó bằng cách thêm một đỉnh mới v′, thay (v₁, v₂) bằng cặp cạnh (v₁, v′) và (v′, v₂), cả hai có sức chứa bằng sức chứa cạnh gốc (10). Mạng thu được thoả: nếu một cạnh có trong mạng thì cạnh ngược của nó không có.

```text
   Trước (Hình 26.2(a)):          Sau (Hình 26.2(b)):
   v₁ ──10──▶ v₂                  v₁ ──10──▶ v′ ──10──▶ v₂
   v₁ ◀──4─── v₂                  v₁ ◀──────4───────── v₂
   (các cạnh khác giữ nguyên như mạng Lucky Puck)
```

Exercise 26.1-1 yêu cầu chứng minh mạng mới tương đương mạng cũ. Như vậy, bài toán thực tế có thể được mô hình tự nhiên nhất bằng mạng có cạnh ngược chiều; sách cấm cạnh ngược chiều cho tiện, và có cách chuyển đơn giản sang mạng tương đương.

#### Mạng có nhiều nguồn và nhiều đích (Networks with multiple sources and sinks)

Một bài toán luồng cực đại có thể có nhiều nguồn và nhiều đích. Chẳng hạn Lucky Puck có thể có m nhà máy {s₁, s₂, …, s_m} và n nhà kho {t₁, t₂, …, t_n}. Bài toán này không khó hơn luồng cực đại thông thường. Ta quy về bài toán một nguồn một đích: thêm một **siêu nguồn** (supersource) s và cạnh có hướng (s, sᵢ) với sức chứa c(s, sᵢ) = ∞ cho mỗi i = 1, 2, …, m; thêm một **siêu đích** (supersink) t và cạnh (tᵢ, t) với c(tᵢ, t) = ∞ cho mỗi i = 1, 2, …, n. Về trực giác, mọi luồng trong mạng nhiều nguồn tương ứng với một luồng trong mạng mới và ngược lại: siêu nguồn cung cấp bao nhiêu luồng cũng được cho các nguồn sᵢ, siêu đích tiêu thụ bao nhiêu cũng được từ các đích tᵢ (Exercise 26.1-2 yêu cầu chứng minh hình thức).

Ví dụ của sách (vẽ lại Hình 26.3): năm nguồn s₁…s₅, ba đích t₁, t₂, t₃ và bốn đỉnh trung gian (người tổng hợp đặt tên a, b, c, d từ trên xuống):

| Cạnh | Sức chứa | Cạnh | Sức chứa |
|---|---|---|---|
| s₁ → a | 10 | b → t₂ | 6 |
| s₂ → a | 12 | s₃ → c | 14 |
| a → t₁ | 3 | s₄ → c | 7 |
| s₂ → b | 5 | c → t₂ | 20 |
| s₃ → b | 8 | c → t₃ | 13 |
| b → t₁ | 15 | s₄ → d | 11 |
| s₅ → d | 2 | d → t₃ | 18 |

Mạng tương đương thêm siêu nguồn s với năm cạnh s → sᵢ sức chứa ∞ và siêu đích t với ba cạnh tⱼ → t sức chứa ∞.

```text
          ∞ ┌─▶ s₁ ─┐                 ┌─ t₁ ─┐ ∞
          ∞ ├─▶ s₂ ─┤   mạng gốc      ├─ t₂ ─┼──▶ t
     s ─────┼─▶ s₃ ─┤  (các cạnh ở    ├─ t₃ ─┘ ∞
          ∞ ├─▶ s₄ ─┤   bảng trên)    │
          ∞ └─▶ s₅ ─┘                 │
```

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp, kỹ thuật "thêm siêu nguồn/siêu đích" và "tách cạnh hay tách đỉnh" là bước dựng mô hình đầu tiên trong hầu hết các bài toán luồng thực tế: lập kế hoạch vận chuyển hàng từ nhiều kho tới nhiều cửa hàng, phân bổ băng thông trong mạng máy tính, gán ca trực cho nhân viên.

### 3. Phương pháp Ford-Fulkerson (26.2 The Ford-Fulkerson method, trang 714–731)

Mục này trình bày phương pháp Ford-Fulkerson. Sách gọi nó là "phương pháp" chứ không phải "thuật toán" vì nó bao gồm nhiều cách cài đặt với thời gian chạy khác nhau. Phương pháp dựa vào ba ý tưởng quan trọng, vượt ra ngoài phạm vi phương pháp và liên quan tới nhiều thuật toán, bài toán luồng khác: **mạng thặng dư** (residual networks), **đường tăng luồng** (augmenting paths) và **lát cắt** (cuts). Ba ý này là cốt lõi của định lý luồng cực đại – lát cắt cực tiểu (Định lý 26.6), định lý đặc trưng giá trị của luồng cực đại qua các lát cắt của mạng. Cuối mục, sách trình bày một cài đặt cụ thể và phân tích thời gian chạy.

Phương pháp Ford-Fulkerson tăng dần giá trị luồng. Bắt đầu với f(u, v) = 0 với mọi u, v ∈ V, tức luồng giá trị 0. Mỗi vòng lặp, ta tăng giá trị luồng trong G bằng cách tìm một "đường tăng luồng" trong "mạng thặng dư" G_f tương ứng. Khi biết các cạnh của một đường tăng luồng trong G_f, ta dễ xác định các cạnh cụ thể trong G cần thay đổi luồng để tăng giá trị luồng. Dù mỗi vòng lặp làm tăng giá trị luồng, luồng trên một cạnh cụ thể của G có thể tăng **hoặc giảm**; giảm luồng trên một số cạnh có thể là cần thiết để đẩy thêm được luồng từ nguồn tới đích. Ta lặp lại cho tới khi mạng thặng dư không còn đường tăng luồng. Định lý luồng cực đại – lát cắt cực tiểu sẽ chứng minh khi dừng, quá trình cho ra luồng cực đại.

```text
FORD-FULKERSON-METHOD(G, s, t)
1  initialize flow f to 0
2  while there exists an augmenting path p in the residual network G_f
3      augment flow f along p
4  return f
```

Dòng 1: khởi tạo luồng 0. Dòng 2: còn đường tăng luồng p trong mạng thặng dư G_f thì lặp. Dòng 3: tăng luồng f dọc theo p. Dòng 4: trả về f.

#### Mạng thặng dư (Residual networks)

Về trực giác, cho mạng luồng G và luồng f, **mạng thặng dư** G_f gồm các cạnh với sức chứa biểu thị cách ta có thể thay đổi luồng trên các cạnh của G. Một cạnh của mạng có thể nhận thêm một lượng luồng bằng sức chứa trừ luồng hiện có. Nếu lượng đó dương, ta đưa cạnh vào G_f với **sức chứa thặng dư** (residual capacity) c_f(u, v) = c(u, v) − f(u, v). Chỉ các cạnh của G còn nhận thêm được luồng mới có trong G_f; các cạnh có luồng bằng sức chứa có c_f(u, v) = 0 và không thuộc G_f.

Mạng thặng dư G_f còn có thể chứa các cạnh **không** có trong G. Khi thuật toán thay đổi luồng để tăng tổng luồng, nó có thể cần giảm luồng trên một cạnh. Để biểu diễn khả năng giảm một luồng dương f(u, v) trên một cạnh của G, ta đưa cạnh (v, u) vào G_f với sức chứa thặng dư c_f(v, u) = f(u, v) — tức là một cạnh cho phép đẩy luồng theo chiều ngược với (u, v), tối đa đến mức triệt tiêu hết luồng trên (u, v). Các cạnh ngược này cho phép thuật toán gửi trả lại luồng đã gửi qua một cạnh; gửi trả luồng tương đương với **giảm** luồng trên cạnh đó, một thao tác cần thiết trong nhiều thuật toán.

Hình thức hơn: cho mạng luồng G = (V, E) với nguồn s, đích t, f là một luồng trong G, xét cặp đỉnh u, v ∈ V. **Sức chứa thặng dư** c_f(u, v) định nghĩa là

```text
            ⎧ c(u, v) − f(u, v)   nếu (u, v) ∈ E
c_f(u, v) = ⎨ f(v, u)             nếu (v, u) ∈ E                     (26.2)
            ⎩ 0                   trong các trường hợp khác
```

Vì giả định (u, v) ∈ E kéo theo (v, u) ∉ E, đúng một trường hợp của (26.2) áp dụng cho mỗi cặp có thứ tự.

Ví dụ: nếu c(u, v) = 16 và f(u, v) = 11 thì có thể tăng f(u, v) thêm tối đa c_f(u, v) = 5 đơn vị trước khi vượt sức chứa; ta cũng muốn cho phép thuật toán trả lại tối đa 11 đơn vị từ v về u, nên c_f(v, u) = 11.

Cho mạng luồng G = (V, E) và luồng f, **mạng thặng dư của G sinh bởi f** là G_f = (V, E_f), với

```text
E_f = { (u, v) ∈ V × V : c_f(u, v) > 0 }                             (26.3)
```

Tức là mỗi cạnh của mạng thặng dư, gọi là **cạnh thặng dư** (residual edge), nhận được một luồng dương. Các cạnh trong E_f hoặc là cạnh của E hoặc là cạnh ngược của chúng, nên |E_f| ≤ 2|E|.

Mạng thặng dư G_f giống một mạng luồng với sức chứa c_f, nhưng không thoả định nghĩa mạng luồng vì có thể chứa cả cạnh (u, v) lẫn cạnh ngược (v, u). Ngoài khác biệt này, mạng thặng dư có cùng tính chất với mạng luồng, và ta định nghĩa **luồng trong mạng thặng dư** là hàm thoả định nghĩa luồng nhưng với sức chứa c_f trong G_f.

**Mạng thặng dư của luồng ví dụ** (vẽ lại Hình 26.4(b): mạng thặng dư của luồng 19 trong bảng trên). Quy ước: cạnh có sức chứa thặng dư 0 không được vẽ (ví dụ (v₁, v₃)).

| Cạnh gốc (f/c) | Cạnh thuận trong G_f (c − f) | Cạnh ngược trong G_f (f) |
|---|---|---|
| s → v₁ (11/16) | s → v₁: 5 | v₁ → s: 11 |
| s → v₂ (8/13) | s → v₂: 5 | v₂ → s: 8 |
| v₂ → v₁ (1/4) | v₂ → v₁: 3 | v₁ → v₂: 1 |
| v₁ → v₃ (12/12) | (không có) | v₃ → v₁: 12 |
| v₃ → v₂ (4/9) | v₃ → v₂: 5 | v₂ → v₃: 4 |
| v₂ → v₄ (11/14) | v₂ → v₄: 3 | v₄ → v₂: 11 |
| v₄ → v₃ (7/7) | (không có) | v₃ → v₄: 7 |
| v₃ → t (15/20) | v₃ → t: 5 | t → v₃: 15 |
| v₄ → t (4/4) | (không có) | t → v₄: 4 |

Một luồng trong mạng thặng dư cho ta "bản đồ" để thêm luồng vào mạng gốc. Nếu f là luồng trong G và f′ là luồng trong mạng thặng dư G_f, ta định nghĩa f ↑ f′, **phép tăng luồng** (augmentation) f bởi f′, là hàm từ V × V vào ℝ:

```text
                ⎧ f(u, v) + f′(u, v) − f′(v, u)   nếu (u, v) ∈ E
(f ↑ f′)(u, v) = ⎨                                                    (26.4)
                ⎩ 0                               trong các trường hợp khác
```

Trực giác theo đúng định nghĩa mạng thặng dư: tăng luồng trên (u, v) thêm f′(u, v) nhưng giảm đi f′(v, u), vì đẩy luồng trên cạnh ngược của mạng thặng dư nghĩa là giảm luồng trong mạng gốc. Đẩy luồng trên cạnh ngược còn gọi là **triệt tiêu** (cancellation). Ví dụ: gửi 5 thùng từ u sang v rồi gửi 2 thùng từ v về u, về kết quả cuối cùng, tương đương chỉ gửi 3 thùng từ u sang v và không gửi gì từ v về u. Kiểu triệt tiêu này thiết yếu cho mọi thuật toán luồng cực đại.

**Bổ đề 26.1.** Cho G = (V, E) là mạng luồng với nguồn s, đích t, f là một luồng trong G, G_f là mạng thặng dư sinh bởi f, và f′ là một luồng trong G_f. Khi đó hàm f ↑ f′ định nghĩa ở (26.4) là một luồng trong G với giá trị |f ↑ f′| = |f| + |f′|.

*Chứng minh.* Trước hết kiểm tra f ↑ f′ thoả ràng buộc sức chứa trên mỗi cạnh của E và bảo toàn luồng tại mỗi đỉnh của V − {s, t}.

*Ràng buộc sức chứa.* Nếu (u, v) ∈ E thì c_f(v, u) = f(u, v). Do đó f′(v, u) ≤ c_f(v, u) = f(u, v), và

```text
(f ↑ f′)(u, v) = f(u, v) + f′(u, v) − f′(v, u)    (theo (26.4))
               ≥ f(u, v) + f′(u, v) − f(u, v)     (vì f′(v, u) ≤ f(u, v))
               = f′(u, v)
               ≥ 0
```

Ngoài ra,

```text
(f ↑ f′)(u, v) = f(u, v) + f′(u, v) − f′(v, u)    (theo (26.4))
               ≤ f(u, v) + f′(u, v)               (vì luồng không âm)
               ≤ f(u, v) + c_f(u, v)              (ràng buộc sức chứa của f′)
               = f(u, v) + c(u, v) − f(u, v)      (định nghĩa c_f)
               = c(u, v)
```

*Bảo toàn luồng.* Vì cả f và f′ đều bảo toàn luồng, với mọi u ∈ V − {s, t}:

```text
Σ_{v∈V} (f ↑ f′)(u, v) = Σ_{v∈V} (f(u, v) + f′(u, v) − f′(v, u))
                       = Σ_v f(u, v) + Σ_v f′(u, v) − Σ_v f′(v, u)
                       = Σ_v f(v, u) + Σ_v f′(v, u) − Σ_v f′(u, v)
                       = Σ_v (f(v, u) + f′(v, u) − f′(u, v))
                       = Σ_{v∈V} (f ↑ f′)(v, u)
```

trong đó dòng thứ ba suy từ dòng thứ hai nhờ bảo toàn luồng (của f và của f′).

*Giá trị.* Vì G không có cạnh ngược chiều (G_f thì có thể có), với mỗi v ∈ V, có thể có cạnh (s, v) hoặc (v, s) nhưng không bao giờ cả hai. Đặt V₁ = {v : (s, v) ∈ E} là tập các đỉnh có cạnh từ s, V₂ = {v : (v, s) ∈ E} là tập các đỉnh có cạnh tới s. Ta có V₁ ∪ V₂ ⊆ V và V₁ ∩ V₂ = ∅. Khi đó

```text
|f ↑ f′| = Σ_{v∈V} (f ↑ f′)(s, v) − Σ_{v∈V} (f ↑ f′)(v, s)
         = Σ_{v∈V₁} (f ↑ f′)(s, v) − Σ_{v∈V₂} (f ↑ f′)(v, s)          (26.5)
```

(dòng hai đúng vì (f ↑ f′)(w, x) = 0 nếu (w, x) ∉ E). Áp dụng định nghĩa f ↑ f′ vào (26.5), sắp xếp lại và nhóm các số hạng:

```text
|f ↑ f′|
 = Σ_{V₁} (f(s,v) + f′(s,v) − f′(v,s)) − Σ_{V₂} (f(v,s) + f′(v,s) − f′(s,v))
 = Σ_{V₁} f(s,v) + Σ_{V₁} f′(s,v) − Σ_{V₁} f′(v,s)
     − Σ_{V₂} f(v,s) − Σ_{V₂} f′(v,s) + Σ_{V₂} f′(s,v)
 = Σ_{V₁} f(s,v) − Σ_{V₂} f(v,s)
     + Σ_{V₁} f′(s,v) + Σ_{V₂} f′(s,v) − Σ_{V₁} f′(v,s) − Σ_{V₂} f′(v,s)
 = Σ_{V₁} f(s,v) − Σ_{V₂} f(v,s) + Σ_{V₁∪V₂} f′(s,v) − Σ_{V₁∪V₂} f′(v,s)   (26.6)
```

Trong (26.6) có thể mở rộng cả bốn tổng thành tổng trên V, vì mỗi số hạng thêm vào đều bằng 0 (Exercise 26.2-1). Vậy

```text
|f ↑ f′| = Σ_V f(s,v) − Σ_V f(v,s) + Σ_V f′(s,v) − Σ_V f′(v,s)        (26.7)
         = |f| + |f′|                                                ∎
```

#### Đường tăng luồng (Augmenting paths)

Cho mạng luồng G = (V, E) và luồng f, một **đường tăng luồng** (augmenting path) p là một **đường đi đơn** từ s tới t trong mạng thặng dư G_f. Theo định nghĩa mạng thặng dư, có thể tăng luồng trên một cạnh (u, v) của đường tăng luồng thêm tối đa c_f(u, v) mà không vi phạm ràng buộc sức chứa trên cạnh nào trong hai cạnh (u, v), (v, u) có mặt trong G.

Trong ví dụ, đường s → v₂ → v₃ → t trong bảng mạng thặng dư ở trên là một đường tăng luồng (sách tô đậm nó trong Hình 26.4(b)): các sức chứa thặng dư là c_f(s, v₂) = 5, c_f(v₂, v₃) = 4, c_f(v₃, t) = 5. Coi G_f như một mạng luồng, có thể tăng luồng qua mỗi cạnh của đường này tối đa 4 đơn vị, vì sức chứa thặng dư nhỏ nhất trên đường là c_f(v₂, v₃) = 4. Lượng tối đa có thể tăng luồng trên mỗi cạnh của đường tăng luồng p gọi là **sức chứa thặng dư của p**:

```text
c_f(p) = min { c_f(u, v) : (u, v) nằm trên p }
```

**Bổ đề 26.2.** Cho G = (V, E) là mạng luồng, f là một luồng trong G, p là một đường tăng luồng trong G_f. Định nghĩa hàm f_p : V × V → ℝ bởi

```text
            ⎧ c_f(p)   nếu (u, v) nằm trên p
f_p(u, v) = ⎨                                                        (26.8)
            ⎩ 0        trong các trường hợp khác
```

Khi đó f_p là một luồng trong G_f với giá trị |f_p| = c_f(p) > 0. (Chứng minh để cho Exercise 26.2-7.) ∎

**Hệ quả 26.3.** Cho G = (V, E) là mạng luồng, f là một luồng trong G, p là một đường tăng luồng trong G_f, f_p định nghĩa như (26.8). Nếu tăng luồng f bởi f_p thì hàm f ↑ f_p là một luồng trong G với giá trị |f ↑ f_p| = |f| + |f_p| > |f|.

*Chứng minh.* Suy ngay từ Bổ đề 26.1 và 26.2. ∎

**Kết quả tăng luồng trong ví dụ** (vẽ lại Hình 26.4(c) và (d)). Tăng 4 đơn vị dọc s → v₂ → v₃ → t: cạnh s → v₂ tăng từ 8 lên 12; cạnh thặng dư v₂ → v₃ là cạnh ngược của v₃ → v₂ nên luồng trên v₃ → v₂ **giảm** từ 4 xuống 0 (triệt tiêu); cạnh v₃ → t tăng từ 15 lên 19. Luồng mới (cạnh không mang luồng chỉ ghi sức chứa):

| Cạnh | s→v₁ | s→v₂ | v₂→v₁ | v₁→v₃ | v₃→v₂ | v₂→v₄ | v₄→v₃ | v₃→t | v₄→t |
|---|---|---|---|---|---|---|---|---|---|
| f/c | 11/16 | 12/13 | 1/4 | 12/12 | 0 (ghi 9) | 11/14 | 7/7 | 19/20 | 4/4 |

Giá trị mới 11 + 12 = 23 = 19 + 4. Mạng thặng dư sinh bởi luồng mới (Hình 26.4(d)): s → v₁: 5, v₁ → s: 11; s → v₂: 1, v₂ → s: 12; v₂ → v₁: 3, v₁ → v₂: 1; v₃ → v₁: 12; v₃ → v₂: 9; v₂ → v₄: 3, v₄ → v₂: 11; v₃ → v₄: 7; v₃ → t: 1, t → v₃: 19; t → v₄: 4. (Kiểm tra của người tổng hợp: từ s đến được v₁, v₂, v₄; từ ba đỉnh này không có cạnh thặng dư nào sang v₃ hay t, nên không còn đường tăng luồng — luồng 23 là cực đại.)

#### Lát cắt của mạng luồng (Cuts of flow networks)

Phương pháp Ford-Fulkerson lặp lại việc tăng luồng dọc các đường tăng luồng cho tới khi tìm được luồng cực đại. Làm sao biết khi thuật toán dừng ta thật sự có luồng cực đại? Định lý luồng cực đại – lát cắt cực tiểu sẽ cho biết: một luồng là cực đại khi và chỉ khi mạng thặng dư của nó không chứa đường tăng luồng. Để chứng minh, trước hết cần khái niệm lát cắt.

Một **lát cắt** (cut) (S, T) của mạng luồng G = (V, E) là một phân hoạch V thành S và T = V − S sao cho s ∈ S và t ∈ T. (Giống định nghĩa "lát cắt" dùng cho cây khung nhỏ nhất ở Chương 23, trừ việc ở đây ta cắt đồ thị có hướng và bắt buộc s ∈ S, t ∈ T.) Nếu f là một luồng, **luồng ròng** (net flow) f(S, T) qua lát cắt (S, T) định nghĩa là

```text
f(S, T) = Σ_{u∈S} Σ_{v∈T} f(u, v) − Σ_{u∈S} Σ_{v∈T} f(v, u)          (26.9)
```

**Sức chứa của lát cắt** (S, T) là

```text
c(S, T) = Σ_{u∈S} Σ_{v∈T} c(u, v)                                     (26.10)
```

Một **lát cắt cực tiểu** (minimum cut) của mạng là lát cắt có sức chứa nhỏ nhất trong mọi lát cắt.

Sự **bất đối xứng** giữa định nghĩa luồng và sức chứa của lát cắt là cố ý và quan trọng: với sức chứa, chỉ đếm sức chứa các cạnh đi từ S sang T, bỏ qua cạnh chiều ngược; với luồng, lấy luồng từ S sang T **trừ** luồng chiều ngược từ T sang S. Lý do sẽ rõ ở phần sau.

**Ví dụ** (vẽ lại Hình 26.5): lát cắt S = {s, v₁, v₂}, T = {v₃, v₄, t} trên luồng giá trị 19 ở bảng mạng Lucky Puck phía trên.

```text
        S (tô đen)      ┆      T (để trắng)
     s ──▶ v₁ ──12/12───┼──▶ v₃ ──15/20──▶ t
     │     ▲       ↙4/9 ┆      ▲            ▲
     ▼     │1/4  ↙      ┆      │7/7         │4/4
     └──▶ v₂ ──11/14────┼──▶ v₄ ───────────┘
   (cạnh v₃ → v₂ đi từ T sang S, mang luồng 4)
```

Luồng ròng qua lát cắt: f(v₁, v₃) + f(v₂, v₄) − f(v₃, v₂) = 12 + 11 − 4 = 19. Sức chứa: c(v₁, v₃) + c(v₂, v₄) = 12 + 14 = 26 (cạnh v₃ → v₂ đi từ T sang S nên không tính).

Bổ đề sau chỉ ra: với một luồng f cho trước, luồng ròng qua **mọi** lát cắt đều như nhau và bằng |f|.

**Bổ đề 26.4.** Cho f là một luồng trong mạng luồng G với nguồn s, đích t, và (S, T) là một lát cắt bất kỳ của G. Khi đó luồng ròng qua (S, T) là f(S, T) = |f|.

*Chứng minh.* Viết lại điều kiện bảo toàn luồng tại mọi đỉnh u ∈ V − {s, t}:

```text
Σ_{v∈V} f(u, v) − Σ_{v∈V} f(v, u) = 0                                 (26.11)
```

Lấy định nghĩa |f| ở (26.1), cộng thêm vế trái của (26.11) (bằng 0) lấy tổng trên mọi đỉnh của S − {s}:

```text
|f| = Σ_V f(s,v) − Σ_V f(v,s) + Σ_{u∈S−{s}} ( Σ_V f(u,v) − Σ_V f(v,u) )
```

Khai triển tổng bên phải và nhóm lại:

```text
|f| = Σ_V f(s,v) − Σ_V f(v,s) + Σ_{u∈S−{s}} Σ_V f(u,v) − Σ_{u∈S−{s}} Σ_V f(v,u)
    = Σ_V ( f(s,v) + Σ_{u∈S−{s}} f(u,v) ) − Σ_V ( f(v,s) + Σ_{u∈S−{s}} f(v,u) )
    = Σ_{v∈V} Σ_{u∈S} f(u,v) − Σ_{v∈V} Σ_{u∈S} f(v,u)
```

Vì V = S ∪ T và S ∩ T = ∅, tách mỗi tổng trên V thành tổng trên S và trên T:

```text
|f| = Σ_{v∈S}Σ_{u∈S} f(u,v) + Σ_{v∈T}Σ_{u∈S} f(u,v)
        − Σ_{v∈S}Σ_{u∈S} f(v,u) − Σ_{v∈T}Σ_{u∈S} f(v,u)
    = Σ_{v∈T}Σ_{u∈S} f(u,v) − Σ_{v∈T}Σ_{u∈S} f(v,u)
        + ( Σ_{v∈S}Σ_{u∈S} f(u,v) − Σ_{v∈S}Σ_{u∈S} f(v,u) )
```

Hai tổng trong ngoặc thực ra bằng nhau, vì với mọi x, y ∈ V, số hạng f(x, y) xuất hiện đúng một lần trong mỗi tổng. Chúng triệt tiêu, còn lại

```text
|f| = Σ_{u∈S}Σ_{v∈T} f(u,v) − Σ_{u∈S}Σ_{v∈T} f(v,u) = f(S, T)        ∎
```

**Hệ quả 26.5.** Giá trị của mọi luồng f trong mạng luồng G bị chặn trên bởi sức chứa của mọi lát cắt của G.

*Chứng minh.* Cho (S, T) là lát cắt bất kỳ và f là luồng bất kỳ. Theo Bổ đề 26.4 và ràng buộc sức chứa:

```text
|f| = f(S, T)
    = Σ_{u∈S}Σ_{v∈T} f(u,v) − Σ_{u∈S}Σ_{v∈T} f(v,u)
    ≤ Σ_{u∈S}Σ_{v∈T} f(u,v)
    ≤ Σ_{u∈S}Σ_{v∈T} c(u,v)
    = c(S, T)                                                        ∎
```

Hệ quả trực tiếp: giá trị luồng cực đại bị chặn trên bởi sức chứa của lát cắt cực tiểu. Định lý quan trọng sau khẳng định hai đại lượng này thực ra **bằng nhau**.

**Định lý 26.6 (Định lý luồng cực đại – lát cắt cực tiểu, max-flow min-cut theorem).** Nếu f là một luồng trong mạng luồng G = (V, E) với nguồn s và đích t thì ba điều kiện sau tương đương:

1. f là luồng cực đại trong G.
2. Mạng thặng dư G_f không chứa đường tăng luồng nào.
3. |f| = c(S, T) với một lát cắt (S, T) nào đó của G.

*Chứng minh.*

(1) ⇒ (2): Giả sử phản chứng f là luồng cực đại nhưng G_f có đường tăng luồng p. Theo Hệ quả 26.3, luồng thu được khi tăng f bởi f_p (định nghĩa ở (26.8)) là một luồng trong G có giá trị lớn hơn hẳn |f|, mâu thuẫn với giả thiết f cực đại.

(2) ⇒ (3): Giả sử G_f không có đường tăng luồng, tức G_f không chứa đường đi nào từ s tới t. Định nghĩa

```text
S = { v ∈ V : tồn tại đường đi từ s tới v trong G_f },   T = V − S
```

Phân hoạch (S, T) là một lát cắt: s ∈ S hiển nhiên, t ∉ S vì không có đường từ s tới t trong G_f. Xét cặp đỉnh u ∈ S và v ∈ T. Nếu (u, v) ∈ E thì phải có f(u, v) = c(u, v), vì nếu không thì (u, v) ∈ E_f và v sẽ thuộc S. Nếu (v, u) ∈ E thì phải có f(v, u) = 0, vì nếu không thì c_f(u, v) = f(v, u) > 0, (u, v) ∈ E_f và v thuộc S. Đương nhiên nếu cả (u, v) và (v, u) đều không thuộc E thì f(u, v) = f(v, u) = 0. Do đó

```text
f(S, T) = Σ_{u∈S}Σ_{v∈T} f(u,v) − Σ_{v∈T}Σ_{u∈S} f(v,u)
        = Σ_{u∈S}Σ_{v∈T} c(u,v) − Σ_{v∈T}Σ_{u∈S} 0
        = c(S, T)
```

Theo Bổ đề 26.4, |f| = f(S, T) = c(S, T).

(3) ⇒ (1): Theo Hệ quả 26.5, |f| ≤ c(S, T) với mọi lát cắt (S, T). Vậy điều kiện |f| = c(S, T) kéo theo f là luồng cực đại. ∎

#### Thuật toán Ford-Fulkerson cơ bản (The basic Ford-Fulkerson algorithm)

Mỗi vòng lặp của phương pháp Ford-Fulkerson tìm **một** đường tăng luồng p nào đó và dùng p để sửa luồng f. Như Bổ đề 26.2 và Hệ quả 26.3 gợi ý, ta thay f bằng f ↑ f_p, được luồng mới có giá trị |f| + |f_p|. Cài đặt sau tính luồng cực đại trong G = (V, E) bằng cách cập nhật thuộc tính luồng (u, v).f cho mỗi cạnh (u, v) ∈ E (cùng kiểu ký hiệu thuộc tính đối tượng như ở Mục 22.1). Nếu (u, v) ∉ E, ngầm hiểu (u, v).f = 0. Sức chứa c(u, v) được cho kèm mạng, c(u, v) = 0 nếu (u, v) ∉ E. Sức chứa thặng dư c_f(u, v) tính theo (26.2). Biểu thức c_f(p) trong mã chỉ là biến tạm lưu sức chứa thặng dư của đường p.

```text
FORD-FULKERSON(G, s, t)
1  for each edge (u, v) ∈ G.E
2      (u, v).f = 0
3  while there exists a path p from s to t in the residual network G_f
4      c_f(p) = min { c_f(u, v) : (u, v) is in p }
5      for each edge (u, v) in p
6          if (u, v) ∈ E
7              (u, v).f = (u, v).f + c_f(p)
8          else (v, u).f = (v, u).f − c_f(p)
```

Dòng 1–2 khởi tạo luồng 0. Vòng while dòng 3–8 lặp lại: tìm một đường tăng luồng p trong G_f và tăng luồng f dọc p thêm c_f(p). Mỗi cạnh thặng dư trên p hoặc là cạnh của mạng gốc hoặc là cạnh ngược của một cạnh trong mạng gốc; dòng 6–8 cập nhật luồng tương ứng: cộng luồng nếu cạnh thặng dư là cạnh gốc, trừ luồng nếu là cạnh ngược. Khi không còn đường tăng luồng, f là luồng cực đại.

**Ví dụ chạy tay FORD-FULKERSON trên mạng Lucky Puck (Hình 26.6 của sách, các phần (a)–(f)).** Mỗi phần gồm mạng thặng dư G_f ở dòng 3 với đường tăng luồng p được chọn (sách tô đậm) và luồng mới sau khi tăng. Ở (a), mạng thặng dư chính là mạng đầu vào G. Người tổng hợp đã kiểm lại từng bước.

| Vòng | Đường tăng luồng p | Sức chứa thặng dư trên từng cạnh của p | c_f(p) | Thay đổi luồng | |f| sau |
|---|---|---|---|---|---|
| (a) | s → v₁ → v₃ → v₂ → v₄ → t | 16, 12, 9, 14, 4 | 4 | s→v₁, v₁→v₃, v₃→v₂, v₂→v₄, v₄→t mỗi cạnh +4 | 4 |
| (b) | s → v₂ → v₁ → v₃ → t | 13, 4, 8, 20 | 4 | s→v₂ +4, v₂→v₁ +4, v₁→v₃ lên 8, v₃→t +4 | 8 |
| (c) | s → v₁ → v₂ → v₃ → t | 12, 4 (ngược của v₂→v₁), 4 (ngược của v₃→v₂), 16 | 4 | s→v₁ lên 8; v₂→v₁ giảm về 0; v₃→v₂ giảm về 0; v₃→t lên 8 | 12 |
| (d) | s → v₂ → v₄ → v₃ → t | 9, 10, 7, 12 | 7 | s→v₂ lên 11, v₂→v₄ lên 11, v₄→v₃ lên 7, v₃→t lên 15 | 19 |
| (e) | s → v₁ → v₃ → t | 8, 4, 5 | 4 | s→v₁ lên 12, v₁→v₃ lên 12, v₃→t lên 19 | 23 |
| (f) | không còn đường | — | — | dừng | 23 |

Luồng sau mỗi vòng (ghi f/c; cạnh không mang luồng ghi sức chứa):

| Sau vòng | s→v₁ | s→v₂ | v₂→v₁ | v₁→v₃ | v₃→v₂ | v₂→v₄ | v₄→v₃ | v₃→t | v₄→t |
|---|---|---|---|---|---|---|---|---|---|
| (a) | 4/16 | 13 | 4 | 4/12 | 4/9 | 4/14 | 7 | 20 | 4/4 |
| (b) | 4/16 | 4/13 | 4/4 | 8/12 | 4/9 | 4/14 | 7 | 4/20 | 4/4 |
| (c) | 8/16 | 4/13 | 4 | 8/12 | 9 | 4/14 | 7 | 8/20 | 4/4 |
| (d) | 8/16 | 11/13 | 4 | 8/12 | 9 | 11/14 | 7/7 | 15/20 | 4/4 |
| (e) | 12/16 | 11/13 | 4 | 12/12 | 9 | 11/14 | 7/7 | 19/20 | 4/4 |

Mạng thặng dư ở lần kiểm tra while cuối cùng (Hình 26.6(f)): s → v₁: 4, v₁ → s: 12; s → v₂: 2, v₂ → s: 11; v₂ → v₁: 4; v₃ → v₁: 12; v₃ → v₂: 9; v₂ → v₄: 3, v₄ → v₂: 11; v₃ → v₄: 7; v₃ → t: 1, t → v₃: 19; t → v₄: 4. Không có đường tăng luồng, nên luồng ở (e) là cực đại, giá trị **23**. Lát cắt cực tiểu tương ứng (theo chứng minh (2) ⇒ (3)): S = {s, v₁, v₂, v₄} (các đỉnh đến được từ s), T = {v₃, t}; sức chứa c(v₁, v₃) + c(v₄, v₃) + c(v₄, t) = 12 + 7 + 4 = 23. Đường tăng luồng ở vòng (c) là đường duy nhất **triệt tiêu** luồng (đi trên hai cạnh ngược).

#### Phân tích Ford-Fulkerson (Analysis of Ford-Fulkerson)

Thời gian chạy của FORD-FULKERSON phụ thuộc vào cách tìm đường tăng luồng p ở dòng 3. Nếu chọn tồi, thuật toán thậm chí có thể **không dừng**: giá trị luồng tăng dần qua các lần tăng nhưng không nhất thiết hội tụ về giá trị luồng cực đại (chú thích của sách: phương pháp Ford-Fulkerson chỉ có thể không dừng khi sức chứa là số vô tỷ). Nếu tìm đường tăng luồng bằng tìm kiếm theo chiều rộng (Mục 22.2), thuật toán chạy trong thời gian đa thức. Trước khi chứng minh điều đó, sách cho một cận đơn giản khi chọn đường tuỳ ý và mọi sức chứa là số nguyên.

Trong thực tế, bài toán luồng cực đại thường có sức chứa nguyên. Nếu sức chứa là số hữu tỷ, có thể nhân lên bằng một hệ số thích hợp để mọi sức chứa thành nguyên. Nếu f* là luồng cực đại trong mạng đã biến đổi, một cài đặt thẳng thắn của FORD-FULKERSON thực hiện vòng while dòng 3–8 **nhiều nhất |f*| lần**, vì giá trị luồng tăng ít nhất 1 đơn vị mỗi vòng.

Có thể làm việc trong vòng while hiệu quả nếu dùng cấu trúc dữ liệu đúng và tìm đường bằng thuật toán thời gian tuyến tính. Giả sử ta giữ một cấu trúc dữ liệu cho đồ thị có hướng G′ = (V, E′) với E′ = {(u, v) : (u, v) ∈ E hoặc (v, u) ∈ E}. Cạnh của G cũng là cạnh của G′, nên dễ giữ sức chứa và luồng trong cấu trúc này. Cho luồng f trên G, các cạnh của mạng thặng dư G_f là mọi cạnh (u, v) của G′ có c_f(u, v) > 0 (c_f theo (26.2)). Thời gian tìm một đường trong mạng thặng dư vì vậy là O(V + E′) = O(E) nếu dùng tìm kiếm theo chiều sâu hoặc theo chiều rộng. Mỗi vòng while tốn O(E), khởi tạo dòng 1–2 cũng vậy, nên tổng thời gian của FORD-FULKERSON là **O(E |f*|)**.

Khi sức chứa nguyên và giá trị luồng tối ưu |f*| nhỏ, thời gian của Ford-Fulkerson tốt. **Ví dụ xấu** (vẽ lại Hình 26.7): mạng bốn đỉnh s, u, v, t với cạnh s → u, s → v, u → t, v → t đều sức chứa 1.000.000 và cạnh u → v sức chứa 1. Luồng cực đại có giá trị 2.000.000: 1.000.000 đơn vị theo s → u → t và 1.000.000 theo s → v → t.

```text
   Mạng gốc (Hình 26.7(a)):
              u
     10⁶  ↗   │   ↘  10⁶
        s     │1     t          (cạnh giữa: u → v, sức chứa 1)
     10⁶  ↘   ▼   ↗  10⁶
              v
```

Sức chứa thặng dư qua hai lần tăng luồng đầu (10⁶ viết là 1.000.000):

| Cạnh thặng dư | (a) ban đầu | (b) sau khi tăng 1 dọc s→u→v→t | (c) sau khi tăng 1 dọc s→v→u→t |
|---|---|---|---|
| s → u / u → s | 1.000.000 / 0 | 999.999 / 1 | 999.999 / 1 |
| s → v / v → s | 1.000.000 / 0 | 1.000.000 / 0 | 999.999 / 1 |
| u → v / v → u | 1 / 0 | 0 / 1 | 1 / 0 |
| u → t / t → u | 1.000.000 / 0 | 1.000.000 / 0 | 999.999 / 1 |
| v → t / t → v | 1.000.000 / 0 | 999.999 / 1 | 999.999 / 1 |

Ở (a) sách tô đậm đường s → u → v → t (sức chứa thặng dư 1); ở (b) tô đậm đường s → v → u → t (sức chứa thặng dư 1, đi qua cạnh ngược v → u).

Nếu đường tăng luồng đầu tiên FORD-FULKERSON tìm được là s → u → v → t, sau vòng đầu luồng có giá trị 1. Mạng thặng dư lúc này có cạnh v → u sức chứa 1 (cạnh ngược). Nếu vòng thứ hai chọn s → v → u → t, luồng có giá trị 2, và luồng trên u → v bị triệt tiêu về 0. Cứ tiếp tục chọn s → u → v → t ở các vòng lẻ và s → v → u → t ở các vòng chẵn, ta phải thực hiện tổng cộng **2.000.000 lần tăng luồng**, mỗi lần chỉ tăng 1 đơn vị. Đây là ví dụ cho thấy cận O(E |f*|) có thể đạt được, tức thời gian Θ(E |f*|).

#### Thuật toán Edmonds-Karp (The Edmonds-Karp algorithm)

Có thể cải thiện cận của FORD-FULKERSON bằng cách tìm đường tăng luồng p ở dòng 3 bằng **tìm kiếm theo chiều rộng** (BFS): chọn đường tăng luồng là đường **ngắn nhất** từ s tới t trong mạng thặng dư, mỗi cạnh có độ dài (trọng số) 1. Phương pháp Ford-Fulkerson cài đặt như vậy gọi là **thuật toán Edmonds-Karp**. Ta chứng minh nó chạy trong thời gian O(VE²).

Phân tích dựa vào khoảng cách tới các đỉnh trong mạng thặng dư G_f. Ký hiệu δ_f(u, v) là khoảng cách đường đi ngắn nhất từ u tới v trong G_f, mỗi cạnh có độ dài 1.

**Bổ đề 26.7.** Nếu chạy thuật toán Edmonds-Karp trên mạng luồng G = (V, E) với nguồn s và đích t, thì với mọi đỉnh v ∈ V − {s, t}, khoảng cách ngắn nhất δ_f(s, v) trong mạng thặng dư G_f **tăng đơn điệu** (không giảm) sau mỗi lần tăng luồng.

*Chứng minh.* Giả sử có một đỉnh v ∈ V − {s, t} mà một lần tăng luồng làm khoảng cách từ s tới v giảm; ta sẽ dẫn tới mâu thuẫn. Gọi f là luồng ngay trước lần tăng luồng **đầu tiên** làm giảm một khoảng cách ngắn nhất nào đó, f′ là luồng ngay sau. Gọi v là đỉnh có δ_f′(s, v) **nhỏ nhất** trong các đỉnh bị giảm khoảng cách, tức δ_f′(s, v) < δ_f(s, v). Gọi p = s ⇝ u → v là một đường ngắn nhất từ s tới v trong G_f′, nên (u, v) ∈ E_f′ và

```text
δ_f′(s, u) = δ_f′(s, v) − 1                                           (26.12)
```

Do cách chọn v, khoảng cách từ s tới u không giảm:

```text
δ_f′(s, u) ≥ δ_f(s, u)                                                (26.13)
```

Ta khẳng định (u, v) ∉ E_f. Vì nếu (u, v) ∈ E_f thì

```text
δ_f(s, v) ≤ δ_f(s, u) + 1      (Bổ đề 24.10, bất đẳng thức tam giác)
          ≤ δ_f′(s, u) + 1     (theo (26.13))
          = δ_f′(s, v)         (theo (26.12))
```

mâu thuẫn với giả thiết δ_f′(s, v) < δ_f(s, v).

Vậy làm sao (u, v) ∉ E_f mà (u, v) ∈ E_f′? Lần tăng luồng phải đã tăng luồng từ v sang u, tức là cạnh (v, u) nằm trên đường tăng luồng. Thuật toán Edmonds-Karp luôn tăng luồng dọc đường ngắn nhất, nên đường ngắn nhất từ s tới u trong G_f có (v, u) là cạnh cuối. Do đó

```text
δ_f(s, v) = δ_f(s, u) − 1
          ≤ δ_f′(s, u) − 1     (theo (26.13))
          = δ_f′(s, v) − 2     (theo (26.12))
```

mâu thuẫn với giả thiết δ_f′(s, v) < δ_f(s, v). Vậy không tồn tại đỉnh v như vậy. ∎

**Định lý 26.8.** Nếu chạy thuật toán Edmonds-Karp trên mạng luồng G = (V, E) với nguồn s và đích t, tổng số lần tăng luồng là O(VE).

*Chứng minh.* Gọi một cạnh (u, v) của mạng thặng dư G_f là **cạnh tới hạn** (critical) trên đường tăng luồng p nếu sức chứa thặng dư của p bằng sức chứa thặng dư của (u, v), tức c_f(p) = c_f(u, v). Sau khi tăng luồng dọc đường p, mọi cạnh tới hạn trên p biến mất khỏi mạng thặng dư. Hơn nữa, mỗi đường tăng luồng có ít nhất một cạnh tới hạn. Ta chứng minh mỗi cạnh trong |E| cạnh trở thành tới hạn nhiều nhất |V|/2 lần.

Cho u và v là hai đỉnh nối bởi một cạnh trong E. Vì đường tăng luồng là đường ngắn nhất, khi (u, v) tới hạn lần đầu ta có

```text
δ_f(s, v) = δ_f(s, u) + 1
```

Sau khi tăng luồng, cạnh (u, v) biến mất khỏi mạng thặng dư. Nó không thể xuất hiện lại trên đường tăng luồng khác cho tới khi luồng từ u sang v bị giảm, điều chỉ xảy ra khi (v, u) xuất hiện trên một đường tăng luồng. Nếu f′ là luồng trong G lúc sự kiện đó xảy ra thì

```text
δ_f′(s, u) = δ_f′(s, v) + 1
```

Vì δ_f(s, v) ≤ δ_f′(s, v) theo Bổ đề 26.7,

```text
δ_f′(s, u) = δ_f′(s, v) + 1
           ≥ δ_f(s, v) + 1
           = δ_f(s, u) + 2
```

Vậy từ lúc (u, v) trở thành tới hạn tới lúc nó tới hạn lần sau, khoảng cách từ nguồn tới u tăng ít nhất 2. Khoảng cách từ nguồn tới u ban đầu ít nhất là 0. Các đỉnh trung gian trên một đường ngắn nhất từ s tới u không thể là s, u hay t (vì (u, v) nằm trên đường tăng luồng nên u ≠ t). Do đó, cho tới khi u không còn đến được từ nguồn (nếu điều đó xảy ra), khoảng cách của u nhiều nhất là |V| − 2. Vậy sau lần đầu (u, v) trở thành tới hạn, nó có thể tới hạn thêm nhiều nhất (|V| − 2)/2 = |V|/2 − 1 lần nữa, tổng cộng nhiều nhất |V|/2 lần. Vì có O(E) cặp đỉnh có thể có cạnh giữa chúng trong mạng thặng dư, tổng số cạnh tới hạn trong cả quá trình chạy là O(VE). Mỗi đường tăng luồng có ít nhất một cạnh tới hạn, nên định lý được chứng minh. ∎

Vì mỗi vòng lặp của FORD-FULKERSON cài đặt được trong O(E) khi tìm đường bằng BFS, tổng thời gian của thuật toán Edmonds-Karp là **O(VE²)**. Các thuật toán đẩy–nâng nhãn còn cho cận tốt hơn: Mục 26.4 cho phương pháp đạt O(V²E), nền tảng cho thuật toán O(V³) ở Mục 26.5.

**Chạy tay Edmonds-Karp trên mạng Lucky Puck (đây là Exercise 26.2-3; lời giải của người tổng hợp).** BFS tìm đường ít cạnh nhất (thứ tự duyệt kề: theo chỉ số đỉnh tăng dần).

| Vòng | Đường ngắn nhất (số cạnh) | c_f(p) | |f| sau |
|---|---|---|---|
| 1 | s → v₁ → v₃ → t (3) | min(16, 12, 20) = 12 | 12 |
| 2 | s → v₂ → v₄ → t (3) | min(13, 14, 4) = 4 | 16 |
| 3 | s → v₂ → v₄ → v₃ → t (4) | min(9, 10, 7, 8) = 7 | 23 |
| 4 | không còn đường | — | 23 |

Chỉ ba lần tăng luồng (so với năm lần ở ví dụ chọn đường tuỳ ý phía trên), và độ dài đường tăng luồng không giảm (3, 3, 4), đúng như Bổ đề 26.7 dự báo.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: Edmonds-Karp và Dinic (thuật toán dùng đồ thị phân tầng, cải tiến trực tiếp ý "đường ngắn nhất" của Edmonds-Karp) là hai cài đặt luồng cực đại phổ biến nhất trong lập trình thi đấu; thư viện đồ thị như Boost Graph Library, NetworkX, OR-Tools đều có các hàm max-flow/min-cut. Định lý luồng cực đại – lát cắt cực tiểu được dùng trong phân đoạn ảnh (graph cut), tìm điểm nghẽn trong mạng giao thông, phân tích độ tin cậy mạng.

### 4. Cặp ghép cực đại trên đồ thị hai phía (26.3 Maximum bipartite matching, trang 732–736)

Một số bài toán tổ hợp có thể diễn đạt trực tiếp thành bài toán luồng cực đại (bài toán nhiều nguồn nhiều đích ở Mục 26.1 là một ví dụ). Một số bài toán khác bề ngoài không liên quan gì tới mạng luồng nhưng thực ra quy được về luồng cực đại. Mục này trình bày một bài toán như vậy: tìm **cặp ghép cực đại** (maximum matching) trong đồ thị hai phía. Để giải, ta tận dụng **tính nguyên** (integrality property) mà phương pháp Ford-Fulkerson bảo đảm, và dùng phương pháp này giải bài toán trên đồ thị G = (V, E) trong thời gian O(VE).

#### Bài toán cặp ghép cực đại trên đồ thị hai phía (The maximum-bipartite-matching problem)

Cho đồ thị vô hướng G = (V, E), một **cặp ghép** (matching) là tập con các cạnh M ⊆ E sao cho với mọi đỉnh v ∈ V, nhiều nhất một cạnh của M liên thuộc với v. Đỉnh v ∈ V được gọi là **được ghép** (matched) bởi M nếu có cạnh nào trong M liên thuộc với v; ngược lại v là **chưa được ghép** (unmatched). Một **cặp ghép cực đại** là cặp ghép có lực lượng lớn nhất, tức là M sao cho với mọi cặp ghép M′, |M| ≥ |M′|. Mục này chỉ xét đồ thị hai phía: tập đỉnh phân hoạch được thành V = L ∪ R, L và R rời nhau, và mọi cạnh trong E nối một đỉnh của L với một đỉnh của R. Giả định thêm mọi đỉnh trong V có ít nhất một cạnh liên thuộc.

**Ví dụ của sách** (vẽ lại Hình 26.8; đánh số theo Exercise 26.3-1: L gồm đỉnh 1–5 từ trên xuống, R gồm đỉnh 6–9 từ trên xuống). Các cạnh: 1–6, 2–6, 2–8, 3–7, 3–8, 3–9, 4–8, 5–8.

```text
   Danh sách kề (L → các đỉnh R kề):
     1 → 6
     2 → 6, 8
     3 → 7, 8, 9
     4 → 8
     5 → 8
   (a) một cặp ghép cỡ 2:          M = {1–6, 3–8}
   (b) một cặp ghép cực đại cỡ 3:  M = {2–6, 3–7, 5–8}
```

Vì sao 3 là cực đại (kiểm tra của người tổng hợp): bốn đỉnh 1, 2, 4, 5 của L chỉ kề với hai đỉnh 6 và 8 của R, nên trong bốn đỉnh đó nhiều nhất hai đỉnh được ghép; cộng đỉnh 3 là nhiều nhất 3.

Bài toán có nhiều ứng dụng. Ví dụ: ghép một tập máy L với một tập công việc R cần thực hiện đồng thời. Cạnh (u, v) ∈ E nghĩa là máy u ∈ L làm được việc v ∈ R. Cặp ghép cực đại cho việc làm tới nhiều máy nhất có thể.

#### Tìm cặp ghép cực đại trên đồ thị hai phía (Finding a maximum bipartite matching)

Có thể dùng phương pháp Ford-Fulkerson để tìm cặp ghép cực đại trong đồ thị hai phía vô hướng G = (V, E) trong thời gian đa thức theo |V| và |E|. Mẹo là dựng một mạng luồng mà luồng trong đó tương ứng với cặp ghép. **Mạng luồng tương ứng** G′ = (V′, E′) của đồ thị hai phía G định nghĩa như sau: nguồn s và đích t là hai đỉnh mới không thuộc V, V′ = V ∪ {s, t}. Nếu phân hoạch đỉnh của G là V = L ∪ R, các cạnh có hướng của G′ là các cạnh của E hướng từ L sang R, cùng |V| cạnh có hướng mới:

```text
E′ = { (s, u) : u ∈ L } ∪ { (u, v) : (u, v) ∈ E } ∪ { (v, t) : v ∈ R }
```

Mọi cạnh trong E′ có **sức chứa 1**. Vì mọi đỉnh trong V có ít nhất một cạnh liên thuộc, |E| ≥ |V|/2. Do đó |E| ≤ |E′| = |E| + |V| ≤ 3|E|, nên |E′| = Θ(E).

Với ví dụ trên, mạng G′ (Hình 26.8(c)) có các cạnh s → 1, …, s → 5; 1 → 6, 2 → 6, 2 → 8, 3 → 7, 3 → 8, 3 → 9, 4 → 8, 5 → 8; 6 → t, 7 → t, 8 → t, 9 → t, tất cả sức chứa 1. Luồng cực đại trong hình: mỗi cạnh s → 2, s → 3, s → 5, 2 → 6, 3 → 7, 5 → 8, 6 → t, 7 → t, 8 → t mang luồng 1, các cạnh khác luồng 0; các cạnh từ L sang R mang luồng chính là cặp ghép cực đại ở (b).

Một luồng f trên mạng luồng G = (V, E) gọi là **nhận giá trị nguyên** (integer-valued) nếu f(u, v) là số nguyên với mọi (u, v) ∈ V × V.

**Bổ đề 26.9.** Cho G = (V, E) là đồ thị hai phía với phân hoạch đỉnh V = L ∪ R, và G′ = (V′, E′) là mạng luồng tương ứng. Nếu M là một cặp ghép trong G thì có một luồng nguyên f trong G′ với giá trị |f| = |M|. Ngược lại, nếu f là một luồng nguyên trong G′ thì có một cặp ghép M trong G với lực lượng |M| = |f|.

*Chứng minh.* Chiều thuận: cho cặp ghép M, định nghĩa f như sau. Nếu (u, v) ∈ M thì f(s, u) = f(u, v) = f(v, t) = 1. Với mọi cạnh khác (u, v) ∈ E′, f(u, v) = 0. Dễ kiểm tra f thoả ràng buộc sức chứa và bảo toàn luồng. Về trực giác, mỗi cạnh (u, v) ∈ M tương ứng với một đơn vị luồng trong G′ đi theo đường s → u → v → t. Hơn nữa, các đường sinh bởi các cạnh của M rời nhau về đỉnh (trừ s và t). Luồng ròng qua lát cắt (L ∪ {s}, R ∪ {t}) bằng |M|; theo Bổ đề 26.4, giá trị luồng là |f| = |M|.

Chiều ngược: cho f là luồng nguyên trong G′, đặt

```text
M = { (u, v) : u ∈ L, v ∈ R, và f(u, v) > 0 }
```

Mỗi đỉnh u ∈ L chỉ có một cạnh đi vào là (s, u), sức chứa 1. Vì vậy mỗi u ∈ L có nhiều nhất một đơn vị luồng đi vào, và nếu có một đơn vị đi vào thì theo bảo toàn luồng phải có một đơn vị đi ra. Hơn nữa, vì f nhận giá trị nguyên, với mỗi u ∈ L, một đơn vị luồng đó chỉ có thể vào qua nhiều nhất một cạnh và ra qua nhiều nhất một cạnh. Do đó một đơn vị luồng đi vào u khi và chỉ khi có đúng một đỉnh v ∈ R với f(u, v) = 1, và nhiều nhất một cạnh rời u mang luồng dương. Lập luận đối xứng áp dụng cho mỗi v ∈ R. Vậy M là một cặp ghép.

Để thấy |M| = |f|: với mọi đỉnh u ∈ L đã được ghép, f(s, u) = 1, và với mọi cạnh (u, v) ∈ E − M, f(u, v) = 0. Do đó luồng ròng qua lát cắt (L ∪ {s}, R ∪ {t}), f(L ∪ {s}, R ∪ {t}), bằng |M|. Theo Bổ đề 26.4, |f| = f(L ∪ {s}, R ∪ {t}) = |M|. ∎

Dựa vào Bổ đề 26.9, ta muốn kết luận cặp ghép cực đại trong G tương ứng với luồng cực đại trong G′, nên có thể tìm cặp ghép cực đại bằng cách chạy thuật toán luồng cực đại trên G′. Trở ngại duy nhất: thuật toán luồng cực đại có thể trả về luồng mà một số f(u, v) không nguyên, dù giá trị |f| phải là số nguyên. Định lý sau cho thấy dùng phương pháp Ford-Fulkerson thì khó khăn này không xảy ra.

**Định lý 26.10 (Định lý tính nguyên, integrality theorem).** Nếu hàm sức chứa c chỉ nhận giá trị nguyên thì luồng cực đại f do phương pháp Ford-Fulkerson tạo ra có |f| là số nguyên. Hơn nữa, với mọi đỉnh u, v, f(u, v) là số nguyên.

*Chứng minh.* Quy nạp theo số vòng lặp (để cho Exercise 26.3-2). *Ý của người tổng hợp:* luồng ban đầu 0 nguyên; nếu f nguyên thì mọi c_f(u, v) nguyên, nên c_f(p) nguyên, và f ↑ f_p chỉ cộng/trừ c_f(p) trên các cạnh, vẫn nguyên. ∎

**Hệ quả 26.11.** Lực lượng của cặp ghép cực đại M trong đồ thị hai phía G bằng giá trị luồng cực đại f trong mạng luồng tương ứng G′.

*Chứng minh.* Dùng ký hiệu của Bổ đề 26.9. Giả sử M là cặp ghép cực đại trong G nhưng luồng f tương ứng trong G′ không cực đại. Khi đó có luồng cực đại f′ trong G′ với |f′| > |f|. Vì sức chứa trong G′ nguyên, theo Định lý 26.10 có thể giả sử f′ nguyên. Vậy f′ tương ứng với cặp ghép M′ trong G có lực lượng |M′| = |f′| > |f| = |M|, mâu thuẫn với giả thiết M cực đại. Tương tự, nếu f là luồng cực đại trong G′ thì cặp ghép tương ứng là cặp ghép cực đại trong G. ∎

Như vậy, cho đồ thị hai phía vô hướng G, ta tìm cặp ghép cực đại bằng cách dựng mạng luồng G′, chạy phương pháp Ford-Fulkerson và đọc trực tiếp cặp ghép cực đại M từ luồng cực đại nguyên f tìm được. Vì mọi cặp ghép trong đồ thị hai phía có lực lượng nhiều nhất min(|L|, |R|) = O(V), giá trị luồng cực đại trong G′ là O(V). Do đó tìm được cặp ghép cực đại trong thời gian O(VE′) = **O(VE)**, vì |E′| = Θ(E) (dùng cận O(E |f*|) của Ford-Fulkerson).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: cặp ghép hai phía xuất hiện trong phân công nhiệm vụ cho máy/người, xếp lịch thi (môn – phòng), ghép tài xế với khách trong ứng dụng gọi xe (thường là cặp ghép có trọng số — bài toán phân công, giải bằng thuật toán Hungary hoặc luồng chi phí nhỏ nhất). Với đồ thị hai phía lớn, thuật toán Hopcroft-Karp (Problem 26-6) chạy O(√V E), nhanh hơn O(VE) của mục này.

### 5. ★ Thuật toán đẩy–nâng nhãn (26.4 Push-relabel algorithms, trang 736–748)

Mục này trình bày cách tiếp cận **đẩy–nâng nhãn** (push-relabel) để tính luồng cực đại. Tới thời điểm sách viết, nhiều thuật toán luồng cực đại nhanh nhất về tiệm cận là thuật toán đẩy–nâng nhãn, và các cài đặt thực tế nhanh nhất cũng dựa trên phương pháp này. Phương pháp đẩy–nâng nhãn còn giải hiệu quả các bài toán luồng khác, như bài toán luồng chi phí nhỏ nhất. Mục này giới thiệu thuật toán luồng cực đại "tổng quát" (generic) của Goldberg, có một cài đặt đơn giản chạy trong O(V²E), cải thiện cận O(VE²) của Edmonds-Karp. Mục 26.5 tinh chỉnh thuật toán tổng quát để được một thuật toán đẩy–nâng nhãn chạy O(V³).

Thuật toán đẩy–nâng nhãn làm việc **cục bộ** hơn phương pháp Ford-Fulkerson. Thay vì xem xét toàn bộ mạng thặng dư để tìm một đường tăng luồng, chúng làm việc trên từng đỉnh một, chỉ nhìn các đỉnh kề của đỉnh đó trong mạng thặng dư. Hơn nữa, khác Ford-Fulkerson, thuật toán đẩy–nâng nhãn **không** giữ tính bảo toàn luồng trong suốt quá trình chạy. Chúng giữ một **tiền luồng** (preflow): hàm f : V × V → ℝ thoả ràng buộc sức chứa và dạng nới lỏng sau của bảo toàn luồng:

```text
Σ_{v∈V} f(v, u) − Σ_{v∈V} f(u, v) ≥ 0      với mọi u ∈ V − {s}
```

Tức là luồng vào một đỉnh được phép vượt luồng ra. Đại lượng

```text
e(u) = Σ_{v∈V} f(v, u) − Σ_{v∈V} f(u, v)                             (26.14)
```

gọi là **luồng dư** (excess flow) tại u: lượng luồng vào vượt quá luồng ra. Một đỉnh u ∈ V − {s, t} gọi là **tràn** (overflowing) nếu e(u) > 0.

Trình tự của mục: trực giác của phương pháp; hai thao tác cơ bản "đẩy" tiền luồng và "nâng nhãn" một đỉnh; thuật toán đẩy–nâng nhãn tổng quát, tính đúng và thời gian chạy.

#### Trực giác (Intuition)

Có thể hiểu phương pháp đẩy–nâng nhãn qua hình ảnh dòng chất lỏng: coi mạng luồng G = (V, E) là hệ thống ống nối với nhau có sức chứa cho trước. Áp dụng hình ảnh này cho Ford-Fulkerson, mỗi đường tăng luồng tạo thêm một dòng chất lỏng không rẽ nhánh chảy từ nguồn tới đích; Ford-Fulkerson lặp lại việc thêm dòng cho tới khi không thêm được nữa.

Thuật toán đẩy–nâng nhãn tổng quát có trực giác khác. Cạnh có hướng vẫn là ống. Đỉnh (điểm nối ống) có hai tính chất đáng chú ý. Thứ nhất, để chứa luồng dư, mỗi đỉnh có một ống thoát dẫn vào một **bể chứa** lớn tuỳ ý tích được chất lỏng. Thứ hai, mỗi đỉnh, bể chứa của nó và mọi ống nối đặt trên một **bệ** có **độ cao** tăng dần theo tiến trình thuật toán.

Độ cao đỉnh quyết định cách đẩy luồng: ta chỉ đẩy luồng **xuống dốc**, từ đỉnh cao xuống đỉnh thấp. Luồng từ đỉnh thấp sang đỉnh cao có thể dương, nhưng thao tác đẩy chỉ đẩy xuống dốc. Độ cao của nguồn cố định ở |V|, của đích cố định ở 0. Các đỉnh khác bắt đầu ở độ cao 0 và tăng dần. Đầu tiên, thuật toán gửi lượng luồng lớn nhất có thể xuống dốc từ nguồn về phía đích: đúng đủ để lấp đầy mọi ống ra khỏi nguồn, tức là gửi đúng sức chứa của lát cắt (s, V − {s}). Khi luồng mới vào một đỉnh trung gian, nó tích vào bể chứa của đỉnh. Từ đó, nó dần được đẩy xuống dốc.

Có lúc ta thấy các ống rời đỉnh u còn chưa đầy chỉ dẫn tới các đỉnh cao bằng u hoặc cao hơn u. Khi đó, để giải phóng luồng dư của đỉnh tràn u, ta phải tăng độ cao của u — thao tác gọi là **nâng nhãn** (relabel) đỉnh u. Ta nâng nó lên cao hơn đúng 1 đơn vị so với đỉnh thấp nhất trong các đỉnh kề mà nó còn ống chưa đầy dẫn tới. Sau khi nâng nhãn, đỉnh có ít nhất một ống ra để đẩy thêm luồng.

Cuối cùng, mọi luồng có thể tới đích đã tới. Không thêm được nữa vì các ống tuân theo ràng buộc sức chứa; lượng luồng qua mọi lát cắt vẫn bị chặn bởi sức chứa lát cắt. Để biến tiền luồng thành luồng "hợp lệ", thuật toán gửi phần dư tích trong bể của các đỉnh tràn **về lại nguồn**, bằng cách tiếp tục nâng nhãn các đỉnh lên cao hơn độ cao cố định |V| của nguồn. Như sẽ thấy, khi mọi bể đã rỗng, tiền luồng không chỉ là luồng hợp lệ mà còn là luồng cực đại.

#### Các thao tác cơ bản (The basic operations)

Thuật toán đẩy–nâng nhãn dùng hai thao tác: **đẩy** luồng dư từ một đỉnh sang một đỉnh kề, và **nâng nhãn** một đỉnh. Khi nào áp dụng được mỗi thao tác phụ thuộc vào độ cao các đỉnh, định nghĩa chính xác như sau.

Cho G = (V, E) là mạng luồng với nguồn s, đích t, f là một tiền luồng trong G. Một hàm h : V → ℕ là **hàm độ cao** (height function) nếu h(s) = |V|, h(t) = 0, và

```text
h(u) ≤ h(v) + 1      với mọi cạnh thặng dư (u, v) ∈ E_f
```

(Chú thích của sách: trong tài liệu, hàm độ cao thường gọi là "hàm khoảng cách" (distance function) và độ cao một đỉnh gọi là "nhãn khoảng cách" (distance label). Sách dùng "độ cao" vì gợi trực giác hơn, nhưng giữ từ "nâng nhãn" cho thao tác tăng độ cao. Độ cao một đỉnh liên quan tới khoảng cách từ nó tới đích t, như tìm được bằng BFS trên đồ thị chuyển vị Gᵀ.)

**Bổ đề 26.12.** Cho G = (V, E) là mạng luồng, f là tiền luồng trong G, h là hàm độ cao trên V. Với hai đỉnh u, v ∈ V bất kỳ, nếu h(u) > h(v) + 1 thì (u, v) không phải cạnh của mạng thặng dư. ∎ (Suy ngay từ định nghĩa.)

##### Thao tác đẩy (The push operation)

Thao tác cơ bản PUSH(u, v) áp dụng được nếu u là đỉnh tràn, c_f(u, v) > 0 và h(u) = h(v) + 1. Mã giả sau cập nhật tiền luồng f và luồng dư của u và v. Nó giả định có thể tính c_f(u, v) trong thời gian hằng khi biết c và f. Luồng dư lưu ở thuộc tính u.e, độ cao ở u.h. Biểu thức Δ_f(u, v) là biến tạm lưu lượng luồng có thể đẩy từ u sang v.

```text
PUSH(u, v)
1  // Applies when: u is overflowing, c_f(u, v) > 0, and u.h = v.h + 1.
2  // Action: Push Δ_f(u, v) = min(u.e, c_f(u, v)) units of flow from u to v.
3  Δ_f(u, v) = min(u.e, c_f(u, v))
4  if (u, v) ∈ E
5      (u, v).f = (u, v).f + Δ_f(u, v)
6  else (v, u).f = (v, u).f − Δ_f(u, v)
7  u.e = u.e − Δ_f(u, v)
8  v.e = v.e + Δ_f(u, v)
```

Dòng 1–2 là chú thích: điều kiện áp dụng và hành động. Vì u có luồng dư dương và sức chứa thặng dư của (u, v) dương, có thể tăng luồng từ u sang v thêm Δ_f(u, v) = min(u.e, c_f(u, v)) mà không làm u.e âm hay vượt sức chứa c(u, v). Dòng 3 tính Δ_f(u, v); dòng 4–6 cập nhật f: dòng 5 tăng luồng trên cạnh (u, v) khi cạnh thặng dư cũng là cạnh gốc; dòng 6 giảm luồng trên (v, u) khi cạnh thặng dư thực ra là cạnh ngược của một cạnh gốc. Dòng 7–8 cập nhật luồng dư của u và v. Do đó, nếu f là tiền luồng trước khi gọi PUSH thì sau đó vẫn là tiền luồng.

Lưu ý mã của PUSH không phụ thuộc độ cao của u và v, nhưng ta **cấm** gọi nó trừ khi u.h = v.h + 1. Như vậy luồng dư chỉ được đẩy xuống dốc với chênh lệch độ cao đúng 1. Theo Bổ đề 26.12, không có cạnh thặng dư giữa hai đỉnh chênh nhau hơn 1, nên chừng nào h còn là hàm độ cao, cho phép đẩy xuống dốc với chênh lệch lớn hơn 1 cũng chẳng được gì.

Thao tác PUSH(u, v) gọi là một lần **đẩy** (push) từ u sang v. Nếu thao tác đẩy áp dụng cho một cạnh (u, v) rời u, ta cũng nói thao tác đẩy áp dụng cho u. Đó là **đẩy bão hoà** (saturating push) nếu cạnh (u, v) trong mạng thặng dư trở thành **bão hoà** (saturated: c_f(u, v) = 0 sau đó); ngược lại là **đẩy không bão hoà** (nonsaturating push). Cạnh bão hoà biến mất khỏi mạng thặng dư.

**Bổ đề 26.13.** Sau một lần đẩy không bão hoà từ u sang v, đỉnh u không còn tràn.

*Chứng minh.* Vì lần đẩy không bão hoà, lượng luồng Δ_f(u, v) thực sự đẩy phải bằng u.e trước khi đẩy. Vì u.e giảm đúng lượng này, nó bằng 0 sau khi đẩy. ∎

##### Thao tác nâng nhãn (The relabel operation)

Thao tác cơ bản RELABEL(u) áp dụng được nếu u tràn và u.h ≤ v.h với mọi cạnh (u, v) ∈ E_f. Nói cách khác, có thể nâng nhãn đỉnh tràn u nếu với mọi đỉnh v mà từ u sang v còn sức chứa thặng dư, không đẩy được luồng từ u sang v vì v không thấp hơn u. (Theo định nghĩa, nguồn s và đích t không bao giờ tràn, nên s và t không bao giờ được nâng nhãn.)

```text
RELABEL(u)
1  // Applies when: u is overflowing and for all v ∈ V such that (u, v) ∈ E_f,
       we have u.h ≤ v.h.
2  // Action: Increase the height of u.
3  u.h = 1 + min { v.h : (u, v) ∈ E_f }
```

Khi gọi RELABEL(u), ta nói đỉnh u được **nâng nhãn** (relabeled). Khi u được nâng nhãn, E_f phải chứa ít nhất một cạnh rời u, nên phép lấy min ở dòng 3 là trên một tập khác rỗng. Tính chất này suy từ việc u tràn:

```text
u.e = Σ_{v∈V} f(v, u) − Σ_{v∈V} f(u, v) > 0
```

Vì mọi luồng không âm, phải có ít nhất một đỉnh v với (v, u).f > 0. Khi đó c_f(u, v) > 0, tức (u, v) ∈ E_f. Như vậy RELABEL(u) cho u độ cao **lớn nhất** mà ràng buộc của hàm độ cao cho phép.

#### Thuật toán tổng quát (The generic algorithm)

Thuật toán đẩy–nâng nhãn tổng quát dùng thủ tục con sau để tạo tiền luồng ban đầu:

```text
INITIALIZE-PREFLOW(G, s)
 1  for each vertex v ∈ G.V
 2      v.h = 0
 3      v.e = 0
 4  for each edge (u, v) ∈ G.E
 5      (u, v).f = 0
 6  s.h = |G.V|
 7  for each vertex v ∈ s.Adj
 8      (s, v).f = c(s, v)
 9      v.e = c(s, v)
10      s.e = s.e − c(s, v)
```

INITIALIZE-PREFLOW tạo tiền luồng ban đầu

```text
           ⎧ c(u, v)   nếu u = s
(u, v).f = ⎨                                                         (26.15)
           ⎩ 0         trong các trường hợp khác
```

tức là lấp đầy mọi cạnh rời nguồn s, các cạnh khác không mang luồng. Với mỗi đỉnh v kề nguồn, ban đầu v.e = c(s, v), và s.e khởi tạo bằng số đối của tổng các sức chứa đó. Thuật toán tổng quát cũng bắt đầu với hàm độ cao ban đầu

```text
      ⎧ |V|   nếu u = s
u.h = ⎨                                                              (26.16)
      ⎩ 0     trong các trường hợp khác
```

(26.16) là hàm độ cao vì các cạnh (u, v) duy nhất có u.h > v.h + 1 là các cạnh có u = s, và chúng đã bão hoà, tức không có trong mạng thặng dư.

Khởi tạo, rồi một dãy thao tác đẩy và nâng nhãn thực hiện **theo thứ tự bất kỳ**, cho ta thuật toán GENERIC-PUSH-RELABEL:

```text
GENERIC-PUSH-RELABEL(G)
1  INITIALIZE-PREFLOW(G, s)
2  while there exists an applicable push or relabel operation
3      select an applicable push or relabel operation and perform it
```

Bổ đề sau cho biết chừng nào còn đỉnh tràn thì ít nhất một trong hai thao tác áp dụng được.

**Bổ đề 26.14 (Đỉnh tràn luôn đẩy được hoặc nâng nhãn được).** Cho G = (V, E) là mạng luồng với nguồn s và đích t, f là tiền luồng, h là một hàm độ cao bất kỳ cho f. Nếu u là đỉnh tràn thì thao tác đẩy hoặc thao tác nâng nhãn áp dụng được cho u.

*Chứng minh.* Với mọi cạnh thặng dư (u, v), h(u) ≤ h(v) + 1 vì h là hàm độ cao. Nếu thao tác đẩy không áp dụng được cho đỉnh tràn u thì với mọi cạnh thặng dư (u, v) phải có h(u) < h(v) + 1, kéo theo h(u) ≤ h(v) (độ cao là số nguyên). Vậy thao tác nâng nhãn áp dụng được cho u. ∎

#### Tính đúng của phương pháp đẩy–nâng nhãn (Correctness of the push-relabel method)

Để chứng minh thuật toán tổng quát giải bài toán luồng cực đại, trước hết chứng minh **nếu** nó dừng thì tiền luồng f là luồng cực đại; sau đó chứng minh nó dừng. Bắt đầu bằng vài nhận xét về hàm độ cao.

**Bổ đề 26.15 (Độ cao đỉnh không bao giờ giảm).** Trong khi chạy GENERIC-PUSH-RELABEL trên mạng luồng G = (V, E), với mỗi đỉnh u ∈ V, độ cao u.h không bao giờ giảm. Hơn nữa, mỗi khi thao tác nâng nhãn áp dụng cho u, u.h tăng ít nhất 1.

*Chứng minh.* Độ cao chỉ thay đổi trong thao tác nâng nhãn, nên chỉ cần chứng minh phát biểu thứ hai. Nếu u sắp được nâng nhãn thì với mọi v có (u, v) ∈ E_f, u.h ≤ v.h. Vậy u.h < 1 + min{v.h : (u, v) ∈ E_f}, nên thao tác phải làm tăng u.h. ∎

**Bổ đề 26.16.** Cho G = (V, E) là mạng luồng với nguồn s và đích t. Khi chạy GENERIC-PUSH-RELABEL trên G, thuộc tính h luôn là một hàm độ cao.

*Chứng minh.* Quy nạp theo số thao tác cơ bản đã thực hiện. Ban đầu h là hàm độ cao như đã nhận xét.

Nếu h là hàm độ cao thì sau RELABEL(u), h vẫn là hàm độ cao. Xét cạnh thặng dư (u, v) ∈ E_f rời u: RELABEL(u) bảo đảm u.h ≤ v.h + 1 sau đó. Xét cạnh thặng dư (w, u) đi vào u: theo Bổ đề 26.15, w.h ≤ u.h + 1 trước khi nâng nhãn kéo theo w.h < u.h + 1 sau đó. Vậy RELABEL(u) giữ h là hàm độ cao.

Xét thao tác PUSH(u, v). Nó có thể thêm cạnh (v, u) vào E_f và có thể xoá (u, v) khỏi E_f. Trường hợp đầu: v.h = u.h − 1 < u.h + 1, nên h vẫn là hàm độ cao. Trường hợp sau: xoá (u, v) khỏi mạng thặng dư xoá luôn ràng buộc tương ứng, h vẫn là hàm độ cao. ∎

Bổ đề sau cho một tính chất quan trọng của hàm độ cao.

**Bổ đề 26.17.** Cho G = (V, E) là mạng luồng với nguồn s và đích t, f là tiền luồng trong G, h là hàm độ cao trên V. Khi đó không có đường đi nào từ nguồn s tới đích t trong mạng thặng dư G_f.

*Chứng minh.* Giả sử phản chứng G_f chứa một đường đi p từ s tới t, p = ⟨v₀, v₁, …, v_k⟩ với v₀ = s, v_k = t. Không mất tổng quát, p là đường đi đơn, nên k < |V|. Với i = 0, 1, …, k − 1, cạnh (vᵢ, vᵢ₊₁) ∈ E_f. Vì h là hàm độ cao, h(vᵢ) ≤ h(vᵢ₊₁) + 1. Cộng dồn dọc đường p được h(s) ≤ h(t) + k. Nhưng h(t) = 0 nên h(s) ≤ k < |V|, mâu thuẫn với yêu cầu h(s) = |V| của hàm độ cao. ∎

Ý nghĩa (người tổng hợp): trong suốt quá trình chạy, mạng thặng dư của tiền luồng luôn "bị cắt" giữa s và t — giống điều kiện (2) của định lý luồng cực đại – lát cắt cực tiểu. Ford-Fulkerson luôn giữ luồng hợp lệ và tiến tới trạng thái "không còn đường"; đẩy–nâng nhãn luôn giữ "không còn đường" và tiến tới trạng thái "luồng hợp lệ".

**Định lý 26.18 (Tính đúng của thuật toán đẩy–nâng nhãn tổng quát).** Nếu GENERIC-PUSH-RELABEL dừng khi chạy trên mạng luồng G = (V, E) với nguồn s và đích t, thì tiền luồng f nó tính được là luồng cực đại của G.

*Chứng minh.* Dùng bất biến vòng lặp sau:

> Mỗi lần kiểm tra điều kiện vòng while ở dòng 2 của GENERIC-PUSH-RELABEL, f là một tiền luồng.

- **Khởi tạo:** INITIALIZE-PREFLOW làm f thành tiền luồng.
- **Duy trì:** Các thao tác duy nhất trong vòng while dòng 2–3 là đẩy và nâng nhãn. Nâng nhãn chỉ ảnh hưởng thuộc tính độ cao, không ảnh hưởng giá trị luồng, nên không ảnh hưởng việc f có là tiền luồng hay không. Như đã lập luận khi giải thích PUSH, nếu f là tiền luồng trước một lần đẩy thì sau đó vẫn là tiền luồng.
- **Kết thúc:** Khi dừng, mọi đỉnh trong V − {s, t} phải có luồng dư 0, vì theo Bổ đề 26.14 và bất biến (f luôn là tiền luồng), không còn đỉnh tràn. Do đó f là một luồng. Bổ đề 26.16 cho biết h là hàm độ cao khi dừng, nên Bổ đề 26.17 cho biết không có đường từ s tới t trong mạng thặng dư G_f. Theo định lý luồng cực đại – lát cắt cực tiểu (Định lý 26.6), f là luồng cực đại. ∎

#### Phân tích phương pháp đẩy–nâng nhãn (Analysis of the push-relabel method)

Để chứng minh thuật toán tổng quát thực sự dừng, ta chặn số thao tác nó thực hiện, chặn riêng từng loại: nâng nhãn, đẩy bão hoà, đẩy không bão hoà. Biết các cận này, dễ dựng một thuật toán chạy O(V²E). Trước hết cần một bổ đề quan trọng. Nhắc lại: mạng thặng dư được phép có cạnh đi vào nguồn.

**Bổ đề 26.19.** Cho G = (V, E) là mạng luồng với nguồn s và đích t, f là tiền luồng trong G. Khi đó với mọi đỉnh tràn x, có một đường đi đơn từ x tới s trong mạng thặng dư G_f.

*Chứng minh.* Với đỉnh tràn x, đặt U = {v : có đường đi đơn từ x tới v trong G_f}, và giả sử phản chứng s ∉ U. Đặt Ū = V − U.

Lấy định nghĩa luồng dư (26.14), cộng trên mọi đỉnh của U, chú ý V = U ∪ Ū:

```text
Σ_{u∈U} e(u)
  = Σ_{u∈U} ( Σ_{v∈V} f(v,u) − Σ_{v∈V} f(u,v) )
  = Σ_{u∈U} ( (Σ_{v∈U} f(v,u) + Σ_{v∈Ū} f(v,u)) − (Σ_{v∈U} f(u,v) + Σ_{v∈Ū} f(u,v)) )
  = Σ_{u∈U}Σ_{v∈U} f(v,u) + Σ_{u∈U}Σ_{v∈Ū} f(v,u) − Σ_{u∈U}Σ_{v∈U} f(u,v) − Σ_{u∈U}Σ_{v∈Ū} f(u,v)
  = Σ_{u∈U}Σ_{v∈Ū} f(v,u) − Σ_{u∈U}Σ_{v∈Ū} f(u,v)
```

(dòng cuối: hai tổng trong U triệt tiêu nhau). Đại lượng Σ_{u∈U} e(u) phải dương vì e(x) > 0, x ∈ U, mọi đỉnh khác s có luồng dư không âm, và theo giả thiết s ∉ U. Vậy

```text
Σ_{u∈U}Σ_{v∈Ū} f(v,u) − Σ_{u∈U}Σ_{v∈Ū} f(u,v) > 0                    (26.17)
```

Mọi luồng trên cạnh không âm, nên để (26.17) đúng phải có Σ_{u∈U}Σ_{v∈Ū} f(v, u) > 0. Do đó tồn tại ít nhất một cặp đỉnh u′ ∈ U, v′ ∈ Ū với f(v′, u′) > 0. Nhưng nếu f(v′, u′) > 0 thì có cạnh thặng dư (u′, v′), nghĩa là có đường đi đơn từ x tới v′ (đường x ⇝ u′ → v′), mâu thuẫn với định nghĩa U. ∎

Bổ đề tiếp theo chặn độ cao các đỉnh, và hệ quả của nó chặn tổng số lần nâng nhãn.

**Bổ đề 26.20.** Cho G = (V, E) là mạng luồng với nguồn s và đích t. Tại mọi thời điểm khi chạy GENERIC-PUSH-RELABEL trên G, u.h ≤ 2|V| − 1 với mọi đỉnh u ∈ V.

*Chứng minh.* Độ cao của nguồn s và đích t không bao giờ đổi vì theo định nghĩa chúng không tràn. Vậy luôn có s.h = |V| và t.h = 0, cả hai không lớn hơn 2|V| − 1.

Xét đỉnh u ∈ V − {s, t} bất kỳ. Ban đầu u.h = 0 ≤ 2|V| − 1. Ta chứng minh sau mỗi lần nâng nhãn vẫn có u.h ≤ 2|V| − 1. Khi u được nâng nhãn, u đang tràn, và Bổ đề 26.19 cho biết có đường đi đơn p từ u tới s trong G_f. Gọi p = ⟨v₀, v₁, …, v_k⟩ với v₀ = u, v_k = s, và k ≤ |V| − 1 vì p đơn. Với i = 0, 1, …, k − 1, (vᵢ, vᵢ₊₁) ∈ E_f nên theo Bổ đề 26.16, vᵢ.h ≤ vᵢ₊₁.h + 1. Cộng dồn dọc p: u.h = v₀.h ≤ v_k.h + k ≤ s.h + (|V| − 1) = 2|V| − 1. ∎

**Hệ quả 26.21 (Cận số lần nâng nhãn).** Cho G = (V, E) là mạng luồng với nguồn s và đích t. Khi chạy GENERIC-PUSH-RELABEL trên G, số lần nâng nhãn nhiều nhất là 2|V| − 1 cho mỗi đỉnh và nhiều nhất (2|V| − 1)(|V| − 2) < 2|V|² tổng cộng.

*Chứng minh.* Chỉ |V| − 2 đỉnh của V − {s, t} có thể được nâng nhãn. Với u ∈ V − {s, t}, RELABEL(u) tăng u.h (ít nhất 1, Bổ đề 26.15). Giá trị u.h ban đầu bằng 0 và theo Bổ đề 26.20 tăng tới nhiều nhất 2|V| − 1. Vậy mỗi đỉnh được nâng nhãn nhiều nhất 2|V| − 1 lần, tổng số lần nâng nhãn nhiều nhất (2|V| − 1)(|V| − 2) < 2|V|². ∎

Bổ đề 26.20 cũng giúp chặn số lần đẩy bão hoà.

**Bổ đề 26.22 (Cận số lần đẩy bão hoà).** Khi chạy GENERIC-PUSH-RELABEL trên mạng luồng G = (V, E) bất kỳ, số lần đẩy bão hoà ít hơn 2|V||E|.

*Chứng minh.* Với mỗi cặp đỉnh u, v ∈ V, đếm chung các lần đẩy bão hoà từ u sang v và từ v sang u, gọi là các lần đẩy bão hoà **giữa** u và v. Nếu có lần đẩy như vậy thì ít nhất một trong (u, v), (v, u) thực sự là cạnh của E. Giả sử vừa có một lần đẩy bão hoà từ u sang v. Lúc đó v.h = u.h − 1. Để có lần đẩy từ u sang v về sau, thuật toán trước hết phải đẩy luồng từ v sang u (cạnh (u, v) đã biến mất khỏi mạng thặng dư), điều không thể xảy ra trước khi v.h = u.h + 1. Vì u.h không bao giờ giảm, để v.h = u.h + 1 thì v.h phải tăng ít nhất 2. Tương tự, u.h phải tăng ít nhất 2 giữa hai lần đẩy bão hoà từ v sang u. Độ cao bắt đầu từ 0 và theo Bổ đề 26.20 không vượt 2|V| − 1, nên số lần một đỉnh bất kỳ có thể tăng độ cao thêm 2 ít hơn |V|. Vì giữa hai lần đẩy bão hoà liên tiếp giữa u và v, ít nhất một trong u.h, v.h phải tăng 2, có ít hơn 2|V| lần đẩy bão hoà giữa u và v. Nhân với số cạnh được cận ít hơn 2|V||E| cho tổng số lần đẩy bão hoà. ∎

Bổ đề sau chặn số lần đẩy không bão hoà trong thuật toán tổng quát.

**Bổ đề 26.23 (Cận số lần đẩy không bão hoà).** Khi chạy GENERIC-PUSH-RELABEL trên mạng luồng G = (V, E) bất kỳ, số lần đẩy không bão hoà ít hơn 4|V|²(|V| + |E|).

*Chứng minh.* Định nghĩa **hàm thế** (potential function) Φ = Σ_{v : e(v)>0} v.h (tổng độ cao các đỉnh có luồng dư dương). Ban đầu Φ = 0, và Φ có thể thay đổi sau mỗi lần nâng nhãn, đẩy bão hoà, đẩy không bão hoà. Ta chặn lượng mà đẩy bão hoà và nâng nhãn có thể làm Φ tăng, rồi chứng minh mỗi lần đẩy không bão hoà làm Φ giảm ít nhất 1, và dùng các cận này để chặn số lần đẩy không bão hoà.

Hai cách Φ có thể tăng. Thứ nhất, nâng nhãn đỉnh u làm Φ tăng ít hơn 2|V|, vì tập lấy tổng không đổi và nâng nhãn không thể tăng độ cao của u quá độ cao tối đa có thể của nó, mà theo Bổ đề 26.20 là 2|V| − 1. Thứ hai, một lần đẩy bão hoà từ u sang v làm Φ tăng ít hơn 2|V|, vì không độ cao nào thay đổi và chỉ đỉnh v, có độ cao nhiều nhất 2|V| − 1, có thể trở thành tràn.

Bây giờ chứng minh một lần đẩy không bão hoà từ u sang v làm Φ giảm ít nhất 1. Trước lần đẩy, u đang tràn, v có thể tràn hoặc không. Theo Bổ đề 26.13, sau lần đẩy u không còn tràn. Ngoài ra, trừ khi v là nguồn, sau lần đẩy v có thể tràn hoặc không. Vậy Φ giảm đúng u.h, và tăng 0 hoặc v.h. Vì u.h − v.h = 1, tác động ròng là Φ giảm ít nhất 1.

Như vậy trong cả quá trình, tổng lượng tăng của Φ là do nâng nhãn và đẩy bão hoà, và Hệ quả 26.21, Bổ đề 26.22 chặn lượng tăng này dưới (2|V|)(2|V|²) + (2|V|)(2|V||E|) = 4|V|²(|V| + |E|). Vì Φ ≥ 0, tổng lượng giảm, và do đó tổng số lần đẩy không bão hoà, ít hơn 4|V|²(|V| + |E|). ∎

Đã chặn được số lần nâng nhãn, đẩy bão hoà và đẩy không bão hoà, ta có phân tích cho GENERIC-PUSH-RELABEL, và do đó cho mọi thuật toán dựa trên phương pháp đẩy–nâng nhãn.

**Định lý 26.24.** Khi chạy GENERIC-PUSH-RELABEL trên mạng luồng G = (V, E) bất kỳ, số thao tác cơ bản là O(V²E).

*Chứng minh.* Suy ngay từ Hệ quả 26.21, Bổ đề 26.22 và 26.23. ∎ (Người tổng hợp làm rõ: 2|V|² + 2|V||E| + 4|V|²(|V| + |E|) = O(V³ + V²E) = O(V²E), vì theo giả định mọi đỉnh nằm trên đường từ s tới t nên |E| ≥ |V| − 1.)

Vậy thuật toán dừng sau O(V²E) thao tác. Còn lại là cho một cách hiệu quả để cài đặt từng thao tác và để chọn thao tác thích hợp.

**Hệ quả 26.25.** Có một cài đặt của thuật toán đẩy–nâng nhãn tổng quát chạy trong O(V²E) trên mọi mạng luồng G = (V, E).

*Chứng minh.* Exercise 26.4-2 yêu cầu chỉ cách cài đặt thuật toán tổng quát với chi phí O(V) mỗi lần nâng nhãn và O(1) mỗi lần đẩy, và thiết kế cấu trúc dữ liệu cho phép chọn một thao tác áp dụng được trong O(1). Hệ quả suy ra từ đó. ∎

#### Ví dụ chạy tay của người tổng hợp (sách không có ví dụ chạy tay cho Mục 26.4)

Mạng bốn đỉnh (|V| = 4): s → a sức chứa 3, s → b sức chứa 2, a → b sức chứa 1, a → t sức chứa 2, b → t sức chứa 2. Luồng cực đại là 4 (lát cắt ({s, a, b}, {t}) có sức chứa 2 + 2 = 4). Ký hiệu h(·), e(·).

| Bước | Thao tác | Lý do / tính toán | Sau bước |
|---|---|---|---|
| 0 | INITIALIZE-PREFLOW | f(s,a) = 3, f(s,b) = 2; h(s) = 4 | e(a) = 3, e(b) = 2, e(s) = −5 |
| 1 | RELABEL(a) | cạnh thặng dư rời a: a→b (1, h 0), a→t (2, h 0), a→s (3, h 4); không đẩy được vì h(a) = 0 | h(a) = 1 + min(0, 0, 4) = 1 |
| 2 | PUSH(a, b) | h(a) = 1 = h(b) + 1; Δ = min(3, 1) = 1, bão hoà | f(a,b) = 1; e(a) = 2, e(b) = 3 |
| 3 | PUSH(a, t) | Δ = min(2, 2) = 2, bão hoà | f(a,t) = 2; e(a) = 0, e(t) = 2 |
| 4 | RELABEL(b) | rời b: b→t (2, h 0), b→s (2, h 4), b→a (1, h 1) | h(b) = 1 + min(0, 4, 1) = 1 |
| 5 | PUSH(b, t) | Δ = min(3, 2) = 2, bão hoà | f(b,t) = 2; e(b) = 1, e(t) = 4 |
| 6 | RELABEL(b) | rời b còn: b→s (2, h 4), b→a (1, h 1) | h(b) = 1 + min(4, 1) = 2 |
| 7 | PUSH(b, a) | cạnh ngược của a→b; Δ = min(1, 1) = 1, bão hoà | f(a,b) = 0; e(b) = 0, e(a) = 1 |
| 8 | RELABEL(a) | rời a: a→b (1, h 2), a→s (3, h 4) | h(a) = 1 + min(2, 4) = 3 |
| 9 | PUSH(a, b) | h(a) = 3 = h(b) + 1; Δ = 1, bão hoà | f(a,b) = 1; e(a) = 0, e(b) = 1 |
| 10 | RELABEL(b) | rời b: b→s (2, h 4), b→a (1, h 3) | h(b) = 1 + min(4, 3) = 4 |
| 11 | PUSH(b, a) | Δ = 1, bão hoà | f(a,b) = 0; e(b) = 0, e(a) = 1 |
| 12 | RELABEL(a) | rời a: a→b (1, h 4), a→s (3, h 4) | h(a) = 5 |
| 13 | PUSH(a, s) | h(a) = 5 = h(s) + 1; cạnh ngược của s→a; Δ = min(1, 3) = 1, không bão hoà | f(s,a) = 2; e(a) = 0, e(s) = −4 |
| — | dừng | không còn đỉnh tràn | |

Kết quả: f(s,a) = 2, f(s,b) = 2, f(a,b) = 0, f(a,t) = 2, f(b,t) = 2, giá trị 4 = luồng cực đại. Ví dụ cho thấy: (1) đơn vị luồng thừa "đi qua lại" giữa a và b (bước 7–11) trong khi độ cao hai đỉnh tăng dần 2 mỗi lượt — đúng cơ chế trong chứng minh Bổ đề 26.22; (2) độ cao a lên tới 5 > |V| = 4 thì luồng thừa mới chảy về nguồn — đúng hình ảnh "nâng các đỉnh lên cao hơn nguồn để trả luồng dư về"; (3) độ cao lớn nhất là 5 ≤ 2|V| − 1 = 7 (Bổ đề 26.20); mỗi đỉnh nâng nhãn 3 lần ≤ 7 (Hệ quả 26.21).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: các cài đặt đẩy–nâng nhãn với heuristic "nâng nhãn toàn cục" (global relabeling — tính lại độ cao bằng BFS ngược từ t, chính là ý của Exercise 26.4-8, 26.4-9) và "khe hở" (gap heuristic) nằm trong nhiều thư viện tối ưu hoá mạng (ví dụ thuật toán max-flow của Google OR-Tools, hàm `preflow_push` của NetworkX, `push_relabel_max_flow` của Boost). Ý tưởng tiền luồng còn là nền của nhiều thuật toán luồng song song, vì mỗi đỉnh tự quyết định chỉ dựa trên thông tin cục bộ.

### 6. ★ Thuật toán nâng nhãn rồi đưa lên đầu (26.5 The relabel-to-front algorithm, trang 748–760)

Phương pháp đẩy–nâng nhãn cho phép áp dụng các thao tác cơ bản theo **bất kỳ** thứ tự nào. Nhưng nếu chọn thứ tự cẩn thận và quản lý cấu trúc dữ liệu mạng hiệu quả, có thể giải bài toán luồng cực đại nhanh hơn cận O(V²E) của Hệ quả 26.25. Mục này khảo sát thuật toán **nâng nhãn rồi đưa lên đầu** (relabel-to-front), một thuật toán đẩy–nâng nhãn có thời gian chạy O(V³), về tiệm cận ít nhất tốt bằng O(V²E) và tốt hơn hẳn với mạng dày.

Thuật toán giữ một danh sách các đỉnh của mạng. Bắt đầu từ đầu danh sách, nó quét danh sách, lặp lại việc chọn một đỉnh tràn u rồi **xả** (discharge) nó, tức là thực hiện các thao tác đẩy và nâng nhãn cho tới khi u không còn luồng dư dương. Mỗi khi nâng nhãn một đỉnh, thuật toán chuyển đỉnh đó lên **đầu danh sách** (từ đó có tên "relabel-to-front") và bắt đầu quét lại.

Tính đúng và phân tích của thuật toán dựa vào khái niệm cạnh "chấp nhận được": các cạnh trong mạng thặng dư mà qua đó đẩy được luồng. Sau khi chứng minh vài tính chất của mạng các cạnh chấp nhận được, sách khảo sát thao tác xả, rồi trình bày và phân tích chính thuật toán.

#### Cạnh và mạng chấp nhận được (Admissible edges and networks)

Nếu G = (V, E) là mạng luồng với nguồn s và đích t, f là tiền luồng trong G, h là hàm độ cao, thì (u, v) là **cạnh chấp nhận được** (admissible edge) nếu c_f(u, v) > 0 và h(u) = h(v) + 1. Ngược lại, (u, v) **không chấp nhận được** (inadmissible). **Mạng chấp nhận được** (admissible network) là G_{f,h} = (V, E_{f,h}), với E_{f,h} là tập các cạnh chấp nhận được.

Mạng chấp nhận được gồm các cạnh mà qua đó có thể đẩy luồng. Bổ đề sau cho thấy nó là một đồ thị có hướng không chu trình (dag).

**Bổ đề 26.26 (Mạng chấp nhận được không có chu trình).** Nếu G = (V, E) là mạng luồng, f là tiền luồng trong G, h là hàm độ cao trên G, thì mạng chấp nhận được G_{f,h} = (V, E_{f,h}) không có chu trình.

*Chứng minh.* Phản chứng. Giả sử G_{f,h} chứa chu trình p = ⟨v₀, v₁, …, v_k⟩ với v₀ = v_k và k > 0. Vì mỗi cạnh trên p chấp nhận được, h(v_{i−1}) = h(vᵢ) + 1 với i = 1, 2, …, k. Cộng quanh chu trình:

```text
Σ_{i=1}^{k} h(v_{i−1}) = Σ_{i=1}^{k} (h(vᵢ) + 1)
                       = Σ_{i=1}^{k} h(vᵢ) + k
```

Vì mỗi đỉnh của chu trình xuất hiện đúng một lần trong mỗi tổng, ta được mâu thuẫn 0 = k. ∎

Hai bổ đề tiếp cho thấy thao tác đẩy và nâng nhãn thay đổi mạng chấp nhận được thế nào.

**Bổ đề 26.27.** Cho G = (V, E) là mạng luồng, f là tiền luồng trong G, và giả sử thuộc tính h là hàm độ cao. Nếu đỉnh u tràn và (u, v) là cạnh chấp nhận được thì PUSH(u, v) áp dụng được. Thao tác này không tạo cạnh chấp nhận được mới nào, nhưng có thể làm (u, v) trở thành không chấp nhận được.

*Chứng minh.* Theo định nghĩa cạnh chấp nhận được, có thể đẩy luồng từ u sang v. Vì u tràn, PUSH(u, v) áp dụng được. Cạnh thặng dư mới duy nhất mà việc đẩy luồng từ u sang v có thể tạo ra là (v, u). Vì v.h = u.h − 1, cạnh (v, u) không thể chấp nhận được. Nếu là đẩy bão hoà thì c_f(u, v) = 0 sau đó và (u, v) trở thành không chấp nhận được. ∎

**Bổ đề 26.28.** Cho G = (V, E) là mạng luồng, f là tiền luồng trong G, và giả sử thuộc tính h là hàm độ cao. Nếu đỉnh u tràn và không có cạnh chấp nhận được nào rời u thì RELABEL(u) áp dụng được. Sau khi nâng nhãn, có ít nhất một cạnh chấp nhận được rời u, nhưng không có cạnh chấp nhận được nào đi vào u.

*Chứng minh.* Nếu u tràn thì theo Bổ đề 26.14, thao tác đẩy hoặc nâng nhãn áp dụng được cho u. Nếu không có cạnh chấp nhận được rời u thì không đẩy được luồng từ u, nên RELABEL(u) áp dụng được. Sau khi nâng nhãn, u.h = 1 + min{v.h : (u, v) ∈ E_f}. Vậy nếu v là đỉnh đạt min trong tập này thì cạnh (u, v) trở thành chấp nhận được. Do đó sau khi nâng nhãn có ít nhất một cạnh chấp nhận được rời u.

Để chứng minh không có cạnh chấp nhận được nào đi vào u sau khi nâng nhãn, giả sử có đỉnh v với (v, u) chấp nhận được. Khi đó v.h = u.h + 1 sau khi nâng nhãn, nên v.h > u.h + 1 ngay trước khi nâng nhãn. Nhưng theo Bổ đề 26.12, không có cạnh thặng dư giữa hai đỉnh chênh độ cao hơn 1. Hơn nữa, nâng nhãn không thay đổi mạng thặng dư. Vậy (v, u) không thuộc mạng thặng dư, nên không thể thuộc mạng chấp nhận được. ∎

#### Danh sách đỉnh kề (Neighbor lists)

Các cạnh trong thuật toán nâng nhãn rồi đưa lên đầu được tổ chức thành "danh sách đỉnh kề". Cho mạng luồng G = (V, E), **danh sách đỉnh kề** (neighbor list) u.N của đỉnh u ∈ V là danh sách liên kết đơn các đỉnh kề u trong G. Tức là v xuất hiện trong u.N nếu (u, v) ∈ E **hoặc** (v, u) ∈ E. Danh sách u.N chứa đúng những đỉnh v mà có thể có cạnh thặng dư (u, v). Thuộc tính u.N.head trỏ tới đỉnh đầu tiên của u.N, và v.next-neighbor trỏ tới đỉnh sau v trong một danh sách đỉnh kề; con trỏ này là NIL nếu v là đỉnh cuối.

Thuật toán đi vòng qua mỗi danh sách đỉnh kề theo một thứ tự tuỳ ý nhưng cố định suốt quá trình chạy. Với mỗi đỉnh u, thuộc tính u.current trỏ tới đỉnh đang xét trong u.N. Ban đầu u.current = u.N.head.

#### Xả một đỉnh tràn (Discharging an overflowing vertex)

Một đỉnh tràn u được **xả** (discharged) bằng cách đẩy toàn bộ luồng dư của nó qua các cạnh chấp nhận được sang các đỉnh kề, nâng nhãn u khi cần để các cạnh rời u trở thành chấp nhận được.

```text
DISCHARGE(u)
1  while u.e > 0
2      v = u.current
3      if v == NIL
4          RELABEL(u)
5          u.current = u.N.head
6      elseif c_f(u, v) > 0 and u.h == v.h + 1
7          PUSH(u, v)
8      else u.current = v.next-neighbor
```

Vòng while dòng 1–8 chạy chừng nào u còn luồng dư dương. Mỗi vòng thực hiện đúng một trong ba hành động, tuỳ đỉnh hiện tại v trong danh sách u.N:

1. Nếu v là NIL thì đã đi hết u.N. Dòng 4 nâng nhãn u, dòng 5 đặt lại đỉnh kề hiện tại của u về đầu u.N. (Bổ đề 26.29 dưới đây khẳng định thao tác nâng nhãn áp dụng được trong tình huống này.)
2. Nếu v khác NIL và (u, v) là cạnh chấp nhận được (kiểm tra ở dòng 6) thì dòng 7 đẩy một phần (hoặc toàn bộ) luồng dư của u sang v.
3. Nếu v khác NIL nhưng (u, v) không chấp nhận được thì dòng 8 dịch u.current thêm một vị trí trong u.N.

Lưu ý: nếu DISCHARGE được gọi trên một đỉnh tràn u thì hành động cuối cùng nó làm phải là một lần đẩy từ u. Vì sao? Thủ tục chỉ dừng khi u.e về 0, và cả nâng nhãn lẫn dịch con trỏ u.current đều không ảnh hưởng u.e.

**Ví dụ: xả đỉnh y (vẽ lại Hình 26.9, 15 vòng lặp while).** Hình chỉ vẽ các đỉnh kề của y và các cạnh vào/ra y. Độ cao: s.h = 5, x.h = 1, z.h = 0, ban đầu y.h = 0. Cạnh: s → y luồng 14/14, x → y luồng 5/5, y → z sức chứa 8 chưa có luồng. Luồng dư ban đầu: e(y) = 19, e(x) = 0, e(z) = 0, e(s) = −26. Danh sách y.N = ⟨s, x, z⟩, ban đầu y.current = s.

| Vòng | y.current | y.h | Hành động | Kết quả |
|---|---|---|---|---|
| 1 | s | 0 | (y, s): sức chứa thặng dư 14 nhưng y.h ≠ s.h + 1 → không chấp nhận được | dịch sang x |
| 2 | x | 0 | (y, x): thặng dư 5 nhưng 0 ≠ 1 + 1 → không | dịch sang z |
| 3 | z | 0 | (y, z): thặng dư 8 nhưng 0 ≠ 0 + 1 → không | dịch sang NIL |
| 4 | NIL | 0 → 1 | RELABEL(y): 1 + min(5, 1, 0) = 1; đặt current = s | y.h = 1 |
| 5 | s | 1 | (y, s) không chấp nhận được | dịch sang x |
| 6 | x | 1 | (y, x): 1 ≠ 1 + 1 → không | dịch sang z |
| 7 | z | 1 | (y, z) chấp nhận được: PUSH đẩy min(19, 8) = 8, bão hoà (current không dịch) | e(y) = 11, e(z) = 8, y→z = 8/8 |
| 8 | z | 1 | (y, z) đã bão hoà → không chấp nhận được | dịch sang NIL |
| 9 | NIL | 1 → 2 | RELABEL(y): cạnh thặng dư còn y→s (h 5), y→x (h 1): 1 + 1 = 2; current = s | y.h = 2 |
| 10 | s | 2 | (y, s) không chấp nhận được | dịch sang x |
| 11 | x | 2 | (y, x) chấp nhận được: đẩy min(11, 5) = 5 (triệt tiêu luồng x→y) | e(y) = 6, e(x) = 5, x→y = 0/5 |
| 12 | x | 2 | (y, x) hết thặng dư → không | dịch sang z |
| 13 | z | 2 | (y, z) bão hoà → không | dịch sang NIL |
| 14 | NIL | 2 → 6 | RELABEL(y): chỉ còn y→s (h 5): 1 + 5 = 6; current = s | y.h = 6 |
| 15 | s | 6 | (y, s) chấp nhận được: đẩy min(6, 14) = 6 về nguồn (giảm luồng s→y) | e(y) = 0, s→y = 8/14, e(s) = −20 |

Sau vòng 15, y không còn luồng dư và DISCHARGE dừng. Trong ví dụ này DISCHARGE bắt đầu và kết thúc với con trỏ current ở đầu danh sách, nhưng nói chung không nhất thiết như vậy.

Cần chắc rằng khi DISCHARGE gọi PUSH hay RELABEL thì thao tác đó áp dụng được. Bổ đề sau chứng minh điều này.

**Bổ đề 26.29.** Nếu DISCHARGE gọi PUSH(u, v) ở dòng 7 thì thao tác đẩy áp dụng được cho (u, v). Nếu DISCHARGE gọi RELABEL(u) ở dòng 4 thì thao tác nâng nhãn áp dụng được cho u.

*Chứng minh.* Các kiểm tra ở dòng 1 và 6 bảo đảm thao tác đẩy chỉ xảy ra khi nó áp dụng được, chứng minh phát biểu thứ nhất.

Để chứng minh phát biểu thứ hai, theo kiểm tra ở dòng 1 và Bổ đề 26.28, chỉ cần chứng minh mọi cạnh rời u đều không chấp nhận được. Nếu một lần gọi DISCHARGE(u) bắt đầu với con trỏ u.current ở đầu danh sách và kết thúc khi nó đi quá cuối danh sách, thì mọi cạnh rời u đều không chấp nhận được và nâng nhãn áp dụng được. Tuy nhiên, có thể trong một lần gọi DISCHARGE(u), con trỏ u.current chỉ đi qua một phần danh sách rồi thủ tục trả về. Sau đó có thể có các lần gọi DISCHARGE trên đỉnh khác, nhưng u.current sẽ tiếp tục đi tiếp trong danh sách ở lần gọi DISCHARGE(u) kế tiếp. Xét điều xảy ra trong một **lượt đi trọn** qua danh sách, bắt đầu ở đầu u.N và kết thúc khi u.current = NIL. Khi u.current tới cuối danh sách, thủ tục nâng nhãn u và bắt đầu lượt mới. Để u.current vượt qua một đỉnh v ∈ u.N trong một lượt, cạnh (u, v) phải bị kiểm tra ở dòng 6 đánh giá là không chấp nhận được. Vậy khi lượt kết thúc, mọi cạnh rời u đều đã từng được xác định là không chấp nhận được vào một lúc nào đó trong lượt. Nhận xét then chốt là **ở cuối lượt, mọi cạnh rời u vẫn không chấp nhận được**. Vì sao? Theo Bổ đề 26.27, thao tác đẩy không tạo cạnh chấp nhận được, bất kể đẩy từ đỉnh nào. Vậy mọi cạnh chấp nhận được mới phải do thao tác nâng nhãn tạo ra. Nhưng u không được nâng nhãn trong lượt, và theo Bổ đề 26.28, mọi đỉnh v khác được nâng nhãn trong lượt (do một lần gọi DISCHARGE(v)) không có cạnh chấp nhận được đi vào sau khi nâng nhãn. Vậy ở cuối lượt, mọi cạnh rời u vẫn không chấp nhận được. ∎

#### Thuật toán nâng nhãn rồi đưa lên đầu (The relabel-to-front algorithm)

Thuật toán giữ một danh sách liên kết L gồm mọi đỉnh của V − {s, t}. Tính chất then chốt: các đỉnh trong L được **sắp xếp topo** theo mạng chấp nhận được (như sẽ thấy ở bất biến vòng lặp dưới đây; nhắc lại theo Bổ đề 26.26, mạng chấp nhận được là một dag).

Mã giả giả định danh sách đỉnh kề u.N đã được tạo cho mỗi đỉnh u, và u.next trỏ tới đỉnh sau u trong L, u.next = NIL nếu u là đỉnh cuối.

```text
RELABEL-TO-FRONT(G, s, t)
 1  INITIALIZE-PREFLOW(G, s)
 2  L = G.V − {s, t}, in any order
 3  for each vertex u ∈ G.V − {s, t}
 4      u.current = u.N.head
 5  u = L.head
 6  while u ≠ NIL
 7      old-height = u.h
 8      DISCHARGE(u)
 9      if u.h > old-height
10          move u to the front of list L
11      u = u.next
```

Cách hoạt động: dòng 1 khởi tạo tiền luồng và độ cao giống thuật toán tổng quát. Dòng 2 khởi tạo L chứa mọi đỉnh có thể tràn, theo thứ tự bất kỳ. Dòng 3–4 đặt con trỏ current của mỗi đỉnh u về đỉnh đầu trong danh sách đỉnh kề của u. Vòng while dòng 6–11 chạy qua danh sách L, xả các đỉnh. Dòng 5 bắt đầu từ đỉnh đầu danh sách. Mỗi vòng, dòng 8 xả một đỉnh u. Nếu u được nâng nhãn trong DISCHARGE, dòng 10 chuyển nó lên đầu L; biết u có được nâng nhãn hay không bằng cách so độ cao trước khi xả (lưu ở biến old-height, dòng 7) với độ cao sau (dòng 9). Dòng 11 cho vòng kế tiếp dùng đỉnh đứng sau u trong L; nếu dòng 10 vừa chuyển u lên đầu thì đó là đỉnh đứng sau u ở vị trí mới.

**Ví dụ chạy tay RELABEL-TO-FRONT (vẽ lại Hình 26.10).** Mạng có 5 đỉnh s, x, y, z, t (nên s.h = 5) với các cạnh: s → x sức chứa 12, s → y sức chứa 14, x → y sức chứa 5, y → z sức chứa 8, z → t sức chứa 10, z → x sức chứa 7, x → t sức chứa 16. Sau INITIALIZE-PREFLOW: s → x = 12/12, s → y = 14/14; e(x) = 12, e(y) = 14, e(s) = −26; mọi độ cao khác 0. L = ⟨x, y, z⟩. Danh sách đỉnh kề: x.N = ⟨s, y, z, t⟩, y.N = ⟨s, x, z⟩, z.N = ⟨x, y, t⟩.

| Phần | Đỉnh được xả | Diễn biến | Trạng thái sau | L sau |
|---|---|---|---|---|
| (a) | x | x.h = 0, không cạnh nào chấp nhận được (s cao 5; y, t cao 0; x → z không có thặng dư); hết danh sách → nâng nhãn x lên 1 + min(5, 0, 0) = 1; đẩy 5 sang y (bão hoà x → y), rồi qua z (không chấp nhận được), đẩy 7 còn lại sang t (không bão hoà); x.current dừng ở t | e(x) = 0, e(y) = 19, e(t) = 7; x → y = 5/5, x → t = 7/16 | x được nâng nhãn, chuyển lên đầu: ⟨x, y, z⟩ (không đổi) |
| (b) | y | 15 vòng lặp như bảng xả y ở trên: đẩy 8 sang z, 5 về x, 6 về s; y.h tăng lên 6 | e(y) = 0, e(x) = 5, e(z) = 8, e(s) = −20; s → y = 8/14, x → y = 0/5, y → z = 8/8 | y được nâng nhãn, lên đầu: ⟨y, x, z⟩ |
| (c) | x (đứng sau y) | x.h = 1, x.current đang ở t: (x, t) chấp nhận được (thặng dư 9, t.h = 0); đẩy toàn bộ 5 sang t | e(x) = 0, e(t) = 12; x → t = 12/16 | x không được nâng nhãn, giữ chỗ: ⟨y, x, z⟩ |
| (d) | z (đứng sau x) | z.h = 0; z.N = ⟨x, y, t⟩: (z, x) có thặng dư 7 nhưng x.h = 1; (z, y) có thặng dư 8 (ngược y → z) nhưng y.h = 6; (z, t) thặng dư 10 nhưng t.h = 0 → nâng nhãn z lên 1 + min(1, 6, 0) = 1; đẩy cả 8 sang t | e(z) = 0, e(t) = 20; z → t = 8/10 | z lên đầu: ⟨z, y, x⟩ |
| (e) | y rồi x | y không có luồng dư, DISCHARGE trả về ngay, y giữ chỗ; x cũng không có luồng dư; hết danh sách | | thuật toán dừng |

Không còn đỉnh tràn; tiền luồng là luồng cực đại với giá trị 20 (luồng vào t: 12 + 8). Kiểm tra của người tổng hợp: lát cắt S = {s, y}, T = {x, z, t} có sức chứa c(s, x) + c(y, z) = 12 + 8 = 20 (cạnh x → y đi từ T sang S không tính), nên 20 đúng là cực đại.

#### Tính đúng (theo lập luận trang 755–758)

Để chứng minh RELABEL-TO-FRONT tính luồng cực đại, ta chứng minh nó là một cài đặt của thuật toán đẩy–nâng nhãn tổng quát. Trước hết, nó chỉ thực hiện đẩy và nâng nhãn khi chúng áp dụng được, vì Bổ đề 26.29 bảo đảm DISCHARGE chỉ thực hiện chúng khi áp dụng được. Còn lại phải chứng minh khi RELABEL-TO-FRONT dừng thì không thao tác cơ bản nào áp dụng được. Phần còn lại của lập luận dựa vào bất biến vòng lặp:

> Mỗi lần kiểm tra ở dòng 6 của RELABEL-TO-FRONT, danh sách L là một sắp xếp topo của các đỉnh trong mạng chấp nhận được G_{f,h} = (V, E_{f,h}), và không đỉnh nào đứng trước u trong danh sách có luồng dư.

- **Khởi tạo:** Ngay sau INITIALIZE-PREFLOW, s.h = |V| và v.h = 0 với mọi v ∈ V − {s}. Vì |V| ≥ 2 (V chứa ít nhất s và t), không cạnh nào chấp nhận được. Vậy E_{f,h} = ∅, và mọi thứ tự của V − {s, t} đều là sắp xếp topo của G_{f,h}. Vì u ban đầu là đầu danh sách L, không có đỉnh nào đứng trước nó, nên không có đỉnh nào đứng trước nó có luồng dư.
- **Duy trì:** Để thấy mỗi vòng while giữ sắp xếp topo, trước hết nhận xét mạng chấp nhận được chỉ thay đổi do đẩy và nâng nhãn. Theo Bổ đề 26.27, thao tác đẩy không làm cạnh nào trở thành chấp nhận được. Vậy chỉ nâng nhãn mới tạo cạnh chấp nhận được. Nhưng sau khi đỉnh u được nâng nhãn, Bổ đề 26.28 nói không có cạnh chấp nhận được nào đi vào u, chỉ có thể có cạnh chấp nhận được đi ra khỏi u. Vậy chuyển u lên đầu L bảo đảm mọi cạnh chấp nhận được rời u thoả thứ tự sắp xếp topo.

  Để thấy không đỉnh nào đứng trước u trong L có luồng dư, ký hiệu u′ là đỉnh sẽ là u ở vòng kế tiếp. Các đỉnh đứng trước u′ ở vòng kế tiếp gồm u hiện tại (do dòng 11) cùng với: không đỉnh nào khác (nếu u được nâng nhãn), hoặc đúng các đỉnh đã đứng trước u (nếu u không được nâng nhãn). Khi u được xả, nó không còn luồng dư. Vậy nếu u được nâng nhãn trong lúc xả, không đỉnh nào đứng trước u′ có luồng dư. Nếu u không được nâng nhãn, không đỉnh nào đứng trước nó trong danh sách nhận thêm luồng dư trong lúc xả, vì L luôn được sắp xếp topo suốt quá trình xả (như vừa nêu, cạnh chấp nhận được chỉ sinh ra do nâng nhãn, không do đẩy), nên mỗi lần đẩy chỉ đưa luồng dư tới các đỉnh đứng sau trong danh sách (hoặc tới s hay t). Một lần nữa, không đỉnh nào đứng trước u′ có luồng dư.
- **Kết thúc:** Khi vòng lặp dừng, u vừa đi quá cuối L, nên bất biến bảo đảm luồng dư của mọi đỉnh bằng 0. Vậy không thao tác cơ bản nào áp dụng được.

#### Phân tích (Analysis)

Ta chứng minh RELABEL-TO-FRONT chạy O(V³) trên mọi mạng luồng G = (V, E). Vì thuật toán là một cài đặt của thuật toán tổng quát, ta tận dụng Hệ quả 26.21, cho cận O(V) số lần nâng nhãn mỗi đỉnh và O(V²) tổng số lần nâng nhãn. Ngoài ra, Exercise 26.4-3 cho cận O(VE) cho tổng thời gian thực hiện các thao tác nâng nhãn, và Bổ đề 26.22 cho cận O(VE) cho tổng số lần đẩy bão hoà.

**Định lý 26.30.** Thời gian chạy của RELABEL-TO-FRONT trên mọi mạng luồng G = (V, E) là O(V³).

*Chứng minh.* Gọi một **pha** (phase) của thuật toán là khoảng thời gian giữa hai lần nâng nhãn liên tiếp. Có O(V²) pha vì có O(V²) lần nâng nhãn. Mỗi pha gồm nhiều nhất |V| lần gọi DISCHARGE, vì: nếu DISCHARGE không nâng nhãn thì lần gọi DISCHARGE kế tiếp ở xa hơn trong danh sách L, và L dài ít hơn |V|; nếu DISCHARGE có nâng nhãn thì lần gọi DISCHARGE kế tiếp thuộc pha khác. Vì mỗi pha có nhiều nhất |V| lần gọi DISCHARGE và có O(V²) pha, số lần gọi DISCHARGE ở dòng 8 là O(V³). Vậy tổng công việc của vòng while trong RELABEL-TO-FRONT, không kể công việc bên trong DISCHARGE, nhiều nhất O(V³).

Còn phải chặn công việc bên trong DISCHARGE trong suốt quá trình chạy. Mỗi vòng while trong DISCHARGE làm một trong ba hành động; phân tích tổng công việc của từng loại:

- **Nâng nhãn (dòng 4–5):** Exercise 26.4-3 cho cận O(VE) cho toàn bộ O(V²) lần nâng nhãn.
- **Dịch con trỏ u.current (dòng 8):** xảy ra O(degree(u)) lần mỗi lần u được nâng nhãn, nên O(V · degree(u)) lần tổng cộng cho đỉnh u. Với mọi đỉnh, tổng công việc dịch con trỏ trong danh sách đỉnh kề là O(VE) theo bổ đề bắt tay (Exercise B.4-1: tổng bậc bằng hai lần số cạnh).
- **Đẩy (dòng 7):** tổng số lần đẩy bão hoà là O(VE). Nếu thực hiện một lần đẩy không bão hoà, DISCHARGE trả về ngay vì lần đẩy đưa luồng dư về 0. Vậy mỗi lần gọi DISCHARGE có nhiều nhất một lần đẩy không bão hoà. DISCHARGE được gọi O(V³) lần, nên tổng thời gian cho đẩy không bão hoà là O(V³).

Vậy thời gian chạy của RELABEL-TO-FRONT là O(V³ + VE), tức O(V³). ∎

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: các cài đặt đẩy–nâng nhãn thực tế thường dùng chiến lược "chọn đỉnh tràn cao nhất" (highest-label, Exercise 26.5-4, chạy O(V²√E)) hoặc hàng đợi FIFO (Exercise 26.5-2), kèm heuristic khe hở (Exercise 26.5-5) và nâng nhãn toàn cục; relabel-to-front chủ yếu có giá trị giảng dạy vì bất biến "danh sách là sắp xếp topo của mạng chấp nhận được" làm chứng minh O(V³) rất gọn.

## Bài tập và bài toán cuối chương

### Bài tập Mục 26.1 (trang 712–714)

- **26.1-1:** Chứng minh tách một cạnh trong mạng luồng cho mạng tương đương. Cụ thể: mạng G chứa cạnh (u, v); tạo mạng G′ bằng cách thêm đỉnh mới x và thay (u, v) bằng hai cạnh (u, x), (x, v) với c(u, x) = c(x, v) = c(u, v). Chứng minh luồng cực đại trong G′ có cùng giá trị với luồng cực đại trong G. *Người tổng hợp:* cho luồng f trong G, đặt f′(u, x) = f′(x, v) = f(u, v), các cạnh khác giữ nguyên: f′ hợp lệ (x bảo toàn) và cùng giá trị. Ngược lại, luồng f′ trong G′ có f′(u, x) = f′(x, v) do bảo toàn tại x; đặt f(u, v) bằng giá trị đó. Hai chiều giữ giá trị nên hai cực đại bằng nhau.
- **26.1-2:** Mở rộng các tính chất và định nghĩa luồng cho bài toán nhiều nguồn, nhiều đích. Chứng minh mọi luồng trong mạng nhiều nguồn nhiều đích tương ứng với một luồng cùng giá trị trong mạng một nguồn một đích (thêm siêu nguồn, siêu đích), và ngược lại. *Người tổng hợp:* định nghĩa: bảo toàn luồng tại mọi đỉnh không phải nguồn hay đích; giá trị |f| = Σᵢ (Σ_v f(sᵢ, v) − Σ_v f(v, sᵢ)). Chiều thuận: đặt f(s, sᵢ) bằng luồng ròng ra khỏi sᵢ và f(tⱼ, t) bằng luồng ròng vào tⱼ; sức chứa ∞ nên hợp lệ (giả định thêm luồng ròng ra khỏi mỗi nguồn và vào mỗi đích không âm, điều sách ngầm hiểu), giá trị bằng tổng luồng ròng ra khỏi các nguồn. Chiều ngược: bỏ s, t và các cạnh vô hạn; bảo toàn tại sᵢ trong mạng mới cho luồng ròng ra khỏi sᵢ bằng f(s, sᵢ), cộng lại đúng bằng giá trị.
- **26.1-3:** Giả sử mạng G vi phạm giả định mọi đỉnh nằm trên một đường s ⇝ v ⇝ t. Cho u là đỉnh không có đường s ⇝ u ⇝ t. Chứng minh tồn tại luồng cực đại f trong G với f(u, v) = f(v, u) = 0 với mọi v. *Người tổng hợp:* phân rã một luồng cực đại thành các đường s–t và các chu trình; mọi đường s–t không đi qua u; bỏ các chu trình (không đổi giá trị). Luồng còn lại không chạm u.
- **26.1-4:** Cho f là luồng, α là số thực. **Tích vô hướng** αf là hàm (αf)(u, v) = α · f(u, v). Chứng minh tập các luồng là **tập lồi**: nếu f₁, f₂ là luồng thì αf₁ + (1 − α)f₂ là luồng với mọi 0 ≤ α ≤ 1. *Người tổng hợp:* ràng buộc sức chứa: 0 ≤ αf₁ + (1 − α)f₂ ≤ αc + (1 − α)c = c; bảo toàn luồng: là tổ hợp tuyến tính của hai đẳng thức tuyến tính.
- **26.1-5:** Phát biểu bài toán luồng cực đại thành bài toán quy hoạch tuyến tính. *Người tổng hợp:* biến f_{uv} cho mỗi (u, v) ∈ E; cực đại Σ_v f_{sv} − Σ_v f_{vs}; ràng buộc 0 ≤ f_{uv} ≤ c(u, v), và Σ_v f_{vu} − Σ_v f_{uv} = 0 với mọi u ∈ V − {s, t} (xem Chương 29).
- **26.1-6:** Giáo sư Adam có hai con ghét nhau đến mức không đi chung đường tới trường và mỗi đứa không chịu đi trên bất kỳ đoạn phố nào đứa kia đã đi trong ngày; chúng không ngại đường cắt nhau tại góc phố. Nhà và trường đều ở góc phố. Giáo sư có bản đồ thị trấn. Diễn đạt bài toán "cả hai con có thể đi tới cùng một trường không" thành bài toán luồng cực đại. *Người tổng hợp:* đỉnh là góc phố, mỗi đoạn phố (vô hướng) thành hai cạnh ngược chiều sức chứa 1 (tách một cạnh bằng đỉnh phụ để khử cạnh ngược chiều); nguồn là nhà, đích là trường. Có hai đường rời cạnh khi và chỉ khi luồng cực đại ≥ 2 (theo định lý tính nguyên, luồng nguyên phân rã thành hai đường dùng mỗi đoạn phố một lần; nếu cả hai chiều của một đoạn đều mang luồng thì triệt tiêu).
- **26.1-7:** Ngoài sức chứa cạnh, mạng có **sức chứa đỉnh**: mỗi đỉnh v có giới hạn l(v) lượng luồng đi qua. Chỉ cách biến G = (V, E) có sức chứa đỉnh thành mạng tương đương G′ = (V′, E′) không có sức chứa đỉnh, cùng giá trị luồng cực đại. G′ có bao nhiêu đỉnh và cạnh? *Người tổng hợp:* tách mỗi đỉnh v thành v_in và v_out nối bởi cạnh (v_in, v_out) sức chứa l(v); mỗi cạnh (u, v) thành (u_out, v_in). |V′| = 2|V|, |E′| = |E| + |V|.

### Bài tập Mục 26.2 (trang 730–731)

- **26.2-1:** Chứng minh các tổng trong (26.6) bằng các tổng trong (26.7). *Người tổng hợp:* các số hạng thêm vào có dạng f(s, v) với v ∉ V₁ (không có cạnh (s, v) nên f(s, v) = 0) hoặc f(v, s) với v ∉ V₂; còn với f′ thì f′(s, v) > 0 chỉ khi (s, v) ∈ E_f, tức (s, v) ∈ E hoặc (v, s) ∈ E, nghĩa là v ∈ V₁ ∪ V₂.
- **26.2-2:** Trong luồng của mạng Lucky Puck (giá trị 19), luồng qua lát cắt ({s, v₂, v₄}, {v₁, v₃, t}) bằng bao nhiêu? Sức chứa lát cắt? *Lời giải của người tổng hợp:* cạnh từ S sang T: s → v₁ (11), v₂ → v₁ (1), v₄ → v₃ (7), v₄ → t (4), tổng 23; cạnh từ T sang S: v₃ → v₂ (4). Luồng ròng 23 − 4 = 19 (đúng như Bổ đề 26.4). Sức chứa: 16 + 4 + 7 + 4 = 31.
- **26.2-3:** Chạy Edmonds-Karp trên mạng Lucky Puck. *Lời giải* ở phần Nội dung chi tiết, Mục 3: ba đường s → v₁ → v₃ → t (12), s → v₂ → v₄ → t (4), s → v₂ → v₄ → v₃ → t (7); luồng cực đại 23.
- **26.2-4:** Trong ví dụ chạy FORD-FULKERSON trên mạng Lucky Puck, lát cắt cực tiểu ứng với luồng cực đại là gì? Đường tăng luồng nào triệt tiêu luồng? *Người tổng hợp:* S = {s, v₁, v₂, v₄}, T = {v₃, t}, sức chứa 12 + 7 + 4 = 23. Đường ở vòng (c), s → v₁ → v₂ → v₃ → t, triệt tiêu luồng trên v₂ → v₁ và v₃ → v₂.
- **26.2-5:** Phép dựng siêu nguồn/siêu đích thêm các cạnh sức chứa vô hạn. Chứng minh mọi luồng trong mạng thu được có giá trị hữu hạn nếu các cạnh của mạng gốc có sức chứa hữu hạn. *Người tổng hợp:* xét lát cắt S = {s, s₁, …, s_m}, T = phần còn lại. Mọi cạnh vô hạn (s, sᵢ) nằm trọn trong S, mọi cạnh vô hạn (tⱼ, t) nằm trọn trong T, nên các cạnh đi từ S sang T đều là cạnh của mạng gốc, sức chứa hữu hạn. Theo Hệ quả 26.5, mọi luồng có giá trị không vượt sức chứa hữu hạn của lát cắt này.
- **26.2-6:** Mỗi nguồn sᵢ sản xuất đúng pᵢ đơn vị (Σ_v f(sᵢ, v) = pᵢ), mỗi đích tⱼ tiêu thụ đúng qⱼ (Σ_v f(v, tⱼ) = qⱼ), với Σᵢ pᵢ = Σⱼ qⱼ. Chuyển bài toán tìm luồng thoả các ràng buộc này về bài toán luồng cực đại một nguồn một đích. *Người tổng hợp:* cạnh (s, sᵢ) sức chứa pᵢ, (tⱼ, t) sức chứa qⱼ; có luồng thoả ràng buộc khi và chỉ khi luồng cực đại bằng Σ pᵢ.
- **26.2-7:** Chứng minh Bổ đề 26.2. *Người tổng hợp:* f_p ≤ c_f(p) ≤ c_f(u, v) trên mỗi cạnh của p; mỗi đỉnh trong của đường đơn có đúng một cạnh vào và một cạnh ra trên p nên bảo toàn; giá trị: đường đơn rời s đúng một lần và không quay lại s, nên |f_p| = c_f(p).
- **26.2-8:** Định nghĩa lại mạng thặng dư để cấm cạnh đi vào s. Lập luận FORD-FULKERSON vẫn tính đúng luồng cực đại. *Người tổng hợp:* đường tăng luồng là đường đơn từ s nên không bao giờ dùng cạnh vào s; định lý luồng cực đại – lát cắt cực tiểu: tập S các đỉnh đến được từ s không đổi khi bỏ cạnh vào s.
- **26.2-9:** Cho f và f′ đều là luồng trong G, tính f ↑ f′. Luồng tăng có bảo toàn không? Có thoả ràng buộc sức chứa không? *Người tổng hợp:* bảo toàn: có (tổng tuyến tính các đẳng thức bảo toàn). Sức chứa: không nhất thiết — ví dụ f = f′ = luồng bão hoà một cạnh thì f + f′ = 2c > c (và với cạnh ngược, có thể âm).
- **26.2-10:** Chỉ cách tìm luồng cực đại bằng một dãy nhiều nhất |E| đường tăng luồng (gợi ý: xác định các đường **sau khi** tìm được luồng cực đại). *Người tổng hợp:* lấy luồng cực đại f*, xét đồ thị con các cạnh có f* > 0; lặp: tìm một đường s–t trong đó (bỏ chu trình nếu gặp), tăng theo min luồng trên đường; mỗi lần ít nhất một cạnh về 0 và bị loại, nên ≤ |E| đường. Chạy Ford-Fulkerson với đúng các đường này từ luồng 0.
- **26.2-11:** **Độ liên thông cạnh** (edge connectivity) của đồ thị vô hướng là số cạnh k nhỏ nhất phải xoá để làm đồ thị mất liên thông (cây có độ liên thông cạnh 1, chu trình có 2). Chỉ cách tính độ liên thông cạnh của G = (V, E) bằng cách chạy thuật toán luồng cực đại trên nhiều nhất |V| mạng, mỗi mạng O(V) đỉnh và O(E) cạnh. *Người tổng hợp:* cố định một đỉnh u; với mỗi v ≠ u, chạy luồng cực đại từ u tới v trên mạng thay mỗi cạnh vô hướng bằng hai cạnh có hướng sức chứa 1; kết quả là min trên các v. Đúng vì lát cắt cạnh nhỏ nhất tách u khỏi một đỉnh v nào đó.
- **26.2-12:** G có cạnh đi vào nguồn s. Cho f là luồng trong G mà một cạnh (v, s) có f(v, s) = 1. Chứng minh tồn tại luồng f′ với f′(v, s) = 0 và |f| = |f′|. Cho thuật toán O(E) tính f′ biết f, sức chứa nguyên. *Hướng của người tổng hợp:* trong đồ thị con các cạnh mang luồng dương, tìm (bằng DFS, O(E)) một đường đi từ s tới v; ghép với cạnh (v, s) được một chu trình mang luồng dương. Giảm 1 đơn vị luồng trên mọi cạnh của chu trình: bảo toàn luồng giữ nguyên tại mọi đỉnh, còn tại s cả luồng ra lẫn luồng vào cùng giảm 1, nên |f′| = |f| và f′(v, s) = 0. (Sự tồn tại đường s ⇝ v dùng phân rã luồng thành đường và chu trình; người tổng hợp không viết chứng minh đầy đủ.)
- **26.2-13:** Trong mọi lát cắt cực tiểu của mạng G sức chứa nguyên, muốn tìm lát cắt có ít cạnh nhất. Chỉ cách sửa sức chứa để tạo G′ mà mọi lát cắt cực tiểu của G′ là lát cắt cực tiểu có ít cạnh nhất trong G. *Người tổng hợp:* đặt c′(u, v) = c(u, v) · (|E| + 1) + 1. Sức chứa lát cắt trong G′ bằng (|E| + 1) · c(S, T) + (số cạnh của lát cắt); vì số cạnh ≤ |E| < |E| + 1, lát cắt cực tiểu của G′ trước hết cực tiểu c, sau đó cực tiểu số cạnh.

### Bài tập Mục 26.3 (trang 735–736)

- **26.3-1:** Chạy Ford-Fulkerson trên mạng của đồ thị hai phía ví dụ (L đánh số 1–5, R đánh số 6–9 từ trên xuống), mỗi vòng chọn đường tăng luồng nhỏ nhất theo thứ tự từ điển, vẽ mạng thặng dư sau mỗi lần tăng. *Lời giải của người tổng hợp:* vòng 1: s → 1 → 6 → t; vòng 2: s → 2 → 6 bị chặn (6 → t đã bão hoà; từ 6 chỉ có cạnh ngược 6 → 1, đi tiếp không được), nên đường nhỏ nhất là s → 2 → 8 → t; vòng 3: s → 3 → 7 → t; vòng 4: từ 4 hay 5 chỉ tới 8, rồi theo cạnh ngược 8 → 2 → 6 → 1, ngõ cụt — không còn đường. Cặp ghép cực đại {1–6, 2–8, 3–7}, cỡ 3. Sau mỗi vòng, mạng thặng dư đảo chiều ba cạnh của đường vừa dùng (ví dụ sau vòng 1: có 1 → s, 6 → 1, t → 6 thay cho s → 1, 1 → 6, 6 → t).
- **26.3-2:** Chứng minh Định lý 26.10 (tính nguyên). *Người tổng hợp:* quy nạp như đã nêu ở Nội dung chi tiết: luồng 0 nguyên; nếu f nguyên thì mọi c_f nguyên, c_f(p) nguyên, f ↑ f_p nguyên.
- **26.3-3:** Cho G hai phía, G′ là mạng tương ứng. Cho cận trên tốt cho độ dài mọi đường tăng luồng FORD-FULKERSON tìm được trong G′. *Người tổng hợp:* đường đơn xen kẽ L → R (cạnh thuận) và R → L (cạnh ngược), dùng mỗi đỉnh một lần; độ dài nhiều nhất 2 min(|L|, |R|) + 1.
- **26.3-4 ★:** **Cặp ghép hoàn hảo** (perfect matching) là cặp ghép mà mọi đỉnh đều được ghép. Cho G hai phía với |L| = |R|. Với X ⊆ V, định nghĩa **lân cận** N(X) = {y ∈ V : (x, y) ∈ E với x ∈ X nào đó}. Chứng minh **định lý Hall**: G có cặp ghép hoàn hảo khi và chỉ khi |A| ≤ |N(A)| với mọi A ⊆ L. *Người tổng hợp:* chiều thuận hiển nhiên (mỗi đỉnh của A ghép với một đỉnh riêng trong N(A)). Chiều ngược: trong G′ đặt sức chứa các cạnh L → R là ∞ (luồng nguyên vẫn tương ứng cặp ghép vì mỗi u ∈ L chỉ nhận tối đa 1 đơn vị từ s). Xét lát cắt cực tiểu (S, T), sức chứa hữu hạn vì lát cắt ({s}, V′ − {s}) có sức chứa |L|. Đặt A = L ∩ S. Không cạnh ∞ nào đi từ S sang T, nên N(A) ⊆ S. Các cạnh bị cắt gồm (s, u) với u ∈ L − A và (v, t) với v ∈ R ∩ S ⊇ N(A), nên c(S, T) ≥ |L − A| + |N(A)| ≥ |L| − |A| + |A| = |L|. Vậy luồng cực đại bằng |L| = |R|, ứng với cặp ghép hoàn hảo.
- **26.3-5 ★:** Đồ thị hai phía G = (V, E), V = L ∪ R, là **d-chính quy** (d-regular) nếu mọi đỉnh có bậc đúng d. Mọi đồ thị hai phía d-chính quy có |L| = |R|. Chứng minh mọi đồ thị hai phía d-chính quy có cặp ghép cỡ |L|, bằng cách lập luận lát cắt cực tiểu của mạng tương ứng có sức chứa |L|. *Người tổng hợp:* luồng phân số f(s, u) = 1, f(u, v) = 1/d trên mọi cạnh, f(v, t) = 1 là hợp lệ với giá trị |L| (mỗi đỉnh có d cạnh); luồng cực đại ≥ |L| và lát cắt ({s}, …) có sức chứa |L|, nên luồng cực đại = |L|; theo định lý tính nguyên có luồng nguyên giá trị |L|, tức cặp ghép cỡ |L|.

### Bài tập Mục 26.4 (trang 747–748)

- **26.4-1:** Chứng minh sau INITIALIZE-PREFLOW(G, s), s.e ≤ −|f*| với f* là luồng cực đại. *Người tổng hợp:* s.e = −c({s}, V − {s}) và theo Hệ quả 26.5, |f*| ≤ c({s}, V − {s}).
- **26.4-2:** Chỉ cách cài đặt thuật toán tổng quát với O(V) mỗi lần nâng nhãn, O(1) mỗi lần đẩy và O(1) để chọn thao tác áp dụng được, tổng O(V²E). *Người tổng hợp:* giữ danh sách các đỉnh tràn; với mỗi đỉnh, duyệt danh sách đỉnh kề bằng con trỏ current như DISCHARGE; nâng nhãn duyệt các đỉnh kề — O(degree) ≤ O(V); đẩy O(1).
- **26.4-3:** Chứng minh thuật toán tổng quát chỉ tốn tổng O(VE) thời gian cho toàn bộ O(V²) lần nâng nhãn. *Người tổng hợp:* nâng nhãn u tốn O(degree(u)); mỗi đỉnh bị nâng nhãn O(V) lần; tổng Σ_u O(V · degree(u)) = O(VE).
- **26.4-4:** Đã có luồng cực đại tìm bằng thuật toán đẩy–nâng nhãn. Cho thuật toán nhanh tìm lát cắt cực tiểu. *Người tổng hợp:* BFS trong mạng thặng dư từ s, S là tập đỉnh đến được — O(E). Cách khác: các đỉnh có độ cao ≥ |V| nằm phía nguồn (xem 26.5-5).
- **26.4-5:** Cho thuật toán đẩy–nâng nhãn hiệu quả tìm cặp ghép cực đại trong đồ thị hai phía, phân tích. *Người tổng hợp:* chạy trên G′; độ cao bị chặn O(V), sức chứa 1 nên mỗi lần đẩy đều bão hoà (luồng dư nguyên, sức chứa 1); số thao tác O(VE) → O(VE) thời gian với cài đặt hợp lý.
- **26.4-6:** Mọi sức chứa thuộc {1, 2, …, k}. Phân tích thời gian thuật toán tổng quát theo |V|, |E|, k (gợi ý: mỗi cạnh chịu được bao nhiêu lần đẩy không bão hoà trước khi bão hoà?). *Người tổng hợp:* với luồng nguyên, mỗi lần đẩy ít nhất 1 đơn vị; giữa hai lần bão hoà một cạnh nhận ≤ k lần đẩy; số lần đẩy bão hoà O(VE) nên tổng số lần đẩy O(kVE), cộng nâng nhãn O(V²): O(kVE).
- **26.4-7:** Chứng minh có thể đổi dòng 6 của INITIALIZE-PREFLOW thành s.h = |G.V| − 2 mà không ảnh hưởng tính đúng hay hiệu năng tiệm cận. *Người tổng hợp:* chỉ cần Bổ đề 26.17 (không có đường s ⇝ t trong G_f) còn đúng. Sau khởi tạo mọi cạnh rời s bão hoà. Một cạnh thặng dư (s, v) chỉ có thể xuất hiện khi đã có luồng được đẩy từ v về s, lúc đó v.h = s.h + 1 = |V| − 1, và độ cao không bao giờ giảm. Giả sử có đường đơn s → v ⇝ t trong G_f; đoạn v ⇝ t không qua s nên có nhiều nhất |V| − 2 cạnh, cộng điều kiện hàm độ cao dọc đoạn này được v.h ≤ |V| − 2, mâu thuẫn với v.h ≥ |V| − 1. Các cận độ cao (≤ 2|V| − 3) và do đó mọi cận tiệm cận giữ nguyên.
- **26.4-8:** Gọi δ_f(u, v) là khoảng cách (số cạnh) từ u tới v trong G_f. Chứng minh GENERIC-PUSH-RELABEL duy trì: u.h < |V| kéo theo u.h ≤ δ_f(u, t), và u.h ≥ |V| kéo theo u.h − |V| ≤ δ_f(u, s). *Người tổng hợp:* cộng điều kiện h(x) ≤ h(y) + 1 dọc một đường ngắn nhất từ u tới t (h(t) = 0) hoặc tới s (h(s) = |V|).
- **26.4-9 ★:** Sửa thuật toán tổng quát để duy trì đẳng thức u.h = δ_f(u, t) khi u.h < |V| và u.h − |V| = δ_f(u, s) khi u.h ≥ |V|; tổng thời gian dành cho việc duy trì phải là O(VE). *Người tổng hợp:* đây là "nâng nhãn chính xác": khi nâng nhãn, cập nhật bằng BFS ngược từ t (và từ s) một cách gia tăng; mỗi đỉnh có độ cao chỉ tăng, tổng O(V) lần tăng mỗi đỉnh, mỗi lần quét O(degree), tổng cộng O(VE).
- **26.4-10:** Chứng minh số lần đẩy không bão hoà của GENERIC-PUSH-RELABEL nhiều nhất 4|V|²|E| khi |V| ≥ 4. *Hướng của người tổng hợp:* đếm chặt hơn trong chứng minh Bổ đề 26.23. Tổng lượng tăng của Φ do mọi lần nâng nhãn chỉ là tổng độ tăng độ cao, nhiều nhất (2|V| − 1)(|V| − 2) (không phải 2|V| · 2|V|²); do đẩy bão hoà nhiều nhất (2|V| − 1) nhân số lần đẩy bão hoà (< 2|V||E|). Cộng lại và dùng |E| ≥ |V| − 1, |V| ≥ 4 để chặn tổng bởi 4|V|²|E|.

### Bài tập Mục 26.5 (trang 759–760)

- **26.5-1:** Minh hoạ RELABEL-TO-FRONT theo kiểu ví dụ chạy tay RELABEL-TO-FRONT ở Nội dung chi tiết, Mục 6, trên mạng Lucky Puck, với thứ tự ban đầu L = ⟨v₁, v₂, v₃, v₄⟩ và danh sách đỉnh kề v₁.N = ⟨s, v₂, v₃⟩, v₂.N = ⟨s, v₁, v₃, v₄⟩, v₃.N = ⟨v₁, v₂, v₄, t⟩, v₄.N = ⟨v₂, v₃, t⟩. *Lời giải tóm tắt của người tổng hợp* (|V| = 6 nên s.h = 6; khởi tạo e(v₁) = 16, e(v₂) = 13):

  | Lần xả | Diễn biến chính | L sau |
  |---|---|---|
  | v₁ | nâng lên 1; đẩy 12 sang v₃ (bão hoà); nâng lên 7; đẩy 4 về s | ⟨v₁, v₂, v₃, v₄⟩ |
  | v₂ | nâng lên 1; đẩy 13 sang v₄ | ⟨v₂, v₁, v₃, v₄⟩ |
  | v₁ | không có luồng dư | — |
  | v₃ | nâng lên 1; đẩy 12 sang t | ⟨v₃, v₂, v₁, v₄⟩ |
  | v₂, v₁ | không có luồng dư | — |
  | v₄ | nâng lên 1; đẩy 4 sang t (bão hoà); nâng lên 2; đẩy 9 về v₂ | ⟨v₄, v₃, v₂, v₁⟩ |
  | v₃ | không có luồng dư | — |
  | v₂ | nâng lên 3; đẩy 9 sang v₄ | ⟨v₂, v₄, v₃, v₁⟩ |
  | v₄ | đẩy 7 sang v₃ (bão hoà v₄ → v₃); nâng lên 4; đẩy 2 về v₂ | ⟨v₄, v₂, v₃, v₁⟩ |
  | v₂ | nâng lên 5; đẩy 2 sang v₄ | ⟨v₂, v₄, v₃, v₁⟩ |
  | v₄ | nâng lên 6; đẩy 2 về v₂ | ⟨v₄, v₂, v₃, v₁⟩ |
  | v₂ | nâng lên 7; đẩy 2 về s | ⟨v₂, v₄, v₃, v₁⟩ |
  | v₄ | không có luồng dư | — |
  | v₃ | đẩy 7 sang t (không nâng nhãn) | — |
  | v₁ | không có luồng dư; hết danh sách | dừng |

  Luồng cuối: s → v₁ 12, s → v₂ 11, v₁ → v₃ 12, v₂ → v₁ 0, v₃ → v₂ 0, v₂ → v₄ 11, v₄ → v₃ 7, v₃ → t 19, v₄ → t 4; giá trị 23, trùng với kết quả Ford-Fulkerson. (Người tổng hợp đã kiểm tra bảo toàn luồng tại cả bốn đỉnh trung gian.)
- **26.5-2 ★:** Cài đặt thuật toán đẩy–nâng nhãn giữ một **hàng đợi FIFO** các đỉnh tràn: lặp lại việc xả đỉnh ở đầu hàng đợi, đỉnh nào trước đó không tràn mà sau đó tràn thì đưa vào cuối hàng; xả xong thì bỏ đỉnh đầu; dừng khi hàng đợi rỗng. Chỉ cách cài đặt để tính luồng cực đại trong O(V³). *Người tổng hợp:* chia thời gian thành các "lượt" (mỗi lượt xả mọi đỉnh có trong hàng đợi lúc đầu lượt); dùng hàm thế Φ = max độ cao các đỉnh tràn để chứng minh số lượt O(V²); mỗi lượt có nhiều nhất |V| lần đẩy không bão hoà, nên tổng O(V³).
- **26.5-3:** Chứng minh thuật toán tổng quát vẫn đúng nếu RELABEL chỉ đặt u.h = u.h + 1. Thay đổi này ảnh hưởng phân tích RELABEL-TO-FRONT thế nào? *Người tổng hợp:* khi RELABEL áp dụng được, u.h ≤ v.h với mọi cạnh thặng dư (u, v), nên sau khi tăng 1 vẫn có u.h ≤ v.h + 1; h vẫn là hàm độ cao, mọi bổ đề về độ cao (26.15–26.20) và các cận số thao tác giữ nguyên, nên thuật toán tổng quát vẫn đúng và vẫn O(V²E). Với RELABEL-TO-FRONT: phần đầu Bổ đề 26.28 hỏng (sau một lần +1 có thể chưa có cạnh chấp nhận được rời u), nên DISCHARGE có thể nâng nhãn rồi duyệt hết danh sách nhiều lần liên tiếp; phần sau (không có cạnh chấp nhận được đi vào u) vẫn đúng nên bất biến sắp xếp topo vẫn giữ. Mỗi lượt duyệt tốn O(degree(u)) và mỗi đỉnh vẫn chỉ được nâng nhãn O(V) lần, nên chi phí dịch con trỏ vẫn O(VE) và cận O(V³) giữ nguyên.
- **26.5-4 ★:** Chứng minh nếu luôn xả đỉnh tràn **cao nhất** thì phương pháp đẩy–nâng nhãn chạy O(V³). *Người tổng hợp:* giữa hai lần nâng nhãn, độ cao lớn nhất của đỉnh tràn chỉ giảm, mỗi đỉnh bị xả nhiều nhất một lần (mỗi lần xả không nâng nhãn dùng một lần đẩy không bão hoà); số pha O(V²), mỗi pha ≤ |V| lần đẩy không bão hoà.
- **26.5-5:** Giả sử tại một thời điểm có số nguyên 0 < k ≤ |V| − 1 mà không đỉnh nào có v.h = k. Chứng minh mọi đỉnh có v.h > k nằm ở phía nguồn của một lát cắt cực tiểu. Nếu có k như vậy, **heuristic khe hở** (gap heuristic) cập nhật mọi đỉnh v ∈ V − {s} có v.h > k thành v.h = max(v.h, |V| + 1). Chứng minh h thu được vẫn là hàm độ cao. (Sách nhấn mạnh heuristic khe hở rất quan trọng để cài đặt đẩy–nâng nhãn chạy tốt trong thực tế.) *Người tổng hợp:* không có cạnh thặng dư từ một đỉnh cao > k xuống đỉnh cao < k (chênh > 1) và không có đỉnh nào cao đúng k, nên các đỉnh cao > k không đến được t trong G_f; chúng không bao giờ đẩy được luồng tới t nữa. Nâng chúng lên ≥ |V| + 1 không vi phạm h(u) ≤ h(v) + 1 vì không có cạnh thặng dư từ chúng sang đỉnh thấp ≤ k.

### Problem 26-1: Bài toán thoát hiểm (Escape problem)

**Lưới** n × n là đồ thị vô hướng gồm n hàng và n cột đỉnh. Đỉnh ở hàng i cột j ký hiệu (i, j). Mọi đỉnh có đúng bốn láng giềng, trừ các đỉnh biên, là các điểm (i, j) với i = 1, i = n, j = 1 hoặc j = n. Cho m ≤ n² điểm xuất phát (x₁, y₁), …, (x_m, y_m) trong lưới, **bài toán thoát hiểm** là xác định có hay không m đường đi **rời nhau về đỉnh** từ các điểm xuất phát tới m điểm biên khác nhau bất kỳ.

Ví dụ của sách (vẽ lại Hình 26.11, lưới 6 × 6, tọa độ (hàng, cột) đếm từ trên trái):

```text
(a) Có lối thoát — 10 điểm xuất phát:         (b) Không có lối thoát — 11 điểm:
    hàng 2: (2,2) (2,4) (2,6)                     hàng 2: (2,2) (2,4) (2,6)
    hàng 3: (3,1) (3,2) (3,4) (3,6)               hàng 3: (3,1) (3,2) (3,4) (3,5) (3,6)
    hàng 4: (4,2) (4,4) (4,6)                     hàng 4: (4,2) (4,4) (4,6)
  Các đường thoát (sách tô đậm):
    (2,2)→(1,2)       (3,2)→(3,3)→(2,3)→(1,3)
    (2,4)→(1,4)       (3,4)→(3,5)→(2,5)→(1,5)
    (4,2)→(4,3)→(5,3)→(6,3)   (4,4)→(5,4)→(6,4)
    (3,1), (2,6), (3,6), (4,6) đã nằm trên biên (đường độ dài 0)
```

- **(a)** Xét mạng luồng mà cả đỉnh lẫn cạnh có sức chứa (tổng luồng dương vào một đỉnh bị chặn). Chứng minh luồng cực đại trong mạng có sức chứa cạnh và đỉnh quy được về bài toán luồng cực đại thường trên mạng cỡ tương đương. *Người tổng hợp:* tách đỉnh như Exercise 26.1-7.
- **(b)** Mô tả thuật toán hiệu quả giải bài toán thoát hiểm và phân tích. *Người tổng hợp:* mỗi đỉnh lưới sức chứa 1 (tách thành v_in → v_out), mỗi cạnh lưới thành hai cạnh có hướng sức chứa 1; siêu nguồn nối tới mọi điểm xuất phát (sức chứa 1), mọi đỉnh biên nối tới siêu đích (sức chứa 1). Có lối thoát khi và chỉ khi luồng cực đại = m. Mạng có O(n²) đỉnh, O(n²) cạnh, luồng ≤ m ≤ n²; Ford-Fulkerson O(E|f*|) = O(n² · m) = O(n⁴). (Nếu m > 4n − 4, số đỉnh biên, thì chắc chắn không có lối thoát.) Ở lưới (b), lý do không thoát (kiểm tra của người tổng hợp): điểm (3,2) có ba láng giềng (2,2), (4,2), (3,1) đều là điểm xuất phát khác, nên đường của nó buộc phải đi qua (3,3); điểm (3,4) có ba láng giềng (2,4), (4,4), (3,5) đều là điểm xuất phát, nên cũng buộc phải đi qua (3,3). Hai đường không thể rời nhau về đỉnh, nên luồng cực đại chỉ đạt 10 < 11. Ở lưới (a), (3,5) là ô trắng nên (3,4) thoát được qua (3,5).

### Problem 26-2: Phủ đường tối thiểu (Minimum path cover)

**Phủ đường** (path cover) của đồ thị có hướng G = (V, E) là tập P các đường đi rời nhau về đỉnh sao cho mọi đỉnh của V thuộc đúng một đường trong P. Đường có thể bắt đầu, kết thúc ở bất kỳ đâu và dài bao nhiêu cũng được, kể cả độ dài 0. **Phủ đường tối thiểu** là phủ đường có ít đường nhất.

- **(a)** Cho thuật toán hiệu quả tìm phủ đường tối thiểu của đồ thị có hướng không chu trình G = (V, E). (Gợi ý: với V = {1, 2, …, n}, dựng G′ = (V′, E′) với V′ = {x₀, x₁, …, x_n} ∪ {y₀, y₁, …, y_n}, E′ = {(x₀, xᵢ) : i ∈ V} ∪ {(yᵢ, y₀) : i ∈ V} ∪ {(xᵢ, yⱼ) : (i, j) ∈ E}, và chạy thuật toán luồng cực đại.) *Người tổng hợp:* mọi cạnh sức chứa 1, nguồn x₀, đích y₀. Luồng nguyên tương ứng với cặp ghép M giữa "đầu ra" xᵢ và "đầu vào" yⱼ; mỗi cạnh ghép (i, j) nối hai đoạn đường lại, giảm số đường đi 1. Số đường tối thiểu = n − |f*|. Thời gian O(VE).
- **(b)** Thuật toán có đúng với đồ thị có chu trình không? Giải thích. *Người tổng hợp:* không — cặp ghép có thể chọn các cạnh tạo thành chu trình (mỗi đỉnh một cạnh vào một cạnh ra quanh vòng), mà chu trình không phải là đường đi; khi đó n − |f*| có thể nhỏ hơn số đường thực sự cần.

### Problem 26-3: Tư vấn thuật toán (Algorithmic consulting)

Giáo sư Gore muốn mở công ty tư vấn thuật toán. Ông xác định n lĩnh vực con quan trọng của thuật toán (tương ứng khoảng các phần của cuốn sách), tập A = {A₁, A₂, …, A_n}. Ở mỗi lĩnh vực A_k, có thể thuê một chuyên gia với giá c_k đô la. Công ty có danh sách J = {J₁, J₂, …, J_m} các dự án tiềm năng. Để làm dự án Jᵢ, công ty cần đã thuê chuyên gia ở một tập con Rᵢ ⊆ A các lĩnh vực. Mỗi chuyên gia có thể làm nhiều dự án cùng lúc. Nếu nhận dự án Jᵢ, công ty phải đã thuê chuyên gia ở mọi lĩnh vực trong Rᵢ, và thu về pᵢ đô la. Cần xác định thuê chuyên gia lĩnh vực nào và nhận dự án nào để **cực đại lợi nhuận ròng** (tổng thu từ các dự án nhận trừ tổng chi phí thuê chuyên gia).

Xét mạng luồng G: đỉnh nguồn s, các đỉnh A₁, …, A_n, các đỉnh J₁, …, J_m, đỉnh đích t. Với k = 1, …, n có cạnh (s, A_k) sức chứa c(s, A_k) = c_k; với i = 1, …, m có cạnh (Jᵢ, t) sức chứa c(Jᵢ, t) = pᵢ; với A_k ∈ Rᵢ có cạnh (A_k, Jᵢ) sức chứa ∞.

- **(a)** Chứng minh nếu Jᵢ ∈ T trong một lát cắt (S, T) sức chứa hữu hạn của G thì A_k ∈ T với mọi A_k ∈ Rᵢ. *Người tổng hợp:* lát cắt có sức chứa hữu hạn thì không cạnh vô hạn nào đi từ S sang T. Cạnh (A_k, Jᵢ) vô hạn nên không thể có A_k ∈ S cùng lúc Jᵢ ∈ T. Vậy Jᵢ ∈ T kéo theo A_k ∈ T với mọi A_k ∈ Rᵢ.
- **(b)** Chỉ cách xác định lợi nhuận ròng cực đại từ sức chứa lát cắt cực tiểu và các pᵢ. *Người tổng hợp:* đọc một lát cắt hữu hạn (S, T) như một phương án: thuê chuyên gia A_k ∈ T, nhận dự án Jᵢ ∈ T (theo (a), phương án này khả thi). Các cạnh bị cắt là (s, A_k) với A_k ∈ T và (Jᵢ, t) với Jᵢ ∈ S, nên c(S, T) = Σ_{A_k∈T} c_k + Σ_{Jᵢ∈S} pᵢ = chi phí thuê + doanh thu bỏ lỡ. Lợi nhuận của phương án = Σᵢ pᵢ − c(S, T). Vậy lợi nhuận ròng cực đại = Σᵢ pᵢ − (sức chứa lát cắt cực tiểu).
- **(c)** Cho thuật toán hiệu quả xác định nhận dự án nào và thuê chuyên gia nào; phân tích theo m, n và r = Σᵢ |Rᵢ|. *Người tổng hợp:* chạy luồng cực đại, lấy T = các đỉnh không đến được từ s trong mạng thặng dư; nhận các Jᵢ ∈ T, thuê các A_k ∈ T. Mạng có n + m + 2 đỉnh, n + m + r cạnh; Edmonds-Karp O(VE²) hoặc RELABEL-TO-FRONT O((n + m)³).

### Problem 26-4: Cập nhật luồng cực đại (Updating maximum flow)

Cho mạng G = (V, E) với nguồn s, đích t, sức chứa nguyên, và một luồng cực đại trong G.

- **(a)** Tăng sức chứa một cạnh (u, v) ∈ E thêm 1. Cho thuật toán O(V + E) cập nhật luồng cực đại. *Người tổng hợp:* luồng cực đại mới tăng nhiều nhất 1 (lát cắt cực tiểu tăng nhiều nhất 1). Tìm một đường tăng luồng trong mạng thặng dư mới (BFS O(V + E)); nếu có thì tăng 1.
- **(b)** Giảm sức chứa một cạnh (u, v) ∈ E đi 1. Cho thuật toán O(V + E). *Người tổng hợp:* nếu f(u, v) ≤ c(u, v) − 1 thì không cần làm gì. Nếu f(u, v) = c(u, v): luồng quá 1 đơn vị trên (u, v). Tìm đường từ u về s và từ t về v trong đồ thị các cạnh mang luồng (đường s ⇝ u → v ⇝ t mang luồng), giảm 1 đơn vị luồng trên cả đường s ⇝ u → v ⇝ t; rồi thử một đường tăng luồng (BFS) để lấy lại 1 đơn vị nếu được.

### Problem 26-5: Luồng cực đại bằng phép co giãn (Maximum flow by scaling)

Cho G = (V, E) với nguồn s, đích t, sức chứa nguyên c(u, v) trên mỗi cạnh. Đặt C = max_{(u,v)∈E} c(u, v).

- **(a)** Lập luận lát cắt cực tiểu của G có sức chứa nhiều nhất C|E|. *Người tổng hợp:* mọi lát cắt có nhiều nhất |E| cạnh, mỗi cạnh ≤ C.
- **(b)** Cho số K, chỉ cách tìm đường tăng luồng có sức chứa ít nhất K trong O(E), nếu có. *Người tổng hợp:* BFS/DFS chỉ dùng cạnh thặng dư có c_f ≥ K.

Có thể dùng biến thể sau của FORD-FULKERSON-METHOD:

```text
MAX-FLOW-BY-SCALING(G, s, t)
1  C = max_{(u,v)∈E} c(u, v)
2  initialize flow f to 0
3  K = 2^⌊lg C⌋
4  while K ≥ 1
5      while there exists an augmenting path p of capacity at least K
6          augment flow f along p
7      K = K/2
8  return f
```

Dòng 3: K là luỹ thừa của 2 lớn nhất không vượt C. Vòng ngoài dòng 4–7 giảm K một nửa mỗi lần; vòng trong dòng 5–6 chỉ tăng luồng dọc các đường có sức chứa thặng dư ít nhất K.

- **(c)** Lập luận MAX-FLOW-BY-SCALING trả về luồng cực đại. *Người tổng hợp:* ở pha cuối K = 1, vòng trong dừng khi không còn đường tăng luồng nào (mọi đường có sức chứa ≥ 1 vì nguyên); theo Định lý 26.6, f cực đại.
- **(d)** Chứng minh sức chứa lát cắt cực tiểu của mạng thặng dư G_f nhiều nhất 2K|E| mỗi lần thực hiện dòng 4. *Người tổng hợp:* lần đầu: ≤ C|E| < 2K|E| vì K > C/2. Các lần sau: pha trước (với 2K) kết thúc khi không còn đường sức chứa ≥ 2K; lát cắt (S, T) với S = đỉnh đến được bằng cạnh có c_f ≥ 2K: mọi cạnh qua lát cắt có c_f < 2K, nên sức chứa thặng dư < 2K|E|.
- **(e)** Lập luận vòng trong dòng 5–6 chạy O(E) lần cho mỗi giá trị K. *Người tổng hợp:* luồng còn có thể thêm ≤ 2K|E|; mỗi lần tăng ít nhất K; nên ≤ 2|E| lần.
- **(f)** Kết luận MAX-FLOW-BY-SCALING cài đặt được trong O(E² lg C). *Người tổng hợp:* O(lg C) pha × O(E) lần tăng × O(E) mỗi lần tìm đường.

### Problem 26-6: Thuật toán cặp ghép hai phía Hopcroft-Karp (The Hopcroft-Karp bipartite matching algorithm)

Bài toán mô tả thuật toán nhanh hơn của Hopcroft và Karp tìm cặp ghép cực đại trên đồ thị hai phía, chạy O(√V E). Cho đồ thị hai phía vô hướng G = (V, E), V = L ∪ R, mọi cạnh có đúng một đầu trong L; M là một cặp ghép trong G. Một đường đi đơn P trong G là **đường tăng** (augmenting path) đối với M nếu nó bắt đầu ở một đỉnh chưa ghép trong L, kết thúc ở một đỉnh chưa ghép trong R, và các cạnh của nó luân phiên thuộc M và E − M. (Định nghĩa này liên quan nhưng khác đường tăng luồng trong mạng luồng.) Trong bài này đường đi được coi là dãy cạnh. **Đường tăng ngắn nhất** đối với M là đường tăng có ít cạnh nhất. Với hai tập A, B, **hiệu đối xứng** A ⊕ B = (A − B) ∪ (B − A), tức các phần tử thuộc đúng một trong hai tập.

- **(a)** Chứng minh nếu M là cặp ghép và P là đường tăng đối với M thì M ⊕ P là cặp ghép và |M ⊕ P| = |M| + 1. Chứng minh nếu P₁, …, P_k là các đường tăng rời nhau về đỉnh đối với M thì M ⊕ (P₁ ∪ … ∪ P_k) là cặp ghép cỡ |M| + k. *Người tổng hợp:* P có một cạnh ngoài M nhiều hơn số cạnh trong M (bắt đầu và kết thúc bằng cạnh ngoài M); đảo vai trò tăng 1; hai đầu chưa ghép nên không xung đột.

Cấu trúc chung của thuật toán:

```text
HOPCROFT-KARP(G)
1  M = ∅
2  repeat
3      let 𝒫 = {P₁, P₂, …, P_k} be a maximal set of vertex-disjoint
           shortest augmenting paths with respect to M
4      M = M ⊕ (P₁ ∪ P₂ ∪ … ∪ P_k)
5  until 𝒫 == ∅
6  return M
```

Dòng 3: lấy một tập **tối đại** (không thêm được nữa — không nhất thiết lớn nhất) các đường tăng ngắn nhất rời nhau về đỉnh. Dòng 4: tăng đồng thời theo tất cả. Phần còn lại yêu cầu phân tích số vòng lặp repeat và mô tả cài đặt dòng 3.

- **(b)** Cho hai cặp ghép M và M* trong G, chứng minh mọi đỉnh trong đồ thị G′ = (V, M ⊕ M*) có bậc nhiều nhất 2. Suy ra G′ là hợp rời của các đường đi đơn hoặc chu trình. Lập luận các cạnh trong mỗi đường hay chu trình luân phiên thuộc M hoặc M*. Chứng minh nếu |M| ≤ |M*| thì M ⊕ M* chứa ít nhất |M*| − |M| đường tăng rời nhau về đỉnh đối với M. *Người tổng hợp:* mỗi đỉnh có ≤ 1 cạnh của M và ≤ 1 cạnh của M*; chu trình và đường có số cạnh M bằng số cạnh M* hoặc chênh 1; số thành phần có nhiều cạnh M* hơn ≥ |M*| − |M|, mỗi thành phần đó là đường tăng đối với M.

Gọi l là độ dài đường tăng ngắn nhất đối với M, và P₁, …, P_k là tập tối đại các đường tăng độ dài l rời nhau về đỉnh. Đặt M′ = M ⊕ (P₁ ∪ … ∪ P_k), và P là một đường tăng ngắn nhất đối với M′.

- **(c)** Chứng minh nếu P rời về đỉnh với P₁, …, P_k thì P có nhiều hơn l cạnh. *Người tổng hợp:* P khi đó là đường tăng đối với M (các cạnh của nó không bị đảo); nếu có độ dài l thì mâu thuẫn tính tối đại; độ dài ≥ l, và nếu đúng l thì mâu thuẫn, nên > l.
- **(d)** Giả sử P không rời về đỉnh với P₁, …, P_k. Đặt A là tập cạnh (M ⊕ M′) ⊕ P. Chứng minh A = (P₁ ∪ … ∪ P_k) ⊕ P và |A| ≥ (k + 1)l. Kết luận P có nhiều hơn l cạnh. *Người tổng hợp:* M ⊕ M′ = P₁ ∪ … ∪ P_k; M ⊕ (M′ ⊕ P) là hiệu giữa M và một cặp ghép cỡ |M| + k + 1, theo (b) chứa ≥ k + 1 đường tăng rời nhau đối với M, mỗi đường ≥ l cạnh, nên |A| ≥ (k + 1)l. Mà |A| = kl + |P| − 2|P ∩ ∪Pᵢ|; P chung ít nhất một cạnh với một Pᵢ (chung đỉnh kéo theo chung cạnh của M′), nên |P| > l.
- **(e)** Chứng minh nếu đường tăng ngắn nhất đối với M có l cạnh thì cặp ghép cực đại có cỡ nhiều nhất |M| + |V|/(l + 1). *Người tổng hợp:* theo (b), M ⊕ M* có ≥ |M*| − |M| đường tăng rời nhau, mỗi đường ≥ l cạnh nên ≥ l + 1 đỉnh; tổng đỉnh ≤ |V|.
- **(f)** Chứng minh số vòng lặp repeat nhiều nhất 2√|V|. (Gợi ý: sau vòng lặp thứ √|V|, M còn tăng được bao nhiêu?) *Người tổng hợp:* sau √|V| vòng, l ≥ √|V| (l tăng mỗi vòng theo (c), (d)), nên theo (e) còn thiếu ≤ |V|/(√|V| + 1) < √|V|; mỗi vòng sau tăng ít nhất 1, nên cần thêm ít hơn √|V| vòng.
- **(g)** Cho thuật toán O(E) tìm tập tối đại các đường tăng ngắn nhất rời nhau về đỉnh P₁, …, P_k cho M. Kết luận tổng thời gian của HOPCROFT-KARP là O(√V E). *Người tổng hợp:* BFS từ mọi đỉnh L chưa ghép để phân tầng (đến tầng đầu tiên chứa đỉnh R chưa ghép), rồi DFS trong đồ thị phân tầng, xoá đỉnh đã dùng hoặc đã thấy ngõ cụt — mỗi cạnh xét O(1) lần, O(E). Nhân O(√V) vòng.

### Ghi chú chương (Chapter notes, trang 765–766)

- Tài liệu tham khảo tốt về luồng mạng và thuật toán liên quan: Ahuja, Magnanti và Orlin; Even; Lawler; Papadimitriou và Steiglitz; Tarjan. Goldberg, Tardos và Tarjan có một khảo sát hay về thuật toán cho bài toán luồng mạng; Schrijver viết một tổng quan thú vị về lịch sử lĩnh vực luồng mạng.
- Phương pháp Ford-Fulkerson là của **Ford và Fulkerson**, những người khởi xướng nghiên cứu hình thức nhiều bài toán trong lĩnh vực luồng mạng, gồm luồng cực đại và cặp ghép hai phía. Nhiều cài đặt sớm của phương pháp tìm đường tăng luồng bằng BFS; **Edmonds và Karp**, và độc lập là **Dinic**, chứng minh chiến lược này cho thuật toán thời gian đa thức. Ý tưởng liên quan, dùng **"luồng chặn"** (blocking flows), cũng do Dinic phát triển đầu tiên. **Karzanov** đầu tiên phát triển ý tưởng **tiền luồng**.
- Phương pháp đẩy–nâng nhãn là của **Goldberg**, và **Goldberg và Tarjan**. Goldberg và Tarjan cho một thuật toán O(V³) dùng hàng đợi để giữ tập đỉnh tràn, và một thuật toán dùng cây động (dynamic trees) đạt O(VE lg(V²/E + 2)). Nhiều nhà nghiên cứu khác phát triển thuật toán luồng cực đại đẩy–nâng nhãn. Ahuja và Orlin, và Ahuja, Orlin và Tarjan cho các thuật toán dùng co giãn (scaling). Cheriyan và Maheshwari đề xuất đẩy luồng từ đỉnh tràn có độ cao lớn nhất. Cheriyan và Hagerup đề xuất hoán vị ngẫu nhiên danh sách đỉnh kề, và một số nhà nghiên cứu phát triển các cách khử ngẫu nhiên khéo léo của ý này, dẫn tới một chuỗi thuật toán nhanh hơn. Thuật toán của **King, Rao và Tarjan** là nhanh nhất trong số đó, chạy O(VE log_{E/(V lg V)} V).
- Thuật toán nhanh nhất về tiệm cận cho tới khi sách viết, của **Goldberg và Rao**, chạy O(min(V^(2/3), E^(1/2)) E lg(V²/E + 2) lg C), với C = max_{(u,v)∈E} c(u, v). Thuật toán này không dùng đẩy–nâng nhãn mà dựa trên tìm luồng chặn. Mọi thuật toán luồng cực đại trước đó, kể cả các thuật toán trong chương, dùng một khái niệm khoảng cách nào đó (đẩy–nâng nhãn dùng khái niệm tương tự là độ cao), với độ dài 1 ngầm gán cho mỗi cạnh. Thuật toán mới tiếp cận khác: gán độ dài 0 cho cạnh sức chứa cao và độ dài 1 cho cạnh sức chứa thấp. Nói nôm na, với các độ dài này, đường ngắn nhất từ nguồn tới đích có xu hướng có sức chứa cao, nên cần ít vòng lặp hơn.
- Trong thực tế, thuật toán đẩy–nâng nhãn hiện thống trị các thuật toán dựa trên đường tăng luồng hay quy hoạch tuyến tính cho bài toán luồng cực đại. Nghiên cứu của **Cherkassky và Goldberg** nhấn mạnh tầm quan trọng của hai heuristic khi cài đặt đẩy–nâng nhãn: thứ nhất, định kỳ chạy BFS trên mạng thặng dư để có độ cao chính xác hơn; thứ hai, heuristic khe hở (Exercise 26.5-5). Họ kết luận biến thể đẩy–nâng nhãn tốt nhất là biến thể chọn xả đỉnh tràn có độ cao lớn nhất.
- Thuật toán tốt nhất cho tới khi sách viết cho cặp ghép hai phía cực đại, của **Hopcroft và Karp**, chạy O(√V E) và được mô tả ở Problem 26-6. Sách của **Lovász và Plummer** là tài liệu tham khảo xuất sắc về các bài toán cặp ghép.

## Luận điểm cốt lõi

### Mệnh đề

Giá trị luồng cực đại từ s tới t bằng sức chứa của lát cắt cực tiểu, và một luồng là cực đại khi và chỉ khi mạng thặng dư của nó không còn đường đi từ s tới t. Từ tiêu chuẩn này có hai cách tìm luồng cực đại trong thời gian đa thức: giữ luồng hợp lệ và tăng dần dọc các đường ngắn nhất (Edmonds-Karp, O(VE²)), hoặc giữ tính chất "không có đường s ⇝ t" nhờ hàm độ cao và dần biến tiền luồng thành luồng hợp lệ (đẩy–nâng nhãn, O(V²E); relabel-to-front, O(V³)). Nhiều bài toán tổ hợp, như cặp ghép cực đại trên đồ thị hai phía, quy được về luồng cực đại nhờ tính nguyên.

### Giả định

- Mạng có hướng, sức chứa không âm, không có cạnh ngược chiều, không có khuyên; mọi đỉnh nằm trên một đường s ⇝ v ⇝ t (nên |E| ≥ |V| − 1). Mạng thực tế vi phạm thì biến đổi trước (tách cạnh, siêu nguồn/siêu đích, tách đỉnh).
- Phân tích O(E|f*|) giả định sức chứa nguyên (hoặc hữu tỷ, nhân lên thành nguyên); sức chứa vô tỷ thì Ford-Fulkerson có thể không dừng.
- Có thể tính c_f(u, v) trong O(1) nhờ giữ cả cạnh gốc lẫn cạnh ngược trong cùng cấu trúc dữ liệu G′ = (V, E ∪ Eᵀ).
- Với đẩy–nâng nhãn: độ cao là số nguyên không âm; mạng thặng dư được phép có cạnh đi vào nguồn.
- Với cặp ghép: đồ thị hai phía, mọi đỉnh có ít nhất một cạnh (nên |E′| = Θ(E)).

### Cơ chế

1. **Mạng thặng dư** biểu diễn mọi cách thay đổi luồng hợp lệ: cạnh thuận còn thêm được c − f, cạnh ngược trả lại được f. Đẩy luồng trên cạnh ngược là triệt tiêu, cho phép thuật toán "sửa sai" lựa chọn trước.
2. **Đường tăng luồng**: một đường s ⇝ t trong G_f, tăng thêm c_f(p) > 0 làm giá trị luồng tăng đúng c_f(p).
3. **Lát cắt** là cận trên: luồng ròng qua mọi lát cắt bằng |f|, không vượt sức chứa lát cắt. Khi hết đường tăng luồng, các đỉnh đến được từ s tạo một lát cắt bị "lấp kín", chứng minh tối ưu.
4. **Chọn đường ngắn nhất** làm khoảng cách từ s không giảm, nên mỗi cạnh chỉ tới hạn O(V) lần.
5. **Đẩy–nâng nhãn** thay quan điểm toàn cục bằng cục bộ: tiền luồng, độ cao, đẩy xuống dốc đúng một bậc, nâng nhãn khi kẹt. Hàm độ cao chặn đường s ⇝ t ngay từ đầu; độ cao bị chặn bởi 2|V| − 1 nhờ đường thặng dư từ đỉnh tràn về nguồn; hàm thế chặn số lần đẩy không bão hoà.
6. **Relabel-to-front**: mạng chấp nhận được là dag; giữ danh sách theo thứ tự topo, chuyển đỉnh vừa nâng nhãn lên đầu; mỗi pha giữa hai lần nâng nhãn chỉ xả ≤ |V| đỉnh, mỗi lần xả nhiều nhất một lần đẩy không bão hoà.

### Bằng chứng và ví dụ tác giả đưa ra

- Mạng Lucky Puck (Vancouver → Winnipeg): một luồng giá trị 19, mạng thặng dư của nó, đường tăng luồng sức chứa 4, luồng 23.
- Lát cắt ({s, v₁, v₂}, {v₃, v₄, t}): luồng ròng 19, sức chứa 26 — minh hoạ sự bất đối xứng của hai định nghĩa.
- Năm vòng FORD-FULKERSON trên mạng Lucky Puck (4, 8, 12, 19, 23), trong đó vòng thứ ba triệt tiêu luồng.
- Mạng 4 đỉnh sức chứa 1.000.000 và cạnh giữa sức chứa 1: 2.000.000 lần tăng nếu chọn đường xen kẽ qua cạnh giữa.
- Ví dụ đồ thị hai phía 5 + 4 đỉnh: cặp ghép cỡ 2, cặp ghép cực đại cỡ 3, mạng tương ứng với luồng cực đại 3.
- Chứng minh chặt cho mọi cận: Bổ đề 26.7 và Định lý 26.8 (Edmonds-Karp), Bổ đề 26.19–26.23 và Định lý 26.24 (đẩy–nâng nhãn), Định lý 26.30 (relabel-to-front).
- Ví dụ xả đỉnh y (15 vòng lặp) và chạy RELABEL-TO-FRONT trên mạng 5 đỉnh (luồng 20).

### Kết luận và hàm ý cho người lập trình

- Khi gặp bài toán "phân bổ", "ghép", "chọn tập con có ràng buộc phụ thuộc", hãy nghĩ tới mô hình luồng/lát cắt: siêu nguồn/siêu đích, tách đỉnh để đặt sức chứa đỉnh, cạnh ∞ để ép ràng buộc "chọn A thì phải chọn B" (Problem 26-3, bài toán đóng tập có trọng số).
- Đừng dùng DFS tuỳ ý để tìm đường tăng luồng khi sức chứa lớn: thời gian phụ thuộc vào |f*|. Dùng BFS (Edmonds-Karp), co giãn (Problem 26-5), Dinic, hoặc đẩy–nâng nhãn.
- Cài đặt cần lưu cạnh ngược cùng cạnh thuận (thường là cặp chỉ số liền nhau trong mảng cạnh) để tính c_f trong O(1).
- Sau khi có luồng cực đại, lát cắt cực tiểu có được miễn phí bằng một lần BFS trên mạng thặng dư.
- Với cặp ghép hai phía, tính nguyên đảm bảo luồng nguyên; dùng Hopcroft-Karp (O(√V E)) khi đồ thị lớn.
- Với đẩy–nâng nhãn thực tế, hai heuristic (nâng nhãn toàn cục bằng BFS định kỳ, khe hở) quan trọng hơn chọn biến thể.

### Trong ngôn ngữ khoa học máy tính

Mạng luồng G = (V, E, c, s, t); luồng f thoả 0 ≤ f ≤ c và bảo toàn tại V − {s, t}; |f| = Σ_v f(s, v) − Σ_v f(v, s). Mạng thặng dư G_f với c_f theo (26.2), |E_f| ≤ 2|E|. Bổ đề 26.4: f(S, T) = |f|; Hệ quả 26.5: |f| ≤ c(S, T); Định lý 26.6: max |f| = min c(S, T). FORD-FULKERSON: O(E|f*|) với sức chứa nguyên; Edmonds-Karp: O(VE) lần tăng, O(VE²). Cặp ghép hai phía: O(VE) qua mạng sức chứa đơn vị và Định lý 26.10. Đẩy–nâng nhãn tổng quát: h ≤ 2|V| − 1, nâng nhãn < 2|V|², đẩy bão hoà < 2|V||E|, đẩy không bão hoà < 4|V|²(|V| + |E|), tổng O(V²E). RELABEL-TO-FRONT: O(V³). Problems: co giãn O(E² lg C), Hopcroft-Karp O(√V E). Ghi chú chương: Goldberg–Rao O(min(V^(2/3), E^(1/2)) E lg(V²/E + 2) lg C).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| flow network | mạng luồng | đồ thị có hướng có sức chứa, nguồn, đích |
| capacity | sức chứa | tốc độ tối đa qua một cạnh |
| source / sink | nguồn / đích | nơi sản xuất / nơi tiêu thụ vật chất |
| flow | luồng | hàm thoả ràng buộc sức chứa và bảo toàn luồng |
| capacity constraint | ràng buộc sức chứa | 0 ≤ f(u, v) ≤ c(u, v) |
| flow conservation | bảo toàn luồng | vào bằng ra tại mọi đỉnh trừ s, t |
| value of a flow | giá trị luồng | luồng ra khỏi s trừ luồng vào s |
| maximum-flow problem | bài toán luồng cực đại | tìm luồng có giá trị lớn nhất |
| antiparallel edges | cạnh ngược chiều | cặp (u, v), (v, u) cùng có trong E |
| supersource / supersink | siêu nguồn / siêu đích | đỉnh thêm vào để gộp nhiều nguồn / nhiều đích |
| residual capacity | sức chứa thặng dư | lượng còn thêm hoặc còn trả lại được |
| residual network / residual edge | mạng thặng dư / cạnh thặng dư | các cặp đỉnh có sức chứa thặng dư dương |
| augmentation (f ↑ f′) | phép tăng luồng | cộng luồng của mạng thặng dư vào luồng gốc |
| cancellation | triệt tiêu | đẩy trên cạnh ngược để giảm luồng gốc |
| augmenting path | đường tăng luồng | đường đơn s ⇝ t trong mạng thặng dư |
| cut (S, T) | lát cắt | phân hoạch đỉnh với s ∈ S, t ∈ T |
| net flow across a cut | luồng ròng qua lát cắt | luồng S → T trừ luồng T → S |
| capacity of a cut | sức chứa của lát cắt | tổng sức chứa các cạnh S → T |
| minimum cut | lát cắt cực tiểu | lát cắt sức chứa nhỏ nhất |
| max-flow min-cut theorem | định lý luồng cực đại – lát cắt cực tiểu | luồng cực đại bằng lát cắt cực tiểu |
| Ford-Fulkerson method | phương pháp Ford-Fulkerson | lặp tăng luồng dọc đường tăng luồng |
| Edmonds-Karp algorithm | thuật toán Edmonds-Karp | Ford-Fulkerson với đường ngắn nhất (BFS) |
| critical edge | cạnh tới hạn | cạnh có sức chứa thặng dư bằng c_f(p) |
| matching / matched / unmatched | cặp ghép / được ghép / chưa được ghép | tập cạnh không chung đỉnh |
| maximum matching | cặp ghép cực đại | cặp ghép có nhiều cạnh nhất |
| perfect matching | cặp ghép hoàn hảo | mọi đỉnh đều được ghép |
| bipartite graph | đồ thị hai phía | đỉnh chia hai phần, cạnh nối hai phần |
| corresponding flow network | mạng luồng tương ứng | mạng sức chứa 1 dựng từ đồ thị hai phía |
| integer-valued flow | luồng nhận giá trị nguyên | mọi f(u, v) là số nguyên |
| integrality theorem | định lý tính nguyên | sức chứa nguyên thì Ford-Fulkerson cho luồng nguyên |
| Hall's theorem / neighborhood | định lý Hall / lân cận | điều kiện có cặp ghép hoàn hảo |
| d-regular | d-chính quy | mọi đỉnh có bậc d |
| push-relabel method | phương pháp đẩy–nâng nhãn | đẩy luồng dư cục bộ theo độ cao |
| preflow | tiền luồng | luồng vào được phép vượt luồng ra |
| excess flow | luồng dư | luồng vào trừ luồng ra tại một đỉnh |
| overflowing vertex | đỉnh tràn | đỉnh khác s, t có luồng dư dương |
| height function (distance function, distance label) | hàm độ cao (hàm khoảng cách, nhãn khoảng cách) | h(s) = |V|, h(t) = 0, h(u) ≤ h(v) + 1 trên cạnh thặng dư |
| push / saturating / nonsaturating push | đẩy / đẩy bão hoà / đẩy không bão hoà | chuyển luồng dư xuống dốc một bậc |
| relabel | nâng nhãn | tăng độ cao đỉnh bị kẹt |
| potential function | hàm thế | dùng để chặn số lần đẩy không bão hoà |
| admissible edge / admissible network | cạnh chấp nhận được / mạng chấp nhận được | cạnh thặng dư xuống dốc đúng một bậc |
| neighbor list | danh sách đỉnh kề | mọi v có (u, v) hoặc (v, u) trong E |
| discharge | xả | đẩy hết luồng dư của một đỉnh |
| relabel-to-front algorithm | thuật toán nâng nhãn rồi đưa lên đầu | xả theo danh sách, đỉnh vừa nâng nhãn lên đầu |
| phase | pha | khoảng giữa hai lần nâng nhãn liên tiếp |
| gap heuristic | heuristic khe hở | nâng hẳn các đỉnh trên một "khe" độ cao |
| blocking flow | luồng chặn | khái niệm của Dinic, nền của Goldberg–Rao |
| scaling | co giãn | chỉ dùng đường có sức chứa ≥ K, K giảm dần |
| escape problem | bài toán thoát hiểm | đường rời nhau từ các điểm tới biên lưới |
| path cover | phủ đường | tập đường rời nhau phủ mọi đỉnh |
| symmetric difference (⊕) | hiệu đối xứng | phần tử thuộc đúng một trong hai tập |
| edge connectivity | độ liên thông cạnh | số cạnh ít nhất cần xoá để mất liên thông |
| vertex capacities | sức chứa đỉnh | giới hạn luồng đi qua một đỉnh |

## Câu nói đáng nhớ

> "Just as we can model a road map as a directed graph in order to find the shortest path from one point to another, we can also interpret a directed graph as a 'flow network' and use it to answer questions about material flows." — mở đầu Chương 26
>
> *Dịch: Giống như có thể mô hình bản đồ đường sá bằng đồ thị có hướng để tìm đường đi ngắn nhất từ điểm này tới điểm kia, ta cũng có thể coi một đồ thị có hướng là một "mạng luồng" và dùng nó để trả lời các câu hỏi về dòng vật chất.*

> "Cancellation of this type is crucial for any maximum-flow algorithm." — Mục 26.2, mạng thặng dư
>
> *Dịch: Kiểu triệt tiêu này thiết yếu cho mọi thuật toán luồng cực đại.*

> "The asymmetry between the definitions of flow and capacity of a cut is intentional and important." — Mục 26.2, lát cắt
>
> *Dịch: Sự bất đối xứng giữa định nghĩa luồng và sức chứa của lát cắt là cố ý và quan trọng.*

> "The important max-flow min-cut theorem … says that the value of a maximum flow is in fact equal to the capacity of a minimum cut." — Mục 26.2
>
> *Dịch: Định lý quan trọng luồng cực đại – lát cắt cực tiểu … nói rằng giá trị của luồng cực đại thực ra bằng sức chứa của lát cắt cực tiểu.*

> "Push-relabel algorithms work in a more localized manner than the Ford-Fulkerson method." — Mục 26.4
>
> *Dịch: Thuật toán đẩy–nâng nhãn làm việc cục bộ hơn phương pháp Ford-Fulkerson.*

> "As we shall see, once we have emptied all the reservoirs, the preflow is not only a 'legal' flow, it is also a maximum flow." — Mục 26.4, trực giác
>
> *Dịch: Như sẽ thấy, khi đã làm rỗng mọi bể chứa, tiền luồng không chỉ là một luồng "hợp lệ" mà còn là luồng cực đại.*

> "In practice, push-relabel algorithms currently dominate augmenting-path or linear-programming based algorithms for the maximum-flow problem." — Ghi chú chương
>
> *Dịch: Trong thực tế, thuật toán đẩy–nâng nhãn hiện thống trị các thuật toán dựa trên đường tăng luồng hay quy hoạch tuyến tính cho bài toán luồng cực đại.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: định lý luồng cực đại – lát cắt cực tiểu được dựng thành chuỗi bổ đề gọn và dùng lại nhiều lần

Chương chọn cách định nghĩa luồng không âm chỉ trên cạnh (khác ấn bản 2 dùng "luồng đối xứng lệch" f(u, v) = −f(v, u) — theo hiểu biết của người tổng hợp), cộng giả định không có cạnh ngược chiều, nên mạng thặng dư (26.2) có đúng một trường hợp cho mỗi cặp đỉnh và trực giác "thêm được / trả lại được" rất rõ. Chuỗi Bổ đề 26.1 → 26.2 → Hệ quả 26.3 → Bổ đề 26.4 → Hệ quả 26.5 → Định lý 26.6 làm định lý trung tâm trở thành gần như hiển nhiên, và chính chứng minh (2) ⇒ (3) cho luôn thuật toán tìm lát cắt cực tiểu. Cùng định lý đó lại được dùng làm bước cuối cho tính đúng của đẩy–nâng nhãn (Định lý 26.18): hai họ thuật toán rất khác nhau nhưng chung một tiêu chuẩn tối ưu.

### Điểm mạnh: phân tích đẩy–nâng nhãn là ví dụ mẫu mực về đếm từng loại thao tác

Mỗi loại thao tác được chặn bằng một công cụ khác: nâng nhãn bằng cận độ cao (từ đường thặng dư về nguồn), đẩy bão hoà bằng lập luận "độ cao phải tăng 2 giữa hai lần", đẩy không bão hoà bằng hàm thế (Chương 17). Relabel-to-front thêm một ý tinh tế: mạng chấp nhận được là dag và danh sách luôn được sắp xếp topo, nên chỉ cần đếm "pha". Người đọc học được cách tách một thuật toán "không xác định thứ tự" thành các sự kiện đếm được.

### Điểm yếu và chỗ đơn giản hoá

- **Không có ví dụ chạy tay nào cho thuật toán đẩy–nâng nhãn tổng quát** ở Mục 26.4 — người đọc phải đợi tới hai ví dụ của Mục 26.5 (xả đỉnh y, mạng 5 đỉnh) mới thấy thao tác cụ thể (bản tổng hợp này bổ sung một ví dụ).
- **Không chứng minh khả năng không dừng với sức chứa vô tỷ**; chú thích chỉ khẳng định. Ví dụ kinh điển (của Zwick, hay ví dụ dùng tỷ lệ vàng — theo hiểu biết của người tổng hợp) không được nêu.
- **Thuật toán Dinic chỉ được nhắc trong ghi chú**, dù trong thực hành (đặc biệt lập trình thi đấu) nó phổ biến hơn Edmonds-Karp và cùng tinh thần "đường ngắn nhất"; trên mạng đơn vị, Dinic chạy O(E√V), bao gồm luôn Hopcroft-Karp.
- **Các heuristic thực tế** (nâng nhãn toàn cục, khe hở) — mà chính ghi chú chương thừa nhận là quyết định hiệu năng — chỉ nằm ở bài tập.
- **Luồng chi phí nhỏ nhất** (min-cost flow), bài toán thực tế rất quan trọng, chỉ được nhắc qua; sách để cho Chương 29 dưới dạng quy hoạch tuyến tính.
- **Định nghĩa đường tăng trong cặp ghép (Problem 26-6) khác đường tăng luồng** — sách có lưu ý, nhưng hai khái niệm cùng tên dễ gây nhầm cho người học.

### So với thực tế

Theo hiểu biết của người tổng hợp: trong thư viện và công cụ, luồng cực đại thường được cài bằng đẩy–nâng nhãn chọn đỉnh cao nhất kèm heuristic (ví dụ trong Boost Graph Library, OR-Tools, LEMON), hoặc Boykov–Kolmogorov cho đồ thị lưới trong thị giác máy tính (phân đoạn ảnh bằng graph cut). Trong lập trình thi đấu, Dinic là lựa chọn mặc định. Về lý thuyết, sau khi sách ra đời, Orlin (2013) đưa ra thuật toán O(VE) cho luồng cực đại, và năm 2022 Chen, Kyng, Liu, Peng, Probst Gutenberg và Sachdeva công bố thuật toán thời gian gần tuyến tính E^(1+o(1)) cho cả luồng chi phí nhỏ nhất — nên nhận định "Goldberg–Rao là nhanh nhất" của ghi chú chương đã lỗi thời.

### Liên hệ các chương khác

- Chương 17: hàm thế Φ trong Bổ đề 26.23 là phương pháp thế của phân tích khấu hao.
- Chương 22: BFS (Edmonds-Karp, tìm lát cắt cực tiểu), DFS, sắp xếp topo (bất biến relabel-to-front), đồ thị chuyển vị Gᵀ (độ cao gắn với khoảng cách tới t).
- Chương 23: khái niệm lát cắt, nay có hướng và có s ∈ S, t ∈ T.
- Chương 24: khoảng cách đường đi ngắn nhất δ và bất đẳng thức tam giác (Bổ đề 24.10) trong chứng minh Bổ đề 26.7.
- Chương 29: luồng cực đại và luồng chi phí nhỏ nhất dạng quy hoạch tuyến tính; định lý luồng cực đại – lát cắt cực tiểu là trường hợp riêng của đối ngẫu.
- Chương 34–35: cặp ghép hai phía giải được trong thời gian đa thức, trái với nhiều bài toán phủ/ghép tổng quát NP-đầy đủ; cặp ghép cực đại dùng trong thuật toán xấp xỉ phủ đỉnh.
- Phụ lục B: bổ đề bắt tay (tổng bậc bằng hai lần số cạnh) trong Định lý 26.30.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** giải thích định lý luồng cực đại – lát cắt cực tiểu và vì sao cần cạnh ngược trong mạng thặng dư (ví dụ mạng 4 đỉnh: không có cạnh ngược thì tham lam chọn s → u → v → t sẽ kẹt ở luồng 1); quy bài toán phân công/ghép về luồng; nêu độ phức tạp Ford-Fulkerson, Edmonds-Karp.
- **Lập trình thi đấu:** mẫu Dinic với danh sách cạnh có cạnh ngược ở chỉ số e ^ 1; các mô hình chuẩn: tách đỉnh (sức chứa đỉnh, đường rời đỉnh — Problem 26-1), phủ đường tối thiểu trên DAG (Problem 26-2), đóng tập có trọng số lớn nhất / chọn dự án (Problem 26-3), luồng có cận dưới, cặp ghép hai phía bằng Hopcroft-Karp hoặc Kuhn.
- **Kỹ thuật phần mềm:** lập lịch và phân bổ tài nguyên (gán tác vụ cho máy có năng lực khác nhau), phân tích điểm nghẽn mạng (lát cắt cực tiểu là tập liên kết yếu nhất), phân đoạn ảnh, phát hiện cộng đồng; khi bài toán có chi phí thì chuyển sang luồng chi phí nhỏ nhất hoặc quy hoạch tuyến tính.

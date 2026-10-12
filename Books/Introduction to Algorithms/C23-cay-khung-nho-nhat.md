# Chương 23 — Cây khung nhỏ nhất (Minimum Spanning Trees)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VI "Graph Algorithms", Chương 23 "Minimum Spanning Trees", trang 624–642 (phần mở đầu chương trang 624–625, Mục 23.1 trang 625–630, Mục 23.2 trang 631–638, Bài toán cuối chương trang 638–641, Ghi chú chương trang 641–642).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Chương 22 ([C22-thuat-toan-do-thi-co-ban.md](C22-thuat-toan-do-thi-co-ban.md)) mở Phần VI bằng cách biểu diễn đồ thị (danh sách kề, ma trận kề) và hai phép duyệt BFS, DFS — đồ thị ở đó chưa có trọng số. Chương 23 là chương đầu tiên của Phần VI làm việc với **đồ thị có trọng số**: tìm tập cạnh nối mọi đỉnh với tổng trọng số nhỏ nhất. Chương dựa trực tiếp vào ba chương trước đó: Chương 16 ([C16-thuat-toan-tham-lam.md](C16-thuat-toan-tham-lam.md)) cho khái niệm thuật toán tham lam và matroid — lý do sâu xa vì sao tham lam đúng với bài toán này; Chương 21 ([C21-cau-truc-du-lieu-cho-tap-roi-nhau.md](C21-cau-truc-du-lieu-cho-tap-roi-nhau.md)) cho cấu trúc tập rời nhau (MAKE-SET, FIND-SET, UNION) mà thuật toán Kruskal dùng; Chương 6 ([C06-heapsort.md](C06-heapsort.md)) và Chương 19 ([C19-dong-fibonacci.md](C19-dong-fibonacci.md)) cho hàng đợi ưu tiên bằng đống nhị phân và đống Fibonacci mà thuật toán Prim dùng. Phụ lục B ([PB-tap-hop-va-cau-truc-roi-rac.md](PB-tap-hop-va-cau-truc-roi-rac.md)) cho định nghĩa cây tự do và định lý "cây n đỉnh có n − 1 cạnh". Chương 24 ([C24-duong-di-ngan-nhat-tu-mot-nguon.md](C24-duong-di-ngan-nhat-tu-mot-nguon.md)) dùng lại gần như nguyên khuôn của thuật toán Prim cho thuật toán Dijkstra; Chương 35 ([C35-thuat-toan-xap-xi.md](C35-thuat-toan-xap-xi.md)) dùng cây khung nhỏ nhất làm bước đầu của thuật toán xấp xỉ cho bài toán người du lịch có bất đẳng thức tam giác.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **bài toán cây khung nhỏ nhất là một trong số ít bài toán mà chiến lược tham lam "lấy cạnh nhẹ nhất có thể ở mỗi bước" luôn cho lời giải tối ưu, và lý do nằm ở một quy tắc duy nhất: nếu tập cạnh A đang nằm trong một cây khung nhỏ nhất nào đó, thì cạnh nhẹ nhất đi qua bất kỳ lát cắt nào tôn trọng A là cạnh an toàn — thêm nó vào A vẫn giữ được tính chất "nằm trong một cây khung nhỏ nhất" (Định lý 23.1). Kruskal và Prim chỉ là hai cách chọn lát cắt khác nhau, chạy O(E lg V) với đống nhị phân, và Prim chạy O(E + V lg V) với đống Fibonacci.** Phần mở đầu chương nêu bài toán đi dây điện nối n chân linh kiện, mô hình hoá thành đồ thị vô hướng liên thông có trọng số, và định nghĩa cây khung (spanning tree) cùng bài toán cây khung nhỏ nhất. Mục 23.1 trình bày phương pháp tổng quát GENERIC-MST: giữ tập cạnh A với bất biến "A là tập con của một cây khung nhỏ nhất", mỗi bước thêm một cạnh an toàn; định nghĩa lát cắt (cut), cạnh đi qua lát cắt, lát cắt tôn trọng A, cạnh nhẹ (light edge); chứng minh Định lý 23.1 bằng kỹ thuật cắt và dán (đổi một cạnh trên đường đi trong cây lấy cạnh nhẹ); rút ra Hệ quả 23.2: cạnh nhẹ nối một thành phần liên thông của rừng (V, A) với thành phần khác là an toàn. Mục 23.2 trình bày hai thuật toán cụ thể. Kruskal giữ A là một rừng, sắp xếp cạnh tăng dần theo trọng số, lần lượt thêm cạnh nối hai cây khác nhau, kiểm tra bằng FIND-SET và gộp bằng UNION; thời gian O(E lg E) = O(E lg V), bị chi phối bởi bước sắp xếp. Prim giữ A là một cây duy nhất mọc từ gốc r; mọi đỉnh chưa vào cây nằm trong hàng đợi ưu tiên min Q theo khoá *key* (trọng số cạnh nhẹ nhất nối đỉnh đó với cây); mỗi bước EXTRACT-MIN lấy đỉnh gần cây nhất rồi cập nhật khoá các đỉnh kề; thời gian O(E lg V) với đống nhị phân, O(E + V lg V) với đống Fibonacci. Các bài toán cuối chương bàn về cây khung nhỏ thứ hai, bước tiền xử lý co cạnh (MST-REDUCE, chính là một vòng của thuật toán Borůvka) để tăng tốc trên đồ thị thưa, cây khung nút cổ chai, và ba "thuật toán có thể đúng" để người đọc tự phân xử. Ghi chú chương kể lịch sử (Borůvka 1926, Jarník 1930, Kruskal 1956, Prim) và các thuật toán nhanh hơn: O(E lg* V), O(E lg lg* V), O(E α̂(E, V)) của Chazelle, thuật toán ngẫu nhiên O(V + E) kỳ vọng.

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong chương.** Dấu sao chỉ xuất hiện ở ba bài tập: Exercise 23.1-11, Exercise 23.2-6 và Exercise 23.2-7.
> - **Lớp chữ PDF hỏng nhiều ký hiệu toán; mọi pseudocode, công thức và hình trong bản tổng hợp được đọc lại từ ảnh trang 624–642.** Cụ thể: chữ v (đỉnh) bị mất hoàn toàn, `.u; /` là (u, v), `: key` là v.key, `: D u` là v.π = u (ký hiệu π cũng mất); dấu ≠, ≤, ≥, ∞, ∅ mất (ví dụ `jEjjVj/NUL 1` là |E| ≥ |V| − 1, `u:keyD1` là u.key = ∞, `Q¤;` là Q ≠ ∅); `˛.V /` là α(V). Chỗ hỏng nặng nhất ở Ghi chú chương trang 642: lớp chữ in "O(E lg V)" và "O(E lg lg V)" cho thuật toán của Fredman–Tarjan và của Gabow–Galil–Spencer–Tarjan, nhưng ảnh trang cho thấy đúng là **O(E lg\* V)** và **O(E lg lg\* V)** (có dấu sao của hàm logarit lặp); "Ey˛.E; V /" là O(E α̂(E, V)); ".V lg V/" là |E| = Ω(V lg V). Ba hình nhiều bước — Hình 23.4 (14 bước của Kruskal, trang 632–633), Hình 23.5 (9 bước của Prim, trang 635) và Hình 23.2 (lát cắt, trang 627) — không đọc được từ lớp chữ; người tổng hợp đọc từ ảnh và tái hiện thành bảng.
> - **Thủ tục MST-REDUCE của Problem 23-2 không loại khuyên (self-loop) — nhận xét của người tổng hợp.** Ở dòng 12–21, một cạnh (x, y) mà hai đầu mút đã được gộp vào cùng một tập (FIND-SET(x) = FIND-SET(y) = u) sẽ được thêm vào G′.E dưới dạng cạnh (u, u). Đồ thị co lại theo đúng nghĩa ở Mục B.4 không có khuyên. Cần thêm điều kiện "nếu u ≠ v" trước dòng 15. Khuyên không làm Prim sai (một khuyên không bao giờ được chọn vì đầu kia đã ở trong cây), nhưng làm sai định nghĩa và tốn thời gian. Người tổng hợp không chắc chỗ này có trong danh sách lỗi chính thức (errata) hay không.
> - **Ví dụ chạy tay đã tự kiểm tra lại và đúng:** cây khung nhỏ nhất của đồ thị 9 đỉnh, 14 cạnh có tổng trọng số 37; Kruskal (Hình 23.4) thêm lần lượt các cạnh trọng số 1, 2, 2, 4, 4, 7, 8, 9 (tổng 37) và loại các cạnh 6, 7, 8, 10, 11, 14; Prim từ gốc a (Hình 23.5) thêm các đỉnh theo thứ tự a, b, c, i, f, g, h, d, e, tổng 37. **Một điểm dễ bỏ sót:** cây mà Kruskal trả về trong Hình 23.4 chứa cạnh (a, h) chứ không chứa (b, c), tức là khác với cây tô đậm trong Hình 23.1 và khác cây của Prim trong Hình 23.5 — cả ba đều nặng 37, khớp với chú thích của Hình 23.1 rằng cây khung nhỏ nhất của đồ thị này không duy nhất.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương này trở thành Chương 21 (vì hai chương đống Fibonacci và cây van Emde Boas bị bỏ khỏi bản in, các chương sau được đánh số lại). Nội dung cốt lõi (GENERIC-MST, Định lý 23.1, Kruskal, Prim) giữ nguyên. Tôi nhớ (không chắc chắn) rằng pseudocode Prim ở ấn bản 4 viết tường minh lời gọi INSERT vào Q và DECREASE-KEY thay vì gán khoá ngầm. Các khác biệt nhỏ hơn về bài tập, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 23.1, trang 624–625) — bài toán đi dây và định nghĩa cây khung nhỏ nhất

```text
       Bài toán thực tế: nối n chân linh kiện điện tử cho cùng điện thế
       · cần n − 1 sợi dây, mỗi sợi nối hai chân
       · muốn tổng chiều dài dây nhỏ nhất
                                │
                                ▼
       Mô hình: đồ thị VÔ HƯỚNG, LIÊN THÔNG G = (V, E)
       · V = các chân; E = các cặp chân có thể nối
       · trọng số w(u, v) = lượng dây cần để nối u với v
                                │
                                ▼
       Tìm tập cạnh T ⊆ E KHÔNG CÓ CHU TRÌNH, nối mọi đỉnh,
       với tổng w(T) = Σ_{(u,v)∈T} w(u, v) nhỏ nhất
       · T không chu trình và nối mọi đỉnh ⇒ T là một CÂY
         gọi là CÂY KHUNG (spanning tree) vì nó "phủ" mọi đỉnh của G
       · "cây khung nhỏ nhất" là cách nói tắt của "cây khung có tổng
         trọng số nhỏ nhất" — không phải ít cạnh nhất, vì mọi cây khung
         đều có đúng |V| − 1 cạnh (Định lý B.2)
                                │
                                ▼
       Hai thuật toán của chương: KRUSKAL và PRIM
       · cả hai dễ đạt O(E lg V) với đống nhị phân thường
       · Prim với đống Fibonacci: O(E + V lg V), tốt hơn khi |V| nhỏ hơn
         nhiều so với |E|
                                │
                                ▼
       Cả hai là thuật toán THAM LAM (Chương 16): mỗi bước chọn cái tốt
       nhất lúc đó. Tham lam nói chung không bảo đảm tối ưu toàn cục,
       nhưng với bài toán này thì chứng minh được là có
                                │
                                ▼
       Quy ước: các đỉnh của một cây T là các đỉnh mà ít nhất một cạnh
       của T chạm vào
```

### Ví dụ xuyên suốt chương — đồ thị 9 đỉnh, 14 cạnh (Hình 23.1, trang 625)

```text
                 8               7
          b ─────────────── c ─────────────── d
        ╱ │               ╱   ╲               │ ╲
     4 ╱  │            2 ╱      ╲ 4           │   ╲ 9
      ╱   │             ╱         ╲           │     ╲
     a    │ 11         i            ╲      14 │       e
      ╲   │         ╱    ╲            ╲       │     ╱
     8 ╲  │      7 ╱      ╲ 6           ╲     │   ╱ 10
        ╲ │     ╱           ╲             ╲   │ ╱
          h ─────────────── g ─────────────── f
                 1               2

       14 cạnh: ab 4, ah 8, bc 8, bh 11, cd 7, ci 2, cf 4, de 9, df 14,
                ef 10, fg 2, gh 1, gi 6, hi 7
       Một cây khung nhỏ nhất (tô đậm trong sách):
                ab 4, bc 8, cd 7, ci 2, cf 4, de 9, fg 2, gh 1
                tổng = 4 + 8 + 7 + 2 + 4 + 9 + 2 + 1 = 37
       Không duy nhất: bỏ (b, c) thay bằng (a, h) cũng được cây nặng 37
```

### Mục 23.1 — Mọc dần một cây khung nhỏ nhất (Growing a minimum spanning tree, trang 625–630)

```text
       PHƯƠNG PHÁP TỔNG QUÁT GENERIC-MST(G, w)
       Giữ tập cạnh A với BẤT BIẾN VÒNG LẶP:
       "trước mỗi vòng lặp, A là tập con của MỘT cây khung nhỏ nhất nào đó"
                                │
                                ▼
       Mỗi bước thêm một CẠNH AN TOÀN (safe edge) (u, v):
       A ∪ {(u, v)} vẫn là tập con của một cây khung nhỏ nhất
       · khởi tạo: A = ∅ hiển nhiên thoả
       · duy trì: chỉ thêm cạnh an toàn
       · kết thúc: A là cây khung và nằm trong một cây khung nhỏ nhất
         ⇒ A chính là cây khung nhỏ nhất
       · luôn tồn tại cạnh an toàn: A ⊊ T nên có cạnh của T ngoài A
                                │
                                ▼
       ĐỊNH NGHĨA (Hình 23.2 — minh hoạ trên đồ thị ví dụ)
       · LÁT CẮT (S, V − S): một cách chia V thành hai phần
       · cạnh ĐI QUA lát cắt: một đầu trong S, đầu kia trong V − S
       · lát cắt TÔN TRỌNG tập A: không cạnh nào của A đi qua nó
       · CẠNH NHẸ đi qua lát cắt: trọng số nhỏ nhất trong các cạnh đi qua
         (có thể có nhiều cạnh nhẹ nếu bằng trọng số)
       Ví dụ: S = {a, b, d, e}; các cạnh đi qua: ah 8, bh 11, bc 8, dc 7,
       df 14, ef 10 ⇒ cạnh nhẹ duy nhất là (d, c) trọng số 7
                                │
                                ▼
       ĐỊNH LÝ 23.1: A nằm trong một cây khung nhỏ nhất, lát cắt (S, V − S)
       tôn trọng A, (u, v) là cạnh nhẹ đi qua lát cắt ⇒ (u, v) an toàn
                                │
                                ▼
       Chứng minh CẮT VÀ DÁN (cut-and-paste):
       · T là cây khung nhỏ nhất chứa A; giả sử (u, v) ∉ T
       · đường đi duy nhất p từ u tới v trong T phải có ít nhất một cạnh
         (x, y) đi qua lát cắt; (x, y) ∉ A vì lát cắt tôn trọng A
       · T′ = T − {(x, y)} ∪ {(u, v)} vẫn là cây khung
       · w(u, v) ≤ w(x, y) ⇒ w(T′) ≤ w(T) ⇒ T′ cũng nhỏ nhất
       · A ∪ {(u, v)} ⊆ T′ ⇒ (u, v) an toàn
                                │
                                ▼
       Hệ quả về cấu trúc: G_A = (V, A) luôn là một RỪNG
       · ban đầu |V| cây một đỉnh; mỗi cạnh an toàn nối hai cây khác nhau
       · vòng lặp chạy đúng |V| − 1 lần
                                │
                                ▼
       HỆ QUẢ 23.2: C là một thành phần (cây) của rừng G_A; (u, v) là cạnh
       nhẹ nối C với thành phần khác ⇒ (u, v) an toàn
       (dùng lát cắt (V_C, V − V_C), lát cắt này tôn trọng A)
```

### Mục 23.2 — Thuật toán Kruskal và Prim (The algorithms of Kruskal and Prim, trang 631–638)

```text
       Cả hai là trường hợp riêng của GENERIC-MST; khác nhau ở cách
       chọn cạnh an toàn ở dòng 3
           ┌────────────────────────────┴────────────────────────────┐
           ▼                                                         ▼
   KRUSKAL                                          PRIM
   · A là một RỪNG phủ mọi đỉnh                     · A luôn là MỘT CÂY mọc từ gốc r
   · cạnh thêm vào: cạnh nhẹ nhất                   · cạnh thêm vào: cạnh nhẹ nhất
     trong cả đồ thị nối HAI CÂY                      nối cây với một đỉnh CHƯA ở
     KHÁC NHAU của rừng                               trong cây
   · cài đặt: tập rời nhau                          · cài đặt: hàng đợi ưu tiên min Q
     MAKE-SET / FIND-SET / UNION                      chứa các đỉnh chưa vào cây,
   · sắp xếp cạnh tăng dần, duyệt                     khoá v.key = trọng số cạnh nhẹ
     lần lượt; nếu FIND-SET(u) ≠                      nhất nối v với cây (∞ nếu không
     FIND-SET(v) thì thêm và UNION                    có), v.π = cha của v trong cây
   · thời gian:                                     · mỗi vòng: u = EXTRACT-MIN(Q);
     sắp xếp O(E lg E)                                với mỗi v kề u còn trong Q, nếu
     + O((V + E) α(V)) cho tập rời nhau               w(u, v) < v.key thì v.π = u,
     = O(E lg E) = O(E lg V)                          v.key = w(u, v) (DECREASE-KEY)
   · trên ví dụ: thêm 1, 2, 2, 4, 4, 7,             · thời gian:
     8 (a, h), 9; loại 6, 7, 8 (b, c),                đống nhị phân O(E lg V)
     10, 11, 14; tổng 37                              đống Fibonacci O(E + V lg V)
                                                    · trên ví dụ, gốc a: thêm các đỉnh
                                                      a, b, c, i, f, g, h, d, e; tổng 37
           └────────────────────────────┬────────────────────────────┘
                                        ▼
       Cả hai đúng nhờ Hệ quả 23.2:
       · Kruskal: cạnh nhẹ nhất nối hai cây C₁, C₂ là cạnh nhẹ nối C₁
         với thành phần khác
       · Prim: cạnh nhẹ nhất nối cây với ngoài cây là cạnh nhẹ đi qua
         lát cắt (V − Q, Q)
```

### Bài toán cuối chương (Problems 23-1 đến 23-4, trang 638–641)

```text
       23-1 Cây khung nhỏ thứ hai (second-best MST)
            · trọng số đôi một khác nhau ⇒ cây khung nhỏ nhất duy nhất,
              nhưng cây nhỏ thứ hai có thể không duy nhất
            · luôn có cây nhỏ thứ hai khác cây nhỏ nhất đúng MỘT cạnh
            · tính max[u, v] (cạnh nặng nhất trên đường u–v trong cây) cho
              mọi cặp trong O(V²) ⇒ cây nhỏ thứ hai trong O(V²)
                                │
                                ▼
       23-2 Cây khung nhỏ nhất trên đồ thị thưa: TIỀN XỬ LÝ BẰNG CO CẠNH
            · MST-REDUCE: mỗi đỉnh chọn cạnh nhẹ nhất chạm vào nó, đưa vào
              cây, co các cạnh đó lại; giữ cạnh nhẹ nhất giữa hai đỉnh mới
            · số đỉnh giảm ít nhất một nửa; mỗi lần O(E)
            · k = lg lg V lần rồi chạy Prim ⇒ O(E lg lg V)
                                │
                                ▼
       23-3 Cây khung nút cổ chai (bottleneck spanning tree)
            · cạnh nặng nhất của cây nhỏ nhất có thể
            · mọi cây khung nhỏ nhất là cây khung nút cổ chai
            · tìm được trong thời gian TUYẾN TÍNH (chia đôi theo trung vị
              trọng số + co cạnh)
                                │
                                ▼
       23-4 Ba "thuật toán có thể đúng"
            · A: xoá cạnh nặng nhất nếu đồ thị vẫn liên thông — ĐÚNG
            · B: thêm cạnh theo thứ tự tuỳ ý nếu không tạo chu trình — SAI
            · C: thêm cạnh tuỳ ý, gặp chu trình thì bỏ cạnh nặng nhất trên
              chu trình — ĐÚNG
```

### Ghi chú chương (Chapter notes, trang 641–642)

```text
       Tài liệu: Tarjan (tổng quan, nâng cao); Graham và Hell (lịch sử)
                                │
                                ▼
       Lịch sử: Borůvka 1926 (thuật toán đầu tiên = O(lg V) lần MST-REDUCE)
                Jarník 1930 (phát minh thuật toán "Prim" trước Prim)
                Kruskal 1956; Prim
                                │
                                ▼
       Lý do tham lam đúng: tập các rừng của một đồ thị là một MATROID
       ĐỒ THỊ (graphic matroid, Mục 16.4)
                                │
                                ▼
       Thuật toán nhanh hơn
       · |E| = Ω(V lg V): Prim + đống Fibonacci đã là O(E)
       · Fredman–Tarjan: O(E lg* V); Gabow–Galil–Spencer–Tarjan: O(E lg lg* V)
       · Chazelle: O(E α̂(E, V)) — KHÔNG theo phương pháp tham lam
       · Karger–Klein–Tarjan: ngẫu nhiên, kỳ vọng O(V + E)
       · Fredman–Willard: tất định O(V + E) nhưng không dựa trên so sánh
         (số nguyên b bit, máy có từ nhớ b bit)
                                │
                                ▼
       Bài toán liên quan: KIỂM CHỨNG cây khung (spanning-tree verification)
       — cho T, kiểm tra T có nhỏ nhất không: King, thời gian tuyến tính
```

## Ba câu hỏi chương này trả lời

1. **Vì sao một chiến lược tham lam lại luôn tìm được cây khung nhỏ nhất?** Vì có một quy tắc nhận diện cạnh an toàn (Định lý 23.1): nếu tập cạnh A đang nằm trong một cây khung nhỏ nhất, lấy bất kỳ lát cắt (S, V − S) nào mà không cạnh nào của A đi qua, thì cạnh nhẹ nhất đi qua lát cắt đó có thể thêm vào A mà A vẫn nằm trong một cây khung nhỏ nhất. Chứng minh bằng cắt và dán: nếu cây khung nhỏ nhất T không chứa cạnh nhẹ (u, v), đường đi từ u tới v trong T phải đi qua lát cắt ở một cạnh (x, y) nào đó với w(x, y) ≥ w(u, v); đổi (x, y) lấy (u, v) được cây T′ không nặng hơn, nên T′ cũng nhỏ nhất và chứa A ∪ {(u, v)}. Trên đồ thị ví dụ với A = ∅ và S = {a, b, d, e}, cạnh (d, c) nặng 7 là cạnh nhẹ nhất trong sáu cạnh đi qua lát cắt (8, 11, 8, 7, 14, 10) và nó đúng là có mặt trong cây khung nhỏ nhất nặng 37.
2. **Thuật toán Kruskal hoạt động thế nào và tốn bao nhiêu thời gian?** Kruskal sắp xếp mọi cạnh theo trọng số không giảm, bắt đầu với |V| cây một đỉnh, rồi duyệt cạnh từ nhẹ tới nặng: cạnh nào nối hai cây khác nhau (FIND-SET(u) ≠ FIND-SET(v)) thì thêm vào và gộp hai cây bằng UNION; cạnh nào nối hai đỉnh cùng cây thì bỏ vì sẽ tạo chu trình. Với rừng tập rời nhau dùng hợp theo hạng và nén đường đi, phần tập rời nhau tốn O((V + E) α(V)), phần sắp xếp tốn O(E lg E), tổng O(E lg E) = O(E lg V) (vì |E| < |V|² nên lg |E| < 2 lg |V|). Trên đồ thị ví dụ, Kruskal thêm 8 cạnh nặng 1, 2, 2, 4, 4, 7, 8, 9 (tổng 37) và loại 6 cạnh nặng 6, 7, 8, 10, 11, 14.
3. **Thuật toán Prim hoạt động thế nào, và vì sao đống Fibonacci làm nó nhanh hơn?** Prim mọc một cây duy nhất từ gốc r. Mọi đỉnh chưa vào cây nằm trong hàng đợi ưu tiên min Q theo khoá v.key — trọng số cạnh nhẹ nhất nối v với cây hiện tại. Mỗi vòng, EXTRACT-MIN lấy ra đỉnh u có khoá nhỏ nhất (thêm cạnh (u, u.π) vào cây), rồi với mỗi đỉnh v kề u còn trong Q mà w(u, v) < v.key thì đặt v.π = u và giảm v.key xuống w(u, v). Có |V| lần EXTRACT-MIN và O(E) lần giảm khoá. Với đống nhị phân mỗi thao tác O(lg V), tổng O(V lg V + E lg V) = O(E lg V); với đống Fibonacci, EXTRACT-MIN tốn O(lg V) khấu hao còn DECREASE-KEY chỉ O(1) khấu hao, tổng O(E + V lg V). Trên đồ thị ví dụ với gốc a, các đỉnh vào cây theo thứ tự a, b, c, i, f, g, h, d, e, tổng trọng số 37. Với đồ thị dày |E| = Θ(V²), V = 1.000: đống nhị phân cỡ E lg V ≈ 10⁶ · 10 = 10⁷ bước cơ bản, đống Fibonacci cỡ E + V lg V ≈ 10⁶ + 10⁴ — nhanh hơn khoảng 10 lần (bỏ qua hằng số).

## Khái niệm cần biết

- **Đồ thị vô hướng liên thông có trọng số (connected, undirected, weighted graph):** đồ thị G = (V, E) mà giữa hai đỉnh bất kỳ có đường đi, cạnh không có hướng, mỗi cạnh (u, v) mang một số thực w(u, v) (hàm trọng số w : E → ℝ). Ví dụ: đồ thị ví dụ của chương có 9 đỉnh a..i, 14 cạnh, trọng số từ 1 tới 14. Quan trọng vì bài toán chỉ có nghĩa trên đồ thị liên thông (nếu không liên thông thì không có cây khung, chỉ có rừng khung). Trọng số được phép âm hoặc bằng 0 — mọi chứng minh trong chương không cần trọng số dương.
- **Cây khung (spanning tree):** tập cạnh T ⊆ E không có chu trình và nối mọi đỉnh của G; T luôn có đúng |V| − 1 cạnh. Ví dụ: với đồ thị ví dụ, tập {ab, bc, cd, ci, cf, de, fg, gh} là một cây khung 8 cạnh. Quan trọng vì đó là đối tượng cần tìm.
- **Cây khung nhỏ nhất (minimum spanning tree, viết tắt MST):** cây khung T có tổng trọng số w(T) = Σ_{(u,v)∈T} w(u, v) nhỏ nhất trong mọi cây khung. Ví dụ: cây trên có w(T) = 4 + 8 + 7 + 2 + 4 + 9 + 2 + 1 = 37, và không cây khung nào của đồ thị ví dụ nhẹ hơn 37. Lưu ý: "nhỏ nhất" là theo tổng trọng số, không phải theo số cạnh.
- **Thuật toán tham lam (greedy algorithm):** ở mỗi bước chọn phương án tốt nhất tại thời điểm đó và không bao giờ quay lại sửa. Ví dụ: Kruskal luôn xét cạnh nhẹ nhất còn lại. Quan trọng vì tham lam thường không tối ưu (ví dụ bài toán cái túi 0-1 ở Chương 16), nhưng với cây khung nhỏ nhất thì chứng minh được là tối ưu.
- **Cạnh an toàn (safe edge) đối với tập A:** cạnh (u, v) ∉ A mà A ∪ {(u, v)} vẫn là tập con của một cây khung nhỏ nhất nào đó. Ví dụ: với A = {gh} (cạnh nặng 1), cạnh ci nặng 2 là an toàn vì {gh, ci} nằm trong cây nặng 37 ở trên. Cạnh hi nặng 7 không an toàn với A = {gh, ci, fg, cf} vì nó tạo chu trình h–i–c–f–g–h. Quan trọng vì toàn bộ phương pháp tổng quát là "lặp lại việc thêm cạnh an toàn".
- **Lát cắt (cut) (S, V − S):** cách chia tập đỉnh V thành hai phần S và V − S. Ví dụ: S = {a, b, d, e}, V − S = {c, f, g, h, i}. Quan trọng vì lát cắt là công cụ để nhận diện cạnh an toàn.
- **Cạnh đi qua lát cắt (edge crossing a cut):** cạnh có một đầu ở S và đầu kia ở V − S. Ví dụ: với lát cắt trên, có sáu cạnh đi qua: ah 8, bh 11, bc 8, dc 7, df 14, ef 10.
- **Lát cắt tôn trọng tập A (cut respects A):** không cạnh nào của A đi qua lát cắt. Ví dụ: A = {ab, ci, cf, gh, fg} — lát cắt S = {a, b, d, e} tôn trọng A vì ab nằm trọn trong S, còn ci, cf, gh, fg nằm trọn trong V − S.
- **Cạnh nhẹ (light edge):** cạnh có trọng số nhỏ nhất trong các cạnh đi qua một lát cắt (hoặc tổng quát hơn: nhỏ nhất trong các cạnh thoả một tính chất cho trước). Có thể có nhiều cạnh nhẹ nếu bằng trọng số. Ví dụ: với lát cắt trên, cạnh nhẹ duy nhất là dc nặng 7; với lát cắt S = {a}, có hai cạnh đi qua là ab 4 và ah 8, cạnh nhẹ là ab.
- **Kỹ thuật cắt và dán (cut-and-paste):** chứng minh tính tối ưu bằng cách lấy một lời giải tối ưu T, cắt bỏ một phần và dán vào phần khác, chỉ ra kết quả không tệ hơn. Ví dụ: cây nặng 37 ở trên chứa bc 8 nhưng không chứa ah 8; thêm ah vào cây tạo chu trình a–b–c–f–g–h–a; cắt bỏ bc khỏi chu trình đó được một cây khung mới nặng 37 − 8 + 8 = 37, vẫn nhỏ nhất. Quan trọng vì là xương sống của Định lý 23.1 (kỹ thuật đã gặp ở Chương 15 và 16).
- **Rừng G_A = (V, A):** đồ thị chỉ gồm các cạnh của A trên toàn bộ tập đỉnh V; mỗi thành phần liên thông là một cây (có thể chỉ một đỉnh). Ví dụ: với A = {gh, ci, fg}, rừng có 6 cây: {g, h, f}, {c, i}, {a}, {b}, {d}, {e}. Quan trọng vì Kruskal làm việc trên chính rừng này.
- **Cấu trúc tập rời nhau (disjoint-set data structure):** quản lý một họ các tập không giao nhau với ba phép toán MAKE-SET(v) (tạo tập {v}), FIND-SET(u) (trả về phần tử đại diện của tập chứa u), UNION(u, v) (gộp hai tập chứa u và v). Với hợp theo hạng và nén đường đi, m phép toán trên n phần tử tốn O(m α(n)) (Chương 21). Ví dụ: sau UNION(g, h) và UNION(g, f), FIND-SET(f) = FIND-SET(h). Quan trọng vì Kruskal dùng nó để hỏi "hai đỉnh có cùng cây không?".
- **Hàm α(n) (nghịch đảo hàm Ackermann):** hàm tăng cực chậm; α(n) ≤ 4 với mọi n thực tế (n ≤ 10⁸⁰). Ví dụ: với đồ thị một tỷ đỉnh, α(V) vẫn ≤ 4. Quan trọng vì nó làm chi phí tập rời nhau gần như tuyến tính, nên bước sắp xếp mới chi phối thời gian của Kruskal.
- **Hàng đợi ưu tiên min (min-priority queue):** cấu trúc lưu phần tử có khoá, hỗ trợ INSERT, EXTRACT-MIN (lấy ra phần tử khoá nhỏ nhất), DECREASE-KEY (giảm khoá một phần tử). Ví dụ: Q chứa b (khoá 4), h (khoá 8), các đỉnh khác (khoá ∞): EXTRACT-MIN trả về b. Đống nhị phân: mọi thao tác O(lg n), dựng ban đầu O(n); đống Fibonacci: EXTRACT-MIN O(lg n) khấu hao, DECREASE-KEY O(1) khấu hao. Quan trọng vì Prim dùng nó, và chọn loại đống quyết định thời gian chạy.
- **Khoá v.key và cha v.π trong Prim:** v.key là trọng số cạnh nhẹ nhất nối v với một đỉnh đã ở trong cây (∞ nếu chưa có cạnh như vậy); v.π là đầu kia của cạnh đó. Ví dụ: sau khi a vào cây, b.key = 4, b.π = a; h.key = 8, h.π = a; mọi đỉnh khác khoá ∞, cha NIL. Quan trọng vì cây khung được đọc ra từ các cặp (v, v.π).
- **Co cạnh (edge contraction):** gộp hai đầu mút của một cạnh thành một đỉnh mới; các cạnh nối với hai đầu cũ trở thành cạnh nối với đỉnh mới (Mục B.4). Ví dụ: co cạnh gh trong đồ thị ví dụ được đỉnh mới {g, h} với các cạnh tới a (8), b (11), i (7 và 6 — giữ cạnh nhẹ hơn là 6 nếu chỉ giữ một), f (2). Quan trọng trong Problem 23-2 và thuật toán Borůvka.
- **Cây khung nút cổ chai (bottleneck spanning tree):** cây khung có cạnh nặng nhất nhỏ nhất có thể. Ví dụ: mọi cây khung của đồ thị ví dụ phải chứa ít nhất một cạnh nặng ≥ 9 (đỉnh e chỉ có hai cạnh: de 9, ef 10), và cây nặng 37 có cạnh nặng nhất là 9, nên giá trị nút cổ chai là 9. Quan trọng trong Problem 23-3.
- **Matroid đồ thị (graphic matroid):** cấu trúc tổ hợp (Mục 16.4) với tập nền là E và các tập "độc lập" là các tập cạnh không có chu trình (các rừng). Trên mọi matroid có trọng số, thuật toán tham lam "thêm phần tử nặng nhất mà vẫn độc lập" cho tập độc lập tối ưu. Quan trọng vì đây là lời giải thích tổng quát nhất của Ghi chú chương cho câu hỏi "vì sao tham lam đúng".

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 624–625)

Chương mở bằng một bài toán thiết kế mạch điện tử: thường cần làm cho các chân của nhiều linh kiện có cùng điện thế bằng cách nối dây chúng lại với nhau. Để nối liên thông một tập n chân, có thể dùng n − 1 sợi dây, mỗi sợi nối hai chân. Trong mọi cách bố trí như vậy, cách tốn ít dây nhất thường là cách được mong muốn nhất.

Bài toán đi dây được mô hình hoá bằng một đồ thị vô hướng, liên thông G = (V, E): V là tập các chân, E là tập các cặp chân có thể nối với nhau, và mỗi cạnh (u, v) ∈ E có trọng số w(u, v) cho biết chi phí (lượng dây cần) để nối u với v. Ta muốn tìm một tập con **không có chu trình** T ⊆ E nối tất cả các đỉnh và có tổng trọng số

```text
w(T) = Σ_{(u,v) ∈ T} w(u, v)
```

nhỏ nhất. Vì T không có chu trình và nối mọi đỉnh, T phải tạo thành một cây; ta gọi nó là **cây khung** (spanning tree) vì nó "phủ" (span) đồ thị G. Bài toán xác định cây T gọi là **bài toán cây khung nhỏ nhất** (minimum-spanning-tree problem).

Chú thích cuối trang của sách: cụm từ "cây khung nhỏ nhất" là dạng rút gọn của "cây khung có trọng số nhỏ nhất". Ta không, chẳng hạn, cực tiểu hoá số cạnh của T, vì mọi cây khung đều có đúng |V| − 1 cạnh theo Định lý B.2.

**Đồ thị ví dụ (Hình 23.1 của sách).** Đồ thị liên thông 9 đỉnh a, b, c, d, e, f, g, h, i và 14 cạnh, cùng một cây khung nhỏ nhất (tô đậm trong sách):

```text
                 8               7
          b ═══════════════ c ═══════════════ d
        ╱ │               ╱   ╲               │ ╲
     4 ╱  │            2 ╱      ╲ 4           │   ╲ 9
      ╱   │             ╱         ╲           │     ╲
     a    │ 11         i            ╲      14 │       e
      ╲   │         ╱    ╲            ╲       │     ╱
     8 ╲  │      7 ╱      ╲ 6           ╲     │   ╱ 10
        ╲ │     ╱           ╲             ╲   │ ╱
          h ═══════════════ g ═══════════════ f
                 1               2
   (cạnh vẽ nét đôi ═ nằm trong cây; các cạnh xiên ab, ci, cf, de cũng
    nằm trong cây — xem bảng dưới)
```

| Cạnh | Trọng số | Trong cây khung nhỏ nhất tô đậm? |
|---|---|---|
| (a, b) | 4 | có |
| (a, h) | 8 | không |
| (b, c) | 8 | có |
| (b, h) | 11 | không |
| (c, d) | 7 | có |
| (c, i) | 2 | có |
| (c, f) | 4 | có |
| (d, e) | 9 | có |
| (d, f) | 14 | không |
| (e, f) | 10 | không |
| (f, g) | 2 | có |
| (g, h) | 1 | có |
| (g, i) | 6 | không |
| (h, i) | 7 | không |

Tổng trọng số của cây: 4 + 8 + 7 + 2 + 4 + 9 + 2 + 1 = 37 (người tổng hợp đã cộng lại, khớp với sách). Cây khung nhỏ nhất này **không duy nhất**: bỏ cạnh (b, c) và thay bằng cạnh (a, h) được một cây khung khác cũng nặng 37. (Kiểm tra: bỏ (b, c) tách cây thành {a, b} và phần còn lại; (a, h) nối lại hai phần đó, cùng trọng số 8.)

Chương khảo sát hai thuật toán giải bài toán: **thuật toán Kruskal** và **thuật toán Prim**. Có thể dễ dàng làm cả hai chạy trong O(E lg V) bằng đống nhị phân thông thường. Dùng đống Fibonacci, thuật toán Prim chạy trong O(E + V lg V), tốt hơn bản đống nhị phân khi |V| nhỏ hơn nhiều so với |E|.

Cả hai thuật toán là thuật toán tham lam theo nghĩa của Chương 16. Mỗi bước của thuật toán tham lam phải chọn một trong nhiều phương án; chiến lược tham lam chủ trương chọn phương án tốt nhất tại thời điểm đó. Chiến lược như vậy nói chung không bảo đảm luôn tìm được lời giải tối ưu toàn cục. Tuy nhiên, với bài toán cây khung nhỏ nhất, ta chứng minh được rằng một số chiến lược tham lam nhất định cho cây khung có trọng số nhỏ nhất. Có thể đọc chương này độc lập với Chương 16, nhưng các phương pháp tham lam ở đây là một ứng dụng kinh điển của các khái niệm lý thuyết giới thiệu ở đó.

Trình tự chương: Mục 23.1 giới thiệu một phương pháp "tổng quát" mọc cây khung bằng cách thêm từng cạnh một. Mục 23.2 cho hai thuật toán cài đặt phương pháp tổng quát: thuật toán thứ nhất, của Kruskal, giống thuật toán tìm thành phần liên thông ở Mục 21.1; thuật toán thứ hai, của Prim, giống thuật toán đường đi ngắn nhất của Dijkstra (Mục 24.3).

Một quy ước: vì cây là một loại đồ thị, để chính xác phải định nghĩa cây bằng cả tập cạnh lẫn tập đỉnh. Chương này tập trung vào cây theo tập cạnh, với cách hiểu ngầm rằng các đỉnh của một cây T là những đỉnh mà ít nhất một cạnh của T chạm vào.

### 2. Mọc dần một cây khung nhỏ nhất (23.1 Growing a minimum spanning tree, trang 625–630)

Giả sử có đồ thị vô hướng liên thông G = (V, E) với hàm trọng số w : E → ℝ, và ta muốn tìm một cây khung nhỏ nhất của G. Hai thuật toán của chương đều dùng cách tiếp cận tham lam, nhưng khác nhau ở cách áp dụng.

#### Phương pháp tổng quát GENERIC-MST

Chiến lược tham lam được gói trong phương pháp tổng quát sau, mọc cây khung nhỏ nhất từng cạnh một. Phương pháp quản lý một tập cạnh A và duy trì **bất biến vòng lặp**:

> Trước mỗi lần lặp, A là tập con của một cây khung nhỏ nhất nào đó.

Ở mỗi bước, ta xác định một cạnh (u, v) có thể thêm vào A mà không phá bất biến, theo nghĩa A ∪ {(u, v)} cũng là tập con của một cây khung nhỏ nhất. Cạnh như vậy gọi là **cạnh an toàn** (safe edge) đối với A, vì có thể thêm nó vào A một cách an toàn mà vẫn giữ bất biến.

```text
GENERIC-MST(G, w)
1  A = ∅
2  while A does not form a spanning tree
3      find an edge (u, v) that is safe for A
4      A = A ∪ {(u, v)}
5  return A
```

Dòng 1: bắt đầu với tập cạnh rỗng. Dòng 2: lặp chừng nào A chưa thành cây khung. Dòng 3: tìm một cạnh an toàn — đây là chỗ khó. Dòng 4: thêm nó vào A. Dòng 5: trả về A.

Bất biến được dùng như sau:

- **Khởi tạo:** sau dòng 1, tập A = ∅ thoả bất biến một cách hiển nhiên (tập rỗng là tập con của mọi cây khung nhỏ nhất).
- **Duy trì:** vòng lặp ở dòng 2–4 giữ bất biến vì chỉ thêm cạnh an toàn.
- **Kết thúc:** mọi cạnh được thêm vào A đều nằm trong một cây khung nhỏ nhất, nên tập A trả về ở dòng 5 phải là một cây khung nhỏ nhất. (Giải thích thêm của người tổng hợp: A là cây khung, A ⊆ T với T là một cây khung nhỏ nhất; hai cây khung cùng có |V| − 1 cạnh nên A = T.)

Phần khó tất nhiên là tìm cạnh an toàn ở dòng 3. Cạnh an toàn luôn tồn tại: khi dòng 3 được thực hiện, bất biến nói có một cây khung nhỏ nhất T với A ⊆ T. Bên trong thân vòng while, A phải là tập con **thực sự** của T (vì A chưa là cây khung), nên phải có một cạnh (u, v) ∈ T với (u, v) ∉ A, và cạnh đó an toàn với A (vì A ∪ {(u, v)} ⊆ T).

Phần còn lại của mục cho một quy tắc (Định lý 23.1) để nhận diện cạnh an toàn. Mục sau mô tả hai thuật toán dùng quy tắc này để tìm cạnh an toàn một cách hiệu quả.

#### Lát cắt, cạnh đi qua lát cắt, cạnh nhẹ

Cần một số định nghĩa.

- Một **lát cắt** (cut) (S, V − S) của đồ thị vô hướng G = (V, E) là một phân hoạch của V thành hai phần.
- Cạnh (u, v) ∈ E **đi qua** (crosses) lát cắt (S, V − S) nếu một đầu mút của nó thuộc S và đầu kia thuộc V − S.
- Lát cắt **tôn trọng** (respects) một tập cạnh A nếu không cạnh nào của A đi qua lát cắt.
- Một cạnh là **cạnh nhẹ** (light edge) đi qua lát cắt nếu trọng số của nó nhỏ nhất trong mọi cạnh đi qua lát cắt. Khi có các trọng số bằng nhau, có thể có nhiều cạnh nhẹ đi qua cùng một lát cắt. Tổng quát hơn, một cạnh là cạnh nhẹ thoả một tính chất cho trước nếu trọng số của nó nhỏ nhất trong mọi cạnh thoả tính chất đó.

**Minh hoạ lát cắt (Hình 23.2 của sách)** trên đồ thị ví dụ, với S = {a, b, d, e} (đỉnh đen trong sách) và V − S = {c, f, g, h, i} (đỉnh trắng). Tập A (tô đậm) gồm các cạnh (a, b), (c, i), (c, f), (g, h), (f, g). Sách vẽ hai cách nhìn:

(a) Vẽ trên hình gốc, một đường cong uốn lượn tách đỉnh đen khỏi đỉnh trắng: cạnh đi qua lát cắt là cạnh nối một đỉnh trắng với một đỉnh đen.

(b) Vẽ lại với các đỉnh của S xếp cột bên trái và các đỉnh của V − S xếp cột bên phải, một đường thẳng đứng ở giữa; cạnh đi qua lát cắt là cạnh nối một đỉnh bên trái với một đỉnh bên phải:

```text
     S (cột trái)          │        V − S (cột phải)
                           │
     a                     │        h
     ║ 4 (thuộc A)         │        │ 7 (h–i)      h ═ g: 1 (thuộc A)
     b                     │        i
                           │        ║ 2 (c–i, thuộc A)   i – g: 6
     d                     │        c
     │ 9 (d–e)             │        ║ 4 (c–f, thuộc A)
     e                     │        f ═ g: 2 (thuộc A)
                           │
     Các cạnh nối trái sang phải (đi qua lát cắt):
     a–h 8,  b–h 11,  b–c 8,  d–c 7,  d–f 14,  e–f 10
```

Liệt kê đầy đủ cả 14 cạnh:

| Cạnh | Trọng số | Thuộc A? | Đi qua lát cắt? |
|---|---|---|---|
| (a, b) | 4 | có | không (cả hai trong S) |
| (d, e) | 9 | không | không (cả hai trong S) |
| (a, h) | 8 | không | **có** |
| (b, h) | 11 | không | **có** |
| (b, c) | 8 | không | **có** |
| (d, c) | 7 | không | **có — cạnh nhẹ duy nhất** |
| (d, f) | 14 | không | **có** |
| (e, f) | 10 | không | **có** |
| (c, i) | 2 | có | không (cả hai trong V − S) |
| (c, f) | 4 | có | không |
| (g, h) | 1 | có | không |
| (f, g) | 2 | có | không |
| (g, i) | 6 | không | không |
| (h, i) | 7 | không | không |

Sáu cạnh đi qua lát cắt có trọng số 8, 11, 8, 7, 14, 10; nhỏ nhất là 7, nên (d, c) là cạnh nhẹ duy nhất. Lát cắt tôn trọng A vì không cạnh nào của A đi qua nó.

#### Định lý 23.1 — quy tắc nhận diện cạnh an toàn

**Định lý 23.1.** Cho G = (V, E) là đồ thị vô hướng liên thông với hàm trọng số thực w xác định trên E. Cho A là một tập con của E nằm trong một cây khung nhỏ nhất nào đó của G, cho (S, V − S) là một lát cắt bất kỳ của G tôn trọng A, và cho (u, v) là một cạnh nhẹ đi qua (S, V − S). Khi đó cạnh (u, v) an toàn đối với A.

*Chứng minh.* Gọi T là một cây khung nhỏ nhất chứa A, và giả sử T không chứa cạnh nhẹ (u, v) (nếu chứa thì xong). Ta sẽ dựng một cây khung nhỏ nhất khác T′ chứa A ∪ {(u, v)} bằng kỹ thuật cắt và dán, qua đó chứng tỏ (u, v) an toàn với A.

Cạnh (u, v) tạo thành một chu trình với các cạnh trên đường đi đơn p từ u tới v trong T. Vì u và v nằm ở hai phía của lát cắt (S, V − S), ít nhất một cạnh của T vừa nằm trên đường đi đơn p vừa đi qua lát cắt. Gọi (x, y) là một cạnh như vậy. Cạnh (x, y) không thuộc A, vì lát cắt tôn trọng A. Vì (x, y) nằm trên đường đi đơn duy nhất từ u tới v trong T, bỏ (x, y) sẽ tách T thành hai thành phần. Thêm (u, v) nối lại hai thành phần đó, tạo thành cây khung mới

```text
T′ = T − {(x, y)} ∪ {(u, v)}
```

Tiếp theo chứng minh T′ là cây khung nhỏ nhất. Vì (u, v) là cạnh nhẹ đi qua (S, V − S) và (x, y) cũng đi qua lát cắt này, w(u, v) ≤ w(x, y). Do đó

```text
w(T′) = w(T) − w(x, y) + w(u, v)
      ≤ w(T)
```

Nhưng T là cây khung nhỏ nhất, nên w(T) ≤ w(T′); vậy T′ cũng phải là cây khung nhỏ nhất.

Còn phải chứng minh (u, v) thực sự an toàn với A. Ta có A ⊆ T′, vì A ⊆ T và (x, y) ∉ A; do đó A ∪ {(u, v)} ⊆ T′. Vì T′ là cây khung nhỏ nhất, (u, v) an toàn với A. ∎

**Minh hoạ chứng minh (Hình 23.3 của sách).** Hình chỉ vẽ các cạnh của cây T (không vẽ các cạnh khác của G). Đỉnh đen thuộc S, đỉnh trắng thuộc V − S; cạnh của A tô đậm; (u, v) là cạnh nhẹ đi qua lát cắt, vẽ nét đứt vì không thuộc T. Mô tả lại:

```text
   Đường đi đơn p trong T từ u tới v (đi theo chiều mũi tên của sách):

   u(đen) ── ●(đen) ══ x(đen) ── y(trắng) ══ ○(trắng) ══ v(trắng)
     ┊                                                    ┊
     └┄┄┄┄┄┄┄┄┄┄┄┄┄┄ (u, v): cạnh nhẹ, nét đứt ┄┄┄┄┄┄┄┄┄┄┄┄┘

   Các cạnh khác của T: một đỉnh trắng treo ở ●(đen) (cạnh mảnh);
   một đỉnh đen treo ở x (cạnh thuộc A); một đỉnh trắng treo ở ○(trắng)
   giữa y và v (cạnh thuộc A).

   ══ : cạnh của T thuộc A         ── : cạnh của T không thuộc A
   Cạnh (x, y) là chỗ đường đi p đổi từ đen sang trắng; nó không thuộc A
   vì lát cắt tôn trọng A.
```

Đường đi p trong T từ u (đen) tới v (trắng) phải đổi màu ít nhất một lần; chỗ đổi màu đó là cạnh (x, y). Bỏ (x, y), thêm (u, v): được T′.

**Kiểm tra trên đồ thị ví dụ (người tổng hợp):** lấy T là cây khung nhỏ nhất nặng 37 ở trên, A = {ab, ci, cf, gh, fg} như ví dụ lát cắt, S = {a, b, d, e}. Cạnh nhẹ (d, c) đã thuộc T, nên không cần đổi. Lấy một trường hợp khác: A = {(a, b)}, lát cắt S = {a, b}; cạnh đi qua: ah 8, bh 11, bc 8 — có hai cạnh nhẹ ah và bc (bằng 8). Nếu chọn (u, v) = (a, h) ∉ T: đường đi trong T từ a tới h là a–b–c–f–g–h, cạnh đầu tiên đi qua lát cắt là (b, c) nặng 8; T′ = T − {bc} ∪ {ah} nặng 37 − 8 + 8 = 37 — đúng là cây khung nhỏ nhất thứ hai mà chú thích Hình 23.1 nhắc tới.

#### Cấu trúc của tập A trong khi chạy

Định lý 23.1 giúp hiểu rõ hơn cách GENERIC-MST chạy trên đồ thị liên thông G = (V, E). Trong suốt quá trình, tập A luôn **không có chu trình**; nếu không, một cây khung nhỏ nhất chứa A sẽ chứa chu trình — mâu thuẫn. Ở bất kỳ thời điểm nào, đồ thị G_A = (V, A) là một **rừng**, và mỗi thành phần liên thông của G_A là một cây. (Một số cây có thể chỉ có một đỉnh, chẳng hạn lúc bắt đầu: A rỗng và rừng gồm |V| cây, mỗi cây một đỉnh.) Hơn nữa, mọi cạnh an toàn (u, v) với A đều nối hai thành phần **khác nhau** của G_A, vì A ∪ {(u, v)} phải không có chu trình.

Vòng while ở dòng 2–4 của GENERIC-MST chạy đúng |V| − 1 lần, vì mỗi lần lặp tìm được một trong |V| − 1 cạnh của cây khung nhỏ nhất. Ban đầu, khi A = ∅, G_A có |V| cây, và mỗi lần lặp giảm số cây đi 1. Khi rừng chỉ còn một cây, phương pháp kết thúc. Với đồ thị ví dụ: 9 cây ban đầu, 8 lần lặp.

#### Hệ quả 23.2

Hai thuật toán ở Mục 23.2 dùng hệ quả sau của Định lý 23.1.

**Hệ quả 23.2.** Cho G = (V, E) là đồ thị vô hướng liên thông với hàm trọng số thực w xác định trên E. Cho A là một tập con của E nằm trong một cây khung nhỏ nhất nào đó của G, và cho C = (V_C, E_C) là một thành phần liên thông (một cây) trong rừng G_A = (V, A). Nếu (u, v) là một cạnh nhẹ nối C với một thành phần khác trong G_A, thì (u, v) an toàn với A.

*Chứng minh.* Lát cắt (V_C, V − V_C) tôn trọng A (mọi cạnh của A hoặc nằm trong C, hoặc nằm trong thành phần khác, không cạnh nào nối C ra ngoài), và (u, v) là cạnh nhẹ của lát cắt này (mọi cạnh đi qua lát cắt đều nối C với một thành phần khác). Do đó, theo Định lý 23.1, (u, v) an toàn với A. ∎

Ví dụ (người tổng hợp): với A = {gh, ci, fg}, lấy C = {c, i}. Các cạnh nối C ra ngoài: bc 8, cd 7, cf 4, gi 6, hi 7. Cạnh nhẹ là cf nặng 4 — an toàn, và đúng là có mặt trong cây nặng 37.

#### Ví dụ hôm nay

Bài toán đi dây của phần mở đầu vẫn là ứng dụng trực tiếp: thiết kế mạng cáp quang, đường ống, lưới điện nối các trạm với chi phí xây dựng nhỏ nhất đều bắt đầu từ cây khung nhỏ nhất (thực tế thêm ràng buộc dự phòng nên thường cần nhiều hơn một cây). Trong phân tích dữ liệu, phân cụm liên kết đơn (single-linkage clustering) tương đương với chạy Kruskal rồi dừng sớm khi còn k cây — theo hiểu biết của người tổng hợp.

### 3. Thuật toán Kruskal và Prim (23.2 The algorithms of Kruskal and Prim, trang 631–638)

Hai thuật toán của mục này chi tiết hoá phương pháp tổng quát. Mỗi thuật toán dùng một quy tắc riêng để xác định cạnh an toàn ở dòng 3 của GENERIC-MST.

- Trong thuật toán Kruskal, tập A là một **rừng** có tập đỉnh là toàn bộ đỉnh của đồ thị. Cạnh an toàn thêm vào A luôn là cạnh có trọng số nhỏ nhất trong đồ thị nối hai thành phần khác nhau.
- Trong thuật toán Prim, tập A tạo thành **một cây duy nhất**. Cạnh an toàn thêm vào A luôn là cạnh có trọng số nhỏ nhất nối cây với một đỉnh chưa ở trong cây.

#### 3.1 Thuật toán Kruskal (Kruskal's algorithm)

Thuật toán Kruskal tìm cạnh an toàn để thêm vào rừng đang mọc bằng cách tìm, trong mọi cạnh nối hai cây bất kỳ của rừng, một cạnh (u, v) có trọng số nhỏ nhất. Gọi C₁ và C₂ là hai cây được (u, v) nối. Vì (u, v) phải là một cạnh nhẹ nối C₁ với một cây khác, Hệ quả 23.2 cho biết (u, v) an toàn với C₁ (nói chính xác: an toàn với A, áp dụng hệ quả với thành phần C = C₁). Thuật toán Kruskal là thuật toán tham lam vì ở mỗi bước nó thêm vào rừng một cạnh có trọng số nhỏ nhất có thể.

Cài đặt của sách giống thuật toán tính thành phần liên thông ở Mục 21.1. Nó dùng cấu trúc dữ liệu tập rời nhau để quản lý nhiều tập phần tử không giao nhau. Mỗi tập chứa các đỉnh của một cây trong rừng hiện tại. Phép toán FIND-SET(u) trả về một phần tử đại diện của tập chứa u. Như vậy, có thể xác định hai đỉnh u và v có cùng một cây hay không bằng cách kiểm tra FIND-SET(u) có bằng FIND-SET(v) không. Để gộp hai cây, thuật toán gọi thủ tục UNION.

```text
MST-KRUSKAL(G, w)
1  A = ∅
2  for each vertex v ∈ G.V
3      MAKE-SET(v)
4  sort the edges of G.E into nondecreasing order by weight w
5  for each edge (u, v) ∈ G.E, taken in nondecreasing order by weight
6      if FIND-SET(u) ≠ FIND-SET(v)
7          A = A ∪ {(u, v)}
8          UNION(u, v)
9  return A
```

Giải thích: dòng 1–3 khởi tạo A là tập rỗng và tạo |V| cây, mỗi cây chứa một đỉnh. Dòng 4 sắp xếp các cạnh theo thứ tự trọng số không giảm. Vòng for ở dòng 5–8 xét các cạnh theo thứ tự trọng số từ nhỏ tới lớn. Với mỗi cạnh (u, v), vòng lặp kiểm tra hai đầu mút u và v có cùng một cây không. Nếu cùng, cạnh (u, v) không thể thêm vào rừng mà không tạo chu trình, nên bị bỏ qua. Nếu không, hai đỉnh thuộc hai cây khác nhau; khi đó dòng 7 thêm (u, v) vào A và dòng 8 gộp các đỉnh của hai cây.

**Ví dụ chạy tay Kruskal trên đồ thị ví dụ (Hình 23.4 của sách, 14 bước (a)–(n)).** Thứ tự cạnh sau khi sắp xếp (cách phá hoà mà sách dùng đọc từ hình): gh 1, ci 2, fg 2, ab 4, cf 4, gi 6, cd 7, hi 7, ah 8, bc 8, de 9, ef 10, bh 11, df 14. Trong hình gốc, mũi tên chỉ cạnh đang xét và cạnh tô đậm thuộc rừng A.

| Bước | Cạnh xét | Trọng số | Hai đầu cùng cây? | Hành động | Các cây của rừng sau bước (chỉ ghi cây ≥ 2 đỉnh) |
|---|---|---|---|---|---|
| (a) | (h, g) | 1 | không | thêm | {g, h} |
| (b) | (c, i) | 2 | không | thêm | {g, h}, {c, i} |
| (c) | (g, f) | 2 | không | thêm | {f, g, h}, {c, i} |
| (d) | (a, b) | 4 | không | thêm | {f, g, h}, {c, i}, {a, b} |
| (e) | (c, f) | 4 | không | thêm | {c, f, g, h, i}, {a, b} |
| (f) | (i, g) | 6 | **có** (cùng cây {c, f, g, h, i}) | bỏ | không đổi |
| (g) | (c, d) | 7 | không | thêm | {c, d, f, g, h, i}, {a, b} |
| (h) | (h, i) | 7 | **có** | bỏ | không đổi |
| (i) | (a, h) | 8 | không | thêm | {a, b, c, d, f, g, h, i} |
| (j) | (b, c) | 8 | **có** | bỏ | không đổi |
| (k) | (d, e) | 9 | không | thêm | {a, b, c, d, e, f, g, h, i} — một cây |
| (l) | (e, f) | 10 | **có** | bỏ | không đổi |
| (m) | (b, h) | 11 | **có** | bỏ | không đổi |
| (n) | (d, f) | 14 | **có** | bỏ | không đổi |

Kết quả: A = {gh, ci, fg, ab, cf, cd, ah, de}, 8 cạnh, tổng 1 + 2 + 2 + 4 + 4 + 7 + 8 + 9 = 37 (người tổng hợp đã cộng lại). Hai nhận xét:

- Cây Kruskal trả về chứa (a, h) chứ **không** chứa (b, c) — khác cây tô đậm ở hình đồ thị ví dụ, nhưng cùng nặng 37. Lý do: (a, h) và (b, c) cùng nặng 8, và cách sắp xếp của sách đặt (a, h) trước. Nếu đặt (b, c) trước, Kruskal sẽ trả về đúng cây của hình đồ thị ví dụ. Đây chính là nội dung Exercise 23.2-1.
- Thuật toán đã có cây khung sau bước (k) nhưng vẫn xét nốt ba cạnh còn lại. Một cài đặt thực tế có thể dừng khi đã thêm |V| − 1 cạnh; pseudocode của sách không làm vậy, nhưng điều đó không đổi bậc tiệm cận.

**Thời gian chạy của Kruskal.** Thời gian chạy trên đồ thị G = (V, E) phụ thuộc cách cài đặt cấu trúc tập rời nhau. Giả sử dùng rừng tập rời nhau của Mục 21.3 với hai kỹ thuật hợp theo hạng (union by rank) và nén đường đi (path compression), vì đó là cài đặt nhanh nhất về tiệm cận đã biết.

- Khởi tạo A ở dòng 1: O(1).
- Sắp xếp cạnh ở dòng 4: O(E lg E).
- Vòng for dòng 5–8 thực hiện O(E) phép FIND-SET và UNION trên rừng tập rời nhau. Cùng với |V| phép MAKE-SET (dòng 2–3), tổng cộng O((V + E) α(V)), với α là hàm tăng cực chậm định nghĩa ở Mục 21.4.
- Vì G liên thông, |E| ≥ |V| − 1, nên các phép toán tập rời nhau tốn O(E α(V)).
- Hơn nữa, vì α(|V|) = O(lg V) = O(lg E), tổng thời gian của Kruskal là O(E lg E).
- Nhận xét |E| < |V|², nên lg |E| = O(lg V), và có thể viết lại thời gian của Kruskal là **O(E lg V)**.

Kiểm tra số (người tổng hợp): đồ thị ví dụ có |E| = 14, lg 14 ≈ 3,8; |V| = 9, lg 9 ≈ 3,2; lg |E| < 2 lg |V| = 6,3 đúng như lập luận. Khi các trọng số đã sắp sẵn (hoặc sắp được trong thời gian tuyến tính, ví dụ trọng số nguyên nhỏ), Kruskal chỉ còn O(E α(V)) — xem Exercise 23.2-4.

#### 3.2 Thuật toán Prim (Prim's algorithm)

Giống Kruskal, thuật toán Prim là một trường hợp riêng của phương pháp tổng quát ở Mục 23.1. Prim hoạt động rất giống thuật toán Dijkstra tìm đường đi ngắn nhất (Mục 24.3). Tính chất của Prim là các cạnh trong A luôn tạo thành **một cây duy nhất**. Cây bắt đầu từ một đỉnh gốc r tuỳ ý và lớn dần cho tới khi phủ mọi đỉnh của V. Mỗi bước thêm vào cây A một cạnh nhẹ nối A với một **đỉnh cô lập** (isolated vertex) — đỉnh mà chưa cạnh nào của A chạm vào. Theo Hệ quả 23.2 (áp dụng với C là cây đang mọc), quy tắc này chỉ thêm các cạnh an toàn với A; vì vậy khi thuật toán kết thúc, các cạnh trong A tạo thành một cây khung nhỏ nhất. Chiến lược này là tham lam vì ở mỗi bước nó thêm vào cây một cạnh làm tăng trọng số của cây ít nhất có thể.

Để cài đặt Prim hiệu quả, cần một cách nhanh để chọn cạnh mới thêm vào cây tạo bởi các cạnh trong A. Trong pseudocode dưới đây, đồ thị liên thông G và gốc r của cây khung nhỏ nhất cần mọc là đầu vào. Trong khi chạy, mọi đỉnh **chưa** ở trong cây nằm trong một hàng đợi ưu tiên min Q dựa trên thuộc tính *key*. Với mỗi đỉnh v, thuộc tính v.key là trọng số nhỏ nhất của một cạnh nối v với một đỉnh trong cây; theo quy ước, v.key = ∞ nếu không có cạnh như vậy. Thuộc tính v.π là cha của v trong cây. Thuật toán ngầm duy trì tập A của GENERIC-MST dưới dạng

```text
A = { (v, v.π) : v ∈ V − {r} − Q }
```

Khi thuật toán kết thúc, hàng đợi ưu tiên min Q rỗng; cây khung nhỏ nhất A của G vì vậy là

```text
A = { (v, v.π) : v ∈ V − {r} }
```

```text
MST-PRIM(G, w, r)
 1  for each u ∈ G.V
 2      u.key = ∞
 3      u.π = NIL
 4  r.key = 0
 5  Q = G.V
 6  while Q ≠ ∅
 7      u = EXTRACT-MIN(Q)
 8      for each v ∈ G.Adj[u]
 9          if v ∈ Q and w(u, v) < v.key
10              v.π = u
11              v.key = w(u, v)
```

Giải thích: dòng 1–5 đặt khoá của mọi đỉnh bằng ∞ (trừ gốc r, khoá đặt bằng 0 để r là đỉnh được xử lý đầu tiên), đặt cha của mọi đỉnh là NIL, và khởi tạo hàng đợi ưu tiên min Q chứa mọi đỉnh. Dòng 7 lấy ra đỉnh u có khoá nhỏ nhất. Dòng 8–11 duyệt các đỉnh kề v của u; nếu v chưa vào cây và cạnh (u, v) nhẹ hơn khoá hiện tại của v, thì cập nhật cha và khoá của v.

**Bất biến vòng lặp ba phần.** Trước mỗi lần lặp của vòng while ở dòng 6–11:

1. A = {(v, v.π) : v ∈ V − {r} − Q}.
2. Các đỉnh đã được đặt vào cây khung nhỏ nhất là các đỉnh trong V − Q.
3. Với mọi đỉnh v ∈ Q, nếu v.π ≠ NIL thì v.key < ∞ và v.key là trọng số của một cạnh nhẹ (v, v.π) nối v với một đỉnh nào đó đã được đặt vào cây khung nhỏ nhất.

Dòng 7 xác định một đỉnh u ∈ Q chạm vào một cạnh nhẹ đi qua lát cắt (V − Q, Q) (trừ lần lặp đầu tiên, khi u = r do dòng 4). Lấy u ra khỏi Q là thêm u vào tập V − Q các đỉnh trong cây, tức là thêm cạnh (u, u.π) vào A. Vòng for ở dòng 8–11 cập nhật thuộc tính *key* và π của mọi đỉnh v kề u mà chưa ở trong cây, nhờ đó duy trì phần thứ ba của bất biến.

**Ví dụ chạy tay Prim trên đồ thị ví dụ với gốc a (Hình 23.5 của sách, 9 bước (a)–(i)).** Trong hình gốc, đỉnh đen là đỉnh đã ở trong cây, cạnh tô đậm thuộc cây đang mọc; ở mỗi bước, các đỉnh trong cây xác định một lát cắt và một cạnh nhẹ đi qua lát cắt được thêm vào cây. Sách không ghi khoá; bảng dưới do người tổng hợp tính lại, ghi khoá các đỉnh còn trong Q **ngay trước** EXTRACT-MIN (dạng khoá/cha; "∞" nghĩa là khoá ∞, cha NIL):

| Bước | b | c | d | e | f | g | h | i | Đỉnh lấy ra (cạnh thêm vào cây) |
|---|---|---|---|---|---|---|---|---|---|
| (a) | ∞ | ∞ | ∞ | ∞ | ∞ | ∞ | ∞ | ∞ | a, khoá 0 (gốc, chưa thêm cạnh) |
| (b) | 4/a | ∞ | ∞ | ∞ | ∞ | ∞ | 8/a | ∞ | b, cạnh (a, b) 4 |
| (c) | — | 8/b | ∞ | ∞ | ∞ | ∞ | 8/a | ∞ | c, cạnh (b, c) 8 (hoà với h, sách chọn c) |
| (d) | — | — | 7/c | ∞ | 4/c | ∞ | 8/a | 2/c | i, cạnh (c, i) 2 |
| (e) | — | — | 7/c | ∞ | 4/c | 6/i | 7/i | — | f, cạnh (c, f) 4 |
| (f) | — | — | 7/c | 10/f | — | 2/f | 7/i | — | g, cạnh (f, g) 2 |
| (g) | — | — | 7/c | 10/f | — | — | 1/g | — | h, cạnh (g, h) 1 |
| (h) | — | — | 7/c | 10/f | — | — | — | — | d, cạnh (c, d) 7 |
| (i) | — | — | — | 9/d | — | — | — | — | e, cạnh (d, e) 9 |

Giải thích từng lần cập nhật khoá (dòng 9–11):
- Lấy a: b.key = 4 (cạnh ab), h.key = 8 (cạnh ah).
- Lấy b: c.key = 8 (cạnh bc); cạnh bh nặng 11 không nhỏ hơn h.key = 8 nên không cập nhật.
- Lấy c (khoá 8, hoà với h khoá 8 — chú thích hình của sách nói ở bước thứ hai thuật toán có thể chọn (b, c) hoặc (a, h) vì cả hai đều là cạnh nhẹ đi qua lát cắt): d.key = 7, f.key = 4, i.key = 2.
- Lấy i: g.key = 6 (cạnh ig); h.key giảm từ 8 xuống 7 (cạnh ih), h.π đổi từ a thành i.
- Lấy f: e.key = 10 (cạnh fe); g.key giảm từ 6 xuống 2 (cạnh fg), g.π = f; cạnh fd nặng 14 không nhỏ hơn d.key = 7.
- Lấy g: h.key giảm từ 7 xuống 1 (cạnh gh), h.π = g.
- Lấy h: mọi đỉnh kề h (a, b, g, i) đã ở trong cây, không cập nhật.
- Lấy d: e.key giảm từ 10 xuống 9 (cạnh de), e.π = d.
- Lấy e: Q rỗng, kết thúc.

Kết quả A = {(b, a), (c, b), (i, c), (f, c), (g, f), (h, g), (d, c), (e, d)}, tổng 4 + 8 + 2 + 4 + 2 + 1 + 7 + 9 = 37 — trùng với cây tô đậm ở hình đồ thị ví dụ (chứa (b, c), không chứa (a, h)). Thứ tự các đỉnh vào cây a, b, c, i, f, g, h, d, e khớp với chín hình (a)–(i) của sách. Ví dụ này cũng cho thấy khoá của một đỉnh có thể giảm nhiều lần (h: ∞ → 8 → 7 → 1) — đó là lý do DECREASE-KEY nhanh quan trọng.

**Thời gian chạy của Prim** phụ thuộc cách cài đặt hàng đợi ưu tiên min Q.

*Với đống nhị phân min (Chương 6):*
- Dùng thủ tục BUILD-MIN-HEAP để thực hiện dòng 1–5 trong O(V).
- Thân vòng while chạy |V| lần, và mỗi EXTRACT-MIN tốn O(lg V), nên tổng thời gian mọi lời gọi EXTRACT-MIN là O(V lg V).
- Vòng for ở dòng 8–11 chạy tổng cộng O(E) lần, vì tổng độ dài các danh sách kề là 2|E|.
- Trong vòng for, có thể kiểm tra "v ∈ Q" ở dòng 9 trong thời gian hằng số bằng cách giữ một bit cho mỗi đỉnh cho biết nó còn trong Q không, và cập nhật bit khi đỉnh bị lấy khỏi Q.
- Phép gán ở dòng 11 ngầm chứa một phép DECREASE-KEY trên đống min, mà đống nhị phân hỗ trợ trong O(lg V).
- Tổng: O(V lg V + E lg V) = **O(E lg V)**, bằng tiệm cận với cài đặt Kruskal ở trên.

*Với đống Fibonacci (Chương 19):* nếu đống Fibonacci chứa |V| phần tử, EXTRACT-MIN tốn O(lg V) thời gian khấu hao và DECREASE-KEY (để cài đặt dòng 11) tốn O(1) thời gian khấu hao. Vì vậy, dùng đống Fibonacci cho Q, thời gian của Prim cải thiện thành **O(E + V lg V)**.

So sánh số (người tổng hợp), bỏ qua hằng số, V = 10⁴:

| Loại đồ thị | |E| | Đống nhị phân E lg V | Đống Fibonacci E + V lg V |
|---|---|---|---|
| thưa, |E| = 3V | 3 · 10⁴ | ≈ 4,0 · 10⁵ | ≈ 1,6 · 10⁵ |
| dày vừa, |E| = V lg V | ≈ 1,3 · 10⁵ | ≈ 1,8 · 10⁶ | ≈ 2,7 · 10⁵ |
| dày, |E| = V²/2 | 5 · 10⁷ | ≈ 6,6 · 10⁸ | ≈ 5,0 · 10⁷ |

(lg 10⁴ ≈ 13,3.) Với đồ thị thưa |E| = Θ(V), hai cách cùng bậc Θ(V lg V); khoảng cách tăng dần khi đồ thị dày lên (Exercise 23.2-3).

#### Ví dụ hôm nay

Thư viện đồ thị phổ biến thường cài cả hai: Kruskal tiện khi đồ thị cho dưới dạng danh sách cạnh (chỉ cần sắp xếp và một cấu trúc tập rời nhau vài dòng code); Prim tiện khi đồ thị cho dưới dạng danh sách kề hoặc ma trận kề. Trong thực tế, hầu như không ai dùng đống Fibonacci: cài đặt Prim phổ biến dùng đống nhị phân với "xoá lười" (đẩy cặp (khoá, đỉnh) mới vào đống thay vì DECREASE-KEY, bỏ qua phần tử cũ khi lấy ra), thời gian O(E lg E) = O(E lg V) — theo hiểu biết của người tổng hợp.

## Bài tập và bài toán cuối chương

### Bài tập Mục 23.1 (trang 629–630)

- **23.1-1:** Cho (u, v) là một cạnh có trọng số nhỏ nhất trong đồ thị liên thông G. Chứng minh (u, v) thuộc một cây khung nhỏ nhất nào đó của G. *Lời giải của người tổng hợp:* áp dụng Định lý 23.1 với A = ∅ (nằm trong mọi cây khung nhỏ nhất) và lát cắt ({u}, V − {u}) (tôn trọng ∅). Cạnh (u, v) đi qua lát cắt và nhẹ nhất trong toàn đồ thị, nên nhẹ nhất trong các cạnh đi qua — là cạnh nhẹ, do đó an toàn với ∅, tức là nằm trong một cây khung nhỏ nhất. Ví dụ: (g, h) nặng 1 trong đồ thị ví dụ.
- **23.1-2:** Giáo sư Sabatier phỏng đoán mệnh đề đảo của Định lý 23.1: với A nằm trong một cây khung nhỏ nhất, lát cắt (S, V − S) tôn trọng A, và (u, v) là một cạnh **an toàn** với A đi qua lát cắt, thì (u, v) là cạnh nhẹ của lát cắt. Chỉ ra phỏng đoán sai bằng phản ví dụ. *Lời giải của người tổng hợp:* đồ thị ba đỉnh a, b, c với ab 1, ac 2, bc 3. Cây khung nhỏ nhất duy nhất là {ab, ac}, nặng 3. Lấy A = ∅, lát cắt ({a}, {b, c}). Cạnh ac nặng 2 an toàn với ∅ (thuộc cây khung nhỏ nhất) và đi qua lát cắt, nhưng cạnh nhẹ của lát cắt là ab nặng 1.
- **23.1-3:** Chứng minh nếu cạnh (u, v) nằm trong một cây khung nhỏ nhất thì nó là cạnh nhẹ đi qua một lát cắt nào đó của đồ thị. *Lời giải:* gọi T là cây khung nhỏ nhất chứa (u, v). Bỏ (u, v) khỏi T tách T thành hai cây với tập đỉnh S (chứa u) và V − S (chứa v). Nếu có cạnh (x, y) đi qua lát cắt này với w(x, y) < w(u, v), thì T − {(u, v)} ∪ {(x, y)} là cây khung nhẹ hơn T — mâu thuẫn. Vậy (u, v) là cạnh nhẹ của lát cắt (S, V − S).
- **23.1-4:** Cho một ví dụ đơn giản về đồ thị liên thông sao cho tập {(u, v) : tồn tại lát cắt (S, V − S) mà (u, v) là cạnh nhẹ đi qua (S, V − S)} không tạo thành cây khung nhỏ nhất. *Lời giải:* tam giác ba cạnh cùng nặng 1. Mỗi cạnh là cạnh nhẹ (hoà) của lát cắt tách một đầu mút của nó ra; tập hợp gồm cả ba cạnh, tạo chu trình, không phải cây.
- **23.1-5:** Cho e là cạnh nặng nhất trên một chu trình nào đó của đồ thị liên thông G = (V, E). Chứng minh có một cây khung nhỏ nhất của G′ = (V, E − {e}) cũng là cây khung nhỏ nhất của G; tức là G có một cây khung nhỏ nhất không chứa e. *Lời giải:* lấy T là cây khung nhỏ nhất của G. Nếu e ∉ T thì xong. Nếu e = (u, v) ∈ T, bỏ e tách T thành hai phần; chu trình chứa e còn phải đi qua lát cắt này ở ít nhất một cạnh khác e′, với w(e′) ≤ w(e) vì e nặng nhất trên chu trình. T′ = T − {e} ∪ {e′} là cây khung, w(T′) ≤ w(T), nên T′ nhỏ nhất và không chứa e. Vì mọi cây khung của G′ cũng là cây khung của G, T′ là cây khung nhỏ nhất của G′. Tính chất này thường gọi là "tính chất chu trình" (cycle property).
- **23.1-6:** Chứng minh nếu với mọi lát cắt của đồ thị đều có duy nhất một cạnh nhẹ đi qua, thì đồ thị có duy nhất một cây khung nhỏ nhất. Chỉ ra mệnh đề đảo sai bằng phản ví dụ. *Lời giải:* giả sử có hai cây khung nhỏ nhất khác nhau T và T′. Lấy cạnh e = (u, v) ∈ T − T′. Bỏ e khỏi T cho lát cắt (S, V − S). Theo Bài tập 23.1-3, e là cạnh nhẹ của lát cắt này, và theo giả thiết là cạnh nhẹ duy nhất, nên mọi cạnh khác đi qua lát cắt nặng hơn hẳn e. Đường đi từ u tới v trong T′ đi qua lát cắt ở một cạnh e″ ≠ e (vì e ∉ T′), w(e″) > w(e). Khi đó T′ − {e″} ∪ {e} là cây khung nhẹ hơn T′ — mâu thuẫn. Phản ví dụ cho mệnh đề đảo: đồ thị chỉ có hai cạnh ab 1, bc 1 (bản thân là một cây, nên cây khung nhỏ nhất duy nhất), nhưng lát cắt ({b}, {a, c}) có hai cạnh nhẹ.
- **23.1-7:** Lập luận rằng nếu mọi trọng số đều dương, thì mọi tập cạnh nối được mọi đỉnh và có tổng trọng số nhỏ nhất phải là một cây. Cho ví dụ chứng tỏ kết luận không còn đúng nếu cho phép trọng số không dương. *Lời giải:* nếu tập cạnh liên thông đó có chu trình, bỏ một cạnh trên chu trình vẫn liên thông và tổng giảm hẳn (trọng số dương) — mâu thuẫn với tính nhỏ nhất; vậy không có chu trình, tức là cây. Ví dụ ngược: tam giác ba cạnh nặng −1: tập cả ba cạnh nặng −3, nhỏ hơn mọi cây khung (−2), và nó không phải cây. (Với trọng số 0, tập có chu trình có thể có cùng tổng nhỏ nhất với cây, nên "mọi tập nhỏ nhất đều là cây" cũng sai.)
- **23.1-8:** Cho T là cây khung nhỏ nhất của G và L là danh sách đã sắp xếp các trọng số cạnh của T. Chứng minh với mọi cây khung nhỏ nhất T′ khác của G, L cũng là danh sách đã sắp xếp các trọng số cạnh của T′. *Lời giải của người tổng hợp:* với mỗi ngưỡng x, gọi G_x là đồ thị con gồm mọi cạnh nặng ≤ x, có c(x) thành phần liên thông. Chứng minh mọi cây khung nhỏ nhất có đúng |V| − c(x) cạnh nặng ≤ x: các cạnh đó tạo rừng trong G_x nên không quá |V| − c(x); nếu ít hơn, có hai mảnh của một thành phần của G_x không được nối bởi cạnh ≤ x của cây, lấy một cạnh e ≤ x của G_x nối hai mảnh đó, thêm e vào cây tạo chu trình chứa một cạnh nặng > x, đổi được cây nhẹ hơn — mâu thuẫn. Số cạnh ≤ x đúng bằng nhau với mọi x, nên hai danh sách trọng số trùng nhau. (Cách khác: Kruskal với các cách phá hoà khác nhau, Bài tập 23.2-1.) Ví dụ: hai cây khung nhỏ nhất của đồ thị ví dụ (chứa bc hoặc chứa ah) cùng có danh sách 1, 2, 2, 4, 4, 7, 8, 9.
- **23.1-9:** Cho T là cây khung nhỏ nhất của G = (V, E), V′ ⊆ V. Gọi T′ là đồ thị con của T cảm sinh bởi V′, G′ là đồ thị con của G cảm sinh bởi V′. Chứng minh nếu T′ liên thông thì T′ là cây khung nhỏ nhất của G′. *Lời giải:* T′ liên thông và không chu trình nên là cây khung của G′. Nếu G′ có cây khung T″ nhẹ hơn T′, thì (T − T′) ∪ T″ vẫn là cây khung của G (thay một cây con liên thông trên V′ bằng một cây khác trên cùng V′ không làm mất liên thông, số cạnh giữ nguyên |V| − 1) và nhẹ hơn T — mâu thuẫn.
- **23.1-10:** Cho G và cây khung nhỏ nhất T; giảm trọng số của một cạnh **trong** T. Chứng minh T vẫn là cây khung nhỏ nhất. Hình thức: chọn (x, y) ∈ T và số dương k, định nghĩa

  ```text
  w′(u, v) = w(u, v)        nếu (u, v) ≠ (x, y)
  w′(u, v) = w(x, y) − k    nếu (u, v) = (x, y)
  ```
  Chứng minh T là cây khung nhỏ nhất của G với trọng số w′. *Lời giải:* với mọi cây khung T″: w′(T″) ≥ w(T″) − k ≥ w(T) − k = w′(T) (bất đẳng thức đầu vì T″ chứa (x, y) thì giảm đúng k, không chứa thì không giảm).
- **23.1-11 ★:** Cho G và cây khung nhỏ nhất T; giảm trọng số của một cạnh **không thuộc** T. Cho thuật toán tìm cây khung nhỏ nhất của đồ thị đã sửa. *Lời giải của người tổng hợp:* gọi cạnh đó là (x, y) với trọng số mới w′. Thêm (x, y) vào T tạo đúng một chu trình (đường đi x–y trong T cộng cạnh mới). Tìm cạnh nặng nhất e trên chu trình (DFS/BFS trên T, O(V)). Nếu e = (x, y) thì T giữ nguyên; nếu không, cây mới là T − {e} ∪ {(x, y)}. Đúng vì mọi cạnh khác ngoài T vẫn là cạnh nặng nhất trên một chu trình (tính chất chu trình, Bài tập 23.1-5). Thời gian O(V).

### Bài tập Mục 23.2 (trang 637–638)

- **23.2-1:** Kruskal có thể trả về các cây khung khác nhau cho cùng một đồ thị tuỳ cách phá hoà khi sắp xếp. Chứng minh với mỗi cây khung nhỏ nhất T của G, có một cách sắp xếp cạnh làm Kruskal trả về đúng T. *Lời giải:* sắp xếp theo trọng số, và trong các cạnh cùng trọng số, đặt các cạnh của T trước. Chứng minh bằng quy nạp rằng sau khi xử lý mọi cạnh nặng ≤ x, rừng của Kruskal bằng tập cạnh của T nặng ≤ x: cạnh của T không bao giờ tạo chu trình với các cạnh T đã có; cạnh không thuộc T cùng trọng số x, xét sau các cạnh T nặng x, nếu nối hai cây khác nhau thì (theo lập luận đếm của Bài tập 23.1-8) T sẽ có ít cạnh ≤ x hơn mức cần — mâu thuẫn. Ví dụ: trên đồ thị ví dụ, đặt (b, c) trước (a, h) thì Kruskal trả về cây chứa (b, c).
- **23.2-2:** Đồ thị biểu diễn bằng ma trận kề. Cho cài đặt Prim đơn giản chạy O(V²). *Lời giải:* bỏ đống, dùng mảng key[1..V] và mảng bit inTree. Mỗi vòng: quét tuyến tính tìm đỉnh ngoài cây có khoá nhỏ nhất (O(V)), đưa vào cây, rồi quét hàng tương ứng của ma trận để cập nhật khoá (O(V)). |V| vòng, tổng O(V²) — tối ưu với đồ thị dày.
- **23.2-3:** Với đồ thị thưa |E| = Θ(V), Prim dùng đống Fibonacci có nhanh hơn tiệm cận bản đống nhị phân không? Với đồ thị dày |E| = Θ(V²) thì sao? |E| và |V| phải liên hệ thế nào để bản đống Fibonacci nhanh hơn tiệm cận? *Lời giải:* thưa: O(V lg V) so với O(V lg V) — không nhanh hơn. Dày: O(V²) so với O(V² lg V) — nhanh hơn hệ số lg V. Tổng quát: E lg V so với E + V lg V; bản Fibonacci nhanh hơn tiệm cận khi và chỉ khi |E| = ω(V), tức |E|/|V| → ∞.
- **23.2-4:** Mọi trọng số là số nguyên từ 1 tới |V|. Có thể làm Kruskal nhanh tới mức nào? Nếu trọng số là số nguyên từ 1 tới W với W là hằng số? *Lời giải:* sắp xếp đếm (counting sort, Chương 8) trong O(V + E) = O(E); phần còn lại O(E α(V)). Tổng O(E α(V)) cho cả hai trường hợp.
- **23.2-5:** Câu hỏi tương tự cho Prim. *Lời giải của người tổng hợp:* trọng số 1..|V|: dùng cây van Emde Boas (Chương 20) trên vũ trụ khoá cỡ |V| (cần xử lý nhiều đỉnh cùng khoá, ví dụ mỗi khoá một danh sách đỉnh), EXTRACT-MIN và DECREASE-KEY đều O(lg lg V), tổng O(E lg lg V). Trọng số 1..W, W hằng: dùng mảng W + 2 "xô" (khoá 1..W và ∞), mỗi xô là danh sách liên kết đôi; DECREASE-KEY là chuyển đỉnh sang xô khác O(1), EXTRACT-MIN quét W + 2 xô O(1); tổng O(V + E) = O(E).
- **23.2-6 ★:** Trọng số phân phối đều trên nửa khoảng [0, 1). Thuật toán nào, Kruskal hay Prim, có thể làm chạy nhanh hơn? *Lời giải của người tổng hợp:* Kruskal: dùng sắp xếp theo xô (bucket sort, Mục 8.4) sắp các cạnh trong thời gian kỳ vọng O(E), phần tập rời nhau O(E α(V)), tổng kỳ vọng O(E α(V)). Prim không hưởng lợi tương tự dễ dàng vì khoá trong hàng đợi thay đổi động.
- **23.2-7 ★:** G đã có cây khung nhỏ nhất. Cập nhật nhanh tới đâu nếu thêm một đỉnh mới cùng các cạnh chạm nó? *Lời giải của người tổng hợp:* theo tính chất chu trình, mọi cạnh cũ không thuộc cây không bao giờ cần dùng lại. Cây khung nhỏ nhất mới là cây khung nhỏ nhất của đồ thị gồm cây cũ (|V| − 1 cạnh) cộng các cạnh mới (≤ |V| cạnh): chạy Prim hoặc Kruskal trên đồ thị O(V) cạnh này tốn O(V lg V). Có thể đạt O(V) bằng cách thêm từng cạnh mới và loại cạnh nặng nhất trên chu trình tạo ra, làm khéo bằng một lần DFS — theo hiểu biết của người tổng hợp.
- **23.2-8:** Giáo sư Borden đề xuất thuật toán chia để trị: chia V thành V₁, V₂ có kích thước chênh nhau không quá 1; E₁ (E₂) là các cạnh chỉ chạm đỉnh trong V₁ (V₂); đệ quy tìm cây khung nhỏ nhất của G₁ = (V₁, E₁) và G₂ = (V₂, E₂); cuối cùng chọn cạnh nhẹ nhất trong E đi qua lát cắt (V₁, V₂) để nối hai cây. Thuật toán đúng hay sai? *Lời giải:* sai. Phản ví dụ: V₁ = {a}, V₂ = {b, c}, cạnh ab 1, ac 1, bc 10. Thuật toán lấy bc 10 trong G₂ và một cạnh nặng 1 qua lát cắt: tổng 11. Cây khung nhỏ nhất thật {ab, ac} nặng 2. Lỗi: cây khung nhỏ nhất không nhất thiết cảm sinh cây khung nhỏ nhất (hay thậm chí cây liên thông) trên mỗi nửa.

### Problem 23-1: Cây khung nhỏ thứ hai (Second-best minimum spanning tree)

Cho G = (V, E) vô hướng liên thông, hàm trọng số w : E → ℝ, giả sử |E| ≥ |V| và mọi trọng số đôi một khác nhau. Định nghĩa: gọi 𝒯 là tập mọi cây khung của G, T′ là một cây khung nhỏ nhất của G. **Cây khung nhỏ thứ hai** (second-best minimum spanning tree) là cây khung T sao cho w(T) = min_{T″ ∈ 𝒯 − {T′}} {w(T″)}.

- **(a)** Chứng minh cây khung nhỏ nhất là duy nhất, nhưng cây khung nhỏ thứ hai không nhất thiết duy nhất. *Lời giải của người tổng hợp:* trọng số khác nhau ⇒ mỗi lát cắt có duy nhất một cạnh nhẹ ⇒ cây khung nhỏ nhất duy nhất (Bài tập 23.1-6). Phản ví dụ cho cây nhỏ thứ hai: hai tam giác chung đỉnh c — tam giác a, b, c với ab 1, bc 2, ac 4; tam giác c, d, e với cd 3, de 5, ce 7. Cây nhỏ nhất {ab, bc, cd, de} nặng 11. Hai cây {ab, ac, cd, de} và {ab, bc, cd, ce} cùng nặng 13; mọi cây khung khác nặng ít nhất 14. Vậy có hai cây nhỏ thứ hai.
- **(b)** Cho T là cây khung nhỏ nhất. Chứng minh G có cạnh (u, v) ∈ T và (x, y) ∉ T sao cho T − {(u, v)} ∪ {(x, y)} là cây khung nhỏ thứ hai. *Ý của người tổng hợp:* lấy T₂ là một cây nhỏ thứ hai. Giả sử T₂ khác T ở từ hai cạnh trở lên. Lấy (x, y) ∈ T₂ − T; thêm (x, y) vào T tạo một chu trình, trên đó có cạnh (u, v) ∈ T − T₂ với w(u, v) < w(x, y) (tính chất chu trình cộng trọng số khác nhau). Cây T − {(u, v)} ∪ {(x, y)} khác T, và bằng lập luận đổi cạnh tương tự (đổi một cạnh của T₂ − T lấy cạnh nhẹ hơn của T) có thể chỉ ra nó không nặng hơn T₂. Vậy luôn có một cây nhỏ thứ hai chỉ khác T đúng một cạnh.
- **(c)** Cho T là một cây khung, với hai đỉnh u, v gọi max[u, v] là cạnh nặng nhất trên đường đi đơn duy nhất giữa u và v trong T. Mô tả thuật toán O(V²) tính max[u, v] cho mọi u, v. *Lời giải:* từ mỗi đỉnh u, chạy BFS/DFS trên T; khi đi từ x sang con y thì max[u, y] = cạnh nặng hơn giữa max[u, x] và (x, y). Mỗi lần duyệt O(V), |V| lần: O(V²).
- **(d)** Cho thuật toán hiệu quả tính cây khung nhỏ thứ hai. *Lời giải:* tìm T bằng Prim (O(E + V lg V)); tính bảng max (O(V²)); với mỗi cạnh (x, y) ∉ T, tính w(x, y) − w(max[x, y]); chọn cạnh có hiệu nhỏ nhất, đổi max[x, y] lấy (x, y). Tổng O(V²).

### Problem 23-2: Cây khung nhỏ nhất trên đồ thị thưa (Minimum spanning tree in sparse graphs)

Với đồ thị liên thông rất thưa G = (V, E), có thể cải thiện thêm thời gian O(E + V lg V) của Prim với đống Fibonacci bằng cách tiền xử lý G để giảm số đỉnh trước khi chạy Prim. Cụ thể: với mỗi đỉnh u, chọn cạnh (u, v) có trọng số nhỏ nhất chạm u, và đưa (u, v) vào cây khung nhỏ nhất đang dựng. Sau đó co tất cả các cạnh đã chọn (Mục B.4). Thay vì co từng cạnh một, trước hết xác định các tập đỉnh sẽ được gộp thành cùng một đỉnh mới. Rồi tạo ra đồ thị lẽ ra thu được khi co từng cạnh, nhưng làm bằng cách "đổi tên" các cạnh theo tập chứa đầu mút của chúng. Nhiều cạnh của đồ thị gốc có thể được đổi thành cùng một tên; khi đó chỉ giữ một cạnh, trọng số bằng nhỏ nhất trong các cạnh gốc tương ứng.

Ban đầu, đặt cây T đang dựng là rỗng, và với mỗi cạnh (u, v) ∈ E, khởi tạo thuộc tính (u, v).orig = (u, v) và (u, v).c = w(u, v). Thuộc tính *orig* trỏ tới cạnh của đồ thị ban đầu ứng với một cạnh trong đồ thị đã co. Thuộc tính *c* giữ trọng số của cạnh, được cập nhật khi co theo quy tắc trên. Thủ tục MST-REDUCE nhận G và T, trả về đồ thị đã co G′ với các thuộc tính cập nhật *orig′* và *c′*, đồng thời tích luỹ các cạnh của G vào cây T.

```text
MST-REDUCE(G, T)
 1  for each v ∈ G.V
 2      v.mark = FALSE
 3      MAKE-SET(v)
 4  for each u ∈ G.V
 5      if u.mark == FALSE
 6          choose v ∈ G.Adj[u] such that (u, v).c is minimized
 7          UNION(u, v)
 8          T = T ∪ {(u, v).orig}
 9          u.mark = v.mark = TRUE
10  G′.V = {FIND-SET(v) : v ∈ G.V}
11  G′.E = ∅
12  for each (x, y) ∈ G.E
13      u = FIND-SET(x)
14      v = FIND-SET(y)
15      if (u, v) ∉ G′.E
16          G′.E = G′.E ∪ {(u, v)}
17          (u, v).orig′ = (x, y).orig
18          (u, v).c′ = (x, y).c
19      else if (x, y).c < (u, v).c′
20          (u, v).orig′ = (x, y).orig
21          (u, v).c′ = (x, y).c
22  construct adjacency lists G′.Adj for G′
23  return G′ and T
```

Giải thích: dòng 1–3 đánh dấu mọi đỉnh "chưa xử lý" và tạo tập một phần tử. Dòng 4–9: với mỗi đỉnh chưa được đánh dấu, chọn cạnh nhẹ nhất chạm nó, gộp hai đầu, đưa cạnh gốc vào T, đánh dấu cả hai đầu. Dòng 10: tập đỉnh mới là tập các đại diện. Dòng 12–21: đổi tên từng cạnh theo đại diện hai đầu; nếu cạnh mới chưa có thì thêm, nếu đã có thì giữ bản nhẹ hơn. (Nhận xét của người tổng hợp, đã nêu ở Lưu ý: cần bỏ qua cạnh có u = v, nếu không G′ chứa khuyên.)

Ví dụ (người tổng hợp) trên đồ thị ví dụ, duyệt đỉnh theo thứ tự a, b, …, i: a chọn ab 4 (đánh dấu a, b); b đã đánh dấu; c chọn ci 2 (c, i); d chọn cd 7 (d); e chọn de 9 (e); f chọn fg 2 (f, g); g đã đánh dấu nên bỏ qua; h chưa đánh dấu, chọn gh 1 (đánh dấu h); i đã đánh dấu. (Lưu ý: d chưa bị đánh dấu khi xét tới vì c chọn ci chứ không chọn cd.) T = {ab, ci, cd, de, fg, gh}, nặng 4 + 2 + 7 + 9 + 2 + 1 = 25, mọi cạnh đều thuộc cây nặng 37. Các tập: {a, b}, {c, d, e, i}, {f, g, h} — 9 đỉnh còn 3 (≤ 9/2). Cạnh của G′ (bỏ các cạnh có hai đầu cùng tập): {a,b}–{f,g,h} giữ ah 8 (bỏ bh 11); {a,b}–{c,d,e,i} là bc 8; {c,d,e,i}–{f,g,h} giữ cf 4 (bỏ df 14, ef 10, gi 6, hi 7). Prim trên G′ chọn cf 4 và một trong hai cạnh nặng 8, ví dụ bc. Kết quả T ∪ {cf, bc} = {ab, ci, cd, de, fg, gh, cf, bc}, nặng 25 + 4 + 8 = 37 — đúng là cây khung nhỏ nhất.

- **(a)** Gọi T là tập cạnh MST-REDUCE trả về, A là cây khung nhỏ nhất của G′ do MST-PRIM(G′, c′, r) tạo ra (r là đỉnh bất kỳ của G′). Chứng minh T ∪ {(x, y).orig′ : (x, y) ∈ A} là cây khung nhỏ nhất của G. *Ý:* mỗi cạnh chọn ở dòng 6 là cạnh nhẹ của lát cắt tách tập (khi đó còn một đỉnh) chứa u — an toàn theo Hệ quả 23.2; sau đó cây khung nhỏ nhất của G chứa T tương ứng một-một với cây khung nhỏ nhất của đồ thị co.
- **(b)** Lập luận |G′.V| ≤ |V|/2. *Ý:* mỗi đỉnh hoặc được xử lý ở dòng 6, hoặc bị đánh dấu nhờ cạnh của đỉnh khác; mọi tập sau dòng 4–9 có ít nhất 2 đỉnh.
- **(c)** Chỉ cách cài MST-REDUCE chạy O(E). (Gợi ý: dùng cấu trúc dữ liệu đơn giản.) *Lời giải của người tổng hợp:* các cạnh chọn tạo một rừng; tìm thành phần liên thông của rừng này bằng DFS trong O(V) và gán nhãn 1..k thay cho FIND-SET; đổi tên mỗi cạnh thành cặp nhãn, bỏ cạnh có hai nhãn trùng, rồi sắp cơ số (radix sort) các cặp nhãn trong O(V + E) để gom các cạnh trùng tên và giữ cạnh nhẹ nhất.
- **(d)** Chạy k pha MST-REDUCE (đầu ra pha trước làm đầu vào pha sau, tích luỹ T). Lập luận tổng thời gian O(kE). *Ý:* số cạnh không tăng qua các pha, mỗi pha O(E).
- **(e)** Sau k pha, chạy MST-PRIM(G′, c′, r). Chỉ cách chọn k để tổng thời gian là O(E lg lg V), và lập luận lựa chọn đó tối ưu. *Lời giải của người tổng hợp:* sau k pha còn ≤ V/2ᵏ đỉnh; Prim với đống Fibonacci tốn O(E + (V/2ᵏ) lg V). Tổng O(kE + V lg V / 2ᵏ). Chọn k = lg lg V: số hạng sau là O(V) ≤ O(E), tổng O(E lg lg V). Lưu ý của người tổng hợp: nếu tối ưu theo cả E thì k tốt nhất là khoảng lg(V lg V / E), cho O(E lg(V lg V / E)); với đồ thị thưa |E| = Θ(V) hai kết quả trùng nhau.
- **(f)** Với giá trị |E| nào (theo |V|) thì Prim có tiền xử lý thắng tiệm cận Prim không tiền xử lý? *Lời giải:* so O(E lg lg V) với O(E + V lg V): thắng khi |E| = o(V lg V / lg lg V).

### Problem 23-3: Cây khung nút cổ chai (Bottleneck spanning tree)

**Cây khung nút cổ chai** T của đồ thị vô hướng G là cây khung của G có trọng số cạnh lớn nhất nhỏ nhất trong mọi cây khung của G. Giá trị của cây khung nút cổ chai là trọng số cạnh nặng nhất trong T.

- **(a)** Lập luận rằng cây khung nhỏ nhất là cây khung nút cổ chai. *Lời giải của người tổng hợp:* gọi T là cây khung nhỏ nhất, e là cạnh nặng nhất của T, b* là giá trị nút cổ chai. Giả sử w(e) > b*. Bỏ e khỏi T cho một lát cắt; cây khung nút cổ chai phải có một cạnh e′ đi qua lát cắt này với w(e′) ≤ b* < w(e). T − {e} ∪ {e′} nhẹ hơn T — mâu thuẫn. Ví dụ: đồ thị ví dụ có giá trị nút cổ chai 9.

Ý (a) cho thấy tìm cây khung nút cổ chai không khó hơn tìm cây khung nhỏ nhất. Các ý còn lại chỉ cách tìm nó trong thời gian tuyến tính.

- **(b)** Cho thuật toán tuyến tính: với đồ thị G và số nguyên b, xác định giá trị cây khung nút cổ chai có ≤ b không. *Lời giải:* giữ các cạnh nặng ≤ b, kiểm tra liên thông bằng BFS/DFS, O(V + E).
- **(c)** Dùng (b) làm thủ tục con cho thuật toán tuyến tính giải bài toán cây khung nút cổ chai. (Gợi ý: dùng thủ tục co tập cạnh như MST-REDUCE ở Problem 23-2.) *Lời giải của người tổng hợp:* tìm trung vị m của các trọng số bằng thuật toán chọn tuyến tính (Mục 9.3). Nếu các cạnh ≤ m làm đồ thị liên thông, giá trị nút cổ chai ≤ m: đệ quy chỉ trên các cạnh ≤ m (một nửa số cạnh). Nếu không, các thành phần liên thông của đồ thị cạnh ≤ m chắc chắn được nối "miễn phí"; co mỗi thành phần thành một đỉnh, giữ lại các cạnh > m giữa các thành phần, đệ quy. Mỗi bước O(V + E), số cạnh giảm một nửa: T(E) = T(E/2) + O(E) = O(E).

### Problem 23-4: Các thuật toán cây khung nhỏ nhất thay thế (Alternative minimum-spanning-tree algorithms)

Bài toán cho pseudocode của ba thuật toán. Mỗi thuật toán nhận đồ thị liên thông và hàm trọng số, trả về một tập cạnh T. Với mỗi thuật toán, chứng minh T là cây khung nhỏ nhất hoặc chứng minh không phải. Mô tả cài đặt hiệu quả nhất của từng thuật toán, dù nó có tính đúng cây khung nhỏ nhất hay không.

```text
a. MAYBE-MST-A(G, w)
   1  sort the edges into nonincreasing order of edge weights w
   2  T = E
   3  for each edge e, taken in nonincreasing order by weight
   4      if T − {e} is a connected graph
   5          T = T − {e}
   6  return T

b. MAYBE-MST-B(G, w)
   1  T = ∅
   2  for each edge e, taken in arbitrary order
   3      if T ∪ {e} has no cycles
   4          T = T ∪ {e}
   5  return T

c. MAYBE-MST-C(G, w)
   1  T = ∅
   2  for each edge e, taken in arbitrary order
   3      T = T ∪ {e}
   4      if T has a cycle c
   5          let e′ be a maximum-weight edge on c
   6          T = T − {e′}
   7  return T
```

*Lời giải của người tổng hợp:*
- **(a) Đúng** ("xoá ngược", reverse-delete). Khi e bị xoá, T − {e} còn liên thông nên e nằm trên một chu trình trong T. Mọi cạnh của T nặng hơn e đã được xét trước và được giữ lại vì là cầu của T lúc đó (bỏ đi thì mất liên thông), nên không cạnh nào trong số đó nằm trên chu trình. Vậy mọi cạnh trên chu trình qua e có trọng số ≤ w(e): e là cạnh nặng nhất trên chu trình, và theo tính chất chu trình (Bài tập 23.1-5) có cây khung nhỏ nhất không chứa e. Cuối cùng T liên thông (không bao giờ xoá cạnh làm mất liên thông) và không chu trình (một chu trình còn sót thì cạnh nặng nhất của nó đã bị xoá khi được xét). Cài đặt: sắp xếp O(E lg E), mỗi kiểm tra liên thông bằng BFS O(V + E): tổng O(E(V + E)). (Có thể nhanh hơn với cấu trúc liên thông động — theo hiểu biết của người tổng hợp.)
- **(b) Sai.** Nó trả về một cây khung bất kỳ. Phản ví dụ: tam giác ab 1, bc 2, ac 3, duyệt theo thứ tự ac, bc, ab: T = {ac, bc} nặng 5, trong khi tối ưu là 3. Cài đặt: tập rời nhau, O(E α(V)).
- **(c) Đúng.** Mỗi cạnh bị loại là cạnh nặng nhất trên một chu trình của đồ thị gồm các cạnh đã xét, nên theo tính chất chu trình không cần cho cây khung nhỏ nhất; cuối cùng T liên thông (không bao giờ bỏ cạnh làm mất liên thông, vì cạnh bị bỏ nằm trên chu trình) và không chu trình. Cài đặt: T luôn là rừng; khi thêm e = (u, v), nếu u, v đã liên thông trong T thì tìm đường u–v bằng DFS O(V) và bỏ cạnh nặng nhất: O(VE). Dùng cây link-cut có thể đạt O(E lg V) — theo hiểu biết của người tổng hợp.

### Ghi chú chương (Chapter notes, trang 641–642)

- **Tarjan** có bài tổng quan về bài toán cây khung nhỏ nhất kèm tài liệu nâng cao rất tốt. **Graham và Hell** biên soạn lịch sử của bài toán.
- Tarjan ghi nhận thuật toán cây khung nhỏ nhất đầu tiên thuộc về bài báo năm 1926 của **O. Borůvka**. Thuật toán Borůvka gồm O(lg V) lần lặp thủ tục MST-REDUCE ở Problem 23-2.
- Thuật toán Kruskal được **Kruskal** công bố năm 1956. Thuật toán thường gọi là thuật toán Prim đúng là do **Prim** phát minh, nhưng nó đã được **V. Jarník** phát minh trước đó, năm 1930.
- Lý do sâu xa vì sao thuật toán tham lam hiệu quả trong việc tìm cây khung nhỏ nhất là: tập các rừng của một đồ thị tạo thành một **matroid đồ thị** (graphic matroid) (Mục 16.4).
- Khi |E| = Ω(V lg V), Prim cài bằng đống Fibonacci chạy O(E). Với đồ thị thưa hơn, kết hợp ý tưởng của Prim, Kruskal, Borůvka cùng các cấu trúc dữ liệu nâng cao, **Fredman và Tarjan** cho thuật toán O(E lg* V). **Gabow, Galil, Spencer và Tarjan** cải tiến thành O(E lg lg* V). **Chazelle** cho thuật toán O(E α̂(E, V)), với α̂(E, V) là hàm ngược của hàm Ackermann (xem Ghi chú Chương 21). Khác các thuật toán trước, thuật toán của Chazelle không theo phương pháp tham lam.
- Một bài toán liên quan là **kiểm chứng cây khung** (spanning-tree verification): cho đồ thị G = (V, E) và cây T ⊆ E, xác định T có phải cây khung nhỏ nhất của G không. **King** cho thuật toán kiểm chứng tuyến tính, dựa trên công trình trước của **Komlós** và **Dixon, Rauch, Tarjan**.
- Các thuật toán trên đều tất định và thuộc mô hình dựa trên so sánh của Chương 8. **Karger, Klein và Tarjan** cho thuật toán ngẫu nhiên chạy kỳ vọng O(V + E). Thuật toán dùng đệ quy giống thuật toán chọn tuyến tính ở Mục 9.3: một lời gọi đệ quy trên bài toán phụ xác định tập cạnh E′ không thể nằm trong bất kỳ cây khung nhỏ nhất nào; một lời gọi đệ quy khác trên E − E′ tìm cây khung nhỏ nhất. Thuật toán cũng dùng ý tưởng của Borůvka và thuật toán kiểm chứng của King.
- **Fredman và Willard** chỉ ra cách tìm cây khung nhỏ nhất trong O(V + E) bằng thuật toán tất định không dựa trên so sánh. Thuật toán giả định dữ liệu là số nguyên b bit và bộ nhớ máy gồm các từ b bit đánh địa chỉ được.

## Luận điểm cốt lõi

### Mệnh đề

Trên đồ thị vô hướng liên thông có trọng số, cây khung nhỏ nhất có thể tìm bằng chiến lược tham lam, vì cạnh nhẹ nhất đi qua bất kỳ lát cắt nào tôn trọng tập cạnh đã chọn luôn an toàn. Kruskal và Prim là hai cách chọn lát cắt, chạy O(E lg V); Prim với đống Fibonacci chạy O(E + V lg V).

### Giả định

- Đồ thị vô hướng và liên thông (nếu không liên thông, các thuật toán cho rừng khung nhỏ nhất).
- Trọng số là số thực tuỳ ý — được phép âm hoặc bằng 0; không cần trọng số khác nhau (trừ Problem 23-1).
- Mô hình dựa trên so sánh: thuật toán chỉ so sánh trọng số với nhau.
- Kruskal dùng rừng tập rời nhau với hợp theo hạng và nén đường đi; Prim dùng đống nhị phân hoặc đống Fibonacci và danh sách kề.

### Cơ chế

1. Bất biến: A luôn nằm trong một cây khung nhỏ nhất nào đó.
2. Định lý 23.1 (cắt và dán): cạnh nhẹ của lát cắt tôn trọng A có thể đổi chỗ với cạnh đi qua lát cắt trên đường đi trong cây mà không làm cây nặng thêm.
3. Hệ quả 23.2: chỉ cần xét lát cắt tách một cây C của rừng G_A khỏi phần còn lại.
4. Kruskal: duyệt cạnh tăng dần; cạnh nối hai cây khác nhau là cạnh nhẹ nhất nối cây của một đầu mút ra ngoài.
5. Prim: lát cắt luôn là (cây hiện tại, phần còn lại); hàng đợi ưu tiên giữ sẵn cạnh nhẹ nhất từ mỗi đỉnh ngoài cây vào cây.

### Bằng chứng và ví dụ tác giả đưa ra

- Đồ thị 9 đỉnh 14 cạnh, cây khung nhỏ nhất nặng 37, không duy nhất (đổi (b, c) lấy (a, h)).
- Ví dụ lát cắt S = {a, b, d, e} với cạnh nhẹ duy nhất (d, c) nặng 7.
- Hình vẽ minh hoạ chứng minh Định lý 23.1: đường đi p từ u tới v trong T, cạnh (x, y) đổi màu.
- 14 bước Kruskal (thêm 1, 2, 2, 4, 4, 7, 8, 9; loại 6, 7, 8, 10, 11, 14) và 9 bước Prim từ gốc a.
- Phân tích thời gian: Kruskal O(E lg V); Prim O(E lg V) với đống nhị phân, O(E + V lg V) với đống Fibonacci.

### Kết luận và hàm ý cho người lập trình

- Khi cần nối mọi điểm với chi phí nhỏ nhất, đừng thử mọi tổ hợp: Kruskal hoặc Prim cho lời giải tối ưu trong O(E lg V).
- Chọn Kruskal khi có sẵn danh sách cạnh, đồ thị thưa, hoặc trọng số sắp được nhanh; chọn Prim khi có danh sách kề hoặc ma trận kề, đặc biệt đồ thị dày (bản mảng O(V²), Bài tập 23.2-2).
- Trọng số âm không gây vấn đề cho cây khung nhỏ nhất (khác hẳn đường đi ngắn nhất ở Chương 24).
- Khi trọng số bằng nhau, có thể có nhiều cây tối ưu; mọi cây tối ưu có cùng danh sách trọng số (Bài tập 23.1-8).
- Tính chất lát cắt (Định lý 23.1) và tính chất chu trình (Bài tập 23.1-5) là hai công cụ chứng minh đủ cho hầu hết các biến thể (cập nhật cây khi đổi trọng số, cây nhỏ thứ hai, cây nút cổ chai).

### Trong ngôn ngữ khoa học máy tính

GENERIC-MST: bất biến A ⊆ T* cho một MST T*; cạnh an toàn = cạnh nhẹ của lát cắt (S, V − S) tôn trọng A. MST-KRUSKAL: sort + |V| MAKE-SET + O(E) FIND-SET/UNION = O(E lg E) + O((V + E) α(V)) = O(E lg V). MST-PRIM: |V| EXTRACT-MIN + O(E) DECREASE-KEY; đống nhị phân O((V + E) lg V) = O(E lg V); đống Fibonacci O(E + V lg V); mảng O(V²). Cận tốt nhất đã biết: tất định O(E α̂(E, V)) (Chazelle), ngẫu nhiên kỳ vọng O(V + E) (Karger–Klein–Tarjan). Cơ sở lý thuyết: rừng của đồ thị là matroid đồ thị.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| spanning tree | cây khung | tập cạnh không chu trình nối mọi đỉnh, có |V| − 1 cạnh |
| minimum spanning tree (MST) | cây khung nhỏ nhất | cây khung có tổng trọng số nhỏ nhất |
| minimum-weight spanning tree | cây khung có trọng số nhỏ nhất | tên đầy đủ của "cây khung nhỏ nhất" |
| weight function w : E → ℝ | hàm trọng số | gán số thực cho mỗi cạnh |
| greedy algorithm | thuật toán tham lam | mỗi bước chọn phương án tốt nhất lúc đó |
| safe edge | cạnh an toàn | thêm vào A vẫn nằm trong một MST |
| loop invariant | bất biến vòng lặp | mệnh đề đúng trước mỗi lần lặp |
| cut (S, V − S) | lát cắt | phân hoạch tập đỉnh thành hai phần |
| edge crosses a cut | cạnh đi qua lát cắt | hai đầu mút ở hai phía |
| cut respects A | lát cắt tôn trọng A | không cạnh nào của A đi qua lát cắt |
| light edge | cạnh nhẹ | cạnh nhẹ nhất trong các cạnh đi qua lát cắt |
| cut-and-paste | cắt và dán | kỹ thuật chứng minh bằng đổi một phần lời giải tối ưu |
| forest G_A = (V, A) | rừng G_A | đồ thị chỉ gồm các cạnh của A |
| connected component | thành phần liên thông | tập đỉnh liên thông tối đại |
| disjoint-set data structure | cấu trúc tập rời nhau | MAKE-SET, FIND-SET, UNION |
| union by rank / path compression | hợp theo hạng / nén đường đi | hai kỹ thuật tăng tốc tập rời nhau |
| min-priority queue | hàng đợi ưu tiên min | INSERT, EXTRACT-MIN, DECREASE-KEY |
| binary min-heap | đống nhị phân min | hàng đợi ưu tiên, mọi thao tác O(lg n) |
| Fibonacci heap | đống Fibonacci | DECREASE-KEY O(1) khấu hao |
| key / π attribute | khoá / cha | trong Prim: trọng số cạnh nhẹ nhất vào cây / đầu kia của cạnh đó |
| isolated vertex | đỉnh cô lập | đỉnh chưa có cạnh nào của A chạm vào |
| adjacency list / matrix | danh sách kề / ma trận kề | hai cách biểu diễn đồ thị |
| edge contraction | co cạnh | gộp hai đầu mút thành một đỉnh |
| second-best MST | cây khung nhỏ thứ hai | cây khung nhẹ nhất khác MST |
| bottleneck spanning tree | cây khung nút cổ chai | cây khung có cạnh nặng nhất nhỏ nhất |
| graphic matroid | matroid đồ thị | matroid có tập độc lập là các rừng |
| spanning-tree verification | kiểm chứng cây khung | kiểm tra một cây cho trước có là MST |
| cycle property | tính chất chu trình | cạnh nặng nhất trên chu trình có thể bỏ (Bài tập 23.1-5) |
| inverse Ackermann function α | hàm ngược Ackermann | tăng cực chậm, ≤ 4 trong thực tế |
| iterated logarithm lg* | logarit lặp | số lần lấy lg tới khi ≤ 1 |

## Câu nói đáng nhớ

> "Since T is acyclic and connects all of the vertices, it must form a tree, which we call a spanning tree since it 'spans' the graph G." — phần mở đầu chương
>
> *Dịch: Vì T không có chu trình và nối mọi đỉnh, nó phải tạo thành một cây, mà ta gọi là cây khung vì nó "phủ" đồ thị G.*

> "Such a strategy does not generally guarantee that it will always find globally optimal solutions to problems. For the minimum-spanning-tree problem, however, we can prove that certain greedy strategies do yield a spanning tree with minimum weight." — phần mở đầu chương
>
> *Dịch: Chiến lược như vậy nói chung không bảo đảm luôn tìm được lời giải tối ưu toàn cục. Tuy nhiên, với bài toán cây khung nhỏ nhất, ta chứng minh được rằng một số chiến lược tham lam nhất định cho cây khung có trọng số nhỏ nhất.*

> "Prior to each iteration, A is a subset of some minimum spanning tree." — Mục 23.1
>
> *Dịch: Trước mỗi lần lặp, A là tập con của một cây khung nhỏ nhất nào đó.*

> "The tricky part is, of course, finding a safe edge in line 3." — Mục 23.1
>
> *Dịch: Phần khó, tất nhiên, là tìm cạnh an toàn ở dòng 3.*

> "Kruskal's algorithm qualifies as a greedy algorithm because at each step it adds to the forest an edge of least possible weight." — Mục 23.2
>
> *Dịch: Thuật toán Kruskal là thuật toán tham lam vì ở mỗi bước nó thêm vào rừng một cạnh có trọng số nhỏ nhất có thể.*

> "The reason underlying why greedy algorithms are effective at finding minimum spanning trees is that the set of forests of a graph forms a graphic matroid." — Ghi chú chương
>
> *Dịch: Lý do sâu xa vì sao thuật toán tham lam hiệu quả trong việc tìm cây khung nhỏ nhất là tập các rừng của một đồ thị tạo thành một matroid đồ thị.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: một định lý, hai thuật toán

Cách trình bày "phương pháp tổng quát + một quy tắc nhận diện cạnh an toàn + hai cách cài đặt" rất tiết kiệm: tính đúng của cả Kruskal lẫn Prim gói trong Hệ quả 23.2, mỗi thuật toán chỉ cần một câu chứng minh. Người đọc học được mẫu tư duy dùng lại nhiều lần: tách "cái gì đúng" (bất biến, cạnh an toàn) khỏi "làm sao nhanh" (tập rời nhau, hàng đợi ưu tiên). Định lý 23.1 cũng đủ mạnh để giải gần hết bài tập: Borůvka, cây nhỏ thứ hai, cây nút cổ chai đều là hệ quả.

### Điểm mạnh: chứng minh không cần trọng số khác nhau hay dương

Định lý 23.1 dùng "≤" thay vì "<", nên xử lý trọn vẹn trường hợp hoà và trọng số âm — nhiều giáo trình khác giả định trọng số khác nhau để đơn giản hoá. Ví dụ chạy tay có hoà thật sự (hai cạnh nặng 8 ở cả Kruskal và Prim) cho thấy hệ quả của việc này: các thuật toán vẫn đúng nhưng cây trả về phụ thuộc cách phá hoà.

### Điểm yếu và chỗ đơn giản hoá

- **Hai hình chạy tay cho hai cây khác nhau mà sách không nói rõ.** Ví dụ chạy tay Kruskal chọn (a, h), ví dụ chạy tay Prim chọn (b, c). Chú thích hình đồ thị ví dụ có nhắc cây không duy nhất, nhưng người đọc so hai hình dễ tưởng mình đọc nhầm.
- **Phân tích Kruskal hơi vòng.** Chuỗi "α(|V|) = O(lg V) = O(lg E)" để gộp phần tập rời nhau vào O(E lg E) đúng nhưng che mất điểm quan trọng: phần tập rời nhau gần tuyến tính, chi phí thật nằm hết ở bước sắp xếp. Bài tập 23.2-4 mới làm rõ điều này.
- **Prim được trình bày với DECREASE-KEY "ngầm" ở dòng 11**, trong khi đống nhị phân của Chương 6 cần biết vị trí phần tử trong đống để giảm khoá (cần thêm một mảng chỉ số). Sách không nói chi tiết này; cài đặt thực tế thường né bằng "xoá lười".
- **MST-REDUCE (Problem 23-2) sinh khuyên** khi không loại các cạnh có hai đầu cùng tập (đã nêu ở Lưu ý).
- **Đống Fibonacci chỉ có lợi trên lý thuyết.** Sách nói Prim + đống Fibonacci "cải thiện" thời gian, nhưng hằng số lớn khiến nó hiếm khi nhanh hơn đống nhị phân trong thực tế — theo hiểu biết của người tổng hợp.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: thư viện đồ thị (Boost Graph Library, NetworkX) cài cả Kruskal và Prim; trong lập trình thi đấu, Kruskal với tập rời nhau là lựa chọn mặc định vì ngắn và khó sai. Với đồ thị cực lớn hoặc song song, thuật toán Borůvka (Ghi chú chương, Problem 23-2) được ưa chuộng vì mỗi vòng xử lý mọi thành phần độc lập. Với điểm trên mặt phẳng (cây khung Euclid), người ta dựng tam giác phân Delaunay trước (O(n lg n) cạnh) rồi chạy Kruskal, thay vì xét đủ n² cặp.

### Liên hệ các chương khác

- Chương 16: tham lam và matroid — Định lý 23.1 là trường hợp riêng của tính đúng của tham lam trên matroid có trọng số.
- Chương 21: Kruskal là ứng dụng tiêu biểu của tập rời nhau; MST-REDUCE cũng dùng MAKE-SET/UNION/FIND-SET.
- Chương 6 và 19: đống nhị phân và đống Fibonacci quyết định thời gian của Prim.
- Chương 22: biểu diễn đồ thị bằng danh sách kề, BFS/DFS dùng trong các bài tập (kiểm tra liên thông, tìm đường trong cây).
- Chương 24: Dijkstra có cùng khung với Prim, chỉ khác khoá: Prim dùng w(u, v), Dijkstra dùng u.d + w(u, v).
- Chương 9: thuật toán chọn tuyến tính dùng trong Problem 23-3 và là hình mẫu đệ quy cho thuật toán ngẫu nhiên Karger–Klein–Tarjan.
- Chương 35: cây khung nhỏ nhất là bước đầu của thuật toán xấp xỉ tỷ lệ 2 cho bài toán người du lịch có bất đẳng thức tam giác.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** viết Kruskal với tập rời nhau (nén đường đi + hợp theo hạng); giải thích tính chất lát cắt và tính chất chu trình; phân biệt Prim với Dijkstra; các biến thể "chi phí nhỏ nhất nối mọi thành phố", "có sẵn vài con đường miễn phí" (đưa cạnh trọng số 0 vào trước).
- **Lập trình thi đấu:** cây khung nhỏ thứ hai (Problem 23-1, thường dùng nâng nhị phân để truy vấn cạnh nặng nhất trên đường đi trong O(lg V)); cây khung nút cổ chai và truy vấn "cạnh nặng nhất nhỏ nhất trên đường đi giữa u và v" (trả lời trên cây khung nhỏ nhất); Kruskal dừng sớm để phân cụm k nhóm; đồ thị đầy đủ trên điểm thì dùng Prim O(V²).
- **Kỹ thuật phần mềm:** thiết kế mạng, phân cụm liên kết đơn, xấp xỉ bài toán Steiner và người du lịch, phân đoạn ảnh dựa trên đồ thị (phương pháp Felzenszwalb–Huttenlocher dùng tư tưởng Kruskal — theo hiểu biết của người tổng hợp).

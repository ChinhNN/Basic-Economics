# Chương 12 — Cây tìm kiếm nhị phân (Binary Search Trees)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần III "Data Structures" (Cấu trúc dữ liệu), Chương 12 "Binary Search Trees", trang 286–307.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (MIT, Dartmouth, Columbia), bộ sách thường được gọi tắt là "CLRS", giáo trình thuật toán phổ biến nhất ở bậc đại học.
**Vị trí trong lập luận của cả cuốn sách:** Chương 10 ([C10-cau-truc-du-lieu-co-ban.md](C10-cau-truc-du-lieu-co-ban.md)) đã dựng các cấu trúc liên kết cơ bản (danh sách liên kết, cách biểu diễn cây có gốc bằng các nút có con trỏ tới cha và con), còn Chương 11 ([C11-bang-bam.md](C11-bang-bam.md)) cho một từ điển (dictionary) với thời gian kỳ vọng O(1) cho tìm kiếm, chèn và xoá nhưng không giữ được thứ tự giữa các khoá. Chương 12 đưa ra cây tìm kiếm nhị phân: một cấu trúc liên kết giữ các khoá theo thứ tự, nên ngoài tìm kiếm, chèn, xoá còn hỗ trợ tìm phần tử nhỏ nhất, lớn nhất, phần tử liền trước, liền sau và in toàn bộ khoá theo thứ tự tăng dần; mọi thao tác chạy trong O(h) với h là chiều cao cây. Chương chứng minh rằng cây được dựng bằng cách chèn các khoá theo thứ tự ngẫu nhiên có chiều cao kỳ vọng O(lg n), nhưng trong trường hợp xấu nhất chiều cao có thể là n − 1. Chương 13 ([C13-cay-do-den.md](C13-cay-do-den.md)) giải quyết điểm yếu đó bằng cây đỏ-đen, luôn có chiều cao O(lg n); Chương 14 ([C14-mo-rong-cau-truc-du-lieu.md](C14-mo-rong-cau-truc-du-lieu.md)) gắn thêm thông tin vào nút cây để trả lời thống kê thứ tự và truy vấn khoảng; Mục 15.5 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)) dựng cây tìm kiếm nhị phân tối ưu khi biết trước tần suất tìm kiếm; Chương 18 ([C18-cay-b.md](C18-cay-b.md)) tổng quát hoá ý tưởng thành cây B cho dữ liệu trên đĩa. Phép phân tích ở Mục 12.4 dùng lại biến ngẫu nhiên chỉ báo của Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)) và giống hệt cấu trúc phân tích quicksort ngẫu nhiên ở Chương 7 ([C07-quicksort.md](C07-quicksort.md)).
**Ý chính:** Tác giả muốn người đọc hiểu rằng **một cây nhị phân mà mọi nút đều thoả "khoá ở cây con trái ≤ khoá của nút ≤ khoá ở cây con phải" (tính chất cây tìm kiếm nhị phân) cho phép làm mọi thao tác của tập động bằng cách đi theo một đường đơn từ gốc xuống (hoặc từ một nút lên), nên chi phí của mọi thao tác tỉ lệ với chiều cao h của cây, không tỉ lệ với số nút n.** Duyệt trung thứ tự (INORDER-TREE-WALK) in mọi khoá theo thứ tự tăng dần trong Θ(n) (Định lý 12.1). Tìm kiếm (TREE-SEARCH, ITERATIVE-TREE-SEARCH), tìm nhỏ nhất/lớn nhất (TREE-MINIMUM, TREE-MAXIMUM), tìm phần tử kế tiếp/liền trước (TREE-SUCCESSOR, TREE-PREDECESSOR) đều chạy trong O(h) (Định lý 12.2). Chèn (TREE-INSERT) và xoá (TREE-DELETE, dùng thủ tục phụ TRANSPLANT để thay một cây con bằng cây con khác) cũng chạy trong O(h) (Định lý 12.3); xoá là phần khó vì khi nút có hai con, phải đưa nút kế tiếp của nó lên thay chỗ. Chiều cao h dao động từ ⌊lg n⌋ (cây cân bằng) tới n − 1 (cây thành một chuỗi khi chèn các khoá đã sắp xếp). Mục 12.4 (mục khó) chứng minh rằng cây dựng ngẫu nhiên trên n khoá phân biệt có chiều cao kỳ vọng O(lg n), bằng kỹ thuật "chiều cao mũ" Yₙ = 2^Xₙ: chứng minh E[Yₙ] ≤ (1/4)·C(n+3, 3) = (n³ + 6n² + 11n + 6)/24, rồi dùng bất đẳng thức Jensen để suy ra E[Xₙ] ≤ lg của đa thức bậc ba, tức E[Xₙ] ≈ 3 lg n = O(lg n).

> **Lưu ý:**
> - **Mục có dấu sao:** Mục 12.4 "Randomly built binary search trees" có dấu ? (mục khó, có thể bỏ qua ở lần đọc đầu). Bài tập 12.4-5 cũng có dấu sao.
> - **Lỗi đánh máy trong lời giải thích TREE-DELETE (trang 298):** sách viết "If y is not z's left child, lines 7–9 replace y as a child of its parent by y's right child…". Đúng ra phải là "**If y is not z's right child**" (nếu y không phải con phải của z), vì y là nút nhỏ nhất trong cây con phải của z nên không bao giờ là con trái của z; điều kiện ở dòng 6 của mã (`if y.p ≠ z`) cũng đúng là "y không phải con phải của z". Theo hiểu biết của người tổng hợp, đây là lỗi nằm trong danh sách errata chính thức của ấn bản 3 (không tra cứu lại).
> - **Thiếu chữ trong chứng minh Định lý 12.4 (trang 300):** câu "We denote the height of a randomly built binary search on n keys by Xₙ" thiếu chữ "tree" (cây tìm kiếm nhị phân dựng ngẫu nhiên).
> - **Một chi tiết cần đọc kỹ trong chứng minh Định lý 12.4:** công thức Yₙ = 2·max(Yᵢ₋₁, Yₙ₋ᵢ) và truy hồi (12.2) chỉ đúng với n ≥ 2. Với n = 1, công thức sẽ cho Y₁ = 2·max(Y₀, Y₀) = 0, mâu thuẫn với quy ước Y₁ = 1; vì vậy sách đặt Y₁ = 1 và Y₀ = 0 làm trường hợp cơ sở, và bước quy nạp phải bắt đầu từ n = 2. Sách không nói rõ điều này nhưng chứng minh vẫn đúng (người tổng hợp đã kiểm tra n = 2: E[Y₂] = 2 ≤ (4/2)(0 + 1) = 2 ≤ (1/4)·C(5,3) = 2,5).
> - **Lớp chữ PDF hỏng:** mọi pseudocode, ký hiệu ´ (là z), ký hiệu  (là v trong TRANSPLANT), các dấu ≤, ≥, ≠, công thức tổ hợp C(n+3, 3), tổng Σ và bất đẳng thức Jensen trong Mục 12.4, công thức hàm sinh B(x) = (1 − √(1 − 4x))/(2x) và bₙ = 4ⁿ/(√π·n^{3/2})·(1 + O(1/n)) ở Bài toán 12-4 đều được đọc lại từ ảnh trang. Các hình 12.1–12.5 không có chữ dùng được trong lớp văn bản; cấu trúc cây được đọc từ ảnh.
> - **Khác biệt với hai ấn bản đầu:** chính Ghi chú chương nói rằng ấn bản 1 và 2 xoá nút có hai con bằng cách chép khoá của nút kế tiếp y vào z rồi xoá y; ấn bản 3 đổi sang cách "đưa y lên thay chỗ z" bằng TRANSPLANT để lệnh xoá z thực sự xoá đúng nút z. Mã TREE-DELETE ở đây vì vậy khác các sách cũ và nhiều tài liệu trên mạng.
> - **Ấn bản 4 (2022):** người tổng hợp không chắc chắn về các thay đổi cụ thể của chương này trong ấn bản 4 (có nhớ mơ hồ rằng mục cây dựng ngẫu nhiên đã bị lược bớt, nhưng không khẳng định), nên không liệt kê.

## Sơ đồ

### Phần mở đầu Chương 12 — cây tìm kiếm hỗ trợ những gì và chi phí phụ thuộc vào đâu (trang 286)

```text
       Cây tìm kiếm hỗ trợ bảy thao tác của tập động:
       SEARCH, MINIMUM, MAXIMUM, PREDECESSOR, SUCCESSOR, INSERT, DELETE
       · vì vậy cây tìm kiếm vừa dùng làm TỪ ĐIỂN, vừa dùng làm HÀNG ĐỢI
         ƯU TIÊN
                                │
                                ▼
       Chi phí mỗi thao tác cơ bản tỉ lệ với CHIỀU CAO h của cây
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       Cây nhị phân đầy đủ n nút:       Cây suy biến thành chuỗi n nút:
       h ≈ lg n, mỗi thao tác           h = n − 1, mỗi thao tác
       mất Θ(lg n) trong trường hợp     mất Θ(n) trong trường hợp
       xấu nhất                         xấu nhất
               └────────────────┬────────────────┘
                                ▼
       Mục 12.4 chứng minh: cây dựng NGẪU NHIÊN có chiều cao kỳ vọng
       O(lg n), nên trung bình mỗi thao tác mất Θ(lg n)
                                │
                                ▼
       Thực tế không bảo đảm được thứ tự chèn ngẫu nhiên, nên các chương
       sau thiết kế biến thể có bảo đảm trường hợp xấu nhất:
       · Chương 13: cây đỏ-đen, chiều cao O(lg n)
       · Chương 18: cây B, phù hợp cơ sở dữ liệu trên đĩa
```

### Mục 12.1 — Cây tìm kiếm nhị phân là gì (What is a binary search tree?, trang 286–289)

```text
       Mỗi nút là một đối tượng gồm: key (khoá), dữ liệu vệ tinh, và ba
       con trỏ left (con trái), right (con phải), p (cha)
       · con hoặc cha không tồn tại thì con trỏ mang giá trị NIL
       · gốc là nút duy nhất có p = NIL
                                │
                                ▼
       TÍNH CHẤT CÂY TÌM KIẾM NHỊ PHÂN (áp dụng cho MỌI nút x):
       · mọi nút y trong cây con trái của x có y.key ≤ x.key
       · mọi nút y trong cây con phải của x có y.key ≥ x.key
                                │
                                ▼
       Cùng một tập khoá {2, 5, 5, 6, 7, 8} có nhiều cây khác nhau:
            (a) chiều cao 2               (b) chiều cao 4
                  6                        2
                /   \                       \
               5     7                       5
              / \     \                       \
             2   5     8                       7
                                              / \
                                             6   8
                                            /
                                           5
                                │
                                ▼
       DUYỆT TRUNG THỨ TỰ (inorder): in cây con trái, rồi in gốc, rồi in
       cây con phải → in khoá theo thứ tự tăng dần: 2, 5, 5, 6, 7, 8
       · duyệt tiền thứ tự (preorder): in gốc TRƯỚC hai cây con
       · duyệt hậu thứ tự (postorder): in gốc SAU hai cây con
                                │
                                ▼
       ĐỊNH LÝ 12.1: INORDER-TREE-WALK trên cây con n nút mất Θ(n)
       · cận dưới Ω(n): thủ tục thăm mọi nút
       · cận trên O(n): chứng minh bằng phương pháp thay thế rằng
         T(n) ≤ (c + d)n + c, với T(0) = c và mỗi lần gọi tốn thêm ≤ d
```

### Mục 12.2 — Truy vấn trên cây tìm kiếm nhị phân (Querying a binary search tree, trang 289–294)

```text
       Cây ví dụ dùng cho cả mục (Hình 12.2 của sách):
                       15
                    /      \
                   6        18
                 /   \     /  \
                3     7   17   20
               / \     \
              2   4     13
                       /
                      9
                                │
                                ▼
       TÌM KIẾM khoá k (TREE-SEARCH đệ quy, ITERATIVE-TREE-SEARCH vòng lặp)
       · so k với x.key: bằng thì dừng; nhỏ hơn thì xuống trái; lớn hơn
         thì xuống phải
       · ví dụ tìm 13: 15 → 6 → 7 → 13
       · các nút gặp tạo thành một đường đơn đi xuống, nên mất O(h)
       · bản vòng lặp thường nhanh hơn trên đa số máy tính
                                │
                                ▼
       NHỎ NHẤT / LỚN NHẤT (TREE-MINIMUM / TREE-MAXIMUM)
       · đi theo con trỏ left (hoặc right) từ gốc tới khi gặp NIL
       · ví dụ: nhỏ nhất 15 → 6 → 3 → 2; lớn nhất 15 → 18 → 20
       · O(h)
                                │
                                ▼
       NÚT KẾ TIẾP (TREE-SUCCESSOR): nút đứng ngay sau x khi duyệt trung
       thứ tự; tìm được mà KHÔNG cần so sánh khoá
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       x có cây con phải:               x không có cây con phải:
       kế tiếp = nút nhỏ nhất của       đi lên từ x cho tới khi gặp một
       cây con phải                     nút là CON TRÁI của cha nó; cha
       ví dụ: kế tiếp của 15 là 17      đó là nút kế tiếp (tổ tiên thấp
                                        nhất có con trái cũng là tổ tiên
                                        của x)
                                        ví dụ: kế tiếp của 13 là 15
               └────────────────┬────────────────┘
                                ▼
       TREE-PREDECESSOR (nút liền trước) đối xứng; cả hai mất O(h)
                                │
                                ▼
       ĐỊNH LÝ 12.2: SEARCH, MINIMUM, MAXIMUM, SUCCESSOR, PREDECESSOR đều
       cài đặt được trong O(h) trên cây chiều cao h
```

### Mục 12.3 — Chèn và xoá (Insertion and deletion, trang 294–299)

```text
       CHÈN (TREE-INSERT): nút mới z có z.key = v, z.left = z.right = NIL
       · con trỏ x đi từ gốc xuống như khi tìm kiếm, cho tới khi x = NIL
       · "con trỏ theo sau" y luôn là cha của x, vì khi gặp NIL thì đã đi
         quá nút cần sửa một bước
       · gắn z làm con trái hoặc con phải của y (hoặc làm gốc nếu cây rỗng)
       · ví dụ: chèn 13 vào cây gốc 12 đi theo 12 → 18 → 15, rồi 13 thành
         con trái của 15
       · O(h)
                                │
                                ▼
       XOÁ nút z — ba trường hợp theo ý tưởng:
       · z không có con: cha của z trỏ tới NIL thay cho z
       · z có một con: đưa con đó lên thay chỗ z
       · z có hai con: lấy nút kế tiếp y (nằm trong cây con phải của z,
         không có con trái) lên thay chỗ z — trường hợp khó
                                │
                                ▼
       Thủ tục phụ TRANSPLANT(T, u, v): thay cây con gốc u bằng cây con
       gốc v ở vị trí con của cha u; cha của u trở thành cha của v
       · không tự sửa v.left, v.right — việc đó do nơi gọi đảm nhận
                                │
                                ▼
       TREE-DELETE tổ chức thành bốn trường hợp (Hình 12.4 của sách):
       ┌─ (a) z không có con trái: thay z bằng con phải r (r có thể NIL)
       ├─ (b) z chỉ có con trái l: thay z bằng l
       ├─ (c) z có hai con, nút kế tiếp y CHÍNH LÀ con phải của z:
       │      thay z bằng y; con trái l của z thành con trái của y; con
       │      phải x của y giữ nguyên
       └─ (d) z có hai con, y nằm sâu hơn trong cây con phải gốc r:
              trước hết thay y bằng con phải x của nó; cho r làm con phải
              của y; rồi thay z bằng y và cho l làm con trái của y
                                │
                                ▼
       Mọi dòng của TREE-DELETE tốn hằng số, trừ lời gọi TREE-MINIMUM,
       nên xoá mất O(h)
                                │
                                ▼
       ĐỊNH LÝ 12.3: INSERT và DELETE cài đặt được trong O(h)
```

### Mục 12.4 (★) — Cây tìm kiếm nhị phân dựng ngẫu nhiên (Randomly built binary search trees, trang 299–303)

```text
       Chiều cao h thay đổi theo thứ tự chèn và xoá
       · chèn n khoá theo thứ tự tăng dần: cây là một chuỗi, h = n − 1
       · luôn có h ≥ ⌊lg n⌋ (Bài tập B.5-4)
                                │
                                ▼
       Khi có cả chèn và xoá, gần như chưa biết gì về chiều cao trung
       bình; nên chỉ xét cây dựng bằng CHÈN:
       CÂY DỰNG NGẪU NHIÊN trên n khoá = chèn các khoá vào cây rỗng theo
       một hoán vị ngẫu nhiên, mỗi hoán vị trong n! hoán vị có xác suất
       bằng nhau (khác với "chọn đều một cây trong mọi cây có thể")
                                │
                                ▼
       ĐỊNH LÝ 12.4: chiều cao kỳ vọng của cây dựng ngẫu nhiên trên n khoá
       phân biệt là O(lg n)
                                │
                                ▼
       Chứng minh (của Aslam):
       1. Xₙ = chiều cao; Yₙ = 2^Xₙ là "chiều cao mũ"
       2. Rₙ = thứ hạng của khoá gốc, đều trên {1, …, n}
          nếu Rₙ = i: cây con trái là cây dựng ngẫu nhiên trên i − 1 khoá,
          cây con phải trên n − i khoá, nên Yₙ = 2·max(Yᵢ₋₁, Yₙ₋ᵢ)
       3. biến chỉ báo Zₙ,ᵢ = I{Rₙ = i}, E[Zₙ,ᵢ] = 1/n, độc lập với
          Yᵢ₋₁ và Yₙ₋ᵢ
       4. E[Yₙ] ≤ (2/n) Σ (E[Yᵢ₋₁] + E[Yₙ₋ᵢ]) = (4/n) Σᵢ₌₀ⁿ⁻¹ E[Yᵢ]   (12.2)
       5. quy nạp: E[Yₙ] ≤ (1/4)·C(n+3, 3), dùng Σᵢ₌₀ⁿ⁻¹ C(i+3, 3) = C(n+3, 4)
       6. 2^x lồi, nên theo Jensen: 2^E[Xₙ] ≤ E[2^Xₙ] = E[Yₙ]
          ≤ (n³ + 6n² + 11n + 6)/24
       7. lấy lg hai vế: E[Xₙ] = O(lg n)
                                │
                                ▼
       Giống quicksort: trường hợp trung bình gần trường hợp tốt nhất hơn
       nhiều so với trường hợp xấu nhất
```

### Phần Bài toán cuối Chương 12 (Problems, trang 303–307)

```text
       12-1 Khoá trùng nhau: TREE-INSERT với n khoá bằng nhau tạo chuỗi,
            mất Θ(n²); so sánh ba cách sửa: cờ luân phiên trái/phải, danh
            sách khoá trùng tại nút, chọn trái/phải ngẫu nhiên
                                │
                                ▼
       12-2 Cây cơ số (radix tree, "trie"): lưu chuỗi bit, đi trái nếu bit
            là 0, phải nếu bit là 1; sắp xếp tập chuỗi có tổng độ dài n
            theo thứ tự từ điển trong Θ(n)
                                │
                                ▼
       12-3 Độ sâu trung bình của nút trong cây dựng ngẫu nhiên là O(lg n):
            tổng độ dài đường đi P(T) thoả P(T) = P(T_L) + P(T_R) + n − 1,
            dẫn tới truy hồi giống hệt quicksort ngẫu nhiên
                                │
                                ▼
       12-4 Số cây nhị phân khác nhau có n nút là số Catalan
            bₙ = C(2n, n)/(n + 1) ≈ 4ⁿ / (√π · n^{3/2})
```

### Ghi chú Chương 12 (Chapter notes, trang 307)

```text
       · Knuth: tài liệu tốt về cây tìm kiếm nhị phân và các biến thể
       · Cây tìm kiếm nhị phân được nhiều người phát hiện độc lập vào cuối
         thập niên 1950
       · Cây cơ số còn gọi là "trie", lấy từ các chữ giữa của "retrieval"
       · Hai ấn bản đầu xoá nút có hai con bằng cách CHÉP khoá của y vào z
         rồi xoá y → con trỏ ở nơi khác có thể trỏ vào nút đã bị xoá;
         ấn bản 3 bảo đảm xoá z thì đúng nút z bị xoá
       · Mục 15.5: dựng cây tìm kiếm nhị phân TỐI ƯU khi biết tần suất
       · Chứng minh của Mục 12.4 là của Aslam; Martínez và Roura đưa ra
         thuật toán chèn/xoá ngẫu nhiên giữ cây luôn "ngẫu nhiên"
```

## Ba câu hỏi chương này trả lời

1. **Một cây nhị phân cần thoả điều kiện gì để tìm kiếm nhanh, và "nhanh" ở đây là bao nhiêu?** Cây phải thoả tính chất cây tìm kiếm nhị phân: với mọi nút x, mọi khoá ở cây con trái ≤ x.key ≤ mọi khoá ở cây con phải. Khi đó mỗi phép so sánh loại bỏ hẳn một cây con, nên tìm kiếm, tìm nhỏ nhất, lớn nhất, kế tiếp, liền trước, chèn và xoá đều chỉ đi theo một đường đơn và chạy trong O(h), với h là chiều cao (Định lý 12.2 và 12.3). Riêng duyệt trung thứ tự in cả n khoá theo thứ tự tăng dần trong Θ(n) (Định lý 12.1). Ví dụ: trong cây có gốc 15 ở trên, tìm 13 chỉ thăm 4 nút 15 → 6 → 7 → 13 trong khi cây có 11 nút.
2. **Làm thế nào để xoá một nút mà vẫn giữ tính chất cây tìm kiếm nhị phân?** Dùng TRANSPLANT để thay một cây con bằng cây con khác, và chia bốn trường hợp: z không có con trái thì thay z bằng con phải; z chỉ có con trái thì thay z bằng con trái; z có hai con thì tìm nút kế tiếp y = TREE-MINIMUM(z.right) (y không có con trái), nếu y là con phải của z thì đưa thẳng y lên, còn nếu không thì trước hết thay y bằng con phải của y, gắn cây con phải của z vào y, rồi mới đưa y lên chỗ z; cuối cùng gắn cây con trái của z vào y. Toàn bộ mất O(h). Ví dụ: xoá gốc 15 của cây trên làm 17 (nút kế tiếp) trở thành gốc mới, 18 mất con trái.
3. **Nếu chèn khoá theo thứ tự ngẫu nhiên thì cây cao bao nhiêu?** Trung bình O(lg n) (Định lý 12.4). Đặt Xₙ là chiều cao, Yₙ = 2^Xₙ; từ truy hồi E[Yₙ] ≤ (4/n)·Σᵢ₌₀ⁿ⁻¹ E[Yᵢ] chứng minh được E[Yₙ] ≤ (1/4)·C(n+3, 3) = (n+3)(n+2)(n+1)/24; vì 2^x lồi nên 2^E[Xₙ] ≤ E[Yₙ], suy ra E[Xₙ] ≤ lg((n³ + 6n² + 11n + 6)/24) ≈ 3 lg n. Ngược lại, nếu chèn theo thứ tự đã sắp xếp thì cây là một chuỗi cao n − 1 và mọi thao tác mất Θ(n) — lý do cần cây cân bằng ở Chương 13.

## Khái niệm cần biết

- **Tập động (dynamic set) và các thao tác của nó:** tập phần tử có khoá, thay đổi theo thời gian, với các thao tác SEARCH, MINIMUM, MAXIMUM, PREDECESSOR, SUCCESSOR, INSERT, DELETE (đã định nghĩa ở phần mở đầu Phần III). Ví dụ: tập {2, 3, 4, 6, 7, 9, 13, 15, 17, 18, 20}; SUCCESSOR của 13 là 15, PREDECESSOR của 9 là 7. Quan trọng vì cây tìm kiếm nhị phân là cấu trúc đầu tiên trong sách hỗ trợ được cả bảy thao tác này với cùng một chi phí O(h).
- **Cây tìm kiếm nhị phân (binary search tree, BST):** cây nhị phân lưu bằng cấu trúc liên kết, mỗi nút có key, dữ liệu vệ tinh và ba con trỏ left, right, p, và các khoá thoả tính chất cây tìm kiếm nhị phân. Ví dụ: cây gốc 6, con trái 5 (có hai con 2 và 5), con phải 7 (có con phải 8). Đây là đối tượng của cả chương.
- **Tính chất cây tìm kiếm nhị phân (binary-search-tree property):** với mọi nút x, nếu y nằm trong cây con trái của x thì y.key ≤ x.key; nếu y nằm trong cây con phải thì y.key ≥ x.key. Lưu ý điều kiện áp dụng cho TOÀN BỘ cây con, không chỉ cho con trực tiếp. Ví dụ: cây gốc 10, con trái 5, con phải của 5 là 12 — mỗi cặp cha–con đều "đúng hướng" (12 > 5) nhưng cây vẫn sai vì 12 nằm trong cây con trái của 10 mà 12 > 10. Mọi thuật toán của chương dựa vào tính chất này.
- **Chiều cao (height) của cây:** số cạnh trên đường đi dài nhất từ gốc xuống một lá. Ví dụ: cây {2, 5, 5, 6, 7, 8} có thể cao 2 hoặc cao 4 tuỳ hình dạng; n khoá chèn theo thứ tự tăng dần tạo cây cao n − 1. Quan trọng vì mọi thao tác truy vấn và cập nhật mất O(h).
- **Duyệt trung thứ tự (inorder tree walk):** in cây con trái, in gốc, in cây con phải. Ví dụ: cây gốc 15 ở Mục 12.2 cho 2, 3, 4, 6, 7, 9, 13, 15, 17, 18, 20. Quan trọng vì nó biến cây thành dãy đã sắp xếp trong Θ(n) và định nghĩa "nút kế tiếp", "nút liền trước".
- **Duyệt tiền thứ tự (preorder) và hậu thứ tự (postorder):** in gốc trước hai cây con, hoặc in gốc sau hai cây con. Ví dụ: cây gốc 6 (5(2, 5), 7(—, 8)) duyệt tiền thứ tự cho 6, 5, 2, 5, 7, 8; hậu thứ tự cho 2, 5, 5, 8, 7, 6. Chương chỉ nhắc tên, dùng ở Bài tập 12.1-4.
- **Nút kế tiếp (successor) và nút liền trước (predecessor):** nút đứng ngay sau (ngay trước) x trong thứ tự duyệt trung thứ tự; với khoá phân biệt, kế tiếp là nút có khoá nhỏ nhất lớn hơn x.key. Ví dụ: kế tiếp của 15 là 17 (nhỏ nhất trong cây con phải), kế tiếp của 13 là 15 (đi lên tới khi gặp một nút là con trái của cha). Quan trọng vì TREE-DELETE dùng nút kế tiếp để thay nút có hai con.
- **Con trỏ theo sau (trailing pointer):** con trỏ y luôn trỏ vào cha của con trỏ đang dò x. Ví dụ: khi chèn 13, x đi 12 → 18 → 15 → NIL, còn y đi NIL → 12 → 18 → 15; lúc x = NIL thì y = 15 chính là nút cần gắn con mới. Cần thiết vì khi phát hiện NIL, ta đã đi quá nút cần sửa một bước.
- **TRANSPLANT (cấy ghép cây con):** thủ tục thay cây con gốc u bằng cây con gốc v trong vị trí con của cha u. Ví dụ: TRANSPLANT(T, 13, 9) trên cây gốc 15 làm 9 thành con phải của 7 và 9.p = 7. Là viên gạch để viết TREE-DELETE gọn gàng và cũng được dùng lại ở cây đỏ-đen (Chương 13).
- **Cây tìm kiếm nhị phân dựng ngẫu nhiên (randomly built binary search tree):** cây thu được khi chèn n khoá phân biệt vào cây rỗng theo một hoán vị chọn đều trong n! hoán vị. Ví dụ với n = 3 khoá {1, 2, 3}: 6 hoán vị cho 5 hình dạng cây; cây có gốc 2 xuất hiện từ hai hoán vị (2,1,3) và (2,3,1) nên có xác suất 2/6 = 1/3, mỗi cây chuỗi còn lại có xác suất 1/6 — khác với chọn đều 5 cây (mỗi cây 1/5). Là mô hình xác suất của Mục 12.4.
- **Chiều cao mũ (exponential height):** Yₙ = 2^Xₙ với Xₙ là chiều cao. Ví dụ: cây 3 nút có gốc 2 cao 1 nên Y = 2; cây chuỗi cao 2 nên Y = 4; với cây dựng ngẫu nhiên n = 3: E[Y₃] = (1/3)·2 + (2/3)·4 = 10/3. Thủ thuật này cho phép chặn max(Yᵢ₋₁, Yₙ₋ᵢ) bằng tổng Yᵢ₋₁ + Yₙ₋ᵢ mà không mất nhiều, vì sai một hằng số nhân trên Yₙ chỉ là sai một hằng số cộng trên Xₙ.
- **Thứ hạng (rank) của khoá:** vị trí của khoá nếu xếp tập khoá theo thứ tự tăng dần. Ví dụ: trong {3, 8, 11, 20}, khoá 11 có thứ hạng 3. Trong Mục 12.4, thứ hạng Rₙ của khoá gốc quyết định cây con trái có Rₙ − 1 khoá.
- **Biến ngẫu nhiên chỉ báo (indicator random variable):** I{A} bằng 1 nếu sự kiện A xảy ra, 0 nếu không; E[I{A}] = Pr{A} (Bổ đề 5.1 ở Chương 5). Ví dụ: Zₙ,ᵢ = I{Rₙ = i}, E[Zₙ,ᵢ] = 1/n. Dùng để viết Yₙ thành tổng và lấy kỳ vọng từng số hạng.
- **Bất đẳng thức Jensen (Jensen's inequality):** với hàm lồi f, f(E[X]) ≤ E[f(X)] (Phụ lục C, công thức C.26). Ví dụ: X nhận 0 và 2 với xác suất 1/2 mỗi giá trị; 2^E[X] = 2¹ = 2 ≤ E[2^X] = (1 + 4)/2 = 2,5. Dùng để chuyển chặn trên của E[Yₙ] thành chặn trên của E[Xₙ].
- **Cây cơ số / trie (radix tree):** cây lưu chuỗi bit, khoá của mỗi nút xác định bởi đường đi từ gốc (bit 0 đi trái, bit 1 đi phải). Ví dụ: lưu {1011, 10, 011, 100, 0}; duyệt tiền thứ tự cho 0, 011, 10, 100, 1011. Xuất hiện ở Bài toán 12-2.
- **Số Catalan (Catalan number):** bₙ = C(2n, n)/(n + 1), số cây nhị phân khác nhau có n nút. Ví dụ: b₀ = 1, b₁ = 1, b₂ = 2, b₃ = 5, b₄ = 14. Xuất hiện ở Bài toán 12-4 và lại xuất hiện ở Chương 15 (số cách đặt ngoặc).

## Nội dung chi tiết

### 1. Phần mở đầu Chương 12 (trang 286)

Cấu trúc dữ liệu cây tìm kiếm hỗ trợ nhiều thao tác của tập động: SEARCH (tìm kiếm), MINIMUM (nhỏ nhất), MAXIMUM (lớn nhất), PREDECESSOR (liền trước), SUCCESSOR (kế tiếp), INSERT (chèn) và DELETE (xoá). Vì vậy cùng một cây tìm kiếm có thể vừa dùng làm từ điển (tìm, chèn, xoá theo khoá) vừa dùng làm hàng đợi ưu tiên (lấy phần tử nhỏ nhất hoặc lớn nhất).

Các thao tác cơ bản trên cây tìm kiếm nhị phân mất thời gian tỉ lệ với chiều cao cây. Với một cây nhị phân đầy đủ n nút, các thao tác này mất Θ(lg n) trong trường hợp xấu nhất; nếu cây là một chuỗi tuyến tính n nút, cùng các thao tác đó mất Θ(n). Mục 12.4 sẽ chỉ ra rằng chiều cao kỳ vọng của một cây dựng ngẫu nhiên là O(lg n), nên trên cây như vậy các thao tác cơ bản mất Θ(lg n) trung bình.

Trong thực tế không phải lúc nào cũng bảo đảm được cây được dựng ngẫu nhiên, nhưng có thể thiết kế các biến thể có bảo đảm tốt cho trường hợp xấu nhất. Chương 13 trình bày cây đỏ-đen, có chiều cao O(lg n); Chương 18 giới thiệu cây B, đặc biệt phù hợp để duy trì cơ sở dữ liệu trên bộ nhớ ngoài (đĩa). Chương 12 lần lượt trình bày tính chất cơ bản của cây tìm kiếm nhị phân, cách duyệt cây để in khoá theo thứ tự, cách tìm một giá trị, tìm phần tử nhỏ nhất và lớn nhất, tìm phần tử liền trước và kế tiếp, và cách chèn, xoá. Các tính chất toán học cơ bản của cây nằm ở Phụ lục B ([PB-tap-hop-va-cau-truc-roi-rac.md](PB-tap-hop-va-cau-truc-roi-rac.md)).

### 2. Cây tìm kiếm nhị phân là gì (12.1 What is a binary search tree?, trang 286–289)

#### Cách biểu diễn

Đúng như tên gọi, cây tìm kiếm nhị phân được tổ chức thành một cây nhị phân. Ta biểu diễn cây bằng cấu trúc dữ liệu liên kết, mỗi nút là một đối tượng. Ngoài khoá (key) và dữ liệu vệ tinh (satellite data), mỗi nút có ba thuộc tính *left*, *right* và *p*, lần lượt trỏ tới con trái, con phải và cha của nút. Nếu thiếu con hoặc thiếu cha, thuộc tính tương ứng chứa giá trị NIL. Nút gốc là nút duy nhất có cha là NIL. Cây T có thuộc tính *T.root* trỏ tới gốc.

#### Tính chất cây tìm kiếm nhị phân

Khoá trong cây luôn được lưu sao cho thoả **tính chất cây tìm kiếm nhị phân**:

> Cho x là một nút của cây tìm kiếm nhị phân. Nếu y là một nút trong cây con trái của x thì y.key ≤ x.key. Nếu y là một nút trong cây con phải của x thì y.key ≥ x.key.

**Hình: hai cây tìm kiếm nhị phân trên cùng tập khoá (Figure 12.1 trong sách).** Tập khoá là {2, 5, 5, 6, 7, 8} (khoá 5 xuất hiện hai lần).

```text
   (a) 6 nút, chiều cao 2            (b) cùng 6 khoá, chiều cao 4
                                         (kém hiệu quả hơn)
            6                             2
          /   \                            \
         5     7                            5
        / \     \                            \
       2   5     8                            7
                                             / \
                                            6   8
                                           /
                                          5
```

Ở cây (a), gốc có khoá 6; các khoá 2, 5, 5 trong cây con trái đều không lớn hơn 6, còn các khoá 7, 8 trong cây con phải đều không nhỏ hơn 6. Tính chất đúng ở mọi nút: chẳng hạn khoá 5 ở con trái của gốc không nhỏ hơn khoá 2 trong cây con trái của nó và không lớn hơn khoá 5 trong cây con phải của nó. Ở cây (b), đường dài nhất là 2 → 5 → 7 → 6 → 5, gồm 4 cạnh. Hai cây biểu diễn cùng một tập giá trị; thời gian xấu nhất của hầu hết các thao tác tỉ lệ với chiều cao, nên cây (a) tốt hơn.

#### Duyệt trung thứ tự

Tính chất cây tìm kiếm nhị phân cho phép in mọi khoá theo thứ tự tăng dần bằng một thuật toán đệ quy đơn giản gọi là **duyệt cây trung thứ tự** (inorder tree walk). Tên gọi đến từ việc nó in khoá của gốc một cây con *ở giữa* việc in các giá trị của cây con trái và in các giá trị của cây con phải. Tương tự, **duyệt tiền thứ tự** (preorder tree walk) in gốc *trước* hai cây con, còn **duyệt hậu thứ tự** (postorder tree walk) in gốc *sau* hai cây con. Để in mọi phần tử của cây T, ta gọi INORDER-TREE-WALK(T.root).

```text
INORDER-TREE-WALK(x)
1  if x ≠ NIL
2      INORDER-TREE-WALK(x.left)
3      print x.key
4      INORDER-TREE-WALK(x.right)
```

- Dòng 1: cây con rỗng thì không làm gì.
- Dòng 2: in toàn bộ cây con trái (mọi khoá ≤ x.key).
- Dòng 3: in khoá của x.
- Dòng 4: in toàn bộ cây con phải (mọi khoá ≥ x.key).

Với cả hai cây ở Hình 12.1, duyệt trung thứ tự in 2, 5, 5, 6, 7, 8. Tính đúng của thuật toán suy ra trực tiếp bằng quy nạp từ tính chất cây tìm kiếm nhị phân: nếu hai lời gọi đệ quy in đúng thứ tự tăng dần các khoá của cây con trái và cây con phải, thì vì mọi khoá trái ≤ x.key ≤ mọi khoá phải, dãy "trái, x, phải" cũng tăng dần.

**Chạy tay trên cây (a):** gọi trên 6 → gọi trên 5 → gọi trên 2 → (con trái NIL) in **2** → (con phải NIL); trở về 5, in **5**; gọi trên 5 (con phải) in **5**; trở về 6, in **6**; gọi trên 7 → con trái NIL, in **7**, gọi trên 8 in **8**. Kết quả 2, 5, 5, 6, 7, 8.

Duyệt một cây n nút mất Θ(n), vì sau lời gọi đầu tiên, thủ tục tự gọi đệ quy đúng hai lần cho mỗi nút của cây — một lần cho con trái và một lần cho con phải. Định lý sau chứng minh chặt chẽ điều đó.

#### Định lý 12.1

> **Định lý 12.1.** Nếu x là gốc của một cây con n nút thì lời gọi INORDER-TREE-WALK(x) mất thời gian Θ(n).

**Chứng minh.** Gọi T(n) là thời gian của INORDER-TREE-WALK khi được gọi trên gốc của một cây con n nút. Vì thủ tục thăm cả n nút nên T(n) = Ω(n). Còn phải chứng minh T(n) = O(n).

Trên cây con rỗng, thủ tục chỉ tốn một hằng số nhỏ (cho phép thử x ≠ NIL), nên T(0) = c với một hằng số c > 0.

Với n > 0, giả sử thủ tục được gọi trên nút x có cây con trái k nút và cây con phải n − k − 1 nút. Thời gian thực hiện INORDER-TREE-WALK(x) bị chặn bởi T(n) ≤ T(k) + T(n − k − 1) + d, với hằng số d > 0 là chặn trên cho thời gian chạy thân thủ tục, không tính thời gian trong các lời gọi đệ quy.

Dùng phương pháp thay thế (substitution method, Chương 4), ta chứng minh T(n) ≤ (c + d)n + c. Với n = 0: (c + d)·0 + c = c = T(0). Với n > 0:

```text
T(n) ≤ T(k) + T(n − k − 1) + d
     = ((c + d)k + c) + ((c + d)(n − k − 1) + c) + d
     = (c + d)n + c − (c + d) + c + d
     = (c + d)n + c ,
```

hoàn tất chứng minh. ∎

(Kiểm tra dòng thứ ba: (c + d)k + (c + d)(n − k − 1) = (c + d)(n − 1) = (c + d)n − (c + d); cộng thêm c + c + d ra (c + d)n − (c + d) + c + c + d = (c + d)n + c.)

#### Ví dụ hôm nay

Duyệt trung thứ tự là cách mọi thư viện cây có thứ tự (như `std::map`, `std::set` trong C++ hay `TreeMap` trong Java — theo hiểu biết của người tổng hợp, chúng cài đặt bằng cây đỏ-đen, một loại cây tìm kiếm nhị phân cân bằng) lặp qua phần tử theo thứ tự khoá. Truy vấn khoảng ("mọi đơn hàng có mã từ 1000 tới 2000") cũng là duyệt trung thứ tự bắt đầu từ một nút kế tiếp. Duyệt tiền thứ tự và hậu thứ tự dùng nhiều trong trình biên dịch (in và tính giá trị cây cú pháp) và khi giải phóng bộ nhớ của cây (phải xoá con trước khi xoá cha).

### 3. Truy vấn trên cây tìm kiếm nhị phân (12.2 Querying a binary search tree, trang 289–294)

Ta thường cần tìm một khoá lưu trong cây. Ngoài SEARCH, cây tìm kiếm nhị phân còn hỗ trợ MINIMUM, MAXIMUM, SUCCESSOR và PREDECESSOR. Mục này chỉ ra mỗi thao tác đều chạy trong O(h) trên mọi cây có chiều cao h.

**Hình: cây dùng cho các truy vấn (Figure 12.2 trong sách).**

```text
                       15
                    /      \
                   6        18
                 /   \     /  \
                3     7   17   20
               / \     \
              2   4     13
                       /
                      9
```

Cây có 11 nút, chiều cao 4 (đường 15 → 6 → 7 → 13 → 9). Duyệt trung thứ tự cho 2, 3, 4, 6, 7, 9, 13, 15, 17, 18, 20. Theo chú thích hình: tìm khoá 13 đi theo đường 15 → 6 → 7 → 13; khoá nhỏ nhất 2 tìm bằng cách đi theo con trỏ *left* từ gốc; khoá lớn nhất 20 tìm bằng cách đi theo con trỏ *right*; nút kế tiếp của 15 là 17 vì 17 là khoá nhỏ nhất trong cây con phải của 15; nút 13 không có cây con phải, nên nút kế tiếp của nó là tổ tiên thấp nhất có con trái cũng là tổ tiên của 13, ở đây là 15.

#### Tìm kiếm (Searching)

Cho con trỏ tới gốc cây và một khoá k, TREE-SEARCH trả về con trỏ tới một nút có khoá k nếu có, ngược lại trả về NIL.

```text
TREE-SEARCH(x, k)
1  if x == NIL or k == x.key
2      return x
3  if k < x.key
4      return TREE-SEARCH(x.left, k)
5  else return TREE-SEARCH(x.right, k)
```

- Dòng 1–2: gặp NIL (không tìm thấy) hoặc gặp đúng khoá thì trả về x.
- Dòng 3–4: k nhỏ hơn x.key thì tìm tiếp trong cây con trái — theo tính chất cây tìm kiếm nhị phân, k không thể nằm trong cây con phải.
- Dòng 5: đối xứng, k lớn hơn thì tìm trong cây con phải.

Thủ tục bắt đầu ở gốc và đi theo một đường đơn xuống dưới. Các nút gặp trong quá trình đệ quy tạo thành một đường đơn từ gốc xuống, nên thời gian chạy là O(h).

**Chạy tay tìm 13:** x = 15, 13 < 15 → sang 6; 13 > 6 → sang 7; 13 > 7 → sang 13; 13 == 13 → trả về nút 13. Bốn nút được thăm.
**Chạy tay tìm 5 (không có trong cây):** 15 → 6 (5 < 15) → 3 (5 < 6) → 4 (5 > 3) → 4.right = NIL (5 > 4) → trả về NIL.

Có thể viết lại thủ tục theo kiểu lặp bằng cách "trải" đệ quy thành vòng **while**; trên đa số máy tính, bản lặp hiệu quả hơn:

```text
ITERATIVE-TREE-SEARCH(x, k)
1  while x ≠ NIL and k ≠ x.key
2      if k < x.key
3          x = x.left
4      else x = x.right
5  return x
```

Vòng lặp dừng khi gặp NIL hoặc gặp khoá; mỗi vòng xuống một mức. Bản đệ quy là đệ quy đuôi (lời gọi đệ quy là việc cuối cùng), nên trải thành vòng lặp không cần ngăn xếp.

#### Nhỏ nhất và lớn nhất (Minimum and maximum)

Luôn tìm được phần tử có khoá nhỏ nhất bằng cách đi theo con trỏ con trái từ gốc cho tới khi gặp NIL. Thủ tục sau trả về con trỏ tới phần tử nhỏ nhất của cây con gốc x (giả sử x ≠ NIL):

```text
TREE-MINIMUM(x)
1  while x.left ≠ NIL
2      x = x.left
3  return x
```

Tính chất cây tìm kiếm nhị phân bảo đảm TREE-MINIMUM đúng. Nếu x không có cây con trái thì, vì mọi khoá trong cây con phải của x đều ≥ x.key, khoá nhỏ nhất của cây con gốc x là x.key. Nếu x có cây con trái thì, vì không khoá nào trong cây con phải nhỏ hơn x.key và mọi khoá trong cây con trái không lớn hơn x.key, khoá nhỏ nhất nằm trong cây con gốc x.left.

Mã của TREE-MAXIMUM đối xứng:

```text
TREE-MAXIMUM(x)
1  while x.right ≠ NIL
2      x = x.right
3  return x
```

Cả hai thủ tục chạy trong O(h) vì, như TREE-SEARCH, dãy nút gặp tạo thành một đường đơn đi xuống từ gốc.

**Chạy tay:** TREE-MINIMUM(15): 15 → 6 → 3 → 2, 2.left = NIL, trả về 2. TREE-MAXIMUM(15): 15 → 18 → 20, trả về 20. TREE-MINIMUM(18) = 17; TREE-MINIMUM(7) = 7 (7 không có con trái).

#### Nút kế tiếp và nút liền trước (Successor and predecessor)

Cho một nút, đôi khi ta cần nút kế tiếp của nó trong thứ tự sắp xếp do duyệt trung thứ tự xác định. Nếu mọi khoá phân biệt, nút kế tiếp của x là nút có khoá nhỏ nhất lớn hơn x.key. Cấu trúc cây cho phép tìm nút kế tiếp mà không cần so sánh khoá. Thủ tục sau trả về nút kế tiếp của x nếu có, và NIL nếu x có khoá lớn nhất cây:

```text
TREE-SUCCESSOR(x)
1  if x.right ≠ NIL
2      return TREE-MINIMUM(x.right)
3  y = x.p
4  while y ≠ NIL and x == y.right
5      x = y
6      y = y.p
7  return y
```

Mã chia hai trường hợp:

- **x có cây con phải (dòng 1–2):** nút kế tiếp là nút trái nhất của cây con phải, tìm bằng TREE-MINIMUM(x.right). Ví dụ: nút kế tiếp của 15 là 17.
- **x không có cây con phải (dòng 3–7):** như Bài tập 12.2-6 yêu cầu chứng minh, nếu x có nút kế tiếp y thì y là tổ tiên thấp nhất của x mà con trái của y cũng là tổ tiên của x (quy ước mỗi nút là tổ tiên của chính nó). Để tìm y, ta đi ngược lên từ x cho tới khi gặp một nút là con trái của cha nó; cha đó là y. Vòng **while** ở dòng 4 tiếp tục chừng nào x còn là con *phải* của y. Ví dụ: nút kế tiếp của 13 là 15.

Lý do trực quan: nếu x không có cây con phải và x là con phải của cha, thì cha có khoá nhỏ hơn x (đã được in trước x), nên phải đi tiếp lên; lần đầu tiên đi lên từ một con *trái*, nút cha đó là nút đầu tiên có khoá lớn hơn mọi khoá đã đi qua, tức là nút được in ngay sau x.

**Chạy tay TREE-SUCCESSOR(13):** 13.right = NIL. y = 7. 13 == 7.right → x = 7, y = 6. 7 == 6.right → x = 6, y = 15. 6 là 15.left, vòng dừng. Trả về 15. ✓ (trong dãy 2, 3, 4, 6, 7, 9, **13, 15**, …)
**Chạy tay TREE-SUCCESSOR(4):** 4.right = NIL. y = 3; 4 == 3.right → x = 3, y = 6; 3 là 6.left → trả về 6. ✓
**Chạy tay TREE-SUCCESSOR(9):** 9.right = NIL. y = 13; 9 là 13.left → trả về 13. ✓
**Chạy tay TREE-SUCCESSOR(20):** y = 18; 20 == 18.right → x = 18, y = 15; 18 == 15.right → x = 15, y = NIL; vòng dừng, trả về NIL — 20 là khoá lớn nhất. ✓

Thời gian chạy TREE-SUCCESSOR trên cây chiều cao h là O(h), vì ta hoặc đi theo một đường đơn lên trên, hoặc đi theo một đường đơn xuống dưới. Thủ tục TREE-PREDECESSOR đối xứng với TREE-SUCCESSOR (sách để làm Bài tập 12.2-3) và cũng chạy trong O(h). Bản đối xứng do người tổng hợp viết:

```text
TREE-PREDECESSOR(x)        (người tổng hợp viết, không có trong sách)
1  if x.left ≠ NIL
2      return TREE-MAXIMUM(x.left)
3  y = x.p
4  while y ≠ NIL and x == y.left
5      x = y
6      y = y.p
7  return y
```

Chạy tay TREE-PREDECESSOR(9): 9.left = NIL; y = 13; 9 == 13.left → x = 13, y = 7; 13 là 7.right → trả về 7. ✓ (dãy …, **7, 9**, …)

Khi các khoá không phân biệt, sách định nghĩa nút kế tiếp và nút liền trước của x đơn giản là nút do TREE-SUCCESSOR(x) và TREE-PREDECESSOR(x) trả về.

#### Định lý 12.2

> **Định lý 12.2.** Ta có thể cài đặt các thao tác tập động SEARCH, MINIMUM, MAXIMUM, SUCCESSOR và PREDECESSOR sao cho mỗi thao tác chạy trong thời gian O(h) trên cây tìm kiếm nhị phân chiều cao h.

Chứng minh chính là các phân tích ở trên: mỗi thủ tục chỉ đi theo một đường đơn lên hoặc xuống, độ dài đường không vượt quá h, mỗi bước tốn hằng số. ∎

#### Ví dụ hôm nay

Các thao tác "tìm khoá nhỏ nhất ≥ k" (`lower_bound`), "phần tử kế tiếp", "phần tử liền trước" của `std::map` hay `TreeMap.ceilingKey/floorKey` trong Java chính là TREE-SEARCH kết hợp TREE-SUCCESSOR/TREE-PREDECESSOR trên cây cân bằng (theo hiểu biết của người tổng hợp). Đây là điểm mà bảng băm (Chương 11) không làm được: bảng băm trả lời "có khoá k không" trong O(1) kỳ vọng, nhưng không trả lời được "khoá liền sau k là gì" nhanh hơn việc quét toàn bộ bảng. Bộ lập lịch, sổ lệnh giao dịch (order book, cần giá mua cao nhất và giá bán thấp nhất), bộ đếm thời gian hết hạn đều cần loại truy vấn có thứ tự này.

### 4. Chèn và xoá (12.3 Insertion and deletion, trang 294–299)

Chèn và xoá làm tập động mà cây biểu diễn thay đổi. Cấu trúc dữ liệu phải được sửa để phản ánh thay đổi đó nhưng vẫn giữ tính chất cây tìm kiếm nhị phân. Sửa cây để chèn một phần tử mới tương đối đơn giản, còn xoá thì phức tạp hơn đôi chút.

#### Chèn (Insertion)

Để chèn giá trị mới v vào cây T, ta dùng TREE-INSERT. Thủ tục nhận một nút z với z.key = v, z.left = NIL, z.right = NIL, rồi sửa T và một số thuộc tính của z để z nằm ở vị trí thích hợp trong cây.

```text
TREE-INSERT(T, z)
 1  y = NIL
 2  x = T.root
 3  while x ≠ NIL
 4      y = x
 5      if z.key < x.key
 6          x = x.left
 7      else x = x.right
 8  z.p = y
 9  if y == NIL
10      T.root = z          // cây T rỗng
11  elseif z.key < y.key
12      y.left = z
13  else y.right = z
```

- Dòng 1–2: khởi tạo con trỏ dò x ở gốc, con trỏ theo sau y = NIL.
- Dòng 3–7: giống TREE-SEARCH, x đi theo một đường đơn xuống dưới, rẽ trái hay phải tuỳ so sánh z.key với x.key, cho tới khi x = NIL. Vị trí NIL đó chính là chỗ cần đặt z. Con trỏ y luôn là cha của x (**con trỏ theo sau**, trailing pointer); cần y vì khi tìm thấy NIL, việc tìm đã đi quá nút cần sửa một bước.
- Dòng 8–13: đặt các con trỏ để gắn z: cha của z là y; nếu y = NIL thì cây rỗng và z thành gốc; ngược lại z thành con trái hoặc con phải của y tuỳ so sánh khoá.

Lưu ý: dòng 5 dùng "<", nên khoá *bằng* x.key luôn đi sang phải (dòng 7) — chi tiết này gây ra vấn đề ở Bài toán 12-1.

Giống các thao tác cơ bản khác, TREE-INSERT chạy trong O(h).

**Hình: chèn khoá 13 (Figure 12.3 trong sách).** Cây trước khi chèn:

```text
              12
            /    \
           5      18
          / \    /  \
         2   9  15   19
                  \
                   17
```

Chạy tay TREE-INSERT với z.key = 13:

| Bước | x trước so sánh | So sánh | y sau bước | x sau bước |
|---|---|---|---|---|
| khởi tạo | — | — | NIL | 12 |
| 1 | 12 | 13 ≥ 12 → sang phải | 12 | 18 |
| 2 | 18 | 13 < 18 → sang trái | 18 | 15 |
| 3 | 15 | 13 < 15 → sang trái | 15 | NIL |

Vòng dừng; z.p = 15; vì 13 < 15 nên 15.left = z. Cây sau khi chèn (trong hình của sách, các nút 12, 18, 15 trên đường đi được tô nhạt, cạnh mới 15–13 vẽ nét đứt):

```text
              12
            /    \
           5      18
          / \    /  \
         2   9  15   19
               /  \
             13    17
```

#### Xoá (Deletion)

Chiến lược tổng thể để xoá nút z khỏi cây T có ba trường hợp cơ bản, trong đó một trường hợp hơi khó:

- z không có con: chỉ cần sửa cha của z để thay z bằng NIL.
- z có đúng một con: đưa con đó lên chiếm vị trí của z, bằng cách sửa cha của z để thay z bằng con của z.
- z có hai con: tìm nút kế tiếp y của z — y phải nằm trong cây con phải của z — và để y chiếm vị trí của z. Phần còn lại của cây con phải ban đầu của z trở thành cây con phải mới của y, và cây con trái của z thành cây con trái mới của y. Trường hợp này khó vì kết quả phụ thuộc y có phải là con phải của z hay không.

Thủ tục xoá nhận con trỏ tới T và z, và tổ chức lại các trường hợp hơi khác so với ba trường hợp trên, thành bốn trường hợp:

- Nếu z không có con trái (phần (a)), thay z bằng con phải của nó — con phải có thể là NIL hoặc không. Khi con phải là NIL, đây là trường hợp z không có con; khi con phải khác NIL, đây là trường hợp z chỉ có một con, là con phải.
- Nếu z chỉ có một con và đó là con trái (phần (b)), thay z bằng con trái.
- Ngược lại, z có cả con trái lẫn con phải. Tìm nút kế tiếp y của z; y nằm trong cây con phải của z và không có con trái (Bài tập 12.2-5). Ta muốn tách y khỏi vị trí hiện tại và đưa nó thay z.
  - Nếu y là con phải của z (phần (c)), thay z bằng y, giữ nguyên con phải của y.
  - Ngược lại, y nằm trong cây con phải của z nhưng không phải con phải của z (phần (d)). Khi đó trước hết thay y bằng con phải của chính nó, rồi thay z bằng y.

**Hình: bốn trường hợp xoá nút z (Figure 12.4 trong sách).** Nút z có thể là gốc, con trái của nút q, hoặc con phải của q. Dấu "…" chỉ một cây con tuỳ ý.

```text
(a) z không có con trái: thay z bằng con phải r (r có thể là NIL)

        q                          q
        |                          |
        z            ═══►          r
       / \                        / \
    NIL   r                     …   …
         / \
       …   …

(b) z có con trái l, không có con phải: thay z bằng l

        q                          q
        |                          |
        z            ═══►          l
       / \                        / \
      l   NIL                   …   …
     / \
   …   …

(c) z có hai con; con phải của z chính là nút kế tiếp y; y không có
    con trái, con phải của y là x. Thay z bằng y, cho l làm con trái
    của y, giữ x làm con phải của y.

        q                          q
        |                          |
        z            ═══►          y
       / \                        / \
      l   y                      l   x
         / \                         ⋮
      NIL   x
            ⋮

(d) z có hai con (l và r); nút kế tiếp y ≠ r nằm sâu trong cây con gốc
    r; y không có con trái, con phải của y là x.
    Bước 1: thay y bằng x, cho r làm con phải của y.
    Bước 2: thay z bằng y (y thành con của q), cho l làm con trái của y.

        q                q                              q
        |                |                              |
        z        ═══►    z        y          ═══►       y
       / \              /        / \                   / \
      l   r            l      NIL   r                 l   r
          ⋮                         ⋮                     ⋮
          y                         x                     x
         / \
      NIL   x
```

#### Thủ tục TRANSPLANT

Để di chuyển cây con bên trong cây, sách định nghĩa thủ tục phụ TRANSPLANT, thay một cây con (ở vị trí con của cha nó) bằng một cây con khác. Khi TRANSPLANT thay cây con gốc u bằng cây con gốc v, cha của u trở thành cha của v, và cha của u có v làm con ở đúng vị trí trước đây của u.

```text
TRANSPLANT(T, u, v)
1  if u.p == NIL
2      T.root = v
3  elseif u == u.p.left
4      u.p.left = v
5  else u.p.right = v
6  if v ≠ NIL
7      v.p = u.p
```

- Dòng 1–2: u là gốc của T, nên v thành gốc.
- Dòng 3–4: u là con trái của cha, cập nhật u.p.left.
- Dòng 5: u là con phải của cha, cập nhật u.p.right.
- Dòng 6–7: v được phép là NIL; nếu v khác NIL thì cập nhật v.p.

TRANSPLANT không cập nhật v.left và v.right; làm hay không làm việc đó là trách nhiệm của nơi gọi TRANSPLANT. TRANSPLANT cũng không động tới u: u vẫn giữ con trỏ cũ của nó.

#### Thủ tục TREE-DELETE

```text
TREE-DELETE(T, z)
 1  if z.left == NIL
 2      TRANSPLANT(T, z, z.right)
 3  elseif z.right == NIL
 4      TRANSPLANT(T, z, z.left)
 5  else y = TREE-MINIMUM(z.right)
 6      if y.p ≠ z
 7          TRANSPLANT(T, y, y.right)
 8          y.right = z.right
 9          y.right.p = y
10      TRANSPLANT(T, z, y)
11      y.left = z.left
12      y.left.p = y
```

TREE-DELETE thực hiện bốn trường hợp như sau:

- Dòng 1–2: z không có con trái (trường hợp (a)) — thay z bằng z.right.
- Dòng 3–4: z có con trái nhưng không có con phải (trường hợp (b)) — thay z bằng z.left.
- Dòng 5–12: z có hai con (trường hợp (c) và (d)). Dòng 5 tìm y, nút kế tiếp của z. Vì z có cây con phải khác rỗng, nút kế tiếp phải là nút có khoá nhỏ nhất trong cây con đó, nên gọi TREE-MINIMUM(z.right). Như đã nói, y không có con trái. Ta muốn tách y khỏi vị trí hiện tại và đưa nó thay z.
  - Nếu y là con phải của z (trường hợp (c), điều kiện dòng 6 sai), dòng 10–12 thay z (ở vị trí con của cha z) bằng y, và thay con trái của y (đang là NIL) bằng con trái của z.
  - Nếu y không phải con phải của z (trường hợp (d)), dòng 7–9 thay y (ở vị trí con của cha y) bằng con phải của y, và biến con phải của z thành con phải của y; sau đó dòng 10–12 thay z bằng y và cho con trái của z làm con trái của y. (Sách in nhầm "If y is not z's left child" ở đoạn này; xem khối Lưu ý.)

Mọi dòng của TREE-DELETE, kể cả các lời gọi TRANSPLANT, tốn thời gian hằng số, trừ lời gọi TREE-MINIMUM ở dòng 5. Vì vậy TREE-DELETE chạy trong O(h).

**Chạy tay trên cây gốc 15 (Hình 12.2), mỗi lần xoá đều làm trên cây ban đầu** (ví dụ của người tổng hợp):

1. *Xoá 4 (lá, trường hợp (a) với con phải NIL):* 4.left = NIL → TRANSPLANT(T, 4, NIL): 4 là con phải của 3 nên 3.right = NIL. Cây còn lại giữ nguyên, chỉ mất 4.
2. *Xoá 13 (chỉ có con trái 9, trường hợp (b)):* 13.left = 9 ≠ NIL, 13.right = NIL → TRANSPLANT(T, 13, 9): 13 là con phải của 7, nên 7.right = 9, 9.p = 7.
3. *Xoá 6 (hai con, trường hợp (c)):* y = TREE-MINIMUM(6.right) = TREE-MINIMUM(7) = 7 (7 không có con trái). y.p = 6 = z nên bỏ qua dòng 7–9. TRANSPLANT(T, 6, 7): 6 là con trái của 15, nên 15.left = 7, 7.p = 15. Dòng 11–12: 7.left = 3, 3.p = 7. Kết quả:

```text
                       15
                    /      \
                   7        18
                 /   \     /  \
                3     13  17   20
               / \   /
              2   4 9
```

4. *Xoá 15 (gốc, hai con, trường hợp (d)):* y = TREE-MINIMUM(18) = 17. y.p = 18 ≠ z. Dòng 7: TRANSPLANT(T, 17, 17.right = NIL): 17 là con trái của 18 nên 18.left = NIL. Dòng 8–9: 17.right = 18, 18.p = 17. Dòng 10: TRANSPLANT(T, 15, 17): 15.p = NIL nên T.root = 17, 17.p = NIL. Dòng 11–12: 17.left = 6, 6.p = 17. Kết quả:

```text
                       17
                    /      \
                   6        18
                 /   \        \
                3     7        20
               / \     \
              2   4     13
                       /
                      9
```

Duyệt trung thứ tự cây mới: 2, 3, 4, 6, 7, 9, 13, 17, 18, 20 — đúng dãy cũ bỏ 15.

#### Định lý 12.3

> **Định lý 12.3.** Ta có thể cài đặt các thao tác tập động INSERT và DELETE sao cho mỗi thao tác chạy trong thời gian O(h) trên cây tìm kiếm nhị phân chiều cao h.

Chứng minh là các phân tích ở trên: TREE-INSERT đi một đường đơn xuống; TREE-DELETE gồm hằng số bước cộng một lời gọi TREE-MINIMUM đi một đường đơn xuống. ∎

#### Ví dụ hôm nay

Cách xoá "đưa nút kế tiếp lên thay chỗ" là cách chuẩn trong mọi cây tìm kiếm cân bằng; cây đỏ-đen ở Chương 13 dùng lại gần như nguyên TRANSPLANT và khung TREE-DELETE, chỉ thêm bước sửa màu. Việc ấn bản 3 bảo đảm "xoá z thì đúng nút z bị xoá" (thay vì chép khoá) quan trọng trong phần mềm thực tế: các thư viện thường bảo đảm rằng con trỏ/iterator tới các phần tử khác vẫn hợp lệ sau khi xoá một phần tử (theo hiểu biết của người tổng hợp, `std::map` của C++ có bảo đảm này), điều mà cách chép khoá sẽ phá vỡ. Cây tìm kiếm nhị phân *không cân bằng* như trong chương ít khi dùng trực tiếp trong sản phẩm vì rủi ro suy biến thành chuỗi khi dữ liệu đến theo thứ tự (ví dụ chèn mã tăng dần, dấu thời gian tăng dần).

### 5. Cây tìm kiếm nhị phân dựng ngẫu nhiên (? 12.4 Randomly built binary search trees, trang 299–303)

#### Đặt vấn đề

Mọi thao tác cơ bản chạy trong O(h), nhưng chiều cao h thay đổi khi chèn và xoá phần tử. Chẳng hạn, nếu chèn n phần tử theo thứ tự tăng ngặt, cây sẽ là một chuỗi có chiều cao n − 1. Mặt khác, Bài tập B.5-4 cho thấy h ≥ ⌊lg n⌋ (một cây nhị phân chiều cao h có nhiều nhất 2^(h+1) − 1 nút). Giống quicksort, có thể chứng minh rằng hành vi trung bình gần với trường hợp tốt nhất hơn nhiều so với trường hợp xấu nhất.

Đáng tiếc là hiểu biết về chiều cao trung bình của cây tìm kiếm nhị phân khi dùng cả chèn lẫn xoá còn rất ít. Khi cây được tạo chỉ bằng phép chèn, phân tích dễ hơn. Vì vậy sách định nghĩa **cây tìm kiếm nhị phân dựng ngẫu nhiên** trên n khoá là cây thu được khi chèn các khoá theo thứ tự ngẫu nhiên vào một cây ban đầu rỗng, trong đó mỗi hoán vị trong n! hoán vị của các khoá đầu vào có xác suất bằng nhau. (Bài tập 12.4-3 yêu cầu chỉ ra khái niệm này khác với giả định mọi cây tìm kiếm nhị phân trên n khoá đều có xác suất bằng nhau — xem ví dụ n = 3 ở mục Khái niệm cần biết: cây gốc 2 có xác suất 1/3 chứ không phải 1/5.)

#### Định lý 12.4 và chứng minh

> **Định lý 12.4.** Chiều cao kỳ vọng của một cây tìm kiếm nhị phân dựng ngẫu nhiên trên n khoá phân biệt là O(lg n).

**Bước 1 — ba biến ngẫu nhiên.** Ký hiệu Xₙ là chiều cao của cây dựng ngẫu nhiên trên n khoá, và định nghĩa **chiều cao mũ** Yₙ = 2^Xₙ. Khi dựng cây trên n khoá, một khoá được chọn làm gốc (khoá chèn đầu tiên); gọi Rₙ là biến ngẫu nhiên chứa *thứ hạng* của khoá này trong tập n khoá, tức vị trí của nó khi tập khoá được sắp xếp. Rₙ nhận mỗi giá trị trong {1, 2, …, n} với xác suất như nhau. Nếu Rₙ = i thì cây con trái của gốc là cây dựng ngẫu nhiên trên i − 1 khoá, cây con phải là cây dựng ngẫu nhiên trên n − i khoá. Vì chiều cao của cây nhị phân lớn hơn 1 so với chiều cao lớn hơn trong hai cây con của gốc, chiều cao mũ bằng hai lần chiều cao mũ lớn hơn của hai cây con. Biết Rₙ = i thì

  Yₙ = 2·max(Yᵢ₋₁, Yₙ₋ᵢ).

Trường hợp cơ sở: Y₁ = 1 vì chiều cao mũ của cây 1 nút là 2⁰ = 1; để tiện, quy ước Y₀ = 0.

**Bước 2 — biến chỉ báo.** Định nghĩa Zₙ,₁, Zₙ,₂, …, Zₙ,ₙ với Zₙ,ᵢ = I{Rₙ = i}. Vì Pr{Rₙ = i} = 1/n với i = 1, 2, …, n, theo Bổ đề 5.1 (kỳ vọng của biến chỉ báo bằng xác suất của sự kiện):

  E[Zₙ,ᵢ] = 1/n,   (12.1)

với i = 1, 2, …, n. Vì đúng một Zₙ,ᵢ bằng 1 và các biến còn lại bằng 0:

  Yₙ = Σᵢ₌₁ⁿ Zₙ,ᵢ·(2·max(Yᵢ₋₁, Yₙ₋ᵢ)).

Mục tiêu là chứng minh E[Yₙ] là một đa thức theo n, từ đó suy ra E[Xₙ] = O(lg n).

**Bước 3 — tính độc lập.** Biến chỉ báo Zₙ,ᵢ = I{Rₙ = i} độc lập với Yᵢ₋₁ và Yₙ₋ᵢ. Khi đã chọn Rₙ = i, cây con trái (chiều cao mũ Yᵢ₋₁) được dựng ngẫu nhiên trên i − 1 khoá có thứ hạng nhỏ hơn i. Cây con này giống hệt mọi cây dựng ngẫu nhiên khác trên i − 1 khoá; ngoài số khoá, cấu trúc của nó hoàn toàn không bị ảnh hưởng bởi việc chọn Rₙ = i, nên Yᵢ₋₁ và Zₙ,ᵢ độc lập. Tương tự, cây con phải (chiều cao mũ Yₙ₋ᵢ) được dựng ngẫu nhiên trên n − i khoá có thứ hạng lớn hơn i, cấu trúc độc lập với Rₙ. (Lý do sâu xa: với hoán vị ngẫu nhiên đều, thứ tự tương đối của các khoá nhỏ hơn gốc là một hoán vị ngẫu nhiên đều của chúng, bất kể khoá nào đứng đầu.)

**Bước 4 — lấy kỳ vọng.** (Đọc từ ảnh trang 301.)

```text
E[Yₙ] = E[ Σᵢ₌₁ⁿ Zₙ,ᵢ (2·max(Yᵢ₋₁, Yₙ₋ᵢ)) ]
      = Σᵢ₌₁ⁿ E[Zₙ,ᵢ (2·max(Yᵢ₋₁, Yₙ₋ᵢ))]        (tuyến tính của kỳ vọng)
      = Σᵢ₌₁ⁿ E[Zₙ,ᵢ] · E[2·max(Yᵢ₋₁, Yₙ₋ᵢ)]      (độc lập)
      = Σᵢ₌₁ⁿ (1/n) · E[2·max(Yᵢ₋₁, Yₙ₋ᵢ)]        (theo (12.1))
      = (2/n) Σᵢ₌₁ⁿ E[max(Yᵢ₋₁, Yₙ₋ᵢ)]            (theo (C.22): E[aX] = aE[X])
      ≤ (2/n) Σᵢ₌₁ⁿ (E[Yᵢ₋₁] + E[Yₙ₋ᵢ])           (theo Bài tập C.3-4)
```

Bài tập C.3-4 là bất đẳng thức E[max(X, Y)] ≤ E[X] + E[Y] với X, Y không âm — đúng vì max(X, Y) ≤ X + Y khi cả hai không âm. Đây là chỗ thủ thuật chiều cao mũ phát huy tác dụng: chặn max bằng tổng chỉ làm mất một hằng số nhân trên Yₙ, tương ứng một hằng số cộng trên Xₙ; nếu làm thẳng trên Xₙ thì chặn max(Xᵢ₋₁, Xₙ₋ᵢ) bằng Xᵢ₋₁ + Xₙ₋ᵢ sẽ quá thô (dẫn tới chặn O(n)).

Mỗi số hạng E[Y₀], E[Y₁], …, E[Yₙ₋₁] xuất hiện hai lần trong tổng cuối — một lần dưới dạng E[Yᵢ₋₁] và một lần dưới dạng E[Yₙ₋ᵢ] — nên ta có truy hồi

  E[Yₙ] ≤ (4/n) Σᵢ₌₀ⁿ⁻¹ E[Yᵢ].   (12.2)

**Bước 5 — giải truy hồi bằng phương pháp thay thế.** Ta chứng minh với mọi số nguyên dương n:

  E[Yₙ] ≤ (1/4)·C(n+3, 3),

trong đó C(a, b) là tổ hợp chập b của a. Ta dùng đẳng thức

  Σᵢ₌₀ⁿ⁻¹ C(i+3, 3) = C(n+3, 4)   (12.3)

(Bài tập 12.4-1 yêu cầu chứng minh; đây là "đẳng thức gậy khúc côn cầu" của tam giác Pascal. Kiểm tra n = 2: C(3,3) + C(4,3) = 1 + 4 = 5 = C(5,4). ✓)

Trường hợp cơ sở: 0 = Y₀ = E[Y₀] ≤ (1/4)·C(3, 3) = 1/4, và 1 = Y₁ = E[Y₁] ≤ (1/4)·C(1+3, 3) = (1/4)·4 = 1. Cả hai đúng. Bước quy nạp (đọc từ ảnh trang 302):

```text
E[Yₙ] ≤ (4/n) Σᵢ₌₀ⁿ⁻¹ E[Yᵢ]
      ≤ (4/n) Σᵢ₌₀ⁿ⁻¹ (1/4)·C(i+3, 3)           (giả thiết quy nạp)
      = (1/n) Σᵢ₌₀ⁿ⁻¹ C(i+3, 3)
      = (1/n) · C(n+3, 4)                       (theo (12.3))
      = (1/n) · (n+3)! / (4! (n−1)!)
      = (1/4) · (n+3)! / (3! n!)
      = (1/4) · C(n+3, 3) .
```

(Kiểm tra dòng thứ sáu: (1/n)·(n+3)!/(4!·(n−1)!) = (n+3)!/(4·3!·n·(n−1)!) = (1/4)·(n+3)!/(3!·n!). ✓) Như đã nói ở khối Lưu ý, bước quy nạp áp dụng cho n ≥ 2.

**Bước 6 — từ E[Yₙ] sang E[Xₙ].** Hàm f(x) = 2^x lồi (Bài tập 12.4-4). Vì vậy áp dụng được bất đẳng thức Jensen (C.26):

  2^E[Xₙ] ≤ E[2^Xₙ] = E[Yₙ],

nên

```text
2^E[Xₙ] ≤ (1/4) · C(n+3, 3)
        = (1/4) · (n+3)(n+2)(n+1)/6
        = (n³ + 6n² + 11n + 6)/24 .
```

(Kiểm tra: (n+1)(n+2) = n² + 3n + 2; nhân (n+3): n³ + 3n² + 2n + 3n² + 9n + 6 = n³ + 6n² + 11n + 6. ✓)

Lấy logarit hai vế được E[Xₙ] ≤ lg((n³ + 6n² + 11n + 6)/24) = 3 lg n + O(1), tức E[Xₙ] = O(lg n). ∎

**Kiểm tra số với n nhỏ (người tổng hợp):**

| n | E[Yₙ] thực tế | Vế phải (12.2) dùng giá trị thực | Chặn (1/4)·C(n+3, 3) |
|---|---|---|---|
| 1 | 1 | — (cơ sở) | 1 |
| 2 | 2 (mọi cây 2 nút cao 1) | (4/2)(0 + 1) = 2 | 2,5 |
| 3 | (1/3)·2 + (2/3)·4 = 10/3 ≈ 3,33 | (4/3)(0 + 1 + 2) = 4 | 5 |

Với n = 3, chặn cho E[X₃] ≤ lg 5 ≈ 2,32, trong khi E[X₃] thực tế = (1/3)·1 + (2/3)·2 = 5/3 ≈ 1,67.

#### Ví dụ hôm nay

Kết quả "chèn ngẫu nhiên cho cây cao O(lg n)" là nền của các cấu trúc ngẫu nhiên hoá như treap (mỗi nút có thêm một độ ưu tiên ngẫu nhiên, khiến cây luôn có hình dạng như cây dựng ngẫu nhiên bất kể thứ tự chèn — xem Bài toán 13-4 ở Chương 13) và danh sách nhảy (skip list), vốn được dùng trong một số cơ sở dữ liệu trong bộ nhớ (theo hiểu biết của người tổng hợp, ví dụ cấu trúc sorted set của Redis dùng skip list). Kỹ thuật chứng minh bằng chiều cao mũ và Jensen cũng là công cụ chuẩn để phân tích chiều cao của các cây ngẫu nhiên khác.

### 6. Bài toán cuối Chương 12 (Problems, trang 303–307)

Bốn bài toán được tóm ở mục "Bài tập và bài toán cuối chương" bên dưới, gồm cả đề đầy đủ và hướng giải. Ở đây chỉ tái hiện hình duy nhất của phần này.

**Hình: cây cơ số lưu các chuỗi bit 1011, 10, 011, 100 và 0 (Figure 12.5 trong sách).** Cạnh nhãn 0 đi sang trái, nhãn 1 đi sang phải. Khoá của mỗi nút xác định bởi đường đi từ gốc tới nút, nên không cần lưu khoá trong nút (khoá ghi trong hình chỉ để minh hoạ). Nút đánh dấu [ ] là nút tô đậm trong sách: chuỗi tương ứng *không* có trong tập, nút chỉ tồn tại để dẫn đường tới nút khác.

```text
                       [gốc]
                     0 /    \ 1
                     "0"     [1]
                       \ 1   / 0
                      [01]  "10"
                        \1  0/  \1
                     "011" "100" [101]
                                   \ 1
                                  "1011"
```

Duyệt tiền thứ tự (thăm nút trước, rồi nhánh 0, rồi nhánh 1) và in các nút có khoá cho đúng thứ tự từ điển: 0, 011, 10, 100, 1011.

### 7. Ghi chú Chương 12 (Chapter notes, trang 307)

Ghi chú chương nêu nguồn gốc và các hướng mở rộng: Knuth là tài liệu tham khảo chính về cây tìm kiếm nhị phân và các biến thể; cây tìm kiếm nhị phân được nhiều người phát hiện độc lập vào cuối thập niên 1950; cây cơ số còn gọi là "trie" (từ chữ *retrieval*). Ghi chú giải thích vì sao ấn bản 3 đổi cách xoá nút có hai con (đưa nút kế tiếp lên thay chỗ thay vì chép khoá, để lệnh xoá z xoá đúng nút z), báo trước Mục 15.5 về cây tìm kiếm nhị phân tối ưu khi biết tần suất tìm kiếm, ghi công chứng minh của Mục 12.4 cho Aslam, và nhắc thuật toán chèn/xoá ngẫu nhiên của Martínez và Roura. Chi tiết từng ý ở cuối mục "Bài tập và bài toán cuối chương" bên dưới.

## Bài tập và bài toán cuối chương

### Bài tập Mục 12.1 (trang 289)

- **12.1-1:** Với tập khoá {1, 4, 5, 10, 16, 17, 21}, vẽ các cây tìm kiếm nhị phân có chiều cao 2, 3, 4, 5 và 6. (Người tổng hợp: chiều cao 2 là cây cân bằng hoàn hảo gốc 10, con 4 và 17, lá 1, 5, 16, 21; chiều cao 6 là chuỗi khi chèn theo thứ tự tăng.)
- **12.1-2:** Tính chất cây tìm kiếm nhị phân khác tính chất đống-min (khoá của nút ≥ khoá của cha, Chương 6 [C06-heapsort.md](C06-heapsort.md)) ở đâu? Tính chất đống-min có dùng được để in khoá của một cây n nút theo thứ tự trong O(n) không? (Người tổng hợp: không — đống chỉ ràng buộc cha–con, không ràng buộc trái–phải; nếu in được thì vì dựng đống mất O(n), ta sẽ sắp xếp bằng so sánh trong O(n), trái với cận dưới Ω(n lg n) của Chương 8.)
- **12.1-3:** Viết thuật toán không đệ quy cho duyệt trung thứ tự. (Gợi ý của sách: dùng ngăn xếp phụ; lời giải khó hơn nhưng đẹp hơn không dùng ngăn xếp mà giả định có thể so sánh hai con trỏ bằng nhau — tức dùng con trỏ cha và nhớ nút vừa đi qua.)
- **12.1-4:** Viết thuật toán đệ quy cho duyệt tiền thứ tự và hậu thứ tự, chạy trong Θ(n).
- **12.1-5:** Lập luận rằng vì sắp xếp n phần tử mất Ω(n lg n) trong trường hợp xấu nhất ở mô hình so sánh, mọi thuật toán dựa trên so sánh để dựng cây tìm kiếm nhị phân từ một danh sách tuỳ ý n phần tử cũng mất Ω(n lg n). (Ý: dựng cây rồi duyệt trung thứ tự Θ(n) là một thuật toán sắp xếp.)

### Bài tập Mục 12.2 (trang 293–294)

- **12.2-1:** Cây chứa các số từ 1 đến 1000, tìm số 363. Dãy nào *không thể* là dãy nút được xét?
  a. 2, 252, 401, 398, 330, 344, 397, 363.
  b. 924, 220, 911, 244, 898, 258, 362, 363.
  c. 925, 202, 911, 240, 912, 245, 363.
  d. 2, 399, 387, 219, 266, 382, 381, 278, 363.
  e. 935, 278, 347, 621, 299, 392, 358, 363.
  (Người tổng hợp: c và e không thể. Ở c, sau 911 ta rẽ trái (363 < 911) nên mọi nút sau phải < 911, nhưng có 912. Ở e, sau 347 ta rẽ phải (363 > 347) nên mọi nút sau phải > 347, nhưng có 299. Các dãy a, b, d đều giữ được khoảng hợp lệ thu hẹp dần.)
- **12.2-2:** Viết bản đệ quy của TREE-MINIMUM và TREE-MAXIMUM.
- **12.2-3:** Viết thủ tục TREE-PREDECESSOR (bản của người tổng hợp đã ghi ở phần "3. Truy vấn trên cây tìm kiếm nhị phân" của Nội dung chi tiết).
- **12.2-4:** Giáo sư Bunyan cho rằng nếu việc tìm khoá k kết thúc ở một lá, với A là tập khoá bên trái đường tìm, B là tập khoá trên đường tìm, C là tập khoá bên phải đường tìm, thì mọi a ∈ A, b ∈ B, c ∈ C thoả a ≤ b ≤ c. Đưa ra phản ví dụ nhỏ nhất. (Người tổng hợp: cây gốc 4, con trái 2, hai con của 2 là 1 và 3; tìm 1 đi qua 4 → 2 → 1, C = {3}, nhưng b = 4 > c = 3. Cây 3 nút không đủ để tạo phản ví dụ, nên 4 nút là nhỏ nhất.)
- **12.2-5:** Chứng minh nếu một nút có hai con thì nút kế tiếp của nó không có con trái và nút liền trước không có con phải.
- **12.2-6:** Với cây có khoá phân biệt, chứng minh: nếu cây con phải của x rỗng và x có nút kế tiếp y, thì y là tổ tiên thấp nhất của x có con trái cũng là tổ tiên của x (mỗi nút là tổ tiên của chính nó).
- **12.2-7:** Một cách duyệt trung thứ tự khác: gọi TREE-MINIMUM rồi gọi n − 1 lần TREE-SUCCESSOR. Chứng minh cách này chạy trong Θ(n). (Ý: mỗi cạnh của cây bị đi qua đúng hai lần, một lần xuống và một lần lên.)
- **12.2-8:** Chứng minh rằng bắt đầu từ nút bất kỳ trên cây chiều cao h, k lần gọi liên tiếp TREE-SUCCESSOR mất O(k + h).
- **12.2-9:** Cây có khoá phân biệt, x là lá, y là cha của x. Chứng minh y.key hoặc là khoá nhỏ nhất trong T lớn hơn x.key, hoặc là khoá lớn nhất trong T nhỏ hơn x.key.

### Bài tập Mục 12.3 (trang 299)

- **12.3-1:** Viết bản đệ quy của TREE-INSERT.
- **12.3-2:** Dựng cây bằng cách chèn lần lượt các giá trị phân biệt. Lập luận rằng số nút được xét khi tìm một giá trị bằng 1 cộng số nút đã xét khi chèn giá trị đó.
- **12.3-3:** Sắp xếp n số bằng cách chèn lần lượt vào cây rồi duyệt trung thứ tự. Thời gian xấu nhất và tốt nhất là bao nhiêu? (Người tổng hợp: xấu nhất Θ(n²) khi cây thành chuỗi; tốt nhất Θ(n lg n) khi cây có chiều cao Θ(lg n).)
- **12.3-4:** Phép xoá có "giao hoán" không, tức xoá x rồi y có cho cùng cây như xoá y rồi x? (Người tổng hợp: không. Phản ví dụ: cây gốc 2, con trái 1, con phải 4, 4 có con trái 3. Xoá 1 rồi 2 → cây gốc 4 với con trái 3. Xoá 2 rồi 1 → nút kế tiếp 3 lên thay 2, được cây gốc 3 với con 1 và 4; xoá tiếp 1 → cây gốc 3 với con phải 4. Hai cây khác nhau.)
- **12.3-5:** Thay vì thuộc tính x.p, mỗi nút giữ x.succ trỏ tới nút kế tiếp. Viết SEARCH, INSERT, DELETE chạy trong O(h). (Gợi ý: viết thủ tục phụ trả về cha của một nút.)
- **12.3-6:** Khi z có hai con, có thể chọn y là nút liền trước thay vì nút kế tiếp. TREE-DELETE cần sửa gì? Có ý kiến rằng chiến lược "công bằng" (ưu tiên ngang nhau cho liền trước và kế tiếp) cho hiệu năng thực nghiệm tốt hơn; sửa TREE-DELETE thế nào để làm điều đó?

### Bài tập Mục 12.4 (trang 303)

- **12.4-1:** Chứng minh đẳng thức (12.3): Σᵢ₌₀ⁿ⁻¹ C(i+3, 3) = C(n+3, 4).
- **12.4-2:** Mô tả một cây n nút có độ sâu trung bình của nút là Θ(lg n) nhưng chiều cao là ω(lg n). Cho chặn trên tiệm cận của chiều cao một cây n nút có độ sâu trung bình Θ(lg n). (Người tổng hợp: ghép một cây cân bằng khoảng n − √(n lg n) nút với một chuỗi dài √(n lg n); chặn trên là O(√(n lg n)).)
- **12.4-3:** Chứng minh khái niệm "cây chọn ngẫu nhiên đều trong mọi cây trên n khoá" khác với "cây dựng ngẫu nhiên" (gợi ý: liệt kê với n = 3; đã làm ở mục Khái niệm cần biết).
- **12.4-4:** Chứng minh hàm f(x) = 2^x lồi.
- **12.4-5 (★):** Với RANDOMIZED-QUICKSORT trên n số phân biệt, chứng minh với mọi hằng số k > 0, tất cả trừ O(1/n^k) trong n! hoán vị đầu vào cho thời gian chạy O(n lg n).

### Bài toán 12-1 Cây tìm kiếm nhị phân với khoá bằng nhau (Binary search trees with equal keys)

Khoá trùng gây khó cho việc cài đặt cây tìm kiếm nhị phân.

- **a.** Hiệu năng tiệm cận của TREE-INSERT khi chèn n phần tử có khoá giống hệt nhau vào cây rỗng là bao nhiêu?

Đề xuất cải tiến: trước dòng 5 kiểm tra z.key = x.key, và trước dòng 11 kiểm tra z.key = y.key. Nếu bằng nhau thì áp dụng một trong các chiến lược sau (mô tả cho dòng 5; thay x bằng y để có chiến lược cho dòng 11). Với mỗi chiến lược, tìm hiệu năng tiệm cận khi chèn n phần tử có khoá giống nhau vào cây rỗng.

- **b.** Giữ một cờ boolean x.b tại nút x, và đặt x thành x.left hoặc x.right theo giá trị x.b; cờ luân phiên FALSE và TRUE mỗi lần thăm x khi chèn một nút có khoá bằng x.
- **c.** Giữ tại x một danh sách các nút có khoá bằng nhau, và chèn z vào danh sách đó.
- **d.** Đặt x ngẫu nhiên thành x.left hoặc x.right. (Cho hiệu năng xấu nhất và suy luận không chặt thời gian kỳ vọng.)

*Hướng giải của người tổng hợp:* (a) mọi khoá bằng nhau đều đi sang phải (dòng 7), cây thành chuỗi, phần tử thứ i tốn Θ(i) nên tổng Θ(n²). (b) cờ luân phiên chia đều phần tử sang hai bên, cây gần cân bằng, tổng Θ(n lg n). (c) mỗi lần chèn chỉ thêm vào danh sách tại nút đầu tiên (đầu danh sách, O(1)), tổng Θ(n). (d) xấu nhất Θ(n²) (luôn chọn cùng một phía), kỳ vọng Θ(n lg n) vì mỗi lần chèn là một bước đi ngẫu nhiên xuống cây, cây có hình dạng gần như cây ngẫu nhiên.

### Bài toán 12-2 Cây cơ số (Radix trees)

Cho hai chuỗi a = a₀a₁…a_p và b = b₀b₁…b_q, mỗi aᵢ và bⱼ thuộc một tập ký tự có thứ tự. Chuỗi a **nhỏ hơn theo thứ tự từ điển** chuỗi b nếu:

1. tồn tại số nguyên j với 0 ≤ j ≤ min(p, q) sao cho aᵢ = bᵢ với mọi i = 0, 1, …, j − 1 và aⱼ < bⱼ; hoặc
2. p < q và aᵢ = bᵢ với mọi i = 0, 1, …, p.

Ví dụ với chuỗi bit: 10100 < 10110 theo quy tắc 1 (với j = 3), và 10100 < 101000 theo quy tắc 2. Thứ tự này giống thứ tự trong từ điển tiếng Anh.

Cây cơ số ở Hình 12.5 (đã vẽ lại ở phần "6. Bài toán cuối Chương 12" của Nội dung chi tiết) lưu các chuỗi 1011, 10, 011, 100 và 0. Khi tìm khoá a = a₀a₁…a_p, tại nút độ sâu i ta đi trái nếu aᵢ = 0 và đi phải nếu aᵢ = 1. Cho S là tập các chuỗi bit phân biệt có tổng độ dài n. Chỉ ra cách dùng cây cơ số để sắp xếp S theo thứ tự từ điển trong Θ(n). Với ví dụ trong hình, kết quả phải là 0, 011, 10, 100, 1011.

*Hướng giải của người tổng hợp:* chèn từng chuỗi vào cây, đánh dấu nút cuối là "có khoá"; tổng chi phí chèn Θ(n) và cây có nhiều nhất n + 1 nút. Duyệt tiền thứ tự (nút, rồi nhánh 0, rồi nhánh 1) và in các nút được đánh dấu: một nút được in trước mọi nút con (quy tắc 2: tiền tố nhỏ hơn), nhánh 0 trước nhánh 1 (quy tắc 1). Duyệt mất Θ(số nút) = O(n).

### Bài toán 12-3 Độ sâu trung bình của nút trong cây dựng ngẫu nhiên (Average node depth in a randomly built binary search tree)

Bài toán chứng minh độ sâu trung bình của một nút trong cây dựng ngẫu nhiên n nút là O(lg n). Kết quả yếu hơn Định lý 12.4 (chiều cao là độ sâu *lớn nhất*), nhưng kỹ thuật cho thấy sự tương đồng bất ngờ giữa việc dựng cây tìm kiếm nhị phân và việc chạy RANDOMIZED-QUICKSORT (Mục 7.3). Định nghĩa **tổng độ dài đường đi** P(T) của cây nhị phân T là tổng, trên mọi nút x của T, độ sâu d(x, T) của x.

- **a.** Lập luận rằng độ sâu trung bình của nút trong T là (1/n)·Σ_{x∈T} d(x, T) = (1/n)·P(T). Như vậy cần chứng minh kỳ vọng của P(T) là O(n lg n).
- **b.** Gọi T_L và T_R là cây con trái và phải của T. Lập luận rằng nếu T có n nút thì P(T) = P(T_L) + P(T_R) + n − 1.
- **c.** Gọi P(n) là tổng độ dài đường đi trung bình của cây dựng ngẫu nhiên n nút. Chứng minh P(n) = (1/n)·Σᵢ₌₀ⁿ⁻¹ (P(i) + P(n − i − 1) + n − 1).
- **d.** Chỉ ra cách viết lại P(n) = (2/n)·Σₖ₌₁ⁿ⁻¹ P(k) + Θ(n).
- **e.** Nhớ lại phân tích khác của quicksort ngẫu nhiên ở Bài toán 7-3, kết luận P(n) = O(n lg n).

Ở mỗi lời gọi đệ quy của quicksort, ta chọn một phần tử chốt ngẫu nhiên để phân hoạch tập phần tử cần sắp xếp. Mỗi nút của cây tìm kiếm nhị phân phân hoạch tập phần tử rơi vào cây con gốc tại nút đó.

- **f.** Mô tả một cài đặt quicksort trong đó các phép so sánh để sắp xếp một tập phần tử giống hệt các phép so sánh để chèn các phần tử đó vào cây tìm kiếm nhị phân (thứ tự thực hiện có thể khác, nhưng cùng tập phép so sánh).

*Hướng giải của người tổng hợp:* (b) mỗi nút trong T_L và T_R sâu hơn 1 so với độ sâu trong cây con của nó, có n − 1 nút như vậy, gốc có độ sâu 0. (c) gốc có thứ hạng i + 1 với xác suất 1/n, khi đó hai cây con là cây dựng ngẫu nhiên trên i và n − i − 1 khoá. (d) mỗi P(k) xuất hiện hai lần và P(0) = 0. (e) đây đúng là truy hồi của số phép so sánh kỳ vọng trong quicksort ngẫu nhiên, nghiệm O(n lg n). (f) quicksort luôn chọn chốt là phần tử *xuất hiện sớm nhất trong thứ tự chèn* của mảng con, và phân hoạch ổn định (giữ thứ tự tương đối); khi đó chốt so sánh với mọi phần tử của mảng con — đúng như gốc của cây con được so sánh với mọi khoá chèn sau rơi vào cây con đó.

### Bài toán 12-4 Số cây nhị phân khác nhau (Number of different binary trees)

Gọi bₙ là số cây nhị phân khác nhau có n nút. Bài toán tìm công thức và ước lượng tiệm cận của bₙ.

- **a.** Chứng minh b₀ = 1 và với n ≥ 1: bₙ = Σₖ₌₀ⁿ⁻¹ bₖ·bₙ₋₁₋ₖ.
- **b.** Theo định nghĩa hàm sinh ở Bài toán 4-4, gọi B(x) = Σₙ₌₀^∞ bₙxⁿ. Chứng minh B(x) = x·B(x)² + 1, và do đó một dạng đóng của B(x) là B(x) = (1/(2x))·(1 − √(1 − 4x)).

  Khai triển Taylor của f(x) quanh x = a là f(x) = Σₖ₌₀^∞ f⁽ᵏ⁾(a)/k! · (x − a)ᵏ, với f⁽ᵏ⁾(x) là đạo hàm cấp k của f tại x.
- **c.** Chứng minh bₙ = (1/(n + 1))·C(2n, n) (số **Catalan** thứ n) bằng khai triển Taylor của √(1 − 4x) quanh x = 0. (Có thể thay bằng khai triển nhị thức tổng quát (C.4) cho số mũ không nguyên n: với số thực n và số nguyên k, hiểu C(n, k) là n(n − 1)⋯(n − k + 1)/k! nếu k ≥ 0 và 0 nếu ngược lại.)
- **d.** Chứng minh bₙ = 4ⁿ/(√π · n^{3/2}) · (1 + O(1/n)).

*Hướng giải và kiểm tra của người tổng hợp:* (a) chọn gốc, cây con trái có k nút, cây con phải có n − 1 − k nút. (b) nhân truy hồi với xⁿ và cộng: B(x) − 1 = x·B(x)²; giải phương trình bậc hai và chọn dấu trừ để B(0) = b₀ = 1 hữu hạn. (d) dùng công thức Stirling cho C(2n, n) ≈ 4ⁿ/√(πn). Giá trị: b₀ = 1, b₁ = 1, b₂ = 2, b₃ = 5 (= 20/4), b₄ = 14 (= 70/5); với n = 4 công thức tiệm cận cho 256/(1,7725·8) ≈ 18,1, sai lệch còn lớn ở n nhỏ, đúng như thừa số (1 + O(1/n)).

### Ghi chú chương (Chapter notes, trang 307)

- **Knuth** (*The Art of Computer Programming*, tập 3) có phần trình bày tốt về cây tìm kiếm nhị phân đơn giản và nhiều biến thể. Cây tìm kiếm nhị phân dường như được nhiều người phát hiện độc lập vào **cuối thập niên 1950**.
- **Cây cơ số** thường được gọi là **"trie"**, lấy từ các chữ cái giữa của từ *retrieval* (truy xuất). Knuth cũng bàn về chúng.
- **Cách xoá trong ấn bản 3:** nhiều sách, kể cả hai ấn bản đầu của chính cuốn này, xoá nút có hai con theo cách đơn giản hơn: thay vì đưa nút kế tiếp y lên thay z, họ xoá nút y nhưng chép khoá và dữ liệu vệ tinh của y vào z. Nhược điểm là nút thực sự bị xoá có thể không phải nút được truyền vào thủ tục xoá; nếu phần khác của chương trình giữ con trỏ tới các nút trong cây, chúng có thể trỏ nhầm vào nút đã bị xoá (con trỏ "cũ", stale). Cách mới phức tạp hơn một chút nhưng bảo đảm lệnh xoá z xoá đúng z và chỉ z.
- **Mục 15.5** sẽ dựng cây tìm kiếm nhị phân tối ưu khi biết trước tần suất tìm kiếm mỗi khoá và tần suất tìm các giá trị nằm giữa các khoá, sao cho tổng số nút được xét là nhỏ nhất.
- **Chứng minh ở Mục 12.4** là của **Aslam**. **Martínez và Roura** đưa ra thuật toán ngẫu nhiên cho chèn và xoá mà kết quả của mỗi thao tác là một cây tìm kiếm nhị phân ngẫu nhiên; định nghĩa "cây ngẫu nhiên" của họ chỉ khác chút ít so với cây dựng ngẫu nhiên của chương này.

## Luận điểm cốt lõi

### Mệnh đề

Cây tìm kiếm nhị phân cài đặt được trọn bộ thao tác của một tập động có thứ tự (tìm, nhỏ nhất, lớn nhất, kế tiếp, liền trước, chèn, xoá) với chi phí O(h) cho mỗi thao tác và in toàn bộ khoá theo thứ tự trong Θ(n); chiều cao h nằm giữa ⌊lg n⌋ và n − 1, và bằng O(lg n) trung bình khi các khoá được chèn theo thứ tự ngẫu nhiên.

### Giả định

- Mô hình RAM của Chương 2: mỗi phép so sánh khoá, mỗi phép gán con trỏ tốn thời gian hằng số.
- Cây được biểu diễn bằng nút liên kết có con trỏ left, right và p (cha); con trỏ cha là cần thiết cho TREE-SUCCESSOR và TRANSPLANT.
- Khoá thuộc một tập có thứ tự toàn phần; khoá có thể trùng nhau (tính chất dùng ≤ và ≥), nhưng nhiều kết quả (định nghĩa nút kế tiếp, Bài tập 12.2-6, Định lý 12.4) giả định khoá phân biệt.
- Định lý 12.4 giả định cây chỉ được dựng bằng phép chèn, theo một hoán vị chọn đều trong n! hoán vị; không có kết quả tương ứng khi xen kẽ chèn và xoá.

### Cơ chế

1. Tính chất cây tìm kiếm nhị phân bảo đảm: tại mỗi nút, một lần so sánh cho biết khoá cần tìm chỉ có thể nằm ở một cây con.
2. Vì vậy tìm kiếm, chèn, tìm nhỏ nhất/lớn nhất đi theo một đường đơn từ gốc xuống: O(h).
3. Thứ tự trung thứ tự là thứ tự sắp xếp; nút kế tiếp hoặc là nút nhỏ nhất của cây con phải, hoặc là tổ tiên đầu tiên mà ta đi lên từ con trái: O(h), không cần so sánh khoá.
4. Xoá dùng TRANSPLANT; nút có hai con được thay bằng nút kế tiếp (nút này không có con trái nên tách ra dễ): O(h).
5. Chiều cao phụ thuộc thứ tự chèn; với thứ tự ngẫu nhiên, truy hồi của chiều cao mũ E[Yₙ] ≤ (4/n)ΣE[Yᵢ] cho E[Yₙ] = O(n³), và Jensen cho E[Xₙ] ≤ 3 lg n + O(1).

### Bằng chứng và ví dụ tác giả đưa ra

- Hình 12.1: cùng tập {2, 5, 5, 6, 7, 8} có cây cao 2 và cây cao 4; duyệt trung thứ tự đều cho 2, 5, 5, 6, 7, 8.
- Định lý 12.1: chứng minh bằng phương pháp thay thế T(n) ≤ (c + d)n + c.
- Hình 12.2: tìm 13 theo đường 15 → 6 → 7 → 13; nhỏ nhất 2, lớn nhất 20; kế tiếp của 15 là 17, kế tiếp của 13 là 15.
- Hình 12.3: chèn 13 theo đường 12 → 18 → 15, thành con trái của 15.
- Hình 12.4: bốn trường hợp xoá (a)–(d).
- Định lý 12.4: E[Yₙ] ≤ (1/4)·C(n+3, 3) = (n³ + 6n² + 11n + 6)/24, suy ra E[Xₙ] = O(lg n).
- Hình 12.5: cây cơ số trên {1011, 10, 011, 100, 0} cho thứ tự 0, 011, 10, 100, 1011.

### Kết luận và hàm ý cho người lập trình

- Chi phí của cây tìm kiếm là chiều cao, không phải số nút; muốn bảo đảm hiệu năng thì phải kiểm soát chiều cao — đó là lý do có cây đỏ-đen, cây AVL, cây B, treap.
- Cây không cân bằng chỉ "tốt trung bình" khi dữ liệu đến theo thứ tự ngẫu nhiên; dữ liệu thực thường có thứ tự (mã tăng dần, thời gian tăng dần), nên dùng cây không cân bằng trong sản phẩm là rủi ro.
- Khi cần truy vấn có thứ tự (kế tiếp, khoảng, nhỏ nhất), cây tìm kiếm thắng bảng băm; khi chỉ cần tra cứu theo khoá, bảng băm thường nhanh hơn.
- Khi xoá, nên di chuyển nút chứ không chép khoá, để con trỏ bên ngoài không bị "cũ".

### Trong ngôn ngữ khoa học máy tính

- INORDER-TREE-WALK: Θ(n).
- TREE-SEARCH, ITERATIVE-TREE-SEARCH, TREE-MINIMUM, TREE-MAXIMUM, TREE-SUCCESSOR, TREE-PREDECESSOR, TREE-INSERT, TREE-DELETE: O(h); TRANSPLANT: O(1).
- ⌊lg n⌋ ≤ h ≤ n − 1.
- Cây dựng ngẫu nhiên: E[Xₙ] ≤ lg((n+1)(n+2)(n+3)/24) = 3 lg n + O(1) = O(lg n); độ sâu trung bình của nút O(lg n) (Bài toán 12-3).
- Số cây nhị phân n nút: bₙ = C(2n, n)/(n + 1) = 4ⁿ/(√π·n^{3/2})·(1 + O(1/n)).
- Sắp xếp bằng cây (chèn rồi duyệt): Θ(n²) xấu nhất, Θ(n lg n) tốt nhất và kỳ vọng với thứ tự ngẫu nhiên; mọi cách dựng cây bằng so sánh cần Ω(n lg n).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| binary search tree (BST) | cây tìm kiếm nhị phân | cây nhị phân thoả tính chất trái ≤ nút ≤ phải |
| binary-search-tree property | tính chất cây tìm kiếm nhị phân | mọi khoá cây con trái ≤ x.key ≤ mọi khoá cây con phải |
| search tree | cây tìm kiếm | cấu trúc cây hỗ trợ các thao tác tập động có thứ tự |
| dynamic set | tập động | tập phần tử thay đổi theo thời gian |
| dictionary | từ điển | cấu trúc hỗ trợ tìm, chèn, xoá theo khoá |
| priority queue | hàng đợi ưu tiên | cấu trúc hỗ trợ lấy phần tử nhỏ nhất/lớn nhất |
| key | khoá | giá trị dùng để so sánh và sắp xếp |
| satellite data | dữ liệu vệ tinh | dữ liệu đi kèm khoá, không tham gia so sánh |
| node | nút | đối tượng trong cây |
| root | gốc | nút duy nhất không có cha |
| leaf | lá | nút không có con |
| left child / right child / parent | con trái / con phải / cha | các thuộc tính left, right, p |
| subtree | cây con | một nút cùng mọi hậu duệ của nó |
| ancestor | tổ tiên | nút trên đường từ gốc tới nút đang xét (kể cả chính nó) |
| NIL | NIL | giá trị con trỏ rỗng |
| height | chiều cao | số cạnh trên đường dài nhất từ gốc tới lá |
| depth | độ sâu | số cạnh từ gốc tới nút |
| complete binary tree | cây nhị phân đầy đủ | cây mọi mức đều đầy, chiều cao ≈ lg n |
| linear chain | chuỗi tuyến tính | cây suy biến, mỗi nút có tối đa một con |
| inorder tree walk | duyệt trung thứ tự | trái, gốc, phải; cho khoá tăng dần |
| preorder tree walk | duyệt tiền thứ tự | gốc, trái, phải |
| postorder tree walk | duyệt hậu thứ tự | trái, phải, gốc |
| successor | nút kế tiếp | nút đứng ngay sau trong thứ tự trung thứ tự |
| predecessor | nút liền trước | nút đứng ngay trước trong thứ tự trung thứ tự |
| minimum / maximum | nhỏ nhất / lớn nhất | nút trái nhất / phải nhất |
| simple path | đường đơn | đường đi không lặp đỉnh |
| trailing pointer | con trỏ theo sau | con trỏ luôn trỏ vào cha của con trỏ đang dò |
| splice out | tách ra | gỡ một nút khỏi vị trí, nối cha với con của nó |
| transplant | cấy ghép (cây con) | thay cây con gốc u bằng cây con gốc v |
| stale pointer | con trỏ cũ | con trỏ trỏ vào nút đã bị xoá |
| randomly built binary search tree | cây tìm kiếm nhị phân dựng ngẫu nhiên | chèn khoá theo hoán vị ngẫu nhiên đều |
| exponential height | chiều cao mũ | Yₙ = 2^Xₙ |
| rank | thứ hạng | vị trí của khoá trong tập đã sắp xếp |
| indicator random variable | biến ngẫu nhiên chỉ báo | bằng 1 nếu sự kiện xảy ra, 0 nếu không |
| linearity of expectation | tính tuyến tính của kỳ vọng | E[ΣXᵢ] = ΣE[Xᵢ] |
| independence | tính độc lập | E[XY] = E[X]E[Y] khi X, Y độc lập |
| convex function | hàm lồi | đồ thị nằm dưới dây cung; ví dụ 2^x |
| Jensen's inequality | bất đẳng thức Jensen | f(E[X]) ≤ E[f(X)] với f lồi |
| substitution method | phương pháp thay thế | đoán nghiệm rồi chứng minh bằng quy nạp |
| total path length | tổng độ dài đường đi | tổng độ sâu mọi nút |
| radix tree / trie | cây cơ số / trie | cây lưu chuỗi theo từng ký tự (bit) |
| lexicographic order | thứ tự từ điển | so sánh chuỗi như trong từ điển |
| generating function | hàm sinh | B(x) = Σ bₙxⁿ |
| Taylor expansion | khai triển Taylor | f(x) = Σ f⁽ᵏ⁾(a)(x − a)ᵏ/k! |
| Catalan number | số Catalan | C(2n, n)/(n + 1), số cây nhị phân n nút |
| optimal binary search tree | cây tìm kiếm nhị phân tối ưu | cây có chi phí tìm kiếm kỳ vọng nhỏ nhất (Mục 15.5) |
| red-black tree | cây đỏ-đen | cây tìm kiếm cân bằng, chiều cao O(lg n) (Chương 13) |
| B-tree | cây B | cây tìm kiếm nhiều nhánh cho dữ liệu trên đĩa (Chương 18) |

## Câu nói đáng nhớ

> "Thus, we can use a search tree both as a dictionary and as a priority queue." — phần mở đầu Chương 12
>
> *Dịch: Vì vậy, ta có thể dùng một cây tìm kiếm vừa làm từ điển vừa làm hàng đợi ưu tiên.*

> "Basic operations on a binary search tree take time proportional to the height of the tree." — phần mở đầu Chương 12
>
> *Dịch: Các thao tác cơ bản trên cây tìm kiếm nhị phân mất thời gian tỉ lệ với chiều cao của cây.*

> "The structure of a binary search tree allows us to determine the successor of a node without ever comparing keys." — Mục 12.2
>
> *Dịch: Cấu trúc của cây tìm kiếm nhị phân cho phép xác định nút kế tiếp của một nút mà không cần so sánh khoá lần nào.*

> "As we shall see, modifying the tree to insert a new element is relatively straightforward, but handling deletion is somewhat more intricate." — Mục 12.3
>
> *Dịch: Như ta sẽ thấy, sửa cây để chèn một phần tử mới khá đơn giản, còn xử lý việc xoá thì phức tạp hơn đôi chút.*

> "As with quicksort, we can show that the behavior of the average case is much closer to the best case than to the worst case." — Mục 12.4
>
> *Dịch: Giống quicksort, ta có thể chỉ ra rằng hành vi của trường hợp trung bình gần với trường hợp tốt nhất hơn nhiều so với trường hợp xấu nhất.*

> "Radix trees are often called “tries,” which comes from the middle letters in the word retrieval." — Ghi chú chương
>
> *Dịch: Cây cơ số thường được gọi là "trie", lấy từ các chữ cái giữa của từ retrieval (truy xuất).*

> "…it guarantees that a call to delete node z deletes node z and only node z." — Ghi chú chương, về cách xoá mới của ấn bản 3
>
> *Dịch: …nó bảo đảm rằng lời gọi xoá nút z sẽ xoá nút z và chỉ nút z.*

## Đánh giá và phát hiện đáng chú ý

### Một chương ngắn, gọn, đặt nền cho cả nửa sau của Phần III

Chương 12 chỉ khoảng 20 trang nhưng định nghĩa toàn bộ "giao diện" mà Chương 13 (cây đỏ-đen) và Chương 14 (mở rộng cấu trúc dữ liệu) sẽ giữ nguyên: các thủ tục TREE-SEARCH, TREE-MINIMUM, TREE-SUCCESSOR dùng lại nguyên văn trên cây đỏ-đen; TREE-INSERT và TREE-DELETE trở thành khung, chỉ thêm bước sửa màu và phép xoay. Vì vậy hiểu kỹ chương này, đặc biệt là bốn trường hợp xoá và TRANSPLANT, gần như là điều kiện để đọc Chương 13. Cách trình bày theo từng thao tác, mỗi thao tác một thủ tục ngắn kèm một ví dụ trên cùng một cây (cây gốc 15), rất dễ theo dõi.

### Thay đổi cách xoá là một quyết định kỹ thuật tốt, nhưng làm mã khó hơn

Ấn bản 3 bỏ cách "chép khoá của nút kế tiếp vào z rồi xoá nút kế tiếp" — cách vẫn phổ biến trong nhiều sách và bài giảng — để chuyển sang TRANSPLANT. Lý do được nêu rõ ở Ghi chú chương (giữ tính hợp lệ của con trỏ bên ngoài), và đây đúng là yêu cầu của thư viện thực tế. Cái giá là TREE-DELETE có tới 12 dòng với một nhánh lồng (dòng 6), và chính đoạn văn giải thích nhánh này lại có lỗi đánh máy "left" thay cho "right". Người học nên tự chạy tay cả bốn trường hợp (như đã làm ở trên với các nút 4, 13, 6, 15) để nắm chắc.

### Mục 12.4: một chứng minh đẹp, ngắn, với thủ thuật đáng học

Kỹ thuật "chiều cao mũ" là điểm sáng: thay vì làm việc với max của hai chiều cao (khó lấy kỳ vọng), chuyển sang 2^chiều cao để có thể chặn max bằng tổng, rồi dùng Jensen để quay lại. Chặn nhận được, E[Xₙ] ≤ 3 lg n + O(1), thực ra khá sát: theo hiểu biết của người tổng hợp (không tra cứu), kết quả chính xác do Devroye chứng minh năm 1986 là chiều cao kỳ vọng ≈ 4,311·ln n ≈ 2,99·lg n. Điểm yếu: chứng minh không nói rõ truy hồi chỉ dùng cho n ≥ 2, và lời văn có một chữ bị thiếu ("binary search [tree]"). Mặt khác, giới hạn "chỉ chèn, không xoá" là hạn chế lớn về thực tiễn; sách thừa nhận điều đó và trỏ sang Martínez–Roura và Chương 13.

### Liên hệ với các chương khác

- **Chương 6 (đống):** tính chất đống chỉ ràng buộc cha–con, nên không duyệt ra thứ tự được (Bài tập 12.1-2); cây tìm kiếm ràng buộc trái–phải nên duyệt ra thứ tự.
- **Chương 7 (quicksort):** dựng cây tìm kiếm từ một dãy và quicksort chọn chốt "phần tử đầu tiên" thực hiện cùng một tập phép so sánh (Bài toán 12-3f); vì thế số phép so sánh kỳ vọng của quicksort ngẫu nhiên bằng tổng độ dài đường đi kỳ vọng của cây dựng ngẫu nhiên.
- **Chương 8 (cận dưới sắp xếp):** dựng cây bằng so sánh cần Ω(n lg n) (Bài tập 12.1-5).
- **Chương 11 (bảng băm):** bảng băm O(1) kỳ vọng cho tra cứu nhưng không có thứ tự; cây tìm kiếm O(h) nhưng có thứ tự.
- **Chương 15 (quy hoạch động):** số Catalan của Bài toán 12-4 lại xuất hiện khi đếm số cách đặt ngoặc nhân dãy ma trận; Mục 15.5 dựng cây tìm kiếm nhị phân tối ưu.

### So với thực tế phần mềm và phần cứng hiện đại

- Cây tìm kiếm nhị phân *không cân bằng* gần như không được dùng trực tiếp trong thư viện chuẩn; thay vào đó là cây đỏ-đen (`std::map`, `TreeMap` — theo hiểu biết của người tổng hợp), cây B/B+ (cơ sở dữ liệu, hệ thống tệp), skip list hoặc treap.
- Trên phần cứng hiện đại, mỗi bước đi xuống cây liên kết thường là một lần trượt bộ nhớ đệm (cache miss) vì các nút nằm rải rác trong bộ nhớ. Do đó với dữ liệu trong bộ nhớ, cây B với nút rộng (nhiều khoá mỗi nút) hoặc mảng đã sắp xếp với tìm kiếm nhị phân (khi ít cập nhật) thường nhanh hơn cây nhị phân dù cùng độ phức tạp O(lg n). Mô hình RAM của sách không phản ánh chi phí này.
- Trie (Bài toán 12-2) được dùng rộng rãi: định tuyến IP theo tiền dài nhất, gợi ý tự động hoàn thành, từ điển nén; theo hiểu biết của người tổng hợp, nhân Linux từng dùng radix tree cho bộ đệm trang (page cache) trước khi thay bằng cấu trúc XArray.

### Cách vận dụng

- **Phỏng vấn kỹ thuật:** các câu hỏi kinh điển gồm kiểm tra một cây có phải BST không (phải truyền khoảng [min, max] xuống, không chỉ so cha–con — lỗi phổ biến đã minh hoạ ở mục Khái niệm cần biết), tìm nút kế tiếp có/không có con trỏ cha, xoá nút, phần tử nhỏ thứ k (duyệt trung thứ tự dừng sớm), dựng BST cân bằng từ mảng đã sắp xếp, đếm số BST có n nút (số Catalan).
- **Lập trình thi đấu:** hiếm khi tự cài BST không cân bằng (dễ bị dữ liệu thử có thứ tự làm suy biến thành Θ(n²)); dùng `std::set/std::map` hoặc tự cài treap khi cần tách/ghép cây hay thống kê thứ tự.
- **Kỹ thuật phần mềm:** khi chọn cấu trúc, hỏi "có cần truy vấn có thứ tự không"; nếu có, dùng cây cân bằng của thư viện; nếu giữ con trỏ/iterator tới phần tử trong cây, kiểm tra bảo đảm của thư viện về tính hợp lệ sau khi xoá — chính là vấn đề mà Ghi chú chương nêu.

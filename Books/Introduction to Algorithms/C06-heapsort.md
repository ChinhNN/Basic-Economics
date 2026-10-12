# Chương 6 — Sắp xếp vun đống (Heapsort)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009). Gồm hai phần: Phần II "Sorting and Order Statistics" — trang tên phần (trang 146, không in số) và lời giới thiệu Phần II (Introduction, trang 147–150); Chương 6 "Heapsort", trang 151–169.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (Dartmouth, MIT, MIT, Columbia) viết cuốn giáo trình thuật toán được dùng rộng rãi nhất, thường gọi tắt là CLRS.
**Vị trí trong lập luận của cả cuốn sách:** Phần I ([C01-vai-tro-cua-thuat-toan.md](C01-vai-tro-cua-thuat-toan.md) tới [C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)) xây công cụ: Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)) giới thiệu bài toán sắp xếp, sắp xếp chèn (tại chỗ, Θ(n²)), sắp xếp trộn (Θ(n lg n), không tại chỗ) và kỹ thuật bất biến vòng lặp; Chương 3 ([C03-tang-truong-cua-ham.md](C03-tang-truong-cua-ham.md)) cho ký hiệu Θ, O, Ω; Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)) cho định lý thợ, được dùng ngay ở Mục 6.2. Lời giới thiệu Phần II đặt bài toán sắp xếp làm trung tâm, phân biệt khoá với dữ liệu vệ tinh, nêu năm lý do sắp xếp là bài toán nền tảng, tóm tắt bảng thời gian chạy của bảy thuật toán sắp xếp trong Chương 2 và 6–8, và giới thiệu bài toán thống kê thứ tự. Chương 6 là chương đầu của Phần II: thuật toán heapsort đạt cùng lúc hai ưu điểm mà sắp xếp chèn và sắp xếp trộn chỉ có riêng từng cái (O(n lg n) trong trường hợp xấu nhất và sắp xếp tại chỗ), đồng thời giới thiệu cấu trúc dữ liệu đầu tiên của sách — **đống nhị phân** (binary heap) — và ứng dụng của nó làm **hàng đợi ưu tiên** (priority queue). Chương 7 ([C07-quicksort.md](C07-quicksort.md)) trình bày quicksort, thường nhanh hơn heapsort trong thực tế nhưng xấu nhất Θ(n²). Chương 8 ([C08-sap-xep-thoi-gian-tuyen-tinh.md](C08-sap-xep-thoi-gian-tuyen-tinh.md)) chứng minh mọi thuật toán sắp xếp bằng so sánh cần Ω(n lg n) phép so sánh, nên heapsort tối ưu tiệm cận. Chương 9 ([C09-trung-vi-va-thong-ke-thu-tu.md](C09-trung-vi-va-thong-ke-thu-tu.md)) giải bài toán thống kê thứ tự nêu ở lời giới thiệu Phần II. Hàng đợi ưu tiên dựng bằng đống được dùng lại ở Chương 16 ([C16-thuat-toan-tham-lam.md](C16-thuat-toan-tham-lam.md), mã Huffman), Chương 23 ([C23-cay-khung-nho-nhat.md](C23-cay-khung-nho-nhat.md), thuật toán Prim) và Chương 24 ([C24-duong-di-ngan-nhat-tu-mot-nguon.md](C24-duong-di-ngan-nhat-tu-mot-nguon.md), thuật toán Dijkstra); Chương 19 ([C19-dong-fibonacci.md](C19-dong-fibonacci.md)) và Chương 20 ([C20-cay-van-emde-boas.md](C20-cay-van-emde-boas.md)) cho các cài đặt hàng đợi ưu tiên nhanh hơn ở một số phép toán; Chương 10 ([C10-cau-truc-du-lieu-co-ban.md](C10-cau-truc-du-lieu-co-ban.md)) mở Phần III với khái niệm tập động, tổng quát hoá cách nhìn "cấu trúc dữ liệu hỗ trợ một nhóm phép toán" đã xuất hiện lần đầu ở Mục 6.5.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **một mảng bình thường, nếu nhìn như một cây nhị phân gần đầy đủ và giữ tính chất "cha không nhỏ hơn con" (tính chất đống max), sẽ cho phép lấy phần tử lớn nhất trong O(1) và khôi phục cấu trúc trong O(lg n); từ đó có thuật toán sắp xếp tại chỗ O(n lg n) trong trường hợp xấu nhất (heapsort) và một hàng đợi ưu tiên mà mọi phép toán đều O(lg n).** Lời giới thiệu Phần II định nghĩa bài toán sắp xếp (đầu vào n số, đầu ra một hoán vị không giảm), bản ghi gồm khoá và dữ liệu vệ tinh, năm lý do sắp xếp là bài toán cơ bản nhất, bảng thời gian chạy của sắp xếp chèn, trộn, vun đống, nhanh, đếm, cơ số, phân cụm, và bài toán thống kê thứ tự thứ i. Mục 6.1 định nghĩa đống nhị phân: mảng A với thuộc tính A.heap-size, gốc A[1], cha của i là ⌊i/2⌋, con trái 2i, con phải 2i + 1; tính chất đống max A[PARENT(i)] ≥ A[i] và đống min A[PARENT(i)] ≤ A[i]; chiều cao của đống n phần tử là ⌊lg n⌋. Mục 6.2 trình bày MAX-HEAPIFY: khi hai cây con của nút i đã là đống max, cho A[i] "chìm xuống" bằng cách đổi với con lớn hơn, lặp lại; thời gian O(lg n), hay O(h) với h là chiều cao nút. Mục 6.3 trình bày BUILD-MAX-HEAP: gọi MAX-HEAPIFY từ nút ⌊n/2⌋ lùi về 1; chứng minh đúng bằng bất biến vòng lặp; cận đơn giản O(n lg n) không chặt, cận chặt O(n) vì có nhiều nhất ⌈n/2^(h+1)⌉ nút ở chiều cao h và Σ h/2^h = 2. Mục 6.4 trình bày HEAPSORT: dựng đống max, rồi n − 1 lần đổi gốc (phần tử lớn nhất) xuống cuối vùng đống, thu nhỏ đống, gọi MAX-HEAPIFY(A, 1); tổng O(n lg n). Mục 6.5 dùng đống max cài hàng đợi ưu tiên max với HEAP-MAXIMUM (Θ(1)), HEAP-EXTRACT-MAX, HEAP-INCREASE-KEY ("nổi lên" về phía gốc) và MAX-HEAP-INSERT (thêm lá −∞ rồi tăng khoá), cùng O(lg n), và nói về "tay cầm" (handle) nối phần tử đống với đối tượng ứng dụng.

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong chương này.** Chỉ có một bài tập có dấu sao: Exercise 6.4-5 (chứng minh thời gian tốt nhất của HEAPSORT là Ω(n lg n) khi các phần tử khác nhau). Ba bài toán cuối chương (6-1, 6-2, 6-3) không có dấu sao.
> - **Số trang Phần II:** trang 146 là trang tên "II Sorting and Order Statistics" (không in số, chỉ có tiêu đề), lời giới thiệu Phần II là trang 147–150 (trang 147 không in số). Chương 6 bắt đầu ở trang 151 và kết thúc ở trang 169 (Ghi chú chương tràn sang trang 169); trang 170 đã là Chương 7. File này dùng các số trang sau khi kiểm tra ảnh trang.
> - **Lớp chữ PDF hỏng nhiều ký hiệu, đã đọc lại từ ảnh trang:** dấu ngoặc vuông thành `Œ` (`AŒi` là A[i]); dấu ≤, ≥ mất hẳn (`AŒPARENT .i / AŒi` là A[PARENT(i)] ≥ A[i] ở trang 152 và ≤ ở trang 153; `l A:heap-size` ở dòng 3 MAX-HEAPIFY là l ≤ A.heap-size); dấu ≠ ở dòng 8 MAX-HEAPIFY mất; dấu trừ và vô cực thành `/NUL` (`/NUL1` là −∞ ở MAX-HEAP-INSERT và Exercise 6.5-4); dấu ⌈ ⌉ thành `˙` (cận ⌈n/2^(h+1)⌉ ở trang 157, 159); tổng và phân số của chặn BUILD-MAX-HEAP ở trang 159 vỡ thành nhiều dòng; căn bậc hai và ε mất ở Ghi chú chương (`O.p lg n/` là O(√lg n), `lg1=3C C` là lg^(1/3+ε) C); Θ thành `‚`, Ω mất. Toàn bộ pseudocode, công thức, Hình 6.1–6.5 và bảng thời gian chạy ở trang 150 được đối chiếu với ảnh trang 147–169.
> - **Chỗ sách sai chính tả hoặc chưa chặt (nhận xét của người tổng hợp):** (1) trang 159 viết "We evalaute" — lỗi chính tả của "evaluate". (2) Trang 153 viết "a heap of n elements is based on a complete binary tree", trong khi Mục 6.1 vừa định nghĩa đống là cây nhị phân *gần* đầy đủ (nearly complete); chữ "complete" ở đây nên hiểu là "nearly complete". (3) Trang 164 mô tả HEAP-INCREASE-KEY "dừng nếu khoá của phần tử nhỏ hơn" khoá cha, nhưng pseudocode dừng khi khoá *không lớn hơn* (bằng nhau cũng dừng) — pseudocode đúng, lời văn chưa chặt. (4) MAX-HEAP-INSERT tăng A.heap-size mà không kiểm tra A.heap-size < A.length (tràn mảng); HEAP-INCREASE-KEY không kiểm tra 1 ≤ i ≤ A.heap-size. Đây là đơn giản hoá có chủ ý của sách. Người tổng hợp không chắc những chỗ này có trong danh sách lỗi chính thức (errata) của ấn bản 3 hay không — theo hiểu biết của người tổng hợp, không tra cứu.
> - **Mọi ví dụ chạy tay trong sách đã được tự kiểm tra lại và đúng:** MAX-HEAPIFY(A, 2) trên ⟨16, 4, 10, 14, 7, 9, 3, 2, 8, 1⟩ cho ⟨16, 14, 10, 8, 7, 9, 3, 2, 4, 1⟩; BUILD-MAX-HEAP trên ⟨4, 1, 3, 2, 16, 9, 10, 14, 8, 7⟩ cho cùng đống đó qua năm lần gọi MAX-HEAPIFY (7 lần đổi chỗ); HEAPSORT trên đống đó cho ⟨1, 2, 3, 4, 7, 8, 9, 10, 14, 16⟩, mọi trạng thái trung gian (b)–(j) khớp; HEAP-INCREASE-KEY tăng A[9] từ 4 lên 15 cho ⟨16, 15, 10, 14, 7, 9, 3, 2, 8, 1⟩. Cận "cây con của một con có nhiều nhất 2n/3 nút" cũng đã kiểm tra: khi tầng đáy đầy đúng một nửa, cây con trái có (2n − 1)/3 < 2n/3 nút.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** Chương 6 vẫn là "Heapsort" với cùng năm mục. Thuộc tính A.length bị bỏ; các thủ tục nhận thêm tham số n (ví dụ BUILD-MAX-HEAP(A, n), HEAPSORT(A, n)). Mục 6.5 được viết lại để hàng đợi ưu tiên lưu *đối tượng* có khoá và nói rõ hơn việc ánh xạ giữa đối tượng ứng dụng và chỉ số mảng (MAX-HEAP-INSERT nhận một đối tượng x thay vì một khoá). Các khác biệt nhỏ hơn về lời văn và bài tập, người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần II — Giới thiệu (Part II Introduction, trang 146–150) — bài toán sắp xếp, vì sao sắp xếp, bảng thời gian chạy, thống kê thứ tự

```text
       BÀI TOÁN SẮP XẾP (sorting problem)
       Đầu vào: dãy n số ⟨a₁, a₂, …, aₙ⟩
       Đầu ra: hoán vị ⟨a′₁, a′₂, …, a′ₙ⟩ của đầu vào với a′₁ ≤ a′₂ ≤ … ≤ a′ₙ
       (đầu vào thường là mảng n phần tử, có thể là danh sách liên kết)
                                │
                                ▼
       CẤU TRÚC DỮ LIỆU THỰC TẾ: mỗi số là KHOÁ (key) của một BẢN GHI
       (record); phần còn lại là DỮ LIỆU VỆ TINH (satellite data), phải di
       chuyển theo khoá
       · bản ghi lớn ⇒ sắp xếp mảng CON TRỎ tới bản ghi, không chép bản ghi
       · thuật toán chỉ mô tả PHƯƠNG PHÁP; khi bàn thuật toán ta giả định
         đầu vào chỉ là các số
                                │
                                ▼
       VÌ SAO SẮP XẾP LÀ BÀI TOÁN CƠ BẢN NHẤT (năm lý do)
       1. ứng dụng tự nó cần sắp xếp (ngân hàng sắp séc theo số séc)
       2. sắp xếp là thủ tục con then chốt (vẽ đối tượng chồng lớp từ
          dưới lên trên)
       3. rất nhiều thuật toán, dùng kho kỹ thuật thiết kế phong phú
       4. chứng minh được cận dưới không tầm thường (Chương 8), và cận
          trên tốt nhất khớp với nó ⇒ biết thuật toán tối ưu tiệm cận
       5. nhiều vấn đề kỹ thuật (bộ nhớ đệm, bộ nhớ ảo, môi trường phần
          mềm) — nên xử lý ở mức thuật toán, không phải "vặn" mã
                                │
                                ▼
       CÁC THUẬT TOÁN SẮP XẾP CỦA PHẦN II
       · Ch.2: sắp xếp chèn Θ(n²), tại chỗ, nhanh khi n nhỏ;
               sắp xếp trộn Θ(n lg n), MERGE không tại chỗ
       · Ch.6: heapsort O(n lg n), tại chỗ, dùng ĐỐNG (cũng cài được hàng
               đợi ưu tiên)
       · Ch.7: quicksort, xấu nhất Θ(n²), kỳ vọng Θ(n lg n), thường nhanh
               hơn heapsort
       · bốn thuật toán trên là SẮP XẾP BẰNG SO SÁNH
       · Ch.8: mô hình cây quyết định ⇒ cận dưới Ω(n lg n) ⇒ heapsort và
               sắp xếp trộn tối ưu tiệm cận; rồi vượt cận bằng sắp xếp
               đếm Θ(k + n), cơ số Θ(d(n + k)), phân cụm O(n) trung bình
                                │
                                ▼
       ┌───────────────┬──────────────────┬───────────────────────────┐
       │ Thuật toán    │ Xấu nhất         │ Trung bình / kỳ vọng      │
       ├───────────────┼──────────────────┼───────────────────────────┤
       │ Sắp xếp chèn  │ Θ(n²)            │ Θ(n²)                     │
       │ Sắp xếp trộn  │ Θ(n lg n)        │ Θ(n lg n)                 │
       │ Heapsort      │ O(n lg n)        │ — (sách không phân tích)  │
       │ Quicksort     │ Θ(n²)            │ Θ(n lg n) (kỳ vọng)       │
       │ Sắp xếp đếm   │ Θ(k + n)         │ Θ(k + n)                  │
       │ Sắp xếp cơ số │ Θ(d(n + k))      │ Θ(d(n + k))               │
       │ Sắp xếp cụm   │ Θ(n²)            │ Θ(n) (trung bình)         │
       └───────────────┴──────────────────┴───────────────────────────┘
                                │
                                ▼
       THỐNG KÊ THỨ TỰ (order statistics): thống kê thứ i = số nhỏ thứ i
       · sắp xếp rồi lấy phần tử thứ i: Ω(n lg n) nếu không giả định gì
       · Ch.9: tìm được trong O(n) — thuật toán ngẫu nhiên (xấu nhất Θ(n²),
         kỳ vọng O(n)) và thuật toán phức tạp hơn O(n) xấu nhất
                                │
                                ▼
       NỀN TẢNG TOÁN: phân tích quicksort, sắp xếp cụm, chọn thống kê
       thứ tự dùng xác suất (Phụ lục C, Chương 5); thuật toán chọn tuyến
       tính xấu nhất cần toán tinh tế hơn
```

### Phần mở đầu Chương 6 (trước Mục 6.1, trang 151) — heapsort kết hợp ưu điểm của hai thuật toán đã biết

```text
       Sắp xếp trộn: O(n lg n) nhưng KHÔNG tại chỗ
       Sắp xếp chèn: tại chỗ nhưng Θ(n²)
                                │
                                ▼
       HEAPSORT: O(n lg n) VÀ tại chỗ (chỉ một số hằng phần tử nằm ngoài
       mảng tại mọi thời điểm)
                                │
                                ▼
       Kỹ thuật thiết kế mới: DÙNG CẤU TRÚC DỮ LIỆU ("đống") để quản lý
       thông tin; đống còn cho một hàng đợi ưu tiên hiệu quả và xuất hiện
       lại ở các chương sau
                                │
                                ▼
       Lưu ý thuật ngữ: "heap" trong sách là cấu trúc dữ liệu, KHÔNG phải
       vùng nhớ được thu gom rác (garbage-collected storage) của Java, Lisp
```

### Mục 6.1 — Đống (Heaps, trang 151–154)

```text
       ĐỐNG NHỊ PHÂN = một mảng A được nhìn như CÂY NHỊ PHÂN GẦN ĐẦY ĐỦ
       · mọi tầng đầy, trừ tầng thấp nhất được lấp từ trái sang
       · A.length: số ô của mảng; A.heap-size: số phần tử thuộc đống,
         0 ≤ A.heap-size ≤ A.length; chỉ A[1..A.heap-size] hợp lệ
                                │
                                ▼
       Điều hướng bằng số học chỉ số (gốc là A[1]):
       PARENT(i) = ⌊i/2⌋   LEFT(i) = 2i   RIGHT(i) = 2i + 1
       (dịch bit: phải 1 bit; trái 1 bit; trái 1 bit rồi thêm bit 1)
                                │
                                ▼
       Ví dụ đống max 10 phần tử (vẽ cây):
                     16(1)
                ┌──────┴──────┐
              14(2)          10(3)
            ┌───┴───┐      ┌──┴──┐
          8(4)    7(5)   9(6)   3(7)
         ┌─┴─┐    │
       2(8) 4(9) 1(10)
       Mảng: [16 14 10 8 7 9 3 2 4 1]; cây cao 3; nút 4 (giá trị 8) cao 1
                                │
                                ▼
       TÍNH CHẤT ĐỐNG (heap property), với mọi nút i khác gốc:
       · đống max: A[PARENT(i)] ≥ A[i]  ⇒ phần tử lớn nhất ở gốc
       · đống min: A[PARENT(i)] ≤ A[i]  ⇒ phần tử nhỏ nhất ở gốc
       heapsort dùng đống max; hàng đợi ưu tiên thường dùng đống min
                                │
                                ▼
       CHIỀU CAO nút = số cạnh trên đường đi xuống dài nhất tới một lá;
       chiều cao đống = chiều cao gốc = ⌊lg n⌋ = Θ(lg n)
       ⇒ các phép toán cơ bản chạy O(lg n)
                                │
                                ▼
       Lộ trình chương: MAX-HEAPIFY O(lg n) · BUILD-MAX-HEAP O(n) ·
       HEAPSORT O(n lg n) · bốn thủ tục hàng đợi ưu tiên O(lg n)
```

### Mục 6.2 — Duy trì tính chất đống (Maintaining the heap property, trang 154–156)

```text
       Tiền điều kiện của MAX-HEAPIFY(A, i): cây con gốc LEFT(i) và cây
       con gốc RIGHT(i) đã là đống max; riêng A[i] có thể nhỏ hơn con
                                │
                                ▼
       Một bước: largest = chỉ số lớn nhất trong {i, LEFT(i), RIGHT(i)}
       (chỉ xét con có chỉ số ≤ A.heap-size)
           ┌────────────────────┴────────────────────┐
           ▼                                         ▼
     largest = i:                              largest là một con:
     cây con gốc i đã là đống max,             đổi A[i] với A[largest];
     dừng                                      nút i nay thoả tính chất,
                                               nhưng cây con gốc largest
                                               có thể bị phá ⇒ gọi đệ quy
                                               MAX-HEAPIFY(A, largest)
                                │
                                ▼
       Ví dụ MAX-HEAPIFY(A, 2), A.heap-size = 10:
       [16 4 10 14 7 9 3 2 8 1]
       · nút 2 (4) có con 14, 7 → đổi với 14 → [16 14 10 4 7 9 3 2 8 1]
       · nút 4 (4) có con 2, 8 → đổi với 8  → [16 14 10 8 7 9 3 2 4 1]
       · nút 9 là lá → dừng
                                │
                                ▼
       Thời gian: Θ(1) mỗi tầng + đệ quy trên cây con của một con
       · cây con của một con có ≤ 2n/3 nút (xấu nhất khi tầng đáy đầy
         đúng một nửa)
       · T(n) ≤ T(2n/3) + Θ(1) ⇒ T(n) = O(lg n) (định lý thợ, trường hợp 2)
       · tương đương: O(h) trên nút có chiều cao h
```

### Mục 6.3 — Dựng đống (Building a heap, trang 156–159)

```text
       Các phần tử A[⌊n/2⌋+1 .. n] đều là lá (Exercise 6.1-7) ⇒ mỗi lá là
       một đống max một phần tử
                                │
                                ▼
       BUILD-MAX-HEAP(A): heap-size = length; for i = ⌊n/2⌋ downto 1:
       MAX-HEAPIFY(A, i)  — đi từ dưới lên
                                │
                                ▼
       BẤT BIẾN: đầu mỗi vòng lặp, mỗi nút i+1, i+2, …, n là gốc một
       đống max
       · khởi tạo: i = ⌊n/2⌋, các nút sau i đều là lá
       · duy trì: con của i có chỉ số > i nên đã là gốc đống max ⇒ đúng
         tiền điều kiện của MAX-HEAPIFY(A, i); giảm i giữ bất biến
       · kết thúc: i = 0 ⇒ nút 1 là gốc một đống max
                                │
                                ▼
       Ví dụ: [4 1 3 2 16 9 10 14 8 7]
       i=5: 16 ≥ 7, không đổi
       i=4: 2 ↔ 14                     → [4 1 3 14 16 9 10 2 8 7]
       i=3: 3 ↔ 10                     → [4 1 10 14 16 9 3 2 8 7]
       i=2: 1 ↔ 16, rồi 1 ↔ 7          → [4 16 10 14 7 9 3 2 8 1]
       i=1: 4 ↔ 16, 4 ↔ 14, 4 ↔ 8      → [16 14 10 8 7 9 3 2 4 1]
                                │
                                ▼
       Thời gian
       · cận thô: O(n) lần gọi × O(lg n) = O(n lg n) — đúng nhưng không chặt
       · cận chặt: có ≤ ⌈n/2^(h+1)⌉ nút cao h; MAX-HEAPIFY trên nút cao h
         tốn O(h)
         Σ_{h=0}^{⌊lg n⌋} ⌈n/2^(h+1)⌉ · O(h) = O(n · Σ_{h=0}^{⌊lg n⌋} h/2^h)
         và Σ_{h=0}^{∞} h/2^h = (1/2)/(1 − 1/2)² = 2   (công thức (A.8), x = 1/2)
         ⇒ BUILD-MAX-HEAP chạy O(n)
       · BUILD-MIN-HEAP: thay MAX-HEAPIFY bằng MIN-HEAPIFY, cũng O(n)
```

### Mục 6.4 — Thuật toán heapsort (The heapsort algorithm, trang 159–162)

```text
       BUILD-MAX-HEAP(A) trên A[1..n]   — O(n)
                                │
                                ▼
       for i = n downto 2:
       · phần tử lớn nhất nằm ở A[1] ⇒ đổi A[1] với A[i]: nó về đúng vị
         trí cuối cùng
       · bỏ nút i khỏi đống: A.heap-size = A.heap-size − 1
       · hai cây con của gốc vẫn là đống max, chỉ gốc mới có thể sai
         ⇒ MAX-HEAPIFY(A, 1) — O(lg n)
                                │
                                ▼
       Mảng trong lúc chạy:
       ┌────────────────────────────┬────────────────────────────────┐
       │ A[1..i]: đống max chứa i   │ A[i+1..n]: n − i phần tử lớn   │
       │ phần tử nhỏ nhất           │ nhất, đã sắp xếp               │
       └────────────────────────────┴────────────────────────────────┘
                                │
                                ▼
       Ví dụ: đống [16 14 10 8 7 9 3 2 4 1] → sau 9 lần lặp
       → [1 2 3 4 7 8 9 10 14 16]
                                │
                                ▼
       Tổng: O(n) + (n − 1) · O(lg n) = O(n lg n), sắp xếp tại chỗ
```

### Mục 6.5 — Hàng đợi ưu tiên (Priority queues, trang 162–166)

```text
       Quicksort cài đặt tốt thường nhanh hơn heapsort trong thực tế,
       nhưng bản thân ĐỐNG có nhiều ứng dụng; phổ biến nhất: HÀNG ĐỢI ƯU TIÊN
                                │
                                ▼
       Hàng đợi ưu tiên max: duy trì tập S, mỗi phần tử có KHOÁ
       · INSERT(S, x): S = S ∪ {x}
       · MAXIMUM(S): trả về phần tử khoá lớn nhất
       · EXTRACT-MAX(S): lấy ra và trả về phần tử khoá lớn nhất
       · INCREASE-KEY(S, x, k): tăng khoá của x lên k (k ≥ khoá cũ)
       ứng dụng: lập lịch công việc trên máy dùng chung
       Hàng đợi ưu tiên min: INSERT, MINIMUM, EXTRACT-MIN, DECREASE-KEY
       ứng dụng: mô phỏng hướng sự kiện (khoá = thời điểm xảy ra);
       Chương 23, 24 dùng DECREASE-KEY
                                │
                                ▼
       TAY CẦM (handle): phần tử đống lưu tay cầm tới đối tượng ứng dụng,
       đối tượng lưu chỉ số mảng của phần tử đống; khi phần tử đổi chỗ
       trong mảng, phải cập nhật chỉ số đó
                                │
                                ▼
       Cài đặt bằng đống max:
       · HEAP-MAXIMUM: return A[1]                              Θ(1)
       · HEAP-EXTRACT-MAX: lấy A[1], đưa A[heap-size] lên gốc,
         giảm heap-size, MAX-HEAPIFY(A, 1)                      O(lg n)
       · HEAP-INCREASE-KEY(A, i, key): gán khoá mới, rồi lặp
         "đổi với cha nếu cha nhỏ hơn" để phần tử NỔI LÊN        O(lg n)
       · MAX-HEAP-INSERT(A, key): thêm lá có khoá −∞,
         rồi HEAP-INCREASE-KEY lên key                           O(lg n)
                                │
                                ▼
       Ví dụ HEAP-INCREASE-KEY: trong đống [16 14 10 8 7 9 3 2 4 1],
       tăng A[9] = 4 lên 15: 15 ↔ 8 (nút 4), 15 ↔ 14 (nút 2), dừng dưới 16
       → [16 15 10 14 7 9 3 2 8 1]
                                │
                                ▼
       Kết luận: đống hỗ trợ mọi phép toán hàng đợi ưu tiên trên tập n
       phần tử trong O(lg n)
```

### Bài toán cuối chương (Problems 6-1 đến 6-3, trang 166–168)

```text
       6-1 Dựng đống bằng phép chèn: BUILD-MAX-HEAP′ gọi MAX-HEAP-INSERT
           lần lượt cho A[2], …, A[n]
           · không phải lúc nào cũng cho cùng đống với BUILD-MAX-HEAP
           · xấu nhất Θ(n lg n) (so với O(n) của BUILD-MAX-HEAP)
                                │
                                ▼
       6-2 Đống d-phân (d-ary heap): mỗi nút trong có d con
           · biểu diễn trong mảng; chiều cao Θ(log_d n)
           · EXTRACT-MAX O(d log_d n); INSERT, INCREASE-KEY O(log_d n)
                                │
                                ▼
       6-3 Bảng Young m × n: hàng tăng từ trái sang, cột tăng từ trên
           xuống, ô ∞ là ô trống
           · EXTRACT-MIN, INSERT, tìm kiếm đều O(m + n)
           · sắp xếp n² số trong O(n³) bằng bảng n × n
```

### Ghi chú chương (Chapter notes, trang 168–169)

```text
       Heapsort do Williams phát minh; ông cũng mô tả hàng đợi ưu tiên
       bằng đống. BUILD-MAX-HEAP do Floyd đề xuất
                                │
                                ▼
       Sách dùng đống min cho hàng đợi ưu tiên min ở Chương 16, 23, 24;
       cài đặt nhanh hơn ở Chương 19 (đống Fibonacci) và Chương 20 (khoá
       là số nguyên không âm trong tập bị chặn)
                                │
                                ▼
       Khoá là số nguyên b bit, bộ nhớ gồm từ b bit:
       · Fredman–Willard: MINIMUM O(1), INSERT và EXTRACT-MIN O(√lg n)
       · Thorup: O(lg lg n) (bộ nhớ không bị chặn theo n; có thể đưa về
         bộ nhớ tuyến tính bằng băm ngẫu nhiên)
                                │
                                ▼
       Trường hợp ĐƠN ĐIỆU (giá trị EXTRACT-MIN trả về tăng dần theo thời
       gian; gặp trong Dijkstra và mô phỏng sự kiện rời rạc), khoá nguyên
       trong 1..C:
       · đống cơ số (radix heap, Ahuja–Mehlhorn–Orlin–Tarjan): EXTRACT-MIN,
         INSERT O(lg C) khấu hao, DECREASE-KEY O(1)
       · kết hợp đống Fibonacci: O(√lg C)
       · Cherkassky–Goldberg–Silverstein: O(lg^(1/3+ε) C) kỳ vọng
       · Raman: O(min(lg^(1/4+ε) C, lg^(1/3+ε) n)), với mọi ε > 0 cố định
```

## Ba câu hỏi chương này trả lời

1. **Đống là gì, và vì sao một mảng bình thường có thể hoạt động như một cây?** Đống nhị phân là mảng A[1..A.heap-size] được nhìn như cây nhị phân gần đầy đủ: gốc ở A[1], nút i có cha ⌊i/2⌋, con trái 2i, con phải 2i + 1, nên không cần lưu con trỏ. Đống max đòi hỏi A[PARENT(i)] ≥ A[i] với mọi nút khác gốc, do đó phần tử lớn nhất ở gốc. Cây n nút có chiều cao ⌊lg n⌋ (với n = 10 là 3; với n = 1.000.000 là 19), nên mọi thao tác chỉ đi theo một đường từ gốc tới lá đều tốn O(lg n). Ví dụ mảng [16, 14, 10, 8, 7, 9, 3, 2, 4, 1] là đống max: 16 ≥ 14, 10; 14 ≥ 8, 7; 10 ≥ 9, 3; 8 ≥ 2, 4; 7 ≥ 1.
2. **Làm sao sắp xếp n số tại chỗ trong O(n lg n) ở trường hợp xấu nhất?** HEAPSORT: dựng đống max bằng BUILD-MAX-HEAP trong O(n) (gọi MAX-HEAPIFY từ nút ⌊n/2⌋ lùi về 1; chi phí tổng Σ ⌈n/2^(h+1)⌉ · O(h) = O(n) vì Σ h/2^h = 2), rồi lặp n − 1 lần: đổi A[1] (lớn nhất) với phần tử cuối của vùng đống, giảm heap-size, gọi MAX-HEAPIFY(A, 1) trong O(lg n). Phần cuối mảng dần chứa các phần tử lớn nhất đã sắp xếp. Tổng O(n lg n), chỉ dùng thêm hằng số biến. Ví dụ: đống [16, 14, 10, 8, 7, 9, 3, 2, 4, 1] trở thành [1, 2, 3, 4, 7, 8, 9, 10, 14, 16] sau 9 lần lặp.
3. **Làm sao cài một hàng đợi ưu tiên mà mọi phép toán đều nhanh?** Dùng đống max: MAXIMUM là đọc A[1] trong Θ(1); EXTRACT-MAX đưa phần tử cuối lên gốc rồi cho chìm xuống bằng MAX-HEAPIFY; INCREASE-KEY gán khoá mới rồi cho phần tử nổi lên bằng cách đổi với cha; INSERT thêm một lá khoá −∞ rồi tăng khoá. Ba phép sau đều đi theo một đường gốc–lá nên O(lg n). So với mảng không sắp xếp (INSERT O(1), EXTRACT-MAX Θ(n)) hay mảng đã sắp xếp (EXTRACT-MAX O(1), INSERT Θ(n)), đống cân bằng cả hai: với 10⁶ phần tử, mỗi phép toán chỉ khoảng 20 tầng.

## Khái niệm cần biết

- **Bài toán sắp xếp (sorting problem):** cho dãy n số ⟨a₁, …, aₙ⟩, tìm một hoán vị ⟨a′₁, …, a′ₙ⟩ của nó với a′₁ ≤ a′₂ ≤ … ≤ a′ₙ. Ví dụ ⟨31, 41, 59, 26, 41, 58⟩ cho ⟨26, 31, 41, 41, 58, 59⟩. Quan trọng vì đây là bài toán của cả Phần II.
- **Bản ghi, khoá, dữ liệu vệ tinh (record, key, satellite data):** trong thực tế mỗi số cần sắp xếp là *khoá* của một *bản ghi*; phần còn lại của bản ghi là dữ liệu vệ tinh, phải đi theo khoá khi khoá bị hoán vị. Ví dụ bản ghi sinh viên (mã số 1023, họ tên, ngày sinh, điểm): sắp theo mã số thì mã số là khoá, các trường khác là dữ liệu vệ tinh. Khi bản ghi lớn, người ta sắp xếp mảng con trỏ tới bản ghi để giảm việc chép dữ liệu.
- **Sắp xếp tại chỗ (in place):** chỉ một số hằng phần tử của mảng đầu vào được lưu ra ngoài mảng tại bất kỳ thời điểm nào. Heapsort tại chỗ (chỉ cần một biến tạm để đổi chỗ, cộng các chỉ số), sắp xếp trộn thì không (thủ tục MERGE cần mảng phụ cỡ n). Quan trọng vì đây là một trong hai ưu điểm heapsort đạt được.
- **Sắp xếp bằng so sánh (comparison sort):** xác định thứ tự chỉ bằng cách so sánh các phần tử. Sắp xếp chèn, trộn, vun đống, nhanh đều là sắp xếp bằng so sánh và chịu cận dưới Ω(n lg n) (Chương 8). Ví dụ với n = 1.024, mọi thuật toán loại này cần ít nhất ⌈lg(1.024!)⌉ ≈ 8.770 phép so sánh trong trường hợp xấu nhất (theo tính toán của người tổng hợp).
- **Thống kê thứ tự (order statistic):** thống kê thứ tự thứ i của tập n số là số nhỏ thứ i. Ví dụ với {7, 2, 9, 4, 5}, thống kê thứ 1 là 2 (min), thứ 3 là 5 (trung vị), thứ 5 là 9 (max). Chương 9 tìm nó trong O(n).
- **Cây nhị phân gần đầy đủ (nearly complete binary tree):** mọi tầng đều đầy, trừ tầng thấp nhất được lấp liên tục từ trái sang tới một điểm. Ví dụ cây 10 nút: tầng 0 có 1 nút, tầng 1 có 2, tầng 2 có 4, tầng 3 có 3 nút đặt ở ba vị trí trái nhất. Quan trọng vì chính hình dạng "không có lỗ" này cho phép lưu cây trong mảng không cần con trỏ.
- **Đống nhị phân (binary heap):** mảng A có hai thuộc tính A.length (số ô của mảng) và A.heap-size (số phần tử thuộc đống, 0 ≤ A.heap-size ≤ A.length); chỉ A[1..A.heap-size] là phần tử hợp lệ của đống. Ví dụ mảng 12 ô chứa đống 10 phần tử: A.length = 12, A.heap-size = 10, hai ô A[11], A[12] có thể chứa số nhưng không thuộc đống. Quan trọng vì heapsort dùng đúng hai thuộc tính này để tách "vùng đống" khỏi "vùng đã sắp xếp" trong cùng một mảng.
- **PARENT, LEFT, RIGHT:** PARENT(i) = ⌊i/2⌋, LEFT(i) = 2i, RIGHT(i) = 2i + 1. Ví dụ nút 5 có cha 2, con trái 10, con phải 11. Trên máy tính, ba phép này là phép dịch bit: 5 = 101₂, dịch trái được 1010₂ = 10, dịch trái và thêm bit 1 được 1011₂ = 11, dịch phải được 10₂ = 2.
- **Tính chất đống max / đống min (max-heap / min-heap property):** đống max: A[PARENT(i)] ≥ A[i] với mọi nút i khác gốc, nên giá trị một nút không lớn hơn giá trị cha, phần tử lớn nhất ở gốc và mỗi cây con chứa giá trị không lớn hơn gốc của nó. Đống min: A[PARENT(i)] ≤ A[i], phần tử nhỏ nhất ở gốc. Ví dụ [1, 3, 2, 7, 4] là đống min (1 ≤ 3, 2; 3 ≤ 7, 4) nhưng không là đống max.
- **Chiều cao của nút và của đống (height):** chiều cao một nút là số cạnh trên đường đi đơn hướng xuống dài nhất từ nút đó tới một lá; chiều cao của đống là chiều cao của gốc. Ví dụ đống 10 phần tử ở trên: lá có chiều cao 0, nút 4 (giá trị 8) có chiều cao 1, nút 2 có chiều cao 2, gốc có chiều cao 3 = ⌊lg 10⌋. Quan trọng vì thời gian của MAX-HEAPIFY tỷ lệ với chiều cao nút.
- **MAX-HEAPIFY (cho chìm xuống):** khi hai cây con của nút i đã là đống max nhưng A[i] có thể nhỏ hơn con, đổi A[i] với con lớn hơn và lặp lại trên cây con đó. Ví dụ [16, 4, 10, 14, 7, 9, 3, 2, 8, 1] với i = 2: 4 đổi với 14, rồi đổi với 8. Thời gian O(lg n). Đây là "viên gạch" của mọi thủ tục khác trong chương.
- **BUILD-MAX-HEAP (dựng đống):** gọi MAX-HEAPIFY từ nút ⌊n/2⌋ lùi về nút 1. Ví dụ [4, 1, 3, 2, 16, 9, 10, 14, 8, 7] thành [16, 14, 10, 8, 7, 9, 3, 2, 4, 1]. Thời gian O(n), không phải O(n lg n), vì đa số nút nằm gần đáy.
- **Hàng đợi ưu tiên (priority queue):** cấu trúc dữ liệu duy trì tập S, mỗi phần tử có một khoá; bản max hỗ trợ INSERT, MAXIMUM, EXTRACT-MAX, INCREASE-KEY; bản min hỗ trợ INSERT, MINIMUM, EXTRACT-MIN, DECREASE-KEY. Ví dụ hàng đợi công việc có độ ưu tiên {3, 8, 5}: EXTRACT-MAX trả về công việc ưu tiên 8, còn {3, 5}. Quan trọng vì đây là ứng dụng chính của đống, dùng lại ở Chương 16, 23, 24.
- **Tay cầm (handle):** thông tin để đi từ phần tử hàng đợi tới đối tượng ứng dụng tương ứng (ví dụ con trỏ hoặc số nguyên) và ngược lại (thường là chỉ số mảng). Ví dụ công việc "in báo cáo" lưu chỉ số 7 trong đống; khi phần tử của nó bị đổi lên ô 3, chỉ số lưu trong đối tượng công việc phải đổi thành 3. Quan trọng vì không có tay cầm thì không gọi được INCREASE-KEY/DECREASE-KEY trên một đối tượng cụ thể.
- **Phép toán "nổi lên" (đổi với cha) trong HEAP-INCREASE-KEY:** sau khi tăng khoá, phần tử được so với cha và đổi chỗ chừng nào cha nhỏ hơn. Ví dụ tăng 4 lên 15 ở nút 9: đổi với 8 ở nút 4, rồi với 14 ở nút 2, dừng vì cha 16 ≥ 15. Đây là chiều ngược lại của MAX-HEAPIFY.
- **Tổng Σ h/2^h:** Σ_{h=0}^{∞} h/2^h = 2, lấy từ công thức (A.8) Σ_{k=0}^{∞} k xᵏ = x/(1 − x)² với x = 1/2: (1/2)/(1/4) = 2. Kiểm tra: 0 + 1/2 + 2/4 + 3/8 + 4/16 + 5/32 = 0,5 + 0,5 + 0,375 + 0,25 + 0,15625 = 1,78125, tiến dần về 2. Quan trọng vì đây là lý do BUILD-MAX-HEAP tuyến tính.
- **Bất biến vòng lặp (loop invariant):** mệnh đề đúng đầu mỗi vòng lặp, chứng minh qua khởi tạo, duy trì, kết thúc (Chương 2). Chương này dùng nó cho BUILD-MAX-HEAP (các nút i + 1..n là gốc đống max), HEAPSORT (Exercise 6.4-2) và HEAP-INCREASE-KEY (Exercise 6.5-5).
- **Định lý thợ (master theorem):** công thức nghiệm cho T(n) = aT(n/b) + f(n) (Chương 4). Ở đây a = 1, b = 3/2, f(n) = Θ(1) = Θ(n^(log_{3/2} 1)) = Θ(n⁰), rơi vào trường hợp 2, cho T(n) = Θ(lg n), nên MAX-HEAPIFY là O(lg n).
- **Đống d-phân (d-ary heap):** như đống nhị phân nhưng mỗi nút trong (trừ tối đa một nút) có d con. Ví dụ d = 3, 13 phần tử: chiều cao 2 (1 + 3 + 9 = 13). Chiều cao nhỏ hơn làm INSERT nhanh hơn, nhưng EXTRACT-MAX phải so d con ở mỗi tầng.
- **Bảng Young (Young tableau):** ma trận m × n, mỗi hàng tăng từ trái sang phải, mỗi cột tăng từ trên xuống, ô ∞ được coi là trống. Ví dụ bảng 2 × 2 [[1, 3], [2, ∞]] chứa 3 số. Là "đống hai chiều" của Problem 6-3.

## Nội dung chi tiết

### 1. Phần II — Giới thiệu (Part II Introduction, trang 146–150)

Trang 146 là trang tên phần, chỉ mang tiêu đề "II Sorting and Order Statistics" (Sắp xếp và thống kê thứ tự). Lời giới thiệu Phần II nằm ở trang 147–150.

#### Bài toán sắp xếp

Phần này trình bày một số thuật toán giải **bài toán sắp xếp** (sorting problem):

- **Đầu vào:** một dãy n số ⟨a₁, a₂, …, aₙ⟩.
- **Đầu ra:** một hoán vị (sắp xếp lại) ⟨a′₁, a′₂, …, a′ₙ⟩ của dãy đầu vào sao cho a′₁ ≤ a′₂ ≤ … ≤ a′ₙ.

Dãy đầu vào thường là một mảng n phần tử, dù có thể được biểu diễn theo cách khác, chẳng hạn danh sách liên kết.

#### Cấu trúc của dữ liệu (The structure of the data)

Trong thực tế, các số cần sắp xếp hiếm khi là giá trị đứng riêng lẻ. Mỗi số thường là một phần của một tập dữ liệu gọi là **bản ghi** (record). Mỗi bản ghi chứa một **khoá** (key) — giá trị dùng để sắp xếp. Phần còn lại của bản ghi là **dữ liệu vệ tinh** (satellite data), thường được mang theo cùng khoá. Trong thực tế, khi thuật toán sắp xếp hoán vị các khoá, nó cũng phải hoán vị dữ liệu vệ tinh. Nếu mỗi bản ghi chứa nhiều dữ liệu vệ tinh, ta thường hoán vị một mảng con trỏ tới các bản ghi thay vì chính các bản ghi, để giảm việc di chuyển dữ liệu.

Theo một nghĩa nào đó, chính những chi tiết cài đặt này phân biệt một thuật toán với một chương trình hoàn chỉnh. Một thuật toán sắp xếp mô tả *phương pháp* xác định thứ tự đã sắp, bất kể ta sắp xếp các số đơn lẻ hay các bản ghi lớn chứa nhiều byte dữ liệu vệ tinh. Vì vậy, khi tập trung vào bài toán sắp xếp, ta thường giả định đầu vào chỉ gồm các số. Chuyển một thuật toán sắp xếp số thành chương trình sắp xếp bản ghi là đơn giản về mặt khái niệm, dù trong một tình huống kỹ thuật cụ thể, những chi tiết tinh tế khác có thể khiến việc lập trình thực sự trở thành thách thức.

Ví dụ của người tổng hợp: ba bản ghi (khoá = điểm) ⟨(8, "An"), (5, "Bình"), (9, "Chi")⟩ sắp theo khoá thành ⟨(5, "Bình"), (8, "An"), (9, "Chi")⟩ — tên đi theo điểm. Nếu mỗi bản ghi dài 1 KB, sắp mảng ba con trỏ (mỗi con trỏ 8 byte) rẻ hơn nhiều so với chép qua lại các bản ghi 1 KB.

#### Vì sao sắp xếp? (Why sorting?)

Nhiều nhà khoa học máy tính coi sắp xếp là bài toán cơ bản nhất trong nghiên cứu thuật toán. Có một số lý do:

- Đôi khi ứng dụng tự nó cần sắp xếp thông tin. Ví dụ, để lập bảng sao kê cho khách hàng, ngân hàng cần sắp séc theo số séc.
- Các thuật toán thường dùng sắp xếp làm thủ tục con then chốt. Ví dụ, một chương trình vẽ các đối tượng đồ hoạ chồng lên nhau có thể phải sắp xếp chúng theo quan hệ "nằm trên" để vẽ từ dưới lên trên. Sách sẽ gặp nhiều thuật toán dùng sắp xếp làm thủ tục con.
- Có rất nhiều thuật toán sắp xếp để lựa chọn, và chúng dùng một kho kỹ thuật phong phú. Thực ra, nhiều kỹ thuật quan trọng dùng khắp ngành thiết kế thuật toán xuất hiện trong các thuật toán sắp xếp được phát triển qua nhiều năm. Theo nghĩa này, sắp xếp cũng là bài toán có giá trị lịch sử.
- Ta chứng minh được một cận dưới không tầm thường cho sắp xếp (Chương 8). Các cận trên tốt nhất khớp với cận dưới về mặt tiệm cận, nên ta biết các thuật toán sắp xếp của mình tối ưu tiệm cận. Hơn nữa, có thể dùng cận dưới của sắp xếp để chứng minh cận dưới cho một số bài toán khác.
- Nhiều vấn đề kỹ thuật nổi lên khi cài đặt thuật toán sắp xếp. Chương trình sắp xếp nhanh nhất cho một tình huống cụ thể có thể phụ thuộc nhiều yếu tố, như hiểu biết trước về khoá và dữ liệu vệ tinh, phân cấp bộ nhớ (bộ nhớ đệm và bộ nhớ ảo) của máy, và môi trường phần mềm. Nhiều vấn đề này nên được giải quyết ở mức thuật toán, chứ không phải bằng cách "vặn" (tweaking) mã.

#### Các thuật toán sắp xếp (Sorting algorithms)

Chương 2 đã giới thiệu hai thuật toán sắp xếp n số thực. Sắp xếp chèn tốn Θ(n²) trong trường hợp xấu nhất; tuy vậy, vì vòng lặp trong của nó gọn, nó là thuật toán sắp xếp tại chỗ nhanh cho đầu vào nhỏ. (Nhắc lại: một thuật toán sắp xếp **tại chỗ** (in place) nếu chỉ một số hằng phần tử của mảng đầu vào từng được lưu ngoài mảng.) Sắp xếp trộn có thời gian tiệm cận tốt hơn, Θ(n lg n), nhưng thủ tục MERGE nó dùng không chạy tại chỗ.

Phần II giới thiệu thêm hai thuật toán sắp xếp số thực bất kỳ. Heapsort, ở Chương 6, sắp xếp n số tại chỗ trong O(n lg n). Nó dùng một cấu trúc dữ liệu quan trọng gọi là đống (heap), với đống ta còn cài đặt được hàng đợi ưu tiên.

Quicksort, ở Chương 7, cũng sắp xếp n số tại chỗ, nhưng thời gian xấu nhất của nó là Θ(n²). Tuy vậy, thời gian kỳ vọng của nó là Θ(n lg n), và nói chung nó chạy nhanh hơn heapsort trong thực tế. Giống sắp xếp chèn, quicksort có mã gọn, nên hằng số ẩn trong thời gian chạy nhỏ. Nó là thuật toán phổ biến để sắp xếp mảng đầu vào lớn.

Sắp xếp chèn, sắp xếp trộn, heapsort và quicksort đều là **sắp xếp bằng so sánh** (comparison sorts): chúng xác định thứ tự của mảng đầu vào bằng cách so sánh các phần tử. Chương 8 mở đầu bằng mô hình cây quyết định để nghiên cứu giới hạn hiệu năng của sắp xếp bằng so sánh. Dùng mô hình này, sách chứng minh cận dưới Ω(n lg n) cho thời gian xấu nhất của mọi thuật toán sắp xếp bằng so sánh trên n đầu vào, qua đó cho thấy heapsort và sắp xếp trộn là các thuật toán sắp xếp bằng so sánh tối ưu tiệm cận.

Chương 8 sau đó chỉ ra rằng ta có thể vượt cận dưới Ω(n lg n) nếu thu được thông tin về thứ tự của đầu vào bằng cách khác ngoài so sánh. Chẳng hạn, thuật toán **sắp xếp đếm** (counting sort) giả định các số đầu vào thuộc tập {0, 1, …, k}. Dùng việc đánh chỉ số mảng làm công cụ xác định thứ tự tương đối, sắp xếp đếm sắp n số trong Θ(k + n). Vì vậy khi k = O(n), sắp xếp đếm chạy trong thời gian tuyến tính theo kích thước mảng đầu vào. Một thuật toán liên quan, **sắp xếp cơ số** (radix sort), mở rộng phạm vi của sắp xếp đếm: nếu có n số nguyên cần sắp, mỗi số có d chữ số, mỗi chữ số nhận tối đa k giá trị, thì sắp xếp cơ số chạy trong Θ(d(n + k)). Khi d là hằng số và k là O(n), sắp xếp cơ số chạy tuyến tính. Thuật toán thứ ba, **sắp xếp phân cụm** (bucket sort), cần biết phân phối xác suất của các số đầu vào; nó sắp n số thực phân phối đều trên nửa khoảng [0, 1) trong thời gian trung bình O(n).

Bảng sau tóm tắt thời gian chạy của các thuật toán sắp xếp ở Chương 2 và 6–8. Như thường lệ, n là số phần tử cần sắp. Với sắp xếp đếm, các phần tử là số nguyên thuộc {0, 1, …, k}. Với sắp xếp cơ số, mỗi phần tử là số có d chữ số, mỗi chữ số nhận k giá trị. Với sắp xếp phân cụm, các khoá là số thực phân phối đều trên [0, 1). Cột phải ghi thời gian trung bình hoặc kỳ vọng, có chú thích loại nào khi nó khác thời gian xấu nhất. Sách bỏ trống thời gian trung bình của heapsort vì không phân tích nó.

| Thuật toán | Thời gian xấu nhất | Thời gian trung bình / kỳ vọng |
|---|---|---|
| Sắp xếp chèn (insertion sort) | Θ(n²) | Θ(n²) |
| Sắp xếp trộn (merge sort) | Θ(n lg n) | Θ(n lg n) |
| Heapsort | O(n lg n) | — |
| Quicksort | Θ(n²) | Θ(n lg n) (kỳ vọng) |
| Sắp xếp đếm (counting sort) | Θ(k + n) | Θ(k + n) |
| Sắp xếp cơ số (radix sort) | Θ(d(n + k)) | Θ(d(n + k)) |
| Sắp xếp phân cụm (bucket sort) | Θ(n²) | Θ(n) (trung bình) |

Nhận xét của người tổng hợp: bảng ghi heapsort là O(n lg n) chứ không phải Θ(n lg n), vì tại đây chưa chứng minh cận dưới; Exercise 6.4-4 sau đó cho thấy thời gian xấu nhất cũng là Ω(n lg n), nên thực ra là Θ(n lg n).

#### Thống kê thứ tự (Order statistics)

**Thống kê thứ tự thứ i** (ith order statistic) của một tập n số là số nhỏ thứ i trong tập. Dĩ nhiên ta có thể chọn thống kê thứ tự thứ i bằng cách sắp xếp đầu vào rồi lấy phần tử thứ i của đầu ra. Không có giả định gì về phân phối đầu vào, cách này tốn Ω(n lg n), như cận dưới ở Chương 8 cho thấy.

Chương 9 chỉ ra rằng có thể tìm phần tử nhỏ thứ i trong O(n), kể cả khi các phần tử là số thực bất kỳ. Sách trình bày một thuật toán ngẫu nhiên với pseudocode gọn, chạy Θ(n²) trong trường hợp xấu nhất nhưng có thời gian kỳ vọng O(n), và một thuật toán phức tạp hơn chạy O(n) trong trường hợp xấu nhất.

#### Nền tảng (Background)

Phần lớn Phần II không dựa vào toán khó, nhưng một số mục đòi hỏi trình độ toán nhất định. Cụ thể, phân tích quicksort, sắp xếp phân cụm và thuật toán thống kê thứ tự dùng xác suất (ôn lại ở Phụ lục C) và nội dung phân tích xác suất, thuật toán ngẫu nhiên ở Chương 5. Phân tích thuật toán chọn thống kê thứ tự tuyến tính trong trường hợp xấu nhất dùng toán tinh tế hơn các phân tích trường hợp xấu nhất khác trong phần này.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: sắp xếp gần như có mặt ở mọi tầng của hệ thống phần mềm — cơ sở dữ liệu sắp xếp để thực hiện ORDER BY, phép nối sort-merge join và dựng chỉ mục; các hệ xử lý dữ liệu lớn có bước "shuffle and sort" giữa hai pha; công cụ tìm kiếm sắp xếp kết quả theo điểm liên quan. Ý "sắp xếp mảng con trỏ thay vì bản ghi" chính là cách các ngôn ngữ như Java, Python sắp xếp danh sách đối tượng: danh sách chỉ chứa tham chiếu, đối tượng không bị chép.

### 2. Phần mở đầu Chương 6 (trang 151)

Chương này giới thiệu một thuật toán sắp xếp khác: **heapsort** (sắp xếp vun đống). Giống sắp xếp trộn nhưng khác sắp xếp chèn, thời gian chạy của heapsort là O(n lg n). Giống sắp xếp chèn nhưng khác sắp xếp trộn, heapsort sắp xếp tại chỗ: chỉ một số hằng phần tử của mảng được lưu ngoài mảng đầu vào tại mọi thời điểm. Như vậy heapsort kết hợp những thuộc tính tốt hơn của hai thuật toán sắp xếp đã bàn.

Heapsort còn giới thiệu một kỹ thuật thiết kế thuật toán khác: dùng một cấu trúc dữ liệu — ở đây là cấu trúc gọi là "đống" (heap) — để quản lý thông tin. Cấu trúc đống không chỉ có ích cho heapsort mà còn tạo ra một hàng đợi ưu tiên hiệu quả. Cấu trúc đống sẽ xuất hiện lại trong các thuật toán ở các chương sau.

Thuật ngữ "heap" ban đầu được đặt ra trong bối cảnh heapsort, nhưng về sau còn được dùng để chỉ "vùng nhớ được thu gom rác" (garbage-collected storage), như vùng nhớ mà các ngôn ngữ lập trình Java và Lisp cung cấp. Cấu trúc đống của sách *không phải* vùng nhớ thu gom rác; mỗi khi sách nói đến đống, đó là một cấu trúc dữ liệu chứ không phải một khía cạnh của việc thu gom rác.

| Thuật toán | Thời gian xấu nhất | Tại chỗ? |
|---|---|---|
| Sắp xếp chèn | Θ(n²) | có |
| Sắp xếp trộn | Θ(n lg n) | không |
| Heapsort | O(n lg n) | có |

### 3. Đống (6.1 Heaps, trang 151–154)

**Đống nhị phân** (binary heap) là một đối tượng mảng mà ta có thể nhìn như một **cây nhị phân gần đầy đủ** (nearly complete binary tree, Mục B.5.3 của Phụ lục B). Mỗi nút của cây ứng với một phần tử của mảng. Cây được lấp đầy ở mọi tầng, trừ có thể tầng thấp nhất, tầng này được lấp từ trái sang tới một điểm nào đó.

Một mảng A biểu diễn đống là đối tượng có hai thuộc tính:
- **A.length**: (như thường lệ) số phần tử của mảng;
- **A.heap-size**: số phần tử của đống được lưu trong mảng A.

Tức là, dù A[1..A.length] có thể chứa số, chỉ các phần tử trong A[1..A.heap-size], với 0 ≤ A.heap-size ≤ A.length, là phần tử hợp lệ của đống. Gốc của cây là A[1], và cho chỉ số i của một nút, ta dễ dàng tính chỉ số của cha, con trái, con phải:

```text
PARENT(i)
1  return ⌊i/2⌋

LEFT(i)
1  return 2i

RIGHT(i)
1  return 2i + 1
```

Trên hầu hết máy tính, thủ tục LEFT tính 2i bằng một lệnh, chỉ việc dịch biểu diễn nhị phân của i sang trái một bit. Tương tự, RIGHT tính nhanh 2i + 1 bằng cách dịch i sang trái một bit rồi thêm bit 1 vào vị trí thấp nhất. PARENT tính ⌊i/2⌋ bằng cách dịch i sang phải một bit. Các cài đặt heapsort tốt thường viết ba thủ tục này dưới dạng "macro" hoặc thủ tục "nội tuyến" (inline).

#### Ví dụ đống max 10 phần tử (Hình 6.1 của sách)

Đống max chứa mảng A = [16, 14, 10, 8, 7, 9, 3, 2, 4, 1]. Nhìn như cây nhị phân (số trong ngoặc là chỉ số mảng, số ngoài ngoặc là giá trị lưu ở nút):

```text
                     16 (1)
              ┌────────┴────────┐
           14 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
       8 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  4 (9)  1 (10)
```

Nhìn như mảng, với quan hệ cha–con ghi bên dưới:

```text
chỉ số:  1   2   3   4   5   6   7   8   9   10
giá trị: 16  14  10  8   7   9   3   2   4   1

cha → các con:  1 → 2, 3     2 → 4, 5     3 → 6, 7
                4 → 8, 9     5 → 10
```

Trong hình gốc, các đường nối phía trên và phía dưới mảng cho thấy quan hệ cha–con; cha luôn nằm bên trái các con của nó. Cây có chiều cao 3; nút ở chỉ số 4 (giá trị 8) có chiều cao 1.

#### Đống max và đống min

Có hai loại đống nhị phân: đống max và đống min. Ở cả hai loại, giá trị ở các nút thoả một **tính chất đống** (heap property), cụ thể tuỳ loại đống.

Trong **đống max** (max-heap), **tính chất đống max** là: với mọi nút i khác gốc,

```text
A[PARENT(i)] ≥ A[i]
```

tức là giá trị của một nút không lớn hơn giá trị của cha nó. Do đó phần tử lớn nhất của đống max nằm ở gốc, và cây con có gốc tại một nút chứa các giá trị không lớn hơn giá trị ở chính nút đó.

**Đống min** (min-heap) được tổ chức theo chiều ngược lại; **tính chất đống min** là: với mọi nút i khác gốc,

```text
A[PARENT(i)] ≤ A[i]
```

Phần tử nhỏ nhất của đống min nằm ở gốc.

Thuật toán heapsort dùng đống max. Đống min thường dùng để cài hàng đợi ưu tiên (Mục 6.5). Sách sẽ nói rõ cần đống max hay đống min cho từng ứng dụng; khi một tính chất áp dụng cho cả hai, sách chỉ dùng từ "đống".

#### Chiều cao

Nhìn đống như cây, ta định nghĩa **chiều cao** (height) của một nút trong đống là số cạnh trên đường đi đơn hướng xuống dài nhất từ nút đó tới một lá, và chiều cao của đống là chiều cao của gốc. Vì đống n phần tử dựa trên một cây nhị phân (gần) đầy đủ, chiều cao của nó là Θ(lg n) (Exercise 6.1-2). Các phép toán cơ bản trên đống chạy trong thời gian tối đa tỷ lệ với chiều cao cây, nên tốn O(lg n).

Bảng chiều cao từng nút trong ví dụ trên (người tổng hợp tính):

| Chỉ số | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Giá trị | 16 | 14 | 10 | 8 | 7 | 9 | 3 | 2 | 4 | 1 |
| Chiều cao | 3 | 2 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 |

Năm lá (chỉ số 6–10) có chiều cao 0; ba nút chiều cao 1; một nút chiều cao 2; gốc chiều cao 3.

#### Lộ trình của phần còn lại của chương

- Thủ tục MAX-HEAPIFY, chạy O(lg n), là chìa khoá để duy trì tính chất đống max.
- Thủ tục BUILD-MAX-HEAP, chạy trong thời gian tuyến tính, tạo đống max từ một mảng đầu vào không có thứ tự.
- Thủ tục HEAPSORT, chạy O(n lg n), sắp xếp một mảng tại chỗ.
- Các thủ tục MAX-HEAP-INSERT, HEAP-EXTRACT-MAX, HEAP-INCREASE-KEY và HEAP-MAXIMUM, chạy O(lg n), cho phép cấu trúc đống cài đặt một hàng đợi ưu tiên.

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: cách lưu cây gần đầy đủ trong mảng bằng công thức chỉ số là kỹ thuật dùng khắp nơi — `heapq` của Python và `std::priority_queue` của C++ lưu đống trong mảng/vector với đúng các công thức này (Python đánh chỉ số từ 0 nên con của i là 2i + 1 và 2i + 2, cha là ⌊(i − 1)/2⌋). Cây phân đoạn (segment tree) trong lập trình thi đấu cũng lưu theo cách này.

### 4. Duy trì tính chất đống (6.2 Maintaining the heap property, trang 154–156)

Để duy trì tính chất đống max, ta gọi thủ tục **MAX-HEAPIFY**. Đầu vào là mảng A và một chỉ số i của mảng. Khi được gọi, MAX-HEAPIFY giả định rằng các cây nhị phân có gốc tại LEFT(i) và RIGHT(i) là đống max, nhưng A[i] có thể nhỏ hơn các con của nó, vi phạm tính chất đống max. MAX-HEAPIFY cho giá trị ở A[i] "chìm xuống" (float down) trong đống max để cây con có gốc tại chỉ số i tuân theo tính chất đống max.

```text
MAX-HEAPIFY(A, i)
 1  l = LEFT(i)
 2  r = RIGHT(i)
 3  if l ≤ A.heap-size and A[l] > A[i]
 4      largest = l
 5  else largest = i
 6  if r ≤ A.heap-size and A[r] > A[largest]
 7      largest = r
 8  if largest ≠ i
 9      exchange A[i] with A[largest]
10      MAX-HEAPIFY(A, largest)
```

Giải thích từng dòng:
- Dòng 1–2: tính chỉ số hai con.
- Dòng 3–5: nếu con trái tồn tại trong đống (l ≤ A.heap-size) và lớn hơn A[i], tạm coi con trái là lớn nhất; ngược lại là chính i.
- Dòng 6–7: nếu con phải tồn tại và lớn hơn phần tử lớn nhất hiện tại, con phải là lớn nhất. Sau dòng 7, *largest* là chỉ số của phần tử lớn nhất trong ba phần tử A[i], A[LEFT(i)], A[RIGHT(i)].
- Dòng 8: nếu A[i] đã lớn nhất, cây con gốc i đã là đống max, thủ tục kết thúc.
- Dòng 9: ngược lại, một trong hai con có phần tử lớn nhất; đổi A[i] với A[largest]. Sau phép đổi, nút i và các con của nó thoả tính chất đống max.
- Dòng 10: nút có chỉ số *largest* bây giờ chứa giá trị ban đầu A[i], nên cây con gốc *largest* có thể vi phạm tính chất đống max. Vì vậy gọi đệ quy MAX-HEAPIFY trên cây con đó.

Chú ý dòng 3 và 6 kiểm tra chỉ số con với A.heap-size chứ không phải A.length: một ô nằm ngoài vùng đống (ví dụ vùng đã sắp xếp của heapsort) không được coi là con.

#### Ví dụ chạy tay MAX-HEAPIFY(A, 2) (Hình 6.2 của sách)

A.heap-size = 10, A = [16, 4, 10, 14, 7, 9, 3, 2, 8, 1].

(a) Cấu hình ban đầu; nút i = 2 (giá trị 4) vi phạm tính chất đống max vì nó không lớn hơn cả hai con (14 và 7):

```text
                     16 (1)
              ┌────────┴────────┐
        i →  4 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
      14 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  8 (9)  1 (10)
```

Dòng 1–7: l = 4, r = 5; A[4] = 14 > 4 nên largest = 4; A[5] = 7 không lớn hơn 14 nên largest giữ 4.

(b) Đổi A[2] với A[4]: tính chất đống max được khôi phục cho nút 2, nhưng bị phá ở nút 4. Lời gọi đệ quy MAX-HEAPIFY(A, 4) có i = 4:

```text
                     16 (1)
              ┌────────┴────────┐
           14 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
  i →  4 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  8 (9)  1 (10)
```

l = 8, r = 9; A[8] = 2 không lớn hơn 4 nên largest = 4; A[9] = 8 > 4 nên largest = 9.

(c) Đổi A[4] với A[9]: nút 4 được sửa xong; lời gọi đệ quy MAX-HEAPIFY(A, 9) không thay đổi gì thêm (l = 18 và r = 19 đều lớn hơn heap-size = 10, nên largest = 9 = i):

```text
                     16 (1)
              ┌────────┴────────┐
           14 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
       8 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  4 (9) ← i   1 (10)
```

Kết quả: A = [16, 14, 10, 8, 7, 9, 3, 2, 4, 1] — chính là đống max ở Mục 6.1. Tổng cộng 2 lần đổi chỗ, 3 lần gọi thủ tục.

#### Thời gian chạy

Thời gian chạy của MAX-HEAPIFY trên cây con kích thước n có gốc tại nút i là thời gian Θ(1) để sửa quan hệ giữa A[i], A[LEFT(i)] và A[RIGHT(i)], cộng thời gian chạy MAX-HEAPIFY trên cây con có gốc tại một con của i (giả sử lời gọi đệ quy xảy ra). Cây con của mỗi con có kích thước tối đa 2n/3 — trường hợp xấu nhất xảy ra khi tầng đáy của cây đầy đúng một nửa — nên thời gian của MAX-HEAPIFY được mô tả bởi truy hồi

```text
T(n) ≤ T(2n/3) + Θ(1)
```

Theo trường hợp 2 của định lý thợ (Định lý 4.1), nghiệm là T(n) = O(lg n). (Chi tiết: a = 1, b = 3/2, n^(log_b a) = n⁰ = 1, f(n) = Θ(1) = Θ(n^(log_b a)), nên T(n) = Θ(n^(log_b a) lg n) = Θ(lg n), và vì truy hồi là bất đẳng thức "≤" nên kết luận là O(lg n).) Cách khác: có thể mô tả thời gian của MAX-HEAPIFY trên một nút chiều cao h là O(h), vì mỗi lời gọi đệ quy đi xuống một tầng.

**Kiểm tra cận 2n/3 (người tổng hợp):** xét cây có gốc, cây con trái là cây đầy đủ cao h − 1 (2^h − 1 nút), cây con phải là cây đầy đủ cao h − 2 (2^(h−1) − 1 nút) — đây là cây có tầng đáy đầy đúng một nửa. Tổng n = 1 + (2^h − 1) + (2^(h−1) − 1) = 3 · 2^(h−1) − 1. Cây con trái có 2^h − 1 = (2(n + 1)/3) − 1 = (2n − 1)/3 nút, nhỏ hơn 2n/3. Ví dụ h = 3: n = 11, cây con trái có 7 nút, 7/11 ≈ 0,636 < 0,667. Tỷ lệ này tiến tới 2/3 khi n lớn, nên 2/3 là hằng số đúng.

#### Ví dụ hôm nay

Thao tác "chìm xuống" (thường gọi là sift-down) chính là hàm `heapq.heapify` gọi lặp lại trong Python và `std::pop_heap` của C++ dùng sau khi đưa phần tử cuối lên gốc — theo hiểu biết của người tổng hợp.

### 5. Dựng đống (6.3 Building a heap, trang 156–159)

Ta có thể dùng MAX-HEAPIFY theo kiểu từ dưới lên để biến mảng A[1..n], với n = A.length, thành một đống max. Theo Exercise 6.1-7, các phần tử trong mảng con A[(⌊n/2⌋ + 1)..n] đều là lá của cây, nên mỗi phần tử là một đống một phần tử ngay từ đầu. Thủ tục BUILD-MAX-HEAP đi qua các nút còn lại của cây và chạy MAX-HEAPIFY trên từng nút.

```text
BUILD-MAX-HEAP(A)
1  A.heap-size = A.length
2  for i = ⌊A.length/2⌋ downto 1
3      MAX-HEAPIFY(A, i)
```

Dòng 1: toàn bộ mảng thuộc đống. Dòng 2–3: duyệt các nút không phải lá, từ nút có chỉ số lớn nhất (gần đáy nhất) lùi về gốc.

#### Tính đúng: bất biến vòng lặp

Để chứng minh BUILD-MAX-HEAP đúng, ta dùng bất biến vòng lặp sau:

> Đầu mỗi lần lặp của vòng **for** ở dòng 2–3, mỗi nút i + 1, i + 2, …, n là gốc của một đống max.

Cần chứng minh bất biến đúng trước lần lặp đầu, mỗi lần lặp duy trì bất biến, và bất biến cho một tính chất hữu ích để chứng minh tính đúng khi vòng lặp kết thúc.

- **Khởi tạo:** trước lần lặp đầu, i = ⌊n/2⌋. Mỗi nút ⌊n/2⌋ + 1, ⌊n/2⌋ + 2, …, n là một lá, nên là gốc của một đống max tầm thường.
- **Duy trì:** các con của nút i có chỉ số lớn hơn i (vì 2i > i và 2i + 1 > i). Theo bất biến, chúng đều là gốc của đống max. Đây chính xác là điều kiện cần cho lời gọi MAX-HEAPIFY(A, i) để biến nút i thành gốc một đống max. Hơn nữa, lời gọi MAX-HEAPIFY giữ nguyên tính chất các nút i + 1, i + 2, …, n đều là gốc của đống max (nó chỉ đổi chỗ trong cây con gốc i, và mỗi lần đổi giữ tính chất đống của các cây con nó đi qua). Giảm i trong phần cập nhật của vòng for thiết lập lại bất biến cho lần lặp kế tiếp.
- **Kết thúc:** khi kết thúc, i = 0. Theo bất biến, mỗi nút 1, 2, …, n là gốc của một đống max. Đặc biệt, nút 1 là gốc đống max, tức cả mảng là đống max.

#### Ví dụ chạy tay BUILD-MAX-HEAP (Hình 6.3 của sách)

Mảng đầu vào 10 phần tử: A = [4, 1, 3, 2, 16, 9, 10, 14, 8, 7]. ⌊10/2⌋ = 5, nên i chạy 5, 4, 3, 2, 1. Mỗi dòng dưới đây là cấu trúc dữ liệu *trước* lời gọi MAX-HEAPIFY ở dòng 3 (đúng như các khung (a)–(e) của hình), rồi kết quả lời gọi.

(a) Mảng đầu vào và cây nó biểu diễn; chỉ số vòng lặp i trỏ tới nút 5 trước lời gọi MAX-HEAPIFY(A, i):

```text
                      4 (1)
              ┌────────┴────────┐
            1 (2)              3 (3)
         ┌───┴───┐          ┌───┴───┐
       2 (4)  16 (5) ← i  9 (6)  10 (7)
      ┌──┴──┐    │
  14 (8)  8 (9)  7 (10)
```

i = 5: A[5] = 16, con duy nhất A[10] = 7 nhỏ hơn: không đổi.

(b) Kết quả giống (a); chỉ số i của lần lặp kế tiếp trỏ tới nút 4. i = 4: A[4] = 2, con A[8] = 14, A[9] = 8 nên đổi 2 với 14; nút 8 là lá, dừng.
Mảng: [4, 1, 3, 14, 16, 9, 10, 2, 8, 7].

(c) i = 3: A[3] = 3, con A[6] = 9, A[7] = 10 nên đổi 3 với 10; nút 7 là lá, dừng.
Mảng: [4, 1, 10, 14, 16, 9, 3, 2, 8, 7].

(d) i = 2: A[2] = 1, con A[4] = 14, A[5] = 16 nên đổi 1 với 16; đệ quy ở nút 5: con A[10] = 7 > 1 nên đổi chỗ; nút 10 là lá, dừng.
Mảng: [4, 16, 10, 14, 7, 9, 3, 2, 8, 1].

```text
   Trạng thái (e), trước lời gọi với i = 1:
                      4 (1) ← i
              ┌────────┴────────┐
           16 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
      14 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  8 (9)  1 (10)
```

(e) i = 1: A[1] = 4, con 16 và 10 nên đổi 4 với 16; ở nút 2: con 14 và 7 nên đổi 4 với 14; ở nút 4: con 2 và 8 nên đổi 4 với 8; nút 9 là lá, dừng.

(f) Đống max sau khi BUILD-MAX-HEAP kết thúc:

```text
                     16 (1)
              ┌────────┴────────┐
           14 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
       8 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  4 (9)  1 (10)
```

A = [16, 14, 10, 8, 7, 9, 3, 2, 4, 1]. Tổng số lần đổi chỗ: 0 + 1 + 1 + 2 + 3 = 7. Chú thích của sách nhấn mạnh: mỗi khi MAX-HEAPIFY được gọi trên một nút, hai cây con của nút đó đều đã là đống max — đúng như bất biến.

#### Thời gian chạy: cận thô

Mỗi lời gọi MAX-HEAPIFY tốn O(lg n), và BUILD-MAX-HEAP gọi O(n) lần. Vậy thời gian chạy là O(n lg n). Cận trên này đúng nhưng không chặt tiệm cận.

#### Thời gian chạy: cận chặt O(n)

Ta có cận chặt hơn khi nhận xét rằng thời gian chạy MAX-HEAPIFY tại một nút thay đổi theo chiều cao của nút, và đa số nút có chiều cao nhỏ. Phân tích chặt dựa vào hai tính chất: đống n phần tử có chiều cao ⌊lg n⌋ (Exercise 6.1-2) và có nhiều nhất ⌈n/2^(h+1)⌉ nút ở chiều cao h bất kỳ (Exercise 6.3-3).

Thời gian MAX-HEAPIFY trên nút chiều cao h là O(h), nên tổng chi phí của BUILD-MAX-HEAP bị chặn trên bởi

```text
 ⌊lg n⌋                         ⌊lg n⌋
   Σ    ⌈ n / 2^(h+1) ⌉ · O(h) = O( n ·  Σ   h / 2^h )
  h=0                            h=0
```

Ta tính tổng cuối bằng cách thay x = 1/2 vào công thức (A.8) (Σ_{k=0}^{∞} k xᵏ = x/(1 − x)² với |x| < 1), được

```text
  ∞
  Σ   h / 2^h  =  (1/2) / (1 − 1/2)²  =  2
 h=0
```

Do đó thời gian của BUILD-MAX-HEAP bị chặn bởi

```text
     ⌊lg n⌋                  ∞
O( n ·  Σ   h/2^h )  =  O( n · Σ  h/2^h )  =  O(n)
       h=0                  h=0
```

Vậy ta dựng được đống max từ một mảng không có thứ tự trong thời gian tuyến tính.

**Kiểm tra số (người tổng hợp), n = 10:** số nút theo chiều cao (bảng ở Mục 6.1) là 5, 3, 1, 1 cho h = 0, 1, 2, 3; cận ⌈10/2^(h+1)⌉ cho 5, 3, 2, 1 — đều thoả. Tổng Σ (số nút) · h = 0 + 3 + 2 + 3 = 8 ≤ 2n = 20. Ví dụ ở trên thực sự tốn 7 lần đổi chỗ. Với n = 2²⁰ − 1 ≈ 10⁶ (cây đầy đủ), tổng chiều cao các nút là n − lg(n + 1) = 1.048.575 − 20 ≈ 1.048.555 < n — mỗi nút trung bình chưa tới một lần đổi chỗ, trong khi cận thô cho tới 20 lần mỗi nút.

Trực giác: một nửa số nút là lá (không tốn gì), một phần tư có chiều cao 1 (tối đa 1 lần đổi), một phần tám có chiều cao 2 (tối đa 2 lần đổi), …; các nút "đắt" (gần gốc) rất ít.

#### BUILD-MIN-HEAP

Ta dựng đống min bằng thủ tục BUILD-MIN-HEAP, giống BUILD-MAX-HEAP nhưng thay lời gọi MAX-HEAPIFY ở dòng 3 bằng MIN-HEAPIFY (Exercise 6.2-2). BUILD-MIN-HEAP tạo đống min từ một mảng tuyến tính không có thứ tự trong thời gian tuyến tính.

#### Ví dụ hôm nay

`heapq.heapify(list)` của Python và `std::make_heap` của C++ đều dựng đống trong thời gian tuyến tính theo đúng cách từ dưới lên này (cách của Floyd) — theo hiểu biết của người tổng hợp. Đây là lý do khi đã có sẵn n phần tử, nên gọi heapify một lần thay vì chèn từng phần tử (Problem 6-1 cho thấy chèn từng phần tử tốn Θ(n lg n) trong trường hợp xấu nhất).

### 6. Thuật toán heapsort (6.4 The heapsort algorithm, trang 159–162)

Thuật toán heapsort bắt đầu bằng BUILD-MAX-HEAP để dựng đống max trên mảng đầu vào A[1..n], với n = A.length. Vì phần tử lớn nhất của mảng nằm ở gốc A[1], ta đặt nó vào đúng vị trí cuối cùng bằng cách đổi nó với A[n]. Nếu bây giờ ta loại nút n khỏi đống — làm được bằng cách đơn giản giảm A.heap-size — ta thấy các con của gốc vẫn là đống max, nhưng phần tử gốc mới có thể vi phạm tính chất đống max. Tất cả những gì cần làm để khôi phục tính chất đống max là gọi MAX-HEAPIFY(A, 1), để lại một đống max trong A[1..n − 1]. Thuật toán heapsort lặp lại quá trình này cho đống max kích thước n − 1, cho tới đống kích thước 2. (Exercise 6.4-2 cho bất biến vòng lặp chính xác.)

```text
HEAPSORT(A)
1  BUILD-MAX-HEAP(A)
2  for i = A.length downto 2
3      exchange A[1] with A[i]
4      A.heap-size = A.heap-size − 1
5      MAX-HEAPIFY(A, 1)
```

Dòng 1: dựng đống max. Dòng 2: i là vị trí cuối của vùng đống hiện tại. Dòng 3: đưa phần tử lớn nhất của đống về ô i — vị trí cuối cùng của nó trong mảng đã sắp. Dòng 4: thu nhỏ đống để ô i không còn thuộc đống (MAX-HEAPIFY sẽ không đụng tới nó nhờ kiểm tra với A.heap-size). Dòng 5: phần tử vừa được đổi lên gốc chìm xuống đúng chỗ. Vòng lặp dừng ở i = 2 vì khi đống còn một phần tử, phần tử đó (nhỏ nhất) đã ở đúng ô 1.

#### Ví dụ chạy tay HEAPSORT (Hình 6.4 của sách)

Bắt đầu từ đống max vừa được BUILD-MAX-HEAP dựng ở dòng 1. Mỗi dòng của bảng là trạng thái ngay sau lời gọi MAX-HEAPIFY ở dòng 5, cùng giá trị i lúc đó. Dấu │ ngăn vùng đống (bên trái) và vùng đã sắp xếp (bên phải; trong hình gốc, các nút vùng này được tô đậm, chỉ các nút tô nhạt còn thuộc đống).

| Khung | i | Diễn biến trong lần lặp | Mảng sau MAX-HEAPIFY |
|---|---|---|---|
| (a) | — | đống ban đầu | 16 14 10 8 7 9 3 2 4 1 │ |
| (b) | 10 | đổi 16 ↔ 1; 1 chìm: ↔14, ↔8, ↔4 | 14 8 10 4 7 9 3 2 1 │ 16 |
| (c) | 9 | đổi 14 ↔ 1; 1 chìm: ↔10, ↔9 | 10 8 9 4 7 1 3 2 │ 14 16 |
| (d) | 8 | đổi 10 ↔ 2; 2 chìm: ↔9, ↔3 | 9 8 3 4 7 1 2 │ 10 14 16 |
| (e) | 7 | đổi 9 ↔ 2; 2 chìm: ↔8, ↔7 | 8 7 3 4 2 1 │ 9 10 14 16 |
| (f) | 6 | đổi 8 ↔ 1; 1 chìm: ↔7, ↔4 | 7 4 3 1 2 │ 8 9 10 14 16 |
| (g) | 5 | đổi 7 ↔ 2; 2 chìm: ↔4 (con còn lại 1 nhỏ hơn) | 4 2 3 1 │ 7 8 9 10 14 16 |
| (h) | 4 | đổi 4 ↔ 1; 1 chìm: ↔3 | 3 2 1 │ 4 7 8 9 10 14 16 |
| (i) | 3 | đổi 3 ↔ 1; 1 chìm: ↔2 | 2 1 │ 3 4 7 8 9 10 14 16 |
| (j) | 2 | đổi 2 ↔ 1; đống một phần tử | 1 │ 2 3 4 7 8 9 10 14 16 |
| (k) | — | mảng kết quả | 1 2 3 4 7 8 9 10 14 16 |

Vẽ lại hai khung đầu dưới dạng cây để thấy cơ chế (nút trong ngoặc vuông đã rời khỏi đống):

```text
(a) đống ban đầu                        (b) sau lần lặp i = 10
            16                                      14
        ┌───┴───┐                               ┌───┴───┐
       14       10                              8       10
     ┌─┴─┐    ┌─┴─┐                           ┌─┴─┐    ┌─┴─┐
     8   7    9   3                           4   7    9   3
    ┌┴┐  │                                   ┌┴┐  │
    2 4  1                                   2 1 [16]
```

Ở (b): 16 được đổi xuống ô 10 và rời đống; 1 lên gốc rồi chìm qua nút 2 (đổi với 14), nút 4 (đổi với 8), nút 9 (đổi với 4).

Kiểm tra từng bước (người tổng hợp đã chạy lại toàn bộ): mọi trạng thái (b)–(j) khớp với Hình 6.4.

#### Thời gian chạy

Thủ tục HEAPSORT tốn O(n lg n), vì lời gọi BUILD-MAX-HEAP tốn O(n) và mỗi lần trong n − 1 lần gọi MAX-HEAPIFY tốn O(lg n).

Nhận xét của người tổng hợp: khác BUILD-MAX-HEAP, ở đây không có "phép màu tuyến tính", vì MAX-HEAPIFY luôn được gọi ở gốc — nút cao nhất — và phần tử vừa được đưa lên gốc là phần tử lấy từ đáy đống, thường nhỏ, nên thường chìm gần hết chiều cao. Exercise 6.4-5 cho thấy kể cả trường hợp tốt nhất (phần tử khác nhau) cũng tốn Ω(n lg n).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: heapsort hiếm khi là thuật toán sắp xếp chính trong thư viện chuẩn vì truy cập bộ nhớ nhảy cóc (từ i tới 2i) làm hỏng bộ nhớ đệm, nhưng nó là "lưới an toàn" của introsort trong `std::sort` của C++: khi quicksort đệ quy quá sâu, thuật toán chuyển sang heapsort để bảo đảm O(n lg n). Nhân Linux cũng dùng heapsort cho hàm `sort()` nội bộ vì không cần bộ nhớ phụ và có cận xấu nhất chắc chắn.

### 7. Hàng đợi ưu tiên (6.5 Priority queues, trang 162–166)

Heapsort là thuật toán xuất sắc, nhưng một cài đặt quicksort tốt (Chương 7) thường thắng nó trong thực tế. Dù vậy, bản thân cấu trúc đống có nhiều ứng dụng. Mục này trình bày một trong những ứng dụng phổ biến nhất của đống: làm **hàng đợi ưu tiên** hiệu quả. Giống đống, hàng đợi ưu tiên có hai dạng: hàng đợi ưu tiên max và hàng đợi ưu tiên min. Mục này tập trung vào cài đặt hàng đợi ưu tiên max, dựa trên đống max; Exercise 6.5-3 yêu cầu viết các thủ tục cho hàng đợi ưu tiên min.

**Hàng đợi ưu tiên** (priority queue) là cấu trúc dữ liệu duy trì một tập S các phần tử, mỗi phần tử gắn với một giá trị gọi là **khoá** (key). **Hàng đợi ưu tiên max** (max-priority queue) hỗ trợ các phép toán:

- **INSERT(S, x)** chèn phần tử x vào tập S, tương đương phép toán S = S ∪ {x}.
- **MAXIMUM(S)** trả về phần tử của S có khoá lớn nhất.
- **EXTRACT-MAX(S)** loại bỏ và trả về phần tử của S có khoá lớn nhất.
- **INCREASE-KEY(S, x, k)** tăng giá trị khoá của phần tử x lên giá trị mới k, được giả định là ít nhất bằng khoá hiện tại của x.

Trong các ứng dụng, có thể dùng hàng đợi ưu tiên max để lập lịch công việc trên một máy tính dùng chung. Hàng đợi ưu tiên max theo dõi các công việc cần thực hiện và độ ưu tiên tương đối của chúng. Khi một công việc xong hoặc bị ngắt, bộ lập lịch chọn công việc ưu tiên cao nhất trong số công việc đang chờ bằng cách gọi EXTRACT-MAX. Bộ lập lịch có thể thêm công việc mới vào hàng đợi bất cứ lúc nào bằng cách gọi INSERT.

Ngược lại, **hàng đợi ưu tiên min** (min-priority queue) hỗ trợ các phép toán INSERT, MINIMUM, EXTRACT-MIN và DECREASE-KEY. Có thể dùng hàng đợi ưu tiên min trong một bộ mô phỏng hướng sự kiện (event-driven simulator). Các phần tử trong hàng đợi là các sự kiện cần mô phỏng, mỗi sự kiện gắn với thời điểm xảy ra làm khoá. Các sự kiện phải được mô phỏng theo thứ tự thời điểm xảy ra, vì việc mô phỏng một sự kiện có thể sinh ra các sự kiện khác cần mô phỏng trong tương lai. Chương trình mô phỏng gọi EXTRACT-MIN ở mỗi bước để chọn sự kiện kế tiếp cần mô phỏng. Khi có sự kiện mới được sinh ra, bộ mô phỏng chèn chúng vào hàng đợi ưu tiên min bằng INSERT. Sách sẽ gặp các ứng dụng khác của hàng đợi ưu tiên min, nhấn mạnh phép toán DECREASE-KEY, ở Chương 23 và 24.

Ví dụ của người tổng hợp về mô phỏng: hàng đợi có sự kiện "khách A đến lúc 3", "khách B đến lúc 7". EXTRACT-MIN lấy sự kiện lúc 3; mô phỏng nó sinh ra sự kiện "khách A rời quầy lúc 5", được INSERT; EXTRACT-MIN kế tiếp lấy sự kiện lúc 5 chứ không phải lúc 7 — đúng thứ tự thời gian dù sự kiện lúc 5 được tạo ra sau.

#### Tay cầm (handle)

Không có gì ngạc nhiên khi dùng đống để cài hàng đợi ưu tiên. Trong một ứng dụng cụ thể, như lập lịch công việc hay mô phỏng hướng sự kiện, các phần tử của hàng đợi ưu tiên ứng với các đối tượng trong ứng dụng. Ta thường cần xác định đối tượng ứng dụng nào ứng với một phần tử hàng đợi cho trước, và ngược lại. Vì vậy, khi dùng đống để cài hàng đợi ưu tiên, ta thường cần lưu trong mỗi phần tử đống một **tay cầm** (handle) tới đối tượng ứng dụng tương ứng. Thành phần cụ thể của tay cầm (con trỏ hay số nguyên chẳng hạn) tuỳ ứng dụng. Tương tự, ta cần lưu trong mỗi đối tượng ứng dụng một tay cầm tới phần tử đống tương ứng; ở đây tay cầm thường là một chỉ số mảng. Vì các phần tử đống đổi vị trí trong mảng khi thực hiện các phép toán trên đống, một cài đặt thực tế, khi di chuyển một phần tử đống, cũng phải cập nhật chỉ số mảng trong đối tượng ứng dụng tương ứng. Vì chi tiết truy cập đối tượng ứng dụng phụ thuộc nhiều vào ứng dụng và cách cài đặt, sách không đi sâu, chỉ lưu ý rằng trong thực tế các tay cầm này phải được duy trì đúng.

#### HEAP-MAXIMUM

Thủ tục HEAP-MAXIMUM cài đặt phép toán MAXIMUM trong thời gian Θ(1):

```text
HEAP-MAXIMUM(A)
1  return A[1]
```

#### HEAP-EXTRACT-MAX

Thủ tục HEAP-EXTRACT-MAX cài đặt phép toán EXTRACT-MAX. Nó tương tự thân vòng for (dòng 3–5) của HEAPSORT.

```text
HEAP-EXTRACT-MAX(A)
1  if A.heap-size < 1
2      error "heap underflow"
3  max = A[1]
4  A[1] = A[A.heap-size]
5  A.heap-size = A.heap-size − 1
6  MAX-HEAPIFY(A, 1)
7  return max
```

Dòng 1–2: đống rỗng thì báo lỗi "tràn dưới" (underflow). Dòng 3: lưu phần tử lớn nhất. Dòng 4: đưa phần tử cuối của đống lên gốc (khác HEAPSORT ở chỗ chỉ chép, không đổi chỗ, vì không cần giữ giá trị cũ ở cuối). Dòng 5: thu nhỏ đống. Dòng 6: cho phần tử ở gốc chìm xuống. Dòng 7: trả về giá trị lớn nhất.

Thời gian chạy của HEAP-EXTRACT-MAX là O(lg n), vì nó chỉ làm thêm một lượng việc hằng số ngoài thời gian O(lg n) của MAX-HEAPIFY.

#### HEAP-INCREASE-KEY

Thủ tục HEAP-INCREASE-KEY cài đặt phép toán INCREASE-KEY. Một chỉ số i của mảng xác định phần tử hàng đợi có khoá cần tăng. Thủ tục trước hết cập nhật khoá của A[i] thành giá trị mới. Vì tăng khoá của A[i] có thể vi phạm tính chất đống max, thủ tục sau đó — theo cách gợi nhớ vòng lặp chèn (dòng 5–7) của INSERTION-SORT ở Mục 2.1 — đi theo một đường đơn từ nút này về phía gốc để tìm chỗ thích hợp cho khoá vừa tăng. Trên đường đi, nó lặp lại việc so sánh một phần tử với cha, đổi khoá của chúng và tiếp tục nếu khoá của phần tử lớn hơn, và dừng nếu khoá của phần tử không lớn hơn khoá cha (sách viết "nhỏ hơn"), vì lúc đó tính chất đống max đã được thoả. (Exercise 6.5-5 cho bất biến vòng lặp chính xác.)

```text
HEAP-INCREASE-KEY(A, i, key)
1  if key < A[i]
2      error "new key is smaller than current key"
3  A[i] = key
4  while i > 1 and A[PARENT(i)] < A[i]
5      exchange A[i] with A[PARENT(i)]
6      i = PARENT(i)
```

Dòng 1–2: khoá mới không được nhỏ hơn khoá cũ. Dòng 3: gán khoá mới. Dòng 4: chừng nào chưa tới gốc và cha nhỏ hơn: Dòng 5 đổi với cha, Dòng 6 đi lên cha.

Thời gian chạy của HEAP-INCREASE-KEY trên đống n phần tử là O(lg n), vì đường đi từ nút được cập nhật ở dòng 3 tới gốc có độ dài O(lg n).

#### Ví dụ chạy tay HEAP-INCREASE-KEY (Hình 6.5 của sách)

(a) Đống max [16, 14, 10, 8, 7, 9, 3, 2, 4, 1] (đống ban đầu của ví dụ heapsort), nút có chỉ số i = 9 (giá trị 4) được tô đậm.

(b) Khoá của nút này được tăng lên 15: A = [16, 14, 10, 8, 7, 9, 3, 2, 15, 1].

```text
                     16 (1)
              ┌────────┴────────┐
           14 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
       8 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8) 15 (9) ← i  1 (10)
```

(c) Sau một lần lặp của vòng while dòng 4–6: cha PARENT(9) = 4 có 8 < 15, nên nút và cha đổi khoá, chỉ số i đi lên cha, i = 4: A = [16, 14, 10, 15, 7, 9, 3, 2, 8, 1].

(d) Sau thêm một lần lặp: cha PARENT(4) = 2 có 14 < 15, đổi, i = 2: A = [16, 15, 10, 14, 7, 9, 3, 2, 8, 1]. Lúc này A[PARENT(2)] = A[1] = 16 ≥ 15 = A[2]. Tính chất đống max đã thoả và thủ tục kết thúc.

```text
                     16 (1)
              ┌────────┴────────┐
    i →    15 (2)             10 (3)
         ┌───┴───┐          ┌───┴───┐
      14 (4)   7 (5)      9 (6)   3 (7)
      ┌──┴──┐    │
   2 (8)  8 (9)  1 (10)
```

#### MAX-HEAP-INSERT

Thủ tục MAX-HEAP-INSERT cài đặt phép toán INSERT. Đầu vào là khoá của phần tử mới cần chèn vào đống max A. Thủ tục trước hết mở rộng đống max bằng cách thêm vào cây một lá mới có khoá −∞. Sau đó nó gọi HEAP-INCREASE-KEY để đặt khoá của nút mới thành giá trị đúng và duy trì tính chất đống max.

```text
MAX-HEAP-INSERT(A, key)
1  A.heap-size = A.heap-size + 1
2  A[A.heap-size] = −∞
3  HEAP-INCREASE-KEY(A, A.heap-size, key)
```

Dòng 1: thêm một ô vào đống (giả định mảng còn chỗ — sách không kiểm tra). Dòng 2: lá mới có khoá −∞, nên không vi phạm tính chất đống max (mọi cha đều ≥ −∞) và mọi khoá thật đều ≥ −∞ (nên dòng 1 của HEAP-INCREASE-KEY không báo lỗi). Dòng 3: tăng khoá lên giá trị thật và cho nó nổi lên.

Thời gian chạy của MAX-HEAP-INSERT trên đống n phần tử là O(lg n).

Tóm lại, đống hỗ trợ mọi phép toán hàng đợi ưu tiên trên tập kích thước n trong thời gian O(lg n).

| Phép toán | Thủ tục | Thời gian |
|---|---|---|
| MAXIMUM | HEAP-MAXIMUM | Θ(1) |
| EXTRACT-MAX | HEAP-EXTRACT-MAX | O(lg n) |
| INCREASE-KEY | HEAP-INCREASE-KEY | O(lg n) |
| INSERT | MAX-HEAP-INSERT | O(lg n) |

So sánh của người tổng hợp với hai cách cài đơn giản: mảng không sắp xếp cho INSERT O(1) nhưng MAXIMUM và EXTRACT-MAX Θ(n); mảng đã sắp xếp cho MAXIMUM và EXTRACT-MAX O(1) nhưng INSERT Θ(n). Với chuỗi n lần INSERT rồi n lần EXTRACT-MAX, cả hai cách đơn giản đều tốn Θ(n²), đống tốn O(n lg n).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: hàng đợi ưu tiên bằng đống là xương sống của bộ lập lịch tác vụ (hàng đợi bộ hẹn giờ trong nhiều vòng lặp sự kiện như libuv của Node.js, `java.util.PriorityQueue`, `DelayQueue`), thuật toán Dijkstra và A* trong định tuyến bản đồ, trộn k luồng dữ liệu đã sắp xếp (Exercise 6.5-9, dùng trong sắp xếp ngoài và trong cơ sở dữ liệu kiểu LSM-tree), và bài toán "top-k" (giữ đống min k phần tử để lấy k phần tử lớn nhất từ một luồng dữ liệu). Vấn đề "tay cầm" là lý do `heapq` của Python không có DECREASE-KEY: tài liệu của nó khuyên đánh dấu phần tử cũ là đã huỷ và chèn bản mới.

## Bài tập và bài toán cuối chương

### Bài tập Mục 6.1 (trang 153–154)

- **6.1-1:** Số phần tử tối thiểu và tối đa của một đống có chiều cao h là bao nhiêu? *Người tổng hợp:* tầng 0..h − 1 đầy (2^h − 1 nút), tầng h có từ 1 tới 2^h nút. Tối thiểu 2^h, tối đa 2^(h+1) − 1. Ví dụ h = 3: từ 8 tới 15 phần tử.
- **6.1-2:** Chứng minh đống n phần tử có chiều cao ⌊lg n⌋. *Người tổng hợp:* theo 6.1-1, 2^h ≤ n ≤ 2^(h+1) − 1 < 2^(h+1); lấy lg: h ≤ lg n < h + 1, nên h = ⌊lg n⌋. Ví dụ n = 10: ⌊lg 10⌋ = ⌊3,32⌋ = 3.
- **6.1-3:** Chứng minh trong mọi cây con của một đống max, gốc của cây con chứa giá trị lớn nhất xuất hiện trong cây con đó. *Người tổng hợp:* với mọi nút x trong cây con gốc r, đi theo đường từ x lên r: x ≤ cha(x) ≤ cha(cha(x)) ≤ … ≤ r theo tính chất đống max và tính bắc cầu của ≤ (hoặc quy nạp theo chiều cao).
- **6.1-4:** Trong đống max với các phần tử khác nhau, phần tử nhỏ nhất có thể nằm ở đâu? *Người tổng hợp:* ở một lá, tức một chỉ số trong ⌊n/2⌋ + 1..n. Nút trong có ít nhất một con, mà con nhỏ hơn hẳn cha (vì khác nhau), nên nút trong không thể nhỏ nhất. Mọi lá đều có thể (ví dụ đặt min ở bất kỳ lá nào cũng được đống hợp lệ).
- **6.1-5:** Một mảng đã sắp xếp (tăng dần) có phải đống min không? *Người tổng hợp:* có. Với mọi i ≥ 2, PARENT(i) = ⌊i/2⌋ < i nên A[PARENT(i)] ≤ A[i]. (Mảng sắp xếp giảm dần là đống max.)
- **6.1-6:** Mảng ⟨23, 17, 14, 6, 13, 10, 1, 5, 7, 12⟩ có phải đống max không? *Người tổng hợp:* không. Nút 4 có giá trị 6, con phải của nó là nút 9 có giá trị 7 > 6, vi phạm. (Các cặp khác đều thoả: 23 ≥ 17, 14; 17 ≥ 6, 13; 14 ≥ 10, 1; 6 ≥ 5; 13 ≥ 12.)
- **6.1-7:** Chứng minh rằng với cách lưu đống n phần tử trong mảng, các lá là các nút có chỉ số ⌊n/2⌋ + 1, ⌊n/2⌋ + 2, …, n. *Người tổng hợp:* nút i là lá khi và chỉ khi LEFT(i) = 2i > n. Với i = ⌊n/2⌋ + 1: 2i = 2⌊n/2⌋ + 2 ≥ n − 1 + 2 = n + 1 > n, nên là lá (và mọi i lớn hơn cũng vậy). Với i = ⌊n/2⌋: 2i = 2⌊n/2⌋ ≤ n, nên có con trái, không phải lá (và mọi i nhỏ hơn cũng vậy). Số lá là n − ⌊n/2⌋ = ⌈n/2⌉.

### Bài tập Mục 6.2 (trang 156)

- **6.2-1:** Theo mẫu của ví dụ MAX-HEAPIFY(A, 2), minh hoạ MAX-HEAPIFY(A, 3) trên A = ⟨27, 17, 3, 16, 13, 10, 1, 5, 7, 12, 4, 8, 9, 0⟩ (14 phần tử). *Lời giải của người tổng hợp:*
  - i = 3: A[3] = 3, con A[6] = 10, A[7] = 1, nên largest = 6, đổi: ⟨27, 17, 10, 16, 13, 3, 1, 5, 7, 12, 4, 8, 9, 0⟩.
  - i = 6: A[6] = 3, con A[12] = 8, A[13] = 9, nên largest = 13, đổi: ⟨27, 17, 10, 16, 13, 9, 1, 5, 7, 12, 4, 8, 3, 0⟩.
  - i = 13: LEFT(13) = 26 > 14, là lá, dừng.
- **6.2-2:** Viết pseudocode MIN-HEAPIFY(A, i) cho đống min, so sánh thời gian với MAX-HEAPIFY. *Người tổng hợp:*

  ```text
  MIN-HEAPIFY(A, i)
   1  l = LEFT(i)
   2  r = RIGHT(i)
   3  if l ≤ A.heap-size and A[l] < A[i]
   4      smallest = l
   5  else smallest = i
   6  if r ≤ A.heap-size and A[r] < A[smallest]
   7      smallest = r
   8  if smallest ≠ i
   9      exchange A[i] with A[smallest]
  10      MIN-HEAPIFY(A, smallest)
  ```
  Thời gian như nhau: O(lg n), hay O(h).
- **6.2-3:** Gọi MAX-HEAPIFY(A, i) khi A[i] lớn hơn các con thì sao? *Người tổng hợp:* largest = i ở dòng 8, thủ tục kết thúc ngay, không thay đổi gì; Θ(1).
- **6.2-4:** Gọi MAX-HEAPIFY(A, i) với i > A.heap-size/2 thì sao? *Người tổng hợp:* nút i là lá (theo 6.1-7), hai điều kiện ở dòng 3 và 6 đều sai, largest = i, không thay đổi gì.
- **6.2-5:** Mã MAX-HEAPIFY khá hiệu quả về hằng số, trừ có thể lời gọi đệ quy ở dòng 10, có thể khiến một số trình biên dịch sinh mã kém. Viết MAX-HEAPIFY hiệu quả dùng vòng lặp thay cho đệ quy. *Người tổng hợp:*

  ```text
  MAX-HEAPIFY-ITERATIVE(A, i)
   1  while TRUE
   2      l = LEFT(i)
   3      r = RIGHT(i)
   4      if l ≤ A.heap-size and A[l] > A[i]
   5          largest = l
   6      else largest = i
   7      if r ≤ A.heap-size and A[r] > A[largest]
   8          largest = r
   9      if largest == i
  10          return
  11      exchange A[i] with A[largest]
  12      i = largest
  ```
- **6.2-6:** Chứng minh thời gian xấu nhất của MAX-HEAPIFY trên đống kích thước n là Ω(lg n). (Gợi ý: cho giá trị các nút sao cho MAX-HEAPIFY được gọi đệ quy ở mọi nút trên một đường đơn từ gốc xuống một lá.) *Người tổng hợp:* đặt ở gốc giá trị nhỏ nhất, phần còn lại sao cho hai cây con là đống max. Khi đó giá trị gốc nhỏ hơn mọi giá trị khác nên luôn bị đổi xuống, cho tới khi tới một lá. Đường đi dài ít nhất ⌊lg n⌋ − 1 cạnh (độ sâu lá nông nhất), nên có Ω(lg n) lời gọi đệ quy. Ví dụ A = [1, 7, 6, 5, 4, 3, 2] (n = 7): 1 đổi với 7, rồi với 5, tới lá ở độ sâu 2 = ⌊lg 7⌋.

### Bài tập Mục 6.3 (trang 159)

- **6.3-1:** Theo mẫu ví dụ BUILD-MAX-HEAP, minh hoạ BUILD-MAX-HEAP trên A = ⟨5, 3, 17, 10, 84, 19, 6, 22, 9⟩ (n = 9, i chạy 4, 3, 2, 1). *Lời giải của người tổng hợp:*

  | i | Diễn biến | Mảng sau lời gọi |
  |---|---|---|
  | 4 | A[4] = 10, con 22 và 9 → đổi với 22 | 5 3 17 22 84 19 6 10 9 |
  | 3 | A[3] = 17, con 19 và 6 → đổi với 19 | 5 3 19 22 84 17 6 10 9 |
  | 2 | A[2] = 3, con 22 và 84 → đổi với 84; nút 5 là lá | 5 84 19 22 3 17 6 10 9 |
  | 1 | A[1] = 5, con 84 và 19 → đổi với 84; nút 2: con 22 và 3 → đổi với 22; nút 4: con 10 và 9 → đổi với 10 | 84 22 19 10 3 17 6 5 9 |

  Kết quả ⟨84, 22, 19, 10, 3, 17, 6, 5, 9⟩ là đống max (84 ≥ 22, 19; 22 ≥ 10, 3; 19 ≥ 17, 6; 10 ≥ 5, 9).
- **6.3-2:** Vì sao chỉ số i ở dòng 2 của BUILD-MAX-HEAP phải giảm từ ⌊A.length/2⌋ về 1 chứ không tăng từ 1 lên? *Người tổng hợp:* MAX-HEAPIFY(A, i) chỉ đúng khi hai cây con của i đã là đống max. Đi từ dưới lên bảo đảm điều đó; đi từ trên xuống thì không. Phản ví dụ ⟨1, 2, 3, 4, 5⟩ đi tăng: i = 1: 1 đổi với 3, được ⟨3, 2, 1, 4, 5⟩; i = 2: 2 đổi với 5, được ⟨3, 5, 1, 4, 2⟩ — gốc 3 < 5, không phải đống max. Đi giảm: i = 2, được ⟨1, 5, 3, 4, 2⟩; i = 1, được ⟨5, 1, 3, 4, 2⟩ rồi ⟨5, 4, 3, 1, 2⟩ — đúng.
- **6.3-3:** Chứng minh có nhiều nhất ⌈n/2^(h+1)⌉ nút có chiều cao h trong mọi đống n phần tử. *Người tổng hợp:* quy nạp theo h. h = 0: số lá là ⌈n/2⌉ (6.1-7). Bước quy nạp: bỏ hết lá, còn lại đống gồm ⌊n/2⌋ nút đầu; nút có chiều cao h trong đống cũ có chiều cao h − 1 trong đống mới. Theo giả thiết quy nạp, số nút đó ≤ ⌈⌊n/2⌋/2^h⌉ ≤ ⌈(n/2)/2^h⌉ = ⌈n/2^(h+1)⌉.

### Bài tập Mục 6.4 (trang 160–162)

- **6.4-1:** Theo mẫu ví dụ HEAPSORT, minh hoạ HEAPSORT trên A = ⟨5, 13, 2, 25, 7, 17, 20, 8, 4⟩. *Lời giải của người tổng hợp:* BUILD-MAX-HEAP (i = 4: không đổi; i = 3: 2 ↔ 20; i = 2: 13 ↔ 25; i = 1: 5 ↔ 25, 5 ↔ 13, 5 ↔ 8) cho đống ⟨25, 13, 20, 8, 7, 17, 2, 5, 4⟩. Sau đó:

  | i | Đổi | Mảng sau MAX-HEAPIFY (│ ngăn vùng đống và vùng đã sắp) |
  |---|---|---|
  | 9 | 25 ↔ 4 | 20 13 17 8 7 4 2 5 │ 25 |
  | 8 | 20 ↔ 5 | 17 13 5 8 7 4 2 │ 20 25 |
  | 7 | 17 ↔ 2 | 13 8 5 2 7 4 │ 17 20 25 |
  | 6 | 13 ↔ 4 | 8 7 5 2 4 │ 13 17 20 25 |
  | 5 | 8 ↔ 4 | 7 4 5 2 │ 8 13 17 20 25 |
  | 4 | 7 ↔ 2 | 5 4 2 │ 7 8 13 17 20 25 |
  | 3 | 5 ↔ 2 | 4 2 │ 5 7 8 13 17 20 25 |
  | 2 | 4 ↔ 2 | 2 │ 4 5 7 8 13 17 20 25 |

  Kết quả ⟨2, 4, 5, 7, 8, 13, 17, 20, 25⟩.
- **6.4-2:** Lập luận tính đúng của HEAPSORT bằng bất biến: "Đầu mỗi lần lặp của vòng for dòng 2–5, mảng con A[1..i] là một đống max chứa i phần tử nhỏ nhất của A[1..n], và mảng con A[i + 1..n] chứa n − i phần tử lớn nhất của A[1..n], đã sắp xếp." *Người tổng hợp:* Khởi tạo: i = n, BUILD-MAX-HEAP vừa biến A[1..n] thành đống max; A[n + 1..n] rỗng. Duy trì: A[1] là lớn nhất trong A[1..i], tức là phần tử nhỏ thứ i của cả mảng, và không lớn hơn mọi phần tử trong A[i + 1..n]; đổi nó về ô i làm A[i..n] chứa n − i + 1 phần tử lớn nhất, đã sắp. Giảm heap-size; hai cây con của gốc vẫn là đống max nên MAX-HEAPIFY(A, 1) biến A[1..i − 1] thành đống max chứa i − 1 phần tử nhỏ nhất. Kết thúc: i = 1; A[2..n] chứa n − 1 phần tử lớn nhất đã sắp, A[1] là phần tử nhỏ nhất, nên cả mảng đã sắp.
- **6.4-3:** Thời gian HEAPSORT trên mảng độ dài n đã sắp tăng dần? Giảm dần? *Người tổng hợp:* cả hai Θ(n lg n). Tăng dần: BUILD-MAX-HEAP tốn O(n) (phải đảo gần hết), sau đó n − 1 lần trích vẫn tốn Θ(n lg n). Giảm dần: mảng đã là đống max, BUILD-MAX-HEAP Θ(n) không đổi chỗ, nhưng mỗi lần đổi gốc với phần tử cuối (nhỏ) rồi cho chìm vẫn tốn Θ(lg n) phần lớn số lần, tổng Θ(n lg n).
- **6.4-4:** Chứng minh thời gian xấu nhất của HEAPSORT là Ω(n lg n). *Người tổng hợp:* heapsort là sắp xếp bằng so sánh nên chịu cận dưới Ω(n lg n) của Chương 8; trực tiếp hơn, theo 6.4-5, ngay cả trường hợp tốt nhất với phần tử khác nhau đã là Ω(n lg n), nên trường hợp xấu nhất cũng vậy.
- **6.4-5 ★:** Chứng minh khi mọi phần tử khác nhau, thời gian tốt nhất của HEAPSORT là Ω(n lg n). *Phác thảo của người tổng hợp* (lập luận thường được quy cho Schaffer và Sedgewick — theo hiểu biết của người tổng hợp): sau BUILD-MAX-HEAP, xét tập S gồm k = ⌈n/2⌉ phần tử lớn nhất. S đóng với phép lấy cha (cha của một phần tử lớn hơn nó, nên cũng thuộc S), tức S tạo thành một cây con chứa gốc. Trong k lần lặp đầu của HEAPSORT, đúng các phần tử của S được trích ra, mỗi phần tử phải đi tới gốc; mỗi lần đổi chỗ của MAX-HEAPIFY chỉ đưa một phần tử lên một tầng. Mỗi lá của đống thuộc S có cha thuộc S là nút trong, mỗi nút trong có tối đa 2 con, nên ít nhất khoảng k/3 phần tử của S nằm ở nút trong; trong số đó, số nút có độ sâu nhỏ hơn lg(k/6) chỉ khoảng k/6, nên ít nhất khoảng k/6 phần tử của S ở độ sâu ≥ lg(k/6) − O(1) và mỗi phần tử cần ngần ấy lần đi lên. Tổng số lần đổi chỗ ≥ (k/6)(lg(k/6) − O(1)) = Ω(n lg n).

### Bài tập Mục 6.5 (trang 164–166)

- **6.5-1:** Minh hoạ HEAP-EXTRACT-MAX trên A = ⟨15, 13, 9, 5, 12, 8, 7, 4, 0, 6, 2, 1⟩. *Lời giải của người tổng hợp:* max = 15; A[1] = A[12] = 1; heap-size = 11: ⟨1, 13, 9, 5, 12, 8, 7, 4, 0, 6, 2⟩. MAX-HEAPIFY(A, 1): 1 đổi với 13 (nút 2); ở nút 2: con 5 và 12 nên đổi với 12 (nút 5); ở nút 5: con A[10] = 6, A[11] = 2 nên đổi với 6 (nút 10); nút 10 là lá. Kết quả ⟨13, 12, 9, 5, 6, 8, 7, 4, 0, 1, 2⟩, trả về 15.
- **6.5-2:** Minh hoạ MAX-HEAP-INSERT(A, 10) trên A = ⟨15, 13, 9, 5, 12, 8, 7, 4, 0, 6, 2, 1⟩. *Lời giải của người tổng hợp:* heap-size = 13, A[13] = −∞, rồi HEAP-INCREASE-KEY(A, 13, 10): A[13] = 10; cha nút 6 có 8 < 10 nên đổi, i = 6; cha nút 3 có 9 < 10 nên đổi, i = 3; cha nút 1 có 15 ≥ 10 nên dừng. Kết quả ⟨15, 13, 10, 5, 12, 9, 7, 4, 0, 6, 2, 1, 8⟩.
- **6.5-3:** Viết pseudocode HEAP-MINIMUM, HEAP-EXTRACT-MIN, HEAP-DECREASE-KEY và MIN-HEAP-INSERT cho hàng đợi ưu tiên min bằng đống min. *Người tổng hợp:*

  ```text
  HEAP-MINIMUM(A)
  1  return A[1]

  HEAP-EXTRACT-MIN(A)
  1  if A.heap-size < 1
  2      error "heap underflow"
  3  min = A[1]
  4  A[1] = A[A.heap-size]
  5  A.heap-size = A.heap-size − 1
  6  MIN-HEAPIFY(A, 1)
  7  return min

  HEAP-DECREASE-KEY(A, i, key)
  1  if key > A[i]
  2      error "new key is larger than current key"
  3  A[i] = key
  4  while i > 1 and A[PARENT(i)] > A[i]
  5      exchange A[i] with A[PARENT(i)]
  6      i = PARENT(i)

  MIN-HEAP-INSERT(A, key)
  1  A.heap-size = A.heap-size + 1
  2  A[A.heap-size] = +∞
  3  HEAP-DECREASE-KEY(A, A.heap-size, key)
  ```
- **6.5-4:** Vì sao phải đặt khoá của nút mới là −∞ ở dòng 2 của MAX-HEAP-INSERT khi ngay sau đó ta tăng nó lên giá trị mong muốn? *Người tổng hợp:* để thoả tiền điều kiện của HEAP-INCREASE-KEY: khoá mới không được nhỏ hơn khoá hiện tại (dòng 1 sẽ báo lỗi nếu ô đó đang chứa một số rác lớn hơn key), và để đống hợp lệ trước lời gọi (lá −∞ không vi phạm tính chất đống max), nên bất biến của HEAP-INCREASE-KEY (Exercise 6.5-5) đúng ngay từ đầu.
- **6.5-5:** Lập luận tính đúng của HEAP-INCREASE-KEY bằng bất biến: "Đầu mỗi lần lặp của vòng while dòng 4–6, mảng con A[1..A.heap-size] thoả tính chất đống max, ngoại trừ có thể một vi phạm: A[i] có thể lớn hơn A[PARENT(i)]." Được giả định A[1..A.heap-size] thoả tính chất đống max khi HEAP-INCREASE-KEY được gọi. *Người tổng hợp:* Khởi tạo: trước dòng 3 đống hợp lệ; tăng A[i] chỉ có thể làm hỏng quan hệ giữa i và cha (với các con, A[i] lớn lên nên vẫn ≥ con). Duy trì: nếu A[PARENT(i)] < A[i], đổi chỗ sửa quan hệ i–cha; giá trị cũ của cha xuống ô i vẫn ≥ các con của i (vì trước đó nó ≥ giá trị cũ của A[i], mà giá trị cũ ≥ các con); vi phạm duy nhất có thể còn là giữa PARENT(i) mới và cha của nó; gán i = PARENT(i) giữ bất biến. Kết thúc: hoặc i = 1 (gốc không có cha), hoặc A[PARENT(i)] ≥ A[i]; cả hai trường hợp không còn vi phạm, đống hợp lệ.
- **6.5-6:** Mỗi phép đổi chỗ ở dòng 5 của HEAP-INCREASE-KEY thường cần ba phép gán. Dùng ý tưởng vòng lặp trong của INSERTION-SORT để giảm ba phép gán xuống còn một. *Người tổng hợp:* dời cha xuống thay vì đổi chỗ, chỉ ghi key một lần ở cuối:

  ```text
  HEAP-INCREASE-KEY′(A, i, key)
  1  if key < A[i]
  2      error "new key is smaller than current key"
  3  while i > 1 and A[PARENT(i)] < key
  4      A[i] = A[PARENT(i)]
  5      i = PARENT(i)
  6  A[i] = key
  ```
- **6.5-7:** Cài hàng đợi vào trước ra trước (FIFO) bằng hàng đợi ưu tiên; cài ngăn xếp bằng hàng đợi ưu tiên (hàng đợi và ngăn xếp định nghĩa ở Mục 10.1). *Người tổng hợp:* giữ một bộ đếm c tăng dần sau mỗi lần chèn. Hàng đợi FIFO: dùng hàng đợi ưu tiên min với khoá c (phần tử chèn sớm có khoá nhỏ, ra trước); ENQUEUE là INSERT, DEQUEUE là EXTRACT-MIN. Ngăn xếp: dùng hàng đợi ưu tiên max với khoá c (phần tử chèn muộn có khoá lớn, ra trước); PUSH là INSERT, POP là EXTRACT-MAX. Mỗi phép toán O(lg n) — chậm hơn cài đặt trực tiếp O(1), nhưng cho thấy hàng đợi ưu tiên tổng quát hơn.
- **6.5-8:** Phép toán HEAP-DELETE(A, i) xoá phần tử ở nút i khỏi đống A. Cài HEAP-DELETE chạy O(lg n) trên đống max n phần tử. *Người tổng hợp:*

  ```text
  HEAP-DELETE(A, i)
  1  key = A[A.heap-size]
  2  A.heap-size = A.heap-size − 1
  3  if i ≤ A.heap-size                // nút bị xoá không phải nút cuối
  4      if key > A[i]
  5          HEAP-INCREASE-KEY(A, i, key)
  6      else A[i] = key
  7          MAX-HEAPIFY(A, i)
  ```
  Phần tử cuối được đưa vào chỗ trống; nó có thể phải nổi lên (nếu lớn hơn phần tử bị xoá) hoặc chìm xuống (nếu nhỏ hơn). Chỉ gọi MAX-HEAPIFY là sai trong trường hợp thứ nhất — lỗi hay gặp.
- **6.5-9:** Thuật toán O(n lg k) trộn k danh sách đã sắp xếp thành một danh sách đã sắp xếp, n là tổng số phần tử. (Gợi ý: dùng đống min để trộn k ngả.) *Người tổng hợp:* đưa phần tử đầu của mỗi danh sách (kèm số hiệu danh sách) vào đống min, dựng trong O(k). Lặp n lần: EXTRACT-MIN lấy phần tử nhỏ nhất, ghi ra đầu ra, chèn phần tử kế tiếp của cùng danh sách (nếu còn). Đống không bao giờ quá k phần tử, mỗi phép toán O(lg k), tổng O(n lg k).

### Problem 6-1: Dựng đống bằng phép chèn (Building a heap using insertion)

Có thể dựng đống bằng cách gọi lặp lại MAX-HEAP-INSERT để chèn các phần tử vào đống. Xét biến thể sau của BUILD-MAX-HEAP:

```text
BUILD-MAX-HEAP′(A)
1  A.heap-size = 1
2  for i = 2 to A.length
3      MAX-HEAP-INSERT(A, A[i])
```

Dòng 1: đống ban đầu chỉ có A[1]. Dòng 2–3: lần lượt chèn A[2], A[3], …; lời gọi ở lần lặp i làm heap-size thành i và đặt khoá vào ô i rồi cho nó nổi lên. (Nhận xét của người tổng hợp: MAX-HEAP-INSERT ghi −∞ vào ô A[i] trước khi tăng khoá, nhưng giá trị A[i] đã được truyền vào như tham số key nên không mất.)

- **(a)** BUILD-MAX-HEAP và BUILD-MAX-HEAP′ có luôn tạo cùng một đống trên cùng mảng đầu vào không? Chứng minh hoặc cho phản ví dụ. *Lời giải của người tổng hợp:* không. Phản ví dụ A = ⟨1, 2, 3⟩. BUILD-MAX-HEAP: i = 1, 1 đổi với 3, được ⟨3, 2, 1⟩. BUILD-MAX-HEAP′: đống ⟨1⟩; chèn 2: 2 > 1 nên đổi, được ⟨2, 1⟩; chèn 3 ở ô 3, cha là ô 1 có 2 < 3 nên đổi, được ⟨3, 1, 2⟩. Hai đống khác nhau (cả hai đều hợp lệ).
- **(b)** Chứng minh trong trường hợp xấu nhất BUILD-MAX-HEAP′ cần Θ(n lg n) để dựng đống n phần tử. *Người tổng hợp:* cận trên: n − 1 lần chèn, mỗi lần O(lg n). Cận dưới: với mảng sắp xếp tăng dần, mỗi phần tử mới lớn hơn mọi phần tử đã có nên nổi lên tới gốc, tốn ⌊lg i⌋ lần đổi chỗ ở lần chèn thứ i. Tổng Σ_{i=2}^{n} ⌊lg i⌋ ≥ Σ_{i=n/2}^{n} (lg n − 2) ≥ (n/2)(lg n − 2) = Ω(n lg n). Ví dụ n = 8 với ⟨1, …, 8⟩: số lần đổi 1 + 1 + 2 + 2 + 2 + 2 + 3 = 13.

### Problem 6-2: Phân tích đống d-phân (Analysis of d-ary heaps)

**Đống d-phân** (d-ary heap) giống đống nhị phân, nhưng (với tối đa một ngoại lệ) các nút không phải lá có d con thay vì 2.

- **(a)** Biểu diễn đống d-phân trong mảng thế nào? *Người tổng hợp:* vẫn lưu theo tầng từ trái sang. Con thứ j (j = 1..d) của nút i là d(i − 1) + j + 1; cha của nút i là ⌊(i − 2)/d⌋ + 1. Kiểm tra d = 2: con là 2i và 2i + 1, cha là ⌊(i − 2)/2⌋ + 1 = ⌊i/2⌋. Ví dụ d = 3: con của nút 1 là 2, 3, 4; con của nút 2 là 5, 6, 7; cha của nút 7 là ⌊5/3⌋ + 1 = 2.
- **(b)** Chiều cao của đống d-phân n phần tử theo n và d? *Người tổng hợp:* cây cao h chứa tối đa 1 + d + … + d^h = (d^(h+1) − 1)/(d − 1) nút, nên h = ⌈log_d(n(d − 1) + 1)⌉ − 1 = Θ(log_d n) = Θ(lg n / lg d). Ví dụ d = 3, n = 13: ⌈log₃ 27⌉ − 1 = 2.
- **(c)** Cài EXTRACT-MAX hiệu quả cho đống d-phân max; phân tích theo d và n. *Người tổng hợp:* như HEAP-EXTRACT-MAX, nhưng MAX-HEAPIFY d-phân tìm con lớn nhất trong d con (d − 1 phép so sánh) ở mỗi tầng. Thời gian O(d log_d n).
- **(d)** Cài INSERT hiệu quả; phân tích. *Người tổng hợp:* như MAX-HEAP-INSERT; vòng nổi lên chỉ so với cha, một phép so sánh mỗi tầng. Thời gian O(log_d n).
- **(e)** Cài INCREASE-KEY(A, i, k): báo lỗi nếu k < A[i], ngược lại đặt A[i] = k rồi cập nhật cấu trúc đống d-phân max; phân tích. *Người tổng hợp:* như HEAP-INCREASE-KEY với hàm cha mới; O(log_d n).

Nhận xét của người tổng hợp: d lớn làm INSERT và INCREASE-KEY nhanh hơn nhưng EXTRACT-MAX chậm hơn. Với thuật toán như Dijkstra, nơi số lần DECREASE-KEY (tối đa m cạnh) lớn hơn nhiều số lần EXTRACT-MIN (n đỉnh), chọn d ≈ m/n cho thời gian O(m log_{m/n} n) (theo hiểu biết của người tổng hợp).

### Problem 6-3: Bảng Young (Young tableaus)

**Bảng Young** m × n là ma trận m × n sao cho các phần tử mỗi hàng được sắp xếp từ trái sang phải và các phần tử mỗi cột được sắp xếp từ trên xuống dưới. Một số phần tử của bảng Young có thể là ∞, được coi là phần tử không tồn tại. Vì vậy bảng Young có thể chứa r ≤ mn số hữu hạn.

- **(a)** Vẽ bảng Young 4 × 4 chứa các phần tử {9, 16, 3, 2, 4, 8, 5, 14, 12}. *Một lời giải của người tổng hợp* (có nhiều đáp án):

  ```text
   2   3   4   5
   8   9  12  14
  16   ∞   ∞   ∞
   ∞   ∞   ∞   ∞
  ```
  Hàng tăng dần; cột: 2 < 8 < 16, 3 < 9, 4 < 12, 5 < 14.
- **(b)** Lập luận rằng bảng Young Y m × n rỗng nếu Y[1, 1] = ∞, và đầy (chứa mn phần tử) nếu Y[m, n] < ∞. *Người tổng hợp:* Y[1, 1] là nhỏ nhất (mọi ô đi được từ (1, 1) bằng các bước sang phải và xuống dưới, giá trị không giảm), nên Y[1, 1] = ∞ kéo theo mọi ô bằng ∞. Tương tự Y[m, n] lớn nhất, nên Y[m, n] < ∞ kéo theo mọi ô hữu hạn.
- **(c)** Cho thuật toán EXTRACT-MIN trên bảng Young m × n khác rỗng chạy O(m + n), dùng thủ tục con đệ quy giải bài m × n bằng cách giải đệ quy bài (m − 1) × n hoặc m × (n − 1). (Gợi ý: nghĩ tới MAX-HEAPIFY.) Định nghĩa T(p), với p = m + n, là thời gian chạy tối đa của EXTRACT-MIN trên mọi bảng Young m × n; cho và giải truy hồi của T(p) ra cận O(m + n). *Người tổng hợp:* lấy min = Y[1, 1], đặt Y[1, 1] = ∞, rồi gọi YOUNGIFY(Y, 1, 1): so ô (i, j) với ô dưới (i + 1, j) và ô phải (i, j + 1); nếu ô nhỏ nhất trong ba ô không phải (i, j), đổi chỗ với nó và đệ quy tại ô đó — vùng còn phải sửa là bảng con bớt một hàng hoặc bớt một cột. T(p) = T(p − 1) + O(1), nên T(p) = O(p) = O(m + n).
- **(d)** Chèn một phần tử mới vào bảng Young m × n chưa đầy trong O(m + n). *Người tổng hợp:* đặt phần tử vào Y[m, n] (đang là ∞ vì bảng chưa đầy), rồi cho nó "nổi" ngược: so với ô trên và ô trái, đổi chỗ với ô lớn hơn trong hai ô nếu ô đó lớn hơn phần tử, lặp lại. Mỗi bước giảm i + j đi 1, nên O(m + n).
- **(e)** Không dùng phương pháp sắp xếp nào khác làm thủ tục con, chỉ ra cách dùng bảng Young n × n để sắp xếp n² số trong O(n³). *Người tổng hợp:* chèn n² số, mỗi lần O(2n); rồi gọi EXTRACT-MIN n² lần, mỗi lần O(2n). Tổng O(n² · n) = O(n³). (Với N = n² số, đây là O(N^1,5) — kém n lg n, chỉ là bài tập.)
- **(f)** Thuật toán O(m + n) kiểm tra một số cho trước có nằm trong bảng Young m × n hay không. *Người tổng hợp:* bắt đầu ở góc trên phải (1, n). Nếu ô bằng x thì tìm thấy; nếu ô lớn hơn x thì cả cột bên dưới đều lớn hơn x, sang trái; nếu ô nhỏ hơn x thì cả hàng bên trái đều nhỏ hơn x, đi xuống. Mỗi bước loại một hàng hoặc một cột: tối đa m + n bước.

### Ghi chú chương (Chapter notes, trang 168–169)

- Thuật toán heapsort do **Williams** phát minh; ông cũng mô tả cách cài hàng đợi ưu tiên bằng đống. Thủ tục BUILD-MAX-HEAP do **Floyd** đề xuất. (Theo hiểu biết của người tổng hợp: cả hai công bố năm 1964 trên *Communications of the ACM*, dưới dạng "Algorithm 232 — Heapsort" và "Algorithm 245 — Treesort 3".)
- Sách dùng đống min để cài hàng đợi ưu tiên min ở Chương 16, 23 và 24. Sách cũng cho một cài đặt có cận thời gian tốt hơn cho một số phép toán ở Chương 19 (đống Fibonacci) và, khi khoá lấy từ một tập bị chặn các số nguyên không âm, ở Chương 20 (cây van Emde Boas).
- Nếu dữ liệu là số nguyên b bit và bộ nhớ máy tính gồm các từ b bit định địa chỉ được, **Fredman và Willard** chỉ ra cách cài MINIMUM trong O(1) và INSERT, EXTRACT-MIN trong O(√lg n). **Thorup** cải thiện cận O(√lg n) thành O(lg lg n). Cận này dùng lượng bộ nhớ không bị chặn theo n, nhưng có thể cài trong bộ nhớ tuyến tính bằng băm ngẫu nhiên.
- Một trường hợp đặc biệt quan trọng của hàng đợi ưu tiên xảy ra khi dãy các phép toán EXTRACT-MIN là **đơn điệu** (monotone), tức các giá trị trả về bởi các lần EXTRACT-MIN liên tiếp tăng đơn điệu theo thời gian. Trường hợp này xuất hiện trong nhiều ứng dụng quan trọng, như thuật toán đường đi ngắn nhất một nguồn của Dijkstra (Chương 24) và mô phỏng sự kiện rời rạc. Với thuật toán Dijkstra, việc cài DECREASE-KEY hiệu quả đặc biệt quan trọng. Trong trường hợp đơn điệu, nếu dữ liệu là số nguyên trong khoảng 1, 2, …, C, **Ahuja, Mehlhorn, Orlin và Tarjan** mô tả cách cài EXTRACT-MIN và INSERT trong thời gian khấu hao O(lg C) (Chương 17 về phân tích khấu hao) và DECREASE-KEY trong O(1), dùng cấu trúc gọi là **đống cơ số** (radix heap). Cận O(lg C) có thể cải thiện thành O(√lg C) bằng cách dùng đống Fibonacci (Chương 19) cùng với đống cơ số. **Cherkassky, Goldberg và Silverstein** cải thiện tiếp cận này thành O(lg^(1/3+ε) C) kỳ vọng bằng cách kết hợp cấu trúc phân cụm nhiều tầng của **Denardo và Fox** với đống của Thorup nói trên. **Raman** cải thiện tiếp các kết quả này để có cận O(min(lg^(1/4+ε) C, lg^(1/3+ε) n)), với mọi ε > 0 cố định.

## Luận điểm cốt lõi

### Mệnh đề

Một mảng được nhìn như cây nhị phân gần đầy đủ và giữ tính chất đống max cho phép đọc phần tử lớn nhất trong Θ(1) và khôi phục cấu trúc sau mỗi thay đổi cục bộ trong O(lg n). Từ đó có (1) heapsort — thuật toán sắp xếp tại chỗ với thời gian xấu nhất O(n lg n), kết hợp ưu điểm của sắp xếp chèn và sắp xếp trộn — và (2) hàng đợi ưu tiên với mọi phép toán O(lg n). Dựng đống từ mảng bất kỳ chỉ tốn O(n).

### Giả định

- Mô hình RAM của Chương 2: so sánh, gán, đổi chỗ, phép toán số học trên chỉ số (2i, ⌊i/2⌋) đều tốn thời gian hằng số.
- Phần tử được so sánh được với nhau theo thứ tự toàn phần (khoá).
- Mảng có đủ chỗ (A.heap-size ≤ A.length); thủ tục không kiểm tra tràn mảng ở MAX-HEAP-INSERT.
- Phân tích MAX-HEAPIFY bằng định lý thợ dùng cận "cây con của một con ≤ 2n/3"; phân tích BUILD-MAX-HEAP dùng cận ⌈n/2^(h+1)⌉ nút ở chiều cao h.
- Ở Mục 6.5, việc duy trì tay cầm giữa phần tử đống và đối tượng ứng dụng được giả định là làm được, không đi vào chi tiết.

### Cơ chế

1. **Hình dạng cố định cho phép điều hướng bằng số học chỉ số:** cây gần đầy đủ không có lỗ nên nút i có cha ⌊i/2⌋ và con 2i, 2i + 1; chiều cao ⌊lg n⌋.
2. **Thứ tự cục bộ đủ để biết phần tử lớn nhất:** chỉ đòi cha ≥ con, đủ để max ở gốc nhưng rẻ để duy trì (không cần sắp xếp hoàn toàn).
3. **Chìm xuống (MAX-HEAPIFY):** sửa một vi phạm ở đỉnh một cây con mà hai cây con dưới đã đúng; mỗi tầng Θ(1), O(h) tổng.
4. **Dựng từ dưới lên (BUILD-MAX-HEAP):** gọi MAX-HEAPIFY từ ⌊n/2⌋ về 1; đa số nút thấp nên tổng Σ ⌈n/2^(h+1)⌉ O(h) = O(n).
5. **Sắp xếp bằng trích liên tiếp (HEAPSORT):** đổi gốc với cuối vùng đống, thu nhỏ đống, chìm xuống; vùng đống và vùng đã sắp chia nhau cùng một mảng.
6. **Nổi lên (HEAP-INCREASE-KEY):** khi một khoá tăng, đổi với cha cho tới khi cha ≥ nó; chèn là "thêm lá −∞ rồi tăng khoá".

### Bằng chứng và ví dụ tác giả đưa ra

- Đống max [16, 14, 10, 8, 7, 9, 3, 2, 4, 1] vẽ cả dạng cây lẫn dạng mảng; cây cao 3, nút 4 cao 1.
- MAX-HEAPIFY(A, 2) trên [16, 4, 10, 14, 7, 9, 3, 2, 8, 1]: 4 chìm qua nút 4 tới nút 9.
- Truy hồi T(n) ≤ T(2n/3) + Θ(1) = O(lg n) bằng định lý thợ.
- Chứng minh BUILD-MAX-HEAP đúng bằng bất biến vòng lặp ba bước; ví dụ dựng đống từ [4, 1, 3, 2, 16, 9, 10, 14, 8, 7] qua sáu khung.
- Chặn Σ h/2^h = 2 bằng công thức (A.8), cho BUILD-MAX-HEAP tuyến tính.
- Ví dụ HEAPSORT qua 11 khung (a)–(k), cho [1, 2, 3, 4, 7, 8, 9, 10, 14, 16].
- Ví dụ HEAP-INCREASE-KEY tăng khoá 4 lên 15, nổi lên hai tầng.
- Bảng thời gian chạy của bảy thuật toán sắp xếp ở lời giới thiệu Phần II.

### Kết luận và hàm ý cho người lập trình

- Khi cần bảo đảm thời gian xấu nhất O(n lg n) và không có bộ nhớ phụ, heapsort là lựa chọn an toàn; khi cần tốc độ trung bình, quicksort thường thắng.
- Đã có đủ n phần tử thì dựng đống một lần (O(n)), đừng chèn từng phần tử (O(n lg n) xấu nhất, Problem 6-1).
- Hàng đợi ưu tiên là công cụ chuẩn cho lập lịch, mô phỏng sự kiện, Dijkstra, Prim, Huffman, trộn k ngả, top-k.
- Muốn dùng DECREASE-KEY/INCREASE-KEY trên đối tượng cụ thể thì phải duy trì tay cầm (chỉ số mảng) và cập nhật mỗi khi phần tử đổi chỗ.
- Cẩn thận ranh giới: so chỉ số con với heap-size chứ không phải length; xoá phần tử ở giữa đống có thể phải nổi lên hoặc chìm xuống (Exercise 6.5-8).
- Heapsort không ổn định (phần tử bằng nhau có thể đổi thứ tự) và truy cập bộ nhớ kém cục bộ; cân nhắc khi cần sắp xếp nhiều khoá hoặc dữ liệu lớn.

### Trong ngôn ngữ khoa học máy tính

Đống nhị phân: mảng A[1..n], PARENT(i) = ⌊i/2⌋, LEFT(i) = 2i, RIGHT(i) = 2i + 1; tính chất đống max ∀i > 1: A[⌊i/2⌋] ≥ A[i]; chiều cao ⌊lg n⌋. MAX-HEAPIFY: T(n) ≤ T(2n/3) + Θ(1) ⇒ O(lg n), Ω(lg n) xấu nhất. BUILD-MAX-HEAP: Σ_{h=0}^{⌊lg n⌋} ⌈n/2^(h+1)⌉ O(h) = O(n Σ h/2^h) = O(n). HEAPSORT: O(n) + (n − 1) O(lg n) = Θ(n lg n) xấu nhất (và tốt nhất khi phần tử khác nhau), bộ nhớ phụ O(1), không ổn định, là sắp xếp bằng so sánh nên tối ưu tiệm cận. Hàng đợi ưu tiên bằng đống: MAXIMUM Θ(1); EXTRACT-MAX, INCREASE-KEY, INSERT O(lg n). Đống d-phân: chiều cao Θ(log_d n), EXTRACT-MAX O(d log_d n), INSERT/INCREASE-KEY O(log_d n).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| sorting problem | bài toán sắp xếp | cho dãy n số, tìm hoán vị không giảm |
| permutation | hoán vị | một cách sắp xếp lại dãy |
| record | bản ghi | tập dữ liệu chứa khoá và dữ liệu vệ tinh |
| key | khoá | giá trị dùng để sắp xếp hoặc để ưu tiên |
| satellite data | dữ liệu vệ tinh | phần dữ liệu đi kèm khoá, thuật toán không dùng |
| in place | tại chỗ | chỉ hằng số phần tử nằm ngoài mảng tại mọi lúc |
| comparison sort | sắp xếp bằng so sánh | chỉ dùng phép so sánh để xác định thứ tự |
| decision-tree model | mô hình cây quyết định | công cụ chứng minh cận dưới Ω(n lg n) ở Chương 8 |
| counting sort / radix sort / bucket sort | sắp xếp đếm / cơ số / phân cụm | các thuật toán vượt cận Ω(n lg n) ở Chương 8 |
| order statistic | thống kê thứ tự | phần tử nhỏ thứ i của tập |
| heapsort | sắp xếp vun đống (heapsort) | sắp xếp bằng đống max, O(n lg n), tại chỗ |
| (binary) heap | đống (nhị phân) | mảng nhìn như cây nhị phân gần đầy đủ có tính chất đống |
| nearly complete binary tree | cây nhị phân gần đầy đủ | mọi tầng đầy trừ tầng đáy lấp từ trái sang |
| heap-size | kích thước đống | số phần tử hợp lệ của đống trong mảng |
| parent / left child / right child | cha / con trái / con phải | ⌊i/2⌋ / 2i / 2i + 1 |
| heap property | tính chất đống | ràng buộc giữa giá trị cha và con |
| max-heap / min-heap | đống max / đống min | cha ≥ con / cha ≤ con |
| height (of a node / of a heap) | chiều cao (nút / đống) | số cạnh của đường đi xuống dài nhất tới lá |
| leaf | lá | nút không có con |
| float down | chìm xuống | phần tử đi xuống bằng cách đổi với con lớn hơn |
| MAX-HEAPIFY | MAX-HEAPIFY | thủ tục khôi phục tính chất đống max tại một nút |
| BUILD-MAX-HEAP | BUILD-MAX-HEAP | dựng đống max từ mảng bất kỳ, O(n) |
| loop invariant | bất biến vòng lặp | mệnh đề đúng đầu mỗi vòng lặp |
| priority queue | hàng đợi ưu tiên | cấu trúc lấy ra phần tử có khoá lớn nhất/nhỏ nhất |
| max-priority / min-priority queue | hàng đợi ưu tiên max / min | ưu tiên khoá lớn nhất / nhỏ nhất |
| INSERT, MAXIMUM, EXTRACT-MAX, INCREASE-KEY | chèn, lấy max, trích max, tăng khoá | bốn phép toán của hàng đợi ưu tiên max |
| DECREASE-KEY | giảm khoá | phép toán của hàng đợi ưu tiên min |
| job scheduling | lập lịch công việc | ứng dụng của hàng đợi ưu tiên max |
| event-driven simulation | mô phỏng hướng sự kiện | ứng dụng của hàng đợi ưu tiên min |
| handle | tay cầm | thông tin nối phần tử đống với đối tượng ứng dụng |
| heap underflow | tràn dưới đống | trích từ đống rỗng |
| d-ary heap | đống d-phân | mỗi nút trong có d con |
| Young tableau | bảng Young | ma trận có hàng và cột đều tăng |
| monotone priority queue | hàng đợi ưu tiên đơn điệu | giá trị EXTRACT-MIN trả về không giảm theo thời gian |
| radix heap | đống cơ số | hàng đợi ưu tiên đơn điệu cho khoá nguyên 1..C |
| amortized time | thời gian khấu hao | chi phí trung bình mỗi phép toán trên một chuỗi (Chương 17) |
| garbage-collected storage | vùng nhớ thu gom rác | nghĩa khác của "heap" trong ngôn ngữ lập trình |

## Câu nói đáng nhớ

> "Thus, heapsort combines the better attributes of the two sorting algorithms we have already discussed." — mở đầu Chương 6
>
> *Dịch: Như vậy, heapsort kết hợp những thuộc tính tốt hơn của hai thuật toán sắp xếp mà ta đã bàn.*

> "Heapsort also introduces another algorithm design technique: using a data structure, in this case one we call a 'heap,' to manage information." — mở đầu Chương 6
>
> *Dịch: Heapsort còn giới thiệu một kỹ thuật thiết kế thuật toán khác: dùng một cấu trúc dữ liệu — ở đây là cấu trúc ta gọi là "đống" — để quản lý thông tin.*

> "Many computer scientists consider sorting to be the most fundamental problem in the study of algorithms." — lời giới thiệu Phần II
>
> *Dịch: Nhiều nhà khoa học máy tính coi sắp xếp là bài toán cơ bản nhất trong nghiên cứu thuật toán.*

> "Many of these issues are best dealt with at the algorithmic level, rather than by 'tweaking' the code." — lời giới thiệu Phần II
>
> *Dịch: Nhiều vấn đề trong số này nên được giải quyết ở mức thuật toán, hơn là bằng cách "vặn vẹo" mã.*

> "Hence, we can build a max-heap from an unordered array in linear time." — Mục 6.3
>
> *Dịch: Vì vậy, ta có thể dựng một đống max từ một mảng không có thứ tự trong thời gian tuyến tính.*

> "Heapsort is an excellent algorithm, but a good implementation of quicksort, presented in Chapter 7, usually beats it in practice." — Mục 6.5
>
> *Dịch: Heapsort là một thuật toán xuất sắc, nhưng một cài đặt tốt của quicksort, trình bày ở Chương 7, thường thắng nó trong thực tế.*

> "In summary, a heap can support any priority-queue operation on a set of size n in O(lg n) time." — Mục 6.5
>
> *Dịch: Tóm lại, đống có thể hỗ trợ mọi phép toán hàng đợi ưu tiên trên tập kích thước n trong thời gian O(lg n).*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: phân tích BUILD-MAX-HEAP là bài học về "cận thô và cận chặt"

Sách cố ý đưa cận O(n lg n) trước (đúng nhưng không chặt), rồi chỉ ra rằng chi phí của MAX-HEAPIFY phụ thuộc chiều cao nút chứ không phải n, và đa số nút ở gần đáy. Lời giải Σ ⌈n/2^(h+1)⌉ O(h) = O(n) với Σ h/2^h = 2 là ví dụ điển hình cho thói quen phân tích nên có: khi tổng chi phí là tổng của nhiều thao tác có chi phí khác nhau, đếm theo "lớp" (ở đây là chiều cao) thay vì nhân số thao tác với chi phí lớn nhất. Cùng tư tưởng này xuất hiện lại ở phân tích khấu hao (Chương 17) và ở phân tích hợp theo hạng (Chương 21).

### Điểm mạnh: một cấu trúc dữ liệu, hai ứng dụng

Chương cho thấy cấu trúc dữ liệu là công cụ thiết kế thuật toán: cùng MAX-HEAPIFY vừa là lõi của một thuật toán sắp xếp tối ưu, vừa là lõi của hàng đợi ưu tiên dùng suốt Phần VI (đồ thị). HEAP-EXTRACT-MAX được viết như "thân vòng lặp của HEAPSORT", làm lộ rõ rằng heapsort chính là "chèn hết vào hàng đợi ưu tiên rồi trích ra lần lượt" — một quan điểm thống nhất cũng giải thích vì sao sắp xếp chọn (selection sort) chậm (hàng đợi ưu tiên bằng mảng không sắp xếp) và sắp xếp chèn chậm (hàng đợi ưu tiên bằng mảng đã sắp xếp) — nhận xét của người tổng hợp.

### Điểm yếu và chỗ đơn giản hoá

- **Không phân tích trường hợp trung bình**, và bảng ở lời giới thiệu Phần II để trống ô đó. Người đọc không biết heapsort trung bình tốn khoảng 2n lg n phép so sánh (theo hiểu biết của người tổng hợp), nhiều hơn quicksort (≈ 1,39 n lg n) và sắp xếp trộn (≈ n lg n); đây là một phần lý do vì sao "quicksort thường thắng heapsort".
- **Không nói về tính cục bộ bộ nhớ.** Lý do thực tế lớn nhất khiến heapsort chậm trên máy hiện đại là truy cập A[i] rồi A[2i], A[4i]… nhảy xa trong bộ nhớ, làm hỏng bộ nhớ đệm khi n lớn. Lời giới thiệu Phần II có nhắc "phân cấp bộ nhớ" là vấn đề kỹ thuật quan trọng, nhưng Chương 6 không áp dụng nhận xét đó cho chính heapsort.
- **Không nhắc biến thể giảm số phép so sánh**, như heapsort "từ dưới lên" (bottom-up heapsort: cho phần tử chìm thẳng tới lá theo con lớn hơn rồi nổi ngược lên, gần n lg n phép so sánh) — theo hiểu biết của người tổng hợp.
- **Thủ tục hàng đợi ưu tiên làm việc trên chỉ số và khoá trần**, còn việc giữ tay cầm được nói bằng lời. Đây là nguồn lỗi chính khi tự cài Dijkstra với DECREASE-KEY. Ấn bản 4 đã viết lại phần này theo hướng đối tượng (theo hiểu biết của người tổng hợp).
- **Một số chỗ lời văn chưa chặt** (đã nêu ở Lưu ý): "complete binary tree" thay cho "nearly complete", "dừng nếu nhỏ hơn" thay cho "không lớn hơn", không kiểm tra tràn mảng ở MAX-HEAP-INSERT.
- **Heapsort không ổn định** nhưng chương không nói; tính chất này chỉ được định nghĩa ở Chương 8.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: heapsort hiếm khi là thuật toán sắp xếp mặc định, nhưng đống là một trong các cấu trúc dữ liệu được dùng nhiều nhất. Các thư viện chuẩn đều có hàng đợi ưu tiên bằng đống nhị phân trong mảng (`heapq` của Python là đống min, `std::priority_queue` của C++ mặc định là đống max, `java.util.PriorityQueue` là đống min). Introsort trong `std::sort` dùng heapsort làm đường lui khi quicksort đệ quy quá sâu. Trong các hệ thống, đống 4-phân (d = 4) thường nhanh hơn đống nhị phân nhờ cây thấp hơn và các con nằm cạnh nhau trong bộ nhớ (Problem 6-2). Còn đống Fibonacci (Chương 19), dù có cận lý thuyết tốt hơn cho DECREASE-KEY, thường chậm hơn đống nhị phân trong thực tế vì hằng số lớn.

### Liên hệ các chương khác

- Chương 2: sắp xếp chèn và sắp xếp trộn — heapsort kết hợp ưu điểm của cả hai; kỹ thuật bất biến vòng lặp dùng lại cho BUILD-MAX-HEAP, HEAPSORT, HEAP-INCREASE-KEY; vòng nổi lên của HEAP-INCREASE-KEY gợi nhớ vòng lặp chèn của INSERTION-SORT.
- Chương 4: định lý thợ cho T(n) ≤ T(2n/3) + Θ(1).
- Phụ lục A: công thức (A.8) Σ k xᵏ = x/(1 − x)²; Phụ lục B: định nghĩa cây nhị phân, cây đầy đủ.
- Chương 7: quicksort — nhanh hơn trung bình, xấu nhất kém hơn; introsort ghép hai thuật toán.
- Chương 8: cận dưới Ω(n lg n) cho sắp xếp bằng so sánh chứng tỏ heapsort tối ưu tiệm cận.
- Chương 9: bài toán thống kê thứ tự nêu ở lời giới thiệu Phần II; đống cũng giải được "k phần tử lớn nhất" trong O(n + k lg n).
- Chương 10: hàng đợi và ngăn xếp (Exercise 6.5-7); khái niệm tập động của Phần III tổng quát hoá hàng đợi ưu tiên.
- Chương 16: mã Huffman dùng hàng đợi ưu tiên min.
- Chương 19, 20: đống Fibonacci và cây van Emde Boas — hàng đợi ưu tiên nhanh hơn ở một số phép toán.
- Chương 23, 24: Prim và Dijkstra dùng hàng đợi ưu tiên min với DECREASE-KEY.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** câu hỏi kinh điển "tìm k phần tử lớn nhất trong luồng dữ liệu" (giữ đống min k phần tử, O(n lg k)), "trộn k danh sách đã sắp xếp" (Exercise 6.5-9), "trung vị của luồng dữ liệu" (hai đống: đống max cho nửa dưới, đống min cho nửa trên), "vì sao dựng đống là O(n) chứ không phải O(n lg n)", và viết MAX-HEAPIFY không lỗi ở ranh giới (so với heap-size, chọn con lớn hơn khi chỉ có một con).
- **Lập trình thi đấu:** dùng hàng đợi ưu tiên của thư viện cho Dijkstra theo kiểu "chèn bản sao, bỏ qua bản cũ khi trích ra" thay vì DECREASE-KEY (O(m lg m) = O(m lg n)); tìm kiếm trên bảng Young (Problem 6-3(f)) là bài "tìm trong ma trận có hàng và cột đã sắp xếp" quen thuộc.
- **Kỹ thuật phần mềm:** hàng đợi ưu tiên cho bộ hẹn giờ, lập lịch tác vụ, giới hạn tốc độ, cache loại bỏ theo ưu tiên; khi cần đổi độ ưu tiên của một đối tượng đang ở trong đống, phải lưu chỉ số của nó và cập nhật mỗi khi đổi chỗ (tay cầm của Mục 6.5), hoặc dùng cấu trúc "indexed priority queue". Khi cần sắp xếp với bảo đảm thời gian và không cấp phát bộ nhớ (hệ nhúng, nhân hệ điều hành), heapsort là lựa chọn hợp lý.

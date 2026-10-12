# Chương 9 — Trung vị và thống kê thứ tự (Medians and Order Statistics)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần II "Sorting and Order Statistics", Chương 9 "Medians and Order Statistics", trang 213–227 (bài toán cuối chương kết thúc ở trang 226, Ghi chú chương nằm ở trang 227).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (MIT, Dartmouth), tác giả bộ giáo trình thuật toán được dùng rộng rãi nhất; Rivest là một trong năm người đề xuất thuật toán chọn tuyến tính trong trường hợp xấu nhất trình bày ở chương này.
**Vị trí trong lập luận của cả cuốn sách:** Chương 7 ([C07-quicksort.md](C07-quicksort.md)) đưa ra thủ tục PARTITION (chia mảng quanh một phần tử chốt trong thời gian tuyến tính) và bản ngẫu nhiên RANDOMIZED-PARTITION (chọn chốt ngẫu nhiên đều); Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)) cung cấp công cụ biến ngẫu nhiên chỉ báo và tính tuyến tính của kỳ vọng; Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)) cung cấp phương pháp thế (substitution method) để giải truy hồi. Chương 8 ([C08-sap-xep-thoi-gian-tuyen-tinh.md](C08-sap-xep-thoi-gian-tuyen-tinh.md)) chứng minh mọi thuật toán sắp xếp chỉ dựa trên so sánh cần Ω(n lg n) phép so sánh, và chỉ vượt được giới hạn đó khi giả định thêm về dữ liệu (số nguyên trong khoảng nhỏ, phân phối đều). Chương 9 khép lại Phần II bằng một kết quả đối lập: bài toán **chọn** phần tử nhỏ thứ i — trong đó có trung vị — giải được trong thời gian **tuyến tính** chỉ bằng phép so sánh, không cần giả định gì về dữ liệu, vì không cần sắp xếp toàn bộ. Phần III mở đầu bằng Chương 10 ([C10-cau-truc-du-lieu-co-ban.md](C10-cau-truc-du-lieu-co-ban.md)); Chương 14 ([C14-mo-rong-cau-truc-du-lieu.md](C14-mo-rong-cau-truc-du-lieu.md)) sẽ giải phiên bản **động** của cùng bài toán (tập hợp thay đổi theo thời gian) bằng cây thống kê thứ tự với thời gian O(lg n) mỗi truy vấn, và nhiều chương sau (ví dụ dùng trung vị làm chốt để quicksort đạt O(n lg n) trong trường hợp xấu nhất) dùng SELECT như một thủ tục con.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **tìm phần tử nhỏ thứ i trong n phần tử dễ hơn hẳn sắp xếp: Θ(n) so với Θ(n lg n)**, và có hai cách đạt được điều đó. Trước hết, với trường hợp đặc biệt: tìm phần tử nhỏ nhất cần đúng n − 1 phép so sánh (thuật toán MINIMUM là tối ưu, chứng minh bằng lập luận "giải đấu": mọi phần tử trừ người thắng phải thua ít nhất một trận), còn tìm đồng thời nhỏ nhất và lớn nhất chỉ cần tối đa 3⌊n/2⌋ phép so sánh nhờ xử lý từng cặp. Với bài toán chọn tổng quát, RANDOMIZED-SELECT (Hoare) mượn ý quicksort nhưng chỉ đệ quy vào **một** phía của phép chia; thời gian kỳ vọng Θ(n), trường hợp xấu nhất Θ(n²). Thuật toán SELECT (Blum, Floyd, Pratt, Rivest, Tarjan) chia phần tử thành các nhóm 5, lấy trung vị của mỗi nhóm, đệ quy tìm "trung vị của các trung vị" làm chốt; chốt này bảo đảm mỗi phía có ít nhất 3n/10 − 6 phần tử, cho truy hồi T(n) ≤ T(⌈n/5⌉) + T(7n/10 + 6) + O(n) và do đó thời gian **tuyến tính trong trường hợp xấu nhất**. Vì hai thuật toán chỉ so sánh phần tử mà vẫn đạt O(n), chúng không bị giới hạn Ω(n lg n) của sắp xếp chi phối: cách "sắp xếp rồi lấy phần tử thứ i" là kém hiệu quả về tiệm cận.

> **Lưu ý:**
> - **Mục khó có dấu sao (★) trong chương:** chương không có mục lớn nào đánh dấu sao; chỉ có hai bài tập đánh dấu sao là 9.1-2 (chứng minh cận dưới ⌈3n/2⌉ − 2 phép so sánh để tìm cả lớn nhất lẫn nhỏ nhất) và 9.3-4 (thuật toán so sánh tìm phần tử thứ i thì đồng thời biết luôn i − 1 phần tử nhỏ hơn và n − i phần tử lớn hơn).
> - **Phạm vi trang:** bảng phân công ghi trang 213–226, nhưng Ghi chú chương (Chapter notes) nằm ở trang 227; bản tổng hợp này bao gồm cả trang 227.
> - **Lớp chữ PDF hỏng, đã đọc lại từ ảnh trang:** toàn bộ pseudocode (MINIMUM, RANDOMIZED-SELECT), các truy hồi và chuỗi bất đẳng thức trong phân tích mục 9.2 (trang 217–219) và mục 9.3 (trang 221–222) — lớp chữ làm mất các dấu ≤, ≥, làm Ω thành ".", tách rời phân số và tổng Σ — cùng với Hình 9.1 (sơ đồ nhóm 5 phần tử) và công thức của Bài toán 9-2, 9-3, 9-4 đều được chép lại từ ảnh trang.
> - **Lỗi đã biết của ấn bản 3:** theo hiểu biết của người tổng hợp, không tra cứu, người tổng hợp không nhớ chắc lỗi in nào được công bố cho chương này. Người tổng hợp đã tự kiểm tra lại các bước đại số trong hai phép chứng minh bằng phương pháp thế và thấy đúng. Có hai điểm nhỏ đáng ghi: (1) ở Bài toán 9-2, đề nói "n phần tử phân biệt" nhưng ví dụ minh hoạ có phần tử lặp (0,1 và 0,05 mỗi số xuất hiện hai lần) — kết luận của ví dụ vẫn đúng; (2) ở mục 9.2, bước thay (⌊n/2⌋ − 1)⌊n/2⌋ bằng (n/2 − 2)(n/2 − 1) là một chặn dưới đúng nhưng lỏng hơn cần thiết (chặn chặt hơn là ((n − 3)/2)((n − 1)/2)); điều này không làm sai kết luận.
> - **Hình 9.1 minh hoạ n = 28** (năm nhóm đủ 5 phần tử và một nhóm 3 phần tử): công thức của sách cho chặn dưới 3(⌈½⌈28/5⌉⌉ − 2) = 3 phần tử lớn hơn x, trong khi hình thực tế tô bóng 10 phần tử chắc chắn lớn hơn x. Đây không phải lỗi, chỉ cho thấy chặn dưới 3n/10 − 6 rất lỏng với n nhỏ — đó là lý do phân tích giả định n ≥ 140.
> - **Thay đổi sau 2009 (theo hiểu biết của người tổng hợp, không tra cứu):** ấn bản 4 (2022) giữ ba mục 9.1–9.3 nhưng viết lại phần phân tích: mục 9.2 dùng một lập luận khác (đếm số lần phép chia "có ích", tức là làm kích thước mảng giảm đủ nhiều) thay cho truy hồi và phương pháp thế; mục 9.3 có pseudocode SELECT tường minh, làm việc tại chỗ trên mảng, xử lý trường hợp n không chia hết cho 5 bằng cách loại dần phần tử nhỏ nhất, và truy hồi được viết gọn hơn. Ý tưởng thuật toán (nhóm 5, trung vị của các trung vị) không đổi.

## Sơ đồ

### Phần mở đầu chương (trước mục 9.1, trang 213) — thống kê thứ tự và bài toán chọn

```text
       Thống kê thứ tự thứ i (i-th order statistic) của một tập n phần tử
       là phần tử nhỏ thứ i
       · i = 1: phần tử nhỏ nhất (minimum)
       · i = n: phần tử lớn nhất (maximum)
                                │
                                ▼
       Trung vị (median) là "điểm giữa" của tập
       · n lẻ: duy nhất, ở vị trí i = (n + 1)/2
       · n chẵn: có hai, ở i = n/2 và i = n/2 + 1
       · tổng quát: trung vị dưới ở i = ⌊(n + 1)/2⌋, trung vị trên ở
         i = ⌈(n + 1)/2⌉; sách quy ước "trung vị" là TRUNG VỊ DƯỚI
                                │
                                ▼
       BÀI TOÁN CHỌN (selection problem)
       · đầu vào: tập A gồm n số phân biệt và số nguyên i, 1 ≤ i ≤ n
       · đầu ra: phần tử x ∈ A lớn hơn đúng i − 1 phần tử khác của A
       · giả định các số phân biệt cho tiện; hầu hết kết quả vẫn đúng khi
         có giá trị lặp
                                │
                                ▼
       Cách hiển nhiên: sắp xếp (heapsort, merge sort) rồi lấy phần tử
       thứ i, mất O(n lg n). Chương này đưa ra thuật toán nhanh hơn:
       · 9.1: tìm nhỏ nhất và lớn nhất
       · 9.2: thuật toán ngẫu nhiên, thời gian KỲ VỌNG O(n)
       · 9.3: thuật toán tất định, thời gian XẤU NHẤT O(n)
```

### Mục 9.1 — Nhỏ nhất và lớn nhất (Minimum and maximum, trang 214–215)

```text
       Tìm phần tử nhỏ nhất: MINIMUM duyệt mảng một lần, giữ phần tử nhỏ
       nhất đã thấy → dùng n − 1 phép so sánh (cận trên)
                                │
                                ▼
       Cận dưới cũng là n − 1: coi thuật toán như một GIẢI ĐẤU
       · mỗi phép so sánh là một trận, phần tử nhỏ hơn thắng
       · mọi phần tử trừ người thắng cuộc phải thua ít nhất một trận
       · có n − 1 người phải thua, nên cần ít nhất n − 1 trận
       ⇒ MINIMUM tối ưu theo số phép so sánh (tương tự cho MAXIMUM)
                                │
                                ▼
       Tìm ĐỒNG THỜI nhỏ nhất và lớn nhất (ví dụ: chương trình đồ hoạ cần
       khoảng giá trị của toạ độ x, y để co dãn dữ liệu cho vừa màn hình)
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       CÁCH ĐƠN GIẢN                    CÁCH XỬ LÝ THEO CẶP
       tìm riêng nhỏ nhất và lớn        lấy hai phần tử một lúc:
       nhất, mỗi việc n − 1 phép        1. so sánh hai phần tử với nhau
       so sánh                          2. phần tử nhỏ hơn so với nhỏ nhất
       · tổng 2n − 2 phép so sánh          hiện tại
       · đã là Θ(n), tối ưu tiệm cận    3. phần tử lớn hơn so với lớn nhất
                                           hiện tại
                                        · 3 phép so sánh cho 2 phần tử
               └────────────────┬────────────────┘
                                ▼
       Khởi tạo tuỳ tính chẵn lẻ của n:
       · n lẻ: nhỏ nhất = lớn nhất = phần tử đầu; xử lý (n − 1)/2 cặp
         → 3⌊n/2⌋ phép so sánh
       · n chẵn: so sánh 2 phần tử đầu để khởi tạo (1 phép), rồi xử lý
         (n − 2)/2 cặp → 1 + 3(n − 2)/2 = 3n/2 − 2 phép so sánh
       ⇒ trong mọi trường hợp: TỐI ĐA 3⌊n/2⌋ phép so sánh
```

### Mục 9.2 — Chọn trong thời gian tuyến tính kỳ vọng (Selection in expected linear time, trang 215–220)

```text
       Bài toán chọn tổng quát có vẻ khó hơn tìm nhỏ nhất, nhưng cả hai đều
       giải được trong Θ(n)
                                │
                                ▼
       RANDOMIZED-SELECT(A, p, r, i): chia để trị, mô phỏng quicksort
       · gọi RANDOMIZED-PARTITION chia A[p..r] quanh một chốt ngẫu nhiên
         A[q]: bên trái ≤ chốt, bên phải > chốt
       · k = q − p + 1 = số phần tử phía thấp, tính cả chốt
       · i = k: chốt là đáp án
       · i < k: đệ quy vào phía thấp A[p..q − 1], vẫn tìm phần tử thứ i
       · i > k: đệ quy vào phía cao A[q + 1..r], tìm phần tử thứ i − k
       · KHÁC quicksort: chỉ đệ quy vào MỘT phía
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       TRƯỜNG HỢP XẤU NHẤT              THỜI GIAN KỲ VỌNG
       Θ(n²), kể cả khi tìm nhỏ         Θ(n) với phần tử phân biệt
       nhất: nếu lần nào chốt cũng      · không có đầu vào cụ thể nào luôn
       là phần tử lớn nhất còn lại,       gây ra trường hợp xấu nhất, vì
       mỗi lần chỉ bớt 1 phần tử,         tính ngẫu nhiên nằm trong thuật
       mỗi lần chia tốn Θ(n)              toán
               └────────────────┬────────────────┘
                                ▼
       PHÂN TÍCH KỲ VỌNG
       1. Biến chỉ báo X_k = I{A[p..q] có đúng k phần tử}; E[X_k] = 1/n
          vì chốt được chọn đều          (9.1)
       2. Chặn trên: giả sử phần tử cần tìm luôn ở phía LỚN hơn (T đơn
          điệu tăng):
          T(n) ≤ Σ_{k=1..n} X_k · T(max(k − 1, n − k)) + O(n)
       3. Lấy kỳ vọng, dùng tính tuyến tính và tính độc lập của X_k với
          thời gian đệ quy:
          E[T(n)] ≤ Σ (1/n) E[T(max(k − 1, n − k))] + O(n)
       4. Mỗi số hạng T(⌈n/2⌉)..T(n − 1) xuất hiện hai lần:
          E[T(n)] ≤ (2/n) Σ_{k=⌊n/2⌋..n−1} E[T(k)] + O(n)
       5. Phương pháp thế với giả thiết E[T(k)] ≤ ck, phần không đệ quy
          ≤ an:
          E[T(n)] ≤ cn − (cn/4 − c/2 − an)
       6. Chọn c > 4a; khi n ≥ 2c/(c − 4a) thì E[T(n)] ≤ cn
       ⇒ E[T(n)] = O(n): mọi thống kê thứ tự, kể cả trung vị, tìm được
         trong thời gian tuyến tính kỳ vọng
```

### Mục 9.3 — Chọn trong thời gian tuyến tính trường hợp xấu nhất (Selection in worst-case linear time, trang 220–224)

```text
       Mục tiêu: thời gian O(n) ngay cả trong trường hợp xấu nhất, bằng
       cách BẢO ĐẢM phép chia luôn khá cân bằng
       · dùng PARTITION tất định của quicksort, sửa để nhận chốt làm tham
         số
                                │
                                ▼
       SELECT tìm phần tử nhỏ thứ i trong n > 1 phần tử phân biệt
       (n = 1 thì trả về phần tử duy nhất):
       1. chia n phần tử thành ⌊n/5⌋ nhóm 5 phần tử và tối đa một nhóm
          gồm n mod 5 phần tử còn lại
       2. sắp xếp chèn từng nhóm (tối đa 5 phần tử), lấy trung vị của mỗi
          nhóm trong ⌈n/5⌉ nhóm
       3. gọi SELECT đệ quy để tìm trung vị x của ⌈n/5⌉ trung vị (số
          trung vị chẵn thì lấy trung vị dưới)
       4. chia mảng quanh x bằng PARTITION đã sửa; k = 1 + số phần tử phía
          thấp (x là phần tử nhỏ thứ k, phía cao có n − k phần tử)
       5. i = k: trả về x; i < k: SELECT đệ quy tìm phần tử thứ i ở phía
          thấp; i > k: tìm phần tử thứ i − k ở phía cao
                                │
                                ▼
       VÌ SAO CHỐT x TỐT
       · ít nhất một nửa số trung vị nhóm ≥ x
       · mỗi nhóm có trung vị > x góp ít nhất 3 phần tử > x (trung vị và
         hai phần tử lớn hơn nó), trừ nhóm chứa x và nhóm thiếu
       · số phần tử > x ít nhất 3(⌈½⌈n/5⌉⌉ − 2) ≥ 3n/10 − 6
       · tương tự, ít nhất 3n/10 − 6 phần tử < x
       ⇒ bước 5 đệ quy trên tối đa 7n/10 + 6 phần tử
                                │
                                ▼
       TRUY HỒI XẤU NHẤT
       · bước 1, 2, 4: O(n); bước 3: T(⌈n/5⌉); bước 5: ≤ T(7n/10 + 6)
       · T(n) ≤ O(1)                                nếu n < 140
         T(n) ≤ T(⌈n/5⌉) + T(7n/10 + 6) + O(n)       nếu n ≥ 140
                                │
                                ▼
       PHƯƠNG PHÁP THẾ với giả thiết T(n) ≤ cn, phần không đệ quy ≤ an:
       T(n) ≤ c⌈n/5⌉ + c(7n/10 + 6) + an ≤ 9cn/10 + 7c + an
            = cn + (−cn/10 + 7c + an)
       · cần −cn/10 + 7c + an ≤ 0, tức c ≥ 10a·n/(n − 70) khi n > 70  (9.2)
       · n ≥ 140 ⇒ n/(n − 70) ≤ 2 ⇒ chọn c ≥ 20a là đủ
       · 140 không có gì đặc biệt: mọi số nguyên > 70 đều dùng được
       ⇒ SELECT chạy trong thời gian TUYẾN TÍNH trường hợp xấu nhất
                                │
                                ▼
       SO VỚI SẮP XẾP: SELECT và RANDOMIZED-SELECT chỉ dùng so sánh, không
       giả định gì về đầu vào, nhưng không bị cận Ω(n lg n) chi phối vì
       không sắp xếp ⇒ "sắp xếp rồi lấy phần tử thứ i" kém hiệu quả về
       tiệm cận
```

### Bài toán cuối chương (Problems 9-1 đến 9-4, trang 224–226)

```text
       9-1  Tìm i số lớn nhất theo thứ tự: so sánh ba cách
            a. sắp xếp cả mảng           → O(n lg n)
            b. hàng đợi ưu tiên + i lần EXTRACT-MAX → O(n + i lg n)
            c. SELECT số lớn thứ i, chia, sắp xếp i số → O(n + i lg i)
                                │
                                ▼
       9-2  Trung vị có trọng số: phần tử x_k với tổng trọng số phía nhỏ
            hơn < 1/2 và phía lớn hơn ≤ 1/2
            · tính trong O(n lg n) bằng sắp xếp, Θ(n) bằng SELECT
            · là lời giải tối ưu cho bài toán đặt bưu điện một chiều;
              hai chiều với khoảng cách Manhattan: tách riêng x và y
                                │
                                ▼
       9-3  Thống kê thứ tự nhỏ: khi i nhỏ so với n, ghép cặp, đệ quy trên
            nửa nhỏ, rồi SELECT trên 2i phần tử
            · U_i(n) = n + O(T(2i) lg(n/i)); i hằng số: n + O(lg n)
                                │
                                ▼
       9-4  Phân tích khác cho RANDOMIZED-SELECT bằng biến chỉ báo
            X_ijk (z_i có được so sánh với z_j khi tìm z_k không)
            · E[X_k] ≤ 4n ⇒ thời gian kỳ vọng O(n)
```

### Ghi chú chương (Chapter notes, trang 227)

```text
       Thuật toán tuyến tính xấu nhất: Blum, Floyd, Pratt, Rivest, Tarjan
       Bản ngẫu nhiên nhanh: Hoare
       Bản ngẫu nhiên cải tiến: Floyd và Rivest — chọn chốt bằng cách đệ quy
       chọn từ một mẫu nhỏ các phần tử
                                │
                                ▼
       Câu hỏi mở: cần CHÍNH XÁC bao nhiêu phép so sánh để tìm trung vị?
       · cận dưới 2n (Bent và John)
       · cận trên 3n (Schönhage, Paterson, Pippenger)
       · Dor và Zwick cải thiện cả hai: cận trên hơi dưới 2,95n, cận dưới
         (2 + ε)n với ε là hằng số dương nhỏ
       · Paterson tổng quan các kết quả này
```

## Ba câu hỏi chương này trả lời

1. **Cần bao nhiêu phép so sánh để tìm phần tử nhỏ nhất, và để tìm cùng lúc nhỏ nhất và lớn nhất?** Tìm nhỏ nhất cần đúng n − 1 phép so sánh: thuật toán MINIMUM đạt con số đó, và không thuật toán nào làm ít hơn vì mỗi phần tử không phải nhỏ nhất phải "thua" ít nhất một lần so sánh. Tìm đồng thời nhỏ nhất và lớn nhất không cần 2n − 2 phép so sánh: xử lý từng cặp (so hai phần tử với nhau, phần tử nhỏ so với nhỏ nhất hiện tại, phần tử lớn so với lớn nhất hiện tại) chỉ tốn 3 phép cho 2 phần tử, tổng cộng tối đa 3⌊n/2⌋ (n lẻ: đúng 3⌊n/2⌋; n chẵn: 3n/2 − 2). Ví dụ n = 100: 148 phép so sánh thay vì 198.
2. **Làm sao chọn phần tử nhỏ thứ i nhanh hơn sắp xếp, nếu chấp nhận ngẫu nhiên?** RANDOMIZED-SELECT chia mảng quanh một chốt ngẫu nhiên như quicksort nhưng chỉ đệ quy vào phía chứa đáp án. Với biến chỉ báo X_k (phía thấp có k phần tử, xác suất 1/n), thời gian kỳ vọng thoả E[T(n)] ≤ (2/n) Σ_{k=⌊n/2⌋}^{n−1} E[T(k)] + O(n), và phương pháp thế cho E[T(n)] ≤ cn với c > 4a khi n ≥ 2c/(c − 4a); vậy E[T(n)] = Θ(n). Trường hợp xấu nhất vẫn là Θ(n²).
3. **Có thể đạt thời gian tuyến tính trong trường hợp xấu nhất không?** Có: SELECT chọn chốt là trung vị của các trung vị nhóm 5. Chốt này lớn hơn ít nhất 3n/10 − 6 phần tử và nhỏ hơn ít nhất 3n/10 − 6 phần tử, nên lần đệ quy sau chỉ xét tối đa 7n/10 + 6 phần tử. Truy hồi T(n) ≤ T(⌈n/5⌉) + T(7n/10 + 6) + O(n) có tổng tỷ lệ 1/5 + 7/10 = 9/10 < 1, nên phương pháp thế với c ≥ 20a và n ≥ 140 cho T(n) ≤ cn. Vì chỉ dùng so sánh mà vẫn tuyến tính, kết quả này cho thấy bài toán chọn thực sự dễ hơn sắp xếp (cận dưới Ω(n lg n)).

## Khái niệm cần biết

- **Thống kê thứ tự (order statistic):** phần tử nhỏ thứ i của một tập. Ví dụ: tập {7, 2, 9, 4, 5} sắp xếp thành 2, 4, 5, 7, 9; thống kê thứ tự thứ 1 là 2, thứ 3 là 5, thứ 5 là 9. Quan trọng vì đây là đại lượng chương này học cách tính mà không cần sắp xếp.
- **Trung vị, trung vị dưới, trung vị trên (median, lower median, upper median):** phần tử ở giữa. Với n = 5 chỉ có một trung vị ở vị trí (5 + 1)/2 = 3. Với tập {2, 4, 5, 7, 9, 11} (n = 6): trung vị dưới ở vị trí ⌊7/2⌋ = 3 là 5, trung vị trên ở ⌈7/2⌉ = 4 là 7. Sách luôn gọi trung vị dưới là "trung vị". Quan trọng vì SELECT dùng quy ước này khi số trung vị nhóm là chẵn.
- **Bài toán chọn (selection problem):** cho tập A gồm n số phân biệt và i (1 ≤ i ≤ n), tìm phần tử lớn hơn đúng i − 1 phần tử khác. Ví dụ: A = {3, 2, 9, 0, 7, 5, 4, 8, 6, 1}, i = 5 → đáp án 4 (lớn hơn đúng 0, 1, 2, 3). Đây là bài toán trung tâm của chương.
- **Cận dưới bằng lập luận giải đấu (tournament argument):** coi mỗi phép so sánh là một trận đấu, phần tử nhỏ hơn thắng. Muốn biết chắc ai nhỏ nhất, mọi phần tử khác phải từng thua; mỗi trận chỉ tạo ra một người thua mới, nên cần ít nhất n − 1 trận. Ví dụ n = 8: ít nhất 7 phép so sánh. Quan trọng vì nó chứng minh MINIMUM là tối ưu chính xác, không chỉ tối ưu tiệm cận.
- **Xử lý theo cặp (processing in pairs):** kỹ thuật tìm đồng thời nhỏ nhất và lớn nhất. Ví dụ A = ⟨5, 2, 9, 1, 7, 3, 8⟩ (n = 7): khởi tạo nhỏ nhất = lớn nhất = 5; cặp (2, 9) tốn 3 phép → nhỏ nhất 2, lớn nhất 9; cặp (1, 7) → nhỏ nhất 1; cặp (3, 8) không đổi gì; tổng 9 = 3⌊7/2⌋ phép so sánh thay vì 2·7 − 2 = 12.
- **Phần tử chốt (pivot) và phép chia (partition):** chia mảng A[p..r] thành A[p..q − 1] (các phần tử ≤ chốt), chốt A[q], và A[q + 1..r] (các phần tử > chốt), trong thời gian tuyến tính. Ví dụ: chia ⟨3, 2, 9, 0, 7, 1, 4, 8, 6, 5⟩ quanh chốt 5 cho ⟨3, 2, 0, 1, 4, 5, 7, 8, 6, 9⟩ với q = 6. Quan trọng vì cả hai thuật toán chọn đều dựa trên nó.
- **Hạng của chốt k (rank of the pivot):** k = q − p + 1, số phần tử của A[p..q], tức chốt là phần tử nhỏ thứ k của mảng con. Trong ví dụ trên k = 6. So i với k quyết định trả về chốt hay đệ quy sang phía nào.
- **Thuật toán ngẫu nhiên (randomized algorithm):** thuật toán có hành vi phụ thuộc một phần vào bộ sinh số ngẫu nhiên. Với RANDOMIZED-SELECT, không có đầu vào cụ thể nào luôn gây ra trường hợp xấu nhất; thời gian là biến ngẫu nhiên và ta phân tích kỳ vọng của nó.
- **Biến ngẫu nhiên chỉ báo (indicator random variable):** I{sự kiện} bằng 1 nếu sự kiện xảy ra, 0 nếu không; kỳ vọng của nó bằng xác suất của sự kiện. Ví dụ: X_3 = I{phía thấp tính cả chốt có đúng 3 phần tử}; vì chốt chọn đều trong n phần tử, E[X_3] = 1/n. Quan trọng vì nó biến truy hồi ngẫu nhiên thành tổng có trọng số dễ lấy kỳ vọng.
- **Tính tuyến tính của kỳ vọng (linearity of expectation) và tích của biến độc lập:** E[ΣY_k] = ΣE[Y_k] luôn đúng; E[XY] = E[X]·E[Y] khi X, Y độc lập (công thức (C.24) của Phụ lục C). Phân tích mục 9.2 dùng cả hai.
- **Trung vị của các trung vị (median-of-medians):** chốt của SELECT. Ví dụ với 15 phần tử ⟨12, 3, 25, 7, 18, 1, 30, 14, 9, 21, 6, 27, 16, 2, 11⟩: ba nhóm có trung vị 12, 14, 11; trung vị của ba số này là 12. Quan trọng vì nó bảo đảm mỗi phía của phép chia có ít nhất khoảng 3n/10 phần tử.
- **Phương pháp thế (substitution method):** đoán dạng nghiệm (ở đây T(n) ≤ cn), thay vào vế phải của truy hồi và chứng minh bằng quy nạp. Ví dụ trong mục 9.3: thay vào cho T(n) ≤ cn + (−cn/10 + 7c + an), và chọn c ≥ 20a để phần trong ngoặc ≤ 0 khi n ≥ 140.
- **Mô hình so sánh (comparison model):** thuật toán chỉ biết thứ tự giữa các phần tử qua phép so sánh. Sắp xếp trong mô hình này cần Ω(n lg n); chọn thì chỉ cần Θ(n). Quan trọng vì đây là thông điệp chính của chương.
- **Trung vị có trọng số (weighted median) — Bài toán 9-2:** phần tử x_k mà tổng trọng số các phần tử nhỏ hơn < 1/2 và tổng trọng số các phần tử lớn hơn ≤ 1/2. Ví dụ: với các phần tử 0,1; 0,35; 0,05; 0,1; 0,15; 0,05; 0,2 mà trọng số bằng chính giá trị, trung vị thường là 0,1 còn trung vị có trọng số là 0,2 (phía nhỏ hơn: 0,05 + 0,05 + 0,1 + 0,1 + 0,15 = 0,45 < 0,5; phía lớn hơn: 0,35 ≤ 0,5).
- **Phân vị bậc k (k-th quantiles) — Bài tập 9.3-6:** k − 1 thống kê thứ tự chia tập đã sắp xếp thành k phần bằng nhau (chênh nhau tối đa 1). Ví dụ với 12 phần tử và k = 4: các thống kê thứ 3, 6, 9.

## Nội dung chi tiết

### 1. Thống kê thứ tự và bài toán chọn (phần mở đầu chương, trang 213)

Thống kê thứ tự thứ i của một tập n phần tử là phần tử nhỏ thứ i. Phần tử nhỏ nhất là thống kê thứ tự thứ nhất (i = 1), phần tử lớn nhất là thống kê thứ tự thứ n (i = n). Trung vị, nói không chặt chẽ, là "điểm giữa" của tập. Khi n lẻ, trung vị là duy nhất, ở vị trí i = (n + 1)/2. Khi n chẵn, có hai trung vị, ở i = n/2 và i = n/2 + 1. Gộp cả hai trường hợp: trung vị nằm ở i = ⌊(n + 1)/2⌋ (**trung vị dưới**) và i = ⌈(n + 1)/2⌉ (**trung vị trên**); khi n lẻ hai vị trí này trùng nhau. Để đơn giản, trong toàn bộ sách cụm từ "trung vị" luôn chỉ trung vị dưới.

Kiểm tra bằng số: n = 7 → ⌊8/2⌋ = ⌈8/2⌉ = 4, một trung vị duy nhất ở vị trí 4. n = 8 → ⌊9/2⌋ = 4 và ⌈9/2⌉ = 5, hai trung vị ở vị trí 4 và 5, khớp với n/2 và n/2 + 1.

Chương xét bài toán chọn thống kê thứ tự thứ i trong một tập n số **phân biệt**. Giả định phân biệt chỉ để tiện; gần như mọi điều trong chương mở rộng được cho tập có giá trị lặp. Phát biểu hình thức:

- **Đầu vào:** một tập A gồm n số (phân biệt) và một số nguyên i, với 1 ≤ i ≤ n.
- **Đầu ra:** phần tử x ∈ A lớn hơn đúng i − 1 phần tử khác của A.

Bài toán giải được trong O(n lg n): sắp xếp các số bằng heapsort hoặc merge sort rồi lấy phần tử thứ i của mảng kết quả. Chương này trình bày các thuật toán nhanh hơn. Mục 9.1 xét bài toán tìm nhỏ nhất và lớn nhất. Hai mục sau xét bài toán chọn tổng quát, thú vị hơn: mục 9.2 phân tích một thuật toán ngẫu nhiên thực dụng đạt thời gian chạy kỳ vọng O(n) (với phần tử phân biệt); mục 9.3 trình bày một thuật toán có ý nghĩa lý thuyết hơn, đạt O(n) ngay cả trong trường hợp xấu nhất.

#### Ví dụ hôm nay

Thống kê thứ tự xuất hiện khắp nơi trong xử lý dữ liệu: trung vị thu nhập, phân vị thứ 95 hoặc 99 của độ trễ phản hồi trong giám sát hệ thống, ngưỡng "top k" trong xếp hạng. Các hệ cơ sở dữ liệu và thư viện phân tích dữ liệu tính trung vị và phân vị theo yêu cầu; nhiều thư viện chuẩn cung cấp sẵn thao tác "chọn phần tử thứ n" chạy trong thời gian tuyến tính trung bình thay vì bắt người dùng sắp xếp cả mảng.

### 2. Nhỏ nhất và lớn nhất (Minimum and maximum, mục 9.1, trang 214–215)

#### Tìm phần tử nhỏ nhất với n − 1 phép so sánh

Cần bao nhiêu phép so sánh để xác định phần tử nhỏ nhất trong n phần tử? Một cận trên n − 1 có ngay: xét lần lượt từng phần tử và luôn ghi nhớ phần tử nhỏ nhất đã thấy. Thủ tục dưới đây giả định tập nằm trong mảng A với A.length = n.

```text
MINIMUM(A)
1  min = A[1]
2  for i = 2 to A.length
3      if min > A[i]
4          min = A[i]
5  return min
```

Dòng 1 lấy phần tử đầu làm ứng viên. Vòng lặp dòng 2–4 chạy n − 1 lần, mỗi lần đúng một phép so sánh ở dòng 3; nếu A[i] nhỏ hơn ứng viên hiện tại thì dòng 4 thay ứng viên. Dòng 5 trả về kết quả. Bất biến vòng lặp: trước mỗi lần lặp với chỉ số i, biến min chứa phần tử nhỏ nhất của A[1..i − 1]. Tìm lớn nhất cũng tốn n − 1 phép so sánh theo cùng cách.

Ví dụ: A = ⟨5, 2, 9, 1, 7⟩. min = 5; i = 2: 5 > 2 → min = 2; i = 3: 2 > 9 sai; i = 4: 2 > 1 → min = 1; i = 5: 1 > 7 sai. Trả về 1 sau 4 = n − 1 phép so sánh.

#### Cận dưới n − 1

Có làm tốt hơn được không? Không, vì có cận dưới n − 1 phép so sánh cho bài toán tìm nhỏ nhất. Hãy coi mọi thuật toán tìm nhỏ nhất như một giải đấu giữa các phần tử: mỗi phép so sánh là một trận, phần tử nhỏ hơn thắng. Mọi phần tử trừ người thắng cuộc chung cuộc phải thua ít nhất một trận (nếu một phần tử chưa từng thua, thuật toán không thể loại trừ khả năng nó là nhỏ nhất). Có n − 1 phần tử phải thua, mỗi trận tạo ra tối đa một người thua, nên cần ít nhất n − 1 phép so sánh. Do đó MINIMUM tối ưu theo số phép so sánh.

#### Đồng thời nhỏ nhất và lớn nhất (Simultaneous minimum and maximum)

Có những ứng dụng cần cả nhỏ nhất và lớn nhất của n phần tử. Ví dụ, một chương trình đồ hoạ cần co dãn một tập điểm (x, y) cho vừa màn hình chữ nhật hoặc thiết bị xuất đồ hoạ khác; muốn vậy, nó phải biết giá trị nhỏ nhất và lớn nhất của mỗi toạ độ.

Cách hiển nhiên dùng Θ(n) phép so sánh, vốn đã tối ưu về tiệm cận: tìm riêng nhỏ nhất và lớn nhất, mỗi việc n − 1 phép, tổng 2n − 2.

Thực ra chỉ cần **tối đa 3⌊n/2⌋** phép so sánh. Ta vẫn duy trì cả nhỏ nhất và lớn nhất đã thấy, nhưng thay vì đem từng phần tử so với cả hai (2 phép mỗi phần tử), ta xử lý **từng cặp**: so hai phần tử của cặp với nhau trước, rồi so phần tử nhỏ hơn với nhỏ nhất hiện tại và phần tử lớn hơn với lớn nhất hiện tại. Như vậy tốn 3 phép cho mỗi 2 phần tử. Lý do hiệu quả: phần tử lớn hơn của cặp không thể là nhỏ nhất, phần tử nhỏ hơn không thể là lớn nhất, nên mỗi phần tử chỉ cần so với một trong hai giá trị hiện tại.

Cách khởi tạo phụ thuộc tính chẵn lẻ của n:

- **n lẻ:** đặt cả nhỏ nhất và lớn nhất bằng phần tử đầu tiên, rồi xử lý các phần tử còn lại theo cặp. Có (n − 1)/2 = ⌊n/2⌋ cặp, tổng 3⌊n/2⌋ phép so sánh.
- **n chẵn:** so sánh 2 phần tử đầu (1 phép) để có giá trị khởi tạo của nhỏ nhất và lớn nhất, rồi xử lý (n − 2)/2 cặp còn lại. Tổng 1 + 3(n − 2)/2 = 3n/2 − 2 phép so sánh.

Trong cả hai trường hợp, số phép so sánh không vượt 3⌊n/2⌋.

**Ví dụ chạy tay, n chẵn.** A = ⟨4, 5, 2, 9, 1, 7, 3, 8⟩ (n = 8).

| Bước | Thao tác | Số phép so sánh | Nhỏ nhất | Lớn nhất |
|---|---|---|---|---|
| Khởi tạo | so 4 với 5 | 1 | 4 | 5 |
| Cặp (2, 9) | 2 < 9; 2 < 4; 9 > 5 | 3 | 2 | 9 |
| Cặp (1, 7) | 1 < 7; 1 < 2; 7 > 9 sai | 3 | 1 | 9 |
| Cặp (3, 8) | 3 < 8; 3 < 1 sai; 8 > 9 sai | 3 | 1 | 9 |
| Tổng | | 10 | | |

10 = 3·8/2 − 2, so với 2·8 − 2 = 14 của cách đơn giản. (Bài tập 9.1-2 cho thấy ⌈3n/2⌉ − 2 cũng là cận dưới, nên cách xử lý theo cặp tối ưu chính xác.)

#### Ví dụ hôm nay

Kỹ thuật xử lý theo cặp vẫn có trong một số thư viện chuẩn: chẳng hạn hàm tìm đồng thời nhỏ nhất và lớn nhất của thư viện chuẩn C++ được đặc tả với số phép so sánh tối đa khoảng 3n/2 (theo hiểu biết của người tổng hợp). Trên phần cứng hiện đại, khi dữ liệu là số nguyên hoặc số thực, chi phí thật thường nằm ở việc đọc bộ nhớ và rẽ nhánh hơn là ở số phép so sánh; trình biên dịch có thể vector hoá vòng lặp đơn giản thành lệnh SIMD tính min/max song song, nên ưu thế của cách theo cặp rõ nhất khi phép so sánh đắt (so sánh chuỗi, đối tượng phức tạp).

### 3. Chọn trong thời gian tuyến tính kỳ vọng (Selection in expected linear time, mục 9.2, trang 215–220)

Bài toán chọn tổng quát có vẻ khó hơn bài toán tìm nhỏ nhất, nhưng điều đáng ngạc nhiên là thời gian chạy tiệm cận của hai bài toán như nhau: Θ(n). Mục này trình bày một thuật toán chia để trị, RANDOMIZED-SELECT, mô phỏng quicksort của Chương 7. Như quicksort, nó chia mảng đầu vào một cách đệ quy. Khác quicksort — vốn xử lý đệ quy cả hai phía của phép chia — RANDOMIZED-SELECT chỉ làm việc trên **một** phía. Khác biệt này thể hiện trong phân tích: quicksort có thời gian kỳ vọng Θ(n lg n), còn RANDOMIZED-SELECT có thời gian kỳ vọng Θ(n), với giả định phần tử phân biệt.

#### Các thủ tục chia mượn từ Chương 7

RANDOMIZED-SELECT dùng thủ tục RANDOMIZED-PARTITION của mục 7.3, nên giống RANDOMIZED-QUICKSORT, nó là thuật toán ngẫu nhiên: hành vi phụ thuộc một phần vào đầu ra của bộ sinh số ngẫu nhiên. Để bản tổng hợp tự chứa, đây là hai thủ tục của Chương 7 (chép từ mục 7.1 và 7.3):

```text
PARTITION(A, p, r)
1  x = A[r]
2  i = p − 1
3  for j = p to r − 1
4      if A[j] ≤ x
5          i = i + 1
6          exchange A[i] with A[j]
7  exchange A[i + 1] with A[r]
8  return i + 1

RANDOMIZED-PARTITION(A, p, r)
1  i = RANDOM(p, r)
2  exchange A[r] with A[i]
3  return PARTITION(A, p, r)
```

PARTITION lấy phần tử cuối A[r] làm chốt x, duy trì vùng A[p..i] gồm các phần tử ≤ x và vùng A[i + 1..j − 1] gồm các phần tử > x; cuối cùng đưa chốt vào vị trí i + 1 và trả về vị trí đó. Thời gian Θ(n) với n = r − p + 1. RANDOMIZED-PARTITION trước đó đổi chỗ A[r] với một phần tử chọn ngẫu nhiên đều trong A[p..r], nên mọi phần tử có cùng xác suất trở thành chốt.

#### Thủ tục RANDOMIZED-SELECT

Thủ tục sau trả về phần tử nhỏ thứ i của mảng A[p..r].

```text
RANDOMIZED-SELECT(A, p, r, i)
1  if p == r
2      return A[p]
3  q = RANDOMIZED-PARTITION(A, p, r)
4  k = q − p + 1
5  if i == k          // the pivot value is the answer
6      return A[q]
7  elseif i < k
8      return RANDOMIZED-SELECT(A, p, q − 1, i)
9  else return RANDOMIZED-SELECT(A, q + 1, r, i − k)
```

Giải thích từng dòng:

- **Dòng 1–2:** trường hợp cơ sở, mảng con A[p..r] chỉ có một phần tử. Khi đó i bắt buộc bằng 1, và A[p] là phần tử nhỏ thứ i.
- **Dòng 3:** chia A[p..r] thành hai mảng con (có thể rỗng) A[p..q − 1] và A[q + 1..r] sao cho mọi phần tử của A[p..q − 1] nhỏ hơn hoặc bằng A[q], và A[q] nhỏ hơn mọi phần tử của A[q + 1..r]. A[q] gọi là **phần tử chốt** (pivot).
- **Dòng 4:** k là số phần tử của A[p..q], tức số phần tử phía thấp cộng một (cho chốt). Nói cách khác, chốt là phần tử nhỏ thứ k của A[p..r].
- **Dòng 5–6:** nếu i = k thì chốt chính là đáp án.
- **Dòng 7–8:** nếu i < k, phần tử cần tìm nằm ở phía thấp; đệ quy tìm phần tử nhỏ thứ i trong A[p..q − 1].
- **Dòng 9:** nếu i > k, phần tử cần tìm nằm ở phía cao. Ta đã biết k phần tử nhỏ hơn nó (toàn bộ A[p..q]), nên nó là phần tử nhỏ thứ i − k của A[q + 1..r].

Mã có vẻ cho phép gọi đệ quy trên mảng con rỗng, nhưng Bài tập 9.2-1 yêu cầu chứng minh điều đó không xảy ra. (Lý do: đệ quy vào phía thấp chỉ khi i < k, mà phía thấp rỗng nghĩa là k = 1, không thể có i < 1; đệ quy vào phía cao chỉ khi i > k, mà phía cao rỗng nghĩa là k = n, không thể có i > n.)

**Ví dụ chạy tay.** Tìm phần tử nhỏ thứ i = 5 trong A[1..10] = ⟨3, 2, 9, 0, 7, 5, 4, 8, 6, 1⟩ (đáp án đúng là 4, vì mảng sắp xếp là 0, 1, …, 9). Chốt là ngẫu nhiên; ở đây ta giả sử một dãy lựa chọn cụ thể.

*Lần gọi 1:* RANDOMIZED-SELECT(A, 1, 10, 5). Giả sử RANDOM(1, 10) trả về 6 (giá trị 5). Đổi A[10] với A[6]: ⟨3, 2, 9, 0, 7, 1, 4, 8, 6, 5⟩. PARTITION với x = 5, i = 0:

| j | A[j] | A[j] ≤ 5? | i sau bước | Mảng sau bước |
|---|---|---|---|---|
| 1 | 3 | có | 1 | 3, 2, 9, 0, 7, 1, 4, 8, 6, 5 |
| 2 | 2 | có | 2 | 3, 2, 9, 0, 7, 1, 4, 8, 6, 5 |
| 3 | 9 | không | 2 | 3, 2, 9, 0, 7, 1, 4, 8, 6, 5 |
| 4 | 0 | có | 3 (đổi A[3], A[4]) | 3, 2, 0, 9, 7, 1, 4, 8, 6, 5 |
| 5 | 7 | không | 3 | 3, 2, 0, 9, 7, 1, 4, 8, 6, 5 |
| 6 | 1 | có | 4 (đổi A[4], A[6]) | 3, 2, 0, 1, 7, 9, 4, 8, 6, 5 |
| 7 | 4 | có | 5 (đổi A[5], A[7]) | 3, 2, 0, 1, 4, 9, 7, 8, 6, 5 |
| 8 | 8 | không | 5 | không đổi |
| 9 | 6 | không | 5 | không đổi |

Dòng 7 của PARTITION đổi A[6] với A[10]: ⟨3, 2, 0, 1, 4, **5**, 7, 8, 6, 9⟩, q = 6. k = 6 − 1 + 1 = 6. Vì i = 5 < 6, gọi đệ quy trên A[1..5] = ⟨3, 2, 0, 1, 4⟩ với i = 5.

*Lần gọi 2:* RANDOMIZED-SELECT(A, 1, 5, 5). Giả sử RANDOM(1, 5) trả về 2 (giá trị 2). Đổi A[5] với A[2]: ⟨3, 4, 0, 1, 2⟩. PARTITION với x = 2: j = 1 (3, không), j = 2 (4, không), j = 3 (0, có → i = 1, đổi A[1] với A[3]: ⟨0, 4, 3, 1, 2⟩), j = 4 (1, có → i = 2, đổi A[2] với A[4]: ⟨0, 1, 3, 4, 2⟩). Đổi A[3] với A[5]: ⟨0, 1, **2**, 4, 3⟩, q = 3, k = 3. Vì i = 5 > 3, gọi đệ quy trên A[4..5] = ⟨4, 3⟩ với i = 5 − 3 = 2.

*Lần gọi 3:* RANDOMIZED-SELECT(A, 4, 5, 2). Giả sử RANDOM(4, 5) trả về 4 (giá trị 4). Đổi A[5] với A[4]: ⟨3, 4⟩ ở vị trí 4–5. PARTITION với x = 4: j = 4 (3 ≤ 4 → i = 4). Đổi A[5] với chính nó; q = 5. k = 5 − 4 + 1 = 2 = i → trả về A[5] = 4. Đúng đáp án.

#### Trường hợp xấu nhất

Thời gian xấu nhất của RANDOMIZED-SELECT là Θ(n²), kể cả khi chỉ tìm phần tử nhỏ nhất: nếu cực kỳ xui, lần nào chốt cũng là phần tử lớn nhất còn lại, mỗi lần chia chỉ loại được một phần tử mà tốn Θ(n), tổng (n − 1) + (n − 2) + … = Θ(n²). (Bài tập 9.2-4 yêu cầu mô tả chuỗi phép chia như vậy khi tìm nhỏ nhất của ⟨3, 2, 9, 0, 7, 5, 4, 8, 6, 1⟩: chốt lần lượt là 9, 8, 7, 6, 5, 4, 3, 2, 1.) Tuy nhiên thuật toán có thời gian kỳ vọng tuyến tính, và vì nó ngẫu nhiên, không đầu vào cụ thể nào luôn gây ra hành vi xấu nhất.

#### Phân tích thời gian kỳ vọng

Gọi T(n) là thời gian chạy trên mảng A[p..r] gồm n phần tử; T(n) là một biến ngẫu nhiên, và ta tìm chặn trên cho E[T(n)].

**Bước 1 — biến chỉ báo.** RANDOMIZED-PARTITION trả về mỗi phần tử làm chốt với xác suất như nhau. Vậy với mỗi k thoả 1 ≤ k ≤ n, mảng con A[p..q] có k phần tử (tất cả ≤ chốt) với xác suất 1/n. Với k = 1, 2, …, n, định nghĩa

  X_k = I{mảng con A[p..q] có đúng k phần tử},

và với giả định phần tử phân biệt:

  E[X_k] = 1/n.  (9.1)

**Bước 2 — truy hồi chặn trên.** Khi gọi RANDOMIZED-SELECT và chọn A[q] làm chốt, ta không biết trước sẽ dừng ngay với đáp án, đệ quy vào A[p..q − 1], hay đệ quy vào A[q + 1..r]; điều đó tuỳ phần tử thứ i nằm ở đâu so với A[q]. Giả sử T(n) đơn điệu tăng, ta chặn thời gian của lời gọi đệ quy bằng thời gian của lời gọi trên đầu vào lớn nhất có thể; tức là, để có chặn trên, giả sử phần tử thứ i luôn ở phía có nhiều phần tử hơn. Trong một lần gọi, đúng một X_k bằng 1, các X_k khác bằng 0. Khi X_k = 1, hai mảng con có thể đệ quy có kích thước k − 1 và n − k. Do đó

  T(n) ≤ Σ_{k=1}^{n} X_k · (T(max(k − 1, n − k)) + O(n))
     = Σ_{k=1}^{n} X_k · T(max(k − 1, n − k)) + O(n).

(Đẳng thức thứ hai đúng vì Σ X_k = 1.)

**Bước 3 — lấy kỳ vọng.**

  E[T(n)] ≤ E[ Σ_{k=1}^{n} X_k · T(max(k − 1, n − k)) + O(n) ]
      = Σ_{k=1}^{n} E[X_k · T(max(k − 1, n − k))] + O(n)  (tính tuyến tính của kỳ vọng)
      = Σ_{k=1}^{n} E[X_k] · E[T(max(k − 1, n − k))] + O(n)  (công thức (C.24))
      = Σ_{k=1}^{n} (1/n) · E[T(max(k − 1, n − k))] + O(n)  (công thức (9.1)).

Công thức (C.24) của Phụ lục C phát biểu rằng kỳ vọng của tích các biến ngẫu nhiên độc lập bằng tích các kỳ vọng. Để áp dụng nó, ta dựa vào việc X_k và T(max(k − 1, n − k)) là hai biến ngẫu nhiên độc lập — Bài tập 9.2-2 yêu cầu giải thích vì sao (ý chính: thời gian của lời gọi đệ quy trên một mảng có kích thước cố định chỉ phụ thuộc các lựa chọn ngẫu nhiên trong lời gọi đó, độc lập với lựa chọn chốt ở mức hiện tại).

**Bước 4 — đếm số hạng.** Ta có

  max(k − 1, n − k) = k − 1 nếu k > ⌈n/2⌉,
  max(k − 1, n − k) = n − k nếu k ≤ ⌈n/2⌉.

Nếu n chẵn, mỗi số hạng từ T(⌈n/2⌉) đến T(n − 1) xuất hiện đúng hai lần trong tổng; nếu n lẻ, các số hạng này cũng xuất hiện hai lần và T(⌊n/2⌋) xuất hiện một lần. Ví dụ n = 6: k = 1..6 cho max lần lượt 5, 4, 3, 3, 4, 5 — mỗi giá trị 3, 4, 5 hai lần. n = 5: k = 1..5 cho 4, 3, 2, 3, 4 — giá trị 3, 4 hai lần, giá trị 2 = ⌊5/2⌋ một lần. Vì vậy

  E[T(n)] ≤ (2/n) Σ_{k=⌊n/2⌋}^{n−1} E[T(k)] + O(n).

**Bước 5 — phương pháp thế.** Ta chứng minh E[T(n)] = O(n). Giả sử E[T(n)] ≤ cn với một hằng số c thoả các điều kiện ban đầu của truy hồi, và giả sử T(n) = O(1) khi n nhỏ hơn một hằng số sẽ chọn sau. Chọn thêm hằng số a sao cho hàm ứng với số hạng O(n) ở trên (phần không đệ quy của thời gian chạy) bị chặn trên bởi an với mọi n > 0. Dùng giả thiết quy nạp:

  E[T(n)] ≤ (2/n) Σ_{k=⌊n/2⌋}^{n−1} ck + an
      = (2c/n) ( Σ_{k=1}^{n−1} k − Σ_{k=1}^{⌊n/2⌋−1} k ) + an
      = (2c/n) ( (n − 1)n/2 − (⌊n/2⌋ − 1)⌊n/2⌋/2 ) + an
      ≤ (2c/n) ( (n − 1)n/2 − (n/2 − 2)(n/2 − 1)/2 ) + an
      = (2c/n) ( (n² − n)/2 − (n²/4 − 3n/2 + 2)/2 ) + an
      = (c/n) ( 3n²/4 + n/2 − 2 ) + an
      = c ( 3n/4 + 1/2 − 2/n ) + an
      ≤ 3cn/4 + c/2 + an
      = cn − ( cn/4 − c/2 − an ).

Giải thích các bước: dòng 2 viết tổng từ ⌊n/2⌋ đến n − 1 thành hiệu hai tổng bắt đầu từ 1; dòng 3 dùng công thức tổng cấp số cộng Σ_{k=1}^{m} k = m(m + 1)/2; dòng 4 dùng ⌊n/2⌋ ≥ n/2 − 1 nên (⌊n/2⌋ − 1)⌊n/2⌋ ≥ (n/2 − 2)(n/2 − 1) — trừ đi một số nhỏ hơn làm vế phải lớn hơn, nên dấu ≤; dòng 5 khai triển (n/2 − 2)(n/2 − 1) = n²/4 − 3n/2 + 2; dòng 6: (n² − n)/2 − (n²/4 − 3n/2 + 2)/2 = (3n²/4 + n/2 − 2)/2, nhân với 2c/n; dòng 8 bỏ số hạng âm −2c/n.

**Bước 6 — chọn hằng số.** Cần chứng minh với n đủ lớn biểu thức cuối không vượt cn, tức cn/4 − c/2 − an ≥ 0. Cộng c/2 vào hai vế và đặt n làm thừa số chung: n(c/4 − a) ≥ c/2. Nếu chọn c sao cho c/4 − a > 0, tức c > 4a, thì chia hai vế cho c/4 − a:

  n ≥ (c/2)/(c/4 − a) = 2c/(c − 4a).

Vậy nếu giả sử T(n) = O(1) với n < 2c/(c − 4a), thì E[T(n)] = O(n). Ví dụ bằng số: với a = 1 và c = 8, cần n ≥ 16/4 = 4; kiểm tra n = 4: cn/4 − c/2 − an = 8 − 4 − 4 = 0 ≥ 0, đúng.

**Kết luận:** ta tìm được mọi thống kê thứ tự, đặc biệt là trung vị, trong thời gian tuyến tính kỳ vọng, với giả định các phần tử phân biệt.

#### Ví dụ hôm nay

Ý tưởng "chia như quicksort nhưng chỉ đi một phía" (thường gọi là quickselect, do Hoare đề xuất) là thuật toán chọn được dùng nhiều nhất trong thực tế. Thao tác "chọn phần tử thứ n" của thư viện chuẩn C++ và hàm phân vùng một phần của thư viện mảng số trong Python được cài đặt bằng các biến thể của nó, thường kết hợp chọn chốt bằng trung vị của vài phần tử và chuyển sang thuật toán có bảo đảm xấu nhất khi đệ quy quá sâu (kiểu "introselect", theo hiểu biết của người tổng hợp). Thuật toán cũng là nền của bài toán "k phần tử lớn nhất" trong phỏng vấn lập trình.

### 4. Chọn trong thời gian tuyến tính trường hợp xấu nhất (Selection in worst-case linear time, mục 9.3, trang 220–224)

#### Thuật toán SELECT

Mục này xét một thuật toán chọn có thời gian O(n) trong trường hợp xấu nhất. Như RANDOMIZED-SELECT, thuật toán SELECT tìm phần tử cần tìm bằng cách chia mảng đầu vào một cách đệ quy. Nhưng ở đây ta **bảo đảm** phép chia tốt. SELECT dùng thuật toán chia tất định PARTITION của quicksort (mục 7.1, đã chép ở phần 3 trên), được sửa để nhận phần tử chốt làm tham số đầu vào (thay vì luôn lấy A[r]; ví dụ, tìm vị trí của chốt rồi đổi nó về cuối trước khi chạy PARTITION như cũ).

SELECT xác định phần tử nhỏ thứ i của một mảng n > 1 phần tử phân biệt qua các bước sau (nếu n = 1, SELECT chỉ trả về giá trị duy nhất):

1. Chia n phần tử của mảng thành ⌊n/5⌋ nhóm, mỗi nhóm 5 phần tử, và tối đa một nhóm gồm n mod 5 phần tử còn lại.
2. Tìm trung vị của mỗi nhóm trong ⌈n/5⌉ nhóm: sắp xếp chèn các phần tử của nhóm (tối đa 5 phần tử) rồi lấy trung vị từ danh sách đã sắp.
3. Dùng SELECT đệ quy để tìm trung vị x của ⌈n/5⌉ trung vị tìm được ở bước 2. (Nếu số trung vị là chẵn thì theo quy ước, x là trung vị dưới.)
4. Chia mảng đầu vào quanh trung vị của các trung vị x bằng PARTITION đã sửa. Đặt k bằng số phần tử phía thấp cộng một, để x là phần tử nhỏ thứ k và phía cao có n − k phần tử.
5. Nếu i = k, trả về x. Ngược lại, dùng SELECT đệ quy để tìm phần tử nhỏ thứ i ở phía thấp nếu i < k, hoặc phần tử nhỏ thứ i − k ở phía cao nếu i > k.

(Ấn bản 3 chỉ mô tả SELECT bằng lời như trên, không có pseudocode.)

**Ví dụ chạy tay.** A = ⟨12, 3, 25, 7, 18, 1, 30, 14, 9, 21, 6, 27, 16, 2, 11⟩ (n = 15), tìm i = 4. Mảng đã sắp xếp: 1, 2, 3, 6, 7, 9, 11, 12, 14, 16, 18, 21, 25, 27, 30, nên đáp án đúng là 6.

*Mức 1 (n = 15, i = 4).*
- Bước 1: ba nhóm ⟨12, 3, 25, 7, 18⟩, ⟨1, 30, 14, 9, 21⟩, ⟨6, 27, 16, 2, 11⟩.
- Bước 2: sắp xếp từng nhóm: 3, 7, **12**, 18, 25 → trung vị 12; 1, 9, **14**, 21, 30 → 14; 2, 6, **11**, 16, 27 → 11.
- Bước 3: SELECT đệ quy trên ⟨12, 14, 11⟩ tìm trung vị (i = 2) → x = 12.
- Bước 4: chia quanh 12: phía thấp {3, 7, 1, 9, 6, 2, 11} (7 phần tử), phía cao {25, 18, 30, 14, 21, 27, 16} (7 phần tử). k = 8.
- Bước 5: i = 4 < 8 → đệ quy tìm phần tử nhỏ thứ 4 trong 7 phần tử phía thấp.

*Mức 2 (n = 7, i = 4), mảng ⟨3, 7, 1, 9, 6, 2, 11⟩.*
- Nhóm ⟨3, 7, 1, 9, 6⟩ sắp thành 1, 3, **6**, 7, 9 → trung vị 6; nhóm ⟨2, 11⟩ → trung vị dưới 2.
- Trung vị dưới của ⟨6, 2⟩ là x = 2.
- Chia quanh 2: phía thấp {1}, phía cao {3, 7, 9, 6, 11}; k = 2.
- i = 4 > 2 → tìm phần tử nhỏ thứ 4 − 2 = 2 ở phía cao.

*Mức 3 (n = 5, i = 2), mảng ⟨3, 7, 9, 6, 11⟩.*
- Một nhóm, sắp thành 3, 6, **7**, 9, 11 → trung vị 7; trung vị của các trung vị x = 7.
- Chia quanh 7: phía thấp {3, 6}, phía cao {9, 11}; k = 3.
- i = 2 < 3 → tìm phần tử nhỏ thứ 2 trong {3, 6}.

*Mức 4 (n = 2, i = 2):* trung vị dưới của nhóm ⟨3, 6⟩ là 3; x = 3, phía thấp rỗng, k = 1; i = 2 > 1 → tìm phần tử nhỏ thứ 1 trong {6}. *Mức 5 (n = 1):* trả về 6. Đúng đáp án.

Ví dụ cũng cho thấy với n rất nhỏ, chốt có thể lệch (ở mức 2, x = 2 chỉ loại được 2 phần tử); bảo đảm "ít nhất 3n/10 − 6 phần tử mỗi phía" chỉ có ý nghĩa khi n đủ lớn.

#### Chặn số phần tử lớn hơn chốt x

Để phân tích thời gian của SELECT, trước hết tìm chặn dưới cho số phần tử lớn hơn phần tử chia x. Hình 9.1 của sách minh hoạ việc đếm này.

**Hình 9.1 (vẽ lại bằng chữ).** Hình gồm n = 28 phần tử, xếp thành 6 cột: 5 cột đủ 5 phần tử và cột thứ 6 có 3 phần tử. Mỗi cột là một nhóm, xếp từ trên xuống theo thứ tự tăng dần (phần tử nhỏ ở trên, lớn ở dưới), trung vị nhóm ở hàng giữa (vẽ bằng vòng tròn trắng). Các cột được sắp sao cho trung vị tăng dần từ trái sang phải; trung vị của các trung vị x là trung vị của cột thứ 3 (với 6 trung vị, x là trung vị dưới, tức trung vị nhỏ thứ 3). Mũi tên đi từ phần tử lớn tới phần tử nhỏ hơn: trong mỗi cột, từ phần tử dưới lên phần tử trên; giữa các trung vị, từ trung vị bên phải sang trung vị bên trái.

```text
   cột:      1     2     3     4     5     6
   hàng 1:   •     •     •     •     •
   hàng 2:   •     •     •     •     •     •
   hàng 3:   ○  ←  ○  ←  x  ←  ○  ←  ○  ←  ○     (trung vị nhóm, tăng dần
   hàng 4:   •     •     ▓     ▓     ▓     ▓      từ trái sang phải)
   hàng 5:   •     •     ▓     ▓     ▓
                               (hàng 3 cột 4, 5, 6 cũng được tô bóng)

   ▓ và các trung vị ○ ở bên phải x: phần tử CHẮC CHẮN lớn hơn x
   (vùng tô bóng): 2 phần tử dưới x ở cột 3; trung vị và 2 phần tử dưới
   ở cột 4 và cột 5 (3 + 3); trung vị và 1 phần tử dưới ở cột 6 → 10
   phần tử. Đối xứng: 2 phần tử trên x ở cột 3 và trung vị cùng 2 phần
   tử trên ở cột 1, 2 → 8 phần tử chắc chắn nhỏ hơn x.
```

Chú thích hình nói: trong mỗi nhóm đủ 5 phần tử ở bên phải x có 3 phần tử lớn hơn x, và trong mỗi nhóm 5 phần tử ở bên trái x có 3 phần tử nhỏ hơn x; các phần tử biết chắc lớn hơn x nằm trên nền tô bóng.

**Lập luận đếm.** Ít nhất một nửa số trung vị tìm ở bước 2 lớn hơn hoặc bằng x. (Vì các số phân biệt, mọi trung vị trừ x hoặc lớn hơn hoặc nhỏ hơn x.) Do đó ít nhất một nửa trong ⌈n/5⌉ nhóm góp ít nhất 3 phần tử lớn hơn x (trung vị của nhóm và hai phần tử lớn hơn trung vị), trừ hai nhóm: nhóm có ít hơn 5 phần tử nếu 5 không chia hết n, và nhóm chứa chính x. Bỏ hai nhóm này, số phần tử lớn hơn x ít nhất là

  3 ( ⌈ (1/2) ⌈n/5⌉ ⌉ − 2 ) ≥ 3n/10 − 6.

(Bất đẳng thức đúng vì ⌈(1/2)⌈n/5⌉⌉ ≥ n/10.) Tương tự, ít nhất 3n/10 − 6 phần tử nhỏ hơn x. Vì vậy, trong trường hợp xấu nhất, bước 5 gọi SELECT đệ quy trên tối đa n − (3n/10 − 6) = 7n/10 + 6 phần tử.

Kiểm tra với Hình 9.1 (n = 28): ⌈28/5⌉ = 6, ⌈6/2⌉ = 3, công thức cho 3(3 − 2) = 3 ≥ 3·28/10 − 6 = 2,4; thực tế hình có 10 phần tử chắc chắn lớn hơn x. Chặn dưới rất lỏng khi n nhỏ, nhưng tăng tuyến tính theo n: với n = 1.000 nó cho ít nhất 3·(100 − 2) = 294 phần tử mỗi phía, nên lần đệ quy sau xét tối đa 706 phần tử.

#### Truy hồi cho thời gian xấu nhất

Bước 1, 2 và 4 tốn O(n). (Bước 2 gồm O(n) lần sắp xếp chèn trên tập có kích thước O(1).) Bước 3 tốn T(⌈n/5⌉), và bước 5 tốn tối đa T(7n/10 + 6), với giả định T đơn điệu tăng. Sách đưa ra một giả định thoạt nhìn có vẻ vô cớ: mọi đầu vào ít hơn 140 phần tử tốn O(1) thời gian; nguồn gốc của "hằng số kỳ diệu" 140 sẽ rõ ngay sau đây. Ta có truy hồi

  T(n) ≤ O(1)                    nếu n < 140,
  T(n) ≤ T(⌈n/5⌉) + T(7n/10 + 6) + O(n)  nếu n ≥ 140.

#### Chứng minh T(n) = O(n) bằng phương pháp thế

Ta chứng minh T(n) ≤ cn với hằng số c đủ lớn và mọi n > 0. Trước hết giả sử T(n) ≤ cn với mọi n < 140; điều này đúng nếu c đủ lớn. Chọn hằng số a sao cho hàm ứng với số hạng O(n) (phần không đệ quy) bị chặn trên bởi an với mọi n > 0. Thay giả thiết quy nạp vào vế phải:

  T(n) ≤ c⌈n/5⌉ + c(7n/10 + 6) + an
     ≤ cn/5 + c + 7cn/10 + 6c + an
     = 9cn/10 + 7c + an
     = cn + (−cn/10 + 7c + an),

đại lượng này không vượt cn nếu

  −cn/10 + 7c + an ≤ 0.  (9.2)

Bất đẳng thức (9.2) tương đương với c ≥ 10a(n/(n − 70)) khi n > 70 (chuyển vế: c(n/10 − 7) ≥ an, tức c(n − 70)/10 ≥ an). Vì ta giả sử n ≥ 140 nên n/(n − 70) ≤ 2, và chọn c ≥ 20a sẽ thoả (9.2). Kiểm tra bằng số: a = 1, c = 20, n = 140: −20·140/10 + 7·20 + 140 = −280 + 140 + 140 = 0 ≤ 0, đúng (vừa khít); n = 200: −400 + 140 + 200 = −60 ≤ 0.

Không có gì đặc biệt ở hằng số 140: có thể thay bằng bất kỳ số nguyên nào lớn hơn hẳn 70 rồi chọn c tương ứng. (Con số 70 xuất hiện vì 7c ≤ (c/10 − a)n đòi hỏi n > 70 ngay cả khi a rất nhỏ.) Vậy **thời gian xấu nhất của SELECT là tuyến tính**.

Trực giác: tổng kích thước hai bài toán con là n/5 + 7n/10 = 9n/10 < n, nên công việc ở mỗi tầng đệ quy giảm theo cấp số nhân tỷ lệ 9/10, tổng là O(n)·(1 + 9/10 + (9/10)² + …) = O(10n) = O(n).

#### Chọn không bị giới hạn Ω(n lg n) của sắp xếp

Như một thuật toán sắp xếp bằng so sánh (mục 8.1), SELECT và RANDOMIZED-SELECT chỉ biết thứ tự tương đối giữa các phần tử qua phép so sánh. Chương 8 đã chứng minh sắp xếp trong mô hình so sánh cần Ω(n lg n), kể cả trung bình (Bài toán 8-1). Các thuật toán sắp xếp tuyến tính của Chương 8 (sắp xếp đếm, sắp xếp cơ số, sắp xếp theo thùng) phải giả định về đầu vào. Ngược lại, các thuật toán chọn tuyến tính của chương này không cần giả định gì về đầu vào. Chúng không bị cận Ω(n lg n) chi phối vì giải được bài toán chọn mà không sắp xếp. Vì thế cách "sắp xếp rồi lấy phần tử thứ i" nêu ở phần mở đầu chương là kém hiệu quả về tiệm cận.

#### Ví dụ hôm nay

Thuật toán trung vị của các trung vị hiếm khi được dùng nguyên dạng làm thuật toán chọn chính, vì hằng số ẩn lớn (Bài toán 9-3 nhắc điều này) và thường chậm hơn quickselect nhiều lần trên dữ liệu thật. Vai trò thực tế của nó là "lưới an toàn": các bản cài đặt kiểu introselect chạy quickselect, và chỉ khi phát hiện đệ quy quá sâu mới chuyển sang chọn chốt bằng trung vị của các trung vị để bảo đảm O(n) (theo hiểu biết của người tổng hợp). Ý tưởng "lấy mẫu có cấu trúc để có chốt tốt có bảo đảm" cũng xuất hiện trong thuật toán song song, xử lý dữ liệu lớn và trong việc dùng trung vị làm chốt để quicksort đạt O(n lg n) xấu nhất (Bài tập 9.3-3).

### 5. Bài toán cuối chương (Problems, trang 224–226)

Bốn bài toán mở rộng nội dung chương; đề và lời giải được trình bày ở mục "Bài tập và bài toán cuối chương" bên dưới.

### 6. Ghi chú chương (Chapter notes, trang 227)

Thuật toán tìm trung vị tuyến tính trường hợp xấu nhất do Blum, Floyd, Pratt, Rivest và Tarjan đưa ra. Phiên bản ngẫu nhiên nhanh là của Hoare. Floyd và Rivest phát triển một phiên bản ngẫu nhiên cải tiến, chia mảng quanh một phần tử được chọn đệ quy từ một mẫu nhỏ các phần tử. Số phép so sánh chính xác cần để tìm trung vị vẫn chưa biết: Bent và John chứng minh cận dưới 2n; Schönhage, Paterson và Pippenger đưa ra cận trên 3n; Dor và Zwick cải thiện cả hai — cận trên hơi dưới 2,95n và cận dưới (2 + ε)n với ε là một hằng số dương nhỏ, qua đó cải thiện nhẹ một kết quả liên quan của Dor và các cộng sự. Paterson có một bài tổng quan về các kết quả này và các công trình liên quan.

(Năm công bố, theo hiểu biết của người tổng hợp, không tra cứu: Hoare công bố thuật toán FIND năm 1961; Blum, Floyd, Pratt, Rivest, Tarjan năm 1973; Floyd và Rivest năm 1975; Schönhage, Paterson, Pippenger năm 1976; Bent và John năm 1985; Dor và Zwick giữa thập niên 1990.)

## Bài tập và bài toán cuối chương

### Bài tập mục 9.1 (trang 215)

- **9.1-1:** Chứng minh có thể tìm phần tử nhỏ thứ hai trong n phần tử với n + ⌈lg n⌉ − 2 phép so sánh trong trường hợp xấu nhất (gợi ý: tìm luôn phần tử nhỏ nhất). *Ý tưởng (của người tổng hợp):* tổ chức giải đấu loại trực tiếp dạng cây nhị phân, tốn n − 1 phép để tìm nhỏ nhất; phần tử nhỏ thứ hai chỉ có thể là một trong các phần tử đã thua trực tiếp phần tử nhỏ nhất, có tối đa ⌈lg n⌉ phần tử như vậy; tìm nhỏ nhất trong số đó tốn ⌈lg n⌉ − 1 phép. Tổng n + ⌈lg n⌉ − 2.
- **9.1-2 (★):** Chứng minh cận dưới ⌈3n/2⌉ − 2 phép so sánh trong trường hợp xấu nhất để tìm cả lớn nhất và nhỏ nhất (gợi ý: xét có bao nhiêu số còn khả năng là lớn nhất hoặc nhỏ nhất, và một phép so sánh ảnh hưởng tới các số đếm đó ra sao). *Ý tưởng (của người tổng hợp):* lập luận đối thủ; chia phần tử thành bốn loại (chưa so sánh; chỉ từng thắng; chỉ từng thua; cả thắng cả thua). Cần chuyển n − 2 phần tử sang loại "cả thắng cả thua" và mỗi phần tử ít nhất ra khỏi loại "chưa so sánh". Một phép so sánh giữa hai phần tử chưa so sánh tạo 2 "đơn vị thông tin", mọi phép khác tối đa 1 khi đối thủ trả lời khéo; tổng thông tin cần là 2n − 2, chỉ ⌊n/2⌋ phép có thể cho 2 đơn vị, từ đó ra ⌈3n/2⌉ − 2.

### Bài tập mục 9.2 (trang 219–220)

- **9.2-1:** Chứng minh RANDOMIZED-SELECT không bao giờ gọi đệ quy trên mảng độ dài 0. (Lời giải đã nêu ở phần 3: phía thấp rỗng nghĩa là k = 1 nên không thể i < k; phía cao rỗng nghĩa là k = n nên không thể i > k.)
- **9.2-2:** Lập luận rằng biến chỉ báo X_k và giá trị T(max(k − 1, n − k)) độc lập.
- **9.2-3:** Viết phiên bản lặp (không đệ quy) của RANDOMIZED-SELECT. *Ý tưởng:* vì mỗi lần chỉ có một lời gọi đệ quy ở cuối, thay bằng vòng lặp cập nhật p, r, i.
- **9.2-4:** Giả sử dùng RANDOMIZED-SELECT tìm phần tử nhỏ nhất của A = ⟨3, 2, 9, 0, 7, 5, 4, 8, 6, 1⟩; mô tả một chuỗi phép chia cho hiệu năng xấu nhất. *Đáp án:* chốt lần lượt là phần tử lớn nhất còn lại: 9, 8, 7, 6, 5, 4, 3, 2, 1.

### Bài tập mục 9.3 (trang 223–224)

- **9.3-1:** Trong SELECT, phần tử được chia thành nhóm 5. Thuật toán còn tuyến tính không nếu dùng nhóm 7? Chứng minh SELECT không chạy tuyến tính nếu dùng nhóm 3. *Ý tưởng (của người tổng hợp):* nhóm 7 cho ít nhất 4(⌈½⌈n/7⌉⌉ − 2) ≥ 2n/7 − 8 phần tử mỗi phía, truy hồi T(n) ≤ T(⌈n/7⌉) + T(5n/7 + 8) + O(n), tổng tỷ lệ 1/7 + 5/7 = 6/7 < 1 → tuyến tính. Nhóm 3 chỉ bảo đảm khoảng n/3 phần tử mỗi phía, truy hồi T(n) ≤ T(n/3) + T(2n/3) + O(n), tổng tỷ lệ bằng 1 → Θ(n lg n).
- **9.3-2:** Phân tích SELECT để chứng minh nếu n ≥ 140 thì ít nhất ⌈n/4⌉ phần tử lớn hơn trung vị của các trung vị x và ít nhất ⌈n/4⌉ phần tử nhỏ hơn x.
- **9.3-3:** Chỉ cách làm quicksort chạy O(n lg n) trong trường hợp xấu nhất, với phần tử phân biệt. *Ý tưởng:* dùng SELECT tìm trung vị làm chốt; T(n) = 2T(n/2) + Θ(n).
- **9.3-4 (★):** Một thuật toán chỉ dùng so sánh để tìm phần tử nhỏ thứ i trong n phần tử; chứng minh nó cũng tìm được i − 1 phần tử nhỏ hơn và n − i phần tử lớn hơn mà không cần thêm phép so sánh. *Ý tưởng:* nếu kết quả các phép so sánh chưa xác định quan hệ giữa đáp án và một phần tử y, đối thủ có thể đổi giá trị y sang phía bên kia mà không mâu thuẫn, làm đáp án sai.
- **9.3-5:** Cho một thủ tục "hộp đen" tìm trung vị trong thời gian tuyến tính xấu nhất; đưa ra thuật toán tuyến tính đơn giản cho bài toán chọn thống kê thứ tự bất kỳ. *Ý tưởng:* tìm trung vị, chia quanh nó, đệ quy vào một nửa: T(n) = T(n/2) + O(n) = O(n).
- **9.3-6:** Phân vị bậc k của tập n phần tử là k − 1 thống kê thứ tự chia tập đã sắp thành k tập bằng nhau (chênh tối đa 1). Đưa ra thuật toán O(n lg k) liệt kê các phân vị bậc k. *Ý tưởng:* dùng SELECT tìm phân vị ở giữa, chia, đệ quy hai phía với k/2 phân vị mỗi bên; độ sâu lg k, mỗi tầng O(n).
- **9.3-7:** Mô tả thuật toán O(n) cho tập S gồm n số phân biệt và số nguyên dương k ≤ n, tìm k số trong S gần trung vị của S nhất. *Ý tưởng:* tìm trung vị m; tính |s − m| cho mọi s; dùng SELECT tìm khoảng cách nhỏ thứ k; lấy các phần tử có khoảng cách không vượt ngưỡng đó.
- **9.3-8:** X[1..n] và Y[1..n] là hai mảng đã sắp xếp; đưa ra thuật toán O(lg n) tìm trung vị của toàn bộ 2n phần tử. *Ý tưởng:* so trung vị của X và của Y; trung vị chung nằm giữa hai giá trị này, nên bỏ nửa dưới của mảng có trung vị nhỏ hơn và nửa trên của mảng kia (bỏ cùng số phần tử), lặp lại.
- **9.3-9:** Giáo sư Olay tư vấn cho một công ty dầu khí định xây đường ống chính chạy theo hướng đông–tây qua một mỏ có n giếng. Mỗi giếng nối với đường ống chính bằng một ống nhánh theo đường ngắn nhất (hướng bắc hoặc nam). Hình 9.2 của sách vẽ một đường ống ngang với các giếng ở trên và dưới, mỗi giếng có một đoạn ống thẳng đứng nối vào ống chính. Biết toạ độ x và y của các giếng, chọn vị trí ống chính để tổng độ dài ống nhánh nhỏ nhất, trong thời gian tuyến tính. *Đáp án (của người tổng hợp):* đặt ống chính ở toạ độ y bằng trung vị các toạ độ y của giếng (n chẵn: bất kỳ giá trị nào giữa hai trung vị); tìm bằng SELECT trong O(n). Toạ độ x không ảnh hưởng.

### Bài toán 9-1 — i số lớn nhất theo thứ tự (Largest i numbers in sorted order, trang 224)

Cho n số, cần tìm i số lớn nhất theo thứ tự đã sắp xếp bằng thuật toán dựa trên so sánh. Với mỗi cách dưới đây, tìm thuật toán cài đặt cách đó có thời gian xấu nhất tốt nhất về tiệm cận, và phân tích thời gian theo n và i.

- **a.** Sắp xếp các số rồi liệt kê i số lớn nhất.
- **b.** Xây hàng đợi ưu tiên cực đại từ các số rồi gọi EXTRACT-MAX i lần.
- **c.** Dùng thuật toán thống kê thứ tự tìm số lớn thứ i, chia quanh số đó, rồi sắp xếp i số lớn nhất.

*Lời giải của người tổng hợp:* (a) heapsort hoặc merge sort: Θ(n lg n) (cộng i để liệt kê, không đáng kể). (b) BUILD-MAX-HEAP tốn O(n) (Chương 6), mỗi EXTRACT-MAX tốn O(lg n): O(n + i lg n). (c) SELECT O(n), PARTITION O(n), sắp i số O(i lg i): O(n + i lg i). Cách (c) tốt nhất.

### Bài toán 9-2 — Trung vị có trọng số (Weighted median, trang 225)

Cho n phần tử phân biệt x_1, x_2, …, x_n với trọng số dương w_1, w_2, …, w_n thoả Σ_{i=1}^{n} w_i = 1, **trung vị có trọng số (dưới)** là phần tử x_k thoả

  Σ_{x_i < x_k} w_i < 1/2  và  Σ_{x_i > x_k} w_i ≤ 1/2.

Ví dụ: các phần tử 0,1; 0,35; 0,05; 0,1; 0,15; 0,05; 0,2 với trọng số bằng chính giá trị (w_i = x_i, i = 1, …, 7) có trung vị 0,1 nhưng trung vị có trọng số 0,2. (Kiểm tra: các phần tử nhỏ hơn 0,2 có tổng trọng số 0,45 < 0,5, phần tử lớn hơn là 0,35 ≤ 0,5; còn 0,15 không thoả vì phía lớn hơn có 0,2 + 0,35 = 0,55.)

- **a.** Chứng minh trung vị của x_1, …, x_n là trung vị có trọng số với w_i = 1/n. *Lời giải:* trung vị dưới ở vị trí m = ⌊(n + 1)/2⌋ có m − 1 phần tử nhỏ hơn, trọng số (m − 1)/n < 1/2, và n − m phần tử lớn hơn, trọng số (n − m)/n ≤ 1/2.
- **b.** Tính trung vị có trọng số trong O(n lg n) xấu nhất bằng sắp xếp. *Lời giải:* sắp xếp, cộng dồn trọng số từ trái, dừng ở phần tử đầu tiên làm tổng dồn đạt ≥ 1/2.
- **c.** Tính trung vị có trọng số trong Θ(n) xấu nhất bằng thuật toán trung vị tuyến tính như SELECT. *Lời giải:* tìm trung vị m bằng SELECT, chia quanh m, tính tổng trọng số W_L phía nhỏ hơn và W_R phía lớn hơn; nếu cả hai điều kiện thoả thì m là đáp án; nếu W_L ≥ 1/2 thì đệ quy phía nhỏ (dồn trọng số phía lớn vào m); ngược lại đệ quy phía lớn. T(n) = T(n/2) + Θ(n) = Θ(n).

**Bài toán đặt bưu điện (post-office location problem):** cho n điểm p_1, …, p_n với trọng số w_1, …, w_n, tìm điểm p (không nhất thiết là một điểm đầu vào) cực tiểu hoá Σ_{i=1}^{n} w_i d(p, p_i), trong đó d(a, b) là khoảng cách giữa a và b.

- **d.** Chứng minh trung vị có trọng số là một lời giải tốt nhất cho bài toán một chiều, với d(a, b) = |a − b|. *Lời giải:* dịch p sang phải một đoạn nhỏ làm tổng thay đổi theo (trọng số bên trái − trọng số bên phải) × độ dịch; tổng giảm khi còn trọng số bên phải > 1/2 và không giảm được nữa tại trung vị có trọng số.
- **e.** Tìm lời giải tốt nhất cho bài toán hai chiều, với điểm (x, y) và **khoảng cách Manhattan** d(a, b) = |x_1 − x_2| + |y_1 − y_2| với a = (x_1, y_1), b = (x_2, y_2). *Lời giải:* tổng tách thành phần chỉ phụ thuộc x cộng phần chỉ phụ thuộc y; lấy x là trung vị có trọng số của các toạ độ x và y là trung vị có trọng số của các toạ độ y.

### Bài toán 9-3 — Thống kê thứ tự nhỏ (Small order statistics, trang 225–226)

Số phép so sánh xấu nhất T(n) mà SELECT dùng để chọn thống kê thứ tự thứ i trong n số thoả T(n) = Θ(n), nhưng hằng số ẩn trong Θ khá lớn. Khi i nhỏ so với n, có thể dùng SELECT làm thủ tục con trong một thủ tục khác tốn ít phép so sánh hơn trong trường hợp xấu nhất.

- **a.** Mô tả thuật toán dùng U_i(n) phép so sánh để tìm phần tử nhỏ thứ i trong n phần tử, với

  U_i(n) = T(n)  nếu i ≥ n/2,
  U_i(n) = ⌊n/2⌋ + U_i(⌈n/2⌉) + T(2i)  trong các trường hợp khác.

  (Gợi ý: bắt đầu bằng ⌊n/2⌋ phép so sánh từng cặp rời nhau, rồi đệ quy trên tập gồm phần tử nhỏ hơn của mỗi cặp.) *Lời giải của người tổng hợp:* ghép cặp, ⌊n/2⌋ phép so sánh; tập các phần tử nhỏ hơn của mỗi cặp (cộng phần tử lẻ nếu có) có ⌈n/2⌉ phần tử; đệ quy tìm i phần tử nhỏ nhất của tập này (theo Bài tập 9.3-4, tìm phần tử thứ i thì biết luôn i − 1 phần tử nhỏ hơn). i phần tử nhỏ nhất của cả tập nằm trong i phần tử này cùng i "bạn cặp" của chúng — tổng 2i phần tử; dùng SELECT trên 2i phần tử, tốn T(2i).
- **b.** Chứng minh nếu i < n/2 thì U_i(n) = n + O(T(2i) lg(n/i)). *Ý tưởng:* mỗi tầng đệ quy giảm n một nửa cho tới khi kích thước ≤ 2i, tức khoảng lg(n/i) tầng; tổng các số hạng ⌊n/2⌋ + ⌊n/4⌋ + … ≤ n; mỗi tầng thêm T(2i).
- **c.** Chứng minh nếu i là hằng số nhỏ hơn n/2 thì U_i(n) = n + O(lg n). (Vì T(2i) = O(1).)
- **d.** Chứng minh nếu i = n/k với k ≥ 2 thì U_i(n) = n + O(T(2n/k) lg k). (Thay i = n/k vào kết quả b.)

### Bài toán 9-4 — Phân tích khác cho chọn ngẫu nhiên (Alternative analysis of randomized selection, trang 226)

Bài toán dùng biến chỉ báo để phân tích RANDOMIZED-SELECT theo cách giống phân tích RANDOMIZED-QUICKSORT ở mục 7.4.2. Giả sử mọi phần tử phân biệt, đổi tên các phần tử của A thành z_1, z_2, …, z_n với z_i là phần tử nhỏ thứ i; lời gọi RANDOMIZED-SELECT(A, 1, n, k) trả về z_k. Với 1 ≤ i < j ≤ n, đặt

  X_ijk = I{z_i được so sánh với z_j vào một lúc nào đó khi thuật toán chạy để tìm z_k}.

- **a.** Cho biểu thức chính xác của E[X_ijk] (gợi ý: biểu thức có thể khác nhau tuỳ giá trị của i, j, k). *Lời giải của người tổng hợp:* z_i và z_j được so sánh khi và chỉ khi, trong khoảng từ z_{min(i,k)} tới z_{max(j,k)}, phần tử đầu tiên được chọn làm chốt là z_i hoặc z_j. Vậy E[X_ijk] = 2/(max(j, k) − min(i, k) + 1), cụ thể: 2/(j − i + 1) nếu i ≤ k ≤ j; 2/(j − k + 1) nếu k < i < j; 2/(k − i + 1) nếu i < j < k.
- **b.** Gọi X_k là tổng số phép so sánh giữa các phần tử của A khi tìm z_k. Chứng minh

  E[X_k] ≤ 2 ( Σ_{i=1}^{k} Σ_{j=k}^{n} 1/(j − i + 1) + Σ_{j=k+1}^{n} (j − k − 1)/(j − k + 1) + Σ_{i=1}^{k−2} (k − i − 1)/(k − i + 1) ).

  *Ý tưởng:* cộng ba trường hợp ở câu a; ở trường hợp thứ hai, với mỗi j có j − k − 1 giá trị i; ở trường hợp thứ ba, với mỗi i có k − i − 1 giá trị j.
- **c.** Chứng minh E[X_k] ≤ 4n. *Ý tưởng:* trong tổng kép, với mỗi độ dài d = j − i + 1 có tối đa d cặp (i, j) chứa k, mỗi cặp góp 1/d, nên tổng ≤ n; hai tổng sau mỗi số hạng < 1 và có tổng cộng (n − k) + (k − 2) < n số hạng. Vậy E[X_k] ≤ 2(n + n) = 4n.
- **d.** Kết luận rằng, với phần tử phân biệt, RANDOMIZED-SELECT chạy trong thời gian kỳ vọng O(n). (Thời gian tỷ lệ với số phép so sánh.)

### Ghi chú chương

Tóm lược ở phần 6 trên: Blum–Floyd–Pratt–Rivest–Tarjan (chọn tuyến tính xấu nhất), Hoare (chọn ngẫu nhiên), Floyd–Rivest (chọn ngẫu nhiên dựa trên mẫu), Bent–John (cận dưới 2n cho trung vị), Schönhage–Paterson–Pippenger (cận trên 3n), Dor–Zwick (cận trên < 2,95n, cận dưới (2 + ε)n), Paterson (tổng quan).

## Luận điểm cốt lõi

### Mệnh đề

Bài toán chọn — tìm phần tử nhỏ thứ i trong n phần tử, đặc biệt là trung vị — giải được trong thời gian Θ(n) chỉ bằng phép so sánh, kỳ vọng với thuật toán ngẫu nhiên và cả trong trường hợp xấu nhất với thuật toán tất định; vì vậy chọn dễ hơn sắp xếp một cách căn bản.

### Giả định

- Mô hình so sánh: thuật toán chỉ biết thứ tự giữa các phần tử qua phép so sánh; mỗi phép so sánh, đổi chỗ tốn O(1).
- Các phần tử phân biệt (để tiện; kết quả mở rộng được cho phần tử lặp, nhưng phân tích của mục 9.2 dựa vào điều này).
- Với RANDOMIZED-SELECT: có bộ sinh số ngẫu nhiên RANDOM(p, r) trả về đều mỗi số nguyên trong [p, r]; thời gian chạy đơn điệu tăng theo n (để chặn bằng phía lớn hơn).
- Với SELECT: hàm thời gian đơn điệu tăng; đầu vào dưới 140 phần tử tốn O(1) (một hằng số lớn).
- Quy ước trung vị là trung vị dưới.

### Cơ chế

1. Tìm nhỏ nhất: duyệt một lượt, n − 1 phép so sánh, tối ưu theo lập luận giải đấu.
2. Tìm nhỏ nhất và lớn nhất: xử lý theo cặp, 3 phép cho 2 phần tử, tổng ≤ 3⌊n/2⌋.
3. Chọn ngẫu nhiên: chia quanh chốt ngẫu nhiên, tính hạng k của chốt, so với i, đệ quy vào một phía duy nhất; vì chốt thường rơi vào khoảng giữa, kích thước giảm theo tỷ lệ hằng số trung bình.
4. Chọn tất định: tạo chốt "đủ tốt" bằng trung vị của các trung vị nhóm 5; chốt này loại được ít nhất 3n/10 − 6 phần tử mỗi lần; hai bài toán con có tổng kích thước ≤ 9n/10 + O(1).
5. Phân tích: truy hồi + phương pháp thế (đoán T(n) ≤ cn, chọn c đủ lớn theo a).

### Bằng chứng và ví dụ tác giả đưa ra

- MINIMUM và lập luận giải đấu cho cận n − 1.
- Phép đếm 3⌊n/2⌋ (n lẻ) và 3n/2 − 2 (n chẵn) cho nhỏ nhất và lớn nhất.
- Pseudocode RANDOMIZED-SELECT và phân tích kỳ vọng với biến chỉ báo X_k, cho E[T(n)] ≤ cn − (cn/4 − c/2 − an), điều kiện c > 4a, n ≥ 2c/(c − 4a).
- Năm bước của SELECT, Hình 9.1 (28 phần tử, 6 nhóm) minh hoạ việc đếm phần tử lớn hơn x, chặn 3n/10 − 6, truy hồi với ngưỡng 140 và điều kiện c ≥ 20a.
- So sánh với cận Ω(n lg n) của sắp xếp (Chương 8).
- Ví dụ trung vị có trọng số 0,2 so với trung vị 0,1 (Bài toán 9-2); bài toán đường ống dầu (Bài tập 9.3-9).

### Kết luận và hàm ý cho người lập trình

- Đừng sắp xếp cả mảng chỉ để lấy trung vị, phân vị hay k phần tử lớn nhất: dùng thao tác chọn (thường có sẵn trong thư viện chuẩn), O(n) thay vì O(n lg n).
- Trong thực tế, chọn ngẫu nhiên (quickselect) nhanh hơn trung vị của các trung vị nhờ hằng số nhỏ; dùng trung vị của các trung vị làm phương án dự phòng khi cần bảo đảm trường hợp xấu nhất (ví dụ chống tấn công bằng đầu vào xấu).
- Khi cần cả nhỏ nhất và lớn nhất, xử lý theo cặp tiết kiệm khoảng 25% số phép so sánh; đáng làm khi phép so sánh đắt.
- Kỹ thuật "chọn chốt tốt có bảo đảm" biến các thuật toán chia để trị có trường hợp xấu Θ(n²) (quicksort) thành O(n lg n) xấu nhất.
- Bài học phân tích: đệ quy vào một phía với kích thước giảm theo tỷ lệ hằng số cho thời gian tuyến tính; đệ quy hai phía với tổng tỷ lệ < 1 (như 1/5 + 7/10) vẫn tuyến tính.

### Trong ngôn ngữ khoa học máy tính

- MINIMUM: đúng n − 1 phép so sánh, tối ưu. MIN-MAX: ≤ 3⌊n/2⌋, cận dưới ⌈3n/2⌉ − 2.
- RANDOMIZED-SELECT: E[T(n)] ≤ (2/n) Σ_{k=⌊n/2⌋}^{n−1} E[T(k)] + O(n) ⇒ E[T(n)] = Θ(n); xấu nhất Θ(n²).
- SELECT: T(n) ≤ T(⌈n/5⌉) + T(7n/10 + 6) + O(n) ⇒ T(n) = Θ(n) xấu nhất.
- Bài toán chọn trong mô hình so sánh: Θ(n), so với sắp xếp: Θ(n lg n).
- Số phép so sánh tối ưu cho trung vị: nằm giữa (2 + ε)n và khoảng 2,95n (chưa biết chính xác).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| order statistic (i-th) | thống kê thứ tự (thứ i) | phần tử nhỏ thứ i của tập |
| minimum / maximum | phần tử nhỏ nhất / lớn nhất | thống kê thứ tự thứ 1 / thứ n |
| median | trung vị | phần tử ở giữa; sách quy ước là trung vị dưới |
| lower median / upper median | trung vị dưới / trung vị trên | phần tử ở vị trí ⌊(n + 1)/2⌋ / ⌈(n + 1)/2⌉ |
| selection problem | bài toán chọn | tìm phần tử lớn hơn đúng i − 1 phần tử khác |
| distinct elements | phần tử phân biệt | không có hai phần tử bằng nhau |
| upper bound / lower bound | cận trên / cận dưới | số phép toán đủ dùng / bắt buộc phải dùng |
| tournament | giải đấu | mô hình coi phép so sánh là trận đấu, dùng chứng minh cận dưới |
| simultaneous minimum and maximum | đồng thời nhỏ nhất và lớn nhất | tìm cả hai trong một lượt duyệt |
| asymptotically optimal | tối ưu tiệm cận | đạt cận dưới sai khác hằng số |
| divide-and-conquer | chia để trị | chia bài toán thành bài toán con, giải đệ quy |
| randomized algorithm | thuật toán ngẫu nhiên | hành vi phụ thuộc bộ sinh số ngẫu nhiên |
| random-number generator | bộ sinh số ngẫu nhiên | thủ tục RANDOM(p, r) |
| partition | phép chia (mảng) | sắp lại mảng quanh chốt: bên trái ≤, bên phải > |
| pivot (element) | phần tử chốt | phần tử dùng để chia mảng |
| low side / high side | phía thấp / phía cao | mảng con các phần tử nhỏ hơn / lớn hơn chốt |
| RANDOMIZED-PARTITION | phép chia ngẫu nhiên | chọn chốt ngẫu nhiên đều rồi gọi PARTITION |
| RANDOMIZED-SELECT | chọn ngẫu nhiên | thuật toán chọn thời gian kỳ vọng Θ(n) (quickselect) |
| SELECT | chọn tất định | thuật toán chọn thời gian xấu nhất Θ(n) |
| expected running time | thời gian chạy kỳ vọng | trung bình theo các lựa chọn ngẫu nhiên của thuật toán |
| worst-case running time | thời gian chạy trường hợp xấu nhất | thời gian lớn nhất trên mọi đầu vào cỡ n |
| random variable | biến ngẫu nhiên | đại lượng phụ thuộc kết quả ngẫu nhiên |
| indicator random variable | biến ngẫu nhiên chỉ báo | I{A} = 1 nếu A xảy ra, 0 nếu không |
| linearity of expectation | tính tuyến tính của kỳ vọng | E[X + Y] = E[X] + E[Y] |
| independent random variables | biến ngẫu nhiên độc lập | khi đó E[XY] = E[X]E[Y] |
| monotonically increasing | đơn điệu tăng | n lớn hơn thì T(n) không nhỏ hơn |
| recurrence | truy hồi | phương trình định nghĩa T(n) qua T của đối số nhỏ hơn |
| substitution method | phương pháp thế | đoán nghiệm rồi chứng minh bằng quy nạp |
| inductive hypothesis | giả thiết quy nạp | giả sử bất đẳng thức đúng với đối số nhỏ hơn |
| median-of-medians | trung vị của các trung vị | chốt của SELECT |
| group of 5 | nhóm 5 phần tử | đơn vị chia của SELECT |
| insertion sort | sắp xếp chèn | dùng để sắp từng nhóm 5 phần tử |
| comparison model / comparison sort | mô hình so sánh / sắp xếp bằng so sánh | chỉ dùng phép so sánh để biết thứ tự |
| max-priority queue / EXTRACT-MAX | hàng đợi ưu tiên cực đại / lấy phần tử lớn nhất | cấu trúc heap của Chương 6, dùng trong Bài toán 9-1 |
| weighted (lower) median | trung vị có trọng số (dưới) | phần tử chia tổng trọng số thành hai nửa |
| post-office location problem | bài toán đặt bưu điện | chọn điểm cực tiểu tổng khoảng cách có trọng số |
| Manhattan distance | khoảng cách Manhattan | |x₁ − x₂| + |y₁ − y₂| |
| small order statistics | thống kê thứ tự nhỏ | trường hợp i nhỏ so với n (Bài toán 9-3) |
| k-th quantiles | phân vị bậc k | k − 1 thống kê thứ tự chia tập thành k phần bằng nhau |
| spur pipeline | ống nhánh | đoạn ống nối giếng với đường ống chính (Bài tập 9.3-9) |
| black-box subroutine | thủ tục con hộp đen | thủ tục dùng mà không cần biết bên trong |

## Câu nói đáng nhớ

> "The *i*th *order statistic* of a set of *n* elements is the *i*th smallest element." — mở đầu Chương 9, trang 213
>
> *Dịch: Thống kê thứ tự thứ i của một tập n phần tử là phần tử nhỏ thứ i.*

> "Think of any algorithm that determines the minimum as a tournament among the elements." — mục 9.1, trang 214, khi chứng minh cận dưới n − 1
>
> *Dịch: Hãy coi mọi thuật toán xác định phần tử nhỏ nhất như một giải đấu giữa các phần tử.*

> "The general selection problem appears more difficult than the simple problem of finding a minimum. Yet, surprisingly, the asymptotic running time for both problems is the same: Θ(n)." — mục 9.2, trang 215
>
> *Dịch: Bài toán chọn tổng quát có vẻ khó hơn bài toán đơn giản tìm phần tử nhỏ nhất. Thế nhưng, thật đáng ngạc nhiên, thời gian chạy tiệm cận của cả hai bài toán là như nhau: Θ(n).*

> "But unlike quicksort, which recursively processes both sides of the partition, RANDOMIZED-SELECT works on only one side of the partition." — mục 9.2, trang 215
>
> *Dịch: Nhưng khác với quicksort, vốn xử lý đệ quy cả hai phía của phép chia, RANDOMIZED-SELECT chỉ làm việc trên một phía.*

> "Here, however, we guarantee a good split upon partitioning the array." — mục 9.3, trang 220, giới thiệu SELECT
>
> *Dịch: Tuy nhiên, ở đây ta bảo đảm một phép chia tốt khi chia mảng.*

> "They are not subject to the Ω(n lg n) lower bound because they manage to solve the selection problem without sorting." — mục 9.3, trang 222
>
> *Dịch: Chúng không bị cận dưới Ω(n lg n) chi phối vì giải được bài toán chọn mà không cần sắp xếp.*

> "It is still unknown exactly how many comparisons are needed to determine the median." — Ghi chú chương, trang 227
>
> *Dịch: Hiện vẫn chưa biết chính xác cần bao nhiêu phép so sánh để xác định trung vị.*

## Đánh giá và phát hiện đáng chú ý

### Chương ngắn nhưng chứa một kết quả kinh điển, trình bày gọn và đúng trọng tâm

Chương chỉ khoảng 15 trang nhưng đi trọn một cung lập luận: bài toán đơn giản nhất (nhỏ nhất) với cận trên và cận dưới khớp nhau chính xác, một mẹo tiết kiệm hằng số (xử lý theo cặp), một thuật toán ngẫu nhiên thực dụng, rồi một thuật toán tất định có bảo đảm. Đặt ở cuối Phần II, ngay sau chứng minh Ω(n lg n) cho sắp xếp, chương làm nổi bật ranh giới giữa "biết thứ tự toàn bộ" và "biết vị trí của một phần tử" — một bài học về việc đặt đúng câu hỏi trước khi chọn thuật toán.

### Phân tích của mục 9.2 chặt chẽ nhưng hơi nặng đại số

Cách dùng biến chỉ báo X_k và tính độc lập để lấy kỳ vọng nhất quán với Chương 5 và 7, nhưng chuỗi bất đẳng thức với ⌊n/2⌋ và các hằng số a, c làm người đọc dễ mất trực giác. Trực giác đơn giản hơn: với xác suất 1/2, chốt rơi vào nửa giữa, khi đó kích thước giảm còn tối đa 3n/4; vậy trung bình sau hai lần chia kích thước giảm theo hằng số, tổng công việc là cấp số nhân. Bài toán 9-4 đưa ra cách phân tích thứ hai, đếm số cặp được so sánh, cho hằng số cụ thể E[X_k] ≤ 4n — hữu ích hơn cho người quan tâm hằng số. Ấn bản 4 đổi sang một cách phân tích trực quan hơn theo hướng này (theo hiểu biết của người tổng hợp).

### SELECT: thanh lịch về lý thuyết, đắt đỏ về hằng số

Sách thẳng thắn gọi SELECT là thuật toán "có ý nghĩa lý thuyết hơn" và Bài toán 9-3 thừa nhận hằng số ẩn "khá lớn". Ngưỡng 140 và điều kiện c ≥ 20a cho thấy chứng minh không cố tối ưu hằng số. Trên máy tính hiện đại, SELECT còn chịu thêm chi phí di chuyển dữ liệu (tạo mảng trung vị, nhiều lượt duyệt), nên quickselect với chốt là trung vị của 3 hoặc của một mẫu nhỏ (ý tưởng Floyd–Rivest) thường nhanh hơn nhiều; thư viện chuẩn chỉ dùng trung vị của các trung vị làm phương án dự phòng. Ấn bản 3 cũng chỉ mô tả SELECT bằng lời, không có pseudocode, khiến các chi tiết cài đặt (làm sao PARTITION nhận chốt làm tham số, xử lý nhóm cuối thiếu, làm tại chỗ hay dùng mảng phụ) để lại cho người đọc.

### Liên hệ các chương khác

- Chương 7: PARTITION, RANDOMIZED-PARTITION và kỹ thuật phân tích quicksort được tái sử dụng trực tiếp; Bài tập 9.3-3 dùng SELECT để quicksort đạt O(n lg n) xấu nhất.
- Chương 8: cận Ω(n lg n) của sắp xếp bằng so sánh là phông nền để thấy ý nghĩa của kết quả tuyến tính.
- Chương 6: Bài toán 9-1 so sánh cách dùng heap với cách dùng SELECT.
- Chương 14: cây thống kê thứ tự giải bài toán chọn trên tập động trong O(lg n) mỗi thao tác — lựa chọn đúng khi phải trả lời nhiều truy vấn trên dữ liệu thay đổi, còn SELECT hợp với truy vấn một lần trên dữ liệu tĩnh.
- Chương 4 và Phụ lục C: phương pháp thế và công thức kỳ vọng của tích biến độc lập.

### Cách vận dụng

- **Phỏng vấn lập trình:** "tìm phần tử lớn thứ k", "k điểm gần gốc nhất", "trung vị của hai mảng đã sắp xếp" (Bài tập 9.3-8), "đặt đường ống/bưu điện tối ưu" (Bài tập 9.3-9, Bài toán 9-2) đều là bài kinh điển xuất phát từ chương này. Câu trả lời mong đợi thường là quickselect O(n) trung bình, kèm hiểu biết rằng trung vị của các trung vị cho O(n) xấu nhất, và heap kích thước k cho O(n lg k) khi dữ liệu đến theo luồng.
- **Lập trình thi đấu:** dùng thao tác chọn của thư viện chuẩn thay vì sắp xếp; ý tưởng "tối ưu tổng khoảng cách tuyệt đối thì chọn trung vị" xuất hiện rất thường xuyên.
- **Kỹ thuật phần mềm:** khi tính phân vị trên dữ liệu lớn hoặc dữ liệu luồng, các hệ thống thường dùng thuật toán xấp xỉ (phác thảo phân vị) vì không thể giữ toàn bộ dữ liệu; thuật toán chính xác của chương này phù hợp khi dữ liệu nằm gọn trong bộ nhớ. Nếu đầu vào có thể do đối thủ kiểm soát, cần chốt ngẫu nhiên (hoặc phương án dự phòng tất định) để tránh trường hợp Θ(n²).
- **Lưu ý phần tử lặp:** phân tích của sách giả định phần tử phân biệt; với nhiều giá trị lặp, PARTITION hai vùng có thể làm quickselect suy biến, nên cài đặt thực tế dùng phép chia ba vùng (nhỏ hơn, bằng, lớn hơn chốt).

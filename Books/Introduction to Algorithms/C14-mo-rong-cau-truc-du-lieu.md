# Chương 14 — Mở rộng cấu trúc dữ liệu (Augmenting Data Structures)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần III "Data Structures", Chương 14 "Augmenting Data Structures", trang sách 339–355 (PDF 360–376).
**Tác giả:** Cormen (Dartmouth), Leiserson và Rivest (MIT), Stein (Columbia) — bốn tác giả của giáo trình thuật toán được dùng rộng rãi nhất ở bậc đại học, thường gọi tắt là "CLRS".
**Vị trí trong lập luận của cả cuốn sách:** Chương 9 ([C09-trung-vi-va-thong-ke-thu-tu.md](C09-trung-vi-va-thong-ke-thu-tu.md)) đã định nghĩa thống kê thứ tự (phần tử nhỏ thứ i của một tập) và cho cách tìm nó trong thời gian O(n) trên một tập *tĩnh, không sắp xếp*. Chương 12 ([C12-cay-tim-kiem-nhi-phan.md](C12-cay-tim-kiem-nhi-phan.md)) xây dựng cây tìm kiếm nhị phân với các thao tác tập động (SEARCH, MINIMUM, MAXIMUM, SUCCESSOR, PREDECESSOR, INSERT, DELETE) chạy trong O(h), h là chiều cao cây. Chương 13 ([C13-cay-do-den.md](C13-cay-do-den.md)) giữ cho cây cân bằng — cây đỏ-đen có chiều cao O(lg n) — nhờ đổi màu và phép quay (rotation), trong đó chèn cần nhiều nhất 2 phép quay và xoá cần nhiều nhất 3. Chương 14 không tạo ra cấu trúc mới hoàn toàn, mà dạy một *kỹ thuật thiết kế*: lấy một cấu trúc dữ liệu có sẵn (ở đây là cây đỏ-đen), gắn thêm thông tin vào mỗi nút, chứng minh rằng các thao tác sửa đổi vẫn duy trì được thông tin đó với chi phí thấp, rồi dùng thông tin đó để có thao tác mới. Chương này đóng lại Phần III. Phần IV mở đầu bằng quy hoạch động ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)). Kỹ thuật "gắn thêm thuộc tính tổng hợp vào nút cây" sẽ được dùng lại ở nhiều nơi: Chương 21 ([C21-cau-truc-du-lieu-cho-tap-roi-nhau.md](C21-cau-truc-du-lieu-cho-tap-roi-nhau.md)) gắn thêm hạng (rank) vào nút của rừng tập rời nhau; Chương 33 ([C33-hinh-hoc-tinh-toan.md](C33-hinh-hoc-tinh-toan.md)) dùng đường quét (sweep line) kết hợp cây đỏ-đen, đúng kiểu bài tập 14.3-7; và phân tích dãy nghịch thế (inversion) của Bài toán 2-4 ([C02-bat-dau.md](C02-bat-dau.md)) được giải lại bằng cây thống kê thứ tự trong bài tập 14.1-7.
**Ý chính:** Các tác giả muốn người đọc hiểu rằng **phần lớn bài toán thực tế không cần cấu trúc dữ liệu hoàn toàn mới, mà cần "mở rộng" một cấu trúc giáo khoa bằng cách lưu thêm thông tin vào mỗi nút; điều khó là phải duy trì thông tin đó khi cấu trúc bị sửa đổi, và với cây đỏ-đen có một tiêu chí đơn giản bảo đảm việc này luôn rẻ.** Mục 14.1 xây dựng **cây thống kê thứ tự (order-statistic tree)**: cây đỏ-đen trong đó mỗi nút x lưu thêm x.size — số nút trong cây con gốc x, thoả x.size = x.left.size + x.right.size + 1 (với T.nil.size = 0). Nhờ đó thủ tục OS-SELECT(x, i) tìm phần tử nhỏ thứ i và OS-RANK(T, x) tính hạng (vị trí theo thứ tự giữa) của nút x đều chạy trong O(lg n), trong khi INSERT và DELETE vẫn O(lg n): tăng/giảm size dọc đường đi từ gốc, và mỗi phép quay chỉ cần sửa size của 2 nút bằng 2 dòng lệnh thêm vào LEFT-ROTATE. Mục 14.2 trừu tượng hoá thành **quy trình bốn bước** (chọn cấu trúc nền; chọn thông tin bổ sung; kiểm tra thông tin được duy trì qua các thao tác sửa đổi; xây dựng thao tác mới) và chứng minh **Định lý 14.1**: nếu thuộc tính f của mỗi nút x chỉ phụ thuộc vào thông tin trong x, x.left, x.right (kể cả x.left.f và x.right.f), thì có thể duy trì f qua chèn và xoá mà không làm thay đổi thời gian O(lg n). Mục 14.3 áp dụng quy trình đó để xây dựng **cây khoảng (interval tree)**: mỗi nút chứa một khoảng đóng x.int = [low, high], khoá là x.int.low, và thuộc tính bổ sung x.max = max(x.int.high, x.left.max, x.right.max). Thủ tục INTERVAL-SEARCH(T, i) đi một đường duy nhất từ gốc xuống, ở mỗi nút rẽ trái nếu x.left.max ≥ i.low, ngược lại rẽ phải, và **Định lý 14.2** chứng minh rằng cách rẽ này luôn "an toàn": thủ tục tìm được một khoảng giao với i trong O(lg n), hoặc trả về T.nil khi và chỉ khi không có khoảng nào giao với i.

> **Lưu ý:**
> - **Mục khó (dấu sao):** chương không có mục nào đánh dấu sao. Các bài tập đánh dấu sao là 14.1-8 (đếm cặp dây cung cắt nhau), 14.2-3 (toán tử kết hợp ⊗ và cập nhật sau phép quay), 14.2-4 (RB-ENUMERATE trong Θ(m + lg n)) và 14.3-7 (phát hiện hình chữ nhật chồng nhau bằng đường quét).
> - **Phạm vi trang:** bảng phân công ghi trang 339–354, nhưng Bài toán 14-2 và phần Ghi chú chương (Chapter notes) nằm ở trang 355; Phần IV bắt đầu ở trang 356 (PDF 377). Bản tổng hợp này bao trùm trang 339–355.
> - **Lớp chữ PDF hỏng:** toàn bộ pseudocode (OS-SELECT, OS-RANK, hai dòng thêm vào LEFT-ROTATE, INTERVAL-SEARCH), đẳng thức x.size, công thức x.max, các bất đẳng thức trong chứng minh Định lý 14.2 (ví dụ i′.high ≤ x.left.max < i.low và i.high < i′.low ≤ i″.low), bảng chạy tay OS-RANK, ba hình cây (Hình 14.1, 14.2, 14.4) và hình khoảng (Hình 14.3, 14.5) đều được đọc lại từ ảnh trang. Trong lớp chữ, "≥", "≤" bị mất hẳn (ví dụ "x: left:max i: low"), "−" thành "/NUL", "⟨3, 6, 2, 7, 5, 1, 4⟩" thành "h3; 6; 2; 7; 5; 1; 4i", và bảng chạy tay OS-RANK bị dính số ("42 6 1 7" là dòng "4 | 26 | 17").
> - **Lỗi câu chữ nhỏ (đọc từ ảnh trang 343):** câu "The first phase either removes one node y from the tree or moves upward it within the tree" đảo trật tự từ; đúng ra là "moves it upward". Không ảnh hưởng nội dung.
> - **Điểm diễn đạt không chặt (nhận xét của người tổng hợp):** sách cho phép khoá trùng nhau trong cây thống kê thứ tự và định nghĩa hạng theo vị trí của *nút* trong phép duyệt giữa, nhưng bất biến vòng lặp của OS-RANK lại phát biểu "r là hạng của x.key trong cây con gốc y". Khi có khoá trùng, "hạng của một khoá" không xác định; phải hiểu là "hạng của nút x". Tương tự, OS-SELECT ngầm giả định 1 ≤ i ≤ x.size; sách không kiểm tra điều kiện này (nếu i lớn hơn số nút, thủ tục sẽ đi tới T.nil và truy cập T.nil.left).
> - **Lỗi đã biết của ấn bản 3:** theo hiểu biết của người tổng hợp, không tra cứu, người tổng hợp không nhớ chắc lỗi nội dung nào trong danh sách errata cho Chương 14; mọi con số chạy tay trong chương (OS-SELECT tìm phần tử thứ 17 ra khoá 38, OS-RANK của nút 38 ra 17, hai lần chạy INTERVAL-SEARCH, giá trị size và max trong các hình, hoán vị Josephus (7, 3)) đã được người tổng hợp tính lại và đều đúng.
> - **Thay đổi sau 2009 (theo hiểu biết của người tổng hợp, không tra cứu):** ở ấn bản thứ tư (2022), chương này được chuyển sang Phần V "Advanced Data Structures" và đổi số thành Chương 17, vẫn giữ tên "Augmenting Data Structures" với ba mục tương ứng (cây thống kê thứ tự, cách mở rộng cấu trúc dữ liệu, cây khoảng); ấn bản 4 cũng bỏ hai chương đống Fibonacci và cây van Emde Boas của ấn bản 3. Người tổng hợp không chắc chi tiết từng thay đổi về bài tập.

## Sơ đồ

### Phần mở đầu chương (trước Mục 14.1, trang 339) — vì sao cần mở rộng cấu trúc dữ liệu

```text
       Nhiều bài toán kỹ thuật chỉ cần một cấu trúc dữ liệu "giáo khoa"
       (danh sách liên kết kép, bảng băm, cây tìm kiếm nhị phân)
                                │
                                ▼
       Nhiều bài toán khác cần sáng tạo thêm, nhưng hiếm khi phải phát
       minh cấu trúc hoàn toàn mới; thường chỉ cần MỞ RỘNG một cấu trúc
       có sẵn bằng cách lưu thêm thông tin vào nó, rồi viết thao tác mới
                                │
                                ▼
       Khó khăn: thông tin thêm vào phải được CẬP NHẬT và DUY TRÌ bởi
       chính các thao tác thông thường (chèn, xoá) của cấu trúc nền
                                │
               ┌────────────────┼────────────────┐
               ▼                ▼                ▼
       Mục 14.1: cây     Mục 14.2: quy trình  Mục 14.3: cây khoảng
       thống kê thứ tự   bốn bước và Định lý  (tìm một khoảng giao
       (tìm phần tử thứ  14.1 về mở rộng cây  với khoảng truy vấn)
       i, tính hạng)     đỏ-đen
```

### Mục 14.1 — Thống kê thứ tự động (Dynamic order statistics, trang 339–345)

```text
       Chương 9: tìm thống kê thứ tự thứ i của tập n phần tử KHÔNG sắp
       xếp mất O(n). Mục tiêu ở đây: tập ĐỘNG (có chèn, xoá), tìm phần tử
       thứ i và tính hạng của một phần tử, mỗi việc trong O(lg n)
                                │
                                ▼
       CÂY THỐNG KÊ THỨ TỰ = cây đỏ-đen, mỗi nút x có thêm thuộc tính
       x.size = số nút (không kể lính canh) trong cây con gốc x
       · quy ước T.nil.size = 0, khi đó
         x.size = x.left.size + x.right.size + 1
       · cho phép khoá trùng; hạng của một nút = vị trí của nút đó khi
         in ra theo phép duyệt giữa (inorder walk)
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       OS-SELECT(x, i): tìm nút có       OS-RANK(T, x): tính hạng của
       khoá nhỏ thứ i trong cây con      nút x trong toàn cây
       gốc x                             · r = x.left.size + 1
       · r = x.left.size + 1 là hạng     · leo từ x lên gốc; mỗi khi nút
         của x trong cây con gốc x         hiện tại y là con PHẢI, cộng
       · i = r: trả về x                   thêm y.p.left.size + 1 vào r
       · i < r: tìm thứ i bên trái       · bất biến: r là hạng của x
       · i > r: tìm thứ (i − r) bên phải   trong cây con gốc y
       · ví dụ: thứ 17 trong cây mẫu     · ví dụ: nút 38 có hạng 17
         là khoá 38                      · O(lg n): mỗi vòng leo 1 mức
       · O(lg n): mỗi lần gọi xuống 1 mức
               └────────────────┬────────────────┘
                                ▼
       DUY TRÌ size KHI CHÈN (hai pha, theo Mục 13.3)
       · pha 1 (đi xuống): tăng x.size cho mọi nút trên đường đi từ gốc;
         nút mới có size = 1 → thêm O(lg n)
       · pha 2 (đi lên, đổi màu, quay): chỉ phép quay làm thay đổi cấu
         trúc, nhiều nhất 2 phép; mỗi phép quay chỉ làm sai size của 2
         nút nằm hai đầu cạnh được quay → thêm 2 dòng vào LEFT-ROTATE:
           13  y.size = x.size
           14  x.size = x.left.size + x.right.size + 1
         → thêm O(1)
                                │
                                ▼
       DUY TRÌ size KHI XOÁ (hai pha, theo Mục 13.4)
       · pha 1: nút y bị gỡ khỏi cây hoặc bị dời lên vị trí khác; giảm
         size của mọi nút trên đường từ vị trí ban đầu của y lên gốc
         → thêm O(lg n)
       · pha 2: nhiều nhất 3 phép quay, mỗi phép sửa size như trên
         → thêm O(1)
                                │
                                ▼
       KẾT QUẢ: INSERT, DELETE, OS-SELECT, OS-RANK đều O(lg n) trên cây
       thống kê thứ tự n nút
```

### Mục 14.2 — Cách mở rộng một cấu trúc dữ liệu (How to augment a data structure, trang 345–348)

```text
       QUY TRÌNH BỐN BƯỚC
       1. Chọn cấu trúc dữ liệu nền
       2. Xác định thông tin bổ sung cần duy trì trong cấu trúc nền
       3. Kiểm tra rằng các thao tác sửa đổi cơ bản của cấu trúc nền
          duy trì được thông tin bổ sung
       4. Xây dựng thao tác mới
       · không làm máy móc theo thứ tự: thiết kế có thử và sai, các
         bước thường tiến song song (chọn thông tin ở bước 2 mà bước 3
         không duy trì nổi thì vô ích)
       · bốn bước cũng là khung tốt để viết tài liệu cho cấu trúc
                                │
                                ▼
       ÁP DỤNG LẠI CHO MỤC 14.1
       · bước 1: cây đỏ-đen, vì đã hỗ trợ tốt MINIMUM, MAXIMUM,
         SUCCESSOR, PREDECESSOR trên thứ tự toàn phần
       · bước 2: thuộc tính size (không có nó, OS-SELECT, OS-RANK vẫn
         viết được nhưng không đạt O(lg n))
       · bước 3: chèn, xoá vẫn O(lg n). Phản ví dụ: nếu lưu HẠNG TRONG
         TOÀN CÂY ở mỗi nút thì truy vấn nhanh, nhưng chèn một phần tử
         nhỏ nhất mới làm thay đổi thông tin ở MỌI nút; lưu size thì
         chèn chỉ làm thay đổi O(lg n) nút
       · bước 4: OS-SELECT, OS-RANK (đôi khi thông tin thêm chỉ để tăng
         tốc thao tác cũ, như bài tập 14.2-1)
                                │
                                ▼
       ĐỊNH LÝ 14.1 (mở rộng cây đỏ-đen)
       Nếu thuộc tính f của mỗi nút x chỉ phụ thuộc vào thông tin ở các
       nút x, x.left, x.right (kể cả x.left.f, x.right.f), thì duy trì
       được f ở mọi nút khi chèn và xoá mà thời gian vẫn O(lg n)
                                │
                                ▼
       Ý CHÍNH CỦA CHỨNG MINH
       · đổi x.f chỉ có thể làm đổi f của TỔ TIÊN của x; cập nhật lan dần
         lên tới gốc rồi dừng → O(lg n) cho mỗi thay đổi
       · chèn: tính f cho nút mới trong O(1) (hai con đều là T.nil), lan
         lên O(lg n); mỗi phép quay đổi 2 nút, lan lên O(lg n); ≤ 2 phép
         quay → tổng O(lg n)
       · xoá: thay đổi cục bộ khi gỡ nút (hoặc dời nút kế tiếp vào chỗ
         nút bị xoá), lan lên O(lg n); ≤ 3 phép quay, mỗi phép O(lg n)
         → tổng O(lg n)
       · thực tế nhiều thuộc tính (như size) chỉ cần O(1) mỗi phép quay
```

### Mục 14.3 — Cây khoảng (Interval trees, trang 348–354)

```text
       ĐỊNH NGHĨA
       · khoảng đóng [t₁, t₂] với t₁ ≤ t₂ là tập {t ∈ ℝ : t₁ ≤ t ≤ t₂};
         khoảng mở / nửa mở bỏ cả hai / một đầu mút. Mục này chỉ xét
         khoảng đóng
       · biểu diễn khoảng bằng đối tượng i với i.low = t₁ (đầu mút dưới),
         i.high = t₂ (đầu mút trên)
       · i và i′ GIAO NHAU (overlap) khi i ∩ i′ ≠ ∅, tức là
         i.low ≤ i′.high và i′.low ≤ i.high
       · TAM PHÂN KHOẢNG (interval trichotomy): với hai khoảng bất kỳ,
         đúng MỘT trong ba điều xảy ra: (a) giao nhau; (b) i nằm bên trái
         i′ (i.high < i′.low); (c) i nằm bên phải i′ (i′.high < i.low)
                                │
                                ▼
       CÂY KHOẢNG: cây đỏ-đen, mỗi phần tử x chứa khoảng x.int; hỗ trợ
       INTERVAL-INSERT(T, x), INTERVAL-DELETE(T, x),
       INTERVAL-SEARCH(T, i) (trả về một nút có khoảng giao với i, hoặc
       T.nil nếu không có)
                                │
                                ▼
       THIẾT KẾ THEO BỐN BƯỚC
       · bước 1: cây đỏ-đen, khoá của x là x.int.low → duyệt giữa liệt kê
         các khoảng theo đầu mút dưới tăng dần
       · bước 2: x.max = giá trị đầu mút lớn nhất trong cây con gốc x
       · bước 3: x.max = max(x.int.high, x.left.max, x.right.max), chỉ
         phụ thuộc x và hai con → theo Định lý 14.1, chèn và xoá vẫn
         O(lg n) (thực tế sửa max sau phép quay chỉ mất O(1))
       · bước 4: INTERVAL-SEARCH
                                │
                                ▼
       INTERVAL-SEARCH(T, i): đi MỘT đường từ gốc xuống
       · dừng khi x = T.nil hoặc x.int giao với i
       · nếu x.left ≠ T.nil và x.left.max ≥ i.low: sang trái
       · ngược lại: sang phải
       · O(lg n)
       · ví dụ trên cây mẫu: i = [22, 25] tìm thấy [15, 23];
         i = [11, 14] trả về T.nil
                                │
                                ▼
       ĐỊNH LÝ 14.2: INTERVAL-SEARCH hoặc trả về nút có khoảng giao với i,
       hoặc trả về T.nil và khi đó cây KHÔNG có khoảng nào giao với i
       · bất biến: nếu cây có khoảng giao với i thì cây con gốc x cũng có
       · rẽ phải vì x.left.max < i.low: mọi i′ bên trái có
         i′.high ≤ x.left.max < i.low → không giao
       · rẽ trái vì x.left.max ≥ i.low: có i′ bên trái với
         i′.high = x.left.max ≥ i.low; nếu i′ không giao i thì
         i.high < i′.low ≤ i″.low với mọi i″ bên phải → bên phải cũng
         không có khoảng nào giao; vậy rẽ trái không bỏ sót gì
```

### Phần Bài toán cuối chương (Problems, trang 354–355)

```text
       14-1 ĐIỂM CHỒNG LẤN NHIỀU NHẤT (Point of maximum overlap)
       · a. luôn có một điểm chồng lấn nhiều nhất là đầu mút của một
            khoảng
       · b. cấu trúc hỗ trợ INTERVAL-INSERT, INTERVAL-DELETE, FIND-POM
            (gợi ý: cây đỏ-đen chứa mọi đầu mút; đầu mút trái mang +1,
            đầu mút phải mang −1; gắn thêm thông tin vào mỗi nút)
                                │
                                ▼
       14-2 HOÁN VỊ JOSEPHUS (Josephus permutation)
       · n người xếp vòng tròn, cứ đếm tới người thứ m thì loại người
         đó; thứ tự bị loại là hoán vị Josephus (n, m)
       · ví dụ: (7, 3) cho ⟨3, 6, 2, 7, 5, 1, 4⟩
       · a. m là hằng số: thuật toán O(n)
       · b. m không phải hằng số: thuật toán O(n lg n) (dùng cây thống
            kê thứ tự)
```

### Phần Ghi chú chương (Chapter notes, trang 355)

```text
       Preparata và Shamos, trong sách hình học tính toán của họ, mô tả
       nhiều loại cây khoảng trong tài liệu, dẫn công trình của
       H. Edelsbrunner (1980) và E. M. McCreight (1981)
                                │
                                ▼
       Sách đó trình bày một cây khoảng cho tập n khoảng TĨNH, liệt kê
       được TẤT CẢ k khoảng giao với một khoảng truy vấn trong O(k + lg n)
```

## Ba câu hỏi chương này trả lời

1. **Làm sao tìm phần tử nhỏ thứ i và tính hạng của một phần tử trong một tập động, mỗi việc trong O(lg n)?** Dùng cây thống kê thứ tự: cây đỏ-đen trong đó mỗi nút x lưu x.size = x.left.size + x.right.size + 1 (T.nil.size = 0). OS-SELECT(x, i) tính r = x.left.size + 1 (hạng của x trong cây con của nó); nếu i = r trả về x, nếu i < r tìm thứ i ở cây con trái, nếu i > r tìm thứ i − r ở cây con phải. OS-RANK(T, x) bắt đầu với r = x.left.size + 1 rồi leo lên gốc, mỗi khi nút hiện tại y là con phải thì cộng y.p.left.size + 1. Cả hai đi qua tối đa một đường dài bằng chiều cao cây, tức O(lg n). Trên cây mẫu 20 nút, tìm phần tử thứ 17 đi qua 26 (hạng 13) → 41 (hạng 6 trong cây con, tìm thứ 4) → 30 (hạng 2, tìm thứ 2 bên phải) → 38 (hạng 2) và trả về khoá 38; OS-RANK của nút 38 cho r lần lượt 2, 4, 4, 17.
2. **Khi nào thông tin bổ sung vào cây đỏ-đen được duy trì "miễn phí" qua chèn và xoá?** Theo Định lý 14.1: khi giá trị f ở nút x chỉ phụ thuộc vào thông tin của x, x.left và x.right (kể cả x.left.f, x.right.f). Lý do: thay đổi f ở một nút chỉ lan lên các tổ tiên, mất O(lg n); chèn gồm một pha đi xuống (O(lg n)) cộng nhiều nhất 2 phép quay, xoá gồm một pha gỡ nút (O(lg n)) cộng nhiều nhất 3 phép quay, mỗi phép quay chỉ đổi 2 nút. Vậy tổng vẫn O(lg n). Với size và max, mỗi phép quay chỉ cần O(1): ví dụ thêm `y.size = x.size` và `x.size = x.left.size + x.right.size + 1` vào cuối LEFT-ROTATE. Ngược lại, hạng trong toàn cây hay độ sâu của nút *không* thoả tiêu chí — chèn một phần tử nhỏ nhất làm đổi hạng của mọi nút.
3. **Làm sao tìm nhanh một khoảng trong tập động giao với khoảng truy vấn i?** Dùng cây khoảng: cây đỏ-đen khoá theo đầu mút dưới, mỗi nút lưu x.max = max(x.int.high, x.left.max, x.right.max). INTERVAL-SEARCH đi một đường từ gốc: nếu x.int không giao i, rẽ trái khi x.left ≠ T.nil và x.left.max ≥ i.low, ngược lại rẽ phải. Theo Định lý 14.2, cách rẽ này không bao giờ bỏ sót: rẽ phải chỉ khi mọi khoảng bên trái kết thúc trước i.low; rẽ trái khi có khoảng i′ bên trái kết thúc ở x.left.max ≥ i.low, và nếu i′ không giao i thì i kết thúc trước i′.low, mà mọi khoảng bên phải bắt đầu sau i′.low, nên bên phải cũng không có gì. Thời gian O(lg n). Trên cây mẫu 10 khoảng, i = [22, 25] đi qua [16, 21] → [8, 9] → [15, 23] và trả về [15, 23]; i = [11, 14] đi qua [16, 21] → [8, 9] → [15, 23] → T.nil và đúng là không khoảng nào giao [11, 14].

## Khái niệm cần biết

- **Mở rộng cấu trúc dữ liệu (augmenting a data structure):** lấy một cấu trúc có sẵn và lưu thêm thông tin vào các phần tử (thường là vào mỗi nút) để hỗ trợ thao tác mới hoặc tăng tốc thao tác cũ. Ví dụ: thêm trường size vào nút cây đỏ-đen biến nó thành cây thống kê thứ tự. Quan trọng vì đây là chủ đề của cả chương: cái khó không nằm ở thao tác mới mà ở chỗ chứng minh chèn, xoá vẫn duy trì được thông tin thêm với chi phí cũ.
- **Thống kê thứ tự thứ i (ith order statistic):** phần tử có khoá nhỏ thứ i trong tập n phần tử, i ∈ {1, 2, …, n}. Ví dụ: trong tập {3, 7, 10, 12, 14, 14, 16, 17, 19, 20, 21, 21, 26, 28, 30, 35, 38, 39, 41, 47}, thống kê thứ tự thứ 17 là 38. Chương 9 tìm nó trong O(n) cho tập tĩnh; chương này làm trong O(lg n) cho tập động.
- **Hạng (rank) của một phần tử:** vị trí của phần tử trong thứ tự tuyến tính của tập. Khi khoá có thể trùng, sách định nghĩa hạng là vị trí mà nút được in ra trong phép duyệt giữa. Ví dụ: trong cây mẫu có hai khoá 14 — nút 14 màu đen (cha của 10 và 16) có hạng 5, nút 14 màu đỏ (con trái của 16) có hạng 6.
- **Cây thống kê thứ tự (order-statistic tree):** cây đỏ-đen mà mỗi nút x có thêm x.size = số nút trong (không kể lính canh) của cây con gốc x. Ví dụ: nút 30 trong cây mẫu có cây con gồm {28, 30, 35, 38, 39} nên 30.size = 5 = 28.size (1) + 38.size (3) + 1. Quan trọng vì đây là ví dụ mẫu của kỹ thuật mở rộng, và là công cụ để giải bài tập nghịch thế, dây cung, Josephus.
- **Lính canh (sentinel) T.nil:** nút giả thay cho mọi con trỏ NIL trong cây đỏ-đen (Chương 13). Quy ước T.nil.size = 0 giúp đẳng thức x.size = x.left.size + x.right.size + 1 đúng cả với lá, không phải xử lý trường hợp riêng. Ví dụ: lá 3 có 3.size = 0 + 0 + 1 = 1.
- **Phép quay (rotation):** thao tác cục bộ của Chương 13 đổi chỗ cha–con giữa hai nút mà vẫn giữ tính chất cây tìm kiếm. LEFT-ROTATE(T, x) với y = x.right biến y thành cha và x thành con trái của y; con trái cũ của y thành con phải của x. Chỉ x và y đổi tập con cháu, nên chỉ hai nút này cần sửa thông tin bổ sung. Ví dụ (Hình 14.2): trước khi quay, x = 42 có size 19, y = 93 có size 12 với các cây con kích thước 6, 4, 7; sau LEFT-ROTATE(T, x), y.size = 19 (lấy size cũ của x) và x.size = 6 + 4 + 1 = 11.
- **Thuộc tính phụ thuộc cục bộ (attribute depending only on x, x.left, x.right):** điều kiện của Định lý 14.1. Ví dụ đạt: size, max của cây khoảng, tổng khoá trong cây con, chiều cao đen. Ví dụ không đạt: hạng trong toàn cây (phụ thuộc vào các nút ở ngoài cây con), độ sâu (phụ thuộc vào tổ tiên). Quan trọng vì đây là tiêu chí nhanh để biết bước 3 của quy trình có dễ hay không.
- **Khoảng đóng, khoảng mở, khoảng nửa mở (closed, open, half-open interval):** [t₁, t₂] = {t ∈ ℝ : t₁ ≤ t ≤ t₂}; khoảng mở bỏ cả hai đầu mút, nửa mở bỏ một. Ví dụ: [8, 9] và [9, 12] giao nhau tại điểm 9, nhưng (8, 9) và (9, 12) thì không. Quan trọng vì điều kiện giao nhau (và do đó INTERVAL-SEARCH) phụ thuộc vào loại khoảng (bài tập 14.3-2).
- **Đầu mút dưới, đầu mút trên (low endpoint, high endpoint):** i.low = t₁, i.high = t₂. Cây khoảng dùng i.low làm khoá.
- **Giao nhau (overlap):** i và i′ giao nhau khi i.low ≤ i′.high và i′.low ≤ i.high. Ví dụ: [22, 25] và [15, 23]: 22 ≤ 23 và 15 ≤ 25 nên giao nhau; [22, 25] và [16, 21]: 22 ≤ 21 sai nên không giao.
- **Tam phân khoảng (interval trichotomy):** với hai khoảng đóng bất kỳ i, i′, đúng một trong ba điều: giao nhau; i bên trái i′ (i.high < i′.low); i bên phải i′ (i′.high < i.low). Ví dụ: [0, 3] và [5, 8]: 3 < 5 nên [0, 3] bên trái. Đây là công cụ chính trong chứng minh Định lý 14.2.
- **Cây khoảng (interval tree):** cây đỏ-đen, mỗi nút chứa khoảng x.int, khoá x.int.low, thông tin thêm x.max = max(x.int.high, x.left.max, x.right.max). Ví dụ: nút [8, 9] trong cây mẫu có con [5, 8] (max 10) và [15, 23] (max 23) nên [8, 9].max = max(9, 10, 23) = 23.
- **Bất biến vòng lặp (loop invariant):** mệnh đề đúng trước mỗi lần lặp, chứng minh bằng ba bước khởi tạo, duy trì, kết thúc (Chương 2). Chương này dùng hai bất biến: của OS-RANK ("r là hạng của x trong cây con gốc y") và của INTERVAL-SEARCH ("nếu cây có khoảng giao với i thì cây con gốc x cũng có").
- **Phản đảo (contrapositive):** "nếu P thì Q" tương đương "nếu không Q thì không P". Chứng minh Định lý 14.2 dùng phản đảo của bất biến khi rẽ trái: nếu cây con trái không có khoảng nào giao với i thì cả cây cũng không.

## Nội dung chi tiết

### 1. Mở đầu chương: vì sao mở rộng một cấu trúc giáo khoa (phần mở đầu Chương 14, trang 339)

Các tác giả mở chương bằng nhận xét thực tế: một số tình huống kỹ thuật chỉ cần một cấu trúc dữ liệu "giáo khoa" như danh sách liên kết kép, bảng băm hay cây tìm kiếm nhị phân, nhưng nhiều tình huống khác cần thêm một chút sáng tạo. Tuy vậy, hiếm khi phải tạo ra một kiểu cấu trúc hoàn toàn mới; thường chỉ cần **mở rộng** một cấu trúc có sẵn bằng cách lưu thêm thông tin vào nó, rồi lập trình các thao tác mới cho ứng dụng. Việc mở rộng không phải lúc nào cũng đơn giản, vì thông tin thêm vào phải được cập nhật và duy trì bởi chính các thao tác thông thường của cấu trúc nền.

Chương trình bày hai cấu trúc xây dựng bằng cách mở rộng cây đỏ-đen. Mục 14.1 mô tả cấu trúc hỗ trợ các thao tác thống kê thứ tự tổng quát trên một tập động: tìm nhanh số nhỏ thứ i, hoặc hạng của một phần tử cho trước. Mục 14.2 trừu tượng hoá quá trình mở rộng và chứng minh một định lý giúp việc mở rộng cây đỏ-đen trở nên đơn giản. Mục 14.3 dùng định lý đó để thiết kế cấu trúc duy trì một tập động các khoảng (chẳng hạn các khoảng thời gian), sao cho với một khoảng truy vấn, ta tìm nhanh được một khoảng trong tập giao với nó.

### 2. Thống kê thứ tự động (14.1 Dynamic order statistics, trang 339–345)

Chương 9 đã định nghĩa thống kê thứ tự thứ i của tập n phần tử (i ∈ {1, 2, …, n}) là phần tử có khoá nhỏ thứ i, và chỉ ra cách tìm bất kỳ thống kê thứ tự nào trong O(n) từ một tập không sắp xếp. Mục này sửa cây đỏ-đen để tìm bất kỳ thống kê thứ tự nào của một **tập động** trong O(lg n), và tính **hạng** của một phần tử — vị trí của nó trong thứ tự tuyến tính của tập — cũng trong O(lg n).

#### Cây thống kê thứ tự (trang 340)

Một **cây thống kê thứ tự** T đơn giản là cây đỏ-đen có lưu thêm thông tin ở mỗi nút. Ngoài các thuộc tính thông thường x.key, x.color, x.p, x.left, x.right, mỗi nút x có thêm x.size: số nút (trong, tức không kể lính canh) của cây con gốc x, tính cả x. Nếu đặt kích thước của lính canh bằng 0 (T.nil.size = 0), ta có đẳng thức

x.size = x.left.size + x.right.size + 1.

Cây thống kê thứ tự không đòi hỏi khoá phân biệt. Khi có khoá trùng, khái niệm hạng ở trên không còn xác định rõ; sách loại bỏ sự mơ hồ bằng cách định nghĩa hạng của một phần tử là vị trí mà nó được in ra trong phép duyệt giữa của cây.

**Hình 14.1 — Một cây thống kê thứ tự (cây đỏ-đen mở rộng).** Mỗi nút ghi "khoá [màu, size]"; cây có 20 nút, có hai khoá 14 và hai khoá 21.

```text
26 [đen, size 20]
├── trái: 17 [đỏ, 12]
│   ├── trái: 14 [đen, 7]
│   │   ├── trái: 10 [đỏ, 4]
│   │   │   ├── trái: 7 [đen, 2]
│   │   │   │   └── trái: 3 [đỏ, 1]
│   │   │   └── phải: 12 [đen, 1]
│   │   └── phải: 16 [đen, 2]
│   │       └── trái: 14 [đỏ, 1]
│   └── phải: 21 [đen, 4]
│       ├── trái: 19 [đen, 2]
│       │   └── phải: 20 [đỏ, 1]
│       └── phải: 21 [đen, 1]
└── phải: 41 [đen, 7]
    ├── trái: 30 [đỏ, 5]
    │   ├── trái: 28 [đen, 1]
    │   └── phải: 38 [đen, 3]
    │       ├── trái: 35 [đỏ, 1]
    │       └── phải: 39 [đỏ, 1]
    └── phải: 47 [đen, 1]
```

Kiểm tra đẳng thức size: 10.size = 7.size (2) + 12.size (1) + 1 = 4; 14.size (nút đen) = 4 + 2 + 1 = 7; 17.size = 7 + 4 + 1 = 12; 41.size = 5 + 1 + 1 = 7; 26.size = 12 + 7 + 1 = 20. Mọi đường từ gốc xuống lá đều qua đúng 3 nút đen (ví dụ 26–14–7, 26–21–19, 26–41–38), nên đây là cây đỏ-đen hợp lệ.

Thứ tự duyệt giữa và hạng của từng nút (người tổng hợp liệt kê để tiện theo dõi các ví dụ):

| Hạng | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Khoá | 3 | 7 | 10 | 12 | 14 (đen) | 14 (đỏ) | 16 | 17 | 19 | 20 | 21 (cha của 19) | 21 (lá) | 26 | 28 | 30 | 35 | 38 | 39 | 41 | 47 |

Như sách nêu, khoá 14 ở nút đen có hạng 5 và khoá 14 ở nút đỏ có hạng 6.

#### Lấy phần tử có hạng cho trước (Retrieving an element with a given rank, trang 340–341)

Thủ tục OS-SELECT(x, i) trả về con trỏ tới nút chứa khoá nhỏ thứ i trong cây con gốc x. Để tìm khoá nhỏ thứ i trong cả cây T, gọi OS-SELECT(T.root, i).

```text
OS-SELECT(x, i)
1  r = x.left.size + 1
2  if i == r
3      return x
4  elseif i < r
5      return OS-SELECT(x.left, i)
6  else return OS-SELECT(x.right, i − r)
```

Giải thích từng dòng:

- **Dòng 1** tính r, hạng của nút x trong cây con gốc x. Giá trị x.left.size là số nút đứng trước x trong phép duyệt giữa của cây con gốc x, nên x.left.size + 1 là hạng của x trong cây con đó.
- **Dòng 2–3:** nếu i = r thì x chính là phần tử nhỏ thứ i; trả về x.
- **Dòng 4–5:** nếu i < r thì phần tử nhỏ thứ i nằm trong cây con trái của x; đệ quy trên x.left với cùng i.
- **Dòng 6:** nếu i > r thì phần tử cần tìm nằm trong cây con phải. Cây con gốc x có r phần tử đứng trước cây con phải của x trong phép duyệt giữa (x.left.size phần tử bên trái cộng chính x), nên phần tử nhỏ thứ i của cây con gốc x là phần tử nhỏ thứ (i − r) của cây con gốc x.right.

**Ví dụ chạy tay (trang 341): tìm phần tử nhỏ thứ 17 trong cây của Hình 14.1.**

| Bước | Nút x | i | x.left.size | r = hạng của x trong cây con | Quyết định |
|---|---|---|---|---|---|
| 1 | 26 | 17 | 12 (cây con gốc 17) | 13 | i > r: sang phải, tìm thứ 17 − 13 = 4 |
| 2 | 41 | 4 | 5 (cây con gốc 30) | 6 | i < r: sang trái, vẫn tìm thứ 4 |
| 3 | 30 | 4 | 1 (cây con gốc 28) | 2 | i > r: sang phải, tìm thứ 4 − 2 = 2 |
| 4 | 38 | 2 | 1 (cây con gốc 35) | 2 | i = r: trả về nút 38 |

Kết quả khớp với bảng hạng: khoá 38 có hạng 17.

**Thời gian chạy.** Mỗi lần gọi đệ quy đi xuống một mức, nên tổng thời gian tỷ lệ với chiều cao cây trong trường hợp xấu nhất. Cây đỏ-đen n nút có chiều cao O(lg n) (Chương 13 chứng minh chiều cao ≤ 2 lg(n + 1)), nên OS-SELECT chạy trong O(lg n).

#### Xác định hạng của một phần tử (Determining the rank of an element, trang 341–343)

Cho con trỏ tới nút x trong cây thống kê thứ tự T, thủ tục OS-RANK trả về vị trí của x trong thứ tự tuyến tính xác định bởi phép duyệt giữa của T.

```text
OS-RANK(T, x)
1  r = x.left.size + 1
2  y = x
3  while y ≠ T.root
4      if y == y.p.right
5          r = r + y.p.left.size + 1
6      y = y.p
7  return r
```

Có thể nghĩ về hạng của x như số nút đứng trước x trong phép duyệt giữa, cộng 1 cho chính x. Dòng 1 đếm phần đứng trước x bên trong cây con của x; vòng lặp dòng 3–6 leo dần lên gốc và cộng thêm các nút đứng trước x nằm ngoài cây con hiện tại. OS-RANK duy trì bất biến vòng lặp:

> Ở đầu mỗi lần lặp của vòng **while** dòng 3–6, r là hạng của x.key trong cây con gốc y.

(Như đã ghi ở khối Lưu ý, khi có khoá trùng nên hiểu là "hạng của nút x".)

- **Khởi tạo:** trước lần lặp đầu, dòng 1 đặt r bằng hạng của x trong cây con gốc x; dòng 2 đặt y = x, nên bất biến đúng lần đầu kiểm tra dòng 3.
- **Duy trì:** cuối mỗi lần lặp ta đặt y = y.p, nên cần chứng minh: nếu đầu thân vòng lặp r là hạng của x trong cây con gốc y, thì cuối thân vòng lặp r là hạng của x trong cây con gốc y.p. Trong cây con gốc y.p, các nút đứng trước x gồm: những nút trong cây con gốc y đứng trước x (đã đếm), những nút trong cây con của anh/em ruột của y đứng trước x, và y.p nếu y.p cũng đứng trước x. Nếu y là con trái, cả y.p lẫn mọi nút trong cây con phải của y.p đều đứng sau x, nên r giữ nguyên. Nếu y là con phải, mọi nút trong cây con trái của y.p đều đứng trước x, và y.p cũng vậy; vì thế dòng 5 cộng y.p.left.size + 1 vào r.
- **Kết thúc:** vòng lặp dừng khi y = T.root, cây con gốc y là cả cây, nên r là hạng của x trong toàn cây.

**Ví dụ chạy tay (trang 342–343): tính hạng của nút có khoá 38 trong Hình 14.1.** Giá trị của y.key và r ở đầu mỗi vòng **while**:

| Lần lặp | y.key | r | Giải thích (người tổng hợp bổ sung) |
|---|---|---|---|
| 1 | 38 | 2 | r = 35.size + 1 = 2; 38 là con phải của 30 nên cộng 30.left.size + 1 = 1 + 1 |
| 2 | 30 | 4 | 30 là con trái của 41, không cộng |
| 3 | 41 | 4 | 41 là con phải của 26, cộng 26.left.size + 1 = 12 + 1 |
| 4 | 26 | 17 | y là gốc, vòng lặp dừng |

Thủ tục trả về hạng 17.

**Thời gian chạy.** Mỗi lần lặp mất O(1) và y đi lên một mức, nên OS-RANK chạy trong thời gian tỷ lệ với chiều cao cây: O(lg n) trên cây thống kê thứ tự n nút.

#### Duy trì kích thước cây con (Maintaining subtree sizes, trang 343–344)

Có thuộc tính size ở mỗi nút thì OS-SELECT và OS-RANK tính nhanh được thông tin thống kê thứ tự. Nhưng nếu các thao tác sửa đổi cơ bản của cây đỏ-đen không duy trì được size một cách hiệu quả thì mọi công sức trên là vô ích. Sách chỉ ra cách duy trì size khi chèn và khi xoá mà không làm thay đổi thời gian tiệm cận của hai thao tác này.

**Chèn.** Theo Mục 13.3, chèn vào cây đỏ-đen gồm hai pha. Pha thứ nhất đi xuống từ gốc và gắn nút mới làm con của một nút có sẵn. Pha thứ hai đi lên, đổi màu và quay để khôi phục các tính chất đỏ-đen.

- Pha 1: chỉ cần tăng x.size thêm 1 cho mọi nút x trên đường đơn đi từ gốc xuống; nút mới có size = 1. Đường đi có O(lg n) nút, nên chi phí thêm là O(lg n).
- Pha 2: thay đổi cấu trúc duy nhất là các phép quay, nhiều nhất 2 phép. Một phép quay là thao tác cục bộ: chỉ 2 nút bị sai size, và cạnh được quay nối đúng hai nút này. Với mã LEFT-ROTATE(T, x) của Mục 13.2, ta thêm hai dòng 13–14.

Mã LEFT-ROTATE của Mục 13.2 (chép lại để tự chứa; giả định x.right ≠ T.nil và cha của gốc là T.nil), cùng hai dòng thêm của Chương 14:

```text
LEFT-ROTATE(T, x)
 1  y = x.right                  // đặt y
 2  x.right = y.left             // cây con trái của y thành cây con phải của x
 3  if y.left ≠ T.nil
 4      y.left.p = x
 5  y.p = x.p                    // nối cha của x với y
 6  if x.p == T.nil
 7      T.root = y
 8  elseif x == x.p.left
 9      x.p.left = y
10  else x.p.right = y
11  y.left = x                   // đặt x làm con trái của y
12  x.p = y
13  y.size = x.size              // dòng thêm ở Chương 14
14  x.size = x.left.size + x.right.size + 1   // dòng thêm ở Chương 14
```

Dòng 13 đúng vì sau phép quay, y đứng ở vị trí cũ của x và cây con của nó gồm đúng các nút cây con cũ của x. Dòng 14 tính lại size của x từ hai con mới (cây con trái cũ của x và cây con trái cũ của y). Thứ tự hai dòng quan trọng: phải lấy x.size cũ cho y trước khi tính lại x.size. RIGHT-ROTATE thay đổi đối xứng.

**Hình 14.2 — Cập nhật size khi quay.** Cạnh được quay nối đúng hai nút cần cập nhật; việc cập nhật cục bộ, chỉ cần size của x, y và gốc của ba cây con (vẽ là tam giác).

```text
   Sau LEFT-ROTATE(T, x)                   Trước LEFT-ROTATE(T, x)
   (trước RIGHT-ROTATE(T, y))              (sau RIGHT-ROTATE(T, y))

            93 = y                                  42 = x
           size 19                                 size 19
          /       \                               /       \
     42 = x       [cây con                   [cây con     93 = y
     size 11       size 7]                    size 6]     size 12
     /     \                                              /     \
 [cây con [cây con                                   [cây con [cây con
  size 6]  size 4]                                    size 4]  size 7]

  ◄──── LEFT-ROTATE(T, x) biến hình phải thành hình trái
  ────► RIGHT-ROTATE(T, y) biến hình trái thành hình phải
```

Kiểm tra: trước khi quay, x.size = 6 + 12 + 1 = 19 và y.size = 4 + 7 + 1 = 12. Sau LEFT-ROTATE, dòng 13 gán y.size = 19 và dòng 14 gán x.size = 6 + 4 + 1 = 11; quả thật 11 + 7 + 1 = 19.

Vì chèn có nhiều nhất 2 phép quay, pha 2 chỉ tốn thêm O(1) cho việc cập nhật size. Tổng thời gian chèn vào cây thống kê thứ tự n nút là O(lg n), như cây đỏ-đen thường.

**Ví dụ chèn không cần quay (người tổng hợp bổ sung).** Chèn khoá 22 vào cây Hình 14.1: đường đi 26 → 17 → 21 (cha của 19) → 21 (lá), vì 22 > 21 nên nút mới thành con phải của lá 21. Pha 1 tăng size: 26: 20 → 21, 17: 12 → 13, 21 (trong): 4 → 5, 21 (lá): 1 → 2; nút 22 có size 1, màu đỏ. Cha của nó màu đen nên không cần sửa. Sau khi chèn, 22 có hạng 13 và 26 chuyển sang hạng 14; OS-RANK của nút 22 cho r = 1 → (22 là con phải của 21 lá: + 0 + 1) 2 → (21 lá là con phải của 21 trong: + 2 + 1) 5 → (21 trong là con phải của 17: + 7 + 1) 13 → (17 là con trái của 26: không cộng) 13.

**Xoá.** Theo Mục 13.4, xoá cũng có hai pha: pha thứ nhất làm việc trên cây tìm kiếm nền, pha thứ hai gây ra nhiều nhất 3 phép quay và ngoài ra không thay đổi cấu trúc.

- Pha 1: hoặc một nút y bị gỡ khỏi cây, hoặc y bị dời lên một vị trí khác trong cây (khi nút cần xoá có hai con, nút kế tiếp y được dời vào vị trí của nó). Để cập nhật size, đi theo đường đơn từ vị trí *ban đầu* của y lên gốc và giảm size của mỗi nút trên đường đi đi 1. Đường này dài O(lg n), nên chi phí thêm là O(lg n).
- Pha 2: xử lý O(1) phép quay giống như khi chèn.

Vậy cả chèn lẫn xoá, kể cả việc duy trì size, đều chạy trong O(lg n) trên cây thống kê thứ tự n nút.

#### Ví dụ hôm nay

Cây thống kê thứ tự và các biến thể cùng ý tưởng (lưu số phần tử của cây con để nhảy theo hạng) xuất hiện ở nhiều nơi, theo hiểu biết của người tổng hợp: thư viện GNU libstdc++ có `__gnu_pbds::tree` với chính sách `tree_order_statistics_node_update`, cung cấp `find_by_order` (tương ứng OS-SELECT) và `order_of_key` (tương ứng đếm số khoá nhỏ hơn), rất phổ biến trong lập trình thi đấu; Redis cài đặt tập có thứ tự (sorted set) bằng danh sách nhảy (skip list) có lưu "độ rộng" mỗi liên kết, cùng ý tưởng với size, để trả lời lệnh ZRANK và ZRANGE theo hạng trong O(lg n); bảng xếp hạng trò chơi, tính phân vị (percentile) trên luồng dữ liệu động, và cây B+ trong một số cơ sở dữ liệu lưu số bản ghi trong mỗi cây con để hỗ trợ đếm và nhảy theo vị trí (OFFSET) nhanh. Trình soạn thảo văn bản dùng cây rope, trong đó mỗi nút lưu độ dài chuỗi của cây con — đúng là thuộc tính size — để nhảy tới ký tự thứ i trong O(lg n).

### 3. Cách mở rộng một cấu trúc dữ liệu (14.2 How to augment a data structure, trang 345–348)

Quá trình mở rộng một cấu trúc dữ liệu cơ bản để có thêm chức năng xảy ra rất thường xuyên trong thiết kế thuật toán. Mục này xem xét các bước của quá trình đó và chứng minh một định lý cho phép mở rộng cây đỏ-đen dễ dàng trong nhiều trường hợp.

#### Quy trình bốn bước (trang 345–346)

Có thể chia quá trình mở rộng một cấu trúc dữ liệu thành bốn bước:

1. Chọn một cấu trúc dữ liệu nền.
2. Xác định thông tin bổ sung cần duy trì trong cấu trúc nền.
3. Kiểm tra rằng có thể duy trì thông tin bổ sung qua các thao tác sửa đổi cơ bản của cấu trúc nền.
4. Xây dựng các thao tác mới.

Như với mọi phương pháp thiết kế mang tính hướng dẫn, không nên làm máy móc theo đúng thứ tự trên. Phần lớn công việc thiết kế có yếu tố thử và sai, và các bước thường tiến song song. Ví dụ, chẳng có ích gì khi xác định thông tin bổ sung và xây dựng thao tác mới (bước 2 và 4) nếu ta không thể duy trì thông tin bổ sung một cách hiệu quả. Tuy vậy, phương pháp bốn bước giúp tập trung nỗ lực khi mở rộng một cấu trúc, và cũng là cách tốt để tổ chức tài liệu mô tả một cấu trúc đã mở rộng.

Mục 14.1 đã làm đúng theo bốn bước này để thiết kế cây thống kê thứ tự:

- **Bước 1:** chọn cây đỏ-đen làm cấu trúc nền. Dấu hiệu cho thấy cây đỏ-đen phù hợp là nó đã hỗ trợ hiệu quả các thao tác tập động khác trên một thứ tự toàn phần như MINIMUM, MAXIMUM, SUCCESSOR, PREDECESSOR.
- **Bước 2:** thêm thuộc tính size, mỗi nút x lưu kích thước cây con gốc x. Nói chung, thông tin bổ sung làm các thao tác hiệu quả hơn: có thể cài đặt OS-SELECT và OS-RANK chỉ bằng các khoá trong cây (ví dụ duyệt giữa và đếm), nhưng khi đó chúng không chạy trong O(lg n). Đôi khi thông tin bổ sung là con trỏ chứ không phải dữ liệu, như trong bài tập 14.2-1.
- **Bước 3:** bảo đảm chèn và xoá duy trì được size mà vẫn chạy trong O(lg n). Lý tưởng là chỉ phải cập nhật một số ít phần tử của cấu trúc. Phản ví dụ: nếu lưu ở mỗi nút hạng của nó trong *toàn cây*, OS-SELECT và OS-RANK sẽ chạy nhanh, nhưng chèn một phần tử nhỏ nhất mới làm thay đổi thông tin này ở *mọi* nút (mọi hạng tăng 1). Khi lưu kích thước cây con, chèn một phần tử chỉ làm thay đổi thông tin ở O(lg n) nút — các nút trên đường từ gốc tới vị trí chèn.
- **Bước 4:** xây dựng OS-SELECT và OS-RANK. Suy cho cùng, nhu cầu thao tác mới là lý do để mở rộng cấu trúc. Thỉnh thoảng, thay vì thao tác mới, ta dùng thông tin bổ sung để tăng tốc thao tác có sẵn, như trong bài tập 14.2-1.

#### Mở rộng cây đỏ-đen (Augmenting red-black trees, trang 346–347)

Khi cấu trúc nền là cây đỏ-đen, có thể chứng minh rằng chèn và xoá luôn duy trì hiệu quả được một số loại thông tin bổ sung, khiến bước 3 trở nên rất dễ. Chứng minh của định lý sau tương tự lập luận ở Mục 14.1 rằng ta duy trì được size cho cây thống kê thứ tự.

**Định lý 14.1 (Mở rộng cây đỏ-đen — Augmenting a red-black tree).** Cho f là một thuộc tính mở rộng cây đỏ-đen T có n nút, và giả sử giá trị của f ở mỗi nút x chỉ phụ thuộc vào thông tin trong các nút x, x.left và x.right, có thể bao gồm x.left.f và x.right.f. Khi đó, ta có thể duy trì giá trị f ở mọi nút của T trong khi chèn và xoá mà không ảnh hưởng tiệm cận tới hiệu năng O(lg n) của các thao tác này.

**Chứng minh.** Ý chính: thay đổi thuộc tính f ở một nút x chỉ lan tới các tổ tiên của x. Nghĩa là thay đổi x.f có thể buộc phải cập nhật x.p.f, nhưng không gì khác; cập nhật x.p.f có thể buộc phải cập nhật x.p.p.f, nhưng không gì khác; cứ thế lên trên. Khi đã cập nhật T.root.f, không nút nào khác phụ thuộc vào giá trị mới, nên quá trình kết thúc. Vì chiều cao cây đỏ-đen là O(lg n), thay đổi f ở một nút tốn O(lg n) để cập nhật mọi nút phụ thuộc.

- **Chèn** nút x vào T gồm hai pha (Mục 13.3). Pha một gắn x làm con của một nút có sẵn x.p. Có thể tính x.f trong O(1), vì theo giả thiết f chỉ phụ thuộc vào các thuộc tính khác của chính x và thông tin của hai con, mà hai con của x đều là lính canh T.nil. Tính xong x.f, thay đổi lan lên trên cây; vậy pha một tốn O(lg n). Trong pha hai, thay đổi cấu trúc duy nhất đến từ các phép quay. Mỗi phép quay chỉ thay đổi 2 nút, nên cập nhật f tốn O(lg n) cho mỗi phép quay. Chèn có nhiều nhất 2 phép quay, nên tổng thời gian chèn là O(lg n).
- **Xoá** cũng có hai pha (Mục 13.4). Trong pha một, cây thay đổi khi nút bị xoá được gỡ ra; nếu nút đó có hai con thì nút kế tiếp của nó được dời vào vị trí của nút bị xoá. Lan truyền các cập nhật f gây ra bởi những thay đổi này tốn nhiều nhất O(lg n), vì các thay đổi chỉ sửa cây một cách cục bộ. Pha hai sửa cây đỏ-đen với nhiều nhất 3 phép quay, mỗi phép cần nhiều nhất O(lg n) để lan truyền cập nhật f. Vậy giống như chèn, tổng thời gian xoá là O(lg n). ∎

Trong nhiều trường hợp, như duy trì size của cây thống kê thứ tự, chi phí cập nhật sau một phép quay chỉ là O(1) chứ không phải O(lg n) như trong chứng minh trên: sau phép quay, tập con cháu của mọi tổ tiên của hai nút được quay không đổi, nên giá trị f của chúng không cần lan truyền. Bài tập 14.2-3 cho một trường hợp tổng quát như vậy.

**Ví dụ áp dụng tiêu chí (người tổng hợp bổ sung).**

| Thuộc tính | Phụ thuộc chỉ vào x, x.left, x.right? | Duy trì được trong O(lg n)? |
|---|---|---|
| x.size = x.left.size + x.right.size + 1 | Có | Có (Mục 14.1) |
| x.max = max(x.int.high, x.left.max, x.right.max) | Có | Có (Mục 14.3) |
| tổng các khoá trong cây con: x.sum = x.left.sum + x.key + x.right.sum | Có | Có |
| chiều cao đen x.bh (xem bài tập 14.2-2) | Có: x.bh suy được từ chiều cao đen và màu của một con | Có |
| hạng của x trong toàn cây | Không: phụ thuộc vào các nút ngoài cây con | Không (chèn phần tử nhỏ nhất đổi Θ(n) giá trị) |
| độ sâu của x | Không: phụ thuộc vào tổ tiên | Không (một phép quay đổi độ sâu của cả một cây con) |

#### Ví dụ hôm nay

Tiêu chí của Định lý 14.1 chính là nền tảng của kỹ thuật "cây cân bằng có thông tin tổng hợp" (thường gọi là monoid-annotated tree hay augmented BST) dùng rộng rãi ngày nay, theo hiểu biết của người tổng hợp: cây ngón tay (finger tree) trong các thư viện lập trình hàm (ví dụ Data.Sequence của Haskell) gắn một giá trị thuộc một vị nhóm (monoid) vào mỗi nút, đúng như bài tập 14.2-3; cây treap/splay có "lazy propagation" trong lập trình thi đấu; cây Merkle gắn băm của cây con vào mỗi nút (băm phụ thuộc vào hai con), dùng trong Git, hệ thống tệp ZFS và blockchain; chỉ mục không gian R-tree lưu hình chữ nhật bao của cây con. Quy trình bốn bước cũng là khung tốt để viết tài liệu thiết kế cho một cấu trúc dữ liệu tự làm.

### 4. Cây khoảng (14.3 Interval trees, trang 348–354)

Mục này mở rộng cây đỏ-đen để hỗ trợ các thao tác trên tập động các khoảng.

#### Khoảng và tam phân khoảng (trang 348–349)

Một **khoảng đóng (closed interval)** là một cặp có thứ tự các số thực [t₁, t₂] với t₁ ≤ t₂. Khoảng [t₁, t₂] biểu diễn tập {t ∈ ℝ : t₁ ≤ t ≤ t₂}. **Khoảng mở (open)** và **nửa mở (half-open)** bỏ cả hai hoặc một trong hai đầu mút khỏi tập. Mục này giả định các khoảng là đóng; mở rộng kết quả cho khoảng mở và nửa mở về mặt khái niệm là đơn giản.

Khoảng tiện để biểu diễn các sự kiện mà mỗi sự kiện chiếm một đoạn thời gian liên tục. Chẳng hạn, ta có thể muốn truy vấn một cơ sở dữ liệu các khoảng thời gian để biết những sự kiện nào xảy ra trong một khoảng cho trước. Cấu trúc trong mục này là cách hiệu quả để duy trì một cơ sở dữ liệu khoảng như vậy.

Biểu diễn khoảng [t₁, t₂] bằng đối tượng i có thuộc tính i.low = t₁ (**đầu mút dưới**) và i.high = t₂ (**đầu mút trên**). Hai khoảng i và i′ **giao nhau (overlap)** nếu i ∩ i′ ≠ ∅, tức là nếu i.low ≤ i′.high và i′.low ≤ i.high. Hai khoảng bất kỳ i và i′ thoả **tam phân khoảng (interval trichotomy)**: đúng một trong ba tính chất sau đúng:

a. i và i′ giao nhau,
b. i nằm bên trái i′ (tức i.high < i′.low),
c. i nằm bên phải i′ (tức i′.high < i.low).

**Hình 14.3 — Tam phân khoảng cho hai khoảng đóng i và i′.**

```text
(a) i và i′ giao nhau: có bốn tình huống; trong cả bốn, i.low ≤ i′.high
    và i′.low ≤ i.high

    1) i nằm lệch phải, phủ đầu phải của i′
              ├────i────┤
         ├────i′───┤
       ─────────────────────►

    2) i chứa trọn i′
         ├──────i──────┤
            ├──i′──┤
       ─────────────────────►

    3) i nằm lệch trái, phủ đầu trái của i′
         ├────i────┤
              ├────i′───┤
       ─────────────────────►

    4) i nằm trọn trong i′
            ├──i──┤
         ├──────i′─────┤
       ─────────────────────►

(b) không giao nhau, i nằm bên trái i′ (i.high < i′.low)
         ├──i──┤   ├───i′───┤
       ─────────────────────────►

(c) không giao nhau, i nằm bên phải i′ (i′.high < i.low)
         ├───i′───┤   ├──i──┤
       ─────────────────────────►
```

Một **cây khoảng (interval tree)** là cây đỏ-đen duy trì một tập động các phần tử, mỗi phần tử x chứa một khoảng x.int. Cây khoảng hỗ trợ các thao tác:

- **INTERVAL-INSERT(T, x)** thêm phần tử x, có thuộc tính int được giả định chứa một khoảng, vào cây khoảng T.
- **INTERVAL-DELETE(T, x)** gỡ phần tử x khỏi cây khoảng T.
- **INTERVAL-SEARCH(T, i)** trả về con trỏ tới một phần tử x trong cây T sao cho x.int giao với khoảng i, hoặc con trỏ tới lính canh T.nil nếu tập không có phần tử như vậy.

Sách lần theo quy trình bốn bước của Mục 14.2 khi trình bày thiết kế cây khoảng.

#### Bước 1: Cấu trúc dữ liệu nền (Underlying data structure, trang 349)

Chọn cây đỏ-đen, trong đó mỗi nút x chứa một khoảng x.int và khoá của x là đầu mút dưới x.int.low của khoảng. Do đó, phép duyệt giữa liệt kê các khoảng theo thứ tự tăng dần của đầu mút dưới.

#### Bước 2: Thông tin bổ sung (Additional information, trang 349)

Ngoài chính các khoảng, mỗi nút x chứa giá trị x.max: giá trị lớn nhất trong mọi đầu mút của các khoảng lưu trong cây con gốc x. (Vì đầu mút trên luôn ≥ đầu mút dưới, x.max chính là đầu mút trên lớn nhất trong cây con.)

#### Bước 3: Duy trì thông tin (Maintaining the information, trang 349–350)

Cần kiểm tra rằng chèn và xoá chạy trong O(lg n) trên cây khoảng n nút. Có thể xác định x.max từ khoảng x.int và giá trị max của hai con của x:

x.max = max(x.int.high, x.left.max, x.right.max).

(Ngầm định T.nil.max = −∞ để công thức đúng ở lá.) Vì vậy, theo Định lý 14.1, chèn và xoá chạy trong O(lg n). Thực ra có thể cập nhật max sau một phép quay trong O(1), như bài tập 14.2-3 và 14.3-1 chỉ ra.

**Hình 14.4 — Một cây khoảng.** (a) Tập 10 khoảng, sắp xếp theo đầu mút dưới:

| Thứ tự theo đầu mút dưới | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Khoảng | [0, 3] | [5, 8] | [6, 10] | [8, 9] | [15, 23] | [16, 21] | [17, 19] | [19, 20] | [25, 30] | [26, 26] |

Vẽ trên trục số từ 0 đến 30 (mỗi khoảng một dòng, dưới lên trên theo đầu mút dưới):

```text
[26,26]                                                     │
[25,30]                                                   ├─────────┤
[19,20]                                       ├─┤
[17,19]                                   ├───┤
[16,21]                                 ├─────────┤
[15,23]                               ├───────────────┤
[8,9]                   ├─┤
[6,10]              ├───────┤
[5,8]             ├─────┤
[0,3]   ├─────┤
        ┼─────────┼─────────┼─────────┼─────────┼─────────┼─────────┼─►
        0         5         10        15        20        25        30
```

(b) Cây khoảng biểu diễn tập đó; mỗi nút ghi "khoảng [màu, max]":

```text
[16,21] [đen, max 30]
├── trái: [8,9] [đỏ, max 23]
│   ├── trái: [5,8] [đen, max 10]
│   │   ├── trái: [0,3] [đỏ, max 3]
│   │   └── phải: [6,10] [đỏ, max 10]
│   └── phải: [15,23] [đen, max 23]
└── phải: [25,30] [đỏ, max 30]
    ├── trái: [17,19] [đen, max 20]
    │   └── phải: [19,20] [đỏ, max 20]
    └── phải: [26,26] [đen, max 26]
```

Kiểm tra max: [5,8].max = max(8, 3, 10) = 10; [8,9].max = max(9, 10, 23) = 23; [17,19].max = max(19, −∞, 20) = 20; [25,30].max = max(30, 20, 26) = 30; gốc max = max(21, 23, 30) = 30. Duyệt giữa cho đúng thứ tự trong bảng (a).

#### Bước 4: Xây dựng thao tác mới (Developing new operations, trang 350–353)

Thao tác mới duy nhất cần có là INTERVAL-SEARCH(T, i), tìm một nút trong cây T có khoảng giao với khoảng i. Nếu cây không có khoảng nào giao với i, thủ tục trả về con trỏ tới lính canh T.nil.

```text
INTERVAL-SEARCH(T, i)
1  x = T.root
2  while x ≠ T.nil and i does not overlap x.int
3      if x.left ≠ T.nil and x.left.max ≥ i.low
4          x = x.left
5      else x = x.right
6  return x
```

Giải thích:

- **Dòng 1:** bắt đầu từ gốc.
- **Dòng 2:** lặp chừng nào chưa đi tới lính canh và khoảng ở nút hiện tại chưa giao với i (phép thử giao nhau: i.low ≤ x.int.high và x.int.low ≤ i.high).
- **Dòng 3–4:** nếu cây con trái khác rỗng và đầu mút lớn nhất trong cây con trái ≥ i.low, đi sang trái.
- **Dòng 5:** ngược lại, đi sang phải.
- **Dòng 6:** trả về x — hoặc một nút có khoảng giao với i, hoặc T.nil.

Tìm kiếm bắt đầu ở gốc và đi xuống, dừng khi tìm được khoảng giao nhau hoặc x trỏ tới T.nil. Mỗi lần lặp tốn O(1) và chiều cao cây đỏ-đen n nút là O(lg n), nên INTERVAL-SEARCH chạy trong O(lg n).

**Ví dụ chạy tay 1 (trang 351): tìm khoảng giao với i = [22, 25] trên cây Hình 14.4.**

| Bước | Nút x | x.int giao i? | x.left.max | So với i.low = 22 | Hướng đi |
|---|---|---|---|---|---|
| 1 | [16, 21] | không (21 < 22) | 23 | 23 ≥ 22 | trái |
| 2 | [8, 9] | không (9 < 22) | 10 | 10 < 22 | phải |
| 3 | [15, 23] | có (15 ≤ 25 và 22 ≤ 23) | — | — | dừng, trả về nút [15, 23] |

**Ví dụ chạy tay 2 (trang 351): tìm kiếm không thành công với i = [11, 14].**

| Bước | Nút x | x.int giao i? | x.left.max | So với i.low = 11 | Hướng đi |
|---|---|---|---|---|---|
| 1 | [16, 21] | không (16 > 14) | 23 | 23 ≥ 11 | trái |
| 2 | [8, 9] | không (9 < 11) | 10 | 10 < 11 | phải (không khoảng nào ở cây con trái giao với i) |
| 3 | [15, 23] | không (15 > 14) | x.left = T.nil | — | phải |
| 4 | T.nil | — | — | — | vòng lặp dừng, trả về T.nil |

Kiểm tra trực tiếp trên bảng (a): khoảng có đầu mút trên ≥ 11 đều có đầu mút dưới ≥ 15 > 14, nên đúng là không khoảng nào giao [11, 14].

Để thấy vì sao INTERVAL-SEARCH đúng, cần hiểu vì sao chỉ xét *một* đường đi từ gốc là đủ. Ý cơ bản: ở bất kỳ nút x nào, nếu x.int không giao i thì tìm kiếm luôn đi theo một hướng an toàn — nếu cây có khoảng giao với i thì tìm kiếm chắc chắn sẽ tìm thấy một khoảng như vậy.

**Định lý 14.2.** Mọi lần thực thi INTERVAL-SEARCH(T, i) hoặc trả về một nút có khoảng giao với i, hoặc trả về T.nil và khi đó cây T không chứa nút nào có khoảng giao với i.

**Chứng minh (trang 352–353).** Vòng **while** dòng 2–5 kết thúc hoặc khi x = T.nil, hoặc khi i giao x.int. Trường hợp sau, trả về x hiển nhiên đúng. Vậy chỉ cần xét trường hợp vòng lặp dừng vì x = T.nil. Dùng bất biến sau cho vòng **while** dòng 2–5:

> Nếu cây T chứa một khoảng giao với i, thì cây con gốc x chứa một khoảng như vậy.

- **Khởi tạo:** trước lần lặp đầu, dòng 1 đặt x là gốc của T, nên bất biến đúng.
- **Duy trì:** mỗi lần lặp thực hiện dòng 4 hoặc dòng 5; cần chứng minh cả hai trường hợp giữ bất biến.

  *Trường hợp thực hiện dòng 5 (sang phải).* Theo điều kiện rẽ nhánh ở dòng 3, hoặc x.left = T.nil, hoặc x.left.max < i.low. Nếu x.left = T.nil, cây con gốc x.left rõ ràng không chứa khoảng nào giao i, nên đặt x = x.right giữ bất biến. Giả sử x.left ≠ T.nil và x.left.max < i.low. Với mọi khoảng i′ trong cây con trái của x,

  i′.high ≤ x.left.max < i.low.

  Theo tam phân khoảng, i′ nằm bên trái i nên i′ và i không giao nhau. Vậy cây con trái của x không chứa khoảng nào giao i (và x.int cũng không giao i theo điều kiện vòng lặp), nên đặt x = x.right giữ bất biến.

  *Trường hợp thực hiện dòng 4 (sang trái).* Ta chứng minh phản đảo của bất biến: nếu cây con gốc x.left không chứa khoảng nào giao i, thì không có khoảng nào trong cả cây giao i. Vì dòng 4 được thực hiện, theo điều kiện ở dòng 3 ta có x.left.max ≥ i.low. Hơn nữa, theo định nghĩa của max, cây con trái của x phải chứa một khoảng i′ sao cho

  i′.high = x.left.max ≥ i.low.

  Vì i và i′ không giao nhau (giả thiết của phản đảo), và không thể có i′.high < i.low, nên theo tam phân khoảng phải có i.high < i′.low. Cây khoảng dùng đầu mút dưới làm khoá, nên tính chất cây tìm kiếm cho biết với mọi khoảng i″ trong cây con phải của x,

  i.high < i′.low ≤ i″.low.

  Theo tam phân khoảng, i và i″ không giao nhau. (x.int cũng có x.int.low ≥ i′.low > i.high nên không giao i; các nút ở ngoài cây con gốc x đã bị loại bởi bất biến.) Vậy dù cây con trái của x có hay không có khoảng giao i, đặt x = x.left vẫn giữ bất biến.
- **Kết thúc:** nếu vòng lặp dừng với x = T.nil thì cây con gốc x không chứa khoảng nào giao i. Phản đảo của bất biến cho biết T không chứa khoảng nào giao i. Do đó trả về x = T.nil là đúng. ∎

Vậy INTERVAL-SEARCH đúng.

**Hình 14.5 — Các khoảng trong chứng minh Định lý 14.2.** Giá trị x.left.max được vẽ là một đường thẳng đứng nét đứt.

```text
(a) Tìm kiếm đi sang phải: không khoảng i′ nào ở cây con trái của x giao được i

        ├──i′──┤        ┊
     ├──i′──┤           ┊
                        ┊      ├────i────┤
    ────────────────────┊──────────────────────►
                  x.left.max < i.low

(b) Tìm kiếm đi sang trái: hoặc cây con trái có khoảng giao i (không vẽ),
    hoặc cây con trái có khoảng i′ với i′.high = x.left.max; vì i không
    giao i′, i cũng không giao bất kỳ i″ nào ở cây con phải, do i′.low ≤ i″.low

                                         ┊       ├──i″──┤
                                ├───────i″┊────────┤
                                   ├─i″─┤┊
             ├──i──┤          ├─────i′───┤
    ─────────────────────────────────────┊───────────────►
             i.high < i′.low       x.left.max = i′.high ≥ i.low
```

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: cây khoảng (và biến thể "augmented interval tree" đúng như trong sách) được dùng trong lịch và hệ thống đặt chỗ (kiểm tra một cuộc hẹn mới có trùng lịch nào không), trong nhân Linux (cây khoảng dựa trên cây đỏ-đen `interval_tree` dùng để quản lý vùng nhớ ánh xạ và tra cứu theo dải địa chỉ), trong tin sinh học (bedtools, các thư viện như `IntervalTree` của Python tìm các gen, đoạn đọc giao với một vùng nhiễm sắc thể), trong bộ cấp phát bộ nhớ và trình gỡ lỗi (tìm vùng nhớ chứa một địa chỉ), và trong thiết kế vi mạch (kiểm tra các hình chữ nhật chồng nhau bằng đường quét, đúng như bài tập 14.3-7). Biến thể tĩnh "liệt kê mọi khoảng giao" trong O(k + lg n) của ghi chú chương là cây khoảng kiểu Edelsbrunner, phổ biến trong đồ hoạ và hình học tính toán.

### 5. Bài toán cuối chương (Problems, trang 354–355)

Chương có hai bài toán: điểm chồng lấn nhiều nhất (14-1) và hoán vị Josephus (14-2). Đề và lời giải được trình bày đầy đủ ở mục "Bài tập và bài toán cuối chương" bên dưới.

### 6. Ghi chú chương (Chapter notes, trang 355)

Trong cuốn sách của mình (sách hình học tính toán, tài liệu tham khảo số [282] của CLRS), Preparata và Shamos mô tả một số loại cây khoảng xuất hiện trong tài liệu nghiên cứu, dẫn công trình của H. Edelsbrunner (1980) và E. M. McCreight (1981). Sách đó trình bày chi tiết một cây khoảng cho cơ sở dữ liệu *tĩnh* gồm n khoảng, cho phép liệt kê tất cả k khoảng giao với một khoảng truy vấn trong O(k + lg n). So với cây khoảng động của Mục 14.3, cấu trúc này đổi khả năng chèn/xoá lấy khả năng liệt kê mọi kết quả với chi phí tối ưu.

## Bài tập và bài toán cuối chương

Lời giải và gợi ý đi kèm là của người tổng hợp, không có trong sách.

### Bài tập Mục 14.1 (trang 344–345)

- **14.1-1:** Cho biết OS-SELECT(T.root, 10) chạy thế nào trên cây T của Hình 14.1. *Lời giải:* tại 26: r = 13, 10 < 13 → trái; tại 17: r = 14.size + 1 = 8, 10 > 8 → phải, i = 2; tại 21 (trong): r = 19.size + 1 = 3, 2 < 3 → trái; tại 19: r = 0 + 1 = 1, 2 > 1 → phải, i = 1; tại 20: r = 1 = i → trả về nút 20 (đúng, khoá 20 có hạng 10).
- **14.1-2:** Cho biết OS-RANK(T, x) chạy thế nào trên Hình 14.1 với x.key = 35. *Lời giải:* r = 1 (35 là lá); y = 35 là con trái của 38 → r = 1; y = 38 là con phải của 30 → r = 1 + 1 + 1 = 3; y = 30 là con trái của 41 → r = 3; y = 41 là con phải của 26 → r = 3 + 12 + 1 = 16; y = 26 là gốc → trả về 16.
- **14.1-3:** Viết phiên bản không đệ quy của OS-SELECT. *Gợi ý:* vòng lặp `while true`: r = x.left.size + 1; nếu i == r trả về x; nếu i < r thì x = x.left; ngược lại i = i − r, x = x.right.
- **14.1-4:** Viết thủ tục đệ quy OS-KEY-RANK(T, k) nhận cây thống kê thứ tự T và khoá k, trả về hạng của k trong tập động do T biểu diễn; giả định khoá phân biệt. *Gợi ý:* hàm phụ đệ quy từ gốc: nếu k == x.key trả về x.left.size + 1; nếu k < x.key đệ quy trái; nếu k > x.key trả về x.left.size + 1 + (hạng của k trong x.right). O(lg n).
- **14.1-5:** Cho phần tử x trong cây thống kê thứ tự n nút và số tự nhiên i, làm sao tìm phần tử kế tiếp thứ i của x trong thứ tự tuyến tính trong O(lg n)? *Gợi ý:* OS-SELECT(T.root, OS-RANK(T, x) + i).
- **14.1-6:** Nhận xét rằng mỗi lần OS-SELECT hay OS-RANK dùng size của một nút thì chỉ để tính hạng. Giả sử mỗi nút lưu hạng của nó trong cây con mà nó là gốc (tức x.left.size + 1). Chỉ ra cách duy trì thông tin này khi chèn và xoá (nhớ rằng hai thao tác này có thể gây phép quay). *Gợi ý:* khi chèn đi xuống, chỉ tăng thuộc tính của các nút mà ta rẽ trái; khi xoá, giảm ở các nút mà đường đi tới nút bị gỡ rẽ trái; LEFT-ROTATE(T, x): y.rank = y.rank + x.rank; RIGHT-ROTATE(T, y): y.rank = y.rank − x.rank.
- **14.1-7:** Chỉ ra cách dùng cây thống kê thứ tự để đếm số nghịch thế (cặp chỉ số i < j với A[i] > A[j], Bài toán 2-4) trong mảng n phần tử trong O(n lg n). *Gợi ý:* duyệt j = 1..n, chèn A[j] rồi cộng (j − hạng của A[j] trong cây) — số phần tử đã chèn lớn hơn A[j] (khi có khoá trùng cần quy ước để phần tử bằng nhau không bị đếm).
- **14.1-8 (dấu sao):** Cho n dây cung trên đường tròn, mỗi dây xác định bởi hai đầu mút; không hai dây chung đầu mút. Mô tả thuật toán O(n lg n) đếm số cặp dây cắt nhau bên trong đường tròn (ví dụ n đường kính cùng đi qua tâm thì đáp số là C(n, 2) = n(n − 1)/2). *Gợi ý:* hai dây cắt nhau khi và chỉ khi đầu mút của chúng xen kẽ quanh đường tròn. Sắp xếp 2n đầu mút theo góc; quét lần lượt: gặp đầu mút thứ nhất của một dây thì chèn thời điểm (vị trí) gặp vào cây thống kê thứ tự; gặp đầu mút thứ hai thì cộng số dây đang mở có vị trí mở lớn hơn vị trí mở của dây này (các dây này mở bên trong và đóng bên ngoài cung của nó), rồi xoá dây khỏi cây. O(n lg n).

### Bài tập Mục 14.2 (trang 347–348)

- **14.2-1:** Bằng cách thêm con trỏ vào nút, chỉ ra cách hỗ trợ MINIMUM, MAXIMUM, SUCCESSOR, PREDECESSOR trong O(1) trường hợp xấu nhất trên cây thống kê thứ tự mở rộng, không ảnh hưởng hiệu năng tiệm cận của các thao tác khác. *Gợi ý:* duy trì danh sách liên kết kép theo thứ tự khoá (con trỏ pred, succ ở mỗi nút) cùng con trỏ min, max của cây; khi chèn, nút mới được nối giữa nút kế trước và kế sau tìm được trong O(lg n); phép quay không làm đổi thứ tự nên không phải sửa.
- **14.2-2:** Có thể duy trì chiều cao đen của các nút như thuộc tính mà không ảnh hưởng hiệu năng tiệm cận của mọi thao tác cây đỏ-đen không? Chỉ ra cách, hoặc lập luận vì sao không. Còn độ sâu của nút thì sao? *Gợi ý:* chiều cao đen thì được — x.bh = x.left.bh + (1 nếu x.left đen, 0 nếu đỏ) chỉ phụ thuộc vào con, nên Định lý 14.1 áp dụng. Độ sâu thì không — một phép quay làm đổi độ sâu của mọi nút trong ba cây con, có thể Θ(n) nút.
- **14.2-3 (dấu sao):** Cho ⊗ là toán tử hai ngôi có tính kết hợp và a là thuộc tính ở mỗi nút cây đỏ-đen. Muốn mỗi nút x có thêm f với x.f = x₁.a ⊗ x₂.a ⊗ ⋯ ⊗ xₘ.a, trong đó x₁, x₂, …, xₘ là danh sách duyệt giữa các nút của cây con gốc x. Chỉ ra cách cập nhật f trong O(1) sau một phép quay; sửa lập luận một chút để áp dụng cho size của cây thống kê thứ tự. *Gợi ý:* x.f = x.left.f ⊗ x.a ⊗ x.right.f (bỏ các hạng tử ứng với T.nil); sau LEFT-ROTATE(T, x): y.f = x.f cũ, rồi tính lại x.f từ hai con mới. Với size: a = 1 ở mọi nút, ⊗ là phép cộng.
- **14.2-4 (dấu sao):** Muốn mở rộng cây đỏ-đen với thao tác RB-ENUMERATE(x, a, b) in ra mọi khoá k với a ≤ k ≤ b trong cây gốc x. Mô tả cách cài đặt trong Θ(m + lg n), với m là số khoá in ra và n là số nút trong của cây (gợi ý của sách: không cần thêm thuộc tính mới). *Gợi ý:* duyệt giữa có cắt tỉa: tại x, nếu x.key > a thì đệ quy trái; nếu a ≤ x.key ≤ b thì in x.key; nếu x.key < b thì đệ quy phải. Các nút được thăm gồm m nút in ra cộng các nút trên hai đường biên tìm a và b (O(lg n)). Hoặc tìm nút đầu tiên ≥ a rồi gọi SUCCESSOR m lần — tổng chi phí SUCCESSOR liên tiếp là O(m + lg n).

### Bài tập Mục 14.3 (trang 353–354)

- **14.3-1:** Viết pseudocode cho LEFT-ROTATE làm việc trên nút cây khoảng và cập nhật max trong O(1). *Gợi ý:* thêm vào cuối LEFT-ROTATE: `y.max = x.max` và `x.max = max(x.int.high, x.left.max, x.right.max)`.
- **14.3-2:** Viết lại INTERVAL-SEARCH để chạy đúng khi mọi khoảng là khoảng mở. *Gợi ý:* phép thử giao nhau thành i.low < x.int.high và x.int.low < i.high; điều kiện ở dòng 3 thành x.left.max > i.low.
- **14.3-3:** Mô tả thuật toán hiệu quả, cho khoảng i, trả về một khoảng giao i có đầu mút dưới nhỏ nhất, hoặc T.nil nếu không có. *Gợi ý:* tại x, nếu cây con trái có thể chứa khoảng giao (x.left.max ≥ i.low) thì đi trái — theo chứng minh Định lý 14.2, nếu có khoảng giao ở bất kỳ đâu thì có ở bên trái; nếu x.int giao i và bên trái không có thì x là đáp án; ngược lại đi phải. Ghi nhớ ứng viên tốt nhất; O(lg n).
- **14.3-4:** Cho cây khoảng T và khoảng i, mô tả cách liệt kê mọi khoảng trong T giao với i trong O(min(n, k lg n)), với k là số khoảng trong kết quả (gợi ý của sách: cách đơn giản là truy vấn nhiều lần và sửa cây giữa các lần; cách phức tạp hơn một chút không sửa cây). *Gợi ý:* cách 1: lặp INTERVAL-SEARCH, mỗi lần tìm được thì ghi lại và xoá khoảng đó, cuối cùng chèn lại tất cả — O(k lg n); cách 2: đệ quy, chỉ vào cây con khi max của nó ≥ i.low và chỉ vào cây con phải khi x.int.low ≤ i.high.
- **14.3-5:** Đề xuất sửa đổi để hỗ trợ INTERVAL-SEARCH-EXACTLY(T, i) trả về nút x có x.int.low = i.low và x.int.high = i.high, hoặc T.nil; mọi thao tác, kể cả thao tác mới, chạy trong O(lg n). *Gợi ý:* sắp thứ tự khoá theo cặp (low, high) theo thứ tự từ điển, rồi tìm như cây tìm kiếm thường.
- **14.3-6:** Duy trì tập động Q các số với thao tác MIN-GAP trả về độ lớn hiệu của hai số gần nhau nhất trong Q (ví dụ Q = {1, 5, 9, 15, 18, 22} thì MIN-GAP(Q) = 18 − 15 = 3). Làm INSERT, DELETE, SEARCH, MIN-GAP hiệu quả nhất có thể và phân tích thời gian. *Gợi ý:* cây đỏ-đen với x.min, x.max (khoá nhỏ nhất, lớn nhất của cây con) và x.mingap = min(x.left.mingap, x.right.mingap, x.key − x.left.max, x.right.min − x.key) (bỏ hạng tử khi con là T.nil; mingap của cây một nút là ∞). Theo Định lý 14.1, INSERT, DELETE, SEARCH O(lg n); MIN-GAP trả về T.root.mingap trong O(1).
- **14.3-7 (dấu sao):** Cơ sở dữ liệu VLSI thường biểu diễn mạch tích hợp như danh sách hình chữ nhật có cạnh song song trục toạ độ, mỗi hình cho bởi toạ độ x, y nhỏ nhất và lớn nhất. Cho thuật toán O(n lg n) quyết định tập n hình chữ nhật có hai hình nào chồng nhau không; phải báo chồng nhau cả khi một hình phủ hoàn toàn hình kia (gợi ý của sách: quét một đường thẳng qua tập hình). *Gợi ý:* sắp 2n cạnh trái/phải theo x; quét từ trái sang: gặp cạnh trái thì INTERVAL-SEARCH khoảng [y_min, y_max] trong cây khoảng các hình đang "mở" — có giao thì báo chồng nhau — rồi chèn vào; gặp cạnh phải thì xoá. O(n lg n).

### Bài toán 14-1: Điểm chồng lấn nhiều nhất (Point of maximum overlap, trang 354–355)

**Đề.** Giả sử ta muốn theo dõi một điểm chồng lấn nhiều nhất trong một tập khoảng — điểm có nhiều khoảng trong tập phủ lên nó nhất.

- **a.** Chứng minh rằng luôn có một điểm chồng lấn nhiều nhất là đầu mút của một trong các đoạn.
- **b.** Thiết kế cấu trúc dữ liệu hỗ trợ hiệu quả INTERVAL-INSERT, INTERVAL-DELETE và FIND-POM (trả về một điểm chồng lấn nhiều nhất). Gợi ý của sách: giữ một cây đỏ-đen chứa mọi đầu mút; gắn giá trị +1 cho mỗi đầu mút trái và −1 cho mỗi đầu mút phải; mở rộng mỗi nút với thông tin bổ sung để duy trì điểm chồng lấn nhiều nhất.

**Lời giải của người tổng hợp.**

- **a.** Lấy một điểm p chồng lấn nhiều nhất. Gọi q là đầu mút trái lớn nhất (≤ p) trong số các khoảng chứa p. Mọi khoảng chứa p đều chứa [q, p] (vì đầu mút trái của chúng ≤ q và đầu mút phải ≥ p), nên q được phủ bởi ít nhất số khoảng phủ p, tức q cũng chồng lấn nhiều nhất, và q là một đầu mút.
- **b.** Cây đỏ-đen khoá theo toạ độ đầu mút (khi bằng nhau, đặt đầu mút trái trước đầu mút phải, vì khoảng đóng). Nút x có x.v = +1 hoặc −1. Thêm ba thuộc tính: x.sum = tổng v trong cây con; x.maxp = giá trị lớn nhất của các tổng tiền tố (theo thứ tự duyệt giữa) trong cây con; x.pom = đầu mút nơi đạt x.maxp. Công thức:
  x.sum = x.left.sum + x.v + x.right.sum;
  x.maxp = max(x.left.maxp, x.left.sum + x.v, x.left.sum + x.v + x.right.maxp), với x.pom lấy theo hạng tử đạt cực đại.
  Các thuộc tính chỉ phụ thuộc x và hai con, nên theo Định lý 14.1, INTERVAL-INSERT (chèn 2 đầu mút) và INTERVAL-DELETE (xoá 2 đầu mút) chạy trong O(lg n); FIND-POM trả về T.root.pom trong O(1), và T.root.maxp là số khoảng chồng lên nhau tại điểm đó.

### Bài toán 14-2: Hoán vị Josephus (Josephus permutation, trang 355)

**Đề.** Bài toán Josephus: n người đứng thành vòng tròn và cho số nguyên dương m ≤ n. Bắt đầu từ một người được chỉ định là người thứ nhất, đi vòng quanh và loại mỗi người thứ m. Sau mỗi lần loại, tiếp tục đếm vòng quanh phần vòng tròn còn lại, cho tới khi loại hết n người. Thứ tự bị loại xác định **hoán vị Josephus (n, m)** của các số 1, 2, …, n. Ví dụ, hoán vị Josephus (7, 3) là ⟨3, 6, 2, 7, 5, 1, 4⟩.

- **a.** Giả sử m là hằng số. Mô tả thuật toán O(n) nhận n và in ra hoán vị Josephus (n, m).
- **b.** Giả sử m không phải hằng số. Mô tả thuật toán O(n lg n) nhận n và m và in ra hoán vị Josephus (n, m).

**Kiểm tra ví dụ (7, 3) (người tổng hợp):** vòng 1, 2, 3, 4, 5, 6, 7 — đếm 1, 2, 3 loại 3; đếm tiếp 4, 5, 6 loại 6; 7, 1, 2 loại 2; còn {1, 4, 5, 7}, đếm 4, 5, 7 loại 7; còn {1, 4, 5}, đếm 1, 4, 5 loại 5; còn {1, 4}, đếm 1, 4, 1 loại 1; còn 4. Kết quả ⟨3, 6, 2, 7, 5, 1, 4⟩, khớp sách.

**Lời giải của người tổng hợp.**

- **a.** Dùng danh sách liên kết vòng chứa 1..n; từ vị trí hiện tại đi m − 1 bước, gỡ và in nút đó. Mỗi lần loại tốn O(m) = O(1) vì m là hằng, tổng O(mn) = O(n).
- **b.** Đặt 1..n vào cây thống kê thứ tự (xây trong O(n lg n), hoặc O(n) nếu dựng cây cân bằng từ dãy đã sắp). Giữ j là hạng của người sắp bị loại trong tập còn lại và k là số người còn lại. Ban đầu k = n, j = m. Lặp n lần: x = OS-SELECT(T.root, j); in x.key; xoá x; k = k − 1; nếu k > 0 thì j = ((j − 1 + m − 1) mod k) + 1. Mỗi lần lặp O(lg n), tổng O(n lg n). Chạy thử (7, 3): j lần lượt 3 (ra 3), 5 trong {1,2,4,5,6,7} (ra 6), 2 trong {1,2,4,5,7} (ra 2), 4 trong {1,4,5,7} (ra 7), 3 trong {1,4,5} (ra 5), 1 trong {1,4} (ra 1), 1 trong {4} (ra 4).

### Ghi chú chương (Chapter notes, trang 355)

Preparata và Shamos, trong sách của họ (tài liệu [282]), mô tả một số cây khoảng trong tài liệu, dẫn công trình của H. Edelsbrunner (1980) và E. M. McCreight (1981). Sách đó trình bày chi tiết một cây khoảng cho cơ sở dữ liệu tĩnh n khoảng, liệt kê được mọi k khoảng giao với một khoảng truy vấn trong O(k + lg n). (Theo hiểu biết của người tổng hợp, không tra cứu: sách của Preparata và Shamos là *Computational Geometry: An Introduction*, 1985.)

## Luận điểm cốt lõi

### Mệnh đề

Thay vì phát minh cấu trúc dữ liệu mới, phần lớn nhu cầu thực tế có thể đáp ứng bằng cách mở rộng một cấu trúc giáo khoa với thông tin bổ sung ở mỗi nút; với cây đỏ-đen, mọi thuộc tính chỉ phụ thuộc vào nút và hai con của nó đều được duy trì qua chèn và xoá mà thời gian vẫn O(lg n), và nhờ đó có được các thao tác mới mạnh như chọn phần tử thứ i, tính hạng, hay tìm khoảng giao nhau trong O(lg n).

### Giả định

- Mô hình RAM của Chương 2: mỗi phép so sánh khoá, đọc/ghi thuộc tính, cộng số nguyên mất O(1).
- Cấu trúc nền là cây đỏ-đen của Chương 13 với chiều cao O(lg n), lính canh T.nil, chèn có ≤ 2 phép quay, xoá có ≤ 3 phép quay, và các phép quay là thao tác cục bộ.
- Khoá thuộc một thứ tự toàn phần; trong cây thống kê thứ tự khoá có thể trùng (hạng định nghĩa theo vị trí duyệt giữa); trong bài tập 14.1-4 thì giả định khoá phân biệt.
- Quy ước giá trị của lính canh: T.nil.size = 0; ngầm định T.nil.max = −∞.
- Cây khoảng làm việc với khoảng đóng; khoảng mở và nửa mở được coi là mở rộng đơn giản.
- Thao tác mới chỉ trả về *một* kết quả (một khoảng giao nhau, một phần tử thứ i); liệt kê mọi kết quả là bài toán khác (bài tập 14.3-4, ghi chú chương).

### Cơ chế

1. **Chọn cấu trúc nền** có sẵn các thao tác cần thiết trên thứ tự toàn phần (cây đỏ-đen).
2. **Chọn thông tin bổ sung** là một hàm *cục bộ* của nút và hai con (size; max), không phải thông tin toàn cục (hạng trong toàn cây; độ sâu).
3. **Duy trì thông tin:** ở pha đi xuống/gỡ nút, sửa thông tin dọc một đường O(lg n); ở mỗi phép quay, sửa hai nút x, y theo đúng thứ tự (nút trở thành cha lấy giá trị cũ của nút bị hạ xuống; nút bị hạ xuống tính lại từ hai con mới).
4. **Xây thao tác mới** bằng cách đi một đường duy nhất trên cây, dùng thông tin bổ sung để biết đi trái hay phải (OS-SELECT, INTERVAL-SEARCH) hoặc leo lên và cộng dồn (OS-RANK).
5. **Chứng minh đúng** bằng bất biến vòng lặp (OS-RANK; INTERVAL-SEARCH với phản đảo và tam phân khoảng).

### Bằng chứng và ví dụ tác giả đưa ra

- Hình 14.1: cây thống kê thứ tự 20 nút có khoá trùng (14, 21); hai nút khoá 14 có hạng 5 và 6.
- OS-SELECT tìm phần tử thứ 17: 26 (r = 13) → 41 (i = 4, r = 6) → 30 (r = 2) → 38 (i = 2, r = 2), trả về 38.
- OS-RANK của nút 38: r = 2, 4, 4, 17.
- Hình 14.2: phép quay trên hai nút size 19 và 12 (hoặc 11), ba cây con size 6, 4, 7; hai dòng thêm vào LEFT-ROTATE.
- Phản ví dụ thiết kế: lưu hạng trong toàn cây khiến chèn phần tử nhỏ nhất làm đổi mọi nút.
- Định lý 14.1 và chứng minh lan truyền lên tổ tiên.
- Hình 14.3: ba trường hợp tam phân khoảng (bốn kiểu giao nhau).
- Hình 14.4: cây khoảng 10 khoảng, max tại gốc là 30.
- INTERVAL-SEARCH với [22, 25] (tìm thấy [15, 23]) và [11, 14] (trả về T.nil).
- Định lý 14.2 và Hình 14.5 minh hoạ hai trường hợp rẽ phải và rẽ trái.

### Kết luận và hàm ý cho người lập trình

- Trước khi tìm một cấu trúc dữ liệu lạ, hãy hỏi: thông tin nào, nếu lưu ở mỗi nút của một cây cân bằng, sẽ trả lời câu hỏi của tôi bằng một đường đi từ gốc?
- Kiểm tra ngay thông tin đó có phải hàm của nút và hai con không. Nếu có, chèn/xoá/quay chỉ cần thêm vài dòng; nếu không (như hạng toàn cục), hãy tìm một đại lượng cục bộ tương đương (như size).
- Khi sửa phép quay, thứ tự cập nhật quan trọng: nút được nâng lên nhận giá trị cũ của nút bị hạ xuống; nút bị hạ xuống phải tính lại *trước* các tổ tiên.
- Thao tác tìm kiếm trên cấu trúc mở rộng cần chứng minh "rẽ an toàn" bằng bất biến — trực giác "chỉ đi một nhánh" dễ sai nếu điều kiện rẽ không chuẩn (ví dụ dùng ≥ hay > tuỳ loại khoảng).
- Quy trình bốn bước là khung tốt cho tài liệu thiết kế và câu trả lời phỏng vấn.

### Trong ngôn ngữ khoa học máy tính

Cây thống kê thứ tự: x.size = x.left.size + x.right.size + 1, T.nil.size = 0; OS-SELECT và OS-RANK O(h) = O(lg n); INSERT/DELETE O(lg n) với O(lg n) cập nhật dọc đường và O(1) mỗi phép quay. Định lý 14.1: nếu f(x) = F(dữ liệu của x, f(x.left), f(x.right), dữ liệu của x.left, x.right) thì INSERT/DELETE vẫn O(lg n) (chi phí xấu nhất trong chứng minh: O(lg n) cho pha một + O(1) phép quay × O(lg n) lan truyền). Cây khoảng: khoá x.int.low, x.max = max(x.int.high, x.left.max, x.right.max); INTERVAL-SEARCH O(lg n), đúng nhờ bất biến "T có khoảng giao i ⇒ cây con gốc x có khoảng giao i" và tam phân khoảng. Trường hợp riêng quan trọng: f là phép gộp theo một toán tử kết hợp ⊗ (vị nhóm) trên thứ tự duyệt giữa, cập nhật O(1) mỗi phép quay (bài tập 14.2-3).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| augmenting a data structure | mở rộng cấu trúc dữ liệu | lưu thêm thông tin vào cấu trúc có sẵn để có thao tác mới |
| underlying data structure | cấu trúc dữ liệu nền | cấu trúc gốc được mở rộng (ở đây là cây đỏ-đen) |
| additional information | thông tin bổ sung | thuộc tính thêm vào mỗi nút (size, max) |
| textbook data structure | cấu trúc dữ liệu giáo khoa | danh sách liên kết kép, bảng băm, cây tìm kiếm nhị phân… |
| order statistic | thống kê thứ tự | phần tử có khoá nhỏ thứ i |
| dynamic order statistics | thống kê thứ tự động | thống kê thứ tự trên tập có chèn, xoá |
| dynamic set | tập động | tập thay đổi theo thời gian qua chèn, xoá |
| rank | hạng | vị trí của phần tử (nút) trong phép duyệt giữa |
| order-statistic tree | cây thống kê thứ tự | cây đỏ-đen có thêm size ở mỗi nút |
| size (of a subtree) | kích thước cây con | số nút trong của cây con, kể cả gốc |
| sentinel (T.nil) | lính canh | nút giả thay cho NIL; T.nil.size = 0 |
| inorder tree walk | phép duyệt giữa | duyệt trái – gốc – phải, cho thứ tự khoá tăng dần |
| OS-SELECT | OS-SELECT (chọn theo hạng) | tìm nút có khoá nhỏ thứ i, O(lg n) |
| OS-RANK | OS-RANK (tính hạng) | tính hạng của nút x, O(lg n) |
| rotation / LEFT-ROTATE / RIGHT-ROTATE | phép quay / quay trái / quay phải | đổi quan hệ cha–con cục bộ, giữ tính chất cây tìm kiếm |
| red-black tree | cây đỏ-đen | cây tìm kiếm nhị phân cân bằng, chiều cao O(lg n) |
| black-height | chiều cao đen | số nút đen trên đường từ nút xuống lá (không tính nút đó) |
| loop invariant | bất biến vòng lặp | mệnh đề đúng ở đầu mỗi lần lặp |
| initialization / maintenance / termination | khởi tạo / duy trì / kết thúc | ba bước chứng minh bằng bất biến |
| contrapositive | phản đảo | "không Q ⇒ không P", tương đương "P ⇒ Q" |
| closed / open / half-open interval | khoảng đóng / mở / nửa mở | có cả hai / không có / có một đầu mút |
| low endpoint / high endpoint | đầu mút dưới / đầu mút trên | i.low, i.high |
| overlap | giao nhau (chồng lấn) | i.low ≤ i′.high và i′.low ≤ i.high |
| interval trichotomy | tam phân khoảng | hai khoảng: giao nhau, bên trái, hoặc bên phải — đúng một |
| interval tree | cây khoảng | cây đỏ-đen chứa khoảng, khoá low, thêm max |
| INTERVAL-INSERT / INTERVAL-DELETE / INTERVAL-SEARCH | chèn / xoá / tìm khoảng | ba thao tác của cây khoảng |
| associative binary operator (⊗) | toán tử hai ngôi kết hợp | (a ⊗ b) ⊗ c = a ⊗ (b ⊗ c), dùng trong bài tập 14.2-3 |
| inversion | nghịch thế | cặp i < j với A[i] > A[j] |
| chord | dây cung | đoạn nối hai điểm trên đường tròn |
| sweep line | đường quét | kỹ thuật quét một đường thẳng qua tập hình |
| VLSI | VLSI (tích hợp rất lớn) | thiết kế vi mạch, dùng trong bài tập 14.3-7 |
| point of maximum overlap | điểm chồng lấn nhiều nhất | điểm bị nhiều khoảng phủ nhất (Bài toán 14-1) |
| Josephus problem / permutation | bài toán / hoán vị Josephus | thứ tự loại người khi đếm vòng (Bài toán 14-2) |
| MIN-GAP | MIN-GAP | hiệu nhỏ nhất giữa hai số trong tập (bài tập 14.3-6) |

## Câu nói đáng nhớ

> "Only in rare situations will you need to create an entirely new type of data structure, though. More often, it will suffice to augment a textbook data structure by storing additional information in it." — phần mở đầu chương, trang 339
>
> *Dịch: Chỉ trong những trường hợp hiếm hoi bạn mới cần tạo ra một kiểu cấu trúc dữ liệu hoàn toàn mới. Thường thì chỉ cần mở rộng một cấu trúc giáo khoa bằng cách lưu thêm thông tin vào nó.*

> "Augmenting a data structure is not always straightforward, however, since the added information must be updated and maintained by the ordinary operations on the data structure." — phần mở đầu chương, trang 339
>
> *Dịch: Tuy vậy, mở rộng một cấu trúc dữ liệu không phải lúc nào cũng đơn giản, vì thông tin thêm vào phải được cập nhật và duy trì bởi các thao tác thông thường của cấu trúc.*

> "But unless we can efficiently maintain these attributes within the basic modifying operations on red-black trees, our work will have been for naught." — Mục 14.1, trang 343
>
> *Dịch: Nhưng nếu không duy trì hiệu quả được các thuộc tính này trong các thao tác sửa đổi cơ bản của cây đỏ-đen, công sức của chúng ta sẽ thành vô ích.*

> "As with any prescriptive design method, you should not blindly follow the steps in the order given." — Mục 14.2, trang 345
>
> *Dịch: Như với mọi phương pháp thiết kế mang tính chỉ dẫn, bạn không nên làm theo các bước một cách mù quáng đúng thứ tự đã nêu.*

> "After all, the need for new operations is why we bother to augment a data structure in the first place." — Mục 14.2, trang 346
>
> *Dịch: Suy cho cùng, nhu cầu có thao tác mới chính là lý do khiến ta phải mất công mở rộng một cấu trúc dữ liệu.*

> "The main idea of the proof is that a change to an f attribute in a node x propagates only to ancestors of x in the tree." — chứng minh Định lý 14.1, trang 346
>
> *Dịch: Ý chính của chứng minh là một thay đổi ở thuộc tính f của nút x chỉ lan tới các tổ tiên của x trong cây.*

> "The basic idea is that at any node x, if x.int does not overlap i, the search always proceeds in a safe direction." — Mục 14.3, trang 351
>
> *Dịch: Ý cơ bản là tại bất kỳ nút x nào, nếu x.int không giao i, việc tìm kiếm luôn đi theo một hướng an toàn.*

## Đánh giá và phát hiện đáng chú ý

### Chương ngắn nhưng dạy một kỹ thuật thiết kế, không chỉ hai cấu trúc

Chỉ 17 trang, Chương 14 là một trong những chương có tỷ lệ "ý tưởng trên trang" cao nhất của Phần III. Giá trị của nó không nằm ở cây thống kê thứ tự hay cây khoảng tự thân, mà ở cách hai cấu trúc này được dùng làm hai ví dụ cho một quy trình chung (bốn bước) và một tiêu chí chung (Định lý 14.1). Thứ tự trình bày cũng có chủ ý: làm một ví dụ cụ thể trước (14.1), rút ra nguyên tắc (14.2), rồi áp dụng nguyên tắc cho ví dụ thứ hai, lần này đi theo đúng nhãn "Step 1–4" (14.3). Người đọc học được cách *nghĩ* ra cấu trúc dữ liệu, điều mà phần lớn giáo trình chỉ ngầm định.

### Điểm mạnh: chứng minh đúng đắn chặt chẽ cho những thủ tục ngắn

OS-RANK và INTERVAL-SEARCH đều chỉ 6–7 dòng, nhưng sách chứng minh bằng bất biến vòng lặp đầy đủ ba bước. Chứng minh Định lý 14.2 đặc biệt đáng học: trường hợp rẽ trái không chứng minh "bên trái chắc chắn có kết quả" mà chứng minh phản đảo "nếu bên trái không có thì bên phải cũng không", dựa vào nút i′ đạt max và tính chất sắp theo low. Đây là kiểu lập luận "trao đổi/loại trừ" xuất hiện lại trong thuật toán tham lam (Chương 16) và nhiều thuật toán tìm kiếm trên cấu trúc mở rộng.

### Điểm yếu và chỗ cần đọc kỹ

- Chứng minh Định lý 14.1 đưa ra cận O(lg n) mỗi phép quay, thô hơn thực tế; sách chỉ nhắc rằng "nhiều trường hợp" chỉ cần O(1) và đẩy sang bài tập 14.2-3. Người đọc nên tự thấy vì sao: sau phép quay, tập con cháu của mọi tổ tiên không đổi, nên với mọi thuộc tính là hàm của *tập* (hay của dãy duyệt giữa) các nút trong cây con, chỉ hai nút được quay cần tính lại.
- Phần xoá được mô tả khá vắn tắt ("đi từ vị trí ban đầu của y lên gốc"), trong khi RB-DELETE của ấn bản 3 có ba nút liên quan (z, y, x). Người cài đặt cần cẩn thận: khi z có hai con, y (nút kế tiếp) được dời vào vị trí z; đường giảm size bắt đầu từ cha cũ của y và đi qua z (vì z là tổ tiên của y), rồi y ở vị trí mới nhận giá trị z.size đã giảm đó. Đây là chỗ hay sinh lỗi nhất khi tự viết cây thống kê thứ tự.
- Bất biến OS-RANK nói "hạng của x.key" trong khi chương cho phép khoá trùng (ghi ở khối Lưu ý); OS-SELECT không kiểm tra 1 ≤ i ≤ size.
- Điều kiện `x.left ≠ T.nil` ở dòng 3 của INTERVAL-SEARCH là thừa nếu đặt T.nil.max = −∞; sách giữ nó để không phải dựa vào quy ước ngầm.

### So với thực tế: thư viện chuẩn và phần cứng hiện đại

Thư viện chuẩn của hầu hết ngôn ngữ (std::map/std::set của C++, TreeMap của Java) cài đặt cây đỏ-đen nhưng *không* mở rộng size, nên không có thao tác "phần tử thứ i" hay "hạng" trong O(lg n) — đúng loại tình huống mà chương nói "cần một chút sáng tạo". Lập trình viên C++ thi đấu thường dùng `__gnu_pbds` (theo hiểu biết của người tổng hợp), người khác phải tự viết treap hoặc cây Fenwick (Binary Indexed Tree) khi miền giá trị nhỏ. Trên phần cứng hiện đại, cây nhị phân với con trỏ có cục bộ bộ nhớ đệm kém; cấu trúc thực tế thường mở rộng cây B hoặc cây B+ (Chương 18) — mỗi nút lưu số phần tử của từng cây con — với cùng nguyên tắc của Định lý 14.1. Khi tập là tĩnh hoặc chỉ thêm, cây phân đoạn (segment tree) hay mảng sắp xếp kèm tìm kiếm nhị phân thường nhanh hơn cây khoảng.

### Liên hệ các chương khác

- Chương 9: thống kê thứ tự trên tập tĩnh O(n) so với O(lg n) mỗi truy vấn ở đây (sau khi đã trả O(n lg n) để xây cây).
- Chương 12–13: toàn bộ chương dựa trên cây tìm kiếm, phép quay và hai pha chèn/xoá của cây đỏ-đen.
- Chương 21 (tập rời nhau): cũng gắn thêm thuộc tính (rank) vào nút của rừng cây, nhưng ở đó không có phép quay nên việc duy trì đơn giản hơn.
- Chương 33 (hình học tính toán): kỹ thuật đường quét với cây đỏ-đen, cùng tinh thần với bài tập 14.3-7.
- Bài toán 2-4 (nghịch thế): bài tập 14.1-7 cho lời giải thứ hai O(n lg n) bên cạnh cách sửa merge sort.

### Cách vận dụng

- **Phỏng vấn:** các câu hỏi "đếm số phần tử nhỏ hơn ở bên phải", "trung vị của luồng dữ liệu", "đặt lịch phòng họp không trùng", "bảng xếp hạng có cập nhật" đều là cây thống kê thứ tự hoặc cây khoảng; trình bày theo bốn bước của Mục 14.2 cho câu trả lời có cấu trúc.
- **Lập trình thi đấu:** thuộc lòng mẫu "x.f = x.left.f ⊗ x.a ⊗ x.right.f, sửa sau mỗi phép quay/tách/ghép" để mở rộng treap hoặc splay tree cho bất kỳ truy vấn đoạn nào có toán tử kết hợp.
- **Kỹ thuật phần mềm:** khi một truy vấn chạy O(n) trên dữ liệu đã có cây chỉ mục, hãy kiểm tra xem có thể lưu một đại lượng tổng hợp cục bộ ở mỗi nút (đếm, tổng, max, băm) để biến nó thành O(lg n) không — và đừng quên chi phí duy trì khi ghi.

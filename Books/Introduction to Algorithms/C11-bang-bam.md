# Chương 11 — Bảng băm (Hash Tables)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần III "Data Structures", Chương 11 "Hash Tables", trang 253–285.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (ba người đầu ở MIT, Stein ở Đại học Columbia); cuốn sách thường được gọi tắt là "CLRS" theo chữ cái đầu tên họ.
**Vị trí trong lập luận của cả cuốn sách:** Lời giới thiệu Phần III và Chương 10 ([C10-cau-truc-du-lieu-co-ban.md](C10-cau-truc-du-lieu-co-ban.md)) đặt ra khái niệm **tập động** (dynamic set) và nhóm phép toán **từ điển** (dictionary) — INSERT, SEARCH, DELETE — rồi cài đặt chúng bằng danh sách liên kết, với SEARCH tốn Θ(n) trong trường hợp xấu nhất. Chương 11 giới thiệu cấu trúc dữ liệu làm từ điển nhanh nhất trong thực tế: bảng băm, đưa thời gian trung bình của cả ba phép toán xuống O(1). Chương này dùng trực tiếp danh sách liên kết đôi của Chương 10 làm "chuỗi" trong bảng băm nối chuỗi; dùng công cụ xác suất của Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)) — biến ngẫu nhiên chỉ thị, Bổ đề 5.1, tính tuyến tính của kỳ vọng, phân tích nghịch lý ngày sinh ở Mục 5.4.1; và lặp lại ý tưởng của quicksort ngẫu nhiên ở Chương 7 ([C07-quicksort.md](C07-quicksort.md)): chọn ngẫu nhiên bên trong thuật toán để không đầu vào nào luôn là đầu vào xấu. Phần chứng minh lớp hàm băm phổ quát cần một chút số học modulo của Chương 31 ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)); các bất đẳng thức xác suất (bất đẳng thức Markov (C.30), công thức (C.25)) lấy từ Phụ lục C ([PC-dem-va-xac-suat.md](PC-dem-va-xac-suat.md)) và các cận tổng từ Phụ lục A ([PA-tong.md](PA-tong.md)). Hai chương kế tiếp, Chương 12 ([C12-cay-tim-kiem-nhi-phan.md](C12-cay-tim-kiem-nhi-phan.md)) và Chương 13 ([C13-cay-do-den.md](C13-cay-do-den.md)), cài đặt từ điển bằng cây tìm kiếm: chậm hơn (O(lg n)) nhưng hỗ trợ thêm các phép toán dựa trên thứ tự (MINIMUM, SUCCESSOR...) mà bảng băm không làm được. Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)) bổ sung kỹ thuật bảng động (dynamic table) — nhân đôi kích thước khi đầy — để giữ hệ số tải bị chặn; Chương 20 ([C20-cay-van-emde-boas.md](C20-cay-van-emde-boas.md)) quay lại ý tưởng "khoá là số nguyên trong một vũ trụ" của bảng địa chỉ trực tiếp; Chương 32 ([C32-so-khop-chuoi.md](C32-so-khop-chuoi.md)) dùng băm theo phép chia trên chuỗi trong thuật toán Rabin–Karp.
**Ý chính:** Tác giả muốn người đọc hiểu rằng **bảng băm tệ ngang danh sách liên kết trong trường hợp xấu nhất (Θ(n) cho một lần tìm kiếm), nhưng dưới các giả định hợp lý thì INSERT, SEARCH, DELETE đều tốn O(1) trung bình; điều đó đạt được bằng cách *tính* chỉ số mảng từ khoá qua một hàm băm thay vì dùng thẳng khoá làm chỉ số, rồi giải quyết các va chạm không thể tránh khỏi bằng nối chuỗi hoặc địa chỉ mở; và khi chọn hàm băm ngẫu nhiên từ một lớp phổ quát, cận O(1) trung bình đúng với mọi dãy khoá, kể cả khoá do đối thủ chọn.** Mục 11.1 trình bày **bảng địa chỉ trực tiếp** (direct-address table): mảng T[0..m − 1] với mỗi ô ứng với một khoá của vũ trụ U = {0, 1, …, m − 1}; ba phép toán từ điển đều O(1) trong trường hợp xấu nhất, nhưng chỉ dùng được khi U nhỏ. Mục 11.2 giới thiệu **bảng băm** (hash table): phần tử khoá k được đặt ở ô h(k), với h : U → {0, 1, …, m − 1} và m nhỏ hơn nhiều so với |U|; vì |U| > m nên **va chạm** (collision) là không tránh khỏi; cách giải quyết đơn giản nhất là **nối chuỗi** (chaining) — mỗi ô trỏ tới một danh sách liên kết. Với **hệ số tải** (load factor) α = n/m và giả định **băm đều đơn giản** (simple uniform hashing), tìm kiếm thất bại và tìm kiếm thành công đều tốn thời gian trung bình Θ(1 + α) (Định lý 11.1, 11.2). Mục 11.3 bàn về hàm băm: một hàm tốt xấp xỉ giả định băm đều đơn giản; **phương pháp chia** h(k) = k mod m (nên chọn m là số nguyên tố không gần luỹ thừa của 2), **phương pháp nhân** h(k) = ⌊m (kA mod 1)⌋ (m có thể là luỹ thừa của 2, Knuth gợi ý A ≈ (√5 − 1)/2), và ★**băm phổ quát** (universal hashing): chọn ngẫu nhiên h từ một lớp ℋ mà với mọi cặp khoá khác nhau, xác suất va chạm ≤ 1/m; lớp ℋ_pm = {h_ab(k) = ((ak + b) mod p) mod m} là phổ quát (Định lý 11.5), và với nó mọi dãy n phép toán chứa O(m) lần INSERT tốn thời gian kỳ vọng Θ(n) (Hệ quả 11.4). Mục 11.4 trình bày **địa chỉ mở** (open addressing): mọi phần tử nằm ngay trong bảng, khi chèn ta **dò** (probe) lần lượt các ô theo một **dãy dò** phụ thuộc khoá; ba cách sinh dãy dò là **dò tuyến tính** (bị **tụ cụm sơ cấp**), **dò bậc hai** (bị **tụ cụm thứ cấp**) và **băm kép** (tốt nhất); dưới giả định **băm đều** (uniform hashing), tìm kiếm thất bại cần trung bình tối đa 1/(1 − α) lần dò (Định lý 11.6) và tìm kiếm thành công tối đa (1/α) ln(1/(1 − α)) lần dò (Định lý 11.8). Mục ★11.5 trình bày **băm hoàn hảo** (perfect hashing) cho tập khoá tĩnh: hai tầng băm phổ quát, tầng hai có bảng S_j kích thước m_j = n_j² nên không có va chạm, tìm kiếm tốn O(1) trong trường hợp xấu nhất, và tổng bộ nhớ kỳ vọng nhỏ hơn 2n ô cho các bảng tầng hai (Hệ quả 11.11).

> **Lưu ý:**
> - **Mục có dấu sao (★) trong chương:** Mục 11.3.3 "Universal hashing" (băm phổ quát) và Mục 11.5 "Perfect hashing" (băm hoàn hảo). **Bài tập có dấu sao:** 11.1-4, 11.3-5, 11.3-6, 11.4-4, 11.4-5, 11.5-1. Không bài toán cuối chương (Problem) nào có dấu sao.
> - **Lớp chữ PDF hỏng toàn bộ ký hiệu toán của chương, đã đọc lại từ ảnh trang:** `‚` là Θ, `˛` là α, `TŒ k` là T[k], `/NUL` là dấu trừ, `hW U!f0; ...g` là h : U → {0, …}, các dấu ≤, ≈, ≠, ∉, ⌊ ⌋, √ bị mất (ví dụ `h.k/Dbkmc` là h(k) = ⌊km⌋, `A .p5/NUL 1/=2` là A ≈ (√5 − 1)/2, `PrfX ig` là Pr{X ≥ i}); chữ ℋ (lớp hàm băm) bị trích thành H; các tổng và tích trong chứng minh Định lý 11.2, 11.3, 11.6, 11.8, 11.10, 11.12 và Bài toán 11-2 bị vỡ thành nhiều dòng. Mọi pseudocode, công thức, chứng minh và nội dung Hình 11.1–11.6 trong bản tổng hợp này được đối chiếu với ảnh trang 254, 256–260, 264–268, 270–276, 278–284. Các hình mũi tên (11.1, 11.2, 11.3, 11.5) và hình hai tầng (11.6) không có trong lớp chữ hoặc bị trích lộn xộn; người tổng hợp đọc trên ảnh (phóng to riêng Hình 11.6 trang 278) và tái hiện thành bảng/sơ đồ text.
> - **Lỗi trong Hình 11.6, trang 278 (nhận xét của người tổng hợp, đã tự tính lại):** bảng phụ S₇ có m₇ = 16, a₇ = 23, b₇ = 88 và p = 101. Hình đặt khoá 40 ở ô 7 của S₇. Tính lại: 23 · 40 + 88 = 1008; 1008 mod 101 = 1008 − 909 = 99; 99 mod 16 = 3. Vậy khoá 40 phải nằm ở **ô 3** của S₇, không phải ô 7. Ba khoá còn lại của S₇ khớp với hình: h₇(52) = ((1196 + 88) mod 101) mod 16 = 72 mod 16 = 8; h₇(22) = ((506 + 88) mod 101) mod 16 = 89 mod 16 = 9; h₇(37) = ((851 + 88) mod 101) mod 16 = 30 mod 16 = 14. Kết luận "không có va chạm trong bảng phụ nào" vẫn đúng (các ô 3, 8, 9, 14 khác nhau). Người tổng hợp không chắc lỗi này có trong danh sách lỗi chính thức (errata) của ấn bản 3 hay không — theo hiểu biết của người tổng hợp, không tra cứu.
> - **Chỗ ký hiệu chưa chặt (nhận xét của người tổng hợp):** (1) Chú thích cuối trang 279 nói khi n_j = m_j = 1 thì dùng a = b = 0; nhưng lớp ℋ_{p,m_j} đòi a ∈ ℤ*_p, tức a ≠ 0, nên hàm "a = b = 0" về hình thức không thuộc lớp — vô hại vì bảng một ô thì mọi hàm đều trả về 0. (2) Trang 271 viết "cả ba kỹ thuật (dò tuyến tính, dò bậc hai, băm kép) đều bảo đảm dãy dò là một hoán vị của ⟨0, 1, …, m − 1⟩", nhưng chính trang 272 nói dò bậc hai chỉ dùng hết bảng khi c₁, c₂, m bị ràng buộc, và trang 273 nói băm kép cần h₂(k) nguyên tố cùng nhau với m. Câu ở trang 271 cần hiểu là "với tham số được chọn đúng". (3) Trong Hệ quả 11.4, chữ n vừa là số phép toán trong dãy, vừa được dùng trong α = n/m như số khoá đang lưu; lập luận đúng vì số khoá đang lưu không vượt quá số lần INSERT, tức O(m). (4) Trong Bài toán 11-4(d), chữ m vừa là thông điệp (message) vừa là ký hiệu kích thước bảng ở đầu bài toán.
> - **Mọi ví dụ số trong sách đã được tự kiểm tra lại và đúng** (trừ vị trí khoá 40 trong Hình 11.6 nêu ở trên): chuỗi `pt` trong cơ số 128 là 112 · 128 + 116 = 14452; 100 mod 12 = 4; ví dụ phương pháp nhân k = 123456, s = 2654435769 cho k · s = 327706022297664 = 76300 · 2³² + 17612864 và 14 bit cao của r₀ là 67; h₃,₄(8) = ((24 + 4) mod 17) mod 6 = 11 mod 6 = 5; băm kép k = 123456, m = 701, m′ = 700 cho h₁(k) = 80, h₂(k) = 257; Hình 11.5 (khoá 14 dò ô 1, ô 5 rồi vào ô 9); các con số 1,387 và 2,559 của Định lý 11.8 (giá trị đúng là 2 ln 2 ≈ 1,3863 và (10/9) ln 10 ≈ 2,5584); trong Hình 11.6 các giá trị h(75) = 2, h₂(75) = 7 và cách chia chín khoá vào các ô 0, 2, 5, 7 của bảng T.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương Bảng băm vẫn là Chương 11 nhưng được viết lại khá nhiều. Mục băm hoàn hảo (11.5 của ấn bản 3) bị bỏ. Phần hàm băm được tổ chức lại quanh ý "băm tĩnh" và "băm ngẫu nhiên", trình bày phương pháp nhân dưới dạng cài đặt nhân-dịch bit (multiply-shift) và có thêm phần về băm đầu vào dài (vector, chuỗi), có nhắc tới hàm băm mật mã. Có thêm một mục về các cân nhắc thực tế (bộ nhớ đệm, hệ thống bộ nhớ phân cấp), trong đó dò tuyến tính được đánh giá lại tích cực hơn và có thủ tục xoá cho dò tuyến tính không cần giá trị DELETED. Các chi tiết khác người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần mở đầu chương (trước Mục 11.1, trang 253) — từ điển và bảng băm

```text
       Nhiều ứng dụng chỉ cần một tập động hỗ trợ ba phép toán TỪ ĐIỂN:
       INSERT, SEARCH, DELETE
       (ví dụ: bảng ký hiệu của trình biên dịch, khoá là tên định danh)
                                │
                                ▼
       Bảng băm là cấu trúc hiệu quả để cài đặt từ điển
       · xấu nhất: tìm kiếm Θ(n) — chậm như danh sách liên kết
       · dưới giả định hợp lý: tìm kiếm trung bình O(1)
                                │
                                ▼
       Bảng băm tổng quát hoá MẢNG thông thường
       · mảng: xem một ô bất kỳ trong O(1)  → địa chỉ trực tiếp (11.1)
       · khi số khoá thực sự lưu nhỏ so với số khoá có thể có:
         chỉ số mảng được TÍNH từ khoá, mảng chỉ cần cỡ tỷ lệ với số
         khoá thực sự lưu
                                │
                                ▼
       Trình tự chương:
       11.1 bảng địa chỉ trực tiếp
       11.2 bảng băm, va chạm, giải quyết bằng NỐI CHUỖI
       11.3 cách tính chỉ số từ khoá: các HÀM BĂM
       11.4 ĐỊA CHỈ MỞ — cách khác để giải quyết va chạm
       11.5 BĂM HOÀN HẢO — tìm kiếm O(1) trong trường hợp XẤU NHẤT khi
            tập khoá tĩnh
```

### Mục 11.1 — Bảng địa chỉ trực tiếp (Direct-address tables, trang 254–255)

```text
       Vũ trụ khoá U = {0, 1, …, m−1} đủ nhỏ; không có hai phần tử trùng khoá
                                │
                                ▼
       BẢNG ĐỊA CHỈ TRỰC TIẾP T[0..m−1]: ô (slot) k ứng với khoá k
       · T[k] trỏ tới phần tử có khoá k
       · không có phần tử khoá k thì T[k] = NIL
                                │
                                ▼
       DIRECT-ADDRESS-SEARCH(T, k):  return T[k]
       DIRECT-ADDRESS-INSERT(T, x):  T[x.key] = x
       DIRECT-ADDRESS-DELETE(T, x):  T[x.key] = NIL
       ⇒ cả ba đều O(1) trong trường hợp xấu nhất
                                │
                                ▼
       Biến thể: lưu thẳng đối tượng trong ô (tiết kiệm bộ nhớ)
       · cần một khoá đặc biệt đánh dấu ô rỗng
       · có thể không cần lưu khoá (chỉ số ô chính là khoá), nhưng khi
         đó phải có cách khác để biết ô có rỗng hay không
```

### Mục 11.2 — Bảng băm (Hash tables, trang 256–261)

```text
       Nhược điểm của địa chỉ trực tiếp: U lớn thì bảng cỡ |U| không vừa
       bộ nhớ; tập khoá thực sự lưu K quá nhỏ so với U nên lãng phí
                                │
                                ▼
       BẢNG BĂM: bộ nhớ Θ(|K|), tìm kiếm vẫn O(1) — nhưng là thời gian
       TRUNG BÌNH (địa chỉ trực tiếp: O(1) XẤU NHẤT)
       · HÀM BĂM h : U → {0, 1, …, m−1}, với m ≪ |U|
       · phần tử khoá k được đặt ở ô h(k); h(k) là GIÁ TRỊ BĂM của k
                                │
                                ▼
       VA CHẠM: hai khoá băm vào cùng một ô
       · |U| > m nên không thể tránh hoàn toàn (nguyên lý chuồng bồ câu)
       · hàm băm "trông như ngẫu nhiên" (nhưng TẤT ĐỊNH) giảm số va chạm
       · vẫn cần cách GIẢI QUYẾT va chạm
                                │
                                ▼
       NỐI CHUỖI: ô j trỏ tới đầu danh sách liên kết các phần tử băm vào j
       · CHAINED-HASH-INSERT: chèn vào đầu danh sách T[h(x.key)] — O(1)
         xấu nhất (giả định x chưa có trong bảng)
       · CHAINED-HASH-SEARCH: tìm khoá k trong T[h(k)] — tỷ lệ độ dài chuỗi
       · CHAINED-HASH-DELETE: xoá x khỏi T[h(x.key)] — O(1) nếu danh sách
         liên kết ĐÔI (nhận con trỏ x, không nhận khoá)
                                │
                                ▼
       PHÂN TÍCH: hệ số tải α = n/m (số phần tử trung bình mỗi chuỗi)
       · xấu nhất: mọi khoá vào cùng một ô → Θ(n) + thời gian tính h
       · giả định BĂM ĐỀU ĐƠN GIẢN: mỗi phần tử có xác suất như nhau rơi
         vào mỗi ô trong m ô, độc lập với các phần tử khác
         ⇒ E[n_j] = α, với n_j là độ dài chuỗi T[j]
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
   Định lý 11.1: TÌM THẤT BẠI          Định lý 11.2: TÌM THÀNH CÔNG
   · duyệt hết chuỗi T[h(k)],          · số phần tử xem = 1 + số phần tử
     độ dài kỳ vọng α                    chèn SAU x vào cùng chuỗi
   · thời gian Θ(1 + α)                · E = 1 + α/2 − α/(2n)
                                       · thời gian Θ(1 + α)
               └────────────────┬────────────────┘
                                ▼
       Nếu m tỷ lệ ít nhất với n (n = O(m)) thì α = O(1)
       ⇒ cả ba phép toán từ điển O(1) trung bình
```

### Mục 11.3 — Hàm băm: phương pháp chia và phương pháp nhân (Hash functions, 11.3.1–11.3.2, trang 262–264)

```text
       Hàm băm tốt: xấp xỉ giả định băm đều đơn giản
       · thường KHÔNG kiểm chứng được (không biết phân phối khoá, khoá có
         thể không độc lập)
       · biết phân phối thì làm được: khoá thực ngẫu nhiên đều trong [0, 1)
         ⇒ h(k) = ⌊km⌋ thoả băm đều đơn giản
       · thực tế: dùng kỹ thuật kinh nghiệm (heuristic), giá trị băm nên độc
         lập với mọi quy luật trong dữ liệu (ví dụ pt và pts nên rơi khác ô)
       · đôi khi cần tính chất mạnh hơn: khoá "gần nhau" cho giá trị băm
         xa nhau (quan trọng với dò tuyến tính)
                                │
                                ▼
       Diễn giải khoá thành SỐ TỰ NHIÊN: chuỗi = số trong cơ số thích hợp
       ví dụ "pt" = (112, 116) trong ASCII → cơ số 128:
       112 · 128 + 116 = 14452
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
   11.3.1 PHƯƠNG PHÁP CHIA             11.3.2 PHƯƠNG PHÁP NHÂN
   h(k) = k mod m                      h(k) = ⌊m (kA mod 1)⌋, 0 < A < 1
   · nhanh: một phép chia              · m không quan trọng, thường 2^p
   · TRÁNH m = 2^p (chỉ lấy p bit      · cài bằng số nguyên: s = A · 2^w,
     thấp của k)                         k · s = r₁ · 2^w + r₀,
   · tránh m = 2^p − 1 khi khoá là       h(k) = p bit cao nhất của r₀
     chuỗi cơ số 2^p (hoán vị ký tự    · Knuth: A ≈ (√5 − 1)/2
     không đổi giá trị băm)              = 0,6180339887…
   · nên chọn m nguyên tố, không gần   · ví dụ k = 123456, p = 14,
     luỹ thừa của 2                      w = 32, s = 2654435769
   · ví dụ n = 2000 chuỗi, chấp nhận     ⇒ h(k) = 67
     ~3 phần tử mỗi lần tìm thất bại
     ⇒ m = 701
```

### Mục ★11.3.3 — Băm phổ quát (Universal hashing, trang 265–268)

```text
       Mọi hàm băm CỐ ĐỊNH đều có điểm yếu: đối thủ chọn n khoá cùng rơi
       vào một ô ⇒ truy xuất trung bình Θ(n)
                                │
                                ▼
       Cách chữa duy nhất hiệu quả: chọn hàm băm NGẪU NHIÊN, độc lập với
       các khoá, lúc bắt đầu chạy (giống quicksort ngẫu nhiên)
                                │
                                ▼
       Lớp ℋ các hàm U → {0, …, m−1} là PHỔ QUÁT nếu với mọi cặp khoá
       khác nhau k, l: số hàm h ∈ ℋ có h(k) = h(l) không quá |ℋ|/m
       (tức xác suất va chạm ≤ 1/m, như khi h(k), h(l) được chọn ngẫu
       nhiên độc lập)
                                │
                                ▼
       Định lý 11.3 (nối chuỗi, h phổ quát, n khoá, m ô):
       · k không có trong bảng: E[n_h(k)] ≤ α
       · k có trong bảng:       E[n_h(k)] ≤ 1 + α
       (kỳ vọng lấy theo lựa chọn hàm băm, KHÔNG giả định gì về khoá)
                                │
                                ▼
       Hệ quả 11.4: mọi dãy n phép INSERT/SEARCH/DELETE chứa O(m) lần INSERT
       trên bảng m ô ban đầu rỗng tốn thời gian kỳ vọng Θ(n)
                                │
                                ▼
       XÂY DỰNG lớp phổ quát: chọn số nguyên tố p > mọi khoá (p > m)
       h_ab(k) = ((ak + b) mod p) mod m,   a ∈ {1, …, p−1}, b ∈ {0, …, p−1}
       ℋ_pm có p(p − 1) hàm; m tuỳ ý (không cần nguyên tố)
       ví dụ p = 17, m = 6: h₃,₄(8) = 5
                                │
                                ▼
       Định lý 11.5: ℋ_pm là phổ quát. Chứng minh:
       · k ≠ l ⇒ r = (ak+b) mod p khác s = (al+b) mod p (p nguyên tố)
       · (a, b) với a ≠ 0  ↔  (r, s) với r ≠ s là song ánh
         ⇒ (r, s) phân bố đều trên các cặp khác nhau
       · với r cố định, số s ≠ r có s ≡ r (mod m) ≤ ⌈p/m⌉ − 1 ≤ (p−1)/m
         ⇒ Pr{va chạm} ≤ 1/m
```

### Mục 11.4 — Địa chỉ mở (Open addressing, trang 269–277)

```text
       Mọi phần tử nằm NGAY TRONG BẢNG; mỗi ô chứa một phần tử hoặc NIL
       · không danh sách, không con trỏ ⇒ cùng bộ nhớ có nhiều ô hơn
       · bảng có thể đầy ⇒ α ≤ 1
                                │
                                ▼
       DÒ (probe): xét lần lượt các ô theo DÃY DÒ phụ thuộc khoá
       h : U × {0, 1, …, m−1} → {0, 1, …, m−1}
       dãy dò ⟨h(k,0), h(k,1), …, h(k,m−1)⟩ phải là một HOÁN VỊ của
       ⟨0, 1, …, m−1⟩
                                │
                                ▼
       HASH-INSERT: dò tới ô NIL đầu tiên, đặt khoá vào; dò hết m ô thì
                    báo lỗi "tràn bảng"
       HASH-SEARCH: dò cùng dãy; dừng khi gặp k (thành công) hoặc gặp NIL
                    hoặc đã dò m ô (thất bại)
       XOÁ khó: không được ghi NIL (làm đứt dãy dò của khoá khác) ⇒ ghi
       DELETED; INSERT coi DELETED như ô rỗng; SEARCH đi qua DELETED
       ⇒ thời gian tìm không còn phụ thuộc α; cần xoá thì nên nối chuỗi
                                │
                                ▼
       Giả định BĂM ĐỀU: dãy dò của mỗi khoá có xác suất như nhau là bất
       kỳ hoán vị nào trong m! hoán vị
                                │
          ┌─────────────────────┼─────────────────────┐
          ▼                     ▼                     ▼
   DÒ TUYẾN TÍNH         DÒ BẬC HAI              BĂM KÉP
   (h′(k) + i) mod m     (h′(k) + c₁i + c₂i²)    (h₁(k) + i·h₂(k)) mod m
                         mod m
   · m dãy dò            · m dãy dò              · Θ(m²) dãy dò (m nguyên
   · TỤ CỤM SƠ CẤP: ô    · TỤ CỤM THỨ CẤP: hai     tố hoặc 2^p)
     rỗng sau i ô đầy      khoá cùng ô đầu thì   · h₂(k) phải nguyên tố
     bị lấp với xác        cùng cả dãy             cùng nhau với m
     suất (i+1)/m        · c₁, c₂, m bị ràng     · gần với băm đều lý
                           buộc (Bài toán 11-3)    tưởng nhất
          └─────────────────────┼─────────────────────┘
                                ▼
       Định lý 11.6: tìm THẤT BẠI tốn ≤ 1/(1 − α) lần dò kỳ vọng
       · Pr{X ≥ i} ≤ α^(i−1); E[X] = Σ Pr{X ≥ i} ≤ Σ α^(i−1) = 1/(1−α)
       · α = 0,5 ⇒ ≤ 2 lần dò; α = 0,9 ⇒ ≤ 10 lần dò
                                │
                                ▼
       Hệ quả 11.7: CHÈN tốn ≤ 1/(1 − α) lần dò kỳ vọng
                                │
                                ▼
       Định lý 11.8: tìm THÀNH CÔNG tốn ≤ (1/α) ln(1/(1−α)) lần dò kỳ vọng
       · tìm khoá thứ i+1 lặp lại đúng dãy dò lúc chèn: ≤ m/(m − i)
       · trung bình trên n khoá, chặn tổng bằng tích phân
       · α = 0,5 ⇒ < 1,387; α = 0,9 ⇒ < 2,559
```

### Mục ★11.5 — Băm hoàn hảo (Perfect hashing, trang 277–282)

```text
       Tập khoá TĨNH (không đổi sau khi lưu): từ khoá của ngôn ngữ lập
       trình, tên tệp trên đĩa CD-ROM
       BĂM HOÀN HẢO: tìm kiếm cần O(1) lần truy cập bộ nhớ trong trường
       hợp XẤU NHẤT
                                │
                                ▼
       HAI TẦNG BĂM, mỗi tầng dùng băm phổ quát
       · tầng 1: h ∈ ℋ_pm băm n khoá vào m = n ô (như nối chuỗi)
       · tầng 2: thay danh sách bằng bảng phụ S_j cỡ m_j = n_j² với hàm
         h_j ∈ ℋ_{p,m_j} chọn sao cho KHÔNG có va chạm
                                │
                                ▼
       Định lý 11.9: n khoá vào bảng cỡ m = n² với h phổ quát ngẫu nhiên
       ⇒ Pr{có va chạm} < 1/2
       · E[số va chạm] = C(n,2) · 1/n² = (n² − n)/(2n²) < 1/2
       · bất đẳng thức Markov với t = 1
       ⇒ thử vài hàm ngẫu nhiên là tìm được hàm không va chạm
                                │
                                ▼
       Bộ nhớ: bảng T, các m_j, a_j, b_j: O(n). Các bảng phụ:
       Định lý 11.10: m = n ⇒ E[Σ n_j²] < 2n
       · n_j² = n_j + 2·C(n_j, 2)
       · Σ C(n_j, 2) = số cặp va chạm, kỳ vọng ≤ C(n,2)/n = (n−1)/2
       · E[Σ n_j²] ≤ n + (n − 1) = 2n − 1 < 2n
                                │
                                ▼
       Hệ quả 11.11: E[tổng cỡ các bảng phụ] = E[Σ m_j] < 2n
       Hệ quả 11.12: Pr{Σ m_j ≥ 4n} < 1/2 (Markov, t = 4n)
       ⇒ thử vài hàm tầng 1 là có hàm dùng bộ nhớ hợp lý
                                │
                                ▼
       Ví dụ: K = {10, 22, 37, 40, 52, 60, 70, 72, 75}, a = 3, b = 42,
       p = 101, m = 9 ⇒ các ô 0: {10}; 2: {60, 72, 75}; 5: {70};
       7: {22, 37, 40, 52}; bảng phụ cỡ 1, 9, 1, 16
```

### Bài toán cuối chương (Problems 11-1 đến 11-4, trang 282–284)

```text
       11-1 Cận lần dò dài nhất (địa chỉ mở, n ≤ m/2, băm đều)
            · Pr{lần chèn thứ i cần > k lần dò} ≤ 2^(−k)
            · Pr{> 2 lg n lần dò} = O(1/n²); Pr{max > 2 lg n} = O(1/n)
            · E[dãy dò dài nhất] = O(lg n)
                                │
                                ▼
       11-2 Cận cỡ ô lớn nhất (nối chuỗi, n khoá vào n ô)
            · Q_k = (1/n)^k (1 − 1/n)^(n−k) C(n,k) < e^k / k^k
            · E[M] = O(lg n / lg lg n), M = độ dài chuỗi dài nhất
                                │
                                ▼
       11-3 Dò bậc hai: j = (j + i) mod m, m = 2^p
            · là dò bậc hai với c₁ = c₂ = 1/2
            · xét đủ mọi ô của bảng
                                │
                                ▼
       11-4 Băm và xác thực
            · k-phổ quát: dãy giá trị băm của k khoá khác nhau phân bố đều
              trên m^k dãy; 2-phổ quát ⇒ phổ quát
            · h_a(x) = Σ a_j x_j mod p: phổ quát nhưng không 2-phổ quát
            · thêm + b: 2-phổ quát
            · thẻ xác thực t = h(m): đối thủ lừa được với xác suất ≤ 1/p
```

### Ghi chú chương (Chapter notes, trang 285)

```text
       Knuth và Gonnet: tài liệu tham khảo tốt về phân tích thuật toán băm
                                │
                                ▼
       H. P. Luhn (1953): phát minh bảng băm và phương pháp nối chuỗi
       (theo Knuth); cùng thời, G. M. Amdahl: ý tưởng địa chỉ mở
                                │
                                ▼
       Carter và Wegman (1979): khái niệm lớp hàm băm phổ quát
                                │
                                ▼
       Fredman, Komlós, Szemerédi: băm hoàn hảo cho tập tĩnh (Mục 11.5)
       Dietzfelbinger và cộng sự: mở rộng cho tập động, chèn và xoá trong
       thời gian kỳ vọng khấu hao O(1)
```

## Ba câu hỏi chương này trả lời

1. **Làm sao cài đặt từ điển (INSERT, SEARCH, DELETE) trong thời gian O(1) khi vũ trụ khoá rất lớn?** Nếu vũ trụ U = {0, …, m − 1} nhỏ, dùng bảng địa chỉ trực tiếp: phần tử khoá k nằm ở ô T[k], cả ba phép toán O(1) trong trường hợp xấu nhất. Khi U lớn (ví dụ mọi chuỗi ký tự), dùng bảng băm m ô: phần tử khoá k nằm ở ô h(k). Hai khoá có thể va chạm (vì |U| > m), nên mỗi ô trỏ tới một danh sách liên kết đôi (nối chuỗi), hoặc khoá được đặt vào ô rỗng đầu tiên trên một dãy dò (địa chỉ mở). Với nối chuỗi và giả định băm đều đơn giản, tìm kiếm tốn Θ(1 + α), α = n/m; chọn m tỷ lệ với n thì α = O(1). Ví dụ: 2000 chuỗi trong bảng m = 701 ô, α ≈ 2,85, mỗi lần tìm thất bại xem trung bình khoảng 3 phần tử.
2. **Chọn hàm băm thế nào, và có bảo đảm gì khi đối thủ chọn khoá?** Phương pháp chia h(k) = k mod m với m nguyên tố xa luỹ thừa của 2; phương pháp nhân h(k) = ⌊m (kA mod 1)⌋ với A ≈ 0,618 và m = 2^p, cài bằng một phép nhân số nguyên rồi lấy p bit cao của nửa thấp tích. Nhưng mọi hàm cố định đều có n khoá cùng rơi vào một ô. Băm phổ quát chọn ngẫu nhiên h từ một lớp mà mọi cặp khoá khác nhau va chạm với xác suất ≤ 1/m; lớp h_ab(k) = ((ak + b) mod p) mod m là phổ quát. Khi đó, với **mọi** tập khoá, độ dài kỳ vọng của chuỗi chứa khoá k là ≤ 1 + α, và một dãy n phép toán (O(m) lần chèn) tốn thời gian kỳ vọng Θ(n).
3. **Địa chỉ mở và băm hoàn hảo cho cận nào?** Với địa chỉ mở dưới giả định băm đều, tìm kiếm thất bại (và chèn) tốn ≤ 1/(1 − α) lần dò kỳ vọng, tìm kiếm thành công ≤ (1/α) ln(1/(1 − α)): bảng đầy 50% thì ≤ 2 và < 1,387 lần dò; đầy 90% thì ≤ 10 và < 2,559 lần dò. Với tập khoá tĩnh, băm hoàn hảo hai tầng (bảng tầng một n ô, bảng tầng hai cỡ n_j²) tìm kiếm O(1) trong trường hợp xấu nhất, tổng bộ nhớ kỳ vọng cho các bảng phụ nhỏ hơn 2n, và với xác suất > 1/2 một hàm ngẫu nhiên dùng dưới 4n ô.

## Khái niệm cần biết

- **Từ điển (dictionary):** tập động chỉ cần ba phép toán INSERT, SEARCH, DELETE (không cần MINIMUM, SUCCESSOR...). Ví dụ: bảng ký hiệu của trình biên dịch lưu các tên biến `count`, `i`, `total` cùng kiểu và địa chỉ; khi gặp `total` trong mã, trình biên dịch tìm kiếm khoá "total". Quan trọng vì bảng băm được thiết kế đúng cho nhóm phép toán này.
- **Vũ trụ khoá U (universe of keys) và tập khoá thực sự lưu K (actual keys):** U là mọi khoá có thể xuất hiện, K ⊆ U là các khoá đang có trong tập. Ví dụ: U là mọi số điện thoại 10 chữ số (10¹⁰ khoá), K là 500 số trong danh bạ một người. Sự chênh lệch |K| ≪ |U| là lý do cần bảng băm.
- **Bảng địa chỉ trực tiếp (direct-address table):** mảng T[0..m − 1], ô k dành riêng cho khoá k. Ví dụ U = {0, …, 9}, K = {2, 3, 5, 8}: T[2], T[3], T[5], T[8] trỏ tới các phần tử, sáu ô còn lại là NIL. Mọi phép toán O(1) xấu nhất, nhưng tốn |U| ô bộ nhớ.
- **Ô (slot):** một vị trí của bảng. Trong bảng địa chỉ trực tiếp, ô k ứng với khoá k; trong bảng băm, ô j chứa (hoặc trỏ tới) các phần tử có giá trị băm j.
- **Hàm băm (hash function) và giá trị băm (hash value):** h : U → {0, 1, …, m − 1}; khoá k "băm vào" (hashes to) ô h(k), và h(k) là giá trị băm của k. Ví dụ h(k) = k mod 9: khoá 28 có giá trị băm 1. Hàm băm phải tất định: cùng khoá luôn cho cùng giá trị.
- **Va chạm (collision):** hai khoá khác nhau có cùng giá trị băm. Ví dụ với h(k) = k mod 9, khoá 10, 19, 28 cùng vào ô 1. Không tránh được vì |U| > m; câu hỏi chỉ là giải quyết thế nào.
- **Nối chuỗi (chaining):** mỗi ô trỏ tới đầu một danh sách liên kết chứa mọi phần tử băm vào ô đó. Ví dụ chèn 10, 19, 28 (theo thứ tự đó) vào ô 1: danh sách là 28 → 19 → 10 (chèn vào đầu). Đây là cách giải quyết va chạm thứ nhất của chương.
- **Hệ số tải (load factor) α = n/m:** số phần tử trung bình mỗi ô. Ví dụ n = 2000, m = 701 thì α ≈ 2,85; với nối chuỗi α có thể lớn hơn 1, với địa chỉ mở α ≤ 1. Mọi cận thời gian của chương được phát biểu theo α.
- **Băm đều đơn giản (simple uniform hashing):** giả định mỗi phần tử có xác suất như nhau 1/m rơi vào mỗi ô, độc lập với các phần tử khác. Hệ quả: độ dài kỳ vọng mỗi chuỗi là E[n_j] = α. Ví dụ m = 4: một khoá mới rơi vào ô 2 với xác suất 1/4 bất kể các khoá cũ ở đâu. Đây là giả định của Định lý 11.1, 11.2.
- **Tìm kiếm thất bại / thành công (unsuccessful / successful search):** thất bại khi không phần tử nào có khoá k (phải duyệt hết chuỗi), thành công khi tìm thấy. Ví dụ chuỗi ô 1 là 28 → 19 → 10: tìm 37 (37 mod 9 = 1) thất bại sau 3 phần tử; tìm 19 thành công ở phần tử thứ 2.
- **Phương pháp chia (division method):** h(k) = k mod m. Ví dụ m = 12, k = 100: h(k) = 4. Nên chọn m nguyên tố xa luỹ thừa của 2, ví dụ m = 701.
- **Phương pháp nhân (multiplication method):** h(k) = ⌊m (kA mod 1)⌋, kA mod 1 là phần lẻ của kA. Ví dụ m = 1000, A = 0,6180339887, k = 61: 61A = 37,700…, phần lẻ 0,700…, h(61) = 700. Ưu điểm: m tuỳ ý, thường chọn 2^p để tính nhanh bằng dịch bit.
- **Băm phổ quát (universal hashing) và lớp hàm băm phổ quát:** lớp hữu hạn ℋ là phổ quát nếu với mọi cặp khoá khác nhau k, l, số hàm h ∈ ℋ có h(k) = h(l) không quá |ℋ|/m. Ví dụ ℋ₇,₃ = {((ak + b) mod 7) mod 3} có 6 · 7 = 42 hàm; người tổng hợp đếm với cặp khoá (1, 4): đúng 10 hàm làm chúng va chạm, 10 ≤ 42/3 = 14. Quan trọng vì nó cho cận kỳ vọng đúng với mọi tập khoá.
- **Địa chỉ mở (open addressing):** mọi phần tử nằm trong chính bảng; khi chèn, dò lần lượt các ô theo dãy dò tới ô rỗng. Ví dụ m = 11, dò tuyến tính, khoá 15 có ô đầu 4 đã bị khoá 4 chiếm, dò tiếp ô 5 và đặt vào đó.
- **Dãy dò (probe sequence):** ⟨h(k, 0), h(k, 1), …, h(k, m − 1)⟩, phải là hoán vị của ⟨0, …, m − 1⟩ để mọi ô đều có lúc được xét. Ví dụ dò tuyến tính với h′(k) = 9, m = 11: ⟨9, 10, 0, 1, …, 8⟩.
- **Băm đều (uniform hashing):** giả định dãy dò của mỗi khoá có xác suất như nhau là bất kỳ hoán vị nào trong m! hoán vị — mở rộng của băm đều đơn giản cho cả dãy dò. Ví dụ m = 3: mỗi khoá có dãy dò là một trong 6 hoán vị ⟨0,1,2⟩, ⟨0,2,1⟩, …, mỗi hoán vị xác suất 1/6. Ba phương pháp thực tế đều không đạt giả định này (chỉ sinh tối đa m² dãy).
- **Dò tuyến tính và tụ cụm sơ cấp (linear probing, primary clustering):** h(k, i) = (h′(k) + i) mod m. Các đoạn ô liên tiếp đã bị chiếm dài dần lên vì một ô rỗng đứng sau i ô đầy sẽ được lấp ở lần chèn kế tiếp với xác suất (i + 1)/m. Ví dụ m = 100, sau một đoạn 9 ô đầy, ô rỗng ngay sau đoạn đó bị lấp với xác suất 10/100, gấp 10 lần một ô rỗng đứng sau ô rỗng.
- **Dò bậc hai và tụ cụm thứ cấp (quadratic probing, secondary clustering):** h(k, i) = (h′(k) + c₁i + c₂i²) mod m. Hai khoá cùng ô đầu thì có cùng toàn bộ dãy dò. Ví dụ c₁ = 1, c₂ = 3, m = 11, h′(k) = 4: dãy dò bắt đầu 4, 8, 7, … cho mọi khoá có h′(k) = 4.
- **Băm kép (double hashing):** h(k, i) = (h₁(k) + i·h₂(k)) mod m; bước nhảy h₂(k) cũng phụ thuộc khoá. Ví dụ m = 13, h₁(k) = k mod 13, h₂(k) = 1 + (k mod 11), khoá 14: dãy dò 1, 5, 9, … Cần h₂(k) nguyên tố cùng nhau với m.
- **Giá trị DELETED:** dấu đánh dấu ô đã từng có khoá nhưng bị xoá trong địa chỉ mở, để tìm kiếm không dừng sai chỗ. Ví dụ: khoá A ở ô 4, khoá B (ô đầu 4) bị đẩy sang ô 5; xoá A bằng cách ghi NIL thì tìm B sẽ dừng ngay ở ô 4 rỗng và báo sai "không có"; ghi DELETED thì tìm kiếm đi tiếp sang ô 5.
- **Băm hoàn hảo (perfect hashing):** cách băm mà tìm kiếm cần O(1) lần truy cập bộ nhớ trong trường hợp xấu nhất, cho tập khoá tĩnh. Ví dụ ở Mục 11.5: 9 khoá, bảng tầng một 9 ô, bảng phụ cỡ 1, 9, 1, 16, không va chạm.
- **Biến ngẫu nhiên chỉ thị và tính tuyến tính của kỳ vọng (indicator random variable, linearity of expectation):** I{A} = 1 nếu A xảy ra; E[I{A}] = Pr{A} (Bổ đề 5.1); kỳ vọng của tổng bằng tổng kỳ vọng. Ví dụ X_ij = I{h(k_i) = h(k_j)} có E[X_ij] = 1/m. Là công cụ của mọi chứng minh trong chương.
- **Bất đẳng thức Markov (Markov's inequality):** với biến ngẫu nhiên X ≥ 0, Pr{X ≥ t} ≤ E[X]/t (công thức (C.30)). Ví dụ E[số va chạm] < 1/2 thì Pr{có ít nhất 1 va chạm} < 1/2. Dùng trong Định lý 11.9 và Hệ quả 11.12.
- **Nghịch đảo modulo p (multiplicative inverse modulo p):** với p nguyên tố và x ≢ 0, tồn tại duy nhất y ∈ {1, …, p − 1} sao cho xy ≡ 1 (mod p). Ví dụ p = 7, x = 3: y = 5 vì 15 = 2 · 7 + 1. Dùng trong chứng minh Định lý 11.5 để giải ngược (a, b) từ (r, s).

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 253)

Nhiều ứng dụng cần một tập động chỉ hỗ trợ ba phép toán từ điển INSERT, SEARCH và DELETE. Ví dụ, một trình biên dịch dịch một ngôn ngữ lập trình duy trì một **bảng ký hiệu** (symbol table), trong đó khoá của các phần tử là các chuỗi ký tự tuỳ ý ứng với các tên định danh (identifier) trong chương trình. Bảng băm là một cấu trúc dữ liệu hiệu quả để cài đặt từ điển. Tìm một phần tử trong bảng băm có thể lâu ngang tìm trong danh sách liên kết — Θ(n) trong trường hợp xấu nhất — nhưng trong thực tế băm chạy cực kỳ tốt: dưới các giả định hợp lý, thời gian trung bình để tìm một phần tử là O(1).

Bảng băm tổng quát hoá khái niệm đơn giản hơn là mảng thông thường. Định địa chỉ trực tiếp vào mảng tận dụng khả năng xem một vị trí bất kỳ của mảng trong O(1) (Mục 11.1). Ta dùng được địa chỉ trực tiếp khi có thể cấp phát một mảng có một vị trí cho **mọi** khoá có thể có.

Khi số khoá thực sự được lưu nhỏ so với tổng số khoá có thể có, bảng băm trở thành lựa chọn hiệu quả thay cho địa chỉ trực tiếp, vì bảng băm thường dùng một mảng có kích thước tỷ lệ với số khoá thực sự lưu. Thay vì dùng khoá làm chỉ số mảng trực tiếp, chỉ số mảng được **tính** từ khoá. Mục 11.2 trình bày ý chính, tập trung vào "nối chuỗi" để xử lý "va chạm" (nhiều khoá ứng với cùng một chỉ số mảng). Mục 11.3 mô tả cách tính chỉ số từ khoá bằng hàm băm, với vài biến thể và phân tích. Mục 11.4 xét "địa chỉ mở", một cách khác để xử lý va chạm. Kết luận chung: băm là kỹ thuật cực kỳ hiệu quả và thực dụng, các phép toán từ điển cơ bản chỉ tốn O(1) trung bình. Mục 11.5 giải thích "băm hoàn hảo" có thể hỗ trợ tìm kiếm trong O(1) **trong trường hợp xấu nhất** khi tập khoá là tĩnh (không bao giờ thay đổi sau khi lưu).

### 2. Bảng địa chỉ trực tiếp (11.1 Direct-address tables, trang 254–255)

Định địa chỉ trực tiếp là kỹ thuật đơn giản, hoạt động tốt khi vũ trụ khoá U khá nhỏ. Giả sử ứng dụng cần một tập động mà mỗi phần tử có khoá lấy từ U = {0, 1, …, m − 1}, với m không quá lớn, và không có hai phần tử nào cùng khoá.

Để biểu diễn tập động, ta dùng một mảng gọi là **bảng địa chỉ trực tiếp** (direct-address table), ký hiệu T[0..m − 1], trong đó mỗi vị trí, gọi là **ô** (slot), ứng với một khoá trong U. Ô k trỏ tới phần tử có khoá k của tập; nếu tập không có phần tử khoá k thì T[k] = NIL.

Hình minh hoạ của sách (Hình 11.1) với U = {0, 1, …, 9} và tập khoá thực sự lưu K = {2, 3, 5, 8}, vẽ lại thành bảng:

| Ô của T | Nội dung | Đối tượng được trỏ tới (khoá, dữ liệu vệ tinh) |
|---|---|---|
| 0 | NIL (tô đậm) | — |
| 1 | NIL | — |
| 2 | con trỏ | khoá 2, dữ liệu vệ tinh |
| 3 | con trỏ | khoá 3, dữ liệu vệ tinh |
| 4 | NIL | — |
| 5 | con trỏ | khoá 5, dữ liệu vệ tinh |
| 6 | NIL | — |
| 7 | NIL | — |
| 8 | con trỏ | khoá 8, dữ liệu vệ tinh |
| 9 | NIL | — |

Trong hình, vũ trụ U là một hình elip lớn chứa các khoá 0..9; bên trong có elip nhỏ K chứa 2, 3, 5, 8; từ mỗi khoá trong K có mũi tên chỉ tới ô tương ứng của T, và từ ô đó có mũi tên tới đối tượng gồm hai trường "key" và "satellite data". Các khoá 0, 1, 4, 6, 7, 9 nằm ngoài K nên ô của chúng chứa NIL.

Các phép toán từ điển cài đặt rất đơn giản:

```text
DIRECT-ADDRESS-SEARCH(T, k)
1  return T[k]

DIRECT-ADDRESS-INSERT(T, x)
1  T[x.key] = x

DIRECT-ADDRESS-DELETE(T, x)
1  T[x.key] = NIL
```

Mỗi phép toán chỉ tốn O(1). Lưu ý DELETE nhận con trỏ tới phần tử x (như quy ước của Phần III), không nhận khoá.

**Lưu thẳng phần tử trong bảng.** Với một số ứng dụng, chính bảng địa chỉ trực tiếp có thể chứa các phần tử của tập động: thay vì lưu khoá và dữ liệu vệ tinh trong một đối tượng bên ngoài bảng và để ô của bảng trỏ tới đối tượng đó, ta lưu đối tượng ngay trong ô, tiết kiệm bộ nhớ. Khi đó cần một khoá đặc biệt trong đối tượng để báo ô rỗng. Hơn nữa, thường không cần lưu khoá của đối tượng, vì có chỉ số của đối tượng trong bảng là có khoá của nó. Tuy nhiên, nếu không lưu khoá, ta phải có cách khác để biết một ô có rỗng hay không.

Ví dụ (người tổng hợp): quản lý trạng thái của 1.000 phòng khách sạn đánh số 0..999 bằng mảng T[0..999], T[k] là thông tin khách ở phòng k hoặc NIL. Chèn, xoá, tra cứu phòng 512 đều là một phép truy cập mảng. Nhưng nếu khoá là số căn cước công dân 12 chữ số, mảng cần 10¹² ô — không khả thi; đó là lúc cần bảng băm.

#### Ví dụ hôm nay

Địa chỉ trực tiếp xuất hiện khắp nơi dưới dạng "mảng tra cứu" (lookup table): mảng 256 phần tử ánh xạ mỗi byte sang lớp ký tự (chữ, số, dấu cách) trong bộ phân tích từ vựng; mảng đếm tần suất của sắp xếp đếm (Chương 8); bảng trang (page table) của hệ điều hành ánh xạ số trang ảo sang khung trang vật lý; bitset/bitmap (Bài tập 11.1-2) để đánh dấu các số nguyên đã gặp — theo hiểu biết của người tổng hợp.

### 3. Bảng băm (11.2 Hash tables, trang 256–261)

Nhược điểm của địa chỉ trực tiếp là rõ ràng: nếu vũ trụ U lớn, lưu một bảng T cỡ |U| có thể không thực tế hoặc không thể với bộ nhớ của một máy tính thông thường. Hơn nữa, tập K các khoá **thực sự được lưu** có thể nhỏ tới mức phần lớn bộ nhớ cấp cho T bị lãng phí.

Khi tập K các khoá lưu trong từ điển nhỏ hơn nhiều so với vũ trụ U, bảng băm cần ít bộ nhớ hơn nhiều so với bảng địa chỉ trực tiếp. Cụ thể, ta giảm được bộ nhớ xuống Θ(|K|) mà vẫn giữ được lợi ích tìm kiếm chỉ tốn O(1). Điểm phải trả giá: cận O(1) này là cho **thời gian trung bình**, còn với địa chỉ trực tiếp nó đúng cho **thời gian xấu nhất**.

Với địa chỉ trực tiếp, phần tử khoá k được lưu ở ô k. Với băm, phần tử này được lưu ở ô h(k): ta dùng một **hàm băm** (hash function) h để tính ô từ khoá k. Ở đây h ánh xạ vũ trụ U vào các ô của **bảng băm** (hash table) T[0..m − 1]:

```text
h : U → {0, 1, …, m − 1}
```

với kích thước bảng m thường nhỏ hơn nhiều so với |U|. Ta nói phần tử khoá k **băm vào** (hashes to) ô h(k), và h(k) là **giá trị băm** (hash value) của khoá k. Hàm băm thu hẹp miền chỉ số mảng, do đó thu nhỏ kích thước mảng: thay vì |U|, mảng chỉ cần m ô.

Hình minh hoạ ý tưởng (Hình 11.2), vẽ lại:

```text
   U (vũ trụ khoá)                       T
   ┌───────────────────────────┐        ┌─────┐ 0
   │   K (khoá thực sự lưu)    │        ├─────┤
   │   k₁ ─────────────────────┼──────▶ │     │ h(k₁)
   │   k₄ ─────────────────────┼──────▶ │     │ h(k₄)
   │   k₅ ─────────────────────┼──┐     ├─────┤
   │   k₂ ─────────────────────┼──┴───▶ │     │ h(k₂) = h(k₅)   ◀ va chạm
   │   k₃ ─────────────────────┼──────▶ │     │ h(k₃)
   └───────────────────────────┘        ├─────┤
                                        └─────┘ m − 1
```

Khoá k₂ và k₅ ánh xạ vào cùng một ô, nên chúng **va chạm**.

**Va chạm.** Có một trở ngại: hai khoá có thể băm vào cùng một ô. Tình huống này gọi là **va chạm** (collision). May mắn là có những kỹ thuật hiệu quả để giải quyết xung đột do va chạm gây ra.

Lý tưởng nhất là tránh va chạm hoàn toàn. Ta có thể thử đạt điều đó bằng cách chọn hàm băm h phù hợp. Một ý là làm cho h trông "ngẫu nhiên", nhờ đó tránh va chạm hoặc ít ra giảm số va chạm. Chính từ "to hash" (băm), gợi hình ảnh trộn và băm nhỏ ngẫu nhiên, thể hiện tinh thần cách làm này. (Dĩ nhiên hàm băm h phải tất định: một đầu vào k cho trước luôn phải cho cùng đầu ra h(k).) Tuy nhiên, vì |U| > m, chắc chắn có ít nhất hai khoá cùng giá trị băm; tránh va chạm hoàn toàn là không thể. Vì vậy, dù một hàm băm được thiết kế tốt, trông "ngẫu nhiên", có thể giảm số va chạm, ta vẫn cần một phương pháp giải quyết những va chạm xảy ra. Phần còn lại của mục này trình bày kỹ thuật đơn giản nhất, gọi là nối chuỗi; Mục 11.4 giới thiệu phương pháp thay thế, gọi là địa chỉ mở.

#### Giải quyết va chạm bằng nối chuỗi (Collision resolution by chaining)

Trong **nối chuỗi** (chaining), ta đặt mọi phần tử băm vào cùng một ô vào cùng một danh sách liên kết. Ô j chứa con trỏ tới đầu danh sách các phần tử đã lưu có giá trị băm j; nếu không có phần tử nào như vậy, ô j chứa NIL.

Hình minh hoạ (Hình 11.3), vẽ lại: bảng T có 9 ô (theo hình), tám khoá k₁, …, k₈, với h(k₁) = h(k₄) và h(k₅) = h(k₇) = h(k₂). Danh sách được vẽ là liên kết đôi (mỗi nút có con trỏ *prev* và *next*), vì xoá nhanh hơn theo cách đó.

```text
   T
  ┌───┐
  │ / │
  ├───┤
  │ ●─┼──▶ [ / | k₁ | ●]⇄[● | k₄ | / ]
  ├───┤
  │ / │
  ├───┤
  │ / │
  ├───┤
  │ ●─┼──▶ [ / | k₅ | ●]⇄[● | k₂ | ●]⇄[● | k₇ | / ]
  ├───┤
  │ / │
  ├───┤
  │ ●─┼──▶ [ / | k₃ | / ]
  ├───┤
  │ ●─┼──▶ [ / | k₈ | ●]⇄[● | k₆ | / ]
  ├───┤
  │ / │
  └───┘
   ( "/" là NIL; mỗi nút: [prev | khoá | next] )
```

Các phép toán từ điển trên bảng băm T khi va chạm được giải quyết bằng nối chuỗi rất dễ cài đặt:

```text
CHAINED-HASH-INSERT(T, x)
1  insert x at the head of list T[h(x.key)]

CHAINED-HASH-SEARCH(T, k)
1  search for an element with key k in list T[h(k)]

CHAINED-HASH-DELETE(T, x)
1  delete x from the list T[h(x.key)]
```

(Dịch: INSERT — chèn x vào đầu danh sách T[h(x.key)]; SEARCH — tìm phần tử có khoá k trong danh sách T[h(k)]; DELETE — xoá x khỏi danh sách T[h(x.key)]. Các thao tác danh sách chính là LIST-INSERT, LIST-SEARCH, LIST-DELETE của Chương 10.)

- **Chèn:** thời gian xấu nhất O(1). Thủ tục nhanh một phần vì nó **giả định** phần tử x chưa có trong bảng; nếu cần, có thể kiểm tra giả định này (tốn thêm) bằng cách tìm phần tử có khoá x.key trước khi chèn.
- **Tìm kiếm:** thời gian xấu nhất tỷ lệ với độ dài danh sách; phân tích kỹ ở dưới.
- **Xoá:** O(1) nếu danh sách liên kết đôi. Lưu ý CHAINED-HASH-DELETE nhận đầu vào là phần tử x, không phải khoá k, nên không phải tìm x trước. Nếu bảng băm hỗ trợ xoá thì các danh sách nên liên kết đôi để xoá nhanh. Nếu danh sách chỉ liên kết đơn, để xoá x ta phải tìm x trong danh sách T[h(x.key)] trước để cập nhật thuộc tính *next* của phần tử đứng trước x; khi đó xoá và tìm kiếm có cùng thời gian tiệm cận.

**Ví dụ chạy tay (người tổng hợp, dữ liệu của Bài tập 11.2-2):** bảng 9 ô, h(k) = k mod 9, chèn lần lượt 5, 28, 19, 15, 20, 33, 12, 17, 10. Giá trị băm: h(5) = 5, h(28) = 1, h(19) = 1, h(15) = 6, h(20) = 2, h(33) = 6, h(12) = 3, h(17) = 8, h(10) = 1. Mỗi khoá mới được chèn vào đầu chuỗi:

| Ô | Chuỗi (từ đầu tới cuối) |
|---|---|
| 0 | NIL |
| 1 | 10 → 19 → 28 |
| 2 | 20 |
| 3 | 12 |
| 4 | NIL |
| 5 | 5 |
| 6 | 33 → 15 |
| 7 | NIL |
| 8 | 17 |

n = 9, m = 9, α = 1. Tìm 37 (37 mod 9 = 1): duyệt 10, 19, 28 rồi báo thất bại — 3 phần tử. Tìm 28: thành công ở phần tử thứ 3.

#### Phân tích băm nối chuỗi (Analysis of hashing with chaining)

Băm nối chuỗi chạy tốt tới mức nào? Cụ thể, tìm một phần tử với khoá cho trước mất bao lâu?

Cho bảng băm T có m ô lưu n phần tử, ta định nghĩa **hệ số tải** (load factor) α của T là n/m, tức số phần tử trung bình lưu trong một chuỗi. Phân tích sẽ tính theo α, có thể nhỏ hơn, bằng hoặc lớn hơn 1.

**Trường hợp xấu nhất rất tệ:** cả n khoá băm vào cùng một ô, tạo một danh sách dài n. Thời gian tìm kiếm xấu nhất vì vậy là Θ(n) cộng thời gian tính hàm băm — không hơn gì dùng một danh sách liên kết cho mọi phần tử. Rõ ràng ta không dùng bảng băm vì hiệu năng xấu nhất của nó. (Tuy nhiên, băm hoàn hảo ở Mục 11.5 cho hiệu năng xấu nhất tốt khi tập khoá tĩnh.)

Hiệu năng trung bình phụ thuộc vào việc hàm băm h phân bố tập khoá cần lưu vào m ô tốt tới đâu, tính trung bình. Mục 11.3 bàn các vấn đề này; tạm thời ta giả định mọi phần tử cho trước có xác suất như nhau băm vào bất kỳ ô nào trong m ô, độc lập với việc các phần tử khác băm vào đâu. Ta gọi đây là giả định **băm đều đơn giản** (simple uniform hashing).

Với j = 0, 1, …, m − 1, ký hiệu độ dài danh sách T[j] là n_j, sao cho

```text
n = n₀ + n₁ + ⋯ + n_{m−1}                                             (11.1)
```

và giá trị kỳ vọng của n_j là E[n_j] = α = n/m.

Ta giả định tính giá trị băm h(k) tốn O(1), nên thời gian tìm phần tử khoá k phụ thuộc tuyến tính vào độ dài n_h(k) của danh sách T[h(k)]. Bỏ qua thời gian O(1) để tính hàm băm và truy cập ô h(k), ta xét số kỳ vọng các phần tử mà thuật toán tìm kiếm xem xét, tức số phần tử trong danh sách T[h(k)] mà thuật toán kiểm tra xem có khoá bằng k hay không. Có hai trường hợp: tìm kiếm **thất bại** (không phần tử nào trong bảng có khoá k) và tìm kiếm **thành công** (tìm được phần tử có khoá k).

**Định lý 11.1.** Trong bảng băm giải quyết va chạm bằng nối chuỗi, một lần tìm kiếm thất bại tốn thời gian trung bình Θ(1 + α), dưới giả định băm đều đơn giản.

*Chứng minh.* Dưới giả định băm đều đơn giản, một khoá k chưa có trong bảng có xác suất như nhau băm vào bất kỳ ô nào trong m ô. Thời gian kỳ vọng để tìm thất bại khoá k là thời gian kỳ vọng để duyệt tới cuối danh sách T[h(k)], có độ dài kỳ vọng E[n_h(k)] = α. Vậy số phần tử kỳ vọng được xem trong một lần tìm thất bại là α, và tổng thời gian (kể cả tính h(k)) là Θ(1 + α). ∎

Trường hợp tìm kiếm thành công hơi khác, vì các danh sách không có xác suất như nhau được tìm: xác suất một danh sách được tìm tỷ lệ với số phần tử nó chứa (danh sách dài thì nhiều khả năng chứa phần tử cần tìm hơn). Dù vậy, thời gian kỳ vọng vẫn là Θ(1 + α).

**Định lý 11.2.** Trong bảng băm giải quyết va chạm bằng nối chuỗi, một lần tìm kiếm thành công tốn thời gian trung bình Θ(1 + α), dưới giả định băm đều đơn giản.

*Chứng minh.* Giả định phần tử cần tìm có xác suất như nhau là bất kỳ phần tử nào trong n phần tử của bảng. Số phần tử được xem khi tìm thành công phần tử x bằng 1 cộng số phần tử đứng **trước** x trong danh sách của x. Vì phần tử mới luôn được chèn vào đầu danh sách, các phần tử đứng trước x đều được chèn **sau** x. Để tìm số phần tử kỳ vọng được xem, ta lấy trung bình trên n phần tử x của bảng, của 1 cộng số kỳ vọng các phần tử được thêm vào danh sách của x sau khi x được thêm.

Gọi x_i là phần tử thứ i được chèn vào bảng, i = 1, 2, …, n, và k_i = x_i.key. Với hai khoá k_i và k_j, định nghĩa biến ngẫu nhiên chỉ thị X_ij = I{h(k_i) = h(k_j)}. Dưới giả định băm đều đơn giản, Pr{h(k_i) = h(k_j)} = 1/m, nên theo Bổ đề 5.1, E[X_ij] = 1/m. Số phần tử kỳ vọng được xem khi tìm thành công là:

```text
E[ (1/n) Σᵢ₌₁ⁿ ( 1 + Σⱼ₌ᵢ₊₁ⁿ X_ij ) ]
   = (1/n) Σᵢ₌₁ⁿ ( 1 + Σⱼ₌ᵢ₊₁ⁿ E[X_ij] )          (tính tuyến tính của kỳ vọng)
   = (1/n) Σᵢ₌₁ⁿ ( 1 + Σⱼ₌ᵢ₊₁ⁿ 1/m )
   = 1 + (1/(nm)) Σᵢ₌₁ⁿ (n − i)
   = 1 + (1/(nm)) ( Σᵢ₌₁ⁿ n − Σᵢ₌₁ⁿ i )
   = 1 + (1/(nm)) ( n² − n(n + 1)/2 )             (theo công thức (A.1))
   = 1 + (n − 1)/(2m)
   = 1 + α/2 − α/(2n)
```

Giải thích dòng thứ tư: với mỗi i, tổng trong có n − i số hạng 1/m (j chạy từ i + 1 tới n). Vậy tổng thời gian cho một lần tìm thành công (kể cả tính hàm băm) là Θ(2 + α/2 − α/(2n)) = Θ(1 + α). ∎

**Kiểm tra bằng tay (người tổng hợp), n = 2, m = 2:** x₁ chèn trước, x₂ chèn sau. Tìm x₂: nó luôn ở đầu chuỗi, xem 1 phần tử. Tìm x₁: xem 1 phần tử nếu x₂ ở ô khác (xác suất 1/2), 2 phần tử nếu cùng ô (xác suất 1/2), kỳ vọng 1,5. Trung bình (1 + 1,5)/2 = 1,25. Công thức: 1 + (n − 1)/(2m) = 1 + 1/4 = 1,25. Khớp.

**Ý nghĩa của phân tích.** Nếu số ô của bảng băm ít nhất tỷ lệ với số phần tử trong bảng, ta có n = O(m), và do đó α = n/m = O(m)/m = O(1). Vậy tìm kiếm tốn thời gian hằng số trung bình. Vì chèn tốn O(1) xấu nhất và xoá tốn O(1) xấu nhất khi danh sách liên kết đôi, ta hỗ trợ được mọi phép toán từ điển trong O(1) trung bình.

Ví dụ số (người tổng hợp): n = 1.000.000 phần tử, m = 500.000 ô, α = 2: tìm thất bại xem trung bình 2 phần tử; tìm thành công xem trung bình 1 + 2/2 − 2/2.000.000 ≈ 2 phần tử. So với danh sách liên kết đơn thuần: trung bình 500.000 phần tử.

#### Ví dụ hôm nay

Hầu hết bảng băm của thư viện chuẩn dùng nối chuỗi: `HashMap` của Java (từ Java 8 còn chuyển một chuỗi dài hơn 8 phần tử thành cây đỏ-đen để chặn trường hợp xấu nhất ở O(lg n)), `std::unordered_map` của C++ (chuẩn gần như buộc dùng nối chuỗi vì yêu cầu con trỏ tới phần tử không đổi khi bảng lớn lên) — theo hiểu biết của người tổng hợp. Cả hai đều tự nhân đôi số ô khi α vượt một ngưỡng (0,75 với Java, 1,0 với C++), chính là cách giữ n = O(m) mà phân tích trên đòi hỏi.

### 4. Hàm băm (11.3 Hash functions, trang 262–269)

Mục này bàn một số vấn đề về thiết kế hàm băm tốt, rồi trình bày ba cách tạo hàm băm. Hai cách — băm theo phép chia và băm theo phép nhân — có bản chất kinh nghiệm (heuristic); cách thứ ba — băm phổ quát — dùng ngẫu nhiên để có hiệu năng tốt **chứng minh được**.

#### Thế nào là một hàm băm tốt? (What makes a good hash function?)

Một hàm băm tốt thoả (xấp xỉ) giả định băm đều đơn giản: mỗi khoá có xác suất như nhau băm vào bất kỳ ô nào trong m ô, độc lập với việc các khoá khác băm vào đâu. Đáng tiếc là thường không có cách kiểm tra điều kiện này, vì hiếm khi ta biết phân phối xác suất mà các khoá được lấy ra; hơn nữa, các khoá có thể không được lấy độc lập.

Đôi khi ta biết phân phối. Ví dụ, nếu biết các khoá là các số thực ngẫu nhiên k, độc lập và phân bố đều trong khoảng 0 ≤ k < 1, thì hàm băm

```text
h(k) = ⌊km⌋
```

thoả điều kiện băm đều đơn giản. (Ví dụ người tổng hợp: m = 10, k = 0,37 thì h(k) = ⌊3,7⌋ = 3; mỗi ô ứng với một đoạn con dài 1/10 của [0, 1).)

Trong thực tế, ta thường dùng kỹ thuật kinh nghiệm để tạo hàm băm chạy tốt. Thông tin định tính về phân phối khoá có thể hữu ích. Chẳng hạn, trong bảng ký hiệu của trình biên dịch, khoá là các chuỗi biểu diễn tên định danh; các ký hiệu gần nhau như `pt` và `pts` hay cùng xuất hiện trong một chương trình. Hàm băm tốt nên giảm thiểu khả năng các biến thể như vậy băm vào cùng ô.

Một cách tốt là tính giá trị băm sao cho ta kỳ vọng nó độc lập với mọi quy luật có thể có trong dữ liệu. Ví dụ, "phương pháp chia" (Mục 11.3.1) lấy giá trị băm là số dư khi chia khoá cho một số nguyên tố cho trước. Cách này thường cho kết quả tốt, miễn là số nguyên tố được chọn không liên quan tới quy luật nào trong phân phối khoá.

Cuối cùng, một số ứng dụng của hàm băm có thể cần tính chất mạnh hơn băm đều đơn giản. Ví dụ, ta có thể muốn các khoá "gần nhau" theo một nghĩa nào đó cho giá trị băm cách xa nhau. (Tính chất này đặc biệt cần khi dùng dò tuyến tính, Mục 11.4.) Băm phổ quát (Mục 11.3.3) thường cung cấp các tính chất mong muốn đó.

#### Diễn giải khoá thành số tự nhiên (Interpreting keys as natural numbers)

Hầu hết hàm băm giả định vũ trụ khoá là tập số tự nhiên ℕ = {0, 1, 2, …}. Vì vậy, nếu khoá không phải số tự nhiên, ta tìm cách diễn giải chúng thành số tự nhiên. Ví dụ, có thể coi một chuỗi ký tự là một số nguyên viết trong một cơ số thích hợp. Tên định danh `pt` có thể coi là cặp số thập phân (112, 116), vì trong bảng mã ASCII `p` = 112 và `t` = 116; viết dưới dạng số nguyên cơ số 128, `pt` thành (112 · 128) + 116 = 14452. Trong bối cảnh một ứng dụng cụ thể, ta thường nghĩ ra được cách như vậy để diễn giải mỗi khoá thành một số tự nhiên (có thể rất lớn). Từ đây ta giả định khoá là số tự nhiên.

Ví dụ thêm (người tổng hợp): `pts` = (112 · 128 + 116) · 128 + 115 = 14452 · 128 + 115 = 1.849.971. Một chuỗi 20 ký tự thành một số cỡ 128²⁰ ≈ 1,4 · 10⁴², vượt xa một từ máy; Bài tập 11.3-2 bàn cách tính phép chia dư mà không cần lưu số lớn này.

#### 11.3.1 Phương pháp chia (The division method)

Trong **phương pháp chia** (division method), ta ánh xạ khoá k vào một trong m ô bằng cách lấy số dư của k chia cho m:

```text
h(k) = k mod m
```

Ví dụ, nếu bảng băm cỡ m = 12 và khoá k = 100 thì h(k) = 4 (100 = 8 · 12 + 4). Vì chỉ cần một phép chia, băm theo phép chia khá nhanh.

Khi dùng phương pháp chia, ta thường tránh một số giá trị m:

- **m không nên là luỹ thừa của 2**: nếu m = 2^p thì h(k) chỉ là p bit thấp nhất của k. Trừ khi biết mọi mẫu p bit thấp đều đồng khả năng, tốt hơn là thiết kế hàm băm phụ thuộc vào **mọi** bit của khoá. (Ví dụ người tổng hợp: m = 16; mọi khoá là bội của 16 — chẳng hạn địa chỉ bộ nhớ căn lề 16 byte — đều có h(k) = 0.)
- **m = 2^p − 1 có thể là lựa chọn tồi khi k là chuỗi ký tự diễn giải trong cơ số 2^p**, vì hoán vị các ký tự của k không làm đổi giá trị băm (Bài tập 11.3-3).

Một số nguyên tố không quá gần một luỹ thừa chính xác của 2 thường là lựa chọn tốt cho m. Ví dụ: muốn cấp phát một bảng băm, giải quyết va chạm bằng nối chuỗi, chứa khoảng n = 2000 chuỗi ký tự, mỗi ký tự 8 bit. Ta chấp nhận xem trung bình 3 phần tử trong một lần tìm kiếm thất bại, nên cấp phát bảng cỡ m = 701. Chọn m = 701 vì nó là số nguyên tố gần 2000/3 (≈ 666,7) nhưng không gần luỹ thừa nào của 2 (gần nhất là 512 và 1024). Coi mỗi khoá k là một số nguyên, hàm băm là

```text
h(k) = k mod 701
```

Kiểm tra (người tổng hợp): α = 2000/701 ≈ 2,85, đúng là "khoảng 3" phần tử mỗi lần tìm thất bại (Định lý 11.1).

#### 11.3.2 Phương pháp nhân (The multiplication method)

**Phương pháp nhân** (multiplication method) tạo hàm băm qua hai bước. Thứ nhất, nhân khoá k với một hằng số A trong khoảng 0 < A < 1 và lấy phần lẻ của kA. Thứ hai, nhân giá trị đó với m và lấy phần nguyên dưới. Tóm lại:

```text
h(k) = ⌊m (kA mod 1)⌋
```

trong đó "kA mod 1" là phần lẻ của kA, tức kA − ⌊kA⌋.

Ưu điểm của phương pháp nhân là giá trị m không quan trọng. Ta thường chọn m là luỹ thừa của 2 (m = 2^p với p nguyên), vì khi đó dễ cài đặt hàm trên hầu hết máy tính như sau. Giả sử kích thước từ máy là w bit và k vừa một từ. Giới hạn A ở dạng phân số s/2^w, với s là số nguyên trong khoảng 0 < s < 2^w. Ta nhân k với số nguyên w bit s = A · 2^w. Kết quả là một giá trị 2w bit r₁ · 2^w + r₀, với r₁ là từ cao của tích và r₀ là từ thấp. Giá trị băm p bit cần tìm gồm **p bit cao nhất của r₀**.

Hình 11.4 của sách, vẽ lại:

```text
                         ◀──── w bit ────▶
                         ┌───────────────┐
                         │       k       │
                   ×     ├───────────────┤
                         │  s = A · 2^w  │
   ──────────────────────┴───────────────┴
   ┌───────────────┐     ┌───────────────┐
   │      r₁       │     │      r₀       │
   └───────────────┘     └───────────────┘
     (từ cao, bỏ)         ╰─ lấy p bit ─╯ (p bit cao nhất của r₀)
                          ┌───────┐
                          │ h(k)  │
                          └───────┘
```

Biểu diễn w bit của khoá k được nhân với giá trị w bit s = A · 2^w; p bit cao nhất của nửa thấp w bit của tích tạo thành giá trị băm h(k). Lý do đúng (người tổng hợp): kA = k · s / 2^w = r₁ + r₀/2^w, nên phần lẻ của kA là r₀/2^w; nhân với m = 2^p rồi lấy phần nguyên dưới chính là lấy p bit cao của r₀ (dịch phải r₀ đi w − p bit).

Phương pháp này hoạt động với mọi giá trị hằng A, nhưng với một số giá trị tốt hơn các giá trị khác. Lựa chọn tối ưu phụ thuộc đặc điểm dữ liệu. Knuth gợi ý

```text
A ≈ (√5 − 1)/2 = 0,6180339887…                                         (11.2)
```

có khả năng hoạt động khá tốt.

**Ví dụ của sách (đã tự kiểm tra):** k = 123456, p = 14, m = 2¹⁴ = 16384, w = 32. Theo gợi ý của Knuth, chọn A là phân số dạng s/2³² gần (√5 − 1)/2 nhất, tức A = 2654435769/2³². Khi đó

```text
k · s = 123456 · 2654435769 = 327706022297664 = (76300 · 2³²) + 17612864
⇒ r₁ = 76300, r₀ = 17612864
14 bit cao nhất của r₀ (dịch phải 32 − 14 = 18 bit): 17612864 / 2¹⁸ = 67,19…
⇒ h(k) = 67
```

(Kiểm tra: 67 · 2¹⁸ = 17.563.648 ≤ 17.612.864 < 68 · 2¹⁸ = 17.825.792.)

Ví dụ thêm (người tổng hợp, dữ liệu của Bài tập 11.3-4): m = 1000, A = (√5 − 1)/2; với k = 61: 61A ≈ 37,7001, phần lẻ ≈ 0,7001, h(61) = 700; k = 62: 62A ≈ 38,3181, h(62) = 318. Hai khoá liền nhau rơi xa nhau — đúng tính chất "khoá gần nhau cho giá trị băm xa nhau".

#### ★ 11.3.3 Băm phổ quát (Universal hashing)

Nếu một đối thủ ác ý chọn các khoá để băm bằng một hàm băm cố định nào đó, đối thủ có thể chọn n khoá cùng băm vào một ô, làm thời gian truy xuất trung bình là Θ(n). Mọi hàm băm cố định đều dễ bị trường hợp xấu nhất tệ hại này; cách hiệu quả duy nhất để cải thiện là chọn hàm băm **ngẫu nhiên** theo cách **độc lập** với các khoá thực sự sẽ được lưu. Cách làm này, gọi là **băm phổ quát** (universal hashing), cho hiệu năng trung bình tốt chứng minh được, bất kể đối thủ chọn khoá nào.

Trong băm phổ quát, lúc bắt đầu chạy, ta chọn hàm băm ngẫu nhiên từ một lớp hàm được thiết kế cẩn thận. Như với quicksort, ngẫu nhiên bảo đảm không đầu vào nào luôn gây ra trường hợp xấu nhất. Vì hàm băm được chọn ngẫu nhiên, thuật toán có thể hành xử khác nhau ở mỗi lần chạy, kể cả với cùng đầu vào, và bảo đảm hiệu năng trung bình tốt với mọi đầu vào. Trở lại ví dụ bảng ký hiệu của trình biên dịch: lựa chọn tên định danh của lập trình viên không còn có thể gây hiệu năng băm tệ một cách nhất quán. Hiệu năng tệ chỉ xảy ra khi trình biên dịch chọn trúng một hàm băm ngẫu nhiên làm tập tên định danh băm tệ, nhưng xác suất đó nhỏ và như nhau với mọi tập tên định danh cùng kích thước.

**Định nghĩa.** Gọi ℋ là một tập hữu hạn các hàm băm ánh xạ vũ trụ khoá U vào miền {0, 1, …, m − 1}. Tập như vậy gọi là **phổ quát** (universal) nếu với mỗi cặp khoá khác nhau k, l ∈ U, số hàm băm h ∈ ℋ có h(k) = h(l) không quá |ℋ|/m. Nói cách khác, với hàm băm chọn ngẫu nhiên từ ℋ, xác suất va chạm giữa hai khoá khác nhau k và l không quá xác suất 1/m của va chạm nếu h(k) và h(l) được chọn ngẫu nhiên, độc lập từ tập {0, 1, …, m − 1}.

Định lý sau cho thấy một lớp hàm băm phổ quát cho hành vi trung bình tốt. Nhắc lại n_i là độ dài danh sách T[i].

**Định lý 11.3.** Giả sử hàm băm h được chọn ngẫu nhiên từ một lớp hàm băm phổ quát và được dùng để băm n khoá vào bảng T cỡ m, giải quyết va chạm bằng nối chuỗi. Nếu khoá k không có trong bảng, độ dài kỳ vọng E[n_h(k)] của danh sách mà k băm vào không quá hệ số tải α = n/m. Nếu khoá k có trong bảng, độ dài kỳ vọng E[n_h(k)] của danh sách chứa k không quá 1 + α.

*Chứng minh.* Các kỳ vọng ở đây lấy theo lựa chọn hàm băm, không phụ thuộc bất kỳ giả định nào về phân phối khoá. Với mỗi cặp khoá khác nhau k và l, định nghĩa biến ngẫu nhiên chỉ thị X_kl = I{h(k) = h(l)}. Theo định nghĩa lớp phổ quát, một cặp khoá va chạm với xác suất không quá 1/m, tức Pr{h(k) = h(l)} ≤ 1/m. Theo Bổ đề 5.1, E[X_kl] ≤ 1/m.

Tiếp theo, với mỗi khoá k, định nghĩa biến ngẫu nhiên Y_k bằng số khoá **khác k** băm vào cùng ô với k:

```text
Y_k = Σ_{l ∈ T, l ≠ k} X_kl
```

Do đó

```text
E[Y_k] = E[ Σ_{l ∈ T, l ≠ k} X_kl ]
       = Σ_{l ∈ T, l ≠ k} E[X_kl]        (tính tuyến tính của kỳ vọng)
       ≤ Σ_{l ∈ T, l ≠ k} 1/m
```

Phần còn lại tuỳ theo k có trong bảng T hay không:

- Nếu k ∉ T thì n_h(k) = Y_k và |{l : l ∈ T và l ≠ k}| = n. Vậy E[n_h(k)] = E[Y_k] ≤ n/m = α.
- Nếu k ∈ T thì, vì k nằm trong danh sách T[h(k)] và Y_k không đếm k, ta có n_h(k) = Y_k + 1 và |{l : l ∈ T và l ≠ k}| = n − 1. Vậy E[n_h(k)] = E[Y_k] + 1 ≤ (n − 1)/m + 1 = 1 + α − 1/m < 1 + α. ∎

Hệ quả sau nói băm phổ quát cho đúng điều ta mong: đối thủ không còn có thể chọn một dãy phép toán ép ra thời gian xấu nhất. Bằng cách ngẫu nhiên hoá khéo léo lựa chọn hàm băm lúc chạy, ta bảo đảm xử lý được **mọi** dãy phép toán với thời gian trung bình tốt.

**Hệ quả 11.4.** Dùng băm phổ quát và giải quyết va chạm bằng nối chuỗi trên một bảng m ô ban đầu rỗng, xử lý bất kỳ dãy n phép toán INSERT, SEARCH, DELETE nào chứa O(m) phép INSERT tốn thời gian kỳ vọng Θ(n).

*Chứng minh.* Vì số lần chèn là O(m), ta có n = O(m) và do đó α = O(1). (Chính xác hơn — người tổng hợp: số khoá có trong bảng tại mọi thời điểm không vượt quá số lần INSERT, tức O(m), nên hệ số tải tại mọi thời điểm là O(1).) Các phép INSERT và DELETE tốn thời gian hằng số, và theo Định lý 11.3, thời gian kỳ vọng của mỗi phép SEARCH là O(1). Theo tính tuyến tính của kỳ vọng, thời gian kỳ vọng của cả dãy n phép toán là O(n). Vì mỗi phép toán tốn Ω(1), cận Θ(n) được suy ra. ∎

##### Thiết kế một lớp hàm băm phổ quát (Designing a universal class of hash functions)

Thiết kế một lớp hàm băm phổ quát khá dễ, như một chút lý thuyết số giúp ta chứng minh (Chương 31 có các kiến thức cần thiết).

Chọn một số nguyên tố p đủ lớn để mọi khoá có thể có k nằm trong khoảng 0 tới p − 1. Ký hiệu ℤ_p = {0, 1, …, p − 1} và ℤ*_p = {1, 2, …, p − 1}. Vì p nguyên tố, ta giải được các phương trình modulo p bằng các phương pháp của Chương 31. Vì giả định kích thước vũ trụ khoá lớn hơn số ô của bảng băm, ta có p > m.

Định nghĩa hàm băm h_ab với mọi a ∈ ℤ*_p và mọi b ∈ ℤ_p, dùng một phép biến đổi tuyến tính rồi rút gọn modulo p, sau đó modulo m:

```text
h_ab(k) = ((ak + b) mod p) mod m                                       (11.3)
```

Ví dụ, với p = 17 và m = 6: h₃,₄(8) = ((3 · 8 + 4) mod 17) mod 6 = (28 mod 17) mod 6 = 11 mod 6 = 5. Họ tất cả các hàm như vậy là

```text
ℋ_pm = { h_ab : a ∈ ℤ*_p và b ∈ ℤ_p }                                   (11.4)
```

Mỗi hàm h_ab ánh xạ ℤ_p vào ℤ_m. Lớp này có tính chất hay là kích thước m của miền giá trị tuỳ ý — không nhất thiết nguyên tố — điều sẽ dùng ở Mục 11.5. Vì có p − 1 cách chọn a và p cách chọn b, ℋ_pm chứa p(p − 1) hàm băm.

Bảng giá trị của h₃,₄ với p = 17, m = 6 (người tổng hợp tính):

| k | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| h₃,₄(k) | 4 | 1 | 4 | 1 | 4 | 2 | 5 | 2 | 5 | 2 | 0 | 3 | 0 | 3 | 0 | 3 | 1 |

**Định lý 11.5.** Lớp ℋ_pm các hàm băm định nghĩa bởi (11.3) và (11.4) là phổ quát.

*Chứng minh.* Xét hai khoá khác nhau k và l thuộc ℤ_p, k ≠ l. Với một hàm h_ab cho trước, đặt

```text
r = (ak + b) mod p
s = (al + b) mod p
```

**Bước 1: r ≠ s.** Ta có r − s ≡ a(k − l) (mod p). Vì p nguyên tố và cả a lẫn (k − l) đều khác 0 modulo p, tích của chúng cũng khác 0 modulo p (Định lý 31.6). Do đó khi tính bất kỳ h_ab ∈ ℋ_pm nào, hai đầu vào khác nhau k và l cho hai giá trị khác nhau r và s modulo p: ở "tầng mod p" chưa có va chạm nào.

**Bước 2: song ánh giữa (a, b) và (r, s).** Mỗi cặp (a, b) trong p(p − 1) cặp với a ≠ 0 cho một cặp (r, s) **khác nhau** với r ≠ s, vì ta giải ngược được a và b khi biết r và s:

```text
a = ((r − s)((k − l)⁻¹ mod p)) mod p
b = (r − ak) mod p
```

trong đó ((k − l)⁻¹ mod p) là nghịch đảo nhân duy nhất modulo p của k − l. Vì chỉ có p(p − 1) cặp (r, s) với r ≠ s, có tương ứng một-một giữa các cặp (a, b) với a ≠ 0 và các cặp (r, s) với r ≠ s. Vậy với mọi cặp đầu vào k và l cho trước, nếu chọn (a, b) ngẫu nhiên đều từ ℤ*_p × ℤ_p, cặp (r, s) thu được có xác suất như nhau là bất kỳ cặp giá trị khác nhau nào modulo p.

**Bước 3: đếm va chạm sau khi lấy mod m.** Do đó xác suất hai khoá khác nhau k và l va chạm bằng xác suất r ≡ s (mod m) khi r và s được chọn ngẫu nhiên là hai giá trị khác nhau modulo p. Với một giá trị r cho trước, trong p − 1 giá trị còn lại của s, số giá trị s với s ≠ r và s ≡ r (mod m) không quá

```text
⌈p/m⌉ − 1 ≤ ((p + m − 1)/m) − 1          (theo bất đẳng thức (3.6))
          = (p − 1)/m
```

Xác suất s va chạm với r khi rút gọn modulo m không quá ((p − 1)/m)/(p − 1) = 1/m. Vậy với mọi cặp giá trị khác nhau k, l ∈ ℤ_p,

```text
Pr{ h_ab(k) = h_ab(l) } ≤ 1/m
```

nên ℋ_pm đúng là phổ quát. ∎

**Kiểm tra bằng đếm (người tổng hợp), p = 7, m = 3:** ℋ₇,₃ có 6 · 7 = 42 hàm. Các số dư modulo 7 chia theo lớp modulo 3: {0, 3, 6}, {1, 4}, {2, 5}. Số cặp có thứ tự (r, s) với r ≠ s và r ≡ s (mod 3) là 3 · 2 + 2 · 1 + 2 · 1 = 10. Vì (r, s) phân bố đều trên 42 cặp khác nhau, mọi cặp khoá khác nhau va chạm dưới đúng 10 hàm (người tổng hợp đã đếm trực tiếp cho mọi cặp k, l), tức xác suất 10/42 ≈ 0,238 ≤ 1/3.

#### Ví dụ hôm nay

Năm 2011, các nhà nghiên cứu chỉ ra rằng có thể gửi tới máy chủ web một yêu cầu chứa hàng chục nghìn tham số có tên được chọn để cùng băm vào một ô trong bảng băm cố định của PHP, Java, Python..., làm một yêu cầu tốn hàng phút CPU (tấn công "HashDoS") — đúng kịch bản "đối thủ ác ý" của mục này. Biện pháp được các ngôn ngữ áp dụng sau đó là chọn ngẫu nhiên khoá bí mật cho hàm băm lúc khởi động tiến trình (ví dụ SipHash trong Python và Rust), tức tinh thần của băm phổ quát — theo hiểu biết của người tổng hợp. Hằng số 2654435769 (≈ 2³² · 0,618) của ví dụ phương pháp nhân vẫn xuất hiện trong nhiều mã nguồn với tên "Fibonacci hashing".

### 5. Địa chỉ mở (11.4 Open addressing, trang 269–277)

Trong **địa chỉ mở** (open addressing), mọi phần tử nằm ngay trong bảng băm. Tức là mỗi ô của bảng chứa hoặc một phần tử của tập động, hoặc NIL. Khi tìm một phần tử, ta xét các ô của bảng một cách có hệ thống cho tới khi tìm thấy phần tử cần tìm hoặc xác định chắc chắn rằng nó không có trong bảng. Khác với nối chuỗi, không có danh sách và không có phần tử nào nằm ngoài bảng. Do đó, với địa chỉ mở, bảng băm có thể "đầy" tới mức không chèn thêm được; một hệ quả là hệ số tải α không bao giờ vượt quá 1.

Dĩ nhiên có thể lưu các danh sách của nối chuỗi ngay trong bảng, trong các ô không dùng tới (Bài tập 11.2-4), nhưng ưu điểm của địa chỉ mở là tránh hoàn toàn con trỏ. Thay vì đi theo con trỏ, ta **tính** dãy các ô cần xét. Bộ nhớ dôi ra do không lưu con trỏ cho phép bảng có nhiều ô hơn với cùng lượng bộ nhớ, có thể làm ít va chạm hơn và truy xuất nhanh hơn.

Để chèn bằng địa chỉ mở, ta lần lượt xét, hay **dò** (probe), bảng băm cho tới khi gặp một ô rỗng để đặt khoá. Thay vì cố định thứ tự 0, 1, …, m − 1 (cách này tốn thời gian tìm kiếm Θ(n)), dãy vị trí được dò **phụ thuộc vào khoá đang được chèn**. Để xác định ô cần dò, ta mở rộng hàm băm, thêm số thứ tự lần dò (bắt đầu từ 0) làm đầu vào thứ hai. Hàm băm trở thành

```text
h : U × {0, 1, …, m − 1} → {0, 1, …, m − 1}
```

Với địa chỉ mở, ta đòi hỏi với mọi khoá k, **dãy dò** (probe sequence)

```text
⟨h(k, 0), h(k, 1), …, h(k, m − 1)⟩
```

là một hoán vị của ⟨0, 1, …, m − 1⟩, để mọi vị trí của bảng cuối cùng đều được xét như một ô cho khoá mới khi bảng đầy dần.

Trong pseudocode dưới đây, ta giả định các phần tử trong bảng T là khoá không kèm dữ liệu vệ tinh: khoá k đồng nhất với phần tử chứa khoá k. Mỗi ô chứa một khoá hoặc NIL (nếu ô rỗng). Thủ tục HASH-INSERT nhận bảng băm T và khoá k; nó trả về số thứ tự ô nơi lưu k, hoặc báo lỗi vì bảng đã đầy.

```text
HASH-INSERT(T, k)
1  i = 0
2  repeat
3      j = h(k, i)
4      if T[j] == NIL
5          T[j] = k
6          return j
7      else i = i + 1
8  until i == m
9  error "hash table overflow"
```

Giải thích: i đếm số lần dò đã thực hiện; dòng 3 tính ô thứ i của dãy dò; nếu ô rỗng thì đặt khoá và trả về ô đó (dòng 4–6); nếu không thì sang lần dò kế (dòng 7). Sau m lần dò mà không có ô rỗng thì bảng đầy (dòng 9: "tràn bảng băm").

Thuật toán tìm khoá k dò đúng dãy ô mà thuật toán chèn đã xét khi chèn k. Vì vậy tìm kiếm có thể kết thúc (thất bại) khi gặp một ô rỗng, vì k lẽ ra đã được chèn vào đó chứ không phải ở vị trí sau trong dãy dò. (Lập luận này giả định không có khoá nào bị xoá khỏi bảng.) Thủ tục HASH-SEARCH nhận bảng T và khoá k, trả về j nếu ô j chứa khoá k, hoặc NIL nếu k không có trong T.

```text
HASH-SEARCH(T, k)
1  i = 0
2  repeat
3      j = h(k, i)
4      if T[j] == k
5          return j
6      i = i + 1
7  until T[j] == NIL or i == m
8  return NIL
```

**Xoá.** Xoá khỏi bảng địa chỉ mở là khó. Khi xoá một khoá khỏi ô i, ta không thể đơn giản đánh dấu ô đó rỗng bằng cách ghi NIL. Nếu làm vậy, có thể không tìm lại được một khoá k nào đó mà trong lúc chèn k ta đã dò qua ô i và thấy nó bị chiếm. Có thể giải quyết bằng cách đánh dấu ô, ghi vào đó giá trị đặc biệt **DELETED** thay cho NIL. Khi đó sửa HASH-INSERT để coi ô như vậy là rỗng, nhờ đó chèn được khoá mới vào. Không cần sửa HASH-SEARCH, vì nó sẽ đi qua các giá trị DELETED khi tìm kiếm. Tuy nhiên khi dùng giá trị DELETED, thời gian tìm kiếm không còn phụ thuộc vào hệ số tải α, và vì lý do này nối chuỗi thường được chọn làm kỹ thuật giải quyết va chạm khi phải xoá khoá.

Ví dụ (người tổng hợp): m = 11, dò tuyến tính với h′(k) = k. Chèn 4 (ô 4), rồi 15 (ô 4 bị chiếm, vào ô 5). Nếu xoá 4 bằng cách ghi T[4] = NIL, thì HASH-SEARCH(T, 15) dò ô 4, thấy NIL và dừng, trả về NIL — sai. Nếu ghi T[4] = DELETED, tìm kiếm dò ô 4 (DELETED ≠ 15 và ≠ NIL), đi tiếp sang ô 5 và tìm thấy 15. Nhưng nếu chèn rồi xoá nhiều lần, bảng đầy dần các ô DELETED: số khoá thực n nhỏ (α nhỏ) mà tìm kiếm thất bại vẫn phải dò rất nhiều ô — đó là ý "thời gian tìm không còn phụ thuộc α".

**Giả định băm đều.** Trong phân tích, ta giả định **băm đều** (uniform hashing): dãy dò của mỗi khoá có xác suất như nhau là bất kỳ hoán vị nào trong m! hoán vị của ⟨0, 1, …, m − 1⟩. Băm đều mở rộng khái niệm băm đều đơn giản ở trên cho hàm băm sinh ra không chỉ một số mà cả một dãy dò. Băm đều thực sự khó cài đặt, và trong thực tế người ta dùng các xấp xỉ phù hợp (như băm kép, định nghĩa dưới đây).

Ta xét ba kỹ thuật thường dùng để tính dãy dò cho địa chỉ mở: dò tuyến tính, dò bậc hai và băm kép. Các kỹ thuật này đều bảo đảm ⟨h(k, 0), …, h(k, m − 1)⟩ là hoán vị của ⟨0, …, m − 1⟩ với mỗi khoá k (với tham số chọn đúng, xem khối Lưu ý). Tuy nhiên không kỹ thuật nào thoả giả định băm đều, vì không kỹ thuật nào sinh được quá m² dãy dò khác nhau (thay vì m! mà băm đều đòi hỏi). Băm kép có nhiều dãy dò nhất và, như có thể đoán, cho kết quả tốt nhất. (So sánh của người tổng hợp: m = 11 thì m! = 39.916.800 trong khi m² = 121.)

#### Dò tuyến tính (Linear probing)

Cho một hàm băm thông thường h′ : U → {0, 1, …, m − 1}, gọi là **hàm băm phụ** (auxiliary hash function), phương pháp **dò tuyến tính** (linear probing) dùng hàm băm

```text
h(k, i) = (h′(k) + i) mod m
```

với i = 0, 1, …, m − 1. Cho khoá k, ta dò T[h′(k)] trước, tức ô do hàm băm phụ cho. Tiếp theo dò ô T[h′(k) + 1], cứ thế tới ô T[m − 1]. Rồi vòng lại các ô T[0], T[1], … cho tới khi cuối cùng dò ô T[h′(k) − 1]. Vì lần dò đầu tiên quyết định toàn bộ dãy dò, chỉ có m dãy dò khác nhau.

Dò tuyến tính dễ cài đặt, nhưng mắc vấn đề gọi là **tụ cụm sơ cấp** (primary clustering): các đoạn dài ô liên tiếp bị chiếm hình thành, làm tăng thời gian tìm kiếm trung bình. Cụm hình thành vì một ô rỗng đứng sau i ô đầy sẽ được lấp ở lần chèn kế tiếp với xác suất (i + 1)/m (khoá mới có ô đầu là bất kỳ ô nào trong i ô đầy đó hoặc chính ô rỗng đều rơi vào ô rỗng này). Đoạn ô bị chiếm càng dài càng có xu hướng dài thêm, và thời gian tìm trung bình tăng.

#### Dò bậc hai (Quadratic probing)

**Dò bậc hai** (quadratic probing) dùng hàm băm dạng

```text
h(k, i) = (h′(k) + c₁i + c₂i²) mod m                                   (11.5)
```

trong đó h′ là hàm băm phụ, c₁ và c₂ là các hằng số phụ dương, và i = 0, 1, …, m − 1. Vị trí dò đầu tiên là T[h′(k)]; các vị trí sau được dịch đi những khoảng phụ thuộc bậc hai vào số thứ tự lần dò i. Phương pháp này tốt hơn nhiều so với dò tuyến tính, nhưng để dùng hết bảng, các giá trị c₁, c₂ và m bị ràng buộc; Bài toán 11-3 chỉ một cách chọn. Ngoài ra, nếu hai khoá có cùng vị trí dò đầu tiên thì dãy dò của chúng giống nhau, vì h(k₁, 0) = h(k₂, 0) kéo theo h(k₁, i) = h(k₂, i). Tính chất này dẫn tới một dạng tụ cụm nhẹ hơn, gọi là **tụ cụm thứ cấp** (secondary clustering). Như dò tuyến tính, lần dò đầu quyết định cả dãy, nên chỉ có m dãy dò khác nhau được dùng.

Ví dụ ràng buộc (người tổng hợp, dữ liệu Bài tập 11.4-1): m = 11, c₁ = 1, c₂ = 3, h′(k) = k. Dãy dò của khoá có ô đầu 0 là 0, 4, 3, 8, 8, 3, 4, 0, 2, … — lặp lại các ô cũ, không phải hoán vị của 0..10 (chẳng hạn ô 1 không bao giờ được dò trong 11 lần dò). Đây là lý do phải chọn tham số cẩn thận.

#### Băm kép (Double hashing)

Băm kép là một trong những phương pháp tốt nhất cho địa chỉ mở, vì các hoán vị nó sinh ra có nhiều đặc điểm của hoán vị chọn ngẫu nhiên. **Băm kép** (double hashing) dùng hàm băm dạng

```text
h(k, i) = (h₁(k) + i·h₂(k)) mod m
```

trong đó h₁ và h₂ đều là hàm băm phụ. Lần dò đầu tiên vào vị trí T[h₁(k)]; các lần dò tiếp theo dịch so với vị trí trước một khoảng h₂(k), modulo m. Như vậy, khác với dò tuyến tính hay bậc hai, dãy dò ở đây phụ thuộc vào khoá k theo hai cách, vì vị trí dò đầu, bước nhảy, hoặc cả hai đều có thể thay đổi.

**Ví dụ chèn bằng băm kép (Hình 11.5 của sách):** bảng cỡ 13, h₁(k) = k mod 13, h₂(k) = 1 + (k mod 11). Trạng thái bảng trước khi chèn 14:

| Ô | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Khoá | – | 79 | – | – | 69 | 98 | – | 72 | – | – | – | 50 | – |

Chèn khoá 14: vì 14 ≡ 1 (mod 13) và 14 ≡ 3 (mod 11), ta có h₁(14) = 1, h₂(14) = 1 + 3 = 4. Dãy dò: ô 1 (bị 79 chiếm), ô 1 + 4 = 5 (bị 98 chiếm), ô 1 + 8 = 9 (rỗng) — khoá 14 được chèn vào ô 9, sau khi xét các ô 1 và 5. Trong hình, hai mũi tên cong vẽ hai bước nhảy 1 → 5 và 5 → 9.

Kiểm tra các khoá có sẵn (người tổng hợp): 79 mod 13 = 1, 69 mod 13 = 4, 72 mod 13 = 7, 50 mod 13 = 11 — đều nằm ở ô đầu của mình. Còn 98 mod 13 = 7 nhưng 98 nằm ở ô 5: nếu 72 đã chiếm ô 7 khi 98 được chèn, thì h₂(98) = 1 + (98 mod 11) = 1 + 10 = 11, lần dò thứ hai vào (7 + 11) mod 13 = 5 — khớp với hình.

**Điều kiện để dò hết bảng.** Giá trị h₂(k) phải nguyên tố cùng nhau với kích thước bảng m thì mới tìm khắp bảng được (Bài tập 11.4-4). Một cách tiện để bảo đảm điều này là cho m là luỹ thừa của 2 và thiết kế h₂ luôn cho số lẻ. Cách khác là cho m nguyên tố và thiết kế h₂ luôn trả về số nguyên dương nhỏ hơn m. Ví dụ, chọn m nguyên tố và

```text
h₁(k) = k mod m
h₂(k) = 1 + (k mod m′)
```

với m′ hơi nhỏ hơn m (chẳng hạn m − 1). Ví dụ k = 123456, m = 701, m′ = 700: h₁(k) = 80 (123456 = 176 · 701 + 80) và h₂(k) = 1 + 256 = 257 (123456 = 176 · 700 + 256). Vậy ta dò ô 80 trước, rồi xét cứ mỗi ô thứ 257 (modulo m) cho tới khi tìm thấy khoá hoặc đã xét mọi ô. (Người tổng hợp: ba lần dò đầu là 80, 337, 594; lần thứ tư là 851 mod 701 = 150.)

Khi m nguyên tố hoặc là luỹ thừa của 2, băm kép tốt hơn dò tuyến tính và dò bậc hai ở chỗ dùng Θ(m²) dãy dò thay vì Θ(m), vì mỗi cặp (h₁(k), h₂(k)) có thể có cho một dãy dò khác nhau. Do đó, với các giá trị m như vậy, hiệu năng của băm kép có vẻ rất gần với hiệu năng của sơ đồ "lý tưởng" băm đều.

Về nguyên tắc có thể dùng giá trị m không phải số nguyên tố hay luỹ thừa của 2 với băm kép, nhưng trong thực tế sẽ khó sinh h₂(k) hiệu quả mà vẫn bảo đảm nguyên tố cùng nhau với m, một phần vì mật độ tương đối φ(m)/m của các số như vậy có thể nhỏ (công thức (31.24); φ là hàm phi Euler, đếm số nguyên trong 1..m nguyên tố cùng nhau với m). Ví dụ người tổng hợp: m = 30 thì φ(30) = 8, chỉ 8/30 ≈ 27% bước nhảy hợp lệ.

#### Phân tích băm địa chỉ mở (Analysis of open-address hashing)

Như với nối chuỗi, ta phân tích địa chỉ mở theo hệ số tải α = n/m. Dĩ nhiên với địa chỉ mở, mỗi ô chứa nhiều nhất một phần tử, nên n ≤ m, tức α ≤ 1.

Ta giả định dùng băm đều. Trong sơ đồ lý tưởng này, dãy dò ⟨h(k, 0), h(k, 1), …, h(k, m − 1)⟩ dùng để chèn hay tìm mỗi khoá k có xác suất như nhau là bất kỳ hoán vị nào của ⟨0, 1, …, m − 1⟩. Dĩ nhiên mỗi khoá cụ thể có một dãy dò cố định duy nhất; ý ở đây là, xét phân phối xác suất trên không gian khoá và cách hàm băm tác động lên khoá, mỗi dãy dò có thể có đều đồng khả năng.

Ta phân tích số lần dò kỳ vọng của băm địa chỉ mở dưới giả định băm đều, bắt đầu với số lần dò trong một lần tìm kiếm thất bại.

**Định lý 11.6.** Cho bảng băm địa chỉ mở với hệ số tải α = n/m < 1, số lần dò kỳ vọng trong một lần tìm kiếm thất bại không quá 1/(1 − α), giả định băm đều.

*Chứng minh.* Trong một lần tìm kiếm thất bại, mọi lần dò trừ lần cuối đều truy cập một ô bị chiếm không chứa khoá cần tìm, và ô dò cuối cùng là ô rỗng. Định nghĩa biến ngẫu nhiên X là số lần dò trong một lần tìm kiếm thất bại, và định nghĩa sự kiện A_i, với i = 1, 2, …, là sự kiện "có lần dò thứ i và nó rơi vào một ô bị chiếm". Khi đó sự kiện {X ≥ i} là giao của các sự kiện A₁ ∩ A₂ ∩ ⋯ ∩ A_{i−1}. Ta chặn Pr{X ≥ i} bằng cách chặn Pr{A₁ ∩ A₂ ∩ ⋯ ∩ A_{i−1}}. Theo Bài tập C.2-5 (quy tắc nhân của xác suất có điều kiện),

```text
Pr{A₁ ∩ A₂ ∩ ⋯ ∩ A_{i−1}} = Pr{A₁} · Pr{A₂ | A₁} · Pr{A₃ | A₁ ∩ A₂} ⋯
                             Pr{A_{i−1} | A₁ ∩ A₂ ∩ ⋯ ∩ A_{i−2}}
```

Vì có n phần tử và m ô, Pr{A₁} = n/m. Với j > 1, xác suất có lần dò thứ j và nó rơi vào ô bị chiếm, biết j − 1 lần dò đầu đều rơi vào ô bị chiếm, là (n − j + 1)/(m − j + 1). Xác suất này đúng vì ta đang tìm một trong (n − (j − 1)) phần tử còn lại trong (m − (j − 1)) ô chưa xét, và theo giả định băm đều, xác suất là tỷ số của hai đại lượng này. Nhận xét rằng n < m kéo theo (n − j)/(m − j) ≤ n/m với mọi j thoả 0 ≤ j < m, ta có với mọi i thoả 1 ≤ i ≤ m,

```text
Pr{X ≥ i} = (n/m) · ((n − 1)/(m − 1)) · ((n − 2)/(m − 2)) ⋯ ((n − i + 2)/(m − i + 2))
          ≤ (n/m)^(i−1)
          = α^(i−1)
```

Dùng công thức (C.25) (với biến ngẫu nhiên nhận giá trị nguyên không âm, E[X] = Σᵢ₌₁^∞ Pr{X ≥ i}) để chặn số lần dò kỳ vọng:

```text
E[X] = Σᵢ₌₁^∞ Pr{X ≥ i}
     ≤ Σᵢ₌₁^∞ α^(i−1)
     = Σᵢ₌₀^∞ α^i
     = 1/(1 − α)
```

∎

Cận 1/(1 − α) = 1 + α + α² + α³ + ⋯ có cách hiểu trực giác. Ta luôn thực hiện lần dò thứ nhất. Với xác suất xấp xỉ α, lần dò thứ nhất gặp ô bị chiếm, nên cần dò lần thứ hai. Với xác suất xấp xỉ α², hai ô đầu đều bị chiếm nên dò lần thứ ba, và cứ thế.

Nếu α là hằng số, Định lý 11.6 dự đoán tìm kiếm thất bại chạy O(1). Ví dụ, bảng đầy một nửa thì số lần dò trung bình trong tìm kiếm thất bại không quá 1/(1 − 0,5) = 2. Đầy 90% thì không quá 1/(1 − 0,9) = 10.

Kiểm tra (người tổng hợp), m = 2, n = 1: lần dò đầu gặp ô bị chiếm với xác suất 1/2, khi đó lần dò thứ hai chắc chắn gặp ô rỗng. E[X] = 1 + 1/2 = 1,5 ≤ 1/(1 − 1/2) = 2. (Giá trị đúng dưới băm đều là (m + 1)/(m − n + 1) = 3/2.)

Định lý 11.6 cho ngay hiệu năng của HASH-INSERT.

**Hệ quả 11.7.** Chèn một phần tử vào bảng băm địa chỉ mở có hệ số tải α cần trung bình không quá 1/(1 − α) lần dò, giả định băm đều.

*Chứng minh.* Một phần tử chỉ được chèn nếu bảng còn chỗ, nên α < 1. Chèn một khoá cần một lần tìm kiếm thất bại, rồi đặt khoá vào ô rỗng đầu tiên tìm được. Vậy số lần dò kỳ vọng không quá 1/(1 − α). ∎

Cần thêm chút công để tính số lần dò kỳ vọng cho tìm kiếm thành công.

**Định lý 11.8.** Cho bảng băm địa chỉ mở với hệ số tải α < 1, số lần dò kỳ vọng trong một lần tìm kiếm thành công không quá

```text
(1/α) ln (1/(1 − α))
```

giả định băm đều và giả định mỗi khoá trong bảng có xác suất như nhau được tìm.

*Chứng minh.* Tìm khoá k lặp lại đúng dãy dò như khi chèn phần tử có khoá k. Theo Hệ quả 11.7, nếu k là khoá thứ (i + 1) được chèn vào bảng (lúc đó bảng có i khoá, hệ số tải i/m), số lần dò kỳ vọng khi tìm k không quá 1/(1 − i/m) = m/(m − i). Lấy trung bình trên cả n khoá trong bảng cho số lần dò kỳ vọng của một lần tìm thành công:

```text
(1/n) Σᵢ₌₀ⁿ⁻¹ m/(m − i) = (m/n) Σᵢ₌₀ⁿ⁻¹ 1/(m − i)
                        = (1/α) Σ_{k=m−n+1}^{m} 1/k
                        ≤ (1/α) ∫_{m−n}^{m} (1/x) dx       (theo bất đẳng thức (A.12))
                        = (1/α) ln (m/(m − n))
                        = (1/α) ln (1/(1 − α))
```

∎

Giải thích bước thứ hai: đặt k = m − i, khi i chạy từ 0 tới n − 1 thì k chạy từ m xuống m − n + 1. Bước thứ ba: tổng của hàm giảm 1/k trên k = m − n + 1..m được chặn trên bởi tích phân của 1/x từ m − n tới m (mỗi số hạng 1/k ≤ ∫_{k−1}^{k} dx/x).

Nếu bảng đầy một nửa, số lần dò kỳ vọng khi tìm thành công nhỏ hơn 1,387. Nếu đầy 90%, nhỏ hơn 2,559.

Bảng so sánh (người tổng hợp tính; hai cột cuối là cận trên dưới giả định băm đều):

| α | Tìm thất bại / chèn ≤ 1/(1 − α) | Tìm thành công ≤ (1/α) ln(1/(1 − α)) |
|---|---|---|
| 0,5 | 2 | 1,386 |
| 0,75 | 4 | 1,848 |
| 0,875 | 8 | 2,377 |
| 0,9 | 10 | 2,558 |
| 0,99 | 100 | 4,652 |

Nhận xét: tìm thành công rẻ hơn nhiều so với tìm thất bại, vì phần lớn khoá được chèn khi bảng còn vơi. Nhưng khi α → 1, tìm thất bại và chèn bùng nổ; đây là lý do thực tế giữ α dưới khoảng 0,7–0,9.

#### Ví dụ hôm nay

`dict` của Python dùng địa chỉ mở với dãy dò giả ngẫu nhiên (kết hợp bit cao của giá trị băm vào bước nhảy, gần với tinh thần băm kép) và tự mở rộng bảng khi đầy khoảng 2/3; bảng băm "SwissTable" của Google (Abseil) và `HashMap` của Rust dùng địa chỉ mở với dò theo nhóm 16 ô, tận dụng lệnh SIMD — theo hiểu biết của người tổng hợp. Chúng chọn địa chỉ mở chính vì lý do sách nêu: không có con trỏ, các ô nằm liền nhau, tốt cho bộ nhớ đệm. Việc xoá trong các cài đặt này dùng đúng dấu "đã xoá" (tombstone) như giá trị DELETED, và bảng được dựng lại định kỳ để dọn các dấu này.

### 6. Băm hoàn hảo (★ 11.5 Perfect hashing, trang 277–282)

Băm thường là lựa chọn tốt vì hiệu năng trung bình xuất sắc, nhưng băm cũng có thể cho hiệu năng **xấu nhất** xuất sắc khi tập khoá là **tĩnh** (static): khi các khoá đã được lưu vào bảng, tập khoá không bao giờ thay đổi. Một số ứng dụng tự nhiên có tập khoá tĩnh: tập từ khoá dành riêng (reserved words) của một ngôn ngữ lập trình, hay tập tên tệp trên một đĩa CD-ROM. Ta gọi một kỹ thuật băm là **băm hoàn hảo** (perfect hashing) nếu cần O(1) lần truy cập bộ nhớ để thực hiện một lần tìm kiếm trong trường hợp xấu nhất.

Để tạo sơ đồ băm hoàn hảo, ta dùng **hai tầng băm**, mỗi tầng dùng băm phổ quát.

- **Tầng thứ nhất** về cơ bản giống băm nối chuỗi: băm n khoá vào m ô bằng một hàm băm h chọn cẩn thận từ một họ hàm băm phổ quát.
- **Tầng thứ hai:** thay vì lập danh sách liên kết các khoá băm vào ô j, ta dùng một **bảng băm phụ** (secondary hash table) nhỏ S_j với hàm băm h_j đi kèm. Bằng cách chọn các hàm h_j cẩn thận, ta bảo đảm không có va chạm ở tầng thứ hai.

Để bảo đảm không va chạm ở tầng thứ hai, ta cần cho kích thước m_j của bảng S_j bằng **bình phương** số khoá n_j băm vào ô j. Dù sự phụ thuộc bậc hai của m_j vào n_j có vẻ dễ làm tổng bộ nhớ quá lớn, ta sẽ chứng minh rằng chọn tốt hàm băm tầng một thì tổng bộ nhớ kỳ vọng chỉ là O(n).

Ta dùng hàm băm chọn từ các lớp phổ quát của Mục 11.3.3. Hàm tầng một lấy từ lớp ℋ_pm, với p là số nguyên tố lớn hơn mọi giá trị khoá như ở Mục 11.3.3. Các khoá băm vào ô j được băm lại vào bảng phụ S_j cỡ m_j bằng hàm h_j chọn từ lớp ℋ_{p,m_j}. (Chú thích của sách: khi n_j = m_j = 1, thực ra không cần hàm băm cho ô j; khi chọn hàm h_ab(k) = ((ak + b) mod p) mod m_j cho ô như vậy, ta chỉ việc dùng a = b = 0.)

**Ví dụ của sách (Hình 11.6):** lưu tập K = {10, 22, 37, 40, 52, 60, 70, 72, 75}. Hàm băm ngoài là h(k) = ((ak + b) mod p) mod m với a = 3, b = 42, p = 101, m = 9. Ví dụ h(75) = ((225 + 42) mod 101) mod 9 = (267 mod 101) mod 9 = 65 mod 9 = 2, nên khoá 75 băm vào ô 2 của bảng T. Bảng phụ S_j chứa mọi khoá băm vào ô j; kích thước S_j là m_j = n_j², và hàm băm đi kèm là h_j(k) = ((a_j k + b_j) mod p) mod m_j. Vì h₂(75) = ((750 + 18) mod 101) mod 9 = (768 mod 101) mod 9 = 61 mod 9 = 7, khoá 75 được lưu ở ô 7 của bảng phụ S₂. Không có va chạm trong bảng phụ nào, nên tìm kiếm tốn thời gian hằng số trong trường hợp xấu nhất.

Nội dung Hình 11.6 vẽ lại thành bảng (mỗi ô j không rỗng của T trỏ tới một bản ghi lưu m_j, a_j, b_j rồi tới bảng S_j):

| Ô j của T | Khoá băm vào j | n_j | m_j | a_j | b_j | Nội dung S_j (ô: khoá) |
|---|---|---|---|---|---|---|
| 0 | 10 | 1 | 1 | 0 | 0 | 0: 10 |
| 1 | — | 0 | — | — | — | (T[1] = NIL) |
| 2 | 60, 72, 75 | 3 | 9 | 10 | 18 | 3: 60; 4: 72; 7: 75 (các ô khác rỗng) |
| 3, 4 | — | 0 | — | — | — | NIL |
| 5 | 70 | 1 | 1 | 0 | 0 | 0: 70 |
| 6 | — | 0 | — | — | — | NIL |
| 7 | 22, 37, 40, 52 | 4 | 16 | 23 | 88 | 3: 40 (hình in ở ô 7 — xem dưới); 8: 52; 9: 22; 14: 37 |
| 8 | — | 0 | — | — | — | NIL |

Người tổng hợp tính lại từng giá trị:

```text
Tầng một, h(k) = ((3k + 42) mod 101) mod 9:
  h(10) = (72 mod 101) mod 9  = 72 mod 9 = 0
  h(22) = (108 mod 101) mod 9 =  7 mod 9 = 7
  h(37) = (153 mod 101) mod 9 = 52 mod 9 = 7
  h(40) = (162 mod 101) mod 9 = 61 mod 9 = 7
  h(52) = (198 mod 101) mod 9 = 97 mod 9 = 7
  h(60) = (222 mod 101) mod 9 = 20 mod 9 = 2
  h(70) = (252 mod 101) mod 9 = 50 mod 9 = 5
  h(72) = (258 mod 101) mod 9 = 56 mod 9 = 2
  h(75) = (267 mod 101) mod 9 = 65 mod 9 = 2
Tầng hai ở S₂, h₂(k) = ((10k + 18) mod 101) mod 9:
  h₂(60) = (618 mod 101) mod 9 = 12 mod 9 = 3
  h₂(72) = (738 mod 101) mod 9 = 31 mod 9 = 4
  h₂(75) = (768 mod 101) mod 9 = 61 mod 9 = 7
Tầng hai ở S₇, h₇(k) = ((23k + 88) mod 101) mod 16:
  h₇(22) = (594 mod 101)  mod 16 = 89 mod 16 = 9
  h₇(37) = (939 mod 101)  mod 16 = 30 mod 16 = 14
  h₇(40) = (1008 mod 101) mod 16 = 99 mod 16 = 3     ◀ hình in ô 7
  h₇(52) = (1284 mod 101) mod 16 = 72 mod 16 = 8
```

Hình in khoá 40 ở ô 7 của S₇, nhưng theo đúng các tham số đã cho, khoá 40 phải ở ô 3. Dù vậy, bốn khoá vẫn rơi vào bốn ô khác nhau (3, 8, 9, 14), nên kết luận "không có va chạm" không đổi.

Tìm kiếm một khoá, ví dụ 52: tính h(52) = 7; đọc m₇ = 16, a₇ = 23, b₇ = 88; tính h₇(52) = 8; so sánh S₇[8] với 52 — khớp. Tìm 41 (không có): h(41) = (165 mod 101) mod 9 = 64 mod 9 = 1; T[1] = NIL nên báo thất bại ngay. Mọi lần tìm chỉ cần hai lần tính hàm băm và một số hằng lần truy cập bộ nhớ.

Ta tiến hành hai bước. Thứ nhất, xác định cách bảo đảm các bảng phụ không có va chạm. Thứ hai, chứng minh tổng bộ nhớ kỳ vọng — cho bảng chính và mọi bảng phụ — là O(n).

**Định lý 11.9.** Giả sử ta lưu n khoá vào bảng băm cỡ m = n² bằng một hàm băm h chọn ngẫu nhiên từ một lớp hàm băm phổ quát. Khi đó xác suất có bất kỳ va chạm nào nhỏ hơn 1/2.

*Chứng minh.* Có C(n, 2) cặp khoá có thể va chạm; mỗi cặp va chạm với xác suất 1/m nếu h được chọn ngẫu nhiên từ họ phổ quát ℋ. (Chính xác: không quá 1/m.) Gọi X là biến ngẫu nhiên đếm số va chạm. Khi m = n², số va chạm kỳ vọng là

```text
E[X] = C(n, 2) · 1/n²
     = ((n² − n)/2) · 1/n²
     < 1/2
```

(Phân tích này giống phân tích nghịch lý ngày sinh ở Mục 5.4.1.) Áp dụng bất đẳng thức Markov (C.30), Pr{X ≥ t} ≤ E[X]/t, với t = 1, ta có Pr{X ≥ 1} < 1/2. ∎

Trong tình huống của Định lý 11.9 (m = n²), một hàm băm h chọn ngẫu nhiên từ ℋ có nhiều khả năng **không** có va chạm nào hơn là có. Với tập K gồm n khoá cần băm (nhớ rằng K tĩnh), vì vậy dễ tìm được hàm băm không va chạm sau vài lần thử ngẫu nhiên. (Người tổng hợp: mỗi lần thử thành công với xác suất > 1/2, nên số lần thử kỳ vọng < 2, và xác suất thất bại t lần liên tiếp < 2^(−t).)

Ví dụ (người tổng hợp): n = 4, m = 16: E[X] = 6/16 = 0,375 < 1/2. Áp dụng cho S₇ trong Hình 11.6: bốn khoá vào bảng 16 ô.

Tuy nhiên khi n lớn, bảng cỡ m = n² là quá lớn. Vì vậy ta dùng cách băm hai tầng, và chỉ dùng cách của Định lý 11.9 để băm các phần tử **trong từng ô**. Dùng một hàm băm ngoài, hay tầng một, h để băm các khoá vào m = n ô. Rồi nếu n_j khoá băm vào ô j, dùng bảng phụ S_j cỡ m_j = n_j² để tra cứu hằng thời gian không va chạm.

Giờ ta chuyển sang vấn đề bảo đảm tổng bộ nhớ là O(n). Vì kích thước m_j của bảng phụ thứ j tăng theo bình phương số khoá n_j được lưu, có nguy cơ tổng bộ nhớ quá lớn.

Nếu bảng tầng một có cỡ m = n, thì bộ nhớ dùng là O(n) cho bảng chính, cho việc lưu các kích thước m_j của bảng phụ, và cho việc lưu các tham số a_j, b_j xác định các hàm băm phụ h_j chọn từ lớp ℋ_{p,m_j} của Mục 11.3.3 (trừ khi n_j = 1 và dùng a = b = 0). Định lý và hệ quả sau chặn tổng kích thước kỳ vọng của mọi bảng phụ. Hệ quả thứ hai chặn xác suất tổng kích thước các bảng phụ là siêu tuyến tính (thực ra là xác suất nó bằng hoặc vượt 4n).

**Định lý 11.10.** Giả sử ta lưu n khoá vào bảng băm cỡ m = n bằng một hàm băm h chọn ngẫu nhiên từ một lớp hàm băm phổ quát. Khi đó

```text
E[ Σⱼ₌₀^{m−1} n_j² ] < 2n
```

với n_j là số khoá băm vào ô j.

*Chứng minh.* Bắt đầu với đẳng thức sau, đúng với mọi số nguyên không âm a:

```text
a² = a + 2·C(a, 2)                                                      (11.6)
```

(Kiểm tra: a + 2 · a(a − 1)/2 = a + a² − a = a². Ví dụ a = 4: 4 + 2 · 6 = 16.) Ta có

```text
E[ Σⱼ n_j² ] = E[ Σⱼ ( n_j + 2·C(n_j, 2) ) ]                  (theo (11.6))
             = E[ Σⱼ n_j ] + 2·E[ Σⱼ C(n_j, 2) ]              (tính tuyến tính của kỳ vọng)
             = E[n] + 2·E[ Σⱼ C(n_j, 2) ]                     (theo (11.1))
             = n + 2·E[ Σⱼ C(n_j, 2) ]                        (vì n không phải biến ngẫu nhiên)
```

(các tổng đều chạy j = 0..m − 1). Để tính tổng Σⱼ C(n_j, 2), nhận xét rằng nó chính là tổng số cặp khoá trong bảng va chạm nhau. Theo tính chất của băm phổ quát, giá trị kỳ vọng của tổng này không quá

```text
C(n, 2) · 1/m = n(n − 1)/(2m)
              = (n − 1)/2
```

vì m = n. Vậy

```text
E[ Σⱼ n_j² ] ≤ n + 2·(n − 1)/2
             = 2n − 1
             < 2n
```

∎

**Hệ quả 11.11.** Giả sử ta lưu n khoá vào bảng băm cỡ m = n bằng một hàm băm h chọn ngẫu nhiên từ một lớp hàm băm phổ quát, và đặt kích thước mỗi bảng phụ là m_j = n_j² với j = 0, 1, …, m − 1. Khi đó lượng bộ nhớ kỳ vọng cần cho mọi bảng phụ trong sơ đồ băm hoàn hảo nhỏ hơn 2n.

*Chứng minh.* Vì m_j = n_j² với j = 0, 1, …, m − 1, Định lý 11.10 cho

```text
E[ Σⱼ₌₀^{m−1} m_j ] = E[ Σⱼ₌₀^{m−1} n_j² ] < 2n                            (11.7)
```

∎

**Hệ quả 11.12.** Giả sử ta lưu n khoá vào bảng băm cỡ m = n bằng một hàm băm h chọn ngẫu nhiên từ một lớp hàm băm phổ quát, và đặt kích thước mỗi bảng phụ là m_j = n_j² với j = 0, 1, …, m − 1. Khi đó xác suất tổng bộ nhớ dùng cho các bảng phụ bằng hoặc vượt 4n nhỏ hơn 1/2.

*Chứng minh.* Lại áp dụng bất đẳng thức Markov (C.30), Pr{X ≥ t} ≤ E[X]/t, lần này cho bất đẳng thức (11.7), với X = Σⱼ₌₀^{m−1} m_j và t = 4n:

```text
Pr{ Σⱼ m_j ≥ 4n } ≤ E[ Σⱼ m_j ] / (4n)
                  < 2n/(4n)
                  = 1/2
```

∎

Từ Hệ quả 11.12, nếu thử vài hàm băm chọn ngẫu nhiên từ họ phổ quát, ta sẽ nhanh chóng tìm được một hàm dùng lượng bộ nhớ hợp lý.

**Áp vào ví dụ Hình 11.6 (người tổng hợp):** n = 9, các n_j khác 0 là 1, 3, 1, 4. Σ n_j² = 1 + 9 + 1 + 16 = 27; số cặp va chạm ở tầng một là C(3, 2) + C(4, 2) = 3 + 6 = 9, và 27 = 9 + 2 · 9 đúng theo (11.6). Giá trị 27 lớn hơn kỳ vọng tối đa 2n − 1 = 17 của Định lý 11.10, nhưng vẫn dưới ngưỡng 4n = 36 của Hệ quả 11.12 — một hàm tầng một "hơi xui" nhưng chấp nhận được. Tổng bộ nhớ: 9 ô của T, bốn bộ ba (m_j, a_j, b_j), và 27 ô bảng phụ.

**Thuật toán dựng bảng (người tổng hợp tóm lại từ lập luận của sách):**

```text
Dựng bảng băm hoàn hảo cho tập tĩnh K, |K| = n:
1  lặp: chọn ngẫu nhiên h ∈ ℋ_{p,n}; tính n_j cho mọi ô j
   cho tới khi Σ n_j² < 4n                    (mỗi lần thử thành công với xác suất > 1/2)
2  với mỗi ô j có n_j ≥ 1:
       m_j = n_j²
       lặp: chọn ngẫu nhiên h_j ∈ ℋ_{p,m_j}
       cho tới khi các khoá của ô j rơi vào các ô khác nhau của S_j
                                               (mỗi lần thử thành công với xác suất > 1/2)
3  tìm kiếm k: j = h(k); nếu n_j = 0 thì thất bại;
   ngược lại so sánh S_j[h_j(k)] với k
```

Thời gian dựng kỳ vọng O(n); bộ nhớ O(n); tìm kiếm O(1) xấu nhất.

#### Ví dụ hôm nay

Ý tưởng "tập tĩnh, đầu tư lúc dựng để tra cứu xấu nhất O(1)" là cơ sở của công cụ `gperf` sinh hàm băm hoàn hảo cho bảng từ khoá của trình biên dịch, và của các cấu trúc băm hoàn hảo tối thiểu (minimal perfect hashing, dùng đúng n ô) trong chỉ mục cơ sở dữ liệu, bộ định tuyến mạng và công cụ tin sinh học — theo hiểu biết của người tổng hợp. Các phương pháp hiện đại (CHD, RecSplit...) dùng chỉ vài bit mỗi khoá, ít hơn nhiều so với sơ đồ hai tầng của sách.

## Bài tập và bài toán cuối chương

### Bài tập Mục 11.1 (trang 255)

- **11.1-1:** Tập động S được biểu diễn bằng bảng địa chỉ trực tiếp T độ dài m. Mô tả thủ tục tìm phần tử lớn nhất của S. Hiệu năng xấu nhất? *Người tổng hợp:* quét k từ m − 1 xuống 0, trả về T[k] đầu tiên khác NIL (hoặc NIL nếu S rỗng). Xấu nhất Θ(m) — khi S rỗng hoặc chỉ chứa khoá nhỏ; thời gian phụ thuộc m chứ không phụ thuộc |S|.
- **11.1-2:** Một **vector bit** (bit vector) là mảng các bit 0 và 1; vector bit độ dài m tốn ít bộ nhớ hơn nhiều so với mảng m con trỏ. Mô tả cách dùng vector bit để biểu diễn tập động các phần tử phân biệt không có dữ liệu vệ tinh, các phép toán từ điển chạy O(1). *Người tổng hợp:* bit b[k] = 1 khi và chỉ khi k thuộc tập. SEARCH(k) trả về b[k]; INSERT(k) gán b[k] = 1; DELETE(k) gán b[k] = 0. Mỗi phép toán là một thao tác bit O(1). Ví dụ m = 10, tập {2, 3, 5, 8}: vector 0011010010.
- **11.1-3:** Cài bảng địa chỉ trực tiếp mà khoá các phần tử không nhất thiết phân biệt và phần tử có thể có dữ liệu vệ tinh; ba phép toán INSERT, DELETE, SEARCH đều O(1). (Nhớ rằng DELETE nhận con trỏ tới đối tượng cần xoá, không nhận khoá.) *Người tổng hợp:* ô T[k] trỏ tới một danh sách liên kết đôi chứa mọi phần tử khoá k. INSERT chèn vào đầu danh sách T[x.key]; DELETE gỡ x khỏi danh sách nhờ con trỏ *prev*, *next* (cập nhật T[x.key] nếu x là đầu); SEARCH(k) trả về phần tử đầu của T[k] (bất kỳ phần tử nào có khoá k).
- **11.1-4 (★):** Cài từ điển bằng địa chỉ trực tiếp trên một mảng **khổng lồ**. Lúc đầu các ô có thể chứa rác, và khởi tạo toàn bộ mảng là không thực tế vì quá lớn. Mỗi đối tượng lưu dùng O(1) bộ nhớ; SEARCH, INSERT, DELETE mỗi phép O(1); khởi tạo cấu trúc O(1). (Gợi ý: dùng thêm một mảng hoạt động như ngăn xếp, kích thước bằng số khoá thực sự lưu, để xác định một ô của mảng khổng lồ có hợp lệ hay không.) *Lời giải của người tổng hợp:* mảng khổng lồ T, ngăn xếp S[1..] với chỉ số đỉnh top (khởi tạo top = 0 — O(1)). Ô T[k] được coi là **hợp lệ** khi và chỉ khi 1 ≤ T[k] ≤ top và S[T[k]] = k (rác trong T[k] không thể vượt qua cả hai kiểm tra vì S[1..top] chỉ chứa khoá thật, mỗi khoá trỏ đúng một vị trí). SEARCH(k): kiểm tra tính hợp lệ, nếu hợp lệ trả về đối tượng lưu kèm S[T[k]]. INSERT(x): top = top + 1; S[top] = x.key (kèm con trỏ tới x); T[x.key] = top. DELETE(x): đặt i = T[x.key]; chuyển phần tử đỉnh vào chỗ trống: S[i] = S[top], T[S[i]] = i; top = top − 1. Mọi phép đều O(1).

### Bài tập Mục 11.2 (trang 261)

- **11.2-1:** Dùng hàm băm h băm n khoá phân biệt vào mảng T độ dài m. Giả định băm đều đơn giản, số va chạm kỳ vọng là bao nhiêu — chính xác hơn, kỳ vọng của lực lượng tập {{k, l} : k ≠ l và h(k) = h(l)}? *Người tổng hợp:* tổng của C(n, 2) biến chỉ thị, mỗi biến kỳ vọng 1/m: E = n(n − 1)/(2m). Ví dụ n = 9, m = 9: 36/9 = 4 cặp.
- **11.2-2:** Minh hoạ việc chèn các khoá 5, 28, 19, 15, 20, 33, 12, 17, 10 vào bảng băm nối chuỗi 9 ô với h(k) = k mod 9. *Lời giải:* đã trình bày ở Nội dung chi tiết, Mục 3: ô 1 chứa 10 → 19 → 28; ô 2: 20; ô 3: 12; ô 5: 5; ô 6: 33 → 15; ô 8: 17; các ô 0, 4, 7 rỗng.
- **11.2-3:** Giáo sư Marley giả thuyết rằng giữ mỗi danh sách ở thứ tự đã sắp xếp sẽ cải thiện hiệu năng đáng kể. Sửa đổi này ảnh hưởng thế nào tới thời gian tìm thành công, tìm thất bại, chèn và xoá? *Người tổng hợp:* tìm thất bại có thể dừng sớm khi gặp khoá lớn hơn k (khoảng một nửa chuỗi), nhưng vẫn Θ(1 + α); tìm thành công không đổi, Θ(1 + α); chèn từ O(1) thành Θ(1 + α) vì phải tìm vị trí; xoá vẫn O(1) với danh sách đôi. Không có cải thiện tiệm cận — giả thuyết sai.
- **11.2-4:** Đề xuất cách cấp phát và giải phóng bộ nhớ cho các phần tử ngay trong bảng băm bằng cách nối mọi ô chưa dùng thành một danh sách tự do. Giả sử một ô lưu được một cờ và hoặc một phần tử cộng một con trỏ, hoặc hai con trỏ. Mọi phép toán từ điển và danh sách tự do phải chạy O(1) kỳ vọng. Danh sách tự do cần liên kết đôi hay liên kết đơn là đủ? *Người tổng hợp:* cờ báo ô đang "tự do" hay "đang dùng". Ô tự do dùng hai con trỏ để nằm trong danh sách tự do liên kết đôi; ô đang dùng chứa một phần tử và con trỏ *next* tới phần tử kế trong chuỗi của nó. Chèn khoá k: nếu ô h(k) tự do, gỡ nó khỏi danh sách tự do (cần liên kết **đôi** để gỡ một ô ở giữa trong O(1)) và đặt k vào, chuỗi dài 1. Nếu ô h(k) đang chứa phần tử của chính chuỗi h(k), lấy một ô tự do bất kỳ (đầu danh sách tự do) đặt k vào và nối vào chuỗi. Nếu ô h(k) đang bị một phần tử của **chuỗi khác** mượn, dời phần tử đó sang một ô tự do khác (cần tìm phần tử đứng trước nó trong chuỗi của nó — O(1) kỳ vọng vì chuỗi dài O(1 + α)), rồi đặt k vào ô h(k). Xoá: gỡ khỏi chuỗi, trả ô về danh sách tự do. Vậy danh sách tự do cần liên kết đôi.
- **11.2-5:** Lưu tập n khoá vào bảng băm cỡ m. Chứng minh nếu khoá lấy từ vũ trụ U với |U| > nm, thì U có một tập con cỡ n gồm các khoá cùng băm vào một ô, nên thời gian tìm xấu nhất của nối chuỗi là Θ(n). *Người tổng hợp:* nguyên lý chuồng bồ câu — nếu mỗi ô có không quá n khoá của U băm vào thì |U| ≤ nm, mâu thuẫn; vậy có ô nhận ít nhất n + 1 khoá, chọn n khoá trong đó.
- **11.2-6:** Đã lưu n khoá vào bảng băm cỡ m bằng nối chuỗi, biết độ dài mỗi chuỗi kể cả độ dài L của chuỗi dài nhất. Mô tả thủ tục chọn ngẫu nhiên đều một khoá trong bảng và trả về trong thời gian kỳ vọng O(L · (1 + 1/α)). *Người tổng hợp (phương pháp loại bỏ):* lặp: chọn ngẫu nhiên đều ô j ∈ {0..m − 1} và chỉ số t ∈ {1..L}; nếu t ≤ n_j thì trả về phần tử thứ t của chuỗi j (duyệt O(L)), ngược lại thử lại. Mỗi cặp (j, t) hợp lệ ứng với đúng một khoá, nên khoá trả về đều. Xác suất thành công mỗi lần thử là n/(mL) = α/L, số lần thử kỳ vọng L/α, mỗi lần O(1); cộng một lần duyệt O(L): tổng O(L/α + L) = O(L(1 + 1/α)).

### Bài tập Mục 11.3 (trang 268–269)

- **11.3-1:** Tìm trong danh sách liên kết độ dài n, mỗi phần tử chứa khoá k (chuỗi ký tự dài) kèm giá trị băm h(k). Tận dụng giá trị băm thế nào? *Người tổng hợp:* tính h của khoá cần tìm một lần, rồi với mỗi phần tử so sánh giá trị băm trước (so sánh số nguyên, rẻ); chỉ khi giá trị băm bằng nhau mới so sánh hai chuỗi dài.
- **11.3-2:** Băm chuỗi r ký tự vào m ô bằng cách coi nó là số cơ số 128 rồi dùng phương pháp chia. Số m vừa một từ máy 32 bit, nhưng chuỗi coi như số cơ số 128 chiếm nhiều từ. Làm sao tính giá trị băm mà chỉ dùng hằng số từ bộ nhớ ngoài chính chuỗi? *Người tổng hợp:* quy tắc Horner với phép lấy dư ở mỗi bước: h = 0; với mỗi ký tự c từ trái sang phải: h = (h · 128 + c) mod m. Đúng vì (a · 128 + c) mod m = ((a mod m) · 128 + c) mod m; giá trị trung gian < 128m, vừa vài từ.
- **11.3-3:** Xét biến thể phương pháp chia h(k) = k mod m với m = 2^p − 1 và k là chuỗi ký tự diễn giải trong cơ số 2^p. Chứng minh nếu chuỗi x có được từ chuỗi y bằng hoán vị các ký tự thì x và y cùng giá trị băm. Cho ví dụ ứng dụng mà tính chất này không mong muốn. *Người tổng hợp:* 2^p ≡ 1 (mod 2^p − 1), nên k = Σ cᵢ · 2^(pi) ≡ Σ cᵢ (mod m): giá trị băm chỉ phụ thuộc tổng mã ký tự, không phụ thuộc thứ tự. Ví dụ không mong muốn: từ điển chứa nhiều từ đảo chữ ("stop", "pots", "tops", "spot", "opts" va chạm hết), hay khoá là tổ hợp toạ độ/ngày tháng ("12-03" và "03-12").
- **11.3-4:** Bảng cỡ m = 1000, h(k) = ⌊m (kA mod 1)⌋ với A = (√5 − 1)/2. Tính vị trí của các khoá 61, 62, 63, 64, 65. *Lời giải người tổng hợp (tính lại):* 700, 318, 936, 554, 172. (Ví dụ 63A ≈ 38,9361 → 936; 65A ≈ 40,1722 → 172.)
- **11.3-5 (★):** Họ ℋ các hàm từ tập hữu hạn U vào tập hữu hạn B gọi là **ε-phổ quát** nếu với mọi cặp phần tử khác nhau k, l ∈ U, Pr{h(k) = h(l)} ≤ ε, xác suất lấy theo h chọn ngẫu nhiên từ ℋ. Chứng minh họ ε-phổ quát phải có ε ≥ 1/|B| − 1/|U|. *Hướng giải của người tổng hợp:* với một h cố định, gọi u_b = |h⁻¹(b)|; số cặp có thứ tự (k, l), k ≠ l, va chạm là Σ_b u_b(u_b − 1) = Σ u_b² − |U| ≥ |U|²/|B| − |U| (bất đẳng thức Cauchy–Schwarz, vì Σ u_b = |U|). Lấy trung bình theo h: tổng xác suất va chạm trên |U|(|U| − 1) cặp có thứ tự ≥ |U|²/|B| − |U|, nên có cặp với xác suất ≥ (|U|/|B| − 1)/(|U| − 1) = (|U| − |B|)/(|B|(|U| − 1)) ≥ (|U| − |B|)/(|B||U|) = 1/|B| − 1/|U|.
- **11.3-6 (★):** U là tập các bộ n giá trị thuộc ℤ_p, B = ℤ_p, p nguyên tố. Với b ∈ ℤ_p định nghĩa h_b(⟨a₀, a₁, …, a_{n−1}⟩) = (Σⱼ₌₀ⁿ⁻¹ a_j b^j) mod p, và ℋ = {h_b : b ∈ ℤ_p}. Lập luận ℋ là ((n − 1)/p)-phổ quát theo định nghĩa ở 11.3-5. (Gợi ý: Bài tập 31.4-4.) *Người tổng hợp:* với hai bộ khác nhau x, y, h_b(x) = h_b(y) khi và chỉ khi b là nghiệm của đa thức Σ (x_j − y_j) z^j modulo p — một đa thức khác 0 bậc ≤ n − 1, nên có không quá n − 1 nghiệm trong ℤ_p. Do đó Pr ≤ (n − 1)/p.

### Bài tập Mục 11.4 (trang 277)

- **11.4-1:** Chèn các khoá 10, 22, 31, 4, 15, 28, 17, 88, 59 vào bảng độ dài m = 11 bằng địa chỉ mở với hàm băm phụ h′(k) = k. Minh hoạ kết quả với dò tuyến tính, dò bậc hai với c₁ = 1, c₂ = 3, và băm kép với h₁(k) = k, h₂(k) = 1 + (k mod (m − 1)). *Lời giải của người tổng hợp* (ghi các ô đã dò của từng khoá):

  | Khoá | Dò tuyến tính | Dò bậc hai (c₁ = 1, c₂ = 3) | Băm kép (h₂ = 1 + k mod 10) |
  |---|---|---|---|
  | 10 | 10 | 10 | 10 |
  | 22 | 0 | 0 | 0 |
  | 31 | 9 | 9 | 9 |
  | 4 | 4 | 4 | 4 |
  | 15 | 4, 5 | 4, 8 | 4, 10, 5 (h₂ = 6) |
  | 28 | 6 | 6 | 6 |
  | 17 | 6, 7 | 6, 10, 9, 3 | 6, 3 (h₂ = 8) |
  | 88 | 0, 1 | 0, 4, 3, 8, 8, 3, 4, 0, 2 | 0, 9, 7 (h₂ = 9) |
  | 59 | 4, 5, 6, 7, 8 | 4, 8, 7 | 4, 3, 2 (h₂ = 10) |

  Bảng cuối cùng (ô 0..10):

  | Ô | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
  |---|---|---|---|---|---|---|---|---|---|---|---|
  | Tuyến tính | 22 | 88 | – | – | 4 | 15 | 28 | 17 | 59 | 31 | 10 |
  | Bậc hai | 22 | – | 88 | 17 | 4 | – | 28 | 59 | 15 | 31 | 10 |
  | Băm kép | 22 | – | 59 | 17 | 4 | 15 | 28 | 88 | – | 31 | 10 |

  Nhận xét: dò tuyến tính tạo một cụm dài 4..10 rồi vòng sang 0, 1 (khoá 59 mất 5 lần dò); dò bậc hai làm khoá 88 mất 9 lần dò vì dãy dò lặp ô (tham số c₁ = 1, c₂ = 3, m = 11 không cho hoán vị); băm kép tối đa 3 lần dò.
- **11.4-2:** Viết pseudocode cho HASH-DELETE như mô tả trong mục, và sửa HASH-INSERT để xử lý giá trị đặc biệt DELETED. *Lời giải của người tổng hợp:*

  ```text
  HASH-DELETE(T, k)
  1  j = HASH-SEARCH(T, k)
  2  if j ≠ NIL
  3      T[j] = DELETED

  HASH-INSERT(T, k)
  1  i = 0
  2  repeat
  3      j = h(k, i)
  4      if T[j] == NIL or T[j] == DELETED
  5          T[j] = k
  6          return j
  7      else i = i + 1
  8  until i == m
  9  error "hash table overflow"
  ```
  HASH-SEARCH giữ nguyên: DELETED khác k và khác NIL nên vòng lặp đi qua nó. (Lưu ý của người tổng hợp: nếu cho phép chèn khoá đã có, HASH-INSERT mới có thể đặt bản thứ hai vào một ô DELETED đứng trước bản cũ; muốn tránh thì tìm trước khi chèn.)
- **11.4-3:** Bảng địa chỉ mở với băm đều. Cho cận trên số lần dò kỳ vọng của tìm thất bại và tìm thành công khi hệ số tải là 3/4 và 7/8. *Người tổng hợp:* α = 3/4: thất bại ≤ 4, thành công ≤ (4/3) ln 4 ≈ 1,848. α = 7/8: thất bại ≤ 8, thành công ≤ (8/7) ln 8 ≈ 2,377.
- **11.4-4 (★):** Dùng băm kép h(k, i) = (h₁(k) + i·h₂(k)) mod m. Chứng minh nếu m và h₂(k) có ước chung lớn nhất d ≥ 1 với một khoá k nào đó, thì một lần tìm thất bại khoá k xét (1/d) bảng trước khi quay về ô h₁(k). Vậy khi d = 1 (m và h₂(k) nguyên tố cùng nhau), tìm kiếm có thể xét toàn bộ bảng. (Gợi ý: Chương 31.) *Người tổng hợp:* h(k, i) = h(k, i′) khi và chỉ khi (i − i′)·h₂(k) ≡ 0 (mod m), tức (i − i′)·(h₂(k)/d) ≡ 0 (mod m/d); vì h₂(k)/d nguyên tố cùng nhau với m/d, điều này tương đương i ≡ i′ (mod m/d). Vậy dãy dò lặp với chu kỳ đúng m/d: xét m/d ô phân biệt, tức 1/d bảng, rồi quay về h₁(k). Ví dụ m = 12, h₂(k) = 4, d = 4: chỉ xét 3 ô.
- **11.4-5 (★):** Bảng địa chỉ mở hệ số tải α. Tìm giá trị α khác 0 sao cho số lần dò kỳ vọng của tìm thất bại bằng hai lần số lần dò kỳ vọng của tìm thành công, dùng các cận trên của Định lý 11.6 và 11.8. *Người tổng hợp:* giải 1/(1 − α) = (2/α) ln(1/(1 − α)) bằng số: α ≈ 0,7153. (Kiểm tra: 1/(1 − 0,7153) ≈ 3,512; (2/0,7153) · ln 3,512 ≈ 2,796 · 1,256 ≈ 3,512.)

### Bài tập Mục 11.5 (trang 282)

- **11.5-1 (★):** Chèn n khoá vào bảng cỡ m bằng địa chỉ mở và băm đều. Gọi p(n, m) là xác suất không có va chạm nào. Chứng minh p(n, m) ≤ e^(−n(n−1)/2m). (Gợi ý: công thức (3.12).) Lập luận khi n vượt √m, xác suất tránh được va chạm giảm nhanh về 0. *Người tổng hợp:* khoá thứ i + 1 không va chạm khi ô đầu của nó rỗng, xác suất (m − i)/m = 1 − i/m. Dùng 1 + x ≤ e^x (công thức (3.12)): p(n, m) = Πᵢ₌₀ⁿ⁻¹ (1 − i/m) ≤ Π e^(−i/m) = e^(−Σi/m) = e^(−n(n−1)/(2m)). Khi n = c√m, số mũ ≈ −c²/2: c = 3 cho p ≤ e^(−4,5) ≈ 0,011. Đây là nghịch lý ngày sinh: m = 365, n = 23 cho p ≤ e^(−0,69) ≈ 0,50.

### Problem 11-1: Cận cho dãy dò dài nhất (Longest-probe bound for hashing)

Dùng bảng băm địa chỉ mở cỡ m để lưu n ≤ m/2 phần tử.

- **(a)** Giả định băm đều, chứng minh với i = 1, 2, …, n, xác suất lần chèn thứ i cần **nhiều hơn hẳn** k lần dò không quá 2^(−k). *Người tổng hợp:* trước lần chèn thứ i có i − 1 < n ≤ m/2 ô bị chiếm. Cần hơn k lần dò khi k lần dò đầu đều gặp ô bị chiếm; như chứng minh Định lý 11.6, xác suất ≤ ((i − 1)/m)^k ≤ (1/2)^k.
- **(b)** Chứng minh với i = 1, …, n, xác suất lần chèn thứ i cần hơn 2 lg n lần dò là O(1/n²). *Người tổng hợp:* thay k = 2 lg n: 2^(−2 lg n) = 1/n².
- Gọi X_i là số lần dò của lần chèn thứ i; (b) cho Pr{X_i > 2 lg n} = O(1/n²). Gọi X = max₁≤ᵢ≤ₙ X_i là số lần dò lớn nhất trong n lần chèn.
- **(c)** Chứng minh Pr{X > 2 lg n} = O(1/n). *Người tổng hợp:* cận hợp (union bound): Pr{∃i : X_i > 2 lg n} ≤ Σ Pr{X_i > 2 lg n} = n · O(1/n²) = O(1/n).
- **(d)** Chứng minh độ dài kỳ vọng E[X] của dãy dò dài nhất là O(lg n). *Người tổng hợp:* mỗi lần chèn có tối đa n − 1 ô bị chiếm nên X ≤ n. E[X] ≤ 2 lg n · Pr{X ≤ 2 lg n} + n · Pr{X > 2 lg n} ≤ 2 lg n + n · O(1/n) = O(lg n).

### Problem 11-2: Cận cho cỡ ô với nối chuỗi (Slot-size bound for chaining)

Bảng băm n ô, nối chuỗi, chèn n khoá; mỗi khoá có xác suất như nhau băm vào mỗi ô. Gọi M là số khoá lớn nhất trong một ô sau khi chèn hết. Nhiệm vụ: chứng minh cận trên O(lg n / lg lg n) cho E[M].

- **(a)** Lập luận rằng xác suất Q_k để đúng k khoá băm vào một ô cụ thể là

  ```text
  Q_k = (1/n)^k · (1 − 1/n)^(n−k) · C(n, k)
  ```
  *Người tổng hợp:* phân phối nhị thức — chọn k khoá trong n (C(n, k) cách), k khoá đó vào ô này (mỗi khoá xác suất 1/n), n − k khoá còn lại vào ô khác (mỗi khoá 1 − 1/n), độc lập.
- **(b)** Gọi P_k là xác suất M = k (ô nhiều khoá nhất chứa đúng k khoá). Chứng minh P_k ≤ n·Q_k. *Người tổng hợp:* M = k kéo theo có ít nhất một ô chứa đúng k khoá; cận hợp trên n ô.
- **(c)** Dùng xấp xỉ Stirling (công thức (3.18)) chứng minh Q_k < e^k/k^k. *Người tổng hợp:* C(n, k) ≤ n^k/k!, nên Q_k ≤ (1/n)^k · n^k/k! = 1/k!; Stirling cho k! > (k/e)^k, nên Q_k < e^k/k^k.
- **(d)** Chứng minh tồn tại hằng số c > 1 sao cho Q_{k₀} < 1/n³ với k₀ = c lg n / lg lg n. Suy ra P_k < 1/n² với k ≥ k₀. *Người tổng hợp:* cần k₀ (lg k₀ − lg e) > 3 lg n. Với k₀ = c lg n / lg lg n: lg k₀ = lg c + lg lg n − lg lg lg n, nên k₀ (lg k₀ − lg e) = c lg n · (1 − (lg lg lg n − lg c + lg e)/lg lg n), tiến tới c lg n; chọn c đủ lớn (ví dụ c > 3 và n đủ lớn) thì vượt 3 lg n. Vì e^k/k^k giảm khi k ≥ 1, Q_k < 1/n³ với mọi k ≥ k₀, và P_k ≤ n Q_k < 1/n².
- **(e)** Lập luận rằng

  ```text
  E[M] ≤ Pr{ M > c lg n / lg lg n } · n + Pr{ M ≤ c lg n / lg lg n } · c lg n / lg lg n
  ```
  và suy ra E[M] = O(lg n / lg lg n). *Người tổng hợp:* M ≤ n luôn đúng, nên phần M > k₀ đóng góp tối đa n lần xác suất của nó, phần M ≤ k₀ đóng góp tối đa k₀. Pr{M > k₀} = Σ_{k>k₀} P_k < n · 1/n² = 1/n, nên số hạng đầu < 1; số hạng sau ≤ k₀. Vậy E[M] < 1 + c lg n/lg lg n = O(lg n / lg lg n).

### Problem 11-3: Dò bậc hai (Quadratic probing)

Cần tìm khoá k trong bảng băm có các vị trí 0, 1, …, m − 1, với hàm băm h ánh xạ không gian khoá vào {0, 1, …, m − 1}. Sơ đồ tìm kiếm:

1. Tính j = h(k), đặt i = 0.
2. Dò vị trí j tìm khoá k. Nếu tìm thấy, hoặc vị trí này rỗng, kết thúc tìm kiếm.
3. Đặt i = i + 1. Nếu i bằng m, bảng đã đầy, kết thúc tìm kiếm. Ngược lại đặt j = (i + j) mod m và quay lại bước 2.

Giả sử m là luỹ thừa của 2.

- **(a)** Chứng minh sơ đồ này là một trường hợp của dò bậc hai tổng quát bằng cách chỉ ra các hằng số c₁, c₂ phù hợp cho (11.5). *Người tổng hợp:* sau lần dò thứ i, j = h(k) + 1 + 2 + ⋯ + i = h(k) + i(i + 1)/2 = h(k) + i/2 + i²/2 (mod m). Vậy c₁ = c₂ = 1/2 (tổng luôn là số nguyên).
- **(b)** Chứng minh thuật toán xét mọi vị trí của bảng trong trường hợp xấu nhất. *Người tổng hợp:* cần chứng minh i(i + 1)/2 mod m khác nhau với i = 0..m − 1. Giả sử 0 ≤ j < i < m và i(i + 1)/2 ≡ j(j + 1)/2 (mod m). Khi đó (i − j)(i + j + 1)/2 ≡ 0 (mod m), tức (i − j)(i + j + 1) chia hết cho 2m = 2^(p+1). Tổng hai thừa số là 2i + 1, lẻ, nên đúng một thừa số lẻ; thừa số lẻ không góp thừa số 2 nào, nên thừa số chẵn phải chia hết cho 2^(p+1) = 2m. Nhưng 0 < i − j < m và 0 < i + j + 1 ≤ 2m − 2 < 2m — mâu thuẫn. Ví dụ m = 8: các độ lệch 0, 1, 3, 6, 10, 15, 21, 28 mod 8 = 0, 1, 3, 6, 2, 7, 5, 4 — đủ 8 ô.

### Problem 11-4: Băm và xác thực (Hashing and authentication)

Gọi ℋ là một lớp hàm băm, mỗi h ∈ ℋ ánh xạ vũ trụ U vào {0, 1, …, m − 1}. Ta nói ℋ là **k-phổ quát** (k-universal) nếu với mọi dãy cố định k khoá phân biệt ⟨x⁽¹⁾, x⁽²⁾, …, x⁽ᵏ⁾⟩ và với h chọn ngẫu nhiên từ ℋ, dãy ⟨h(x⁽¹⁾), h(x⁽²⁾), …, h(x⁽ᵏ⁾)⟩ có xác suất như nhau là bất kỳ dãy nào trong m^k dãy độ dài k với phần tử lấy từ {0, 1, …, m − 1}.

- **(a)** Chứng minh nếu ℋ là 2-phổ quát thì nó phổ quát. *Người tổng hợp:* với k ≠ l, cặp (h(k), h(l)) đều trên m² cặp; m cặp có hai thành phần bằng nhau, nên Pr{h(k) = h(l)} = m/m² = 1/m.
- **(b)** U là tập các bộ n giá trị lấy từ ℤ_p = {0, 1, …, p − 1}, p nguyên tố. Với x = ⟨x₀, x₁, …, x_{n−1}⟩ ∈ U và mọi bộ a = ⟨a₀, a₁, …, a_{n−1}⟩ ∈ U, định nghĩa h_a(x) = (Σⱼ₌₀ⁿ⁻¹ a_j x_j) mod p, và ℋ = {h_a}. Chứng minh ℋ phổ quát nhưng không 2-phổ quát. (Gợi ý: tìm một khoá mà mọi hàm trong ℋ cho cùng giá trị.) *Người tổng hợp:* phổ quát — với x ≠ y khác nhau ở toạ độ i, h_a(x) = h_a(y) khi và chỉ khi a_i(x_i − y_i) ≡ −Σ_{j≠i} a_j(x_j − y_j) (mod p); cố định các a_j khác, đúng một giá trị a_i thoả, nên xác suất 1/p (ở đây m = p). Không 2-phổ quát — khoá x = ⟨0, …, 0⟩ có h_a(x) = 0 với mọi a, nên cặp (h(0), h(y)) không bao giờ có thành phần đầu khác 0, không thể đều trên p² cặp.
- **(c)** Sửa ℋ một chút: với mọi a ∈ U và b ∈ ℤ_p, định nghĩa h′_ab(x) = (Σⱼ₌₀ⁿ⁻¹ a_j x_j + b) mod p và ℋ′ = {h′_ab}. Lập luận ℋ′ là 2-phổ quát. (Gợi ý: xét x, y cố định với x_i ≠ y_i với một i nào đó; điều gì xảy ra với h′_ab(x), h′_ab(y) khi a_i và b chạy trên ℤ_p?) *Người tổng hợp:* cố định các a_j với j ≠ i. Ánh xạ (a_i, b) ↦ (h′(x), h′(y)) là hệ tuyến tính modulo p với định thức x_i − y_i ≠ 0, nên là song ánh từ ℤ_p² vào ℤ_p². Vậy (h′(x), h′(y)) đều trên p² cặp.
- **(d)** Alice và Bob bí mật thống nhất một hàm băm h từ họ 2-phổ quát ℋ, mỗi h ánh xạ vũ trụ U vào ℤ_p, p nguyên tố. Sau đó Alice gửi thông điệp m ∈ U cho Bob qua Internet, kèm **thẻ xác thực** t = h(m); Bob kiểm tra cặp (m, t) nhận được có thoả t = h(m). Đối thủ chặn (m, t) trên đường đi và thay bằng cặp khác (m′, t′). Lập luận xác suất đối thủ lừa được Bob chấp nhận (m′, t′) không quá 1/p, dù đối thủ có sức tính toán bao nhiêu, và kể cả khi biết họ ℋ. *Người tổng hợp:* nếu m′ = m thì t′ ≠ t, Bob từ chối chắc chắn. Nếu m′ ≠ m: do 2-phổ quát, Pr{h(m) = t và h(m′) = t′} = 1/p², và Pr{h(m) = t} = 1/p, nên Pr{h(m′) = t′ | h(m) = t} = 1/p. Đối thủ chỉ thấy (m, t), tức chỉ biết h(m) = t; với mọi lựa chọn (m′, t′) (kể cả lựa chọn ngẫu nhiên phụ thuộc (m, t)), xác suất thành công ≤ 1/p. Sức tính toán không giúp được vì thông tin về h(m′) hoàn toàn không có — đây là an toàn theo lý thuyết thông tin. (Lưu ý ký hiệu: chữ m ở đây là thông điệp, khác với m là số ô ở đầu bài toán.)

### Ghi chú chương (Chapter notes, trang 285)

- **Knuth** và **Gonnet** là tài liệu tham khảo xuất sắc về phân tích thuật toán băm.
- Knuth ghi công **H. P. Luhn** (1953) phát minh bảng băm cùng phương pháp nối chuỗi để giải quyết va chạm. Cùng thời gian đó, **G. M. Amdahl** khởi xướng ý tưởng địa chỉ mở.
- **Carter** và **Wegman** đưa ra khái niệm lớp hàm băm phổ quát năm 1979.
- **Fredman, Komlós** và **Szemerédi** xây dựng sơ đồ băm hoàn hảo cho tập tĩnh trình bày ở Mục 11.5 (thường gọi là sơ đồ FKS — theo hiểu biết của người tổng hợp). **Dietzfelbinger** và cộng sự mở rộng phương pháp cho tập động, xử lý chèn và xoá trong thời gian kỳ vọng khấu hao O(1).

## Luận điểm cốt lõi

### Mệnh đề

Bảng băm cài đặt từ điển (INSERT, SEARCH, DELETE) với thời gian trung bình O(1) và bộ nhớ Θ(n), bằng cách tính chỉ số ô từ khoá qua một hàm băm và giải quyết va chạm bằng nối chuỗi hoặc địa chỉ mở; trường hợp xấu nhất vẫn là Θ(n), nhưng băm phổ quát biến cận trung bình thành cận kỳ vọng đúng với **mọi** tập khoá, và băm hoàn hảo cho tìm kiếm O(1) xấu nhất khi tập khoá tĩnh.

### Giả định

- Mô hình RAM: tính h(k) tốn O(1); khoá được diễn giải thành số tự nhiên (vừa một từ máy, hoặc xử lý từng phần như Bài tập 11.3-2).
- Phân tích nối chuỗi (Mục 11.2): **băm đều đơn giản** — mỗi khoá rơi vào mỗi ô với xác suất 1/m, độc lập. Phân tích tìm thành công còn giả định phần tử cần tìm đều trên n phần tử và chèn vào đầu chuỗi.
- Phân tích địa chỉ mở (Mục 11.4): **băm đều** — dãy dò đều trên m! hoán vị; không phép xoá (không có DELETED).
- Băm phổ quát (★11.3.3, ★11.5): không giả định gì về khoá; ngẫu nhiên nằm trong việc chọn hàm băm, độc lập với khoá; p nguyên tố lớn hơn mọi khoá.
- Băm hoàn hảo: tập khoá biết trước và không đổi.

### Cơ chế

1. **Thu hẹp miền chỉ số:** h ánh xạ U khổng lồ vào m ô, m tỷ lệ với số khoá thực sự lưu.
2. **Chấp nhận va chạm và xử lý cục bộ:** nối chuỗi gom các khoá cùng ô vào một danh sách; địa chỉ mở tính một dãy dò riêng cho mỗi khoá.
3. **Giữ hệ số tải là hằng:** chi phí mỗi phép toán là Θ(1 + α) (nối chuỗi) hay ≤ 1/(1 − α) lần dò (địa chỉ mở); m = Θ(n) thì O(1).
4. **Ngẫu nhiên hoá hàm băm:** lớp phổ quát bảo đảm mọi cặp khoá va chạm với xác suất ≤ 1/m; tính tuyến tính của kỳ vọng cộng các cặp lại thành độ dài chuỗi kỳ vọng ≤ 1 + α.
5. **Bình phương kích thước để loại va chạm:** bảng n² ô cho n khoá thì kỳ vọng số va chạm < 1/2 (nghịch lý ngày sinh); hai tầng (n ô rồi n_j² ô) giữ tổng bộ nhớ kỳ vọng < 2n nhờ Σ n_j² = n + 2·(số cặp va chạm).

### Bằng chứng và ví dụ tác giả đưa ra

- Hình bảng địa chỉ trực tiếp với U = {0..9}, K = {2, 3, 5, 8}; hình hàm băm và va chạm k₂, k₅; hình nối chuỗi với tám khoá.
- Định lý 11.1, 11.2: tìm thất bại và thành công Θ(1 + α); phép tính chính xác 1 + α/2 − α/(2n) bằng biến chỉ thị X_ij.
- Ví dụ `pt` = 14452 (cơ số 128); 100 mod 12 = 4; m = 701 cho 2000 chuỗi; phương pháp nhân k = 123456 cho h(k) = 67 với A = 2654435769/2³².
- Định lý 11.3, Hệ quả 11.4 (băm phổ quát); Định lý 11.5 (ℋ_pm phổ quát) với ví dụ h₃,₄(8) = 5.
- Ví dụ băm kép Hình 11.5 (khoá 14 dò 1, 5, 9) và k = 123456, m = 701 cho h₁ = 80, h₂ = 257.
- Định lý 11.6, Hệ quả 11.7, Định lý 11.8 với các con số 2 và 10 (tìm thất bại), 1,387 và 2,559 (tìm thành công) ở α = 0,5 và 0,9.
- Định lý 11.9, 11.10, Hệ quả 11.11, 11.12 và Hình 11.6 (chín khoá, bảng hai tầng; người tổng hợp phát hiện vị trí khoá 40 bị in sai).

### Kết luận và hàm ý cho người lập trình

- Dùng bảng băm khi chỉ cần tra cứu theo khoá chính xác; cần thứ tự (nhỏ nhất, kế tiếp, truy vấn khoảng) thì dùng cây tìm kiếm cân bằng (Chương 12–13).
- Giữ hệ số tải bị chặn: tự động nhân đôi bảng khi α vượt ngưỡng (kỹ thuật bảng động, Chương 17); với địa chỉ mở, đừng để α tới gần 1 vì chi phí tăng như 1/(1 − α).
- Hàm băm quyết định tất cả: tránh m = 2^p với phương pháp chia; khoá có cấu trúc (địa chỉ căn lề, số liên tiếp) dễ phá hàm băm ngây thơ.
- Với đầu vào không tin cậy (dữ liệu từ mạng), dùng hàm băm có khoá ngẫu nhiên bí mật (tinh thần băm phổ quát) để chống tấn công từ chối dịch vụ.
- Cần xoá thường xuyên thì nối chuỗi đơn giản hơn; địa chỉ mở phải dùng DELETED và dọn định kỳ.
- Tập khoá tĩnh (từ khoá, bảng tra cứu cố định) có thể dựng băm hoàn hảo để có tra cứu O(1) xấu nhất.

### Trong ngôn ngữ khoa học máy tính

Bảng địa chỉ trực tiếp: mọi phép toán O(1) xấu nhất, bộ nhớ Θ(|U|). Băm nối chuỗi với băm đều đơn giản: INSERT O(1) xấu nhất, DELETE O(1) xấu nhất (danh sách đôi), SEARCH Θ(1 + α) trung bình, Θ(n) xấu nhất; tìm thành công xem 1 + α/2 − α/(2n) phần tử. Băm phổ quát: Pr{h(k) = h(l)} ≤ 1/m; E[n_h(k)] ≤ α (k ∉ T), ≤ 1 + α (k ∈ T); dãy n phép toán với O(m) INSERT tốn Θ(n) kỳ vọng; ℋ_pm = {((ak + b) mod p) mod m} phổ quát, |ℋ_pm| = p(p − 1). Địa chỉ mở với băm đều, α < 1: tìm thất bại và chèn ≤ 1/(1 − α) lần dò; tìm thành công ≤ (1/α) ln(1/(1 − α)). Dò tuyến tính, dò bậc hai: m dãy dò; băm kép: Θ(m²) dãy dò. Băm hoàn hảo (FKS): m = n, m_j = n_j², E[Σ m_j] < 2n, Pr{Σ m_j ≥ 4n} < 1/2, bảng n² ô không va chạm với xác suất > 1/2; tìm kiếm O(1) xấu nhất, bộ nhớ O(n), dựng trong thời gian kỳ vọng O(n). Nối chuỗi n khoá vào n ô: chuỗi dài nhất kỳ vọng O(lg n / lg lg n) (Bài toán 11-2); địa chỉ mở với n ≤ m/2: dãy dò dài nhất kỳ vọng O(lg n) (Bài toán 11-1).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| dictionary | từ điển | tập động chỉ cần INSERT, SEARCH, DELETE |
| symbol table | bảng ký hiệu | từ điển của trình biên dịch, khoá là tên định danh |
| hash table | bảng băm | mảng m ô, phần tử khoá k ở ô h(k) |
| direct addressing / direct-address table | địa chỉ trực tiếp / bảng địa chỉ trực tiếp | ô k dành cho khoá k; cần |U| ô |
| slot | ô | một vị trí của bảng |
| universe of keys U | vũ trụ khoá U | mọi khoá có thể xuất hiện |
| actual keys K | tập khoá thực sự lưu K | các khoá đang có trong bảng |
| satellite data | dữ liệu vệ tinh | dữ liệu đi kèm khoá, cấu trúc không dùng tới |
| hash function / hash value | hàm băm / giá trị băm | h : U → {0..m − 1}; h(k) |
| hashes to | băm vào | khoá k băm vào ô h(k) |
| collision | va chạm | hai khoá khác nhau cùng giá trị băm |
| collision resolution | giải quyết va chạm | nối chuỗi hoặc địa chỉ mở |
| chaining | nối chuỗi | mỗi ô trỏ tới danh sách các phần tử băm vào ô |
| load factor α | hệ số tải α | n/m, số phần tử trung bình mỗi ô |
| simple uniform hashing | băm đều đơn giản | mỗi khoá vào mỗi ô xác suất 1/m, độc lập |
| unsuccessful / successful search | tìm kiếm thất bại / thành công | không có khoá / có khoá |
| division method | phương pháp chia | h(k) = k mod m |
| multiplication method | phương pháp nhân | h(k) = ⌊m (kA mod 1)⌋ |
| radix notation | biểu diễn theo cơ số | coi chuỗi là số trong cơ số 128, 256... |
| word size w | kích thước từ máy w | số bit của một từ |
| universal hashing / universal collection | băm phổ quát / lớp phổ quát | chọn h ngẫu nhiên; va chạm ≤ 1/m mỗi cặp |
| ε-universal | ε-phổ quát | xác suất va chạm mỗi cặp ≤ ε |
| k-universal | k-phổ quát | giá trị băm của k khoá phân biệt đều trên m^k dãy |
| adversary | đối thủ | người chọn đầu vào xấu nhất cho thuật toán |
| multiplicative inverse modulo p | nghịch đảo nhân modulo p | y với xy ≡ 1 (mod p) |
| open addressing | địa chỉ mở | mọi phần tử nằm trong bảng, dò tìm ô |
| probe / probe sequence | dò / dãy dò | xét một ô / thứ tự các ô xét cho khoá k |
| auxiliary hash function | hàm băm phụ | h′, h₁, h₂ dùng để dựng dãy dò |
| uniform hashing | băm đều | dãy dò đều trên m! hoán vị |
| linear probing | dò tuyến tính | (h′(k) + i) mod m |
| quadratic probing | dò bậc hai | (h′(k) + c₁i + c₂i²) mod m |
| double hashing | băm kép | (h₁(k) + i·h₂(k)) mod m |
| primary clustering | tụ cụm sơ cấp | các đoạn ô liên tiếp bị chiếm dài dần (dò tuyến tính) |
| secondary clustering | tụ cụm thứ cấp | cùng ô đầu thì cùng dãy dò (dò bậc hai) |
| relatively prime | nguyên tố cùng nhau | ước chung lớn nhất bằng 1 |
| DELETED | DELETED (dấu đã xoá) | giá trị đặc biệt đánh dấu ô bị xoá trong địa chỉ mở |
| hash table overflow | tràn bảng băm | địa chỉ mở hết ô rỗng |
| static set | tập tĩnh | tập khoá không đổi sau khi lưu |
| perfect hashing | băm hoàn hảo | tìm kiếm O(1) truy cập bộ nhớ xấu nhất |
| first-level / secondary hash table | bảng tầng một / bảng băm phụ (tầng hai) | hai tầng của băm hoàn hảo |
| Markov's inequality | bất đẳng thức Markov | Pr{X ≥ t} ≤ E[X]/t với X ≥ 0 |
| birthday paradox | nghịch lý ngày sinh | khoảng √m khoá đã đủ để có va chạm |
| bit vector | vector bit | mảng bit biểu diễn tập con |
| free list | danh sách tự do | danh sách các ô chưa dùng |
| authentication tag | thẻ xác thực | t = h(m) gửi kèm thông điệp |

## Câu nói đáng nhớ

> "Although searching for an element in a hash table can take as long as searching for an element in a linked list—Θ(n) time in the worst case—in practice, hashing performs extremely well." — mở đầu Chương 11
>
> *Dịch: Dù tìm một phần tử trong bảng băm có thể lâu ngang tìm trong danh sách liên kết — Θ(n) trong trường hợp xấu nhất — trong thực tế băm chạy cực kỳ tốt.*

> "Instead of using the key as an array index directly, the array index is *computed* from the key." — mở đầu Chương 11
>
> *Dịch: Thay vì dùng khoá làm chỉ số mảng trực tiếp, chỉ số mảng được tính ra từ khoá.*

> "Clearly, we do not use hash tables for their worst-case performance." — Mục 11.2
>
> *Dịch: Rõ ràng ta không dùng bảng băm vì hiệu năng xấu nhất của nó.*

> "Any fixed hash function is vulnerable to such terrible worst-case behavior; the only effective way to improve the situation is to choose the hash function *randomly* in a way that is *independent* of the keys that are actually going to be stored." — Mục 11.3.3
>
> *Dịch: Mọi hàm băm cố định đều dễ bị trường hợp xấu nhất tệ hại như vậy; cách hiệu quả duy nhất để cải thiện là chọn hàm băm một cách ngẫu nhiên, độc lập với các khoá thực sự sẽ được lưu.*

> "Deletion from an open-address hash table is difficult." — Mục 11.4
>
> *Dịch: Xoá khỏi bảng băm địa chỉ mở là việc khó.*

> "We always make the first probe. With probability approximately α, the first probe finds an occupied slot, so that we need to probe a second time." — Mục 11.4, sau Định lý 11.6
>
> *Dịch: Ta luôn thực hiện lần dò thứ nhất. Với xác suất xấp xỉ α, lần dò thứ nhất gặp ô bị chiếm, nên cần dò lần thứ hai.*

> "We call a hashing technique *perfect hashing* if O(1) memory accesses are required to perform a search in the worst case." — Mục 11.5
>
> *Dịch: Ta gọi một kỹ thuật băm là băm hoàn hảo nếu cần O(1) lần truy cập bộ nhớ để thực hiện một lần tìm kiếm trong trường hợp xấu nhất.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: ba cấp độ bảo đảm được phân biệt rõ

Chương xếp các kết quả theo độ mạnh của giả định một cách rất sư phạm: (1) giả định băm đều đơn giản về **dữ liệu** (Định lý 11.1, 11.2) — dễ hiểu nhưng không kiểm chứng được; (2) băm phổ quát chuyển ngẫu nhiên từ dữ liệu sang **thuật toán** (Định lý 11.3) — cùng cận 1 + α nhưng đúng với mọi tập khoá, đúng bài học "ngẫu nhiên hoá" của quicksort ở Chương 7; (3) băm hoàn hảo cho cận **xấu nhất** khi chấp nhận thêm giả định tập tĩnh. Chứng minh Định lý 11.3 gần như chép lại chứng minh Định lý 11.2, chỉ đổi nguồn xác suất — cho người đọc thấy chính xác giả định nào được thay bằng giả định nào.

### Điểm mạnh: chứng minh ngắn, cùng một bộ công cụ

Mọi chứng minh của chương chỉ dùng biến chỉ thị, tính tuyến tính của kỳ vọng và bất đẳng thức Markov. Đẳng thức a² = a + 2·C(a, 2) trong Định lý 11.10 là một mẹo đẹp: biến tổng bình phương (khó) thành số cặp va chạm (dễ, vì đó đúng là đại lượng mà định nghĩa phổ quát chặn được).

### Điểm yếu và chỗ đơn giản hoá

- **Giả định băm đều (cho địa chỉ mở) không thực tế và sách thừa nhận điều đó**, nhưng không cho bất kỳ phân tích nào cho phương pháp thực sự dùng. Theo hiểu biết của người tổng hợp, Knuth đã phân tích chính xác dò tuyến tính: tìm thành công khoảng (1/2)(1 + 1/(1 − α)) và tìm thất bại khoảng (1/2)(1 + 1/(1 − α)²) lần dò — ở α = 0,9 là 5,5 và 50,5 lần dò, tệ hơn nhiều so với 2,56 và 10 của băm đều. Sách chỉ nói định tính "tụ cụm sơ cấp".
- **Đánh giá thấp dò tuyến tính.** Trên phần cứng hiện đại, dò tuyến tính thường nhanh nhất trong thực tế ở α vừa phải nhờ đọc các ô liền kề nằm trong cùng dòng bộ nhớ đệm; sách (2009) đo hiệu năng bằng số lần dò, không tính chi phí bộ nhớ. Theo hiểu biết của người tổng hợp, ấn bản 4 đã sửa cách nhìn này.
- **Xoá trong địa chỉ mở chỉ được bàn sơ lược.** Sách nói dùng DELETED làm thời gian tìm "không còn phụ thuộc α" nhưng không nêu cách xử lý (dựng lại bảng định kỳ, hay xoá dịch lùi cho dò tuyến tính).
- **Băm phổ quát cần số nguyên tố p lớn hơn mọi khoá và phép nhân mod p** — với khoá 64 bit, cần số học 128 bit; sách không bàn chi phí này hay các họ phổ quát nhanh hơn dùng phép dịch bit (multiply-shift của Dietzfelbinger và cộng sự — theo hiểu biết của người tổng hợp).
- **Không bàn kích thước bảng thay đổi.** Mọi phân tích giả định m cố định; trong thực tế bảng phải lớn lên khi n tăng. Chương 17 (bảng động) mới bù phần này.
- **Lỗi nhỏ trong Hình 11.6** (khoá 40 phải ở ô 3 của S₇) và vài chỗ ký hiệu chưa chặt (chú thích a = b = 0, chữ n trong Hệ quả 11.4, chữ m trong Bài toán 11-4) — đã nêu ở khối Lưu ý.

### So với thực tế

Theo hiểu biết của người tổng hợp: bảng băm là cấu trúc dữ liệu được dùng nhiều nhất trong phần mềm thực tế — đối tượng của JavaScript và Python, bảng ký hiệu của trình biên dịch, bộ đệm (cache) trong bộ nhớ như Memcached, phép nối băm (hash join) và chỉ mục băm trong cơ sở dữ liệu, bảng định tuyến. Các cài đặt hiện đại khác sách ở ba điểm: (1) hàm băm là các hàm trộn bit nhanh (MurmurHash, xxHash, wyhash) hoặc hàm có khoá chống tấn công (SipHash), không phải k mod m với m nguyên tố; (2) kích thước bảng thường là luỹ thừa của 2 để thay phép chia bằng phép AND, bù lại hàm băm phải trộn kỹ mọi bit; (3) địa chỉ mở với dò tuyến tính hoặc dò theo nhóm (SwissTable, Robin Hood hashing) được ưa chuộng hơn nối chuỗi vì tính cục bộ bộ nhớ. Ngoài ra còn các biến thể sách không nhắc như cuckoo hashing (tìm kiếm xấu nhất O(1) cho tập động, kỳ vọng khấu hao O(1) cho chèn), hàm băm nhất quán (consistent hashing) để chia dữ liệu cho nhiều máy, và bộ lọc Bloom (dùng nhiều hàm băm và một vector bit như Bài tập 11.1-2 để kiểm tra thuộc tập với xác suất dương tính giả nhỏ).

### Liên hệ các chương khác

- Chương 5 ([C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md)): biến chỉ thị, Bổ đề 5.1; nghịch lý ngày sinh (Mục 5.4.1) là nền của Định lý 11.9 và Bài tập 11.5-1; bài toán "bóng và thùng" (Mục 5.4.2) liên quan Bài toán 11-2.
- Chương 7 ([C07-quicksort.md](C07-quicksort.md)): cùng triết lý "ngẫu nhiên bên trong thuật toán thay cho giả định về đầu vào" như băm phổ quát.
- Chương 10 ([C10-cau-truc-du-lieu-co-ban.md](C10-cau-truc-du-lieu-co-ban.md)): danh sách liên kết đôi làm chuỗi; danh sách tự do (Bài tập 11.2-4); ngăn xếp trong Bài tập 11.1-4.
- Chương 12 và 13 ([C12-cay-tim-kiem-nhi-phan.md](C12-cay-tim-kiem-nhi-phan.md), [C13-cay-do-den.md](C13-cay-do-den.md)): từ điển có thứ tự, O(lg n) xấu nhất (cây đỏ-đen) so với O(1) trung bình của băm.
- Chương 17 ([C17-phan-tich-khau-hao.md](C17-phan-tich-khau-hao.md)): bảng động nhân đôi kích thước — giữ α = O(1) khi n không biết trước.
- Chương 20 ([C20-cay-van-emde-boas.md](C20-cay-van-emde-boas.md)): một cấu trúc khác cho khoá trong vũ trụ {0..u − 1}, như địa chỉ trực tiếp nhưng hỗ trợ cả SUCCESSOR trong O(lg lg u).
- Chương 31 ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)): số nguyên tố, nghịch đảo modulo, Định lý 31.6, hàm phi Euler — dùng trong Định lý 11.5 và Bài tập 11.4-4.
- Chương 32 ([C32-so-khop-chuoi.md](C32-so-khop-chuoi.md)): Rabin–Karp băm các đoạn chuỗi bằng phương pháp chia và quy tắc Horner (giống Bài tập 11.3-2), so sánh giá trị băm trước khi so sánh chuỗi (giống Bài tập 11.3-1).
- Phụ lục A, C ([PA-tong.md](PA-tong.md), [PC-dem-va-xac-suat.md](PC-dem-va-xac-suat.md)): công thức (A.1), bất đẳng thức tích phân (A.12), công thức (C.25), bất đẳng thức Markov (C.30).

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** hàng loạt bài kinh điển giải bằng bảng băm trong O(n): "hai số có tổng bằng k", đếm tần suất, phát hiện phần tử trùng, nhóm các từ đảo chữ (dùng khoá là chuỗi đã sắp xếp — ngược với Bài tập 11.3-3, ở đây ta *muốn* hoán vị cho cùng khoá), bộ đệm LRU (bảng băm kết hợp danh sách liên kết đôi). Câu hỏi lý thuyết thường gặp: vì sao bảng băm là O(1) "trung bình" chứ không phải xấu nhất, khi nào nên chọn cây thay vì bảng băm, nối chuỗi khác địa chỉ mở ra sao, vì sao xoá trong địa chỉ mở cần dấu DELETED.
- **Lập trình thi đấu:** bảng băm của thư viện chuẩn (ví dụ `unordered_map` trong C++) có thể bị bộ test thiết kế sẵn ép va chạm (hàm băm số nguyên mặc định là hàm đồng nhất); cách phòng thủ là tự viết hàm băm có hằng số ngẫu nhiên lúc chạy (ví dụ splitmix64 cộng với thời gian khởi động) — đúng tinh thần băm phổ quát. Băm chuỗi đa thức modulo số nguyên tố (Bài tập 11.3-2, 11.3-6) dùng để so sánh xâu con trong O(1); xác suất va chạm ≤ (n − 1)/p theo Bài tập 11.3-6, nên chọn p lớn (cỡ 10⁹ hoặc dùng hai modulo).
- **Kỹ thuật phần mềm:** chọn bảng băm khi chỉ cần tra cứu chính xác; định nghĩa `hashCode`/`__hash__` nhất quán với phép so sánh bằng (khoá bằng nhau phải cùng giá trị băm); không dùng đối tượng thay đổi được làm khoá; dùng hàm băm có khoá bí mật cho dữ liệu đến từ bên ngoài; theo dõi hệ số tải và chi phí bộ nhớ; với tập khoá cố định lớn (từ điển, bảng tra cứu nhúng), cân nhắc băm hoàn hảo.

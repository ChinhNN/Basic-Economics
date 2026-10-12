# Chương 27 — Thuật toán đa luồng (Multithreaded Algorithms)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009). Gồm hai phần: Phần VII "Selected Topics" — trang tên phần (trang 768, không in số; trang 767 để trắng) và lời giới thiệu Phần VII (Introduction, trang 769–771); Chương 27 "Multithreaded Algorithms", trang 772–812.
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (ba người đầu ở MIT, Stein ở Đại học Columbia); cuốn sách thường được gọi tắt là "CLRS". Riêng Charles E. Leiserson là một trong những người dẫn dắt dự án Cilk ở MIT, nguồn gốc trực tiếp của mô hình lập trình trong chương này (theo chính phần Ghi chú chương).
**Vị trí trong lập luận của cả cuốn sách:** Sáu phần đầu của sách đều làm việc trên mô hình máy RAM tuần tự của Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)): mỗi lúc chỉ một lệnh được thực hiện. Phần VII "Các chủ đề chọn lọc" mở rộng và bổ sung cho phần trước: một số chương đưa vào mô hình tính toán mới (mạch, máy song song), một số đi vào lĩnh vực chuyên biệt (hình học tính toán, lý thuyết số), hai chương cuối bàn giới hạn của việc thiết kế thuật toán hiệu quả. Chương 27 là chương đầu tiên của Phần VII và là chỗ duy nhất trong sách thay mô hình tuần tự bằng **mô hình song song đa luồng động** (dynamic multithreading). Chương dùng lại rất nhiều thứ đã có: dãy Fibonacci và tỷ lệ vàng của Chương 3 ([C03-tang-truong-cua-ham.md](C03-tang-truong-cua-ham.md)); truy hồi, định lý thợ, Bài tập 4.6-2 và các thuật toán nhân ma trận (ba vòng lặp lồng, chia để trị tám phép nhân, Strassen) của Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)); sắp xếp trộn và thủ tục MERGE của Chương 2; đường đi dài nhất trong dag của Mục 24.2 ([C24-duong-di-ngan-nhat-tu-mot-nguon.md](C24-duong-di-ngan-nhat-tu-mot-nguon.md)); PARTITION và RANDOMIZED-QUICKSORT của Chương 7 ([C07-quicksort.md](C07-quicksort.md)); RANDOMIZED-SELECT và SELECT của Chương 9 ([C09-trung-vi-va-thong-ke-thu-tu.md](C09-trung-vi-va-thong-ke-thu-tu.md)); thuật toán Floyd-Warshall của Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)); LCS và mẫu "ô phụ thuộc ô trên, ô trái" của Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)). Bài toán cuối chương nhìn về phía trước: song song hoá phân tích LU/LUP của Chương 28 ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)) và RECURSIVE-FFT của Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)). Các chương còn lại của Phần VII: [C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md), [C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md), [C32-so-khop-chuoi.md](C32-so-khop-chuoi.md), [C33-hinh-hoc-tinh-toan.md](C33-hinh-hoc-tinh-toan.md), [C34-np-day-du.md](C34-np-day-du.md), [C35-thuat-toan-xap-xi.md](C35-thuat-toan-xap-xi.md).
**Ý chính:** Tác giả muốn người đọc thấy rằng **chỉ cần thêm ba từ khoá — spawn, sync và parallel — vào mã giả tuần tự là mô tả được một thuật toán song song trên máy nhiều nhân bộ nhớ chung; hiệu năng của nó được đo bằng hai con số độc lập với máy là khối lượng công việc T₁ (work, thời gian chạy trên một bộ xử lý) và độ dài đường găng T∞ (span, thời gian chạy khi có vô hạn bộ xử lý); hai con số này cho cận dưới T_P ≥ max(T₁/P, T∞), và bất kỳ bộ lập lịch tham lam nào cũng đạt T_P ≤ T₁/P + T∞ — tức là trong phạm vi hệ số 2 của tối ưu, và gần tăng tốc tuyến tính hoàn hảo khi độ song song T₁/T∞ lớn hơn nhiều so với số bộ xử lý P. Vì vậy mục tiêu thiết kế là giữ khối lượng công việc bằng bản tuần tự tốt nhất và làm đường găng càng ngắn càng tốt.** Mục 27.1 xây mô hình qua ví dụ P-FIB: song song lồng nhau (spawn/sync), đồ thị tính toán (dag) gồm các mạch (strand) với bốn loại cạnh, máy tính song song lý tưởng có bộ nhớ nhất quán tuần tự, luật khối lượng công việc T_P ≥ T₁/P, luật đường găng T_P ≥ T∞, hệ số tăng tốc, độ song song, độ dư song song; Định lý 27.1 về lập lịch tham lam và hai hệ quả; quy tắc ghép nối tiếp (cộng span) và song song (lấy max span); vòng lặp **parallel for** được biên dịch thành cây chia đôi nên tốn thêm Θ(lg n) span; tranh chấp tất định (determinacy race) và câu chuyện chương trình cờ vua ★Socrates cho thấy "nhanh hơn trên 32 bộ xử lý" có thể "chậm hơn trên 512 bộ xử lý". Mục 27.2 song song hoá nhân ma trận: ba vòng lặp lồng (work Θ(n³), span Θ(n)), chia để trị tám phép nhân với ma trận tạm (span Θ(lg² n), độ song song Θ(n³/lg² n)) và Strassen (work Θ(n^lg 7), span Θ(lg² n)). Mục 27.3 song song hoá sắp xếp trộn: chỉ sinh nhánh hai lời gọi đệ quy thì độ song song chỉ Θ(lg n) vì MERGE tuần tự là nút cổ chai; trộn song song P-MERGE (lấy trung vị của mảng dài hơn, tìm nhị phân vị trí của nó trong mảng kia, đặt vào chỗ, đệ quy hai nửa song song) có work Θ(n), span Θ(lg² n); P-MERGE-SORT có work Θ(n lg n), span Θ(lg³ n), độ song song Θ(n/lg² n).

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong chương này.** Dấu sao chỉ có ở hai bài tập: Exercise 27.3-5 (song song hoá RANDOMIZED-SELECT) và Exercise 27.3-6 (song song hoá SELECT). Ký hiệu "★" trong tên chương trình cờ vua "★Socrates" (trang 790) là một phần của tên riêng, không phải dấu bài khó.
> - **Lớp chữ PDF hỏng nặng ký hiệu toán của chương, đã đọc lại từ ảnh trang:** "T1" của lớp chữ dùng chung cho cả T₁ (work) lẫn T∞ (span) — ký hiệu ∞ mất hoàn toàn, nên các công thức "T1=T1" thực ra là T₁/T∞; "‚.n/" là Θ(φⁿ) (ký hiệu φ mất); "PM1", "PMS1", "MS01", "M1" lẫn lộn chỉ số 1 và ∞; mọi dấu ≤, ≥, ≪ bị mất (ví dụ "TP T1=P" là T_P ≥ T₁/P); "˛" là α, "˝" là ⊗; "AŒq3" là A[q₃]; dòng 3 của P-MERGE mất chú thích "// ensure that n₁ ≥ n₂". Toàn bộ pseudocode, công thức (27.1)–(27.11), Định lý 27.1, Hệ quả 27.2–27.3 và Hình 27.1–27.6 trong bản tổng hợp này được đối chiếu với ảnh các trang 774–812. Hình 27.1, 27.2, 27.4, 27.5, 27.6 gần như không còn gì trong lớp chữ; người tổng hợp đọc trên ảnh và vẽ lại bằng sơ đồ text/bảng.
> - **Lỗi in và chỗ chưa chặt của sách (nhận xét của người tổng hợp):**
>   - Trang 800, lời giải thích dòng 10 của P-MERGE viết "all the elements in T[q₂ .. p₂] are at least as large as T[q₁]"; đúng phải là **T[q₂ .. r₂]**.
>   - Trang 774 thiếu chữ: "as well how the underlying concurrency platform…" (đúng: "as well as how"). Trang 790 "processsors" (thừa chữ s). Trang 792 "straighforward" (thiếu chữ t). Trang 795 "add the products from T into C in using…" (thừa chữ "in").
>   - Truy hồi (27.9) viết số hạng cộng thêm là O(lg n), nhưng dòng thế ngay sau lại viết Θ(lg n). Không ảnh hưởng kết luận.
>   - Phép thế cho FIB (trang 775–776) chỉ chứng minh T(n) ≤ aFₙ − b, tức là cận trên O(Fₙ); sách viết kết luận T(n) = Θ(Fₙ) mà không nêu cận dưới (cận dưới dễ: số lời gọi là 2Fₙ₊₁ − 1 ≥ Fₙ).
>   - Sách nói khi trộn lẫn lệnh của hai bộ xử lý trong RACE-EXAMPLE thì "most orderings produce correct results". Nếu đếm đều mọi cách xen kẽ hai chuỗi 3 lệnh thì có C(6, 3) = 20 cách, và chỉ **2** cách cho kết quả đúng 2 (một bộ xử lý làm xong hết rồi bộ kia mới đọc); 18 cách còn lại in ra 1. Câu của sách chỉ đúng theo nghĩa thực tế (ba lệnh của một bộ xử lý chạy rất sát nhau nên hiếm khi bị chen ngang), không đúng theo nghĩa đếm thứ tự.
>   - Sách gọi độ song song Θ(n^lg 7/lg² n) của Strassen đa luồng là "slightly less" so với Θ(n³/lg² n). Thực ra chênh lệch là một luỹ thừa của n (hệ số n^(3 − lg 7) ≈ n^0,19), tuy với n thực tế thì vẫn nhỏ.
>   - P-MERGE-SORT không xử lý trường hợp mảng rỗng (n = 0): khi đó dòng 5 cho q = p − 1, dòng 7 gọi lại chính bài toán rỗng và đệ quy không dừng. Thủ tục ngầm giả định n ≥ 1.
>   - Người tổng hợp không chắc những chỗ trên có nằm trong danh sách errata chính thức của ấn bản 3 hay không (không tra cứu).
> - **Các ví dụ chạy tay đã tự kiểm tra lại:** cây đệ quy FIB(6) có 25 nút (= 2F₇ − 1); dag P-FIB(4) có 17 mạch, đường găng 8 mạch, độ song song 17/8 = 2,125 (khớp sách); dag MAT-VEC-MAIN-LOOP(A, x, y, 8, 1, 8) có 7 · 3 + 8 = 29 mạch và đường găng 10 mạch; bảng giá trị x, r₁, r₂ của RACE-EXAMPLE khớp sách; ví dụ cờ vua: T₃₂ = 2048/32 + 1 = 65, T′₃₂ = 1024/32 + 8 = 40, T₅₁₂ = 4 + 1 = 5, T′₅₁₂ = 2 + 8 = 10 — đều khớp sách. Người tổng hợp tự chạy tay thêm P-MERGE trên ⟨2, 5, 8, 9⟩ và ⟨1, 6, 7⟩, P-SCAN-3 trên ⟨1, 2, 3, 4, 5⟩ và một lịch tham lam cho P-FIB(5) trên 3 bộ xử lý (phần Nội dung chi tiết và Bài tập).
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** chương này trở thành Chương 26 với tên "Parallel Algorithms"; mô hình được gọi là song song fork-join (fork-join parallelism), vẫn dùng các từ khoá spawn, sync và parallel for. Phần VII của ấn bản 4 có thêm hai chương mới là "Online Algorithms" và "Machine-Learning Algorithms", nên lời giới thiệu Phần VII cũng khác. Các chi tiết khác (ví dụ câu chuyện ★Socrates còn hay không, đánh số bài tập), người tổng hợp không nhớ chắc nên không liệt kê.

## Sơ đồ

### Phần VII — Giới thiệu (Part VII Selected Topics, Introduction, trang 768–771) — các chủ đề chọn lọc mở rộng phần trước

```text
       Phần VII gồm các chủ đề thuật toán chọn lọc, MỞ RỘNG và BỔ SUNG
       cho nội dung các phần trước
                                │
           ┌────────────────────┼─────────────────────┐
           ▼                    ▼                     ▼
   MÔ HÌNH TÍNH TOÁN MỚI   LĨNH VỰC CHUYÊN BIỆT    GIỚI HẠN CỦA THUẬT TOÁN
   (mạch, máy song song)   (hình học tính toán,    HIỆU QUẢ và cách đối phó
                            lý thuyết số…)          (hai chương cuối)
           │                    │                     │
           ▼                    ▼                     ▼
   Ch.27 Đa luồng động:    Ch.28 Ma trận: LU, LUP  Ch.34 NP-đầy đủ: cách
   work, span; nhân ma     giải hệ phương trình    chứng minh một bài toán
   trận, sắp xếp trộn      O(n³); nghịch đảo nhanh  NP-đầy đủ; chu trình
   song song               bằng nhân; bình phương  Hamilton, SAT, tổng tập
                           tối thiểu               con, người du lịch
   Ch.30 Đa thức và FFT:   Ch.29 Quy hoạch tuyến   Ch.35 Thuật toán xấp xỉ:
   nhân hai đa thức bậc n  tính: thuật toán đơn    phủ đỉnh (có/không
   trong O(n lg n); có     hình — không đa thức    trọng số), MAX-3-CNF,
   một mạch FFT song song  trong trường hợp xấu    người du lịch, phủ tập,
                           nhất nhưng hiệu quả     tổng tập con
                           trong thực tế
                           Ch.31 Lý thuyết số:
                           Euclid, phương trình
                           đồng dư, luỹ thừa mod,
                           RSA, Miller-Rabin,
                           rho của Pollard
                           Ch.32 So khớp chuỗi:
                           ngây thơ, Rabin-Karp,
                           ôtômat hữu hạn, KMP
                           Ch.33 Hình học tính
                           toán: quét để tìm giao
                           đoạn thẳng, bao lồi
                           (Graham, Jarvis), cặp
                           điểm gần nhất

       (Sách chỉ nêu ba nhóm chung chung; việc xếp từng chương vào nhóm
        là của người tổng hợp)
```

### Phần mở đầu chương (trước Mục 27.1, trang 772–774) — từ máy tuần tự sang máy song song bộ nhớ chung

```text
       Gần như mọi thuật toán của sách là THUẬT TOÁN TUẦN TỰ (serial):
       máy một bộ xử lý, mỗi lúc một lệnh
                                │
                                ▼
       Máy song song đã phổ biến, ở mọi tầm giá:
       · bộ đa xử lý trên chip (chip multiprocessor): một chip ĐA NHÂN,
         mỗi nhân là một bộ xử lý đầy đủ, dùng chung bộ nhớ
       · cụm máy (cluster): nhiều máy PC nối bằng mạng riêng
       · siêu máy tính: kiến trúc và mạng tự thiết kế
                                │
                                ▼
       Chưa có mô hình song song nào được chấp nhận rộng như máy RAM,
       vì các hãng không thống nhất kiến trúc:
       · BỘ NHỚ CHUNG (shared memory): mọi bộ xử lý đọc/ghi mọi ô nhớ
       · BỘ NHỚ PHÂN TÁN (distributed memory): bộ nhớ riêng, phải gửi
         thông điệp để đọc bộ nhớ của bộ xử lý khác
       Xu hướng (máy đa nhân): bộ nhớ chung — chương chọn hướng này
                                │
                                ▼
       ĐA LUỒNG TĨNH (static threading): luồng = "bộ xử lý ảo" dùng chung
       bộ nhớ, sống suốt quá trình tính; chia việc đều cho các luồng rất
       khó và dễ lỗi → ra đời NỀN TẢNG XỬ LÝ ĐỒNG THỜI (concurrency
       platform): lớp phần mềm điều phối, lập lịch, quản lý tài nguyên
                                │
                                ▼
       ĐA LUỒNG ĐỘNG (dynamic multithreading) — mô hình của chương:
       · người lập trình chỉ nêu SONG SONG LOGIC
       · bộ lập lịch của nền tảng tự cân bằng tải
       · hai tính năng: song song lồng nhau (spawn) và vòng lặp song song
                                │
                                ▼
       Ưu điểm của mô hình:
       · chỉ thêm 3 từ khoá parallel, spawn, sync; xoá chúng đi thì được
         BẢN TUẦN TỰ HOÁ (serialization) — mã giả tuần tự cùng bài toán
       · đo độ song song gọn gàng bằng "work" và "span"
       · hợp tự nhiên với chia để trị, phân tích bằng truy hồi
       · sát thực tế: Cilk, Cilk++, OpenMP, Task Parallel Library,
         Threading Building Blocks
                                │
                                ▼
       Lộ trình: 27.1 mô hình và các thước đo; 27.2 nhân ma trận đa luồng;
       27.3 sắp xếp trộn đa luồng (khó hơn)
```

### Mục 27.1 — Cơ bản về đa luồng động (The basics of dynamic multithreading, trang 774–792)

```text
       FIB(n) đệ quy: T(n) = T(n−1) + T(n−2) + Θ(1) = Θ(φⁿ)   (27.1)
       Hai lời gọi FIB(n−1), FIB(n−2) ĐỘC LẬP → có thể chạy song song
                                │
                                ▼
       P-FIB(n): x = spawn P-FIB(n−1); y = P-FIB(n−2); sync; return x + y
       · spawn: cha (parent) KHÔNG đợi con (child), được phép chạy tiếp
         song song — "được phép", không bắt buộc; bộ lập lịch quyết định
       · sync: đợi mọi con đã sinh nhánh xong; mọi thủ tục ngầm sync
         trước khi return
                                │
                                ▼
       MÔ HÌNH THỰC THI: đồ thị tính toán G = (V, E) là một dag
       · đỉnh = MẠCH (strand): chuỗi lệnh không chứa điều khiển song song
       · cạnh tiếp nối (ngang), cạnh sinh nhánh và cạnh gọi (xuống),
         cạnh trả về (lên); một mạch đầu, một mạch cuối
       · u, v NỐI TIẾP nếu có đường đi u ⇝ v; ngược lại là SONG SONG
       · máy song song lý tưởng: P bộ xử lý ngang sức, bộ nhớ NHẤT QUÁN
         TUẦN TỰ, bỏ qua chi phí lập lịch
                                │
                                ▼
       THƯỚC ĐO
       · WORK T₁ = tổng thời gian mọi mạch = thời gian trên 1 bộ xử lý
       · SPAN T∞ = đường dài nhất (đường găng) = thời gian với ∞ bộ xử lý
       · luật work: T_P ≥ T₁/P   (27.2);  luật span: T_P ≥ T∞   (27.3)
       · tăng tốc T₁/T_P ≤ P; tuyến tính nếu Θ(P), hoàn hảo nếu = P
       · ĐỘ SONG SONG T₁/T∞: tăng tốc tối đa có thể; P vượt nó thì không
         thể tăng tốc tuyến tính hoàn hảo
       · ĐỘ DƯ (slackness) (T₁/T∞)/P: < 1 thì không thể hoàn hảo
       Ví dụ P-FIB(4): 17 mạch, đường găng 8 → độ song song 2,125
                                │
                                ▼
       LẬP LỊCH THAM LAM: mỗi bước gán càng nhiều mạch sẵn sàng càng tốt
       · bước đầy (≥ P mạch sẵn sàng) ≤ ⌊T₁/P⌋ bước
       · bước không đầy: chạy mọi mạch sẵn sàng → span phần còn lại giảm 1
         → ≤ T∞ bước
       ⇒ Định lý 27.1: T_P ≤ T₁/P + T∞   (27.4)
       ⇒ Hệ quả 27.2: trong phạm vi hệ số 2 của lịch tối ưu
       ⇒ Hệ quả 27.3: P ≪ T₁/T∞ thì T_P ≈ T₁/P (tăng tốc ≈ P)
       Quy tắc kinh nghiệm: độ dư ≥ 10 là đủ
                                │
                                ▼
       PHÂN TÍCH: work = thời gian của bản tuần tự hoá;
       span: nối tiếp thì CỘNG, song song thì lấy MAX
       P-FIB: T₁ = Θ(φⁿ); T∞(n) = T∞(n−1) + Θ(1) = Θ(n); độ song song
       Θ(φⁿ/n) — rất lớn
                                │
                                ▼
       VÒNG LẶP SONG SONG (parallel for): trình biên dịch dựng cây chia
       đôi khoảng lặp bằng spawn/sync (MAT-VEC-MAIN-LOOP)
       · work tăng thêm không quá hằng số lần
       · span = Θ(lg n) + max_i span(lần lặp i)
       MAT-VEC: work Θ(n²), span Θ(n), độ song song Θ(n)
                                │
                                ▼
       TRANH CHẤP TẤT ĐỊNH: hai lệnh song song logic cùng truy cập một ô
       nhớ, ít nhất một lệnh ghi → kết quả tuỳ thứ tự (RACE-EXAMPLE có
       thể in 1 thay vì 2; MAT-VEC-WRONG sai). Quy ước: các mạch song
       song phải ĐỘC LẬP
                                │
                                ▼
       BÀI HỌC CỜ VUA (★Socrates): bản cũ T₁ = 2048, T∞ = 1; bản "tối ưu"
       T₁ = 1024, T∞ = 8. Trên 32 bộ xử lý: 65 s so với 40 s; trên 512:
       5 s so với 10 s → bỏ bản "tối ưu". Work và span dự báo tốt hơn
       thời gian đo được
```

### Mục 27.2 — Nhân ma trận đa luồng (Multithreaded matrix multiplication, trang 792–797)

```text
       P-SQUARE-MATRIX-MULTIPLY: song song hoá hai vòng ngoài (i, j),
       giữ vòng k tuần tự
       · work Θ(n³); span Θ(lg n) + Θ(lg n) + Θ(n) = Θ(n)
       · độ song song Θ(n²)
       (song song hoá cả vòng k bằng parallel for sẽ gây tranh chấp)
                                │
                                ▼
       CHIA ĐỂ TRỊ: chia A, B, C thành 4 khối n/2 × n/2   (27.6)
       C = [A₁₁B₁₁ A₁₁B₁₂; A₂₁B₁₁ A₂₁B₁₂] + [A₁₂B₂₁ A₁₂B₂₂; A₂₂B₂₁ A₂₂B₂₂]
       P-MATRIX-MULTIPLY-RECURSIVE(C, A, B):
       · 4 tích đầu ghi vào C, 4 tích sau ghi vào ma trận tạm T
       · 7 lời gọi sinh nhánh + 1 lời gọi thường, sync
       · cộng T vào C bằng hai vòng parallel for lồng nhau
                                │
                                ▼
       work M₁(n) = 8M₁(n/2) + Θ(n²) = Θ(n³)  (trường hợp 1 định lý thợ)
       span M∞(n) = M∞(n/2) + Θ(lg n) = Θ(lg² n)   (27.7, Bài tập 4.6-2)
       độ song song Θ(n³/lg² n) — rất cao
                                │
                                ▼
       STRASSEN ĐA LUỒNG
       1. chia khối: Θ(1) work và span
       2. tạo S₁..S₁₀ bằng parallel for: work Θ(n²), span Θ(lg n)
       3. sinh nhánh 7 tích đệ quy P₁..P₇
       4. ghép C₁₁, C₁₂, C₂₁, C₂₂ bằng parallel for: Θ(n²), Θ(lg n)
       work Θ(n^lg 7); span cùng truy hồi (27.7) = Θ(lg² n);
       độ song song Θ(n^lg 7 / lg² n)
```

### Mục 27.3 — Sắp xếp trộn đa luồng (Multithreaded merge sort, trang 797–805)

```text
       MERGE-SORT′: chỉ sinh nhánh lời gọi đệ quy đầu, rồi sync, rồi
       gọi MERGE tuần tự
       · work MS′₁(n) = 2MS′₁(n/2) + Θ(n) = Θ(n lg n)
       · span MS′∞(n) = MS′∞(n/2) + Θ(n) = Θ(n)
       · độ song song chỉ Θ(lg n) — nút cổ chai là MERGE tuần tự
                                │
                                ▼
       TRỘN SONG SONG P-MERGE(T, p₁, r₁, p₂, r₂, A, p₃)
       (giả sử n₁ ≥ n₂, đổi chỗ nếu cần)
       1. x = T[q₁], q₁ = ⌊(p₁+r₁)/2⌋ — trung vị của mảng DÀI hơn
       2. q₂ = BINARY-SEARCH(x, T, p₂, r₂): chỗ chèn x vào mảng kia
       3. q₃ = p₃ + (q₁ − p₁) + (q₂ − p₂); A[q₃] = x
       4. song song: trộn T[p₁..q₁−1] với T[p₂..q₂−1] vào A[p₃..q₃−1]
                     trộn T[q₁+1..r₁] với T[q₂..r₂]   vào A[q₃+1..r₃]
                                │
                                ▼
       Mỗi lời gọi đệ quy nhận ≤ 3n/4 phần tử (vì n₂ ≤ n/2)
       · span PM∞(n) = PM∞(3n/4) + Θ(lg n) = Θ(lg² n)   (27.8)
       · work PM₁(n) = PM₁(αn) + PM₁((1−α)n) + O(lg n), 1/4 ≤ α ≤ 3/4
         (27.9); thế PM₁(n) ≤ c₁n − c₂ lg n ⇒ Θ(n)
       · độ song song Θ(n/lg² n)
                                │
                                ▼
       P-MERGE-SORT(A, p, r, B, s): sắp hai nửa song song vào mảng tạm
       T[1..n], sync, P-MERGE vào B[s..s+r−p]
       · work PMS₁(n) = 2PMS₁(n/2) + Θ(n) = Θ(n lg n)
       · span PMS∞(n) = PMS∞(n/2) + Θ(lg² n) = Θ(lg³ n)   (27.10)
       · độ song song Θ(n/lg² n) — tốt hơn hẳn Θ(lg n)
       Thực tế: gộp trường hợp cơ sở (chuyển sang sắp xếp tuần tự khi
       mảng đủ nhỏ) để giảm hằng số
```

### Bài toán cuối chương (Problems 27-1 đến 27-6, trang 805–811)

```text
       27-1 Cài vòng lặp song song bằng song song lồng nhau:
            SUM-ARRAYS; chia đôi đệ quy cho span Θ(lg n); sinh nhánh tuần
            tự từng khối kích thước grain-size cho span Θ(n/g + g),
            tốt nhất g = √n
                                │
                                ▼
       27-2 Bỏ ma trận tạm trong nhân ma trận: tính C = C + AB, sync
            giữa hai đợt 4 phép nhân; span tăng lên Θ(n), độ song song
            Θ(n²) — với n = 1000 vẫn khoảng 10⁶
                                │
                                ▼
       27-3 Song song hoá LU-DECOMPOSITION, LUP-DECOMPOSITION, LUP-SOLVE
            và nghịch đảo ma trận đối xứng xác định dương (Chương 28)
                                │
                                ▼
       27-4 Phép rút gọn ⊗ (reduction) và tính tiền tố ⊗ (scan):
            P-REDUCE Θ(n)/Θ(lg n); P-SCAN-1 (work Θ(n²)), P-SCAN-2
            (Θ(n lg n), Θ(lg² n)), P-SCAN-3 hai lượt lên/xuống
            (Θ(n), Θ(lg n))
                                │
                                ▼
       27-5 Tính toán khuôn (stencil) đơn giản: ô A[i, j] phụ thuộc ô
            trên/trái; chia 2×2 cho span Θ(n^lg 3); chia b×b vẫn chỉ
            o(n) song song; đi theo đường chéo cho Θ(n/lg n)
                                │
                                ▼
       27-6 Thuật toán đa luồng ngẫu nhiên: luật work/span và cận tham
            lam theo kỳ vọng; tăng tốc nên định nghĩa E[T₁]/E[T_P];
            P-RANDOMIZED-QUICKSORT
```

### Ghi chú chương (Chapter notes, trang 811–812)

```text
       Máy song song và mô hình lập trình song song đã có từ lâu; các ấn
       bản trước của sách trình bày mạng sắp xếp và mô hình PRAM; mô
       hình song song dữ liệu là một mô hình phổ biến khác
                                │
                                ▼
       Graham và Brent: tồn tại bộ lập lịch đạt cận Định lý 27.1;
       Eager, Zahorjan, Lazowska: MỌI bộ lập lịch tham lam đều đạt, và đề
       xuất phân tích bằng work/span (chưa gọi tên như vậy);
       Blelloch: mô hình work/"depth" cho song song dữ liệu
                                │
                                ▼
       Blumofe và Leiserson: lập lịch phân tán "đánh cắp việc"
       (work-stealing) ngẫu nhiên đạt E[T_P] ≤ T₁/P + O(T∞); thêm Arora,
       Blumofe, Plaxton và Blelloch, Gibbons, Matias
                                │
                                ▼
       Mã giả và mô hình lấy cảm hứng từ Cilk (MIT) và Cilk++ (Cilk
       Arts); nhiều thuật toán từ ghi chép bài giảng của Leiserson và
       Prokop; trộn song song lấy ý từ Akl; nhất quán tuần tự là của
       Lamport
```

## Ba câu hỏi chương này trả lời

1. **Làm sao mô tả một thuật toán song song mà không phải lo luồng, khoá và chia việc, và làm sao đo được nó "song song" đến đâu?** Dùng mô hình đa luồng động: thêm từ khoá **spawn** trước một lời gọi để cho phép thủ tục cha chạy tiếp song song với con, **sync** để đợi mọi con xong, và **parallel for** để cho các lần lặp chạy đồng thời; xoá ba từ khoá đi thì được bản tuần tự hoá giải cùng bài toán. Một lần chạy được xem như một dag các mạch (strand). Hai thước đo: khối lượng công việc T₁ (work) là tổng thời gian mọi mạch, độ dài đường găng T∞ (span) là thời gian của đường dài nhất trong dag. Độ song song là T₁/T∞. Ví dụ P-FIB(4): 17 mạch, đường găng 8 mạch, độ song song 17/8 = 2,125 — dù có bao nhiêu bộ xử lý cũng không chạy nhanh hơn khoảng 2 lần. Còn P-FIB(n) tổng quát có T₁ = Θ(φⁿ), T∞ = Θ(n), độ song song Θ(φⁿ/n); với n = 30 (theo cách đếm mạch của người tổng hợp) là khoảng 5,39 triệu mạch trên đường găng 60 mạch, độ song song gần 90.000.
2. **Với P bộ xử lý, thuật toán chạy nhanh đến đâu?** Không nhanh hơn T₁/P (luật work, mỗi bước P bộ xử lý chỉ làm được P đơn vị việc) và không nhanh hơn T∞ (luật span). Bộ lập lịch tham lam — mỗi bước chạy min(P, số mạch sẵn sàng) mạch — đạt T_P ≤ T₁/P + T∞ (Định lý 27.1): số bước đầy không quá ⌊T₁/P⌋, số bước không đầy không quá T∞ vì mỗi bước không đầy chạy hết các mạch sẵn sàng nên rút ngắn đường găng còn lại đúng 1. Từ đó lịch tham lam không tệ hơn 2 lần lịch tối ưu, và khi độ dư (T₁/T∞)/P lớn (quy tắc kinh nghiệm: ≥ 10) thì T_P ≈ T₁/P, tăng tốc gần P. Ví dụ ★Socrates: với T₁ = 2048, T∞ = 1 thì T₅₁₂ ≈ 2048/512 + 1 = 5 giây; bản "tối ưu" T₁ = 1024, T∞ = 8 nhanh hơn trên 32 bộ xử lý (40 so với 65 giây) nhưng chậm gấp đôi trên 512 bộ xử lý (10 so với 5 giây).
3. **Song song hoá nhân ma trận và sắp xếp trộn được đến mức nào?** Nhân ma trận: song song hai vòng ngoài cho span Θ(n) và độ song song Θ(n²); chia để trị tám phép nhân con chạy song song rồi cộng bằng parallel for cho span M∞(n) = M∞(n/2) + Θ(lg n) = Θ(lg² n), độ song song Θ(n³/lg² n) (với n = 1000, bỏ hằng số, khoảng 10⁹/10² = 10⁷); Strassen đa luồng giữ work Θ(n^lg 7) với cùng span Θ(lg² n). Sắp xếp trộn: chỉ chạy song song hai lời gọi đệ quy thì span vẫn Θ(n) vì MERGE tuần tự, độ song song chỉ Θ(lg n) (khoảng 23 với 10 triệu phần tử). Phải song song hoá chính phép trộn: P-MERGE lấy trung vị x của mảng dài hơn, tìm nhị phân chỗ của x trong mảng kia, đặt x vào đúng vị trí đầu ra và trộn hai phần nhỏ song song; mỗi phần không quá 3n/4 phần tử nên span Θ(lg² n), work Θ(n). P-MERGE-SORT khi đó có work Θ(n lg n), span Θ(lg³ n), độ song song Θ(n/lg² n) (khoảng 18.500 với 10 triệu phần tử, bỏ hằng số).

## Khái niệm cần biết

- **Thuật toán tuần tự và thuật toán song song (serial / parallel algorithm):** thuật toán tuần tự chạy trên máy một bộ xử lý, mỗi lúc một lệnh (mô hình RAM của Chương 2); thuật toán song song chạy trên máy nhiều bộ xử lý, cho phép nhiều lệnh thực hiện đồng thời. Ví dụ: cộng 8 số tuần tự cần 7 phép cộng nối nhau; song song theo cây nhị phân cần 3 tầng (4 phép, rồi 2, rồi 1). Đây là chuyển dịch mô hình của cả chương.
- **Bộ nhớ chung và bộ nhớ phân tán (shared / distributed memory):** bộ nhớ chung: mọi bộ xử lý đọc/ghi trực tiếp mọi ô nhớ (máy tính xách tay đa nhân); bộ nhớ phân tán: mỗi bộ xử lý có bộ nhớ riêng, muốn đọc bộ nhớ của bộ xử lý khác phải gửi thông điệp (cụm máy). Chương chỉ xét bộ nhớ chung.
- **Đa luồng tĩnh (static threading) và nền tảng xử lý đồng thời (concurrency platform):** đa luồng tĩnh cho người lập trình các luồng (thread) — "bộ xử lý ảo" có bộ đếm chương trình riêng, dùng chung bộ nhớ, thường sống suốt quá trình tính vì tạo/huỷ luồng chậm. Chia việc đều cho các luồng rất khó, nên người ta xây nền tảng xử lý đồng thời: lớp phần mềm điều phối, lập lịch và quản lý tài nguyên song song (thư viện thời gian chạy hoặc ngôn ngữ có trình biên dịch riêng).
- **Đa luồng động (dynamic multithreading):** loại nền tảng xử lý đồng thời mà người lập trình chỉ nêu chỗ nào *có thể* song song (song song logic), còn bộ lập lịch của nền tảng tự cân bằng tải. Hầu hết hỗ trợ hai tính năng: song song lồng nhau và vòng lặp song song. Ví dụ các nền tảng sách kể: Cilk, Cilk++, OpenMP, Task Parallel Library, Threading Building Blocks.
- **spawn, sync, song song lồng nhau (nested parallelism):** "x = spawn P-FIB(n − 1)" cho phép thủ tục cha (parent) chạy tiếp dòng sau song song với con (child) thay vì đợi. sync bắt thủ tục đợi mọi con đã sinh nhánh hoàn tất; mọi thủ tục ngầm thực hiện sync trước khi trả về. Ví dụ: trong P-FIB(n), không có sync ở dòng 5 thì "return x + y" có thể cộng khi x chưa được tính. Song song lồng nhau là khi từ khoá spawn đứng trước một lời gọi thủ tục, và vì đệ quy, các con lại sinh nhánh tiếp, tạo cây tính toán lớn.
- **Song song logic và bộ lập lịch (logical parallelism, scheduler):** từ khoá chỉ nói phần nào *được phép* chạy song song; lúc chạy, bộ lập lịch quyết định phần nào thực sự chạy đồng thời bằng cách gán cho các bộ xử lý rảnh. Ví dụ: chạy P-FIB trên 1 bộ xử lý thì không có gì chạy đồng thời, kết quả vẫn đúng.
- **Bản tuần tự hoá (serialization):** thuật toán tuần tự thu được khi xoá spawn, sync và parallel. Bản tuần tự hoá của P-FIB chính là FIB. Quan trọng vì work của thuật toán đa luồng bằng thời gian chạy của bản tuần tự hoá.
- **Đồ thị tính toán (computation dag) và mạch (strand):** một lần chạy chương trình đa luồng được xem là dag G = (V, E). Về khái niệm đỉnh là lệnh, cạnh (u, v) nghĩa là u phải chạy trước v; để gọn, mỗi chuỗi lệnh liên tiếp không chứa điều khiển song song (spawn, sync, trả về từ một lần spawn) được gộp thành một **mạch**. Ví dụ: mỗi lần gọi P-FIB(n) với n ≥ 2 gồm 3 mạch — từ đầu tới spawn ở dòng 3; từ dòng 4 tới sync; sau sync tới return — còn lời gọi trường hợp cơ sở là 1 mạch. P-FIB(4) có 4 lời gọi không cơ sở và 5 lời gọi cơ sở: 4 · 3 + 5 = 17 mạch.
- **Bốn loại cạnh của dag:** cạnh tiếp nối (continuation edge) (u, u′) nối mạch u với mạch kế tiếp trong cùng lời gọi (vẽ ngang); cạnh sinh nhánh (spawn edge) (u, v) khi u sinh nhánh v (vẽ xuống); cạnh gọi (call edge) cho lời gọi thường (vẽ xuống); cạnh trả về (return edge) (u, x) từ mạch cuối của con lên mạch x ngay sau sync kế tiếp của cha (vẽ lên). Khác biệt giữa spawn và gọi: spawn tạo thêm cạnh tiếp nối từ u sang u′, cho phép u′ chạy cùng lúc với v; lời gọi thường thì không.
- **Nối tiếp và song song logic giữa hai mạch (in series / in parallel):** u và v nối tiếp nếu dag có đường đi có hướng từ u tới v (hoặc ngược lại); không có đường nào thì chúng song song. Ví dụ trong P-FIB(4): mạch của P-FIB(1) do P-FIB(2) sinh nhánh và mạch của P-FIB(0) do chính P-FIB(2) đó gọi là song song.
- **Máy tính song song lý tưởng (ideal parallel computer) và nhất quán tuần tự (sequential consistency):** gồm các bộ xử lý ngang sức và bộ nhớ chung nhất quán tuần tự — kết quả như thể mỗi bước chỉ một lệnh của một bộ xử lý được thực hiện, theo một thứ tự tuyến tính giữ đúng thứ tự riêng của từng bộ xử lý (với đa luồng động: giữ đúng thứ tự bộ phận của dag). Mô hình bỏ qua chi phí lập lịch.
- **Khối lượng công việc T₁ (work):** tổng thời gian chạy mọi mạch, cũng là thời gian chạy trên một bộ xử lý. Với dag mỗi mạch tốn một đơn vị thời gian, work là số đỉnh. Ví dụ P-FIB(4): T₁ = 17.
- **Độ dài đường găng T∞ (span) và đường găng (critical path):** thời gian dài nhất để chạy các mạch dọc theo một đường đi trong dag; với mạch đơn vị là số đỉnh trên đường dài nhất (đường găng). Cũng là thời gian chạy khi có vô hạn bộ xử lý. Ví dụ P-FIB(4): T∞ = 8. Đường găng của dag tìm được trong Θ(V + E) (Mục 24.2).
- **T_P, luật work và luật span:** T_P là thời gian chạy trên P bộ xử lý. Luật work: T_P ≥ T₁/P (27.2) vì mỗi bước P bộ xử lý làm tối đa P đơn vị việc. Luật span: T_P ≥ T∞ (27.3) vì máy vô hạn bộ xử lý có thể giả lập máy P bộ xử lý. Ví dụ P-FIB(4) trên 2 bộ xử lý: T₂ ≥ max(17/2, 8) = 8,5, tức ít nhất 9 bước.
- **Hệ số tăng tốc (speedup):** T₁/T_P; theo luật work không vượt P. Tăng tốc tuyến tính (linear speedup) khi T₁/T_P = Θ(P); tăng tốc tuyến tính hoàn hảo (perfect linear speedup) khi T₁/T_P = P. Ví dụ: T₁ = 2048, T₃₂ = 65 thì tăng tốc 31,5 trên 32 bộ xử lý.
- **Độ song song (parallelism):** T₁/T∞. Ba cách nhìn: lượng việc trung bình có thể làm song song ở mỗi bước dọc đường găng; tăng tốc tối đa với bất kỳ số bộ xử lý nào; giới hạn để còn có thể tăng tốc tuyến tính hoàn hảo — P vượt độ song song thì T₁/T_P ≤ T₁/T∞ < P. Ví dụ: chương trình ★Socrates bản gốc có độ song song 2048/1 = 2048, bản "tối ưu" chỉ 1024/8 = 128.
- **Độ dư song song (parallel slackness):** (T₁/T∞)/P = T₁/(P·T∞), số lần độ song song vượt số bộ xử lý. Nhỏ hơn 1 thì không thể tăng tốc tuyến tính hoàn hảo; càng lớn hơn 1 thì bộ lập lịch tốt càng tiến gần tăng tốc hoàn hảo. Ví dụ: độ song song 128 trên 512 bộ xử lý cho độ dư 0,25.
- **Bộ lập lịch trực tuyến, phân tán, tập trung (on-line, distributed, centralized scheduler):** bộ lập lịch phải trực tuyến — không biết trước khi nào mạch được sinh hay kết thúc. Bộ lập lịch tốt trong thực tế là phân tán (các luồng cùng nhau cân bằng tải); để phân tích đơn giản, chương xét bộ lập lịch tập trung, biết toàn bộ trạng thái tính toán.
- **Bộ lập lịch tham lam, bước đầy, bước không đầy (greedy scheduler, complete step, incomplete step):** mỗi bước gán càng nhiều mạch sẵn sàng cho bộ xử lý càng tốt. Bước có ít nhất P mạch sẵn sàng là bước đầy (chạy P mạch bất kỳ); bước có ít hơn P mạch sẵn sàng là bước không đầy (chạy hết). Ví dụ P = 3, có 5 mạch sẵn sàng: bước đầy, chạy 3 trong 5.
- **Quy tắc ghép work và span (Hình 27.3):** hai phần tính A, B ghép nối tiếp: T₁(A ∪ B) = T₁(A) + T₁(B), T∞(A ∪ B) = T∞(A) + T∞(B). Ghép song song: work vẫn cộng, nhưng T∞(A ∪ B) = max(T∞(A), T∞(B)). Ví dụ: A có (work 10, span 4), B có (work 6, span 5): nối tiếp cho (16, 9), song song cho (16, 5).
- **Vòng lặp song song (parallel for) và gộp lá (coarsening):** "parallel for" cho phép các lần lặp chạy đồng thời; trình biên dịch cài nó bằng thủ tục chia đôi khoảng lặp đệ quy với spawn/sync (cây nhị phân, lá là từng lần lặp). Span của vòng n lần lặp là Θ(lg n) + max_i span(lần lặp i). Gộp lá là cho mỗi lá chạy nhiều lần lặp để giảm chi phí sinh nhánh, đổi lại giảm độ song song. Ví dụ: vòng khởi tạo y_i = 0 với n = 1024 có span khoảng lg 1024 = 10 tầng sinh nhánh.
- **Tất định, không tất định và tranh chấp tất định (deterministic, nondeterministic, determinacy race):** thuật toán tất định luôn làm cùng một việc trên cùng đầu vào dù lập lịch thế nào. Tranh chấp tất định xảy ra khi hai lệnh song song logic cùng truy cập một ô nhớ và ít nhất một lệnh ghi. Ví dụ RACE-EXAMPLE: hai lần lặp song song cùng làm x = x + 1 từ x = 0, có thể in 1 thay vì 2. Chương quy ước các mạch song song phải **độc lập** (không tranh chấp).
- **Ma trận khối và Strassen (nhắc lại từ Chương 4):** chia ma trận n × n thành bốn khối n/2 × n/2; tích khối dùng 8 phép nhân khối, Strassen dùng 7 phép nhân khối cùng 18 phép cộng/trừ khối nên chạy Θ(n^lg 7) ≈ Θ(n^2,81). Quan trọng vì Mục 27.2 song song hoá chính các thuật toán này.
- **Trộn song song (parallel merging):** trộn hai mảng đã sắp xếp bằng chia để trị: chọn trung vị x của mảng dài hơn, tìm nhị phân chỗ của x trong mảng ngắn hơn, đặt x vào đúng chỗ đầu ra, trộn hai cặp nửa nhỏ song song. Ví dụ: trộn ⟨2, 5, 8, 9⟩ với ⟨1, 6, 7⟩: x = 5, chỗ chèn trong mảng kia là trước 6, nên 5 đứng thứ 3 đầu ra; cặp bên trái là ⟨2⟩ với ⟨1⟩, cặp bên phải là ⟨8, 9⟩ với ⟨6, 7⟩.
- **Rút gọn ⊗ và tính tiền tố ⊗ (⊗-reduction, ⊗-prefix computation / ⊗-scan), Problem 27-4:** với ⊗ là phép kết hợp (associative), rút gọn là x[1] ⊗ x[2] ⊗ … ⊗ x[n]; tính tiền tố là mảng y với y[i] = x[1] ⊗ … ⊗ x[i]. Ví dụ ⊗ = + và x = ⟨1, 2, 3, 4, 5⟩: rút gọn là 15, tiền tố là ⟨1, 3, 6, 10, 15⟩.
- **Khuôn tính toán (stencil), Problem 27-5:** mẫu cố định các ô lân cận mà giá trị một ô phụ thuộc vào. Ví dụ LCS (Mục 15.4): c[i, j] phụ thuộc c[i − 1, j], c[i, j − 1], c[i − 1, j − 1].

## Nội dung chi tiết

### 1. Lời giới thiệu Phần VII "Các chủ đề chọn lọc" (Part VII Selected Topics — Introduction, trang 768–771)

Trang 768 là trang tên phần "VII Selected Topics"; trang 767 trước đó để trắng. Lời giới thiệu (trang 769–771) nói Phần VII chứa một tuyển chọn các chủ đề thuật toán mở rộng và bổ sung cho nội dung trước. Một số chương đưa vào **mô hình tính toán mới** như mạch (circuit) hay máy tính song song; một số chương đi vào **lĩnh vực chuyên biệt** như hình học tính toán hay lý thuyết số; **hai chương cuối** bàn một số giới hạn đã biết của việc thiết kế thuật toán hiệu quả và giới thiệu kỹ thuật đối phó với các giới hạn đó. Sau đó tác giả tóm tắt từng chương:

| Chương | Nội dung theo lời giới thiệu |
|---|---|
| 27 — Thuật toán đa luồng ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)) | Một mô hình thuật toán cho tính toán song song dựa trên đa luồng động; cơ bản về mô hình, cách định lượng độ song song bằng hai thước đo work và span; một số thuật toán đa luồng thú vị, trong đó có nhân ma trận và sắp xếp trộn. |
| 28 — Phép toán ma trận ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)) | Thuật toán hiệu quả trên ma trận: hai phương pháp tổng quát — phân tích LU và phân tích LUP — để giải hệ phương trình tuyến tính bằng khử Gauss trong O(n³); chứng minh nghịch đảo ma trận và nhân ma trận nhanh như nhau; cuối chương là cách tính nghiệm xấp xỉ bình phương tối thiểu khi hệ không có nghiệm đúng. |
| 29 — Quy hoạch tuyến tính ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)) | Cực đại hoá hoặc cực tiểu hoá một mục tiêu với tài nguyên hạn chế và các ràng buộc cạnh tranh; xuất hiện trong nhiều ứng dụng thực tế. Chương trình bày cách mô hình hoá và giải bài toán quy hoạch tuyến tính bằng thuật toán đơn hình (simplex) — thuật toán lâu đời nhất cho bài toán này. Khác nhiều thuật toán trong sách, đơn hình không chạy thời gian đa thức trong trường hợp xấu nhất, nhưng khá hiệu quả và dùng rộng rãi trong thực tế. |
| 30 — Đa thức và FFT ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)) | Các phép toán trên đa thức; dùng một kỹ thuật xử lý tín hiệu nổi tiếng là biến đổi Fourier nhanh (FFT) để nhân hai đa thức bậc n trong O(n lg n); các cài đặt hiệu quả của FFT, trong đó có một mạch song song. |
| 31 — Thuật toán số học ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)) | Ôn lý thuyết số sơ cấp; thuật toán Euclid tính ước chung lớn nhất; giải phương trình tuyến tính đồng dư; luỹ thừa một số theo modulo số khác; ứng dụng quan trọng là hệ mật mã khoá công khai RSA (vừa mã hoá để đối thủ không đọc được, vừa tạo chữ ký số); phép kiểm tra nguyên tố ngẫu nhiên Miller-Rabin để tìm số nguyên tố lớn hiệu quả — điều kiện thiết yếu cho RSA; cuối cùng là heuristic "rho" của Pollard để phân tích số nguyên ra thừa số và tình hình hiện tại của bài toán phân tích số nguyên. |
| 32 — So khớp chuỗi ([C32-so-khop-chuoi.md](C32-so-khop-chuoi.md)) | Tìm mọi lần xuất hiện của một chuỗi mẫu trong một văn bản — bài toán thường gặp trong trình soạn thảo văn bản. Sau cách ngây thơ là cách tiếp cận đẹp của Rabin và Karp; sau lời giải hiệu quả dựa trên ôtômat hữu hạn là thuật toán Knuth-Morris-Pratt, sửa thuật toán ôtômat để tiết kiệm bộ nhớ nhờ tiền xử lý mẫu khéo léo. |
| 33 — Hình học tính toán ([C33-hinh-hoc-tinh-toan.md](C33-hinh-hoc-tinh-toan.md)) | Các thao tác cơ bản của hình học tính toán; phương pháp "quét" để xác định hiệu quả một tập đoạn thẳng có cặp nào cắt nhau không; hai thuật toán khéo tìm bao lồi của tập điểm — quét Graham và hành quân Jarvis — cũng minh hoạ sức mạnh của phương pháp quét; cuối chương là thuật toán hiệu quả tìm cặp điểm gần nhau nhất trong mặt phẳng. |
| 34 — NP-đầy đủ ([C34-np-day-du.md](C34-np-day-du.md)) | Nhiều bài toán tính toán thú vị là NP-đầy đủ, và chưa biết thuật toán thời gian đa thức nào cho bất kỳ bài toán nào trong số đó. Chương trình bày kỹ thuật xác định khi nào một bài toán là NP-đầy đủ, chứng minh một số bài toán kinh điển là NP-đầy đủ: đồ thị có chu trình Hamilton không, công thức boolean có thoả được không, một tập số có tập con với tổng bằng giá trị đích không; và chứng minh bài toán người du lịch nổi tiếng là NP-đầy đủ. |
| 35 — Thuật toán xấp xỉ ([C35-thuat-toan-xap-xi.md](C35-thuat-toan-xap-xi.md)) | Tìm hiệu quả nghiệm xấp xỉ cho bài toán NP-đầy đủ. Với một số bài toán, nghiệm gần tối ưu khá dễ có; với bài toán khác, thuật toán xấp xỉ tốt nhất đã biết càng kém khi kích thước bài toán tăng; lại có bài toán cho phép đầu tư thêm thời gian tính để có nghiệm xấp xỉ ngày càng tốt. Minh hoạ bằng bài toán phủ đỉnh (bản không trọng số và có trọng số), phiên bản tối ưu hoá của tính thoả được 3-CNF, bài toán người du lịch, bài toán phủ tập và bài toán tổng tập con. |

Nhận xét của người tổng hợp: Phần VII không có một "lập luận chung" như các phần trước (Phần II về sắp xếp, Phần VI về đồ thị); các chương gần như độc lập, chỉ có cặp 34–35 nối tiếp nhau và Chương 27 có bài toán cuối chương nhắm tới Chương 28 và 30. Lời giới thiệu ngắn (khoảng hai trang), chủ yếu là mục lục có chú giải.

### 2. Phần mở đầu chương (trang 772–774)

**Từ tuần tự sang song song.** Phần lớn thuật toán trong sách là **thuật toán tuần tự** (serial algorithm), hợp với máy một bộ xử lý chỉ thực hiện một lệnh mỗi lúc. Chương này mở rộng mô hình thuật toán sang **thuật toán song song** (parallel algorithm), chạy trên máy đa xử lý cho phép nhiều lệnh thực hiện đồng thời; cụ thể là mô hình đẹp của thuật toán đa luồng động, vừa dễ thiết kế và phân tích, vừa cài đặt hiệu quả được trong thực tế.

**Máy song song ở mọi tầm giá.** Máy tính song song — máy có nhiều đơn vị xử lý — ngày càng phổ biến. Máy để bàn và máy xách tay khá rẻ chứa **bộ đa xử lý trên chip** (chip multiprocessor): một chip mạch tích hợp **đa nhân** (multicore) chứa nhiều "nhân" xử lý, mỗi nhân là một bộ xử lý đầy đủ truy cập bộ nhớ chung. Ở tầm giá/hiệu năng trung bình là các **cụm máy** (cluster) ghép từ các máy riêng — thường là máy cỡ PC đơn giản — nối bằng mạng riêng. Đắt nhất là **siêu máy tính**, thường kết hợp kiến trúc và mạng tự thiết kế để đạt hiệu năng cao nhất tính theo số lệnh mỗi giây.

**Vì sao chưa có "máy RAM song song".** Máy đa xử lý đã có hàng chục năm, nhưng trong khi cộng đồng sớm thống nhất mô hình máy truy cập ngẫu nhiên (RAM) cho tính toán tuần tự, chưa có mô hình tính toán song song nào được chấp nhận rộng như vậy. Lý do chính: các hãng chưa thống nhất một kiến trúc. Có máy dùng **bộ nhớ chung** (shared memory) — mỗi bộ xử lý truy cập trực tiếp mọi ô nhớ; có máy dùng **bộ nhớ phân tán** (distributed memory) — bộ nhớ của mỗi bộ xử lý là riêng, muốn truy cập bộ nhớ của bộ xử lý khác phải gửi thông điệp tường minh. Với công nghệ đa nhân, mọi máy xách tay và máy để bàn mới đều là máy song song bộ nhớ chung, và xu hướng có vẻ nghiêng về đa xử lý bộ nhớ chung. "Thời gian sẽ trả lời", nhưng đó là hướng chương chọn.

**Đa luồng tĩnh và khó khăn của nó.** Một cách lập trình thông dụng cho bộ đa xử lý trên chip và máy bộ nhớ chung khác là **đa luồng tĩnh** (static threading): phần mềm cung cấp trừu tượng "bộ xử lý ảo" gọi là **luồng** (thread), dùng chung bộ nhớ. Mỗi luồng có bộ đếm chương trình riêng và chạy mã độc lập với các luồng khác. Hệ điều hành nạp luồng lên bộ xử lý và thay ra khi luồng khác cần chạy. Hệ điều hành cho phép tạo và huỷ luồng nhưng các thao tác này tương đối chậm, nên với đa số ứng dụng, luồng tồn tại suốt quá trình tính — vì thế gọi là "tĩnh". Lập trình trực tiếp bằng luồng tĩnh khó và dễ lỗi: một lý do là chia việc động cho các luồng sao cho mỗi luồng nhận tải xấp xỉ nhau rất phức tạp; với ứng dụng không tầm thường, người lập trình phải dùng giao thức liên lạc phức tạp để cài một bộ lập lịch cân bằng tải. Tình hình đó dẫn tới các **nền tảng xử lý đồng thời** (concurrency platform): lớp phần mềm điều phối, lập lịch và quản lý tài nguyên tính toán song song. Có nền tảng là thư viện thời gian chạy (runtime library), có nền tảng là ngôn ngữ song song đầy đủ với trình biên dịch và hỗ trợ thời gian chạy.

**Lập trình đa luồng động (Dynamic multithreaded programming).** Một lớp nền tảng quan trọng là **đa luồng động** (dynamic multithreading) — mô hình của chương. Nó cho phép người lập trình nêu độ song song của ứng dụng mà không phải lo giao thức liên lạc, cân bằng tải và những phiền toái khác của luồng tĩnh. Nền tảng chứa một **bộ lập lịch** tự động cân bằng tải, làm việc của người lập trình đơn giản hẳn. Chức năng của các môi trường đa luồng động còn đang phát triển, nhưng hầu như đều hỗ trợ hai tính năng: **song song lồng nhau** (nested parallelism) — cho phép "sinh nhánh" (spawn) một chương trình con, để bên gọi chạy tiếp trong khi chương trình con tính kết quả; và **vòng lặp song song** (parallel loop) — như vòng for thường nhưng các lần lặp có thể chạy đồng thời. Hai tính năng này là nền của mô hình trong chương. Điểm then chốt: người lập trình chỉ cần nêu **song song logic** trong tính toán; các luồng của nền tảng bên dưới tự lập lịch và cân bằng tải với nhau. Chương xét các thuật toán đa luồng viết cho mô hình này và cách nền tảng lập lịch chúng hiệu quả.

**Bốn ưu điểm của mô hình** (theo sách):
- Mở rộng đơn giản của mô hình lập trình tuần tự: chỉ thêm ba từ khoá "đồng thời" **parallel**, **spawn**, **sync** vào mã giả. Xoá chúng đi thì được mã giả tuần tự cho cùng bài toán, gọi là **bản tuần tự hoá** (serialization).
- Cho cách định lượng độ song song sạch sẽ về mặt lý thuyết, dựa trên "work" và "span".
- Nhiều thuật toán đa luồng dùng song song lồng nhau đi ra tự nhiên từ chia để trị, và cũng phân tích được bằng giải truy hồi như thuật toán chia để trị tuần tự.
- Trung thành với thực tiễn đang phát triển: ngày càng nhiều nền tảng hỗ trợ một biến thể của đa luồng động — Cilk, Cilk++, OpenMP, Task Parallel Library, Threading Building Blocks.

Mục 27.1 giới thiệu mô hình và các thước đo work, span, độ song song; Mục 27.2 nhân ma trận đa luồng; Mục 27.3 giải bài toán khó hơn là sắp xếp trộn đa luồng.

### 3. Cơ bản về đa luồng động (27.1 The basics of dynamic multithreading, trang 774–792)

#### 3.1. Ví dụ dẫn: số Fibonacci tính đệ quy

Nhắc lại định nghĩa (truy hồi (3.22) ở Chương 3): F₀ = 0, F₁ = 1, Fᵢ = Fᵢ₋₁ + Fᵢ₋₂ với i ≥ 2. Thuật toán đệ quy tuần tự đơn giản:

```text
FIB(n)
1  if n ≤ 1
2      return n
3  else x = FIB(n − 1)
4       y = FIB(n − 2)
5       return x + y
```

Không ai thực sự tính số Fibonacci lớn theo cách này vì nó lặp lại rất nhiều việc. Cây các lời gọi khi tính FIB(6) (vẽ lại Hình 27.1; mỗi nút là một lời gọi, con trái là FIB(n − 1), con phải là FIB(n − 2)):

```text
                               FIB(6)
                 ┌───────────────┴────────────────┐
              FIB(5)                            FIB(4)
        ┌───────┴────────┐                  ┌─────┴──────┐
     FIB(4)            FIB(3)             FIB(3)       FIB(2)
    ┌──┴───┐          ┌──┴──┐            ┌──┴──┐       ┌──┴──┐
  FIB(3) FIB(2)     FIB(2) FIB(1)      FIB(2) FIB(1) FIB(1) FIB(0)
  ┌─┴─┐   ┌─┴─┐     ┌─┴─┐              ┌─┴─┐
FIB(2) F(1) F(1) F(0) F(1) F(0)        F(1) F(0)
 ┌─┴─┐
F(1) F(0)
```

(F(k) viết tắt cho FIB(k) ở các tầng dưới.) Lời gọi FIB(6) gọi FIB(5) rồi FIB(4); nhưng FIB(5) cũng gọi FIB(4). Hai lần FIB(4) cho cùng kết quả F₄ = 3; vì FIB không ghi nhớ (memoize), lần gọi FIB(4) thứ hai lặp lại toàn bộ việc của lần thứ nhất. Đếm lại (người tổng hợp): cây có 1 + 2 + 4 + 8 + 8 + 2 = 25 nút, khớp công thức số lời gọi của FIB(n) là 2Fₙ₊₁ − 1 = 2 · 13 − 1 = 25.

Gọi T(n) là thời gian chạy của FIB(n). Vì FIB(n) gồm hai lời gọi đệ quy cộng một lượng việc hằng số:

```text
T(n) = T(n − 1) + T(n − 2) + Θ(1)
```

Nghiệm là T(n) = Θ(Fₙ); sách chứng minh (phía cận trên) bằng phương pháp thế với giả thiết quy nạp T(n) ≤ aFₙ − b, a > 1 và b > 0 là hằng:

```text
T(n) ≤ (aFₙ₋₁ − b) + (aFₙ₋₂ − b) + Θ(1)
     = a(Fₙ₋₁ + Fₙ₋₂) − 2b + Θ(1)
     = aFₙ − b − (b − Θ(1))
     ≤ aFₙ − b
```

nếu chọn b đủ lớn để lấn át hằng số trong Θ(1); rồi chọn a đủ lớn để thoả điều kiện ban đầu. Từ phương trình (3.25) (Fₙ là φⁿ/√5 làm tròn tới số nguyên gần nhất) suy ra

```text
T(n) = Θ(φⁿ)                                                         (27.1)
```

với φ = (1 + √5)/2 ≈ 1,618 là tỷ lệ vàng. Vì Fₙ tăng theo hàm mũ, đây là cách đặc biệt chậm để tính số Fibonacci (Problem 31-3 có những cách nhanh hơn nhiều). Nhưng nó là ví dụ tốt để minh hoạ phân tích thuật toán đa luồng: trong FIB(n), hai lời gọi ở dòng 3 và 4 **độc lập** với nhau — gọi theo thứ tự nào cũng được, và tính toán của lời gọi này không ảnh hưởng gì tới lời gọi kia. Vì vậy chúng có thể chạy song song.

#### 3.2. spawn, sync và bản tuần tự hoá

Thêm các **từ khoá đồng thời** (concurrency keywords) **spawn** và **sync** vào mã giả, FIB viết lại cho đa luồng động như sau:

```text
P-FIB(n)
1  if n ≤ 1
2      return n
3  else x = spawn P-FIB(n − 1)
4       y = P-FIB(n − 2)
5       sync
6       return x + y
```

Xoá spawn và sync khỏi P-FIB thì văn bản còn lại giống hệt FIB (trừ việc đổi tên thủ tục ở đầu và ở hai lời gọi). **Bản tuần tự hoá** (serialization) của một thuật toán đa luồng là thuật toán tuần tự có được khi xoá các từ khoá đa luồng spawn, sync và (khi có vòng lặp song song) parallel. Mã giả đa luồng của sách có tính chất tốt: bản tuần tự hoá luôn là mã giả tuần tự bình thường giải cùng bài toán.

**Song song lồng nhau** (nested parallelism) xảy ra khi từ khoá spawn đứng trước một lời gọi thủ tục, như ở dòng 3. Ngữ nghĩa của spawn khác lời gọi thường: lời gọi đang thực hiện spawn — **cha** (parent) — có thể chạy tiếp song song với chương trình con được sinh nhánh — **con** (child) — thay vì đợi con xong như trong chạy tuần tự. Ở đây, trong khi con tính P-FIB(n − 1), cha có thể tính tiếp P-FIB(n − 2) ở dòng 4 song song với con. Vì P-FIB đệ quy, hai lời gọi này lại tạo song song lồng nhau, con của chúng cũng vậy, tạo ra một cây tính toán con có thể rất lớn, tất cả chạy song song.

Tuy nhiên, spawn **không** nói thủ tục *phải* chạy đồng thời với con, chỉ nói *có thể*. Các từ khoá đồng thời diễn tả **song song logic** (logical parallelism): phần nào của tính toán được phép chạy song song. Lúc chạy, **bộ lập lịch** (scheduler) quyết định phần nào thực sự chạy đồng thời bằng cách gán chúng cho các bộ xử lý rảnh khi tính toán diễn ra.

Một thủ tục không thể dùng an toàn giá trị trả về của các con đã sinh nhánh cho tới khi thực hiện câu lệnh **sync** (dòng 5). Từ khoá sync nghĩa là thủ tục phải đợi (khi cần) cho mọi con đã sinh nhánh hoàn tất rồi mới sang câu lệnh sau sync. Trong P-FIB, sync trước return ở dòng 6 là bắt buộc để tránh dị thường cộng x với y khi x chưa được tính. Ngoài sync tường minh, **mọi thủ tục ngầm thực hiện sync trước khi trả về**, bảo đảm mọi con kết thúc trước cha.

#### 3.3. Mô hình thực thi đa luồng: đồ thị tính toán

Nên hình dung một **tính toán đa luồng** (multithreaded computation) — tập các lệnh được bộ xử lý thực hiện lúc chạy thay mặt chương trình đa luồng — như một đồ thị có hướng không chu trình G = (V, E), gọi là **đồ thị tính toán** (computation dag). Về khái niệm, đỉnh là lệnh và cạnh (u, v) ∈ E nghĩa là lệnh u phải chạy trước lệnh v. Để tiện, nếu một chuỗi lệnh không chứa điều khiển song song (không có spawn, sync, hay trả về từ một lần spawn — qua câu lệnh return tường minh hoặc lần trả về ngầm khi tới cuối thủ tục), ta gộp chúng thành một **mạch** (strand), mỗi mạch là một hay nhiều lệnh. Các lệnh điều khiển song song không nằm trong mạch mà được thể hiện qua cấu trúc của dag. Chẳng hạn, nếu một mạch có hai mạch đứng sau, một trong hai phải được sinh nhánh; một mạch có nhiều mạch đứng trước nghĩa là các mạch đó hội lại vì một câu lệnh sync. Tổng quát, V là tập mạch và E là tập cạnh có hướng biểu diễn phụ thuộc giữa các mạch do điều khiển song song tạo ra.

Nếu G có đường đi có hướng từ mạch u tới mạch v, hai mạch là **nối tiếp (logic)** (logically in series); ngược lại u và v là **song song (logic)** (logically in parallel).

Có thể hình dung tính toán đa luồng là dag các mạch nhúng trong cây các lời gọi thủ tục. Cây lời gọi FIB(6) vẽ ở mục 3.1 (Hình 27.1 của sách) cũng chính là cây lời gọi của P-FIB(6), chỉ không có chi tiết mạch; dag của P-FIB(4) dưới đây (Hình 27.2 của sách) phóng to một phần cây đó, cho thấy các mạch tạo nên từng lời gọi. Mọi cạnh có hướng nối các mạch đều chạy bên trong một lời gọi hoặc dọc theo cạnh (vô hướng) của cây lời gọi.

**Vẽ lại Hình 27.2 (dag của P-FIB(4)).** Mỗi lời gọi P-FIB(n) với n ≥ 2 có ba mạch: **mạch đen** b — phần thủ tục tới lệnh spawn P-FIB(n − 1) ở dòng 3; **mạch xám** s — phần gọi P-FIB(n − 2) ở dòng 4 tới sync ở dòng 5 (tại đó nó tạm dừng đợi con được sinh nhánh trả về); **mạch trắng** w — phần sau sync, cộng x và y rồi trả về. Mỗi lời gọi trường hợp cơ sở (P-FIB(1), P-FIB(0)) là một mạch đen duy nhất. Trong hình, các mạch của cùng một lời gọi nằm trong một hình chữ nhật bo góc, tô nhạt nếu lời gọi được sinh nhánh, tô đậm nếu được gọi thường. Cạnh sinh nhánh và cạnh gọi hướng xuống, cạnh tiếp nối hướng ngang sang phải, cạnh trả về hướng lên.

```text
 Lời gọi (loại)                 Mạch       Cạnh đi ra
 ─────────────────────────────  ─────────  ──────────────────────────────────────
 P-FIB(4) (gốc)                 b4 s4 w4   b4 → s4 (tiếp nối); b4 ⇒ b3 (sinh nhánh)
                                           s4 → b2′ (gọi P-FIB(2) bên phải)
 P-FIB(3) (sinh nhánh từ b4)    b3 s3 w3   b3 → s3; b3 ⇒ b2 (sinh nhánh P-FIB(2) trái)
                                           s3 → P-FIB(1) (gọi); w3 ↑ w4 (trả về)
 P-FIB(2) trái (sinh từ b3)     b2 s2 w2   b2 → s2; b2 ⇒ P-FIB(1) (sinh nhánh)
                                           s2 → P-FIB(0) (gọi); w2 ↑ w3
 P-FIB(2) phải (gọi từ s4)      b2′ s2′ w2′ b2′ → s2′; b2′ ⇒ P-FIB(1); s2′ → P-FIB(0)
                                           w2′ ↑ w4
 P-FIB(1), P-FIB(0) (lá, 5 cái) 1 mạch     cạnh trả về lên mạch trắng của cha
```

Sơ đồ dạng cây (→ là cạnh tiếp nối, ⇒ là cạnh sinh nhánh, ↓ là cạnh gọi, "↑ w" là cạnh trả về lên mạch trắng w; giữa s và w của cùng một lời gọi không có cạnh trực tiếp — w chờ các cạnh trả về của hai con):

```text
P-FIB(4) [b4 → s4 · w4]
├─⇒ (sinh nhánh từ b4) P-FIB(3) [b3 → s3 · w3]          w3 ↑ w4
│    ├─⇒ (từ b3) P-FIB(2) [b2 → s2 · w2]                 w2 ↑ w3
│    │    ├─⇒ (từ b2) P-FIB(1) [lá, 1 mạch]              ↑ w2
│    │    └─↓ (từ s2) P-FIB(0) [lá, 1 mạch]              ↑ w2
│    └─↓ (từ s3) P-FIB(1) [lá]                           ↑ w3
└─↓ (gọi từ s4) P-FIB(2) [b2′ → s2′ · w2′]               w2′ ↑ w4
     ├─⇒ (từ b2′) P-FIB(1) [lá]                          ↑ w2′
     └─↓ (từ s2′) P-FIB(0) [lá]                          ↑ w2′
```

Đếm: 4 lời gọi có ba mạch (P-FIB(4), P-FIB(3), hai P-FIB(2)) cho 12 mạch, cộng 5 lá (ba P-FIB(1), hai P-FIB(0)) — tổng **17 mạch**. **Đường găng** (tô đậm trong hình) đi qua **8 mạch**: b4 → b3 → b2 → s2 → P-FIB(0) (lá do s2 gọi) → w2 → w3 → w4. (Kiểm tra của người tổng hợp: đường qua lá do b2 sinh nhánh chỉ có 7 mạch vì bỏ qua s2; đường qua nhánh phải b4 → s4 → b2′ → s2′ → P-FIB(0) → w2′ → w4 có 7 mạch.)

**Phân loại cạnh.** Một **cạnh tiếp nối** (continuation edge) (u, u′), vẽ ngang, nối mạch u với mạch kế tiếp u′ trong cùng lời gọi. Khi mạch u sinh nhánh mạch v, dag có **cạnh sinh nhánh** (spawn edge) (u, v), vẽ hướng xuống. **Cạnh gọi** (call edge), biểu diễn lời gọi thường, cũng hướng xuống. Khác biệt giữa "u sinh nhánh v" và "u gọi v": sinh nhánh tạo thêm cạnh tiếp nối ngang từ u tới mạch u′ đứng sau u trong thủ tục, cho biết u′ được tự do chạy cùng lúc với v; lời gọi thường không tạo cạnh đó. Khi mạch u trả về thủ tục gọi nó và x là mạch đứng ngay sau sync kế tiếp trong thủ tục gọi, dag có **cạnh trả về** (return edge) (u, x), vẽ hướng lên. Một tính toán bắt đầu bằng đúng một **mạch đầu** (initial strand) — đỉnh đen trong lời gọi P-FIB(4) — và kết thúc bằng đúng một **mạch cuối** (final strand) — đỉnh trắng trong lời gọi P-FIB(4).

**Máy tính song song lý tưởng.** Chương nghiên cứu việc chạy thuật toán đa luồng trên **máy tính song song lý tưởng** (ideal parallel computer): một tập bộ xử lý và một bộ nhớ chung **nhất quán tuần tự** (sequentially consistent). Nhất quán tuần tự nghĩa là bộ nhớ chung — trong thực tế có thể đang nhận nhiều lệnh đọc/ghi từ các bộ xử lý cùng lúc — cho kết quả như thể ở mỗi bước có đúng một lệnh của một bộ xử lý được thực hiện; tức là bộ nhớ hành xử như thể các lệnh chạy tuần tự theo một thứ tự tuyến tính toàn cục giữ nguyên thứ tự mà mỗi bộ xử lý phát lệnh của mình. Với tính toán đa luồng động được nền tảng tự lập lịch, bộ nhớ chung hành xử như thể các lệnh của tính toán được xen kẽ thành một thứ tự tuyến tính giữ nguyên thứ tự bộ phận của dag. Tuỳ lập lịch, thứ tự có thể khác nhau giữa các lần chạy, nhưng hành vi của bất kỳ lần chạy nào cũng hiểu được bằng cách giả định các lệnh chạy theo *một* thứ tự tuyến tính nào đó phù hợp với dag.

Ngoài giả định về ngữ nghĩa, mô hình còn có giả định về hiệu năng: mọi bộ xử lý có sức tính như nhau, và **bỏ qua chi phí lập lịch**. Giả định sau nghe có vẻ lạc quan, nhưng với thuật toán có đủ "độ song song" (định nghĩa ngay dưới đây), chi phí lập lịch trong thực tế thường rất nhỏ.

#### 3.4. Các thước đo hiệu năng (Performance measures)

Hiệu quả lý thuyết của thuật toán đa luồng được đo bằng hai chỉ số:

- **Khối lượng công việc** (work) là tổng thời gian chạy toàn bộ tính toán trên một bộ xử lý, tức tổng thời gian của mọi mạch. Với dag mà mỗi mạch tốn một đơn vị thời gian, work là số đỉnh.
- **Độ dài đường găng** (span) là thời gian dài nhất để chạy các mạch dọc theo một đường đi bất kỳ trong dag. Với mạch đơn vị, span là số đỉnh trên một đường dài nhất, gọi là **đường găng** (critical path). (Mục 24.2: tìm được đường găng của dag G = (V, E) trong Θ(V + E).)

Ví dụ: dag P-FIB(4) có 17 đỉnh, 8 đỉnh trên đường găng; nếu mỗi mạch tốn một đơn vị, work là 17 và span là 8 đơn vị thời gian.

Thời gian chạy thực tế còn phụ thuộc số bộ xử lý và cách bộ lập lịch phân mạch. Ký hiệu **T_P** là thời gian chạy trên P bộ xử lý. Work là thời gian chạy trên một bộ xử lý, **T₁**. Span là thời gian chạy nếu mỗi mạch có bộ xử lý riêng — tức có vô hạn bộ xử lý — nên ký hiệu là **T∞**.

Work và span cho hai **cận dưới** của T_P:

- Mỗi bước, máy lý tưởng P bộ xử lý làm tối đa P đơn vị việc, nên trong thời gian T_P làm tối đa P·T_P việc. Tổng việc là T₁, nên P·T_P ≥ T₁. Chia cho P được **luật work** (work law):

```text
T_P ≥ T₁/P                                                           (27.2)
```

- Máy P bộ xử lý không thể nhanh hơn máy vô hạn bộ xử lý; nhìn cách khác, máy vô hạn bộ xử lý có thể giả lập máy P bộ xử lý bằng cách chỉ dùng P bộ xử lý của nó. Do đó có **luật span** (span law):

```text
T_P ≥ T∞                                                             (27.3)
```

**Hệ số tăng tốc** (speedup) trên P bộ xử lý là tỷ số T₁/T_P: tính toán chạy nhanh gấp bao nhiêu lần so với trên một bộ xử lý. Theo luật work, T_P ≥ T₁/P nên T₁/T_P ≤ P: tăng tốc trên P bộ xử lý tối đa là P. Khi tăng tốc tuyến tính theo số bộ xử lý, T₁/T_P = Θ(P), ta có **tăng tốc tuyến tính** (linear speedup); khi T₁/T_P = P, ta có **tăng tốc tuyến tính hoàn hảo** (perfect linear speedup).

Tỷ số T₁/T∞ của work trên span là **độ song song** (parallelism) của tính toán, nhìn từ ba góc:
- như một tỷ số: lượng việc trung bình có thể làm song song cho mỗi bước dọc đường găng;
- như một cận trên: tăng tốc lớn nhất có thể đạt với bất kỳ số bộ xử lý nào;
- quan trọng nhất, như giới hạn của khả năng tăng tốc tuyến tính hoàn hảo: khi số bộ xử lý vượt độ song song thì không thể tăng tốc tuyến tính hoàn hảo. Thật vậy, giả sử P > T₁/T∞; luật span cho T₁/T_P ≤ T₁/T∞ < P. Hơn nữa, nếu P ≫ T₁/T∞ thì T₁/T_P ≪ P: dùng càng nhiều bộ xử lý vượt quá độ song song, tăng tốc càng kém hoàn hảo.

Ví dụ P-FIB(4) với mạch đơn vị: T₁ = 17, T∞ = 8, độ song song 17/8 = 2,125. Vì vậy không thể tăng tốc hơn khoảng gấp đôi, dù dùng bao nhiêu bộ xử lý. Với đầu vào lớn hơn, P-FIB(n) có độ song song đáng kể (mục 3.6).

**Độ dư song song** ((parallel) slackness) của tính toán trên máy lý tưởng P bộ xử lý là tỷ số (T₁/T∞)/P = T₁/(P·T∞) — số lần độ song song vượt số bộ xử lý. Nếu độ dư nhỏ hơn 1, không thể hy vọng tăng tốc tuyến tính hoàn hảo, vì T₁/(P·T∞) < 1 và luật span cho T₁/T_P ≤ T₁/T∞ < P. Độ dư giảm từ 1 về 0 thì tăng tốc càng xa hoàn hảo. Nếu độ dư lớn hơn 1, ràng buộc là lượng việc trên mỗi bộ xử lý; và như sẽ thấy, độ dư tăng từ 1 thì bộ lập lịch tốt càng gần tăng tốc tuyến tính hoàn hảo.

#### 3.5. Lập lịch (Scheduling)

Hiệu năng tốt không chỉ cần work và span nhỏ; các mạch còn phải được lập lịch hiệu quả lên các bộ xử lý. Mô hình lập trình không cho cách chỉ định mạch nào chạy trên bộ xử lý nào; ta dựa vào bộ lập lịch của nền tảng để ánh xạ tính toán đang dần mở ra lên từng bộ xử lý. Thực tế, bộ lập lịch ánh xạ mạch lên luồng tĩnh và hệ điều hành lập lịch luồng lên bộ xử lý, nhưng tầng gián tiếp này không cần cho việc hiểu lập lịch: cứ hình dung bộ lập lịch ánh xạ mạch thẳng lên bộ xử lý.

Bộ lập lịch đa luồng phải lập lịch mà không biết trước khi nào mạch được sinh ra hay khi nào xong — nó phải hoạt động **trực tuyến** (on-line). Bộ lập lịch tốt còn hoạt động **phân tán** (distributed): các luồng cài bộ lập lịch cùng nhau cân bằng tải. Đã có những bộ lập lịch trực tuyến phân tán chứng minh được là tốt, nhưng phân tích chúng phức tạp. Để phân tích đơn giản, chương xét bộ lập lịch trực tuyến **tập trung** (centralized), biết trạng thái toàn cục của tính toán ở mọi thời điểm. Cụ thể là **bộ lập lịch tham lam** (greedy scheduler): mỗi bước gán càng nhiều mạch cho bộ xử lý càng tốt. Nếu trong một bước có ít nhất P mạch sẵn sàng, bước đó là **bước đầy** (complete step) và bộ lập lịch tham lam gán P mạch sẵn sàng bất kỳ cho các bộ xử lý. Ngược lại, có ít hơn P mạch sẵn sàng, bước đó là **bước không đầy** (incomplete step), và bộ lập lịch gán mỗi mạch sẵn sàng cho một bộ xử lý riêng.

Theo luật work, thời gian tốt nhất có thể hy vọng trên P bộ xử lý là T_P = T₁/P; theo luật span là T_P = T∞. Định lý sau cho thấy lập lịch tham lam tốt một cách chứng minh được: nó đạt *tổng* hai cận dưới làm cận trên.

**Định lý 27.1.** Trên máy tính song song lý tưởng có P bộ xử lý, bộ lập lịch tham lam chạy một tính toán đa luồng có work T₁ và span T∞ trong thời gian

```text
T_P ≤ T₁/P + T∞                                                      (27.4)
```

*Chứng minh.* Xét các bước đầy trước. Mỗi bước đầy, P bộ xử lý cùng làm tổng cộng P đơn vị việc. Giả sử phản chứng số bước đầy lớn hẳn hơn ⌊T₁/P⌋. Khi đó tổng việc của các bước đầy ít nhất là

```text
P · (⌊T₁/P⌋ + 1) = P⌊T₁/P⌋ + P
                 = T₁ − (T₁ mod P) + P      (theo phương trình (3.8): a mod n = a − n⌊a/n⌋)
                 > T₁                        (theo bất đẳng thức (3.9): 0 ≤ a mod n < n)
```

Vậy P bộ xử lý làm nhiều việc hơn tính toán cần — mâu thuẫn. Do đó số bước đầy không quá ⌊T₁/P⌋.

Xét một bước không đầy. Gọi G là dag của toàn bộ tính toán; không mất tổng quát, giả sử mỗi mạch tốn một đơn vị thời gian (mạch dài hơn có thể thay bằng một chuỗi mạch đơn vị). Gọi G′ là phần đồ thị con của G chưa chạy ở đầu bước không đầy, G″ là phần còn lại sau bước đó. Một đường dài nhất trong dag nhất thiết bắt đầu ở một đỉnh có bậc vào 0. Vì bước không đầy của bộ lập lịch tham lam chạy **mọi** mạch có bậc vào 0 trong G′, độ dài đường dài nhất trong G″ phải ngắn hơn đường dài nhất trong G′ đúng 1. Nói cách khác, mỗi bước không đầy giảm span của dag chưa chạy đi 1. Vậy số bước không đầy không quá T∞.

Mỗi bước hoặc đầy hoặc không đầy, nên định lý được chứng minh. ∎

**Hệ quả 27.2.** Thời gian chạy T_P của bất kỳ tính toán đa luồng nào được lập lịch bởi bộ lập lịch tham lam trên máy lý tưởng P bộ xử lý nằm trong phạm vi hệ số 2 của tối ưu.

*Chứng minh.* Gọi T*_P là thời gian của lịch tối ưu trên máy P bộ xử lý; T₁, T∞ là work và span. Luật work và luật span (27.2), (27.3) cho T*_P ≥ max(T₁/P, T∞). Theo Định lý 27.1:

```text
T_P ≤ T₁/P + T∞
    ≤ 2 · max(T₁/P, T∞)
    ≤ 2T*_P                                                            ∎
```

**Hệ quả 27.3.** Gọi T_P là thời gian chạy của một tính toán đa luồng do bộ lập lịch tham lam tạo ra trên máy lý tưởng P bộ xử lý, T₁ và T∞ là work và span. Nếu P ≪ T₁/T∞ thì T_P ≈ T₁/P, hay tương đương, tăng tốc xấp xỉ P.

*Chứng minh.* Nếu P ≪ T₁/T∞ thì cũng có T∞ ≪ T₁/P, nên Định lý 27.1 cho T_P ≤ T₁/P + T∞ ≈ T₁/P. Luật work (27.2) buộc T_P ≥ T₁/P, nên T_P ≈ T₁/P, tức tăng tốc T₁/T_P ≈ P. ∎

Ký hiệu ≪ nghĩa là "nhỏ hơn nhiều", nhưng nhiều là bao nhiêu? Quy tắc kinh nghiệm: độ dư ít nhất 10 — độ song song gấp 10 lần số bộ xử lý — thường đủ cho tăng tốc tốt. Khi đó số hạng span trong cận tham lam (27.4) nhỏ hơn 10% số hạng việc-trên-mỗi-bộ-xử-lý, đủ tốt cho đa số tình huống kỹ thuật. Chẳng hạn, nếu tính toán chỉ chạy trên 10 hay 100 bộ xử lý, không có lý do coi độ song song 1.000.000 tốt hơn độ song song 10.000, dù chênh 100 lần. Problem 27-2 cho thấy đôi khi giảm độ song song cực lớn lại cho thuật toán tốt hơn ở khía cạnh khác mà vẫn mở rộng tốt trên số bộ xử lý hợp lý.

Ví dụ số (người tổng hợp): T₁ = 10⁶, T∞ = 10³ (độ song song 1000). Với P = 100 (độ dư 10): cận tham lam 10⁴ + 10³ = 11.000, so với cận dưới 10.000 — chênh 10%. Với P = 1000 (độ dư 1): cận tham lam 1000 + 1000 = 2000, chỉ bảo đảm tăng tốc ≥ 500. Với P = 10.000 (độ dư 0,1): cận dưới là max(100, 1000) = 1000 — tăng tốc không quá 1000 dù có 10.000 bộ xử lý.

#### 3.6. Phân tích thuật toán đa luồng (Analyzing multithreaded algorithms)

Phân tích work tương đối dễ: nó chỉ là phân tích thời gian chạy của một thuật toán tuần tự bình thường — bản tuần tự hoá — việc mà gần như cả cuốn sách đã làm. Phân tích span thú vị hơn nhưng thường không khó hơn khi đã quen.

Work T₁(n) của P-FIB(n) đã có sẵn: FIB thực chất là bản tuần tự hoá của P-FIB, nên T₁(n) = T(n) = Θ(φⁿ) theo (27.1).

**Quy tắc ghép (vẽ lại Hình 27.3):**

```text
(a) Ghép NỐI TIẾP:   ──▶ [ A ] ──▶ [ B ] ──▶
    Work: T₁(A ∪ B) = T₁(A) + T₁(B)
    Span: T∞(A ∪ B) = T∞(A) + T∞(B)

(b) Ghép SONG SONG:        ┌──▶ [ A ] ──┐
                       ──▶─┤            ├──▶
                           └──▶ [ B ] ──┘
    Work: T₁(A ∪ B) = T₁(A) + T₁(B)
    Span: T∞(A ∪ B) = max(T∞(A), T∞(B))
```

Hai phần tính ghép nối tiếp thì span cộng lại; ghép song song thì span của tổ hợp chỉ là max của hai span; work trong cả hai trường hợp đều cộng.

Với P-FIB(n), lời gọi sinh nhánh P-FIB(n − 1) ở dòng 3 chạy song song với lời gọi P-FIB(n − 2) ở dòng 4. Do đó span thoả truy hồi

```text
T∞(n) = max(T∞(n − 1), T∞(n − 2)) + Θ(1)
      = T∞(n − 1) + Θ(1)
```

có nghiệm T∞(n) = Θ(n). Độ song song của P-FIB(n) là T₁(n)/T∞(n) = Θ(φⁿ/n), tăng rất nhanh khi n lớn. Vì vậy, kể cả trên máy song song lớn nhất, chỉ cần n vừa phải là P-FIB(n) đạt tăng tốc gần tuyến tính hoàn hảo, vì thủ tục có độ dư song song rất lớn.

Kiểm tra bằng đếm mạch (người tổng hợp): với n ≥ 2, P-FIB(n) có Fₙ₊₁ − 1 lời gọi không cơ sở (3 mạch) và Fₙ₊₁ lời gọi cơ sở (1 mạch), nên work = 4Fₙ₊₁ − 3 mạch; span S(n) thoả S(n) = max(S(n − 1) + 2, S(n − 2) + 3), S(0) = S(1) = 1, cho S(2) = 4, S(3) = 6, S(4) = 8, S(5) = 10, tổng quát S(n) = 2n. Với n = 4: work 4 · 5 − 3 = 17, span 8 — khớp Hình 27.2. Với n = 30: F₃₁ = 1.346.269, work = 5.385.073 mạch, span = 60, độ song song ≈ 89.751.

#### 3.7. Vòng lặp song song (Parallel loops)

Nhiều thuật toán có vòng lặp mà mọi lần lặp có thể chạy song song. Có thể song song hoá chúng bằng spawn và sync, nhưng tiện hơn nhiều nếu nói thẳng các lần lặp chạy đồng thời được: mã giả dùng từ khoá **parallel** đặt trước **for**.

Ví dụ: nhân ma trận n × n A = (a_ij) với vectơ x = (x_j) cỡ n. Kết quả là vectơ y = (y_i) với

```text
y_i = Σ_{j=1}^{n} a_ij · x_j ,      i = 1, 2, …, n
```

Tính mọi phần tử của y song song:

```text
MAT-VEC(A, x)
1  n = A.rows
2  let y be a new vector of length n
3  parallel for i = 1 to n
4      y_i = 0
5  parallel for i = 1 to n
6      for j = 1 to n
7          y_i = y_i + a_ij · x_j
8  return y
```

Từ khoá parallel for ở dòng 3 và 5 cho biết các lần lặp của hai vòng đó có thể chạy đồng thời. Trình biên dịch có thể cài mỗi vòng parallel for thành một chương trình con chia để trị dùng song song lồng nhau. Ví dụ vòng ở dòng 5–7 được cài bằng lời gọi MAT-VEC-MAIN-LOOP(A, x, y, n, 1, n), với chương trình con phụ do trình biên dịch sinh:

```text
MAT-VEC-MAIN-LOOP(A, x, y, n, i, i′)
1  if i == i′
2      for j = 1 to n
3          y_i = y_i + a_ij · x_j
4  else mid = ⌊(i + i′)/2⌋
5      spawn MAT-VEC-MAIN-LOOP(A, x, y, n, i, mid)
6      MAT-VEC-MAIN-LOOP(A, x, y, n, mid + 1, i′)
7      sync
```

Mã này đệ quy sinh nhánh nửa đầu các lần lặp để chạy song song với nửa sau rồi sync, tạo một cây nhị phân thực thi mà lá là từng lần lặp. **Vẽ lại Hình 27.4** (dag của MAT-VEC-MAIN-LOOP(A, x, y, 8, 1, 8); mỗi nút ghi hai tham số cuối i, i′; nút trong có ba mạch: đen — tới spawn ở dòng 5; xám — gọi ở dòng 6 tới sync ở dòng 7; trắng — phần (không đáng kể) sau sync tới khi trả về; lá có một mạch đen chạy dòng 1–3):

```text
                              [1,8]: b → s   w
                    ⇓ sinh nhánh    ↓ gọi
              [1,4]: b → s  w                    [5,8]: b → s  w
             ⇓       ↓                           ⇓       ↓
      [1,2]: b→s w     [3,4]: b→s w       [5,6]: b→s w     [7,8]: b→s w
       ⇓    ↓           ⇓    ↓             ⇓    ↓           ⇓    ↓
     [1,1] [2,2]      [3,3] [4,4]        [5,5] [6,6]      [7,7] [8,8]
     (mỗi lá trả về ↑ mạch trắng của cha; mạch trắng của con trả về
      ↑ mạch trắng của cha; [1,4] được sinh nhánh, [5,8] được gọi thường)
```

Đếm (người tổng hợp): 7 nút trong × 3 mạch + 8 lá = 29 mạch. Đường găng với mạch đơn vị: b[1,8] → s[1,8] → b[5,8] → s[5,8] → b[7,8] → s[7,8] → lá [8,8] → w[7,8] → w[5,8] → w[1,8] = 10 mạch, tức 3 lg 8 + 1.

**Work của vòng lặp song song.** Work T₁(n) của MAT-VEC trên ma trận n × n là thời gian của bản tuần tự hoá (thay parallel for bằng for thường): T₁(n) = Θ(n²), vì hai vòng lồng ở dòng 5–7 chiếm ưu thế. Phân tích này có vẻ bỏ qua chi phí sinh nhánh đệ quy khi cài vòng song song. Thực ra chi phí đó có làm tăng work so với bản tuần tự hoá, nhưng không về mặt tiệm cận: cây các lời gọi là cây nhị phân đầy đủ (full binary tree), nên số nút trong ít hơn số lá đúng 1 (Exercise B.5-3). Mỗi nút trong làm việc hằng số để chia khoảng lặp, còn mỗi lá ứng với một lần lặp, tốn ít nhất hằng số thời gian (ở đây Θ(n)). Vậy có thể khấu hao chi phí sinh nhánh vào việc của các lần lặp, chỉ thêm tối đa một hệ số hằng vào tổng work.

Trong thực tế, các nền tảng đa luồng động đôi khi **gộp lá** (coarsen) của cây đệ quy bằng cách cho mỗi lá chạy nhiều lần lặp — tự động hoặc theo chỉ định của người lập trình — để giảm chi phí sinh nhánh. Đổi lại độ song song giảm, nhưng nếu tính toán có đủ độ dư song song thì không phải hy sinh tăng tốc gần tuyến tính hoàn hảo.

**Span của vòng lặp song song.** Cũng phải tính chi phí sinh nhánh đệ quy khi phân tích span. Vì độ sâu đệ quy là logarit theo số lần lặp, một vòng song song n lần lặp, lần lặp thứ i có span iter∞(i), có span

```text
T∞(n) = Θ(lg n) + max_{1≤i≤n} iter∞(i)
```

Với MAT-VEC: vòng khởi tạo ở dòng 3–4 có span Θ(lg n), vì sinh nhánh đệ quy lấn át việc hằng số của mỗi lần lặp. Hai vòng lồng ở dòng 5–7 có span Θ(n), vì mỗi lần lặp của vòng parallel for ngoài chứa n lần lặp của vòng for trong (tuần tự). Phần còn lại tốn hằng số, nên span của cả thủ tục là Θ(n). Work Θ(n²) nên độ song song là Θ(n²)/Θ(n) = Θ(n). (Exercise 27.1-6 yêu cầu một cài đặt có độ song song lớn hơn.)

#### 3.8. Tranh chấp (Race conditions)

Một thuật toán đa luồng là **tất định** (deterministic) nếu luôn làm cùng một việc trên cùng đầu vào, bất kể các lệnh được lập lịch thế nào trên máy đa nhân; là **không tất định** (nondeterministic) nếu hành vi có thể khác nhau giữa các lần chạy. Thường một thuật toán đa luồng *định* là tất định lại không tất định vì chứa một "tranh chấp tất định".

Tranh chấp là tai hoạ của lập trình đồng thời. Những lỗi tranh chấp nổi tiếng gồm máy xạ trị Therac-25 (làm chết ba người và bị thương vài người) và vụ mất điện Bắc Mỹ năm 2003 (hơn 50 triệu người mất điện). Loại lỗi này nổi tiếng khó tìm: có thể chạy thử trong phòng thí nghiệm nhiều ngày không lỗi rồi phát hiện phần mềm thỉnh thoảng sập khi dùng thật.

**Tranh chấp tất định** (determinacy race) xảy ra khi hai lệnh song song logic cùng truy cập một ô nhớ và ít nhất một trong hai lệnh ghi. Thủ tục sau minh hoạ:

```text
RACE-EXAMPLE( )
1  x = 0
2  parallel for i = 1 to 2
3      x = x + 1
4  print x
```

Sau khi khởi tạo x = 0 ở dòng 1, RACE-EXAMPLE tạo hai mạch song song, mỗi mạch tăng x ở dòng 3. Tưởng như nó luôn in 2 (bản tuần tự hoá chắc chắn in 2), nhưng nó có thể in 1. Lý do: khi một bộ xử lý tăng x, thao tác không phải nguyên tử mà gồm một chuỗi lệnh:

1. Đọc x từ bộ nhớ vào một thanh ghi của bộ xử lý.
2. Tăng giá trị trong thanh ghi.
3. Ghi giá trị trong thanh ghi trở lại x trong bộ nhớ.

**Vẽ lại Hình 27.5.** (a) Dag phụ thuộc giữa các lệnh riêng lẻ (số là thứ tự đánh số lệnh; r₁, r₂ là thanh ghi của bộ xử lý 1 và 2; các lệnh không liên quan tới tranh chấp như điều khiển vòng lặp bị lược bỏ):

```text
                     1: x = 0
                ┌────────┴────────┐
                ▼                 ▼
          2: r₁ = x          4: r₂ = x
                ▼                 ▼
          3: incr r₁         5: incr r₂
                ▼                 ▼
          7: x = r₁          6: x = r₂
                └────────┬────────┘
                         ▼
                     8: print x
```

(b) Một thứ tự chạy gây lỗi, với giá trị x trong bộ nhớ và hai thanh ghi sau mỗi bước ("–" là chưa có giá trị):

| Bước (lệnh) | x | r₁ | r₂ |
|---|---|---|---|
| 1: x = 0 | 0 | – | – |
| 2: r₁ = x | 0 | 0 | – |
| 3: incr r₁ | 0 | 1 | – |
| 4: r₂ = x | 0 | 1 | 0 |
| 5: incr r₂ | 0 | 1 | 1 |
| 6: x = r₂ | 1 | 1 | 1 |
| 7: x = r₁ | 1 | 1 | 1 |

Bước 1, một bộ xử lý đặt x = 0. Bước 2 và 3, bộ xử lý 1 đọc x vào r₁ và tăng, r₁ = 1. Lúc đó bộ xử lý 2 vào cuộc, chạy lệnh 4–6: đọc x vào r₂, tăng thành 1, ghi vào x, x = 1. Bộ xử lý 1 tiếp tục ở bước 7, ghi r₁ = 1 vào x — x không đổi. Bước 8 in 1 chứ không phải 2.

Nếu hiệu quả của việc chạy song song là bộ xử lý 1 làm hết lệnh của nó trước bộ xử lý 2, kết quả là 2; ngược lại cũng vậy. Nhưng khi lệnh của hai bộ xử lý chạy xen nhau, có thể mất một lần cập nhật x như ví dụ. Dĩ nhiên nhiều thứ tự không gây lỗi, ví dụ ⟨1, 2, 3, 7, 4, 5, 6, 8⟩ hay ⟨1, 4, 5, 6, 2, 3, 7, 8⟩ cho kết quả đúng. Đó chính là vấn đề của tranh chấp tất định: thường thì phần lớn thứ tự cho kết quả đúng (như mọi thứ tự mà lệnh bên trái chạy hết trước lệnh bên phải hoặc ngược lại), nhưng một số thứ tự xen kẽ cho kết quả sai. Vì vậy tranh chấp cực khó kiểm thử: có thể chạy thử nhiều ngày không thấy lỗi rồi gặp sự cố thảm hoạ khi dùng thật ở lúc hệ trọng. (Như đã ghi trong khối Lưu ý, nếu đếm đều 20 cách xen kẽ hai chuỗi ba lệnh thì chỉ 2 cách cho kết quả 2.)

Có nhiều cách đối phó với tranh chấp, kể cả khoá loại trừ lẫn nhau (mutual-exclusion lock) và các phương pháp đồng bộ khác; trong chương, ta chỉ đơn giản bảo đảm các mạch chạy song song là **độc lập** (independent): không có tranh chấp tất định giữa chúng. Vì vậy trong cấu trúc parallel for, mọi lần lặp phải độc lập. Giữa một spawn và sync tương ứng, mã của con được sinh nhánh phải độc lập với mã của cha, kể cả mã do các con khác (sinh nhánh hay gọi thường) chạy. Lưu ý đối số truyền cho con được tính trong cha *trước* khi spawn xảy ra, nên việc tính đối số nối tiếp với mọi truy cập tới các đối số đó sau spawn.

Ví dụ về việc dễ viết ra mã có tranh chấp — một cài đặt sai của nhân ma trận–vectơ đa luồng đạt span Θ(lg n) bằng cách song song hoá vòng for trong:

```text
MAT-VEC-WRONG(A, x)
1  n = A.rows
2  let y be a new vector of length n
3  parallel for i = 1 to n
4      y_i = 0
5  parallel for i = 1 to n
6      parallel for j = 1 to n
7          y_i = y_i + a_ij · x_j
8  return y
```

Thủ tục này sai vì tranh chấp khi cập nhật y_i ở dòng 7, dòng này chạy đồng thời cho cả n giá trị của j (Exercise 27.1-6 yêu cầu một cài đặt đúng với span Θ(lg n)). Một thuật toán đa luồng có tranh chấp đôi khi vẫn đúng — ví dụ hai luồng song song cùng ghi *cùng một giá trị* vào một biến chung, ai ghi trước cũng không sao. Nhưng nói chung chương coi mã có tranh chấp là không hợp lệ.

#### 3.9. Bài học cờ vua (A chess lesson)

Câu chuyện có thật trong quá trình phát triển chương trình chơi cờ đa luồng đẳng cấp thế giới **★Socrates** (các con số đã được đơn giản hoá để trình bày). Chương trình được làm mẫu trên máy 32 bộ xử lý nhưng cuối cùng sẽ chạy trên siêu máy tính 512 bộ xử lý. Có lúc nhóm phát triển thêm một "tối ưu hoá" giảm thời gian chạy trên một bài kiểm chuẩn quan trọng trên máy 32 bộ xử lý từ T₃₂ = 65 giây xuống T′₃₂ = 40 giây. Vậy mà họ dùng work và span để kết luận bản tối ưu — nhanh hơn trên 32 bộ xử lý — sẽ *chậm hơn* bản gốc trên 512 bộ xử lý, và bỏ "tối ưu hoá" đó.

Phân tích của họ: bản gốc có work T₁ = 2048 giây và span T∞ = 1 giây. Coi bất đẳng thức (27.4) như đẳng thức, T_P = T₁/P + T∞, làm xấp xỉ thời gian trên P bộ xử lý:

| Phiên bản | T₁ | T∞ | Độ song song | T₃₂ ≈ T₁/32 + T∞ | T₅₁₂ ≈ T₁/512 + T∞ |
|---|---|---|---|---|---|
| Gốc | 2048 | 1 | 2048 | 64 + 1 = 65 | 4 + 1 = 5 |
| "Tối ưu" | 1024 | 8 | 128 | 32 + 8 = 40 | 2 + 8 = 10 |

Trên 512 bộ xử lý, thứ tự đảo ngược: tối ưu hoá làm chương trình chậm gấp đôi! Span 8 của bản tối ưu — không phải số hạng chính trên 32 bộ xử lý — trở thành số hạng chính trên 512 bộ xử lý, triệt tiêu lợi ích của việc dùng thêm bộ xử lý. Bài học: **work và span là phương tiện ngoại suy hiệu năng tốt hơn thời gian chạy đo được.** (Exercise 27.1-9: hai bản chạy bằng nhau khi 2048/P + 1 = 1024/P + 8, tức P = 1024/7 ≈ 146,3.)

#### Ví dụ hôm nay

Mô hình spawn/sync sống tiếp trong nhiều công cụ hiện nay (theo hiểu biết của người tổng hợp): `ForkJoinPool` và `parallelStream` của Java, thư viện Rayon của Rust (`rayon::join` là đúng một cặp spawn/sync, `par_iter` là parallel for), Intel oneTBB (hậu duệ của Threading Building Blocks), OpenMP `task`/`taskwait`, Go với goroutine và `sync.WaitGroup` (không hoàn toàn là mô hình fork-join chặt). Hầu hết dùng bộ lập lịch đánh cắp việc (work-stealing) đúng như Ghi chú chương nhắc. Quy tắc "độ dư ≥ 10" và "work/span ngoại suy tốt hơn thời gian đo" vẫn là lời khuyên đúng khi chọn kích thước hạt (grain size) cho các tác vụ.

### 4. Nhân ma trận đa luồng (27.2 Multithreaded matrix multiplication, trang 792–797)

Mục này song song hoá phép nhân ma trận, bài toán đã phân tích thời gian tuần tự ở Mục 4.2: các thuật toán dựa trên ba vòng lặp lồng chuẩn, và các thuật toán chia để trị.

#### 4.1. Song song hoá ba vòng lặp lồng (Multithreaded matrix multiplication)

Thuật toán đầu tiên là cách thẳng thắn: song song hoá các vòng lặp của thủ tục SQUARE-MATRIX-MULTIPLY (Mục 4.2: với mỗi i, j, đặt c_ij = 0 rồi cộng dồn a_ik · b_kj với k = 1..n):

```text
P-SQUARE-MATRIX-MULTIPLY(A, B)
1  n = A.rows
2  let C be a new n × n matrix
3  parallel for i = 1 to n
4      parallel for j = 1 to n
5          c_ij = 0
6          for k = 1 to n
7              c_ij = c_ij + a_ik · b_kj
8  return C
```

Bản tuần tự hoá chính là SQUARE-MATRIX-MULTIPLY, nên work là T₁(n) = Θ(n³), bằng thời gian chạy của SQUARE-MATRIX-MULTIPLY. Span là T∞(n) = Θ(n): đường găng đi xuống cây đệ quy của vòng parallel for ở dòng 3, rồi xuống cây đệ quy của vòng parallel for ở dòng 4, rồi chạy hết n lần lặp của vòng for thường ở dòng 6, tổng Θ(lg n) + Θ(lg n) + Θ(n) = Θ(n). Vậy độ song song là Θ(n³)/Θ(n) = Θ(n²). Exercise 27.2-3 yêu cầu song song hoá cả vòng trong để có độ song song Θ(n³/lg n); điều này không làm thẳng bằng parallel for được, vì sẽ tạo tranh chấp (nhiều lần lặp k cùng cộng vào một c_ij, giống MAT-VEC-WRONG).

Ví dụ số (người tổng hợp): n = 1000, bỏ hằng số: work 10⁹, span khoảng 1000 + 2 · 10 = 1020, độ song song khoảng 10⁶ — dư sức cho mọi máy đa nhân.

#### 4.2. Thuật toán chia để trị đa luồng (A divide-and-conquer multithreaded algorithm for matrix multiplication)

Mục 4.2 cho thấy có thể nhân ma trận n × n tuần tự trong Θ(n^lg 7) = O(n^2,81) bằng chiến lược chia để trị của Strassen, nên đáng song song hoá loại thuật toán này. Bắt đầu, như Mục 4.2, bằng một thuật toán chia để trị đơn giản hơn. Thủ tục SQUARE-MATRIX-MULTIPLY-RECURSIVE (Mục 4.2) nhân hai ma trận n × n A, B thành C bằng cách chia mỗi ma trận thành bốn ma trận con n/2 × n/2:

```text
A = ⎛A₁₁ A₁₂⎞ ,   B = ⎛B₁₁ B₁₂⎞ ,   C = ⎛C₁₁ C₁₂⎞
    ⎝A₂₁ A₂₂⎠         ⎝B₂₁ B₂₂⎠         ⎝C₂₁ C₂₂⎠
```

Khi đó tích ma trận viết được là

```text
⎛C₁₁ C₁₂⎞   ⎛A₁₁ A₁₂⎞ ⎛B₁₁ B₁₂⎞
⎝C₂₁ C₂₂⎠ = ⎝A₂₁ A₂₂⎠ ⎝B₂₁ B₂₂⎠

            ⎛A₁₁B₁₁  A₁₁B₁₂⎞   ⎛A₁₂B₂₁  A₁₂B₂₂⎞
          = ⎝A₂₁B₁₁  A₂₁B₁₂⎠ + ⎝A₂₂B₂₁  A₂₂B₂₂⎠                      (27.6)
```

Như vậy để nhân hai ma trận n × n, ta làm tám phép nhân ma trận n/2 × n/2 và một phép cộng ma trận n × n. Mã giả sau cài chiến lược này bằng song song lồng nhau. Khác thủ tục gốc SQUARE-MATRIX-MULTIPLY-RECURSIVE, P-MATRIX-MULTIPLY-RECURSIVE nhận ma trận kết quả làm tham số để tránh cấp phát ma trận không cần thiết.

```text
P-MATRIX-MULTIPLY-RECURSIVE(C, A, B)
 1  n = A.rows
 2  if n == 1
 3      c₁₁ = a₁₁ b₁₁
 4  else let T be a new n × n matrix
 5      partition A, B, C, and T into n/2 × n/2 submatrices
            A₁₁, A₁₂, A₂₁, A₂₂; B₁₁, B₁₂, B₂₁, B₂₂; C₁₁, C₁₂, C₂₁, C₂₂;
            and T₁₁, T₁₂, T₂₁, T₂₂; respectively
 6      spawn P-MATRIX-MULTIPLY-RECURSIVE(C₁₁, A₁₁, B₁₁)
 7      spawn P-MATRIX-MULTIPLY-RECURSIVE(C₁₂, A₁₁, B₁₂)
 8      spawn P-MATRIX-MULTIPLY-RECURSIVE(C₂₁, A₂₁, B₁₁)
 9      spawn P-MATRIX-MULTIPLY-RECURSIVE(C₂₂, A₂₁, B₁₂)
10      spawn P-MATRIX-MULTIPLY-RECURSIVE(T₁₁, A₁₂, B₂₁)
11      spawn P-MATRIX-MULTIPLY-RECURSIVE(T₁₂, A₁₂, B₂₂)
12      spawn P-MATRIX-MULTIPLY-RECURSIVE(T₂₁, A₂₂, B₂₁)
13      P-MATRIX-MULTIPLY-RECURSIVE(T₂₂, A₂₂, B₂₂)
14      sync
15      parallel for i = 1 to n
16          parallel for j = 1 to n
17              c_ij = c_ij + t_ij
```

Giải thích: dòng 3 xử lý trường hợp cơ sở, nhân hai ma trận 1 × 1. Trường hợp đệ quy ở dòng 4–17. Dòng 4 cấp phát ma trận tạm T; dòng 5 chia mỗi ma trận A, B, C, T thành các ma trận con n/2 × n/2 (như ở SQUARE-MATRIX-MULTIPLY-RECURSIVE, sách bỏ qua chi tiết dùng phép tính chỉ số để biểu diễn một khối con của ma trận). Lời gọi đệ quy ở dòng 6 đặt C₁₁ bằng tích A₁₁B₁₁, tức số hạng thứ nhất trong tổng tạo nên C₁₁ ở (27.6). Tương tự dòng 7–9 đặt C₁₂, C₂₁, C₂₂ bằng số hạng thứ nhất của tổng tương ứng. Dòng 10 đặt T₁₁ bằng A₁₂B₂₁, số hạng thứ hai của tổng tạo nên C₁₁; dòng 11–13 đặt T₁₂, T₂₁, T₂₂ bằng số hạng thứ hai của tổng tạo nên C₁₂, C₂₁, C₂₂. Bảy lời gọi đầu được sinh nhánh, lời gọi cuối chạy trong mạch chính. Câu lệnh sync ở dòng 14 bảo đảm mọi tích khối ở dòng 6–13 đã xong; sau đó hai vòng parallel for lồng ở dòng 15–17 cộng các tích trong T vào C. (Tám lời gọi ghi vào tám khối khác nhau — C₁₁, C₁₂, C₂₁, C₂₂, T₁₁, T₁₂, T₂₁, T₂₂ — và chỉ đọc A, B, nên chúng độc lập, không có tranh chấp; đó là lý do cần ma trận tạm T — nhận xét của người tổng hợp.)

**Work.** Gọi M₁(n) là work, theo đúng cách phân tích thời gian tuần tự của SQUARE-MATRIX-MULTIPLY-RECURSIVE. Ở trường hợp đệ quy: chia khối Θ(1), tám phép nhân đệ quy cỡ n/2 × n/2, và Θ(n²) việc để cộng hai ma trận n × n:

```text
M₁(n) = 8M₁(n/2) + Θ(n²)
      = Θ(n³)
```

theo trường hợp 1 của định lý thợ (a = 8, b = 2, n^(log₂ 8) = n³ lớn hơn đa thức so với n²). Tức work của thuật toán đa luồng tiệm cận bằng thời gian chạy của SQUARE-MATRIX-MULTIPLY với ba vòng lồng.

**Span.** Gọi M∞(n) là span. Span của bước chia khối là Θ(1), bị lấn át bởi span Θ(lg n) của hai vòng parallel for lồng ở dòng 15–17. Vì tám lời gọi đệ quy song song đều chạy trên ma trận cùng cỡ, span lớn nhất của một lời gọi chính là span của một lời gọi bất kỳ. Do đó

```text
M∞(n) = M∞(n/2) + Θ(lg n)                                            (27.7)
```

Truy hồi này không thuộc trường hợp nào của định lý thợ, nhưng thoả điều kiện của Exercise 4.6-2 (nếu f(n) = Θ(n^(log_b a) lg^k n) với k ≥ 0 thì T(n) = Θ(n^(log_b a) lg^(k+1) n); ở đây a = 1, b = 2, n^0 = 1, k = 1). Vậy M∞(n) = Θ(lg² n). Kiểm tra trực tiếp (người tổng hợp): trải truy hồi ra được c(lg n + (lg n − 1) + … + 1) = c · lg n (lg n + 1)/2 = Θ(lg² n).

**Độ song song.** M₁(n)/M∞(n) = Θ(n³/lg² n), rất cao. Ví dụ (Problem 27-2): với ma trận 1000 × 1000, bỏ hằng số, lg 1000 ≈ 10 nên độ song song khoảng 1000³/10² = 10⁷.

#### 4.3. Strassen đa luồng (Multithreading Strassen's method)

Theo đúng khung tuần tự ở Mục 4.2, chỉ thay bằng song song lồng nhau:

1. Chia các ma trận đầu vào A, B và ma trận kết quả C thành các ma trận con n/2 × n/2 như (27.6). Bước này tốn Θ(1) work và span nhờ tính chỉ số.
2. Tạo 10 ma trận S₁, S₂, …, S₁₀, mỗi ma trận cỡ n/2 × n/2 là tổng hoặc hiệu của hai ma trận ở bước 1. Có thể tạo cả 10 ma trận với Θ(n²) work và Θ(lg n) span bằng các vòng parallel for lồng nhau.
3. Dùng các ma trận con ở bước 1 và 10 ma trận ở bước 2, đệ quy sinh nhánh việc tính bảy tích n/2 × n/2 là P₁, P₂, …, P₇.
4. Tính các khối kết quả C₁₁, C₁₂, C₂₁, C₂₂ bằng cộng trừ các tổ hợp của các Pᵢ, lại bằng vòng parallel for lồng nhau. Có thể tính cả bốn khối với Θ(n²) work và Θ(lg n) span.

Để bản tổng hợp tự chứa, nhắc lại các công thức của Strassen từ Mục 4.2 (người tổng hợp chép lại và đã nhân ra kiểm tra):

```text
S₁ = B₁₂ − B₂₂     S₂ = A₁₁ + A₁₂     S₃ = A₂₁ + A₂₂     S₄ = B₂₁ − B₁₁
S₅ = A₁₁ + A₂₂     S₆ = B₁₁ + B₂₂     S₇ = A₁₂ − A₂₂     S₈ = B₂₁ + B₂₂
S₉ = A₁₁ − A₂₁     S₁₀ = B₁₁ + B₁₂

P₁ = A₁₁ · S₁      P₂ = S₂ · B₂₂      P₃ = S₃ · B₁₁      P₄ = A₂₂ · S₄
P₅ = S₅ · S₆       P₆ = S₇ · S₈       P₇ = S₉ · S₁₀

C₁₁ = P₅ + P₄ − P₂ + P₆        C₁₂ = P₁ + P₂
C₂₁ = P₃ + P₄                  C₂₂ = P₅ + P₁ − P₃ − P₇
```

(Ví dụ kiểm tra C₁₂: P₁ + P₂ = A₁₁B₁₂ − A₁₁B₂₂ + A₁₁B₂₂ + A₁₂B₂₂ = A₁₁B₁₂ + A₁₂B₂₂, đúng như (27.6).)

**Phân tích.** Bản tuần tự hoá trùng thuật toán tuần tự gốc, nên work bằng thời gian chạy của nó: Θ(n^lg 7). Về span, bảy lời gọi đệ quy chạy song song, đều trên ma trận cùng cỡ, và các bước 2, 4 có span Θ(lg n), nên ta được đúng truy hồi (27.7) như với P-MATRIX-MULTIPLY-RECURSIVE, nghiệm Θ(lg² n). Vậy độ song song của Strassen đa luồng là Θ(n^lg 7/lg² n): cao, dù thấp hơn của P-MATRIX-MULTIPLY-RECURSIVE (sách nói "slightly less"; như khối Lưu ý đã ghi, thực ra thấp hơn một hệ số n^0,19).

Bảng tổng kết Mục 27.2:

| Thuật toán | Work | Span | Độ song song |
|---|---|---|---|
| P-SQUARE-MATRIX-MULTIPLY | Θ(n³) | Θ(n) | Θ(n²) |
| P-MATRIX-MULTIPLY-RECURSIVE | Θ(n³) | Θ(lg² n) | Θ(n³/lg² n) |
| Strassen đa luồng | Θ(n^lg 7) | Θ(lg² n) | Θ(n^lg 7/lg² n) |

#### Ví dụ hôm nay

Thư viện BLAS đa luồng (OpenBLAS, Intel MKL) và các khung học máy nhân ma trận bằng cách chia khối rồi giao khối cho các nhân — tinh thần giống P-MATRIX-MULTIPLY-RECURSIVE, nhưng khối lá lớn (gộp lá) để vừa bộ nhớ đệm, và hầu như không dùng Strassen vì sai số làm tròn và hằng số lớn (theo hiểu biết của người tổng hợp). Trên GPU, mỗi ô c_ij hoặc mỗi khối nhỏ của C do một nhóm luồng tính — đúng kiểu "parallel for i, parallel for j" của P-SQUARE-MATRIX-MULTIPLY.

### 5. Sắp xếp trộn đa luồng (27.3 Multithreaded merge sort, trang 797–805)

#### 5.1. Cách song song hoá ngây thơ: MERGE-SORT′

Sắp xếp trộn tuần tự xuất hiện ở Mục 2.3.1, phân tích ở Mục 2.3.2 là Θ(n lg n). Vì nó đã dùng chia để trị, nó có vẻ là ứng viên tuyệt vời cho đa luồng bằng song song lồng nhau. Dễ dàng sửa mã giả để sinh nhánh lời gọi đệ quy thứ nhất:

```text
MERGE-SORT′(A, p, r)
1  if p < r
2      q = ⌊(p + r)/2⌋
3      spawn MERGE-SORT′(A, p, q)
4      MERGE-SORT′(A, q + 1, r)
5      sync
6      MERGE(A, p, q, r)
```

Như bản tuần tự, MERGE-SORT′ sắp xếp mảng con A[p..r]. Sau khi hai lời gọi đệ quy ở dòng 3 và 4 xong (sync ở dòng 5 bảo đảm điều đó), MERGE-SORT′ gọi đúng thủ tục MERGE của Mục 2.3.1 (trộn hai mảng con liền kề đã sắp xếp A[p..q] và A[q + 1..r] bằng cách chép ra hai mảng phụ rồi lần lượt lấy phần tử nhỏ hơn).

Để phân tích, trước hết phân tích MERGE: thời gian tuần tự để trộn n phần tử là Θ(n); vì MERGE tuần tự, cả work lẫn span của nó đều là Θ(n). Work của MERGE-SORT′ trên n phần tử:

```text
MS′₁(n) = 2MS′₁(n/2) + Θ(n)
        = Θ(n lg n)
```

bằng thời gian tuần tự của sắp xếp trộn. Vì hai lời gọi đệ quy có thể chạy song song, span thoả

```text
MS′∞(n) = MS′∞(n/2) + Θ(n)
        = Θ(n)
```

Vậy độ song song của MERGE-SORT′ là MS′₁(n)/MS′∞(n) = Θ(lg n) — không ấn tượng. Ví dụ sắp xếp 10 triệu phần tử: có thể tăng tốc tuyến tính trên vài bộ xử lý, nhưng không mở rộng hiệu quả lên hàng trăm bộ xử lý. (Người tổng hợp: lg 10⁷ ≈ 23,3; bỏ hằng số, độ song song chỉ cỡ vài chục. Cụ thể hơn, lần MERGE cuối cùng ở gốc một mình đã tốn n bước tuần tự, cộng n/2 ở tầng dưới, …, tổng span ≈ 2n.)

Nút cổ chai rõ ràng là thủ tục MERGE tuần tự. Thoạt nhìn trộn có vẻ vốn dĩ tuần tự, nhưng thực ra có thể làm phiên bản đa luồng bằng song song lồng nhau.

#### 5.2. Ý tưởng trộn song song (vẽ lại Hình 27.6)

Chiến lược chia để trị cho trộn đa luồng làm việc trên các mảng con của một mảng T. Giả sử cần trộn hai mảng con đã sắp xếp T[p₁..r₁] độ dài n₁ = r₁ − p₁ + 1 và T[p₂..r₂] độ dài n₂ = r₂ − p₂ + 1 vào một mảng con khác A[p₃..r₃] độ dài n₃ = r₃ − p₃ + 1 = n₁ + n₂. Không mất tổng quát, giả sử đơn giản hoá n₁ ≥ n₂.

Trước hết tìm phần tử giữa x = T[q₁] của T[p₁..r₁], với q₁ = ⌊(p₁ + r₁)/2⌋. Vì mảng con đã sắp xếp, x là một trung vị của T[p₁..r₁]: mọi phần tử của T[p₁..q₁ − 1] không lớn hơn x, mọi phần tử của T[q₁ + 1..r₁] không nhỏ hơn x. Sau đó dùng tìm kiếm nhị phân tìm chỉ số q₂ trong T[p₂..r₂] sao cho mảng con vẫn sắp xếp nếu chèn x vào giữa T[q₂ − 1] và T[q₂].

Rồi trộn T[p₁..r₁] và T[p₂..r₂] vào A[p₃..r₃] như sau:

1. Đặt q₃ = p₃ + (q₁ − p₁) + (q₂ − p₂).
2. Chép x vào A[q₃].
3. Đệ quy trộn T[p₁..q₁ − 1] với T[p₂..q₂ − 1], đặt kết quả vào A[p₃..q₃ − 1].
4. Đệ quy trộn T[q₁ + 1..r₁] với T[q₂..r₂], đặt kết quả vào A[q₃ + 1..r₃].

Khi tính q₃: q₁ − p₁ là số phần tử của T[p₁..q₁ − 1], q₂ − p₂ là số phần tử của T[p₂..q₂ − 1]; tổng của chúng là số phần tử đứng trước x trong A[p₃..r₃].

Hình 27.6 vẽ lại bằng chữ:

```text
          p₁         q₁         r₁            p₂        q₂       r₂
 T:  … │   ≤ x     │ x │   ≥ x    │  …  │    < x     │   ≥ x    │ …
          └──┬────┘  │  └───┬────┘          └──┬───┘   └───┬───┘
             │       │      │                  │           │
             │       │      └──────────┐  ┌────┘           │
             │       │   ┌─────────────┼──┘                │
             ▼       │   ▼             ▼                     ▼
          (trộn đệ quy)  │          (trộn đệ quy) ◀──────────┘
             │      (chép)                │
             ▼       ▼                    ▼
 A:  … │      ≤ x        │ x │         ≥ x          │ …
          p₃               q₃                   r₃

 · phần tô nhạt: T[p₁..q₁−1] (≤ x) và T[p₂..q₂−1] (< x) → trộn vào A[p₃..q₃−1]
 · phần tô đậm: T[q₁+1..r₁] (≥ x) và T[q₂..r₂] (≥ x)   → trộn vào A[q₃+1..r₃]
 · x = T[q₁] được chép thẳng vào A[q₃]
```

Trường hợp cơ sở là n₁ = n₂ = 0: không có việc gì để trộn hai mảng rỗng. Vì đã giả sử T[p₁..r₁] ít nhất dài bằng T[p₂..r₂] (n₁ ≥ n₂), chỉ cần kiểm tra n₁ = 0. Cũng phải bảo đảm đệ quy xử lý đúng khi chỉ một trong hai mảng rỗng — theo giả sử n₁ ≥ n₂, đó phải là T[p₂..r₂].

#### 5.3. Tìm kiếm nhị phân BINARY-SEARCH

Viết tìm kiếm nhị phân dạng tuần tự. BINARY-SEARCH(x, T, p, r) nhận khoá x và mảng con T[p..r], trả về:
- nếu T[p..r] rỗng (r < p): chỉ số p;
- nếu x ≤ T[p], tức x nhỏ hơn hoặc bằng mọi phần tử của T[p..r]: chỉ số p;
- nếu x > T[p]: chỉ số q lớn nhất trong khoảng p < q ≤ r + 1 sao cho T[q − 1] < x.

```text
BINARY-SEARCH(x, T, p, r)
1  low = p
2  high = max(p, r + 1)
3  while low < high
4      mid = ⌊(low + high)/2⌋
5      if x ≤ T[mid]
6          high = mid
7      else low = mid + 1
8  return high
```

Lời gọi BINARY-SEARCH(x, T, p, r) tốn Θ(lg n) thời gian tuần tự trong trường hợp xấu nhất, với n = r − p + 1 là cỡ mảng con (Exercise 2.3-5). Vì là thủ tục tuần tự, work và span xấu nhất của nó đều Θ(lg n). (Nhận xét của người tổng hợp: dòng 2 dùng max(p, r + 1) để khi mảng rỗng, r + 1 ≤ p, vòng while không chạy và trả về p. Bất biến: mọi chỉ số < low có T < x, và chỗ chèn nằm trong [low, high].)

Chạy tay (người tổng hợp): T[5..7] = ⟨1, 6, 7⟩, x = 5. low = 5, high = 8. mid = 6: x = 5 ≤ T[6] = 6 nên high = 6. mid = 5: 5 ≤ T[5] = 1 sai nên low = 6. Dừng, trả về 6: x chèn giữa T[5] = 1 và T[6] = 6.

#### 5.4. Thủ tục P-MERGE

Như MERGE, P-MERGE giả sử hai mảng con cần trộn nằm trong cùng một mảng. Khác MERGE, P-MERGE **không** giả sử chúng liền kề (không cần p₂ = r₁ + 1). Khác biệt nữa: P-MERGE nhận làm đối số một mảng con đầu ra A để ghi kết quả. Lời gọi P-MERGE(T, p₁, r₁, p₂, r₂, A, p₃) trộn hai mảng con đã sắp xếp T[p₁..r₁] và T[p₂..r₂] vào A[p₃..r₃], với r₃ = p₃ + (r₁ − p₁ + 1) + (r₂ − p₂ + 1) − 1 = p₃ + (r₁ − p₁) + (r₂ − p₂) + 1, không cần truyền vào.

```text
P-MERGE(T, p₁, r₁, p₂, r₂, A, p₃)
 1  n₁ = r₁ − p₁ + 1
 2  n₂ = r₂ − p₂ + 1
 3  if n₁ < n₂                       // ensure that n₁ ≥ n₂
 4      exchange p₁ with p₂
 5      exchange r₁ with r₂
 6      exchange n₁ with n₂
 7  if n₁ == 0                       // both empty?
 8      return
 9  else q₁ = ⌊(p₁ + r₁)/2⌋
10      q₂ = BINARY-SEARCH(T[q₁], T, p₂, r₂)
11      q₃ = p₃ + (q₁ − p₁) + (q₂ − p₂)
12      A[q₃] = T[q₁]
13      spawn P-MERGE(T, p₁, q₁ − 1, p₂, q₂ − 1, A, p₃)
14      P-MERGE(T, q₁ + 1, r₁, q₂, r₂, A, q₃ + 1)
15      sync
```

Dòng 1–2 tính độ dài n₁, n₂. Dòng 3–6 bảo đảm giả định n₁ ≥ n₂ (chú thích: "bảo đảm n₁ ≥ n₂"). Dòng 7 kiểm tra trường hợp cơ sở: T[p₁..r₁] rỗng (do đó T[p₂..r₂] cũng rỗng) thì trả về (chú thích: "cả hai rỗng?"). Dòng 9–15 cài chiến lược chia để trị. Dòng 9 tính điểm giữa của T[p₁..r₁]; dòng 10 tìm điểm q₂ trong T[p₂..r₂] sao cho mọi phần tử của T[p₂..q₂ − 1] nhỏ hơn T[q₁] (tức x) và mọi phần tử của T[q₂..r₂] ít nhất bằng T[q₁] (sách in nhầm là T[q₂..p₂]). Dòng 11 tính chỉ số q₃ của phần tử chia mảng đầu ra thành A[p₃..q₃ − 1] và A[q₃ + 1..r₃]; dòng 12 chép T[q₁] thẳng vào A[q₃]. Rồi đệ quy bằng song song lồng nhau: dòng 13 sinh nhánh bài toán con thứ nhất, dòng 14 gọi bài toán con thứ hai song song. sync ở dòng 15 bảo đảm các bài toán con xong trước khi thủ tục trả về. (Vì mọi thủ tục ngầm sync trước khi trả về, có thể bỏ dòng 15, nhưng viết ra là thói quen tốt.) Mã có chút khéo léo để chạy đúng khi T[p₂..r₂] rỗng: mỗi lời gọi đệ quy đặt một trung vị của T[p₁..r₁] vào mảng đầu ra, cho tới khi chính T[p₁..r₁] rỗng, kích hoạt trường hợp cơ sở.

Hai lời gọi ở dòng 13–14 độc lập: chúng đọc các vùng của T, ghi vào hai vùng rời nhau A[p₃..q₃ − 1] và A[q₃ + 1..r₃] (nhận xét của người tổng hợp; với điều kiện A và T là hai mảng khác nhau hoặc vùng ghi không chồng vùng đọc).

**Chạy tay P-MERGE (ví dụ của người tổng hợp).** T[1..7] = ⟨2, 5, 8, 9, 1, 6, 7⟩; trộn T[1..4] = ⟨2, 5, 8, 9⟩ với T[5..7] = ⟨1, 6, 7⟩ vào A[1..7].

```text
P-MERGE(T,1,4, 5,7, A,1): n₁=4, n₂=3. q₁=2, x=5. q₂=BINARY-SEARCH(5,T,5,7)=6.
    q₃ = 1 + (2−1) + (6−5) = 3.  A[3] = 5.
├─ spawn P-MERGE(T,1,1, 5,5, A,1)   trộn ⟨2⟩ với ⟨1⟩ vào A[1..2]
│     n₁=1,n₂=1. q₁=1, x=2. q₂=BINARY-SEARCH(2,T,5,5)=6. q₃=1+0+1=2. A[2]=2.
│     ├─ spawn P-MERGE(T,1,0, 5,5, A,1): n₁=0 < n₂=1 → đổi: p₁=5,r₁=5,
│     │     p₂=1,r₂=0. q₁=5, x=1. q₂=BINARY-SEARCH(1,T,1,0)=1 (mảng rỗng).
│     │     q₃=1+0+0=1. A[1]=1. Hai lời gọi con đều rỗng, trả về ngay.
│     └─ P-MERGE(T,2,1, 6,5, A,3): cả hai rỗng, trả về.
└─ P-MERGE(T,3,4, 6,7, A,4)         trộn ⟨8,9⟩ với ⟨6,7⟩ vào A[4..7]
      n₁=2,n₂=2. q₁=3, x=8. q₂=BINARY-SEARCH(8,T,6,7)=8. q₃=4+0+2=6. A[6]=8.
      ├─ spawn P-MERGE(T,3,2, 6,7, A,4): n₁=0 < n₂=2 → đổi: p₁=6,r₁=7,
      │     p₂=3,r₂=2. q₁=6, x=6. q₂=BINARY-SEARCH(6,T,3,2)=3 (mảng rỗng).
      │     q₃=4+0+0=4. A[4]=6.
      │     └─ P-MERGE(T,7,7, 3,2, A,5): q₁=7, x=7, q₃=5. A[5]=7.
      └─ P-MERGE(T,4,4, 8,7, A,7): q₁=4, x=9. q₂=BINARY-SEARCH(9,T,8,7)=8.
            q₃=7+0+0=7. A[7]=9.
Kết quả A[1..7] = ⟨1, 2, 5, 6, 7, 8, 9⟩ — đúng.
```

Ví dụ cho thấy cơ chế "khéo léo" mà sách nhắc: khi mảng ngắn hơn rỗng, các dòng 3–6 đổi vai hai mảng, BINARY-SEARCH trên mảng rỗng trả về ngay p₂, và mỗi tầng chỉ chép một trung vị sang A cho tới khi hết phần tử.

#### 5.5. Phân tích trộn đa luồng (Analysis of multithreaded merging)

**Span.** Gọi PM∞(n) là span của P-MERGE với n = n₁ + n₂ phần tử. Vì spawn ở dòng 13 và lời gọi ở dòng 14 song song logic, chỉ cần xét lời gọi tốn hơn. Mấu chốt: trong trường hợp xấu nhất, số phần tử trong mỗi lời gọi đệ quy không quá 3n/4. Thật vậy, dòng 3–6 bảo đảm n₂ ≤ n₁, nên n₂ = 2n₂/2 ≤ (n₁ + n₂)/2 = n/2. Trường hợp xấu nhất, một trong hai lời gọi trộn ⌊n₁/2⌋ phần tử của T[p₁..r₁] với cả n₂ phần tử của T[p₂..r₂], nên số phần tử của lời gọi đó là

```text
⌊n₁/2⌋ + n₂ ≤ n₁/2 + n₂/2 + n₂/2
            = (n₁ + n₂)/2 + n₂/2
            ≤ n/2 + n/4
            = 3n/4
```

Cộng thêm chi phí Θ(lg n) của BINARY-SEARCH ở dòng 10, được truy hồi cho span xấu nhất:

```text
PM∞(n) = PM∞(3n/4) + Θ(lg n)                                         (27.8)
```

(Trường hợp cơ sở có span Θ(1) vì dòng 1–8 chạy trong thời gian hằng.) Truy hồi không thuộc trường hợp nào của định lý thợ nhưng thoả điều kiện Exercise 4.6-2 (a = 1, b = 4/3, k = 1), nên PM∞(n) = Θ(lg² n).

**Work.** Gọi PM₁(n) là work của P-MERGE trên n phần tử; nó là Θ(n). Vì mỗi phần tử trong n phần tử phải được chép từ T sang A, PM₁(n) = Ω(n). Còn phải chứng minh PM₁(n) = O(n). Truy hồi cho work xấu nhất: tìm kiếm nhị phân ở dòng 10 tốn Θ(lg n) trong trường hợp xấu nhất, lấn át mọi việc khác ngoài các lời gọi đệ quy. Về các lời gọi đệ quy: dù hai lời gọi ở dòng 13 và 14 có thể trộn số phần tử khác nhau, cộng lại chúng trộn nhiều nhất n phần tử (thực ra n − 1, vì T[q₁] không tham gia lời gọi nào). Hơn nữa, như khi phân tích span, mỗi lời gọi xử lý không quá 3n/4 phần tử. Do đó

```text
PM₁(n) = PM₁(αn) + PM₁((1 − α)n) + O(lg n)                            (27.9)
```

với α nằm trong khoảng 1/4 ≤ α ≤ 3/4, và α thực tế có thể khác nhau ở mỗi tầng đệ quy.

Chứng minh (27.9) có nghiệm PM₁ = O(n) bằng phương pháp thế. Giả sử PM₁(n) ≤ c₁n − c₂ lg n với các hằng dương c₁, c₂. Thế vào:

```text
PM₁(n) ≤ (c₁αn − c₂ lg(αn)) + (c₁(1 − α)n − c₂ lg((1 − α)n)) + Θ(lg n)
       = c₁(α + (1 − α))n − c₂(lg(αn) + lg((1 − α)n)) + Θ(lg n)
       = c₁n − c₂(lg α + lg n + lg(1 − α) + lg n) + Θ(lg n)
       = c₁n − c₂ lg n − (c₂(lg n + lg(α(1 − α))) − Θ(lg n))
       ≤ c₁n − c₂ lg n
```

vì có thể chọn c₂ đủ lớn để c₂(lg n + lg(α(1 − α))) lấn át số hạng Θ(lg n). (Người tổng hợp: với 1/4 ≤ α ≤ 3/4 thì α(1 − α) ≥ 3/16, nên lg(α(1 − α)) ≥ lg(3/16) ≈ −2,42; với n đủ lớn, lg n − 2,42 ≥ (lg n)/2, và chọn c₂ lớn hơn hai lần hằng số trong Θ(lg n) là đủ.) Thêm nữa, chọn c₁ đủ lớn để thoả điều kiện biên. Vì work PM₁(n) vừa Ω(n) vừa O(n), PM₁(n) = Θ(n).

Ý nghĩa của giả thiết "trừ c₂ lg n" (nhận xét của người tổng hợp): nếu chỉ giả sử PM₁(n) ≤ c₁n thì thế vào được c₁n + Θ(lg n), không đóng được quy nạp; phải trừ bớt một số hạng bậc thấp hơn — cùng mẹo "trừ đi số hạng bậc thấp" của Mục 4.3.

**Độ song song** của P-MERGE: PM₁(n)/PM∞(n) = Θ(n/lg² n).

#### 5.6. P-MERGE-SORT

Có thủ tục trộn song song tốt, giờ ghép vào sắp xếp trộn đa luồng. Bản này giống MERGE-SORT′, nhưng nhận đối số là mảng con đầu ra B chứa kết quả. Cụ thể, lời gọi P-MERGE-SORT(A, p, r, B, s) sắp xếp các phần tử của A[p..r] và lưu chúng vào B[s..s + r − p].

```text
P-MERGE-SORT(A, p, r, B, s)
 1  n = r − p + 1
 2  if n == 1
 3      B[s] = A[p]
 4  else let T[1..n] be a new array
 5      q = ⌊(p + r)/2⌋
 6      q′ = q − p + 1
 7      spawn P-MERGE-SORT(A, p, q, T, 1)
 8      P-MERGE-SORT(A, q + 1, r, T, q′ + 1)
 9      sync
10      P-MERGE(T, 1, q′, q′ + 1, n, B, s)
```

Sau khi dòng 1 tính số phần tử n của A[p..r], dòng 2–3 xử lý trường hợp cơ sở mảng một phần tử. Dòng 4–6 chuẩn bị cho lời gọi sinh nhánh ở dòng 7 và lời gọi ở dòng 8, chạy song song. Cụ thể, dòng 4 cấp phát mảng tạm T gồm n phần tử để chứa kết quả của hai lần sắp xếp đệ quy. Dòng 5 tính chỉ số q chia A[p..r] thành A[p..q] và A[q + 1..r] để sắp xếp đệ quy; dòng 6 tính số phần tử q′ của mảng con thứ nhất A[p..q], dùng ở dòng 8 để xác định chỉ số bắt đầu trong T của kết quả sắp xếp A[q + 1..r]. Rồi lời gọi sinh nhánh và lời gọi đệ quy được thực hiện, tiếp theo là sync ở dòng 9 buộc thủ tục đợi lời gọi sinh nhánh xong. Cuối cùng dòng 10 gọi P-MERGE trộn hai mảng con đã sắp xếp, lúc này ở T[1..q′] và T[q′ + 1..n], vào mảng con đầu ra B[s..s + r − p].

Chạy tay ngắn (người tổng hợp): A[1..4] = ⟨4, 1, 3, 2⟩, gọi P-MERGE-SORT(A, 1, 4, B, 1). n = 4, q = 2, q′ = 2, T[1..4] mới. Lời gọi sinh nhánh sắp A[1..2] = ⟨4, 1⟩ vào T[1..2]: bên trong, mảng tạm T′[1..2] nhận ⟨4⟩ và ⟨1⟩, P-MERGE ghi ⟨1, 4⟩ vào T[1..2]. Song song, lời gọi thường sắp A[3..4] = ⟨3, 2⟩ vào T[3..4] = ⟨2, 3⟩. Sau sync, P-MERGE(T, 1, 2, 3, 4, B, 1) trộn ⟨1, 4⟩ với ⟨2, 3⟩: x = T[1] = 1 (q₁ = ⌊3/2⌋ = 1), q₂ = 3, q₃ = 1, B[1] = 1; nửa phải trộn ⟨4⟩ với ⟨2, 3⟩ vào B[2..4], cho B = ⟨1, 2, 3, 4⟩.

#### 5.7. Phân tích sắp xếp trộn đa luồng (Analysis of multithreaded merge sort)

**Work** PMS₁(n) dễ hơn nhiều so với work của P-MERGE:

```text
PMS₁(n) = 2PMS₁(n/2) + PM₁(n)
        = 2PMS₁(n/2) + Θ(n)
```

giống truy hồi (4.4) của MERGE-SORT thường ở Mục 2.3.1, nghiệm PMS₁(n) = Θ(n lg n) theo trường hợp 2 của định lý thợ.

**Span** xấu nhất PMS∞(n): hai lời gọi đệ quy ở dòng 7 và 8 song song logic nên bỏ qua một cái:

```text
PMS∞(n) = PMS∞(n/2) + PM∞(n)
        = PMS∞(n/2) + Θ(lg² n)                                        (27.10)
```

Như (27.8), định lý thợ không áp dụng cho (27.10) nhưng Exercise 4.6-2 thì có (a = 1, b = 2, k = 2). Nghiệm là PMS∞(n) = Θ(lg³ n), nên span của P-MERGE-SORT là Θ(lg³ n).

**Độ song song.** Trộn song song cho P-MERGE-SORT lợi thế lớn về độ song song so với MERGE-SORT′ (vốn gọi MERGE tuần tự, chỉ có độ song song Θ(lg n)):

```text
PMS₁(n)/PMS∞(n) = Θ(n lg n)/Θ(lg³ n)
                = Θ(n/lg² n)
```

tốt hơn nhiều cả về lý thuyết lẫn thực tế. Ví dụ số của người tổng hợp với n = 10⁷, bỏ hằng số: lg n ≈ 23,25, lg² n ≈ 540, nên độ song song khoảng 10⁷/540 ≈ 18.500, so với khoảng 23 của MERGE-SORT′.

Một cài đặt tốt trong thực tế sẽ hy sinh một phần độ song song bằng cách **gộp trường hợp cơ sở** để giảm các hằng số ẩn trong ký hiệu tiệm cận. Cách thẳng thắn là chuyển sang một thuật toán sắp xếp tuần tự thông thường, có thể là quicksort, khi mảng đủ nhỏ.

Bảng tổng kết Mục 27.3:

| Thủ tục | Work | Span | Độ song song |
|---|---|---|---|
| MERGE (tuần tự) | Θ(n) | Θ(n) | Θ(1) |
| MERGE-SORT′ | Θ(n lg n) | Θ(n) | Θ(lg n) |
| BINARY-SEARCH | Θ(lg n) | Θ(lg n) | Θ(1) |
| P-MERGE | Θ(n) | Θ(lg² n) | Θ(n/lg² n) |
| P-MERGE-SORT | Θ(n lg n) | Θ(lg³ n) | Θ(n/lg² n) |

#### Ví dụ hôm nay

Các hàm sắp xếp song song trong thư viện (ví dụ `std::sort` với chính sách `std::execution::par` của C++17, `Arrays.parallelSort` của Java, `par_sort` của Rayon) đều theo tinh thần "chia để trị với ngưỡng chuyển sang sắp xếp tuần tự", và nhiều cài đặt dùng chính kiểu trộn song song "lấy trung vị một bên, tìm nhị phân bên kia" — theo hiểu biết của người tổng hợp. Mẹo cấp phát mảng tạm T ở mỗi lời gọi trong P-MERGE-SORT thì trong thực tế thường được thay bằng một mảng phụ dùng chung, luân phiên vai trò nguồn/đích giữa các tầng đệ quy, để tránh chi phí cấp phát.

## Bài tập và bài toán cuối chương

### Bài tập Mục 27.1 (trang 791–792)

- **27.1-1:** Nếu ở dòng 4 của P-FIB ta *sinh nhánh* P-FIB(n − 2) thay vì gọi thường, work, span và độ song song tiệm cận thay đổi thế nào? *Người tổng hợp:* không đổi. Work vẫn là thời gian của bản tuần tự hoá, Θ(φⁿ) (chỉ thêm hằng số chi phí sinh nhánh). Span vẫn T∞(n) = max(T∞(n − 1), T∞(n − 2)) + Θ(1) = Θ(n), vì hai lời gọi vốn đã song song logic. Độ song song vẫn Θ(φⁿ/n). Khác biệt duy nhất là dag thêm một mạch (mạch giữa spawn thứ hai và sync gần như rỗng).
- **27.1-2:** Vẽ dag của P-FIB(5). Với mạch đơn vị, work, span, độ song song là bao nhiêu? Chỉ cách lập lịch dag trên 3 bộ xử lý bằng lập lịch tham lam, ghi trên mỗi mạch bước thời gian nó chạy. *Lời giải của người tổng hợp.* Đặt tên các lời gọi: A = P-FIB(5); A sinh nhánh B = P-FIB(4) và gọi C = P-FIB(3); B sinh nhánh D = P-FIB(3), gọi E = P-FIB(2); C sinh nhánh F = P-FIB(2), gọi lá G = P-FIB(1); D sinh nhánh H = P-FIB(2), gọi lá I = P-FIB(1); E sinh nhánh lá J = P-FIB(1), gọi lá K = P-FIB(0); F sinh nhánh lá L₁, gọi lá M₁; H sinh nhánh lá L₂, gọi lá M₂. Mỗi lời gọi A, B, C, D, E, F, H có ba mạch X.b, X.s, X.w; tám lá mỗi lá một mạch. **Work = 7 · 3 + 8 = 29**; **span = 10** (A.b → B.b → D.b → H.b → H.s → M₂ → H.w → D.w → B.w → A.w; khớp công thức S(n) = 2n); **độ song song = 2,9**. Một lịch tham lam trên 3 bộ xử lý (ưu tiên mạch có đường còn lại dài nhất, nhưng mọi bước đều chạy min(3, số mạch sẵn sàng) mạch):

  | Bước | Mạch chạy | Số mạch sẵn sàng |
  |---|---|---|
  | 1 | A.b | 1 |
  | 2 | A.s, B.b | 2 |
  | 3 | C.b, B.s, D.b | 3 |
  | 4 | H.b, F.b, E.b | 5 (còn C.s, D.s) |
  | 5 | H.s, D.s, L₂ | 8 |
  | 6 | M₂, F.s, E.s | 7 |
  | 7 | H.w, I, C.s | 7 |
  | 8 | D.w, L₁, M₁ | 6 |
  | 9 | J, K, F.w | 4 |
  | 10 | G, E.w | 2 |
  | 11 | B.w, C.w | 2 |
  | 12 | A.w | 1 |

  Tổng 29 mạch trong 12 bước. So sánh: cận dưới max(⌈29/3⌉, 10) = 10; cận tham lam (27.4) 29/3 + 10 ≈ 19,7; cận chặt hơn (27.5) (29 − 10)/3 + 10 ≈ 16,3.
- **27.1-3:** Chứng minh bộ lập lịch tham lam đạt cận chặt hơn một chút so với Định lý 27.1:

  ```text
  T_P ≤ (T₁ − T∞)/P + T∞                                             (27.5)
  ```
  *Chứng minh của người tổng hợp.* Mạch đơn vị. Gọi C là số bước đầy, I là số bước không đầy. Mỗi bước (đầy hay không) giảm span của phần chưa chạy đi nhiều nhất 1 (chỉ mạch bậc vào 0 được chạy), và mỗi bước không đầy giảm đúng 1. Gọi C′ là số bước đầy có giảm span; thì I + C′ = T∞. Đếm việc: P·C + I ≤ T₁ (mỗi bước không đầy chạy ít nhất 1 mạch), nên P·C ≤ T₁ − T∞ + C′. Do đó T_P = C + I = C + T∞ − C′ ≤ (T₁ − T∞)/P + C′/P + T∞ − C′ ≤ (T₁ − T∞)/P + T∞, vì C′/P ≤ C′.
- **27.1-4:** Dựng dag mà một lần chạy tham lam có thể tốn gần gấp đôi một lần chạy tham lam khác trên cùng số bộ xử lý. *Người tổng hợp:* mạch đầu nối tới một chuỗi L mạch nối tiếp và tới P·L mạch độc lập (cùng sẵn sàng ngay). Lần chạy tốt: mỗi bước chạy mạch kế tiếp của chuỗi cùng P − 1 mạch độc lập; sau L bước chuỗi xong, còn L mạch độc lập, cần thêm L/P bước: tổng ≈ L(1 + 1/P). Lần chạy xấu (vẫn tham lam): L bước đầu chọn toàn mạch độc lập (P mỗi bước), hết PL mạch; rồi chạy chuỗi L bước một mình: tổng ≈ 2L. Tỷ số 2/(1 + 1/P) gần 2 khi P lớn.
- **27.1-5:** Giáo sư Karan đo thuật toán đa luồng tất định của mình trên 4, 10 và 64 bộ xử lý của máy lý tưởng với bộ lập lịch tham lam, khai T₄ = 80 giây, T₁₀ = 42 giây, T₆₄ = 10 giây. Lập luận rằng bà ấy nói dối hoặc đo sai. (Gợi ý: dùng luật work, luật span và (27.5).) *Người tổng hợp:* luật work từ T₄ = 80: T₁ ≤ 4 · 80 = 320. Luật span từ T₆₄ = 10: T∞ ≤ 10. Bất đẳng thức (27.5) với P = 10: 42 = T₁₀ ≤ (T₁ − T∞)/10 + T∞, nên T₁ ≥ 10 · 42 − 9T∞ = 420 − 9T∞ ≥ 420 − 90 = 330 > 320. Mâu thuẫn.
- **27.1-6:** Cho thuật toán đa luồng nhân ma trận n × n với vectơ cỡ n đạt độ song song Θ(n²/lg n) mà vẫn giữ work Θ(n²). *Người tổng hợp:* parallel for theo i; với mỗi i, tính y_i bằng một phép rút gọn cộng chia để trị (như P-REDUCE của Problem 27-4) trên các tích a_ij·x_j, j = 1..n: hai nửa tính song song (spawn/sync) rồi cộng. Work Θ(n²), span Θ(lg n) + Θ(lg n) = Θ(lg n), độ song song Θ(n²/lg n). Không có tranh chấp vì mỗi lá tính tổng riêng, chỉ ghi y_i một lần.
- **27.1-7:** Xét mã giả chuyển vị tại chỗ ma trận n × n:

  ```text
  P-TRANSPOSE(A)
  1  n = A.rows
  2  parallel for j = 2 to n
  3      parallel for i = 1 to j − 1
  4          exchange a_ij with a_ji
  ```
  Phân tích work, span, độ song song. *Người tổng hợp:* các cặp (i, j) với i < j rời nhau nên không có tranh chấp. Work Θ(n²) (n(n − 1)/2 phép đổi). Span Θ(lg n) (vòng ngoài) + Θ(lg n) (vòng trong) = Θ(lg n). Độ song song Θ(n²/lg n).
- **27.1-8:** Thay parallel for ở dòng 3 của P-TRANSPOSE bằng for thường. *Người tổng hợp:* work vẫn Θ(n²); span là Θ(lg n) + max_j (j − 1) = Θ(n); độ song song Θ(n).
- **27.1-9:** Với bao nhiêu bộ xử lý thì hai phiên bản chương trình cờ vua chạy nhanh bằng nhau, giả sử T_P = T₁/P + T∞? *Người tổng hợp:* 2048/P + 1 = 1024/P + 8, tức 1024/P = 7, P = 1024/7 ≈ 146,3. Với ít hơn khoảng 146 bộ xử lý thì bản "tối ưu" nhanh hơn, nhiều hơn thì bản gốc nhanh hơn.

### Bài tập Mục 27.2 (trang 796–797)

- **27.2-1:** Vẽ dag của P-SQUARE-MATRIX-MULTIPLY trên ma trận 2 × 2, ghi rõ đỉnh nào ứng với mạch nào; dùng quy ước cạnh sinh nhánh và cạnh gọi hướng xuống, cạnh tiếp nối ngang sang phải, cạnh trả về hướng lên. Với mạch đơn vị, phân tích work, span, độ song song. *Người tổng hợp, theo quy ước đếm giống Hình 27.4* (mỗi parallel for là một thủ tục chia đôi; nút trong ba mạch; mỗi lá vòng ngoài hoà vào nút gốc của vòng trong; mỗi lá vòng trong là một mạch chạy hai lần lặp k; dòng 1–2 hoà vào mạch đen đầu tiên, dòng 8 hoà vào mạch trắng cuối): vòng ngoài [i: 1,2] có 3 mạch; hai vòng trong [j: 1,2] (cho i = 1 và i = 2) mỗi vòng 3 mạch; bốn lá (i, j) mỗi lá 1 mạch. Work = 3 + 2 · 3 + 4 = 13. Đường găng: b(ngoài) → s(ngoài) → b(trong, i = 2) → s(trong, i = 2) → lá (2, 2) → w(trong, i = 2) → w(ngoài) = 7. Độ song song 13/7 ≈ 1,86. Quy ước khác (tách riêng các mạch dòng 1–2, dòng 8, lá vòng ngoài) cho số hơi khác, nhưng cùng dạng.
- **27.2-2:** Làm lại 27.2-1 cho P-MATRIX-MULTIPLY-RECURSIVE. *Người tổng hợp (cùng quy ước):* lời gọi gốc có 8 mạch trước sync (mạch u₀ chạy dòng 1–5 tới spawn dòng 6; các mạch u₁ … u₆ mỗi mạch kết thúc ở một spawn dòng 7–12; mạch u₇ gọi dòng 13 tới sync); tám lời gọi con 1 × 1 mỗi lời gọi 1 mạch; sau sync là hai vòng parallel for 2 × 2 như bài 27.2-1, 13 mạch. Work = 8 + 8 + 13 = 29. Đường găng: u₀ → u₁ → … → u₇ (8 mạch) → lời gọi con ở dòng 13 (1) → phần cộng sau sync (7) = 16. Độ song song 29/16 ≈ 1,81. Nhận xét: với n nhỏ, chuỗi tiếp nối của bảy lệnh spawn làm span dài; với n lớn, các hằng số này chìm vào Θ(lg² n).
- **27.2-3:** Cho mã giả nhân hai ma trận n × n với work Θ(n³) nhưng span chỉ Θ(lg n). *Người tổng hợp:* parallel for i, parallel for j, rồi c_ij = rút gọn cộng song song (chia đôi khoảng k, spawn/sync, cộng hai nửa) của a_ik·b_kj, k = 1..n. Work Θ(n³); span Θ(lg n) + Θ(lg n) + Θ(lg n) = Θ(lg n); độ song song Θ(n³/lg n). (Cách khác: tính mọi tích d_ijk = a_ik·b_kj vào mảng ba chiều bằng ba vòng parallel for, rồi rút gọn theo k — cùng cận, tốn Θ(n³) bộ nhớ.)
- **27.2-4:** Cho thuật toán đa luồng hiệu quả nhân ma trận p × q với ma trận q × r, phải rất song song kể cả khi một trong p, q, r bằng 1. *Người tổng hợp:* parallel for i = 1..p, parallel for j = 1..r, c_ij = rút gọn cộng song song theo k = 1..q. Work Θ(pqr); span Θ(lg p + lg r + lg q); độ song song Θ(pqr/(lg p + lg q + lg r)). Nếu p = r = 1 (tích vô hướng) vẫn có độ song song Θ(q/lg q) nhờ rút gọn theo k; nếu q = 1 (tích ngoài) vẫn có Θ(pr/lg(pr)) nhờ hai vòng ngoài. Cách chia để trị theo chiều lớn nhất cũng đạt cận tương tự.
- **27.2-5:** Cho mã giả chuyển vị tại chỗ ma trận n × n bằng chia để trị thành bốn khối n/2 × n/2. *Người tổng hợp:* hai thủ tục. TRANSPOSE-DIAG(X) cho khối vuông trên đường chéo: nếu 1 × 1 thì xong; ngược lại spawn TRANSPOSE-DIAG(X₁₁), spawn TRANSPOSE-DIAG(X₂₂), gọi TRANSPOSE-SWAP(X₁₂, X₂₁), sync. TRANSPOSE-SWAP(Y, Z) đổi Y với Zᵀ (Y, Z cùng cỡ, đối xứng qua đường chéo): nếu 1 × 1 thì đổi hai phần tử; ngược lại sinh nhánh song song bốn lời gọi TRANSPOSE-SWAP(Y₁₁, Z₁₁), (Y₁₂, Z₂₁), (Y₂₁, Z₁₂), (Y₂₂, Z₂₂), rồi sync. Các lời gọi chạm vùng rời nhau nên không tranh chấp. Work Θ(n²). Span: SWAP S(n) = S(n/2) + Θ(1) = Θ(lg n); DIAG D(n) = max(D(n/2), S(n/2)) + Θ(1) = Θ(lg n). Độ song song Θ(n²/lg n).
- **27.2-6:** Cho cài đặt đa luồng hiệu quả của thuật toán Floyd-Warshall (Mục 25.2: d_ij^(k) = min(d_ij^(k−1), d_ik^(k−1) + d_kj^(k−1)), k = 1..n). *Người tổng hợp:* vòng k phải tuần tự (bước k cần kết quả bước k − 1); trong mỗi bước k: parallel for i, parallel for j tính D^(k) từ D^(k−1) (dùng hai ma trận luân phiên để mọi lần lặp độc lập). Work Θ(n³), span n · Θ(lg n) = Θ(n lg n), độ song song Θ(n²/lg n). (Dùng một ma trận tại chỗ thì về giá trị vẫn đúng khi không có chu trình âm, vì hàng k và cột k không đổi ở bước k, nhưng về hình thức vẫn có lệnh đọc và ghi cùng ô song song — trái quy ước "không tranh chấp" của chương.)

### Bài tập Mục 27.3 (trang 804–805)

- **27.3-1:** Giải thích cách gộp trường hợp cơ sở của P-MERGE. *Người tổng hợp:* khi n = n₁ + n₂ nhỏ hơn một ngưỡng g, gọi một thủ tục trộn tuần tự kiểu MERGE ghi thẳng vào A[p₃..r₃] (hai chỉ số chạy trên hai mảng nguồn). Work vẫn Θ(n); span thành Θ(lg² n + g); ngưỡng g cỡ vài nghìn phần tử trong thực tế để chi phí sinh nhánh không đáng kể.
- **27.3-2:** Thay vì tìm trung vị của mảng dài hơn như P-MERGE, tìm trung vị của *toàn bộ* phần tử hai mảng đã sắp xếp bằng kết quả Exercise 9.3-8 (tìm trung vị của hợp hai mảng đã sắp xếp trong O(lg n)). Cho mã giả trộn đa luồng dùng thủ tục này và phân tích. *Người tổng hợp:* tìm k = ⌈n/2⌉-phần tử nhỏ nhất của hợp hai mảng, đồng thời có hai vị trí cắt i trong mảng 1 và j trong mảng 2 (i + j = k); đệ quy song song trộn T[p₁..i] với T[p₂..j] vào nửa đầu A và phần còn lại vào nửa sau. Mỗi lời gọi nhận đúng khoảng n/2 phần tử. Span PM∞(n) = PM∞(n/2) + Θ(lg n) = Θ(lg² n); work W(n) = 2W(n/2) + Θ(lg n) = Θ(n). Cùng bậc với P-MERGE nhưng chia cân hơn (hằng số tốt hơn), không cần đổi vai hai mảng.
- **27.3-3:** Cho thuật toán đa luồng hiệu quả phân hoạch một mảng quanh chốt như PARTITION (Mục 7.1); không cần tại chỗ; càng song song càng tốt. (Gợi ý: có thể cần mảng phụ và nhiều lượt duyệt.) *Người tổng hợp:* (1) parallel for đặt cờ f[i] = 1 nếu A[i] ≤ x, ngược lại 0 (bỏ chốt); (2) tính tổng tiền tố của f bằng P-SCAN-3 (Problem 27-4), cho mỗi phần tử ≤ x vị trí đích; (3) parallel for chép các phần tử ≤ x vào B theo vị trí đó; (4) làm tương tự với cờ 1 − f cho các phần tử > x, đặt sau chốt; (5) đặt chốt ở giữa, chép B về A nếu cần. Work Θ(n), span Θ(lg n), độ song song Θ(n/lg n). Kết quả còn giữ thứ tự tương đối (ổn định), khác PARTITION.
- **27.3-4:** Cho phiên bản đa luồng của RECURSIVE-FFT (Chương 30), càng song song càng tốt. *Người tổng hợp:* tách a thành hệ số chẵn a^[0] và lẻ a^[1] bằng parallel for; spawn đệ quy FFT(a^[0]), gọi FFT(a^[1]), sync; vòng "bướm" k = 0..n/2 − 1 viết thành parallel for, tính ω_n^k trực tiếp (thay vì nhân dồn ω = ω·ω_n, vốn tạo phụ thuộc giữa các lần lặp). Work Θ(n lg n); span S(n) = S(n/2) + Θ(lg n) = Θ(lg² n); độ song song Θ(n/lg n).
- **27.3-5 ★:** Cho phiên bản đa luồng của RANDOMIZED-SELECT (Chương 9), càng song song càng tốt. (Gợi ý: dùng thuật toán phân hoạch của 27.3-3.) *Người tổng hợp:* giữ nguyên cấu trúc (chọn chốt ngẫu nhiên, phân hoạch, đệ quy một phía), chỉ thay phân hoạch bằng phân hoạch song song span Θ(lg n). Work kỳ vọng Θ(n) như bản tuần tự. Mỗi lần phân hoạch, với xác suất hằng số mảng giảm theo một tỷ lệ hằng, nên số tầng kỳ vọng O(lg n), span kỳ vọng O(lg² n); độ song song (theo định nghĩa E[T₁]/E[T∞] của Problem 27-6) Θ(n/lg² n).
- **27.3-6 ★:** Chỉ cách song song hoá SELECT của Mục 9.3, càng song song càng tốt. *Người tổng hợp:* chia nhóm 5 và tìm trung vị mỗi nhóm bằng parallel for (span Θ(lg n)); đệ quy tìm trung vị của các trung vị; phân hoạch song song quanh nó (span Θ(lg n)); đệ quy một phía. Hai lời gọi đệ quy phải nối tiếp (lời gọi thứ hai cần chốt từ lời gọi thứ nhất), nên span S(n) = S(n/5) + S(7n/10) + Θ(lg n). Vì (1/5)^p + (7/10)^p = 1 khi p ≈ 0,84, theo phương pháp Akra–Bazzi (theo hiểu biết của người tổng hợp) S(n) = Θ(n^0,84); work Θ(n); độ song song chỉ Θ(n^0,16). SELECT tất định khó song song hoá tốt; trong thực tế bản ngẫu nhiên (27.3-5) tốt hơn hẳn.

### Problem 27-1: Cài vòng lặp song song bằng song song lồng nhau (Implementing parallel loops using nested parallelism)

Xét thuật toán cộng từng cặp hai mảng n phần tử A[1..n], B[1..n], ghi tổng vào C[1..n]:

```text
SUM-ARRAYS(A, B, C)
1  parallel for i = 1 to A.length
2      C[i] = A[i] + B[i]
```

- **(a)** Viết lại vòng song song trong SUM-ARRAYS bằng song song lồng nhau (spawn và sync) theo kiểu MAT-VEC-MAIN-LOOP; phân tích độ song song. *Người tổng hợp:* SUM-ARRAYS-AUX(A, B, C, i, j): nếu i == j thì C[i] = A[i] + B[i]; ngược lại mid = ⌊(i + j)/2⌋, spawn SUM-ARRAYS-AUX(A, B, C, i, mid), SUM-ARRAYS-AUX(A, B, C, mid + 1, j), sync. Work Θ(n), span Θ(lg n), độ song song Θ(n/lg n).

Xét cách cài khác, có một giá trị kích thước hạt grain-size cần chọn:

```text
SUM-ARRAYS′(A, B, C)
1  n = A.length
2  grain-size = ?                      // to be determined
3  r = ⌈n/grain-size⌉
4  for k = 0 to r − 1
5      spawn ADD-SUBARRAY(A, B, C, k · grain-size + 1,
                          min((k + 1) · grain-size, n))
6  sync

ADD-SUBARRAY(A, B, C, i, j)
1  for k = i to j
2      C[k] = A[k] + B[k]
```

(Dòng 2: "cần xác định". Dòng 4–5 là vòng for *tuần tự* lần lượt sinh nhánh r khối, mỗi khối grain-size phần tử.)

- **(b)** Nếu grain-size = 1, độ song song là bao nhiêu? *Người tổng hợp:* vòng for ở dòng 4 sinh nhánh n con *tuần tự*, nên span Θ(n) (chuỗi n mạch tiếp nối trong cha) dù mỗi con chỉ tốn Θ(1); work Θ(n); độ song song Θ(1).
- **(c)** Cho công thức span của SUM-ARRAYS′ theo n và grain-size = g; tìm g tốt nhất để cực đại hoá độ song song. *Người tổng hợp:* span = Θ(r + g) = Θ(n/g + g) (chuỗi r lệnh spawn cộng khối cuối dài g). Cực tiểu khi n/g = g, tức g = √n: span Θ(√n), độ song song Θ(√n) — vẫn kém Θ(n/lg n) của cách chia đôi đệ quy ở (a).

### Problem 27-2: Tiết kiệm bộ nhớ tạm khi nhân ma trận (Saving temporary space in matrix multiplication)

P-MATRIX-MULTIPLY-RECURSIVE phải cấp phát ma trận tạm T cỡ n × n, có thể làm hằng số ẩn trong Θ xấu đi. Nhưng nó có độ song song cao: bỏ hằng số, độ song song khi nhân ma trận 1000 × 1000 là khoảng 1000³/10² = 10⁷, vì lg 1000 ≈ 10. Hầu hết máy song song có ít hơn nhiều so với 10 triệu bộ xử lý.

- **(a)** Mô tả thuật toán đa luồng đệ quy bỏ được ma trận tạm T, đổi lại span tăng lên Θ(n). (Gợi ý: tính C = C + AB theo khung của P-MATRIX-MULTIPLY-RECURSIVE, nhưng khởi tạo C song song và đặt một sync ở chỗ khéo chọn.) *Người tổng hợp:*

  ```text
  P-MATRIX-MULTIPLY-ADD(C, A, B)          // C = C + AB
  1  n = A.rows
  2  if n == 1
  3      c₁₁ = c₁₁ + a₁₁b₁₁
  4  else partition A, B, C into n/2 × n/2 submatrices
  5      spawn P-MATRIX-MULTIPLY-ADD(C₁₁, A₁₁, B₁₁)
  6      spawn P-MATRIX-MULTIPLY-ADD(C₁₂, A₁₁, B₁₂)
  7      spawn P-MATRIX-MULTIPLY-ADD(C₂₁, A₂₁, B₁₁)
  8      P-MATRIX-MULTIPLY-ADD(C₂₂, A₂₁, B₁₂)
  9      sync
  10     spawn P-MATRIX-MULTIPLY-ADD(C₁₁, A₁₂, B₂₁)
  11     spawn P-MATRIX-MULTIPLY-ADD(C₁₂, A₁₂, B₂₂)
  12     spawn P-MATRIX-MULTIPLY-ADD(C₂₁, A₂₂, B₂₁)
  13     P-MATRIX-MULTIPLY-ADD(C₂₂, A₂₂, B₂₂)
  14     sync
  ```
  Thủ tục ngoài: parallel for đặt C = 0 (span Θ(lg n)), rồi gọi P-MATRIX-MULTIPLY-ADD(C, A, B). sync ở dòng 9 ngăn hai lời gọi cùng cộng vào một khối Cᵢⱼ cùng lúc (tranh chấp).
- **(b)** Truy hồi cho work và span. *Người tổng hợp:* work W(n) = 8W(n/2) + Θ(1) = Θ(n³); span S(n) = 2S(n/2) + Θ(1) = Θ(n) (hai đợt nối tiếp, mỗi đợt bốn lời gọi song song cỡ n/2).
- **(c)** Phân tích độ song song; bỏ hằng số, ước lượng với ma trận 1000 × 1000; so với P-MATRIX-MULTIPLY-RECURSIVE. *Người tổng hợp:* Θ(n³)/Θ(n) = Θ(n²); với n = 1000 khoảng 10⁶ — ít hơn 10⁷ mười lần nhưng vẫn vượt xa số bộ xử lý thực tế, nên theo quy tắc "độ dư ≥ 10", bỏ ma trận tạm là đáng.

### Problem 27-3: Thuật toán ma trận đa luồng (Multithreaded matrix algorithms)

- **(a)** Song song hoá LU-DECOMPOSITION (Chương 28) bằng mã giả đa luồng, càng song song càng tốt; phân tích work, span, độ song song. *Người tổng hợp:* vòng k = 1..n tuần tự; trong mỗi bước k, vòng tính các phần tử cột của L (l_ik = a_ik/a_kk, i > k) và hàng của U thành parallel for; vòng lồng cập nhật phần bù Schur a_ij = a_ij − l_ik·u_kj (i, j > k) thành hai parallel for lồng. Work Θ(n³), span n · Θ(lg n) = Θ(n lg n), độ song song Θ(n²/lg n).
- **(b)** Làm tương tự cho LUP-DECOMPOSITION. *Người tổng hợp:* thêm bước tìm hàng chốt (giá trị tuyệt đối lớn nhất trong cột k) bằng rút gọn max song song, span Θ(lg n), và đổi hai hàng bằng parallel for, span Θ(lg n). Cùng cận: work Θ(n³), span Θ(n lg n), độ song song Θ(n²/lg n).
- **(c)** Làm tương tự cho LUP-SOLVE. *Người tổng hợp:* thế xuôi y_i = b_π[i] − Σ_{j<i} l_ij·y_j và thế ngược đều tuần tự theo i, nhưng mỗi tổng là một rút gọn cộng song song span Θ(lg n). Work Θ(n²), span Θ(n lg n), độ song song Θ(n/lg n).
- **(d)** Làm tương tự cho thuật toán đa luồng dựa trên phương trình (28.13) để nghịch đảo ma trận đối xứng xác định dương. *Người tổng hợp (chưa chắc (28.13) đúng là công thức này, không tra cứu):* dùng công thức khối với phần bù Schur S = D − C B⁻¹ Cᵀ: A⁻¹ gồm các khối B⁻¹ + B⁻¹CᵀS⁻¹CB⁻¹, −B⁻¹CᵀS⁻¹, −S⁻¹CB⁻¹, S⁻¹. Hai lần nghịch đảo đệ quy (B rồi S) phải nối tiếp; các phép nhân ma trận dùng P-MATRIX-MULTIPLY-RECURSIVE (span Θ(lg² n)). Span I(n) = 2I(n/2) + Θ(lg² n) = Θ(n); work Θ(n³) (hoặc Θ(n^lg 7) nếu nhân bằng Strassen); độ song song Θ(n²).

### Problem 27-4: Rút gọn và tính tiền tố đa luồng (Multithreading reductions and prefix computations)

**⊗-rút gọn** (⊗-reduction) của mảng x[1..n], với ⊗ là toán tử kết hợp, là giá trị y = x[1] ⊗ x[2] ⊗ ⋯ ⊗ x[n]. Thủ tục sau tính ⊗-rút gọn của mảng con x[i..j] tuần tự:

```text
REDUCE(x, i, j)
1  y = x[i]
2  for k = i + 1 to j
3      y = y ⊗ x[k]
4  return y
```

- **(a)** Dùng song song lồng nhau cài thuật toán đa luồng P-REDUCE làm cùng việc với work Θ(n), span Θ(lg n). *Người tổng hợp:*

  ```text
  P-REDUCE(x, i, j)
  1  if i == j
  2      return x[i]
  3  else k = ⌊(i + j)/2⌋
  4      left = spawn P-REDUCE(x, i, k)
  5      right = P-REDUCE(x, k + 1, j)
  6      sync
  7      return left ⊗ right
  ```
  Đúng nhờ tính kết hợp của ⊗ (thứ tự các toán hạng giữ nguyên, nên không cần giao hoán). Work W(n) = 2W(n/2) + Θ(1) = Θ(n); span S(n) = S(n/2) + Θ(1) = Θ(lg n).

Bài toán liên quan là **⊗-tính tiền tố** (⊗-prefix computation), còn gọi **⊗-scan**: tạo mảng y[1..n] với y[1] = x[1], y[2] = x[1] ⊗ x[2], y[3] = x[1] ⊗ x[2] ⊗ x[3], …, y[n] = x[1] ⊗ x[2] ⊗ ⋯ ⊗ x[n] — mọi tiền tố của x được "cộng" bằng ⊗. Thủ tục tuần tự:

```text
SCAN(x)
1  n = x.length
2  let y[1..n] be a new array
3  y[1] = x[1]
4  for i = 2 to n
5      y[i] = y[i − 1] ⊗ x[i]
6  return y
```

Song song hoá SCAN không thẳng thắn: đổi for thành parallel for sẽ tạo tranh chấp, vì mỗi lần lặp phụ thuộc lần trước. Thủ tục sau tính song song nhưng kém hiệu quả:

```text
P-SCAN-1(x)
1  n = x.length
2  let y[1..n] be a new array
3  P-SCAN-1-AUX(x, y, 1, n)
4  return y

P-SCAN-1-AUX(x, y, i, j)
1  parallel for l = i to j
2      y[l] = P-REDUCE(x, 1, l)
```

- **(b)** Phân tích work, span, độ song song của P-SCAN-1. *Người tổng hợp:* work Σ_{l=1}^{n} Θ(l) = Θ(n²); span Θ(lg n) (vòng) + Θ(lg n) (P-REDUCE) = Θ(lg n); độ song song Θ(n²/lg n) — cao nhưng work gấp n lần bản tuần tự, nên không đáng.

Dùng song song lồng nhau có cách hiệu quả hơn:

```text
P-SCAN-2(x)
1  n = x.length
2  let y[1..n] be a new array
3  P-SCAN-2-AUX(x, y, 1, n)
4  return y

P-SCAN-2-AUX(x, y, i, j)
1  if i == j
2      y[i] = x[i]
3  else k = ⌊(i + j)/2⌋
4      spawn P-SCAN-2-AUX(x, y, i, k)
5      P-SCAN-2-AUX(x, y, k + 1, j)
6      sync
7      parallel for l = k + 1 to j
8          y[l] = y[k] ⊗ y[l]
```

- **(c)** Lập luận P-SCAN-2 đúng và phân tích. *Người tổng hợp:* quy nạp: sau P-SCAN-2-AUX(x, y, i, j), y[l] = x[i] ⊗ ⋯ ⊗ x[l] với mọi l ∈ [i, j]. Sau hai lời gọi đệ quy, y[i..k] là tiền tố của x[i..k] và y[k + 1..j] là tiền tố của x[k + 1..j]; dòng 7–8 nhân trái mỗi y[l] (l > k) với y[k] = x[i] ⊗ ⋯ ⊗ x[k], được x[i] ⊗ ⋯ ⊗ x[l] (dùng tính kết hợp). Vòng ở dòng 7 không tranh chấp vì y[k] chỉ được đọc, các y[l] khác nhau được ghi. Work W(n) = 2W(n/2) + Θ(n) = Θ(n lg n); span S(n) = S(n/2) + Θ(lg n) = Θ(lg² n); độ song song Θ(n/lg n).

Có thể cải tiến cả P-SCAN-1 và P-SCAN-2 bằng hai lượt duyệt dữ liệu: lượt đầu gom các "tổng" ⊗ của những mảng con liền kề vào mảng tạm t; lượt hai dùng t để tính y. Mã giả sau, với vài biểu thức bị bỏ trống:

```text
P-SCAN-3(x)
1  n = x.length
2  let y[1..n] and t[1..n] be new arrays
3  y[1] = x[1]
4  if n > 1
5      P-SCAN-UP(x, t, 2, n)
6      P-SCAN-DOWN(x[1], x, t, y, 2, n)
7  return y

P-SCAN-UP(x, t, i, j)
1  if i == j
2      return x[i]
3  else
4      k = ⌊(i + j)/2⌋
5      t[k] = spawn P-SCAN-UP(x, t, i, k)
6      right = P-SCAN-UP(x, t, k + 1, j)
7      sync
8      return ______                       // fill in the blank

P-SCAN-DOWN(v, x, t, y, i, j)
1  if i == j
2      y[i] = v ⊗ x[i]
3  else
4      k = ⌊(i + j)/2⌋
5      spawn P-SCAN-DOWN(______, x, t, y, i, k)        // fill in the blank
6      P-SCAN-DOWN(______, x, t, y, k + 1, j)          // fill in the blank
7      sync
```

- **(d)** Điền ba biểu thức còn thiếu ở dòng 8 của P-SCAN-UP và dòng 5, 6 của P-SCAN-DOWN; lập luận P-SCAN-3 đúng. (Gợi ý: chứng minh giá trị v truyền cho P-SCAN-DOWN(v, x, t, y, i, j) thoả v = x[1] ⊗ x[2] ⊗ ⋯ ⊗ x[i − 1].) *Lời giải của người tổng hợp:* dòng 8 của P-SCAN-UP: **return t[k] ⊗ right**; dòng 5 của P-SCAN-DOWN: **v**; dòng 6: **v ⊗ t[k]**. Lý do: P-SCAN-UP(x, t, i, j) trả về x[i] ⊗ ⋯ ⊗ x[j] và lưu t[k] = x[i] ⊗ ⋯ ⊗ x[k] ở mỗi nút. Theo gợi ý, nửa trái [i..k] nhận v = x[1..i − 1] (giữ nguyên); nửa phải [k + 1..j] cần x[1..k] = v ⊗ (x[i] ⊗ ⋯ ⊗ x[k]) = v ⊗ t[k]. Ở lá, y[i] = v ⊗ x[i] = x[1] ⊗ ⋯ ⊗ x[i]. Lời gọi đầu P-SCAN-DOWN(x[1], …, 2, n) thoả gợi ý với i = 2. Mỗi t[k] được ghi đúng một lần bởi đúng nút có điểm giữa k, nên không tranh chấp.

  Chạy tay với ⊗ = + và x = ⟨1, 2, 3, 4, 5⟩: P-SCAN-UP(2, 5): k = 3; t[3] = UP(2, 3) [k = 2, t[2] = x[2] = 2, right = 3, trả về 5]; right = UP(4, 5) [k = 4, t[4] = 4, right = 5, trả về 9]; trả về 5 + 9 = 14. Vậy t[2] = 2, t[3] = 5, t[4] = 4. P-SCAN-DOWN(1, 2, 5): k = 3; trái DOWN(1, 2, 3): k = 2, DOWN(1, 2, 2) cho y[2] = 1 + 2 = 3, DOWN(1 + t[2] = 3, 3, 3) cho y[3] = 3 + 3 = 6; phải DOWN(1 + t[3] = 6, 4, 5): k = 4, DOWN(6, 4, 4) cho y[4] = 10, DOWN(6 + t[4] = 10, 5, 5) cho y[5] = 15. Kết quả y = ⟨1, 3, 6, 10, 15⟩ — đúng.
- **(e)** Phân tích work, span, độ song song của P-SCAN-3. *Người tổng hợp:* cả UP và DOWN có W(n) = 2W(n/2) + Θ(1) = Θ(n) và S(n) = S(n/2) + Θ(1) = Θ(lg n). Vậy work Θ(n), span Θ(lg n), độ song song Θ(n/lg n) — tốt nhất trong ba bản (đây là thuật toán quét song song kinh điển kiểu Blelloch, theo hiểu biết của người tổng hợp).

### Problem 27-5: Đa luồng hoá một tính toán khuôn đơn giản (Multithreading a simple stencil calculation)

Khoa học tính toán đầy những thuật toán điền một mảng bằng giá trị phụ thuộc vào một số ô lân cận đã tính, cùng thông tin không đổi trong suốt quá trình. Mẫu các ô lân cận không đổi trong quá trình tính và gọi là **khuôn** (stencil). Ví dụ Mục 15.4 có thuật toán khuôn tính dãy con chung dài nhất: c[i, j] chỉ phụ thuộc c[i − 1, j], c[i, j − 1], c[i − 1, j − 1] và các phần tử x_i, y_j của hai dãy đầu vào; hai dãy cố định, thuật toán điền mảng hai chiều c sao cho c[i, j] được tính sau cả ba ô kia.

Bài toán xét tính toán khuôn đơn giản trên mảng n × n A, trong đó giá trị đặt vào A[i, j] chỉ phụ thuộc các giá trị A[i′, j′] với i′ ≤ i và j′ ≤ j (và tất nhiên i′ ≠ i hoặc j′ ≠ j): một ô chỉ phụ thuộc các ô ở trên và/hoặc bên trái nó, cùng thông tin tĩnh ngoài mảng. Giả sử khi các ô mà A[i, j] phụ thuộc đã điền xong thì điền A[i, j] tốn Θ(1) (như LCS-LENGTH). Chia A thành bốn mảng con n/2 × n/2:

```text
A = ⎛A₁₁ A₁₂⎞                                                         (27.11)
    ⎝A₂₁ A₂₂⎠
```

Điền A₁₁ đệ quy được ngay vì nó không phụ thuộc ba khối kia. Khi A₁₁ xong, có thể điền A₁₂ và A₂₁ đệ quy song song, vì cả hai phụ thuộc A₁₁ nhưng không phụ thuộc nhau. Cuối cùng điền A₂₂ đệ quy.

- **(a)** Cho mã giả đa luồng SIMPLE-STENCIL theo phân rã (27.11) (không cần lo chi tiết trường hợp cơ sở). Lập và giải truy hồi cho work và span theo n; độ song song? *Người tổng hợp:* SIMPLE-STENCIL(X): nếu X đủ nhỏ thì điền trực tiếp; ngược lại SIMPLE-STENCIL(X₁₁); spawn SIMPLE-STENCIL(X₁₂); SIMPLE-STENCIL(X₂₁); sync; SIMPLE-STENCIL(X₂₂). Work W(n) = 4W(n/2) + Θ(1) = Θ(n²). Span S(n) = 3S(n/2) + Θ(1) = Θ(n^lg 3) ≈ Θ(n^1,585). Độ song song Θ(n^(2 − lg 3)) ≈ Θ(n^0,415).
- **(b)** Sửa để chia thành chín mảng con n/3 × n/3, đệ quy với nhiều song song nhất có thể; phân tích; so độ song song với (a). *Người tổng hợp:* các khối A_ab (a, b ∈ {1, 2, 3}) điền theo "đường chéo ngược" a + b: đợt 1 {A₁₁}; đợt 2 {A₁₂, A₂₁}; đợt 3 {A₁₃, A₂₂, A₃₁}; đợt 4 {A₂₃, A₃₂}; đợt 5 {A₃₃}; các khối trong một đợt chạy song song, các đợt nối tiếp (sync giữa các đợt). Work Θ(n²); span S(n) = 5S(n/3) + Θ(1) = Θ(n^(log₃ 5)) ≈ Θ(n^1,465); độ song song Θ(n^(2 − log₃ 5)) ≈ Θ(n^0,535) — nhiều hơn (a) một hệ số khoảng n^0,12.
- **(c)** Tổng quát: chọn số nguyên b ≥ 2, chia mảng thành b² mảng con n/b × n/b, đệ quy song song tối đa. Work, span, độ song song theo n và b? Lập luận rằng với cách này độ song song phải là o(n) với mọi b ≥ 2. (Gợi ý: chỉ ra số mũ của n trong độ song song nhỏ hẳn hơn 1.) *Người tổng hợp:* có 2b − 1 đợt (theo a + b từ 2 tới 2b). Work Θ(n²); span S(n) = (2b − 1)S(n/b) + Θ(b) = Θ(n^(log_b(2b − 1))) (b là hằng); độ song song Θ(n^(2 − log_b(2b − 1))). Vì 2b − 1 > b nên log_b(2b − 1) > 1, số mũ 2 − log_b(2b − 1) < 1, độ song song o(n). (Khi b lớn, log_b(2b − 1) → 1 nhưng không bao giờ bằng 1.)
- **(d)** Cho mã giả đạt độ song song Θ(n/lg n). Lập luận bằng work và span rằng bài toán thực ra có độ song song nội tại Θ(n). Hoá ra bản chất chia để trị của mã giả đa luồng không cho phép đạt độ song song tối đa này. *Người tổng hợp:* điền theo đường chéo ngược của từng ô: for d = 2 to 2n (tuần tự), parallel for mọi ô (i, j) với i + j = d. Mỗi đường chéo tốn span Θ(lg n), có 2n − 1 đường chéo: span Θ(n lg n), work Θ(n²), độ song song Θ(n/lg n). Nội tại: dag phụ thuộc giữa các ô có đường dài nhất từ (1, 1) tới (n, n) gồm 2n − 1 ô, nên span tối thiểu Θ(n), work Θ(n²), độ song song nội tại Θ(n); chi phí Θ(lg n) của mỗi parallel for là cái giá của việc mô phỏng "rào chắn" bằng cây spawn.

### Problem 27-6: Thuật toán đa luồng ngẫu nhiên (Randomized multithreaded algorithms)

Như thuật toán tuần tự, đôi khi ta muốn cài thuật toán đa luồng ngẫu nhiên. Bài toán xét cách điều chỉnh các thước đo để xử lý hành vi kỳ vọng, và yêu cầu thiết kế, phân tích quicksort ngẫu nhiên đa luồng.

- **(a)** Giải thích cách sửa luật work (27.2), luật span (27.3) và cận tham lam (27.4) để dùng với kỳ vọng khi T_P, T₁, T∞ đều là biến ngẫu nhiên. *Người tổng hợp:* các bất đẳng thức đúng cho từng lần chạy, lấy kỳ vọng hai vế và dùng tính tuyến tính: E[T_P] ≥ E[T₁]/P, E[T_P] ≥ E[T∞], E[T_P] ≤ E[T₁]/P + E[T∞].
- **(b)** Xét thuật toán đa luồng ngẫu nhiên mà 1% số lần T₁ = 10⁴ và T₁₀.₀₀₀ = 1, còn 99% số lần T₁ = T₁₀.₀₀₀ = 10⁹. Lập luận rằng tăng tốc của thuật toán ngẫu nhiên nên định nghĩa là E[T₁]/E[T_P] chứ không phải E[T₁/T_P]. *Người tổng hợp:* E[T₁/T_P] = 0,01 · 10⁴ + 0,99 · 1 ≈ 101 — gợi ý thuật toán tăng tốc 101 lần. Nhưng E[T₁] = 100 + 0,99 · 10⁹ ≈ 9,9 · 10⁸ và E[T_P] = 0,01 + 0,99 · 10⁹ ≈ 9,9 · 10⁸, tỷ số ≈ 1,0000001: trung bình thời gian chờ không giảm chút nào, vì hầu như mọi lần chạy đều không tăng tốc. E[T₁]/E[T_P] phản ánh đúng thực tế.
- **(c)** Lập luận rằng độ song song của thuật toán ngẫu nhiên nên định nghĩa là E[T₁]/E[T∞]. *Người tổng hợp:* để khớp với (a): khi P ≪ E[T₁]/E[T∞] thì E[T_P] ≤ E[T₁]/P + E[T∞] ≈ E[T₁]/P, tức tăng tốc (theo định nghĩa ở (b)) xấp xỉ P — đúng vai trò của độ song song trong Hệ quả 27.3.
- **(d)** Đa luồng hoá RANDOMIZED-QUICKSORT (Chương 7) bằng song song lồng nhau (không song song hoá RANDOMIZED-PARTITION). Cho mã giả P-RANDOMIZED-QUICKSORT. *Người tổng hợp:*

  ```text
  P-RANDOMIZED-QUICKSORT(A, p, r)
  1  if p < r
  2      q = RANDOMIZED-PARTITION(A, p, r)
  3      spawn P-RANDOMIZED-QUICKSORT(A, p, q − 1)
  4      P-RANDOMIZED-QUICKSORT(A, q + 1, r)
  5      sync
  ```
  Hai lời gọi chạm hai vùng rời nhau A[p..q − 1] và A[q + 1..r] nên độc lập.
- **(e)** Phân tích. (Gợi ý: xem lại phân tích RANDOMIZED-SELECT.) *Người tổng hợp:* work kỳ vọng Θ(n lg n) (bản tuần tự hoá là RANDOMIZED-QUICKSORT). Span: S(n) = Θ(n) + max(S(q − 1), S(n − q)) — phân hoạch tuần tự ở gốc đã tốn Θ(n); đi theo nhánh lớn hơn giống hệt phân tích RANDOMIZED-SELECT, nên E[S(n)] = Θ(n). Độ song song E[T₁]/E[T∞] = Θ(lg n) — giống MERGE-SORT′; muốn tốt hơn phải dùng phân hoạch song song của Exercise 27.3-3 (khi đó span kỳ vọng O(lg² n)).

### Ghi chú chương (Chapter notes, trang 811–812)

- Máy tính song song, mô hình máy song song và mô hình thuật toán cho lập trình song song đã tồn tại dưới nhiều dạng từ lâu. Các ấn bản trước của sách có nội dung về **mạng sắp xếp** (sorting networks) và mô hình **PRAM** (Parallel Random-Access Machine — máy truy cập ngẫu nhiên song song). Mô hình **song song dữ liệu** (data-parallel) là một mô hình lập trình thuật toán phổ biến khác, lấy các phép toán trên vectơ và ma trận làm phép toán cơ bản.
- **Graham** và **Brent** chỉ ra tồn tại bộ lập lịch đạt cận của Định lý 27.1. **Eager, Zahorjan và Lazowska** chỉ ra *mọi* bộ lập lịch tham lam đạt cận này, và đề xuất phương pháp dùng work và span (dù chưa gọi tên như vậy) để phân tích thuật toán song song. **Blelloch** xây một mô hình lập trình thuật toán cho song song dữ liệu dựa trên work và span (ông gọi span là "độ sâu" — depth — của tính toán).
- **Blumofe và Leiserson** đưa ra thuật toán lập lịch phân tán cho đa luồng động dựa trên **"đánh cắp việc" ngẫu nhiên** (randomized work-stealing) và chứng minh nó đạt E[T_P] ≤ T₁/P + O(T∞). **Arora, Blumofe và Plaxton**, cùng **Blelloch, Gibbons và Matias**, cũng đưa ra các thuật toán lập lịch tính toán đa luồng động chứng minh được là tốt.
- Mã giả đa luồng và mô hình lập trình chịu ảnh hưởng lớn của dự án **Cilk** ở MIT và phần mở rộng **Cilk++** cho C++ do Cilk Arts, Inc. phân phối. Nhiều thuật toán trong chương xuất hiện trong ghi chép bài giảng chưa xuất bản của C. E. Leiserson và H. Prokop và đã được cài bằng Cilk hoặc Cilk++. Thuật toán sắp xếp trộn đa luồng lấy cảm hứng từ một thuật toán của **Akl**.
- Khái niệm **nhất quán tuần tự** là của **Lamport**.
- Theo hiểu biết của người tổng hợp (không tra cứu): Cilk Arts được Intel mua năm 2009, Cilk Plus từng nằm trong trình biên dịch của Intel và GCC rồi bị loại bỏ khoảng năm 2017–2018; ý tưởng đánh cắp việc thì sống tiếp trong hầu hết thư viện song song tác vụ hiện nay.

## Luận điểm cốt lõi

### Mệnh đề

Trên máy song song bộ nhớ chung, một thuật toán đa luồng động — mã giả tuần tự thêm spawn, sync, parallel for — được đánh giá đầy đủ bằng hai đại lượng độc lập với máy: khối lượng công việc T₁ và độ dài đường găng T∞. Mọi lịch đều cần ít nhất max(T₁/P, T∞) thời gian, và mọi bộ lập lịch tham lam đạt không quá T₁/P + T∞; do đó thuật toán tốt là thuật toán có T₁ bằng bản tuần tự tốt nhất (hiệu quả về work) và độ song song T₁/T∞ vượt xa số bộ xử lý. Chia để trị với các lời gọi đệ quy chạy song song, cộng việc song song hoá cả bước kết hợp (cộng ma trận, trộn), đạt đúng mục tiêu đó: nhân ma trận với span Θ(lg² n), sắp xếp trộn với span Θ(lg³ n).

### Giả định

- Máy tính song song lý tưởng: P bộ xử lý ngang sức, bộ nhớ chung nhất quán tuần tự, bỏ qua chi phí lập lịch, liên lạc, bộ nhớ đệm và tranh chấp băng thông.
- Bộ lập lịch tập trung, tham lam (để phân tích); thực tế là bộ lập lịch phân tán đánh cắp việc, đạt cận tương tự theo kỳ vọng.
- Các mạch song song logic phải độc lập: không có tranh chấp tất định (mã có tranh chấp coi là không hợp lệ).
- Vòng parallel for được cài bằng chia đôi đệ quy, nên tốn Θ(lg n) span cho n lần lặp.
- Chi phí cấp phát bộ nhớ (ma trận tạm T, mảng tạm T trong P-MERGE-SORT) được tính như hằng số hoặc gộp vào work, không phân tích riêng.
- Phân tích tiệm cận; hằng số của sinh nhánh được xem là nhỏ và được khấu hao (cây nhị phân đầy đủ có số nút trong ít hơn số lá).

### Cơ chế

1. **Diễn tả:** đánh dấu những gì *có thể* chạy song song (spawn cho lời gọi độc lập, parallel for cho lần lặp độc lập), sync trước khi dùng kết quả của con.
2. **Mô hình hoá:** một lần chạy là dag các mạch; work là tổng trọng số đỉnh, span là đường dài nhất.
3. **Phân tích:** work bằng thời gian của bản tuần tự hoá; span theo quy tắc nối tiếp cộng, song song lấy max; viết thành truy hồi (ví dụ M∞(n) = M∞(n/2) + Θ(lg n)), giải bằng định lý thợ hoặc Bài tập 4.6-2.
4. **Lập lịch:** bộ lập lịch tham lam: bước đầy ≤ ⌊T₁/P⌋, bước không đầy ≤ T∞ (mỗi bước không đầy cắt bớt một tầng của đường găng còn lại).
5. **Thiết kế:** tìm bước tuần tự dài nhất (MERGE tuần tự Θ(n), vòng k tuần tự Θ(n)) và chia để trị chính bước đó (P-MERGE, rút gọn song song), giữ work không đổi về bậc.
6. **Ngoại suy:** dùng T_P ≈ T₁/P + T∞ để dự báo hiệu năng trên máy lớn hơn máy đang đo (★Socrates).

### Bằng chứng và ví dụ tác giả đưa ra

- FIB và P-FIB: cây lời gọi FIB(6) (Hình 27.1); dag P-FIB(4) với 17 mạch và đường găng 8 mạch (Hình 27.2); độ song song 2,125; tổng quát Θ(φⁿ/n).
- Chứng minh Định lý 27.1 (đếm bước đầy và bước không đầy), Hệ quả 27.2 (hệ số 2) và 27.3 (tăng tốc gần P khi độ dư lớn); quy tắc "độ dư ≥ 10".
- Hình 27.3: work cộng; span cộng khi nối tiếp, lấy max khi song song.
- MAT-VEC và MAT-VEC-MAIN-LOOP (Hình 27.4): parallel for thành cây chia đôi; work Θ(n²), span Θ(n).
- RACE-EXAMPLE (Hình 27.5): in 1 thay vì 2; MAT-VEC-WRONG; Therac-25 và vụ mất điện Bắc Mỹ 2003.
- Câu chuyện ★Socrates: 65 s so với 40 s trên 32 bộ xử lý, 5 s so với 10 s trên 512 bộ xử lý.
- Ba thuật toán nhân ma trận đa luồng với work/span Θ(n³)/Θ(n), Θ(n³)/Θ(lg² n), Θ(n^lg 7)/Θ(lg² n).
- MERGE-SORT′ độ song song Θ(lg n); P-MERGE (Hình 27.6) với lập luận 3n/4 và chứng minh work Θ(n) bằng phép thế c₁n − c₂ lg n; P-MERGE-SORT độ song song Θ(n/lg² n).

### Kết luận và hàm ý cho người lập trình

- Hãy nghĩ theo hai con số: "việc tổng cộng" và "chuỗi phụ thuộc dài nhất". Tăng số luồng không bao giờ vượt được T∞; giảm T∞ quan trọng ngang giảm T₁ khi máy lớn.
- Một tối ưu hoá chỉ đo trên máy hiện tại có thể phản tác dụng trên máy lớn hơn (★Socrates); ước lượng T₁ và T∞ để ngoại suy.
- Đủ độ song song là đủ: độ dư khoảng 10 lần số lõi thường đã tốt; độ song song thừa có thể đổi lấy bộ nhớ ít hơn (Problem 27-2) hoặc hằng số nhỏ hơn (gộp lá).
- Đừng chỉ song song hoá lời gọi đệ quy; bước kết hợp tuần tự (trộn, cộng dồn) sẽ thành nút cổ chai (MERGE-SORT′ chỉ đạt Θ(lg n)).
- Tranh chấp dữ liệu là lỗi khó tìm nhất: giữ các nhánh song song độc lập — mỗi nhánh ghi vào vùng riêng (C₁₁ … T₂₂ trong P-MATRIX-MULTIPLY-RECURSIVE), cộng dồn bằng rút gọn chứ không ghi chung một biến (MAT-VEC-WRONG).
- Vòng lặp parallel for nên được cài bằng chia đôi đệ quy chứ không bằng một vòng sinh nhánh tuần tự (Problem 27-1: Θ(lg n) so với Θ(n) hay Θ(√n)).
- Gộp trường hợp cơ sở (chuyển sang thuật toán tuần tự khi bài toán nhỏ) để giảm chi phí sinh nhánh.

### Trong ngôn ngữ khoa học máy tính

T_P ≥ max(T₁/P, T∞); lập lịch tham lam: T_P ≤ T₁/P + T∞ (chặt hơn: (T₁ − T∞)/P + T∞) ≤ 2·T*_P; tăng tốc T₁/T_P ≤ min(P, T₁/T∞); độ dư T₁/(P·T∞). Ghép: nối tiếp (T₁, T∞) cộng; song song T₁ cộng, T∞ lấy max. parallel for n lần lặp: span Θ(lg n) + max iter∞(i). P-FIB: Θ(φⁿ)/Θ(n). MAT-VEC: Θ(n²)/Θ(n). P-SQUARE-MATRIX-MULTIPLY: Θ(n³)/Θ(n). P-MATRIX-MULTIPLY-RECURSIVE: Θ(n³)/Θ(lg² n). Strassen: Θ(n^lg 7)/Θ(lg² n). P-MERGE: Θ(n)/Θ(lg² n). P-MERGE-SORT: Θ(n lg n)/Θ(lg³ n), độ song song Θ(n/lg² n). P-REDUCE và P-SCAN-3: Θ(n)/Θ(lg n). Lập lịch đánh cắp việc ngẫu nhiên: E[T_P] ≤ T₁/P + O(T∞).

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| serial algorithm | thuật toán tuần tự | chạy trên máy một bộ xử lý, mỗi lúc một lệnh |
| parallel algorithm | thuật toán song song | cho phép nhiều lệnh chạy đồng thời |
| multithreaded algorithm | thuật toán đa luồng | thuật toán song song viết bằng spawn, sync, parallel |
| chip multiprocessor / multicore | bộ đa xử lý trên chip / đa nhân | một chip chứa nhiều nhân xử lý dùng chung bộ nhớ |
| cluster / supercomputer | cụm máy / siêu máy tính | nhiều máy nối mạng / máy song song cao cấp nhất |
| shared memory / distributed memory | bộ nhớ chung / bộ nhớ phân tán | mọi bộ xử lý thấy mọi ô nhớ / phải gửi thông điệp |
| static threading, thread | đa luồng tĩnh, luồng | "bộ xử lý ảo" do người lập trình quản lý |
| concurrency platform | nền tảng xử lý đồng thời | phần mềm điều phối, lập lịch tài nguyên song song |
| dynamic multithreading | đa luồng động | chỉ nêu song song logic, bộ lập lịch tự cân bằng tải |
| nested parallelism | song song lồng nhau | spawn trước một lời gọi, con lại sinh nhánh tiếp |
| parallel loop / parallel for | vòng lặp song song | các lần lặp được phép chạy đồng thời |
| concurrency keywords: spawn, sync, parallel | từ khoá đồng thời | ba từ khoá thêm vào mã giả |
| parent / child | cha / con | lời gọi thực hiện spawn / lời gọi được sinh nhánh |
| logical parallelism | song song logic | phần nào được phép chạy song song |
| scheduler | bộ lập lịch | quyết định mạch nào chạy trên bộ xử lý nào, lúc nào |
| serialization | bản tuần tự hoá | xoá các từ khoá đồng thời |
| multithreaded computation | tính toán đa luồng | tập lệnh thực thi lúc chạy của chương trình đa luồng |
| computation dag | đồ thị tính toán | dag các mạch và phụ thuộc giữa chúng |
| strand | mạch | chuỗi lệnh không chứa điều khiển song song |
| continuation / spawn / call / return edge | cạnh tiếp nối / sinh nhánh / gọi / trả về | bốn loại cạnh của dag |
| initial / final strand | mạch đầu / mạch cuối | mạch bắt đầu và kết thúc tính toán |
| (logically) in series / in parallel | nối tiếp / song song (logic) | có / không có đường đi giữa hai mạch |
| ideal parallel computer | máy tính song song lý tưởng | bộ xử lý ngang sức, bỏ qua chi phí lập lịch |
| sequential consistency | nhất quán tuần tự | bộ nhớ hành xử như các lệnh chạy theo một thứ tự tuyến tính |
| work (T₁) | khối lượng công việc | tổng thời gian mọi mạch; thời gian trên 1 bộ xử lý |
| span (T∞) | độ dài đường găng | đường dài nhất trong dag; thời gian với ∞ bộ xử lý |
| critical path | đường găng | đường dài nhất trong dag |
| work law / span law | luật work / luật span | T_P ≥ T₁/P / T_P ≥ T∞ |
| speedup | hệ số tăng tốc | T₁/T_P |
| linear / perfect linear speedup | tăng tốc tuyến tính / tuyến tính hoàn hảo | T₁/T_P = Θ(P) / = P |
| parallelism | độ song song | T₁/T∞ |
| (parallel) slackness | độ dư song song | (T₁/T∞)/P |
| on-line / distributed / centralized scheduler | bộ lập lịch trực tuyến / phân tán / tập trung | không biết trước / nhiều luồng hợp tác / biết toàn cục |
| greedy scheduler | bộ lập lịch tham lam | mỗi bước chạy càng nhiều mạch sẵn sàng càng tốt |
| complete / incomplete step | bước đầy / bước không đầy | ≥ P / < P mạch sẵn sàng |
| coarsen (the leaves) | gộp lá | cho mỗi lá chạy nhiều lần lặp để giảm chi phí sinh nhánh |
| grain size | kích thước hạt | số lần lặp gộp trong một tác vụ |
| deterministic / nondeterministic | tất định / không tất định | luôn cùng kết quả / có thể khác giữa các lần chạy |
| determinacy race | tranh chấp tất định | hai lệnh song song cùng truy cập một ô, ít nhất một lệnh ghi |
| race condition | tình trạng tranh chấp | lỗi do kết quả phụ thuộc thứ tự thực thi |
| mutual-exclusion lock | khoá loại trừ lẫn nhau | cơ chế đồng bộ chặn truy cập đồng thời |
| independent strands | mạch độc lập | không có tranh chấp giữa chúng |
| work-stealing | đánh cắp việc | bộ xử lý rảnh lấy việc từ hàng đợi của bộ xử lý khác |
| reduction / prefix computation (scan) | rút gọn / tính tiền tố (quét) | gộp cả mảng / mọi tiền tố bằng phép kết hợp ⊗ |
| associative operator | toán tử kết hợp | (a ⊗ b) ⊗ c = a ⊗ (b ⊗ c) |
| stencil | khuôn (tính toán) | mẫu ô lân cận cố định mà một ô phụ thuộc |
| PRAM | máy truy cập ngẫu nhiên song song | mô hình song song cũ, có ở ấn bản trước |
| data-parallel model | mô hình song song dữ liệu | phép toán vectơ/ma trận là phép cơ bản |

## Câu nói đáng nhớ

> "The concurrency keywords express the logical parallelism of the computation, indicating which parts of the computation may proceed in parallel." — Mục 27.1
>
> *Dịch: Các từ khoá đồng thời diễn tả song song logic của tính toán, chỉ ra những phần nào của tính toán có thể tiến hành song song.*

> "Indeed, our multithreaded pseudocode has the nice property that a serialization is always ordinary serial pseudocode to solve the same problem." — Mục 27.1
>
> *Dịch: Thật vậy, mã giả đa luồng của chúng ta có tính chất hay là bản tuần tự hoá luôn là mã giả tuần tự bình thường giải cùng bài toán.*

> "Specifically, once the number of processors exceeds the parallelism, the computation cannot possibly achieve perfect linear speedup." — Mục 27.1, các thước đo hiệu năng
>
> *Dịch: Cụ thể, một khi số bộ xử lý vượt quá độ song song, tính toán không thể nào đạt tăng tốc tuyến tính hoàn hảo.*

> "As a rule of thumb, a slackness of at least 10—that is, 10 times more parallelism than processors—generally suffices to achieve good speedup." — Mục 27.1, lập lịch
>
> *Dịch: Theo kinh nghiệm, độ dư ít nhất 10 — tức độ song song gấp 10 lần số bộ xử lý — thường đủ để đạt tăng tốc tốt.*

> "Race conditions are the bane of concurrency." — Mục 27.1, tranh chấp
>
> *Dịch: Tranh chấp là tai hoạ của lập trình đồng thời.*

> "The moral of the story is that work and span can provide a better means of extrapolating performance than can measured running times." — Mục 27.1, bài học cờ vua
>
> *Dịch: Bài học của câu chuyện là work và span có thể là phương tiện ngoại suy hiệu năng tốt hơn so với thời gian chạy đo được.*

> "Although merging might initially seem to be inherently serial, we can, in fact, fashion a multithreaded version of it by using nested parallelism." — Mục 27.3
>
> *Dịch: Dù thoạt nhìn phép trộn có vẻ vốn dĩ tuần tự, thực ra ta có thể dựng một phiên bản đa luồng của nó bằng song song lồng nhau.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: một mô hình nhỏ gọn mà giữ được toàn bộ bộ công cụ của sách

Chương chọn đúng một mô hình — fork-join với spawn/sync — và cho thấy nó hoà hợp hoàn toàn với phần còn lại của sách: work là thời gian chạy của bản tuần tự hoá (người đọc đã biết phân tích), span là một truy hồi mới cùng dạng (định lý thợ, Bài tập 4.6-2), và mọi ví dụ (Fibonacci, nhân ma trận, sắp xếp trộn, quicksort, select, FFT, LU, Floyd-Warshall, LCS) đều là thuật toán đã học. Định lý 27.1 với chứng minh nửa trang (đếm bước đầy, bước không đầy) là một trong những kết quả "đắt giá nhất trên mỗi dòng" của sách: nó tách bài toán song song thành hai phần độc lập — thuật toán chỉ cần lo T₁ và T∞, bộ lập lịch lo phần còn lại — và giải thích vì sao các nền tảng thực tế cho người lập trình chỉ nêu song song logic.

### Điểm mạnh: câu chuyện ★Socrates

Ví dụ cờ vua là cách dạy rất hiệu quả rằng "nhanh hơn trên máy hiện có" không có nghĩa là "nhanh hơn" — và rằng mô hình lý thuyết đơn giản T₁/P + T∞ có giá trị dự báo thực tế. Nó cũng cho thấy work và span là hai trục tối ưu khác nhau, có thể đánh đổi.

### Điểm mạnh: P-MERGE

Phép trộn song song với lập luận "mỗi bên không quá 3n/4" và chứng minh work Θ(n) qua truy hồi có α thay đổi theo tầng là một ví dụ hay về phân tích truy hồi không cân, và về mẹo "trừ một số hạng bậc thấp" trong phương pháp thế.

### Điểm yếu và chỗ đơn giản hoá

- **Bỏ qua bộ nhớ.** Mô hình lý tưởng không tính bộ nhớ đệm, băng thông, chia sẻ giả (false sharing) hay chi phí cấp phát. Trên máy thật, P-MATRIX-MULTIPLY-RECURSIVE cấp phát ma trận tạm ở *mọi* tầng (tổng bộ nhớ có thể rất lớn khi nhiều nhánh chạy cùng lúc), P-MERGE-SORT cấp phát mảng tạm ở mọi lời gọi; sách chỉ nhắc nhẹ (Problem 27-2) mà không phân tích không gian. Theo hiểu biết của người tổng hợp, các tài liệu sau này về Cilk có phân tích không gian ngăn xếp S_P ≤ P·S₁ cho lập lịch đánh cắp việc — chương không đề cập.
- **Bộ lập lịch tập trung, tham lam là lý tưởng hoá.** Không có bộ lập lịch thật nào biết trạng thái toàn cục miễn phí; kết quả cho bộ lập lịch thực tế (đánh cắp việc) chỉ được nêu ở Ghi chú chương, không chứng minh.
- **Chỉ một mô hình.** Chương bỏ hẳn mô hình bộ nhớ phân tán, truyền thông điệp, GPU/SIMD, và các thuật toán không tất định có khoá. Tác giả nói rõ đây là lựa chọn ("time will tell"), nhưng người đọc dễ có ấn tượng song song hoá chỉ là "thêm spawn".
- **Một số khẳng định thiếu chính xác nhỏ** (đã ghi trong khối Lưu ý): "phần lớn thứ tự cho kết quả đúng" trong RACE-EXAMPLE (thực ra 2/20), "slightly less" cho Strassen, lỗi in T[q₂..p₂], phép thế FIB chỉ cho cận trên.
- **Hằng số của sinh nhánh trong span.** Sách nói parallel for tốn Θ(lg n) span, nhưng vòng lặp sinh nhánh tuần tự (Problem 27-1) hay chuỗi bảy spawn liên tiếp ở P-MATRIX-MULTIPLY-RECURSIVE cho thấy cách viết mã ảnh hưởng span thực; với n nhỏ (Exercise 27.2-2), các hằng số này chiếm phần lớn đường găng.

### So với thực tế

Mô hình fork-join của chương là mô hình chủ đạo của lập trình song song trên máy đa nhân hiện nay (theo hiểu biết của người tổng hợp): Java ForkJoinPool, .NET Task Parallel Library, Intel oneTBB, OpenMP tasks, Rust Rayon, và Cilk (nay là OpenCilk) đều dùng lập lịch đánh cắp việc và có lời khuyên giống chương: tạo đủ tác vụ (độ dư), gộp lá (grain size), tránh tranh chấp. Tuy vậy, hiệu năng thực tế của các thuật toán như sắp xếp hay nhân ma trận thường bị giới hạn bởi băng thông bộ nhớ trước khi bị giới hạn bởi span: sắp xếp song song trên 64 lõi hiếm khi nhanh gấp 64 lần dù độ song song Θ(n/lg² n) rất lớn. Trên GPU, mô hình phổ biến là song song dữ liệu (rất nhiều luồng chạy cùng lệnh), gần với "data-parallel model" mà Ghi chú chương nhắc; các thuật toán quét song song (Problem 27-4) là viên gạch cơ bản ở đó.

### Liên hệ các chương khác

- Chương 2 ([C02-bat-dau.md](C02-bat-dau.md)): mô hình RAM tuần tự mà chương này mở rộng; MERGE và MERGE-SORT là đối tượng song song hoá ở Mục 27.3; tìm kiếm nhị phân (Exercise 2.3-5).
- Chương 3 ([C03-tang-truong-cua-ham.md](C03-tang-truong-cua-ham.md)): số Fibonacci, tỷ lệ vàng φ, (3.8) và (3.9) về phép mod dùng trong chứng minh Định lý 27.1.
- Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)): SQUARE-MATRIX-MULTIPLY, SQUARE-MATRIX-MULTIPLY-RECURSIVE, Strassen, định lý thợ và Bài tập 4.6-2 (truy hồi T(n) = aT(n/b) + Θ(n^(log_b a) lg^k n)).
- Chương 7 ([C07-quicksort.md](C07-quicksort.md)) và Chương 9 ([C09-trung-vi-va-thong-ke-thu-tu.md](C09-trung-vi-va-thong-ke-thu-tu.md)): PARTITION, RANDOMIZED-QUICKSORT, RANDOMIZED-SELECT, SELECT — các bài tập 27.3-3, 27.3-5, 27.3-6 và Problem 27-6.
- Chương 15 ([C15-quy-hoach-dong.md](C15-quy-hoach-dong.md)): LCS là ví dụ tính toán khuôn của Problem 27-5; nhiều bảng quy hoạch động có thể song song hoá theo đường chéo.
- Chương 24 ([C24-duong-di-ngan-nhat-tu-mot-nguon.md](C24-duong-di-ngan-nhat-tu-mot-nguon.md)): đường găng trong dag tìm trong Θ(V + E) — đúng là span của đồ thị tính toán.
- Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)): Floyd-Warshall đa luồng (Exercise 27.2-6).
- Chương 28 ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)) và Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)): LU/LUP và FFT là đối tượng song song hoá ở Problem 27-3 và Exercise 27.3-4; Chương 30 còn có một mạch FFT song song — một mô hình tính toán song song khác (mạch).
- Phụ lục B ([PB-tap-hop-va-cau-truc-roi-rac.md](PB-tap-hop-va-cau-truc-roi-rac.md)): cây nhị phân đầy đủ có số nút trong ít hơn số lá 1 (Exercise B.5-3), dùng để khấu hao chi phí sinh nhánh của parallel for.

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** giải thích work/span và luật Amdahl (theo hiểu biết của người tổng hợp, luật span là một dạng của luật Amdahl: phần tuần tự giới hạn tăng tốc); vì sao x = x + 1 từ hai luồng có thể mất cập nhật; viết tổng song song bằng chia đôi (P-REDUCE); viết tổng tiền tố song song (P-SCAN-3) — một câu hỏi kinh điển ở các công ty làm hệ thống/GPU; giải thích vì sao sắp xếp trộn song song cần trộn song song.
- **Lập trình thi đấu:** hầu như không dùng đa luồng; nhưng các kỹ thuật cấu trúc như "chia để trị trộn kết quả", "tổng tiền tố bằng cây", "điền bảng quy hoạch động theo đường chéo" xuất hiện thường xuyên.
- **Kỹ thuật phần mềm:** khi song song hoá một đoạn mã, ước lượng T₁ và T∞ trước (đường phụ thuộc dài nhất là gì?); chọn kích thước hạt để có độ dư khoảng 10 lần số lõi; ưu tiên cấu trúc không tranh chấp (mỗi tác vụ ghi vùng riêng, gộp bằng rút gọn) thay vì khoá; đo trên nhiều cỡ máy hoặc ngoại suy bằng T₁/P + T∞ trước khi giữ một "tối ưu hoá"; dùng công cụ phát hiện tranh chấp (ví dụ ThreadSanitizer, hay Cilksan cho Cilk — theo hiểu biết của người tổng hợp) vì kiểm thử thông thường hầu như không bắt được lỗi tranh chấp.

# Nhập môn thuật toán — Cormen, Leiserson, Rivest, Stein (ấn bản thứ ba, 2009)

*Introduction to Algorithms*, thường gọi tắt là CLRS. Mỗi chương (và mỗi phụ lục) được tổng hợp thành một file riêng. File nào cũng đi qua đủ từng mục của chương theo đúng thứ tự, chép lại mọi pseudocode, định lý kèm chứng minh, vẽ lại mọi hình bằng sơ đồ chữ hoặc bảng, trình bày từng bước mọi ví dụ chạy tay, và nêu đề kèm lời giải ngắn cho mọi bài tập và bài toán cuối chương. **Mọi ví dụ số của sách đã được người tổng hợp chạy lại.** Sau đó là các khái niệm cần biết, luận điểm cốt lõi, bảng thuật ngữ Anh–Việt và phần đánh giá: chỗ nào sách sai hoặc viết chưa chặt, điều gì đã thay đổi ở ấn bản 4, cách vận dụng khi phỏng vấn, lập trình thi đấu và làm phần mềm.

**Tác giả:** Thomas H. Cormen (Dartmouth), Charles E. Leiserson (MIT), Ronald L. Rivest (MIT), Clifford Stein (Columbia). Ấn bản đầu năm 1990 (ba tác giả đầu); Stein tham gia từ ấn bản 2 (2001). Đây là giáo trình thuật toán được dùng rộng rãi nhất ở bậc đại học và sau đại học.

**Nguồn:** ấn bản thứ ba (MIT Press, 2009), bản PDF tiếng Anh 1313 trang, có lớp chữ. Số trang ghi trong các file là **số trang in** của sách (trang PDF = trang in + 20).

> **Lưu ý về nguồn:**
> - **Lớp chữ PDF hỏng gần hết ký hiệu toán** (Θ thành `‚`, `A[j]` thành `AŒj`, mất ≤ ≥ ≠ √, vỡ chỉ số trên và dưới). Mọi pseudocode, công thức, hình và bảng trong các file được chép lại từ ảnh trang; khối **Lưu ý** đầu mỗi file ghi rõ đã đọc lại những trang nào.
> - **Sách có lỗi, và bản tổng hợp ghi cả chỗ sai lẫn bản đúng** (nhận xét của người tổng hợp, chưa đối chiếu danh sách errata chính thức). Một số ví dụ:
>   - Chương 4: số mảng con cần xét là C(n, 2), không phải C(n − 1, 2); Bài tập 4.3-8 cho truy hồi có nghiệm Θ(n² lg n) chứ không phải Θ(n²).
>   - Chương 11: Hình 11.6 đặt khoá 40 ở ô 7 của bảng phụ; tính theo tham số của hình thì phải là ô 3.
>   - Chương 16: chứng minh Bổ đề 16.12 viết "hạn chót lớn thứ i", đúng là "nhỏ thứ i".
>   - Chương 22: đề Bài tập 22.2-3 và 22.3-4 chỉ nhầm dòng pseudocode có thể bỏ.
>   - Chương 29: lỗi dấu khi tách biến tự do (x̂″ⱼ = −x̄ⱼ); điều kiện dừng của đơn hình là "không còn hệ số dương", không phải "mọi hệ số âm".
>   - Chương 33: chứng minh Định lý 33.1 (Graham scan) có một bước sai, dù định lý vẫn đúng.
>   - Phụ lục C: chứng minh Định lý C.4 viết tổng từ i = 0 thay vì i = 1.
> - **Mục có dấu sao (★)** là phần nâng cao mà sách cho phép bỏ qua ở lần đọc đầu; bản tổng hợp vẫn trình bày đủ và giữ dấu sao trong tiêu đề.
> - **Thay đổi ở ấn bản 4 (2022)** được ghi cuối khối Lưu ý của từng file, theo hiểu biết của người tổng hợp, không tra cứu. Đáng kể nhất: đống Fibonacci (C19), cây van Emde Boas (C20) và hình học tính toán (C33) bị đưa ra khỏi bản in; các chương sau Chương 18 bị đánh số lại.
> - **Lời giải bài tập là của người tổng hợp** (sách không có đáp án). Các bài khó có dấu sao thường chỉ có hướng giải; từng file ghi rõ bài nào chưa chứng minh đầy đủ.
> - **Sách còn bản quyền.** Bản tổng hợp diễn đạt lại bằng lời mới; câu trích nguyên văn chủ yếu nằm ở mục "Câu nói đáng nhớ".

## Chuỗi lập luận của cả cuốn sách

```text
       PHẦN I — NỀN TẢNG (Chương 1–5)
       · C1: thuật toán là một công nghệ; thuật toán tốt quan trọng ngang
         phần cứng nhanh
       · C2: sắp xếp chèn và sắp xếp trộn; bất biến vòng lặp để chứng minh
         đúng; mô hình máy RAM để đếm thời gian; chia để trị
       · C3: ký hiệu tiệm cận Θ, O, Ω, o, ω — so sánh thuật toán bằng bậc
         tăng trưởng, bỏ hằng số và số hạng bậc thấp
       · C4: giải truy hồi của chia để trị: phương pháp thế, cây đệ quy,
         định lý thợ; Strassen nhân ma trận Θ(n^2,81)
       · C5: phân tích xác suất và thuật toán ngẫu nhiên; biến ngẫu nhiên
         chỉ thị và tính tuyến tính của kỳ vọng
                                │
                                ▼
       PHẦN II — SẮP XẾP VÀ THỐNG KÊ THỨ TỰ (Chương 6–9)
       · C6 heapsort và hàng đợi ưu tiên; C7 quicksort (kỳ vọng Θ(n lg n))
       · C8: mọi sắp xếp so sánh cần Ω(n lg n); vượt rào bằng sắp xếp đếm,
         cơ số, theo khối
       · C9: tìm phần tử nhỏ thứ i trong thời gian tuyến tính
                                │
                                ▼
       PHẦN III — CẤU TRÚC DỮ LIỆU (Chương 10–14)
       · tập động: ngăn xếp, hàng đợi, danh sách liên kết (C10); bảng băm
         (C11); cây tìm kiếm nhị phân (C12); cây đỏ-đen cân bằng, mọi thao
         tác O(lg n) (C13); mở rộng cấu trúc bằng thông tin phụ (C14)
                                │
                                ▼
       PHẦN IV — KỸ THUẬT THIẾT KẾ VÀ PHÂN TÍCH NÂNG CAO (Chương 15–17)
       · C15 quy hoạch động: cấu trúc con tối ưu + bài toán con gối nhau
       · C16 tham lam: thêm tính chất lựa chọn tham lam; matroid
       · C17 phân tích khấu hao: tổng chi phí của dãy thao tác
                                │
                                ▼
       PHẦN V — CẤU TRÚC DỮ LIỆU NÂNG CAO (Chương 18–21)
       · cây B cho dữ liệu trên đĩa (C18); đống Fibonacci với DECREASE-KEY
         khấu hao O(1) (C19); cây van Emde Boas O(lg lg u) cho khoá nguyên
         (C20); tập rời nhau O(m α(n)) (C21)
                                │
                                ▼
       PHẦN VI — THUẬT TOÁN ĐỒ THỊ (Chương 22–26)
       · BFS, DFS, sắp xếp topo, thành phần liên thông mạnh (C22)
       · cây khung nhỏ nhất: Kruskal, Prim (C23)
       · đường đi ngắn nhất một nguồn: Bellman-Ford, DAG, Dijkstra, ràng
         buộc hiệu (C24); mọi cặp đỉnh: Floyd-Warshall, Johnson (C25)
       · luồng cực đại: Ford-Fulkerson, Edmonds-Karp, ghép cặp hai phía,
         đẩy–nâng nhãn (C26)
                                │
                                ▼
       PHẦN VII — CHỦ ĐỀ CHỌN LỌC (Chương 27–35)
       · song song (C27), ma trận (C28), quy hoạch tuyến tính (C29), FFT
         (C30), số học và RSA (C31), so khớp chuỗi (C32), hình học (C33)
       · C34 NP-đầy đủ: lớp P, NP, phép quy dẫn; khi bài toán là NP-đầy đủ
       · C35 thuật toán xấp xỉ: lời giải có bảo đảm hệ số so với tối ưu
                                │
                                ▼
       PHẦN VIII — PHỤ LỤC: NỀN TẢNG TOÁN HỌC (A–D)
       · tổng (A), tập hợp, quan hệ, đồ thị, cây (B), đếm và xác suất (C),
         ma trận (D)
```

## Mục lục

- [Lời nói đầu](00-loi-noi-dau.md) (Preface): sách dành cho ai, cách dùng cho các loại khoá học, thay đổi so với ấn bản 2

### Phần I — Nền tảng (Foundations)
- [Chương 1 — Vai trò của thuật toán trong tính toán](C01-vai-tro-cua-thuat-toan.md) (The Role of Algorithms in Computing), kèm lời giới thiệu Phần I: thuật toán là gì, bài toán khó, thuật toán như một công nghệ
- [Chương 2 — Bắt đầu](C02-bat-dau.md) (Getting Started): sắp xếp chèn, bất biến vòng lặp, mô hình RAM, sắp xếp trộn
- [Chương 3 — Tăng trưởng của hàm](C03-tang-truong-cua-ham.md) (Growth of Functions): ký hiệu tiệm cận, các hàm chuẩn
- [Chương 4 — Chia để trị](C04-chia-de-tri.md) (Divide-and-Conquer): mảng con lớn nhất, Strassen, phương pháp thế, cây đệ quy, định lý thợ và chứng minh
- [Chương 5 — Phân tích xác suất và thuật toán ngẫu nhiên](C05-phan-tich-xac-suat-va-thuat-toan-ngau-nhien.md) (Probabilistic Analysis and Randomized Algorithms): bài toán tuyển dụng, biến ngẫu nhiên chỉ thị, hoán vị ngẫu nhiên, nghịch lý ngày sinh, bài toán thư ký

### Phần II — Sắp xếp và thống kê thứ tự (Sorting and Order Statistics)
- [Chương 6 — Sắp xếp vun đống](C06-heapsort.md) (Heapsort), kèm lời giới thiệu Phần II: đống max, MAX-HEAPIFY, BUILD-MAX-HEAP Θ(n), heapsort, hàng đợi ưu tiên
- [Chương 7 — Sắp xếp nhanh](C07-quicksort.md) (Quicksort): phân hoạch Lomuto, quicksort ngẫu nhiên, phân tích kỳ vọng
- [Chương 8 — Sắp xếp trong thời gian tuyến tính](C08-sap-xep-thoi-gian-tuyen-tinh.md) (Sorting in Linear Time): cận dưới cây quyết định, sắp xếp đếm, cơ số, theo khối
- [Chương 9 — Trung vị và thống kê thứ tự](C09-trung-vi-va-thong-ke-thu-tu.md) (Medians and Order Statistics): RANDOMIZED-SELECT, SELECT tuyến tính trong trường hợp xấu nhất

### Phần III — Cấu trúc dữ liệu (Data Structures)
- [Chương 10 — Các cấu trúc dữ liệu cơ bản](C10-cau-truc-du-lieu-co-ban.md) (Elementary Data Structures), kèm lời giới thiệu Phần III: ngăn xếp, hàng đợi, danh sách liên kết, cài đặt con trỏ, cây có gốc
- [Chương 11 — Bảng băm](C11-bang-bam.md) (Hash Tables): địa chỉ trực tiếp, nối chuỗi, hàm băm, băm phổ quát, địa chỉ mở, ★băm hoàn hảo
- [Chương 12 — Cây tìm kiếm nhị phân](C12-cay-tim-kiem-nhi-phan.md) (Binary Search Trees): truy vấn, chèn, xoá, ★cây dựng ngẫu nhiên
- [Chương 13 — Cây đỏ-đen](C13-cay-do-den.md) (Red-Black Trees): năm tính chất, phép xoay, chèn, xoá
- [Chương 14 — Mở rộng cấu trúc dữ liệu](C14-mo-rong-cau-truc-du-lieu.md) (Augmenting Data Structures): thống kê thứ tự động, cây khoảng

### Phần IV — Kỹ thuật thiết kế và phân tích nâng cao (Advanced Design and Analysis Techniques)
- [Chương 15 — Quy hoạch động](C15-quy-hoach-dong.md) (Dynamic Programming), kèm lời giới thiệu Phần IV: cắt thanh, nhân chuỗi ma trận, dãy con chung dài nhất, cây tìm kiếm nhị phân tối ưu
- [Chương 16 — Thuật toán tham lam](C16-thuat-toan-tham-lam.md) (Greedy Algorithms): chọn hoạt động, mã Huffman, ★matroid, ★lập lịch công việc
- [Chương 17 — Phân tích khấu hao](C17-phan-tich-khau-hao.md) (Amortized Analysis): phương pháp gộp, kế toán, thế năng; bảng động

### Phần V — Cấu trúc dữ liệu nâng cao (Advanced Data Structures)
- [Chương 18 — Cây B](C18-cay-b.md) (B-Trees), kèm lời giới thiệu Phần V: định nghĩa, tìm, chèn, xoá trên cây B
- [Chương 19 — Đống Fibonacci](C19-dong-fibonacci.md) (Fibonacci Heaps): thao tác đống gộp được, DECREASE-KEY, chặn bậc lớn nhất
- [Chương 20 — Cây van Emde Boas](C20-cay-van-emde-boas.md) (van Emde Boas Trees): cấu trúc proto-vEB, cây vEB, thao tác O(lg lg u)
- [Chương 21 — Cấu trúc dữ liệu cho tập rời nhau](C21-cau-truc-du-lieu-cho-tap-roi-nhau.md) (Data Structures for Disjoint Sets): danh sách liên kết, rừng tập rời nhau, ★phân tích với hàm Ackermann ngược

### Phần VI — Thuật toán đồ thị (Graph Algorithms)
- [Chương 22 — Các thuật toán đồ thị cơ bản](C22-thuat-toan-do-thi-co-ban.md) (Elementary Graph Algorithms), kèm lời giới thiệu Phần VI: biểu diễn đồ thị, BFS, DFS, sắp xếp topo, thành phần liên thông mạnh
- [Chương 23 — Cây khung nhỏ nhất](C23-cay-khung-nho-nhat.md) (Minimum Spanning Trees): cạnh an toàn, Kruskal, Prim
- [Chương 24 — Đường đi ngắn nhất từ một nguồn](C24-duong-di-ngan-nhat-tu-mot-nguon.md) (Single-Source Shortest Paths): Bellman-Ford, đồ thị không chu trình, Dijkstra, ràng buộc hiệu
- [Chương 25 — Đường đi ngắn nhất giữa mọi cặp đỉnh](C25-duong-di-ngan-nhat-moi-cap-dinh.md) (All-Pairs Shortest Paths): nhân ma trận, Floyd-Warshall, bao đóng bắc cầu, Johnson
- [Chương 26 — Luồng cực đại](C26-luong-cuc-dai.md) (Maximum Flow): mạng luồng, Ford-Fulkerson, Edmonds-Karp, ghép cặp hai phía, ★đẩy–nâng nhãn, ★relabel-to-front

### Phần VII — Chủ đề chọn lọc (Selected Topics)
- [Chương 27 — Thuật toán đa luồng](C27-thuat-toan-da-luong.md) (Multithreaded Algorithms), kèm lời giới thiệu Phần VII: work, span, độ song song, nhân ma trận và sắp xếp trộn song song
- [Chương 28 — Các phép toán ma trận](C28-phep-toan-ma-tran.md) (Matrix Operations): phân rã LUP, nghịch đảo ma trận, bình phương tối thiểu
- [Chương 29 — Quy hoạch tuyến tính](C29-quy-hoach-tuyen-tinh.md) (Linear Programming): dạng chuẩn và dạng bù, thuật toán đơn hình, đối ngẫu, nghiệm khả thi cơ sở ban đầu
- [Chương 30 — Đa thức và biến đổi Fourier nhanh](C30-da-thuc-va-fft.md) (Polynomials and the FFT): biểu diễn đa thức, DFT, FFT đệ quy và lặp
- [Chương 31 — Thuật toán số học](C31-thuat-toan-so-hoc.md) (Number-Theoretic Algorithms): Euclid, số học modulo, định lý số dư Trung Hoa, RSA, ★Miller-Rabin, ★Pollard rho
- [Chương 32 — So khớp chuỗi](C32-so-khop-chuoi.md) (String Matching): thuật toán ngây thơ, Rabin-Karp, ôtômat hữu hạn, ★Knuth-Morris-Pratt
- [Chương 33 — Hình học tính toán](C33-hinh-hoc-tinh-toan.md) (Computational Geometry): tích có hướng, giao đoạn thẳng bằng đường quét, bao lồi (Graham, Jarvis), cặp điểm gần nhất
- [Chương 34 — NP-đầy đủ](C34-np-day-du.md) (NP-Completeness): thời gian đa thức, kiểm chứng, quy dẫn, SAT, 3-CNF, clique, phủ đỉnh, chu trình Hamilton, người bán hàng, tổng tập con
- [Chương 35 — Thuật toán xấp xỉ](C35-thuat-toan-xap-xi.md) (Approximation Algorithms): phủ đỉnh, người bán hàng, phủ tập, ngẫu nhiên hoá và quy hoạch tuyến tính, tổng tập con

### Phần VIII — Phụ lục: Nền tảng toán học (Appendix: Mathematical Background)
- [Phụ lục A — Tổng](PA-tong.md) (Summations), kèm lời giới thiệu Phần VIII: công thức tổng, chặn tổng bằng quy nạp, so sánh với tích phân
- [Phụ lục B — Tập hợp và các khái niệm liên quan](PB-tap-hop-va-cau-truc-roi-rac.md) (Sets, Etc.): tập hợp, quan hệ, hàm, đồ thị, cây
- [Phụ lục C — Đếm và xác suất](PC-dem-va-xac-suat.md) (Counting and Probability): tổ hợp, xác suất, biến ngẫu nhiên, phân phối hình học và nhị thức, ★đuôi phân phối nhị thức
- [Phụ lục D — Ma trận](PD-ma-tran.md) (Matrices): phép toán ma trận, hạng, định thức, ma trận xác định dương

## Gợi ý đọc

- **Đọc trước tiên:** Chương 2 và 3 (cách phân tích và ký hiệu tiệm cận), rồi Chương 4 (truy hồi). Hầu hết các chương sau dùng lại ba chương này.
- **Thiếu nền toán rời rạc và xác suất:** đọc Phụ lục A và C trước Chương 4 và 5; Phụ lục B trước Phần VI.
- **Chuẩn bị phỏng vấn kỹ thuật:** Chương 6–13, 15, 16, 22–24; mỗi file có mục "Vận dụng" nêu các câu hỏi thường gặp.
- **Lập trình thi đấu:** thêm Chương 21 (tập rời nhau), 25, 26 (luồng), 30 (FFT), 31 (số học), 32 (KMP), 33 (hình học).
- **Muốn hiểu giới hạn của tính toán:** Chương 34 rồi Chương 35; Chương 29 là cầu nối giữa tối ưu hoá và thuật toán xấp xỉ.
- **Phân tích nâng cao:** Chương 17 (khấu hao) là nền cho Chương 19 và 21.

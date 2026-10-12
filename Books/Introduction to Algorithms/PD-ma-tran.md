# Phụ lục D — Ma trận (Matrices)

**Nguồn:** Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein, *Introduction to Algorithms*, ấn bản thứ ba (MIT Press, 2009), Phần VIII "Appendix: Mathematical Background", Phụ lục D "Matrices", trang 1217–1230 (phần mở đầu, Mục D.1, Mục D.2, Bài toán D-1 và D-2, Ghi chú phụ lục; trang 1230 để trống).
**Tác giả:** Cormen, Leiserson, Rivest, Stein — bốn nhà khoa học máy tính (ba người đầu ở MIT, Stein ở Đại học Columbia); cuốn sách thường được gọi tắt là "CLRS" theo chữ cái đầu tên họ.
**Vị trí trong lập luận của cả cuốn sách:** Phụ lục D là phụ lục cuối cùng của Phần VIII, bộ tài liệu tra cứu toán học của cuốn sách. Lời giới thiệu Phần VIII (tóm tắt trong [PA-tong.md](PA-tong.md)) nói về phụ lục này một câu: nó định nghĩa ma trận, các phép toán trên ma trận và vài tính chất cơ bản; người đã học đại số tuyến tính hầu như đã biết hết, nhưng nên có một chỗ để tra ký hiệu và định nghĩa của sách. Ba phụ lục còn lại là Phụ lục A ([PA-tong.md](PA-tong.md): tổng), Phụ lục B ([PB-tap-hop-va-cau-truc-roi-rac.md](PB-tap-hop-va-cau-truc-roi-rac.md): tập hợp, quan hệ, hàm, đồ thị, cây) và Phụ lục C ([PC-dem-va-xac-suat.md](PC-dem-va-xac-suat.md): đếm và xác suất). Các chương dùng trực tiếp nội dung phụ lục này: Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)) cài đặt công thức nhân ma trận (D.2) thành SQUARE-MATRIX-MULTIPLY chạy Θ(n³) rồi hạ xuống Θ(n^lg 7) bằng thuật toán Strassen; Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)) dùng một phép "nhân ma trận" với min thay cho cộng và cộng thay cho nhân để tính đường đi ngắn nhất mọi cặp đỉnh; Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)) song song hoá phép nhân ma trận; Chương 28 ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)) là người dùng chính: phân rã LU và LUP dùng ma trận tam giác dưới đơn vị, tam giác trên, ma trận hoán vị; nghịch đảo ma trận dùng tính duy nhất của nghịch đảo và (BA)⁻¹ = A⁻¹B⁻¹; Mục 28.3 dùng ma trận đối xứng xác định dương và Định lý D.6 (AᵀA xác định dương khi A có hạng cột đầy đủ) cho bài toán bình phương tối thiểu; Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)) viết quy hoạch tuyến tính dưới dạng ma trận Ax ≤ b; Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)) dùng định thức Vandermonde (Bài toán D-1) và Định lý D.5 để chứng minh nội suy đa thức là duy nhất (Định lý 30.1).
**Ý chính:** Phụ lục muốn người đọc nắm **bộ từ vựng và ký hiệu ma trận mà sách dùng ở các chương sau — ma trận, vectơ cột, chuyển vị, các loại ma trận vuông đặc biệt (đường chéo, đơn vị, ba đường chéo, tam giác trên/dưới, hoán vị, đối xứng), các phép cộng, nhân vô hướng, nhân ma trận; và các tính chất cơ bản: nghịch đảo, độc lập tuyến tính, hạng, định thức, ma trận xác định dương — cùng một chuỗi định lý nối các khái niệm này với nhau: hạng đầy đủ ⇔ không suy biến ⇔ không có vectơ không ⇔ định thức khác 0.** Phần mở đầu chỉ nói ma trận có mặt trong rất nhiều ứng dụng, không riêng tính toán khoa học. Mục D.1 định nghĩa ma trận m × n A = (aᵢⱼ), tập ℝ^(m×n) và S^(m×n), chuyển vị Aᵀ, vectơ (dạng chuẩn là vectơ cột, chuyển vị thành vectơ hàng), vectơ đơn vị eᵢ, ma trận không; bảy loại ma trận vuông đặc biệt; phép cộng theo từng phần tử, nhân vô hướng, ma trận đối, phép trừ; phép nhân cᵢⱼ = Σₖ aᵢₖbₖⱼ (D.2) với điều kiện tương thích, tốn n³ phép nhân và n²(n − 1) phép cộng với ma trận vuông; các luật: đơn vị, nhân với ma trận không, kết hợp, phân phối, và **không giao hoán** khi n > 1; tích trong xᵀy, tích ngoài xyᵀ, chuẩn Euclid ‖x‖ = (xᵀx)^(1/2). Mục D.2 định nghĩa nghịch đảo A⁻¹ (ma trận suy biến và không suy biến), (BA)⁻¹ = A⁻¹B⁻¹, (A⁻¹)ᵀ = (Aᵀ)⁻¹; phụ thuộc và độc lập tuyến tính; hạng cột, hạng hàng, hạng (hai cái luôn bằng nhau), định nghĩa tương đương "hạng là r nhỏ nhất để A = BC với B cỡ m × r, C cỡ r × n"; Định lý D.1 (vuông có hạng đầy đủ ⇔ không suy biến), Định lý D.2 (hạng cột đầy đủ ⇔ không có vectơ không) và Hệ quả D.3; định thức định nghĩa đệ quy bằng khai triển theo hàng đầu với các ma trận con (minor) và phần bù đại số (cofactor), Định lý D.4 (năm tính chất của định thức và det(AB) = det(A)det(B)), Định lý D.5 (suy biến ⇔ det = 0); ma trận xác định dương xᵀAx > 0 và Định lý D.6 kèm chứng minh. Bài toán D-1 chứng minh định thức Vandermonde bằng Π (xₖ − xⱼ); Bài toán D-2 nghiên cứu các hoán vị của {0, 1, …, 2ⁿ − 1} sinh bởi phép nhân ma trận 0-1 với vectơ bit trên trường GF(2), và chỉ ra rằng các "hoán vị tuyến tính" x ↦ Ax + c chỉ là một phần rất nhỏ của mọi hoán vị.

> **Lưu ý:**
> - **Không có mục có dấu sao (★) trong phụ lục này, và không bài tập hay bài toán nào có dấu sao.** Phụ lục gồm hai mục (D.1, D.2), 4 bài tập ở Mục D.1, 8 bài tập ở Mục D.2, 2 bài toán (D-1, D-2) và một ghi chú ngắn. Không có pseudocode và không có hình đánh số.
> - **Số trang:** trang 1216 là Ghi chú của Phụ lục C. Phụ lục D bắt đầu ở trang 1217, Bài toán D-2 kết thúc và Ghi chú phụ lục nằm ở trang 1229, trang 1230 trống, trang 1231 đã là Tài liệu tham khảo (Bibliography). Đã kiểm tra trên ảnh trang.
> - **Lớp chữ PDF hỏng gần như mọi ký hiệu toán của phụ lục:** dấu bằng thành `D` (`AD .aij/` là A = (aᵢⱼ)), dấu trừ thành `/NUL` (`A/NUL1` là A⁻¹, `.n/NUL1/` là (n − 1)), dấu cộng thành `C`, dấu nhân × mất hẳn (`2 3 matrix` là ma trận 2 × 3, `Rm/STXn` là ℝ^(m×n)), ≠ thành `¤`, Θ thành `‚`, λ mất hẳn (`If  is a number` là "Nếu λ là một số"), ≥ mất trong chứng minh Định lý D.6 (`kAxk2 0` là ‖Ax‖² ≥ 0), ≤ mất trong Exercise D.2-8 và trong chỉ số của tích Vandermonde (`0j< kn/NUL1` là 0 ≤ j < k ≤ n − 1), π mất trong Bài toán D-2 (`A.3/` là π_A(3)), ⊆ mất (`S  Sn` là S ⊆ Sₙ); mọi ma trận bị tách thành các dãy số dính liền (`123 456` là ma trận (1 2 3; 4 5 6); `41 19` là hàng (4 11 9)); dấu ngoặc lớn thành ký tự lạ `˙`, `/BEL`, `ˇ`, `‚`; chỉ số dưới A[ij] của ma trận con thành `AŒij`. Toàn bộ định nghĩa, công thức (D.1), (D.2), các ma trận ví dụ, Định lý D.1–D.6, bài tập và hai bài toán trong bản tổng hợp này được chép lại từ ảnh trang 1217–1229.
> - **Chỗ diễn đạt chưa chặt (nhận xét của người tổng hợp):**
>   - Định nghĩa ma trận hoán vị (trang 1220) viết "có đúng một số 1 ở mỗi hàng **hoặc** cột" (exactly one 1 in each row or column). Phải là "mỗi hàng **và** mỗi cột": ma trận (1 0; 1 0) có đúng một số 1 ở mỗi hàng nhưng không phải ma trận hoán vị (nó suy biến, nhân với vectơ (a, b)ᵀ cho (a, a)ᵀ chứ không hoán vị gì cả).
>   - Trang 1221 nói SQUARE-MATRIX-MULTIPLY "thực hiện n³ phép nhân và n²(n − 1) phép cộng". Con số n²(n − 1) là số phép cộng **cần thiết** (mỗi cᵢⱼ là tổng n tích, cần n − 1 phép cộng). Còn pseudocode ở Mục 4.2 gán cᵢⱼ = 0 rồi thực hiện cᵢⱼ = cᵢⱼ + aᵢₖ · bₖⱼ đúng n lần, tức n³ phép cộng nếu đếm từng dòng. Không ảnh hưởng tới kết luận Θ(n³).
>   - Hạng cột và hạng hàng được định nghĩa cho "ma trận khác không" (nonzero matrix), sau đó sách nói thêm hạng của ma trận không là 0. Hai câu không mâu thuẫn, nhưng nếu coi tập rỗng là tập độc lập tuyến tính thì định nghĩa chung "kích thước tập cột độc lập lớn nhất" áp dụng được luôn cho ma trận không, khỏi cần trường hợp riêng.
>   - Định nghĩa ma trận xác định dương (trang 1225) chỉ đòi xᵀAx > 0, **không** đòi A đối xứng. Theo định nghĩa này, A = (1 1; −1 1) là xác định dương (xᵀAx = x₁² + x₂²) dù không đối xứng. Chương 28 luôn nói "ma trận đối xứng xác định dương" (symmetric positive-definite) nên không bị ảnh hưởng; nhiều sách đại số tuyến tính chỉ dùng thuật ngữ "xác định dương" cho ma trận đối xứng — theo hiểu biết của người tổng hợp.
>   - Exercise D.2-6, câu thứ hai ("nếu B là ma trận m × n bất kỳ thì BABᵀ đối xứng") chỉ đúng khi A đối xứng, giả thiết lấy từ câu thứ nhất; nếu A không đối xứng thì sai, ví dụ B = I₂, A = (0 1; 0 0).
>   - Bài toán D-2(a) yêu cầu kết luận "A định nghĩa một hoán vị **chỉ khi** A có hạng đầy đủ". Thực ra là **khi và chỉ khi** (hạng đầy đủ thì |R(A)| = 2ⁿ nên ánh xạ là toàn ánh trên tập hữu hạn, do đó song ánh). Không sai, chỉ yếu hơn mức có thể.
> - **Mọi ví dụ số trong sách đã được tự kiểm tra lại và đúng:** chuyển vị của (1 2 3; 4 5 6); hai tích AB = (1 0; 0 0) và BA = (0 0; 0 1) trong ví dụ không giao hoán; nghịch đảo (1 1; 1 0)⁻¹ = (0 1; 1 −1); quan hệ phụ thuộc 2x₁ + 3x₂ − 2x₃ = 0 với x₁ = (1 2 3), x₂ = (2 6 4), x₃ = (4 11 9); hoán vị π_A(0) = 0, π_A(1) = 3, π_A(2) = 2, π_A(3) = 1 và π_{A,c}(0) = 2, π_{A,c}(1) = 1, π_{A,c}(2) = 0, π_{A,c}(3) = 3 trong Bài toán D-2; ví dụ khối B(S, m) với n = 3, m = 1, S = {1, 4, 5}. Không phát hiện lỗi số học.
> - **Thay đổi ở ấn bản 4 (2022) — theo hiểu biết của người tổng hợp, không tra cứu:** Phần VIII vẫn kết thúc bằng Phụ lục D "Matrices" với hai mục về định nghĩa/phép toán và tính chất cơ bản. Người tổng hợp không nhớ chắc các thay đổi về bài tập, bài toán hay lời văn nên không liệt kê.

## Sơ đồ

### Phần mở đầu Phụ lục D (trước Mục D.1, trang 1217) — phụ lục này dùng để làm gì

```text
       Ma trận xuất hiện trong rất nhiều ứng dụng
       (tính toán khoa học là một ví dụ, nhưng không phải duy nhất)
                                │
                                ▼
       Người đã học ma trận sẽ thấy phần lớn nội dung quen thuộc,
       có thể có vài điểm mới
                                │
                                ▼
       Trình tự phụ lục:
       D.1 định nghĩa cơ bản về ma trận và các phép toán
       D.2 một số tính chất cơ bản của ma trận
       (sau đó: 2 bài toán và ghi chú)
```

### Mục D.1 — Ma trận và các phép toán trên ma trận (Matrices and matrix operations, trang 1217–1222)

```text
       MA TRẬN VÀ VECTƠ
       · ma trận = bảng số hình chữ nhật; A = (aᵢⱼ) cỡ m × n,
         aᵢⱼ ở hàng i, cột j; chữ hoa cho ma trận, chữ thường có chỉ số
         cho phần tử
         ví dụ (D.1): A = (1 2 3; 4 5 6) là ma trận 2 × 3
       · ℝ^(m×n): mọi ma trận m × n phần tử thực; S^(m×n): phần tử thuộc S
       · CHUYỂN VỊ Aᵀ: đổi hàng thành cột; Aᵀ của (D.1) = (1 4; 2 5; 3 6)
       · VECTƠ = mảng một chiều; n-vectơ; dạng chuẩn là VECTƠ CỘT (n × 1),
         VECTƠ HÀNG là chuyển vị: x = (2, 3, 5)ᵀ, xᵀ = (2 3 5)
       · vectơ đơn vị eᵢ (1 ở vị trí i, còn lại 0); ma trận không 0
                                │
                                ▼
       MA TRẬN VUÔNG n × n — bảy loại đặc biệt
       1 đường chéo: aᵢⱼ = 0 khi i ≠ j; viết diag(a₁₁, …, aₙₙ)
       2 đơn vị Iₙ = diag(1, …, 1); cột thứ i của Iₙ là eᵢ
       3 ba đường chéo: tᵢⱼ = 0 khi |i − j| > 1
       4 tam giác trên: uᵢⱼ = 0 khi i > j  (đơn vị nếu đường chéo toàn 1)
       5 tam giác dưới: lᵢⱼ = 0 khi i < j  (đơn vị nếu đường chéo toàn 1)
       6 hoán vị: đúng một số 1 trên mỗi hàng và mỗi cột; Px hoán vị x
       7 đối xứng: A = Aᵀ, ví dụ (1 2 3; 2 6 4; 3 4 5)
                                │
                                ▼
       CÁC PHÉP TOÁN CƠ BẢN (phần tử lấy từ một hệ số: thực, phức,
       số nguyên modulo một số nguyên tố…)
       · cộng: cᵢⱼ = aᵢⱼ + bᵢⱼ (từng phần tử); A + 0 = A = 0 + A
       · nhân vô hướng λA = (λaᵢⱼ); ma trận đối −A = (−1)·A;
         A + (−A) = 0; trừ: A − B = A + (−B)
       · nhân: A (m × n) và B (n × p) TƯƠNG THÍCH (số cột A = số hàng B)
         C = AB cỡ m × p,  cᵢⱼ = Σₖ₌₁ⁿ aᵢₖ bₖⱼ                       (D.2)
         SQUARE-MATRIX-MULTIPLY (Mục 4.2): n³ phép nhân, n²(n − 1) phép
         cộng ⇒ Θ(n³)
                                │
                                ▼
       LUẬT ĐẠI SỐ (có nhiều, nhưng không phải mọi luật của số)
       · IₘA = AIₙ = A;  A0 = 0
       · kết hợp A(BC) = (AB)C; phân phối A(B + C) = AB + AC,
         (B + C)D = BD + CD
       · KHÔNG GIAO HOÁN khi n > 1:
         A = (0 1; 0 0), B = (0 0; 1 0): AB = (1 0; 0 0) ≠ BA = (0 0; 0 1)
                                │
                                ▼
       TÍCH VỚI VECTƠ (coi vectơ là ma trận n × 1 hoặc 1 × n)
       · A (m × n) nhân n-vectơ x cho m-vectơ Ax
       · tích trong xᵀy = Σ xᵢyᵢ (một số, đúng ra là ma trận 1 × 1)
       · tích ngoài xyᵀ = ma trận Z cỡ n × n, zᵢⱼ = xᵢyⱼ
       · chuẩn Euclid ‖x‖ = (x₁² + … + xₙ²)^(1/2) = (xᵀx)^(1/2):
         độ dài của x trong không gian Euclid n chiều
                                │
                                ▼
       Bài tập D.1-1 … D.1-4: tổng/hiệu ma trận đối xứng, (AB)ᵀ = BᵀAᵀ,
       tích ma trận tam giác dưới, tính chất ma trận hoán vị
```

### Mục D.2 — Các tính chất cơ bản của ma trận (Basic matrix properties, trang 1222–1226)

```text
       NGHỊCH ĐẢO
       · A⁻¹ (nếu có): AA⁻¹ = Iₙ = A⁻¹A
         ví dụ (1 1; 1 0)⁻¹ = (0 1; 1 −1)
       · không có nghịch đảo: KHÔNG KHẢ NGHỊCH = SUY BIẾN, ví dụ (1 0; 1 0)
         có nghịch đảo: KHẢ NGHỊCH = KHÔNG SUY BIẾN; nghịch đảo là duy nhất
       · (BA)⁻¹ = A⁻¹B⁻¹;  (A⁻¹)ᵀ = (Aᵀ)⁻¹
                                │
                                ▼
       ĐỘC LẬP TUYẾN TÍNH VÀ HẠNG
       · x₁, …, xₙ PHỤ THUỘC TUYẾN TÍNH nếu có c₁, …, cₙ không đồng thời
         bằng 0 với c₁x₁ + … + cₙxₙ = 0; ví dụ 2(1 2 3) + 3(2 6 4)
         − 2(4 11 9) = 0; không phụ thuộc thì ĐỘC LẬP (cột của Iₙ)
       · HẠNG CỘT / HẠNG HÀNG = số cột / số hàng độc lập nhiều nhất;
         luôn bằng nhau ⇒ gọi chung là HẠNG; 0 ≤ hạng ≤ min(m, n)
       · định nghĩa tương đương: hạng của A ≠ 0 là r nhỏ nhất để
         A = BC với B cỡ m × r, C cỡ r × n
       · HẠNG ĐẦY ĐỦ (vuông, hạng n); HẠNG CỘT ĐẦY ĐỦ (m × n, hạng n)
                                │
                                ▼
       CHUỖI ĐỊNH LÝ
       Định lý D.1: vuông có hạng đầy đủ ⇔ không suy biến
       VECTƠ KHÔNG (null vector) của A: x ≠ 0 với Ax = 0
       Định lý D.2: hạng cột đầy đủ ⇔ không có vectơ không
       Hệ quả D.3: vuông suy biến ⇔ có vectơ không
                                │
                                ▼
       ĐỊNH THỨC (định nghĩa đệ quy)
       · ma trận con A[ij]: bỏ hàng i, cột j (cỡ (n − 1) × (n − 1))
       · det(A) = a₁₁ nếu n = 1;
         det(A) = Σⱼ₌₁ⁿ (−1)^(1+j) a₁ⱼ det(A[1j]) nếu n > 1
       · phần bù đại số của aᵢⱼ: (−1)^(i+j) det(A[ij])
       Định lý D.4: hàng/cột toàn 0 ⇒ det = 0; nhân một hàng (cột) với λ
       ⇒ det nhân λ; cộng một hàng (cột) vào hàng (cột) khác ⇒ det không
       đổi; det(A) = det(Aᵀ); đổi chỗ hai hàng (cột) ⇒ det đổi dấu;
       det(AB) = det(A)·det(B)
       Định lý D.5: A suy biến ⇔ det(A) = 0
                                │
                                ▼
       MA TRẬN XÁC ĐỊNH DƯƠNG
       · xᵀAx > 0 với mọi n-vectơ x ≠ 0; ví dụ Iₙ: xᵀx = Σ xᵢ² > 0
       Định lý D.6: A có hạng cột đầy đủ ⇒ AᵀA xác định dương
       Chứng minh: xᵀ(AᵀA)x = (Ax)ᵀ(Ax) = ‖Ax‖² ≥ 0; bằng 0 ⇒ Ax = 0
       ⇒ x = 0 (Định lý D.2)
       (Mục 28.3 khai thác thêm các tính chất của ma trận xác định dương)
                                │
                                ▼
       Bài tập D.2-1 … D.2-8: nghịch đảo duy nhất, định thức và nghịch
       đảo của ma trận tam giác, nghịch đảo ma trận hoán vị, cập nhật
       nghịch đảo khi cộng hàng, nghịch đảo của ma trận thực, nghịch đảo
       ma trận đối xứng, chứng minh Định lý D.2, hạng của tích
```

### Bài toán cuối phụ lục (Problems D-1 và D-2, trang 1226–1229)

```text
       D-1 Ma trận Vandermonde V(x₀, …, xₙ₋₁): hàng k là
           (1, xₖ, xₖ², …, xₖⁿ⁻¹)
           det V = Π_{0 ≤ j < k ≤ n−1} (xₖ − xⱼ)
           Gợi ý: nhân cột i với −x₀ cộng vào cột i + 1 (i = n − 1, …, 1),
           rồi quy nạp
                                │
                                ▼
       D-2 Hoán vị sinh bởi phép nhân ma trận–vectơ trên GF(2)
           · Sₙ = {0, 1, …, 2ⁿ − 1}; x ↔ vectơ bit (x₀, …, xₙ₋₁)ᵀ,
             x = Σ xᵢ2ⁱ; số học trên GF(2): như số nguyên nhưng chỉ giữ
             bit thấp nhất, 1 + 1 = 0
           · ma trận 0-1 A cho ánh xạ x ↦ Ax; ví dụ A = (1 0; 1 1):
             π_A = (0→0, 1→3, 2→2, 3→1)
           (a) hạng r ⇒ |R(A)| = 2ʳ; A cho hoán vị chỉ khi hạng đầy đủ
           (b) tập nghịch ảnh P(A, y) có 2ⁿ⁻ʳ phần tử
           (c) chia Sₙ thành khối 2ᵐ số liên tiếp; r là hạng của khối con
               dưới-trái (n − m) × m ⇒ một khối được ánh xạ vào đúng 2ʳ
               khối, mỗi khối nhận 2ᵐ⁻ʳ số
           · hoán vị tuyến tính: x ↦ Ax + c (A hạng đầy đủ, c là n-bit);
             ví dụ thêm c = (0, 1)ᵀ: π_{A,c} = (0→2, 1→1, 2→0, 3→3)
           (d) đếm: số hoán vị tuyến tính nhỏ hơn rất nhiều so với (2ⁿ)!
           (e) tìm n và một hoán vị không tuyến tính
```

### Ghi chú phụ lục (Appendix notes, trang 1229)

```text
       Sách giáo khoa đại số tuyến tính cung cấp đủ kiến thức nền về
       ma trận
                                │
                                ▼
       Đặc biệt nên đọc hai cuốn của Gilbert Strang: Introduction to
       Applied Mathematics (1986) và Linear Algebra and Its
       Applications (ấn bản 4, 2006) — tài liệu [323], [324] của sách
```

## Ba câu hỏi chương này trả lời

1. **Sách dùng những khái niệm và ký hiệu ma trận nào, và các loại ma trận đặc biệt khác nhau ra sao?** Ma trận m × n viết A = (aᵢⱼ), aᵢⱼ ở hàng i cột j, ví dụ A = (1 2 3; 4 5 6) cỡ 2 × 3 có a₂₃ = 6; chuyển vị Aᵀ = (1 4; 2 5; 3 6). Vectơ mặc định là vectơ cột (ma trận n × 1), vectơ hàng là chuyển vị của nó. Bảy loại ma trận vuông đặc biệt được phân biệt bằng vị trí các số 0 bắt buộc: đường chéo (aᵢⱼ = 0 khi i ≠ j), đơn vị Iₙ (đường chéo toàn 1), ba đường chéo (tᵢⱼ = 0 khi |i − j| > 1), tam giác trên (0 dưới đường chéo), tam giác dưới (0 trên đường chéo), hoán vị (mỗi hàng và mỗi cột đúng một số 1), đối xứng (A = Aᵀ). Phép nhân C = AB chỉ xác định khi số cột của A bằng số hàng của B, với cᵢⱼ = Σₖ aᵢₖbₖⱼ; cách tính thẳng tốn n³ phép nhân cho ma trận n × n (với n = 2 là 8 phép nhân, 4 phép cộng). Phép nhân kết hợp và phân phối nhưng không giao hoán: với A = (0 1; 0 0), B = (0 0; 1 0) thì AB = (1 0; 0 0) còn BA = (0 0; 0 1).
2. **Khi nào một ma trận vuông có nghịch đảo, và các cách nhận biết liên quan với nhau thế nào?** Bốn điều kiện tương đương cho ma trận vuông A cỡ n × n: A không suy biến (có A⁻¹ với AA⁻¹ = I = A⁻¹A); A có hạng đầy đủ n (Định lý D.1); A không có vectơ không, tức Ax = 0 kéo theo x = 0 (Hệ quả D.3); det(A) ≠ 0 (Định lý D.5). Ví dụ (1 1; 1 0) có định thức 1·0 − 1·1 = −1 ≠ 0, hai cột độc lập, nghịch đảo (0 1; 1 −1); còn (1 0; 1 0) có định thức 0, hạng 1, vectơ không x = (0, 1)ᵀ, không có nghịch đảo. Hạng là số cột (bằng số hàng) độc lập tuyến tính nhiều nhất; ví dụ ba hàng (1 2 3), (2 6 4), (4 11 9) phụ thuộc vì 2x₁ + 3x₂ − 2x₃ = 0, ma trận ghép từ chúng có hạng 2 và định thức 0.
3. **Định thức và ma trận xác định dương được định nghĩa thế nào, và vì sao AᵀA thường xác định dương?** Định thức được định nghĩa đệ quy bằng khai triển theo hàng thứ nhất: det(A) = Σⱼ (−1)^(1+j) a₁ⱼ det(A[1j]), với A[1j] là ma trận bỏ hàng 1, cột j; ví dụ det(1 2 3; 2 6 4; 3 4 5) = 1·14 − 2·(−2) + 3·(−10) = −12. Định lý D.4 cho các quy tắc biến đổi (đổi hai hàng thì đổi dấu, cộng một hàng vào hàng khác thì không đổi, det(AB) = det(A)det(B)). Ma trận A xác định dương nếu xᵀAx > 0 với mọi x ≠ 0. Định lý D.6: nếu A có hạng cột đầy đủ thì AᵀA xác định dương, vì xᵀAᵀAx = ‖Ax‖² ≥ 0, và bằng 0 chỉ khi Ax = 0, tức x = 0. Ví dụ A = (1 0; 0 1; 1 1) cỡ 3 × 2 có hạng 2 nên AᵀA = (2 1; 1 2) xác định dương: xᵀ(AᵀA)x = 2x₁² + 2x₁x₂ + 2x₂² = x₁² + x₂² + (x₁ + x₂)². Đây là lý do ma trận trong bài toán bình phương tối thiểu (Mục 28.3) luôn giải được.

## Khái niệm cần biết

- **Ma trận (matrix) và ký hiệu A = (aᵢⱼ):** bảng số hình chữ nhật gồm m hàng, n cột; aᵢⱼ là phần tử ở hàng i, cột j. Sách dùng chữ hoa cho ma trận và chữ thường cùng tên có chỉ số cho phần tử. Ví dụ A = (1 2 3; 4 5 6) là ma trận 2 × 3 với a₁₂ = 2, a₂₁ = 4. Tập mọi ma trận m × n phần tử thực ký hiệu ℝ^(m×n); phần tử lấy từ tập S thì ký hiệu S^(m×n) (Bài toán D-2 dùng S = {0, 1}). Quan trọng vì đây là đối tượng của cả phụ lục và của Chương 28.
- **Chuyển vị (transpose) Aᵀ:** ma trận có được khi đổi hàng thành cột: phần tử (i, j) của Aᵀ là aⱼᵢ. Ví dụ (1 2 3; 4 5 6)ᵀ = (1 4; 2 5; 3 6). Tính chất then chốt: (AB)ᵀ = BᵀAᵀ (Exercise D.1-2). Quan trọng vì nó định nghĩa ma trận đối xứng, vectơ hàng, tích trong, và xuất hiện trong mọi công thức bình phương tối thiểu.
- **Vectơ (vector), vectơ cột và vectơ hàng (column / row vector):** mảng một chiều; vectơ cỡ n gọi là n-vectơ, phần tử thứ i là xᵢ. Sách quy ước vectơ ở dạng chuẩn là **vectơ cột** (ma trận n × 1); vectơ hàng là chuyển vị. Ví dụ x = (2, 3, 5)ᵀ, xᵀ = (2 3 5). Quan trọng vì nhờ quy ước này mà Ax, xᵀy, xᵀAx đều là tích ma trận thông thường.
- **Vectơ đơn vị (unit vector) eᵢ và ma trận không (zero matrix):** eᵢ có phần tử thứ i bằng 1, mọi phần tử khác bằng 0; cỡ của nó suy từ ngữ cảnh. Ví dụ trong ℝ³, e₂ = (0, 1, 0)ᵀ. Ma trận không có mọi phần tử bằng 0, thường viết 0, cỡ suy từ ngữ cảnh. Quan trọng vì Aeᵢ là cột thứ i của A — ý chính của gợi ý Bài toán D-2(e).
- **Ma trận vuông (square matrix) và các loại đặc biệt:** ma trận n × n. Đường chéo diag(a₁₁, …, aₙₙ); đơn vị Iₙ = diag(1, …, 1); ba đường chéo (khác 0 chỉ ở đường chéo chính và hai đường sát nó); tam giác trên U (0 dưới đường chéo), tam giác dưới L (0 trên đường chéo), "đơn vị" nếu đường chéo toàn 1; hoán vị P; đối xứng A = Aᵀ. Ví dụ (1 0 0; 2 1 0; 5 −3 1) là tam giác dưới đơn vị. Quan trọng vì phân rã LUP (Chương 28) viết PA = LU với đúng ba loại: hoán vị, tam giác dưới đơn vị, tam giác trên; hệ ba đường chéo là đề Problem 28-1.
- **Ma trận hoán vị (permutation matrix):** có đúng một số 1 trên mỗi hàng và mỗi cột, còn lại là 0. Nhân Px sắp xếp lại các phần tử của x. Ví dụ với ma trận P 5 × 5 của sách (hàng 1 có số 1 ở cột 2, hàng 2 ở cột 4, hàng 3 ở cột 1, hàng 4 ở cột 5, hàng 5 ở cột 3) và x = (10, 20, 30, 40, 50)ᵀ thì Px = (20, 40, 10, 50, 30)ᵀ. Nghịch đảo của P là Pᵀ (Exercise D.2-3). Quan trọng vì ghi lại các phép đổi hàng khi chọn trụ trong phân rã LUP mà không cần lưu cả ma trận.
- **Phép cộng, nhân vô hướng, ma trận đối, phép trừ (addition, scalar multiple, negative, subtraction):** cộng từng phần tử cᵢⱼ = aᵢⱼ + bᵢⱼ (hai ma trận cùng cỡ); λA = (λaᵢⱼ); −A = (−1)·A; A − B = A + (−B). Ví dụ (1 2; 3 4) + (5 6; 7 8) = (6 8; 10 12); 3·(1 2; 3 4) = (3 6; 9 12). Ma trận không là phần tử đơn vị của phép cộng.
- **Phép nhân ma trận (matrix multiplication) và tính tương thích (compatible):** A cỡ m × n và B cỡ n × p tương thích (số cột A bằng số hàng B); C = AB cỡ m × p với cᵢⱼ = Σₖ₌₁ⁿ aᵢₖbₖⱼ (D.2) — tích trong của hàng i của A và cột j của B. Ví dụ (1 2; 3 4)(5 6; 7 8) = (1·5 + 2·7, 1·6 + 2·8; 3·5 + 4·7, 3·6 + 4·8) = (19 22; 43 50). Quan trọng vì đây là phép toán mà Chương 4 (Strassen), Chương 25 (đường đi ngắn nhất), Chương 27 (đa luồng), Chương 28 (nghịch đảo quy về nhân) đều tìm cách làm nhanh hơn Θ(n³).
- **Không giao hoán (not commutative):** với n > 1 nói chung AB ≠ BA. Ví dụ của sách: A = (0 1; 0 0), B = (0 0; 1 0) cho AB = (1 0; 0 0), BA = (0 0; 0 1). Quan trọng vì mọi biến đổi đại số trên ma trận phải giữ thứ tự nhân: (BA)⁻¹ = A⁻¹B⁻¹ (đảo thứ tự), (AB)ᵀ = BᵀAᵀ.
- **Tích trong, tích ngoài, chuẩn Euclid (inner product, outer product, euclidean norm):** với hai n-vectơ, tích trong xᵀy = Σ xᵢyᵢ là một số; tích ngoài xyᵀ là ma trận n × n với phần tử xᵢyⱼ; chuẩn ‖x‖ = (xᵀx)^(1/2) là độ dài của x. Ví dụ x = (2, 3, 5)ᵀ: xᵀx = 4 + 9 + 25 = 38, ‖x‖ = √38 ≈ 6,164; với y = (1, 0, 2)ᵀ thì xᵀy = 2 + 0 + 10 = 12 và xyᵀ = (2 0 4; 3 0 6; 5 0 10). Quan trọng vì ‖Ax‖² = xᵀAᵀAx là mấu chốt của Định lý D.6; tích ngoài xuất hiện trong phân rã LU (phần bù Schur A′ − vwᵀ/a₁₁ ở Chương 28).
- **Nghịch đảo (inverse), ma trận suy biến / không suy biến (singular / nonsingular):** A⁻¹ là ma trận n × n với AA⁻¹ = Iₙ = A⁻¹A, nếu có. Có nghịch đảo thì gọi là khả nghịch (invertible) hay không suy biến; không có thì gọi là không khả nghịch (noninvertible) hay suy biến. Ví dụ (1 1; 1 0)⁻¹ = (0 1; 1 −1); (1 0; 1 0) suy biến dù khác không. Nghịch đảo nếu có là duy nhất (Exercise D.2-1). Quan trọng vì "giải Ax = b" có nghiệm duy nhất x = A⁻¹b đúng khi A không suy biến (Chương 28).
- **Phụ thuộc / độc lập tuyến tính (linearly dependent / independent):** x₁, …, xₙ phụ thuộc tuyến tính nếu có hệ số c₁, …, cₙ không đồng thời bằng 0 sao cho c₁x₁ + … + cₙxₙ = 0; không phụ thuộc thì độc lập. Ví dụ của sách: (1 2 3), (2 6 4), (4 11 9) phụ thuộc vì 2·(1 2 3) + 3·(2 6 4) = (8 22 18) = 2·(4 11 9). Các cột của Iₙ độc lập. Quan trọng vì hạng và mọi định lý D.1–D.3 dựa trên khái niệm này.
- **Hạng (rank), hạng cột, hạng hàng, hạng đầy đủ, hạng cột đầy đủ (column rank, row rank, full rank, full column rank):** hạng cột là số cột độc lập tuyến tính nhiều nhất; hạng hàng tương tự với hàng; hai số này luôn bằng nhau nên gọi chung là hạng, nằm trong khoảng 0..min(m, n). Định nghĩa tương đương: hạng của A ≠ 0 là số r nhỏ nhất để A = BC với B cỡ m × r và C cỡ r × n. Ví dụ (1 2 3; 2 4 6) có hạng 1 vì bằng (1, 2)ᵀ nhân (1 2 3). Ma trận vuông có hạng đầy đủ nếu hạng là n; ma trận m × n có hạng cột đầy đủ nếu hạng là n (mọi cột độc lập). Quan trọng vì "hạng cột đầy đủ" là giả thiết của Định lý D.6 và của bài toán bình phương tối thiểu.
- **Vectơ không (null vector):** vectơ x ≠ 0 thoả Ax = 0. Ví dụ x = (0, 1)ᵀ là vectơ không của (1 0; 1 0); x = (2, 3, −2)ᵀ là vectơ không của ma trận có ba **cột** (1, 2, 3)ᵀ, (2, 6, 4)ᵀ, (4, 11, 9)ᵀ. Quan trọng vì có vectơ không tương đương với suy biến (Hệ quả D.3).
- **Ma trận con (minor), định thức (determinant), phần bù đại số (cofactor):** ma trận con A[ij] của A (n > 1) là ma trận (n − 1) × (n − 1) có được khi bỏ hàng i và cột j. Định thức định nghĩa đệ quy: det(A) = a₁₁ nếu n = 1, và det(A) = Σⱼ₌₁ⁿ (−1)^(1+j) a₁ⱼ det(A[1j]) nếu n > 1. Phần bù đại số của aᵢⱼ là (−1)^(i+j) det(A[ij]). Ví dụ det(a b; c d) = ad − bc; det(1 1; 1 0) = −1. Quan trọng vì det(A) ≠ 0 là tiêu chuẩn khả nghịch (Định lý D.5), và vì định thức Vandermonde (Bài toán D-1) chứng minh nội suy đa thức là duy nhất (Chương 30). Chú ý: lưu ý của người tổng hợp — tính định thức theo đúng định nghĩa đệ quy này tốn Θ(n!) phép tính; trong thực tế người ta tính qua phân rã LU trong Θ(n³).
- **Ma trận xác định dương (positive-definite matrix):** ma trận n × n A với xᵀAx > 0 cho mọi n-vectơ x ≠ 0. Ví dụ Iₙ (xᵀx = Σ xᵢ² > 0); (2 1; 1 2) vì xᵀAx = x₁² + x₂² + (x₁ + x₂)²; còn (1 2; 2 1) không xác định dương vì x = (1, −1)ᵀ cho 1 − 2 − 2 + 1 = −2. Quan trọng vì ma trận đối xứng xác định dương luôn phân rã LU được mà không cần chọn trụ (Mục 28.3), và AᵀA với A có hạng cột đầy đủ thuộc loại này (Định lý D.6).
- **Ma trận Vandermonde (Vandermonde matrix):** ma trận n × n mà hàng k là (1, xₖ, xₖ², …, xₖⁿ⁻¹). Định thức là Π_{0≤j<k≤n−1} (xₖ − xⱼ), khác 0 khi các xₖ đôi một khác nhau. Ví dụ x = (1, 2, 3): det(1 1 1; 1 2 4; 1 3 9) = 2 = (2 − 1)(3 − 1)(3 − 2). Quan trọng vì đây là ma trận của hệ phương trình "tìm đa thức đi qua n điểm" (Chương 30).
- **Trường GF(2) (Galois field of two elements):** hệ số chỉ có 0 và 1, cộng và nhân như số nguyên nhưng chỉ giữ bit thấp nhất, nên 1 + 1 = 0 (phép cộng chính là XOR, phép nhân là AND). Ví dụ 1·1 + 1·1 = 0 trong GF(2). Quan trọng vì Bài toán D-2 cho thấy các khái niệm hạng, ảnh, nghịch ảnh vẫn dùng được trên trường này, và tạo ra một họ hoán vị bit có cấu trúc.
- **Hoán vị tuyến tính (linear permutation):** hoán vị của Sₙ = {0, …, 2ⁿ − 1} có dạng x ↦ Ax + c trên GF(2), với A là ma trận 0-1 n × n có hạng đầy đủ và c là vectơ n bit. Ví dụ n = 2, A = (1 0; 1 1), c = (0, 1)ᵀ cho 0 → 2, 1 → 1, 2 → 0, 3 → 3. Quan trọng (theo hiểu biết của người tổng hợp) vì các phép hoán vị bit hay gặp trong thực tế — hoán vị đảo bit của FFT (Chương 30), chuyển vị ma trận lưu trên đĩa, mã Gray — đều thuộc lớp này.

## Nội dung chi tiết

### 1. Phần mở đầu Phụ lục D (trang 1217)

Phụ lục mở đầu bằng nhận xét: ma trận xuất hiện trong rất nhiều ứng dụng, bao gồm — nhưng không hề giới hạn ở — tính toán khoa học. Người đọc đã gặp ma trận trước đây sẽ thấy phần lớn nội dung quen thuộc, nhưng có thể có vài điểm mới. Mục D.1 trình bày các định nghĩa và phép toán cơ bản trên ma trận; Mục D.2 trình bày một số tính chất cơ bản.

Lời giới thiệu Phần VIII (trang 1144) nói thêm về vai trò của phụ lục: nó định nghĩa ma trận, các phép toán và vài tính chất cơ bản; nếu đã học một khoá đại số tuyến tính thì người đọc có lẽ đã biết gần hết, nhưng có thể thấy tiện khi có một chỗ để tra ký hiệu và định nghĩa của sách.

### 2. Ma trận và các phép toán trên ma trận (D.1 Matrices and matrix operations, trang 1217–1222)

Mục này ôn các khái niệm cơ bản của lý thuyết ma trận và vài tính chất nền tảng.

#### Ma trận và vectơ (Matrices and vectors)

**Ma trận** (matrix) là một bảng số hình chữ nhật. Ví dụ

```text
A = ⎛ a₁₁  a₁₂  a₁₃ ⎞  =  ⎛ 1  2  3 ⎞                              (D.1)
    ⎝ a₂₁  a₂₂  a₂₃ ⎠     ⎝ 4  5  6 ⎠
```

là ma trận 2 × 3, viết A = (aᵢⱼ), trong đó với i = 1, 2 và j = 1, 2, 3, phần tử ở hàng i, cột j ký hiệu là aᵢⱼ. Sách dùng chữ hoa để chỉ ma trận và chữ thường tương ứng có chỉ số dưới để chỉ phần tử của nó. Tập mọi ma trận m × n có phần tử thực ký hiệu là ℝ^(m×n); tổng quát, tập ma trận m × n có phần tử lấy từ tập S ký hiệu là S^(m×n).

Trong bản tổng hợp này, khi viết ma trận trên một dòng, các hàng được ngăn bằng dấu chấm phẩy: (1 2 3; 4 5 6) là ma trận (D.1).

**Chuyển vị** (transpose) của ma trận A là ma trận Aᵀ có được bằng cách đổi hàng thành cột. Với ma trận A của (D.1):

```text
Aᵀ = ⎛ 1  4 ⎞
     ⎜ 2  5 ⎟
     ⎝ 3  6 ⎠
```

Tức là phần tử ở hàng i, cột j của Aᵀ là aⱼᵢ; một ma trận m × n chuyển vị thành ma trận n × m.

**Vectơ** (vector) là một mảng số một chiều. Ví dụ

```text
x = ⎛ 2 ⎞
    ⎜ 3 ⎟
    ⎝ 5 ⎠
```

là vectơ cỡ 3. Đôi khi sách gọi vectơ độ dài n là **n-vectơ** (n-vector). Vectơ ký hiệu bằng chữ thường, và phần tử thứ i của vectơ x cỡ n ký hiệu là xᵢ, với i = 1, 2, …, n. Sách quy ước dạng chuẩn của vectơ là **vectơ cột** (column vector), tương đương ma trận n × 1; **vectơ hàng** (row vector) tương ứng có được bằng phép chuyển vị:

```text
xᵀ = ( 2  3  5 )
```

**Vectơ đơn vị** (unit vector) eᵢ là vectơ có phần tử thứ i bằng 1 và mọi phần tử khác bằng 0. Cỡ của vectơ đơn vị thường rõ từ ngữ cảnh. Ví dụ trong ℝ⁴, e₃ = (0, 0, 1, 0)ᵀ.

**Ma trận không** (zero matrix) là ma trận mà mọi phần tử bằng 0. Ma trận này thường được ký hiệu 0, vì sự nhập nhằng giữa số 0 và ma trận gồm toàn số 0 thường dễ phân biệt nhờ ngữ cảnh. Nếu ý muốn nói là ma trận 0, thì cỡ của nó cũng phải suy ra từ ngữ cảnh.

#### Ma trận vuông (Square matrices)

Ma trận **vuông** (square) n × n xuất hiện rất thường xuyên. Có bảy trường hợp đặc biệt đáng chú ý.

**1. Ma trận đường chéo** (diagonal matrix): aᵢⱼ = 0 với mọi i ≠ j. Vì mọi phần tử ngoài đường chéo đều bằng 0, có thể xác định ma trận bằng cách liệt kê các phần tử trên đường chéo:

```text
                          ⎛ a₁₁   0   …   0  ⎞
diag(a₁₁, a₂₂, …, aₙₙ) =  ⎜  0   a₂₂  …   0  ⎟
                          ⎜  ⋮    ⋮   ⋱   ⋮  ⎟
                          ⎝  0    0   …  aₙₙ ⎠
```

**2. Ma trận đơn vị** (identity matrix) Iₙ cỡ n × n là ma trận đường chéo có toàn số 1 trên đường chéo:

```text
                          ⎛ 1  0  …  0 ⎞
Iₙ = diag(1, 1, …, 1)  =  ⎜ 0  1  …  0 ⎟
                          ⎜ ⋮  ⋮  ⋱  ⋮ ⎟
                          ⎝ 0  0  …  1 ⎠
```

Khi I xuất hiện không có chỉ số dưới, cỡ của nó suy từ ngữ cảnh. Cột thứ i của ma trận đơn vị chính là vectơ đơn vị eᵢ.

**3. Ma trận ba đường chéo** (tridiagonal matrix) T là ma trận có tᵢⱼ = 0 nếu |i − j| > 1. Phần tử khác 0 chỉ có thể nằm trên đường chéo chính, ngay trên đường chéo chính (tᵢ,ᵢ₊₁ với i = 1, 2, …, n − 1), hoặc ngay dưới đường chéo chính (tᵢ₊₁,ᵢ với i = 1, 2, …, n − 1):

```text
    ⎛ t₁₁  t₁₂   0    0   …     0          0          0      ⎞
    ⎜ t₂₁  t₂₂  t₂₃   0   …     0          0          0      ⎟
    ⎜  0   t₃₂  t₃₃  t₃₄  …     0          0          0      ⎟
T = ⎜  ⋮    ⋮    ⋮    ⋮   ⋱     ⋮          ⋮          ⋮      ⎟
    ⎜  0    0    0    0   …  tₙ₋₂,ₙ₋₂   tₙ₋₂,ₙ₋₁      0      ⎟
    ⎜  0    0    0    0   …  tₙ₋₁,ₙ₋₂   tₙ₋₁,ₙ₋₁   tₙ₋₁,ₙ    ⎟
    ⎝  0    0    0    0   …     0       tₙ,ₙ₋₁      tₙₙ      ⎠
```

Ví dụ (người tổng hợp) với n = 4: (2 −1 0 0; −1 2 −1 0; 0 −1 2 −1; 0 0 −1 2) là ma trận ba đường chéo; nó có tối đa 3n − 2 = 10 phần tử khác 0 thay vì n² = 16.

**4. Ma trận tam giác trên** (upper-triangular matrix) U là ma trận có uᵢⱼ = 0 nếu i > j. Mọi phần tử dưới đường chéo bằng 0:

```text
    ⎛ u₁₁  u₁₂  …  u₁ₙ ⎞
U = ⎜  0   u₂₂  …  u₂ₙ ⎟
    ⎜  ⋮    ⋮   ⋱   ⋮  ⎟
    ⎝  0    0   …  uₙₙ ⎠
```

Ma trận tam giác trên được gọi là **tam giác trên đơn vị** (unit upper-triangular) nếu mọi phần tử trên đường chéo đều bằng 1.

**5. Ma trận tam giác dưới** (lower-triangular matrix) L là ma trận có lᵢⱼ = 0 nếu i < j. Mọi phần tử trên đường chéo bằng 0:

```text
    ⎛ l₁₁   0   …   0  ⎞
L = ⎜ l₂₁  l₂₂  …   0  ⎟
    ⎜  ⋮    ⋮   ⋱   ⋮  ⎟
    ⎝ lₙ₁  lₙ₂  …  lₙₙ ⎠
```

Ma trận tam giác dưới được gọi là **tam giác dưới đơn vị** (unit lower-triangular) nếu mọi phần tử trên đường chéo đều bằng 1. Ví dụ (người tổng hợp): (1 0 0; 2 1 0; 5 −3 1) là tam giác dưới đơn vị, còn (2 1 4; 0 3 −1; 0 0 7) là tam giác trên (không đơn vị).

**6. Ma trận hoán vị** (permutation matrix) P có đúng một số 1 ở mỗi hàng và mỗi cột (sách in "mỗi hàng hoặc cột" — xem khối Lưu ý), và số 0 ở mọi chỗ khác. Ví dụ của sách:

```text
    ⎛ 0  1  0  0  0 ⎞
    ⎜ 0  0  0  1  0 ⎟
P = ⎜ 1  0  0  0  0 ⎟
    ⎜ 0  0  0  0  1 ⎟
    ⎝ 0  0  1  0  0 ⎠
```

Ma trận này được gọi là ma trận hoán vị vì nhân một vectơ x với nó có tác dụng hoán vị (sắp xếp lại) các phần tử của x. Kiểm tra với ma trận trên (người tổng hợp): hàng 1 có số 1 ở cột 2 nên phần tử thứ nhất của Px là x₂; tương tự hàng 2 cho x₄, hàng 3 cho x₁, hàng 4 cho x₅, hàng 5 cho x₃. Vậy Px = (x₂, x₄, x₁, x₅, x₃)ᵀ; với x = (10, 20, 30, 40, 50)ᵀ thì Px = (20, 40, 10, 50, 30)ᵀ. Exercise D.1-4 khảo sát thêm các tính chất của ma trận hoán vị.

**7. Ma trận đối xứng** (symmetric matrix) A thoả điều kiện A = Aᵀ. Ví dụ

```text
⎛ 1  2  3 ⎞
⎜ 2  6  4 ⎟
⎝ 3  4  5 ⎠
```

là ma trận đối xứng: a₁₂ = a₂₁ = 2, a₁₃ = a₃₁ = 3, a₂₃ = a₃₂ = 4.

Quan hệ giữa các loại (người tổng hợp): ma trận đường chéo vừa là tam giác trên, vừa là tam giác dưới, vừa là ba đường chéo, vừa đối xứng; ma trận đơn vị là ma trận đường chéo và cũng là ma trận hoán vị (của hoán vị đồng nhất).

#### Các phép toán cơ bản trên ma trận (Basic matrix operations)

Phần tử của ma trận hay vectơ là các số lấy từ một hệ số, chẳng hạn số thực, số phức, hoặc số nguyên modulo một số nguyên tố. Hệ số đó định nghĩa cách cộng và nhân các số. Ta mở rộng các định nghĩa này để bao gồm phép cộng và phép nhân ma trận.

**Phép cộng ma trận** (matrix addition). Nếu A = (aᵢⱼ) và B = (bᵢⱼ) là hai ma trận m × n, thì tổng C = (cᵢⱼ) = A + B là ma trận m × n xác định bởi

```text
cᵢⱼ = aᵢⱼ + bᵢⱼ
```

với i = 1, 2, …, m và j = 1, 2, …, n. Nghĩa là phép cộng ma trận thực hiện theo từng thành phần. Ma trận không là phần tử đơn vị của phép cộng ma trận:

```text
A + 0 = A = 0 + A
```

**Nhân vô hướng** (scalar multiple). Nếu λ là một số và A = (aᵢⱼ) là ma trận, thì λA = (λaᵢⱼ) là bội vô hướng của A, có được bằng cách nhân mọi phần tử của A với λ. Trường hợp riêng, **ma trận đối** (negative) của A = (aᵢⱼ) được định nghĩa là −1 · A = −A, nên phần tử (i, j) của −A là −aᵢⱼ. Do đó

```text
A + (−A) = 0 = (−A) + A
```

Ma trận đối được dùng để định nghĩa **phép trừ ma trận** (matrix subtraction): A − B = A + (−B).

Ví dụ (người tổng hợp): (1 2; 3 4) + (5 6; 7 8) = (6 8; 10 12); 3 · (1 2; 3 4) = (3 6; 9 12); (1 2; 3 4) − (5 6; 7 8) = (−4 −4; −4 −4).

**Phép nhân ma trận** (matrix multiplication). Bắt đầu với hai ma trận A và B **tương thích** (compatible), theo nghĩa số cột của A bằng số hàng của B. (Nói chung, một biểu thức chứa tích AB luôn được ngầm hiểu là A và B tương thích.) Nếu A = (aᵢₖ) là ma trận m × n và B = (bₖⱼ) là ma trận n × p, thì tích C = AB là ma trận m × p C = (cᵢⱼ), trong đó

```text
cᵢⱼ = Σₖ₌₁ⁿ aᵢₖ bₖⱼ                                                (D.2)
```

với i = 1, 2, …, m và j = 1, 2, …, p. Bằng lời: phần tử ở hàng i, cột j của tích là tổng các tích từng cặp giữa hàng i của A và cột j của B.

Thủ tục SQUARE-MATRIX-MULTIPLY ở Mục 4.2 cài đặt phép nhân ma trận theo cách thẳng thắn dựa trên (D.2), giả sử các ma trận vuông: m = n = p. Để nhân hai ma trận n × n, SQUARE-MATRIX-MULTIPLY thực hiện n³ phép nhân và n²(n − 1) phép cộng, nên thời gian chạy là Θ(n³). Nhắc lại thủ tục (đã chép ở bản tổng hợp Chương 4):

```text
SQUARE-MATRIX-MULTIPLY(A, B)
1  n = A.rows
2  let C be a new n × n matrix
3  for i = 1 to n
4      for j = 1 to n
5          cᵢⱼ = 0
6          for k = 1 to n
7              cᵢⱼ = cᵢⱼ + aᵢₖ · bₖⱼ
8  return C
```

Ba vòng lặp lồng nhau, mỗi vòng n lần, nên dòng 7 chạy n³ lần. (Về số phép cộng n²(n − 1) so với n³ lần thực hiện dòng 7, xem khối Lưu ý.)

Ví dụ chạy tay (người tổng hợp), nhân ma trận (D.1) với chuyển vị của nó: A (2 × 3) nhân Aᵀ (3 × 2) cho ma trận 2 × 2:

```text
c₁₁ = 1·1 + 2·2 + 3·3 = 14        c₁₂ = 1·4 + 2·5 + 3·6 = 32
c₂₁ = 4·1 + 5·2 + 6·3 = 32        c₂₂ = 4·4 + 5·5 + 6·6 = 77
AAᵀ = (14 32; 32 77)  — một ma trận đối xứng (đúng như Exercise D.1-2 dự báo)
```

Còn AᵀA là ma trận 3 × 3: (17 22 27; 22 29 36; 27 36 45). Hai tích AAᵀ và AᵀA có cỡ khác nhau — một minh hoạ sớm rằng thứ tự nhân quan trọng.

**Các tính chất đại số.** Ma trận có nhiều (nhưng không phải tất cả) tính chất đại số đặc trưng của số.

- Ma trận đơn vị là phần tử đơn vị của phép nhân ma trận: IₘA = AIₙ = A với mọi ma trận A cỡ m × n. (Chú ý cỡ của I ở hai phía khác nhau khi A không vuông.)
- Nhân với ma trận không cho ma trận không: A0 = 0.
- Phép nhân ma trận có tính kết hợp: A(BC) = (AB)C với mọi ma trận A, B, C tương thích.
- Phép nhân phân phối đối với phép cộng: A(B + C) = AB + AC và (B + C)D = BD + CD.
- Với n > 1, phép nhân ma trận n × n **không giao hoán**. Ví dụ, nếu A = (0 1; 0 0) và B = (0 0; 1 0), thì

```text
AB = ⎛ 1  0 ⎞        BA = ⎛ 0  0 ⎞
     ⎝ 0  0 ⎠             ⎝ 0  1 ⎠
```

Kiểm tra (người tổng hợp): phần tử (1, 1) của AB là a₁₁b₁₁ + a₁₂b₂₁ = 0·0 + 1·1 = 1, các phần tử còn lại bằng 0; phần tử (2, 2) của BA là b₂₁a₁₂ + b₂₂a₂₂ = 1·1 + 0·0 = 1, các phần tử còn lại bằng 0. Hai tích khác nhau.

**Tích ma trận–vectơ và vectơ–vectơ.** Tích ma trận–vectơ hay vectơ–vectơ được định nghĩa như thể vectơ là ma trận n × 1 tương đương (hoặc ma trận 1 × n nếu là vectơ hàng). Vì vậy nếu A là ma trận m × n và x là n-vectơ thì Ax là m-vectơ. Ví dụ (người tổng hợp): ma trận (D.1) nhân x = (1, 1, 1)ᵀ cho Ax = (6, 15)ᵀ — tổng từng hàng.

Nếu x và y là hai n-vectơ thì

```text
xᵀy = Σᵢ₌₁ⁿ xᵢ yᵢ
```

là một số (đúng ra là ma trận 1 × 1), gọi là **tích trong** (inner product) của x và y. Ma trận xyᵀ là ma trận n × n Z, gọi là **tích ngoài** (outer product) của x và y, với zᵢⱼ = xᵢyⱼ.

**Chuẩn (Euclid)** ‖x‖ của n-vectơ x được định nghĩa bởi

```text
‖x‖ = (x₁² + x₂² + … + xₙ²)^(1/2)
    = (xᵀx)^(1/2)
```

Như vậy chuẩn của x là độ dài của nó trong không gian Euclid n chiều.

Ví dụ (người tổng hợp) với x = (2, 3, 5)ᵀ và y = (1, 0, 2)ᵀ:

```text
xᵀy  = 2·1 + 3·0 + 5·2 = 12
xyᵀ  = ⎛ 2·1  2·0  2·2 ⎞   ⎛ 2  0   4 ⎞
       ⎜ 3·1  3·0  3·2 ⎟ = ⎜ 3  0   6 ⎟     (mọi hàng tỷ lệ với yᵀ: hạng 1)
       ⎝ 5·1  5·0  5·2 ⎠   ⎝ 5  0  10 ⎠
‖x‖  = (4 + 9 + 25)^(1/2) = √38 ≈ 6,164
‖y‖  = √5 ≈ 2,236
```

Nhận xét của người tổng hợp: tích ngoài của hai vectơ khác 0 luôn có hạng đúng 1 — chính là trường hợp r = 1 của định nghĩa hạng tương đương ở Mục D.2 (A = BC với B cỡ n × 1, C cỡ 1 × n).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: ma trận là cấu trúc dữ liệu trung tâm của học máy và đồ hoạ máy tính. Một lớp mạng nơ-ron "kết nối đầy đủ" tính y = Wx + b — đúng phép nhân ma trận–vectơ (D.2) cộng một vectơ; huấn luyện theo lô biến nó thành nhân hai ma trận, và các bộ tăng tốc (GPU, TPU) được thiết kế chủ yếu để làm phép này thật nhanh. Trong đồ hoạ 3D, mỗi phép xoay, co giãn, chiếu là một ma trận 4 × 4, và việc ghép các phép biến đổi là phép nhân ma trận — tính không giao hoán thể hiện ngay: "xoay rồi dịch" khác "dịch rồi xoay". Thư viện BLAS (hàm GEMM) và LAPACK là các cài đặt chuẩn của những phép toán trong phụ lục này.

### 3. Các tính chất cơ bản của ma trận (D.2 Basic matrix properties, trang 1222–1226)

Mục này định nghĩa các tính chất cơ bản liên quan tới ma trận: nghịch đảo, phụ thuộc và độc lập tuyến tính, hạng, và định thức. Mục cũng định nghĩa lớp ma trận xác định dương.

#### Nghịch đảo, hạng và định thức (Matrix inverses, ranks, and determinants)

**Nghịch đảo** (inverse) của ma trận A cỡ n × n là ma trận n × n, ký hiệu A⁻¹ (nếu tồn tại), thoả AA⁻¹ = Iₙ = A⁻¹A. Ví dụ:

```text
⎛ 1  1 ⎞⁻¹   ⎛ 0   1 ⎞
⎝ 1  0 ⎠   = ⎝ 1  −1 ⎠
```

Kiểm tra (người tổng hợp): (1 1; 1 0)(0 1; 1 −1) = (1·0 + 1·1, 1·1 + 1·(−1); 1·0 + 0·1, 1·1 + 0·(−1)) = (1 0; 0 1). Nhân theo thứ tự ngược lại: (0 1; 1 −1)(1 1; 1 0) = (0 + 1, 0 + 0; 1 − 1, 1 − 0) = (1 0; 0 1). Đúng cả hai phía.

Nhiều ma trận n × n khác không không có nghịch đảo. Ma trận không có nghịch đảo được gọi là **không khả nghịch** (noninvertible), hay **suy biến** (singular). Ví dụ một ma trận khác không mà suy biến:

```text
⎛ 1  0 ⎞
⎝ 1  0 ⎠
```

Lý do (người tổng hợp): hai hàng của ma trận này bằng nhau, nên với mọi ma trận X, tích (1 0; 1 0)·X cũng có hai hàng bằng nhau (hàng i của tích là hàng i của ma trận nhân với X). Ma trận I₂ = (1 0; 0 1) có hai hàng khác nhau, nên không có X nào làm tích bằng I₂.

Nếu ma trận có nghịch đảo, nó được gọi là **khả nghịch** (invertible), hay **không suy biến** (nonsingular). Nghịch đảo của ma trận, nếu tồn tại, là duy nhất (Exercise D.2-1). Nếu A và B là hai ma trận n × n không suy biến, thì

```text
(BA)⁻¹ = A⁻¹B⁻¹
```

(thứ tự đảo ngược: kiểm tra (BA)(A⁻¹B⁻¹) = B(AA⁻¹)B⁻¹ = BB⁻¹ = I, nhờ tính kết hợp). Phép nghịch đảo giao hoán với phép chuyển vị:

```text
(A⁻¹)ᵀ = (Aᵀ)⁻¹
```

(kiểm tra: Aᵀ(A⁻¹)ᵀ = (A⁻¹A)ᵀ = Iᵀ = I, dùng (XY)ᵀ = YᵀXᵀ của Exercise D.1-2.)

**Phụ thuộc tuyến tính** (linearly dependent). Các vectơ x₁, x₂, …, xₙ phụ thuộc tuyến tính nếu tồn tại các hệ số c₁, c₂, …, cₙ, không phải tất cả đều bằng 0, sao cho c₁x₁ + c₂x₂ + … + cₙxₙ = 0. Ví dụ, ba vectơ hàng x₁ = (1 2 3), x₂ = (2 6 4) và x₃ = (4 11 9) phụ thuộc tuyến tính, vì 2x₁ + 3x₂ − 2x₃ = 0. Kiểm tra từng thành phần (người tổng hợp):

```text
thành phần 1:  2·1 + 3·2  − 2·4  = 2 + 6  − 8  = 0
thành phần 2:  2·2 + 3·6  − 2·11 = 4 + 18 − 22 = 0
thành phần 3:  2·3 + 3·4  − 2·9  = 6 + 12 − 18 = 0
```

Nếu các vectơ không phụ thuộc tuyến tính thì chúng **độc lập tuyến tính** (linearly independent). Ví dụ, các cột của ma trận đơn vị độc lập tuyến tính (c₁e₁ + … + cₙeₙ = (c₁, …, cₙ)ᵀ chỉ bằng 0 khi mọi cᵢ = 0).

**Hạng** (rank). **Hạng cột** (column rank) của ma trận A cỡ m × n khác không là kích thước của tập cột độc lập tuyến tính lớn nhất của A. Tương tự, **hạng hàng** (row rank) của A là kích thước của tập hàng độc lập tuyến tính lớn nhất. Một tính chất nền tảng của mọi ma trận A là hạng hàng luôn bằng hạng cột, nên có thể gọi đơn giản là **hạng** của A. Hạng của ma trận m × n là một số nguyên trong khoảng từ 0 tới min(m, n), kể cả hai đầu. (Hạng của ma trận không là 0, hạng của ma trận đơn vị n × n là n.)

Một định nghĩa khác, tương đương và thường hữu ích hơn: hạng của ma trận A cỡ m × n khác không là số r nhỏ nhất sao cho tồn tại hai ma trận B và C, lần lượt cỡ m × r và r × n, với

```text
A = BC
```

Ví dụ (người tổng hợp): ma trận ghép từ ba hàng x₁, x₂, x₃ ở trên, M = (1 2 3; 2 6 4; 4 11 9), có hạng 2: x₁ và x₂ độc lập (không vectơ nào là bội của vectơ kia), còn x₃ = x₁ + (3/2)x₂ là tổ hợp của chúng (từ 2x₁ + 3x₂ − 2x₃ = 0). Theo định nghĩa thứ hai, M = BC với B cỡ 3 × 2 và C cỡ 2 × 3:

```text
    ⎛ 1    0  ⎞
B = ⎜ 0    1  ⎟ ,   C = ⎛ 1  2  3 ⎞      (hàng của C là x₁, x₂;
    ⎝ 1   3/2 ⎠         ⎝ 2  6  4 ⎠       hàng i của B cho hệ số tổ hợp)
```

Hàng 3 của BC là 1·(1 2 3) + (3/2)·(2 6 4) = (1 + 3, 2 + 9, 3 + 6) = (4 11 9). Đúng.

Ma trận vuông n × n có **hạng đầy đủ** (full rank) nếu hạng của nó là n. Ma trận m × n có **hạng cột đầy đủ** (full column rank) nếu hạng của nó là n (tức mọi cột độc lập tuyến tính; điều này đòi m ≥ n). Định lý sau nêu một tính chất nền tảng của hạng.

**Định lý D.1.** Ma trận vuông có hạng đầy đủ khi và chỉ khi nó không suy biến. ∎ (Sách không chứng minh.)

**Vectơ không** (null vector) của ma trận A là một vectơ khác không x sao cho Ax = 0. Định lý sau (chứng minh để cho Exercise D.2-7) và hệ quả của nó nối khái niệm hạng cột và tính suy biến với vectơ không.

**Định lý D.2.** Ma trận A có hạng cột đầy đủ khi và chỉ khi nó không có vectơ không. ∎

**Hệ quả D.3.** Ma trận vuông A suy biến khi và chỉ khi nó có vectơ không. ∎

Ý chứng minh (người tổng hợp): Ax = x₁a₁ + x₂a₂ + … + xₙaₙ, với aⱼ là cột j của A. Vậy "có x ≠ 0 với Ax = 0" nghĩa đúng là "các cột của A phụ thuộc tuyến tính", tức là "A không có hạng cột đầy đủ" — đó là Định lý D.2. Với ma trận vuông, hạng cột đầy đủ là hạng đầy đủ, và theo Định lý D.1 là không suy biến — đó là Hệ quả D.3. Ví dụ: (1 0; 1 0) có vectơ không x = (0, 1)ᵀ, đúng là ma trận suy biến; M ở trên có vectơ không x = (2, 3, −2)ᵀ nếu xếp x₁, x₂, x₃ làm **cột** (tức với Mᵀ), và Mᵀ suy biến.

**Định thức** (determinant). **Ma trận con** thứ ij (ijth minor) của ma trận A cỡ n × n, với n > 1, là ma trận (n − 1) × (n − 1) A[ij] có được bằng cách xoá hàng i và cột j của A. Định thức của ma trận A cỡ n × n được định nghĩa đệ quy theo các ma trận con:

```text
          ⎧ a₁₁                                   nếu n = 1
det(A) =  ⎨
          ⎩ Σⱼ₌₁ⁿ (−1)^(1+j) a₁ⱼ det(A[1j])      nếu n > 1
```

Số hạng (−1)^(i+j) det(A[ij]) được gọi là **phần bù đại số** (cofactor) của phần tử aᵢⱼ. Như vậy định nghĩa trên chính là "khai triển theo hàng 1": định thức bằng tổng các phần tử của hàng 1 nhân với phần bù đại số của chúng.

Ví dụ chạy tay (người tổng hợp):

- n = 2: det(a b; c d) = a · det(d) − b · det(c) = ad − bc. Với ma trận (1 1; 1 0): 1·0 − 1·1 = −1. Với (1 0; 1 0): 1·0 − 0·1 = 0.
- n = 3, ma trận đối xứng của sách A = (1 2 3; 2 6 4; 3 4 5):

```text
A[11] = (6 4; 4 5)  → det = 6·5 − 4·4 = 30 − 16 = 14
A[12] = (2 4; 3 5)  → det = 2·5 − 4·3 = 10 − 12 = −2
A[13] = (2 6; 3 4)  → det = 2·4 − 6·3 =  8 − 18 = −10
det(A) = (+1)·1·14 + (−1)·2·(−2) + (+1)·3·(−10)
       = 14 + 4 − 30 = −12
```

- Ma trận M = (1 2 3; 2 6 4; 4 11 9) có các hàng phụ thuộc: det = 1·(54 − 44) − 2·(18 − 16) + 3·(22 − 24) = 10 − 4 − 6 = 0, khớp với Định lý D.5 dưới đây.

Các định lý sau, mà sách bỏ qua chứng minh, nêu các tính chất nền tảng của định thức.

**Định lý D.4 (Tính chất của định thức).** Định thức của ma trận vuông A có các tính chất sau:

- Nếu một hàng hay một cột nào đó của A toàn số 0 thì det(A) = 0.
- Định thức của A được nhân với λ nếu mọi phần tử của một hàng (hoặc một cột) nào đó của A được nhân với λ.
- Định thức của A không đổi nếu các phần tử của một hàng (tương ứng, một cột) được cộng vào các phần tử của một hàng (tương ứng, một cột) khác.
- Định thức của A bằng định thức của Aᵀ.
- Định thức của A được nhân với −1 nếu đổi chỗ hai hàng (hoặc hai cột) bất kỳ.

Ngoài ra, với mọi ma trận vuông A và B, det(AB) = det(A) det(B). ∎

Kiểm tra từng tính chất trên ma trận 2 × 2 (người tổng hợp), với A = (1 2; 3 4), det(A) = 4 − 6 = −2:

```text
hàng 2 toàn 0:        det(1 2; 0 0) = 0
nhân hàng 1 với 5:    det(5 10; 3 4) = 20 − 30 = −10 = 5·(−2)
cộng hàng 1 vào 2:    det(1 2; 4 6)  = 6 − 8   = −2   (không đổi)
chuyển vị:            det(1 3; 2 4)  = 4 − 6   = −2
đổi hai hàng:         det(3 4; 1 2)  = 6 − 4   =  2 = −1·(−2)
tích: B = (0 1; 1 1), det(B) = −1;  AB = (2 3; 4 7), det(AB) = 14 − 12 = 2
      = (−2)·(−1)
```

Nhận xét của người tổng hợp: từ tính chất 2 và 3 suy ra cộng một **bội** của hàng này vào hàng khác cũng không đổi định thức (nhân hàng với λ, cộng vào, rồi chia lại hàng đó cho λ khi λ ≠ 0) — đây là nền của phép khử Gauss: đưa A về tam giác trên U bằng các phép cộng bội hàng (và đổi hàng, mỗi lần đổi dấu), rồi det(A) = ± tích đường chéo của U (Exercise D.2-2).

**Định lý D.5.** Ma trận A cỡ n × n suy biến khi và chỉ khi det(A) = 0. ∎

Kết hợp D.1, D.3, D.5, với ma trận vuông A, bốn mệnh đề sau tương đương: A không suy biến; A có hạng đầy đủ; A không có vectơ không; det(A) ≠ 0.

#### Ma trận xác định dương (Positive-definite matrices)

Ma trận xác định dương đóng vai trò quan trọng trong nhiều ứng dụng. Ma trận A cỡ n × n là **xác định dương** (positive-definite) nếu xᵀAx > 0 với mọi n-vectơ x ≠ 0. Ví dụ, ma trận đơn vị xác định dương, vì với mọi vectơ khác không x = (x₁ x₂ ⋯ xₙ)ᵀ,

```text
xᵀIₙx = xᵀx
      = Σᵢ₌₁ⁿ xᵢ²
      > 0
```

(tổng các bình phương, có ít nhất một số hạng dương vì x ≠ 0).

Ví dụ thêm (người tổng hợp): A = (2 1; 1 2) cho xᵀAx = 2x₁² + 2x₁x₂ + 2x₂² = x₁² + x₂² + (x₁ + x₂)² > 0 khi x ≠ 0, nên xác định dương; còn (1 2; 2 1) với x = (1, −1)ᵀ cho xᵀAx = 1 − 2 − 2 + 1 = −2 < 0, nên không xác định dương dù mọi phần tử đều dương.

Ma trận xuất hiện trong ứng dụng thường xác định dương nhờ định lý sau.

**Định lý D.6.** Với mọi ma trận A có hạng cột đầy đủ, ma trận AᵀA xác định dương.

*Chứng minh.* Ta phải chứng minh xᵀ(AᵀA)x > 0 với mọi vectơ khác không x. Với mọi vectơ x,

```text
xᵀ(AᵀA)x = (Ax)ᵀ(Ax)        (theo Exercise D.1-2: xᵀAᵀ = (Ax)ᵀ)
         = ‖Ax‖²
```

Chú ý ‖Ax‖² chính là tổng bình phương các phần tử của vectơ Ax. Do đó ‖Ax‖² ≥ 0. Nếu ‖Ax‖² = 0 thì mọi phần tử của Ax bằng 0, tức là Ax = 0. Vì A có hạng cột đầy đủ, Ax = 0 kéo theo x = 0, theo Định lý D.2. Vậy AᵀA xác định dương. ∎

Ví dụ (người tổng hợp): A = (1 0; 0 1; 1 1) cỡ 3 × 2 có hai cột (1, 0, 1)ᵀ và (0, 1, 1)ᵀ độc lập, nên hạng cột đầy đủ. AᵀA = (1·1 + 0·0 + 1·1, 1·0 + 0·1 + 1·1; 0·1 + 1·0 + 1·1, 0·0 + 1·1 + 1·1) = (2 1; 1 2) — đúng ma trận đã thấy xác định dương ở trên. Với x = (1, −1)ᵀ: Ax = (1, −1, 0)ᵀ, ‖Ax‖² = 2, và xᵀ(AᵀA)x = 2 − 1 − 1 + 2 = 2. Khớp. Ngược lại, với A = (1 2; 2 4; 3 6) (cột 2 gấp đôi cột 1, không có hạng cột đầy đủ), x = (2, −1)ᵀ cho Ax = 0, nên xᵀAᵀAx = 0: AᵀA không xác định dương.

Mục 28.3 khảo sát thêm các tính chất khác của ma trận xác định dương (ma trận đối xứng xác định dương không suy biến, các ma trận con chính ở góc trên-trái và phần bù Schur của nó cũng xác định dương, nên phân rã LU không cần chọn trụ; và bài toán bình phương tối thiểu giải hệ (AᵀA)c = Aᵀy).

#### Ví dụ hôm nay

Theo hiểu biết của người tổng hợp: Định lý D.6 là lý do hồi quy tuyến tính bình phương tối thiểu có nghiệm duy nhất khi các cột dữ liệu (các đặc trưng) độc lập tuyến tính; khi hai cột gần như phụ thuộc (đa cộng tuyến), AᵀA gần suy biến và nghiệm rất nhạy với sai số — người ta thêm λI vào AᵀA (hồi quy ridge) để nó chắc chắn xác định dương. Trong tối ưu hoá, ma trận Hessian xác định dương tại một điểm dừng nghĩa là điểm đó là cực tiểu địa phương; ma trận hiệp phương sai trong thống kê luôn đối xứng và nửa xác định dương. Định thức thì hiếm khi được tính trực tiếp trong phần mềm số: các thư viện tính nó qua phân rã LU, đúng như hệ quả của Định lý D.4.

## Bài tập và bài toán cuối chương

### Bài tập Mục D.1 (trang 1222)

- **D.1-1:** Chứng minh nếu A và B là hai ma trận đối xứng n × n thì A + B và A − B cũng đối xứng. *Lời giải của người tổng hợp:* phép chuyển vị tuyến tính theo từng phần tử: phần tử (i, j) của (A + B)ᵀ là aⱼᵢ + bⱼᵢ, tức (A + B)ᵀ = Aᵀ + Bᵀ = A + B. Tương tự (A − B)ᵀ = Aᵀ − Bᵀ = A − B. Ví dụ: (1 2; 2 3) + (0 5; 5 1) = (1 7; 7 4), vẫn đối xứng.
- **D.1-2:** Chứng minh (AB)ᵀ = BᵀAᵀ và AᵀA luôn là ma trận đối xứng. *Lời giải của người tổng hợp:* với A cỡ m × n, B cỡ n × p, phần tử (i, j) của (AB)ᵀ là phần tử (j, i) của AB, bằng Σₖ aⱼₖbₖᵢ. Phần tử (i, j) của BᵀAᵀ là Σₖ (Bᵀ)ᵢₖ(Aᵀ)ₖⱼ = Σₖ bₖᵢaⱼₖ — cùng một tổng. Từ đó (AᵀA)ᵀ = Aᵀ(Aᵀ)ᵀ = AᵀA, nên AᵀA đối xứng. Ví dụ với ma trận (D.1): AᵀA = (17 22 27; 22 29 36; 27 36 45), đối xứng. Đây là đẳng thức dùng trong chứng minh Định lý D.6.
- **D.1-3:** Chứng minh tích hai ma trận tam giác dưới là tam giác dưới. *Lời giải của người tổng hợp:* gọi L, M tam giác dưới, C = LM, cᵢⱼ = Σₖ lᵢₖmₖⱼ. Xét i < j. Số hạng lᵢₖ khác 0 chỉ khi k ≤ i; số hạng mₖⱼ khác 0 chỉ khi k ≥ j. Không có k nào vừa k ≤ i vừa k ≥ j (vì i < j), nên mọi tích bằng 0 và cᵢⱼ = 0. Ngoài ra cᵢᵢ = lᵢᵢmᵢᵢ (chỉ k = i đóng góp), nên tích hai ma trận tam giác dưới **đơn vị** cũng là tam giác dưới đơn vị — điều Chương 28 cần.
- **D.1-4:** Chứng minh nếu P là ma trận hoán vị n × n và A là ma trận n × n thì PA là A với các hàng bị hoán vị, và AP là A với các cột bị hoán vị. Chứng minh tích hai ma trận hoán vị là ma trận hoán vị. *Lời giải của người tổng hợp:* gọi π là hoán vị sao cho hàng i của P có số 1 ở cột π(i), tức pᵢₖ = 1 khi k = π(i) và bằng 0 khi khác. Khi đó (PA)ᵢⱼ = Σₖ pᵢₖaₖⱼ = a_{π(i), j}: hàng i của PA là hàng π(i) của A. Tương tự (AP)ᵢⱼ = Σₖ aᵢₖpₖⱼ = a_{i, π⁻¹(j)} (chỉ có k với π(k) = j đóng góp): cột j của AP là cột π⁻¹(j) của A. Với hai ma trận hoán vị P, Q: PQ là Q với các hàng bị hoán vị; mỗi hàng của Q có đúng một số 1 và việc đổi chỗ các hàng không làm thay đổi số số 1 trên mỗi cột (vẫn đúng một), nên PQ là ma trận hoán vị. Ví dụ với P của sách và A có các hàng r₁, …, r₅, PA có các hàng r₂, r₄, r₁, r₅, r₃.

### Bài tập Mục D.2 (trang 1225–1226)

- **D.2-1:** Chứng minh nghịch đảo của ma trận là duy nhất: nếu B và C đều là nghịch đảo của A thì B = C. *Lời giải của người tổng hợp:* B = BI = B(AC) = (BA)C = IC = C, dùng AC = I, BA = I và tính kết hợp. (Thực ra chứng minh này chỉ cần B là nghịch đảo trái, C là nghịch đảo phải.)
- **D.2-2:** Chứng minh định thức của ma trận tam giác dưới hoặc tam giác trên bằng tích các phần tử trên đường chéo. Chứng minh nghịch đảo của ma trận tam giác dưới, nếu tồn tại, là tam giác dưới. *Lời giải của người tổng hợp:*
  - Định thức, quy nạp theo n với L tam giác dưới. n = 1 hiển nhiên. Với n > 1, hàng 1 của L là (l₁₁, 0, …, 0), nên khai triển theo định nghĩa chỉ còn số hạng j = 1: det(L) = l₁₁ det(L[11]); L[11] (bỏ hàng 1, cột 1) vẫn là tam giác dưới, theo giả thiết quy nạp có định thức l₂₂⋯lₙₙ. Với U tam giác trên: Uᵀ là tam giác dưới cùng đường chéo, và det(U) = det(Uᵀ) (Định lý D.4). Ví dụ det(2 1 4; 0 3 −1; 0 0 7) = 2·3·7 = 42.
  - Nghịch đảo: nếu L khả nghịch thì det(L) = Π lᵢᵢ ≠ 0, nên mọi lᵢᵢ ≠ 0. Viết L dạng khối L = (l₁₁ 0; v L′) với v là cột (n − 1) phần tử và L′ tam giác dưới khả nghịch. Kiểm tra trực tiếp: ma trận (1/l₁₁ 0; −L′⁻¹v/l₁₁ L′⁻¹) nhân với L cho (1 0; 0 I). Theo quy nạp L′⁻¹ tam giác dưới, và hàng đầu của ma trận này là (1/l₁₁, 0, …, 0), nên nó tam giác dưới; theo D.2-1 nó chính là L⁻¹. Ví dụ (2 0; 3 1)⁻¹ = (1/2 0; −3/2 1).
- **D.2-3:** Chứng minh nếu P là ma trận hoán vị thì P khả nghịch, nghịch đảo của nó là Pᵀ, và Pᵀ là ma trận hoán vị. *Lời giải của người tổng hợp:* (PPᵀ)ᵢⱼ = Σₖ pᵢₖpⱼₖ, bằng 1 khi hàng i và hàng j có số 1 ở cùng một cột, tức khi i = j (mỗi cột chỉ có một số 1), và bằng 0 khi i ≠ j. Vậy PPᵀ = I; lập luận tương tự với cột cho PᵀP = I. Pᵀ có các hàng là các cột của P, mỗi cột của P có đúng một số 1, nên Pᵀ là ma trận hoán vị. Ý nghĩa: "hoàn tác" một hoán vị không cần khử Gauss, chỉ cần chuyển vị.
- **D.2-4:** Cho A, B là hai ma trận n × n với AB = I. Chứng minh nếu A′ có được từ A bằng cách cộng hàng j vào hàng i, thì trừ cột i khỏi cột j của B sẽ được nghịch đảo B′ của A′. *Lời giải của người tổng hợp:* phép "cộng hàng j vào hàng i" là nhân trái với E = I + eᵢeⱼᵀ (ma trận đơn vị thêm số 1 ở vị trí (i, j)), nên A′ = EA. Với i ≠ j, E⁻¹ = I − eᵢeⱼᵀ (vì (eᵢeⱼᵀ)² = eᵢ(eⱼᵀeᵢ)eⱼᵀ = 0). Vậy A′⁻¹ = A⁻¹E⁻¹ = B(I − eᵢeⱼᵀ) = B − (Beᵢ)eⱼᵀ. Ma trận (Beᵢ)eⱼᵀ có cột j bằng cột i của B, các cột khác bằng 0. Vậy B′ là B với cột j bị trừ đi cột i. Ví dụ: A = (1 1; 1 0), B = (0 1; 1 −1); cộng hàng 2 vào hàng 1 được A′ = (2 1; 1 0); trừ cột 1 khỏi cột 2 của B được B′ = (0 1; 1 −2); kiểm tra A′B′ = (0 + 1, 2 − 2; 0, 1) = (1 0; 0 1). Ý nghĩa: cập nhật nghịch đảo sau một phép biến đổi hàng chỉ tốn Θ(n) thay vì nghịch đảo lại Θ(n³).
- **D.2-5:** Cho A là ma trận n × n không suy biến có phần tử phức. Chứng minh mọi phần tử của A⁻¹ là số thực khi và chỉ khi mọi phần tử của A là số thực. *Lời giải của người tổng hợp:* ký hiệu X̄ là ma trận lấy liên hợp phức từng phần tử; liên hợp giữ nguyên phép cộng và nhân nên (XY)‾ = X̄Ȳ. Nếu A thực thì Ā = A, và từ AA⁻¹ = I lấy liên hợp được A·(A⁻¹)‾ = I, tương tự (A⁻¹)‾·A = I; theo D.2-1, (A⁻¹)‾ = A⁻¹, tức A⁻¹ thực. Chiều ngược lại áp dụng chiều thuận cho A⁻¹, với (A⁻¹)⁻¹ = A. (Cách khác: A⁻¹ = (ma trận phần bù đại số)ᵀ/det(A), mọi số trong đó đều thực khi A thực.)
- **D.2-6:** Chứng minh nếu A là ma trận n × n không suy biến và đối xứng thì A⁻¹ đối xứng. Chứng minh nếu B là ma trận m × n bất kỳ thì ma trận m × m BABᵀ đối xứng. *Lời giải của người tổng hợp:* (A⁻¹)ᵀ = (Aᵀ)⁻¹ = A⁻¹. Với câu hai (ngầm giả thiết A đối xứng như câu một): (BABᵀ)ᵀ = (Bᵀ)ᵀAᵀBᵀ = BABᵀ, dùng (XYZ)ᵀ = ZᵀYᵀXᵀ. Nếu A không đối xứng thì kết luận sai, ví dụ B = I₂ và A = (0 1; 0 0). Ví dụ đúng: B = (1 2), A = I₂ cho BABᵀ = (5), ma trận 1 × 1 luôn đối xứng; B = (1 0; 1 1), A = (2 1; 1 2): BABᵀ = (2 3; 3 6).
- **D.2-7:** Chứng minh Định lý D.2: A có hạng cột đầy đủ khi và chỉ khi Ax = 0 kéo theo x = 0. (Gợi ý: biểu diễn sự phụ thuộc tuyến tính của một cột vào các cột khác dưới dạng phương trình ma trận–vectơ.) *Lời giải của người tổng hợp:* gọi a₁, …, aₙ là các cột của A. Theo (D.2), Ax = x₁a₁ + … + xₙaₙ. "Có x ≠ 0 với Ax = 0" đúng nghĩa là có hệ số x₁, …, xₙ không đồng thời bằng 0 với Σ xⱼaⱼ = 0, tức các cột phụ thuộc tuyến tính, tức hạng cột nhỏ hơn n. Phủ định hai vế: hạng cột bằng n ⇔ Ax = 0 chỉ có nghiệm x = 0.
- **D.2-8:** Chứng minh với mọi hai ma trận tương thích A và B, rank(AB) ≤ min(rank(A), rank(B)), và đẳng thức xảy ra nếu A hoặc B là ma trận vuông không suy biến. (Gợi ý: dùng định nghĩa thay thế của hạng.) *Lời giải của người tổng hợp:* nếu A = B₁C₁ với cỡ trong rank(A) thì AB = B₁(C₁B), một phân tích qua cỡ trong rank(A), nên rank(AB) ≤ rank(A). Nếu B = B₂C₂ với cỡ trong rank(B) thì AB = (AB₂)C₂, nên rank(AB) ≤ rank(B). (Nếu AB = 0 thì hạng 0, bất đẳng thức hiển nhiên.) Đẳng thức: nếu A vuông n × n không suy biến thì B = A⁻¹(AB), áp dụng phần vừa chứng minh được rank(B) ≤ rank(AB); kết hợp được rank(AB) = rank(B), và rank(B) ≤ n = rank(A) nên bằng min. Tương tự khi B không suy biến. Ví dụ: A = (1 0; 0 0), B = (0 0; 0 1), cả hai hạng 1 nhưng AB = 0 hạng 0 — bất đẳng thức có thể chặt.

### Problem D-1: Ma trận Vandermonde (Vandermonde matrix)

Cho các số x₀, x₁, …, xₙ₋₁, chứng minh định thức của **ma trận Vandermonde**

```text
                       ⎛ 1   x₀     x₀²    ⋯   x₀ⁿ⁻¹   ⎞
V(x₀, x₁, …, xₙ₋₁) =   ⎜ 1   x₁     x₁²    ⋯   x₁ⁿ⁻¹   ⎟
                       ⎜ ⋮   ⋮      ⋮      ⋱   ⋮       ⎟
                       ⎝ 1   xₙ₋₁   xₙ₋₁²  ⋯   xₙ₋₁ⁿ⁻¹ ⎠
```

là

```text
det(V(x₀, x₁, …, xₙ₋₁)) = Π_{0 ≤ j < k ≤ n−1} (xₖ − xⱼ)
```

(Gợi ý: nhân cột i với −x₀ rồi cộng vào cột i + 1, với i = n − 1, n − 2, …, 1, sau đó dùng quy nạp.)

*Lời giải của người tổng hợp.* Đánh số cột từ 1 tới n, cột i chứa các luỹ thừa bậc i − 1. Quy nạp theo n; n = 1 thì V = (1), định thức 1 bằng tích rỗng.

1. Với i = n − 1, n − 2, …, 1 (đi từ phải sang trái để cột i còn nguyên giá trị gốc khi được dùng), thay cột i + 1 bằng cột i + 1 trừ x₀ lần cột i. Theo Định lý D.4 (nhân một cột với hằng số rồi cộng vào cột khác — hệ quả của tính chất 2 và 3), định thức không đổi.
2. Sau bước 1, phần tử ở hàng k, cột i + 1 là xₖⁱ − x₀xₖⁱ⁻¹ = xₖⁱ⁻¹(xₖ − x₀). Hàng 0 trở thành (1, 0, 0, …, 0) vì x₀ⁱ − x₀·x₀ⁱ⁻¹ = 0.
3. Khai triển theo hàng 0 (hàng thứ nhất): chỉ còn số hạng j = 1, định thức bằng định thức của ma trận (n − 1) × (n − 1) có hàng k (k = 1, …, n − 1) là (xₖ − x₀)·(1, xₖ, xₖ², …, xₖⁿ⁻²).
4. Rút thừa số (xₖ − x₀) ra khỏi từng hàng (tính chất 2 của Định lý D.4): định thức bằng Πₖ₌₁ⁿ⁻¹ (xₖ − x₀) · det V(x₁, …, xₙ₋₁).
5. Theo giả thiết quy nạp, det V(x₁, …, xₙ₋₁) = Π_{1≤j<k≤n−1} (xₖ − xⱼ). Nhân với các thừa số j = 0 ở bước 4 ra đúng Π_{0≤j<k≤n−1} (xₖ − xⱼ). ∎

Ví dụ chạy tay với x = (1, 2, 3):

```text
V = (1 1 1; 1 2 4; 1 3 9)
i = 2: cột 3 ← cột 3 − 1·cột 2 = (1−1, 4−2, 9−3) = (0, 2, 6)
i = 1: cột 2 ← cột 2 − 1·cột 1 = (0, 1, 2)
được (1 0 0; 1 1 2; 1 2 6); khai triển hàng 1: det(1 2; 2 6) = 6 − 4 = 2
công thức: (2 − 1)(3 − 1)(3 − 2) = 1·2·1 = 2   ✓
```

Ví dụ thêm (kiểm bằng khai triển trực tiếp): x = (2, 3, 5, −1) cho det = (3−2)(5−2)(−1−2)(5−3)(−1−3)(−1−5) = 1·3·(−3)·2·(−4)·(−6) = −432. Hệ quả: V không suy biến khi và chỉ khi các xₖ đôi một khác nhau (Định lý D.5) — đây là lý do n cặp điểm–giá trị với các điểm phân biệt xác định duy nhất một đa thức bậc nhỏ hơn n (Định lý 30.1).

### Problem D-2: Hoán vị định nghĩa bởi phép nhân ma trận–vectơ trên GF(2) (Permutations defined by matrix-vector multiplication over GF(2))

Một lớp hoán vị của các số nguyên trong tập Sₙ = {0, 1, 2, …, 2ⁿ − 1} được định nghĩa bằng phép nhân ma trận trên GF(2). Với mỗi số nguyên x trong Sₙ, ta xem biểu diễn nhị phân của nó là một vectơ n bit (x₀, x₁, x₂, …, xₙ₋₁)ᵀ, với x = Σᵢ₌₀ⁿ⁻¹ xᵢ2ⁱ (x₀ là bit thấp nhất, đứng **đầu** vectơ). Nếu A là ma trận n × n mà mọi phần tử bằng 0 hoặc 1, ta có thể định nghĩa một ánh xạ biến mỗi giá trị x trong Sₙ thành số có biểu diễn nhị phân là tích ma trận–vectơ Ax. Mọi phép tính ở đây làm trên **GF(2)**: mọi giá trị là 0 hoặc 1, và các quy tắc cộng, nhân thông thường được áp dụng, với một ngoại lệ: 1 + 1 = 0. Có thể nghĩ số học trên GF(2) giống hệt số học số nguyên, chỉ khác là chỉ giữ bit thấp nhất.

Ví dụ, với S₂ = {0, 1, 2, 3}, ma trận A = (1 0; 1 1) định nghĩa hoán vị π_A: π_A(0) = 0, π_A(1) = 3, π_A(2) = 2, π_A(3) = 1. Để thấy vì sao π_A(3) = 1, trên GF(2):

```text
π_A(3) = ⎛ 1  0 ⎞ ⎛ 1 ⎞ = ⎛ 1·1 + 0·1 ⎞ = ⎛ 1 ⎞
         ⎝ 1  1 ⎠ ⎝ 1 ⎠   ⎝ 1·1 + 1·1 ⎠   ⎝ 0 ⎠
```

là biểu diễn nhị phân của 1. Kiểm tra cả bốn giá trị (người tổng hợp): x = 1 là vectơ (1, 0)ᵀ, Ax = (1, 1)ᵀ, tức 1 + 2 = 3; x = 2 là (0, 1)ᵀ, Ax = (0, 1)ᵀ, tức 2; x = 0 cho 0. Bằng lời: bit mới thấp là x₀, bit mới cao là x₀ XOR x₁.

Phần còn lại của bài toán làm việc trên GF(2), mọi phần tử ma trận và vectơ là 0 hoặc 1. **Hạng** của ma trận 0-1 trên GF(2) được định nghĩa như với ma trận thường, nhưng mọi phép tính xác định độc lập tuyến tính thực hiện trên GF(2). **Ảnh** (range) của ma trận 0-1 A cỡ n × n là

```text
R(A) = { y : y = Ax với x nào đó thuộc Sₙ }
```

tức R(A) là tập các số trong Sₙ mà ta có thể tạo ra bằng cách nhân mỗi x trong Sₙ với A.

- **(a)** Nếu r là hạng của A, chứng minh |R(A)| = 2ʳ. Kết luận A định nghĩa một hoán vị trên Sₙ chỉ khi A có hạng đầy đủ.
  *Lời giải của người tổng hợp:* Ax = Σ xⱼaⱼ là tổng (XOR) của một tập con các cột aⱼ, nên R(A) là tập mọi tổ hợp tuyến tính của các cột trên GF(2). Chọn r cột độc lập b₁, …, bᵣ; mọi cột khác là tổ hợp của chúng (nếu không thì có tập độc lập lớn hơn), nên R(A) = {c₁b₁ + … + cᵣbᵣ : cᵢ ∈ {0, 1}}. Có 2ʳ bộ (c₁, …, cᵣ), và hai bộ khác nhau cho hai vectơ khác nhau (nếu bằng nhau thì hiệu — trên GF(2) cũng là tổng — là một tổ hợp không tầm thường bằng 0, trái với độc lập). Vậy |R(A)| = 2ʳ. Hoán vị cần |R(A)| = 2ⁿ, tức r = n. (Và ngược lại, r = n thì ánh xạ là toàn ánh từ tập 2ⁿ phần tử vào chính nó, nên là song ánh.) Ví dụ: A = (1 1; 1 1) có hạng 1, π: 0 → 0, 1 → 3, 2 → 3, 3 → 0; R(A) = {0, 3}, đúng 2¹ phần tử.

  Với ma trận A cỡ n × n và một giá trị y ∈ R(A), **nghịch ảnh** (preimage) của y là

  ```text
  P(A, y) = { x : Ax = y }
  ```

  tức tập các giá trị trong Sₙ được ánh xạ thành y khi nhân với A.

- **(b)** Nếu r là hạng của A và y ∈ R(A), chứng minh |P(A, y)| = 2ⁿ⁻ʳ.
  *Lời giải của người tổng hợp:* ánh xạ x ↦ Ax là tuyến tính: A(x + x′) = Ax + Ax′. Lấy một x* với Ax* = y; khi đó Ax = y ⇔ A(x + x*) = 0 (vì y + y = 0). Vậy P(A, y) = {x* + z : Az = 0} có cùng số phần tử với P(A, 0). Mọi y ∈ R(A) có cùng số nghịch ảnh, 2ⁿ phần tử của Sₙ chia đều cho 2ʳ giá trị của R(A), nên mỗi giá trị có 2ⁿ/2ʳ = 2ⁿ⁻ʳ nghịch ảnh. Ví dụ A = (1 1; 1 1): P(A, 0) = {0, 3}, P(A, 3) = {1, 2}, mỗi tập 2²⁻¹ = 2 phần tử.

  Cho 0 ≤ m ≤ n, và chia tập Sₙ thành các **khối** gồm các số liên tiếp, khối thứ i gồm 2ᵐ số i2ᵐ, i2ᵐ + 1, i2ᵐ + 2, …, (i + 1)2ᵐ − 1. Với mọi tập con S ⊆ Sₙ, định nghĩa B(S, m) là tập các khối cỡ 2ᵐ của Sₙ chứa ít nhất một phần tử của S. Ví dụ, khi n = 3, m = 1 và S = {1, 4, 5}, thì B(S, m) gồm khối 0 (vì 1 nằm trong khối 0 = {0, 1}) và khối 2 (vì cả 4 và 5 nằm trong khối 2 = {4, 5}).

- **(c)** Gọi r là hạng của ma trận con dưới-trái cỡ (n − m) × m của A, tức ma trận tạo bởi giao của n − m hàng dưới cùng và m cột bên trái nhất của A. Gọi S là một khối cỡ 2ᵐ bất kỳ của Sₙ, và S′ = {y : y = Ax với x nào đó thuộc S}. Chứng minh |B(S′, m)| = 2ʳ và với mỗi khối trong B(S′, m), có đúng 2ᵐ⁻ʳ số trong S được ánh xạ vào khối đó.
  *Lời giải của người tổng hợp:* tách vectơ bit x thành z (m bit thấp x₀..xₘ₋₁) và w (n − m bit cao). Hai số cùng một khối khi và chỉ khi có cùng w; trong một khối S, w cố định và z chạy qua cả 2ᵐ giá trị. Chia A thành bốn khối con theo hàng/cột: A = (A₁₁ A₁₂; A₂₁ A₂₂), với A₂₁ là khối dưới-trái (n − m) × m. Phần bit cao của y = Ax — thứ quyết định y rơi vào khối nào — là A₂₁z + A₂₂w. Với w cố định, A₂₂w là một hằng vectơ c. Áp dụng lập luận của (a) và (b) cho ánh xạ tuyến tính z ↦ A₂₁z (ma trận chữ nhật, cùng lập luận): nó nhận đúng 2ʳ giá trị, mỗi giá trị đúng 2ᵐ⁻ʳ lần; cộng thêm hằng c chỉ dịch các giá trị đi một cách song ánh. Vậy ảnh của khối S rơi vào đúng 2ʳ khối, mỗi khối nhận đúng 2ᵐ⁻ʳ số của S. Ví dụ n = 2, m = 1, A = (1 0; 1 1): khối dưới-trái là (a₂₁) = (1), r = 1; khối S = {0, 1} được ánh xạ thành {0, 3}, nằm ở khối 0 = {0, 1} và khối 1 = {2, 3}: 2¹ = 2 khối, mỗi khối nhận 2⁰ = 1 số. Với A = I₂ thì r = 0: {0, 1} ánh xạ vào chính nó, 1 khối nhận 2 số.

  Vì nhân vectơ 0 với bất kỳ ma trận nào cũng ra vectơ 0, tập các hoán vị của Sₙ định nghĩa bằng cách nhân với ma trận 0-1 n × n hạng đầy đủ trên GF(2) không thể gồm mọi hoán vị của Sₙ (mọi hoán vị như vậy đều giữ nguyên 0). Ta mở rộng lớp hoán vị bằng cách thêm một số hạng cộng: x ∈ Sₙ được ánh xạ thành Ax + c, với c là vectơ n bit và phép cộng làm trên GF(2). Ví dụ, khi A = (1 0; 1 1) và c = (0, 1)ᵀ, ta được hoán vị π_{A,c}: π_{A,c}(0) = 2, π_{A,c}(1) = 1, π_{A,c}(2) = 0, π_{A,c}(3) = 3. (Kiểm tra của người tổng hợp: c = (0, 1)ᵀ là số 2, phép cộng vectơ trên GF(2) là XOR, nên π_{A,c}(x) = π_A(x) XOR 2: 0 XOR 2 = 2, 3 XOR 2 = 1, 2 XOR 2 = 0, 1 XOR 2 = 3. Đúng.) Mọi hoán vị biến x ∈ Sₙ thành Ax + c, với A là ma trận 0-1 n × n hạng đầy đủ và c là vectơ n bit nào đó, được gọi là một **hoán vị tuyến tính** (linear permutation).

- **(d)** Dùng một lập luận đếm để chứng minh số hoán vị tuyến tính của Sₙ nhỏ hơn rất nhiều so với số hoán vị của Sₙ.
  *Lời giải của người tổng hợp:* số cặp (A, c) không quá 2^(n²) · 2ⁿ = 2^(n² + n), trong khi số hoán vị của Sₙ là (2ⁿ)!. Vì (2ⁿ)! ≥ (2ⁿ/e)^(2ⁿ), ta có lg((2ⁿ)!) ≥ 2ⁿ(n − lg e), tăng theo hàm mũ của n, còn lg của số hoán vị tuyến tính chỉ là n² + n, đa thức. Đếm chính xác: hai cặp (A, c) khác nhau cho hai hoán vị khác nhau (vì c = π(0) và cột i của A bằng π(2ⁱ) XOR c), nên số hoán vị tuyến tính đúng bằng số ma trận khả nghịch trên GF(2) nhân 2ⁿ, tức (2ⁿ − 1)(2ⁿ − 2)(2ⁿ − 4)⋯(2ⁿ − 2ⁿ⁻¹) · 2ⁿ (công thức theo hiểu biết của người tổng hợp; mỗi cột phải nằm ngoài không gian sinh bởi các cột trước).

  | n | số hoán vị tuyến tính | (2ⁿ)! | tỷ lệ |
  |---|---|---|---|
  | 2 | 6 · 4 = 24 | 24 | 100% |
  | 3 | 168 · 8 = 1.344 | 40.320 | khoảng 3,3% |
  | 4 | 20.160 · 16 = 322.560 | khoảng 2,09 · 10¹³ | khoảng 1,5 · 10⁻⁸ |

- **(e)** Cho ví dụ một giá trị n và một hoán vị của Sₙ không thể đạt được bằng bất kỳ hoán vị tuyến tính nào. (Gợi ý: với một hoán vị cho trước, nghĩ xem phép nhân ma trận với vectơ đơn vị liên quan thế nào tới các cột của ma trận.)
  *Lời giải của người tổng hợp:* Aeᵢ là cột thứ i của A, nên với hoán vị tuyến tính π, π(0) = c và π(2ⁱ) = aᵢ + c. Như vậy n + 1 giá trị π(0), π(1), π(2), π(4), …, π(2ⁿ⁻¹) quyết định toàn bộ π; hơn nữa π(x XOR y) = π(x) XOR π(y) XOR π(0). Như đã đếm ở (d), với n = 2 cả 24 hoán vị đều tuyến tính, nên phải lấy n ≥ 3. Lấy n = 3 và hoán vị π chỉ đổi chỗ 3 và 5, giữ nguyên mọi số khác. Nếu π tuyến tính thì c = π(0) = 0, các cột A là π(1) = 1, π(2) = 2, π(4) = 4, tức A = I và π phải là hoán vị đồng nhất; nhưng π(3) = 5 ≠ 3. Mâu thuẫn. (Kiểm tra bằng đẳng thức: π(3) phải bằng π(1) XOR π(2) XOR π(0) = 1 XOR 2 XOR 0 = 3.)

### Ghi chú phụ lục (Appendix notes, trang 1229)

- Sách giáo khoa đại số tuyến tính cung cấp rất nhiều kiến thức nền về ma trận.
- Các cuốn sách của **Strang** (tài liệu [323] và [324] trong thư mục của CLRS) đặc biệt tốt. Theo thư mục tài liệu tham khảo của sách (trang 1248), đó là Gilbert Strang, *Introduction to Applied Mathematics* (Wellesley-Cambridge Press, 1986) và Gilbert Strang, *Linear Algebra and Its Applications* (Thomson Brooks/Cole, ấn bản thứ tư, 2006).

## Luận điểm cốt lõi

### Mệnh đề

Để đọc các chương về ma trận, đường đi ngắn nhất, quy hoạch tuyến tính và FFT, người đọc cần một bộ định nghĩa thống nhất về ma trận và các phép toán trên nó; bộ định nghĩa ấy xoay quanh một chuỗi tương đương trung tâm: với ma trận vuông, **có nghịch đảo ⇔ hạng đầy đủ ⇔ không có vectơ không ⇔ định thức khác 0**, và với ma trận chữ nhật, **hạng cột đầy đủ ⇔ không có vectơ không ⇒ AᵀA xác định dương**.

### Giả định

- Phần tử của ma trận lấy từ một hệ số có phép cộng và nhân (số thực, số phức, số nguyên modulo số nguyên tố, GF(2)); các khái niệm hạng, nghịch đảo, định thức hoạt động như nhau trên mọi hệ số loại này (Bài toán D-2 dùng GF(2)).
- Vectơ mặc định là vectơ cột; mọi tích có mặt trong biểu thức được ngầm hiểu là tương thích.
- Các tính chất nền tảng — hạng hàng bằng hạng cột, Định lý D.1, D.4, D.5 — được phát biểu không chứng minh; người đọc được giả định đã học hoặc chấp nhận chúng từ sách đại số tuyến tính.
- Chi phí tính toán: phép nhân ma trận n × n theo (D.2) tính bằng số phép nhân, cộng số học, mỗi phép tốn thời gian hằng số (mô hình RAM).

### Cơ chế

1. Định nghĩa đối tượng: ma trận A = (aᵢⱼ), chuyển vị, vectơ cột, các loại ma trận vuông đặc biệt nhận dạng bằng vị trí số 0 bắt buộc.
2. Định nghĩa phép toán: cộng từng phần tử, nhân vô hướng, nhân ma trận cᵢⱼ = Σₖ aᵢₖbₖⱼ; ghi lại luật nào giữ được (kết hợp, phân phối, đơn vị) và luật nào mất (giao hoán).
3. Định nghĩa tính chất: nghịch đảo, độc lập tuyến tính, hạng (hai định nghĩa tương đương), vectơ không, định thức (đệ quy theo hàng 1).
4. Nối các tính chất bằng định lý: D.1 (hạng đầy đủ ⇔ không suy biến), D.2 và D.3 (vectơ không), D.5 (định thức bằng 0 ⇔ suy biến).
5. Chứng minh một kết quả dùng được ngay: Định lý D.6, AᵀA xác định dương khi A có hạng cột đầy đủ, nhờ xᵀAᵀAx = ‖Ax‖².
6. Hai bài toán mở rộng: D-1 tính định thức Vandermonde bằng phép biến đổi cột và quy nạp; D-2 áp dụng hạng, ảnh, nghịch ảnh trên GF(2) cho các hoán vị bit.

### Bằng chứng và ví dụ tác giả đưa ra

- Ma trận (D.1) A = (1 2 3; 4 5 6) và chuyển vị (1 4; 2 5; 3 6); vectơ x = (2, 3, 5)ᵀ và xᵀ = (2 3 5).
- Các mẫu tổng quát của ma trận đường chéo, đơn vị, ba đường chéo, tam giác trên, tam giác dưới; ma trận hoán vị 5 × 5 cụ thể; ma trận đối xứng (1 2 3; 2 6 4; 3 4 5).
- Số phép toán của SQUARE-MATRIX-MULTIPLY: n³ phép nhân, n²(n − 1) phép cộng, Θ(n³).
- Ví dụ không giao hoán: A = (0 1; 0 0), B = (0 0; 1 0), AB = (1 0; 0 0), BA = (0 0; 0 1).
- Nghịch đảo (1 1; 1 0)⁻¹ = (0 1; 1 −1); ma trận khác không suy biến (1 0; 1 0).
- Ba vectơ phụ thuộc tuyến tính (1 2 3), (2 6 4), (4 11 9) với 2x₁ + 3x₂ − 2x₃ = 0.
- Ma trận đơn vị xác định dương vì xᵀx = Σ xᵢ² > 0; chứng minh đầy đủ của Định lý D.6.
- Bài toán D-2: π_A với A = (1 0; 1 1) cho 0 → 0, 1 → 3, 2 → 2, 3 → 1; π_{A,c} với c = (0, 1)ᵀ cho 0 → 2, 1 → 1, 2 → 0, 3 → 3; ví dụ khối n = 3, m = 1, S = {1, 4, 5}.

### Kết luận và hàm ý cho người lập trình

- Luôn kiểm tra cỡ khi nhân: A (m × n) nhân B (n × p) cho m × p; lỗi lệch cỡ là lỗi phổ biến nhất khi cài đặt.
- Không bao giờ giả định AB = BA; khi đảo ngược hay chuyển vị một tích, đảo thứ tự: (AB)ᵀ = BᵀAᵀ, (BA)⁻¹ = A⁻¹B⁻¹.
- Để kiểm tra một ma trận vuông có khả nghịch không, đừng tính định thức theo định nghĩa đệ quy (Θ(n!)); hãy khử Gauss/phân rã LU (Θ(n³)) và xem có trụ bằng 0 không — Định lý D.4 bảo đảm hai cách cho cùng câu trả lời. Theo hiểu biết của người tổng hợp, trên số thực dấu phẩy động, "định thức bằng 0 đúng" gần như không bao giờ xảy ra; người ta đo mức gần suy biến bằng số điều kiện, không bằng định thức.
- Ma trận hoán vị không cần lưu thành ma trận n × n: một mảng π[1..n] là đủ, và nghịch đảo là chuyển vị (Exercise D.2-3) — đúng cách Chương 28 lưu P trong LUP.
- Khi cần giải hệ có ma trận AᵀA (bình phương tối thiểu), hạng cột đầy đủ của A là điều kiện để hệ có nghiệm duy nhất (Định lý D.6).
- Trên GF(2), phép cộng là XOR và phép nhân là AND: một vectơ n bit vừa với một từ máy, và phép nhân ma trận–vectơ là n phép AND rồi đếm bit lẻ chẵn; các hoán vị bit tuyến tính (Bài toán D-2) chỉ là một phần rất nhỏ trong mọi hoán vị nhưng tính được rất rẻ.

### Trong ngôn ngữ khoa học máy tính

A ∈ ℝ^(m×n), (AB)ᵢⱼ = Σₖ₌₁ⁿ aᵢₖbₖⱼ, chi phí nhân trực tiếp Θ(mnp) (Θ(n³) với ma trận vuông). Tính chất: kết hợp, phân phối, IₘA = AIₙ = A, không giao hoán với n > 1; (AB)ᵀ = BᵀAᵀ; (BA)⁻¹ = A⁻¹B⁻¹; (A⁻¹)ᵀ = (Aᵀ)⁻¹. rank(A) = hạng cột = hạng hàng = min{r : A = BC, B ∈ ℝ^(m×r), C ∈ ℝ^(r×n)} ≤ min(m, n); rank(AB) ≤ min(rank A, rank B). Với A vuông n × n: A khả nghịch ⇔ rank(A) = n ⇔ ker(A) = {0} ⇔ det(A) ≠ 0. det(A) = Σⱼ (−1)^(1+j) a₁ⱼ det(A[1j]); det(AB) = det(A)det(B); det(Aᵀ) = det(A). A xác định dương ⇔ xᵀAx > 0 ∀x ≠ 0; rank(A) = n (hạng cột đầy đủ) ⇒ AᵀA xác định dương. det V(x₀, …, xₙ₋₁) = Π_{j<k} (xₖ − xⱼ). Trên GF(2): |R(A)| = 2^rank(A), |P(A, y)| = 2^(n − rank(A)); số hoán vị affine x ↦ Ax + c bằng |GL(n, 2)| · 2ⁿ ≤ 2^(n² + n) ≪ (2ⁿ)!.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| matrix | ma trận | bảng số hình chữ nhật A = (aᵢⱼ) |
| m × n matrix | ma trận m × n | m hàng, n cột |
| element / entry | phần tử | số aᵢⱼ ở hàng i, cột j |
| ℝ^(m×n), S^(m×n) | tập ma trận m × n | phần tử thực / phần tử thuộc S |
| transpose Aᵀ | chuyển vị | đổi hàng thành cột |
| vector, n-vector | vectơ, n-vectơ | mảng số một chiều độ dài n |
| column vector / row vector | vectơ cột / vectơ hàng | ma trận n × 1 / 1 × n; dạng chuẩn là cột |
| unit vector eᵢ | vectơ đơn vị | 1 ở vị trí i, 0 ở mọi chỗ khác |
| zero matrix | ma trận không | mọi phần tử bằng 0 |
| square matrix | ma trận vuông | số hàng bằng số cột |
| diagonal matrix, diag(…) | ma trận đường chéo | khác 0 chỉ trên đường chéo chính |
| identity matrix Iₙ | ma trận đơn vị | ma trận đường chéo toàn 1 |
| tridiagonal matrix | ma trận ba đường chéo | tᵢⱼ = 0 khi \|i − j\| > 1 |
| upper-triangular / unit upper-triangular | tam giác trên / tam giác trên đơn vị | 0 dưới đường chéo / thêm đường chéo toàn 1 |
| lower-triangular / unit lower-triangular | tam giác dưới / tam giác dưới đơn vị | 0 trên đường chéo / thêm đường chéo toàn 1 |
| permutation matrix | ma trận hoán vị | đúng một số 1 trên mỗi hàng và mỗi cột |
| symmetric matrix | ma trận đối xứng | A = Aᵀ |
| matrix addition / subtraction | cộng / trừ ma trận | theo từng phần tử |
| componentwise | theo từng thành phần | áp dụng riêng cho từng vị trí (i, j) |
| scalar multiple | bội vô hướng | λA = (λaᵢⱼ) |
| negative of a matrix | ma trận đối | −A = (−1)·A |
| matrix multiplication / product | nhân ma trận / tích ma trận | cᵢⱼ = Σₖ aᵢₖbₖⱼ (D.2) |
| compatible matrices | ma trận tương thích | số cột của A bằng số hàng của B |
| associative / distributive / commutative | kết hợp / phân phối / giao hoán | nhân ma trận có hai tính đầu, không có tính thứ ba |
| matrix-vector product | tích ma trận–vectơ | Ax, với x coi như ma trận n × 1 |
| inner product | tích trong | xᵀy = Σ xᵢyᵢ, một số |
| outer product | tích ngoài | xyᵀ, ma trận n × n có phần tử xᵢyⱼ |
| (euclidean) norm ‖x‖ | chuẩn (Euclid) | (xᵀx)^(1/2), độ dài của x |
| inverse A⁻¹ | nghịch đảo | AA⁻¹ = I = A⁻¹A |
| invertible / nonsingular | khả nghịch / không suy biến | có nghịch đảo |
| noninvertible / singular | không khả nghịch / suy biến | không có nghịch đảo |
| linearly dependent / independent | phụ thuộc / độc lập tuyến tính | có / không có tổ hợp không tầm thường bằng 0 |
| column rank / row rank / rank | hạng cột / hạng hàng / hạng | số cột / hàng độc lập nhiều nhất; hai số bằng nhau |
| full rank | hạng đầy đủ | ma trận vuông n × n có hạng n |
| full column rank | hạng cột đầy đủ | ma trận m × n có hạng n |
| null vector | vectơ không | x ≠ 0 với Ax = 0 |
| minor A[ij] | ma trận con | bỏ hàng i, cột j |
| determinant det(A) | định thức | định nghĩa đệ quy bằng khai triển theo hàng 1 |
| cofactor | phần bù đại số | (−1)^(i+j) det(A[ij]) |
| positive-definite matrix | ma trận xác định dương | xᵀAx > 0 với mọi x ≠ 0 |
| Vandermonde matrix | ma trận Vandermonde | hàng k là (1, xₖ, xₖ², …, xₖⁿ⁻¹) |
| GF(2) | trường GF(2) | số học trên {0, 1} với 1 + 1 = 0 |
| 0-1 matrix | ma trận 0-1 | mọi phần tử bằng 0 hoặc 1 |
| range R(A) | ảnh | tập mọi giá trị Ax |
| preimage P(A, y) | nghịch ảnh | tập mọi x với Ax = y |
| block (of size 2ᵐ) | khối (cỡ 2ᵐ) | 2ᵐ số liên tiếp i2ᵐ, …, (i + 1)2ᵐ − 1 |
| submatrix | ma trận con (khối) | giao của một số hàng và một số cột |
| linear permutation | hoán vị tuyến tính | x ↦ Ax + c trên GF(2), A hạng đầy đủ |

## Câu nói đáng nhớ

> "Matrices arise in numerous applications, including, but by no means limited to, scientific computing." — mở đầu Phụ lục D
>
> *Dịch: Ma trận xuất hiện trong rất nhiều ứng dụng, bao gồm — nhưng không hề giới hạn ở — tính toán khoa học.*

> "Matrices have many (but not all) of the algebraic properties typical of numbers." — Mục D.1
>
> *Dịch: Ma trận có nhiều (nhưng không phải tất cả) tính chất đại số đặc trưng của các con số.*

> "For n > 1, multiplication of n × n matrices is not commutative." — Mục D.1
>
> *Dịch: Với n > 1, phép nhân các ma trận n × n không có tính giao hoán.*

> "A fundamental property of any matrix A is that its row rank always equals its column rank, so that we can simply refer to the rank of A." — Mục D.2
>
> *Dịch: Một tính chất nền tảng của mọi ma trận A là hạng hàng của nó luôn bằng hạng cột, nên ta có thể gọi đơn giản là hạng của A.*

> "Matrices that arise in applications are often positive-definite due to the following theorem." — Mục D.2, trước Định lý D.6
>
> *Dịch: Các ma trận xuất hiện trong ứng dụng thường xác định dương, nhờ định lý sau.*

> "You can think of arithmetic over GF(2) as being just like regular integer arithmetic, except that you use only the least significant bit." — Bài toán D-2
>
> *Dịch: Có thể nghĩ số học trên GF(2) giống hệt số học số nguyên thông thường, chỉ khác là chỉ dùng bit thấp nhất.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: gọn và đúng những gì các chương sau cần

Mười ba trang của phụ lục không cố dạy đại số tuyến tính; chúng chọn đúng các khái niệm mà Chương 28 (LUP, nghịch đảo, bình phương tối thiểu), Chương 29 (dạng ma trận của quy hoạch tuyến tính) và Chương 30 (ma trận Vandermonde, ma trận DFT) cần, và đặt tên thống nhất cho chúng. Bảy loại ma trận vuông đặc biệt được liệt kê đúng là những loại xuất hiện về sau: tam giác dưới đơn vị, tam giác trên và hoán vị trong PA = LU; ba đường chéo trong Problem 28-1; đối xứng xác định dương ở Mục 28.3. Chuỗi Định lý D.1–D.3 và D.5 là chuỗi tương đương mà mọi lập luận "hệ có nghiệm duy nhất" của Chương 28 dùng tới.

### Điểm mạnh: định nghĩa hạng thứ hai và chứng minh Định lý D.6

Định nghĩa "hạng là r nhỏ nhất để A = BC" ít gặp trong giáo trình nhập môn nhưng rất hợp với khoa học máy tính: nó nói thẳng hạng là "cỡ nhỏ nhất để nén ma trận thành tích hai ma trận mảnh", và nó làm Exercise D.2-8 (hạng của tích) chỉ còn một dòng. Theo hiểu biết của người tổng hợp, chính góc nhìn này là nền của các kỹ thuật xấp xỉ hạng thấp hiện đại (nén mô hình, hệ gợi ý dựa trên phân rã ma trận). Chứng minh Định lý D.6 cũng là ví dụ mẫu cho cách viết lại xᵀAᵀAx thành ‖Ax‖² — một mẹo dùng lại nhiều lần.

### Điểm yếu và chỗ đơn giản hoá

- **Nhiều định lý không chứng minh:** hạng hàng bằng hạng cột, Định lý D.1, D.4, D.5 đều chỉ được phát biểu. Hợp lý với một phụ lục tra cứu, nhưng người chưa học đại số tuyến tính sẽ phải tin.
- **Định nghĩa định thức chỉ bằng khai triển theo hàng 1** — dễ viết, nhưng nếu ai cài đặt nguyên văn sẽ được thuật toán Θ(n!) (truy hồi T(n) = nT(n − 1) + Θ(n)). Phụ lục không nhắc rằng thực tế tính định thức qua phân rã LU trong Θ(n³); điều này chỉ suy ra được gián tiếp từ Định lý D.4 và Exercise D.2-2.
- **Không có trị riêng, vectơ riêng, không gian vectơ, cơ sở, phép chiếu.** Sách không cần chúng trong các chương chính, nhưng người đọc làm tiếp về đồ thị (ma trận kề, phổ), xác suất (xích Markov) sẽ phải tìm ở sách khác.
- **Định nghĩa xác định dương không đòi đối xứng** (xem khối Lưu ý), lệch với cách dùng phổ biến; Chương 28 bù lại bằng cách luôn nói "đối xứng xác định dương".
- **Vài chỗ diễn đạt lỏng:** "mỗi hàng hoặc cột" ở định nghĩa ma trận hoán vị; Exercise D.2-6 câu hai thiếu giả thiết A đối xứng; số phép cộng n²(n − 1) không khớp từng dòng với pseudocode của Mục 4.2.

### So với cách làm thực tế

Theo hiểu biết của người tổng hợp: phần mềm số không bao giờ tính A⁻¹ để giải Ax = b, mà dùng phân rã LU/QR/Cholesky (Chương 28 nói điều này); không dùng định thức để kiểm tra suy biến, mà dùng số điều kiện hoặc giá trị kỳ dị nhỏ nhất, vì trên số dấu phẩy động định thức có thể cực nhỏ với ma trận hoàn toàn bình thường (ví dụ 0,1·I₁₀₀ có định thức 10⁻¹⁰⁰) và không nhỏ với ma trận gần suy biến. Phép nhân ma trận thực tế được cài đặt bằng các thư viện BLAS tối ưu theo bộ nhớ đệm (chia khối), chạy cùng Θ(n³) phép tính như (D.2) nhưng nhanh hơn cài đặt ba vòng lặp ngây thơ hàng chục lần; thuật toán Strassen và các thuật toán tiệm cận nhanh hơn ít khi được dùng vì hằng số lớn và kém ổn định số. Ma trận thưa (đa số phần tử bằng 0, như ma trận ba đường chéo) được lưu riêng các phần tử khác 0.

### Liên hệ các chương khác

- Chương 4 ([C04-chia-de-tri.md](C04-chia-de-tri.md)): SQUARE-MATRIX-MULTIPLY cài đặt (D.2); Strassen dùng tính kết hợp, phân phối (không dùng giao hoán, nên áp dụng đệ quy cho khối ma trận được) để giảm 8 phép nhân khối xuống 7.
- Chương 25 ([C25-duong-di-ngan-nhat-moi-cap-dinh.md](C25-duong-di-ngan-nhat-moi-cap-dinh.md)): "nhân ma trận" với (min, +) thay (+, ·) — cấu trúc (D.2) giữ nguyên, chỉ đổi hệ số; tính kết hợp cho phép bình phương lặp.
- Chương 27 ([C27-thuat-toan-da-luong.md](C27-thuat-toan-da-luong.md)): nhân ma trận đa luồng; nhân ma trận–vectơ song song.
- Chương 28 ([C28-phep-toan-ma-tran.md](C28-phep-toan-ma-tran.md)): người dùng chính — ma trận tam giác, hoán vị, PA = LU, nghịch đảo, (BA)⁻¹ = A⁻¹B⁻¹, Định lý D.6 cho bình phương tối thiểu, tích ngoài trong phần bù Schur.
- Chương 29 ([C29-quy-hoach-tuyen-tinh.md](C29-quy-hoach-tuyen-tinh.md)): quy hoạch tuyến tính dạng chuẩn "cực đại cᵀx với Ax ≤ b, x ≥ 0" viết bằng ký hiệu ma trận, vectơ, chuyển vị của phụ lục.
- Chương 30 ([C30-da-thuc-va-fft.md](C30-da-thuc-va-fft.md)): ma trận Vandermonde và định thức của nó (Bài toán D-1) chứng minh nội suy duy nhất; DFT là phép nhân với ma trận Vandermonde của các căn đơn vị; hoán vị đảo bit của FFT lặp là một hoán vị tuyến tính theo nghĩa Bài toán D-2 (theo nhận xét của người tổng hợp).
- Chương 31 ([C31-thuat-toan-so-hoc.md](C31-thuat-toan-so-hoc.md)): số học modulo số nguyên tố — một "hệ số" mà phụ lục nhắc tới, nơi các định nghĩa nghịch đảo và hạng vẫn đúng.
- Phụ lục A ([PA-tong.md](PA-tong.md)): ký hiệu Σ trong (D.2) và tích trong; Phụ lục C ([PC-dem-va-xac-suat.md](PC-dem-va-xac-suat.md)): (2ⁿ)! và các cận đếm dùng ở Bài toán D-2(d).

### Vận dụng (phỏng vấn, lập trình thi đấu, kỹ thuật phần mềm)

- **Phỏng vấn:** cài đặt nhân hai ma trận (chú ý cỡ, thứ tự vòng lặp i-k-j thân thiện bộ nhớ đệm hơn i-j-k — theo hiểu biết của người tổng hợp); xoay ma trận ảnh 90° (chuyển vị rồi đảo thứ tự cột); nhân ma trận thưa; tính số Fibonacci thứ n trong O(lg n) bằng luỹ thừa ma trận (1 1; 1 0)ⁿ — chính ma trận mà sách dùng làm ví dụ nghịch đảo.
- **Lập trình thi đấu:** luỹ thừa nhanh ma trận cho truy hồi tuyến tính và đếm đường đi độ dài k trong đồ thị (phần tử (i, j) của Aᵏ với A là ma trận kề); khử Gauss modulo số nguyên tố để tính định thức, hạng, nghịch đảo; khử Gauss trên GF(2) bằng bitset cho bài toán XOR (cơ sở tuyến tính của một tập số — "linear basis") — dùng đúng các kết quả |R(A)| = 2ʳ và |P(A, y)| = 2ⁿ⁻ʳ của Bài toán D-2(a)(b) để đếm số tập con có XOR bằng một giá trị cho trước; định thức Vandermonde và nội suy Lagrange.
- **Kỹ thuật phần mềm:** dùng thư viện (NumPy/BLAS/LAPACK, Eigen) thay vì tự viết; không tính nghịch đảo khi chỉ cần giải hệ; lưu ma trận hoán vị bằng mảng; với dữ liệu có cột gần phụ thuộc tuyến tính (đa cộng tuyến), biết rằng AᵀA gần suy biến và cần chính quy hoá. Trong mật mã và mã sửa lỗi, ma trận trên GF(2) là công cụ hằng ngày: mã Hamming và mã kiểm tra chẵn lẻ là các ma trận 0-1, và các lớp trộn bit trong mã khối là các hoán vị tuyến tính hoặc affine theo đúng nghĩa của Bài toán D-2.

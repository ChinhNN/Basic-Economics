# How Should Socially Minded AI Firms Price Their Products? — Doanh nghiệp AI có mục tiêu xã hội nên định giá sản phẩm thế nào?

**Nguồn:** IMF Working Paper.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Nhiều công ty AI hàng đầu tuyên bố theo đuổi mục tiêu xã hội bên cạnh lợi nhuận, nhưng chưa có khung phân tích nào nói họ nên định giá ra sao. Bài xây dựng một Quy tắc Lerner Mở rộng, trong đó biên lợi nhuận tối ưu bằng tỷ số giữa một chỉ số động cơ tổng hợp và độ co giãn của cầu. Kết quả định lượng đáng chú ý: một công ty vị lợi thuần tuý sẽ định giá THẤP hơn công ty tối đa hoá lợi nhuận, và động cơ phân phối lại đóng góp rất ít, chỉ khoảng một xu ở nhóm thu nhập thấp nhất. Kết luận chính sách là chính sách giá của doanh nghiệp không thể thay thế thuế và chuyển nhượng của nhà nước.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Thông tin nguồn lấy từ phần đầu văn bản.

## Sơ đồ

### Từ Quy tắc Lerner cổ điển tới Quy tắc Lerner Mở rộng

```text
       QUY TẮC LERNER CỔ ĐIỂN — doanh nghiệp tối đa hoá LỢI NHUẬN
              P − MC        1
              ────────  =  ───
                 P          ε
       · biên lợi nhuận tỷ lệ NGHỊCH với độ co giãn của cầu
       · cầu càng ít co giãn → định giá càng cao
                                │
                                ▼
       QUY TẮC LERNER MỞ RỘNG — doanh nghiệp có MỤC TIÊU XÃ HỘI
              P − MC        M
              ────────  =  ───
                 P          ε
       trong đó M là CHỈ SỐ ĐỘNG CƠ TỔNG HỢP, M = 1 khi doanh nghiệp
       thuần tuý vị lợi nhuận, và M < 1 khi doanh nghiệp coi trọng
       phúc lợi xã hội
       → cùng một công thức, nhưng TỬ SỐ mang toàn bộ nội dung xã hội
                                │
                                ▼
       M ĐƯỢC TẠO TỪ BỐN ĐỘNG CƠ
       ❶ ĐỘNG CƠ LỢI NHUẬN — trọng số doanh nghiệp đặt lên lợi nhuận
         của chính mình · ĐẨY GIÁ LÊN
       ❷ ĐỘNG CƠ THẶNG DƯ TIÊU DÙNG — coi trọng lợi ích người dùng
         nhận được ngoài phần trả · ĐẨY GIÁ XUỐNG
       ❸ ĐỘNG CƠ PHÂN PHỐI — đặt trọng số CAO HƠN lên phúc lợi của
         người thu nhập thấp · ĐẨY GIÁ XUỐNG, nhưng ĐỘ LỚN NHỎ
       ❹ ĐỘNG CƠ LAO ĐỘNG — tính tới việc sản phẩm làm DỊCH CHUYỂN
         việc làm, gây tổn thất cho người lao động bị thay thế
         · ĐẨY GIÁ LÊN (giá cao làm chậm tốc độ áp dụng)
       ────────────────────────────────────────────────────────────
       ĐIỂM TINH TẾ: động cơ ❷ và ❹ KÉO NGƯỢC CHIỀU NHAU. Quan tâm
       tới người TIÊU DÙNG nói "hạ giá"; quan tâm tới người LAO ĐỘNG
       bị thay thế nói "đừng hạ quá nhanh".
```

### Năm mệnh đề của bài

```text
       MỆNH ĐỀ 1 — tồn tại và dạng của Quy tắc Lerner Mở rộng: với
       hàm cầu chuẩn, giá tối ưu của doanh nghiệp có mục tiêu xã hội
       thoả mãn (P−MC)/P = M/ε với M tổng hợp bốn động cơ
                                │
       MỆNH ĐỀ 2 — doanh nghiệp VỊ LỢI THUẦN TUÝ (chỉ tối đa hoá
       tổng phúc lợi, không đặt trọng số riêng cho lợi nhuận) định
       giá THẤP HƠN doanh nghiệp tối đa hoá lợi nhuận, nhưng vẫn
       CAO HƠN chi phí biên khi có chi phí cố định phải thu hồi
                                │
       MỆNH ĐỀ 3 — động cơ PHÂN PHỐI đóng góp vào M một lượng tỷ lệ
       với HIỆP PHƯƠNG SAI giữa trọng số phúc lợi xã hội và mức tiêu
       dùng sản phẩm · nếu người giàu dùng NHIỀU hơn, động cơ này
       làm giá TĂNG chứ không giảm
                                │
       MỆNH ĐỀ 4 — động cơ LAO ĐỘNG làm giá TĂNG khi sản phẩm thay
       thế lao động, và độ lớn tỷ lệ với tổn thất phúc lợi của người
       bị dịch chuyển cùng tốc độ dịch chuyển
                                │
       MỆNH ĐỀ 5 — chính sách giá là công cụ phân phối lại KÉM HIỆU
       QUẢ so với thuế và chuyển nhượng, vì nó chỉ tác động qua MỘT
       sản phẩm và không nhắm được đúng đối tượng
```

### Kết quả định lượng: ba loại doanh nghiệp

```text
       HIỆU CHUẨN MÔ HÌNH
       · 525 nghề nghiệp ở Hoa Kỳ
       · α = 4% (mức độ tiếp xúc của tác vụ với AI)
       · σ = 3 (độ co giãn thay thế)
       · ψ = 0,5 × mức lương trung bình (chi phí dịch chuyển)
       · μ = λ = 0,5 (trọng số các động cơ)
       ────────────────────────────────────────────────────────────
       ┌──────────────────┬──────────┬──────────────────────────┐
       │ LOẠI DOANH NGHIỆP│ BIÊN GIÁ │ DIỄN GIẢI                │
       ├──────────────────┼──────────┼──────────────────────────┤
       │ TỐI ĐA HOÁ LỢI   │ 32% → 50%│ khi AI mạnh hơn, cầu ít  │
       │ NHUẬN            │          │ co giãn hơn → TĂNG biên  │
       ├──────────────────┼──────────┼──────────────────────────┤
       │ VỊ LỢI THUẦN TUÝ │ 15% → 20%│ định giá THẤP hơn nhiều, │
       │ (utilitarian)    │          │ chỉ đủ bù chi phí cố định│
       ├──────────────────┼──────────┼──────────────────────────┤
       │ ĐA MỤC TIÊU      │ 33% → 15%│ ★ CHIỀU NGƯỢC LẠI: khi   │
       │ (multi-objective)│          │ AI mạnh hơn, mối lo về   │
       │                  │          │ dịch chuyển lao động NHỎ │
       │                  │          │ dần so với lợi ích tiêu  │
       │                  │          │ dùng → GIẢM biên giá     │
       └──────────────────┴──────────┴──────────────────────────┘
       → HÌNH DẠNG QUỸ ĐẠO khác nhau chứ không chỉ MỨC khác nhau
       ────────────────────────────────────────────────────────────
       ĐỘ LỚN CỦA ĐỘNG CƠ PHÂN PHỐI — kết quả then chốt
       · ở nhóm thu nhập THẤP NHẤT: kéo giá xuống ≈ 1 XU
       · ở nhóm thu nhập CAO NHẤT: kéo giá lên ≈ 12 XU
       → động cơ phân phối gần như KHÔNG ĐÁNG KỂ về mặt kinh tế
       ────────────────────────────────────────────────────────────
       SO SÁNH VỚI NHÀ HOẠCH ĐỊNH XÃ HỘI
       · nhà hoạch định có công cụ THUẾ: biên giá tối ưu chỉ 7%,
         và dưới 1% khi có chuyển nhượng nhắm đúng đối tượng
       → KHOẢNG CÁCH giữa 15% và 7% chính là CÁI GIÁ của việc dùng
         giá thay cho chính sách tài khoá
```

## Ba câu hỏi bài viết trả lời

1. Một công ty AI vừa muốn lợi nhuận vừa muốn phục vụ xã hội nên định giá theo nguyên tắc nào?
2. Bốn động cơ xã hội tác động tới giá theo chiều nào và với độ lớn bao nhiêu?
3. Chính sách giá của doanh nghiệp có thể thay thế thuế và chuyển nhượng của nhà nước không?

## Khái niệm cần biết

**Chi phí biên (marginal cost).** Chi phí phải bỏ thêm để làm ra thêm một đơn vị sản phẩm. Với sản phẩm AI, chi phí biên là tiền điện và năng lực tính toán cho thêm một lượt trả lời, thường rất nhỏ; phần tốn kém lớn là huấn luyện mô hình, vốn là chi phí cố định. Ví dụ minh hoạ: nếu mỗi lượt trả lời tốn 1 xu tiền tính toán thì chi phí biên là 1 xu, dù công ty đã chi hàng trăm triệu đô la để huấn luyện mô hình. Khái niệm này quan trọng vì mọi quy tắc định giá trong bài đều đo giá so với chi phí biên.

**Biên giá (markup).** Phần chênh giữa giá và chi phí biên, tính theo tỷ lệ trên giá: (P − MC)/P, với P là giá và MC là chi phí biên. Ví dụ minh hoạ: giá 10 đô la, chi phí biên 6 đô la thì biên giá là (10 − 6)/10 = 40%. Mọi kết quả định lượng của bài (32%, 50%, 15%, 7%…) đều là biên giá theo nghĩa này.

**Độ co giãn của cầu theo giá (price elasticity), ký hiệu ε.** Phần trăm lượng mua giảm khi giá tăng 1%. Ví dụ minh hoạ: nếu giá tăng 1% làm lượng mua giảm 3% thì ε = 3. Cầu càng co giãn (ε lớn) thì người mua càng dễ bỏ đi khi giá lên, nên doanh nghiệp càng khó đặt giá cao. Trong bài, khi AI mạnh hơn và hữu ích hơn, người dùng khó bỏ nó hơn, tức cầu ít co giãn đi.

**Quy tắc Lerner (Lerner Rule).** Công thức chuẩn của kinh tế học cho doanh nghiệp tối đa hoá lợi nhuận: biên giá tối ưu bằng nghịch đảo độ co giãn, (P − MC)/P = 1/ε. Ví dụ minh hoạ: với ε = 3, biên giá tối ưu là 1/3, khoảng 33%; với ε = 2, biên giá là 50%. Bài lấy công thức này làm điểm xuất phát và chỉ sửa đúng một chỗ là tử số.

**Chỉ số động cơ tổng hợp (motive index), ký hiệu M.** Con số thay cho số 1 ở tử số của Quy tắc Lerner, gom mọi mục tiêu của doanh nghiệp vào một chỗ. M = 1 nghĩa là doanh nghiệp chỉ quan tâm lợi nhuận; M < 1 nghĩa là doanh nghiệp coi trọng phúc lợi xã hội và đặt giá thấp hơn. Ví dụ minh hoạ: với ε = 3 và M = 0,6, biên giá là 0,6/3 = 20% thay vì 33%. Đây là khái niệm trung tâm của bài, vì toàn bộ nội dung xã hội nằm trong M.

**Thặng dư tiêu dùng (consumer surplus).** Phần lợi người mua nhận được vượt quá số tiền họ trả. Ví dụ minh hoạ: một người sẵn lòng trả 30 đô la mỗi tháng cho một công cụ AI nhưng chỉ phải trả 20 đô la thì thặng dư tiêu dùng của họ là 10 đô la. Doanh nghiệp coi trọng thặng dư này sẽ muốn hạ giá để nhiều người được lợi hơn.

**Trọng số phúc lợi xã hội (social welfare weight) và hiệp phương sai.** Trọng số phúc lợi cho biết xã hội coi một đô la đến tay mỗi nhóm thu nhập là quý đến mức nào; thường một đô la cho người nghèo được tính nặng hơn một đô la cho người giàu. Hiệp phương sai đo hai đại lượng có đi cùng chiều với nhau hay không. Ví dụ minh hoạ: nếu nhóm thu nhập cao dùng sản phẩm gấp ba lần nhóm thu nhập thấp, thì mức tiêu dùng đi ngược chiều với trọng số phúc lợi (hiệp phương sai âm). Khái niệm này quyết định dấu của động cơ phân phối trong bài.

**Nhà hoạch định xã hội (social planner) và chuyển nhượng nhắm đúng đối tượng (targeted transfer).** Nhà hoạch định xã hội là một nhân vật giả định, có trong tay mọi công cụ của nhà nước như thuế và trợ cấp, và chọn mọi thứ để tối đa phúc lợi chung. Chuyển nhượng nhắm đúng đối tượng là khoản tiền chuyển thẳng tới người cần hỗ trợ, ví dụ trợ cấp tiền mặt cho hộ thu nhập thấp. Bài dùng nhân vật này làm thước đo: khoảng cách giữa giá của doanh nghiệp và giá của nhà hoạch định cho biết cái giá của việc dùng giá thay cho chính sách tài khoá.

## Nội dung chi tiết

### 1. Vấn đề đặt ra

Nhiều công ty AI hàng đầu công khai tuyên bố theo đuổi mục tiêu xã hội bên cạnh lợi nhuận. Cam kết này được thể hiện qua cấu trúc sở hữu đặc biệt, qua điều lệ công ty và qua các tuyên bố công khai. Nhưng khi đến lúc đặt giá cho sản phẩm, họ không có khung phân tích nào để tham chiếu: kinh tế học có sẵn công thức định giá cho doanh nghiệp chỉ cần lợi nhuận, chứ không có công thức cho doanh nghiệp vừa muốn lợi nhuận vừa muốn phục vụ xã hội.

Câu hỏi này không tầm thường vì giá của sản phẩm AI quyết định cùng lúc ba việc:

- **Ai được tiếp cận công nghệ.** Giá cao loại bớt người dùng có thu nhập thấp.
- **Doanh nghiệp thu được bao nhiêu để tái đầu tư**, trong đó có nghiên cứu về an toàn AI.
- **Tốc độ lao động bị thay thế.** Giá càng thấp, doanh nghiệp khách hàng càng nhanh dùng AI thay cho người làm.

Bài lấp khoảng trống này bằng cách mở rộng công cụ chuẩn của kinh tế học định giá là Quy tắc Lerner. Yêu cầu đặt ra là bản mở rộng phải chứa được các mục tiêu xã hội, mà vẫn giữ được dạng đơn giản như bản gốc và vẫn hiệu chuẩn được bằng số liệu thực tế.

### 2. Khung lý thuyết

**Điểm xuất phát: Quy tắc Lerner cổ điển.** Doanh nghiệp tối đa hoá lợi nhuận đặt giá sao cho

(P − MC)/P = 1/ε,

tức biên lợi nhuận tương đối bằng nghịch đảo của độ co giãn cầu. Biên giá tỷ lệ nghịch với độ co giãn: doanh nghiệp đối mặt với cầu ít co giãn (người mua khó bỏ đi) thì định giá cao hơn. Ví dụ minh hoạ: nếu ε = 3 thì biên giá là khoảng 33%; nếu ε giảm xuống 2 thì biên giá lên 50%.

**Bản mở rộng: Quy tắc Lerner Mở rộng.** Với doanh nghiệp có mục tiêu xã hội, bài chứng minh giá tối ưu thoả mãn

(P − MC)/P = M/ε.

Cấu trúc giữ nguyên, chỉ có tử số thay đổi: số 1 được thay bằng chỉ số động cơ tổng hợp M. Khi M = 1, ta quay lại đúng trường hợp tối đa hoá lợi nhuận. Khi M < 1, doanh nghiệp coi trọng phúc lợi xã hội và định giá thấp hơn. Như vậy cùng một công thức, nhưng toàn bộ nội dung xã hội được dồn vào tử số. Ưu điểm của cách viết này là người đọc chỉ cần biết hai con số, M và ε, để biết một doanh nghiệp sẽ đặt biên giá bao nhiêu.

**M được tạo từ bốn động cơ.** Bài phân rã M thành bốn thành phần, mỗi thành phần kéo giá theo một hướng:

| Động cơ | Nội dung | Tác động lên giá |
|---|---|---|
| Động cơ lợi nhuận | Trọng số doanh nghiệp đặt lên lợi nhuận của chính mình | Đẩy giá lên |
| Động cơ thặng dư tiêu dùng | Coi trọng lợi ích người dùng nhận được ngoài phần tiền họ trả | Đẩy giá xuống |
| Động cơ phân phối | Đặt trọng số cao hơn lên phúc lợi của người thu nhập thấp | Đẩy giá xuống (trong trường hợp thông thường), nhưng độ lớn nhỏ |
| Động cơ lao động | Tính tới việc sản phẩm làm dịch chuyển việc làm, gây tổn thất cho người lao động bị thay thế | Đẩy giá lên, vì giá cao làm chậm tốc độ áp dụng AI |

**Điểm tinh tế nhất: hai động cơ kéo ngược chiều nhau.** Động cơ thặng dư tiêu dùng và động cơ lao động đối nghịch. Quan tâm tới người tiêu dùng nói "hãy hạ giá" để nhiều người tiếp cận được. Quan tâm tới người lao động bị thay thế nói "đừng hạ quá nhanh", vì giá thấp làm doanh nghiệp khách hàng áp dụng AI nhanh hơn, và do đó đẩy nhanh việc mất việc làm. Một doanh nghiệp quan tâm tới cả hai nhóm phải cân hai lực này với nhau, và giá cuối cùng phụ thuộc vào lực nào lớn hơn.

### 3. Năm mệnh đề

Phần lý thuyết của bài được tóm lại trong năm mệnh đề:

**Mệnh đề 1: tồn tại và dạng của quy tắc mở rộng.** Với các giả định chuẩn về hàm cầu, giá tối ưu của doanh nghiệp có mục tiêu xã hội luôn tồn tại và thoả mãn (P − MC)/P = M/ε, với M tổng hợp bốn động cơ nói trên.

**Mệnh đề 2: doanh nghiệp vị lợi thuần tuý.** Doanh nghiệp vị lợi thuần tuý là doanh nghiệp chỉ tối đa hoá tổng phúc lợi, không đặt trọng số riêng nào cho lợi nhuận của mình. Doanh nghiệp này định giá thấp hơn doanh nghiệp tối đa hoá lợi nhuận, nhưng vẫn cao hơn chi phí biên khi có chi phí cố định phải thu hồi. Đây là điểm quan trọng: ngay cả một doanh nghiệp hoàn toàn không quan tâm tới lợi nhuận riêng cũng không nên định giá bằng chi phí biên. Nếu bán đúng bằng chi phí biên, doanh nghiệp không thu lại được khoản tiền đã bỏ ra để huấn luyện mô hình, và sẽ không có nguồn cho nghiên cứu và phát triển tiếp theo.

**Mệnh đề 3: động cơ phân phối có thể làm giá tăng.** Đây là kết quả trái trực giác. Phần đóng góp của động cơ phân phối vào M tỷ lệ với hiệp phương sai giữa trọng số phúc lợi xã hội và mức tiêu dùng sản phẩm. Nói bằng lời thường: hạ giá chỉ giúp người nghèo nhiều hơn người giàu khi người nghèo dùng sản phẩm nhiều hơn. Sản phẩm AI cao cấp thường được người thu nhập cao dùng nhiều hơn, nên hiệp phương sai này có thể mang dấu khiến động cơ phân phối làm giá tăng chứ không giảm. Lý do: hạ giá một sản phẩm mà người giàu dùng nhiều thì phần lớn lợi ích của việc hạ giá đến tay người giàu.

**Mệnh đề 4: động cơ lao động.** Động cơ lao động làm giá tăng khi sản phẩm thay thế lao động. Độ lớn của nó tỷ lệ với hai thứ: tổn thất phúc lợi của người bị dịch chuyển, và tốc độ dịch chuyển.

**Mệnh đề 5: kết luận chính sách.** Định giá là công cụ phân phối lại kém hiệu quả so với thuế và chuyển nhượng. Lý do là giá chỉ tác động qua một sản phẩm duy nhất, và một mức giá áp chung cho mọi người không nhắm được đúng đối tượng cần hỗ trợ.

### 4. Hiệu chuẩn và kết quả định lượng

**Các tham số hiệu chuẩn.** Mô hình được hiệu chuẩn trên 525 nghề nghiệp tại Hoa Kỳ, với các giá trị sau:

| Tham số | Ý nghĩa | Giá trị |
|---|---|---|
| α | Mức độ tiếp xúc của tác vụ với AI | 4% |
| σ | Độ co giãn thay thế giữa AI và lao động | 3 |
| ψ | Chi phí dịch chuyển của người lao động bị thay thế | 0,5 × mức lương trung bình |
| μ = λ | Trọng số các động cơ | 0,5 |

**Ba loại doanh nghiệp đi theo ba quỹ đạo khác nhau khi năng lực AI tăng:**

| Loại doanh nghiệp | Biên giá khi AI mạnh dần | Cơ chế |
|---|---|---|
| Tối đa hoá lợi nhuận | Tăng từ 32% lên 50% | Sản phẩm hữu ích hơn nên cầu ít co giãn hơn, doanh nghiệp tăng biên |
| Vị lợi thuần tuý (utilitarian) | Tăng từ 15% lên 20% | Định giá thấp hơn nhiều, chủ yếu chỉ đủ trang trải chi phí cố định |
| Đa mục tiêu (multi-objective) | Giảm từ 33% xuống 15% | Đi theo chiều ngược lại: lợi ích tiêu dùng tăng nhanh hơn tổn thất dịch chuyển lao động, nên cân bằng giữa hai động cơ đối nghịch dịch về phía hạ giá |

Kết quả của doanh nghiệp đa mục tiêu là đáng chú ý nhất. Khi AI mạnh hơn, mối lo về dịch chuyển lao động nhỏ dần so với lợi ích mà người tiêu dùng nhận được, nên doanh nghiệp giảm biên giá. Điều này cho thấy các loại doanh nghiệp khác nhau không chỉ ở mức giá mà ở cả hình dạng quỹ đạo giá theo thời gian: một loại tăng biên, một loại giảm biên.

**Độ lớn của động cơ phân phối: kết quả then chốt.** Bài tính riêng phần mà động cơ phân phối đóng góp vào giá ở từng nhóm thu nhập:

- Ở nhóm thu nhập thấp nhất, động cơ này kéo giá xuống khoảng 1 xu.
- Ở nhóm thu nhập cao nhất, nó kéo giá lên khoảng 12 xu.

Nói cách khác, mối quan tâm phân phối gần như không có ý nghĩa kinh tế trong quyết định giá. Một doanh nghiệp tuyên bố định giá vì công bằng thực ra chỉ thay đổi được giá vài xu.

**So sánh với nhà hoạch định xã hội.** Nhà hoạch định xã hội có đầy đủ công cụ thuế sẽ đặt biên giá tối ưu chỉ 7%. Nếu có thêm cơ chế chuyển nhượng nhắm đúng đối tượng, biên giá tối ưu giảm xuống dưới 1%. Khoảng cách giữa 15% của doanh nghiệp vị lợi và 7% của nhà hoạch định chính là cái giá của việc phải dùng giá thay cho chính sách tài khoá. Doanh nghiệp vị lợi không định giá cao hơn vì tham lợi nhuận, mà vì nó phải tự thu hồi chi phí cố định qua giá, trong khi nhà hoạch định có thể thu hồi qua thuế chung.

| Chủ thể định giá | Biên giá tối ưu |
|---|---|
| Doanh nghiệp vị lợi thuần tuý | 15% (lên 20% khi AI mạnh hơn) |
| Nhà hoạch định xã hội có công cụ thuế | 7% |
| Nhà hoạch định có thêm chuyển nhượng nhắm đúng đối tượng | Dưới 1% |

### 5. Hàm ý

**Với doanh nghiệp.** Tuyên bố mục tiêu xã hội hàm ý một mức giá thấp hơn đáng kể so với tối đa hoá lợi nhuận, nhưng không hàm ý định giá bằng chi phí, vì chi phí cố định vẫn phải được thu hồi. Và nếu doanh nghiệp thực sự quan tâm tới người lao động bị thay thế, họ cần nhận ra rằng mối quan tâm đó đẩy giá theo chiều ngược với mối quan tâm tới người tiêu dùng; hai mục tiêu không thể cùng được phục vụ tối đa bằng một mức giá.

**Với nhà hoạch định chính sách.** Không nên trông cậy vào chính sách giá của doanh nghiệp để đạt mục tiêu phân phối, vì như bài đã tính, tác động phân phối của giá chỉ vài xu. Công cụ phân phối lại phải là thuế và chuyển nhượng. Ở khâu định giá, điều nhà nước nên quan tâm là sức mạnh thị trường (doanh nghiệp có đang lạm dụng vị thế để đặt giá cao không) và khả năng tiếp cận, chứ không phải công bằng phân phối.

**Về chi phí dịch chuyển lao động.** Bài gợi ý rằng nếu xã hội muốn doanh nghiệp AI tính tới chi phí mà người lao động bị thay thế phải gánh, cách hiệu quả hơn là nội hoá chi phí đó, tức là buộc nó hiện ra trong chi phí của doanh nghiệp, qua thuế hoặc qua một cơ chế bảo hiểm cho người lao động. Cách này tốt hơn việc trông cậy vào lòng vị tha của doanh nghiệp thể hiện qua giá.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Lerner Rule | Quy tắc Lerner, biên lợi nhuận tối ưu bằng nghịch đảo độ co giãn cầu |
| Modified Lerner Rule | Quy tắc Lerner Mở rộng, thay tử số bằng chỉ số động cơ tổng hợp |
| Markup | Biên giá, phần chênh giữa giá và chi phí biên tính theo tỷ lệ trên giá |
| Marginal cost | Chi phí biên để sản xuất thêm một đơn vị |
| Price elasticity | Độ co giãn của cầu theo giá |
| Motive index | Chỉ số động cơ tổng hợp, tử số trong quy tắc mở rộng |
| Profit motive | Động cơ lợi nhuận, đẩy giá lên |
| Consumer surplus motive | Động cơ thặng dư tiêu dùng, đẩy giá xuống |
| Distributional motive | Động cơ phân phối, đặt trọng số cao hơn cho người thu nhập thấp |
| Labor motive | Động cơ lao động, tính tới tổn thất của người bị thay thế |
| Utilitarian firm | Doanh nghiệp vị lợi, tối đa hoá tổng phúc lợi không ưu tiên lợi nhuận riêng |
| Multi-objective firm | Doanh nghiệp đa mục tiêu, cân bằng lợi nhuận và phúc lợi |
| Social planner | Nhà hoạch định xã hội, có đầy đủ công cụ thuế và chuyển nhượng |
| Social welfare weight | Trọng số phúc lợi xã hội gán cho từng nhóm thu nhập |
| Task exposure | Mức độ tiếp xúc của tác vụ nghề nghiệp với khả năng tự động hoá bằng AI |
| Elasticity of substitution | Độ co giãn thay thế giữa AI và lao động con người |
| Displacement cost | Chi phí dịch chuyển mà người lao động bị thay thế phải gánh |
| Fixed cost recovery | Thu hồi chi phí cố định, lý do giá phải cao hơn chi phí biên |
| Covariance term | Số hạng hiệp phương sai quyết định dấu của động cơ phân phối |
| Targeted transfer | Chuyển nhượng nhắm đúng đối tượng, công cụ phân phối lại hiệu quả hơn giá |

## Câu nói đáng nhớ

> "Concern for consumers says lower the price. Concern for displaced workers says do not lower it too fast."

> "The distributional motive moves the price by about one cent at the bottom of the distribution. It is economically negligible."

> "Pricing is a poor substitute for taxes and transfers."

## Đánh giá và phát hiện đáng chú ý

### Đóng góp thật là một kết quả phủ định, và nó được đo bằng một con số đủ nhỏ để kết thúc tranh luận

Phần lớn giá trị của bài không nằm ở công thức mà nằm ở một con số: **một xu**. Đó là mức mà mối quan tâm phân phối kéo giá xuống ở nhóm thu nhập thấp nhất.

Điều làm con số này có sức nặng là nó bác bỏ một lập luận rất phổ biến bằng phương pháp mà lập luận đó tự nhận là dựa vào. Khi một công ty công nghệ nói rằng chính sách giá của mình phục vụ mục tiêu tiếp cận công bằng, họ đang tuyên bố rằng động cơ phân phối có ảnh hưởng đáng kể tới giá. Bài tính ra ảnh hưởng đó và nó gần bằng không.

Quan trọng hơn con số là cơ chế, vì cơ chế thì tổng quát. Đóng góp của động cơ phân phối tỷ lệ với **hiệp phương sai giữa trọng số phúc lợi xã hội và mức tiêu dùng sản phẩm**. Nói bằng lời thường: định giá chỉ là công cụ phân phối lại khi người nghèo dùng sản phẩm nhiều hơn người giàu. Với một sản phẩm cao cấp mà người giàu dùng nhiều hơn, dấu của hiệp phương sai đảo lại, và việc quan tâm tới phân phối sẽ đẩy giá **lên** — đúng mười hai xu ở nhóm thu nhập cao nhất, theo tính toán của bài.

Kết quả này vượt xa phạm vi AI. Nó là một lập luận tổng quát chống lại việc dùng giá của bất kỳ sản phẩm cao cấp nào làm công cụ công bằng xã hội, và nó áp dụng trực tiếp cho mọi cơ chế trợ giá chéo trong dịch vụ công.

### Kết quả hữu dụng nhất bị giấu trong một bảng: cách phân biệt lời nói với hành động

Bài ghi nhận rằng doanh nghiệp tối đa hoá lợi nhuận tăng biên giá từ 32% lên 50% khi năng lực AI tăng, còn doanh nghiệp đa mục tiêu **đi ngược lại**, giảm từ 33% xuống 15%. Bài gọi đây là khác biệt về hình dạng quỹ đạo chứ không chỉ về mức, rồi dừng lại.

Hãy để ý con số xuất phát: 32% và 33%. Gần như trùng nhau. Nghĩa là **tại một thời điểm, không thể phân biệt hai loại doanh nghiệp bằng giá của họ**. Một công ty có mục tiêu xã hội thật và một công ty tối đa hoá lợi nhuận thuần tuý có thể đang bán ở cùng một mức biên, và mọi phân tích cắt ngang đều bất lực.

Thứ phân biệt được hai loại là **đạo hàm**: giá thay đổi theo chiều nào khi sản phẩm mạnh lên. Bên tối đa hoá lợi nhuận tăng biên vì cầu trở nên ít co giãn hơn khi sản phẩm hữu ích hơn — đây là hành vi bắt buộc của kẻ có sức mạnh thị trường. Bên đa mục tiêu giảm biên vì khi lợi ích tiêu dùng tăng nhanh hơn tổn thất dịch chuyển lao động, cân bằng giữa hai động cơ đối nghịch dịch về phía hạ giá.

Đây là một tiêu chí **quan sát được, kiểm chứng được và khó nguỵ tạo**, và nó tốt hơn nhiều so với mọi công cụ hiện đang được dùng để đánh giá cam kết xã hội của doanh nghiệp công nghệ: điều lệ công ty, cấu trúc sở hữu đặc biệt, hội đồng đạo đức, tuyên bố sứ mệnh. Tất cả những thứ đó đều rẻ để tuyên bố và không ràng buộc gì. Quỹ đạo giá thì tốn tiền thật.

Đây là ý tưởng thực tiễn nhất trong bài và nó nằm trong một ô bảng.

### Căng thẳng giữa hai động cơ dẫn tới một kết luận mà bài không dám phát biểu thẳng

Phát hiện rằng động cơ thặng dư tiêu dùng và động cơ lao động kéo ngược chiều nhau là điểm mới thật sự của khung này. Nhưng hãy dịch nó ra tiếng thường.

Một doanh nghiệp thực sự quan tâm tới người lao động bị thay thế **nên giữ giá sản phẩm ở mức cao**, vì giá cao làm chậm tốc độ áp dụng và do đó làm chậm tốc độ mất việc. Nói cách khác, hành vi đạo đức được khuyến nghị ở đây là **hạn chế quyền tiếp cận một công nghệ có lợi, bằng giá, để bảo vệ việc làm**.

Đó là một loại thuế tự động hoá. Nhưng nó là một thứ thuế có ba đặc tính bất thường. Thứ nhất, **mức thuế do chính bên hưởng lợi từ tự động hoá đặt ra**. Thứ hai, **tiền thuế chảy vào túi bên đặt thuế**, không vào ngân sách và không tới người lao động bị thay thế. Thứ ba, và đây là điểm khó chịu nhất: **nó không phân biệt được với hành vi định giá độc quyền**. Cùng một mức giá cao, cùng một dòng lợi nhuận, chỉ khác nhau ở lời giải thích.

Mệnh đề thứ năm của bài đi tới kết luận đúng — hãy dùng thuế và chuyển nhượng — nhưng bài không nói ra điều đáng nói nhất: rằng mức giá "có đạo đức" và mức giá độc quyền trùng nhau về hình thức, nên việc khuyến khích doanh nghiệp tự nguyện tính tới chi phí lao động qua giá là trao cho họ một lời biện minh đạo đức cho chính hành vi mà chính sách cạnh tranh tồn tại để ngăn chặn.

### Ba giả định làm kết quả định lượng mong manh hơn vẻ ngoài của nó

**Mức độ tiếp xúc của tác vụ với AI đặt ở bốn phần trăm.** Đây là một con số rất thấp so với hầu hết các ước lượng đang lưu hành, và động cơ lao động tỷ lệ trực tiếp với nó. Nếu mức tiếp xúc thực tế là hai mươi phần trăm, động cơ lao động lớn gấp năm lần, và toàn bộ kết quả về hình dạng quỹ đạo có thể đổi: doanh nghiệp đa mục tiêu sẽ không còn giảm biên giá khi AI mạnh lên, vì tổn thất dịch chuyển tăng nhanh hơn. Kết luận về hình dạng quỹ đạo — phần hay nhất của bài — phụ thuộc vào tốc độ tăng tương đối của hai số hạng, mà điều đó lại phụ thuộc vào một tham số được đặt khá tuỳ ý.

**Hiệu chuẩn trên 525 nghề nghiệp Hoa Kỳ.** Cấu trúc nghề nghiệp, mức lương và chi phí dịch chuyển ở Hoa Kỳ rất khác với các nền kinh tế đang phát triển. Với một nước có tỷ trọng lớn lao động trong nông nghiệp và chế biến thâm dụng lao động, mức tiếp xúc với AI thấp hơn nhưng năng lực hấp thụ dịch chuyển cũng thấp hơn nhiều, nên hai hiệu ứng không triệt tiêu nhau một cách gọn gàng.

**Một doanh nghiệp, một mức giá.** Đây là giả định hạn chế nhất và nó đóng lại đúng lối thoát mà ngành đang dùng. Thị trường AI thực tế đầy phân biệt giá: bậc miễn phí, giá cho sinh viên và tổ chức giáo dục, giá theo quốc gia, giá doanh nghiệp cao gấp nhiều lần giá cá nhân, hạn ngạch sử dụng thay cho giá. Một doanh nghiệp muốn vừa tối đa thặng dư tiêu dùng vừa hạn chế tốc độ dịch chuyển lao động **sẽ không đặt một mức giá** — nó sẽ đặt giá thấp cho cá nhân và giá cao cho doanh nghiệp, vì chính khách hàng doanh nghiệp mới là bên thực hiện việc thay thế lao động.

Chiến lược đó giải quyết căng thẳng trung tâm của bài một cách gần như hoàn hảo, và mô hình một giá không có chỗ cho nó. Đây là hạn chế đáng kể, vì nó có nghĩa là bài đang phân tích một bài toán mà thị trường thực đã giải bằng cách khác.

### Con số đáng nhớ nhất không phải một xu, mà là khoảng cách giữa mười lăm và bảy

Doanh nghiệp vị lợi thuần tuý — loại quan tâm tối đa tới phúc lợi xã hội, không đặt trọng số riêng nào cho lợi nhuận của mình — vẫn định giá ở biên mười lăm phần trăm. Nhà hoạch định xã hội có công cụ thuế thì đặt biên tối ưu ở bảy phần trăm, và dưới một phần trăm nếu có cơ chế chuyển nhượng nhắm đúng đối tượng.

Khoảng cách tám điểm đó là **cái giá của việc không có công cụ tài khoá**, được đo lần đầu tiên bằng một con số. Và nó nói một điều tinh tế: doanh nghiệp vị lợi không định giá cao vì tham, mà vì nó phải tự thu hồi chi phí cố định qua giá, trong khi nhà hoạch định xã hội có thể thu hồi chúng qua thuế chung và để giá gần chi phí biên.

Điều này đặt lại toàn bộ cuộc tranh luận về giá của sản phẩm AI. Nó không phải cuộc tranh luận về đạo đức doanh nghiệp mà là một bài toán tối ưu bậc hai: khi công cụ tốt nhất không có, ta dùng công cụ tệ hơn, và độ tệ đo được. Kết luận hành động là rõ: nếu xã hội muốn giá AI gần chi phí biên, cách để đạt điều đó không phải là thuyết phục doanh nghiệp tử tế hơn mà là tìm một cơ chế khác để tài trợ chi phí cố định — tài trợ nghiên cứu công, mua sắm công, hoặc mô hình trọng số mở.

### Với người đọc Việt Nam: bài này không nói về AI nhiều bằng nói về trợ giá chéo

Đây là tài liệu ít liên quan tới Việt Nam nhất trong thư mục, nếu đọc nó như một bài về công ty AI. Nhưng khung phân tích của nó lại áp dụng trực tiếp vào một thực tiễn rất quen thuộc.

Khái niệm "doanh nghiệp có mục tiêu xã hội" ở Hoa Kỳ chủ yếu là một tuyên bố tự nguyện của công ty tư nhân. Ở Việt Nam, đó là một **loại hình thể chế có thật và phổ biến**: doanh nghiệp nhà nước và doanh nghiệp có vốn nhà nước trong viễn thông, điện, ngân hàng và dịch vụ công, được giao đồng thời nhiệm vụ kinh doanh và nhiệm vụ xã hội. Và công cụ mặc định để thực hiện nhiệm vụ xã hội ấy là **trợ giá chéo**: đặt giá thấp cho nhóm này và cao cho nhóm kia trong cùng một biểu giá.

Bài này nói rằng cách làm đó gần như luôn kém hiệu quả hơn thuế và chuyển nhượng, và quan trọng hơn, nó đưa ra điều kiện để biết khi nào cách làm đó **phản tác dụng**: khi nhóm khá giả tiêu dùng dịch vụ nhiều hơn nhóm khó khăn. Với nhiều dịch vụ, điều kiện đó đúng — người tiêu thụ nhiều điện hơn, dùng nhiều dữ liệu di động hơn, giao dịch ngân hàng nhiều hơn thường là người có thu nhập cao hơn. Trong những trường hợp đó, trợ giá chéo trên biểu giá chung là một cơ chế **lũy thoái được khoác tên xã hội**, và kết quả hiệp phương sai của bài giải thích chính xác vì sao.

Góc thứ hai, ở phía cầu. Việt Nam là bên **nhập khẩu dịch vụ AI** với giá do doanh nghiệp nước ngoài đặt, và không có đòn bẩy nào đối với việc họ chọn quỹ đạo giá nào. Kết quả của bài nói rằng quỹ đạo đó có thể đi lên hoặc đi xuống tuỳ vào mục tiêu nội bộ của từng công ty. Đặt cược khả năng tiếp cận công nghệ của cả một nền kinh tế vào thiện chí của vài nhà cung cấp nước ngoài là một rủi ro không cần thiết. Hai biện pháp giảm rủi ro đó không nằm trong bài nhưng suy ra được từ nó: duy trì cạnh tranh giữa nhiều nhà cung cấp thay vì khoá vào một bên, và giữ năng lực dùng được mô hình trọng số mở — vì mô hình trọng số mở làm cho độ co giãn của cầu tăng lên, và theo đúng Quy tắc Lerner, độ co giãn cao hơn kéo biên giá của mọi nhà cung cấp xuống, bất kể họ có mục tiêu xã hội hay không.

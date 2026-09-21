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

## Dàn ý chi tiết

### 1. Vấn đề đặt ra

- Nhiều công ty AI hàng đầu công khai tuyên bố theo đuổi mục tiêu xã hội bên cạnh lợi nhuận, thể hiện qua cấu trúc sở hữu đặc biệt, điều lệ công ty và các cam kết công khai. Nhưng khi đến lúc đặt giá cho sản phẩm, họ không có khung phân tích nào để tham chiếu.
- Câu hỏi không tầm thường vì giá của sản phẩm AI quyết định đồng thời ba thứ: ai được tiếp cận công nghệ, doanh nghiệp thu được bao nhiêu để tái đầu tư vào nghiên cứu an toàn, và tốc độ mà lao động bị thay thế.
- Bài lấp khoảng trống này bằng cách mở rộng công cụ chuẩn của kinh tế học định giá là Quy tắc Lerner, sao cho nó chứa được các mục tiêu xã hội mà vẫn giữ dạng đơn giản và có thể hiệu chuẩn bằng số liệu.

### 2. Khung lý thuyết

- Trong Quy tắc Lerner cổ điển, biên lợi nhuận tương đối bằng nghịch đảo của độ co giãn cầu. Doanh nghiệp đối mặt với cầu ít co giãn định giá cao hơn.
- Quy tắc Lerner Mở rộng giữ nguyên cấu trúc nhưng thay tử số bằng một chỉ số động cơ tổng hợp. Khi chỉ số này bằng một, ta quay lại trường hợp tối đa hoá lợi nhuận. Khi nhỏ hơn một, doanh nghiệp định giá thấp hơn.
- Chỉ số động cơ được phân rã thành bốn thành phần. **Động cơ lợi nhuận** phản ánh trọng số doanh nghiệp đặt lên lợi nhuận của mình và đẩy giá lên. **Động cơ thặng dư tiêu dùng** phản ánh việc coi trọng lợi ích người dùng và đẩy giá xuống. **Động cơ phân phối** phản ánh việc đặt trọng số cao hơn lên phúc lợi của người thu nhập thấp. **Động cơ lao động** phản ánh việc tính tới tổn thất của người lao động bị sản phẩm thay thế.
- Điểm tinh tế nhất của khung này là hai động cơ cuối kéo ngược chiều nhau. Quan tâm tới người tiêu dùng nói hãy hạ giá để nhiều người tiếp cận được; quan tâm tới người lao động bị thay thế nói đừng hạ quá nhanh, vì giá thấp đẩy nhanh việc áp dụng và do đó đẩy nhanh dịch chuyển việc làm.

### 3. Năm mệnh đề

- Mệnh đề đầu thiết lập sự tồn tại và dạng của quy tắc mở rộng với các giả định cầu chuẩn.
- Mệnh đề thứ hai cho thấy doanh nghiệp vị lợi thuần tuý định giá thấp hơn doanh nghiệp tối đa hoá lợi nhuận, nhưng vẫn cao hơn chi phí biên khi tồn tại chi phí cố định cần thu hồi. Đây là điểm quan trọng: ngay cả một doanh nghiệp hoàn toàn không quan tâm tới lợi nhuận riêng cũng không nên định giá bằng chi phí biên, vì như vậy sẽ không có nguồn cho nghiên cứu và phát triển.
- Mệnh đề thứ ba đưa ra một kết quả trái trực giác. Đóng góp của động cơ phân phối vào chỉ số động cơ tỷ lệ với hiệp phương sai giữa trọng số phúc lợi xã hội và mức tiêu dùng sản phẩm. Vì sản phẩm AI cao cấp thường được người thu nhập cao dùng nhiều hơn, hiệp phương sai này có thể mang dấu khiến động cơ phân phối làm giá tăng chứ không giảm.
- Mệnh đề thứ tư định lượng động cơ lao động: nó làm giá tăng khi sản phẩm thay thế lao động, với độ lớn tỷ lệ với tổn thất phúc lợi của người bị dịch chuyển và tốc độ dịch chuyển.
- Mệnh đề thứ năm là kết luận chính sách: định giá là công cụ phân phối lại kém hiệu quả so với thuế và chuyển nhượng, vì nó chỉ tác động qua một sản phẩm duy nhất và không nhắm được đúng đối tượng cần hỗ trợ.

### 4. Hiệu chuẩn và kết quả định lượng

- Mô hình được hiệu chuẩn trên 525 nghề nghiệp tại Hoa Kỳ, với mức độ tiếp xúc của tác vụ với AI đặt ở 4%, độ co giãn thay thế bằng 3, chi phí dịch chuyển lao động bằng một nửa mức lương trung bình, và các trọng số động cơ đặt ở 0,5.
- Khi năng lực AI tăng, doanh nghiệp tối đa hoá lợi nhuận tăng biên giá từ 32% lên 50%, vì cầu trở nên ít co giãn hơn khi sản phẩm hữu ích hơn.
- Doanh nghiệp vị lợi thuần tuý cũng tăng biên giá nhưng từ mức thấp hơn nhiều, từ 15% lên 20%, chủ yếu để trang trải chi phí cố định.
- Doanh nghiệp đa mục tiêu cho kết quả đáng chú ý nhất: biên giá đi theo chiều ngược lại, giảm từ 33% xuống 15%. Cơ chế là khi AI mạnh hơn, lợi ích tiêu dùng tăng nhanh hơn tổn thất dịch chuyển lao động, nên cân bằng giữa hai động cơ đối nghịch dịch chuyển về phía hạ giá. Điều này có nghĩa là các loại doanh nghiệp khác nhau không chỉ ở mức giá mà ở cả hình dạng quỹ đạo giá theo thời gian.
- Về động cơ phân phối, kết quả rất rõ ràng: ở nhóm thu nhập thấp nhất, động cơ này kéo giá xuống khoảng một xu; ở nhóm thu nhập cao nhất, nó kéo giá lên khoảng mười hai xu. Nói cách khác, mối quan tâm phân phối gần như không có ý nghĩa kinh tế trong quyết định giá.
- So sánh với nhà hoạch định xã hội có đầy đủ công cụ thuế: biên giá tối ưu chỉ 7%, và giảm xuống dưới 1% khi có sẵn cơ chế chuyển nhượng nhắm đúng đối tượng. Khoảng cách giữa 15% của doanh nghiệp vị lợi và 7% của nhà hoạch định chính là cái giá của việc phải dùng giá thay cho chính sách tài khoá.

### 5. Hàm ý

- Với doanh nghiệp: tuyên bố mục tiêu xã hội hàm ý một mức giá thấp hơn đáng kể so với tối đa hoá lợi nhuận, nhưng không hàm ý định giá bằng chi phí. Và nếu doanh nghiệp thực sự quan tâm tới người lao động bị thay thế, họ nên nhận ra rằng mối quan tâm đó đẩy giá theo chiều ngược với mối quan tâm tới người tiêu dùng.
- Với nhà hoạch định chính sách: không nên trông cậy vào chính sách giá của doanh nghiệp để đạt mục tiêu phân phối. Công cụ phân phối lại phải là thuế và chuyển nhượng. Điều nhà nước nên quan tâm ở khâu định giá là sức mạnh thị trường và khả năng tiếp cận, chứ không phải công bằng.
- Bài cũng gợi ý rằng nếu xã hội muốn doanh nghiệp AI tính tới chi phí dịch chuyển lao động, cách hiệu quả hơn là nội hoá chi phí đó qua thuế hoặc qua cơ chế bảo hiểm, thay vì trông cậy vào lòng vị tha của doanh nghiệp thể hiện qua giá.

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

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

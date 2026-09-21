# Understanding Stablecoins — Hiểu về stablecoin

**Nguồn:** IMF Departmental Paper.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 7, không có trang bìa và trang tác giả).
**Ý chính:** Stablecoin đã đạt quy mô khoảng 300 tỷ đô la vào tháng 9/2025, chiếm khoảng 7% thị trường tiền mã hoá, với hơn 97% neo vào đô la Mỹ. Bài lập luận rằng stablecoin không phải một thứ duy nhất mà là một họ công cụ khác nhau về bảy đặc tính, và rằng đa số hoạt động hiện nay vẫn nằm trong hệ sinh thái tiền mã hoá chứ chưa phải thanh toán thực. Rủi ro chính không nằm ở công nghệ mà ở cấu trúc: một công cụ hứa hẹn ổn định mệnh giá nhưng được bảo chứng bằng tài sản có rủi ro và không có người cho vay cuối cùng.

> **Lưu ý:** bản PDF bắt đầu từ trang 7. Trang bìa, tóm tắt và danh sách tác giả không có trong bản này.

## Sơ đồ

### Bảy đặc tính định nghĩa một stablecoin

```text
       ❶ CƠ CHẾ NEO GIÁ
         · bảo chứng bằng tiền pháp định (chiếm ÁP ĐẢO thị trường)
         · bảo chứng bằng tiền mã hoá, thường THẾ CHẤP VƯỢT MỨC
         · thuật toán, không có tài sản bảo chứng đầy đủ
           → nhóm này đã SỤP ĐỔ ngoạn mục (TerraUSD, 5/2022)
                                │
       ❷ THÀNH PHẦN DỰ TRỮ
         · tiền mặt và tín phiếu kho bạc ngắn hạn ◂── chất lượng cao
         · thương phiếu, tiền gửi, repo ◂── rủi ro tín dụng
         · vàng, tiền mã hoá khác ◂── rủi ro giá
       → QUYẾT ĐỊNH khả năng chịu đựng khi bị rút hàng loạt
                                │
       ❸ QUYỀN QUY ĐỔI
         · ai được quy đổi TRỰC TIẾP với bên phát hành? thường CHỈ
           các đối tác được cấp phép, KHÔNG phải người nắm giữ lẻ
         · phí quy đổi, mức tối thiểu, thời gian xử lý
         · quyền TẠM DỪNG quy đổi ◂── điểm dễ tổn thương nhất
       → người nắm giữ lẻ phải bán trên THỊ TRƯỜNG THỨ CẤP, nơi giá
         có thể lệch mệnh giá khi căng thẳng
                                │
       ❹ CẤU TRÚC PHÁP LÝ VÀ NƠI ĐĂNG KÝ
         · yêu cầu trên bên phát hành? trên tài sản dự trữ? hay chỉ
           là quan hệ hợp đồng?
         · nhiều bên phát hành đặt tại các trung tâm tài chính hải
           ngoại → quyền của người nắm giữ khi phá sản KHÔNG RÕ
                                │
       ❺ SỔ CÁI VÀ KHẢ NĂNG LIÊN THÔNG
         · phát hành trên nhiều blockchain cùng lúc
         · cầu nối giữa các chuỗi là điểm yếu an ninh đã bị khai thác
                                │
       ❻ QUẢN TRỊ VÀ KIỂM SOÁT
         · ai có quyền ĐÓNG BĂNG hoặc HUỶ token? (phần lớn bên phát
           hành lớn ĐỀU có quyền này)
         · ai quyết định thay đổi dự trữ, phí, điều khoản?
                                │
       ❼ MINH BẠCH
         · chứng thực (attestation) ≠ KIỂM TOÁN đầy đủ
         · tần suất công bố, mức chi tiết, bên xác nhận độc lập
```

### Bức tranh thị trường tháng 9/2025

```text
       QUY MÔ ────────────────────────────────────────────────────
       · tổng vốn hoá ≈ 300 TỶ ĐÔ LA
       · ≈ 7% toàn thị trường tiền mã hoá
       · hơn 97% neo vào ĐÔ LA MỸ → stablecoin về bản chất là hiện
         tượng ĐÔ LA HOÁ KỸ THUẬT SỐ
       · thị trường TẬP TRUNG CAO vào hai bên phát hành lớn nhất
       ────────────────────────────────────────────────────────────
       KHỐI LƯỢNG GIAO DỊCH — CẢNH BÁO VỀ SỐ LIỆU
       · con số khối lượng thô rất lớn, thường được dùng để lập luận
         rằng stablecoin đã vượt các mạng thẻ
       · NHƯNG ước tính khoảng 80% lưu lượng là do BOT tạo ra: giao
         dịch chênh lệch giá, tạo lập thị trường tự động, chuyển nội
         bộ giữa các ví của cùng một chủ thể
       → sau khi lọc, khối lượng THANH TOÁN THỰC nhỏ hơn NHIỀU
       ────────────────────────────────────────────────────────────
       CÔNG DỤNG THỰC TẾ — theo thứ tự quan trọng
       ① TÀI SẢN ĐỆM trong giao dịch tiền mã hoá (vào/ra vị thế mà
         không phải về tiền pháp định) ◂── ÁP ĐẢO
       ② TÀI SẢN BẢO ĐẢM trong tài chính phi tập trung
       ③ LƯU TRỮ GIÁ TRỊ bằng đô la ở nước có lạm phát cao hoặc
         kiểm soát ngoại hối chặt ◂── đang TĂNG
       ④ THANH TOÁN XUYÊN BIÊN GIỚI và kiều hối ◂── tiềm năng thật
         nhưng quy mô còn NHỎ so với kênh truyền thống
       ⑤ THANH TOÁN BÁN LẺ hàng ngày ◂── vẫn RẤT HẠN CHẾ
```

### Tám nhóm rủi ro

```text
       ❶ RÚT CHẠY HÀNG LOẠT
         cấu trúc giống quỹ thị trường tiền tệ: hứa mệnh giá cố định
         nhưng nắm tài sản có giá biến động · KHÔNG có bảo hiểm tiền
         gửi, KHÔNG có người cho vay cuối cùng
                                │
       ❷ LAN TRUYỀN SANG THỊ TRƯỜNG TÍN PHIẾU KHO BẠC
         khi dự trữ đủ lớn, việc bán tháo tín phiếu để đáp ứng quy
         đổi có thể GÂY ÁP LỰC lên chính thị trường được coi là an
         toàn nhất → kênh lây nhiễm từ tiền mã hoá sang tài chính
         truyền thống
                                │
       ❸ PHI TRUNG GIAN HOÁ NGÂN HÀNG
         tiền gửi rời khỏi ngân hàng → giảm nguồn vốn cho tín dụng
         · tác động mạnh hơn ở nước có hệ thống ngân hàng nhỏ
                                │
       ❹ THAY THẾ TIỀN TỆ
         ở nước lạm phát cao, stablecoin đô la dễ tiếp cận qua điện
         thoại → đô la hoá NHANH và SÂU hơn các đợt trước, làm suy
         yếu chính sách tiền tệ và thu phát hành tiền
                                │
       ❺ LÁCH QUẢN LÝ DÒNG VỐN
         token chuyển qua biên giới không đi qua ngân hàng đại lý,
         nơi các biện pháp CFM vốn được thực thi
                                │
       ❻ PHÂN MẢNH HỆ THỐNG THANH TOÁN
         nhiều stablecoin trên nhiều chuỗi, không liên thông →
         nguy cơ quay lại thời "tiền ngân hàng tư nhân" mỗi loại
         giao dịch ở mức chiết khấu khác nhau
                                │
       ❼ TÍNH TOÀN VẸN TÀI CHÍNH
         chuyển giao ngang hàng, ví không lưu ký, bên phát hành đặt
         ở nơi quản lý lỏng → rửa tiền, né trừng phạt
                                │
       ❽ RỦI RO PHÁP LÝ VÀ VẬN HÀNH
         quyền của người nắm giữ khi phá sản chưa rõ · lỗi hợp đồng
         thông minh · tấn công cầu nối chuỗi chéo
```

### Bốn khung quản lý đang hình thành

```text
       ┌──────────┬──────────────────────────────────────────────┐
       │ NHẬT BẢN │ sửa Luật Dịch vụ Thanh toán (PSA) — đi ĐẦU   │
       │          │ · chỉ NGÂN HÀNG, công ty uỷ thác và nhà      │
       │          │   chuyển tiền được cấp phép mới được phát    │
       │          │   hành → coi stablecoin là TIỀN, không phải  │
       │          │   tài sản mã hoá                             │
       │          │ · dự trữ phải giữ dưới dạng tiền gửi hoặc    │
       │          │   tài sản an toàn, TÁCH BIỆT khỏi bên phát   │
       │          │   hành                                       │
       ├──────────┼──────────────────────────────────────────────┤
       │ EU       │ MiCA — khung TOÀN DIỆN đầu tiên của một khối │
       │          │ · phân biệt token tiền điện tử (EMT, neo MỘT │
       │          │   đồng tiền) và token tham chiếu tài sản     │
       │          │   (ART, neo GIỎ)                             │
       │          │ · quyền quy đổi theo MỆNH GIÁ, MIỄN PHÍ cho  │
       │          │   người nắm giữ ◂── điểm mạnh nhất           │
       │          │ · quy tắc chặt hơn cho token "QUAN TRỌNG"    │
       │          │ · hạn chế stablecoin ngoại tệ dùng làm       │
       │          │   phương tiện thanh toán rộng rãi            │
       ├──────────┼──────────────────────────────────────────────┤
       │ HOA KỲ   │ Đạo luật GENIUS                              │
       │          │ · bên phát hành được phép ở cấp liên bang và │
       │          │   cấp bang, dự trữ 1:1 bằng tài sản chất     │
       │          │   lượng cao, công bố hàng tháng              │
       │          │ · CẤM trả lãi cho người nắm giữ ◂── nhằm     │
       │          │   hạn chế cạnh tranh với tiền gửi ngân hàng  │
       ├──────────┼──────────────────────────────────────────────┤
       │ ANH      │ BoE và FCA — cách tiếp cận PHÂN TẦNG         │
       │          │ · FCA quản lý bên phát hành nói chung        │
       │          │ · BoE giám sát riêng những loại đạt quy mô   │
       │          │   HỆ THỐNG, có thể áp HẠN MỨC NẮM GIỮ        │
       └──────────┴──────────────────────────────────────────────┘
       ĐIỂM CHUNG: cấp phép, dự trữ chất lượng cao và tách biệt,
       quyền quy đổi, công bố định kỳ
       ĐIỂM KHÁC: ai được phát hành · có trả lãi không · xử lý
       stablecoin ngoại tệ · ngưỡng "hệ thống"
       → RỦI RO: chênh lệch quy định tạo cơ hội ARBITRAGE PHÁP LÝ
```

## Ba câu hỏi bài viết trả lời

1. Stablecoin thực chất là gì, và những đặc tính nào quyết định mức rủi ro của từng loại?
2. Chúng đang được dùng để làm gì trong thực tế, và số liệu thị trường nói gì sau khi lọc nhiễu?
3. Các khung quản lý lớn đang hội tụ ở đâu và còn khác nhau ở đâu?

## Dàn ý chi tiết

### 1. Stablecoin không phải một thứ duy nhất

- Thuật ngữ stablecoin che giấu sự đa dạng lớn. Bài đề xuất phân loại theo bảy đặc tính: cơ chế neo giá, thành phần dự trữ, quyền quy đổi, cấu trúc pháp lý và nơi đăng ký, sổ cái và khả năng liên thông, quản trị và quyền kiểm soát, cùng mức độ minh bạch.
- Trong đó, quyền quy đổi và thành phần dự trữ quyết định phần lớn hồ sơ rủi ro. Một điểm thường bị hiểu sai: ở đa số stablecoin lớn, chỉ các đối tác được cấp phép mới quy đổi trực tiếp được với bên phát hành. Người nắm giữ lẻ phải bán trên thị trường thứ cấp, nơi giá có thể lệch mệnh giá khi căng thẳng.
- Nhóm stablecoin thuật toán, không có tài sản bảo chứng đầy đủ, đã sụp đổ ngoạn mục trong vụ TerraUSD tháng 5/2022. Bài coi đây là bằng chứng rằng cơ chế neo dựa hoàn toàn vào kỳ vọng thị trường không bền vững.
- So với tiền gửi ngân hàng, stablecoin thiếu ba thứ: bảo hiểm tiền gửi, quyền tiếp cận người cho vay cuối cùng, và khung giám sát thận trọng đầy đủ. So với quỹ thị trường tiền tệ, chúng thiếu các quy tắc về chất lượng và kỳ hạn tài sản vốn đã được siết sau các đợt khủng hoảng trước.

### 2. Thị trường thực tế

- Tổng vốn hoá khoảng 300 tỷ đô la vào tháng 9/2025, tương đương khoảng 7% thị trường tiền mã hoá. Hơn 97% neo vào đô la Mỹ, khiến stablecoin về bản chất là một hiện tượng đô la hoá kỹ thuật số chứ không phải một hệ thống tiền tệ đa dạng.
- Thị trường tập trung cao độ vào hai bên phát hành lớn nhất, làm rủi ro tập trung trở thành mối quan tâm riêng.
- Bài đưa ra một cảnh báo phương pháp quan trọng: các con số khối lượng giao dịch thô thường được dùng để lập luận rằng stablecoin đã vượt các mạng thẻ về quy mô thanh toán. Nhưng ước tính khoảng 80% lưu lượng trên chuỗi là do bot tạo ra, gồm giao dịch chênh lệch giá, tạo lập thị trường tự động và chuyển nội bộ giữa các ví của cùng một chủ thể. Sau khi lọc, khối lượng thanh toán thực nhỏ hơn rất nhiều.
- Các công dụng thực tế, xếp theo mức độ quan trọng: làm tài sản đệm trong giao dịch tiền mã hoá, làm tài sản bảo đảm trong tài chính phi tập trung, làm phương tiện lưu trữ giá trị bằng đô la ở các nước có lạm phát cao hoặc kiểm soát ngoại hối chặt, làm kênh thanh toán xuyên biên giới và kiều hối, và cuối cùng là thanh toán bán lẻ hàng ngày, vốn vẫn rất hạn chế.

### 3. Lợi ích tiềm năng

- Thanh toán xuyên biên giới và kiều hối là trường hợp có luận cứ mạnh nhất. Kênh truyền thống vẫn chậm, đắt và hoạt động theo giờ hành chính. Stablecoin hoạt động liên tục và có thể rẻ hơn ở một số hành lang chuyển tiền.
- Bài cẩn trọng nêu điều kiện: lợi ích này chỉ hiện thực hoá khi tính đến toàn bộ chi phí chuyển đổi vào và ra tiền pháp định ở hai đầu, chi phí tuân thủ, và rủi ro biến động trong thời gian nắm giữ. Khi tính đủ, lợi thế chi phí thu hẹp đáng kể ở nhiều hành lang.
- Các lợi ích khác gồm khả năng lập trình cho thanh toán có điều kiện, hoạt động liên tục, và tiềm năng bao trùm tài chính ở nơi hệ thống ngân hàng phủ sóng kém. Bài lưu ý rằng bao trùm tài chính đòi hỏi nhiều thứ hơn là một công cụ thanh toán, và rằng các giải pháp tiền di động đã đạt được nhiều điều tương tự mà không cần blockchain.

### 4. Tám nhóm rủi ro

- **Rút chạy hàng loạt.** Cấu trúc kinh tế giống quỹ thị trường tiền tệ: hứa mệnh giá cố định trong khi nắm giữ tài sản có giá biến động. Không có bảo hiểm tiền gửi và không có người cho vay cuối cùng.
- **Lan truyền sang thị trường tín phiếu kho bạc.** Khi quy mô dự trữ đủ lớn, việc bán tháo tín phiếu để đáp ứng làn sóng quy đổi có thể gây áp lực lên chính thị trường được coi là an toàn nhất, tạo kênh lây nhiễm từ tiền mã hoá sang tài chính truyền thống.
- **Phi trung gian hoá ngân hàng.** Tiền gửi rời khỏi ngân hàng làm giảm nguồn vốn cho tín dụng, tác động mạnh hơn ở các nước có hệ thống ngân hàng nhỏ.
- **Thay thế tiền tệ.** Ở các nước lạm phát cao, stablecoin đô la dễ tiếp cận qua điện thoại có thể đẩy nhanh và làm sâu sắc quá trình đô la hoá so với các đợt trước, làm suy yếu chính sách tiền tệ và thu phát hành tiền.
- **Lách quản lý dòng vốn.** Token di chuyển qua biên giới mà không đi qua hệ thống ngân hàng đại lý, nơi các biện pháp này vốn được thực thi.
- **Phân mảnh hệ thống thanh toán.** Nhiều loại stablecoin trên nhiều chuỗi không liên thông với nhau tạo nguy cơ quay lại tình trạng tiền ngân hàng tư nhân thế kỷ 19, khi mỗi loại giấy bạc giao dịch ở một mức chiết khấu khác nhau.
- **Tính toàn vẹn tài chính.** Chuyển giao ngang hàng, ví không lưu ký và bên phát hành đặt tại nơi quản lý lỏng tạo điều kiện cho rửa tiền và né trừng phạt.
- **Rủi ro pháp lý và vận hành.** Quyền của người nắm giữ khi bên phát hành phá sản chưa rõ ở nhiều nơi; lỗi hợp đồng thông minh và tấn công vào cầu nối chuỗi chéo đã gây tổn thất lớn trong thực tế.

### 5. Bốn khung quản lý

- **Nhật Bản** đi đầu bằng việc sửa Luật Dịch vụ Thanh toán, chỉ cho phép ngân hàng, công ty uỷ thác và nhà chuyển tiền được cấp phép phát hành. Cách tiếp cận này coi stablecoin về bản chất là tiền chứ không phải tài sản mã hoá, và yêu cầu dự trữ được tách biệt khỏi tài sản của bên phát hành.
- **Liên minh châu Âu** với quy định MiCA là khung toàn diện đầu tiên ở cấp khối. MiCA phân biệt token tiền điện tử neo vào một đồng tiền và token tham chiếu tài sản neo vào một giỏ. Điểm mạnh nhất là quyền quy đổi theo mệnh giá và miễn phí dành cho người nắm giữ. MiCA cũng áp quy tắc chặt hơn cho các token được xếp loại quan trọng và hạn chế việc dùng stablecoin ngoại tệ làm phương tiện thanh toán rộng rãi.
- **Hoa Kỳ** với Đạo luật GENIUS thiết lập con đường cấp phép ở cả cấp liên bang và cấp bang, yêu cầu dự trữ một đổi một bằng tài sản chất lượng cao và công bố hàng tháng. Một đặc điểm gây tranh luận là cấm trả lãi cho người nắm giữ, nhằm hạn chế cạnh tranh trực tiếp với tiền gửi ngân hàng.
- **Anh** áp dụng cách tiếp cận phân tầng, trong đó cơ quan FCA quản lý bên phát hành nói chung, còn Ngân hàng Anh giám sát riêng những loại đạt quy mô hệ thống và có thể áp hạn mức nắm giữ.
- Các khung này hội tụ ở bốn điểm: yêu cầu cấp phép, dự trữ chất lượng cao và tách biệt, quyền quy đổi rõ ràng, và công bố định kỳ. Chúng khác nhau ở chỗ ai được phép phát hành, có được trả lãi không, xử lý stablecoin ngoại tệ ra sao, và ngưỡng nào thì bị coi là có tầm quan trọng hệ thống.

### 6. Hàm ý chính sách

- Sự khác biệt giữa các khung tạo cơ hội arbitrage pháp lý, khi bên phát hành chọn nơi đăng ký có yêu cầu nhẹ nhất trong khi phục vụ người dùng toàn cầu. Bài kêu gọi phối hợp quốc tế về các yếu tố cốt lõi.
- Với các nền kinh tế mới nổi và đang phát triển, ưu tiên là bảo vệ chủ quyền tiền tệ. Các lựa chọn gồm cải thiện chính sách vĩ mô để giảm động cơ chuyển sang đô la, hiện đại hoá hệ thống thanh toán trong nước để cạnh tranh về tiện lợi, và cân nhắc các hạn chế trực tiếp, dù bài lưu ý rằng lệnh cấm khó thực thi.
- Bài kết luận rằng câu hỏi trung tâm không phải là công nghệ mà là cấu trúc: liệu một công cụ hứa hẹn ổn định mệnh giá có thể tồn tại bền vững ngoài mạng lưới an toàn của ngân hàng trung ương hay không. Lịch sử tiền tư nhân cho thấy câu trả lời thường là không.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Stablecoin | Token mã hoá được thiết kế để giữ giá trị ổn định so với một tài sản tham chiếu |
| Fiat-backed | Bảo chứng bằng tiền pháp định, loại chiếm áp đảo thị trường |
| Crypto-collateralized | Bảo chứng bằng tiền mã hoá, thường phải thế chấp vượt mức |
| Algorithmic stablecoin | Neo giá bằng cơ chế thuật toán, không có tài sản bảo chứng đầy đủ |
| Overcollateralization | Thế chấp vượt mức để chịu được biến động giá tài sản bảo đảm |
| Reserve assets | Tài sản dự trữ bảo chứng cho stablecoin đang lưu hành |
| Attestation | Chứng thực về dự trữ, phạm vi hẹp hơn kiểm toán đầy đủ |
| Redemption right | Quyền quy đổi token lấy tiền pháp định từ bên phát hành |
| Authorized participant | Đối tác được cấp phép, thường là bên duy nhất quy đổi trực tiếp được |
| De-pegging | Mất neo, giá thị trường lệch khỏi mệnh giá tham chiếu |
| Run risk | Rủi ro rút chạy hàng loạt khi người nắm giữ đồng loạt quy đổi |
| Fire sale | Bán tháo tài sản dự trữ dưới giá để đáp ứng làn sóng quy đổi |
| Disintermediation | Phi trung gian hoá, tiền gửi rời hệ thống ngân hàng |
| Currency substitution | Thay thế tiền tệ, người dân chuyển sang dùng đồng tiền nước khác |
| Seigniorage | Thu phát hành tiền của ngân hàng trung ương |
| CFM | Biện pháp quản lý dòng vốn |
| MiCA | Quy định của EU về Thị trường Tài sản Mã hoá |
| EMT | Token tiền điện tử theo MiCA, neo vào một đồng tiền pháp định |
| ART | Token tham chiếu tài sản theo MiCA, neo vào một giỏ tài sản |
| GENIUS Act | Đạo luật của Hoa Kỳ thiết lập khung cấp phép cho bên phát hành stablecoin |
| PSA | Luật Dịch vụ Thanh toán của Nhật Bản, sửa đổi để điều chỉnh stablecoin |
| Systemic stablecoin | Stablecoin đạt quy mô có tầm quan trọng hệ thống, bị giám sát chặt hơn |
| Regulatory arbitrage | Arbitrage pháp lý, chọn nơi đăng ký có yêu cầu nhẹ nhất |
| Wash trading | Giao dịch giả tạo khối lượng, một phần của lưu lượng bot |
| Cross-chain bridge | Cầu nối giữa các blockchain, điểm yếu an ninh đã bị khai thác nhiều lần |
| Free banking | Thời kỳ tiền ngân hàng tư nhân, mỗi loại giấy bạc giao dịch ở chiết khấu khác |

## Câu nói đáng nhớ

> "Stablecoins are not one thing. They are a family of instruments with very different risk profiles."

> "Headline transaction volumes overstate real payment use: an estimated 80 percent of on-chain activity is bot-driven."

> "A promise of par value backed by risky assets, without deposit insurance or a lender of last resort, is a familiar structure with a familiar history."

## Đánh giá và phát hiện đáng chú ý

### Tám mươi phần trăm là bot: con số đó không phải nhiễu cần lọc, nó là mô tả về bản chất của thị trường

Việc bài dám nêu thẳng rằng khoảng tám mươi phần trăm lưu lượng trên chuỗi là do bot tạo ra là một hành động làm sạch dữ liệu đáng giá, vì nó phá vỡ lập luận phổ biến nhất trong toàn bộ cuộc tranh luận: rằng stablecoin đã vượt các mạng thẻ về khối lượng. Con số đó là một sản phẩm thống kê, không phải một sự kiện kinh tế.

Nhưng bài dừng lại ở chỗ coi phần bot là nhiễu cần loại bỏ để nhìn ra "khối lượng thanh toán thực". Có một cách đọc khác, và có lẽ đúng hơn: **phần bot chính là hoạt động kinh doanh**. Stablecoin tồn tại chủ yếu như tài sản đệm và tài sản bảo đảm trong giao dịch tiền mã hoá, và đó không phải một giai đoạn quá độ đang chờ chuyển thành thanh toán — đó là công dụng đang nuôi sống quy mô ba trăm tỷ đô la.

Hệ quả của cách đọc này là một rủi ro không có trong danh sách tám nhóm của bài. Nếu quy mô stablecoin là **nội sinh với hoạt động thị trường tiền mã hoá** chứ không với nhu cầu thanh toán, thì khối lượng dự trữ — tức khối lượng tín phiếu kho bạc mà các bên phát hành nắm giữ — sẽ phình ra khi thị trường tiền mã hoá sôi động và co lại khi nó nguội.

Đây là một cơ chế **thuận chu kỳ**, và nó nguy hiểm hơn kênh lan truyền mà bài mô tả. Bài lo về việc bán tháo tín phiếu khi có làn sóng quy đổi hoảng loạn, tức một sự kiện hiếm. Cơ chế thuận chu kỳ thì không cần hoảng loạn: chỉ cần thị trường tiền mã hoá đi xuống là cung stablecoin co lại một cách bình thường, kéo theo việc bán tín phiếu ra. Và thị trường tiền mã hoá đi xuống thường trùng với những giai đoạn tâm lý né rủi ro chung — tức là việc bán tín phiếu xảy ra đúng lúc các bên khác cũng đang cần tiền mặt.

### Chín mươi bảy phần trăm neo vào đô la là một cánh cửa chỉ mở một chiều

Bài gọi đúng tên hiện tượng: đây là đô la hoá kỹ thuật số. Nhưng điều cần nhấn mạnh thêm là **hình thái đô la hoá này khác về bản chất với mọi đợt đô la hoá trước đó**, và khác theo hướng tệ hơn cho nước bị tác động.

Đô la hoá cổ điển đòi hỏi tiền giấy vật lý — cồng kềnh, cần buôn lậu hoặc cần hệ thống ngân hàng hợp tác — hoặc đòi hỏi tài khoản ngoại tệ tại một ngân hàng trong nước, tức đòi hỏi sự cho phép ngầm của cơ quan quản lý. Cả hai kênh đều có ma sát, và ma sát ấy chính là công cụ chính sách: chính quyền có thể siết hoặc nới.

Đô la hoá bằng stablecoin chỉ cần một chiếc điện thoại. Không cần ngân hàng trong nước hợp tác, không cần ai cấp phép, không cần tiền giấy qua biên giới. Ma sát gần như biến mất, và cùng với nó là công cụ chính sách.

Điều làm tình huống nghiêm trọng là **tính bất đối xứng**. Những gì đã biết về đô la hoá từ trước tới nay — và đây là một trong các kết quả vững chắc nhất trong kinh tế học tiền tệ — là hiện tượng này có quán tính rất mạnh: một khi giá cả, hợp đồng, tiền tiết kiệm và thói quen thanh toán đã chuyển sang ngoại tệ, chúng không tự quay lại ngay cả sau khi lạm phát đã được kiểm soát và ổn định vĩ mô đã được lập lại. Việc đi vào thì dễ chưa từng có, việc đi ra thì vẫn khó y như cũ.

Kết hợp hai đặc tính đó cho một kết luận về thời điểm hành động: đây là loại rủi ro phải xử lý **trước khi nó xảy ra**, vì sau khi xảy ra thì không còn công cụ hiệu quả. Và nó cũng có nghĩa là lập luận "hãy chờ xem quy mô có đủ lớn không rồi hãy quản" — một lập luận rất hợp lý với đa số rủi ro tài chính — lại là lập luận sai với đúng rủi ro này.

### Sự thật kỹ thuật quan trọng nhất bị chôn trong đặc tính thứ ba

Ở phần liệt kê bảy đặc tính, bài ghi một chi tiết dễ lướt qua: ở đa số stablecoin lớn, **chỉ các đối tác được cấp phép mới quy đổi trực tiếp được với bên phát hành**; người nắm giữ lẻ phải bán trên thị trường thứ cấp.

Chi tiết này thay đổi hoàn toàn bản chất của lời hứa "một đồng stablecoin bằng một đô la". Với người nắm giữ thông thường, cái neo đó không phải một quyền pháp lý mà là **một mức giá thị trường được duy trì bởi hoạt động kinh doanh chênh lệch giá**. Nó giữ được chừng nào việc kinh doanh chênh lệch giá còn có lãi và các đối tác được cấp phép còn sẵn sàng bỏ vốn ra làm.

Nhưng vốn dành cho kinh doanh chênh lệch giá là loại vốn rút lui sớm nhất khi thị trường căng thẳng — nó cần bảng cân đối, cần hạn mức rủi ro, và cần niềm tin rằng mức giá sẽ hội tụ. Đúng vào lúc cái neo cần được bảo vệ nhất thì lực bảo vệ nó yếu nhất. Đây là cùng một cấu trúc đã lộ ra ở các quỹ hoán đổi danh mục trái phiếu vào tháng 3/2020, khi giá thị trường lệch khỏi giá trị tài sản ròng đúng trong những ngày căng thẳng nhất.

Hệ quả cho bảo vệ người tiêu dùng rất trực tiếp và thường bị bỏ qua: gọi các công cụ này là "đô la số" là một mô tả **gây hiểu nhầm về mặt vật chất**, vì người nghe hiểu rằng mình có một khoản đòi nợ theo mệnh giá trong khi thực tế mình có một tài sản thị trường không có quyền đòi. Đây cũng là lý do điểm mạnh nhất trong bốn khung quản lý lại là điểm của châu Âu: quyền quy đổi theo mệnh giá và miễn phí **dành cho chính người nắm giữ**, chứ không chỉ cho các đối tác được cấp phép. Đó là điều khoản biến lời hứa thành nghĩa vụ.

### Bốn khung quản lý hội tụ ở phần ống nước và phân kỳ ở đúng phần quyết định

Bài nhận xét rằng bốn khung hội tụ ở cấp phép, chất lượng dự trữ, quyền quy đổi và công bố định kỳ, rồi phân kỳ ở việc ai được phát hành, có trả lãi không, xử lý stablecoin ngoại tệ ra sao, và ngưỡng nào là hệ thống. Bài coi phần phân kỳ là nguồn của arbitrage pháp lý và kêu gọi phối hợp quốc tế.

Nhưng hãy nhìn vào **nội dung** của sự phân kỳ, và một mô thức rõ ràng hiện ra. Hoa Kỳ cấm trả lãi — để bảo vệ tiền gửi ngân hàng trong nước. Châu Âu hạn chế stablecoin ngoại tệ làm phương tiện thanh toán rộng rãi — để bảo vệ đồng euro. Nhật Bản chỉ cho ngân hàng và tổ chức được cấp phép phát hành — để giữ việc tạo tiền trong hệ thống ngân hàng. Anh áp hạn mức nắm giữ với loại đạt quy mô hệ thống — để bảo vệ khả năng kiểm soát của ngân hàng trung ương.

Bốn điểm phân kỳ, bốn cách bảo vệ một lợi ích chủ quyền khác nhau. Đây **không phải sự khác biệt ngẫu nhiên** do các nước chưa kịp bàn với nhau. Đó là kết quả của việc mỗi tài phán nội hoá đúng mối lo lớn nhất của mình.

Từ đó suy ra hai điều mà bài không nói. Thứ nhất, lời kêu gọi phối hợp quốc tế sẽ thành công ở phần ống nước — nơi mọi người đã đồng ý — và sẽ thất bại ở đúng bốn điểm quan trọng nhất, vì mỗi nước sẽ không nhượng bộ ở điểm chạm vào chủ quyền tiền tệ của mình. Thứ hai, và hữu dụng hơn: **mỗi điểm phân kỳ là một mẫu thiết kế có thể mượn**, và nước nào nên mượn mẫu nào thì tuỳ vào mối lo nào là mối lo của mình.

Điều này nối với một quan sát lịch sử mà bài nêu ra rồi bỏ dở. Bài so sánh nguy cơ phân mảnh với thời kỳ tiền ngân hàng tư nhân thế kỷ mười chín, khi mỗi loại giấy bạc giao dịch ở một mức chiết khấu khác nhau. Nhưng bài không kể phần kết: tình trạng đó không chấm dứt vì cạnh tranh thị trường chọn ra người thắng, mà vì nhà nước **tạo ra một đồng tiền quốc gia thống nhất và đánh thuế giấy bạc tư nhân tới mức chúng biến mất**. Giải pháp lịch sử cho sự phân mảnh tiền tư nhân là một hành động chủ quyền bằng pháp luật, không phải một kết quả của thị trường. Điều đó gợi ý khá mạnh rằng hồi kết của chuyện stablecoin cũng sẽ được quyết định bằng luật, và cách châu Âu đang làm chính là phiên bản hiện đại của cùng động tác đó.

### Với Việt Nam: đây là bài về rủi ro thứ tư và thứ năm, không phải về tám rủi ro

Trong tám nhóm rủi ro mà bài liệt kê, phần lớn không phải rủi ro của Việt Nam. Rủi ro rút chạy hàng loạt và rủi ro lan truyền sang thị trường tín phiếu kho bạc là rủi ro của hệ thống tài chính Hoa Kỳ, nơi dự trữ được đầu tư. Rủi ro phi trung gian hoá ngân hàng chỉ nghiêm trọng khi người dân có thể giữ số dư lớn bằng stablecoin một cách hợp pháp và tiện lợi.

Hai rủi ro thực sự chạm tới Việt Nam là rủi ro thứ tư, **thay thế tiền tệ**, và rủi ro thứ năm, **lách quản lý dòng vốn**. Và chúng chạm mạnh, vì hồ sơ của Việt Nam khớp gần như hoàn hảo với điều kiện sinh ra cả hai: mức phổ cập tiền mã hoá trong dân cư nhiều năm liền thuộc nhóm cao nhất thế giới theo các chỉ số quốc tế; tài khoản vốn chưa tự do hoá và giao dịch ngoại hối của cá nhân bị hạn chế; một lịch sử dài người dân tự phòng vệ giá trị tài sản bằng vàng và đô la mỗi khi có bất ổn; và một dòng kiều hối rất lớn tạo sẵn thói quen giao dịch xuyên biên giới ở cấp hộ gia đình.

Đặt trong khung của bài, điều đó có nghĩa là **kênh ma sát mà quản lý ngoại hối dựa vào đã bị vòng qua**. Các biện pháp quản lý dòng vốn được thực thi tại hệ thống ngân hàng đại lý; token chuyển từ ví sang ví không đi qua đó. Đây không còn là một rủi ro lý thuyết mà là một mô tả về hiện trạng.

Và chính bài đã nói ra điều làm cho lựa chọn chính sách trở nên hẹp: **lệnh cấm khó thực thi**. Khi mức phổ cập đã cao trong điều kiện chưa có khuôn khổ pháp lý, đó là bằng chứng thực nghiệm rằng việc ngăn chặn bằng cách không thừa nhận đã không hiệu quả. Lựa chọn thực tế vì vậy không phải giữa chấp nhận và cấm, mà giữa **một dòng chảy được nhìn thấy và một dòng chảy không được nhìn thấy**.

Nếu phải chọn một mẫu thiết kế trong bốn mẫu, mẫu của châu Âu là mẫu gần nhất với mối lo của Việt Nam, vì nó là mẫu duy nhất trong bốn mẫu **nhắm thẳng vào rủi ro thay thế tiền tệ** chứ không phải vào rủi ro ổn định tài chính. Cấu trúc của nó gồm ba phần đi cùng nhau: thừa nhận và cấp phép để có dữ liệu và có điểm thực thi; hạn chế riêng việc dùng stablecoin ngoại tệ làm phương tiện thanh toán rộng rãi trong nước; và song song đó hiện đại hoá hệ thống thanh toán nội tệ để cạnh tranh về tiện lợi thay vì chỉ cạnh tranh bằng lệnh cấm. Phần thứ ba là phần quan trọng nhất và cũng là phần Việt Nam đã làm tốt nhất — chuyển khoản tức thời và quét mã phủ rộng đã loại bỏ phần lớn lý do tiện lợi để người dân tìm tới một công cụ thanh toán khác.

Điều còn lại chưa được xử lý là lý do thứ hai khiến người ta tìm tới stablecoin, và nó không phải tiện lợi mà là **mong muốn giữ giá trị bằng đô la**. Với lý do đó, không có cải tiến thanh toán nào chạm tới được. Chỉ có ổn định vĩ mô, lạm phát thấp và một mức lợi tức thực dương trên tiết kiệm bằng nội tệ mới cạnh tranh được — đúng như kết luận cổ điển về đô la hoá, chỉ là lần này thời gian để hành động ngắn hơn nhiều.

# Financial Integrity Implications of Retail Central Bank Digital Currencies (rCBDCs) — Tác động của tiền số ngân hàng trung ương bán lẻ tới tính toàn vẹn tài chính

**Nguồn:** IMF Fintech Note NOTE/2025/010, do Nhóm Tính toàn vẹn Tài chính thuộc Vụ Pháp lý IMF thực hiện, tài trợ bởi Quỹ Chuyên đề AML/CFT của IMF.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 7, không có trang bìa và trang tác giả).
**Ý chính:** Tính đến 2025 gần như mọi quốc gia đều đã hoặc đang khám phá tiền số ngân hàng trung ương bán lẻ (rCBDC), nhưng chỉ ba nước đã phát hành thật. Bài phân tích các lựa chọn thiết kế rCBDC dưới lăng kính chống rửa tiền và chống tài trợ khủng bố, đối chiếu với 40 Khuyến nghị của FATF. Kết luận cốt lõi: rủi ro không nằm ở bản thân công nghệ mà ở từng lựa chọn thiết kế, và 18 trên 40 Khuyến nghị được đánh giá là khó áp dụng ở mức trung bình hoặc đáng kể.

> **Lưu ý:** bản PDF bắt đầu từ trang 7 (phần Giới thiệu). Trang bìa, tóm tắt và danh sách tác giả không có trong bản này. Tên bài và số hiệu lấy từ trang bìa sau.

## Sơ đồ

### Bối cảnh và mục đích của tài liệu

```text
       TÌNH HÌNH rCBDC TOÀN CẦU tính đến 2025
       · ĐÃ PHÁT HÀNH (3 nước): Bahamas (Sand Dollar), Jamaica
         (Jam-Dex), Nigeria (eNaira) — quy mô người dùng TƯƠNG ĐỐI NHỎ
       · ĐANG THÍ ĐIỂM: Trung Quốc (e-CNY), Ghana (e-Cedi), Ấn Độ
         (Digital Rupee), Kazakhstan (Digital Tenge), Türkiye, và một
         khối khu vực là Liên minh Tiền tệ Đông Caribe (DCash)
         → một số thí điểm tới HÀNG TRIỆU người dùng (Trung Quốc, Ấn Độ)
       · NGHIÊN CỨU NÂNG CAO: EU, Indonesia, Maroc, Thuỵ Điển, UAE, Anh
       · TẠM DỪNG hoặc CHẤM DỨT: Canada, Ecuador
                                │
                                ▼
       VÌ SAO PHẢI LO VỀ TÍNH TOÀN VẸN TÀI CHÍNH?
       · rCBDC cũng như mọi loại tài sản khác, CÓ THỂ BỊ LỢI DỤNG để
         rửa tiền (ML), tài trợ khủng bố (TF), tài trợ phổ biến vũ khí
         huỷ diệt hàng loạt (PF)
       · ÍT NHẤT MỘT nước phát hành ĐÃ PHÁT HIỆN vụ lạm dụng hình sự
         (Trung Quốc, vụ rửa tiền bằng nhân dân tệ số, 2022)
       · nếu được ÁP DỤNG RỘNG RÃI, rCBDC có thể tác động ĐÁNG KỂ tới
         tính toàn vẹn của hệ thống tài chính TOÀN CẦU
                                │
                                ▼
       CHUẨN MỰC ĐỐI CHIẾU: Ban Điều hành IMF đã thông qua BỘ CHUẨN
       FATF (40 Khuyến nghị, Ghi chú Diễn giải và Bảng Thuật ngữ) làm
       chuẩn cho công tác AML/CFT của Quỹ
       · FATF (2020) khẳng định chuẩn của mình "áp dụng cho CBDC TƯƠNG
         TỰ như mọi hình thái tiền pháp định khác do ngân hàng trung
         ương phát hành"
       · NHƯNG tại thời điểm soạn thảo, CHƯA có cơ quan đánh giá nào
         từng đánh giá hiệu quả AML/CFT của một nước đã phát hành hay
         thí điểm rCBDC, và tài liệu học thuật còn RẤT ÍT
       → nhiều nước đã tìm tới Vụ Pháp lý IMF xin hỗ trợ kỹ thuật
                                │
                                ▼
       MỤC ĐÍCH KÉP CỦA TÀI LIỆU
       ① HƯỚNG DẪN nhà hoạch định chính sách và cơ quan có thẩm quyền
         về cách triển khai chuẩn AML/CFT quốc tế trong bối cảnh rCBDC
       ② LÀM NỔI BẬT những khía cạnh của chuẩn AML/CFT CẦN SUY NGHĨ THÊM
       · tài liệu KHÔNG đại diện cho quan điểm của FATF và không nhằm
         đoán trước quan điểm đó
```

### Bảy đặc điểm thiết kế quan trọng với AML/CFT

```text
       ❶ BÁN LẺ so với BÁN BUÔN
       · rCBDC phân phối cho ĐẠI CHÚNG, dùng cho thanh toán HÀNG NGÀY;
         cả ba CBDC đã phát hành đầy đủ đều là bán lẻ
       · wCBDC phân phối cho MỘT SỐ tổ chức tài chính được chọn, dùng
         để quyết toán giao dịch GIÁ TRỊ LỚN
       → hai hướng KHÔNG loại trừ nhau; một số nước theo đuổi CẢ HAI
         (Israel, UAE) · chuẩn AML/CFT toàn cầu chủ yếu nhắm vào hoạt
         động NGÂN HÀNG BÁN LẺ, nên bài tập trung vào rCBDC
                                │
                                ▼
       ❷ DỰA TRÊN TOKEN so với DỰA TRÊN TÀI KHOẢN
       · TOKEN: vật mang giá trị nội tại, giống công cụ VÔ DANH kỹ
         thuật số · sở hữu chứng minh bằng VIỆC NẮM GIỮ, chuyển giao
         không cần trung gian · ví dụ cổ điển là TIỀN MẶT · đến nay
         CHƯA nước nào theo đuổi nghiêm túc mô hình token thuần tuý
       · TÀI KHOẢN: tạo quyền và nghĩa vụ trên tài khoản người dùng,
         dựa vào BÊN THỨ BA giữ sổ sách khách quan · ví dụ là tài
         khoản ngân hàng
       → trên thực tế sự phân biệt này KHÁ HỌC THUẬT: hầu hết thiết kế
         KẾT HỢP cả hai (e-CNY là công cụ lai, chuyển nhượng kiểu token
         nhưng kiểm soát kiểu tài khoản)
                                │
                                ▼
       ❸ PHƯƠNG THỨC PHÂN PHỐI: TRỰC TIẾP so với GIÁN TIẾP
       · TRỰC TIẾP (một tầng, không trung gian): ngân hàng trung ương
         tự phân phối tới người dùng cuối, TỰ mở và quản lý ví/tài
         khoản, đảm nhận vai trò TIẾP XÚC KHÁCH HÀNG
       · GIÁN TIẾP (hai tầng, có trung gian): ngân hàng trung ương phát
         cho các trung gian được xác định (thường là ngân hàng, có thể
         là tổ chức tài chính phi ngân hàng hoặc cả tổ chức phi tài
         chính) · người dùng mở tài khoản với trung gian
       · ĐIỂM TINH TẾ: theo nguyên tắc được thừa nhận rộng rãi, CBDC
         "thật" phải là NGHĨA VỤ trên bảng cân đối của ngân hàng trung
         ương → trung gian KHÔNG nắm giữ tài khoản khách hàng về mặt
         pháp lý, mà chỉ là LỚP TIẾP XÚC KHÁCH HÀNG
       → MỌI thăm dò rCBDC đến nay đều theo một dạng có trung gian;
         KHÔNG ngân hàng trung ương nào theo đuổi nghiêm túc mô hình
         phân phối trực tiếp không trung gian
                                │
                                ▼
       ❹ TẬP TRUNG so với PHI TẬP TRUNG · ❺ SỔ CÁI CÓ PHÉP so với
       KHÔNG PHÉP · ❻ TRONG NƯỚC so với XUYÊN BIÊN GIỚI · ❼ CHỨC NĂNG
       NGOẠI TUYẾN và TÍNH RIÊNG TƯ
       · cả ba rCBDC đã phát hành và mọi mô hình tại bàn tròn đều là
         hệ thống CÓ PHÉP (permissioned)
       · đến nay CHƯA hệ thống KHÔNG PHÉP hoàn toàn nào được theo đuổi
         nghiêm túc
       · tính đến 2025, MỌI thí điểm và phát hành rCBDC đều ĐƠN PHƯƠNG
         và chỉ thiết kế cho sử dụng TRONG NƯỚC
       · CHƯA nước nào theo đuổi hệ thống NGOẠI TUYẾN HOÀN TOÀN (payer
         và payee ở ngoại tuyến vô thời hạn), do lo ngại CHI TIÊU HAI
         LẦN và tính toàn vẹn tài chính
       · MỌI thăm dò đều có MỘT DẠNG bảo vệ riêng tư, NHƯNG đến nay
         CHƯA nước nào theo đuổi rCBDC ẨN DANH HOÀN TOÀN, bất kể tên
         gọi của đồng tiền gợi ý điều gì
```

### Ba điểm nghẽn lớn nhất khi áp dụng chuẩn FATF

```text
       ❶ CẤM TÀI KHOẢN ẨN DANH (Khuyến nghị 10)
       · R.10 CẤM tổ chức tài chính duy trì tài khoản ẩn danh
       · HAI khái niệm phải làm rõ: (i) "ẩn danh" — FATF không định
         nghĩa rõ, nhưng trọng tâm là việc CỐ Ý che giấu hoặc xuyên tạc
         danh tính để tránh bị phát hiện; (ii) "tài khoản" — Bảng Thuật
         ngữ FATF không định nghĩa, chỉ nói bao gồm "các quan hệ kinh
         doanh tương tự", hàm ý phải có QUAN HỆ KHÁCH HÀNG
       · VẤN ĐỀ: các tính năng bảo vệ riêng tư CÓ THỂ XUNG ĐỘT với lệnh
         cấm này · hệ thống rCBDC thiết kế "giống tiền mặt" và không
         yêu cầu định danh bởi trung gian thì RẤT KHÓ thoả mãn ngay cả
         yêu cầu CDD ĐƠN GIẢN HOÁ nhất
       · GIẢI PHÁP thẳng thắn là cho phép giao dịch NGANG HÀNG thật sự
         (ví không lưu ký), NHƯNG đến nay CHƯA nước nào theo đuổi
       → ĐIỀU KIỆN TỐI THIỂU: để mô hình phân tầng thoả mãn CDD đơn
         giản hoá, ở tầng cơ bản nhất người dùng ít nhất phải TỰ KHAI
         TÊN của mình
                                │
                                ▼
       ❷ TRỪNG PHẠT TÀI CHÍNH CÓ MỤC TIÊU — TFS (Khuyến nghị 6 và 7)
       · khác mọi nghĩa vụ AML/CFT khác, TFS áp dụng cho MỌI NGƯỜI
         trong một nước (không chỉ đơn vị báo cáo) và MỌI giao dịch với
         BẤT KỲ loại tài sản nào
       · TFS gắn chặt với TÊN, bí danh và định danh của người bị chỉ
         định → RẤT KHÓ triển khai với mô hình cho phép người dùng ẩn
         danh hoặc chỉ định danh bằng bí danh không gắn danh tính thật
       · THỜI ĐIỂM SÀNG LỌC: FATF yêu cầu phong toả "KHÔNG CHẬM TRỄ"
         · nếu không giới hạn chặt thời gian ví được ở ngoại tuyến, một
         khoảng thời gian ĐÁNG KỂ có thể trôi qua trước khi trung gian
         phát hiện giao dịch bất hợp pháp
       · GIAO DỊCH NGOẠI TUYẾN: sàng lọc trên thực tế CHỈ diễn ra khi
         thiết bị kết nối lại · phát hiện HẬU KIỂM tuy tốt hơn không
         phát hiện, NHƯNG không NGĂN được giao dịch đã xảy ra
       · GIẢI PHÁP: triển khai TFS CHUNG giữa các nhà cung cấp dịch vụ
         — ví dụ nếu mô hình phân tầng gắn với SỐ ĐIỆN THOẠI, có thể
         xây khung buộc nhà mạng thông báo NGAY cho tổ chức tài chính
         khi trúng danh sách trừng phạt · LƯU Ý: tổ chức tài chính VẪN
         chịu trách nhiệm nếu nhà mạng không phát hiện được
       · LO NGẠI SÂU XA: lập luận chính cho hiệu quả của TFS là nó CẮT
         ĐỨT khủng bố khỏi hệ thống tài chính CHÍNH THỨC, buộc chúng
         dùng cách chậm hơn, đắt hơn, kém an toàn hơn · nếu rCBDC cho
         phép ví không định danh, xác suất LÁCH TRỪNG PHẠT qua kênh
         chính thức có thể TĂNG, làm tăng rủi ro TF
                                │
                                ▼
       ❸ MÔ HÌNH TRỰC TIẾP và VAI TRÒ MỚI CỦA NGÂN HÀNG TRUNG ƯƠNG
       · nếu ngân hàng trung ương thực hiện MỘT trong 13 hoạt động
         trong định nghĩa "tổ chức tài chính" của FATF, "VỚI TƯ CÁCH
         MỘT DOANH NGHIỆP", nó phải chịu TOÀN BỘ nghĩa vụ AML/CFT
       · CÂU HỎI MẤU CHỐT: hoạt động của ngân hàng trung ương — một cơ
         quan CÔNG — có được coi là mang tính THƯƠNG MẠI không?
       · một số ngân hàng trung ương ĐÃ có hoạt động bán lẻ nhỏ lẻ (mua
         bán tiền xu, tiền giấy, phát hành chứng khoán) nhưng thường
         KHÔNG bị coi là đơn vị báo cáo (ví dụ Ngân hàng Dự trữ Nam Phi,
         Ngân hàng Jamaica)
       · BA THÁCH THỨC GIÁM SÁT nếu điều đó xảy ra:
         (i) XUNG ĐỘT LỢI ÍCH — nhất là khi cơ quan giám sát AML/CFT
             NẰM TRONG chính ngân hàng trung ương; căng thẳng giữa thúc
             đẩy bao trùm tài chính và đổi mới với chống tội phạm tài
             chính · giải pháp: khung quản trị rõ ràng, tách bộ phận
             riêng hoặc đơn vị có tường lửa, như cách một số FIU được
             đặt trong ngân hàng trung ương
         (ii) ĐỘC LẬP CỦA NGÂN HÀNG TRUNG ƯƠNG — nếu trở thành đơn vị
             báo cáo, nó phải chịu giám sát AML/CFT KỂ CẢ việc bị áp
             chế tài · ở nước có nhà nước pháp quyền yếu và tham nhũng
             phổ biến, chế tài có thể trở thành công cụ TRẢ ĐŨA và gây
             áp lực chính trị · nhiều chế độ pháp lý trong nước KHÔNG
             cho phép loại giám sát này
         (iii) NẾU KHÔNG THỂ áp chế tài lên ngân hàng trung ương trong
             mô hình trực tiếp, thì yêu cầu của KHUYẾN NGHỊ 27 KHÔNG
             THỂ được thoả mãn
```

## Ba câu hỏi bài viết trả lời

1. Những lựa chọn thiết kế nào của rCBDC ảnh hưởng tới rủi ro rửa tiền và tài trợ khủng bố?
2. Áp dụng 40 Khuyến nghị của FATF vào rCBDC gặp khó ở đâu, và khó tới mức nào?
3. Các nước nên làm gì trước khi phát hành, và câu hỏi nào còn bỏ ngỏ cho cộng đồng quốc tế?

## Dàn ý chi tiết

### 1. Vì sao cần bàn về rCBDC và tính toàn vẹn tài chính

- Ngân hàng trung ương đang đổi mới và hiện đại hoá hệ thống thanh toán cũ, nổi bật là qua tiền số ngân hàng trung ương. Tuy chưa có định nghĩa phổ quát, khái niệm này thường được hiểu là một hình thái số của tiền ngân hàng trung ương. CBDC khác với tiền điện tử (e-money, thường do tổ chức tài chính phi ngân hàng phát hành) và tài sản ảo (do tư nhân phát hành).
- Việc triển khai hiệu quả các chuẩn quốc tế liên quan là cần thiết để bảo đảm rCBDC không làm suy giảm tính toàn vẹn tài chính. Như mọi loại tài sản khác, rCBDC có thể bị lợi dụng cho rửa tiền, tài trợ khủng bố, tài trợ phổ biến vũ khí và các tội phạm tài chính khác. Ít nhất một nước phát hành đã phát hiện trường hợp lạm dụng hình sự.
- Bài phân tích việc áp dụng Bộ chuẩn FATF trong bối cảnh rCBDC và nêu bật các lĩnh vực cần thảo luận thêm. Tại thời điểm soạn thảo, thực tiễn và hướng dẫn về việc triển khai chuẩn FATF trong bối cảnh này còn rất hạn chế, khiến nhiều nước tìm tới Vụ Pháp lý IMF xin hỗ trợ kỹ thuật.
- Phân tích dựa trên các lựa chọn thiết kế rCBDC và Bộ chuẩn FATF tại một thời điểm cụ thể. Các thăm dò CBDC có thể thay đổi mạnh, và Bộ chuẩn FATF cũng tiếp tục tiến hoá để thích ứng với bối cảnh tài chính và các hình thái rửa tiền mới.

### 2. Bảy đặc điểm thiết kế quan trọng

- **Bán lẻ và bán buôn.** rCBDC phân phối cho đại chúng để thanh toán hàng ngày; wCBDC phân phối cho một số tổ chức tài chính được chọn để quyết toán giao dịch giá trị lớn. Hai hướng không loại trừ nhau. Bài tập trung vào rCBDC vì chuẩn AML/CFT toàn cầu chủ yếu nhằm ngăn rửa tiền qua hoạt động ngân hàng bán lẻ, chứ không phải các hoạt động như cho vay liên ngân hàng vốn đã qua các biện pháp AML/CFT.
- **Dựa trên token và dựa trên tài khoản.** Trên thực tế sự phân biệt này khá học thuật. Hầu hết thiết kế CBDC kết hợp đặc điểm của cả hai mô hình, dùng xác thực an toàn để ngăn chi tiêu hai lần (như hệ thống token), đồng thời ghi số dư và cho phép quản lý tài khoản (như hệ thống tài khoản). Mọi thí điểm nâng cao và phát hành đều mang cả hai đặc điểm.
- **Phương thức phân phối.** Mọi thăm dò rCBDC đến nay đều theo một dạng hệ thống có trung gian. Người tham gia bàn tròn áp đảo chọn mô hình gián tiếp, dù không có hai nước nào có cách tiếp cận giống hệt nhau về hạ tầng sổ cái, loại trung gian và vai trò của các bên trong hệ sinh thái. Bản chất trung gian hoá rất khác nhau: ngân hàng trung ương có thể giữ toàn bộ sổ cái và ghi giao dịch bán lẻ, hoặc chỉ giữ sổ cái bán buôn với các trung gian giữ sổ phụ. Một số đang khám phá khả năng cho nhiều trung gian tương tác với cùng một tài khoản khách hàng do ngân hàng trung ương nắm giữ về mặt pháp lý (dự án Sela).
- **Tập trung và phi tập trung.** Hệ thống tập trung do ngân hàng trung ương kiểm soát hoàn toàn; hệ thống phi tập trung phân tán việc duy trì sổ cái và xác thực giao dịch qua nhiều nút. Nhiều mức độ có thể cùng tồn tại trong một mô hình. Đa số người tham gia bàn tròn nghiêng về hệ thống tập trung.
- **Truy cập sổ cái và công nghệ.** Ba rCBDC đã phát hành và mọi mô hình tại bàn tròn đều là hệ thống có phép. Có thể kết hợp truy cập hạn chế và không hạn chế ở các phần khác nhau của cùng một sổ cái, ví dụ lớp tài sản có phép còn lớp dịch vụ (lớp giao diện lập trình ứng dụng) không phép.
- **Trong nước và xuyên biên giới.** Tính đến 2025, mọi thí điểm và phát hành rCBDC đều đơn phương và chỉ thiết kế cho sử dụng trong nước. Các thăm dò về chức năng xuyên biên giới có tồn tại nhưng còn sơ khai. Kiến trúc xuyên biên giới gồm nền tảng chung một đồng tiền (DCash, đồng euro số) và các thoả thuận đa tiền tệ (nền tảng liên kết như dự án Icebreaker, hoặc nền tảng chung).
- **Chức năng ngoại tuyến.** Thanh toán ngoại tuyến là chuyển giá trị giữa các thiết bị không cần kết nối tới bất kỳ hệ thống sổ cái nào. Động cơ gồm khả năng chống chịu, bao trùm tài chính, mang lại lựa chọn giống tiền mặt và bảo vệ riêng tư. Chưa nước nào theo đuổi hệ thống ngoại tuyến hoàn toàn.
- **Tính năng bảo vệ riêng tư.** Mức độ riêng tư là một đặc tính có thể lập trình. Hai mục tiêu chính là riêng tư trước người quản trị sổ cái (đa số chọn sổ cái bí danh, thông tin định danh do trung gian giữ riêng) và riêng tư khi giao dịch (hệ thống phân tầng với tầng thấp nhất yêu cầu định danh tối thiểu hoặc không yêu cầu). Điểm quan trọng cần nhớ là chuẩn so sánh trong giao dịch tài chính không phải là riêng tư tuyệt đối: tổ chức tài chính vốn đã thường xuyên giám sát và phân tích hành vi khách hàng.

### 3. Áp dụng chuẩn FATF: nơi dễ, nơi khó

- Phần lớn Bộ chuẩn FATF sẽ được triển khai trong bối cảnh rCBDC một cách thẳng thắn và giống hệt như với tiền truyền thống. Ví dụ, hình phạt hình sự cho rửa tiền liên quan CBDC cần hiệu quả, tương xứng và có tính răn đe đúng như với mọi tài sản khác.
- **Đánh giá rủi ro (R.1 và R.15).** FATF cảnh báo rủi ro phải được xử lý theo hướng nhìn về phía trước, trước khi phát hành bất kỳ CBDC nào. Việc giảm thiểu rủi ro nên do chính người phát hành CBDC dẫn dắt. So với sản phẩm khác, đánh giá rủi ro rCBDC có thể phức tạp hơn do tính mới của hệ thống.
- **So sánh rủi ro (Bảng 2).** rCBDC có tính ẩn danh từ thấp đến cao (ẩn danh quy mô lớn ít khả năng xảy ra theo các thăm dò hiện tại), khả năng chuyển đổi sang tài sản khác cao, phạm vi địa lý tuỳ thiết kế, tốc độ và tính di động cao. Về giảm thiểu, rCBDC có truy vết mạnh, hạn mức giao dịch mạnh, CDD mạnh, lưu trữ hồ sơ mạnh, giám sát giao dịch mạnh. Đối chiếu, tiền mặt có ẩn danh cao và mọi biện pháp giảm thiểu đều yếu.
- **Biện pháp phòng ngừa.** Mọi chủ thể trong hệ sinh thái CBDC đáp ứng định nghĩa tổ chức tài chính, nhà cung cấp dịch vụ tài sản ảo hoặc doanh nghiệp phi tài chính được chỉ định đều phải chịu nghĩa vụ AML/CFT. Nơi nhà cung cấp ví chỉ cung cấp phần mềm thì có thể không đáp ứng định nghĩa nào cả; nơi nhà mạng viễn thông được giao thực hiện chức năng tuân thủ thay tổ chức tài chính thì trách nhiệm cuối cùng vẫn thuộc về tổ chức tài chính thuê ngoài.
- **CDD đơn giản hoá và miễn trừ.** Cần phân biệt giữa xác định khách hàng và xác minh danh tính. CDD đơn giản hoá không có nghĩa là miễn trừ hoàn toàn, mà là cách tiếp cận được hiệu chỉnh tương xứng với rủi ro. Trong tình huống rủi ro thấp, xác định có thể dựa vào các hình thức định danh thay thế (chứng minh hết hạn, thẻ thuế), còn xác minh có thể trì hoãn. Vấn đề hiện nay là việc xác định hạn mức nắm giữ và giao dịch phù hợp thường không dựa trên bất kỳ đánh giá rủi ro nào.
- **Dựa vào bên thứ ba và thuê ngoài (R.17).** Trong kịch bản dựa vào bên thứ ba, bên đó tự có nghĩa vụ AML/CFT và chịu quản lý giám sát. Trong kịch bản thuê ngoài, bên nhận việc không có nghĩa vụ AML/CFT nên phải làm theo chỉ dẫn và quy trình của tổ chức tài chính uỷ quyền. Trong cả hai trường hợp, trách nhiệm cuối cùng vẫn thuộc về đơn vị báo cáo.
- **Minh bạch thanh toán (R.16).** Với mô hình mà thông tin đã có sẵn trên sổ cái và các bên trong chuỗi thanh toán đều truy cập được, có thể không cần truyền riêng. Nhưng vì đa số sổ cái được thiết kế bí danh, thông tin CDD thường không nằm trên sổ cái, nên thông tin bắt buộc vẫn phải do trung gian khởi tạo gửi cho trung gian nhận.
- **Lưu trữ hồ sơ (R.11).** Trong bối cảnh rCBDC, thông tin liên quan CDD có thể gồm các định danh số như khoá công khai hoặc địa chỉ ví, vốn có chức năng tương tự số tài khoản. Nếu ngân hàng trung ương giữ toàn bộ sổ cái trong khi trung gian chỉ thấy bản sao của ví khách hàng, câu hỏi đặt ra là liệu lỗi lưu trữ hồ sơ (ví dụ sổ cái trục trặc) có bị quy cho trung gian hay không.
- **Giám sát giao dịch và báo cáo giao dịch đáng ngờ (R.20).** Phương pháp giám sát trong mô hình có trung gian nhiều khả năng giống thực tiễn hiện nay. Khó khăn nảy sinh ở mô hình trực tiếp, ví cơ bản với thông tin hạn chế, và chức năng ngoại tuyến. Chính các ngân hàng trung ương xác định rủi ro liên quan chức năng ngoại tuyến là trong nhóm đáng kể nhất.
- **Thực thi hình sự.** Phong toả, tịch thu tài sản số và dừng hoặc đảo ngược giao dịch có thể đòi hỏi quyền truy cập trực tiếp vào sổ cái và thẩm quyền can thiệp vào hoạt động ví. Trong hệ thống phi tập trung hoàn toàn, cơ quan có thẩm quyền có rất ít khả năng kiểm soát sổ cái. Nơi cơ quan thực thi pháp luật được trao quyền trực tiếp trên sổ cái, cần có các biện pháp bảo vệ để bảo đảm đúng quy trình tố tụng.

### 4. Cơ hội mà rCBDC mang lại cho tuân thủ

- Một sổ cái CBDC thống nhất, không bị phân mảnh, có thể nâng cao giám sát giao dịch bằng cách mở rộng tập thông tin sẵn có, từ thông tin do từng tổ chức nắm giữ lên toàn bộ giao dịch trên sổ cái của ngân hàng trung ương.
- Cơ quan có thẩm quyền truy cập trực tiếp sổ cái thống nhất có thể tự phân tích để phát hiện giao dịch và mẫu hình đáng ngờ kịp thời, không phải chờ báo cáo từ trung gian. Nếu cần, họ có thể xin thêm thông tin định danh chủ ví từ trung gian liên quan.
- Cấu trúc lưu trữ hồ sơ của rCBDC có thể cải thiện quy trình CDD và tinh giản việc chia sẻ dữ liệu bằng cách giảm trùng lặp, chẳng hạn qua việc dùng một token "biết khách hàng của bạn". Tuy nhiên chất lượng dữ liệu nền là mấu chốt: nơi chế độ CDD kém, việc chia sẻ thông tin sai lệch không cải thiện được gì.
- Số hoá giao dịch có thể mở đường cho việc tự động hoá một số yêu cầu AML/CFT, ví dụ viết yêu cầu quy định trực tiếp vào hợp đồng thông minh. Tuy nhiên bài nhấn mạnh các cơ chế tuân thủ theo thiết kế không phải liều thuốc thần: những sáng kiến tương tự như chế độ định danh khách hàng điện tử đã được theo đuổi cho dịch vụ thanh toán hiện có mà chưa chứng minh được hiệu quả trong mọi trường hợp, và các giải pháp này không được IMF chứng thực.

### 5. Kết quả khảo sát bàn tròn tháng 1/2025

- Bàn tròn ảo do Vụ Pháp lý IMF tổ chức, có đại diện ngân hàng trung ương và cơ quan liên quan từ 14 nước và khối khu vực, cùng đại diện các vụ khác của IMF và Ban Thư ký FATF. Các nước tham gia gồm Bahamas, Trung Quốc, Ngân hàng Trung ương Đông Caribe, ECB, Ghana, Hong Kong SAR, Nhật Bản, Kazakhstan, Maroc, New Zealand, Nigeria, Thuỵ Điển, Türkiye và một nước không nêu tên.
- **Mô hình phân phối:** 93% theo mô hình gián tiếp có trung gian, 7% chưa quyết.
- **Trung gian:** một nửa chỉ cho phép tổ chức tài chính, hơn một phần ba dự kiến hỗn hợp tổ chức tài chính và phi tài chính, 14% chưa quyết. Một số bày tỏ cởi mở với trung gian như nhà mạng viễn thông vốn không có trách nhiệm AML/CFT truyền thống nhưng tiếp cận được lượng khách hàng lớn.
- **Trách nhiệm AML/CFT:** 93% giao cho trung gian khu vực tư nhân, 7% chưa quyết.
- **Hạ tầng sổ cái:** 36% sổ cái phân tán, 29% sổ cái tập trung, 28% chưa quyết, 7% lai. Không nước nào thăm dò hệ thống phi tập trung hoàn toàn hay không phép.
- **Tính năng riêng tư:** 38% biện pháp bảo vệ theo quy định, 31% thiết kế thu thập tối thiểu hoặc không thu thập dữ liệu, 28% công nghệ tăng cường riêng tư, 3% chưa quyết.
- **Chức năng ngoại tuyến:** 64% có theo đuổi, 29% chưa quyết, 7% không.
- **Sửa luật AML/CFT:** 50% chưa sửa, 36% chưa áp dụng, 14% đã sửa. Nhiều nước quyết định tận dụng khung pháp lý thanh toán hiện có thay vì xây khung riêng cho rCBDC.

### 6. Kết luận và các câu hỏi bỏ ngỏ

- Dù mức độ sử dụng rCBDC còn hạn chế, rõ ràng tác động tới tính toàn vẹn tài chính khác nhau rất nhiều tuỳ lựa chọn thiết kế. Mô hình token thuần tuý về bản chất rủi ro cao hơn mô hình tài khoản thuần tuý vì không bao gồm các khía cạnh quản lý tài khoản. Hệ thống phi tập trung và không phép cao độ có rủi ro cao hơn vì ngân hàng trung ương và cơ quan khác kiểm soát ít hơn. Mô hình trực tiếp không trung gian gây gián đoạn đáng kể cho hệ thống hiện tại.
- rCBDC không vận hành trong chân không. Điểm yếu và lỗ hổng hiện có trong khung AML/CFT của một nước nhiều khả năng sẽ được duy trì và thậm chí trầm trọng thêm. Do đó các nước nên nỗ lực khắc phục những thiếu sót AML/CFT chính trước khi phát hành rCBDC. Tương tự, những điểm mạnh hiện có sẽ tiếp tục tồn tại và nên được tận dụng.
- Về cơ bản, rCBDC có thể đặt ra câu hỏi về bản chất mong muốn của trung gian hoá tài chính và phòng ngừa AML/CFT. Theo chuẩn FATF hiện hành, trách nhiệm được phân định giữa khu vực tư nhân (áp dụng biện pháp phòng ngừa) và cơ quan có thẩm quyền (quản lý, giám sát, thực thi). Trong mô hình trực tiếp, ngân hàng trung ương bước vào vai trò người gác cổng.
- Một nghịch lý đáng chú ý: nếu rCBDC được áp dụng rộng rãi và trở thành hình thái tiền ngân hàng trung ương chủ yếu cho thanh toán bán lẻ, thì theo quy tắc CDD hiện hành sẽ gần như không còn chỗ cho giao dịch không bị giám sát và không được định danh. Điều này trái ngược với hiện tại, khi tỷ lệ giao dịch bằng tiền pháp định truyền thống chịu kiểm soát AML/CFT còn thấp hơn.
- **Sáu nhóm câu hỏi còn bỏ ngỏ** được nêu trong Bảng 3: vai trò đúng đắn của ngân hàng trung ương so với trung gian; liệu một số nghĩa vụ AML/CFT có cần điều chỉnh không; liệu mô hình rCBDC nào có thể tích hợp tính năng giống tiền mặt mà không vi phạm chuẩn FATF; cách thực hiện TFS và báo cáo giao dịch đáng ngờ với ví không định danh và chức năng ngoại tuyến; cách đánh giá rủi ro rCBDC trước tính mới của nó; và loại cơ hội công nghệ nào nên được tận dụng.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Retail CBDC (rCBDC) | Tiền số ngân hàng trung ương bán lẻ, phân phối cho đại chúng dùng thanh toán hàng ngày |
| Wholesale CBDC (wCBDC) | CBDC bán buôn, dành cho tổ chức tài chính để quyết toán giao dịch giá trị lớn |
| E-money | Tiền điện tử, thường do tổ chức tài chính phi ngân hàng phát hành, không token hoá |
| Virtual assets (VAs) | Tài sản ảo, tài sản số do tư nhân phát hành |
| FATF | Lực lượng Đặc nhiệm Tài chính, cơ quan liên chính phủ đặt chuẩn AML/CFT từ 1989 |
| AML/CFT | Chống rửa tiền và chống tài trợ khủng bố |
| ML/TF/PF | Rửa tiền, tài trợ khủng bố, tài trợ phổ biến vũ khí huỷ diệt hàng loạt |
| Token-based CBDC | CBDC dựa trên token, sở hữu chứng minh bằng việc nắm giữ, như công cụ vô danh |
| Account-based CBDC | CBDC dựa trên tài khoản, dựa vào bên thứ ba giữ sổ sách khách quan |
| Direct (one-tiered) system | Hệ thống trực tiếp, ngân hàng trung ương tự tiếp xúc khách hàng cuối |
| Indirect (two-tiered) system | Hệ thống gián tiếp, trung gian là lớp tiếp xúc khách hàng |
| Permissioned system | Hệ thống có phép, chỉ nhóm được uỷ quyền mới truy cập sổ cái |
| Permissionless system | Hệ thống không phép, mở cho mọi người không cần uỷ quyền trước |
| CDD | Thẩm định khách hàng, gồm xác định và xác minh danh tính, xác định chủ sở hữu hưởng lợi |
| SDD | Thẩm định khách hàng đơn giản hoá, áp dụng khi rủi ro được đánh giá là thấp |
| Anonymous account | Tài khoản ẩn danh, bị Khuyến nghị 10 cấm duy trì |
| TFS | Trừng phạt tài chính có mục tiêu, phải phong toả tài sản "không chậm trễ" |
| Unhosted wallet | Ví không lưu ký, do người dùng tự kiểm soát, nằm ngoài phạm vi quản lý |
| Pseudonymous ledger | Sổ cái bí danh, người dùng được nhận diện bằng khoá riêng hoặc định danh khác |
| Zero-Knowledge Proof | Bằng chứng không tiết lộ, chứng minh quyền giao dịch mà không lộ thông tin cá nhân |
| Third-party reliance | Dựa vào bên thứ ba có nghĩa vụ AML/CFT để thực hiện một phần CDD |
| Outsourcing/agency | Thuê ngoài cho bên không có nghĩa vụ AML/CFT, theo chỉ dẫn của bên uỷ quyền |
| Travel Rule | Quy tắc truyền thông tin người gửi và người nhận kèm giao dịch chuyển tiền |
| STR | Báo cáo giao dịch đáng ngờ gửi cho đơn vị tình báo tài chính |
| FIU | Đơn vị tình báo tài chính |
| PFMI | Nguyên tắc dành cho Hạ tầng Thị trường Tài chính của CPMI-IOSCO |
| Compliance-by-design | Tuân thủ theo thiết kế, mã hoá quy định vào chính kiến trúc của đồng tiền |

## Câu nói đáng nhớ

> "Financial integrity implications vary greatly depending on the specific design choices adopted."

> "rCBDCs do not operate in a vacuum. Existing weaknesses and vulnerabilities in a country's AML/CFT framework will likely be perpetuated and even exacerbated."

> "Central banks should ensure that their CBDC does not create substantial new loopholes that criminals or terrorists could easily exploit."

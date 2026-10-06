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

## Khái niệm cần biết

**Tiền số ngân hàng trung ương bán lẻ (rCBDC).** Một hình thái số của tiền ngân hàng trung ương, phân phối cho đại chúng để thanh toán hằng ngày. Nó khác **tiền điện tử** (e-money), loại thường do công ty tài chính phi ngân hàng phát hành và là nợ của công ty đó, và khác **tài sản ảo** như tiền mã hoá do tư nhân phát hành. Ví dụ trong bài: Sand Dollar của Bahamas, Jam-Dex của Jamaica và eNaira của Nigeria là ba rCBDC đã phát hành chính thức. Đây là đối tượng của toàn bài.

**Chống rửa tiền và chống tài trợ khủng bố (AML/CFT).** Rửa tiền là biến tiền bẩn (từ buôn lậu, tham nhũng, lừa đảo) thành tiền trông có vẻ hợp pháp bằng cách cho nó đi qua nhiều giao dịch. Tài trợ khủng bố là chuyển tiền, kể cả tiền sạch, cho tổ chức khủng bố. AML/CFT là tập hợp các nghĩa vụ buộc ngân hàng và tổ chức tài chính phải biết khách hàng là ai, theo dõi giao dịch và báo cáo khi thấy đáng ngờ. Ví dụ minh hoạ: một người gửi 50 khoản tiền mặt nhỏ vào 50 tài khoản khác nhau rồi gom về một tài khoản ở nước ngoài; hệ thống AML phải nhận ra mẫu hình đó. Bài hỏi liệu rCBDC làm việc này dễ hơn hay khó hơn.

**FATF và 40 Khuyến nghị.** FATF (Lực lượng Đặc nhiệm Hành động Tài chính) là cơ quan liên chính phủ đặt chuẩn quốc tế về AML/CFT. Bộ chuẩn gồm 40 Khuyến nghị, kèm ghi chú diễn giải; mỗi Khuyến nghị (viết tắt R., ví dụ R.10) là một nghĩa vụ cụ thể. Ví dụ: R.10 cấm tổ chức tài chính duy trì tài khoản ẩn danh. Ban Điều hành IMF đã chấp nhận bộ chuẩn này làm chuẩn cho công việc AML/CFT của Quỹ, nên bài đối chiếu từng lựa chọn thiết kế rCBDC với từng Khuyến nghị.

**Thẩm định khách hàng (CDD) và thẩm định đơn giản hoá (SDD).** CDD là quy trình tổ chức tài chính xác định khách hàng là ai (hỏi tên, ngày sinh) và xác minh điều đó (đối chiếu giấy tờ), cùng xác định ai là chủ sở hữu thật sự đứng sau. SDD là phiên bản nhẹ hơn, áp dụng khi rủi ro được đánh giá là thấp. Ví dụ minh hoạ: một ví chỉ được giữ tối đa vài triệu đồng có thể chỉ cần số điện thoại và tên tự khai, còn ví không giới hạn thì phải có giấy tờ tuỳ thân đầy đủ. Đây là công cụ chính để cân bằng giữa riêng tư và chống tội phạm trong rCBDC.

**Mô hình trực tiếp và gián tiếp (một tầng và hai tầng).** Trong mô hình trực tiếp, ngân hàng trung ương tự mở ví cho người dân và tự tiếp xúc khách hàng. Trong mô hình gián tiếp, ngân hàng trung ương phát hành cho các trung gian (thường là ngân hàng) và trung gian mở ví, chăm sóc khách hàng. Ví dụ trong khảo sát của bài: 93% nước tham gia chọn mô hình gián tiếp. Phân biệt này quyết định ai phải gánh nghĩa vụ AML/CFT.

**Trừng phạt tài chính có mục tiêu (TFS).** Nghĩa vụ phong toả "không chậm trễ" mọi tài sản của những cá nhân, tổ chức nằm trong danh sách trừng phạt (thường của Liên Hợp Quốc) và cấm mọi người chuyển tiền cho họ. Ví dụ minh hoạ: khi một người bị đưa vào danh sách lúc 9 giờ sáng, ngân hàng phải chặn mọi giao dịch của người đó ngay trong ngày. TFS khó áp dụng với ví ẩn danh hoặc giao dịch ngoại tuyến, nên là một trong ba điểm nghẽn lớn nhất của bài.

**Sổ cái có phép và không phép, sổ cái bí danh.** Sổ cái có phép (permissioned) chỉ cho nhóm đã được uỷ quyền truy cập và ghi giao dịch; sổ cái không phép (permissionless) mở cho bất kỳ ai, như sổ cái của bitcoin. Sổ cái bí danh ghi giao dịch theo mã số hoặc địa chỉ ví chứ không theo tên thật; tên thật do trung gian giữ riêng. Ví dụ trong bài: cả ba rCBDC đã phát hành đều dùng hệ thống có phép.

**Chức năng ngoại tuyến (offline functionality).** Khả năng chuyển tiền giữa hai thiết bị, ví dụ chạm hai điện thoại vào nhau, mà không cần kết nối tới sổ cái trung tâm vào lúc đó. Ví dụ trong khảo sát: 64% nước tham gia có theo đuổi chức năng này. Nó hữu ích khi mất mạng nhưng làm khó việc giám sát, vì giao dịch chỉ được kiểm tra khi thiết bị kết nối lại.

## Nội dung chi tiết

### 1. Vì sao cần bàn về rCBDC và tính toàn vẹn tài chính

Ngân hàng trung ương ở nhiều nước đang hiện đại hoá hệ thống thanh toán cũ, nổi bật là qua tiền số ngân hàng trung ương (CBDC). Chưa có định nghĩa phổ quát, nhưng CBDC thường được hiểu là một hình thái số của tiền ngân hàng trung ương. Nó khác tiền điện tử, loại thường do tổ chức tài chính phi ngân hàng phát hành, và khác tài sản ảo do tư nhân phát hành.

**Tình hình rCBDC toàn cầu tính đến 2025:**

| Nhóm | Nước |
|---|---|
| Đã phát hành (3 nước) | Bahamas (Sand Dollar), Jamaica (Jam-Dex), Nigeria (eNaira); quy mô người dùng tương đối nhỏ |
| Đang thí điểm | Trung Quốc (e-CNY), Ghana (e-Cedi), Ấn Độ (Digital Rupee), Kazakhstan (Digital Tenge), Türkiye, và Liên minh Tiền tệ Đông Caribe (DCash); một số thí điểm đã tới hàng triệu người dùng (Trung Quốc, Ấn Độ) |
| Nghiên cứu nâng cao | EU, Indonesia, Maroc, Thuỵ Điển, UAE, Anh |
| Tạm dừng hoặc chấm dứt | Canada, Ecuador |

**Vì sao phải lo về tính toàn vẹn tài chính.** Như mọi loại tài sản khác, rCBDC có thể bị lợi dụng để rửa tiền, tài trợ khủng bố, tài trợ phổ biến vũ khí huỷ diệt hàng loạt và các tội phạm tài chính khác. Đây không phải lo ngại lý thuyết: ít nhất một nước phát hành đã phát hiện vụ lạm dụng hình sự, cụ thể là vụ rửa tiền bằng nhân dân tệ số ở Trung Quốc năm 2022. Nếu được dùng rộng rãi, rCBDC có thể tác động đáng kể tới tính toàn vẹn của hệ thống tài chính toàn cầu. Vì vậy việc triển khai hiệu quả các chuẩn quốc tế là cần thiết.

**Chuẩn đối chiếu.** Ban Điều hành IMF đã thông qua bộ chuẩn FATF (40 Khuyến nghị, các Ghi chú Diễn giải và Bảng Thuật ngữ) làm chuẩn cho công tác AML/CFT của Quỹ. FATF (2020) khẳng định chuẩn của mình áp dụng cho CBDC tương tự như mọi hình thái tiền pháp định khác do ngân hàng trung ương phát hành. Nhưng tại thời điểm soạn thảo, chưa cơ quan đánh giá nào từng đánh giá hiệu quả AML/CFT của một nước đã phát hành hay thí điểm rCBDC, và tài liệu học thuật về chủ đề này còn rất ít. Thực tiễn và hướng dẫn hạn chế khiến nhiều nước tìm tới Vụ Pháp lý IMF xin hỗ trợ kỹ thuật.

**Mục đích kép của tài liệu:**

1. Hướng dẫn nhà hoạch định chính sách và cơ quan có thẩm quyền về cách triển khai chuẩn AML/CFT quốc tế trong bối cảnh rCBDC.
2. Làm nổi bật những khía cạnh của chuẩn AML/CFT cần suy nghĩ thêm.

Tài liệu không đại diện cho quan điểm của FATF và không nhằm đoán trước quan điểm đó. Phân tích dựa trên các lựa chọn thiết kế rCBDC và bộ chuẩn FATF tại một thời điểm cụ thể. Các dự án CBDC có thể thay đổi mạnh, và bộ chuẩn FATF cũng tiếp tục tiến hoá để thích ứng với các hình thái rửa tiền mới.

### 2. Bảy đặc điểm thiết kế quan trọng

Bài xác định bảy đặc điểm thiết kế có ảnh hưởng lớn tới rủi ro AML/CFT.

**Đặc điểm 1: bán lẻ và bán buôn.** rCBDC phân phối cho đại chúng để thanh toán hằng ngày; cả ba CBDC đã phát hành đầy đủ đều là bán lẻ. wCBDC (bán buôn) phân phối cho một số tổ chức tài chính được chọn, dùng để quyết toán giao dịch giá trị lớn. Hai hướng không loại trừ nhau; một số nước theo đuổi cả hai, như Israel và UAE. Bài tập trung vào rCBDC vì chuẩn AML/CFT toàn cầu chủ yếu nhắm ngăn rửa tiền qua hoạt động ngân hàng bán lẻ, chứ không phải các hoạt động như cho vay liên ngân hàng, vốn giữa các bên đã qua kiểm tra AML/CFT.

**Đặc điểm 2: dựa trên token và dựa trên tài khoản.**

| | Dựa trên token | Dựa trên tài khoản |
|---|---|---|
| Bản chất | Vật mang giá trị nội tại, giống một công cụ vô danh dạng số | Tạo quyền và nghĩa vụ trên tài khoản của người dùng |
| Chứng minh sở hữu | Bằng việc nắm giữ | Bằng sổ sách do bên thứ ba giữ một cách khách quan |
| Chuyển giao | Không cần trung gian | Qua bên giữ sổ |
| Ví dụ cổ điển | Tiền mặt | Tài khoản ngân hàng |

Chưa nước nào theo đuổi nghiêm túc mô hình token thuần tuý. Trên thực tế sự phân biệt này khá học thuật: hầu hết thiết kế kết hợp cả hai, dùng xác thực an toàn để ngăn chi tiêu hai lần (như hệ thống token), đồng thời ghi số dư và cho phép quản lý tài khoản (như hệ thống tài khoản). Mọi thí điểm nâng cao và phát hành đều mang đặc điểm của cả hai. Ví dụ, e-CNY là công cụ lai: chuyển nhượng kiểu token nhưng kiểm soát kiểu tài khoản.

**Đặc điểm 3: phương thức phân phối trực tiếp và gián tiếp.** Trong mô hình trực tiếp (một tầng, không trung gian), ngân hàng trung ương tự phân phối tới người dùng cuối, tự mở và quản lý ví hay tài khoản, và đảm nhận vai trò tiếp xúc khách hàng. Trong mô hình gián tiếp (hai tầng, có trung gian), ngân hàng trung ương phát hành cho các trung gian được xác định, thường là ngân hàng, nhưng có thể là tổ chức tài chính phi ngân hàng hoặc cả tổ chức phi tài chính; người dùng mở tài khoản với trung gian.

Có một điểm tinh tế: theo nguyên tắc được thừa nhận rộng rãi, CBDC "thật" phải là nghĩa vụ nợ trên bảng cân đối của ngân hàng trung ương. Vì vậy trung gian không nắm giữ tài khoản khách hàng về mặt pháp lý, mà chỉ là lớp tiếp xúc khách hàng.

Mọi dự án rCBDC đến nay đều theo một dạng có trung gian; không ngân hàng trung ương nào theo đuổi nghiêm túc mô hình trực tiếp không trung gian. Người tham gia bàn tròn áp đảo chọn mô hình gián tiếp, dù không có hai nước nào giống hệt nhau về hạ tầng sổ cái, loại trung gian và vai trò các bên. Mức độ trung gian hoá rất khác nhau: ngân hàng trung ương có thể giữ toàn bộ sổ cái và ghi từng giao dịch bán lẻ, hoặc chỉ giữ sổ cái bán buôn còn các trung gian giữ sổ phụ. Một số đang thử cho nhiều trung gian cùng tương tác với một tài khoản khách hàng mà ngân hàng trung ương nắm giữ về mặt pháp lý (dự án Sela).

**Đặc điểm 4: tập trung và phi tập trung.** Hệ thống tập trung do ngân hàng trung ương kiểm soát hoàn toàn. Hệ thống phi tập trung phân tán việc duy trì sổ cái và xác thực giao dịch cho nhiều máy chủ (nút). Nhiều mức độ có thể cùng tồn tại trong một mô hình. Đa số người tham gia bàn tròn nghiêng về hệ thống tập trung.

**Đặc điểm 5: truy cập sổ cái (có phép và không phép).** Ba rCBDC đã phát hành và mọi mô hình tại bàn tròn đều là hệ thống có phép; chưa hệ thống không phép hoàn toàn nào được theo đuổi nghiêm túc. Có thể kết hợp truy cập hạn chế và không hạn chế ở các phần khác nhau của cùng một sổ cái, ví dụ lớp tài sản có phép còn lớp dịch vụ (lớp giao diện lập trình ứng dụng, nơi bên ngoài kết nối vào) không phép.

**Đặc điểm 6: trong nước và xuyên biên giới.** Tính đến 2025, mọi thí điểm và phát hành rCBDC đều đơn phương và chỉ thiết kế cho sử dụng trong nước. Các dự án về chức năng xuyên biên giới có tồn tại nhưng còn sơ khai. Kiến trúc xuyên biên giới có hai dạng: nền tảng chung cho một đồng tiền dùng ở nhiều nước (DCash, đồng euro số), và thoả thuận đa tiền tệ, hoặc qua nền tảng liên kết (như dự án Icebreaker) hoặc nền tảng chung.

**Đặc điểm 7: chức năng ngoại tuyến và tính riêng tư.** Thanh toán ngoại tuyến là chuyển giá trị giữa các thiết bị không cần kết nối tới sổ cái. Động cơ gồm khả năng chống chịu khi mất mạng, bao trùm tài chính cho vùng không có sóng, mang lại lựa chọn giống tiền mặt và bảo vệ riêng tư. Nhưng chưa nước nào theo đuổi hệ thống ngoại tuyến hoàn toàn, tức người trả và người nhận ở ngoại tuyến vô thời hạn, vì lo ngại chi tiêu hai lần (cùng một khoản tiền bị tiêu hai lần trước khi hệ thống kịp ghi nhận) và lo ngại về tính toàn vẹn tài chính.

Về riêng tư, mức độ riêng tư là một đặc tính có thể lập trình. Có hai mục tiêu chính:

- **Riêng tư trước người quản trị sổ cái**: đa số chọn sổ cái bí danh, trong đó thông tin định danh do trung gian giữ riêng, ngân hàng trung ương chỉ thấy mã số.
- **Riêng tư khi giao dịch**: hệ thống phân tầng, trong đó tầng thấp nhất (hạn mức nhỏ) yêu cầu định danh tối thiểu hoặc không yêu cầu.

Mọi dự án đều có một dạng bảo vệ riêng tư, nhưng chưa nước nào theo đuổi rCBDC ẩn danh hoàn toàn, bất kể tên gọi của đồng tiền gợi ý điều gì. Điểm cần nhớ là chuẩn so sánh trong giao dịch tài chính không phải riêng tư tuyệt đối: ngân hàng vốn đã thường xuyên giám sát và phân tích hành vi khách hàng.

### 3. Áp dụng chuẩn FATF: nơi dễ, nơi khó

**Phần lớn chuẩn áp dụng thẳng.** Phần lớn bộ chuẩn FATF sẽ được triển khai cho rCBDC giống hệt như với tiền truyền thống. Ví dụ, hình phạt hình sự cho rửa tiền bằng CBDC cần hiệu quả, tương xứng và có tính răn đe như với mọi tài sản khác. Tuy vậy, theo đánh giá của bài, 18 trên 40 Khuyến nghị gặp khó khăn ở mức trung bình hoặc đáng kể khi áp dụng.

**Đánh giá rủi ro (R.1 và R.15).** FATF cảnh báo rủi ro phải được xử lý theo hướng nhìn về phía trước, tức trước khi phát hành bất kỳ CBDC nào, và việc giảm thiểu rủi ro nên do chính người phát hành CBDC dẫn dắt. Đánh giá rủi ro rCBDC có thể phức tạp hơn sản phẩm khác vì hệ thống còn mới, chưa có dữ liệu về cách tội phạm thực sự lợi dụng nó.

**So sánh rủi ro rCBDC với tiền mặt.** Bài lập bảng so sánh các yếu tố rủi ro và khả năng giảm thiểu:

| Yếu tố | rCBDC | Tiền mặt |
|---|---|---|
| Tính ẩn danh | Từ thấp đến cao tuỳ thiết kế (ẩn danh quy mô lớn ít khả năng xảy ra theo các dự án hiện tại) | Cao |
| Khả năng chuyển đổi sang tài sản khác | Cao | |
| Phạm vi địa lý | Tuỳ thiết kế | |
| Tốc độ và tính di động | Cao | |
| Truy vết | Mạnh | Yếu |
| Hạn mức giao dịch | Mạnh | Yếu |
| Thẩm định khách hàng | Mạnh | Yếu |
| Lưu trữ hồ sơ | Mạnh | Yếu |
| Giám sát giao dịch | Mạnh | Yếu |

Tức là rCBDC nhanh và dễ chuyển hơn tiền mặt, nhưng cũng dễ kiểm soát hơn nhiều.

**Biện pháp phòng ngừa.** Mọi chủ thể trong hệ sinh thái CBDC đáp ứng định nghĩa tổ chức tài chính, nhà cung cấp dịch vụ tài sản ảo hoặc doanh nghiệp phi tài chính được chỉ định đều phải chịu nghĩa vụ AML/CFT. Nơi nhà cung cấp ví chỉ cung cấp phần mềm thì có thể không đáp ứng định nghĩa nào. Nơi nhà mạng viễn thông được giao thực hiện chức năng tuân thủ thay tổ chức tài chính thì trách nhiệm cuối cùng vẫn thuộc về tổ chức tài chính thuê ngoài.

**CDD đơn giản hoá và miễn trừ.** Cần phân biệt **xác định** khách hàng (hỏi họ là ai) và **xác minh** danh tính (kiểm tra điều họ khai). CDD đơn giản hoá không có nghĩa là miễn trừ hoàn toàn, mà là cách tiếp cận được hiệu chỉnh tương xứng với rủi ro. Trong tình huống rủi ro thấp, việc xác định có thể dựa vào giấy tờ thay thế như chứng minh thư hết hạn hay thẻ thuế, còn việc xác minh có thể trì hoãn. Vấn đề hiện nay là hạn mức nắm giữ và giao dịch của các ví thường được đặt ra mà không dựa trên đánh giá rủi ro nào.

**Dựa vào bên thứ ba và thuê ngoài (R.17).** Hai trường hợp khác nhau:

- **Dựa vào bên thứ ba**: bên thứ ba tự có nghĩa vụ AML/CFT và tự chịu quản lý, giám sát.
- **Thuê ngoài**: bên nhận việc không có nghĩa vụ AML/CFT, nên phải làm theo chỉ dẫn và quy trình của tổ chức tài chính uỷ quyền.

Trong cả hai trường hợp, trách nhiệm cuối cùng vẫn thuộc về đơn vị báo cáo, tức tổ chức tài chính có nghĩa vụ.

**Minh bạch thanh toán (R.16).** Quy tắc này yêu cầu thông tin người gửi và người nhận đi kèm giao dịch chuyển tiền. Nếu thông tin đã có sẵn trên sổ cái và mọi bên trong chuỗi thanh toán đều truy cập được, có thể không cần truyền riêng. Nhưng vì đa số sổ cái được thiết kế bí danh, thông tin khách hàng thường không nằm trên sổ cái, nên trung gian khởi tạo vẫn phải gửi thông tin bắt buộc cho trung gian nhận.

**Lưu trữ hồ sơ (R.11).** Với rCBDC, thông tin về khách hàng có thể gồm định danh số như khoá công khai hoặc địa chỉ ví, có chức năng tương tự số tài khoản. Câu hỏi mới nảy sinh: nếu ngân hàng trung ương giữ toàn bộ sổ cái còn trung gian chỉ thấy bản sao ví của khách hàng, thì khi sổ cái trục trặc làm mất hồ sơ, lỗi đó có bị quy cho trung gian không.

**Giám sát giao dịch và báo cáo giao dịch đáng ngờ (R.20).** Trong mô hình có trung gian, cách giám sát nhiều khả năng giống thực tiễn hiện nay. Khó khăn nảy sinh ở ba chỗ: mô hình trực tiếp, ví cơ bản với ít thông tin về chủ, và chức năng ngoại tuyến. Chính các ngân hàng trung ương xếp rủi ro của chức năng ngoại tuyến vào nhóm đáng kể nhất.

**Thực thi hình sự.** Phong toả, tịch thu tài sản số, dừng hoặc đảo ngược giao dịch có thể đòi quyền truy cập trực tiếp vào sổ cái và quyền can thiệp vào ví. Trong hệ thống phi tập trung hoàn toàn, cơ quan có thẩm quyền gần như không kiểm soát được sổ cái. Ngược lại, nơi cơ quan thực thi pháp luật được trao quyền trực tiếp trên sổ cái, cần có biện pháp bảo vệ để bảo đảm đúng quy trình tố tụng.

**Ba điểm nghẽn lớn nhất.**

*Điểm nghẽn thứ nhất: cấm tài khoản ẩn danh (Khuyến nghị 10).* R.10 cấm tổ chức tài chính duy trì tài khoản ẩn danh. Có hai khái niệm phải làm rõ. (i) "Ẩn danh": FATF không định nghĩa rõ, nhưng trọng tâm là việc cố ý che giấu hoặc xuyên tạc danh tính để tránh bị phát hiện. (ii) "Tài khoản": Bảng Thuật ngữ FATF không định nghĩa, chỉ nói bao gồm "các quan hệ kinh doanh tương tự", hàm ý phải có quan hệ khách hàng. Vấn đề là các tính năng bảo vệ riêng tư có thể xung đột với lệnh cấm này. Một hệ thống rCBDC thiết kế "giống tiền mặt", không yêu cầu trung gian định danh người dùng, sẽ rất khó thoả mãn ngay cả yêu cầu CDD đơn giản hoá nhẹ nhất. Giải pháp thẳng thắn là cho phép giao dịch ngang hàng thật sự qua ví không lưu ký (ví do người dùng tự giữ, nằm ngoài trung gian), nhưng đến nay chưa nước nào theo đuổi. Điều kiện tối thiểu: để mô hình phân tầng thoả mãn CDD đơn giản hoá, ở tầng cơ bản nhất người dùng ít nhất phải tự khai tên của mình.

*Điểm nghẽn thứ hai: trừng phạt tài chính có mục tiêu (Khuyến nghị 6 và 7).* Khác mọi nghĩa vụ AML/CFT khác, TFS áp dụng cho mọi người trong một nước (không chỉ các đơn vị báo cáo) và cho mọi giao dịch với bất kỳ loại tài sản nào. TFS gắn chặt với tên, bí danh và định danh của người bị chỉ định, nên rất khó triển khai với mô hình cho người dùng ẩn danh hoặc chỉ định danh bằng bí danh không gắn danh tính thật.

- *Thời điểm sàng lọc*: FATF yêu cầu phong toả "không chậm trễ". Nếu không giới hạn chặt thời gian ví được ở ngoại tuyến, một khoảng thời gian đáng kể có thể trôi qua trước khi trung gian phát hiện giao dịch bất hợp pháp.
- *Giao dịch ngoại tuyến*: sàng lọc trên thực tế chỉ diễn ra khi thiết bị kết nối lại. Phát hiện hậu kiểm tốt hơn không phát hiện, nhưng không ngăn được giao dịch đã xảy ra.
- *Giải pháp*: triển khai TFS chung giữa các nhà cung cấp dịch vụ. Ví dụ, nếu mô hình phân tầng gắn với số điện thoại, có thể xây khung buộc nhà mạng thông báo ngay cho tổ chức tài chính khi một thuê bao trúng danh sách trừng phạt. Lưu ý: tổ chức tài chính vẫn chịu trách nhiệm nếu nhà mạng không phát hiện được.
- *Lo ngại sâu xa*: lập luận chính cho hiệu quả của TFS là nó cắt đứt khủng bố khỏi hệ thống tài chính chính thức, buộc chúng dùng cách chậm hơn, đắt hơn, kém an toàn hơn. Nếu rCBDC cho phép ví không định danh, khả năng lách trừng phạt ngay trong kênh chính thức có thể tăng, làm tăng rủi ro tài trợ khủng bố.

*Điểm nghẽn thứ ba: mô hình trực tiếp và vai trò mới của ngân hàng trung ương.* Định nghĩa "tổ chức tài chính" của FATF liệt kê 13 hoạt động. Nếu ngân hàng trung ương thực hiện một trong 13 hoạt động đó "với tư cách một doanh nghiệp", nó phải chịu toàn bộ nghĩa vụ AML/CFT. Câu hỏi mấu chốt: hoạt động của ngân hàng trung ương, một cơ quan công, có được coi là mang tính thương mại không? Một số ngân hàng trung ương đã có hoạt động bán lẻ nhỏ lẻ (mua bán tiền xu, tiền giấy, phát hành chứng khoán) nhưng thường không bị coi là đơn vị báo cáo, ví dụ Ngân hàng Dự trữ Nam Phi và Ngân hàng Jamaica. Nếu ngân hàng trung ương trở thành đơn vị báo cáo, sẽ có ba thách thức giám sát:

| Thách thức | Nội dung | Hướng xử lý hoặc hệ quả |
|---|---|---|
| (i) Xung đột lợi ích | Nhất là khi cơ quan giám sát AML/CFT nằm trong chính ngân hàng trung ương; căng thẳng giữa thúc đẩy bao trùm tài chính, đổi mới và chống tội phạm tài chính | Khung quản trị rõ ràng; tách bộ phận riêng hoặc đơn vị có tường lửa, như cách một số đơn vị tình báo tài chính (FIU) được đặt trong ngân hàng trung ương |
| (ii) Độc lập của ngân hàng trung ương | Là đơn vị báo cáo thì phải chịu giám sát AML/CFT, kể cả bị áp chế tài | Ở nước có nhà nước pháp quyền yếu và tham nhũng phổ biến, chế tài có thể thành công cụ trả đũa, gây áp lực chính trị; nhiều chế độ pháp lý trong nước không cho phép loại giám sát này |
| (iii) Không áp được chế tài | Nếu không thể áp chế tài lên ngân hàng trung ương trong mô hình trực tiếp | Yêu cầu của Khuyến nghị 27 (về quyền hạn của cơ quan giám sát) không thể được thoả mãn |

### 4. Cơ hội mà rCBDC mang lại cho tuân thủ

Bài không chỉ nói rủi ro mà còn nêu bốn cơ hội:

- **Giám sát giao dịch tốt hơn.** Một sổ cái CBDC thống nhất, không phân mảnh, mở rộng tập thông tin sẵn có: thay vì mỗi ngân hàng chỉ thấy giao dịch của khách mình, có thể nhìn toàn bộ giao dịch trên sổ cái của ngân hàng trung ương. Ví dụ minh hoạ: một kẻ rửa tiền chia tiền qua 20 ngân hàng khác nhau, mỗi ngân hàng chỉ thấy một mảnh nhỏ vô hại, nhưng trên sổ cái thống nhất cả mẫu hình hiện ra.
- **Phát hiện kịp thời.** Cơ quan có thẩm quyền truy cập trực tiếp sổ cái thống nhất có thể tự phân tích để phát hiện giao dịch và mẫu hình đáng ngờ, không phải chờ báo cáo từ trung gian. Khi cần, họ có thể xin thêm thông tin định danh chủ ví từ trung gian liên quan.
- **Lưu trữ và chia sẻ dữ liệu khách hàng gọn hơn.** Cấu trúc hồ sơ của rCBDC có thể cải thiện quy trình thẩm định khách hàng và giảm trùng lặp, chẳng hạn qua một token "biết khách hàng của bạn" mà khách mang theo sang nhiều trung gian. Tuy nhiên, chất lượng dữ liệu gốc là mấu chốt: nơi chế độ thẩm định khách hàng kém, chia sẻ thông tin sai lệch không cải thiện được gì.
- **Tự động hoá tuân thủ.** Số hoá giao dịch mở đường cho việc tự động hoá một số yêu cầu AML/CFT, ví dụ viết yêu cầu quy định trực tiếp vào hợp đồng thông minh (đoạn mã tự thực thi trên sổ cái). Nhưng bài nhấn mạnh tuân thủ theo thiết kế không phải liều thuốc thần: những sáng kiến tương tự như định danh khách hàng điện tử đã được áp dụng cho dịch vụ thanh toán hiện có mà chưa chứng minh được hiệu quả trong mọi trường hợp, và IMF không chứng thực các giải pháp này.

### 5. Kết quả khảo sát bàn tròn tháng 1/2025

Tháng 1/2025, Vụ Pháp lý IMF tổ chức một bàn tròn trực tuyến với đại diện ngân hàng trung ương và cơ quan liên quan từ 14 nước và khối khu vực, cùng đại diện các vụ khác của IMF và Ban Thư ký FATF. Các bên tham gia gồm Bahamas, Trung Quốc, Ngân hàng Trung ương Đông Caribe, ECB, Ghana, Hong Kong SAR, Nhật Bản, Kazakhstan, Maroc, New Zealand, Nigeria, Thuỵ Điển, Türkiye và một nước không nêu tên. Kết quả khảo sát:

| Chủ đề | Kết quả |
|---|---|
| Mô hình phân phối | 93% gián tiếp có trung gian; 7% chưa quyết |
| Loại trung gian | Một nửa chỉ cho phép tổ chức tài chính; hơn một phần ba dự kiến hỗn hợp tổ chức tài chính và phi tài chính; 14% chưa quyết |
| Trách nhiệm AML/CFT | 93% giao cho trung gian khu vực tư nhân; 7% chưa quyết |
| Hạ tầng sổ cái | 36% sổ cái phân tán; 29% sổ cái tập trung; 28% chưa quyết; 7% lai |
| Tính năng riêng tư | 38% bảo vệ bằng quy định pháp luật; 31% thiết kế thu thập tối thiểu hoặc không thu thập dữ liệu; 28% công nghệ tăng cường riêng tư; 3% chưa quyết |
| Chức năng ngoại tuyến | 64% có theo đuổi; 29% chưa quyết; 7% không |
| Sửa luật AML/CFT | 50% chưa sửa; 36% chưa áp dụng; 14% đã sửa |

Một vài điểm đáng chú ý. Một số nước cởi mở với trung gian như nhà mạng viễn thông, vốn không có trách nhiệm AML/CFT truyền thống nhưng tiếp cận được rất nhiều khách hàng. Không nước nào thăm dò hệ thống phi tập trung hoàn toàn hay không phép. Nhiều nước quyết định dùng luôn khung pháp lý thanh toán hiện có thay vì xây khung riêng cho rCBDC, nên chỉ 14% đã sửa luật AML/CFT.

### 6. Kết luận và các câu hỏi bỏ ngỏ

**Rủi ro nằm ở lựa chọn thiết kế.** Dù mức sử dụng rCBDC còn hạn chế, rõ ràng tác động tới tính toàn vẹn tài chính khác nhau rất nhiều tuỳ thiết kế:

- Mô hình token thuần tuý rủi ro cao hơn mô hình tài khoản thuần tuý, vì thiếu các khía cạnh quản lý tài khoản.
- Hệ thống phi tập trung và không phép cao độ rủi ro cao hơn, vì ngân hàng trung ương và các cơ quan khác kiểm soát ít hơn.
- Mô hình trực tiếp không trung gian gây gián đoạn đáng kể cho hệ thống hiện tại.

**rCBDC không vận hành trong chân không.** Điểm yếu và lỗ hổng sẵn có trong khung AML/CFT của một nước nhiều khả năng sẽ được giữ nguyên và thậm chí trầm trọng thêm khi có rCBDC. Vì vậy các nước nên khắc phục những thiếu sót AML/CFT chính trước khi phát hành. Ngược lại, điểm mạnh sẵn có sẽ tiếp tục tồn tại và nên được tận dụng.

**Câu hỏi về bản chất trung gian hoá.** Theo chuẩn FATF hiện hành, trách nhiệm được phân định rõ: khu vực tư nhân áp dụng biện pháp phòng ngừa, còn cơ quan nhà nước quản lý, giám sát và thực thi. Trong mô hình trực tiếp, ngân hàng trung ương bước vào vai trò người gác cổng, vốn là việc của khu vực tư nhân, và ranh giới đó bị xoá.

**Một nghịch lý.** Nếu rCBDC được dùng rộng rãi và trở thành hình thái tiền ngân hàng trung ương chủ yếu cho thanh toán bán lẻ, thì theo quy tắc thẩm định khách hàng hiện hành sẽ gần như không còn chỗ cho giao dịch không bị giám sát và không được định danh. Điều này ngược hẳn với hiện tại, khi phần lớn giao dịch bằng tiền ngân hàng trung ương là tiền mặt và tỷ lệ chịu kiểm soát AML/CFT còn thấp. Tức là rCBDC có thể làm giao dịch kém riêng tư hơn tiền mặt rất nhiều nếu cứ áp nguyên chuẩn hiện hành.

**Sáu nhóm câu hỏi còn bỏ ngỏ** cho cộng đồng quốc tế:

1. Vai trò đúng đắn của ngân hàng trung ương so với trung gian là gì.
2. Có cần điều chỉnh một số nghĩa vụ AML/CFT không.
3. Mô hình rCBDC nào có thể có tính năng giống tiền mặt mà không vi phạm chuẩn FATF.
4. Thực hiện trừng phạt tài chính có mục tiêu và báo cáo giao dịch đáng ngờ thế nào với ví không định danh và chức năng ngoại tuyến.
5. Đánh giá rủi ro rCBDC thế nào khi nó còn quá mới.
6. Nên tận dụng những cơ hội công nghệ nào.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Retail CBDC (rCBDC) | Tiền số ngân hàng trung ương bán lẻ, phân phối cho đại chúng dùng thanh toán hàng ngày |
| Wholesale CBDC (wCBDC) | CBDC bán buôn, dành cho tổ chức tài chính để quyết toán giao dịch giá trị lớn |
| E-money | Tiền điện tử, thường do tổ chức tài chính phi ngân hàng phát hành, không token hoá |
| Virtual assets (VAs) | Tài sản ảo, tài sản số do tư nhân phát hành |
| FATF | Lực lượng Đặc nhiệm Hành động Tài chính, cơ quan liên chính phủ đặt chuẩn AML/CFT từ 1989 |
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

## Đánh giá và phát hiện đáng chú ý

### Nghịch lý ở cuối bài đảo ngược toàn bộ câu chuyện, và nó chỉ được cho một gạch đầu dòng

Suốt hai trăm trang lập luận, tài liệu hỏi một câu duy nhất: liệu rCBDC có làm suy yếu khả năng chống rửa tiền không. Rồi ở phần kết, gần như tình cờ, nó ghi nhận rằng nếu rCBDC được dùng rộng rãi thì **sẽ gần như không còn chỗ cho giao dịch không bị giám sát và không được định danh**, trái ngược hẳn với hiện tại khi phần lớn giao dịch bằng tiền pháp định truyền thống không chịu kiểm soát nào cả.

Câu đó lật ngược cả khung phân tích. Nếu nó đúng, thì rCBDC không phải một rủi ro cần được kiềm chế mà là **công cụ chống rửa tiền mạnh nhất từng được đề xuất trong lịch sử tài chính**. Bảng so sánh rủi ro trong chính bài nói đúng điều này: tiền mặt có tính ẩn danh cao và mọi biện pháp giảm thiểu đều yếu, còn rCBDC có truy vết mạnh, hạn mức mạnh, thẩm định khách hàng mạnh, giám sát giao dịch mạnh. Không có công cụ nào khác trong danh mục của cơ quan chống rửa tiền đạt được cả bốn.

Vì sao một tài liệu chuyên về tính toàn vẹn tài chính lại dành gần hết dung lượng để lo về rủi ro thay vì nói về cơ hội? Câu trả lời nằm ở bản chất của bộ chuẩn được dùng làm thước. Bốn mươi Khuyến nghị của FATF là một cơ chế **một chiều**: chúng đặt sàn về mức giám sát tối thiểu nhưng không có bất kỳ khái niệm nào về mức giám sát tối đa. Không có điều khoản nào nói rằng theo dõi quá nhiều là một vấn đề. Nên khi áp bộ chuẩn đó lên một công nghệ, kết quả tất yếu là một thiết kế tối đa hoá khả năng theo dõi, và mọi tính năng bảo vệ quyền riêng tư đều xuất hiện dưới dạng một "điểm nghẽn khi áp dụng chuẩn".

Đây không phải lỗi của nhóm tác giả, họ làm đúng nhiệm vụ được giao. Nhưng nó có nghĩa là **câu hỏi chính sách thực sự nằm ngoài phạm vi tài liệu**: xã hội có muốn một thế giới mà không còn khoảng không giao dịch riêng tư nào không, và ai là người quyết định điều đó. Bộ công cụ được dùng ở đây không có khả năng đặt câu hỏi ấy, chứ đừng nói tới trả lời.

### Bài toán chấp nhận và bài toán toàn vẹn thực ra là một bài toán

Hai kết quả trong tài liệu, khi ghép lại, tạo ra một ràng buộc chặt mà bài không phát biểu.

Kết quả thứ nhất: Khuyến nghị 10 cấm tài khoản ẩn danh, và điều kiện tối thiểu để một mô hình phân tầng thoả mãn thẩm định khách hàng đơn giản hoá là ở tầng thấp nhất người dùng **ít nhất phải tự khai tên**. Giải pháp thẳng thắn cho một rCBDC thực sự giống tiền mặt là cho phép ví không lưu ký giao dịch ngang hàng, và tài liệu ghi nhận rằng **chưa nước nào theo đuổi**.

Kết quả thứ hai, đến từ mọi bằng chứng thực nghiệm về ba nước đã phát hành: rCBDC không được dùng, kể cả khi miễn phí hoàn toàn.

Ghép lại: thứ duy nhất mà rCBDC có thể cung cấp và không công cụ số nào khác cung cấp được là **tính giống tiền mặt** — không cần tài khoản, không để lại dấu vết, dùng được với người không có giấy tờ. Chuyển khoản tức thời đã làm tốt mọi thứ khác. Nhưng tính giống tiền mặt lại chính là thứ bị bộ chuẩn chống rửa tiền cấm.

Nghĩa là bài toán chấp nhận không phải vấn đề tiếp thị hay thiết kế giao diện. Nó là hệ quả logic của một ràng buộc pháp lý: **tính năng duy nhất tạo ra nhu cầu là tính năng duy nhất không được phép có**. Đây là lý do cấu trúc khiến các chương trình rCBDC bán lẻ khó thành công, và nó giải thích vì sao Bahamas cuối cùng phải tính tới việc buộc ngân hàng phân phối — khi không thể tạo nhu cầu, chỉ còn cách tạo nguồn cung bắt buộc.

### Phần về ngân hàng trung ương làm đơn vị báo cáo là phần sắc nhất, và nó chỉ ra một nghịch lý thể chế

Lập luận rằng nếu ngân hàng trung ương trở thành đơn vị báo cáo thì nó phải chịu giám sát chống rửa tiền kể cả việc bị áp chế tài, và ở nước có nhà nước pháp quyền yếu, chế tài đó có thể trở thành công cụ trả đũa chính trị — đây là quan sát pháp lý tinh tế nhất trong cả tài liệu, và nó đi xa hơn chỗ bài dừng lại.

Hãy nối nó với lý do chính khiến người ta đề xuất mô hình phân phối trực tiếp. Mô hình trực tiếp hấp dẫn khi mạng lưới ngân hàng thương mại thưa, khi trung gian tư nhân không có động cơ phục vụ người nghèo, khi năng lực của khu vực tư nhân yếu. Nói cách khác, mô hình trực tiếp hấp dẫn nhất ở **đúng những nước có thể chế yếu nhất**.

Nhưng đó cũng chính là những nước mà việc biến ngân hàng trung ương thành đối tượng bị chế tài nguy hiểm nhất cho tính độc lập của nó. Và tài liệu còn đẩy xa hơn: nếu không thể áp chế tài lên ngân hàng trung ương, thì Khuyến nghị 27 **không thể được thoả mãn** — tức mô hình trực tiếp không tuân thủ được bộ chuẩn, chấm hết.

Kết quả là một nghịch lý thể chế gọn gàng: lập luận bao trùm tài chính mạnh nhất ở nơi mô hình trực tiếp khả thi nhất về kinh tế nhưng bất khả thi nhất về pháp lý. Điều này giải thích vì sao chín mươi ba phần trăm các nước được khảo sát chọn mô hình có trung gian, một con số thường được diễn giải là sự đồng thuận kỹ thuật, trong khi thực ra nó là sự đồng thuận về việc **không ai muốn gánh trách nhiệm người gác cổng**.

### Con số khảo sát cần đọc kèm cảnh báo, và hai con số trong đó mâu thuẫn nhau

Trước hết là về mẫu. Mười bốn nước và khối khu vực tham gia một bàn tròn do IMF tổ chức là một mẫu **tự chọn**: đây là nhóm đã quan tâm đủ để dành thời gian tham dự. Nên các tỷ lệ này mô tả sự hội tụ trong nhóm nhiệt tình, không mô tả xu hướng toàn cầu. Nước đã quyết định không làm gì thì không có mặt ở bàn tròn, và sự vắng mặt của họ không được tính vào mẫu số.

Trong các con số đó, hai con số đặt cạnh nhau tạo thành một cảnh báo. **Sáu mươi tư phần trăm đang theo đuổi chức năng ngoại tuyến** — trong khi chính tài liệu xác định chức năng ngoại tuyến là một trong các rủi ro toàn vẹn đáng kể nhất, vì việc sàng lọc trừng phạt trên thực tế chỉ diễn ra khi thiết bị kết nối lại, và phát hiện hậu kiểm thì không ngăn được giao dịch đã xảy ra. **Năm mươi phần trăm chưa sửa luật chống rửa tiền**, và nhiều nước có ý định tận dụng khung pháp lý thanh toán hiện có thay vì xây khung riêng.

Nghĩa là đa số đang xây tính năng rủi ro nhất trong khi một nửa chưa động tới khung pháp lý. Đây không phải sự bất cẩn — nó phản ánh một thực tế chính trị: chức năng ngoại tuyến là thứ bán được cho công chúng và cho nhà lập pháp, còn sửa luật chống rửa tiền thì không.

Một chi tiết nữa đáng được chú ý hơn mức nó nhận được: một số nước cởi mở với việc cho **nhà mạng viễn thông** làm trung gian. Đây là lựa chọn thiết kế có hệ quả lớn nhất trong toàn bộ khảo sát. Nhà mạng có mạng lưới phân phối ở đúng nơi ngân hàng không có, nên đó là con đường thực tế duy nhất tới bao trùm tài chính. Nhưng nhà mạng không có văn hoá tuân thủ, không có bộ phận chống rửa tiền, và tài liệu nói rõ rằng **tổ chức tài chính uỷ quyền vẫn chịu trách nhiệm cuối cùng nếu nhà mạng làm sai**. Không ngân hàng nào tự nguyện nhận một cấu trúc trách nhiệm như vậy. Đây mới là ràng buộc thật đang chặn lời hứa bao trùm tài chính, chứ không phải công nghệ.

### Câu bền nhất trong tài liệu không nói về CBDC

"rCBDC không vận hành trong chân không. Điểm yếu và lỗ hổng hiện có trong khung chống rửa tiền của một nước nhiều khả năng sẽ được duy trì và thậm chí trầm trọng thêm."

Đây là câu sẽ còn đúng khi mọi chi tiết kỹ thuật trong tài liệu đã lỗi thời, và phạm vi áp dụng của nó rộng hơn nhiều so với CBDC. Nguyên lý là: **hạ tầng số khuếch đại chất lượng thể chế sẵn có theo cả hai hướng**. Một nước có hệ thống định danh tốt, sổ đăng ký chủ sở hữu hưởng lợi đáng tin và cơ quan giám sát có năng lực thì số hoá sẽ nhân lên các thế mạnh đó. Một nước thiếu những thứ đó thì số hoá chỉ làm cho khuyết điểm chạy nhanh hơn và ở quy mô lớn hơn.

Nó cũng là phiên bản thể chế của một nguyên lý xuất hiện ở dạng vật lý trong phân tích về thanh toán ở nước mong manh: công nghệ nằm ở tầng trên không sửa được khiếm khuyết ở tầng dưới. Ở đó tầng dưới là điện và sóng; ở đây tầng dưới là định danh, hồ sơ và năng lực giám sát. Cùng một cấu trúc lập luận, hai lĩnh vực khác nhau, và nó nên được đọc như một quy tắc chung để đánh giá mọi đề xuất số hoá tài chính.

Hệ quả trực tiếp là khuyến nghị quan trọng nhất của tài liệu cũng là khuyến nghị ít gây hứng thú nhất: **sửa các thiếu sót chống rửa tiền chính trước khi phát hành, chứ không phải bằng việc phát hành**.

### Với Việt Nam: chuỗi ưu tiên đã được tài liệu này viết sẵn

Tài liệu không nhắc tới Việt Nam, nhưng nó mô tả khá chính xác tình huống của một nước có bốn đặc điểm cùng lúc: hệ thống định danh điện tử quốc gia đã phủ rộng và đã liên kết với tài khoản ngân hàng, mạng lưới nhà mạng viễn thông có độ phủ vượt xa mạng lưới chi nhánh ngân hàng ở nông thôn, thí điểm tiền di động do chính các nhà mạng vận hành, và một khung chống rửa tiền từng bị đưa vào diện giám sát tăng cường của FATF và phải chạy một chương trình hành động để khắc phục.

Ghép bốn đặc điểm đó vào phân tích của bài, thứ tự ưu tiên hiện ra khá rõ và nó ngược với thứ tự mà các cuộc thảo luận công khai thường đi.

**Thứ nhất, hệ thống định danh điện tử là tài sản, không phải nền tảng cho một đồng tiền mới.** Điều mà tài liệu mô tả là khó nhất — làm sao thoả mãn thẩm định khách hàng ở tầng thấp nhất mà không phá bao trùm tài chính — thì một nước đã có định danh điện tử phủ rộng gần như đã giải xong. Nhưng chính vì đã giải xong, lý do phải có rCBDC để phục vụ người chưa có tài khoản cũng yếu đi tương ứng: nếu ai cũng định danh được thì ai cũng mở được tài khoản, và bài toán còn lại là mạng lưới nạp rút chứ không phải công cụ.

**Thứ hai, cấu trúc trách nhiệm với nhà mạng là vấn đề phải giải trước, không phải sau.** Mô hình tiền di động do nhà mạng vận hành đặt đúng câu hỏi mà tài liệu nêu: ai là đơn vị báo cáo, ai chịu trách nhiệm cuối cùng khi bên vận hành không phát hiện được giao dịch đáng ngờ, và cơ chế nào buộc nhà mạng thông báo ngay khi có kết quả trúng danh sách trừng phạt. Những câu hỏi này đã tồn tại với tiền di động hiện nay và sẽ chỉ lớn hơn nếu có thêm bất kỳ công cụ nào chạy trên cùng mạng lưới đó.

**Thứ ba, và đây là điểm bài nói thẳng nhất: khắc phục thiếu sót chống rửa tiền là việc phải làm dù có hay không có CBDC**, và làm nó trước sẽ rẻ hơn làm nó sau. Một nước còn đang trong chương trình hành động khắc phục mà phát hành một công cụ tiền tệ mới thì chỉ nhân lên các khuyết điểm đang được yêu cầu sửa, đồng thời tạo thêm một mặt trận đánh giá mới.

Nói gọn: tài liệu này, đọc cho Việt Nam, không phải là hướng dẫn thiết kế rCBDC. Nó là một danh sách kiểm tra về chất lượng khung chống rửa tiền, được viết dưới hình thức một tài liệu về CBDC.

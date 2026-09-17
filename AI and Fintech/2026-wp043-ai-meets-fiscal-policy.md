# AI Meets Fiscal Policy: Mapping Government Spending Actions Across 64 Countries — AI gặp chính sách tài khoá: lập bản đồ hành động chi tiêu chính phủ ở 64 nước

**Nguồn:** IMF Working Paper No. WP/2026/043.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 3, không có trang bìa và trang tác giả).
**Ý chính:** Phương pháp tự sự (narrative) của Romer và Romer rất tốn công người, nên chỉ có dữ liệu cho vài nước và ở tần suất năm. Nhóm tác giả dùng GPT-4.1 với MỘT PROMPT CỐ ĐỊNH đọc báo cáo quốc gia của Economist Intelligence Unit để phân loại hành động chi tiêu là ngoại sinh hay nội sinh, tạo ra bộ dữ liệu QUÝ đầu tiên cho 64 nước từ 1952Q1. AI khớp với mã hoá của chuyên gia trên 93%. Số nhân chi tiêu ở nước trung vị là 0,74 sau một năm và 0,67 sau hai năm.

> **Lưu ý:** bản PDF bắt đầu từ trang 3 (phần Giới thiệu). Trang bìa, tóm tắt và danh sách tác giả không có trong bản này. Tên bài và số hiệu working paper lấy từ trang bìa sau.

## Sơ đồ

### Vấn đề và cách giải quyết

```text
       CÂU HỎI: SỐ NHÂN CHI TIÊU CHÍNH PHỦ của một nước CỤ THỂ là
       bao nhiêu? → có ý nghĩa chính sách lớn suốt hai thập kỷ qua,
       khi nhiều nước tung các gói kích thích lớn để chống KHỦNG
       HOẢNG TÀI CHÍNH TOÀN CẦU và đại dịch COVID-19
       · NHƯNG tài liệu hiện có chủ yếu trả lời cho các nền kinh tế
         CỤ THỂ, phần lớn là TIÊN TIẾN (đặc biệt là MỸ), hoặc đưa ra
         ước tính TRUNG BÌNH cho NHÓM nước
                                │
                                ▼
       VÌ SAO CÓ KHOẢNG TRỐNG? ước lượng số nhân đòi hỏi XÁC ĐỊNH
       các thước đo chi tiêu NGOẠI SINH — bản chất đã khó
       · PHƯƠNG PHÁP TỰ SỰ (narrative) do ROMER và ROMER (2010) tiên
         phong: phân tích TÀI LIỆU LỊCH SỬ, phân loại hành động tài
         khoá theo ĐỘNG CƠ ĐƯỢC NÊU RA
       · phân biệt biện pháp vì lý do DÀI HẠN hoặc THÂM HỤT THỪA KẾ
         với biện pháp ứng phó ĐIỀU KIỆN KINH TẾ HIỆN TẠI → tách
         hành động chính sách ngoại sinh khỏi phản ứng nội sinh
       · phương pháp này TRUNG TÂM của tài liệu hiện đại về truyền
         dẫn tài khoá, NHƯNG TỐN RẤT NHIỀU CÔNG SỨC
                                │
                                ▼
       HỆ QUẢ: bộ dữ liệu tự sự chỉ có cho VÀI NƯỚC (Romer & Romer
       2010 cho Mỹ; Cloyne và cộng sự 2024 cho Anh) hoặc NHÓM NHỎ
       (Guajardo và cộng sự 2014 cho OECD; Adler và cộng sự 2024)
       · các bộ dữ liệu liên quốc gia này CHỈ CÓ TẦN SUẤT NĂM và phủ
         giai đoạn TƯƠNG ĐỐI NGẮN (từ thập niên 1980) → khó phân
         tích chuỗi thời gian
                                │
                                ▼
       ĐÓNG GÓP CỦA BÀI: bộ dữ liệu MỚI về CÚ SỐC CHI TIÊU NGOẠI
       SINH TỰ SỰ — CẢ MỞ RỘNG LẪN THẮT CHẶT — cho bảng KHÔNG CÂN
       BẰNG gồm 64 NƯỚC, tần suất QUÝ, bắt đầu từ 1952Q1
       → ĐÂY LÀ NỖ LỰC ĐẦU TIÊN xây dựng bộ dữ liệu lịch sử về cú
         sốc chi tiêu ngoại sinh ở tần suất quý cho một nhóm LỚN và
         ĐA DẠNG gồm cả nước phát triển lẫn đang phát triển, phủ gần
         như TOÀN BỘ giai đoạn hậu Thế chiến II
```

### Quy trình AI đọc báo cáo

```text
       NGUỒN: BÁO CÁO QUỐC GIA CỦA ECONOMIST INTELLIGENCE UNIT (EIU)
       · EIU làm báo cáo CHUẨN HOÁ cho nhiều nền kinh tế tiên tiến,
         mới nổi và thu nhập thấp, phủ nhiều nước từ THẬP NIÊN 1950
       · thường phát hành QUÝ; một số năm sau có nước theo THÁNG →
         nhóm tác giả xây kho lưu trữ QUÝ với MỘT báo cáo mỗi
         nước–quý (giữ báo cáo TOÀN DIỆN cuối cùng trong quý; khi có
         cả "Updater" ngắn và "Main Report" dài thì giữ Main Report)
       · QUY TRÌNH BIÊN TẬP TẬP TRUNG: chuyên gia quốc gia soạn thảo
         từ nguồn địa phương → chuyên gia rà soát → biên tập để rõ
         ràng và nhất quán nội bộ → CHUẨN HOÁ này rất có giá trị
       · so với báo cáo OECD và nhiều báo cáo IMF, EIU cho TẦN SUẤT
         CAO HƠN và CHUỖI LỊCH SỬ DÀI cho nhiều nước, kể cả mới nổi
         và thu nhập thấp
       · kho EIU đầy đủ phủ hơn 140 nền kinh tế, nhưng phân tích tập
         trung vào 64 NƯỚC có dữ liệu vĩ mô và tài khoá quý nhất quán
                                │
                                ▼
       BỐN "YÊU CẦU" của ROMER và ROMER (2023) mà bài tuân thủ:
       ① nguồn tự sự ĐÁNG TIN CẬY ② ý tưởng RÕ RÀNG về thông tin cần
       tìm ③ cách tiếp cận VÔ TƯ và NHẤT QUÁN ④ TÀI LIỆU HOÁ cẩn thận
       bằng chứng tự sự
                                │
                                ▼
       ĐỊNH NGHĨA NGOẠI SINH: một hành động tài khoá là NGOẠI SINH
       khi ĐỘNG CƠ ĐƯỢC NÊU RA KHÔNG liên quan đến điều kiện vĩ mô
       ĐƯƠNG THỜI · hai nhóm động cơ thoả tiêu chí này:
       · biện pháp xử lý MẤT CÂN ĐỐI TÀI KHOÁ THỪA KẾ
       · biện pháp phản ánh MỤC TIÊU DÀI HẠN về quy mô hay thành
         phần khu vực công (tăng trưởng, công bằng, thiết kế thể chế)
       → cả hai đều TRỰC GIAO với động cơ ổn định dao động NGẮN HẠN
                                │
                                ▼
       PROMPT CỐ ĐỊNH GPT-4.1 — giữ NGUYÊN VẸN qua mọi nước và thời
       gian, mô hình dùng NGUYÊN BẢN, KHÔNG huấn luyện hay tinh
       chỉnh cho nhiệm vụ → ngăn việc điều chỉnh theo mẫu và THIÊN
       LỆCH NHÌN TRƯỚC, đồng thời cho phép người khác TÁI LẶP
       · NHIỆM VỤ: "Đọc trích đoạn báo cáo EIU cho nước C và quý Q.
         Xác định các hành động chi tiêu chính phủ ngoại sinh trong
         Q dựa trên các động cơ nêu ra trong văn bản, và tóm tắt tác
         động định hướng ròng lên chi tiêu."
       · ĐỊNH NGHĨA NGOẠI SINH trong prompt: chỉ phân loại ngoại sinh
         nếu động cơ RÕ RÀNG không liên quan diễn biến vĩ mô ngắn
         hạn · động cơ phi chu kỳ điển hình: mục tiêu CỦNG CỐ TRUNG
         HẠN, mục tiêu TƯ TƯỞNG hay CƠ CẤU DÀI HẠN, TUÂN THỦ luật,
         hiệp ước hay quy tắc siêu quốc gia · nếu văn bản nói hành
         động nhằm chống SUY THOÁI/tăng trưởng chậm, giảm THẤT
         NGHIỆP, làm nguội QUÁ NÓNG, hay ứng phó LẠM PHÁT, LÃI SUẤT,
         ÁP LỰC TỶ GIÁ, CĂNG THẲNG TÀI TRỢ đương thời → coi là NỘI
         SINH · việc THỪA NHẬN điều kiện hiện tại tự nó KHÔNG hàm ý
         nội sinh nếu động cơ nêu ra rõ ràng là phi chu kỳ
                                │
                                ▼
       ĐẦU RA của prompt:
       ① EXOG_NET_SPENDING ∈ {EXP_, CON_, NEUTRAL, UNCLEAR}
       ② MOTIVATION: cụm từ ngắn nêu động cơ
       ③ COMPONENT: thành phần chi tiêu được nhắc đến
       ④ INTENSITY_ORDINAL ∈ {−10,…,10}: cường độ định hướng
       ⑤ CONFIDENCE: tự đánh giá độ tin cậy
       → GHI CHÚ: phân loại NGHIÊM NGẶT theo văn bản cung cấp; KHÔNG
         suy diễn động cơ không nêu ra; nếu hướng không được văn bản
         hỗ trợ thì trả về NEUTRAL hoặc UNCLEAR
                                │
                                ▼
       XÂY DỰNG CÚ SỐC: gộp đầu ra cấp báo cáo thành proxy nước–quý
              z(i,t) = +1 nếu EXP_ · −1 nếu CON_ · 0 nếu NEUTRAL/UNCLEAR
       → ÁNH XẠ THẬN TRỌNG: bất cứ khi nào động cơ KHÔNG rõ ràng phi
         chu kỳ, hoặc báo cáo gắn hành động với tăng trưởng, thất
         nghiệp, lạm phát, lãi suất, áp lực tỷ giá hay căng thẳng tài
         trợ đương thời → phân loại là PHI NGOẠI SINH, không đóng góp
         vào hiệu ứng ròng
       · nhóm tác giả GIỮ LẠI các trích đoạn NGUYÊN VĂN kích hoạt mỗi
         phân loại và công bố cùng chuỗi đã mã hoá, để MINH BẠCH và
         TÁI LẶP
```

### Bốn phép kiểm chứng

```text
       ❶ SO VỚI MÃ HOÁ CỦA CHUYÊN GIA — ROMER và ROMER (2019), viết
       tắt RR19, nghiên cứu phản ứng tài khoá trong các đợt CĂNG
       THẲNG TÀI CHÍNH ở 31 nước OECD giai đoạn 1980–2017, dùng
       CHÍNH các báo cáo EIU · với mỗi đợt họ xem một chuỗi báo cáo
       cố định (thường chín) và trả lời BỐN câu hỏi
       → nhóm tác giả thiết kế prompt phản chiếu bốn câu hỏi đó và
         áp dụng lên CÙNG bộ báo cáo EIU mà RR19 dùng, cho CÙNG 19
         nước (200 báo cáo)
       · KẾT QUẢ MỞ RỘNG: AI khớp LẬP TRƯỜNG 14/16 ca (87,5%) và
         ĐỘNG CƠ 32/34 ca (94,1%)
       · KẾT QUẢ THẮT CHẶT: khớp HƯỚNG 18/19 ca (95%) và ĐỘNG CƠ
         44/45 ca (97,8%)
       → TỔNG THỂ AI KHỚP MÃ HOÁ CHUYÊN GIA TRÊN 93%
       · QUAN TRỌNG: các "bất đồng" KHÔNG đến từ việc không diễn giải
         được văn bản, mà từ các báo cáo mô tả ĐỒNG THỜI cả biện pháp
         mở rộng lẫn thắt chặt · mô hình nhìn chung trích xuất chính
         xác từng hành động và dấu của chúng, NHƯNG vì độ lớn KHÔNG
         quan sát được và cách phân loại CỐ Ý THẬN TRỌNG, lập trường
         ròng có thể khác phán đoán HẬU NGHIỆM của RR19 (Thổ Nhĩ Kỳ,
         Iceland) · Na Uy là ca BIÊN GIỚI về việc hỗ trợ khu vực tài
         chính có được coi là chi tiêu tài khoá không
       · CHỈ CÓ HAI LỖI THẬT SỰ: (i) Hàn Quốc, mô hình bỏ sót gợi ý
         động cơ chính trị rõ ràng ("với con mắt hướng về bầu cử...");
         (ii) mục Mỹ trong Bảng 4, mô hình liệt kê đúng các biện pháp
         nhưng suy ra lập trường tổng thể từ nhận xét về thâm hụt
         tăng và gán SAI DẤU hiệu ứng ròng
                                │
                                ▼
       ❷ KHẢ NĂNG TÁI LẶP — chạy lại prompt 51 LẦN trên 20 báo cáo
       · thước đo: TỶ TRỌNG MODE (modal share) = tỷ lệ số lần chạy
         trả về giá trị xuất hiện nhiều nhất; bằng 1 là hoàn hảo
       · HƯỚNG của lập trường tài khoá: HOÀN TOÀN ỔN ĐỊNH — cả 20 báo
         cáo đều có tỷ trọng mode bằng 1
       · ĐỘNG CƠ: thấp hơn một chút nhưng vẫn CAO
       · CƯỜNG ĐỘ và ĐỘ TIN CẬY: tái lặp THẤP HƠN, một số ca phân
         tán đáng kể
       → MÔ HÌNH NÀY KHÔNG BẤT NGỜ: hướng là phân loại THÔ, nhị phân,
         gắn chặt với tự sự định tính · động cơ là cấu trúc ĐA HẠNG
         MỤC và thường ĐA DIỆN (một hành động có thể phục vụ nhiều
         mục tiêu) · cường độ và độ tin cậy đòi hỏi phán đoán ĐỊNH
         LƯỢNG TINH TẾ HƠN, vốn nhạy hơn với cách diễn đạt và mơ hồ
       → KẾT LUẬN: phân loại bằng AI RẤT VỮNG ở chiều QUAN TRỌNG
         NHẤT cho nhận dạng tự sự là HƯỚNG chính sách tài khoá
                                │
                                ▼
       ❸ SO VỚI DỮ LIỆU CHI TIÊU THỰC TẾ — ước lượng local projection
       · TẠI THỜI ĐIỂM TÁC ĐỘNG (h=0): thắt chặt (cú sốc âm) làm
         giảm log G khoảng −0,005 (điểm log; mức 0,5%)
       · mở rộng (+1) tăng MUỘN HƠN MỘT QUÝ với hệ số ≈ 0,002
       · TÍCH LUỸ: thắt chặt đạt khoảng −0,06 vào h≈8; mở rộng đạt
         khoảng 0,04 trong cùng giai đoạn
                                │
                                ▼
       ❹ ĐỐI CHIẾU VỚI ADLER và cộng sự (2024) — bộ dữ liệu NĂM về
       quy mô gói CỦNG CỐ TÀI KHOÁ công bố cho 31 nước, tính theo %
       GDP, chỉ gồm biện pháp chủ yếu vì GIẢM THÂM HỤT TRUNG HẠN
       · TEST 1 (BIÊN MỞ RỘNG): với ngưỡng τ = 0,5% GDP có 138
         nước–năm được Adler phân loại là năm củng cố · trong 96,4%
         số ca, dữ liệu quý của bài ghi nhận ÍT NHẤT MỘT quý thắt
         chặt · với gói lớn hơn (τ = 1,0 và 2,0), tỷ lệ trúng vẫn
         trên 96% và đạt 100% ở τ = 2,0 · theo nhóm nước: Mỹ Latinh
         và Caribe trúng 100% ở mọi ngưỡng; nước tiên tiến trên 95%
       · 23–25% các năm "củng cố lớn" này CŨNG chứa ít nhất một quý
         mở rộng → phản ánh HỖN HỢP TRONG NĂM: chính phủ thường thực
         hiện nhiều hành động khác dấu trong cùng năm dương lịch
       · TEST 2 (XÁC SUẤT): mô hình xác suất tuyến tính có hiệu ứng
         cố định quốc gia · hệ số any_consol = 0,126 (sai số 0,019)
         → quan sát ít nhất một quý thắt chặt gắn với xác suất CAO
         HƠN 12,6 ĐIỂM PHẦN TRĂM rằng Adler phân loại năm đó là củng
         cố lớn · hệ số any_expand = −0,073 (sai số 0,02)
       · TEST 3 (CƯỜNG ĐỘ): hệ số net_stance = 0,263 (sai số 0,044)
         → đi từ năm THUẦN MỞ RỘNG (−1) sang năm THUẦN CỦNG CỐ (+1)
         gắn với mức tăng khoảng 0,5 ĐIỂM PHẦN TRĂM GDP trong quy mô
         củng cố dựa trên chi tiêu
       → KẾT LUẬN: cả hai nguồn nắm bắt CÙNG MỘT đối tượng chính sách
         — các dịch chuyển tuỳ nghi trong lập trường chi tiêu của
         chính phủ nhằm điều chỉnh tài khoá trung hạn — dù khác nhau
         về TẦN SUẤT, PHẠM VI và THIẾT KẾ MÃ HOÁ
```

### Dữ liệu thu được và tính không dự đoán được

```text
       THỐNG KÊ MÔ TẢ
       · XỬ LÝ 16.029 quan sát nước–quý
       · XÁC ĐỊNH 8.636 đợt chi tiêu tuỳ nghi = 53,9% mẫu
       · 4.374 MỞ RỘNG và 4.262 THẮT CHẶT → mở rộng chiếm 50,6% số
         quan sát khác không
       · GIAI ĐOẠN: 1952Q1–2023Q4 (bảng không cân bằng, ngày bắt đầu
         mỗi nước khác nhau)
       · sự cân bằng gần như hoàn hảo giữa mở rộng và thắt chặt
         (50,6% so với 49,4%) HỮU ÍCH cho chiến lược nhận dạng dựa
         vào BIẾN THIÊN DẤU thay vì độ lớn
                                │
                                ▼
       KHÁC BIỆT GIỮA CÁC NHÓM THU NHẬP
       · TIÊN TIẾN: 3.129 quý khác không, tỷ lệ mở rộng 45,8% → nhiều
         THẮT CHẶT hơn (54,2%), có thể phản ánh việc áp dụng QUY TẮC
         TÀI KHOÁ rộng rãi hơn ở các nước này
       · MỚI NỔI: 3.587 quý, tỷ lệ mở rộng 49,5% → gần như cân bằng
       · THU NHẬP THẤP: 1.920 quý (22,2% tổng), tỷ lệ mở rộng 60,7%
         → ĐA SỐ biện pháp là MỞ RỘNG · con số này làm nổi bật GIÁ
         TRỊ GIA TĂNG của việc mở rộng phạm vi tự sự ra ngoài nhóm
         tiên tiến và mới nổi
                                │
                                ▼
       ĐỘNG CƠ ĐẰNG SAU HÀNH ĐỘNG — phân tích mẫu con ngẫu nhiên
       bằng từ điển dựa trên văn bản → MỘT SỰ BẤT ĐỐI XỨNG RÕ RỆT
       · MỞ RỘNG gắn áp đảo với tăng ĐẦU TƯ CÔNG, đặc biệt HẠ TẦNG và
         dự án vốn — chiếm gần 60% số đợt mở rộng
       · THẮT CHẶT bị chi phối bởi biện pháp CỦNG CỐ RÕ RÀNG như kìm
         hãm chi tiêu và giảm thâm hụt — chiếm hơn HAI PHẦN BA số
         đợt thắt chặt
       · các hạng mục khác (chi xã hội, tư nhân hoá, tài trợ bên
         ngoài) đóng vai trò THỨ YẾU và xuất hiện ở cả hai
       → MỞ RỘNG VÀ CỦNG CỐ KHÔNG PHẢI LÀ HÌNH ẢNH PHẢN CHIẾU CỦA
         NHAU: mở rộng chủ yếu do ĐẦU TƯ dẫn dắt, thắt chặt chủ yếu
         phản ánh nỗ lực GIẢM THÂM HỤT có chủ ý
                                │
                                ▼
       TÍNH KHÔNG DỰ ĐOÁN ĐƯỢC — mối lo do JORDÀ và TAYLOR (2015) nêu
       ra: cú sốc tự sự từ phiên bản trước của Adler (tức Guajardo và
       cộng sự 2014) CÓ THỂ DỰ BÁO ĐƯỢC bằng các chỉ báo vĩ mô chuẩn
       · hồi quy z(i,t) lên nợ/GDP, chênh lệch sản lượng, tăng trưởng
         GDP (đều trễ một quý) và cú sốc trễ
       · KẾT QUẢ: qua cả ba mẫu, yếu tố dự báo VỮNG DUY NHẤT là CHÍNH
         ĐỘ TRỄ CỦA NÓ · các hệ số của nợ/GDP, chênh lệch sản lượng
         và tăng trưởng GDP KHÔNG phân biệt được với không · R² ≤ 0,1
       · ĐỐI CHIẾU: cú sốc tự sự NĂM của Adler có R² 0,243–0,305, và
         tăng trưởng GDP trễ CŨNG góp phần dự báo
       · KIỂM TRA THÊM: gộp cú sốc quý thành năm (thang −4 đến +4) →
         tính dự đoán được TĂNG RÕ (R² 0,125); nợ/GDP trễ và tăng
         trưởng GDP trễ trở thành yếu tố dự báo có ý nghĩa thống kê
       → tính không dự đoán được yếu ở tần suất QUÝ phản ánh bản chất
         TẦN SUẤT CAO của thước đo; thông tin hệ thống về điều kiện
         vĩ mô DỄ PHÁT HIỆN HƠN khi cùng hành động đó được nhìn ở
         tần suất năm
```

### Ước lượng số nhân và kết quả

```text
       CHIẾN LƯỢC NHẬN DẠNG: mỗi nước một VAR BAYES nhỏ
              x(t) = [ z(t), g(t), y(t) ]
       với z là proxy tự sự, g = log chi tiêu chính phủ thực,
       y = log GDP thực · độ trễ p = 8 · proxy XẾP ĐẦU TIÊN
       · CÔNG CỤ NỘI SINH (internal instrument) theo PLAGBORG-MØLLER
         và WOLF (2021): cú sốc là ĐỔI MỚI TRỰC GIAO THỨ NHẤT (cú
         sốc Cholesky đầu tiên) — nó có thể ảnh hưởng mọi biến còn
         lại ĐỒNG THỜI, trong khi các đổi mới khác bị ràng buộc KHÔNG
         có hiệu ứng tác động lên proxy
       · GIẢI QUYẾT HẠN CHẾ CỐT LÕI: khác Adler, bài KHÔNG quan sát
         được quy mô tính bằng đô la của biện pháp, chỉ HƯỚNG ĐỊNH
         TÍNH · trong khung này, PHẢN ỨNG ĐỒNG THỜI CỦA CHI TIÊU GHIM
         THANG ĐO của đổi mới cấu trúc → bản chất định tính của proxy
         KHÔNG CÒN QUYẾT ĐỊNH với việc nhận dạng
       · ước lượng Bayes với TIÊN NGHIỆM MINNESOTA (chuẩn ma trận /
         Wishart nghịch đảo), lấy mẫu Gibbs · thêm ĐIỀU KIỆN CHẤP
         NHẬN có động cơ kinh tế (accept–reject) để loại các lượt rút
         mà đổi mới proxy gần như không cung cấp thông tin về chi
         tiêu thực hiện, gây số nhân cực đoan một cách máy móc
       · SỐ NHÂN TÍCH LUỸ ở kỳ hạn h = tỷ lệ phản ứng tích luỹ của
         GDP trên phản ứng tích luỹ của chi tiêu, chia cho TỶ TRỌNG
         CHI TIÊU TRÊN GDP trung bình của nước đó
                                │
                                ▼
       KẾT QUẢ CƠ SỞ — phản ứng xung
       · cú sốc chi tiêu dương kích hoạt mức TĂNG MẠNH và NGAY LẬP
         TỨC của chi tiêu chính phủ, ĐẠT ĐỈNH khoảng 0,4% quanh kỳ
         hạn một năm và duy trì cao qua giai đoạn hai năm
       · phản ứng sản lượng cũng DƯƠNG ở mọi kỳ hạn, dao động 0,06
         đến 0,08%
       · chia nhóm: cú sốc gắn với phản ứng chi tiêu LỚN HƠN ở nền
         kinh tế đang phát triển điển hình so với nước tiên tiến ·
         phản ứng GDP cũng lớn hơn ở nước đang phát triển NHƯNG khác
         biệt KHÔNG có ý nghĩa thống kê (dải tin cậy chồng lấn)
                                │
                                ▼
       SỐ NHÂN TRỌNG SỐ NGHỊCH ĐẢO PHƯƠNG SAI
              Mẫu               1 năm     2 năm
              Toàn mẫu          0,74      0,67
              Nước tiên tiến    0,70      0,61
              EMDE              0,80      0,81
       → nằm GỌN trong khoảng mà tài liệu hiện có báo cáo (Ramey 2019)
       · VÌ SAO số nhân gần nhau dù phản ứng khác nhau? vì TỶ TRỌNG
         CHI TIÊU CHÍNH PHỦ TRÊN GDP — dùng để chia ngược lại khi
         hiệu chỉnh tỷ lệ hai phản ứng — LỚN HƠN NHIỀU ở nước tiên
         tiến trung vị (39%) so với nước đang phát triển trung vị (17%)
       · KHÁC BIỆT TRONG NHÓM RẤT LỚN: khoảng tứ phân vị của số nhân
         mỗi nhóm trải xấp xỉ từ 0 đến 1,5
                                │
                                ▼
       QUÝ SO VỚI NĂM — lợi thế của dữ liệu tần suất cao
              Mẫu            1 năm (Quý/Năm)   2 năm (Quý/Năm)
              Toàn mẫu         0,74 / 0,72      0,67 / 0,61
              Tiên tiến        0,70 / 0,84      0,61 / 0,63
              EMDE             0,80 / 0,58      0,81 / 0,60
       → khác biệt ĐÁNG KỂ giữa hai tần suất, nhấn mạnh THIÊN LỆCH
         TIỀM TÀNG khi dùng dữ liệu năm · HAI YẾU TỐ:
       ① cú sốc NĂM dễ dự đoán hơn → thiên lệch do BỎ SÓT BIẾN vĩ mô
       ② ngay cả khi cú sốc không dự đoán được, BẢN THÂN VIỆC GỘP đã
         gây thiên lệch · STRAM và WEI (1986): nếu quá trình sinh dữ
         liệu thật ở tần suất quý là TỰ HỒI QUY (AR), việc gộp lên
         năm biến nó thành TỰ HỒI QUY TRUNG BÌNH TRƯỢT (ARMA) · ước
         lượng VAR ở cấp năm mà bỏ qua thành phần MA dẫn đến SAI ĐẶC
         TẢ MÔ HÌNH và ước lượng thiên lệch
```

### Khác biệt giữa các nước và theo trạng thái

```text
       ❶ ĐẶC ĐIỂM CƠ CẤU CHẬM THAY ĐỔI (bảng panel gộp, theo khung
       của ILZETZKI, MENDOZA và VEGH 2013 — viết tắt IMV)
              Nhóm                    M4       M8
              ĐỘ MỞ THƯƠNG MẠI
                Đóng (26 nước)       1,425    1,364
                Mở (34 nước)         0,558    0,649
              NỢ CÔNG
                Thấp (56)            0,738    0,893
                Cao (26)             0,821    0,851
              CHẾ ĐỘ TỶ GIÁ
                Cố định (51)         1,104    1,119
                Thả nổi (8)          0,715    0,703
              PHI CHÍNH THỨC
                Thấp (28)            1,173    1,195
                Cao (28)             0,788    0,798
              LINH HOẠT LAO ĐỘNG
                Thấp (25)            1,439    1,347
                Cao (24)             1,560    1,662
       → ĐỘ MỞ tái hiện quy luật trung tâm của IMV: số nhân NHỎ HƠN
         ở nền kinh tế MỞ HƠN · nhất quán với logic RÒ RỈ NHẬP KHẨU —
         phần lớn hơn của cầu thêm bị NHẬP KHẨU hấp thụ
       → TỶ GIÁ cho quy luật IMV kinh điển còn lại: số nhân LỚN HƠN
         dưới chế độ CỐ ĐỊNH · với thả nổi, ước lượng điểm nhỏ hơn
         nhưng suy luận YẾU HƠN NHIỀU vì mẫu chỉ có 8 nước và khoảng
         90% chứa số không → coi kết quả này chủ yếu là bằng chứng
         mạnh về THỨ HẠNG (cố định trên thả nổi)
       → NỢ: khác biệt HẠN CHẾ trong khung này; số nhân biến thiên
         mạnh hơn theo độ mở và chế độ tỷ giá hơn là theo trạng thái nợ
       → PHI CHÍNH THỨC nổi lên như một BIÊN QUAN TRỌNG VỀ LƯỢNG cho
         truyền dẫn tài khoá (đo bằng chỉ số Medina và Schneider 2018)
       → LAO ĐỘNG LINH HOẠT HƠN cho số nhân lớn hơn, khoảng cách
         khiêm tốn ở một năm nhưng rõ hơn ở hai năm (đo bằng chỉ số
         bảo vệ việc làm của Alesina và cộng sự 2024)
                                │
                                ▼
       ❷ TRẠNG THÁI CHU KỲ KINH DOANH — VAR panel chuyển tiếp trơn
       (smooth transition), theo cách của AUERBACH và GORODNICHENKO
       (2012), với hàm logistic áp lên tăng trưởng sản lượng trễ
              Đặc tả             1 năm (Cao/Thấp)  2 năm (Cao/Thấp)
              VAR Δlog          −0,01 / 0,77      −0,01 / 0,77
              VAR log mức        0,25 / 0,74       0,58 / 1,39
       → số nhân MẠNH HƠN trong môi trường TĂNG TRƯỞNG YẾU
       · NHƯNG khác biệt CHỈ GỢI Ý, chưa ước lượng chính xác: chỉ bác
         bỏ được giả thuyết bằng nhau ở mức tin cậy khoảng 10% cho
         đặc tả cơ sở ở kỳ hạn một năm (p = 0,11)
                                │
                                ▼
       ❸ BẤT ĐỊNH CHÍNH SÁCH — dùng CHỈ SỐ BẤT ĐỊNH THẾ GIỚI (WUI)
       của AHIR và cộng sự (2022), đếm tần suất từ "uncertain" trong
       CHÍNH các báo cáo EIU, và chỉ số BẤT ĐỊNH TẬP TRUNG VÀO CHÍNH
       SÁCH TÀI KHOÁ (FUI) dùng cùng cách khai thác văn bản
              Kỳ hạn      WUI (Thấp/Cao)    FUI (Thấp/Cao)
              1 năm       1,04 / 0,51       0,95 / 0,21
              2 năm       1,09 / 0,42       1,13 / 0,18
       → dưới CẢ HAI khái niệm bất định, BẤT ĐỊNH CAO gắn với TRUYỀN
         DẪN TÀI KHOÁ YẾU HƠN · khoảng tin cậy bootstrap cho hiệu số
         cao trừ thấp RỘNG và chứa số không, phản ánh độ chính xác
         hạn chế khi chia mẫu theo trạng thái
                                │
                                ▼
       ❹ ỦNG HỘ CHÍNH TRỊ — mã hoá thêm một chỉ báo tự sự về việc
       môi trường chính trị có THUẬN LỢI cho việc thông qua và duy
       trì biện pháp tài khoá không, cũng bằng prompt LLM cố định
       đọc phần "Domestic politics" của báo cáo EIU
       · Supp = 1 khi CẢ BA điều kiện cùng đúng: hành pháp được ĐA SỐ
         LÀM VIỆC trong lập pháp hậu thuẫn; KHÔNG có bầu cử quốc gia
         trong quý này hoặc quý tới; báo cáo KHÔNG nêu bật bất ổn
         chính trị, bế tắc kéo dài hay tê liệt lập pháp đáng kể
       · thiếu văn bản chính trị được xử lý như MỘT TRẠNG THÁI RIÊNG,
         không quy về nhóm bất lợi
              Kỳ hạn   Supp=0   Supp=1   Thiếu
              h = 4      –      1,0590   1,1078
              h = 8    0,1880   0,9627  −0,6868
       → trong môi trường chính trị THUẬN LỢI, số nhân nhất quán
         dương và có ý nghĩa kinh tế, khoảng 1,0–1,1 · dưới ủng hộ
         BẤT LỢI, số nhân gần bằng không
       · CƠ CHẾ: động lực chính của sự phụ thuộc trạng thái này là
         PHẢN ỨNG CHI TIÊU THỰC HIỆN · chênh lệch dạng rút gọn của
         chi tiêu tích luỹ giữa quý có và không có ủng hộ là LỚN và
         CÓ Ý NGHĨA ở kỳ hạn trung bình: ΔRF = 0,0182 ở h = 4, t = 2,94
       → ủng hộ chính trị LÀM TĂNG KHẢ NĂNG các hành động chi tiêu đã
         công bố hay đã lập pháp ĐƯỢC THỰC THI và DUY TRÌ
                                │
                                ▼
       CHIỀU NÀO QUAN TRỌNG? tách "ủng hộ" thành ba thành tố nguyên
       thuỷ: ĐA SỐ/GẮN KẾT, BẦU CỬ SẮP TỚI, BẤT ỔN/BẾ TẮC
              Kỳ hạn   z×Supp        z×BầuCử        Ròng
              h = 4   0,02044(2,17) −0,01956(−2,20) 0,00088
              h = 8   0,01955(2,26) −0,01834(−2,75) 0,00121
       → ngay cả khi kiểm soát các thành tố, ỦNG HỘ THUẬN LỢI vẫn gắn
         với phản ứng chi tiêu MẠNH HƠN đáng kể
       → BẦU CỬ SẮP TỚI độc lập gắn với TRUYỀN DẪN CHI TIÊU YẾU HƠN
         HẲN · độ lớn TƯƠNG ĐƯƠNG, hàm ý BẦU CỬ SẮP TỚI CÓ THỂ GẦN
         NHƯ TRIỆT TIÊU lợi thế thực thi mà ủng hộ chính trị mang lại
       · KIỂM TRA: thành phần dấu của cú sốc GẦN NHƯ Y HỆT giữa các
         trạng thái ủng hộ (tỷ lệ z = −1 là 0,551 khi Supp=0 và 0,546
         khi Supp=1) → kết quả KHÔNG do chọn lọc dấu đơn giản
       · TÁCH BẠCH: biến bối cảnh chính trị KHÔNG BAO GIỜ được dùng
         để phân loại hành động tài khoá là ngoại sinh hay nội sinh ·
         sàng lọc ngoại sinh CHỈ dựa vào động cơ nêu ra trong văn bản
         tài khoá; biến chính trị chỉ dùng để ĐÁNH CHỈ SỐ môi trường
```

## Ba câu hỏi bài viết trả lời

1. Làm sao dùng AI để tạo bộ dữ liệu cú sốc chi tiêu ngoại sinh ở tần suất quý cho nhiều nước?
2. Bộ dữ liệu đó có đáng tin không, và số nhân chi tiêu ở từng nước là bao nhiêu?
3. Số nhân thay đổi thế nào theo đặc điểm cơ cấu, chu kỳ, bất định và điều kiện chính trị?

## Dàn ý chi tiết

### 1. Khoảng trống trong tài liệu

- Số nhân chi tiêu chính phủ của một nước cụ thể là bao nhiêu? Câu hỏi này đã có ý nghĩa chính sách đáng kể trong hai thập kỷ qua, khi nhiều nước thực hiện các gói kích thích lớn để chống lại tác động của các cuộc suy thoái lớn như Khủng hoảng Tài chính Toàn cầu và đại dịch COVID-19. Dù đã có nhiều nghiên cứu về chủ đề này, tài liệu hiện có chủ yếu đưa ra câu trả lời cho các nền kinh tế cụ thể, phần lớn là tiên tiến (đáng chú ý là Mỹ), hoặc đưa ra ước tính số nhân trung bình cho các nhóm nước.
- Lý do chính của khoảng trống này là việc ước lượng số nhân chi tiêu đòi hỏi xác định các thước đo chi tiêu chính phủ ngoại sinh, điều vốn khó về bản chất. Một cách tiếp cận nổi bật là phương pháp tự sự do Romer và Romer (2010) tiên phong, phân tích các tài liệu lịch sử để phân loại hành động tài khoá dựa trên động cơ được nêu ra. Bằng cách phân biệt các biện pháp thực hiện vì lý do dài hạn hoặc thâm hụt thừa kế với các biện pháp ứng phó điều kiện kinh tế hiện tại, cách tiếp cận tự sự tách các hành động chính sách ngoại sinh khỏi các phản ứng nội sinh. Phương pháp này đã là trung tâm của tài liệu hiện đại về truyền dẫn tài khoá, nhưng nó tốn rất nhiều công sức.
- Không ngạc nhiên, các bộ dữ liệu về biện pháp tài khoá ngoại sinh xác định bằng cách tiếp cận tự sự chỉ có cho một vài nước cụ thể (Romer và Romer 2010 cho Mỹ, Cloyne và cộng sự 2024 cho Anh), hoặc cho một nhóm nước tương đối nhỏ (Guajardo và cộng sự 2014 cho các nền kinh tế OECD; Adler và cộng sự 2024 cho một tập hợp nền kinh tế OECD và nước khác). Tuy nhiên, các bộ dữ liệu liên quốc gia này chỉ có ở tần suất năm và phủ một giai đoạn tương đối ngắn (từ thập niên 1980), khiến phân tích chuỗi thời gian trở nên khó khăn.
- Để lấp khoảng trống này, bài xây dựng một bộ dữ liệu mới về các cú sốc chi tiêu chính phủ ngoại sinh tự sự, cả mở rộng lẫn thắt chặt, cho một bảng không cân bằng gồm 64 nước ở tần suất quý bắt đầu từ 1952Q1. Đây là nỗ lực đầu tiên phát triển một bộ dữ liệu lịch sử về cú sốc chi tiêu ngoại sinh ở tần suất quý cho một nhóm lớn và đa dạng các nước phát triển và đang phát triển, phủ gần như toàn bộ giai đoạn hậu Thế chiến II.

### 2. Xây dựng cơ sở dữ liệu tự sự bằng AI

- **Nguồn dữ liệu.** Nguồn tự sự chính là Báo cáo Quốc gia của Economist Intelligence Unit (EIU). EIU sản xuất các báo cáo quốc gia chuẩn hoá cho một tập hợp rộng các nền kinh tế tiên tiến, mới nổi và thu nhập thấp, với phạm vi phủ cho nhiều nước kéo dài về tận thập niên 1950. Báo cáo thường phát hành theo quý; trong những năm sau một số nước được phủ ở tần suất tháng. Để nhất quán, nhóm tác giả xây dựng một kho lưu trữ quý với một báo cáo cho mỗi nước–quý. Khi có nhiều báo cáo trong một quý, họ giữ báo cáo toàn diện cuối cùng về mặt thời gian được phát hành trong quý đó, vì phạm vi phủ chồng lấn cung cấp ít thông tin bổ sung về hành động chính sách tài khoá và động cơ được nêu ra.
- Báo cáo EIU tuân theo một quy trình biên tập tập trung thúc đẩy khả năng so sánh giữa các nước và thời gian. Chuyên gia phân tích quốc gia soạn bản thảo ban đầu dựa trên nguồn địa phương. Bản thảo sau đó được các chuyên gia rà soát và biên tập để rõ ràng và nhất quán nội bộ trước khi xuất bản. Sự chuẩn hoá này có giá trị vì nó tạo thuận lợi cho việc trích xuất có hệ thống các hành động tài khoá và động cơ nêu ra theo một định dạng có thể so sánh được. So với báo cáo OECD và nhiều báo cáo quốc gia của IMF, báo cáo EIU cung cấp phạm vi phủ tần suất cao hơn cho nhiều nền kinh tế và chuỗi thời gian lịch sử dài cho một mặt cắt ngang rộng các nước, kể cả nền kinh tế mới nổi và thu nhập thấp.
- **Thông tin cần tìm.** Mục tiêu là xác định các hành động chi tiêu chính phủ tuỳ nghi "ngoại sinh". Theo Romer và Romer (2010), một hành động tài khoá được coi là ngoại sinh khi động cơ được nêu ra không liên quan đến điều kiện vĩ mô đương thời. Trong nghiên cứu tự sự về Mỹ của họ, Romer và Romer nhấn mạnh hai nhóm động cơ thoả tiêu chí này: các biện pháp thực hiện để xử lý một mất cân đối tài khoá thừa kế; và các biện pháp phản ánh mục tiêu dài hạn về quy mô hay thành phần của khu vực công (tăng trưởng, công bằng, thiết kế thể chế). Cả hai động cơ đều trực giao với các động cơ liên quan đến ổn định dao động ngắn hạn.
- **Cách tiếp cận vô tư và nhất quán.** Nhóm tác giả dùng một prompt GPT-4.1 cố định để xác định các hành động tài khoá và phân loại chúng là nội sinh hay ngoại sinh. Để duy trì nhất quán, đặc tả prompt và quy tắc mã hoá giữ nguyên vẹn qua các nước và theo thời gian, với mô hình được dùng nguyên bản, không có huấn luyện hay tinh chỉnh cho nhiệm vụ cụ thể. Cách tiếp cận này ngăn việc điều chỉnh riêng cho mẫu và thiên lệch nhìn trước, đồng thời cho phép các nhà nghiên cứu khác tái lặp.
- Prompt cũng ghi lại liệu các biện pháp được xác định có được thực hiện trong quý hiện tại hay được công bố cho các quý tương lai. Các trường này được giữ để kiểm toán và kiểm tra vững. Tuy nhiên, chuỗi kinh tế lượng cơ sở dùng trong VAR chỉ dựa vào phân loại dấu rời rạc (mở rộng, thắt chặt, hoặc không hành động).
- **Xây dựng cú sốc.** Đầu ra cấp báo cáo được gộp thành một proxy nước–quý z(i,t) nhận giá trị +1 nếu mở rộng, −1 nếu thắt chặt, và 0 nếu trung tính hay không rõ. Ánh xạ này thận trọng: bất cứ khi nào động cơ nêu ra không rõ ràng là phi chu kỳ, hoặc khi báo cáo gắn hành động với tăng trưởng, thất nghiệp, lạm phát, lãi suất, áp lực tỷ giá hay căng thẳng tài trợ đương thời, prompt phân loại hành động là phi ngoại sinh và nó không đóng góp vào hiệu ứng ròng.
- Báo cáo mô tả các hành động chính sách tuỳ nghi khi chúng được công bố, lập pháp và thực hiện, nhưng khó tách bạch sạch sẽ giữa thời điểm công bố ("tin tức") và thời điểm thực hiện. Cơ sở dữ liệu không thực hiện việc tách công bố/thực hiện ở giai đoạn phân loại. Do đó z(i,t) được diễn giải là một proxy định tính cho các hành động chi tiêu tuỳ nghi được ghi lại theo thời gian thực, có thể phản ánh một hỗn hợp các yếu tố công bố và thực hiện.
- **Ví dụ các đợt tự sự.** *Ví dụ 1 (ý tưởng dài hạn; mở rộng), Ghana 2010Q3:* Quốc hội thông qua một thoả thuận nhà ở gây tranh cãi trị giá 10 tỷ USD với công ty xây dựng Hàn Quốc STX Korea vào đầu tháng Tám. Lập trường: Mở rộng; Động cơ: mục tiêu nêu ra là mở rộng nguồn cung nhà ở và năng lực hạ tầng. Độ tin cậy: 95%. *Ví dụ 2 (thâm hụt thừa kế; thắt chặt), Ecuador 1982Q4:* Nhà chức trách bỏ trợ cấp xăng và lúa mì nhập khẩu như một phần của củng cố tài khoá; động cơ là kiềm chế áp lực ngân sách và cải thiện tính bền vững. Độ tin cậy: 90%. *Ví dụ 3 (không hành động), Anh 2005Q4:* Báo cáo bàn về các điều chỉnh kỹ thuật và việc hoãn lại đã thực hiện ở các quý trước, cùng ý định tương lai, nhưng không có thay đổi chi tiêu rõ ràng nào được xác định.

### 3. Kiểm chứng

- **So với mã hoá của chuyên gia.** Romer và Romer (2019), viết tắt RR19, nghiên cứu các phản ứng chính sách tài khoá trong các đợt căng thẳng tài chính ở 31 nước OECD giai đoạn 1980–2017 dùng bằng chứng tự sự từ chính các Báo cáo Quốc gia EIU. Với mỗi đợt, họ xem xét một chuỗi báo cáo cố định (thường chín, một đợt có mười một) và trả lời bốn câu hỏi về lập trường chính sách tài khoá, động cơ, việc EIU có nhắc đến tỷ lệ nợ trên GDP không, và những điều đáng chú ý khác.
- RR19 cung cấp một chuẩn nghiêm ngặt cho thành phần diễn giải tự sự của cách tiếp cận này. Các phân loại của họ do người đọc chuyên gia tạo ra, dựa trên cùng nguồn tự sự, và quy tắc mã hoá được mô tả minh bạch trong bài của họ. Nhóm tác giả thiết kế một prompt cố định phản chiếu bốn câu hỏi của RR19 và áp dụng nó lên cùng bộ báo cáo EIU mà RR19 dùng cho cùng 19 nước (tổng cộng 200 báo cáo).
- Kết quả: với các đợt mở rộng, AI khớp lập trường trong 14 trên 16 ca (87,5%) và động cơ trong 32 trên 34 ca (94,1%). Với các đợt thắt chặt, AI khớp hướng trong 18 trên 19 ca (95%) và động cơ trong 44 trên 45 ca (97,8%). Tổng thể, AI khớp mã hoá chuyên gia với độ chính xác vượt 93%.
- Quan trọng là các "bất đồng" bề ngoài không bắt nguồn từ việc không diễn giải được văn bản, mà nảy sinh ở các báo cáo mô tả đồng thời cả biện pháp mở rộng lẫn thắt chặt. Trong các ca như vậy, mô hình nhìn chung trích xuất chính xác từng hành động và dấu của chúng. Tuy nhiên, vì độ lớn không quan sát được và cách phân loại cố ý thận trọng, lập trường tài khoá ròng do mô hình gán có thể khác phán đoán hậu nghiệm của RR19. Chỉ có hai lỗi thật sự được xác định: ở Hàn Quốc, mô hình bỏ sót một gợi ý động cơ chính trị rõ ràng và do đó phân loại sai lập trường; và ở mục Mỹ trong Bảng 4, dù mô hình liệt kê đúng các biện pháp, nó suy ra lập trường tổng thể từ các nhận xét về thâm hụt tăng và gán sai dấu hiệu ứng ròng.
- **Khả năng tái lặp.** Prompt được chạy lại 51 lần trên một tập con 20 báo cáo. Dấu của lập trường tài khoá giữ nguyên nhất quán cho mọi báo cáo. Thước đo dùng là "tỷ trọng mode", tỷ lệ số lần chạy trong đó giá trị được gán nhiều nhất xuất hiện; bằng một khi cùng một giá trị được trả về ở mọi lần chạy. Kết quả cho thấy một thứ hạng rõ ràng: hướng của lập trường tài khoá hoàn toàn ổn định (cả 20 báo cáo có tỷ trọng mode bằng một); động cơ có khả năng tái lặp thấp hơn một chút nhưng vẫn cao; cường độ và độ tin cậy có khả năng tái lặp thấp hơn. Mô hình này không bất ngờ: hướng là một phân loại thô, nhị phân gắn chặt với tự sự định tính, trong khi cường độ và độ tin cậy đòi hỏi các phán đoán định lượng tinh tế hơn, vốn nhạy hơn với cách diễn đạt, sự nhấn mạnh và mơ hồ.
- **So với dữ liệu chi tiêu thực tế.** Ở thời điểm tác động (h = 0), các đợt thắt chặt (cú sốc âm) làm giảm log G khoảng −0,005 (điểm log, mức 0,5%), trong khi các đợt mở rộng (+1) tăng lên một quý sau đó với hệ số khoảng 0,002. Tích luỹ, thắt chặt đạt khoảng −0,06 vào h ≈ 8, trong khi mở rộng đạt khoảng 0,04 trong cùng giai đoạn.
- **Đối chiếu với Adler và cộng sự (2024).** Nguồn bên ngoài là bộ dữ liệu năm báo cáo, cho 31 nền kinh tế tiên tiến và mới nổi, quy mô công bố của các gói củng cố tài khoá tuỳ nghi, phân tách thành biện pháp thuế và biện pháp chi tiêu, tính theo phần trăm GDP. Ba phép kiểm tra được thực hiện. *Thứ nhất, biên mở rộng:* với ngưỡng 0,5% GDP, có 138 nước–năm mà Adler phân loại là năm củng cố; trong 96,4% các ca này, cơ sở dữ liệu quý ghi nhận ít nhất một quý thắt chặt. Với các gói lớn hơn, tỷ lệ trúng vẫn trên 96% và đạt 100% ở ngưỡng 2,0. *Thứ hai, xác suất:* trong mô hình xác suất tuyến tính có hiệu ứng cố định quốc gia, hệ số trên chỉ báo có quý thắt chặt là 0,126, nghĩa là xác suất cao hơn 12,6 điểm phần trăm rằng Adler phân loại năm đó là củng cố lớn. *Thứ ba, cường độ:* hệ số trên chỉ số lập trường ròng năm là 0,263, nghĩa là đi từ một năm thuần mở rộng sang một năm thuần củng cố gắn với mức tăng khoảng 0,5 điểm phần trăm GDP trong quy mô củng cố.
- Kết quả được diễn giải là bằng chứng rằng, dù khác biệt về tần suất, phạm vi và thiết kế mã hoá, cả hai nguồn nắm bắt cùng một hiện tượng nền tảng: các dịch chuyển tuỳ nghi trong lập trường chi tiêu của chính phủ nhằm điều chỉnh tài khoá trung hạn.

### 4. Đặc điểm dữ liệu

- **Thống kê mô tả.** Trong 16.029 quan sát nước–quý được xử lý, nhóm tác giả xác định 8.636 đợt chi tiêu tuỳ nghi, tương ứng 53,9% mẫu. Trong số đó, 4.374 được phân loại là mở rộng và 4.262 là thắt chặt, nghĩa là mở rộng chiếm 50,6% mọi quan sát khác không. Sự cân bằng gần như hoàn hảo giữa mở rộng và thắt chặt hữu ích cho các chiến lược nhận dạng dựa vào biến thiên dấu thay vì độ lớn.
- **Khác biệt giữa các nhóm nước.** Các nền kinh tế tiên tiến thể hiện tỷ lệ thắt chặt cao hơn (54,2%) so với mở rộng (45,8%), có thể phản ánh việc áp dụng các quy tắc tài khoá rộng rãi hơn ở các nước này. Ở thị trường mới nổi, tỷ lệ đợt mở rộng (49,5%) gần bằng tỷ lệ thắt chặt. Ở các nước thu nhập thấp, đa số biện pháp (60,7%) là mở rộng. Các nước thu nhập thấp chiếm 1.920 trong số 8.636 quý khác không (22,2%), làm nổi bật giá trị gia tăng của việc mở rộng phạm vi tự sự ra ngoài các nền kinh tế tiên tiến và mới nổi.
- **Động cơ đằng sau hành động chi tiêu.** Phân tích một mẫu con ngẫu nhiên bằng một từ điển đơn giản dựa trên văn bản cho thấy một sự bất đối xứng rõ rệt. Các hành động mở rộng gắn áp đảo với việc tăng đầu tư công, đặc biệt là hạ tầng và dự án vốn, chiếm gần 60% số đợt mở rộng. Ngược lại, các hành động thắt chặt bị chi phối bởi các biện pháp củng cố rõ ràng như kìm hãm chi tiêu và giảm thâm hụt, chiếm hơn hai phần ba số đợt thắt chặt. Các mô hình này gợi ý rằng mở rộng và củng cố tài khoá không phải là hình ảnh phản chiếu của nhau: mở rộng chủ yếu do đầu tư dẫn dắt, trong khi thắt chặt phần lớn phản ánh các nỗ lực giảm thâm hụt có chủ ý.
- **Tính không dự đoán được.** Dù các cú sốc được thiết kế để ngoại sinh về mặt động cơ, việc diễn giải nhân quả đáng tin cũng đòi hỏi chúng không liên hệ hệ thống với các điều kiện vĩ mô quan sát được ở kỳ trước. Jordà và Taylor (2015) đã chỉ ra rằng các cú sốc tự sự từ một phiên bản trước của bộ dữ liệu Adler có thể được dự báo bằng các chỉ báo vĩ mô chuẩn. Qua cả ba mẫu được xem xét, yếu tố dự báo vững duy nhất của cú sốc quý là chính độ trễ của nó; các hệ số trên nợ trên GDP trễ, chênh lệch sản lượng và tăng trưởng GDP đều không phân biệt được với không về mặt thống kê, và các hồi quy có sức giải thích rất hạn chế với R² không quá 0,1. Để so sánh, các hồi quy tương tự cho cú sốc tự sự năm của Adler cho R² trong khoảng 0,24 đến 0,31. Khi gộp cú sốc quý lên năm, tính dự đoán được trở nên rõ rệt hơn, nhất quán với diễn giải rằng tính không dự đoán được yếu ở tần suất quý phản ánh bản chất tần suất cao của thước đo.

### 5. Chiến lược nhận dạng và số nhân

- **Nhận dạng.** Dùng chuỗi tự sự như một proxy quan sát được cho các hành động chi tiêu bất ngờ, nhóm tác giả ước lượng VAR cấu trúc riêng cho từng nước và nhận dạng cú sốc chi tiêu qua một thứ tự đệ quy ("công cụ nội sinh") đặt proxy đầu tiên. Với thứ tự này, đổi mới trực giao thứ nhất được diễn giải là cú sốc tài khoá: nó có thể ảnh hưởng mọi biến còn lại đồng thời, trong khi các đổi mới còn lại bị ràng buộc không có hiệu ứng tác động lên proxy. Một hạn chế của dữ liệu tự sự là, khác Adler và cộng sự, nhóm tác giả không quan sát được quy mô tính bằng đô la của các biện pháp tài khoá, chỉ hướng định tính. Trong khung này, phản ứng đồng thời của chi tiêu chính phủ ghim thang đo của đổi mới cấu trúc, khiến bản chất định tính của proxy không còn quyết định với việc nhận dạng.
- Với mỗi nước, VAR luôn bao gồm proxy tự sự, chi tiêu chính phủ thực và GDP thực, độ trễ p = 8. Ước lượng là Bayes với tiên nghiệm Minnesota, lấy mẫu Gibbs. Ngoài nhận dạng đệ quy dựa trên proxy, nhóm tác giả đưa vào các điều kiện chấp nhận có động cơ kinh tế lên phản ứng chi tiêu hàm ý và số nhân kéo theo. Mục đích thuần tuý là suy luận: tránh rút ra kết luận từ các lượt rút hậu nghiệm trong đó đổi mới proxy trên thực tế không cung cấp thông tin về chi tiêu thực hiện và do đó tạo ra số nhân cực đoan một cách máy móc.
- Số nhân chi tiêu tích luỹ ở kỳ hạn h là tỷ lệ của các phản ứng mức tích luỹ, chia cho tỷ trọng chi tiêu trên GDP trung bình của nước đó.
- **Kết quả cơ sở.** Một cú sốc chi tiêu dương kích hoạt mức tăng mạnh và ngay lập tức của chi tiêu chính phủ, đạt đỉnh khoảng 0,4% quanh kỳ hạn một năm và duy trì ở mức cao qua giai đoạn hai năm. Phản ứng sản lượng cũng dương ở mọi kỳ hạn, với hiệu ứng dao động giữa 0,06 và 0,08%. Các phản ứng này che giấu những khác biệt đáng kể giữa các nước: cú sốc chi tiêu gắn với phản ứng chi tiêu chính phủ lớn hơn ở nền kinh tế đang phát triển điển hình so với nền kinh tế tiên tiến điển hình, dù khác biệt về phản ứng GDP không có ý nghĩa thống kê.
- Với nền kinh tế trung vị trong mẫu, số nhân ước lượng là 0,74 ở kỳ hạn một năm và 0,67 ở kỳ hạn hai năm, các giá trị nằm gọn trong khoảng mà tài liệu hiện có báo cáo. Số nhân trung vị ở kỳ hạn một và hai năm tương tự nhau cho nền kinh tế tiên tiến (0,70 và 0,61) và đang phát triển (0,80 và 0,81). Điều này là vì tỷ trọng chi tiêu chính phủ trên GDP, vốn được dùng theo chiều nghịch để hiệu chỉnh tỷ lệ hai phản ứng, lớn hơn nhiều ở nền kinh tế tiên tiến trung vị (39%) so với nền kinh tế đang phát triển trung vị (17%). Đồng thời, khác biệt trong mỗi nhóm rất lớn, với khoảng tứ phân vị của số nhân trải xấp xỉ từ 0 đến 1,5.
- **Lợi thế của dữ liệu quý.** So sánh số nhân ước lượng từ dữ liệu quý và năm cho thấy khác biệt đáng kể giữa hai tần suất, ngay cả khi gộp qua các nước. Hai yếu tố ảnh hưởng đến thiên lệch này. Thứ nhất, cú sốc năm có xu hướng dễ dự đoán hơn, dẫn đến thiên lệch do bỏ sót biến vĩ mô. Thứ hai, ngay cả khi cú sốc không dự đoán được, bản thân việc gộp đã gây thiên lệch. Stram và Wei (1986) chỉ ra rằng nếu quá trình sinh dữ liệu thật ở tần suất quý là tự hồi quy, việc gộp lên tần suất năm biến nó thành quá trình tự hồi quy trung bình trượt. Ước lượng một VAR ở cấp năm trong khi bỏ qua thành phần trung bình trượt dẫn đến sai đặc tả mô hình và ước lượng thiên lệch.

### 6. Khác biệt giữa các nước

- Phần này đánh giá liệu số nhân hàm ý bởi proxy tự sự quý có thể hiện các quy luật liên quốc gia mà Ilzetzki, Mendoza và Vegh (2013) nhấn mạnh hay không. Nhóm tác giả làm việc với một bảng quý gộp và ước lượng hiệu ứng động của chi tiêu chính phủ riêng cho các nhóm nước được định nghĩa bởi các đặc điểm cơ cấu và thể chế chậm thay đổi.
- **Độ mở thương mại** tái hiện quy luật trung tâm rằng số nhân nhỏ hơn ở các nền kinh tế mở hơn. Số nhân một năm là 1,425 cho nền kinh tế tương đối đóng và 0,558 cho nền kinh tế mở hơn, với cùng thứ hạng ở hai năm (1,364 so với 0,649). Mô hình này nhất quán với logic rò rỉ nhập khẩu: một phần lớn hơn của cầu thêm bị nhập khẩu hấp thụ ở các nền kinh tế mở hơn, làm suy giảm phản ứng sản lượng trong nước.
- **Nợ công** cho thấy khác biệt hạn chế theo trạng thái nợ trong khung này. Số nhân một và hai năm tương tự ở trạng thái nợ thấp và nợ cao. Trong thiết kế bảng gộp, số nhân biến thiên mạnh hơn theo độ mở và chế độ tỷ giá hơn là theo trạng thái nợ.
- **Chế độ tỷ giá** cho quy luật kinh điển còn lại: số nhân lớn hơn dưới các thoả thuận tỷ giá cố định. Với chế độ cố định, số nhân tích luỹ gần bằng đơn vị và được ước lượng chính xác (1,104 và 1,119, cả hai khác không về mặt thống kê). Với chế độ thả nổi, ước lượng điểm nhỏ hơn (0,715 và 0,703), nhưng suy luận yếu hơn đáng kể vì mẫu con chế độ thả nổi chỉ chứa tương đối ít nước và các khoảng 90% bao gồm số không. Do đó kết quả này được xem chủ yếu là bằng chứng mạnh về thứ hạng, cố định trên thả nổi.
- **Phi chính thức.** Đo bằng chỉ số do Medina và Schneider (2018) phát triển, kết quả gợi ý số nhân nhỏ hơn ở các nền kinh tế phi chính thức hơn. Số nhân giảm từ 1,173 ở nhóm phi chính thức thấp xuống 0,788 ở nhóm phi chính thức cao ở một năm, với khoảng cách tương tự ở hai năm. Do đó phi chính thức nổi lên như một biên quan trọng về lượng cho truyền dẫn tài khoá.
- **Linh hoạt thị trường lao động.** Đo bằng chỉ số bảo vệ việc làm của Alesina và cộng sự (2024), số nhân lớn hơn ở các nước có thị trường lao động linh hoạt hơn. Khoảng cách khiêm tốn ở một năm (1,560 so với 1,439) và trở nên rõ rệt hơn hướng về kỳ hạn hai năm (1,662 so với 1,347).

### 7. Phụ thuộc trạng thái theo thời gian

- **Chu kỳ kinh doanh.** Một tài liệu lý thuyết và thực nghiệm rộng lớn ghi nhận rằng số nhân chi tiêu có xu hướng lớn hơn trong suy thoái và khi chi tiêu tăng được theo sau bởi sự nới lỏng của chính sách tiền tệ. Nhóm tác giả dùng một chỉ số tăng trưởng liên tục, xác định trước, và ước lượng một VAR panel proxy chuyển tiếp trơn, theo sát cách tiếp cận của Auerbach và Gorodnichenko (2012) với một hàm chuyển tiếp logistic áp lên tăng trưởng sản lượng trễ. Khác biệt then chốt là nhóm tác giả nhúng cấu trúc chuyển tiếp trơn này vào một khung panel proxy-SVAR và cho phép chính mô men công cụ bên ngoài biến thiên theo trọng số chế độ.
- Hai mô hình nổi lên. Thứ nhất, các ước lượng điểm gợi ý số nhân mạnh hơn trong môi trường tăng trưởng yếu. Theo đặc tả sai phân log, số nhân tăng trưởng cao về cơ bản bằng không, trong khi số nhân tăng trưởng thấp khoảng 0,77 ở cả hai kỳ hạn. Theo đặc tả log mức, số nhân dương ở cả hai điều kiện nhưng lại lớn hơn dưới tăng trưởng thấp. Thứ hai, các khác biệt này chỉ mang tính gợi ý và chưa được ước lượng chính xác; chỉ có thể bác bỏ giả thuyết các giá trị bằng nhau ở mức tin cậy khoảng 10% cho đặc tả cơ sở ở kỳ hạn một năm.
- **Bất định chính sách.** Nhóm tác giả dùng các thước đo bất định xây từ chính báo cáo EIU, bảo đảm phạm vi phủ khớp chặt với phạm vi nước của proxy tự sự. Chỉ số Bất định Thế giới (WUI) của Ahir và cộng sự (2022) được tính bằng cách đếm tần suất từ "uncertain" và các biến thể trong báo cáo EIU, chia theo độ dài báo cáo. Chỉ số này được bổ sung bằng một chỉ số bất định tập trung vào chính sách tài khoá (FUI) áp dụng cùng cách khai thác văn bản nhưng giới hạn chú ý vào các đoạn về chính sách tài khoá và tài chính công.
- Với bất định rộng, số nhân chi tiêu thấp hơn trong các quý bất định cao ở cả hai kỳ hạn: ở một năm giảm từ khoảng 1,04 xuống 0,51, và ở hai năm giảm từ 1,09 xuống 0,42. Bất định tập trung vào chính sách tài khoá cho kết luận định tính tương tự: ở một năm giảm từ 0,95 xuống 0,21, và ở hai năm giảm từ 1,13 xuống 0,18. Dưới cả hai khái niệm bất định, bất định cao gắn với truyền dẫn tài khoá yếu hơn. Các khoảng bất định dựa trên bootstrap cho hiệu số cao trừ thấp rộng và bao gồm số không, phản ánh độ chính xác hạn chế khi chia mẫu thành các trạng thái bất định.

### 8. Ủng hộ chính trị

- Một tài liệu kinh tế chính trị rộng lớn lập luận rằng các hiệu ứng vĩ mô của chính sách tài khoá, và thành công của các đợt củng cố nói riêng, phụ thuộc vào môi trường chính trị đang thịnh hành. Sự ủng hộ đa số trong nghị viện, tính ổn định của nội các, và thời điểm bầu cử định hình cả thành phần lẫn độ bền của các gói tài khoá, cũng như khả năng chính phủ giữ vững lộ trình khi các biện pháp trở nên không được lòng dân.
- Nhóm tác giả bổ sung cơ sở dữ liệu cú sốc chi tiêu bằng một chỉ báo tự sự quý về việc môi trường chính trị có thuận lợi cho việc áp dụng và duy trì các biện pháp tài khoá hay không. Với mỗi nước–quý, họ dùng phần Chính trị trong nước và các phần liên quan của Báo cáo Quốc gia EIU để mã hoá một chỉ báo ủng hộ thô, với giá trị 1 chỉ một bối cảnh chính trị nhìn chung thuận lợi. Việc mã hoá được thực hiện bằng một prompt mô hình ngôn ngữ lớn cố định, định sẵn, trong cùng môi trường an toàn, không thích nghi được dùng cho chuỗi tự sự tài khoá. Mô hình trả về các trích đoạn nguyên văn ngắn hỗ trợ mỗi phân loại, được giữ lại để kiểm toán.
- Vì "ủng hộ" về mặt khái niệm là đa chiều, ba thành tố chính trị nguyên thuỷ cũng được mã hoá từ cùng văn bản EIU: đa số/gắn kết (đa số lập pháp làm việc hay liên minh ổn định), bầu cử sắp tới (bầu cử quốc gia được lên lịch trong quý hiện tại hoặc quý tới), và bất ổn hay bế tắc nghiêm trọng. Văn bản chính trị thiếu là vấn đề không nhỏ trong kho EIU; các đặc tả cơ sở xử lý ủng hộ thiếu như một trạng thái riêng thay vì quy nạp, để tránh việc ước lượng ngầm quy sự thiếu vắng về một trong hai nhóm.
- **Kết quả.** Trong môi trường chính trị thuận lợi, số nhân nhất quán dương và có ý nghĩa kinh tế: ở các kỳ hạn một đến ba năm, số nhân đô la đã hiệu chỉnh khoảng 1,0 đến 1,1. Ngược lại, dưới ủng hộ bất lợi, số nhân gần bằng không và đôi khi hơi âm.
- Động lực chính của sự phụ thuộc trạng thái này là phản ứng chi tiêu thực hiện. Trong các quý ủng hộ thấp, dạng rút gọn của chi tiêu tích luỹ nhỏ và không ổn định ở kỳ hạn ngắn, nên số nhân không được xác định rõ ở đó. Dưới ủng hộ cao, ngược lại, cùng cú sốc tự sự chuyển thành một phản ứng chi tiêu tích luỹ lớn hơn đáng kể, và sản lượng phản ứng dương. Chênh lệch trong dạng rút gọn của chi tiêu tích luỹ giữa các quý có và không có ủng hộ là lớn và có ý nghĩa thống kê ở kỳ hạn trung bình (0,0182 ở h = 4, t = 2,94). Các mô hình này nhất quán với việc ủng hộ chính trị làm tăng khả năng các hành động chi tiêu đã công bố hay đã lập pháp được thực thi và duy trì.
- **Chiều nào quan trọng?** Ngay cả khi kiểm soát các thành tố nguyên thuỷ, ủng hộ thuận lợi vẫn gắn với một phản ứng chi tiêu tích luỹ mạnh hơn đáng kể ở kỳ hạn trung bình. Thứ hai, bầu cử sắp tới độc lập gắn với truyền dẫn chi tiêu yếu hơn hẳn: hệ số vào khoảng −0,018 đến −0,020, cả hai đều có ý nghĩa thống kê. Các độ lớn tương đương nhau, hàm ý rằng bầu cử sắp tới có thể gần như triệt tiêu lợi thế thực thi gắn với ủng hộ chính trị. Một mối lo tiềm tàng là cú sốc có thể khác nhau giữa các trạng thái chính trị; nhóm tác giả xác minh rằng thành phần dấu của cú sốc tự sự về cơ bản giống hệt nhau giữa các trạng thái ủng hộ quan sát được, gợi ý rằng kết quả không do chọn lọc dấu đơn giản.
- **Tách bạch khỏi mã hoá tài khoá.** Các biến bối cảnh chính trị không bao giờ được dùng để phân loại hành động tài khoá là ngoại sinh hay nội sinh. Sàng lọc ngoại sinh tự sự cho các biện pháp tài khoá chỉ dựa vào động cơ nêu ra trong văn bản tài khoá, và các biến chính trị chỉ được dùng để đánh chỉ số môi trường trong đó các hành động chi tiêu ngoại sinh đã được xác định diễn ra.

### 9. Kết luận và hướng tiếp theo

- Bài phát triển cách tiếp cận tự sự có AI hỗ trợ đầu tiên để xác định cú sốc chi tiêu chính phủ ở tần suất quý và dùng nó để xây một cơ sở dữ liệu toàn cầu mới về hành động tài khoá. Xây trên nền Romer và Romer, nhóm tác giả cho thấy một mô hình ngôn ngữ lớn nguyên bản, vận hành dưới một prompt cố định trong môi trường an toàn, không thích nghi, có thể trích xuất một cách đáng tin cậy lập trường và động cơ tài khoá từ các nguồn văn bản. Quy trình này thận trọng: prompt được định sẵn và đồng nhất qua các nước và thời gian, mô hình được dùng không tinh chỉnh cho nhiệm vụ, và chỉ các hành động có động cơ rõ ràng trực giao với điều kiện vĩ mô đương thời được giữ lại là ngoại sinh.
- Về mặt phương pháp, bài chứng minh cách các mô hình ngôn ngữ lớn có thể được tích hợp vào kinh tế vĩ mô thực nghiệm mà không làm tổn hại việc nhận dạng. Vai trò của AI được giới hạn ở một nhiệm vụ phân loại minh bạch, định sẵn; mọi prompt và quy tắc mã hoá đều được tài liệu hoá; và cơ sở dữ liệu máy đọc được kèm mã nguồn cùng danh sách quốc gia được cung cấp để tái lặp. Lớp tự sự đã phong phú, và ràng buộc chính đối với việc mở rộng phạm vi không nằm ở năng lực AI mà ở sự sẵn có của dữ liệu vĩ mô và tài khoá quý nhất quán.
- Ba hướng nghiên cứu tiếp theo được nêu ra. Thứ nhất, phương pháp có thể được điều chỉnh cho các nguồn tự sự và lĩnh vực chính sách khác, gồm thay đổi thuế, can thiệp tín dụng và quy định, cùng các hành động tiền tệ hay an toàn vĩ mô, nơi tài liệu văn bản liên quan dồi dào nhưng tốn kém để mã hoá thủ công. Thứ hai, cơ sở dữ liệu liên quốc gia có thể được tích hợp với dữ liệu vi mô phong phú hơn về đầu tư doanh nghiệp, tiêu dùng hộ gia đình, hay kết quả phân phối, để nghiên cứu gánh nặng và thành phần của cú sốc tài khoá. Thứ ba, các chiều chính trị và bất định được khám phá ở đây có thể được mở rộng để bao gồm thêm các đặc điểm thể chế như quy tắc tài khoá hay tính độc lập của ngân hàng trung ương, và để nghiên cứu tương tác giữa chính sách tài khoá và tiền tệ.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Government spending multiplier | Số nhân chi tiêu chính phủ: mức tăng GDP trên mỗi đơn vị chi tiêu tăng thêm |
| Narrative method | Phương pháp tự sự: phân tích tài liệu lịch sử để phân loại hành động theo động cơ nêu ra |
| Exogenous fiscal action | Hành động tài khoá ngoại sinh: động cơ không liên quan điều kiện vĩ mô đương thời |
| Endogenous response | Phản ứng nội sinh: hành động ứng phó suy thoái, thất nghiệp, lạm phát đương thời |
| Economist Intelligence Unit (EIU) | Nguồn tự sự chính: báo cáo quốc gia chuẩn hoá, phủ nhiều nước từ thập niên 1950 |
| Fixed prompt | Prompt cố định: giữ nguyên qua mọi nước và thời gian, ngăn thiên lệch nhìn trước |
| Off-the-shelf model | Mô hình nguyên bản: không huấn luyện hay tinh chỉnh cho nhiệm vụ cụ thể |
| Look-ahead bias | Thiên lệch nhìn trước: dùng thông tin chỉ có sau này để phân loại quá khứ |
| Narrative proxy z(i,t) | Proxy tự sự: +1 mở rộng, −1 thắt chặt, 0 trung tính hoặc không rõ |
| Modal share | Tỷ trọng mode: tỷ lệ số lần chạy trả về giá trị phổ biến nhất, thước đo tái lặp |
| Internal instrument | Công cụ nội sinh: đưa proxy vào VAR ở vị trí đầu tiên thay vì dùng bên ngoài |
| Proxy-SVAR | VAR cấu trúc nhận dạng bằng proxy làm công cụ bên ngoài |
| Cholesky ordering | Thứ tự Cholesky: phân rã ma trận hiệp phương sai để trực giao hoá đổi mới |
| Minnesota priors | Tiên nghiệm Minnesota: tiên nghiệm chuẩn cho VAR Bayes |
| Accept–reject filter | Bộ lọc chấp nhận: loại lượt rút cho số nhân cực đoan do mẫu số gần không |
| Local projection (LP) | Chiếu cục bộ: ước lượng phản ứng xung bằng hồi quy riêng cho từng kỳ hạn |
| Impulse response function (IRF) | Hàm phản ứng xung: phản ứng của biến theo thời gian trước một cú sốc |
| Cumulative multiplier | Số nhân tích luỹ: tỷ lệ phản ứng GDP tích luỹ trên phản ứng chi tiêu tích luỹ |
| Inverse-variance weighting | Trọng số nghịch đảo phương sai: gộp ước lượng các nước theo độ chính xác |
| Temporal aggregation | Gộp thời gian: quá trình AR ở tần suất quý thành ARMA ở tần suất năm |
| Smooth-transition VAR | VAR chuyển tiếp trơn: hệ số biến thiên theo hàm logistic của biến trạng thái |
| World Uncertainty Index (WUI) | Chỉ số Bất định Thế giới: đếm tần suất từ "uncertain" trong báo cáo EIU |
| Fiscal Uncertainty Index (FUI) | Chỉ số bất định tập trung vào các đoạn về chính sách tài khoá |
| Import leakage | Rò rỉ nhập khẩu: cầu thêm bị nhập khẩu hấp thụ, làm giảm số nhân |
| Informality | Phi chính thức: tỷ trọng kinh tế ngoài khu vực chính thức |
| Country-cluster bootstrap | Bootstrap theo cụm quốc gia: lấy lại mẫu các nước để giữ phụ thuộc chuỗi trong nước |
| Extensive vs intensive margin | Biên mở rộng (có hay không) so với biên cường độ (lớn bao nhiêu) |
| Implementation channel | Kênh thực hiện: ủng hộ chính trị làm tăng khả năng hành động được thực thi |

## Câu nói đáng nhớ

> "To the best of our knowledge, this is the first effort to develop a historical dataset of exogenous government spending shocks at quarterly frequency for a large and diverse group of developed and developing countries."

> "Our results show that the AI matches expert coding with an accuracy exceeding 93 percent."

> "The main constraint on expanding coverage lies not in AI capabilities but in the availability of consistent quarterly macro-fiscal data."

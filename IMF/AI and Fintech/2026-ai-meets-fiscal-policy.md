# AI Meets Fiscal Policy: Mapping Government Spending Actions Across 64 Countries — AI gặp chính sách tài khoá: lập bản đồ hành động chi tiêu chính phủ ở 64 nước

**Nguồn:** IMF Working Paper No. WP/2026/043.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 3, không có trang bìa và trang tác giả).
**Ý chính:** Phương pháp tự sự (narrative) của Romer và Romer rất tốn công người, nên chỉ có dữ liệu cho vài nước và ở tần suất năm. Nhóm tác giả dùng GPT-4.1 với MỘT PROMPT CỐ ĐỊNH đọc báo cáo quốc gia của Economist Intelligence Unit để phân loại hành động chi tiêu là ngoại sinh hay nội sinh, tạo ra bộ dữ liệu QUÝ đầu tiên cho 64 nước từ 1952Q1. AI khớp với mã hoá của chuyên gia trên 93%. Số nhân chi tiêu ở nước trung vị là 0,74 sau một năm và 0,67 sau hai năm.

> **Lưu ý:** bản PDF bắt đầu từ trang 3 (phần Giới thiệu). Trang bìa, tóm tắt và danh sách tác giả không có trong bản này. Tên bài và số hiệu working paper lấy từ trang bìa sau.
> - Ở bảng số nhân theo đặc điểm cơ cấu, hai nhóm nợ công cộng lại **56 + 26 = 82** nước, vượt mẫu **64** nước (các cách chia khác đều không vượt: 60, 59, 56, 49). Có thể một nước được xếp vào cả hai nhóm khi mức nợ thay đổi qua thời gian, nhưng bài không nói rõ; không đủ dữ liệu để biết số nào sai.

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

## Khái niệm cần biết

**Số nhân chi tiêu chính phủ (government spending multiplier).** Khi chính phủ chi thêm một đồng, GDP tăng thêm bao nhiêu đồng. Nếu số nhân lớn hơn 1, mỗi đồng chi kéo theo thêm hoạt động của khu vực tư nhân; nếu nhỏ hơn 1, một phần chi tiêu công chỉ thay thế hoặc chèn lấn chi tiêu tư nhân, hoặc chảy ra nước ngoài qua nhập khẩu. Ví dụ trong bài: ở nước trung vị, số nhân là 0,74 sau một năm, nghĩa là chi thêm 100 đồng thì GDP tích luỹ tăng khoảng 74 đồng. Đây là con số mà mọi gói kích thích, như các gói chống Khủng hoảng Tài chính Toàn cầu và đại dịch COVID-19, cần biết để định cỡ.

**Ngoại sinh và nội sinh (exogenous, endogenous).** Một hành động chi tiêu là *nội sinh* nếu nó là phản ứng trước tình hình kinh tế hiện tại, ví dụ tăng chi vì đang suy thoái. Nó là *ngoại sinh* nếu động cơ không liên quan đến tình hình vĩ mô lúc đó, ví dụ cắt chi để xử lý một khoản thâm hụt tích tụ từ nhiều năm trước, hay xây hạ tầng vì mục tiêu phát triển dài hạn. Ví dụ minh hoạ: nếu chính phủ chi thêm đúng lúc GDP đang giảm, ta thấy "chi nhiều đi cùng tăng trưởng thấp" và có thể kết luận sai rằng chi tiêu làm hại tăng trưởng. Chỉ những hành động ngoại sinh mới cho phép đo số nhân mà không bị lẫn với chiều nhân quả ngược.

**Phương pháp tự sự (narrative method).** Cách nhận dạng hành động ngoại sinh bằng cách đọc tài liệu lịch sử (văn bản ngân sách, báo cáo, bài phát biểu) và phân loại từng hành động theo động cơ được nêu ra. Romer và Romer (2010) tiên phong cách này cho Mỹ. Nó đáng tin nhưng rất tốn công người đọc, nên trước bài này chỉ có dữ liệu cho vài nước, ở tần suất năm, từ thập niên 1980. Bài thay người đọc bằng GPT-4.1 để mở rộng lên 64 nước ở tần suất quý từ 1952Q1.

**Proxy tự sự z(i,t).** Một biến chỉ ghi *hướng* của hành động chi tiêu ngoại sinh ở nước i, quý t: +1 nếu mở rộng, −1 nếu thắt chặt, 0 nếu trung tính hoặc không rõ. Nó không ghi quy mô bằng tiền. Ví dụ: nếu báo cáo quý 3 năm 2010 của một nước nói quốc hội thông qua một chương trình nhà ở lớn vì mục tiêu dài hạn, thì z = +1 cho quý đó. Mọi ước lượng số nhân trong bài đều dựa trên biến thô này.

**VAR và hàm phản ứng xung (vector autoregression, impulse response).** VAR là mô hình trong đó mỗi biến (ở đây là proxy, chi tiêu chính phủ thực, GDP thực) được giải thích bằng các giá trị quá khứ của chính nó và của các biến còn lại. Hàm phản ứng xung cho biết sau một cú sốc, mỗi biến thay đổi thế nào qua từng quý. Ví dụ trong bài: sau một cú sốc chi tiêu dương, chi tiêu chính phủ tăng đạt đỉnh khoảng 0,4% quanh kỳ hạn một năm. Số nhân được tính từ hai đường phản ứng này.

**Tỷ trọng mode (modal share).** Thước đo độ ổn định của câu trả lời khi chạy lại cùng một câu lệnh nhiều lần: tỷ lệ số lần mô hình trả về đáp án phổ biến nhất. Ví dụ: chạy 51 lần, nếu cả 51 lần đều trả lời "thắt chặt" thì tỷ trọng mode bằng 1; nếu 40 lần "thắt chặt" và 11 lần "trung tính" thì bằng khoảng 0,78. Khái niệm này quan trọng vì mô hình ngôn ngữ không cho cùng kết quả ở mỗi lần chạy, và bài dùng nó để chọn trường đầu ra nào đủ tin cậy.

**Rò rỉ nhập khẩu (import leakage).** Khi chính phủ chi thêm, một phần tiền được dùng mua hàng nước ngoài, nên không tạo ra sản lượng trong nước. Ví dụ minh hoạ: nếu 40% mỗi đồng chi tiêu tăng thêm chảy vào hàng nhập khẩu, chỉ 60% còn lại kích thích sản xuất trong nước. Vì vậy nền kinh tế càng mở thì số nhân càng nhỏ, và bài tìm thấy đúng điều đó: 1,425 ở nhóm nước đóng so với 0,558 ở nhóm nước mở.

**Gộp thời gian (temporal aggregation).** Biến dữ liệu quý thành dữ liệu năm bằng cách cộng hoặc lấy trung bình bốn quý. Việc này làm mất thông tin về thứ tự trước sau trong năm và có thể làm sai lệch ước lượng. Ví dụ minh hoạ: nếu chính phủ cắt chi ở quý 1 và tăng chi ở quý 3, số liệu năm có thể ghi nhận "không thay đổi". Bài chỉ ra số nhân tính từ dữ liệu năm khác đáng kể so với dữ liệu quý, đó là lý do chính để xây bộ dữ liệu quý.

## Nội dung chi tiết

### 1. Khoảng trống trong tài liệu

Câu hỏi xuất phát của bài rất cụ thể: số nhân chi tiêu chính phủ của **một nước cụ thể** là bao nhiêu? Câu hỏi này có ý nghĩa chính sách lớn suốt hai thập kỷ qua, khi nhiều nước tung ra các gói kích thích lớn để chống tác động của các cuộc suy thoái nặng như Khủng hoảng Tài chính Toàn cầu và đại dịch COVID-19. Muốn biết gói kích thích nên lớn bao nhiêu thì phải biết mỗi đồng chi tạo ra bao nhiêu sản lượng.

Dù đã có rất nhiều nghiên cứu, tài liệu hiện có chủ yếu trả lời cho các nền kinh tế cụ thể, phần lớn là nền kinh tế tiên tiến (đặc biệt là Mỹ), hoặc chỉ đưa ra một con số trung bình cho cả một nhóm nước. Một bộ trưởng tài chính ở một nước đang phát triển gần như không có con số nào dành riêng cho nước mình.

**Vì sao có khoảng trống này.** Muốn ước lượng số nhân thì phải tìm được những thay đổi chi tiêu ngoại sinh, tức là không phải phản ứng trước tình hình kinh tế. Việc này khó về bản chất, vì phần lớn chi tiêu công tăng giảm chính là để đối phó chu kỳ. Cách tiếp cận nổi bật nhất là **phương pháp tự sự** do Romer và Romer (2010) tiên phong: đọc tài liệu lịch sử và phân loại từng hành động tài khoá theo động cơ được nêu ra. Bằng cách phân biệt các biện pháp làm vì lý do dài hạn hoặc vì thâm hụt thừa kế với các biện pháp ứng phó điều kiện kinh tế hiện tại, phương pháp này tách được hành động chính sách ngoại sinh khỏi phản ứng nội sinh. Nó đã trở thành trung tâm của tài liệu hiện đại về truyền dẫn tài khoá, nhưng tốn rất nhiều công sức của người đọc chuyên gia.

**Hệ quả.** Không ngạc nhiên, các bộ dữ liệu tự sự chỉ có cho vài nước hoặc một nhóm nhỏ:

| Bộ dữ liệu | Phạm vi |
|---|---|
| Romer và Romer (2010) | Mỹ |
| Cloyne và cộng sự (2024) | Anh |
| Guajardo và cộng sự (2014) | các nền kinh tế OECD |
| Adler và cộng sự (2024) | một tập hợp nền kinh tế OECD và các nước khác |

Các bộ dữ liệu liên quốc gia này lại chỉ có tần suất năm và phủ một giai đoạn tương đối ngắn (từ thập niên 1980), nên rất khó dùng cho phân tích chuỗi thời gian, vốn cần nhiều quan sát liên tiếp.

**Đóng góp của bài.** Để lấp khoảng trống, bài xây một bộ dữ liệu mới về các cú sốc chi tiêu chính phủ ngoại sinh xác định bằng phương pháp tự sự, gồm cả mở rộng lẫn thắt chặt, cho một bảng không cân bằng (mỗi nước bắt đầu ở thời điểm khác nhau) gồm 64 nước, tần suất quý, bắt đầu từ 1952Q1. Theo nhóm tác giả, đây là nỗ lực đầu tiên xây một bộ dữ liệu lịch sử về cú sốc chi tiêu ngoại sinh ở tần suất quý cho một nhóm lớn và đa dạng gồm cả nước phát triển lẫn đang phát triển, phủ gần như toàn bộ giai đoạn hậu Thế chiến II.

### 2. Xây dựng cơ sở dữ liệu tự sự bằng AI

**Nguồn dữ liệu: báo cáo quốc gia của Economist Intelligence Unit (EIU).** EIU làm báo cáo quốc gia theo khuôn mẫu chuẩn hoá cho rất nhiều nền kinh tế tiên tiến, mới nổi và thu nhập thấp, với nhiều nước có báo cáo từ tận thập niên 1950. Báo cáo thường phát hành theo quý; những năm sau này một số nước có báo cáo theo tháng. Để nhất quán, nhóm tác giả xây một kho lưu trữ quý với đúng một báo cáo cho mỗi cặp nước–quý. Khi trong một quý có nhiều báo cáo, họ giữ báo cáo toàn diện phát hành muộn nhất trong quý đó (khi có cả bản "Updater" ngắn và bản "Main Report" dài thì giữ Main Report), vì các báo cáo chồng lấn nhau thêm rất ít thông tin mới về hành động tài khoá và động cơ.

Báo cáo EIU đi qua một quy trình biên tập tập trung: chuyên gia quốc gia soạn thảo từ nguồn địa phương, rồi bản thảo được chuyên gia rà soát và biên tập để rõ ràng và nhất quán nội bộ trước khi xuất bản. Sự chuẩn hoá này rất có giá trị vì nó cho phép trích xuất có hệ thống các hành động tài khoá và động cơ theo cùng một định dạng, so sánh được giữa các nước và theo thời gian. So với báo cáo OECD và nhiều báo cáo quốc gia của IMF, báo cáo EIU có tần suất cao hơn và chuỗi lịch sử dài hơn cho nhiều nước, kể cả nước mới nổi và thu nhập thấp. Kho EIU đầy đủ phủ hơn 140 nền kinh tế, nhưng phân tích chỉ tập trung vào 64 nước có dữ liệu vĩ mô và tài khoá quý nhất quán để ước lượng.

**Bốn yêu cầu của Romer và Romer (2023).** Bài tuân thủ bốn điều kiện mà Romer và Romer (2023) đặt ra cho một nghiên cứu tự sự tốt:

1. nguồn tự sự đáng tin cậy;
2. ý tưởng rõ ràng về thông tin cần tìm;
3. cách tiếp cận vô tư và nhất quán;
4. tài liệu hoá cẩn thận bằng chứng tự sự.

**Thông tin cần tìm: định nghĩa ngoại sinh.** Theo Romer và Romer (2010), một hành động tài khoá là ngoại sinh khi động cơ được nêu ra không liên quan đến điều kiện vĩ mô đương thời. Trong nghiên cứu về Mỹ, họ nhấn mạnh hai nhóm động cơ thoả tiêu chí này:

- biện pháp xử lý một **mất cân đối tài khoá thừa kế** (thâm hụt hay nợ tích tụ từ trước);
- biện pháp phản ánh **mục tiêu dài hạn** về quy mô hay thành phần của khu vực công, như tăng trưởng, công bằng, thiết kế thể chế.

Cả hai nhóm đều trực giao, tức là không liên quan, với động cơ ổn định dao động ngắn hạn.

**Cách tiếp cận vô tư và nhất quán: một prompt cố định.** Nhóm tác giả dùng một prompt GPT-4.1 cố định để tìm các hành động tài khoá và phân loại chúng là nội sinh hay ngoại sinh. Đặc tả prompt và quy tắc mã hoá được giữ nguyên vẹn qua mọi nước và mọi thời điểm. Mô hình được dùng nguyên bản, không huấn luyện thêm hay tinh chỉnh cho nhiệm vụ. Cách làm này ngăn việc chỉnh prompt cho khớp với từng mẫu và ngăn thiên lệch nhìn trước (dùng hiểu biết có được sau này để phân loại quá khứ), đồng thời cho phép người khác tái lặp đúng quy trình.

Nhiệm vụ trong prompt được phát biểu: "Đọc trích đoạn báo cáo EIU cho nước C và quý Q. Xác định các hành động chi tiêu chính phủ ngoại sinh trong Q dựa trên các động cơ nêu ra trong văn bản, và tóm tắt tác động định hướng ròng lên chi tiêu."

Định nghĩa ngoại sinh trong prompt rất chặt:

- Chỉ phân loại là ngoại sinh nếu động cơ **rõ ràng** không liên quan đến diễn biến vĩ mô ngắn hạn.
- Các động cơ phi chu kỳ điển hình: mục tiêu củng cố tài khoá trung hạn, mục tiêu tư tưởng hay cơ cấu dài hạn, tuân thủ luật, hiệp ước hay quy tắc siêu quốc gia.
- Nếu văn bản nói hành động nhằm chống suy thoái hay tăng trưởng chậm, giảm thất nghiệp, làm nguội nền kinh tế quá nóng, hoặc ứng phó lạm phát, lãi suất, áp lực tỷ giá, căng thẳng tài trợ đương thời, thì hành động đó là nội sinh.
- Việc báo cáo **nhắc tới** điều kiện kinh tế hiện tại tự nó không làm hành động thành nội sinh, nếu động cơ được nêu rõ là phi chu kỳ.

**Đầu ra của prompt** gồm năm trường:

| Trường | Nội dung |
|---|---|
| Thứ nhất: EXOG_NET_SPENDING | hướng ròng, một trong bốn giá trị EXP_ (mở rộng), CON_ (thắt chặt), NEUTRAL (trung tính), UNCLEAR (không rõ) |
| Thứ hai: MOTIVATION | cụm từ ngắn nêu động cơ |
| Thứ ba: COMPONENT | thành phần chi tiêu được nhắc đến |
| Thứ tư: INTENSITY_ORDINAL | cường độ định hướng, thang từ −10 đến 10 |
| Thứ năm: CONFIDENCE | mô hình tự đánh giá độ tin cậy |

Prompt ghi chú rằng phải phân loại nghiêm ngặt theo văn bản cung cấp, không được suy diễn động cơ không được nêu ra; nếu văn bản không hỗ trợ một hướng cụ thể thì trả về NEUTRAL hoặc UNCLEAR. Prompt cũng ghi lại biện pháp được thực hiện ngay trong quý hay chỉ được công bố cho các quý sau. Các trường này được giữ để kiểm toán và kiểm tra độ vững, nhưng chuỗi dùng trong ước lượng VAR cơ sở chỉ dựa vào phân loại dấu rời rạc: mở rộng, thắt chặt, hoặc không hành động.

**Xây dựng cú sốc.** Đầu ra ở cấp từng báo cáo được gộp thành proxy nước–quý:

z(i,t) = +1 nếu EXP_; −1 nếu CON_; 0 nếu NEUTRAL hoặc UNCLEAR.

Ánh xạ này thận trọng: bất cứ khi nào động cơ không rõ ràng là phi chu kỳ, hoặc báo cáo gắn hành động với tăng trưởng, thất nghiệp, lạm phát, lãi suất, áp lực tỷ giá hay căng thẳng tài trợ đương thời, hành động được xếp là phi ngoại sinh và không đóng góp vào hiệu ứng ròng. Nhóm tác giả giữ lại các trích đoạn nguyên văn đã kích hoạt từng phân loại và công bố chúng cùng chuỗi đã mã hoá, để ai cũng kiểm tra và tái lặp được.

Báo cáo EIU mô tả hành động chính sách khi chúng được công bố, được lập pháp và được thực hiện, nhưng khó tách sạch thời điểm công bố ("tin tức") với thời điểm thực hiện. Cơ sở dữ liệu không cố tách hai thời điểm này ở bước phân loại. Vì vậy z(i,t) nên được hiểu là một proxy định tính cho các hành động chi tiêu tuỳ nghi được ghi nhận theo thời gian thực, có thể pha trộn cả yếu tố công bố lẫn yếu tố thực hiện.

**Ba ví dụ về các đợt tự sự:**

| Ví dụ | Nước và quý | Nội dung trong báo cáo | Phân loại |
|---|---|---|---|
| Ý tưởng dài hạn, mở rộng | Ghana, 2010Q3 | Quốc hội thông qua đầu tháng Tám một thoả thuận nhà ở gây tranh cãi trị giá 10 tỷ USD với công ty xây dựng Hàn Quốc STX Korea; mục tiêu nêu ra là mở rộng nguồn cung nhà ở và năng lực hạ tầng | Mở rộng, độ tin cậy 95% |
| Thâm hụt thừa kế, thắt chặt | Ecuador, 1982Q4 | Nhà chức trách bỏ trợ cấp xăng và lúa mì nhập khẩu như một phần của củng cố tài khoá; động cơ là kiềm chế áp lực ngân sách và cải thiện tính bền vững | Thắt chặt, độ tin cậy 90% |
| Không hành động | Anh, 2005Q4 | Báo cáo bàn về điều chỉnh kỹ thuật, việc hoãn lại đã làm ở các quý trước và ý định tương lai, nhưng không có thay đổi chi tiêu rõ ràng | Không có hành động |

### 3. Kiểm chứng

Bài kiểm chứng bộ dữ liệu bằng bốn phép thử độc lập.

**Phép thử thứ nhất: so với mã hoá của chuyên gia.** Romer và Romer (2019), viết tắt RR19, nghiên cứu phản ứng chính sách tài khoá trong các đợt căng thẳng tài chính ở 31 nước OECD giai đoạn 1980–2017, dùng bằng chứng tự sự từ chính các báo cáo quốc gia của EIU. Với mỗi đợt, họ đọc một chuỗi báo cáo cố định (thường là chín báo cáo, một đợt có mười một) và trả lời bốn câu hỏi: lập trường chính sách tài khoá là gì, động cơ là gì, EIU có nhắc tới tỷ lệ nợ trên GDP không, và có điều gì đáng chú ý khác.

RR19 là một chuẩn đối chiếu nghiêm ngặt: phân loại do người đọc chuyên gia làm, dựa trên cùng nguồn văn bản, và quy tắc mã hoá được mô tả minh bạch. Nhóm tác giả thiết kế một prompt cố định phản chiếu bốn câu hỏi đó và chạy nó trên cùng bộ báo cáo EIU mà RR19 đã dùng, cho cùng 19 nước, tổng cộng 200 báo cáo.

| Loại đợt | Khía cạnh | Số ca khớp | Tỷ lệ khớp |
|---|---|---|---|
| Mở rộng | lập trường | 14/16 | 87,5% |
| Mở rộng | động cơ | 32/34 | 94,1% |
| Thắt chặt | hướng | 18/19 | 95% |
| Thắt chặt | động cơ | 44/45 | 97,8% |

Tổng thể, AI khớp với mã hoá của chuyên gia với độ chính xác trên 93%.

Điều quan trọng là phần lớn các "bất đồng" không đến từ việc mô hình hiểu sai văn bản. Chúng nảy sinh ở những báo cáo mô tả đồng thời cả biện pháp mở rộng lẫn thắt chặt. Trong các ca này, mô hình nhìn chung trích xuất đúng từng hành động và dấu của nó. Nhưng vì không quan sát được độ lớn của từng biện pháp, và vì cách phân loại cố ý thận trọng, lập trường ròng mà mô hình gán có thể khác với phán đoán hậu nghiệm (nhìn lại sau khi biết kết cục) của RR19, như ở Thổ Nhĩ Kỳ và Iceland. Na Uy là một ca nằm ở ranh giới: chưa rõ việc hỗ trợ khu vực tài chính có nên tính là chi tiêu tài khoá hay không.

Chỉ có hai lỗi thật sự:

- Ở **Hàn Quốc**, mô hình bỏ sót một gợi ý rõ ràng về động cơ chính trị trong văn bản (cụm "với con mắt hướng về bầu cử..."), nên phân loại sai lập trường.
- Ở trường hợp **Mỹ**, mô hình liệt kê đúng các biện pháp, nhưng lại suy ra lập trường tổng thể từ các nhận xét về thâm hụt tăng, và gán sai dấu cho hiệu ứng ròng.

**Phép thử thứ hai: khả năng tái lặp.** Mô hình ngôn ngữ có thể trả lời khác nhau khi chạy lại cùng câu lệnh. Nhóm tác giả chạy lại prompt 51 lần trên một tập con 20 báo cáo, và đo bằng tỷ trọng mode: tỷ lệ số lần chạy trả về giá trị xuất hiện nhiều nhất, bằng 1 khi mọi lần chạy cho cùng một đáp án.

| Trường đầu ra | Mức tái lặp |
|---|---|
| Hướng của lập trường tài khoá | hoàn toàn ổn định: cả 20 báo cáo có tỷ trọng mode bằng 1 |
| Động cơ | thấp hơn một chút nhưng vẫn cao |
| Cường độ và độ tin cậy | thấp hơn, một số ca phân tán đáng kể |

Thứ hạng này không bất ngờ. Hướng là một phân loại thô, gần như nhị phân, gắn chặt với câu chuyện định tính trong văn bản. Động cơ là một biến nhiều hạng mục và thường đa diện, vì một hành động có thể phục vụ nhiều mục tiêu cùng lúc. Cường độ và độ tin cậy đòi hỏi phán đoán định lượng tinh tế, nên nhạy hơn với cách diễn đạt, sự nhấn mạnh và chỗ mơ hồ trong văn bản. Kết luận: phân loại bằng AI rất vững ở đúng chiều quan trọng nhất cho nhận dạng tự sự, là **hướng** của chính sách tài khoá. Đây cũng là lý do bài chỉ dùng hướng trong ước lượng.

**Phép thử thứ ba: so với dữ liệu chi tiêu thực tế.** Nếu proxy có ý nghĩa thì chi tiêu chính phủ thực tế phải di chuyển theo nó. Bài ước lượng bằng phương pháp chiếu cục bộ (local projection, hồi quy riêng cho từng kỳ hạn):

| Kỳ hạn | Thắt chặt (cú sốc −1) | Mở rộng (cú sốc +1) |
|---|---|---|
| Tại thời điểm tác động, h = 0 | log G giảm khoảng −0,005 điểm log, tức khoảng 0,5% | chưa phản ứng; tăng muộn hơn một quý với hệ số khoảng 0,002 |
| Tích luỹ tới khoảng h ≈ 8 quý | khoảng −0,06 | khoảng 0,04 |

Chi tiêu thực tế đi đúng hướng của proxy, và thắt chặt thể hiện nhanh hơn, mạnh hơn mở rộng.

**Phép thử thứ tư: đối chiếu với Adler và cộng sự (2024).** Đây là bộ dữ liệu năm cho 31 nền kinh tế tiên tiến và mới nổi, ghi quy mô công bố của các gói củng cố tài khoá tuỳ nghi, tách thành biện pháp thuế và biện pháp chi tiêu, tính theo phần trăm GDP, và chỉ gồm các biện pháp chủ yếu nhằm giảm thâm hụt trung hạn. Bài làm ba phép kiểm tra.

*Kiểm tra thứ nhất, biên mở rộng (có hay không).* Với ngưỡng τ = 0,5% GDP, có 138 nước–năm mà Adler xếp là năm củng cố. Trong 96,4% số ca đó, dữ liệu quý của bài ghi nhận ít nhất một quý thắt chặt. Với các gói lớn hơn (ngưỡng τ = 1,0 và τ = 2,0% GDP), tỷ lệ trúng vẫn trên 96% và đạt 100% ở ngưỡng 2,0. Theo nhóm nước, Mỹ Latinh và Caribe trúng 100% ở mọi ngưỡng; nước tiên tiến trúng trên 95%. Đồng thời, 23–25% các năm "củng cố lớn" này cũng chứa ít nhất một quý mở rộng. Điều này phản ánh sự pha trộn trong năm: chính phủ thường làm nhiều hành động khác dấu trong cùng một năm dương lịch, và dữ liệu năm không thấy được điều đó.

*Kiểm tra thứ hai, xác suất.* Trong một mô hình xác suất tuyến tính có hiệu ứng cố định theo quốc gia, hệ số của biến "có ít nhất một quý thắt chặt" (any_consol) là 0,126 (sai số chuẩn 0,019). Nghĩa là năm nào bài ghi nhận ít nhất một quý thắt chặt thì xác suất Adler xếp năm đó là củng cố lớn cao hơn 12,6 điểm phần trăm. Hệ số của biến "có ít nhất một quý mở rộng" (any_expand) là −0,073 (sai số chuẩn 0,02), tức đi theo chiều ngược lại như kỳ vọng.

*Kiểm tra thứ ba, cường độ.* Hệ số của chỉ số lập trường ròng năm (net_stance) là 0,263 (sai số chuẩn 0,044). Nghĩa là đi từ một năm thuần mở rộng (giá trị −1) sang một năm thuần củng cố (giá trị +1) gắn với mức tăng khoảng 0,5 điểm phần trăm GDP trong quy mô củng cố dựa trên chi tiêu mà Adler ghi nhận.

Kết luận của phép thử này: dù khác nhau về tần suất, phạm vi và cách mã hoá, hai nguồn dữ liệu nắm bắt cùng một hiện tượng nền tảng, là các dịch chuyển tuỳ nghi trong lập trường chi tiêu của chính phủ nhằm điều chỉnh tài khoá trung hạn.

### 4. Đặc điểm dữ liệu

**Thống kê mô tả.**

| Đại lượng | Giá trị |
|---|---|
| Số quan sát nước–quý được xử lý | 16.029 |
| Số đợt chi tiêu tuỳ nghi xác định được | 8.636 (53,9% mẫu) |
| Trong đó mở rộng | 4.374 (50,6% số quan sát khác không) |
| Trong đó thắt chặt | 4.262 (49,4%) |
| Giai đoạn | 1952Q1–2023Q4, bảng không cân bằng, mỗi nước bắt đầu ở thời điểm khác nhau |

Sự cân bằng gần như hoàn hảo giữa mở rộng và thắt chặt (50,6% so với 49,4%) có ích cho chiến lược nhận dạng của bài, vốn dựa vào sự biến thiên của **dấu** chứ không phải độ lớn: có đủ cả hai loại cú sốc để so sánh.

**Khác biệt giữa các nhóm thu nhập.**

| Nhóm nước | Số quý khác không | Tỷ lệ mở rộng | Nhận xét |
|---|---|---|---|
| Tiên tiến | 3.129 | 45,8% | thắt chặt nhiều hơn (54,2%), có thể do quy tắc tài khoá được áp dụng rộng rãi hơn |
| Mới nổi | 3.587 | 49,5% | gần như cân bằng |
| Thu nhập thấp | 1.920 (22,2% của 8.636) | 60,7% | đa số biện pháp là mở rộng |

Việc nhóm thu nhập thấp chiếm hơn một phần năm số quý có hành động cho thấy giá trị thêm của việc mở rộng phương pháp tự sự ra ngoài nhóm tiên tiến và mới nổi: đây là nhóm trước kia gần như không có dữ liệu.

**Động cơ đằng sau hành động chi tiêu.** Phân tích một mẫu con ngẫu nhiên bằng một từ điển đơn giản dựa trên văn bản cho thấy một bất đối xứng rõ rệt:

- **Mở rộng** gắn áp đảo với tăng đầu tư công, đặc biệt là hạ tầng và dự án vốn, chiếm gần 60% số đợt mở rộng.
- **Thắt chặt** bị chi phối bởi các biện pháp củng cố rõ ràng như kìm hãm chi tiêu và giảm thâm hụt, chiếm hơn hai phần ba số đợt thắt chặt.
- Các hạng mục khác (chi xã hội, tư nhân hoá, tài trợ bên ngoài) đóng vai trò thứ yếu và xuất hiện ở cả hai chiều.

Như vậy mở rộng và củng cố không phải là hình ảnh phản chiếu của nhau: mở rộng chủ yếu do đầu tư dẫn dắt, còn thắt chặt chủ yếu phản ánh nỗ lực giảm thâm hụt có chủ ý.

**Tính không dự đoán được.** Cú sốc được thiết kế để ngoại sinh về mặt động cơ, nhưng muốn diễn giải nhân quả một cách đáng tin thì chúng còn phải không liên hệ có hệ thống với điều kiện vĩ mô quan sát được ở kỳ trước. Jordà và Taylor (2015) từng chỉ ra rằng cú sốc tự sự trong một phiên bản trước của bộ dữ liệu Adler (tức Guajardo và cộng sự 2014) có thể dự báo được bằng các chỉ báo vĩ mô chuẩn, tức là chưa thật sự "bất ngờ".

Bài hồi quy z(i,t) lên nợ trên GDP, chênh lệch sản lượng, tăng trưởng GDP (đều trễ một quý) và giá trị trễ của chính cú sốc:

| Phép hồi quy | Kết quả |
|---|---|
| Cú sốc quý của bài, cả ba mẫu | yếu tố dự báo vững duy nhất là độ trễ của chính nó; hệ số của nợ trên GDP, chênh lệch sản lượng, tăng trưởng GDP không khác không về mặt thống kê; R² không quá 0,1 |
| Cú sốc tự sự năm của Adler | R² trong khoảng 0,243–0,305 (khoảng 0,24 đến 0,31), và tăng trưởng GDP trễ cũng góp phần dự báo |
| Cú sốc quý của bài gộp lên năm (thang từ −4 đến +4) | tính dự đoán được tăng rõ, R² 0,125; nợ trên GDP trễ và tăng trưởng GDP trễ trở thành yếu tố dự báo có ý nghĩa thống kê |

Bài diễn giải rằng tính không dự đoán được yếu ở tần suất quý phản ánh bản chất tần suất cao của thước đo: thông tin có hệ thống về điều kiện vĩ mô dễ phát hiện hơn khi cùng các hành động đó được nhìn ở tần suất năm.

### 5. Chiến lược nhận dạng và số nhân

**Nhận dạng.** Bài dùng chuỗi tự sự như một proxy quan sát được cho các hành động chi tiêu bất ngờ, và ước lượng cho mỗi nước một VAR Bayes nhỏ:

x(t) = [z(t), g(t), y(t)]

trong đó z là proxy tự sự, g là log chi tiêu chính phủ thực, y là log GDP thực, với độ trễ p = 8 quý. Proxy được xếp đầu tiên trong thứ tự đệ quy, theo cách "công cụ nội sinh" (internal instrument) của Plagborg-Møller và Wolf (2021). Với thứ tự này, đổi mới trực giao thứ nhất (cú sốc Cholesky đầu tiên) được diễn giải là cú sốc tài khoá: nó được phép tác động đồng thời lên mọi biến còn lại, trong khi các đổi mới khác bị ràng buộc không tác động tức thời lên proxy.

Hạn chế cốt lõi của dữ liệu tự sự là, khác với Adler và cộng sự, bài không quan sát được quy mô bằng đô la của từng biện pháp, chỉ có hướng định tính. Trong khung VAR này, hạn chế đó được giải quyết: phản ứng đồng thời của chi tiêu chính phủ thực tế "ghim" thang đo của cú sốc. Nói cách khác, cú sốc lớn hay nhỏ được đo bằng việc chi tiêu thực sự thay đổi bao nhiêu, nên bản chất định tính của proxy không còn quyết định việc nhận dạng.

**Ước lượng Bayes và bộ lọc chấp nhận.** Mô hình được ước lượng theo phương pháp Bayes với tiên nghiệm Minnesota (dạng chuẩn ma trận và Wishart nghịch đảo), lấy mẫu bằng thuật toán Gibbs. Ngoài nhận dạng đệ quy, bài thêm các điều kiện chấp nhận có động cơ kinh tế (accept–reject) lên phản ứng chi tiêu và số nhân. Mục đích thuần tuý là suy luận: loại bỏ những lượt rút hậu nghiệm mà ở đó đổi mới proxy gần như không mang thông tin gì về chi tiêu thực hiện. Nếu giữ những lượt rút đó, mẫu số của số nhân gần bằng không và số nhân trở nên cực đoan một cách máy móc.

**Cách tính số nhân.** Số nhân tích luỹ ở kỳ hạn h bằng tỷ lệ giữa phản ứng tích luỹ của GDP và phản ứng tích luỹ của chi tiêu chính phủ, chia cho tỷ trọng chi tiêu chính phủ trên GDP trung bình của nước đó. Bước chia này đổi từ đơn vị phần trăm sang đơn vị tiền: một đồng chi thêm tạo ra bao nhiêu đồng GDP.

**Kết quả cơ sở: phản ứng xung.** Một cú sốc chi tiêu dương kích hoạt mức tăng mạnh và ngay lập tức của chi tiêu chính phủ, đạt đỉnh khoảng 0,4% quanh kỳ hạn một năm và duy trì cao trong suốt hai năm. Phản ứng của sản lượng dương ở mọi kỳ hạn, dao động từ 0,06 đến 0,08%. Các con số trung bình này che giấu khác biệt lớn giữa các nước: cú sốc đi kèm phản ứng chi tiêu lớn hơn ở nền kinh tế đang phát triển điển hình so với nước tiên tiến điển hình; phản ứng GDP cũng lớn hơn ở nước đang phát triển, nhưng khác biệt đó không có ý nghĩa thống kê vì dải tin cậy chồng lấn.

**Số nhân gộp bằng trọng số nghịch đảo phương sai** (nước nào ước lượng chính xác hơn được tính nặng hơn):

| Mẫu | Sau 1 năm | Sau 2 năm |
|---|---|---|
| Toàn mẫu (nước trung vị) | 0,74 | 0,67 |
| Nước tiên tiến | 0,70 | 0,61 |
| Thị trường mới nổi và đang phát triển (EMDE) | 0,80 | 0,81 |

Các giá trị này nằm gọn trong khoảng mà tài liệu hiện có báo cáo (theo tổng quan của Ramey 2019).

Vì sao số nhân hai nhóm gần nhau trong khi phản ứng chi tiêu ở nước đang phát triển lớn hơn? Vì bước chia cho tỷ trọng chi tiêu trên GDP. Tỷ trọng này lớn hơn nhiều ở nước tiên tiến trung vị (39%) so với nước đang phát triển trung vị (17%). Ví dụ minh hoạ: cùng một mức tăng chi tiêu 1% thì ở nước tiên tiến tương đương 0,39% GDP, còn ở nước đang phát triển chỉ tương đương 0,17% GDP; việc quy đổi này kéo hai số nhân lại gần nhau. Đồng thời, khác biệt bên trong mỗi nhóm rất lớn: khoảng tứ phân vị (từ nước ở vị trí 25% tới nước ở vị trí 75%) của số nhân mỗi nhóm trải xấp xỉ từ 0 đến 1,5. Một con số trung bình cho cả nhóm vì thế ít giá trị với từng nước.

**Lợi thế của dữ liệu quý.** So sánh số nhân ước lượng từ dữ liệu quý và từ dữ liệu năm:

| Mẫu | 1 năm: quý / năm | 2 năm: quý / năm |
|---|---|---|
| Toàn mẫu | 0,74 / 0,72 | 0,67 / 0,61 |
| Tiên tiến | 0,70 / 0,84 | 0,61 / 0,63 |
| EMDE | 0,80 / 0,58 | 0,81 / 0,60 |

Khác biệt giữa hai tần suất đáng kể, nhất là ở nhóm EMDE, cho thấy nguy cơ thiên lệch khi dùng dữ liệu năm. Có hai nguyên nhân:

1. **Cú sốc năm dễ dự đoán hơn** (như phần 4 đã chỉ ra), nên ước lượng bị thiên lệch do bỏ sót các biến vĩ mô có liên quan.
2. **Bản thân việc gộp đã gây thiên lệch**, ngay cả khi cú sốc không dự đoán được. Stram và Wei (1986) chỉ ra rằng nếu quá trình sinh dữ liệu thật ở tần suất quý là tự hồi quy (AR, mỗi giá trị phụ thuộc vào các giá trị trước), thì khi gộp lên năm nó trở thành quá trình tự hồi quy trung bình trượt (ARMA, có thêm thành phần phụ thuộc vào các cú sốc quá khứ). Ước lượng VAR ở cấp năm mà bỏ qua thành phần trung bình trượt dẫn đến sai đặc tả mô hình và ước lượng thiên lệch.

### 6. Khác biệt giữa các nước

Phần này hỏi: số nhân tính từ proxy tự sự quý có tái hiện các quy luật liên quốc gia mà Ilzetzki, Mendoza và Vegh (2013), viết tắt IMV, đã nêu hay không. Bài gộp các nước thành bảng panel quý và ước lượng hiệu ứng động của chi tiêu chính phủ riêng cho từng nhóm nước, chia theo các đặc điểm cơ cấu và thể chế thay đổi chậm. Bảng dưới ghi số nhân tích luỹ sau 4 quý (M4, tức một năm) và sau 8 quý (M8, tức hai năm); số trong ngoặc là số nước trong nhóm.

| Đặc điểm | Nhóm | M4 | M8 |
|---|---|---|---|
| Độ mở thương mại | Đóng (26 nước) | 1,425 | 1,364 |
| | Mở (34 nước) | 0,558 | 0,649 |
| Nợ công | Thấp (56) | 0,738 | 0,893 |
| | Cao (26) | 0,821 | 0,851 |
| Chế độ tỷ giá | Cố định (51) | 1,104 | 1,119 |
| | Thả nổi (8) | 0,715 | 0,703 |
| Phi chính thức | Thấp (28) | 1,173 | 1,195 |
| | Cao (28) | 0,788 | 0,798 |
| Linh hoạt thị trường lao động | Thấp (25) | 1,439 | 1,347 |
| | Cao (24) | 1,560 | 1,662 |

**Độ mở thương mại** tái hiện quy luật trung tâm của IMV: số nhân nhỏ hơn ở nền kinh tế mở hơn. Số nhân một năm là 1,425 ở nhóm tương đối đóng và 0,558 ở nhóm mở, với cùng thứ hạng ở hai năm (1,364 so với 0,649). Điều này khớp với logic rò rỉ nhập khẩu: ở nền kinh tế mở, phần lớn hơn của cầu tăng thêm bị hàng nhập khẩu hấp thụ, làm phản ứng của sản lượng trong nước yếu đi.

**Nợ công** cho thấy khác biệt hạn chế. Số nhân một năm và hai năm tương tự nhau ở trạng thái nợ thấp và nợ cao. Trong thiết kế panel gộp này, số nhân thay đổi theo độ mở và chế độ tỷ giá mạnh hơn nhiều so với theo mức nợ.

**Chế độ tỷ giá** cho quy luật kinh điển còn lại của IMV: số nhân lớn hơn dưới tỷ giá cố định. Với tỷ giá cố định, số nhân tích luỹ gần bằng 1 và được ước lượng chính xác (1,104 và 1,119, cả hai khác không về mặt thống kê). Với tỷ giá thả nổi, ước lượng điểm nhỏ hơn (0,715 và 0,703), nhưng suy luận yếu hơn nhiều vì nhóm này chỉ có 8 nước và khoảng tin cậy 90% chứa số không. Vì vậy kết quả nên được xem chủ yếu là bằng chứng mạnh về **thứ hạng** (cố định cao hơn thả nổi), không phải về con số chính xác.

**Phi chính thức**, đo bằng chỉ số của Medina và Schneider (2018), nổi lên như một yếu tố quan trọng về lượng đối với truyền dẫn tài khoá. Số nhân giảm từ 1,173 ở nhóm phi chính thức thấp xuống 0,788 ở nhóm phi chính thức cao sau một năm, và khoảng cách tương tự sau hai năm (1,195 so với 0,798).

**Linh hoạt thị trường lao động**, đo bằng chỉ số bảo vệ việc làm của Alesina và cộng sự (2024): thị trường lao động linh hoạt hơn đi kèm số nhân lớn hơn. Khoảng cách khiêm tốn sau một năm (1,560 so với 1,439) và rõ hơn sau hai năm (1,662 so với 1,347).

### 7. Phụ thuộc trạng thái theo thời gian

Ngoài các đặc điểm cơ cấu thay đổi chậm, số nhân có thể thay đổi theo trạng thái của nền kinh tế ở từng thời điểm. Bài xét ba loại trạng thái; hai loại đầu nằm ở mục này, loại thứ ba (chính trị) ở mục 8.

**Chu kỳ kinh doanh.** Một khối lớn tài liệu lý thuyết và thực nghiệm ghi nhận số nhân thường lớn hơn trong suy thoái, và khi chi tiêu tăng đi kèm nới lỏng chính sách tiền tệ. Bài dùng một chỉ số tăng trưởng liên tục, xác định trước, và ước lượng một VAR panel proxy chuyển tiếp trơn, theo sát cách của Auerbach và Gorodnichenko (2012): một hàm logistic áp lên tăng trưởng sản lượng trễ quyết định nền kinh tế đang ở gần trạng thái "tăng trưởng cao" hay "tăng trưởng thấp", và hệ số của mô hình chuyển dần giữa hai trạng thái. Điểm khác biệt then chốt là bài nhúng cấu trúc chuyển tiếp trơn vào khung panel proxy-SVAR và cho phép chính mô men công cụ bên ngoài thay đổi theo trọng số của từng trạng thái.

| Đặc tả | 1 năm: tăng trưởng cao / thấp | 2 năm: tăng trưởng cao / thấp |
|---|---|---|
| VAR sai phân log (Δlog) | −0,01 / 0,77 | −0,01 / 0,77 |
| VAR log mức | 0,25 / 0,74 | 0,58 / 1,39 |

Hai điều nổi lên. Thứ nhất, các ước lượng điểm gợi ý số nhân mạnh hơn khi tăng trưởng yếu. Theo đặc tả sai phân log, số nhân khi tăng trưởng cao về cơ bản bằng không, còn khi tăng trưởng thấp khoảng 0,77 ở cả hai kỳ hạn. Theo đặc tả log mức, số nhân dương ở cả hai trạng thái nhưng vẫn lớn hơn khi tăng trưởng thấp. Thứ hai, khác biệt này chỉ mang tính gợi ý và chưa được ước lượng chính xác: chỉ bác bỏ được giả thuyết hai số nhân bằng nhau ở mức tin cậy khoảng 10%, cho đặc tả cơ sở ở kỳ hạn một năm (p = 0,11).

**Bất định chính sách.** Bài dùng các thước đo bất định xây từ chính báo cáo EIU, nhờ đó phạm vi nước khớp chặt với proxy tự sự:

- **Chỉ số Bất định Thế giới (WUI)** của Ahir và cộng sự (2022): đếm tần suất từ "uncertain" và các biến thể trong báo cáo EIU, chia cho độ dài báo cáo.
- **Chỉ số bất định tập trung vào chính sách tài khoá (FUI)**: cùng cách khai thác văn bản, nhưng chỉ đếm trong các đoạn về chính sách tài khoá và tài chính công.

| Kỳ hạn | WUI: bất định thấp / cao | FUI: bất định thấp / cao |
|---|---|---|
| 1 năm | 1,04 / 0,51 | 0,95 / 0,21 |
| 2 năm | 1,09 / 0,42 | 1,13 / 0,18 |

Dưới cả hai khái niệm bất định, bất định cao đi kèm truyền dẫn tài khoá yếu hơn rõ rệt: với bất định rộng, số nhân một năm giảm từ khoảng 1,04 xuống 0,51 và số nhân hai năm từ 1,09 xuống 0,42; với bất định tài khoá, từ 0,95 xuống 0,21 và từ 1,13 xuống 0,18. Tuy vậy, khoảng tin cậy bootstrap cho hiệu số "cao trừ thấp" rộng và chứa số không, phản ánh độ chính xác hạn chế khi chia mẫu theo trạng thái.

### 8. Ủng hộ chính trị

Một khối lớn tài liệu kinh tế chính trị lập luận rằng tác động vĩ mô của chính sách tài khoá, và đặc biệt sự thành công của các đợt củng cố, phụ thuộc vào môi trường chính trị. Sự ủng hộ đa số trong nghị viện, độ ổn định của nội các và thời điểm bầu cử định hình cả thành phần lẫn độ bền của các gói tài khoá, cũng như khả năng chính phủ giữ vững lộ trình khi các biện pháp trở nên không được lòng dân.

**Cách mã hoá.** Bài bổ sung một chỉ báo tự sự theo quý về việc môi trường chính trị có thuận lợi cho việc thông qua và duy trì các biện pháp tài khoá hay không. Với mỗi nước–quý, một prompt mô hình ngôn ngữ lớn cố định, chạy trong cùng môi trường an toàn và không thích nghi như chuỗi tài khoá, đọc phần "Domestic politics" (Chính trị trong nước) và các phần liên quan của báo cáo EIU. Chỉ báo Supp = 1 khi cả ba điều kiện cùng đúng:

1. hành pháp được một đa số làm việc được trong cơ quan lập pháp hậu thuẫn;
2. không có bầu cử quốc gia trong quý này hoặc quý tới;
3. báo cáo không nêu bật bất ổn chính trị, bế tắc kéo dài hay tê liệt lập pháp đáng kể.

Mô hình trả về các trích đoạn nguyên văn ngắn làm căn cứ cho mỗi phân loại, được giữ để kiểm toán. Vì "ủng hộ" là khái niệm nhiều chiều, ba thành tố gốc cũng được mã hoá riêng từ cùng văn bản: đa số và gắn kết (đa số lập pháp làm việc được hay liên minh ổn định), bầu cử sắp tới (bầu cử quốc gia lên lịch trong quý hiện tại hoặc quý tới), và bất ổn hay bế tắc nghiêm trọng. Văn bản chính trị bị thiếu khá phổ biến trong kho EIU; đặc tả cơ sở xử lý "thiếu" như một trạng thái riêng chứ không gán nó vào nhóm bất lợi hay thuận lợi, để tránh việc ước lượng ngầm xếp sự thiếu vắng vào một trong hai nhóm.

**Kết quả.**

| Kỳ hạn | Supp = 0 (bất lợi) | Supp = 1 (thuận lợi) | Thiếu văn bản |
|---|---|---|---|
| h = 4 quý | không báo cáo | 1,0590 | 1,1078 |
| h = 8 quý | 0,1880 | 0,9627 | −0,6868 |

Trong môi trường chính trị thuận lợi, số nhân nhất quán dương và có ý nghĩa kinh tế: ở các kỳ hạn một đến ba năm, số nhân tính theo đô la khoảng 1,0 đến 1,1. Dưới ủng hộ bất lợi, số nhân gần bằng không và đôi khi hơi âm.

**Cơ chế.** Động lực chính của sự khác biệt này là phản ứng của **chi tiêu được thực hiện**, không phải phản ứng của sản lượng trên mỗi đồng chi. Trong các quý ủng hộ thấp, chi tiêu tích luỹ (ở dạng rút gọn) phản ứng nhỏ và không ổn định ở kỳ hạn ngắn, nên số nhân không xác định rõ. Dưới ủng hộ cao, cùng một cú sốc tự sự chuyển thành phản ứng chi tiêu tích luỹ lớn hơn hẳn, và sản lượng phản ứng dương. Chênh lệch chi tiêu tích luỹ giữa quý có và không có ủng hộ lớn và có ý nghĩa thống kê ở kỳ hạn trung bình: ΔRF = 0,0182 ở h = 4, thống kê t = 2,94. Nói cách khác, ủng hộ chính trị làm tăng khả năng những hành động chi tiêu đã công bố hay đã được lập pháp thực sự được thực thi và duy trì.

**Chiều nào quan trọng?** Bài tách "ủng hộ" thành ba thành tố (đa số và gắn kết, bầu cử sắp tới, bất ổn và bế tắc) và ước lượng cùng lúc. Bảng dưới ghi hệ số tương tác với cú sốc z; số trong ngoặc là thống kê t.

| Kỳ hạn | z × Ủng hộ | z × Bầu cử sắp tới | Hiệu ứng ròng |
|---|---|---|---|
| h = 4 | 0,02044 (2,17) | −0,01956 (−2,20) | 0,00088 |
| h = 8 | 0,01955 (2,26) | −0,01834 (−2,75) | 0,00121 |

Hai kết luận. Thứ nhất, ngay cả khi kiểm soát các thành tố, ủng hộ thuận lợi vẫn gắn với phản ứng chi tiêu tích luỹ mạnh hơn đáng kể ở kỳ hạn trung bình. Thứ hai, bầu cử sắp tới gắn độc lập với truyền dẫn chi tiêu yếu hơn hẳn: hệ số khoảng −0,018 đến −0,020, đều có ý nghĩa thống kê. Hai độ lớn gần như bằng nhau, nên hiệu ứng ròng gần bằng không: một cuộc bầu cử sắp tới có thể gần như triệt tiêu lợi thế thực thi mà ủng hộ chính trị mang lại.

**Kiểm tra.** Một mối lo là bản thân cú sốc có thể khác nhau giữa các trạng thái chính trị, ví dụ chính phủ được ủng hộ thì hay thắt chặt hơn. Bài kiểm tra thành phần dấu của cú sốc và thấy gần như y hệt: tỷ lệ cú sốc thắt chặt (z = −1) là 0,551 khi Supp = 0 và 0,546 khi Supp = 1. Vậy kết quả không đến từ việc chọn lọc dấu đơn giản.

**Tách bạch khỏi mã hoá tài khoá.** Các biến bối cảnh chính trị không bao giờ được dùng để phân loại một hành động tài khoá là ngoại sinh hay nội sinh. Việc sàng lọc ngoại sinh chỉ dựa vào động cơ được nêu trong văn bản tài khoá; biến chính trị chỉ dùng để đánh dấu môi trường trong đó các hành động ngoại sinh đã xác định diễn ra.

### 9. Kết luận và hướng tiếp theo

Bài phát triển cách tiếp cận tự sự có AI hỗ trợ đầu tiên để xác định cú sốc chi tiêu chính phủ ở tần suất quý, và dùng nó để xây một cơ sở dữ liệu toàn cầu mới về hành động tài khoá. Xây trên nền phương pháp Romer và Romer, nhóm tác giả cho thấy một mô hình ngôn ngữ lớn dùng nguyên bản, vận hành dưới một prompt cố định trong môi trường an toàn và không thích nghi, có thể trích xuất đáng tin cậy lập trường và động cơ tài khoá từ văn bản. Quy trình được thiết kế thận trọng: prompt định sẵn và đồng nhất qua mọi nước và thời điểm, mô hình không được tinh chỉnh, và chỉ những hành động có động cơ rõ ràng không liên quan đến điều kiện vĩ mô đương thời mới được giữ lại là ngoại sinh.

Về phương pháp, bài cho thấy mô hình ngôn ngữ lớn có thể được đưa vào kinh tế vĩ mô thực nghiệm mà không làm hỏng việc nhận dạng nhân quả, với điều kiện vai trò của AI được giới hạn trong một nhiệm vụ phân loại minh bạch, định sẵn. Mọi prompt và quy tắc mã hoá đều được tài liệu hoá; cơ sở dữ liệu dạng máy đọc được công bố kèm mã nguồn và danh sách quốc gia để người khác tái lặp. Lớp văn bản tự sự đã rất phong phú; ràng buộc chính đối với việc mở rộng phạm vi không còn nằm ở năng lực của AI mà ở sự sẵn có của dữ liệu vĩ mô và tài khoá quý nhất quán. Đó là lý do kho EIU phủ hơn 140 nền kinh tế nhưng bài chỉ ước lượng được cho 64 nước.

Bài nêu ba hướng nghiên cứu tiếp theo:

1. **Mở rộng sang lĩnh vực khác**: điều chỉnh phương pháp cho các nguồn tự sự và lĩnh vực chính sách khác, như thay đổi thuế, can thiệp tín dụng và quy định, các hành động tiền tệ hay an toàn vĩ mô, nơi văn bản liên quan rất nhiều nhưng tốn kém để mã hoá bằng tay.
2. **Kết hợp với dữ liệu vi mô**: ghép cơ sở dữ liệu liên quốc gia với dữ liệu chi tiết về đầu tư doanh nghiệp, tiêu dùng hộ gia đình hay kết quả phân phối, để nghiên cứu ai chịu tác động của cú sốc tài khoá và cú sốc gồm những thành phần nào.
3. **Thêm đặc điểm thể chế**: mở rộng các chiều chính trị và bất định đã khám phá, để bao gồm quy tắc tài khoá hay tính độc lập của ngân hàng trung ương, và nghiên cứu tương tác giữa chính sách tài khoá và chính sách tiền tệ.

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

## Đánh giá và phát hiện đáng chú ý

### Đóng góp thật không phải con số 0,74 mà là việc một điểm nghẽn bốn mươi năm vừa bị dời chỗ

Số nhân 0,74 ở một năm và 0,67 ở hai năm, như chính bài thừa nhận, nằm gọn trong khoảng mà tài liệu hiện có đã báo cáo. Nếu đọc bài như một bài ước lượng số nhân, nó xác nhận điều đã biết.

Giá trị thật nằm ở chỗ khác. Từ năm 2010, phương pháp tự sự đã là chuẩn vàng để nhận dạng cú sốc tài khoá, và suốt mười lăm năm nó chỉ phủ được vài nước. Lý do không phải là lý thuyết mà là **giờ đọc của chuyên gia**. Mỗi cú sốc đòi hỏi một người có chuyên môn đọc tài liệu gốc, hiểu bối cảnh chính trị, và phán đoán về động cơ. Nguồn lực đó khan hiếm, đắt, và không mở rộng theo quy mô. Đó là lý do tài liệu về truyền dẫn tài khoá gần như là tài liệu về Hoa Kỳ.

Bài này gỡ bỏ đúng ràng buộc đó, và kết quả là 16.029 quan sát nước–quý với 8.636 đợt chi tiêu được xác định, phủ từ 1952 và bao gồm 1.920 quý của các nước thu nhập thấp — một nhóm trước đây gần như vắng mặt hoàn toàn khỏi loại nghiên cứu này.

Câu kết luận của bài về điểm nghẽn mới đáng được đọc kỹ: ràng buộc chính không còn nằm ở năng lực AI mà ở **sự sẵn có của dữ liệu vĩ mô và tài khoá quý nhất quán**. Đây là một sự dời chỗ có hệ quả thực tiễn rất cụ thể cho các nước đang phát triển. Trước đây, muốn biết số nhân chi tiêu của chính nước mình, cần một chương trình nghiên cứu nhiều năm và một nhóm chuyên gia. Bây giờ, cái cần là **một chuỗi số liệu tài khoá và tài khoản quốc gia theo quý đủ dài và đủ nhất quán** — tức là một khoản đầu tư vào cơ quan thống kê, không phải vào viện nghiên cứu. Đó là một thông điệp về ưu tiên ngân sách mà ít ai rút ra từ một bài kinh tế lượng.

### Bài giải đúng bài toán khó nhất của việc dùng mô hình ngôn ngữ trong nghiên cứu, và cách giải nên trở thành chuẩn

Vấn đề trung tâm khi đưa mô hình ngôn ngữ vào một quy trình nghiên cứu kinh tế là mô hình **không tất định**: chạy lại cùng một câu lệnh có thể ra kết quả khác. Kinh tế học đã xây toàn bộ chuẩn mực tái lập quanh dữ liệu và mã lệnh, cả hai đều tĩnh; một bước xử lý không tĩnh phá vỡ chuẩn mực đó.

Cách bài xử lý vấn đề này là phần đáng học nhất, và nó gồm ba động tác.

**Thứ nhất, đo mức độ không tất định thay vì giả định nó nhỏ.** Chạy lại năm mươi mốt lần trên hai mươi báo cáo và báo cáo tỷ trọng mode **riêng cho từng trường đầu ra**. Kết quả cho một thứ hạng rất rõ: hướng của lập trường tài khoá hoàn toàn ổn định, tỷ trọng mode bằng một ở cả hai mươi báo cáo; động cơ thấp hơn một chút; cường độ và độ tin cậy thì phân tán đáng kể.

**Thứ hai, và đây là động tác quyết định: thiết kế lại mô hình kinh tế lượng quanh đúng trường ổn định.** Prompt sinh ra năm trường, trong đó có một thang cường độ từ âm mười tới mười — một thang trông rất hấp dẫn về mặt kinh tế lượng vì nó cho độ lớn chứ không chỉ dấu. Nhóm tác giả **vứt bỏ nó** và chỉ dùng phân loại dấu ba giá trị. Đây là một sự tự kiềm chế đáng kể, và nó được biện minh bằng bằng chứng chứ không bằng trực giác.

Việc bỏ độ lớn lẽ ra sẽ là một tổn thất nghiêm trọng cho việc nhận dạng, và bài giải quyết nó bằng một mẹo kỹ thuật gọn: đặt proxy ở vị trí đầu tiên trong VAR, để **phản ứng đồng thời của chi tiêu thực hiện tự ghim thang đo** của cú sốc cấu trúc. Nói cách khác, độ lớn được lấy từ dữ liệu chi tiêu thật chứ không từ phán đoán của mô hình ngôn ngữ. Mô hình ngôn ngữ chỉ làm đúng việc nó làm đáng tin cậy — nói hướng — còn dữ liệu làm phần còn lại.

**Thứ ba, giữ lại trích đoạn nguyên văn kích hoạt mỗi phân loại và công bố cùng chuỗi đã mã hoá.** Điều này quan trọng hơn vẻ ngoài thủ tục của nó, vì nó là giải pháp duy nhất cho một vấn đề chưa ai giải được: GPT-4.1 sẽ bị ngừng phục vụ trong vài năm. Khi đó câu lệnh vẫn còn nhưng công cụ thì không, và không ai chạy lại được. Nhưng nếu có trích đoạn nguyên văn, một nhà nghiên cứu tương lai vẫn **kiểm tra được bằng tay** rằng phân loại đó có hợp lý hay không, kể cả khi mô hình đã biến mất.

Ba động tác này nên trở thành quy trình chuẩn cho mọi nghiên cứu dùng mô hình ngôn ngữ làm bước xử lý dữ liệu: đo độ tái lặp theo từng trường, chỉ dùng trường nào đủ ổn định, và lưu bằng chứng văn bản để kiểm chứng được sau khi công cụ đã lỗi thời.

### Hai lỗi thật của mô hình có cùng bản chất, và nó mô tả chính xác giới hạn hiện nay của công cụ

Con số 93% gây ấn tượng, nhưng hai lỗi được xác định thì thông tin hơn nhiều, vì chúng cùng một loại.

Ở trường hợp Hàn Quốc, mô hình bỏ sót một gợi ý động cơ chính trị rõ ràng trong văn bản. Ở trường hợp Hoa Kỳ, mô hình **liệt kê đúng từng biện pháp** nhưng rồi suy ra lập trường tổng thể từ một nhận xét về thâm hụt tăng và gán sai dấu cho hiệu ứng ròng.

Cả hai đều không phải lỗi đọc hiểu. Chúng là lỗi ở bước **tổng hợp nhiều dữ kiện thành một phán đoán tổng thể** — bước đòi hỏi giữ vài sự kiện mâu thuẫn trong đầu cùng lúc và cân chúng với nhau. Bài cũng nói rằng phần lớn các "bất đồng" khác với chuyên gia đều nảy sinh ở những báo cáo mô tả đồng thời cả biện pháp mở rộng lẫn thắt chặt, tức là đúng những trường hợp cần cân.

Điều này khớp chính xác với kết quả về độ tái lặp: **trích xuất thì ổn định, đánh giá thì không**. Hai bằng chứng độc lập, cùng một kết luận. Và kết luận đó là mô tả tốt nhất hiện có về vị trí của mô hình ngôn ngữ trong một quy trình nghiên cứu: dùng nó để tìm và trích, đừng dùng nó để kết luận.

Cần thêm một cảnh báo về chính con số 93% mà bài không nêu. Phép kiểm chứng được thực hiện trên 200 báo cáo thuộc **các đợt căng thẳng tài chính** ở 19 nước. Đó là những giai đoạn mà chính sách tài khoá được bàn nhiều nhất, được nêu động cơ rõ nhất và được viết rành mạch nhất trong báo cáo. Nhưng phần lớn trong số 16.029 quan sát của bộ dữ liệu là những quý bình thường, nơi văn bản mờ nhạt hơn và động cơ ít khi được nêu thẳng. Độ chính xác trên mẫu ứng dụng vì vậy nhiều khả năng **thấp hơn** độ chính xác trên mẫu kiểm chứng, và ta không biết thấp hơn bao nhiêu. Mẫu kiểm chứng không đại diện cho mẫu ứng dụng — đây là hạn chế đáng kể và không khó khắc phục, chỉ cần lấy một mẫu ngẫu nhiên các quý bình thường và cho chuyên gia đọc song song.

### Phép kiểm tra tính không dự đoán được có hai cách đọc, và bài chỉ trình bày cách có lợi cho mình

Toàn bộ khả năng diễn giải nhân quả của bài phụ thuộc vào một phép kiểm tra: cú sốc có dự báo được bằng các chỉ báo vĩ mô trễ hay không. Kết quả ở tần suất quý là yên tâm — yếu tố dự báo vững duy nhất là chính độ trễ của cú sốc, hệ số của nợ trên GDP, chênh lệch sản lượng và tăng trưởng GDP đều không phân biệt được với không, và R² không quá 0,1.

Nhưng khi gộp cùng những cú sốc đó lên tần suất năm, tính dự đoán được **tăng rõ rệt**: R² lên 0,125, và nợ trên GDP trễ cùng tăng trưởng GDP trễ trở thành yếu tố dự báo có ý nghĩa thống kê.

Bài diễn giải điều này theo hướng có lợi: dữ liệu tần suất cao sạch hơn, và thông tin hệ thống về điều kiện vĩ mô dễ lộ ra hơn khi nhìn ở tần suất năm. Cách đọc này có thể đúng.

Nhưng có một cách đọc thứ hai không được nêu và cũng phù hợp với cùng số liệu: dữ liệu quý có **tỷ lệ tín hiệu trên nhiễu thấp hơn**, nên tính dự đoán được có hệ thống **khó phát hiện hơn**, chứ không phải không tồn tại. Cùng những hành động chính sách ấy, nhìn ở một tần suất thì trông ngoại sinh, nhìn ở tần suất khác thì trông nội sinh. Không thể vừa là một vừa là kia.

Đây là sự khác biệt giữa "không bác bỏ được giả thuyết không dự đoán được" và "đã chứng minh là không dự đoán được", và trong bối cảnh này nó không phải một chi tiết học thuật. Nếu cách đọc thứ hai đúng, các số nhân quý đang bị nhiễm nội sinh nhiều hơn vẻ ngoài của chúng, và phần chênh lệch giữa ước lượng quý và ước lượng năm — vốn được bài trình bày như bằng chứng về thiên lệch của dữ liệu năm — có thể mang cả dấu vết của vấn đề ngược lại.

### Kết quả quan trọng nhất nằm ở mục cuối cùng và nó không phải một kết quả về chính sách tài khoá

Bài dành phần lớn dung lượng cho phương pháp và cho các quy luật liên quốc gia quen thuộc. Nhưng kết quả có sức nặng lớn nhất nằm ở mục về ủng hộ chính trị, và nó lớn hơn mọi kết quả khác theo đúng nghĩa số học.

Trong môi trường chính trị thuận lợi, số nhân khoảng 1,0 tới 1,1. Dưới ủng hộ bất lợi, số nhân **gần bằng không**. Khoảng biến thiên này lớn hơn khoảng biến thiên theo độ mở thương mại, theo chế độ tỷ giá, theo mức phi chính thức, theo linh hoạt lao động, theo trạng thái chu kỳ và theo bất định — tức là lớn hơn mọi chiều khác mà bài kiểm tra.

Và cơ chế đã được nhận dạng, không phải suy đoán: nó chạy qua **kênh thực hiện**. Chênh lệch nằm ở phản ứng của chi tiêu thực hiện, không ở phản ứng của sản lượng trên mỗi đồng chi. Ủng hộ chính trị làm tăng khả năng những hành động đã công bố hay đã lập pháp **thực sự được chi ra và duy trì**.

Điều này đặt lại toàn bộ cuộc tranh luận về số nhân. Câu hỏi thông thường là "một đồng chi thêm tạo ra bao nhiêu đồng sản lượng" — một câu hỏi về phía cầu, về độ dốc của đường IS, về rò rỉ nhập khẩu và về phản ứng của chính sách tiền tệ. Kết quả này nói rằng một phần rất lớn của sự khác biệt giữa các nước đến từ một câu hỏi **đứng trước** câu hỏi đó: đồng tiền đã công bố có thực sự được chi ra hay không. Đó là một câu hỏi về hành chính công và kinh tế chính trị, không phải về kinh tế vĩ mô.

Kết quả về bầu cử còn sắc hơn và có dấu phản trực giác: bầu cử sắp tới gắn với truyền dẫn chi tiêu **yếu hơn hẳn**, với độ lớn gần như triệt tiêu toàn bộ lợi thế mà ủng hộ chính trị mang lại. Điều này trái với trực giác về chu kỳ kinh doanh chính trị, vốn nói rằng chính phủ chi nhiều hơn trước bầu cử.

Bài không hoà giải hai điều này, nhưng lời hoà giải nằm sẵn trong thiết kế của chính nó. Các cú sốc ở đây được sàng lọc để **ngoại sinh theo động cơ**: chúng là những biện pháp vì mục tiêu dài hạn hoặc vì mất cân đối thừa kế. Chi tiêu vì bầu cử, theo định nghĩa, có động cơ gắn với điều kiện chính trị ngắn hạn và phần lớn đã bị loại khỏi mẫu. Vậy kết quả không nói "chính phủ chi ít hơn trước bầu cử". Nó nói một điều cụ thể và hữu ích hơn nhiều: **các chương trình chi tiêu mang tính cơ cấu, không theo chu kỳ, bị đình lại khi bầu cử tới gần**. Cải cách và đầu tư dài hạn nhường chỗ cho những thứ khác.

### Một bất đối xứng mô tả bị bỏ phí, và nó gợi ý phần mở rộng tự nhiên nhất của bài

Thống kê mô tả cho thấy mở rộng và thắt chặt **không phải hình ảnh phản chiếu của nhau**. Gần 60% các đợt mở rộng là tăng đầu tư công, đặc biệt hạ tầng và dự án vốn. Hơn hai phần ba các đợt thắt chặt là biện pháp củng cố rõ ràng như kìm hãm chi tiêu và giảm thâm hụt.

Đây là một quan sát quan trọng và nó mâu thuẫn ngầm với đặc tả kinh tế lượng của chính bài. Mô hình VAR ước lượng một phản ứng tuyến tính và đối xứng theo dấu: một cú sốc âm được giả định có tác động bằng và ngược chiều với một cú sốc dương. Nhưng nếu cú sốc dương chủ yếu là **chi đầu tư** còn cú sốc âm chủ yếu là **cắt chi thường xuyên trên diện rộng**, thì hai loại này khác nhau về bản chất kinh tế, không chỉ về dấu.

Chi đầu tư công có một thành phần phía cung mà chi thường xuyên không có: nó tạo ra tài sản hạ tầng làm tăng năng lực sản xuất về sau. Theo lý thuyết, số nhân của nó phải lớn hơn và phải tích luỹ ở kỳ hạn dài hơn, chứ không đạt đỉnh rồi giảm trong hai năm. Một số nhân đối xứng duy nhất đang lấy trung bình của hai đối tượng kinh tế khác nhau, và không ai biết trung bình đó nằm gần cái nào.

Phần mở rộng tự nhiên nhất, và bài không nêu trong ba hướng nghiên cứu tiếp theo của mình, là **kiểm định bất đối xứng theo dấu**. Dữ liệu đã có sẵn: 4.374 đợt mở rộng và 4.262 đợt thắt chặt, gần như cân bằng hoàn hảo, và trường động cơ cùng trường thành phần chi tiêu đã được mã hoá sẵn trong chính prompt.

Điều này đặc biệt quan trọng với nhóm thu nhập thấp, nơi 60,7% các hành động là mở rộng và phần lớn trong số đó là đầu tư hạ tầng. Nghĩa là với nhóm nước này, cái mà bài gọi là "số nhân chi tiêu" trên thực tế gần với **hiệu quả của đầu tư công** hơn là với số nhân Keynes cổ điển. Và hiệu quả của đầu tư công thì phụ thuộc vào chất lượng lựa chọn dự án, chất lượng thẩm định và mức thất thoát trong thi công — đúng những vấn đề được bàn trong các tài liệu về đầu tư công và nợ công ở thư mục khác của kho này. Hai dòng nghiên cứu đang nói về cùng một hiện tượng bằng hai ngôn ngữ khác nhau.

### Với Việt Nam: các quy luật liên quốc gia kéo ngược nhau, nhưng kênh thực hiện thì không mơ hồ

Chiếu các đặc điểm cơ cấu của Việt Nam vào bảng phân nhóm của bài cho một kết quả mâu thuẫn, và sự mâu thuẫn đó tự nó là thông tin.

**Độ mở thương mại kéo số nhân xuống rất mạnh.** Đây là khoảng cách lớn nhất trong toàn bộ bảng: 1,425 cho nền kinh tế tương đối đóng so với 0,558 cho nền kinh tế mở. Việt Nam thuộc nhóm có tỷ lệ thương mại trên GDP cao nhất thế giới, nên theo quy luật rò rỉ nhập khẩu, một phần lớn của cầu thêm sẽ chảy ra nước ngoài thay vì kích hoạt sản xuất trong nước.

**Chế độ tỷ giá kéo số nhân lên.** Với tỷ giá được neo hoặc ổn định hoá, số nhân là 1,104 so với 0,715 của chế độ thả nổi, vì chính sách tiền tệ không phản ứng bù trừ bằng cách để đồng tiền lên giá.

**Mức phi chính thức kéo số nhân xuống**, từ 1,173 xuống 0,788, và đây là chiều mà Việt Nam nằm ở phía bất lợi với một khu vực phi chính thức chiếm tỷ trọng đáng kể trong việc làm.

Ba lực này không cùng chiều, nên không rút ra được một dự đoán gọn gàng từ các quy luật nhóm. Kết luận trung thực là **ước lượng riêng cho từng nước quan trọng hơn trung bình nhóm**, và khoảng tứ phân vị trải từ 0 tới 1,5 trong mỗi nhóm mà bài báo cáo chính là bằng chứng cho điều đó.

Nhưng kênh thực hiện thì không mơ hồ chút nào, và đây là chỗ bài chạm trực tiếp vào một vấn đề được thảo luận công khai ở Việt Nam suốt nhiều năm. Vấn đề thường trực của các gói kích thích và các chương trình đầu tư công ở đây **không phải là tiền chi ra không có tác dụng, mà là tiền không chi ra được**: giải ngân chậm, vốn được bố trí nhưng không tiêu hết, dự án kéo dài qua nhiều năm kế hoạch.

Theo đúng kết quả của bài, đó chính là tình huống số nhân gần bằng không — không phải vì nền kinh tế không phản ứng, mà vì cú sốc không bao giờ thực sự xảy ra. Và nếu sửa được kênh thực hiện có thể nâng số nhân hữu hiệu từ gần không lên khoảng một, thì **lợi ích của việc sửa bộ máy giải ngân lớn hơn lợi ích của việc tăng quy mô gói**. Một gói lớn gấp đôi mà giải ngân được một nửa thì bằng một gói bình thường giải ngân đủ, nhưng tốn gấp đôi dư địa tài khoá.

Điều này nối thẳng với phân tích về công nghệ trong quản lý tài chính công ở cùng thư mục, nơi điểm nghẽn được mô tả cụ thể tới từng bước — nghiệm thu khối lượng, xác nhận tiến độ, hoàn thiện hồ sơ thanh toán — và nơi chỉ 86 trên 193 nước có hệ thống số hoá cho quản lý đầu tư công. Hai tài liệu tiếp cận từ hai phía hoàn toàn khác nhau, một bên là kinh tế lượng vĩ mô và một bên là quản trị công, và cùng chỉ vào một kết luận: **ở nhiều nước, biến số quyết định hiệu lực của chính sách tài khoá không nằm trong mô hình vĩ mô mà nằm trong quy trình hành chính**.

Cuối cùng, một hàm ý về đầu tư thống kê. Bài nói rõ ràng buộc để mở rộng phạm vi không phải AI mà là dữ liệu vĩ mô và tài khoá quý nhất quán. Một nước muốn có ước lượng số nhân của riêng mình — thay vì mượn con số trung bình của một nhóm mà mình chỉ giống một phần — cần trước hết một chuỗi tài khoản quốc gia và số liệu tài khoá theo quý, đủ dài và không bị đứt gãy phương pháp. Khoản đầu tư đó phục vụ mọi mục đích khác, và giờ đây nó còn là điều kiện để trả lời một câu hỏi mà trước đây chỉ vài nước giàu mới trả lời được.

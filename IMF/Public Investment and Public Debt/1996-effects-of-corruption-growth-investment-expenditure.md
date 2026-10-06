# The Effects of Corruption on Growth, Investment, and Government Expenditure — Tác động của tham nhũng lên tăng trưởng, đầu tư và chi tiêu chính phủ

**Nguồn:** IMF Working Paper WP/96/98, tháng 9/1996, Vụ Xây dựng và Rà soát Chính sách. Bài cũng được in trong tập hội thảo "Corruption and the World Economy" do Kimberly Ann Elliott biên tập (Institute for International Economics).
**Tác giả:** Paolo Mauro.
**Ý chính:** Bài có hai phần. Phần đầu điểm lại các **nguyên nhân** và **hệ quả** của tham nhũng, tập trung vào những mối liên hệ kiểm định được bằng hồi quy xuyên quốc gia. Nguyên nhân chính là các **khoản đặc lợi**, phần lớn do chính sách nhà nước tạo ra: hạn chế thương mại, trợ cấp, kiểm soát giá, đa tỷ giá, lương công chức thấp. Ngoài ra còn các nguồn không do chính sách như tài nguyên thiên nhiên và yếu tố xã hội. Phần sau mở rộng Mauro (1995) với chỉ số tham nhũng là **bình quân hai chỉ số BI và ICRG** cho 106 nước. Cải thiện chỉ số tham nhũng thêm **một độ lệch chuẩn (2,38 điểm)** đi kèm **đầu tư tăng hơn 4 điểm phần trăm GDP** và **tăng trưởng GDP bình quân đầu người tăng khoảng 0,7 điểm phần trăm mỗi năm**. Phần lớn tác động lên tăng trưởng đi qua kênh đầu tư. Phát hiện mới là tham nhũng **làm thay đổi cơ cấu chi tiêu công**: nước tham nhũng hơn **chi ít hơn cho giáo dục**, khoảng **0,5% GDP** cho mỗi độ lệch chuẩn. Lý do có thể là khó thu hối lộ từ lương giáo viên và sách giáo khoa hơn so với từ dự án hạ tầng lớn hay vũ khí.

> **Lưu ý:** bản PDF quét bị mất chữ cuối dòng ở lề phải nhiều trang. Bài có một số điểm không khớp nội bộ:
> - Các mục được dẫn chiếu là "III.1, III.2, III.3", trong khi tiêu đề thực tế là A, B, C.
> - Phần giới thiệu nói "Mục IV kết luận", nhưng kết luận nằm ở Mục V.
> - Văn bản dẫn Keefer và Knack (1994) và Rauch (1993), còn danh mục tài liệu ghi 1995.
> - Chú thích 16 viết "khái quát hoá Barro (1991)", nhưng phụ lục khái quát hoá Barro (1990).
> - Chú thích Hình 1 ghi "ICGR" thay vì ICRG.
> - Ví dụ minh hoạ trong bài: tăng chỉ số từ 6 lên 8 điểm làm tăng trưởng tăng "gần nửa điểm phần trăm". Theo hệ số 0,0029 thì con số thực là khoảng 0,58 điểm, tức hơi hơn nửa điểm.
> - Câu "thêm đầu tư vào hồi quy tăng trưởng làm hệ số tham nhũng giảm khoảng hai phần ba, còn 0,0028" không rõ so với cột nào: so với cột 1 (0,0029) thì gần như không đổi, so với cột 3 (0,0038) chỉ giảm khoảng một phần tư; chỉ so với cột 2SLS (0,0081) mới giảm khoảng hai phần ba, nhưng cột 5 là OLS. Không có bản gốc đầy đủ để xác định nên giữ nguyên.

## Sơ đồ

### Đo tham nhũng như thế nào

```text
       ⚠ tham nhũng KHÓ ĐO vì bản chất che giấu
       → dùng chỉ số của CÔNG TY XẾP HẠNG TƯ NHÂN (bán cho công ty
         đa quốc gia, ngân hàng quốc tế), từ bảng hỏi chuẩn gửi
         chuyên gia tư vấn ở nhiều nước
       ┌──────────────────────┬───────────────┬──────────────────┐
       │ NGUỒN                │ GIAI ĐOẠN     │ SỐ NƯỚC          │
       ├──────────────────────┼───────────────┼──────────────────┤
       │ ICRG (Political Risk │ bình quân     │ hơn 100          │
       │ Services, IRIS tổng  │ 1982–1995     │                  │
       │ hợp)                 │               │                  │
       │ Business             │ bình quân     │ 67               │
       │ International (nay   │ 1980–1983     │                  │
       │ thuộc EIU)           │               │                  │
       └──────────────────────┴───────────────┴──────────────────┘
       thang 0 (tham nhũng nhất) → 10 (ít tham nhũng nhất)
       ★ tương quan giữa hai chỉ số r = 0,81 → có đồng thuận
       ★ chỉ số dùng trong bài = BÌNH QUÂN hai chỉ số (giảm sai số)
         106 nước · trung bình 5,85 · độ lệch chuẩn 2,38 ·
         thấp nhất 0,59 · cao nhất 10
       ═══════════════════════════════════════════════════════════
       ⚠ BA HẠN CHẾ
       ① chủ quan; chuyên gia có thể bị ảnh hưởng bởi CHÍNH kết
          quả kinh tế của nước đó → rủi ro NỘI SINH
       ② không phân biệt tham nhũng CẤP CAO (mua máy bay chiến đấu
          đắt để ăn hối lộ lớn) với CẤP THẤP (hối lộ lấy bằng lái)
       ③ không phân biệt tham nhũng CÓ TỔ CHỨC với KHÔNG CÓ TỔ
          CHỨC — loại sau tệ hơn vì không rõ đưa bao nhiêu, cho ai,
          đưa rồi có được việc không (Shleifer–Vishny 1993)
```

### Nguyên nhân của tham nhũng

```text
       GỐC RỄ: ĐẶC LỢI (rent) — lý thuyết tìm kiếm đặc lợi của
       Krueger 1974, Tullock 1967, Bhagwati 1982, Rose-Ackerman 1978
       ═══════════════════════════════════════════════════════════
       ❶ ĐẶC LỢI DO CHÍNH SÁCH TẠO RA (có thể sửa được)
       hạn chế thương mại ····· giấy phép nhập khẩu có giá trị →
                                hối lộ; ★ Ades–Di Tella 1994: độ mở
                                thương mại cao hơn đi kèm tham
                                nhũng THẤP hơn
       trợ cấp, ưu đãi thuế ···· chính sách công nghiệp; trợ cấp chế
                                tạo / GDP liên quan tới chỉ số tham
                                nhũng (Ades–Di Tella 1995)
       kiểm soát giá ··········· hối lộ để giữ đầu vào giá thấp hơn
                                thị trường
       đa tỷ giá, phân bổ ngoại tệ · hối lộ quản lý ngân hàng nhà
                                nước để được ngoại tệ nhập đầu vào
       lương công chức THẤP ···· cơ chế lương hiệu quả: phải kiếm
                                thêm để sống, bị bắt và đuổi việc
                                cũng mất ít → ⚠ cẩn trọng khi cắt
                                lương đồng loạt để giảm quỹ lương
       ═══════════════════════════════════════════════════════════
       ❷ ĐẶC LỢI KHÔNG DO CHÍNH SÁCH
       tài nguyên thiên nhiên ·· bán giá xa hơn chi phí khai thác
                                (Sachs–Warner 1995, tương quan chưa
                                đủ ý nghĩa thống kê)
       yếu tố xã hội ··········· nhiều sắc tộc → tham nhũng kém tổ
                                chức hơn (Shleifer–Vishny); quan hệ
                                gia đình mạnh → thiên vị họ hàng
                                (Tanzi 1994)
```

### Hệ quả của tham nhũng

```text
       ① ĐẦU TƯ VÀ TĂNG TRƯỞNG · tham nhũng như một loại THUẾ, lại
          phải giữ BÍ MẬT và BẤT ĐỊNH → giảm động cơ đầu tư
       ② PHÂN BỔ NHÂN TÀI · người giỏi chọn tìm đặc lợi thay vì
          làm việc sản xuất (Murphy–Shleifer–Vishny 1991)
       ③ VIỆN TRỢ KÉM HIỆU QUẢ · tiền bị chuyển hướng; nhà tài trợ
          ngày càng chú ý quản trị, có nơi cắt giảm viện trợ
       ④ MẤT THU THUẾ · trốn thuế, miễn thuế tuỳ tiện (chỉ là tham
          nhũng khi có tiền trả cho cán bộ thuế)
       ⑤ HỆ QUẢ NGÂN SÁCH VÀ TIỀN TỆ · vd cho vay chỉ định lãi thấp
          của ngân hàng nhà nước
       ⑥ HẠ TẦNG CHẤT LƯỢNG THẤP · cho dùng vật liệu rẻ → cầu, nhà
          sập
       ⑦ ★ CƠ CẤU CHI TIÊU CÔNG · chọn khoản chi DỄ THU HỐI LỘ VÀ
          GIỮ BÍ MẬT
       ┌─────────────────────────────┬─────────────────────────┐
       │ DỄ THU HỐI LỘ               │ KHÓ THU HỐI LỘ          │
       ├─────────────────────────────┼─────────────────────────┤
       │ dự án lớn, hàng chuyên biệt │ sách giáo khoa          │
       │ khó định giá                │ lương giáo viên         │
       │ hạ tầng quy mô lớn          │ lương bác sĩ, y tá      │
       │ vũ khí công nghệ cao, máy   │                         │
       │ bay quân sự (Hines 1995)    │                         │
       │ toà nhà bệnh viện, thiết bị │                         │
       │ y tế hiện đại               │                         │
       └─────────────────────────────┴─────────────────────────┘
       → hàng của doanh nghiệp trong thị trường độc quyền nhóm, nơi
         có đặc lợi
```

### Kết quả: đầu tư và tăng trưởng

```text
       ★ BẢNG 1a — ĐẦU TƯ / GDP, bình quân 1960–1985
       ┌──────────────────┬──────────┬──────────┬──────────┬──────────┐
       │                  │ (1) OLS  │ (2) 2SLS │ (3) OLS  │ (4) 2SLS │
       ├──────────────────┼──────────┼──────────┼──────────┼──────────┤
       │ chỉ số tham nhũng│★ 0,0187  │ 0,0320   │ 0,0095   │ 0,0281   │
       │                  │ (7,03)   │ (3,93)   │ (2,09)   │ (0,99)   │
       │ GDP/người 1960   │          │          │ −0,0062  │ −0,0213  │
       │ học trung học    │          │          │ 0,1749   │ 0,1241   │
       │   1960           │          │          │ (2,95)   │ (1,21)   │
       │ tăng dân số      │          │          │ −0,8226  │ −1,0160  │
       │ R²               │ 0,32     │   —      │ 0,44     │   —      │
       └──────────────────┴──────────┴──────────┴──────────┴──────────┘
       ═══════════════════════════════════════════════════════════
       ★ BẢNG 1b — TĂNG TRƯỞNG GDP/NGƯỜI, 1960–1985
       ┌──────────────────┬───────┬───────┬───────┬───────┬───────┐
       │                  │ (1)   │ (2)   │ (3)   │ (4)   │ (5)   │
       │                  │ OLS   │ 2SLS  │ OLS   │ 2SLS  │ OLS   │
       ├──────────────────┼───────┼───────┼───────┼───────┼───────┤
       │ chỉ số tham nhũng│0,0029 │0,0081 │0,0038 │0,0175 │0,0028 │
       │                  │(4,74) │(3,61) │(2,95) │(1,40) │(2,01) │
       │ đầu tư           │       │       │       │       │★0,1056│
       │                  │       │       │       │       │(3,09) │
       │ R²               │ 0,14  │  —    │ 0,31  │  —    │ 0,42  │
       └──────────────────┴───────┴───────┴───────┴───────┴───────┘
       ★★ ĐỌC CÁC BẢNG NÀY
       +1 độ lệch chuẩn (2,38) → đầu tư +4,4 điểm % GDP, tăng
         trưởng +0,7 điểm %/năm (cột 1)
       ví dụ trong bài: từ "6/10" lên "8/10" → đầu tư +gần 4 điểm %
       2SLS (công cụ: đa dạng dân tộc–ngôn ngữ) → hệ số LỚN HƠN
       ⚠ khi thêm biến kiểm soát và dùng công cụ, hệ số mất ý nghĩa
         thống kê (cột 4)
       ★ thêm ĐẦU TƯ vào hồi quy tăng trưởng → hệ số tham nhũng
         giảm khoảng HAI PHẦN BA (còn 0,0028, vừa đủ ý nghĩa 5%)
         → phần lớn tác động đi QUA ĐẦU TƯ, phần còn lại có thể trực
           tiếp
```

### Biến công cụ

```text
       ① CHỈ SỐ ĐA DẠNG DÂN TỘC–NGÔN NGỮ (ELF), năm 1960
          ELF = 1 − Σ (nᵢ/N)²
          = xác suất hai người chọn ngẫu nhiên KHÔNG cùng nhóm
          nguồn: Atlas Narodov Mira (Liên Xô, 1964)
          tương quan với chỉ số tham nhũng 0,39
       ② TỪNG LÀ THUỘC ĐỊA (sau 1776) · tương quan 0,46
       ③ ĐỘC LẬP SAU 1945 · tương quan 0,38
       ─────────────────────────────────────────────────────────
       điều kiện hợp lệ: các biến này chỉ ảnh hưởng tăng trưởng,
       đầu tư, chi tiêu QUA tham nhũng
       ⚠ tác giả tự nhận: nói đúng ra chúng là công cụ cho HIỆU QUẢ
         THỂ CHẾ nói chung, dùng chủ yếu để xử lý tính chủ quan của
         chỉ số
```

### Mô hình chuẩn so sánh (Phụ lục)

```text
       KHÁI QUÁT HOÁ BARRO (1990) với N loại chi tiêu công
       y = A k^(1−α) Π gᵢ^αᵢ,   Σ αᵢ = α
       chính phủ tối đa hoá (1 − ψ)·U_dân + ψ·U_quan chức
         ψ = mức "tham nhũng"; θ = độ bất ổn chính trị
       ═══════════════════════════════════════════════════════════
       KẾT QUẢ
       ψ hoặc θ cao hơn → thuế + hối lộ τ CAO hơn → đầu tư tư nhân
         và tăng trưởng THẤP hơn ✔ khớp Bảng 1
       ★★ NHƯNG tỷ lệ mỗi loại chi / GDP KHÔNG phụ thuộc tham nhũng:
          φⱼ/φₖ = αⱼ/αₖ
       → nếu hối lộ chỉ như một loại THUẾ TỶ LỆ trên thu nhập, cơ
         cấu chi tiêu sẽ không đổi
       → ★ nếu dữ liệu cho thấy cơ cấu chi tiêu CÓ liên quan tham
         nhũng, thì hối lộ phải dễ thu ở MỘT SỐ khoản chi hơn các
         khoản khác
```

### Kết quả: cơ cấu chi tiêu công

```text
       ★ BẢNG 2 — SỐ LIỆU BARRO, bình quân 1970–1985, % GDP
       ┌──────────────────────────┬──────────────┬──────────────┐
       │                          │ CHỈ THAM     │ + GDP/người  │
       │                          │ NHŨNG        │ 1980         │
       ├──────────────────────────┼──────────────┼──────────────┤
       │ ★ giáo dục               │ 0,0023 (3,97)│★0,0020 (2,20)│
       │ tiêu dùng chính phủ      │−0,0047(−1,70)│ 0,0052 (1,46)│
       │ quốc phòng               │ 0,0004 (0,28)│ 0,0009 (0,25)│
       │ chuyển giao              │ 0,0208 (7,22)│ 0,0001 (0,03)│
       │ an sinh, phúc lợi        │ 0,0156 (7,94)│ 0,0041 (1,64)│
       └──────────────────────────┴──────────────┴──────────────┘
       → +1 độ lệch chuẩn → chi GIÁO DỤC +khoảng 0,5% GDP
       ★ chuyển giao và phúc lợi MẤT ý nghĩa khi kiểm soát thu nhập
         (luật Wagner: nước giàu chi nhiều hơn so với GDP)
       → GIÁO DỤC là khoản DUY NHẤT còn ý nghĩa ở mức 95%
       ═══════════════════════════════════════════════════════════
       ★ BẢNG 3 — SỐ LIỆU GFS năm 1985 (có kiểm soát GDP/người)
       tổng chi ··········· 0,0043 (0,36) · KHÔNG liên quan
       chi thường xuyên ··· 0,0124 (1,34)
       chi đầu tư ········· −0,0064 (−1,61) · tham nhũng hơn →
                            chi đầu tư nhiều hơn, chỉ vừa sát 90%
                            → giả thuyết "con voi trắng" được ủng hộ
                            yếu
       ★ giáo dục ········· 0,0030 (2,29)
       ★ y tế ············· 0,0027 (2,34)
       trường học 0,0028 (1,60) · đại học 0,0008 (2,45)
       quốc phòng, giao thông: KHÔNG có ý nghĩa
       ═══════════════════════════════════════════════════════════
       BẢNG 4 — ĐẦU TƯ CÔNG (Easterly–Rebelo, ~40 nước đang phát
       triển): hầu như KHÔNG có quan hệ nào có ý nghĩa
       → gợi ý: tham nhũng có thể GIỮ mức đầu tư công (nhưng không
         giữ chất lượng) trong khi đầu tư tư nhân giảm
       → hối lộ khó thu từ lương giáo viên nhưng DỄ thu từ xây
         trường
```

### Kiểm tra độ vững cho giáo dục

```text
       ★ BẢNG 5
       ┌────────────────────────────────┬──────────┬─────────────┐
       │ đặc tả                         │ hệ số    │ t           │
       ├────────────────────────────────┼──────────┼─────────────┤
       │ GD/GDP + tiêu dùng CP/GDP      │ 0,0027   │ 5,48        │
       │   + GDP/người                  │ 0,0014   │ 1,62 (vừa)  │
       │ GD/tiêu dùng CP                │ 0,0256   │ 5,40        │
       │   + GDP/người                  │ 0,0056   │ ⚠ 1,09      │
       │ GD/GDP, công cụ ELF            │ 0,0011   │ ⚠ 0,74      │
       │ GD/GDP, ELF + thuộc địa        │ 0,0015   │ ⚠ 1,36      │
       │ GD/tiêu dùng CP, ELF           │ ★ 0,0318 │ 3,04        │
       │ GD/tiêu dùng CP, ELF + thuộc địa│★ 0,0331 │ 3,95        │
       └────────────────────────────────┴──────────┴─────────────┘
       → dùng công cụ: hệ số với GD/GDP GIẢM MỘT NỬA; hệ số với
         tỷ trọng trong tiêu dùng chính phủ TĂNG
       → bằng chứng GỢI Ý chứ KHÔNG kết luận được rằng tham nhũng
         GÂY RA chi giáo dục thấp
```

### Chiều nhân quả có quan trọng cho chính sách?

```text
       KHẢ NĂNG A: cơ cấu chi xấu → TẠO cơ hội tham nhũng
         → buộc cải thiện cơ cấu chi SẼ giảm tham nhũng
       KHẢ NĂNG B: tham nhũng → CHỌN cơ cấu chi xấu
         ⚠ chính phủ tham nhũng sẽ LÁCH: thay dự án hữu ích bằng dự
           án béo bở NGAY TRONG cùng một hạng mục, vẫn báo cáo "tỷ
           trọng chi giáo dục đã tăng"
       ★ KẾT LUẬN: khuyến khích cải thiện cơ cấu chi có thể vẫn hữu
         ích với CẢ HAI chiều nhân quả — NHƯNG chỉ khi cơ cấu chi
         được quy định đủ chi tiết để khó thay thế BÊN TRONG hạng
         mục
```

## Ba câu hỏi bài viết trả lời

1. Những nguyên nhân và hệ quả nào của tham nhũng có thể kiểm định bằng hồi quy xuyên quốc gia, và các nghiên cứu gần đây tìm thấy gì?
2. Tham nhũng làm giảm đầu tư và tăng trưởng tới mức nào khi dùng mẫu lớn hơn?
3. Tham nhũng có làm thay đổi cơ cấu chi tiêu công không, nhất là chi cho giáo dục?

## Khái niệm cần biết

**Tham nhũng (corruption).** Việc công chức dùng quyền lực công để thu lợi riêng, điển hình là nhận hối lộ để cấp giấy phép, bỏ qua vi phạm hoặc chọn nhà thầu. Ví dụ trong bài: hối lộ để được cấp bằng lái xe (tham nhũng vặt) và hối lộ khi mua máy bay chiến đấu đắt tiền (tham nhũng cấp cao). Bài coi tham nhũng như một loại thuế đặc biệt độc hại, vì nó phải giữ bí mật và người nộp không chắc trả rồi có được việc hay không.

**Đặc lợi và tìm kiếm đặc lợi (rents / rent seeking).** Đặc lợi là phần lợi ích vượt quá mức mà cạnh tranh bình thường mang lại, sinh ra từ một quy định, một giấy phép hay một nguồn tài nguyên khan hiếm. Tìm kiếm đặc lợi là bỏ công sức, kể cả hối lộ, để giành phần lợi ích đó thay vì sản xuất ra của cải mới. Ví dụ minh hoạ: nếu hạn ngạch nhập khẩu làm một mặt hàng bán trong nước cao hơn giá thế giới 30%, thì giấy phép nhập khẩu lô hàng 1 triệu USD có giá trị khoảng 300.000 USD, và người ta sẵn sàng hối lộ một phần số đó để có giấy phép. Bài coi đặc lợi là gốc rễ của tham nhũng.

**Chỉ số tham nhũng.** Điểm số do công ty xếp hạng rủi ro tư nhân chấm cho từng nước, dựa trên bảng hỏi gửi chuyên gia, trên thang 0 (tham nhũng nhất) tới 10 (ít tham nhũng nhất). Ví dụ trong bài: chỉ số dùng là bình quân của hai nguồn ICRG và BI, có giá trị trung bình 5,85 và độ lệch chuẩn 2,38 trên 106 nước. Đây là biến giải thích trung tâm của mọi hồi quy trong bài, nên mọi kết luận đều phụ thuộc vào độ tin cậy của nó.

**Độ lệch chuẩn (standard deviation).** Thước đo mức phân tán của một biến quanh giá trị trung bình; nếu phân phối gần với phân phối chuẩn thì khoảng hai phần ba số nước nằm trong phạm vi một độ lệch chuẩn quanh trung bình. Ví dụ: với trung bình 5,85 và độ lệch chuẩn 2,38, "cải thiện một độ lệch chuẩn" nghĩa là chỉ số tăng khoảng 2,38 điểm, chẳng hạn từ 5,85 lên 8,23. Bài dùng đơn vị này để quy hệ số hồi quy thành con số dễ hình dung.

**Hồi quy chéo, OLS và hệ số t.** Hồi quy chéo so sánh nhiều nước tại cùng một thời điểm hoặc trên số bình quân dài hạn. OLS (bình phương nhỏ nhất thông thường) là cách ước lượng đơn giản nhất. Hệ số t là hệ số chia cho sai số chuẩn của nó; theo quy ước, |t| lớn hơn khoảng 2 nghĩa là có ý nghĩa thống kê ở mức 5%. Ví dụ trong bài: hệ số tham nhũng với đầu tư là 0,0187 với t = 7,03, rất chắc chắn; nhưng ở một cột khác là 0,0281 với t = 0,99, không có ý nghĩa. Biết đọc t là điều kiện để hiểu bài chắc chắn tới đâu.

**Nội sinh và biến công cụ (endogeneity / instrumental variables, 2SLS).** Nội sinh là khi biến giải thích có thể chịu tác động ngược của biến kết quả: ví dụ chuyên gia thấy một nước tăng trưởng nhanh thì có xu hướng chấm nước đó "ít tham nhũng". Biến công cụ là một biến khác có liên quan tới tham nhũng nhưng chỉ ảnh hưởng tới tăng trưởng qua kênh tham nhũng; phương pháp bình phương nhỏ nhất hai giai đoạn (2SLS) dùng biến đó để tách phần biến thiên "sạch" của tham nhũng. Ví dụ trong bài: chỉ số đa dạng dân tộc–ngôn ngữ có tương quan 0,39 với chỉ số tham nhũng. Bài dùng cách này để kiểm tra chiều nhân quả, và chính tác giả thừa nhận điều kiện của nó khó thoả mãn.

**Chỉ số đa dạng dân tộc–ngôn ngữ (ELF).** Xác suất để hai người chọn ngẫu nhiên trong một nước không thuộc cùng một nhóm dân tộc–ngôn ngữ, tính bằng 1 trừ tổng bình phương tỷ trọng các nhóm. Ví dụ minh hoạ: một nước có hai nhóm, mỗi nhóm 50% dân số, có ELF = 1 − (0,5² + 0,5²) = 0,5; một nước chỉ có một nhóm có ELF = 0. Đây là biến công cụ chính của bài.

**Cơ cấu chi tiêu công và luật Wagner.** Cơ cấu chi tiêu công là tỷ trọng của từng khoản chi (giáo dục, y tế, quốc phòng, chuyển giao, đầu tư) so với GDP hoặc tổng chi. Luật Wagner là quan sát rằng khi thu nhập tăng, chi tiêu công so với GDP cũng tăng, nhất là chi phúc lợi. Ví dụ trong bài: chi chuyển giao và phúc lợi tương quan mạnh với chỉ số tham nhũng, nhưng mất ý nghĩa khi kiểm soát GDP đầu người, vì nước ít tham nhũng thường cũng là nước giàu. Phân biệt hai hiệu ứng này là điều kiện để thấy vì sao chỉ giáo dục còn lại là kết quả đáng tin.

## Nội dung chi tiết

### 1. Mở đầu

Nguyên nhân và hệ quả của tham nhũng đã được nghiên cứu từ lâu, ít nhất từ các công trình lý thuyết về tìm kiếm đặc lợi. Nhưng nghiên cứu thực nghiệm còn hạn chế, vì hiệu quả thể chế đã khó định lượng mà tham nhũng còn khó đo hơn: bản chất của nó là che giấu. Bài có hai phần: phần đầu điểm lại những nguyên nhân và hệ quả có thể kiểm định bằng hồi quy xuyên quốc gia; phần sau mở rộng nghiên cứu Mauro (1995) với mẫu lớn hơn và xét thêm tác động lên cơ cấu chi tiêu công.

**Cách đo tham nhũng.** Vì không có số liệu trực tiếp, bài dùng chỉ số của các công ty xếp hạng rủi ro tư nhân. Các công ty này bán đánh giá cho công ty đa quốc gia và ngân hàng quốc tế, dựa trên bảng hỏi chuẩn gửi chuyên gia tư vấn ở nhiều nước. Hai nguồn được dùng:

| Nguồn | Giai đoạn | Số nước |
|---|---|---|
| ICRG (International Country Risk Guide của Political Risk Services, do IRIS tổng hợp) | bình quân 1982–1995 | hơn 100 |
| Business International (BI, nay thuộc Economist Intelligence Unit) | bình quân 1980–1983 | 67 |

Cả hai đều chấm trên thang 0 (tham nhũng nhất) tới 10 (ít tham nhũng nhất). Hai chỉ số tương quan với nhau rất cao, r = 0,81, cho thấy các nguồn khác nhau có đồng thuận về nước nào tham nhũng hơn. Việc khách hàng sẵn sàng trả giá cao cho các đánh giá này cũng là bằng chứng gián tiếp rằng thông tin có ích. Chỉ số dùng trong bài là **bình quân hai chỉ số** khi nước đó có cả hai, để giảm sai số đo lường. Kết quả cho 106 nước:

| Thống kê | Giá trị |
|---|---|
| Số nước | 106 |
| Trung bình | 5,85 |
| Độ lệch chuẩn | 2,38 |
| Thấp nhất | 0,59 |
| Cao nhất | 10 |

**Ba hạn chế của chỉ số.**

1. Chỉ số mang tính chủ quan. Chuyên gia có thể bị ảnh hưởng bởi chính kết quả kinh tế của nước họ đánh giá: thấy kinh tế tăng trưởng tốt thì chấm điểm tham nhũng nhẹ tay hơn. Đây là rủi ro nội sinh, nên phải rất thận trọng khi đọc tương quan như quan hệ nhân quả; biến công cụ là một cách xử lý.
2. Chỉ số không phân biệt tham nhũng cấp cao (ví dụ mua máy bay chiến đấu đắt tiền để ăn hối lộ lớn) với tham nhũng cấp thấp (ví dụ hối lộ để lấy bằng lái xe).
3. Chỉ số không phân biệt tham nhũng có tổ chức với tham nhũng không có tổ chức. Theo Shleifer và Vishny (1993), loại không có tổ chức tệ hơn, vì người đưa hối lộ không biết phải đưa bao nhiêu, đưa cho ai, và đưa rồi có được việc hay không.

### 2. Nguyên nhân

Theo lý thuyết tìm kiếm đặc lợi (Krueger 1974, Tullock 1967, Bhagwati 1982, Rose-Ackerman 1978), nguồn gốc cuối cùng của tham nhũng là sự tồn tại của **đặc lợi**, thường do chính phủ tạo ra. Khi quy định dày đặc và công chức có nhiều quyền tuỳ ý, người dân và doanh nghiệp sẵn sàng hối lộ để được hưởng phần đặc lợi đó. Tanzi (1994) nhấn mạnh vấn đề càng tệ khi quy định thiếu đơn giản và minh bạch. Bài chia nguồn đặc lợi thành hai nhóm.

**Nhóm 1: đặc lợi do chính sách tạo ra (sửa được bằng chính sách).**

| Nguồn | Cơ chế |
|---|---|
| Hạn chế thương mại | Trong chế độ hạn ngạch, giấy phép nhập khẩu rất có giá trị, nên người ta hối lộ để có nó. Ades và Di Tella (1994) thấy nền kinh tế mở hơn với thương mại đi kèm tham nhũng thấp hơn |
| Trợ cấp, ưu đãi thuế | Chính sách công nghiệp tạo ra đặc lợi cho doanh nghiệp được chọn. Ades và Di Tella (1995) thấy tỷ lệ trợ cấp cho ngành chế tạo trên GDP liên quan tới chỉ số tham nhũng, và cho rằng khi đánh giá chính sách công nghiệp cần tính cả tham nhũng như một sản phẩm phụ ngoài ý muốn |
| Kiểm soát giá | Doanh nghiệp hối lộ để được mua đầu vào ở giá quy định, thấp hơn giá thị trường |
| Đa tỷ giá, phân bổ ngoại tệ | Doanh nghiệp hối lộ cán bộ ngân hàng nhà nước để được cấp ngoại tệ theo tỷ giá ưu đãi để nhập đầu vào. Quy mô đặc lợi này có thể đo bằng chênh lệch tỷ giá trên thị trường song song |
| Lương công chức thấp | Khi lương thấp so với khu vực tư hay so với GDP bình quân đầu người, công chức phải kiếm thêm để sống, và nếu bị bắt, đuổi việc thì cũng mất ít. Đây là cơ chế lương hiệu quả đảo chiều |

Hệ quả chính sách của điểm cuối: khi phải giảm quỹ lương khu vực công, cần cân nhắc kỹ giữa cắt lương đồng loạt và cắt biên chế. Cắt lương đồng loạt có thể làm tham nhũng vặt tăng lên.

**Nhóm 2: đặc lợi không do chính sách.**

- **Tài nguyên thiên nhiên**: dầu mỏ, khoáng sản bán được với giá cao hơn nhiều so với chi phí khai thác, tạo ra khoản đặc lợi lớn để tranh giành. Sachs và Warner (1995) có đề cập, nhưng tương quan giữa tài nguyên và tham nhũng chưa đủ ý nghĩa thống kê.
- **Yếu tố xã hội**: theo Shleifer và Vishny, ở nước có nhiều sắc tộc, tham nhũng có thể kém tổ chức hơn (nhiều nhóm cùng đòi hối lộ độc lập nhau). Theo Tanzi (1994), quan hệ gia đình mạnh dẫn tới thiên vị họ hàng.

Nhà hoạch định chính sách không xoá được các nguồn này, nhưng cần cảnh giác và tính đến chúng khi đánh giá tác động của chính sách.

### 3. Hệ quả

Bài liệt kê bảy hệ quả của tham nhũng:

1. **Đầu tư và tăng trưởng.** Nhà đầu tư biết một phần lợi nhuận có thể bị quan chức chiếm, và hối lộ thường phải trả trước để được cấp phép. Tham nhũng vì vậy giống một loại thuế, nhưng độc hại hơn thuế thường vì phải giữ bí mật và kèm bất định, nên làm giảm động cơ đầu tư. Mauro (1995) và Keefer và Knack cho thấy tham nhũng làm giảm đầu tư và tăng trưởng. Theo Keefer và Knack, biến thể chế còn có tác động trực tiếp lên tăng trưởng ngoài kênh đầu tư, có thể qua việc phân bổ nguồn lực giữa các ngành hoặc giữa khu vực chính thức và phi chính thức.
2. **Phân bổ nhân tài.** Khi tìm kiếm đặc lợi sinh lời hơn sản xuất, người giỏi chọn làm việc đó thay vì làm việc sản xuất (Murphy, Shleifer và Vishny 1991).
3. **Viện trợ kém hiệu quả.** Tiền viện trợ bị chuyển hướng. Các nhà tài trợ ngày càng chú ý tới quản trị, và có nơi đã cắt giảm viện trợ vì tham nhũng.
4. **Mất thu thuế.** Qua trốn thuế và miễn thuế tuỳ tiện. Bài lưu ý trốn thuế chỉ là tham nhũng khi có tiền trả cho cán bộ thuế.
5. **Hệ quả ngân sách và tiền tệ.** Ví dụ ngân hàng nhà nước cho vay chỉ định với lãi suất thấp cho người có quan hệ.
6. **Hạ tầng chất lượng thấp.** Cán bộ giám sát nhận hối lộ để cho nhà thầu dùng vật liệu rẻ, dẫn tới cầu sập, nhà sập.
7. **Cơ cấu chi tiêu công.** Quan chức tham nhũng có động cơ chọn những khoản chi dễ thu hối lộ và dễ giữ bí mật.

Hệ quả thứ bảy là trọng tâm thực nghiệm của bài. Nghiên cứu trước về chủ đề này rất ít. Một ví dụ là Rauch: làn sóng cải cách chính quyền đô thị thời Tiến bộ ở Mỹ làm tăng tỷ trọng chi cho đường và cống, qua đó thúc đẩy việc làm ngành chế tạo.

Bài phân loại các khoản chi theo mức độ dễ thu hối lộ:

| Dễ thu hối lộ | Khó thu hối lộ |
|---|---|
| Dự án lớn, hàng chuyên biệt khó định giá | Sách giáo khoa |
| Hạ tầng quy mô lớn | Lương giáo viên |
| Vũ khí công nghệ cao, máy bay quân sự (Hines 1995) | Lương bác sĩ, y tá |
| Toà nhà bệnh viện, thiết bị y tế hiện đại | |

Điểm chung của nhóm dễ thu hối lộ là hàng hoá do doanh nghiệp trong thị trường độc quyền nhóm cung cấp, nơi có đặc lợi để chia. Ngược lại, lương giáo viên được trả theo thang bảng công khai, sách giáo khoa có giá dễ so sánh, nên khó "rút" ra khoản hối lộ đáng kể.

### 4. Dữ liệu

**Chỉ số tham nhũng** là bình quân của ICRG và BI khi có cả hai nguồn. Trong mẫu Barro có 106 nước có chỉ số.

**Ba nguồn dữ liệu chi tiêu công:**

| Bộ dữ liệu | Phạm vi | Đặc điểm |
|---|---|---|
| Barro | bình quân 1970–1985 | các khoản chi lớn tính theo % GDP |
| Devarajan và cộng sự, từ GFS (Thống kê Tài chính Chính phủ của IMF) | quan sát năm 1985, bổ sung thêm nước công nghiệp | có chi tiết giáo dục và y tế cho khoảng 60 nước |
| Easterly và Rebelo | khoảng 40 nước đang phát triển | đầu tư công hợp nhất cả khu vực chính phủ lẫn doanh nghiệp nhà nước |

**Phương pháp.** Bài dùng hồi quy chéo trên số bình quân dài hạn, vì hiệu quả thể chế thay đổi rất chậm nên dùng dữ liệu theo năm cũng không thêm được nhiều thông tin. Mauro (1993) đã cho thấy quan hệ giữa đầu tư và tham nhũng vẫn có ý nghĩa trong bảng dữ liệu có hiệu ứng cố định nước.

### 5. Đầu tư và tăng trưởng

**Đầu tư.** Biến phụ thuộc là tỷ lệ đầu tư trên GDP, bình quân 1960–1985. Con số trong ngoặc là hệ số t.

| Biến | (1) OLS | (2) 2SLS | (3) OLS | (4) 2SLS |
|---|---|---|---|---|
| Chỉ số tham nhũng | 0,0187 (7,03) | 0,0320 (3,93) | 0,0095 (2,09) | 0,0281 (0,99) |
| GDP đầu người năm 1960 | | | −0,0062 | −0,0213 |
| Tỷ lệ nhập học trung học năm 1960 | | | 0,1749 (2,95) | 0,1241 (1,21) |
| Tăng dân số | | | −0,8226 | −1,0160 |
| R² | 0,32 | — | 0,44 | — |

**Tăng trưởng.** Biến phụ thuộc là tăng trưởng GDP bình quân đầu người 1960–1985.

| Biến | (1) OLS | (2) 2SLS | (3) OLS | (4) 2SLS | (5) OLS |
|---|---|---|---|---|---|
| Chỉ số tham nhũng | 0,0029 (4,74) | 0,0081 (3,61) | 0,0038 (2,95) | 0,0175 (1,40) | 0,0028 (2,01) |
| Đầu tư | | | | | 0,1056 (3,09) |
| R² | 0,14 | — | 0,31 | — | 0,42 |

**Đọc các bảng.**

- *Hồi quy đơn biến (cột 1)* cho quan hệ có ý nghĩa với cả đầu tư lẫn tăng trưởng. Cải thiện chỉ số tham nhũng một độ lệch chuẩn (2,38 điểm) đi kèm đầu tư tăng khoảng 4,4 điểm phần trăm GDP (0,0187 × 2,38) và tăng trưởng tăng khoảng 0,7 điểm phần trăm mỗi năm (0,0029 × 2,38). Ví dụ của chính bài: một nước nâng chỉ số từ 6/10 lên 8/10 thì đầu tư tăng gần 4 điểm phần trăm GDP.
- *Dùng biến công cụ (cột 2)*, với công cụ là chỉ số đa dạng dân tộc–ngôn ngữ, hệ số còn lớn hơn: 0,0320 với đầu tư và 0,0081 với tăng trưởng.
- *Thêm biến kiểm soát chuẩn (cột 3)* theo Levine và Renelt, gồm thu nhập ban đầu, tỷ lệ nhập học trung học ban đầu và tăng dân số, quan hệ vẫn có ý nghĩa nhưng hệ số với đầu tư nhỏ đi một nửa (0,0095).
- *Vừa có biến kiểm soát vừa dùng công cụ (cột 4)*, hệ số mất ý nghĩa thống kê (t = 0,99 với đầu tư, 1,40 với tăng trưởng).
- *Thêm đầu tư vào hồi quy tăng trưởng (cột 5)*: hệ số tham nhũng giảm khoảng hai phần ba so với các đặc tả không có đầu tư, còn 0,0028, vừa đủ ý nghĩa ở mức 5%. Nghĩa là phần lớn tác động của tham nhũng lên tăng trưởng đi **qua kênh đầu tư**, phần còn lại có thể là tác động trực tiếp.

**Biến công cụ.** Bài dùng ba biến công cụ:

| Biến công cụ | Tương quan với chỉ số tham nhũng |
|---|---|
| Chỉ số đa dạng dân tộc–ngôn ngữ (ELF) năm 1960 | 0,39 |
| Từng là thuộc địa (sau 1776) | 0,46 |
| Độc lập sau 1945 | 0,38 |

ELF được tính bằng 1 − Σ(nᵢ/N)², trong đó nᵢ là số người thuộc nhóm i và N là tổng dân số; nó bằng xác suất hai người chọn ngẫu nhiên không cùng một nhóm. Số liệu lấy từ Atlas Narodov Mira, do Liên Xô xuất bản năm 1964. Điều kiện để các biến này hợp lệ là chúng chỉ ảnh hưởng tới tăng trưởng, đầu tư và chi tiêu **qua** tham nhũng. Tác giả tự thừa nhận rằng nói đúng ra chúng là công cụ cho hiệu quả thể chế nói chung, và được dùng chủ yếu để xử lý tính chủ quan của chỉ số.

### 6. Cơ cấu chi tiêu công

**Mô hình chuẩn so sánh.** Bài khái quát hoá mô hình tăng trưởng của Barro (1990) với N loại chi tiêu công. Sản lượng là y = A·k^(1−α)·Π gᵢ^αᵢ, trong đó k là vốn tư nhân, gᵢ là từng loại chi tiêu công, và tổng các αᵢ bằng α. Chính phủ tối đa hoá một trung bình có trọng số giữa lợi ích của dân và lợi ích của quan chức: (1 − ψ)·U_dân + ψ·U_quan chức, trong đó ψ là mức "tham nhũng" và θ là độ bất ổn chính trị.

Mô hình cho hai kết quả:

- ψ hoặc θ cao hơn thì tổng thuế cộng hối lộ τ cao hơn, nên đầu tư tư nhân và tăng trưởng thấp hơn. Điều này khớp với kết quả hồi quy đầu tư và tăng trưởng ở mục 5.
- Nhưng tỷ lệ mỗi loại chi trên GDP **không phụ thuộc** mức tham nhũng: tỷ lệ giữa hai khoản chi bất kỳ là φⱼ/φₖ = αⱼ/αₖ, chỉ do công nghệ sản xuất quyết định.

Ý nghĩa: nếu hối lộ chỉ hoạt động như một khoản thuế tỷ lệ trên thu nhập, cơ cấu chi tiêu sẽ không đổi theo tham nhũng. Vì vậy, nếu dữ liệu cho thấy cơ cấu chi **có** liên quan tới tham nhũng, thì phải hiểu là hối lộ dễ thu ở một số khoản chi hơn các khoản khác. Mô hình đóng vai trò giả thuyết đối chứng.

**Lưu ý về dữ liệu.** Dữ liệu chi tiêu nhiễu: khó bảo đảm các nước phân loại khoản chi giống nhau, và mỗi hạng mục đều chứa cả dự án hữu ích lẫn vô ích. Dù vậy bài vẫn tìm thấy quan hệ có ý nghĩa với chi giáo dục.

**Kết quả với số liệu Barro** (bình quân 1970–1985, % GDP; hệ số dương nghĩa là nước ít tham nhũng hơn chi nhiều hơn; t trong ngoặc):

| Khoản chi | Chỉ có chỉ số tham nhũng | Thêm GDP đầu người năm 1980 |
|---|---|---|
| Giáo dục | 0,0023 (3,97) | 0,0020 (2,20) |
| Tiêu dùng chính phủ | −0,0047 (−1,70) | 0,0052 (1,46) |
| Quốc phòng | 0,0004 (0,28) | 0,0009 (0,25) |
| Chuyển giao | 0,0208 (7,22) | 0,0001 (0,03) |
| An sinh, phúc lợi | 0,0156 (7,94) | 0,0041 (1,64) |

Cải thiện chỉ số một độ lệch chuẩn đi kèm chi giáo dục tăng khoảng 0,5% GDP. Chi chuyển giao và phúc lợi có quan hệ rất mạnh khi đứng một mình, nhưng mất ý nghĩa khi kiểm soát thu nhập: đó là luật Wagner, nước giàu chi phúc lợi nhiều hơn so với GDP, và nước giàu cũng thường ít tham nhũng. Giáo dục là khoản **duy nhất** còn có ý nghĩa ở mức 95% sau khi kiểm soát thu nhập.

**Kết quả với số liệu GFS năm 1985** (có kiểm soát GDP đầu người):

| Khoản chi | Hệ số (t) | Nhận xét |
|---|---|---|
| Tổng chi | 0,0043 (0,36) | không liên quan |
| Chi thường xuyên | 0,0124 (1,34) | không có ý nghĩa |
| Chi đầu tư | −0,0064 (−1,61) | nước tham nhũng hơn chi đầu tư nhiều hơn, chỉ vừa sát mức 90% |
| Giáo dục | 0,0030 (2,29) | có ý nghĩa |
| Y tế | 0,0027 (2,34) | có ý nghĩa |
| Trường học (tiểu mục giáo dục) | 0,0028 (1,60) | mờ nhạt |
| Đại học (tiểu mục giáo dục) | 0,0008 (2,45) | có ý nghĩa nhưng nhỏ |
| Quốc phòng, giao thông | — | không có ý nghĩa |

Với số liệu chi tiết hơn này, chi y tế cũng có quan hệ có ý nghĩa: nước tham nhũng hơn chi ít hơn cho y tế. Quan hệ với các tiểu mục của giáo dục và y tế thì mờ nhạt hơn. Giả thuyết phổ biến rằng tham nhũng đẩy chính phủ sang chi đầu tư lớn cho các dự án "con voi trắng" (công trình phô trương mà vô ích) chỉ được ủng hộ yếu.

**Kết quả với đầu tư công** (số liệu Easterly–Rebelo, khoảng 40 nước đang phát triển): hầu như không có quan hệ nào có ý nghĩa. Có thể do mẫu nhỏ. Cũng có thể vì tham nhũng giữ nguyên **mức** đầu tư công (nhưng không giữ chất lượng) trong khi đầu tư tư nhân giảm, và vì hối lộ khó thu từ lương giáo viên nhưng dễ thu từ việc xây trường, tức là tham nhũng có thể làm thay đổi cơ cấu bên trong một hạng mục mà không làm thay đổi tổng.

**Kiểm tra độ vững cho giáo dục.**

| Đặc tả | Hệ số | t |
|---|---|---|
| Giáo dục/GDP, kiểm soát tiêu dùng chính phủ/GDP | 0,0027 | 5,48 |
| Như trên, thêm GDP đầu người | 0,0014 | 1,62 (vừa sát ngưỡng) |
| Giáo dục/tiêu dùng chính phủ | 0,0256 | 5,40 |
| Như trên, thêm GDP đầu người | 0,0056 | 1,09 (không có ý nghĩa) |
| Giáo dục/GDP, công cụ ELF | 0,0011 | 0,74 (không có ý nghĩa) |
| Giáo dục/GDP, công cụ ELF và thuộc địa | 0,0015 | 1,36 (không có ý nghĩa) |
| Giáo dục/tiêu dùng chính phủ, công cụ ELF | 0,0318 | 3,04 |
| Giáo dục/tiêu dùng chính phủ, công cụ ELF và thuộc địa | 0,0331 | 3,95 |

Khi dùng biến công cụ, kết quả lẫn lộn: hệ số với tỷ lệ giáo dục trên GDP giảm khoảng một nửa và mất ý nghĩa, còn hệ số với tỷ trọng giáo dục trong tiêu dùng chính phủ lại tăng và có ý nghĩa. Bài kết luận rằng bằng chứng **gợi ý** chứ không kết luận được rằng tham nhũng là nguyên nhân làm chi giáo dục thấp.

### 7. Chiều nhân quả và chính sách

Chiều nhân quả giữa tham nhũng và cơ cấu chi thường mờ: không rõ quy định sinh ra tham nhũng, hay quan chức tham nhũng tạo ra quy định để thu lợi. Nhiều khả năng nhân quả đi theo cả hai chiều. Bài xét hai khả năng:

| Khả năng | Chiều nhân quả | Hệ quả chính sách |
|---|---|---|
| A | Cơ cấu chi xấu tạo ra cơ hội tham nhũng | Buộc cải thiện cơ cấu chi sẽ làm giảm tham nhũng |
| B | Tham nhũng khiến chính phủ chọn cơ cấu chi xấu | Chính phủ tham nhũng sẽ lách: thay dự án hữu ích bằng dự án béo bở ngay trong cùng một hạng mục, mà vẫn báo cáo "tỷ trọng chi giáo dục đã tăng" |

Kết luận của bài: tương quan quan sát được có thể đủ để cân nhắc khuyến khích chính phủ chi nhiều hơn cho các hạng mục ít bị tham nhũng, và cách làm đó có thể hữu ích với cả hai chiều nhân quả. Nhưng nó chỉ hiệu quả khi cơ cấu chi được quy định đủ chi tiết để không thể thay thế bên trong hạng mục. Ví dụ minh hoạ: nếu chỉ tiêu chỉ là "tăng chi giáo dục", chính phủ có thể đáp ứng bằng cách xây thêm trường thay vì trả thêm lương giáo viên, và mục tiêu thực sự không đạt được.

### 8. Kết luận

Tham nhũng có tác động tiêu cực đáng kể lên tăng trưởng kinh tế. Kênh chính là làm giảm đầu tư tư nhân: cải thiện chỉ số tham nhũng một độ lệch chuẩn đi kèm đầu tư cao hơn hơn 4 điểm phần trăm GDP và tăng trưởng GDP bình quân đầu người cao hơn hơn 0,5 điểm phần trăm mỗi năm (theo hệ số cột 1 là khoảng 0,7 điểm). Một kênh khác có thể là cơ cấu chi tiêu công kém hơn.

Quan hệ âm giữa tham nhũng và chi cho giáo dục, khoảng 0,5% GDP cho mỗi độ lệch chuẩn, là điều đáng lo ngại, vì tài liệu trước đã cho thấy trình độ giáo dục là một yếu tố quan trọng quyết định tăng trưởng.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Corruption index | Chỉ số tham nhũng, thang 0 tới 10, cao hơn là ít tham nhũng hơn |
| Rent seeking | Tìm kiếm đặc lợi |
| Rents | Đặc lợi, lợi ích vượt mức cạnh tranh do quy định hoặc tài nguyên tạo ra |
| Business International (BI) | Công ty xếp hạng rủi ro, nay thuộc Economist Intelligence Unit |
| International Country Risk Guide (ICRG) | Chỉ số rủi ro quốc gia của Political Risk Services |
| High-level, low-level corruption | Tham nhũng cấp cao và tham nhũng vặt |
| Well-organized corruption | Tham nhũng có tổ chức, biết rõ đưa bao nhiêu và cho ai |
| Efficiency wage | Lương hiệu quả, lương cao để giảm động cơ vi phạm |
| Multiple exchange rate practices | Chế độ đa tỷ giá |
| Parallel market premium | Chênh lệch tỷ giá thị trường song song |
| Ethnolinguistic fractionalization (ELF) | Chỉ số đa dạng dân tộc và ngôn ngữ |
| Instrumental variables, 2SLS | Biến công cụ, bình phương nhỏ nhất hai giai đoạn |
| Endogeneity | Tính nội sinh |
| Wagner's law | Luật Wagner, chi tiêu công so với GDP tăng khi thu nhập tăng |
| White elephant | Con voi trắng, dự án phô trương mà vô ích |
| Composition of government expenditure | Cơ cấu chi tiêu chính phủ |
| Government Finance Statistics (GFS) | Thống kê Tài chính Chính phủ của IMF |
| Fungibility of aid | Tính thay thế được của viện trợ |
| Allocation of talent | Phân bổ nhân tài |

## Câu nói đáng nhớ

> "Corruption may be interpreted to act as a tax—though of a particularly pernicious nature, given the need for secrecy and the uncertainty that come with it."

> "A priori, one might expect that it is easier to collect substantial bribes on large infrastructure projects or high-technology defense equipment than on textbooks and teachers' salaries."

> "While bribes are difficult to levy on teachers' salaries, they are easier to levy on the construction of school buildings."

## Đánh giá và phát hiện đáng chú ý

### Mô hình lý thuyết ở phụ lục không dùng để giải thích, mà dùng làm giả thuyết không

Chi tiết dễ bị bỏ qua nhất của bài lại là chi tiết khéo nhất. Bản khái quát hoá mô hình Barro cho ra kết quả φⱼ/φₖ = αⱼ/αₖ — tức tỷ trọng mỗi khoản chi trong GDP **không phụ thuộc vào mức tham nhũng**. Thoạt nhìn đây là một kết quả thất bại: mô hình không giải thích được điều bài muốn chứng minh.

Nhưng Mauro dùng nó theo hướng ngược lại. Nếu hối lộ chỉ hoạt động như một khoản thuế tỷ lệ trên thu nhập, cơ cấu chi tiêu phải trung lập với tham nhũng. Vậy nên **mọi tương quan quan sát được giữa tham nhũng và cơ cấu chi đều là bằng chứng bác bỏ giả định "hối lộ là thuế tỷ lệ"**, và buộc ta phải kết luận rằng hối lộ dễ thu ở một số khoản chi hơn các khoản khác. Mô hình không đóng vai trò mô tả thế giới; nó đóng vai trò định nghĩa thế giới sẽ trông thế nào nếu giả thuyết của bài sai.

Đây là cách dùng lý thuyết mà các bài thực nghiệm về tham nhũng sau này hiếm khi lặp lại, và nó biến một tương quan chéo tầm thường thành một phép kiểm định có nội dung.

### Kết quả âm về "con voi trắng" quan trọng hơn kết quả dương về giáo dục

Giả thuyết phổ biến — tham nhũng đẩy chính phủ sang các dự án đầu tư hoành tráng — chỉ được ủng hộ **rất yếu**: hệ số chi đầu tư là −0,0064 với t = −1,61, vừa sát mức 90%. Và trong bộ dữ liệu Easterly–Rebelo về đầu tư công ở khoảng 40 nước đang phát triển, **hầu như không có quan hệ nào có ý nghĩa**.

Đây là một kết quả âm mà bài chỉ dành cho vài dòng, nhưng hệ quả thực tiễn của nó sắc hơn kết luận chính. Nó có nghĩa là **không thể phát hiện tham nhũng bằng cách nhìn vào tỷ lệ đầu tư công trên GDP**. Một nước tham nhũng nặng và một nước sạch có thể có cùng con số đầu tư công. Cái khác nhau nằm ở chỗ khác: chất lượng công trình, giá thành trên mỗi đơn vị năng lực, và tuổi thọ tài sản — tức là những thứ không nằm trong bất kỳ bảng thống kê tài khoá nào.

Suy luận mà bài gợi ra nhưng không nói thẳng: tham nhũng có thể **giữ nguyên mức đầu tư công trong khi bóp nghẹt đầu tư tư nhân**. Nếu đúng vậy, tỷ trọng đầu tư công trong tổng đầu tư sẽ tăng lên ở nước tham nhũng — và con số đó sẽ bị đọc nhầm thành "nhà nước đang tích cực dẫn dắt".

### Biến công cụ càng làm hệ số to ra thì càng đáng ngờ, chứ không phải càng yên tâm

Bài trình bày việc 2SLS cho hệ số lớn hơn OLS (0,0320 so với 0,0187 với đầu tư; 0,0081 so với 0,0029 với tăng trưởng) như một dấu hiệu củng cố, hàm ý sai số đo lường đã làm OLS bị suy giảm. Cách đọc này chỉ đúng nếu điều kiện loại trừ được thoả mãn.

Ba công cụ là chỉ số đa dạng dân tộc–ngôn ngữ, từng là thuộc địa, và độc lập sau 1945. Điều kiện loại trừ đòi hỏi chúng ảnh hưởng tới đầu tư và tăng trưởng **chỉ qua tham nhũng**. Điều này gần như chắc chắn sai: đa dạng sắc tộc tác động tới xung đột nội bộ, khả năng cung cấp hàng hoá công, mức độ tin cậy xã hội và độ ổn định chính trị — tất cả đều là kênh độc lập tới tăng trưởng. Chính Mauro thừa nhận chúng thực ra là công cụ cho **hiệu quả thể chế nói chung**.

Nhưng nếu đã thừa nhận như vậy thì hệ số 2SLS lớn hơn không phải bằng chứng rằng tác động của tham nhũng lớn hơn; nó là bằng chứng rằng **tác động của cả gói thể chế lớn hơn tác động của riêng tham nhũng** — điều không ai nghi ngờ và cũng không cho ta biết gì mới. Cột đáng tin nhất trong toàn bộ Bảng 1a là cột vừa có biến kiểm soát vừa dùng công cụ, và chính cột đó cho hệ số 0,0281 với t = 0,99: **mất ý nghĩa thống kê hoàn toàn**. Bài dẫn dắt người đọc bằng cột đơn giản nhất.

### Khuyến nghị về lương công chức là một lời phản đối kín đáo với chính sách điều chỉnh đương thời

Giữa một bài kỹ thuật, có một đoạn rất ít kỹ thuật: cảnh báo rằng lương công chức thấp so với khu vực tư khuyến khích tham nhũng vặt qua cơ chế lương hiệu quả, và vì vậy **cần cân nhắc kỹ khi chọn giữa cắt lương đồng loạt và cắt biên chế** để giảm quỹ lương.

Năm 1996, cắt quỹ lương là một cấu phần tiêu chuẩn của các chương trình điều chỉnh tài khoá mà chính IMF thiết kế, và cách dễ nhất về mặt chính trị luôn là cắt lương thực tế bằng cách không điều chỉnh theo lạm phát, chứ không phải sa thải. Bài nói rằng lựa chọn dễ đó có thể tự phá huỷ chính mục tiêu của chương trình: quỹ lương giảm hôm nay, thất thoát qua hối lộ và mất thu thuế tăng ngày mai.

Đây là một nhận xét có hệ quả phân phối rõ ràng mà bài không phát biểu: cắt lương đồng loạt dồn chi phí lên công chức trung thực (họ mất thu nhập thật) trong khi gần như không chạm tới công chức ở các vị trí có đặc lợi (họ bù lại bằng hối lộ). Nói cách khác, một biện pháp được trình bày là trung lập lại có tác dụng **chọn lọc ngược**: nó đẩy người liêm chính ra khỏi khu vực công và giữ lại người không liêm chính.

### Lỗ hổng "thay thế bên trong hạng mục" vô hiệu hoá gần hết khuyến nghị chính sách

Phần bàn về chiều nhân quả kết thúc bằng một điều kiện mà nếu đọc kỹ sẽ thấy nó gần như không thể thoả mãn. Bài lập luận rằng khuyến khích chính phủ chi nhiều hơn cho các hạng mục khó ăn hối lộ có thể hữu ích **bất kể nhân quả đi chiều nào** — nhưng chỉ khi cơ cấu chi được quy định đủ chi tiết để không thể thay thế ngay bên trong hạng mục.

Chính bài đã cung cấp ví dụ phản bác: hối lộ khó thu từ lương giáo viên nhưng dễ thu từ **xây trường**. Cả hai đều là "chi cho giáo dục". Một chính phủ bị ép nâng tỷ trọng chi giáo dục lên 20% ngân sách có thể làm đúng chỉ tiêu bằng cách xây thêm trường, mua thiết bị thí nghiệm nhập khẩu, và không tăng một đồng lương giáo viên nào. Chỉ tiêu được hoàn thành, và bản chất không đổi.

Điều này có nghĩa là toàn bộ dòng khuyến nghị "cơ cấu lại chi tiêu công để giảm tham nhũng" chỉ có ý nghĩa ở mức độ chi tiết mà không một khuôn khổ ngân sách trung hạn nào theo được. Ràng buộc phải đặt ở cấp **dòng ngân sách**, không phải cấp ngành — và ở cấp đó, quyền tự chủ của cơ quan chi tiêu bị triệt tiêu, kéo theo một cái giá hiệu quả riêng.

### Với Việt Nam, và mức độ tin cậy cần giữ khi trích dẫn

Ba hệ quả cụ thể.

**Thứ nhất**, các chỉ tiêu kiểu "chi giáo dục đạt 20% tổng chi ngân sách" hay "chi khoa học công nghệ đạt 2%" — vốn phổ biến trong các nghị quyết của Việt Nam — đúng là loại chỉ tiêu mà bài này chỉ ra là dễ bị lách nhất. Con số cần theo dõi song song là **cơ cấu bên trong**: tỷ trọng chi thường xuyên cho con người so với chi xây dựng cơ bản trong cùng một ngành.

**Thứ hai**, kết quả âm về đầu tư công có ý nghĩa trực tiếp với tranh luận về giải ngân đầu tư công. Tỷ lệ giải ngân cao không phải là bằng chứng về chất lượng quản trị, và tỷ lệ giải ngân thấp cũng không phải bằng chứng về sự trong sạch. Bằng chứng nằm ở suất đầu tư trên mỗi kilômét đường, mỗi megawatt công suất, và ở tuổi thọ công trình — đúng những chỉ số mà khuôn khổ đánh giá hiệu quả đầu tư công của IMF nhấn mạnh.

**Thứ ba**, danh sách nguyên nhân của bài đặt độ mở thương mại, kiểm soát giá và đa tỷ giá ở vị trí trung tâm. Ở đây có một liên hệ thú vị với các tài liệu về kiểm soát vốn và hạn chế thanh toán thương mại trong repo: mỗi công cụ hành chính can thiệp vào giá hoặc vào quyền tiếp cận ngoại tệ đều tạo ra một khoản đặc lợi, và khoản đặc lợi đó có giá thị trường. Cái giá ấy hiếm khi được tính vào khi đánh giá lợi ích của công cụ.

Cần nói thẳng về mức độ tin cậy. Đây là hồi quy chéo trên số bình quân dài hạn, với chỉ số tham nhũng do chuyên gia tư vấn chấm điểm — mà chính các chuyên gia đó có thể đã bị ảnh hưởng bởi kết quả kinh tế của nước họ đánh giá. Bài thừa nhận rủi ro này ngay ở trang đầu, thừa nhận công cụ chỉ là công cụ cho thể chế nói chung, và kết luận về giáo dục bằng đúng chữ "gợi ý chứ không kết luận được".

Ba mươi năm sau, con số "+1 độ lệch chuẩn về chỉ số tham nhũng đi kèm đầu tư tăng hơn 4 điểm phần trăm GDP" vẫn được trích như một ước lượng nhân quả trong các báo cáo chính sách. Độ chắc chắn đã tăng lên trên đường lan truyền, trong khi bằng chứng thì không. Khi dùng lại con số này, nên trích kèm đúng cột đã sinh ra nó và đúng những dè dặt mà chính tác giả đã viết.

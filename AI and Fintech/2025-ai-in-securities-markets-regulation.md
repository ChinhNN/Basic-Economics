# Regulatory Considerations Regarding Accelerated Use of AI in Securities Markets — Những cân nhắc về quản lý trước việc tăng tốc sử dụng AI trên thị trường chứng khoán

**Nguồn:** IMF Technical Notes and Manuals TNM/2025/16.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** AI đang thấm vào thị trường vốn qua năm mảng nghiệp vụ, và bài chỉ ra rằng ở các thị trường mới nổi tốc độ tăng trưởng của robo-advisory và neo-broking còn nhanh hơn ở nước phát triển, dù xuất phát điểm thấp hơn nhiều. Rủi ro lớn nhất không phải một mô hình AI bị hỏng, mà là rất nhiều tổ chức cùng dùng một số ít mô hình và nguồn dữ liệu giống nhau, khiến thị trường đồng bộ hoá hành vi và khuếch đại biến động. Bài đưa ra bảy khuyến nghị cho cơ quan quản lý, trong đó nhấn mạnh rằng công cụ giám sát phải được nâng cấp bằng chính công nghệ mà nó đang giám sát.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Số hiệu tài liệu lấy từ trang bìa sau.

## Sơ đồ

### Năm mảng nghiệp vụ AI đang xâm nhập

```text
       ┌──────────────────────────────────────────────────────────┐
       │ ① QUẢN LÝ TÀI SẢN                                        │
       │   khảo sát Mercer 2024 với 150 nhà quản lý tài sản:      │
       │   phân tích dữ liệu lớn ······················· 40%      │
       │   tạo ý tưởng đầu tư ·························· 32%      │
       │   xác định dữ liệu và tín hiệu ················ 31%      │
       │   ★ KHÔNG DÙNG AI ····························· 29%      │
       │   ra quyết định đầu tư ························ 25%      │
       │   hiệu quả theo BCG: tiếp thị 30–40% · CNTT 15–30%       │
       │   vận hành 20–25% · bán hàng 15–25% · rủi ro 15–25%      │
       ├──────────────────────────────────────────────────────────┤
       │ ② GIAO DỊCH BÁN BUÔN — giao dịch thuật toán              │
       │   Hoa Kỳ ~70% · Châu Âu ~50% · Châu Á ~43% · Mỹ Latin    │
       │   ~30% (12/2024) · Ấn Độ NSE/BSE ~45–58%                 │
       │   Thái Lan SET ~44,8% (10/2025)                          │
       ├──────────────────────────────────────────────────────────┤
       │ ③ TƯ VẤN ĐẦU TƯ TỰ ĐỘNG (robo-advisory)                  │
       │   tài sản quản lý dự báo VƯỢT 2 NGHÌN TỶ ĐÔ tới 2028     │
       │   tăng trưởng 2017–23: Hoa Kỳ 418%/năm ·                 │
       │   ★ THỊ TRƯỜNG MỚI NỔI 172%/năm > PHÁT TRIỂN 140%/năm    │
       ├──────────────────────────────────────────────────────────┤
       │ ④ MÔI GIỚI THẾ HỆ MỚI (neo-broking)                      │
       │   ★ MỚI NỔI 223%/năm (2017–22) > PHÁT TRIỂN 197%/năm     │
       │   ứng dụng di động, hoa hồng bằng 0, trò chơi hoá        │
       ├──────────────────────────────────────────────────────────┤
       │ ⑤ GỌI VỐN CỘNG ĐỒNG — Anh và Hoa Kỳ chiếm hơn một nửa    │
       │   khối lượng; mới nổi tăng nhanh hơn phát triển          │
       └──────────────────────────────────────────────────────────┘
       DỮ LIỆU ĐẦU VÀO: 35% chuyên gia đầu tư dùng công cụ kiểu
       ChatGPT · 64% dùng DỮ LIỆU THAY THẾ · 48% dùng NGUỒN MỞ
```

### Phân loại rủi ro

```text
       BA TẦNG NGUỒN RỦI RO
       ┌───────────────┬───────────────┬──────────────────────────┐
       │ HẠ TẦNG       │ DỮ LIỆU       │ MÔ HÌNH                  │
       │ · phụ thuộc   │ · chất lượng  │ · ĐỒNG BỘ HOÁ hành vi    │
       │   bên thứ ba  │   kém         │ · TẬP TRUNG vào vài mô   │
       │ · rủi ro an   │ · ĐỘC QUYỀN   │   hình giống nhau        │
       │   ninh mạng   │   NHÓM của    │ · thiếu bền vững và      │
       │               │   nhà cung    │   KHÔNG GIẢI THÍCH ĐƯỢC  │
       │               │   cấp dữ liệu │ · sai phạm khi thực thi  │
       │               │ · dữ liệu phi │   lệnh                   │
       │               │   cấu trúc bị │ · thực hành không công   │
       │               │   THAO TÚNG   │   bằng với nhà đầu tư    │
       └───────┬───────┴───────┬───────┴──────────┬───────────────┘
               └───────────────┼──────────────────┘
                               ▼
       HẬU QUẢ TRÊN THỊ TRƯỜNG
       ▸ HÀNH VI BẦY ĐÀN — nhiều bên cùng mua, cùng bán một lúc
       ▸ TÍNH THUẬN CHU KỲ — khuếch đại xu hướng sẵn có
       ▸ BIẾN ĐỘNG TĂNG, thanh khoản bốc hơi đúng lúc cần nhất
       ▸ BÓP MÉO THỊ TRƯỜNG — giá không còn phản ánh thông tin
       ▸ BẤT ĐỐI XỨNG THÔNG TIN giữa tổ chức lớn và nhà đầu tư nhỏ
       ▸ SAI PHẠM VỚI NHÀ ĐẦU TƯ CÁ NHÂN
       ═══════════════════════════════════════════════════════════
       ★ LUẬN ĐIỂM TRUNG TÂM: rủi ro hệ thống KHÔNG đến từ một mô
         hình hỏng, mà từ việc RẤT NHIỀU tổ chức dùng CÙNG một số
         ít mô hình và CÙNG nguồn dữ liệu → khi tín hiệu đổi
         chiều, tất cả cùng quay đầu một lúc
```

### Thông đồng thuật toán: ranh giới mới của pháp luật

```text
       HỘP 1 — AI CÓ THỂ THÔNG ĐỒNG MÀ KHÔNG AI RA LỆNH
       ┌──────────────────────────────────────────────────────────┐
       │ CÓ CHỦ Ý        │ KHÔNG CHỦ Ý                            │
       │ con người lập   │ thuật toán TỰ HỌC ra rằng giữ giá cao  │
       │ trình cho thuật │ thì có lợi hơn cạnh tranh — KHÔNG có   │
       │ toán phối hợp   │ thoả thuận, KHÔNG có liên lạc, KHÔNG   │
       │ giá             │ có ý định của con người                │
       │ → luật cạnh     │ → ⚠ LUẬT CẠNH TRANH HIỆN HÀNH THƯỜNG   │
       │   tranh xử lý   │   ĐÒI HỎI BẰNG CHỨNG VỀ THOẢ THUẬN     │
       │   được          │   → rơi vào KHOẢNG TRỐNG PHÁP LÝ       │
       └──────────────────────────────────────────────────────────┘
       CƠ SỞ: Calvano và cộng sự (2020) chứng minh trong thí
       nghiệm rằng thuật toán học tăng cường tự học được cách
       duy trì giá siêu cạnh tranh
       TIỀN LỆ THỰC: vụ Trod Ltd / GB Eye — Cơ quan Cạnh tranh và
       Thị trường Anh xử lý năm 2018, dùng phần mềm định giá để
       phối hợp giá trên sàn thương mại điện tử
```

### Bốn bài học từ các sự cố đã xảy ra

```text
       ① KNIGHT CAPITAL (2012)
          phần mềm giao dịch lỗi khi triển khai
          ★ MẤT 440 TRIỆU ĐÔ TRONG 45 PHÚT
          bài học: RỦI RO VẬN HÀNH của tốc độ tự động
                              │
       ② SỤP ĐỔ CHỚP NHOÁNG 2010
          chỉ số bốc hơi rồi hồi phục trong vài phút
          Navinder Sarao bị truy tố vì SPOOFING — đặt lệnh giả
          để dẫn dụ thuật toán khác
          bài học: THAO TÚNG có thể NHẮM VÀO chính thuật toán
                              │
       ③ QUỸ RENAISSANCE (3/2020)
          mô hình định lượng THẤT BẠI khi chế độ thị trường đổi
          đột ngột vì đại dịch
          bài học: mô hình học từ QUÁ KHỨ không xử lý được
          CÚ SỐC CHƯA TỪNG CÓ TIỀN LỆ
                              │
       ④ "AI WASHING" — SEC xử phạt Delphia và Global Predictions
          vì KHAI KHỐNG về năng lực AI của mình
          bài học: rủi ro không chỉ từ AI thật, mà từ LỜI HỨA AI
```

### Bảy khuyến nghị cho cơ quan quản lý

```text
       ❶ NĂNG LỰC VÀ BỘ KỸ NĂNG GIÁM SÁT
         tuyển và giữ người hiểu học máy, không chỉ hiểu luật
                              │
       ❷ CÔNG CỤ GIÁM SÁT DỰA TRÊN CÔNG NGHỆ (SupTech)
         ★ dùng chính AI để giám sát AI
         tham chiếu: FINRA giám sát 100% hoạt động giao dịch
                              │
       ❸ GIÁM SÁT THỊ TRƯỜNG THEO NGUYÊN TẮC TƯƠNG XỨNG
         Bảng 2 đưa bộ chỉ tiêu tham chiếu để theo dõi mức độ
         tập trung, đồng bộ hoá và bất thường
                              │
       ❹ MINH BẠCH VÀ CÔNG BỐ THÔNG TIN
         nhà đầu tư phải biết AI đang được dùng ở khâu nào
                              │
       ❺ GIÁM SÁT MẠNG XÃ HỘI
         nội dung do AI tạo ra và người ảnh hưởng tài chính
                              │
       ❻ HỢP TÁC XUYÊN BIÊN GIỚI
         ⚠ đặc biệt cấp thiết ở thị trường mới nổi:
         Mexico — ngân hàng nước ngoài nắm HƠN 80% tài sản ngân
                  hàng; giao dịch OTC với đối tác nước ngoài GẤP
                  ĐÔI giao dịch trong nước
         Nam Phi — nước ngoài chiếm 30% cổ phiếu JSE, 25% trái
                  phiếu chính phủ
         Thái Lan — bán khống và giao dịch theo chương trình của
                  nước ngoài lên tới 15% giao dịch ngày
                              │
       ❼ RỦI RO TẬP TRUNG VÀ HẠ TẦNG
         vài nhà cung cấp đám mây và dữ liệu trở thành ĐIỂM HỎNG
         DUY NHẤT của cả thị trường
```

### Bức tranh quản lý hiện tại

```text
       KHẢO SÁT 31 KHU VỰC PHÁP LÝ / 33 CƠ QUAN
       ── Ở CẤP QUỐC GIA ──────────────────────────────────────
       luật về tội phạm mạng ························ 97%
       quản trị dữ liệu ····························· 94%
       chiến lược quốc gia về AI ···················· 84%
       ★ ĐẠO LUẬT RIÊNG VỀ AI ······················· 52% ◂ mới
                                                        quá nửa
       ── Ở CẤP CƠ QUAN QUẢN LÝ CHỨNG KHOÁN ───────────────────
       hướng dẫn về tư vấn đầu tư tự động ··········· 88%
       hướng dẫn về giao dịch thuật toán ············ 79%
       hoạt động tiếp cận, phổ biến ················· 67%
       văn bản làm rõ cách áp dụng quy định sẵn có ··· 61%
       quy định dựa trên nguyên tắc riêng cho AI ······ 9%
       ★ HÀNH ĐỘNG CƯỠNG CHẾ ·························· 3% ◂ gần
                                                          như
                                                          chưa có
       ── VÍ DỤ CỤ THỂ ────────────────────────────────────────
       EU · Đạo luật AI, Điều 14 về GIÁM SÁT CỦA CON NGƯỜI
       Hong Kong · SFC ra thông tư tháng 11/2024
       Trung Quốc · quy tắc AI tạo sinh hiệu lực 15/8/2023, cơ
                    chế ĐĂNG KÝ THUẬT TOÁN
       Ấn Độ · SEBI thông tư 2019; đề xuất 2024 quy TRÁCH NHIỆM
               HOÀN TOÀN cho tổ chức trung gian dùng AI
       Thái Lan · SEC nghiên cứu giao dịch tần suất cao và quản
                  lý người ảnh hưởng tài chính
```

## Ba câu hỏi bài viết trả lời

1. AI đang được dùng ở đâu trên thị trường vốn, và vì sao thị trường mới nổi lại tăng tốc nhanh hơn thị trường phát triển?
2. Rủi ro thực sự nằm ở đâu, nếu không phải ở việc một mô hình đơn lẻ bị hỏng?
3. Cơ quan quản lý cần làm gì khi tốc độ của thị trường đã vượt xa tốc độ của công cụ giám sát?

## Dàn ý chi tiết

### 1. Năm mảng nghiệp vụ

- Bài chọn năm mảng làm khung quan sát: quản lý tài sản, giao dịch bán buôn, tư vấn đầu tư tự động, môi giới thế hệ mới, và gọi vốn cộng đồng. Bảng 1 ánh xạ từng mảng với các ứng dụng AI cụ thể.
- Trong quản lý tài sản, khảo sát Mercer năm 2024 với một trăm năm mươi nhà quản lý cho thấy bức tranh chưa đồng đều: bốn mươi phần trăm dùng AI để phân tích dữ liệu lớn, nhưng hai mươi chín phần trăm vẫn hoàn toàn không dùng AI, và chỉ hai mươi lăm phần trăm đưa AI vào chính khâu ra quyết định đầu tư.
- Ước tính của BCG về mức tăng hiệu quả cho thấy lợi ích tập trung ở khâu hỗ trợ chứ không phải khâu đầu tư: tiếp thị ba mươi tới bốn mươi phần trăm, công nghệ thông tin mười lăm tới ba mươi, vận hành hai mươi tới hai mươi lăm, còn rủi ro và tuân thủ mười lăm tới hai mươi lăm.
- Giao dịch thuật toán đã chiếm tỷ trọng rất lớn ở thị trường phát triển và đang lan sang thị trường mới nổi, với Ấn Độ ở khoảng bốn mươi lăm tới năm mươi tám phần trăm và Thái Lan khoảng bốn mươi bốn phẩy tám phần trăm tính tới tháng 10/2025.
- Điểm gây chú ý nhất là tốc độ tăng trưởng ở thị trường mới nổi. Tư vấn đầu tư tự động tăng một trăm bảy mươi hai phần trăm mỗi năm ở nhóm mới nổi so với một trăm bốn mươi phần trăm ở nhóm phát triển ngoài Hoa Kỳ. Môi giới thế hệ mới tăng hai trăm hai mươi ba phần trăm mỗi năm ở nhóm mới nổi so với một trăm chín mươi bảy phần trăm ở nhóm phát triển.
- Về dữ liệu đầu vào, ba mươi lăm phần trăm chuyên gia đầu tư dùng công cụ kiểu ChatGPT, sáu mươi bốn phần trăm dùng dữ liệu thay thế và bốn mươi tám phần trăm dùng nguồn mở. Điều này quan trọng vì nó là tiền đề cho rủi ro đồng bộ hoá ở phần sau.

### 2. Cấu trúc rủi ro

- Bài phân rủi ro theo ba tầng nguồn: hạ tầng, dữ liệu, và mô hình, rồi cho thấy cả ba đều đổ vào cùng một nhóm hậu quả trên thị trường.
- Ở tầng dữ liệu, ngoài vấn đề chất lượng còn có hai rủi ro ít được nói tới: sự độc quyền nhóm của một số ít nhà cung cấp dữ liệu, và khả năng dữ liệu phi cấu trúc bị thao túng có chủ đích để đánh lừa mô hình.
- Ở tầng mô hình, rủi ro nghiêm trọng nhất là sự đồng bộ hoá và tập trung. Nếu nhiều tổ chức cùng dùng một số ít mô hình nền và cùng nguồn dữ liệu, họ sẽ phản ứng giống nhau trước cùng một tín hiệu.
- Hậu quả gồm hành vi bầy đàn, tính thuận chu kỳ, biến động tăng, bóp méo thị trường, bất đối xứng thông tin, và sai phạm với nhà đầu tư cá nhân. Điểm cần nhấn mạnh là những hậu quả này mang tính hệ thống chứ không phải cục bộ.

### 3. Thông đồng thuật toán

- Hộp 1 phân biệt hai trường hợp khác nhau về bản chất pháp lý. Thông đồng có chủ ý, khi con người lập trình cho thuật toán phối hợp giá, thì luật cạnh tranh hiện hành xử lý được, và vụ Trod Ltd cùng GB Eye do Cơ quan Cạnh tranh và Thị trường Anh xử lý năm 2018 là tiền lệ.
- Trường hợp khó là phối hợp không chủ ý. Calvano và cộng sự năm 2020 chứng minh trong môi trường thí nghiệm rằng thuật toán học tăng cường có thể tự học ra cách duy trì giá siêu cạnh tranh mà không cần bất kỳ thoả thuận hay liên lạc nào giữa các bên.
- Đây là khoảng trống pháp lý thực sự, vì luật cạnh tranh ở hầu hết nơi đòi hỏi bằng chứng về một thoả thuận. Khi không có thoả thuận, không có liên lạc và không có ý định của con người, cơ quan quản lý gần như không có công cụ.

### 4. Các sự cố đã xảy ra

- Knight Capital năm 2012 mất bốn trăm bốn mươi triệu đô la trong bốn mươi lăm phút vì lỗi triển khai phần mềm giao dịch, minh hoạ rủi ro vận hành của tốc độ tự động.
- Sụp đổ chớp nhoáng năm 2010 và vụ truy tố Navinder Sarao cho thấy thao túng có thể nhắm vào chính các thuật toán, bằng cách đặt rồi huỷ lệnh để dẫn dụ chúng.
- Quỹ Renaissance Institutional Equities thất bại vào tháng 3/2020 khi chế độ thị trường thay đổi đột ngột vì đại dịch, minh hoạ rằng mô hình học từ dữ liệu quá khứ không xử lý được cú sốc chưa từng có tiền lệ.
- Các vụ xử phạt của SEC với Delphia và Global Predictions về hành vi khai khống năng lực AI cho thấy một dạng rủi ro khác hẳn: không phải AI gây hại, mà là lời hứa về AI được dùng để lừa nhà đầu tư.
- Ở thị trường mới nổi, bài nêu vụ SEBI xử lý Nimi Enterprises năm 2023, cùng các vụ FCA kiện Da Vinci Invest năm 2015 và Paul Axel Walter năm 2017 ở Anh.

### 5. Bức tranh quản lý

- Khảo sát ba mươi mốt khu vực pháp lý với ba mươi ba cơ quan cho thấy nền tảng pháp lý chung khá vững: chín mươi bảy phần trăm có luật về tội phạm mạng, chín mươi bốn phần trăm có khung quản trị dữ liệu, tám mươi bốn phần trăm có chiến lược quốc gia về AI.
- Nhưng chỉ năm mươi hai phần trăm có đạo luật riêng về AI, và ở cấp cơ quan quản lý chứng khoán, hành động cưỡng chế liên quan tới AI mới ở mức ba phần trăm. Phần lớn hoạt động vẫn là tiếp cận, phổ biến và làm rõ cách áp dụng quy định sẵn có.
- Hướng dẫn cụ thể tập trung vào hai mảng đã quen thuộc: tám mươi tám phần trăm có hướng dẫn về tư vấn đầu tư tự động và bảy mươi chín phần trăm về giao dịch thuật toán.
- Ở cấp tổ chức đặt chuẩn, bài dẫn các báo cáo của Hội đồng Ổn định Tài chính năm 2017, 2024 và 2025, cùng báo cáo IOSCO năm 2021 với sáu biện pháp đề xuất, tài liệu tham vấn năm 2025 và báo cáo về môi giới thế hệ mới.
- Ở cấp quốc gia, bài dẫn ESMA và Đạo luật AI của EU với Điều 14 về giám sát của con người, thông tư tháng 11/2024 của SFC Hong Kong, quy tắc AI tạo sinh của Trung Quốc có hiệu lực từ 15/8/2023 cùng cơ chế đăng ký thuật toán, và đề xuất năm 2024 của SEBI quy trách nhiệm hoàn toàn cho tổ chức trung gian sử dụng AI.

### 6. Bảy khuyến nghị

- Về năng lực giám sát, cơ quan quản lý cần bộ kỹ năng mới, không chỉ pháp lý mà cả kỹ thuật, và phải cạnh tranh về nhân sự với chính khu vực tư nhân mà họ giám sát.
- Về công cụ, bài lập luận rằng giám sát phải được nâng cấp bằng chính công nghệ đang được giám sát, dẫn ví dụ FINRA giám sát toàn bộ một trăm phần trăm hoạt động giao dịch.
- Về giám sát thị trường theo nguyên tắc tương xứng, Bảng 2 đưa một bộ chỉ tiêu tham chiếu để theo dõi mức độ tập trung, đồng bộ hoá và bất thường, cho phép cơ quan nhỏ tập trung nguồn lực vào nơi rủi ro cao nhất.
- Về minh bạch, yêu cầu công bố rằng AI đang được dùng ở khâu nào, để nhà đầu tư hiểu được bản chất dịch vụ mình mua.
- Về mạng xã hội, giám sát nội dung do AI tạo ra và hoạt động của người ảnh hưởng tài chính, vốn có thể tác động tới hành vi nhà đầu tư nhỏ lẻ ở quy mô lớn.
- Về hợp tác xuyên biên giới, bài đưa ra lập luận đặc biệt mạnh cho thị trường mới nổi bằng các số liệu về mức độ hiện diện của nhà đầu tư và tổ chức nước ngoài: ngân hàng nước ngoài nắm hơn tám mươi phần trăm tài sản ngân hàng ở Mexico, nhà đầu tư nước ngoài nắm ba mươi phần trăm cổ phiếu và hai mươi lăm phần trăm trái phiếu chính phủ ở Nam Phi, và hoạt động bán khống cùng giao dịch theo chương trình của nước ngoài chiếm tới mười lăm phần trăm giao dịch ngày ở Thái Lan. Bài cũng lưu ý bài học từ các nỗ lực hội nhập thị trường trước đây, như việc Liên kết Giao dịch ASEAN ngừng hoạt động năm 2017.
- Về rủi ro tập trung, vài nhà cung cấp đám mây và dữ liệu có thể trở thành điểm hỏng duy nhất cho cả thị trường, và đây là rủi ro không tổ chức đơn lẻ nào có thể tự xử lý.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Robo-advisory | Tư vấn đầu tư tự động bằng thuật toán, ít hoặc không có con người |
| Neo-broking | Môi giới thế hệ mới, ứng dụng di động, phí thấp hoặc bằng 0 |
| Algorithmic trading | Giao dịch thuật toán, lệnh do chương trình tự sinh và thực thi |
| High-frequency trading | Giao dịch tần suất cao, tốc độ mili-giây |
| Crowdfunding | Gọi vốn cộng đồng qua nền tảng |
| Alternative data | Dữ liệu thay thế, ngoài báo cáo tài chính truyền thống |
| Herd behavior | Hành vi bầy đàn, nhiều bên cùng hành động một lúc |
| Procyclicality | Tính thuận chu kỳ, khuếch đại xu hướng sẵn có |
| Synchronization | Đồng bộ hoá, các mô hình phản ứng giống nhau trước cùng tín hiệu |
| Model concentration | Tập trung mô hình, nhiều tổ chức dùng chung vài mô hình nền |
| Explainability | Khả năng giải thích được quyết định của mô hình |
| Robustness | Tính bền vững của mô hình trước dữ liệu ngoài phân bố huấn luyện |
| Algorithmic collusion | Thông đồng thuật toán, có hoặc không có chủ ý của con người |
| Reinforcement learning | Học tăng cường, thuật toán học qua thử và thưởng phạt |
| Spoofing | Đặt lệnh giả rồi huỷ để dẫn dụ thuật toán khác |
| Flash crash | Sụp đổ chớp nhoáng, giá lao dốc rồi hồi phục trong vài phút |
| AI washing | Khai khống năng lực AI để thu hút nhà đầu tư |
| Gamification | Trò chơi hoá giao diện để tăng tần suất giao dịch |
| SupTech | Công nghệ phục vụ hoạt động giám sát của cơ quan quản lý |
| Human oversight | Giám sát của con người, yêu cầu tại Điều 14 Đạo luật AI của EU |
| Third-party dependency | Phụ thuộc bên thứ ba về hạ tầng và dữ liệu |
| Single point of failure | Điểm hỏng duy nhất khiến cả hệ thống ngừng hoạt động |
| Proportionality | Nguyên tắc tương xứng, cường độ quản lý theo mức rủi ro |
| Finfluencer | Người ảnh hưởng tài chính trên mạng xã hội |
| IOSCO | Tổ chức Quốc tế các Uỷ ban Chứng khoán |
| FSB | Hội đồng Ổn định Tài chính |
| Uptick rule | Quy tắc chỉ cho bán khống khi giá vừa tăng, biện pháp của Thái Lan |

## Câu nói đáng nhớ

> "The risk is not that one model fails, but that many firms rely on the same few models and the same data."

> "Enforcement action related to AI stands at just 3 percent of surveyed authorities."

> "Supervisory tools must be upgraded using the very technology they are meant to supervise."

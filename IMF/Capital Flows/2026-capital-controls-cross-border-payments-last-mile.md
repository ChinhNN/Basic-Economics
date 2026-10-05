# Do Capital Controls Slow Cross-Border Payments in the Last Mile? — Kiểm soát vốn có làm chậm thanh toán xuyên biên giới ở chặng cuối không?

**Nguồn:** IMF Working Paper WP/2026/068.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 4, không có trang bìa và trang tác giả).
**Ý chính:** Nhóm G20 đặt mục tiêu hoàn tất 75% thanh toán xuyên biên giới trong vòng một giờ, nhưng năm năm sau chỉ 54,6% đạt được, và phần lớn độ trễ nằm ở chặng cuối sau khi tiền đã tới ngân hàng thụ hưởng. Bài ghép hai bộ dữ liệu vi mô mới — thời gian xử lý từng giao dịch trên mạng Swift và chỉ số hạn chế tài khoản tài chính xây từ AREAER — và tìm thấy rằng tăng một độ lệch chuẩn mức kiểm soát vốn đi kèm với thanh toán chậm thêm **bốn tới tám giờ**. Tác động tập trung ở các nền kinh tế mới nổi và đang phát triển, và rất khác nhau giữa các khu vực. Bài tự đặt giới hạn rõ ràng cho mình: đây là tương quan mạnh và vững, chưa phải quan hệ nhân quả, và chỉ số chỉ đếm số biện pháp chứ không đo cường độ hay hiệu quả thực thi.

> **Lưu ý:** bản PDF bắt đầu từ trang 4 (phần Giới thiệu), không có trang bìa và trang tác giả. Số hiệu tài liệu lấy từ trang bìa sau.

## Sơ đồ

### Vấn đề chặng cuối

```text
       MỤC TIÊU G20 (từ 2020): 75% THANH TOÁN XUYÊN BIÊN GIỚI
       HOÀN TẤT TRONG MỘT GIỜ
       ★ NĂM NĂM SAU (FSB 2025): chỉ 54,6% số thanh toán trên
         100.000 đô la (không tính loại ghi ngày giá trị tương
         lai) đạt được mục tiêu
                              │
                              ▼
       ĐỘ TRỄ NẰM Ở ĐÂU? — GIẢI PHẪU MỘT LỆNH CHUYỂN TIỀN
       người trả → NGÂN HÀNG GỬI → mạng Swift + ngân hàng trung
       gian → NGÂN HÀNG THỤ HƯỞNG → người nhận
       └─CHẶNG GỬI─┘ └──── CHẶNG BAY ────┘ └─★ CHẶNG THỤ HƯỞNG ─┘
                                             ĐÂY LÀ CHỖ TẮC
       (CPMI-BIS-Swift 2022; FSB 2023, 2024; Swift 2024)
                              │
                              ▼
       ★★ CHÊNH LỆCH KHU VỰC RẤT LỚN — tỷ lệ quyết toán trong
          một giờ ở chặng thụ hưởng, năm 2024
          Bắc Mỹ ······· 81,8%
          Châu Phi ····· 24,7%   ★ CHỈ BẰNG MỘT PHẦN BA
                              │
                              ▼
       CÁC NGHI CAN
       · giờ mở cửa của ngân hàng và hạ tầng thị trường, múi giờ
       · xử lý theo lô thay vì theo từng giao dịch
       · thủ tục chống rửa tiền và tài trợ khủng bố
       · ★ KIỂM SOÁT VỐN và quy trình tuân thủ đi kèm ← BÀI NÀY
                              │
                              ▼
       KIỂM SOÁT VỐN ĐƯỢC THỰC THI Ở ĐÂU TRONG CHUỖI?
       ngân hàng THỤ HƯỞNG phải kiểm tra SAU KHI tiền đã vào tài
       khoản của mình nhưng TRƯỚC KHI giải ngân cho người nhận:
       ① xác minh thông tin người thụ hưởng (loại hình, hoạt
          động, tính chính xác của mã số thuế)
       ② mục đích thanh toán (dạng mã hoặc dạng văn bản)
       ③ chứng từ chứng minh (hợp đồng, hoá đơn, vận đơn xuất khẩu)
       một số nơi còn yêu cầu: hạn mức số tiền, hạn chế loại tài
       khoản được nhận chuyển khoản nước ngoài, và BÁO CÁO MỌI
       GIAO DỊCH cho cơ quan quản lý địa phương
       ⚠ NHIỀU QUY TRÌNH TRONG SỐ NÀY KHÔNG DỄ TỰ ĐỘNG HOÁ
       → thời gian xử lý dao động từ VÀI PHÚT (hồ sơ đầy đủ,
         khách quen, giao dịch lặp lại) tới VÀI NGÀY (thiếu hoặc
         sai thông tin)
```

### Hai bộ dữ liệu mới

```text
       ┌──────────────────────────────────────────────────────────┐
       │ BỘ 1 — TỐC ĐỘ THANH TOÁN, TỪ DỮ LIỆU GIAO DỊCH SWIFT     │
       │ Swift kết nối HƠN 11.500 thành viên tại HƠN 220 nước     │
       │ và vùng lãnh thổ                                         │
       │ Vũ trụ dữ liệu: KHOẢNG 4 TỶ QUAN SÁT (2020–2022; thời    │
       │ hạn lưu trữ tối đa của Swift là bốn năm)                 │
       │ Đo bằng Mã Tham chiếu Giao dịch Đầu-cuối Duy nhất (UETR) │
       │ trong hệ thống Đổi mới Thanh toán Toàn cầu của Swift     │
       │ ═══ BỐN BỘ LỌC ═══                                       │
       │ ① LOẠI các nước bị Swift hạn chế truy cập 2020–2022      │
       │    (Afghanistan, Belarus, Iran, Myanmar, Nga, Somalia,   │
       │     Venezuela) → bảo đảm kết quả do KIỂM SOÁT VỐN chứ    │
       │    không phải do CẤM VẬN                                 │
       │ ② BỎ thanh toán trong nước — NHƯNG GIỮ giao dịch ngoại   │
       │    tệ giữa các ngân hàng trong nước, vì nhiều biện pháp  │
       │    kiểm soát vốn nhắm chính vào việc nắm giữ và chuyển   │
       │    ngoại tệ trong nước                                   │
       │ ③ CHỈ GIỮ lệnh chuyển tiền khách hàng đơn lẻ (mã điện    │
       │    MT103) — loại quyết toán liên ngân hàng, kho bạc,     │
       │    chứng khoán, tài trợ thương mại, quản lý tiền mặt     │
       │ ④ CHỈ GIỮ giao dịch có mã trạng thái ACCC (đã ghi có     │
       │    xác nhận) và LOẠI giao dịch ghi ngày giá trị tương    │
       │    lai — nếu tính vào sẽ THỔI PHỒNG tốc độ giao thực tế  │
       └──────────────────────────────────────────────────────────┘
       ┌──────────────────────────────────────────────────────────┐
       │ BỘ 2 — CHỈ SỐ HẠN CHẾ TÀI KHOẢN TÀI CHÍNH (FARI)         │
       │ Baba và cộng sự (2026), xây từ AREAER của IMF            │
       │ thang 0 tới 1 · 0 = ít hạn chế nhất · 29 thành phần cho  │
       │ chiều DÒNG VÀO                                           │
       │ ★ PHẠM VI RỘNG HƠN các chỉ số quen thuộc: ngoài đầu tư   │
       │   danh mục và đầu tư trực tiếp, còn gồm tài khoản ngoại  │
       │   tệ của người KHÔNG CƯ TRÚ trong nước, tài khoản của    │
       │   người CƯ TRÚ ở nước ngoài, và yêu cầu HỒI HƯƠNG cùng   │
       │   NỘP LẠI ngoại tệ                                       │
       │ ⚠ KHÔNG bao gồm hạn chế giao dịch vãng lai như nhập      │
       │   khẩu và giao dịch vô hình                              │
       │ Dùng chỉ số DÒNG VÀO vì nó khớp nhất với chặng thụ       │
       │ hưởng; tương quan với chỉ số tổng hợp là 0,9             │
       └──────────────────────────────────────────────────────────┘
       PHẠM VI CUỐI: 176 NƯỚC, 2020–2022, tần suất NĂM
```

### Thống kê mô tả và kết quả cơ sở

```text
       THỐNG KÊ MÔ TẢ (Bảng 1)
       ┌───────────────────────────┬───────┬───────┬──────┬──────┐
       │                           │ T.BÌNH│ T.VỊ  │ NHỎ  │ LỚN  │
       ├───────────────────────────┼───────┼───────┼──────┼──────┤
       │ ★ Thời gian chặng thụ     │ 30,72 │ 27,84 │ 2,50 │120,00│
       │   hưởng (giờ)             │       │       │      │      │
       │   độ lệch chuẩn 19,93     │       │       │      │      │
       │ ★ FARI dòng vào           │  0,29 │  0,21 │ 0,00 │ 0,83 │
       │   độ lệch chuẩn 0,22      │       │       │      │      │
       └───────────────────────────┴───────┴───────┴──────┴──────┘
       ★ MỘT ĐỘ LỆCH CHUẨN CỦA FARI = 0,22 ≈ 6–7 THÀNH PHẦN trong
         số 29 có kiểm soát vốn được áp dụng
       ⚠ PHẦN LỚN BIẾN THIÊN LÀ GIỮA CÁC NƯỚC, không phải trong
         nội bộ một nước theo thời gian — vì kiểm soát vốn là quy
         trình DI CHUYỂN CHẬM
       ═══════════════════════════════════════════════════════════
       BẢNG 2 — HỒI QUY CƠ SỞ (biến phụ thuộc: thời gian trung
       bình chặng thụ hưởng, tính bằng giờ)
       ┌──────────────────────────┬──────────────┬──────────────┐
       │                          │ (1) ĐƠN BIẾN │ (2) ĐA BIẾN  │
       ├──────────────────────────┼──────────────┼──────────────┤
       │ ★★ FARI dòng vào         │  34,87***    │  19,54***    │
       │                          │  (3,62)      │  (4,02)      │
       │ → QUY RA MỖI ĐỘ LỆCH     │  ★ ~8 GIỜ    │  ★ ~4 GIỜ    │
       │   CHUẨN                  │              │              │
       ├──────────────────────────┼──────────────┼──────────────┤
       │ Thương mại (X+M)/GDP     │              │ −6.059,45*** │
       │ Đầu tư trực tiếp/GDP     │              │   −725,10*   │
       │ Kiều hối/GDP             │              │    +16,53*** │
       │ Chỉ số an ninh mạng      │              │     −0,89*** │
       │ Mức sẵn sàng số          │              │     −5,68*** │
       │ Log GDP đầu người        │              │      0,33    │
       │ Log dân số               │              │     −0,70    │
       ├──────────────────────────┼──────────────┼──────────────┤
       │ R bình phương            │    0,15      │    0,28      │
       │ Số quan sát              │     528      │     528      │
       └──────────────────────────┴──────────────┴──────────────┘
       ★ RIÊNG FARI giải thích KHOẢNG 15% biến thiên tốc độ thanh
         toán → kiểm soát vốn đóng vai trò đáng kể
       ⚠ Hệ số GIẢM khi thêm biến kiểm soát — điều này ĐƯỢC KỲ
         VỌNG và cho thấy các biến kiểm soát có tương quan với cả
         FARI lẫn tốc độ thanh toán (chệch lên nếu bỏ sót)
       DẤU CỦA CÁC BIẾN KIỂM SOÁT ĐỀU HỢP LÝ
       · phụ thuộc thương mại càng cao → thanh toán càng NHANH
         (có thể do đầu tư vào hạ tầng thanh toán tốt hơn)
       · an ninh mạng và sẵn sàng số càng cao → càng NHANH
       ⚠ BIẾN ĐÃ THỬ NHƯNG KHÔNG CÓ Ý NGHĨA: danh sách xám của
         Lực lượng Đặc nhiệm Hành động Tài chính — ngay cả khi
         dùng làm biến giải thích DUY NHẤT
```

### Chênh lệch theo nhóm nước và khu vực

```text
       BẢNG 3 — THEO NHÓM THU NHẬP (nhóm tham chiếu: nước tiên tiến)
       ┌────────────────────────────────┬────────────────────────┐
       │ FARI (cho nước TIÊN TIẾN)      │ −16,16 KHÔNG Ý NGHĨA   │
       │ FARI × nước MỚI NỔI            │ ★ +39,09*              │
       │ Biến giả nước mới nổi          │ ★ +12,86***            │
       └────────────────────────────────┴────────────────────────┘
       ★★ ĐỌC THẾ NÀO — HAI TẦNG BẤT LỢI CỘNG DỒN
       ① với nước TIÊN TIẾN, KHÔNG BÁC BỎ ĐƯỢC giả thuyết rằng
          tác động của kiểm soát vốn BẰNG KHÔNG
       ② với nước MỚI NỔI, mỗi độ lệch chuẩn FARI làm chậm thêm
          KHOẢNG 9 GIỜ so với nước tiên tiến
       ③ ngoài ra, ngay cả khi ĐÃ TÍNH tới kiểm soát vốn, thanh
          toán ở nước mới nổi vẫn chậm hơn KHOẢNG 13 GIỜ
       ═══════════════════════════════════════════════════════════
       THEO MỨC SẴN SÀNG SỐ (chỉ số Cisco 2021, bảy thành phần;
       chia mẫu theo trung vị)
       FARI × nhóm sẵn sàng số CAO ····· +7,01 KHÔNG Ý NGHĨA
       Biến giả nhóm sẵn sàng số CAO ··· ★ −22,01***
       ★★ PHÁT HIỆN TINH TẾ: mức sẵn sàng số KHÔNG thay đổi được
          TÁC ĐỘNG của kiểm soát vốn, nhưng TỰ NÓ tạo chênh lệch
          RẤT LỚN — nước sẵn sàng số cao thanh toán nhanh hơn
          KHOẢNG 22 GIỜ
          → công nghệ KHÔNG "chữa" được ma sát do kiểm soát vốn,
            nhưng vẫn là đòn bẩy độc lập rất mạnh
       ═══════════════════════════════════════════════════════════
       BẢNG 4 — THEO KHU VỰC (tham chiếu: CHÂU ÂU VÀ TRUNG Á)
       ┌───────────────────────┬───────────┬──────────────────────┐
       │ KHU VỰC               │ ĐỘ DỐC    │ HỆ SỐ CHẶN           │
       │                       │ (× FARI)  │ (chậm hơn tham chiếu)│
       ├───────────────────────┼───────────┼──────────────────────┤
       │ ★ Châu Âu và Trung Á  │ +58,88*** │  —  (tham chiếu)     │
       │   (tức ~13 giờ mỗi độ │           │                      │
       │    lệch chuẩn)        │           │                      │
       │   Đông Á và TBD       │ −45,95*** │ +20,15***            │
       │   Châu Mỹ             │ −42,33*** │ +12,18***            │
       │   Châu Phi hạ Sahara  │ −34,33*** │ +21,89***            │
       │   Nam Á               │ −74,39*** │ ★★ +52,29***         │
       │   Trung Đông và Bắc   │  −8,37    │ +21,23***            │
       │   Phi                 │ không ý   │                      │
       │                       │ nghĩa     │                      │
       └───────────────────────┴───────────┴──────────────────────┘
       ★★ ĐỌC CẶP SỐ NÀY CHO NAM Á — TRƯỜNG HỢP THÚ VỊ NHẤT
       · độ dốc: 58,88 − 74,39 = −15,5 → tổng tác động của kiểm
         soát vốn KHÔNG KHÁC KHÔNG về mặt thống kê
       · hệ số chặn: thanh toán chậm hơn châu Âu và Trung Á tới
         52 GIỜ, BẤT KỂ mức kiểm soát vốn
       → ở Nam Á, nút thắt nằm ở CHỖ KHÁC, không phải kiểm soát vốn
       ★ NGHỊCH LÝ: châu Âu và Trung Á có hệ số chặn THẤP NHẤT
         (thanh toán nhanh nhất) nhưng ĐỘ DỐC DỐC NHẤT — nghĩa là
         nơi thanh toán vốn nhanh lại là nơi kiểm soát vốn gây
         thiệt hại tương đối lớn nhất
       ⚠ LƯU Ý PHƯƠNG PHÁP: Bắc Mỹ được GỘP với Mỹ Latin và Caribe
         để xoá thông tin nhận dạng từng nước, do dữ liệu Swift có
         tính bảo mật
```

### Kiểm chứng và giới hạn tự nhận

```text
       KIỂM CHỨNG ĐỘ VỮNG
       ① DÙNG TRUNG VỊ THAY VÌ TRUNG BÌNH (Phụ lục 1)
          trung bình nhạy với giá trị ngoại lai; trung vị lại
          triệt tiêu bớt biến thiên có ích
          kết quả: 28,78*** đơn biến → ~6 GIỜ
                   17,65*** đa biến → ~4 GIỜ
          dấu và mức ý nghĩa GIỐNG, độ lớn NHỎ HƠN CHÚT — chênh
          lệch giữa hai cách đo KHÔNG PHÂN BIỆT ĐƯỢC về thống kê
       ② KIỂM TRA PHI TUYẾN (Phụ lục 2)
          thêm FARI bình phương: hệ số 10,06 (trung bình) và
          15,93 (trung vị) — CẢ HAI ĐỀU KHÔNG CÓ Ý NGHĨA
          → kết quả cơ sở KHÔNG do giả định tuyến tính gây ra
       ═══════════════════════════════════════════════════════════
       ★★ BỐN GIỚI HẠN BÀI TỰ NÊU RÕ
       ❶ CHƯA PHẢI NHÂN QUẢ — chỉ là tương quan vững; các yếu tố
          vĩ mô và thể chế có thể gây ra CẢ HAI
       ❷ ★ CHỈ ĐO BIÊN NGOẠI DIÊN — FARI đếm CÓ BAO NHIÊU biện
          pháp, KHÔNG đo CƯỜNG ĐỘ của từng biện pháp. Giá trị
          chỉ số KHÔNG ĐỔI nếu một thành phần được tự do hoá một
          phần, hoặc nếu biện pháp hiện có bị siết chặt thêm
       ❸ KHÔNG ĐO HIỆU QUẢ THỰC THI — cả cường độ lẫn hiệu quả
          thực thi có thể ảnh hưởng tới kết quả NGANG NGỬA với
          số lượng biện pháp
       ❹ MẪU TRÙNG GIAI ĐOẠN COVID, khi phong toả và môi trường
          chính sách biến động có thể ảnh hưởng tới cả dòng vốn
          lẫn tốc độ thanh toán
       ⚠ Một nguồn sai số đo khác: trong vũ trụ giao dịch Swift
         KHÔNG THỂ tách giao dịch bị kiểm soát vốn chi phối khỏi
         giao dịch không bị. Thanh toán bán lẻ và kiều hối ít bị
         ảnh hưởng nhưng vẫn nằm trong mẫu
       ✔ NHƯNG: sai số đo ở BIẾN KẾT QUẢ làm SAI SỐ CHUẨN LỚN HƠN
         chứ KHÔNG gây CHỆCH kết quả
                              │
                              ▼
       HƯỚNG NGHIÊN CỨU TIẾP
       · dùng dữ liệu CẤP GIAO DỊCH đã ẩn danh ghép với dữ liệu
         AREAER chi tiết → áp dụng kỹ thuật suy luận nhân quả
         hiện đại, tập trung vào giai đoạn kiểm soát vốn THAY ĐỔI
         MẠNH thay vì chỉ nhìn biên ngoại diên
       · hai chỉ số ĐO CƯỜNG ĐỘ đang được xây dựng từ văn bản
         tường thuật AREAER bằng mã hoá thủ công và mô hình ngôn
         ngữ lớn (Bergant và cộng sự 2026; Li 2026)
       · mở rộng FARI ra nhiều năm hơn để phân tích tương tác với
         chuẩn thanh toán ISO 20022 — chuẩn mới mà giới hành nghề
         tin rằng chứa đủ thông tin phong phú để ĐẨY NHANH việc
         thực thi kiểm soát vốn ở nơi cơ quan quản lý yêu cầu
```

## Ba câu hỏi bài viết trả lời

1. Độ trễ trong thanh toán xuyên biên giới nằm ở chặng nào, và kiểm soát vốn được thực thi ở đúng chặng đó ra sao?
2. Mức kiểm soát vốn cao hơn đi kèm với thanh toán chậm hơn bao nhiêu, và con số đó có vững không?
3. Tác động này giống nhau hay khác nhau giữa các nhóm nước?

## Khái niệm cần biết

**Ngân hàng đại lý (correspondent banking).** Cách chuyển tiền quốc tế truyền thống: ngân hàng của người gửi không có tài khoản trực tiếp ở ngân hàng của người nhận, nên tiền đi qua một hoặc nhiều ngân hàng trung gian có quan hệ tài khoản với nhau. Ví dụ minh hoạ: một doanh nghiệp ở Kenya trả tiền cho nhà cung cấp ở Đức có thể đi qua một ngân hàng ở London rồi mới tới ngân hàng ở Frankfurt. Mỗi mắt xích thêm một chỗ có thể trễ, và bài đo xem mắt xích cuối cùng chậm đến đâu.

**Chặng thụ hưởng hay chặng cuối (last mile).** Đoạn thời gian từ lúc ngân hàng của người nhận đã nhận được lệnh chuyển tiền tới lúc tiền thật sự được ghi có vào tài khoản người nhận. Ví dụ từ bài: thời gian trung bình của chặng này trong mẫu là 30,72 giờ, có nơi chỉ 2,50 giờ, có nơi tới 120,00 giờ. Đây là đối tượng đo của toàn bài, vì phần lớn độ trễ nằm ở đây và cũng là nơi kiểm soát vốn được thực thi.

**Swift và mã UETR.** Swift là mạng nhắn tin tài chính mà các ngân hàng dùng để gửi lệnh chuyển tiền cho nhau, kết nối hơn 11.500 thành viên ở hơn 220 nước và vùng lãnh thổ. Mỗi lệnh được gắn một Mã Tham chiếu Giao dịch Đầu-cuối Duy nhất (UETR), giống như mã vận đơn của một gói hàng, nên có thể biết lệnh đó đi qua từng công đoạn lúc mấy giờ. Nhờ mã này, bài đo được chính xác thời gian chặng thụ hưởng của khoảng 4 tỷ giao dịch.

**Kiểm soát vốn (capital controls) và chỉ số FARI.** Kiểm soát vốn là các quy định hạn chế tiền vào hoặc ra khỏi một nước: phải xin phép, phải nêu mục đích, phải nộp chứng từ, có hạn mức, phải đổi ngoại tệ thu được ra nội tệ. Chỉ số Hạn chế Tài khoản Tài chính (FARI) đếm xem trong 29 loại giao dịch vốn liên quan đến dòng vào, có bao nhiêu loại đang bị kiểm soát, rồi quy về thang 0 tới 1. Ví dụ minh hoạ: một nước có kiểm soát ở 6 trong 29 loại sẽ có FARI khoảng 0,21, đúng bằng giá trị trung vị trong mẫu. Đây là biến giải thích chính của bài.

**Độ lệch chuẩn (standard deviation).** Thước đo mức phân tán của một biến quanh giá trị trung bình. Bài quy mọi hệ số về "tác động của một độ lệch chuẩn" để dễ hình dung. Ví dụ: độ lệch chuẩn của FARI là 0,22, tương đương khoảng 6–7 loại giao dịch có kiểm soát; hệ số 34,87 nhân với 0,22 cho ra khoảng 8 giờ chậm thêm. Không có khái niệm này thì không hiểu được các con số "bốn tới tám giờ" của bài.

**Hồi quy đơn biến, đa biến và biến kiểm soát.** Hồi quy là phương pháp thống kê ước lượng một biến thay đổi bao nhiêu khi biến khác thay đổi. Hồi quy đơn biến chỉ dùng một biến giải thích; hồi quy đa biến thêm các "biến kiểm soát", tức các yếu tố khác có thể ảnh hưởng tới kết quả, để tách riêng tác động của biến chính. Ví dụ: nếu nước kiểm soát vốn chặt cũng thường là nước nghèo công nghệ, thì hồi quy đơn biến sẽ gán cả phần chậm do công nghệ cho kiểm soát vốn. Trong bài, hệ số giảm từ 34,87 xuống 19,54 khi thêm biến kiểm soát chính là vì lý do này.

**Hệ số góc và hệ số chặn (slope / intercept).** Khi so các nhóm nước, hệ số góc (độ dốc) cho biết kiểm soát vốn làm chậm thêm bao nhiêu trong nhóm đó; hệ số chặn cho biết nhóm đó chậm hơn nhóm tham chiếu bao nhiêu ngay cả khi mức kiểm soát vốn như nhau. Ví dụ: Nam Á có hệ số chặn +52,29, tức chậm hơn châu Âu và Trung Á khoảng 52 giờ bất kể kiểm soát vốn. Phân biệt hai hệ số này giúp biết nút thắt nằm ở kiểm soát vốn hay ở chỗ khác.

**Tương quan và nhân quả.** Hai biến đi cùng nhau (tương quan) chưa chắc biến này gây ra biến kia (nhân quả); có thể một yếu tố thứ ba gây ra cả hai. Ví dụ minh hoạ: nước có thể chế yếu vừa hay dùng kiểm soát vốn, vừa có ngân hàng xử lý chậm. Bài tự nhận kết quả của mình là tương quan mạnh và vững, chưa phải nhân quả.

## Nội dung chi tiết

### 1. Bối cảnh và khoảng trống nghiên cứu

Thanh toán xuyên biên giới hiệu quả là nền tảng của hoạt động kinh tế toàn cầu: doanh nghiệp trả tiền hàng, người lao động gửi tiền về nhà, nhà đầu tư chuyển vốn. Đồng thời, một số nước áp dụng kiểm soát dòng vốn vào hoặc ra để đạt các mục tiêu vĩ mô, chẳng hạn ổn định thị trường khi có dòng vốn rút ra đột ngột. Những biện pháp này có thể cản trở thanh toán.

Theo Quan điểm Thể chế của IMF về Tự do hoá và Quản lý Dòng vốn, kiểm soát vốn là một dạng biện pháp quản lý dòng vốn, chỉ phù hợp trong một số hoàn cảnh nhất định và chỉ khi không được dùng để thay thế cho điều chỉnh vĩ mô cần thiết (như điều chỉnh lãi suất, tỷ giá hay tài khoá).

Từ năm 2020, nhóm G20 đặt mục tiêu 75% thanh toán xuyên biên giới phải hoàn tất trong vòng một giờ. Năm năm sau, theo báo cáo của Hội đồng Ổn định Tài chính (FSB) năm 2025, chỉ 54,6% số thanh toán trên 100.000 đô la (không tính loại ghi ngày giá trị tương lai) đạt mục tiêu này.

Khoảng trống nghiên cứu khá rõ. Phần lớn tài liệu về kiểm soát vốn nhìn vào hàm ý vĩ mô như tỷ giá, dòng vốn, tăng trưởng, mà ít chú ý tới tác động lên hệ thống thanh toán. Ngược lại, tài liệu về hiệu quả hệ thống thanh toán gần như chỉ tập trung vào hệ thống quyết toán tổng tức thời (nơi các ngân hàng trong nước quyết toán từng giao dịch lớn ngay lập tức) và thanh toán tức thì trong nước, chủ yếu xoay quanh rủi ro quyết toán.

Bằng chứng hiện có về quan hệ giữa kiểm soát vốn và tốc độ thanh toán hoặc hẹp về phạm vi, hoặc thuần định tính. Báo cáo CPMI-BIS-Swift năm 2022 tìm thấy rằng các nước có kiểm soát vốn đáng kể có xu hướng mất nhiều thời gian hơn ở chặng thụ hưởng, dùng hồi quy bình phương tối thiểu từng phần trên hơn một trăm bốn mươi nước. Các khảo sát và phỏng vấn của IMF và FSB gợi ý rằng việc xử lý thủ tục kiểm soát vốn, như xác minh mục đích chuyển tiền hoặc thiếu chứng từ, có thể làm chậm việc ghi có từ hàng giờ tới hàng ngày. Bài này đo quan hệ đó một cách định lượng, trên dữ liệu từng giao dịch và cho 176 nước.

### 2. Giải phẫu một lệnh chuyển tiền xuyên biên giới

Một lệnh chuyển tiền qua ngân hàng đại lý gồm ba chặng:

| Chặng | Bắt đầu | Kết thúc |
|---|---|---|
| Chặng gửi | Người trả khởi tạo lệnh | Ngân hàng gửi đưa lệnh lên mạng Swift |
| Chặng bay | Lệnh lên mạng Swift | Ngân hàng thụ hưởng nhận được lệnh, có thể sau khi qua một hoặc nhiều ngân hàng trung gian |
| Chặng thụ hưởng | Ngân hàng thụ hưởng nhận lệnh | Tiền được ghi có vào tài khoản của người nhận cuối |

Các nghiên cứu của CPMI-BIS-Swift (2022), FSB (2023, 2024) và Swift (2024) cho thấy chỗ tắc chủ yếu nằm ở chặng thụ hưởng. Chênh lệch giữa các khu vực rất lớn: năm 2024, tỷ lệ thanh toán được quyết toán trong một giờ ở chặng thụ hưởng là 81,8% ở Bắc Mỹ nhưng chỉ 24,7% ở châu Phi, tức chưa bằng một phần ba.

Có nhiều nguyên nhân có thể gây ra độ trễ này: giờ mở cửa của ngân hàng và hạ tầng thị trường, chênh lệch múi giờ, việc xử lý theo lô thay vì xử lý từng giao dịch ngay khi tới, thủ tục chống rửa tiền và tài trợ khủng bố, và kiểm soát vốn cùng các quy trình tuân thủ đi kèm. Bài này tập trung vào nguyên nhân cuối.

Điểm mấu chốt trong thiết kế nghiên cứu là: chính sách kiểm soát dòng vốn vào đòi hỏi nhiều loại kiểm tra tuân thủ, và các kiểm tra này do ngân hàng thụ hưởng thực hiện sau khi tiền đã vào tài khoản của ngân hàng nhưng trước khi giải ngân cho người nhận. Tức là đúng ở chặng thứ ba. Vì vậy, nếu kiểm soát vốn gây chậm trễ, dấu vết sẽ hiện ra ở thời gian của chặng thụ hưởng.

Với hầu hết các nước, kiểm tra gồm ba việc:

1. Xác minh thông tin người thụ hưởng: loại hình (cá nhân hay doanh nghiệp), lĩnh vực hoạt động, mã số thuế có chính xác không.
2. Xác định mục đích thanh toán, ghi dưới dạng mã hoặc dạng văn bản.
3. Kiểm tra chứng từ chứng minh như hợp đồng, hoá đơn, vận đơn xuất khẩu.

Một số nơi còn yêu cầu thêm: hạn mức số tiền, hạn chế loại tài khoản được phép nhận chuyển khoản từ nước ngoài, và buộc ngân hàng thụ hưởng báo cáo mọi giao dịch cho cơ quan quản lý địa phương. Nhiều quy trình trong số này không dễ tự động hoá, vì phải có người đọc hợp đồng hay đối chiếu hoá đơn. Do đó thời gian xử lý dao động từ vài phút (hồ sơ đầy đủ, khách quen, giao dịch lặp lại) tới vài ngày (thiếu thông tin hoặc thông tin sai).

### 3. Dữ liệu

Bài ghép hai bộ dữ liệu mới.

**Bộ thứ nhất: tốc độ thanh toán từ dữ liệu giao dịch Swift.** Swift kết nối hơn 11.500 thành viên tại hơn 220 nước và vùng lãnh thổ. Thời lượng chặng thụ hưởng được đo bằng mã UETR trong hệ thống Đổi mới Thanh toán Toàn cầu (gpi) của Swift, vốn ghi dấu thời gian ở từng công đoạn. Vũ trụ dữ liệu gồm khoảng 4 tỷ quan sát trong 2020–2022; dữ liệu chỉ có từ năm 2020 vì Swift lưu trữ tối đa bốn năm.

Bốn bộ lọc được áp dụng, mỗi bộ lọc có lý do rõ ràng:

1. **Loại các nước bị Swift hạn chế truy cập trong 2020–2022**: Afghanistan, Belarus, Iran, Myanmar, Nga, Somalia và Venezuela. Mục đích là bảo đảm quan hệ quan sát được là do kiểm soát vốn, không phải do cấm vận.
2. **Bỏ thanh toán trong nước**, vì kiểm soát vốn không tác động trực tiếp lên chúng. Tuy nhiên vẫn giữ các giao dịch bằng ngoại tệ giữa các ngân hàng trong nước, vì nhiều biện pháp kiểm soát vốn nhắm chính vào việc nắm giữ và chuyển ngoại tệ trong nước.
3. **Chỉ giữ lệnh chuyển tiền của khách hàng đơn lẻ** (loại điện MT103), loại bỏ các loại điện liên quan tới quyết toán liên ngân hàng, kho bạc, chứng khoán, tài trợ thương mại và quản lý tiền mặt.
4. **Chỉ giữ giao dịch có mã trạng thái ACCC** (đã được xác nhận ghi có) và loại giao dịch ghi ngày giá trị tương lai. Loại này đã tới ngân hàng thụ hưởng nhưng tiền chưa khả dụng cho khách hàng; nếu tính vào sẽ thổi phồng tốc độ giao tiền thực tế.

**Bộ thứ hai: Chỉ số Hạn chế Tài khoản Tài chính (FARI).** Chỉ số do Baba và cộng sự (2026) xây từ Báo cáo Thường niên về Cơ chế và Hạn chế Hối đoái (AREAER) của IMF. Thang đo từ 0 tới 1, với 0 là ít hạn chế nhất; chiều dòng vào có 29 thành phần. Ưu điểm so với các chỉ số quen thuộc như Chinn-Ito hay Fernández và cộng sự là phạm vi rộng hơn: ngoài đầu tư danh mục và đầu tư trực tiếp, FARI còn phủ tài khoản ngoại tệ của người không cư trú mở trong nước, tài khoản của người cư trú mở ở nước ngoài, và yêu cầu hồi hương (buộc mang ngoại tệ thu được về nước) cùng yêu cầu nộp lại ngoại tệ (buộc bán ngoại tệ cho ngân hàng). Nhược điểm là FARI không bao gồm hạn chế đối với giao dịch vãng lai như nhập khẩu và giao dịch vô hình (dịch vụ, thu nhập).

Bài dùng chỉ số dòng vào vì nó khớp nhất với chặng thụ hưởng: tiền đi vào nước của người nhận. Tương quan giữa chỉ số dòng vào và chỉ số tổng hợp là 0,9, nên lựa chọn này khó làm thay đổi kết quả.

Phạm vi cuối cùng của mẫu là 176 nước trong 2020–2022, tần suất năm.

**Sai số đo được nêu thẳng.** Trong vũ trụ giao dịch Swift, không thể tách giao dịch chịu sự chi phối của kiểm soát vốn khỏi giao dịch không chịu. Thanh toán bán lẻ và kiều hối ít bị ảnh hưởng nhưng vẫn nằm trong mẫu. Tuy nhiên, sai số đo nằm ở biến kết quả (thời gian thanh toán) chỉ làm sai số chuẩn lớn hơn, tức kết quả kém chính xác hơn, chứ không làm kết quả bị chệch về một phía.

### 4. Kết quả cơ sở

**Thống kê mô tả.**

| Biến | Trung bình | Trung vị | Nhỏ nhất | Lớn nhất | Độ lệch chuẩn |
|---|---|---|---|---|---|
| Thời gian chặng thụ hưởng (giờ) | 30,72 | 27,84 | 2,50 | 120,00 | 19,93 |
| FARI dòng vào | 0,29 | 0,21 | 0,00 | 0,83 | 0,22 |

Một độ lệch chuẩn của FARI là 0,22, tương đương khoảng 6–7 trong số 29 thành phần có kiểm soát vốn được áp dụng. Phần lớn biến thiên của FARI là giữa các nước, không phải trong nội bộ một nước theo thời gian, vì kiểm soát vốn là quy trình di chuyển chậm: trong ba năm, một nước hiếm khi thay đổi nhiều biện pháp.

Khi vẽ thời gian trung bình chặng thụ hưởng theo chỉ số kiểm soát vốn, mỗi điểm là một cặp nước và năm, quan hệ dương hiện ra rõ ràng. Nhưng ở mỗi giá trị của chỉ số, các điểm phân tán rất rộng, cho thấy nhiều yếu tố khác cũng ảnh hưởng tới tốc độ thanh toán.

**Hồi quy cơ sở.** Biến phụ thuộc là thời gian trung bình chặng thụ hưởng, tính bằng giờ. Số trong ngoặc là sai số chuẩn; \*\*\* là có ý nghĩa ở mức 1%, \* là có ý nghĩa ở mức 10%.

| Biến | (1) Đơn biến | (2) Đa biến |
|---|---|---|
| FARI dòng vào | 34,87\*\*\* (3,62) | 19,54\*\*\* (4,02) |
| Quy ra mỗi độ lệch chuẩn | khoảng 8 giờ | khoảng 4 giờ |
| Thương mại (xuất khẩu cộng nhập khẩu)/GDP | | −6.059,45\*\*\* |
| Đầu tư trực tiếp/GDP | | −725,10\* |
| Kiều hối/GDP | | +16,53\*\*\* |
| Chỉ số an ninh mạng | | −0,89\*\*\* |
| Mức sẵn sàng số | | −5,68\*\*\* |
| Log GDP đầu người | | 0,33 |
| Log dân số | | −0,70 |
| R bình phương | 0,15 | 0,28 |
| Số quan sát | 528 | 528 |

Hồi quy đơn biến cho hệ số 34,87, tức thời gian trung bình tăng gần 8 giờ cho mỗi độ lệch chuẩn của chỉ số (34,87 × 0,22). R bình phương 0,15 nghĩa là riêng FARI đã giải thích khoảng 15% biến thiên của tốc độ thanh toán giữa các nước, một tỷ lệ đáng kể cho một biến duy nhất.

Khi thêm các biến kiểm soát về điều kiện vĩ mô tài chính, khả năng tiếp cận tài chính và mức sẵn sàng số, hệ số giảm xuống 19,54, tức khoảng 4 giờ cho mỗi độ lệch chuẩn, nhưng vẫn có ý nghĩa ở mức 1%. Bài giải thích rằng mức giảm này là điều được kỳ vọng: các biến kiểm soát có tương quan với cả FARI lẫn tốc độ thanh toán, nên nếu bỏ sót chúng thì hệ số của FARI sẽ bị chệch lên. Vì vậy con số "bốn tới tám giờ" là khoảng giữa ước lượng có và không có biến kiểm soát.

Dấu của các biến kiểm soát đều hợp lý:

- Phụ thuộc thương mại càng cao, thanh toán càng nhanh, có thể vì các nước buôn bán nhiều đã đầu tư vào hạ tầng thanh toán tốt hơn.
- Chỉ số an ninh mạng và chỉ số sẵn sàng số đều có hệ số âm: nước kém tiên tiến về công nghệ có thanh toán chậm hơn.

Một biến đã được thử nhưng không có ý nghĩa là việc một nước có nằm trong danh sách xám của Lực lượng Đặc nhiệm Hành động Tài chính (FATF, danh sách các nước bị giám sát tăng cường về chống rửa tiền) hay không, ngay cả khi dùng làm biến giải thích duy nhất. Khi đưa vào cùng FARI, hệ số của FARI nhỏ đi một chút, còn biến danh sách xám chuyển sang hơi âm và không có ý nghĩa ở mọi mức tin cậy thông thường.

### 5. Chênh lệch theo nhóm nước

**Theo nhóm thu nhập** (nhóm tham chiếu là nước tiên tiến):

| Biến | Hệ số |
|---|---|
| FARI (cho nước tiên tiến) | −16,16, không có ý nghĩa |
| FARI × nước mới nổi | +39,09\* |
| Biến giả nước mới nổi | +12,86\*\*\* |

Kết quả cho thấy hai tầng bất lợi cộng dồn với các nền kinh tế mới nổi và đang phát triển:

1. Với nước tiên tiến, không bác bỏ được giả thuyết rằng tác động của kiểm soát vốn bằng không.
2. Với nước mới nổi, mỗi độ lệch chuẩn của FARI làm chậm thêm khoảng 9 giờ so với nước tiên tiến.
3. Ngoài ra, ngay cả khi đã tính tới kiểm soát vốn, thanh toán ở nước mới nổi vẫn chậm hơn khoảng 13 giờ.

**Theo mức sẵn sàng số.** Mức sẵn sàng số được đo bằng chỉ số Cisco năm 2021, gồm bảy thành phần: hạ tầng và mức độ áp dụng công nghệ, môi trường kinh doanh, phát triển vốn con người, đầu tư của doanh nghiệp và chính phủ, nhu cầu cơ bản của con người, và môi trường khởi nghiệp. Mẫu được chia đôi theo trung vị.

| Biến | Hệ số |
|---|---|
| FARI × nhóm sẵn sàng số cao | +7,01, không có ý nghĩa |
| Biến giả nhóm sẵn sàng số cao | −22,01\*\*\* |

Kết quả rất tinh tế. Hệ số góc không khác nhau có ý nghĩa giữa hai nhóm, tức là mức sẵn sàng số không làm thay đổi tác động của kiểm soát vốn. Nhưng hệ số chặn khác nhau rất lớn: nước có mức sẵn sàng số cao thanh toán nhanh hơn khoảng 22 giờ. Hàm ý là công nghệ không chữa được ma sát do kiểm soát vốn gây ra, nhưng tự nó vẫn là một đòn bẩy độc lập rất mạnh để tăng tốc thanh toán.

**Theo khu vực** (nhóm tham chiếu là châu Âu và Trung Á):

| Khu vực | Độ dốc (nhân với FARI) | Hệ số chặn (chậm hơn tham chiếu, giờ) |
|---|---|---|
| Châu Âu và Trung Á | +58,88\*\*\* (khoảng 13 giờ mỗi độ lệch chuẩn) | tham chiếu |
| Đông Á và Thái Bình Dương | −45,95\*\*\* | +20,15\*\*\* |
| Châu Mỹ | −42,33\*\*\* | +12,18\*\*\* |
| Châu Phi hạ Sahara | −34,33\*\*\* | +21,89\*\*\* |
| Nam Á | −74,39\*\*\* | +52,29\*\*\* |
| Trung Đông và Bắc Phi | −8,37, không có ý nghĩa | +21,23\*\*\* |

Độ dốc ở các khu vực khác được tính so với châu Âu và Trung Á. Ở châu Âu và Trung Á, mỗi độ lệch chuẩn của FARI làm chậm khoảng 13 giờ. Đông Á và Thái Bình Dương, châu Mỹ và châu Phi hạ Sahara có độ dốc thoải hơn lần lượt khoảng 10, 9 và 8 giờ mỗi độ lệch chuẩn so với mức đó. Ở Trung Đông và Bắc Phi, chênh lệch độ dốc so với nhóm tham chiếu không có ý nghĩa.

Nam Á là trường hợp thú vị nhất. Độ dốc tổng là 58,88 − 74,39 = −15,5, và tổng tác động này không khác không về mặt thống kê: ở Nam Á, nhiều hay ít kiểm soát vốn không làm thanh toán nhanh hay chậm hơn. Nhưng hệ số chặn cho thấy thanh toán ở Nam Á chậm hơn châu Âu và Trung Á tới 52 giờ, bất kể mức kiểm soát vốn. Kết hợp hai con số cho một kết luận rõ: ở Nam Á, nút thắt nằm ở chỗ khác, không phải ở kiểm soát vốn.

Các hệ số chặn cũng cho thấy mọi khu vực đều chậm hơn châu Âu và Trung Á một cách có ý nghĩa. Từ đó nảy ra một nghịch lý: châu Âu và Trung Á có hệ số chặn thấp nhất (thanh toán nhanh nhất) nhưng độ dốc dốc nhất. Nghĩa là ở nơi thanh toán vốn đã nhanh, kiểm soát vốn lại gây thiệt hại tương đối lớn nhất.

Một lưu ý về phương pháp: Bắc Mỹ được gộp với Mỹ Latin và Caribe thành nhóm "châu Mỹ" để xoá thông tin có thể nhận dạng từng nước, vì dữ liệu Swift có tính bảo mật.

### 6. Kiểm chứng độ vững

**Kiểm chứng thứ nhất: dùng trung vị thay vì trung bình.** Bài lập luận cân bằng hai chiều. Thời gian trung bình nhạy với giá trị ngoại lai: vài giao dịch bị kẹt nhiều ngày có thể kéo trung bình lên. Nhưng lấy trung vị lại triệt tiêu bớt phần biến thiên có ích. Kết quả với trung vị:

| Mô hình | Hệ số | Quy ra mỗi độ lệch chuẩn |
|---|---|---|
| Đơn biến | 28,78\*\*\* | khoảng 6 giờ |
| Đa biến | 17,65\*\*\* | khoảng 4 giờ |

Dấu và mức ý nghĩa giống kết quả cơ sở. Độ lớn nhỏ hơn một chút, nhưng chênh lệch giữa hai cách đo không phân biệt được về mặt thống kê.

**Kiểm chứng thứ hai: kiểm tra phi tuyến.** Bài thêm số hạng FARI bình phương để xem tác động có tăng nhanh hơn khi kiểm soát vốn rất chặt hay không. Hệ số của số hạng bình phương là 10,06 (với trung bình) và 15,93 (với trung vị), cả hai đều không có ý nghĩa. Việc thêm số hạng này làm giảm mức ý nghĩa của hệ số tuyến tính, nhưng thống kê F (kiểm định hai hệ số cùng bằng không) vẫn lớn. Kết luận là kết quả cơ sở không phải do giả định quan hệ tuyến tính gây ra.

### 7. Diễn giải và giới hạn

Bài nói rõ rằng kiểm soát vốn vẫn là một phần trong khuôn khổ chính sách của các nước nhằm ngăn lan truyền cú sốc kinh tế và tài chính quốc tế. Theo Quan điểm Thể chế, biện pháp với dòng vào có thể hữu ích trong một số hoàn cảnh, kể cả theo hướng phòng ngừa, miễn là không thay thế cho điều chỉnh vĩ mô cần thiết.

Nhưng kiểm soát vốn áp đặt chi phí hành chính và ma sát lên tổ chức trung gian và người nhận cuối. Kết quả không thể diễn giải theo nghĩa nhân quả, nhưng gợi ý rằng kiểm soát vốn có thể là một nguồn gây chậm trễ, và điều này nên được đưa vào khi đánh giá chi phí và lợi ích vĩ mô của kiểm soát vốn.

Bài tự nêu rõ bốn giới hạn:

1. **Chưa phải nhân quả.** Đây chỉ là tương quan vững; các yếu tố vĩ mô và thể chế có thể gây ra cả kiểm soát vốn chặt lẫn thanh toán chậm.
2. **Chỉ đo biên ngoại diên.** FARI đếm có bao nhiêu biện pháp được áp dụng, không đo cường độ của từng biện pháp. Giá trị chỉ số không đổi nếu một thành phần được tự do hoá một phần, hoặc nếu một biện pháp hiện có bị siết chặt thêm.
3. **Không đo hiệu quả thực thi.** Cả cường độ lẫn hiệu quả thực thi có thể ảnh hưởng tới kết quả ngang ngửa với số lượng biện pháp.
4. **Mẫu trùng giai đoạn COVID**, khi phong toả và môi trường chính sách biến động có thể ảnh hưởng tới cả dòng vốn lẫn tốc độ thanh toán.

Sự khác biệt của kết quả giữa các nhóm thu nhập, mức sẵn sàng số và khu vực địa lý gợi ý rằng các yếu tố khác ngoài kiểm soát vốn có vai trò lớn. Điều đó nhấn mạnh tầm quan trọng của việc mỗi nước triển khai các chính sách quốc tế đã thống nhất trong Lộ trình Thanh toán Xuyên biên giới của G20.

Nhiều nỗ lực đang góp phần cải thiện tốc độ: toàn ngành chuyển sang chuẩn ISO 20022 cho thanh toán và báo cáo xuyên biên giới (một chuẩn thông điệp chứa dữ liệu có cấu trúc phong phú hơn về người gửi, người nhận và mục đích), sử dụng nhiều hơn các dịch vụ giảm ma sát của Swift, và tích hợp các công nghệ như trí tuệ nhân tạo và giao diện lập trình ứng dụng.

**Hướng nghiên cứu tiếp:**

- Dùng dữ liệu cấp giao dịch đã ẩn danh ghép với dữ liệu AREAER chi tiết để áp dụng các kỹ thuật suy luận nhân quả hiện đại, tập trung vào những giai đoạn kiểm soát vốn thay đổi mạnh thay vì chỉ nhìn biên ngoại diên.
- Vào thời điểm viết, hai chỉ số đo cường độ kiểm soát vốn đang được xây dựng từ văn bản tường thuật trong AREAER, bằng mã hoá thủ công và bằng mô hình ngôn ngữ lớn (Bergant và cộng sự 2026; Li 2026).
- Mở rộng FARI ra nhiều năm hơn sẽ cho phép phân tích tương tác giữa kiểm soát vốn và việc áp dụng ISO 20022. Giới hành nghề tin rằng chuẩn này chứa đủ thông tin để đẩy nhanh việc thực thi kiểm soát vốn ở nơi cơ quan quản lý yêu cầu.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Cross-border payment | Thanh toán xuyên biên giới |
| Last mile | Chặng cuối, đoạn từ ngân hàng thụ hưởng tới khách hàng cuối |
| Originator leg | Chặng gửi, từ người trả tới khi lệnh lên mạng Swift |
| In-flight leg | Chặng bay, thời gian lệnh đi trên mạng Swift |
| Beneficiary leg | Chặng thụ hưởng, từ khi ngân hàng nhận tới khi ghi có cho khách |
| Beneficiary Elapsed Time | Thời gian trôi qua ở chặng thụ hưởng, biến kết quả chính |
| Swift | Mạng nhắn tin tài chính toàn cầu |
| UETR | Mã Tham chiếu Giao dịch Đầu-cuối Duy nhất, cho phép theo dấu thời gian |
| GPI | Hệ thống Đổi mới Thanh toán Toàn cầu của Swift |
| MT103 | Mã điện cho lệnh chuyển tiền khách hàng đơn lẻ |
| ACCC | Mã trạng thái xác nhận đã ghi có cho người thụ hưởng |
| FVD | Ngày giá trị tương lai, tiền chưa khả dụng cho khách |
| Correspondent bank | Ngân hàng đại lý trong chuỗi thanh toán |
| Capital control | Kiểm soát vốn: hạn chế, thuế hoặc cấm giao dịch vốn |
| CFM | Biện pháp quản lý dòng vốn theo phân loại của IMF |
| Institutional View | Quan điểm Thể chế của IMF về tự do hoá và quản lý dòng vốn |
| AREAER | Báo cáo Thường niên về Cơ chế và Hạn chế Hối đoái của IMF |
| FARI | Chỉ số Hạn chế Tài khoản Tài chính, thang 0 tới 1, 29 thành phần |
| Extensive margin | Biên ngoại diên, số lượng biện pháp đang áp dụng |
| Intensive margin | Biên nội hàm, cường độ của từng biện pháp |
| Repatriation requirement | Yêu cầu hồi hương nguồn thu về nước |
| Surrender requirement | Yêu cầu nộp lại ngoại tệ cho ngân hàng trung ương |
| AML/CFT | Chống rửa tiền và tài trợ khủng bố |
| FATF grey list | Danh sách xám của Lực lượng Đặc nhiệm Hành động Tài chính |
| Batch processing | Xử lý theo lô thay vì theo từng giao dịch |
| ISO 20022 | Chuẩn dữ liệu mới cho thanh toán và báo cáo xuyên biên giới |
| Digital readiness | Mức sẵn sàng số, chỉ số Cisco gồm bảy thành phần |
| G20 Roadmap | Lộ trình Thanh toán Xuyên biên giới của G20 |
| Standard deviation | Độ lệch chuẩn, đơn vị dùng để quy đổi độ lớn hệ số |

## Câu nói đáng nhớ

> "A one-standard-deviation increase in the measure of capital controls is associated with cross-border payments that are four to eight hours slower."

> "Our measure only reflects how many capital controls are in place, without accounting for the intensity of any specific capital control."

> "For advanced economies, we cannot reject that the impact of capital controls is zero."

## Đánh giá và phát hiện đáng chú ý

### Lần đầu tiên chi phí hành chính của kiểm soát vốn có đơn vị đo là giờ

Tranh luận về kiểm soát vốn hai thập kỷ qua diễn ra trên một mặt phẳng lệch: phía lợi ích có số, phía chi phí chỉ có tính từ. Đóng góp thật của bài nằm ở đó, không nằm ở phương pháp — **nó biến một tính từ thành một con số có đơn vị**. Bốn tới tám giờ cho mỗi độ lệch chuẩn, mà một độ lệch chuẩn ở đây rất dễ hình dung: khoảng sáu tới bảy trong hai mươi chín thành phần được kích hoạt. Từ nay, câu hỏi có nên thêm một biện pháp hạn chế dòng vào có thể đặt dưới dạng: biện pháp này đáng giá bao nhiêu giờ chậm trễ cho mọi giao dịch đi vào nền kinh tế.

Nhưng phải giữ con số ấy đúng tỷ lệ. Thời gian trung bình ở chặng thụ hưởng là **30,72 giờ**, trung vị 27,84. So với mục tiêu một giờ của G20, phần do kiểm soát vốn giải thích chỉ chiếm một phần tư tới một phần tám độ trễ. Xoá sạch kiểm soát vốn trên toàn thế giới thì nước trung bình vẫn cách mục tiêu hơn một ngày làm việc. Số liệu của bài nói rõ điều mà bài không nói: **kiểm soát vốn là một nguyên nhân thật, không phải nguyên nhân chính**.

### 528 quan sát, biến thiên nằm giữa các nước, và COVID nằm trọn trong mẫu

Mẫu là 176 nước trong ba năm, 528 quan sát, tần suất năm. Bài tự thừa nhận phần lớn biến thiên nằm **giữa các nước chứ không trong nội bộ một nước theo thời gian**, nên không thể đưa hiệu ứng cố định theo nước vào mà không triệt tiêu hết biến thiên cần thiết. Dù trình bày dưới dạng bảng nhiều năm, đây về bản chất là **một hồi quy cắt ngang**, với R bình phương 0,28 — tức 72% biến thiên nằm ngoài mô hình. Biến bỏ sót đáng ngờ nhất là **năng lực hành chính của hệ thống ngân hàng**, thứ vừa sinh ra nhiều biện pháp hơn vừa sinh ra quy trình hậu kiểm chậm hơn; chỉ số an ninh mạng và mức sẵn sàng số đều đo hạ tầng công nghệ, không đo năng lực hành chính.

Vấn đề COVID cũng nặng hơn mức bài tự nhận. Giai đoạn 2020–2022 đúng là lúc nhiều nền kinh tế mới nổi siết biện pháp ngoại hối khẩn cấp, **và cũng là lúc bộ phận hậu kiểm của ngân hàng làm việc từ xa**. Hai thứ đẩy cùng một hướng: đây là chệch có hướng, không phải nhiễu. Nên coi bốn tới tám giờ là **cận trên**.

Thêm một điểm bài không đối chiếu: hệ số cho nhóm tiên tiến là −16,16 và không có ý nghĩa, trong khi châu Âu và Trung Á lại có **độ dốc dốc nhất mẫu**, 58,88. Hai con số chỉ hoà giải được nếu độ dốc ấy do phần Trung Á, Caucasus và Tây Balkan trong cùng nhóm tạo ra. **Hai lát cắt không trực giao với nhau**, và "nghịch lý" mà bài nêu ra nhiều khả năng là sản phẩm của cách chia nhóm chứ không phải một quy luật kinh tế.

### Hệ quả bài không dám phát biểu: Lộ trình G20 và Quan điểm Thể chế kéo ngược nhau

Bài nhắc rằng theo Quan điểm Thể chế, biện pháp với dòng vào có thể hữu ích, kể cả theo hướng phòng ngừa. Ngay sau đó nó đưa bằng chứng rằng những biện pháp ấy làm chậm thanh toán bốn tới tám giờ. Mục tiêu của G20 là một giờ.

Kết luận không cần phép tính nào: **một nước không thể vừa duy trì kiểm soát vốn ở mức trung bình của nhóm mới nổi vừa đạt mục tiêu G20**. Hai cam kết quốc tế mà cùng một nước có thể đã ký đang đòi hai điều loại trừ nhau. Câu "nên được đưa vào khi đánh giá vĩ mô về chi phí và lợi ích" là phiên bản ngoại giao của một xung đột thể chế thật.

Hệ quả phái sinh còn khó chịu hơn: tỷ lệ 54,6% mà FSB công bố như một chỉ số tiến độ chung thực ra **đang đo lựa chọn chính sách vĩ mô của các nước chứ không đo nỗ lực kỹ thuật của họ**. Một nước có thể đầu tư tối đa vào hạ tầng thanh toán mà vẫn tụt hạng, chỉ vì chọn giữ tài khoản vốn đóng.

### Vì sao đoạn cuối về ISO 20022 lật ngược ý nghĩa của cả bài

Đoạn gần cuối nhắc rằng giới hành nghề tin chuẩn ISO 20022 đủ giàu thông tin để **đẩy nhanh** việc thực thi kiểm soát vốn. Câu này nằm trong phần hướng nghiên cứu tiếp, như một ghi chú kỹ thuật, nhưng nó phủ định cách đọc mặc định của toàn bài.

Nếu đúng vậy, bốn tới tám giờ **không phải chi phí nội tại của kiểm soát vốn mà là chi phí của việc điện thanh toán không mang theo đủ dữ liệu**. Ngân hàng thụ hưởng chậm vì phải đi hỏi lại mục đích thanh toán, mã số thuế, hợp đồng, vận đơn — những thứ mà một chuẩn điện đủ giàu chuyển kèm được ngay từ đầu. Khi đó đại lượng bài ước lượng là thứ **sửa được bằng kỹ thuật**, không phải một khoản thuế cố hữu. Kết quả về mức sẵn sàng số củng cố cách đọc này: hệ số tương tác +7,01 không có ý nghĩa, tức công nghệ **không làm thay đổi độ dốc**, nhưng tự nó dịch hệ số chặn tới 22 giờ. Hạ tầng số tốt không giúp gì cho một hồ sơ thiếu vận đơn; chỉ công nghệ nhắm vào **nội dung dữ liệu đi kèm giao dịch** mới làm phẳng được độ dốc đó.

Đây cũng là chỗ bài vô tình giải thích sức hút của stablecoin ở các nền kinh tế mới nổi. Nó không nằm ở việc sổ cái phân tán nhanh hơn mạng Swift — chặng bay vốn không phải chỗ tắc — mà ở việc **bỏ qua hoàn toàn trạm kiểm soát tại ngân hàng thụ hưởng**. Đọc cùng các tài liệu về stablecoin và tương lai của thanh toán trong repo này, thứ stablecoin thật sự cạnh tranh không phải là công nghệ nhắn tin mà là chủ quyền quản lý dòng vốn — điều giải thích vì sao phản ứng của cơ quan quản lý nhóm mới nổi gay gắt hơn hẳn nhóm tiên tiến, nơi mà theo chính bài này kiểm soát vốn không tạo ra ma sát đáng kể nào.

### Với Việt Nam: nút thắt nằm ở hệ số chặn, không nằm ở độ dốc

Với Đông Á và Thái Bình Dương, độ dốc là 58,88 − 45,95 = **12,93**, tức khoảng **2,8 giờ cho mỗi độ lệch chuẩn**, chỉ bằng một phần năm độ dốc của châu Âu và Trung Á. Trong khi đó hệ số chặn là **+20,15 giờ chậm hơn nhóm tham chiếu, bất kể mức kiểm soát vốn**.

Đọc cặp số này như bài đã đọc cho Nam Á thì kết luận là: **với một nước Đông Á, phần lớn độ trễ không đến từ kiểm soát vốn**. Nếu Việt Nam tự do hoá một mảng đáng kể tài khoản vốn — một động tác vĩ mô rất lớn — phần thưởng về tốc độ thanh toán chỉ vài giờ. Còn 20 giờ kia nằm ở giờ mở cửa ngân hàng, xử lý theo lô, múi giờ và chất lượng dữ liệu trong điện thanh toán: những thứ sửa được bằng quyết định vận hành, **không đòi hỏi đánh đổi nào về chính sách vĩ mô**. Bốn việc cụ thể — chuyển dứt điểm sang ISO 20022, bỏ xử lý theo lô ở khâu ghi có ngoại tệ, kéo dài giờ xử lý điện quốc tế, và chuẩn hoá trước bộ chứng từ cho khách hàng xuất nhập khẩu giao dịch lặp lại — đều không đụng tới một dòng nào trong khung quản lý ngoại hối, mà lại nhắm đúng nhóm giao dịch bài mô tả là xử lý được trong vài phút thay vì vài ngày.

Một lưu ý cuối: chỉ số FARI **không bao gồm hạn chế giao dịch vãng lai**. Với một nền kinh tế mà phần lớn luồng ngoại tệ đi qua kênh thương mại và yêu cầu chứng từ thương mại là trọng tâm của quản lý ngoại hối, thước đo này bỏ sót đúng phần quan trọng nhất — chỉ số dòng vào có thể thấp trong khi ma sát thực tế của một doanh nghiệp xuất khẩu lại cao. Điểm này ăn khớp với tài liệu về hạn chế thanh toán thương mại và kiểm soát vốn trong thư mục ASEAN 2026, nơi hai loại biện pháp được xử lý tách bạch.

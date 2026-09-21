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

## Dàn ý chi tiết

### 1. Bối cảnh và khoảng trống nghiên cứu

- Thanh toán xuyên biên giới hiệu quả là nền tảng của hoạt động kinh tế toàn cầu. Đồng thời một số nước áp dụng kiểm soát dòng vốn vào hoặc ra với các mục tiêu vĩ mô như ổn định thị trường khi có dòng ra đột ngột, và những biện pháp này có thể cản trở thanh toán.
- Theo Quan điểm Thể chế của IMF về Tự do hoá và Quản lý Dòng vốn, kiểm soát vốn là một dạng biện pháp quản lý dòng vốn, chỉ phù hợp trong hoàn cảnh nhất định và chỉ khi không thay thế cho điều chỉnh vĩ mô cần thiết.
- Khoảng trống nghiên cứu khá rõ. Phần lớn tài liệu về kiểm soát vốn nhìn vào hàm ý vĩ mô, ít chú ý tới hàm ý lên hệ thống thanh toán. Ngược lại, tài liệu về hiệu quả hệ thống thanh toán gần như chỉ tập trung vào hệ thống quyết toán tổng tức thời và thanh toán tức thì trong bối cảnh trong nước, chủ yếu về rủi ro quyết toán.
- Bằng chứng hiện có về quan hệ giữa hai thứ hoặc hẹp về phạm vi hoặc thuần định tính. Báo cáo CPMI-BIS-Swift năm 2022 tìm thấy rằng các nước có kiểm soát vốn đáng kể có xu hướng có thời gian xử lý cao hơn ở chặng thụ hưởng, dùng hồi quy bình phương tối thiểu từng phần trên hơn một trăm bốn mươi nước. Bằng chứng từ khảo sát và phỏng vấn của IMF và FSB gợi ý rằng việc xử lý kiểm soát vốn, như xác minh mục đích hoặc thiếu chứng từ, có thể làm chậm việc ghi có từ hàng giờ tới hàng ngày.

### 2. Giải phẫu một lệnh chuyển tiền xuyên biên giới

- Một lệnh chuyển tiền qua ngân hàng đại lý gồm ba chặng. Chặng gửi tính từ khi người trả khởi tạo lệnh tới khi ngân hàng gửi đưa lệnh lên mạng Swift. Chặng bay là thời gian trên mạng Swift cho tới khi ngân hàng thụ hưởng nhận được, có thể qua một hoặc nhiều ngân hàng trung gian. Chặng thụ hưởng tính từ khi ngân hàng thụ hưởng nhận lệnh tới khi tiền được ghi có vào tài khoản khách hàng cuối.
- Điểm mấu chốt về mặt thiết kế nghiên cứu là chính sách kiểm soát dòng vốn vào đòi hỏi nhiều loại kiểm tra tuân thủ, và các kiểm tra đó được ngân hàng thụ hưởng thực hiện sau khi tiền đã vào tài khoản của mình nhưng trước khi giải ngân. Tức là đúng ở chặng thứ ba.
- Với hầu hết các nước, kiểm tra gồm xác minh thông tin người thụ hưởng, mục đích thanh toán, và chứng từ chứng minh. Một số nơi yêu cầu thêm hạn mức số tiền, hạn chế loại tài khoản đủ điều kiện nhận chuyển khoản nước ngoài, và yêu cầu ngân hàng thụ hưởng báo cáo mọi giao dịch cho cơ quan quản lý địa phương. Bài lưu ý rằng một số quy trình trong đó không dễ tự động hoá, nên thời gian xử lý dao động từ vài phút tới vài ngày.

### 3. Dữ liệu

- Thước đo tốc độ được tính từ dữ liệu giao dịch của Swift, mạng nhắn tin tài chính kết nối hơn mười một nghìn năm trăm thành viên tại hơn hai trăm hai mươi nước và vùng lãnh thổ. Thời lượng chặng thụ hưởng được đo bằng Mã Tham chiếu Giao dịch Đầu-cuối Duy nhất trong hệ thống Đổi mới Thanh toán Toàn cầu, vốn ghi dấu thời gian ở từng công đoạn.
- Vũ trụ dữ liệu khoảng bốn tỷ quan sát, chỉ có từ năm 2020 vì thời hạn lưu trữ tối đa của Swift là bốn năm. Bốn bộ lọc được áp dụng, và mỗi bộ lọc đều có lý do rõ ràng. Loại các nước bị Swift hạn chế truy cập để bảo đảm quan hệ quan sát được do kiểm soát vốn chứ không do cấm vận. Bỏ thanh toán trong nước vì kiểm soát vốn không tác động trực tiếp, nhưng giữ giao dịch ngoại tệ giữa các ngân hàng trong nước vì nhiều biện pháp kiểm soát vốn nhắm chính vào việc nắm giữ và chuyển ngoại tệ trong nước. Chỉ giữ lệnh chuyển tiền khách hàng đơn lẻ, loại các loại điện liên quan tới quyết toán liên ngân hàng, kho bạc, chứng khoán, tài trợ thương mại và quản lý tiền mặt. Chỉ giữ giao dịch đã được xác nhận ghi có và loại giao dịch ghi ngày giá trị tương lai, vì loại này đã tới ngân hàng thụ hưởng nhưng tiền chưa khả dụng cho khách, nếu tính vào sẽ thổi phồng tốc độ giao thực tế.
- Thước đo kiểm soát vốn là Chỉ số Hạn chế Tài khoản Tài chính, xây từ AREAER. Ưu điểm so với các chỉ số quen thuộc như Chinn-Ito hay Fernández và cộng sự là phạm vi rộng hơn, phủ cả tài khoản ngoại tệ của người không cư trú trong nước, tài khoản của người cư trú ở nước ngoài, cùng yêu cầu hồi hương và nộp lại. Nhưng nó không bao gồm hạn chế giao dịch vãng lai. Bài dùng chỉ số dòng vào vì nó khớp nhất với chặng thụ hưởng, và lưu ý tương quan với chỉ số tổng hợp là không phẩy chín nên lựa chọn này khó làm thay đổi kết quả.
- Một sai số đo được nêu thẳng: trong vũ trụ giao dịch Swift không thể tách giao dịch bị kiểm soát vốn chi phối khỏi giao dịch không bị. Thanh toán bán lẻ và kiều hối ít bị ảnh hưởng nhưng vẫn nằm trong mẫu. Tuy nhiên, sai số đo ở biến kết quả làm sai số chuẩn lớn hơn chứ không gây chệch.

### 4. Kết quả cơ sở

- Hình 2 vẽ quan hệ giữa thời gian trung bình chặng thụ hưởng và chỉ số kiểm soát vốn, mỗi điểm là một cặp nước và năm. Quan hệ dương rõ ràng, nhưng độ phân tán rất lớn ở mỗi giá trị của chỉ số, cho thấy nhiều yếu tố khác cũng ảnh hưởng tới tốc độ thanh toán.
- Hồi quy đơn biến cho hệ số ba mươi bốn phẩy tám bảy, tức thời gian trung bình tăng gần tám giờ cho mỗi độ lệch chuẩn của chỉ số. Cần lưu ý rằng một độ lệch chuẩn tương đương khoảng sáu tới bảy trong số hai mươi chín thành phần có kiểm soát vốn được áp dụng. Riêng chỉ số này giải thích khoảng mười lăm phần trăm biến thiên.
- Khi thêm bộ biến kiểm soát về điều kiện vĩ mô tài chính, khả năng tiếp cận tài chính và mức sẵn sàng số, hệ số giảm xuống mười chín phẩy năm tư, tức khoảng bốn giờ cho mỗi độ lệch chuẩn, nhưng vẫn có ý nghĩa ở mức một phần trăm. Bài giải thích rằng mức giảm này được kỳ vọng và cho thấy các biến kiểm soát có tương quan với cả hai biến chính, nghĩa là bỏ sót chúng sẽ làm hệ số chệch lên.
- Dấu của các biến kiểm soát đều hợp lý. Phụ thuộc thương mại càng cao đi kèm thanh toán càng nhanh, có thể vì các nước đó đầu tư vào hạ tầng thanh toán tốt hơn. Cả chỉ số an ninh mạng lẫn chỉ số sẵn sàng số đều có hệ số âm, cho thấy nước kém tiên tiến về công nghệ có thanh toán chậm hơn.
- Một biến đã thử nhưng không có ý nghĩa là việc một nước có nằm trong danh sách xám của Lực lượng Đặc nhiệm Hành động Tài chính hay không, ngay cả khi dùng làm biến giải thích duy nhất. Khi đưa vào cùng chỉ số kiểm soát vốn, hệ số của chỉ số này nhỏ đi một chút còn biến danh sách xám chuyển sang hơi âm và không có ý nghĩa ở mọi mức tin cậy thông thường.

### 5. Chênh lệch theo nhóm nước

- Khi chia theo nhóm thu nhập, kết quả cho thấy hai tầng bất lợi cộng dồn với các nền kinh tế mới nổi và đang phát triển. Với nước tiên tiến, không bác bỏ được giả thuyết rằng tác động bằng không. Với nước mới nổi, mỗi độ lệch chuẩn của chỉ số làm chậm thêm khoảng chín giờ so với nước tiên tiến. Ngoài ra, ngay cả khi đã tính tới kiểm soát vốn, thanh toán ở nước mới nổi vẫn chậm hơn khoảng mười ba giờ.
- Khi chia theo mức sẵn sàng số, đo bằng chỉ số Cisco năm 2021 gồm bảy thành phần về hạ tầng và mức độ áp dụng công nghệ, môi trường kinh doanh, phát triển vốn con người, đầu tư của doanh nghiệp và chính phủ, nhu cầu cơ bản của con người và môi trường khởi nghiệp, kết quả rất tinh tế. Hệ số góc không khác nhau có ý nghĩa giữa hai nhóm, tức mức sẵn sàng số không thay đổi được tác động của kiểm soát vốn. Nhưng hệ số chặn khác nhau rất lớn: nước có mức sẵn sàng số cao thanh toán nhanh hơn khoảng hai mươi hai giờ. Hàm ý là công nghệ không chữa được ma sát do kiểm soát vốn, nhưng vẫn là một đòn bẩy độc lập rất mạnh.
- Khi chia theo khu vực, độ dốc khác nhau rõ rệt. Ở châu Âu và Trung Á, nhóm tham chiếu, mỗi độ lệch chuẩn của chỉ số làm chậm khoảng mười ba giờ. Đông Á và Thái Bình Dương, châu Mỹ và châu Phi hạ Sahara có độ dốc thoải hơn lần lượt khoảng mười, chín và tám giờ. Ở Nam Á, tổng tác động không khác không có ý nghĩa. Ở Trung Đông và Bắc Phi, chênh lệch so với nhóm tham chiếu không có ý nghĩa.
- Các hệ số chặn cho thấy mọi khu vực đều chậm hơn châu Âu và Trung Á một cách có ý nghĩa. Nam Á là trường hợp cực đoan nhất với năm mươi hai giờ chậm hơn, ngoài tác động của kiểm soát vốn. Kết hợp hai con số cho Nam Á cho ra một kết luận rõ: ở khu vực này nút thắt nằm ở chỗ khác, không phải kiểm soát vốn.
- Một điểm phương pháp được nêu: Bắc Mỹ được gộp với Mỹ Latin và Caribe để xoá thông tin nhận dạng từng nước, do dữ liệu Swift có tính bảo mật.

### 6. Kiểm chứng độ vững

- Kiểm chứng thứ nhất dùng trung vị thay vì trung bình. Bài lập luận cân bằng hai chiều: kết quả dựa trên trung bình nhạy hơn với giá trị ngoại lai, nhưng lấy trung vị lại triệt tiêu bớt biến thiên có ích. Kết quả cho khoảng sáu giờ ở mô hình đơn biến và khoảng bốn giờ ở mô hình đa biến, với dấu và mức ý nghĩa tương tự. Độ lớn nhỏ hơn một chút nhưng không phân biệt được về mặt thống kê với kết quả từ trung bình.
- Kiểm chứng thứ hai thêm số hạng bình phương của chỉ số để kiểm tra phi tuyến. Số hạng bình phương không khác không có ý nghĩa ở cả hai cách đo, và việc đưa vào làm giảm mức ý nghĩa của hệ số tuyến tính, nhưng thống kê F vẫn lớn. Kết luận là kết quả cơ sở không do giả định tuyến tính gây ra.

### 7. Diễn giải và giới hạn

- Bài nói rõ rằng kiểm soát vốn vẫn là một phần trong khuôn khổ chính sách của các nước nhằm ngăn lan truyền cú sốc kinh tế và tài chính quốc tế, và theo Quan điểm Thể chế thì biện pháp với dòng vào có thể hữu ích trong một số hoàn cảnh, kể cả theo hướng phòng ngừa, miễn là không thay thế cho điều chỉnh vĩ mô cần thiết.
- Nhưng kiểm soát vốn áp đặt chi phí hành chính và ma sát lên tổ chức trung gian và người nhận cuối. Kết quả không thể diễn giải theo nghĩa nhân quả, nhưng gợi ý rằng kiểm soát vốn có thể là một nguồn gây chậm trễ, và điều này nên được đưa vào khi đánh giá vĩ mô về chi phí và lợi ích của kiểm soát vốn.
- Giới hạn quan trọng nhất là chỉ số chỉ phản ánh có bao nhiêu biện pháp được áp dụng, tức biên ngoại diên, mà không tính tới cường độ của từng biện pháp. Giá trị chỉ số không thay đổi nếu một thành phần được tự do hoá một phần, hoặc nếu các biện pháp hiện có bị siết chặt thêm. Chỉ số cũng không đo hiệu quả thực thi. Cả cường độ lẫn hiệu quả thực thi đều có thể ảnh hưởng tới kết quả ngang ngửa với số lượng biện pháp.
- Sự khác biệt của kết quả giữa các nhóm thu nhập, mức sẵn sàng số và khu vực địa lý gợi ý rằng các yếu tố khác này có vai trò. Điều đó nhấn mạnh tầm quan trọng của việc triển khai ở cấp quốc gia các chính sách quốc tế đã thống nhất trong Lộ trình Thanh toán Xuyên biên giới của G20.
- Nhiều nỗ lực đang góp phần cải thiện tốc độ: việc toàn ngành chuyển sang chuẩn ISO 20022 cho thanh toán và báo cáo xuyên biên giới, việc sử dụng nhiều hơn các dịch vụ giảm ma sát của Swift, và việc tích hợp các công nghệ như trí tuệ nhân tạo và giao diện lập trình ứng dụng.
- Hướng nghiên cứu tiếp gồm dùng dữ liệu cấp giao dịch đã ẩn danh ghép với dữ liệu AREAER chi tiết để áp dụng kỹ thuật suy luận nhân quả hiện đại, tập trung vào các giai đoạn kiểm soát vốn thay đổi mạnh. Bài cũng lưu ý rằng vào thời điểm viết, hai chỉ số đo cường độ kiểm soát vốn đang được xây dựng từ văn bản tường thuật AREAER bằng mã hoá thủ công và mô hình ngôn ngữ lớn. Mở rộng chỉ số ra nhiều năm hơn sẽ cho phép phân tích tương tác giữa kiểm soát vốn và việc áp dụng ISO 20022, chuẩn mà giới hành nghề tin rằng chứa đủ thông tin phong phú để đẩy nhanh việc thực thi kiểm soát vốn ở nơi cơ quan quản lý yêu cầu.

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

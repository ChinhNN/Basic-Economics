# HANK-Based Fiscal Consolidation for a High-Debt Advanced Euro Area Economy — Củng cố tài khoá cho một nền kinh tế nợ cao trong khu vực đồng euro: phân tích bằng mô hình HANK

**Nguồn:** IMF Working Paper WP/2026/121.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 2, không có trang bìa, tóm tắt và trang tác giả).
**Ý chính:** Các nền kinh tế nợ cao của khu vực đồng euro phải giảm nợ trong khi vẫn phải hỗ trợ tăng trưởng và bảo vệ hộ dễ tổn thương. Bài dùng **mô hình Keynes mới với hộ gia đình không đồng nhất (HANK)** hai loại tài sản, thêm nhiều công cụ tài khoá, **phần bù rủi ro chủ quyền tăng theo nợ** và **nợ nhiều kỳ hạn**, hiệu chỉnh cho một nền kinh tế đại diện ghép từ **Bỉ, Pháp và Ý** với nợ **125% GDP**. Ba kết luận: thứ nhất, **giữ nguyên chính sách không phải là trung lập**, vì nợ trôi lên, chênh lệch lợi suất tăng và đầu tư tư nhân bị lấn át; thứ hai, với cùng nỗ lực **1,5 điểm phần trăm GDP trong 2027–31**, **củng cố dựa vào chi** làm sản lượng năm đầu giảm khoảng **0,2%**, ít hơn mức **0,25%** của **củng cố dựa vào thu**, và giảm nợ nhanh hơn, vì thuế lao động đánh vào thu nhập của những hộ tiêu gần hết phần thu nhập tăng thêm; thứ ba, **một khoản bù nhỏ nhắm đúng vào hộ nghèo** gần như triệt tiêu thiệt hại ở nhóm đáy với chi phí rất thấp. Nếu **thêm cải cách cơ cấu nâng năng suất**, sản lượng vượt mức giữ nguyên chính sách từ năm thứ hai và lợi ích nghiêng về hộ nghèo.

> **Lưu ý:** bản PDF bắt đầu từ trang 2, thiếu trang bìa, tóm tắt và trang tác giả. Số hiệu lấy từ trang bìa sau. Mô hình hiệu chỉnh theo năm, nhưng phụ lục gọi xu hướng tiêu dùng biên mục tiêu 0,44 là "theo quý", trong khi phần mở đầu nói xu hướng tiêu dùng biên theo quý trung bình 0,15–0,25. Tỷ trọng hộ "kiếm được bao nhiêu tiêu bấy nhiêu" trong mô hình (43,8%) cao gấp đôi dữ liệu (khoảng 22%). Các số lấy từ hình là giá trị ước đọc.

## Sơ đồ

### Bài toán

```text
       NỀN KINH TẾ NỢ CAO KHU VỰC EURO (~125% GDP)
       ┌─────────────────────────────────────────────────────────┐
       │ áp lực chi mới: dân số già, chuyển đổi xanh và số, quốc │
       │ phòng · tăng trưởng tiềm năng thấp · lạm phát năng lượng│
       │ đã bào mòn thu nhập thực từ 2021                        │
       └─────────────────────────────────────────────────────────┘
       ═══════════════════════════════════════════════════════════
       VÌ SAO KHÓ HƠN BÌNH THƯỜNG
       ① tăng trưởng thấp → khó "tăng trưởng để thoát nợ"
       ② nợ cao → nhà đầu tư định giá trượt tài khoá; chênh lệch lợi
          suất lan sang chi phí vốn của DOANH NGHIỆP
          ⚠ trong liên minh tiền tệ: chênh lệch tăng → cầu giảm → giá
            giảm → ECB không bù riêng cho một nước → lãi suất thực vẫn
            cao → tài khoá xấu thêm ("vòng xoáy giảm phát")
       ③ hộ gia đình KHÔNG ĐỒNG NHẤT: hộ thiếu thanh khoản tiêu gần
          hết phần thay đổi thu nhập sau thuế và trợ cấp
       ❓ nên thiết kế THÀNH PHẦN của củng cố thế nào?
          khung tài khoá EU mới cho phép giai đoạn điều chỉnh tới 7 năm
```

### Mô hình

```text
       NỀN: Auclert, Rognlie, Straub (2024), giải bằng Jacobian không
       gian chuỗi
       ═══════════════════════════════════════════════════════════
       HỘ GIA ĐÌNH — HAI TÀI KHOẢN
       ┌─────────────────────┬──────────────────────────────────┐
       │ tài sản THANH KHOẢN │ rút bất kỳ lúc nào nhưng lãi thấp│
       │                     │ hơn (trung gian thu phí ζ)       │
       │ tài sản KÉM THANH   │ lãi đầy đủ r nhưng chỉ điều chỉnh│
       │ KHOẢN               │ được với xác suất ν mỗi kỳ       │
       └─────────────────────┴──────────────────────────────────┘
       → hai nhóm "kiếm được bao nhiêu tiêu bấy nhiêu" (HtM):
         NGHÈO HtM: gần như không có tài sản
         GIÀU HtM: có tài sản kém thanh khoản (nhà, lương hưu) nhưng
           không có tiền mặt → vẫn tiêu theo thu nhập
       ★ không được vay; thuế lũy tiến kiểu Heathcote–Storesletten–
         Violante; năng suất cá nhân theo chuỗi Markov 11 nút
       ═══════════════════════════════════════════════════════════
       CÔNG CỤ TÀI KHOÁ
       thu · thuế lao động · thuế doanh nghiệp · thuế khoán (công cụ
             cân đối, phản ứng theo nợ)
       chi · trợ cấp BẢO HIỂM (lương hưu đóng góp, trợ cấp thất
             nghiệp) · trợ cấp khoán PHỔ QUÁT · trợ cấp NHẮM ĐÍCH (chỉ
             4 thập phân vị năng suất thấp nhất) · tiêu dùng chính phủ
             · đầu tư công (vào hàm sản xuất)
       ═══════════════════════════════════════════════════════════
       ★★ PHẦN MỞ RỘNG (theo Langot và cộng sự 2025)
       phần bù rủi ro ··· η × (nợ/GDP − nợ/GDP dài hạn)
       nợ nhiều kỳ hạn ·· coupon bình quân chỉ điều chỉnh DẦN khi
                          trái phiếu đáo hạn và được tái cấp vốn
       quy tắc Taylor ··· hệ số với lạm phát trong nước được thu nhỏ vì
                          ECB nhìn lạm phát TOÀN KHU VỰC
```

### Hiệu chỉnh

```text
       BỈ + PHÁP + Ý, bình quân gia quyền theo GDP
       (loại Hy Lạp vì thu ngân sách thấp, Tây Ban Nha vì tăng trưởng
        cao)
       ┌──────────────────────────────┬─────────┬──────────────────┐
       │ tham số                      │ giá trị │ nguồn/mục tiêu   │
       ├──────────────────────────────┼─────────┼──────────────────┤
       │ hệ số chiết khấu β           │ 0,94    │ tài sản/GDP      │
       │ co giãn Frisch               │ 0,5     │                  │
       │ chênh lệch kém/thanh khoản   │ 0,09    │ ★ MPC bình quân  │
       │ xác suất điều chỉnh ν        │ 0,15    │   = 0,44         │
       │ lãi suất thực r              │ 0,05    │ Auclert 2024     │
       │ tỷ phần vốn α                │ 0,4219  │ Penn World Table │
       │ độ dốc Phillips giá · lương  │ 0,22·0,10│ Auclert 2024    │
       │ hệ số Taylor                 │ 1,2     │ Langot 2025      │
       │ ★ độ nhạy chênh lệch theo nợ │ 0,0077  │ Langot 2025      │
       │ nợ/GDP                       │ 1,25    │ Eurostat Q3/2025 │
       │ tiêu dùng chính phủ/GDP      │ 0,21    │ World Bank       │
       └──────────────────────────────┴─────────┴──────────────────┘
       ═══════════════════════════════════════════════════════════
       ★ BẢNG 2 — THỜI ĐIỂM KHÔNG NHẮM TỚI
       ┌──────────────────────────────┬─────────┬─────────┐
       │                              │ MÔ HÌNH │ DỮ LIỆU │
       ├──────────────────────────────┼─────────┼─────────┤
       │ tỷ trọng HtM                 │ 0,438   │ ~0,22   │
       │ tỷ trọng giàu HtM            │ 0,324   │ ~0,17   │
       │ thanh khoản ≤ 10% thu nhập   │ 0,638   │ —       │
       │ Gini tài sản                 │ 0,845   │ ~0,67   │
       │ 10% giàu nhất nắm            │ 0,798   │ ~0,52   │
       └──────────────────────────────┴─────────┴─────────┘
       ⚠ mô hình dự báo QUÁ CAO tỷ trọng HtM và mức bất bình đẳng
       ★ biện hộ: nhắm MPC bình quân vì đó là thống kê đủ cho động
         thái tổng (Debortoli–Galí 2024, Bilbiie 2020)
```

### Bốn kênh truyền dẫn

```text
       ❶ CHI TIÊU CHÍNH PHỦ
          cắt tiêu dùng công → cầu giảm TƯƠNG ĐƯƠNG, bỏ qua MPC
          cắt đầu tư công → giảm cầu ngắn hạn VÀ bào mòn vốn công, kéo
            tụt sản lượng tiềm năng → số nhân LỚN NHẤT
       ❷ THU NHẬP KHẢ DỤNG
          trực tiếp qua thuế, trợ cấp; gián tiếp qua lương, việc làm
          ★ rơi vào hộ HtM (kể cả giàu HtM) → cầu co mạnh hơn
       ❸ LÃI SUẤT
          củng cố → giảm phát → ECB hạ lãi → khuyến khích tiêu dùng
          ★ nợ giảm → phần bù rủi ro giảm → vốn rẻ cho doanh nghiệp
       ❹ ĐỊNH GIÁ LẠI TÀI SẢN
          lãi thực giảm → giá tài sản tăng → lợi cho hộ GIÀU; bị trễ vì
          tài sản kém thanh khoản
       ═══════════════════════════════════════════════════════════
       TÁC ĐỘNG PHÂN PHỐI THEO CÔNG CỤ
       cắt trợ cấp BẢO HIỂM ··· trúng nhóm TRUNG LƯU (tài sản kẹt ở
                                dạng kém thanh khoản)
       cắt trợ cấp NHẮM ĐÍCH ·· trúng hộ NGHÈO, MPC cao nhất
       cắt trợ cấp phổ quát ··· cầu co ÍT hơn (hộ giàu dùng tiết kiệm)
       tăng thuế LAO ĐỘNG ····· cung lao động co, trúng hộ thu nhập
                                thấp phụ thuộc lương
       tăng thuế DOANH NGHIỆP · giảm đầu tư, giảm cổ tức của hộ giàu
```

### Kịch bản

```text
       CƠ SỞ: GIỮ NGUYÊN CHÍNH SÁCH sau 2025
       → nợ/GDP trôi lên, chênh lệch tăng dần, đầu tư bị lấn át
       ═══════════════════════════════════════════════════════════
       HAI GÓI CỦNG CỐ, cùng 1,5 điểm % GDP, 0,3 điểm/năm, 2027–31
       ┌─────────────────────────────┬──────────────┬──────────────┐
       │ (% nỗ lực)                  │ ★ ExC        │ ReC          │
       │                             │ (dựa vào chi)│ (dựa vào thu)│
       ├─────────────────────────────┼──────────────┼──────────────┤
       │ trợ cấp bảo hiểm            │ −40          │ −5           │
       │ trợ cấp khoán phổ quát      │ −40          │ −5           │
       │ tiêu dùng chính phủ         │ −30          │ −30          │
       │ trợ cấp NHẮM ĐÍCH (bù)      │ +20          │ +18          │
       │ thuế lao động               │ +5           │ +50          │
       │ thuế doanh nghiệp           │ +5           │ +28          │
       └─────────────────────────────┴──────────────┴──────────────┘
       ★ đầu tư công GIỮ NGUYÊN trong mọi kịch bản
       ★ ExC+SR = ExC + năng suất tổng hợp tăng 0,1–0,2 điểm %/năm
```

### Kết quả vĩ mô

```text
       ❶ ★★ CHI PHÍ CỦA VIỆC CHỜ ĐỢI (Hình 2, ExC+SR so với cơ sở)
       2031: nợ/GDP ~134% so với ~139% → chênh ~5 điểm %
       đầu tư tư nhân cao hơn ~0,7 điểm % trong 2027–31
       trả lãi giảm từ ~3,7% xuống ~3,4% GDP; cơ sở vẫn ~3,7%
       ⚠ bài tự cảnh báo: con số này phụ thuộc giả định về độ dốc của
         nợ trong kịch bản cơ sở, và ExC+SR gộp cả lợi ích cải cách
       ⚠ vượt một ngưỡng thì chính sách tài khoá và tiền tệ chủ động
         không thể cùng duy trì (Elenev và cộng sự 2025) → chi phí
         có thể NHẢY BẬC
       ═══════════════════════════════════════════════════════════
       ❷ ★★ THÀNH PHẦN QUAN TRỌNG (Hình 3)
       ┌─────────────────────────┬──────────────┬──────────────┐
       │                         │ ExC          │ ReC          │
       ├─────────────────────────┼──────────────┼──────────────┤
       │ sản lượng năm đầu so với│ ★ ~−0,2%     │ ~−0,25%      │
       │ giữ nguyên chính sách   │              │              │
       │ tốc độ giảm nợ          │ ★ nhanh hơn  │ chậm hơn     │
       │                         │              │ (cơ sở thuế  │
       │                         │              │  co lại)     │
       └─────────────────────────┴──────────────┴──────────────┘
       ⚠ các nước này đã có mức thuế cao → chi phí biên của tăng
         thuế nằm ở mức CAO của khoảng ước lượng
       → nếu buộc phải tăng thu: MỞ RỘNG CƠ SỞ THUẾ, cắt ưu đãi thuế,
         chống trốn thuế thay vì tăng thuế suất
       ═══════════════════════════════════════════════════════════
       ❸ ★ CHÊNH LỆCH LỢI SUẤT
       ExC: chênh lệch giảm ~50 điểm cơ bản cuối kỳ → tiết kiệm lãi
         ~0,2% GDP/năm
       → lập luận cho củng cố SỚM và ĐÁNG TIN
```

### Ai gánh chịu

```text
       NHÓM THEO THẬP PHÂN VỊ TÀI SẢN: thấp = 1 · giữa = 5 · cao = 10
       ═══════════════════════════════════════════════════════════
       ExC
       không có bù nhắm đích → tiêu dùng nhóm đáy giảm ~0,5% năm đầu
       ★ bù 20% nỗ lực vào trợ cấp nhắm đích → gần như TRIỆT TIÊU
         thiệt hại nhóm đáy (MPC ~1)
       ⚠ nhóm GIỮA gánh nặng nhất, vì trợ cấp bảo hiểm và phổ quát
         tập trung ở đây
       ReC
       thuế lao động chi phối phần giảm ở MỌI nhóm; thuế doanh nghiệp
         thêm phần nhỏ, lũy tiến, ở nhóm giàu
       ═══════════════════════════════════════════════════════════
       ★ HÌNH 6 — TIÊU DÙNG SO VỚI GIỮ NGUYÊN CHÍNH SÁCH (ước đọc)
       ┌──────────────┬─────────────────────┬─────────────────────┐
       │              │ ExC (2027 → 2031)   │ ReC (2027 → 2031)   │
       ├──────────────┼─────────────────────┼─────────────────────┤
       │ nhóm thấp    │ ~0 → ~−0,1%         │ ~0 → ~−0,14%        │
       │ nhóm giữa    │ ~−0,42 → ~−0,44%    │ ~−0,42 → ~−0,48%    │
       │ nhóm cao     │ ~−0,27 → ~−0,21%    │ ~−0,32 → ~−0,29%    │
       └──────────────┴─────────────────────┴─────────────────────┘
       ⚠ mô hình KHÔNG có biên việc làm–thất nghiệp → tác động thật
         lên nhóm đáy có thể LỚN HƠN (lao động phi chính thức, bán
         thời gian, lương thấp)
```

### Cải cách cơ cấu

```text
       ExC+SR: năng suất tổng hợp tăng 0,1–0,2 điểm %/năm
       ═══════════════════════════════════════════════════════════
       VĨ MÔ
       sản lượng vượt mức giữ nguyên chính sách từ SAU NĂM 2
       cơ sở thuế rộng ra, nợ giảm nhanh hơn, chênh lệch nén mạnh hơn
       → "biến điều chỉnh gây co hẹp thành điều chỉnh thân thiện với
          tăng trưởng"
       PHÂN PHỐI
       lương thực năm thứ 4 cao hơn ExC ~0,2%
       ★ lũy tiến: hộ HtM sống bằng lương được lợi nhiều nhất
       ★ cần ÍT trợ cấp nhắm đích hơn để bảo vệ hộ nghèo
       ═══════════════════════════════════════════════════════════
       ★ THÀNH PHẦN CẢI CÁCH CŨNG LÀ LỰA CHỌN PHÂN PHỐI
       bãi bỏ quy định trong nước · tăng năng suất NHANH nhất nhưng
         có thể ép thu nhập người lao động ngành được bảo hộ (trung lưu)
       thị trường chung EU · lợi ích lan rộng hơn nhưng chậm hơn
       nâng kỹ năng, chính sách lao động chủ động · chậm nhất nhưng
         LŨY TIẾN nhất
       IMF 2025: một gói cải cách vừa phải giảm nhu cầu điều chỉnh
         tích lũy ~1,5 điểm % GDP
```

### Kiểm tra độ vững

```text
       ❶ ĐỘ NHẠY CHÊNH LỆCH THEO NỢ η
       0,0100 và 0,0125 (Pamies và cộng sự 2021, so với Bund Đức) ·
       0,0150 (ước lượng của bài)
       → η lớn hơn: tiết kiệm lãi lớn hơn một chút, nợ giảm nhanh hơn;
         thứ hạng các kịch bản GIỮ NGUYÊN
       ❷ TỶ TRỌNG HtM
       cách 1: đo trực tiếp từ vi dữ liệu (HFCS, SCF); Arroyo–Tisnés
         2023: khác biệt giữa các nước chủ yếu do giàu HtM
       cách 2 (bài chọn): nhắm MPC bình quân, để tỷ trọng HtM tự hình
         thành → 43% HtM gồm 32% giàu và 11% nghèo
       ⚠ phân tích phân phối vì vậy có ĐIỀU KIỆN theo cách hiệu chỉnh
```

## Ba câu hỏi bài viết trả lời

1. Với một nền kinh tế nợ cao trong khu vực đồng euro, việc trì hoãn củng cố tài khoá có thực sự trung lập không?
2. Cùng một mức nỗ lực tài khoá, củng cố dựa vào chi và dựa vào thu khác nhau thế nào về sản lượng, tốc độ giảm nợ và việc ai gánh chịu?
3. Trợ cấp nhắm đích và cải cách cơ cấu giúp giảm chi phí vĩ mô và phân phối của củng cố tới mức nào?

## Khái niệm cần biết

**Củng cố tài khoá (fiscal consolidation).** Một chương trình cải thiện cán cân ngân sách trong nhiều năm để nợ công ngừng tăng hoặc giảm xuống, bằng cách cắt chi, tăng thu, hoặc cả hai. Bài so sánh hai loại: củng cố dựa vào chi (ExC) và củng cố dựa vào thu (ReC). Ví dụ trong bài: cả hai gói đều có cùng quy mô 1,5 điểm phần trăm GDP, thực hiện 0,3 điểm mỗi năm trong 2027–31. Câu hỏi của bài không phải là có củng cố hay không, mà là củng cố bằng thành phần nào thì ít hại nhất.

**Xu hướng tiêu dùng biên (marginal propensity to consume, MPC).** Phần của một đồng thu nhập tăng thêm mà một hộ đem đi tiêu ngay. Ví dụ minh hoạ: một hộ nhận thêm 100 euro và tiêu 90 euro thì MPC là 0,9; một hộ giàu nhận 100 euro và tiêu 10 euro thì MPC là 0,1. Đây là cơ chế trung tâm của bài: nếu cắt 100 euro thu nhập của hộ có MPC cao, cầu trong nền kinh tế giảm gần 100 euro; nếu cắt của hộ có MPC thấp, cầu chỉ giảm ít. Trong mô hình, MPC bình quân được hiệu chỉnh ở mức 0,44.

**Hộ "kiếm được bao nhiêu tiêu bấy nhiêu" (hand-to-mouth, HtM).** Hộ không có khoản đệm tiền mặt nào, nên mỗi khi thu nhập thay đổi thì tiêu dùng thay đổi theo gần như ngay lập tức; MPC của họ gần bằng 1. Có hai loại. Hộ nghèo HtM gần như không có tài sản. Hộ giàu HtM có tài sản, nhưng là tài sản kém thanh khoản như nhà ở hay quyền lương hưu, không rút ra tiêu được, nên vẫn tiêu theo thu nhập hiện tại. Ví dụ minh hoạ: một gia đình sở hữu căn nhà trị giá 300.000 euro nhưng chỉ có 500 euro trong tài khoản; nếu lương giảm 200 euro một tháng, họ phải cắt chi tiêu ngay. Trong mô hình, khoảng 43% hộ là HtM, trong đó 32% là giàu HtM và 11% là nghèo HtM.

**Tài sản thanh khoản và kém thanh khoản.** Tài sản thanh khoản (như tiền gửi) rút ra được bất kỳ lúc nào nhưng lãi thấp. Tài sản kém thanh khoản (như nhà, quỹ hưu) cho lãi cao hơn nhưng khó hoặc tốn kém mới chuyển thành tiền được. Ví dụ trong bài: tài sản kém thanh khoản nhận lãi suất thực đầy đủ 0,05; chênh lệch lãi giữa hai loại tài sản được hiệu chỉnh ở mức 0,09; và mỗi năm hộ chỉ có xác suất 0,15 được điều chỉnh khoản tài sản kém thanh khoản. Cấu trúc hai tài sản này là thứ sinh ra nhóm giàu HtM và khác biệt về MPC giữa các hộ.

**Mô hình HANK.** Viết tắt của "Heterogeneous Agent New Keynesian": mô hình Keynes mới (giá và lương điều chỉnh chậm, ngân hàng trung ương đặt lãi suất) nhưng có hàng nghìn loại hộ gia đình khác nhau về thu nhập và tài sản, thay vì một "hộ đại diện" duy nhất. Ví dụ minh hoạ: trong mô hình một hộ đại diện, cắt trợ cấp của người nghèo hay người giàu đều như nhau; trong HANK, hai việc đó có tác động lên tổng cầu khác hẳn nhau. Nhờ vậy bài phân tích được đồng thời tác động vĩ mô và việc ai gánh chịu.

**Số nhân tài khoá (fiscal multiplier).** Mức thay đổi của sản lượng khi chi tiêu hoặc thuế của chính phủ thay đổi một đồng. Ví dụ minh hoạ: số nhân 0,8 nghĩa là cắt 1 tỷ euro chi tiêu làm GDP giảm 0,8 tỷ euro. Trong bài, công cụ có số nhân lớn nhất là đầu tư công, nên mọi kịch bản đều giữ nguyên đầu tư công.

**Phần bù rủi ro chủ quyền và nợ nhiều kỳ hạn.** Phần bù rủi ro chủ quyền là lãi suất mà nhà đầu tư đòi thêm vì lo chính phủ không trả được nợ; trong bài nó tăng theo mức nợ vượt mức dài hạn. Nợ nhiều kỳ hạn nghĩa là chính phủ có nhiều loại trái phiếu đáo hạn ở các thời điểm khác nhau, nên khi lãi suất thị trường tăng, chỉ phần trái phiếu mới phát hành chịu lãi cao. Ví dụ minh hoạ: nếu mỗi năm chỉ 1/7 khối nợ đáo hạn và được vay lại, thì lãi suất thị trường tăng 1 điểm chỉ làm lãi bình quân trên toàn bộ nợ tăng khoảng 0,14 điểm trong năm đầu. Hai cơ chế này giúp mô hình nắm được lợi ích của việc giảm nợ qua tiết kiệm lãi.

**Quy tắc Taylor.** Một công thức mô tả cách ngân hàng trung ương đặt lãi suất: lạm phát cao hơn mục tiêu thì tăng lãi suất mạnh hơn mức tăng lạm phát. Ví dụ trong bài: hệ số với lạm phát là 1,2, tức lạm phát tăng 1 điểm thì lãi suất danh nghĩa tăng 1,2 điểm. Nhưng ECB nhìn lạm phát của cả khu vực euro, nên phản ứng với lạm phát của riêng một nước được thu nhỏ lại. Điều này quan trọng vì nó có nghĩa là khi một nước củng cố tài khoá, ECB gần như không hạ lãi suất để đỡ riêng cho nước đó.

## Nội dung chi tiết

### 1. Động cơ

**Bài toán.** Bài xét một nền kinh tế nợ cao của khu vực đồng euro, với nợ khoảng 125% GDP. Tỷ lệ nợ vẫn cao sau đại dịch và cú sốc năng lượng, và nếu không điều chỉnh sẽ tiếp tục tăng. Cùng lúc có các áp lực chi mới: dân số già, chuyển đổi xanh và chuyển đổi số, chi quốc phòng. Tăng trưởng tiềm năng thấp. Lạm phát năng lượng từ 2021 đã bào mòn thu nhập thực của hộ gia đình. Kinh tế chính trị của điều chỉnh ngày càng bị chi phối bởi mối lo về phân phối, vì các áp lực chi mới không thể đáp ứng nếu không cắt ở chỗ khác.

**Ba lý do khiến điều chỉnh khó hơn bình thường:**

1. **Tăng trưởng thấp**, nên khó "tăng trưởng để thoát nợ". Khi nợ cao, động thái của nợ rất nhạy với chênh lệch giữa tăng trưởng và lãi suất.
2. **Nợ cao khiến nhà đầu tư định giá rủi ro trượt tài khoá.** Rủi ro chủ quyền tác động vượt ra ngoài ngân sách: chênh lệch lợi suất cao làm tăng chi phí vốn của doanh nghiệp, nhất là các doanh nghiệp và ngân hàng nắm nhiều trái phiếu chính phủ, và chi phí phúc lợi dồn lên những hộ ít khả năng tự bảo hiểm nhất. Trong một liên minh tiền tệ còn có một vòng xoáy giảm phát: chênh lệch lợi suất tăng làm cầu giảm, cầu giảm làm giá giảm, nhưng ECB không bù riêng cho một nước, nên lãi suất thực vẫn cao và tình hình tài khoá xấu thêm.
3. **Hộ gia đình không đồng nhất.** Các hộ thiếu thanh khoản tiêu gần hết phần thay đổi trong thu nhập sau thuế và trợ cấp, nên việc cắt hay tăng nhắm vào ai sẽ quyết định cầu co lại bao nhiêu.

**Câu hỏi chính sách.** Khung tài khoá mới của EU cho phép giai đoạn điều chỉnh kéo dài tới 7 năm. Tốc độ điều chỉnh vì vậy là một lựa chọn chính sách bậc nhất, và câu trả lời phụ thuộc vào dấu và độ lớn của tác động của nỗ lực tài khoá lên chênh lệch lợi suất và hoạt động kinh tế. Câu hỏi cụ thể của bài: nên thiết kế thành phần của gói củng cố thế nào?

### 2. Đóng góp

**Mở rộng mô hình nền.** Bài xây trên mô hình HANK của Auclert, Rognlie và Straub (2024), giải bằng phương pháp Jacobian không gian chuỗi (một kỹ thuật tính toán cho phép giải nhanh mô hình có rất nhiều loại hộ). Bài mở rộng theo hai hướng chính:

- **Nhiều công cụ tài khoá giống ngân sách thật**: thuế lao động, thuế doanh nghiệp, ba loại trợ cấp, tiêu dùng và đầu tư công, thay vì các cú sốc chi tiêu hay thuế cách điệu.
- **Phần bù rủi ro chủ quyền nội sinh**, tăng theo tỷ lệ nợ (theo Langot và cộng sự, 2025).

Ngoài ra, nợ có cấu trúc nhiều kỳ hạn, nên thay đổi của chênh lệch lợi suất chỉ truyền dần vào chi phí lãi. Quy tắc Taylor được thu nhỏ để phản ánh nhiệm vụ toàn khu vực của ECB.

**Cơ chế truyền dẫn trung tâm** là sự khác biệt về xu hướng tiêu dùng biên giữa các hộ, sinh ra một cách nội sinh từ cấu trúc hai tài sản. Mô hình tái tạo được ba sự thật thực nghiệm: nhiều hộ có tài sản kém thanh khoản nhưng ít tiền mặt; xu hướng tiêu dùng biên cao đối với thu nhập tạm thời; và một số lượng đáng kể hộ đang chạm ràng buộc thanh khoản.

### 3. Mô hình

**Hộ gia đình.** Mỗi hộ chọn mức tiêu dùng, số giờ lao động và cách phân bổ tiết kiệm giữa hai tài khoản:

| Tài khoản | Đặc điểm |
|---|---|
| Tài sản thanh khoản | rút bất kỳ lúc nào, nhưng lãi thấp hơn vì trung gian thu một khoản phí (ký hiệu ζ) |
| Tài sản kém thanh khoản | nhận lãi đầy đủ r, nhưng mỗi kỳ chỉ được điều chỉnh với xác suất ν |

Cấu trúc này sinh ra hai nhóm HtM: nhóm nghèo HtM gần như không có tài sản, và nhóm giàu HtM có tài sản kém thanh khoản (nhà, lương hưu) nhưng không có tiền mặt nên vẫn tiêu theo thu nhập. Hộ không được vay. Thuế thu nhập luỹ tiến theo dạng Heathcote–Storesletten–Violante. Năng suất của mỗi cá nhân thay đổi ngẫu nhiên theo một chuỗi Markov có 11 mức (nút).

**Công cụ tài khoá:**

| Phía | Công cụ |
|---|---|
| Thu | thuế lao động; thuế doanh nghiệp; thuế khoán (công cụ cân đối, phản ứng theo nợ) |
| Chi | trợ cấp bảo hiểm (lương hưu có đóng góp, trợ cấp thất nghiệp); trợ cấp khoán phổ quát (mọi hộ nhận như nhau); trợ cấp nhắm đích (chia đều cho 4 thập phân vị năng suất thấp nhất); tiêu dùng chính phủ; đầu tư công (đi vào hàm sản xuất) |

Thuế khoán là công cụ cân đối: nó phản ứng theo nợ để giữ tỷ lệ nợ ổn định trong dài hạn, mà không làm méo quyết định lao động hay tiết kiệm của hộ.

**Doanh nghiệp.** Doanh nghiệp sản xuất bằng vốn công, vốn tư và lao động. Vốn tư chịu chi phí điều chỉnh bậc hai (thay đổi càng nhanh càng tốn). Giá và lương chịu chi phí điều chỉnh kiểu Rotemberg, tương đương với kiểu Calvo ở mức xấp xỉ bậc một; nói đơn giản là giá và lương điều chỉnh chậm.

**Lãi suất và nợ.** Lãi suất thực phụ thuộc vào lãi suất danh nghĩa, phần bù rủi ro và thuế doanh nghiệp hiệu dụng. Ba phần mở rộng quan trọng:

- **Phần bù rủi ro** bằng η nhân với khoảng cách giữa tỷ lệ nợ trên GDP hiện tại và tỷ lệ nợ dài hạn.
- **Nợ nhiều kỳ hạn:** coupon bình quân chỉ điều chỉnh dần khi trái phiếu cũ đáo hạn và được tái cấp vốn. Vì vậy khi kỳ hạn dài, chênh lệch lợi suất nới rộng đột ngột làm tăng chi phí của các đợt phát hành mới, nhưng ít ảnh hưởng tới tổng chi phí lãi ngay lập tức.
- **Quy tắc Taylor:** hệ số với lạm phát trong nước được thu nhỏ, vì ECB nhìn lạm phát của toàn khu vực.

**Hiệu chỉnh.** Nền kinh tế đại diện là bình quân gia quyền theo GDP của Bỉ, Pháp và Ý. Hy Lạp bị loại vì thu ngân sách thấp, Tây Ban Nha bị loại vì tăng trưởng cao, đều không đại diện. Các tham số chính:

| Tham số | Giá trị | Nguồn hoặc mục tiêu |
|---|---|---|
| Hệ số chiết khấu β | 0,94 | khớp tỷ lệ tài sản trên GDP |
| Độ co giãn Frisch của cung lao động | 0,5 | |
| Chênh lệch lãi giữa tài sản kém thanh khoản và thanh khoản | 0,09 | khớp MPC bình quân = 0,44 |
| Xác suất điều chỉnh ν | 0,15 | khớp MPC bình quân = 0,44 |
| Lãi suất thực r | 0,05 | Auclert và cộng sự 2024 |
| Tỷ phần vốn α | 0,4219 | Penn World Table |
| Độ dốc đường Phillips của giá và của lương | 0,22 và 0,10 | Auclert và cộng sự 2024 |
| Hệ số Taylor | 1,2 | Langot và cộng sự 2025 |
| Độ nhạy của chênh lệch lợi suất theo nợ η | 0,0077 | Langot và cộng sự 2025 |
| Nợ trên GDP | 1,25 | Eurostat, quý 3/2025 |
| Tiêu dùng chính phủ trên GDP | 0,21 | Ngân hàng Thế giới |

**So sánh với dữ liệu ở những đại lượng không nhắm tới:**

| Đại lượng | Mô hình | Dữ liệu |
|---|---|---|
| Tỷ trọng hộ HtM | 0,438 | khoảng 0,22 |
| Tỷ trọng hộ giàu HtM | 0,324 | khoảng 0,17 |
| Tỷ trọng hộ có tài sản thanh khoản không quá 10% thu nhập | 0,638 | không có số liệu |
| Hệ số Gini tài sản | 0,845 | khoảng 0,67 |
| Tỷ phần tài sản của 10% giàu nhất | 0,798 | khoảng 0,52 |

Mô hình dự báo quá cao cả tỷ trọng hộ HtM lẫn mức bất bình đẳng tài sản. Bài biện hộ rằng họ nhắm vào MPC bình quân vì đó là thống kê đủ cho động thái của các biến tổng (theo Debortoli và Galí 2024, Bilbiie 2020).

**Bốn kênh truyền dẫn của củng cố:**

1. **Chi tiêu chính phủ.** Cắt tiêu dùng công làm cầu giảm tương đương với khoản cắt, không phụ thuộc vào MPC. Cắt đầu tư công vừa giảm cầu ngắn hạn vừa bào mòn vốn công, kéo tụt sản lượng tiềm năng, nên có số nhân lớn nhất.
2. **Thu nhập khả dụng.** Thay đổi trực tiếp qua thuế và trợ cấp, gián tiếp qua lương và việc làm. Nếu phần giảm rơi vào hộ HtM (kể cả giàu HtM), cầu co mạnh hơn.
3. **Lãi suất.** Củng cố gây áp lực giảm phát, ECB hạ lãi suất phần nào, khuyến khích tiêu dùng. Nợ giảm làm phần bù rủi ro giảm, giúp doanh nghiệp vay vốn rẻ hơn.
4. **Định giá lại tài sản.** Lãi suất thực giảm làm giá tài sản tăng, có lợi cho hộ giàu; tác động này bị trễ vì tài sản kém thanh khoản.

**Tác động phân phối của từng công cụ:**

| Công cụ | Ai chịu |
|---|---|
| Cắt trợ cấp bảo hiểm | nhóm trung lưu, vì tài sản của họ kẹt ở dạng kém thanh khoản |
| Cắt trợ cấp nhắm đích | hộ nghèo, nhóm có MPC cao nhất |
| Cắt trợ cấp phổ quát | cầu co ít hơn, vì hộ giàu dùng tiết kiệm để bù |
| Tăng thuế lao động | cung lao động co lại; trúng hộ thu nhập thấp phụ thuộc vào lương |
| Tăng thuế doanh nghiệp | giảm đầu tư, giảm cổ tức của hộ giàu |

### 4. Trạng thái dừng

Ở trạng thái cân bằng dài hạn của mô hình, khoảng 43% hộ là HtM, trong đó 32% là giàu HtM và 11% là nghèo HtM. Xu hướng tiêu dùng biên gần bằng một ở nhóm đáy; vẫn cao ở nhóm giữa, vì tài sản của họ chủ yếu là tài sản kém thanh khoản; và thấp ở nhóm giàu, những người nắm phần lớn tài sản.

Tài sản thanh khoản thấp tập trung ở nhóm thu nhập thấp và trung bình. Vì vậy, việc chọn công cụ tài khoá theo đối tượng chịu tác động là rất quan trọng: cùng một khoản cắt giảm có thể làm cầu co mạnh hay yếu tuỳ nó rơi vào ai.

### 5. Chi phí của việc chờ đợi

**Kịch bản cơ sở: giữ nguyên chính sách sau 2025.** Thâm hụt tiếp tục mở rộng khi tiền trả lãi tăng; phần bù rủi ro nới rộng và làm nợ tích luỹ nhanh hơn, tạo thành một vòng lặp tài khoá–tài chính tự củng cố. Đầu tư tư nhân bị lấn át qua thị trường tài sản, vì nợ công hút tiết kiệm của hộ; lương thực bị bào mòn. Như bài viết, giữ nguyên hiện trạng không phải là trung lập: trì hoãn điều chỉnh tự nó gây chi phí dưới dạng đầu tư thấp hơn, gánh nặng trả nợ cao hơn và thiệt hại phân phối cho các hộ bị ràng buộc.

**Hai gói củng cố** có cùng quy mô 1,5 điểm phần trăm GDP, thực hiện 0,3 điểm mỗi năm trong 2027–31. Thành phần (tính bằng % của tổng nỗ lực; dấu âm là cắt chi, dấu dương ở trợ cấp nhắm đích là khoản bù, ở thuế là tăng thuế):

| Hạng mục | ExC (dựa vào chi) | ReC (dựa vào thu) |
|---|---|---|
| Trợ cấp bảo hiểm | −40 | −5 |
| Trợ cấp khoán phổ quát | −40 | −5 |
| Tiêu dùng chính phủ | −30 | −30 |
| Trợ cấp nhắm đích (bù) | +20 | +18 |
| Thuế lao động | +5 | +50 |
| Thuế doanh nghiệp | +5 | +28 |

Đầu tư công được giữ nguyên trong mọi kịch bản. Kịch bản thứ ba, ExC+SR, là ExC cộng thêm cải cách cơ cấu làm năng suất tổng hợp tăng 0,1–0,2 điểm phần trăm mỗi năm.

**Chi phí của việc chờ** (so sánh ExC+SR với kịch bản cơ sở; ước đọc từ biểu đồ):

| Chỉ tiêu | ExC+SR | Giữ nguyên chính sách |
|---|---|---|
| Nợ trên GDP năm 2031 | khoảng 134% | khoảng 139% (chênh khoảng 5 điểm phần trăm) |
| Đầu tư tư nhân 2027–31 | cao hơn khoảng 0,7 điểm phần trăm | |
| Chi trả lãi | giảm từ khoảng 3,7% xuống khoảng 3,4% GDP | vẫn khoảng 3,7% GDP |

**Hai lưu ý của chính bài.** Thứ nhất, độ lớn của chi phí phụ thuộc vào giả định về độ dốc của nợ trong kịch bản cơ sở. Thứ hai, so sánh với ExC+SR phóng đại khác biệt, vì nó gộp cả lợi ích từ cải cách năng suất. Tuy vậy, kết luận định tính rằng trì hoãn là tốn kém vẫn đúng khi so ExC và ReC thuần với kịch bản cơ sở.

Bài còn dẫn kết quả của Elenev và cộng sự (2025): khi nợ vượt một ngưỡng nhất định, chính sách tài khoá chủ động và chính sách tiền tệ chủ động không thể cùng duy trì. Khi đó chi phí của việc chờ có thể nhảy bậc chứ không tăng dần.

### 6. Thành phần của củng cố

**Kết quả về sản lượng và nợ:**

| | ExC | ReC |
|---|---|---|
| Sản lượng năm đầu so với giữ nguyên chính sách | khoảng −0,2% | khoảng −0,25% |
| Tốc độ giảm nợ | nhanh hơn | chậm hơn, vì cơ sở thuế co lại |

**Vì sao ExC giảm nợ nhanh hơn.** Cắt chi cải thiện trực tiếp cán cân sơ cấp. Với ReC, thuế cao hơn làm hoạt động kinh tế yếu đi và thu hẹp cơ sở thuế, nên một phần số thu dự tính không thành hiện thực.

**Vì sao số nhân của ExC nhỏ hơn.** Một phần trợ cấp bị cắt rơi vào các hộ không bị ràng buộc thanh khoản, những hộ có thể dùng tiết kiệm để giữ mức tiêu dùng. Ngược lại, thuế lao động làm thu nhập co lại trên diện rộng, trong một nền kinh tế có nhiều hộ HtM tiêu gần hết thu nhập, nên cầu giảm mạnh hơn. Thêm vào đó, các nước này đã có mức thuế cao, nên chi phí biên của việc tăng thuế thêm nằm ở mức cao của khoảng ước lượng. Nếu buộc phải tăng thu, bài khuyên mở rộng cơ sở thuế, cắt ưu đãi thuế và chống trốn thuế, thay vì tăng thuế suất.

**Tiết kiệm lãi nhờ chênh lệch lợi suất giảm.** Dưới ExC, chênh lệch lợi suất giảm khoảng 50 điểm cơ bản (0,5 điểm phần trăm) vào cuối kỳ, giúp tiết kiệm tiền lãi khoảng 0,2% GDP mỗi năm. Hiệu ứng này vắng mặt trong các mô hình giả định chênh lệch lợi suất cố định. Đây là lập luận cho một cuộc củng cố sớm và đáng tin.

### 7. Phân phối

Bài chia hộ theo thập phân vị tài sản và báo cáo ba nhóm: nhóm thấp (thập phân vị 1), nhóm giữa (thập phân vị 5) và nhóm cao (thập phân vị 10).

**Dưới ExC.** Nếu không có khoản bù nhắm đích, việc cắt trợ cấp bảo hiểm và trợ cấp phổ quát rơi nặng lên hộ thu nhập thấp và trung bình, những hộ nhận khoảng 60% tổng trợ cấp; tiêu dùng của nhóm đáy giảm khoảng 0,5% ngay năm đầu. Nhưng khi dành 20% nỗ lực để tăng trợ cấp nhắm đích, thiệt hại của nhóm đáy gần như bị triệt tiêu, vì người nhận có MPC gần bằng 1: mỗi đồng bù quay lại thành cầu gần như ngay lập tức. Như bài kết luận, bảo trợ xã hội nhắm đúng không chỉ công bằng mà còn hiệu quả về vĩ mô. Nhóm giữa chịu mức giảm lớn nhất, vì trợ cấp bảo hiểm và trợ cấp phổ quát tập trung ở nhóm này.

**Dưới ReC.** Thuế lao động chi phối phần giảm tiêu dùng ở mọi nhóm; thuế doanh nghiệp thêm một phần nhỏ, có tính luỹ tiến, ở nhóm giàu. Tác động của thuế doanh nghiệp lên nhóm giàu bị giảm và trễ vì tài sản của họ kém thanh khoản. Gánh nặng trải đều hơn giữa các nhóm, nhưng tổng mức giảm tiêu dùng sâu hơn.

**Tiêu dùng so với giữ nguyên chính sách** (ước đọc từ biểu đồ, năm 2027 và năm 2031):

| Nhóm | ExC: 2027 → 2031 | ReC: 2027 → 2031 |
|---|---|---|
| Nhóm thấp | khoảng 0 → khoảng −0,1% | khoảng 0 → khoảng −0,14% |
| Nhóm giữa | khoảng −0,42 → khoảng −0,44% | khoảng −0,42 → khoảng −0,48% |
| Nhóm cao | khoảng −0,27 → khoảng −0,21% | khoảng −0,32 → khoảng −0,29% |

Ở cả hai gói, nhóm giữa chịu nặng nhất; gói ReC làm mọi nhóm thiệt hơn gói ExC.

**Phân phối không phải tác dụng phụ.** Bài nhấn mạnh rằng tác động phân phối không chỉ là một hệ quả cần giảm nhẹ, mà quay lại tác động lên tổng cầu: cắt vào nhóm có MPC cao thì cầu co mạnh hơn. Lựa chọn con đường củng cố cũng là lựa chọn về việc ai gánh chi phí. Hạn chế: mô hình không có biên việc làm–thất nghiệp (người lao động chỉ làm nhiều hay ít giờ, không mất việc), nên tác động thật lên nhóm đáy, gồm lao động phi chính thức, bán thời gian và lương thấp, có thể lớn hơn.

### 8. Cải cách cơ cấu

**Kịch bản ExC+SR.** Củng cố dựa vào chi, cộng thêm cải cách làm năng suất tổng hợp tăng 0,1–0,2 điểm phần trăm mỗi năm.

**Tác động vĩ mô.** Năng suất cao hơn nâng sản phẩm biên của lao động và vốn, hỗ trợ đầu tư và khôi phục lương thực. Sản lượng vượt mức giữ nguyên chính sách từ sau năm thứ 2. Cơ sở thuế rộng ra, nợ giảm nhanh hơn và chênh lệch lợi suất bị nén mạnh hơn. Cải cách vì vậy biến một cuộc điều chỉnh gây co hẹp thành một cuộc điều chỉnh thân thiện với tăng trưởng. Theo IMF (2025), một gói cải cách vừa phải có thể giảm nhu cầu điều chỉnh tài khoá tích luỹ khoảng 1,5 điểm phần trăm GDP.

**Tác động phân phối.** Lương thực vào năm thứ 4 cao hơn kịch bản ExC khoảng 0,2%. Lợi ích có tính luỹ tiến, vì kênh lương tác động mạnh hơn ở nhóm đáy: các hộ HtM sống bằng lương được lợi nhiều nhất. Nhờ vậy cần ít trợ cấp nhắm đích hơn để bảo vệ hộ nghèo.

**Loại cải cách cũng là lựa chọn phân phối:**

| Loại cải cách | Tốc độ | Ai được, ai mất |
|---|---|---|
| Bãi bỏ quy định trong nước | tăng năng suất nhanh nhất | có thể ép thu nhập của người lao động trong các ngành được bảo hộ, chủ yếu là trung lưu |
| Hội nhập thị trường chung EU | chậm hơn | lợi ích lan rộng hơn |
| Nâng kỹ năng, chính sách lao động chủ động | chậm nhất | luỹ tiến nhất |

Một gói nghiêng về thị trường chung và nâng kỹ năng sẽ luỹ tiến hơn một gói dựa chủ yếu vào bãi bỏ quy định trong nước.

**Kiểm tra độ vững.** Bài kiểm tra hai giả định quan trọng:

- **Độ nhạy của chênh lệch lợi suất theo nợ η.** Ngoài mức cơ sở 0,0077, bài thử 0,0100 và 0,0125 (theo Pamies và cộng sự 2021, so với trái phiếu Bund của Đức) và 0,0150 (ước lượng của chính bài). Với η lớn hơn, tiết kiệm lãi lớn hơn một chút và nợ giảm nhanh hơn, nhưng thứ hạng các kịch bản giữ nguyên.
- **Tỷ trọng hộ HtM.** Có hai cách hiệu chỉnh. Cách thứ nhất đo trực tiếp từ vi dữ liệu khảo sát hộ gia đình (HFCS của khu vực euro, SCF của Mỹ); theo Arroyo và Tisnés (2023), khác biệt giữa các nước chủ yếu do nhóm giàu HtM. Cách thứ hai, bài chọn, là nhắm vào MPC bình quân và để tỷ trọng HtM tự hình thành, cho ra 43% HtM gồm 32% giàu và 11% nghèo. Vì vậy các kết quả phân tích phân phối là có điều kiện, phụ thuộc vào cách hiệu chỉnh này.

### 9. Hàm ý thiết kế

- **Hành động ngay rẻ hơn chờ đợi.** Cam kết một lộ trình bền vững nhiều năm, thay vì điều chỉnh tuỳ ý hằng năm, mới tạo ra hiệu ứng kỳ vọng giúp nén chênh lệch lợi suất.
- **Thành phần tiết kiệm chi quan trọng ngang quy mô.** Loại bỏ trợ cấp kém hiệu quả, hay cải cách các khoản trợ cấp phổ quát nhắm kém, ít tốn kém về cầu hơn.
- **Bảo vệ đầu tư công**, để giữ tính bổ trợ giữa vốn công và vốn tư: đường sá, hạ tầng tốt làm vốn tư nhân sinh lợi hơn.
- **Một hệ thống bảo trợ có thể mở rộng trợ cấp nhắm đích nhanh** là bổ sung then chốt cho mọi gói củng cố.
- **Khi bất bình đẳng cao, tính bền vững của nợ phụ thuộc vào phân phối tài sản.** Một cuộc điều chỉnh để các hộ bị ràng buộc thanh khoản chịu tổn thất quá lớn sẽ làm suy yếu chính khả năng thực hiện kế hoạch, cả về kinh tế lẫn chính trị.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| HANK | Mô hình Keynes mới với hộ gia đình không đồng nhất |
| Fiscal consolidation | Củng cố tài khoá, cải thiện cán cân để giảm nợ |
| Expenditure-based consolidation (ExC) | Củng cố dựa vào cắt chi |
| Revenue-based consolidation (ReC) | Củng cố dựa vào tăng thu |
| Structural reforms (SR) | Cải cách cơ cấu nâng năng suất |
| Hand-to-mouth (HtM) | Hộ kiếm được bao nhiêu tiêu bấy nhiêu |
| Wealthy hand-to-mouth | Hộ có tài sản kém thanh khoản nhưng thiếu tiền mặt |
| Marginal propensity to consume (MPC) | Xu hướng tiêu dùng biên |
| Liquid, illiquid assets | Tài sản thanh khoản và kém thanh khoản |
| Calvo-style portfolio friction | Ma sát điều chỉnh danh mục ngẫu nhiên kiểu Calvo |
| Sovereign risk premium | Phần bù rủi ro chủ quyền |
| Coupon smoothing | Làm mượt coupon khi nợ được tái cấp vốn dần |
| Sequence-space Jacobian | Phương pháp Jacobian không gian chuỗi |
| Insurance-based transfers | Trợ cấp bảo hiểm: lương hưu đóng góp, trợ cấp thất nghiệp |
| Targeted transfers | Trợ cấp nhắm đích cho hộ thu nhập thấp |
| Lump-sum transfers | Trợ cấp khoán phổ quát |
| Crowding out | Lấn át đầu tư tư nhân |
| Doom loop | Vòng xoáy tự củng cố giữa nợ, chênh lệch và cầu |
| Austerity threshold | Ngưỡng thắt lưng buộc bụng |
| Base-broadening | Mở rộng cơ sở thuế |
| Tax expenditures | Ưu đãi thuế, chi tiêu qua hệ thống thuế |
| Untargeted moments | Thời điểm thống kê không được nhắm khi hiệu chỉnh |

## Câu nói đáng nhớ

> "The status quo is not neutral: delaying adjustment generates its own costs in the form of lower investment, higher debt-service burdens, and distributional damage to constrained households."

> "Well-targeted social protection is not just equitable—it is macroeconomically efficient."

> "The choice of consolidation path is also a choice about the distribution of who bears its cost."

## Đánh giá và phát hiện đáng chú ý

### Kết quả được đưa lên đầu lại là kết quả mô hình không phân biệt nổi

Kết luận thứ hai trong phần tóm tắt — củng cố dựa vào chi làm sản lượng năm đầu giảm khoảng **0,2%**, ít hơn mức **0,25%** của củng cố dựa vào thu — là con số sẽ được trích dẫn nhiều nhất. Cần nhìn kỹ độ lớn của nó.

Khác biệt là **0,05 điểm phần trăm sản lượng**, cho một nỗ lực điều chỉnh 1,5 điểm phần trăm GDP trải qua năm năm, tính từ một mô hình được hiệu chỉnh. Năm điểm cơ bản.

Đặt con số đó cạnh những gì bài tự công bố về độ chính xác của hiệu chỉnh thì nó không còn nhiều ý nghĩa. Tỷ trọng hộ "kiếm được bao nhiêu tiêu bấy nhiêu" trong mô hình là **43,8%** so với khoảng **22%** trong dữ liệu — cao gấp đôi. Tỷ trọng hộ giàu thuộc nhóm này là **32,4%** so với khoảng **17%**. Hệ số Gini tài sản là **0,845** so với khoảng **0,67**. Nhóm 10% giàu nhất nắm **79,8%** tài sản trong mô hình so với khoảng **52%** trong thực tế.

Một mô hình lệch tới mức đó ở các đại lượng quyết định độ lớn của số nhân tài khoá thì không thể phân giải được một khác biệt 0,05 điểm phần trăm. Cách đọc trung thực là: **mô hình không phân biệt được hai loại củng cố về mặt tác động lên tổng sản lượng**, và thứ hạng giữa chúng nên được coi là gợi ý về hướng, không phải một ước lượng.

Điều này không làm hỏng bài, vì đóng góp thật của nó nằm ở chỗ khác.

### Trợ cấp nhắm đích cứu nhóm đáy, và dồn toàn bộ chi phí lên nhóm giữa

Kết quả đáng giá nhất — và là lý do biện minh cho toàn bộ bộ máy HANK — là: dành **20% nỗ lực củng cố** cho trợ cấp nhắm đích **gần như triệt tiêu hoàn toàn thiệt hại tiêu dùng ở nhóm đáy**, với chi phí rất thấp.

Cơ chế thì đơn giản nhưng chỉ tồn tại trong một mô hình có hộ gia đình không đồng nhất: nhóm đáy có xu hướng tiêu dùng biên gần bằng **1**. Mỗi đồng chuyển tới họ quay lại thành cầu gần như toàn bộ, trong cùng kỳ. Một đồng cắt từ họ cũng rút khỏi cầu gần như toàn bộ.

Từ đó ra câu có sức nặng nhất trong bài: **bảo trợ xã hội nhắm đúng không chỉ công bằng mà còn hiệu quả về vĩ mô.** Đây không phải một lời kêu gọi đạo đức được gắn thêm vào một phân tích kỹ thuật; nó là một kết quả của chính phân tích đó. Trong một mô hình đại diện với một hộ gia đình duy nhất, mệnh đề này thậm chí không phát biểu được.

Hệ quả thiết kế rất cụ thể: nếu buộc phải củng cố, khoản chi **cuối cùng** nên bị cắt là khoản chi tới tay nhóm có xu hướng tiêu dùng biên cao nhất — vì cắt ở đó vừa đắt nhất về phúc lợi vừa đắt nhất về sản lượng. Hai tiêu chí trùng nhau, điều hiếm gặp trong kinh tế học tài khoá.

Đây là điều bài ghi nhận trong một dòng và không khai thác, dù nó quyết định liệu kế hoạch có thực hiện được hay không.

Dưới kịch bản củng cố dựa vào chi có kèm bù nhắm đích, con số tiêu dùng so với giữ nguyên chính sách vào năm 2031 là: nhóm thấp khoảng **−0,1%**, nhóm cao khoảng **−0,21%**, và **nhóm giữa khoảng −0,44%** — gấp hơn bốn lần nhóm đáy và gấp đôi nhóm đỉnh.

Lý do nằm ngay trong cấu trúc của gói: nỗ lực được lấy chủ yếu từ **trợ cấp bảo hiểm** (lương hưu đóng góp, trợ cấp thất nghiệp) và **trợ cấp khoán phổ quát**, mỗi loại 40% nỗ lực. Và cả hai loại này đều tập trung ở nhóm giữa. Nhóm này cũng chính là nhóm mà bài gọi là **hộ giàu "kiếm được bao nhiêu tiêu bấy nhiêu"**: có tài sản, nhưng là tài sản kém thanh khoản như nhà ở và quyền hưu trí, nên vẫn tiêu theo thu nhập hiện tại và vẫn có xu hướng tiêu dùng biên cao.

Nói thẳng ra: **phương án được mô hình đánh giá là tối ưu lại là phương án đánh trúng cử tri trung vị**. Đó là cấu hình chính trị khó thực hiện nhất có thể hình dung, và nó giải thích vì sao các cuộc cải cách lương hưu ở đúng ba nước được dùng để hiệu chỉnh mô hình này — Bỉ, Pháp, Ý — lại là các cuộc cải cách khó khăn nhất trong chính trị châu Âu.

Bài kết luận rằng lựa chọn con đường củng cố cũng là lựa chọn về việc ai gánh chi phí. Đúng. Nhưng nó dừng lại trước bước tiếp theo: **ai gánh chi phí cũng quyết định con đường đó có đi được hay không**.

### Hai khiếm khuyết của mô hình đẩy kết luận về cùng một hướng

Bài rất trung thực về giới hạn của mình, và đáng khen. Nhưng đáng làm rõ rằng hai giới hạn lớn nhất không triệt tiêu nhau mà **cùng làm kết luận chính có vẻ mạnh hơn thực tế**.

**Thứ nhất, mô hình quá nhiều hộ bị ràng buộc thanh khoản.** Với 43,8% thay vì 22%, số người có xu hướng tiêu dùng biên gần 1 lớn gấp đôi thực tế. Điều đó vừa **phóng đại hiệu lực của trợ cấp nhắm đích** (mỗi đồng chuyển đi tạo ra nhiều cầu hơn thực tế) vừa **phóng đại chi phí của củng cố dựa vào thuế lao động** (nhiều người không thể làm mượt tiêu dùng hơn thực tế). Cả hai đều là kết luận trung tâm của bài.

Lời biện hộ — nhắm vào xu hướng tiêu dùng biên bình quân vì đó là thống kê đủ cho động thái tổng — hợp lệ **cho các đại lượng tổng**. Nhưng đóng góp chính của bài là **phân tích phân phối**, và với phân tích phân phối thì chính phân phối là đối tượng cần đo, không phải một tham số phiền toái cần trung hoà. Một thống kê đủ cho tổng không phải là thống kê đủ cho phân phối. Bài thừa nhận điều này ở phần kiểm tra độ vững, trong khi các kết quả phân phối nằm ở phần tóm tắt.

**Thứ hai, mô hình không có biên việc làm–thất nghiệp.** Bài nêu điều này và nói tác động thật lên nhóm đáy có thể lớn hơn. Nhưng với một bài về chi phí phân phối của thắt lưng buộc bụng ở khu vực đồng euro, đây không phải một thiếu sót nhỏ. Kinh nghiệm thực tế của các đợt điều chỉnh trong khu vực euro giai đoạn 2010–2014 là chi phí đến **áp đảo qua thất nghiệp**, không qua mức lương và mức trợ cấp. Một mô hình chỉ có biên cường độ lao động sẽ đánh giá thấp một cách có hệ thống thiệt hại của nhóm đáy — và do đó làm cho khoản bù nhắm đích trông **đủ** trong khi thực tế có thể không.

Hai khiếm khuyết này đi theo hai hướng khác nhau về tỷ trọng hộ bị ràng buộc, nhưng cùng một hướng về kết luận: **trợ cấp nhắm đích trông rẻ hơn và hiệu quả hơn so với thực tế**.

### "Chi phí của việc chờ đợi", và chế độ tiền tệ đã tạo ra nó

Con số được nhấn mạnh nhất về mặt chính sách — nợ ở mức 134% GDP so với 139% vào năm 2031, chênh khoảng 5 điểm — được tính bằng cách so kịch bản **ExC+SR** với kịch bản giữ nguyên chính sách.

Nhưng ExC+SR gộp cả **cải cách cơ cấu nâng năng suất tổng hợp 0,1–0,2 điểm phần trăm mỗi năm** — một thứ hoàn toàn không liên quan gì tới việc củng cố sớm hay muộn. Một nước có thể làm cải cách cơ cấu mà không củng cố, hoặc củng cố mà không cải cách. Gộp chúng lại rồi gọi hiệu số là "chi phí của việc chờ đợi" là một phép so sánh thổi phồng.

Bài tự nêu cảnh báo này, và đó là thực hành tốt. Nhưng con số 5 điểm sẽ được trích dẫn mà không kèm cảnh báo, vì con số luôn sống lâu hơn dấu hoa thị đi kèm nó.

Điều đáng chú ý là lập luận **mạnh hơn** cho việc hành động sớm lại nằm ở một dòng phụ: dẫn chiếu tới kết quả rằng vượt qua một ngưỡng nhất định, chính sách tài khoá chủ động và chính sách tiền tệ chủ động **không thể cùng duy trì**, nên chi phí có thể **nhảy bậc** chứ không tăng dần.

Đó mới là lý do thuyết phục để không chờ: không phải vì chi phí của việc chờ tăng đều 5 điểm, mà vì **có thể tồn tại một vách đá**. Bài nhắc tới nó và không mô hình hoá nó.

Vòng xoáy mà bài mô tả cần được đọc kỹ vì nó quyết định phạm vi áp dụng của toàn bộ kết luận: chênh lệch lợi suất tăng → cầu trong nước giảm → giá giảm → **Ngân hàng Trung ương châu Âu không bù riêng cho một nước** → lãi suất thực vẫn cao → tình hình tài khoá xấu thêm.

Mắt xích quyết định là mắt xích thứ ba, và nó **chỉ tồn tại trong một liên minh tiền tệ**. Một nước có đồng tiền riêng và tỷ giá linh hoạt không đối mặt với vòng xoáy này: ngân hàng trung ương của nó có thể hạ lãi suất để bù, và đồng tiền mất giá tạo ra một kênh hỗ trợ cầu bên ngoài mà một thành viên khu vực euro không có.

Nghĩa là sự cấp bách của bài — hành động ngay, vì chờ đợi có chi phí tự nó — là hàm của **chế độ tiền tệ**, không phải của mức nợ. Áp thẳng kết luận này cho một nước ngoài liên minh tiền tệ là một sai lầm về phạm vi.

Điều này cũng giải thích một kết quả khác trong bài: quy tắc Taylor được thu nhỏ vì Ngân hàng Trung ương châu Âu nhìn lạm phát toàn khu vực. Nói cách khác, mô hình được xây trên giả định rằng **chính sách tiền tệ không phản ứng với tình trạng của nước đang xét**, và đó là giả định tạo ra phần lớn cái giá của củng cố trong mô hình.

### Thành phần của cải cách cơ cấu cũng là một lựa chọn phân phối, và nó có thể cộng dồn tai hại

Phần về cải cách cơ cấu chứa một phân loại rất hữu ích mà bài để ở cuối: **bãi bỏ quy định trong nước** nâng năng suất nhanh nhất nhưng có thể ép thu nhập của người lao động trong các ngành được bảo hộ; **hội nhập thị trường chung** lan toả rộng hơn nhưng chậm hơn; **nâng kỹ năng và chính sách lao động chủ động** chậm nhất nhưng **luỹ tiến nhất**.

Ghép với kết quả phân phối của phần củng cố thì hiện ra một rủi ro cộng dồn. Củng cố dựa vào chi đã dồn gánh nặng lên nhóm giữa. Bãi bỏ quy định trong nước cũng đánh vào nhóm giữa — người lao động trong các ngành được bảo hộ chính là nhóm đó. Thực hiện đồng thời hai chương trình này nghĩa là **toàn bộ chi phí của cả gói, trong cả hai chiều, rơi lên cùng một nhóm dân cư**.

Trong khi đó bài cũng cho thấy cải cách cơ cấu có tính luỹ tiến theo kênh lương — lương thực năm thứ tư cao hơn khoảng 0,2% so với kịch bản không cải cách, và hộ sống bằng lương được lợi nhiều nhất, nên **cần ít trợ cấp nhắm đích hơn để bảo vệ hộ nghèo**. Đây là một kết quả đẹp: cải cách đúng loại làm giảm nhu cầu bù đắp.

Kết hợp hai điều trên cho một thứ tự ưu tiên rõ ràng: **ưu tiên loại cải cách có tác động luỹ tiến qua kênh lương, vì nó vừa nâng năng suất vừa tự tài trợ cho phần bảo vệ xã hội**, thay vì loại cải cách nhanh nhất về năng suất nhưng tập trung chi phí vào cùng nhóm đang gánh phần lớn cuộc củng cố.

### Với Việt Nam: mô hình không chuyển giao được, nhưng ba cơ chế thì có

Đây là mô hình cho một nền kinh tế nợ 125% GDP, trong liên minh tiền tệ, với mức thuế đã rất cao và hệ thống bảo trợ xã hội phổ quát. Không một con số nào trong bài áp dụng được cho Việt Nam. Ba cơ chế thì có.

**Thứ nhất, và quan trọng nhất: bài này làm được điều mà nhánh tài liệu khác về củng cố tài khoá trong cùng thư mục không làm được — nó tách riêng đầu tư công.** Mô hình **giữ nguyên đầu tư công trong mọi kịch bản**, và lý do được nêu rõ: cắt đầu tư công vừa giảm cầu ngắn hạn vừa bào mòn vốn công và kéo tụt sản lượng tiềm năng, nên nó có **số nhân lớn nhất** trong toàn bộ danh mục công cụ.

Đây là kết luận đáng giá nhất của bài với một thư mục về đầu tư công và nợ công, vì nó mâu thuẫn trực tiếp với thực tiễn phổ biến. Khi cần siết tài khoá gấp, dòng đầu tư công gần như luôn bị cắt trước, vì nó không tạo ra người mất việc ngay và không phải sửa luật. Mô hình nói rằng đó chính xác là lựa chọn tệ nhất trong danh mục.

**Thứ hai, khái niệm "hộ giàu kiếm được bao nhiêu tiêu bấy nhiêu" mô tả một hiện tượng rất phổ biến ở Việt Nam.** Đó là hộ có tài sản — nhưng là bất động sản và quyền lợi dài hạn, không phải tiền mặt — nên vẫn tiêu theo thu nhập hiện tại và vẫn có xu hướng tiêu dùng biên cao. Với một nền kinh tế mà của cải hộ gia đình tập trung nặng vào bất động sản, nhóm này có thể rất lớn.

Hàm ý: **thống kê về tài sản đánh giá thấp một cách có hệ thống mức độ nhạy cảm của tiêu dùng hộ gia đình với thu nhập hiện tại**. Và nó có nghĩa là các chính sách liên quan tới bất động sản — thuế tài sản, điều kiện tín dụng, thanh khoản thị trường nhà ở — có tác động lên tổng cầu lớn hơn nhiều so với mức mà tỷ trọng của chúng trong GDP gợi ý.

**Thứ ba, công cụ trung tâm của bài đòi một điều kiện tiền đề mà bài giả định sẵn có.** Toàn bộ kết quả về trợ cấp nhắm đích dựa trên việc nhà nước có thể **xác định đúng bốn thập phân vị thu nhập thấp nhất và chuyển tiền tới họ nhanh chóng**. Ở Bỉ, Pháp và Ý, hạ tầng đó tồn tại. Ở một nền kinh tế có khu vực phi chính thức lớn và hệ thống bảo trợ xã hội chưa phủ hết, nó không tồn tại — và không thể nhắm đích cái mà ta không nhận diện được.

Điều này nối trực tiếp với lập luận về hạ tầng số công trong số Finance & Development cùng thư mục: định danh số, thanh toán và trao đổi dữ liệu là điều kiện để có thể nhắm đích, và cái giá của việc không có chúng được định lượng bằng ví dụ chương trình bảo vệ việc làm của Mỹ, nơi trong 800 tỷ USD chỉ khoảng một phần tư tới một phần ba tới đúng người lao động cần.

Nói cách khác, **năng lực nhắm đích là một dạng dư địa tài khoá**. Nó không xuất hiện trong bất kỳ chỉ tiêu nợ hay thâm hụt nào, nhưng nó quyết định một nước có thể điều chỉnh với chi phí phúc lợi thấp hay không. Và nó phải được xây trước khi cần dùng, chứ không phải trong lúc khủng hoảng.

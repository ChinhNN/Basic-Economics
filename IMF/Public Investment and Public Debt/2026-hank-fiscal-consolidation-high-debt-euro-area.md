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

## Dàn ý chi tiết

### 1. Động cơ

- Tỷ lệ nợ vẫn cao sau đại dịch và cú sốc năng lượng, và nếu không điều chỉnh sẽ tiếp tục tăng. Khi nợ cao, động thái nợ rất nhạy với chênh lệch giữa tăng trưởng và lãi suất.
- Kinh tế chính trị của điều chỉnh ngày càng bị chi phối bởi mối lo phân phối, vì áp lực chi mới không thể đáp ứng nếu không cắt ở chỗ khác.
- Rủi ro chủ quyền tác động vượt ra ngoài ngân sách: chênh lệch lợi suất cao làm tăng chi phí vốn của doanh nghiệp, nhất là doanh nghiệp nắm nhiều trái phiếu chính phủ, và chi phí phúc lợi dồn lên hộ ít khả năng tự bảo hiểm nhất.
- Tốc độ điều chỉnh vì vậy là lựa chọn chính sách bậc nhất, phụ thuộc vào dấu và độ lớn tác động của nỗ lực tài khoá lên chênh lệch và hoạt động kinh tế.

### 2. Đóng góp

- Bài mở rộng mô hình của Auclert và cộng sự theo hai hướng: nhiều công cụ tài khoá giống ngân sách thật thay vì các cú sốc chi tiêu hay thuế cách điệu, và phần bù rủi ro chủ quyền nội sinh theo tỷ lệ nợ.
- Nợ có cấu trúc nhiều kỳ hạn nên thay đổi chênh lệch chỉ truyền dần vào chi phí lãi. Quy tắc Taylor được thu nhỏ để phản ánh nhiệm vụ toàn khu vực của ECB.
- Cơ chế truyền dẫn trung tâm là sự khác biệt về xu hướng tiêu dùng biên, sinh ra nội sinh từ cấu trúc hai tài sản. Mô hình tái tạo được ba sự thật: nhiều hộ có tài sản kém thanh khoản nhưng ít tiền mặt, xu hướng tiêu dùng biên cao với thu nhập tạm thời, và một khối lượng đáng kể hộ nằm ở ràng buộc thanh khoản.

### 3. Mô hình

- Hộ gia đình chọn tiêu dùng, lao động và phân bổ giữa hai tài khoản. Trợ cấp nhắm đích chia đều cho bốn thập phân vị năng suất thấp nhất.
- Doanh nghiệp dùng vốn công, vốn tư và lao động; vốn tư chịu chi phí điều chỉnh bậc hai; giá và lương chịu chi phí điều chỉnh kiểu Rotemberg, tương đương Calvo ở bậc một.
- Lãi suất thực phụ thuộc lãi danh nghĩa, phần bù rủi ro theo khoảng cách nợ so với dài hạn, và thuế doanh nghiệp hiệu dụng.
- Khi kỳ hạn dài, chênh lệch nới rộng đột ngột làm tăng chi phí phát hành mới nhưng ít ảnh hưởng tổng chi phí lãi ngay lập tức.
- Thuế khoán là công cụ cân đối, phản ứng theo nợ để giữ tỷ lệ nợ ổn định dài hạn mà không làm méo quyết định lao động hay tiết kiệm.

### 4. Trạng thái dừng

- Khoảng 43% hộ là HtM, trong đó 32% là giàu HtM. Xu hướng tiêu dùng biên gần bằng một ở nhóm đáy, vẫn cao ở nhóm giữa do tài sản kém thanh khoản, và thấp ở nhóm giàu nắm phần lớn tài sản.
- Tài sản thanh khoản thấp tập trung ở nhóm thu nhập thấp và trung bình, nên việc nhắm công cụ tài khoá theo đối tượng chịu tác động là rất quan trọng.

### 5. Chi phí của việc chờ đợi

- Giữ nguyên chính sách, thâm hụt tiếp tục mở rộng khi trả lãi tăng, phần bù rủi ro nới rộng và làm nợ tích lũy nhanh hơn trong một vòng lặp tài khoá tài chính tự củng cố.
- Đầu tư tư nhân bị lấn át qua thị trường tài sản, vì nợ công hút tiết kiệm; lương thực bị bào mòn.
- Bài nêu hai lưu ý: độ lớn của chi phí phụ thuộc giả định về kịch bản cơ sở, và so sánh với ExC+SR phóng đại khác biệt vì gộp lợi ích năng suất. Kết luận định tính rằng trì hoãn tốn kém vẫn đúng với ExC và ReC thuần.

### 6. Thành phần của củng cố

- ExC giảm nợ nhanh hơn vì cắt chi trực tiếp cải thiện cán cân sơ cấp; ReC chậm hơn vì thuế làm yếu hoạt động và thu hẹp cơ sở thuế.
- Số nhân của ExC nhỏ hơn vì trợ cấp bị cắt một phần rơi vào hộ không bị ràng buộc thanh khoản, trong khi thuế lao động làm thu nhập co lại diện rộng ở một nền kinh tế nhiều hộ HtM.
- Chênh lệch lợi suất giảm tạo tiết kiệm lãi đáng kể, hiệu ứng vắng mặt trong các mô hình giả định chênh lệch cố định.

### 7. Phân phối

- Dưới ExC, nếu không có bù nhắm đích, cắt trợ cấp bảo hiểm và phổ quát rơi nặng lên hộ thu nhập thấp và trung bình, vốn nhận khoảng 60% tổng trợ cấp. Nhóm giữa chịu mức giảm tuyệt đối lớn nhất.
- Bù nhắm đích nhỏ gần như triệt tiêu thiệt hại ở nhóm đáy vì người nhận có xu hướng tiêu dùng biên gần một. Bảo trợ xã hội nhắm đúng không chỉ công bằng mà còn hiệu quả về vĩ mô.
- Dưới ReC, gánh nặng trải đều hơn nhưng tổng mức giảm tiêu dùng sâu hơn. Tác động của thuế doanh nghiệp lên nhóm giàu bị giảm và trễ vì tài sản kém thanh khoản.
- Phân phối không phải tác dụng phụ để giảm nhẹ mà quay lại tác động lên tổng cầu. Mô hình không có biên thất nghiệp, nên thiệt hại thực của nhóm đáy có thể lớn hơn.

### 8. Cải cách cơ cấu

- Với cải cách, năng suất cao hơn nâng sản phẩm biên của lao động và vốn, hỗ trợ đầu tư và khôi phục lương thực. Sản lượng vượt mức giữ nguyên chính sách từ sau năm thứ hai.
- Lợi ích lũy tiến vì kênh lương có tác dụng mạnh hơn ở nhóm đáy. Cần ít trợ cấp nhắm đích hơn để bảo vệ hộ nghèo.
- Loại cải cách quyết định ai được lợi; gói nghiêng về thị trường chung và nâng kỹ năng sẽ lũy tiến hơn gói dựa chủ yếu vào bãi bỏ quy định trong nước.

### 9. Hàm ý thiết kế

- Hành động ngay rẻ hơn chờ đợi; cam kết một lộ trình bền vững thay vì điều chỉnh tùy ý hằng năm mới tạo ra hiệu ứng kỳ vọng làm nén chênh lệch.
- Thành phần tiết kiệm chi quan trọng ngang quy mô: loại bỏ trợ cấp kém hiệu quả hay cải cách trợ cấp phổ quát nhắm kém ít tốn về cầu.
- Bảo vệ đầu tư công để giữ tính bổ trợ giữa vốn công và vốn tư.
- Hệ thống bảo trợ có thể mở rộng trợ cấp nhắm đích nhanh là bổ sung then chốt.
- Khi bất bình đẳng cao, tính bền vững nợ phụ thuộc vào phân phối tài sản: điều chỉnh để hộ bị ràng buộc quá lộ ra sẽ làm suy yếu chính khả năng thực hiện kế hoạch.

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

### Đóng góp thật là kết quả về trợ cấp nhắm đích, và nó là thứ mô hình đại diện không thể tạo ra

Kết quả đáng giá nhất — và là lý do biện minh cho toàn bộ bộ máy HANK — là: dành **20% nỗ lực củng cố** cho trợ cấp nhắm đích **gần như triệt tiêu hoàn toàn thiệt hại tiêu dùng ở nhóm đáy**, với chi phí rất thấp.

Cơ chế thì đơn giản nhưng chỉ tồn tại trong một mô hình có hộ gia đình không đồng nhất: nhóm đáy có xu hướng tiêu dùng biên gần bằng **1**. Mỗi đồng chuyển tới họ quay lại thành cầu gần như toàn bộ, trong cùng kỳ. Một đồng cắt từ họ cũng rút khỏi cầu gần như toàn bộ.

Từ đó ra câu có sức nặng nhất trong bài: **bảo trợ xã hội nhắm đúng không chỉ công bằng mà còn hiệu quả về vĩ mô.** Đây không phải một lời kêu gọi đạo đức được gắn thêm vào một phân tích kỹ thuật; nó là một kết quả của chính phân tích đó. Trong một mô hình đại diện với một hộ gia đình duy nhất, mệnh đề này thậm chí không phát biểu được.

Hệ quả thiết kế rất cụ thể: nếu buộc phải củng cố, khoản chi **cuối cùng** nên bị cắt là khoản chi tới tay nhóm có xu hướng tiêu dùng biên cao nhất — vì cắt ở đó vừa đắt nhất về phúc lợi vừa đắt nhất về sản lượng. Hai tiêu chí trùng nhau, điều hiếm gặp trong kinh tế học tài khoá.

### Nhưng cùng thiết kế đó dồn toàn bộ chi phí lên nhóm giữa

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

### "Chi phí của việc chờ đợi" được so với một kịch bản không công bằng

Con số được nhấn mạnh nhất về mặt chính sách — nợ ở mức 134% GDP so với 139% vào năm 2031, chênh khoảng 5 điểm — được tính bằng cách so kịch bản **ExC+SR** với kịch bản giữ nguyên chính sách.

Nhưng ExC+SR gộp cả **cải cách cơ cấu nâng năng suất tổng hợp 0,1–0,2 điểm phần trăm mỗi năm** — một thứ hoàn toàn không liên quan gì tới việc củng cố sớm hay muộn. Một nước có thể làm cải cách cơ cấu mà không củng cố, hoặc củng cố mà không cải cách. Gộp chúng lại rồi gọi hiệu số là "chi phí của việc chờ đợi" là một phép so sánh thổi phồng.

Bài tự nêu cảnh báo này, và đó là thực hành tốt. Nhưng con số 5 điểm sẽ được trích dẫn mà không kèm cảnh báo, vì con số luôn sống lâu hơn dấu hoa thị đi kèm nó.

Điều đáng chú ý là lập luận **mạnh hơn** cho việc hành động sớm lại nằm ở một dòng phụ: dẫn chiếu tới kết quả rằng vượt qua một ngưỡng nhất định, chính sách tài khoá chủ động và chính sách tiền tệ chủ động **không thể cùng duy trì**, nên chi phí có thể **nhảy bậc** chứ không tăng dần.

Đó mới là lý do thuyết phục để không chờ: không phải vì chi phí của việc chờ tăng đều 5 điểm, mà vì **có thể tồn tại một vách đá**. Bài nhắc tới nó và không mô hình hoá nó.

### Cơ chế cấp bách nhất của bài là một cơ chế của liên minh tiền tệ, không phải của mức nợ

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

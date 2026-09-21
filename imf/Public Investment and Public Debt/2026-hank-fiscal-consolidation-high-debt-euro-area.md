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

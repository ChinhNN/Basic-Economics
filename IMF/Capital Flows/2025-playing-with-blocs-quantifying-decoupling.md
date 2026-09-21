# Playing with Blocs: Quantifying Decoupling — Chơi với các khối: định lượng quá trình tách rời

**Nguồn:** IMF Working Paper WP/2025/263.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 1 của bài, không có trang bìa và trang tác giả).
**Ý chính:** Sau Brexit, chiến tranh thương mại Mỹ–Trung và việc phương Tây cắt quan hệ với Nga, ai cũng chờ thương mại thế giới sụt giảm. Nhưng tỷ lệ thương mại trên GDP toàn cầu **không hề giảm** kể từ 2015. Bài dùng phần dư của phương trình lực hấp dẫn để **tự động phát hiện đường đứt gãy** giữa các khối mà không cần giả định trước, rồi đưa vào mô hình mạng sản xuất toàn cầu 66 nước và 22 ngành. Kết luận trung tâm: thế giới đang **tách rời chứ không phi toàn cầu hoá** — chi phí thương mại giữa hai khối tăng, nhưng **trong nội bộ mỗi khối lại giảm nhiều hơn**, khiến nước trung vị **được lợi 0,6% thu nhập thực**. Phát hiện gây bất ngờ nhất nằm ở phần phản thực: **các nước đang ở nhầm khối** — nước nghiêng về Mỹ trung bình sẽ có lợi hơn nếu sang khối Trung Quốc, và ngược lại. Điều đó hàm ý động cơ chi phối việc chọn phe **không phải là lợi ích thương mại**.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Số hiệu tài liệu lấy từ trang bìa sau.

## Sơ đồ

### Nghịch lý mở đầu: thương mại không hề giảm

```text
       TỶ LỆ THƯƠNG MẠI HÀNG HOÁ TRÊN GDP, 1985–2023
       (đường thẳng đứng đánh dấu năm 2015 — trước trưng cầu
        Brexit và trước bầu cử Mỹ 2016)
       ┌─────────────────────────────────────────────────────────┐
       │ THẾ GIỚI ····· vẫn KIÊN CƯỜNG; thực ra còn ĐẢO NGƯỢC    │
       │   MỘT PHẦN xu hướng giảm bắt đầu từ 2009                │
       │ ★ HOA KỲ ····· KHÔNG có sụt giảm rõ rệt                 │
       │ ★ TRUNG QUỐC · KHÔNG có sụt giảm rõ rệt                 │
       │ ★ LIÊN MINH ·· KHÔNG có sụt giảm rõ rệt                 │
       │   CHÂU ÂU                                               │
       └─────────────────────────────────────────────────────────┘
       ⚠ NGAY CẢ các bên CHÍNH trong xung đột thương mại cũng
         KHÔNG chứng kiến tổng thương mại giảm
       ═══════════════════════════════════════════════════════════
       ★★ BẢNG 1 — LỜI GIẢI NẰM Ở ĐÂY
       thay đổi tỷ lệ NHẬP KHẨU TRÊN GDP giữa 2015 và 2023
       ┌──────────┬────────┬────────┬────────┬────────┐
       │ XUẤT ↓   │  HOA   │ TRUNG  │   EU   │  PHẦN  │
       │ NHẬP →   │  KỲ    │ QUỐC   │        │  CÒN   │
       │          │        │        │        │  LẠI   │
       ├──────────┼────────┼────────┼────────┼────────┤
       │ HOA KỲ   │   —    │ ★−0,275│ +0,262 │ +0,015 │
       │ TRUNG QUỐC│★−0,401│   —    │ +0,237 │ +0,137 │
       │ EU       │ +0,050 │ −0,066 │ +0,148 │ −0,014 │
       │ PHẦN CÒN │ +0,012 │ +0,047 │ +0,035 │ +0,105 │
       │ LẠI      │        │        │        │        │
       ├──────────┼────────┼────────┼────────┼────────┤
       │ ★ TỔNG   │ −0,070 │ +0,005 │ +0,128 │ +0,076 │
       │ NHẬP/GDP │        │        │        │        │
       └──────────┴────────┴────────┴────────┴────────┘
       ★★★ ĐỌC BẢNG NÀY: thương mại Mỹ–Trung SỤP (−27,5% và
          −40,1%), NHƯNG thương mại của CẢ HAI với PHẦN CÒN LẠI
          THẾ GIỚI đều TĂNG
       → ★ "Nền kinh tế thế giới đang trải qua TÁCH RỜI, chứ
           KHÔNG PHẢI PHI TOÀN CẦU HOÁ"
```

### Phương pháp: để dữ liệu tự chỉ ra các khối

```text
       BƯỚC ❶ — PHƯƠNG TRÌNH LỰC HẤP DẪN LẤY SAI PHÂN LOGARIT
              Δln X(m,n) = δ(m) + δ(n) + w(m,n)
              └─ thay đổi ─┘  └── hiệu ứng ──┘  └ phần ┘
                 log xuất      cố định nước       dư
                 khẩu m→n      xuất và nhập
       ★ hiệu ứng cố định HẤP THỤ TOÀN BỘ: cú sốc cung và cầu
         riêng của từng nước, thay đổi chỉ số giá, và MỌI thay đổi
         rào cản thương mại xảy ra ở cấp NƯỚC (chứ không cấp CẶP)
       → ★★ PHẦN DƯ phản ánh thay đổi của TOÀN BỘ rào cản thương
         mại SONG PHƯƠNG giữa m và n — cả quan sát được lẫn không
       ⚠ bài nói rõ: KHÔNG tách được nguồn gốc của các thay đổi
         này. Chúng có thể phản ánh thay đổi CHÍNH SÁCH thương
         mại, dịch chuyển SỞ THÍCH, thay đổi BIÊN LỢI NHUẬN song
         phương, hoặc cú sốc song phương khác
       ★ chuyển thành chi phí thương mại: Δln τ = ŵ / (1 − γ)
       ★ chọn 2015 làm năm gốc vì trưng cầu Brexit và bầu cử
         Trump 2016 là hai sự kiện LỚN ĐẦU TIÊN của kỷ nguyên
         tách rời; kết thúc 2023 vì Nga xâm lược Ukraine năm 2022
       ═══════════════════════════════════════════════════════════
       BƯỚC ❷ — QUY TẮC PHÂN LOẠI KHỐI (rất đơn giản)
       ┌─────────────────────────────────────────────────────────┐
       │        thay đổi chi phí thương mại VỚI TRUNG QUỐC        │
       │                         ▲                               │
       │   ★ KHỐI HOA KỲ         │                               │
       │   (chi phí với Mỹ GIẢM, │      KHÔNG LIÊN KẾT           │
       │    với Trung Quốc TĂNG) │   (cùng tăng hoặc cùng giảm)  │
       │ ────────────────────────┼──────────────────────────▶    │
       │     KHÔNG LIÊN KẾT      │   ★ KHỐI TRUNG QUỐC           │
       │                         │   (chi phí với Trung Quốc     │
       │                         │    GIẢM, với Mỹ TĂNG)         │
       │        thay đổi chi phí thương mại VỚI HOA KỲ           │
       └─────────────────────────────────────────────────────────┘
       ★★ NHẤN MẠNH QUAN TRỌNG: phân loại dựa trên THAY ĐỔI chi
          phí thương mại TƯƠNG ĐỐI, KHÔNG dựa trên MỨC thương mại
          song phương ban đầu
          → một nước có thương mại BAN ĐẦU rất lớn với Mỹ vẫn có
            thể bị xếp vào khối Trung Quốc nếu chi phí với Trung
            Quốc GIẢM còn với Mỹ TĂNG trong giai đoạn này
       ⚠ bài cũng nói rõ: chỉ xét liên kết THƯƠNG MẠI, không xét
         FDI, kiều hối, chuyển giao công nghệ hay chính sách di cư
       ═══════════════════════════════════════════════════════════
       ★ KẾT QUẢ PHÂN LOẠI — 187 NƯỚC
       khối HOA KỲ ········ 43 nước
       khối TRUNG QUỐC ···· 46 nước
       ★★ KHÔNG LIÊN KẾT ·· 98 nước (ĐA SỐ)
       ─────────────────────────────────────────────────────────
       ⚠ MỘT SỐ TRƯỜNG HỢP GÂY BẤT NGỜ (trong mẫu mô hình)
       rõ ràng nghiêng về TRUNG QUỐC · Nga · ★ Ả-rập Xê-út ·
         ★ ISRAEL · ★ Hong Kong · Brazil · Colombia · Indonesia ·
         Malaysia · Campuchia · ★ SLOVENIA
       nghiêng về HOA KỲ · chủ yếu là CHÂU ÂU, nhưng cũng có
         ★ ẤN ĐỘ · Hàn Quốc · Nhật Bản · Singapore · ★ MYANMAR
       ★ KHÔNG LIÊN KẾT · Canada · Thuỵ Sĩ · Bỉ · Hà Lan · Pháp ·
         Ý · Tây Ban Nha · Mexico · Việt Nam · Nam Phi · Thái Lan
```

### Định cỡ mức chi phí: con số quyết định

```text
       ⚠ VẤN ĐỀ KỸ THUẬT: hồi quy lực hấp dẫn CHỈ nhận diện được
         thay đổi chi phí TƯƠNG ĐỐI (so với một cặp nước bị bỏ
         ra), KHÔNG cho biết MỨC TUYỆT ĐỐI
       ⚠ và KHÔNG THỂ dùng kỹ thuật đảo mô hình thông thường vì
         KHÔNG CÓ dữ liệu HẤP THỤ NỘI ĐỊA cho năm 2023
                              │
                              ▼
       ★ GIẢI PHÁP: dùng chính mô hình để ĐỊNH CỠ
       τ̂ = exp[ Δln τ(m,n) + Δln τ^cơ_sở ]  ∀ m ≠ n
                └─ tương đối ─┘  └─ dịch chuyển chung ─┘
       tìm Δln τ^cơ_sở sao cho tỷ lệ thương mại trên GDP thế giới
       trong MÔ HÌNH khớp với DỮ LIỆU: từ 21,8% (2015) lên 22,6%
       (2023) — tăng 0,8 điểm phần trăm
                              │
                              ▼
       ★★★ KẾT QUẢ: Δln τ^cơ_sở = −0,003
          tức là NẾU CÓ GÌ THÌ chi phí thương mại BÌNH QUÂN đã
          GIẢM 0,3% — chứ KHÔNG TĂNG
       ✔ cách này GIỮ NGUYÊN toàn bộ tính không đồng nhất ở cấp
         cặp nước, đồng thời khớp với xu hướng thương mại thế giới
       ═══════════════════════════════════════════════════════════
       ★★ BẢNG 4 — CHI PHÍ THƯƠNG MẠI GIỮA CÁC KHỐI (đã gồm cơ sở)
       ┌──────────────┬────────┬────────┬────────┬─────────┐
       │ XUẤT ↓ NHẬP →│ KHỐI   │ KHỐI   │ KHÔNG  │ TỔNG    │
       │              │ HOA KỲ │ TRUNG  │ LIÊN   │         │
       │              │        │ QUỐC   │ KẾT    │         │
       ├──────────────┼────────┼────────┼────────┼─────────┤
       │ ★ KHỐI HOA KỲ│ −0,046 │ +0,040 │ +0,004 │ −0,003  │
       │ ★ KHỐI TRUNG │★+0,114 │ −0,072 │ +0,023 │ ★+0,050 │
       │   QUỐC       │        │        │        │         │
       │   KHÔNG LIÊN │ −0,033 │ −0,035 │ −0,008 │ −0,024  │
       │   KẾT        │        │        │        │         │
       ├──────────────┼────────┼────────┼────────┼─────────┤
       │ ★★ TỔNG      │ +0,002 │ −0,012 │ +0,003 │ ★ 0,000 │
       └──────────────┴────────┴────────┴────────┴─────────┘
       ★★★ BA ĐIỀU CẦN ĐỌC TRONG BẢNG NÀY
       ① chi phí GIỮA HAI KHỐI ĐÚNG LÀ TĂNG: từ khối Trung Quốc
          sang khối Mỹ +11,4%, chiều ngược lại +4,0%
       ② ★ NHƯNG chi phí TRONG NỘI BỘ mỗi khối GIẢM (−4,6% và
          −7,2%), và chi phí nhập từ nhóm KHÔNG LIÊN KẾT cũng giảm
       ③ ★★ Ô GÓC DƯỚI BÊN PHẢI BẰNG ĐÚNG 0,000
          → chỉ khối TRUNG QUỐC chịu mức tăng chi phí XUẤT tổng
            thể (+0,050); KHÔNG khối nào chịu mức tăng chi phí
            NHẬP đáng kể
       → ★ "dù tách rời ĐÃ XẢY RA, chi phí thương mại tổng thể
           KHÔNG TĂNG"
```

### Kết quả mô hình: hầu hết đều được lợi

```text
       CẤU TRÚC MÔ HÌNH
       mạng sản xuất toàn cầu đa quốc gia đa ngành theo Huo,
       Levchenko và Pandalai-Nayar (2025) và Bonadio và cộng sự
       66 NƯỚC · 22 NGÀNH · bảng đầu vào đầu ra liên quốc gia của
       OECD bản 2021 · giải bằng đại số mũ chính xác
       hộ gia đình có sở thích GHH, cung lao động theo ngành kiểu
       Roy-Fréchet; doanh nghiệp lợi suất không đổi theo quy mô;
       thương mại chịu chi phí tảng băng
       ┌─────────────────────────┬─────────────────────────────┐
       │ THAM SỐ                 │ GIÁ TRỊ VÀ NGUỒN            │
       │ ρ, ε (thay thế giữa     │ 1                           │
       │   các ngành)            │                             │
       │ γ, ν (thay thế giữa     │ 4 (Broda–Weinstein 2006)    │
       │   nguồn gốc, Armington) │                             │
       │ ψ (co giãn Frisch)      │ 1 (Chetty và cộng sự 2011)  │
       │ μ (cung lao động ngành) │ 1,5 (Galle và cộng sự 2023) │
       └─────────────────────────┴─────────────────────────────┘
       ═══════════════════════════════════════════════════════════
       ★★ BẢNG 5 — THAY ĐỔI GDP THỰC VÀ THU NHẬP THỰC (điểm %)
       ┌──────────────┬──────────────────┬──────────────────────┐
       │ KHỐI         │ GDP THỰC         │ THU NHẬP THỰC        │
       │              │ p25 · TRUNG VỊ · │ p25 · TRUNG VỊ · p75 │
       │              │        p75       │                      │
       ├──────────────┼──────────────────┼──────────────────────┤
       │ ★ TỔNG THỂ   │0,061· 0,588 ·1,297│0,059· 0,619 ·1,322  │
       │   Khối Hoa Kỳ│0,125· 0,532 ·0,712│0,147· 0,536 ·0,699  │
       │ ⚠ Khối Trung │−0,263·0,299·0,773│−0,261·0,372 ·0,780  │
       │   Quốc       │                  │                      │
       │ ★ Không liên │0,034· 0,787 ·1,397│0,066· 0,755 ·1,432  │
       │   kết        │                  │                      │
       └──────────────┴──────────────────┴──────────────────────┘
       ★★★ ĐỌC BẢNG NÀY
       nước TRUNG VỊ được lợi 0,6% — TRÁI với trực giác thông
       thường rằng tách rời làm giảm GDP thế giới
       ★ 51 TRONG 66 NƯỚC có thu nhập thực TĂNG
       ★ ba phần tư số nước tăng ở CẢ GDP LẪN thu nhập
       ⚠ CHỈ khối TRUNG QUỐC có phân vị 25 ÂM
       ★ nhóm KHÔNG LIÊN KẾT được lợi NHIỀU NHẤT (0,787) — vì họ
         KHÔNG tăng chi phí thương mại với BẤT KỲ khối nào một
         cách hệ thống
       ⚠ Hoa Kỳ và Trung Quốc TỰ THÂN gần như KHÔNG THAY ĐỔI
       ─────────────────────────────────────────────────────────
       ★ PHÂN RÃ (Bảng B2): KHOẢNG 90% mức thay đổi thu nhập thực
         đến từ thay đổi chi phí TƯƠNG ĐỐI SONG PHƯƠNG (0,574 trên
         0,637), chỉ 0,074 đến từ mức giảm chung 0,3%
       → kết luận KHÔNG phụ thuộc vào bước định cỡ
       ═══════════════════════════════════════════════════════════
       ★★ HAI CỰC CỦA PHÂN BỐ
       ĐƯỢC LỢI NHẤT
         ★ VIỆT NAM ···· +6,9%   ★ LÀO ···· +3,5%
         cả hai đều chứng kiến chi phí thương mại GIẢM với CẢ Mỹ
         LẪN Trung Quốc → bị xếp KHÔNG LIÊN KẾT, nhưng mô hình
         cho thấy thương mại song phương với họ TĂNG MẠNH
         ✔ khớp với các tường thuật về chuỗi cung ứng dịch chuyển
           khỏi Trung Quốc sang các nước như Việt Nam
       THIỆT HẠI NHẤT
         ⚠ CÁC NƯỚC BALTIC ···· −3% tới −5%
         quan hệ thương mại chặt chẽ với Nga BỊ ĐỨT GÃY, mà KHÔNG
         có mức giảm chi phí bù đắp ở nơi khác
```

### Phản thực: các nước đang ở nhầm khối

```text
       Ý TƯỞNG: với mỗi nước, tính xem GDP và thu nhập sẽ thay
       đổi thế nào NẾU nó thuộc một khối KHÁC
       ★ KỸ THUẬT QUAN TRỌNG: thay chi phí thực tế của nước đó
         bằng chi phí BÌNH QUÂN của khối đích với mọi đối tác,
         RỒI CHUẨN HOÁ LẠI sao cho mức thay đổi chi phí bình quân
         gia quyền theo thương mại BẰNG ĐÚNG mức thực tế
         → để tránh hiệu ứng MỨC MANG TÍNH CƠ HỌC
       ★ thực hiện TỪNG NƯỚC MỘT, giữ nguyên chi phí của mọi nước
         khác ở giá trị thực tế
       ═══════════════════════════════════════════════════════════
       ★★★ BẢNG 6 — THAY ĐỔI SO VỚI THỰC TẾ (trung vị, điểm %)
       ┌────────────────────┬──────────────┬────────────────────┐
       │ DI CHUYỂN          │ GDP THỰC     │ THU NHẬP THỰC      │
       ├────────────────────┼──────────────┼────────────────────┤
       │ SANG KHỐI HOA KỲ                                       │
       │ ★★ nước khối TRUNG │ ★ +0,658     │ ★ +0,661           │
       │    QUỐC            │ (6/10 được   │                    │
       │                    │  lợi)        │                    │
       │ ⚠ nước KHÔNG LIÊN  │  −0,710      │  −0,762            │
       │   KẾT              │              │                    │
       ├────────────────────┼──────────────┼────────────────────┤
       │ SANG KHỐI TRUNG QUỐC                                   │
       │ ★★ nước khối HOA KỲ│ ★ +0,211     │ ★ +0,238           │
       │                    │ (8/14 được   │                    │
       │                    │  lợi)        │                    │
       │ ⚠ nước KHÔNG LIÊN  │  −0,501      │  −0,476            │
       │   KẾT              │              │                    │
       ├────────────────────┼──────────────┼────────────────────┤
       │ SANG NHÓM KHÔNG LIÊN KẾT                               │
       │ ⚠ nước khối HOA KỲ │  −0,622      │  −0,629            │
       │ ⚠ nước khối TRUNG  │  −0,324      │  −0,328            │
       │   QUỐC             │              │                    │
       └────────────────────┴──────────────┴────────────────────┘
       ★★★ ĐỌC HAI DÒNG ĐẦU CỦA MỖI KHỐI CÙNG NHAU
       nước đang nghiêng về TRUNG QUỐC sẽ có lợi hơn nếu sang MỸ
       nước đang nghiêng về MỸ sẽ có lợi hơn nếu sang TRUNG QUỐC
       ★★ tức là "TRUNG BÌNH MÀ NÓI, CÁC NƯỚC TRONG KHỐI MỸ VÀ
          KHỐI TRUNG QUỐC ĐANG Ở 'SAI' KHỐI"
       → ★ HÀM Ý: "việc phân loại khối quan sát được trong dữ liệu
           KHỚP RẤT KÉM với lợi ích kinh tế liên quan tới thương
           mại" → các động cơ KHÁC, PHỎNG ĐOÁN LÀ ĐỊA CHÍNH TRỊ,
           nhiều khả năng đang chi phối việc sắp xếp lại dòng
           thương mại những năm gần đây
       ⚠ NHƯNG: nước trong hai khối cũng sẽ THIỆT nếu trở thành
         KHÔNG LIÊN KẾT → không phải cứ trung lập là tốt
       ⚠ và ĐẰNG SAU các số trung vị là ĐỘ PHÂN TÁN HOÀN TOÀN:
         trong MỌI loại di chuyển đều có cả kẻ THẮNG lẫn kẻ THUA
       ★ vài ngoại lệ đáng chú ý: Ả-rập Xê-út, Latvia và Lithuania
         sẽ thấy GDP TĂNG HƠN 2% nếu trở thành không liên kết
```

### Kiểm chứng và điều gì thực sự dẫn dắt

```text
       ❶ ★ THUẾ QUAN — bằng chứng TRỰC TIẾP QUAN SÁT ĐƯỢC
       vì mức tuyệt đối do mô hình định cỡ, có thể lo ngại kết quả
       phụ thuộc mô hình → bài kiểm bằng cấu phần chi phí thương
       mại QUAN SÁT ĐƯỢC trực tiếp: THUẾ QUAN (nguồn UN-TRAINS,
       2015–2021)
       ★★ mức thay đổi BÌNH QUÂN GẦN BẰNG 0, và ★ 39,5% SỐ CẶP
          NƯỚC chứng kiến thuế quan GIẢM
       ✔ khớp với Bown, Jung và Zhang (2019): trong chiến tranh
         thương mại Mỹ–Trung, Trung Quốc HẠ thuế tối huệ quốc với
         phần còn lại thế giới trong khi NÂNG với Mỹ
       ═══════════════════════════════════════════════════════════
       ❷ THUẬT TOÁN LEIDEN — cách phân khối hoàn toàn khác
       phương pháp học máy phát hiện cộng đồng không chồng lấn
       trong mạng lớn; chạy 100 lượt (có thành phần ngẫu nhiên),
       xếp nước theo TỶ LỆ SỐ LẦN cùng cộng đồng với Mỹ hoặc Trung
       Quốc
       ★ với 73 nước được CẢ HAI phương pháp xếp vào khối Mỹ hoặc
         Trung Quốc, 52 nước (71%) được xếp VÀO CÙNG khối
       ⚠ phương pháp cơ sở BẢO THỦ HƠN: xếp nhiều nước hơn vào
         nhóm không liên kết
       ═══════════════════════════════════════════════════════════
       ❸ ★★ NĂM GỐC VÀ NĂM CUỐI THAY THẾ — PHÁT HIỆN VỀ THỜI GIAN
       2016 làm năm gốc (thuế chiến Mỹ–Trung có hiệu lực 2017):
         phân loại TƯƠNG TỰ; KHÔNG nước nào trong mẫu mô hình bị
         xếp vào khối NGƯỢC LẠI so với cơ sở
       ★★★ GIAI ĐOẠN TRƯỚC COVID 2015–2019 — KẾT QUẢ KHÁC HẲN
       ┌─────────────────────────────────────────────────────────┐
       │ chi phí giữa khối Mỹ và khối Trung Quốc ĐÃ TĂNG rồi     │
       │ ⚠ NHƯNG mức giảm chi phí TRONG NỘI BỘ khối KÉM RÕ RỆT   │
       │   và GẦN NHƯ BẰNG KHÔNG với khối Mỹ                     │
       │ → tổng chi phí thương mại TĂNG NHẸ                      │
       │ ★ thu nhập thực nước trung vị: −0,06%                   │
       │   (so với +0,6% ở giai đoạn 2015–2023)                  │
       └─────────────────────────────────────────────────────────┘
       ★★ PHÁT HIỆN VỀ TRÌNH TỰ THỜI GIAN
          mức TĂNG chi phí GIỮA CÁC KHỐI đến TRƯỚC
          mức GIẢM chi phí TRONG NỘI BỘ khối đến SAU
          → "rõ ràng các nước cần MỘT THỜI GIAN để giảm rào cản
            thương mại trong nội bộ khối sau cú sốc tách rời
            Mỹ–Trung ban đầu"
       ⚠ bài nêu cách diễn giải thay thế: COVID và cuộc xâm lược
         Ukraine 2022 cùng những thay đổi kinh tế và chính sách mà
         các cú sốc lớn này gây ra cũng có thể ảnh hưởng tới rào
         cản song phương
       ═══════════════════════════════════════════════════════════
       ❹ ★ GIẢ DƯỢC 2002–2007 — trước khi có căng thẳng Mỹ–Trung
       ★★ KHÔNG TÌM THẤY bằng chứng tách rời nào
          chỉ 3 nước được xếp vào khối Trung Quốc, KỂ CẢ Trung Quốc
          70% số nước không liên kết (so với 60% ở cơ sở)
          ★ MỌI cặp khối, KỂ CẢ từ khối Trung Quốc sang khối Mỹ,
            đều chứng kiến chi phí thương mại GIẢM
       ═══════════════════════════════════════════════════════════
       ❺ KIỂM CHỨNG PHƯƠNG PHÁP ĐỊNH CỠ
       so với phương pháp Head và Ries (đòi hỏi dữ liệu hấp thụ
       nội địa, chỉ có tới 2010) trên các cửa sổ 8 năm từ 2000
       ★ chênh lệch −0,9% ở trung bình, −0,03% ở trung vị
       ★ tương quan 0,79
       ═══════════════════════════════════════════════════════════
       ❻ ★★ ĐIỀU GÌ THỰC SỰ DẪN DẮT — BỎ PHIẾU LIÊN HỢP QUỐC
       ┌──────────────────────┬────────────┬───────────────────┐
       │ BIẾN                 │ 2015–2023  │ GIẢ DƯỢC 2010–2015│
       ├──────────────────────┼────────────┼───────────────────┤
       │ ★★ Đồng thuận bỏ     │ ★ 0,672*** │ ★ 0,184           │
       │    phiếu LHQ         │            │ KHÔNG Ý NGHĨA     │
       │ Log dòng thương mại  │ −0,423***  │ −0,354***         │
       │   năm gốc            │            │                   │
       │ ★ Log dòng thương    │ +0,148***  │ +0,0957***        │
       │   mại NĂM 2000       │            │                   │
       │ Log khoảng cách      │ −0,288***  │ −0,291***         │
       └──────────────────────┴────────────┴───────────────────┘
       ★★★ HAI CÁCH ĐỌC QUAN TRỌNG
       ① cặp nước BỎ PHIẾU GIỐNG NHAU tại Đại hội đồng năm 2015
          chứng kiến thương mại song phương TĂNG TƯƠNG ĐỐI sau đó
          — nhưng ở giai đoạn GIẢ DƯỢC thì KHÔNG có tương quan nào
       ② ★ dòng thương mại năm GỐC có hệ số ÂM, còn dòng năm 2000
          có hệ số DƯƠNG
          → "thương mại tăng nhiều hơn với các cặp GẦN GŨI VỀ ĐỊA
            CHÍNH TRỊ, và các nước RỜI XA đối tác năm 2015 để QUAY
            VỀ với đối tác LỊCH SỬ năm 2000"
       ★ nghiên cứu sự kiện: TRƯỚC 2015 hệ số đồng thuận LHQ gần
         như BẰNG 0 và không có xu hướng; SAU 2015 tương quan BẮT
         ĐẦU TĂNG và MẠNH DẦN THEO THỜI GIAN
       → ★★ "2015–2017 đánh dấu khởi đầu của việc GIA TĂNG vai trò
           các lực địa chính trị trong thương mại quốc tế"
```

## Ba câu hỏi bài viết trả lời

1. Thế giới có đang phi toàn cầu hoá không, nếu thương mại trên GDP không hề giảm?
2. Nước nào đã nghiêng về khối nào, và làm sao biết được mà không cần giả định trước?
3. Các nước có chọn khối theo lợi ích kinh tế không?

## Dàn ý chi tiết

### 1. Nghịch lý mở đầu

- Sau một kỷ nguyên dài hội nhập ngày càng sâu, thập kỷ qua chứng kiến nhiều lực cản mạnh với hội nhập kinh tế, đánh dấu bằng Brexit, chiến tranh thương mại Mỹ và Trung Quốc, cùng việc quan hệ kinh tế giữa phương Tây với Nga bị cắt đứt. Người ta thường tự hỏi liệu đây có phải khởi đầu của phi toàn cầu hoá.
- Nhưng thương mại thế giới so với hoạt động kinh tế không hề giảm kể từ khi các cú sốc này bắt đầu. Tỷ lệ thương mại trên GDP thậm chí đảo ngược một phần xu hướng giảm bắt đầu từ năm 2009. Đáng chú ý hơn, tỷ lệ này cũng không giảm ở chính các nền kinh tế lớn nằm ở tâm điểm của các gián đoạn do chính sách gây ra.
- Lời giải thích gần nhất là ngay cả khi các nước trong xung đột thương mại rút khỏi nhau, họ lại tăng thương mại với các nước khác. Nền kinh tế thế giới đang trải qua tách rời chứ không phải phi toàn cầu hoá.

### 2. Phương pháp phát hiện khối

- Bài dùng cách tiếp cận hoàn toàn dựa trên dữ liệu để phát hiện đường đứt gãy phân mảnh trong dòng thương mại quốc tế. Dựa vào truyền thống lực hấp dẫn về đo chi phí thương mại, bài chiếu thay đổi logarit của thương mại hàng hoá song phương giai đoạn 2015 tới 2023 lên sức cản đa phương, thể hiện qua hiệu ứng cố định nước xuất khẩu và nước nhập khẩu.
- Các hiệu ứng cố định hấp thụ toàn bộ cú sốc cung và cầu riêng của từng nước, thay đổi chỉ số giá, và mọi thay đổi rào cản thương mại xảy ra ở cấp nước chứ không phải cấp cặp nước. Phần dư do đó phản ánh thay đổi của toàn bộ rào cản thương mại song phương, cả quan sát được lẫn không quan sát được.
- Bài nói rõ rằng theo thông lệ, họ không tách các nguồn gốc của những thay đổi này. Chúng có thể phản ánh thay đổi chính sách thương mại, dịch chuyển sở thích, thay đổi biên lợi nhuận song phương, hoặc các cú sốc song phương khác ảnh hưởng tới rào cản.
- Quy tắc phân loại rất đơn giản. Một nước thuộc khối Mỹ nếu chi phí thương mại bình quân với Mỹ giảm và với Trung Quốc tăng. Ngược lại cho khối Trung Quốc. Mọi nước còn lại là không liên kết.
- Bài nhấn mạnh một điểm quan trọng: phân loại dựa trên thay đổi chi phí thương mại tương đối, không dựa trên mức thương mại song phương ban đầu. Do đó một nước có dòng thương mại ban đầu rất lớn với Mỹ vẫn có thể bị xếp vào nhóm nghiêng về Trung Quốc nếu chi phí tương đối của nó với Trung Quốc giảm còn với Mỹ tăng trong giai đoạn này.
- Kết quả là trong 187 nước có dữ liệu, 43 nghiêng về Mỹ, 46 nghiêng về Trung Quốc, và 98 nước còn lại không liên kết. Trong mẫu mô hình, Nga, Ả-rập Xê-út, Israel và Hong Kong rõ ràng nghiêng về Trung Quốc, còn các nước nghiêng về Mỹ chủ yếu là châu Âu nhưng cũng gồm Ấn Độ, Hàn Quốc, Nhật Bản và Singapore.

### 3. Định cỡ mức chi phí

- Thách thức kỹ thuật là hồi quy lực hấp dẫn chỉ nhận diện được thay đổi chi phí tương đối so với một cặp nước bị bỏ ra, không cho biết mức tuyệt đối. Đồng thời không thể dùng kỹ thuật đảo mô hình thông thường để khôi phục thay đổi chi phí thương mại, vì không có dữ liệu hấp thụ nội địa cho năm 2023.
- Giải pháp là nhân thang toàn bộ ma trận thay đổi chi phí suy ra từ hồi quy với một hệ số chung, sao cho mô hình khớp với thay đổi của tỷ lệ thương mại trên GDP thế giới trong dữ liệu, từ 21,8 phần trăm năm 2015 lên 22,6 phần trăm năm 2023. Cách này giữ nguyên toàn bộ tính không đồng nhất ở cấp cặp nước.
- Kết quả là hệ số chung bằng âm không phẩy không không ba, hàm ý rằng nếu có gì thì chi phí thương mại bình quân đã giảm khoảng không phẩy ba phần trăm chứ không tăng.
- Bài nêu rõ giả định: mọi thay đổi trong dòng thương mại song phương sau khi trừ hiệu ứng cố định nước đều được quy cho thay đổi chi phí thương mại. Mô hình có thể chứa các cú sốc chuẩn như năng suất hay cầu, nhưng chúng đã bị hiệu ứng cố định nước hấp thụ. Bài cũng không xét riêng các cú sốc song phương khác như thay đổi biên lợi nhuận mà nhà xuất khẩu áp cho một nước nhập khẩu cụ thể, thay đổi hình mẫu sản xuất năng lượng toàn cầu, hay thay đổi dòng di cư, kiều hối và đầu tư.
- Bảng chi phí giữa các khối cho ba kết quả. Chi phí từ khối Trung Quốc sang khối Mỹ tăng mười một phẩy bốn phần trăm và chiều ngược lại tăng bốn phần trăm. Nhưng các mức tăng này bị bù đắp bởi mức giảm chi phí trong nội bộ khối cũng như chi phí nhập khẩu từ các nước không liên kết. Chỉ khối Trung Quốc chịu mức tăng chi phí xuất khẩu tổng thể, và không khối nào chứng kiến chi phí nhập khẩu tổng thể tăng đáng kể.

### 4. Mô hình định lượng

- Mô hình là mạng sản xuất toàn cầu đa quốc gia đa ngành theo Huo, Levchenko và Pandalai-Nayar cùng Bonadio và cộng sự, với 66 nước và 22 ngành, dùng bảng đầu vào và đầu ra liên quốc gia của OECD bản 2021.
- Hộ gia đình có sở thích kiểu Greenwood, Hercowitz và Huffman ở cấp tổng, nhưng cung lao động theo từng ngành lại co giãn đẳng trị theo lương tương đối của ngành đó, theo cách xây dựng kiểu Roy và Fréchet. Cả tiêu dùng cuối lẫn đầu vào trung gian đều có hai tầng: tầng trên gộp các ngành rộng, tầng dưới là tổng hợp Armington các mặt hàng từ các nước nguồn khác nhau.
- Bài báo cáo hai kết quả tổng hợp. GDP thực là đại lượng quen thuộc được hệ thống tài khoản quốc gia theo dõi, nhưng vì giữ giá ở mức trước cú sốc nên không tính tới việc thay đổi chi phí thương mại ảnh hưởng tới giá nhập khẩu vốn nằm trong chỉ số giá tiêu dùng. Vì vậy bài cũng báo cáo thu nhập thực.

### 5. Kết quả cơ sở

- Nước trung vị được lợi khoảng không phẩy sáu phần trăm về cả GDP thực lẫn thu nhập thực, và ba phần tư số nước tăng ở cả hai chỉ tiêu. Trung vị dương ở mọi khối. Hoa Kỳ và Trung Quốc tự thân gần như không thay đổi.
- Nhóm không liên kết được lợi nhiều nhất, điều mà bài giải thích bằng việc họ không tăng chi phí thương mại với bất kỳ khối nào một cách hệ thống. Chỉ khối Trung Quốc có phân vị hai mươi lăm âm.
- Phân rã cho thấy khoảng chín mươi phần trăm mức thay đổi thu nhập thực đến từ thay đổi chi phí tương đối song phương, chỉ một phần nhỏ đến từ mức giảm chung. Điều này quan trọng vì nó cho thấy kết luận không phụ thuộc vào bước định cỡ mức chi phí bằng mô hình.
- Hai cực của phân bố rất cách biệt. Việt Nam và Lào được lợi mạnh nhất, lần lượt sáu phẩy chín và ba phẩy năm phần trăm, do chi phí thương mại giảm với cả Mỹ lẫn Trung Quốc. Dù phân loại xếp hai nước này là không liên kết, mô hình cho thấy thương mại song phương với họ tăng mạnh, nhất quán với các tường thuật về chuỗi cung ứng dịch chuyển khỏi Trung Quốc. Ở cực ngược lại là các nước Baltic, có quan hệ thương mại chặt chẽ với Nga bị đứt gãy mà không có mức giảm chi phí bù đắp ở nơi khác, dẫn tới thiệt hại ba tới năm phần trăm.
- Bài nêu rõ giới hạn của mô phỏng: chúng bỏ qua nhiều kênh mà thay đổi chi phí thương mại có thể ảnh hưởng tới thu nhập thực, như hiệu ứng năng suất động và chuyển giao tri thức, lợi suất tăng theo quy mô, hay ma sát trong tái phân bổ và đa dạng hoá chuỗi cung ứng phát sinh từ hợp đồng không hoàn chỉnh, chi phí chìm và chi phí tìm kiếm.
- Một cảnh báo khác cũng được nêu: trong giai đoạn 2020 tới 2021 thế giới đối mặt nhiều gián đoạn liên quan đại dịch, còn năm 2022 Nga xâm lược Ukraine. Hậu quả kinh tế và chính sách của các cú sốc này, gồm phong toả, kích thích tài khoá, lạm phát cao và căng thẳng địa chính trị, không được mô hình hoá trong các phản thực và có thể phản ánh một phần trong chi phí thương mại suy ra từ dữ liệu.

### 6. Phản thực về lựa chọn khối

- Với mỗi nước, bài tính xem GDP và thu nhập sẽ thay đổi thế nào nếu nó thuộc một khối khác. Kỹ thuật quan trọng là thay chi phí thực tế của nước đó bằng chi phí bình quân của khối đích với mọi đối tác, rồi chuẩn hoá lại sao cho mức thay đổi chi phí bình quân gia quyền theo thương mại bằng đúng mức thực tế, nhằm tránh hiệu ứng mức mang tính cơ học. Phép thử được thực hiện từng nước một, giữ nguyên chi phí của mọi nước khác.
- Kết quả trung tâm là sáu trong mười nước khối Trung Quốc sẽ có lợi nếu chuyển sang khối Mỹ, và tám trong mười bốn nước khối Mỹ sẽ có lợi nếu chuyển sang khối Trung Quốc. Nói cách khác, trung bình mà nói các nước trong hai khối đang ở sai khối.
- Nhưng nước trong cả hai khối cũng sẽ thiệt nếu trở thành không liên kết, nên không phải cứ trung lập là tốt. Vài ngoại lệ đáng chú ý là Ả-rập Xê-út, Latvia và Lithuania sẽ thấy GDP tăng hơn hai phần trăm nếu trở thành không liên kết.
- Bài cũng nhấn mạnh rằng đằng sau các số trung vị là độ phân tán hoàn toàn: trong mọi loại di chuyển đều có cả kẻ thắng lẫn kẻ thua.
- Hàm ý được nêu thẳng: việc phân loại khối quan sát được trong dữ liệu khớp rất kém với lợi ích kinh tế liên quan tới thương mại, nên các động cơ khác, phỏng đoán là địa chính trị, nhiều khả năng đang chi phối việc sắp xếp lại dòng thương mại những năm gần đây.

### 7. Kiểm chứng độ vững

- Về thuế quan, vì mức tuyệt đối của thay đổi chi phí do mô hình định cỡ, có thể lo ngại kết quả phụ thuộc mô hình. Bài kiểm bằng cấu phần chi phí quan sát được trực tiếp là thuế quan, và thấy mức thay đổi bình quân gần bằng không với ba mươi chín phẩy năm phần trăm số cặp nước chứng kiến thuế quan giảm. Điều này khớp với ghi nhận rằng trong chiến tranh thương mại Mỹ và Trung Quốc, Trung Quốc hạ thuế tối huệ quốc với phần còn lại thế giới trong khi nâng thuế với Mỹ.
- Về phân loại khối, bài dùng thuật toán Leiden, một phương pháp học máy phát hiện cộng đồng không chồng lấn trong mạng lớn, chạy một trăm lượt. Với bảy mươi ba nước được cả hai phương pháp xếp vào khối Mỹ hoặc khối Trung Quốc, năm mươi hai nước tức bảy mươi mốt phần trăm được xếp vào cùng khối. Phương pháp cơ sở bảo thủ hơn ở chỗ xếp nhiều nước hơn vào nhóm không liên kết.
- Khi dùng 2016 làm năm gốc, phân loại tương tự và không nước nào trong mẫu mô hình bị xếp vào khối ngược lại.
- Kết quả cho giai đoạn trước COVID từ 2015 tới 2019 khác hẳn và rất đáng chú ý. Chi phí giữa khối Mỹ và khối Trung Quốc đã tăng trong mẫu này, nhưng mức giảm chi phí trong nội bộ khối kém rõ rệt hơn và gần như bằng không với khối Mỹ, khiến tổng chi phí tăng nhẹ. Kết quả là thu nhập thực của nước trung vị giảm không phẩy không sáu phần trăm thay vì tăng không phẩy sáu phần trăm.
- Điều này tiết lộ một trình tự thời gian thú vị: mức tăng chi phí giữa các khối đến trước, còn mức giảm trong nội bộ khối đến sau. Rõ ràng các nước cần một thời gian để giảm rào cản thương mại trong nội bộ khối sau cú sốc tách rời ban đầu. Bài cũng nêu cách diễn giải thay thế liên quan tới vai trò của COVID và cuộc xâm lược Ukraine.
- Bài thực hiện một phép thử giả dược với dữ liệu giai đoạn 2002 tới 2007, trước khi có căng thẳng Mỹ và Trung Quốc. Trong trường hợp đó không tìm thấy bằng chứng tách rời nào: chỉ ba nước được xếp vào khối Trung Quốc kể cả chính Trung Quốc, bảy mươi phần trăm số nước không liên kết, và mọi cặp khối kể cả từ khối Trung Quốc sang khối Mỹ đều chứng kiến chi phí thương mại giảm.
- Cuối cùng, để chứng minh phương pháp định cỡ bằng tỷ lệ thương mại trên GDP là đáng tin, bài áp dụng nó cho các năm có dữ liệu hấp thụ nội địa và so với phương pháp Head và Ries. Chênh lệch là âm không phẩy chín phần trăm ở trung bình và âm không phẩy không ba phần trăm ở trung vị, với tương quan không phẩy bảy chín.

### 8. Điều gì thực sự dẫn dắt

- Vì kết quả phản thực hàm ý rằng một số nước không nhất thiết chọn khối tối ưu về kinh tế, bài tìm hiểu các động lực khác của thay đổi hình mẫu thương mại sau 2015.
- Hồi quy thay đổi dòng thương mại song phương giữa 2015 và 2023 lên mức đồng thuận bỏ phiếu tại Đại hội đồng Liên Hợp Quốc năm 2015 cho hệ số dương và có ý nghĩa cao, trong khi hồi quy giả dược dùng giai đoạn 2010 tới 2015 không cho tương quan nào.
- Hai kết quả bổ sung cũng quan trọng. Dòng thương mại năm gốc có hệ số âm, trong khi dòng thương mại năm 2000 có hệ số dương. Điều này cho thấy thương mại tăng nhiều hơn với các cặp gần gũi về địa chính trị, và các nước rời xa đối tác năm 2015 để quay về với đối tác lịch sử năm 2000.
- Hồi quy kiểu nghiên cứu sự kiện với hiệu ứng cố định nước nhập khẩu theo năm, nước xuất khẩu theo năm và cặp nước xác nhận thêm. Trước năm 2015, mức đồng thuận bỏ phiếu không có tác động nào lên thương mại so với năm tham chiếu. Sau 2015, tương quan bắt đầu tăng và mạnh dần theo thời gian.
- Kết luận là giai đoạn 2015 tới 2017 đánh dấu khởi đầu của việc gia tăng vai trò các lực địa chính trị trong thương mại quốc tế. Sau 2015, các nước tăng thương mại với đồng minh trước 2015 của mình, đánh đổi bằng thương mại với các nước không phải đồng minh.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Decoupling | Tách rời, thay đổi nguồn và đích của dòng thương mại |
| Deglobalization | Phi toàn cầu hoá, sự sụt giảm tổng thể của thương mại |
| Fragmentation fault line | Đường đứt gãy phân mảnh trong dòng thương mại |
| Gravity equation | Phương trình lực hấp dẫn về thương mại song phương |
| Multilateral resistance | Sức cản đa phương, hấp thụ bởi hiệu ứng cố định nước |
| Residual | Phần dư, được diễn giải là thay đổi rào cản song phương |
| Trade elasticity | Độ co giãn thương mại, dùng để chuyển phần dư thành chi phí |
| Iceberg cost | Chi phí tảng băng, chỉ một phần hàng hoá tới được đích |
| Base trade cost shift | Dịch chuyển chi phí chung, định cỡ bằng tỷ lệ thương mại trên GDP |
| Model inversion | Đảo mô hình, kỹ thuật khôi phục chi phí từ dữ liệu thương mại |
| Domestic absorption | Hấp thụ nội địa, dữ liệu cần cho phương pháp Head–Ries |
| Head-Ries ratio | Tỷ số Head–Ries, cách tính chi phí thương mại song phương |
| ICIO | Bảng đầu vào và đầu ra liên quốc gia của OECD |
| DOTS | Thống kê Hướng Thương mại của IMF, phủ 187 nước tới 2023 |
| Exact-hat algebra | Đại số mũ chính xác, giải mô hình theo tỷ lệ thay đổi |
| Armington aggregate | Tổng hợp Armington, hàng phân biệt theo nơi sản xuất |
| GHH preferences | Sở thích Greenwood–Hercowitz–Huffman |
| Roy-Fréchet | Cách mô hình hoá lựa chọn ngành của người lao động |
| Frisch elasticity | Độ co giãn Frisch của cung lao động |
| Equipped labor | Lao động được trang bị, gộp mọi dịch vụ nhân tố sơ cấp |
| Real income | Thu nhập thực, tiền lương chia chỉ số giá tiêu dùng |
| Counterfactual | Phản thực, giả định nước đó thuộc khối khác |
| Bloc misalignment | Lệch khối, nước không ở khối tối ưu về kinh tế |
| Connector country | Nước kết nối, trung chuyển giữa các khối |
| Leiden algorithm | Thuật toán học máy phát hiện cộng đồng trong mạng |
| Ideal point distance | Khoảng cách điểm lý tưởng, đo gần gũi địa chính trị |
| UN vote agreement | Mức đồng thuận bỏ phiếu tại Đại hội đồng Liên Hợp Quốc |
| MFN tariff | Thuế tối huệ quốc, đo với ít sai số hơn thuế áp dụng thực |
| Friend-shoring | Đưa sản xuất về nước đồng minh |
| Placebo test | Phép thử giả dược dùng giai đoạn trước khi có cú sốc |

## Câu nói đáng nhớ

> "The world economy is experiencing decoupling, rather than deglobalization."

> "The bloc alignment uncovered in the data corresponds poorly to trade-related economic interests."

> "As cross-bloc trade costs went up, within-bloc trade costs fell."

## Đánh giá và phát hiện đáng chú ý

### Đóng góp thật là đảo ngược thứ tự: để dữ liệu vẽ bản đồ khối, thay vì vẽ trước rồi đo

Gần như toàn bộ văn liệu về phân mảnh làm theo một thứ tự: lấy một danh sách khối có sẵn — bỏ phiếu Liên Hợp Quốc, liên minh quân sự, danh sách trừng phạt — rồi đo xem thương mại giữa các khối đó giảm bao nhiêu. Khuyết tật khó chữa của cách làm đó là **kết quả được quyết định từ lúc vẽ bản đồ**, trước khi chạm vào một con số thương mại nào.

Bài này lật ngược: phần dư của phương trình lực hấp dẫn vẽ bản đồ, con người không can thiệp. Và bản đồ nó vẽ ra khác hẳn bản đồ trực giác — Ả-rập Xê-út, Israel và Hong Kong nằm trong khối Trung Quốc; Ấn Độ và Myanmar nằm trong khối Mỹ; Canada, Bỉ, Hà Lan, Mexico không liên kết. Nếu đặt trước bản đồ địa chính trị thì Israel không bao giờ rơi vào khối Trung Quốc, và ta sẽ không bao giờ biết rằng **chi phí thương mại thực tế của Israel đã dịch chuyển ngược với liên minh chính trị của nó**.

Nhưng đúng cái làm nên sức mạnh ấy cũng là điểm yếu. Phần dư, theo chính lời bài, hấp thụ mọi thứ không xảy ra ở cấp nước — chính sách thương mại, sở thích, biên lợi nhuận song phương, và tất cả những gì còn lại. Với Ả-rập Xê-út và Nga, thứ "còn lại" đó gần như chắc chắn là **tái định tuyến dòng dầu thô sau 2022**, một hiện tượng năng lượng chứ không phải một lựa chọn khối. Chiếc máy phân loại không phân biệt được "chọn phe" với "bán dầu cho người còn mua".

### Kết luận trung tâm sống hay chết là do cửa sổ thời gian, và bài đã tự nói ra điều đó

Đây là chỗ cần đọc kỹ nhất trong cả bài, và nó nằm khiêm tốn ở phần kiểm chứng độ vững.

Trên cửa sổ 2015–2023, nước trung vị **được lợi 0,6%** thu nhập thực. Trên cửa sổ 2015–2019, cũng phương pháp ấy, cũng mô hình ấy, nước trung vị **thiệt 0,06%**. Toàn bộ dấu của kết luận đảo chiều chỉ vì thêm vào bốn năm. Và bốn năm đó là 2020–2023: đại dịch, đứt gãy chuỗi cung ứng, gói kích thích khổng lồ, lạm phát, và một cuộc chiến tranh ở châu Âu.

Bài đưa ra hai cách diễn giải và tỏ ra nghiêng về cách thứ nhất: các nước cần thời gian để hạ rào cản trong nội bộ khối sau cú sốc ban đầu, nên chi phí giữa khối tăng trước, chi phí trong khối giảm sau. Cách thứ hai — mà bài nêu rồi đi tiếp — là những cú sốc 2020–2022 đã in dấu vào chính phần dư được diễn giải là chi phí thương mại.

Không có cách nào trong bài để phân định hai lời giải này, và **sự khác biệt giữa chúng là sự khác biệt giữa "tách rời có lợi" và "tách rời có hại"**. Nói cho công bằng: mệnh đề bền vững của bài không phải "tách rời làm tăng phúc lợi", mà là mệnh đề mô tả khiêm tốn hơn và chắc chắn hơn nhiều — thương mại Mỹ–Trung sụp 27,5% và 40,1% mà thương mại thế giới trên GDP vẫn tăng từ 21,8% lên 22,6%, nên **cái đang diễn ra là đổi nguồn và đổi đích, không phải co lại**. Nên trích dẫn bài ở mệnh đề đó, không phải ở con số 0,6%.

### Một mâu thuẫn nội tại mà bài trình bày cạnh nhau nhưng không nối lại

Hai kết quả sau nằm cách nhau vài trang và xung khắc trực tiếp:

- Nhóm **không liên kết được lợi nhiều nhất** trong kịch bản cơ sở, trung vị 0,787 so với 0,532 của khối Mỹ và 0,299 của khối Trung Quốc.
- Nhưng **trở thành không liên kết thì thiệt với mọi nước**: nước khối Mỹ mất 0,622, nước khối Trung Quốc mất 0,324.

Cách hoà giải nằm ở chỗ nhãn "không liên kết" đang gộp hai loại nước hoàn toàn khác nhau vào một ô. Loại thứ nhất là nước mà chi phí thương mại **giảm với cả hai bên** — Việt Nam, Lào — tức là được cả hai khối tranh nhau. Loại thứ hai là nước mà chi phí **tăng với cả hai** hoặc không nhúc nhích, tức là bị cả hai bỏ quên. Quy tắc phân loại của bài, vốn chỉ đọc dấu của hai chiều tương đối, ném cả hai vào chung một rổ 98 nước.

Hệ quả rất thực tế: **con số 0,787 không phải là phần thưởng cho trung lập**. Nó là phần thưởng cho việc được cả hai bên cần, và đó là một trạng thái phải giành lấy chứ không phải một tư thế ngoại giao có thể tuyên bố.

### Kết quả "ai cũng ở nhầm khối" yếu hơn vẻ ngoài của nó, nhưng hệ quả thì mạnh hơn

Phát hiện gây chú ý nhất là tính đối xứng: nước khối Trung Quốc sang khối Mỹ được thêm 0,658, nước khối Mỹ sang khối Trung Quốc được thêm 0,211. Cả hai chiều đều dương.

Cần thận trọng với chính tính đối xứng đó. Phép phản thực thay chi phí thực tế của một nước bằng **chi phí bình quân của khối đích** rồi chuẩn hoá lại. Với bất kỳ nước nào có chi phí lệch xa khỏi trung bình khối mình, thao tác này tự động kéo nó về gần trung bình — và trong một mô hình mà mọi đường cong đều lõm, kéo về trung bình gần như luôn cho hiệu ứng dương. Tỷ lệ 6/10 và 8/14 cũng rất nhỏ; nói "trung bình mà nói các nước đang ở sai khối" dựa trên 10 và 14 quan sát là mạnh hơn mức bằng chứng cho phép.

Nhưng nếu chấp nhận kết quả ở mức định tính thì hệ quả của nó sắc hơn nhiều so với điều bài dám viết. Hồi quy bỏ phiếu Liên Hợp Quốc cho hệ số **0,672 có ý nghĩa cao** ở giai đoạn 2015–2023 và **0,184 không có ý nghĩa** ở giai đoạn giả dược 2010–2015. Ghép với phản thực, thông điệp thật là: **việc chọn khối đang được quyết định bởi thứ không phải lợi ích thương mại, và các nước đang trả giá cho lựa chọn đó**. Đây là lời phê bình thẳng vào chính sách của cả Washington lẫn Bắc Kinh, được gói trong một câu trung tính về "các động cơ khác, phỏng đoán là địa chính trị".

### Việt Nam đứng đầu bảng, và đó là lý do phải đọc con số +6,9% dè dặt nhất

Việt Nam được lợi 6,9% thu nhập thực, cao nhất trong 66 nước, gấp hơn mười một lần nước trung vị. Một con số như thế đòi hỏi phải hỏi nó đến từ đâu trước khi mừng.

Nó đến từ một mô hình thương mại **tĩnh, lợi suất không đổi theo quy mô, chi phí tảng băng, không có tích luỹ vốn và không có chuyển giao công nghệ**. Toàn bộ lợi ích trong một mô hình như vậy là lợi ích tái phân bổ: hàng hoá đổi đường đi, Việt Nam nằm trên đường mới, phúc lợi tăng. Mô hình **không phân biệt được** giữa một nhà máy mới có thật và một chuyến hàng chỉ dán lại nhãn — cả hai đều hiện ra như chi phí thương mại song phương giảm.

Đây là chỗ cần đọc cùng tài liệu về thương mại và đầu tư của ASEAN trong một thế giới phân mảnh, vốn lập luận rằng cái phân biệt lợi ích bền với lợi ích ảo là **dòng vốn FDI cấp doanh nghiệp đi trước đơn hàng**. Bài này không có kênh đó và cũng nói rõ là chỉ xét liên kết thương mại, không xét FDI, kiều hối, chuyển giao công nghệ hay di cư. Nói cách khác, **6,9% là giới hạn trên của lợi ích, đo trong một thế giới nơi lắp ráp khâu cuối và sản xuất thực được tính như nhau**.

Hai hệ quả đáng giữ lại. Thứ nhất, vị thế của Việt Nam trong bài không phải là "trung lập" mà là "chi phí giảm với cả hai phía" — một trạng thái mong manh, vì chỉ cần một bên siết quy tắc xuất xứ là nửa cơ chế biến mất. Thứ hai, những kênh phân mảnh nguy hiểm nhất với Việt Nam lại **nằm đúng trong phần bài này loại ra khỏi phạm vi**: sàng lọc FDI, kiểm soát xuất khẩu công nghệ, và kênh thanh toán. Với một nền kinh tế còn kiểm soát tài khoản vốn và đồng tiền chưa chuyển đổi tự do, rủi ro ở kênh thanh toán và kênh đồng tiền không hiện lên trong bất kỳ con số nào ở đây — điều mà tài liệu về hạn chế thanh toán thương mại và kiểm soát vốn, cùng tài liệu về định giá bằng đồng tiền thống trị, xử lý trực tiếp hơn nhiều.

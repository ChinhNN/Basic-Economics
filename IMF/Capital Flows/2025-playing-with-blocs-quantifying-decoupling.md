# Playing with Blocs: Quantifying Decoupling — Chơi với các khối: định lượng quá trình tách rời

**Nguồn:** IMF Working Paper WP/25/263, Vụ Nghiên cứu, tháng 12/2025 (Antonio Spilimbergo cho phép phát hành).
**Tác giả:** Barthélémy Bonadio (NYU Abu Dhabi), Zhen Huo (Yale), Elliot Kang (PwC và Đại học Minnesota), Andrei A. Levchenko (Đại học Michigan), Nitya Pandalai-Nayar (Đại học Texas tại Austin), Hiroshi Toma (Texas A&M), Petia Topalova (IMF).
**Ý chính:** Sau Brexit, chiến tranh thương mại Mỹ–Trung và việc phương Tây cắt quan hệ với Nga, ai cũng chờ thương mại thế giới sụt giảm. Nhưng tỷ lệ thương mại trên GDP toàn cầu **không hề giảm** kể từ 2015. Bài dùng phần dư của phương trình lực hấp dẫn để **tự động phát hiện đường đứt gãy** giữa các khối mà không cần giả định trước, rồi đưa vào mô hình mạng sản xuất toàn cầu 66 nước và 22 ngành. Kết luận trung tâm: thế giới đang **tách rời chứ không phi toàn cầu hoá** — chi phí thương mại giữa hai khối tăng, nhưng **trong nội bộ mỗi khối lại giảm nhiều hơn**, khiến nước trung vị **được lợi 0,6% thu nhập thực**. Phát hiện gây bất ngờ nhất nằm ở phần phản thực: **các nước đang ở nhầm khối** — nước nghiêng về Mỹ trung bình sẽ có lợi hơn nếu sang khối Trung Quốc, và ngược lại. Điều đó hàm ý động cơ chi phối việc chọn phe **không phải là lợi ích thương mại**.

> **Lưu ý:** bản tổng hợp này ban đầu viết từ một bản PDF thiếu trang bìa và trang tác giả; tên tác giả, đơn vị và thời điểm phát hành được bổ sung sau từ bản PDF đầy đủ. Bài được tài trợ một phần bởi chương trình Chính sách kinh tế vĩ mô ở các nước thu nhập thấp của Bộ Ngoại giao, Khối thịnh vượng chung và Phát triển Anh, và chương trình Nghiên cứu kinh tế vĩ mô về biến đổi khí hậu và rủi ro mới nổi ở châu Á của Bộ Kinh tế và Tài chính Hàn Quốc. Mục "trích dẫn khuyến nghị" ở trang tóm tắt chỉ ghi "Bonadio et al. (2025)", không có tên bài và số hiệu. Bản tổng hợp ghi thuế quan trong chiến tranh thương mại Mỹ–Trung "có hiệu lực từ 2017"; theo hiểu biết chung các đợt thuế quan này bắt đầu có hiệu lực từ năm 2018, nên năm 2017 đáng ngờ (có thể chép nhầm), nhưng không có bản gốc để đối chiếu nên giữ nguyên.

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

## Khái niệm cần biết

**Tách rời và phi toàn cầu hoá (decoupling, deglobalization).** Phi toàn cầu hoá là khi tổng thương mại thế giới co lại so với quy mô nền kinh tế. Tách rời là khi tổng thương mại không giảm nhưng **đổi hướng**: hai nước hay hai khối buôn bán với nhau ít đi và buôn bán với nước khác nhiều hơn. Ví dụ từ bài: từ 2015 đến 2023, xuất khẩu của Mỹ sang Trung Quốc tính trên GDP giảm 27,5%, nhưng tỷ lệ thương mại trên GDP thế giới vẫn tăng từ 21,8% lên 22,6%. Phân biệt này là kết luận trung tâm của bài.

**Phương trình lực hấp dẫn (gravity equation).** Quy luật thực nghiệm rằng thương mại giữa hai nước tỷ lệ thuận với quy mô kinh tế của hai nước và tỷ lệ nghịch với rào cản giữa chúng, như khoảng cách, thuế quan hay khác biệt ngôn ngữ, giống lực hút giữa hai vật. Ví dụ minh hoạ: hai nước lớn gấp đôi thì buôn bán với nhau nhiều hơn, còn hai nước xa gấp đôi thì buôn bán ít hơn. Bài dùng phương trình này để tách phần thay đổi thương mại do chính quan hệ của từng cặp nước.

**Hiệu ứng cố định và phần dư.** Hiệu ứng cố định là một biến riêng cho từng nước, hấp thụ mọi thứ xảy ra với nước đó nói chung (kinh tế tăng trưởng, giá cả thay đổi, thuế quan áp cho mọi đối tác). Phần dư là phần thay đổi thương mại còn lại sau khi đã trừ hết những thứ đó, tức phần chỉ riêng cặp nước ấy mới có. Ví dụ minh hoạ: nếu xuất khẩu của Việt Nam đi mọi nơi đều tăng 10%, nhưng riêng sang Mỹ tăng 30%, thì phần dư của cặp Việt Nam–Mỹ phản ánh 20% chênh thêm. Bài coi phần dư này là thay đổi rào cản thương mại song phương và dùng nó để phát hiện khối.

**Chi phí thương mại và chi phí tảng băng (iceberg cost).** Chi phí thương mại gồm mọi thứ làm hàng hoá đắt hơn khi bán ra nước ngoài: thuế quan, vận tải, thủ tục, rủi ro chính trị. "Tảng băng" là cách mô hình hoá: gửi đi 1 đơn vị hàng thì chỉ một phần tới nơi, như tảng băng tan dọc đường. Ví dụ từ bài: chi phí từ khối Trung Quốc sang khối Mỹ tăng 11,4%, nghĩa là bán cùng một lượng hàng sang đó đắt hơn khoảng 11,4%. Đây là đại lượng mà bài đo rồi đưa vào mô hình.

**Độ co giãn thay thế Armington và độ co giãn thương mại (trade elasticity).** Độ co giãn thay thế (ký hiệu γ) đo mức người mua dễ chuyển từ hàng nước này sang hàng nước khác khi giá tương đối thay đổi; bài dùng γ = 4 (Broda và Weinstein 2006). Từ đó suy ra độ co giãn thương mại, tức thương mại giảm bao nhiêu phần trăm khi chi phí tăng 1%, bằng γ − 1 = 3 về độ lớn. Ví dụ minh hoạ: chi phí thương mại của một cặp nước tăng 1% thì thương mại giữa họ giảm khoảng 3%; ngược lại, thấy thương mại giảm thêm 3% thì suy ra chi phí đã tăng khoảng 1%. Đây là cách bài chuyển phần dư (thay đổi thương mại) thành thay đổi chi phí, qua công thức Δln τ = ŵ / (1 − γ).

**GDP thực và thu nhập thực.** GDP thực đo sản lượng theo giá cố định của năm gốc. Thu nhập thực đo tiền lương chia cho chỉ số giá tiêu dùng, nên nó tính cả việc hàng nhập khẩu rẻ đi hay đắt lên. Ví dụ minh hoạ: nếu chi phí nhập khẩu giảm làm hàng tiêu dùng rẻ đi 1% trong khi lương không đổi, GDP thực có thể không đổi nhưng thu nhập thực tăng khoảng 1%. Bài báo cáo cả hai, và kết luận chính dùng thu nhập thực.

**Phản thực (counterfactual).** Phép thử "nếu như" trong mô hình: giữ mọi thứ khác như thực tế, chỉ thay một điều để xem kết quả khác đi bao nhiêu. Ví dụ từ bài: nếu một nước khối Trung Quốc có cấu trúc chi phí của khối Mỹ thì GDP thực trung vị cao hơn 0,658 điểm phần trăm. Đây là cách bài đưa ra kết luận "các nước đang ở nhầm khối".

**Phép thử giả dược (placebo test).** Lặp lại đúng phân tích cho một giai đoạn mà ta biết chắc không có hiện tượng cần tìm. Nếu phương pháp vẫn "phát hiện" ra hiện tượng thì nó đáng ngờ. Ví dụ từ bài: áp dụng cho 2002–2007, trước căng thẳng Mỹ–Trung, chỉ 3 nước bị xếp vào khối Trung Quốc kể cả chính Trung Quốc. Đây là bằng chứng phương pháp không tự tạo ra khối.

## Nội dung chi tiết

### 1. Nghịch lý mở đầu

Sau một kỷ nguyên dài hội nhập ngày càng sâu, thập kỷ qua chứng kiến nhiều lực cản mạnh với hội nhập kinh tế: Brexit, chiến tranh thương mại giữa Mỹ và Trung Quốc, và việc quan hệ kinh tế giữa phương Tây với Nga bị cắt đứt. Người ta thường tự hỏi liệu đây có phải khởi đầu của phi toàn cầu hoá.

Nhưng nhìn vào tỷ lệ thương mại hàng hoá trên GDP trong giai đoạn 1985–2023, lấy năm 2015 làm mốc (trước trưng cầu Brexit và trước bầu cử Mỹ năm 2016), thì thấy:

- **Thế giới:** tỷ lệ này vẫn kiên cường; thực ra còn đảo ngược một phần xu hướng giảm bắt đầu từ năm 2009.
- **Hoa Kỳ, Trung Quốc, Liên minh châu Âu:** không có sụt giảm rõ rệt nào.

Tức là ngay cả các bên chính trong xung đột thương mại cũng không thấy tổng thương mại của mình giảm.

Lời giải nằm ở việc nhìn thương mại theo từng cặp. Bảng dưới cho thay đổi tỷ lệ nhập khẩu trên GDP giữa 2015 và 2023 (hàng là nước xuất khẩu, cột là nước nhập khẩu; số liệu là thay đổi tỷ lệ, ví dụ −0,275 nghĩa là giảm 27,5%):

| Xuất khẩu từ \ Nhập khẩu vào | Hoa Kỳ | Trung Quốc | EU | Phần còn lại |
|---|---|---|---|---|
| Hoa Kỳ | — | −0,275 | +0,262 | +0,015 |
| Trung Quốc | −0,401 | — | +0,237 | +0,137 |
| EU | +0,050 | −0,066 | +0,148 | −0,014 |
| Phần còn lại | +0,012 | +0,047 | +0,035 | +0,105 |
| **Tổng nhập khẩu/GDP** | **−0,070** | **+0,005** | **+0,128** | **+0,076** |

Thương mại Mỹ–Trung sụp mạnh: nhập khẩu của Trung Quốc từ Mỹ giảm 27,5%, nhập khẩu của Mỹ từ Trung Quốc giảm 40,1%. Nhưng thương mại của cả hai với EU và phần còn lại của thế giới đều tăng. Nói cách khác, ngay cả khi các nước trong xung đột thương mại rút khỏi nhau, họ lại tăng thương mại với các nước khác. Kết luận của bài: "Nền kinh tế thế giới đang trải qua tách rời, chứ không phải phi toàn cầu hoá."

### 2. Phương pháp phát hiện khối

Bài dùng cách tiếp cận hoàn toàn dựa trên dữ liệu để phát hiện đường đứt gãy phân mảnh trong dòng thương mại quốc tế, thay vì giả định trước nước nào thuộc phe nào. Có hai bước.

**Bước 1: phương trình lực hấp dẫn lấy sai phân logarit.** Dựa vào truyền thống lực hấp dẫn trong đo chi phí thương mại, bài hồi quy thay đổi logarit của thương mại hàng hoá song phương giai đoạn 2015–2023 lên sức cản đa phương, thể hiện qua hiệu ứng cố định nước xuất khẩu và nước nhập khẩu:

Δln X(m,n) = δ(m) + δ(n) + w(m,n)

Vế trái là thay đổi log xuất khẩu từ nước m sang nước n; δ(m) và δ(n) là hiệu ứng cố định của nước xuất khẩu và nước nhập khẩu; w(m,n) là phần dư.

Các hiệu ứng cố định hấp thụ toàn bộ: cú sốc cung và cầu riêng của từng nước, thay đổi chỉ số giá, và mọi thay đổi rào cản thương mại xảy ra ở cấp nước (áp cho mọi đối tác) chứ không phải cấp cặp nước. Phần dư do đó phản ánh thay đổi của toàn bộ rào cản thương mại song phương giữa m và n, cả quan sát được lẫn không quan sát được.

Bài nói rõ rằng theo thông lệ, họ không tách được nguồn gốc của những thay đổi này. Chúng có thể phản ánh thay đổi chính sách thương mại, dịch chuyển sở thích của người mua, thay đổi biên lợi nhuận song phương, hoặc các cú sốc song phương khác ảnh hưởng tới rào cản.

Phần dư được chuyển thành thay đổi chi phí thương mại bằng công thức Δln τ = ŵ / (1 − γ), trong đó γ là độ co giãn thay thế giữa các nguồn hàng (bằng 4 trong mô hình). Ví dụ minh hoạ: phần dư −0,3 (thương mại giảm thêm khoảng 30% so với dự đoán) tương ứng chi phí tăng khoảng 0,3/3 = 0,1, tức khoảng 10%.

Bài chọn 2015 làm năm gốc vì trưng cầu Brexit và bầu cử Trump năm 2016 là hai sự kiện lớn đầu tiên của kỷ nguyên tách rời; kết thúc ở 2023 để bao gồm hậu quả của việc Nga xâm lược Ukraine năm 2022.

**Bước 2: quy tắc phân loại khối.** Quy tắc rất đơn giản, dựa trên thay đổi chi phí thương mại bình quân của mỗi nước với Mỹ và với Trung Quốc:

| | Chi phí với Trung Quốc giảm | Chi phí với Trung Quốc tăng |
|---|---|---|
| **Chi phí với Mỹ giảm** | Không liên kết | **Khối Hoa Kỳ** |
| **Chi phí với Mỹ tăng** | **Khối Trung Quốc** | Không liên kết |

Mọi nước có chi phí với hai bên cùng tăng hoặc cùng giảm đều là không liên kết.

Bài nhấn mạnh một điểm quan trọng: phân loại dựa trên **thay đổi** chi phí thương mại tương đối, không dựa trên **mức** thương mại song phương ban đầu. Do đó một nước có dòng thương mại ban đầu rất lớn với Mỹ vẫn có thể bị xếp vào khối Trung Quốc nếu chi phí tương đối của nó với Trung Quốc giảm còn với Mỹ tăng trong giai đoạn này. Bài cũng nói rõ chỉ xét liên kết thương mại, không xét đầu tư trực tiếp nước ngoài, kiều hối, chuyển giao công nghệ hay chính sách di cư.

**Kết quả phân loại.** Trong 187 nước có dữ liệu (theo Thống kê Hướng Thương mại DOTS của IMF):

| Nhóm | Số nước |
|---|---|
| Khối Hoa Kỳ | 43 |
| Khối Trung Quốc | 46 |
| Không liên kết | 98 (đa số) |

Một số trường hợp trong mẫu mô hình gây bất ngờ:

- **Rõ ràng nghiêng về Trung Quốc:** Nga, Ả-rập Xê-út, Israel, Hong Kong, Brazil, Colombia, Indonesia, Malaysia, Campuchia, Slovenia.
- **Nghiêng về Hoa Kỳ:** chủ yếu là các nước châu Âu, nhưng cũng có Ấn Độ, Hàn Quốc, Nhật Bản, Singapore và Myanmar.
- **Không liên kết:** Canada, Thuỵ Sĩ, Bỉ, Hà Lan, Pháp, Ý, Tây Ban Nha, Mexico, Việt Nam, Nam Phi, Thái Lan.

Những trường hợp như Israel trong khối Trung Quốc hay Myanmar trong khối Mỹ cho thấy rõ phân loại này đo hướng thay đổi của chi phí thương mại, không đo quan hệ chính trị hay mức thương mại.

### 3. Định cỡ mức chi phí

**Thách thức kỹ thuật.** Hồi quy lực hấp dẫn chỉ nhận diện được thay đổi chi phí tương đối, so với một cặp nước bị bỏ ra làm mốc, chứ không cho biết mức tuyệt đối. Tức là ta biết chi phí Mỹ–Trung tăng nhiều hơn chi phí Mỹ–EU bao nhiêu, nhưng không biết cả hai cùng tăng hay cùng giảm. Đồng thời không thể dùng kỹ thuật đảo mô hình thông thường (suy ngược chi phí từ dữ liệu thương mại) vì cách đó cần dữ liệu hấp thụ nội địa (phần sản lượng một nước tự tiêu dùng), mà dữ liệu này chưa có cho năm 2023.

**Giải pháp: dùng chính mô hình để định cỡ.** Bài nhân thang toàn bộ ma trận thay đổi chi phí suy ra từ hồi quy với một hệ số chung:

τ̂ = exp[Δln τ(m,n) + Δln τ^cơ_sở], với mọi m ≠ n

Phần đầu là thay đổi tương đối của từng cặp; phần sau là một dịch chuyển chung cho mọi cặp. Bài tìm giá trị dịch chuyển chung sao cho tỷ lệ thương mại trên GDP thế giới trong mô hình khớp với dữ liệu: từ 21,8% năm 2015 lên 22,6% năm 2023, tức tăng 0,8 điểm phần trăm. Cách này giữ nguyên toàn bộ tính không đồng nhất ở cấp cặp nước, đồng thời khớp với xu hướng thương mại thế giới.

**Kết quả:** dịch chuyển chung bằng −0,003. Nghĩa là nếu có gì thì chi phí thương mại bình quân đã giảm khoảng 0,3%, chứ không tăng.

**Giả định đi kèm.** Mọi thay đổi trong dòng thương mại song phương sau khi trừ hiệu ứng cố định nước đều được quy cho thay đổi chi phí thương mại. Mô hình có thể chứa các cú sốc chuẩn như năng suất hay cầu, nhưng chúng đã bị hiệu ứng cố định nước hấp thụ. Bài cũng không xét riêng các cú sốc song phương khác như thay đổi biên lợi nhuận mà nhà xuất khẩu áp cho một nước nhập khẩu cụ thể, thay đổi hình mẫu sản xuất năng lượng toàn cầu, hay thay đổi dòng di cư, kiều hối và đầu tư.

**Chi phí thương mại giữa các khối** (đã gồm dịch chuyển chung; hàng là bên xuất khẩu, cột là bên nhập khẩu; số liệu là thay đổi log, xấp xỉ phần trăm khi nhân 100):

| Xuất khẩu từ \ Nhập khẩu vào | Khối Hoa Kỳ | Khối Trung Quốc | Không liên kết | Tổng |
|---|---|---|---|---|
| Khối Hoa Kỳ | −0,046 | +0,040 | +0,004 | −0,003 |
| Khối Trung Quốc | +0,114 | −0,072 | +0,023 | +0,050 |
| Không liên kết | −0,033 | −0,035 | −0,008 | −0,024 |
| **Tổng** | **+0,002** | **−0,012** | **+0,003** | **0,000** |

Ba điều cần đọc trong bảng này:

1. **Chi phí giữa hai khối đúng là tăng:** từ khối Trung Quốc sang khối Mỹ tăng 11,4%, chiều ngược lại tăng 4,0%.
2. **Nhưng chi phí trong nội bộ mỗi khối giảm**, −4,6% trong khối Mỹ và −7,2% trong khối Trung Quốc, và chi phí nhập khẩu từ nhóm không liên kết cũng giảm. Các mức giảm này bù đắp cho mức tăng giữa hai khối.
3. **Ô góc dưới bên phải bằng đúng 0,000.** Chỉ khối Trung Quốc chịu mức tăng chi phí xuất khẩu tổng thể (+0,050); không khối nào chịu mức tăng chi phí nhập khẩu tổng thể đáng kể.

Kết luận của bài: "dù tách rời đã xảy ra, chi phí thương mại tổng thể không tăng".

### 4. Mô hình định lượng

Để biết các thay đổi chi phí trên tác động tới GDP và thu nhập của từng nước ra sao, bài đưa chúng vào một mô hình mạng sản xuất toàn cầu đa quốc gia đa ngành, theo Huo, Levchenko và Pandalai-Nayar (2025) và Bonadio và cộng sự. Mô hình có 66 nước và 22 ngành, dùng bảng đầu vào và đầu ra liên quốc gia (ICIO) của OECD bản 2021, và được giải bằng đại số mũ chính xác (*exact-hat algebra*), tức giải trực tiếp theo tỷ lệ thay đổi so với năm gốc mà không cần biết mọi tham số mức.

**Các thành phần:**

- **Hộ gia đình** có sở thích kiểu Greenwood, Hercowitz và Huffman (GHH) ở cấp tổng, nghĩa là cung lao động tổng không bị hiệu ứng thu nhập kéo xuống. Nhưng cung lao động theo từng ngành co giãn đẳng trị theo lương tương đối của ngành đó, theo cách xây dựng kiểu Roy và Fréchet: người lao động chọn ngành trả lương tốt hơn, nhưng không chuyển hết ngay vì mỗi người hợp với mỗi ngành khác nhau.
- **Doanh nghiệp** có lợi suất không đổi theo quy mô.
- **Thương mại** chịu chi phí tảng băng.
- **Tiêu dùng cuối và đầu vào trung gian** đều có hai tầng: tầng trên gộp các ngành rộng, tầng dưới là tổng hợp Armington các mặt hàng từ các nước nguồn khác nhau (hàng cùng loại nhưng sản xuất ở nước khác được coi là khác nhau).

**Tham số:**

| Tham số | Ý nghĩa | Giá trị và nguồn |
|---|---|---|
| ρ, ε | Độ thay thế giữa các ngành | 1 |
| γ, ν | Độ thay thế giữa các nguồn gốc (Armington) | 4 (Broda–Weinstein 2006) |
| ψ | Độ co giãn Frisch của cung lao động | 1 (Chetty và cộng sự 2011) |
| μ | Độ co giãn cung lao động theo ngành | 1,5 (Galle và cộng sự 2023) |

**Hai thước đo kết quả.** GDP thực là đại lượng quen thuộc được hệ thống tài khoản quốc gia theo dõi. Nhưng vì giữ giá ở mức trước cú sốc, nó không tính tới việc thay đổi chi phí thương mại làm thay đổi giá hàng nhập khẩu, vốn nằm trong chỉ số giá tiêu dùng. Vì vậy bài cũng báo cáo thu nhập thực.

### 5. Kết quả cơ sở

Thay đổi GDP thực và thu nhập thực (điểm phần trăm), theo phân vị 25, trung vị và phân vị 75 trong mỗi nhóm:

| Nhóm | GDP thực: p25 | GDP thực: trung vị | GDP thực: p75 | Thu nhập thực: p25 | Thu nhập thực: trung vị | Thu nhập thực: p75 |
|---|---|---|---|---|---|---|
| **Tổng thể** | 0,061 | 0,588 | 1,297 | 0,059 | 0,619 | 1,322 |
| Khối Hoa Kỳ | 0,125 | 0,532 | 0,712 | 0,147 | 0,536 | 0,699 |
| Khối Trung Quốc | −0,263 | 0,299 | 0,773 | −0,261 | 0,372 | 0,780 |
| Không liên kết | 0,034 | 0,787 | 1,397 | 0,066 | 0,755 | 1,432 |

**Đọc bảng này.**

- Nước trung vị được lợi khoảng 0,6% về cả GDP thực lẫn thu nhập thực, trái với trực giác thông thường rằng tách rời làm giảm GDP thế giới. 51 trong 66 nước có thu nhập thực tăng, và ba phần tư số nước tăng ở cả hai chỉ tiêu. Trung vị dương ở mọi khối.
- Nhóm không liên kết được lợi nhiều nhất (GDP thực trung vị 0,787), điều bài giải thích bằng việc họ không tăng chi phí thương mại với bất kỳ khối nào một cách hệ thống.
- Chỉ khối Trung Quốc có phân vị 25 âm, tức ít nhất một phần tư số nước trong khối bị thiệt.
- Hoa Kỳ và Trung Quốc tự thân gần như không thay đổi.

**Phân rã.** Khoảng 90% mức thay đổi thu nhập thực đến từ thay đổi chi phí tương đối song phương (0,574 trên tổng 0,637), chỉ 0,074 đến từ mức giảm chung 0,3%. Điều này quan trọng vì nó cho thấy kết luận không phụ thuộc vào bước định cỡ mức chi phí bằng mô hình.

**Hai cực của phân bố.**

- **Được lợi nhất:** Việt Nam (+6,9%) và Lào (+3,5%). Cả hai đều chứng kiến chi phí thương mại giảm với cả Mỹ lẫn Trung Quốc, nên bị xếp là không liên kết, nhưng mô hình cho thấy thương mại song phương với họ tăng mạnh. Điều này khớp với các tường thuật về chuỗi cung ứng dịch chuyển khỏi Trung Quốc sang các nước như Việt Nam.
- **Thiệt hại nhất:** các nước Baltic, mất từ 3% tới 5%. Quan hệ thương mại chặt chẽ của họ với Nga bị đứt gãy mà không có mức giảm chi phí bù đắp ở nơi khác.

**Giới hạn của mô phỏng.** Bài nêu rõ mô phỏng bỏ qua nhiều kênh mà thay đổi chi phí thương mại có thể ảnh hưởng tới thu nhập thực: hiệu ứng năng suất động và chuyển giao tri thức; lợi suất tăng theo quy mô; và ma sát trong tái phân bổ và đa dạng hoá chuỗi cung ứng phát sinh từ hợp đồng không hoàn chỉnh, chi phí chìm và chi phí tìm kiếm đối tác.

Một cảnh báo khác: trong giai đoạn 2020–2021 thế giới đối mặt nhiều gián đoạn liên quan đại dịch, còn năm 2022 Nga xâm lược Ukraine. Hậu quả kinh tế và chính sách của các cú sốc này, gồm phong toả, kích thích tài khoá, lạm phát cao và căng thẳng địa chính trị, không được mô hình hoá trong các phản thực, và có thể phản ánh một phần trong chi phí thương mại suy ra từ dữ liệu.

### 6. Phản thực về lựa chọn khối

**Ý tưởng.** Với mỗi nước, bài tính xem GDP và thu nhập sẽ thay đổi thế nào nếu nó thuộc một khối khác.

**Kỹ thuật.** Thay chi phí thực tế của nước đó bằng chi phí bình quân của khối đích với mọi đối tác, rồi chuẩn hoá lại sao cho mức thay đổi chi phí bình quân gia quyền theo thương mại bằng đúng mức thực tế. Bước chuẩn hoá này nhằm tránh hiệu ứng mức mang tính cơ học: nếu khối đích có chi phí bình quân giảm nhiều hơn, nước đó sẽ "được lợi" chỉ vì chi phí chung thấp hơn, chứ không phải vì cấu trúc đối tác tốt hơn. Phép thử được thực hiện từng nước một, giữ nguyên chi phí của mọi nước khác ở giá trị thực tế.

**Kết quả** (thay đổi so với thực tế, trung vị, điểm phần trăm):

| Di chuyển | Nước xuất phát | GDP thực | Thu nhập thực |
|---|---|---|---|
| Sang khối Hoa Kỳ | Nước khối Trung Quốc | +0,658 (6/10 nước được lợi) | +0,661 |
| Sang khối Hoa Kỳ | Nước không liên kết | −0,710 | −0,762 |
| Sang khối Trung Quốc | Nước khối Hoa Kỳ | +0,211 (8/14 nước được lợi) | +0,238 |
| Sang khối Trung Quốc | Nước không liên kết | −0,501 | −0,476 |
| Sang nhóm không liên kết | Nước khối Hoa Kỳ | −0,622 | −0,629 |
| Sang nhóm không liên kết | Nước khối Trung Quốc | −0,324 | −0,328 |

**Đọc cùng nhau dòng đầu của mỗi khối.** Nước đang nghiêng về Trung Quốc sẽ có lợi hơn nếu sang khối Mỹ: sáu trong mười nước khối Trung Quốc được lợi. Nước đang nghiêng về Mỹ sẽ có lợi hơn nếu sang khối Trung Quốc: tám trong mười bốn nước khối Mỹ được lợi. Nói cách khác, "trung bình mà nói, các nước trong khối Mỹ và khối Trung Quốc đang ở 'sai' khối".

**Nhưng không phải cứ trung lập là tốt.** Nước trong cả hai khối cũng sẽ thiệt nếu trở thành không liên kết (−0,622 và −0,324). Vài ngoại lệ đáng chú ý là Ả-rập Xê-út, Latvia và Lithuania sẽ thấy GDP tăng hơn 2% nếu trở thành không liên kết.

Bài cũng nhấn mạnh rằng đằng sau các số trung vị là độ phân tán hoàn toàn: trong mọi loại di chuyển đều có cả kẻ thắng lẫn kẻ thua.

**Hàm ý được nêu thẳng.** "Việc phân loại khối quan sát được trong dữ liệu khớp rất kém với lợi ích kinh tế liên quan tới thương mại." Vì vậy các động cơ khác, mà bài phỏng đoán là địa chính trị, nhiều khả năng đang chi phối việc sắp xếp lại dòng thương mại những năm gần đây.

### 7. Kiểm chứng độ vững

**Thuế quan: bằng chứng quan sát được trực tiếp.** Vì mức tuyệt đối của thay đổi chi phí do mô hình định cỡ, có thể lo ngại kết quả phụ thuộc mô hình. Bài kiểm bằng cấu phần chi phí thương mại quan sát được trực tiếp là thuế quan, theo nguồn UN-TRAINS giai đoạn 2015–2021. Mức thay đổi bình quân gần bằng 0, và 39,5% số cặp nước chứng kiến thuế quan giảm. Điều này khớp với Bown, Jung và Zhang (2019): trong chiến tranh thương mại Mỹ–Trung, Trung Quốc hạ thuế tối huệ quốc (mức thuế áp chung cho mọi thành viên WTO) với phần còn lại thế giới trong khi nâng thuế với Mỹ.

**Thuật toán Leiden: một cách phân khối hoàn toàn khác.** Đây là phương pháp học máy phát hiện cộng đồng không chồng lấn trong mạng lớn, tức tìm các nhóm nước buôn bán với nhau nhiều hơn với bên ngoài. Vì thuật toán có thành phần ngẫu nhiên, bài chạy 100 lượt rồi xếp nước theo tỷ lệ số lần nước đó nằm cùng cộng đồng với Mỹ hoặc Trung Quốc. Với 73 nước được cả hai phương pháp xếp vào khối Mỹ hoặc khối Trung Quốc, 52 nước, tức 71%, được xếp vào cùng khối. Phương pháp cơ sở bảo thủ hơn ở chỗ xếp nhiều nước hơn vào nhóm không liên kết.

**Năm gốc và năm cuối thay thế.**

- Dùng 2016 làm năm gốc (thuế quan trong chiến tranh thương mại Mỹ–Trung có hiệu lực từ 2017): phân loại tương tự, và không nước nào trong mẫu mô hình bị xếp vào khối ngược lại so với cơ sở.
- Giai đoạn trước COVID, 2015–2019: kết quả khác hẳn và rất đáng chú ý. Chi phí giữa khối Mỹ và khối Trung Quốc đã tăng trong giai đoạn này, nhưng mức giảm chi phí trong nội bộ khối kém rõ rệt hơn và gần như bằng không với khối Mỹ, khiến tổng chi phí thương mại tăng nhẹ. Thu nhập thực của nước trung vị giảm 0,06%, thay vì tăng 0,6% như ở giai đoạn 2015–2023.

Điều này tiết lộ một trình tự thời gian: mức tăng chi phí giữa các khối đến trước, còn mức giảm trong nội bộ khối đến sau. Theo bài, "rõ ràng các nước cần một thời gian để giảm rào cản thương mại trong nội bộ khối sau cú sốc tách rời Mỹ–Trung ban đầu". Bài cũng nêu cách diễn giải thay thế: COVID và cuộc xâm lược Ukraine năm 2022, cùng những thay đổi kinh tế và chính sách mà các cú sốc lớn này gây ra, cũng có thể ảnh hưởng tới rào cản song phương.

**Phép thử giả dược 2002–2007**, trước khi có căng thẳng Mỹ–Trung. Không tìm thấy bằng chứng tách rời nào: chỉ 3 nước được xếp vào khối Trung Quốc, kể cả chính Trung Quốc; 70% số nước không liên kết (so với khoảng 60% ở kết quả cơ sở); và mọi cặp khối, kể cả từ khối Trung Quốc sang khối Mỹ, đều chứng kiến chi phí thương mại giảm.

**Kiểm chứng phương pháp định cỡ.** Để chứng minh cách định cỡ bằng tỷ lệ thương mại trên GDP là đáng tin, bài áp dụng nó cho các năm có dữ liệu hấp thụ nội địa (chỉ có tới 2010), trên các cửa sổ 8 năm bắt đầu từ 2000, rồi so với phương pháp Head và Ries (tính chi phí thương mại song phương trực tiếp từ dữ liệu thương mại và hấp thụ nội địa). Chênh lệch là −0,9% ở trung bình và −0,03% ở trung vị, với hệ số tương quan 0,79.

### 8. Điều gì thực sự dẫn dắt

Vì kết quả phản thực hàm ý một số nước không nhất thiết chọn khối tối ưu về kinh tế, bài tìm hiểu các động lực khác của thay đổi hình mẫu thương mại sau 2015. Biến được thử là mức đồng thuận bỏ phiếu tại Đại hội đồng Liên Hợp Quốc năm 2015, một thước đo mức gần gũi địa chính trị giữa hai nước.

Hồi quy thay đổi dòng thương mại song phương giữa 2015 và 2023 lên các biến sau, so với một hồi quy giả dược cho giai đoạn 2010–2015:

| Biến | 2015–2023 | Giả dược 2010–2015 |
|---|---|---|
| Đồng thuận bỏ phiếu Liên Hợp Quốc | 0,672\*\*\* | 0,184 (không có ý nghĩa) |
| Log dòng thương mại năm gốc | −0,423\*\*\* | −0,354\*\*\* |
| Log dòng thương mại năm 2000 | +0,148\*\*\* | +0,0957\*\*\* |
| Log khoảng cách địa lý | −0,288\*\*\* | −0,291\*\*\* |

Hai cách đọc quan trọng:

1. Các cặp nước bỏ phiếu giống nhau tại Đại hội đồng năm 2015 chứng kiến thương mại song phương tăng tương đối sau đó (hệ số 0,672, có ý nghĩa cao). Ở giai đoạn giả dược thì không có tương quan nào. Tức là gần gũi địa chính trị chỉ bắt đầu quan trọng với thương mại từ sau 2015.
2. Dòng thương mại năm gốc có hệ số âm, còn dòng thương mại năm 2000 có hệ số dương. Theo bài, điều này cho thấy "thương mại tăng nhiều hơn với các cặp gần gũi về địa chính trị, và các nước rời xa đối tác năm 2015 để quay về với đối tác lịch sử năm 2000".

**Nghiên cứu sự kiện.** Hồi quy với hiệu ứng cố định nước nhập khẩu theo năm, nước xuất khẩu theo năm và cặp nước xác nhận thêm: trước năm 2015, hệ số của đồng thuận bỏ phiếu gần như bằng 0 và không có xu hướng so với năm tham chiếu; sau 2015, tương quan bắt đầu tăng và mạnh dần theo thời gian.

**Kết luận.** Giai đoạn 2015–2017 đánh dấu khởi đầu của việc gia tăng vai trò các lực địa chính trị trong thương mại quốc tế. Sau 2015, các nước tăng thương mại với đồng minh trước 2015 của mình, đánh đổi bằng thương mại với các nước không phải đồng minh.

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

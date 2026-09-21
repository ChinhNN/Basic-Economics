# Maximum Sustainable Debt Across Countries: An Assessment using P-Theory — Mức nợ bền vững tối đa của các nước: đánh giá bằng lý thuyết p

**Nguồn:** IMF Working Paper WP/25/223, tháng 10/2025, Vụ Tài khoá.
**Tác giả:** Yongquan Cao, Wei Jiang, W. Raphael Lam, Neng Wang.
**Ý chính:** Nợ công toàn cầu vượt **100 nghìn tỷ USD năm 2024** và sắp tới **100% GDP**, với rủi ro nghiêng lên. Một nước gánh được bao nhiêu nợ trước khi rơi vào khủng hoảng? Bài dùng **lý thuyết p** của Jiang, Sargent, Wang và Yang (2024), trong đó chính phủ chọn thuế suất gây méo để tài trợ chi tiêu, có quyền vỡ nợ, được hưởng **lợi suất tiện ích** của tài sản an toàn, và chịu **cú sốc nợ nhảy vọt**. Mức nợ bền vững tối đa là ngưỡng mà ở đó chính phủ **bàng quan giữa trả nợ và vỡ nợ**, và được tính bằng **hai phương trình đóng**. Hiệu chỉnh cho **hơn 170 nước, 2000–2024**, mức nợ bền vững tối đa bình quân năm 2024 là khoảng **124% GDP ở nước phát triển, 76% ở nước mới nổi và 57% ở nước thu nhập thấp**. Nước đang phát triển tăng trưởng nhanh hơn nhưng biến động mạnh hơn và dễ gặp cú sốc nợ hơn. **54 trên 172 nước** đã có nợ vượt ngưỡng. Khoảng cách tới ngưỡng **khớp rất tốt với xếp hạng rủi ro** trong các khung đánh giá bền vững nợ của IMF. Ước lượng **rất nhạy khi chênh lệch lãi suất–tăng trưởng hẹp**. Các con số được bài nêu rõ là **minh hoạ**, để bổ sung chứ không thay thế các phương pháp hiện có.

> **Lưu ý:** bản PDF đầy đủ. Một số điểm không khớp trong bài:
> - Trang tác giả IMF ghi Wei Jiang ở HKUST và Neng Wang ở CKGSB, còn trang đầu bài ghi ngược lại.
> - Mục 3.1 viết năng lực thuế "đặt ở 5% cho nước mới nổi và 6,7% cho nước thu nhập thấp". Theo Bảng 1 (bình quân 41,7% và 39,9%), đây phải là **mức tăng thêm** so với tỷ lệ thu thuế lịch sử.
> - Số liệu trong lời văn Mục 4.2 không khớp Hình 3. Văn bản ghi Mỹ 160% (2014), đỉnh 213% (2018), 154% (2020), còn hình cho khoảng 135%, đỉnh khoảng 165%, khoảng 135%. Brazil văn bản ghi 113,6% → 91,3%, hình cho khoảng 100% → 92%.
> - Văn bản nói 54 nước vượt ngưỡng năm 2024, giảm còn 49 nước vào 2029, "37 nước có nợ giảm tới 2030": hai mốc năm khác nhau.
> - Phân rã Shapley ký hiệu chi phí phòng ngừa là σ trong khi phương trình dùng λ. Văn bản nói "cán cân sơ cấp thực tế góp phần tích luỹ nợ" dù phân rã chỉ gồm cán cân sơ cấp tối ưu.
> - Lãi suất phi rủi ro được lấy trung bình 2000–2029, tức gồm cả số dự báo.
> Các số lấy từ hình là giá trị đọc trên hình.

## Sơ đồ

### Mô hình: nợ biến động thế nào

```text
       ḃ = [γ − τ(b)] − g·b + [r − δ + π(b/b̄)]·b + λ·b
           └ thâm hụt ┘  └tăng┘  └── chi phí lãi ──┘   └phòng┘
             sơ cấp     trưởng                          ngừa
       ┌──────┬──────────────────────────────────────────────────┐
       │ γ    │ chi tiêu chính phủ / GDP (ngoại sinh)            │
       │ τ    │ thuế suất, GÂY MÉO                               │
       │ g    │ tăng trưởng, làm nợ/GDP giảm dần                 │
       │ r    │ lãi suất phi rủi ro toàn cầu                     │
       │ δ    │ ★ LỢI SUẤT TIỆN ÍCH: phần lãi được giảm nhờ trái │
       │      │ phiếu là tài sản an toàn, thanh khoản            │
       │ π    │ phần bù rủi ro tín dụng = ζ̃·(b/b̄)^ω, TĂNG khi nợ │
       │      │ tiến gần ngưỡng                                  │
       │ ζ̃    │ tần suất cú sốc NỢ NHẢY VỌT (Poisson)            │
       │ λ    │ chi phí PHÒNG NGỪA biến động sản lượng           │
       └──────┴──────────────────────────────────────────────────┘
       ★ khung tổng hợp: chứng khoán Arrow và bảo hiểm theo GDP của
         Shiller · làm mượt thuế của Barro · vỡ nợ của Eaton–
         Gersovitz · lợi suất tiện ích của Krishnamurthy–Vissing-
         Jorgensen
       ⚠ KHÔNG xét cơ cấu kỳ hạn, cơ cấu tiền tệ hay kỳ vọng lạm phát
       ★ có lợi suất tiện ích → chính phủ VAY TRƯỚC, ĐÁNH THUẾ SAU, có
         thể tới mức vỡ nợ trở nên đáng chọn
```

### Hai phương trình đóng

```text
       Ở NGƯỠNG: chính phủ BÀNG QUAN giữa tiếp tục đánh thuế để trả nợ
       và vỡ nợ; nợ/GDP đứng yên (ḃ = 0)
       ═══════════════════════════════════════════════════════════
       ① THUẾ TỐI ƯU
       τN = min{ τ̄ , (1/φ)·[ √(1 + 2φ(1 − α + γ + φκγ²/(2α))) − 1 ] }
       ② MỨC NỢ BỀN VỮNG TỐI ĐA
       b̄ = (τN − γ) / (r + ζ̃ + λ − δ − g)
       ═══════════════════════════════════════════════════════════
       ┌──────┬──────────────────────────────────────────────────┐
       │ φ    │ mức méo của thuế (tổn thất vô ích)               │
       │ τ̄    │ NĂNG LỰC THUẾ tối đa khả thi về chính trị        │
       │ 1 − α│ tổn thất sản lượng khi vỡ nợ                     │
       │ κ    │ méo thuế tăng thêm sau khi vỡ nợ                 │
       └──────┴──────────────────────────────────────────────────┘
       ★ tử số = thặng dư sơ cấp tối đa · mẫu số = "r − g" ở NGAY
         NGƯỠNG vỡ nợ (có thêm cú sốc, phòng ngừa, lợi suất tiện ích)
         → khác với r − g của một năm bình thường
       ─────────────────────────────────────────────────────────
       ★ KIỂM TRA VỚI HÌNH 1 (r 0,9 · ζ̃ 8,2 · λ 3,0 · δ 0,1 · g 4,3)
         mẫu số = 0,9 + 8,2 + 3,0 − 0,1 − 4,3 = 7,7%
         τ̄ = 40%, γ ≈ 21% → b̄ ≈ (40 − 21)/7,7 ≈ ★ 250% GDP (đỉnh hình)
         τ̄ = 30%, γ ≈ 16% → b̄ ≈ (30 − 16)/7,7 ≈ ★ 180% GDP
```

### Chi tiêu và năng lực thuế

```text
       HÌNH 1 — b̄ THEO CHI TIÊU γ
       ┌──────────────────┬──────────┬──────────┬──────────┬────────┐
       │ γ (% GDP)        │ 10       │ ~16      │ ~21      │ 30 / 40│
       ├──────────────────┼──────────┼──────────┼──────────┼────────┤
       │ τ̄ = 30% (THẤP)   │ ~112     │ ★ ~182   │ ~120     │ 0 ở 30 │
       │                  │          │ (đỉnh)   │          │        │
       │ τ̄ = 40% (CAO)    │ ~112     │ ~182     │ ★ ~250   │ 0 ở 40 │
       │                  │          │          │ (đỉnh)   │        │
       └──────────────────┴──────────┴──────────┴──────────┴────────┘
       (b̄ theo % GDP, đọc từ hình; hai đường trùng nhau tới γ ≈ 16)
       ★ trái đỉnh: thuế tối ưu CHƯA chạm trần → chi nhiều hơn đi kèm
         thuế tương lai cao hơn → b̄ TĂNG
       ★ phải đỉnh: thuế đã CHẠM TRẦN τ̄ → mỗi đồng chi thêm ăn vào
         thặng dư → b̄ GIẢM, về 0 khi γ = τ̄
       ⚠ mô hình giả định thuế điều chỉnh linh hoạt; thực tế cần luật
         pháp, chậm và khó — nhưng không ảnh hưởng đánh giá DÀI HẠN
```

### Các yếu tố quyết định

```text
       ┌────────────────────────────┬─────────┬─────────────────────┐
       │ YẾU TỐ                     │ tác động│ kênh                │
       │                            │ lên b̄   │                     │
       ├────────────────────────────┼─────────┼─────────────────────┤
       │ TÀI KHOÁ                   │         │                     │
       │ méo thuế φ cao             │  ↓      │ thu thuế đắt hơn    │
       │ năng lực thuế τ̄ cao        │  ↑      │ thặng dư tối đa lớn │
       │ chi tiêu γ                 │ ↑ hoặc ↓│ tuỳ trần thuế       │
       ├────────────────────────────┼─────────┼─────────────────────┤
       │ VĨ MÔ                      │         │                     │
       │ lãi phi rủi ro r           │  ↓      │ vay đắt hơn         │
       │ tần suất nợ nhảy vọt ζ̃     │  ↓      │ vd nợ ngoài ngân    │
       │                            │         │ sách lộ ra          │
       │ tăng trưởng g              │  ↑      │ cơ sở thuế rộng ra  │
       │ chi phí phòng ngừa λ       │  ↓      │ sản lượng biến động │
       │ lợi suất tiện ích δ        │  ↑      │ vay rẻ hơn; cũng có │
       │                            │         │ thể là áp chế tài   │
       │                            │         │ chính               │
       ├────────────────────────────┼─────────┼─────────────────────┤
       │ CAM KẾT HẠN CHẾ            │         │                     │
       │ tổn thất sản lượng khi vỡ  │  ↑      │ vỡ nợ càng đau,     │
       │ nợ 1 − α                   │         │ càng ít muốn vỡ     │
       │ méo thuế sau vỡ nợ κ       │  ↑      │ như trên            │
       └────────────────────────────┴─────────┴─────────────────────┘
```

### Hiệu chỉnh

```text
       ★ BẢNG 1 — BÌNH QUÂN THEO NHÓM
       ┌────────────────────────────┬────────┬────────┬────────┐
       │                            │ PHÁT   │ MỚI    │ THU    │
       │                            │ TRIỂN  │ NỔI    │ NHẬP   │
       │                            │        │        │ THẤP   │
       ├────────────────────────────┼────────┼────────┼────────┤
       │ năng lực thuế τ̄ (%)        │ 49,0   │ 41,7   │ 39,9   │
       │ α (1 − tổn thất vỡ nợ, %)  │ 95,4   │ 96,2   │ 95,7   │
       │ chi tiêu γ (% GDP)         │ 39,3   │ 29,1   │ 22,9   │
       │ ★ chi phí phòng ngừa λ (%) │ 1,6    │ 3,1    │ 3,3    │
       │ ★ tăng trưởng g (%)        │ 2,1    │ 3,5    │ 4,3    │
       │ ★ nợ nhảy vọt ζ̃ (%)        │ 4,3    │ 5,9    │ 8,2    │
       │ lãi phi rủi ro r (%)       │ 0,9    │ 0,9    │ 0,9    │
       │ lợi suất tiện ích δ (%)    │ 0,5*/0,1│ 0,1   │ 0,1    │
       │ méo thuế φ · κ             │ 3,7·1,3│ 3,7·1,3│ 3,7·1,3│
       └────────────────────────────┴────────┴────────┴────────┘
       (* 0,5% cho Mỹ, Nhật, Đức theo Krishnamurthy–Vissing-Jorgensen)
       ═══════════════════════════════════════════════════════════
       CÁCH LẤY SỐ
       τ̄ ···· nước phát triển: đủ tạo thặng dư sơ cấp 5% GDP (phân vị
              95 của nhóm); nước đang phát triển: mức tăng thuế khả thi
              theo IMF 2023
       r ···· lãi thực hiệu dụng của Mỹ (lãi trả / nợ kỳ trước − lạm
              phát), bình quân 2000–2029
       g ···· tăng trưởng bình quân từ 2000 (Nhật dùng dự báo trung hạn)
       λ ···· độ lệch chuẩn của tăng trưởng
       ζ̃ ···· phân phối Pareto của các lần nợ/GDP tăng trên 10%
       α ···· nước phát triển: khớp nợ và chênh lệch lợi suất; nước
              đang phát triển: chênh lệch lãi hiệu dụng so với Mỹ tại
              mức nợ bình quân; thiếu số liệu thì lấy 5%
       ★★ nghịch lý: nước đang phát triển TĂNG NHANH hơn nhưng BIẾN
          ĐỘNG và dễ bị NỢ NHẢY VỌT hơn → mẫu số lớn hơn → b̄ thấp hơn
```

### Kết quả xuyên quốc gia

```text
       ★★ b̄ BÌNH QUÂN 2024 (% GDP)
       phát triển ~124 · mới nổi ~76 · thu nhập thấp ~57
       ★ 54/172 nước đã có nợ VƯỢT ngưỡng năm 2024 → 49 nước vào 2029
         (giữ ngưỡng 2024); 37 trong 54 nước dự kiến nợ giảm
       ⚠ nhiều nước mới nổi và thu nhập thấp đã SÁT ngưỡng → ít dư địa
       ═══════════════════════════════════════════════════════════
       ★★ ĐỐI CHIẾU VỚI KHUNG CỦA IMF (khoảng cách = b̄ − nợ, % GDP)
       BẢNG 2 — khung nước thu nhập thấp (LIC DSF)
       ┌────────────────┬─────────┬──────────────┐
       │ xếp hạng       │ số nước │ khoảng cách  │
       ├────────────────┼─────────┼──────────────┤
       │ thấp           │ 7       │ +28,8        │
       │ trung bình     │ 24      │ +12,6        │
       │ cao            │ 21      │ +3,4         │
       │ ★ đang khó khăn│ 9       │ ★ −44,0      │
       └────────────────┴─────────┴──────────────┘
       BẢNG 3 — khung nước tiếp cận thị trường (MAC SRDSF)
       ┌──────────────────────────────┬───────┬───────┬───────┐
       │ đánh giá                     │ THẤP  │ VỪA   │ CAO   │
       ├──────────────────────────────┼───────┼───────┼───────┤
       │ dài hạn                      │ 44,0  │ 28,9  │ 16,7  │
       │ trung hạn, cuối cùng         │ 50,2  │ 17,3  │ 2,4   │
       │ ★ ngắn hạn, cuối cùng        │ 39,2  │ 8,1   │ −15,0 │
       │ ★ rủi ro căng thẳng tổng thể │ 48,0  │ 17,4  │ −17,2 │
       └──────────────────────────────┴───────┴───────┴───────┘
       bền vững (cơ học): khả năng cao +14,6 · không chắc −26,6 ·
         không bền vững −37,4
       → khoảng cách GIẢM ĐỀU theo mức rủi ro → dùng được làm chỉ báo
         bổ sung
```

### Theo thời gian và phân rã

```text
       tính lại b̄ bằng các bản Triển vọng Kinh tế Thế giới tháng 10
       cũ: đổi g, γ, r, λ; giữ nguyên các tham số khác
       ═══════════════════════════════════════════════════════════
       HÌNH 3 (theo văn bản)
       Brazil · 113,6 (2014) → 91,3 (2017) → dao động qua đại dịch →
                103,3 (2024); nợ từng VƯỢT ngưỡng năm 2020
       Mỹ ····· 160 (2014) → đỉnh 213 (2018) → 154 (2020) → gần mức
                trước đại dịch (2024)
       ═══════════════════════════════════════════════════════════
       ★ PHÂN RÃ SHAPLEY (Hình 4): trung bình đóng góp biên của mỗi
         tham số qua MỌI thứ tự thay đổi → chính xác kể cả khi phi
         tuyến (nhất là khi trần thuế ràng buộc)
       Mỹ ····· 2014–19: lãi thấp, biến động thấp → b̄ TĂNG
                2020: biến động vọt, tăng trưởng co, chi tăng → GIẢM
                2021–24: tăng trưởng hồi, biến động giảm → hồi một phần
       Brazil · TĂNG TRƯỞNG chi phối, nhất là trong suy thoái dài
                ★ chi tăng lại NÂNG b̄ vì thuế tối ưu chưa chạm trần
       cả hai: cán cân sơ cấp tối ưu đóng góp ÍT NHẤT
```

### Độ nhạy

```text
       ∂b̄/∂r = − b̄ / (r + ζ̃ + λ − δ − g)
       → mẫu số càng NHỎ (gần 0), b̄ càng NHẠY; b̄ gốc càng lớn, thay
         đổi tuyệt đối càng lớn; tương tự với g
       ═══════════════════════════════════════════════════════════
       HÌNH 5 — G20 và vài nước khác
       lãi suất ± 0,5 điểm (độ lệch chuẩn lãi hiệu dụng Mỹ 15 năm)
       chi tiêu ± 1 điểm % GDP
       ★ Trung Quốc: dải RẤT RỘNG (khoảng 150–300% GDP) → mẫu số hẹp
       ★ Ai Cập, Pakistan, Nigeria: nợ đã VƯỢT ngưỡng
       chi tiêu: dấu tác động TUỲ trần thuế
         còn dư địa thuế → chi nhiều hơn nâng b̄
         sát trần thuế → chi nhiều hơn hạ b̄
```

## Ba câu hỏi bài viết trả lời

1. Làm sao tính được mức nợ bền vững tối đa của một nước bằng một mô hình vừa có cơ sở lý thuyết vừa đủ đơn giản để áp dụng cho hơn 170 nước?
2. Mức nợ bền vững tối đa khác nhau thế nào giữa nước phát triển, mới nổi và thu nhập thấp, và bao nhiêu nước đã vượt ngưỡng?
3. Ngưỡng này thay đổi theo thời gian vì những yếu tố nào, và nhạy tới đâu với lãi suất và chi tiêu?

## Dàn ý chi tiết

### 1. Mở đầu

- Nợ công toàn cầu sắp vượt đỉnh đại dịch. Trong kịch bản xấu nghiêm trọng, nợ có thể cao hơn dự báo 20 điểm phần trăm sau ba năm do bất định chính sách, điều kiện tài chính thắt chặt và căng thẳng địa chính trị. Vì vậy cần biết mỗi nước gánh được bao nhiêu nợ mà không rơi vào khủng hoảng.
- Bài có hai đóng góp: một khung gọn nhưng giải được để tính mức nợ bền vững tối đa, với ánh xạ trực tiếp từ lãi phi rủi ro, lợi suất tiện ích và phần bù rủi ro nhảy vọt sang chênh lệch lợi suất; và hiệu chỉnh đầu tiên trên quy mô lớn cho hơn 170 nước từ 2000 tới 2024.

### 2. Vị trí trong tài liệu

- Mô hình làm mượt thuế của Barro coi nợ là bộ đệm giảm méo thuế nhưng giả định cam kết trả nợ hoàn hảo. Mô hình vỡ nợ của Arellano và cách tiếp cận giới hạn tài khoá của Bi và Leeper mô hình hoá ngưỡng mà chính phủ không còn tạo đủ thặng dư.
- Nghiên cứu thực nghiệm ước lượng dư địa tài khoá từ hành vi quá khứ: "mệt mỏi tài khoá" của Ghosh và cộng sự, "không chịu nổi nợ" của Reinhart, Rogoff và Savastano ở nước mới nổi. Các ý tưởng này đi vào khung đánh giá bền vững nợ của IMF và Ngân hàng Thế giới.
- Bài bổ sung một chỉ báo cho hơn 170 nước, kết hợp với thước đo Nợ có rủi ro của Furceri và cộng sự.

### 3. Mô hình

- Sản lượng theo quá trình khuếch tán có nhảy; một phần rủi ro phòng ngừa được bằng bảo hiểm theo GDP, phần nhảy thì không. Chính phủ đánh thuế gây méo để tài trợ chi tiêu ngoại sinh, có quyền vỡ nợ và được hưởng lợi suất tiện ích.
- Ngưỡng được xác định bằng cách so hai hàm giá trị: tiếp tục trả nợ với thuế gây méo, và vỡ nợ. Vỡ nợ gây mất sản lượng và làm thu thuế kém hiệu quả hơn, và chính phủ mất quyền tiếp cận thị trường vĩnh viễn.
- Thuế tối ưu bị chặn bởi năng lực thuế; theo IMF, cải cách toàn diện có thể tăng thu thêm khoảng 3 tới 5 điểm phần trăm GDP trong trung hạn.

### 4. Hiệu chỉnh

- Méo thuế và méo thuế sau vỡ nợ lấy từ Jiang và cộng sự, giống nhau cho mọi nước. Chi tiêu dùng số liệu chính phủ chung chứ không chỉ trung ương.
- Lợi suất tiện ích đặt dương nhưng nhỏ cho mọi nước vì lý do kỹ thuật: chính phủ chỉ vay trước khi có lợi suất tiện ích dương.
- Xác suất nợ nhảy vọt được hiệu chỉnh theo đuôi của phân phối thay đổi nợ, thay vì theo thảm hoạ sản lượng như bài gốc.
- Tổn thất vỡ nợ được ước lượng từ chênh lệch lãi hiệu dụng thay vì chênh lệch trái phiếu quốc tế, vì phản ánh đầy đủ hơn điều kiện vay, kể cả phát hành bằng nội tệ hay trái phiếu chỉ số hoá lạm phát.

### 5. Kết quả

- Có khác biệt lớn giữa các nước. Nước phát triển có ngưỡng cao nhờ tài chính ổn định, lợi suất tiện ích cao ở các nước quan trọng về hệ thống, biến động thấp và ít cú sốc nợ. Nước mới nổi và thu nhập thấp có ngưỡng thấp dù tăng trưởng cao hơn.
- Khoảng cách tới ngưỡng giảm đều theo mức rủi ro trong các khung đánh giá của IMF, ở cả dài hạn, trung hạn, ngắn hạn và đánh giá bền vững, cho thấy mô hình nắm được cả rủi ro hệ thống chứ không chỉ mất cân đối nhất thời.
- Ngưỡng tương đối ổn định theo thời gian, dao động chủ yếu do triển vọng tăng trưởng, phần bù rủi ro, lãi phi rủi ro và thay đổi chi tiêu.
- Độ nhạy lớn nhất khi chênh lệch lãi suất–tăng trưởng ở ngưỡng hẹp.

### 6. Kết luận

- Mức nợ bền vững do tương tác giữa nền tảng tài khoá vĩ mô, định giá tài sản và rủi ro chủ quyền quyết định. Nước phát triển có ngưỡng cao hơn nhưng vẫn dễ tổn thương trước lãi suất toàn cầu; nhiều nước mới nổi và thu nhập thấp đã vượt ngưỡng.
- Cần đánh giá linh hoạt, theo từng nước, để định hướng chính sách tài khoá và quản lý nợ thận trọng.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Maximum sustainable debt | Mức nợ bền vững tối đa, ngưỡng bàng quan giữa trả nợ và vỡ nợ |
| Debt-carrying capacity | Năng lực gánh nợ |
| P-theory | Lý thuyết p về thuế và quản lý nợ của Jiang, Sargent, Wang, Yang |
| Tax distortion | Méo thuế, tổn thất vô ích do đánh thuế |
| Tax capacity | Năng lực thuế tối đa khả thi |
| Convenience yield | Lợi suất tiện ích của tài sản an toàn |
| Jump-risk premium | Phần bù rủi ro nhảy vọt |
| Debt surge | Nợ nhảy vọt, vd lộ ra nợ ngoài ngân sách |
| Hedging cost | Chi phí phòng ngừa biến động sản lượng |
| GDP-indexed insurance | Bảo hiểm chỉ số hoá theo GDP |
| Limited commitment | Cam kết hạn chế, chính phủ có thể vỡ nợ |
| Output cost of default | Tổn thất sản lượng khi vỡ nợ |
| Interest-growth differential | Chênh lệch lãi suất và tăng trưởng |
| Effective interest rate | Lãi suất hiệu dụng, lãi trả chia nợ kỳ trước |
| Pareto distribution | Phân phối Pareto, mô tả đuôi dày |
| Shapley decomposition | Phân rã Shapley, chia đóng góp của từng tham số |
| Fiscal fatigue | Mệt mỏi tài khoá |
| Debt intolerance | Không chịu nổi nợ |
| LIC DSF | Khung bền vững nợ cho nước thu nhập thấp |
| MAC SRDSF | Khung rủi ro chủ quyền và bền vững nợ cho nước tiếp cận thị trường |
| Financial repression | Áp chế tài chính |

## Câu nói đáng nhớ

> "While current debt levels in many economies remain within maximum sustainable debt levels, debt burdens in many emerging markets and low-income countries are near their respective sustainable levels."

> "When this denominator is small—particularly when it approaches zero—the debt limit becomes highly sensitive to changes in the interest rate."

> "Throughout, quantitative figures are illustrative and meant to complement existing method to assess sovereign risks."

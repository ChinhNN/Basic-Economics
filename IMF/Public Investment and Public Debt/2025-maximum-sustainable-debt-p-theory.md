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

## Khái niệm cần biết

**Mức nợ bền vững tối đa (maximum sustainable debt).** Mức nợ/GDP cao nhất mà tại đó chính phủ vẫn còn muốn và còn có thể trả nợ. Vượt mức này, chi phí đánh thuế để trả nợ lớn hơn chi phí của việc vỡ nợ, nên chính phủ có động cơ vỡ nợ và thị trường biết điều đó. Ví dụ: bài ước tính mức này năm 2024 bình quân khoảng 124% GDP ở nước phát triển nhưng chỉ khoảng 57% GDP ở nước thu nhập thấp. Đây là con số trung tâm của bài, dùng để đo mỗi nước còn bao nhiêu dư địa.

**Thuế gây méo (distortionary tax) và năng lực thuế.** Thuế gây méo là thuế làm thay đổi hành vi theo hướng thu hẹp hoạt động kinh tế: thuế thu nhập cao khiến người ta làm ít hơn, thuế lợi nhuận cao khiến doanh nghiệp đầu tư ít hơn. Thuế suất càng cao, tổn thất (gọi là tổn thất vô ích) tăng càng nhanh. Năng lực thuế là thuế suất tối đa khả thi về mặt chính trị và hành chính. Ví dụ: năng lực thuế bình quân trong bài là 49,0% ở nước phát triển, 39,9% ở nước thu nhập thấp. Năng lực thuế quyết định thặng dư tối đa mà chính phủ có thể dành để trả nợ.

**Thâm hụt sơ cấp và thặng dư sơ cấp.** Chênh lệch giữa thu và chi ngân sách khi chưa tính tiền trả lãi. Thặng dư sơ cấp là phần tiền còn lại để trả lãi và giảm nợ. Ví dụ minh hoạ: thu 40% GDP, chi (không kể lãi) 21% GDP, thì thặng dư sơ cấp tối đa là 19% GDP. Trong công thức của bài, tử số chính là thặng dư sơ cấp tối đa này.

**Chênh lệch lãi suất – tăng trưởng (r − g).** Lãi suất trên nợ trừ tốc độ tăng trưởng kinh tế. Khi r lớn hơn g, nợ/GDP tự tăng nếu không có thặng dư sơ cấp; khi r nhỏ hơn g, nợ/GDP tự giảm dần. Ví dụ minh hoạ: nợ 100% GDP, lãi 5%, tăng trưởng 3%, thì mỗi năm cần thặng dư sơ cấp 2% GDP chỉ để giữ nợ/GDP đứng yên. Bài dùng một phiên bản mở rộng của r − g "ở ngay ngưỡng vỡ nợ", và cho thấy khi chênh lệch này hẹp, ngưỡng nợ trở nên cực kỳ nhạy.

**Lợi suất tiện ích (convenience yield).** Phần lãi suất mà chính phủ được giảm vì trái phiếu của họ được coi là tài sản an toàn và dễ mua bán, nên nhà đầu tư chấp nhận lãi thấp hơn để nắm giữ. Ví dụ: bài đặt lợi suất tiện ích 0,5% cho Mỹ, Nhật, Đức và 0,1% cho các nước khác, tức trái phiếu Mỹ được vay rẻ hơn 0,5 điểm phần trăm nhờ vị thế tài sản an toàn. Lợi suất tiện ích làm vay rẻ hơn, nhưng cũng tạo động cơ "vay trước, đánh thuế sau".

**Cú sốc nợ nhảy vọt (debt jump).** Các lần nợ/GDP tăng vọt bất ngờ, ví dụ khi một khoản nợ ngoài ngân sách của doanh nghiệp nhà nước bị lộ ra, khi ngân hàng phải được cứu, hay khi đồng tiền mất giá mạnh. Bài coi những lần nợ/GDP tăng trên 10% là cú sốc nhảy vọt và đo tần suất của chúng. Ví dụ: tần suất bình quân là 4,3% mỗi năm ở nước phát triển và 8,2% ở nước thu nhập thấp. Tần suất này đi thẳng vào mẫu số của công thức và kéo ngưỡng nợ xuống.

**Chi phí phòng ngừa (precautionary cost).** Khi sản lượng biến động mạnh, một mức nợ nhất định trở nên rủi ro hơn, nên cần một "đệm" an toàn lớn hơn. Bài đo chi phí này bằng độ lệch chuẩn của tăng trưởng. Ví dụ: chi phí phòng ngừa là 1,6% ở nước phát triển so với 3,3% ở nước thu nhập thấp. Đây là một lý do khiến nước tăng trưởng nhanh nhưng bấp bênh lại có ngưỡng nợ thấp hơn.

**Phân rã Shapley.** Cách chia một thay đổi tổng cho nhiều nguyên nhân khi các nguyên nhân tác động phi tuyến (ảnh hưởng của yếu tố này phụ thuộc vào yếu tố kia). Phương pháp lấy trung bình đóng góp biên của mỗi yếu tố qua mọi thứ tự thay đổi có thể. Ví dụ minh hoạ: nếu ngưỡng nợ của một nước giảm 20 điểm vì cả lãi suất lẫn biến động tăng, phân rã Shapley có thể cho biết 12 điểm do biến động, 8 điểm do lãi suất. Bài dùng nó để giải thích vì sao ngưỡng nợ của Mỹ và Brazil thay đổi theo thời gian.

## Nội dung chi tiết

### 1. Mở đầu

Nợ công toàn cầu đã vượt 100 nghìn tỷ USD năm 2024, sắp tới 100% GDP và sắp vượt đỉnh thời đại dịch. Rủi ro nghiêng về phía tăng: trong kịch bản xấu nghiêm trọng, nợ có thể cao hơn dự báo 20 điểm phần trăm sau ba năm, do bất định chính sách, điều kiện tài chính thắt chặt và căng thẳng địa chính trị. Vì vậy cần trả lời câu hỏi: mỗi nước gánh được bao nhiêu nợ mà không rơi vào khủng hoảng?

Bài có hai đóng góp:
- **Một khung gọn nhưng giải được** để tính mức nợ bền vững tối đa. Khung này ánh xạ trực tiếp từ lãi suất phi rủi ro, lợi suất tiện ích và phần bù rủi ro nhảy vọt sang chênh lệch lợi suất mà một nước phải trả. Nền tảng là lý thuyết p của Jiang, Sargent, Wang và Yang (2024).
- **Hiệu chỉnh đầu tiên trên quy mô lớn**, cho hơn 170 nước (172 nước) từ 2000 tới 2024.

Bài nói rõ các con số là minh hoạ, để bổ sung chứ không thay thế các phương pháp đánh giá bền vững nợ hiện có.

### 2. Vị trí trong tài liệu

**Mô hình lý thuyết.** Mô hình làm mượt thuế của Barro coi nợ là bộ đệm: thay vì tăng thuế đột ngột khi chi tăng, chính phủ vay rồi trả dần, nhờ đó giảm tổn thất do thuế gây méo. Nhưng mô hình này giả định chính phủ cam kết trả nợ hoàn hảo. Mô hình vỡ nợ của Arellano (dựa trên Eaton–Gersovitz) và cách tiếp cận "giới hạn tài khoá" của Bi và Leeper bỏ giả định đó, và mô hình hoá ngưỡng mà ở đó chính phủ không còn tạo đủ thặng dư để trả nợ.

**Nghiên cứu thực nghiệm** ước lượng dư địa tài khoá từ hành vi trong quá khứ: khái niệm "mệt mỏi tài khoá" của Ghosh và cộng sự (chính phủ không thể tăng thặng dư mãi khi nợ cao), và "không chịu nổi nợ" của Reinhart, Rogoff và Savastano (nước mới nổi vỡ nợ ở mức nợ thấp hơn nhiều so với nước phát triển). Các ý tưởng này đã đi vào các khung đánh giá bền vững nợ của IMF và Ngân hàng Thế giới.

Bài bổ sung một chỉ báo có cơ sở lý thuyết cho hơn 170 nước, có thể dùng kết hợp với thước đo Nợ có rủi ro của Furceri và cộng sự.

### 3. Mô hình

**Thiết lập.** Sản lượng biến động theo một quá trình khuếch tán (dao động liên tục) có thêm các bước nhảy (cú sốc đột ngột). Một phần rủi ro dao động có thể phòng ngừa được bằng các công cụ kiểu bảo hiểm theo GDP; phần nhảy vọt thì không. Chính phủ đánh thuế gây méo để tài trợ chi tiêu ngoại sinh, có quyền vỡ nợ, và được hưởng lợi suất tiện ích. Khung này tổng hợp nhiều ý tưởng kinh điển: chứng khoán Arrow và bảo hiểm theo GDP của Shiller, làm mượt thuế của Barro, vỡ nợ của Eaton–Gersovitz, lợi suất tiện ích của Krishnamurthy–Vissing-Jorgensen. Mô hình không xét cơ cấu kỳ hạn nợ, cơ cấu tiền tệ của nợ hay kỳ vọng lạm phát.

**Nợ biến động thế nào.** Thay đổi của nợ/GDP theo thời gian:

ḃ = [γ − τ(b)] − g·b + [r − δ + π(b/b̄)]·b + λ·b

Bốn thành phần, từ trái sang phải: thâm hụt sơ cấp, tác động của tăng trưởng, chi phí lãi, và chi phí phòng ngừa.

| Ký hiệu | Ý nghĩa |
|---|---|
| γ | Chi tiêu chính phủ / GDP (ngoại sinh) |
| τ | Thuế suất, có gây méo |
| g | Tăng trưởng, làm nợ/GDP giảm dần |
| r | Lãi suất phi rủi ro toàn cầu |
| δ | Lợi suất tiện ích: phần lãi được giảm nhờ trái phiếu là tài sản an toàn, thanh khoản |
| π | Phần bù rủi ro tín dụng = ζ̃·(b/b̄)^ω, tăng lên khi nợ tiến gần ngưỡng |
| ζ̃ | Tần suất cú sốc nợ nhảy vọt (theo quá trình Poisson) |
| λ | Chi phí phòng ngừa biến động sản lượng |

Một hàm ý quan trọng: khi có lợi suất tiện ích, chính phủ có động cơ **vay trước, đánh thuế sau**, vì vay đang rẻ; và nếu không có giới hạn, có thể vay tới mức vỡ nợ trở nên đáng chọn.

**Ngưỡng được xác định thế nào.** Bài so hai hàm giá trị (tổng phúc lợi kỳ vọng): tiếp tục trả nợ bằng thuế gây méo, và vỡ nợ. Vỡ nợ không miễn phí: sản lượng mất một phần (1 − α), thu thuế sau đó kém hiệu quả hơn (méo thuế tăng thêm κ), và chính phủ mất quyền tiếp cận thị trường vĩnh viễn. Mức nợ bền vững tối đa là điểm mà chính phủ **bàng quan** giữa hai lựa chọn, và tại đó nợ/GDP đứng yên (ḃ = 0).

**Hai phương trình đóng.** Ngưỡng tính được bằng hai công thức:

1. Thuế tối ưu: τN = min{ τ̄ , (1/φ)·[ √(1 + 2φ(1 − α + γ + φκγ²/(2α))) − 1 ] }
2. Mức nợ bền vững tối đa: b̄ = (τN − γ) / (r + ζ̃ + λ − δ − g)

| Ký hiệu | Ý nghĩa |
|---|---|
| φ | Mức méo của thuế (tổn thất vô ích) |
| τ̄ | Năng lực thuế tối đa khả thi về chính trị |
| 1 − α | Tổn thất sản lượng khi vỡ nợ |
| κ | Méo thuế tăng thêm sau khi vỡ nợ |

Cách đọc công thức thứ hai: tử số là **thặng dư sơ cấp tối đa** (thuế tối ưu trừ chi tiêu); mẫu số là một dạng "r − g" đo **ngay tại ngưỡng vỡ nợ**, có thêm tần suất cú sốc, chi phí phòng ngừa và trừ đi lợi suất tiện ích. Nó khác với r − g của một năm bình thường. Logic giống như định giá một dòng tiền vĩnh viễn: giá trị bằng dòng tiền chia cho tỷ suất chiết khấu.

**Ví dụ tính tay** với các tham số của nước thu nhập thấp: r = 0,9; ζ̃ = 8,2; λ = 3,0; δ = 0,1; g = 4,3 (đều tính theo %). Mẫu số = 0,9 + 8,2 + 3,0 − 0,1 − 4,3 = 7,7%. Với năng lực thuế τ̄ = 40% và chi tiêu γ ≈ 21% GDP, b̄ ≈ (40 − 21)/7,7 ≈ 250% GDP. Với τ̄ = 30% và γ ≈ 16% GDP, b̄ ≈ (30 − 16)/7,7 ≈ 180% GDP.

**Chi tiêu tác động lên ngưỡng theo hình chữ V ngược.** Mức nợ bền vững tối đa theo chi tiêu γ (giá trị đọc trên hình, % GDP):

| γ (% GDP) | 10 | khoảng 16 | khoảng 21 | 30 hoặc 40 |
|---|---|---|---|---|
| τ̄ = 30% (năng lực thuế thấp) | khoảng 112 | khoảng 182 (đỉnh) | khoảng 120 | về 0 khi γ = 30 |
| τ̄ = 40% (năng lực thuế cao) | khoảng 112 | khoảng 182 | khoảng 250 (đỉnh) | về 0 khi γ = 40 |

Hai đường trùng nhau cho tới γ ≈ 16. Bên trái đỉnh, thuế tối ưu **chưa chạm trần** τ̄: chi nhiều hơn đi kèm thuế tương lai cao hơn (vì thuế tối ưu tăng theo chi tiêu), nên khả năng trả nợ và b̄ tăng. Bên phải đỉnh, thuế đã **chạm trần**: mỗi đồng chi thêm ăn thẳng vào thặng dư, nên b̄ giảm, và về 0 khi chi tiêu bằng năng lực thuế. Mô hình giả định thuế điều chỉnh linh hoạt; thực tế tăng thuế cần luật pháp, chậm và khó, nhưng điều này không ảnh hưởng đến đánh giá dài hạn.

**Năng lực thuế** chặn thuế tối ưu. Theo IMF, cải cách thuế toàn diện có thể tăng thu thêm khoảng 3 tới 5 điểm phần trăm GDP trong trung hạn.

**Tổng hợp các yếu tố quyết định:**

| Nhóm | Yếu tố | Tác động lên b̄ | Kênh |
|---|---|---|---|
| Tài khoá | Méo thuế φ cao | giảm | Thu thuế đắt hơn |
| | Năng lực thuế τ̄ cao | tăng | Thặng dư tối đa lớn hơn |
| | Chi tiêu γ | tăng hoặc giảm | Tuỳ thuế đã chạm trần hay chưa |
| Vĩ mô | Lãi phi rủi ro r | giảm | Vay đắt hơn |
| | Tần suất nợ nhảy vọt ζ̃ | giảm | Ví dụ nợ ngoài ngân sách lộ ra |
| | Tăng trưởng g | tăng | Cơ sở thuế rộng ra |
| | Chi phí phòng ngừa λ | giảm | Sản lượng biến động |
| | Lợi suất tiện ích δ | tăng | Vay rẻ hơn; nhưng cũng có thể phản ánh áp chế tài chính (ép ngân hàng trong nước mua trái phiếu) |
| Cam kết hạn chế | Tổn thất sản lượng khi vỡ nợ 1 − α | tăng | Vỡ nợ càng đau, càng ít muốn vỡ |
| | Méo thuế sau vỡ nợ κ | tăng | Như trên |

### 4. Hiệu chỉnh

**Bình quân tham số theo nhóm nước:**

| Tham số | Phát triển | Mới nổi | Thu nhập thấp |
|---|---|---|---|
| Năng lực thuế τ̄ (%) | 49,0 | 41,7 | 39,9 |
| α (1 − tổn thất khi vỡ nợ, %) | 95,4 | 96,2 | 95,7 |
| Chi tiêu γ (% GDP) | 39,3 | 29,1 | 22,9 |
| Chi phí phòng ngừa λ (%) | 1,6 | 3,1 | 3,3 |
| Tăng trưởng g (%) | 2,1 | 3,5 | 4,3 |
| Tần suất nợ nhảy vọt ζ̃ (%) | 4,3 | 5,9 | 8,2 |
| Lãi phi rủi ro r (%) | 0,9 | 0,9 | 0,9 |
| Lợi suất tiện ích δ (%) | 0,5 cho Mỹ, Nhật, Đức; 0,1 cho các nước khác | 0,1 | 0,1 |
| Méo thuế φ và κ | 3,7 và 1,3 | 3,7 và 1,3 | 3,7 và 1,3 |

**Cách lấy từng tham số:**
- **Méo thuế φ và méo thuế sau vỡ nợ κ** lấy từ Jiang và cộng sự, giống nhau cho mọi nước.
- **Chi tiêu γ** dùng số liệu chính phủ chung (gồm cả địa phương), không chỉ trung ương.
- **Năng lực thuế τ̄**: ở nước phát triển, đặt đủ cao để tạo được thặng dư sơ cấp 5% GDP (mức ở phân vị 95 của nhóm); ở nước đang phát triển, bằng thu thuế lịch sử cộng mức tăng thuế khả thi theo IMF (2023).
- **Lãi phi rủi ro r**: lãi thực hiệu dụng của Mỹ (lãi đã trả chia nợ kỳ trước, trừ lạm phát), bình quân 2000–2029.
- **Tăng trưởng g**: bình quân từ 2000 (riêng Nhật dùng dự báo trung hạn).
- **Chi phí phòng ngừa λ**: độ lệch chuẩn của tăng trưởng.
- **Lợi suất tiện ích δ** đặt dương nhưng nhỏ cho mọi nước vì một lý do kỹ thuật: trong mô hình, chính phủ chỉ vay trước khi lợi suất tiện ích dương. Mức 0,5% cho Mỹ, Nhật, Đức theo Krishnamurthy–Vissing-Jorgensen.
- **Tần suất nợ nhảy vọt ζ̃** được hiệu chỉnh theo đuôi của phân phối thay đổi nợ: dùng phân phối Pareto cho các lần nợ/GDP tăng trên 10%. Đây là thay đổi so với bài gốc của lý thuyết p, vốn hiệu chỉnh theo các thảm hoạ sản lượng.
- **Tổn thất vỡ nợ (qua α)**: ở nước phát triển, chọn để khớp mức nợ và chênh lệch lợi suất; ở nước đang phát triển, ước lượng từ chênh lệch lãi hiệu dụng so với Mỹ tại mức nợ bình quân; thiếu số liệu thì lấy 5%. Bài dùng chênh lệch lãi hiệu dụng thay vì chênh lệch trái phiếu quốc tế vì nó phản ánh đầy đủ hơn điều kiện vay, kể cả phát hành bằng nội tệ hay trái phiếu chỉ số hoá lạm phát.

**Nghịch lý của nước đang phát triển.** Họ tăng trưởng nhanh hơn (g 4,3% ở nước thu nhập thấp so với 2,1% ở nước phát triển), điều lẽ ra làm ngưỡng nợ cao hơn. Nhưng họ cũng biến động mạnh hơn và dễ gặp cú sốc nợ nhảy vọt hơn, và hai yếu tố này lớn hơn lợi thế tăng trưởng. Kết quả là mẫu số lớn hơn, nên b̄ thấp hơn.

### 5. Kết quả

**Khác biệt lớn giữa các nước.** Mức nợ bền vững tối đa bình quân năm 2024 là khoảng 124% GDP ở nước phát triển, khoảng 76% ở nước mới nổi và khoảng 57% ở nước thu nhập thấp. Nước phát triển có ngưỡng cao nhờ tài chính ổn định, lợi suất tiện ích cao ở các nước quan trọng về hệ thống, biến động thấp và ít cú sốc nợ. Nước mới nổi và thu nhập thấp có ngưỡng thấp dù tăng trưởng cao hơn.

54 trên 172 nước đã có nợ vượt ngưỡng năm 2024. Nếu giữ nguyên ngưỡng 2024, con số này giảm còn 49 nước vào 2029, vì 37 trong 54 nước dự kiến có nợ giảm. Nhiều nước mới nổi và thu nhập thấp khác đã sát ngưỡng, nên dư địa rất ít.

**Đối chiếu với các khung đánh giá của IMF.** Khoảng cách tới ngưỡng được tính bằng b̄ trừ nợ hiện tại (% GDP); dương là còn dư địa, âm là đã vượt.

Khung cho nước thu nhập thấp (LIC DSF):

| Xếp hạng rủi ro | Số nước | Khoảng cách bình quân |
|---|---|---|
| Thấp | 7 | +28,8 |
| Trung bình | 24 | +12,6 |
| Cao | 21 | +3,4 |
| Đang khó khăn về nợ | 9 | −44,0 |

Khung cho nước tiếp cận thị trường (MAC SRDSF):

| Đánh giá | Rủi ro thấp | Rủi ro vừa | Rủi ro cao |
|---|---|---|---|
| Dài hạn | 44,0 | 28,9 | 16,7 |
| Trung hạn, cuối cùng | 50,2 | 17,3 | 2,4 |
| Ngắn hạn, cuối cùng | 39,2 | 8,1 | −15,0 |
| Rủi ro căng thẳng tổng thể | 48,0 | 17,4 | −17,2 |

Với đánh giá bền vững (cơ học): nhóm "bền vững với khả năng cao" có khoảng cách +14,6; nhóm "bền vững nhưng không chắc" −26,6; nhóm "không bền vững" −37,4.

Ở cả hai khung, khoảng cách giảm đều theo mức rủi ro, ở mọi chân trời dài hạn, trung hạn, ngắn hạn và trong đánh giá bền vững. Điều này cho thấy mô hình nắm được cả rủi ro mang tính hệ thống chứ không chỉ các mất cân đối nhất thời, và có thể dùng làm chỉ báo bổ sung.

**Theo thời gian.** Bài tính lại b̄ cho các năm trước bằng các bản Triển vọng Kinh tế Thế giới tháng 10 cũ: thay đổi g, γ, r, λ theo từng năm, giữ nguyên các tham số khác. Ngưỡng tương đối ổn định, dao động chủ yếu do triển vọng tăng trưởng, phần bù rủi ro, lãi phi rủi ro và thay đổi chi tiêu. Hai ví dụ (theo số trong văn bản của bài):
- **Brazil**: 113,6% (2014), giảm còn 91,3% (2017), dao động qua đại dịch, lên 103,3% (2024). Nợ của Brazil từng vượt ngưỡng năm 2020.
- **Mỹ**: 160% (2014), đỉnh 213% (2018), xuống 154% (2020), rồi về gần mức trước đại dịch năm 2024.

**Phân rã Shapley** cho biết yếu tố nào gây ra các thay đổi đó. Phương pháp lấy trung bình đóng góp biên của mỗi tham số qua mọi thứ tự thay đổi, nên chính xác kể cả khi quan hệ phi tuyến (nhất là khi trần thuế ràng buộc):
- **Mỹ**: 2014–19, lãi thấp và biến động thấp làm b̄ tăng; năm 2020, biến động vọt lên, tăng trưởng co lại, chi tăng nên b̄ giảm; 2021–24, tăng trưởng hồi phục và biến động giảm nên b̄ hồi một phần.
- **Brazil**: tăng trưởng là yếu tố chi phối, nhất là trong đợt suy thoái dài. Đáng chú ý, chi tăng lại **nâng** b̄, vì thuế tối ưu của Brazil chưa chạm trần.
- Ở cả hai nước, cán cân sơ cấp tối ưu đóng góp ít nhất.

**Độ nhạy.** Đạo hàm của ngưỡng theo lãi suất:

∂b̄/∂r = − b̄ / (r + ζ̃ + λ − δ − g)

Mẫu số càng nhỏ (càng gần 0), b̄ càng nhạy; và b̄ gốc càng lớn thì thay đổi tuyệt đối càng lớn. Tăng trưởng g tác động tương tự nhưng ngược dấu. Bài thử cho G20 và vài nước khác: thay đổi lãi suất ± 0,5 điểm phần trăm (bằng độ lệch chuẩn của lãi hiệu dụng của Mỹ trong 15 năm) và chi tiêu ± 1 điểm phần trăm GDP. Kết quả:
- Trung Quốc có dải ngưỡng rất rộng (khoảng 150–300% GDP) vì mẫu số hẹp.
- Ai Cập, Pakistan và Nigeria đã có nợ vượt ngưỡng.
- Dấu tác động của chi tiêu tuỳ trần thuế: nước còn dư địa thuế thì chi nhiều hơn nâng b̄; nước sát trần thuế thì chi nhiều hơn hạ b̄.

Nói chung, độ nhạy lớn nhất khi chênh lệch lãi suất–tăng trưởng ở ngưỡng hẹp; khi đó một thay đổi nhỏ về lãi suất có thể làm ngưỡng dịch hàng chục điểm phần trăm GDP.

### 6. Kết luận

Mức nợ bền vững là kết quả của tương tác giữa nền tảng tài khoá vĩ mô (năng lực thuế, chi tiêu, tăng trưởng), định giá tài sản (lãi phi rủi ro, lợi suất tiện ích) và rủi ro chủ quyền (biến động, cú sốc nợ, chi phí vỡ nợ). Nước phát triển có ngưỡng cao hơn nhưng vẫn dễ tổn thương trước lãi suất toàn cầu, vì ngưỡng lớn đồng nghĩa với thay đổi tuyệt đối lớn khi lãi suất đổi. Nhiều nước mới nổi và thu nhập thấp đã vượt ngưỡng.

Hàm ý: cần đánh giá linh hoạt, theo từng nước, để định hướng chính sách tài khoá và quản lý nợ thận trọng. Mức nợ bền vững tối đa là một chỉ báo bổ sung hữu ích, nhất là khi kết hợp với các khung đánh giá hiện có và thước đo nợ có rủi ro, chứ không phải một ngưỡng cứng để áp dụng máy móc.

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

## Đánh giá và phát hiện đáng chú ý

### Toàn bộ khác biệt giữa các nước nằm ở một tham số, và tham số đó không phải lãi suất

Công thức trung tâm là b̄ = (τN − γ)/(r + ζ̃ + λ − δ − g). Mọi thứ khác trong bài là cách lấy số cho các chữ cái này. Vì vậy điều đáng làm nhất là nhìn xem trong mẫu số, chữ cái nào thực sự chi phối.

Với nhóm nước thu nhập thấp, các giá trị hiệu chỉnh là: lãi phi rủi ro r = 0,9%, tăng trưởng g = 4,3%, lợi suất tiện ích δ = 0,1%, tần suất nợ nhảy vọt ζ̃ = 8,2%, chi phí phòng ngừa λ = 3,3%.

Đặt cạnh nhau thì kết quả rất đáng chú ý. Phần "chênh lệch lãi suất – tăng trưởng" quen thuộc, r − g − δ, bằng **−3,5%**, tức **âm**: theo số học nợ thông thường, các nước này đang ở trạng thái mà nợ tự tan dần và về lý thuyết có thể vay không giới hạn. Cái duy nhất làm cho ngưỡng nợ trở nên hữu hạn là ζ̃ + λ = **11,5%**.

Nói cách khác, trong mô hình này, **giới hạn vay của một nước đang phát triển hoàn toàn không do chi phí vốn quyết định, mà do tần suất các cú sốc nợ nhảy vọt và mức biến động sản lượng quyết định**. Đây là một kết luận có nội dung thật và đi ngược trực tiếp với cách tranh luận phổ biến, vốn xoay quanh lãi suất và chênh lệch lợi suất. Bài đưa ra dữ liệu để rút ra kết luận này nhưng không bao giờ phát biểu nó.

So sánh với nhóm phát triển làm điều này rõ hơn nữa: ζ̃ giảm từ 8,2% xuống 4,3% và λ từ 3,3% xuống 1,6%, tổng cộng giảm 5,6 điểm; trong khi tăng trưởng giảm từ 4,3% xuống 2,1%, tức đi ngược lại 2,2 điểm. Ưu thế của nước giàu không nằm ở việc họ tăng trưởng tốt hơn — họ tăng trưởng kém hơn hẳn — mà ở việc **họ ít bị bất ngờ hơn**.

### Tham số quyết định nhất là một thước đo minh bạch tài khoá, và nó được đo bằng quá khứ

Nếu ζ̃ chi phối kết quả, thì phải hỏi ζ̃ được đo bằng gì. Bài hiệu chỉnh nó bằng phân phối Pareto của các lần tỷ lệ nợ trên GDP tăng hơn 10 điểm trong lịch sử, và đưa ra ví dụ minh hoạ cho nguồn gốc của những cú nhảy đó: **nợ ngoài ngân sách lộ ra**.

Đây là một chi tiết có sức nặng lớn hơn vẻ ngoài của nó. Nợ nhảy vọt vì nợ ngoài ngân sách lộ ra không phải một cú sốc kinh tế; đó là một sự kiện **kế toán và quản trị**. Nó xảy ra khi bảo lãnh chính phủ bị gọi, khi nợ doanh nghiệp nhà nước được hợp nhất, khi một hợp đồng hợp tác công tư có điều khoản bảo đảm doanh thu phải được ghi nhận, hoặc khi một khoản vay song phương có điều khoản bảo mật được công bố.

Từ đó rút ra một hàm ý chính sách mà bài hoàn toàn không nêu, dù nó là hàm ý trực tiếp nhất của chính mô hình: **cách rẻ nhất để nâng trần nợ của một nước không phải là tăng thuế hay cắt chi, mà là thu hẹp phần nghĩa vụ không được ghi nhận**. Với nhóm thu nhập thấp, nếu ζ̃ giảm từ 8,2% xuống mức của nước phát triển là 4,3%, mẫu số giảm gần một nửa và ngưỡng nợ gần như tăng gấp đôi — mà không cần thay đổi một đồng thuế hay chi nào.

Điều đó cũng có nghĩa là nếu dùng mô hình này để đánh giá một nước, thì tham số cần tranh luận nhất không phải là dự báo tăng trưởng mà là **ước lượng quy mô của phạm vi nghĩa vụ tiềm tàng**. Và đó lại chính là con số khó nhất để biết.

Mặt trái của điều trên: ζ̃ được lấy từ **lịch sử nhảy nợ của chính nước đó**. Một nước từng có nhiều đợt nợ tăng vọt sẽ bị gán tần suất cao, và do đó bị gán ngưỡng nợ thấp.

Điều này tạo ra một vòng luẩn quẩn nhẹ. Các đợt nợ tăng vọt trong quá khứ thường chính là hệ quả của những cuộc khủng hoảng mà ngưỡng nợ được cho là dùng để dự báo. Gán cho một nước từng khủng hoảng một ngưỡng thấp rồi thấy ngưỡng đó khớp với việc nước đó gặp khó khăn nợ không hẳn là một kiểm chứng; nó gần với việc đọc lại đầu vào.

Vấn đề đối xứng cũng đáng nói: một nước chưa bao giờ có đợt nhảy nợ nào vì đơn giản **chưa bao giờ vay được nhiều** sẽ nhận một ζ̃ thấp và một ngưỡng hào phóng. Mô hình không phân biệt được "chưa từng gặp rắc rối vì quản trị tốt" với "chưa từng gặp rắc rối vì chưa từng có cơ hội".

### Việc khớp với xếp hạng của IMF là một kiểm chứng yếu hơn vẻ ngoài

Bài dùng sự tương ứng giữa khoảng cách tới ngưỡng và các xếp hạng rủi ro trong khung đánh giá bền vững nợ của IMF làm bằng chứng ủng hộ. Con số thì đẹp: khoảng cách đi từ +28,8 ở nhóm rủi ro thấp xuống +3,4 ở nhóm rủi ro cao và −44,0 ở nhóm đang khó khăn.

Nhưng cần thấy khoảng cách được định nghĩa là **b̄ trừ đi b**, trong đó b là mức nợ thực tế. Và phương sai của b giữa các nước lớn hơn hẳn phương sai của b̄: b̄ chỉ chạy từ khoảng 57% tới 124% theo nhóm, trong khi nợ thực tế của các nước trong mẫu trải từ dưới 20% tới trên 200% GDP. Nghĩa là đại lượng "khoảng cách" phần lớn bị chi phối bởi chính b.

Khi đó, phát hiện rằng "khoảng cách tới ngưỡng giảm đều theo mức rủi ro" phần lớn tương đương với phát hiện rằng "**nước nợ cao hơn thì được xếp hạng rủi ro cao hơn**" — điều đúng theo thiết kế của các khung xếp hạng, vì chúng đều lấy mức nợ làm đầu vào chính. Kiểm chứng thật sự phải là kiểm tra xem b̄ có bổ sung thông tin gì **vượt ra ngoài** b hay không, tức là chạy một hồi quy xếp hạng lên cả hai và xem b̄ có hệ số riêng không. Bài không làm phép kiểm tra đó.

### Nhánh trái của đường cong ngưỡng là một sản phẩm của giả định cam kết

Kết quả gây ngạc nhiên nhất về mặt định tính là hình chữ đồi: khi chi tiêu còn thấp hơn một mức nào đó, **chi nhiều hơn làm tăng ngưỡng nợ**. Lý do trong mô hình rất rõ ràng — chừng nào thuế tối ưu chưa chạm trần, chi tiêu cao hơn hàm ý thuế tương lai cao hơn, tức năng lực trả nợ cao hơn.

Cơ chế này đòi một giả định cụ thể: thuế suất điều chỉnh **tự động và tức thì** theo nhu cầu trả nợ. Bài thừa nhận trong thực tế việc đó cần quy trình lập pháp, chậm và khó, rồi gạt đi bằng lập luận rằng điều đó không ảnh hưởng tới đánh giá dài hạn.

Lập luận gạt đi này không đứng vững, vì nhánh trái của đường cong **chính là** một mệnh đề dài hạn. Nó nói rằng một nước chi 16% GDP có năng lực gánh nợ thấp hơn cùng nước đó nếu chi 21% GDP. Mệnh đề này chỉ đúng nếu việc nâng thuế lên tương ứng là chắc chắn. Nếu ngược lại — nếu chi tiêu dễ tăng và khó giảm, trong khi thuế khó tăng, đúng như lịch sử tài khoá của hầu hết các nước cho thấy — thì chi cao hơn không phải là bằng chứng của năng lực thuế tiềm tàng mà là bằng chứng của một nghĩa vụ cứng.

Có một bất đối xứng ngay trong thiết kế mô hình làm rõ điều này: **thuế được tối ưu hoá, còn chi tiêu là ngoại sinh**. Trong kinh tế chính trị thực tế, quan hệ thường ngược lại: chi tiêu là thứ được lựa chọn qua đấu tranh chính trị, còn năng lực thuế là ràng buộc kỹ thuật và thể chế không thay đổi nhanh được.

### Lợi suất tiện ích, áp chế tài chính, và những thứ bị giả định đi

Bài đặt δ = 0,5% cho Mỹ, Nhật, Đức và 0,1% cho các nước còn lại, gọi đó là lợi suất tiện ích của tài sản an toàn, rồi ghi thêm một dòng rằng nó "cũng có thể là áp chế tài chính".

Dòng ghi thêm đó đáng được viết thành một mục riêng. Về mặt toán học, hai hiện tượng này giống hệt nhau: cả hai đều làm chính phủ vay được dưới mức lãi suất phi rủi ro, và cả hai đều làm tăng ngưỡng nợ. Về mặt kinh tế và phân phối, chúng đối lập. Lợi suất tiện ích thật là một khoản chuyển giao **từ nhà đầu tư nước ngoài** sang chính phủ phát hành, vì thế giới sẵn sàng trả giá để nắm tài sản an toàn. Áp chế tài chính là một khoản chuyển giao **từ người tiết kiệm trong nước** sang chính phủ, vì họ không có lựa chọn nào khác.

Hệ quả thực tiễn là một cái bẫy rất cụ thể. Một nước có thị trường trái phiếu chính phủ do các định chế trong nước bị ràng buộc về quy định chi phối sẽ quan sát được lợi suất thấp, và nếu đưa lợi suất đó vào mô hình thì sẽ nhận được một δ dương và một **ngưỡng nợ được nâng lên**. Nhưng cái được đo không phải là năng lực vay; đó là một khoản thuế ngầm đang được thu từ người gửi tiết kiệm. Mô hình sẽ báo rằng nước đó còn nhiều dư địa, đúng vào lúc dư địa ấy đang được tạo ra bằng cách bòn rút tiết kiệm trong nước. Đây là mối liên hệ trực tiếp với nhánh tài liệu về cơ cấu nợ và cơ sở nhà đầu tư trong cùng thư mục, nơi chi phí ẩn dài hạn của cấu hình này được mô tả chi tiết.

Bài nói thẳng: mô hình **không xét cơ cấu kỳ hạn, cơ cấu tiền tệ hay kỳ vọng lạm phát**. Lời thừa nhận này thành thật nhưng cũng chỉ ra một giới hạn sâu.

Ba thứ bị bỏ ra chính là ba thứ quyết định một nước có gặp khủng hoảng hay không tại một mức nợ cho trước. Một nước có nợ 80% GDP, toàn bộ bằng nội tệ, kỳ hạn bình quân mười năm, lãi cố định, là một nước hoàn toàn khác với một nước có nợ 80% GDP, một nửa bằng ngoại tệ, kỳ hạn bình quân hai năm. Trong mô hình này chúng có cùng b̄ nếu các tham số vĩ mô giống nhau.

Đặt cạnh tài liệu về cơ cấu nợ chính phủ trong cùng thư mục, hai công trình gần như phản biện lẫn nhau. Công trình kia kết luận rằng **không có khung lý thuyết nào diễn giải thống nhất được các mẫu hình về cơ cấu nợ**, và rằng cơ cấu là thứ quyết định chi phí và rủi ro. Công trình này tính ra một con số về mức nợ bằng cách giả định cơ cấu đi. Cả hai đều hợp lệ trong phạm vi của mình, nhưng đặt chúng cạnh nhau thì rõ rằng con số b̄ nên được đọc như một **chỉ báo về nền tảng vĩ mô tài khoá**, không phải như một ngưỡng an toàn.

### 54 nước đã vượt ngưỡng mà chưa vỡ nợ, và cách đọc công thức cho Việt Nam

Con số được nhấn mạnh — 54 trên 172 nước đã có nợ vượt mức bền vững tối đa năm 2024 — cần được đối chiếu với định nghĩa của chính ngưỡng đó: mức mà tại đó chính phủ **bàng quan giữa trả nợ và vỡ nợ**.

Nếu gần một phần ba số nước trên thế giới đang ở trên điểm bàng quan mà phần lớn vẫn tiếp tục trả nợ bình thường, thì có ba khả năng. Hoặc hiệu chỉnh cho ra ngưỡng quá thấp một cách có hệ thống. Hoặc chính phủ thực tế có lý do để trả nợ mà mô hình không nắm được — chi phí chính trị, mất khả năng tiếp cận viện trợ, hệ luỵ cho hệ thống ngân hàng trong nước, quan hệ ngoại giao. Hoặc ngưỡng không phải một điểm mà là một vùng rộng, và việc vượt qua nó chỉ làm tăng xác suất chứ không kích hoạt gì.

Bài tự bảo vệ bằng câu rằng mọi con số chỉ mang tính minh hoạ, và đó là một lời rào đón đúng mực. Nhưng nó cần được giữ nguyên mỗi lần con số được trích dẫn. Trong thực tế, các con số ngưỡng có tuổi thọ dài hơn các lời rào đón đi kèm chúng — đúng như số phận của ngưỡng 90% trong nhánh tài liệu về nợ và tăng trưởng của thư mục này.

Áp khung này cho Việt Nam sẽ cho một ngưỡng tương đối rộng rãi nếu chỉ nhìn các tham số quan sát được: tăng trưởng g cao, làm mẫu số co lại mạnh; chi tiêu chính phủ γ ở mức vừa phải so với nhóm nước phát triển; biến động sản lượng λ tương đối thấp so với mặt bằng nước đang phát triển. Ba yếu tố này đều đẩy b̄ lên.

Nhưng chính cấu trúc của công thức chỉ ra nơi cần dồn chú ý, và đó không phải ba yếu tố trên.

**ζ̃ là biến cần tranh luận.** Với Việt Nam, nguồn nhảy nợ đáng kể nhất không phải một cú sốc vĩ mô mà là việc hợp nhất hoặc hiện thực hoá các nghĩa vụ hiện đang nằm ngoài nợ công trực tiếp: bảo lãnh chính phủ, nghĩa vụ theo hợp đồng hợp tác công tư trong hạ tầng, và nợ của doanh nghiệp nhà nước. Theo logic của mô hình, quy mô và mức độ được kiểm soát của phạm vi này có tác động lên năng lực gánh nợ **lớn hơn nhiều** so với vài điểm phần trăm nợ công trên GDP.

**δ là biến dễ bị đọc sai nhất.** Lợi suất trái phiếu chính phủ Việt Nam thấp một phần vì cơ sở nhà đầu tư trong nước bị ràng buộc về quy định. Đưa mức lợi suất đó vào mô hình sẽ sinh ra một δ dương và một ngưỡng nợ cao hơn, trong khi thực chất đang đo một khoản chuyển giao từ người tiết kiệm trong nước. Đây là chỗ mô hình sẽ đưa ra tín hiệu sai một cách có hệ thống.

**τ̄ là biến có dư địa thật.** Bài ghi nhận rằng theo đánh giá của IMF, cải cách toàn diện có thể nâng thu thêm khoảng 3 tới 5 điểm phần trăm GDP trong trung hạn. Trong công thức, mỗi điểm phần trăm tăng thêm của τN đi thẳng vào tử số. Với một mẫu số cỡ 5–7%, một điểm năng lực thuế đổi được khoảng 15–20 điểm phần trăm GDP năng lực gánh nợ. Đó là một tỷ lệ chuyển đổi rất đáng chú ý, và nó liên hệ trực tiếp với nhánh tài liệu về nguyên lý đánh thuế và huy động thu trong nước ở các thư mục khác của repo.

# Cách tính tỷ suất lợi nhuận bài toán mua bán bò

**Nguồn:** AI WikiMoney (wikimoney.ai.vn), chuyên mục Đầu tư › Lãi suất / Tỷ suất lợi nhuận, đăng ngày 9/9/2025. https://wikimoney.ai.vn/cach-tinh-ty-suat-loi-nhuan-bai-toan-mua-ban-bo-3819.html
**Tác giả:** Lâm Minh Chánh (trích từ sách "Tài chính cá nhân dành cho người Việt Nam").
**Ý chính:** Bài toán mua bán bò quen thuộc có đáp án 5 triệu tiền lời, không phải 1 triệu, vì mỗi phi vụ mua rồi bán là một vị thế độc lập, giá bán lần trước không phải giá vốn của lần mua sau. Tỷ suất sinh lợi cũng không phải 5/11 = 45,45% mà phải tính bằng IRR trên dòng tiền theo tháng: 9,34%/tháng, tương đương 191,93%/năm nếu lãi kép. Bài học: luôn nghĩ theo dòng tiền và giá trị thời gian của tiền, và nhớ rằng ngoài đời 10–15%/năm bền vững đã là xuất sắc.

## Sơ đồ

### Hai phi vụ độc lập

```text
  Cuối T3/2019        Cuối T4         Cuối T6          Cuối T10
  MUA bò 7tr ───────▶ BÁN 10tr        MUA lại 14tr ───▶ BÁN 16tr
  (mở vị thế)         (đóng vị thế)   (mở vị thế mới)   (đóng vị thế)
       └── Phi vụ 1: −7 + 10 = +3 ──┘ └── Phi vụ 2: −14 + 16 = +2 ──┘
                                │
                                ▼
            Tổng lời = 3 + 2 = 5 triệu  (= −7 + 10 − 14 + 16)
            SAI: coi 10tr là giá vốn → "lỗ 4tr" khi mua lại → 1tr
```

### Ba cách tính tỷ suất, từ sai đến đúng

```text
  Bỏ qua thời gian, lời/vốn ..... 5/11 = 45,45%   (ít sai hơn, vẫn sai)
                    │
                    ▼
  IRR trên dòng tiền tháng .............. 9,34%/tháng     (đúng)
                    │
          ┌─────────┴──────────┐
          ▼                    ▼
  Quy năm lãi đơn:      Quy năm lãi kép:
  9,34% × 12 = 112,08%  (1,0934)^12 − 1 = 191,93%
```

## Ba câu hỏi bài viết trả lời

1. Tổng cộng B lời hay lỗ bao nhiêu sau bốn lần mua bán, và vì sao nhiều người tính ra 1 triệu?
2. Vì sao lấy tiền lời chia vốn bỏ ra (5/11) vẫn là cách tính sai tỷ suất sinh lợi?
3. Tính tỷ suất sinh lợi tháng và năm bằng IRR như thế nào, và kiểm chứng ra sao?

## Dàn ý chi tiết

### 1. Đề bài
- Cuối tháng 3/2019: B mua bò X giá 7 triệu.
- Cuối tháng 4: B bán bò X giá 10 triệu.
- Cuối tháng 6: B mua lại bò X giá 14 triệu.
- Cuối tháng 10: B bán lại bò X giá 16 triệu.
- Hỏi: (1) B lời/lỗ bao nhiêu? (2) Tỷ suất sinh lợi tính theo năm là bao nhiêu?

### 2. Câu 1: tính lời/lỗ
- **Cách sai phổ biến:** mua 7 bán 10 → lời 3; mua lại 14 → "lỗ 4" (vì tự coi giá vốn là 10); mua 14 bán 16 → lời 2; tổng 3 − 4 + 2 = 1 triệu.
- Chỗ sai: B vừa bán 10 triệu nên người giải mặc nhiên coi giá vốn của con bò là 10 triệu. Giả định này sai.
- **Tư duy đúng theo từng phi vụ:**
  - Một phi vụ bắt đầu khi trả tiền mua (mở trạng thái, open position) và kết thúc khi thu tiền bán (đóng trạng thái, close position).
  - Nếu bán khống (bán trước, mua sau) thì ngược lại: bán là mở, mua là đóng.
  - Cuối tháng 3: mở vị thế, bỏ ra 7 triệu, có 1 con bò.
  - Cuối tháng 4: đóng vị thế, không còn bò; phi vụ 1 lời −7 + 10 = +3 triệu.
  - Cuối tháng 6: mở vị thế mới, không liên quan phi vụ trước; chưa thể nói lời/lỗ cho đến khi bán.
  - Cuối tháng 10: đóng vị thế; phi vụ 2 lời −14 + 16 = +2 triệu.
- Tổng: 3 + 2 = 5 triệu (đúng).
- Cách nhanh: cộng các dòng tiền −7 + 10 − 14 + 16 = 5 triệu.

### 3. Câu 2: tỷ suất sinh lợi
- Phần lớn người giải sai vì bỏ qua giá trị thời gian của tiền: không được cộng trừ nhân chia trực tiếp tiền của tháng X và tháng Y.
- **Cách "có logic" nhưng vẫn sai:** lời 5 triệu; vốn bỏ ra 7 triệu ban đầu + 4 triệu thêm ở phi vụ 2 (14 − 10) = 11 triệu; tỷ suất = 5/11 = 45,45%. Cách này ít sai hơn nhưng vẫn sai.
- **Cách đúng: IRR trên dòng tiền theo tháng:**

| Thời điểm | Dòng tiền (triệu) | Giá trị hiện tại ở 9,34%/tháng |
|---|---|---|
| Cuối T3 | −7 | −7 / 1,0934^0 = −7,00 |
| Cuối T4 | +10 | 10 / 1,0934^1 ≈ 9,15 |
| Cuối T5 | 0 | 0 |
| Cuối T6 | −14 | −14 / 1,0934^3 ≈ −10,71 |
| Cuối T7 | 0 | 0 |
| Cuối T8 | 0 | 0 |
| Cuối T9 | 0 | 0 |
| Cuối T10 | +16 | 16 / 1,0934^7 ≈ 8,56 |
| **Tổng** | | **≈ 0** |

- IRR = 9,34%/tháng; tổng giá trị hiện tại bằng 0 xác nhận kết quả.

### 4. Quy ra tỷ suất năm
- Theo lãi đơn: 9,34% × 12 = 112,08%/năm.
- Theo lãi kép: (1 + 9,34%)^12 − 1 = 191,93%/năm.
- Kiểm tra: 100 đồng với 9,34%/tháng sau 12 tháng = 100 × 1,0934^12 = 291,93 đồng; 100 đồng với 191,93%/năm sau 1 năm = 291,93 đồng. Hai kết quả bằng nhau.
- Tóm lại: lời 5 triệu; tỷ suất tháng 9,34%; tỷ suất năm 191,93% (giả sử B lặp lại được chu kỳ đầu tư này).

### 5. Ghi chú của tác giả
- Bài chỉ nhằm dạy cách tính lời lỗ và tỷ suất sinh lợi, không minh họa một hình thức đầu tư thực tế.
- Thực tế, đạt 10–15%/năm trong thời gian dài đã là rất xuất sắc.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Mở trạng thái (open position) | Lúc trả tiền ra mua tài sản, bắt đầu một phi vụ |
| Đóng trạng thái (close position) | Lúc bán tài sản thu tiền về, kết thúc phi vụ |
| Bán khống (short selling) | Bán trước mua sau; bán là mở, mua là đóng |
| Giá vốn (cost basis) | Số tiền thực bỏ ra để mua tài sản trong một phi vụ |
| Dòng tiền (cash flow) | Các khoản tiền ra (âm) và vào (dương) theo thời gian |
| Giá trị thời gian của tiền (time value of money) | Tiền ở các thời điểm khác nhau không cộng trừ trực tiếp được |
| IRR (tỷ suất hoàn vốn nội bộ) | Lãi suất làm tổng giá trị hiện tại các dòng tiền bằng 0 |
| Quy đổi lãi đơn / lãi kép | Nhân lãi tháng với 12, hoặc (1 + lãi tháng)^12 − 1 |

## Câu nói đáng nhớ

> "Vì B mới bán ra 10 triệu nên các bạn tự động giả định rằng giá vốn của bò X là 10 triệu... Giả định như thế là SAI."

> "Tiền có giá trị theo thời gian, nên không thể cộng trừ hay nhân chia trực tiếp giữa tiền của tháng X và tháng Y."

> "Trong thực tế, nếu đạt được tỷ suất sinh lợi 10%–15%/năm trong thời gian dài đã là rất xuất sắc rồi."

## Đánh giá và phát hiện đáng chú ý

### Lời giải câu 1 rất chuẩn và giải tỏa một lỗi tư duy phổ biến
Lỗi "lỗ 4 triệu khi mua lại" là một dạng thiên lệch neo giá (anchoring): người ta neo vào giá bán gần nhất như thể đó là chi phí. Cách nhìn theo vị thế mở/đóng và cách cộng thẳng các dòng tiền giúp tránh lỗi này. Bài học áp dụng trực tiếp cho người lướt sóng cổ phiếu: bán ra rồi mua lại giá cao hơn không phải là "lỗ", mà là bỏ lỡ một phần lợi nhuận; lời lỗ chỉ đo bằng tiền vào trừ tiền ra.

### Các con số đều kiểm tra được và đúng
IRR của dòng tiền (−7; 10; 0; −14; 0; 0; 0; 16) đúng là khoảng 9,34%/tháng; quy năm lãi kép ra 191,93% và lãi đơn ra 112,08%. Ba giá trị hiện tại 9,15; −10,71; 8,56 cũng khớp. Bài không có lỗi số học.

### "Đúng" ở đây phụ thuộc vào giả định về thời gian vốn nằm chờ
IRR coi khoảng tháng 4 đến tháng 6, khi B cầm 10 triệu trong tay, là thời gian tiền không sinh lời nhưng vẫn tính vào tổng thời gian. Đồng thời IRR ngầm giả định 10 triệu thu về ở tháng 4 có thể tái đầu tư ở mức 9,34%/tháng, điều không thực tế. Một cách đo khác là IRR hiệu chỉnh (MIRR) với lãi tái đầu tư bằng lãi tiết kiệm. Ngoài ra, dòng tiền đổi dấu ba lần nên về lý thuyết IRR có thể có nhiều nghiệm; ở bài này chỉ có một nghiệm hợp lý, nhưng người học nên biết giới hạn đó.

### Con số 191,93%/năm dễ bị hiểu sai nếu đọc không kỹ
Tỷ suất năm chỉ có ý nghĩa nếu B lặp lại được chu kỳ trong suốt 12 tháng với cùng hiệu suất, điều bài có ghi chú. Quy năm một phi vụ ngắn hạn là cách các mô hình lừa đảo hay dùng để thổi phồng "lợi nhuận". Chính tác giả kết bài bằng mốc 10–15%/năm, đó là chuẩn mực người đọc nên giữ.

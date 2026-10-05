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

## Khái niệm cần biết

**Phi vụ, mở vị thế và đóng vị thế (open / close position).** Một phi vụ bắt đầu khi bạn trả tiền mua tài sản (mở vị thế) và kết thúc khi bạn bán tài sản thu tiền về (đóng vị thế). Lời hay lỗ của phi vụ chỉ biết được khi đã đóng vị thế. Ví dụ trong bài: mua bò 7 triệu rồi bán 10 triệu là một phi vụ trọn vẹn, lời 3 triệu. Cách nhìn này là chìa khoá để giải đúng câu 1.

**Giá vốn (cost basis).** Số tiền thực sự bỏ ra để mua tài sản trong một phi vụ. Ví dụ trong bài: ở phi vụ thứ hai, giá vốn là 14 triệu (giá mua lại), chứ không phải 10 triệu (giá vừa bán ở phi vụ trước). Nhầm giá vốn là nguồn gốc của đáp án sai "lời 1 triệu".

**Bán khống (short selling).** Bán một tài sản trước (thường là tài sản đi mượn) rồi mua lại sau. Khi đó bán là mở vị thế, mua là đóng vị thế. Ví dụ minh hoạ: mượn một con bò bán 10 triệu, sau đó mua lại 8 triệu để trả, lời 2 triệu. Bài nêu khái niệm này để cho thấy thứ tự mở/đóng phụ thuộc vào cách phi vụ bắt đầu.

**Dòng tiền (cash flow).** Danh sách các khoản tiền ra (dấu âm) và vào (dấu dương) theo thời gian. Ví dụ trong bài: dòng tiền theo tháng của B là −7; +10; 0; −14; 0; 0; 0; +16 (triệu). Cộng thẳng các con số này cho tổng lời 5 triệu.

**Giá trị thời gian của tiền (time value of money).** Một đồng nhận hôm nay đáng giá hơn một đồng nhận sau này, vì có thể đem đi sinh lời trong khoảng thời gian đó. Vì vậy không được cộng trừ nhân chia trực tiếp tiền của các tháng khác nhau khi tính tỷ suất. Đây là lý do cách tính 5/11 = 45,45% bị coi là sai.

**IRR (tỷ suất hoàn vốn nội bộ).** Mức lãi suất mỗi kỳ làm cho tổng giá trị hiện tại của mọi dòng tiền bằng 0. Ví dụ trong bài: dòng tiền của B có IRR 9,34%/tháng. Đây là cách đúng để đo tỷ suất sinh lợi khi tiền ra vào ở nhiều thời điểm.

**Quy đổi lãi tháng ra lãi năm.** Theo lãi đơn thì nhân lãi tháng với 12; theo lãi kép thì tính (1 + lãi tháng)^12 − 1. Ví dụ trong bài: 9,34%/tháng quy ra 112,08%/năm (lãi đơn) hoặc 191,93%/năm (lãi kép). Cách lãi kép phản ánh đúng việc lợi nhuận mỗi tháng được tái đầu tư.

## Nội dung chi tiết

### 1. Đề bài

Bài toán quen thuộc như sau. B mua bán một con bò X bốn lần:

| Thời điểm | Giao dịch | Số tiền |
|---|---|---|
| Cuối tháng 3/2019 | Mua bò X | 7 triệu |
| Cuối tháng 4 | Bán bò X | 10 triệu |
| Cuối tháng 6 | Mua lại bò X | 14 triệu |
| Cuối tháng 10 | Bán lại bò X | 16 triệu |

Đề hỏi hai câu: (1) B lời hay lỗ bao nhiêu? (2) Tỷ suất sinh lợi tính theo năm là bao nhiêu?

### 2. Câu 1: tính lời/lỗ

**Cách sai phổ biến.** Nhiều người giải như sau: mua 7 bán 10 thì lời 3; mua lại với giá 14 thì "lỗ 4" (vì tự coi giá vốn của con bò là 10); mua 14 bán 16 thì lời 2. Tổng cộng 3 − 4 + 2 = 1 triệu.

Chỗ sai nằm ở bước giữa. Vì B vừa bán con bò với giá 10 triệu, người giải mặc nhiên coi 10 triệu là giá vốn của con bò, nên khi mua lại 14 triệu thì thấy như "mất" 4 triệu. Giả định này sai: lúc mua lại, B bỏ ra 14 triệu tiền thật, và đó mới là giá vốn của phi vụ mới. Việc trả giá cao hơn giá vừa bán chỉ có nghĩa là B bỏ lỡ một phần lợi nhuận nếu giữ con bò, chứ không phải một khoản lỗ.

**Tư duy đúng: tách theo từng phi vụ.** Một phi vụ bắt đầu khi trả tiền mua (mở trạng thái, open position) và kết thúc khi thu tiền bán (đóng trạng thái, close position). Nếu bán khống, tức bán trước mua sau, thì ngược lại: bán là mở, mua là đóng. Áp dụng vào bài:

| Thời điểm | Sự kiện | Kết quả |
|---|---|---|
| Cuối tháng 3 | Mở vị thế: bỏ ra 7 triệu, có 1 con bò | Chưa biết lời lỗ |
| Cuối tháng 4 | Đóng vị thế: bán bò, không còn bò | Phi vụ 1 lời −7 + 10 = +3 triệu |
| Cuối tháng 6 | Mở vị thế mới, không liên quan phi vụ trước | Chưa thể nói lời lỗ cho đến khi bán |
| Cuối tháng 10 | Đóng vị thế | Phi vụ 2 lời −14 + 16 = +2 triệu |

Tổng lời: 3 + 2 = 5 triệu. Đây là đáp án đúng.

**Cách nhanh.** Chỉ cần cộng mọi khoản tiền ra (âm) và vào (dương): −7 + 10 − 14 + 16 = 5 triệu. Cách này tự động tránh được lỗi coi giá bán là giá vốn, vì nó chỉ quan tâm tiền thật đi ra và đi vào.

### 3. Câu 2: tỷ suất sinh lợi

Theo bài, phần lớn người giải sai câu này vì bỏ qua giá trị thời gian của tiền. Tiền ở tháng X và tiền ở tháng Y không thể đem cộng trừ nhân chia trực tiếp với nhau.

**Cách "có logic" nhưng vẫn sai.** Lời 5 triệu. Vốn bỏ ra gồm 7 triệu ban đầu cộng 4 triệu phải bỏ thêm ở phi vụ 2 (vì mua lại 14 triệu trong khi chỉ có 10 triệu từ lần bán trước: 14 − 10 = 4), tổng 11 triệu. Tỷ suất = 5/11 = 45,45%. Cách này ít sai hơn cách tính lời 1 triệu, nhưng vẫn sai, vì nó không tính đến việc mỗi đồng vốn nằm trong phi vụ bao lâu.

**Cách đúng: IRR trên dòng tiền theo tháng.** Ghi dòng tiền của B cho từng tháng từ cuối tháng 3 đến cuối tháng 10, kể cả những tháng không có giao dịch (dòng tiền bằng 0), rồi tìm lãi suất tháng làm tổng giá trị hiện tại bằng 0:

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

Kết quả IRR = 9,34%/tháng. Việc tổng giá trị hiện tại các dòng tiền bằng 0 (−7,00 + 9,15 − 10,71 + 8,56 ≈ 0) xác nhận con số này đúng.

### 4. Quy ra tỷ suất năm

Có hai cách quy 9,34%/tháng ra năm:

| Cách quy đổi | Phép tính | Kết quả |
|---|---|---|
| Lãi đơn | 9,34% × 12 | 112,08%/năm |
| Lãi kép | (1 + 9,34%)^12 − 1 = (1,0934)^12 − 1 | 191,93%/năm |

Cách lãi kép đúng hơn vì giả định lợi nhuận mỗi tháng được đem đi tái đầu tư. Kiểm tra: 100 đồng sinh lời 9,34%/tháng trong 12 tháng thành 100 × 1,0934^12 = 291,93 đồng; 100 đồng sinh lời 191,93%/năm trong 1 năm cũng thành 291,93 đồng. Hai kết quả bằng nhau, chứng tỏ hai con số tương đương.

Tóm lại đáp án của bài: B lời 5 triệu; tỷ suất sinh lợi 9,34%/tháng; tỷ suất năm 191,93%, với giả định B lặp lại được chu kỳ đầu tư này suốt cả năm.

Ba cách tính tỷ suất xếp từ sai đến đúng:

| Cách | Kết quả | Đánh giá |
|---|---|---|
| Lời chia vốn, bỏ qua thời gian | 5/11 = 45,45% | Ít sai hơn nhưng vẫn sai |
| IRR trên dòng tiền tháng | 9,34%/tháng | Đúng |
| Quy năm từ IRR | 112,08% (lãi đơn) hoặc 191,93% (lãi kép) | Lãi kép là cách quy đúng |

### 5. Ghi chú của tác giả

Tác giả nói rõ bài toán chỉ nhằm dạy cách tính lời lỗ và tỷ suất sinh lợi, không minh hoạ một hình thức đầu tư thực tế. Con số 191,93%/năm là kết quả của một bài toán số học, không phải mức lợi nhuận có thể kỳ vọng.

Theo tác giả, trong thực tế, đạt tỷ suất sinh lợi 10–15%/năm trong thời gian dài đã là rất xuất sắc. Ví dụ minh hoạ: 100 triệu đồng tăng đều 12%/năm trong 10 năm thành khoảng 310 triệu đồng, một kết quả rất tốt dù kém xa con số gần 192% mỗi năm của bài toán con bò.

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

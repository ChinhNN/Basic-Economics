# Cách tính lãi suất từ A đến Z: hướng dẫn toàn diện

**Nguồn:** AI WikiMoney (wikimoney.ai.vn), chuyên mục Đầu tư › Lãi suất / Tỷ suất lợi nhuận, đăng ngày 9/9/2025. https://wikimoney.ai.vn/cach-tinh-lai-suat-tu-a-den-z-huong-dan-toan-dien-3794.html
**Tác giả:** Lâm Minh Chánh.
**Ý chính:** Mọi công thức lãi suất đều xuất phát từ hai công thức một kỳ: lãi suất = (cuối kỳ − đầu kỳ)/đầu kỳ và cuối kỳ = đầu kỳ × (1 + lãi suất). Từ đó bài dựng dần lãi đơn, lãi kép, giá trị hiện tại/tương lai, tỷ suất bình quân hình học (CAGR), dòng niên kim cuối kỳ/đầu kỳ, hàm RATE và IRR trong Excel. Thông điệp thực hành: tiền có giá trị thời gian nên không được cộng tiền ở các mốc khác nhau; muốn so sánh phải quy về cùng một mốc, và khi lợi nhuận các năm không đều phải dùng bình quân hình học chứ không dùng trung bình cộng.

> **Lưu ý:** Ở mục dòng tiền đều (mục 8), phần "tính tay" của bài đánh số năm lệch một kỳ so với công thức. Bài ghi khoản 24 triệu đầu tiên ở "cuối năm 0" rồi cộng thêm mỗi năm, nên theo cách đánh số đó con số 442,07 triệu xuất hiện ở cuối năm 9 (nếu tiếp tục tới cuối năm 10 thì là 523,54 triệu). Tương tự, với dòng tiền đầu kỳ, 499,54 triệu rơi vào "cuối năm 9" theo cách đánh số của bài. Kết quả công thức (10 khoản góp) là đúng; chỉ nhãn năm trong phần tính tay bị lệch.

## Sơ đồ

### Từ công thức một kỳ đến IRR

```text
     CÔNG THỨC 1 KỲ: r = (Cuối − Đầu)/Đầu ;  Cuối = Đầu × (1 + r)
                              │
          ┌───────────────────┴───────────────────┐
          ▼                                       ▼
     LÃI ĐƠN (lãi rút ra)                 LÃI KÉP (lãi nhập gốc)
     Tổng = Gốc × (1 + r×n)               FV = PV × (1 + r)^n
     được cộng tiền khác năm              PV = FV / (1 + r)^n (chiết khấu)
                                               │
                ┌──────────────────────────────┼───────────────────┐
                ▼                              ▼                   ▼
     TSLN BÌNH QUÂN (CAGR)         DÒNG TIỀN ĐỀU (niên kim)   NHIỀU DÒNG
     (Cuối/Đầu)^(1/n) − 1          cuối kỳ / đầu kỳ           TIỀN KHÁC NHAU
     (không dùng trung bình cộng)  Excel: FV, RATE            Excel: IRR
```

### Vì sao không được cộng tiền khác mốc thời gian

```text
  100 hôm nay ──×(1+8%)^5──▶ 146,93 ở năm 5
  146,93 ở năm 5 ──÷(1+8%)^5──▶ 100 hôm nay
          │
          ▼
  Hai con số "khác nhau" nhưng TƯƠNG ĐƯƠNG → muốn cộng/so sánh
  phải đưa tất cả về MỘT mốc (thường là cuối năm 0 = hiện tại)
```

## Ba câu hỏi bài viết trả lời

1. Lãi suất, lãi đơn, lãi kép, giá trị hiện tại và giá trị tương lai được tính như thế nào, và tại sao sự tăng giá của đất, vàng, chứng chỉ quỹ cũng là lãi kép?
2. Khi lợi nhuận các năm không đều, vì sao trung bình cộng cho kết quả sai và phải dùng tỷ suất bình quân hình học?
3. Làm sao tính giá trị tương lai của dòng tiền góp đều, và tính tỷ suất lợi nhuận của khoản đầu tư có nhiều dòng tiền ra vào bằng RATE và IRR trong Excel?

## Khái niệm cần biết

**Lãi suất một kỳ (holding period return).** Phần tiền tăng thêm trong một kỳ chia cho số tiền lúc đầu kỳ. Ví dụ trong bài: đầu kỳ 100 đồng, cuối kỳ 108 đồng thì lãi suất là (108 − 100)/100 = 8%. Bài coi công thức này và công thức ngược lại của nó (cuối kỳ = đầu kỳ × (1 + lãi suất)) là gốc của mọi công thức khác.

**Lãi đơn (simple interest).** Lãi mỗi kỳ được rút ra, không nhập vào gốc, nên kỳ nào cũng chỉ có gốc ban đầu sinh lãi. Ví dụ trong bài: 100 đồng, 8%/năm, 5 năm thì mỗi năm lãi 8 đồng, tổng cộng 140 đồng. Đây là mốc so sánh để thấy sức mạnh của lãi kép.

**Lãi kép (compound interest).** Lãi mỗi kỳ được nhập vào gốc, nên kỳ sau cả gốc lẫn lãi cũ cùng sinh lãi. Ví dụ trong bài: cùng 100 đồng, 8%/năm, 5 năm thì thành 146,93 đồng thay vì 140. Theo bài, cả sự tăng giá của đất, vàng, chứng chỉ quỹ cũng là lãi kép.

**Giá trị hiện tại (PV) và giá trị tương lai (FV).** Giá trị tương lai là số tiền hôm nay sẽ lớn thành bao nhiêu sau n kỳ; giá trị hiện tại là số tiền hôm nay tương đương với một khoản ở tương lai. Ví dụ trong bài: ở lãi 8%/năm, 100 đồng hôm nay tương đương 146,93 đồng ở năm 5. Việc quy ngược từ tương lai về hiện tại gọi là **chiết khấu**.

**Giá trị thời gian của tiền.** Vì tiền có thể sinh lãi, một đồng hôm nay đáng giá hơn một đồng ở tương lai. Hệ quả: không được cộng thẳng các khoản tiền ở những thời điểm khác nhau. Ví dụ minh hoạ: 100 đồng hôm nay cộng 146,93 đồng ở năm 5 không phải là "246,93 đồng", mà là 200 đồng tính theo giá trị hôm nay (ở lãi 8%).

**Bình quân hình học, hay tốc độ tăng trưởng kép hằng năm (CAGR).** Mức tăng đều mỗi năm sao cho từ giá trị đầu đi đến đúng giá trị cuối: (Cuối/Đầu)^(1/n) − 1. Ví dụ trong bài: tài sản từ 100 triệu lên 148,43 triệu sau 7 năm có CAGR 5,80%/năm, trong khi trung bình cộng các năm là 7,14% và cho kết quả sai.

**Niên kim (annuity).** Chuỗi khoản tiền bằng nhau phát sinh đều mỗi năm, như góp tiết kiệm hay trả góp. Góp vào cuối mỗi năm gọi là niên kim cuối kỳ, góp đầu mỗi năm là niên kim đầu kỳ. Ví dụ trong bài: góp 24 triệu mỗi năm trong 10 năm ở 13%/năm thì được 442,07 triệu (cuối kỳ) hoặc 499,54 triệu (đầu kỳ).

**IRR (tỷ suất hoàn vốn nội bộ).** Mức lãi suất làm cho tổng giá trị hiện tại của mọi khoản tiền ra và vào của một khoản đầu tư bằng 0. Nói cách khác, đó là "lãi suất thật" mà khoản đầu tư mang lại. Ví dụ trong bài: căn nhà mua 5 tỷ năm 2010, cho thuê, rồi bán 11 tỷ năm 2018 có IRR 12,94%/năm. Đây là công cụ dùng khi các dòng tiền không đều.

## Nội dung chi tiết

### 1. Lãi suất một kỳ

Bài bắt đầu từ trường hợp đơn giản nhất. Đầu kỳ bạn có 100 đồng, sau 1 kỳ nhận về 108 đồng. Lãi suất của kỳ đó là phần tăng thêm chia cho số tiền ban đầu: (108 − 100)/100 = 0,08 = 8%.

Từ ví dụ này, bài rút ra hai công thức:

- **Lãi suất = (Số tiền cuối kỳ − Số tiền đầu kỳ)/Số tiền đầu kỳ.**
- **Số tiền cuối kỳ = Số tiền đầu kỳ × (1 + Lãi suất).** Đây chỉ là công thức trên viết ngược lại.

"Kỳ" có thể dài ngắn tuỳ ý: 1 tháng, 1 năm, 3 năm hay 5 tháng. Vì vậy, khi nói một mức lãi suất phải nói rõ kỳ của nó; 8% một tháng khác rất xa 8% một năm. Trong tài chính, kỳ thông dụng nhất là năm.

Bài nhấn mạnh hai công thức một kỳ này là nền tảng; mọi công thức phức tạp hơn ở phần sau đều chỉ là áp dụng chúng nhiều lần.

### 2. Lãi suất đơn (nhiều kỳ)

Lãi đơn là cách tính trong đó tiền lãi mỗi năm không được đưa vào gốc để tiếp tục sinh lãi.

Ví dụ: gốc 100 đồng, lãi 8%/năm, trong 5 năm. Cuối mỗi năm có 108 đồng, nhưng 8 đồng lãi được rút ra, nên đầu năm sau gốc vẫn chỉ là 100 đồng. Sau 5 năm, tổng lãi là 8 + 8 + 8 + 8 + 8 = 40 đồng, và tổng số tiền là 140 đồng.

Công thức gộp: **Tổng số tiền = Gốc × (1 + Lãi suất × Số kỳ)** = 100 × (1 + 8% × 5) = 100 × 1,4 = 140 đồng.

Bài lưu ý một điểm quan trọng: trong môi trường lãi đơn, vì lãi không sinh lãi, ta có thể cộng tiền của các năm với nhau. Trong môi trường lãi kép thì không được: muốn cộng phải đưa mọi khoản về cùng một mốc thời gian, thường là cuối năm 0, tức hiện tại.

### 3. Lãi suất kép (nhiều kỳ)

Lãi kép là cách tính trong đó tiền lãi mỗi năm được nhập vào gốc để tiếp tục sinh lãi. Với cùng dữ kiện 100 đồng, 8%/năm, 5 năm, số tiền tăng như sau:

| Thời điểm | Phép tính | Số tiền (đồng) |
|---|---|---|
| Cuối năm 0 | | 100,00 |
| Cuối năm 1 | 100 × 1,08 | 108,00 |
| Cuối năm 2 | 108 × 1,08 | 116,64 |
| Cuối năm 3 | 116,64 × 1,08 | 125,97 |
| Cuối năm 4 | 125,97 × 1,08 | 136,05 |
| Cuối năm 5 | 136,05 × 1,08 | 146,93 |

Gộp năm phép nhân lại: 100 × (1 + 8%)^5 = 146,93 đồng. So với lãi đơn (140 đồng), lãi kép cho thêm 6,93 đồng, chính là phần "lãi của lãi".

Công thức tổng quát: **Số tiền kỳ n = Số tiền đầu tiên × (1 + Lãi suất)^số kỳ.** Hệ số (1 + r)^n làm số tiền tăng theo luỹ thừa: lãi suất càng cao và thời gian càng dài thì kết quả càng lớn, và lớn nhanh dần.

Ví dụ của bài cho thấy khoảng cách khi thời gian dài: 100 triệu đồng ở 15%/năm trong 30 năm:

| Cách tính | Phép tính | Kết quả |
|---|---|---|
| Lãi kép | 100 × 1,15^30 | 6.621 triệu, khoảng 6,6 tỷ |
| Lãi đơn | 100 × (1 + 15% × 30) | 550 triệu |

Lãi kép cho kết quả gấp khoảng 12 lần lãi đơn.

### 4. Lãi chính là sự tăng giá của tài sản

Nhiều người nghĩ vàng, đất hay chứng chỉ quỹ không có lãi kép, vì không thấy chúng "trả lãi" định kỳ như tiết kiệm hay trái phiếu. Bài chỉ ra rằng với các tài sản này, lãi chính là sự tăng giá, và phần lãi đó nằm lại ngay trong tài sản.

Ví dụ: một miếng đất mua với giá 1.000.000.000 đồng, sau 1 năm lên 1.100.000.000 đồng. Tỷ suất lợi nhuận năm đó là (1,1 tỷ − 1 tỷ)/1 tỷ = 10%/năm, đúng công thức lãi suất một kỳ.

Nếu sau 5 năm miếng đất có giá 1.800.000.000 đồng, tỷ suất bình quân mỗi năm là (1,8 tỷ/1 tỷ)^(1/5) − 1 = 12,47%/năm. Kiểm tra lại: 1.000.000.000 × (1 + 12,47%)^5 = 1.800.000.000 đồng.

Vì phép tính dùng công thức lãi kép, tức giả định phần tăng giá mỗi năm tự "nhập gốc" và năm sau lại tăng tiếp trên giá mới, nên đây là lãi kép, dù không thấy khoản lãi nào được "sinh ra" và trả cho chủ đất. Cần nhớ đây là tỷ suất danh nghĩa, chưa trừ thuế, phí và lạm phát.

### 5. Giá trị hiện tại và giá trị tương lai

Bài định nghĩa:

- **Giá trị hiện tại (PV):** giá trị của một khoản tiền tại thời điểm bắt đầu.
- **Giá trị tương lai (FV):** giá trị của khoản tiền đó ở kỳ thứ N.

Hai giá trị liên hệ với nhau bằng công thức lãi kép: **FV = PV × (1 + Lãi suất)^số kỳ.**

Với lãi suất 8%/năm, 100 đồng hôm nay tương đương 108,00 đồng ở năm 1, 116,64 ở năm 2, 125,97 ở năm 3, 136,05 ở năm 4 và 146,93 ở năm 5. Đi theo chiều ngược lại, 146,93 đồng ở năm 5 có giá trị hiện tại là 100 đồng: 146,93 ÷ (1 + 8%)^5 = 100.

Việc quy một giá trị tương lai về hiện tại gọi là **chiết khấu**: **PV = FV/(1 + Lãi suất)^số kỳ.**

Ý nghĩa: 100 đồng hôm nay và 146,93 đồng ở năm 5 là hai con số "khác nhau" nhưng tương đương nhau (ở lãi 8%). Vì vậy muốn cộng hay so sánh các khoản tiền, phải đưa tất cả về một mốc, thường là cuối năm 0, tức hiện tại.

### 6. Giá trị thời gian của tiền

Vì có lãi suất nên tiền sinh ra tiền, và giá trị của một khoản tiền thay đổi theo thời điểm. Bài cho hai ví dụ:

- Ở lãi suất 12%/năm, 1 tỷ đồng hiện nay có giá trị ở năm thứ 9 là 1 × 1,12^9 = 2,77 tỷ.
- Ở lãi suất 15%/năm, 5 tỷ đồng nhận ở năm thứ 8 có giá trị hiện tại là 5/1,15^8 = 1,63 tỷ.

Ví dụ thứ hai cho thấy một khoản tiền lớn ở xa trong tương lai có thể "nhỏ" hơn nhiều khi quy về hôm nay. Hệ quả mà bài nhấn mạnh: không được cộng tiền ở các thời điểm khác nhau; phải đưa chúng về cùng một mốc rồi mới cộng.

### 7. Tỷ suất lợi nhuận bình quân tài chính (nhiều kỳ không đều)

Khi lợi nhuận mỗi năm khác nhau, câu hỏi "bình quân mỗi năm được bao nhiêu" cần được trả lời cẩn thận. Bài lấy ví dụ một tài sản trị giá 100 triệu đồng năm 2015, tăng giảm qua các năm như sau:

| Năm | Tăng trưởng | Giá trị (triệu) |
|---|---|---|
| 2015 | | 100,00 |
| 2016 | +10% | 110,00 |
| 2017 | +15% | 126,50 |
| 2018 | +16% | 146,74 |
| 2019 | +19% | 174,62 |
| 2020 | −20% | 139,70 |
| 2021 | −15% | 118,74 |
| 2022 | +25% | 148,43 |

**Cách sai: trung bình cộng.** Cộng các tỷ lệ rồi chia cho 7 năm: (10 + 15 + 16 + 19 − 20 − 15 + 25)/7 = 7,14%. Nếu tài sản thật sự tăng 7,14% mỗi năm, sau 7 năm nó phải là 100 × 1,0714^7 = 162,08 triệu, khác xa giá trị thật 148,43 triệu. Vậy trung bình cộng cho kết quả sai.

**Cách đúng: bình quân tài chính (bình quân hình học).** Tính (148,43/100)^(1/7) − 1 = 5,80%. Cho 100 triệu tăng đều 5,80%/năm trong 7 năm thì ra đúng 148,43 triệu.

Lý do trung bình cộng sai là vì các năm lỗ và lãi không bù trừ nhau theo phép cộng: giảm 20% rồi tăng 20% không đưa tài sản về chỗ cũ. Bình quân hình học tránh vấn đề này vì nó coi tài sản tăng đều mỗi năm và chỉ cần ba thông tin: điểm đầu (100), điểm cuối (148,43) và số kỳ (7).

Công thức: **TSLNBQ = (Số cuối/Số đầu)^(1/số kỳ) − 1.** Tốc độ tăng trưởng kép hằng năm (CAGR) dùng trong kinh tế cũng được tính đúng theo cách này.

### 8. Dòng tiền đều hằng kỳ (chuỗi tiền tệ, niên kim)

Khi một khoản tiền bằng nhau phát sinh đều đặn mỗi kỳ, ta gọi đó là chuỗi tiền tệ; khi kỳ là năm thì gọi là dòng niên kim (annuities). Câu hỏi thường gặp là: góp đều như vậy thì sau n năm có bao nhiêu?

**8.1 Dòng tiền cuối kỳ.** Bạn A cuối mỗi năm tích luỹ được 24 triệu đồng và đầu tư vào chứng chỉ quỹ có tỷ suất bình quân 13%/năm. Hỏi đến cuối năm thứ 10 có bao nhiêu tiền?

Cách tính tay theo bài: có 24 triệu, sinh lãi 24 × 13% = 3,12 triệu, thành 27,12 triệu; cộng thêm khoản góp 24 triệu mới thì được 51,12 triệu. Kỳ sau: 51,12 × 13% = 6,65 triệu lãi, thành 57,77; cộng 24 thì được 81,77 triệu. Cứ tiếp tục như vậy, số dư lần lượt là 116,40; 155,53; 199,74; 249,71; 306,17; 369,98 và 442,07 triệu.

Cách tính bằng công thức: **FV = PMT × [(1 + r)^n − 1]/r** = 24 × [(1,13)^10 − 1]/0,13 = 24 × 18,41975 = 442,07 triệu đồng. Ở đây PMT là khoản góp mỗi kỳ, và hệ số [(1 + r)^n − 1]/r gọi là hệ số niên kim của dòng tiền cuối kỳ.

Lưu ý về cách đánh số năm: phần tính tay của bài đặt khoản 24 triệu đầu tiên ở "cuối năm 0", nên theo cách đánh số đó, 442,07 triệu rơi vào cuối năm 9 (nếu tính tiếp tới cuối năm 10 thì là 523,54 triệu). Cách đánh số đúng với công thức là: khoản góp đầu tiên ở cuối năm 1, khoản thứ mười ở cuối năm 10, và số dư cuối năm 10 là 442,07 triệu. Kết quả của công thức (10 khoản góp) là đúng.

Trong Excel: **FV(Rate = 13%, Nper = 10, PMT = −24, PV = 0, Type = 0) = 442,07.** PMT mang dấu âm vì là tiền bỏ ra (outflow); kết quả mang dấu dương vì là tiền nhận về (inflow); Type = 0 nghĩa là góp vào cuối kỳ.

**8.2 Dòng tiền đầu kỳ.** Cùng dữ kiện, nhưng bạn A góp vào đầu mỗi năm.

Cách tính tay theo bài: khoản 24 triệu góp đầu kỳ sinh lãi 3,12, thành 27,12 vào cuối kỳ. Kỳ sau cộng 24 thành 51,12, sinh lãi 6,65, thành 57,77. Kỳ sau cộng 24 thành 81,77, sinh lãi 10,63, thành 92,40. Tiếp tục, số dư lần lượt là 131,53; 175,74; 225,71; 282,17; 345,98; 418,07 và 499,54 triệu. Tương tự như trên, theo cách đánh số của bài, 499,54 triệu rơi vào "cuối năm 9".

Công thức: **FV = PMT × [(1 + r)^n − 1] × (1 + r)/r** = 24 × 20,8143 = 499,54 triệu đồng. Hệ số [(1 + r)^n − 1](1 + r)/r là hệ số niên kim của dòng tiền đầu kỳ. Trong Excel: **FV(13%, 10, −24, 0, Type = 1) = 499,54.**

| | Cuối kỳ (Type = 0) | Đầu kỳ (Type = 1) |
|---|---|---|
| Hệ số niên kim (r = 13%, n = 10) | 18,41975 | 20,8143 |
| Giá trị tương lai | 442,07 triệu | 499,54 triệu |

Chênh lệch 499,54 − 442,07 = 57,47 triệu đồng chỉ vì mỗi khoản góp được đưa vào sớm hơn một năm, nên mỗi khoản sinh lãi thêm một năm; kết quả đầu kỳ gấp đúng 1,13 lần kết quả cuối kỳ.

### 9. Dùng Excel tính lãi suất (hàm RATE)

Bài toán ngược: biết số tiền bỏ ra và số tiền nhận về, hỏi lãi suất bình quân là bao nhiêu. Hàm RATE trong Excel giải bài toán này.

Ví dụ: bạn B có sẵn 100 triệu đồng đầu tư vào chứng chỉ quỹ X, và cuối mỗi năm góp thêm 36 triệu. Sau 20 năm, bạn B có 5.600 triệu (5,6 tỷ). Hỏi tỷ suất bình quân năm.

| Tham số | Giá trị | Giải thích |
|---|---|---|
| Nper | 20 | Số năm |
| PMT | −36 | Khoản góp mỗi năm, tiền bỏ ra nên mang dấu âm |
| PV | −100 | Số tiền bỏ ra ở cuối năm 0, dấu âm |
| FV | 5.600 | Số tiền nhận về, dấu dương |
| Type | 0 | Góp cuối kỳ |

Kết quả: **Rate = 15,37%/năm.** Nghĩa là toàn bộ các khoản bỏ ra của bạn B đã sinh lời bình quân 15,37% mỗi năm.

### 10. Nhiều dòng tiền khác nhau: IRR

Khi các khoản tiền ra vào không đều nhau, không dùng được công thức niên kim. Khi đó bài dùng IRR (Internal Rate of Return, tỷ suất hoàn vốn nội bộ): mức lãi suất làm cho tổng giá trị hiện tại của mọi dòng tiền bằng 0.

Ví dụ anh C: cuối năm 2010 mua một căn nhà giá 5 tỷ đồng; cho thuê được 216 triệu/năm; cuối năm 2013 chi 450 triệu nâng cấp nội thất; sau đó cho thuê được 264 triệu/năm; cuối năm 2018 bán nhà được 11 tỷ.

| Năm | Dòng tiền ròng (triệu) | Ghi chú | Chiết khấu về 2010 ở 12,94% (triệu) |
|---|---|---|---|
| 2010 | −5.000 | mua nhà | −5.000,00 |
| 2011 | +216 | tiền thuê | 191,26 |
| 2012 | +216 | tiền thuê | 169,35 |
| 2013 | −234 | 216 thuê − 450 nâng cấp | −162,45 |
| 2014 | +264 | tiền thuê | 162,28 |
| 2015 | +264 | tiền thuê | 143,69 |
| 2016 | +264 | tiền thuê | 127,23 |
| 2017 | +264 | tiền thuê | 112,65 |
| 2018 | +11.264 | 264 thuê + 11.000 bán | 4.255,99 |

Trong Excel: **IRR(−5.000; 216; 216; −234; 264; 264; 264; 264; 11.264) = 12,94%/năm.**

Để kiểm tra, bài chiết khấu từng dòng tiền về năm 2010 ở mức 12,94% (cột cuối của bảng). Tổng các giá trị hiện tại này xấp xỉ bằng 0, chứng tỏ 12,94% đúng là tỷ suất lợi nhuận của phi vụ. Nói cách khác, mua nhà, cho thuê, nâng cấp rồi bán như trên tương đương với gửi tiền ở mức lãi kép 12,94%/năm.

Tóm lại, toàn bộ bài đi theo một mạch: từ công thức một kỳ dựng lên lãi đơn và lãi kép; từ lãi kép dựng lên giá trị hiện tại, giá trị tương lai và chiết khấu; rồi áp dụng cho ba trường hợp thực tế là tăng trưởng không đều (dùng CAGR), góp đều (dùng niên kim, hàm FV và RATE) và dòng tiền bất kỳ (dùng IRR).

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Lãi suất một kỳ (holding period return) | (Cuối kỳ − Đầu kỳ)/Đầu kỳ, kỳ có thể dài ngắn tùy ý |
| Lãi đơn (simple interest) | Lãi không nhập gốc; Tổng = Gốc × (1 + r × n) |
| Lãi kép (compound interest) | Lãi nhập gốc; FV = PV × (1 + r)^n |
| Giá trị hiện tại (present value, PV) | Giá trị ở thời điểm bắt đầu của một khoản tiền tương lai |
| Giá trị tương lai (future value, FV) | Giá trị ở kỳ N của một khoản tiền hiện tại |
| Chiết khấu (discounting) | Quy giá trị tương lai về hiện tại: PV = FV/(1 + r)^n |
| Trung bình cộng (arithmetic mean) | Cộng các tỷ suất rồi chia số năm; sai khi lợi nhuận các năm không đều |
| Bình quân tài chính, CAGR (geometric mean) | (Cuối/Đầu)^(1/n) − 1; tỷ suất đều tương đương |
| Niên kim (annuity) | Dòng tiền bằng nhau mỗi năm; cuối kỳ (Type 0) hoặc đầu kỳ (Type 1) |
| Dòng tiền ra / vào (outflow / inflow) | Tiền bỏ ra mang dấu âm, tiền nhận về mang dấu dương trong Excel |
| RATE | Hàm Excel tìm lãi suất khi biết PV, PMT, FV, số kỳ |
| IRR (tỷ suất hoàn vốn nội bộ) | Lãi suất làm tổng giá trị hiện tại các dòng tiền bằng 0 |

## Câu nói đáng nhớ

> "Lãi ở đây là sự tăng giá của tài sản."

> "Vì tiền có giá trị thời gian nên ta không được cộng tiền ở các thời gian khác nhau, mà chúng ta phải đưa tiền về một mốc thời gian, rồi mới có thể cộng tiền lại được với nhau."

> "Lãi suất trung bình số học (Arithmetic Mean) này không có ý nghĩa lắm, và sẽ cho chúng ta kết quả sai."

## Đánh giá và phát hiện đáng chú ý

### Cấu trúc sư phạm tốt: mọi thứ quy về hai công thức một kỳ
Điểm mạnh của bài là đi từ một kỳ lên nhiều kỳ, từ dòng tiền đơn lên niên kim và IRR, mỗi bước đều có ví dụ kiểm tra lại. Người đọc học được thói quen "tính xong thì thử lại", điều mà nhiều tài liệu phổ thông bỏ qua. Các con số đều đúng: 1,8^(1/5) − 1 = 12,47%; 1,12^9 = 2,77; 5/1,15^8 = 1,63; chuỗi tăng trưởng 2015–2022 cho đúng 148,43 và CAGR 5,80%; hệ số niên kim 18,41975; RATE 15,37%; IRR 12,94%.

### Bài trộn lẫn lãi suất danh nghĩa với tỷ suất tăng giá mà chưa nhắc lạm phát và chi phí
Coi tăng giá đất là "lãi kép" là đúng về mặt toán học, nhưng tỷ suất 12,47%/năm của miếng đất là tỷ suất danh nghĩa, trước thuế, phí chuyển nhượng, chi phí cơ hội và chưa trừ lạm phát. Với đất, còn có rủi ro thanh khoản: giá "trên giấy" 1,8 tỷ chưa phải là tiền nhận được. Người đọc Việt Nam hay so tỷ suất tăng giá đất với lãi tiết kiệm; muốn so công bằng phải trừ các chi phí đó và so ở cùng mức rủi ro.

### Phân biệt trung bình cộng và bình quân hình học là bài học quan trọng nhất
Ví dụ 7,14% so với 5,80% cho thấy rõ: khi có năm lỗ, trung bình cộng luôn phóng đại kết quả thực, vì một năm −20% cần hơn +20% mới bù lại. Đây chính là lý do các quỹ hay quảng cáo "lợi nhuận trung bình" cần được hỏi lại "trung bình gì". Bối cảnh bổ sung: chênh lệch giữa hai loại trung bình xấp xỉ một nửa phương sai của lợi nhuận, nên tài sản càng biến động thì khoảng cách càng lớn.

### IRR mạnh nhưng có giới hạn mà bài chưa nêu
IRR giả định các dòng tiền trung gian được tái đầu tư ở chính mức IRR, và khi dòng tiền đổi dấu nhiều lần (như năm 2013 âm giữa các năm dương) về lý thuyết có thể có nhiều nghiệm. Ví dụ của bài chỉ có một nghiệm nên không sao, nhưng với các khoản như hụi hay đầu tư có nhiều lần góp, rút, người đọc nên kiểm tra thêm bằng NPV ở một lãi suất chiết khấu cho trước. Ví dụ nhà cho thuê cũng bỏ qua thuế cho thuê, chi phí bảo trì, thời gian trống khách, nên 12,94% là cận trên.

### Lỗi đánh số năm ở phần tính tay niên kim dễ gây rối cho người mới
Phần tính tay đặt khoản góp đầu tiên ở "cuối năm 0" rồi gọi kết quả là "cuối năm 10", trong khi theo đúng cách đánh số đó 442,07 triệu là số dư cuối năm 9. Người học tự làm bảng Excel theo lời văn sẽ ra 523,54 triệu ở năm 10 và tưởng mình sai. Cách đúng cho dòng tiền cuối kỳ là: khoản đầu tiên ở cuối năm 1, khoản thứ mười ở cuối năm 10, và số dư cuối năm 10 là 442,07 triệu.

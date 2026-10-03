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

## Dàn ý chi tiết

### 1. Lãi suất một kỳ
- Ví dụ: đầu kỳ 100 đồng, sau 1 kỳ nhận 108 đồng.
- Lãi suất = (108 − 100)/100 = 0,08 = 8%.
- Công thức tổng quát: Lãi suất = (Số tiền cuối kỳ − Số tiền đầu kỳ)/Số tiền đầu kỳ.
- Ngược lại: Số tiền cuối kỳ = Số tiền đầu kỳ × (1 + Lãi suất).
- "Kỳ" có thể là 1 tháng, 1 năm, 3 năm, 5 tháng; nói lãi suất phải nói rõ kỳ. Kỳ thông dụng nhất trong tài chính là năm.
- Hai công thức này là nền tảng để hiểu mọi công thức phức tạp hơn.

### 2. Lãi suất đơn (nhiều kỳ)
- Định nghĩa: tiền lãi hằng năm không được đưa vào gốc để tiếp tục sinh lãi.
- Ví dụ: gốc 100 đồng, 8%/năm, 5 năm. Mỗi năm cuối kỳ có 108 đồng nhưng 8 đồng lãi được rút ra, đầu năm sau gốc vẫn là 100.
- Sau 5 năm: lãi = 8 + 8 + 8 + 8 + 8 = 40 đồng; tổng = 140 đồng.
- Công thức: Tổng số tiền = Gốc × (1 + Lãi suất × Số kỳ) = 100 × (1 + 8% × 5) = 100 × 1,4 = 140 đồng.
- Trong môi trường lãi đơn (lãi không sinh lãi) có thể cộng tiền các năm với nhau. Trong môi trường lãi kép thì không được: muốn cộng phải đưa về cùng một mốc, thường là cuối năm 0 (hiện tại).

### 3. Lãi suất kép (nhiều kỳ)
- Định nghĩa: tiền lãi hằng năm được nhập vào gốc để tiếp tục sinh lãi.
- Ví dụ cùng dữ kiện 100 đồng, 8%, 5 năm:

| Thời điểm | Phép tính | Số tiền (đồng) |
|---|---|---|
| Cuối năm 0 | | 100,00 |
| Cuối năm 1 | 100 × 1,08 | 108,00 |
| Cuối năm 2 | 108 × 1,08 | 116,64 |
| Cuối năm 3 | 116,64 × 1,08 | 125,97 |
| Cuối năm 4 | 125,97 × 1,08 | 136,05 |
| Cuối năm 5 | 136,05 × 1,08 | 146,93 |

- Gộp lại: 100 × (1 + 8%)^5 = 146,93 đồng.
- Công thức tổng quát: Số tiền kỳ n = Số tiền đầu tiên × (1 + Lãi suất)^số kỳ. Hệ số (1 + r)^n làm số tiền tăng theo lũy thừa: lãi suất càng cao, thời gian càng dài thì kết quả càng lớn.
- Ví dụ: 100 triệu, 15%/năm, 30 năm → khoảng 6,6 tỷ (100 × 1,15^30 = 6.621 triệu), cách biệt khoảng 12 lần so với lãi đơn (lãi đơn: 100 × (1 + 15% × 30) = 550 triệu).

### 4. Lãi chính là sự tăng giá của tài sản
- Nhiều người nghĩ vàng, đất, chứng chỉ quỹ không có lãi kép vì không thấy "trả lãi" như tiết kiệm hay trái phiếu. Thực ra lãi ở đây là sự tăng giá, và phần lãi đó nằm lại trong tài sản.
- Ví dụ miếng đất mua 1.000.000.000 đồng, sau 1 năm lên 1.100.000.000 đồng: tỷ suất lợi nhuận = (1,1 tỷ − 1 tỷ)/1 tỷ = 10%/năm.
- Sau 5 năm giá 1.800.000.000 đồng: tỷ suất bình quân năm = (1,8 tỷ/1 tỷ)^(1/5) − 1 = 12,47%/năm.
- Kiểm tra: 1.000.000.000 × (1 + 12,47%)^5 = 1.800.000.000 đồng.
- Vì dùng công thức lãi kép (giả định lãi hằng năm tự nhập gốc) nên đây là lãi kép, dù không thấy lãi "sinh ra".

### 5. Giá trị hiện tại và giá trị tương lai
- Giá trị hiện tại (PV): giá trị của một số tiền ở thời điểm bắt đầu. Giá trị tương lai (FV): giá trị của số tiền đó ở kỳ thứ N.
- FV = PV × (1 + Lãi suất)^số kỳ.
- Với 8%/năm: 100 đồng hôm nay tương đương 108,00 (năm 1), 116,64 (năm 2), 125,97 (năm 3), 136,05 (năm 4), 146,93 (năm 5). Ngược lại 146,93 đồng ở năm 5 có giá trị hiện tại 100 đồng.
- Quy giá trị tương lai về hiện tại gọi là chiết khấu: PV = FV/(1 + Lãi suất)^số kỳ.

### 6. Giá trị thời gian của tiền
- Vì có lãi suất nên tiền sinh ra tiền, giá trị tiền tăng theo thời gian.
- Lãi suất 12%/năm: 1 tỷ hiện nay có giá trị ở năm thứ 9 = 1 × 1,12^9 = 2,77 tỷ.
- Lãi suất 15%/năm: 5 tỷ ở năm thứ 8 có giá trị hiện tại = 5/1,15^8 = 1,63 tỷ.
- Hệ quả: không được cộng tiền ở các thời điểm khác nhau; phải đưa về một mốc rồi mới cộng.

### 7. Tỷ suất lợi nhuận bình quân tài chính (nhiều kỳ không đều)
- Tài sản trị giá 100 triệu năm 2015, tăng trưởng các năm như sau:

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

- Trung bình cộng (arithmetic mean) = (10 + 15 + 16 + 19 − 20 − 15 + 25)/7 = 7,14%. Nếu dùng nó: 100 × 1,0714^7 = 162,08 triệu, khác xa giá trị thật 148,43 triệu → kết quả sai.
- Bình quân tài chính (geometric mean) = (148,43/100)^(1/7) − 1 = 5,80%. Cho 100 triệu tăng đều 5,80%/năm trong 7 năm thì ra đúng 148,43 triệu.
- Bản chất: bình quân hình học coi tài sản tăng đều mỗi năm, chỉ cần điểm đầu (100), điểm cuối (148,43) và số kỳ (7).
- Công thức: TSLNBQ = (Số cuối/Số đầu)^(1/số kỳ) − 1. Tốc độ tăng trưởng kép hằng năm (CAGR) trong kinh tế cũng tính theo cách này.

### 8. Dòng tiền đều hằng kỳ (chuỗi tiền tệ, niên kim)
- Dòng tiền đều phát sinh mỗi kỳ gọi là chuỗi tiền tệ; khi kỳ là năm gọi là dòng niên kim (annuities).
- **8.1 Dòng tiền cuối kỳ.** Bạn A cuối mỗi năm tích lũy 24 triệu, đầu tư vào chứng chỉ quỹ có tỷ suất bình quân 13%/năm. Hỏi số tiền cuối năm thứ 10.
  - Tính tay theo bài: có 24 triệu → sinh lãi 24 × 13% = 3,12 → 27,12; cộng 24 triệu mới → 51,12 triệu. Kỳ sau: 51,12 × 13% = 6,65 → 57,77; cộng 24 → 81,77 triệu. Tiếp tục như vậy: 116,40; 155,53; 199,74; 249,71; 306,17; 369,98; 442,07 triệu.
  - Công thức: FV = PMT × [(1 + r)^n − 1]/r = 24 × [(1,13)^10 − 1]/0,13 = 24 × 18,41975 = 442,07 triệu đồng. Hệ số [(1 + r)^n − 1]/r là hệ số niên kim dòng tiền cuối kỳ.
  - Excel: FV(Rate = 13%, Nper = 10, PMT = −24, PV = 0, Type = 0) = 442,07. PMT âm vì là tiền bỏ ra (outflow); kết quả dương vì là tiền nhận về (inflow); Type = 0 nghĩa là góp cuối kỳ.
- **8.2 Dòng tiền đầu kỳ.** Cùng dữ kiện nhưng góp đầu mỗi năm.
  - Tính tay theo bài: 24 triệu góp đầu kỳ sinh lãi 3,12 → 27,12 cuối kỳ; kỳ sau cộng 24 → 51,12, sinh lãi 6,65 → 57,77; kỳ sau cộng 24 → 81,77, sinh lãi 10,63 → 92,40. Tiếp tục: 131,53; 175,74; 225,71; 282,17; 345,98; 418,07; 499,54 triệu.
  - Công thức: FV = PMT × [(1 + r)^n − 1] × (1 + r)/r = 24 × 20,8143 = 499,54 triệu đồng. Hệ số [(1 + r)^n − 1](1 + r)/r là hệ số niên kim dòng tiền đầu kỳ.
  - Excel: FV(13%, 10, −24, 0, Type = 1) = 499,54.
  - Chênh lệch 499,54 − 442,07 = 57,47 triệu chỉ vì mỗi khoản góp sớm hơn một năm (gấp đúng 1,13 lần).

### 9. Dùng Excel tính lãi suất (hàm RATE)
- Bạn B có sẵn 100 triệu đầu tư vào chứng chỉ quỹ X, cuối mỗi năm góp thêm 36 triệu; sau 20 năm có 5.600 triệu (5,6 tỷ). Hỏi tỷ suất bình quân năm.
- Tham số: Nper = 20; PMT = −36; PV = −100 (tiền bỏ ra ở cuối năm 0); FV = 5.600 (tiền nhận về, dấu dương); Type = 0.
- Kết quả: Rate = 15,37%/năm.

### 10. Nhiều dòng tiền khác nhau: IRR
- IRR (Internal Rate of Return, tỷ suất hoàn vốn nội bộ) là lãi suất làm tổng giá trị hiện tại của mọi dòng tiền bằng 0.
- Ví dụ anh C: cuối 2010 mua nhà 5 tỷ; cho thuê 216 triệu/năm; cuối 2013 chi 450 triệu nâng cấp nội thất; sau đó cho thuê 264 triệu/năm; cuối 2018 bán nhà 11 tỷ.

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

- IRR(−5.000; 216; 216; −234; 264; 264; 264; 264; 11.264) = 12,94%/năm.
- Kiểm tra: tổng giá trị hiện tại các dòng ở mức 12,94% ≈ 0, chứng tỏ 12,94% là tỷ suất đúng của phi vụ.

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

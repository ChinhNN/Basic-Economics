# Vay trả góp: lãi suất thực tế cao hơn bạn nghĩ

**Nguồn:** AI WikiMoney (wikimoney.ai.vn), chuyên mục Đầu tư › Lãi suất / Tỷ suất lợi nhuận, đăng ngày 15/12/2025. https://wikimoney.ai.vn/vay-tra-gop-lai-suat-thuc-te-cao-hon-ban-nghi-3858.html
**Tác giả:** Lâm Minh Chánh.
**Ý chính:** Vay 100 triệu rồi trả góp 10 triệu/tháng trong 12 tháng (tổng 120 triệu) nghe như lãi 20%/năm, nhưng vì bạn trả dần gốc từ tháng đầu nên không được dùng đủ 100 triệu suốt năm, và các khoản trả sớm có giá trị thời gian cao hơn. Tính bằng IRR, lãi thực tế là 2,92%/tháng, tương đương 41,30%/năm, gấp đôi con số quảng cáo. Cần tính kỹ lãi suất thực tế và chỉ vay trả góp khi thực sự cần.

## Sơ đồ

### Cùng tổng 120 triệu, hai mức lãi khác hẳn nhau

```text
          VAY 100 TRIỆU, "LÃI 20%/NĂM"
                       │
        ┌──────────────┴───────────────┐
        ▼                              ▼
  TRẢ CUỐI KỲ                    TRẢ GÓP ĐỀU
  dùng đủ 100tr × 12 tháng       10tr/tháng × 12 = 120tr
  tháng 12 trả 120tr             vốn còn dùng: 100 → 90 → 80 → ...
        │                              │
        ▼                              ▼
  lãi thực 20%/năm               IRR = 2,92%/tháng
                                 (1 + 2,92%)^12 − 1 = 41,30%/năm
```

### Hai cách giải thích

```text
  Cách 1: VỐN THỰC SỰ ĐƯỢC DÙNG          Cách 2: GIÁ TRỊ THỜI GIAN
  trả 10tr ngay tháng 1 → còn            10tr trả ở tháng 1 đáng giá hơn
  dùng ~90tr, rồi 80tr, 70tr...          10tr ở tháng 12 (có thể sinh lời)
  → dư nợ bình quân chỉ ~một nửa         → quy về cuối kỳ, tổng các khoản
  → 20tr lãi trên vốn dùng ít hơn          trả > 120tr
                 └──────────────┬──────────────┘
                                ▼
                 Lãi suất thực tế ≈ gấp đôi lãi quảng cáo
```

## Ba câu hỏi bài viết trả lời

1. Vì sao cùng tổng tiền trả 120 triệu cho khoản vay 100 triệu, trả góp đều lại đắt hơn trả một lần cuối kỳ?
2. Có những cách nào để giải thích trực quan lãi suất thực tế cao hơn của vay trả góp?
3. Tính lãi suất thực tế của khoản trả góp như thế nào?

## Dàn ý chi tiết

### 1. Ví dụ minh họa
- **Vay thông thường (trả gốc và lãi cuối kỳ):** vay 100 triệu, lãi 20%/năm, nhận đủ 100 triệu và dùng trọn 12 tháng; cuối năm trả một lần 100 triệu gốc + 20 triệu lãi = 120 triệu.
- **Vay trả góp (trả đều hằng tháng):** người cho vay đề nghị trả 10 triệu/tháng trong 12 tháng, tổng vẫn 120 triệu. Nghe tiện vì khớp thu nhập tháng và trả nợ nhanh, nhưng lãi thực tế cao hơn.

### 2. Cách giải thích 1: khác biệt về việc sử dụng vốn
- Vay thông thường: dùng toàn bộ 100 triệu suốt 12 tháng, trả cuối kỳ; tối ưu lợi ích từ vốn vay.
- Vay trả góp: nhận 100 triệu nhưng ngay sau tháng đầu đã trả 10 triệu (gồm cả gốc và lãi), nên chỉ còn dùng khoảng 90 triệu; các tháng sau còn 80 triệu, 70 triệu... Không được dùng đủ 100 triệu suốt kỳ → lãi thực tế cao hơn 20% quảng cáo.

### 3. Cách giải thích 2: giá trị thời gian của tiền
- Tiền hôm nay giá trị hơn tiền tương lai vì lạm phát và cơ hội đầu tư. Ví dụ: cho vay 10 triệu và chỉ nhận lại đúng 10 triệu sau 12 tháng thì ít ai chấp nhận, trừ người thân.
- Mỗi khoản 10 triệu trả góp có giá trị khác nhau khi quy về cùng thời điểm (ví dụ tháng 12): 10 triệu ở tháng 1 đáng giá hơn 10 triệu ở tháng 12 vì có thể đầu tư sinh lời ngay. Do đó tổng giá trị các khoản trả quy về cuối kỳ lớn hơn 120 triệu → lãi thực tế cao hơn.

### 4. Tính lãi suất thực tế bằng IRR
- Dòng tiền theo tháng: tháng 0 nhận +100 triệu; tháng 1 đến tháng 12 mỗi tháng trả −10 triệu.
- IRR (hàm Excel hoặc công cụ tài chính) → lãi suất tháng = 2,92%.
- Lãi suất năm = (1 + 2,92%)^12 − 1 = 41,30%.
- Kết luận: lãi vay trả góp cao hơn ta tưởng; cần thận trọng, tính kỹ lãi thực tế, đánh giá khả năng trả nợ, chỉ vay khi thực sự cần.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Vay trả cuối kỳ (bullet loan) | Dùng trọn vốn suốt kỳ, trả gốc và lãi một lần cuối kỳ |
| Vay trả góp (installment loan) | Trả đều hằng tháng gồm cả gốc và lãi |
| Lãi suất quảng cáo | Con số lãi tính trên số tiền vay ban đầu, ở đây 20%/năm |
| Lãi suất thực tế (effective rate) | Lãi suất tính theo dòng tiền thật, ở đây 41,30%/năm |
| Lãi phẳng (flat rate) | Lãi tính trên gốc ban đầu suốt kỳ dù gốc đã trả dần; cách tính ẩn trong ví dụ |
| Dư nợ giảm dần (declining balance) | Lãi tính trên phần gốc còn nợ, cách tính chuẩn |
| Giá trị thời gian của tiền | Tiền nhận hoặc trả sớm có giá trị cao hơn tiền muộn |
| IRR (tỷ suất hoàn vốn nội bộ) | Lãi suất làm tổng giá trị hiện tại của dòng tiền vay và trả bằng 0 |

## Câu nói đáng nhớ

> "Kết quả là bạn không được sử dụng đầy đủ 100 triệu đồng trong toàn bộ thời gian, dẫn đến lãi suất thực tế cao hơn so với mức 20% được quảng cáo."

> "10 triệu đồng ở tháng 1 đáng giá hơn 10 triệu đồng ở tháng 12 vì nó có thể được đầu tư để sinh lời ngay."

> "Hãy tính toán kỹ lãi suất thực tế, đánh giá khả năng trả nợ và chỉ vay khi thực sự cần thiết."

## Đánh giá và phát hiện đáng chú ý

### Con số đúng, và đây chính là bẫy "lãi phẳng" phổ biến ở Việt Nam
Tính lại: dòng tiền +100, rồi −10 mỗi tháng trong 12 tháng cho IRR 2,923%/tháng, quy năm (1,02923)^12 − 1 ≈ 41,3%. Bài không gọi tên, nhưng cơ chế này chính là "lãi phẳng" (flat rate): tính 20% trên toàn bộ 100 triệu ban đầu trong khi dư nợ giảm dần. Nhiều công ty tài chính tiêu dùng, cửa hàng điện máy, gói trả góp xe máy quảng cáo lãi phẳng mỗi tháng (ví dụ 1,5–2%/tháng) mà người vay hiểu nhầm là lãi trên dư nợ giảm dần. Quy tắc nhẩm: lãi thực tế theo dư nợ giảm dần xấp xỉ gần gấp đôi lãi phẳng.

### Cách giải thích 1 nên kèm con số dư nợ bình quân để chặt chẽ hơn
Dư nợ bình quân của khoản trả góp chỉ khoảng 57 triệu chứ không phải 100 triệu (gốc giảm dần từ 100 về 0). Trả 20 triệu lãi trên dư nợ bình quân khoảng 57 triệu tương ứng 20/57 ≈ 35%/năm, đúng bằng 2,92% × 12; quy theo lãi kép tháng thì thành khoảng 41%. Bài nói đúng hướng nhưng chỉ dừng ở mô tả 90, 80, 70 triệu.

### Cách giải thích 2 hơi lẫn giữa góc nhìn người cho vay và người vay
Bài nói tổng các khoản trả "quy về cuối kỳ sẽ lớn hơn 120 triệu". Điều đó đúng với bất kỳ lãi suất chiết khấu dương nào, nhưng không trực tiếp chứng minh lãi thực tế là 41%; chỉ IRR mới cho con số chính xác. Lời giải thích nên được hiểu là trực giác, còn phép tính IRR mới là bằng chứng.

### So sánh 41% với 20% cần cùng cơ sở quy đổi
Con số 41,30% là lãi năm hiệu dụng (lãi kép tháng). Nếu quy theo kiểu ngân hàng hay công bố (lãi tháng × 12) thì là 2,92% × 12 = 35,1%/năm. Cả hai đều cao hơn hẳn 20%, nhưng khi so với lãi vay ngân hàng công bố theo năm, người đọc nên dùng cùng một quy ước. Bối cảnh bổ sung: pháp luật Việt Nam yêu cầu tổ chức tín dụng công bố lãi suất cho vay theo tỷ lệ phần trăm/năm trên dư nợ, nên khi được báo lãi "theo tháng" hay "phẳng" thì cần hỏi lại cách tính.

### Hàm ý thực hành
Trước khi ký hợp đồng trả góp, chỉ cần ba con số: số tiền nhận được thực tế (trừ phí, bảo hiểm khoản vay bắt buộc), số tiền trả mỗi kỳ và số kỳ. Dùng hàm RATE hoặc IRR trong Excel là ra lãi thực tế. Các khoản phí trả trước và bảo hiểm khoản vay làm giảm số tiền nhận được và còn đẩy lãi thực tế cao hơn mức 41% của ví dụ.

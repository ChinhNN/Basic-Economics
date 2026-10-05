# Làm sao để đo lường và quản trị rủi ro khi đầu tư chứng khoán?

**Nguồn:** AI WikiMoney (wikimoney.ai.vn), chuyên mục Đầu tư › Rủi ro trong đầu tư, đăng ngày 4/7/2025. https://wikimoney.ai.vn/lam-sao-de-do-luong-va-quan-tri-rui-ro-khi-dau-tu-chung-khoan-3813.html
**Tác giả:** WikiMoney Team.
**Ý chính:** Lợi nhuận luôn đi cùng rủi ro và "không đo lường thì không kiểm soát được". Bài giới thiệu ba thước đo phổ biến (Beta cho độ nhạy với thị trường, VaR cho mức lỗ ở một độ tin cậy, độ lệch chuẩn cho độ dao động lợi nhuận) và bốn chiến lược quản trị cho nhà đầu tư cá nhân: đa dạng hoá, ngưỡng cắt lỗ và chốt lời, giới hạn tỷ trọng và đòn bẩy, phòng ngừa bằng phái sinh. Kết luận: đầu tư thông minh là sống chung với rủi ro một cách chủ động, có kiểm soát.

> **Lưu ý:** Ở mục Beta, bài viết "Công thức toán học của Beta là:" nhưng bản văn bản không có công thức đi kèm (có thể là ảnh bị mất khi in). Tổng hợp ghi công thức chuẩn của Beta thay thế. Ngoài ra bài lấy "Điện lực EVN" làm ví dụ cổ phiếu Beta thấp, trong khi Tập đoàn Điện lực Việt Nam (EVN) là doanh nghiệp nhà nước chưa niêm yết; ví dụ chỉ nên hiểu là nhóm cổ phiếu ngành điện, tiện ích.

## Sơ đồ

### Từ đo lường đến quản trị

```text
            NGUỒN RỦI RO CHỨNG KHOÁN
   biến động thị trường │ vĩ mô (lạm phát, lãi suất)
   sự kiện bất ngờ      │ sai lầm cá nhân
                        │
                        ▼
            ĐO LƯỜNG ("không đo – không kiểm soát")
   ┌────────────────┬────────────────┬────────────────┐
   ▼                ▼                ▼
  BETA             VaR              ĐỘ LỆCH CHUẨN
  độ nhạy với      lỗ tối đa ở      dao động quanh
  VN-Index         độ tin cậy X%    lợi nhuận TB
  (rủi ro hệ       VaR 1 ngày 95%   A: 10% ± 15%
  thống)           = 10 tr          B: 10% ± 5% → B an toàn hơn
   └────────────────┴────────┬───────┴────────────────┘
                             ▼
                        QUẢN TRỊ
   ┌──────────────┬──────────────┬──────────────┬──────────────┐
   ▼              ▼              ▼              ▼
  ĐA DẠNG HOÁ   CẮT LỖ/CHỐT   TỶ TRỌNG &     HEDGING
  tài sản,      LỜI           ĐÒN BẨY        put options,
  ngành, khu    lời 15% bán   1 mã ≤10–20%   futures
  vực (giảm     bớt; lỗ       tiền mặt       (cho người có
  phi hệ thống) 8–10% thoát   10–20%, hạn    kinh nghiệm)
                              chế margin
                             │
                             ▼
       KHẨU VỊ RỦI RO + RÀ SOÁT ĐỊNH KỲ + HỌC LIÊN TỤC
```

## Ba câu hỏi bài viết trả lời

1. Vì sao nhà đầu tư chứng khoán phải đo lường rủi ro trước khi nói đến quản trị rủi ro?
2. Beta, VaR và độ lệch chuẩn đo cái gì, đọc như thế nào và có hạn chế gì?
3. Nhà đầu tư cá nhân có thể áp dụng những chiến lược quản trị rủi ro cụ thể nào (với những ngưỡng con số nào)?

## Khái niệm cần biết

**Rủi ro trong đầu tư chứng khoán.** Khả năng mất tiền hoặc không đạt được mục tiêu tài chính đã đặt ra. Ví dụ minh hoạ: bạn đặt mục tiêu lãi 10% một năm, cuối năm danh mục chỉ lãi 2%; dù không lỗ, bạn vẫn đã gặp rủi ro theo định nghĩa này. Cả bài xoay quanh việc biến khái niệm mơ hồ này thành những con số đo được.

**Rủi ro hệ thống và rủi ro phi hệ thống (systematic and unsystematic risk).** Rủi ro hệ thống là rủi ro chung của cả thị trường, như lạm phát hay lãi suất tăng, không tránh được bằng cách mua nhiều mã. Rủi ro phi hệ thống là rủi ro riêng của một công ty hay một ngành, giảm được bằng đa dạng hoá. Ví dụ minh hoạ: lãi suất tăng làm hầu hết cổ phiếu giảm (hệ thống); một công ty bị phát hiện sai phạm làm riêng mã đó giảm (phi hệ thống). Bài cần phân biệt hai loại này vì Beta đo loại thứ nhất, còn đa dạng hoá chỉ chống được loại thứ hai.

**Beta.** Con số cho biết một cổ phiếu thường biến động mạnh hay yếu hơn thị trường chung. Ví dụ trong bài: cổ phiếu A có Beta 1,5, nên khi VN-Index tăng 1% thì A có thể tăng 1,5%, và khi thị trường giảm 1% thì A có thể giảm 1,5%. Beta giúp người đầu tư biết mình đang chịu bao nhiêu rủi ro của thị trường.

**Phương sai và hiệp phương sai (variance, covariance).** Phương sai đo mức một chuỗi số dao động quanh giá trị trung bình của nó; hiệp phương sai đo mức hai chuỗi số cùng dao động với nhau. Ví dụ minh hoạ: nếu tháng nào thị trường tăng thì cổ phiếu cũng tăng, hiệp phương sai giữa hai chuỗi lợi nhuận là dương. Hai đại lượng này là nguyên liệu của công thức Beta và của một cách tính VaR.

**VaR (Value at Risk).** Mức lỗ mà danh mục sẽ không vượt quá trong một khoảng thời gian, với một độ tin cậy cho trước. Ví dụ trong bài: VaR 1 ngày bằng 10 triệu đồng ở độ tin cậy 95% nghĩa là trong 95% số ngày, danh mục không lỗ quá 10 triệu; còn 5% số ngày có thể lỗ nhiều hơn. VaR là thước đo thứ hai bài giới thiệu, dùng để đặt giới hạn lỗ chấp nhận được.

**Độ lệch chuẩn (standard deviation).** Mức lợi nhuận thực tế thường lệch khỏi lợi nhuận trung bình bao nhiêu. Ví dụ trong bài: hai cổ phiếu cùng lãi trung bình 10% một năm, nhưng A có độ lệch chuẩn 15%, B chỉ 5%; B ổn định hơn nên ít rủi ro hơn. Đây là thước đo thứ ba, hữu ích nhất khi so các tài sản có cùng lợi nhuận kỳ vọng.

**Đòn bẩy, giao dịch ký quỹ (margin).** Vay tiền công ty chứng khoán để mua thêm cổ phiếu. Ví dụ minh hoạ: có 100 triệu, vay thêm 100 triệu để mua 200 triệu cổ phiếu; cổ phiếu giảm 10% thì mất 20 triệu, tức 20% vốn tự có. Bài khuyên hạn chế margin vì nó khuếch đại cả lời lẫn lỗ.

**Phòng ngừa rủi ro (hedging) và quyền chọn bán (put option).** Hedging là mua một công cụ tài chính có lãi khi danh mục lỗ, để bù đắp. Quyền chọn bán là hợp đồng cho người mua quyền (không bắt buộc) bán tài sản ở một mức giá định trước. Ví dụ minh hoạ: mua quyền bán một chỉ số ở mức 1.000 điểm; chỉ số rơi xuống 900 điểm thì quyền chọn có lãi, bù cho phần cổ phiếu bị giảm giá. Bài xếp đây là chiến lược nâng cao, chỉ hợp người có kinh nghiệm.

## Nội dung chi tiết

### 1. Vì sao cần đo lường và quản trị rủi ro

Bài mở đầu bằng nhận định rằng không khoản đầu tư nào hoàn toàn an toàn. Ngay cả cổ phiếu bluechip của các công ty lớn hay trái phiếu chính phủ cũng có lúc biến động giá. Lợi nhuận không bao giờ đi một mình mà luôn song hành cùng rủi ro.

Rủi ro trong đầu tư chứng khoán được định nghĩa là khả năng mất tiền hoặc không đạt được mục tiêu tài chính đã đề ra. Bài liệt kê bốn nguồn gốc của rủi ro:

| Nguồn rủi ro | Ví dụ trong bài |
|---|---|
| Biến động thị trường | Cung cầu, tin tức kinh tế, tâm lý đám đông |
| Thay đổi vĩ mô | Lạm phát, lãi suất, chính sách tiền tệ |
| Sự kiện bất ngờ | Khủng hoảng chính trị, thiên tai, báo cáo tài chính không đạt kỳ vọng |
| Sai lầm cá nhân | Quyết định theo cảm xúc, thiếu thông tin, không có kế hoạch |

Rủi ro không thể loại bỏ hoàn toàn. Nhưng nếu đo lường và quản trị tốt, người đầu tư giới hạn được tác động tiêu cực và còn biến rủi ro thành công cụ định hướng chiến lược.

Nguyên tắc nền tảng của bài là câu "bạn không thể kiểm soát thứ mà bạn không thể đo lường". Người không biết mình đang chịu mức rủi ro nào dễ mắc ba sai lầm: đầu tư quá nhiều vào tài sản không phù hợp với mình; chọn sai cổ phiếu vì không hiểu cổ phiếu đó nhạy với thị trường đến đâu; và hoảng loạn bán tháo khi giá giảm. Ngược lại, khi đo được mức biến động, khả năng thua lỗ tối đa và độ nhạy với thị trường, người đầu tư có thể chọn cổ phiếu hợp với khẩu vị rủi ro của mình, phân bổ vốn cân bằng giữa lợi nhuận và rủi ro, xây dựng chiến lược quản lý vốn và đặt kỳ vọng lợi nhuận thực tế. Bài dẫn Investopedia để nhấn mạnh rằng quản trị rủi ro là yếu tố then chốt giúp tránh những thất bại lớn như khủng hoảng 2008.

### 2. Chỉ số Beta: độ biến động so với thị trường

Beta đo mức biến động của một cổ phiếu so với thị trường chung. Ở Việt Nam thị trường chung thường được đại diện bằng VN-Index, ở Mỹ bằng chỉ số S&P 500. Beta là công cụ đánh giá rủi ro hệ thống, tức loại rủi ro không loại bỏ được bằng đa dạng hoá.

Cách đọc Beta:

| Giá trị | Ý nghĩa | Ví dụ trong bài |
|---|---|---|
| Beta = 1 | Biến động ngang thị trường | |
| Beta > 1 | Biến động mạnh hơn thị trường, rủi ro cao hơn | Cổ phiếu công nghệ như Tesla |
| Beta < 1 | Ổn định hơn thị trường, rủi ro thấp hơn | Cổ phiếu tiện ích như ngành điện |

Ví dụ: cổ phiếu A có Beta = 1,5. Khi VN-Index tăng 1%, A có thể tăng 1,5%; khi thị trường giảm 1%, A có thể giảm 1,5%. A "nhạy cảm" hơn thị trường, nên hợp với nhà đầu tư ưa mạo hiểm, chịu được các nhịp lên xuống mạnh.

Công thức chuẩn của Beta (bản trích của bài bị thiếu phần công thức, nên ghi bổ sung ở đây): Beta = Cov(R cổ phiếu, R thị trường) / Var(R thị trường). Nói bằng lời, đó là hiệp phương sai giữa lợi nhuận cổ phiếu và lợi nhuận thị trường, chia cho phương sai lợi nhuận thị trường. Tử số cho biết cổ phiếu đi cùng thị trường đến mức nào, mẫu số quy đổi về đơn vị biến động của thị trường.

Người đầu tư cá nhân không cần tự tính, vì Beta có sẵn trên các nền tảng tài chính. Bài cũng lưu ý Beta chỉ mang tính tương đối, nên dùng cùng các chỉ số khác.

### 3. VaR: giá trị rủi ro tiềm ẩn của danh mục

VaR (Value at Risk) dự đoán mức lỗ tối đa của danh mục trong một khoảng thời gian, với một mức tin cậy nhất định (gọi chung là X%). Nó trả lời câu hỏi: "trong điều kiện bình thường, tôi có thể lỗ bao nhiêu, với xác suất bao nhiêu?".

Ví dụ của bài: VaR 1 ngày bằng 10 triệu đồng với độ tin cậy 95%. Điều này có nghĩa là trong 95% trường hợp, danh mục sẽ không lỗ quá 10 triệu trong 1 ngày. Nhưng vẫn còn 5% khả năng lỗ vượt mức đó, nhất là khi thị trường biến động bất thường. Nói cách khác, cứ khoảng 20 ngày giao dịch thì có thể có một ngày lỗ nhiều hơn 10 triệu, và VaR không nói ngày đó lỗ bao nhiêu.

Lợi ích của VaR theo bài: giúp xác định giới hạn rủi ro chấp nhận được; giúp lập kế hoạch phân bổ vốn và đặt điểm dừng lỗ; và giúp đánh giá hiệu quả quản lý danh mục.

Có ba phương pháp tính VaR:

| Phương pháp | Cách làm |
|---|---|
| Lịch sử | Xếp hạng các mức lỗ trong dữ liệu quá khứ, lấy mức ở ngưỡng tin cậy cần tìm |
| Phương sai – hiệp phương sai | Dùng độ lệch chuẩn và tương quan giữa các tài sản để tính |
| Monte Carlo | Mô phỏng hàng nghìn kịch bản lợi nhuận ngẫu nhiên rồi xem phân phối lỗ lãi |

Hạn chế lớn của VaR là không dự đoán được các sự kiện cực đoan như khủng hoảng 2008, vì nó được xây cho "điều kiện bình thường". Do đó cần kết hợp VaR với công cụ khác.

### 4. Độ lệch chuẩn: sự ổn định của lợi nhuận

Độ lệch chuẩn đo mức dao động của lợi nhuận quanh giá trị trung bình, tức lợi nhuận thực tế thường lệch khỏi kỳ vọng bao nhiêu. Độ lệch chuẩn cao nghĩa là biến động lớn và rủi ro cao; độ lệch chuẩn thấp nghĩa là biến động nhỏ và rủi ro thấp.

Ví dụ của bài:

| Cổ phiếu | Lợi nhuận trung bình/năm | Độ lệch chuẩn |
|---|---|---|
| A | 10% | 15% |
| B | 10% | 5% |

Hai cổ phiếu có cùng lợi nhuận trung bình 10% một năm. Nhưng lợi nhuận của A thường dao động trong khoảng 10% ± 15%, tức có năm lỗ 5%, có năm lãi 25%; còn B thường dao động trong khoảng 10% ± 5%, tức từ 5% đến 15%. Vì vậy B có rủi ro thấp hơn do ổn định hơn, còn A biến động lớn và hợp với người ưa mạo hiểm. Độ lệch chuẩn đặc biệt hữu ích khi cần chọn giữa các tài sản có cùng lợi nhuận kỳ vọng: khi đó nên chọn tài sản dao động ít hơn.

### 5. Chiến lược quản trị rủi ro cho nhà đầu tư cá nhân

Sau khi đo, bài đưa ra bốn chiến lược quản trị, đánh số từ 5.1 đến 5.4.

**5.1 Đa dạng hoá ("không bỏ trứng vào một giỏ").** Mục đích là giảm rủi ro phi hệ thống, tức rủi ro đến từ từng công ty hay từng ngành. Có ba hướng phân bổ:

- theo loại tài sản: cổ phiếu, trái phiếu, vàng, bất động sản, tiền mặt;
- theo ngành: ngân hàng, công nghệ, tiêu dùng, năng lượng;
- theo khu vực: trong nước và quốc tế.

Ví dụ: danh mục 50% cổ phiếu và 50% trái phiếu. Khi chứng khoán giảm, trái phiếu có thể tăng hoặc giữ giá, giúp cân bằng danh mục. Bài lưu ý đa dạng hoá không loại bỏ được rủi ro hệ thống.

**5.2 Đặt ngưỡng cắt lỗ và chốt lời rõ ràng**, nhất là khi lướt sóng ngắn hạn. Chốt lời: ví dụ khi lời 15% thì bán một phần để bảo vệ thành quả. Cắt lỗ: ví dụ khi lỗ 8–10% thì thoát vị thế. Nên dùng lệnh dừng lỗ (stop-loss) để hệ thống tự động bán khi giá chạm ngưỡng, tránh để cảm xúc chi phối quyết định.

**5.3 Quản lý tỷ lệ đầu tư và vốn.** Ba quy tắc:

| Quy tắc | Ngưỡng |
|---|---|
| Tỷ trọng tối đa của một cổ phiếu | Không quá 10–20% danh mục, dù tin tưởng đến đâu |
| Tiền mặt dự phòng | Giữ 10–20% để phòng rủi ro hoặc tận dụng cơ hội |
| Đòn bẩy (margin) | Hạn chế, nhất là với người mới, vì khuếch đại cả lời lẫn lỗ |

**5.4 Phòng ngừa rủi ro (hedging).** Dùng sản phẩm phái sinh như quyền chọn (options) và hợp đồng tương lai (futures) để bảo vệ danh mục, ví dụ mua quyền chọn bán (put options) để có lãi khi giá giảm, bù cho phần lỗ của cổ phiếu. Cách này đòi hỏi kiến thức sâu và chỉ phù hợp với người có kinh nghiệm.

### 6. Lời khuyên thực tế

Bài kết thúc phần hướng dẫn bằng ba lời khuyên.

**Hiểu khẩu vị rủi ro của mình.** Hãy tự hỏi: mình sẵn sàng lỗ bao nhiêu phần trăm mà vẫn ngủ ngon? Mục tiêu là tăng trưởng nhanh hay bảo toàn vốn? Nếu thấy lo lắng khi tài khoản giảm 5–10%, nên ưu tiên cổ phiếu ổn định (Beta < 1), cổ phiếu trả cổ tức đều, hoặc quỹ mở, thay vì lướt sóng.

**Rà soát định kỳ** hàng tháng hoặc hàng quý: tỷ trọng các khoản còn hợp lý không, mã nào kém cần thay, mã nào tăng mạnh nên chốt lời. Việc tái cân bằng giúp giữ chiến lược đi đúng hướng.

**Học liên tục:** đọc sách như "The Intelligent Investor" của Benjamin Graham, theo dõi nguồn tin tài chính uy tín, và học từ kinh nghiệm của các nhà đầu tư thành công.

### 7. Kết luận

Rủi ro là không tránh được, nhưng điều đó không có nghĩa là phải mù mờ hay phó mặc. Khi đo rủi ro bằng Beta, VaR và độ lệch chuẩn, rồi áp dụng chiến lược quản trị phù hợp, rủi ro trở thành công cụ định hướng thay vì nỗi sợ. Theo bài, đầu tư thông minh không phải là tránh rủi ro hoàn toàn mà là sống chung với rủi ro một cách chủ động, có kiểm soát và hợp lý; điều đó cần kiến thức, kỷ luật và sự chuẩn bị kỹ.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Beta | Độ nhạy của lợi nhuận cổ phiếu với thị trường; Beta 1,5 nghĩa là thị trường đi 1% thì cổ phiếu đi khoảng 1,5% |
| Rủi ro hệ thống (systematic risk) | Rủi ro chung của toàn thị trường, không đa dạng hoá được, được Beta đo |
| Rủi ro phi hệ thống (unsystematic risk) | Rủi ro riêng của công ty, ngành, giảm được nhờ đa dạng hoá |
| VaR (Value at Risk) | Mức lỗ không bị vượt quá trong một kỳ ở một độ tin cậy (ví dụ 95%) |
| Độ lệch chuẩn (standard deviation) | Mức dao động trung bình của lợi nhuận quanh giá trị trung bình |
| Mô phỏng Monte Carlo | Tạo hàng nghìn kịch bản ngẫu nhiên để ước tính phân phối lỗ lãi |
| Lệnh dừng lỗ (stop-loss) | Lệnh tự động bán khi giá chạm ngưỡng định trước |
| Margin (giao dịch ký quỹ) | Vay công ty chứng khoán để mua thêm cổ phiếu, khuếch đại lời lẫn lỗ |
| Hedging (phòng ngừa rủi ro) | Dùng phái sinh như put options, futures để bù đắp thua lỗ của danh mục |
| Khẩu vị rủi ro (risk appetite) | Mức thua lỗ một người chịu được về tài chính và tâm lý |
| Tái cân bằng (rebalancing) | Đưa tỷ trọng danh mục về mức mục tiêu định kỳ |

## Câu nói đáng nhớ

> "Bạn không thể kiểm soát thứ mà bạn không thể đo lường"

> "Lợi nhuận không bao giờ đi một mình—nó luôn song hành cùng rủi ro."

> "Đầu tư thông minh không phải là tránh rủi ro hoàn toàn, mà là sống chung với rủi ro một cách chủ động, có kiểm soát và hợp lý."

## Đánh giá và phát hiện đáng chú ý

### VaR bị gọi là "lỗ tối đa", một cách diễn đạt dễ gây hiểu lầm nguy hiểm
Bài định nghĩa VaR là "mức lỗ tối đa", rồi ngay sau đó thừa nhận vẫn có 5% khả năng lỗ vượt mức. Đúng ra VaR là một ngưỡng phân vị: mức lỗ chỉ bị vượt trong X% số trường hợp, và nó không nói gì về việc khi vượt thì lỗ bao nhiêu. Chính điểm mù này khiến VaR thất bại năm 2008. Thước đo bổ sung chuẩn là Expected Shortfall (lỗ kỳ vọng trong những ngày tệ nhất vượt ngưỡng VaR), cùng với kiểm tra sức chịu đựng (stress test). Người đọc nên nhớ: VaR là "ngày xấu bình thường", không phải "ngày tệ nhất".

### Beta và độ lệch chuẩn đo hai thứ khác nhau, bài chưa làm rõ quan hệ
Beta chỉ đo phần rủi ro gắn với thị trường, còn độ lệch chuẩn đo tổng biến động gồm cả rủi ro riêng của doanh nghiệp. Một cổ phiếu có thể Beta thấp nhưng độ lệch chuẩn rất cao (ví dụ cổ phiếu nhỏ chịu tin riêng như vụ PNJ được phân tích ở một bài khác cùng chuyên mục). Vì vậy lời khuyên "dễ lo lắng thì chọn Beta < 1" chưa đủ: Beta thấp không bảo vệ trước cú sốc riêng của công ty. Ngoài ra Beta ước tính từ dữ liệu quá khứ, thay đổi theo giai đoạn và kém tin cậy với cổ phiếu thanh khoản thấp, điều rất phổ biến trên HOSE, HNX, UPCoM.

### Ví dụ cổ phiếu – trái phiếu 50/50 dựa trên giả định tương quan âm không phải lúc nào cũng đúng
Bài nói khi chứng khoán giảm, trái phiếu có thể tăng hoặc giữ giá. Điều này thường đúng khi cú sốc là suy thoái và lãi suất giảm, nhưng sai khi cú sốc là lạm phát và lãi suất tăng; bối cảnh bổ sung là năm 2022 cổ phiếu và trái phiếu ở nhiều thị trường cùng giảm mạnh. Ở Việt Nam, nhà đầu tư cá nhân còn khó tiếp cận trái phiếu chính phủ, và trái phiếu doanh nghiệp từng là nguồn rủi ro chứ không phải chỗ trú ẩn. Bài "Vàng và cổ phiếu cùng giảm" cùng chuyên mục bàn kỹ hơn về vấn đề tương quan này.

### Các ngưỡng con số hữu ích nhưng nên hiểu là quy tắc ngón tay cái
Cắt lỗ 8–10%, chốt lời 15%, mỗi mã tối đa 10–20%, tiền mặt 10–20% là những mốc thực hành tốt cho người mới, nhưng không có cơ sở lý thuyết cố định. Ví dụ ngưỡng cắt lỗ nên gắn với độ biến động của từng cổ phiếu: với mã dao động 7% mỗi phiên như biên độ HOSE, cắt lỗ 8% có thể bị kích hoạt bởi nhiễu thông thường. Riêng hedging bằng put options hiện khó áp dụng cho nhà đầu tư cá nhân Việt Nam vì thị trường phái sinh trong nước chủ yếu là hợp đồng tương lai chỉ số và trái phiếu chính phủ, chưa có quyền chọn cổ phiếu niêm yết rộng rãi.

### Bài thiếu thước đo quan trọng nhất với người mới: mức sụt giảm tối đa
Với nhà đầu tư cá nhân, câu hỏi "ngủ ngon" thực chất là câu hỏi về mức sụt giảm từ đỉnh xuống đáy (maximum drawdown), vốn dễ hiểu hơn Beta hay VaR. Một danh mục thuần cổ phiếu Việt Nam có thể mất một nửa giá trị trong các giai đoạn như 2008 hay 2022, và biết trước điều này giúp đặt tỷ trọng cổ phiếu phù hợp hơn mọi chỉ số kỹ thuật.

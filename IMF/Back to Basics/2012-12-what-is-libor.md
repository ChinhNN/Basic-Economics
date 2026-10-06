# What Is LIBOR? — LIBOR là gì?

**Nguồn:** IMF *Finance & Development*, Back to Basics, tháng 12/2012, tr. 32–33.
**Tác giả:** John Kiff, chuyên gia cao cấp khu vực tài chính, Vụ Tiền tệ và Thị trường vốn của IMF.
**Ý chính:** LIBOR là lãi suất trung bình mà các ngân hàng lớn *tin* mình có thể vay lẫn nhau ở London, làm chuẩn cho 300 nghìn tỷ USD hợp đồng tài chính. Vì dựa trên ước đoán chứ không phải giao dịch thật, LIBOR bị gọi là "hư cấu tiện lợi", bị Barclays thao túng, và đang được Anh cải cách.

> **Lưu ý:** bài nói việc bỏ 5 đồng tiền và 4 kỳ hạn sẽ giảm số lãi suất LIBOR từ 150 xuống 20, nhưng phép tính không khớp: 10 đồng tiền × 15 kỳ hạn = 150, còn 5 đồng tiền × 11 kỳ hạn còn lại = 55 chứ không phải 20. Có thể bài gốc tóm lược thiếu một bước cắt giảm khác; chưa có tài liệu gốc để đối chiếu nên giữ nguyên số của bài.

## Sơ đồ

### LIBOR được tạo ra thế nào

```text
       MỖI NGÀY ~11h SÁNG: 18 NH lớn (dưới Hiệp hội NH Anh) báo
       lãi suất họ TIN có thể vay "lượng hợp lý" USD từ nhau trên
       thị trường liên NH London · 15 kỳ hạn (qua đêm → 1 năm)
       → Thomson Reuters gom, BỎ 4 CAO NHẤT + 4 THẤP NHẤT, lấy
       trung bình phần còn lại → công bố
       · làm cho 10 đồng tiền (panel 6–16 NH) → 150 lãi suất
                                │
                                ▼
       QUAN TRỌNG KHÔNG PHẢI VÌ NH giao dịch ở mức đó (dù có thể)
       mà vì là CHUẨN cho lãi suất khác: 300 nghìn tỷ USD hợp đồng
       (Bộ Tài chính Anh) + hàng chục tỷ thế chấp lãi suất thả nổi,
       vay tiêu dùng · USD LIBOR dùng nhiều nhất
                                │
                                ▼
       LỊCH SỬ: ý tưởng mới · gốc từ bùng nổ hợp đồng tương lai
       phòng hộ lãi suất đầu 1980 → cần chuẩn để thanh toán →
       BBA ra LIBOR 1986 (3 đồng: USD, yên, bảng) · chuẩn định giá
       vay DN lãi thả nổi · trùng với FRA, hoán đổi lãi suất
                                │
                                ▼
       VẤN ĐỀ LÂU NAY: phương pháp có lỗi, méo khi thị trường
       căng thẳng (NH ngừng cho vay nhau ở kỳ hạn dài)
       · "HƯ CẤU TIỆN LỢI": NH cho nhau vay ≤1 tuần → LIBOR kỳ
         hạn dài là ƯỚC ĐOÁN · nhưng ~95% giao dịch tham chiếu kỳ
         hạn ≥3 tháng (3 tháng USD phổ biến nhất) · ICAP ngừng
         công bố NYFR vì thiếu dữ liệu → cho vay không bảo đảm
         kỳ hạn dài gần như là hư cấu
```

### Bê bối và cải cách

```text
       BARCLAYS 6/2012: nộp phạt ~450 triệu USD (Anh + Mỹ) vì
       thao túng LIBOR · NH khác đang bị điều tra, phạt và kiện
       có thể gần 50 tỷ USD
                                │
                                ▼
       NHÌN CHUNG LIBOR KHÁ CHÍNH XÁC, bám sát chuẩn dựa giao dịch
       thật (thương phiếu) · NGOẠI LỆ RÕ: sau Lehman 9/2008,
       LIBOR 3 tháng USD THẤP HƠN HẲN Eurodollar và NYFR
                                │
                                ▼
       VÌ SAO THẤP? quy tắc BBA công bố NGAY báo cáo từng NH (để
       buộc trung thực) → 2007–08 PHẢN TÁC DỤNG: NH không muốn lộ
       khó khăn vốn → báo THẤP HƠN thực để che vấn đề thanh khoản
       · nghiên cứu: NH "báo thấp" sau Bear Stearns 3/2008 và
         Lehman · bằng chứng thông đồng: không kết luận được
                                │
                                ▼
       BỎ LIBOR? quá quan trọng, phổ biến → CỨU thay vì bỏ
       CẢI CÁCH WHEATLEY (9/2012):
       · chính phủ giám sát thay BBA ("rõ ràng thất bại")
       · NH phải cung cấp DỮ LIỆU chứng minh lãi báo phản ánh chi
         phí vay thật
       · công bố báo cáo cá nhân TRỄ 3 THÁNG → bớt động cơ nói dối
         khi căng thẳng
       · HÌNH SỰ HOÁ báo cáo sai
       · bỏ AUD, CAD, DKK, NZD, SEK và 4 kỳ hạn → 150 xuống 20
                                │
                                ▼
       NHƯNG nhiều lãi suất vẫn không có giao dịch liên NH thật
       → khuyến khích thị trường NGHĨ LẠI việc dùng LIBOR và có
       KẾ HOẠCH DỰ PHÒNG nếu LIBOR không còn
```

## Ba câu hỏi bài viết trả lời

1. LIBOR được xác định thế nào và vì sao quan trọng?
2. Vì sao LIBOR bị gọi là "hư cấu tiện lợi" và bị thao túng ra sao?
3. Anh đề xuất cải cách gì?

## Khái niệm cần biết

**Thị trường liên ngân hàng (interbank market).** Nơi các ngân hàng cho nhau vay tiền ngắn hạn, thường không có tài sản bảo đảm, để bù chỗ thừa thiếu vốn hằng ngày. Ví dụ minh hoạ: cuối ngày ngân hàng A thừa 100 triệu USD, ngân hàng B thiếu, A cho B vay qua đêm. LIBOR là con số tóm tắt mức lãi trên thị trường này ở London.

**Lãi suất chuẩn (benchmark rate).** Một lãi suất được công bố công khai, dùng làm mốc để tính lãi của các hợp đồng khác. Ví dụ minh hoạ: một khoản vay doanh nghiệp có lãi "LIBOR 3 tháng cộng 2%"; nếu LIBOR là 1% thì người vay trả 3%, nếu LIBOR lên 2% thì trả 4%. Khái niệm này giải thích vì sao bài nói LIBOR quan trọng không phải vì ngân hàng giao dịch ở mức đó mà vì hàng trăm nghìn tỷ USD hợp đồng khác tính lãi theo nó.

**Kỳ hạn (tenor).** Thời gian của khoản vay mà một lãi suất áp dụng: qua đêm, một tuần, một tháng, ba tháng… cho tới một năm. LIBOR được công bố cho 15 kỳ hạn mỗi đồng tiền. Khái niệm này quan trọng vì vấn đề "hư cấu tiện lợi" nằm đúng ở chỗ các kỳ hạn dài gần như không có giao dịch thật.

**Lãi suất thả nổi (floating rate).** Lãi suất của một khoản vay được điều chỉnh định kỳ theo một lãi suất chuẩn, thay vì cố định suốt thời hạn. Ví dụ minh hoạ: khoản vay mua nhà điều chỉnh lãi ba tháng một lần theo LIBOR cộng một biên cố định. Hàng chục tỷ USD thế chấp nhà và vay tiêu dùng trên thế giới gắn với LIBOR theo cách này.

**Hợp đồng tương lai, hợp đồng lãi suất kỳ hạn và hoán đổi lãi suất.** Các công cụ phái sinh cho phép hai bên chốt trước hoặc trao đổi dòng tiền lãi để phòng hộ rủi ro lãi suất. Ví dụ minh hoạ về hoán đổi lãi suất: doanh nghiệp đang vay thả nổi theo LIBOR đồng ý trả cho ngân hàng lãi cố định 3% và nhận lại lãi thả nổi theo LIBOR, nhờ vậy chi phí lãi của họ thành cố định. Mọi hợp đồng loại này đều cần một lãi suất chuẩn đáng tin để tính tiền thanh toán, và đó là lý do LIBOR ra đời.

**Báo thấp (lowballing).** Ngân hàng cố ý báo mức lãi mình có thể vay thấp hơn mức thực tin là phải trả, để không lộ ra rằng mình đang khó vay. Ví dụ minh hoạ: một ngân hàng thực ra chỉ vay được ở 3,5% nhưng báo 3,0% để trông giống các ngân hàng khoẻ. Đây là cơ chế làm LIBOR thấp bất thường sau khi Lehman Brothers sụp đổ.

**Điểm cơ bản (basis point).** Một phần trăm của một phần trăm, tức 0,01%. Ví dụ: lãi suất tăng từ 2,00% lên 2,25% là tăng 25 điểm cơ bản. Với 300 nghìn tỷ USD hợp đồng gắn với LIBOR, sai lệch chỉ vài điểm cơ bản cũng tương ứng với số tiền rất lớn.

## Nội dung chi tiết

### 1. Quy trình và tầm quan trọng

**LIBOR được tạo ra thế nào.** Mỗi ngày làm việc, khoảng 11 giờ sáng (11h), 18 ngân hàng lớn, dưới sự bảo trợ của Hiệp hội Ngân hàng Anh (BBA), báo cáo mức lãi suất mà họ **tin** rằng họ có thể vay một "lượng hợp lý" đô la Mỹ từ các ngân hàng khác trên thị trường liên ngân hàng London. Mỗi ngân hàng báo cho 15 kỳ hạn, từ qua đêm đến một năm. Sau đó:

1. Thomson Reuters gom tất cả các báo cáo.
2. Với mỗi kỳ hạn, bỏ 4 mức cao nhất và 4 mức thấp nhất.
3. Lấy trung bình các mức còn lại (với panel 18 ngân hàng là 10 mức).
4. Công bố lãi suất trung bình cho từng kỳ hạn.

Việc bỏ hai đầu nhằm hạn chế ảnh hưởng của một ngân hàng báo quá lệch. Quy trình tương tự được thực hiện cho chín đồng tiền khác nữa, tổng cộng 10 đồng tiền, mỗi đồng có một panel từ 6 đến 16 ngân hàng báo hằng ngày chi phí vay của mình: đô la Úc, bảng Anh, đô la Canada, krone Đan Mạch, euro, yên Nhật, đô la New Zealand, krona Thụy Điển và franc Thụy Sĩ, bên cạnh đô la Mỹ. Với 10 đồng tiền và 15 kỳ hạn, có tất cả 150 lãi suất. Người ta thường gọi chung bằng số ít là "lãi suất liên ngân hàng London" (LIBOR), một trong những lãi suất nổi tiếng và quan trọng nhất thế giới.

**Vì sao LIBOR quan trọng.** Tầm quan trọng của LIBOR không đến từ việc các ngân hàng thực sự vay nhau ở mức công bố, dù họ có thể làm vậy. Nó đến từ việc LIBOR được dùng rộng rãi làm **chuẩn** cho rất nhiều lãi suất khác mà ở đó giao dịch thật sự diễn ra. Theo báo cáo của Bộ Tài chính Anh, khoảng 300 nghìn tỷ USD hợp đồng tài chính gắn với LIBOR, chưa kể hàng chục tỷ USD khoản vay thế chấp nhà có lãi suất thả nổi và các khoản vay tiêu dùng khắp thế giới cũng tham chiếu LIBOR. Vì đô la Mỹ là đồng tiền quan trọng nhất, LIBOR USD là loại được dùng và trích dẫn nhiều nhất.

**Thay đổi sắp đến.** Nhiều thứ sắp thay đổi vì hai lý do: tranh cãi về cách một số ngân hàng báo mức lãi họ "tin", và vấn đề nằm ngay trong khái niệm LIBOR. Cuối tháng 9/2012, chính phủ Anh công bố đề xuất ba hướng: đưa việc thiết lập và duy trì chuẩn này vào tầm quản lý của nhà nước, dựa nó trên giao dịch thật, và bỏ phần lớn trong số 150 lãi suất riêng lẻ.

### 2. Một phát minh gần đây

**Nguồn gốc.** Các ngân hàng ở London đã cho nhau vay hàng thế kỷ, nhưng LIBOR là một ý tưởng khá mới. Nó bắt nguồn từ sự tăng trưởng đột ngột, đầu thập niên 1980, của các hợp đồng tương lai dùng để phòng hộ rủi ro lãi suất. Các hợp đồng này cần một lãi suất chuẩn tốt để làm căn cứ thanh toán khi đáo hạn. Thị trường tìm đến hiệp hội ngành ngân hàng và Ngân hàng Trung ương Anh, và Hiệp hội Ngân hàng Anh cho ra đời LIBOR năm 1986, ban đầu chỉ cho 3 đồng tiền: đô la Mỹ, yên Nhật và bảng Anh.

**Mục đích và sự lan rộng.** LIBOR được lập ra làm chuẩn để định giá các khoản vay doanh nghiệp có lãi suất thả nổi. Nhưng thời điểm nó ra đời lại trùng với sự phát triển của các công cụ tài chính mới dựa trên lãi suất, như hợp đồng lãi suất kỳ hạn (FRA) và hoán đổi lãi suất. Những công cụ này cũng cần một lãi suất chuẩn được chuẩn hoá và minh bạch, nên LIBOR nhanh chóng trở thành chuẩn chung.

**LIBOR đo cái gì, và điểm yếu.** Về nguyên tắc, LIBOR phản ánh thực tế: nó là trung bình của mức mà các ngân hàng tin họ phải trả để vay một lượng tiền hợp lý trong một kỳ hạn ngắn xác định, tức là chi phí vốn của họ, kể cả vào những ngày họ không thực sự cần vay. Tuy vậy, từ lâu LIBOR đã bị nghi là có phương pháp lỗi: nó dễ bị méo trong thời kỳ căng thẳng, khi các ngân hàng ngừng cho nhau vay ở toàn bộ dải kỳ hạn, nên mức báo không còn dựa trên giao dịch nào.

**Bê bối Barclays.** Thách thức trực tiếp hơn đến từ việc Barclays, một ngân hàng lớn của Anh, đã tìm cách thao túng LIBOR và một số chuẩn khác. Tháng 6/2012, Barclays đồng ý nộp phạt tổng cộng khoảng 450 triệu USD cho các cơ quan quản lý của Anh và Mỹ. Nhiều ngân hàng khác cũng đang bị điều tra vì báo sai, và giới phân tích ước tính tổng tiền phạt và bồi thường kiện tụng có thể lên gần 50 tỷ USD.

### 3. Hư cấu tiện lợi

**Vì sao gọi là "hư cấu tiện lợi".** Ngay cả trước tranh cãi về thao túng, LIBOR đã thường bị gọi là "hư cấu tiện lợi" vì có sự lệch pha giữa LIBOR dùng làm chuẩn và việc vay mượn thực tế trên thị trường liên ngân hàng London. Phần lớn các ngân hàng chỉ cho nhau vay kỳ hạn 1 tuần hoặc ngắn hơn, nên LIBOR ở các kỳ hạn dài hơn chủ yếu dựa trên ước đoán có căn cứ chứ không phải giao dịch. Nghịch lý là gần 95% giao dịch tham chiếu LIBOR, từ phái sinh lãi suất đến thế chấp nhà, lại gắn với kỳ hạn từ 3 tháng trở lên. Theo Bộ Tài chính Anh, LIBOR USD kỳ hạn 3 tháng là loại phổ biến nhất. Tức là phần được dùng nhiều nhất của LIBOR cũng là phần ít dựa trên giao dịch thật nhất.

Một dấu hiệu nữa cho thấy cho vay không bảo đảm kỳ hạn dài giữa các ngân hàng gần như đã thành hư cấu: ICAP, một công ty môi giới lớn ở London, quyết định ngừng công bố chỉ số vốn New York (NYFR) kỳ hạn một tháng và ba tháng, vốn là một lựa chọn thay thế LIBOR, vì không có đủ dữ liệu từ các ngân hàng ở New York.

**LIBOR nhìn chung chính xác, trừ một giai đoạn.** Dù vậy, phần lớn thời gian LIBOR khá chính xác: nó bám sát các chuẩn tương tự gắn với chi phí vốn không bảo đảm thật của ngân hàng, như lãi suất thương phiếu. Ngoại lệ rõ ràng là giai đoạn ngay sau khi Lehman Brothers sụp đổ tháng 9/2008, sự kiện châm ngòi cho khủng hoảng toàn cầu. Khi đó LIBOR USD 3 tháng tách khỏi hai lãi suất ngắn hạn tương tự được công bố công khai:

| So với | Diễn biến |
|---|---|
| Lãi suất tiền gửi Eurodollar 3 tháng (tiền gửi bằng USD tại ngân hàng ngoài nước Mỹ) | LIBOR đã thấp hơn từ đầu năm 2008, và thấp hơn hẳn ngay sau Lehman |
| NYFR của ICAP | LIBOR bám rất sát, trừ ngay sau Lehman khi cũng thấp hơn rõ rệt |

**Vì sao LIBOR thấp bất thường.** Một phần nguyên nhân là hệ quả ngoài ý muốn của chính quy tắc mà Hiệp hội Ngân hàng Anh đặt ra để buộc ngân hàng báo trung thực: báo cáo của từng ngân hàng được công bố ngay lập tức. Bình thường, việc công khai này khuyến khích trung thực vì ai báo lệch sẽ bị nhìn thấy. Nhưng trong giai đoạn 2007–08, cơ chế bảo vệ đó có thể đã phản tác dụng. Một ngân hàng báo mức lãi cao hơn các ngân hàng khác sẽ ngầm thừa nhận rằng mình đang khó vay. Vì vậy, để che giấu vấn đề thanh khoản, những ngân hàng đang gặp khó có động cơ báo thấp hơn mức họ thực sự tin.

Nhiều nghiên cứu gợi ý các ngân hàng đã báo thấp sau khi Bear Stearns sụp đổ tháng 3/2008 và một lần nữa sau khi Lehman sụp đổ sáu tháng sau đó. Các nghiên cứu khác tìm thấy những tình huống gợi ý ngân hàng báo không chính xác. Tuy nhiên, các nghiên cứu đi tìm dấu hiệu cụ thể của sự **thông đồng** giữa các ngân hàng nhìn chung không đưa ra được kết luận.

### 4. Cải cách Wheatley

**Cứu chứ không bỏ.** Sau bê bối, đã có những lời kêu gọi bỏ hẳn LIBOR. Nhưng vì LIBOR quá quan trọng và quá phổ biến làm chuẩn, chính phủ Anh kết luận không thể vứt bỏ mà phải cứu nó.

**Nội dung cải cách.** Martin Wheatley, giám đốc điều hành Cơ quan Dịch vụ Tài chính Anh, nêu các thay đổi đề xuất trong báo cáo cuối tháng 9/2012. Ông nói Hiệp hội Ngân hàng Anh đã "rõ ràng thất bại trong việc giám sát đúng đắn quy trình thiết lập LIBOR". Các đề xuất gồm:

| Đề xuất | Mục đích |
|---|---|
| Chính phủ tiếp quản việc giám sát LIBOR từ Hiệp hội Ngân hàng Anh | Thay một cơ chế tự quản đã thất bại |
| LIBOR vẫn được lập hằng ngày từ báo cáo của panel ngân hàng, nay gửi cho cơ quan quản lý Anh, và ngân hàng phải cung cấp dữ liệu chứng minh mức báo phản ánh chính xác chi phí vay thật | Gắn mức báo với giao dịch có thể kiểm chứng |
| Vẫn công bố báo cáo của từng ngân hàng, nhưng trễ 3 tháng | Để ngân hàng không còn động cơ nói dối trong thời kỳ căng thẳng, vì khi số liệu được công bố thì căng thẳng đã qua |
| Chế tài hình sự với ngân hàng báo sai | Tăng cái giá của thao túng |
| Loại dần 5 đồng tiền (đô la Úc, đô la Canada, krone Đan Mạch, đô la New Zealand, krona Thụy Điển) và bỏ 4 kỳ hạn | Tập trung vào các lãi suất quan trọng và có chi phí vốn kiểm chứng được |

Theo bài, nhờ các cắt giảm trên, số lãi suất LIBOR giảm từ 150 xuống còn 20 lãi suất quan trọng nhất với thị trường.

**Vấn đề còn lại.** Ngay cả sau cải cách, nhiều lãi suất LIBOR vẫn không có giao dịch liên ngân hàng thật đứng sau. Vì vậy báo cáo Wheatley khuyến khích các thành viên thị trường suy nghĩ lại việc dùng LIBOR làm chuẩn, và chuẩn bị kế hoạch dự phòng cho trường hợp lãi suất này không còn được công bố nữa.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| LIBOR | Lãi suất liên ngân hàng London: trung bình lãi suất ngân hàng lớn tin mình vay được từ nhau |
| British Bankers' Association (BBA) | Hiệp hội Ngân hàng Anh: bảo trợ LIBOR từ 1986 |
| Tenor | Kỳ hạn của lãi suất, từ qua đêm đến một năm |
| Benchmark | Lãi suất chuẩn để định giá hợp đồng khác |
| Floating-rate loan | Vay lãi suất thả nổi, gắn với LIBOR |
| Forward rate agreement / interest rate swap | Hợp đồng lãi suất kỳ hạn / hoán đổi lãi suất: công cụ cần chuẩn lãi suất |
| Convenient fiction | "Hư cấu tiện lợi": LIBOR kỳ hạn dài dựa ước đoán vì ít giao dịch thật |
| NYFR | Chỉ số vốn New York của ICAP, lựa chọn thay thế LIBOR, ngừng 8/2012 |
| Eurodollar deposits | Tiền gửi USD tại ngân hàng ngoài Mỹ |
| Lowballing | Báo thấp: ngân hàng báo lãi thấp hơn thực để che khó khăn thanh khoản |
| Wheatley report | Báo cáo cải cách LIBOR của Anh, tháng 9/2012 |
| Basis point | Điểm cơ bản: 1/100 của 1% |

## Câu nói đáng nhớ

> "LIBOR's importance derives from its widespread use as a benchmark for many other interest rates at which business is actually carried out."

> "LIBOR was often called a 'convenient fiction' because of the disconnect between the LIBORs used as benchmarks and actual borrowing in the London interbank market."

## Đánh giá và phát hiện đáng chú ý

### Bài đưa ra chẩn đoán đúng, rồi tường thuật một phương thuốc không thể chữa được căn bệnh đó

Toàn bộ cấu trúc bài đi theo giọng "cứu chứ không bỏ": chính phủ Anh kết luận LIBOR quá quan trọng để vứt đi, nên sẽ siết giám sát, buộc chứng minh bằng dữ liệu, hoãn công bố ba tháng, hình sự hóa việc báo sai, và cắt từ 150 lãi suất xuống 20.

Không gói cải cách nào trong số đó có thể tạo ra thứ đang thiếu. Và bài biết điều đó — đoạn cuối cùng nói thẳng rằng nhiều lãi suất vẫn không có giao dịch thật đứng sau, nên thị trường nên chuẩn bị kế hoạch dự phòng. **Đoạn ngắn nhất và ít nhấn mạnh nhất lại là đoạn đúng nhất.** LIBOR các đồng bảng, euro, yên, franc Thụy Sĩ ngừng cuối 2021; LIBOR đô la Mỹ, thứ quan trọng nhất trong cả họ, ngừng công bố ngày 30/6/2023. Cải cách Wheatley kéo dài tuổi thọ của nó thêm mười năm, không hơn.

Bài học tổng quát đáng giữ: khi một chỉ số đo một thứ không tồn tại, cải thiện quy trình đo không giải quyết được gì. Câu hỏi đúng không phải "làm sao để ngân hàng báo cáo trung thực hơn" mà "có giao dịch nào để báo cáo không".

### Nghịch lý 95% so với một tuần, và lý do nó đã quay lại dưới một cái tên mới

Con số đáng suy nghĩ nhất trong bài nằm ở phần "hư cấu tiện lợi": các ngân hàng thực tế cho nhau vay **một tuần hoặc ngắn hơn**, trong khi gần **95%** hợp đồng tham chiếu LIBOR gắn với kỳ hạn **ba tháng trở lên**. Đây không phải một lỗi kỹ thuật mà là một nhu cầu kinh tế không được đáp ứng: người cho vay và người vay muốn biết trước lãi suất của cả quý, trong khi thị trường liên ngân hàng chỉ sản xuất được thông tin cho vài ngày tới.

Cái thay thế LIBOR ở Mỹ xử lý vấn đề trung thực rất tốt: nó được tính từ hàng nghìn tỷ đô la giao dịch repo thật mỗi ngày, không ai báo cáo gì, không ai thao túng được. Nhưng nó là lãi suất **qua đêm**. Để dùng cho một khoản vay ba tháng, phải cộng gộp lãi suất qua đêm suốt kỳ và người vay chỉ biết mình trả bao nhiêu vào lúc kỳ đã kết thúc — điều mà một doanh nghiệp lập kế hoạch dòng tiền không chấp nhận được.

Thị trường phản ứng bằng cách tạo ra một phiên bản kỳ hạn của lãi suất mới, suy ra từ **hợp đồng tương lai** — tức là từ kỳ vọng của thị trường về lãi suất qua đêm trong tương lai, chứ không phải từ giao dịch vay kỳ hạn thật. Đây là một cải thiện lớn so với việc hỏi ý kiến 18 ngân hàng, nhưng xét về bản chất logic, "hư cấu tiện lợi" đã quay lại: một con số cho kỳ hạn ba tháng, dựng từ một thị trường không giao dịch kỳ hạn ba tháng. Sự khác biệt là giờ đây nó được dựng từ giá thị trường quan sát được thay vì từ lời khai, và đó là một khác biệt thật — nhưng nhỏ hơn cách nó thường được trình bày.

### Chuẩn mới đã gỡ bỏ đúng thứ khiến LIBOR hữu ích với ngân hàng

Đây là hệ quả mà bài không thể lường trước vì nó chỉ lộ ra sau khi chuyển đổi hoàn tất.

LIBOR là lãi suất vay **không có bảo đảm** giữa các ngân hàng, nên trong nó có sẵn một phần bù rủi ro tín dụng ngân hàng. Chuẩn thay thế là lãi suất vay **có bảo đảm bằng trái phiếu kho bạc**, nên phần bù đó bằng không. Trong điều kiện bình thường, chênh lệch nhỏ và không ai bận tâm.

Trong khủng hoảng thì hai chỉ số chạy **ngược chiều nhau**. Tháng 3/2020, khi thị trường hoảng loạn, chi phí vay không bảo đảm của ngân hàng tăng vọt trong khi tiền chạy vào trái phiếu kho bạc kéo lãi suất có bảo đảm xuống gần 0 — khoảng cách giữa hai loại giãn ra hơn một trăm điểm cơ bản trong vài tuần.

Hệ quả với một ngân hàng cho vay theo lãi suất thả nổi neo vào chuẩn mới rất khó chịu: đúng lúc chi phí huy động của chính nó tăng vì thị trường nghi ngờ khu vực ngân hàng, thì lãi suất nó thu từ danh mục cho vay lại giảm. Biên lãi bị ép từ hai phía cùng một lúc, và bị ép mạnh nhất vào đúng lúc ngân hàng dễ tổn thương nhất. Ngành đã thử vài chuẩn thay thế có chứa phần bù tín dụng ngân hàng, một trong số đó bị khai tử năm 2023, và vấn đề đến nay vẫn chưa có lời giải sạch. Nói cách khác: cuộc cải cách giải quyết được bài toán liêm chính và tạo ra một bài toán quản trị rủi ro mới.

Một chi tiết nữa đáng ghi: bài tường thuật việc hình sự hóa báo cáo sai như một trụ cột của cải cách. Hơn một thập niên sau, tòa án cao nhất của Anh đã hủy bản án của những nhà giao dịch bị kết tội thao túng LIBOR nổi bật nhất, với lý do phần hướng dẫn bồi thẩm đoàn đã xử lý sai câu hỏi liệu việc tính đến lợi ích thương mại khi đưa ra một mức báo cáo hợp lệ có cấu thành gian lận hay không. Kết cục này không xóa bỏ bản chất của bê bối, nhưng nó nói một điều đáng suy nghĩ về việc dùng luật hình sự để vá một chỉ số mà chính quy tắc của nó chưa bao giờ định nghĩa rõ thế nào là một con số đúng.

### Phát hiện có giá trị nhất của bài bị chôn ở giữa: minh bạch có thể tự phá hỏng chính nó

Đoạn giải thích vì sao LIBOR **thấp hơn** các chuẩn khác ngay sau Lehman là phần sâu nhất của bài, và nó được viết như một ghi chú kỹ thuật.

Hiệp hội Ngân hàng Anh công bố ngay lập tức báo cáo của từng ngân hàng, chủ đích là buộc họ trung thực vì ai cũng nhìn thấy. Trong thời bình, cơ chế này hoạt động. Trong khủng hoảng, nó đảo ngược hoàn toàn: báo cáo một mức lãi cao đồng nghĩa với việc công khai thừa nhận "không ai muốn cho tôi vay", một tín hiệu có thể tự nó kích hoạt cuộc rút vốn. Nên ngân hàng gặp khó khăn nhất lại có động cơ mạnh nhất để **báo thấp hơn** mức mình thật sự tin.

Nguyên lý rút ra vượt xa phạm vi LIBOR: **mọi cơ chế công bố thông tin mà bản thân việc công bố là một tín hiệu về sức khỏe của người công bố sẽ bị bóp méo đúng vào lúc độ chính xác quan trọng nhất.** Cùng một cơ chế giải thích vì sao ngân hàng né cửa sổ cho vay khẩn cấp của ngân hàng trung ương dù đang cần tiền — vay ở đó bị coi là dấu hiệu tuyệt vọng. Nó cũng giải thích vì sao việc công bố kết quả kiểm tra sức chịu đựng từng ngân hàng là con dao hai lưỡi, một điểm nên đọc cùng bài về kiểm tra sức chịu đựng trong cùng thư mục này. Cải cách Wheatley đã nhận ra và xử lý đúng chỗ này bằng cách hoãn công bố ba tháng — một sửa đổi nhỏ về thủ tục nhưng đúng về nguyên lý.

### Với Việt Nam: chuẩn lãi suất còn yếu hơn LIBOR, và người vay mua nhà là bên chịu

Bài này đọc từ Việt Nam sẽ thấy quen một cách khó chịu.

Lãi suất liên ngân hàng Việt Nam về nguyên tắc có cấu trúc giống LIBOR — do các ngân hàng thành viên báo, thị trường kỳ hạn dài mỏng, giao dịch thật tập trung ở qua đêm và một tuần. Nhưng khác biệt quan trọng là nó hầu như **không được dùng làm chuẩn** cho hợp đồng tín dụng.

Thay vào đó, hợp đồng vay mua nhà lãi suất thả nổi ở Việt Nam thường neo vào "lãi suất tiết kiệm kỳ hạn 12 hoặc 13 tháng của chính ngân hàng cho vay, cộng biên độ". Xét theo tiêu chuẩn mà bài này dùng để phê phán LIBOR, cách làm đó tệ hơn ở mọi chiều: không phải trung bình của một nhóm mà là con số của **một** tổ chức; tổ chức đó chính là bên thu lãi, nên có lợi ích trực tiếp từ việc con số cao lên; không có cơ chế cắt bỏ giá trị cực trị; không có cơ quan quản lý giám sát việc thiết lập; và mức lãi tiết kiệm 13 tháng thường là một sản phẩm rất ít khách hàng thực sự gửi, nghĩa là bản thân nó cũng gần với một con số niêm yết hơn là một giá giao dịch.

Toàn bộ chuỗi lập luận của bài — xung đột lợi ích, thiếu giao dịch nền, cần giám sát nhà nước, cần dữ liệu chứng minh — áp dụng trực tiếp, và áp dụng cho một loại hợp đồng mà bên chịu thiệt là hộ gia đình chứ không phải nhà giao dịch phái sinh.

Hệ quả thứ hai ít được nói tới: khi không có một chuẩn lãi suất đáng tin, thị trường phái sinh lãi suất không thể hình thành, nên doanh nghiệp Việt Nam không có công cụ phòng hộ rủi ro lãi suất. Bài nhắc rằng LIBOR ra đời **chính vì** nhu cầu thanh toán hợp đồng tương lai lãi suất đầu thập niên 1980 — tức chuẩn lãi suất là điều kiện tiên quyết, không phải hệ quả, của một thị trường quản trị rủi ro.

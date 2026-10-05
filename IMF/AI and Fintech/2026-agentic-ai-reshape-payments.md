# How Agentic AI Will Reshape Payments — AI tác tử sẽ định hình lại thanh toán như thế nào

**Nguồn:** IMF Note NOTE/2026/004, tháng 4/2026.
**Tác giả:** Sonja Davidovic và Hervé Tourpe.
**Ý chính:** Thanh toán đang chuyển từ "bấm để trả" sang "quyết định để trả": con người uỷ quyền cho tác tử AI tự tìm kiếm, thương lượng và thực hiện giao dịch. Bài đề xuất mô hình ba lớp — lớp ý định và điều phối, lớp kiểm soát và uỷ quyền, lớp quyết toán — để phân tích thay đổi này, và lập luận rằng lớp ở giữa là nơi quyền lực kinh tế cùng trách nhiệm quản lý sẽ tập trung. Rủi ro lớn nhất không phải công nghệ hỏng, mà là tốc độ và quy mô của lỗi khi tác tử hành động nhanh hơn khả năng can thiệp của con người.

## Sơ đồ

### Từ "click-to-pay" sang "decide-to-pay"

```text
       MÔ HÌNH CŨ — CLICK-TO-PAY
       Người dùng ──▸ duyệt ──▸ chọn ──▸ BẤM XÁC NHẬN ──▸ thanh toán
                                           ▲
                          MỖI giao dịch có MỘT hành động CÓ Ý THỨC
                          của con người tại ĐÚNG thời điểm chuyển tiền
       → sự đồng ý, danh tính và uỷ quyền TRÙNG NHAU trong một cú bấm
                                │
                                ▼
       MÔ HÌNH MỚI — DECIDE-TO-PAY
       Người dùng ──▸ nêu MỤC TIÊU ("đặt chuyến đi dưới 800 đô,
                      bay thẳng, huỷ được")
            │
            ▼
       Tác tử AI ──▸ tìm kiếm ──▸ so sánh ──▸ THƯƠNG LƯỢNG ──▸ mua
            │                                        │
            │                          có thể gọi TÁC TỬ KHÁC (bên bán,
            │                          bên vận chuyển, bên bảo hiểm)
            ▼
       Con người CHỈ thấy KẾT QUẢ, không thấy từng bước
       → sự đồng ý được cho TRƯỚC và theo DẢI RỘNG, tách khỏi thời
         điểm chuyển tiền cả về THỜI GIAN lẫn NỘI DUNG
                                │
                                ▼
       BA HỆ QUẢ TRỰC TIẾP
       ① SỐ LƯỢNG giao dịch tăng vọt, GIÁ TRỊ mỗi giao dịch giảm
         (tác tử chia nhỏ, thử, huỷ, thử lại) → áp lực lên phí cố định
         và lên hạ tầng vi thanh toán
       ② TỐC ĐỘ vượt nhịp con người: một lỗi logic có thể nhân bản
         thành HÀNG NGHÌN giao dịch trước khi ai kịp nhìn
       ③ Câu hỏi "AI ĐÃ UỶ QUYỀN cho giao dịch này?" thay thế câu hỏi
         "AI đã bấm nút?" → cần bằng chứng uỷ quyền KIỂM TOÁN ĐƯỢC
```

### Kiến trúc ba lớp

```text
       ┌───────────────────────────────────────────────────────────┐
       │ LỚP 1 — Ý ĐỊNH VÀ ĐIỀU PHỐI (intent & orchestration)      │
       │ · nơi mục tiêu của con người được DIỄN GIẢI thành kế hoạch│
       │ · tác tử phân rã mục tiêu, gọi công cụ, gọi tác tử khác   │
       │ · giao thức đang hình thành: MCP (kết nối tác tử với công │
       │   cụ và dữ liệu), A2A (tác tử nói chuyện với tác tử)      │
       │ · RỦI RO: diễn giải sai ý định, tác tử bị tiêm lệnh        │
       │   (prompt injection), xung đột mục tiêu giữa các tác tử   │
       └───────────────────────────┬───────────────────────────────┘
                                   │ ý định đã cấu trúc hoá
                                   ▼
       ┌───────────────────────────────────────────────────────────┐
       │ LỚP 2 — KIỂM SOÁT VÀ UỶ QUYỀN (control & authorization)   │
       │ ★ LỚP QUYẾT ĐỊNH — nơi tập trung quyền lực và trách nhiệm │
       │ · kiểm tra: tác tử này CÓ QUYỀN chi tiêu không? trong hạn │
       │   mức nào? thay mặt AI? phạm vi nào? hết hạn khi nào?     │
       │ · công cụ: uỷ quyền có thể kiểm chứng bằng mật mã, token  │
       │   phạm vi hẹp, hạn mức, danh sách thương nhân, chữ ký     │
       │ · chuẩn đang cạnh tranh: UCP của OpenAI-Stripe, AP2 của   │
       │   Google, x402 (hồi sinh mã HTTP 402), ERC-1812/4337/     │
       │   6900/8004 trên Ethereum                                 │
       │ · Ở ĐÂY diễn ra KYA (know your agent), chống rửa tiền,    │
       │   trừng phạt, giới hạn rủi ro, và CÔNG TẮC NGẮT           │
       └───────────────────────────┬───────────────────────────────┘
                                   │ lệnh đã được uỷ quyền
                                   ▼
       ┌───────────────────────────────────────────────────────────┐
       │ LỚP 3 — QUYẾT TOÁN (settlement)                           │
       │ · chuyển giá trị thật: thẻ, chuyển khoản tức thời, tiền   │
       │   gửi token hoá, stablecoin, CBDC                         │
       │ · phần lớn hạ tầng này ĐÃ TỒN TẠI và hoạt động tốt        │
       │ · thách thức là THÍCH ỨNG: chi phí đơn vị cho giao dịch   │
       │   siêu nhỏ, tính khả dụng 24/7, khả năng ĐẢO NGƯỢC        │
       └───────────────────────────────────────────────────────────┘
       LUẬN ĐIỂM TRUNG TÂM: lớp 3 không phải điểm nghẽn. AI THẮNG hay
       THUA ở LỚP 2. Ai kiểm soát lớp uỷ quyền sẽ đặt ra luật chơi
       kinh tế và là đối tượng tự nhiên của quản lý nhà nước.
```

### Bốn thập niên thay đổi và nơi tác tử chen vào

```text
       1980s  THẺ và MÁY ATM ──▸ tách thanh toán khỏi quầy ngân hàng
       1990s  THƯƠNG MẠI ĐIỆN TỬ ──▸ tách thanh toán khỏi cửa hàng
       2000s  VÍ ĐIỆN TỬ và PayPal ──▸ tách thanh toán khỏi thẻ nhựa
       2010s  DI ĐỘNG và MÃ QR ──▸ tách thanh toán khỏi thiết bị đầu
              cuối; thanh toán tức thời trở nên phổ biến
       2020s  THANH TOÁN NHÚNG và THỜI GIAN THỰC ──▸ tách thanh toán
              khỏi hành động thanh toán (nhúng vào ứng dụng gọi xe,
              giao đồ ăn, phần mềm kế toán)
       ────────────────────────────────────────────────────────────
       2020s cuối  AI TÁC TỬ ──▸ tách QUYẾT ĐỊNH khỏi CON NGƯỜI
              · mỗi làn sóng trước đây bỏ đi một BƯỚC THAO TÁC
              · làn sóng này bỏ đi chính NGƯỜI RA QUYẾT ĐỊNH tại
                thời điểm giao dịch
       ────────────────────────────────────────────────────────────
       AI ĐANG XÂY GÌ (Hộp 1)
       · OpenAI + Stripe: Universal Commerce Protocol, mua hàng ngay
         trong hội thoại
       · Amazon: tác tử mua sắm gắn với danh mục của chính mình
       · Google: Agent Payments Protocol (AP2) mở cho bên thứ ba
       · Visa và Mastercard: chương trình tác tử với token uỷ quyền
         gắn vào mạng thẻ hiện có
       · PayPal: bộ công cụ tác tử cho thương nhân
       → CUỘC ĐUA THỰC SỰ là giành LỚP 2, không phải lớp 3
```

### Ma trận rủi ro và hướng giảm thiểu

```text
       ❶ RỦI RO VẬN HÀNH — lỗi nhân bản theo cấp số
         · tác tử hiểu sai "rẻ nhất" và đặt 400 vé không huỷ được
         · giảm thiểu: HẠN MỨC cứng theo giao dịch, theo ngày, theo
           thương nhân · CÔNG TẮC NGẮT (kill switch) ở cấp tác tử,
           cấp nhà cung cấp và cấp hệ thống · giới hạn tốc độ
                                │
       ❷ RỦI RO UỶ QUYỀN VÀ TRÁCH NHIỆM — ai chịu khi tác tử sai?
         · người dùng? nhà phát triển tác tử? nền tảng? ngân hàng?
         · luật bảo vệ người tiêu dùng hiện hành giả định con người
           bấm nút → khái niệm "giao dịch không được uỷ quyền" trở
           nên MƠ HỒ
         · giảm thiểu: bằng chứng uỷ quyền KIỂM TOÁN ĐƯỢC, phân định
           trách nhiệm theo hợp đồng và theo luật
                                │
       ❸ RỦI RO TÍNH TOÀN VẸN — KYA bên cạnh KYC
         · tác tử có thể bị chiếm quyền, giả mạo, hoặc dùng làm lớp
           che giấu chủ sở hữu hưởng lợi
         · giảm thiểu: danh tính tác tử có thể kiểm chứng, sổ đăng ký
           tác tử, gắn mỗi tác tử với MỘT chủ thể pháp lý chịu trách
           nhiệm
                                │
       ❹ RỦI RO THỊ TRƯỜNG VÀ CẠNH TRANH — tập trung hoá
         · vài nền tảng có thể kiểm soát cả lớp ý định lẫn lớp uỷ
           quyền, tự ưu tiên hàng hoá của mình
         · tác tử đồng loạt phản ứng giống nhau → HÀNH VI BẦY ĐÀN
           và biến động giá đồng bộ
         · giảm thiểu: khả năng liên thông bắt buộc, chuẩn mở, quyền
           chuyển đổi tác tử
                                │
       ❺ RỦI RO HỆ THỐNG VÀ VĨ MÔ
         · nếu tác tử trở thành kênh thanh toán chính, sự cố một nhà
           cung cấp mô hình lan ra toàn nền kinh tế
         · giảm thiểu: giám sát tập trung rủi ro nhà cung cấp, kiểm
           thử chịu đựng, yêu cầu khả năng chống chịu vận hành
       ────────────────────────────────────────────────────────────
       KHUNG QUẢN LÝ ĐANG HÌNH THÀNH
       · Singapore IMDA: khung quản trị AI tác tử
       · EU AI Act: nghĩa vụ theo mức rủi ro, minh bạch với hệ thống
         tương tác với con người
       · KHUYẾN NGHỊ CỦA BÀI: quản lý theo CHỨC NĂNG (hoạt động nào
         đang được thực hiện) chứ không theo NHÃN công nghệ; đặt
         nghĩa vụ ở LỚP UỶ QUYỀN vì đó là nơi có thể thực thi
```

## Ba câu hỏi bài viết trả lời

1. AI tác tử thay đổi điều gì về bản chất trong chuỗi thanh toán, so với các làn sóng số hoá trước?
2. Vì sao lớp kiểm soát và uỷ quyền, chứ không phải lớp quyết toán, là nơi quyết định?
3. Cơ quan quản lý và ngân hàng trung ương nên chuẩn bị gì ngay từ bây giờ?

## Khái niệm cần biết

**AI tác tử (agentic AI).** Hệ thống AI không chỉ trả lời câu hỏi mà tự lập kế hoạch và tự hành động để đạt một mục tiêu được giao: tìm kiếm, so sánh, gọi phần mềm khác, điền biểu mẫu và trả tiền. Ví dụ trong bài: người dùng chỉ nói "đặt chuyến đi dưới 800 đô, bay thẳng, huỷ được", tác tử tự làm phần còn lại. Khái niệm này là nền của cả bài, vì thứ thay đổi là người ra quyết định tại thời điểm trả tiền không còn là con người.

**"Bấm để trả" và "quyết định để trả" (click-to-pay, decide-to-pay).** Trong mô hình bấm để trả, mỗi giao dịch có một hành động có ý thức của con người đúng lúc tiền chuyển đi, ví dụ bấm nút "Thanh toán". Trong mô hình quyết định để trả, con người đồng ý trước với một dải kết quả, còn tác tử chọn giao dịch cụ thể sau. Ví dụ minh hoạ: bạn cho phép tác tử "mua đồ tạp hoá hằng tuần, tối đa 1,5 triệu đồng", rồi không còn duyệt từng đơn. Đây là tên bài dùng cho bước chuyển mà nó phân tích.

**Uỷ quyền (authorization) và bằng chứng uỷ quyền kiểm toán được.** Uỷ quyền là việc xác nhận một giao dịch được người có quyền cho phép. Trong thanh toán cũ, cú bấm của chủ tài khoản kèm mật khẩu hay mã OTP là bằng chứng. Với tác tử, bằng chứng phải là một văn bản số ghi rõ ai cho phép, cho tác tử nào, trong hạn mức và thời hạn nào, và bên thứ ba kiểm tra lại được. Ví dụ minh hoạ: một "giấy uỷ quyền số" cho phép tác tử X chi tối đa 200 đô la mỗi tháng tại ba cửa hàng nhất định, hết hạn cuối năm. Bài coi đây là trọng tâm của toàn bộ vấn đề.

**Chứng thư có thể kiểm chứng và token phạm vi hẹp (verifiable credential, scoped token).** Chứng thư có thể kiểm chứng là một tài liệu số được ký bằng mật mã, nên ai cũng kiểm tra được nó thật và chưa bị sửa. Token phạm vi hẹp là một "chìa khoá" thanh toán chỉ dùng được trong giới hạn định trước: số tiền, thương nhân, thời gian. Ví dụ minh hoạ: thay vì đưa tác tử số thẻ thật, ngân hàng cấp một token chỉ chi được tối đa 50 đô la tại một hãng hàng không trong 24 giờ. Đây là công cụ chính của lớp kiểm soát và uỷ quyền.

**Biết tác tử của bạn (KYA, know your agent).** Ngân hàng vốn phải "biết khách hàng của bạn" (KYC): xác minh người mở tài khoản là ai. KYA là nghĩa vụ tương tự với tác tử: tác tử này là gì, do ai vận hành, thay mặt ai, ai chịu trách nhiệm pháp lý. Ví dụ minh hoạ: một sổ đăng ký trong đó mỗi tác tử có mã định danh gắn với một công ty hoặc cá nhân cụ thể. KYA quan trọng vì tác tử có thể bị chiếm quyền, giả mạo, hoặc bị dùng để che giấu người thật đứng sau.

**Công tắc ngắt (kill switch) và giới hạn tốc độ.** Công tắc ngắt là cơ chế dừng khẩn cấp mọi hoạt động của một tác tử, một nhà cung cấp, hay cả hệ thống. Giới hạn tốc độ là trần số giao dịch được phép trong một khoảng thời gian. Ví dụ trong bài: một tác tử hiểu sai "rẻ nhất" và đặt 400 vé không huỷ được; giới hạn tốc độ và công tắc ngắt chặn lỗi trước khi nó nhân lên. Đây là biện pháp giảm thiểu chính cho rủi ro vận hành.

**Vi thanh toán (micropayment).** Giao dịch có giá trị rất nhỏ, có thể chỉ vài xu, mà tác tử tạo ra với tần suất cao, ví dụ trả tiền cho mỗi lần truy vấn một nguồn dữ liệu. Ví dụ minh hoạ: nếu phí cố định mỗi giao dịch thẻ là 0,30 đô la, thì một khoản trả 0,05 đô la sẽ tốn phí gấp sáu lần giá trị của nó. Vì vậy thanh toán bằng tác tử gây áp lực lên cách tính phí của hạ tầng hiện có.

**Hành vi bầy đàn (herding behavior).** Khi nhiều tác tử dùng chung một mô hình nền và phản ứng giống nhau trước cùng một tín hiệu, chúng cùng mua hoặc cùng bán một lúc, làm giá biến động đồng bộ. Ví dụ minh hoạ: hàng nghìn tác tử cùng thấy một mặt hàng giảm giá và cùng đặt mua trong một phút, khiến hàng hết và giá bật tăng. Đây là một kênh rủi ro cạnh tranh và hệ thống trong bài.

## Nội dung chi tiết

### 1. Vì sao lần này khác

Trong bốn thập niên qua, thanh toán liên tục bị gỡ bỏ các bước trung gian. Mỗi làn sóng tách thanh toán khỏi một thứ:

| Thập niên | Đổi mới | Thanh toán được tách khỏi |
|---|---|---|
| 1980s | Thẻ và máy ATM | Quầy giao dịch ngân hàng |
| 1990s | Thương mại điện tử | Cửa hàng vật lý |
| 2000s | Ví điện tử và PayPal | Thẻ nhựa |
| 2010s | Di động và mã QR; thanh toán tức thời trở nên phổ biến | Thiết bị đầu cuối tại quầy |
| 2020s | Thanh toán nhúng và thời gian thực (trong ứng dụng gọi xe, giao đồ ăn, phần mềm kế toán) | Chính hành vi thanh toán có ý thức |
| Cuối 2020s | AI tác tử | Con người ra quyết định |

Mỗi làn sóng trước đây bỏ đi một bước thao tác, nhưng vẫn giữ nguyên một điểm cố định: tại thời điểm tiền chuyển đi, một con người đã ra quyết định. AI tác tử gỡ bỏ chính điểm cố định ấy. Đó là lý do bài gọi bước chuyển này là từ "bấm để trả" (click-to-pay) sang "quyết định để trả" (decide-to-pay).

**So sánh hai mô hình.** Trong mô hình cũ, người dùng duyệt hàng, chọn, bấm xác nhận rồi tiền đi. Trong mô hình mới, người dùng chỉ nêu mục tiêu, ví dụ "đặt chuyến đi dưới 800 đô, bay thẳng, huỷ được". Tác tử AI tự tìm kiếm, so sánh, thương lượng và mua; nó có thể gọi các tác tử khác của bên bán, bên vận chuyển, bên bảo hiểm. Con người chỉ thấy kết quả cuối, không thấy từng bước.

**Hệ quả pháp lý sâu xa.** Trong mô hình cũ, ba thứ hội tụ tại một cú bấm: sự đồng ý của người dùng, việc xác thực danh tính, và việc uỷ quyền chi tiêu. Trong mô hình mới, ba thứ đó tách rời nhau cả về thời gian lẫn phạm vi. Người dùng đồng ý trước với một dải kết quả có thể xảy ra, khi chưa biết giao dịch cụ thể sẽ là gì.

**Ba hệ quả trực tiếp:**

1. **Số lượng giao dịch tăng vọt, giá trị mỗi giao dịch giảm.** Tác tử chia nhỏ đơn hàng, thử, huỷ, thử lại. Điều này gây áp lực lên các khoản phí cố định mỗi giao dịch và lên hạ tầng vi thanh toán.
2. **Tốc độ vượt nhịp con người.** Một lỗi logic có thể nhân bản thành hàng nghìn giao dịch trước khi ai kịp nhìn thấy.
3. **Câu hỏi trung tâm thay đổi.** Câu hỏi của toàn ngành thanh toán không còn là "ai đã bấm nút" mà là "ai đã uỷ quyền cho giao dịch này, trong phạm vi nào, và có bằng chứng gì". Vì vậy cần bằng chứng uỷ quyền kiểm toán được.

### 2. Mô hình ba lớp

Bài đề xuất chia chuỗi thanh toán bằng tác tử thành ba lớp xếp chồng. Ý định đi từ lớp 1 xuống, được cấu trúc hoá, rồi được uỷ quyền ở lớp 2, rồi mới tới lớp 3 để chuyển tiền.

**Lớp 1: ý định và điều phối (intent and orchestration).** Đây là nơi mục tiêu bằng ngôn ngữ tự nhiên được diễn giải thành một kế hoạch có cấu trúc. Tác tử phân rã mục tiêu thành các bước, gọi công cụ, truy vấn dữ liệu và có thể gọi các tác tử khác. Hai giao thức đang hình thành: MCP (Model Context Protocol) để kết nối tác tử với công cụ và dữ liệu, và A2A (Agent-to-Agent) để tác tử trao đổi trực tiếp với nhau. Rủi ro ở lớp này gồm diễn giải sai ý định người dùng, tác tử bị "tiêm lệnh" (prompt injection, tức bị cài chỉ dẫn độc hại giấu trong nội dung nó đọc), và xung đột mục tiêu giữa các tác tử.

**Lớp 2: kiểm soát và uỷ quyền (control and authorization).** Đây là lớp mà bài coi là quyết định, nơi tập trung quyền lực và trách nhiệm. Nó trả lời các câu hỏi: tác tử này có quyền chi tiêu không, thay mặt ai, trong hạn mức nào, với thương nhân nào, phạm vi nào, hiệu lực đến khi nào. Công cụ gồm uỷ quyền có thể kiểm chứng bằng mật mã, token phạm vi hẹp, hạn mức, danh sách thương nhân được phép, và chữ ký số. Đây cũng là nơi tự nhiên để đặt KYA, kiểm tra chống rửa tiền, sàng lọc trừng phạt, giới hạn rủi ro và công tắc ngắt.

Các chuẩn đang cạnh tranh ở lớp này:

| Chuẩn | Bên đứng sau | Đặc điểm |
|---|---|---|
| UCP (Universal Commerce Protocol) | OpenAI và Stripe | Chuẩn thương mại tác tử, mua hàng ngay trong hội thoại |
| AP2 (Agent Payments Protocol) | Google | Chuẩn thanh toán tác tử mở cho bên thứ ba |
| x402 | | Hồi sinh mã trạng thái HTTP 402 ("cần thanh toán"), vốn có từ lâu nhưng chưa từng được dùng |
| ERC-1812, ERC-4337, ERC-6900, ERC-8004 | Cộng đồng Ethereum | Các chuẩn trên chuỗi khối Ethereum; ví dụ ERC-4337 cho phép ví lập trình được, ERC-8004 đề xuất danh tính và uy tín của tác tử |

**Lớp 3: quyết toán (settlement).** Việc chuyển giá trị thật diễn ra qua các kênh đã có: mạng thẻ, hệ thống chuyển khoản tức thời, tiền gửi token hoá, stablecoin hoặc CBDC. Phần lớn hạ tầng này đã tồn tại và vận hành tốt. Thách thức không phải xây mới mà là thích ứng với ba đòi hỏi: chi phí đơn vị thấp cho giao dịch siêu nhỏ, tính khả dụng 24/7, và khả năng đảo ngược khi tác tử sai.

**Luận điểm trung tâm.** Lớp 3 không phải điểm nghẽn. Ai thắng hay thua sẽ được quyết định ở lớp 2. Ai kiểm soát lớp uỷ quyền sẽ đặt ra luật chơi kinh tế của thương mại tác tử, và vì thế là đối tượng tự nhiên của quản lý nhà nước.

**Ai đang xây gì.** Cuộc cạnh tranh thương mại hiện nay đều nhắm vào lớp 2:

- **OpenAI và Stripe**: Universal Commerce Protocol, mua hàng ngay trong cuộc hội thoại với chatbot.
- **Amazon**: tác tử mua sắm gắn với danh mục hàng của chính Amazon.
- **Google**: Agent Payments Protocol (AP2), mở cho bên thứ ba.
- **Visa và Mastercard**: chương trình tác tử với token uỷ quyền gắn vào mạng thẻ hiện có.
- **PayPal**: bộ công cụ tác tử cho thương nhân.

Cuộc đua thực sự là giành lớp 2, không phải lớp 3: ai định nghĩa được chuẩn uỷ quyền tác tử sẽ định nghĩa được luật chơi.

### 3. Hành trình thanh toán được viết lại

Bài đi qua từng bước của một giao dịch để thấy mỗi bước thay đổi thế nào khi có tác tử:

| Bước | Trước đây | Với tác tử |
|---|---|---|
| Khởi tạo | Người dùng chọn sản phẩm và phương thức thanh toán | Tác tử nhận mục tiêu và tự chọn cả hai |
| Uỷ quyền | Xác thực hai yếu tố (mật khẩu cộng mã gửi về điện thoại) đúng lúc giao dịch | Hệ thống kiểm tra một chứng thư uỷ quyền đã cấp trước |
| Khớp lệnh và thương lượng | Gần như không có, người mua chấp nhận giá niêm yết | Tác tử bên mua thương lượng với tác tử bên bán |
| Quyết toán | Qua hạ tầng hiện có | Vẫn qua hạ tầng hiện có, nhưng giá trị nhỏ hơn, tần suất cao hơn, cần tức thời |
| Hậu giao dịch | Đối soát, tranh chấp, hoàn tiền theo quy trình quen thuộc | Phức tạp hơn vì phải truy ngược chuỗi quyết định của máy |

**Khởi tạo.** Việc chọn phương thức thanh toán trở thành một bài toán tối ưu hoá của máy, dựa trên chi phí, tốc độ, khả năng hoàn tiền và chương trình thưởng. Thẻ hay ví nào được dùng không còn do thói quen của người dùng quyết định.

**Uỷ quyền.** Chứng thư uỷ quyền cấp trước cần nêu rõ phạm vi, hạn mức, thời hạn, và danh tính của cả người uỷ quyền lẫn tác tử được uỷ quyền.

**Khớp lệnh và thương lượng.** Đây là bước hoàn toàn mới. Hai tác tử có thể thương lượng về giá, điều kiện giao hàng, bảo hiểm và chính sách huỷ. Giao dịch có thể được chia nhỏ, thử, huỷ và thử lại nhiều lần trước khi chốt.

**Quyết toán.** Tác tử cần quyết toán tức thời để biết giao dịch đã xong và tiếp tục bước tiếp theo trong kế hoạch.

**Hậu giao dịch.** Bài nhấn mạnh nhu cầu về nhật ký kiểm toán ghi lại không chỉ giao dịch mà cả lý do tác tử đưa ra quyết định đó, để khi có tranh chấp người ta biết nó đã "nghĩ" gì.

### 4. Rủi ro

Bài phân năm nhóm rủi ro, mỗi nhóm kèm hướng giảm thiểu.

**Rủi ro vận hành: lỗi nhân bản theo cấp số.** Rủi ro đặc trưng không phải là một loại lỗi mới, mà là tốc độ và quy mô. Một lỗi logic trong tác tử có thể nhân bản thành hàng nghìn giao dịch sai trong vài giây, trước khi bất kỳ ai kịp nhìn thấy. Ví dụ trong bài: tác tử hiểu sai "rẻ nhất" và đặt 400 vé không huỷ được. Giảm thiểu đòi hỏi hạn mức cứng nhiều tầng (theo giao dịch, theo ngày, theo thương nhân), giới hạn tốc độ, và công tắc ngắt ở ba cấp: cấp tác tử, cấp nhà cung cấp và cấp hệ thống.

**Rủi ro uỷ quyền và trách nhiệm: ai chịu khi tác tử sai?** Người dùng, nhà phát triển tác tử, nền tảng hay ngân hàng? Khung bảo vệ người tiêu dùng hiện hành giả định con người bấm nút: giao dịch không được uỷ quyền là giao dịch mà chủ tài khoản không thực hiện, và khi đó ngân hàng thường phải hoàn tiền. Nhưng khi tác tử hành động trong phạm vi được cấp mà cho ra kết quả người dùng không mong muốn, giao dịch đó có được uỷ quyền hay không vẫn là câu hỏi mở; khái niệm "giao dịch không được uỷ quyền" trở nên mơ hồ. Bài kêu gọi bằng chứng uỷ quyền kiểm toán được và phân định rõ trách nhiệm giữa người dùng, nhà phát triển tác tử, nền tảng và tổ chức tài chính, cả bằng hợp đồng lẫn bằng luật.

**Rủi ro tính toàn vẹn: cần KYA bên cạnh KYC.** Tác tử có thể bị chiếm quyền, bị giả mạo, hoặc bị dùng làm lớp che giấu chủ sở hữu hưởng lợi, tức người thật sự hưởng tiền. Giải pháp hướng tới danh tính tác tử có thể kiểm chứng, sổ đăng ký tác tử, và gắn mỗi tác tử với một chủ thể pháp lý chịu trách nhiệm.

**Rủi ro thị trường và cạnh tranh: tập trung hoá.** Nếu một số ít nền tảng kiểm soát cả lớp ý định lẫn lớp uỷ quyền, họ có thể để tác tử của mình tự ưu tiên hàng hoá của chính họ và dựng rào cản với đối thủ. Ngoài ra, khi nhiều tác tử dùng chung một mô hình nền và phản ứng giống nhau trước cùng một tín hiệu, hành vi bầy đàn và biến động giá đồng bộ có thể xuất hiện. Giảm thiểu: bắt buộc khả năng liên thông, chuẩn mở, và quyền chuyển đổi tác tử (người dùng mang uỷ quyền của mình sang tác tử khác).

**Rủi ro hệ thống và vĩ mô.** Nếu thương mại tác tử trở thành kênh thanh toán chính, sự cố ở một nhà cung cấp mô hình có thể lan ra toàn nền kinh tế: sự phụ thuộc vào vài nhà cung cấp tạo ra một điểm hỏng đơn lẻ mới. Rủi ro tập trung nhà cung cấp cần được giám sát như rủi ro hạ tầng quan trọng, kèm kiểm thử chịu đựng và yêu cầu về khả năng chống chịu vận hành.

### 5. Hàm ý chính sách

**Quản lý theo chức năng, không theo nhãn công nghệ.** Câu hỏi là hoạt động gì đang được thực hiện, không phải công nghệ gì đang thực hiện nó. Nếu một tác tử thực hiện hoạt động khởi tạo thanh toán, hoạt động đó nên chịu cùng nghĩa vụ như bất kỳ đơn vị khởi tạo thanh toán nào khác, dù là phần mềm hay con người.

**Đặt nghĩa vụ ở lớp uỷ quyền.** Đó là điểm duy nhất trong kiến trúc mà mọi giao dịch đều đi qua và nơi nghĩa vụ có thể thực thi được. Đặt nghĩa vụ ở lớp ý định là không khả thi, vì lớp đó phân tán và biến đổi quá nhanh. Đặt ở lớp quyết toán là quá muộn, vì khi đó quyết định đã được đưa ra.

**Dựa vào các khung đã có.** Khung quản trị AI tác tử của IMDA (Cơ quan Phát triển Truyền thông Thông tin Singapore) và Đạo luật AI của EU, với nghĩa vụ phân theo mức rủi ro và yêu cầu minh bạch với hệ thống tương tác với con người, đưa ra các nguyên tắc về minh bạch, giám sát của con người và phân loại rủi ro, có thể áp dụng vào bối cảnh thanh toán.

**Ba việc nên làm ngay.** Ngân hàng trung ương và cơ quan giám sát nên:

1. Xây năng lực kỹ thuật để hiểu và kiểm tra hệ thống tác tử.
2. Tham gia đặt chuẩn uỷ quyền ngay khi các chuẩn còn đang hình thành, thay vì tiếp nhận chuẩn đã cố định do tư nhân đặt.
3. Làm rõ trách nhiệm pháp lý trước khi khối lượng giao dịch tác tử đủ lớn để gây sự cố hệ thống.

**Thời điểm là bây giờ.** Bài kết luận rằng phải hành động khi chuẩn còn mềm dẻo. Một khi kiến trúc uỷ quyền đông cứng lại quanh các lựa chọn thương mại của vài nền tảng, việc sửa lại sẽ tốn kém hơn nhiều.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Agentic AI | AI tác tử, hệ thống tự lập kế hoạch và hành động để đạt mục tiêu được giao |
| Click-to-pay | Mô hình cũ, mỗi giao dịch cần một hành động bấm xác nhận của con người |
| Decide-to-pay | Mô hình mới, con người uỷ quyền trước, tác tử tự quyết định giao dịch cụ thể |
| Intent layer | Lớp ý định, nơi mục tiêu con người được diễn giải thành kế hoạch hành động |
| Orchestration | Điều phối, việc tác tử phân rã mục tiêu và gọi công cụ hoặc tác tử khác |
| Authorization layer | Lớp uỷ quyền, nơi kiểm tra quyền chi tiêu và áp dụng hạn mức, lớp trung tâm |
| Settlement layer | Lớp quyết toán, nơi giá trị thật sự chuyển giao |
| MCP | Model Context Protocol, chuẩn kết nối tác tử với công cụ và nguồn dữ liệu |
| A2A | Agent-to-Agent, giao thức cho tác tử trao đổi trực tiếp với nhau |
| UCP | Universal Commerce Protocol, chuẩn thương mại tác tử của OpenAI và Stripe |
| AP2 | Agent Payments Protocol, chuẩn thanh toán tác tử của Google |
| x402 | Giao thức thanh toán dựa trên mã trạng thái HTTP 402 vốn chưa từng dùng |
| ERC-4337 | Chuẩn trừu tượng hoá tài khoản trên Ethereum, cho phép ví lập trình được |
| ERC-8004 | Chuẩn đề xuất về danh tính và uy tín của tác tử trên chuỗi |
| Verifiable credential | Chứng thư có thể kiểm chứng bằng mật mã, dùng làm bằng chứng uỷ quyền |
| Scoped token | Token phạm vi hẹp, giới hạn tác tử theo số tiền, thương nhân và thời hạn |
| KYA | Know Your Agent, biết tác tử của bạn, bổ sung cho KYC truyền thống |
| Kill switch | Công tắc ngắt, cơ chế dừng khẩn cấp hoạt động của tác tử |
| Micropayment | Vi thanh toán, giao dịch giá trị rất nhỏ mà tác tử tạo ra với tần suất cao |
| Embedded payments | Thanh toán nhúng, tích hợp vào ứng dụng khác nên người dùng không thấy |
| Herding behavior | Hành vi bầy đàn, nhiều tác tử phản ứng giống nhau gây biến động đồng bộ |
| Concentration risk | Rủi ro tập trung, phụ thuộc vào ít nhà cung cấp mô hình nền |
| Auditability | Khả năng kiểm toán, truy vết được ai uỷ quyền và vì sao tác tử quyết định vậy |
| EU AI Act | Đạo luật AI của EU, phân loại nghĩa vụ theo mức rủi ro của hệ thống |
| IMDA | Cơ quan Phát triển Truyền thông Thông tin Singapore, ban hành khung AI tác tử |

## Câu nói đáng nhớ

> "The shift is from click-to-pay to decide-to-pay."

> "The competition is not for the settlement rails. It is for the authorization layer."

> "The risk is not that machines make mistakes humans would not. It is that they make them faster than humans can intervene."

## Đánh giá và phát hiện đáng chú ý

### Sự đồng ý đổi từ một khoảnh khắc thành một chính sách, và đó là thay đổi lớn hơn mọi thứ khác trong bài

Bài mô tả rất kỹ việc sự đồng ý bị tách khỏi thời điểm chuyển tiền, nhưng chưa gọi tên đúng bản chất của điều đang xảy ra. Đây không phải là sự đồng ý bị dịch chuyển về trước. Đây là sự đồng ý **đổi loại**.

Trong toàn bộ lịch sử thanh toán, sự đồng ý là một **sự kiện**: một chữ ký, một mã PIN, một cú bấm. Nó có một thời điểm xác định, một nội dung xác định, và một số tiền xác định. Mọi khái niệm pháp lý của ngành — giao dịch không được uỷ quyền, nghĩa vụ chứng minh, quyền đòi lại tiền, thời hạn khiếu nại — đều được xây trên giả định rằng tồn tại một sự kiện như vậy để đối chiếu.

Trong mô hình tác tử, sự đồng ý trở thành một **bộ quy tắc**: một phạm vi, một hạn mức, một danh sách đối tác, một thời hạn. Nó không còn là sự kiện mà là chính sách. Và một chính sách thì không thể so sánh với một giao dịch cụ thể theo cách nhị phân đúng hay sai; nó chỉ có thể được diễn giải.

Điều đáng chú ý là ngành luật đã có sẵn một bộ khái niệm cho đúng tình huống này, chỉ có điều nó không nằm trong luật thanh toán. Đó là luật về **đại diện và uỷ quyền**: quan hệ giữa người uỷ quyền và người được uỷ quyền, phạm vi thẩm quyền biểu kiến, nghĩa vụ trung thành của bên được uỷ quyền. Bộ khái niệm này cổ hơn thẻ tín dụng hàng thế kỷ và đã xử lý đúng câu hỏi "ai chịu khi người đại diện hành động trong phạm vi nhưng ra kết quả xấu".

Bài lại đi tìm lời giải ở phía kỹ thuật — chứng thư kiểm chứng được bằng mật mã, token phạm vi hẹp, danh tính tác tử. Những thứ đó cần thiết nhưng chúng chỉ ghi lại phạm vi, không quyết định ai chịu tổn thất khi phạm vi được tôn trọng mà kết quả vẫn sai. Có một lý do khiến không ai muốn nhắc tới luật đại diện ở đây: câu trả lời mặc định của nó là **người uỷ quyền chịu**. Áp dụng thẳng nguyên tắc đó nghĩa là đẩy toàn bộ rủi ro tác tử sang người tiêu dùng, điều không ai muốn nói ra nhưng cũng chưa ai bác bỏ bằng một lập luận rõ ràng.

### Luận điểm "quyền lực tập trung ở lớp hai" có thể đúng vì lý do sai

Bài lập luận rằng lớp uỷ quyền là nơi quyền lực kinh tế tập trung, vì đó là điểm mà mọi giao dịch phải đi qua. Nhưng chính dòng thời gian bốn thập niên trong bài lại kể một câu chuyện khác.

Trong mọi làn sóng trước, giá trị không chảy về điểm nghẽn kỹ thuật mà chảy về **bên sở hữu giao diện với người dùng**. Mạng thẻ là điểm nghẽn bắt buộc của mọi giao dịch thẻ, nhưng phần thặng dư và quyền định hình sản phẩm lại dịch dần về phía ví trên điện thoại và nút thanh toán trên trang bán hàng. Ai đứng ở chỗ người dùng nhìn vào thì người đó đặt luật; ai đứng ở chỗ bắt buộc phải đi qua thì người đó bị quản lý và bị ép biên lợi nhuận.

Trong kiến trúc của bài, giao diện với người dùng là **lớp một**, không phải lớp hai. Danh sách các bên đang cạnh tranh cũng ủng hộ cách đọc này: hai bên có vị thế mạnh nhất là bên sở hữu cuộc hội thoại với người dùng và bên sở hữu danh mục hàng hoá. Họ đi từ lớp một xuống. Mạng thẻ thì đi từ lớp hai lên, và đó là tư thế của bên đang phòng thủ chứ không phải bên đang chiếm lĩnh.

Bài gộp hai câu hỏi khác nhau vào một kết luận: "nơi đặt nghĩa vụ quản lý hiệu quả nhất" và "nơi quyền lực kinh tế tập trung". Câu trả lời thứ nhất gần như chắc chắn là lớp hai — nó là điểm duy nhất có thể thực thi được. Câu trả lời thứ hai có lẽ là lớp một. Nếu vậy thì kết cục khả dĩ nhất là lớp hai trở thành hạ tầng bị quản lý chặt và biên lợi nhuận mỏng, trong khi phần tô nằm ở lớp trên — tức là chính mô thức đã xảy ra với ngành thanh toán trong hai mươi năm qua. Đó không phải tin xấu cho cơ quan quản lý, nhưng nó có nghĩa là đặt nghĩa vụ ở lớp hai sẽ **không** chạm tới nơi có quyền lực thật.

### Một rủi ro bài bỏ trống hoàn toàn: thương lượng máy với máy không phải là trò chơi trung lập

Bài mô tả việc tác tử bên mua thương lượng với tác tử bên bán như một bước mới trong hành trình giao dịch, với giọng trung tính. Nhưng kinh tế học của thương lượng song phương giữa hai bên có thông tin bất đối xứng thì không trung tính chút nào.

Người mua dùng một tác tử phổ thông, được huấn luyện chung, không biết gì riêng về người bán. Người bán thì có lịch sử giao dịch của chính mình, mô hình định giá riêng, dữ liệu về độ co giãn cầu theo từng phân khúc, và động cơ để đầu tư vào một tác tử chuyên biệt vì mỗi phần trăm biên lợi nhuận nhân với toàn bộ doanh số. Khi hai tác tử này gặp nhau lặp đi lặp lại, bên có nhiều dữ liệu và nhiều động cơ đầu tư hơn sẽ **học được hàm phản ứng của bên kia**.

Kết quả nhiều khả năng không phải là người tiêu dùng mua được rẻ hơn, mà là **phân biệt giá trở nên hoàn hảo hơn**: mỗi người mua bị tính đúng mức giá cao nhất mà tác tử của họ sẽ chấp nhận. Đây là sự dịch chuyển thặng dư từ người mua sang người bán, được thực hiện bởi chính công cụ được quảng cáo là giúp người mua.

Phần cạnh tranh của bài lo về việc nền tảng tự ưu tiên hàng hoá của mình, đó là mối lo đúng nhưng là mối lo cũ, đã có công cụ chống độc quyền để xử lý. Kênh phân biệt giá qua thương lượng máy thì mới, khó phát hiện vì mỗi giao dịch đều có vẻ hợp lý khi xét riêng, và không có công cụ pháp lý nào đang nhắm vào nó.

Liên quan chặt tới điều này là rủi ro tiêm lệnh, bài có nhắc ở lớp một nhưng chỉ như một mục trong danh sách. Hàm ý của nó lớn hơn thế: khi tác tử của người mua phải đọc văn bản do người bán kiểm soát — mô tả sản phẩm, trang web, thư điện tử, điều khoản — thì **mọi ký tự do đối phương viết ra đều là một bề mặt tấn công nhắm thẳng vào ví tiền**. Kẻ tấn công không cần xâm nhập hệ thống nào cả; họ chỉ cần được tác tử đọc.

### Khẳng định "lớp quyết toán không phải điểm nghẽn" mâu thuẫn với chính dự báo của bài

Bài nói hạ tầng quyết toán phần lớn đã tồn tại và hoạt động tốt, thách thức chỉ là thích ứng. Nhưng bài cũng dự báo số lượng giao dịch tăng vọt trong khi giá trị mỗi giao dịch giảm mạnh, vì tác tử chia nhỏ, thử, huỷ và thử lại.

Hai mệnh đề này khó cùng đúng. Lý do nằm ở **cấu trúc chi phí cố định của tuân thủ**, chứ không nằm ở năng lực xử lý kỹ thuật. Mỗi giao dịch, dù trị giá một đô hay một xu, đều phải qua sàng lọc danh sách trừng phạt, kiểm tra chống rửa tiền, ghi nhận, đối soát và lưu trữ. Những chi phí này gần như không giảm theo giá trị giao dịch. Nếu khối lượng tăng một trăm lần, chi phí tuân thủ tăng xấp xỉ một trăm lần, trong khi doanh thu trên mỗi giao dịch giảm.

Nghĩa là điểm nghẽn thật không ở khả năng chuyển tiền mà ở **khả năng tuân thủ trên mỗi đơn vị giao dịch**, và nó nằm đúng ở ranh giới giữa lớp hai và lớp ba. Điều này lại củng cố kết luận của bài về tầm quan trọng của lớp uỷ quyền, nhưng bằng một lập luận mạnh hơn và cụ thể hơn lập luận mà bài đưa ra: lớp hai quan trọng vì nó là nơi duy nhất có thể **sàng lọc một lần cho nhiều giao dịch**, thay vì sàng lọc từng giao dịch một. Ai giải được bài toán đó sẽ quyết định kinh tế học của toàn bộ thương mại tác tử.

### Phần sẽ lỗi thời nhanh nhất và phần sẽ còn đúng lâu

Danh sách giao thức là phần dễ hỏng nhất của tài liệu. Một cuộc đua chuẩn ở giai đoạn có sáu, bảy ứng viên cùng lúc hầu như luôn kết thúc với một hoặc hai chuẩn sống sót, thường là chuẩn được hậu thuẫn bởi bên có sẵn khối lượng giao dịch chứ không phải chuẩn tốt nhất về kỹ thuật. Nên đọc danh sách này như một bức ảnh chụp **ai đang tranh giành ở thời điểm 2026**, không phải như mô tả về hạ tầng tương lai. Tương tự, việc phân định ranh giới giữa các lớp sẽ dịch chuyển: các bên sẽ cố gộp lớp một và lớp hai, vì gộp được thì kiểm soát được cả ý định lẫn quyền chi.

Phần bền là ba thứ. Thứ nhất là **phép phân rã ba lớp** — nó đúng vì nó phản ánh ba câu hỏi khác nhau về bản chất: muốn gì, có được phép không, tiền đi bằng đường nào. Thứ hai là việc **tách sự đồng ý, danh tính và uỷ quyền** thành ba thứ riêng biệt, vốn từng trùng nhau trong một cú bấm; sự tách rời này sẽ không quay lại. Thứ ba là nguyên lý về **tốc độ lỗi**: khi hành động nhanh hơn khả năng can thiệp, biện pháp kiểm soát duy nhất còn hiệu lực là biện pháp đặt trước và tự động, tức hạn mức cứng và công tắc ngắt. Nguyên lý này giống hệt bài học của các sự cố giao dịch thuật toán trên thị trường chứng khoán, và nó gợi ý rằng ngành thanh toán nên mượn thẳng bộ công cụ đã được dùng ở đó thay vì phát minh lại: ngắt mạch, giới hạn tốc độ lệnh, và ngưỡng dừng bắt buộc.

### Với Việt Nam: một lợi thế hạ tầng thật và một điểm yếu ít ai nhận ra

Lợi thế trước. Thương mại tác tử cần một lớp quyết toán rẻ ở mức giao dịch nhỏ. Ở các nền kinh tế dựa vào thẻ, mỗi giao dịch mang một mức phí cố định khiến vi thanh toán không khả thi về kinh tế. Việt Nam thì đã có chuyển khoản tức thời hoạt động hai bốn trên bảy với chi phí ở phía người dùng gần bằng không, cộng với mã quét phủ tới người bán rất nhỏ. Xét thuần tuý về hạ tầng, đây là nền quyết toán phù hợp cho thương mại tác tử hơn phần lớn nước phát triển — một trường hợp lợi thế của người đi sau.

Điểm yếu nằm ở chính đặc tính vừa nêu. Chuyển khoản tức thời là giao dịch **đẩy và chung thẩm**: tiền đi là đi, không có cơ chế đòi lại kiểu tranh chấp thẻ, không có bên trung gian đứng ra tạm giữ. Bài nêu "khả năng đảo ngược" như một trong các thách thức thích ứng của lớp ba, nhưng với một nền kinh tế dựa vào chuyển khoản tức thời thì đây không phải một thách thức trong số nhiều thách thức — nó là ràng buộc quyết định. Khi bên trả tiền là một cái máy có thể sai hàng nghìn lần trong vài giây, mà đường ray lại không có nút hoàn tác, thì toàn bộ gánh nặng an toàn dồn lên lớp uỷ quyền. Hạn mức cứng theo ngày, theo đối tác và theo giao dịch không phải là biện pháp bổ sung mà là biện pháp duy nhất.

Một lợi thế thứ hai ít được nhắc: khái niệm "biết tác tử của bạn" đòi hỏi mỗi tác tử phải gắn được với một chủ thể pháp lý chịu trách nhiệm. Việt Nam đã có hệ thống định danh điện tử quốc gia phủ rộng và đã gắn với tài khoản ngân hàng. Đây chính là nguyên liệu mà phần lớn nước khác còn đang thiếu để xây sổ đăng ký tác tử. Việc đáng làm sớm, và rẻ, là quy định rằng mọi uỷ quyền chi tiêu cho phần mềm phải truy được về một danh tính đã định danh — làm trước khi khối lượng đủ lớn, đúng như bài khuyến nghị, vì sửa một kiến trúc đã đông cứng thì tốn kém hơn nhiều.

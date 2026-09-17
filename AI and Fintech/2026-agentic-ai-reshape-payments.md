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

## Dàn ý chi tiết

### 1. Vì sao lần này khác

- Bốn thập niên qua, thanh toán liên tục bị gỡ bỏ các bước trung gian: thẻ và ATM tách thanh toán khỏi quầy giao dịch, thương mại điện tử tách nó khỏi cửa hàng vật lý, ví điện tử tách khỏi thẻ nhựa, di động và mã QR tách khỏi thiết bị đầu cuối, thanh toán nhúng tách khỏi chính hành vi thanh toán có ý thức.
- Mỗi làn sóng đó vẫn giữ nguyên một điểm cố định: tại thời điểm tiền chuyển đi, một con người đã ra quyết định. AI tác tử gỡ bỏ chính điểm cố định ấy. Đó là lý do bài gọi bước chuyển này là từ "click-to-pay" sang "decide-to-pay".
- Hệ quả pháp lý sâu xa: trong mô hình cũ, sự đồng ý, việc xác thực danh tính và việc uỷ quyền chi tiêu hội tụ tại một cú bấm. Trong mô hình mới, ba thứ đó tách rời nhau cả về thời gian lẫn phạm vi. Người dùng đồng ý với một dải kết quả có thể xảy ra, trước khi biết giao dịch cụ thể sẽ là gì.
- Điều này đặt lại câu hỏi trung tâm của toàn bộ ngành thanh toán. Câu hỏi không còn là "ai đã bấm nút" mà là "ai đã uỷ quyền cho giao dịch này, trong phạm vi nào, và có bằng chứng gì".

### 2. Mô hình ba lớp

- **Lớp ý định và điều phối.** Đây là nơi mục tiêu bằng ngôn ngữ tự nhiên được chuyển thành một kế hoạch có cấu trúc. Tác tử phân rã mục tiêu thành các bước, gọi công cụ, truy vấn dữ liệu và có thể gọi các tác tử khác. Giao thức đang hình thành gồm Model Context Protocol để kết nối tác tử với công cụ và dữ liệu, và Agent-to-Agent để tác tử trao đổi với nhau.
- **Lớp kiểm soát và uỷ quyền.** Đây là lớp mà bài coi là quyết định. Nó trả lời các câu hỏi: tác tử này có được phép chi tiêu không, thay mặt ai, trong hạn mức nào, với thương nhân nào, hiệu lực đến khi nào. Công cụ gồm uỷ quyền có thể kiểm chứng bằng mật mã, token phạm vi hẹp và chữ ký số. Đây cũng là nơi tự nhiên để đặt kiểm tra chống rửa tiền, sàng lọc trừng phạt, giới hạn rủi ro và công tắc ngắt.
- **Lớp quyết toán.** Việc chuyển giá trị thật diễn ra qua các kênh đã có: mạng thẻ, hệ thống thanh toán tức thời, tiền gửi token hoá, stablecoin hoặc CBDC. Phần lớn hạ tầng này đã tồn tại và vận hành tốt. Thách thức không phải là xây mới mà là thích ứng với khối lượng lớn giao dịch giá trị nhỏ, tính khả dụng liên tục và khả năng đảo ngược khi tác tử sai.
- Bài nhấn mạnh rằng cuộc cạnh tranh thương mại hiện nay, thể hiện qua các sáng kiến của OpenAI cùng Stripe, Amazon, Google, Visa, Mastercard và PayPal, đều nhắm vào lớp thứ hai. Ai định nghĩa được chuẩn uỷ quyền tác tử sẽ định nghĩa được luật chơi kinh tế của thương mại tác tử.

### 3. Hành trình thanh toán được viết lại

- **Khởi tạo.** Thay vì người dùng chọn sản phẩm và phương thức, tác tử nhận mục tiêu và tự chọn cả hai. Việc chọn phương thức thanh toán trở thành một quyết định tối ưu hoá của máy, dựa trên chi phí, tốc độ, khả năng hoàn tiền và chương trình thưởng.
- **Uỷ quyền.** Thay vì xác thực hai yếu tố tại thời điểm giao dịch, hệ thống kiểm tra một chứng thư uỷ quyền đã được cấp trước. Chứng thư này cần nêu rõ phạm vi, hạn mức, thời hạn và danh tính của cả người uỷ quyền lẫn tác tử được uỷ quyền.
- **Khớp lệnh và thương lượng.** Đây là bước hoàn toàn mới. Tác tử bên mua có thể thương lượng với tác tử bên bán về giá, điều kiện giao hàng, bảo hiểm và chính sách huỷ. Giao dịch có thể được chia nhỏ, thử, huỷ và thử lại nhiều lần trước khi chốt.
- **Quyết toán.** Giá trị chuyển đi qua hạ tầng hiện có, nhưng với đặc điểm mới: giá trị nhỏ hơn, tần suất cao hơn, và nhu cầu quyết toán tức thời để tác tử có thể tiếp tục bước tiếp theo.
- **Hậu giao dịch.** Đối soát, tranh chấp và hoàn tiền trở nên phức tạp hơn vì phải truy ngược qua chuỗi quyết định của máy. Bài nhấn mạnh nhu cầu về nhật ký kiểm toán ghi lại không chỉ giao dịch mà cả lý do tác tử đưa ra quyết định đó.

### 4. Rủi ro

- **Vận hành.** Rủi ro đặc trưng không phải là lỗi mới về bản chất, mà là tốc độ và quy mô. Một lỗi logic trong tác tử có thể nhân bản thành hàng nghìn giao dịch sai trong vài giây, trước khi bất kỳ con người nào kịp nhìn thấy. Giảm thiểu đòi hỏi hạn mức cứng nhiều tầng, giới hạn tốc độ và công tắc ngắt ở cấp tác tử, cấp nhà cung cấp và cấp hệ thống.
- **Uỷ quyền và trách nhiệm.** Khung bảo vệ người tiêu dùng hiện hành xây trên giả định rằng giao dịch không được uỷ quyền là giao dịch mà chủ tài khoản không thực hiện. Khi tác tử hành động trong phạm vi được cấp nhưng đưa ra kết quả người dùng không mong muốn, giao dịch đó được uỷ quyền hay không vẫn là câu hỏi mở. Bài kêu gọi làm rõ phân định trách nhiệm giữa người dùng, nhà phát triển tác tử, nền tảng và tổ chức tài chính.
- **Tính toàn vẹn.** Bên cạnh biết khách hàng của bạn, cần khái niệm biết tác tử của bạn. Tác tử có thể bị chiếm quyền, bị giả mạo, hoặc bị dùng làm lớp che giấu chủ sở hữu hưởng lợi. Giải pháp hướng tới danh tính tác tử có thể kiểm chứng và việc gắn mỗi tác tử với một chủ thể pháp lý chịu trách nhiệm.
- **Cạnh tranh.** Nếu một số ít nền tảng kiểm soát cả lớp ý định lẫn lớp uỷ quyền, họ có thể tự ưu tiên sản phẩm của mình và dựng rào cản. Ngoài ra, khi nhiều tác tử dùng chung một mô hình nền và phản ứng giống nhau trước cùng một tín hiệu, hành vi bầy đàn và biến động giá đồng bộ có thể xuất hiện.
- **Hệ thống.** Nếu thương mại tác tử trở thành kênh chủ đạo, sự phụ thuộc vào một số ít nhà cung cấp mô hình tạo ra điểm hỏng đơn lẻ mới cho toàn nền kinh tế. Rủi ro tập trung nhà cung cấp cần được giám sát như rủi ro hạ tầng quan trọng.

### 5. Hàm ý chính sách

- Quản lý nên theo chức năng kinh tế chứ không theo nhãn công nghệ. Nếu một tác tử thực hiện hoạt động khởi tạo thanh toán, hoạt động đó nên chịu cùng nghĩa vụ như bất kỳ đơn vị khởi tạo nào khác, bất kể nó là phần mềm hay con người.
- Nghĩa vụ nên được đặt ở lớp uỷ quyền, vì đó là điểm duy nhất trong kiến trúc mà mọi giao dịch đều đi qua và có thể thực thi được. Đặt nghĩa vụ ở lớp ý định là không khả thi vì lớp đó phân tán và biến đổi nhanh; đặt ở lớp quyết toán là quá muộn.
- Các sáng kiến hiện có cung cấp điểm tựa. Khung quản trị AI tác tử của cơ quan IMDA Singapore và Đạo luật AI của EU đưa ra nguyên tắc về minh bạch, giám sát của con người và phân loại theo mức rủi ro, có thể được áp dụng vào bối cảnh thanh toán.
- Ngân hàng trung ương và cơ quan giám sát nên bắt đầu ngay ba việc: xây năng lực kỹ thuật để hiểu và kiểm tra hệ thống tác tử; tham gia vào quá trình đặt chuẩn uỷ quyền khi các chuẩn còn đang hình thành thay vì tiếp nhận chuẩn đã cố định; và làm rõ trách nhiệm pháp lý trước khi khối lượng giao dịch tác tử đủ lớn để gây sự cố hệ thống.
- Bài kết luận rằng thời điểm hành động là bây giờ, khi chuẩn còn mềm dẻo. Một khi kiến trúc uỷ quyền đông cứng lại quanh các lựa chọn thương mại của vài nền tảng, việc sửa lại sẽ tốn kém hơn nhiều.

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

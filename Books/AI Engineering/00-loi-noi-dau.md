# Lời nói đầu, Lời kết và Về tác giả (Preface, Epilogue, About the Author)

**Nguồn:** Chip Huyen, *AI Engineering: Building Applications with Foundation Models*, O'Reilly Media, ấn bản đầu tiên (12/2024), phần "Preface" (trang PDF 9–31, gồm ba chú thích ở trang PDF 31), "Epilogue" (trang PDF 930–931), "About the Author" (trang PDF 989) và "Colophon" (trang PDF 990–991).
**Tác giả:** Chip Huyen — nhà văn và nhà khoa học máy tính chuyên về hệ thống học máy; từng làm ở NVIDIA, Snorkel AI, sáng lập một startup hạ tầng AI (sau được mua lại), dạy hệ thống học máy ở Đại học Stanford; tác giả *Designing Machine Learning Systems* (O'Reilly 2022) và bốn sách tiếng Việt bán chạy, trong đó có bộ *Xách ba lô lên và đi*.
**Vị trí trong lập luận của cả cuốn sách:** Lời nói đầu đặt khung cho toàn bộ cuốn sách: nó giải thích vì sao cần một ngành "AI engineering" (kỹ thuật xây dựng ứng dụng trên mô hình nền tảng), tác giả chọn nội dung theo tiêu chí nào (cái gì sẽ còn dùng được lâu), sách dành cho ai, và — trong mục "Navigating This Book" — sắp mười chương theo đúng trình tự của quy trình phát triển một ứng dụng AI: quyết định có nên làm ([Chương 1](C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md)), hiểu mô hình ([Chương 2](C02-hieu-ve-mo-hinh-nen-tang.md)), đánh giá ([Chương 3](C03-phuong-phap-danh-gia.md), [Chương 4](C04-danh-gia-he-thong-ai.md)), cải thiện chất lượng qua chỉ dẫn, context và chính mô hình ([Chương 5](C05-prompt-engineering.md), [Chương 6](C06-rag-va-agent.md), [Chương 7](C07-finetuning.md), [Chương 8](C08-ky-thuat-du-lieu.md)), làm suy luận rẻ và nhanh hơn ([Chương 9](C09-toi-uu-suy-luan.md)), rồi ghép tất cả thành kiến trúc hoàn chỉnh có vòng phản hồi người dùng ([Chương 10](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md)). Lời kết khép lại cuốn sách sau Chương 10; Về tác giả và Colophon là phần phụ cuối sách.
**Ý chính:** **Mô hình nền tảng làm bùng nổ số ứng dụng AI và hạ thấp rào cản gia nhập, nhưng xây ứng dụng tốt vẫn cần một quy trình kỹ thuật có hệ thống — kết hợp các thực hành đã kiểm chứng của học máy truyền thống với các kỹ thuật mới sinh ra cùng mô hình nền tảng — và cuốn sách trình bày quy trình đó theo nền tảng thay vì theo công cụ.** Tác giả kể rằng khi ChatGPT ra đời, điều làm bà bất ngờ không phải kích thước hay năng lực của mô hình (cộng đồng AI đã biết từ hơn mười năm rằng mô hình lớn hơn thì tốt hơn; bài báo AlexNet năm 2012 đã nói kết quả sẽ tốt lên chỉ nhờ GPU nhanh hơn và dữ liệu lớn hơn) mà là số lượng ứng dụng mà bước nhảy năng lực ấy mở ra. Sách là khung (framework) để điều chỉnh mô hình nền tảng — gồm mô hình ngôn ngữ lớn (LLM) và mô hình đa phương thức lớn (LMM) — cho ứng dụng cụ thể, trả lời các câu hỏi như có nên xây ứng dụng không, đánh giá ra sao, vì sao có hallucination, khi nào finetune, cần bao nhiêu dữ liệu, làm mô hình nhanh và rẻ hơn thế nào. Tác giả viết trong hai năm (khoảng 150.000 từ), dựa trên ghi chép từ hơn 100 cuộc trò chuyện và phỏng vấn, và chọn nội dung theo ba tiêu chí: vấn đề có xuất phát từ giới hạn căn bản của AI hay sẽ biến mất khi mô hình tốt hơn; ý kiến của mạng lưới nhà nghiên cứu và kỹ sư; và Định luật Lindy (công nghệ càng tồn tại lâu thì càng có khả năng tồn tại tiếp). Sách không phải sách hướng dẫn dùng công cụ, cũng không phải sách lý thuyết học máy; người đọc không cần nền học máy, nhưng biết các khái niệm xác suất, học máy, kiến trúc mạng nơ-ron và các thước đo cơ bản sẽ làm việc hiệu quả hơn. Lời kết thống kê sách có hơn 150.000 từ, 160 hình minh hoạ, 250 chú thích và 975 đường dẫn tham khảo, và nhắc rằng phần khó nhất của viết kỹ thuật là đặt đúng câu hỏi. Colophon cho biết con vật trên bìa là cú Oman (*Strix butleri*).

> **Lưu ý:**
> - **Lời kết mở đầu bằng câu "This is some text." (trang PDF 930):** đây rõ ràng là chữ giữ chỗ (placeholder) còn sót lại từ bản dàn trang, không có nội dung; ảnh trang xác nhận câu này được in thật trên trang, không phải lỗi trích xuất lớp chữ.
> - **Địa chỉ liên hệ trong Lời kết:** sách viết "email at https://huyenchip.com/communication", nhưng đó là một trang web chứ không phải địa chỉ email; Lời nói đầu (trang PDF 11) cho địa chỉ email thật là hi@huyenchip.com.
> - **Tên bộ sách tiếng Việt** trong About the Author được in không dấu: "Xach ba lo len va Di"; tên đúng là *Xách ba lô lên và đi*.
> - **Colophon kéo dài sang trang PDF 991** (tình trạng bảo tồn theo IUCN, người vẽ bìa, phông chữ), không chỉ trang PDF 990.
> - **Bố cục của bản chuyển ePub:** khung bên "Reading AI Engineering (AIE) with Designing Machine Learning Systems (DMLS)" (trang PDF 14) bị chèn vào giữa mục "What This Book Is About", ngay trước đoạn "Determining whether something will last…"; đoạn này thật ra nối tiếp câu "Tools become outdated quickly, but fundamentals should last longer" ở trang PDF 13. Bản tổng hợp đọc theo mạch ý: tiêu chí "cái gì sẽ còn lâu" đi liền sau câu về nền tảng và công cụ.
> - **Chú thích:** lớp chữ mất số thứ tự; ảnh trang PDF 9 và 13 cho thấy chú thích 1 và 2 cùng gắn sau câu trích bài báo AlexNet, chú thích 3 gắn sau câu "fundamentals should last longer". Bản tổng hợp đưa nội dung ba chú thích vào đúng chỗ.
> - **Mục "Navigating This Book" không gọi tên số "Chương 8" ở lần đầu** ("The next chapter is all about data"), rồi mới nhắc "Chapter 8" ở câu sau; Chương 10 được gọi là "The last chapter". Bản tổng hợp ghi đủ số chương.
> - **Quy ước dịch:** "foundation model" dịch là *mô hình nền tảng*; "AI engineering" giữ tiếng Anh khi nói tên ngành (giải thích là kỹ thuật xây dựng ứng dụng AI trên mô hình nền tảng), "AI engineer" là *kỹ sư AI*; "ML engineering" là *kỹ thuật học máy*. Các thuật ngữ prompt, context, RAG, agent, finetuning, hallucination, latency giữ tiếng Anh.
> - **Theo hiểu biết của người tổng hợp:** startup hạ tầng AI mà tác giả sáng lập là Claypot AI (xử lý dữ liệu thời gian thực), được Voltron Data mua lại năm 2023; sách không nêu tên. Ilya Sutskever (đồng tác giả AlexNet, được nhắc ở chú thích 1) đã rời OpenAI vào tháng 5/2024 và lập công ty Safe Superintelligence; sách chỉ nói ông "đồng sáng lập OpenAI", điều này vẫn đúng.

## Sơ đồ

### Preface, phần mở đầu — vì sao tác giả viết cuốn sách (Preface, trang PDF 9–11)

```text
       Khi ChatGPT ra đời, tác giả (như nhiều đồng nghiệp) bị choáng
                                │
                                ▼
       Điều KHÔNG làm bà bất ngờ: mô hình lớn hơn thì giỏi hơn
       · cộng đồng AI biết điều này hơn mười năm
       · AlexNet (2012): kết quả sẽ tốt lên chỉ nhờ chờ GPU nhanh hơn
         và tập dữ liệu lớn hơn
       · chú thích: Ilya Sutskever, đồng tác giả AlexNet, sau đồng sáng
         lập OpenAI và biến bài học này thành các mô hình GPT
       · chú thích: dự án nhỏ năm 2017 của tác giả (dùng mô hình ngôn
         ngữ đánh giá chất lượng bản dịch) cũng kết luận cần "một mô
         hình ngôn ngữ tốt hơn"
                                │
                                ▼
       Điều LÀM bà bất ngờ: số ứng dụng mà bước nhảy năng lực mở ra
       · tưởng chất lượng tăng ít thì ứng dụng tăng vừa phải; thực tế
         là bùng nổ khả năng mới
       · nhu cầu ứng dụng AI tăng; rào cản gia nhập giảm (có thể xây
         ứng dụng mà không viết dòng code nào)
       · AI chuyển từ ngành chuyên sâu thành công cụ ai cũng dùng được
                                │
                                ▼
       Nhưng nền móng không mới:
       · bài báo về mô hình hoá ngôn ngữ có từ thập niên 1950
       · RAG dựa trên công nghệ truy xuất của hệ thống tìm kiếm và gợi ý
       · thực hành tốt của học máy truyền thống vẫn đúng: thử nghiệm có
         hệ thống, đánh giá chặt, tối ưu không ngừng cho mô hình nhanh
         hơn và rẻ hơn
                                │
                                ▼
       Quen thuộc nhưng không phải không có gì mới: quy mô và năng lực
       của mô hình tạo cơ hội và thách thức cần giải pháp mới
                                │
                                ▼
       Sách bao quát trọn quy trình điều chỉnh mô hình nền tảng để giải
       bài toán thật: kỹ thuật đã kiểm chứng từ các ngành kỹ thuật khác
       cộng kỹ thuật mới sinh ra cùng mô hình nền tảng
       · nguồn: dự án tác giả làm, bài báo, hơn 100 cuộc trò chuyện và
         phỏng vấn (phòng thí nghiệm AI lớn, nhà phát triển framework,
         lãnh đạo, quản lý sản phẩm, nhà phát triển độc lập)
       · người đọc sớm và hàng nghìn bình luận trên blog của tác giả
       · mời góp ý qua X, LinkedIn, email hi@huyenchip.com
```

### What This Book Is About — sách bàn về điều gì và chọn nội dung thế nào (What This Book Is About, trang PDF 12–15)

```text
       Sách là KHUNG để điều chỉnh mô hình nền tảng (LLM và LMM) cho
       ứng dụng cụ thể: nêu nhiều giải pháp và các câu hỏi để chọn
                                │
                                ▼
       Mười nhóm câu hỏi sách giúp trả lời:
       · có nên xây ứng dụng AI này không?
       · đánh giá ứng dụng ra sao? dùng AI đánh giá AI được không?
       · vì sao có hallucination? phát hiện và giảm bằng cách nào?
       · thực hành tốt nhất của prompt engineering là gì?
       · vì sao RAG hiệu quả? các chiến lược làm RAG?
       · agent là gì? xây và đánh giá agent thế nào?
       · khi nào nên và không nên finetune?
       · cần bao nhiêu dữ liệu? kiểm tra chất lượng dữ liệu ra sao?
       · làm mô hình nhanh hơn, rẻ hơn, an toàn hơn thế nào?
       · tạo vòng phản hồi để liên tục cải thiện ứng dụng thế nào?
       Ngoài ra: định hướng giữa các loại mô hình, benchmark đánh giá,
       vô số use case và mẫu ứng dụng
                                │
                                ▼
       Minh hoạ bằng case study (nhiều cái tác giả trực tiếp làm), nhiều
       tài liệu tham khảo, chuyên gia đa lĩnh vực đọc duyệt; viết trong
       hai năm, dựa trên kinh nghiệm mười năm với mô hình ngôn ngữ và
       hệ thống học máy
                                │
                                ▼
       Như sách trước (DMLS): tập trung vào NỀN TẢNG, không vào công cụ
       hay API cụ thể — công cụ lỗi thời nhanh
       · chú thích: dạy khoá TensorFlow năm 2017 cho tác giả bài học đau
         về tốc độ lỗi thời của công cụ và bài hướng dẫn
                                │
                                ▼
       Ba tiêu chí xác định cái gì sẽ còn dùng được lâu:
       1. vấn đề do giới hạn căn bản của cách AI hoạt động, hay sẽ tự hết
          khi mô hình tốt hơn? Nếu căn bản thì phân tích thách thức và
          giải pháp, đi từ giải pháp đơn giản nhất lên phức tạp dần
       2. hỏi mạng lưới nhà nghiên cứu và kỹ sư về vấn đề và giải pháp
          quan trọng nhất
       3. đôi khi dùng Định luật Lindy: tuổi thọ còn lại của một công
          nghệ tỷ lệ với tuổi hiện tại của nó
       Ngoại lệ: đôi khi giữ khái niệm có lẽ tạm thời vì nó hữu ích ngay
       hoặc minh hoạ một cách giải quyết vấn đề thú vị
```

### Khung bên: đọc AIE cùng DMLS (Reading AI Engineering (AIE) with Designing Machine Learning Systems (DMLS), trang PDF 14)

```text
  DMLS (2022)                              AIE (2025)
  ┌──────────────────────────────┐   ┌──────────────────────────────┐
  │ ứng dụng trên mô hình học máy│   │ ứng dụng trên mô hình nền    │
  │ truyền thống                 │   │ tảng                         │
  │ · gán nhãn dữ liệu dạng bảng │   │ · prompt engineering         │
  │ · feature engineering        │   │ · xây dựng context           │
  │ · huấn luyện mô hình         │   │ · finetuning tiết kiệm tham  │
  │                              │   │   số                         │
  └──────────────────────────────┘   └──────────────────────────────┘
                 └───────────────┬───────────────┘
                                 ▼
       · hai sách tự chứa, đọc riêng được; nhiều chủ đề có ở sách này
         mà không có ở sách kia
       · chủ đề đã bàn kỹ ở DMLS vẫn có trong AIE nhưng ngắn hơn, kèm
         trỏ tới tài liệu
       · Chương 1 của AIE so sánh kỹ thuật học máy truyền thống với AI
         engineering; hệ thống thật thường dùng cả hai loại mô hình
```

### What This Book Is Not — sách không phải là gì (What This Book Is Not, trang PDF 16–17)

```text
       KHÔNG phải sách hướng dẫn (tutorial)
       · có nhắc công cụ và mã giả để minh hoạ, nhưng không dạy dùng
         công cụ; thay vào đó cho khung để CHỌN công cụ, bàn đánh đổi
         giữa các giải pháp và câu hỏi cần đặt
       · hướng dẫn công cụ dễ tìm trên mạng; chatbot AI cũng giúp được
                                │
                                ▼
       KHÔNG phải sách lý thuyết học máy
       · không giải thích mạng nơ-ron là gì, không dạy huấn luyện mô
         hình từ đầu; chỉ giải thích lý thuyết liên quan trực tiếp
       · là sách thực hành: xây ứng dụng AI thành công cho bài toán thật
                                │
                                ▼
       Không cần nền học máy để đọc, nhưng biết các khái niệm sau giúp
       xây ứng dụng tốt hơn và tránh khổ không cần thiết:
       · xác suất: lấy mẫu, tính tất định, phân phối
       · học máy: học có giám sát, tự giám sát, log-likelihood, gradient
         descent, lan truyền ngược, hàm mất mát, tinh chỉnh siêu tham số
       · kiến trúc mạng: feedforward, hồi quy (recurrent), transformer
       · thước đo: accuracy, F1, precision, recall, cosine similarity,
         cross entropy
       Chưa biết thì sách có giải thích ngắn hoặc trỏ tới tài liệu
```

### Who This Book Is For — sách dành cho ai (Who This Book Is For, trang PDF 18–19)

```text
       Ai muốn dùng mô hình nền tảng giải bài toán thật; ngôn ngữ hướng
       tới vai trò kỹ thuật: kỹ sư AI, kỹ sư học máy, nhà khoa học dữ
       liệu, quản lý kỹ thuật, quản lý sản phẩm kỹ thuật
                                │
       ┌────────────────────────┴────────────────────────┐
       ▼                                                 ▼
  Ba tình huống chính                          Các nhóm cũng hưởng lợi
  · đang xây hoặc tối ưu ứng dụng AI,          · nhà phát triển công cụ
    từ đầu hoặc đưa từ demo lên production;      tìm khoảng trống chưa ai
    gặp hallucination, bảo mật, latency,         phục vụ trong hệ sinh thái
    chi phí                                    · nhà nghiên cứu muốn hiểu
  · muốn quy trình phát triển AI của đội         use case
    có hệ thống, nhanh, tin cậy hơn            · ứng viên muốn rõ kỹ năng
  · muốn hiểu tổ chức dùng mô hình nền tảng      cần để làm kỹ sư AI
    để tăng lợi nhuận và lập đội làm việc đó   · bất kỳ ai muốn hiểu năng
                                                 lực, giới hạn của AI và
                                                 tác động tới các vai trò
       └────────────────────────┬────────────────────────┘
                                ▼
       Một số mục đi sâu kỹ thuật; tác giả báo trước, người đọc có thể
       bỏ qua
```

### Navigating This Book — mười chương theo quy trình phát triển ứng dụng AI (Navigating This Book, trang PDF 19–22)

```text
       Sách đi theo quy trình phát triển ứng dụng AI điển hình; các
       chương độc lập, có thể bỏ qua phần đã biết
                                │
                                ▼
  ┌─────────────────────────────────────────────────────────────────┐
  │ Chương 1 — QUYẾT ĐỊNH: ứng dụng có cần không? có cần AI không?  │
  │ có phải tự xây không? + các use case thành công                 │
  └─────────────────────────────────────────────────────────────────┘
                                ▼
  ┌─────────────────────────────────────────────────────────────────┐
  │ Chương 2 — HIỂU MÔ HÌNH: công thức dữ liệu huấn luyện, kiến trúc│
  │ và quy mô, căn chỉnh theo sở thích con người; mô hình sinh câu  │
  │ trả lời ra sao (giải thích tính thiếu nhất quán, hallucination);│
  │ đổi thiết lập sinh là cách rẻ để tăng chất lượng                │
  └─────────────────────────────────────────────────────────────────┘
                                ▼
  ┌─────────────────────────────────────────────────────────────────┐
  │ Chương 3 và 4 — ĐÁNH GIÁ: một trong những thách thức khó nhất;  │
  │ các phương pháp đánh giá và cách dựng pipeline đánh giá tin cậy,│
  │ có hệ thống                                                     │
  └─────────────────────────────────────────────────────────────────┘
                                ▼
       Chất lượng câu trả lời (ngoài thiết lập sinh) phụ thuộc ba thứ:
       chỉ dẫn │ context │ chính mô hình
                                ▼
  ┌──────────────────┬───────────────────┬──────────────────────────┐
  │ Chương 5 —       │ Chương 6 —        │ Chương 7 — FINETUNING:   │
  │ PROMPT           │ CONTEXT: hai mẫu  │ đổi chính mô hình; kỹ    │
  │ ENGINEERING:     │ RAG (đã kiểm      │ thuật tiết kiệm bộ nhớ;  │
  │ prompt là gì, vì │ chứng trong       │ model merging; mục tính  │
  │ sao hiệu quả,    │ production) và    │ bộ nhớ của mô hình       │
  │ thực hành tốt;   │ agent (mạnh hơn,  │                          │
  │ tấn công prompt  │ phức tạp hơn,     │                          │
  │ và phòng thủ     │ còn đang khám phá)│                          │
  └──────────────────┴───────────────────┴──────────────────────────┘
                                ▼
  ┌─────────────────────────────────────────────────────────────────┐
  │ Chương 8 — DỮ LIỆU: thu thập, gán nhãn, tổng hợp, xử lý; chất   │
  │ lượng dữ liệu là gì và đánh giá ra sao (vượt ra ngoài finetune) │
  └─────────────────────────────────────────────────────────────────┘
                                ▼
       Chương 5–8 nâng CHẤT LƯỢNG; Chương 9 làm suy luận RẺ và NHANH
  ┌─────────────────────────────────────────────────────────────────┐
  │ Chương 9 — TỐI ƯU SUY LUẬN: ở mức mô hình và mức dịch vụ suy    │
  │ luận; dùng API thì nhà cung cấp lo phần lớn, tự host thì phải   │
  │ tự làm                                                          │
  └─────────────────────────────────────────────────────────────────┘
                                ▼
  ┌─────────────────────────────────────────────────────────────────┐
  │ Chương 10 — GHÉP LẠI: kiến trúc ứng dụng từ đầu tới cuối; phần  │
  │ hai thiên về sản phẩm: thiết kế hệ thống phản hồi người dùng vừa│
  │ thu được phản hồi hữu ích vừa giữ trải nghiệm tốt               │
  └─────────────────────────────────────────────────────────────────┘
       Ghi chú: "chúng ta" trong sách là người đọc và tác giả (thói
       quen từ thời dạy học)
```

### Conventions, Using Code Examples, O'Reilly Online Learning, How to Contact Us (trang PDF 23–27)

```text
       Quy ước in ấn chuẩn của O'Reilly (nghiêng, chữ đều, ô TIP/NOTE/
       WARNING); tài liệu bổ sung ở github.com/chiphuyen/aie-book; trang
       đính chính oreil.ly/ai-engineering; thông tin liên hệ nhà xuất bản
```

### Acknowledgments — lời cảm ơn (Acknowledgments, trang PDF 27–30)

```text
       Tiến độ gấp: hai năm cho sách 150.000 từ, nên tác giả cảm ơn người duyệt
       kỹ thuật đọc nhanh
                                │
                                ▼
       Vòng duyệt đầu: Luke Metz (kiểm tra giả định), Han-chung Lee (chỉ
       tài liệu bị bỏ sót)
       Góc nhìn lãnh đạo: Vittorio Cretella, Andrei Lopatenko (dẫn dắt
       đổi mới AI ở công ty Fortune 500); Vicki Reyzelman (giữ nội dung
       gần người làm kỹ thuật phần mềm)
       Hỗ trợ chung: Eugene Yan, Shawn Wang (swyx), Sanyam Bhutani
                                │
                                ▼
       Đóng góp theo chương:
       · Kyle Kranen (quy trình finetune) và Mark Saroufim (hiệu năng):
         then chốt cho Chương 7 và 9
       · Kittipat "Bot" Kampa (hình dung nền tảng AI), Denys Linkov
         (đánh giá, nền tảng), Chetan Tekur (mẫu ứng dụng), Shengzhi
         (Alex) Li và Hien Luu (kiến trúc AI)
       · Aileen Bui (góc nhìn quản lý sản phẩm), Todor Markov (chương RAG
         và Agent), Tal Kachman (hoàn tất chương Finetuning)
                                │
                                ▼
       Danh sách dài người trò chuyện, người đọc sớm (Douglas Bailley;
       Nutan Sahoo gợi ý cách giải thích perplexity), đội O'Reilly, đồng
       nghiệp cũ và hiện tại
```

### Epilogue — lời kết (Epilogue, trang PDF 930–931)

```text
       Sách đã xong: hơn 150.000 từ, 160 hình, 250 chú thích, 975 đường
       dẫn tham khảo
                                │
                                ▼
       · có thời gian để học là một đặc ân; cảm ơn người đọc
       · phần khó nhất của viết kỹ thuật không phải tìm câu trả lời đúng
         mà là đặt đúng câu hỏi
                                │
                                ▼
       Số ứng dụng trên mô hình nền tảng sẽ tăng theo cấp số nhân; cách
       tiếp cận có hệ thống làm phát triển dễ hơn và mở thêm ứng dụng
       · liên hệ: X @chipro, LinkedIn /in/chiphuyen,
         huyenchip.com/communication; kho GitHub của sách
       · thách thức của AI engineering không phải cái nào cũng vui,
         nhưng cái nào cũng là cơ hội phát triển và tạo tác động
```

### About the Author — về tác giả (About the Author, trang PDF 989)

```text
       Chip Huyen: nhà văn, nhà khoa học máy tính chuyên hệ thống học máy
       · làm ở NVIDIA, Snorkel AI; sáng lập startup hạ tầng AI (đã được
         mua lại); dạy hệ thống học máy ở Stanford
       · sách dựa trên kinh nghiệm giúp tổ chức lớn và startup dùng AI
       · Designing Machine Learning Systems (O'Reilly 2022): bán chạy trên
         Amazon mảng AI, dịch ra hơn 10 thứ tiếng
       · bốn sách tiếng Việt bán chạy, có bộ Xách ba lô lên và đi
```

### Colophon — con vật trên bìa: cú Oman (Colophon, trang PDF 990–991)

```text
       Cú Oman (Strix butleri): "cú không tai", sống ở Oman, Iran, UAE
                                │
                                ▼
       1878: một con cú được thu mẫu, đặt tên Strix butleri theo người
       phát hiện (đại tá, nhà điểu học Edward Arthur Butler); quen gọi
       là cú Hume, tưởng phổ biến khắp Trung Đông
                                │
                                ▼
       2013: phát hiện một loài cú chưa biết ở Oman, đặt tên Strix
       omanensis, mô tả từ ảnh và ghi âm (không có mẫu vật)
                                │
                                ▼
       2015: phân tích mẫu chuẩn 1878 cho thấy nó chính là Strix
       omanensis, khác loài cú phổ biến ở Trung Đông
       · theo quy tắc đặt tên, loài giữ tên gốc Strix butleri
       · loài phổ biến hơn được đặt tên mới Strix hadorami (cú sa mạc)
                                │
                                ▼
       Đặc điểm: mặt xám nhạt và xám đậm, mắt cam; lưng nâu xám đậm,
       bụng xám nhạt có vệt sẫm hẹp; cỡ vừa, đầu tròn, không có chùm lông
       tai; IUCN xếp "thiếu dữ liệu"
       Bìa: Karen Montgomery vẽ theo bản khắc trong Royal Natural History
       của Lydekker
```

## Ba câu hỏi chương này trả lời

1. **Vì sao cần một cuốn sách về AI engineering khi xây ứng dụng AI đã dễ đến mức không cần viết code?** Vì sự dễ dàng ấy khiến nhiều người tưởng không có gì mới, trong khi quy mô và năng lực của mô hình nền tảng đặt ra cả cơ hội lẫn thách thức cần giải pháp mới (đánh giá đầu ra mở, hallucination, tấn công prompt, chi phí và latency của mô hình rất lớn). Đồng thời các thực hành cũ của học máy — thử nghiệm có hệ thống, đánh giá chặt, tối ưu cho rẻ và nhanh — vẫn đúng. Sách gom cả hai thành một quy trình, dựa trên hai năm viết, hơn 100 cuộc phỏng vấn và mười năm kinh nghiệm của tác giả.
2. **Tác giả chọn nội dung theo nguyên tắc nào để sách không lỗi thời nhanh?** Tập trung vào nền tảng thay cho công cụ (bài học từ khoá TensorFlow năm 2017), và lọc bằng ba tiêu chí: vấn đề có phải giới hạn căn bản của AI không; ý kiến của mạng lưới chuyên gia; Định luật Lindy (thứ đã tồn tại lâu thì nhiều khả năng còn tồn tại lâu). Một số khái niệm có lẽ tạm thời vẫn được giữ nếu hữu ích ngay hoặc minh hoạ một cách giải quyết vấn đề hay.
3. **Mười chương được sắp xếp theo logic nào?** Theo quy trình phát triển ứng dụng: quyết định có làm không (Chương 1), hiểu mô hình (Chương 2), đánh giá (Chương 3–4), cải thiện ba yếu tố quyết định chất lượng câu trả lời — chỉ dẫn (Chương 5), context (Chương 6), chính mô hình (Chương 7) cùng dữ liệu để finetune (Chương 8) — rồi làm suy luận rẻ và nhanh (Chương 9), cuối cùng ghép thành kiến trúc hoàn chỉnh có vòng phản hồi người dùng (Chương 10).

## Khái niệm cần biết

- **Mô hình nền tảng (foundation model):** mô hình rất lớn, huấn luyện trên lượng dữ liệu khổng lồ, dùng làm nền cho nhiều ứng dụng khác nhau; sách gộp cả LLM và LMM vào khái niệm này. Ví dụ: một mô hình như GPT-4 có thể vừa dịch, vừa tóm tắt, vừa viết code mà không cần huấn luyện riêng cho từng việc. Quan trọng vì cả cuốn sách bàn cách điều chỉnh loại mô hình này cho ứng dụng cụ thể.
- **LLM và LMM (large language model, large multimodal model):** LLM là mô hình ngôn ngữ lớn, làm việc với văn bản; LMM là mô hình đa phương thức lớn, làm việc với nhiều loại dữ liệu như văn bản, hình ảnh, âm thanh. Ví dụ: một LMM nhận ảnh hoá đơn và trả lời "tổng tiền là bao nhiêu". Quan trọng vì phạm vi của sách bao trùm cả hai.
- **AI engineering:** quy trình kỹ thuật xây ứng dụng trên mô hình nền tảng có sẵn, khác với kỹ thuật học máy truyền thống vốn tự huấn luyện mô hình. Theo khung bên về hai cuốn sách, học máy truyền thống thiên về gán nhãn dữ liệu bảng, feature engineering, huấn luyện; AI engineering thiên về prompt engineering, xây dựng context, finetuning tiết kiệm tham số. Quan trọng vì đây là tên cuốn sách và tên nghề mà sách nhắm tới.
- **Mở rộng quy mô (scaling):** làm mô hình lớn hơn và dữ liệu nhiều hơn để mô hình tốt hơn. Ví dụ: năm 2012 nhóm AlexNet viết rằng mọi thí nghiệm cho thấy kết quả sẽ tốt lên chỉ nhờ chờ GPU nhanh hơn và dữ liệu lớn hơn. Quan trọng vì tác giả coi đây là điều đã biết; điểm mới là số ứng dụng mà bước nhảy năng lực mở ra.
- **Hallucination:** mô hình sinh ra nội dung nghe hợp lý nhưng sai hoặc bịa. Ví dụ: chatbot trích một bài báo không tồn tại. Quan trọng vì sách hứa giải thích nguyên nhân (Chương 2) và cách phát hiện, giảm thiểu.
- **Prompt engineering:** cách viết chỉ dẫn cho mô hình để có câu trả lời mong muốn mà không đổi trọng số mô hình. Ví dụ: thêm "trả lời bằng tối đa ba câu, kèm nguồn" vào chỉ dẫn. Quan trọng vì đây là cách đầu tiên và rẻ nhất để điều chỉnh mô hình (Chương 5).
- **Context và xây dựng context (context construction):** thông tin đưa vào cùng câu hỏi để mô hình dựa vào khi trả lời. Ví dụ: chèn ba đoạn trích từ tài liệu nội bộ vào trước câu hỏi của khách hàng. Quan trọng vì chất lượng câu trả lời phụ thuộc vào context mô hình có (Chương 6).
- **RAG (retrieval-augmented generation — sinh có tăng cường truy xuất):** truy xuất thông tin liên quan từ nguồn bên ngoài rồi đưa vào context để mô hình sinh câu trả lời. Ví dụ: hệ thống tìm 5 đoạn liên quan nhất trong 10.000 trang quy chế rồi để mô hình trả lời dựa trên 5 đoạn đó. Quan trọng vì tác giả nhấn mạnh RAG dựa trên công nghệ truy xuất có từ lâu và là mẫu đã kiểm chứng trong production.
- **Agent:** hệ thống trong đó mô hình tự lập kế hoạch và dùng công cụ (tìm kiếm, chạy code, gọi API) để hoàn thành nhiệm vụ. Ví dụ: agent tự tìm giá vé, so sánh rồi đặt chỗ. Quan trọng vì tác giả đánh giá mẫu agent mạnh hơn RAG nhưng phức tạp hơn và còn đang được khám phá.
- **Finetuning và finetuning tiết kiệm tham số (parameter-efficient finetuning):** finetuning là huấn luyện tiếp mô hình có sẵn trên dữ liệu riêng để đổi chính mô hình; phiên bản tiết kiệm tham số chỉ cập nhật một phần nhỏ tham số để giảm bộ nhớ. Ví dụ: chỉ huấn luyện thêm một lớp nhỏ thay vì toàn bộ hàng tỷ tham số. Quan trọng vì Chương 7 bàn khi nào nên finetune và làm sao finetune với ít bộ nhớ.
- **Model merging (ghép mô hình):** kết hợp nhiều mô hình (thường là các bản finetune) thành một mô hình. Ví dụ: ghép một bản giỏi toán với một bản giỏi viết. Quan trọng vì sách giới thiệu đây là hướng còn thử nghiệm trong Chương 7.
- **Tối ưu suy luận (inference optimization):** làm cho việc chạy mô hình để sinh câu trả lời rẻ hơn và nhanh hơn, ở mức mô hình và mức dịch vụ. Ví dụ: giảm latency từ 2 giây xuống 0,5 giây cho mỗi câu trả lời. Quan trọng vì tự host mô hình thì phải tự làm; dùng API thì nhà cung cấp làm phần lớn (Chương 9).
- **Model API và tự host (self-hosting):** dùng mô hình do bên khác chạy qua API, hoặc tự chạy mô hình mã nguồn mở hay mô hình tự phát triển. Ví dụ: gọi API trả tiền theo token, so với thuê GPU chạy mô hình mở. Quan trọng vì nó quyết định ai chịu trách nhiệm tối ưu suy luận.
- **Vòng phản hồi (feedback loop):** cơ chế thu phản hồi người dùng để cải thiện ứng dụng liên tục. Ví dụ: nút thích/không thích dưới mỗi câu trả lời, dữ liệu dùng để sửa prompt hoặc finetune. Quan trọng vì Chương 10 dành nửa sau cho thiết kế hệ thống phản hồi mà không làm hỏng trải nghiệm.
- **Định luật Lindy (Lindy's Law):** quy tắc kinh nghiệm cho rằng tuổi thọ còn lại của một công nghệ tỷ lệ với tuổi hiện tại của nó. Ví dụ minh hoạ: một kỹ thuật đã dùng 20 năm được kỳ vọng còn dùng lâu hơn nhiều so với một kỹ thuật mới xuất hiện 6 tháng. Quan trọng vì đây là một trong ba tiêu chí tác giả dùng để chọn nội dung.
- **Cách tiếp cận bắt đầu đơn giản (start-simple approach):** với mỗi vấn đề, bắt đầu từ giải pháp đơn giản nhất rồi chỉ thêm giải pháp phức tạp khi thách thức tăng lên. Ví dụ: thử prompt trước, rồi RAG, rồi mới finetune. Quan trọng vì nó quyết định thứ tự trình bày giải pháp trong nhiều chương.

## Nội dung chi tiết

### 1. Lời nói đầu: điều gì thật sự mới (Preface, trang PDF 9–11)

Tác giả mở đầu bằng trải nghiệm cá nhân: khi ChatGPT ra đời, cũng như nhiều đồng nghiệp, bà thấy mất phương hướng. Điều làm bà bất ngờ không phải kích thước hay năng lực của mô hình. Hơn mười năm nay cộng đồng AI đã biết rằng mở rộng quy mô mô hình làm mô hình tốt hơn. Năm 2012, nhóm tác giả AlexNet đã viết trong bài báo mang tính bước ngoặt của họ rằng mọi thí nghiệm đều gợi ý kết quả có thể tốt lên chỉ bằng cách chờ GPU nhanh hơn và tập dữ liệu lớn hơn xuất hiện. Hai chú thích gắn vào câu này bổ sung: một đồng tác giả AlexNet, Ilya Sutskever, sau đó đồng sáng lập OpenAI và biến bài học ấy thành hiện thực với các mô hình GPT; và ngay cả một dự án nhỏ của tác giả năm 2017, dùng mô hình ngôn ngữ để đánh giá chất lượng bản dịch, cũng kết luận rằng "cần một mô hình ngôn ngữ tốt hơn".

Điều thật sự làm tác giả bất ngờ là số lượng ứng dụng mà bước nhảy năng lực ấy mở ra. Bà từng nghĩ chỉ số chất lượng mô hình tăng một chút thì số ứng dụng tăng vừa phải; thực tế là một vụ bùng nổ khả năng mới. Năng lực mới vừa làm tăng nhu cầu ứng dụng AI, vừa hạ thấp rào cản cho nhà phát triển: bắt đầu xây ứng dụng AI đã trở nên rất dễ, thậm chí có thể xây ứng dụng mà không viết dòng code nào. Sự chuyển dịch này biến AI từ một ngành chuyên sâu thành một công cụ phát triển mạnh mà ai cũng dùng được.

Tuy vậy, việc ứng dụng AI hôm nay trông mới nhưng dựa trên các kỹ thuật đã có từ lâu. Các bài báo về mô hình hoá ngôn ngữ xuất hiện từ thập niên 1950. Ứng dụng RAG dựa trên công nghệ truy xuất vốn vận hành các hệ thống tìm kiếm và gợi ý từ trước khi thuật ngữ RAG ra đời. Các thực hành tốt nhất khi triển khai ứng dụng học máy truyền thống — thử nghiệm có hệ thống, đánh giá chặt chẽ, không ngừng tối ưu để mô hình nhanh hơn và rẻ hơn — vẫn là thực hành tốt nhất khi làm việc với ứng dụng dựa trên mô hình nền tảng.

Chính sự quen thuộc và dễ dùng của nhiều kỹ thuật AI engineering có thể khiến người ta nghĩ ngành này không có gì mới. Tác giả phản bác: nhiều nguyên tắc xây ứng dụng AI vẫn giữ nguyên, nhưng quy mô và năng lực cao hơn của mô hình AI tạo ra cơ hội và thách thức đòi hỏi giải pháp mới. Cuốn sách bao quát quy trình từ đầu đến cuối để điều chỉnh mô hình nền tảng giải bài toán thực tế, gồm cả các kỹ thuật đã được kiểm chứng từ những ngành kỹ thuật khác lẫn các kỹ thuật mới xuất hiện cùng mô hình nền tảng.

Tác giả viết sách vì muốn học, và đã học được nhiều: từ các dự án đã làm, các bài báo đã đọc và những người đã phỏng vấn. Bà dùng ghi chép từ hơn 100 cuộc trò chuyện và phỏng vấn với nhà nghiên cứu ở các phòng thí nghiệm AI lớn (OpenAI, Google, Anthropic…), nhà phát triển framework (NVIDIA, Meta, Hugging Face, Anyscale, LangChain, LlamaIndex…), lãnh đạo và trưởng bộ phận AI/dữ liệu ở công ty nhiều quy mô, quản lý sản phẩm, nhà nghiên cứu cộng đồng và nhà phát triển ứng dụng độc lập. Bà học đặc biệt nhiều từ người đọc sớm — những người thử thách giả định, đưa góc nhìn khác và nêu vấn đề mới. Một số phần của sách, khi đăng trên blog của tác giả, nhận hàng nghìn bình luận, nhiều bình luận cho góc nhìn mới hoặc xác nhận giả thuyết. Tác giả mong quá trình học tiếp tục khi sách đến tay người đọc và mời góp ý qua X, LinkedIn hoặc email hi@huyenchip.com.

### 2. Sách bàn về điều gì (What This Book Is About, trang PDF 12–15)

#### Phạm vi và các câu hỏi

Sách cung cấp một khung để điều chỉnh mô hình nền tảng — gồm cả mô hình ngôn ngữ lớn (LLM) và mô hình đa phương thức lớn (LMM) — cho các ứng dụng cụ thể. Có nhiều cách để xây một ứng dụng; sách phác ra nhiều giải pháp và nêu các câu hỏi để người đọc tự đánh giá giải pháp phù hợp nhất. Các câu hỏi sách giúp trả lời gồm:

- Có nên xây ứng dụng AI này không?
- Đánh giá ứng dụng thế nào? Có thể dùng AI để đánh giá đầu ra của AI không?
- Điều gì gây ra hallucination? Phát hiện và giảm hallucination bằng cách nào?
- Thực hành tốt nhất cho prompt engineering là gì?
- Vì sao RAG hiệu quả? Có những chiến lược nào để làm RAG?
- Agent là gì? Xây và đánh giá agent thế nào?
- Khi nào nên finetune mô hình, khi nào không?
- Cần bao nhiêu dữ liệu? Kiểm tra chất lượng dữ liệu thế nào?
- Làm sao để mô hình nhanh hơn, rẻ hơn và an toàn hơn?
- Làm sao tạo vòng phản hồi để liên tục cải thiện ứng dụng?

Sách cũng giúp người đọc định hướng giữa bối cảnh AI đang quá tải thông tin: các loại mô hình, các benchmark đánh giá, và số use case cùng mẫu ứng dụng tưởng như vô tận.

#### Cách xây dựng nội dung

Nội dung được minh hoạ bằng case study, nhiều case tác giả trực tiếp làm, dựa trên nhiều tài liệu tham khảo và được chuyên gia từ nhiều nền tảng khác nhau duyệt kỹ. Sách viết trong hai năm nhưng rút từ kinh nghiệm làm việc với mô hình ngôn ngữ và hệ thống học máy trong mười năm.

Giống cuốn sách O'Reilly trước của tác giả, *Designing Machine Learning Systems* (DMLS), cuốn này tập trung vào nền tảng của AI engineering thay vì một công cụ hay API cụ thể, vì công cụ lỗi thời nhanh còn nền tảng thì bền hơn. Chú thích ở câu này kể rằng việc dạy một khoá học về cách dùng TensorFlow năm 2017 đã cho tác giả một bài học đau đớn về tốc độ lỗi thời của công cụ và bài hướng dẫn.

#### Ba tiêu chí chọn cái gì sẽ còn lâu

Xác định cái gì sẽ tồn tại lâu thường khó. Tác giả dựa vào ba tiêu chí:

1. **Bản chất của vấn đề.** Với mỗi vấn đề, tác giả xét nó xuất phát từ giới hạn căn bản trong cách AI hoạt động, hay sẽ biến mất khi có mô hình tốt hơn. Nếu vấn đề là căn bản, sách phân tích các thách thức và giải pháp cho từng thách thức. Tác giả theo cách tiếp cận "bắt đầu đơn giản": với nhiều vấn đề, sách đi từ giải pháp đơn giản nhất rồi tiến tới giải pháp phức tạp hơn khi thách thức tăng lên.
2. **Ý kiến chuyên gia.** Tác giả hỏi một mạng lưới rộng gồm nhà nghiên cứu và kỹ sư về những vấn đề và giải pháp mà họ cho là quan trọng nhất.
3. **Định luật Lindy.** Thỉnh thoảng tác giả dựa vào định luật này: tuổi thọ tương lai của một công nghệ tỷ lệ với tuổi hiện tại của nó. Thứ gì đã tồn tại khá lâu thì được giả định sẽ còn tồn tại thêm một thời gian nữa.

Dù vậy, sách đôi khi vẫn đưa vào một khái niệm mà tác giả tin là tạm thời, vì nó hữu ích ngay cho một số nhà phát triển ứng dụng hoặc vì nó minh hoạ một cách giải quyết vấn đề thú vị.

#### Khung bên: đọc AIE cùng DMLS (Reading AI Engineering (AIE) with Designing Machine Learning Systems (DMLS), trang PDF 14)

AIE có thể đi kèm DMLS. DMLS tập trung xây ứng dụng trên mô hình học máy truyền thống, nên thiên về gán nhãn dữ liệu dạng bảng, feature engineering (thiết kế đặc trưng) và huấn luyện mô hình. AIE tập trung xây ứng dụng trên mô hình nền tảng, nên thiên về prompt engineering, xây dựng context và finetuning tiết kiệm tham số. Hai sách đều tự chứa và chia mô-đun, đọc riêng cuốn nào cũng được.

Vì mô hình nền tảng cũng là mô hình học máy, một số khái niệm dùng được cho cả hai. Chủ đề nào liên quan đến AIE nhưng đã bàn kỹ ở DMLS thì vẫn có trong AIE nhưng ngắn hơn, kèm trỏ tới tài liệu. Nhiều chủ đề có ở DMLS mà không có ở AIE và ngược lại. Chương 1 của AIE cũng nêu khác biệt giữa kỹ thuật học máy truyền thống và AI engineering. Hệ thống thực tế thường dùng cả mô hình học máy truyền thống lẫn mô hình nền tảng, nên thường cần biết làm việc với cả hai.

### 3. Sách không phải là gì (What This Book Is Not, trang PDF 16–17)

Sách không phải sách hướng dẫn từng bước. Dù có nhắc công cụ cụ thể và có đoạn mã giả để minh hoạ khái niệm, sách không dạy cách dùng công cụ; thay vào đó nó cho một khung để chọn công cụ, với nhiều thảo luận về đánh đổi giữa các giải pháp và các câu hỏi nên đặt khi đánh giá một giải pháp. Khi cần dùng một công cụ, thường dễ tìm hướng dẫn trên mạng, và chatbot AI cũng khá giỏi giúp bắt đầu với các công cụ phổ biến.

Sách cũng không phải sách lý thuyết học máy: không giải thích mạng nơ-ron là gì, không hướng dẫn xây và huấn luyện mô hình từ đầu. Sách giải thích nhiều khái niệm lý thuyết liên quan trực tiếp đến thảo luận, nhưng là sách thực hành, nhằm giúp xây ứng dụng AI thành công cho bài toán thực tế.

Có thể xây ứng dụng dựa trên mô hình nền tảng mà không có chuyên môn học máy, nhưng hiểu biết cơ bản về học máy và thống kê giúp xây ứng dụng tốt hơn và tránh những khổ sở không cần thiết. Người đọc không cần nền học máy, nhưng sẽ làm hiệu quả hơn nếu biết:

| Nhóm | Khái niệm |
|---|---|
| Xác suất | lấy mẫu (sampling), tính tất định (determinism), phân phối (distribution) |
| Học máy | học có giám sát (supervision), tự giám sát (self-supervision), log-likelihood, gradient descent, lan truyền ngược (backpropagation), hàm mất mát (loss function), tinh chỉnh siêu tham số (hyperparameter tuning) |
| Kiến trúc mạng nơ-ron | feedforward, hồi quy (recurrent), transformer |
| Thước đo | accuracy, F1, precision, recall, cosine similarity, cross entropy |

Nếu chưa biết, sách có giải thích ngắn ở mức tổng quan hoặc trỏ tới tài liệu để người đọc bắt kịp.

### 4. Sách dành cho ai (Who This Book Is For, trang PDF 18–19)

Sách dành cho bất kỳ ai muốn dùng mô hình nền tảng để giải bài toán thực tế. Đây là sách kỹ thuật, nên ngôn ngữ hướng tới các vai trò kỹ thuật: kỹ sư AI, kỹ sư học máy, nhà khoa học dữ liệu, quản lý kỹ thuật và quản lý sản phẩm kỹ thuật. Sách hợp với người đọc nếu họ ở một trong ba tình huống:

- Đang xây hoặc tối ưu một ứng dụng AI, dù bắt đầu từ đầu hay muốn vượt qua giai đoạn demo để lên mức sẵn sàng cho production; có thể đang gặp hallucination, vấn đề bảo mật, latency (độ trễ) hoặc chi phí và cần giải pháp nhắm đúng.
- Muốn làm cho quy trình phát triển AI của đội có hệ thống hơn, nhanh hơn và tin cậy hơn.
- Muốn hiểu tổ chức có thể dùng mô hình nền tảng thế nào để cải thiện lợi nhuận và cách lập một đội để làm điều đó.

Các nhóm sau cũng được lợi: nhà phát triển công cụ muốn tìm những mảng chưa được phục vụ đủ trong AI engineering để định vị sản phẩm trong hệ sinh thái; nhà nghiên cứu muốn hiểu rõ hơn các use case AI; ứng viên muốn biết rõ kỹ năng cần để theo nghề kỹ sư AI; và bất kỳ ai muốn hiểu năng lực, giới hạn của AI và tác động của nó lên các vai trò khác nhau.

Tác giả thích đi tới tận gốc vấn đề, nên một số mục đi khá sâu vào kỹ thuật. Nhiều người đọc sớm thích mức chi tiết này, nhưng không phải ai cũng cần; tác giả sẽ báo trước khi nội dung quá kỹ thuật để người đọc có thể bỏ qua.

### 5. Đi qua cuốn sách (Navigating This Book, trang PDF 19–22)

Sách được sắp theo quy trình điển hình để phát triển một ứng dụng AI; mỗi chương ứng với một bước. Vì sách chia mô-đun, người đọc có thể bỏ qua phần đã quen hoặc ít liên quan.

#### Bước 1 — quyết định có xây ứng dụng không: Chương 1

Trước khi quyết định xây một ứng dụng AI, cần hiểu quy trình gồm những gì và trả lời các câu hỏi: ứng dụng này có cần thiết không? Có cần AI không? Có phải tự xây không? Chương đầu tiên ([C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md](C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md)) giúp trả lời các câu hỏi này, đồng thời giới thiệu một loạt use case thành công để người đọc hình dung mô hình nền tảng làm được gì.

#### Bước 2 — hiểu mô hình hoạt động bên trong: Chương 2

Không cần nền học máy để xây ứng dụng AI, nhưng hiểu mô hình nền tảng hoạt động bên trong ra sao giúp tận dụng nó tốt nhất. Chương 2 ([C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md)) phân tích cách tạo ra một mô hình nền tảng và các quyết định thiết kế có ảnh hưởng lớn tới ứng dụng phía sau: công thức dữ liệu huấn luyện, kiến trúc và quy mô mô hình, và cách mô hình được huấn luyện để phù hợp với sở thích con người. Chương này sau đó bàn cách mô hình sinh ra câu trả lời, điều giải thích những hành vi tưởng như khó hiểu của mô hình như thiếu nhất quán và hallucination. Thay đổi thiết lập sinh (generation setting) của mô hình cũng thường là cách rẻ và dễ để tăng đáng kể chất lượng.

#### Bước 3 — đánh giá ở mọi bước: Chương 3 và 4

Khi đã quyết định xây ứng dụng với mô hình nền tảng, đánh giá sẽ là phần không thể thiếu ở mọi bước. Đánh giá là một trong những thách thức khó nhất của AI engineering, nếu không phải là khó nhất. Sách dành hai chương — Chương 3 ([C03-phuong-phap-danh-gia.md](C03-phuong-phap-danh-gia.md)) và Chương 4 ([C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md)) — để khảo sát các phương pháp đánh giá và cách dùng chúng dựng một pipeline (chuỗi xử lý) đánh giá tin cậy, có hệ thống cho ứng dụng.

#### Bước 4 — cải thiện ba yếu tố quyết định chất lượng: Chương 5, 6, 7 (và 8)

Với một truy vấn, chất lượng câu trả lời của mô hình (ngoài thiết lập sinh) phụ thuộc ba yếu tố:

| Yếu tố | Chương tối ưu yếu tố này |
|---|---|
| Chỉ dẫn về cách mô hình nên hành xử | Chương 5 — prompt engineering |
| Context mô hình có thể dùng để trả lời | Chương 6 — RAG và agent |
| Chính mô hình | Chương 7 — finetuning (cùng dữ liệu ở Chương 8) |

- **Chương 5** ([C05-prompt-engineering.md](C05-prompt-engineering.md)) bàn prompt engineering: prompt là gì, vì sao prompt engineering hiệu quả, và các thực hành tốt nhất. Chương này sau đó bàn cách kẻ xấu khai thác ứng dụng bằng tấn công prompt và cách phòng thủ.
- **Chương 6** ([C06-rag-va-agent.md](C06-rag-va-agent.md)) giải thích vì sao context quan trọng để mô hình sinh câu trả lời chính xác, và đi sâu vào hai mẫu ứng dụng chính để xây dựng context: RAG và agent. Mẫu RAG được hiểu rõ hơn và đã chứng minh hiệu quả trong production. Mẫu agent hứa hẹn mạnh hơn nhiều nhưng cũng phức tạp hơn và vẫn đang được khám phá.
- **Chương 7** ([C07-finetuning.md](C07-finetuning.md)) bàn cách điều chỉnh mô hình cho ứng dụng bằng cách thay đổi chính mô hình qua finetuning. Do quy mô của mô hình nền tảng, finetune toàn bộ mô hình tốn rất nhiều bộ nhớ, nên nhiều kỹ thuật được phát triển để finetune mô hình tốt hơn với ít bộ nhớ hơn. Chương trình bày các cách finetune khác nhau, bổ sung một hướng mang tính thử nghiệm hơn là model merging (ghép mô hình), và có một mục kỹ thuật hơn chỉ cách tính lượng bộ nhớ một mô hình chiếm.
- **Chương 8** ([C08-ky-thuat-du-lieu.md](C08-ky-thuat-du-lieu.md)): vì có sẵn nhiều framework finetuning, bản thân việc finetune thường đơn giản; cái khó là có dữ liệu để finetune. Chương 8 dành trọn cho dữ liệu: thu thập, gán nhãn, tổng hợp (data synthesis) và xử lý dữ liệu. Nhiều chủ đề ở đây có ý nghĩa vượt ra ngoài finetuning, gồm câu hỏi chất lượng dữ liệu nghĩa là gì và đánh giá chất lượng dữ liệu ra sao.

#### Bước 5 — làm suy luận rẻ hơn và nhanh hơn: Chương 9

Nếu Chương 5–8 nhằm nâng chất lượng mô hình, thì Chương 9 ([C09-toi-uu-suy-luan.md](C09-toi-uu-suy-luan.md)) nhằm làm suy luận rẻ hơn và nhanh hơn. Chương bàn tối ưu cả ở mức mô hình lẫn mức dịch vụ suy luận. Nếu dùng model API — tức bên khác host mô hình — thì API đó nhiều khả năng đã lo phần tối ưu suy luận. Nếu tự host mô hình, dù là mô hình mã nguồn mở hay mô hình tự phát triển, người làm ứng dụng sẽ phải tự triển khai nhiều kỹ thuật trong chương này.

#### Bước 6 — ghép thành hệ thống hoàn chỉnh và lắng nghe người dùng: Chương 10

Chương cuối ([C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md)) ghép các khái niệm trong sách để xây một ứng dụng từ đầu đến cuối. Phần thứ hai của chương thiên về sản phẩm, bàn cách thiết kế hệ thống phản hồi người dùng để thu được phản hồi hữu ích mà vẫn giữ trải nghiệm người dùng tốt.

Ghi chú của tác giả ở cuối mục: bà thường dùng "chúng ta" để chỉ người đọc và tác giả — thói quen từ thời dạy học, vì bà coi việc viết là một trải nghiệm học chung của người viết và người đọc.

#### Ví dụ hôm nay (minh hoạ do người tổng hợp đặt)

Một công ty muốn làm trợ lý trả lời câu hỏi của khách hàng về chính sách bảo hành. Đi theo trình tự của sách: (1) hỏi xem có cần AI không — nếu 80% câu hỏi chỉ thuộc 20 mẫu, một trang FAQ có thể đủ (Chương 1); (2) hiểu vì sao mô hình đôi khi bịa điều khoản không có thật và chỉnh thiết lập sinh như nhiệt độ lấy mẫu (Chương 2); (3) dựng bộ 200 câu hỏi mẫu có đáp án để chấm mọi thay đổi (Chương 3–4); (4) viết prompt yêu cầu trả lời ngắn và chỉ dựa trên tài liệu (Chương 5), rồi thêm RAG truy xuất đúng điều khoản (Chương 6); chỉ khi vẫn chưa đạt mới cân nhắc finetune và chuẩn bị dữ liệu (Chương 7–8); (5) nếu tự host mô hình và latency quá cao thì tối ưu suy luận (Chương 9); (6) ghép thành kiến trúc có guardrail và nút phản hồi để cải thiện tiếp (Chương 10). Thứ tự này cũng phản ánh cách tiếp cận "bắt đầu đơn giản" của tác giả.

### 6. Quy ước, ví dụ code, học trực tuyến O'Reilly và liên hệ (Conventions Used in This Book; Using Code Examples; O'Reilly Online Learning; How to Contact Us, trang PDF 23–27)

Đây là các trang chuẩn của O'Reilly: quy ước in (chữ nghiêng cho thuật ngữ mới và địa chỉ; chữ độ rộng cố định cho code, tên biến và prompt đưa vào mô hình; các ô TIP, NOTE, WARNING), tài liệu bổ sung ở kho https://github.com/chiphuyen/aie-book (gồm bài báo quan trọng, công cụ hữu ích, các chủ đề quá sâu cho sách và số liệu hậu trường về quá trình viết), điều kiện dùng lại code mẫu, trang đính chính https://oreil.ly/ai-engineering và thông tin liên hệ nhà xuất bản.

### 7. Lời cảm ơn (Acknowledgments, trang PDF 27–30)

Tác giả nói sách sẽ mất lâu hơn nhiều và thiếu nhiều chủ đề quan trọng nếu không có những người đã giúp. Vì tiến độ gấp — hai năm cho một cuốn sách 150.000 từ bao quát rất rộng — bà cảm ơn các người duyệt kỹ thuật đã dành thời gian đọc nhanh.

- **Vòng duyệt đầu tiên:** Luke Metz, người "phản biện" giúp kiểm tra giả định và tránh đi sai hướng; Han-chung Lee, luôn cập nhật tin AI mới nhất, chỉ ra những tài liệu tác giả bỏ sót. Hai người đọc bản nháp trước khi gửi sang vòng duyệt kỹ thuật tiếp theo.
- **Góc nhìn lãnh đạo và kỹ thuật phần mềm:** Vittorio Cretella và Andrei Lopatenko, từng dẫn dắt đổi mới AI ở các công ty Fortune 500, góp ý kết hợp chuyên môn kỹ thuật sâu với góc nhìn điều hành; Vicki Reyzelman giúp nội dung gần gũi với người đọc có nền kỹ thuật phần mềm.
- **Hỗ trợ chung:** Eugene Yan (hỗ trợ cả kỹ thuật lẫn tinh thần), Shawn Wang (swyx) (giúp tác giả tự tin hơn về cuốn sách), Sanyam Bhutani (góp ý bằng văn bản và quay cả video giải thích góp ý).
- **Đóng góp cho từng chương:** Kyle Kranen phỏng vấn đồng nghiệp và chia sẻ bản tổng hợp về quy trình finetune của họ, định hướng cho chương Finetuning; Mark Saroufim giới thiệu tài liệu hay về hiệu năng; góp ý của Kyle và Mark then chốt cho Chương 7 và Chương 9. Kittipat "Bot" Kampa chia sẻ hình dung chi tiết về nền tảng AI; Denys Linkov có cách tiếp cận có hệ thống với đánh giá và phát triển nền tảng; Chetan Tekur cho ví dụ giúp sắp xếp các mẫu ứng dụng AI; Shengzhi (Alex) Li và Hien Luu góp ý bản nháp về kiến trúc AI. Aileen Bui góp ý và ví dụ từ góc nhìn quản lý sản phẩm; Todor Markov cho lời khuyên thiết thực cho chương RAG và Agent; Tal Kachman tham gia phút chót để hoàn tất chương Finetuning.
- **Những người trò chuyện và gợi ý ý tưởng:** một danh sách dài (Andrew Francis, Anish Nag, Anthony Galczak, Anton Bacaj, Balázs Galambosi, Charles Frye, Charles Packer, Chris Brousseau, Eric Hartford, Goku Mohandas, Hamel Husain, Harpreet Sahota, Hassan El Mghari, Huu Nguyen, Jeremy Howard, Jesse Silver, John Cook, Juan Pablo Bottaro, Kyle Gallatin, Lance Martin, Lucio Dery, Matt Ross, Maxime Labonne, Miles Brundage, Nathan Lambert, Omar Khattab, Phong Nguyen, Purnendu Mukherjee, Sam Reiswig, Sebastian Raschka, Shahul ES, Sharif Shameem, Soumith Chintala, Teknium, Tim Dettmers, Undi95, Val Andrei Fajardo, Vern Liang, Victor Sanh, Wing Lian, Xiquan Cui, Ying Sheng và Kristofer). Tác giả xin lỗi trước nếu quên tên ai và mời nhắc để bổ sung.
- **Người đọc sớm:** Douglas Bailley góp rất nhiều ý; Nutan Sahoo gợi ý một cách giải thích perplexity gọn gàng; cùng mọi người đã trả lời câu hỏi, bình luận bài đăng hoặc gửi email.
- **Đội O'Reilly:** biên tập phát triển Melissa Potter, Corbin Collins, Jill Leonard; biên tập sản xuất Elizabeth Kelly; biên tập bản thảo Liz Wheeler; Nicole Butterfield theo dõi cuốn sách từ ý tưởng đến sản phẩm cuối.
- **Đồng nghiệp cũ và hiện tại:** sách là tích luỹ những bài học tác giả học được trong sự nghiệp; mỗi người từng làm cùng đều dạy bà điều mới về việc đưa học máy vào thế giới thực.

### 8. Lời kết (Epilogue, trang PDF 930–931)

Lời kết chúc mừng người đọc đã đọc xong một cuốn sách kỹ thuật hơn 150.000 từ, 160 hình minh hoạ, 250 chú thích và 975 đường dẫn tham khảo. Tác giả nói có thể dành thời gian để học là một đặc ân; bà biết ơn cơ hội viết sách và học điều mới, và biết ơn người đọc đã dành thời gian học quý giá cho cuốn sách.

Theo tác giả, phần khó nhất của viết kỹ thuật không phải tìm câu trả lời đúng mà là đặt đúng câu hỏi. Viết cuốn sách khiến bà đặt ra nhiều câu hỏi dẫn tới những phát hiện thú vị và hữu ích, và bà mong cuốn sách cũng gợi cho người đọc những câu hỏi thú vị.

Đã có rất nhiều ứng dụng ấn tượng xây trên mô hình nền tảng, và con số này chắc chắn sẽ tăng theo cấp số nhân. Các cách tiếp cận có hệ thống hơn với AI engineering, như những cách giới thiệu trong sách, sẽ làm quá trình phát triển dễ hơn và mở đường cho nhiều ứng dụng hơn nữa. Tác giả mời người đọc liên hệ để trao đổi use case (X @chipro, LinkedIn /in/chiphuyen, trang huyenchip.com/communication) và tham khảo thêm tài nguyên ở kho GitHub của sách. Bà kết rằng AI engineering có nhiều thách thức; không phải thách thức nào cũng vui, nhưng thách thức nào cũng là cơ hội để phát triển và tạo tác động, và bà mong được biết người đọc sẽ xây gì.

### 9. Về tác giả (About the Author, trang PDF 989)

Chip Huyen là nhà văn và nhà khoa học máy tính chuyên về hệ thống học máy. Bà từng làm ở NVIDIA và Snorkel AI, sáng lập một startup hạ tầng AI (sau được mua lại), và dạy hệ thống học máy ở Đại học Stanford. Cuốn sách rút từ kinh nghiệm giúp các tổ chức lớn và startup dùng AI cho giải pháp thực tế. Cuốn sách năm 2022 của bà, *Designing Machine Learning Systems* (O'Reilly), là sách bán chạy trên Amazon ở mảng AI và đã được dịch ra hơn 10 thứ tiếng. Bà cũng là tác giả bốn cuốn sách tiếng Việt bán chạy, trong đó có bộ *Xách ba lô lên và đi* (Pack Your Bag and Go).

### 10. Colophon — cú Oman trên bìa (Colophon, trang PDF 990–991)

Con vật trên bìa *AI Engineering* là cú Oman (*Strix butleri*), một loài được gọi là "cú không tai", sống ở Oman, Iran và Các Tiểu vương quốc Ả Rập Thống nhất (UAE).

Lịch sử đặt tên loài khá rắc rối. Một con cú thu mẫu năm 1878 được đặt tên *Strix butleri* theo người phát hiện, nhà điểu học đại tá Edward Arthur Butler. Loài chim này thường được gọi là cú Hume và từng được cho là phân bố rộng khắp Trung Đông. Năm 2013, một loài cú chưa từng biết được phát hiện ở Oman và đặt tên *Strix omanensis* (cú Oman); không có mẫu vật nào được thu, loài được mô tả từ ảnh chụp và ghi âm. Năm 2015, phân tích mẫu chuẩn (holotype, tức mẫu gốc tìm thấy năm 1878) của *Strix butleri* cho thấy con cú đó thực ra cùng loài với *Strix omanensis*, và khác với loài cú phổ biến hơn ở Trung Đông. Theo quy tắc đặt tên, loài này giữ tên gốc *Strix butleri*, còn loài phổ biến hơn được đặt tên mới là *Strix hadorami* (cú sa mạc).

Cú Oman có mặt màu xám nhạt và xám đậm, mắt màu cam; phần lưng nâu xám đậm, phần bụng xám nhạt với các vệt sẫm hẹp. Đây là loài cú cỡ vừa, đầu tròn, không có chùm lông tai. Vì mới được phát hiện, các nhà điểu học vẫn đang nghiên cứu hành vi, sinh thái và phân bố của nó; Liên minh Bảo tồn Thiên nhiên Quốc tế (IUCN) xếp tình trạng bảo tồn là "thiếu dữ liệu". Colophon nhắc rằng nhiều con vật trên bìa sách O'Reilly đang bị đe doạ, và tất cả đều quan trọng với thế giới.

Hình bìa do Karen Montgomery vẽ, dựa trên một bản khắc nét cổ trong *Royal Natural History* của Lydekker. Thiết kế bộ sách do Edie Freedman, Ellie Volckhausen và Karen Montgomery thực hiện. Phông bìa là Gilroy Semibold và Guardian Sans; phông chữ thân là Adobe Minion Pro; phông tiêu đề là Adobe Myriad Condensed; phông code là Ubuntu Mono của Dalton Maag.

## Luận điểm cốt lõi

### Mệnh đề

Mô hình nền tảng không mới ở chỗ "lớn hơn thì giỏi hơn", mà mới ở chỗ bước nhảy năng lực mở ra vô số ứng dụng và hạ thấp rào cản gia nhập. Xây ứng dụng tốt trên mô hình nền tảng cần một quy trình kỹ thuật có hệ thống — AI engineering — kết hợp thực hành cũ của học máy với kỹ thuật mới, và quy trình ấy nên được học qua các nền tảng bền vững thay vì qua công cụ.

### Giả định

- Mô hình nền tảng sẽ tiếp tục được dùng rộng rãi và số ứng dụng sẽ tăng theo cấp số nhân.
- Người đọc chủ yếu điều chỉnh mô hình có sẵn chứ không huấn luyện mô hình nền tảng từ đầu.
- Có thể phân biệt khá tin cậy giữa vấn đề căn bản (sẽ còn) và vấn đề tạm thời (sẽ hết khi mô hình tốt hơn).
- Công cụ thay đổi nhanh hơn nhiều so với nguyên lý.

### Cơ chế

- Quy trình phát triển ứng dụng có trình tự: quyết định, hiểu mô hình, đánh giá, cải thiện chất lượng, giảm chi phí và độ trễ, ghép hệ thống và thu phản hồi.
- Chất lượng câu trả lời (ngoài thiết lập sinh) phụ thuộc ba yếu tố có thể điều chỉnh: chỉ dẫn, context, và chính mô hình. Người tổng hợp nhận xét rằng thứ tự Chương 5–7 cũng là thứ tự chi phí tăng dần (prompt rẻ nhất, finetune tốn nhất), khớp cách tiếp cận bắt đầu đơn giản; sách không nói thẳng điều này ở Lời nói đầu.
- Đánh giá đi xuyên mọi bước, vì không đo được thì không biết thay đổi nào có ích.

### Bằng chứng và ví dụ tác giả đưa ra

- Câu trích AlexNet 2012 về GPU và dữ liệu; chú thích về Ilya Sutskever và các mô hình GPT; dự án đánh giá bản dịch năm 2017 của tác giả.
- Mô hình hoá ngôn ngữ có từ thập niên 1950; RAG dựa trên công nghệ tìm kiếm và gợi ý có từ trước.
- Bài học khoá TensorFlow 2017 về tốc độ lỗi thời của công cụ.
- Quy mô công sức: hai năm, hơn 100 cuộc phỏng vấn, khoảng 150.000 từ, 160 hình, 250 chú thích, 975 đường dẫn; hàng nghìn bình luận trên blog.

### Kết luận và hàm ý cho người xây dựng ứng dụng AI

- Đừng coi sự dễ bắt đầu là dấu hiệu dễ làm tốt: từ demo lên production mới là phần khó (hallucination, bảo mật, latency, chi phí).
- Đi theo trình tự: hỏi có cần AI không trước, dựng đánh giá sớm, thử cách rẻ (prompt, context) trước cách đắt (finetune).
- Học nguyên lý để chọn công cụ, không học công cụ thay cho nguyên lý.
- Đặt đúng câu hỏi quan trọng hơn tìm nhanh câu trả lời.

## Thuật ngữ

| Thuật ngữ | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| foundation model | mô hình nền tảng | mô hình lớn dùng làm nền cho nhiều ứng dụng |
| large language model (LLM) | mô hình ngôn ngữ lớn | mô hình nền tảng xử lý văn bản |
| large multimodal model (LMM) | mô hình đa phương thức lớn | mô hình xử lý nhiều loại dữ liệu (chữ, ảnh, âm thanh) |
| AI engineering | AI engineering (kỹ thuật xây dựng ứng dụng AI) | quy trình xây ứng dụng trên mô hình nền tảng |
| ML engineering | kỹ thuật học máy | xây ứng dụng trên mô hình học máy truyền thống |
| AI engineer | kỹ sư AI | người xây ứng dụng trên mô hình nền tảng |
| scaling | mở rộng quy mô | tăng kích thước mô hình và dữ liệu |
| application pattern | mẫu ứng dụng | cách tổ chức ứng dụng lặp lại được (RAG, agent…) |
| use case | use case | trường hợp sử dụng cụ thể |
| hallucination | hallucination | mô hình sinh nội dung sai hoặc bịa |
| prompt engineering | prompt engineering | viết chỉ dẫn để điều khiển mô hình |
| prompt attack | tấn công prompt | kẻ xấu dùng prompt để khai thác ứng dụng |
| context construction | xây dựng context | chuẩn bị thông tin đưa vào cùng truy vấn |
| retrieval-augmented generation (RAG) | sinh có tăng cường truy xuất | truy xuất thông tin rồi đưa vào context |
| agent / agentic pattern | agent / mẫu agent | mô hình tự lập kế hoạch và dùng công cụ |
| finetuning | finetuning | huấn luyện tiếp mô hình để thay đổi nó |
| parameter-efficient finetuning | finetuning tiết kiệm tham số | chỉ cập nhật một phần nhỏ tham số |
| model merging | ghép mô hình | kết hợp nhiều mô hình thành một |
| memory footprint | lượng bộ nhớ chiếm | bộ nhớ cần để chạy hoặc huấn luyện mô hình |
| data synthesis | tổng hợp dữ liệu | tạo dữ liệu nhân tạo (thường bằng AI) |
| data annotation | gán nhãn dữ liệu | thêm nhãn hoặc đáp án cho dữ liệu |
| feature engineering | thiết kế đặc trưng | tạo biến đầu vào cho mô hình truyền thống |
| inference | suy luận | chạy mô hình để sinh đầu ra |
| inference optimization | tối ưu suy luận | làm suy luận rẻ và nhanh hơn |
| inference service | dịch vụ suy luận | hệ thống phục vụ mô hình cho người dùng |
| model API | model API | mô hình do bên khác host, gọi qua API |
| self-hosting | tự host | tự chạy mô hình trên hạ tầng của mình |
| generation setting | thiết lập sinh | tham số điều khiển cách mô hình sinh câu trả lời |
| alignment to human preference | căn chỉnh theo sở thích con người | huấn luyện để mô hình trả lời như người muốn |
| evaluation pipeline | pipeline đánh giá | chuỗi bước đánh giá có hệ thống |
| benchmark | benchmark | bộ kiểm tra chuẩn để so sánh mô hình |
| latency | latency (độ trễ) | thời gian chờ câu trả lời |
| production | production | môi trường chạy thật phục vụ người dùng |
| feedback loop | vòng phản hồi | thu phản hồi để cải thiện liên tục |
| Lindy's Law | Định luật Lindy | tuổi thọ còn lại tỷ lệ với tuổi hiện tại |
| start-simple approach | cách tiếp cận bắt đầu đơn giản | đi từ giải pháp đơn giản tới phức tạp |
| tutorial | sách hướng dẫn | tài liệu dạy dùng công cụ từng bước |
| pseudocode | mã giả | code minh hoạ không chạy được trực tiếp |
| holotype | mẫu chuẩn | mẫu vật gốc dùng để định danh loài |
| colophon | colophon | trang ghi thông tin bìa, phông chữ, in ấn |

## Câu nói đáng nhớ

> "All of our experiments suggest that our results can be improved simply by waiting for faster GPUs and bigger datasets to become available." — nhóm tác giả AlexNet (2012), được trích trong Preface, trang PDF 9
>
> *Dịch: Mọi thí nghiệm của chúng tôi đều gợi ý rằng kết quả có thể được cải thiện chỉ bằng cách chờ GPU nhanh hơn và tập dữ liệu lớn hơn xuất hiện.*
>
> Ý nghĩa: cho thấy quy luật "lớn hơn thì tốt hơn" đã được biết từ hơn mười năm trước ChatGPT.

> "What surprised me was the sheer number of applications this capability boost unlocked." — Preface, trang PDF 9
>
> *Dịch: Điều làm tôi bất ngờ là số lượng khổng lồ các ứng dụng mà bước nhảy năng lực này mở ra.*
>
> Ý nghĩa: đặt trọng tâm của sách vào ứng dụng chứ không vào bản thân mô hình.

> "The familiarity and ease of use of many AI engineering techniques can mislead people into thinking there is nothing new to AI engineering." — Preface, trang PDF 10
>
> *Dịch: Sự quen thuộc và dễ dùng của nhiều kỹ thuật AI engineering có thể khiến người ta lầm tưởng AI engineering chẳng có gì mới.*
>
> Ý nghĩa: lý do tồn tại của cuốn sách — vừa cũ vừa mới.

> "Tools become outdated quickly, but fundamentals should last longer." — What This Book Is About, trang PDF 13
>
> *Dịch: Công cụ lỗi thời nhanh, còn nền tảng thì bền hơn.*
>
> Ý nghĩa: nguyên tắc chọn nội dung của cả cuốn sách.

> "Evaluation is one of the hardest, if not the hardest, challenges of AI engineering." — Navigating This Book, trang PDF 20
>
> *Dịch: Đánh giá là một trong những thách thức khó nhất, nếu không phải là khó nhất, của AI engineering.*
>
> Ý nghĩa: giải thích vì sao sách dành hai chương cho đánh giá.

> "Due to the availability of many finetuning frameworks, the finetuning process itself is often straightforward. However, getting data for finetuning is hard." — Navigating This Book, trang PDF 21
>
> *Dịch: Vì có sẵn nhiều framework finetuning, bản thân việc finetune thường đơn giản. Nhưng có được dữ liệu để finetune thì khó.*
>
> Ý nghĩa: dời trọng tâm từ thuật toán sang dữ liệu.

> "The hardest part of technical writing isn't finding the correct answers but asking the right questions." — Epilogue, trang PDF 930
>
> *Dịch: Phần khó nhất của viết kỹ thuật không phải tìm câu trả lời đúng mà là đặt đúng câu hỏi.*
>
> Ý nghĩa: cũng là tinh thần của sách — đưa ra câu hỏi để chọn giải pháp thay vì đáp án sẵn.

> "AI engineering has a lot of challenges. Not all of them are fun, but all of them are opportunities for growth and impact." — Epilogue, trang PDF 931
>
> *Dịch: AI engineering có rất nhiều thách thức. Không phải cái nào cũng vui, nhưng cái nào cũng là cơ hội để phát triển và tạo tác động.*
>
> Ý nghĩa: lời kết thực tế và khích lệ cho người làm nghề.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Lời nói đầu nói rõ phạm vi (mô hình nền tảng, gồm LLM và LMM), giới hạn (không phải tutorial, không phải lý thuyết học máy), người đọc mục tiêu và — quan trọng nhất — tiêu chí chọn nội dung. Ba tiêu chí "cái gì sẽ còn lâu" là một cam kết phương pháp hiếm thấy trong sách kỹ thuật về một lĩnh vực đổi nhanh, và giải thích vì sao sách ít nói về công cụ cụ thể. Mục "Navigating This Book" biến mười chương thành một quy trình có thứ tự, và cách chia chất lượng câu trả lời thành ba yếu tố (chỉ dẫn, context, mô hình) là bản đồ tư duy hữu ích cho cả cuốn sách. Danh sách mười câu hỏi ở đầu sách đóng vai trò như mục tiêu học tập.

### Những chỗ đơn giản hoá hoặc chưa chặt

- Ba tiêu chí chọn nội dung là định tính; Định luật Lindy là quy tắc kinh nghiệm, áp dụng kém cho lĩnh vực mà phần lớn kỹ thuật mới vài năm tuổi.
- Ranh giới "vấn đề căn bản" và "vấn đề sẽ hết khi mô hình tốt hơn" thường chỉ rõ khi nhìn lại; ví dụ, giới hạn độ dài context từng được coi là căn bản nhưng đã nới ra rất nhanh.
- Mô tả Chương 6 chỉ nêu hai mẫu RAG và agent, trong khi bản thân chương còn bàn về bộ nhớ (memory) cho agent; mục "Navigating" không nhắc.
- Lời kết còn sót câu giữ chỗ "This is some text." và ghi một trang web như là địa chỉ email — lỗi biên tập nhỏ.

### Những gì đã thay đổi từ cuối 2024 (theo hiểu biết của người tổng hợp)

- Mẫu agent mà sách gọi là "còn đang khám phá" đã phát triển nhanh trong 2025: các mô hình suy luận (reasoning models) và agent viết code, agent dùng trình duyệt được triển khai rộng; các giao thức nối mô hình với công cụ như Model Context Protocol (MCP) trở nên phổ biến. Nhận định "RAG ổn định, agent phức tạp hơn" về cơ bản vẫn đúng.
- Rào cản "xây ứng dụng không cần viết code" còn thấp hơn nữa nhờ trợ lý lập trình AI, củng cố luận điểm của Lời nói đầu rằng phần khó đã dời sang đánh giá và vận hành.
- Context của mô hình thương mại phổ biến đã lên tới hàng trăm nghìn hoặc hàng triệu token, làm thay đổi cân nhắc giữa RAG và đưa toàn bộ tài liệu vào context, nhưng không làm mất vai trò của truy xuất.
- Ilya Sutskever (chú thích 1) đã rời OpenAI tháng 5/2024 và lập Safe Superintelligence.

### Liên hệ các chương khác

- [C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md](C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md): có nên xây ứng dụng, use case, khác biệt giữa kỹ thuật học máy và AI engineering.
- [C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md): dữ liệu huấn luyện, kiến trúc, căn chỉnh, cách sinh câu trả lời, hallucination.
- [C03-phuong-phap-danh-gia.md](C03-phuong-phap-danh-gia.md) và [C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md): phương pháp và pipeline đánh giá, dùng AI để đánh giá AI.
- [C05-prompt-engineering.md](C05-prompt-engineering.md): prompt, thực hành tốt, tấn công và phòng thủ.
- [C06-rag-va-agent.md](C06-rag-va-agent.md): context, RAG và agent.
- [C07-finetuning.md](C07-finetuning.md): finetuning, tiết kiệm bộ nhớ, model merging, cách tính bộ nhớ.
- [C08-ky-thuat-du-lieu.md](C08-ky-thuat-du-lieu.md): thu thập, gán nhãn, tổng hợp, xử lý dữ liệu, chất lượng dữ liệu.
- [C09-toi-uu-suy-luan.md](C09-toi-uu-suy-luan.md): tối ưu ở mức mô hình và mức dịch vụ.
- [C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md): kiến trúc từ đầu đến cuối và hệ thống phản hồi người dùng.

### Vận dụng

- **Kỹ sư xây dựng ứng dụng AI:** dùng mục "Navigating This Book" làm danh sách kiểm tra cho dự án: đã trả lời "có cần AI không" chưa; đã có bộ đánh giá trước khi chỉnh prompt chưa; đã thử prompt và context trước khi finetune chưa; ai lo tối ưu suy luận (API hay tự host); có cơ chế thu phản hồi chưa. Khi chọn công nghệ, hỏi theo ba tiêu chí của tác giả: vấn đề này có còn khi mô hình tốt hơn không, chuyên gia nghĩ gì, công nghệ đã tồn tại bao lâu.
- **Người làm tài chính và kinh tế dùng AI:** đọc Chương 1 để quyết định có nên dùng AI cho một tác vụ (phân tích báo cáo, tóm tắt tin tức, trả lời câu hỏi về quy định), Chương 3–4 để biết cách kiểm tra độ đúng trước khi tin vào kết quả — đặc biệt với rủi ro hallucination trong số liệu — và Chương 6 vì RAG trên tài liệu nội bộ thường là mẫu phù hợp nhất cho công việc dựa trên văn bản. Bài học "nền tảng bền hơn công cụ" cũng đúng khi đánh giá các sản phẩm AI cho ngành tài chính: hỏi cách sản phẩm được đánh giá và xử lý dữ liệu, thay vì chỉ xem demo.

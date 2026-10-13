# Kỹ thuật AI — Chip Huyen (2025)

*AI Engineering: Building Applications with Foundation Models.* Mỗi chương được tổng hợp thành một file riêng; Lời nói đầu, Lời kết, Về tác giả và trang Colophon gộp vào một file. File nào cũng đi qua đủ từng mục và tiểu mục của chương theo đúng thứ tự trong sách, chép lại mọi bảng, mô tả và đọc số từ mọi hình, chép prompt mẫu và đoạn code, đưa chú thích cuối chương vào đúng chỗ, và **tính lại mọi phép tính của sách** (số tham số, FLOPs và chi phí huấn luyện, perplexity, bộ nhớ khi finetuning, tham số LoRA, MBU, KV cache, chi phí suy luận…). Sau đó là các khái niệm cần biết, luận điểm cốt lõi, bảng thuật ngữ Anh–Việt, câu nói đáng nhớ và phần đánh giá: chỗ nào sách viết sai hoặc tính nhầm, điều gì đã thay đổi từ cuối 2024, và cách vận dụng cho kỹ sư xây dựng ứng dụng AI cũng như cho người làm tài chính, kinh tế dùng AI.

**Tác giả:** Chip Huyen (Huyền Chip), nhà văn và nhà khoa học máy tính chuyên về hệ thống học máy. Bà từng làm ở NVIDIA và Snorkel AI, sáng lập một startup hạ tầng AI (sau được mua lại) và dạy môn hệ thống học máy ở Đại học Stanford. Bà là tác giả *Designing Machine Learning Systems* (O'Reilly 2022), sách bán chạy trong mảng AI trên Amazon, đã dịch ra hơn 10 thứ tiếng, và bốn sách tiếng Việt bán chạy, trong đó có bộ *Xách ba lô lên và đi*.

**Nguồn:** bản PDF tiếng Anh 991 trang, chuyển từ ePub bằng calibre, của ấn bản đầu tiên (O'Reilly Media, phát hành 4/12/2024, bản quyền 2025; ISBN 978-1-098-16630-4).

> **Lưu ý về nguồn:**
> - **Số trang.** Bản PDF chuyển từ ePub không có số trang in, nên mọi file ghi "trang PDF n" theo số thứ tự trang của bản PDF này; số này không khớp với bản in.
> - **Bản chuyển có lỗi riêng.** Mọi hình là ảnh; người tổng hợp đọc số từ ảnh trang, nên số đọc từ biểu đồ là xấp xỉ (thường sai số 1–2 điểm phần trăm). Nhiều bảng và khung code bị **cắt mép phải** (ví dụ Bảng 1-5, 3-1, 3-6, 4-3, 4-5, 7-2, 7-4, 7-5, 10-1, code model gateway ở Chương 10). Phần bị cắt được khôi phục khi suy ra được từ chính sách (tính đối xứng của bảng, cột số lượng, ngữ cảnh), hoặc ghi rõ là phỏng đoán hay theo trí nhớ của người tổng hợp; chỗ nào không khôi phục được thì ghi là mất. Số thứ tự chú thích cuối chương đã mất trong lớp chữ; chú thích được khớp vào chỗ theo nội dung.
> - **Lỗi của sách; bản tổng hợp ghi cả chữ hoặc số của sách và bản đúng** (nhận xét của người tổng hợp, chưa đối chiếu danh sách đính chính của O'Reilly). Phần lớn là lỗi gõ, năm trích dẫn lệch, hoặc tham chiếu sai số chương. Những lỗi làm thay đổi nội dung:
>   - Lời kết: mở đầu bằng câu giữ chỗ "This is some text." (có trong bản gốc). Địa chỉ huyenchip.com/communication được ghi như một email.
>   - Chương 1: cụm "I can't wait to build AI applications" chỉ có 8 token chứ không phải 9; hình minh hoạ là cụm có thêm chữ "awesome". Số liệu McKinsey bị quy đổi lệch: hình ghi mức *giảm thời gian* 35–45% cho sinh mã, tương đương năng suất tăng 54–82%, không phải "tăng 25–50%". Mô tả CoT@32 là "xem 32 ví dụ" là sai; đó là lấy 32 mẫu trả lời rồi chọn theo đa số (theo hiểu biết của người tổng hợp).
>   - Chương 2: phép tính chi phí huấn luyện GPT-3 dùng "256 ngày" trong khi câu trước ra khoảng 236 ngày (4,14 thay vì 4,49 triệu USD). Sơ đồ transformer giản lược của sách chỉ cho Llama 2-7B khoảng 5,3 tỷ tham số; phải thêm MLP ba ma trận và attention nhóm mới ra 6,74 tỷ. Bảng 2-4 ghi "Llama 3-7B" (đúng là 8B). Loss của reward model thiếu dấu trừ. Sách nói GPT-2 dùng ReLU, thực ra cả GPT-2 và GPT-3 dùng GELU.
>   - Chương 3: Bảng 3-6 (so sánh từng cặp mô hình) có chu trình thắng thua (1 thắng 2, 2 thắng 5, 5 thắng 1) mà sách không nhắc; khớp Bradley–Terry chỉ dự đoán đúng 7/10 cặp. Ví dụ độ tương đồng từ vựng: con số "3/5" là recall, tính theo precision là 3/7.
>   - Chương 4: Bảng 4-5 (tương quan giữa các benchmark) không đối xứng ở ô HellaSwag–TruthfulQA. Bảng 4-6 in đậm nhầm ô; ở nhóm 2, mô hình A mới tốt hơn. Tính lại Hình 4-10 ra −19,2% và +22,1% thay vì −21% và +20%. Sách nói IFEval có 25 loại chỉ dẫn nhưng bảng chỉ có 17 dòng. Bảng cỡ mẫu của OpenAI không nêu giả định; theo kiểm định chuẩn (mức ý nghĩa 5%, lực 80%), số mẫu cần gấp khoảng 4 lần.
>   - Chương 5: "ba thế hệ GPT đầu có context 1K, 2K, 4K" thực ra là GPT-2, GPT-3, GPT-3.5 (GPT-1 chỉ có 512 token). Chú thích hình giải nghĩa sai SVAMP. Prompt khắc phục sự cố router bị rút gọn mất bước khởi động lại.
>   - Chương 6: lời văn định nghĩa IDF là N/C(t) nhưng công thức là log(N/C(t)). Ví dụ RRF (1 + 0,5 = 1,5) ứng với k = 0, trong khi sách khuyên k = 60. Ví dụ lập kế hoạch Kitty Vogue không khớp tên hàm giữa danh sách công cụ và kế hoạch.
>   - Chương 7: Bảng 7-6 ghi LoRA "r=2, query và key", nhưng 3,28M và 18,87M tham số chỉ đúng khi áp cho cả bốn ma trận attention (chỉ q, k thì là 1,64M và 9,44M). Bảng 7-3 có ba ô TF32 cắt bớt thay vì làm tròn. Chú thích ghi GPT-4-0314 ra năm 2024 (đúng là 2023).
>   - Chương 8: 16 nghìn tỷ token của Llama 3 chia 2.000 token mỗi ví dụ là 8 tỷ ví dụ, không phải 15 tỷ. Ví dụ quy trình thu thập dữ liệu ghi lẫn "100 mẫu", "10 mẫu" và "100 chỉ dẫn mỗi mẫu", ba số không khớp nhau. Mixtral-8x7B được gọi là 56 tỷ tham số (thực tế khoảng 46,7 tỷ).
>   - Chương 9: ví dụ MBU ghi "7B × 2 × 100 = 700 GB/s", đúng là 1,4 TB/s; bước sau sách vẫn viết "(700 GB/s) / (2 TB/s) = 70%", phép chia sai, nhưng kết quả 70% lại đúng với 1,4 TB/s. Sách viết ngược chiều tác động của batching ở hai chỗ: batching làm *tăng* throughput và làm độ trễ *tăng*. Sách nói số phép tính attention tăng "theo hàm mũ"; đúng là theo bình phương độ dài. Hình goodput nói 3/10 yêu cầu đạt SLO, số trong hình chỉ cho 2. SLO là service-level objective, không phải "software-level".
>   - Chương 10: code model gateway không chạy được nguyên trạng (thiếu import, khởi tạo Flask, dùng API OpenAI cũ). Trace LangSmith trong hình trả lời "15 điểm" trong khi dữ kiện cho 30 điểm. MTTR được gọi là "mean time to response" nhưng định nghĩa là thời gian xử lý xong. (Ngoài ra, theo nhận xét của người tổng hợp, PyRIT được kể trong danh sách công cụ guardrail nhưng thực chất là công cụ tấn công thử, red teaming.)
> - **Những gì đã thay đổi từ cuối 2024** (mô hình suy luận, MCP, context hàng triệu token, mô hình mở mạnh lên…) được viết **theo hiểu biết của người tổng hợp**, không tra web, và ghi rõ như vậy trong từng file.
> - **Phần người tổng hợp bổ sung.** Công thức sách không in (entropy, KL, BLEU, ROUGE, Elo, Bradley–Terry, BM25, số token kỳ vọng của speculative decoding…), các phép tính minh hoạ và các đoạn "Ví dụ hôm nay" đều ghi rõ là của người tổng hợp.
> - **Sách còn bản quyền.** Bản tổng hợp diễn đạt lại bằng lời mới; câu trích nguyên văn chủ yếu nằm ở mục "Câu nói đáng nhớ", cùng các prompt mẫu và đoạn code ngắn cần cho việc hiểu.
> - **Thuật ngữ.** Các từ phổ biến trong cộng đồng AI Việt Nam (prompt, token, embedding, finetuning, RAG, agent, context, latency, throughput, benchmark, guardrail, LoRA, KV cache…) được giữ tiếng Anh và giải thích ở lần đầu; khái niệm thông thường được dịch sang tiếng Việt.

## Chuỗi lập luận của cả cuốn sách

```text
       LỜI NÓI ĐẦU — SÁCH NÓI VỀ GÌ
       · mô hình nền tảng (foundation model) biến AI từ thứ phải tự huấn
         luyện thành dịch vụ ai cũng gọi được; người xây ứng dụng nay
         phải giải bài toán mới: đánh giá, thích nghi mô hình, chi phí
       · sách dạy khung tư duy và nguyên tắc nền, không dạy công cụ cụ thể
                                │
                                ▼
       CHƯƠNG 1 — TỔNG QUAN: KỸ THUẬT AI LÀ GÌ
       · từ mô hình ngôn ngữ → mô hình ngôn ngữ lớn (tự giám sát)
         → mô hình nền tảng (đa phương thức)
       · các nhóm ứng dụng; cách lên kế hoạch một ứng dụng AI
       · ba tầng: phát triển ứng dụng, phát triển mô hình, hạ tầng;
         kỹ thuật AI khác kỹ thuật học máy truyền thống ở chỗ thích nghi
         mô hình có sẵn thay vì tự huấn luyện, và đánh giá khó hơn
                                │
                                ▼
       CHƯƠNG 2 — HIỂU MÔ HÌNH NỀN TẢNG
       · dữ liệu huấn luyện quyết định mô hình giỏi gì (ngôn ngữ, lĩnh vực)
       · kiến trúc transformer, cỡ mô hình, quy luật Chinchilla
       · post-training: SFT và finetuning theo sở thích (RLHF, DPO)
       · sampling: temperature, top-k, top-p; vì sao AI không nhất quán
         và bịa (hallucination)
                                │
                                ▼
       CHƯƠNG 3–4 — ĐÁNH GIÁ
       · C3: độ đo mô hình ngôn ngữ (cross entropy, perplexity), đánh giá
         chính xác (chạy code, so với đáp án mẫu, embedding), dùng AI
         làm giám khảo, xếp hạng bằng so sánh từng cặp
       · C4: tiêu chí đánh giá ứng dụng (năng lực lĩnh vực, chất lượng sinh,
         làm theo chỉ dẫn, chi phí, độ trễ); chọn mô hình, tự host hay
         dùng API, đọc benchmark công khai; dựng quy trình đánh giá
                                │
                                ▼
       CHƯƠNG 5–8 — THÍCH NGHI MÔ HÌNH, TỪ RẺ ĐẾN ĐẮT
       · C5: prompt engineering và phòng thủ trước tấn công prompt
       · C6: RAG (truy xuất thông tin đưa vào context) và agent (mô hình
         dùng công cụ, lập kế hoạch), cùng bộ nhớ
       · C7: finetuning: khi nào nên, bộ nhớ cần bao nhiêu, LoRA,
         lượng tử hoá, gộp mô hình
       · C8: kỹ thuật dữ liệu: chọn lọc, tổng hợp bằng AI, chưng cất,
         làm sạch và định dạng dữ liệu
                                │
                                ▼
       CHƯƠNG 9 — TỐI ƯU SUY LUẬN
       · độ đo: TTFT, TPOT, throughput, goodput, MFU, MBU; bộ tăng tốc AI
       · tối ưu mô hình (lượng tử hoá, speculative decoding, KV cache,
         attention hiệu quả) và tối ưu dịch vụ (batching, prompt caching,
         song song hoá)
                                │
                                ▼
       CHƯƠNG 10 — KIẾN TRÚC VÀ PHẢN HỒI NGƯỜI DÙNG
       · lắp hệ thống từng bước: thêm context, guardrail, router và
         gateway, cache, mẫu agent; giám sát và điều phối pipeline
       · thu thập và thiết kế phản hồi người dùng để cải thiện ứng dụng
```

## Mục lục

- [Lời nói đầu, Lời kết và Về tác giả](00-loi-noi-dau.md) (Preface, Epilogue, About the Author): sách nói về gì và không nói về gì, dành cho ai, cấu trúc 10 chương, lời cảm ơn; lời kết; tiểu sử tác giả; con cú Oman trên bìa
- [Chương 1 — Giới thiệu về xây dựng ứng dụng AI với mô hình nền tảng](C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md) (Introduction to Building AI Applications with Foundation Models)
- [Chương 2 — Hiểu về mô hình nền tảng](C02-hieu-ve-mo-hinh-nen-tang.md) (Understanding Foundation Models)
- [Chương 3 — Phương pháp đánh giá](C03-phuong-phap-danh-gia.md) (Evaluation Methodology)
- [Chương 4 — Đánh giá hệ thống AI](C04-danh-gia-he-thong-ai.md) (Evaluate AI Systems)
- [Chương 5 — Prompt engineering](C05-prompt-engineering.md) (Prompt Engineering)
- [Chương 6 — RAG và agent](C06-rag-va-agent.md) (RAG and Agents)
- [Chương 7 — Finetuning](C07-finetuning.md) (Finetuning)
- [Chương 8 — Kỹ thuật dữ liệu](C08-ky-thuat-du-lieu.md) (Dataset Engineering)
- [Chương 9 — Tối ưu suy luận](C09-toi-uu-suy-luan.md) (Inference Optimization)
- [Chương 10 — Kiến trúc kỹ thuật AI và phản hồi người dùng](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md) (AI Engineering Architecture and User Feedback)

## Gợi ý đọc

- **Đọc trước tiên:** Lời nói đầu và Chương 1 để nắm toàn cảnh, rồi Chương 3–4 (đánh giá). Tác giả coi đánh giá là việc khó nhất và quan trọng nhất của kỹ thuật AI.
- **Muốn làm ứng dụng ngay:** Chương 5 (prompt), rồi Chương 6 (RAG, agent), rồi Chương 10 (kiến trúc). Ba chương này dùng được mà không cần huấn luyện mô hình.
- **Muốn hiểu bên trong mô hình:** Chương 2, rồi Chương 7 (bộ nhớ, biểu diễn số, LoRA) và Chương 9 (suy luận); đây là ba chương nhiều phép tính nhất.
- **Người làm tài chính, kinh tế dùng AI:** Chương 1 (đánh giá ca sử dụng, kỳ vọng và chi phí), Chương 4 (chọn mô hình, tự host hay mua API), Chương 6 (RAG cho tài liệu nội bộ) và Chương 10 (guardrail, giám sát). Đọc kèm Chương 3–4 để biết vì sao không nên tin ngay một điểm benchmark.
- **Liên hệ trong repo:** đọc kèm [The Art of Statistics](../The%20Art%20of%20Statistics/README.md) cho khoảng tin cậy, cỡ mẫu và kiểm định (dùng ở Chương 3–4), và các bài trong mục AI and Fintech, ví dụ [Hứa hẹn và hiểm hoạ của AI](../../IMF/Back%20to%20Basics/2023-12-artificial-intelligences-promise-and-peril.md) và [AI tác tử sẽ định hình lại thanh toán như thế nào](../../IMF/AI%20and%20Fintech/2026-agentic-ai-reshape-payments.md).

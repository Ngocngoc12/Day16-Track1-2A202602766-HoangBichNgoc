# Memo Teardown — ChatGPT

**Họ tên:** Hoàng Bích Ngọc  
**Ngày hoàn thiện:** 03/10/2026

**Vì sao chọn sản phẩm này:**

ChatGPT là một sản phẩm AI-native có dữ liệu công khai dày, đồng thời cho thấy rõ quá trình đi từ chatbot hỏi–đáp sang một lớp giao diện cho model, công cụ, dữ liệu cá nhân và các tác vụ nhiều bước. Đây là lựa chọn phù hợp để quan sát cả năng lực model lẫn các quyết định product khiến người dùng quay lại.

> **Phạm vi phân tích:** Các mốc dưới đây là các quyết định sản phẩm lớn, không phải toàn bộ changelog. Các liên kết là nguồn gốc công khai, chủ yếu từ OpenAI. Phần “nguyên lý”, phân tích JTBD và dự đoán là nhận định của người viết dựa trên các nguồn đó.

## §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| 30/11/2022 — [Introducing ChatGPT](https://openai.com/index/chatgpt/) | OpenAI ra mắt ChatGPT dưới dạng research preview miễn phí, tập trung vào hội thoại nhiều lượt, hỏi tiếp, thừa nhận sai và từ chối yêu cầu không phù hợp. | Người dùng phổ thông chưa có một giao diện đơn giản để trực tiếp thử model ngôn ngữ mạnh. OpenAI ưu tiên đưa sản phẩm ra để quan sát cách người thật sử dụng và tìm giới hạn của model. | **Vòng lặp học:** tung sản phẩm đủ đơn giản để có thật nhiều tương tác, sau đó dùng feedback và lỗi thực tế để cải thiện model, safety và UX. |
| 14/03/2023 — [GPT-4 in ChatGPT](https://openai.com/index/gpt-4/) | Đưa GPT-4 vào ChatGPT Plus, với năng lực reasoning, làm theo chỉ dẫn và sáng tạo tốt hơn; đồng thời duy trì giới hạn sử dụng. | Nhu cầu vượt quá một chatbot thử nghiệm: người dùng muốn dùng cho học tập, viết, lập trình và công việc có giá trị cao hơn. GPT-4 cũng đắt và giới hạn hơn GPT-3.5. | **x10 bằng chất lượng:** khi năng lực model cải thiện đủ lớn, chuyển từ “trả lời được” sang “đáng tin và làm được việc khó hơn”; **freemium như cơ chế phân tầng giá trị**. |
| 06/11/2023 — [Introducing GPTs](https://openai.com/index/introducing-gpts/) | Cho phép người dùng tạo các phiên bản ChatGPT tùy chỉnh bằng instructions, knowledge và tools; mở hướng chia sẻ GPT và GPT Store. | ChatGPT đã có lượng người dùng lớn nhưng prompt và quy trình vẫn nằm trong đầu từng người. OpenAI cần biến use case cá nhân thành cấu hình có thể lặp lại, chia sẻ và dùng trong doanh nghiệp. | **Wrapper/moat từ workflow:** model nền có thể bị đối thủ sao chép, nhưng instructions, dữ liệu, actions và workflow cụ thể tạo ra giá trị sử dụng cao hơn một ô chat trống. |
| 13/02/2024, mở rộng trong 2024–2025 — [Memory and new controls](https://openai.com/index/memory-and-new-controls-for-chatgpt/) | ChatGPT bắt đầu ghi nhớ thông tin người dùng; sau đó mở rộng memory cho nhiều gói và tham chiếu ngữ cảnh từ các cuộc trò chuyện trước. | Nếu mỗi cuộc trò chuyện bắt đầu từ số 0, người dùng phải lặp lại sở thích, dự án và bối cảnh. Khi ChatGPT được dùng thường xuyên, cá nhân hóa trở thành lợi thế quan trọng hơn một câu trả lời đơn lẻ. | **Tăng switching cost bằng context:** dữ liệu và hiểu biết tích lũy về người dùng làm sản phẩm hữu ích hơn theo thời gian; đồng thời phải có quyền xem, sửa, xóa và tắt memory để giữ niềm tin. |
| 13/05/2024 — [GPT-4o and more tools to ChatGPT free users](https://openai.com/index/gpt-4o-and-more-tools-to-chatgpt-free/) | Ra mắt GPT-4o, nhanh hơn và có năng lực text, vision, audio; đồng thời đưa thêm nhiều công cụ nâng cao tới người dùng miễn phí. | Chatbot text-only bắt đầu giống nhau giữa các đối thủ. Tốc độ, giọng nói, hình ảnh và khả năng tương tác tự nhiên là cách mở rộng use case khỏi việc gõ prompt. | **x10 về trải nghiệm, không chỉ benchmark:** giảm friction và đưa AI vào bối cảnh đời thực; **phân phối trước, thu tiền sau** bằng cách cho free user trải nghiệm đủ tốt rồi phân tầng usage. |
| 02/02/2025 — [Introducing deep research](https://openai.com/index/introducing-deep-research/) | Deep research cho phép ChatGPT tự lập kế hoạch, duyệt web, phân tích nhiều nguồn và tạo báo cáo có trích dẫn; sau đó mở rộng thêm agent mode, nguồn kết nối và giới hạn sử dụng. | Người dùng không chỉ cần câu trả lời tức thời mà còn cần hoàn thành công việc nghiên cứu nhiều bước. Đây là vùng mà chatbot thông thường dễ bị giới hạn bởi thời gian, context và khả năng kiểm chứng. | **Từ copilot sang agent:** giá trị chuyển từ “sinh text” sang “hoàn thành task”; **định nghĩa ‘tốt’ = kết quả có thể kiểm chứng**, không chỉ câu trả lời nghe hay. |
| 07/08/2025 — [Introducing GPT-5](https://openai.com/index/introducing-gpt-5/) | GPT-5 trở thành hệ thống mặc định mới trong ChatGPT, kết hợp trả lời nhanh, reasoning sâu và router tự chọn cách xử lý; mở rộng cho writing, coding, health và công việc chuyên môn. | Người dùng không muốn tự chọn giữa quá nhiều model hoặc biết trước câu hỏi thuộc loại nào. ChatGPT cần biến tiến bộ model thành trải nghiệm “một sản phẩm, nhiều chế độ thông minh”. | **Ẩn complexity sau một interface:** dùng router và feedback thực tế để tự chọn model; **vòng lặp học** tiếp tục nằm trong routing, preference và correctness signals. |
| 03/09/2026 — [Introducing GPT-6 Astra](https://openai.com/index/gpt-6-astra/) và các cập nhật ChatGPT Work | GPT-6 Astra được giới thiệu cho công việc nhiều bước: computer use, browsing, coding và tạo document, spreadsheet, presentation theo template; ChatGPT Work và các gói ngành dọc tiếp tục được mở rộng. | ChatGPT đã vượt khỏi use case cá nhân và bắt đầu cạnh tranh ở workflow của tổ chức. Khi model có thể thao tác qua công cụ, lợi thế không còn chỉ là câu trả lời mà là độ hoàn chỉnh của đầu ra và khả năng tuân theo chuẩn doanh nghiệp. | **Vertical AI = AI Expert + Domain Expert:** năng lực model được ghép với dữ liệu, template, quyền truy cập và quy trình ngành; **moat nằm trong workflow và trust**, không chỉ trong model. |

### Vì sao chọn những mốc này

Tôi chọn các mốc làm thay đổi “đơn vị giá trị” của ChatGPT: từ hội thoại (2022), sang model cao cấp có trả phí (2023), tùy chỉnh và cộng đồng (GPTs), cá nhân hóa (memory), tương tác đa phương thức (GPT-4o), hoàn thành nghiên cứu (deep research), tự động điều phối reasoning (GPT-5), rồi thực thi công việc chuyên môn (GPT-6 Astra/Work). Tôi loại các cập nhật nhỏ về giao diện, giới hạn hoặc sửa lỗi vì chúng không đủ làm thay đổi tệp user hoặc cách sản phẩm tạo giá trị. Các cập nhật memory trong 2025 và deep research trong 2026 được gộp vào mốc lớn tương ứng thay vì tách thành nhiều hàng changelog.

## §2. Tệp user & JTBD

| | Early adopters | Tệp hiện tại |
|---|---|---|
| **Đặc điểm** | Người dùng công nghệ, sinh viên, developer và knowledge worker tò mò; sẵn sàng thử sản phẩm chưa hoàn thiện, chấp nhận kiểm chứng câu trả lời và tự học cách viết prompt. Một ví dụ cụ thể là sinh viên hoặc lập trình viên cá nhân đã quen dùng công cụ web/IDE và cần tăng tốc một việc ngay trong ngày. | Phổ rộng hơn: học sinh–sinh viên, người viết nội dung, nhân viên văn phòng, lập trình viên, người làm nghiên cứu, gia đình và team/doanh nghiệp. Các nhóm mới không nhất thiết hiểu model; họ kỳ vọng ChatGPT tự chọn cách xử lý, nhớ bối cảnh, tìm nguồn và tạo ra file/đầu ra dùng được. |
| **JTBD chính** | “Khi gặp một việc trí óc bị mắc hoặc tốn thời gian, tôi muốn có một đối tác phản hồi ngay để thử ý tưởng, giải thích khái niệm, sửa code hoặc tạo bản nháp đầu tiên, để tôi tiến thêm một bước mà không phải tìm chuyên gia.” | “Khi phải hoàn thành một công việc nhiều bước trong học tập hoặc công việc, tôi muốn giao cho một trợ lý hiểu bối cảnh của mình, biết tìm và tổng hợp thông tin, rồi tạo đầu ra theo yêu cầu, để tôi giảm thời gian từ câu hỏi đến kết quả có thể sử dụng.” |
| **Trước đó họ làm bằng cách nào** | Google Search, Stack Overflow, diễn đàn, sách/tài liệu, tự viết code, hỏi đồng nghiệp hoặc thuê người khác. Các cách này thường hữu ích nhưng bị chia nhỏ theo nguồn và có độ trễ cao. | Kết hợp search engine, spreadsheet, email, docs, ứng dụng chuyên môn, trợ lý con người và nhiều công cụ AI riêng lẻ. ChatGPT cố gắng gom các bước vào một giao diện có memory, tools, connectors, browsing và agentic work. |

### Dịch chuyển tệp

Mốc **GPT-4** nâng ChatGPT từ một thử nghiệm thú vị thành công cụ có thể dùng cho việc học và knowledge work. **GPTs** và **memory** khiến sản phẩm phù hợp hơn với các workflow lặp lại và nhu cầu cá nhân hóa. **GPT-4o** hạ friction cho người không muốn gõ prompt dài. **Deep research**, **GPT-5** và **GPT-6 Astra/Work** tiếp tục kéo sản phẩm sang tệp chuyên môn và doanh nghiệp: họ không chỉ muốn “nói chuyện với AI” mà muốn hoàn thành một deliverable có nguồn, có cấu trúc và có thể đưa vào quy trình.

### Switching cost — map 4 forces

| Force | Phân tích với ChatGPT |
|---|---|
| **Push — vấn đề với cách hiện tại** | Search, copy–paste giữa nhiều ứng dụng và tự làm các bước nghiên cứu mất thời gian. Người dùng cũng gặp vấn đề khi phải lặp lại bối cảnh, viết nháp, xử lý file hoặc học công cụ mới cho từng task. |
| **Pull — sức hút của phương án mới** | ChatGPT kết hợp hội thoại, model mạnh, voice/vision, memory, web search, deep research, GPTs, connectors và tạo tài liệu. Lời hứa hấp dẫn nhất là giảm thời gian từ ý định đến đầu ra, đặc biệt với task cần nhiều bước. |
| **Anxiety — nỗi lo khi chuyển sang** | Lo hallucination, nguồn không đáng tin, rò rỉ dữ liệu, memory nhớ sai, chi phí gói trả phí và việc AI làm thay nhưng không minh bạch. Với doanh nghiệp, còn có rủi ro quyền truy cập, compliance và chất lượng đầu ra không đồng đều. |
| **Habit — thói quen cũ** | Người dùng đã quen Google, Office/Docs, IDE, email và đồng nghiệp chuyên môn. Họ cũng quen tự kiểm tra bằng nhiều nguồn. ChatGPT phải thắng bằng việc nằm trên các workflow đó, chứ không chỉ yêu cầu người dùng bỏ hết công cụ cũ. |

**Lực giữ user mạnh nhất:** là sự kết hợp giữa *context tích lũy* và *workflow đã được đóng gói*. Memory, Projects, GPTs, file, lịch sử chat và connectors khiến ChatGPT ngày càng hiểu người dùng; đồng thời deep research/Work biến nó thành nơi bắt đầu và kết thúc của một số task. Nếu lực này biến mất — ví dụ memory không chính xác, export dữ liệu dễ dàng và đối thủ có cùng chất lượng agent — switching cost sẽ giảm mạnh vì model nền có thể bị thay thế tương đối dễ.

## §3. Ba dự đoán hướng đi (6–12 tháng tới)

### Dự đoán 1 *(loại: mở rộng tính năng / agent)*

- **Dự đoán:** Trong giai đoạn 10/2026–10/2027, ChatGPT sẽ đẩy mạnh “Work” và các agent có thể hoàn thành chuỗi việc end-to-end: đọc nguồn, dùng ứng dụng được kết nối, tạo file, xin phê duyệt ở điểm nhạy cảm và tiếp tục chạy theo lịch.
- **Lập luận:** Deep research đã chuyển từ trả lời sang nghiên cứu nhiều bước; GPT-5 đưa reasoning vào router mặc định; GPT-6 Astra bổ sung computer use và tạo document/spreadsheet/presentation theo template. Khi đơn vị giá trị đã là “task hoàn thành”, bước tự nhiên tiếp theo là agent chạy lâu hơn và phối hợp với công cụ người dùng.

### Dự đoán 2 *(loại: mở rộng segment / Vertical AI)*

- **Dự đoán:** ChatGPT sẽ mở rộng các gói chuyên biệt cho những ngành có dữ liệu và workflow rõ như tài chính, nghiên cứu, y tế, giáo dục và customer support, thay vì chỉ bán một chatbot chung cho mọi người.
- **Lập luận:** Tệp user đã dịch từ early adopters sang tổ chức; GPT-6 Astra nhấn mạnh công việc chuyên môn, còn ChatGPT for Financial Services cho thấy hướng ghép model với dữ liệu premium, citation và design partner. Đây là cách tạo moat bằng domain expertise, permission và trust — những thứ khó bị model khác sao chép chỉ bằng cách bắt chước giao diện chat.

### Dự đoán 3 *(loại: mô hình kiếm tiền / phân phối)*

- **Dự đoán:** OpenAI sẽ tiếp tục phân tầng mạnh giữa Free/Go, Plus/Pro và Work/Enterprise: free dùng để mở rộng distribution, còn reasoning cao, agent usage, connectors, dữ liệu ngành và tốc độ cao sẽ là các biến số kiếm tiền; quảng cáo hoặc commerce có thể xuất hiện ở các use case tiêu dùng nhưng sẽ được tách khỏi trải nghiệm trả phí.
- **Lập luận:** Từ GPT-4 trả phí đến GPT-4o mở rộng cho free, GPT-5 theo usage/plan và GPT-6 Astra có tier tốc độ cao, sản phẩm liên tục dùng freemium để mở adoption rồi thu tiền theo compute và giá trị công việc. Changelog 2026 cũng cho thấy thử nghiệm ads ở Free/Go và các trải nghiệm tài chính/mua sắm; điều đó gợi ý ChatGPT đang xây nhiều “điểm kiếm tiền” quanh intent của user, trong khi phải giữ trust ở các gói chuyên nghiệp.

**Dự đoán tôi tự tin nhất:** Dự đoán 1, vì cả ba mốc deep research, GPT-5 và GPT-6 Astra đều cùng hướng từ chat sang agentic execution. Giả định có thể làm dự đoán này gãy là độ tin cậy và chi phí: nếu agent vẫn thường xuyên thao tác sai, cần người giám sát quá nhiều hoặc chi phí inference không giảm đủ, ChatGPT sẽ phải giữ Work ở dạng copilot thay vì tự động hóa end-to-end.

## §4. AI Log

| Việc | AI làm hay bạn làm? | Bạn kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tìm các mốc phát hành, ngày tháng và nguồn công khai | **AI hỗ trợ tìm kiếm và lập danh sách ứng viên.** | Mở lại từng trang OpenAI/Help Center được dẫn, đối chiếu ngày và nội dung; chỉ giữ các mốc có nguồn gốc công khai, loại các kết quả trùng hoặc chỉ là cập nhật nhỏ. |
| Chọn 8 cột mốc đưa vào timeline | **Bạn quyết định.** | Dùng tiêu chí “có làm thay đổi đơn vị giá trị, segment hoặc cách ChatGPT tạo moat không”; vì vậy không đưa các bản vá giao diện vào timeline chính. |
| Viết context và revert về nguyên lý x10, wrapper/moat, Vertical AI, vòng lặp học | **AI đề xuất diễn giải ban đầu; bạn phán đoán và biên tập.** | Kiểm tra mỗi nguyên lý có gắn với một quyết định cụ thể trong mốc hay không; loại nhãn chung chung như “để tăng trưởng” và thay bằng khái niệm có tên. |
| Phân tích early adopters, tệp hiện tại và JTBD | **Bạn làm phần phán đoán; AI hỗ trợ cấu trúc hóa.** | Kiểm tra JTBD có mô tả “việc cần hoàn thành” thay vì tên tính năng; đối chiếu sự dịch chuyển với các mốc GPT-4, GPTs, memory, deep research và Work. |
| Map switching cost theo 4 forces | **AI hỗ trợ tạo khung; bạn chịu trách nhiệm nội dung.** | Tách rõ Push, Pull, Anxiety, Habit và kiểm tra lực giữ user có liên quan đến dữ liệu/context/workflow thật, không chỉ là “user thích sản phẩm”. |
| Viết 3 dự đoán 6–12 tháng | **Bạn phán đoán, dựa trên dữ liệu đã phân tích; AI hỗ trợ diễn đạt.** | Mỗi dự đoán phải trỏ ngược được về ít nhất một mốc timeline và một nhận định về user/switching cost; ghi rõ đây là dự đoán, không phải thông tin đã xảy ra. |
| Kiểm tra memo cuối | **AI hỗ trợ checklist; bạn kiểm tra lần cuối.** | Đối chiếu đủ 4 phần, đủ 6–8 mốc, mỗi mốc có link, AI log có ít nhất 3 hàng và mọi hàng đều có cột kiểm chứng/phán đoán. |

### Câu hỏi phản biện cuối

Phần AI làm thay nhiều nhất là việc gom nguồn và dựng bản nháp timeline. Nếu bỏ phần đó, tôi vẫn có thể tự giải thích vì sao chọn các mốc, vì sao ChatGPT tạo switching cost từ context/workflow, và vì sao hướng đi tiếp theo là agent + vertical workflow. Tuy nhiên, tôi vẫn phải tự mở lại nguồn gốc trước khi coi ngày tháng và nội dung phát hành là đúng.

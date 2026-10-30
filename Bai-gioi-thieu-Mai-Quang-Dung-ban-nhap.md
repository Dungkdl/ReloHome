# Bản nháp giới thiệu bản thân sau 6 tuần AI thực chiến

> Ghi chú biên tập — xóa trước khi gửi: Bản này được đối chiếu với hai CV và lịch sử mã nguồn ReloHome. Những chỗ trong ngoặc vuông cần bạn tự điền/xác nhận. Điểm kỹ năng và hai vai trò là đề xuất, không phải kết quả đánh giá. Số liệu kiểm thử/hiệu năng là bằng chứng lịch sử có ngày và phạm vi cụ thể, không phải kết quả vừa chạy lại. Không suy từ tên tác giả commit rằng mọi dòng code đều do bạn tự viết. Các mục trải nghiệm cá nhân và mức đóng góp của AI phải được bạn xác nhận.

**Tiêu đề email:** Giới thiệu bản thân sau 6 tuần AI thực chiến — Mai Quang Dũng — 2A202602966

Kính gửi anh/chị,

Em là Mai Quang Dũng, mã học viên 2A202602966, sinh viên ngành Khoa học dữ liệu, Trường Đại học Khoa học Tự nhiên, ĐHQG TP.HCM. Định hướng của em là phát triển ứng dụng AI, đặc biệt là AI agent, RAG và các hệ thống kết nối mô hình với dữ liệu, công cụ và quy trình nghiệp vụ.

Sau 6 tuần học, điều em muốn thể hiện là khả năng tham gia xây dựng một hệ thống có nhiều thành phần và có bằng chứng kiểm chứng, bên cạnh kinh nghiệm làm mô hình và ứng dụng AI trước đó. Dưới đây là phần tự nhìn lại của em.

## 1. Trước và sau 6 tuần

Trước khóa học, em đã có nền tảng Python, SQL, machine learning và xây dựng ứng dụng với FastAPI, Docker. Em từng thực hiện Taxi Fare Prediction ML Pipeline với các bước tiền xử lý, huấn luyện, tối ưu và đánh giá mô hình; XGBoost đạt R² = 0,961, RMSE = 6,67 và MAE = 3,98 trên tập kiểm thử của dự án. Em cũng đã làm Agentic Python Repo RAG Copilot, kết hợp phân tích mã nguồn bằng AST, tìm kiếm hybrid, reranking và bộ đánh giá 50 trường hợp. Vì vậy, em không bắt đầu khóa học từ mức chưa biết AI hoặc chưa từng làm RAG.

Sau khóa học, phần kinh nghiệm bổ sung rõ nhất của em là tham gia ReloHome: từ dữ liệu địa điểm, tìm nhà và công cụ MCP đến giao diện, API và chức năng tìm người ở ghép. Em tiếp xúc với việc phối hợp Python và TypeScript trong cùng hệ thống, quản lý contract giữa các dịch vụ, xử lý trạng thái người dùng và kiểm thử các luồng đi qua nhiều thành phần.

Trong CV hiện tại, em còn có FinSight, hệ thống dự báo tiền mã hóa kết hợp các nhánh mô hình định lượng, tin tức, dữ liệu cơ bản và tổng hợp kết quả. Dự án có sử dụng LightGBM/GRU, walk-forward validation và quy trình domain adaptation, knowledge distillation cho FinBERT. Em xem đây là phần kinh nghiệm bổ sung về mô hình và đánh giá; ReloHome là sản phẩm em chọn để trình bày sâu về quá trình làm việc nhóm trong khóa học. **[Nếu đề cập mốc trước/sau 6 tuần của FinSight, hãy điền đúng thời gian thực hiện; không tự gán toàn bộ dự án vào khóa học.]**

Một minh chứng là đợt tối ưu truy vấn Housing ngày 10/10. Trong benchmark local dùng cùng dữ liệu và request, lấy trung vị của 3 lần chạy, truy vấn tìm kiếm theo chữ giảm thời gian SQL từ 274,18 ms xuống 28,33 ms. Đợt kiểm chứng đi kèm 24 bộ request và 65 phép so sánh với code gốc để kiểm tra việc tối ưu có giữ nguyên kết quả. Đây là số đo SQL trên môi trường local, không phải độ trễ toàn bộ ứng dụng hoặc cam kết hiệu năng production.

## 2. Sản phẩm tốt nhất trong khóa: ReloHome

ReloHome là sản phẩm của nhóm, hướng đến hỗ trợ người có nhu cầu chuyển nơi ở: tìm nhà, xem địa điểm và tiện ích trên bản đồ, tìm người ở ghép, yêu cầu báo giá chuyển đồ và tra cứu chuyến bay. Khó khăn của bài toán là những nhu cầu này liên quan với nhau, trong khi dữ liệu và dịch vụ được cung cấp từ nhiều nguồn.

Phần đóng góp của em tập trung vào Location/Housing/Map, dữ liệu và truy vấn, giao diện cùng một số luồng tích hợp; sau đó mở rộng sang Roommate. Ví dụ, em tham gia xây dựng công cụ Location MCP như `search_areas`, `resolve_location`, `search_housing` và `calculate_route_between_entities`. Các công cụ này cung cấp dữ liệu và phép tính cụ thể để tầng agent sử dụng. Với Roommate, em tham gia các phần hồ sơ, tìm kiếm, lời mời kết nối, quyền truy cập và tích hợp vào luồng hội thoại.

Hệ thống sử dụng Python/FastAPI/LangGraph cho tầng agent, TypeScript cho giao diện và nhiều dịch vụ nghiệp vụ, PostgreSQL/PostGIS cho dữ liệu không gian, OSRM cho định tuyến. Mô hình ngôn ngữ có sẵn được gọi qua API để hiểu yêu cầu, lập kế hoạch và xử lý hội thoại. Phần ReloHome em trình bày ở đây không phải một dự án tự pre-train mô hình.

Em sử dụng **[điền đúng công cụ đã dùng: Codex, Claude Code hoặc công cụ khác]** trong quá trình phát triển. AI hỗ trợ **[điền phần thực tế: phân tích repository, đề xuất phương án, sinh bản nháp code/test, rà lỗi hoặc viết tài liệu]**. Phần em trực tiếp thực hiện và chịu trách nhiệm là **[nêu cụ thể việc bạn tự làm: chốt yêu cầu, đọc và sửa đoạn code nào, chạy thử tình huống nào, đối chiếu dữ liệu nào; không chỉ ghi “review code”]**.

Một kết quả khác được ghi nhận trong đợt bàn giao Roommate ngày 07/10 là 169 kiểm thử thuộc phạm vi backend/API/agent đạt. Những kiểm thử này bao gồm luồng session gateway → API → SQLite thật, xử lý retry, quyền truy cập và consent; không đồng nghĩa 169 bài kiểm thử trình duyệt hoặc toàn bộ hệ thống đã đạt mọi điều kiện phát hành. Ở checkpoint này, suite toàn dự án vẫn có 29 lỗi baseline được ghi riêng.

Nếu làm lại, em sẽ **[tự điền điều thực sự muốn đổi]**. Một hướng em có thể cân nhắc là chốt sớm một luồng người dùng xuyên suốt, contract dữ liệu và bộ kiểm thử chấp nhận tối thiểu, rồi mở rộng từng phần. **[Chỉ giữ hướng này nếu đúng nhận xét của bạn; thêm một tình huống thật cho thấy nó cần thiết.]**

- Repository: https://github.com/AI20K-Build-Phase-Cohort-4/P-044
- Website được ghi trong README của dự án: https://c4-app-044.io.vn/
- Ví dụ commit đóng góp: `1f0d7fa` — POI, routing và Housing; `56a6ca9` — lọc và phân trang trước khi lấy chi tiết Housing; `f31120b` — đăng ký capability Roommate chỉ đọc cho agent.

## 3. Một lần AI làm sai

Trong lúc làm **[tên chức năng]**, em yêu cầu AI **[yêu cầu cụ thể]**. AI đã **[mô tả chính xác kết quả sai, có thể dẫn file/đoạn code hoặc đầu ra]**.

Em phát hiện vấn đề khi **[mô tả test thất bại, dữ liệu đối chiếu hoặc thao tác thực tế]**. Sau khi kiểm tra **[nguồn dữ liệu/tài liệu/code]**, em xác định nguyên nhân là **[nguyên nhân]**. Em đã **[cách sửa]** và kiểm chứng lại bằng **[test/lệnh/thao tác, kèm kết quả]**.

Từ đó, em đặt quy tắc **[quy tắc bản thân thực sự áp dụng]**. Ví dụ có thể là yêu cầu bằng chứng trước khi chấp nhận thay đổi, giữ test hồi quy, hoặc luôn kiểm tra dữ liệu trước và sau thao tác ghi — hãy chọn quy tắc gắn trực tiếp với sự cố vừa kể.

## 4. Điều khó nhất hoặc chưa hiểu rõ

Điều em còn thấy khó là **[một vấn đề cụ thể]**. Khó khăn thể hiện ở **[một tình huống trong dự án]**, vì **[nguyên nhân bạn thực sự chưa hiểu hoặc chưa xử lý tốt]**.

Em đã thử **[những cách đã làm, kèm kết quả]**. Hiện tại, em làm được **[phạm vi đã hiểu]**, nhưng còn chưa rõ **[ranh giới còn thiếu]**. Để tiến bộ, em cần **[tài liệu, bài tập, feedback hoặc hướng dẫn cụ thể]**.

## 5. Làm việc nhóm

Trong nhóm, em thường nhận vai trò **[vai trò thực tế]**. Một việc thể hiện vai trò đó là **[tình huống, phần bạn nhận và kết quả]**. Các phần đóng góp được ghi trong repo của em gồm Location/Housing/Map, Roommate và những tài liệu bàn giao liên quan; em sẽ trình bày rõ đâu là phần của em và đâu là kết quả chung của nhóm.

Một lần nhóm có ý kiến khác nhau về **[vấn đề]**: em đề xuất **[phương án A]**, còn **[thành viên/vai trò]** đề xuất **[phương án B]**. Em đã xử lý bằng **[cách trao đổi, thử nghiệm hoặc phân chia công việc thực tế]**. Nhóm thống nhất **[quyết định]**, với kết quả **[kết quả cụ thể]**. Qua việc này, em rút ra **[bài học cá nhân]**.

## 6. Vai trò em muốn nhận

**Ưu tiên 1 — Agent: lập trình agent và MCP.** Kinh nghiệm từ Agentic Python Repo RAG Copilot và ReloHome cho em nền tảng để tiếp tục theo hướng kết nối mô hình với dữ liệu và công cụ. Em muốn đảm nhiệm các phần như thiết kế tool có input/output rõ ràng, nối tool vào luồng agent và kiểm chứng hành vi khi thiếu dữ liệu hoặc khi tool lỗi. Em cần học sâu thêm về lựa chọn ngữ cảnh, đánh giá agent theo tác vụ, xử lý lỗi và quản lý trạng thái của workflow dài.

**Ưu tiên 2 — Ngữ cảnh & test: rule cho AI, kiểm thử tích hợp và E2E.** Kinh nghiệm làm RAG và kiểm thử các luồng Housing/Roommate có liên quan đến hướng này. Em muốn phát triển khả năng xây bộ tình huống thực tế, xác định bằng chứng cần thiết cho câu trả lời và kiểm tra hệ thống khi người dùng đổi ý, retry hoặc mất quyền truy cập. Em cần học thêm cách thiết kế bộ đánh giá có tính đại diện và vận hành chúng ổn định trong CI.

## Tự đánh giá kỹ năng

**Điểm dưới đây là gợi ý cần em tự xác nhận trước khi gửi.** Thang quy chiếu đề xuất: 0 = chưa dùng; 1 = đã tiếp xúc, cần hướng dẫn; 2 = đã làm trong dự án và có thể giải thích phần mình làm; 3 = chủ động thiết kế, xử lý vấn đề và hướng dẫn người khác.

| Kỹ năng | Điểm gợi ý | Một câu minh chứng cần tự xác nhận |
|---|---:|---|
| Git | 2/3 | Em đã làm việc trên nhánh QuangDung, tạo commit và tích hợp thay đổi trong repository ReloHome. |
| Linux | [0–3]/3 | [Điền một thao tác thực sự tự làm trên Linux; nếu chưa dùng thì ghi 0 và nêu rõ.] |
| Docker | 2/3 | Em đã có kinh nghiệm container hóa ứng dụng RAG trong CV và tham gia đóng gói Location MCP để bàn giao. |
| SQL | 2/3 | Em tham gia xử lý dữ liệu PostgreSQL/PostGIS và tối ưu truy vấn Housing, có benchmark và so sánh kết quả trước/sau. |
| Java | [0–3]/3 | [Điền đúng mức hiện tại; hai CV chưa cung cấp minh chứng Java.] |
| TypeScript | 2/3 | Em có đóng góp ở dịch vụ Location/Housing, schema, MCP và giao diện ReloHome. |
| Python | 2/3 | Em đã dùng Python trong pipeline ML, ứng dụng RAG và các phần backend/agent của Roommate. |
| Viết prompt / Claude Code | 2/3 | [Nêu đúng công cụ đã dùng và một prompt thật, cùng cách bạn kiểm tra kết quả.] |
| Agent/MCP | 2/3 | Em đã làm Agentic RAG, tham gia xây Location MCP và tích hợp capability Roommate vào agent ReloHome. |
| Viết test | 2/3 | Em có đóng góp kiểm thử backend/API và trình duyệt; ví dụ commit `92f04cb` kiểm tra điều hướng hồ sơ Roommate trên mobile. |
| CI/CD | 1/3 | Em đã tiếp xúc với kiểm tra build/test và sửa phạm vi build dữ liệu trong commit `434f5a8`; em chưa nhận mình làm chủ toàn bộ pipeline triển khai. |
| Viết tài liệu | 2/3 | Em có tài liệu bàn giao nhánh QuangDung, hướng dẫn dữ liệu và ghi nhận phạm vi/kết quả kiểm thử. |

## Prompt đã dùng

**[Dán 1–3 prompt thật từ lịch sử công cụ, bỏ thông tin nhạy cảm. Không biến các gợi ý dưới đây thành lời khẳng định đã dùng.]**

1. **[Prompt thật về xây hoặc tích hợp một MCP tool/agent.]** Kết quả AI tạo: **[...]**. Phần em kiểm tra hoặc sửa: **[...]**.
2. **[Prompt thật về xử lý dữ liệu hoặc tối ưu SQL.]** Kết quả AI tạo: **[...]**. Phần em kiểm tra hoặc sửa: **[...]**.
3. **[Tùy chọn: prompt thật về test hồi quy/E2E.]** Kết quả AI tạo: **[...]**. Phần em kiểm tra hoặc sửa: **[...]**.

Em cảm ơn anh/chị đã đọc phần giới thiệu. Em sẵn sàng trao đổi cụ thể về các phần đóng góp, kết quả đã kiểm chứng và những điểm em còn cần học thêm.

Trân trọng,

**Mai Quang Dũng**  
Mã học viên: **2A202602966**

---

## Nguồn đối chiếu cho bản nháp — có thể bỏ khi gửi

- CV trước: `D:/Tự học/CV/2026_AI Thực chiến Khóa IV.pdf` — đã có RAG Copilot, Taxi Fare ML Pipeline và Fintech BI; không mô tả bản thân trước khóa học như người chưa biết AI.
- CV mới: `D:/Tự học/CV/2A202602966_Mai Quang Dũng.pdf` — thêm FinSight, mô tả LangGraph, causal validation và distillation chi tiết hơn. Không mặc định FinSight được làm trong đúng 6 tuần nếu chưa có xác nhận của bạn.
- `P-044/docs/integration/quangdung-housing-performance-handoff-2026-10-10.md`: thời gian SQL 274,18 → 28,33 ms; 24 bộ request, 65 so sánh; số đo local, median 3 lần.
- `P-044/docs/design/housing-query-performance.md`: giải thích phương án lọc/phân trang trước khi lấy chi tiết và giới hạn phép đo.
- `P-044/docs/integration/roommate-backend-checkpoint.md`: 169 test focused đạt ở checkpoint 07/10; suite toàn dự án có 29 lỗi baseline, không phải chứng nhận phát hành.
- `P-044/docs/integration/quangdung-handoff-2026-10-08.md`: phạm vi bàn giao frontend, Roommate, dữ liệu và kiểm thử.
- `git log`/`git show` với tác giả `maidung2005bk18@gmail.com`: kiểm tra liên hệ giữa đóng góp và các commit được dẫn.
- URL demo lấy từ README trong checkout, chưa kiểm tra website trực tiếp trong lượt soạn bài này.

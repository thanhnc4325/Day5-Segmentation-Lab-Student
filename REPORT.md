# Báo cáo Day 5 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên VLearn. Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202602219
- Ngày / CVAT local: 17/09/2026
- Công cụ đã dùng: Brush (80%) / Polygon (15%) / Intelligent Scissors (5%)

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh VLearn đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | easy_semantic.zip | 3 / 3 | 20 |
| medium_instance | medium_instance.zip | 3 / 3 | 32 |
| hard_panoptic | hard_panoptic.zip | 2 / 2 | 30 |
| cp1_holes | cp1_holes.zip | 1 / 1 | 3 |
| cp2_slice | cp2_slice.zip | 1 / 1 | 3 |
| cp5_occlusion | cp5_occlusion.zip | 1 / 1 | 3 |
| cp3_thin | cp3_thin.zip | 1 / 1 | 3 |
| cp4_curb | cp4_curb.zip | 1 / 1 | 3 |
| cp6_coverage | cp6_coverage.zip | 1 / 1 | 3 |
| **Tổng tối đa** | | | **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: 000000181542.jpg - Vị trí góc trái khung hình - chọn class `car` (ô tô) về đầu tiên.
- Class và quy tắc tôi dùng để chọn biên: Class car. Quy tắc: Vẽ bám sát viền ngoài của xe, dừng lại ở ranh giới tiếp xúc mặt đường và cản trước, không lấn sang bóng râm đổ xuống đường.
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: Vùng gợi ý tự động bị lẹm sang bóng râm dưới gầm xe, hành động của tôi là dùng Brush để xóa bớt vùng thừa và giữ lại đúng mép gầm xe vì phần bóng râm không thuộc object `car`.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: `cp3_thin` / 839f7736-abe28069.jpg / Vùng nét mảnh của cột điện (pole).
- Lỗi thuộc loại: sai lớp / thiếu-thừa vật / gộp-tách / biên / phủ vùng / khác: thiếu vật (nét mảnh bị đứt đoạn).
- Bằng chứng tôi nhìn thấy: Khi zoom lớn khung hình, mask của class `pole` bị đứt đoạn, chưa bao phủ toàn bộ chiều dài của thân cột.
- Quy tắc và hành động sửa: Áp dụng quy tắc phủ kín bề mặt nhìn thấy, tôi dùng Brush với kích thước nhỏ để tô nối lại các đoạn đứt gãy cho liền mạch.
- Sau sửa đã Save và export lại chưa? Đã Save và export lại đè lên file `cp3_thin.zip` cũ.

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): … / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| cp1_holes (000000144300.jpg) - Vùng kính cửa sổ xe bus | Đục lỗ (khoét mask) phần kính xe để chừa khoảng không bên trong, HOẶC vẽ phủ kín cả phần kính. | Theo tài liệu tự nhắc: Kính/lỗ nằm trong mask, không tự khoét. | Tôi quyết định giữ nguyên mask bao phủ trọn vẹn cả phần bề mặt kính cửa sổ của xe bus. |
| cp5_occlusion (000000336232.jpg) - Vùng người bị xe che khuất giữa thân | Tạo 2 mask riêng biệt cho 2 phần bị cắt xẻ, HOẶC gộp chung thành 1 mask duy nhất. | Theo tài liệu tự nhắc: Vật bị che thành hai phần nhìn thấy vẫn là một instance. | Tôi quyết định gộp chung (group) các phần nhìn thấy của người đó thành một instance duy nhất. |
| cp2_slice (000000017627.jpg) - Vùng hai chiếc xe đỗ sát cạnh nhau | Gộp chung thành 1 mask lớn vì biên giới chúng dính liền, HOẶC tách làm 2 mask. | Theo tài liệu tự nhắc: Hai xe cùng lớp sát nhau vẫn là hai instance biệt lập. | Tôi quyết định vẽ 2 instance riêng biệt và soi kỹ mép để đảm bảo đường biên giữa 2 xe không lấn lên nhau. |

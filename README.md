# LTXLDL — pilot lab 01–14

Mỗi sinh viên có một **private repo riêng trong `uet-iai-notebook-labs-2026`**, chứa tất cả các lab.
Đây là bộ pilot để thử quy trình nộp/chấm, chưa phải điểm chính thức của môn học.

| File | Nội dung | Điểm máy tối đa | Phần giảng viên |
|---|---|---:|---:|
| [lab-01.ipynb](lab-01.ipynb) | Notebook, trạng thái, đọc dữ liệu và quy trình AI | 40 | 60 |
| [lab-02.ipynb](lab-02.ipynb) | Python, CSV, làm sạch và tổng hợp | 80 | 20 |
| [lab-03.ipynb](lab-03.ipynb) | NumPy: bộ nhớ, view/copy, broadcasting, thống kê và lấy mẫu | 80 | 20 |
| [lab-04.ipynb](lab-04.ipynb) | pandas: lập hồ sơ một quận — chọn/lọc, `.loc`, mẫu số và NaN, xuất CSV | 80 | 20 |
| [lab-05.ipynb](lab-05.ipynb) | pandas: phân khúc giá, host chuyên nghiệp — `groupby`, `transform`, `pivot_table`, `merge` | 80 | 20 |
| [lab-06.ipynb](lab-06.ipynb) | Dữ liệu ngoài: đọc có chọn lọc, Parquet, response API lịch sử, DuckDB `JOIN` | 80 | 20 |
| [lab-07.ipynb](lab-07.ipynb) | Chuỗi và regex trên cột đánh giá: `str.contains`, `str.replace`, `str.extract` | 80 | 20 |
| [lab-08.ipynb](lab-08.ipynb) | Chuỗi thời gian: cắt lát, quý chưa trọn, `rolling`, so cùng kỳ | 80 | 20 |
| [lab-10.ipynb](lab-10.ipynb) | Đảm bảo chất lượng chéo bảng: khoá ngoại, khoá tự nhiên, cột dẫn xuất, `qa_report` | 80 | 20 |
| [lab-11.ipynb](lab-11.ipynb) | Kỷ luật đo lường cho LLM: chọn mẫu, schema Pydantic, nhãn tay, hậu kiểm | 80 | 20 |
| [lab-12.ipynb](lab-12.ipynb) | Biểu đồ cho báo cáo: đường, thanh ngang, histogram, sửa trục bị cắt; kiểm tra bằng `assert` | 80 | 20 |
| [lab-13.ipynb](lab-13.ipynb) | seaborn, bản đồ số chỗ ở, phản biện hình chọn mốc có lợi | 80 | 20 |
| [lab-14.ipynb](lab-14.ipynb) | Kể chuyện bằng dữ liệu: kim tự tháp, lời đúng mức, nghịch lý Simpson, thẩm định kết luận | 80 | 20 |

## Tạo repo bài nộp từ template

Thực hiện một lần khi bắt đầu học; dùng cùng repo cho mọi lab.

1. Đăng nhập GitHub và chấp nhận lời mời tham gia organization `uet-iai-notebook-labs-2026` của giảng viên.
2. Mở [repo template](https://github.com/uet-iai-notebook-labs-2026/notebook-labs-template), chọn **Use this template → Create a new repository**.
3. Điền thông tin như sau:

   | Trường | Giá trị |
   |---|---|
   | Owner | `uet-iai-notebook-labs-2026` |
   | Repository name | `<mã_lớp>_<mssv>`, theo quy tắc bên dưới |
   | Visibility | **Private** |
   | Include all branches | Không chọn |

4. Bấm **Create repository** (hoặc **Create repository from template**).
5. Gửi giảng viên **họ tên, mã lớp, MSSV, GitHub username và URL repo** để đăng ký chấm bài.
6. Clone repo vừa tạo về máy hoặc mở notebook của repo đó bằng Colab. Làm bài và commit trên branch `main` của repo cá nhân trong org.

**Quy tắc đặt tên:** dùng mã lớp được giảng viên cung cấp, viết thường, nối với MSSV bằng dấu gạch dưới `_`; không thêm khoảng trắng hoặc họ tên.

Ví dụ mã lớp `dse2049_7` thì tên repo theo mẫu `dse2049_7_mssv`.
Sinh viên có MSSV `23020001` đặt tên **`dse2049_7_23020001`**, với URL:

```text
https://github.com/uet-iai-notebook-labs-2026/dse2049_7_23020001
```

Thay `mssv` bằng mã số sinh viên thật của mình. Mỗi sinh viên tạo một repo cho lớp đang học, chứa tất cả lab; không tạo repo riêng cho từng lab.

Nếu không thấy org trong mục Owner, không mở được template hoặc không có quyền tạo repo, báo giảng viên để kiểm tra lời mời và quyền truy cập. Không tạo repo dưới tài khoản cá nhân để thay thế.

Sau khi tạo repo, không cần cấu hình GitHub Actions hay secret chấm bài. Chờ giảng viên xác nhận đăng ký repo, rồi nộp từng lab bằng tag theo mục **Nộp một lab** bên dưới.

## Làm bài

1. Mở notebook bằng Colab hoặc Jupyter. Điền cell TODO và phần trả lời Markdown.
2. Chạy public checks ngay trong notebook; trước khi nộp dùng Restart & Run all.
3. Lưu file về đúng tên và vị trí gốc của repo. Lưu trên Drive chưa phải nộp GitHub.

Không có GitHub Actions ở repo sinh viên. Public checks phục vụ tự kiểm tra;
private grader chấm độc lập, không đọc bảng PUBLIC_RESULTS hay output lưu sẵn để lấy điểm.

Giữ nguyên cell ID, tên hàm/biến và hợp đồng input/output. Có thể viết helper trong chính cell bài làm;
grader không chạy những cell helper mới nằm rải rác ngoài cell đó. Các câu được chấm độc lập với đầu vào riêng.
Các import chuẩn `csv`, `json`, `numpy as np`, `pandas as pd` và hàm `trung_vi` được cung cấp khi phù hợp.
Phần markdown do giảng viên đọc. Các bài E của lab 02 và lab 03 bản cũ vẫn là mở rộng tùy chọn, không làm giảm điểm Q.
Lab 03 bản mới chấm Q1–Q6 và Q8 tự động; Q7 đo thời gian do giảng viên đọc nhận xét.

## Môi trường và dữ liệu

Khuyến nghị Python 3.12. Nếu chạy local:

```bash
python -m pip install -r requirements.txt
python -m ipykernel install --user --name ltxldl --display-name "LTXLDL"
```

Chọn kernel LTXLDL trong Jupyter/VS Code. Colab có sẵn nhiều thư viện; chỉ cài khi import chưa hoạt động.

Lab 01–02 mở mặc định bằng 6 dòng giả lập để thử quy trình; không suy rộng kết quả thành kết luận về Santiago.
Có thể dùng snapshot Santiago 2026-06-29 theo hướng dẫn notebook. Q2 lab 01 chấp nhận câu trả lời đọc bảng
cho bộ 6 dòng hoặc snapshot 18.534 dòng đã nêu trong đề. Các hàm khác phải tính từ input, không ghi cứng số.
Private grader không tải URL từ notebook và không chạy API bên ngoài.

## Nộp một lab

Repo phải được giảng viên đăng ký trước. Ví dụ nộp lab 02 lần đầu trên branch `main`:

```bash
git add lab-02.ipynb
git commit -m "Submit lab 02 attempt 1"
git push origin main
git tag submit/lab-02/v1
git push origin submit/lab-02/v1
```

Tag tương ứng của các lab khác là `submit/lab-01/v1`, `submit/lab-03/v1`, `submit/lab-04/v1` … `submit/lab-14/v1` (không có lab 09).
Pilot hiện hỗ trợ v1, v2, v3 cho từng lab. Sửa bài phải tạo commit mới và tag lần tiếp theo;
không di chuyển/force-push tag đã nộp. Commit/push không có tag chưa được xem là bài nộp tự động.

## Xem kết quả

Grader quét **20:00 thứ Bảy, giờ Việt Nam**; giảng viên có thể chạy thủ công để thử ngay.
Giờ bắt đầu thực tế có thể trễ do GitHub xếp hàng.

Mở commit mà tag trỏ tới → xem status `private-grader/lab-01`, `private-grader/lab-02` hoặc
`private-grader/lab-03`, `private-grader/lab-04` … `private-grader/lab-14`. Ví dụ `Auto 70/80; manual 20 pending` nghĩa là máy đã chấm 70/80,
20 điểm còn chờ giảng viên; đây chưa phải điểm cuối cùng. Status xanh chỉ xác nhận các mục Q tự động đã qua.
Không cần vào tab Actions ở repo sinh viên. Link Details dẫn đến grader private, chỉ giảng viên xem được.

Nếu đã nộp đúng tag nhưng chưa có status, gửi giảng viên tên repo, lab, tag và commit SHA.


## Cập nhật lab 03 — 20/09/2026

Lab 03 hiện dùng đề **NumPy và tư duy vector hoá**, phiên bản `numpy-vectorization-v2`,
gồm 8 bài với dữ liệu tự tạo; ví dụ giá là giả lập USD/đêm, không phải dữ liệu Santiago.
Tổng điểm vẫn là 80 tự động + 20 giảng viên.

Repo đã tạo từ template không tự nhận bản cập nhật. Nếu được giảng viên yêu cầu chuyển sang đề mới,
lưu bản bài làm cũ trước, tải `lab-03.ipynb` từ template và đưa vào repo của mình;
không ghi đè phần đã làm mà chưa sao lưu. Hai đề khác nhau, không chỉ đổi tên hàm.
Dùng tag lần nộp kế tiếp nếu đã nộp bài; không di chuyển tag cũ.
Grader vẫn nhận diện đề cũ để chấm theo hợp đồng cũ; giảng viên xác định đề áp dụng cho lớp.


## Lab 04 và lab 05 — 24/09/2026

Hai lab pandas trên snapshot Santiago 2026-06-29, cùng cách chấm như lab 03: **8 bài × 10 điểm tự động + 20 điểm giảng viên**.

| Lab | Phiên bản đề | Nội dung chấm tự động |
|---|---|---|
| `lab-04.ipynb` | `pandas-district-profile-v1` | chọn cột/hàng, lọc quận, lọc kết hợp, `nsmallest`, sửa bằng `.loc` và tính lại cột, tỷ lệ theo 2 mẫu số, cơ cấu loại phòng, xuất/đọc lại CSV |
| `lab-05.ipynb` | `pandas-groupby-merge-v1` | `loc`/`iloc`, alignment, `map` với hàm, `agg` đặt tên, host chuyên nghiệp, `transform`, `pivot_table`, `merge(validate="m:1")` |

Notebook mở mặc định bằng **12 dòng giả lập** để Run all được khi không có mạng; đặt `LISTINGS_PATH = SNAPSHOT_URL`
trong cell dữ liệu để thực hành trên Santiago. Public checks và grader không dùng snapshot, không tải URL.
Hàm phải nhận dữ liệu qua tham số và **không sửa DataFrame đầu vào**; grader kiểm tra cả việc này.
Hai lab chạy với Copy-on-Write của pandas 3 (bật sẵn trong notebook và khi chấm).

Repo đã tạo từ template không tự nhận file mới: tải `lab-04.ipynb`, `lab-05.ipynb` từ template, đặt ở gốc repo
của mình rồi làm bài. Nộp bằng tag `submit/lab-04/vN`, `submit/lab-05/vN`.


## Lab 06, 07 và 08 — 25/09/2026

Cùng cách chấm như lab 03–05: **80 điểm tự động + 20 điểm giảng viên**.

| Lab | Phiên bản đề | Nội dung chấm tự động |
|---|---|---|
| `lab-06.ipynb` | `external-data-duckdb-v1` | `usecols`/`parse_dates`, làm sạch giá chuỗi, CSV và Parquet, lưu response API thô, đếm review theo ngày, ghép thời tiết và tương quan, DuckDB `GROUP BY`/`JOIN` |
| `lab-07.ipynb` | `text-regex-v1` | chuẩn hoá chuỗi, `contains` với `na=False`/`regex=False`, khảo sát độ dài, làm sạch `<br/>`, quy tắc ngôn ngữ, `str.extract`, bảng tần suất |
| `lab-08.ipynb` | `time-series-v1` | loại ngày sau mốc chụp, cắt lát theo năm, quý và quý chưa trọn, cực trị, đếm theo ngày, cửa sổ trượt, so kỳ trước và so cùng kỳ |

Mặc định cả ba notebook dùng **dữ liệu giả lập** (`USE_SNAPSHOT = False`) để Run all được khi không có mạng;
đặt `USE_SNAPSHOT = True` trong cell dữ liệu để tải snapshot Santiago (và gọi API Open-Meteo ở lab 06).
Grader không có mạng: hàm nhận đường dẫn file hoặc dict response qua tham số, không tự tải URL hay gọi API.
Lab 06 cần `duckdb` và `pyarrow` (Colab có sẵn; chạy local thì cài lại `requirements.txt`).
Không commit các file dữ liệu notebook tạo ra (`data/`, `data_demo/`, `raw/`, `t6.*` — đã có trong `.gitignore`).

Repo đã tạo từ template không tự nhận file mới: tải `lab-06.ipynb`, `lab-07.ipynb`, `lab-08.ipynb` (và `requirements.txt`,
`.gitignore` mới) từ template, đặt ở gốc repo của mình rồi làm bài. Nộp bằng tag `submit/lab-06/vN` … `submit/lab-08/vN`.


## Lab 10 và lab 11 — 25/09/2026

Không có lab 09 (tuần thi giữa kỳ). Cùng cách chấm: **80 điểm tự động + 20 điểm giảng viên**; phần 🧭 hỗ trợ bài tập lớn
ở cuối mỗi lab làm theo nhóm, không tính điểm lab.

| Lab | Phiên bản đề | Nội dung chấm tự động |
|---|---|---|
| `lab-10.ipynb` | `qa-cross-table-v1` | miền thời gian và mốc chụp, review mồ côi (khoá ngoại), dòng lặp theo khoá ứng viên, đối chiếu `number_of_reviews`, lệch cửa sổ LTM, ghi `qa_report` |
| `lab-11.ipynb` | `llm-eval-v1` | chọn mẫu tái lập được, ước token và chi phí, schema Pydantic `ReviewInfo`, kiểm tra hàng loạt đầu ra LLM, độ chính xác trên nhãn tay, hậu kiểm tự mâu thuẫn |

Hai notebook mặc định dùng dữ liệu giả lập (`USE_SNAPSHOT = False`); lab 11 **không cần khóa API** và grader không gọi LLM.
Mỗi phép kiểm ở lab 10 là một hàm nhận bảng qua tham số để chạy lại được trên mốc chụp khác. Lab 11 cần `pydantic` bản 2
(Colab có sẵn; chạy local thì cài lại `requirements.txt`). Khi chấm Bài 4 lab 11, grader dùng `ReviewInfo` chuẩn nên
Bài 4 không bị ảnh hưởng nếu Bài 3 còn sai. **Không bao giờ** dán khóa API vào notebook hay commit.

Tải `lab-10.ipynb`, `lab-11.ipynb` (và `requirements.txt`, `.gitignore` mới) từ template vào gốc repo của mình.
Nộp bằng tag `submit/lab-10/vN`, `submit/lab-11/vN`.


## Lab 12, 13 và 14 — 25/09/2026

Cùng cách chấm: **80 điểm tự động + 20 điểm giảng viên**; phần 🧭 hỗ trợ bài tập lớn không tính điểm lab.

| Lab | Phiên bản đề | Nội dung chấm tự động |
|---|---|---|
| `lab-12.ipynb` | `report-charts-v1` | chuỗi tháng của một quận, biểu đồ đường có nguồn, bảng tỷ lệ nguyên căn, thanh ngang có nhãn, histogram hai đỉnh, sửa trục bị cắt |
| `lab-13.ipynb` | `seaborn-maps-critique-v1` | boxplot seaborn có `hue` trên thang log, ghép bản đồ số chỗ ở (NaN → 0), đếm theo năm, so các mốc, bản sửa hình chọn mốc có lợi |
| `lab-14.ipynb` | `storytelling-review-v1` | thứ tự kim tự tháp, nhãn đúng mức/quá mức, giá trung bình gộp, tỷ trọng phân khúc, truy số, phán quyết thẩm định |

Hàm vẽ phải **tạo hình mới, lưu bằng `savefig` và trả về `ax`**: grader đọc cấu trúc hình (dữ liệu đã vẽ, tiêu đề, nhãn, giới hạn trục,
thang log, chú giải) và file đã lưu; tiêu đề có nêu đúng thông điệp hay không do giảng viên đánh giá. Lab 13 cần `seaborn`, phần vẽ bản đồ cần
`geopandas` (Colab có sẵn; chạy local thì cài lại `requirements.txt`). Ở lab 14, Bài 1, 2, 6 là câu trả lời gán vào biến: public check
chỉ kiểm định dạng, không cho biết đúng/sai. Hai notebook 12–13 mặc định dùng dữ liệu giả lập (`USE_SNAPSHOT = False`).

Tải `lab-12.ipynb`, `lab-13.ipynb`, `lab-14.ipynb` (và `requirements.txt` mới) từ template vào gốc repo của mình.
Nộp bằng tag `submit/lab-12/vN` … `submit/lab-14/vN`.

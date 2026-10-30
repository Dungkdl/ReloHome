# ReloHome — Mai Quang Dũng

Repository cá nhân lưu mã nguồn dự án ReloHome cùng bài giới thiệu của Mai Quang Dũng (mã học viên 2A202602966).

- [Bài giới thiệu (PDF)](Bai-gioi-thieu-Mai-Quang-Dung.pdf)
- [Mã nguồn LaTeX của bài giới thiệu](Bai-gioi-thieu-Mai-Quang-Dung.tex)
- [Bản nháp tham khảo, còn các mục cần điền](Bai-gioi-thieu-Mai-Quang-Dung-ban-nhap.md)
- [Mã nguồn và hướng dẫn chạy ReloHome](P-044/README.md)

## Nguồn dự án

Thư mục `P-044/` lưu mã nguồn từ dự án nhóm [AI20K-Build-Phase-Cohort-4/P-044](https://github.com/AI20K-Build-Phase-Cohort-4/P-044), tại commit `00a8b4d98ba9d9c1c0b0e81452bf274d44438bdd`. Đây là kết quả chung của nhóm; phần đóng góp cá nhân được trình bày trong bài giới thiệu. Giấy phép gốc được giữ tại [P-044/LICENSE](P-044/LICENSE).

`P-044/` được lưu thành các tệp mã nguồn trong repository này, có thể tải bằng `git clone` thông thường.

## Biên dịch bài giới thiệu

Cài XeLaTeX (MiKTeX hoặc TeX Live), rồi chạy tại thư mục gốc:

```sh
xelatex -interaction=nonstopmode -halt-on-error Bai-gioi-thieu-Mai-Quang-Dung.tex
```

PDF hoàn chỉnh được lưu cùng mã nguồn; các tệp LaTeX trung gian được bỏ qua bởi `.gitignore`.

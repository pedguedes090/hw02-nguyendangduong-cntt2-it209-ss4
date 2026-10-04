# Bài 2 — Quản lý nhánh và xử lý Merge Conflict

**Sinh viên:** NguyễnDăngDương
**Lớp:** CNTT2
**Môn học:** IT209 — Session 04

Merge conflict target: initial README line.

## Quy trình

1. Tạo commit ban đầu trên `main` với README có một dòng giới thiệu.
2. Tạo nhánh `feature-update`, sửa dòng giới thiệu rồi commit.
3. Quay lại `main`, sửa chính dòng đó theo nội dung khác rồi commit.
4. Chạy `git merge feature-update`. Git báo conflict ở README vì hai nhánh thay đổi cùng một vùng.
5. Mở README, tự chọn nội dung cuối cùng và xóa các dấu `<<<<<<<`, `=======`, `>>>>>>>`.
6. Chạy `git add README.md` và `git commit` để hoàn thành merge commit.

## Lệnh tham khảo

```bash
git switch -c feature-update
git add README.md
git commit -m "Update feature description"
git switch main
git add README.md
git commit -m "Revise main description"
git merge feature-update
git status
git add README.md
git commit -m "Resolve README merge conflict"
git log --graph --oneline --decorate --all
```

Merge conflict được xử lý thủ công trong nội dung file trước khi staging. Merge commit có hai parent commit, nhánh `feature-update` và nhánh `main`; đồ thị log dùng để kiểm tra quan hệ này.

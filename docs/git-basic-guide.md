# Tài liệu học Git & GitHub cơ bản

## I. Giới thiệu về Git và GitHub

* **Git** là một hệ thống quản lý phiên bản mã nguồn (Source Version Control).
* **GitHub** là một nền tảng lưu trữ mã nguồn trực tuyến dựa trên Git, hỗ trợ làm việc nhóm, quản lý code, issue, CI/CD...

## II. Sơ đồ kỹ năng Git cơ bản

```
Git Workflow

Làm việc cục bộ (Local)               Làm việc từ xa (Remote)
----------------------               ------------------------
Working Directory  <---edit--->  Staging Area  <---add--->  Local Repo  <---commit--->
                                                    |
                                                push/pull
                                                    |
                                                Remote Repo (GitHub)
```

## III. Các lệnh Git cơ bản và ví dụ

### 1. Cấu hình Git

```bash
git config --global user.name "Nguyen Van A"
git config --global user.email "email@example.com"
git config --list
```

### 2. Khởi tạo repository

```bash
# Tạo Git repo mới trong thư mục hiện tại
git init

# Clone repo từ GitHub
git clone https://github.com/username/repo.git
```

### 3. Theo dõi và commit file

```bash
# Kiểm tra trạng thái
$ git status

# Thêm file vào stage
$ git add ten_file.txt
# Hoặc thêm toàn bộ tại thư mục hiện tại
$ git add .

# Commit thay đổi với tin nhắn
$ git commit -m "Add new feature"
```

### 4. Quản lý branch

```bash
# Xem danh sách tất cả branch
$ git branch -a

# Tạo branch mới
$ git branch ten_branch

# Chuyển sang branch mới
$ git checkout ten_branch

# Tạo và chuyển luôn sang branch mới
$ git checkout -b ten_branch
```

### 5. Làm việc với remote

```bash
# Liên kết repo local với GitHub
$ git remote add origin https://github.com/user/repo.git

# Push lên remote branch GitHub
$ git push -u origin main

# Kéo thay đổi từ GitHub
$ git pull origin main
```

### 6. Gộp nhánh (Merge)

```bash
# Gộp nhánh vào main (khi đang ở main)
$ git merge ten_branch

# Kiểm tra xung đột (conflict) nếu có và sửa
```

### 7. Quản lý xung đột (Conflict)

* Khi 2 người thay đổi cùng 1 dòng → xảy ra conflict.
* Git đánh dấu vùng bị xung đột:

```bash
<<<<<<< HEAD
Nội dung của bạn
=======
Nội dung của người khác
>>>>>>> branch-khac
```

* Sau khi sửa xong:

```bash
git add .
git commit -m "Fix conflict"
```

### 8. Xem lịch sử thay đổi

```bash
git log             # Xem log

git log --oneline   # Dạng rút gọn
```

### 9. Pull Request (trên GitHub)

1. Fork repo hoặc tạo branch mới từ `main`
2. Push lên GitHub
3. Vào GitHub → Chọn "Compare & Pull Request"
4. Mô tả thay đổi và gửi pull request để người khác review

## IV. Quy trình làm việc chuẩn nhóm (Team Workflow)

1. Clone repository từ GitHub
2. Tạo branch theo task (`feature/login`, `bugfix/api-error`...)
3. Thực hiện thay đổi, commit từng phần
4. Push branch lên GitHub
5. Tạo Pull Request để merge vào `main`
6. Được review và merge code

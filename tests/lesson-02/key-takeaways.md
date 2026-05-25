# Key Takeaways - Lesson 2: Git & JavaScript Basic

> Lesson 2 - Version Control System, Git Basics, JavaScript Basics

---

# 1. Version Control System (VCS)

## 1.1 VCS là gì?

**Version Control System** = Hệ thống quản lý phiên bản.

Giúp:

- Xem lịch sử thay đổi
- Biết:
  - Ai sửa?
  - Sửa lúc nào?
  - Sửa gì?
- Quay về version cũ nếu cần

---

## 1.2 Các loại VCS

### Local VCS

- Lưu trên máy cá nhân
- Đơn giản
- Không hỗ trợ teamwork

### Centralized VCS

- Lưu ở server trung tâm
- Có teamwork
- Phụ thuộc internet/server

### Distributed VCS (DVCS)

- Mỗi máy đều có repository
- Có thể làm offline
- Backup tốt hơn

> Git là một **Distributed Version Control System (DVCS)**.

---

# 2. Git Basics

## 2.1 Git là gì?

Git là:

- Công cụ quản lý version
- Miễn phí
- Nhanh
- Phổ biến nhất hiện nay

Cha đẻ của Git:

```text
Linus Torvalds
```

(cha đẻ Linux)

---

## 2.2 Git vs GitHub

### Git

- Phần mềm cài trên máy
- Command line tool
- Quản lý version local

### GitHub

- Website/service
- Nơi host repository online
- Dùng để upload Git repo

> Git ≠ GitHub

---

# 3. Git Three States

Git hoạt động dựa trên **3 trạng thái**:

```text
Working Directory
↓ git add
Staging Area
↓ git commit
Repository
```

---

## 3.1 Working Directory

Chứa:

- File mới
- File đã chỉnh sửa

Ví dụ:

```text
test1.spec.ts
package.json
.gitignore
```

---

## 3.2 Staging Area

Nơi chuẩn bị commit.

Khi chạy:

```bash
git add .
```

File được đưa vào vùng staging.

---

## 3.3 Repository

Nơi chứa:

- Commit
- History
- Version

Khi chạy:

```bash
git commit -m "message"
```

File từ staging → repository.

---

# 4. Git Commands

## 4.1 Khởi tạo repo

```bash
git init
```

### Dùng khi nào?
Tạo Git repository local.

> Chỉ làm 1 lần duy nhất.

---

## 4.2 Kiểm tra trạng thái file

```bash
git status
```

### Ý nghĩa màu

#### Màu đỏ
```text
Working Directory
```

#### Màu xanh
```text
Staging Area
```

---

## 4.3 Add file vào staging

### Add tất cả file

```bash
git add .
```

### Add 1 file

```bash
git add test1.spec.ts
```

---

## 4.4 Commit code

```bash
git commit -m "message"
```

Ví dụ:

```bash
git commit -m "feat: add login test"
```

---

## 4.5 Kiểm tra commit history

```bash
git log
```

---

## 4.6 Link local repo với GitHub

```bash
git remote add origin <url>
```

Ví dụ:

```bash
git remote add origin https://github.com/abc/project.git
```

> Chỉ làm 1 lần.

---

## 4.7 Push code

```bash
git push origin main
```

---

# 5. Git Config

## 5.1 Vì sao cần config?

Git cần biết:

```text
Bạn là ai?
```

Nếu không config sẽ không commit được.

---

## 5.2 Global config

Áp dụng cho toàn bộ máy tính:

```bash
git config --global user.name "Tên của bạn"
git config --global user.email "email@gmail.com"
```

---

## 5.3 Config riêng từng repo

Nếu mỗi project dùng account khác nhau:

```bash
git config user.name "Alex"
git config user.email "alex@gmail.com"
```

> Chạy trong repo đó.

---

# 6. Commit Convention

## 6.1 Convention là gì?

Convention = quy tắc.

Giúp:

- Team code thống nhất
- Dễ đọc
- Chuyên nghiệp hơn

---

## 6.2 Format commit

```text
<type>: <short_description>
```

Ví dụ:

```text
feat: add login test
fix: fix failed testcase
chore: remove unused file
```

---

## 6.3 Các loại commit

### feat

Feature mới

Ví dụ:

```text
feat: add register feature
```

---

### fix

Sửa lỗi

Ví dụ:

```text
fix: fix login test
```

---

### chore

Việc nhỏ lẻ

Ví dụ:

```text
chore: remove unused file
```

---

# 7. Simple Git Workflow

## Lần đầu setup

```bash
git init
git remote add origin <url>
```

---

## Workflow hằng ngày

```bash
git add .
git commit -m "message"
git push origin main
```

---

# 8. JavaScript Basic

## 8.1 JavaScript là gì?

JavaScript:

- Ngôn ngữ lập trình
- Ra đời năm 1995
- Tạo bởi Brendan Eich
- Giúp browser hoạt động

---

## 8.2 Nội dung JS trong bài

- Hello World
- Variables & Constants
- Comments
- Data Types
- Operators
- if condition
- for loop

> Sẽ học kỹ hơn ở các lesson tiếp theo.

---

# Quick Summary

## Git Flow

```text
git init
↓
git add .
↓
git commit -m "message"
↓
git push origin main
```

## Three States

```text
Working Directory
→ Staging Area
→ Repository
```

## Important Commands

```bash
git status
git add .
git commit -m "message"
git log
git push origin main
```

## Commit Convention

```text
feat → feature mới
fix → sửa bug
chore → việc nhỏ lẻ
```
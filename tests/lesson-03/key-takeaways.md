# Key Takeaways - Lesson 3: Git & Javascript Basic (Continue)

> Lesson 3 - Git Undo, Branching, .gitignore, JavaScript Condition, Loop, Convention

---

# 1. Git - Undo

## 1.1 Sửa commit message mới nhất

Khi commit sai message:

```bash
git commit --amend -m "message mới"
```

Ví dụ:

```bash
git commit --amend -m "feat: add login feature"
```

### Khi dùng?
- Gõ sai commit message
- Muốn rename commit gần nhất

---

## 1.2 Un-stage file (Staging → Working Directory)

### Un-stage 1 file

```bash
git restore --staged <file>
```

Ví dụ:

```bash
git restore --staged index.js
```

### Un-stage tất cả file

```bash
git restore --staged .
```

> Dấu `.` nghĩa là tất cả file

### Khi dùng?
Đã `git add` nhầm file nhưng chưa commit.

---

## 1.3 Un-commit (Repository → Staging)

Đưa commit cuối về staging:

```bash
git reset --soft HEAD~1
```

### Kết quả
- Commit bị xoá
- Code vẫn còn
- File vẫn nằm ở staging
c. Thêm file .gitignore, thêm vào 2 dòng:
### Khi dùng?
Muốn commit lại với message mới hoặc chỉnh sửa thêm.

---

## 1.4 Un-commit (Repository → Working Directory)

Đưa commit cuối về working directory:

```bash
git reset HEAD~1
```

### Kết quả
- Commit bị xoá
- Code vẫn còn
- File không còn ở staging

### Khi dùng?
Muốn sửa code trước khi add + commit lại.

### Lưu ý
- Commit đầu tiên không reset được
- Nếu cần reset commit đầu tiên:
  - Xoá thư mục `.git`
  - `git init` lại

---

# 2. Git - Branching

## 2.1 Branch là gì?

Branch = nhánh phát triển riêng trong project.

### Mục đích của branch
- Làm feature mới mà không ảnh hưởng code stable
- Team làm việc độc lập
- Dễ thử nghiệm
- Sai thì xoá branch

### Bản chất branch
Branch **không copy code**.

Nó chỉ là một **pointer** trỏ tới commit.

Ví dụ:

```text
main: A → B → C
             ↑
feature/login
```

Khi có commit mới:

```text
main: A → B → C
                \
feature/login:   D → E
```

---

## 2.2 Commands thường dùng

### Xem branch

```bash
git branch
```

> Cần có ít nhất 1 commit

---

### Tạo branch

```bash
git branch feature/login
```

---

### Chuyển branch

```bash
git checkout feature/login
```

---

### Tạo + chuyển branch luôn

```bash
git checkout -b feature/login
```

---

### Xoá branch local

```bash
git branch -D feature/login
```

> Phải đứng ở branch khác trước khi xoá

---

### Push branch lên GitHub

```bash
git push origin feature/login
```

---

### Xoá branch remote

```bash
git push -D origin feature/login
```

---

# 3. Git - .gitignore

## 3.1 `.gitignore` là gì?

File cấu hình để Git **không track** file/folder không cần thiết.

---

## 3.2 Vì sao cần `.gitignore`?

Để bỏ qua:

### File nặng
```text
node_modules/
dist/
build/
```

### File nhạy cảm
```text
.env
password
api key
certificate
```

### File hệ điều hành
```text
.DS_Store
Thumbs.db
```

### File log
```text
*.log
```

---

## 3.3 Syntax `.gitignore`

### Ignore 1 file

```gitignore
secret.txt
```

---

### Ignore extension

```gitignore
*.log
```

---

### Ignore folder

```gitignore
node_modules/
build/
```

---

### Ignore trong thư mục con

```gitignore
**/*.tmp
```

---

### Exception (không ignore)

```gitignore
!important.log
```

---

### Ignore file ở root

```gitignore
/TODO
```

---

## 3.4 Practice

Tạo:

```text
.env
.env.example
.env.dev
.env.prod
```

Thêm vào `.gitignore`:

```gitignore
.env
.env.dev
.env.prod
```

Kiểm tra:

```bash
git status
```

> `.env.example` vẫn track để team biết format env.

---

# 4. JavaScript - Condition (Câu điều kiện)

## 4.1 Dùng để làm gì?

Kiểm tra logic trước khi chạy code.

**Điều kiện đúng → chạy**

---

## 4.2 Các loại condition

- `if`
- `if...else`
- `if...else if...else`
- `switch...case`

---

## 4.3 Basic if

```js
let hour = 8;

if (hour <= 11) {
  console.log("Good morning");
}
```

---

## 4.4 Multiple conditions

```js
let hour = 8;

if (hour >= 6 && hour <= 11) {
  console.log("Good morning");
}
```

### Operators thường dùng

```text
&&  AND
||  OR
!   NOT
```

---

## 4.5 Nested condition

```js
let hour = 8;

if (hour >= 6) {
  if (hour <= 11) {
    console.log("Good morning");
  }
}
```

---

# 5. JavaScript - Loop (Vòng lặp)

## 5.1 Dùng để làm gì?

Lặp lại một đoạn logic nhiều lần.

---

## 5.2 Các loại loop

- `for`
- `for...of`
- `forEach`
- `for...in`
- `while`
- `do...while`

---

## 5.3 for loop syntax

```js
for (khởi_tạo; điều_kiện; cập_nhật) {
  // code
}
```

### Ý nghĩa

#### Khởi tạo
Chạy 1 lần duy nhất.

#### Điều kiện
Đúng → tiếp tục  
Sai → dừng

#### Cập nhật
Thay đổi biến đếm mỗi vòng.

---

## 5.4 Example

```js
for (let i = 0; i < 5; i++) {
  console.log("Xin chào!");
}
```

### Flow

```text
i = 0 → chạy
i = 1 → chạy
i = 2 → chạy
i = 3 → chạy
i = 4 → chạy
i = 5 → dừng
```

---

# 6. JavaScript Convention

## 6.1 Convention là gì?

Convention = quy tắc viết code.

### Mục đích
- Code dễ nhìn
- Team dễ đọc code
- Code đồng nhất

---

## 6.2 Một số loại convention

- Đặt tên file
- Đặt tên biến
- Đặt tên commit
- Format code

---

## 6.3 Naming Convention phổ biến

### snake_case

```text
user_name
first_name
```

---

### kebab-case

```text
login-page
do-minh-phong
```

---

### camelCase

Chữ đầu viết thường, các chữ sau viết hoa.

```text
userName
firstName
doMinhPhong
```

---

### PascalCase

Mỗi từ viết hoa chữ cái đầu.

```text
UserProfile
LoginPage
DoMinhPhong
```

---

# Quick Summary

## Git
- `git commit --amend` → sửa commit message
- `git restore --staged` → un-stage
- `git reset --soft HEAD~1` → un-commit về staging
- `git reset HEAD~1` → un-commit về working directory
- Branch = pointer tới commit
- `.gitignore` để bỏ file không cần track

## JavaScript
- Condition → kiểm tra logic
- Loop → lặp code
- `for` gồm: khởi tạo → điều kiện → cập nhật
- Convention giúp code dễ đọc & đồng nhất
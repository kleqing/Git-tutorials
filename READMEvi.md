Git Commands
============

## Phiên bản khác đã được dịch
- [English](README.md)
___

_Dưới đây là 1 vài mẹo dùng git mà mình học được_

*Lưu ý: Đây không phải là fork từ [Git-Commands](https://github.com/joshnh/bash_profile/blob/master/.bash_profile) rồi dịch lại mà là 1 vài hướng dẫn cách dùng cơ bản các câu lệnh git mà mình học được!*

---

### Đăng kí với Git (Nếu cài đặt qua [Git](https://git-scm.com))

| Lệnh | Mô tả |
| ------- | ----------- |
| `git config --global user.name "[username]"` | Chỉ định username của người dùng (thay [username] bằng username bạn muốn, có thể là giống với trên Github) |
| `git config --global user.email [email address]` | Chỉ định email của người dùng (khuyến khích dùng email giống với tài khoản Git của bạn) |
| `git config --system init.defaultbranch [branch]` | Đổi branch mặc định của Git (Thông thường, Git mặc định là `master`. Nếu bạn gặp vấn đề khi push vì `master` và `main` khác nhau, hãy sử dụng lệnh này để thay đổi branch mặc định) |

### Bắt đầu với repo

| Lệnh | Mô tả |
| ------- | ----------- |
| `git init` | 	Chỉ dùng khi bạn đã tạo một repository trên Github và làm việc với dự án trên local. Dùng lệnh này để khởi tạo một Git repository trên máy tính của bạn. |
| `git remote add origin https://github.com/username/repository.git` | Liên kết repository local với remote Git (giúp bạn có thể push từ local lên Git) |
| `git pull origin [branch] --allow-unrelated-histories` | **NOTE: Chỉ chạy lệnh này sau khi chạy 2 lệnh trên nếu như trên Git của bạn có sẵn các file như `README`,`.gitignore`,... hoặc những file khác** |
| `git clone https://github.com/username/repository.git` | Clone một repository từ Git |

### Làm việc với repo

| Lệnh | Mô tả |
| ------- | ----------- |
| `git status` | Kiểm tra trạng thái của repo trên local |
| `git add [file-name.txt]` | Thêm một file vào staging area |
| `git add -A` hoặc `git add .` | Thêm tất cả file vào staging area |
| `git commit -m "[commit message]"` | Thêm commit message khi commit |
| `git rm -r [file-name.txt]` | Xoá một file khỏi local và staging area |
| `git rm --cached [file-name.txt]` | Xoá một file khỏi staging area nhưng vẫn giữ lại trên local |
| `git remote -v` | Kiểm tra tình trạng remote |

* **Tips:** ***Nếu bạn lỡ commit nhưng chưa push, có thể dùng các lệnh sau:***

| Lệnh | Mô tả |
| ------- | ----------- |
| `git reset --soft HEAD~1` | Hủy commit gần nhất và đưa file về trạng thái chưa commit |
| `git reset --hard HEAD~1` | Hủy commit gần nhất và xóa luôn file kèm theo (không thể khôi phục) |
| `git reflog` -> `git reset --hard [<mã HEAD]` | Nếu bạn lỡ dùng `--hard` thì có thể dùng hai lệnh này để chọn HEAD bạn muốn quay lại |

### Branch & Merge (Khuyến khích merge trên Git)

| Lệnh | Mô tả |
| ------- | ----------- |
| `git branch` | Liệt kê các branch trên Git |
| `git branch -a` | Liệt kê tất cả các branch (local và remote) |
| `git branch [branch name]` | Tạo một branch mới |
| `git branch -d [branch name]` | Xoá 1 branch |
| `git push origin --delete [branch name]` | Xoá branch trên remote |
| `git checkout -b [branch name]` | Tạo một branch mới và chuyển sang branch đó |
| `git checkout -b [branch name] origin/[branch name]` | Clone một branch từ remote và chuyển sang branch đó |
| `git branch -m [old branch name] [new branch name]` | Đổi tên branch |
| `git checkout [branch name]` | Chuyển sang branch khác |
| `git checkout -` | Chuyển sang branch vừa chuyển trước đó (ví dụ: `main` -> `dev`sử dụng lệnh này sẽ quay lại `main`) |
| `git checkout -- [file-name.txt]` | Hủy thay đổi của một file |
| `git merge [branch name]` | Merge một branch vào branch hiện tại |
| `git merge [source branch] [target branch]` | Merge một branch vào branch khác |
| `git stash` | Lưu các thay đổi tạm thời trên file/thư mục |
| `git stash clear` | Hủy các thay đổi tạm thời đã lưu |
| `git stash pop` | Khôi phục lại các thay đổi đã lưu |

* **Tips:** ***Nếu bạn đang làm việc ở branch này nhưng quên đổi sang branch khác và không muốn mất các file thay đổi, bạn có thể dùng `git stash`, sau đó checkout rồi `pop` là được!*** 

### Update

| Lệnh | Mô tả |
| ------- | ----------- |
| `git push origin [branch name]` | Push một branch từ local lên remote repository |
| `git push -u origin [branch name]` | Push các thay đổi từ local lên remote và ghi nhớ branch đó cho các lần push sau |
| `git push` | Push các thay đổi tới remote repository với branch đã ghi nhớ trước đó |
| `git push origin --delete [branch name]` | Xoá branch trên remote repository |
| `git pull` | Cập nhật repository local với các commit mới nhất từ remote |
| `git pull origin [branch name]` | Kéo các thay đổi từ branch đã chọn từ remote repository về local |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Liên kết repository local với remote bằng SSH |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Đặt URL SSH cho repository remote |

### Kiểm tra & So sánh

| Lệnh | Mô tả |
| ------- | ----------- |
| `git log` hoặc `git reflog` | Xem các thay đổi |
| `git log --summary` | Xem các thay đổi (chi tiết) |
| `git log --oneline` | Xem các thay đổi (ngắn gọn) |
| `git diff [source branch] [target branch]` | Xem các thay đổi giữa hai branch trước khi merge |

### Bonus

Đây chỉ là 1 trong số ít các câu lệnh mà bạn sẽ dùng nhiều khi làm việc với git. Bạn có thể tham khảo thêm ở 1 vài nguồn khác:
- [Awesome Git Commands](https://github.com/onmyway133/awesome-git-commands)
- [Atlassian Git](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
- [Git game](https://github.com/git-game/git-game)
- [Learn Git Branching](https://learngitbranching.js.org/)
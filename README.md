# ISUCON13-BKOLD-training

## ISUCON13 Info

https://isucon.net/archives/57801192.html
Tao mot github repo ~ 12/11 - Tuan (IN PROGRESS)
Try connect repo ~ 25/11 - ALL
Deploy app script ~ 18/11 - Tuan
(optional) Deploy DB server ~ 18/11
Vi du migrate database (sqlite -> mysql / mysql -> cachedb) -> sua file init.sql, init.sh -> docker compose up db
(optional) Config nginx server script ~ 18/11 - Tuan
Log format ? ~ 18/11 - Default - Tue
Order theo cai gi, top 10/20/100
Log tool ~ 11/11 - Tue
ALP, ...
Config slowquery ~ 11/11 - Son
Copy command SCP from Remote server ve Local ~ 11/11 - Son
https://stackabuse.com/copying-a-directory-with-scp -

## Deploy script

- Makefile deploy local to server (DUC init deploy source code)
  check current_dir/deploy-local-server.template
  https://www.freecodecamp.org/news/scp-linux-command-example-how-to-ssh-file-transfer-from-remote-to-local
  (optional) Setting ALB tren nhieu server ~ 11/11 - Son

## Flow

1, Check manual

### Fresh Start flow

1, Check servers
ssh all servers
2, tim hieu cau truc thu muc (default: home/isucon/webapp)
3.1, run benchmark (Từ bước 1)
3.2,
Tuấn 1, Copy code từ server về local.
Tuấn 2, Push len github.
/ git push origin [branch_name]

### Init flow

4, All 1, Team tu pull code ve
/ git pull origin main
5, All 2, Team phân tích application (Check Application manual)
6, All 3, Tạo deploy script

### Application,DB Flow

7.1, Tuệ, setup nginx log
7.2, Đức, Enable DB slow query
8, All, Phân tích slow query
9.1, Tuấn, Sửa application logic (N+1, etc)
9.2, Đức, Sửa DB schema (Đánh index, etc)
9.3, Tuệ, Sửa DB schema (Đánh index, etc)
--- Sau khoảng 3 tiếng sửa slow query, (Đến >10.000 14:00, hoặc no hope)

### Infra

10, check cache image, css, js, etc (tuỳ đề)
11, check timeout
12, check architecture
/ dùng lệnh top, etc, để check cpu, memory của từng server
13, rearchitecture
/ case 1: scale DB server
/ case 2: scale Application server
/ case 3: Key-value server

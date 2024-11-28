# Git

```javascript
Gitflow
------------------
Các nhánh tương ứng với các môi trường:
test MOR: develop
staging: staging
production: main (hoặc master)
---------------------
Nhánh staging được checkout từ main
-----------------------
Release lần đầu lên production
checkout nhánh release/1.0.0 từ nhánh develop
Tạo PR merge nhánh release/1.0.0 vào nhánh staging
--------------------------
Các bug phát sinh trong thời gian khách UAT version 1.0.0 này được checkout và sửa trên nhánh release/1.0.0
Sau đó sẽ merge release/1.0.0 vào develop để test lại trên MOR.
Test done MOR sẽ merge release/1.0.0 vào staging để test lại trên staging.
Khi nào golive lên production, nhánh release/1.0.0 sẽ được merged vào main (hoặc master)
Tag the main (or master) theo release version number:  v1.0.0

```

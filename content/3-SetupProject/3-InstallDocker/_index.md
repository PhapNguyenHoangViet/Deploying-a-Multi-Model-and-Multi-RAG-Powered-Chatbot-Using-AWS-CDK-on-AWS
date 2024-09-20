+++
title = "Cài đặt Docker"
date = "`r Sys.Date()`"
weight = 3
chapter = false
pre = "<b>3.3. </b>"
+++

1. **Cập nhật danh sách gói** trên hệ thống của bạn.

```
sudo apt-get update
```

![installdocker](/images/3-setupproject/3-installdocker/001-3-installdocker.png?width=90pc)

2. Cài đặt **Docker**.
```
sudo apt-get install -y docker.io
```

![installdocker](/images/3-setupproject/3-installdocker/002-3-installdocker.png?width=90pc)

3. Khởi động **Docker service** and **enables Docker** khởi động tự động khi khởi động hệ thống.
```
sudo systemctl start docker
sudo systemctl enable docker
```

![installdocker](/images/3-setupproject/3-installdocker/003-3-installdocker.png?width=90pc)

4. Thêm người dùng của bạn vào nhóm Docker để có thể chạy các lệnh Docker mà không cần `sudo`.
```
sudo usermod -aG docker $USER
```

![installdocker](/images/3-setupproject/3-installdocker/004-3-installdocker.png?width=90pc)

5. Hiển thị phiên bản **Docker** đã cài đặt.
```
docker --version
```

![installdocker](/images/3-setupproject/3-installdocker/005-3-installdocker.png?width=90pc)

6. Cập nhật nhóm hiện tại của người dùng để áp dụng thay đổi.
```
newgrp docker
groups $USER
ls -l /var/run/docker.sock
```

![installdocker](/images/3-setupproject/3-installdocker/006-3-installdocker.png?width=90pc)

7. Thiết lập quyền trên tệp socket Docker.
```
sudo chmod 660 /var/run/docker.sock
```

![installdocker](/images/3-setupproject/3-installdocker/007-3-installdocker.png?width=90pc)



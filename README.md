Dispatch is the service which dispatches the product after purchase.
It is written in GoLang, So wanted to install GoLang.

1. Install GoLang

```
# yum install golang -y
```

2. Add roboshop User

```
# useradd roboshop
```

3. Switch to roboshop user and perform the following commands.

```
$ curl -L -s -o /tmp/dispatch.zip https://github.com/roboshop-devops-project/dispatch/archive/refs/heads/main.zip
$ unzip /tmp/dispatch.zip 
$ mv dispatch-main dispatch 
$ cd dispatch 
$ go mod init dispatch
$ go get 
$ go build 
```

4. Update the systemd file and configure the systemd service

```
# mv /home/roboshop/dispatch/systemd.service /etc/systemd/system/dispatch.service
# systemctl daemon-reload
# systemctl enable dispatch 
# systemctl start dispatch
```
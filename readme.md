# ติดตั้งโปรแกรม Golang

```
./docker pull golang:1.14-alpine
```
# command Golang ใน shell
```
./docker run -it golang:1.14-alpine sh
```
# เช็คโปรแกรม
```
./go # go version
./go version go1.14.1 linux/amd64
```
# สร้างโฟลเดอร์มา 1 โฟลเดอร์ 
```
./ mkdir golang
./cd golang
```
# สร้างไฟล์ docker-compose.yml & main.go
```
./touch docker-compose.yml main.go //สร้างไฟล์ docker-compose.yml & main.go

```
# เริ่มต้นการใช้งาน ในโฟลเดอร์
```
./git init
./vim docker-compose.yml                                                                                                                                       
./cat docker-compose.yml                                                                  
```
# ไฟล์ข้างใน docker-compose.yml
```
version: "3.7"
services:  
  api:
    image: golang:1.14-alpine
    command: go version
```
# Run & Check Version
```
./docker -compose up         
./docker-compose version 
```
# ไฟล์ข้างใน main.go
```
./vim main.go
./cat main.go 

package main

import "fmt"

func main() {
    fmt.Println("hello man")
}

```
# ทำการรัน 
```
./docker-compose up                                                                                                                                            
Starting golang_api_1 ... done
Attaching to golang_api_1
api_1  | hello man
golang_api_1 exited with code 0

./docker-compose run api                                                                                                                                       
hello man
```
# เข้า Command go api sh
```
docker-compose run api sh                                                                                                                                    
/go/src/go-docker # ls
docker-compose.yml  main.go
/go/src/go-docker # ls
docker-compose.yml  main.go             man
/go/src/go-docker # touch man-container
/go/src/go-docker # go mod init
go: creating new go.mod: module go-docker
/go/src/go-docker # go mod tidy
/go/src/go-docker # 
```
# check line
```
tig                                                  
git log --online 
```
*(ต้องทำการ settimg tig)
# settimg tig
```
brew install tig
```
# go mod
```
./git init
./vim docker-compose.yml                                                                                                 
./cat docker-compose.yml   

command: go mod init

#Code
version: "3.7"
services:
  api:
    image: golang:1.14-alpine
    volumes:
      - .:/go/src/go-docker
    working_dir: /go/src/go-docker
    command: go mod init
```

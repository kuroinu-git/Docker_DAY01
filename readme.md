

---docker pull golang:1.14-alpine-- //ติดตั้ง โปรแกรม

---docker run -it golang:1.14-alpine sh
//  /go # go version
//   go version go1.14.1 linux/amd64

--- mkdir golang
--- cd golang

-- touch docker-compose.yml main.go //สร้างไฟล์ docker-compose.yml & main.go


-- git init

-- vim docker-compose.yml                                                                                                                                       ✭
-- cat docker-compose.yml                                                                                                                                       ✭
version: "3.7"
services:  
  api:
    image: golang:1.14-alpine
    command: go version
--docker -compose up         
--docker-compose version 

-- vim maim.go
--cat main.go 

-- docker-compose up                                                                                                                                            ✭
Starting golang_api_1 ... done
Attaching to golang_api_1
api_1  | hello man
golang_api_1 exited with code 0

--docker-compose run api                                                                                                                                       ✭
hello man

docker-compose run api sh                                                                                                                                    ✭
/go/src/go-docker # ls
docker-compose.yml  main.go
/go/src/go-docker # ls
docker-compose.yml  main.go             man
/go/src/go-docker # touch man-container
/go/src/go-docker # go mod init
go: creating new go.mod: module go-docker
/go/src/go-docker # go mod tidy
/go/src/go-docker # 


tig                                                  ✚
git log --online 

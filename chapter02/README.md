---
theme: gaia
paginate: true
class: section
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.jpg')
style: |
  section {
    font-size : 1.4rem;
  }
marp: true
---

# What to do

- DB를 사용하는 간단한 방명록 서비스
- 프론트, 서버, DB 가 별도의 컨테이너에 존재
- 외부 IP에서 프론트 서버는 접근 가능 API 서버,DB서버는 접근 불가능

---

# Docker 키워드

## Run

```
docker run -i -t ubuntu
```

`docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`

- -i : interactive (대화형)
- -t : pseudo-tty
- -it : -i -t
- -d : --detach docker 이미지를 background 에서 작동하도록 함
- --rm : 종료시 자동 삭제

- https://docs.docker.com/engine/reference/commandline/run/

---

## Create

```
docker start my_container
```

![w:500 h:320](../image/runVSstart.jpeg)

- https://docs.docker.com/engine/reference/commandline/start/

---

## attach

---

## Pull

```
docker pull debian
```

`docker pull [OPTIONS] NAME[:TAG|@DIGEST]`

- https://docs.docker.com/engine/reference/commandline/pull/
- https://www.44bits.io/ko/post/how-docker-image-work
- https://devaom.tistory.com/5

---

## ps

```
docker ps
```

- https://docs.docker.com/engine/reference/commandline/ps/

---

## rm

#### shotCut

`docker rm $(docker ps -a -q)`
`docker container prune`

- https://docs.docker.com/engine/reference/commandline/rm/

---

## stop

---

# Network

## Inside of network

![w:500 h:320](../image/docker-network.png)

- veth => virtual eth
- docker() => 각 veth 인터페이스와 바인딩 돼 호스트의 eth()인터페이스와 이어주는 역할
- https://joont92.github.io/docker/network-%EA%B5%AC%EC%A1%B0/

---

## network driver

- bridge
  - 컨테이너와 컨테이너를 연결할때 사용
  - connect, disconnect 명령어 사용 가능
- host
  - 호스트의 네트워크 환경을 사용가능
- none
  - 외부와 단절
- contanier
  - 다른 컨테이너의 네트워크 네임 스페이스 공유 가능
- overlay

---

## link

- link를 쓸때 주의 할 점
  - link 의 대상이 되는 컨테이너가 없다면 컨테이너가 실행되지 않음!
  - deprecated

---

## docker port

---

# Volume

---

## -v

```
\[호스트의 디렉토리\]:\[컨테이너의 디렉토리\]
```

- 컨테이너에 해당 디렉토리의 파일이 있다면 덮어쓰기가 됨

## --volumes-from

![w:500 h:320](../image/--volumes-from.png)

---

## docker volume

### volume 은 어디 있을까?

```
docker volume inspect [VOLUME_NAME]
```

```
❯ docker volume inspect minikube
[
    {
        "CreatedAt": "2020-09-03T05:03:16Z",
        "Driver": "local",
        "Labels": {
            "created_by.minikube.sigs.k8s.io": "true",
            "name.minikube.sigs.k8s.io": "minikube"
        },
        "Mountpoint": "/var/lib/docker/volumes/minikube/_data",
        "Name": "minikube",
        "Options": {},
        "Scope": "local"
    }
]
```

---

```
❯ cd /var/lib/docker/volumes/minikube/_data
cd: no such file or directory: /var/lib/docker/volumes/minikube/_data
```

맥/윈도우 에서는 VM 위에서 작동하므로 실제 위치는 다른 곳에 위치

실제는 여기 (도커 버전, OS 버전 바다 다름)

```
~/Library/Containers/com.docker.docker/Data/vms/0/Docker.raw
```

- https://stackoverflow.com/questions/19234831/where-are-docker-images-stored-on-the-host-machine/37642236#37642236

---

# log

---

# Docker Image

---

## Docker Image 생성

---

## Docker 이미지의 구조

---

## Docker 이미지 추출

---

## Docker 이미지 배포

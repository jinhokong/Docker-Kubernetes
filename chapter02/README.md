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

- DB를 사용하는 간단한 블로그 서비스
- 장고 서버, DB, log 서버 가 별도의 컨테이너에 존재
- 각 이미지는 로컬에 자신의 레지스터리에 올림

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

## Pull

```
docker pull debian
```

`docker pull [OPTIONS] NAME[:TAG|@DIGEST]`

- https://docs.docker.com/engine/reference/commandline/pull/

---

##

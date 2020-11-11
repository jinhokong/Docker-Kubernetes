**실행순서**

1. mongodb
2. backend (mongodb를 바라봄)
3. frontend (backend를 바라봄)

**frontend**

| 정보                   | 내용                               |
| ---------------------- | ---------------------------------- |
| 이미지                 | subicura/guestbook-frontend:latest |
| 리스닝 포트            | `PORT` 환경변수                    |
| PORT ENV               | 리스닝 포트로 설정                 |
| GUESTBOOK_API_ADDR ENV | Backend 서버 주소 ex) backend:8000 |

**backend**

| 정보                  | 내용                              |
| --------------------- | --------------------------------- |
| 이미지                | subicura/guestbook-backend:latest |
| 리스닝 포트           | `PORT` 환경변수                   |
| PORT ENV              | 리스닝 포트로 설정                |
| GUESTBOOK_DB_ADDR ENV | DB 서버 주소 ex) mongodb:27017    |

**mongodb**

| 정보        | 내용    |
| ----------- | ------- |
| 이미지      | mongo:4 |
| 리스닝 포트 | 27017   |

- frontend / backend 서버의 리스닝 포트는 정해져있지 않고 `PORT` 환경변수를 따라갑니다.

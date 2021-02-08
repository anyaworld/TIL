# Ngrok

## how to insall

1. download here [link](https://ngrok.com/download)

1. unzip

1. 실행

1. mac >> 시스템 환경 설정 >> 보안 및 개인 정보 보호 설정 > 일반 > 다음에서 다운로드한 앱 허용 -> 허용

## How to use

1. <http://localhost> 를 실행하고 ngrok 실행한다.

1. ./ngrok http port_number ( ex ./ngrok http 8080)

    ```bash
    Forwarding    https://aaaaaaaaaaaa.ngrok.io -> http://localhost:8080
    ```

    aaaaaaaaaaaa 부분이 임시로 만들어진 https 로 된 부분이고 localhost로 리다이렉션된다.

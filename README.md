# 리눅스 기반 원격 하드웨어 제어 시스템 (Remote Device Control System)

## 1. 프로젝트 개요
TCP/IP 소켓 통신을 이용하여 라즈베리파이에 연결된 하드웨어(LED, Buzzer, FND, CDS)를 원격(Ubuntu PC)에서 제어하고 모니터링하는 시스템입니다.  
서버는 **데몬(Daemon)** 프로세스로 동작하며, 하드웨어 제어부는 **공유 라이브러리(.so)**로 분리하여 유지보수성을 높였습니다.

## 2. 개발 환경
* **Target:** Raspberry Pi 4 (Raspbian OS)
* **Host:** Ubuntu Linux 20.04 LTS
* **Language:** C (Standard C99)
* **Libraries:** WiringPi, Pthread
* **Build Tool:** Make (Makefile)

## 3. 디렉토리 구조
project_submit/
├── code/
│   ├── client/ (클라이언트 소스)
│   ├── server/ (서버 및 라이브러리 소스)
│   └── Makefile (통합 빌드 스크립트)
├── exec/
│   ├── lib/ (생성된 공유 라이브러리 위치)
│   ├── server (서버 실행 파일)
│   └── client (클라이언트 실행 파일)
└── docs/ (개발 문서)

## 4. 빌드 방법 (Build)
`code` 디렉토리로 이동하여 `make` 명령어를 실행합니다.
```bash
$ cd code
$ make

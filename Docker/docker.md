# Docker
<br>

## Docker 란?
<br>

>#### 애플리케이션을 신속하게 구축, 테스트 및 배포할 수 있는 소프트웨어 플랫폼이다.
>#### Docker는 소프트웨어를 컨테이너라는 표준화된 유닛으로 패키징한다.
>#### 이 컨테이너에는 라이브러리, 시스템 도구, 코드, 런타임 등 소프트웨어를 실행하기 위해 필요한 모든 것이 포함되어 있다.  
<br><br>

### Docker 장점
<br>

> - 기존 가상머신에 비해 성능 오버헤드가 적다. <br>
> - 빠르고 쉽게 애플리케이션을 배포할 수 있다. <br>
> - 이미지 버전 관리가 쉽다.
> - 각 컨테이너 사이에 독립적인 동작 환경을 제공한다.

<br><br>

### 기존 방식과 비교
<br>

| 기존 방식 | Docker |
|----|:---:|
| `OS를 가상머신마다 중복 설치`  | `OS를 가상머신마다 중복 설치 X`|
| `이미지 크기가 큼` | `이미지 크기가 작음 (배포 편리)` |
| `OS를 가상화하여 느림` | `직접 호스트의 OS 자원을 사용하여 빠름` |
<br><br>

### Image & Container
<br>

> #### 서버 구성에 필요한 파일들을 묶어 놓은 것이다.
> #### 실행파일 = Image, 프로세스 = Container
> #### 실행파일, 라이브러리, 설정파일 등을 포함한다.
> #### push 와 pull을 사용하여 배포 단위로 저장소에 올리고 받을 수 있다.
<br><br>

## Docker 명령어
<br>

### Docker 목록
<br>

- Container가 죽은 목록을 포함하여 확인할 때는 -a 옵션 추가
```
$ docker ps 
$ docekr ps -a
```
<br>

### Docker Image 설치
<br>

```
$ docker pull <이미지 이름>:<태그>
```
<br>

### Docker Image 확인
<br>

```
$ docker images
```
<br>

### Docker run
<br>

- -it는 쉘을 실행시키기 위한 옵션, bash를 실행한다. 
- --name 옵션을 주면 이미지의 별칭을 설정할 수 있다. 
```
$ docker run -it <이미지이름:태그> <command>

ex)
$ docker run -it test:latest bash
```
<br>

### Docker stop
<br>

```
$ docker stop test
```
<br>

### Docker Container 들어가기
<br>

```
$ docker exec -it test /bin/bash
```
<br>

### Docker Container 삭제
<br>

- 태그이름을 지정하지 않으면 모든 태그가 삭제된다.
```
$ docker rm <컨테이너이름>
$ docker rmi <컨테이너이름>:<태그이름>
```
<br>


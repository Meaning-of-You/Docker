# Ubuntu 설치 및 실행

> Docker image를 통해 Ubuntu 설치



### Ubuntu 설치

##### 이미지 다운로드

```shell
$ docker pull [다운로드 할 이미지 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfNDQg/MDAxNTg4NDM5OTk3OTI2.mSa5vSiixM1iY5jawbtNC46_NSlsnqC8h57VUOh5KSMg.LU6w7GEHum2IShvdGnQpm8Kxxi_RoOFJltvT2DWBHA0g.PNG.oymlmjo/SE-c1083d45-8ef4-4f43-aeca-b4b18296da59.png?type=w773)



##### 다운로드한 이미지 목록 확인

```shell
$ docker images
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTQx/MDAxNTg4NDQxMzcxNjQ2.B2mYXTHY2VwKpd5g-P3wDBWsrO_t3IJIUPtZ1-nAp3gg.suek311vsmg8KRAqeEkaxgVDObdf6flk-6KmqcreRTwg.PNG.oymlmjo/SE-6c5da395-cb45-4f60-bad6-b443a79bccf4.png?type=w773)



#####  Container 생성

- `-i`: 상호 입출력
- `-t`: tty를 활성화해서 bash 셸 사용

```shell
$ docker create -it --name [컨테이너 명] [이미지 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjI4/MDAxNTg4NDQyMDU4MjQy.STnUEkDEy0fDJn8YRfGjJgMenaji7TeGnu-Nc51epAsg.d-RtmPiiFpDkP-H8MHjjryfQS7O3v7TzB-QFgaMexQYg.PNG.oymlmjo/image.png?type=w773)



##### 프로세스 확인 

- `-a`: 모든 프로세스 확인

```shell
$ docker ps
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjg5/MDAxNTg4NDQyMTQ4NTE4.Gzll6IgopOk_hi2CW0uSXdTf4-xTOlMznYZCwU8zNb4g.Ptg8OOOcy32nGH0vHqY-8_OEpIbejAmcHln3XH85gcQg.PNG.oymlmjo/image.png?type=w773)



### Ubuntu 실행

##### 생성된 container 실행

```shell
$ docker start [컨테이너 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTI0/MDAxNTg4NDQyNzA0NTIw._WOBrr3y1njZUAiKhv67XI2xN5F0MjTLDTdvC8UZ10Ug._H6C_5KiC5UcmPhEIetLfmQG7JDbjfs1JakI9Xn6koQg.PNG.oymlmjo/image.png?type=w773)

- Ubuntu 실행 시 STATUS는 Up으로 나타남

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfNzIg/MDAxNTg4NDQyODQ3NzUx.FQkXAZzZiqB3nDiRpDhN-zh6J-vJRyLEKnJa5PF-zSUg.979Uv-9M_Sgxo0Gpn5OfYiFQ9q9-yaTYqmqVNN3lhhwg.PNG.oymlmjo/image.png?type=w773)



##### container 접속

```shell
$ docker attach [컨테이너 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjM0/MDAxNTg4NDQzMzE5Mzc4._vRSgM520nyHCuAcknofa7Kv3GkFguwaeDyyZOWtc90g.SbMQVP48b5IxpBM-21TwKkQgcJUKFcJpjR9N6xlsNnAg.PNG.oymlmjo/image.png?type=w773)

- 정상적으로 접속되면 root@~~~:/#으로 쉘 변경



##### container 종료

```shell
exit
```



### container 명령어

##### container 이름 변경

```shell
$ docker rename [기존 컨테이너 명] [변경할 컨테이너 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjQ3/MDAxNTg4NDQ0Mjk2NTI1.AJjS8yDu9fjPnuTNmcHTRvHfqcNkMeSBSFGXN52ftFwg.CS00vYOtXS6ki1LaVZuXeYlRMkdo0VCgOSGYLHxcuIkg.PNG.oymlmjo/image.png?type=w773)

##### container 중지

```shell
$ docker stop [컨테이너 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTAx/MDAxNTg4NDQ0Mzg5NzIz.aFdbiS8EcYYh5Vax8qfPz_5nTqLjEfiObry5ENJGOSsg.o2LjqAk3BTByItYlvc8bdJZShbANtfm7HCljBHyv60Ig.PNG.oymlmjo/image.png?type=w773)

##### container 삭제

- 중지 후 재실행이 가능한 stop과 달리 모든 내용이 삭제 되므로 주의

```shell
$ docker rm [컨테이너 명]
```

- container가 실행중인 상태에서 삭제하면 오류 발생
  - `-f`: 실행중에도 삭제 가능

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTc5/MDAxNTg4NDQ0NjQ5NjIw.Efav9zglkfMYKUB-fdX7rgsQ99l1gju2IWaMSLvBnBwg.7-wNqxHr436SGI2ShtAgKKs-VZY92effAYpILPUi0d4g.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTg5/MDAxNTg4NDQ0NTkxOTAx.r6tLWp1hqxJR7Ga6slDmPdO1NYsS9jAaCz4HX2F7tJgg.VTZsbGG8CaK4DADRO7xkK8FbV7LKudMn_7B-oaf1Alcg.PNG.oymlmjo/image.png?type=w773)



##### 모든 container 삭제

```shell
$ docker container prune
```



##### container 생성 및 실행

- docker create + docker start + docker attach를 한번에 실행하는 것과 같음

```shell
$ docker run
```
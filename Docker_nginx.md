# nginx 설치 및 실행

> 웹 서버 소프트웨어 활용



### nginx 설치 및 컨테이너 생성

##### nginx 설치

```shell
$ docker pull nginx
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMTkz/MDAxNTg5NjIzMTY3ODQ3.cNN5mJ8mDd4g_CdFgP_mE6biDldlRTxsMPRMplFwEa4g.So2kj9t9yc7QOh_8WtQ2Qq8n_F-xEruGNqUHx8dw8qUg.PNG.oymlmjo/image.png?type=w773)



##### 설치 여부 확인

``` shell
$ docker images
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMTM1/MDAxNTg5NjIzMjAyMjE0.eeF8FHUUzLk-OIwuLDfB0rEIBFgxRxJurgj7Bj3IO98g.kK1GIOl9N1pUp8TItA3TCKAc9h3QuXOLEL_U4w-3Vt4g.PNG.oymlmjo/image.png?type=w773)



##### container 생성

```shell
$ docker container run --name [컨테이너 명] -d -p 80:80 nginx
```

- `-p 80:80`: 앞의 80은 Host port를, 뒤의 80은 컨테이너 port를 의미

- nginx의 경우 80:80으로 정해져 있기 때문에 다음과 같이 설정

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMjE4/MDAxNTg5NjIzMjczMTY4.WxIcyZ7ubVCZt6fCbbkyqYipF4MFDiDsytxhTG2showg.Kt11XIHKKjehJaBuO-hcmwKy5UOn-PHy89AxOUOkzO4g.PNG.oymlmjo/image.png?type=w773)



##### container 생성 및 실행 확인

```shell
$ docker ps -a 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMjg2/MDAxNTg5NjIzMzAyODAy.C1cI8fzdQwaS2HI2cNnuy1aDj7SIi4wtUDwD2CJanYYg.E1Pmw0ngNa0hXUH0cE6ceH2Hxkduc1g-AMESSrCIGw0g.PNG.oymlmjo/image.png?type=w773)



### Port Forwarding

- Windows와 docker사이에 Oracle VitualBox가 있으므로 바로 도커 컨테이너로 진입 할 수 없기 때문에  Port Forward를 해주어야 함

##### 방법

1. Oracle VM VirtualBox로 들어가서  [설정] - [네트워크]로 들어가게 되면 2개의 어댑터가 나타나는데, 고급을 눌러서 포트 포워딩 버튼을 누를 수 있는 어댑터 선택

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMjg2/MDAxNTg5NjI0Njk5MTc2.Yv730ovQv29YZawXCDfdQlKKjxo6V742j5AfaprtLdcg.JIFR_9P3-5xG98kRtibJlJ2-_0Fe9e3BunXVqeRzy4wg.PNG.oymlmjo/image.png?type=w773)

2. nginx의 경우  http로 통신하기 때문에 다음과 같이 포트 포워딩 규칙 생성

- 호스트 포트는 내 pc의 포트번호이고, 게스트 포트는 docker의 포트번호

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfODgg/MDAxNTg5NjI0OTY1NDMz.41__ENs39_7Oot8ee52zoRlkmoJ_5UWLogLfBSa8wLIg.VJnhUJPf7DlTRHlrlTTRTxn_OrMdK8ekmOMD_g3Zjh0g.PNG.oymlmjo/image.png?type=w773)



##### 웹브라우저에서 확인

- localhost:80 입력

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMTU3/MDAxNTg5NjI1Njk2NDM4.MyH5MHduY9FMeymjoX22RKzlMKihjnzFJGz4Ec0Pkdcg.OFH1_fKSWybreiHlErU7Dbo0exTjQdCu3KZoTnpKS0sg.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MTZfMTY3/MDAxNTg5NjI1NjEzNTIw.SfnIZSG4Z4-ePOuPSGGyomWlkA3DyQCgaS9r6twEbEQg.N_RbUM3fNBkdiP_U-tUTHFmKcrdy87K7yQy8DqrUHaYg.PNG.oymlmjo/image.png?type=w773)
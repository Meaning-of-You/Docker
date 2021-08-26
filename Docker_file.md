# 이미지 및 컨테이너 생성

> docker 파일 활용하기 



### Docker 파일 작성

##### Docker 폴더 생성

- 로컬 디스크 (C:) - Users 폴더 안에 Docker 폴더 생성

![img](https://postfiles.pstatic.net/MjAyMDA2MDZfMTgg/MDAxNTkxNDU0NjQxMjY3.KhnXflLjFHtvd0l13ghueAwyA_dt61wAIHTr1AcgJjgg.Df5a6CwXy9cciV71RuDL-l58jMBI1fE8XWO9Z7ZkUo4g.PNG.oymlmjo/image.png?type=w773)

##### 권한 수정

1. Docker 폴더에 대고 마우스 오른쪽을 클릭한 후, [속성] - [보안] - [편집]에 들어감

![img](https://postfiles.pstatic.net/MjAyMDA2MDZfNTUg/MDAxNTkxNDU0NzI1OTI4.QC47mjkmbRBO49HkDQWc7UvMHg8-VL5pw3KYRI2ajHog.d-AToX_UM6HcH14ykPEejh-1_7mfg4lqyYm5hIJg4WUg.PNG.oymlmjo/image.png?type=w773)

2. User의 사용 권한에서 수정 및 쓰기를 허용으로 수정

![img](https://postfiles.pstatic.net/MjAyMDA2MDZfMTU5/MDAxNTkxNDU0NzQ0NjM5.5TDBupI_QI98F_Vpq5MWErNxQjAOzly1fuhVNac14_4g.hUWjGzGCrkeLNKqCvsdjdVQIOjO1i1kOYdAX0hgoz28g.PNG.oymlmjo/image.png?type=w773)

##### Dockerfile 생성

1. Docker 폴더에 확장자없이 Dockerfile을 생성

![img](https://postfiles.pstatic.net/MjAyMDA2MDZfMjYg/MDAxNTkxNDU1MDQyNjc1.tEYUNrc-HI9fCwplPBAf5ZaK2h9TzROtkiaPGMKk37Eg.IozsdEt3jzCMyrUjuT_-8Vnt9fAy-LovUoSLk2A0fd0g.PNG.oymlmjo/image.png?type=w773)

2. 다음과 같이 Dockerfile 작성

- CMD ["nginx", "-g", "daemon off;"]로 수정해야함

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMjg4/MDAxNTkxNTE5MjI1Mjk2.808NNrGwMTlFwrgLihpG8brbfGObQyIIxCdAmqvvtLAg.-qRRXB_bqutopPWph9SZ6_6HNI_NHhSzu2FFqIVU__Eg.PNG.oymlmjo/image.png?type=w773)



### 이미지 및 container 생성

##### 이미지 생성

```shell
$ docker build --tag [계정명]/mydocker:0.1 .
```

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMTk3/MDAxNTkxNDYwNjk0NzY0.szxPNf5g0wy-2ujPUaCbEZeY0v0I_qq4qa-8KAMLn4Qg.5pQqEkx9OZgkyPQb1FOEL9X3aow42PF6AKLlUU1a89kg.PNG.oymlmjo/image.png?type=w773)



##### 이미지 확인

```shell
$ docker images
```

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMjg2/MDAxNTkxNDYxMDcwMjk4.hyIEbhhJ9mY6SQ_aoL8V667w0BtoLwxrVT4wov80aLcg.S7us5KFCG5WDwri8kgca5w80gXHP3Q4VpqvnDdpajI0g.PNG.oymlmjo/image.png?type=w773)



##### container 생성

```shell
$ docker run --name [컨테이너 명] -d -p 80:80 [계정명]/mydocker:0.1
```

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMjA4/MDAxNTkxNDU2MjEzMzEw.8nesKUC64G8oH4S9kRbQ46OUl4oWTz0Def5O7Fk2Aisg.G3RwfoB5mdQtR4XPR3t7g2Nsp6zQloBoNDe9ek03y2Ag.PNG.oymlmjo/image.png?type=w773)



##### container 실행 확인

```shell
$ docker ps -a 
```

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMTA2/MDAxNTkxNTE5NjAxODUy._cjHvh6TI6GNy5DCnWxmhQ4n1L_UdURhkwfN7fG1Uasg.sLj0DV876SLw_detVdBcyCg9k5GtclU_Rd6ZK0ZleMIg.PNG.oymlmjo/image.png?type=w773)



##### 웹브라우저 확인

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMTE1/MDAxNTkxNTE5NjU1Mjkx.PskBqMqF8MQBVEsOYCLA-YXjGqRPwdxyyVmp157cD30g.Bmy5c_AXTnEJIBLnh8XO4mx8Nb9d_u2iCOeKA-3urZcg.PNG.oymlmjo/image.png?type=w773)
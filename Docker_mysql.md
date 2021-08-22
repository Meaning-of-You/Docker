# MySQL 설치 및 실행

> Docker image를 통해 MySQL 설치



### MySQL 설치

##### 이미지 다운로드

```shell
$ docker pull [다운로드 할 이미지 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjkg/MDAxNTg4NDQ1ODY1MDgz.hPHMR4agIVQ-R-ItnRpjAOK7z3Zz4I0LQSmueq6zSUog.n6cZY0EOGMvhhwsISUJgoABy0UiUuGR8Bn234kjn6U8g.PNG.oymlmjo/image.png?type=w773)



##### 다운로드한 이미지 목록 확인

```shell
$ docker images
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjYx/MDAxNTg4NDQ1OTI5MDAx.H8vd0jyRLJHZsLb3v8tcehQlBHmmJ4EnjshlIrXkkcEg.xmjVYJT5NCxAcAp6BV7HoB60s5EgTfTVhmPUgLjHWeUg.PNG.oymlmjo/image.png?type=w773)



##### container 생성

```shell
$ docker run -d --name [컨테이너 명] -p 3306:3306 -e MYSQL_ROOT_PASSWORD=[비밀번호] mysql
```

- `-d `: 백그라운드 데몬 모드로 동작 

- `-p 3306:3306`: mysql의 3306 서비스 포트를 OS의 3306 포트와 연동 

- `-i -t`: 실행중인 컨테이너에 shell 접속을 가능하게 함

- `-e MYSQL_ROOT_PASSWORD=[패스워드] `: MySQL의 루트 계정의 패스워드를 설정

- `--name [컨테이너이름]`: 컨테이너 이름을 수동으로 지정

![Inkedimage_LI](../../../아비/Inkedimage_LI.jpg)



### MySQL 실행

##### container 접속

```shell
$ docker exec -it [컨테이너 명] bash
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjU1/MDAxNTg4NDQ2ODg3MjE4.z09SUraRN0pt4pJ9Xhwb4GPJP4Dx28glEZnlUx1_UD0g.oRdDWp5UnEyK-U-D3S76t4LDtxKFr_mp1BoOgZVRCWgg.PNG.oymlmjo/image.png?type=w773)

-  exec 명령어는 컨테이너가 up인 상태에서만 가능하므로, up인 상태가 아닐 때에는 다음과 같은 오류가 나타남![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTAz/MDAxNTg4NDQ3MDMxMzQw.xtlYId6J3qv27iqi2PZ1L-PaFtmRCnKvPsK6Vle_yFAg.SVMGk7aJbXxU1Ta5c4-oTtBR1X2QoAH2Fj33pIXoIRkg.PNG.oymlmjo/image.png?type=w773)



##### MySQL 실행

```shell
# mysql -uroot –p[비밀번호]
```

![Inkedimage (1)_LI](../../../아비/Inkedimage (1)_LI.jpg)



##### MySQL 종료

```shell
exit
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTgz/MDAxNTg4NDQ3NDI1NjI5.hxEYH_PntzX7BXICGa1B-68AWs4F96v-ylFMlU-mBjkg.IQ5CUMTBG-UtcQVWxCM3oHC_tZLoQqUYK3YCmL5BU6kg.PNG.oymlmjo/image.png?type=w773)



### MySQL 활용

##### 현재 존재하는 데이터베이스 확인

```shell
show databases; 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTE2/MDAxNTg4NDQ3Nzk0MDIy.HBQvOzMmjDIOIwO_IMqg5S2SlNiFnNTueR0gCpYKUTUg.CmgkcCNlFocpkymTtOBYfJMWl9HybjEelwZ-0q36ycUg.PNG.oymlmjo/image.png?type=w773)



##### 사용할 데이터베이스 선택 및 테이블 확인

```shell
use [데이터베이스 명]; 
show tables;
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfNzYg/MDAxNTg4NDQ4MDg5NDIy.-H2XqJbFfHc96bJcVatRuyE7jHwk-qV0QZawfK8HNQgg.XdgVmp_r7vC1mHeEs9kMelLwaUfg96VpOVSRpzuE-Isg.PNG.oymlmjo/image.png?type=w773)

- 데이터베이스를 선택하지 않고 테이블을 보면 다음과 같은 오류가 나타남![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjE5/MDAxNTg4NDQ3OTE2OTEy.C5E14Deu7AUkkVsEIUcIzhFNNaJFNf5c_m9AZRU9lvIg.2LzB1KT1S8GAuNedEOaoHLVp9kBFicFTbN4JJOXMV6Eg.PNG.oymlmjo/image.png?type=w773)



##### 테이블 생성

```shell
create table [테이블명] (칼럼명 데이터타입, ··· );
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjcy/MDAxNTg4NDQ4Njk0MzU5.6JakWXMztxLx8-Ch4V44M5k118WYhYrHcqDQCLCvDH8g.t0C5jhkEz6NcbFuP_VjR1iYc5MYQzo-km_OkgH-cDWAg.PNG.oymlmjo/image.png?type=w773)

- `primary key` : 기본키 정의, 하나의 테이블에 하나의 기본키만 가능

- `not null` : null 값의 입력 금지, 무조건 값이 있어야함



##### 테이블 정보 확인

```shell
desc [테이블명] 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjE5/MDAxNTg4NDQ4ODk1ODc0.xIGJzwzejbWheo3GvEzXJqpbejYGUlE0fNyzOcG8Vmkg._NVvbAcFKeMN6cWMwX9lnNMP_-0ofZMcIBmAWA18C2gg.PNG.oymlmjo/image.png?type=w773)



##### 데이터 입력

```shell
insert into [테이블명] (컬럼명, ···) values (입력 값, ···) 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTUg/MDAxNTg4NDQ5Njg2NzYx.C37bZDscsBkqdvipgrUQfKHk7VIRWEd74nMPMsXrQb4g.g8VMDxHom7Xe5ny_TErz3uNds6LsK3MgLddzv9yUNfsg.PNG.oymlmjo/image.png?type=w773)



##### 데이터 조회

```
select (칼럼명, ···), from [테이블명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMTI1/MDAxNTg4NDQ5ODc4NDU1.PKi4gQw8WRcZoDTE9WU9IuAPpw-_B_k2zqfhqysEECEg.EbeyjugLBMbOJ-SI6_75zgrUnzWHJN26y_hcb3g4r7Qg.PNG.oymlmjo/image.png?type=w773)

- 와일드카드(*)를 사용하면 모든 칼럼정보 확인

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMzYg/MDAxNTg4NDQ5ODExNTMx.ahZyO6GSkeaw65c2lahH-zCtJuISUm6ZW40298K1ItEg.3WotqiJrZZFbz8RV6ENDLFgyWPgUx10CW_EucS2hgVwg.PNG.oymlmjo/image.png?type=w773)

-  where 절을 통해 조건에 맞는 데이터만 확인

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfNTcg/MDAxNTg4NDUwMzU3MDM3._vpKonmayyRt9-iN-RZ-ytAH6UboC4Vw7h-T8Yl5igwg.drJmvTK3WFsAGjviqNMnJ91os16ph7OwN4Mq-AWuIckg.PNG.oymlmjo/image.png?type=w773)



##### 데이터 수정

```shell
update [테이블명] set 칼럼명 = 새로운 값; 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfOTgg/MDAxNTg4NDUwMDQyNTcz.PEBvrKMLIn3upltRXhA_VIYY2f5d6_fWkG-m1V0otiYg.N2GDXKQKwXYhFv3n1VKYyoBD5BgYVAaWI91ESkVr4Sog.PNG.oymlmjo/image.png?type=w773)



##### 데이터 삭제

```shell
delete from [테이블명]; 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjMg/MDAxNTg4NDUwMTgzMTEy.rtshkIKlqojRe23X2ZbsKDgkS7AiOqGmQB3kqZpvGNQg.Sj2BoBYV8re2stq1ZquSuO0vPmeNIgXweFd6vlTfaSQg.PNG.oymlmjo/image.png?type=w773)



##### 테이블 삭제

```shell
drop table [테이블명]; 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDNfMjU4/MDAxNTg4NDUwNjUwODYx.jwhioberknnrE1RFky9xl2dj6PMRFZQsVEDVUwZaNVYg.GFgBsQnmYxuMQWWzeOaQG4cCgTRJmIygEqtE4ivblLkg.PNG.oymlmjo/image.png?type=w773)
# nginx 설치 및 php 연동

> Debian buster 활용



### Debian 내 nginx 설치

##### container 생성

```shell
$ docker run -it --name [컨테이너 명] p 80:80 debian:buster
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTUg/MDAxNTg5ODE0ODM5Njkx.mPq3zcJw2jcrhoOq1pHFJQ2dsasslbALyACqv8wbBLIg.n9_FSP3bodkTcDrtdvvbjMjV7tD0a0eV2g6rZavz9yAg.PNG.oymlmjo/image.png?type=w773)



##### container 생성 확인

```shell
$ docker ps -a
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTMz/MDAxNTg5ODE1MDc5NjE0.OtlOHKo8eqXDQnAwwLCEFnOtBgkdcZzH9eZvzDETYfEg.EBMSW-5gDbU8SP19b1ITK9Qh0o77I4gEzpfvSjyuzWsg.PNG.oymlmjo/image.png?type=w773)



##### 기본 패키지 설치

```shell
apt update
apt upgrade
apt install vim
apt-get install nano
apt-get install net-tools
apt install sudo
```



##### nginx 설치

```shell
apt-get install nginx
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTA0/MDAxNTg5ODE1NTAzNjcx.9JSwzNEjOfbZn0WAWWjxvmCf3KzZ0wVBdw31TDDDXgcg.vBoyDYx_k9ZO9ELTU7YP-7vpGAIsF9IaAJ05oo-w1jMg.PNG.oymlmjo/image.png?type=w773)



##### nginx 서비스 실행

```shell
service nginx start 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTg1/MDAxNTg5ODE1Njk3MjE3.TiRzpx2egx8iZJY2kOysUubEIaentGvrC0gaQDxD8hEg.tSaBlsHvm2cwVFiRBsU6ZAnfwXNZl6nlTW1c9QK84PQg.PNG.oymlmjo/image.png?type=w773)



##### nginx 작동 확인

```shell
service nginx status
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMjA3/MDAxNTg5ODE1NzAzOTMz.3n8WCjhpiodyyGp4X4TlpDRIvk-hUKshE0nJF-BvAe4g.zVMCld5UgXR-gUuBIXsWNB0it8izpumIOhWNX3sKT2Ug.PNG.oymlmjo/image.png?type=w773)



### PHP 설치

##### php 설치

```shell
$ apt-get install php7.3 php-mysql php-fpm php-cli php-mbstring php-curl php-gd
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMSAg/MDAxNTg5ODE2MDgxMDE2.a7ZRbqVDX5n0gp1Fy4DzZl3Hsz9rfeSkm5uMwpBbspcg.hOvEvkIGU6X307xMc0pQ6kT07vljmK3tFtvM0c5gKSgg.PNG.oymlmjo/image.png?type=w773)



### nginx 연동

##### nginx 환경설정 파일 수정

1. /etc/nginx/sites-available로 이동

```shell
cd /etc/nginx/sites-available
```

2. default 파일 존재 여부 확인

```shell
ls -l
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfODgg/MDAxNTg5ODE2NTQwODI1.Y8PXjPWAqKMm_c9dHHbdtzKatITfeI40j6-hA5FRtXAg.ISM-3wSqQuXw91-0kT_MBJnRI0wn7SQeAQaDNOKXf6gg.PNG.oymlmjo/image.png?type=w773)

3. default 파일 수정

```shell
nano default 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfNzgg/MDAxNTg5ODE3MjE1NjQ1.uD2uQVgFHOQ2wbV3mdTi5KKA7t3wdh_C7ZkXBGAgkQ4g.kPyQKRY9xW8URngSI_Me1hgVtZnmEXLXFPtJZfR3yQsg.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMjcw/MDAxNTg5ODE2NzE5MTk4.u-SR_8Y0rZwlpbeANf0oA_nrvnh9lBFiEKAimvKyTuog.h2CT9w4iYPb8lJuGh_RKYvQ7knYYenmdhrHYhwwi20kg.PNG.oymlmjo/image.png?type=w773)

##### 

##### php 파일 수정

1. /etc/php/7.3/fpm으로 이동

```shell
cd /etc/php/7.3/fpm
```

2. php.ini 수정

```shell
nano php.ini 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfOTAg/MDAxNTg5ODE3MTEwMjAw.Hmkp1JPLhtS32EnPXWA_NhTF9RzxMFTEWsEpSW6UCrsg.pYjfiThenTagOi43CscmEfUm7MvRgMOOvXKum5iZ50og.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTIw/MDAxNTg5ODE3MTE4NTU3.w1GQYrVgW-zE4D_yOaKLau7z5mDLuQ-9ZKxRka19kf8g.OHV3VPLEzrZx6yc5bwt7E1MA3F7tHzOSqwETWhobHfcg.PNG.oymlmjo/image.png?type=w773)

3.  /etc/php/7.3/cli로 이동

```shell
cd /etc/php/7.3/cli
```

4. php.ini 수정

```shell
nano php.ini 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMjE4/MDAxNTg5ODE3MzM5OTA2.4WhkXQHzhADwkdYfG9cYKy-JW1CXg_6Wn7C2biO9arAg.2X9bEm7A9_AuYJYWCTBofWs5NTia_sAjD6Hgxq2pgcQg.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMjM5/MDAxNTg5ODE3MzQ2MDkz.SKv-lv1-OBG0x68VEl5S_6sYgHYFXMtheGK4gNYZ0Bsg.sYTcusnLU4djCNNqP-b9AAmMnCHCeoz6hs7-mFLQS9og.PNG.oymlmjo/image.png?type=w773)



### nginx 연동 확인

##### nginx 재시작

```shell
service nginx restart
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTQ5/MDAxNTg5ODE3NDYwMDU3.qKid7yCEkqA1r_z1hQ339A4anweso4f8zr3FBtVYFfgg.xsnmcdVgF7kChlLr3OEPAkIMZUqnz8H8fiNB0GmKzIkg.PNG.oymlmjo/image.png?type=w773)

##### php 시작

```shell
$ service php7.3-fpm start
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfNDQg/MDAxNTg5ODE3NTkwNDAw.wbitcD7bOe3r1TWVuuzjI6n5MStiBogrLwSpbIqx_24g.u-_Ez_4xN6g9uUWErqfl8BCYs8OVpTcLJ9UiTdoE-oIg.PNG.oymlmjo/image.png?type=w773)

##### run 폴더 확인

```shell
cd run
ls
cd php
ls
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfNzAg/MDAxNTg5ODE3NTk5NDY3.9cG91VrOsrLsxBdtuVx9ExyG6PuLEhfp8SYu_hK4_Lcg.SMjulbPy3NMXxfEAcpbjjWKGMc4cFyCn-8fVhNbuCSgg.PNG.oymlmjo/image.png?type=w773)

##### php 재시작

```shell
$ service php7.3-fpm restart
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMjMg/MDAxNTg5ODE3NzMzMDEy.Wh1jVKccLu29CmPAnOxBpcXFX5cQ66CT1lduHGCpFocg.51iZ-mg6LhCUET2UJKrQIGmykdratxtTVQX56ohjgKUg.PNG.oymlmjo/image.png?type=w773)



### 파일 생성

1. /var/www/html 이동

```shell
cd /var/www/html
```

2. test.php 생성

```shell
nano test.php
```

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTQy/MDAxNTg5ODE3ODA2MTU2.wtK7K-zQAJPEslFfVL4sJ-k2rpbmMlCjCCmr6TZU4aQg.LybpXKXAwOgVJpEs6K_KfCi7D7DfPuPL21RurDU3F4cg.PNG.oymlmjo/image.png?type=w773)

3. 아무 내용이나 입력

   - echo는 문자열 출력을 위해 사용

   ![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMyAg/MDAxNTg5ODE3OTIyMjk0.NUj3yx_hSBa4vtUglKRLtdQV7PpvLVldx01UmnXZE6Ag.SdSW0g43O85yzlhntlvgxVhdYPbD0duGAjZzTFoN1T0g.PNG.oymlmjo/image.png?type=w773)



### 웹 브라우저 확인

![img](https://postfiles.pstatic.net/MjAyMDA1MTlfMTM3/MDAxNTg5ODE3OTgxMTE3.Y0T2ff79nRI76_UeTkX5yETXO9UDdd4ju6WPiRmzreAg.08tQi9uMYU47U6PNFg2JQlRfPcxbYxUMhi6ao3yAGTQg.PNG.oymlmjo/image.png?type=w773)
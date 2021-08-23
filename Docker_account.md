# 사용자 계정 생성 및 디렉토리 생성

> Ubuntu 활용



### 패키지 설치

- 시작 전 Ubuntu의 STATUS가 **Up**인지 확인하고 attach 명령어를 통해 접속

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMjM2/MDAxNTg4NTI1MTcwMjQ5.XeJAAfDe3EHmznwJzEZw4dfYDxLOi9xLnB97GOyxxH4g.M3h-sjk3ZWPYCPaAhGGoBpXoUF0UgZJRwTWWaZER82og.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfODAg/MDAxNTg4NTI1MzQzNzEy.bCErAL--7QH3hww075yIECJAG3rX0B9diFzjhwIdF5Eg.SF4CTSBOsRXXb3RFhIrAJk-mGr-WzwRVx857OC4WW4kg.PNG.oymlmjo/image.png?type=w773)



##### Ubuntu 업그레이드

```shell
apt update && apt upgrade 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMjIz/MDAxNTg4NTI1NDQ4NzM0.s_Qkpm0H18No4wWTo9ZJXPxsrQv_azHK78DTy1fQuYUg.aAbFustCw0UqEvIQKwIiALmjyoNk8dx1iSEKQNXYSu8g.PNG.oymlmjo/image.png?type=w773)



##### vi 에디터 설치

```shell
apt intall vim
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMTk4/MDAxNTg4NTI1NTgyNjUw.2-KciM_yrAsEyy-VKgdR3TyURZS3DBnLSYqWq-TN904g.p6sqGoBfLGdUdyu2BdM7fw8TJ_6bmp4UgtSiRsXGArMg.PNG.oymlmjo/image.png?type=w773)



##### 통신 패키지 설치

```shell
apt install net-tools 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMjY5/MDAxNTg4NTI1NzkyNTg2.VeJxWJ2X57pGoexT57MT96mZ96ookCvVVnsLMsMAhaYg.NcaA7QAW8hWTK-dQx1NXEQ3H5MkV4XUZrcCMLHQt11wg.PNG.oymlmjo/image.png?type=w773)



##### sudo 명령어 설치

```shell
apt install sudo
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMTE4/MDAxNTg4NTI1ODYyNDUz.rmijN8aiZ3r0UZXpLr-kadkjgEe3Khpo_FwS70LoaHEg.-IELIxBNkt6D4xVChdqpVfHjrLSR6tqK9e3NBXm4lzcg.PNG.oymlmjo/image.png?type=w773)



### 사용자 계정 생성 및 관리

##### 사용자 계정 생성

```shell
adduser [사용자 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMjk2/MDAxNTg4NTMxODk2Mjk4.OhfbCWZ2anYB_TVQZdWqJVvcvHOJgblkPjxPSPPkRe0g.4GDBm597XWefFcoI31hnOf6LgP8ByxudsFs4irz2Zsog.PNG.oymlmjo/SE-c4563ad4-3e9e-4504-80d7-9a5668688f08.png?type=w773)



##### 사용자 변경

```shell
su [사용자 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMTAz/MDAxNTg4NTI2MzM0NTI5.fD4fyLDN85X41rS-SqvyFyiMRqTRAp9Mx4--8f31TQgg.KHGArTt_8kH7G5yiNBn03LrXKlq1jXgWolyuEXqD5igg.PNG.oymlmjo/image.png?type=w773)



##### 사용자 권한 부여

- 사용자가 root로 되어있어야함

```shell
usermod -aG sudo [사용자 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMjc3/MDAxNTg4NTI2NzIzMjU2.CWS3TlGG6jScCwFXd0hZF--c8PcI3AEEHhSdZ8v7guYg.BJ-mn7rkzxeybPE8jiOynyvkYQThMMSl5iddEbmjlB8g.PNG.oymlmjo/image.png?type=w773)



### 디렉토리 생성 및 파일 생성

##### 디렉토리 생성

```shell
mkdir [디렉토리 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDZfMjc1/MDAxNTg4NzUxMDY5NDEx.cQkZPKdoLf_fDKzJQ9Dj1TrmlpbRWi4Bzs2YxsGriowg.oLwEFluuPj3ZN8PX-J14flMdBRQQlyoSZE_e2AYoFC8g.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MDZfMjY1/MDAxNTg4NzUxMjA4ODU0.ZAoFbUQPuZ9Zt-d6ti0TVRWh1qzzemBoyIx1u-CJAp8g.TuY4F1YqcJVr6mdbYbTjR5I1sLkvkZIy1jFdC16pfBMg.PNG.oymlmjo/image.png?type=w773)

##### 디렉토리 생성 확인

```shell
ls -l 
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDZfMTQz/MDAxNTg4NzUxMjMwOTU3.pW1kPMhHMclOyq8ZUwJVGWYhw23Y7swqIhTqKjS7eEUg.owRpXN4SVNR0ZVArFiONluIZZBMXTGA92-ovDHipVr8g.PNG.oymlmjo/image.png?type=w773)



##### 디렉토리 위치 이동

```shell
cd [디렉토리 명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDRfMzMg/MDAxNTg4NTMyNjUxNDY4.ATAXF96-x5EHrL3j2KM2mUFLz5m9xiJZpk5XSwLKSQ0g.qRQM-NMvCI01iVjEMaTdBeaYYDLT3Wl1pNCJDakuOMkg.PNG.oymlmjo/image.png?type=w773)

- `cd ../`: 상위 디렉토리 이동



##### 파일 생성

```shell
touch [파일명]
```

![img](https://postfiles.pstatic.net/MjAyMDA1MDZfNzIg/MDAxNTg4NzUxNDIxNDE0.z82pPkgJpwygRZxp6LkffDQHKEuylJQJroda6Cyq8XUg.O6GfLqb9l7WR9jXh8IZshYEqoT6Pn6SztFKBhGo-Uocg.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA1MDZfNCAg/MDAxNTg4NzUxNDM4OTg1.nVKF0FEk5pcS1U7jQcjkd2JJFbWJl0TxrUIjPMGAlRMg.gCs3LcXISy-qCJV7At0dcMGF2jktip_gcL5ZePLupbUg.PNG.oymlmjo/image.png?type=w773)
# Docker Hub

> Docker Hub 활용하기



### 계정 생성하기

https://hub.docker.com/

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMTcg/MDAxNTkxNTA0Mjg3MjMw.ljtO3TQOpyLUfmo4WkmYcHiZbBmUl1MDr_RKNssmKy4g.Yr_iGDJktOxB5i35qP8nuzdijj0gmpYd7bzh3dawF9Ug.PNG.oymlmjo/image.png?type=w773)



### 이미지 올리기

##### 로그인

- 처음 접속할때는 계정명과 비밀번호 순서대로 입력

```shell
$ docker login
```

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfNzUg/MDAxNTkxNTA0NDk0NDUx.Z6TGwaEbzT3bSrUhzfOzSEXe7zhUWvlses68VWyBvbAg.NG8E3iPY23ToAtU9m1ZUVfZx86aH_phNnobxu5GZ1log.PNG.oymlmjo/image.png?type=w773)



##### 이미지 올리기

```shell
$ docker push [계정명]/mydocker 
```

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMjU1/MDAxNTkxNTIwNTA4ODA3.RBn9HRxZIFbXd4Vs_RvUQlTsLOFqrlaqyq9oZ_HTMCEg.ZzmEyqM5RzESTj_bjJsivpIoJff_CX0dPkVp98Y-IPAg.PNG.oymlmjo/image.png?type=w773)



##### 이미지 확인

- Docker Hub 사이트 상단에 Repositories

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMTAz/MDAxNTkxNTA0NjY0MDM5.oU95Oa0hEBsSk1DiFk7s90Bwj0A7oM9ZRh_ePMS6jvUg.G46lc2ioJXorSnM4uQqnJhk69LyOPQaOM4chSYVV7KIg.PNG.oymlmjo/image.png?type=w773)

![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMjc1/MDAxNTkxNTA0NzI3ODU2.yIQ3Li0tuv9o-7Aswz_2fDg_SrMnRfCLhS1NnVgcSTEg.d1G4MWn7vrcdoHFCPvFi69OHjPny_slXgsXaEM69mXEg.PNG.oymlmjo/image.png?type=w773)

- 위 과정을 똑같이 따라했는데 올라온 것이 없을 경우

  - Create Repository 클릭
  - 가입했을 때 사용한 이메일 확인

  ![img](https://postfiles.pstatic.net/MjAyMDA2MDdfMTY5/MDAxNTkxNTA0ODU4OTk5.1bzxYMrsf5NF4TWYfx2UUsGVnk7lffnim77g7SnG_6Yg.3T6aD0xUvgdF5cod8IVbc6qLUD9aSgfK4ffWEWr6Jj4g.PNG.oymlmjo/image.png?type=w773)

  - Verify email address 클릭
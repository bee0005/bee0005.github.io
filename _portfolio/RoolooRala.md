---
title: "RooLoo RaLa"
excerpt: "스마트 화장실을 위한 시스템입니다. 아두이노, 임베디드보드(E-cube4412), 안드로이드를 사용하였습니다."
header:
  image: null
  teaser: /portfolios/rooloo/2.png
sidebar:
  - title: "Role"
    image: /portfolios/rooloo/1.jpg
    image_alt: "logo"
    text: "Android, 통신"
  - title: "Member"
    text: "4명"
  - title: "Term"
    text: "2016.04~ / 2달"
pegallery:
  - url: /portfolios/rooloo/5.jpg
    image_path: /portfolios/rooloo/5.jpg
    alt: "사진1"
  - url: /portfolios/rooloo/6.jpg
    image_path: /portfolios/rooloo/6.jpg
    alt: "사진1"
phgallery:
  - url: /portfolios/rooloo/9.jpg
    image_path: /portfolios/rooloo/9.jpg
    alt: "사진1"
  - url: /portfolios/rooloo/10.jpg
    image_path: /portfolios/rooloo/10.jpg
    alt: "사진1"
  - url: /portfolios/rooloo/11.jpg
    image_path: /portfolios/rooloo/11.jpg
    alt: "사진1"
  - url: /portfolios/rooloo/12.jpg
    image_path: /portfolios/rooloo/12.jpg
    alt: "사진1"
phgallery2:
  - url: /portfolios/rooloo/zz.png
    image_path: /portfolios/rooloo/zz.png
augallery:
  - url: /portfolios/rooloo/155.jpg
    image_path: /portfolios/rooloo/155.jpg
augallery2:
  - url: /portfolios/rooloo/14.jpg
    image_path: /portfolios/rooloo/14.jpg
augallery3:
  - url: /portfolios/rooloo/poster.jpg
    image_path: /portfolios/rooloo/poster.jpg
---

## About Project

2016년 1학기 시스템프로그래밍 수업을 수강하였다. 수업에서 `임베디드보드(E-cube4412)`를 이용한 프로젝트를 진행하였다.

우리 팀은 `아두이노, 임베디드보드, 안드로이드`를 이용해 깨끗한 화장실을 관리 할 수 있는 시스템을 기획하였다.

프로젝트의 이름은 *ROOLOO RALA*로 깨끗한 화장실을 사용할 때의 즐거운 기분을 표현하는 이름이였다.

총 4명이 팀원이 되어 프로젝트를 진행하였다.

내 역할은 안드로이드 구현과 임베디드, 안드로이드 간의 통신, Touch Panel을 구현하였다.

4학점 수업의 프로젝트 였지만, 정말 많은 시간을 투자하여 프로젝트를 완성하였다.

특히 팀원에 Simon이라는 외국인 친구를 만났다. 의사소통과 문화차이로 프로젝트 중에 큰 갈등이 있었지만, 잘 해결하였다.

4명이서 서로 의사소통 하면서 많은 시간을 투자해 진행한 프로젝트로 많은 경험을 하였다.

{% include gallery id="pegallery" caption="4학점이지만 정말 많은 모임과 밤샘을 했던 프로젝트" %}

## 세부 기능

**임베디드 보드(E-cube4412)**는 화장실 입구에 설치되는 가정을 하고 구현을 하였다.

{% include gallery id="augallery"  caption="프로젝트 시연을 미니 화장실을 만들어 발표하였다."%}

보드의 *7-Segment, Dot Matrix, LED* 를 이용해 화장실 내부의 온,습도와 메탄 값을 보여 주었고,

화장실 내부의 대부분의 악취는 메탄가스가 원인이기 때문에 메탄 값을 측정하여 화장실 내부의 악취의 정도를 확인하였다.

*Tlcd, Oled*를 이용해 화장실 관리자의 사진과 전화번호를 보여주었다.

또한, *Touch Panel*를 이용하여 사용자가 관리자에게 위급상황이나 다른 요구 사항들은 터치를 이용해 관리자에게 알림을 가게 하였다.

관리자의 휴대폰(안드로이드)는 APP을 이용해 알림을 받을 수 있다. 

이때 `Help` 버튼을 누르면 *Buzzer*도 함께 울린다. *Color Led*를 이용해 화장실의 상태( 초록 - 깨끗함, 빨강 - 더러움, 노랑- 청소중)을 표현하였다.


{% include gallery id="augallery2"  caption="프로젝트 시연을 미니 화장실을 만들어 발표하였다."%}

**아두이노 센서**로는 *온,습도 센서 / 가스 센서 / 버튼 센서 / 모터 / 물체 감지 센서* 를 사용하였다.

*온, 습도, 가스 센서*를 이용하여 화장실 내부의 상태를 측정하였다.

화장실 칸이 더러울 땐 칸에 있는 *버튼 센서* 를 눌러 관리자 핸드폰에 알람으로 주었다 .

*물체 감지 센서와 모터 센서*를 이용하여 대변기가 자동으로 물이 내려갈 수 있도록 구현하였다.

이때, 사소한 거리 감지에 대한 오차를 줄이기 위해 7초 이상 물체가 감지되고 물체가 사라지면 4초 후에 모터가 작동하게 구현하였다.

{% include gallery id="phgallery2" caption="[안드로이드] 화장실 내부 상태, 알람, 관리자 비밀번호 설정 화면이다" %}


마지막으로 **안드로이드**를 이용해 화장실 내부의 상태 정보(온도, 습도, 메탄 수치)를 확인 할수 있다.

그리고 화장실의 사용자가 버튼 또는 임베디드 보드 터치 패널을 눌렀을때, 알람이 온다. 알람들의 기록을 확인 할수 있다.

마지막으로 화장실 관리자의 비밀번호를 설정하여, 임베디드 보드의 *KeyPad*를 이용해 관리자 로그인을 할 수 있다.


{% include gallery id="augallery3"  caption="Project Poster"%}

## Demo
데모 비디오

## 개발 환경
- Linux
- C
- Android
- Arduino



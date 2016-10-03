---
title: "[OpenStack] OpenStack"
excerpt: "[7월 18일] OpenStack 개념 정리 "
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - OpenStack
  - Study


---
# OpenStack

`OpenStack`은 `클라우드 컴퓨팅`환경을 만드는 **오픈소스 플랫폼** 이다.

### *OpenStack History*
`락스페이스사(Rackspace)`는 클라우드 스토리지를 오픈소스화 하였고, `미 항공 우주국(NASA)`는 서버 가상화 플랫폼을 오픈 소스화 하였다.

그후 2010년 6월 `Rackspace`와 `NASA`가 `OpenStack`을 설립하고 첫번째 버전인 **Austin** 을 릴리즈 하였다.

`OpenStack`은 2010년에 시작하여 얼마 안된 오픈소스 프로젝트이다. 6개월마다 새로운 버전이 릴리즈 되고 있다.
[OpenStack Release](http://releases.openstack.org/)

처음 `OpenStack`은 **컴퓨트, 이미지, 오브젝트 스토리지** 라는 3가지의 기본 서비스로 시작하여, 매번 릴리즈마다 부가 서비스가 구축되었다.


### *OpenStack Architecture*
`OpenStack`은 **컴퓨트, 이미지, 오브젝트 스토리지, 인증 서비스** 등이 유기적으로 연결되어 하나의 커다란 클라우드 컴퓨팅을 구축하였다.

처음에는 인스턴스를 생성하고 삭제하는 *Compute Service*, 이때 필요한 OS Image를 관리하는 *Image Service*, 이미지를 백업하기 위한 *Object Storage* 서비스 뿐이였다.

그후, 컴퓨트 서비스는 *Nova*, 이미지 관리 서비스는 *Glance*, 오브젝트 스토리지는 *Swift* 라는 이름이 붙었다.

또한, *Nova, Glance, Swift* 서비스의 인증을 관리하기 위한 *Keystone*, 서비스들을 쉽게 이용할 수 있는 DashBoard를 제공해주는 *Horizon* 이 추가 되었다.

> 네트워크 서비스 *Quantum*, 블록 스토리지 서비스 *Cinder*, 오케스트레이션 서비스 *Heat*, 모니터링 & 미터링 서비스 *Ceilometer*, 데이터베이스 서비스 *Trove* 등 도 새롭게 추가 되었다.

## 출처
[장현정] 저자의 `오플스택을 다루는 기술` 을 읽으면서 공부한 내용을 혼자 요약하고 정리하였다.

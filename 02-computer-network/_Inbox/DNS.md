## 개요

- 도메인 이름 -> IP 주소로 변환하는 시스템

## 제공 기능

- host aliasing

- load distribution
	- 하나의 이름에 꼭 하나의 IP 만 대응시킬 필요는 없음
	- 요청이 많으면 서로 다른 IP 로 요청을 분산시키기도 함

## 형식

```
www.hongik.ac.kr.
```

- fully qualified domain name

```
www
```

- partially qualified domain name

## 계층 구조

- Root DNS Servers - Root
	- .com DNS Servers - TLD (Top Level Domain)
		- ...
	- .org DNS Servers
		- ...
	- .edu DNS Servers
		- ...

- Root DNS Server 가 모든 걸 다 알고 있지는 않다
	- 하위 DNS Server 들에게 요청에 대한 답변 권한을 이양한다
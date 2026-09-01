
중앙 서버를 거치지 않고 네트워크에 참여하는 개별 컴퓨터(peer)들이 직접 데이터를 주고 받는 방식

## Features

- 탈중앙화
- 동등한 지위
- 확장성

## Problems

- Rare chunk
	- 희귀한 청크 문제
	- `rarest-first`
		- 가장 희귀한 청크들을 우선적으로 다운로드

- Free rider
	- 무임 승차 문제
	- `tit-for-tat`
		- 참여도가 높은 peer 에게 우선적으로 되돌려 줌

- High churn
	- `churn` : 접속을 해제하는 것
	- 접속 해제가 잦은 네트워크에서는 데이터 가용성이 떨어진다

## keywords

- frame
- MPEG
- coding

## Coding

- CBR
- VBR

## Continuous playout constraint - 지속적 재생 제약

사용자가 영상을 시청할 때 영상이 중간에 끊기지 않고 매끄럽게 재생되어야 한다는 조건

- `jitter`
- 네트워크 가변성
- 시작 지연

#### 해결 전략
- `Buffering`

## DASH - Dynamic, Adaptive Streaming over HTTP

HTTP 를 이용해 동적으로 화질을 조절하여 스트리밍하는 기술
클라이언트가 자신의 인터넷 속도 및 환경에 따라 요청 화질을 결정한다

- `manifest file`
-  

## 초기화 및 속성

- 데이터로부터 생성: `torch.tensor(data)`를 통해 직접 생성 가능
- NumPy 호환: `torch.from_numpy(np_array)`를 통해 변환 가능
- 주요 속성: `shape`(모양), `dtype`(데이터 타입), `device`(저장 장치) 등을 확인해야 함
- GPU 이동:`if torch.cuda.is_available(): tensor = tensor.to('cuda')`를 통해 GPU로 이동

## 주요 연산

- 슬라이싱
- 행렬 곱
- 요소별 곱

## 데이터 처리

- `Dataset`
- `Custom Dataset`
- `DataLoader`

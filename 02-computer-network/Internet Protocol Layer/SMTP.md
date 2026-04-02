## 개요

- 이메일을 **서버 간 전송**할 때 사용하는 프로토콜

- **Application Layer** 프로토콜

- **텍스트 기반(text-based)** 통신

- **line-based** 프로토콜

---

## 동작 방식

### 기본 흐름

```

클라이언트 → SMTP → 메일 서버 → SMTP → 수신 서버

```

### 명령-응답 구조

```

HELO mail.example.com

MAIL FROM:<me@example.com>

RCPT TO:<you@example.com>

DATA

Hello

.

QUIT

```

- 클라이언트가 명령어 전송
- 서버가 상태 코드 + 메시지로 응답
- `CRLF.CRLF` 를 수신하면 통신 종료

---

## ASCII와의 관계

### ASCII란?

- 문자를 숫자로 표현하는 인코딩 방식

- 예:

  - A → 65

  - a → 97

### SMTP와 ASCII

- SMTP는 **ASCII 기반 프로토콜**

- 모든 데이터는 **문자열 형태로 전송**


---

## ASCII 기반의 특징

### 1) 명령어가 텍스트

```

HELO, MAIL FROM, DATA ...

```

### 2) 이메일 내용도 텍스트

```

Subject: Hello

Body: Hi

```

---

## 문제점: 바이너리 전송 불가

- ASCII는 7bit 기반 → 표현 제한

- 이미지, 파일 등 ****바이너리 데이터 직접 전송 불가****


---

## 해결: MIME

### MIME (Multipurpose Internet Mail Extensions)

- 바이너리 데이터를 ASCII로 변환해서 전송

### 방식

```

Binary Data → Base64 인코딩 → ASCII → SMTP 전송

```


---

## 전체 흐름


```

파일/이미지

   ↓

Base64 인코딩

   ↓

ASCII 문자열

   ↓

SMTP 전송

```


---

## 핵심 정리

- SMTP = 이메일 전송 프로토콜

- **텍스트 기반 (ASCII)**

- **명령-응답 구조**

- 바이너리는 **MIME + Base64로 처리**
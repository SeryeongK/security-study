---
name: commit
description: security-study 저장소에서 커밋 메시지를 쓰거나 커밋할 때 사용. 타입·분야·요약 형식과 공개 전 점검 규칙을 따른다.
---

# 커밋 규칙

## 형식

```
<type>(<area>): <summary>

<body - 선택>
```

- **summary:** 영어, 명령형 현재형(Add, Fix, Update), 첫 글자 대문자, 끝에 마침표 없음, 50자 이내
- **body:** 선택. 한국어 가능. 무엇을 왜 바꿨는지. 한 줄 72자 이내
- 한 커밋에는 한 문제(또는 한 가지 변경)만

## type

| type | 언제 |
| --- | --- |
| `writeup` | 새 풀이 추가 |
| `exploit` | 공격 스크립트 추가·수정 |
| `defense` | 방어 코드 추가·수정 |
| `lab` | `labs/` 실습 환경 추가·수정 |
| `docs` | README, 템플릿, 개념 정리 |
| `fix` | 오타, 깨진 링크, 잘못된 설명 수정 |
| `chore` | 설정, `.gitignore`, 폴더 구조 |

## area

폴더 이름 그대로: `web`, `crypto`, `network`, `ics`, `ai`, `hardware`, `mobile`, `labs`. 저장소 전체면 생략.

## 예시

```
writeup(web): Add dreamhack cookie
exploit(web): Add session hijack script for dreamhack session
defense(web): Add Laravel signed cookie example
lab(network): Add MQTT broker docker compose
docs: Add writeup template
fix(crypto): Fix HMAC explanation in replay-attack writeup
chore: Ignore pcap files
```

## 커밋 전 점검 (매번)

1. `git diff --cached`에 **플래그 값**이 없는지 확인 (`flag{`, `DH{` 등 검색)
2. `.env`, 키, 토큰, 비밀번호가 없는지 확인
3. 문제 소스 전체를 복사하지 않았는지 확인 (취약한 부분만 인용)
4. 진행 중인 CTF 문제가 아닌지 확인
5. 새 풀이면 README의 "풀이 목록" 표에 한 줄 추가했는지 확인
6. 커밋 메시지에 `Co-Authored-By` 등 AI 표기 트레일러를 넣지 않음

하나라도 걸리면 커밋하지 말고 사용자에게 알린다.

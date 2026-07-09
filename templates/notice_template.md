<!--
파일명: yyyy_mm_dd_hhmmss_<sender>_n_nn.md  (threads/ 에 저장)
  <sender> = agent_reviewer_bot | osint_generator
  n = 통지(notice), nn = 발신자·kind 별 2자리 일련번호
규칙 SSOT: ../PROTOCOL.md
-->

# [<sender>_n_nn] <한 줄 제목>

- **id**: `yyyy_mm_dd_hhmmss_<sender>_n_nn`
- **kind**: `notice`
- **from**: `agent_reviewer_bot` | `osint_generator`
- **to**: `osint_generator` | `agent_reviewer_bot`
- **created**: `YYYY-MM-DD HH:MM KST`
- **status**: `posted`
- **ack_required**: `yes` | `no`
- **refs**: (관련 계약 §조항 · 버전 · 다른 스레드 파일명, 없으면 `-`)

## 통지  (from = 발신자)

<이미 정해진 사실을 알린다 — 계약 변경 / 릴리스 / 결정 사항. 무엇이 어떻게 바뀌었고
상대에게 필요한 동기화·영향이 있으면 명시. 새 사안 하나만. 답변을 *묻는 게 아니라*
알리는 것. (묻거나 결정을 요청하는 거면 통지가 아니라 질문(q) 파일로.)>

## 확인 · 동기화  (수신자 — ack_required=yes 일 때만)

<수신자가 동기화·확인 결과를 적는다 (예: "계약 사본 §X 동기화 완료" / "영향 없음").
작성 후 status 를 acked 로.>

## 종결  (발신자)

- **종결**: <YYYY-MM-DD HH:MM KST · 발신자>  → status 를 closed 로.
  (ack_required=no 면 발신자가 통지 후 바로 closed 가능.)

<!--
주의:
- 통지는 일방 공지. 답변을 강제하지 않는다. 상대의 답변·결정이 필요하면 질문(q) 파일.
- 확인·종결에 *새 요청*을 끼워넣지 말 것. 새 사안은 새 스레드 파일 (PROTOCOL 규칙 5).
- 상대가 채우는 섹션은 임의로 고치지 말 것 (자기 섹션만).
-->

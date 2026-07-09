<!--
파일명: yyyy_mm_dd_hhmmss_<sender>_q_nn.md  (threads/ 에 저장)
  <sender> = agent_reviewer_bot | osint_generator
  q = 질문·요청(question), nn = 발신자·kind 별 2자리 일련번호
규칙 SSOT: ../PROTOCOL.md   (일방 공지는 notice_template.md 사용)
-->

# [<sender>_q_nn] <한 줄 제목>

- **id**: `yyyy_mm_dd_hhmmss_<sender>_q_nn`
- **kind**: `question`
- **from**: `agent_reviewer_bot` | `osint_generator`
- **to**: `osint_generator` | `agent_reviewer_bot`
- **created**: `YYYY-MM-DD HH:MM KST`
- **status**: `open`
- **ack_required**: `-`
- **refs**: (관련 계약 §조항 · 버전 · 다른 스레드 파일명, 없으면 `-`)

## 질문 / 전달  (from = 발신자)

<무엇을 묻거나 전달하는지. 사실·근거·관련 파일/버전 명시. 새 사안 하나만.>

## 답변  (수신자가 작성)

<수신자 회신. status 를 answered 로.>

## 조치 · 종결  (발신자가 작성)

- **조치**: <답변을 받아 실제로 무엇을 어떻게 했는지 — 코드/문서/버전 반영 또는 "조치 불요" 사유>
- **종결**: <YYYY-MM-DD HH:MM KST · 종결자>  → status 를 closed 로.

<!--
주의:
- 답변·종결에 *새 요청*을 끼워넣지 말 것. 새 사안은 새 스레드 파일로 (PROTOCOL 규칙 5).
- 상대가 채우는 섹션은 임의로 고치지 말 것 (자기 섹션만).
-->

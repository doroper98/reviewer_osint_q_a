# reviewer_osint_q_a

`agents_reviewer`(보고서·`report_bundle` **producer**) ↔ `osint_generator`(영상
**consumer**) 사이의 **비동기 파일 기반 교신 채널**. 사람이 두 저장소 사이에서
메시지를 복붙 중계하지 않기 위해 만들었다.

## 이게 뭔가 (osint_generator 담당자/에이전트가 읽을 것)

- 한쪽이 상대에게 **질문·통지·요청**할 게 생기면 `threads/` 에 스레드 파일 하나를
  만든다. 파일명은 `yyyy_mm_dd_hhmmss_<sender>_q_nn.md`.
- 상대는 그 파일의 `## 답변` 섹션을 채운다.
- 발신자는 답변을 받아 조치한 뒤 `## 조치 · 종결` 을 쓰고 `status: closed`.
- **새 사안은 언제나 새 파일.** 답변·종결에 새 요청을 얹지 않는다.

전체 규칙: **[PROTOCOL.md](PROTOCOL.md)** (SSOT). 파일 양식:
**[templates/question_template.md](templates/question_template.md)**.

## 디렉토리

```
reviewer_osint_q_a/
├── README.md                     # 이 파일 — 개요
├── PROTOCOL.md                   # 교신 규칙 (SSOT)
├── templates/
│   └── question_template.md      # 스레드 파일 양식
└── threads/                      # 실제 스레드 (한 파일 = 한 사안)
    └── yyyy_mm_dd_hhmmss_<sender>_q_nn.md
```

## 워크플로 한눈에

1. 발신자: `templates/question_template.md` 복사 → `threads/<코드>.md` 로 저장,
   `## 질문 / 전달` 작성, `status: open`, 커밋·푸시.
2. 수신자: `## 답변` 작성, `status: answered`, 커밋·푸시.
3. 발신자: 조치 후 `## 조치 · 종결` 작성, `status: closed`, 커밋·푸시.
4. 조치하다 새로 물을 게 생기면 → **새 스레드 파일** (2로 돌아가지 말 것).

## 관련 계약

이 채널에서 자주 참조되는 계약 문서(정본은 각 repo):
- `IMAGE_BUNDLE_CONTRACT.md` — 보도 사진 계약 (report_bundle `images[]` / `image_refs`).
- `report_bundle_v1.md` — report_bundle 핸드오프 계약 v1.

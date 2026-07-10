# A4R Zotero Bridge — 배포 저장소

Zotero의 서지·PDF 하이라이트를 옵시디언 문헌노트로 자동 동기화하고, 본문 인용(`[[@citekey#p.42]]`)을 렌더링해 Word(.docx)로 내보내는 연구자용 옵시디언 플러그인입니다.

> 이 저장소는 **배포 전용**입니다 — 소스 코드는 별도 비공개 저장소에서 관리되며, 여기에는 설치에 필요한 릴리스 파일만 올라옵니다.

## 설치 (BRAT)

1. 옵시디언 → 설정 → **커뮤니티 플러그인**에서 **BRAT** 를 검색해 설치·활성화합니다.
2. BRAT 설정 → **Add beta plugin** 을 누르고 아래 주소를 입력합니다.

   ```
   ai4pastor/a4r-zotero-bridge-releases
   ```

3. 설치가 끝나면 설정 → 커뮤니티 플러그인에서 **A4R Zotero Bridge** 를 활성화합니다.
4. 이후 업데이트는 BRAT가 자동으로 확인합니다 (BRAT 설정에서 "Check for updates at startup" 권장).

## 요구사항

| 항목 | 내용 |
|---|---|
| Zotero | 7 이상 실행 중 + 설정 → 고급 → **"이 컴퓨터의 다른 애플리케이션이 Zotero와 통신하도록 허용"(로컬 API)** 켜기 |
| Better BibTeX | Zotero 애드온 ([설치 안내](https://retorque.re/zotero-better-bibtex/installation/)) |
| citekey formula | Better BibTeX 설정 → Citation keys에 `auth.lower + year + veryshorttitle.lower` |
| Pandoc (선택) | Word 내보내기에만 필요 — macOS: `brew install pandoc` |

## 설치 후 첫 확인

플러그인 설정을 열면 **연결 진단** 이 자동 실행됩니다. Zotero 로컬 API · Better BibTeX · **citekey formula** · 문헌노트 폴더 · persona.json 오버레이가 모두 ✅인지 확인한 뒤, 명령 팔레트에서 **"동기화 점검 (변경 없음)"** 으로 dry-run을 먼저 돌려보세요.

분류 어휘를 본인 것으로 바꾸려면 홈페이지 WORD 생성기에서 만든 `persona.json`을 볼트의 `.a4p/` 폴더에 넣으면 플러그인·AI 분류·템플릿이 모두 자동 연동됩니다.

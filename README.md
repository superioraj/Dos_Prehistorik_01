# 고인돌 1 — 웹 버전

1991년 DOS 게임 「고인돌 1」을 브라우저에서 바로 플레이할 수 있도록 [js-dos](https://js-dos.com) (브라우저용 DOSBox)로 감싼 정적 사이트입니다.
외부 CDN 없이 이 폴더만으로 동작합니다.

## GitHub Pages에 올리는 법

1. GitHub에서 새 저장소를 만듭니다 (예: `goindol1`).
2. 이 폴더 안의 파일을 **전부** 저장소 최상위에 올립니다.
   (`index.html`, `goindol1.jsdos`, `js-dos/` 폴더, `.nojekyll`)
   - 웹에서 올릴 때: 저장소 → **Add file → Upload files** → 파일과 `js-dos` 폴더를 끌어다 놓기
   - `.nojekyll`은 숨김 파일이라 끌어다 놓기에서 빠질 수 있지만, 없어도 동작합니다.
3. 저장소 **Settings → Pages** → Source를 **Deploy from a branch**, Branch를 `main` / `/ (root)`로 지정 후 Save.
4. 1~2분 뒤 `https://<아이디>.github.io/<저장소이름>/` 에서 플레이할 수 있습니다.

## 조작법

| 동작 | 키 |
| --- | --- |
| 이동 | W A D X (방향키 대신) |
| 공격 | Tab / Shift |

- 게임 화면을 한 번 클릭해야 키보드 입력이 들어갑니다.
- 왼쪽 사이드바에서 일시정지, 소리, 전체화면, 가상 키보드(모바일)를 쓸 수 있습니다.

## 파일 구성

- `index.html` — 실행 페이지
- `goindol1.jsdos` — 게임 파일 + DOSBox 설정을 묶은 번들 (zip 형식, 안에 `.jsdos/dosbox.conf`)
- `js-dos/` — 에뮬레이터 엔진 (js-dos v7, GPL-2.0)

## 참고

- 원본 패키지의 `save/1.sav`는 윈도우용 DOSBox 전용 상태 저장 파일이라 웹 버전에서는 쓸 수 없어 제외했습니다.
- 로컬에서 `index.html`을 더블클릭하면 브라우저 보안 정책 때문에 실행되지 않습니다. 로컬 테스트는 `python -m http.server`처럼 간단한 웹 서버로 여세요.

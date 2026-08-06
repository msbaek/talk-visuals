# talk-visuals

발표·글에서 쓰는 시각물(GIF·이미지·설명 페이지)을 로그인 없이 누구나 볼 수 있는 URL로 공유하기 위한 저장소.

`presentation-designer`(비공개)는 발표 자료 원본을 다루지만, 그 안의 Claude 아티팩트 링크는 비로그인 사용자가 열 수 있는지 보장되지 않는다. 이 저장소는 GitHub Pages(정적 호스팅, 무료·공개)로 그 문제를 해결한다.

## 사이트

- 목록: https://msbaek.github.io/talk-visuals/
- GitHub Pages 설정: 브랜치 `main`, 경로 `/` (저장소 전체를 그대로 서빙)

## 새 시각물 추가하는 법

1. `<주제-slug>/` 폴더를 만든다 (영문 소문자 + 하이픈, 공백·한글 금지 — URL 인코딩 문제 회피)
2. 그 안에 `index.html`과 이미지/GIF를 넣는다. GIF는 `<img src="파일명.gif">`처럼 **상대경로**로 참조한다 (base64 인라인 불필요 — 그건 Claude 아티팩트의 CSP 우회용이었을 뿐, 여기선 필요 없음)
3. 커밋 + `git push`
4. 30초~1분 안에 `https://msbaek.github.io/talk-visuals/<주제-slug>/` 로 바로 열린다 — Pages 설정을 다시 만질 필요 없음(정적 호스팅은 `index.html` 있는 폴더를 자동으로 서빙)
5. (선택) 루트 `index.html`에 카드 한 장 추가 — 목록에서 찾기 편하게 하는 용도일 뿐, URL 접속 자체엔 필수 아님

## 규약

- 폴더당 하나의 독립된 페이지. 다른 폴더 자산을 참조하지 않는다.
- 다크/라이트 테마 모두 고려한 CSS (`prefers-color-scheme` + `data-theme` 오버라이드)
- 페이지 문구는 한국어, 코드/식별자는 영어

## 이력

- 2026-08-06: 저장소 신설. 첫 항목 `commit-granularity/` — 커밋 단위를 내비게이션 안내에 빗댄 3막 애니메이션 (출처: `presentation-designer/assets/commit-granularity-nav/build_nav.py`)

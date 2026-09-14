# Garage Lab

주말에 만드는 단일 파일 웹 실험 모음. 실험 하나당 폴더 하나, 그 안에 `index.html` 한 장.
빌드 도구도 의존성 설치도 없고, GitHub Pages에 그대로 올라갑니다.

## 실험

| 실험 | 설명 | 주소 |
|---|---|---|
| 제로백 | 폰 GPS + 가속도 센서로 가속 시간·최고속도·제동 거리 측정, 주행 경로 기록(지도·GPX). 자동차 / 전기자전거, 드라이브 모드별 계기판·기록 | `/zeroback/` |

## 폰에서 열기 (ngrok)

GPS·센서를 쓰는 실험은 https 주소에서만 동작합니다. 폴더를 통째로 띄우고 ngrok으로 엽니다.

```bash
cd ~/Documents/garage-lab && python -m http.server 8000
ngrok http 8000        # 다른 터미널에서
```

ngrok이 준 `https://…` 주소로 열면 루트 목록이 나오고, 거기서 실험을 고릅니다. 코드를 고치면 새로고침만 하면 됩니다.

## GitHub Pages로 고정 주소 만들기 (선택)

저장소: `ysg00245/garage-lab` (현재 private). 무료 계정은 저장소를 **public**으로 바꿔야 Pages를 쓸 수 있습니다.

1. Settings → Pages → Source를 `main` 브랜치, 폴더는 `/ (root)`로 지정합니다.
2. 1~2분 뒤 `https://ysg00245.github.io/garage-lab/` 으로 접속합니다.

## 실험 추가하기

1. 폴더를 하나 만들고 그 안에 `index.html`을 넣습니다.
2. 루트 `index.html`의 목록에 줄을 하나 추가합니다.
3. 커밋하고 푸시하면 끝입니다.

## 알아두기

- **HTTPS 필수.** GPS, 센서, 저장 기능은 `file://`로 열면 동작하지 않습니다. 크롬이 권한 창조차 띄우지 않습니다.
- 기록 같은 브라우저 저장값은 **주소별로** 따로 저장됩니다. ngrok 주소가 바뀌면 이전 기록이 안 보입니다.
- `.nojekyll` 파일은 지우지 마세요. GitHub Pages가 파일을 그대로 서빙하게 합니다.
- 제로백은 트랙이나 통제된 장소에서만 사용하세요.

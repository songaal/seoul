# Orbit 안드로이드 앱

Orbit 웹사이트(`https://songaal.github.io/seoul/`)를 휴대폰의 Chrome으로 전체 화면에 띄우는 얇은 껍데기 앱입니다.
화면과 기능은 전부 웹사이트라서, 사이트를 고치면 앱도 같이 바뀝니다. 앱을 다시 설치할 필요가 없습니다.

## 설치 파일 받기

https://github.com/songaal/seoul/releases/latest/download/seoul.apk

`android/` 폴더가 바뀌어 `main`에 올라갈 때마다 GitHub가 자동으로 새 설치 파일을 만들어 위 주소에 올립니다.

## 서명 열쇠

- `signing/seoul-release.p12` 는 앱 서명 열쇠입니다. 비밀번호로 잠겨 있어서 파일만으로는 쓸 수 없습니다.
- 비밀번호는 저장소 Secret `KEYSTORE_PASSWORD` 에 들어 있습니다. 이 비밀번호를 잃어버리면 같은 앱으로 업데이트를 낼 수 없으니 따로 적어 두세요.

## 주소창 없애기 (선택)

처음에는 앱 위쪽에 얇은 주소창이 보입니다. 없애려면 `assetlinks.json` 파일이
`https://songaal.github.io/.well-known/assetlinks.json` 주소로 열려야 합니다.
그러려면 `songaal.github.io` 라는 이름의 저장소를 만들고 그 안에 `.well-known/assetlinks.json` 과 빈 `.nojekyll` 파일을 넣습니다.

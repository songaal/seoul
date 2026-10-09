# seoul

관심사로 이어지는 SNS. 구글 계정으로 로그인하고, 사진·글을 올리고, 서로의 글을 봅니다.

사이트 주소: https://songaal.github.io/seoul/

## 파일

| 파일 | 하는 일 |
|---|---|
| `index.html` | 앱 전체. 맨 위 `CONFIG`에 Firebase 설정값이 들어갑니다 |
| `firestore.rules` | 누가 무엇을 읽고 쓸 수 있는지 정한 규칙. Firebase 콘솔에 붙여 넣습니다 |
| `storage.rules` | 사진·동영상 저장소 규칙. Storage를 켰을 때만 씁니다 |

## 켜는 순서

1. **사이트 공개**: 이 저장소의 Settings → Pages → Branch를 `main` / `(root)` 로 고르고 Save.
2. **Firebase 프로젝트**: https://console.firebase.google.com 에서 프로젝트를 만들고 웹 앱(`</>`)을 등록합니다.
   나오는 `firebaseConfig` 값 6개를 `index.html` 맨 위 `CONFIG`에 넣습니다.
3. **구글 로그인**: Authentication → 로그인 방법 → Google → 사용 설정.
4. **주소 등록**: Authentication → 설정 → 승인된 도메인 → `songaal.github.io` 추가.
5. **데이터베이스**: Firestore Database → 데이터베이스 만들기 (위치 `asia-northeast3`, 프로덕션 모드).
   만든 뒤 "규칙" 탭에 `firestore.rules` 내용을 통째로 붙여 넣고 게시합니다.

`CONFIG`가 비어 있는 동안에는 "미리보기로 둘러보기"만 됩니다. 미리보기에서 올린 글은 그 브라우저에만 저장됩니다.

## 알아둘 점

- 카카오톡·인스타그램 안에서 연 화면에서는 구글이 로그인을 막습니다. Chrome이나 Safari로 열어 주세요.
- 동영상은 Firebase Storage(유료 요금제 Blaze 필요)를 켜고 `index.html`의 `USE_STORAGE`를 `true`로 바꿔야 올라갑니다. 끄면 사진만 올라갑니다.
- 예시 계정과 예시 게시물은 없습니다. 사람들이 올린 글만 보입니다.
- 노래 검색은 Apple의 공개 검색 서비스를 씁니다. 게시물에는 곡 링크와 누르면 나오는 30초 미리듣기가 붙습니다.

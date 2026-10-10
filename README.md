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

## 신고·차단·관리자

- 게시물과 댓글의 `···` 또는 "신고"에서 신고하거나 그 사람을 차단할 수 있습니다. 차단하면 그 사람의 글과 댓글이 내 화면에서 사라집니다.
- 앱 주인은 내 프로필의 "신고함"에서 들어온 신고를 보고, 남의 게시물과 댓글을 지울 수 있습니다.
- 누가 앱 주인인지는 `firestore.rules`의 `OWNER_EMAIL_HERE` 자리에 적은 구글 계정 메일로 정해집니다. Firebase 콘솔의 규칙에 붙여 넣을 때 본인 메일로 바꿉니다. 이 저장소는 공개라서 여기에는 메일을 적지 않았습니다.

## 알아둘 점

- 카카오톡·인스타그램 안에서 연 화면에서는 구글이 로그인을 막습니다. Chrome이나 Safari로 열어 주세요.
- 동영상은 한 개에 20MB까지 올라갑니다. 유료 저장소 없이 쓰려고, 동영상을 1MB보다 작은 조각으로 잘라 데이터베이스에 넣고 볼 때 다시 이어 붙입니다. 그래서 누른 뒤 다 받아야 재생됩니다.
- 무료 데이터베이스 용량은 1GB라서 20MB 동영상이면 50개쯤 들어갑니다. 더 필요하면 Firebase Storage(유료 요금제 Blaze)를 켜고 `index.html`의 `USE_STORAGE`를 `true`로 바꿉니다.
- 예시 계정과 예시 게시물은 없습니다. 사람들이 올린 글만 보입니다.
- 노래 검색은 Apple의 공개 검색 서비스를 씁니다. 게시물에는 곡 링크와 누르면 나오는 30초 미리듣기가 붙습니다.

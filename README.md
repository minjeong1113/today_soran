# 오늘의 소란

다섯 가지 질문에 답하면 오늘의 마음에 어울리는 소란의 노래를 추천해주는 모바일 중심 웹앱입니다.

## GitHub에 올리기

1. GitHub에서 새 저장소를 만듭니다.
2. `Add file` → `Upload files`를 누릅니다.
3. 이 압축파일을 푼 뒤, 폴더 안의 모든 파일과 폴더를 업로드합니다.
4. `Commit changes`를 누릅니다.

`index.html`이 저장소의 가장 바깥쪽에 있어야 합니다. `soran-today-github` 폴더 자체를 한 단계 더 안에 넣지 마세요.

## Vercel에 배포하기

1. Vercel에서 `Add New` → `Project`를 누릅니다.
2. 방금 만든 GitHub 저장소를 선택합니다.
3. Framework Preset은 `Other`로 선택합니다.
4. Build Command와 Output Directory는 비워둡니다.
5. `Deploy`를 누릅니다.

## 곡 데이터 업데이트

웹앱은 공개된 Google Sheets CSV를 먼저 읽습니다. 기존 시트의 `곡 리스트의 최종` 탭에 새 곡을 추가하면 배포 파일을 다시 올리지 않아도 방문자가 새로 접속할 때 반영됩니다.

- 기존 열 제목은 변경하지 않습니다.
- 감정·관계·상황·역할·사운드 태그는 쉼표로 구분합니다.
- 앨범 이미지는 Cloudinary의 공개 이미지 주소를 입력합니다.
- 시트 연결에 실패할 때만 `data/songs.js`의 내장 데이터를 대신 사용합니다.

## 주요 파일

- `index.html`: 질문, 추천 계산, 화면 디자인
- `data/songs.js`: 시트 연결 실패 시 사용하는 곡 데이터
- `assets/covers`: 시트 이미지가 없을 때 사용하는 앨범 이미지

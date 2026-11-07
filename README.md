# eyuzu 포트폴리오

컴퓨터인공지능학부 2학년 학생의 웹 실습과 학습 기록을 모은 개인 포트폴리오입니다.

수업에서 제공된 예제를 실행하고 수정한 경험, GitHub Pages 배포 과정, 문제를 해결하며 배운 내용을 기록합니다.

- [포트폴리오 방문하기](https://dbwn05-a11y.github.io/)
- [소개](https://dbwn05-a11y.github.io/about/)
- [프로젝트](https://dbwn05-a11y.github.io/projects/)
- [학습 기록](https://dbwn05-a11y.github.io/posts/)
- [연락처](https://dbwn05-a11y.github.io/contact/)

## 정리한 실습

### Movie Lab 배포 실습

수업에서 제공된 영화 검색 예제를 두 가지 방식으로 배포했습니다.

- 컴퓨터에서 빌드한 결과물을 직접 올리는 방식
- GitHub Actions가 소스 코드를 빌드하고 배포하는 방식

저장소 이름에 맞는 경로 설정과 커밋·푸시·배포의 관계를 익혔습니다.

### 팀 소개 페이지 배포 실습

제공된 HTML, CSS, JavaScript 예제를 바탕으로 Git 저장소를 만들고 소개 문구를 수정해 배포했습니다.

페이지 이름은 ‘팀 소개’이지만, 이곳에 정리한 활동은 혼자 진행한 개인 실습입니다.

## 포트폴리오에서 수정한 내용

- Hugo Coder로 시작한 사이트에 Hugo Profile 테마 적용
- 이름, 소개 문구, 메뉴와 연락처 수정
- 파란색 로봇 이미지와 한글 글씨체 적용
- 날짜가 없는 페이지의 잘못된 날짜 표시 수정
- 읽는 시간 표시 숨김과 한국어 인터페이스 적용
- 다른 프로젝트로 연결되는 배포 링크 수정
- 배포 오류와 해결 과정에 관한 학습 글 작성

## 주요 파일

실제 사이트의 원본 파일은 `site/` 폴더에 있습니다.

| 파일 또는 폴더 | 역할 |
| --- | --- |
| `site/hugo.toml` | 소개, 메뉴, 색상 등 사이트 설정 |
| `site/pages.json` | 배포 주소와 사용할 테마 설정 |
| `site/content/about.md` | 소개 페이지 |
| `site/content/projects.md` | 프로젝트 페이지 |
| `site/content/contact.md` | 연락처 페이지 |
| `site/content/posts/` | 학습 기록 |
| `site/static/style.css` | 글씨체와 화면 스타일 |
| `site/static/images/` | 사이트 이미지 |
| `site/layouts/_default/single.html` | 개별 페이지의 사용자 수정 템플릿 |
| `.github/workflows/hugo-pages.yml` | 자동 빌드와 배포 설정 |

## 로컬 미리보기

### 처음 실행할 때 준비하기

Windows PowerShell을 기준으로 안내합니다.

1. [Git for Windows](https://git-scm.com/install/windows)를 설치합니다.
2. 배포 환경과 맞추기 위해 [Hugo Extended 0.167.0](https://github.com/gohugoio/hugo/releases/tag/v0.167.0)을 준비합니다.
3. Hugo 압축을 풀고 `hugo.exe`가 들어 있는 폴더를 Windows의 PATH 환경 변수에 추가합니다.
4. PowerShell을 새로 열고 다음 명령으로 설치 상태를 확인합니다.

```powershell
git --version
hugo version
```

`hugo version` 결과에 `v0.167.0`과 `extended`가 표시되는지 확인합니다. 명령을 찾을 수 없다고 나오면 설치 경로와 PATH 설정을 확인합니다.

### 저장소 내려받기

저장소를 처음 내려받는 경우, 작업할 상위 폴더에서 다음 명령을 한 줄씩 실행합니다.

```powershell
git clone https://github.com/dbwn05-a11y/dbwn05-a11y.github.io.git
Set-Location .\dbwn05-a11y.github.io
```

이미 저장소를 내려받았다면 해당 저장소의 최상위 폴더에서 진행합니다. `README.md`와 `site/` 폴더가 보이는 위치입니다.

테마 파일은 저장소에 포함되어 있으므로 별도로 내려받지 않아도 됩니다.

### 미리보기 실행하기

저장소 최상위 폴더에서 다음 명령을 실행합니다.

```powershell
hugo server --source site --config "hugo.toml,pages.json" --baseURL "http://localhost:1313/" --renderToMemory --noBuildLock --disableFastRender
```

`--config "hugo.toml,pages.json"`은 사이트 설정과 배포 주소·테마 설정을 함께 읽기 위한 옵션입니다.

브라우저에서 [로컬 미리보기](http://localhost:1313/)에 접속합니다.

미리보기를 사용하는 동안 터미널을 열어 두고, 종료할 때는 Ctrl + C를 누릅니다.

## 새 학습 기록 만들기

터미널에서 `hugo` 명령을 사용할 수 있는 환경이라면, 저장소 최상위 폴더에서 다음 명령을 실행합니다.

```powershell
hugo new content posts/new-learning-note.md --source site --config "hugo.toml,pages.json"
```

`new-learning-note.md`는 작성할 글에 맞는 영문 파일명으로 바꿉니다.

이 명령은 `site/archetypes/posts.md` 템플릿을 사용해 `site/content/posts/` 안에 새 글을 만듭니다. 날짜는 자동으로 입력됩니다.

1. 제목과 설명을 글의 내용에 맞게 수정합니다.
2. 본문의 안내 문장을 실제 학습 내용으로 바꿉니다.
3. 직접 확인한 결과와 참고 자료, AI의 도움을 받은 부분을 기록합니다.

새 글은 `draft = true`인 초안으로 생성되어 일반 빌드에서는 사이트에 표시되지 않습니다. 초안을 포함한 미리보기는 다음 명령으로 실행합니다.

```powershell
hugo server --source site --config "hugo.toml,pages.json" --baseURL "http://localhost:1313/" --renderToMemory --noBuildLock --disableFastRender --buildDrafts
```

글을 완성하고 미리보기에서 확인한 뒤 `draft = false`로 바꿉니다. 저장하고 커밋·푸시한 다음, 배포 결과와 공개 사이트를 확인합니다.

## 배포와 확인

1. 파일을 수정하고 저장합니다.
2. 미리보기에서 변경 내용을 확인합니다.
3. 변경한 파일을 Git에 추가하고 커밋합니다.
4. `main` 브랜치로 푸시합니다.
5. GitHub Actions에서 빌드와 배포 결과를 확인합니다.
6. 공개 사이트에서도 수정한 내용과 링크를 확인합니다.

배포 과정에서는 `.github/pages_build.py`가 빌드 결과의 경로를 보정합니다. 따라서 로컬 미리보기뿐 아니라 공개 사이트에서도 링크를 확인합니다.

생성된 `public/` 파일을 직접 수정하지 않고 `site/`의 원본 파일을 수정합니다.

## 사용한 자료와 AI 도움

### 테마·라이브러리·글꼴

| 자료 | 사용한 부분 | 라이선스 |
| --- | --- | --- |
| [Hugo Profile](https://github.com/gurusabarish/hugo-profile) | 현재 포트폴리오의 기본 테마 | [MIT](https://github.com/gurusabarish/hugo-profile/blob/master/LICENSE) |
| [Hugo Coder](https://github.com/luizdepra/hugo-coder) | 처음 사이트를 구성할 때 사용한 테마 | [MIT](https://github.com/luizdepra/hugo-coder/blob/main/LICENSE.md) |
| [Bootstrap 5.1.3](https://github.com/twbs/bootstrap/tree/v5.1.3) | 테마에 포함된 화면 배치와 버튼 스타일 | [MIT](https://github.com/twbs/bootstrap/blob/v5.1.3/LICENSE) |
| [Font Awesome Free 6.4.2](https://github.com/FortAwesome/Font-Awesome/tree/6.4.2) | 테마의 아이콘 | [아이콘: CC BY 4.0, 코드: MIT](https://github.com/FortAwesome/Font-Awesome/blob/6.4.2/LICENSE.txt) |
| [Gowun Dodum](https://fonts.google.com/specimen/Gowun+Dodum) | 본문 글꼴 | [SIL Open Font License 1.1](https://github.com/google/fonts/blob/main/ofl/gowundodum/OFL.txt) |
| [Jua](https://fonts.google.com/specimen/Jua) | 제목 글꼴 | [SIL Open Font License 1.1](https://github.com/google/fonts/blob/main/ofl/jua/OFL.txt) |

각 자료에는 해당 원본 프로젝트의 라이선스가 적용됩니다. 원본 라이선스 파일과 코드에 포함된 저작권 표기를 유지하며, 이 저장소에서는 기존 자료를 바탕으로 개인화한 내용과 실습 과정을 정리합니다.

### 이미지와 AI 도움

- 파란색 로봇 이미지는 AI로 생성했습니다.
- 파란색 e 모양의 사이트 아이콘은 AI가 제공한 SVG 코드를 바탕으로 파일을 저장하고 사이트에 연결했습니다.
- 글의 구성, 설정과 코드 수정 방법, 오류 확인, 영어 커밋 메시지 작성에도 AI의 도움을 받았습니다.
- 파일 편집과 저장, Git 명령 실행, 배포 결과와 실제 화면 확인은 직접 진행했습니다.

기존 테마와 라이브러리, AI의 도움을 받은 부분을 구분하여 기록했습니다.


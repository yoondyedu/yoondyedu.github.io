# AI Cording Project — 시작 안내

GitHub Pages + Jekyll 블로그입니다. 블로그 이름의 Cording은 요청한 표기를 유지했습니다.
스타트업 · 사회 이슈 · 야구 분류, 연재별 목차, 연재 이전/다음 편, 모바일 레이아웃, RSS를 포함합니다.
초기 글 4개는 모두 명시적으로 표시한 예시이며 실제 기사나 사용자 경험을 대필한 것이 아닙니다.

## 1. 새 저장소 만들기

1. GitHub 로그인 후 우측 위 + → New repository를 누릅니다.
2. Repository name에 `본인아이디.github.io`를 입력합니다. 본인아이디는 GitHub 사용자명으로 바꾸고 소문자로 적습니다. 예: 사용자명이 myname이면 myname.github.io입니다.
3. Public을 선택합니다. 무료 개인 계정에서 이 방법으로 이용하려면 공개 저장소를 사용하세요.
4. Add a README file을 켜고 Create repository를 누릅니다.

## 2. 파일 올리기

1. 다운로드한 ZIP의 압축을 풉니다.
2. 저장소의 Code 화면에서 Add file → Upload files를 누릅니다.
3. 압축을 푼 폴더의 **안쪽 파일과 폴더 전체**를 드래그해 올립니다. ZIP 자체나 바깥 폴더 하나를 올리지 않습니다.
4. Commit changes로 저장합니다.
5. 저장소 최상위에 `_config.yml`, `index.html`, `_layouts`, `_posts`, `assets`가 보이는지 확인합니다.

중요: `_`로 시작하는 폴더와 파일도 빠짐없이 올려 주세요. `.gitignore`는 누락되어도 게시에는 영향이 없습니다. 별도 Actions 설정 파일은 필요하지 않습니다.

## 3. 사이트 주소 설정하기

저장소에서 `_config.yml`을 열고 연필 아이콘(Edit this file)으로 아래 두 줄을 설정합니다.

```yaml
url: "https://본인아이디.github.io"
baseurl: ""
```

반드시 사용자명으로 바꾸고 Commit changes를 누릅니다. 이 안내는 사용자 사이트용입니다. 다른 이름의 프로젝트 저장소를 쓰면 baseurl 설정이 달라집니다.

## 4. GitHub Pages 켜기

1. 저장소 Settings → Pages로 이동합니다.
2. Build and deployment의 Source에서 **Deploy from a branch**를 선택합니다.
3. Branch는 **main**, 폴더는 **/(root)**를 선택하고 Save를 누릅니다.
4. Actions 탭에서 Pages 관련 배포 작업의 상태를 확인합니다.
5. 성공 후 Settings → Pages의 Visit site로 접속합니다. 처음 반영에는 최대 약 10분이 걸릴 수 있습니다.

이 구성은 초보자가 웹 화면으로 파일을 올리기 쉬운 기본 Jekyll 브랜치 게시 방식을 사용합니다. GitHub 문서는 사용자 정의 자동화에는 GitHub Actions 방식을 권장하며, 원할 때 전환할 수 있습니다.

## 5. 새 글 올리기 — 브라우저만으로 가능

1. 저장소 Code → Add file → Create new file을 누릅니다.
2. 파일 이름에 `_posts/2026-11-14-my-first-post.md`처럼 입력합니다. 날짜는 실제 게시일로 바꾸고 영문 파일명은 매번 다르게 적습니다.
3. 아래 내용을 복사한 뒤 제목, 날짜, 분류, 설명, 본문을 수정합니다.

```markdown
---
layout: post
title: "나의 첫 번째 글"
date: 2026-11-14 09:00:00 +0900
category: 스타트업
series: "나의 창업 기록"
series_order: 1
description: "이번 글을 소개하는 한 문장입니다."
---

## 오늘의 기록

여기에 본문을 적습니다.
```

4. Commit changes를 누르면 다시 배포됩니다.

- 분류는 `스타트업`, `사회 이슈`, `야구` 중 하나로 정확히 적습니다.
- 연재가 아닌 단독 글은 `series`, `series_order` 두 줄을 모두 삭제합니다.
- 같은 연재는 series를 완전히 동일하게 쓰고, series_order를 1, 2, 3 순으로 늘립니다. 같은 번호를 중복 사용하지 않습니다.
- 연재 순서는 게시 날짜가 아니라 series_order를 기준으로 합니다.
- 미래 날짜의 글은 해당 시점이 지난 뒤 **다음 빌드 시** 공개됩니다. 시각만 지나면 자동 배포되는 예약 게시 기능은 아닙니다.
- 예시 글은 `_posts`에서 삭제하거나 직접 수정합니다. `templates/new-post.md`는 복사용이며 사이트에 게시되지 않습니다.

## 6. Markdown 기본 사용법

```markdown
## 소제목
**굵게** / *기울임*
- 목록 항목
[링크 제목](https://example.com)
> 인용문
```

이미지는 저장소에 `assets/images/사진.jpg`로 올린 뒤 다음처럼 넣습니다.

```liquid
![사진 설명]({{ '/assets/images/사진.jpg' | relative_url }})
```

이미지 폴더는 필요할 때 직접 생성하세요. 출처와 사용 권한을 확인하세요.

## 7. 꾸미기

- 이름/설명: `_config.yml` (화면 상단·하단의 이름도 바꾸려면 `_layouts/default.html`의 동일 문구 수정)
- 소개글: `about.md`
- 색상/글꼴/간격: `assets/style.css`
- 홈 인사말: `index.html`
- 댓글·방문 통계·외부 추적 스크립트는 넣지 않았습니다. 별도 서버나 데이터베이스도 없습니다.

## 8. 문제 해결

- 404: 저장소 이름, main/(root), 최상위 index.html, 배포 성공 여부를 확인합니다.
- 글이 안 보임: `_posts/YYYY-MM-DD-영문이름.md` 형식, 앞부분의 --- 두 줄, 날짜/시간, main 브랜치 저장 여부를 확인합니다.
- CSS가 안 나옴: `_config.yml`의 baseurl이 빈 문자열인지 확인합니다.
- 빌드 실패: Actions에서 실패한 Pages 작업을 열어 오류를 확인합니다. YAML 제목에 콜론(:)이 있으면 제목 전체를 큰따옴표로 감쌉니다.
- 사이트 내용은 공개됩니다. 개인정보, 비밀번호, API 키를 올리지 마세요.

## 검증 범위

파일 구조, 문서 메타데이터, 내부 레이아웃 참조, ZIP 내용을 점검했습니다. 이 환경에서는 Jekyll 빌드를 실행하지 않았으므로 실제 빌드/배포 확인은 GitHub Actions의 Pages 작업에서 해야 합니다. 저장소 생성·업로드·게시까지 대신 수행한 것은 아닙니다.

공식 안내: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll

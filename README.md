# Dev Ian Blog

[Hexo](https://hexo.io) + [Tranquilpeak](https://github.com/LouisBarranqueiro/hexo-theme-tranquilpeak) 테마로 만든 개인 공부용 블로그입니다.
👉 https://yhlee217.github.io

이 저장소는 **글(마크다운) 소스**를 관리합니다. `master` 브랜치에 push 하면
GitHub Actions가 자동으로 빌드해서 GitHub Pages에 배포합니다.
(예전처럼 로컬에서 `hexo deploy` 할 필요가 없습니다.)

## 📂 구조

```
_config.yml                 # Hexo 사이트 설정
_config.tranquilpeak.yml    # 테마 사용자 설정
source/_posts/              # ✍️ 글(.md) — 여기에 글을 추가하면 됩니다
source/all-categories/      # 카테고리 목록 페이지
source/all-tags/            # 태그 목록 페이지
source/all-archives/        # 연도별 보관 페이지
themes/tranquilpeak/        # 테마(빌드된 에셋 포함)
.github/workflows/deploy.yml# 자동 빌드·배포 워크플로
```

## ✍️ 글 쓰는 법

`source/_posts/` 에 `.md` 파일을 만들고 아래처럼 front-matter를 작성합니다.

```markdown
---
title: "글 제목"
date: 2026-06-01 12:00:00
tags:
  - 태그1
  - 태그2
categories:
  - 카테고리
---

본문 내용 (마크다운)
```

파일을 `master` 에 push 하면 1~2분 뒤 사이트에 자동 반영됩니다.

> URL은 `_config.yml` 의 `permalink: :year/:month/:day/:title/` 규칙을 따르며,
> `:title` 은 **파일 이름**(slug)에서 만들어집니다.

## 🔒 비밀번호로 잠그는 글 (hexo-blog-encrypt)

특정 글을 **비밀번호를 입력해야 볼 수 있게** 만들 수 있습니다.
글의 front-matter 에 `password` 한 줄만 추가하면 됩니다.

```markdown
---
title: "잠긴 글"
date: 2026-06-01 12:00:00
password: 원하는_비밀번호
abstract: 이 글은 비밀번호로 보호되어 있습니다.   # (선택) 잠금 화면 안내문
message: 비밀번호를 입력하세요.                  # (선택) 입력창 위 문구
---

본문은 비밀번호를 입력해야 보입니다.
```

- 배포된 HTML에는 본문이 **암호화(AES)되어** 들어가므로, 비밀번호를 모르면 내용을 볼 수 없습니다.
- 기본 안내 문구는 `_config.yml` 의 `encrypt:` 에서 바꿀 수 있습니다.
- 예시 글: `source/_posts/secret-example.md` (비밀번호 `hello`) — 필요 없으면 삭제하세요.

> 참고: 글을 **아예 사이트에 안 띄우려면** front-matter 에 `published: false` 를 넣거나
> `source/_drafts/` 폴더에 두면 됩니다(빌드에서 제외됨).

## 🖥 로컬에서 미리보기 (선택)

```bash
npm install
# 테마는 저장소에 포함되어 있으므로 별도 설치 불필요
npx hexo server      # http://localhost:4000
```

빌드만 확인하려면:

```bash
npx hexo clean && npx hexo generate   # 결과물은 public/ 에 생성
```

## ⚙️ 최초 1회 설정 (중요)

자동 배포가 동작하려면 GitHub 저장소 설정에서 Pages 소스를 바꿔야 합니다.

**Settings → Pages → Build and deployment → Source → `GitHub Actions`** 로 변경

(기존의 "Deploy from a branch" 에서 "GitHub Actions" 로 바꾸는 것)

## 🎨 테마 / 설정 변경

- 사이드바 메뉴·소셜 링크: `themes/tranquilpeak/_config.yml`
- 그 외 테마 옵션(프로필, 댓글, 검색, 분석 등): `_config.tranquilpeak.yml`
- 사이트 제목/설명/URL 등: `_config.yml`

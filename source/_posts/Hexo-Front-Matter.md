---
title: "Hexo_Front-Matter"
date: 2020-12-05 01:45:34
updated: 2020-12-20 06:56:29
tags:
  - Blog
  - HEXO
---

## Front Matter

- **Tranquilpeak** 기준
- *.md 파일 내 Post 기본 설정

  
```
title: title
date: yyyy-MM-dd hh:mm:ss
tags:
- "tag1"
- "tag2"
category:
- category1
keywords: # 검색엔진에서 사용될 키워드 지정
- "keyword_1"
- "keyword_2"
clearReading: true # 게시물볼때 옆에 사이드바 치움
thumbnailImage: image-1.png # 썸네일이미지 지정(`source/_post/게시물md파일이름/`폴더 안에 해당 이미지가 있어야함)
thumbnailImagePosition: bottom # 썸네일이미지 위치지정
autoThumbnailImage: yes #thumbnailImage로 썸네일이미지가 지정안되어있을경우 cover이미지나 게시물의 이미지를 이용하여 자동으로 썸네일 지정
metaAlignment: center # 게시물의 메타정보 정렬유형
coverImage: image-2.png # 커버이미지 지정(이것역시 썸네일이미지처럼 게시물폴더안에 이미지가있어야함)
coverCaption: "A beautiful sunrise" # 커버캡션 지정(따로 지정해놓지않으면 게시물제목으로 설정됨)
coverMeta: out # 커버캡션을 cover이미지 안에 넣을건지 밖에 따로 놓을건지 설정
coverSize: full # 커버이미지 사이즈
gallery: #
- "image_1"
- "image_2"
comments: false # 댓글
meta: false # 메타
actions: false
```

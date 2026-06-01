---
title: "비밀글 예시 (비밀번호: hello)"
date: 2026-06-01 12:00:00
tags:
  - Blog
password: hello
abstract: 이 글은 비밀번호로 보호되어 있습니다. 비밀번호를 입력해 주세요.
message: 비밀번호를 입력하세요. (예시 비밀번호는 hello 입니다)
---

이 글은 `hexo-blog-encrypt` 로 암호화된 예시 글입니다.

front-matter 에 `password: hello` 를 넣었기 때문에,
방문자는 **비밀번호 `hello`** 를 입력해야 아래 내용을 볼 수 있습니다.

## 비밀번호를 걸려면

글 맨 위 front-matter 에 아래 한 줄만 추가하면 됩니다.

```yaml
password: 원하는_비밀번호
```

필요 없으면 이 예시 글(`source/_posts/secret-example.md`)은 삭제하세요.

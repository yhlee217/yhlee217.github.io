---
title: "About NPM"
date: 2020-12-19 21:42:09
updated: 2020-12-20 07:00:28
tags:
  - NPM
  - Blog
---

![image](https://user-images.githubusercontent.com/42199367/102707218-75b58200-42dc-11eb-92c8-afa46810e342.png)

## [NPM](https://www.npmjs.com/)(Node Package Manager)

- #### 공식 홈페이지 : <https://www.npmjs.com/>
- #### 원저자 : Isaac Z. Schlueter
- #### 개발자 : Rebecca Turner, Kat Marchan 등
- #### 발표일 : 2010년 1월
- #### Git : <https://github.com/npm/cli>
- 명령 줄 클라이언트(npm), 그리고 공개 패키지와 지불 방식의 개인 패키지의 온라인 데이터베이스(npm 레지스트리)로 이루어져 있다.
- 레지스트리는 클라이언트를 통해 접근되며 사용 가능한 패키지들은 npm 웹사이트를 통해 찾아보고 검색할 수 있다. 패키지 관리자와 레지스트리는 npm사에 의해 관리된다.
- #### 비슷한 개념

```
Ruby - Gem
PHP - Composer
C# - NuGet
Java - JPM
Python - Pip
```
```
# Hexo Blog 'package.json'
{
"name": "hexo-site",
"version": "0.0.0",
"private": true,
"scripts": {
"build": "hexo generate",
"clean": "hexo clean",
"deploy": "hexo deploy",
"server": "hexo server"
},
"hexo": {
"version": "5.2.0"
},
"dependencies": {
"hexo": "^5.0.0",
"hexo-deployer-git": "^2.1.0",
"hexo-generator-archive": "^1.0.0",
"hexo-generator-category": "^1.0.0",
"hexo-generator-index": "^2.0.0",
"hexo-generator-searchdb": "^1.3.3",
"hexo-generator-tag": "^1.0.0",
"hexo-renderer-ejs": "^1.0.0",
"hexo-renderer-marked": "^3.0.0",
"hexo-renderer-stylus": "^2.0.0",
"hexo-server": "^2.0.0"
}
}
```

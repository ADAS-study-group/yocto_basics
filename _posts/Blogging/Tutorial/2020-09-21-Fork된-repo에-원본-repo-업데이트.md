---
title: Fork된 repo에 원본 repo 업데이트
author: devlee
date: 2020-09-21 00:00:00 +0800
categories: [Blogging, Tutorial]
tags: [Writing, Blogging]
---

## 원본 repo에서 fork로 가져와 local에서 작업중에 원본 repo가 업데이트 되었다. 최신 원본 repo로 업데이트 하는 방법을 알아보자 

### 1. 원본 repo와 fork로 가져온 로컬 repo는 다음과 같다.

- 원본 repo : [https://github.com/ADAS-study-group/adas-study-group.github.io.git](https://github.com/ADAS-study-group/adas-study-group.github.io.git)
- fork repo : [https://github.com/devlee8585/adas-study-group.github.io.git](https://github.com/devlee8585/adas-study-group.github.io.git)

### 2. PC에 git clone한 로컬 repo에 원본 repo 등록

``` sh
git remote add {REPOSITORY_NAME} {GIT_URL}
```
![Desktop View]({{ "/assets/img/post/2020-09-21/fork_update_1.png" | relative_url }})

### 3. 원본 git remote로부터 로컬 repo에 업데이트

``` sh
git pull {REMOTE_ORIGIN_REPO_NAME} {BRANCH_NAME_OF_LOCAL_REPO}
```
![Desktop View]({{ "/assets/img/post/2020-09-21/fork_update_2.png" | relative_url }})

### 4. 로컬 repo에 원본 repo 변경 사항 업데이트 후 Fork repo에 반영

``` sh
git push {REMOTE_FORKED_REPO_NAME} {BRANCH_NAME_OF_LOCAL_REPO}
```

![Desktop View]({{ "/assets/img/post/2020-09-21/fork_update_3.png" | relative_url }})

![Desktop View]({{ "/assets/img/post/2020-09-21/fork_update_4.png" | relative_url }})

## 요약
- Fork 된 repo는 생성 지점을 기준으로 이후에 발생한 원본 repo의 변경이 반영되지 않음
- PC 로컬 git repo를 경유하여 Fork된 repo에 원본의 변경 사항을 반영할 수 있음
- PC 로컬 git repo에 “upstream”이라는 이름으로 원본 레파지토리를 등록하고 git pull과 git push 명령으로 위와 같은 절차로 원본의 변경 사항을 fork repo에 반영할 수 있습니다.
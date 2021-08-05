---
title: "Markdown 문법 써보기"
excerpt: "블로그 글 작성을 연습할겸 Markdown 언어를 공부해봤다."

categories:
  - "Markdown"
tags:
  - "Markdown"
---

## 목차

- [markdown ?](#markdown-)
- [markdown 문법](#markdown-문법)
  - [글머리](#글머리)
  - [인용](#인용)
  - [정렬 목록](#정렬-목록)
  - [비정렬 목록](#비정렬-목록)
  - [코드](#코드)
  - [수평선](#수평선)
  - [링크](#링크)
  - [이미지 삽입](#이미지-삽입)
  - [표 만들기](#표-만들기)

---

## markdown ?

- markdown은 텍스트 기반의 마크업 언어이다.
- 문법이 간단 하고 가독성이 좋다.
- GitHub에 README 파일이 markdown 형식으로 되어있다.

## markdown 문법

markdown 문법에 대해 알아 보겠다.

### 글머리

# 제목 1 입니다.

```markdown
# 제목 1 입니다.
```

## 제목 2 입니다.

```markdown
## 제목 2 입니다.
```

### 제목 3 입니다.

```markdown
### 제목 3 입니다.
```

### 제목 4 입니다.

```markdown
### 제목 4 입니다.
```

### 제목 5 입니다.

```markdown
### 제목 5 입니다.
```

### 인용

```markdown
> 두발은 나쁘고 네발은 좋다.
```

> 두발은 나쁘고 네발은 좋다.

단계별 인용

```markdown
> 스퀄러
>
> > 스노우볼
> >
> > > 나폴레옹
```

> 스퀄러
>
> > 스노우볼
> >
> > > 나폴레옹

### 정렬 목록

```markdown
1. 펄프픽션
2. 노인을 위한 나라는 없다.
3. 로스트 인 더스트
4. 살인의 추억
```

1. 펄프픽션
2. 노인을 위한 나라는 없다.
3. 로스트 인 더스트
4. 살인의 추억

### 비정렬 목록

```markdown
- 안녕
  - hello
    - 잘가
```

- 안녕
  - hello
    - 잘가

### 코드

````markdown
```Python
print("알고리즘을 알고 있니?");
```
````

```python
print("알고리즘을 알고 있니?");
```

### 수평선

```markdown
---
```

---

### 링크

```markdown
- 링크 표시법 : [Title](link)
  [구글 링크](https://google.com)
```

[구글 링크](https://google.com)

- 주소 직접 표시법

```markdown
<https://google.com>
```

<https://google.com>

### 이미지 삽입

```markdown
![](/assets/images/trueman.jpg)
```

![](/assets/images/trueman.jpg)

```markdown
![](/assets/images/trueman.jpg){: .align-center}
```

![](/assets/images/trueman.jpg){: .align-center}

```markdown
![](/assets/images/trueman.jpg "트루먼 쇼"){: .align-center}
```

![](/assets/images/trueman.jpg "트루먼 쇼"){: .align-center}

### 표 만들기

- 표 내용 중앙 정렬

```markdown
| 안  | 녕  | 하  |
| :-: | :-: | :-: |
| 안  | 녕  | 하  |
```

| 안  | 녕  | 하  |
| :-: | :-: | :-: |
| 안  | 녕  | 하  |

- 표 내용 좌측 정렬-중앙 정렬-우측 정렬

```markdown
| 하하하하 | 아아아아아 | 이이이이이 |
| :------- | :--------: | ---------: |
| 안       |     녕     |         하 |
```

| 하하하하 | 아아아아아 | 이이이이이 |
| :------- | :--------: | ---------: |
| 안       |     녕     |         하 |

여기까지 마크다운 기본적인 문법이다.

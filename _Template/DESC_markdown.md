Reference URL : https://goddaehee.tistory.com/307

## 1. 제목
- 설명 : h1 ~ h6 까지 표현 가능하다.
```
# 제목1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
###### 제목 6
```

## 2. 줄바꿈 
- 설명 : 띄어쓰기 2번 또는 <br/>로 표현 가능 하다.
```
# 줄바꿈(Line Breaks) 
띄어쓰기 2번  
또는 <br/>
```

## 3. 수평선
- 설명 : 가시적으로 페이지를 나누는 용도로 주로 사용 됨.
- ---
***
___
******
```
---
***
___
******
```

## 4. 글자 강조
- 굵은 글씨
- 기울임
- 취소선
- 밑줄
**굵은 글씨**  
*이텔릭*  
_이탤릭_  
~~취소선~~  
<u>밑줄</u>  
ex)  
This is the **bold** text and this is the *italic* text and <u>let's</u> do ~~strikethrough~~
```
**굵은 글씨**  
*이텔릭*  
_이탤릭_  
~~취소선~~  
<u>밑줄</u>  
ex)  
This is the **bold** text and this is the *italic* text and <u>let's</u> do ~~strikethrough~~
```
## 5. 인용문 (BlockQuote)
- 설명 : ">"  블럭 인용 문자를 사용하면 인용문 표현이 가능하다.
> 인용문장
>> 중첩된 인용문
>>> 중첩된 인용문 2
```
> 인용문장
>> 중첩된 인용문
>>> 중첩된 인용문 2
```
## 6. 목록 (List)
### 6-1. 순서가 없는 목록 ( *, +, - 지원)
- 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록
        - 순서가 필요하지 않은 목록
* 순서가 필요하지 않은 목록
    * 순서가 필요하지 않은 목록
        * 순서가 필요하지 않은 목록
+ 순서가 필요하지 않은 목록
    + 순서가 필요하지 않은 목록
        + 순서가 필요하지 않은 목록

- 순서가 필요하지 않은 목록
    * 순서가 필요하지 않은 목록
    + 순서가 필요하지 않은 목록
```
- 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록
        - 순서가 필요하지 않은 목록
* 순서가 필요하지 않은 목록
    * 순서가 필요하지 않은 목록
        * 순서가 필요하지 않은 목록
+ 순서가 필요하지 않은 목록
    + 순서가 필요하지 않은 목록
        + 순서가 필요하지 않은 목록

- 순서가 필요하지 않은 목록
    * 순서가 필요하지 않은 목록
    + 순서가 필요하지 않은 목록
```

### 6-2. 순서가 있는 목록
1. 순서가 필요한 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
1. 순서가 필요한 목록


1. 순서가 필요한 목록
    9. 순서가 필요한 목록
    3. 순서가 필요한 목록
8. 순서가 필요한 목록

```
1. 순서가 필요한 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
1. 순서가 필요한 목록


1. 순서가 필요한 목록
    9. 순서가 필요한 목록
    3. 순서가 필요한 목록
8. 순서가 필요한 목록
```

### 6-3. 혼합 사용
- 순서가 필요하지 않은 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
- 순서가 필요하지 않은 목록2
    1. 순서가 필요한 목록
    3. 순서가 필요한 목록
    8. 순서가 필요한 목록

```
- 순서가 필요하지 않은 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
- 순서가 필요하지 않은 목록2
    1. 순서가 필요한 목록
    3. 순서가 필요한 목록
    8. 순서가 필요한 목록
```

## 7. 링크
### 7-1. 기본 방법
Click [here](https://github.com/commGom/Azure_Study2023)  
[Azure_Study2023](https://github.com/commGom/Azure_Study2023)

### 7-2. 참조 링크 사용 방법
- 설명
```
 [link keyword][id]
 [id]: URL "Optional Title" 
```
ex) title 옵션 없이 사용
[commGom 깃허브 url][commGom]
[commGom]: https://github.com/commGom/Azure_Study2023
```
[commGom 깃허브 url][commGom]
[commGom]: https://github.com/commGom/Azure_Study2023
```

### 7-3. 자동 링크 사용 방법
- 설명 : 인터넷 URL 혹은 이메일 주소를 적합한 형식으로 링크를 생성해준다.
```
https://github.com/commGom/Azure_Study2023
```
https://github.com/commGom/Azure_Study2023

### 8-1. 기본문법 
![Image Description](./brokenArm-commGom.jpeg)
```
![대체텍스트](이미지주소)
ex) ![Image Description](./brokenArm-commGom.jpeg)
```

### 8-2. 참조 링크 사용 방법
![이미지설명입력](ID)
[ID]:https://이미지링크

```
![이미지설명입력](ID)
[ID]:https://이미지링크
```

### 8-3. 이미지 노출과 동시에 링크처리
[![commGom로고이미지](./brokenArm-commGom.jpeg)](https://github.com/commGom/Azure_Study2023)
```
[![commGom로고이미지](./brokenArm-commGom.jpeg)](https://github.com/commGom/Azure_Study2023)
```

## 9. 표 (Table)
- 설명 
   - |(vertical bar) 기호를 통해 테이블을 표현 가능. (가장 좌측, 우측 생략 가능)

   - 헤더와 셀을 구분할 때 3개 이상의 -(하이픈, 대시)가 필요 하다.

   - : (콜론) 기호를 통해 정렬할 수 있다.

| Header | value | Description |
| --: | :-- | :--: |
| 정렬 | --: | 우측정렬 |
| 정렬 | :-- | 좌측정렬 |
| 정렬 | :--: | 가운데정렬 |

```
| Header | value | Description |
| --: | :-- | :--: |
| 정렬 | --: | 우측정렬 |
| 정렬 | :-- | 좌측정렬 |
| 정렬 | :--: | 가운데정렬 |
```

## 10. 코드(code)
- 설명 : 백틱(` : 숫자 1번 키 왼쪽에 위치)으로 강조할 내용을 감싸면 된다. 
(```언어)
  - ex) html, css, javascript, bash, plaintext

## 11. HTML 문법 이용 가능
- 이미지 크기 지정(html 이용하여)
  - commGom <img width="10" src="./brokenArm-commGom.jpeg" alt="commGom" />
  - commGom <img width="70" src="./brokenArm-commGom.jpeg" alt="commGom" />
  - commGom <img width="100" src="./brokenArm-commGom.jpeg" alt="commGom" />
  - commGom <img width="150" src="./brokenArm-commGom.jpeg" alt="commGom" />

- 인라인 style 적용하여 style 적용
  - <span style="text-decoration: underline;">commGom</span>  입니다.
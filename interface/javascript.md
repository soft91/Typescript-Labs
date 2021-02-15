---
description: >-
  참조 :
  https://stackoverflow.com/questions/1187518/how-to-get-the-difference-between-two-arrays-in-javascript
---

# \[Javascript\] 두 배열의 대한 비교 방법

실무에서나 알고리즘의 대한 공부를 할 때 두 배열의 대한 비교나 교집합\(Intersection\), 차집합\(Difference\)은 정말 많이 사용되는 것 같다.

특히 알고리즘을 풀 때 단골 문제가 아닐까 싶다.

실무에서 작업하는 도중 갑자기 차집합의 대한 문제가 있어 Stackoverflow에 아주 좋은 설명이 있어서 정리하려고 한다.

먼저 **두 배열의 대한 제일 간단한 비교는 JSON.stringify를 통해 문자열로 변경해 준 뒤 비교하는 방법이 있다.**

아마 이게 제일 간단할 것 같다.

  


![&#xB450; &#xBC30;&#xC5F4;&#xC744; &#xBE44;&#xAD50;&#xD558;&#xB294; &#xAC04;&#xB2E8;&#xD55C; &#xBC29;&#xBC95;. &#xACB0;&#xACFC;&#xB294; false&#xB85C; &#xB5A8;&#xC5B4;&#xC9C4;&#xB2E4;.](https://blog.kakaocdn.net/dn/bwzXt2/btqXu5cxJoA/fXfGRMdy9zejJfzkKP5tjK/img.png)

**교집합과 차집합 같은 경우엔 Array의 filter와 includes prototype Method로 간단하게 비교할 수 있다.**

#### **교집합\(Intersection\)**

![&#xAD50;&#xC9D1;&#xD569;&#xC758; &#xC608;](https://blog.kakaocdn.net/dn/0F5AB/btqXj8ab6xf/4OOtDjuOa1gp5i5YJQnjS0/img.png)

```text
// 배열 선언
const arr1 = ['1','2','3','4','5'];
const arr2 = ['1','2'];


// 교집합(Intersection)
console.log(arr1.filter(x => arr2.includes(x)));

// Result : ['1','2']
```

arr2에 includes 함수를 통해서 arr1의 값\(x\)이 있으면 true, 아니면 false를 반환하여 

arr1의 filter 함수를 통해 true 값만 걸러내 새로운 배열을 만든다.

#### 차집합\(Difference\)

![&#xCC28;&#xC9D1;&#xD569;&#xC758; &#xC608;](https://blog.kakaocdn.net/dn/bl9Ppm/btqXxd2aC4Q/gxY6lEdQK6ZH6O89wmjvsK/img.png)

```text
// 배열 선언
const arr1 = ['1','2','3','4','5'];
const arr2 = ['1','2'];


// 교집합(Intersection)
console.log(arr1.filter(x => !arr2.includes(x)));

// Result : ['3','4','5']
```

arr2에 includes 함수를 통해서 arr1의 값\(x\)이 있으면 false, 아니면 true를 반환하여

arr1의 filter 함수를 통해 true 값만 걸러내 새로운 배열을 만든다.

두 함수로 간단한 배열비교를 할 수 있다.


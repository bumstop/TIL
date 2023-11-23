# TIL

- **[ 마크다운(Markdown) 사용법 ]**  
  <https://gist.github.com/ihoneymon/652be052a0727ad59601>

---
# JS

## React

### [ 리액트 CDN 방식 ]

```
<!-- 1.리액트 기본 라이브러리 -->
<script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script>
<!-- 2.리액트 가상돔 라이브러리 -->
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script>
<!-- 3.리액트 바벨 라이브러리 -->
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>



<!-- 아래쪽에 나의 JS : 반드시 type="text/babel" 쓸것! -->
<!-- import할 모듈JS가 위쪽에 위치 -->
<script src="모듈JS" data-plugins="transform-es2015-modules-umd" type="text/babel"></script>
<!-- 메인 JS가 아래쪽에 위치 -->
<script src="메인JS" data-plugins="transform-es2015-modules-umd" type="text/babel"></script>
```

<br/>

---

### 리액트 이미지 삽입

- 리액트 이미지등 정적 컨텐츠는 public 폴더에 넣어줘야 올바른 경로로 읽어온다.
  <br/><br/>

---

### [Warning: Each child in a list should have a unique "key" prop.] 에러

- React는 key prop을 사용하여 컴포넌트와 DOM 요소 간의 관계를 생성한다. <br/>
  리액트 라이브러리는 이 관계를 이용해 컴포넌트 리렌더링 여부를 결정한다. <br/>
  불필요한 리렌더링을 방지하기 위해서는 각 자식 컴포넌트마다<br/> 독립적인 key값을 넣어줘야 한다.<br/>
  **(key가 전역적으로 고유할 필요는 없다. 형제 요소에서 고유해야 한다.)**

- 해결방법으로는 배열로 map 함수를 사용해 JSX 리스트를 구현할 때 key prop을 자식 컴포넌트마다 넣어줘야 한다.

자바스크립트의 배열은 정적이지 않다.즉, 배열의 길이나 원소 등이 변할 수 있다는 의미이다.
<br/>
따라서 배열의 index를 key prop으로 사용하는 것을 지양해야 한다.

배열의 원소의 순서가 바뀌면 index도 바뀌고 컴포넌트마다 고유해야 하는 key값도 같이 바뀌기 때문이다. <br/>
이렇게 되면 리액트는 리렌더링 해야하는 컴포넌트를 헷갈려 잘못된 컴포넌트를 리렌더링할 수 있다.

```
// BAD :(

{["AAA", "BBB", "CCC"].map((item,index) =>
      <div key={index}>{item}</div>
  )}


// GOOD :)

{["AAA", "BBB", "CCC"].map(item =>
    <div key="{item}">{item}</div>
  )}
```

<br/>

---
# CSS

- **[ 폰트 파일 적용하기 ]**

  <https://velog.io/@jehjong/CSS%EC%97%90-%ED%8F%B0%ED%8A%B8-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-%EC%9B%B9%ED%8F%B0%ED%8A%B8-%ED%8F%B0%ED%8A%B8-%ED%8C%8C%EC%9D%BC#%ED%8F%B0%ED%8A%B8-%ED%8C%8C%EC%9D%BC-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0>
  <br/>

  ***

- **[ display: contents ]**

  속성이 부여된 요소의 자식이 자신의 부모를 무시하고, <br/>
  조부모의 직계 자식인 것처럼 동작하게 하는 속성

  ***

- **[ transform-style: preserve-3d ]**

  - 3D 애니메이션 속성 - 입체적으로 보이게 하는 속성
    <br/>

  ***

- **[ svg 라인 애니메이션을 위한 중요속성 ]**

  1. stroke-dasharray : 선과 공백으로 만드는 점선셋팅

  - 단위없이 숫자만 쓰면 px단위
  - 숫자를 하나만 쓰면 선,공백이 동일하게 셋팅됨
  - 숫자를 2개 이상 쓰면 선,공백 순으로 크기를 셋팅함  
     [ 만일 %단위를 쓰면? ]
    -> 50%를 주고 몇조각 나는지 세어본다!
    <br/><br/>

  2. stroke-dashoffset : 선, 공백 순서에서 시작위치 셋팅 -> 공백부터 시작가능!
     <br/><br/>

```
stroke-dasharray: 400%;
```

50%를 값으로 주고 몇조각? 8조각남!<br/>
50% \* 8 = 400% -> 결과적으로 선만 보임!<br/>
공백이 숨어있음 -> 시작위치를 밀어서 공백부터 보이게함<br/>
-> stroke-dashoffset으로 밀어준다! <br/>
-> stroke-dasharray값과 같은 값을 주면 공백부터시작!<br/><br/>

---



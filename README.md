# TIL

- **[ 마크다운(Markdown) 사용법 ]**  
  <https://gist.github.com/ihoneymon/652be052a0727ad59601>

---

# CSS

- **[ 폰트 파일 적용하기 ]**
  <br/>
  <https://velog.io/@jehjong/CSS%EC%97%90-%ED%8F%B0%ED%8A%B8-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-%EC%9B%B9%ED%8F%B0%ED%8A%B8-%ED%8F%B0%ED%8A%B8-%ED%8C%8C%EC%9D%BC#%ED%8F%B0%ED%8A%B8-%ED%8C%8C%EC%9D%BC-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0>
  <br/><br/>

  ***

- **[ 3D 애니메이션 : 입체적으로 보이게하는 속성 ]**
  - transform-style: preserve-3d;
    <br/><br/>
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

# JS

## React

### [ 리액트 CDN방식 호출코드 ]

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

- 리액트 이미지 삽입
    - 리액트 이미지등 정적 컨텐츠는 public 폴더에 넣어줘야 올바른 경로로 읽어온다.

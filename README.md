# TIL
* [ 마크다운(Markdown) 사용법 ]   
 <https://gist.github.com/ihoneymon/652be052a0727ad59601>
---
# CSS
## [ 폰트 파일 적용하기 ]
<https://velog.io/@jehjong/CSS%EC%97%90-%ED%8F%B0%ED%8A%B8-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-%EC%9B%B9%ED%8F%B0%ED%8A%B8-%ED%8F%B0%ED%8A%B8-%ED%8C%8C%EC%9D%BC#%ED%8F%B0%ED%8A%B8-%ED%8C%8C%EC%9D%BC-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0>


* 입체적으로 보이게하는 속성

    transform-style: preserve-3d;

# JS

## React

### [ 리엑트 CDN방식 호출코드 ]
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

* 리액트 이미지 삽입

    리액트 이미지등 정적 컨텐츠는 public 폴더에 넣어줘야 올바른 경로로 읽어온다.

    (src 폴더에) 넣어두면 경로를 읽지 못한다.

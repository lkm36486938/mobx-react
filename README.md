# MOBX practice

## React without CRA

### for river and ddon-gae
<br/>
<br/>

## INTRODUCTION
CRA로 만든 프로젝트에서 MOBX 를 공부하려하다가 데코레이터 쓰는부분에서 막혀서 <br/>
CRA없이 React 프로젝트만들기를 해봐야겠다 싶어서 만든 프로젝트임. <br/>
MOBX 공부도 업로드 <br/>
README.md 파일의 설정은 초기설정임을 참고.

## COMMAND LIST
```
npm 을 사용해도 되고 yarn 을 사용해도 됨
하지만, yarn 이 좀 더 장점이 많다고 하여 yarn 을 사용.
```
관련링크: https://dongmin-jang.medium.com/npm-vs-yarn-7b699c5d6034
<br/>
https://www.carlrippon.com/creating-react-app-with-typescript-eslint-with-webpack5/

<br/>

### TS 
1. 설치
```
yarn add typescript @types/react @types/react-dom @types/node @types/jest -D
```
2. ts 설정파일 생성
```
npx typescript --init
```

### WEBPACK 
1. 설치 (webpack 은 5버젼으로 깔리겠지만 @types/webpack 은 4버젼으로 해줘야 devServer 컬럼에서 컴파일 에러가 안남..)
```
yarn add webpack webpack-cli @types/webpack@4 webpack-dev-server @types/webpack-dev-server babel-loader html-webpack-plugin -D
```
2. 개발용 설정파일 생성

루트폴더에 webpack.dev.config.ts 파일 생성

### REACT
1. 설치
```
yarn add react react-dom
yarn add @types/react @types/react-dom -D
```

### 설치 후 
src폴더안에 index.html 작성
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>My app</title>
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
```
이후 같은위치에 index.tsx 생성
```
import React from "react";
import ReactDOM from "react-dom";

const App = () => <h1>My React and TypeScript App!</h1>;

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById("root")
);

```

### BABEL 
1. 설치
```
yarn add @babel/core @babel/preset-env @babel/preset-react @babel/preset-typescript @babel/plugin-transform-runtime @babel/runtime -D
```
2. Babel 설정파일 (.babelrc) 생성
```
{
  "presets": [
    "@babel/preset-env",
    "@babel/preset-react",
    "@babel/preset-typescript"
  ],
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "regenerator": true
      }
    ]
  ]
}
```

### TS-NODE
ts-node 는 TypeScript의 실행엔진이며,
TypeScript를 JavaScript 로 변환하여 미리 컴파일하지 않고도 Node.js 에서 TypeScript를 직접 실행할 수 있도록 도와준다.
1. 설치
```
yarn add ts-node -D
```
# **Routing(라우팅)**
- 호출되는 url에 따라 페이지 이동을 설정하는 것
- `react-router-dom`(패키지): BrowserRouter, Route, Link 기능을 제공한다
    - Route: 호출되는 url에 따라 이동할 component를 정의한다
    - Link: <a> 태그와 같이 페이지에 표시되는 링크를 클릭하면 url을 호출한다
    - BrowserRouter 태그로 감싸야 Route, Link를 사용할 수 있다
- 참조자료: 초보자를 위한 리액트 200제 p273

### 페이지 나누는 법(리액트 사용)

- 컴포넌트 만들어서 상세페이지 내용 채우기
- react-router-dom 라이브러리 설치 및 사용하기
    1. 터미널 `npm install react-router-dom@6`입력
    2. main.jsx 파일에 `<BrowserRouter>` 태그 추가
        
        ```jsx
        import React from "react";
        import ReactDOM from "react-dom/client";
        import App from "./App.jsx";
        import "./index.css";
        import { BrowserRouter } from "react-router-dom";
        
        ReactDOM.createRoot(document.getElementById("root")).render(
          <React.StrictMode>
            <BrowserRouter>
              <App />
            </BrowserRouter>
          </React.StrictMode>
        );
        ```
        
    3. App.jsx 파일에 Route `import`
        
        ```jsx
        import { Routes, Route, Link } from "react-router-dom";
        ```
        
    4. App.jsx에 상세페이지 코드 넣어보기
        
        ```jsx
        function App() {
          return (
            <div className="App">
              <Routes>
                <Route path="/detail" element={<div>상세페이지</div>} />
              </Routes>
        
        ```
        
    5. 페이지 나누기
        
        ```jsx
        <Route path="/" element={ 기존에 만들었던 코드 뭉치 삽입 } /> 
        ```
        
    6. 기존에 만든 코드 뭉치를 컴포넌트로 만들어서, 코드 간소화
        
        ```jsx
        <Routes>
        	 <Route path="/" element={<MainPage />} />
           <Route path="/detail" element={<DetailPage />} />
        </Routes>
        ```
        
    7. 페이지 이동버튼 만들기
        - `Link` 컴포넌트는 React 애플리케이션에서 페이지 간 네비게이션을 제공하는 데 사용
        - `to` 속성을 사용하여 이동할 경로를 지정
        
        ```jsx
        function App() {
          return (
            <div className="App">
              <Navbar className="navBar" data-bs-theme="dark">
                <Container>
                  <Navbar.Brand href="#home">OOTD</Navbar.Brand>
                  <Nav className="me-auto">
                    <Nav.Link href="#home">Home</Nav.Link>
                    <Nav.Link href="#features">Product</Nav.Link>
                    <Nav.Link href="#pricing">Info</Nav.Link>
                  </Nav>
                  {/* 페이지 이동 버튼 만들기 */}
                  ⭐️<Link to="/">홈</Link>
                  ⭐️<Link to="/detail">상세페이지</Link>
                </Container>
              </Navbar>
        
              <Routes> 
        ```

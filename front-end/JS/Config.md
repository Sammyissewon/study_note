## Config(**configuration)**

- 설정이라는 의미로, 소프트웨어 또는 시스템에서 설정 파일 또는 설정 객체를 의미한다. 다양한 설정 값을 저장하고, 프로그램이나 애플리케이션의 동작을 제어하는 데 사용
- 주로 json 형태로 많이 사용되며, .xml, .js, .config 등의 형태로도 사용할 수 있다

### Config의 주요 역할

1. 환경 설정관리: 개발환경, 테스트 환경, 운영 환경에 따라 다른 데이터베이스 접속 정보, API URL 등을 설정할 수 있다. 
2. 유연성 제공: 프로그램 소스 코드를 수정하지 않고도 설정 값을 변경할 수 있게 도와준다. 
3. 구성의 통합관리: 프로그램에 필요한 다양한 매개변수나 옵션들을 한 곳에서 관리할 수 있어 유지보수와 코드 관리가 용이하다다.

```javascript
import axios from "axios";

const API_BASE_URL = import.meta.env.VITE_API_BASE_URL || "";

const apiRequest = async (method, endpoint, data = {}, customHeaders = {}) => {
  const headers = {
    "Content-Type": "application/json",
    ...customHeaders,
  };

  const config = {
    method,
    url: `${API_BASE_URL}/api/${endpoint}`,
    headers,
    ...(method !== "GET" && { data }), // GET을 제외한 요청에서만 data를 포함
  };

  const response = await axios(config);
  return endpoint === "user/login" ? response : response.data;
};

// 메소드별 단축 함수
export const get = (endpoint, customHeaders) => 
  apiRequest("GET", endpoint, {}, customHeaders);

export const post = (endpoint, data, customHeaders) => 
  apiRequest("POST", endpoint, data, customHeaders);

export const put = (endpoint, data, customHeaders) => 
  apiRequest("PUT", endpoint, data, customHeaders);

export const deleteRequest = (endpoint, data, customHeaders) => 
  apiRequest("DELETE", endpoint, data, customHeaders);

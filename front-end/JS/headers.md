# Headers

- **HTTP 요청** 또는 **응답**에서 사용되는 메타데이터로, 클라이언트(웹 브라우저)와 서버 간에 **추가 정보를 전달**하는 데 사용됩니다.
- HTTP 헤더는 HTTP 메시지의 일부분으로, 요청이나 응답에 대한 다양한 세부 정보를 설명하는 역할을 합니다.

### HTTP 헤더의 역할

1. **클라이언트-서버 간의 정보 전달**: 클라이언트와 서버가 통신할 때, 필요한 정보(사용자 에이전트, 인증 토큰 등)를 전달하는 데 사용됩니다.
2. **데이터 형식과 인코딩 설정**: 전송되는 데이터의 형식, 압축 방식, 캐싱 정보 등을 포함하여 통신 환경을 최적화합니다.

### HTTP 요청 헤더(Request Headers)

클라이언트가 서버로 데이터를 요청할 때 추가적으로 포함하는 정보입니다. 요청 헤더는 **서버가 요청을 어떻게 처리해야 하는지**에 대한 정보를 제공합니다.

- **`Host`**: 요청하는 서버의 호스트 주소를 지정합니다.
- **`User-Agent`**: 클라이언트 애플리케이션(브라우저)의 정보(예: 브라우저 종류, 운영체제)입니다.
- **`Authorization`**: 서버가 보호된 리소스를 제공하기 위한 인증 정보(예: API 토큰, 사용자 이름/비밀번호)입니다.
- **`Accept`**: 클라이언트가 처리 가능한 MIME 타입을 서버에 전달합니다. 예를 들어, `Accept: application/json`은 JSON 응답을 기대함을 의미합니다.

### HTTP 응답 헤더(Response Headers)

서버가 클라이언트에게 응답할 때, 전송되는 데이터에 대한 정보를 포함합니다.

- **`Content-Type`**: 서버가 반환하는 데이터의 MIME 타입을 정의합니다. 예를 들어, `Content-Type: application/json`은 서버가 JSON 데이터를 반환함을 나타냅니다.
- **`Content-Length`**: 전송되는 응답 데이터의 크기를 나타냅니다.
- **`Set-Cookie`**: 서버가 클라이언트에게 **쿠키**를 설정하는 데 사용됩니다.
- **`Cache-Control`**: 클라이언트가 캐시 데이터를 사용할 수 있는 방법과 기간을 정의합니다.

### 중요한 헤더 종류

1. **일반 헤더(General Headers)**: 요청이나 응답에 모두 사용할 수 있으며, 메시지에 대한 일반적인 정보를 전달합니다. (예: `Cache-Control`, `Connection`)
2. **요청 헤더(Request Headers)**: 클라이언트가 서버로 요청을 보낼 때 사용하는 헤더입니다. (예: `Accept`, `Authorization`)
3. **응답 헤더(Response Headers)**: 서버가 클라이언트에게 응답을 보낼 때 사용하는 헤더입니다. (예: `Set-Cookie`, `Content-Type`)
4. **엔티티 헤더(Entity Headers)**: 요청 또는 응답 본문에 대한 메타데이터를 포함하는 헤더입니다. (예: `Content-Length`, `Content-Encoding`)

```javascript
const headers = {
  "Content-Type": "application/json",  // 기본 헤더로, JSON 형식의 데이터를 서버로 전송할 때 사용
  ...customHeaders,                    // 추가적인 헤더 정보를 병합
};
```
```javascript
const customHeaders = {
  Authorization: 'Bearer some_token',
};
apiRequest('GET', 'user/profile', {}, customHeaders);
```

# google_login

1. ```cloud.google.com/cloud-console/``` 사이트에 접속하여 로그인 후 새 프로젝트를 만든다
2. ```google people api```를 검색하여 사용한다
3. ```api 서비스```->```사용자 인증정보```->```동의 화면 구성```
4. ```userType "외부"```->```만들기```->```내용입력 저장```
5. ```범위 추가 또는 삭제```->```people api```->```저장 후 계속```
6. ```add user 테스트 사용자 추가```->```대시보드```
7. ```API 및 서비스``` -> ```사용자 인증정보```->```사용자 인증 정보 만들기``` -> ```API 키```
8. ```API 및 서비스``` -> ```사용자 인증정보```->```사용자 인증 정보 만들기``` -> ```OAuth 클라이언트 ID 웹 애플리케이션``` -> ```url 추가```  
(API 키, OAuth 2.0 클라이언트 ID키 복사)
9. content에 본인의 OAuth 2.0 클라이언트 ID넣기
```html
<head>
    <meta name ="google-signin-client_id" content="217755353555-3msma49ckq4fa47k0tg5tkshatcdh8c9.apps.googleusercontent.com">
    <script src="https://apis.google.com/js/platform.js?onload=init" async defer></script>
</head>
<body>
    <ul>
 <li id="GgCustomLogin">
  <a href="javascript:void(0)">
   <span>Login with Google</span>
  </a>
 </li>
</ul>
</body>
```
10. 
```js
function init() {
	gapi.load('auth2', function() {
		gapi.auth2.init();
		options = new gapi.auth2.SigninOptionsBuilder();
		options.setPrompt('select_account');
		options.setScope('email profile openid https://www.googleapis.com/auth/user.birthday.read');
		gapi.auth2.getAuthInstance().attachClickHandler('GgCustomLogin', options, onSignIn, onSignInFailure);
	})
}

function onSignIn(googleUser) {
	var access_token = googleUser.getAuthResponse().access_token
	$.ajax({
		url: 'https://people.googleapis.com/v1/people/me'
		, data: {personFields:'birthdays', key:'나의 api key', 'access_token': access_token}
		, method:'GET'
	})
	.done(function(e){.
		var profile = googleUser.getBasicProfile();
		console.log(profile)
	})
	.fail(function(e){
		console.log(e);
	})
}
function onSignInFailure(t){		
	console.log(t);
}
```
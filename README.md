# dreamnemo.github.com
# 임시정보


1. Initialize

		///
		/// 모듈을 초기화 한다.
		///
		/// @param jsonParam 초기화 및 모듈 전역에서 사용하는 속성값을 포함하는 Json 문자열
		/// @return 성공시 {"result": "true", "msg": ""},
		///               실패시 {"result": "false", "msg": "error message"}
		///
		/// @note jsonParam은 다음과 같은 형식을 갖는다.
		///	{"param": {"challenge": "b12345", "": "pkcs_sign"}}
		///
		char* initialize (const std::string& jsonParam)

1. Invoke

		///
		/// 모듈내의 함수를 호출한다.
		///
		/// @param reserved 윈도우 핸들 또는 nullptr
		/// @param jsonParam 명령어와 인자값으로 구성된 Json 문자열
		/// @return 성공시 {"result": "true", "msg": "json 형식의 결과 문자열"},
		///               실패시 {"result": "false", "msg": "error message"}
		///
		/// @todo 문자열의 형식을 정의할 것인가에 대한 고민이 필요하다.
		///
		/// @note jsonParam은 다음과 같은 형식을 갖는다.
		///	{"cmd": "login", "param": {"challenge": "b12345", "msg": "123456", "type": "pkcs_sign"}}
		///
		/// @note 결과 메시지는 다음과 같은 형식을 갖는다.
		///	{"result": "true", "msg": {"sign_value": "b12345", "cert_info": "123456", "mac_info": "b09876"}}
		///
		char* invoke (const void* reserved, const std::string& jsonParam)

1. Release
 
		///
		/// 모듈을 해제한다.
		///
		/// @return 성공시 {"result": "true", "msg": ""},
		///               실패시 {"result": "false", "msg": "error message"}
		///
		char* release ()


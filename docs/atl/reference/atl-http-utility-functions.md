---
title: ATL HTTP 유틸리티 함수
ms.date: 11/04/2016
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
ms.openlocfilehash: 8f26a23190f9358ff8913e35f5ed7274c8b274ea
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449969"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP 유틸리티 함수

이러한 함수에는 Url의 조작은 지원 합니다.

|||
|-|-|
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|안전 하지 않은 문자와 공백을 이스케이프 시퀀스로 변환 하는 URL을 canonicalizes입니다.|
|[AtlCombineUrl](#atlcombineurl)|기본 URL과 상대 URL을 단일 정규 URL을 결합합니다.|
|[AtlEscapeUrl](#atlescapeurl)|모든 안전 하지 않은 문자를 이스케이프 시퀀스로 변환 합니다.|
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|특정 인터넷 프로토콜 또는 체계를 사용 하 여 연결 된 기본 포트 번호를 가져옵니다.|
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|안전 하 게 URL에 사용할 문자 인지 확인 합니다.|
|[AtlUnescapeUrl](#atlunescapeurl)|이스케이프 된 문자를 원래 값으로 다시 변환 합니다.|
|[RGBToHtml](#rgbtohtml)|변환 된 [COLORREF](/windows/desktop/gdi/colorref) 를 색 값에 해당 하는 HTML 텍스트 값입니다.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|시스템 시간을 HTTP 헤더에서 사용하기에 적합한 형식의 문자열로 변환하려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

## <a name="atlcanonicalizeurl"></a> AtlCanonicalizeUrl

안전하지 않은 문자와 공백을 이스케이프 시퀀스로 변환하는 등 URL을 정식화하려면 이 함수를 호출합니다.

```cpp
inline BOOL AtlCanonicalizeUrl(
   LPCTSTR szUrl,
   LPTSTR szCanonicalized,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*szUrl*<br/>
정식화 될 URL입니다.

*szCanonicalized*<br/>
정규화 된 URL을 받으려면 호출자 할당 버퍼입니다.

*pdwMaxLength*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szCanonicalized*합니다. 함수가 성공 하면 변수는 null 종결 문자를 포함 하 여 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수의 null 종결 문자에 대 한 공간을 포함 하는 버퍼의 바이트 길이 받게 됩니다.

*dwFlags*<br/>
이 함수의 동작을 제어 하는 ATL_URL 플래그입니다.

- 인코딩 또는 "#" 뒤에 문자를 디코딩할 ATL_URL_BROWSER_MODE 않습니다 또는 "?", 후 후행 공백을 제거 하지 않는 "?"입니다. 이 값을 지정 하지 않으면 전체 URL 인코딩 되 고 후행 공백이 제거 됩니다.

- ATL_URL_DECODE 자로 된 URL을 구문 분석 전에 이스케이프 시퀀스를 포함 하 여 모든 %XX 시퀀스를 변환 합니다.

- 모든 백분율 기호 발생 ATL_URL_ENCODE_PERCENT 인코딩합니다. 기본적으로 백분율 기호는 인코딩되지 않습니다.

- ATL_URL_ENCODE_SPACES_ONLY 인코딩합니다 공간만 합니다.

- ATL_URL_ESCAPE 변환 해당 문자를 모두 이스케이프 시퀀스 (%XX).

- 안전 하지 않은 문자를 이스케이프 시퀀스로 변환 하지 ATL_URL_NO_ENCODE 않습니다.

- ATL_URL_NO_META에서는 meta 시퀀스를 제거 하지 않습니다 (같은 "."및"..") URL에서 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

현재 버전 처럼 [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla) 하지만 WinInet 또는 Internet Explorer를 설치할 필요는 없습니다.

## <a name="atlcombineurl"></a> AtlCombineUrl

기본 URL과 상대 URL을 단일 정규 URL로 결합하려면 이 함수를 호출합니다.

```cpp
inline BOOL AtlCombineUrl(
   LPCTSTR szBaseUrl,
   LPCTSTR szRelativeUrl,
   LPTSTR szBuffer,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*szBaseUrl*<br/>
기본 URL입니다.

*szRelativeUrl*<br/>
기본 URL에 상대적인 URL입니다.

*szBuffer*<br/>
정규화 된 URL을 받으려면 호출자 할당 버퍼입니다.

*pdwMaxLength*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szBuffer*합니다. 함수가 성공 하면 변수는 null 종결 문자를 포함 하 여 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수의 null 종결 문자에 대 한 공간을 포함 하는 버퍼의 바이트 길이 받게 됩니다.

*dwFlags*<br/>
이 함수의 동작을 제어 하는 플래그입니다. 참조 [AtlCanonicalizeUrl](#atlcanonicalizeurl)합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

현재 버전 처럼 [InternetCombineUrl](/windows/desktop/api/wininet/nf-wininet-internetcombineurla) 하지만 WinInet 또는 Internet Explorer를 설치할 필요는 없습니다.

## <a name="atlescapeurl"></a> AtlEscapeUrl

모든 안전하지 않은 문자를 이스케이프 시퀀스로 변환하려면 이 함수를 호출합니다.

```cpp
inline BOOL AtlEscapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();

inline BOOL AtlEscapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*lpszStringIn*<br/>
변환할 URL입니다.

*lpszStringOut*<br/>
변환 된 URL을 쓸 호출자 할당 버퍼입니다.

*pdwStrLen*<br/>
DWORD 변수에 대 한 포인터입니다. 함수가 성공 하면 *pdwStrLen* null 종결 문자를 포함 하는 버퍼에 기록 된 문자 수를 받습니다. 함수가 실패할 경우 변수의 null 종결 문자에 대 한 공간을 포함 하는 버퍼의 바이트 길이 받게 됩니다. 이 메서드의 와이드 문자 버전을 사용 하면 *pdwStrLen* 문자의 수를 필요한 바이트 수가 아니라 수신 합니다.

*dwMaxLength*<br/>
버퍼의 크기 *lpszStringOut*합니다.

*dwFlags*<br/>
이 함수의 동작을 제어 하는 ATL_URL 플래그입니다. 참조 [ATLCanonicalizeUrl](#atlcanonicalizeurl) 가능한 값에 대 한 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort

특정 인터넷 프로토콜 또는 체계와 관련된 기본 포트 번호를 가져오려면 이 함수를 호출합니다.

```
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();
```

### <a name="parameters"></a>매개 변수

*m_nScheme*<br/>
합니다 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 포트 번호를 가져오려면 원하는 구성표를 식별 하는 값입니다.

### <a name="return-value"></a>반환 값

합니다 [ATL_URL_PORT](atl-typedefs.md#atl_url_port) 스키마가 인식 되지 않으면 ATL_URL_INVALID_PORT_NUMBER에 지정 된 스키마와 연결 합니다.

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar

URL에서 문자를 안전하게 사용할 수 있는지 확인하려면 이 함수를 호출합니다.

```
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();
```

### <a name="parameters"></a>매개 변수

*chIn*<br/>
안전을 위해 테스트할 문자입니다.

### <a name="return-value"></a>반환 값

입력된 문자 인지 안전 하지 않은, FALSE 그렇지 않은 경우 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

문자를 Url에 사용할 수는이 함수를 사용 하 여 테스트할 수 있습니다 하 고 사용 하 여 변환 [AtlCanonicalizeUrl](#atlcanonicalizeurl)합니다.

## <a name="atlunescapeurl"></a> AtlUnescapeUrl

이스케이프된 문자를 원래 값으로 다시 변환하려면 이 함수를 호출합니다.

```cpp
inline BOOL AtlUnescapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();

inline BOOL AtlUnescapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();
```

### <a name="parameters"></a>매개 변수

*lpszStringIn*<br/>
변환할 URL입니다.

*lpszStringOut*<br/>
변환 된 URL을 쓸 호출자 할당 버퍼입니다.

*pdwStrLen*<br/>
DWORD 변수에 대 한 포인터입니다. 함수가 성공 하면 변수는 null 종결 문자를 포함 하 여 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수의 null 종결 문자에 대 한 공간을 포함 하는 버퍼의 바이트 길이 받게 됩니다.

*dwMaxLength*<br/>
버퍼의 크기 *lpszStringOut*합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

적용 하 여 변환 프로세스를 반대로 [AtlEscapeUrl](#atlescapeurl)합니다.

## <a name="rgbtohtml"></a> RGBToHtml

변환 된 [COLORREF](/windows/desktop/gdi/colorref) 를 색 값에 해당 하는 HTML 텍스트 값입니다.

```cpp
bool inline RGBToHtml(
   COLORREF color,
   LPTSTR pbOut,
   long nBuffer);
```

### <a name="parameters"></a>매개 변수

*color*<br/>
RGB 색 값입니다.

*pbOut*<br/>
HTML 색 값에 대 한 텍스트를 받으려면 호출자 할당 버퍼입니다. 버퍼 공간이 해야 null 종결자를 위한 공간이 포함 하 여 적어도 8 자).

*nBuffer*<br/>
(Null 종결자를 위한 공간이 포함)는 버퍼의 바이트 크기입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

HTML 색 값은 2 자리를 사용 하 여 각 색의 빨강, 녹색 및 파랑 구성 요소에 대 한 6 자리 16 진수 값 뒤에 파운드 기호 (예를 들어 #FFFFFF 흰색인).

## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate

시스템 시간을 HTTP 헤더에서 사용하기에 적합한 형식의 문자열로 변환하려면 이 함수를 호출합니다.

```cpp
inline void SystemTimeToHttpDate(
   const SYSTEMTIME& st,
   CStringA& strTime);
```

### <a name="parameters"></a>매개 변수

*st*<br/>
HTTP 형식 문자열로 가져올 시스템 시간입니다.

*strTime*<br/>
RFC 2616에 정의 된 대로 HTTP 날짜 시간을 수신 하는 문자열 변수에 대 한 참조 ([https://www.ietf.org/rfc/rfc2616.txt](https://www.ietf.org/rfc/rfc2616.txt)) 및 RFC 1123 ([https://www.ietf.org/rfc/rfc1123.txt](https://www.ietf.org/rfc/rfc1123.txt)).

## <a name="see-also"></a>참고자료

[개념](../active-template-library-atl-concepts.md)<br/>
[ATL COM 데스크톱 구성 요소](../atl-com-desktop-components.md)<br/>
[InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla)

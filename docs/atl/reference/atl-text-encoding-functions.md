---
title: ATL 텍스트 인코딩 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
ms.openlocfilehash: 13c521bae6790a030212c4a8edac460c960ecfc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247866"
---
# <a name="atl-text-encoding-functions"></a>ATL 텍스트 인코딩 함수

이러한 함수는 텍스트 인코딩 및 디코딩을 지원 합니다.

|||
|-|-|
|[AtlGetHexValue](#atlgethexvalue)|16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.|
|[AtlGetVersion](#atlgetversion)|사용 중인 ATL 라이브러리의 버전을 가져오려면이 함수를 호출 합니다.  |
|[AtlHexDecode](#atlhexdecode)|에 대 한 이전 호출에서와 같이 16 진수 텍스트로 인코딩된 데이터의 문자열을 디코딩합니다 [AtlHexEncode](#atlhexencode)합니다.|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|지정된 길이의 16진수로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.|
|[AtlHexEncode](#atlhexencode)|16진수 텍스트 문자열로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[AtlHexValue](#atlhexvalue)|16진수의 숫자 값을 가져오려면 이 함수를 호출합니다. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|유니코드 문자열을 UTF-8로 변환하려면 이 함수를 호출합니다. |
|[BEncode](#bencode)|"B" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.|
|[BEncodeGetRequiredLength](#bencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[EscapeXML](#escapexml)|XML에서 사용하기에 안전하지 않은 문자를 안전한 문자로 변환하려면 이 함수를 호출합니다.|
|[GetExtendedChars](#getextendedchars)|문자열에서 확장된 문자 수를 가져오려면 이 함수를 호출합니다.|
|[IsExtendedChar](#isextendedchar)|지정한 문자가 확장된 문자(32보다 작거나 126보다 크고 탭, 줄 바꿈 또는 캐리지 리턴이 아님)인지 확인하려면 이 함수를 호출합니다.|
|[QEncode](#qencode)|"Q" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[QPDecode](#qpdecode)|에 대 한 이전 호출에서 같이 quoted-printable 형식으로 인코딩된 데이터의 문자열을 디코딩합니다 [QPEncode](#qpencode)합니다.|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|지정된 길이의 quoted-printable로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.|
|[QPEncode](#qpencode)|quoted-printable 형식으로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[UUDecode](#uudecode)|에 대 한 이전 호출에서와 같이 uuencode 된 데이터의 문자열을 디코딩합니다 [UUEncode](#uuencode)합니다.|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|지정된 길이의 uuencode된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.|
|[UUEncode](#uuencode)|일부 데이터를 uuencode하려면 이 함수를 호출합니다. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlenc.h의

## <a name="atlgethexvalue"></a> AtlGetHexValue

16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.

```
inline char AtlGetHexValue(char chIn) throw();
```

### <a name="parameters"></a>매개 변수

*chIn*<br/>
16 진수 문자 '0'-'9', 'A'-'F' 또는 'a'-'f'입니다.

### <a name="return-value"></a>반환 값

입력 문자의 숫자 값을 16 진수 자리 수로 해석 합니다. 예를 들어, '0'의 입력 값이 0 반환 하 고 'A'의 입력 값이 10 반환 합니다. 16 진수 입력된 문자가 없는 경우이 함수는-1을 반환 합니다.

## <a name="atlgetversion"></a> AtlGetVersion

사용 중인 ATL 라이브러리의 버전을 가져오려면이 함수를 호출 합니다.

```
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);
```

### <a name="parameters"></a>매개 변수

*pReserved*<br/>
예약 된 포인터입니다.

### <a name="return-value"></a>반환 값

ATL 라이브러리 컴파일 또는 실행 중인 버전의 DWORD 정수 값을 반환 합니다.

## <a name="example"></a>예제

함수는 다음과 같이 호출 되어야 합니다.

[!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlhexdecode"></a> AtlHexDecode

에 대 한 이전 호출에서와 같이 16 진수 텍스트로 인코딩된 데이터의 문자열을 디코딩합니다 [AtlHexEncode](#atlhexencode)합니다.

```
inline BOOL AtlHexDecode(
   LPCSTR pSrcData,
   int nSrcLen,
   LPBYTE pbDest,
   int* pnDestLen) throw();
```

### <a name="parameters"></a>매개 변수

*pSrcData*<br/>
디코딩할 데이터가 포함 된 문자열입니다.

*nSrcLen*<br/>
문자에서 길이 *pSrcData*합니다.

*pbDest*<br/>
디코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
길이 (바이트) 포함 하는 변수에 대 한 포인터 *pbDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 바이트 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 바이트 길이 받게 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength

지정된 길이의 16진수로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.

```
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 문자열의 문자 수입니다.

### <a name="return-value"></a>반환 값

디코딩된 문자열을 포함할 수 있는 버퍼에 대 한 필요한 바이트 수가 *nSrcLen* 문자입니다.

## <a name="atlhexencode"></a> AtlHexEncode

16진수 텍스트 문자열로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.

```
inline BOOL AtlHexEncode(
   const BYTE * pbSrcData,
   int nSrcLen,
   LPSTR szDest,
int * pnDestLen) throw();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
인코딩된 데이터를 포함 하는 버퍼입니다.

*nSrcLen*<br/>
인코딩된 데이터의 길이 (바이트)에서입니다.

*szDest*<br/>
인코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 문자에서 길이 수신 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

원본 데이터의 각 바이트는 16 진수 문자를 2로 인코딩됩니다.

## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength

지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.

```
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 데이터의 바이트 수입니다.

### <a name="return-value"></a>반환 값

인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 *nSrcLen* 바이트입니다.

## <a name="atlhexvalue"></a> AtlHexValue

16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.

```
inline short AtlHexValue(char chIn) throw();
```

### <a name="parameters"></a>매개 변수

*chIn*<br/>
16 진수 문자 '0'-'9', 'A'-'F' 또는 'a'-'f'입니다.

### <a name="return-value"></a>반환 값

입력 문자의 숫자 값을 16 진수 자리 수로 해석 합니다. 예를 들어, '0'의 입력 값이 0 반환 하 고 'A'의 입력 값이 10 반환 합니다. 16 진수 입력된 문자가 없는 경우이 함수는-1을 반환 합니다.

## <a name="atlunicodetoutf8"></a> AtlUnicodeToUTF8

유니코드 문자열을 UTF-8로 변환하려면 이 함수를 호출합니다.

```
ATL_NOINLINE inline int AtlUnicodeToUTF8(
   LPCWSTR wszSrc,
   int nSrc,
   LPSTR szDest,
   int nDest) throw();
```

### <a name="parameters"></a>매개 변수

*wszSrc*<br/>
변환할 유니코드 문자열

*nSrc*<br/>
유니코드 문자열의 문자 길이입니다.

*szDest*<br/>
변환된 된 문자열을 받으려면 호출자 할당 버퍼입니다.

*nDest*<br/>
버퍼의 길이 (바이트)에서입니다.

### <a name="return-value"></a>반환 값

변환 된 문자열의 문자 수를 반환합니다.

### <a name="remarks"></a>설명

변환된 된 문자열에 필요한 버퍼의 크기를 확인 하려면에 대 한 0을 전달 합니다.이 함수를 호출 *szDest* 하 고 *nDest*합니다.

## <a name="bencode"></a> BEncode

"B" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.

```
inline BOOL BEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCSTR pszCharSet) throw();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
인코딩된 데이터를 포함 하는 버퍼입니다.

*nSrcLen*<br/>
인코딩된 데이터의 길이 (바이트)에서입니다.

*szDest*<br/>
인코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 문자에서 길이 수신 합니다.

*pszCharSet*<br/>
문자 집합을 변환 하는 데 사용 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

RFC 2047에 설명 된 "B" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength

지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.

```
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 데이터의 바이트 수입니다.

*nCharsetLen*<br/>
변환에 대해 사용 하도록 설정 된 문자의 문자 길이입니다.

### <a name="return-value"></a>반환 값

인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 *nSrcLen* 바이트입니다.

### <a name="remarks"></a>설명

RFC 2047에 설명 된 "B" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="escapexml"></a> EscapeXML

XML에서 사용하기에 안전하지 않은 문자를 안전한 문자로 변환하려면 이 함수를 호출합니다.

```
inline int EscapeXML(
   const wchar_t * szIn,
   int nSrcLen,
   wchar_t * szEsc,
   int nDestLen,
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();
```

### <a name="parameters"></a>매개 변수

*szIn*<br/>
변환할 문자열입니다.

*nSrclen*<br/>
변환할 문자열의 문자 길이입니다.

*szEsc*<br/>
변환된 된 문자열을 받으려면 호출자 할당 버퍼입니다.

*nDestLen*<br/>
호출자 할당 버퍼의 문자 길이입니다.

*dwFlags*<br/>
변환을 수행 하는 하는 방법을 설명 하는 ATL_ESC 플래그입니다.

- ATL_ESC_FLAG_NONE 기본 동작입니다. 인용 부호 및 아포스트로피 변환 되지 않습니다.
- ATL_ESC_FLAG_ATTR 인용 부호 및 아포스트로피 변환할 `&quot;` 고 `&apos;` 각각.

### <a name="return-value"></a>반환 값

변환된 된 문자열의 문자 길이입니다.

### <a name="remarks"></a>설명

이 함수에 의해 수행 되는 가능한 변환 테이블에 나와 있습니다.

|Source|대상|
|------------|-----------------|
|\<|&lt;|
|>|&gt;|
|&|&amp;|
|'|&apos;|
|"|&quot;|

## <a name="getextendedchars"></a> GetExtendedChars

문자열에서 확장된 문자 수를 가져오려면 이 함수를 호출합니다.

```
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();
```

### <a name="parameters"></a>매개 변수

*szSrc*<br/>
분석할 문자열입니다.

*nSrcLen*<br/>
문자에서 문자열의 길이입니다.

### <a name="return-value"></a>반환 값

기준으로 하는 문자열 내에 있는 확장 된 문자 수를 반환 [IsExtendedChar](#isextendedchar)합니다.

## <a name="isextendedchar"></a> IsExtendedChar

지정한 문자가 확장된 문자(32보다 작거나 126보다 크고 탭, 줄 바꿈 또는 캐리지 리턴이 아님)인지 확인하려면 이 함수를 호출합니다.

```
inline int IsExtendedChar(char ch) throw();
```

### <a name="parameters"></a>매개 변수

*ch*<br/>
테스트할 문자

### <a name="return-value"></a>반환 값

문자 연장 되 면 TRUE, FALSE 그렇지 않은 경우.

## <a name="qencode"></a> QEncode

"Q" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.

```
inline BOOL QEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCSTR pszCharSet,
   int* pnNumEncoded = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
인코딩된 데이터를 포함 하는 버퍼입니다.

*nSrcLen*<br/>
인코딩된 데이터의 길이 (바이트)에서입니다.

*szDest*<br/>
인코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 문자에서 길이 수신 합니다.

*pszCharSet*<br/>
문자 집합을 변환 하는 데 사용 합니다.

*pnNumEncoded*<br/>
반환 시 변환 하는 안전 하지 않은 문자 수를 포함 하는 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

RFC 2047에 설명 된 "Q" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength

지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.

```
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 데이터의 바이트 수입니다.

*nCharsetLen*<br/>
변환에 대해 사용 하도록 설정 된 문자의 문자 길이입니다.

### <a name="return-value"></a>반환 값

인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 *nSrcLen* 바이트입니다.

### <a name="remarks"></a>설명

RFC 2047에 설명 된 "Q" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="qpdecode"></a> QPDecode

에 대 한 이전 호출에서 같이 quoted-printable 형식으로 인코딩된 데이터의 문자열을 디코딩합니다 [QPEncode](#qpencode)합니다.

```
inline BOOL QPDecode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
[in] 디코딩할 데이터를 포함 하는 버퍼입니다.

*nSrcLen*<br/>
[in] 바이트 길이 *pbSrcData*합니다.

*szDest*<br/>
[out] 디코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
[out] 길이 (바이트) 포함 하는 변수에 대 한 포인터 *szDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 바이트 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 바이트 길이 받게 됩니다.

*dwFlags*<br/>
[in] 변환을 수행 하는 하는 방법을 설명 하는 ATLSMTP_QPENCODE 플래그입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

따옴표 붙은 인쇄 가능한 인코딩 체계 RFC 2045에 설명 된 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength

지정된 길이의 quoted-printable로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.

```
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 문자열의 문자 수입니다.

### <a name="return-value"></a>반환 값

디코딩된 문자열을 포함할 수 있는 버퍼에 대 한 필요한 바이트 수가 *nSrcLen* 문자입니다.

### <a name="remarks"></a>설명

따옴표 붙은 인쇄 가능한 인코딩 체계 RFC 2045에 설명 된 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="qpencode"></a> QPEncode

quoted-printable 형식으로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.

```
inline BOOL QPEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   DWORD dwFlags = 0) throw ();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
인코딩된 데이터를 포함 하는 버퍼입니다.

*nSrcLen*<br/>
인코딩된 데이터의 길이 (바이트)에서입니다.

*szDest*<br/>
인코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 문자에서 길이 수신 합니다.

*dwFlags*<br/>
변환을 수행 하는 하는 방법을 설명 하는 ATLSMTP_QPENCODE 플래그입니다.

- 줄의 시작 부분에 잠시 나타납니다 ATLSMTP_QPENCODE_DOT 경우, 것은 출력을 추가할 뿐만 아니라 인코딩.

- ATLSMTP_QPENCODE_TRAILING_SOFT 추가 `=\r\n` 인코딩된 문자열입니다.

따옴표 붙은 인쇄 가능한 인코딩 체계에 설명 되어 [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt)합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

따옴표 붙은 인쇄 가능한 인코딩 체계 RFC 2045에 설명 된 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength

지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.

```
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 데이터의 바이트 수입니다.

### <a name="return-value"></a>반환 값

인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 *nSrcLen* 바이트입니다.

### <a name="remarks"></a>설명

따옴표 붙은 인쇄 가능한 인코딩 체계 RFC 2045에 설명 된 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="uudecode"></a> UUDecode

에 대 한 이전 호출에서와 같이 uuencode 된 데이터의 문자열을 디코딩합니다 [UUEncode](#uuencode)합니다.

```
inline BOOL UUDecode(
   BYTE* pbSrcData,
   int nSrcLen,
   BYTE* pbDest,
   int* pnDestLen) throw ();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
디코딩할 데이터가 포함 된 문자열입니다.

*nSrcLen*<br/>
바이트 길이 *pbSrcData*합니다.

*pbDest*<br/>
디코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
길이 (바이트) 포함 하는 변수에 대 한 포인터 *pbDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 바이트 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 바이트 길이 받게 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 uuencoding 구현 POSIX P1003.2b/D11 사양을 따릅니다.

## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength

지정된 길이의 uuencode된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.

```
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 문자열의 문자 수입니다.

### <a name="return-value"></a>반환 값

디코딩된 문자열을 포함할 수 있는 버퍼에 대 한 필요한 바이트 수가 *nSrcLen* 문자입니다.

### <a name="remarks"></a>설명

이 uuencoding 구현 POSIX P1003.2b/D11 사양을 따릅니다.

## <a name="uuencode"></a> UUEncode

일부 데이터를 uuencode하려면 이 함수를 호출합니다.

```
inline BOOL UUEncode(
   const BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCTSTR lpszFile = _T("file"),
   DWORD dwFlags = 0) throw ();
```

### <a name="parameters"></a>매개 변수

*pbSrcData*<br/>
인코딩된 데이터를 포함 하는 버퍼입니다.

*nSrcLen*<br/>
인코딩된 데이터의 길이 (바이트)에서입니다.

*szDest*<br/>
인코딩된 데이터를 받는 호출자 할당 버퍼입니다.

*pnDestLen*<br/>
문자에서 길이 포함 하는 변수에 대 한 포인터 *szDest*합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자의 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 문자에서 길이 수신 합니다.

*lpszFile*<br/>
ATLSMTP_UUENCODE_HEADER이 지정 된 경우 헤더에 추가할 파일 *dwFlags*합니다.

*dwFlags*<br/>
이 함수의 동작을 제어 하는 플래그입니다.

- 헤더 ATLSMTP_UUENCODE_HEADE가 인코드됩니다.

- 끝 ATLSMTP_UUENCODE_END가 인코드됩니다.

- ATLSMTP_UUENCODE_DOT 데이터 오해의 소지가 수행 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 uuencoding 구현 POSIX P1003.2b/D11 사양을 따릅니다.

## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength

지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.

```
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>매개 변수

*nSrcLen*<br/>
인코딩된 데이터의 바이트 수입니다.

### <a name="return-value"></a>반환 값

인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 *nSrcLen* 바이트입니다.

### <a name="remarks"></a>설명

이 uuencoding 구현 POSIX P1003.2b/D11 사양을 따릅니다.

## <a name="see-also"></a>참고자료

[개념](../active-template-library-atl-concepts.md)<br/>
[ATL COM 데스크톱 구성 요소](../atl-com-desktop-components.md)

---
title: _strdec, _wcsdec, _mbsdec, _mbsdec_l
ms.date: 11/04/2016
apiname:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdec
- mbsdec_l
- strdec
- _mbsdec
- _mbsdec_l
- mbsdec
- wcsdec
- _wcsdec
helpviewer_keywords:
- mbsdec_l function
- mbsdec function
- tcsdec function
- _tcsdec function
- _strdec function
- _wcsdec function
- _mbsdec_l function
- strdec function
- wcsdec function
- _mbsdec function
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
ms.openlocfilehash: 7e88bcf5bf7ffc5eba6feecd545cda8f7950829c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353891"
---
# <a name="strdec-wcsdec-mbsdec-mbsdecl"></a>_strdec, _wcsdec, _mbsdec, _mbsdec_l

문자열 포인터를 한 문자 뒤로 이동합니다.

> [!IMPORTANT]
> **mbsdec** 하 고 **mbsdec_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
unsigned char *_strdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned wchar_t *_wcsdec(
   const unsigned wchar_t *start,
   const unsigned wchar_t *current
);
unsigned char *_mbsdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned char *_mbsdec_l(
   const unsigned char *start,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*start*<br/>
모든 문자에 대 한 포인터 (또는 **_mbsdec** 하 고 **_mbsdec_l**, 모든 멀티 바이트 문자의 첫 번째 바이트) 소스 문자열에서는 *시작* 앞에 야 *현재* 소스 문자열에서입니다.

*current*<br/>
모든 문자에 대 한 포인터 (또는 **_mbsdec** 하 고 **_mbsdec_l**, 모든 멀티 바이트 문자의 첫 번째 바이트) 소스 문자열에서는 *현재* 따라야 *시작* 소스 문자열에서입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbsdec**, **_mbsdec_l**합니다 **_strdec**, 및 **_wcsdec** 바로 앞에 오는 문자에 대 한 포인터를 반환할 각 *현재*; **_mbsdec** 반환 **NULL** 하는 경우의 값 *시작* 보다 크거나과 동일한 지 *현재*합니다. **_tcsdec** 이러한 함수 및 해당 반환 값 중 하나에 매핑되며 매핑에 따라 달라 집니다.

## <a name="remarks"></a>설명

합니다 **_mbsdec** 하 고 **_mbsdec_l** 함수는 바로 앞에 오는 멀티 바이트 문자의 첫 번째 바이트에 대 한 포인터를 반환 합니다. *현재* 포함 된 문자열에서 *시작*합니다.

출력 값의 설정이 적용 됩니다는 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 자세한 내용은 합니다.  **_mbsdec** 현재 사용 중인 로캘에 따라 멀티 바이트 문자 시퀀스를 인식 하는 동안 **_mbsdec_l** 대신 전달 된 로캘 매개 변수를 사용 하 여 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

하는 경우 *시작* 또는 *현재* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 합니다 **EINVAL** 집합과 **errno** 하 **EINVAL**합니다.

> [!IMPORTANT]
> 이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다. 버퍼 오버런은 불필요한 권한 상승을 발생시킬 수 있으므로 시스템 공격에 사용될 수 있습니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsdec**|**_strdec**|**_mbsdec**|**_wcsdec**|

**_strdec** 하 고 **_wcsdec** 싱글바이트 문자 및 와이드 문자 버전입니다 **_mbsdec** 하 고 **_mbsdec_l**합니다. **_strdec** 하 고 **_wcsdec** 이러한 매핑을 위해서만 제공 되 고 그렇지 않으면 사용할 수 없습니다.

자세한 내용은 [일반 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [일반 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_mbsdec**|\<mbstring.h>|\<mbctype.h>|
|**_mbsdec_l**|\<mbstring.h>|\<mbctype.h>|
|**_strdec**|\<tchar.h>||
|**_wcsdec**|\<tchar.h>||

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

다음 예제는 사용 방법을 보여 줍니다 **_tcsdec**합니다.

```cpp
// crt_tcsdec.cpp
// Compile by using: cl /EHsc crt_tcsdec.cpp
#include <iostream>
#include <tchar.h>
using namespace std;

int main()
{
   const TCHAR *str = _T("12345");
   cout << "str: " << str << endl;

   const TCHAR *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   TCHAR *answer;
   answer = _tcsdec( str, str2 );
   cout << "answer: " << answer << endl;

   return (0);
}
```

다음 예제는 사용 방법을 보여 줍니다 **_mbsdec**합니다.

```cpp
// crt_mbsdec.cpp
// Compile by using: cl /EHsc crt_mbsdec.c
#include <iostream>
#include <mbstring.h>
using namespace std;

int main()
{
   char *str = "12345";
   cout << "str: " << str << endl;

   char *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   unsigned char *answer;
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));

   cout << "answer: " << answer << endl;

   return (0);
}
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>

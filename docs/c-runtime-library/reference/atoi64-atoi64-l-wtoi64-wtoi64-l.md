---
title: _atoi64, _atoi64_l, _wtoi64, _wtoi64_l
ms.date: 11/04/2016
api_name:
- _atoi64_l
- _wtoi64
- _atoi64
- _wtoi64_l
api_location:
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _atoi64
- _tstoi64
- _ttoi64
- wtoi64
- _tstoi64_l
- atoi64
- _wtoi64_l
- _wtoi64
- wtoi64_l
- _atoi64_l
- atoi64_l
helpviewer_keywords:
- tstoi64 function
- wtoi64 function
- atoi64_l function
- _ttoi64 function
- string conversion, to integers
- wtoi64_l function
- atoi64 function
- _tstoi64 function
- _atoi64_l function
- _wtoi64_l function
- ttoi64 function
- _wtoi64 function
- _atoi64 function
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
ms.openlocfilehash: 950774e74462e8d1f301a1d5b933e57feaa9f840
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939491"
---
# <a name="_atoi64-_atoi64_l-_wtoi64-_wtoi64_l"></a>_atoi64, _atoi64_l, _wtoi64, _wtoi64_l

문자열을 64비트 정수로 변환합니다.

## <a name="syntax"></a>구문

```C
__int64 _atoi64(
   const char *str
);
__int64 _wtoi64(
   const wchar_t *str
);
__int64 _atoi64_l(
   const char *str,
   _locale_t locale
);
__int64 _wtoi64_l(
   const wchar_t *str,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
변환할 문자열입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

각 함수는 입력 문자를 숫자로 해석 하 여 생성 된 **__int64** 값을 반환 합니다. 입력을 해당 형식의 값으로 변환할 수 없는 경우 반환 값은 **_atoi64** 의 경우 0입니다.

큰 양의 정수 값을 사용 하는 오버플로의 경우 **_atoi64** 는 큰 음의 정수 값을 사용 하는 오버플로의 경우 **I64_MAX** 및 **I64_MIN** 를 반환 합니다.

범위를 벗어난 모든 경우에는 **errno** 가 **ERANGE**로 설정 됩니다. 전달 된 매개 변수가 **NULL**인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우 이러한 함수는 **errno** 를 **EINVAL** 로 설정 하 고 0을 반환 합니다.

## <a name="remarks"></a>설명

이러한 함수는 문자열을 64비트 정수 값으로 변환합니다.

입력 문자열은 지정된 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다. 함수는 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중지합니다. 이 문자는 문자열을 종결하는 null 문자('\0' 또는 L'\0')일 수 있습니다.

**_Atoi64** 에 대 한 *str* 인수는 다음과 같은 형식입니다.

> [*whitespace*] [*sign*] [*digits*]

공백은 무시 되는 공백 또는 탭 *문자로 구성 됩니다* . *sign* 은 더하기 (+) 또는 빼기 (-) 중 하나입니다. *숫자* 는 하나 이상의 숫자입니다.

**_wtoi64** 는 와이드 문자열을 매개 변수로 사용 한다는 점을 제외 하 고 **_wtoi64** 와 동일 합니다.

**_L** 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoi64**|**_atoi64**|**_atoi64**|**_wtoi64**|
|**_ttoi64**|**_atoi64**|**_atoi64**|**_wtoi64**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|--------------|---------------------|
|**_atoi64**, **_atoi64_l**|\<stdlib.h>|
|**_wtoi64**, **_wtoi64_l**|\<stdlib.h> 또는 \<wchar.h>|

## <a name="example"></a>예제

이 프로그램은 **_atoi64** 함수를 사용 하 여 문자열로 저장 된 숫자를 숫자 값으로 변환할 수 있는 방법을 보여 줍니다.

```C
// crt_atoi64.c
// This program shows how numbers stored as
// strings can be converted to numeric values
// using the _atoi64 functions.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    __int64 value = 0;

    // An example of the _atoi64 function
    // with leading and trailing white spaces.
    str = "  -2309 ";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );

    // Another example of the _atoi64 function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );

    // Another example of the _atoi64 function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: _atoi64( "  -2309 " ) = -2309
Function: _atoi64( "314127.64" ) = 314127
Function: _atoi64( "3336402735171707160320" ) = -1
Overflow condition occurred.
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>

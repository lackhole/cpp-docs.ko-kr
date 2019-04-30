---
title: atoll, _atoll_l, _wtoll, _wtoll_l
ms.date: 11/04/2016
apiname:
- _wtoll
- _atoll_l
- _wtoll_l
- atoll
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tstoll_l
- _wtoll
- _atoll_l
- _ttoll
- _tstoll
- _wtoll_l
- atoll
helpviewer_keywords:
- atoll function
- _wtoll_l function
- _wtoll function
- _atoll_l function
ms.assetid: 5e85fcac-b351-4882-bff2-6e7c469b7fa8
ms.openlocfilehash: 7933b3e25185b5abdbd10c1b3fd616742bb28f92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341186"
---
# <a name="atoll-atolll-wtoll-wtolll"></a>atoll, _atoll_l, _wtoll, _wtoll_l

문자열을 변환 합니다는 **긴** **긴** 정수입니다.

## <a name="syntax"></a>구문

```C
long long atoll(
   const char *str
);
long long _wtoll(
   const wchar_t *str
);
long long _atoll_l(
   const char *str,
   _locale_t locale
);
long long _wtoll_l(
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

각 함수가 반환 하는 **긴** **긴** 입력된 문자를 숫자로 해석 하 여 생성 되는 값입니다. 반환 값 **산호 섬** 0 경우 입력 값이 해당 형식으로 변환할 수 없습니다.

큰 양의 정수 값을 사용 하 여 오버플로 **산호 섬** 반환 **LLONG_MAX**, 큰 음의 정수 값을 사용 하 여 오버플로 대 한 반환 **LLONG_MIN**합니다.

모든 범위를 벗어난 경우에 **errno** 로 설정 된 **ERANGE**합니다. 전달 된 매개 변수가 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 0을 반환 합니다.

## <a name="remarks"></a>설명

이러한 함수는 문자열을 변환 된 **긴** **긴** 정수 값입니다.

입력 문자열은 지정된 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다. 함수는 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중지합니다. 이 문자는 문자열을 종결하는 null 문자('\0' 또는 L'\0')일 수 있습니다.

합니다 *str* 인수를 **산호 섬** 다음과 같은 형식을 갖습니다.

> [*whitespace*] [*sign*] [*digits*]

A *공백* 무시 되는 공백 또는 탭 문자로 구성 됩니다 *로그인* 는 더하기 (+) 또는 빼기 (-) 이며 및 *숫자* 하나 이상의 숫자가 됩니다.

**_wtoll** 동일 **산호 섬** 와이드 문자 문자열을 매개 변수로 소요 되는 점을 제외 하 고 있습니다.

접미사가 있는 이러한 함수 버전은 **_l** 접미사는 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 하는 점을 제외 하 고, 없는 버전과 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoll**|**atoll**|**atoll**|**_wtoll**|
|**_tstoll_l**|**_atoll_l**|**_atoll_l**|**_wtoll_l**|
|**_ttoll**|**_atoll**|**_atoll**|**_wtoll**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|--------------|---------------------|
|**atoll**, **_atoll_l**|\<stdlib.h>|
|**_wtoll**, **_wtoll_l**|\<stdlib.h> 또는 \<wchar.h>|

## <a name="example"></a>예제

이 프로그램에서는 사용 하는 **산호 섬** 저장 된 숫자 문자열을 숫자 값으로 변환 하는 함수입니다.

```C
// crt_atoll.c
// Build with: cl /W4 /Tc crt_atoll.c
// This program shows how to use the atoll
// functions to convert numbers stored as
// strings to numeric values.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main(void)
{
    char *str = NULL;
    long long value = 0;

    // An example of the atoll function
    // with leading and trailing white spaces.
    str = "  -27182818284 ";
    value = atoll(str);
    printf("Function: atoll(\"%s\") = %lld\n", str, value);

    // Another example of the atoll function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = atoll(str);
    printf("Function: atoll(\"%s\") = %lld\n", str, value);

    // Another example of the atoll function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atoll(str);
    printf("Function: atoll(\"%s\") = %lld\n", str, value);
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atoll("  -27182818284 ") = -27182818284
Function: atoll("314127.64") = 314127
Function: atoll("3336402735171707160320") = 9223372036854775807
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

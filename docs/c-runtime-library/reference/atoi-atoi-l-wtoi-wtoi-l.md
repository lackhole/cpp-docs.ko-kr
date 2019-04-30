---
title: atoi, _atoi_l, _wtoi, _wtoi_l
ms.date: 11/04/2016
apiname:
- _wtoi
- _wtoi_l
- atoi
- _atoi_l
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _tstoi
- _wtoi
- _ttoi
- atoi
- _atoi_l
- _wtoi_l
helpviewer_keywords:
- _atoi_l function
- ttoi function
- atoi_l function
- string conversion, to integers
- _wtoi function
- wtoi_l function
- tstoi function
- _ttoi function
- _tstoi function
- _wtoi_l function
- atoi function
- wtoi function
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
ms.openlocfilehash: b6a1f52e6c83f53230c736db3a506aed4b52e434
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347849"
---
# <a name="atoi-atoil-wtoi-wtoil"></a>atoi, _atoi_l, _wtoi, _wtoi_l

문자열을 정수로 변환합니다.

## <a name="syntax"></a>구문

```C
int atoi(
   const char *str
);
int _wtoi(
   const wchar_t *str
);
int _atoi_l(
   const char *str,
   _locale_t locale
);
int _wtoi_l(
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

각 함수가 반환 하는 **int** 입력된 문자를 숫자로 해석 하 여 생성 된 값입니다. 반환 값은 0입니다 **atoi** 하 고 **_wtoi**이면 입력 해당 형식의 값으로 변환할 수 없습니다.

큰 음의 정수 값을 사용 하는 오버플로의 경우 **LONG_MIN** 반환 됩니다. **atoi** 하 고 **_wtoi** 반환 **INT_MAX** 하 고 **INT_MIN** 이러한 조건에서 합니다. 모든 범위를 벗어난 경우에 **errno** 로 설정 된 **ERANGE**합니다. 전달 된 매개 변수 인지 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 0을 반환 합니다.

## <a name="remarks"></a>설명

이러한 함수는 문자열을 정수 값으로 변환 (**atoi** 하 고 **_wtoi**). 입력 문자열은 지정된 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다. 함수는 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중지합니다. 이 문자는 문자열을 종결하는 null 문자('\0' 또는 L'\0')일 수 있습니다.

합니다 *str* 인수 **atoi** 하 고 **_wtoi** 형식은:

> [*whitespace*] [*sign*] [*digits*]]

A *공백* 무시 되는 공백 또는 탭 문자로 구성 됩니다 *로그인* 는 더하기 (+) 또는 빼기 (-) 이며 및 *숫자* 하나 이상의 숫자가 됩니다.

포함 된 이러한 함수의 버전을 **_l** 접미사 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstoi**|**atoi**|**atoi**|**_wtoi**|
|**_ttoi**|**atoi**|**atoi**|**_wtoi**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|--------------|---------------------|
|**atoi**|\<stdlib.h>|
|**_atoi_l**, **_wtoi**, **_wtoi_l**|\<stdlib.h> 또는 \<wchar.h>|

## <a name="example"></a>예제

이 프로그램을 사용 하 여 숫자 값을 문자열로 저장 된 숫자를 변환할 수 하는 방법을 보여 줍니다 합니다 **atoi** 함수입니다.

```C
// crt_atoi.c
// This program shows how numbers
// stored as strings can be converted to
// numeric values using the atoi functions.

#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    int     value = 0;

    // An example of the atoi function.
    str = "  -2309 ";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );

    // Another example of the atoi function.
    str = "31412764";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );

    // Another example of the atoi function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atoi( "  -2309 " ) = -2309
Function: atoi( "31412764" ) = 31412764
Function: atoi( "3336402735171707160320" ) = 2147483647
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

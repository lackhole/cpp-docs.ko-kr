---
title: _gcvt
ms.date: 04/05/2018
apiname:
- _gcvt
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
- _gcvt
helpviewer_keywords:
- _gcvt function
- _CVTBUFSIZE
- gcvt function
- floating-point functions, converting number to string
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
ms.openlocfilehash: 9cf966b455af601d09b4444a5c590e305a6681c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332255"
---
# <a name="gcvt"></a>_gcvt

부동 소수점 값을 버퍼에 저장되는 문자열로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_gcvt_s](gcvt-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_gcvt(
   double value,
   int digits,
   char *buffer
);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
변환할 값입니다.

*digits*<br/>
저장된 유효 자릿수입니다.

*buffer*<br/>
결과의 스토리지 위치입니다.

## <a name="return-value"></a>반환 값

**_gcvt** 숫자의 문자열에 대 한 포인터를 반환 합니다.

## <a name="remarks"></a>설명

**_gcvt** 함수는 부동 소수점 변환 *값* 를 포함 하는 소수점 및 가능한 부호 바이트 문자열로 문자열을 가져와 *버퍼*합니다. 합니다 *버퍼* 변환 된 값과 자동으로 추가 되는 종료 null 문자를 수용 하기에 충분 해야 합니다. 경우는 버퍼 크기인 *자릿수* + 1은 사용, 함수는 버퍼의 끝을 덮어씁니다. 이는 변환된 문자열에 소수점이 포함되어 있고 부호 및 지수 정보가 포함될 수 있기 때문입니다. 오버플로에 대한 프로비전이 없습니다. **_gcvt** 생성 하려고 *자릿수* 10 진수 형식의 숫자입니다. 수 없는 경우 생성 *자릿수* 지 수 서식의 자릿수입니다. 변환 시 뒤에 오는 0을 표시하지 않을 수 있습니다.

*버퍼* 길이의 **_CVTBUFSIZE** 충분 모두 부동 소수점 값입니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *버퍼* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **NULL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_gcvt**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_gcvt.c
// compile with: /W3
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   char buffer[_CVTBUFSIZE];
   double value = -1234567890.123;
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );
   _gcvt( value, 12, buffer ); // C4996
   // Note: _gcvt is deprecated; consider using _gcvt_s instead
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );

   printf( "\n" );
   value = -12.34567890123;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
}
```

```Output
The following numbers were converted by _gcvt(value,12,buffer):
buffer: '-1234567890.12' (14 chars)
buffer: '-12345678901.2' (14 chars)
buffer: '-123456789012' (13 chars)
buffer: '-1.23456789012e+012' (19 chars)

buffer: '-12.3456789012' (14 chars)
buffer: '-1.23456789012' (14 chars)
buffer: '-0.123456789012' (15 chars)
buffer: '-1.23456789012e-002' (19 chars)
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>

---
title: _ecvt
ms.date: 04/05/2018
apiname:
- _ecvt
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
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 36c9cb2e8cd9eb4dd67bb91e9e4dbd36d8d1fc8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288674"
---
# <a name="ecvt"></a>_ecvt

변환 된 **이중** 숫자를 문자열로 합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_ecvt_s](ecvt-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
변환할 숫자입니다.

*count*<br/>
저장된 자릿수입니다.

*dec*<br/>
저장된 소수점 위치입니다.

*sign*<br/>
변환된 숫자의 부호입니다.

## <a name="return-value"></a>반환 값

**_ecvt** 자릿수; 문자열에 대 한 포인터를 반환 합니다. **NULL** 오류가 발생 합니다.

## <a name="remarks"></a>설명

합니다 **_ecvt** 함수는 부동 소수점 숫자를 문자열로 변환 합니다. 합니다 *값* 매개 변수는 변환할 부동 소수점 숫자입니다. 이 함수를 저장 *개수* 자릿수 *값* 문자열로 고 null 문자 ('\0')를 추가 합니다. 경우에 자릿수 *값* 초과 *개수*, 낮은 자리 숫자가 반올림 됩니다. 개 보다 적으면 *개수* 숫자, 문자열은 0으로 채워집니다.

반환 된 총 자릿수 **_ecvt** 초과 하지 것입니다 **_CVTBUFSIZE**합니다.

숫자만 문자열에 저장됩니다. 소수점 및 부호의 위치 *값* 에서 얻을 수 있습니다 *dec* 하 고 *기호* 호출 후 합니다. 합니다 *dec* 매개 변수는 문자열의 시작을 기준으로 소수점의 위치를 제공 하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. 합니다 *기호* 매개 변수 변환 된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.

차이점 **_ecvt** 및 **_fcvt** 의 해석 합니다 *개수* 매개 변수입니다. **_ecvt** 해석 *개수* 출력 문자열에 전체 자릿수와 반면 **_fcvt** 해석 *개수* 뒤의 자릿수로 숫자로 합니다 소수점입니다.

**_ecvt** 하 고 **_fcvt** 변환에 대 한 정적으로 할당 된 단일 버퍼를 사용 합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *dec* 또는 *기호* 됩니다 **NULL**, 또는 *개수* 0 인에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 하 고 **NULL** 반환 됩니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>

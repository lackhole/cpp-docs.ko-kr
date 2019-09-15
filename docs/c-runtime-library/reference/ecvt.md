---
title: _ecvt
ms.date: 04/05/2018
api_name:
- _ecvt
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
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 9f91733c566c1782d5ccfc9a7c01e490a5915a85
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942055"
---
# <a name="_ecvt"></a>_ecvt

**Double** 숫자를 문자열로 변환 합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_ecvt_s](ecvt-s.md)를 참조하세요.

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

*value*<br/>
변환할 숫자입니다.

*count*<br/>
저장된 자릿수입니다.

*dec*<br/>
저장된 소수점 위치입니다.

*sign*<br/>
변환된 숫자의 부호입니다.

## <a name="return-value"></a>반환 값

**_ecvt** 는 숫자 문자열에 대 한 포인터를 반환 합니다. 오류가 발생 한 경우 **NULL** 입니다.

## <a name="remarks"></a>설명

**_Ecvt** 함수는 부동 소수점 숫자를 문자열로 변환 합니다. *값* 매개 변수는 변환할 부동 소수점 숫자입니다. 이 함수는 *값* 의 숫자 *수* 를 문자열로 저장 하 고 null 문자 (' \ 0 ')를 추가 합니다. *값* 의 자릿수 수가 *count*를 초과 하는 경우 하위 숫자가 반올림 됩니다. *개수* 보다 작은 경우 문자열은 0으로 채워집니다.

**_Ecvt** 에서 반환 된 총 자릿수는 **_CVTBUFSIZE**을 초과 하지 않습니다.

숫자만 문자열에 저장됩니다. 소수점 및 부호 *값* 의 위치는 *dec* 에서 가져오고 호출 후에 *서명할* 수 있습니다. *Dec* 매개 변수는 문자열의 시작 부분을 기준으로 소수점의 위치를 제공 하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. *부호* 매개 변수는 변환 된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.

**_Ecvt** 와 **_ecvt** 간의 차이는 *count* 매개 변수를 해석 하는 것입니다. **_ecvt** 는 *카운트* 를 출력 문자열의 전체 자릿수로 해석 하는 반면 **_ecvt** 는 *카운트* 를 소수점 뒤의 자릿수로 해석 합니다.

**_ecvt** 및 **_ecvt** 는 변환에 대해 정적으로 할당 된 단일 버퍼를 사용 합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *Dec* 또는 *sign* 이 **NULL**이거나 *Count* 가 0 이면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우에는 **errno** 가 **EINVAL** 로 설정 되 고 **NULL** 이 반환 됩니다.

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

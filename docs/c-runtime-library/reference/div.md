---
title: div, ldiv, lldiv
ms.date: 04/05/2018
apiname:
- div
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- div
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: 0ee1b3b6a5d7b15470ffe1e667b4077d1f9581e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339262"
---
# <a name="div-ldiv-lldiv"></a>div, ldiv, lldiv

두 정수 값의 몫과 나머지를 계산합니다.

## <a name="syntax"></a>구문

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*numer*<br/>
분자입니다.

*denom*<br/>
분모입니다.

## <a name="return-value"></a>반환 값

**div** 형식의 인수를 사용 하 여 호출한 **int** 형식의 구조체를 반환 **div_t**, 몫과 나머지를 구성 하는 합니다. 형식의 인수를 사용 하 여 반환 값 **긴** 됩니다 **ldiv_t**, 형식의 인수를 사용 하 여 반환 값과 **긴** **긴** 는**lldiv_t**합니다. **div_t**, **ldiv_t**, 및 **lldiv_t** 에 정의 된 \<b. h >입니다.

## <a name="remarks"></a>설명

**div** 함수 *필드가* 하 여 *denom* 있으므로 몫과 나머지를 계산 하 고 있습니다. 합니다 [div_t](../../c-runtime-library/standard-types.md) 구조에는 몫인 **q u o t**, 및 나머지 인 **rem**합니다. 몫의 부호는 수학적 몫의 부호와 같습니다. 몫의 절대 값은 수학적 몫의 절대 값보다 작은 가장 큰 정수입니다. 분모가 0이면 프로그램이 종료되고 오류 메시지가 표시됩니다.

오버 로드 **div** 형식의 인수를 사용 하는 **긴** 또는 **긴** **긴** 이용할 C++ 코드입니다. 반환 형식은 [ldiv_t](../../c-runtime-library/standard-types.md) 하 고 [lldiv_t](../../c-runtime-library/standard-types.md) 멤버가 포함 되어 **q u o t** 및 **rem**, 의멤버와동일한의미를포함하는**div_t**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>

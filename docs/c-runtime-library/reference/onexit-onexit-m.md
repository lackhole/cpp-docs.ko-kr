---
title: _onexit, _onexit_m
ms.date: 11/04/2016
apiname:
- _onexit
- _onexit_m
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
apitype: DLLExport
f1_keywords:
- _onexit
- onexit_m
- onexit
- _onexit_m
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
ms.openlocfilehash: c190f777032904802f771bab9fc323ba305ff32e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156047"
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m

종료 시 호출할 루틴을 등록합니다.

## <a name="syntax"></a>구문

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>매개 변수

*function*<br/>
종료 시 호출할 함수에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**_onexit** 성공 하면 함수에 대 한 포인터를 반환 하거나 **NULL** 함수 포인터를 저장할 공간이 없는 경우.

## <a name="remarks"></a>설명

합니다 **_onexit** 함수는 함수의 주소가 전달 됩니다 (*함수*) 프로그램이 정상적으로 종료 될 때 호출 되 합니다. 에 대 한 연속 호출 **_onexit** LIFO (마지막에-선입 선출) 순서 대로 실행 되는 함수의 레지스터가 만들어집니다. 함수에 전달 **_onexit** 매개 변수를 사용할 수 없습니다.

에서는 때 **_onexit** 등록 된 루틴이 DLL 내에서 호출 되 **_onexit** 후 실행 DLL의 언로드에서 **DllMain** DLL_PROCESS_DETACH를 사용 하 여 호출 됩니다.

**_onexit** Microsoft 확장입니다. ANSI 이식성이 필요한 경우에는 [atexit](atexit.md)을 사용하세요. 합니다 **_onexit_m** 함수의 버전은 혼합 된 모드용입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>출력

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>

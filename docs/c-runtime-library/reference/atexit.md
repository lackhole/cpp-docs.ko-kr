---
title: atexit
ms.date: 11/04/2016
apiname:
- atexit
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
- atexit
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
ms.openlocfilehash: 48f0fbfa1f3350f73899fcdbb3bf7922f1c6174d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341589"
---
# <a name="atexit"></a>atexit

종료 시 지정된 함수를 처리합니다.

## <a name="syntax"></a>구문

```C
int atexit(
   void (__cdecl *func )( void )
);
```

### <a name="parameters"></a>매개 변수

*func*<br/>
호출할 함수입니다.

## <a name="return-value"></a>반환 값

**atexit** 오류가 발생 한 경우 성공 하면 0 또는 0이 아닌 값을 반환 합니다.

## <a name="remarks"></a>설명

합니다 **atexit** 함수는 함수의 주소가 전달 됩니다 *func* 프로그램이 정상적으로 종료 될 때 호출 되 합니다. 에 대 한 연속 호출 **atexit** lifo (후입선출) 순서로 마지막에 실행 되는 함수의 레지스터가 만들어집니다. 함수에 전달 **atexit** 매개 변수를 사용할 수 없습니다. **atexit** 하 고 **_onexit** 함수의 레지스터를 저장 하는 힙을 사용 합니다. 따라서 등록 가능한 함수의 수는 힙 메모리에 의해서만 제한됩니다.

코드를 **atexit** 함수 수 이미 언로드된 경우 모든 DLL에 대 한 종속성을 포함 하지 않아야는 **atexit** 함수를 호출 합니다.

ANSI 호환 응용 프로그램을 생성 하려면 ANSI 표준 사용 **atexit** 함수 (대신 유사한 **_onexit** 함수).

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>예제

이 프로그램 푸시 4 개의 함수 될 때 실행할 함수 스택에 **atexit** 라고 합니다. 프로그램이 종료되면 LIFO(후입선출) 방식으로 이러한 프로그램이 실행됩니다.

```C
// crt_atexit.c
#include <stdlib.h>
#include <stdio.h>

void fn1( void ), fn2( void ), fn3( void ), fn4( void );

int main( void )
{
   atexit( fn1 );
   atexit( fn2 );
   atexit( fn3 );
   atexit( fn4 );
   printf( "This is executed first.\n" );
}

void fn1()
{
   printf( "next.\n" );
}

void fn2()
{
   printf( "executed " );
}

void fn3()
{
   printf( "is " );
}

void fn4()
{
   printf( "This " );
}
```

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>

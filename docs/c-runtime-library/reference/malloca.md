---
title: _malloca
ms.date: 11/04/2016
apiname:
- _malloca
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
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 22a63002c900d69e8a7706a54acedf0b4b4f6376
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156878"
---
# <a name="malloca"></a>_malloca

스택에 메모리를 할당합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_alloca](alloca.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
스택에서 할당할 바이트입니다.

## <a name="return-value"></a>반환 값

합니다 **_malloca** 루틴의 반환을 **void** 맞춰지도록 모든 형식의 개체 저장소로 할당된 된 공간에 대 한 포인터입니다. 하는 경우 *크기* 가 0 이면 **_malloca** 길이가 0 인 항목을 할당 하 고 해당 항목에 대 한 유효한 포인터를 반환 합니다.

경우 *크기* 보다 크면 **_ALLOCA_S_THRESHOLD**, 한 다음 **_malloca** 힙에서 할당 하려고 하며 공간을 할당할 수 없는 경우 null 포인터를 반환 합니다. 하는 경우 *크기* 보다 작거나 같음 **_ALLOCA_S_THRESHOLD**, 한 다음 **_malloca** 스택의 스택 오버플로 예외에 할당 하려고 공간이 없는 경우 생성 됩니다 할당 됩니다. 스택 오버플로 예외 없습니다는 C++ 예외 이 구조적된 예외입니다. 사용 하는 대신 C++ 예외 처리를 사용 해야 합니다 [구조적 예외 처리](../../cpp/structured-exception-handling-c-cpp.md) (SEH)이이 예외를 catch 합니다.

## <a name="remarks"></a>설명

**_malloca** 할당 *크기* 프로그램 스택이나 요청 하 여 지정 된 바이트는 특정 크기를 초과 하는 경우 힙 바이트 **_ALLOCA_S_THRESHOLD**합니다. 차이점 **_malloca** 하 고 **_alloca** 는 **_alloca** 항상 크기에 관계 없이 스택에 할당 합니다. 와 달리 **_alloca**에 필요 하지 않거나에 대 한 호출을 허용 하는 **무료** 할당 메모리를 확보 하기 **_malloca** 사용 해야 [_freea](freea.md)메모리를 확보 합니다. 디버그 모드일에서 **_malloca** 항상 힙에서 메모리를 할당 합니다.

명시적으로 호출 제한은 **_malloca** 는 EH (예외 처리기)에 있습니다. X86 급 프로세서에서 실행 되는 EH 루틴은 고유한 메모리 프레임에서 작동 합니다. 바깥쪽 함수 스택 포인터의 현재 위치를 기반으로 하지 않는 메모리 공간에서 해당 작업을 수행 하며 합니다. 가장 일반적인 구현에는 Windows NT SEH(구조적 예외 처리) 및 C++ catch 절 식이 포함됩니다. 따라서 명시적으로 호출 **_malloca** 호출 EH 루틴으로 돌아가는 동안 프로그램 오류가 발생 했습니다. 다음 시나리오 중 하나에서:

- Windows NT SEH 예외 필터 식: **__except** (`_malloca ()` )

- Windows NT SEH 최종 예외 처리기: **__finally** {0}`_malloca ()` }

- C++ EH catch 절 식

그러나 **_malloca** 수에서 직접 호출할 수는 EH 루틴 내 또는 호출 되는 응용 프로그램 제공 콜백에서 위에 나열 된 EH 시나리오 중 하나입니다.

> [!IMPORTANT]
> Windows XP의 경우 **_malloca** 라고는 try/catch 블록 내에서 호출 해야 [_resetstkoflw](resetstkoflw.md) catch 블록에서.

위의 제한에 사용 하는 경우 외에 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 **_malloca** 에서 사용할 수 없습니다 **__except** 블록입니다. 자세한 내용은 [/clr Restrictions](../../build/reference/clr-restrictions.md)을 참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>예제

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>예제

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>입력

```Input
1000
```

### <a name="sample-output"></a>샘플 출력

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>

---
title: exit, _Exit, _exit
ms.date: 01/02/2018
apiname:
- _exit
- exit
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: c16f306d745b96d8bc7c223213378140fdae14bb
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927391"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

호출 프로세스를 종료합니다. **Exit** 함수는 정리 후 종료 합니다. **_exit** 및 **_exit** 는 즉시 종료 합니다.

> [!NOTE]
> 테스트 또는 디버깅 시나리오를 제외 하 고이 메서드를 사용 하 여 UWP (유니버설 Windows 플랫폼) 앱을 종료 하지 마세요. 프로그래밍 또는 UI 방식으로 스토어 앱을 닫는 것은 [Microsoft Store 정책](/legal/windows/agreements/store-policies)에 따라 허용 되지 않습니다. 자세한 내용은 [UWP 앱 수명 주기](/windows/uwp/launch-resume/app-lifecycle)를 참조 하세요. Windows 10 앱에 대한 자세한 내용은 [Windows 10 앱에 대한 방법 가이드](https://developer.microsoft.com/windows/apps)를 참조하세요.

## <a name="syntax"></a>구문

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
종료 상태 코드입니다.

## <a name="remarks"></a>설명

**Exit**, **_exit** 및 **_exit** 함수는 호출 프로세스를 종료 합니다. **Exit** 함수는 스레드 로컬 개체에 대 한 소멸자를 호출한 다음 **atexit** 및 **_onexit**에서 등록 된 함수를 LIFO (LIFO) 순서로 호출 하 고를 종료 하기 전에 모든 파일 버퍼를 플러시합니다. 프로세스. **_Exit** 및 **_exit** 함수는 스레드 로컬 개체를 삭제 하거나 **atexit** 또는 **_onexit** 함수를 처리 하지 않고 스트림 버퍼를 플러시하지 않고 프로세스를 종료 합니다.

**Exit**, **_exit** 및 **_exit** 호출은 값을 반환 하지 않지만 프로세스가 종료 된 후 호스트 환경 또는 호출 대기 중인 프로세스 (있는 경우)에서 *상태* 값을 사용할 수 있습니다. 일반적으로 호출자는 *상태* 값을 0으로 설정 하 여 정상 종료를 나타내거나 다른 값으로 설정 하 여 오류를 표시 합니다. *상태* 값은 운영 체제 일괄 처리 명령 **ERRORLEVEL** 에서 사용할 수 있으며 다음 두 가지 상수 중 하나로 표시 됩니다. 값 0을 나타내는 **EXIT_SUCCESS**또는 값 1을 나타내는 **EXIT_FAILURE**입니다.

**Exit**, **_exit**, **_exit**, **quick_exit**, **_cexit**및 **_c_exit** 함수는 다음과 같이 동작 합니다.

|함수|Description|
|--------------|-----------------|
|**exit**|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_Exit**|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_exit**|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**quick_exit**|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_cexit**|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|
|**_c_exit**|최소 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|

**Exit**, **_exit** 또는 **_exit** 함수를 호출 하는 경우 호출 시 존재 하는 임시 또는 자동 개체에 대 한 소멸자가 호출 되지 않습니다. 자동 개체는 함수에 정의 된 비정적 로컬 개체입니다. 임시 개체는 함수 호출에서 반환 되는 값과 같이 컴파일러에 의해 생성 되는 개체입니다. **Exit**, **_exit**또는 **_exit**를 호출 하기 전에 자동 개체를 삭제 하려면 다음과 같이 개체에 대 한 소멸자를 명시적으로 호출 합니다.

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**DLL_PROCESS_ATTACH** 를 사용 하 여 **DllMain**에서 **exit** 를 호출 하지 마세요. **DLLMain** 함수를 종료 하려면 **DLL_PROCESS_ATTACH**에서 **FALSE** 를 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**exit**, **_Exit**, **_exit**|\<process.h> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

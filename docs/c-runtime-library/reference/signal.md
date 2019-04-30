---
title: 신호
ms.date: 04/12/2018
apiname:
- signal
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
- signal
helpviewer_keywords:
- signal function
ms.openlocfilehash: 351bdbe1d787fc5e5d741460adfe415df7fda756
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356292"
---
# <a name="signal"></a>신호

인터럽트 신호 처리를 설정합니다.

> [!IMPORTANT]
> 테스트 또는 디버깅 시나리오에서 Microsoft Store 앱을 제외 하 고 종료 하려면이 메서드를 사용 하지 마십시오. 스토어 앱을 닫으려면 프로그래밍 또는 UI 방식으로에 따라 허용 되지 않습니다 합니다 [Microsoft Store 정책](/legal/windows/agreements/store-policies)합니다. 자세한 내용은 [UWP 앱 수명 주기](/windows/uwp/launch-resume/app-lifecycle)합니다.

## <a name="syntax"></a>구문

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>매개 변수

*sig*<br/>
신호 값입니다.

*func*<br/>
두 번째 실행할 함수에 대 한 포인터입니다. 첫 번째 매개 변수는 신호 값이고 두 번째 매개 변수는 첫 번째 매개 변수가 SIGFPE일 때 사용할 수 있는 하위 코드입니다.

## <a name="return-value"></a>반환 값

**신호** 주어진된 신호와 연관 된 func의 이전 값을 반환 합니다. 예를 들어 경우의 이전 값 *func* 되었습니다 **SIG_IGN**, 반환 값 이기도 **SIG_IGN**합니다. 반환 값 **SIG_ERR** 오류를 나타내는 경우; **errno** 로 설정 되어 **EINVAL**합니다.

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **신호** 함수를 사용 하면 운영 체제에서 인터럽트 신호를 처리 하는 몇 가지 방법 중 하나를 선택 하는 프로세스입니다. 합니다 *sig* 인수가 하는 인터럽트 **신호** 응답 신호에 정의 된 다음 매니페스트 상수 중 하나 여야 합니다. 8.

|*sig* value|설명|
|-----------------|-----------------|
|**SIGABRT**|비정상적인 종료|
|**SIGFPE**|부동 소수점 오류|
|**SIGILL**|잘못된 명령|
|**SIGINT**|Ctrl+C 신호|
|**SIGSEGV**|잘못된 스토리지 액세스|
|**SIGTERM**|종료 요청|

하는 경우 *sig* 이 아닌에 위의 값을 잘못 된 매개 변수 처리기가 호출에 정의 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **SIG_ERR**합니다.

기본적으로 **신호** 의 값에 관계 없이 종료 코드 3 사용 하 여 호출 프로그램을 종료 *sig*합니다.

> [!NOTE]
> **SIGINT** Win32 응용 프로그램에 대 한 지원 되지 않습니다. Ctrl+C 인터럽트가 발생할 때 Win32 운영 체제는 특히 해당 인터럽트를 처리하기 위해 새 스레드를 생성합니다. 이렇게 하면 UNIX에서와 같은 단일 스레드 애플리케이션이 다중 스레드가 되며 예기치 않은 동작을 발생시킵니다.

합니다 *func* 인수는 개발자가 작성 한 신호 처리기 또는 미리 정의 된 상수 중 하나에 주소 **SIG_DFL** 또는 **SIG_IGN**, 신호에도 정의 되어 있는 합니다. 8. 하는 경우 *func* 함수는 주어진된 신호에 대 한 신호 처리기로 설치 됩니다. 신호 처리기의 프로토타입에 필요한 하나의 형식 인수 *sig*, 형식의 **int**합니다. 통해 실제 인수를 제공 하는 운영 체제 *sig* 인터럽트가 발생할 때 인수가 인터럽트를 생성 한 신호입니다. 따라서 앞의 표에 나열된 6개의 매니페스트 상수를 신호 처리기에서 사용하여 인터럽트가 발생했는지 여부를 확인하고 적절한 조치를 취할 수 있습니다. 예를 들어, 호출할 수 있습니다 **신호** 동일한 처리기 두 개의 서로 다른 신호를 할당 한 다음 테스트를 두 번의 *sig* 수신 신호를 기반으로 다른 작업을 수행 하는 처리기에 대 한 인수입니다.

부동 소수점 예외에 대 한 테스트 하는 경우 (**SIGFPE**), *func* 는 선택적 두 번째 인수를 사용 하는 함수를 가리킵니다 FLOAT에 정의 된 여러 매니페스트 상수 중 하나인 메시지를 표시 합니다. 폼의 H **FPE_xxx**합니다. 경우는 **SIGFPE** 신호 발생 부동 소수점 예외의 종류를 확인 하 고 적절 한 조치를 취할 두 번째 인수의 값을 테스트할 수 있습니다. 이 인수 및 가능한 값은 Microsoft 확장입니다.

부동 소수점 예외의 경우 값 *func* 신호를 받을 때 다시 설정 되지 않습니다. 부동 소수점 예외에서 복구하려면 try/except 절을 사용하여 부동 소수점 작업을 둘러쌉니다. 또한 [setjmp](setjmp.md)를 [longjmp](longjmp.md)와 함께 사용하여 복구할 수 있습니다. 이 두 경우 모두에서 호출 프로세스는 실행을 다시 시작하고 프로세스의 부동 소수점 상태를 정의되지 않은 상태로 둡니다.

신호 처리기가 반환하는 경우 호출 프로세스는 인터럽트 신호를 받은 시점 직후 실행을 다시 시작합니다. 이는 신호 또는 작동 모드의 유형에 상관없이 적용됩니다.

지정된 된 함수를 실행 하기 전에 변수의 *func* 로 설정 된 **SIG_DFL**합니다. 에 대해 설명한 다음 인터럽트 신호 처리 됩니다 **SIG_DFL**장애가 있는 호출 되지 않은 경우 **신호** 그렇지 않도록 지정 합니다. 이 기능을 사용하면 호출된 함수에서 신호를 다시 설정할 수 있습니다.

인터럽트가 발생할 때 신호 처리기 루틴이 일반적으로 비동기적으로 호출되기 때문에 런타임 작업이 불완전하고 알 수 없는 상태일 때 신호 처리기 함수가 제어될 수 있습니다. 다음 목록에서는 신호 처리기 루틴에서 사용할 수 있는 함수를 결정하는 제한 사항을 요약합니다.

- 하위 수준 문제 되지 또는 STDIO를 수행 합니다. H I/O 루틴 (예를 들어 **printf** 하거나 **fread**).

- 힙 루틴 또는 힙 루틴을 사용 하는 임의의 루틴을 호출 하지 마세요 (예를 들어 **malloc**를 **_strdup**, 또는 **_putenv**). 자세한 내용은 [malloc](malloc.md)를 참조하세요.

- 시스템 호출을 생성 하는 함수를 사용 하지 마십시오 (예를 들어 **_getcwd** 하거나 **시간**).

- 사용 하지 마세요 **longjmp** 인터럽트를 부동 소수점 예외를 발생 하지 않는 한 (즉, *sig* 됩니다 **SIGFPE**). 이 경우에 대 한 호출을 사용 하 여에 먼저 부동 소수점 패키지를 다시 초기화 **_fpreset**합니다.

- 오버레이 루틴을 사용하지 마십시오.

프로그램을 트래핑할 경우 부동 소수점 코드를 포함 해야 합니다 **SIGFPE** 함수를 사용 하 여 예외입니다. 프로그램에 부동 소수점 코드가 없으며 런타임 라이브러리의 신호 처리 코드가 필요한 경우 volatile double을 선언하고 0으로 초기화합니다.

```C
volatile double d = 0.0f;
```

합니다 **SIGILL** 하 고 **SIGTERM** 신호는 Windows에서 생성 되지 않습니다. 이는 ANSI 호환성을 위해 포함됩니다. 따라서 사용 하 여 이러한 신호에 대 한 신호 처리기를 설정할 수 있습니다 **신호**를 호출 하 여 이러한 신호를 명시적으로 생성할 수 있습니다 [발생](raise.md)합니다.

호출 하 여 만든 생성 된 프로세스에서 신호 설정은 유지 되지 않습니다 [_exec](../../c-runtime-library/exec-wexec-functions.md) 하거나 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 함수입니다. 신호 설정은 새 프로세스에서 기본값으로 다시 설정됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**signal**|\<signal.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법을 보여 줍니다 **신호** 일부 사용자 지정 동작을 추가 하는 **SIGABRT** 신호입니다. abort 동작에 대한 자세한 내용은 [_set_abort_behavior](set-abort-behavior.md)를 참조하세요.

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_fpreset](fpreset.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>

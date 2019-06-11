---
title: _beginthread, _beginthreadex
ms.date: 02/27/2018
apiname:
- _beginthread
- _beginthreadex
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
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
ms.openlocfilehash: f64fd7b945fc8ea2e5c111d300266e07faade0e7
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504535"
---
# <a name="beginthread-beginthreadex"></a>_beginthread, _beginthreadex

스레드를 만듭니다.

## <a name="syntax"></a>구문

```cpp
uintptr_t _beginthread( // NATIVE CODE
   void( __cdecl *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthread( // MANAGED CODE
   void( __clrcall *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthreadex( // NATIVE CODE
   void *security,
   unsigned stack_size,
   unsigned ( __stdcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
uintptr_t _beginthreadex( // MANAGED CODE
   void *security,
   unsigned stack_size,
   unsigned ( __clrcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
```

### <a name="parameters"></a>매개 변수

*start_address*<br/>
새 스레드의 실행을 시작하는 루틴의 시작 주소입니다. 에 대 한 **_beginthread**, 호출 규칙입니다 [__cdecl](../../cpp/cdecl.md) (네이티브 코드용) 또는 [__clrcall](../../cpp/clrcall.md) (관리 코드용), **_beginthreadex**에 [__stdcall](../../cpp/stdcall.md) (네이티브 코드용) 또는 [__clrcall](../../cpp/clrcall.md) (관리 코드용)입니다.

*stack_size*<br/>
새 스레드의 스택 크기 또는 0입니다.

*arglist*<br/>
새 스레드에 전달할 인수 목록 또는 **NULL**합니다.

*보안*<br/>
반환된 핸들이 자식 프로세스에 의해 상속되는지 여부를 결정하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조에 대한 포인터입니다. 하는 경우 *보안* 됩니다 **NULL**, 핸들을 상속할 수 없습니다. 여야 **NULL** Windows 95 응용 프로그램에 대 한 합니다.

*initflag*<br/>
새 스레드의 초기 상태를 제어하는 플래그입니다. 설정 *initflag* 즉시 실행 하는 0 또는 **CREATE_SUSPENDED** 스레드를 만들지는 일시 중단 된 상태에서 사용 하 여 [ResumeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-resumethread) 스레드를 실행 하려면. 설정 *initflag* 하 **STACK_SIZE_PARAM_IS_A_RESERVATION** 플래그를 사용 하 여 *stack_size* 초기 예약 크기 (바이트)에서 스택의 경우이 플래그를 지정 하지 않으면 대로*stack_size* 커밋 크기를 지정 합니다.

*thrdaddr*<br/>
스레드 식별자를 수신하는 32비트 변수를 가리킵니다. 있으면 **NULL**, 사용 되지 않습니다.

## <a name="return-value"></a>반환 값

성공 하면 이러한 각 함수 핸들을 반환 합니다 새로 만든된 스레드에; 그러나 새로 만든된 스레드가 너무 신속 하 게 종료 하는 경우 **_beginthread** 유효한 핸들을 반환 하지 않을 수 있습니다. 설명 단원의 설명을 참조하세요. 오류 발생 시 **_beginthread** -1l로 반환 하 고 **errno** 로 설정 되어 **EAGAIN** 없으면 너무 많은 스레드를 **EINVAL** 인수가 잘못 되었거나 스택 크기가 올바르지 않습니다. 또는 **EACCES** 경우 (예: 메모리) 리소스가 부족 합니다. 오류 발생 시 **_beginthreadex** 가 0을 반환 하 고 **errno** 하 고 **_doserrno** 설정 됩니다.

하는 경우 *start_address* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 고-1을 반환 합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

에 대 한 자세한 내용은 **uintptr_t**를 참조 하십시오 [표준 형식](../../c-runtime-library/standard-types.md)합니다.

## <a name="remarks"></a>설명

합니다 **_beginthread** 함수에서 루틴 실행을 시작 하는 스레드를 만듭니다 *start_address*합니다. 루틴 *start_address* 사용 해야 합니다 **__cdecl** (네이티브 코드용) 또는 **__clrcall** (관리 코드용) 호출 규칙 및 반환 값이 없습니다. 스레드가 루틴에서 반환되면 자동으로 종료됩니다. 스레드에 대한 자세한 내용은 [이전 코드를 위한 다중 스레드 지원(Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)을 참조하세요.

**_beginthreadex** win32 [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) 자세한 API 보다 밀접 하 게 **_beginthread** 않습니다. **_beginthreadex** 에서 서로 다릅니다 **_beginthread** 다음과 같은 방법으로:

- **_beginthreadex** 3 개의 추가 매개 변수가: *initflag*, *Security*, 및 **threadaddr**합니다. 새 스레드는 지정 된 보안을 사용 하 여 일시 중단 된 상태로 만들 수 있으며 사용 하 여 액세스할 수 있습니다 *thrdaddr*, 스레드 식별자 인 합니다.

- 루틴 *start_address* 에 전달 되는 **_beginthreadex** 사용 해야 합니다 **__stdcall** (네이티브 코드용) 또는 **__clrcall** ( 관리 코드) 호출 규칙이 고, 스레드 종료 코드를 반환 해야 합니다.

- **_beginthreadex** -1l이 아닌 오류, 0을 반환 합니다.

- 사용 하 여 만든 스레드에서 **_beginthreadex** 를 호출 하 여 종료 됩니다 [_endthreadex](endthread-endthreadex.md)합니다.

**_beginthreadex** 함수를 보다 스레드를 만드는 방법을 보다 자세히 제어 사용 **_beginthread** 않습니다. 합니다 **_endthreadex** 함수는 더 유연 하기도 합니다. 예를 들어 **_beginthreadex**, 보안 정보를 사용 하 여, 실행, 일시 중단 된 스레드의 초기 상태를 설정 및 새로 만든 스레드의 스레드 식별자를 가져올 수 있습니다. 반환 되는 스레드 핸들을 사용할 수도 있습니다 **_beginthreadex** Api 사용 하 여 할 수 없는 동기화를 사용 하 여 **_beginthread**합니다.

사용할 혼용 **_beginthreadex** 보다 **_beginthread**합니다. 경우에서 생성 되는 스레드가 **_beginthread** 의 호출자에 게 반환 되는 핸들을 신속 하 게 종료 **_beginthread** 유효 하지 않게 될 수 있습니다 또는 다른 스레드를 가리킵니다. 그러나에서 반환 되는 핸들 **_beginthreadex** 를 호출자가 닫아야 **_beginthreadex**이므로 경우 유효한 핸들 이어야 반드시 **_beginthreadex** 오류를 반환 하지 않았습니다.

호출할 수 있습니다 [_endthread](endthread-endthreadex.md) 또는 **_endthreadex** 명시적으로 스레드를 종료할; 그러나 **_endthread** 하거나 **_endthreadex** 라고 자동으로 반환 될 때 스레드가 매개 변수로 전달 된 루틴에서. 호출 하 여 스레드를 종료 **_endthread** 하거나 **_endthreadex** 스레드에 대 한 할당 되는 리소스의 올바른 복구 보장 합니다.

**_endthread** 스레드 핸들을 자동으로 닫지만 **_endthreadex** 하지 않습니다. 따라서 사용 하는 경우 **_beginthread** 하 고 **_endthread**를 명시적으로 닫지 마세요 스레드 핸들을 Win32를 호출 하 여 [CloseHandle](/windows/desktop/api/handleapi/nf-handleapi-closehandle) API. 이 동작은 Win32 [ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread) API와 다릅니다.

> [!NOTE]
> Libcmt.lib로 연결 된 실행 파일에 대 한 Win32을 호출 하지 마세요 **ExitThread** API 런타임 시스템에서 회수 하지 없도록 할당 된 리소스입니다. **_endthread** 하 고 **_endthreadex** 할당 된 스레드 리소스를 회수 하 고 호출 **ExitThread**합니다.

스택 할당을 처리 하는 운영 체제 때 어느 **_beginthread** 또는 **_beginthreadex** 버전이 호출 됩니다; 스레드 스택의 주소 이러한 함수 중 하나에 전달할 필요가 없습니다. 또한 합니다 *stack_size* 인수는 0 인 경우 운영 체제 주 스레드에 대 한 지정 된 스택과 동일한 값을 사용 하는 될 수 있습니다.

*arglist* 새로 만든된 스레드에 전달 될 매개 변수입니다. 일반적으로 문자열과 같은 데이터 항목의 주소입니다. *arglist* 될 수 있습니다 **NULL** 필요 하지 않은 경우 있지만 **_beginthread** 하 고 **_beginthreadex** 새로운 스레드로 전달할 값을 지정 해야 합니다. 모든 스레드 호출 하는 경우 모든 스레드가 종료 됩니다 [중단](abort.md), **종료**합니다 **_exit**, 또는 **ExitProcess**합니다.

새 스레드의 로캘에 프로세스별 전역 현재 로캘 정보를 사용 하 여 초기화 됩니다. 스레드별 로캘은를 호출 하 여 설정할지 여부 [_configthreadlocale](configthreadlocale.md) (전역으로 또는 새 스레드에 대 한 전용), 스레드 수 해당 로캘 독립적으로 다른 스레드에서 호출 하 여 변경할 **setlocale** 또는 **_wsetlocale**합니다. 스레드별 로캘 플래그가 설정 되지 않은 스레드는 새로 생성 된 모든 스레드의 뿐만 아니라 없는 또한 스레드별 로캘 플래그를 설정 하 고, 다른 모든 스레드 로캘 정보를 발생할 수 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

에 대 한 **/clr** 코드 **_beginthread** 및 **_beginthreadex** 각각 두 개의 오버 로드를 포함 합니다. 하나는 네이티브 호출 규칙 함수 포인터 및 다른 오버 로드는 **__clrcall** 함수 포인터입니다. 첫 번째 오버로드는 애플리케이션 도메인에 안전하지 않고 어떤 방법으로도 안전할 수 없습니다. 작성 하는 경우 **/clr** 관리 되는 리소스를 코드에 액세스 하기 전에 새 스레드가 올바른 응용 프로그램 도메인에 들어가면 있는지 확인 해야 합니다. 이 작업은 예를 들어 [call_in_appdomain 함수](../../dotnet/call-in-appdomain-function.md)를 사용하여 수행할 수 있습니다. 두 번째 오버 로드는 응용 프로그램 도메인 안전 합니다. 호출자의 응용 프로그램 도메인에서 새로 생성된 된 스레드는 항상 결국 **_beginthread** 하거나 **_beginthreadex**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

다중 스레드 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 입니다.

사용 하도록 **_beginthread** 하거나 **_beginthreadex**, 응용 프로그램은 다중 스레드 C 런타임 라이브러리 중 하나를 사용 하 여 연결 해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 **_beginthread** 하 고 **_endthread**합니다.

```C
// crt_BEGTHRD.C
// compile with: /MT /D "_X86_" /c
// processor: x86
#include <windows.h>
#include <process.h>    /* _beginthread, _endthread */
#include <stddef.h>
#include <stdlib.h>
#include <conio.h>

void Bounce( void * );
void CheckKey( void * );

// GetRandom returns a random integer between min and max.
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))
// GetGlyph returns a printable ASCII character value
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))

BOOL repeat = TRUE;                 // Global repeat flag
HANDLE hStdOut;                     // Handle for console window
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure

int main()
{
    int param = 0;
    int * pparam = &param;

    // Get display screen's text row and column information.
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hStdOut, &csbi );

    // Launch CheckKey thread to check for terminating keystroke.
    _beginthread( CheckKey, 0, NULL );

    // Loop until CheckKey terminates program or 1000 threads created.
    while( repeat && param < 1000 )
    {
        // launch another character thread.
        _beginthread( Bounce, 0, (void *) pparam );

        // increment the thread parameter
        param++;

        // Wait one second between loops.
        Sleep( 1000L );
    }
}

// CheckKey - Thread to wait for a keystroke, then clear repeat flag.
void CheckKey( void * ignored )
{
    _getch();
    repeat = 0;    // _endthread implied
}

// Bounce - Thread to create and control a colored letter that moves
// around on the screen.
//
// Params: parg - the value to create the character from
void Bounce( void * parg )
{
    char       blankcell = 0x20;
    CHAR_INFO  ci;
    COORD      oldcoord, cellsize, origin;
    DWORD      result;
    SMALL_RECT region;

    cellsize.X = cellsize.Y = 1;
    origin.X = origin.Y = 0;

    // Generate location, letter and color attribute from thread argument.
    srand( _threadid );
    oldcoord.X = region.Left = region.Right =
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);
    oldcoord.Y = region.Top = region.Bottom =
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));
    ci.Attributes = GetRandom(1, 15);

    while (repeat)
    {
        // Pause between loops.
        Sleep( 100L );

        // Blank out our old position on the screen, and draw new letter.
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);

        // Increment the coordinate for next placement of the block.
        oldcoord.X = region.Left;
        oldcoord.Y = region.Top;
        region.Left = region.Right += GetRandom(-1, 1);
        region.Top = region.Bottom += GetRandom(-1, 1);

        // Correct placement (and beep) if about to go off the screen.
        if (region.Left < csbi.srWindow.Left)
            region.Left = region.Right = csbi.srWindow.Left + 1;
        else if (region.Right >= csbi.srWindow.Right)
            region.Left = region.Right = csbi.srWindow.Right - 2;
        else if (region.Top < csbi.srWindow.Top)
            region.Top = region.Bottom = csbi.srWindow.Top + 1;
        else if (region.Bottom >= csbi.srWindow.Bottom)
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;

        // If not at a screen border, continue, otherwise beep.
        else
            continue;
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);
    }
    // _endthread given to terminate
    _endthread();
}
```

아무 키나 눌러 샘플 애플리케이션을 종료합니다.

## <a name="example"></a>예제

다음 샘플 코드에서 반환 되는 스레드 핸들을 사용 하는 방법을 보여 줍니다 **_beginthreadex** 동기화 API 사용 하 여 [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject)합니다. 주 스레드는 두 번째 스레드가 종료할 때까지 기다린 다음 계속합니다. 두 번째 스레드가 호출 하는 경우 **_endthreadex**, 스레드 개체가 신호를 받은 상태로 이동 하면 됩니다. 그러면 기본 스레드를 계속 실행할 수 있습니다. 사용 하 여이 작업을 수행할 수 없습니다 **_beginthread** 하 고 **_endthread**이므로 **_endthread** 호출 **CloseHandle**, 스레드를 소멸 하는 전에 개체를 신호 받음 상태로 설정할 수 있습니다.

```cpp
// crt_begthrdex.cpp
// compile with: /MT
#include <windows.h>
#include <stdio.h>
#include <process.h>

unsigned Counter;
unsigned __stdcall SecondThreadFunc( void* pArguments )
{
    printf( "In second thread...\n" );

    while ( Counter < 1000000 )
        Counter++;

    _endthreadex( 0 );
    return 0;
}

int main()
{
    HANDLE hThread;
    unsigned threadID;

    printf( "Creating second thread...\n" );

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );

    // Wait until second thread terminates. If you comment out the line
    // below, Counter will not be correct because the thread has not
    // terminated, and Counter most likely has not been incremented to
    // 1000000 yet.
    WaitForSingleObject( hThread, INFINITE );
    printf( "Counter should be 1000000; it is-> %d\n", Counter );
    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
Creating second thread...
In second thread...
Counter should be 1000000; it is-> 1000000
```

## <a name="see-also"></a>참고자료

- [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)
- [_endthread, _endthreadex](endthread-endthreadex.md)
- [abort](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)

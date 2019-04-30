---
title: _spawnvp, _wspawnvp
ms.date: 11/04/2016
apiname:
- _wspawnvp
- _spawnvp
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wspawnvp
- _spawnvp
- wspawnvp
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
ms.openlocfilehash: b697eabd7a45eedbf9c892acee570a9e8b818d1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355135"
---
# <a name="spawnvp-wspawnvp"></a>_spawnvp, _wspawnvp

프로세스를 만들고 실행합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
intptr_t _spawnvp(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnvp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>매개 변수

*모드*<br/>
프로세스 호출을 위한 실행 모드입니다.

*cmdname*<br/>
실행할 파일의 경로입니다.

*argv*<br/>
인수에 대한 포인터 배열입니다. 인수 *argv*[0]은 일반적으로 경로에 대 한 포인터 리얼 모드에서 또는 프로그램 이름을 가리키는 보호 모드에서 및 *argv*[1]를 통해 *argv*[**n**]은 새로운 인수 목록을 형성 하는 문자열을 가리키는 포인터입니다. 인수 *argv*[**n** + 1] 이어야 합니다는 **NULL** 인수 목록의 끝을 표시에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

반환 값은 동기 **_spawnvp** 하거나 **_wspawnvp** (**_P_WAIT** 에 대해 지정 된 *모드*) 새 프로세스의 종료 상태 . 비동기 작업의 반환 값 **_spawnvp** 하거나 **_wspawnvp** (**_P_NOWAIT** 하거나 **_P_NOWAITO** 에 대해 지정 된  *모드*)은 프로세스 핸들입니다. 프로세스가 정상적으로 종료되는 경우 종료 상태는 0입니다. 생성된 된 프로세스 호출을 구체적으로 0이 아닌 인수를 사용 하는 경우 종료 상태 0이 아닌 값으로 설정할 수 있습니다 합니다 **종료** 루틴입니다. 새 프로세스가 양수 값의 종료 상태를 명시적으로 설정하지 않은 경우, 양수 값의 종료 상태는 중단되거나 인터럽트된 비정상적인 종료를 나타냅니다. 반환 값이-1 (새 프로세스가 시작 되지 않습니다.) 오류를 나타냅니다. 이 예에서 **errno** 다음 값 중 하나로 설정 됩니다.

|||
|-|-|
| **E2BIG** | 인수 목록이 1024바이트를 초과합니다. |
| **EINVAL** | *모드* 인수가 잘못 되었습니다. |
| **ENOENT** | 파일 또는 경로를 찾을 수 없습니다. |
| **ENOEXEC** | 지정한 파일이 실행할 수 없거나 실행 파일 형식이 잘못되었습니다. |
| **ENOMEM** | 메모리가 부족하여 새 프로세스를 실행할 수 없습니다. |

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

새 프로세스를 만들고 이러한 각 함수 및 실행 하 고 포인터 배열을 명령줄 인수를 사용 하 여 전달 된 **경로** 환경 변수를 실행 하려면 파일을 찾습니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 *cmdname* 또는 *argv* 가 null 포인터 이거나 *argv* null 포인터를 가리키는 또는 *argv*[0]은 빈 문자열에 잘못 된 에 설명 된 대로 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL**,-1을 반환 합니다. 새로운 프로세스가 생성되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h> 또는 \<process.h>|
|**_wspawnvp**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

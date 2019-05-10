---
title: _spawnle, _wspawnle
ms.date: 11/04/2016
apiname:
- _spawnle
- _wspawnle
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
- spawnle
- _spawnle
- wspawnle
- _wspawnle
helpviewer_keywords:
- spawnle function
- processes, creating
- _wspawnle function
- processes, executing new
- process creation
- wspawnle function
- _spawnle function
ms.assetid: 80308892-2815-49b1-8cca-53894c366f5a
ms.openlocfilehash: 1caa949fab71a7ebc7731c91871e460869ca9f5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355292"
---
# <a name="spawnle-wspawnle"></a>_spawnle, _wspawnle

새 프로세스를 만들고 실행합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
intptr_t _spawnle(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wspawnle(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>매개 변수

*모드*<br/>
호출 프로세스의 실행 모드입니다.

*cmdname*<br/>
실행할 파일의 경로입니다.

*arg0*, *arg1*, ... *argn*<br/>
인수에 대한 포인터 목록입니다. 합니다 *arg0* 인수에 대 한 포인터는 일반적으로 *cmdname*합니다. 인수 *arg1* 를 통해 *argn* 새로운 인수 목록을 구성 하는 문자열에 대 한 포인터입니다. 다음 *argn*에 있어야는 **NULL** 인수 목록의 끝을 표시에 대 한 포인터입니다.

*envp*<br/>
환경 설정에 대한 포인터 배열입니다.

## <a name="return-value"></a>반환 값

반환 값은 동기 **_spawnle** 하거나 **_wspawnle** (**_P_WAIT** 에 대해 지정 된 *모드*) 새 프로세스의 종료 상태 . 비동기 작업의 반환 값 **_spawnle** 하거나 **_wspawnle** (**_P_NOWAIT** 하거나 **_P_NOWAITO** 에 대해 지정 된  *모드*)은 프로세스 핸들입니다. 프로세스가 정상적으로 종료되는 경우 종료 상태는 0입니다. 생성된 된 프로세스를 명확 하 게 호출 하는 경우 종료 상태 0이 아닌 값으로 설정할 수 있습니다 합니다 **종료** 0이 아닌 인수를 사용 하 여 일상적인 합니다. 새 프로세스가 양수 값의 종료 상태를 명시적으로 설정하지 않은 경우, 양수 값의 종료 상태는 중단되거나 인터럽트된 비정상적인 종료를 나타냅니다. 반환 값이-1 (새 프로세스가 시작 되지 않습니다.) 오류를 나타냅니다. 이 예에서 **errno** 다음 값 중 하나로 설정 됩니다.

|||
|-|-|
| **E2BIG** | 인수 목록이 1024바이트를 초과합니다. |
| **EINVAL** | *모드* 인수가 잘못 되었습니다. |
| **ENOENT** | 파일 또는 경로를 찾을 수 없습니다. |
| **ENOEXEC** | 지정한 파일이 실행할 수 없거나 실행 파일 형식이 잘못되었습니다. |
| **ENOMEM** | 메모리가 부족하여 새 프로세스를 실행할 수 없습니다. |

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

이러한 각 함수는 각각의 명령줄 인수를 별도의 매개 변수로 전달하고 포인터 배열을 환경 설정에 전달하는 새 프로세스를 만들고 실행합니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 이면 *cmdname* 또는 *arg0* 빈 문자열 이거나 null 포인터인 경우 잘못 된 매개 변수 처리기가 호출 됩니다에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL**,-1을 반환 합니다. 새로운 프로세스가 생성되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_spawnle**|\<process.h>|
|**_wspawnle**|\<stdio.h> 또는 \<wchar.h>|

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

---
title: _execvpe, _wexecvpe
ms.date: 11/04/2016
apiname:
- _execvpe
- _wexecvpe
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
- wexecvpe
- execvpe
- _wexecvpe
- _execvpe
helpviewer_keywords:
- wexecvpe function
- execvpe function
- _wexecvpe function
- _execvpe function
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
ms.openlocfilehash: 064f8b94a9a97795015c09c11cd56e0370dcc60c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339405"
---
# <a name="execvpe-wexecvpe"></a>_execvpe, _wexecvpe

새 자식 프로세스를 로드하고 실행합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
intptr_t _execvpe(
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wexecvpe(
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>매개 변수

*cmdname*<br/>
실행할 파일의 경로입니다.

*argv*<br/>
매개 변수에 대한 포인터 배열입니다.

*envp*<br/>
환경 설정에 대한 포인터 배열입니다.

## <a name="return-value"></a>반환 값

성공하면 이러한 함수는 호출 프로세스에 값을 반환하지 않습니다. 반환 값이-1 나타냅니다 오류가 있는 경우에 **errno** 전역 변수가 설정 됩니다.

|**errno** 값|설명|
|-------------------|-----------------|
|**E2BIG**|인수 및 환경 설정에 필요한 공간의 크기가 32KB를 초과합니다.|
|**EACCES**|지정한 파일이 잠금 또는 공유 위반이 되었습니다.|
|**EMFILE**|너무 많은 파일이 열려 있습니다. 실행 파일인지 여부를 확인하려면 지정한 파일이 열려 있어야 합니다.|
|**ENOENT**|파일 또는 경로를 찾을 수 없습니다.|
|**ENOEXEC**|지정한 파일이 실행할 수 없거나 실행 파일 형식이 잘못되었습니다.|
|**ENOMEM**|메모리가 부족하여 새 프로세스를 실행할 수 없습니다. 사용 가능한 메모리가 손상되었거나 잘못된 블록이 있습니다. 이는 호출 프로세스가 제대로 할당되지 않았음을 나타냅니다.|

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 새 프로세스를 로드 및 실행하고, 명령줄 인수에 대한 포인터 배열 및 환경 설정에 대한 포인터 배열을 전달합니다. 이러한 함수를 사용 합니다 **경로** 환경 변수를 실행 하려면 파일을 찾습니다.

합니다 **_execvpe** 함수 매개 변수 유효성을 검사 합니다. 경우는 *cmdname* 가 null 포인터 이거나 *argv* null 포인터, 빈 배열에 대 한 포인터 또는 첫 번째 인수로 빈 문자열이 포함 된 배열에 대 한 포인터 이면 이러한 함수는 잘못 된 호출 에 설명 된 대로 매개 변수 처리기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 고-1을 반환 합니다. 프로세스가 시작되지 않습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|선택적 헤더|
|--------------|---------------------|---------------------|
|**_execvpe**|\<process.h>|\<errno.h>|
|**_wexecvpe**|\<process.h> 또는 \<wchar.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

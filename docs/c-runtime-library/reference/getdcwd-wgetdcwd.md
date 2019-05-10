---
title: _getdcwd, _wgetdcwd
ms.date: 11/04/2016
apiname:
- _getdcwd
- _wgetdcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
ms.openlocfilehash: 464a254775d9a1d2488247d6dafb4b85cd763f10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331833"
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd

지정한 드라이브의 현재 작업 디렉터리의 전체 경로를 가져옵니다.

## <a name="syntax"></a>구문

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>매개 변수

*drive*<br/>
드라이브를 지정하는 음수가 아닌 정수입니다(0 = 기본 드라이브, 1 = A, 2 = B 등).

지정된 된 드라이브를 사용할 수 없는 경우 또는 드라이브 유형 (예: 이동식, 고정, CD-ROM, RAM 디스크 또는 네트워크 드라이브)을 확인할 수 없는 잘못 된 매개 변수 처리기가 호출 됩니다. 자세한 내용은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)를 참조하세요.

*buffer*<br/>
경로에 대한 스토리지 위치 또는 **NULL**입니다.

하는 경우 **NULL** 지정 된 경우이 함수에서의 버퍼를 하나 이상 할당 *maxlen* 사용 하 여 크기 **malloc**, 및의 반환 값 **_getdcwd**할당된 된 버퍼에 대 한 포인터입니다. 호출 하 여 버퍼를 해제할 수 있습니다 **무료** 포인터를 전달 합니다.

*maxlen*<br/>
문자에서는 경로의 최대 길이 지정 하는 0이 아닌 양의 정수: **char** 에 대 한 **_getdcwd** 하 고 **wchar_t** 에 대 한 **_wgetdcwd**.

하는 경우 *maxlen* 보다 작거나 0에 잘못 된 매개 변수 처리기를 호출 합니다. 자세한 내용은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)를 참조하세요.

## <a name="return-value"></a>반환 값

지정된 된 드라이브의 현재 작업 디렉터리의 전체 경로 나타내는 문자열에 대 한 포인터 또는 **NULL**, 오류가 나타냅니다.

하는 경우 *버퍼* 로 지정 됩니다 **NULL** 할당할 메모리가 부족 하 고 *maxlen* 문자, 오류가 발생 하 고 **errno** 는 로 **ENOMEM**합니다. Null 종결 문자를 포함 하 여 경로의 길이 초과 하는 경우 *maxlen*, 오류가 발생 하 고 **errno** 로 설정 되어 **ERANGE**합니다. 이러한 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

합니다 **_getdcwd** 함수가 지정된 된 드라이브의 현재 작업 디렉터리의 전체 경로 가져오고에 저장 *버퍼*합니다. 현재 작업 디렉터리가 루트로 설정되는 경우 문자열이 백슬래시(\\)로 끝납니다. 현재 작업 디렉터리가 루트 이외의 디렉터리로 설정되는 경우 문자열은 백슬래시가 아닌 디렉터리의 이름으로 끝납니다.

**_wgetdcwd** 의 와이드 문자 버전이 **_getdcwd**, 및 해당 *버퍼* 매개 변수 및 반환 값은 와이드 문자 문자열입니다. 그렇지 않으면 **_wgetdcwd** 하 고 **_getdcwd** 동일 하 게 작동 합니다.

이 함수는 자체적으로 스레드로부터 안전하지 않는 **GetFullPathName**에 의존하지만 스레드로부터 안전합니다. 다중 스레드 응용 프로그램 모두이 함수를 호출 하는 경우 스레드 안전성을 위반할 수는 있지만 및 [GetFullPathNameA](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)합니다.

이 함수의 버전은는 **_nolock** 접미사 동일 하 게 동작이 함수는 스레드로부터 안전 하지 않습니다 하 고 다른 스레드의 간섭 으로부터 보호 되지 한다는 합니다. 자세한 내용은 [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md)을 참조하세요.

때 **_DEBUG** 하 고 **_CRTDBG_MAP_ALLOC** 정의 된, 호출 하는 **_getdcwd** 하 고 **_wgetdcwd** 를호출하여대체됩니다 **_getdcwd_dbg** 하 고 **_wgetdcwd_dbg** 메모리 할당을 디버그할 수 있도록 합니다. 자세한 내용은[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_getdrive](getdrive.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>

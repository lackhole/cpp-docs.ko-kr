---
title: _getcwd_dbg, _wgetcwd_dbg
ms.date: 11/04/2016
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
ms.openlocfilehash: 9616c5f7e29b4f003d3943ba058d1f1a1d5adb5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287230"
---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg

[_getcwd, _wgetcwd](getcwd-wgetcwd.md) 함수의 디버그 버전입니다(디버그 중에만 사용 가능).

## <a name="syntax"></a>구문

```C
char *_getcwd_dbg(
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetcwd_dbg(
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
경로의 스토리지 위치입니다.

*maxlen*<br/>
문자에서는 경로의 최대 길이: **char** 에 대 한 **_getcwd_dbg** 하 고 **wchar_t** 에 대 한 **_wgetcwd_dbg**합니다.

*blockType*<br/>
요청 된 메모리 블록의 형식: **_CLIENT_BLOCK** 하거나 **_NORMAL_BLOCK**합니다.

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 있는 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 *버퍼*합니다. A **NULL** 반환 값은 오류를 나타내고 및 **errno** 설정 됩니다 **ENOMEM**를 할당할 메모리가 부족 한지를 나타내는 *maxlen* 바이트 (경우는 **NULL** 인수도 제공 됩니다 *버퍼*), 또는 **ERANGE**, 경로 보다 긴 임을 나타내는 *maxlen*  문자입니다.

자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **_getcwd_dbg** 하 고 **_wgetcwd_dbg** 함수는 동일 **_getcwd** 및 **_wgetcwd** 점을 제외 하 고, **_ 디버그** 은의 디버그 버전을 사용 하 여 이러한 함수를 정의 **malloc** 및 **_malloc_dbg** 하는 경우 메모리를 할당할 **NULL** 로 전달 되는 첫 번째 매개 변수입니다. 자세한 내용은 [_malloc_dbg](malloc-dbg.md)를 참조하세요.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 정의할 수 있습니다 합니다 **_CRTDBG_MAP_ALLOC** 플래그입니다. 때 **_CRTDBG_MAP_ALLOC** 에 대 한 호출을 정의 하면 **_getcwd** 하 고 **_wgetcwd** 로 다시 매핑되고 **_getcwd_dbg** 및 **_ wgetcwd_dbg**각각 사용 하 여 합니다 *blockType* 로 설정 **_NORMAL_BLOCK**합니다. 따라서 힙 블록으로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다 **_CLIENT_BLOCK**합니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

## <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h>|
|**_wgetcwd_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>

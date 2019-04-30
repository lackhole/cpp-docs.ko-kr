---
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
apiname:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
ms.openlocfilehash: b84c5b77d0a9bfb298d4c597e372cd39a92441f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332951"
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg

버전의 [_fullpath, _wfullpath](fullpath-wfullpath.md) 의 디버그 버전을 사용 하는 **malloc** 메모리를 할당 합니다.

## <a name="syntax"></a>구문

```C
char *_fullpath_dbg(
   char *absPath,
   const char *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wfullpath_dbg(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*absPath*<br/>
절대 또는 전체 경로 이름을 포함 하는 버퍼에 대 한 포인터 또는 **NULL**합니다.

*relPath*<br/>
상대 경로 이름입니다.

*maxLength*<br/>
절대 경로 이름 버퍼의 최대 길이 (*absPath*). 이 길이 바이트 단위로 **_fullpath** 있지만 와이드 문자에서 (**wchar_t**)에 대 한 **_wfullpath**합니다.

*blockType*<br/>
요청 된 메모리 블록의 형식: **_CLIENT_BLOCK** 하거나 **_NORMAL_BLOCK**합니다.

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 있는 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

절대 경로 이름을 포함 하는 버퍼에 대 한 포인터를 반환 하는 각 함수 (*absPath*). 오류가 발생 하는 경우 (값을 전달 하는 경우에 예를 들어 *relPath* 유효 하지 않거나 찾을 수 없는 드라이브 문자가 포함 경우 또는 작성된 된 절대 경로 이름의 길이 (*absPath*) 보다 *maxLength*)를 반환 **NULL**합니다.

## <a name="remarks"></a>설명

합니다 **_fullpath_dbg** 하 고 **_wfullpath_dbg** 함수는 동일 **_fullpath** 및 **_wfullpath** 점을 제외 하 고, **_DEBUG** 는 정의 된 이러한 함수 사용의 디버그 버전 **malloc**를 **_malloc_dbg**메모리를 할당 하는 경우 **NULL** 전달 됩니다 첫 번째 매개 변수입니다. 디버깅 기능에 대 한 내용은 **_malloc_dbg**를 참조 하십시오 [_malloc_dbg](malloc-dbg.md)합니다.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 정의할 수 있습니다 합니다 **_CRTDBG_MAP_ALLOC** 플래그입니다. 때 **_CRTDBG_MAP_ALLOC** 에 대 한 호출을 정의 하면 **_fullpath** 하 고 **_wfullpath** 로 다시 매핑되고 **_fullpath_dbg** 및 **_wfullpath_dbg**각각 사용 하 여는 *blockType* 로 설정 **_NORMAL_BLOCK**합니다. 따라서 힙 블록으로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다 **_CLIENT_BLOCK**합니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>

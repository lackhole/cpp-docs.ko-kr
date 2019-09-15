---
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
api_name:
- _wfullpath_dbg
- _fullpath_dbg
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 9271e26bcf4a78ff8d2e4fcf108f1e483c22c1d7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956305"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg, _wfullpath_dbg

**Malloc** 의 디버그 버전을 사용 하 여 메모리를 할당 하는 [_fullpath, _wfullpath](fullpath-wfullpath.md) 의 버전입니다.

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
절대 또는 전체 경로 이름이 나 **NULL**을 포함 하는 버퍼에 대 한 포인터입니다.

*relPath*<br/>
상대 경로 이름입니다.

*maxLength*<br/>
절대 경로 이름 버퍼의 최대 길이 (*absPath*)입니다. 이 길이는 **_fullpath** 에 대 한 바이트 단위 이지만 **_wfullpath**의 경우 와이드 문자 (**wchar_t**)입니다.

*blockType*<br/>
요청 된 메모리 블록 형식: **_CLIENT_BLOCK** 또는 **_NORMAL_BLOCK**.

*filename*<br/>
할당 작업 또는 **NULL**을 요청한 소스 파일의 이름에 대 한 포인터입니다.

*linenumber*<br/>
할당 작업이 요청 되었거나 **NULL 인**소스 파일의 줄 번호입니다.

## <a name="return-value"></a>반환 값

각 함수는 절대 경로 이름 (*absPath*)을 포함 하는 버퍼에 대 한 포인터를 반환 합니다. 오류가 있는 경우 (예: *relPath* 에 전달 된 값에 잘못 되었거나 찾을 수 없는 드라이브 문자가 포함 된 경우 또는 생성 된 절대 경로 이름 (*absPath*)의 길이가 *maxLength*보다 큰 경우) 함수는를 반환 **합니다. NULL**입니다.

## <a name="remarks"></a>설명

**_Fullpath_dbg** 및 **_Wfullpath_dbg** 함수는 **_debug** 가 정의 되 면 이러한 함수가 **malloc**, **_malloc_dbg**, 디버그 버전을 사용 한다는 점을 제외 하 고 **_fullpath** 및 **_wfullpath** 와 동일 합니다. **NULL** 이 첫 번째 매개 변수로 전달 되는 경우 메모리를 할당 합니다. **_Malloc_dbg**의 디버깅 기능에 대 한 자세한 내용은 [_malloc_dbg](malloc-dbg.md)를 참조 하세요.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 **_CRTDBG_MAP_ALLOC** 플래그를 정의할 수 있습니다. **_CRTDBG_MAP_ALLOC** 가 정의 되 면 **_fullpath** 및 **_wfullpath** 에 대 한 호출은 각각 **_wfullpath_dbg**로 설정 된 *blocktype* 을 사용 하 여 **_fullpath_dbg** 및 **_NORMAL_BLOCK**에 다시 매핑됩니다. 따라서 힙 블록을 **_CLIENT_BLOCK**로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

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

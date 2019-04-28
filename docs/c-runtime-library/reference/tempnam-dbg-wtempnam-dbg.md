---
title: _tempnam_dbg, _wtempnam_dbg
ms.date: 11/04/2016
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
ms.openlocfilehash: 804c8ad1f17c6ee1df563cafc69ee7aef494d1cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258138"
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg

함수 버전 [_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) 의 디버그 버전을 사용 하는 **malloc**하십시오 **_malloc_dbg**합니다.

## <a name="syntax"></a>구문

```C
char *_tempnam_dbg(
   const char *dir,
   const char *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wtempnam_dbg(
   const wchar_t *dir,
   const wchar_t *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*dir*<br/>
TMP 환경 함수가 없는 경우 또는 TMP가 올바른 디렉터리가 아닌 경우 파일 이름에 사용되는 경로입니다.

*prefix*<br/>
반환 하는 이름에 붙일 수 있는 문자열 **_tempnam**합니다.

*blockType*<br/>
요청 된 메모리 블록의 형식: **_CLIENT_BLOCK** 하거나 **_NORMAL_BLOCK**합니다.

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 되는 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

각 함수는 생성 된 이름에 대 한 포인터를 반환 하거나 **NULL** 오류가 발생 하는 경우. TMP 환경 변수에서 지정 된 잘못 된 디렉터리 이름이 오류가 발생할 수 있습니다 합니다 *dir* 매개 변수입니다.

> [!NOTE]
> **사용 가능한** (또는 **free_dbg**)에서 할당 한 포인터를 호출할 필요가 **_tempnam_dbg** 하 고 **_wtempnam_dbg**합니다.

## <a name="remarks"></a>설명

합니다 **_tempnam_dbg** 하 고 **_wtempnam_dbg** 함수는 동일 **_tempnam** 및 **_wtempnam** 점을 제외 하 고, **_DEBUG** 는 정의 된 이러한 함수 사용의 디버그 버전 **malloc** 하 고 **_malloc_dbg**메모리를 할당 하는 경우 **NULL** 는 첫 번째 매개 변수로 전달 합니다. 자세한 내용은 [_malloc_dbg](malloc-dbg.md)를 참조하세요.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 플래그를 정의할 수 있습니다 **_CRTDBG_MAP_ALLOC**합니다. 때 **_CRTDBG_MAP_ALLOC** 에 대 한 호출을 정의 하면 **_tempnam** 하 고 **_wtempnam** 로 다시 매핑되고 **_tempnam_dbg** 및 **_ wtempnam_dbg**각각 사용 하 여 합니다 *blockType* 로 설정 **_NORMAL_BLOCK**합니다. 따라서 힙 블록으로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다 **_CLIENT_BLOCK**합니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>

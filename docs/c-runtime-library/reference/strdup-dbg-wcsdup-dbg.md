---
title: _strdup_dbg, _wcsdup_dbg
ms.date: 11/04/2016
api_name:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
ms.openlocfilehash: 9f7d4fd8781269ee37f7515fdcab72e5195fdf00
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958195"
---
# <a name="_strdup_dbg-_wcsdup_dbg"></a>_strdup_dbg, _wcsdup_dbg

**Malloc**의 디버그 버전을 사용 하는 [_strdup 및 _wcsdup](strdup-wcsdup-mbsdup.md) 의 버전입니다.

## <a name="syntax"></a>구문

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
Null 종료 소스 문자열입니다.

*blockType*<br/>
요청 된 메모리 블록 형식: **_CLIENT_BLOCK** 또는 **_NORMAL_BLOCK**.

*filename*<br/>
할당 작업 또는 **NULL**을 요청한 소스 파일의 이름에 대 한 포인터입니다.

*linenumber*<br/>
할당 작업이 요청 되었거나 **NULL 인**소스 파일의 줄 번호입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 복사 된 문자열의 저장소 위치에 대 한 포인터를 반환 하거나, 저장소를 할당할 수 없는 경우 **NULL** 을 반환 합니다.

## <a name="remarks"></a>설명

**_Strdup_dbg** 및 **_Wcsdup_dbg** 함수는 **_debug** 가 정의 되 면 이러한 함수가 **malloc**, **_malloc_dbg**의 디버그 버전을 사용 하 여를 할당 한다는 점을 제외 하 고는 **_strdup** 및 **_wcsdup** 와 동일 합니다. 중복 된 문자열에 대 한 메모리입니다. **_Malloc_dbg**의 디버깅 기능에 대 한 자세한 내용은 [_malloc_dbg](malloc-dbg.md)를 참조 하세요.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 **_CRTDBG_MAP_ALLOC**플래그를 정의할 수 있습니다. **_CRTDBG_MAP_ALLOC** 가 정의 되 면 **_strdup** **및**_Wcsrrssrrssrrrrrrrrrrrrrrra가 **_NORMAL_BLOCK** *로 설정 된 상태에서 각각* **_strdup_dbg** 따라서 힙 블록을 **_CLIENT_BLOCK**로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다. 블록 형식에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strdup_dbg**, **_wcsdup_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 디버그 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup, _wcsdup, _mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>

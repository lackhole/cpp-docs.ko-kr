---
title: _strdup, _wcsdup, _mbsdup
ms.date: 11/04/2016
apiname:
- _strdup
- _mbsdup
- _wcsdup
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
ms.openlocfilehash: 094843fdb1432aa58ec04b3b4e39ac8861b928ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353902"
---
# <a name="strdup-wcsdup-mbsdup"></a>_strdup, _wcsdup, _mbsdup

문자열을 복제합니다.

> [!IMPORTANT]
> **_mbsdup** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.

## <a name="syntax"></a>구문

```C
char *_strdup(
   const char *strSource
);
wchar_t *_wcsdup(
   const wchar_t *strSource
);
unsigned char *_mbsdup(
   const unsigned char *strSource
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
Null 종료 소스 문자열입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 복사한 문자열의 저장소 위치에 대 한 포인터를 반환 하거나 **NULL** 저장소를 할당할 수 없는 경우.

## <a name="remarks"></a>설명

합니다 **_strdup** 함수 호출 [malloc](malloc.md) 복사본에 대 한 저장소 공간을 할당할 *strSource* 복사 *strSource* 에 할당 된 공간입니다.

**_wcsdup** 하 고 **_mbsdup** 와이드 문자 및 멀티 바이트 문자 버전입니다 **_strdup**합니다. 인수 및 반환 값 **_wcsdup** 은 와이드 문자열이 고 **_mbsdup** 는 멀티 바이트 문자 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup**|**_strdup**|**_mbsdup**|**_wcsdup**|

때문에 **_strdup** 호출 **malloc** 복사본에 대 한 저장소 공간을 할당할 *strSource*, 항상 합니다 호출하여이메모리를해제하는것이좋습니다[여유](free.md) 호출에서 반환 되는 포인터에 대 한 일상적인 **_strdup**합니다.

하는 경우 **_DEBUG** 하 고 **_CRTDBG_MAP_ALLOC** 정의 된 **_strdup** 하 고 **_wcsdup** 호출으로 대체 됩니다 **_strdup_dbg**  하 고 **_wcsdup_dbg** 메모리 할당 디버깅을 허용 합니다. 자세한 내용은 [_strdup_dbg, _wcsdup_dbg](strdup-dbg-wcsdup-dbg.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strdup**|\<string.h>|
|**_wcsdup**|\<string.h> 또는 \<wchar.h>|
|**_mbsdup**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strdup.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is the buffer text";
   char *newstring;
   printf( "Original: %s\n", buffer );
   newstring = _strdup( buffer );
   printf( "Copy:     %s\n", newstring );
   free( newstring );
}
```

```Output
Original: This is the buffer text
Copy:     This is the buffer text
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>

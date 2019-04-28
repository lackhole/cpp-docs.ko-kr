---
title: _unlink, _wunlink
ms.date: 11/04/2016
apiname:
- _unlink
- _wunlink
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tunlink
- _unlink
- wunlink
- _wunlink
helpviewer_keywords:
- files [C++], deleting
- _wunlink function
- wunlink function
- unlink function
- _unlink function
- tunlink function
- files [C++], removing
- _tunlink function
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
ms.openlocfilehash: ec59a02f1302fe4a2149889cf1b48090d061d6b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268774"
---
# <a name="unlink-wunlink"></a>_unlink, _wunlink

파일을 삭제합니다.

## <a name="syntax"></a>구문

```C
int _unlink(
   const char *filename
);
int _wunlink(
   const wchar_t *filename
);
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
제거할 파일의 이름입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 정상적으로 실행되면 0을 반환합니다. 함수가-1을 반환 하는 고, 그렇지 집합과 **errno** 하 **EACCES**, 읽기 전용 파일 또는 디렉터리를 지정 경로 즉 또는 **ENOENT**, 즉, 파일 또는 경로 가 없습니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **_unlink** 함수에서 지정한 파일을 삭제 *filename*합니다. **_wunlink** 의 와이드 문자 버전이 **_unlink**; *filename* 인수를 **_wunlink** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tunlink**|**_unlink**|**_unlink**|**_wunlink**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_unlink**|\<io.h> 및 \<stdio.h>|
|**_wunlink**|\<io.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="code-example"></a>코드 예제

이 프로그램은 _unlink를 사용하여 CRT_UNLINK.TXT를 삭제합니다.

```C
// crt_unlink.c

#include <stdio.h>

int main( void )
{
   if( _unlink( "crt_unlink.txt" ) == -1 )
      perror( "Could not delete 'CRT_UNLINK.TXT'" );
   else
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );
}
```

### <a name="input-crtunlinktxt"></a>입력: crt_unlink.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>샘플 출력

```Output
Deleted 'CRT_UNLINK.TXT'
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[remove, _wremove](remove-wremove.md)<br/>

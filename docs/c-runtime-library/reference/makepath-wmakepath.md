---
title: _makepath, _wmakepath
ms.date: 11/04/2016
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: 073f8aba6936aa33dafcef7ed47f5286802a4948
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285701"
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath

구성 요소에서 경로 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>매개 변수

*path*<br/>
전체 경로 버퍼입니다.

*drive*<br/>
원하는 드라이브에 따른 문자(A, B 등) 및 후행 콜론(선택 사항)을 포함합니다. **_makepath** 없을 경우 복합 경로에 콜론을 자동으로 삽입 합니다. 하는 경우 *드라이브* 됩니다 **NULL** 복합 빈 문자열을 가리킵니다, 드라이브 문자 없이 표시 *경로* 문자열입니다.

*dir*<br/>
드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다. 후행 슬래시는 선택 사항, 슬래시 (/) 또는 백슬래시 (\\) 또는 둘 다에서 사용 하는 단일 *dir* 인수입니다. 후행 슬래시(/ 또는 \\)가 지정되지 않은 경우 자동으로 삽입됩니다. 하는 경우 *dir* 됩니다 **NULL** 또는 복합에서 빈 문자열로, 디렉터리 경로가 없는 지점에 삽입 됩니다 *경로* 문자열입니다.

*fname*<br/>
파일 확장명 없이 기본 파일 이름을 포함합니다. 하는 경우 *fname* 됩니다 **NULL** 또는 빈 문자열인 경우 없는 파일 이름 가리킵니다 복합에 삽입 됩니다 *경로* 문자열입니다.

*ext*<br/>
앞에 마침표(.)가 있거나 없는 실제 파일 확장명을 포함합니다. **_makepath** 에 나타나지 않으면 기간에 자동으로 삽입 *ext*합니다. 하는 경우 *ext* 됩니다 **NULL** 또는 빈 문자열인 경우 확장명이 없는 가리키는 복합에 삽입 됩니다 *경로* 문자열입니다.

## <a name="remarks"></a>설명

합니다 **_makepath** 함수에서 결과 저장 하는 개별 구성 요소에서 복합 경로 문자열을 만듭니다 *경로*합니다. 합니다 *경로* 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장명 포함 될 수 있습니다. **_wmakepath** 의 와이드 문자 버전이 **_makepath**;에 대 한 인수 **_wmakepath** 는 와이드 문자 문자열입니다. **_wmakepath** 하 고 **_makepath** 동일 하 게 작동 합니다.

**보안 정보** null로 끝나는 문자열을 사용하세요. 버퍼 오버런을 방지 하려면 null로 끝나는 문자열의 크기를 넘지 않아야 합니다 *경로* 버퍼입니다. **_makepath** 복합 경로 문자열의 길이 초과 하지 않는지를 보장 하지 않습니다 **_max_path(256**합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

합니다 *경로* 인수를 전체 경로 저장할 만큼 큰 빈 버퍼를 가리켜야 합니다. 복합 *경로* 보다 크지 않아야 합니다 **_max_path(256** Stdlib.h에 정의 된 상수입니다.

경로가 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 또한 **errno** 로 설정 된 **EINVAL**합니다. **NULL** 다른 모든 매개 변수에 대해 값이 허용 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>

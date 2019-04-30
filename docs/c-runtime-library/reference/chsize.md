---
title: _chsize
ms.date: 03/29/2018
apiname:
- _chsize
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
apitype: DLLExport
f1_keywords:
- _chsize
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
ms.openlocfilehash: 5c60f3aa08a405eb9a83dc6ba8636cd316a32925
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340328"
---
# <a name="chsize"></a>_chsize

파일 크기를 변경합니다. 더 안전한 버전을 사용할 수 있습니다. [_chsize_s](chsize-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

*size*<br/>
파일의 새 길이(바이트)입니다.

## <a name="return-value"></a>반환 값

**_chsize** 파일 크기 변경이 완료 되는 경우 값 0을 반환 합니다. 반환 값이-1은 오류를 나타냅니다: **errno** 로 설정 되어 **EACCES** 지정 된 파일이 읽기 전용인 지 여부 지정된 된 파일에 액세스에 대해 잠긴 경우 **EBADF** 경우는 설명자 올바르지 **ENOSPC** 장치에 남아 있는 공간이 없는 경우 또는 **EINVAL** 하는 경우 *크기* 가 0 보다 작습니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **_chsize** 함수를 확장 또는 연결 된 파일을 자릅니다 *fd* 하 여 지정 된 길이로 *크기*합니다. 파일은 쓰기를 허용하는 모드로 열려 있어야 합니다. 파일이 확장되는 경우 Null 문자('\0')가 추가됩니다. 파일이 잘린 경우 짧아진 파일의 끝부터 파일의 원래 길이까지의 모든 데이터가 손실됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *크기* 가 0 보다 작거나 또는 *fd* 잘못 된 파일 설명자 인에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_chsize.c
// This program uses _filelength to report the size
// of a file before and after modifying it with _chsize.

#include <io.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh, result;
   unsigned int nbytes = BUFSIZ;

   // Open a file
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,
                 _S_IREAD | _S_IWRITE ) == 0 )
   {
      printf( "File length before: %ld\n", _filelength( fh ) );
      if( ( result = _chsize( fh, 329678 ) ) == 0 )
         printf( "Size successfully changed\n" );
      else
         printf( "Problem in changing the size\n" );
      printf( "File length after:  %ld\n", _filelength( fh ) );
      _close( fh );
   }
}
```

```Output
File length before: 0
Size successfully changed
File length after:  329678
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>

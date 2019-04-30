---
title: _read
ms.date: 02/13/2019
apiname:
- _read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: 40f52ea37ae5419fe986aa505aad4fddfe8403ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357657"
---
# <a name="read"></a>_read

파일에서 데이터를 읽습니다.

## <a name="syntax"></a>구문

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

*buffer*<br/>
데이터의 스토리지 위치입니다.

*buffer_size*<br/>
읽을 바이트의 최대 수입니다.

## <a name="return-value"></a>반환 값

**_read** 작을 수 있으며는 읽은 바이트 수를 반환 합니다 보다 *buffer_size* 개 보다 적으면 *buffer_size* 파일에 남아 있는 바이트 또는 텍스트 모드에서 파일을 연 경우. 텍스트 모드에서 각 캐리지 리턴-줄 바꿈 쌍 `\r\n` 단일 줄 바꿈 문자로 바뀝니다 `\n`합니다. 반환 값에서는 단일 줄 바꿈 문자만 계산됩니다. 이러한 바꾸기는 파일 포인터에 영향을 주지 않습니다.

함수는 파일의 끝에서 읽기를 시도하는 경우 0을 반환합니다. 하는 경우 *fd* 은 유효 하지 않은 파일이 열려 있지 않으면 읽기 또는 파일이 잠겨에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행 함수는-1 반환 하 고 집합을 계속 하도록 허용 된 경우 **errno** 하 **EBADF**합니다.

하는 경우 *버퍼* 됩니다 **NULL**, 이거나 *buffer_size* > **INT_MAX**, 잘못 된 매개 변수 처리기가 호출 됩니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 **errno** 로 설정 된 **EINVAL**합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

**_read** 함수는 최대를 읽습니다 *buffer_size* 바이트 *버퍼* 연관 된 파일에서 *fd*합니다. 읽기 작업은 지정된 파일과 연결된 파일 포인터의 현재 위치에서 시작됩니다. 읽기 작업 후 파일 포인터는 읽지 않은 다음 문자를 가리킵니다.

읽기 종료 될 때 파일이 텍스트 모드로 열려 있으면 **_read** 파일 끝 표시기로 간주 되는 CTRL + Z 문자를 발견 합니다. 파일 끝 표시기를 지우려면 [_lseek](lseek-lseeki64.md)를 사용합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_read**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh, bytesread;
   unsigned int nbytes = 60000;

   /* Open file for input: */
   if ( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ))
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if (( bytesread = _read( fh, buffer, nbytes )) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crtreadtxt"></a>입력: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>

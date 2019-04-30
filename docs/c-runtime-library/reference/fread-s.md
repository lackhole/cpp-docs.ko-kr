---
title: fread_s
ms.date: 11/04/2016
apiname:
- fread_s
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
- fread_s
- stdio/fread_s
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
ms.openlocfilehash: 898e813c19fd53cfdacd536c2e9819743a62a8da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287813"
---
# <a name="freads"></a>fread_s

스트림에서 데이터를 읽습니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 이 버전의 [fread](fread.md)에 대한 보안 기능이 향상되었습니다.

## <a name="syntax"></a>구문

```C
size_t fread_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
데이터의 스토리지 위치입니다.

*bufferSize*<br/>
출력 버퍼의 바이트 크기입니다.

*elementSize*<br/>
읽을 항목의 크기(바이트)입니다.

*count*<br/>
읽힐 항목의 최대 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fread_s** 일 수 있는 버퍼로 읽은 (전체) 번호 항목을 반환 미만 *개수* 읽기 오류 또는 파일 끝 하기 전에 발생 하는 경우 *개수* 에 도달 하면 합니다. 사용 된 **feof** 또는 **ferror** 오류가 파일 끝 조건을 구분 하기 위해 함수입니다. 하는 경우 *크기* 또는 *개수* 0 **fread_s** 0 고 버퍼 콘텐츠가 변경 되지 않은 반환 합니다. 하는 경우 *스트림을* 하거나 *버퍼* 가 null 포인터 **fread_s** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) . 이 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** 0을 반환 합니다.

오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**fread_s** 함수를 읽고 *개수* 항목 *elementSize* 입력에서 바이트 *stream* 에저장합니다*버퍼*합니다.  연결 된 파일 포인터 *스트림을* (있는 경우) 실제로 읽는 바이트 수 만큼 증가 됩니다. 지정된 된 스트림에 텍스트 모드로 열리면, 캐리지 리턴-줄 바꿈 쌍 단일 줄 바꿈 문자로 바뀝니다. 이렇게 바뀌더라도 파일 포인터 또는 반환 값에는 영향을 미치지 않습니다. 오류가 발생할 경우 파일 포인터 위치는 비활성화 상태입니다. 부분적으로 읽은 항목의 값은 확인할 수 없습니다.

이 함수는 다른 스레드를 잠급니다. 잠기지 않는 버전에 필요한 경우 사용할 **_fread_nolock**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fread_s**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_fread_s.c
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c
//
// This program opens a file that's named FREAD.OUT and
// writes characters to the file. It then tries to open
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

#define BUFFERSIZE 30
#define DATASIZE 22
#define ELEMENTCOUNT 2
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)
#define FILENAME "FREAD.OUT"

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   for ( i = 0; i < DATASIZE; i++ )
      list[i] = (char)('z' - i);
   list[DATASIZE] = '\0'; // terminal null so we can print it

   // Open file in text mode:
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )
   {
      // Write DATASIZE characters to stream
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );
      printf( "Wrote %d items\n\n", numwritten );
      fclose( stream );
   } else {
      printf( "Problem opening the file\n" );
      return -1;
   }

   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {
      // Attempt to read in characters in 2 blocks of 11
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );
      printf( "Contents of buffer after write/read:\n\t%s\n", list );
      fclose( stream );
   } else {
      printf( "File could not be opened\n" );
      return -1;
   }
}
```

```Output
Contents of buffer before write/read:
        zyxwvutsrqponmlkjihgfe

Wrote 22 items

Number of 11-byte elements read = 2

Contents of buffer after write/read:
        zyxwvutsrqponmlkjihgfe
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>

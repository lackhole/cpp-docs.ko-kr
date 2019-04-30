---
title: _dup, _dup2
ms.date: 11/04/2016
apiname:
- _dup
- _dup2
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
- _dup2
- _dup
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
ms.openlocfilehash: a00b9506102e6b274a9aa87c33c144d75cfc2508
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288968"
---
# <a name="dup-dup2"></a>_dup, _dup2

열려 있는 파일에 대 한 두 번째 파일 설명자를 만듭니다 (**_dup**), 파일 설명자를 다시 할당 하거나 (**_dup2**).

## <a name="syntax"></a>구문

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>매개 변수

*fd*, *fd1*<br/>
열려 있는 파일을 나타내는 파일 설명자입니다.

*fd2*<br/>
모든 파일 설명자입니다.

## <a name="return-value"></a>반환 값

**_dup** 새 파일 설명자를 반환 합니다. **_dup2** 성공을 나타내기 위해 0을 반환 합니다. 오류가 발생 하는 각 함수는-1 반환 하 고 설정 하는 경우 **errno** 하 **EBADF** 파일 설명자가 올바르지 않은 경우 또는 **EMFILE** 없습니다 더 이상 파일 설명자를 사용할 수 있는 경우. 잘못된 파일 설명자의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

합니다 **_dup** 하 고 **_dup2** 함수는 현재 열려 있는 파일을 사용 하 여 두 번째 파일 설명자를 연결 합니다. 이러한 함수에 대 한 것과 같은 미리 정의 된 파일 설명자를 연결 하려면 사용할 수 있습니다 **stdout**, 다른 파일을 사용 하 여 합니다. 파일 설명자 중 하나를 사용하여 파일 작업을 수행할 수 있습니다. 파일에 허용된 액세스 형식은 새 설명자 만들기의 영향을 받지 않습니다. **_dup** 지정된 된 파일에 대 한 다음 사용 가능한 파일 설명자를 반환 합니다. **_dup2** 강제로 *fd2* 와 동일한 파일을 가리키도록 *fd1*합니다. 하는 경우 *fd2* 관련이 호출 시 열려 있는 파일을 사용 하 여 해당 파일이 닫힙니다.

둘 다 **_dup** 하 고 **_dup2** 파일 설명자 매개 변수로 수락 합니다. 스트림을 전달할 (`FILE *`) 이러한 함수 중 하나를 사용 하 여 [_fileno](fileno.md)합니다. 합니다 **fileno** 루틴은 지정 된 스트림과 현재 연결 된 파일 설명자를 반환 합니다. 다음 예제에서는 연결 하는 방법을 보여 줍니다 **stderr** (으로 정의 `FILE *` Stdio.h에) 파일 설명자를 사용 합니다.

```C
int cstderr = _dup( _fileno( stderr ));
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_dup**|\<io.h>|
|**_dup2**|\<io.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_dup.c
// This program uses the variable old to save
// the original stdout. It then opens a new file named
// DataFile and forces stdout to refer to it. Finally, it
// restores stdout to its original state.

#include <io.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int old;
   FILE *DataFile;

   old = _dup( 1 );   // "old" now refers to "stdout"
                      // Note:  file descriptor 1 == "stdout"
   if( old == -1 )
   {
      perror( "_dup( 1 ) failure" );
      exit( 1 );
   }
   _write( old, "This goes to stdout first\n", 26 );
   if( fopen_s( &DataFile, "data", "w" ) != 0 )
   {
      puts( "Can't open file 'data'\n" );
      exit( 1 );
   }

   // stdout now refers to file "data"
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )
   {
      perror( "Can't _dup2 stdout" );
      exit( 1 );
   }
   puts( "This goes to file 'data'\n" );

   // Flush stdout stream buffer so it goes to correct file
   fflush( stdout );
   fclose( DataFile );

   // Restore original stdout
   _dup2( old, 1 );
   puts( "This goes to stdout\n" );
   puts( "The file 'data' contains:" );
   _flushall();
   system( "type data" );
}
```

```Output
This goes to stdout first
This goes to stdout

The file 'data' contains:
This goes to file 'data'
```

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>

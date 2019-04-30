---
title: _write
ms.date: 11/04/2016
apiname:
- _write
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
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: b3fa53b21d4ea23c5f8e59de673f4074deedb505
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383414"
---
# <a name="write"></a>_write

파일에 데이터를 씁니다.

## <a name="syntax"></a>구문

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
데이터를 쓸 파일의 파일 설명자입니다.

*buffer*<br/>
쓸 데이터입니다.

*count*<br/>
바이트 수입니다.

## <a name="return-value"></a>반환 값

성공 하면 **_write** 실제로 쓴 바이트 수를 반환 합니다. 실제 디스크에 남아 있는 공간을 사용 하면 함수를 디스크에 작성 하는 버퍼의 크기 보다 작으면 **_write** 실패 하 고 플러시하지 않습니다 모든 버퍼의 내용을 디스크에 있습니다. 반환 값이-1 오류를 나타냅니다. 잘못된 매개 변수가 전달되면 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 **errno** 세 가지 값 중 하나로 설정 됩니다. **EBADF**, 파일 설명자를 의미 하는 유효 하지 않거나 파일을 쓰기에 대 한 열은 **ENOSPC**, 의미 없는 충분 한 공간이 장치에 남아 있는 작업에 대 한 또는 **EINVAL**, 즉 *버퍼* 가 null 포인터 이거나는 경상 *개수* 바이트의 유니코드 모드에서 파일을 쓸 수 있도록 전달 되었습니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

파일을 텍스트 모드에서 열면 각 줄 바꿈 문자는 캐리지 리턴-줄 바꿈 쌍 출력에서으로 대체 됩니다. 바뀌더라도 반환 값에는 영향을 미치지 않습니다.

유니코드 변환 모드로 파일을 열면-예를 들어 경우 *fd* 사용 하 여 **_open** 또는 **_sopen** 및 포함 된 모드 매개 변수 **_O_ WTEXT**, **_O_U16TEXT**, 또는 **_O_U8TEXT**를 사용 하 여는 것이 열려 있는지 또는 **fopen** 포함 된 모드 매개 변수 **ccs = 유니코드**, **ccs = u t F-16LE**, 또는 **ccs = u t F-8**를 사용 하 여 모드를 유니코드 변환 모드로 변경 된 경우 또는 **_setmode**-*버퍼* 배열에 대 한 포인터로 해석 됩니다 **wchar_t** 포함 하는 **u t F-16** 데이터입니다. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.

## <a name="remarks"></a>설명

합니다 **_write** 쓰기 함수 *개수* 바이트 *버퍼* 연관 된 파일에 *fd*합니다. 쓰기 작업은 지정된 파일과 연결된 파일 포인터(있는 경우)의 현재 위치에서 시작됩니다. 추가의 목적으로 파일을 연 경우 쓰기 작업은 파일의 현재 끝에서 시작됩니다. 쓰기 작업 후 파일 포인터는 실제로 쓴 바이트 수만큼 증가됩니다.

텍스트 모드에서 열린 파일에 쓸 때 **_write** 논리-의-파일 끝에 CTRL + Z 문자 취급 합니다. 장치에 쓸 때 **_write** 를 출력 종결자로 버퍼의 CTRL + Z 문자를 처리 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_write**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occured
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>

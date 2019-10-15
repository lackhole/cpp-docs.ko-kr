---
title: ftell, _ftelli64
ms.date: 11/04/2016
api_name:
- _ftelli64
- ftell
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: fda309420e6ae241d3c8ed73c3d41c8ae50de662
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956449"
---
# <a name="ftell-_ftelli64"></a>ftell, _ftelli64

파일 포인터의 현재 위치를 가져옵니다.

## <a name="syntax"></a>구문

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
대상 **파일** 구조.

## <a name="return-value"></a>반환 값

현재 파일 위치 **를 반환** 합니다. 텍스트 모드에서 캐리지 리턴-줄 바꿈 변환을 수행 하기 때문에 **ftell** 및 **_ftelli64** 에서 반환 된 값에는 텍스트 모드로 연 스트림의 실제 바이트 오프셋이 반영 되지 않을 수 있습니다. **ftell**과 함께 [fseek](fseek-fseeki64.md) 또는 **_ftelli64**와 함께 [_fseeki64](fseek-fseeki64.md)를 사용하여 파일 위치로 돌아옵니다. 오류가 발생 하는 경우에는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 **ftell** 및 **_ftelli64** 에서 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우 이러한 함수는-1L을 반환 하 고 **errno** 를 errno에 정의 된 두 상수 중 하나로 설정 합니다. 넣기. **Ebadf** 상수는 *stream* 인수가 잘못 된 파일 포인터 값 이거나 열려 있는 파일을 참조 하지 않음을 의미 합니다. **EINVAL** 는 잘못 된 *스트림* 인수가 함수에 전달 되었음을 의미 합니다. 검색 되지 않는 장치 (예: 터미널 및 프린터) 또는 *스트림이* 열려 있는 파일을 참조 하지 않는 경우 반환 값은 정의 되지 않습니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**Fokand** **_fanfm64** 함수는 *스트림과*연결 된 파일 포인터 (있는 경우)의 현재 위치를 검색 합니다. 위치는 스트림 시작을 기준으로 하는 오프셋으로 표현됩니다.

데이터를 추가하기 위해 파일이 열리면 현재 파일 위치는 다음 쓰기가 수행되는 위치가 아니라 마지막 I/O 작업에 의해 결정됩니다. 예를 들어 파일이 추가를 위해 열리고 마지막 작업이 읽기였다면 파일 위치는 다음 쓰기가 시작되는 위치가 아니라 다음 읽기 작업이 시작되는 지점입니다. 파일이 추가를 위해 열린 경우 파일 위치는 쓰기 작업 전에 파일의 끝으로 이동합니다. 추가를 위해 열린 파일에서 I/O 작업이 아직 수행되지 않은 경우 파일 위치는 파일의 시작입니다.

텍스트 모드에서 Ctrl+Z는 입력 시 파일 끝 문자로 해석됩니다. 읽기/쓰기용으로 열려 있는 파일에서 **fopen** 및 모든 관련 루틴은 파일 끝에 CTRL + Z가 있는지 확인 하 고 가능 하면 제거 합니다. 이 작업은 **ftell** 및 [fseek](fseek-fseeki64.md) 또는 **_ftelli64** 및 [_fseeki64](fseek-fseeki64.md)의 조합을 사용하여 CTRL+Z로 끝나는 파일 내에서 **ftell** 또는 **_ftelli64** 파일이 이동 하는 경우에 발생합니다.

이 함수는 실행 중에 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전은 **_ftell_nolock**를 참조 하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|선택적 헤더|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>

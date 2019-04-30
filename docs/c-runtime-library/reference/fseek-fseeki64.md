---
title: fseek, _fseeki64
ms.date: 11/04/2016
apiname:
- _fseeki64
- fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: e5f775eab370f8f4a3b6a5c1d7f0918ec7efa3ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287588"
---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64

파일 포인터를 지정된 위치로 이동합니다.

## <a name="syntax"></a>구문

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

*offset*<br/>
*origin*부터의 바이트 수입니다.

*origin*<br/>
초기 위치입니다.

## <a name="return-value"></a>반환 값

성공 하면 **fseek** 하 고 **_fseeki64** 0을 반환 합니다. 그렇지 않으면 0이 아닌 값을 반환합니다. 검색을 수행할 수 없는 디바이스에서는 반환 값이 정의되지 않습니다. 하는 경우 *스트림을* 가 null 포인터 이거나 *원본* 아래에 설명 된 허용 되는 값 중 하나가 아닙니다 **fseek** 및 **_fseeki64** 잘못 된 호출 에 설명 된 대로 매개 변수 처리기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 고-1을 반환 합니다.

## <a name="remarks"></a>설명

합니다 **fseek** 하 고 **_fseeki64** 파일 포인터 (있는 경우)와 관련 된 이동 함수 *stream* 는 새 위치로 *오프셋* 바이트 *원본*합니다. 스트림에 대한 다음 작업은 새 위치에서 수행됩니다. 업데이트를 위해 열린 스트림에 대한 다음 작업은 읽기 또는 쓰기일 수 있습니다. 인수 *원본* STDIO에 정의 된 다음 상수 중 하나 여야 합니다. H:

|원본 값|의미|
|-|-|
| **SEEK_CUR** | 파일 포인터의 현재 위치 |
| **SEEK_END** | 파일 끝 |
| **SEEK_SET** | 파일 시작 |

사용할 수 있습니다 **fseek** 하 고 **_fseeki64** 파일에서는 포인터를 어디서 나 위치 합니다. 포인터는 파일 끝을 지나서 배치될 수도 있습니다. **fseek** 하 고 **_fseeki64** 파일 끝 표시기를 지우고 모든 이전 버전의 결과 부정 [ungetc](ungetc-ungetwc.md) 에 대 한 호출 *stream*합니다.

데이터를 추가하기 위해 파일이 열리면 현재 파일 위치는 다음 쓰기가 수행되는 위치가 아니라 마지막 I/O 작업에 의해 결정됩니다. 추가를 위해 열린 파일에서 I/O 작업이 아직 수행되지 않은 경우 파일 위치는 파일의 시작입니다.

텍스트 모드에서 열린 스트림에 대 한 **fseek** 하 고 **_fseeki64** 캐리지 리턴-줄 바꿈 번역 될 수 있으므로 사용 제한 **fseek** 고 **_ fseeki64** 예기치 않은 결과를 생성 합니다. 유일한 **fseek** 하 고 **_fseeki64** 텍스트 모드에서 열린 스트림에서 수행 하도록 보장 하는 작업은:

- 원점 값을 기준으로 한 0 오프셋을 사용하여 검색

- 에 대 한 호출에서 반환 된 오프셋된 값을 사용 하 여 파일의 시작 부분에서 검색 [ftell](ftell-ftelli64.md) 사용 하는 경우 **fseek** 하거나 [_ftelli64](ftell-ftelli64.md) 사용 하는 경우 **_fseeki64**.

또한 텍스트 모드에서 Ctrl+Z는 입력 시 파일 끝 문자로 해석됩니다. 읽기/쓰기용으로 열려 있는 파일의 [fopen](fopen-wfopen.md) 및 모든 관련된 루틴 파일의 끝에 CTRL + Z를 확인 하 고 가능한 경우 제거 합니다. 조합을 사용 하기 때문에 이렇게 **fseek** 하 고 [ftell](ftell-ftelli64.md) 또는 **_fseeki64** 고 [_ftelli64](ftell-ftelli64.md)로 끝나는 파일 내에서 이동 하면 CTRL + Z 않을 **fseek** 하거나 **_fseeki64** 파일 끝 가까이 제대로 동작 하려면.

CRT가 BOM(바이트 순서 표시)으로 시작되는 파일을 열면 파일 포인터는 BOM 뒤(파일 실제 콘텐츠의 시작)에 배치됩니다. 해야 할 경우 **fseek** 파일의 시작 부분에 사용 하 여 [ftell](ftell-ftelli64.md) 초기 위치를 가져올 수 및 **fseek** 위치 0 대신에 해당 합니다.

이 함수는 실행 중에 다른 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>

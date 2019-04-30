---
title: rewind
ms.date: 11/04/2016
apiname:
- rewind
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
- rewind
helpviewer_keywords:
- rewind function
- repositioning file pointers
- file pointers [C++], repositioning
- file pointers [C++]
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
ms.openlocfilehash: d2e50c34d48b5a9570691a8a702cd05c1a48242d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357566"
---
# <a name="rewind"></a>rewind

파일 포인터의 위치를 파일의 시작 부분으로 변경합니다.

## <a name="syntax"></a>구문

```C
void rewind(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="remarks"></a>설명

합니다 **rewind** 함수에 연결 된 파일 포인터 위치를 변경 *스트림* 파일의 시작 부분에 있습니다. **rewind**에 대한 호출은 다음과 유사합니다.

**(void) fseek(** _stream_**, 0L, SEEK_SET );**

그러나와 달리 [fseek](fseek-fseeki64.md)하십시오 **rewind** 스트림에 대 한 오류 표시기는 물론 파일 끝 표시기도 지웁니다. 또한 달리 [fseek](fseek-fseeki64.md)를 **rewind** 포인터가 성공적으로 이동 하는지 여부를 나타내는 값을 반환 하지 않습니다.

사용 하 여 키보드 버퍼를 지우려면 **rewind** 스트림을 사용 하 여 **stdin**, 기본적으로 키보드와 연결 되는 합니다.

스트림이 **NULL** 에 설명 된 대로 포인터인 경우 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 하 고 **errno** 로 설정 된 **EINVAL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**rewind**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_rewind.c
/* This program first opens a file named
* crt_rewind.out for input and output and writes two
* integers to the file. Next, it uses rewind to
* reposition the file pointer to the beginning of
* the file and reads the data back in.
*/
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int data1, data2;

   data1 = 1;
   data2 = -37;

   fopen_s( &stream, "crt_rewind.out", "w+" );
   if( stream != NULL )
   {
      fprintf( stream, "%d %d", data1, data2 );
      printf( "The values written are: %d and %d\n", data1, data2 );
      rewind( stream );
      fscanf_s( stream, "%d %d", &data1, &data2 );
      printf( "The values read are: %d and %d\n", data1, data2 );
      fclose( stream );
   }
}
```

### <a name="output"></a>출력

```Output
The values written are: 1 and -37
The values read are: 1 and -37
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>

---
title: _putw
ms.date: 11/04/2016
apiname:
- _putw
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
- _putw
- putw
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
ms.openlocfilehash: 3fd18c2a8869d6b09703547f50ee6e096bd72395
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358055"
---
# <a name="putw"></a>_putw

정수를 스트림에 씁니다.

## <a name="syntax"></a>구문

```C
int _putw(
   int binint,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*binint*<br/>
출력할 이진 정수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

작성된 값을 반환합니다. 반환 값 **EOF** 오류를 나타낼 수 있습니다. 때문에 **EOF** 합법적인 정수 값을 사용 하 여 이기도 **ferror** 오류를 확인 합니다. 하는 경우 *스트림을* 가 null 포인터인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EOF**합니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **_putw** 함수 형식의 이진값을 씁니다 **int** 의 현재 위치에 *스트림 합니다.* **_putw** 스트림의 항목 정렬에 영향을 주지 않습니다도 않습니다 특수 정렬도 간주 합니다. **_putw** 주로 이전 라이브러리와의 호환성입니다. 이식성 문제가 발생할 수 있습니다 **_putw** 때문에 크기를 **int** 내의 바이트 순서가 **int** 시스템 간에 다릅니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_putw**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_putw.c
/* This program uses _putw to write a
* word to a stream, then performs an error check.
*/

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   unsigned u;
   if( fopen_s( &stream, "data.out", "wb" ) )
      exit( 1 );
   for( u = 0; u < 10; u++ )
   {
      _putw( u + 0x2132, stream );   /* Write word to stream. */
      if( ferror( stream ) )         /* Make error check. */
      {
         printf( "_putw failed" );
         clearerr_s( stream );
         exit( 1 );
      }
   }
   printf( "Wrote ten words\n" );
   fclose( stream );
}
```

### <a name="output"></a>출력

```Output
Wrote ten words
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_getw](getw.md)<br/>

---
title: _getw
ms.date: 11/04/2016
apiname:
- _getw
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
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: 615d3ac9bdc73ad200368eaeabf7c84951bc91ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157632"
---
# <a name="getw"></a>_getw

스트림에서 정수를 가져옵니다.

## <a name="syntax"></a>구문

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**_getw** 읽은 정수 값을 반환 합니다. 반환 값 **EOF** 오류 또는 파일의 끝을 나타냅니다. 그러나 때문에 **EOF** 값은 올바른 정수 값도 사용 합니다 **feof** 또는 **ferror** 는 파일의 끝 또는 오류 조건을 확인 합니다. 하는 경우 *스트림을* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **EOF**합니다.

## <a name="remarks"></a>설명

합니다 **_getw** 함수 형식의 다음 이진 값을 읽고 **int** 연관 된 파일에서 *stream* 가리키도록 (있는 경우) 연결된 된 파일 포인터를 증가 시킵니다 읽지 않은 다음 문자입니다. **_getw** 어떠한 특별 한 스트림의 항목 맞춤을 가정 하지는 않습니다. 이식 관련 문제가 발생할 수 있습니다 **_getw** 때문에 크기를 **int** 형식과 내의 바이트 순서를 **int** 형식이 시스템에서 다를 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getw.c
// This program uses _getw to read a word
// from a stream, then performs an error check.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   int i;

   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )
      printf( "Couldn't open file\n" );
   else
   {
      // Read a word from the stream:
      i = _getw( stream );

      // If there is an error...
      if( ferror( stream ) )
      {
         printf( "_getw failed\n" );
         clearerr_s( stream );
      }
      else
         printf( "First data word in file: 0x%.4x\n", i );
      fclose( stream );
   }
}
```

### <a name="input-crtgetwtxt"></a>입력: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>

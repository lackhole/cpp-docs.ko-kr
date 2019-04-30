---
title: fflush
ms.date: 11/04/2016
apiname:
- fflush
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
- fflush
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: d03d20ee5024915d0ca4c5a21db4159e8c4f876a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333984"
---
# <a name="fflush"></a>fflush

스트림을 플러시합니다.

## <a name="syntax"></a>구문

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fflush** 버퍼 성공적으로 플러시된 경우 0을 반환 합니다. 지정된 스트림에 버퍼가 없거나 해당 스트림이 읽기 전용으로 열린 경우에도 값 0이 반환됩니다. 반환 값 **EOF** 은 오류를 나타냅니다.

> [!NOTE]
> 하는 경우 **fflush** 반환 **EOF**, 데이터 쓰기 오류로 인해 손실 되었을 수 있습니다. 오류 처리기를 설정할 때 버퍼링을 끄거나 사용 하 여 가장 안전한 합니다 **setvbuf** 함수와 같은 하위 수준 I/O 루틴을 사용 하 여 **열기 (_o)**, **_close**, 및 **_write** 스트림 I/O 함수 대신 합니다.

## <a name="remarks"></a>설명

합니다 **fflush** 함수는 스트림을 플러시합니다 *스트림*합니다. 스트림이 쓰기 모드에서 열렸거나 업데이트 모드에서 열리고 마지막 작업이 쓰기였던 경우 스트림 버퍼의 콘텐츠가 기본 파일 또는 디바이스에 기록되고 버퍼가 삭제됩니다. 읽기 모드에서 열렸거나 스트림에 또는 스트림 버퍼가 호출 하는 경우 **fflush** , 영향을 주지 않으며 모든 버퍼가 유지 됩니다. 에 대 한 호출 **fflush** 이전 호출의 결과 부정 **ungetc** 스트림에 대 한 합니다. 스트림은 호출 후에 열려 있습니다.

경우 *스트림을* 됩니다 **NULL**, 동작에 대 한 호출 동일 **fflush** 각 열린 스트림에 대. 쓰기 모드로 열린 모든 스트림과 마지막 작업이 쓰기인 업데이트 모드로 열린 모든 스트림이 플러시됩니다. 이 호출은 다른 스트림에 영향을 미치지 않습니다.

버퍼는 보통 운영 체제에서 유지 관리됩니다. 운영 체제에서는 버퍼가 가득 찼을 때, 스트림이 닫혀 있을 때, 스트림을 닫지 않고 프로그램이 정상적으로 종료될 때 등 디스크에 데이터를 자동으로 쓰는 최적의 시간을 결정합니다. 런타임 라이브러리의 디스크에 커밋 기능을 사용하면 중요한 데이터가 운영 체제 버퍼 대신 디스크에 직접 기록되어 있는지 확인할 수 있습니다. 기존 프로그램을 다시 작성하지 않고 프로그램의 개체 파일을 COMMODE.OBJ에 연결하여 이 기능을 사용할 수 있습니다. 결과 실행 파일을 호출 **_flushall** 모든 버퍼의 내용을 디스크에 씁니다. 만 **_flushall** 하 고 **fflush** commode.obj의 영향을 합니다.

디스크에 커밋 기능을 제어하는 방법에 대한 자세한 내용은 [스트림 I/O](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) 및 [_fdopen](fdopen-wfdopen.md)을 참조하세요.

이 함수는 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않은 버전을 참조 하세요 **_fflush_nolock**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fflush.c
#include <stdio.h>
#include <conio.h>

int main( void )
{
   int integer;
   char string[81];

   // Read each word as a string.
   printf( "Enter a sentence of four words with scanf: " );
   for( integer = 0; integer < 4; integer++ )
   {
      scanf_s( "%s", string, sizeof(string) );
      printf( "%s\n", string );
   }

   // You must flush the input buffer before using gets.
   // fflush on input stream is an extension to the C standard
   fflush( stdin );
   printf( "Enter the same sentence with gets: " );
   gets_s( string, sizeof(string) );
   printf( "%s\n", string );
}
```

```Input
This is a test
This is a test
```

```Output
Enter a sentence of four words with scanf: This is a test
This
is
a
test
Enter the same sentence with gets: This is a test
This is a test
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>

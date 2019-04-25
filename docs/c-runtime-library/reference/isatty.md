---
title: _isatty
ms.date: 11/04/2016
apiname:
- _isatty
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
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: ef0df5f859779c081df47ef4bfe938ec2601d524
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157476"
---
# <a name="isatty"></a>_isatty

파일 설명자가 문자 디바이스와 연결되어 있는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int _isatty( int fd );
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
테스트할 디바이스를 나타내는 파일 설명자입니다.

## <a name="return-value"></a>반환 값

**_isatty** 설명자가 문자 장치와 연결 된 경우 0이 아닌 값을 반환 합니다. 그렇지 않으면 **_isatty** 0을 반환 합니다.

## <a name="remarks"></a>설명

합니다 **_isatty** 함수를 결정 하는지 여부를 *fd* (터미널, 콘솔, 프린터 또는 직렬 포트) 문자 장치와 연결 됩니다.

이 함수는 유효성을 검사 합니다 *fd* 매개 변수입니다. 하는 경우 *fd* 잘못 된 파일 포인터인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행 함수는 0 반환 하 고 집합을 계속 하도록 허용 된 경우 **errno** 하 **EBADF**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_isatty**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>샘플 출력

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>

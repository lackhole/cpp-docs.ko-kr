---
title: _memccpy
ms.date: 11/04/2016
apiname:
- _memccpy
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _memccpy
helpviewer_keywords:
- _memccpy function
- memccpy function
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
ms.openlocfilehash: 5cd037974d8580b6ee90b1af736e8f2c6897fe8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156605"
---
# <a name="memccpy"></a>_memccpy

버퍼에서 문자를 복사합니다.

## <a name="syntax"></a>구문

```C
void *_memccpy(
   void *dest,
   const void *src,
   int c,
   size_t count
);
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
대상에 대한 포인터입니다.

*src*<br/>
소스에 대한 포인터입니다.

*c*<br/>
복사할 마지막 문자입니다.

*count*<br/>
문자 수입니다.

## <a name="return-value"></a>반환 값

경우 문자 *c* 복사 **_memccpy** char에 대 한 포인터를 반환 합니다 *dest* 문자를 바로 다음에 오는 합니다. 하는 경우 *c* 복사 되지 반환 **NULL**합니다.

## <a name="remarks"></a>설명

**_memccpy** 함수는 0 개 이상의 문자를 복사 *src* 에 *dest*를 중지 하는 경우 문자 *c* 복사 되었습니다 때나 *개수* 문자가 복사 된 경우 먼저 도달 합니다.

**보안 정보** 대상 버퍼의 크기가 소스 버퍼의 크기보다 크거나 같아야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_memccpy**|\<memory.h> 또는 \<string.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_memccpy.c

#include <memory.h>
#include <stdio.h>
#include <string.h>

char string1[60] = "The quick brown dog jumps over the lazy fox";

int main( void )
{
   char buffer[61];
   char *pdest;

   printf( "Function: _memccpy 60 characters or to character 's'\n" );
   printf( "Source: %s\n", string1 );
   pdest = _memccpy( buffer, string1, 's', 60 );
   *pdest = '\0';
   printf( "Result: %s\n", buffer );
   printf( "Length: %d characters\n", strlen( buffer ) );
}
```

### <a name="output"></a>출력

```Output
Function: _memccpy 60 characters or to character 's'
Source: The quick brown dog jumps over the lazy fox
Result: The quick brown dog jumps
Length: 25 characters
```

## <a name="see-also"></a>참고자료

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>

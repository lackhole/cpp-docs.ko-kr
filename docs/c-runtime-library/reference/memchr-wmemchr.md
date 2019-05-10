---
title: memchr, wmemchr
ms.date: 03/31/2019
apiname:
- wmemchr
- memchr
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
ms.openlocfilehash: 00a1f0d12047cc388b56074a657ffd739e986827
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285263"
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr

버퍼에서 문자를 찾습니다.

## <a name="syntax"></a>구문

```C
void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C only
void *memchr(
   void *buffer,
   int c,
   size_t count
); // C++ only
const void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C++ only
wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C only
wchar_t *wmemchr(
   wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
const wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
버퍼에 대한 포인터입니다.

*c*<br/>
찾을 문자입니다.

*count*<br/>
검사할 문자 수입니다.

## <a name="return-value"></a>반환 값

성공 하면 포인터의 첫 번째 위치를 반환 *c* 에 *버퍼*합니다. 그렇지 않으면 NULL을 반환 합니다.

## <a name="remarks"></a>설명

`memchr` 및 `wmemchr` 처음 검색할 *c* 첫 번째에서 *개수* 자의 *버퍼*합니다. 찾으면 중지 *c* 첫 번째 검사 하거나 *개수* 문자입니다.

C에서 이러한 함수는 다음과 같이 사용 됩니다.는 **const** 첫 번째 인수에 대 한 포인터입니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. 에 대 한 포인터를 갖는 오버 로드 **상수** 에 대 한 포인터를 반환 **const**;는 버전에 대 한 포인터를은 비**const** 에 대 한 포인터를 반환 하는 비-**const** . 매크로 \_CRT\_CONST\_올바름\_오버 로드 모두 정의 됩니다는 **const** 및 비-**const** 이러한 함수의 버전은 사용할 수 있습니다. 비-필요한 경우**const** 둘 다에 대 한 동작 C++ 의 오버 로드 C++, 기호를 정의 \_CONST\_를 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`memchr`|\<memory.h> 또는 \<string.h>|
|`wmemchr`|\<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_memchr.c

#include <memory.h>
#include <stdio.h>

int  ch = 'r';
char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int result;
   printf( "String to be searched:\n             %s\n", string );
   printf( "             %s\n             %s\n\n", fmt1, fmt2 );

   printf( "Search char: %c\n", ch );
   pdest = memchr( string, ch, sizeof( string ) );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "Result:      %c found at position %d\n", ch, result );
   else
      printf( "Result:      %c not found\n" );
}
```

### <a name="output"></a>출력

```Output
String to be searched:
             The quick brown dog jumps over the lazy fox
                      1         2         3         4         5
             12345678901234567890123456789012345678901234567890

Search char: r
Result:      r found at position 12
```

## <a name="see-also"></a>참고자료

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>

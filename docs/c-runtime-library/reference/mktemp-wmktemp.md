---
title: _mktemp, _wmktemp
ms.date: 11/04/2016
apiname:
- _wmktemp
- _mktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
ms.openlocfilehash: c1c5f0ee12c9e07d76405014bb4a6a6ecc7d97e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156514"
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp

고유한 파일 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*nameTemplate*<br/>
파일 이름 패턴입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수 수정된 nameTemplate에 대 한 포인터를 반환합니다. 함수 반환 **NULL** 경우 *nameTemplate* 잘못 된 형식의 또는 지정 된 nameTemplate에서 더 이상 고유한 이름을 만들 수 있습니다.

## <a name="remarks"></a>설명

합니다 **_mktemp** 함수를 수정 하 여 고유한 파일 이름을 만듭니다 합니다 *nameTemplate* 인수입니다. **_mktemp** 런타임 시스템에서 현재 사용 중인 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하며 필요에 따라 멀티 바이트 문자열 인수를 자동으로 처리 합니다. **_wmktemp** 의 와이드 문자 버전이 **_mktemp**;의 인수와 반환 값 **_wmktemp** 는 와이드 문자 문자열입니다. **_wmktemp** 하 고 **_mktemp** 동일 하 게 한다는 점을 제외 하 고, 그렇지 동작 **_wmktemp** 멀티 바이트 문자열을 처리 하지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

합니다 *nameTemplate* 인수의 형식은 *기본*XXXXXX 여기서 *기본* 제공 하는 새 파일 이름 부분은 속하며 각 X는에서 제공 하는 문자열에 대 한 자리 표시자 **_mktemp**합니다. 각 자리 표시자 문자 *nameTemplate* 는 대문자 X 여야 **_mktemp** 유지 *기본* 첫 번째 후행 X를 영문자로 바꿉니다. **_mktemp** 대체 다음 후행 X 5 자리 숫자 값을 사용 하 여이 값은 프로세스 또는 다중 스레드 프로그램을 호출 하는 스레드에서 호출을 식별 하는 고유 번호입니다.

성공한 각 호출에 **_mktemp** 수정 *nameTemplate*합니다. 각 후속 호출에서 동일한 프로세스 또는 스레드의 동일한 *nameTemplate* 인수 **_mktemp** 반환한 이름과 일치 하는 파일 이름에 대 한 검사 **_mktemp** 에서 이전 호출 합니다. 지정 된 이름에 대 한 파일이 없는 경우 **_mktemp** 해당 이름을 반환 합니다. 이전에 반환 된 모든 이름에 대 한 파일이 존재 하는 경우 **_mktemp** 다음 사용 가능한 소문자를 'a' ~ 'z'까지에서 순서 대로 사용 하 여 이전에 반환 된 이름에서 사용한 영문자를 대체 하 여 새 이름을 만듭니다. 예를 들어 있으면 *기본* 됩니다.

> **fn**

및에서 제공 하는 5 자리 숫자 값 **_mktemp** 이 12345 인 경우 첫 번째 반환 되는:

> **fna12345**

이 이름이 FNA12345 파일을 만드는 데 사용 됩니다 하 고이 파일이 있는지, 동일한 프로세스 또는 스레드가 동일한 호출에서 반환 된 다음 이름이 *기본* 에 대 한 *nameTemplate* 됩니다.

> **fnb12345**

FNA12345가 존재하지 않는 경우 반환된 다음 이름은 다시 아래와 같습니다.

> **fna12345**

**_mktemp** 의 지정된 된 조합에 대 한 고유한 파일 이름 26 개까지 만들 수 있습니다 *기본* 하 고 *nameTemplate* 값입니다. 따라서 FNZ12345는 마지막 고유한 파일 이름을 **_mktemp** 에 대해 만들 수는 *기본* 및 *nameTemplate* 이 예제에서 사용 되는 값입니다.

실패 시 **errno** 설정 됩니다. 하는 경우 *nameTemplate* 형식이 잘못 되었습니다 (6 개 보다 적은 예를 들어, X), **errno** 로 설정 되어 **EINVAL**합니다. 하는 경우 **_mktemp** 26 모든 가능한 파일 이름이 이미 존재 하기 때문에 고유한 이름을 만들 수 없는 **_mktemp** nameTemplate을 빈 문자열로 설정 하 고 반환 **EEXIST**합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>

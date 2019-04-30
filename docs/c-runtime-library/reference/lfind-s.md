---
title: _lfind_s
ms.date: 11/04/2016
apiname:
- _lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind_s
- _lfind_s
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
ms.openlocfilehash: 08c04d9d1ca69998d54304c96468298013907179
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286429"
---
# <a name="lfinds"></a>_lfind_s

지정된 키에 대해 선형 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_lfind](lfind.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *_lfind_s(
   const void *key,
   const void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 개체입니다.

*base*<br/>
검색 데이터의 기준에 대한 포인터입니다.

*number*<br/>
배열 요소의 수입니다.

*size*<br/>
배열 요소의 크기(바이트)입니다.

*compare*<br/>
비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수를 *상황에 맞는* 포인터입니다. 두 번째 매개 변수는 검색할 키에 대한 포인터입니다. 세 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

*context*<br/>
비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

키가 있으면 **_lfind_s** 배열의 요소에 대 한 포인터를 반환 합니다. *기본* 일치 하는 *키*합니다. 키가 없으면 **_lfind_s** 반환 **NULL**합니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **NULL**합니다.

### <a name="error-conditions"></a>오류 조건

|key|base|compare|num|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|0|**EINVAL**|
|any|any|**NULL**|an|any|**EINVAL**|

## <a name="remarks"></a>설명

합니다 **_lfind_s** 함수 값에 대 한 선형 검색을 수행 *키* 배열을 *번호* 의 각 요소 *너비* 바이트입니다. 와 달리 **bsearch_s**하십시오 **_lfind_s** 배열을 정렬할 필요가 없습니다. 합니다 *기본* 인수는 검색할 배열의 밑에 대 한 포인터입니다. 합니다 *비교* 인수는 두 배열 요소를 비교 하 고 해당 관계를 지정 하는 값을 반환 하는 사용자가 제공한 루틴에 대 한 포인터입니다. **_lfind_s** 호출을 *비교* 일상적인 한 번 이상 전달 검색 중를 *상황에 맞는* 포인터 및 각 호출에서 두 배열 요소에 대 한 포인터입니다. 합니다 *비교* 루틴 요소를 비교 다음 0이 아닌 값 (즉 요소를 서로 다르게 되어 있는지)를 반환 해야 합니다 또는 0 (요소가 동일 하다는 의미).

**_lfind_s** 비슷합니다 **_lfind** 추가 제외 하 고는 *상황에 맞는* 비교 함수의 인수 및 함수의 매개 변수 목록에 대 한 포인터입니다. 합니다 *상황에 맞는* 포인터는 검색된 데이터 구조가 개체의 일부 경우에 유용할 수 있습니다 및 *비교* 함수 개체의 멤버에 액세스 해야 합니다. 합니다 *비교* 함수 해당 개체의 적절 한 개체 유형 및 액세스 멤버에는 void 포인터를 캐스팅할 수 있습니다. 추가 합니다 *상황에 맞는* 매개 변수 **_lfind_s** 추가 데이터를 사용할 수 있도록 정적 변수를 사용 하 여 연결 하는 재진입 버그를 방지 하려면 추가 컨텍스트를 사용할 수 있으므로 보안 합니다 *비교* 함수입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_lfind_s.cpp
// This program uses _lfind_s to search a string array,
// passing a locale as the context.
// compile with: /EHsc
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char *s1 = *(char**)str1;
    char *s2 = *(char**)str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

void find_it( char *key, char *array[], unsigned int num, locale &loc )
{
   char **result = (char **)_lfind_s( &key, array,
                      &num, sizeof(char *), compare, &loc );
   if( result )
      printf( "%s found\n", *result );
   else
      printf( "%s not found\n", key );
}

int main( )
{
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );
}
```

```Output
weit found
```

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>

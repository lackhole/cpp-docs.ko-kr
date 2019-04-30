---
title: _lfind
ms.date: 11/04/2016
apiname:
- _lfind
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
- lfind
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 1508d54d6b2f2566e4aee3afef02af45b28e4f48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286494"
---
# <a name="lfind"></a>_lfind

지정된 키에 대해 선형 검색을 수행합니다. 이 함수의 보다 안전한 버전을 사용할 수 있습니다. [_lfind_s](lfind-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 개체입니다.

*base*<br/>
검색 데이터의 기준에 대한 포인터입니다.

*number*<br/>
배열 요소의 수입니다.

*width*<br/>
배열 요소의 너비입니다.

*compare*<br/>
비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 검색할 키에 대한 포인터입니다. 두 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

키가 있으면 **_lfind** 배열의 요소에 대 한 포인터를 반환 합니다. *기본* 일치 하는 *키*합니다. 키가 없으면 **_lfind** 반환 **NULL**합니다.

## <a name="remarks"></a>설명

합니다 **_lfind** 함수 값에 대 한 선형 검색을 수행 *키* 배열을 *번호* 의 각 요소 *너비* 바이트입니다. 와 달리 **bsearch**하십시오 **_lfind** 배열을 정렬할 필요가 없습니다. 합니다 *기본* 인수는 검색할 배열의 밑에 대 한 포인터입니다. 합니다 *비교* 인수는 두 배열 요소를 비교 하 고 해당 관계를 지정 하는 값을 반환 하는 사용자가 제공한 루틴에 대 한 포인터입니다. **_lfind** 호출을 *비교* 일상적인 한 번 이상 각 호출에서 두 배열 요소에 대 한 포인터를 전달 하는 검색 중. 합니다 *비교* 루틴에서 요소를 비교 하 고 (요소가 다르다는 의미) 0이 아닌 값을 반환 해야 합니다 또는 0 (요소가 동일 하다는 의미).

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *비교*, *키* 또는 *번호* 은 **NULL**, 또는 *기본* 은 **NULL**하 고 *번호* 이 값은 0 이거나 *너비* 작습니다 0 보다는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **NULL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_lfind**|\<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_lfind.c
// This program uses _lfind to search a string array
// for an occurrence of "hello".

#include <search.h>
#include <string.h>
#include <stdio.h>

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}

int main( )
{
   char *arr[] = {"Hi", "Hello", "Bye"};
   int n = sizeof(arr) / sizeof(char*);
   char **result;
   char *key = "hello";

   result = (char **)_lfind( &key, arr,
                      &n, sizeof(char *), compare );

   if( result )
      printf( "%s found\n", *result );
   else
      printf( "hello not found!\n" );
}
```

```Output
Hello found
```

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>

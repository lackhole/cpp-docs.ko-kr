---
title: bsearch
ms.date: 11/04/2016
apiname:
- bsearch
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: e170ce67d22c0d97825a7eb754546a29daac6d89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347758"
---
# <a name="bsearch"></a>bsearch

정렬된 배열의 이진 검색을 수행합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [bsearch_s](bsearch-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void *bsearch(
   const void *key,
   const void *base,
   size_t num,
   size_t width,
   int ( __cdecl *compare ) (const void *key, const void *datum)
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 개체입니다.

*base*<br/>
검색 데이터 기준에 대한 포인터입니다.

*number*<br/>
요소의 수입니다.

*width*<br/>
요소의 너비입니다.

*compare*<br/>
두 요소를 비교하는 콜백 함수입니다. 첫 번째 요소는 검색 키에 대한 포인터이고 두 번째 요소는 키와 비교할 배열 요소에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**bsearch** 발생에 대 한 포인터를 반환 *키* 가 가리키는 배열의 *기본*입니다. 하는 경우 *키* 발견 되지 않으면 반환 **NULL**합니다. 배열이 오름차순 정렬이 아니거나 동일한 키를 가진 중복 레코드를 포함하는 경우에는 결과를 예측할 수 없습니다.

## <a name="remarks"></a>설명

**bsearch** 의 정렬 된 배열의 이진 검색을 수행 하는 함수 *번호* 의 각 요소 *너비* 크기에서 (바이트). 합니다 *기본* 값은 검색할 배열의 밑에 대 한 포인터 및 *키* 가 검색 되는 값입니다. 합니다 *비교* 매개 변수는 배열 요소에 요청된 된 키를 비교 하 고 해당 관계를 지정 하는 다음 값 중 하나를 반환 하는 사용자가 제공한 루틴에 대 한 포인터:

|반환 된 값 *비교* 루틴|설명|
|-----------------------------------------|-----------------|
|\< 0|키가 배열 요소보다 작습니다.|
|0|키가 배열 요소와 같습니다.|
|> 0|키가 배열 요소보다 큽니다.|

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *비교*, *키* 또는 *번호* 은 **NULL**, 또는 *기본* 은 **NULL**하 고 *수* 값은 0 이거나 *너비* 가 0 이면에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 `EINVAL` 고 함수가 반환 **NULL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**bsearch**|\<stdlib.h> 및 \<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 qsort를 사용하여 문자열 배열을 정렬한 다음 bsearch를 사용하여 "cat" 단어를 찾습니다.

```C
// crt_bsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( char **arg1, char **arg2 )
{
   /* Compare all of both strings: */
   return _strcmpi( *arg1, *arg2 );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};
   char **result;
   char *key = "cat";
   int i;

   /* Sort using Quicksort algorithm: */
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const
   void*, const void*))compare );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),
                              sizeof( char * ), (int (*)(const void*, const void*))compare );
   if( result )
      printf( "\n%s found at %Fp\n", *result, result );
   else
      printf( "\nCat not found!\n" );
}
```

```Output
cat cow dog goat horse human pig rat
cat found at 002F0F04
```

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>

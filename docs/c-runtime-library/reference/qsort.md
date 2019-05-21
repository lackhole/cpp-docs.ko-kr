---
title: qsort
ms.date: 11/04/2016
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: 8a770965a03e43227b99f122924c723691f79c61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358101"
---
# <a name="qsort"></a>qsort

빠른 정렬을 수행합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [qsort_s](qsort-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void qsort(
   void *base,
   size_t number,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>매개 변수

*base*<br/>
대상 배열의 시작 부분입니다.

*number*<br/>
요소의 배열 길이입니다.

*width*<br/>
요소 크기(바이트)입니다.

*compare*<br/>
두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다.

## <a name="remarks"></a>설명

합니다 **qsort** 배열을 정렬 하려면 빠른 정렬 알고리즘을 구현 하는 함수 *번호* 의 각 요소 *너비* 바이트입니다. 인수 *기본* 정렬할 배열의 밑에 대 한 포인터입니다. **qsort** 정렬 된 요소를 사용 하 여이 배열을 덮어씁니다.

**qsort** 호출을 *비교* 일상적인 하나 이상의 정렬 하는 동안 시간 및 각 호출에서 두 배열 요소에 대 한 포인터를 전달 합니다.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

루틴은 요소를 비교한 후에 다음 값 중 하나를 반환합니다.

|비교 함수 반환 값|설명|
|-----------------------------------|-----------------|
|< 0|**elem1** 보다 작거나 **elem2**|
|0|**elem1** 같음 **elem2**|
|> 0|**elem1** 보다 큰 **elem2**|

비교 함수에 정의된 대로 배열은 오름차순으로 정렬됩니다. 배열을 내림차순으로 정렬하려면 비교 함수에서 "보다 큼"과 "보다 작음"의 의미를 반전하면 됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *비교* 또는 *번호* 는 **NULL**, 이거나 *기본* 은 **NULL** 및 *수* 이 값은 0 이거나 *너비* 작으면 0 보다는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 함수 반환 하 고 **errno** 로 설정 된 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**qsort**|\<stdlib.h> 및 \<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_qsort.c
// arguments: every good boy deserves favor

/* This program reads the command-line
* parameters and uses qsort to sort them. It
* then displays the sorted arguments.
*/

#include <stdlib.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main( int argc, char **argv )
{
   int i;
   /* Eliminate argv[0] from sort: */
   argv++;
   argc--;

   /* Sort remaining args using Quicksort algorithm: */
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );

   /* Output sorted list: */
   for( i = 0; i < argc; ++i )
      printf( " %s", argv[i] );
   printf( "\n" );
}

int compare( const void *arg1, const void *arg2 )
{
   /* Compare all of both strings: */
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );
}
```

```Output
boy deserves every favor good
```

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>

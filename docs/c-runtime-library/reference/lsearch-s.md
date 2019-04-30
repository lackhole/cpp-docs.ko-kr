---
title: _lsearch_s
ms.date: 11/04/2016
apiname:
- _lsearch_s
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
- _lsearch_s
- lsearch_s
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
ms.openlocfilehash: f57a96622419e3f72fc2df5b260cbbbdd59666ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156958"
---
# <a name="lsearchs"></a>_lsearch_s

값에 대한 선형 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_lsearch](lsearch.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *_lsearch_s(
   const void *key,
   void *base,
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
검색할 배열의 기준에 대한 포인터입니다.

*number*<br/>
요소의 수입니다.

*size*<br/>
각 배열 요소의 크기(바이트)입니다.

*compare*<br/>
비교 루틴에 대한 포인터입니다. 두 번째 매개 변수는 검색할 키에 대한 포인터입니다. 세 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

*context*<br/>
비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

하는 경우 *키* 발견 되 면 **_lsearch_s** 배열의 요소에 대 한 포인터를 반환 합니다 *기본* 일치 하는 *키*합니다. 하는 경우 *키* 찾지 못하면 **_lsearch_s** 배열의 끝에서 새로 추가 된 항목에 대 한 포인터를 반환 합니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행이 계속 해 서를 허용 하는 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **NULL**합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*key*|*base*|*compare*|*number*|*size*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|0|**EINVAL**|
|any|any|**NULL**|an|any|**EINVAL**|

## <a name="remarks"></a>설명

합니다 **_lsearch_s** 함수 값에 대 한 선형 검색을 수행 *키* 배열을 *번호* 의 각 요소 *너비* 바이트입니다. 와 달리 **bsearch_s**하십시오 **_lsearch_s** 배열을 정렬할 필요가 없습니다. 하는 경우 *키* 발견 되지 않으면 다음 **_lsearch_s** 배열 및 증가의 끝에 추가 하 고 *번호*합니다.

합니다 *비교* 함수는 두 배열 요소를 비교 하 고 서로의 관계를 지정 하는 값을 반환 하는 사용자가 제공한 루틴에 대 한 포인터입니다. 합니다 *비교* 함수는 첫 번째 인수로 컨텍스트에 대 한 포인터도 사용 합니다. **_lsearch_s** 호출 *비교* 검색, 각 호출에서 두 배열 요소에 대 한 포인터를 전달 하는 동안 한 번 이상. *비교* 요소를 비교 하 고 다음 중 하나를 반환 해야 합니다 (요소가 다르다는 의미) 0이 아닌 값 또는 0 (요소가 동일 하다는 의미).

합니다 *상황에 맞는* 포인터는 검색된 데이터 구조가 개체의 일부 경우에 유용할 수 있습니다 및 *비교* 함수 개체의 멤버에 액세스 해야 합니다. 예를 들어, 코드를 *비교* 함수 해당 개체의 적절 한 개체 유형 및 액세스 멤버에는 void 포인터를 캐스팅할 수 있습니다. 추가 합니다 *상황에 맞는* 포인터는 **_lsearch_s** 추가 데이터를 사용할 수 있도록 정적 변수를 사용 하 여 연결 하는 재진입 버그를 방지 하려면 추가 컨텍스트를 사용할 수 있으므로 보안 합니다 *비교* 함수입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>

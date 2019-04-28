---
title: wctrans
ms.date: 11/04/2016
apiname:
- wctrans
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 3c7aace7a93160d2e9a4c1523d49bcaf6ae4dc20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188457"
---
# <a name="wctrans"></a>wctrans

문자 코드 집합 간의 매핑을 결정합니다.

## <a name="syntax"></a>구문

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>매개 변수

*속성*<br/>
유효한 변환 중 하나를 지정하는 문자열입니다.

## <a name="return-value"></a>반환 값

경우는 **LC_CTYPE** 현재 로캘의 범주 이름이 속성 문자열을 일치 하는 매핑을 정의 하지 않습니다 *속성*, 함수가 0을 반환 합니다. 그렇지 않으면 이 함수는 [towctrans](towctrans.md)에 대한 후속 호출에 두 번째 인수로 사용할 수 있는 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

이 함수는 문자 코드 집합 간의 매핑을 결정합니다.

다음 호출 쌍은 모든 로캘에서 동일하게 동작하지만 "C" 로캘에서도 추가 매핑을 정의할 수 있습니다.

|함수|동일한 항목|
|--------------|-------------|
|tolower(c)|towctrans(c, wctrans("towlower"))|
|towupper(c)|towctrans(c, wctrans("toupper"))|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>

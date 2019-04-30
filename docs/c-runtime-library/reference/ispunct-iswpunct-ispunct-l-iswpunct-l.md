---
title: ispunct, iswpunct, _ispunct_l, _iswpunct_l
ms.date: 11/04/2016
apiname:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
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
- iswpunct
- _istpunct
- ispunct
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
ms.openlocfilehash: 209f94bb8f9d3338f62b719d4d4b94b152ed5ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286537"
---
# <a name="ispunct-iswpunct-ispunctl-iswpunctl"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l

정수가 문장 부호 문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int ispunct(
   int c
);
int iswpunct(
   wint_t c
);
int _ispunct_l(
   int c,
   _locale_t locale
);
int _iswpunct_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

각 이러한 루틴 0이 아닌 경우 반환 *c* 문장 부호 문자의 특정 표현입니다. **ispunct** 공백 문자 또는 문자를 하지 않은 모든 인쇄 가능한 문자에 대 한 0이 아닌 값을 반환 **isalnum** 0이 아닌 합니다. **iswpunct** 공백 와이드 문자 또는 와이드 문자는 인쇄 가능한 와이드 문자에 대 한 0이 아닌 값을 반환 **iswalnum** 0이 아닌 합니다. 이러한 루틴은 각각 0을 반환 *c* 테스트 조건을 충족 하지 않습니다.

에 대 한 테스트 조건의 결과 **ispunct** 함수에 따라 달라 집니다 합니다 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 자세한 내용은 합니다. 없는 이러한 함수의 버전은는 **_l** 로캘 종속 동작에 대해 현재 로캘 사용 접미사; 않은 버전을 **_l** 접미사를 사용 하는 점을 제외 하면 동일 합니다 대신에 전달 되는 로캘. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

동작 **ispunct** 하 고 **_ispunct_l** 경우 정의 되지 않습니다 *c* EOF가 범위인 0부터 0xff까지 포괄 합니다. 디버그 CRT 라이브러리가 사용 되는 경우 및 *c* 함수 raise 이러한 값 중 하나가 아닌 한 어설션입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istpunct**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**ispunct**|\<ctype.h>|
|**iswpunct**|\<ctype.h> 또는 \<wchar.h>|
|**_ispunct_l**|\<ctype.h>|
|**_iswpunct_l**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>

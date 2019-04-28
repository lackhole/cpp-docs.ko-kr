---
title: isascii, __isascii, iswascii
ms.date: 11/04/2016
apiname:
- iswascii
- __isascii
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
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
ms.openlocfilehash: d150e7bb335dc77ed86f445128eebf97b8be5ac3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287471"
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

특정 문자가 ASCII 문자인지 여부를 결정합니다.

## <a name="syntax"></a>구문

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

## <a name="return-value"></a>반환 값

각 이러한 루틴 0이 아닌 경우 반환 **c** ASCII 문자의 특정 표현입니다. **__isascii** 이면 0이 아닌 값을 반환 **c** 은 0x00-0x7F 범위의) (에서 ASCII 문자입니다. **iswascii** 이면 0이 아닌 값을 반환 **c** ASCII 문자를 와이드 문자 표현입니다. 이러한 루틴은 각각 0을 반환 **c** 테스트 조건을 충족 하지 않습니다.

## <a name="remarks"></a>설명

둘 다 **__isascii** 하 고 **iswascii** 전처리기 매크로 _CTYPE_DISABLE_MACROS가 정의 매크로로 구현 됩니다.

이전 버전과 호환성을 위해 **isascii** 경우에만 매크로로 구현 되 [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) 정의 되지 않았거나 0으로 정의 된 그렇지 않으면 정의 되지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> 또는 \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h> 또는 \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> 또는 \<wchar.h>|

합니다 **isascii**, **__isascii** 하 고 **iswascii** 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>

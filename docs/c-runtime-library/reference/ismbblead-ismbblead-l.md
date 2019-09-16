---
title: _ismbblead, _ismbblead_l
ms.date: 11/04/2016
api_name:
- _ismbblead_l
- _ismbblead
api_location:
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: c0f9ec748a86d5d1413cf4f881234d786c2a2d78
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954059"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

문자를 테스트하여 멀티바이트 문자의 선행 바이트인지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

정수 *c* 가 멀티 바이트 문자의 첫 번째 바이트인 경우 0이 아닌 값을 반환 합니다.

## <a name="remarks"></a>설명

멀티바이트 문자는 선행 바이트와 그 뒤에 오는 후행 바이트로 구성됩니다. 선행 바이트는 지정된 문자 집합에 대한 특정 범위에 있는 것으로 구분됩니다. 예를 들어 코드 페이지 932에만 0x81-0x9F 및 0xE0-0xFC의 선행 바이트 범위를 사용할 수 있습니다.

**_ismbblead** 는 로캘 종속 동작에 현재 로캘을 사용 합니다. **_ismbblead_l** 은 전달 된 로캘을 대신 사용 한다는 점을 제외 하 고 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|항상 false를 반환합니다.|**_ismbblead**|항상 false를 반환합니다.|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* 테스트 조건에 대한 매니페스트 상수에 해당합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>

---
title: towctrans
ms.date: 11/04/2016
apiname:
- towctrans
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
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: b814c65d2f5d0bb18b19d97a539d79dd6df8a1c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269165"
---
# <a name="towctrans"></a>towctrans

문자를 변형합니다.

## <a name="syntax"></a>구문

```C
wint_t towctrans(
   wint_t c,
   wctrans_t category
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
변형할 문자입니다.

*category*<br/>
[wctrans](wctrans.md)의 반환 값을 포함하는 식별자입니다.

## <a name="return-value"></a>반환 값

문자 *c*뒤 **towctrans** 변환 규칙에서 사용 되는 *범주*합니다.

## <a name="remarks"></a>설명

변수의 *범주* 호출에 의해 이전 성공적으로 반환 합니다 [wctrans](wctrans.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

참조 **wctrans** 사용 하는 샘플에 대 한 **towctrans**합니다.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>

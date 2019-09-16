---
title: towctrans
ms.date: 11/04/2016
api_name:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: d63fc343647cd0f949f282e2a64d4a0636e62bd7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957434"
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

**Towctrans** 뒤의 문자 *c*는 *범주*에서 변환 규칙을 사용 했습니다.

## <a name="remarks"></a>설명

[Wctrans](wctrans.md)에 대 한 이전 성공적인 호출에서 *category* 값을 반환 해야 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

**Towctrans**를 사용 하는 샘플은 **wctrans** 를 참조 하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>

---
title: ctan, ctanf, ctanl
ms.date: 11/04/2016
api_name:
- ctan
- ctanf
- ctanl
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ctan
- ctanf
- ctanl
- complex/ctan
- complex/ctanf
- complex/ctanl
helpviewer_keywords:
- ctan function
- ctanf function
- ctanl function
ms.assetid: d3cbd25c-1e93-4a6d-8154-da42921f7223
ms.openlocfilehash: 3d1275f795ae68777515e833a19f2b90f4fedf93
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938454"
---
# <a name="ctan-ctanf-ctanl"></a>ctan, ctanf, ctanl

복소수의 탄젠트를 검색합니다.

## <a name="syntax"></a>구문

```C
_Dcomplex ctan(
   _Dcomplex z
);
_Fcomplex ctan(
   _Fcomplex z
);  // C++ only
_Lcomplex ctan(
   _Lcomplex z
);  // C++ only
_Fcomplex ctanf(
   _Fcomplex z
);
_Lcomplex ctanl(
   _Lcomplex z
);
```

### <a name="parameters"></a>매개 변수

*z*<br/>
라디안으로 각도를 나타내는 복소수입니다.

## <a name="return-value"></a>반환 값

*Z*의 탄젠트입니다.

|입력|SEH 예외|**_matherr** 발생할|
|-----------|-------------------|--------------------------|
|± ∞, QNAN, IND|없음|_DOMAIN|
|± ∞ (**tan**, **tanf**)|INVALID|_DOMAIN|

## <a name="remarks"></a>설명

는 C++ 오버 로드를 허용 하므로 **_Fcomplex** 및 **_fcomplex** 값을 사용 하 고 반환 하는 **ctan** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **ctan** 은 항상 **_dcomplex** 값을 사용 하 고 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**ctan**,               **ctanf**, **ctanl**|\<complex.h>|\<ccomplex>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>

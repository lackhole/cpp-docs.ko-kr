---
title: csinh, csinhf, csinhl
ms.date: 11/04/2016
apiname:
- csinh
- csinhf
- csinhl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- csinh
- csinhf
- csinhl
- complex/csinh
- complex/csinhf
- complex/csinhl
helpviewer_keywords:
- csinh function
- csinhf function
- csinhl function
ms.assetid: cc616e55-d14d-4cd3-91f0-fbee03ce5edf
ms.openlocfilehash: 2ea6eaedc7eae7256310bf55b06fde0ecb2c64de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289405"
---
# <a name="csinh-csinhf-csinhl"></a>csinh, csinhf, csinhl

복소수의 쌍곡 사인을 검색합니다.

## <a name="syntax"></a>구문

```C
_Dcomplex csinh(
   _Dcomplex z
);
_Fcomplex csinh(
   _Fcomplex z
);  // C++ only
_Lcomplex csinh(
   _Lcomplex z
);  // C++ only
_Fcomplex csinhf(
   _Fcomplex z
);
_Lcomplex csinhl(
   _Lcomplex z
);
```

### <a name="parameters"></a>매개 변수

*z*<br/>
라디안으로 각도를 나타내는 복소수입니다.

## <a name="return-value"></a>반환 값

하이퍼볼릭 사인 *z*, 라디안에서입니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **csinh** 및 반환 하는 **_Fcomplex** 하 고 **_Lcomplex** 값입니다. C 프로그램에서 **csinh** 항상 받아서 반환 된 **_Dcomplex** 값입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**csinh**,               **csinhf**, **csinhl**|\<complex.h>|\<ccomplex>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>

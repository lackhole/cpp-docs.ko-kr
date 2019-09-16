---
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: e9b5aa1f7dc20cc920a51c2c36371eb907469875
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957058"
---
# <a name="fpclassify"></a>fpclassify

인수의 부동 소수점 분류를 반환합니다.

## <a name="syntax"></a>구문

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**fpclassify** 는 인수 *x*의 부동 소수점 클래스를 나타내는 정수 값을 반환 합니다. 다음 표에서는 >에 \<정의 된 **fpclassify**에서 반환 되는 가능한 값을 보여 줍니다.

|값|설명|
|-----------|-----------------|
|**FP_NAN**|자동, 신호 또는 비활성화 상태 NaN|
|**FP_INFINITE**|양수 또는 음수 무한대|
|**FP_NORMAL**|정규화된 0이 아닌 양수 또는 음수 값|
|**FP_SUBNORMAL**|비정규화된 양수 또는 음수 값|
|**FP_ZERO**|양수 또는 음수 0 값|

## <a name="remarks"></a>설명

C에서 **fpclassify** 는 매크로입니다. 에서 C++ **fpclassify** 는 **float**, **double**또는 **long** **double**의 인수 형식을 사용 하 여 오버 로드 된 함수입니다. 두 경우 모두 반환되는 값은 인수 식의 유효 형식에 따라 결정되고 중간 표현의 영향은 받지 않습니다. 예를 들어, 보통 **double** 또는 **long** **double** 값은 **float**로 변환 될 때 infinity, denormal 또는 0 값이 될 수 있습니다.

## <a name="requirements"></a>요구 사항

|함수/매크로|필수 헤더(C)|필수 헤더(C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> 또는 \<cmath>|

**Fpclassify** 매크로 및 **FPCLASSIFY** 함수는 ISO C99 및 c + + 11 사양을 따릅니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>

---
title: fpclassify
ms.date: 04/05/2018
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: a25897a110d96923a45695d61f923dc7818c7e3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287943"
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

**fpclassify** 인수의 부동 소수점 클래스를 나타내는 정수 값을 반환 *x*합니다. 이 테이블에서 반환 된 가능한 값을 보여 줍니다 **fpclassify**에 정의 된 \<math.h >.

|값|설명|
|-----------|-----------------|
|**FP_NAN**|자동, 신호 또는 비활성화 상태 NaN|
|**FP_INFINITE**|양수 또는 음수 무한대|
|**FP_NORMAL**|정규화된 0이 아닌 양수 또는 음수 값|
|**FP_SUBNORMAL**|비정규화된 양수 또는 음수 값|
|**FP_ZERO**|양수 또는 음수 0 값|

## <a name="remarks"></a>설명

C에서 **fpclassify** 는 매크로, C++를 **fpclassify** 의 인수 형식을 사용 하 여 오버 로드 된 함수 **float**를 **double**, 또는 **긴** **double**합니다. 두 경우 모두 반환되는 값은 인수 식의 유효 형식에 따라 결정되고 중간 표현의 영향은 받지 않습니다. 예를 들어, 일반적인 **이중** 또는 **긴** **double** 값 수 있게 무한대, 비정상 또는 0 값으로 변환할 때를 **float**합니다.

## <a name="requirements"></a>요구 사항

|함수/매크로|필수 헤더(C)|필수 헤더(C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> 또는 \<cmath>|

합니다 **fpclassify** 매크로 **fpclassify** 함수는 ISO C99 및 c++11 사양을 준수 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>

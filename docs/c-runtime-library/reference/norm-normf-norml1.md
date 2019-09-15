---
title: norm, normf, norml
ms.date: 04/05/2018
api_name:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
ms.openlocfilehash: 8deaa07d984a3840c73e594535ffffc9078d4716
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951314"
---
# <a name="norm-normf-norml"></a>norm, normf, norml

복소수의 제곱 크기를 검색합니다.

## <a name="syntax"></a>구문

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>매개 변수

*z*<br/>
복소수입니다.

## <a name="return-value"></a>반환 값

*Z*의 제곱 크기입니다.

## <a name="remarks"></a>설명

는 C++ 오버 로드를 허용 하므로 **_Fcomplex** 또는 **_fcomplex** 값을 사용 하 고 **float** 또는 **long double** **값을 반환 하는 일반적인** 오버 로드를 호출할 수 있습니다. C 프로그램에서 일반은 항상 **_d** **값을 사용** 하 여 **double** 값을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**norm**, **normf**, **norml**|\<complex.h>|\<complex.h>|

**_Fcomplex**, **_Fcomplex**및 **_Fcomplex** 형식은 각각 C99에서 구현 되지 않은 네이티브 형식으로 **서, float**, **Double _complex**및 **long double _complex**의 Microsoft 관련 항목입니다.  호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>

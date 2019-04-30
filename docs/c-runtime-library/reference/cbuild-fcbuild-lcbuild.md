---
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
apiname:
- _Cbuild
- _FCbuild
- _LCbuild
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
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: 5565c87a3cccd1715a1357f417238587f3fba4d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340468"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

실수부 및 허수부에서 복소수 생성합니다.

## <a name="syntax"></a>구문

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>매개 변수

*real*<br/>
실수 부분을 생성 하는 복소수입니다.

*imaginary*<br/>
생성 하는 복소수의 허수 부분입니다.

## <a name="return-value"></a>반환 값

A **_Dcomplex**를 **_Fcomplex**, 또는 **_Lcomplex** 복소수를 나타내는 구조 (*실제*, *허수*  \* 있나요) 지정 된 부동 소수점 형식의 값에 대 한 합니다.

## <a name="remarks"></a>설명

합니다 **_Cbuild**를 **_FCbuild**, 및 **_LCbuild** 복합 형식의 생성을 단순화 하는 함수입니다. 사용 된 [creal, crealf, creall](creal-crealf-creall.md) 및 [cimag, cimagf, cimagl](cimag-cimagf-cimagl.md) 표시 되는 복소수의 실수와 허수 부분을 검색 하는 함수입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

이러한 함수는 Microsoft 전용입니다. 형식을 **_Dcomplex**를 **_Fcomplex**, 및 **_Lcomplex** 구현 되지 않은 C99 네이티브 형식에 해당 하는 Microsoft 전용은 **double _Complex** 하십시오 **float _Complex**, 및 **long double _Complex**각각. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>

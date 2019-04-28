---
title: clog10, clog10f, clog10l
ms.date: 11/04/2016
apiname:
- clog10
- clog10f
- clog10l
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
- clog10
- clog10f
- clog10l
- complex/clog10
- complex/clog10f
- complex/clog10l
helpviewer_keywords:
- clog10 function
- clog10f function
- clog10l function
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
ms.openlocfilehash: 195f4be80f0320e83cc9455a598185ce281bbf59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335456"
---
# <a name="clog10-clog10f-clog10l"></a>clog10, clog10f, clog10l

복소수의 밑이 10인 로그를 검색합니다.

## <a name="syntax"></a>구문

```C
_Dcomplex clog10( _Dcomplex z );
_Fcomplex clog10f( _Fcomplex z );
_Lcomplex clog10l( _Lcomplex z );
```

```cpp
_Fcomplex clog10( _Fcomplex z );  // C++ only
_Lcomplex clog10( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>매개 변수

*z*<br/>
로그의 밑입니다.

## <a name="return-value"></a>반환 값

가능한 반환 값은 다음과 같습니다.

|z 매개 변수|반환 값|
|-----------------|------------------|
|양수|z의 밑이 10인 로그|
|0|- ∞|
|음수|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **clog10** 및 반환 하는 **_Fcomplex** 하 고 **_Lcomplex** 값입니다. C 프로그램에서 **clog10** 항상 받아서 반환 된 **_Dcomplex** 값입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**clog10**,               **clog10f**, **clogl**|\<complex.h>|\<ccomplex>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>

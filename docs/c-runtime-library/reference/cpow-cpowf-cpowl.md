---
title: cpow, cpowf, cpowl
ms.date: 11/04/2016
apiname:
- cpow
- cpowf
- cpowl
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
- cpow
- cpowf
- cpowl
- complex/cpow
- complex/cpowf
- complex/copwl
helpviewer_keywords:
- cpow function
- cpowf function
- complex/cpowl function
ms.assetid: 83fe2187-22b7-4295-ab16-4d77abdbb80b
ms.openlocfilehash: 588c437a01237de297e1db31fb2c507eb1145d90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339847"
---
# <a name="cpow-cpowf-cpowl"></a>cpow, cpowf, cpowl

지정된 지수로 거듭제곱한 밑에 해당하는 값을 검색합니다. 여기서 밑과 지수는 복소수입니다. 이 함수는 음의 실수 축을 따라 지수에 대한 분기가 있습니다.

## <a name="syntax"></a>구문

```C
_Dcomplex cpow(
   _Dcomplex x, _Dcomplex y
);
_Fcomplex cpow(
   _Fcomplex x, _Fcomplex y
);  // C++ only
_Lcomplex cpow(
   _Lcomplex x, _Lcomplex y
);  // C++ only
_Fcomplex cpowf(
   _Fcomplex x, _Fcomplex y
);
_Lcomplex cpowl(
   _Lcomplex x, _Lcomplex y
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
밑입니다.

*y*<br/>
지수입니다.

## <a name="return-value"></a>반환 값

변수의 *x* 의 거듭제곱 *y* 에 대 한 분기를 사용 하 여 *x* 음의 실수 축을 따라 합니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **cpow** 및 반환 하는 **_Fcomplex** 하 고 **_Lcomplex** 값입니다. C 프로그램에서 **cpow** 항상 받아서 반환 된 **_Dcomplex** 값입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**cpow**,               **cpowf**, **cpowl**|\<complex.h>|\<ccomplex>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>

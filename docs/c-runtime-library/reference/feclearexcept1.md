---
title: feclearexcept1
ms.date: 04/05/2018
apiname:
- feclearexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- feclearexcept
- fenv/feclearexcept
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
ms.openlocfilehash: 3c2f037a5be903fc006debfa7319c483431fdd92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334738"
---
# <a name="feclearexcept"></a>feclearexcept

인수를 통해 지정한 부동 소수점 예외 플래그를 지우려고 합니다.

## <a name="syntax"></a>구문

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>매개 변수

*excepts*<br/>
지울 예외 상태 플래그입니다.

## <a name="return-value"></a>반환 값

경우에는 0을 반환 합니다 *를 제외한* 가 0 이면 모든 지정 된 예외가 성공적으로 지워진 경우. 그렇지 않으면 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

합니다 **feclearexcept** 부동의 선택을 취소 하려고 하는 함수 지점으로 지정 된 예외 상태 플래그 *제외한*합니다. 이 함수는 fenv.h에 정의된 다음 예외 매크로를 지원합니다.

|예외 매크로|설명|
|---------------------|-----------------|
|FE_DIVBYZERO|초기 부동 소수점 작업에서 특이성 또는 극 오류가 발생했습니다. 무한대 값이 생성되었습니다.|
|FE_INEXACT|함수가 초기 부동 소수점 작업의 저장된 결과를 강제로 반올림했습니다.|
|FE_INVALID|초기 부동 소수점 작업에서 도메인 오류가 발생했습니다.|
|FE_OVERFLOW|범위 오류가 발생했습니다. 초기 부동 소수점 작업 결과가 표시하기에 너무 큽니다.|
|FE_UNDERFLOW|초기 부동 소수점 작업 결과가 완전히 정확하게 표시하기에 너무 작습니다. 비정상적인 값이 생성되었습니다.|
|FE_ALL_EXCEPT|모든 지원되는 부동 소수점 예외의 비트 OR입니다.|

합니다 *를 제외한* 인수는 0 또는 지원 되는 예외 매크로 중 하나 이상의 비트 OR 일 수 있습니다. 기타 인수 값의 결과는 정의 해제됩니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>

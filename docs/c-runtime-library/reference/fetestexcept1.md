---
title: fetestexcept
ms.date: 04/05/2018
apiname:
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
ms.openlocfilehash: ed75ab0ff13029f6ec10c1aafbcb7f7b23b46fd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334167"
---
# <a name="fetestexcept"></a>fetestexcept

지정된 부동 소수점 예외 상태 플래그 중 현재 설정되어 있는 예외 상태 플래그를 확인합니다.

## <a name="syntax"></a>구문

```C
int fetestexcept(
   int excepts
);
```

### <a name="parameters"></a>매개 변수

*excepts*<br/>
테스트할 부동 소수점 상태 플래그의 비트 OR입니다.

## <a name="return-value"></a>반환 값

성공할 경우 현재 설정된 예외 상태 플래그에 해당하는 부동 소수점 예외 매크로의 비트 OR가 포함된 비트 마스크를 반환합니다. 예외가 설정되지 않은 경우 0을 반환합니다.

## <a name="remarks"></a>설명

fetestexcept 함수를 사용하여 부동 소수점 작업을 통해 어떤 예외가 발생했는지 확인합니다. 사용 된 *를 제외한* 매개 변수를 테스트 하는 예외 상태 플래그를 지정 합니다. 합니다 **fetestexcept** 함수에 정의 된 다음 예외 매크로 사용 하 여 \<n v. h >에 *제외한* 및 반환 값:

|예외 매크로|설명|
|---------------------|-----------------|
|FE_DIVBYZERO|초기 부동 소수점 작업에서 특이성 또는 극 오류가 발생했습니다. 무한대 값이 생성되었습니다.|
|FE_INEXACT|함수가 초기 부동 소수점 작업의 저장된 결과를 강제로 반올림했습니다.|
|FE_INVALID|초기 부동 소수점 작업에서 도메인 오류가 발생했습니다.|
|FE_OVERFLOW|범위 오류가 발생했습니다. 초기 부동 소수점 작업 결과가 표시하기에 너무 큽니다.|
|FE_UNDERFLOW|초기 부동 소수점 작업 결과가 완전히 정확하게 표시하기에 너무 작습니다. 비정상적인 값이 생성되었습니다.|
|FE_ALLEXCEPT|모든 지원되는 부동 소수점 예외의 비트 OR입니다.|

지정 된 *를 제외한* 인수 또는 매크로 중 두 개 이상의 지원 되는 부동 소수점 예외 매크로 또는 비트는 0 일 수 있습니다. 다른 미치는 *를 제외한* 인수 값이 정의 되지 않습니다.

이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>

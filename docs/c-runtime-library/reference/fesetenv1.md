---
title: fesetenv
ms.date: 04/05/2018
apiname:
- fesetenv
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
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 8c91bfbb89df964fed0a632d5fb5ebac47ebe948
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334197"
---
# <a name="fesetenv"></a>fesetenv

현재 부동 소수점 환경을 설정합니다.

## <a name="syntax"></a>구문

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>매개 변수

*penv*<br/>
에 대 한 포인터를 **fenv_t** 를 호출 하 여 집합으로 부동 소수점 환경을 포함 하는 개체 [fegetenv](fegetenv1.md) 하거나 [feholdexcept](feholdexcept2.md)합니다. 사용 하 여 기본 시작 부동 소수점 환경을 지정할 수도 있습니다는 **FE_DFL_ENV** 매크로입니다.

## <a name="return-value"></a>반환 값

환경이 성공적으로 설정된 경우 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

**fesetenv** 에 저장 된 값에서 현재 부동 소수점 환경을 설정 하는 함수는 **fenv_t** 가리키는 개체가 *penv*합니다. 부동 소수점 환경은 부동 소수점 계산에 영향을 미치는 상태 플래그 및 제어 모드의 집합입니다. 여기에는 부동 소수점 예외에 대한 상태 플래그와 반올림 모드가 포함됩니다.  하는 경우 *penv* 아닙니다 **FE_DFL_ENV** 유효한를 가리키지 않습니다 또는 **fenv_t** 개체를 후속 동작이 정의 되지 않습니다.

이 함수 호출 예외에는 상태 플래그를 설정 합니다 *penv* 개체 있지만 이러한 예외를 발생 하지 않습니다.

이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>

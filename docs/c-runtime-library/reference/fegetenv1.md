---
title: fegetenv
ms.date: 04/05/2018
apiname:
- fetegenv
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
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: d3985e4dd2b3944bcdddb79605887def7ba15473
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334413"
---
# <a name="fegetenv"></a>fegetenv

지정된 개체에 현재 부동 소수점 환경을 저장합니다.

## <a name="syntax"></a>구문

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>매개 변수

*penv*<br/>
에 대 한 포인터를 **fenv_t** 현재 부동 소수점 환경 값을 포함 하는 개체입니다.

## <a name="return-value"></a>반환 값

부동 소수점 환경에 성공적으로 저장 된 경우 0 반환 합니다 *penv*합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

합니다 **fegetenv** 함수에서 가리키는 개체에 따라 현재 부동 소수점 환경을 저장 *penv*합니다. 부동 소수점 환경은 부동 소수점 계산에 영향을 미치는 상태 플래그 및 제어 모드의 집합입니다. 여기에는 부동 소수점 예외에 대한 상태 플래그와 반올림 방향 모드가 포함됩니다.  하는 경우 *penv* 유효한 가리키지 **fenv_t** 개체를 후속 동작이 정의 되지 않습니다.

이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>

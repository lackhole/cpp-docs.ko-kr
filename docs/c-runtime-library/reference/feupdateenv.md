---
title: feupdateenv
ms.date: 04/05/2018
apiname:
- feupdateenv
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
- feupdateenv
- fenv/feupdateenv
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
ms.openlocfilehash: 6d553d6899f55f5bdfb3ff313e88abfcb56ab4ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334076"
---
# <a name="feupdateenv"></a>feupdateenv

현재 발생한 부동 소수점 예외를 저장하고, 지정된 부동 소수점 환경 상태를 복원하고 나서, 저장된 부동 소수점 예외를 발생시킵니다.

## <a name="syntax"></a>구문

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>매개 변수

*penv*<br/>
에 대 한 포인터를 **fenv_t** 를 호출 하 여 집합으로 부동 소수점 환경을 포함 하는 개체 [fegetenv](fegetenv1.md) 하거나 [feholdexcept](feholdexcept2.md)합니다. FE_DFL_ENV 매크로를 사용하여 기본 시작 부동 소수점 환경을 지정할 수도 있습니다.

## <a name="return-value"></a>반환 값

모든 작업이 성공적으로 완료되면 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

합니다 **feupdateenv** 함수는 여러 작업을 수행 합니다. 먼저, 현재 발생한 부동 소수점 예외 상태 플래그를 자동 스토리지에 저장합니다. 그런 다음 저장 된 값에서 현재 부동 소수점 환경을 설정 합니다 **fenv_t** 가리키는 개체 *penv*합니다. 하는 경우 *penv* 아닙니다 **FE_DFL_ENV** 유효한를 가리키지 않습니다 또는 **fenv_t** 개체를 후속 동작이 정의 되지 않습니다. 마지막으로, **feupdateenv** 로컬에 저장 된 부동 소수점 예외를 발생 시킵니다.

이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>

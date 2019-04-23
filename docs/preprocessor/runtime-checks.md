---
title: runtime_checks
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: 44c26fb90a2d2f9ba78ec7dba7cceed65a4b4ed7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027085"
---
# <a name="runtimechecks"></a>runtime_checks
[/RTC](../build/reference/rtc-run-time-error-checks.md) 설정을 사용할 수 없도록 설정하거나 복원합니다.

## <a name="syntax"></a>구문

```
#pragma runtime_checks( "[runtime_checks]", {restore | off} )
```

## <a name="remarks"></a>설명

컴파일러 옵션으로 설정되지 않은 런타임 검사를 사용할 수 없습니다. 예를 들어, 지정 하지 않는 경우 `/RTCs`지정, `#pragma runtime_checks( "s", restore)` 가 스택 프레임 유효성 확인을 사용 하지 않습니다.

**runtime_checks** pragma는 함수 외부에 있어야 하며 pragma가 표시된 후에 정의된 첫 번째 함수에 적용됩니다. *restore* 및 *off* 인수는 **runtime_checks** 에 지정된 옵션을 켜거나 끕니다.

**runtime_checks** 는 다음 표에 표시된 0개 이상의 매개 변수가 될 수 있습니다.

### <a name="parameters-of-the-runtimechecks-pragma"></a>runtime_checks Pragma의 매개 변수

|매개 변수|런타임 검사 형식|
|--------------------|-----------------------------|
|*s*|스택(프레임)을 확인하도록 설정합니다.|
|*c*|데이터 손실이 발생하는 더 작은 데이터 형식에 값이 할당되는 경우 이를 보고합니다.|
|*u*|정의되기 전에 변수를 사용하면 보고합니다.|

이 동일한 문자 사용을 `/RTC` 컴파일러 옵션입니다. 예를 들어:

```
#pragma runtime_checks( "sc", restore )
```

**runtime_checks** pragma를 빈 문자열(**""**)과 함께 사용하는 것은 특별한 형태의 지시문입니다.

- *off* 매개 변수를 사용하는 경우 위의 표에 나열된 런타임 오류 검사를 끕니다.

- 사용 하는 경우는 *복원* 매개 변수를 런타임 오류 검사를 재설정 지정 된 된 `/RTC` 컴파일러 옵션입니다.

```
#pragma runtime_checks( "", off )
.
.
.
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
title: ArgTraitsHelper 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: fbba6d96106cc95910ccd9d0029cb3e9c254d7d3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784983"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>매개 변수

*TDelegateInterface*<br/>
대리자 인터페이스입니다.

## <a name="remarks"></a>설명

대리자 인수의 공통 된 특징을 정의할 수 있습니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름         | 설명
------------ | ------------------------------------------------------
`methodType` | `decltype(&TDelegateInterface::Invoke)`의 동의어입니다.
`Traits`     | `ArgTraits<methodType>`의 동의어입니다.

### <a name="public-constants"></a>공용 상수

이름                           | 설명
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper::args](#args) | 데 도움이 됩니다 [argtraits:: Args](#args) 매개 변수 개수를 유지는 `Invoke` 대리자 인터페이스의 메서드입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ArgTraitsHelper`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="args"></a>ArgTraitsHelper::args

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>설명

데 도움이 됩니다 `ArgTraitsHelper::args` 매개 변수 개수를 유지는 `Invoke` 대리자 인터페이스의 메서드입니다.

---
title: VerifyInheritanceHelper 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: c37a0eb74fd65b3d349d5b8b7c792fbaf7d1ac9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398084"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>매개 변수

*I*<br/>
형식입니다.

*Base*<br/>
다른 형식입니다.

## <a name="remarks"></a>설명

하나의 인터페이스는 다른 인터페이스에서 파생 됩니다 있는지 테스트 합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

이름                                       | 설명
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper::Verify](#verify) | 현재 템플릿 매개 변수로 지정 된 두 가지 인터페이스를 테스트 하 고 하나의 인터페이스는 다른 파생 되었는지 여부를 결정 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`VerifyInheritanceHelper`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="verify"></a>VerifyInheritanceHelper::Verify

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static void Verify();
```

### <a name="remarks"></a>설명

현재 템플릿 매개 변수로 지정 된 두 가지 인터페이스를 테스트 하 고 하나의 인터페이스는 다른 파생 되었는지 여부를 결정 합니다.

오류는 하나의 인터페이스는 다른에서 파생 되지 않은 경우에 내보내집니다.

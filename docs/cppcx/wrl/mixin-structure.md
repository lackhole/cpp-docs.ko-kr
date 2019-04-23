---
title: MixIn 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: 16fd6b46d616df7163a304afa7f32ac3c095d398
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031078"
---
# <a name="mixin-structure"></a>MixIn 구조체

런타임 클래스가 Windows 런타임 인터페이스에서 파생되었는지 확인한 다음 있는 경우 클래식 COM 인터페이스를 확인합니다.

## <a name="syntax"></a>구문

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>매개 변수

*파생 된*<br/>
형식에서 파생 된 [구현](implements-structure.md) 구조입니다.

*MixInType*<br/>
기본 형식입니다.

*hasImplements*<br/>
**true** 하는 경우 *MixInType* 는 현재 구현에서 파생 된 기본 형식입니다. **false** 그렇지 않은 경우.

## <a name="remarks"></a>설명

Windows 런타임 및 COM 클래스 인터페이스에서 파생 된 클래스는, 클래스 선언 목록에는 모든 Windows 런타임 인터페이스 먼저 나열 해야 합니다 하 고 모든 클래식 COM 인터페이스입니다. **MixIn** 인터페이스가 올바른 순서로 지정 되어 있는지 확인 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`MixIn`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고자료

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
---
title: RuntimeClassType 열거형
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 3b869be00cdc405569b82bdf3730f8d4ca4f3aab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785708"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 열거형

유형을 지정 [RuntimeClass](runtimeclass-class.md) 지원 되는 인스턴스.

## <a name="syntax"></a>구문

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>멤버

### <a name="values"></a>값

|이름|설명|
|----------|-----------------|
|`ClassicCom`|클래식 COM 런타임 클래스입니다.|
|`Delegate`|`ClassicCom`와 같습니다.|
|`InhibitFtmBase`|사용 하지 않도록 설정 `FtmBase` 하는 동안 지원을 `__WRL_CONFIGURATION_LEGACY__` 정의 되어 있지 않습니다.|
|`InhibitWeakReference`|약한 참조 지원을 사용 하지 않도록 설정 합니다.|
|`WinRt`|Windows 런타임 클래스입니다.|
|`WinRtClassicComMix`|`WinRt` 및 `ClassicCom`의 조합입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
---
title: GetModuleBase 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 4d8c8467b7aeb9c21bf5f4ee19c60e6e60880688
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784938"
---
# <a name="getmodulebase-function"></a>GetModuleBase 함수

검색을 [ModuleBase](modulebase-class.md) 포인터의 참조 횟수를 증가 및 감소를 허용 하는 [RuntimeClass](runtimeclass-class.md) 개체입니다.

## <a name="syntax"></a>구문

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>반환 값

`ModuleBase` 개체에 대한 포인터입니다.

## <a name="remarks"></a>설명

이 함수는 데 내부적으로 증가 및 감소 개체 참조를 계산 합니다.

호출 하 여 참조 횟수를 제어 하려면이 함수를 사용할 수 있습니다 [modulebase:: Incrementobjectcount](modulebase-class.md#incrementobjectcount) 하 고 [modulebase:: Decrementobjectcount](modulebase-class.md#decrementobjectcount)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고자료

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
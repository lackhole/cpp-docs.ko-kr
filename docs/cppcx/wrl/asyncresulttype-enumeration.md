---
title: AsyncResultType 열거형
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: d3f99fa85a777ae8361ed6f7cb82fe97ddd8d667
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028055"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 열거형

반환 된 결과의 형식을 지정 합니다 `GetResults()` 메서드.

## <a name="syntax"></a>구문

```cpp
enum AsyncResultType;
```

## <a name="members"></a>멤버

### <a name="values"></a>값

|이름|설명|
|----------|-----------------|
|`MultipleResults`|간에 점진적으로 제공 되는 여러 결과 집합이 `Start` 상태 전과 `Close()` 라고 합니다.|
|`SingleResult`|후 제공 되는 단일 결과는 `Complete` 이벤트가 발생 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** async.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고자료

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
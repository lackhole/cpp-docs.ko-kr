---
title: raw_dispinterfaces
ms.date: 11/04/2016
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: ef8ed3992c77df0f1d551e923ddc90c2d1bb9b0b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027925"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C++ 전용**

호출 하는 dispinterface 메서드 및 속성에 대 한 하위 수준의 래퍼 함수를 생성 하도록 컴파일러에 지시 `IDispatch::Invoke` HRESULT 오류 코드를 반환 합니다.

## <a name="syntax"></a>구문

```
raw_dispinterfaces
```

## <a name="remarks"></a>설명

이 특성이 지정되지 않은 경우 실패 시 C++ 예외를 throw하는 상위 수준 래퍼만 생성됩니다.

**C++ 전용 종료**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
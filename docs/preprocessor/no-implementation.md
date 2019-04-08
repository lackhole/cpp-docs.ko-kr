---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 26527ca69c66c73f5d41084dc42df5faa34481d3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030543"
---
# <a name="noimplementation"></a>no_implementation
**C++ 전용**

래퍼 멤버 함수의 구현이 포함된 .tli 헤더를 생성하지 않습니다.

## <a name="syntax"></a>구문

```
no_implementation
```

## <a name="remarks"></a>설명

이 특성이 지정된 경우 형식 라이브러리 항목을 노출하는 선언이 포함된 .tlh 헤더가 .tli 헤더 파일을 포함하는 `#include` 문 없이 생성됩니다.

이 특성은 함께에서 사용 [implementation_only](../preprocessor/implementation-only.md)합니다.

**C++ 전용 종료**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
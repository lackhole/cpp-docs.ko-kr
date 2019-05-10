---
title: 컴파일러 경고(수준 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 9868d33538a1f56906455f2b1772b53eb3a7734d
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447092"
---
# <a name="compiler-warning-level-1-c4581"></a>컴파일러 경고(수준 1) C4581

사용 되지 않는 동작: '"string1" ' 'string2' 프로세스 특성을 사용 하 여 대체

이 오류는 Visual Studio 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 시각적 개체에 대해 확인 하는 매개 변수 C++ 특성입니다.

이전 버전에서는 특성 값은 따옴표로 묶여 있는지 여부 또는 허용 되었습니다. 값이 열거형 인 경우 하지 인용 부호로 묶어야 합니다.

## <a name="example"></a>예제

다음 샘플 C4581를 생성합니다.

```
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```
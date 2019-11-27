---
title: 컴파일러 경고(수준 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: 1d0531b79ef29d2aa9528cc29046fa9e9514c379
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541978"
---
# <a name="compiler-warning-level-4-c4268"></a>컴파일러 경고(수준 4) C4268

' identifier ': 컴파일러에서 생성 된 ' const ' 정적/전역 데이터는 개체를 0으로 채웁니다.

특수 하지 않은 클래스의 **const** 전역 또는 정적 인스턴스는 컴파일러 생성 기본 생성자를 사용 하 여 초기화 됩니다.

## <a name="example"></a>예제

```cpp
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

클래스의이 인스턴스가 **const**이므로 `m_data`의 값은 변경할 수 없습니다.
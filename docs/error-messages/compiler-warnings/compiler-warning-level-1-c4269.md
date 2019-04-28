---
title: 컴파일러 경고(수준 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 9a7f42b2dd65644d3f2abec58236a0b93cc6f635
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207235"
---
# <a name="compiler-warning-level-1-c4269"></a>컴파일러 경고(수준 1) C4269

'identifier': 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 하는 'const' 자동 데이터 신뢰할 수 없는 결과 생성 합니다.

A **const** trivial이 아닌 클래스의 자동 인스턴스는 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 됩니다.

## <a name="example"></a>예제

```
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

클래스의이 인스턴스가 생성의 초기 값을 스택에 `m_data` 하나일 수 있습니다. 또한 이므로 **상수** 인스턴스를 값 `m_data` 변경할 수 없습니다.
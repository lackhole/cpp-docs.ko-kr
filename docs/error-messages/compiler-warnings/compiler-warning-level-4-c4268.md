---
title: 컴파일러 경고(수준 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: e3cda7ed70963508d7663c6c12b2b98ac64db204
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400918"
---
# <a name="compiler-warning-level-4-c4268"></a>컴파일러 경고(수준 4) C4268

'identifier': 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 하는 'const' 정적/전역 데이터 개체를 0으로 채우는

A **const** trivial이 아닌 클래스의 인스턴스를 전역 또는 정적 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 됩니다.

## <a name="example"></a>예제

```
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

클래스의이 인스턴스는 **상수**, 변수의 `m_data` 변경할 수 없습니다.
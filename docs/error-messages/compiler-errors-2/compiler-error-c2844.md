---
title: 컴파일러 오류 C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: fdfd2200503f80addb120117ce06f5f837d6b9f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752017"
---
# <a name="compiler-error-c2844"></a>컴파일러 오류 C2844

' member ': ' interface ' 인터페이스의 멤버일 수 없습니다.

[인터페이스 클래스](../../extensions/interface-class-cpp-component-extensions.md) 는 속성 이기도 한 경우를 제외 하 고는 데이터 멤버를 포함할 수 없습니다.

인터페이스에는 속성 또는 멤버 함수 이외의 모든 항목을 사용할 수 없습니다. 또한 생성자, 소멸자 및 연산자는 허용 되지 않습니다.

다음 샘플에서는 C2844를 생성 합니다.

```cpp
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```

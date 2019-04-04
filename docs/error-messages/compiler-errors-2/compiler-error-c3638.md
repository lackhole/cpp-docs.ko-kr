---
title: 컴파일러 오류 C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 33bb248faf946c39543de4a14a44e2ebbda49880
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775233"
---
# <a name="compiler-error-c3638"></a>컴파일러 오류 C3638

'operator': 기본 boxing 및 unboxing 변환 연산자를 재정의할 수 없습니다

컴파일러는 암시적 boxing을 지원 하도록 각 관리 되는 클래스에 대 한 변환 연산자를 정의 합니다. 이 연산자를 재정의할 수 없습니다.

자세한 내용은 [암시적 Boxing](../../extensions/boxing-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3638 오류가 생성 됩니다.

```
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```
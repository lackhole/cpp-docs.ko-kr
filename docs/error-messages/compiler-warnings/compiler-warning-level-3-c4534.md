---
title: 컴파일러 경고(수준 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 81445ff42aca78a8e40e9c88eff4bb76a41a8669
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776900"
---
# <a name="compiler-warning-level-3-c4534"></a>컴파일러 경고(수준 3) C4534

'constructor'를 기본 인수 때문에 ' class' 클래스에 대 한 기본 생성자를 됩니다.

관리 되지 않는 클래스에는 기본값이 있는 매개 변수를 사용 하 여 생성자가 수 및 컴파일러가 기본 생성자로 사용 됩니다. 클래스에 표시 된 `value` 키워드는 생성자를 사용 하지는 기본값을 사용 하 여 해당 매개 변수에 대 한 기본 생성자로 합니다.

자세한 내용은 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)합니다.

다음 샘플에서는 C4534 오류가 생성 됩니다.

```
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```
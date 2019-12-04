---
title: 컴파일러 오류 C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 20c17eaa6555b5511ecbc930eacdb2ec92475b23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749505"
---
# <a name="compiler-error-c3893"></a>컴파일러 오류 C3893

' var ': ' type_name ' 클래스의 인스턴스 생성자 에서만 initonly 데이터 멤버를 l-value로 사용할 수 있습니다.

정적 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버는 정적 생성자에서 해당 주소만 가져올 수 있습니다.

인스턴스 (비정적) initonly 데이터 멤버는 인스턴스 (비정적) 생성자에서 해당 주소만 가져올 수 있습니다.

다음 샘플에서는 C3893를 생성 합니다.

```cpp
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```

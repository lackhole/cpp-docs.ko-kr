---
title: 컴파일러 오류 C2775
ms.date: 11/04/2016
f1_keywords:
- C2775
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
ms.openlocfilehash: be858c7508aa520f78ec144b02738af02099b49b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740054"
---
# <a name="compiler-error-c2775"></a>컴파일러 오류 C2775

' identifier ':이 속성과 연결 된 ' get ' 메서드가 없습니다.

확장 특성 [속성](../../cpp/property-cpp.md) 을 사용 하 여 선언 된 데이터 멤버에 `get` 함수가 지정 되어 있지 않지만 식이 해당 값을 검색 하려고 합니다.

다음 샘플에서는 C2775를 생성 합니다.

```cpp
// C2775.cpp
struct A {
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;
   int GetProp2(){return 0;}
   void PutProp2(int){}

   __declspec(property(put=PutProp)) int prop;
   int PutProp(void){}

};

int main() {
   A* pa = new A;
   int x;
   x = pa->prop;   // C2775
   x = pa->prop2;
}
```

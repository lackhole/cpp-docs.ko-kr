---
title: 컴파일러 오류 C2775
ms.date: 11/04/2016
f1_keywords:
- C2775
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
ms.openlocfilehash: b0f04a64354f549115c8636cf6130d6e96470016
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257194"
---
# <a name="compiler-error-c2775"></a>컴파일러 오류 C2775

'identifier': 없음 'get' 메서드는이 속성을 사용 하 여 연결

데이터 멤버를 사용 하 여 선언 합니다 [속성](../../cpp/property-cpp.md) 확장된 특성이 없으면를 `get` 함수를 지정 했지만 식을 해당 값을 검색 하려고 합니다.

다음 샘플에서는 C2775 오류가 생성 됩니다.

```
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
---
title: 컴파일러 오류 C2774
ms.date: 11/04/2016
f1_keywords:
- C2774
helpviewer_keywords:
- C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
ms.openlocfilehash: 2630dba6a74bf6b31a5df7af57e42fd7c8fd4e09
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740106"
---
# <a name="compiler-error-c2774"></a>컴파일러 오류 C2774

' identifier ':이 속성과 연결 된 ' put ' 메서드가 없습니다.

[속성](../../cpp/property-cpp.md) 을 사용 하 여 선언 된 데이터 멤버에 `put` 함수가 없지만 식에서 해당 값을 설정 하려고 합니다.

다음 샘플에서는 C2774를 생성 합니다.

```cpp
// C2774.cpp
struct A {
   __declspec(property(get=GetProp)) int prop;
   int GetProp(void);

   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;
   int GetProp2(void);
   void PutProp2(int);
};

int main() {
   A* pa = new A;
   int val = 0;
   pa->prop = val;   // C2774
   pa->prop++;   // C2774
}
```

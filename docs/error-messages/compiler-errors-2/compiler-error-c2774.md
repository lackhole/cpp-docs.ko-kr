---
title: 컴파일러 오류 C2774
ms.date: 11/04/2016
f1_keywords:
- C2774
helpviewer_keywords:
- C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
ms.openlocfilehash: 6197e3da81a9f059c90d15608a939ad4887e526d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257142"
---
# <a name="compiler-error-c2774"></a>컴파일러 오류 C2774

'identifier':이 속성과 연결 된 'put' 메서드가 없습니다

데이터 멤버를 사용 하 여 선언 [속성](../../cpp/property-cpp.md) 아무런 `put` 함수 하지만 식을 해당 값을 설정 하려고 합니다.

다음 샘플에서는 C2774 오류가 생성 됩니다.

```
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
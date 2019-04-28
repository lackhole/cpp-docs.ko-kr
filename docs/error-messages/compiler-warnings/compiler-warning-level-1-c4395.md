---
title: 컴파일러 경고(수준 1) C4395
ms.date: 11/04/2016
f1_keywords:
- C4395
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
ms.openlocfilehash: 27503b94a18b949637293201203e18793f5e7788
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182407"
---
# <a name="compiler-warning-level-1-c4395"></a>컴파일러 경고(수준 1) C4395

'function': 멤버 함수가 initonly 데이터 멤버 'member'의 복사본에서 호출 됩니다

호출 된 멤버 함수는 [initonly (C++/CLI)](../../dotnet/initonly-cpp-cli.md) 데이터 멤버입니다.  C4395 경고 하는 **initonly** 함수에 의해 데이터 멤버를 수정할 수 없습니다.

다음 샘플에서는 C4395 오류가 생성 됩니다.

```
// C4395.cpp
// compile with: /W1 /clr
public value class V {
public:
   V(int data) : m_data(data) {}

   void Mutate() {
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);
      m_data *= 2;
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);
   }

   int m_data;
};

public ref class R {
public:
   static void f() {
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
      v.Mutate();   // C4395
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
   }

private:
   initonly static V v = V(4);
};

int main() {
   R::f();
}
```
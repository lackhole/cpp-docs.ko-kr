---
title: 컴파일러 경고(수준 1) C4620
ms.date: 11/04/2016
f1_keywords:
- C4620
helpviewer_keywords:
- C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
ms.openlocfilehash: d03c7d845923b918fbb665933147d8ff97cda7ab
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051460"
---
# <a name="compiler-warning-level-1-c4620"></a>컴파일러 경고(수준 1) C4620

'type' 형식에 대한 'operator ++' 후위 형식이 없으므로 전위 형식이 사용됩니다.

지정된 형식에 대해 정의된 후위 증가 연산자가 없습니다. 컴파일러가 오버로드된 전위 연산자를 사용했습니다.

이 경고는 후위 `++` 연산자를 정의하여 방지할 수 있습니다. 인수가 두 개인 버전의 `++` 연산자를 다음과 같이 만듭니다.

```cpp
// C4620.cpp
// compile with: /W1
class A
{
public:
   A(int nData) : m_nData(nData)
   {
   }

   A operator++()
   {
      m_nData -= 1;
      return *this;
   }

   // A operator++(int)
   // {
   //    A tmp = *this;
   //    m_nData -= 1;
   //    return tmp;
   // }

private:
   int m_nData;
};

int main()
{
   A a(10);
   ++a;
   a++;   // C4620
}
```
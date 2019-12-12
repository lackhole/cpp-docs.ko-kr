---
title: 컴파일러 경고(수준 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: 3ea32e8693fbe310b82eeeb87b1e97f2281ddf04
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990758"
---
# <a name="compiler-warning-level-4-c4670"></a>컴파일러 경고(수준 4) C4670

'identifier': 기본 클래스에 액세스할 수 없습니다.

**try** 블록에서 throw되는 개체의 지정된 기본 클래스에 액세스할 수 없습니다. Throw되는 경우 개체를 인스턴스화할 수 없습니다. 기본 클래스가 올바른 액세스 지정자와 함께 상속되는지 확인합니다.

다음 샘플에서는 C4670을 생성합니다.

```cpp
// C4670.cpp
// compile with: /EHsc /W4
class A
{
};

class B : /* public */ A
{
} b;   // inherits A with private access by default

int main()
{
    try
    {
       throw b;   // C4670
    }
    catch( B )
    {
    }
}
```

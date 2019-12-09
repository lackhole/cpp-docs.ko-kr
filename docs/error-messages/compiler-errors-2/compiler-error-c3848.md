---
title: 컴파일러 오류 C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 51a5cf6d866a5e5ee914a3d70365761749f79eea
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761948"
---
# <a name="compiler-error-c3848"></a>컴파일러 오류 C3848

' t r u e ' 형식의 식에서 ' function '을 호출 하기 위해 일부 const volatile 한정자가 손실 됩니다.

지정 된 const volatile 형식의 변수는 동일 하거나 더 큰 const volatile 자격으로 정의 된 멤버 함수만 호출할 수 있습니다.

다음 샘플에서는 C3848를 생성 합니다.

```cpp
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```

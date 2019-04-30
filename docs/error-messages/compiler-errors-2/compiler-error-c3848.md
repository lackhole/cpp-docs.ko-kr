---
title: 컴파일러 오류 C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 1d738311ada14999a5345a4e2394631254dda00a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381002"
---
# <a name="compiler-error-c3848"></a>컴파일러 오류 C3848

'type' 식 'function'를 호출 하기 위해 일부 const-volatile 한정자가 손실

지정된 된 const volatile 형식 사용 하 여 변수 멤버 같거나 큰 const volatile 한정자가 정의 된 함수를 호출할만 수 있습니다.

다음 샘플에서는 c3848:

```
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
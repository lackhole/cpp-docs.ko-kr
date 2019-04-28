---
title: 컴파일러 오류 C2326
ms.date: 11/04/2016
f1_keywords:
- C2326
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
ms.openlocfilehash: 36df63ce1ac5bcdb444721be3aa10f9867ae7c58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300899"
---
# <a name="compiler-error-c2326"></a>컴파일러 오류 C2326

'declarator': 함수에서 'name'에 액세스할 수 없습니다.

코드에서 멤버 변수를 수정하려고 하는데, 이는 불가능합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2326을 생성합니다.

```
// C2326.cpp
void MyFunc() {
   int i;

   class MyClass  {
   public:
      void mf() {
         i = 4;   // C2326 i is inaccessible
      }
   };
}
```
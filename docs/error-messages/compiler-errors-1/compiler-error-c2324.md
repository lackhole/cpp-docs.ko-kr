---
title: 컴파일러 오류 C2324
ms.date: 11/04/2016
f1_keywords:
- C2324
helpviewer_keywords:
- C2324
ms.assetid: 215f0544-85b0-452d-825f-17a388b6a61c
ms.openlocfilehash: 694d1b2c9df4830e721af51517044e9734fcf415
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400385"
---
# <a name="compiler-error-c2324"></a>컴파일러 오류 C2324

'identifier': 예기치 않은 'name' 오른쪽에

잘못 된 식별자를 사용 하 여 소멸자가 호출 됩니다.

다음 샘플에서는 C2324 오류가 생성 됩니다.

```
// C2324.cpp
class A {};
typedef A* pA_t;
int i;

int main() {
   pA_t * ppa = new pA_t;
   ppa->~i;   // C2324
   ppa->~pA_t();   // OK
}
```
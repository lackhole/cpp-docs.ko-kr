---
title: 컴파일러 경고(수준 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: af821d80ff8c4c7717986f2ff4d0f3392cd6fca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349726"
---
# <a name="compiler-warning-level-2-c4244"></a>컴파일러 경고(수준 2) C4244

'argument': 'type1'에서 'type2', 데이터 손실으로 변환

정수 형식으로 변환 된 부동 소수점 형식입니다.  데이터 손실이 발생했을 수 있습니다.

C4244 오류가 발생하는 경우 호환되는 형식을 사용하도록 프로그램을 변경하거나 코드에 일부 논리를 추가하여 가능한 값의 범위가 사용 중인 형식과 항상 호환되는지 확인해야 합니다.

C4244 3 및 4; 수준에서 발생할 수도 있습니다. 참조 [컴파일러 경고 (수준 3 및 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4244 오류가 발생하는 경우를 보여 줍니다.

```
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```
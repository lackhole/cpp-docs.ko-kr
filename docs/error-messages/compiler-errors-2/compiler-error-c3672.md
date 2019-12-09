---
title: 컴파일러 오류 C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: 3288f7ea0b95d141dd6b4281d7080de1409da606
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758101"
---
# <a name="compiler-error-c3672"></a>컴파일러 오류 C3672

의사 (pseudo) 소멸자 식은 함수 호출의 일부로만 사용할 수 있습니다.

소멸자를 잘못 호출 했습니다.  자세한 내용은 [소멸자](../../cpp/destructors-cpp.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3672를 생성 합니다.

```cpp
// C3672.cpp
template<typename T>
void f(T* pT) {
   &pT->T::~T;   // C3672
   pT->T::~T();   // OK
};

int main() {
   int i;
   f(&i);
}
```

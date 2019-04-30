---
title: 컴파일러 오류 C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: 36048f3e4b8cc1be3e766f11b5c131513a3365da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215006"
---
# <a name="compiler-error-c3672"></a>컴파일러 오류 C3672

함수 호출의 일부로 의사 (pseudo) 소멸자 식만 사용할 수 있습니다.

소멸자를 잘못 호출 했습니다.  자세한 내용은 [소멸자](../../cpp/destructors-cpp.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3672를 생성합니다.

```
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
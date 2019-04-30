---
title: 컴파일러 오류 C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: 296224532b19d9ff85c8644aa653b6d842205213
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265882"
---
# <a name="compiler-error-c2892"></a>컴파일러 오류 C2892

지역 클래스 멤버 템플릿을 가질 수 없습니다.

템플릿 멤버 함수는 함수에 정의 된 클래스에서 사용할 수 없습니다.

다음 샘플에서는 C2892 오류가 생성 됩니다.

```
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```
---
title: 컴파일러 오류 C2688
ms.date: 11/04/2016
f1_keywords:
- C2688
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
ms.openlocfilehash: cc871467e1e3fb23edc6231c3adb182f5e26c0d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760246"
---
# <a name="compiler-error-c2688"></a>컴파일러 오류 C2688

' C2:: fgrv ': varargs 함수에 대해 다중 또는 가상 상속이 지원 되지 않으므로 공변 (covariant)을 반환 합니다.

함수가 가변 인수를 포함 하는 경우 C++ 에는 시각적 개체에서 공변 (Covariant) 반환 형식이 지원 되지 않습니다.

이 오류를 해결 하려면 변수 인수를 사용 하거나 모든 가상 함수에 대해 반환 값을 동일 하 게 설정 하지 않도록 함수를 정의 합니다.

다음 샘플에서는 C2688를 생성 합니다.

```cpp
// C2688.cpp
struct G1 {};
struct G2 {};
struct G3 : G1, G2 {};
struct G4 {};
struct G5 {};
struct G6 : G4, G5 {};
struct G7 : G3, G6 {};

struct C1 {
   virtual G4& fgrv(int,...);
};

struct C2 : C1 {
   virtual G7& fgrv(int,...);   // C2688, does not return G4&
};
```

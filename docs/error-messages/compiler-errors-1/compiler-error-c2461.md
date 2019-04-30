---
title: 컴파일러 오류 C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: e8f82ed4ce8ad77a22961a42c8e9a256e6f647db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368034"
---
# <a name="compiler-error-c2461"></a>컴파일러 오류 C2461

> '*클래스*': 생성자 구문에 정식 매개 변수가 없음

클래스의 생성자는 정식 매개 변수를 지정 하지 않습니다. 생성자 선언에 정식 매개 변수 목록을 지정 해야 합니다. 목록은 비어 있을 수 있습니다.

이 문제를 해결 하려면 선언 뒤에 괄호 한 쌍 추가 *클래스*:: **클래스*합니다.

## <a name="example"></a>예제

다음 샘플 C2461를 해결 하는 방법을 보여 줍니다.

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```
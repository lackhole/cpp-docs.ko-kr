---
title: 컴파일러 오류 C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 3ef669a49f4a3ec5a1af1a15a79f2511fa2699dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755787"
---
# <a name="compiler-error-c2733"></a>컴파일러 오류 C2733

오버 로드 된 ' function ' 함수의 두 번째 C 링크는 허용 되지 않습니다.

C 링크를 사용 하 여 오버 로드 된 함수가 두 개 이상 선언 되었습니다. C 링크를 사용 하는 경우 지정 된 함수의 한 폼만 외부가 될 수 있습니다. 오버 로드 된 함수는 데코레이팅되지 않은 이름이 동일 하므로 C 프로그램에서 사용할 수 없습니다.

다음 샘플에서는 C2733를 생성 합니다.

```cpp
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```

---
title: C++의 선언 지점
ms.date: 11/04/2016
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
ms.openlocfilehash: d6cb4c3813d88c8b29fbcb2e0827805f406e6c81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183403"
---
# <a name="point-of-declaration-in-c"></a>C++의 선언 지점

선언자 바로 뒤, 이니셜라이저 앞(선택 사항)에서 이름이 선언된다고 간주합니다. 선언자에 대한 자세한 내용은 [선언 및 정의](declarations-and-definitions-cpp.md)를 참조하세요.

다음 예제를 고려해 보세요.

```cpp
// point_of_declaration1.cpp
// compile with: /W1
double dVar = 7.0;
int main()
{
   double dVar = dVar;   // C4700
}
```

선언 시점이 초기화 *후* 일 경우 로컬 `dVar` 이 전역 변수 `dVar`의 값인 7.0으로 초기화됩니다. 그러나 그런 경우는 아니므로 `dVar`이 정의되지 않은 값으로 초기화됩니다.

## <a name="see-also"></a>참고 항목

[범위(Visual C++)](../cpp/scope-visual-cpp.md)
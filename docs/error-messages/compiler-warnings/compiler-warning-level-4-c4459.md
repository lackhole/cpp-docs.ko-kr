---
title: 컴파일러 경고 (수준 4) C4459
ms.date: 11/04/2016
f1_keywords:
- C4459
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
ms.openlocfilehash: 0cbab7c7cca1fc88bb99210262be45c56b6be7a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391428"
---
# <a name="compiler-warning-level-4-c4459"></a>컴파일러 경고 (수준 4) C4459

> 선언의 '*식별자*' 전역 선언을 숨깁니다.

선언의 *식별자* 로컬 범위에 같은 이름의 선언을 숨깁니다 *식별자* 전역 범위에 있습니다. 이 경고를 사용 하면에 대 한 참조는 알고 *식별자* 이 범위에는 의도 하지 않을 수도 있고 전역 버전이 아니라 로컬로 선언 된 버전을 확인 합니다. 일반적으로 적절 한 엔지니어링 실무와 전역 변수의 사용을 최소화 하는 것이 좋습니다. 전역 네임 스페이스 공해를 최소화 하려면 전역 변수에 대 한 명명된 된 네임 스페이스의 사용을 좋습니다.

이 경고가 시각적 개체의 Visual Studio 2015의 새로운 기능 C++ 컴파일러 버전 18.00 합니다. 컴파일러 또는 코드를 마이그레이션하는 동안 나중에 해당 버전에서 발생 한 경고를 표시 하지 않으려면 사용 합니다 [/wv:18](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4459 오류가 생성 됩니다.

```cpp
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() {
    int global_or_local; // warning C4459
    global_or_local = 2;
}
```

이 문제를 해결 하는 한 가지 방법은 전역 네임 스페이스를 만들지만 사용 하는 것을 `using` 정규화 된 이름을 지시문을 가져와서 해당 네임 스페이스 범위에 대 한 모든 참조는 모호 하지 않은 사용 해야 합니다.

```cpp
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() {
    int global_or_local; // OK
    global_or_local = 2;
    globals::global_or_local = 3;
}
```

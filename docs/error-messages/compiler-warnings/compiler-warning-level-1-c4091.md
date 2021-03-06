---
title: 컴파일러 경고 (수준 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: ce6dd980ef70f129a0dbae474b8f717f7573f861
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626748"
---
# <a name="compiler-warning-level-1-c4091"></a>컴파일러 경고 (수준 1) C4091

' keyword ': 변수가 선언 되지 않은 경우 ' t r u e '의 왼쪽에는 무시 됩니다.

컴파일러에서 사용자가 변수를 선언 했지만 컴파일러가 변수를 선언할 수 없는 경우를 발견 했습니다.

## <a name="example"></a>예제

사용자 정의 형식 선언의 시작 부분에 있는 `__declspec` 특성은 해당 형식의 변수에 적용 됩니다. C4091는 변수가 선언 되지 않았음을 나타냅니다. 다음 샘플에서는 C4091를 생성 합니다.

```cpp
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>예제

식별자가 typedef 인 경우 변수 이름일 수도 없습니다. 다음 샘플에서는 C4091를 생성 합니다.

```cpp
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```
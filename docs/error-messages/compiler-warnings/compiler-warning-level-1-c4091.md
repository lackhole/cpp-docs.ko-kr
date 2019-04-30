---
title: 컴파일러 경고 (수준 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 87432a74dfe7c09a52f436d4e91b3f70eb66856b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410449"
---
# <a name="compiler-warning-level-1-c4091"></a>컴파일러 경고 (수준 1) C4091

'keyword': 변수가 없으면 선언 되 면 왼쪽 'type'은 무시 됩니다

컴파일러는 사용자를 선언 하는 변수를 위한 것 하지만 컴파일러에서 변수를 선언할 수 없습니다 경우를 발견 했습니다.

## <a name="example"></a>예제

`__declspec` 특성을 사용자 정의 형식 선언의 시작 부분에서 해당 형식의 변수에 적용 됩니다. C4091 선언 된 변수가 없음을 나타냅니다. 다음 샘플 C4091를 생성합니다.

```
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

식별자 형식 정의 인 경우 변수 이름을 수도 없습니다. 다음 샘플 C4091를 생성합니다.

```
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```
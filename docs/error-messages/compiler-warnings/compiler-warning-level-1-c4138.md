---
title: 컴파일러 경고(수준 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: e6e368f27371b744efa4006630938f68f51a2ca0
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627104"
---
# <a name="compiler-warning-level-1-c4138"></a>컴파일러 경고(수준 1) C4138

'*/'가 주석 외부에 있습니다.

닫는 주석 구분 기호 앞에 여는 주석 구분 기호가 없습니다. 컴파일러는 별표(<strong>\*</strong>)와 슬래시(/) 사이에 공백이 있다고 가정합니다.

## <a name="example"></a>예제

```cpp
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

이 경고는 주석을 중첩하려는 경우에 발생할 수 있습니다.

주석을 포함하는 코드 섹션을 주석으로 처리하고 **#if/#endif** 블록에 코드를 포함한 다음 제어하는 식을 0으로 설정하면 이 경고를 해결할 수 있습니다.

```cpp
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```
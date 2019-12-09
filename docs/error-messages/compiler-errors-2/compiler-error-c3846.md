---
title: 컴파일러 오류 C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: a4c51ccfc724cf8309044812b287677f0f1a2ff0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754903"
---
# <a name="compiler-error-c3846"></a>컴파일러 오류 C3846

' symbol ': ' assembly2 '에서 기호를 가져올 수 없습니다. 다른 어셈블리 ' assembly1 '에서 ' 기호 '를 이미 가져왔습니다.

이전에 참조 된 어셈블리에서 가져온 것 이므로 참조 된 어셈블리에서 기호를 가져올 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3846를 생성 합니다.

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

그리고 다음을 컴파일합니다.

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```

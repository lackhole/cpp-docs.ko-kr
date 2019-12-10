---
title: 컴파일러 오류 C3121
ms.date: 11/04/2016
f1_keywords:
- C3121
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
ms.openlocfilehash: e5d5f85631dbbedcabce89c25d9af7a7a685342c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740925"
---
# <a name="compiler-error-c3121"></a>컴파일러 오류 C3121

' class_name ' 클래스의 GUID를 변경할 수 없습니다.

[__Declspec (uuid)](../../cpp/uuid-cpp.md)를 사용 하 여 클래스 ID를 변경 하려고 했습니다.

예를 들어 다음 코드는 C3121을 생성 합니다.

```cpp
// C3121.cpp
[emitidl];
[module(name="MyLibrary")];

[coclass, uuid="00000000-0000-0000-0000-111111111111"]
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121
{
};
int main()
{
}
```

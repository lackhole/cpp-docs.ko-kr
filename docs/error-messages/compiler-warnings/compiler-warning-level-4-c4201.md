---
title: 컴파일러 경고(수준 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: 1f029d7717f99e55a977ad9cb80dacbfa1485086
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541209"
---
# <a name="compiler-warning-level-4-c4201"></a>컴파일러 경고(수준 4) C4201

비표준 확장이 사용 됨: 이름이 없는 구조체/공용 구조체입니다.

Microsoft 확장 (/Ze)에서 선언 자가 없는 구조체를 다른 구조체 또는 공용 구조체의 멤버로 지정할 수 있습니다. 이러한 구조체는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 오류를 생성 합니다.

## <a name="example"></a>예제

```cpp
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```
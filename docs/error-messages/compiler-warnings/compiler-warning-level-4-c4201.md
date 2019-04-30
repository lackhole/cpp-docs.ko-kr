---
title: 컴파일러 경고(수준 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: c7c10273e06ec35528dbd9d51c02bb844d275638
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401256"
---
# <a name="compiler-warning-level-4-c4201"></a>컴파일러 경고(수준 4) C4201

비표준 확장이 사용 됨: 이름이 없는 구조체/공용 구조체

Microsoft 확장 (/Ze)에서는 다른 구조체 또는 공용 구조체의 멤버로 선언 자 없이 구조체를 지정할 수 있습니다. 이러한 구조는 ANSI 호환성 오류를 생성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>예제

```
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
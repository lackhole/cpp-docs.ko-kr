---
title: 컴파일러 경고(수준 4) C4324
ms.date: 11/04/2016
f1_keywords:
- C4324
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
ms.openlocfilehash: 696f53dff6398555355ca3a58e25d2c6d64eaaab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400866"
---
# <a name="compiler-warning-level-4-c4324"></a>컴파일러 경고(수준 4) C4324

'struct_name': __declspec(align()) 때문에 구조체가 채워졌습니다

안쪽 여백을 지정 했기 때문에 구조체의 끝에 추가 된를 [__declspec (align)](../../cpp/align-cpp.md) 값입니다.

예를 들어, 다음 코드에서는 C4324를 생성합니다.

```
// C4324.cpp
// compile with: /W4
struct __declspec(align(32)) A
{
   char a;
};   // C4324

int main()
{
}
```
---
title: 컴파일러 오류 C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 34287b785532394d33e94e37e7a6a9955d935f14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360198"
---
# <a name="compiler-error-c2691"></a>컴파일러 오류 C2691

'data type': WinRTarray 또는 관리 되는이 요소 형식을 사용할 수 없습니다.

관리되는 배열 또는 WinRT 배열의 요소 형식은 값 형식이나 참조 형식일 수 있습니다.

다음 샘플에서는 C2691 오류가 발생하는 경우를 보여 줍니다.

```
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```

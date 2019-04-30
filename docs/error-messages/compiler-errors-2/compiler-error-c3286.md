---
title: 컴파일러 오류 C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 8c09ea34c7dabf2cadecad7c76d766c9496f5a5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381359"
---
# <a name="compiler-error-c3286"></a>컴파일러 오류 C3286

> '*지정자*': 반복 변수에 저장소 클래스 지정자를 사용할 수 없습니다

저장소 클래스에 반복 변수를 지정할 수 없습니다. 자세한 내용은 참조 하세요. [저장소 클래스 (C++)](../../cpp/storage-classes-cpp.md) 하 고 [각각의](../../dotnet/for-each-in.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3286을 생성 하 고 또한 올바른 사용법을 보여 줍니다.

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```
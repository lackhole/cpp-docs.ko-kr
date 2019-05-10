---
title: 컴파일러 오류 C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: d635601fbf8b36218fb47c09444f3f5d023c823e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383089"
---
# <a name="compiler-error-c2719"></a>컴파일러 오류 C2719

'parameter': __declspec(align('#'))를 사용하는 정식 매개 변수는 정렬되지 않습니다.

합니다 [맞춤](../../cpp/align-cpp.md) `__declspec` 한정자 함수 매개 변수에서 허용 되지 않습니다. 함수 매개 변수 맞춤은 사용되는 호출 규칙에 의해 제어됩니다. 자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md)합니다.

다음 샘플에서는 C2719 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
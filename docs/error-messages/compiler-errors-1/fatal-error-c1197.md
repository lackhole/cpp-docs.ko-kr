---
title: 심각한 오류 C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: 7f698262c73f0b311a92a8940107b552430919bb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747243"
---
# <a name="fatal-error-c1197"></a>심각한 오류 C1197

프로그램이 이미 ' mscorlib.dll. dll_2 '을 참조 했으므로 ' mscorlib. dll_1 '를 참조할 수 없습니다.

컴파일러는 공용 언어 런타임 버전과 일치 합니다.  그러나 이전 버전에서 공용 언어 런타임 파일의 버전을 참조 하려고 했습니다.

이 오류를 해결 하려면 컴파일하는 시각적 개체 C++ 버전과 함께 제공 되는 공용 언어 런타임 버전의 파일만 참조 하십시오.

## <a name="example"></a>예제

다음 샘플에서는 C1197를 생성 합니다.

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```

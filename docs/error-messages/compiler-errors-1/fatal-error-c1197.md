---
title: 심각한 오류 C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: e1c00a001c807b0cc6a5946b61ca4e9d5dc0167a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229124"
---
# <a name="fatal-error-c1197"></a>심각한 오류 C1197

프로그램에 이미 'mscorlib.dll_2'를 참조 하는 대로 'mscorlib.dll_1'를 참조할 수 없습니다.

컴파일러는 공용 언어 런타임의 버전으로 일치 됩니다.  그러나 시도가 이전 버전에서 공용 언어 런타임 파일의 버전을 참조 하려고 합니다.

이 오류를 해결 하려면만 참조 파일 시각적 개체의 버전과 함께 제공 되는 공용 언어 런타임의 버전에서 C++ 사용 하 여 컴파일하고 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C1197 오류가 생성 됩니다.

```
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
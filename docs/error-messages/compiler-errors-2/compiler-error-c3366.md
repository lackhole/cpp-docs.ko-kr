---
title: 컴파일러 오류 C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 4d1cd510cda9957ced1d9dd5fd8fea267f39220d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300559"
---
# <a name="compiler-error-c3366"></a>컴파일러 오류 C3366

'variable': 관리 되는 정적 데이터 멤버 또는 WinRTtypes 클래스 정의 내에서 정의 해야 합니다

WinRT 또는 .NET 클래스 또는 인터페이스의 정적 멤버를 해당 클래스 또는 인터페이스의 정의 외부에서 참조하려고 했습니다.

컴파일러는 한 번 통과한 후 메타데이터를 내보내기 위해 클래스의 전체 정의를 알아야 하며 클래스 내에서 정적 데이터 멤버가 초기화되어야 합니다.

예를 들어 다음 예제에서는 C3366 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```

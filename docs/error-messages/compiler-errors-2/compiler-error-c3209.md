---
title: 컴파일러 오류 C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: f907d0605cccf0a36abd1361d8c87a783bb81506
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243247"
---
# <a name="compiler-error-c3209"></a>컴파일러 오류 C3209

'class': 제네릭 클래스는 관리 되는 또는 WinRTclass 해야 합니다.

제네릭 클래스는 관리되는 클래스 또는 Windows 런타임 클래스여야 합니다.

다음 샘플에서는 C3209를 생성하고 해결 방법을 보여 줍니다.

```
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```
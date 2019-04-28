---
title: 컴파일러 오류 C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: bd783d9510b1699b33f108a4ce8d8c491028b758
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328707"
---
# <a name="compiler-error-c3387"></a>컴파일러 오류 C3387

'member': __declspec (dllexport) /\__declspec(dllimport) 멤버 관리 되는 또는 WinRT 형식에 적용할 수 없습니다

`dllimport` 하 고 [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` 한정자 관리 되는 멤버 또는 Windows 런타임 형식에서 유효 하지 않습니다.

다음 샘플에서는 C3387 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```
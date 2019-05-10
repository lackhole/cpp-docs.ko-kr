---
title: 컴파일러 오류 C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: a9183e1f62e7ebaf5db04a35a45806ec02169e69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328811"
---
# <a name="compiler-error-c3386"></a>컴파일러 오류 C3386

'type': __declspec (dllexport) /\__declspec(dllimport) 관리 되는 또는 WinRTtype에 적용할 수 없습니다

합니다 `dllimport` 하 고 [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` 한정자 Windows 런타임 또는 관리 되는 유효 하지 않습니다. 형식입니다.

다음 샘플에서는 C3386 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
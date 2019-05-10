---
title: 컴파일러 경고(수준 1) C4616
ms.date: 11/04/2016
f1_keywords:
- C4616
helpviewer_keywords:
- C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
ms.openlocfilehash: d63e1abffce617a48ac1a5cd8c61feba941b31ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221360"
---
# <a name="compiler-warning-level-1-c4616"></a>컴파일러 경고(수준 1) C4616

\#pragma 경고: 경고 번호 '번호' 올바른 컴파일러 경고가 아니라

에 지정 된 경고 번호를 [경고](../../preprocessor/warning.md) pragma를 다시 할당할 수 없습니다. Pragma가 무시 되었습니다.

다음 샘플에서는 C4616 오류가 생성 됩니다.

```
// C4616.cpp
// compile with: /W1 /c
#pragma warning( disable : 0 )   // C4616
#pragma warning( disable : 999 )   // OK
#pragma warning( disable : 4998 )   // OK
```
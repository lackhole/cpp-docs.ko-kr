---
title: 컴파일러 오류 C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: 746f01706c7c0ec09a64c5faee748f9582ac9a14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367761"
---
# <a name="compiler-error-c2633"></a>컴파일러 오류 C2633

'identifier': 'inline'는 생성자에 맞는 유일한 저장소 클래스

생성자는 인라인 이외의 저장소 클래스로 선언 됩니다.

다음 샘플에서는 C2633 오류가 생성 됩니다.

```
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```
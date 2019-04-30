---
title: 컴파일러 오류 C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: d320f78937fc60910bbed4a5b1b89841ea674fb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303517"
---
# <a name="compiler-error-c2396"></a>컴파일러 오류 C2396

'your_type::operator'type'' : CLR 또는 WinRT 사용자 정의 변환 functionnot 유효 합니다. 변환 하거나 변환 합니다. ' T ^', ' T ^ %', ' T ^ &', 여기서 T = 'your_type'

Windows 런타임 또는 관리되는 형식의 변환 함수에 해당 형식이 변환 함수를 포함하는 형식과 동일한 매개 변수가 하나 이상 없습니다.

다음 샘플에서는 C2396을 생성하고 해결 방법을 보여 줍니다.

```
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```
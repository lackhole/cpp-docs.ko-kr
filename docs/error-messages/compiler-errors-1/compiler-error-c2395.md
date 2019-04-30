---
title: 컴파일러 오류 C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303664"
---
# <a name="compiler-error-c2395"></a>컴파일러 오류 C2395

'your_type::operator'op'' : 유효 하지 않은 CLR 또는 WinRT 연산자입니다. 하나 이상의 매개 변수가 다음 형식 이어야 합니다. ' T '를 ' T %', ' T &', ' T ^', ' T ^ %', ' T ^ &', 여기서 T = 'your_type'

Windows 런타임 또는 관리되는 형식의 연산자는 형식이 연산자 반환 값의 형식과 동일한 매개 변수를 하나 이상 사용할 수 없습니다.

다음 샘플에서는 C2395를 생성하고 해결 방법을 보여 줍니다.

```
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```
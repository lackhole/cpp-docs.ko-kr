---
title: 컴파일러 오류 C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 8f428699aa14cbd1f021a57ed8dcabefa8b24c16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165088"
---
# <a name="compiler-error-c2504"></a>컴파일러 오류 C2504

'class' : base class undefined

기본 클래스 선언 되었지만 정의 되지 않습니다.  가능한 원인:

1. 포함 파일이 없습니다.

1. 선언 되지 외부 기본 클래스 [extern](../../cpp/using-extern-to-specify-linkage.md)합니다.

다음 샘플에서는 C2504 오류가 생성 됩니다.

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

그래

```
class C{};
class D : public C {};
```
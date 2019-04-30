---
title: 컴파일러 오류 C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: 447869b029df41219f71dcc633e9ae8a3934e0ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408487"
---
# <a name="compiler-error-c2570"></a>컴파일러 오류 C2570

'identifier': 공용 구조체는 기본 클래스를 사용할 수 없습니다.

공용 구조체는 클래스, 구조체 또는 공용 구조체에서 파생 됩니다. 이것은 허용되지 않습니다. 대신 파생된 된 형식으로 클래스 또는 구조체 선언 합니다.

다음 샘플에서는 C2570 오류가 생성 됩니다.

```
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
---
title: 컴파일러 오류 C3050
ms.date: 11/04/2016
f1_keywords:
- C3050
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
ms.openlocfilehash: 255647a2e603b5a71855374dba3248ffef1e025e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187476"
---
# <a name="compiler-error-c3050"></a>컴파일러 오류 C3050

'type1': ref 클래스는 'type1'에서 상속될 수 없습니다.

`System::ValueType` 이 참조 형식에 대한 기본 클래스가 될 수 없습니다.

다음 샘플에서는 C3050을 생성합니다.

```
// C3050.cpp
// compile with: /clr /LD
ref struct X : System::ValueType {};   // C3050
ref struct Y {};   // OK
```
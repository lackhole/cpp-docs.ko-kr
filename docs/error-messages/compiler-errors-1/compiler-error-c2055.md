---
title: 컴파일러 오류 C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 3c198168b4445e619148e5611621fa3ddba95d6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408789"
---
# <a name="compiler-error-c2055"></a>컴파일러 오류 C2055

형식 목록이 아니라 정식 매개 변수 목록이 필요합니다.

함수 정의는 정식 매개 변수 목록 대신 매개 변수 유형 목록을 포함합니다. ANSI C void 또는 줄임표가 않은 이름을 지정 하는 정식 매개 변수를 사용 하려면 (`...`).

다음 샘플에서는 C2055 오류가 생성 됩니다.

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```
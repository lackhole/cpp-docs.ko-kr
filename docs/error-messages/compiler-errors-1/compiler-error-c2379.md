---
title: 컴파일러 오류 C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 1b3256efb6c0ff8236ba80a9ac681780f34fa8dd
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345643"
---
# <a name="compiler-error-c2379"></a>컴파일러 오류 C2379

정식 매개 변수 번호의 형식이 다릅니다.

지정 된 매개 변수 형식의 이전 선언에서 형식 사용 하 여 기본 프로 모션을 통해 호환 되지 않습니다. 이것은 ANSI C에서 오류 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) 및 Microsoft 확장을 사용 하 여 경고 (**/Ze**).

다음 샘플에서는 C2379를 생성합니다.

```
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
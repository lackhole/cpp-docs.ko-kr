---
title: 컴파일러 오류 C2192
ms.date: 11/04/2016
f1_keywords:
- C2192
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
ms.openlocfilehash: 3285221089c2a1ed61b03572ed8915ebfbb00e48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303010"
---
# <a name="compiler-error-c2192"></a>컴파일러 오류 C2192

매개 변수 'number' 선언이 다릅니다.

C 함수에는 다른 매개 변수 목록 사용 하 여 두 번 선언 되었습니다. C에서 오버 로드 된 함수를 지원 하지 않습니다.

다음 샘플에서는 C2192 오류가 생성 됩니다.

```
// C2192.c
// compile with: /Za /c
void func( float, int );
void func( int, float );   // C2192, different parameter list
void func2( int, float );   // OK
```
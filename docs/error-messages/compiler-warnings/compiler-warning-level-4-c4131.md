---
title: 컴파일러 경고(수준 4) C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: 266d62126d9154cd87706d3124e69e107bbdefde
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541584"
---
# <a name="compiler-warning-level-4-c4131"></a>컴파일러 경고(수준 4) C4131

'function': 이전 스타일의 선언자를 사용합니다.

지정된 함수 선언은 프로토타입 형식이 아닙니다.

이전 스타일 함수 선언을 프로토타입 형식으로 변환해야 합니다.

다음 예제에는 이전 스타일 함수 선언을 보여 줍니다.

```c
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

다음 예제에서는 프로토타입 형식을 보여 줍니다.

```c
void addrec( char *name, int id )
{ }
```
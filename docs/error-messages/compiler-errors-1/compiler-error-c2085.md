---
title: 컴파일러 오류 C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 7dbf7266a6330a1fdb46d7f2df90e7684f026d9a
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301966"
---
# <a name="compiler-error-c2085"></a>컴파일러 오류 C2085

' identifier ': 정식 매개 변수 목록에 없습니다.

식별자가 함수 정의에서 선언 되었지만 형식 매개 변수 목록에는 선언 되지 않았습니다. (ANSI C만 해당)

다음 샘플에서는 C2085를 생성 합니다.

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

가능한 해결 방법:

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

세미콜론이 누락 된 `func1()`은 프로토타입이 아닌 함수 정의 처럼 보이지만, `func1()`내에서 `main` 정의 되어 식별자 `main`에 대 한 오류 C2085 생성 됩니다.

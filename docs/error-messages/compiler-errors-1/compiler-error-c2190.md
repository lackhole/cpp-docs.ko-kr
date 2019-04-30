---
title: 컴파일러 오류 C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: b52797b945b1a652506b4a85171e60a91544bbf0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282831"
---
# <a name="compiler-error-c2190"></a>컴파일러 오류 C2190

첫 번째 매개 변수 목록이 둘째 보다 깁니다.

C 함수를 한 번 더 짧은 매개 변수 목록 사용 하 여 선언 되었습니다. C에서 오버 로드 된 함수를 지원 하지 않습니다.

다음 샘플에서는 C2190를 생성합니다.

```
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```
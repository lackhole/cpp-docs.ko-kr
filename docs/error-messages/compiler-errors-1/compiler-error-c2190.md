---
title: 컴파일러 오류 C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: 027c7f49b361ef3aa06a4d74e10f0ff27331b4a9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301888"
---
# <a name="compiler-error-c2190"></a>컴파일러 오류 C2190

첫 번째 매개 변수 목록이 두 번째 보다 깁니다.

C 함수가 더 짧은 매개 변수 목록을 사용 하 여 두 번 선언 되었습니다. C는 오버 로드 된 함수를 지원 하지 않습니다.

다음 샘플에서는 C2190를 생성 합니다.

```c
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```

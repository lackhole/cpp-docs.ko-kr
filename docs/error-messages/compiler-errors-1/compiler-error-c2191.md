---
title: 컴파일러 오류 C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: 23dfe1d95ab75f253fc2a7b4b00dfcd1aaaa3bbf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302972"
---
# <a name="compiler-error-c2191"></a>컴파일러 오류 C2191

두 번째 매개 변수 목록이 첫째 보다 깁니다.

C 함수 매개 변수 목록 사용 하 여 두 번 선언 되었습니다. C에서 오버 로드 된 함수를 지원 하지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2191 오류가 생성 됩니다.

```
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```
---
title: 컴파일러 오류 C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: 66b7d70b9010855ada7b9d24fba80915450a685b
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301875"
---
# <a name="compiler-error-c2191"></a>컴파일러 오류 C2191

둘째 매개 변수 목록이 첫째 보다 깁니다.

C 함수가 더 긴 매개 변수 목록을 사용 하 여 두 번 선언 되었습니다. C는 오버 로드 된 함수를 지원 하지 않습니다.

## <a name="example"></a>예

다음 샘플에서는 C2191를 생성 합니다.

```c
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```

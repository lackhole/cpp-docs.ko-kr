---
title: 컴파일러 오류 C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: 8c92a49499a18c12807f97cb97b24cc3beaf700b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174109"
---
# <a name="compiler-error-c3176"></a>컴파일러 오류 C3176

'type': 지역 값 형식을 선언할 수 없습니다.

클래스는 전역 범위에서 값 형식으로 선언할 수만 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3176 오류가 발생 합니다.

```
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```
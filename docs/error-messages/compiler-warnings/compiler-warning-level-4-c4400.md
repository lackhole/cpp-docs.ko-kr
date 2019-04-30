---
title: 컴파일러 경고(수준 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: 61a6d3090355c9bda8aa11c041b302e4ec77ec8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391545"
---
# <a name="compiler-warning-level-4-c4400"></a>컴파일러 경고(수준 4) C4400

'type':이 형식에서 const/volatile 한정자는 지원 되지 않습니다

합니다 [const](../../cpp/const-cpp.md)하 고 [volatile](../../cpp/volatile-cpp.md)한정자가 공용 언어 런타임 형식의 변수를 사용 하 여 작동 하지 것입니다.

## <a name="example"></a>예제

다음 샘플 C4400를 생성합니다.

```
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```
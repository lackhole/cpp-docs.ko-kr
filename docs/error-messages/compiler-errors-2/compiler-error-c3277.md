---
title: 컴파일러 오류 C3277
ms.date: 11/04/2016
f1_keywords:
- C3277
helpviewer_keywords:
- C3277
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
ms.openlocfilehash: e49de69354d00babf8c6fa609e92153e88bf64c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382114"
---
# <a name="compiler-error-c3277"></a>컴파일러 오류 C3277

관리 되지 않는 열거형 'enum' 관리 되는 'type' 내부에 정의할 수 없습니다.

관리 되는 형식 내에서 열거형 잘못 정의 되었습니다.

다음 샘플에서는 C3277 오류가 생성 됩니다.

```
// C3277a.cpp
// compile with: /clr
ref class A
{
   enum E {e1,e2};   // C3277
   // try the following line instead
   // enum class E {e1,e2};
};

int main()
{
}
```

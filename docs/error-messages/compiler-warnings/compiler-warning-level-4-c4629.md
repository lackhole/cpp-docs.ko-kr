---
title: 컴파일러 경고(수준 4) C4629
ms.date: 11/04/2016
f1_keywords:
- C4629
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
ms.openlocfilehash: db3f4201dbf5ff925449b0924d08a43ee4283b3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408045"
---
# <a name="compiler-warning-level-4-c4629"></a>컴파일러 경고(수준 4) C4629

digraph가 사용되었습니다. 문자 시퀀스 'digraph'는 토큰 'char'로 해석됩니다. 이렇게 해석하려는 경우가 아니라면 두 문자 사이에 공백을 넣으세요.

컴파일러에서 digraph를 발견한 경우 [/Za](../../build/reference/za-ze-disable-language-extensions.md)아래에 경고가 표시됩니다.

다음 샘플에서는 C4629를 생성합니다.

```
// C4629.cpp
// compile with: /Za /W4
int main()
<%   // C4629 <% digraph for {
}
```
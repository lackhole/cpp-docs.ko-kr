---
title: 컴파일러 경고(수준 4) C4255
ms.date: 11/04/2016
f1_keywords:
- C4255
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
ms.openlocfilehash: 1796e28e88bbe52c4c21ffdf0a8a96a278a44388
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400970"
---
# <a name="compiler-warning-level-4-c4255"></a>컴파일러 경고(수준 4) C4255

'function': 함수 프로토타입을 입력 하지 않았습니다. '()'에서 '(void)'로 변환

컴파일러는 명시적인 함수에 대 한 인수 목록을 찾을 수 없습니다. 이 경고는 C 컴파일러만 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4255를 생성합니다.

```
// C4255.c
// compile with: /W4 /WX
#pragma warning (default : 4255)

void f()  { // C4255
// try the following line instead
//void f(void) {
}

int main(int argc, char *argv[]) {
   f();
}
```
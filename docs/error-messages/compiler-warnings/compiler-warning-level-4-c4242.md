---
title: 컴파일러 경고(수준 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: e0582f3dfdd223b4571e361dc69fae1990aeea1c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401009"
---
# <a name="compiler-warning-level-4-c4242"></a>컴파일러 경고(수준 4) C4242

'identifier': 'type1'에서 'type2', 데이터 손실으로 변환

형식이 서로 다릅니다. 형식 변환의 데이터가 손실에서 될 수 있습니다. 컴파일러에서 형식 변환 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

C4242에 대 한 자세한 내용은 참조 하세요. [일반적인 컴파일러 오류](/windows/desktop/WinProg64/common-compiler-errors)합니다.

다음 샘플에서는 C4242 경고가 생성 됩니다.

```
// C4242.cpp
// compile with: /W4
#pragma warning(4:4242)
int func() {
   return 0;
}

int main() {
   char a;
   a = func();   // C4242, return type and variable type do not match
}
```
---
title: 컴파일러 경고(수준 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: ebb71155774ce32d6b4fc2b9920fdd31dd466841
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221208"
---
# <a name="compiler-warning-level-1-c4628"></a>컴파일러 경고(수준 1) C4628

-Ze에는 digraph가 지원되지 않습니다. 문자 시퀀스 'digraph'은(는) 'char'에 대한 대체 토큰으로 해석되지 않습니다.

아래에 digraph가 지원 되지 않습니다 [/Ze](../../build/reference/za-ze-disable-language-extensions.md)합니다. 이 경고 뒤에 오류가 발생 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4628 오류가 생성 됩니다.

```
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```
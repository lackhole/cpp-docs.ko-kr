---
title: 복합 문(블록)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 6aef2a0b5716ab501fabe80f0dda15080abe3ff5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154866"
---
# <a name="compound-statements-blocks"></a>복합 문(블록)

복합문은 중괄호(**{}**)로 묶인 0개 또는 그 이상의 문으로 이루어져 있습니다. 복합문은 문을 사용할 수 있는 곳이라면 어느 곳에서든 사용할 수 있습니다. 복합 문은 일반적으로 "블록"이라고 합니다.

## <a name="syntax"></a>구문

```
{ [ statement-list ] }
```

## <a name="remarks"></a>설명

다음 예제에서는 **if** 문의 부분 *문*으로서의 복합문을 보여줍니다. ([if-else 문](../cpp/if-else-statement-cpp.md)에 대한 문법을 참조합니다.)

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
>  선언은 문입니다. 선언은 *문 목록의* 문중 하나가 될 수 있습니다. 결과적으로, 정적으로 선언되어 있지 않은 복합문 내에서 선언된 이름은 로컬 범위와 개체 수명을 갖습니다. 로컬 범위를 사용한 이름 처리에 대한 자세한 내용은 [범위](../cpp/scope-visual-cpp.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[C++ 문 개요](../cpp/overview-of-cpp-statements.md)
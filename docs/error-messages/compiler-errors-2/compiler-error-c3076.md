---
title: 컴파일러 오류 C3076
ms.date: 11/04/2016
f1_keywords:
- C3076
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
ms.openlocfilehash: ac9afdfc11a13dd667b06289c73332593a4d884e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406654"
---
# <a name="compiler-error-c3076"></a>컴파일러 오류 C3076

'instance': 'type', 참조 형식의 인스턴스를 네이티브 형식에 포함할 수 없습니다

네이티브 형식은 CLR 형식의 인스턴스를 포함할 수 없습니다.

자세한 내용은 [ C++ 참조 형식에 대 한 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3076를 생성합니다.

```
// C3076.cpp
// compile with: /clr /c
ref struct U {};

struct V {
   U y;   // C3076
};

ref struct W {
   U y;   // OK
};
```
---
title: 컴파일러 오류 C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: 3465c3275783a625c172b711e9c41789b6f36713
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770229"
---
# <a name="compiler-error-c2959"></a>컴파일러 오류 C2959

제네릭 클래스 또는 함수 템플릿의 구성원이 아닐 수 있습니다.

자세한 내용은 [Windows 런타임 및 관리 템플릿](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) 하 고 [제네릭](../../extensions/generics-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C2959를 생성합니다.

```
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```
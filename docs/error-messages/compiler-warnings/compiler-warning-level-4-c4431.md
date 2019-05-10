---
title: 컴파일러 경고(수준 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 6a07a9ffa938d9372ebed9676847b3274115d526
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447015"
---
# <a name="compiler-warning-level-4-c4431"></a>컴파일러 경고(수준 4) C4431

형식 지정자가 없습니다. int로 가정합니다. 참고: C 기본 int를 더 이상 지원

이 오류는 Visual Studio 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다. Visual C++ 더 이상 기본적으로 int로 형식화 되지 않은 식별자를 만듭니다. 식별자의 형식은 명시적으로 지정 되어야 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

## <a name="example"></a>예제

다음 샘플 C4431를 생성합니다.

```
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```
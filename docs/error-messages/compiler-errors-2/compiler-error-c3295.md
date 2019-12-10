---
title: 컴파일러 오류 C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 4ee79e87085b0b939a762fec4c576c393846c2ae
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756866"
---
# <a name="compiler-error-c3295"></a>컴파일러 오류 C3295

'#pragma pragma'는 전역 또는 네임스페이스 범위에서만 사용할 수 있습니다.

일부 pragma는 함수에 사용할 수 없습니다.  자세한 내용은 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3295를 생성합니다.

```cpp
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```

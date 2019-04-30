---
title: 컴파일러 오류 C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: eca598233dbe4cae4730e952b45945653ec8ffaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363637"
---
# <a name="compiler-error-c3363"></a>컴파일러 오류 C3363

'type': 'typeid'는 형식에만 적용될 수 있습니다.

[typeid](../../extensions/typeid-cpp-component-extensions.md) 연산자를 잘못 사용했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3363을 생성합니다.

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```
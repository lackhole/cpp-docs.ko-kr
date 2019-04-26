---
title: 컴파일러 오류 C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: 5ef39e4580601dd90b5695d9115902bb5b834409
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174707"
---
# <a name="compiler-error-c3170"></a>컴파일러 오류 C3170

프로젝트에서 다른 모듈 식별자를 사용할 수 없습니다.

[모듈](../../windows/module-cpp.md) 특성 이름이 서로 다른 두 개의 컴파일에서 파일에서 찾을 수 없습니다. 하나의 고유한 `module` 컴파일 작업당 특성을 지정할 수 있습니다.

동일한 `module` 둘 이상의 소스 코드 파일에서 특성을 지정할 수 있습니다.

예를 들어 다음 모듈 특성을 찾을 수 없습니다.

```
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

그리고

```
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

다르다는 C3170 (여러 이름을 참고).
---
title: 컴파일러 오류 C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 1da2676d660d23e3fb71b56263779b1f1edacbf9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761740"
---
# <a name="compiler-error-c3172"></a>컴파일러 오류 C3172

' module_name ': 프로젝트에서 다른 idl_module 특성을 지정할 수 없습니다.

컴파일할 때 두 파일 중에서 이름이 같지만 `dllname` 또는 `version` 매개 변수를 사용 하는 [idl_module](../../windows/idl-module.md) 특성이 있습니다. 컴파일 당 고유한 `idl_module` 특성을 하나만 지정할 수 있습니다.

둘 이상의 소스 코드 파일에 동일한 `idl_module` 특성을 지정할 수 있습니다.

예를 들어 다음 `idl_module` 특성을 찾은 경우

```cpp
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

그리고

```cpp
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

컴파일러는 C3172를 생성 합니다 (다른 버전 값에 유의).

---
title: 컴파일러 오류 C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 5c9c1561b63c740b9f7f5d85b2bf3e04de2542c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175188"
---
# <a name="compiler-error-c3172"></a>컴파일러 오류 C3172

'module_name': 프로젝트에 다른 idl_module 특성을 지정할 수 없습니다

[idl_module](../../windows/idl-module.md) 같은 특성 이름을 다르게 `dllname` 또는 `version` 컴파일할에서 파일의 두 매개 변수를 찾았습니다. 하나의 고유한 `idl_module` 컴파일 작업당 특성을 지정할 수 있습니다.

동일한 `idl_module` 둘 이상의 소스 코드 파일에서 특성을 지정할 수 있습니다.

예를 들어 경우 다음 `idl_module` 특성이 발견 되었습니다.

```
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

그리고

```
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

다르다는 C3172 (다른 버전 값 참고).
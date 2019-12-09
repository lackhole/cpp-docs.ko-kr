---
title: 컴파일러 오류 C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 247aba1b4dfe6b6d6db1e2b8f46f2aa08abf1a79
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739989"
---
# <a name="compiler-error-c2778"></a>컴파일러 오류 C2778

__declspec (uuid ())에 잘못 된 형식의 GUID가 있습니다.

[Uuid](../../cpp/uuid-cpp.md) 확장 특성에 잘못 된 GUID가 제공 되었습니다.

GUID는 다음 형식의 16 진수 문자열 이어야 합니다.

```cpp
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

`uuid` 확장 특성은 중괄호 구분 기호를 사용 하거나 사용 하지 않고 [Clsidfromstring](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)에서 인식 하는 문자열을 허용 합니다.

다음 샘플에서는 C2778를 생성 합니다.

```cpp
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```

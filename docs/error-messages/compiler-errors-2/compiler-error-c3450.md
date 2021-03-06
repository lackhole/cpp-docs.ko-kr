---
title: 컴파일러 오류 C3450
ms.date: 11/04/2016
f1_keywords:
- C3450
helpviewer_keywords:
- C3450
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
ms.openlocfilehash: 7b57b67e8f4542266818ad5b3d90d78a1a943d55
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756229"
---
# <a name="compiler-error-c3450"></a>컴파일러 오류 C3450

'type': 특성이 아닙니다. [System::AttributeUsageAttribute] 또는 [Windows::Foundation::Metadata::AttributeUsageAttribute]를 지정할 수 없습니다.

사용자 정의된 관리되는 특성은 <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>에서 상속해야 합니다. Windows 런타임 특성은 `Windows::Foundation::Metadata` 네임스페이스에서 정의해야 합니다.

자세한 내용은 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3450 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C3450.cpp
// compile with: /clr
// C3450 expected
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref struct AtClass {
   AtClass(Type ^) {}
};

[attribute(AttributeTargets::All)]
ref struct AtClass2 {
   AtClass2() {}
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
// Delete the following line to resolve.
ref class B {};
// Uncomment the following line to resolve.
// ref class B : Attribute {};
```

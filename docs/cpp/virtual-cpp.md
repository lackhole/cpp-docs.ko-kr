---
title: virtual (C++)
ms.date: 11/04/2016
f1_keywords:
- virtual_cpp
- virtual
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
ms.openlocfilehash: f68bd2e500ebe16c43ef6c3d7a5aede26421b27d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393911"
---
# <a name="virtual-c"></a>virtual (C++)

**virtual** 키워드는 가상 함수 또는 가상 기본 클래스를 선언합니다.

## <a name="syntax"></a>구문

```
virtual [type-specifiers] member-function-declarator
virtual [access-specifier] base-class-name
```

#### <a name="parameters"></a>매개 변수

*type-specifiers*<br/>
가상 멤버 함수의 반환 형식을 지정합니다.

*member-function-declarator*<br/>
멤버 함수를 선언합니다.

*access-specifier*<br/>
기본 클래스에 대한 액세스 수준을 **public**, **protected** 또는 **private**으로 정의합니다. **virtual** 키워드 앞이나 뒤에 나타날 수 있습니다.

*base-class-name*<br/>
이전에 선언된 클래스 형식을 식별합니다.

## <a name="remarks"></a>설명

자세한 내용은 [가상 함수](../cpp/virtual-functions.md)를 참조하세요.

또한 키워드 [class](../cpp/class-cpp.md), [private](../cpp/private-cpp.md), [public](../cpp/public-cpp.md) 및 [protected](../cpp/protected-cpp.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)
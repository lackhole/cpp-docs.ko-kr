---
title: 컴파일러 오류 C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 5ef4352101541391a7cda88471fbaa6aeae4ffb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328720"
---
# <a name="compiler-error-c3451"></a>컴파일러 오류 C3451

'attribute': 'type' 관리 되지 않는 특성을 적용할 수 없습니다

C++ CLR 형식에 특성을 적용할 수 없습니다. 참조 [ C++ 특성 참조](../../windows/attributes/attributes-alphabetical-reference.md) 에 대 한 자세한 내용은 합니다.

자세한 내용은 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.

이 오류는 시각적 개체에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다 C++ 2005: 합니다 [uuid](../../windows/uuid-cpp-attributes.md) CLR 프로그래밍을 사용 하 여 사용자 정의 특성에서 특성을 사용할 수 없습니다. 대신 <xref:System.Runtime.InteropServices.GuidAttribute>를 사용하세요.

## <a name="example"></a>예제

다음 샘플 C3451를 생성합니다.

```
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```
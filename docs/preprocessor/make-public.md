---
title: make_public
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
ms.openlocfilehash: d569758f90b9e55f65ad13517f86dea41d151ca8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371765"
---
# <a name="makepublic"></a>make_public
네이티브 형식이 공용 어셈블리 액세스 가능성을 갖도록 지정합니다.

## <a name="syntax"></a>구문

```
#pragma make_public(type)
```

### <a name="parameters"></a>매개 변수

*형식* 공용 어셈블리 액세스 가능성을 갖도록 하려는 형식의 이름입니다.

## <a name="remarks"></a>설명

**make_public** 변경할 수 없는.h 파일에서 참조 하려는 네이티브 형식이 표시 되는 경우에 유용 합니다. 공용 어셈블리 표시 유형이 있는 형식의 공용 함수 시그니처에서 네이티브 형식을 사용하려는 경우 해당 네이티브 형식에도 공용 어셈블리 액세스 가능성이 있어야 하며, 그렇지 않으면 컴파일러에서 경고를 생성합니다.

**make_public** 전역 범위에서 지정 해야 하며 하며 선언 된 소스 코드 파일의 끝에만 지점에서 적용 됩니다.

네이티브 형식으로 암시적 또는 명시적으로 private 수 있습니다. 참조 [형식 표시 유형](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 자세한 내용은 합니다.

## <a name="examples"></a>예제

다음 샘플은 두 네이티브 구조체에 대한 정의가 포함된 .h 파일의 내용입니다.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

다음 코드 예제는 헤더 파일을 사용 하 고 표시 하지 않으면 명시적으로 공용으로 네이티브 구조체를 사용 하 여 보여 줍니다 **make_public**에서 네이티브 구조체를 사용 하려고 하면 컴파일러에서 경고를 생성 합니다 관리 되는 공용 형식의 공용 함수 시그니처에서.

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
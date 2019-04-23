---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: c46924d2757d01a934c21a70f23e6556f6a10fd3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034091"
---
# <a name="embeddedidl"></a>embedded_idl

**C++특정**

특성에서 생성된 코드를 유지한 상태에서 형식 라이브러리가 .tlh 파일에 작성되도록 지정합니다.

## <a name="syntax"></a>구문

```
embedded_idl[("param")]
```

### <a name="parameters"></a>매개 변수

*param*<br/>
다음 두 값 중 하나일 수 있습니다.

- **emitidl**: Typelib에서 가져온 형식 정보가 특성 사용된 프로젝트에 대해 생성 된 IDL에 표시 됩니다.  `embedded_idl`에 대한 매개 변수를 지정하지 않는 경우 이 값이 기본값으로 적용됩니다.

- **no_emitidl**: Typelib에서 가져온 형식 정보가 특성 사용된 프로젝트에 대해 생성 된 IDL에 표시 되지 않습니다.

## <a name="example"></a>예제

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

## <a name="remarks"></a>설명

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)
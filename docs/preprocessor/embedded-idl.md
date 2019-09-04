---
title: embedded_idl import 특성
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 01948b171b20ad0a3bf3e7a41047f1fe3df185b0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216333"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl import 특성

**C++컴퓨터별**

특성 생성 코드를 유지 하 여 형식 라이브러리 `.tlh` 를 파일에 쓸지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **embedded_idl** [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>매개 변수

**emitidl**\
*형식 라이브러리* 에서 가져온 형식 정보가 특성 사용 프로젝트에 대해 생성 된 IDL에 존재 합니다. 이 동작은 기본값이 며에 `embedded_idl`매개 변수를 지정 하지 않는 경우에 적용 됩니다.

**"no_emitidl"** \
*형식 라이브러리* 에서 가져온 형식 정보가 특성 사용 프로젝트에 대해 생성 된 IDL에 없습니다.

## <a name="example"></a>예제

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)

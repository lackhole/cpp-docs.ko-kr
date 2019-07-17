---
title: '&lt;cstdarg&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdarg>
helpviewer_keywords:
- cstdarg header
ms.assetid: 639b4ef7-8408-4640-9343-41631f0ab663
ms.openlocfilehash: f8d2d3b886cfa46905e8f17f1e13b51881b80191
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244481"
---
# <a name="ltcstdarggt"></a>&lt;cstdarg&gt;

표준 C 라이브러리 헤더를 포함 \<stdarg.h >에 연결된 된 이름을 추가 하 고는 `std` 네임 스페이스입니다. 외부 링크를 사용 하 여 표준 C 라이브러리 헤더에 선언 된 이름에 선언 되어 있는지 확인이 헤더를 포함 하는 `std` 네임 스페이스입니다.

## <a name="syntax"></a>구문

```cpp
#include <cstdarg>
```

## <a name="namespace-and-macros"></a>Namespace 및 매크로

```cpp
namespace std {
    using va_list = see below;
}

#define va_arg(V, P)
#define va_copy(VDST, VSRC)
#define va_end(V)
#define va_start(V, P)
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

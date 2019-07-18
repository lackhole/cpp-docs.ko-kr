---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 14dda03e835ec411013b2d827bd1ccaa77f8982e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245014"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

표준 C 라이브러리 헤더를 포함 \<r t. h >에 연결된 된 이름을 추가 하 고는 `std` 네임 스페이스입니다. 외부 링크를 사용 하 여 표준 C 라이브러리 헤더에 선언 된 이름에 선언 되어 있는지 확인이 헤더를 포함 하는 `std` 네임 스페이스입니다.

> [!NOTE]
> \<r t. h >를 정의 하지 않습니다는 `static_assert` 매크로입니다.

## <a name="syntax"></a>구문

```cpp
#include <cassert>
```

## <a name="macros"></a>매크로

```cpp
#define assert(E)
```

### <a name="remarks"></a>설명

`assert(E)` 상수 NDEBUG 정의 된 경우만 여기서 `assert` 마지막으로 정의 되어 있거나 재정의 된 또는 *E* 변환할 bool로 **true**합니다.

## <a name="see-also"></a>참고자료

[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

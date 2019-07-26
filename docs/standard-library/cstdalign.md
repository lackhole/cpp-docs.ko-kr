---
title: '&lt;cstdalign&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- cstdalign
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 603a590190c50495aa80f1b41a574149eb8f760a
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68342842"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign&gt;

일부 C++ 표준 라이브러리 구현에서이 헤더는 C 표준 라이브러리 헤더 \<stdalign. h >를 포함 하 고 `std` 네임 스페이스에 연결 된 이름을 추가 합니다. 해당 헤더는 MSVC에서 구현 되지 않으므로 cstdalign > 헤더는 호환성 매크로 \< `__alignas_is_defined` 및 `__alignof_is_defined`을 정의 합니다.

> [!NOTE]
> Stdalign \<. h > 헤더는의 C++키워드인 매크로를 정의 하므로이를 포함 하 여 아무런 효과가 없습니다. Stdalign. h > 헤더는에서 C++더 이상 사용 되지 않습니다. \< \<Cstdalign > 헤더는 c + + 17에서 더 이상 사용 되지 않으며 초안 c + + 20 표준에서 제거 되었습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<cstdalign >

**네임스페이스:** std

## <a name="macros"></a>매크로

| 매크로 | Description |
| - | - |
| `__alignas_is_defined` | 정수 상수 1로 확장 되는 C 호환성 매크로입니다. |
| `__alignof_is_defined` | 정수 상수 1로 확장 되는 C 호환성 매크로입니다. |

## <a name="see-also"></a>참고자료

[헤더 파일 참조](cpp-standard-library-header-files.md)\
[C++표준 라이브러리 개요](cpp-standard-library-overview.md)\
[C++ 표준 라이브러리의 스레드 보안](thread-safety-in-the-cpp-standard-library.md)

---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: 339c32f9b487db2e318f8763ac01a0d155fc1dc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159706"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체된 이 매크로는 반복기 디버깅 기능이 디버그 빌드에서 사용하도록 설정되었는지 여부를 정의합니다. 반복기 디버깅은 기본적으로 디버그 빌드에서는 사용하도록 설정되고 정품 빌드에서는 사용하지 않도록 설정됩니다. 자세한 내용은 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)을 참조하세요.

> [!IMPORTANT]
> _HAS_ITERATOR_DEBUGGING 매크로 직접 사용 하는 사용 되지 않습니다. 대신, _ITERATOR_DEBUG_LEVEL 반복기 디버그 설정 제어 하기를 사용 합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.

## <a name="remarks"></a>설명

디버그 빌드에서 디버그 반복기를 사용 하려면 _ITERATOR_DEBUG_LEVEL 2로 설정 합니다. 이 1 _HAS_ITERATOR_DEBUGGING 설정을 동일 또는 사용 하도록 설정 합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL 2로 설정할 수 없습니다 (및 _HAS_ITERATOR_DEBUGGING 1로 설정할 수 없습니다) 일반 정품 빌드에서 합니다.

디버그 빌드에서 디버그 반복기를 사용 하지 않으려면 _ITERATOR_DEBUG_LEVEL 0 또는 1로 설정 합니다. 이 0 _HAS_ITERATOR_DEBUGGING 설정을 동일 또는 사용 하지 않도록 설정 합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>참고자료

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)<br/>

---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: a1e3017ed7c6def18ce02d99dc8253b69c11ab58
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448828"
---
# <a name="_has_iterator_debugging"></a>_HAS_ITERATOR_DEBUGGING

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체된 이 매크로는 반복기 디버깅 기능이 디버그 빌드에서 사용하도록 설정되었는지 여부를 정의합니다. 반복기 디버깅은 기본적으로 디버그 빌드에서는 사용하도록 설정되고 제품 빌드에서는 사용하지 않도록 설정됩니다. 자세한 내용은 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)을 참조하세요.

> [!IMPORTANT]
> _HAS_ITERATOR_DEBUGGING 매크로를 직접 사용하는 것은 더 이상 사용 되지 않습니다. 대신 _ITERATOR_DEBUG_LEVEL를 사용하여 반복기 디버그 설정을 제어 합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.

## <a name="remarks"></a>설명

디버그 빌드에서 반복기 디버깅을 사용 하도록 설정 하려면 _ITERATOR_DEBUG_LEVEL을 2로 설정 합니다. 이는 _HAS_ITERATOR_DEBUGGING 설정 1에 해당 하거나 사용 하도록 설정된 것과 같습니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

소매점 빌드에서는 _ITERATOR_DEBUG_LEVEL을 2로 설정할 수 없으며 _HAS_ITERATOR_DEBUGGING을 1로 설정할 수 없습니다.

디버그 빌드에서 디버그 반복기를 사용 하지 않도록 설정 하려면 _ITERATOR_DEBUG_LEVEL을 0 또는 1로 설정 합니다. 이는 _HAS_ITERATOR_DEBUGGING 설정 0 또는 해제와 동일 합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>참고자료

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[디버그 반복기 지원](../standard-library/debug-iterator-support.md)\
[확인된 반복기](../standard-library/checked-iterators.md)\
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)

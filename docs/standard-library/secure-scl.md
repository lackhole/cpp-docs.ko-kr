---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1af084363fc0d6d1723a9af7b633779f92ed2b38
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450538"
---
# <a name="_secure_scl"></a>_SECURE_SCL

[확인된 반복기](../standard-library/checked-iterators.md)가 사용하도록 설정되었는지를 정의하는 이 매크로는 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체되었습니다. 확인된 반복기는 기본적으로 디버그 빌드에서는 사용하도록 설정되고 제품 빌드에서는 사용하지 않도록 설정됩니다.

> [!IMPORTANT]
> _SECURE_MM 매크로를 직접 사용하는 것은 더 이상 권장되지 않습니다. 대신 _ITERATOR_DEBUG_LEVEL을 사용하여 확인된 반복기 설정을 제어합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.

## <a name="remarks"></a>설명

확인된 반복기를 사용하는 경우에는 안전하지 않은 반복기 사용으로 인해 런타임 오류가 발생하며 프로그램이 종료됩니다. 확인 된 반복기를 사용 하도록 설정 하려면 _ITERATOR_DEBUG_LEVEL을 1 또는 2로 설정 합니다. 이는 _SECURE_SCL 설정 1에 해당 하거나 사용 하도록 설정 된 것과 같습니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

확인 된 반복기를 사용 하지 않도록 설정 하려면 _ITERATOR_DEBUG_LEVEL을 0으로 설정 합니다. 이는 _SECURE_SCL 설정 0 또는 사용 안 함에 해당 합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

확인된 반복기에 대한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[확인된 반복기](../standard-library/checked-iterators.md)\
[디버그 반복기 지원](../standard-library/debug-iterator-support.md)\
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)

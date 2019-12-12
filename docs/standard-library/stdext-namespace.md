---
title: stdext 네임스페이스
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: d40f3f7a99db72784cc9a32a9c37064228597d34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412425"
---
# <a name="stdext-namespace"></a>stdext 네임스페이스

[\<hash_map>](../standard-library/hash-map.md)과 [\<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 현재 ISO C++ 표준이 아닙니다. 따라서 C++ 표준을 계속 준수하기 위해 이러한 형식 및 멤버를 `std` 네임스페이스에서 `stdext`네임스페이스로 이동했습니다.

기본값인 [/Ze](../build/reference/za-ze-disable-language-extensions.md)로 컴파일할 때 컴파일러는 \<hash_map>과 \<hash_set> 헤더 파일의 멤버에 `std` 사용에 대하여 경고합니다. 이 경고를 사용하지 않도록 설정하려면 [warning](../preprocessor/warning.md) pragma를 사용합니다.

**/Ze**와 함께 \<hash_map>과 \<hash_set> 헤더 파일의 멤버에 `std`를 사용할 때 컴파일러가 오류를 발생하도록 하려면 C++ 표준 라이브러리 헤더 파일을 `#include`하기 전에 다음 지시문을 추가합니다.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

**/Za**로 컴파일할 때 컴파일러는 오류를 생성합니다.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)

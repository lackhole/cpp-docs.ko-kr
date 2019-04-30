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

멤버는 [ \<hash_map >](../standard-library/hash-map.md) 하 고 [ \<hash_set >](../standard-library/hash-set.md) 헤더 파일의 일부분이 아닌 현재 ISO C++ 표준입니다. 따라서 C++ 표준을 계속 준수하기 위해 이러한 형식 및 멤버를 `std` 네임스페이스에서 `stdext`네임스페이스로 이동했습니다.

로 컴파일하는 경우 [/Ze](../build/reference/za-ze-disable-language-extensions.md), 기본값인, 컴파일러가를 사용할 때의 경고 `std` 의 멤버에 대 한 합니다 \<hash_map > 및 \<hash_set > 헤더 파일입니다. 이 경고를 사용하지 않도록 설정하려면 [경고](../preprocessor/warning.md) pragma를 사용합니다.

컴파일러의 사용에 대 한 오류를 생성 하려면 `std` 의 멤버에 대 한는 \<hash_map > 및 \<hash_set > 헤더 파일을 **/Ze**를 하기 전에 다음 지시문을 추가 `#include` 모든 C++ 표준 라이브러리 헤더 파일입니다.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

사용 하 여 컴파일하면 **/Za**, 컴파일러는 오류를 생성 합니다.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)

---
title: 런타임 형식 정보
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
ms.openlocfilehash: 1d11ee3ea472f935120c59f0faefee905361ee97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267404"
---
# <a name="run-time-type-information"></a>런타임 형식 정보

RTTI(런타임 형식 정보)는 프로그램 실행 중에 개체의 형식이 결정될 수 있도록 하는 메커니즘입니다. 많은 클래스 라이브러리 공급업체가 이 기능을 자체적으로 구현하고 있었기 때문에 RTTI가 C++ 언어에 추가되었습니다. 이 때문에 라이브러리 간에 호환되지 않는 문제가 발생하게 되었으므로 언어 수준에서 런타임 형식 정보에 대한 지원이 필요하다는 사실이 명백해졌습니다.

명확성을 위해 여기에서 RTTI에 대한 설명은 거의 전적으로 포인터에 국한됩니다. 하지만 설명된 개념은 참조에도 적용됩니다.

런타임 형식 정보에는 다음 세 가지 기본 C++ 언어 요소가 있습니다.

- [dynamic_cast](../cpp/dynamic-cast-operator.md) 연산자

   다형 형식을 변환하는 데 사용됩니다.

- [typeid](../cpp/typeid-operator.md) 연산자

   개체의 정확한 형식을 식별하는 데 사용됩니다.

- [type_info](../cpp/type-info-class.md) 클래스

   **typeid** 연산자에서 반환된 형식 정보를 저장하는 데 사용됩니다.

## <a name="see-also"></a>참고 항목

[캐스팅](../cpp/casting.md)
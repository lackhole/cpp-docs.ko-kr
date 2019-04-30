---
title: 모호한 선언 해결 (C++)
ms.date: 11/04/2016
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
ms.openlocfilehash: 52e94f474d59505298cb4f78a477cedd21b90aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403401"
---
# <a name="resolving-ambiguous-declarations-c"></a>모호한 선언 해결 (C++)

한 형식에서 다른 한 형식으로의 명시적 변환을 수행하려면 원하는 형식 이름을 지정하여 캐스팅을 사용해야 합니다. 일부 형식 캐스팅 결과 구문이 모호해집니다. 다음 함수 스타일 형식 캐스팅이 모호합니다.

```cpp
char *aName( String( s ) );
```

분명 하지 함수 선언 또는 함수 스타일 캐스트가 이니셜라이저인 개체 선언 인지 합니다. 형식을 반환 하는 함수를 선언 `char *` 형식의 인수 하나를 사용 하는 `String`, 또는 개체를 선언할 수 없습니다 `aName` 의 값을 사용 하 여 초기화 `s` 형식으로 캐스팅 `String`합니다.

선언이 올바른 함수 선언으로 간주될 수 있는 경우 해당 선언이 이와 같이 처리됩니다. 해당 선언이 함수 선인일 수 없는 경우에만, 즉 구문상으로 잘못된 경우 함수 스타일 형식 캐스트인지 여부를 확인하기 위해 문이 검사됩니다. 따라서 컴파일러는 문을 함수의 선언으로 간주하고 `s` 식별자 주위의 괄호를 무시합니다. 반면 다음

```cpp
char *aName( (String)s );
```

및

```cpp
char *aName = String( s );
```

문은 분명히 개체의 선언이며 `String` 형식에서 `char *` 형식으로의 사용자 정의 변환이 호출되어 `aName`의 초기화를 수행합니다.

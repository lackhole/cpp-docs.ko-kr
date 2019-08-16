---
title: 통합
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: 288af427bd6a8d9baf572dfad8e4a25452694ad9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491978"
---
# <a name="aggregation"></a>통합

객체의 구현자가 다른 미리 만들어진 객체에 의해 제공되는 서비스를 활용하고자 할 때가 있습니다. 더욱이 이런 두번째 개체를 첫번째 개체의 일부로 표시되도록 하려고 합니다. COM은 포함(Containment) 및 통합(Aggregation)을 통해 이러한 목표를 달성합니다.

통합은 포함하는(외부) 개체가 생성된 프로세스의 일부로 포함된(내부) 개체를 만들고, 내부 개체의 인터페이스가 외부에 의해 노출됨을 의미합니다. 개체는 자신이 통합 가능한지 여부를 결정할 수 있습니다. 통합 가능한 경우 통합이 제대로 동작하도록 특정 규칙을 수행해야 합니다.

기본적으로, 포함되는 개체에 대한 모든 `IUnknown` 메서드 호출은 포함하는 개체에 위임해야 합니다.

## <a name="see-also"></a>참고자료

[COM 소개](../atl/introduction-to-com.md)<br/>
[개체 재사용](/windows/win32/com/reusing-objects)

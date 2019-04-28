---
title: COM 인터페이스 진입점
ms.date: 03/27/2019
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: eb8fc425d6b9849f6367d9b207e5181652386be3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207854"
---
# <a name="com-interface-entry-points"></a>COM 인터페이스 진입점

COM 인터페이스의 멤버 함수를 사용 합니다 `METHOD_PROLOGUE` 내보낸된 인터페이스의 메서드를 호출할 때 적절 한 전역 상태를 유지 하는 매크로입니다.

인터페이스의 멤버 함수에서 구현 되는 일반적으로 `CCmdTarget`-파생된 개체의 자동 초기화를 제공 하려면이 매크로 이미 사용 된 `pThis` 포인터입니다. 예를 들어:

[!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]

자세한 내용은 참조 하세요. [기술 참고 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) MFC/OLE에 `IUnknown` 구현 합니다.

`METHOD_PROLOGUE` 매크로로 정의 됩니다.

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

전역 상태 관리와 관련된 매크로 부분은 다음과 같습니다.

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

이 식에서 *m_pModuleState* 포함 하는 개체의 멤버 변수 것으로 간주 됩니다. 에 의해 구현 됩니다 합니다 `CCmdTarget` 기본 클래스 및 적절 한 값으로 초기화 됩니다 `COleObjectFactory`개체를 인스턴스화할 때, 합니다.

## <a name="see-also"></a>참고자료

[MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)

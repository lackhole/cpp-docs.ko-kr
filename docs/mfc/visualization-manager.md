---
title: 시각화 관리자
ms.date: 11/19/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: 9c9dc19266d80d56f696953c5f5896eb9d99cc8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358578"
---
# <a name="visualization-manager"></a>시각화 관리자

비주얼 관리자는 전체 응용 프로그램의 모양을 제어 하는 개체입니다. 역할 단일 클래스로 응용 프로그램에 대 한 모든 그리기 코드를 넣을 수 있는 합니다. MFC 라이브러리는 여러 비주얼 관리자를 포함합니다. 응용 프로그램에 대 한 사용자 지정 보기를 만들려는 경우에 고유한 비주얼 관리자를 만들 수 있습니다. 다음 이미지는 다른 비주얼 관리자 활성화 된 경우 동일한 응용 프로그램을 보여 줍니다.

![CMFCVisualManagerWindows에서 렌더링 된 MyApp](../mfc/media/vmwindows.png "CMFCVisualManagerWindows에서 렌더링 된 MyApp") <br/>
CMFCVisualManagerWindows 비주얼 관리자를 사용 하는 MyApp

![CMFCVisualManagerVS2005에서 렌더링 된 MyApp](../mfc/media/vmvs2005.png "CMFCVisualManagerVS2005에서 렌더링 된 MyApp") <br/>
CMFCVisualManagerVS2005 비주얼 관리자를 사용 하는 MyApp

![CMFCVisualManagerOfficeXP에서 렌더링 된 MyApp](../mfc/media/vmofficexp.png "CMFCVisualManagerOfficeXP에서 렌더링 된 MyApp") <br/>
CMFCVisualManagerOfficeXP 비주얼 관리자를 사용 하는 MyApp

![CMFCVisualManagerOffice2003에서 렌더링 된 MyApp](../mfc/media/vmoffice2003.png "CMFCVisualManagerOffice2003에서 렌더링 된 MyApp") <br/>
CMFCVisualManagerOffice2003 비주얼 관리자를 사용 하는 MyApp

![CMFCVisualManagerOffice2007에서 렌더링 된 MyApp](../mfc/media/msoffice2007.png "CMFCVisualManagerOffice2007에서 렌더링 된 MyApp") <br/>
CMFCVisualManagerOffice2007 비주얼 관리자를 사용 하는 MyApp

기본적으로 visual manager에는 여러 GUI 요소에 대 한 그리기 코드를 유지 관리합니다. 사용자 지정 UI 요소를 제공 하려면 비주얼 관리자의 관련된 그리기 메서드를 재정의 해야 합니다. 이러한 메서드의 목록에 대 한 참조 [CMFCVisualManager 클래스](../mfc/reference/cmfcvisualmanager-class.md)합니다. 사용자 지정 모양을 제공 하기 위해 재정의할 수 있는 메서드는 시작 하는 모든 메서드 `OnDraw`합니다.

응용 프로그램 하나만 있을 수 있습니다 `CMFCVisualManager` 개체입니다. 정적 함수를 호출 응용 프로그램에 대 한 비주얼 관리자에 대 한 포인터를 얻으려면 [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance)합니다. 모든 비주얼 관리자 상속할 `CMFCVisualManager`, `CMFCVisualManager::GetInstance` 메서드는 포인터를 얻으려면 비주얼 관리자를 적절 한 사용자 지정 비주얼 관리자를 만드는 경우에 합니다.

사용자 지정 비주얼 관리자를 만들려는 경우 이미 존재 하는 비주얼 관리자에서 파생 해야 합니다. 기본 클래스에서 파생 하는 `CMFCVisualManager`합니다. 그러나 응용 프로그램에 대해 원하는 더 유사 하는 경우 다른 비주얼 관리자를 사용할 수 있습니다. 예를 들어 사용 하려는 경우는 `CMFCVisualManagerOffice2007` 비주얼 관리자 구분 기호를 확인 하는 방법을 변경 하지만 원하는에서 사용자 지정 클래스를 파생할 수 `CMFCVisualManagerOffice2007`입니다. 이 시나리오에서는 구분 기호를 그리기 위한 메서드만 덮어써야 합니다.

응용 프로그램에 대 한 특정 비주얼 관리자를 사용 하는 두 가지 방법이 있습니다. 첫 번째 방법은 호출 하는 [cmfcvisualmanager:: Setdefaultmanager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) 메서드 및 매개 변수로 적절 한 비주얼 관리자를 전달 합니다. 다음 코드 예제에서는 사용 하는 방법의 `CMFCVisualManagerVS2005` 이 메서드를 사용 하 여 비주얼 관리자:

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

응용 프로그램에서 비주얼 관리자를 사용 하는 다른 방법은 수동으로 만들어야 하는 경우 그런 다음 응용 프로그램 모든 렌더링에 대 한이 새 비주얼 관리자를 사용 합니다. 그러나 하나만 있을 수 있으므로 `CMFCVisualManager` 응용 프로그램당 개체 새로 만들기 전에 현재 비주얼 관리자를 삭제 해야 합니다. 다음 예에서 `CMyVisualManager` 에서 파생 되는 사용자 지정 비주얼 관리자는 `CMFCVisualManager`합니다. 다음 메서드는 비주얼 관리자는 인덱스에 따라 응용 프로그램에 표시를 변경 합니다.

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
        CMFCVisualManager::GetInstance();
        break;

    case CUSTOM_STYLE:
        new CMyVisualManager;
        break;

    default:
        CMFCVisualManager::GetInstance();
        break;
    }

    CMFCVisualManager::GetInstance()->RedrawAll();
}
```

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)<br/>
[CMFCVisualManager 클래스](../mfc/reference/cmfcvisualmanager-class.md)

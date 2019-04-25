---
title: '컨테이너: 클라이언트 항목 알림'
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
ms.openlocfilehash: 583c438820c002a4c192d15358ca98424d02889a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153427"
---
# <a name="containers-client-item-notifications"></a>컨테이너: 클라이언트 항목 알림

이 문서에서는 MFC 프레임 워크 클라이언트 응용 프로그램의 문서에서 항목을 수정 하는 서버 응용 프로그램을 호출 하는 재정의 가능 함수를 설명 합니다.

[COleClientItem](../mfc/reference/coleclientitem-class.md) 서버 응용 프로그램이 라고도 하는 구성 요소 응용 프로그램에서 요청에 대 한 응답으로 호출 되는 몇 가지 재정의 가능 함수를 정의 합니다. 이러한 함수는 일반적으로 알림으로 작동합니다. 컨테이너 응용 프로그램을의 위치 및 편집, 항목을 조작 하는 경우 사용자가 변경한 내용을 변경 또는 스크롤, 활성화 등의 다양 한 이벤트를 알려 줍니다.

프레임 워크에 컨테이너 응용 프로그램에 대 한 호출을 통해 변경 내용 알립니다 `COleClientItem::OnChange`, 함수로 구현이 필요 합니다. 이 보호 된 함수는 두 개의 인수를 받습니다. 첫 번째 서버 항목을 변경한 이유를 지정 합니다.

|알림|의미|
|------------------|-------------|
|**OLE_CHANGED**|OLE 항목의 모양을 변경 되었습니다.|
|**OLE_SAVED**|OLE 항목이 저장 되었습니다.|
|**OLE_CLOSED**|OLE 항목이 사용 중지 되었습니다.|
|**OLE_RENAMED**|OLE 항목을 포함 하는 서버 문서가 바뀌었습니다.|
|**OLE_CHANGED_STATE**|OLE 항목은 다른 한 상태에서 변경 되었습니다.|
|**OLE_CHANGED_ASPECT**|OLE 항목의 그리기 모양은 프레임 워크에 의해 변경 되었습니다.|

이러한 값은는 **OLE_NOTIFICATION** AFXOLE에 정의 된 열거형입니다. 8.

이 함수에서 두 번째 인수에는 항목을 변경 하는 방법 또는 어떤 상태로 전환 되었음을 지정 합니다.

|첫 번째 인수는 경우|두 번째 인수|
|----------------------------|---------------------|
|**OLE_SAVED** 또는 **OLE_CLOSED**|사용 되지 않습니다.|
|**OLE_CHANGED**|변경 된 OLE 항목의 모양을 지정 합니다.|
|**OLE_CHANGED_STATE**|입력 상태를 설명 합니다 (*emptyState*, *loadedState*를 *openState*를 *activeState*, 또는  *activeUIState*).|

클라이언트 항목을 가정할 수 상태에 대 한 자세한 내용은 참조 하세요. [컨테이너: 클라이언트 항목 상태](../mfc/containers-client-item-states.md)합니다.

프레임 워크 호출 `COleClientItem::OnGetItemPosition` 경우 항목이 활성화 되 고 내부 편집 합니다. 구현은 내부 편집을 지 원하는 응용 프로그램에 필요 합니다. MFC 응용 프로그램 마법사를 항목의 좌표를 할당 하는 기본 구현을 제공 합니다 `CRect` 인수로 전달 되는 개체 `OnGetItemPosition`합니다.

내부 편집 하는 동안 OLE 항목의 위치 또는 크기가 변경 되 면 항목의 위치 및 클리핑 사각형에 대 한 컨테이너의 정보를 업데이트 해야 하 고 서버 변경 내용에 대 한 정보를 받아야 합니다. 프레임 워크 호출 `COleClientItem::OnChangeItemPosition` 이 목적입니다. MFC 응용 프로그램 마법사는 기본 클래스의 함수를 호출 하는 재정의 제공 합니다. 응용 프로그램 마법사가 작성 하는 함수를 편집 해야 프로그램 `COleClientItem`-클라이언트 항목 개체에 의해 보존 된 모든 정보를 업데이트 하는 함수는 클래스를 파생 합니다.

## <a name="see-also"></a>참고자료

[컨테이너](../mfc/containers.md)<br/>
[컨테이너: 클라이언트 항목 상태](../mfc/containers-client-item-states.md)<br/>
[COleClientItem::OnChangeItemPosition](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

---
title: 가상 목록 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: 7372aca9e24a554e01f7a61f43d6170e99fe34c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358260"
---
# <a name="virtual-list-controls"></a>가상 목록 컨트롤

가상 목록 컨트롤은 LVS_OWNERDATA 스타일이 적용 된 목록 뷰 컨트롤입니다. 이 스타일을 사용 하면 최대 항목 수를 지원 하도록 컨트롤을 **DWORD** (기본 항목 수로만 확장을 **int**). 그러나이 스타일의 가장 큰 장점은 한 번에 메모리에 데이터 항목의 하위 집합 하나만 수입니다. 이렇게 하면 자신을 대여할 정보의 큰 데이터베이스 사용에 대 한 가상 목록 뷰 컨트롤에서 있는 특정 데이터에 액세스 하는 방법이 이미 진행에서 합니다.

> [!NOTE]
>  가상 목록 기능을 제공 하는 것 외에도 `CListCtrl`, MFC는 또한 동일한 기능을 제공 합니다 [CListView](../mfc/reference/clistview-class.md) 클래스입니다.

가상 목록 컨트롤을 개발할 때 고려해 야 하는 몇 가지 호환성 문제가 있습니다. 자세한 내용은 Windows SDK의 목록 뷰 컨트롤 항목의 호환성 문제 섹션을 참조 하세요.

## <a name="handling-the-lvngetdispinfo-notification"></a>LVN_GETDISPINFO 알림 처리

가상 목록 컨트롤 항목 정보를 거의 유지 관리합니다. 항목 선택 및 포커스가 정보를 제외 하 고 모든 항목 정보는 컨트롤의 소유자에 의해 관리 됩니다. LVN_GETDISPINFO 알림 메시지를 통해 프레임 워크에서 정보를 요청 합니다. 요청된 된 정보를 제공 하려면 가상 목록 컨트롤 (또는 컨트롤 자체)의 소유자가 알림이 메시지를 처리 해야 합니다. 쉽게 이렇게 하려면 속성 창을 사용 하 여 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)). 결과 코드는 다음과 같이 표시 됩니다 (여기서 `CMyDialog` 가상 목록 컨트롤 개체를 소유 하 고 대화 상자에서 알림을 처리 하 고):

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

LVN_GETDISPINFO 알림 메시지에 대 한 처리기에서 어떤 유형의 정보를 요청 하는 참조를 확인 해야 합니다. 가능한 값은 다음과 같습니다.

- `LVIF_TEXT` 합니다 *pszText* 멤버 입력 해야 합니다.

- `LVIF_IMAGE` 합니다 *iImage* 멤버 입력 해야 합니다.

- `LVIF_INDENT` 합니다 *iIndent* 멤버 입력 해야 합니다.

- `LVIF_PARAM` 합니다 *lParam* 멤버 입력 해야 합니다. (없음 하위 항목에 대 한 합니다.)

- `LVIF_STATE` 합니다 *상태* 멤버 입력 해야 합니다.

다음 프레임 워크를 다시 요청 된 정보를 제공 해야 합니다.

(List 컨트롤 개체에 대 한 알림 처리기의 본문에서 가져온) 다음 예제에서 텍스트 버퍼와 항목의 이미지에 대 한 정보를 제공 하 여 가능한 방법 중 하나를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>캐싱 및 가상 목록 컨트롤

이 유형의 목록 컨트롤은 이므로 큰 데이터 집합에 대 한 검색 성능 향상을 위해 요청 된 항목 데이터를 캐시 하는 하는 것이 좋습니다. 프레임 워크 LVN_ODCACHEHINT 알림 메시지를 전송 하 여 캐시를 최적화 하는 데 도움이 되는 캐시 힌트 메커니즘을 제공 합니다.

다음 예제에서는 처리기 함수에 전달 하는 범위를 사용 하 여 캐시를 업데이트 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

준비 하 고 캐시를 유지 관리에 대 한 자세한 내용은 Windows SDK의 목록 뷰 컨트롤 항목의 캐시 관리 섹션을 참조 합니다.

## <a name="finding-specific-items"></a>특정 항목 찾기

LVN_ODFINDITEM 알림 메시지는 특정 목록 컨트롤 항목을 찾을 수 해야 할 때 가상 목록 컨트롤에서 전송 됩니다. 목록 뷰 컨트롤에서 키 빠른 받으면 또는 LVM_FINDITEM 메시지를 받으면 알림 전송 됩니다. 형태로 검색 정보가 전송 됩니다는 **LVFINDINFO** 구성원 인 구조체의는 **NMLVFINDITEM** 구조입니다. 재정의 하 여이 메시지를 처리 합니다 `OnChildNotify` 목록에 함수 개체를 제어 하 고 처리기의 본문 내에서 LVN_ODFINDITEM 메시지를 확인 합니다. 하는 경우 적절 한 작업을 수행 합니다.

목록 뷰 컨트롤에서 제공한 정보와 일치 하는 항목을 검색할 수 있도록 준비 해야 합니다. 일치 하는 항목이 있으면 성공한 경우 항목의 인덱스를 반환 해야 합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)

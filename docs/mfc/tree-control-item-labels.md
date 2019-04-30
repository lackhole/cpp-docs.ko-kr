---
title: 트리 컨트롤 항목 레이블
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
ms.openlocfilehash: c945556ff9236db1ca61b15f1072efdc2f49541f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371953"
---
# <a name="tree-control-item-labels"></a>트리 컨트롤 항목 레이블

트리 컨트롤에 항목을 추가할 때 일반적으로 항목의 레이블 텍스트를 지정 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). 합니다 `InsertItem` 멤버 함수를 전달할 수는 [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) 레이블의 텍스트를 포함 하는 문자열을 포함 하 여 항목의 속성을 정의 하는 구조입니다. `InsertItem` 다양 한 조합을 매개 변수를 사용 하 여 호출할 수 있는 여러 오버 로드가 있습니다.

각 항목을 저장 하기 위한 메모리를 할당 하는 트리 컨트롤 이 메모리의 상당한 부분을 차지 하는 항목 레이블의 텍스트입니다. 트리 컨트롤에서 문자열의 복사본을 유지 하는 응용 프로그램을 하는 경우를 지정 하 여 컨트롤의 메모리 요구 사항을 줄일 수 있습니다 합니다 **LPSTR_TEXTCALLBACK** 값을 *pszText* 소속`TV_ITEM` 또는 *lpszItem* 트리 컨트롤에 실제 문자열을 전달 하는 대신 매개 변수입니다. 사용 하 여 **LPSTR_TEXTCALLBACK** 하면 트리 컨트롤 항목을 그려야 할 때마다 응용 프로그램에서 항목의 레이블 텍스트를 검색 합니다. 트리 컨트롤에서 보내는 텍스트를 검색 하려면를 [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo) 주소를 포함 하는 알림 메시지를 [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) 구조입니다. 포함된 구조체의 적절 한 멤버를 설정 하 여 응답 해야 합니다.

트리 컨트롤 트리 컨트롤을 만드는 프로세스의 힙에서 할당 된 메모리를 사용 합니다. 트리 컨트롤에서 항목의 최대 수는 힙에서 사용 가능한 메모리 양을 기반으로 합니다. 각 항목에는 64 바이트를 사용합니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)

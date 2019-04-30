---
title: 메뉴, 컨트롤 막대 및 액셀러레이터 관리
ms.date: 11/04/2016
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
ms.openlocfilehash: 9a089829658265cd835a8c7344aa5bc45fbc109a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226172"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>메뉴, 컨트롤 막대 및 액셀러레이터 관리

프레임 창의 메뉴, 도구 모음 단추, 상태 표시줄 및 액셀러레이터를 포함 하 여 사용자 인터페이스 개체 업데이트를 관리 합니다. 또한 공유 MDI 응용 프로그램의 메뉴 모음을 관리 합니다.

## <a name="managing-menus"></a>관리 메뉴

프레임 창 사용자 인터페이스 항목에 설명 된 ON_UPDATE_COMMAND_UI 메커니즘을 사용 하 여 업데이트에 참여 [사용자 인터페이스 개체 업데이트 하는 방법](../mfc/how-to-update-user-interface-objects.md)합니다. 유휴 루프 중 도구 모음 및 기타 컨트롤 막대의 단추 업데이트 됩니다. 메뉴 모음에서 드롭다운 메뉴에서 메뉴 항목 메뉴가 드롭다운 직전에 업데이트 됩니다.

MDI 프레임 창은 MDI 응용 프로그램에 대 한 메뉴와 캡션이 관리합니다. MDI 프레임 창은 활성 MDI 자식 창이 없는 경우 메뉴 모음으로 사용 되는 하나의 기본 메뉴를 소유 합니다. 활성 자식 경우 MDI 프레임 창의 메뉴 모음 활성 MDI 자식 창에 대 한 메뉴를 통해 수행 됩니다. MDI 응용 프로그램 문서, 워크시트 및 차트 같은 여러 문서 유형을 지 원하는 경우 각 유형에 고유한 메뉴가 메뉴 모음에 배치 하 고 주 프레임 창의 캡션 변경 합니다.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI 응용 프로그램에 대 한 표시 되는 창 메뉴 표준 명령에 대 한 기본 구현을 제공 합니다. 특히, 새 프레임 창 및 현재 문서에서 보기를 만들려면 (ID_WINDOW_NEW) 새 창 명령을 구현 됩니다. 고급 사용자 지정 해야 하는 경우에 이러한 구현을 재정의 해야 합니다.

동일한 문서 유형의 여러 MDI 자식 창 메뉴 리소스를 공유 합니다. 여러 MDI 자식 창을 동일한 문서 템플릿에 의해 생성 되 면 이러한 모든 리소스를 사용할 수 동일한 메뉴, Windows 시스템 리소스에 저장 합니다.

## <a name="managing-the-status-bar"></a>상태 표시줄 관리

프레임 창도 해당 클라이언트 영역 내에서 상태 표시줄을 배치 하 고 상태 관리 표시줄의 표시기입니다. 프레임 창 및 필요에 따라 상태 표시줄 메시지 영역 업데이트 지우고에 설명 된 대로 프롬프트 문자열을 사용자가 도구 모음 단추 또는 메뉴 항목 표시 [상태 표시줄에 명령 정보 표시 방법](../mfc/how-to-display-command-information-in-the-status-bar.md)합니다.

## <a name="managing-accelerators"></a>액셀러레이터 키 관리

각 프레임 창에는 액셀러레이터 번역을 자동으로 키보드에 선택적 액셀러레이터 키 테이블 유지 관리 합니다. 이 메커니즘은 쉽게 메뉴 명령을 호출 하는 액셀러레이터 키 (바로 가기 키 라고도 함)을 정의할 수 있습니다.

## <a name="see-also"></a>참고자료

[프레임 창 사용](../mfc/using-frame-windows.md)

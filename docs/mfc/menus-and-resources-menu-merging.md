---
title: '메뉴 및 리소스: 메뉴 병합'
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
ms.openlocfilehash: e00464e59de5e20627fd2423c101c23629d7c4d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225541"
---
# <a name="menus-and-resources-menu-merging"></a>메뉴 및 리소스: 메뉴 병합

이 문서에서는 OLE 문서 응용 프로그램에서 내부 활성화 제대로 비주얼 편집을 처리 하는 데 필요한 단계를 자세히 설명 합니다. 내부 활성화 (구성 요소) 응용 프로그램 컨테이너와 서버 모두에 대 한 문제를 제기 합니다. 사용자 (컨테이너 문서의 컨텍스트) 내에서 동일한 프레임 창에 남아 있지만 다른 응용 프로그램 (서버)를 실제로 실행 됩니다. 컨테이너 및 서버 응용 프로그램의 리소스 간의 조정이 필요합니다.

이 문서에서 다루는 항목은 다음과 같습니다.

- [메뉴 레이아웃](#_core_menu_layouts)

- [도구 모음 및 상태 표시줄](#_core_toolbars_and_status_bars)

##  <a name="_core_menu_layouts"></a> 메뉴 레이아웃

첫 번째 단계는 메뉴 레이아웃을 조정 하는 것입니다. 자세한 내용은 참조는 **메뉴 만들기** 섹션 [메뉴 프로그래밍 고려 사항](https://msdn.microsoft.com/library/ms647557.aspx) Windows SDK의 합니다.

컨테이너 응용 프로그램 내부에서 포함 된 항목은 활성화 하는 경우에 사용할 새 메뉴를 만들어야 합니다. 최소한이 메뉴 나열 된 순서로 다음을 구성 되어야 합니다.

1. 파일 메뉴에 파일이 열려 있는 경우 사용 하는 것과 동일 합니다. (일반적으로 다른 메뉴 항목이 사항이 다음 항목 앞.)

1. 두 개의 연속 된 구분 기호입니다.

1. 파일이 열린 경우 사용 된 것과 동일한 창 메뉴 (경우에만 MDI 응용 프로그램에서 컨테이너 응용 프로그램). 일부 응용 프로그램에 포함 된 항목 위치에서 활성화 될 때 메뉴에 유지 되는이 그룹에 속하는 다른 메뉴, 옵션 메뉴와 같은 있을 수 있습니다.

    > [!NOTE]
    >  확대/축소와 같은 컨테이너 문서의 뷰에 영향을 미치는 다른 메뉴가 있을 수 있습니다. 이러한 컨테이너 메뉴가 메뉴 리소스에서 두 개의 구분 기호 사이 나타납니다.

서버 (구성 요소) 응용 프로그램에는 또한 내부 활성화에 맞게 새 메뉴를 만들어야 합니다. 파일 및 데이터 대신 서버 문서를 조작 하는 창과 같은 메뉴 항목을 하지 않고 파일을 열 때 사용 되는 메뉴와 같은 것이 있어야 합니다. 일반적으로 다음으로 구성이 됩니다.

1. 편집 메뉴 파일이 열린 경우 사용 하는 것과 동일 합니다.

1. 구분선입니다.

1. Scribble 샘플 응용 프로그램에 펜 메뉴 등 메뉴 편집 개체입니다.

1. 구분선입니다.

1. 도움말 메뉴입니다.

예를 들어, 컨테이너 및 서버에 대 한 일부 샘플 전체 메뉴의 레이아웃을 살펴봅니다. 예제를 명확 하 게 하려면 각 메뉴 항목의 세부 정보 제거 되었습니다. 컨테이너의 전체 메뉴에는 다음 항목에 있습니다.

```
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&File C1"
    MENUITEM SEPARATOR
    POPUP "&Zoom C2"
    MENUITEM SEPARATOR
    POPUP "&Options C3"
    POPUP "&Window C3"
END
```

연속 된 구분 기호 서버의 메뉴의 첫 번째 부분 어디로 나타냅니다. 이제 서버의 전체 메뉴에 표시 됩니다.

```
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&Edit S1"
    MENUITEM SEPARATOR
    POPUP "&Format S2"
    MENUITEM SEPARATOR
    POPUP "&Help S3"
END
```

여기에서 구분 기호 컨테이너 메뉴 항목의 두 번째 그룹은 어디에 나타냅니다. 이 컨테이너 내부에서이 서버에서 개체 활성화 되 면 결과 메뉴 구조는 다음과 같습니다.

```
BEGIN
    POPUP "&File C1"
    POPUP "&Edit S1"
    POPUP "&Zoom C2"
    POPUP "&Format S2"
    POPUP "&Options C3
    POPUP "&Window C3"
    POPUP "&Help S3"
END
```

알 수 있듯이 각 응용 프로그램의 메뉴의 다른 그룹과 구분 기호 대체 되었습니다.

액셀러레이터 키 테이블에서 전체 메뉴와 연결 된 서버 응용 프로그램에서 제공 되어야 합니다. 컨테이너는 고유한 액셀러레이터 키 테이블을 통합 하 여 합니다.

포함 된 항목의 현재 위치 활성화 되 면 프레임 워크 내부 메뉴를 로드 합니다. 서버 응용 프로그램에 내부 활성화를 요청 하 고 구분 기호가 있는 삽입 합니다. 메뉴를 결합 하는 방법입니다. 메뉴 컨테이너에서 파일 및 창 배치에 대해 작업 하 고 항목에서 작동 하는 것에 대 한 서버에서 메뉴를 얻게 됩니다.

##  <a name="_core_toolbars_and_status_bars"></a> 도구 모음 및 상태 표시줄

서버 응용 프로그램 도구 모음을 새로 만들고 해당 비트맵 별도 파일에 저장 해야 합니다. 이 비트맵 ITOOLBAR 라는 파일에 저장 하는 응용 프로그램 마법사에서 생성 된 응용 프로그램입니다. BMP 합니다. 새 도구 모음을 서버 항목 내부에서 활성화 될 해야에 일반 도구 모음과 동일한 항목을 포함 하며 파일과 창 메뉴에 항목을 나타내는 아이콘 제거 될 때 컨테이너 응용 프로그램의 도구 모음을 바꿉니다.

이 도구 모음에서 로드 되 여 `COleIPFrameWnd`-응용 프로그램 마법사에서 만든 클래스를 파생 합니다. 상태 표시줄 컨테이너 응용 프로그램에서 처리 됩니다. 내부 프레임 창 구현에 대 한 자세한 내용은 참조 하세요. [서버: 서버 구현](../mfc/servers-implementing-a-server.md)합니다.

## <a name="see-also"></a>참고자료

[메뉴 및 리소스(OLE)](../mfc/menus-and-resources-ole.md)<br/>
[활성화](../mfc/activation-cpp.md)<br/>
[서버](../mfc/servers.md)<br/>
[컨테이너](../mfc/containers.md)

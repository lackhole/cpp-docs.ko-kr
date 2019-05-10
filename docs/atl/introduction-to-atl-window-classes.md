---
title: ATL 창 클래스 소개
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 0c3bc70b5edfb089a6276003625b876d8c553dcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250482"
---
# <a name="introduction-to-atl-window-classes"></a>ATL 창 클래스 소개

ATL 클래스는 구현 하 고 windows를 조작 하도록 설계 되었습니다.

- [CWindow](../atl/reference/cwindow-class.md) 에 대 한 창 핸들에 연결할 수 있도록 합니다 `CWindow` 개체입니다. 호출 하 여 `CWindow` 창을 조작 하는 메서드.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) 새 창을 구현 및 메시지 맵 사용 하 여 메시지를 처리할 수 있습니다. 만들 수 있습니다 새 Windows 클래스, 기존 클래스를 슈퍼 클래스 또는 서브 클래스에 따라 창을 기존 창입니다.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) 모달 또는 모덜리스 대화 상자 및 프로세스 메시지 메시지 맵 사용 하 여 구현할 수 있습니다.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) 다른 클래스에 있는 메시지 맵이 포함 된 창을 구현 하는 미리 작성 된 클래스입니다. 사용 하 여 `CContainedWindowT` 하나의 클래스에서 메시지 처리를 중앙 집중화할 수 있습니다.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX 컨트롤을 호스트 하는 대화 상자 (모달 또는 모덜리스)를 구현할 수 있습니다.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) 기본 기능을 사용 하 여 모달 대화 상자를 구현할 수 있습니다.

- [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX 컨트롤을 호스팅하는 창의 구현할 수 있습니다.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) 사용이 허가 된 ActiveX 컨트롤을 호스팅하는 창의 구현할 수 있습니다.

특정 창 클래스 외에도 ATL ATL 창 개체의 구현을 쉽게 수행할 수 있도록 설계 된 여러 클래스를 제공 합니다. 그 차이점은 다음과 같습니다.

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 새 창 클래스의 정보를 관리 합니다.

- [CWinTraits](../atl/reference/cwintraits-class.md) 하 고 [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) ATL 창 개체의 특성을 표준화 하는 간단한 방법을 제공 합니다.

## <a name="see-also"></a>참고자료

[창 클래스](../atl/atl-window-classes.md)

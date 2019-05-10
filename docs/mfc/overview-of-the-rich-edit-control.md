---
title: Rich Edit 컨트롤의 개요
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: c45cb638ec860bb803c7de32065606dc3cc176b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160174"
---
# <a name="overview-of-the-rich-edit-control"></a>Rich Edit 컨트롤의 개요

> [!IMPORTANT]
>  Rich edit 컨트롤을 사용 하는 대화 상자에서 하는 경우 (응용 프로그램의 SDI와 MDI, 인지에 관계 없이 또는 대화 상자 기반)를 호출 해야 합니다 [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) 대화 상자가 표시 되 면 합니다. 이 함수를 호출 하는 일반적인 위치는 프로그램의 `InitInstance` 멤버 함수입니다. 처음에만 대화 상자를 표시할 때마다 호출할 필요가 없습니다. 호출할 필요가 없습니다 `AfxInitRichEdit` 작업할 경우 `CRichEditView`합니다.

Rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 텍스트 서식 지정에 대 한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 서식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다. 즉, 풍부한 편집 선택한 텍스트의 문자 또는 단락 특성을 변경 하는 컨트롤 지원 합니다. 몇 가지 예가 문자 특성은 굵게, 기울임꼴, 글꼴 패밀리 및 글꼴 크기. 단락 특성의 예로 맞춤, 여백 및 탭 정지를 들 수 있습니다. 그러나 이며 사용자 인터페이스를 제공할 수 있습니다 최대 도구 모음 단추, 메뉴 항목 또는 서식 문자 대화 상자 현재 선택 항목의 특성에 대 한 서식 있는 편집 컨트롤을 쿼리 하는 함수가 있습니다. 이러한 함수를 사용 특성의 현재 설정을 표시 하려면 예를 들어, 선택 영역에 굵은 문자 서식을 특성 명령 UI에서 확인 표시를 설정 합니다.

문자 및 단락 서식 지정에 대 한 자세한 내용은 참조 하세요. [문자 서식을](../mfc/character-formatting-in-rich-edit-controls.md) 하 고 [단락 서식이](../mfc/paragraph-formatting-in-rich-edit-controls.md) 이 항목의 뒷부분에 나오는.

서식 있는 편집 작업 및 여러 줄 편집 컨트롤을 사용 하는 알림 메시지의 거의 모든 컨트롤 지원 합니다. 따라서 응용 프로그램을 이미 사용 하 여 편집 컨트롤 변경 될 수 있음을 쉽게 다양 한을 사용 하는 컨트롤을 편집 합니다. 추가 메시지 및 알림 기능 고유 rich edit 컨트롤에 액세스 하려면 응용 프로그램을 사용 하도록 설정 합니다. 편집 컨트롤에 대 한 자세한 내용은 [CEdit](../mfc/reference/cedit-class.md)합니다.

알림에 대 한 자세한 내용은 참조 하세요. [서식 있는 편집 컨트롤에서 알림](../mfc/notifications-from-a-rich-edit-control.md) 이 항목의에서 뒷부분에 있습니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)

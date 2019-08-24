---
title: 출력(디바이스 컨텍스트) 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.output
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
ms.openlocfilehash: 1d76570e7bfd4ce587b3803235394ec5406d30b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410202"
---
# <a name="output-device-context-classes"></a>출력(디바이스 컨텍스트) 클래스

이러한 클래스는 다양 한 유형의 Windows에서 사용할 수 있는 장치 컨텍스트를 캡슐화합니다.

다음 클래스는 대부분 Windows 장치 컨텍스트에 대 한 핸들을 캡슐화합니다. 장치 컨텍스트에 화면 또는 프린터와 같은 장치 그리기 특성에 대 한 정보를 포함 하는 Windows 개체입니다. 모든 그리기 호출은 디바이스 컨텍스트 개체를 통해 수행 됩니다. 추가 클래스에서 파생 된 `CDC` Windows 메타 파일에 대 한 지원을 비롯 하 여 특수화 된 디바이스 컨텍스트 기능을 캡슐화 합니다.

[CDC](../mfc/reference/cdc-class.md)<br/>
장치 컨텍스트에 대 한 기본 클래스입니다. 전체 표시에 액세스 하 고 프린터 같은 nondisplay 컨텍스트에 액세스 하기 위한 직접 사용 합니다.

[CPaintDC](../mfc/reference/cpaintdc-class.md)<br/>
에 사용 되는 디스플레이 컨텍스트 `OnPaint` windows의 멤버 함수입니다. 자동으로 호출 `BeginPaint` 생성 시 및 `EndPaint` 소멸 합니다.

[CClientDC](../mfc/reference/cclientdc-class.md)<br/>
창의 클라이언트 영역에 대 한 디스플레이 컨텍스트. 사용 예를 들어 마우스 이벤트에 대 한 즉각적인 응답에 그릴 수 있습니다.

[CWindowDC](../mfc/reference/cwindowdc-class.md)<br/>
클라이언트 및 비클라이언트 영역을 포함 한 전체 windows에 대 한 디스플레이 컨텍스트.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md)<br/>
Windows 메타 파일에 대 한 디바이스 컨텍스트입니다. Windows 메타 파일 이미지를 만드는 재생할 수 있는 그래픽 장치 GDI (인터페이스) 명령 시퀀스를 포함 합니다. 멤버 함수에 대 한 호출을 `CMetaFileDC` 메타 파일에 기록 됩니다.

## <a name="related-classes"></a>관련된 클래스

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
좌표(x, y) 쌍을 저장합니다.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
거리, 상대 위치 또는 쌍으로 이뤄진 값을 저장합니다.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
사각형 영역의 좌표를 저장합니다.

[CRgn](../mfc/reference/crgn-class.md)<br/>
타원형, 다각형, 또는 불규칙 한 영역 창 내에서 조작에 대 한 GDI 영역을 캡슐화 합니다. 클래스의 클리핑 멤버 함수와 함께 사용 `CDC`합니다.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
표시 하 고 사각형 개체를 이동 및 크기 조정에 대 한 사용자 인터페이스를 처리 합니다.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
색을 선택 하기 위한 표준 대화 상자를 제공 합니다.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
글꼴 선택 하기 위한 표준 대화 상자를 제공 합니다.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
파일 인쇄를 위한 표준 대화 상자를 제공 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)

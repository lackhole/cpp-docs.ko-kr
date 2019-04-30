---
title: OLE 일반 대화 상자 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
ms.openlocfilehash: d34c141fc9a2b53eab6a4c0b0ce1799ff5243d84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186394"
---
# <a name="ole-common-dialog-classes"></a>OLE 일반 대화 상자 클래스

이러한 클래스는 다양 한 표준 OLE 대화 상자를 구현 하 여 일반적인 OLE 작업을 처리 합니다. 또한 OLE 기능에 대 한 일관 된 사용자 인터페이스를 제공합니다.

[COleDialog](../mfc/reference/coledialog-class.md)<br/>
모든 OLE 대화 상자에 대 한 일반적인 구현을 포함 하는 프레임 워크에서 사용 합니다. 사용자 인터페이스 범주에 있는 모든 대화 상자 클래스는이 기본 클래스에서 파생 됩니다. `COleDialog` 직접 사용할 수 없습니다.

[COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)<br/>
연결 된 새 OLE를 삽입 하거나 항목을 포함 하면 표준 사용자 인터페이스 개체 삽입 대화 상자를 표시 합니다.

[COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)<br/>
편집 하 여 붙여넣기 명령 구현에 대 한 표준 사용자 인터페이스를 선택 하 여 붙여넣기 대화 상자를 표시 합니다.

[COleLinksDialog](../mfc/reference/colelinksdialog-class.md)<br/>
연결 된 항목에 대 한 정보를 수정 하기 위한 표준 사용자 인터페이스를 링크 편집 대화 상자를 표시 합니다.

[COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)<br/>
아이콘 변경 대화 상자, 포함 된 OLE와 사용 하 여 연결 된 아이콘을 변경 하거나 링크 된 항목에 대 한 표준 사용자 인터페이스를 표시 합니다.

[COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)<br/>
변환 대화 상자 OLE 항목을 다른 형식 간에 변환 하는 것에 대 한 표준 사용자 인터페이스를 표시 합니다.

[COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)<br/>
Windows 공용 OLE 속성 대화 상자를 캡슐화합니다. 일반 OLE 속성 대화 상자 표시 Windows 표준에 부합 하는 방식에서 OLE 문서 항목의 속성을 수정 하는 쉬운 방법을 제공 합니다.

[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)<br/>
문서에서 모든 링크를 업데이트 하기 위한 표준 사용자 인터페이스 업데이트 대화 상자를 표시 합니다. 대화 상자를 표시 하려면 얼마나 근접 업데이트 절차가 완료 진행률 표시기를 포함 합니다.

[COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)<br/>
링크의 원본 또는 대상 변경에 대 한 표준 사용자 인터페이스 소스 변경 대화 상자를 표시 합니다.

[COleBusyDialog](../mfc/reference/colebusydialog-class.md)<br/>
서버 작업 중이 고 서버가 응답 하지 대화 상자를 사용 중인 응용 프로그램에 대 한 호출을 처리 하기 위한 표준 사용자 인터페이스를 표시 합니다. 일반적으로 자동으로 표시 되는 `COleMessageFilter` 구현 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)

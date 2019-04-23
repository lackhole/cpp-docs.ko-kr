---
title: OLE의 대화 상자
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
ms.openlocfilehash: fa3d87e2cc17e297c3e6387920c6d527d8ddbe39
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767654"
---
# <a name="dialog-boxes-in-ole"></a>OLE의 대화 상자

사용자가 OLE 지원 응용 프로그램을 실행 하는 동안 응용 프로그램에서 사용자 정보를에서 작업을 수행 하기 위해 필요한 시간이 있습니다. MFC OLE 클래스는 다양 한 필요한 정보를 수집 하려면 대화 상자를 제공 합니다. 이 항목에서는 OLE 대화 상자에서 처리 하는 작업 및 해당 대화 상자를 표시 하는 데 필요한 클래스를 나열 합니다. OLE 대화 상자 및 해당 동작을 사용자 지정 하는 데 사용 되는 구조에 대 한 세부 정보를 참조 하세요 [MFC 참조](../mfc/mfc-desktop-applications.md)합니다.

*개체를 삽입 합니다.*<br/>
이 대화 상자 복합 문서에 사용자가 새로 만든 삽입 하거나 기존 개체를 허용 합니다. 또한 아이콘으로 항목을 표시 하도록 선택할 수 있도록 하 고 아이콘 변경 명령 단추를 활성화 합니다. 편집 메뉴에서 개체 삽입을 선택 하면이 대화 상자를 표시 합니다. 사용 된 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md) 이 대화 상자를 표시 하는 클래스입니다. 참고 MDI 응용 프로그램 자체에 삽입할 수 있습니다. SDI 응용 프로그램 아닌 컨테이너/서버 응용 프로그램 자체에 삽입할 수 없습니다.

*붙여넣기*<br/>
이 대화 상자에 사용자를가 복합 문서에 데이터를 붙여 넣을 때 사용 하는 형식을 제어할 수 있습니다. 데이터의 형식을 포함 하거나 데이터를 연결할 것인지 및 아이콘으로 표시할지 여부를 선택할 수 있습니다. 편집 메뉴에서 선택 하 여 붙여넣기 선택 하면이 대화 상자를 표시 합니다. 사용 된 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) 이 대화 상자를 표시 하는 클래스입니다.

*아이콘 변경*<br/>
이 대화 상자를 사용 하면 연결 되거나 포함 된 항목을 나타내는 아이콘은 표시를 선택 합니다. 사용자 편집 메뉴에서 변경 아이콘을 선택 하거나 선택 하 여 붙여넣기 또는 변환 대화 상자에서 변경 아이콘 단추를 선택 하면이 대화 상자를 표시 합니다. 또한 표시를 사용자 개체 삽입 대화 상자를 열고 아이콘으로 표시를 선택 합니다. 사용 된 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md) 이 대화 상자를 표시 하는 클래스입니다.

*변환*<br/>
이 대화 상자에 사용자를가 포함 되거나 연결 된 항목의 유형을 변경할 수 있습니다. 예를 들어, 복합 문서에는 메타 파일을 포함 하 고 나중에 다른 응용 프로그램을 사용 하 여 포함 된 메타 파일을 수정 하려면 변환 대화 상자를 사용할 수 있습니다. 이 대화 상자를 클릭 하 여 일반적으로 표시 됩니다 *항목 유형을* 개체 편집 메뉴에서 선택한 다음, 계단식 메뉴에서 변환을 클릭 하 합니다. 사용 된 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) 이 대화 상자를 표시 하는 클래스입니다. 예를 들어 MFC OLE 샘플을 실행 [OCLIENT](../overview/visual-cpp-samples.md)합니다.

*편집 링크 또는 업데이트 링크*<br/>
링크 편집 대화 상자에 사용자를가 연결된 된 개체의 원본에 대 한 정보를 변경할 수 있습니다. 업데이트 연결 대화 상자에서 현재 대화 상자에서 연결 된 모든 항목의 원본을 확인 하 고 필요한 경우 연결 편집 대화 상자를 표시 합니다. 편집 메뉴에서 링크를 선택 하면 링크 편집 대화 상자를 표시 합니다. 연결 업데이트 대화 상자는 일반적으로 복합 문서를 처음으로 열릴 때 표시 됩니다. 하나를 사용 합니다 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) 또는 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md) 클래스를 표시 하려면 어떤 대화 상자에 따라 합니다.

*서버 작업 중 또는 서버가 응답 하지 않음*<br/>
서버 작업 중 대화 상자는 사용자가 항목을 활성화 하려고 하 고 서버를 현재 요청을 처리, 일반적으로 서버가 이므로 다른 사용자에 의해 사용 또는 작업 수 없는 경우에 표시 됩니다. 서버 정품 인증 요청에 전혀 응답 하지 않으면 서버가 응답 하지 대화 상자가 표시 됩니다. 이러한 대화 상자를 통해 표시 됩니다 `COleMessageFilter`OLE 인터페이스의 구현에 따라 `IMessageFilter`, 사용자를 활성화 요청을 다시 시도할지 여부를 결정할 수 있습니다. 사용 된 [COleBusyDialog](../mfc/reference/colebusydialog-class.md) 이 대화 상자를 표시 하는 클래스입니다.

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE](../mfc/ole-in-mfc.md)

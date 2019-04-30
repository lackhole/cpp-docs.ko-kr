---
title: 대화 상자 구현
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 1a3084d4655e173234d3bb6e8d411b28e8968377
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198055"
---
# <a name="implementing-a-dialog-box"></a>대화 상자 구현

ATL 프로젝트 대화 상자를 추가 하는 방법은 두 가지: ATL 대화 상자 마법사를 사용 하거나 수동으로 추가 합니다.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL 대화 상자 마법사를 사용 하 여 대화 상자 추가

에 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md), ATL 대화 상자 개체 ATL 프로젝트에 추가 대화 상자를 선택 합니다. ATL 대화 상자 마법사 적절 하 게 입력 하 고 클릭 **완료**합니다. 파생 된 클래스를 추가 하는 마법사 [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) 프로젝트입니다. 엽니다 **리소스 뷰** 에서 합니다 **보기** 메뉴 대화 상자를 찾아 두 번 클릭 하 여 리소스 편집기에서 엽니다.

> [!NOTE]
>  대화 상자에서 파생 된 경우 `CAxDialogImpl`, 모두 ActiveX 호스트할 수 및 Windows를 제어 합니다. 사용 하 여 대화 상자 클래스에서 ActiveX 컨트롤 지원이 오버 헤드를 않으려면 [CSimpleDialog](../atl/reference/csimpledialog-class.md) 하거나 [CDialogImpl](../atl/reference/cdialogimpl-class.md) 대신 합니다.

클래스 뷰에서 대화 상자 클래스 메시지 및 이벤트 처리기를 추가할 수 있습니다. 자세한 내용은 [ATL 메시지 처리기 추가](../atl/adding-an-atl-message-handler.md)합니다.

## <a name="adding-a-dialog-box-manually"></a>대화 상자를 수동으로 추가

대화 상자를 구현 하는 것은 창을 구현 하는 것과 비슷합니다. 클래스를 파생 [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md), 또는 [CSimpleDialog](../atl/reference/csimpledialog-class.md) 선언 및를 [메시지 맵을](../atl/message-maps-atl.md) 메시지를 처리 하 합니다. 그러나 파생된 클래스에서 대화 상자 템플릿 리소스 ID도 지정 해야 합니다. 클래스 라는 데이터 멤버가 있어야 합니다. `IDD` 에이 값을 보유 합니다.

> [!NOTE]
>  ATL 대화 상자 마법사를 사용 하 여 대화 상자를 만들려면 마법사를 자동으로 추가 합니다 `IDD` 멤버를 **열거형** 형식.

`CDialogImpl` 모달 또는 Windows 컨트롤을 호스트 하는 모덜리스 대화 상자를 구현할 수 있습니다. `CAxDialogImpl` 모달 또는 Windows와 ActiveX 컨트롤을 호스트 하는 모덜리스 대화 상자를 구현할 수 있습니다.

모달 대화 상자를 만들려면의 인스턴스를 만들 사용자 `CDialogImpl`-파생 (또는 `CAxDialogImpl`-파생) 클래스 하 고 호출 하는 [DoModal](../atl/reference/cdialogimpl-class.md#domodal) 메서드. 모달 대화 상자를 닫으려면 호출을 [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) 메시지 처리기에서 메서드. 모덜리스 대화 상자를 만들려면 다음을 호출 합니다 [Create](../atl/reference/cdialogimpl-class.md#create) 메서드 대신 `DoModal`합니다. 모덜리스 대화 상자를 삭제 하려면 호출 [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow)합니다.

자동으로 수행 됩니다 이벤트를 싱크하기 [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)합니다. 처리기와 마찬가지로 대화 상자의 메시지 처리기를 구현 된 `CWindowImpl`-클래스를 파생 합니다. 메시지 관련 반환 값의 경우로 서 반환을 `LRESULT`입니다. 반환 된 `LRESULT` Windows 대화 상자 관리자가 올바르게 처리 하기 위해 ATL 매핑된 값입니다. 세부 정보에 대 한 소스 코드를 참조 하세요 [CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) atlwin.h에 있습니다.

## <a name="example"></a>예제

다음 클래스는 대화 상자를 구현합니다.

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>참고자료

[창 클래스](../atl/atl-window-classes.md)

---
title: ATL 대화 상자를 추가합니다.
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
ms.openlocfilehash: ebbb610debe5d480cd1161149f89c4d357f9cd02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261607"
---
# <a name="adding-an-atl-dialog-box"></a>ATL 대화 상자를 추가합니다.

ATL 대화 상자에 프로젝트를 추가 하려면 프로젝트에 ATL 프로젝트 또는 ATL 지원을 포함 하는 MFC 프로젝트 중 하나 여야 합니다. [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 애플리케이션을 만들거나 [MFC 애플리케이션에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 애플리케이션용 ATL 지원을 구현할 수 있습니다.

기본적으로 ATL 대화 상자 마법사에서 파생 된 대화 상자를 구현 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)합니다. 이 클래스에는 Windows 및 ActiveX 컨트롤을 호스팅하기 위한 지원이 포함 됩니다. ActiveX 컨트롤 지원이 오버 헤드는 마법사가 코드를 생성 하는 면에 하지 않을 수 있습니다, 경우 바꾸려면 `CAxDialogImpl` 중 하나를 사용 하 여 [CSimpleDialog](../../atl/reference/csimpledialog-class.md) 하거나 [CDialogImpl](../../atl/reference/cdialogimpl-class.md) 기본 클래스로 .

> [!NOTE]
> `CSimpleDialog` 만 Windows 공용 컨트롤을 지 원하는 모달 대화 상자만 만듭니다. `CDialogImpl` 모달 또는 모덜리스 대화 상자 중 하나를 만듭니다.

## <a name="to-add-an-atl-dialog-resource-to-your-project"></a>ATL 대화 상자 리소스를 프로젝트에 추가 하려면

1. 사용 하 여 ATL 프로젝트 만들기를 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)합니다.

1. [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code), 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가** 바로 가기 메뉴에서. 클릭 **클래스 추가**합니다.

1. 에 **템플릿** 창 합니다 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자에서 클릭 **ATL 대화 상자**합니다. 클릭 **엽니다** 표시할 합니다 [ATL 대화 상자 마법사](../../atl/reference/atl-dialog-wizard.md)합니다.

자세한 내용은 [대화 상자 구현](../../atl/implementing-a-dialog-box.md)합니다.

## <a name="see-also"></a>참고자료

[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[창 클래스](../../atl/atl-window-classes.md)<br/>
[메시지 맵](../../atl/message-maps-atl.md)

---
title: ATL 대화 상자 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
ms.openlocfilehash: 043c170021ce1ceb072dba3e5a450375f556753a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248852"
---
# <a name="atl-dialog-wizard"></a>ATL 대화 상자 마법사

이 마법사에서 파생 된 ATL 대화 상자 개체를 프로젝트에 삽입 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)합니다. 대화 상자에서 파생 된 `CAxDialogImpl` ActiveX 컨트롤을 호스트할 수 있습니다.

기본값을 사용 하 여 대화 상자 리소스를 만듭니다 **확인** 하 고 **취소** 단추입니다. 대화 상자 리소스 편집 하 고 사용 하 여 ActiveX 컨트롤을 추가 합니다 [대화 상자 편집기](../../windows/dialog-editor.md) 리소스 뷰에서 합니다.

헤더 파일에 삽입 하는 마법사를 [메시지 맵을](../../atl/message-maps-atl.md) 기본값 처리에 대 한 선언을 이벤트를 클릭 합니다. 참조 [대화 상자 구현](../../atl/implementing-a-dialog-box.md) ATL 대화 상자에 대 한 자세한 내용은 합니다.

- **짧은 이름**

   ATL 대화 상자 개체에 대 한 약식된 이름을 설정합니다. 사용자가 제공한 이름을 개별적으로 해당 필드를 변경 하지 않는 한 클래스 이름 및 파일 (.cpp 파일과.h) 이름이 결정 합니다.

- **클래스**

   만들 클래스의 이름을 설정 합니다. 이 이름은 기반에 제공한 이름으로 **약식 이름**클래스 이름에 대 한 일반적인 접두사 'C'가 뒤에서 합니다.

- **.h 파일**

   새 개체 클래스에 대한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에 제공한 이름에 기반 **약식 이름**합니다. 파일 이름을 선택한 위치에 저장하거나 클래스 선언을 기존 파일에 추가하려면 줄임표 단추를 클릭합니다. 기존 파일을 선택하면 마법사에서 **마침**을 클릭해야 해당 파일이 선택한 위치에 저장됩니다.

   마법사는 파일을 덮어쓰지 않습니다. 기존 파일의 이름을 선택하면 마법사에서 **마침**을 클릭할 때 클래스 선언을 파일의 내용에 추가해야 하는지 여부를 나타내는 메시지가 표시됩니다. **예**를 클릭하여 파일을 추가하거나, **아니요**를 클릭하여 마법사로 돌아가서 다른 파일 이름을 지정합니다.

- **.cpp 파일**

   새 개체의 클래스에 대한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에 제공한 이름에 기반 **약식 이름**합니다. 파일 이름을 선택한 위치에 저장하려면 줄임표 단추를 클릭합니다. 마법사에서 **마침**을 클릭해야 해당 파일이 선택한 위치에 저장됩니다.

   마법사는 파일을 덮어쓰지 않습니다. 기존 파일의 이름을 선택하면 마법사에서 **마침**을 클릭할 때 클래스 구현을 파일의 내용에 추가해야 하는지 여부를 나타내는 메시지가 표시됩니다. **예**를 클릭하여 파일을 추가하거나, **아니요**를 클릭하여 마법사로 돌아가서 다른 파일 이름을 지정합니다.

## <a name="see-also"></a>참고자료

[ATL 대화 상자](../../atl/reference/adding-an-atl-dialog-box.md)

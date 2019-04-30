---
title: 수동으로 컨트롤 추가
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
ms.openlocfilehash: c70539b49fcf2aa87f0bee375a87b38277b6ed42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394808"
---
# <a name="adding-controls-by-hand"></a>수동으로 컨트롤 추가

수 있습니다 [대화 상자 편집기를 사용 하 여 대화 상자에 컨트롤 추가](../mfc/using-the-dialog-editor-to-add-controls.md) 하거나 코드를 사용 하 여 사용자가 직접 추가 합니다.

컨트롤 개체를 직접 만들려면 하면 일반적으로 포함 됩니다는 C++ 에서 컨트롤 개체를 C++ 대화 상자 또는 프레임 창 개체입니다. 프레임 워크의 다른 많은 개체와 같은 컨트롤에는 2 단계 생성이 필요합니다. 컨트롤의 호출 해야 **만들기** 부모 대화 상자 또는 프레임 창 만들기의 일환으로 멤버 함수입니다. 대화 상자에 대 한 일반적으로 이루어지는 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 및 프레임 창에서 [OnCreate](../mfc/reference/cwnd-class.md#oncreate)합니다.

다음 예제에서는 어떻게 선언할 수 있습니다는 `CEdit` 파생된 대화 상자 클래스의 클래스 선언에서 개체를 호출 합니다 `Create` 멤버 함수 `OnInitDialog`합니다. 때문에 합니다 `CEdit` 개체가 포함 된 개체로 선언 된, 대화 상자 개체를 생성 하지만 자체와 아직 초기화 해야 하는 경우 자동으로 생성 된 `Create` 멤버 함수입니다.

[!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]

다음 `OnInitDialog` 사각형을 설정으로 함수 호출 `Create` Windows 편집 컨트롤을 만들고 연결 하는 초기화 되지 않은 `CEdit` 개체입니다.

[!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]

편집 개체를 만든 후 하 여 설정할 수도 있습니다 입력된 포커스를 컨트롤에 호출 된 `SetFocus` 멤버 함수입니다. 0을 반환 하는 마지막으로, `OnInitDialog` 포커스를 설정 하면 표시 됩니다. 0이 아닌 값을 반환 하는 경우 대화 상자 관리자 대화 항목 목록에서 첫 번째 컨트롤 항목에 포커스를 설정 합니다. 대부분의 경우에서 대화 상자 편집기를 사용 하 여 사용자가 대화 상자에 컨트롤을 추가 해야 합니다.

## <a name="see-also"></a>참고자료

[컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)<br/>
[컨트롤](../mfc/controls-mfc.md)<br/>
[CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)

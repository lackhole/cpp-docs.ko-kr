---
title: 대화 상자 데이터 교환
ms.date: 11/19/2018
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
ms.openlocfilehash: 9a0199577ea46520c2eadc308812de8a1ce4b514
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "71685800"
---
# <a name="dialog-data-exchange"></a>대화 상자 데이터 교환

DDX 메커니즘을 사용 하는 경우 일반적으로 `OnInitDialog` 처리기 또는 대화 상자 생성자에서 대화 상자 개체의 멤버 변수에 대 한 초기 값을 설정 합니다. 대화 상자가 표시 되기 직전에 프레임 워크의 DDX 메커니즘은 멤버 변수의 값을 대화 상자의 컨트롤에 전송 합니다. 그러면 대화 상자 자체가 `DoModal` 또는 `Create`에 대 한 응답에 표시 될 때 표시 됩니다. @No__t_1에서 `OnInitDialog`의 기본 구현은 클래스 `CWnd`의 `UpdateData` 멤버 함수를 호출 하 여 대화 상자의 컨트롤을 초기화 합니다.

사용자가 확인 단추를 클릭 하거나 인수 **TRUE**를 사용 하 여 `UpdateData` 멤버 함수를 호출할 때마다 동일한 메커니즘에서 컨트롤의 값을 멤버 변수로 전송 합니다. 대화 상자 데이터 유효성 검사 메커니즘은 유효성 검사 규칙을 지정한 데이터 항목의 유효성을 검사 합니다.

다음 그림은 대화 상자 데이터 교환을 보여 줍니다.

![대화 상자 데이터 교환](../mfc/media/vc379d1.gif "대화 상자 데이터 교환") <br/>
대화 상자 데이터 교환

`UpdateData`은 전달 된 **BOOL** 매개 변수에서 지정한 대로 양방향으로 작동 합니다. Exchange를 수행 하기 위해 `UpdateData` `CDataExchange` 개체를 설정 하 고 `CDialog`의 `DoDataExchange` 멤버 함수에 대 한 대화 상자 클래스의 재정의를 호출 합니다. `DoDataExchange`는 `CDataExchange` 형식의 인수를 사용 합니다. @No__t_1에 전달 되는 `CDataExchange` 개체는 exchange의 방향으로 해당 정보를 정의 하는 exchange의 컨텍스트를 나타냅니다.

사용자가 (또는 코드 마법사)가 `DoDataExchange`를 재정의 하는 경우 데이터 멤버 (컨트롤) 당 하나의 DDX 함수 호출을 지정 합니다. 각 DDX 함수는 `UpdateData` 여 `DoDataExchange`에 전달 된 `CDataExchange` 인수로 제공 된 컨텍스트를 기반으로 양방향으로 데이터를 교환 하는 방법을 알고 있습니다.

MFC는 다양 한 종류의 exchange에 대해 다양 한 DDX 함수를 제공 합니다. 다음 예에서는 두 개의 DDX 함수와 하나의 DDV 함수를 호출 하는 `DoDataExchange` 재정의를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

@No__t_0 및 `DDV_` 줄은 데이터 맵입니다. 표시 되는 샘플 DDX 및 DDV 함수는 각각 확인란 컨트롤과 편집 상자 컨트롤에 대 한 것입니다.

사용자가 모달 대화 상자를 취소 하면 `OnCancel` 멤버 함수는 대화 상자를 종료 하 고 `DoModal` **IDCANCEL**값을 반환 합니다. 이 경우 대화 상자와 대화 상자 개체 간에 데이터가 교환 되지 않습니다.

## <a name="see-also"></a>참조

[대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)<br/>
[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[대화 상자 데이터 유효성 검사](../mfc/dialog-data-validation.md)

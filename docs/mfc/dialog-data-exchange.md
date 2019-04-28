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
ms.openlocfilehash: 338630aef358d9490461179288d5c45a2d3b821c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348801"
---
# <a name="dialog-data-exchange"></a>대화 상자 데이터 교환

DDX 메커니즘을 사용 하는 경우 대화 상자의 초기 값 개체의 멤버 변수를 설정 하면 일반적으로 프로그램 `OnInitDialog` 처리기 또는 대화 상자 생성자입니다. 프레임 워크의 DDX 메커니즘 표시 되는 위치 대화 상자에서 컨트롤에 멤버 변수의 값을 전송 하는 대화 상자가 표시 되기 전에 즉시를 대화 상자가 표시 되 면 자체에 대 한 응답 `DoModal` 또는 `Create`합니다. 기본 구현의 `OnInitDialog` 에서 `CDialog` 호출을 `UpdateData` 클래스의 멤버 함수 `CWnd` 대화 상자에서 컨트롤을 초기화 합니다.

동일한 메커니즘 값에서에서 전송 컨트롤 멤버 변수 확인 단추를 클릭할 때 (또는 호출 될 때마다 합니다 `UpdateData` 인수를 사용 하 여 멤버 함수 **TRUE**). 대화 상자 데이터 유효성 검사 메커니즘은 유효성 검사 규칙을 지정한 데이터 항목의 유효성을 검사 합니다.

다음 그림에서는 대화 상자 데이터 교환 합니다.

![대화 상자 데이터 교환](../mfc/media/vc379d1.gif "대화 상자 데이터 교환") <br/>
대화 상자 데이터 교환

`UpdateData` 지정 된 대로 양방향으로 작동 합니다 **BOOL** 매개 변수를 전달 합니다. 교환 수행 하 `UpdateData` 설정 된 `CDataExchange` 대화 상자 클래스의 개체 및 호출의 재정의 `CDialog`의 `DoDataExchange` 멤버 함수입니다. `DoDataExchange` 형식의 인수 `CDataExchange`합니다. 합니다 `CDataExchange` 에 전달 된 개체 `UpdateData` exchange의 방향으로 이러한 정보를 정의 exchange의 컨텍스트를 나타냅니다.

사용자 (또는 코드 마법사) 재정의 하는 경우 `DoDataExchange`, 데이터 멤버 (컨트롤) 당 하나의 DDX 함수에 대 한 호출을 지정 합니다. 각 DDX 함수 제공한 컨텍스트를 기반으로 양방향으로 데이터를 교환 하는 방법을 파악 합니다 `CDataExchange` 에 전달 된 인수에 `DoDataExchange` 하 여 `UpdateData`합니다.

MFC는 다양 한 종류의 exchange에 대 한 다양 한 DDX 함수를 제공합니다. 다음 예제와 `DoDataExchange` 재정의 두 DDX 함수 및 DDV 함수 라고 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

합니다 `DDX_` 고 `DDV_` 선은 데이터 맵. 표시 된 샘플 DDX 및 DDV 함수는 각각 확인란 컨트롤과 편집 상자 컨트롤에는입니다.

사용자가 모달 대화 상자를 취소 합니다 `OnCancel` 대화 상자를 종료 하는 멤버 함수 및 `DoModal` 값을 반환 합니다 **IDCANCEL**합니다. 이 경우 데이터가 없는 대화 상자 및 대화 상자 개체 간에 교환 됩니다.

## <a name="see-also"></a>참고자료

[대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[대화 상자 데이터 유효성 검사](../mfc/dialog-data-validation.md)

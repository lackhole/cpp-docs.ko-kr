---
title: 'MFC ActiveX 컨트롤: 스톡 메서드 추가'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: 29cb0d6f53d4e8fbbce12a83b2eecb8658c82697
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396394"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX 컨트롤: 스톡 메서드 추가

스톡 메서드가 달리 사용자 지정 메서드에서는 클래스에 의해 이미 구현 [COleControl](../mfc/reference/colecontrol-class.md)합니다. 예를 들어 `COleControl` 메서드를 지 원하는 새로 고침 컨트롤에 대 한 미리 정의 된 멤버 함수를 포함 합니다. 이 스톡 메서드가 디스패치 맵 항목은 DISP_STOCKFUNC_REFRESH 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

`COleControl` 두 주식 방법을 지원합니다. DoClick 및 새로 고침 합니다. 새로 고침을 즉시 컨트롤의 모양을;을 업데이트 하도록 컨트롤의 사용자가 호출할 컨트롤의 클릭 시키려면 DoClick가 호출 하는 이벤트입니다.

|메서드|디스패치 맵 항목|주석|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK( )**|클릭 이벤트를 발생 시킵니다.|
|`Refresh`|**DISP_STOCKPROP_REFRESH( )**|컨트롤의 모양을 즉시 업데이트 됩니다.|

##  <a name="_core_adding_a_stock_method_using_classwizard"></a> 추가 스톡 메서드가 수행 하는 메서드 추가 마법사

간단 스톡 메서드 추가 사용 하는 [메서드 추가 마법사](../ide/add-method-wizard.md)합니다. 다음 절차는 MFC ActiveX 컨트롤 마법사를 사용 하 여 만든 컨트롤에 새로 고침 메서드를 추가 하는 방법을 보여 줍니다.

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>메서드 추가 마법사를 사용 하 여 주식 Refresh 메서드를 추가 하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **메서드 추가**합니다.

   이 메서드 추가 마법사를 엽니다.

1. 에 **메서드 이름** 상자를 클릭 합니다 **새로 고침**합니다.

1. **마침**을 클릭합니다.

##  <a name="_core_classwizard_changes_for_stock_methods"></a> 스톡 메서드 추가 마법사 변경 메서드

주식 새로 고침 메서드는 컨트롤의 기본 클래스에서 지원 되므로 합니다 **메서드 추가 마법사** 컨트롤의 클래스 선언에는 전혀 변경 되지 않습니다. 컨트롤의 디스패치 맵에 및 메서드에 대 한 항목을 추가 하 고 해당 합니다. IDL 파일입니다. 다음 줄 구현 되는 컨트롤의 디스패치 맵에 추가 됩니다 (합니다. Cpp) 됩니다.

[!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

이렇게 하면 컨트롤의 사용자에 게 사용할 수 있는 새로 고침 메서드가 있습니다.

다음 줄은 컨트롤에 추가 됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

이 줄 Refresh 메서드를 특정 ID 번호를 할당합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

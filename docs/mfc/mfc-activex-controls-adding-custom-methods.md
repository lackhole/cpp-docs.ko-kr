---
title: 'MFC ActiveX 컨트롤: 사용자 지정 메서드 추가'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: 4f5a7dc844d80ae94df8af7c0b2eea141376f9e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160148"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX 컨트롤: 사용자 지정 메서드 추가

사용자 지정 메서드 스톡 메서드 점에서 다릅니다에서 이미 구현 하지 않는 `COleControl`합니다. 컨트롤에 추가한 각 사용자 지정 방법에 대 한 구현을 제공 해야 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

ActiveX 컨트롤 사용자 컨트롤 관련 작업을 수행 하려면 언제 든 사용자 지정 메서드를 호출할 수 있습니다. 사용자 지정 메서드에 대 한 디스패치 맵 항목 DISP_FUNCTION 폼입니다.

##  <a name="_core_adding_a_custom_method_with_classwizard"></a> 사용 하 여 사용자 지정 메서드 추가 메서드 추가 마법사

다음 절차는 ActiveX 컨트롤의 기본 코드에 PtInCircle 사용자 지정 메서드를 추가 하는 방법을 보여 줍니다. PtInCircle 내부 또는 외부 원 컨트롤에 전달 하는 좌표 되는지 여부를 결정 합니다. 이 절차는 다른 사용자 지정 메서드를 추가 하려면 데도 사용할 수 있습니다. 사용자 지정 메서드 이름 및 PtInCircle 메서드 이름과 매개 변수를 해당 매개 변수를 대체 합니다.

> [!NOTE]
>  이 예제에서는 `InCircle` 이벤트 아티클에서 함수입니다. 이 함수에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: ActiveX 컨트롤에 사용자 지정 이벤트 추가](../mfc/mfc-activex-controls-adding-custom-events.md)합니다.

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>메서드 추가 마법사를 사용 하 여 PtInCircle 사용자 지정 메서드를 추가 하려면

1. 컨트롤의 프로젝트를 로드 합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **메서드 추가**합니다.

   이 메서드 추가 마법사를 엽니다.

1. 에 **메서드 이름** 상자에 입력 *PtInCircle*합니다.

1. 에 **내부 이름** 상자에, 메서드의 내부 함수의 이름을 입력 하거나 기본값을 사용 (이 예제의 경우 *PtInCircle*).

1. 에 **반환 형식** 상자를 클릭 합니다 **VARIANT_BOOL** 메서드의 반환 형식에 대 한 합니다.

1. 사용 하 여는 **매개 변수 형식이** 및 **매개 변수 이름** 이라는 매개 변수를 추가 하는 컨트롤 *xCoord* (형식 *OLE_XPOS_PIXELS*).

9. 사용 하 여는 **매개 변수 형식이** 및 **매개 변수 이름** 이라는 매개 변수를 추가 하는 컨트롤 *yCoord* (형식 *OLE_YPOS_PIXELS*).

10. **마침**을 클릭합니다.

##  <a name="_core_classwizard_changes_for_custom_methods"></a> 사용자 지정 메서드 추가 마법사 변경 메서드

사용자 지정 메서드를 추가 하면 메서드 추가 마법사에 게 몇 가지 변경 내용을 컨트롤 클래스 헤더 (합니다. H) 및 구현 (합니다. CPP) 파일입니다. 다음 줄은 컨트롤 클래스 헤더에 디스패치 맵 선언에 추가 됩니다 (합니다. H) 파일:

[!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

이 코드에서는 호출 하는 디스패치 메서드 처리기를 선언 `PtInCircle`합니다. External name을 사용 하 여 컨트롤 사용자가이 함수를 호출할 수 있습니다 `PtInCircle`합니다.

다음 줄은 컨트롤에 추가 됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

이 줄에서 할당 된 `PtInCircle` 메서드는 특정 ID 번호, 메서드 추가 마법사 메서드 및 속성 목록에 있는 메서드의 위치입니다. 사용자 지정 메서드를 추가 하는 메서드 추가 마법사 사용 되었으므로, 프로젝트의 항목에 대 한 자동으로 추가 되었습니다. IDL 파일입니다.

다음 줄을 구현에는 또한 (합니다. 컨트롤의 디스패치 맵에 cpp) 컨트롤 클래스에 추가 됩니다.

[!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

DISP_FUNCTION 매크로 메서드에 매핑합니다 `PtInCircle` 컨트롤의 처리기 함수에 `PtInCircle`를 선언 된 반환 형식이 **VARIANT_BOOL**, 형식의 두 매개 변수를 선언 하 고 **VTS_XPOS_PIXELS** 하 고 **VTS_YPOSPIXELS** 전달할 `PtInCircle`합니다.

메서드 추가 마법사에서 스텁 함수를 추가 하는 마지막으로, `CSampleCtrl::PtInCircle` 구현은 컨트롤의 맨 아래에 (합니다. Cpp) 합니다. 에 대 한 `PtInCircle` 앞서 설명한 것 처럼 작동 하 고 수정 해야 합니다 다음과 같이 합니다.

[!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[클래스 뷰 및 개체 브라우저 아이콘](/visualstudio/ide/class-view-and-object-browser-icons)

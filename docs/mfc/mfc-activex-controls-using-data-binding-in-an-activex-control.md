---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용'
ms.date: 11/19/2018
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
ms.openlocfilehash: e21a31b71e681cdffed555c10079c2598967543f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239542"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용

ActiveX 컨트롤을 사용 하는 더 강력한 중 하나는 데이터베이스의 특정 필드를 사용 하 여 바인딩할 컨트롤의 속성을 사용 하면 데이터 바인딩과입니다. 사용자가이 바인딩된 속성의 데이터를 수정 하는 경우 컨트롤에는 데이터베이스 및 레코드 필드를 업데이트 해야 하는 요청에 알립니다. 데이터베이스에는 다음 요청이 실패 또는 성공의 컨트롤에 알립니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

이 문서에서는 제어 측면에서의 작업을 설명 합니다. 데이터베이스를 사용 하 여 데이터 바인딩 상호 작용을 구현 하는 것은 컨트롤 컨테이너의 책임입니다. 이 문서의 범위를 벗어납니다 컨테이너에서 데이터베이스 상호 작용을 관리 하는 방법입니다. 이 문서의 나머지 부분에서 데이터 바인딩에 대 한 제어를 준비 하는 방법을 설명 되어 있습니다.

![데이터 영역의 개념 다이어그램과&#45;컨트롤에 바인딩된](../mfc/media/vc374v1.gif "데이터 영역의 개념 다이어그램과&#45;바인딩 컨트롤") <br/>
데이터 바인딩된 컨트롤의 개념적 다이어그램

`COleControl` 클래스는 데이터 바인딩 구현 하는 쉬운 프로세스는 두 멤버 함수를 제공 합니다. 첫 번째 함수 [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), 속성 값을 변경 하는 권한을 요청 하는 데 사용 됩니다. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), 두 번째 함수는 속성 값을 성공적으로 변경 된 후 호출 됩니다.

이 문서에서는 다음 항목을 다룹니다.

- [바인딩할 수 있는 스톡 속성 만들기](#vchowcreatingbindablestockproperty)

- [바인딩 가능한 Get/Set 메서드 만들기](#vchowcreatingbindablegetsetmethod)

##  <a name="vchowcreatingbindablestockproperty"></a> 바인딩할 수 있는 스톡 속성 만들기

것 보다는 할 수 있지만 주식 데이터 바인딩된 속성을 만들 수는 [바인딩할 수 있는 get/set 메서드](#vchowcreatingbindablegetsetmethod)합니다.

> [!NOTE]
> 스톡 속성을 `bindable` 및 `requestedit` 기본적으로 특성입니다.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 바인딩 가능한 스톡 속성을 추가 하려면

1. 사용 하 여 프로젝트를 시작 합니다 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)합니다.

1. 컨트롤의 인터페이스 노드를 마우스 오른쪽 단추로 클릭 합니다.

   바로 가기 메뉴가 열립니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **속성 추가**합니다.

1. 항목을 중 하나를 선택 합니다 **속성 이름이** 드롭 다운 목록. 예를 들어, 선택할 수 있습니다 **텍스트**합니다.

   때문에 **텍스트** 스톡 속성으로는 **바인딩할 수 있는** 및 **requestedit** 특성을 이미 검사 합니다.

1. 다음 확인란을 선택 합니다 **IDL 특성** 탭: **displaybind** 및 **defaultbind** 프로젝트의 속성 정의에 특성을 추가 합니다. IDL 파일입니다. 이러한 컨트롤을 사용자에 게 표시 되도록 특성과 스톡 속성의 기본 바인딩 가능 속성을 확인 합니다.

이 시점에서 컨트롤을 데이터 원본에서 데이터를 표시할 수 있지만 사용자는 데이터 필드를 업데이트할 수 없습니다. 데이터 업데이트를 변경할 수 있도록 하려면 컨트롤을 원하는 경우 합니다 `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) 함수를 다음과 같이 표시 합니다.

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

이제 컨트롤을 등록 하는 프로젝트를 빌드할 수 있습니다. 대화 상자에 컨트롤을 삽입할 때 합니다 **데이터 필드** 하 고 **데이터 원본** 속성은 추가 했 고 이제 데이터 원본 및 컨트롤에 표시할 필드를 선택할 수 있습니다.

##  <a name="vchowcreatingbindablegetsetmethod"></a> 바인딩 가능한 Get/Set 메서드 만들기

데이터 바인딩된 get/set 메서드 외에도 만들 수도 있습니다는 [바인딩할 수 있는 스톡 속성](#vchowcreatingbindablestockproperty)합니다.

> [!NOTE]
> 이 절차는 Windows 컨트롤을 프로젝트 ActiveX 컨트롤을 가정 합니다.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 바인딩 가능한 get/set 메서드를 추가 하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 에 **제어 설정을** 페이지, 하위 컨트롤에 대 한 창 클래스를 선택 합니다. 예를 들어, 하려는 하위 클래스 편집 컨트롤입니다.

1. 컨트롤의 프로젝트를 로드합니다.

1. 컨트롤의 인터페이스 노드를 마우스 오른쪽 단추로 클릭 합니다.

   바로 가기 메뉴가 열립니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **속성 추가**합니다.

1. 에 속성 이름을 입력 합니다 **속성 이름이** 상자입니다. 사용 하 여 `MyProp` 예입니다.

1. 데이터 형식을 선택 합니다 **속성 형식** 드롭다운 목록 상자입니다. 사용 하 여 **짧은** 예입니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. IDL 특성 탭에서 다음 확인란을 선택 합니다. **바인딩할 수 있는**, **requestedit**, **displaybind**, 및 **defaultbind** 추가할 프로젝트의 속성 정의에 대 한 특성입니다. IDL 파일입니다. 이러한 컨트롤을 사용자에 게 표시 되도록 특성과 스톡 속성의 기본 바인딩 가능 속성을 확인 합니다.

1. **마침**을 클릭합니다.

1. 본문을 수정 합니다 `SetMyProp` 함수를 다음 코드를 포함 합니다.

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. 매개 변수를 전달 합니다 `BoundPropertyChanged` 및 `BoundPropertyRequestEdit` 기능은 id () 특성의 속성에 대해 전달 된 매개 변수 속성의 dispid를 합니다. IDL 파일입니다.

1. 수정 된 [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) 함수 이므로 다음 코드를 포함 합니다.

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. 수정 된 `OnDraw` 함수를 다음 코드를 포함 합니다.

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. 헤더 파일 컨트롤 클래스에 대 한 헤더 파일의 공용 섹션으로 멤버 변수에 대 한 다음 정의 (생성자)를 추가 합니다.

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. 다음 줄의 마지막 줄을 확인 합니다 `DoPropExchange` 함수:

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. 수정 된 `OnResetState` 함수를 다음 코드를 포함 합니다.

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. 수정 된 `GetMyProp` 함수를 다음 코드를 포함 합니다.

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

이제 컨트롤을 등록 하는 프로젝트를 빌드할 수 있습니다. 대화 상자에 컨트롤을 삽입할 때 합니다 **데이터 필드** 하 고 **데이터 원본** 속성은 추가 했 고 이제 데이터 원본 및 컨트롤에 표시할 필드를 선택할 수 있습니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

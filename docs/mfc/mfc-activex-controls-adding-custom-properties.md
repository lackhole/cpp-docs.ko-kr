---
title: 'MFC ActiveX 컨트롤: 사용자 지정 속성 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: e02d5523b894f89aa93c8d2765a128920afa2353
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392780"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX 컨트롤: 사용자 지정 속성 추가

사용자 지정 속성에서 아직 구현 하지 않는 스톡 속성에서 사용자 지정 속성 다는 `COleControl` 클래스입니다. 사용자 지정 속성을 특정 상태 또는 컨트롤을 사용 하 여 프로그래머에 ActiveX 컨트롤의 모양 표시 됩니다.

이 문서에서는 ActiveX 컨트롤 속성 추가 마법사를 사용 하 여 사용자 지정 속성을 추가 하는 방법 및 결과 코드 수정 내용을 설명 합니다. 다루는 주제는 다음과 같습니다.

- [속성 추가 마법사를 사용 하 여 사용자 지정 속성을 추가 하려면](#_core_using_classwizard_to_add_a_custom_property)

- [추가 사용자 지정 속성에 대 한 속성 마법사 변경](#_core_classwizard_changes_for_custom_properties)

사용자 지정 속성 구현의 네 가지가 제공 합니다. 멤버 변수, 알림, Get/Set 메서드를 사용 하 여 멤버 변수 및 매개 변수가 있는 합니다.

- 멤버 변수 구현

   이 구현은 컨트롤 클래스에서 멤버 변수로 속성의 상태를 나타냅니다. 속성 값을 변경 하는 경우 알아야 중요 하지 않을 때 멤버 변수 구현을 사용 합니다. 이 구현은 세 가지 유형의 속성에 대 한 지원 코드의 최소 크기를 만듭니다. 멤버 변수 구현에 대 한 디스패치 맵 항목 매크로가 [DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property)합니다.

- 멤버 변수 알림 구현

   이 구현은 멤버 변수 및 속성 추가 마법사에서 만든 알림 함수로 구성 됩니다. 알림 함수는 자동으로 속성 값 변경 된 후 프레임 워크에서 호출 됩니다. 멤버 변수 알림 구현 해야 할 때 사용 속성 값이 변경 후 알림을 받도록 합니다. 이 구현은 함수 호출이 필요 하기 때문에 더 많은 시간이 필요 합니다. 이 구현에 대 한 디스패치 맵 항목 매크로가 [DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify)합니다.

- Get/Set 메서드 구현

   이 구현은 컨트롤 클래스의 멤버 함수 쌍으로 구성 합니다. Get/Set 메서드 구현을 자동으로 호출 Get 멤버가 속성의 현재 값을 요청 하는 컨트롤의 사용자 함수 및 집합 멤버 함수 속성이 변경 될 컨트롤의 사용자가 요청 하는 경우. 런타임에 속성 값을 계산 합니다. 실제 속성을 변경 하기 전에 컨트롤의 사용자에 의해 전달 된 값의 유효성을 검사 하거나 읽기 또는 쓰기 전용 속성 유형을 구현 하는 경우이 구현을 사용 합니다. 이 구현에 대 한 디스패치 맵 항목 매크로가 [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex)합니다. 다음 섹션인 [속성 추가 마법사를 사용 하 여 사용자 지정 속성을 추가 하려면](#_core_using_classwizard_to_add_a_custom_property), CircleOffset 사용자 지정 속성을 사용 하 여이 구현을 보여 줍니다.

- 매개 변수가 있는 구현

   매개 변수가 있는 구현 속성 추가 마법사에서 지원 됩니다. 매개 변수화 된 속성 (속성 배열 라고도 함) 값 집합을 컨트롤의 단일 속성을 통해 액세스를 사용할 수 있습니다. 이 구현에 대 한 디스패치 맵 항목 매크로 DISP_PROPERTY_PARAM입니다. 이 형식을 구현 하는 방법은 참조 하세요 [매개 변수가 있는 속성 구현](../mfc/mfc-activex-controls-advanced-topics.md) 문서의 ActiveX 컨트롤: 고급 항목입니다.

##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> 사용 하는 속성 추가 마법사 사용자 지정 속성을 추가 하려면

다음 절차에서는 CircleOffset Get/Set 메서드 구현을 사용 하는 사용자 지정 속성을 추가 하는 방법을 보여 줍니다. CircleOffset 사용자 지정 속성에는 컨트롤의 사용자를 컨트롤의 경계 사각형의 가운데에서 원 오프셋 수 있습니다. Get/Set 메서드 이외의 구현 사용 하 여 사용자 지정 속성 추가 대 한 절차는 매우 비슷합니다.

이 절차는 다른 사용자 지정 속성을 추가 하려면 데도 사용할 수 있습니다. CircleOffset 속성 이름 및 매개 변수 사용자 지정 속성 이름으로를 바꿉니다.

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 CircleOffset 사용자 지정 속성을 추가 하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **속성 추가**합니다.

   열립니다는 [속성 추가 마법사](../ide/names-add-property-wizard.md)합니다.

1. 에 **속성 이름이** 상자에 입력 *CircleOffset*합니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. 에 **속성 형식** 상자에서 **짧은**합니다.

1. Get 및 Set 함수의 고유 이름을 입력 하거나 기본 이름을 적용 합니다.

9. **마침**을 클릭합니다.

##  <a name="_core_classwizard_changes_for_custom_properties"></a> 사용자 지정 속성에 대 한 추가 속성 마법사 변경

CircleOffset 사용자 지정 속성에 추가 하면 속성 추가 마법사 변경한 헤더 (합니다. H) 및 구현 (합니다. 컨트롤 클래스의 CPP) 파일입니다.

다음 줄에 추가 되는 합니다. H 파일을 호출 하는 두 함수를 선언 `GetCircleOffset` 고 `SetCircleOffset`:

[!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

다음 줄에 컨트롤에 추가 됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

이 줄 CircleOffset 속성을 속성 추가 마법사의 메서드 및 속성 목록에 있는 메서드의 위치에서 가져온 특정 ID 번호를 할당 합니다.

또한 다음 줄을 디스패치 맵에 추가 됩니다 (에서 합니다. 컨트롤 클래스의 CPP 파일) 속성을 매핑할 CircleOffset 컨트롤의 두 처리기 함수:

[!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

마지막으로 구현 된 `GetCircleOffset` 및 `SetCircleOffset` 함수는 컨트롤의 끝에 추가 됩니다. CPP 파일입니다. 대부분의 경우에서 속성의 값을 반환 하는 Get 함수를 수정 합니다. Set 함수에는 대개 전이나 속성이 변경 된 후 실행 되어야 하는 코드가 포함 됩니다.

[!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

속성 추가 마법사 자동으로 추가 호출을 하 [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), Set 함수 본문입니다. 수정 된 것으로 컨트롤을 표시이 함수를 호출 합니다. 컨트롤을 수정 하는 경우 컨테이너를 저장할 때 새 상태로 저장 됩니다. 컨트롤의 영구 상태의 일부로 저장 하는 속성 값이 변경 될 때마다이 함수를 호출 해야 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl 클래스](../mfc/reference/colecontrol-class.md)

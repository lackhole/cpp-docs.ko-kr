---
title: 'MFC ActiveX 컨트롤: 고급 속성 구현'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: 438c95c56961cc587b64e494678ade191f18ab6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392806"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX 컨트롤: 고급 속성 구현

이 문서에서는 고급 ActiveX 컨트롤에서 속성을 구현 하는 데 관련 된 항목을 설명 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

- [읽기 전용 및 쓰기 전용 속성](#_core_read2donly_and_write2donly_properties)

- [속성에서 오류 코드를 반환합니다.](#_core_returning_error_codes_from_a_property)

##  <a name="_core_read2donly_and_write2donly_properties"></a> 읽기 전용 및 쓰기 전용 속성

속성 추가 마법사 컨트롤에 대 한 읽기 전용 또는 쓰기 전용 속성을 구현 하는 쉽고 빠르게 메서드를 제공 합니다.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>읽기 전용 또는 쓰기 전용 속성을 구현 하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **속성 추가**합니다.

   열립니다는 [속성 추가 마법사](../ide/names-add-property-wizard.md)합니다.

1. 에 **속성 이름이** 상자 속성의 이름을 입력 합니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. 에 **속성 형식** 상자, 속성에 대 한 적절 한 유형을 선택 합니다.

1. 읽기 전용 속성을 원하는 경우 집합 함수 이름의 선택을 취소 합니다. 쓰기 전용 속성을 원한다 면 Get 함수 이름의 선택을 취소 합니다.

9. **마침**을 클릭합니다.

이렇게 하면 속성 추가 마법사 함수를 삽입 합니다 `SetNotSupported` 또는 `GetNotSupported` 함수를 가져오거나 대신 일반 디스패치 맵 항목에 설정 합니다.

읽기 전용 이거나 쓰기 전용 이어야 하는 기존 속성을 변경 하려는 경우 디스패치 맵 수동으로 편집한 control 클래스에서 불필요 한 Set 또는 Get 함수를 제거 합니다.

정상적으로 Set 또는 Get 함수를 제공 하 고 호출 수는 속성을 조건에 따라 읽기 전용 또는 쓰기 전용 (예: 컨트롤 특정 모드에서 작동 하는 경우에)를 사용 하도록 하려는 경우는 `SetNotSupported` 또는 `GetNotSupported` 적절 한 작동 합니다. 예를 들어:

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

이 코드 샘플을 호출 `SetNotSupported` 경우는 `m_bReadOnlyMode` 데이터 멤버가 **TRUE**합니다. 하는 경우 **FALSE**, 속성이 새 값으로 설정 됩니다.

##  <a name="_core_returning_error_codes_from_a_property"></a> 속성에서 오류 코드를 반환합니다.

Get 또는 속성을 설정 하는 동안 오류가 발생 했음을 알리는 사용 하 여는 `COleControl::ThrowError` 매개 변수로 SCODE (상태 코드)를 사용 하는 함수입니다. 미리 정의 된 SCODE를 사용 하거나 자신만 정의 수 있습니다. 목록을 미리 정의 된 SCODEs 및 사용자 지정 SCODEs 정의 대 한 지침을 참조 하세요 [Your ActiveX 컨트롤의 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) 문서 ActiveX 컨트롤에서: 고급 항목입니다.

도우미 함수는 가장 일반적인 같은 미리 정의 된 SCODEs에 대 한 존재 [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported)하십시오 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), 및 [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

> [!NOTE]
>  `ThrowError` 속성의 Get 또는 Set 내에서 오류를 반환 하는 수단 으로만 사용 하려는 함수 또는 메서드를 자동화 합니다. 이 스택에 적절 한 예외 처리기 수 있는 시간이 존재 합니다.

코드의 다른 영역에서 예외를 보고 하는 방법은 참조 하세요 [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 섹션 [Your ActiveX 컨트롤의 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) 문서의 ActiveX 컨트롤: 고급 항목입니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl 클래스](../mfc/reference/colecontrol-class.md)

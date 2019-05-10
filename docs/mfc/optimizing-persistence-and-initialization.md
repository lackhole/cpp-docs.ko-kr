---
title: 지속성 및 초기화 최적화
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
ms.openlocfilehash: 294d9c43f5f767329c04932c574485d7dca704e9
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342127"
---
# <a name="optimizing-persistence-and-initialization"></a>지속성 및 초기화 최적화

기본적으로 지 속성 및 컨트롤의 초기화에서 처리 됩니다는 `DoPropExchange` 멤버 함수입니다. 이 함수를 일반적인 컨트롤에서 몇 가지에 대 한 호출을 포함 **PX_** 함수 (`PX_Color`, `PX_Font`등), 각 속성에 대 한 합니다.

이 방법은 이점이 있는 단일 `DoPropExchange` 초기화, 이진 형식으로 지 속성 및 일부 컨테이너에서 사용 하는 소위 "속성 모음" 형식에서 지 속성 구현을 사용할 수 있습니다. 이 함수는 속성과 편리 하 게 한곳에서 기본 값에 대 한 모든 정보를 제공 합니다.

그러나이 일반 성을 효율성이 저하 됩니다. 합니다 **PX_** 함수 가져오기 작은 본질적으로 다중된 구현을 통해 유연성을 더 직접적 이지만 유연성도 낮습니다 접근 방식 보다 효율적입니다. 또한 컨트롤에 기본 값을 전달 하는 경우는 **PX_** 함수에 기본 값 기본값 반드시 사용할 수 없습니다 하는 경우에도 모든 시간을 제공 해야 합니다. 기본 값을 생성할 인 경우 (예: 앰비언트 속성에서 값을 가져오는 경우), 중요 한 작업을 추가 기본값을 사용 하지 되는 경우 불필요 한 작업 수행 됩니다.

컨트롤의 재정의 하 여 컨트롤의 이진 지 속성 성능은 향상 시킬 수 있습니다 `Serialize` 함수입니다. 이 멤버 함수의 기본 구현을 호출 하 여 `DoPropExchange` 함수입니다. 를 재정의 하 여 이진 지 속성에 대 한 더 직접적인 구현을 제공할 수 있습니다. 예를 들어이 `DoPropExchange` 함수:

[!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]

이 컨트롤의 이진 지 속성의 성능 향상을 위해 재정의할 수 있습니다는 `Serialize` 다음과 같이 작동 합니다.

[!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]

`dwVersion` 로컬 변수는 버전의 컨트롤의 영구 상태가 로드 또는 저장 된 검색에 사용할 수 있습니다. 이 변수를 사용 하 여 호출 하는 대신 [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion)합니다.

작은 공간에 대 한 영구 형식으로 저장 하는 **BOOL** 속성 (에 의해 생성 된 형식과 호환 `PX_Bool`)를 속성으로 저장할 수 있습니다를 **바이트**같이:

[!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]

캐스팅 하는 것이 아니라 부하의 경우는 임시 변수를 사용 하 고 해당 값을 할당 한 다음 *m_boolProp* 에 **바이트** 참조 합니다. 1 바이트의 캐스팅 방법을 초래 *m_boolProp* 수정 하 고, 나머지 바이트는 초기화 되지 않았습니다.

동일한 컨트롤에 대 한 재정의 하 여 컨트롤의 초기화를 최적화할 수 있습니다 [COleControl::OnResetState](../mfc/reference/colecontrol-class.md#onresetstate) 다음과 같습니다.

[!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]

하지만 `Serialize` 하 고 `OnResetState` 재정의 된는 `DoPropExchange` 함수 유지할지 그대로-propertybag 형식으로 지 속성을 위해 사용 되 고 있으므로. 컨트롤 속성과 일관 되 게 관리 되도록 이러한 함수는 지 속성에 관계 없이 컨테이너 메커니즘 사용의 세 가지 모두를 유지 하는 것이 반드시 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)

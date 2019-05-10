---
title: 'MFC ActiveX 컨트롤: 직렬화 하는 작업'
ms.date: 09/12/2018
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
ms.openlocfilehash: 0c1c845640be2dfaa6aeda2defb478afb650b83b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324742"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX 컨트롤: 직렬화 하는 작업

이 문서에서는 ActiveX 컨트롤을 serialize 하는 방법을 설명 합니다. Serialization은 프로세스에서 읽고 있는지 아니면 디스크 파일과 같은 영구적 저장소 매체에 쓸입니다. Microsoft Foundation 클래스 (MFC) 라이브러리 클래스의 serialization에 대 한 기본 제공 지원을 제공 `CObject`합니다. `COleControl` 속성 교환 메커니즘을 사용 하 여 ActiveX 컨트롤이 지원이 확장 되었습니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

ActiveX 컨트롤에 대 한 serialization 재정의 하 여 구현 됩니다 [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)합니다. 이 함수를 로드 하는 동안 호출 및 멤버 변수 또는 변경 알림 사용 하 여 멤버 변수를 사용 하 여 구현 하는 모든 속성을 저장 컨트롤 개체의 저장 합니다.

다음 항목에서는 ActiveX 컨트롤을 직렬화와 관련 된 주요 문제를 설명 합니다.

- 구현 `DoPropExchange` 컨트롤 개체를 serialize 하는 함수

- [Serialization 프로세스를 사용자 지정](#_core_customizing_the_default_behavior_of_dopropexchange)

- [구현 버전 지원](#_core_implementing_version_support)

##  <a name="_core_implementing_the_dopropexchange_function"></a> DoPropExchange 함수 구현

여러 기본 처리기 함수가 컨트롤 클래스의 기본 구현을 포함 하 여 자동으로 추가 되어 컨트롤 프로젝트를 생성 하 여 ActiveX 컨트롤 마법사를 사용 하는 경우 [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)합니다. 다음 예제에서는 ActiveX 컨트롤 마법사를 사용 하 여 만든 클래스에 추가한 코드를 보여 줍니다.

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

영구 속성을 확인 하려는 경우 수정 `DoPropExchange` 속성 exchange 함수에 대 한 호출을 추가 하 여 합니다. 다음 예제에서는 CircleShape 속성이 기본값은 사용자 지정 부울 CircleShape 속성의 serialization **TRUE**:

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

다음 표에 가능한 속성 exchange 함수는 컨트롤의 속성을 serialize 하는 데 사용할 수 있습니다.

|속성 교환 함수|용도|
|---------------------------------|-------------|
|**PX_Blob( )**|큰 BLOB (Binary Object) 데이터 속성 형식을 serialize 합니다.|
|**PX_Bool( )**|형식을 부울 속성을 serialize 합니다.|
|**PX_Color( )**|유형 색 속성을 serialize합니다.|
|**PX_Currency( )**|형식을 serialize **CY** (currency) 속성입니다.|
|**PX_Double( )**|형식을 serialize **이중** 속성입니다.|
|**PX_Font( )**|글꼴 형식 속성을 serialize합니다.|
|**PX_Float( )**|형식을 serialize **float** 속성입니다.|
|**PX_IUnknown( )**|형식의 속성을 serialize `LPUNKNOWN`합니다.|
|**PX_Long( )**|형식을 serialize **긴** 속성입니다.|
|**PX_Picture( )**|그림 속성 형식을 serialize 합니다.|
|**PX_Short( )**|형식을 serialize **짧은** 속성입니다.|
|**PXstring( )**|형식을 serialize `CString` 속성입니다.|
|**PX_ULong( )**|형식을 serialize **ULONG** 속성입니다.|
|**PX_UShort( )**|형식을 serialize **USHORT** 속성입니다.|

이러한 속성 exchange 함수에 대 한 자세한 내용은 참조 하세요. [지 속성의 OLE 컨트롤](../mfc/reference/persistence-of-ole-controls.md) 에 *MFC 참조*합니다.

##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> DoPropExchange 기본 동작을 사용자 지정

기본 구현의 `DoPropertyExchange` (이전 항목에서 표시)는 기본 클래스에 대 한 호출 `COleControl`합니다. 이 자동으로 지 원하는 속성의 집합을 serialize `COleControl`, 컨트롤의 사용자 지정 속성만 직렬화 하는 작업 보다 더 많은 저장소 공간을 사용 하는 합니다. 중요 한 것이 좋습니다 속성만 serialize 할 개체를 허용이 호출을 제거 합니다. 구현 된 컨트롤에 스톡 속성 상태를 저장 하거나 명시적으로 추가 하지 않는 한 컨트롤 개체를 로드 하는 경우 serialize 되지 것입니다 **PX_** 에 호출 됩니다.

##  <a name="_core_implementing_version_support"></a> 구현 버전 지원

버전 지원을 통해 수정 된 ActiveX 컨트롤을 새 영구 속성을 추가 하 고 검색 하 고 컨트롤의 이전 버전에서 만든 영구 상태를 로드 하는 일을 할 수 있습니다. 컨트롤의 버전을 사용할 수 있도록 자체 영구 데이터의 일부로, 호출 [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) 컨트롤의 `DoPropExchange` 함수입니다. 이 호출은 ActiveX 컨트롤은 ActiveX 컨트롤 마법사를 사용 하 여 생성 된 경우에 자동으로 삽입 됩니다. 버전 지원 필요 하지 않은 경우에 제거할 수 있습니다. 그러나 컨트롤 크기의 비용은 매우 버전 지원을 제공 하는 추가 유연성에 대 한 작은 (4 바이트)입니다.

컨트롤은 ActiveX 컨트롤 마법사를 사용 하 여 만들지 않은, 경우에 호출을 추가 `COleControl::ExchangeVersion` 의 시작 부분에 다음 줄을 삽입 하 여 프로그램 `DoPropExchange` 함수 (호출 하기 전에 `COleControl::DoPropExchange`):

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

사용할 수 있습니다 **DWORD** 버전 번호로 합니다. ActiveX 컨트롤 마법사에서 생성 된 프로젝트를 사용 `_wVerMinor` 고 `_wVerMajor` 기본적으로 합니다. 이들은 프로젝트의 ActiveX 컨트롤 클래스의 구현 파일에 정의 된 전역 상수입니다. 나머지 부분 내에서 프로그램 `DoPropExchange` 함수를 호출할 수 있습니다 [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) 언제 든 지 저장 하거나 검색 하는 버전을 검색 합니다.

다음 예제에서는이 샘플 컨트롤의 버전 1에는 "발표일" 속성만 있습니다. 버전 2는 "OriginalDate" 속성을 추가합니다. 컨트롤이 이전 버전에서 영구 상태를 로드 하도록 지시를 하는 경우 기본 값으로 새 속성에 대 한 멤버 변수를 초기화 합니다.

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

기본적으로 컨트롤을 "변환" 오래 된 데이터를 최신 형식입니다. 예를 들어, 버전 2는 컨트롤의 버전 1에서 저장 된 데이터를 로드 하는 경우 다시 저장 될 때 버전 2 형식으로 기록 합니다. 컨트롤 형식으로 마지막으로 읽은 데이터 저장을 원한다 면 전달 **FALSE** 호출 하는 경우 세 번째 매개 변수로 `ExchangeVersion`합니다. 이 세 번째 매개 변수는 선택적 이며 **TRUE** 기본적으로 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

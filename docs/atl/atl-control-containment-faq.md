---
title: ATL 컨트롤 포함 FAQ
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 42f9b41b99e13fcfe2fb003acb348c9464e0fd05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223321"
---
# <a name="atl-control-containment-faq"></a>ATL 컨트롤 포함 FAQ

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>어떤 ATL 클래스가 ActiveX 컨트롤 포함 용이?

모든 ATL 클래스를 사용 하 여 ATL의 컨트롤 호스팅 코드 필요 하지 않습니다. 간단히 만들 수 있습니다는 **"AtlAxWin80"** 창 및 필요한 경우 컨트롤 호스팅 API 사용 하 여 (자세한 내용은 참조 하십시오 **ATL 컨트롤 호스팅 API 란 무엇 인가요**합니다. 그러나 다음 클래스를 쉽게 포함 기능 사용 합니다.

|클래스|설명|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|래핑하는 **"AtlAxWin80"** 창 만들기 창, 컨트롤 만들기 및/또는 창으로 컨트롤을 연결 및 호스트 개체에서 인터페이스 포인터를 검색에 대 한 메서드를 제공 합니다.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|래핑하는 **"AtlAxWinLic80"** 창 만들기 창, 컨트롤 만들기 및/또는 사용이 허가 된 컨트롤을 창에 연결 및 호스트 개체에서 인터페이스 포인터를 검색에 대 한 메서드를 제공 합니다.|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|대화 상자 리소스를 기반으로 하는 ActiveX 컨트롤 클래스에 대 한 기본 클래스로 작동 합니다. 이러한 컨트롤 다른 ActiveX 컨트롤을 포함할 수 있습니다.|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|대화 상자 리소스를 기반으로 하는 대화 상자 클래스에 대 한 기본 클래스로 작동 합니다. 이러한 대화 상자는 ActiveX 컨트롤을 포함할 수 있습니다.|
|[CWindow](../atl/reference/cwindow-class.md)|메서드를 제공 합니다 [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), 해당 호스트 창의 ID를 지정 된 컨트롤에 인터페이스 포인터를 반환 됩니다. Windows API 래퍼에 의해 노출 되는 또한 `CWindow` 일반적으로 창 관리를 용이 합니다.|

## <a name="what-is-the-atl-control-hosting-api"></a>새로운 ATL 컨트롤 호스팅 API?

ATL의 컨트롤 호스팅 API는 ActiveX 컨트롤 컨테이너 역할을 허용 하는 함수 집합입니다. 이러한 함수 정적으로 또는 동적으로 소스 코드로 제공 되므로 프로젝트에 연결 되며 ATL90.dll에 의해 노출 합니다. 컨트롤 호스팅 함수는 아래 표에 나열 됩니다.

|함수|설명|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|호스트 개체를 만듭니다, 그리고 제공된 된 창에 연결한 다음 기존 컨트롤을 연결 합니다.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|호스트 개체를 만듭니다, 그리고 제공된 된 창에 연결한 다음 컨트롤을 로드 합니다.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|사용이 허가 된 ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)합니다.|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|호스트 개체를 만들고, 제공된 된 창에 연결한 다음 컨트롤을 로드 (또한를 통해 이벤트 싱크 설정).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)합니다.|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|대화 상자 리소스에서 모덜리스 대화 상자를 만들고 창 핸들을 반환 합니다.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|대화 상자 리소스에서 모달 대화 상자를 만듭니다.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|반환 된 **IUnknown** 창에서 호스팅되는 컨트롤의 인터페이스 포인터입니다.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|반환 된 **IUnknown** 창에 호스트 개체의 인터페이스 포인터에 연결 합니다.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|컨트롤 호스팅 코드를 초기화합니다.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|컨트롤 호스팅 코드를 초기화 하지 않습니다.|

`HWND` 처음 세 함수에 매개 변수 (거의) 모든 종류의 기존 창을 이어야 합니다. 이러한 세 가지 함수를 명시적으로 호출 하는 경우 (일반적으로 않아도)을 이미 역할을 호스트 하는 창에 대 한 핸들을 전달 하지 않습니다 (이렇게 하면 기존 호스트 개체 않습니다 해제) 합니다.

처음 7 개의 함수 호출 [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 암시적으로 합니다.

> [!NOTE]
>  컨트롤 호스팅 API는 ActiveX 컨트롤 포함에 대 한 ATL의 지원의 기초를 구성 합니다. 그러나 방법이 일반적으로 활용 하거나 ATL의 래퍼 클래스를 최대한 활용 하는 경우 이러한 함수를 직접 호출할 필요는 없습니다. 자세한 내용은 [는 ATL 클래스 용이 하 게 ActiveX 컨트롤 포함](which-atl-classes-facilitate-activex-control-containment-q.md)합니다.

## <a name="what-is-atlaxwin100"></a>AtlAxWin100 이란?

`AtlAxWin100` ATL의 컨트롤 호스팅 기능을 제공 하는 데 도움이 되는 창 클래스의 이름이입니다. 이 클래스의 인스턴스를 만들면 창 프로시저 창과 연결 된 호스트 개체를 만들고 창의 제목으로 지정 하는 컨트롤을 사용 하 여 로드 컨트롤 호스팅 API를 자동으로 사용 합니다.

## <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit를 호출 해야 하는 경우는 합니까?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 등록 합니다 **"AtlAxWin80"** 호스트 창을 만들 하려고 하기 전에이 함수를 호출 해야 하므로 창 클래스 (또한 몇 가지 사용자 지정 창 메시지). 그러나 Api (및 사용 하는 클래스)을 호스팅하는 이후이 함수를 명시적으로 호출할 필요가 항상 자주이 함수를 호출 하는 것입니다. 이 함수를 두 번 이상 호출에 아무런 문제가 없습니다.

## <a name="what-is-a-host-object"></a>호스트 개체는 무엇입니까?

호스트 개체를이 특정 창에 대 한 ATL에서 제공 하는 ActiveX 컨트롤 컨테이너를 나타내는 COM 개체입니다. 호스트 개체 서브 클래스 컨테이너 창 컨트롤에 대 한 메시지를 반영할 수 컨트롤을 사용 하는 데 필요한 컨테이너 인터페이스를 제공 하 고 노출 합니다 [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) 고 [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) 인터페이스 컨트롤의 환경을 구성할 수 있습니다.

컨테이너의 앰비언트 속성을 설정 하려면 호스트 개체를 사용할 수 있습니다.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>하나의 창에서 하나 이상의 컨트롤을 호스트할 수 있나요?

하나의 ATL 호스트 창에서 하나 이상의 컨트롤을 호스트 하는 것이 불가능 합니다. 각 호스트 창 (메시지 리플렉션 및 컨트롤 단위로 앰비언트 속성을 처리 하기 위한 간단한 메커니즘에 대 한 허용) 한 번에 하나만 제어를 유지 하도록 설계 되었습니다. 그러나 사용자에 게 하나의 창에서 여러 컨트롤 표시를 해야 하는 경우 것 해당 창의 자식으로 여러 호스트 창을 만드는 것이 간단 합니다.

## <a name="can-i-reuse-a-host-window"></a>호스트 창을 다시 사용할 수 있나요?

호스트 창을 다시 사용 하는 권장 되지 않습니다. 코드의 견고성을 위해 단일 컨트롤의 수명 동안 호스트 창의 수명에 연결 해야 합니다.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>AtlAxWinTerm을 호출 해야 하는 경우는 합니까?

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) 등록을 취소 합니다 **"AtlAxWin80"** 창 클래스입니다. 이 함수 (경우에 호출 해야 호스트 창을 만들 필요가 없습니다) 모든 기존 호스트 창을 제거 된 후입니다. 이 함수를 호출 하지 않으면, 창 클래스를 등록 취소할 수 자동으로 프로세스가 종료 될 때.

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅

이 단원의 샘플에서는 사용할 수 있는 클래스를 만드는 방법 및 다양 한 ATL 함수를 사용 하 여 ActiveX 컨트롤을 호스트 하는 방법을 보여 줍니다. 또한 컨트롤 및 싱크 이벤트를 액세스 하는 방법을 보여 줍니다 (사용 하 여 [IDispEventImpl](../atl/reference/idispeventimpl-class.md))에서 호스트 되는 컨트롤입니다. 주 창 또는 자식 창에서 달력 컨트롤을 호스트 하는 샘플입니다.

정의 확인 합니다 `USE_METHOD` 기호입니다. 1에서 8 사이의 변경 하려면이 기호의 값을 변경할 수 있습니다. 컨트롤은 생성 하는 방법을 결정 하는 기호의 값:

- 값이 짝수 `USE_METHOD`, 창 호스트 서브 클래스를 만들기에 대 한 호출 컨트롤 호스트를 변환 합니다. 홀수 번호 값에 대 한 코드는 호스트 역할을 하는 자식 창을 만듭니다.

- 값에 대해 `USE_METHOD` 1에서 4 사이의 컨트롤에 액세스 하 고 이벤트 싱크.dgml 파일을 호스트 하는 호출에서 수행 됩니다. 5 ~ 8 사이의 값 인터페이스에 대 한 호스트를 쿼리하고 싱크를 연결 합니다.

다음은 요약입니다.

|USE_METHOD|호스트|액세스 제어와 이벤트 싱크|함수 설명|
|-----------------|----------|--------------------------------------|---------------------------|
|1|자식 창|한 단계|CreateControlLicEx|
|2|주 창|한 단계|AtlAxCreateControlLicEx|
|3|자식 창|한 단계|CreateControlEx|
|4|주 창|한 단계|AtlAxCreateControlEx|
|5|자식 창|여러 단계|CreateControlLic|
|6|주 창|여러 단계|AtlAxCreateControlLic|
|7|자식 창|여러 단계|CreateControl|
|8|주 창|여러 단계|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>참고자료

[컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T 클래스](../atl/reference/caxwindow2t-class.md)<br/>
[IAxWinHostWindowLic 인터페이스](../atl/reference/iaxwinhostwindowlic-interface.md)

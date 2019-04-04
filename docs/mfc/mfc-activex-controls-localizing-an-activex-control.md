---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 지역화'
ms.date: 09/12/2018
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
ms.openlocfilehash: 13c8ff545763017b01685e012ab2d497eaf7084a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767550"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 지역화

이 문서에서는 ActiveX 제어 인터페이스의 지역화를 위한 절차를 설명 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

국제 시장에 ActiveX 컨트롤을 조정 하려는 경우에 컨트롤을 지역화 하는 것이 좋습니다. Windows 기본 영어, 독일어, 프랑스어 및 스웨덴어를 포함 하는 것 외에도 많은 언어를 지원 합니다. 해당 인터페이스는 영어로 하는 경우 컨트롤에 대 한 문제를 제공할 수이 있습니다.

일반적으로 ActiveX 컨트롤 LocaleID 앰비언트 속성에 해당 로캘을 기반 항상 해야 합니다. 이렇게 하는 데는 다음과 같은 세 가지 방법이 있습니다.

- LocaleID 앰비언트 속성의 현재 값을 기반으로 요청 시 항상 리소스를 로드 합니다. MFC ActiveX 컨트롤 샘플 [LOCALIZE](../overview/visual-cpp-samples.md) 이 전략을 사용 합니다.

- 첫 번째 컨트롤의 인스턴스가 생성 앰비언트 LocaleID 속성을 기반으로 하는 경우 리소스를 로드 하 고 다른 모든 인스턴스에 대 한 이러한 리소스를 사용 합니다. 이 문서에서는이 전략을 보여 줍니다.

    > [!NOTE]
    >  이 제대로 작동 하지 경우에 따라 이후 인스턴스에 서로 다른 로캘에 있는 경우.

- 사용 하 여는 `OnAmbientChanged` 알림 함수를 동적으로 컨테이너의 로캘에 대 한 적절 한 리소스를 로드 합니다.

    > [!NOTE]
    >  이 컨트롤에 대 한 작동 하지만 LocaleID 앰비언트 속성이 변경 되 면 런타임 DLL 동적으로 자체 리소스를 업데이트 하지는 않습니다. 또한 ActiveX 컨트롤 런타임 Dll 스레드 로캘을 사용 하 여 해당 리소스에 대 한 로캘을 결정 합니다.

이 문서의 나머지 부분에서는 두 가지 지역화 방법을 설명합니다. 첫 번째 전략 [컨트롤의 프로그래밍 기능 인터페이스 보여지는](#_core_localizing_your_control.92.s_programmability_interface) (속성, 메서드 및 이벤트의 이름). 두 번째 전략 [컨트롤의 사용자 인터페이스를 보여지는](#_core_localizing_the_control.92.s_user_interface), 컨테이너의 앰비언트 LocaleID 속성을 사용 합니다. 컨트롤 지역화의 데모를 보려면 MFC ActiveX 컨트롤 샘플을 참조 하세요 [LOCALIZE](../overview/visual-cpp-samples.md)합니다.

##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> 컨트롤의 프로그래밍 인터페이스를 지역화합니다.

컨트롤의 프로그래밍 인터페이스 (컨트롤을 사용 하는 응용 프로그램을 작성 하는 프로그래머가 사용 하는 인터페이스)를 지역화 하는 경우 컨트롤의 수정된 된 버전을 만들어야 합니다. IDL 파일 (컨트롤 형식 라이브러리를 구축 하기 위한 스크립트)를 지원 하려는 각 언어입니다. 컨트롤 속성 이름을 지역화 해야 할 유일한 위치입니다.

지역화 된 컨트롤을 개발할 때 형식 라이브러리 수준에서 특성으로 로캘 ID를 포함 합니다. 예를 들어 프랑스어 지역화 된 속성 이름의 형식 라이브러리를 제공 하려는 경우 샘플의 복사본을 만듭니다. IDL 파일을 선택한 SAMPLEFR를 호출 합니다. IDL 합니다. 로캘 ID 특성 (프랑스어에 대 한 로캘 ID은 0x040c) 파일을 추가할 다음과 비슷합니다.

[!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

SAMPLEFR 속성 이름을 변경 합니다. 사용 하 여 MKTYPLIB와 프랑스어 해당 하는 IDL 합니다. 프랑스어를 생성 하는 EXE SAMPLEFR 라이브러리를 입력 합니다. TLB 합니다.

여러 지역화 된 형식 라이브러리를 만들려면 어떤 지역화를 추가할 수 있습니다. IDL 파일을 프로젝트 및 이러한 자동으로 생성 됩니다.

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>추가 하는 합니다. ActiveX 컨트롤 프로젝트에 대 한 IDL 파일

1. 컨트롤 프로젝트를 열고에 **프로젝트** 메뉴에서 클릭 **기존 항목 추가**합니다.

   합니다 **기존 항목 추가** 대화 상자가 나타납니다.

1. 필요한 경우에 드라이브 및 디렉터리를 선택 합니다.

1. 에 **파일 형식** 상자에서 **모든 파일 (\*.\*)** .

1. 파일 목록 상자를 두 번 클릭 합니다. IDL 파일을 프로젝트에 삽입 하려고 합니다.

1. 클릭 **열고** 때 필요한 모든 추가 했습니다. IDL 파일입니다.

파일을 프로젝트에 추가한, 때문에 프로젝트의 나머지 부분을 빌드할 때 빌드됩니다. 지역화 된 형식 라이브러리는 현재 ActiveX 컨트롤 프로젝트 디렉터리에 있습니다.

코드 내에서 내부 속성 (일반적으로 영어)에서 항상 사용 하는 이름과 지역화 되지 않습니다. 컨트롤 디스패치 맵, 속성 exchange 함수 및 속성 페이지 데이터 exchange 코드 포함 됩니다.

하나의 형식 라이브러리 (합니다. TLB) 파일 제어 구현 리소스에 바인딩할 수 있습니다 (합니다. OCX) 파일입니다. 이 일반적으로 표준화 된 버전 (일반적으로 영어) 이름입니다. 지역화 된 버전을 제공 하려면 컨트롤을 제공 합니다. OCX (하는 이미 바인딩된 기본값입니다. TLB 버전) 및 합니다. 적절 한 로캘을 TLB 합니다. 이 의미 합니다. 영어 버전에 대 한 올바른 이후 OCX 필요 합니다. 이미 TLB에 바인딩 되었습니다. 다른 로캘에 대해 지역화 된 형식 라이브러리도 함께 제공 되어야 합니다. OCX 합니다.

클라이언트 컨트롤의 지역화 된 형식 라이브러리를 찾을 수 있는지를 확인 하 여 로캘별을 등록 합니다. Windows 시스템 레지스트리 TypeLib 섹션 TLB 파일. 세 번째 매개 변수 (일반적으로 선택 사항)를 [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) 함수는이 목적을 위해 제공 됩니다. 다음 예제에서는 ActiveX 컨트롤에 대 한 프랑스어 형식 라이브러리를 등록합니다.

[!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

컨트롤에 등록 하는 경우는 `AfxOleRegisterTypeLib` 함수는 지정 된 자동으로 찾습니다. 컨트롤로 동일한 디렉터리에 TLB 파일에서 Windows 등록 데이터베이스에 등록 합니다. 경우는 합니다. TLB 파일 없는, 함수에 영향을 주지 않습니다.

##  <a name="_core_localizing_the_control.92.s_user_interface"></a> 컨트롤의 사용자 인터페이스를 지역화합니다.

컨트롤의 사용자 인터페이스를 지역화 하려면 모든 컨트롤의 사용자가 볼 리소스 (예: 속성 페이지와 오류 메시지)를 언어별 리소스 Dll에 배치 합니다. 그런 다음 수 컨테이너의 앰비언트 LocaleID 속성을 사용 하면 사용자의 로캘에 대 한 적절 한 DLL을 선택 합니다.

다음 코드 예제를 찾아 특정 로캘에 대 한 리소스 DLL을 로드 한 가지 방법을 보여 줍니다. 이 멤버 함수를 호출 `GetLocalizedResourceHandle` 예를 들어 ActiveX 컨트롤 클래스의 멤버 함수를 수 있습니다.

[!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

Note switch 문의 보다 전문화 된 지역화를 제공할 경우 각 보조 언어 ID를 확인할 수 있었습니다. 이 함수의 데모를 참조 하세요. 합니다 `GetResourceHandle` 함수에서 MFC ActiveX 컨트롤 샘플 [LOCALIZE](../overview/visual-cpp-samples.md)합니다.

호출할 수 있는 로드 되 면 컨트롤 먼저 자체 컨테이너로 [COleControl::AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid) 로캘 ID를 검색 컨트롤에 반환 된 로캘 ID 값을 전달한 수는 `GetLocalizedResourceHandle` 적절 한 리소스 라이브러리를 로드 하는 함수입니다. 컨트롤이 있는 경우 결과 핸들을 전달 해야 하 [AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):

[!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

위의 코드 샘플의 재정의 같이 컨트롤의 멤버 함수에 배치 [COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite)합니다. 또한 *m_hresdll은 해당* 컨트롤 클래스의 멤버 변수 이어야 합니다.

컨트롤의 속성 페이지의 지역화를 위한 비슷한 논리를 사용할 수 있습니다. 속성 페이지를 지역화 하려면 속성 페이지의 구현 파일에 다음 샘플과 유사한 코드를 추가 (의 재정의 [COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)):

[!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

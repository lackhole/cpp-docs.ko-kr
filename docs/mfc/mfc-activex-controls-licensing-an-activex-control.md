---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스'
ms.date: 11/19/2018
f1_keywords:
- COleObjectFactory
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: eda2ea08c6bd3526befb71c704aa20eba6935b04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392760"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스

지원 라이선스 ActiveX 컨트롤의 선택적 기능으로 지정할 수 있습니다를 사용 하거나 컨트롤을 배포할 수 있습니다. (추가 내용은 라이선스 문제에 대 한 라이선스 문제를 참조 하세요 [기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md).)

> [!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

이 문서에서는 다음 토픽을 설명합니다.

- [ActiveX 컨트롤 라이선스 개요](#_core_overview_of_activex_control_licensing)

- [사용이 허가 된 컨트롤 만들기](#_core_creating_a_licensed_control)

- [라이선스 지원](#_core_licensing_support)

- [ActiveX 컨트롤의 라이선스를 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control)

ActiveX 컨트롤 라이선스를 구현 하는 다른 사용자가 ActiveX 컨트롤을 사용 하는 방법을 결정 하는 컨트롤 개발자로 서를 허용 합니다. 컨트롤과 컨트롤 구매자를 제공 하 고 있습니다. 구매자 컨트롤을 제외한 배포할 수 있습니다 규약과 없음 파일 합니다. 컨트롤을 사용 하는 응용 프로그램을 사용 하 여 없음 파일입니다. 이렇게 하면 첫 번째 사용자 컨트롤 라이선스 없이 컨트롤을 사용 하는 새 응용 프로그램을 작성에서 응용 프로그램의 사용자가 않습니다.

##  <a name="_core_overview_of_activex_control_licensing"></a> ActiveX 컨트롤 라이선스 개요

ActiveX 컨트롤에 대 한 라이선스 지원을 제공 하는 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) 클래스의 여러 함수에 대 한 구현을 제공 합니다 `IClassFactory2` 인터페이스: `IClassFactory2::RequestLicKey`, `IClassFactory2::GetLicInfo`, 및 `IClassFactory2::CreateInstanceLic`. 컨테이너 응용 프로그램 개발자에 대 한 호출 컨트롤의 인스턴스를 만드는 요청을 수행 하는 경우 `GetLicInfo` 되어 있는지 확인 하려고 하는 컨트롤입니다. 없음 파일은 있습니다. 컨트롤의 사용이 허가 되는 경우 컨트롤의 인스턴스 수 만들어지고 컨테이너에 배치 합니다. 컨테이너 응용 프로그램 개발자 완료 된 후 다른 함수 호출,이 이번에 `RequestLicKey`, 이루어집니다. 이 함수는 컨테이너 응용 프로그램 라이선스 키 (단순한 문자 문자열)을 반환합니다. 반환 된 키가 다음 응용 프로그램에 포함 됩니다.

아래 그림에서는 ActiveX 컨트롤 컨테이너 응용 프로그램을 개발 하는 동안 사용할 라이선스 확인을 보여 줍니다. 이전에 설명한 대로 적절 한 컨테이너 응용 프로그램 개발자에 있어야 합니다. 컨트롤의 인스턴스를 만들려면 개발 컴퓨터에 설치-사용권 계약 파일입니다.

![사용이 허가 된 ActiveX 컨트롤이 개발 시 확인 됨](../mfc/media/vc374d1.gif "사용이 허가 된 ActiveX 컨트롤이 개발 시 확인 됨") <br/>
개발 도중 사용이 허가된 ActiveX 컨트롤 확인

다음 그림에 표시 된 다음 프로세스는 최종 사용자는 컨테이너 응용 프로그램을 실행 하는 경우에 발생 합니다.

응용 프로그램이 시작 되 면 컨트롤의 인스턴스는 일반적으로 만들려는 해야 합니다. 컨테이너를 호출 하 여이 수행 `CreateInstanceLic`, 포함 된 라이선스 키를 매개 변수로 전달 합니다. 그런 다음 문자열 비교를 포함 된 라이선스 키와 라이선스 키의 컨트롤의 자체 복사본 간에 이루어집니다. 성공한 일치 하는 경우 컨트롤의 인스턴스 생성 되 고 응용 프로그램 계속 정상적으로 실행 합니다. 유의 합니다. 없음 파일 제어 사용자의 컴퓨터에 없이 필요 합니다.

![사용이 허가 된 ActiveX 컨트롤이 실행 시 확인 됨](../mfc/media/vc374d2.gif "사용이 허가 된 ActiveX 컨트롤이 실행 시 확인 됨") <br/>
실행 도중 사용이 허가된 ActiveX 컨트롤 확인

두 가지 기본 구성 요소로 이루어져 컨트롤 라이선스: DLL 컨트롤 구현에서 특정 코드 및 라이선스 파일. 코드는 두 개 (또는 세 가지 가능한 경우) 함수 호출부터 "라이선스"를 포함 하는 문자열 저작권 표시 라고 하는 문자열의 구성 됩니다. 컨트롤 구현에서 이러한 호출 및 라이선스 문자열 있습니다 (합니다. Cpp) 합니다. ActiveX 컨트롤 마법사에서 생성 한 라이선스 파일에는 저작권 정보를 사용 하 여 텍스트 파일입니다. 라고 하 고 사용 하 여 프로젝트 이름을 사용 하는 합니다. 예를 들어 샘플 없음 확장입니다. 없음입니다. 사용이 허가 된 컨트롤을 디자인 타임에 사용 하 여 필요한 경우 라이선스 파일 수반 되어야 합니다.

##  <a name="_core_creating_a_licensed_control"></a> 사용이 허가 된 컨트롤 만들기

ActiveX 컨트롤 마법사를 사용 하 여 제어 프레임 워크를 만들 때 지원 라이선스를 포함 하기 쉽습니다. 컨트롤이 런타임에 라이선스가 있어야 함을 지정 하는 경우 ActiveX 컨트롤 마법사 라이선스를 지원 하려면 컨트롤 클래스에 코드를 추가 합니다. 라이선스 확인에 대 한 키 및 라이선스 파일을 사용 하는 함수의 코드 구성 됩니다. 또한 이러한 함수는 컨트롤 라이선스를 사용자 지정을 수정할 수 있습니다. 라이선스 사용자 지정에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤의 라이선스를 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control) 이 문서의 뒷부분에 나오는.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>컨트롤 프로젝트를 만들 때 ActiveX 컨트롤 마법사를 사용 하 여 라이선스에 대 한 지원을 추가 하려면

1. 지침을 따르세요 [MFC ActiveX 컨트롤을 만드는](../mfc/reference/creating-an-mfc-activex-control.md)합니다. 합니다 **응용 프로그램 설정** ActiveX 컨트롤 마법사의 페이지 런타임 라이선스를 사용 하 여 컨트롤을 만드는 옵션을 포함 합니다.

ActiveX 컨트롤 마법사에는 이제 기본 라이선스 지원이 포함 된 ActiveX 컨트롤 프레임 워크를 생성 합니다. 라이선스 코드의 자세한 내용은 다음 항목을 참조 하세요.

##  <a name="_core_licensing_support"></a> 라이선스 지원

ActiveX 컨트롤 마법사를 사용 하 여 ActiveX 컨트롤 라이선스 지원을 추가 하는 경우 ActiveX 컨트롤 마법사 선언 하 고 라이선스는 기능을 구현 하는 코드는 추가할 컨트롤 헤더 및 구현 파일을 추가 합니다. 이 코드는 이루어져를 `VerifyUserLicense` 멤버 함수 및 `GetLicenseKey` 에 기본 구현을 재정의 하는 멤버 함수 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) 합니다. 이러한 함수를 검색 하 고 컨트롤 라이선스를 확인 합니다.

> [!NOTE]
>  세 번째 구성원 함수의 경우 `VerifyLicenseKey` ActiveX 컨트롤 마법사에 의해 생성 되지 않습니다 하지만 라이선스 키 확인 동작을 사용자 지정으로 재정의할 수 있습니다.

이러한 멤버 함수는:

- [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   컨트롤 라이선스 파일의 존재에 대 한 시스템을 확인 하 여 디자인 타임에 사용할 컨트롤을 허용 하는지 확인 합니다. 이 함수는 처리의 일부로 프레임 워크에서 호출 됩니다 `IClassFactory2::GetLicInfo` 고 `IClassFactory::CreateInstanceLic`입니다.

- [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   컨트롤 DLL에서에서 고유 키를 요청합니다. 이 키 컨테이너 응용 프로그램에 포함 되며 나중에 함께 사용 `VerifyLicenseKey`, 컨트롤의 인스턴스를 만들려고 합니다. 이 함수는 처리의 일부로 프레임 워크에서 호출 됩니다 `IClassFactory2::RequestLicKey`합니다.

- [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   포함된 된 키와 컨트롤의 고유 키가 동일한 지 확인 합니다. 이렇게 하면 컨테이너 용도 맞게 컨트롤의 인스턴스를 만들 수 있습니다. 이 함수는 처리의 일부로 프레임 워크에서 호출 됩니다 `IClassFactory2::CreateInstanceLic` 라이선스 키의 사용자 지정된 확인을 제공 하려면 재정의할 수 있습니다. 기본 구현에는 문자열 비교를 수행 합니다. 자세한 내용은 [ActiveX 컨트롤의 라이선스를 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control)이 문서의 뒷부분에 나오는.

###  <a name="_core_header_file_modifications"></a> 헤더 파일 수정

ActiveX 컨트롤 마법사 컨트롤 헤더 파일에 다음 코드를 배치합니다. 이 예에서 두 멤버 함수 `CSampleCtrl`개체의 `factory` 를 선언 하는 컨트롤의 현재 상태를 확인 하는 것입니다. 없음 파일 및 다른 컨트롤이 포함 된 응용 프로그램에서 사용할 라이선스 키를 검색 합니다.

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

###  <a name="_core_implementation_file_modifications"></a> 구현 파일 수정

라이선스 파일 이름 및 라이선스 문자열을 선언 하는 컨트롤 구현 파일에 다음 두 문이 배치 하는 ActiveX 컨트롤 마법사:

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
>  수정 하는 경우 `szLicString` 어떤 방식으로든에서 수정 해야 컨트롤의 첫 번째 줄. 파일 없음 또는 라이선스 제대로 작동 하지 않습니다.

컨트롤 클래스를 정의 하는 컨트롤 구현 파일에 다음 코드를 배치 하는 ActiveX 컨트롤 마법사 `VerifyUserLicense` 및 `GetLicenseKey` 함수:

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

마지막으로, 합니다 **ActiveX 컨트롤 마법사** 컨트롤 프로젝트를 수정 합니다. IDL 파일입니다. 합니다 **사용이 허가 된** 키워드는 다음 예제와 같이 컨트롤의 coclass 선언에 추가 됩니다.

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> ActiveX 컨트롤의 라이선스를 사용자 지정

때문에 `VerifyUserLicense`하십시오 `GetLicenseKey`, 및 `VerifyLicenseKey` 컨트롤 팩터리 클래스의 가상 멤버 함수로 선언 된 라이선스 컨트롤의 동작을 사용자 지정할 수 있습니다.

예를 들어, 여러 수준의 재정의 하 여 컨트롤에 대 한 라이선스를 제공할 수 있습니다 합니다 `VerifyUserLicense` 또는 `VerifyLicenseKey` 멤버 함수입니다. 이 함수 안에서 검색 라이선스 수준에 따라 사용자에 게 노출 되는 메서드나 속성을 조정할 수 있습니다.

코드를 추가할 수도 있습니다는 `VerifyLicenseKey` 생성을 제어 하는 사용자에 게 알리는 실패에 대 한 사용자 지정된 메서드를 제공 하는 함수입니다. 예를 들어 프로그램 `VerifyLicenseKey` 멤버 함수는 메시지를 표시할 수 상자 컨트롤을 초기화 하지 않는다는 이유와 합니다.

> [!NOTE]
>  호출 하는 대신 특정 레지스트리 키에 대 한 등록 데이터베이스를 확인 하는 ActiveX 컨트롤 라이선스 확인을 사용자 지정 하는 또 다른 방법은 `AfxVerifyLicFile`합니다. 기본 구현 예제를 참조 하세요. 합니다 [구현 파일 수정](#_core_implementation_file_modifications) 이 문서의 섹션입니다.

추가 내용은 라이선스 문제에 대 한 라이선스 문제를 참조 하세요. [기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md)합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)

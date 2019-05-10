---
title: 인터넷의 ActiveX 컨트롤
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
ms.openlocfilehash: d268da8bef4facfb9259e6ce43648c8713464ec9
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448196"
---
# <a name="activex-controls-on-the-internet"></a>인터넷의 ActiveX 컨트롤

ActiveX 컨트롤은 업데이트 된 버전의 OLE 컨트롤 사양입니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)합니다.

컨트롤은 다양 한 인터넷에서 COM 인식 웹 브라우저를 비롯 한 다른 컨테이너에서에서 사용할 수 있는 프로그래밍 가능한 소프트웨어 구성 요소를 개발 하기 위한 기본 아키텍처입니다. 모든 ActiveX 컨트롤 인터넷 컨트롤 수 및 활성 문서에 해당 기능을 추가 하거나 웹 페이지의 일부가 될 수 있습니다. 컨트롤이 웹 페이지에는 스크립팅을 사용 하 여 서로 통신할 수 있습니다.

ActiveX 컨트롤 인터넷에 제한 되지 않습니다. ActiveX 컨트롤 데도 사용할 수 있습니다 모든 컨테이너에서 컨트롤에서 해당 컨테이너에 필요한 인터페이스를 지원 합니다.

**ActiveX 컨트롤에 다음과 같은 이점을**

- 이전의 OLE 컨트롤 보다 필요한 인터페이스 수가 적습니다.

- 창 없는 수 수와 항상 내부 활성입니다.

**ActiveX 컨트롤에 위해를 제어 해야 합니다.**

- 지원 된 `IUnknown` 인터페이스입니다.

- COM 개체 여야 합니다.

- 내보낼 **DLLRegisterServer** 하 고 **DLLUnRegisterServer**합니다.

- 기능에 대 한 필요에 따라 추가 인터페이스를 지원 합니다.

## <a name="making-your-existing-controls-internet-friendly"></a>인터넷 친화적이 기존 컨트롤 만들기

인터넷에 상대적으로 낮은 전송 속도 대 한 고려 사항이 필요 인터넷 환경에서 잘 작동 하는 컨트롤을 디자인 합니다. 기존 컨트롤;를 사용할 수 있습니다. 그러나는 프로그램 코드 크기를 작게을 비동기적으로 다운로드 하 여 컨트롤 속성을 확인 하려면 수행 해야 하는 단계가 있습니다.

컨트롤의 성능 향상을 위해 효율성 고려 사항에 다음이 팁을 따릅니다.

- 이 문서에서 설명한 기술을 구현 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.

- 어떻게 컨트롤을 인스턴스화하는 것이 좋습니다.

- 비동기; 수 다른 프로그램 보유 하지 마십시오.

- 작은 블록으로에서 데이터를 다운로드 합니다.

   비트맵 또는 비디오 데이터 같은 큰 스트림을 다운로드 하는 경우 컨테이너를 사용 하 여 공동 작업에 비동기적으로 컨트롤의 데이터에 액세스 합니다. 데이터 검색 될 수 있는 다른 컨트롤을 사용 하 여 공동으로 작업 하는 증분 또는 점진적 동기적으로 데이터를 검색 합니다. 코드는 비동기적으로 다운로드 될 수 있습니다.

- 백그라운드에서 속성과 코드를 다운로드 합니다.

- 사용자 인터페이스 될 active 최대한 신속 하 게 합니다.

- 것이 좋습니다 (예: 비트맵 이미지 또는 비디오 데이터) 속성 및 큰 데이터를 Blob 영구 데이터를 저장 하는 방법입니다.

   많은 양의 큰 비트맵 또는 AVI 파일 등의 영구 데이터를 사용 하 여 컨트롤 메서드를 다운로드 하는 데 세심 한 주의 필요 합니다. 문서 또는 페이지를 가능한 한 빨리 표시 됩니다 하 고 사용자 컨트롤은 백그라운드에서 데이터를 검색 하는 동안 페이지와 상호 작용할 수 있도록 수 있습니다.

- 코드 크기를 유지 하 고 실행 시간을 효율적으로 루틴을 작성 합니다.

   작은 단추 및 레이블 컨트롤을 몇 바이트만 영구 데이터를 사용 하 여 인터넷 환경 및 브라우저 내 작업에 적합합니다.

- 진행률이 컨테이너에 전달 하는 것이 좋습니다.

   다운로드가 완료 되 면 사용자는 페이지와 상호 작용을 시작할 수 있는 시기 및 포함 하 여 비동기 다운로드를 진행을 컨테이너를 알립니다. 컨테이너 수 진행률 (예: % % 완료) 사용자에 게 표시 합니다.

- 클라이언트 컴퓨터에 컨트롤을 등록 하는 방법을 고려해 야 합니다.

## <a name="creating-a-new-activex-control"></a>새 ActiveX 컨트롤 만들기

응용 프로그램 마법사를 사용 하는 새 컨트롤을 만들 때 비동기 모니커 뿐만 아니라 다른 최적화에 대 한 지원을 사용 하도록 선택할 수 있습니다. 에 컨트롤 속성을 비동기적으로 다운로드 하는 지원을 추가 하려면 다음이 단계를 수행 합니다.

#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사를 사용 하 여 프로젝트를 만들려면

1. 클릭 **새로 만들기** 에 **파일** 메뉴.

1. 선택 **MFC ActiveX 컨트롤 마법사** Visual Studio에서 C++ 프로젝트 및 프로젝트 이름을 지정 합니다.

1. 에 **제어 설정을** 페이지에서 **속성을 비동기적으로 로드**합니다. 이 옵션을 선택 하면에 대 한 준비 상태 속성 및 준비 상태 변경 이벤트를 설정 합니다.

   다른 최적화와 같은 선택할 수도 있습니다 **창 없는 활성화**에 설명 되어 있습니다 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.

1. 선택할 **완료** 프로젝트를 만듭니다.

#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>CDataPathProperty에서 파생 된 클래스를 만들려면

1. 파생 된 클래스를 만들 `CDataPathProperty`합니다.

1. 각 컨트롤에 대 한 헤더 파일이 포함 된 소스 파일에서 앞에이 클래스에 대 한 헤더 파일을 추가 합니다.

1. 이 클래스에서 재정의 `OnDataAvailable`합니다. 이 함수는 데이터 표시를 위해 가능할 때마다 호출 됩니다. 데이터를 사용할 수 있게 되 면 선택 된 모든 방식, 예를 들어 점진적으로 렌더링 하 여 처리할 수 있습니다.

   다음 코드 부분은 점진적으로 편집 컨트롤에 데이터를 표시 하는 간단한 예입니다. 사용 하 여 플래그 **BSCF_FIRSTDATANOTIFICATION** 편집 컨트롤의 선택을 취소 합니다.

   [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]

   AFXCMN 포함 해야 하는 참고 합니다. H를 사용 하 여 `CListCtrl` 클래스입니다.

1. 컨트롤의 전체 상태 변경 (예를 들어 로드를 초기화 또는 사용자의 대화형)을 호출 `COleControl::InternalSetReadyState`합니다. 컨트롤에 하나의 데이터 요소만 경로 속성을 하는 경우에 코드를 추가할 수 있습니다 **BSCF_LASTDATANOTIFICATION** 다운로드가 완료 되는 컨테이너를 알립니다. 예를 들어:

   [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]

1. `OnProgress`을 재정의합니다. `OnProgress`, 최대 범위를 표시 하는 숫자를 전달 하 고 현재 다운로드의 진행 정도 숫자 표시 됩니다. 사용자에 게 완료율와 같은 상태를 표시 하려면이 숫자를 사용할 수 있습니다.

다음 절차를 컨트롤에 파생 된 클래스를 사용 하 여 속성을 추가 합니다.

#### <a name="to-add-a-property"></a>속성을 추가 하려면

1. **클래스 뷰**, 라이브러리 노드 아래에 있는 인터페이스를 마우스 오른쪽 단추로 **추가**, 한 다음 **속성 추가**합니다. 이렇게 하면 시작 됩니다 합니다 **속성 추가 마법사**합니다.

1. **속성 추가 마법사**를 선택 합니다 **Set/Get 메서드** 라디오 단추, 형식을 **속성 이름**, 예: EditControlText, 및 select BSTR로는 **속성 형식**합니다.

1. **마침**을 클릭합니다.

1. 멤버 변수 선언에 `CDataPathProperty`-ActiveX 컨트롤 클래스를 파생 클래스입니다.

   [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]

1. `Get/Set` 메서드를 구현합니다. 에 대 한 `Get`, 문자열을 반환 합니다. 에 대 한 `Set`, 속성 및 호출 로드 `SetModifiedFlag`합니다.

   [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]

1. [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange), 다음 줄을 추가 합니다.

   [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]

1. 재정의 [ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata) 이 줄을 추가 하 여 해당 컨트롤을 다시 설정할 속성에 알리기 위해:

   [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]

## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>CDataPathProperty 또는 CCachedDataPathProperty 파생 여부 결정

이전 예제에서 컨트롤의 속성을 파생 시키기 위한 단계를 설명 합니다. `CDataPathProperty`합니다. 이 자주 변경 되 고 모든 데이터를 현재 값을 유지 하지 필요가 실시간 데이터를 다운로드 하는 경우에 적합 합니다. 예제 주식 시세 컨트롤입니다.

파생할 수 있습니다 `CCachedDataPathProperty`합니다. 이 경우 다운로드 한 데이터가 메모리 파일에 캐시 됩니다. 모든 다운로드 한 데이터를 유지 해야 할 경우이 좋은 선택-점진적으로 비트맵을 렌더링 하는 컨트롤 예를 들어 있습니다. 이 경우 클래스에 데이터를 포함 하는 멤버 변수:

`CMemFile m_Cache;`

ActiveX 컨트롤 클래스에서이 메모리 매핑된 파일을 사용할 수 있습니다 `OnDraw` 데이터를 표시 합니다. ActiveX 컨트롤에서 `CCachedDataPathProperty`-파생 클래스 멤버 함수를 재정의할 `OnDataAvailable` 하 고 기본 클래스 구현을 호출한 후 컨트롤을 무효화 합니다.

[!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]

## <a name="downloading-data-asynchronously-using-activex-controls"></a>ActiveX 컨트롤을 사용 하 여 비동기적으로 데이터를 다운로드 합니다.

비동기적으로 네트워크를 통해 데이터를 다운로드를 수행 해야 합니다. 이렇게 하면 장점이 따라서 하는 경우 많은 양의 데이터를 전송 하거나 연결이 느린 경우 다운로드 프로세스의 다른 프로세스에서 클라이언트를 차단 하지 것입니다.

비동기 모니커 네트워크를 통해 데이터를 비동기적으로 다운로드 하는 방법을 제공 합니다. 비동기 모니커는 읽기 작업은 작업이 완료 되지 않은 경우에 즉시 반환 합니다.

예를 들어만 10 바이트를 사용할 수 있고 읽기 1k 파일에서 비동기적으로 호출 되는지, 읽기 차단 하지 않지만 현재 사용할 수 있는 10 바이트를 사용 하 여 반환 합니다.

구현할 [비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md) 사용 하는 `CAsyncMonikerFile` 클래스입니다. 그러나 ActiveX 컨트롤을 사용할 수는 `CDataPathProperty` 클래스에서 파생 된 `CAsyncMonikerFile`, 비동기 컨트롤 속성을 구현할 수 있도록 합니다.

## <a name="displaying-a-control-on-a-web-page"></a>웹 페이지에 컨트롤 표시

Object 태그 및 웹 페이지에 컨트롤을 삽입 하는 것에 대 한 특성의 예는 다음과 같습니다.

```xml
<OBJECT
  CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"
  CODEBASE="/ie/download/activex/iechart.ocx"
  ID=chart1
  WIDTH=400
  HEIGHT=200
  ALIGN=center
  HSPACE=0
  VSPACE=0>
  <PARAM NAME="BackColor" value="#ffffff"/>
  <PARAM NAME="ForeColor" value="#0000ff"/>
  <PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt"/>
</OBJECT>
```

## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>ActiveX 컨트롤의 새로운 기능을 사용 하 여 기존 OLE 컨트롤을 업데이트 합니다.

시각적 개체의 버전을 사용 하 여 OLE 컨트롤을 작성 하는 경우 C++ 4.2 이전 단계가 성능 향상을 위한 기능을 향상을 수행할 수 있습니다. 이러한 변경 내용의 자세한 내용은 참조 하세요. [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.

준비 상태 속성을 추가 해야 기존 컨트롤에 비동기 속성 지원을 추가 하는 경우 및 `ReadyStateChange` 이벤트 직접. 컨트롤에 대 한 생성자에서 다음을 추가 합니다.

[!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]

코드를 호출 하 여 다운로드는 준비 상태가 업데이트 됩니다 [COleControl::InternalSetReadyState](../mfc/reference/colecontrol-class.md#internalsetreadystate)합니다. 곳에 호출할 수 있습니다 `InternalSetReadyState` 에서는 `OnProgress` 재정의 `CDataPathProperty`-클래스를 파생 합니다.

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

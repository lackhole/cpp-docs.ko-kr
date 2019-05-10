---
title: MFC ActiveX 컨트롤 마법사, 컨트롤 설정
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.settings
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
ms.openlocfilehash: 34cc49fff88399a6c3cf5f7db71410c88e5c9bab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373286"
---
# <a name="control-settings-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사, 컨트롤 설정

마법사의이 페이지를 사용 하 여 컨트롤이 동작 하는 방법을 지정 합니다. 예를 들어 수 표준 Windows 컨트롤 형식에 컨트롤을 기본, 해당 동작과 모양을 최적화 또는 컨트롤이 다른 컨트롤에 대 한 컨테이너로 작용할 수 있는지를 나타냅니다.

컨트롤의 효율성을 최대화 하기 위해이 페이지의 옵션을 선택 하는 방법에 대 한 자세한 내용은 참조 하세요. [MFC ActiveX 컨트롤: 최적화](../../mfc/mfc-activex-controls-optimization.md)합니다.

## <a name="uielement-list"></a>UI 요소 목록

- **기반으로 하는 컨트롤 만들기**

   이 목록에 컨트롤이 상속 해야 하는 컨트롤의 종류를 선택할 수 있습니다. 목록에 사용할 수 있는 컨트롤 클래스의 하위 집합인 `CreateWindowEx` 및 commctrl.h에 지정 된 공용 컨트롤을 추가 합니다. 선택 영역에서 컨트롤의 스타일을 결정 합니다 `PreCreateWindow` 함수는 *ProjName*Ctrl.cpp 파일입니다. 자세한 내용은 참조 하세요. [MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)합니다.

   |컨트롤|설명|
   |-------------|-----------------|
   |**BUTTON**|Windows 단추 컨트롤|
   |**COMBOBOX**|Windows 콤보 상자 컨트롤|
   |**EDIT**|Windows 편집 상자 컨트롤|
   |**LISTBOX**|Windows 목록 상자 컨트롤|
   |**SCROLLBAR**|Windows 스크롤 막대 컨트롤|
   |**STATIC**|Windows 정적 컨트롤|
   |**msctls_hotkey32**|일반적인 바로 가기 키 컨트롤|
   |**msctls_progress32**|진행률 표시줄 공용 컨트롤|
   |**msctls_statusbar32**|상태 표시줄 공용 컨트롤|
   |**msctls_trackbar32**|공용 컨트롤 막대 추적|
   |**msctls_updown32**|스핀 단추 (또는 위-아래) 공용 컨트롤|
   |**SysAnimate32**|애니메이션 공용 컨트롤|
   |**SysHeader32**|공용 헤더 컨트롤|
   |**SysListView32**|목록 뷰 공용 컨트롤|
   |**SysTabControl32**|공용 탭 컨트롤|
   |**SysTreeView32**|트리 뷰 공용 컨트롤|

- **표시 되었을 때 활성화**

   액세스할 때 컨트롤에 대 한 창을 만들도록 지정 합니다. 기본적으로 **표시 되었을 때 활성화** 옵션을 선택 합니다. 컨테이너에서 필요로 할 (예: 사용자가 마우스를 클릭할 때)까지 제어 활성화를 지연 하려는 경우이 옵션의 선택을 취소 합니다. 이 기능을 해제 하면 필요할 때까지 컨트롤 창 만드는 비용이 발생 하지 않습니다. 자세한 내용은 [때 표시 활성화 옵션 해제](../../mfc/turning-off-the-activate-when-visible-option.md)합니다.

- **런타임에 숨김**

   컨트롤에는 사용자 인터페이스가 없으며 런타임에 지정 합니다. 타이머는 표시 되지 않도록 하려는 경우 컨트롤의 종류입니다.

- **에 정보 대화 상자**

   컨트롤에는 표준 Windows 지정 **에 대 한** 버전 번호 및 저작권 정보를 표시 하는 대화 상자.

   > [!NOTE]
   > 사용자가 액세스 하는 컨트롤에 대 한 도움말을 구현한 방법 도움말 컨테이너 도움말을 사용 하 여 컨트롤 도움말 통합 했는지 여부에 따라 달라 집니다. 도움말을 통합 하는 방법에 대 한 자세한 내용은 합니다 [MSDN Library](http://go.microsoft.com/fwlink/p/?linkid=150542) 웹 사이트에서 "추가 상황에 맞는 도움말에 MFC ActiveX 컨트롤"를 검색 합니다.

   삽입이 옵션을 선택 합니다 `AboutBox` 프로젝트 컨트롤 클래스의 메서드를 제어 (C*ProjName*Ctrl.cpp) AboutBox 프로젝트 디스패치 맵에 추가 합니다. 기본적으로 이 옵션이 선택됩니다.

- **그리기 코드 최적화**

   컨테이너 원래 GDI 개체를 자동으로 복원 후 모든 동일한 장치 컨텍스트로 그려지는 그려진 하는 컨테이너 컨트롤을 지정 합니다. 이 기능에 대 한 자세한 내용은 참조 하세요. [컨트롤 그리기 최적화](../../mfc/optimizing-control-drawing.md)합니다.

- **창 없는 활성화**

   컨트롤이 활성화 될 때 창을 생성 하지 않습니다 지정 합니다. 사각형이 아닌 투명 한 컨트롤에 대 한 창 없는 활성화를 허용 하며 창 없는 컨트롤 기간이 된 컨트롤 보다 적은 시스템 오버 헤드가 필요 합니다. 창 없는 컨트롤 잘리지 않는 장치 컨텍스트 또는 깜빡임 없는 활성화를 허용 하지 않습니다. 1996 년 이전에 만들어진 컨테이너가 창 없는 활성화를 지원 하지 않습니다. 이 옵션을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [창 없는 활성화 제공](../../mfc/providing-windowless-activation.md)합니다.

- **잘리지 않는 장치 컨텍스트**

   재정의 [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) 컨트롤 헤더에서 (*projname*ctrl.h)에 대 한 호출을 사용 하지 않으려면 `IntersectClipRect` 수행한 `COleControl`합니다. 이 옵션을 선택 하면 속도가 약간 빨라집니다를 제공 합니다. 선택 하는 경우 **창 없는 활성화**,이 기능은 사용할 수 없습니다. 자세한 내용은 [잘리지 않는 장치 컨텍스트를 사용 하 여](../../mfc/using-an-unclipped-device-context.md)입니다.

- **깜빡임 없는 활성화**

   그리기 작업 및 깜빡임을 컨트롤의 활성 및 비활성 상태 사이 나타나는 제거 합니다. 선택 하는 경우 **창 없는 활성화**,이 기능은 사용할 수 없습니다. 이 옵션을 설정 하는 경우는 `noFlickerActivate` 플래그를 사용 하 여 반환 되는 플래그를 중 하나인 [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags)합니다. 자세한 내용은 [깜빡임 없는 활성화 제공](../../mfc/providing-flicker-free-activation.md)합니다.

- **개체 삽입 대화 상자에서 사용할 수 있습니다.**

   컨트롤에서 사용할 수 있도록 지정 합니다 **개체 삽입** 활성화 된 컨테이너에 대 한 대화 상자. 이 옵션을 선택 합니다 `afxRegInsertable` 플래그에 의해 반환 된 플래그 중 하나는 `AfxOleRegisterControlClass`합니다. 사용 하 여 합니다 **개체 삽입** 대화 상자에서 새로 만든 삽입할 수 있습니다 하거나 기존 복합 문서로 개체입니다.

- **비활성 상태일 때 마우스 포인터 알림**

   컨트롤의 활성화 여부를 컨트롤을 마우스 포인터 알림 처리할 수 있습니다. 이 옵션을 선택 하면 합니다 `pointerInactive` 플래그를 사용 하 여 반환 되는 플래그를 중 하나인 [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags)합니다. 이 옵션을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [제공 마우스 상호 작용 하는 동안 비활성](../../mfc/providing-mouse-interaction-while-inactive.md)합니다.

- **단순 프레임 컨트롤로 역할**

   컨트롤에 대 한 비트가 OLEMISC_SIMPLEFRAME를 설정 하 여 컨트롤이 다른 컨트롤에 대 한 컨테이너 임을 지정 합니다. 자세한 내용은는 [MSDN Library](http://go.microsoft.com/fwlink/p/?linkid=150542) 웹 사이트에서 "간단한 프레임 사이트 포함 항목"를 검색 합니다.

- **속성을 비동기적으로 로드**

   이전 비동기 데이터를 다시 설정 하 고 컨트롤의 비동기 속성의 새 부하를 시작 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[애플리케이션 설정, MFC ActiveX 컨트롤 마법사](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[MFC ActiveX 컨트롤 마법사, 컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md)

---
title: 모양, ATL 컨트롤 마법사
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 4d3b0519951636fad4175dc35261ba35b3694ffa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248955"
---
# <a name="appearance-atl-control-wizard"></a>모양, ATL 컨트롤 마법사

마법사의이 페이지를 사용 하 여 컨트롤에 대 한 추가 사용자 요소 옵션을 식별 합니다. 로 식별 되는 컨트롤에 대 한이 페이지는 **표준 컨트롤** 아래에서 **컨트롤 형식과** 에 [옵션, ATL 컨트롤 마법사](../../atl/reference/options-atl-control-wizard.md) 페이지입니다.

## <a name="uielement-list"></a>UI 요소 목록

- **상태 보기**

   컨테이너 내의 컨트롤의 모양을 설정합니다.

   - **불투명**: 비트 VIEWSTATUS_OPAQUE 설정 합니다 [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) 열거 및에 전달 된 전체 컨트롤 사각형을 그립니다 합니다 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) 메서드. 컨트롤 완전히 불투명 나타나고 컨트롤 경계 뒤 컨테이너 하나도 보여 줍니다.

      이 컨테이너 컨트롤을 더 빠르게 그릴 수 있습니다. 이 옵션을 선택 하지 않으면 컨트롤이 투명 한 부분을 포함할 수 있습니다.

      불투명 컨트롤에만 단색 배경이 있을 수 있습니다.

   - **단색 배경**: VIEWSTATUS 열거형 비트 VIEWSTATUS_SOLIDBKGND를 설정 합니다. 컨트롤의 배경 패턴을 사용 하 여 단색으로 표시 됩니다.

      이 옵션은 사용할 경우에만 **불투명** 옵션도 선택 되어 있습니다.

- **컨트롤 추가 기준**

   컨트롤이 추가 하 여 Windows 컨트롤 형식에 따라 수를 설정 된 [CContainedWindow](ccontainedwindowt-class.md) 컨트롤을 구현 하는 클래스 데이터 멤버입니다. 또한 메시지 맵 및 메시지 처리기 함수 컨트롤에 대 한 Windows 메시지 처리를 추가 합니다. Windows 컨트롤을 만들려고 할 수 있는 경우의 형식 목록에서 선택 합니다.

   - **Button**

   - **ListBox**

   - **SysAnimate32**

   - **SysListView32**

   - **ComboBox**

   - **RichEdit**

   - **SysDateTimePick32**

   - **SysMonthCal32**

   - **ComboBoxEx32**

   - **ScrollBar**

   - **SysHeader32**

   - **SysTabControl32**

   - **편집**

   - **정적**

   - **SysIPAddress32**

   - **SysTreeView32**

- **기타 상태**

   컨트롤에 대 한 추가 모양 및 동작 옵션을 설정합니다.

   - **런타임에 보이지 않는**: 런타임 시 표시 되지 않도록 하려면 컨트롤을 설정 합니다. 시간 제한 간격 이벤트를 발생 시키고 같은 백그라운드에서 작업을 수행할 보이지 않는 컨트롤을 사용할 수 있습니다.

   - **단추와 같은 역할**: 비트 OLEMISC_ACTSLIKEBUTTON를 설정 합니다 [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) 열거형 컨트롤 역할을 사용 하도록 설정 하려면 같은 단추입니다. 컨테이너가 기본 단추 컨트롤의 클라이언트 사이트에 표시 하는 경우이 옵션을 선택 하면 두꺼운 프레임 그려지고 기본 단추로 표시 되도록 단추 컨트롤이 사용 하도록 설정 합니다. 참조 [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) 자세한 내용은 합니다.

   - **레이블 처럼 작동**: 컨테이너의 기본 레이블을 바꿀 컨트롤을 사용 하도록 설정 하려면 OLEMISC_ACTSLIKELABEL OLEMISC 열거형에서 비트를 설정 합니다. 컨테이너 경우 아무 것도이 플래그를 사용 하 여 수행할 작업을 결정 합니다.

- **기타**

   컨트롤에 대 한 추가 동작 옵션을 설정합니다.

   - **DC 정규화**: 정규화 된 장치 컨텍스트를 자신을 그리는 호출 될 때 만들 컨트롤을 설정 합니다. 이 작업은 컨트롤의 모양 표준화 되지만 그리기 덜 효율적입니다.

   - **창 에서만**: 컨트롤이 창 없는 일 수 없음을 지정 합니다. 이 옵션을 선택 하지 않으면 컨트롤은 창 없는 개체를 지 원하는 컨테이너의 자동 창 및 컨테이너 창 없는 개체를 지원 하지 않는 것입니다. 이 옵션을 선택 하면 창 없는 개체를 지 원하는 컨테이너에도 기간 이동 되는 컨트롤을 강제로 수행 합니다.

   - **삽입**: 컨트롤에 표시 하려면이 옵션을 선택 합니다 **개체 삽입** Word 및 Excel 같은 응용 프로그램의 대화 상자. 그런 다음이 대화 상자를 통해 포함 된 개체를 지 원하는 응용 프로그램에서 컨트롤을 삽입할 수 있습니다.

## <a name="see-also"></a>참고자료

[ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)<br/>
[샘플 SUBEDIT: 표준 Windows 컨트롤의 슈퍼 클래스](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)

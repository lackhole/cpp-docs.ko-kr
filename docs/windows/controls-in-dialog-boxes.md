---
title: 대화 상자 컨트롤 (c + +) | Microsoft Docs
ms.date: 02/15/2019
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls [C++], about dialog box controls
- dialog box controls
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
ms.openlocfilehash: 563cf73299c00413889ada2520b1bf4fcd86f2be
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023700"
---
# <a name="dialog-box-controls-c"></a>대화 상자 컨트롤 (c + +)

사용 하 여 대화 상자 컨트롤을 추가할 수 있습니다는 **대화 상자 편집기** 탭에 [도구 상자 창](/visualstudio/ide/reference/toolbox) 원하는 대화 상자에 끌어 놓기 컨트롤을 선택할 수 있도록 합니다. 기본적으로 **도구 상자** 창은 자동 숨기기로 설정 됩니다. 솔루션의 왼쪽된 여백에 탭으로 나타납니다 때 합니다 **대화 상자 편집기** 열려 있습니다. 고정할 수 있습니다는 **도구 상자** 위치를 선택 하 여 창 합니다 **자동 숨기기** 창의 오른쪽 위 모퉁이의 단추입니다. 이 창의 동작을 제어 하는 방법에 대 한 자세한 내용은 참조 하세요. [창 관리](/visualstudio/ide/customizing-window-layouts-in-visual-studio)합니다.

대화 상자에 컨트롤을 추가, 기존 컨트롤의 위치를 변경 하거나 다른 하나의 대화 상자에서 컨트롤을 이동 하는 가장 빠른 방법은 끌어서 놓기 메서드를 사용 하는 것입니다. 컨트롤의 위치는 대화 상자에 놓을 때까지 점선에 설명 된 합니다. 끌어서 놓기 메서드를 사용 하 여 대화 상자에 컨트롤을 추가 하면 컨트롤의 해당 형식에 적합 한 표준 높이 컨트롤에 지정 됩니다.

대화 상자에 컨트롤을 추가 하거나 위치를 변경할 때 가이드 또는 여백에서의 최종 위치를 확인할 수 있습니다 또는 레이아웃 모눈 켜져 있는지 여부입니다.

대화 상자에 컨트롤을 추가한 후에 해당 캡션 등의 속성을 변경할 수 있습니다 합니다 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 여러 컨트롤을 선택 하 고 해당 속성을 한 번에 변경할 수도 있습니다.

대 한 자세한 내용은 합니다 **대화 상자 편집기**를 참조 하는 방법 [추가, 편집 또는 삭제 컨트롤](adding-editing-or-deleting-controls.md), [레이아웃 컨트롤](../windows/arrangement-of-controls-on-dialog-boxes.md), 및 [정의 대 한 액세스 제어 및 값](../windows/defining-mnemonics-access-keys.md).

컨트롤 및 대화 상자에 대 한 자세한 내용은 참조 하세요. [컨트롤 클래스](../mfc/control-classes.md)하십시오 [대화 상자 클래스](../mfc/dialog-box-classes.md), 및 [스크롤 막대 스타일](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)합니다.

사용할 수 있는 표준 컨트롤을 **도구 상자** 이벤트와 기본:

|컨트롤 이름|기본 이벤트|
|---|---|
|[Button 컨트롤](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[확인란 컨트롤](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[콤보 상자 컨트롤](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[편집 컨트롤](../mfc/reference/cedit-class.md)|EN_CHANGE|
|그룹 상자|(해당 사항 없음)|
|[목록 상자 컨트롤](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[라디오 단추 컨트롤](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[정적 텍스트 컨트롤](../mfc/reference/cstatic-class.md)|(해당 사항 없음)|
|[그림 컨트롤](../mfc/reference/cpictureholder-class.md)|(해당 사항 없음)|
|[Rich Edit 2.0 컨트롤](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[스크롤 막대 컨트롤](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

> [!NOTE]
> 사용 하 여 대 한 자세한 내용은 합니다 **RichEdit 1.0** MFC를 사용 하 여 컨트롤을 참조 하세요 [MFC에 RichEdit 1.0 컨트롤 사용](../windows/using-the-richedit-1-0-control-with-mfc.md) 하 고 [서식 있는 편집 컨트롤 예](../mfc/rich-edit-control-examples.md)합니다.

[Windows 공용 컨트롤](../mfc/controls-mfc.md) 에서 사용할 수 있는 합니다 **도구 상자** 향상 된 기능은 제공:

|컨트롤 이름|기본 이벤트|
|---|---|
|[Slider 컨트롤](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[Spin 컨트롤](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[Progress 컨트롤](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[Hot Key 컨트롤](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[목록 컨트롤](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[트리 컨트롤](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[탭 컨트롤](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[애니메이션 컨트롤](../mfc/using-an-animation-control.md)|ACN_START|
|[날짜 시간 선택 컨트롤](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[MonthCalendar 컨트롤](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP 주소 컨트롤](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[확장된 콤보 상자 컨트롤](../mfc/creating-an-extended-combo-box-control.md)||
|사용자 지정 컨트롤|TTN_GETDISPINFO|

## <a name="custom-controls"></a>사용자 지정 컨트롤

합니다 **대화 상자 편집기** 사용 하 여 기존 사용자 지정 또는 사용자 정의 컨트롤을 대화 상자 템플릿에 수 있습니다.

> [!NOTE]
> 여기서 사용자 지정 컨트롤 ActiveX 컨트롤을 혼동 해서는 안 됩니다. ActiveX 컨트롤 된 OLE 사용자 지정 컨트롤이 라고도 합니다. 또한 Windows에서 소유자가 그린 컨트롤을 사용 하 여 이러한 컨트롤을 혼동 하지 마세요.

이 기능은 Windows에서 제공 하지 않는 컨트롤을 사용할 수 있게 됩니다. 런타임 시 컨트롤 (같지 c + + 클래스로) 창 클래스를 사용 하 여 연결 됩니다. 동일한 작업을 수행 하는 보다 일반적인 방법은 대화 상자에서 정적 컨트롤과 같은 모든 컨트롤을 설치 하는 것입니다. 그런 다음 런타임에만는 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수, 해당 컨트롤을 제거 및 사용자 고유의 사용자 지정 컨트롤을 대신 합니다.

> [!NOTE]
> 이것이 오래 된 기술입니다. 지금 시켜야 하는 대부분의 경우에서 ActiveX 컨트롤 또는 Windows 공용 컨트롤을 서브 클래스를 작성 합니다.

이러한 사용자 지정 컨트롤에 대 한 개로 제한 됩니다.

- 대화 상자에서 위치를 설정 합니다.

- 캡션을 입력 합니다.

- 응용 프로그램 코드는이 이름으로 컨트롤을 등록 해야 하므로 컨트롤의 Windows 클래스의 이름을 식별 합니다.

- 컨트롤의 스타일을 설정 하는 32 비트 16 진수 값을 입력 합니다.

- 확장된 스타일을 설정 합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[대화 상자 편집기](../windows/dialog-editor.md)<br/>

<!--
[Adding Event Handlers for Dialog Box Controls](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Controls](../mfc/controls-mfc.md)<br/>-->
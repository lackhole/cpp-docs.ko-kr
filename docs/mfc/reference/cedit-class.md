---
title: CEdit Class
ms.date: 09/12/2018
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
ms.openlocfilehash: 295a58a86f35fca3b8d25706857162facc9cb3ea
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503742"
---
# <a name="cedit-class"></a>CEdit Class

Windows 편집 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CEdit : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CEdit::CEdit](#cedit)|생성 된 `CEdit` 컨트롤 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CEdit::CanUndo](#canundo)|편집 컨트롤 작업을 실행 취소할 수 있는지 여부를 결정 합니다.|
|[CEdit::CharFromPos](#charfrompos)|지정된 된 위치에 가장 가까운 문자에 대 한 줄과 문자 인덱스를 검색합니다.|
|[CEdit::Clear](#clear)|삭제 (삭제) 편집에서 현재 선택 (있을 경우)를 제어 합니다.|
|[CEdit::Copy](#copy)|현재 선택 영역 (있는 경우) 편집 컨트롤의 클립보드에 복사 CF_TEXT 형식에서입니다.|
|[CEdit::Create](#create)|Windows 편집 컨트롤을 만들고에 연결 된 `CEdit` 개체입니다.|
|[CEdit::Cut](#cut)|삭제 (구분) 편집에서 현재 선택 (있을 경우) 제어 하 고 복사본 CF_TEXT 클립보드에 삭제 한 텍스트 서식을 지정 합니다.|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|한 편집 실행 취소 플래그 (지우기) 컨트롤을 다시 설정합니다.|
|[CEdit::FmtLines](#fmtlines)|여러 줄 편집 컨트롤 내에서 소프트 줄 바꿈 문자를 포함 또는 해제를 설정합니다.|
|[CEdit::GetCueBanner](#getcuebanner)|텍스트 큐 또는 컨트롤 비어 있고 포커스가 없을 때 편집 컨트롤에 팁으로 표시 되는 텍스트를 검색 합니다.|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|편집 컨트롤에 표시 되는 맨 위 줄을 확인합니다.|
|[CEdit::GetHandle](#gethandle)|여러 줄 편집 컨트롤에 현재 할당 된 메모리에 대 한 핸들을 검색 합니다.|
|[CEdit::GetHighlight](#gethighlight)|시작 및 끝 문자 현재 편집 컨트롤에 강조 표시 되는 텍스트 범위에 있는 인덱스를 가져옵니다.|
|[CEdit::GetLimitText](#getlimittext)|이 텍스트의 최대 크기를 가져옵니다 `CEdit` 포함 될 수 있습니다.|
|[CEdit::GetLine](#getline)|편집 컨트롤에서 텍스트 줄을 검색합니다.|
|[CEdit::GetLineCount](#getlinecount)|여러 줄 편집 컨트롤의 줄 번호를 검색합니다.|
|[CEdit::GetMargins](#getmargins)|이 대 한 왼쪽 및 오른쪽 여백을 가져옵니다 `CEdit`합니다.|
|[CEdit::GetModify](#getmodify)|편집 컨트롤의 내용이 수정 되었으면 여부를 결정 합니다.|
|[CEdit::GetPasswordChar](#getpasswordchar)|사용자가 텍스트를 입력 하면 편집 컨트롤에 표시 되는 암호 문자를 검색 합니다.|
|[CEdit::GetRect](#getrect)|편집 컨트롤의 서식 지정 사각형을 가져옵니다.|
|[CEdit::GetSel](#getsel)|편집 컨트롤에서 현재 선택 영역의 첫 번째 및 마지막 문자 위치를 가져옵니다.|
|[CEdit::HideBalloonTip](#hideballoontip)|현재 편집 컨트롤과 연결 된 모든 풍선을 숨깁니다.|
|[CEdit::LimitText](#limittext)|편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 합니다.|
|[CEdit::LineFromChar](#linefromchar)|지정된 된 문자 인덱스를 포함 하는 줄의 줄 번호를 검색 합니다.|
|[CEdit::LineIndex](#lineindex)|여러 줄 편집 컨트롤 내에서 줄의 문자 인덱스를 검색합니다.|
|[CEdit::LineLength](#linelength)|편집 컨트롤에서 줄의 길이 검색합니다.|
|[CEdit::LineScroll](#linescroll)|여러 줄 편집 컨트롤의 텍스트를 스크롤합니다.|
|[CEdit::Paste](#paste)|현재 커서 위치에 있는 편집 컨트롤로 클립보드의 데이터를 삽입합니다. 클립보드 CF_TEXT 형식으로 데이터를에서 포함 하는 경우에 데이터가 삽입 됩니다.|
|[CEdit::PosFromChar](#posfromchar)|지정 된 문자 인덱스의 왼쪽 위 모퉁이의 좌표를 검색합니다.|
|[CEdit::ReplaceSel](#replacesel)|지정 된 텍스트 편집 컨트롤에서 현재 선택 영역을 대체합니다.|
|[CEdit::SetCueBanner](#setcuebanner)|텍스트 큐 또는 컨트롤 비어 있고 포커스가 없을 때 편집 컨트롤에 팁으로 표시 되는 텍스트를 설정 합니다.|
|[CEdit::SetHandle](#sethandle)|여러 줄 편집 컨트롤에서 사용 될 로컬 메모리에 핸들을 설정 합니다.|
|[CEdit::SetHighlight](#sethighlight)|현재에서 표시 되는 텍스트 범위를 강조 표시 컨트롤을 편집 합니다.|
|[CEdit::SetLimitText](#setlimittext)|이 텍스트의 최대 크기를 설정 `CEdit` 포함 될 수 있습니다.|
|[CEdit::SetMargins](#setmargins)|왼쪽 및 오른쪽 여백을 설정 하 고이 대 한 `CEdit`합니다.|
|[CEdit::SetModify](#setmodify)|설정 하거나 편집 컨트롤에 대 한 수정 플래그를 지웁니다.|
|[CEdit::SetPasswordChar](#setpasswordchar)|설정 하거나 사용자가 텍스트를 입력 하면 편집 컨트롤에 표시 되는 암호 문자를 제거 합니다.|
|[CEdit::SetReadOnly](#setreadonly)|편집 컨트롤의 읽기 전용 상태를 설정합니다.|
|[CEdit::SetRect](#setrect)|여러 줄 편집 컨트롤의 서식 지정 영역을 설정 하 고 컨트롤을 업데이트 합니다.|
|[CEdit::SetRectNP](#setrectnp)|컨트롤 창을 다시 그릴 필요 없이 여러 줄 편집 컨트롤의 서식 지정 영역을 설정 합니다.|
|[CEdit::SetSel](#setsel)|편집 컨트롤에서 문자 범위를 선택합니다.|
|[CEdit::SetTabStops](#settabstops)|여러 줄에서의 탭 정지 설정 편집 컨트롤입니다.|
|[CEdit::ShowBalloonTip](#showballoontip)|현재 편집 컨트롤과 연결 된 풍선 설명을 표시 합니다.|
|[CEdit::Undo](#undo)|마지막 편집 컨트롤 작업을 취소합니다.|

## <a name="remarks"></a>설명

편집 컨트롤에는 사용자가 텍스트를 입력할 수 있는 사각형 자식 창입니다.

대화 상자 템플릿에서 또는 코드에서 직접 편집 컨트롤을 만들 수 있습니다. 두 경우 모두 먼저 생성자를 호출 `CEdit` 생성 하는 `CEdit` 개체를 만든 다음 호출 합니다 [만들기](#create) 멤버 함수는 Windows를 만들려면 편집 컨트롤 및 연결을 `CEdit` 개체.

생성 1 단계 프로세스에서 파생 된 클래스 수 `CEdit`입니다. 파생된 클래스 및 호출에 대 한 생성자 작성 `Create` 에서 생성자 내에서.

`CEdit` 중요 한 기능을 상속 `CWnd`합니다. 설정 및 텍스트를 검색 하는 `CEdit` 개체를 `CWnd` 멤버 함수 [SetWindowText](cwnd-class.md#setwindowtext) 및 [GetWindowText](cwnd-class.md#getwindowtext), 편집의 전체 내용을 제어는 set 또는 get, 경우에도 것 여러 줄로 된 컨트롤이입니다. 여러 줄로 된 컨트롤의 텍스트 줄 문자 시퀀스 '\r\n'로 구분 됩니다. 또한 여러 줄 편집 컨트롤을 이면 가져오고 호출 하 여 컨트롤의 텍스트 부분을 설정 합니다 `CEdit` 멤버 함수 [GetLine](#getline)를 [SetSel](#setsel)를 [GetSel](#getsel), 및 [ ReplaceSel](#replacesel)합니다.

편집 컨트롤에서 해당 부모에 보냅니다 Windows 알림 메시지를 처리 하려는 경우 (일반적으로 클래스에서 파생 `CDialog`), 각 메시지에 대 한 부모 클래스에는 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다.

각 메시지 맵 항목은 다음 형식을 사용 합니다.

  **ON_** _NOTIFICATION_ **(** _id_ **,** _memberFxn_ **)**

여기서 `id` 알림을 전송 하는 편집 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하는 것이 기록한 부모 멤버 함수의 이름입니다.

부모의 함수 프로토타입에 다음과 같습니다.

**afx_msg** void memberFxn **( );**

다음은 잠재적인 메시지 맵 항목 및 부모로 전송 되는 있는 경우에 대 한 설명을의 목록.

- ON_EN_CHANGE 사용자 편집 컨트롤의 텍스트를 변경할 수 있는 작업을 수행 했습니다. EN_UPDATE 알림 메시지와 달리 Windows 업데이트를 표시 하 고 나면이 알림 메시지 전송 됩니다.

- 편집 컨트롤 ON_EN_ERRSPACE 특정 요청에 맞게 충분 한 메모리를 할당할 수 없습니다.

- ON_EN_HSCROLL 사용자가 편집 컨트롤의 가로 스크롤 막대를 클릭합니다. 부모 창에는 화면 업데이트 되기 전에 알림이 전송 됩니다.

- ON_EN_KILLFOCUS 편집 컨트롤에 입력된 포커스를 잃게 됩니다.

- 현재 삽입 ON_EN_MAXTEXT 지정된 편집 컨트롤에 대 한 문자 수를 초과 했습니다 및 잘렸습니다. ES_AUTOHSCROLL 스타일의 편집 컨트롤에 없는 및 삽입할 문자 수에는 편집 컨트롤의 너비를 초과 하는 경우에 전달 합니다. ES_AUTOVSCROLL 스타일의 편집 컨트롤에 없는 및 텍스트 삽입을에서 발생 하는 줄의 총 편집 컨트롤의 높이 초과 하는 경우에 전달 합니다.

- ON_EN_SETFOCUS 편집 컨트롤이 입력된 포커스를 받을 때 전송 합니다.

- ON_EN_UPDATE 편집 컨트롤을 변경 하는 표시 텍스트입니다. 컨트롤에 텍스트의 서식을 지정한 되었으나 해당 화면 텍스트 창 크기를 변경할 수 있도록 필요에 따라 전송 합니다.

- ON_EN_VSCROLL 사용자가 편집 컨트롤의 세로 스크롤 막대를 클릭합니다. 부모 창에는 화면 업데이트 되기 전에 알림이 전송 됩니다.

만드는 경우는 `CEdit` 대화 상자 내에서 개체를 `CEdit` 개체에는 사용자가 대화 상자를 닫으면 자동으로 제거 됩니다.

만드는 경우는 `CEdit` 대화 상자 편집기를 사용 하 여 대화 상자 리소스의 개체는 `CEdit` 개체에는 사용자가 대화 상자를 닫으면 자동으로 제거 됩니다.

만드는 경우는 `CEdit` 창 내에서 개체 삭제 해야 합니다. 만드는 경우는 `CEdit` 개체 스택에 자동으로 제거 됩니다. 만드는 경우는 `CEdit` 를 사용 하 여 힙에 있는 개체에는 **새** 를 호출 해야 함수를 **삭제** 사용자는 Windows 종료 될 때 소멸 시킬 개체에서 컨트롤을 편집 합니다. 메모리를 할당 하는 경우는 `CEdit` 개체를 재정의 합니다 `CEdit` 소멸자는 할당을 삭제 합니다.

편집 컨트롤 (예: ES_READONLY)에서 특정 스타일을 수정 하려면 사용 하는 대신 컨트롤에 특정 메시지를 전송 해야 [ModifyStyle](cwnd-class.md#modifystyle)합니다. 참조 [컨트롤 스타일 편집](/windows/desktop/Controls/edit-control-styles) Windows SDK에에서 있습니다.

에 대 한 자세한 `CEdit`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="canundo"></a>  CEdit::CanUndo

마지막 편집 작업을 취소할 수는 경우를 결정 하는이 함수를 호출 합니다.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>반환 값

마지막 편집 작업을 호출 하 여 실행 취소할 수 있는 경우 0이 아닌는 `Undo` 멤버 함수, 작업은 실행 취소할 수 없는 경우 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [EM_CANUNDO](/windows/desktop/Controls/em-canundo) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::Undo](#undo)합니다.

##  <a name="cedit"></a>  CEdit::CEdit

`CEdit` 개체를 생성합니다.

```
CEdit();
```

### <a name="remarks"></a>설명

사용 하 여 [만들기](#create) 생성 하는 Windows 컨트롤을 편집 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

##  <a name="charfrompos"></a>  CEdit::CharFromPos

0부터 시작 줄 및이 지정된 된 점 가장 가까운 문자의 문자 인덱스를 검색 하려면이 함수를 호출 `CEdit` 컨트롤

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
이 클라이언트 영역에 있는 지점의 좌표 `CEdit` 개체입니다.

### <a name="return-value"></a>반환 값

하위 단어의 문자 인덱스 및 상위 WORD에서 줄 인덱스입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 [EM_CHARFROMPOS](/windows/desktop/Controls/em-charfrompos) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

##  <a name="clear"></a>  CEdit::Clear

삭제 하려면 (clear) 현재 선택 영역 (있는 경우) 편집 컨트롤에서이 함수를 호출 합니다.

```
void Clear();
```

### <a name="remarks"></a>설명

수행한 삭제 `Clear` 를 호출 하 여 실행 취소할 수는 [취소](#undo) 멤버 함수입니다.

현재 선택 영역을 삭제 하 고 삭제 된 내용을 클립보드에 배치 하려면 호출을 [잘라내기](#cut) 멤버 함수입니다.

자세한 내용은 [WM_CLEAR](/windows/desktop/dataxchg/wm-clear) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

##  <a name="copy"></a>  CEdit::Copy

이 함수를 호출 복사 하려면 현재 선택 영역 (있는 경우) CF_TEXT 형식으로 클립보드에 편집 컨트롤에 있습니다.

```
void Copy();
```

### <a name="remarks"></a>설명

자세한 내용은 [WM_COPY](/windows/desktop/dataxchg/wm-copy) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

##  <a name="create"></a>  CEdit::Create

Windows 편집 컨트롤을 만들고에 연결 된 `CEdit` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
편집 컨트롤의 스타일을 지정합니다. 어떤 조합도 적용할 [스타일 편집](styles-used-by-mfc.md#edit-styles) 컨트롤입니다.

*rect*<br/>
편집 컨트롤의 크기와 위치를 지정합니다. 수는 `CRect` 개체 또는 `RECT` 구조입니다.

*pParentWnd*<br/>
지정 된 편집 컨트롤의 부모 창 (일반적으로 `CDialog`). NULL이 아니어야 합니다.

*nID*<br/>
편집 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CEdit` 두 단계에서 개체입니다. 먼저 호출 된 `CEdit` 생성자를 호출 하 고 `Create`, Windows 편집 컨트롤을 만들고 연결 하는 `CEdit` 개체입니다.

때 `Create` 보냅니다 Windows를 실행 합니다 [WM_NCCREATE](/windows/desktop/winmsg/wm-nccreate), [WM_NCCALCSIZE](/windows/desktop/winmsg/wm-nccalcsize)를 [WM_CREATE](/windows/desktop/winmsg/wm-create), 및 [WM_GETMINMAXINFO](/windows/desktop/winmsg/wm-getminmaxinfo) 편집 컨트롤에 대 한 메시지입니다.

기본적으로 이러한 메시지의 처리를 [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize)합니다 [OnCreate](cwnd-class.md#oncreate), 및 [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) 멤버 함수 에 `CWnd` 기본 클래스입니다. 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CEdit`메시지 맵을 새 클래스를 추가 하 고 위의 메시지 처리기 멤버 함수를 재정의 합니다. 재정의 `OnCreate`, 예를 들어, 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.

다음 적용 [창 스타일](styles-used-by-mfc.md#window-styles) 편집 컨트롤입니다.

- WS_CHILD 항상

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의

- 그룹 컨트롤에 WS_GROUP

- WS_TABSTOP 탭 이동 순서에 편집 컨트롤을 포함 하려면

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

##  <a name="cut"></a>  CEdit::Cut

편집 컨트롤에 현재 선택 영역 (있는 경우) (잘라내기)을 삭제 하려면이 함수를 호출 하 고 CF_TEXT 형식으로 클립보드에 삭제 된 텍스트를 복사 합니다.

```
void Cut();
```

### <a name="remarks"></a>설명

수행한 삭제 `Cut` 를 호출 하 여 실행 취소할 수는 [취소](#undo) 멤버 함수입니다.

삭제 된 텍스트를 클립보드에 배치 하지 않고 현재 선택 영역을 삭제 하려면 다음을 호출 합니다 [지우기](#clear) 멤버 함수입니다.

자세한 내용은 [WM_CUT](/windows/desktop/dataxchg/wm-cut) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer

편집 컨트롤의 실행 취소 플래그 (지우기)를 다시 설정 하려면이 함수를 호출 합니다.

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>설명

편집 컨트롤은 이제 없게 마지막 작업을 취소할 수 있습니다. 편집 컨트롤 내에서 작업을 취소할 수 때마다 실행 취소 플래그가 설정 됩니다.

실행 취소 플래그는 자동으로 때마다 삭제를 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) 또는 [SetHandle](#sethandle) `CWnd` 멤버 함수가 호출 됩니다.

자세한 내용은 [EM_EMPTYUNDOBUFFER](/windows/desktop/Controls/em-emptyundobuffer) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

##  <a name="fmtlines"></a>  CEdit::FmtLines

여러 줄 편집 컨트롤 내에서 소프트 줄 바꿈 문자를 포함 또는 해제를 설정 하려면이 함수를 호출 합니다.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>매개 변수

*bAddEOL*<br/>
소프트 줄 바꿈 문자를 삽입할 수 있는지 여부를 지정 합니다. 값이 true 이면; 문자를 삽입합니다. FALSE 값으로 제거합니다.

### <a name="return-value"></a>반환 값

있는 경우 0이 아닌 서식 지정 발생 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 개의 캐리지 리턴 및 줄 바꿈 인해 중단 된 줄의 끝에 삽입 하는 줄 바꿈 소프트 줄 바꿈을 구성 됩니다. 하드 줄 바꿈을 하나 캐리지 리턴 및 줄 바꿈 이루어져 있습니다. 하드 줄 바꿈을 끝나는 줄 영향을 받지 않는 `FmtLines`합니다.

경우에 Windows 응답할는 `CEdit` 개체는 여러 줄 편집 컨트롤입니다.

`FmtLines` 반환 되는 버퍼에만 영향을 [GetHandle](#gethandle) 반환한 텍스트가 [WM_GETTEXT](/windows/desktop/winmsg/wm-gettext)합니다. 있기 편집 컨트롤 내의 텍스트의 표시에 영향을 주지 않습니다.

자세한 내용은 [EM_FMTLINES](/windows/desktop/Controls/em-fmtlines) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

##  <a name="getcuebanner"></a>  CEdit::GetCueBanner

텍스트 큐 또는 컨트롤 비어 있을 때 편집 컨트롤에 팁으로 표시 되는 텍스트를 검색 합니다.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
[out] 큐 텍스트를 포함 하는 문자열에 대 한 포인터입니다.

*cchText*<br/>
[in] 받을 수 있는 문자의 수입니다. 이 수에는 NULL 종결 문자 포함 됩니다.

### <a name="return-value"></a>반환 값

첫 번째 오버 로드에 대 한 메서드가 성공할 경우 TRUE 그렇지 않으면 FALSE입니다.

두 번째 오버 로드에 대 한는 [CString](../../atl-mfc-shared/using-cstring.md) 방법이 고, 그렇지 않으면 성공한 경우 큐 텍스트를 포함 하는 빈 문자열 ("").

### <a name="remarks"></a>설명

이 메서드는 전송 된 [EM_GETCUEBANNER](/windows/desktop/Controls/em-getcuebanner) Windows SDK에 설명 된 메시지입니다. 자세한 내용은 참조는 [Edit_GetCueBannerText](/windows/desktop/api/commctrl/nf-commctrl-edit_getcuebannertext) 매크로입니다.

##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine

편집 컨트롤에 표시 되는 맨 위 줄을 확인 하려면이 함수를 호출 합니다.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>반환 값

맨 위에 표시 되는 줄의 0부터 시작 하는 인덱스입니다. 단일 줄 편집 컨트롤에 대 한 반환 값은 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [EM_GETFIRSTVISIBLELINE](/windows/desktop/Controls/em-getfirstvisibleline) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

##  <a name="gethandle"></a>  CEdit::GetHandle

여러 줄 편집 컨트롤에 대 한 현재 할당 된 메모리에 대 한 핸들을 검색 하려면이 함수를 호출 합니다.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>반환 값

편집 컨트롤의 내용을 보유 하는 버퍼를 식별 하는 로컬 메모리 핸들입니다. 단일 줄 편집 컨트롤에 메시지를 보내는 등의 오류가 발생 한 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

핸들을 로컬 메모리는 및에서 사용할 수는 **로컬** 로컬 메모리를 사용 하는 Windows 메모리 함수 매개 변수로 처리 합니다.

`GetHandle` 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.

호출 `GetHandle` DS_LOCALEDIT 스타일 플래그가 설정 된 대화 상자를 만든 경우에 대화 상자에서 여러 줄 편집 컨트롤에 대 한 합니다. DS_LOCALEDIT 스타일 설정 되어 있지 않으면 0이 아닌 반환 값을 계속 하면 있지만 반환 된 값을 사용할 수 없습니다.

> [!NOTE]
> `GetHandle` Windows 95/98 작동 하지 않습니다. 호출 하는 경우 `GetHandle` 98, Windows 95에서에서 NULL이 반환 됩니다. `GetHandle` Windows NT 버전 3.51 이상 아래 설명 된 대로 작동 합니다.

자세한 내용은 [EM_GETHANDLE](/windows/desktop/Controls/em-gethandle) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

##  <a name="gethighlight"></a>  CEdit::GetHighlight

현재 편집 컨트롤에 강조 표시 되는 텍스트 범위에서 첫 번째 및 마지막 문자의 인덱스를 가져옵니다.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pichStart*|[out] 강조 표시 되는 텍스트 범위에서 첫 번째 문자의 0부터 시작 인덱스입니다.|
|*pichEnd*|[out] 강조 표시 된 텍스트 범위의 마지막 문자의 0부터 시작 인덱스입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [EM_GETHILITE](/windows/desktop/Controls/em-gethilite) Windows SDK에 설명 된 메시지입니다. 둘 다 `SetHighlight` 고 `GetHighlight` 유니코드만 빌드에 대 한 현재 사용 하도록 설정 됩니다.

##  <a name="getlimittext"></a>  CEdit::GetLimitText

이 텍스트 제한을 가져올를이 멤버 함수 호출 `CEdit` 개체입니다.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>반환 값

현재 텍스트 크기 제한, TCHARs이 `CEdit` 개체입니다.

### <a name="remarks"></a>설명

텍스트 제한은 TCHARs 편집 컨트롤을 받아들일 수 있는 텍스트의 최대 크기입니다.

> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 [EM_GETLIMITTEXT](/windows/desktop/Controls/em-getlimittext) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

##  <a name="getline"></a>  CEdit::GetLine

편집 컨트롤에서 텍스트 줄을 검색 하려면이 함수를 호출 하 고에 배치 *lpszBuffer*합니다.

```
int GetLine(
    int nIndex,
    LPTSTR lpszBuffer) const;

int GetLine(
    int nIndex,
    LPTSTR lpszBuffer,
    int nMaxLength) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
컨트롤을 편집 하는 여러 줄에서 검색할 줄 번호를 지정 합니다. 줄 번호는 0부터 시작 합니다. 첫 번째 줄을 지정 하는 값이 0입니다. 이 매개 변수는 단일 줄 편집 컨트롤에서 무시 됩니다.

*lpszBuffer*<br/>
줄의 복사본을 수신 하는 버퍼를 가리킵니다. 버퍼의 첫 번째 단어 TCHARs 버퍼에 복사할 수 있는 최대 수를 지정 해야 합니다.

*nMaxLength*<br/>
버퍼에 복사할 수 있는 TCHAR 문자의 최대 수를 지정 합니다. `GetLine` 이 값의 첫 번째 단어에 배치 *lpszBuffer* Windows 호출 하기 전에 합니다.

### <a name="return-value"></a>반환 값

실제로 복사된 문자 수입니다. 줄 번호를 지정 하면 반환 값이 0 *nIndex* 줄 편집 컨트롤의 수보다 큽니다.

### <a name="remarks"></a>설명

복사한 행에 null 종결 문자가 없습니다.

자세한 내용은 [EM_GETLINE](/windows/desktop/Controls/em-getline) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::GetLineCount](#getlinecount)합니다.

##  <a name="getlinecount"></a>  CEdit::GetLineCount

여러 줄 편집 컨트롤의 줄 번호를 검색 하려면이 함수를 호출 합니다.

```
int GetLineCount() const;
```

### <a name="return-value"></a>반환 값

여러 줄의 줄 수가 포함 된 정수 편집 컨트롤입니다. 편집 컨트롤에 없는 텍스트를 입력 하는 경우 반환 값은 1입니다.

### <a name="remarks"></a>설명

`GetLineCount` 여러 줄 편집 컨트롤에서만 처리 됩니다.

자세한 내용은 [EM_GETLINECOUNT](/windows/desktop/Controls/em-getlinecount) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

##  <a name="getmargins"></a>  CEdit::GetMargins

편집 컨트롤의 왼쪽 및 오른쪽 여백을 검색 하려면이 멤버 함수를 호출 합니다.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>반환 값

하위 단어 및 상위 단어의 오른쪽 여백 너비 왼쪽 여백의 너비입니다.

### <a name="remarks"></a>설명

여백 (픽셀) 단위로 측정 됩니다.

> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 [EM_GETMARGINS](/windows/desktop/Controls/em-getmargins) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)합니다.

##  <a name="getmodify"></a>  CEdit::GetModify

편집 컨트롤의 내용이 수정 되었으면 여부를 결정 하는이 함수를 호출 합니다.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>반환 값

편집 컨트롤 내용이 수정 되었습니다. 0이 아닌 값 0 전문적 해당 하는 경우 변경 되지 않습니다.

### <a name="remarks"></a>설명

Windows 편집 컨트롤의 내용을 변경 되었는지 여부를 나타내는 내부 플래그를 유지 관리 합니다. 편집 컨트롤 먼저 생성 되 고 호출 하 여도 지울 수 있습니다 하는 경우이 플래그가 해제 되는 [SetModify](#setmodify) 멤버 함수입니다.

자세한 내용은 [EM_GETMODIFY](/windows/desktop/Controls/em-getmodify) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar

사용자가 텍스트를 입력 하면 편집 컨트롤에 표시 되는 암호 문자를 검색 하려면이 함수를 호출 합니다.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>반환 값

사용자가 입력 하는 문자 대신 표시할 문자를 지정 합니다. 암호 문자 아님 있으면 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

ES_PASSWORD 스타일을 사용 하 여 편집 컨트롤을 만드는 경우 컨트롤을 지 원하는 DLL의 기본 암호 문자를 결정 합니다. 매니페스트 또는 [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) 메서드 결정을 지 원하는 DLL 편집 컨트롤입니다. 기본 암호 문자는 별표 user32.dll 편집 컨트롤을 지 원하는 경우 ('* ', U + 002A). Comctl32.dll 버전 6 편집 컨트롤을 지 원하는 경우 기본 문자는 검정색 원 ('●', U + 25CF). 공용 컨트롤을 참조 하는 DLL 및 버전 지원에 대 한 자세한 [셸 및 공용 컨트롤 버전](/previous-versions/windows/desktop/legacy/bb776779\(v=vs.85\))합니다.

이 메서드는 전송 된 [EM_GETPASSWORDCHAR](/windows/desktop/Controls/em-getpasswordchar) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

##  <a name="getrect"></a>  CEdit::GetRect

편집 컨트롤의 서식 지정 영역을 가져오려면이 함수를 호출 합니다.

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 `RECT` 서식 지정 영역을 수신 하는 구조입니다.

### <a name="remarks"></a>설명

서식 지정 사각형은 편집 컨트롤 창의 크기에 관계 없이 텍스트의 사각형을 제한 합니다.

가 여러 줄 편집 컨트롤의 서식 지정 영역을 수정할 수는 [SetRect](#setrect) 하 고 [SetRectNP](#setrectnp) 멤버 함수입니다.

자세한 내용은 [EM_GETRECT](/windows/desktop/Controls/em-getrect) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::LimitText](#limittext)합니다.

##  <a name="getsel"></a>  CEdit::GetSel

시작 및 끝의 반환 값 또는 매개 변수를 사용 하 여 편집 컨트롤에서 현재 선택 (해당 되는 경우)의 문자 위치를 가져오려면이 함수를 호출 합니다.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>매개 변수

*nStartChar*<br/>
현재 선택 영역의 첫 번째 문자의 위치를 받게 됩니다 하는 정수에 대 한 참조입니다.

*nEndChar*<br/>
현재 선택 영역의 끝을 지나서 선택 되지 않은 첫 번째 문자의 위치를 수신 하는 정수에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

DWORD를 반환 하는 버전의 상위 단어 선택 항목이 종료 된 후 하위 단어의 시작 위치와 선택 되지 않은 첫 번째 문자의 위치를 포함 하는 값을 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [EM_GETSEL](/windows/desktop/Controls/em-getsel) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip

현재 편집 컨트롤과 연결 된 모든 풍선을 숨깁니다.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 함수는 [EM_HIDEBALLOONTIP](/windows/desktop/Controls/em-hideballoontip) Windows SDK에 설명 된 메시지입니다.

##  <a name="limittext"></a>  CEdit::LimitText

사용자 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 하려면이 함수를 호출 합니다.

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>매개 변수

*nChars*<br/>
(TCHARs)의 길이 입력할 수 있는 텍스트를 지정 합니다. 이 매개 변수가 0 이면 텍스트 길이가 UINT_MAX 바이트로 설정 됩니다. 이는 기본 동작입니다.

### <a name="remarks"></a>설명

텍스트도 변경 입력할 수 있는 텍스트에만 제한 합니다. 편집 컨트롤에서 이미 모든 텍스트에 영향을 주지 것도 복사 하 여 편집 컨트롤에 텍스트의 길이 영향을 하는 [SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수 `CWnd`합니다. 응용 프로그램에서 사용 하는 경우는 `SetWindowText` 함수에 대 한 호출에서 지정 된 편집 컨트롤에 더 많은 텍스트를 배치할 `LimitText`, 사용자에 편집 컨트롤 내의 텍스트를 삭제할 수 있습니다. 그러나 문자 제한 기존 텍스트 새 텍스트 바꿉니다에서 사용자를 하지 것입니다, 그리고 현재 선택 영역을 삭제 하지 않는 한 하면 텍스트 문자 제한 미만으로 떨어질입니다.

> [!NOTE]
>  Win32에서 (Windows NT 및 Windows 95/98) [SetLimitText](#setlimittext) 이 함수를 대체 합니다.

자세한 내용은 [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

##  <a name="linefromchar"></a>  CEdit::LineFromChar

지정된 된 문자 인덱스를 포함 하는 줄의 줄 번호를 검색 하려면이 함수를 호출 합니다.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
편집 컨트롤의 텍스트에 원하는 문자에 대 한 인덱스 값을 포함 하거나-1을 포함 합니다. 하는 경우 *nIndex* 은-1, 캐럿을 포함 하는 줄, 현재 줄을 지정 합니다.

### <a name="return-value"></a>반환 값

지정 되는 문자 인덱스를 포함 하는 줄의 0부터 시작 줄 번호 *nIndex*합니다. 하는 경우 *nIndex* 가-1 이면 선택의 첫 번째 문자를 포함 하는 줄 수가 반환 됩니다. 선택 영역이 없는 경우에 현재 줄 번호 반환 됩니다.

### <a name="remarks"></a>설명

문자 인덱스에는 편집 컨트롤의 시작 부분에서 문자 수입니다.

이 멤버 함수는 여러 줄 편집 컨트롤에만 사용 됩니다.

자세한 내용은 [EM_LINEFROMCHAR](/windows/desktop/Controls/em-linefromchar) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

##  <a name="lineindex"></a>  CEdit::LineIndex

여러 줄 편집 컨트롤 내에서 줄의 문자 인덱스를 검색 하려면이 함수를 호출 합니다.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>매개 변수

*nLine*<br/>
편집 컨트롤의 텍스트에서 원하는 줄의 인덱스 값을 포함 하거나-1을 포함 합니다. 하는 경우 *n 줄* 은-1, 캐럿을 포함 하는 줄, 현재 줄을 지정 합니다.

### <a name="return-value"></a>반환 값

에 지정 된 줄의 문자 인덱스 *n 줄* 또는 지정된 된 줄 번호로 편집 컨트롤의 줄 수가 보다 큰 경우-1입니다.

### <a name="remarks"></a>설명

문자 인덱스를 지정된 된 줄 편집 컨트롤의 시작 부분에서 문자입니다.

이 멤버 함수는 여러 줄 편집 컨트롤에서만 처리 됩니다.

자세한 내용은 [EM_LINEINDEX](/windows/desktop/controls/em-lineindex) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

##  <a name="linelength"></a>  CEdit::LineLength

편집 컨트롤에서 줄의 길이 검색합니다.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>매개 변수

*nLine*<br/>
줄 길이 검색할 문자의 0부터 시작 하는 인덱스입니다. 기본값은 -1입니다.

### <a name="return-value"></a>반환 값

단일 줄 편집 컨트롤에 대 한 반환 값은 편집 컨트롤의 텍스트의 길이, TCHARs 합니다.

여러 줄 편집 컨트롤에 대 한 반환 값은 지정 된 줄의 길이 TCHARs, 합니다 *n 줄* 매개 변수입니다. ANSI 텍스트 길이; 줄에서 바이트 수 유니코드 텍스트는 길이 줄의 문자 수입니다. 길이 줄의 끝에 캐리지 리턴 문자를 포함 되지 않습니다.

경우는 *n 줄* 매개 변수를 사용 하는 컨트롤의 문자 수보다 더, 반환 값은 0입니다.

경우는 *n 줄* 매개 변수가-1 이면 반환 값은 선택 된 문자가 포함 된 줄에서 선택 하지 않은 문자 수입니다. 예를 들어 다음 줄의 끝에서 8 번째 문자까지 줄의 네 번째 문자에서 선택 영역 확장 하는 경우 반환 값은 10입니다. 즉, 첫 번째 줄은 다음 7에 3 개의 문자입니다.

TCHAR 형식에 대 한 자세한 내용은 표의 TCHAR 행을 보려면 [Windows 데이터 형식](/windows/desktop/WinProg/windows-data-types)합니다.

### <a name="remarks"></a>설명

이 메서드는에서 지원 합니다 [EM_LINELENGTH](/windows/desktop/Controls/em-linelength) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::LineIndex](#lineindex)합니다.

##  <a name="linescroll"></a>  CEdit::LineScroll

여러 줄 편집 컨트롤의 텍스트를 스크롤할 수이 함수를 호출 합니다.

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>매개 변수

*nLines*<br/>
세로로 스크롤되는 줄 수를 지정 합니다.

*nChars*<br/>
가로로 스크롤합니다 문자 위치의 수를 지정 합니다. 편집 컨트롤에 ES_RIGHT 또는 ES_CENTER 스타일이 있으면이 값은 무시 됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.

편집 컨트롤에서 텍스트의 마지막 줄 다음에 편집 컨트롤 세로 방향으로 스크롤되지 않습니다. 현재는 경우 지정 된 줄 수 또한 줄 *nLines* 줄 편집 컨트롤의 총 수를 초과 하면, 편집 컨트롤의 마지막 줄 편집 컨트롤 창의 위쪽 스크롤할 수 있도록 조정 되는 값입니다.

`LineScroll` 모든 줄의 문자를 지난 문자를 가로로 스크롤할를 사용할 수 있습니다.

자세한 내용은 [EM_LINESCROLL](/windows/desktop/Controls/em-linescroll) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::GetFirstVisibleLine](#getfirstvisibleline)합니다.

##  <a name="paste"></a>  CEdit::Paste

에 클립보드에서 데이터를 삽입 하려면이 함수를 호출 합니다 `CEdit` 삽입 지점입니다.

```
void Paste();
```

### <a name="remarks"></a>설명

클립보드 CF_TEXT 형식으로 데이터를에서 포함 하는 경우에 데이터가 삽입 됩니다.

자세한 내용은 [WM_PASTE](/windows/desktop/dataxchg/wm-paste) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

##  <a name="posfromchar"></a>  CEdit::PosFromChar

이 지정 된 문자의 위치 (왼쪽 위 모서리)을 가져오려면이 함수를 호출 `CEdit` 개체입니다.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>매개 변수

*nChar*<br/>
지정 된 문자의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

지정 된 문자의 왼쪽 위 모퉁이의 좌표 *nChar*합니다.

### <a name="remarks"></a>설명

문자는 0부터 시작 인덱스 값을 제공 하 여 지정 됩니다. 하는 경우 *nChar* 이 마지막 문자의 인덱스 보다 크면 `CEdit` 개체를 반환 값이 마지막 문자 바로 다음에 오는 문자 위치의 좌표를 지정 `CEdit` 개체입니다.

> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 [EM_POSFROMCHAR](/windows/desktop/Controls/em-posfromchar) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::LineFromChar](#linefromchar)합니다.

##  <a name="replacesel"></a>  CEdit::ReplaceSel

이 함수를 지정 하는 텍스트 편집 컨트롤에서 현재 선택한 바꿉니다 호출 *lpszNewText*합니다.

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszNewText*<br/>
대체 텍스트를 포함 하는 null로 끝나는 문자열을 가리킵니다.

*bCanUndo*<br/>
이 기능을 취소할 수 있는지를 지정 하려면이 매개 변수의 값을 TRUE로 설정 합니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

편집 컨트롤에서 텍스트의 일부만 대체합니다. 모든 텍스트를 바꾸려는 경우 사용 합니다 [CWnd::SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수입니다.

현재 선택 영역이 없는 경우 대체 텍스트는 현재 커서 위치에 삽입 됩니다.

자세한 내용은 [EM_REPLACESEL](/windows/desktop/Controls/em-replacesel) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::LineIndex](#lineindex)합니다.

##  <a name="setcuebanner"></a>  CEdit::SetCueBanner

텍스트 큐로 표시 됩니다 또는 팁 편집 컨트롤이 비어를 제어 하는 텍스트를 설정 합니다.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
[in] 편집 컨트롤에 표시할 큐를 포함 하는 문자열에 대 한 포인터입니다.

*fDrawWhenFocused*<br/>
[in] FALSE 인 경우 사용자가 편집 컨트롤 클릭 하 고 컨트롤 포커스 큐 배너를 그리지 않습니다.

TRUE 인 경우 컨트롤에 포커스가 있을 때에 큐 배너를 그립니다. 큐 배너를 사용자 컨트롤에 입력 하기 시작 하면 사라집니다.

기본값은 FALSE입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [EM_SETCUEBANNER](/windows/desktop/Controls/em-setcuebanner) Windows SDK에 설명 된 메시지입니다. 자세한 내용은 참조는 [Edit_SetCueBannerTextFocused](/windows/desktop/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) 매크로입니다.

### <a name="example"></a>예제

다음 예제는 [CEdit::SetCueBanner](#setcuebanner) 메서드.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

##  <a name="sethandle"></a>  CEdit::SetHandle

여러 줄 편집 컨트롤에서 사용 될 로컬 메모리에 핸들을 설정 하려면이 함수를 호출 합니다.

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>매개 변수

*hBuffer*<br/>
로컬 메모리에 대 한 핸들을 포함합니다. 이 핸들에 대 한 이전 호출에서 만든 것 이어야 합니다 [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) LMEM_MOVEABLE 플래그를 사용 하 여 Windows 함수입니다. 메모리는 null로 끝나는 문자열을 포함 하도록 간주 됩니다. 없는 경우 할당된 된 메모리의 첫 번째 바이트는 0으로 설정 되어야 합니다.

### <a name="remarks"></a>설명

편집 컨트롤 자체 버퍼를 할당 하는 대신 현재 표시 된 텍스트를 저장 하려면이 버퍼를 사용 합니다.

이 멤버 함수는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.

새 메모리 핸들을 설정 하는 응용 프로그램을 먼저 사용 해야 합니다 [GetHandle](#gethandle) 멤버 함수를 현재 메모리 버퍼에 핸들을 가져오고 사용 하 여 해당 메모리를 해제 합니다 `LocalFree` Windows 함수입니다.

`SetHandle` 실행 취소 버퍼를 지웁니다 (합니다 [CanUndo](#canundo) 멤버 함수는 0을 반환 합니다) 및 내부 수정 플래그 (합니다 [GetModify](#getmodify) 멤버 함수는 0을 반환 합니다). 편집 컨트롤 창의 다시 그려집니다.

DS_LOCALEDIT 스타일 플래그가 설정 된 대화 상자를 만든 경우에 대화 상자에서 여러 줄 편집 컨트롤에서이 멤버 함수를 사용할 수 있습니다.

> [!NOTE]
> `GetHandle` Windows 95/98 작동 하지 않습니다. 호출 하는 경우 `GetHandle` 98, Windows 95에서에서 NULL이 반환 됩니다. `GetHandle` Windows NT 버전 3.51 이상 아래 설명 된 대로 작동 합니다.

자세한 내용은 [EM_SETHANDLE](/windows/desktop/Controls/em-sethandle)를 [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc), 및 [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree) Windows SDK의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

##  <a name="sethighlight"></a>  CEdit::SetHighlight

현재에서 표시 되는 텍스트 범위를 강조 표시 컨트롤을 편집 합니다.

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*ichStart*|[in] 강조 표시 하는 텍스트 범위에서 첫 번째 문자의 0부터 시작 인덱스입니다.|
|*ichEnd*|[in] 강조 표시 하는 텍스트 범위에서 마지막 문자의 0부터 시작 인덱스입니다.|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) Windows SDK에 설명 된 메시지입니다.  이 메서드는 전송 된 [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) Windows SDK에 설명 된 메시지입니다. 둘 다 `SetHighlight` 및 `GetHighlight` 유니코드만 빌드에 대 한 활성화 됩니다.

##  <a name="setlimittext"></a>  CEdit::SetLimitText

이 텍스트 제한을 설정 하려면이 멤버 함수 호출 `CEdit` 개체입니다.

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
새 텍스트 제한, 문자입니다.

### <a name="remarks"></a>설명

텍스트 제한은 최대 텍스트 편집 컨트롤을 받아들일 수 있는 문자입니다.

텍스트도 변경 입력할 수 있는 텍스트에만 제한 합니다. 편집 컨트롤에서 이미 모든 텍스트에 영향을 주지 것도 복사 하 여 편집 컨트롤에 텍스트의 길이 영향을 하는 [SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수 `CWnd`합니다. 응용 프로그램에서 사용 하는 경우는 `SetWindowText` 함수에 대 한 호출에서 지정 된 편집 컨트롤에 더 많은 텍스트를 배치할 `LimitText`, 사용자에 편집 컨트롤 내의 텍스트를 삭제할 수 있습니다. 그러나 문자 제한 기존 텍스트 새 텍스트 바꿉니다에서 사용자를 하지 것입니다, 그리고 현재 선택 영역을 삭제 하지 않는 한 하면 텍스트 문자 제한 미만으로 떨어질입니다.

이 함수 대체 [LimitText](#limittext) Win32에서.

자세한 내용은 [EM_SETLIMITTEXT](/windows/desktop/Controls/em-setlimittext) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)합니다.

##  <a name="setmargins"></a>  CEdit::SetMargins

편집 컨트롤의 왼쪽 및 오른쪽 여백을 설정 하려면이 메서드를 호출 합니다.

```
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>매개 변수

*nLeft*<br/>
너비 (픽셀)에서 새 왼쪽된 여백입니다.

*nRight*<br/>
너비 (픽셀)에서 새 오른쪽 여백입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 [EM_SETMARGINS](/windows/desktop/Controls/em-setmargins) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)합니다.

##  <a name="setmodify"></a>  CEdit::SetModify

설정 하거나 편집 컨트롤에 대 한 수정 된 플래그를 해제 하려면이 함수를 호출 합니다.

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>매개 변수

*bModified*<br/>
값이 true 이면 텍스트를 수정 하 고 FALSE 값은 수정 된 의미를 나타냅니다. 기본적으로 수정 된 플래그를 설정 됩니다.

### <a name="remarks"></a>설명

수정 된 플래그를 텍스트 편집 컨트롤에 수정 되었는지 여부를 나타냅니다. 사용자가 텍스트를 변경할 때마다 자동으로 설정 됩니다. 해당 값으로 검색할 수 있습니다 합니다 [GetModify](#getmodify) 멤버 함수입니다.

자세한 내용은 [EM_SETMODIFY](/windows/desktop/Controls/em-setmodify) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::GetModify](#getmodify)합니다.

##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar

설정 또는 사용자가 텍스트를 입력할 때 편집 컨트롤에 표시 되는 암호 문자를 제거 하려면이 함수를 호출 합니다.

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>매개 변수

*ch*<br/>
사용자가 입력 문자 대신 표시할 문자를 지정 합니다. 하는 경우 *ch* 가 0 이면 사용자가 입력 하는 실제 문자는 표시 됩니다.

### <a name="remarks"></a>설명

암호 문자를 설정 하면 사용자가 각 문자에 대 한 문자가 표시 됩니다.

이 멤버 함수에 영향을 주지는 여러 줄 편집 컨트롤에 있습니다.

경우는 `SetPasswordChar` 멤버 함수가 호출 될 `CEdit` 하 여 지정 된 문자를 사용 하 여 모든 표시 문자를 다시 그릴 *ch*합니다.

편집 컨트롤을 사용 하 여 만들어지는 경우 합니다 [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) 스타일이, 기본 암호 문자는 별표로 설정 됩니다 ( <strong>\*</strong>). 이 스타일이 제거 됩니다 `SetPasswordChar` 사용 하 여 이라고 *ch* 0으로 설정 합니다.

자세한 내용은 [EM_SETPASSWORDCHAR](/windows/desktop/Controls/em-setpasswordchar) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

##  <a name="setreadonly"></a>  CEdit::SetReadOnly

편집 컨트롤의 읽기 전용 상태를 설정 하려면이 함수를 호출 합니다.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>매개 변수

*bReadOnly*<br/>
설정 하거나 편집 컨트롤의 읽기 전용 상태를 제거할 것인지 지정 합니다. 읽기 전용 상태를 설정 하는 TRUE 값 FALSE 값 읽기/쓰기 상태를 설정 합니다.

### <a name="return-value"></a>반환 값

작업이 성공 하면 0 오류가 발생할 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

현재 설정을 테스트 하 여 찾을 수 있습니다 합니다 [ES_READONLY](styles-used-by-mfc.md#edit-styles) 반환 값에 플래그 [CWnd::GetStyle](cwnd-class.md#getstyle)합니다.

자세한 내용은 [EM_SETREADONLY](/windows/desktop/Controls/em-setreadonly) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

##  <a name="setrect"></a>  CEdit::SetRect

지정된 된 좌표를 사용 하 여 사각형의 크기를 설정 하려면이 함수를 호출 합니다.

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 합니다 `RECT` 구조 또는 `CRect` 서식 지정 사각형의 새 크기를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.

사용 하 여 `SetRect` 서식을 지정 하는 여러 줄의 사각형 컨트롤을 편집 합니다. 서식 지정 사각형은 편집 컨트롤 창의 크기에 관계 없이 텍스트의 사각형을 제한 합니다. 편집 컨트롤 처음 만들어질 때 서식 지정 영역이 같습니다 편집 컨트롤 창의 클라이언트 영역입니다. 사용 하 여는 `SetRect` 멤버 함수를 편집 컨트롤 창의 보다 크거나 작은 응용 프로그램 서식 지정 영역 확인 수 있습니다.

편집 컨트롤에 스크롤 막대가 없는 경우 텍스트는 잘린 상태로 인쇄 됩니다 래핑되지 않으면, 서식 지정 영역 창 보다 큰 경우. 편집 컨트롤에 테두리를 포함 하는 경우 서식 지정 영역 테두리의 크기에 따라 줄어듭니다. 반환 된 사각형을 조정 하는 경우는 `GetRect` 멤버 함수에 사각형을 전달 하기 전에 테두리의 크기를 제거 해야 `SetRect`합니다.

때 `SetRect` 호출 되는 편집 컨트롤의 텍스트는 또한 다시 포맷 하 고 다시 표시 됩니다.

자세한 내용은 [EM_SETRECT](/windows/desktop/Controls/em-setrect) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

##  <a name="setrectnp"></a>  CEdit::SetRectNP

여러 줄 편집 컨트롤의 서식 지정 영역을 설정 하려면이 함수를 호출 합니다.

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 `RECT` 구조 또는 `CRect` 사각형의 새 크기를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

서식 지정 사각형은 편집 컨트롤 창의 크기에 관계 없이 텍스트의 사각형을 제한 합니다.

`SetRectNP` 동일 합니다 `SetRect` 멤버 함수 제외 하 고 편집 컨트롤 창의 다시 그려지지 않습니다.

편집 컨트롤 처음 만들어질 때 서식 지정 영역이 같습니다 편집 컨트롤 창의 클라이언트 영역입니다. 호출 하 여는 `SetRectNP` 멤버 함수를 편집 컨트롤 창의 보다 크거나 작은 응용 프로그램 서식 지정 영역 확인 수 있습니다.

편집 컨트롤에 스크롤 막대가 없는 경우 텍스트는 잘린 상태로 인쇄 됩니다 래핑되지 않으면, 서식 지정 영역 창 보다 큰 경우.

이 멤버는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.

자세한 내용은 [EM_SETRECTNP](/windows/desktop/Controls/em-setrectnp) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::SetRect](#setrect)합니다.

##  <a name="setsel"></a>  CEdit::SetSel

편집 컨트롤에서 문자 범위를 선택 하려면이 함수를 호출 합니다.

```
void SetSel(
    DWORD dwSelection,
    BOOL bNoScroll = FALSE);

void SetSel(
    int nStartChar,
    int nEndChar,
    BOOL bNoScroll = FALSE);
```

### <a name="parameters"></a>매개 변수

*dwSelection*<br/>
하위 단어의 시작 위치 및 상위 단어의 끝 위치를 지정합니다. 하위 워드 0이 고 상위 word가-1의 모든 텍스트 편집 컨트롤에 선택 됩니다. 하위 워드-1 인 경우 모든 현재 선택 영역 제거 됩니다.

*bNoScroll*<br/>
캐럿은 뷰로 스크롤할 수 있는지 여부를 나타냅니다. False 인 경우, 캐럿 뷰로 스크롤됩니다. True 인 경우, 캐럿 하지 뷰로 스크롤됩니다.

*nStartChar*<br/>
시작 위치를 지정합니다. 하는 경우 *nStartChar* 은 0 및 *nEndChar* 가-1 이면 모든 편집 컨트롤의 텍스트를 선택 합니다. 하는 경우 *nStartChar* 가-1 이면 현재 선택에서 제거 됩니다.

*nEndChar*<br/>
끝 위치를 지정합니다.

### <a name="remarks"></a>설명

자세한 내용은 [EM_SETSEL](/windows/desktop/Controls/em-setsel) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEdit::GetSel](#getsel)합니다.

##  <a name="settabstops"></a>  CEdit::SetTabStops

여러 줄 편집 컨트롤의 탭 정지를 설정 하려면이 함수를 호출 합니다.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>매개 변수

*cxEachStop*<br/>
탭 정지에 설정할 지정 마다 *cxEachStop* 대화 상자 단위입니다.

*nTabStops*<br/>
에 포함 된 탭 정지의 수를 지정 *rgTabStops*합니다. 이 번호는 1 보다 커야 합니다.

*rgTabStops*<br/>
탭을 지정 하는 부호 없는 정수의 배열 가리킵니다 대화 상자 단위에서를 중지 합니다. 대화 상자 단위는 가로 또는 세로 거리입니다. 하나의 가로 대화 상자 단위는 1-4 현재 대화 기본 너비 단위 같음 및 1 세로 대화 단위 현재 대화 기본 높이 단위의 1 / 8와 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 너비와 높이에 따라 계산 됩니다. `GetDialogBaseUnits` Windows 함수 현재 대화 상자 기본 단위를 픽셀 단위로 반환 합니다.

### <a name="return-value"></a>반환 값

탭 설정 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

여러 줄 편집 컨트롤에 텍스트를 복사 하면 텍스트에 탭 문자와 다음 탭 정지까지 생성 되는 공간을 발생 합니다.

탭 정지 32 대화 상자 단위는 기본 크기를 설정 하려면이 멤버 함수는 매개 변수가 없는 버전을 호출 합니다. 탭 정지 32 이외의 크기를 설정 하려면 사용 하 여 버전을 호출 합니다 *cxEachStop* 매개 변수입니다. 탭 정지 배열의 크기를 설정 하려면 두 개의 매개 변수를 사용 하 여 버전을 사용 합니다.

이 멤버 함수는 여러 줄 편집 컨트롤에서만 처리 됩니다.

`SetTabStops` 편집 창이 자동으로 그려지지 않습니다. 텍스트 편집 컨트롤에 이미 있는 탭 정지를 변경 하면 호출 [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) 에 편집 창을 다시 그리도록 합니다.

자세한 내용은 [EM_SETTABSTOPS](/windows/desktop/Controls/em-settabstops) 하 고 [GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows SDK의 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CEditView::SetTabStops](ceditview-class.md#settabstops)합니다.

##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip

현재 편집 컨트롤과 연결 된 풍선 설명을 표시 합니다.

```
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,
    LPCWSTR lpszText,
    INT ttiIcon = TTI_NONE);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pEditBalloonTip*|[in] 에 대 한 포인터를 [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) 풍선 설명 하는 구조입니다.|
|*lpszTitle*|[in] 풍선 설명의 제목을 포함 하는 유니코드 문자열에 대 한 포인터입니다.|
|*lpszText*|[in] 풍선 도구 설명 텍스트를 포함 하는 유니코드 문자열에 대 한 포인터입니다.|
|*ttiIcon*|[in] **INT** 풍선 연결할 아이콘의 형식을 지정 하는 합니다. 기본값은 TTI_NONE 합니다. 자세한 내용은 참조 하세요. 합니다 `ttiIcon` 의 멤버는 [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) 구조입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 함수는 [EM_SHOWBALLOONTIP](/windows/desktop/Controls/em-showballoontip) Windows SDK에 설명 된 메시지입니다. 자세한 내용은 참조는 [Edit_ShowBalloonTip](/windows/desktop/api/commctrl/nf-commctrl-edit_showballoontip) 매크로입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_cedit`, 즉 현재 편집 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 편집 컨트롤의 풍선 설명을 표시 합니다. 합니다 [CEdit::ShowBalloonTip](#showballoontip) 메서드 제목 및 풍선 팁 텍스트를 지정 합니다.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

##  <a name="undo"></a>  CEdit::Undo

마지막 편집 컨트롤 작업을 취소 하려면이 함수를 호출 합니다.

```
BOOL Undo();
```

### <a name="return-value"></a>반환 값

단일 줄 편집 컨트롤을 반환 값은 항상 0이 아닌 값입니다. 여러 줄 편집 컨트롤에 대 한 반환 값은 실행 취소 작업에 성공 하면 0이 아닌 값 또는 실행 취소 작업이 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

실행 취소 작업 또한 취소할 수 없습니다. 예를 들어, 첫 번째 호출을 사용 하 여 삭제 된 텍스트를 복원할 수 있습니다 `Undo`합니다. 중간 편집 작업이 없습니다으로 다시에 대 한 두 번째 호출을 사용 하 여 텍스트를 제거할 수 있습니다 `Undo`합니다.

자세한 내용은 [EM_UNDO](/windows/desktop/Controls/em-undo) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>참고자료

[CALCDRIV MFC 샘플](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](cwnd-class.md)<br/>
[CButton 클래스](cbutton-class.md)<br/>
[CComboBox 클래스](ccombobox-class.md)<br/>
[CListBox 클래스](clistbox-class.md)<br/>
[CScrollBar 클래스](cscrollbar-class.md)<br/>
[CStatic 클래스](cstatic-class.md)<br/>
[CDialog 클래스](cdialog-class.md)

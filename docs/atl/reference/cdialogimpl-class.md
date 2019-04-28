---
title: CDialogImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: 1124630d8ee15dd284893516bef8057f852b4632
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245757"
---
# <a name="cdialogimpl-class"></a>CDialogImpl 클래스

이 클래스는 모달 또는 모덜리스 대화 상자 만들기에 대 한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CDialogImpl`합니다.

*TBase*<br/>
새 클래스의 기본 클래스입니다. 기본 클래스는 [CWindow](../../atl/reference/cwindow-class.md)합니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[만들기](#create)|모덜리스 대화 상자를 만듭니다.|
|[DestroyWindow](#destroywindow)|모덜리스 대화 상자를 제거합니다.|
|[DoModal](#domodal)|모달 대화 상자를 만듭니다.|
|[EndDialog](#enddialog)|모달 대화 상자를 제거합니다.|

### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT 메서드

|||
|-|-|
|[GetDialogProc](#getdialogproc)|현재 대화 상자 프로시저를 반환합니다.|
|[MapDialogRect](#mapdialogrect)|지정된 된 사각형의 대화 상자 단위 화면 단위 (픽셀)에 매핑됩니다.|
|[OnFinalMessage](#onfinalmessage)|일반적으로 WM_NCDESTROY 마지막 메시지를 받은 후 호출 됩니다.|

### <a name="static-functions"></a>정적 함수

|||
|-|-|
|[DialogProc](#dialogproc)|대화 상자에 전송 된 메시지를 처리 합니다.|
|[StartDialogProc](#startdialogproc)|대화 상자에 전송 된 메시지를 처리 하는 데 첫 번째 메시지를 받을 때 호출 됩니다.|

## <a name="remarks"></a>설명

사용 하 여 `CDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CDialogImpl` 기본 메시지 맵을 사용해 메시지를 해당 처리기를 직접을 대화 상자 프로시저를 제공 합니다.

기본 클래스 소멸자 `~CWindowImplRoot` 창 개체를 소멸 하기 전에 제거 되 고 있는지 확인 합니다.

`CDialogImpl` 파생 `CDialogImplBaseT`에서 파생 됩니다는 `CWindowImplRoot`합니다.

> [!NOTE]
>  클래스를 정의 해야 합니다는 `IDD` 대화 상자 템플릿 리소스 ID를 지정 하는 멤버 예를 들어, ATL 프로젝트 마법사는 자동으로 클래스에 다음 줄을 추가합니다.

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

여기서 `MyDlg` 은 **약식 이름** 마법사의 입력 **이름** 페이지.

|추가 정보|참조|
|--------------------------------|---------|
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|
|ATL 대화 상자를 사용 하 여|[ATL 창 클래스](../../atl/atl-window-classes.md)|
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|
|대화 상자|[대화 상자](/windows/desktop/dlgbox/dialog-boxes) 및 Windows SDK의 후속 항목|

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="create"></a>  CDialogImpl::Create

모덜리스 대화 상자를 만듭니다.

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
[in] 소유자 창에 대 한 핸들입니다.

**RECT &** *rect* [in] [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조 대화 상자의 크기와 위치를 지정 합니다.

*dwInitParam*<br/>
[in] 대화 상자에 전달할 값을 지정 합니다 *lParam* WM_INITDIALOG 메시지의 매개 변수입니다.

### <a name="return-value"></a>반환 값

새로 만든된 대화 상자에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 대화 상자에 자동으로 연결 되는 `CDialogImpl` 개체입니다. 모달 대화 상자를 만들려면 호출 [DoModal](#domodal)합니다. 위의 두 번째 재정의 사용 됩니다 [CComControl](../../atl/reference/ccomcontrol-class.md)합니다.

##  <a name="destroywindow"></a>  CDialogImpl::DestroyWindow

모덜리스 대화 상자를 제거합니다.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>반환 값

TRUE 이면 대화 상자를 성공적으로 제거 되었습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

TRUE를 반환 하는 경우 대화 상자를 성공적으로 제거 되었습니다. 그렇지 않으면 FALSE입니다.

##  <a name="dialogproc"></a>  CDialogImpl::DialogProc

이 정적 함수는 대화 상자 프로시저를 구현합니다.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 대화 상자에 대 한 핸들입니다.

*uMsg*<br/>
[in] 대화 상자에 전송 된 메시지입니다.

*wParam*<br/>
[in] 추가 메시지 관련 정보입니다.

*lParam*<br/>
[in] 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 메시지를 처리 합니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`DialogProc` 기본 메시지 맵을 사용 하 여 메시지를 해당 처리기로 직접.

재정의할 수 있습니다 `DialogProc` 메시지를 처리 하기 위한 다른 메커니즘을 제공 합니다.

##  <a name="domodal"></a>  CDialogImpl::DoModal

모달 대화 상자를 만듭니다.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
[in] 소유자 창에 대 한 핸들입니다. 기본값은의 반환 값을 [GetActiveWindow](/windows/desktop/api/winuser/nf-winuser-getactivewindow) Win32 함수입니다.

*dwInitParam*<br/>
[in] 대화 상자에 전달할 값을 지정 합니다 *lParam* WM_INITDIALOG 메시지의 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 값을 *nRetCode* 호출에서 지정 된 매개 변수 [EndDialog](#enddialog)합니다. 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

이 대화 상자에 자동으로 연결 되는 `CDialogImpl` 개체입니다.

모덜리스 대화 상자를 만들려면 호출 [만들기](#create)합니다.

##  <a name="enddialog"></a>  CDialogImpl::EndDialog

모달 대화 상자를 제거합니다.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>매개 변수

*nRetCode*<br/>
[in] 값을 반환할 [CDialogImpl::DoModal](#domodal)합니다.

### <a name="return-value"></a>반환 값

대화 상자가 소멸 될; 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`EndDialog` 대화 상자 프로시저를 통해 호출 해야 합니다. Windows의 값을 사용 하 여 대화 상자 제거 후 *nRetCode* 반환 값으로 `DoModal`, 대화 상자를 생성 하는 합니다.

> [!NOTE]
>  호출 하지 마십시오 `EndDialog` 모덜리스 대화 상자를 삭제 하려면. 호출 [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) 대신 합니다.

##  <a name="getdialogproc"></a>  CDialogImpl::GetDialogProc

반환 `DialogProc`, 현재 대화 상자 프로시저입니다.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>반환 값

현재 대화 상자 프로시저입니다.

### <a name="remarks"></a>설명

사용자의 대화 상자 프로시저로 바꾸도록이 메서드를 재정의 합니다.

##  <a name="mapdialogrect"></a>  CDialogImpl::MapDialogRect

(Maps) 대화 상자 단위 화면에 지정된 된 사각형의 단위 (픽셀)를 변환합니다.

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 `CRect` 개체 또는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 업데이트 영역을 둘러싸는 업데이트의 클라이언트 좌표를 수신 하는 것입니다.

### <a name="return-value"></a>반환 값

업데이트 성공 하면 0이 아닌 값 업데이트가 실패 하는 경우 0입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

### <a name="remarks"></a>설명

함수는 지정 된 좌표를 대체 `RECT` 구조 대화 상자를 만들거나 대화 상자 내에서 컨트롤을 배치 하는 데 사용할 수 있는 변환 된 좌표를 사용 하 여 구조체입니다.

##  <a name="onfinalmessage"></a>  CDialogImpl::OnFinalMessage

마지막 메시지를 받은 후에 호출 됩니다 (일반적으로 `WM_NCDESTROY`).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 소멸 될 창의 핸들입니다.

### <a name="remarks"></a>설명

창 소멸 시 개체를 자동으로 삭제 하려는 경우를 호출할 수 있음을 유의 **; 삭제** 여기 있습니다.

##  <a name="startdialogproc"></a>  CDialogImpl::StartDialogProc

대화 상자에 전송 된 메시지를 처리 하는 데 첫 번째 메시지가 수신 되 면 한 번만 호출 됩니다.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 대화 상자에 대 한 핸들입니다.

*uMsg*<br/>
[in] 대화 상자에 전송 된 메시지입니다.

*wParam*<br/>
[in] 추가 메시지 관련 정보입니다.

*lParam*<br/>
[in] 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>반환 값

창 프로시저입니다.

### <a name="remarks"></a>설명

초기 호출 후 `StartDialogProc`, `DialogProc` 대화 프로시저 및 호출 추가로 이동으로 설정 됩니다.

## <a name="see-also"></a>참고자료

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

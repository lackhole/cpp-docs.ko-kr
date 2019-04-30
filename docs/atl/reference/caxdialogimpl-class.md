---
title: CAxDialogImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: d6f08553a9eff421923ef348caee2022849674ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259965"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl 클래스

이 클래스는 대화 상자 (모달 또는 모덜리스) 호스트 하는 ActiveX 컨트롤을 구현합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CAxDialogImpl`합니다.

*TBase*<br/>
에 대 한 기본 창 클래스 `CDialogImplBaseT`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Advise 하거나 unadvise 개체의 싱크 이벤트 맵의 모든 항목에이 메서드를 호출 합니다.|
|[CAxDialogImpl::Create](#create)|모덜리스 대화 상자를 만들려면이 메서드를 호출 합니다.|
|[CAxDialogImpl::DestroyWindow](#destroywindow)|모덜리스 대화 상자를 삭제 하려면이 메서드를 호출 합니다.|
|[CAxDialogImpl::DoModal](#domodal)|모달 대화 상자를 만들려면이 메서드를 호출 합니다.|
|[CAxDialogImpl::EndDialog](#enddialog)|모달 대화 상자를 삭제 하려면이 메서드를 호출 합니다.|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|에 대 한 포인터를 가져오려면이 메서드를 호출 하 여 `DialogProc` 콜백 함수입니다.|
|[CAxDialogImpl::GetIDD](#getidd)|대화 상자 템플릿 리소스 ID를 가져오려면이 메서드를 호출 합니다.|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|이 대화 상자는 메시지는 보내집니다 여부를 확인 하려면이 메서드를 호출 하 고이 경우 메시지를 처리 합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAxDialogImpl::m_bModal](#m_bmodal)|디버그에만 존재 하는 변수 빌드되고 경우 대화 상자의 모달을 true로 설정 됩니다.|

## <a name="remarks"></a>설명

`CAxDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CAxDialogImpl` 기본 메시지 맵을 사용해 메시지를 해당 처리기를 직접을 대화 상자 프로시저를 제공 합니다.

`CAxDialogImpl` 파생 `CDialogImplBaseT`에에서 파생 됩니다 *TBase* (기본적으로 `CWindow`) 및 `CMessageMap`합니다.

클래스는 대화 상자 템플릿 리소스 ID를 지정 하는 IDD 멤버를 정의 해야 합니다. 예를 들어, 사용 하 여 ATL 대화 상자 개체를 추가 합니다 **클래스 추가** 대화 상자 클래스에 다음 줄을 자동으로 추가 합니다.

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

여기서 `MyDialog` 은 **약식 이름** ATL 대화 상자 마법사에 입력 합니다.

참조 [대화 상자 구현](../../atl/implementing-a-dialog-box.md) 자세한 내용은 합니다.

모달 대화 상자에서 ActiveX 컨트롤을 사용 하 여 만든 note `CAxDialogImpl` 액셀러레이터 키를 지원 하지 것입니다. 사용 하 여 만든 대화 상자에서 액셀러레이터 키를 지원 하도록 `CAxDialogImpl`모덜리스 대화 상자를 만들고, 고유한 메시지 루프를 사용 하 여 [CAxDialogImpl::IsDialogMessage](#isdialogmessage) 처리를 큐에서 메시지를 받은 후를 액셀러레이터 키입니다.

에 대 한 자세한 `CAxDialogImpl`를 참조 하세요 [ATL 컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="advisesinkmap"></a>  CAxDialogImpl::AdviseSinkMap

Advise 하거나 unadvise 개체의 싱크 이벤트 맵의 모든 항목에이 메서드를 호출 합니다.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>매개 변수

*bAdvise*<br/>
알림을 받을 수 있습니다; 싱크 항목이 모든 경우 true로 설정 모든 경우에 false 싱크 항목이를 권장 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="create"></a>  CAxDialogImpl::Create

모덜리스 대화 상자를 만들려면이 메서드를 호출 합니다.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
[in] 소유자 창에 대 한 핸들입니다.

*dwInitParam*<br/>
[in] 대화 상자에 전달할 값을 지정 합니다 *lParam* WM_INITDIALOG 메시지의 매개 변수입니다.

*RECT&*<br/>
이 매개 변수는 사용되지 않습니다. 이 매개 변수는에 의해 전달 된 `CComControl`합니다.

### <a name="return-value"></a>반환 값

새로 만든된 대화 상자에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 대화 상자에 자동으로 연결 되는 `CAxDialogImpl` 개체입니다. 모달 대화 상자를 만들려면 호출 [DoModal](#domodal)합니다.

두 번째 재정의 대화 상자를 사용 하 여 사용할 수 있도록 하기 위해서만 제공 됩니다 [CComControl](../../atl/reference/ccomcontrol-class.md)합니다.

##  <a name="destroywindow"></a>  CAxDialogImpl::DestroyWindow

모덜리스 대화 상자를 삭제 하려면이 메서드를 호출 합니다.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>반환 값

창이 소멸 성공적으로 되; 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

호출 하지 마십시오 `DestroyWindow` 을 모달 대화 상자를 삭제 합니다. 호출 [EndDialog](#enddialog) 대신 합니다.

##  <a name="domodal"></a>  CAxDialogImpl::DoModal

모달 대화 상자를 만들려면이 메서드를 호출 합니다.

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

성공 하면 값을 *nRetCode* 호출에서 지정 된 매개 변수 [EndDialog](#enddialog)고, 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

이 대화 상자에 자동으로 연결 되는 `CAxDialogImpl` 개체입니다.

모덜리스 대화 상자를 만들려면 호출 [만들기](#create)합니다.

##  <a name="enddialog"></a>  CAxDialogImpl::EndDialog

모달 대화 상자를 삭제 하려면이 메서드를 호출 합니다.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>매개 변수

*nRetCode*<br/>
[in] 값을 반환할 [DoModal](#domodal)합니다.

### <a name="return-value"></a>반환 값

대화 상자가 소멸 될; 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`EndDialog` 대화 상자 프로시저를 통해 호출 해야 합니다. Windows의 값을 사용 하 여 대화 상자 제거 후 *nRetCode* 반환 값으로 `DoModal`, 대화 상자를 생성 하는 합니다.

> [!NOTE]
>  호출 하지 마십시오 `EndDialog` 모덜리스 대화 상자를 삭제 하려면. 호출 [DestroyWindow](#destroywindow) 대신 합니다.

##  <a name="getdialogproc"></a>  CAxDialogImpl::GetDialogProc

에 대 한 포인터를 가져오려면이 메서드를 호출 하 여 `DialogProc` 콜백 함수입니다.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 `DialogProc` 콜백 함수입니다.

### <a name="remarks"></a>설명

`DialogProc` 함수는 응용 프로그램에서 정의 된 콜백 함수입니다.

##  <a name="getidd"></a>  CAxDialogImpl::GetIDD

대화 상자 템플릿 리소스 ID를 가져옵니다.이 메서드를 호출 합니다.

```
int GetIDD();
```

### <a name="return-value"></a>반환 값

대화 상자 템플릿 리소스 ID를 반환합니다.

##  <a name="isdialogmessage"></a>  CAxDialogImpl::IsDialogMessage

이 대화 상자는 메시지는 보내집니다 여부를 확인 하려면이 메서드를 호출 하 고이 경우 메시지를 처리 합니다.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
에 대 한 포인터를 [MSG](/windows/desktop/api/winuser/ns-winuser-msg) 검사할 메시지를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

메시지 되었으면이 고, FALSE 처리 그렇지 않은 경우 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 메시지 루프 내에서 호출 됩니다.

##  <a name="m_bmodal"></a>  CAxDialogImpl::m_bModal

디버그에만 존재 하는 변수 빌드되고 경우 대화 상자의 모달을 true로 설정 됩니다.

```
bool m_bModal;
```

## <a name="see-also"></a>참고자료

[CDialogImpl 클래스](../../atl/reference/cdialogimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

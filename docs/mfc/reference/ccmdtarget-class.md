---
title: CCmdTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 9314717fab53b1a89b87d657ec617a4c6bd45b8b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776195"
---
# <a name="ccmdtarget-class"></a>CCmdTarget 클래스

Microsoft Foundation Class 라이브러리 메시지 맵 아키텍처에 대 한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CCmdTarget : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|`CCmdTarget` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|모래 시계 커서도 커서를 표시합니다.|
|[CCmdTarget::DoOleVerb](#dooleverb)|OLE 동사를 수행 하 여 지정 된 동작이 발생 합니다.|
|[CCmdTarget::EnableAutomation](#enableautomation)|에 대 한 OLE 자동화를 `CCmdTarget` 개체입니다.|
|[CCmdTarget::EnableConnections](#enableconnections)|연결 지점을 통해 이벤트 발생을 수 있습니다.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|개체의 형식 라이브러리를 사용 하도록 설정 합니다.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|이전 커서를 반환 합니다.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|개체의 OLE 동사를 열거합니다.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|에 대 한 포인터를 반환 합니다 `CCmdTarget` 연관 된 개체는 `IDispatch` 포인터입니다.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|기본 디스패치 인터페이스 ID를 가져옵니다.|
|[CCmdTarget::GetIDispatch](#getidispatch)|에 대 한 포인터를 반환 합니다 `IDispatch` 연관 된 개체는 `CCmdTarget` 개체입니다.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|개체를 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.|
|[CCmdTarget::GetTypeLib](#gettypelib)|형식 라이브러리에 대 한 포인터를 가져옵니다.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|형식 라이브러리 캐시를 가져옵니다.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|자동화 메서드 호출을 사용 하도록 설정 합니다.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|반환 하는 경우 자동화 함수를 0이 아닌 값을 반환 해야 합니다.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|라우팅하고 명령 메시지를 디스패치합니다.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|마지막 OLE 참조가 해제 된 후 정리 합니다.|
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|모래 시계 커서를 복원합니다.|

## <a name="remarks"></a>설명

메시지 맵을 처리 쓸 멤버 함수에 명령 또는 메시지를 라우팅합니다. (명령 메뉴 항목, 명령 단추 또는 액셀러레이터 키에서 메시지입니다.)

키 프레임 워크 클래스에서 파생 된 `CCmdTarget` 포함 [CView](../../mfc/reference/cview-class.md)를 [CWinApp](../../mfc/reference/cwinapp-class.md)를 [CDocument](../../mfc/reference/cdocument-class.md)를 [CWnd](../../mfc/reference/cwnd-class.md), 및 [ CFrameWnd](../../mfc/reference/cframewnd-class.md)합니다. 메시지를 처리 하는 새 클래스를 호스팅하려는 경우 다음 중 하나에서 클래스를 파생 `CCmdTarget`-클래스를 파생 합니다. 클래스를 파생 거의 `CCmdTarget` 직접.

명령 대상에 대 한 개요와 `OnCmdMsg` 참조 라우팅 [명령 대상](../../mfc/command-targets.md), [명령 라우팅](../../mfc/command-routing.md), 및 [메시지 매핑](../../mfc/mapping-messages.md)합니다.

`CCmdTarget` 모래 시계 커서의 표시를 처리 하는 멤버 함수를 포함 합니다. 명령을 실행 하는 눈에 띄는 시간 간격을 원하는 경우에 모래 시계 커서를 표시 합니다.

디스패치 맵, 메시지 맵 비슷합니다, OLE 자동화를 노출 하는 데 사용 됩니다 `IDispatch` 기능입니다. 이 인터페이스를 노출 시 킴으로써 다른 응용 프로그램 (예: Visual Basic) 응용 프로그램에 호출할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor

명령을 실행 하는 눈에 띄는 시간 간격을 원하는 경우 모래시계로 커서를 표시 하려면이 함수를 호출 합니다.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>설명

사용 중인 경우와 같이 사용자를 표시 하려면이 함수를 호출 하는 프레임 워크는 `CDocument` 개체 로드 하거나 파일로 저장 하는 자체입니다.

사항의 `BeginWaitCursor` 항상 적용 됩니다 단일 메시지 처리기 외부에서 다른 작업으로 같은 `OnSetCursor` 처리, 커서 변경 될 수 있습니다.

호출 `EndWaitCursor` 이전 커서를 복원 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget

`CCmdTarget` 개체를 생성합니다.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb

OLE 동사를 수행 하 여 지정 된 동작이 발생 합니다.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
동사의 숫자 식별자입니다.

*lpMsg*<br/>
에 대 한 포인터를 [MSG](/windows/desktop/api/winuser/ns-winuser-msg) 동사를 호출한 이벤트 (예: 두 번 클릭)를 설명 하는 구조입니다.

*hWndParent*<br/>
개체가 포함된 문서 창의 핸들입니다.

*lpRect*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 개체를 정의 하는 픽셀 단위의 좌표가 포함 된 구조체의 경계 사각형 *hwndParent*합니다.

### <a name="return-value"></a>반환 값

TRUE 이면 성공적이 고, 그렇지 않으면 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 구현의 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb)합니다. 가능한 작업 열거 하는 [CCmdTarget::EnumOleVerbs](#enumoleverbs)합니다.

##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation

OLE automation 개체를 사용 하도록 설정 하려면이 함수를 호출 합니다.

```
void EnableAutomation();
```

### <a name="remarks"></a>설명

이 함수는 일반적으로 개체의 생성자에서 호출 되 고 디스패치 맵 클래스의 선언 된 경우에 호출 해야 합니다. Automation에 대 한 자세한 내용은 문서를 참조 하세요 [자동화 클라이언트](../../mfc/automation-clients.md) 하 고 [자동화 서버](../../mfc/automation-servers.md)합니다.

##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections

연결 지점을 통해 이벤트 발생을 수 있습니다.

```
void EnableConnections();
```

### <a name="remarks"></a>설명

연결점을 사용 하려면 파생된 클래스의 생성자에서이 멤버 함수를 호출 합니다.

##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib

개체의 형식 라이브러리를 사용 하도록 설정 합니다.

```
void EnableTypeLib();
```

### <a name="remarks"></a>설명

생성자에서이 멤버 함수를 호출 하면 `CCmdTarget`-형식 정보를 제공 하는 경우 개체를 파생 합니다.

##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor

이 함수를 호출한 후 호출을 `BeginWaitCursor` 이전 커서 모래 시계 커서에서 반환할 멤버 함수입니다.

```
void EndWaitCursor();
```

### <a name="remarks"></a>설명

프레임 워크는 또한 모래 시계 커서를 호출한 후이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs

개체의 OLE 동사를 열거합니다.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>매개 변수

*ppenumOleVerb*<br/>
에 대 한 포인터에 대 한 포인터를 [IEnumOLEVERB](/windows/desktop/api/oleidl/nn-oleidl-ienumoleverb) 인터페이스입니다.

### <a name="return-value"></a>반환 값

개체가 하나 이상의 OLE 동사를 지원 하면 TRUE (이때 \* *ppenumOleVerb* 가리키는 `IEnumOLEVERB` 열거자 인터페이스)이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 구현의 [ioleobject:: Enumverbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs)합니다.

##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch

매핑할이 함수를 호출을 `IDispatch` 클래스의 automation 멤버 함수에서 받은 포인터를 `CCmdTarget` 의 인터페이스를 구현 하는 개체는 `IDispatch` 개체입니다.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CCmdTarget` 연관 된 개체 *lpDispatch*합니다. 없으면이 함수는 NULL을 반환 합니다 `IDispatch` 개체는 Microsoft Foundation Class로 인식 되지 않습니다 `IDispatch` 개체입니다.

### <a name="remarks"></a>설명

이 함수의 결과 멤버 함수에 대 한 호출의 역 `GetIDispatch`합니다.

##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID

기본 디스패치 인터페이스 ID를 가져옵니다.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>매개 변수

*pIID*<br/>
인터페이스 ID에 대 한 포인터 (한 [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931)).

### <a name="return-value"></a>반환 값

TRUE 이면 성공적이 고, 그렇지 않으면 FALSE. 성공 하면 \* *pIID* 기본 디스패치 인터페이스 ID로 설정 되어

### <a name="remarks"></a>설명

파생된 클래스에서이 멤버 함수를 재정의 해야 (재정의 되지 않으면 `GetDispatchIID` FALSE를 반환 합니다). 참조 [COleControl](../../mfc/reference/colecontrol-class.md)합니다.

##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch

검색 하려면이 멤버 함수를 호출 합니다 `IDispatch` 포인터 반환 하거나 자동화 메서드에서 `IDispatch` 포인터나는 `IDispatch` 포인터 참조로.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>매개 변수

*bAddRef*<br/>
개체에 대 한 참조 횟수를 증가 것인지 지정 합니다.

### <a name="return-value"></a>반환 값

`IDispatch` 개체와 연결 된 포인터입니다.

### <a name="remarks"></a>설명

에 대 한 호출 하는 개체 `EnableAutomation` 이 함수가 기본 클래스 구현에 포인터를 반환 해당 생성자의 경우 사용 하도록 설정 하는 자동화를 쉽게 `IDispatch` 을 통해 통신 하는 클라이언트에서 사용 되는 `IDispatch` 인터페이스입니다. 호출 하는 데 필요한 이므로 포인터에 대 한 참조를 추가이 함수를 자동으로 호출 [iunknown:: Addref](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)합니다.

##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount

개체를 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>반환 값

형식 정보 인터페이스의 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 구현 [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)합니다.

파생된 클래스에는 (0 또는 1)를 제공 하는 형식 정보 인터페이스의 수를 반환 하려면이 함수를 재정의 해야 합니다. 재정의 되지 않으면 `GetTypeInfoCount` 0을 반환 합니다. 재정의 하려면 사용 합니다 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 도 구현 하는 매크로 `GetTypeLib` 및 `GetTypeLibCache`.

##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid

지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>매개 변수

*lcid*<br/>
로캘 식별자 ( `LCID`).

*guid*<br/>
합니다 [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) 형식 설명입니다.

*ppTypeInfo*<br/>
에 대 한 포인터에 대 한 포인터를 `ITypeInfo` 인터페이스입니다.

### <a name="return-value"></a>반환 값

호출의 성공 여부를 나타내는 HRESULT입니다. 성공 하면 \* *ppTypeInfo* 형식 정보 인터페이스를 가리킵니다.

##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib

형식 라이브러리에 대 한 포인터를 가져옵니다.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>매개 변수

*lcid*<br/>
LCID(로캘 식별자)입니다.

*ppTypeLib*<br/>
에 대 한 포인터에 대 한 포인터를 `ITypeLib` 인터페이스입니다.

### <a name="return-value"></a>반환 값

호출의 성공 여부를 나타내는 HRESULT입니다. 성공 하면 \* *ppTypeLib* 형식 라이브러리 인터페이스를 가리킵니다.

### <a name="remarks"></a>설명

파생된 클래스에서이 멤버 함수를 재정의 해야 (재정의 되지 않으면 `GetTypeLib` TYPE_E_CANTLOADLIBRARY 반환). 사용 합니다 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 도 구현 하는 매크로 `GetTypeInfoCount` 및 `GetTypeLibCache`합니다.

##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache

형식 라이브러리 캐시를 가져옵니다.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>반환 값

`CTypeLibCache` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

파생된 클래스에서이 멤버 함수를 재정의 해야 (재정의 되지 않으면 `GetTypeLibCache` NULL을 반환 합니다). 사용 합니다 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 도 구현 하는 매크로 `GetTypeInfoCount` 및 `GetTypeLib`합니다.

##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed

이 함수는 MFC의 구현에 의해 호출 됩니다 `IDispatch::Invoke` 하는 경우 지정 된 자동화 메서드를 확인 하려면 (구분 *dispid*) 호출할 수 있습니다.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
디스패치 id입니다.

### <a name="return-value"></a>반환 값

메서드 호출, 그렇지 않으면 FALSE 일 수 있으면 TRUE입니다.

### <a name="remarks"></a>설명

하는 경우 `IsInvokeAllowed` TRUE를 반환 `Invoke` ; 메서드를 호출 하려면 진행이 고, 그렇지 `Invoke` E_UNEXPECTED를 반환 실패 합니다.

파생된 클래스에서 적절 한 값을 반환 하려면이 함수를 재정의할 수 있습니다 (재정의 되지 않으면 `IsInvokeAllowed` TRUE를 반환 합니다). 특히 참조 [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed)합니다.

##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected

사용 하 여 `IsResultExpected` automation 함수 호출에서 반환 값을 클라이언트에 필요한 지 여부를 확인 합니다.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>반환 값

자동화 기능 값을 반환 해야 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

클라이언트를 사용 하 여 아니면 함수 호출의 결과 무시 하는지 여부에 대 한 MFC에 대 한 정보를 제공 하는 OLE 인터페이스 및 MFC 사용 하 여이 정보에 대 한 호출의 결과 결정 하려면 `IsResultExpected`합니다. 반환 값의 프로덕션 시간 또는 리소스-집약적인 경우 반환 값을 계산 하기 전에이 함수를 호출 하 여 효율성을 높일 수 있습니다.

이 함수에서에서 호출 하면 해당 automation 함수는 다른 automation 함수에서 유효한 반환 값을 얻으려면 됩니다 있도록 클라이언트 호출에 한 번만 0을 반환 합니다.

`IsResultExpected` 자동화 함수 호출을 진행에서 없을 때 호출 되는 경우 0이 아닌 값을 반환 합니다.

##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg

경로 명령 메시지를 발송 하 고 명령 사용자 인터페이스 개체 업데이트를 처리 하는 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
포함 명령 id입니다.

*nCode*<br/>
명령 알림 코드를 식별합니다. 참조 **주의** 에 대 한 자세한 내용은 *nCode*합니다.

*pExtra*<br/>
값에 따라 사용할 *nCode*합니다. 참조 **주의** 에 대 한 자세한 내용은 *pExtra*합니다.

*pHandlerInfo*<br/>
NULL이 아닌 경우 `OnCmdMsg` 채웁니다 합니다 *pTarget* 및 *pmf* 의 멤버는 *pHandlerInfo* 명령 디스패치 하는 대신 구조입니다. 일반적으로이 매개 변수는 NULL 이어야 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 메시지 처리 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이것이 프레임 명령 아키텍처의 기본 구현 루틴입니다.

런타임에 `OnCmdMsg` 루트 클래스를 호출 하 여 명령 자체를 처리 또는 다른 개체에 명령을 디스패치합니다 `CCmdTarget::OnCmdMsg`는 실제 메시지 맵에서 조회를 않습니다. 기본 명령 라우팅의 설명은 참조 하세요 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.

가끔은 프레임 워크를 확장 하려면이 멤버 함수를 재정의 하려는 표준 명령 라우팅입니다. 가리킵니다 [기술 참고 21](../../mfc/tn021-command-and-message-routing.md) 명령 라우팅 아키텍처의 고급 정보에 대 한 합니다.

재정의 하는 경우 `OnCmdMsg`에 대 한 적절 한 값을 제공 해야 합니다 *nCode*, 명령 알림 코드 및 *pExtra*의 값에 따라 다름 *nCode* . 다음 표에서 해당 값을 나열합니다.

|*nCode* 값|*pExtra* value|
|-------------------|--------------------|
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease

개체에서 마지막 OLE 참조가 해제 될 때 프레임 워크에서 호출 됩니다.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>설명

이 상황에 대 한 특수 처리를 제공 하려면이 함수를 재정의 합니다. 기본 구현에서는 개체를 삭제합니다.

##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor

(예를 들어, 메시지 상자에 열리고 후 시간이 오래 걸리는 작업을 분석 하는 동안 닫으면) 시스템 커서 변경 된 후 적절 한 모래 시계 커서를 복원 하려면이 함수를 호출 합니다.

```
void RestoreWaitCursor();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>참고자료

[ACDUAL MFC 샘플](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[COleDispatchDriver 클래스](../../mfc/reference/coledispatchdriver-class.md)

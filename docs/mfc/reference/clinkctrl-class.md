---
title: CLinkCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: 38f529f46623bc7095879b29fba09427626073ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225482"
---
# <a name="clinkctrl-class"></a>CLinkCtrl 클래스

Windows의 공용 SysLink 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|`CLinkCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CLinkCtrl::Create](#create)|링크 컨트롤을 만들고 연결 하는 `CLinkCtrl` 개체입니다.|
|[CLinkCtrl::CreateEx](#createex)|확장된 스타일을 사용 하 여 링크 컨트롤을 만들고 연결 하는 `CLinkCtrl` 개체입니다.|
|[CLinkCtrl::GetIdealHeight](#getidealheight)|링크 컨트롤의 이상적인 높이 검색합니다.|
|[CLinkCtrl::GetIdealSize](#getidealsize)|링크의 지정된 된 너비에 따라 현재 링크 컨트롤에 대 한 링크 텍스트의 기본 설정된 높이 계산합니다.|
|[CLinkCtrl::GetItem](#getitem)|상태 및 링크 컨트롤 항목의 특성을 검색합니다.|
|[CLinkCtrl::GetItemID](#getitemid)|링크 컨트롤 항목의 ID를 검색합니다.|
|[CLinkCtrl::GetItemState](#getitemstate)|링크 컨트롤 항목의 상태를 검색합니다.|
|[CLinkCtrl::GetItemUrl](#getitemurl)|링크 컨트롤 항목을 나타내는 URL을 검색 합니다.|
|[CLinkCtrl::HitTest](#hittest)|사용자 지정 된 링크를 클릭 여부를 결정 합니다.|
|[CLinkCtrl::SetItem](#setitem)|상태 및 링크 컨트롤 항목의 특성을 설정합니다.|
|[CLinkCtrl::SetItemID](#setitemid)|링크 컨트롤 항목의 ID를 설정 합니다.|
|[CLinkCtrl::SetItemState](#setitemstate)|링크 컨트롤 항목의 상태를 설정합니다.|
|[CLinkCtrl::SetItemUrl](#setitemurl)|링크 컨트롤 항목을 나타내는 URL을 설정 합니다.|

## <a name="remarks"></a>설명

"Link 컨트롤" 창에 하이퍼텍스트 링크를 포함 하는 편리한 방법을 제공 합니다. 실제 컨트롤에 표시 된 위쪽 텍스트를 렌더링 하 고 포함 된 링크를 클릭할 때 적절 한 응용 프로그램을 시작 하는 창입니다. 여러 링크 컨트롤 내에서 지원 됩니다 및 인덱스는 0부터 시작 하 여 액세스할 수 있습니다.

이 컨트롤 (및 따라서는 `CLinkCtrl` 클래스) Windows xp 및 이후 버전을 실행 하는 프로그램에만 사용할 수 있습니다.

자세한 내용은 [SysLink 컨트롤](/windows/desktop/Controls/syslink-overview) Windows SDK에 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="clinkctrl"></a>  CLinkCtrl::CLinkCtrl

`CLinkCtrl` 개체를 생성합니다.

```
CLinkCtrl();
```

##  <a name="create"></a>  CLinkCtrl::Create

링크 컨트롤을 만들고 연결 하는 `CLinkCtrl` 개체입니다.

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszLinkMarkup*<br/>
표시할 텍스트 표시를 포함 하는 0으로 끝나는 문자열에 대 한 포인터입니다. 자세한 내용은 항목의 "태그 및 링크 액세스" 섹션을 참조 하세요 [SysLink 컨트롤의 개요](/windows/desktop/Controls/syslink-overview)합니다.

*dwStyle*<br/>
링크 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용 됩니다. 참조 [공용 컨트롤 스타일](/windows/desktop/Controls/common-control-styles) 에 `Windows SDK` 자세한 내용은 합니다.

*rect*<br/>
링크 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조입니다.

*pParentWnd*<br/>
링크 컨트롤의 부모 창을 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
링크 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

생성 된 `CLinkCtrl` 두 단계에서 개체입니다. 먼저 생성자를 호출 하 고 호출 `Create`, 링크 컨트롤을 만들고 연결 하는 `CLinkCtrl` 개체입니다. 컨트롤을 사용 하 여 확장된 창 스타일을 사용 하려는 경우 호출할 [CLinkCtrl::CreateEx](#createex) 대신 `Create`합니다.

두 번째 형태는 `Create` 메서드는 사용 되지 않습니다. 지정 하는 첫 번째 폼을 사용 합니다 *lpszLinkMarkup* 매개 변수입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 라는 두 개의 변수를 정의 `m_Link1` 및 `m_Link2`, 두 개의 링크 컨트롤에 액세스 하는 데 사용 되는 합니다.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 다른 링크 컨트롤의 위치를 기반으로 하는 하나의 링크 컨트롤을 만듭니다. 리소스 로더는 응용 프로그램 시작 시 첫 번째 링크 컨트롤을 만듭니다. 응용 프로그램의 OnInitDialog 메서드 들어가면 첫 번째 링크 컨트롤의 위치를 기준으로 두 번째 링크 컨트롤이 만들어집니다. 다음 두 번째 링크 컨트롤 표시 하는 텍스트에 맞게 크기를 있습니다.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

##  <a name="createex"></a>  CLinkCtrl::CreateEx

확장된 스타일을 사용 하 여 링크 컨트롤을 만들고 연결 하는 `CLinkCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>매개 변수

*lpszLinkMarkup*<br/>
표시할 텍스트 표시를 포함 하는 0으로 끝나는 문자열에 대 한 포인터입니다. 자세한 내용은 항목의 "태그 및 링크 액세스" 섹션을 참조 하세요 [SysLink 컨트롤의 개요](/windows/desktop/Controls/syslink-overview)합니다.

*dwExStyle*<br/>
링크 컨트롤의 확장된 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록은 참조 하세요. 합니다 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

*dwStyle*<br/>
링크 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용 됩니다. 자세한 내용은 [공용 컨트롤 스타일](/windows/desktop/Controls/common-control-styles) Windows SDK의 합니다.

*rect*<br/>
링크 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조입니다.

*pParentWnd*<br/>
링크 컨트롤의 부모 창을 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
링크 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of [만들기](#create) 확장된 Windows 스타일 상수를 적용 합니다.

두 번째 형태는 `CreateEx` 메서드는 사용 되지 않습니다. 지정 하는 첫 번째 폼을 사용 합니다 *lpszLinkMarkup* 매개 변수입니다.

##  <a name="getidealheight"></a>  CLinkCtrl::GetIdealHeight

링크 컨트롤의 이상적인 높이 검색합니다.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>반환 값

픽셀 단위의 컨트롤의 이상적인 높이입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_GETIDEALHEIGHT](/windows/desktop/Controls/lm-getidealheight)Windows SDK에 설명 된 대로 합니다.

##  <a name="getidealsize"></a>  CLinkCtrl::GetIdealSize

링크의 지정된 된 너비에 따라 현재 링크 컨트롤에 대 한 링크 텍스트의 기본 설정된 높이 계산합니다.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*cxMaxWidth*|[in] 링크 픽셀에서의 최대 너비입니다.|
|[out] \* *pSize*|Windows에 대 한 포인터 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조입니다. 이 메서드는 반환 될 때를 *cy* 의 멤버는 `SIZE` 구조에 지정 된 링크 텍스트의 너비에 대 한 이상적인 링크 텍스트 높이가 포함 됩니다 *cxMaxWidth*합니다. 합니다 *cx* 구조체의 멤버에 실제로 필요한 링크 텍스트의 너비를 포함 합니다.|

### <a name="return-value"></a>반환 값

링크 텍스트 픽셀에서의 기본 설정된 높이입니다. 반환 값은 값으로 동일한 합니다 *cy* 의 멤버는 `SIZE` 구조입니다.

### <a name="remarks"></a>설명

예는 `GetIdealSize` 메서드를에서 예제를 참조 하세요 [CLinkCtrl::Create](#create)합니다.

이 메서드는 전송 된 [LM_GETIDEALSIZE](/windows/desktop/Controls/lm-getidealsize) Windows SDK에 설명 된 메시지입니다.

##  <a name="getitem"></a>  CLinkCtrl::GetItem

상태 및 링크 컨트롤 항목의 특성을 검색합니다.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
에 대 한 포인터를 [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) 항목 정보를 받는 구조체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_GETITEM](/windows/desktop/Controls/lm-getitem)Windows SDK에 설명 된 대로 합니다.

##  <a name="getitemid"></a>  CLinkCtrl::GetItemID

링크 컨트롤 항목의 ID를 검색합니다.

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>매개 변수

*iLink*<br/>
링크 컨트롤 항목의 인덱스입니다.

*strID*<br/>
A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 지정된 된 항목의 ID를 포함 하는 개체입니다.

*szID*<br/>
지정된 된 항목의 ID를 포함 하는 null 종료 문자열입니다.

*cchID*<br/>
크기의 문자를 *szID* 버퍼입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

> [!NOTE]
>  이 함수는도 FALSE를 반환 하는 경우의 버퍼 *szID 또는* MAX_LINKID_TEXT 보다 작습니다.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 ID를 검색합니다. 자세한 내용은 Win32 메시지를 참조 하세요 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK에 있습니다.

##  <a name="getitemstate"></a>  CLinkCtrl::GetItemState

링크 컨트롤 항목의 상태를 검색합니다.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>매개 변수

*iLink*<br/>
링크 컨트롤 항목의 인덱스입니다.

*pnState*<br/>
지정 된 상태 항목의 값입니다.

*stateMask*<br/>
가져올 대상이 되는 상태 항목을 설명 하는 플래그의 조합입니다. 목록은 값에 대 한 설명을 참조는 `state` 멤버를 [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) 구조입니다. 허용 되는 항목 동일 허용 `state`합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 지정 된 상태 항목의 값을 검색합니다. 자세한 내용은 Win32 메시지를 참조 하세요 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK에 있습니다.

##  <a name="getitemurl"></a>  CLinkCtrl::GetItemUrl

링크 컨트롤 항목을 나타내는 URL을 검색 합니다.

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>매개 변수

*iLink*<br/>
링크 컨트롤 항목의 인덱스입니다.

*strUrl*<br/>
A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 지정된 된 항목을 나타내는 URL이 포함 된 개체

*szUrl*<br/>
지정된 된 항목을 나타내는 URL이 포함 된 null로 끝나는 문자열을

*cchUrl*<br/>
크기의 문자를 *szURL* 버퍼입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

> [!NOTE]
>  이 함수는도 FALSE를 반환 하는 경우의 버퍼 *szUrl 또는 strUrl* MAX_LINKID_TEXT 보다 작습니다.

### <a name="remarks"></a>설명

지정 된 링크 컨트롤 항목을 나타내는 URL을 검색 합니다. 자세한 내용은 Win32 메시지를 참조 하세요 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK에 있습니다.

##  <a name="hittest"></a>  CLinkCtrl::HitTest

사용자가 지정 된 링크를 클릭 한 경우를 결정 합니다.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>매개 변수

*phti*<br/>
에 대 한 포인터를 `LHITTESTINFO` 사용자가 클릭 한 링크에 대 한 모든 정보를 포함 하는 구조체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_HITTEST](/windows/desktop/Controls/lm-hittest)Windows SDK에 설명 된 대로 합니다.

##  <a name="setitem"></a>  CLinkCtrl::SetItem

상태 및 링크 컨트롤 항목의 특성을 설정합니다.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
에 대 한 포인터를 [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) 설정 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_SETITEM](/windows/desktop/Controls/lm-setitem)Windows SDK에 설명 된 대로 합니다.

##  <a name="setitemid"></a>  CLinkCtrl::SetItemID

링크 컨트롤 항목의 ID를 검색합니다.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>매개 변수

*iLink*<br/>
링크 컨트롤 항목의 인덱스입니다.

*szID*<br/>
지정된 된 항목의 ID를 포함 하는 null 종료 문자열입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 ID를 설정합니다. 자세한 내용은 Win32 메시지를 참조 하세요 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK에 있습니다.

##  <a name="setitemstate"></a>  CLinkCtrl::SetItemState

링크 컨트롤 항목의 상태를 검색합니다.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>매개 변수

*iLink*<br/>
링크 컨트롤 항목의 인덱스입니다.

*pnState*<br/>
설정할 지정 된 상태 항목의 값입니다.

*stateMask*<br/>
설정 상태 항목을 설명 하는 플래그의 조합입니다. 목록은 값에 대 한 설명을 참조는 `state` 멤버를 [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) 구조입니다. 허용 되는 항목 동일 허용 `state`합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 지정 된 상태 항목의 값을 설정합니다. 자세한 내용은 Win32 메시지를 참조 하세요 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK에 있습니다.

##  <a name="setitemurl"></a>  CLinkCtrl::SetItemUrl

링크 컨트롤 항목을 나타내는 URL을 설정 합니다.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*iLink*<br/>
링크 컨트롤 항목의 인덱스입니다.

*szUrl*<br/>
지정된 된 항목을 나타내는 URL이 포함 된 null로 끝나는 문자열을

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

지정 된 링크 컨트롤 항목을 나타내는 URL을 설정 합니다. 자세한 내용은 Win32 메시지를 참조 하세요 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)

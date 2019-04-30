---
title: IAtlMemMgr 클래스
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: b9b6ac6dc265378f617e053bc48ac6030425cef4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276264"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr 클래스

이 클래스는 메모리 관리자 인터페이스를 나타냅니다.

## <a name="syntax"></a>구문

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Allocate](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[무료](#free)|메모리 블록을 해제 하려면이 메서드를 호출 합니다.|
|[GetSize](#getsize)|할당된 된 메모리 블록의 크기를 검색 하려면이 메서드를 호출 합니다.|
|[Reallocate](#reallocate)|메모리 블록 다시 할당 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

이 인터페이스에서 구현 됩니다 [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md)합니다 [CLocalHeap](../../atl/reference/clocalheap-class.md)를 [CGlobalHeap](../../atl/reference/cglobalheap-class.md), 또는 [CWin32Heap](../../atl/reference/cwin32heap-class.md).

> [!NOTE]
>  로컬 및 전역 힙 함수를 다른 메모리 관리 함수를 사용 하 여 보다 느린 및 많은 기능을 제공 하지 않습니다. 따라서 새 응용 프로그램을 사용 해야 합니다 [힙 함수](/windows/desktop/Memory/heap-functions)합니다. 사용할 수 있는 이러한 합니다 [CWin32Heap](../../atl/reference/cwin32heap-class.md) 클래스입니다.

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** atlmem.h

##  <a name="allocate"></a>  IAtlMemMgr::Allocate

메모리 블록을 할당하려면 이 메서드를 호출합니다.

```
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*nBytes*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>반환 값

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

호출 [IAtlMemMgr::Free](#free) 하거나 [IAtlMemMgr::Reallocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

### <a name="example"></a>예제

예를 들어 참조 된 [IAtlMemMgr 개요](../../atl/reference/iatlmemmgr-class.md)합니다.

##  <a name="free"></a>  IAtlMemMgr::Free

메모리 블록을 해제 하려면이 메서드를 호출 합니다.

```
void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 가져온 메모리를 확보 [IAtlMemMgr::Allocate](#allocate) 하거나 [IAtlMemMgr::Reallocate](#reallocate)합니다.

### <a name="example"></a>예제

예를 들어 참조 된 [IAtlMemMgr 개요](../../atl/reference/iatlmemmgr-class.md)합니다.

##  <a name="getsize"></a>  IAtlMemMgr::GetSize

할당된 된 메모리 블록의 크기를 검색 하려면이 메서드를 호출 합니다.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

메모리 블록의 크기 (바이트)를 반환합니다.

### <a name="example"></a>예제

예를 들어 참조 된 [IAtlMemMgr 개요](../../atl/reference/iatlmemmgr-class.md)합니다.

##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate

이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.

```
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

*nBytes*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>반환 값

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

호출 [IAtlMemMgr::Free](#free) 하거나 [IAtlMemMgr::Reallocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

개념적으로이 메서드는 기존 메모리를 해제 하 고 새 메모리 블록을 할당 합니다. 실제로 기존 메모리를 확장 하거나 그렇지 않은 경우 다시 수 있습니다.

### <a name="example"></a>예제

예를 들어 참조 된 [IAtlMemMgr 개요](../../atl/reference/iatlmemmgr-class.md)합니다.

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

`AllowContextMenu` 속성 상황에 맞는 메뉴를 표시 하는 호스트 된 컨트롤 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*pbAllowContextMenu*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI

`AllowShowUI` 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스에 표시할 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*pbAllowShowUI*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation

`AllowWindowlessActivation` 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*pbAllowWindowless*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor

`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>매개 변수

*pclrBackground*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을 (인지에 따라 호스트 창의 부모 대화 여부)이이 속성의 값을 기본값으로 COLOR_BTNFACE 또는 COLOR_WINDOW를 사용 합니다.

##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault` 기본 컨트롤 인지 확인 하려면 제어를 허용 하는 앰비언트 속성이입니다.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*pbDisplayAsDefault*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` 속성을 두 번 클릭에 대 한 응답에서 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHostDoubleClickFlags*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIDBLCLK_DEFAULT를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags

`DocHostFlags` 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHostFlags*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIFLAG_NO3DBORDER를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font

`Font` 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
[out] 주소는 `IFontDisp` 이 속성의 현재 값을 수신 하는 데 사용 되는 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 기본 GUI 글꼴 또는 시스템 글꼴을 사용합니다.

##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor

`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>매개 변수

*pclrForeground*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 시스템 창 텍스트 색을 사용합니다.

##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID

`LocaleID` 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*plcidLocaleID*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 기본 값으로 사용자의 기본 로캘을 사용 하는 ATL 호스트 개체 구현 합니다.

이 메서드를 사용 하 여 앰비언트 LocalID를 검색할 수 있습니다, 즉, 프로그램의 LocaleID 컨트롤 사용량입니다. LocaleID를 알게 되 면 리소스 파일 또는 위성 DLL에서 등 로캘별 캡션 로드 하는 코드, 오류 메시지 텍스트를 호출할 수 있습니다.

##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect

`MessageReflect` 앰비언트 속성은 컨테이너 호스트 된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>매개 변수

*pbMessageReflect*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath

`OptionKeyPath` 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*pbstrOptionKeyPath*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

`ShowGrabHandles` 앰비언트 속성 경우 해당 그려야 자체 잡기 핸들을 사용 하 여 확인 하도록 허용 합니다.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>매개 변수

*pbShowGrabHandles*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현에서는 항상이 속성의 값으로 VARIANT_FALSE가 반환 됩니다.

##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching

`ShowHatching` 앰비언트 속성 무늬 자체 그리기 해야 하는 경우 확인 하도록 허용 합니다.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>매개 변수

*pbShowHatching*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현에서는 항상이 속성의 값으로 VARIANT_FALSE가 반환 됩니다.

##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode

`UserMode` 속성에는 컨테이너의 앰비언트 사용자 모드를 지정 합니다.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>매개 변수

*pbUserMode*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu

`AllowContextMenu` 속성 상황에 맞는 메뉴를 표시 하는 호스트 된 컨트롤 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*bAllowContextMenu*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI

`AllowShowUI` 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스에 표시할 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*bAllowShowUI*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation

`AllowWindowlessActivation` 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*bAllowWindowless*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor

`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>매개 변수

*clrBackground*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을 (인지에 따라 호스트 창의 부모 대화 여부)이이 속성의 값을 기본값으로 COLOR_BTNFACE 또는 COLOR_WINDOW를 사용 합니다.

##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault` 기본 컨트롤 인지 확인 하려면 제어를 허용 하는 앰비언트 속성이입니다.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*bDisplayAsDefault*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` 속성을 두 번 클릭에 대 한 응답에서 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHostDoubleClickFlags*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIDBLCLK_DEFAULT를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags

`DocHostFlags` 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHostFlags*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIFLAG_NO3DBORDER를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font

`Font` 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 기본 GUI 글꼴 또는 시스템 글꼴을 사용합니다.

##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor

`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>매개 변수

*clrForeground*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 시스템 창 텍스트 색을 사용합니다.

##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID

`LocaleID` 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*lcidLocaleID*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 기본 값으로 사용자의 기본 로캘을 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect

`MessageReflect` 앰비언트 속성은 컨테이너 호스트 된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>매개 변수

*bMessageReflect*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath

`OptionKeyPath` 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*bstrOptionKeyPath*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

`UserMode` 속성에는 컨테이너의 앰비언트 사용자 모드를 지정 합니다.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>매개 변수

*bUserMode*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

이 메서드는 사용자 정의 인터페이스를 사용 하 여 기본 앰비언트 속성 인터페이스를 보완 하기 위해 호출 됩니다.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>매개 변수

*pDispatch*<br/>
새 인터페이스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

때 `SetAmbientDispatch` 라고 새 인터페이스에 대 한 포인터를 사용 하 여이 새 인터페이스 하는 데 사용할 속성 또는 호스팅된 컨트롤에서 묻는 메시지가 표시 되는 메서드를 호출 합니다.-해당 속성에서 이미 제공 하지 않는 경우 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl

기존 (및 이전에 초기화) 컨트롤을 식별 하 여 창을 사용 하 여 호스트 개체에 연결 *hWnd*합니다.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*pUnkControl*<br/>
[in] 에 대 한 포인터를 `IUnknown` 호스트 개체에 연결 될 컨트롤의 인터페이스입니다.

*hWnd*<br/>
[in] 호스팅에 사용 되는 창 핸들입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl

컨트롤을 만들고, 초기화 및 구분 창에 호스팅합니다 *hWnd*합니다.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
[in] 만들 컨트롤을 식별 하는 문자열입니다. (중괄호를 포함 해야 함) CLSID, ProgID, URL 또는 원시 HTML 수 (접두사로 **MSHTML:**).

*hWnd*<br/>
[in] 호스팅에 사용 되는 창 핸들입니다.

*pStream*<br/>
[in] 컨트롤에 대 한 초기화 데이터를 포함 하는 스트림에 대 한 인터페이스 포인터입니다. NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

메시지를 컨트롤에 반영 될 수 있습니다 하 고 다른 컨테이너 기능을 사용할 수 있도록이 인터페이스를 노출 하는 호스트 개체에서이 창을 서브클래싱 할 됩니다.

이 메서드를 호출 하는 것 [IAxWinHostWindow::CreateControlEx](#createcontrolex)합니다.

사용이 허가 된 ActiveX 컨트롤을 참조 하세요 [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex)합니다.

##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx

ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [IAxWinHostWindow::CreateControl](#createcontrol)합니다.

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
[in] 만들 컨트롤을 식별 하는 문자열입니다. (중괄호를 포함 해야 함) CLSID, ProgID, URL 또는 원시 HTML 수 (접두사로 **MSHTML:**).

*hWnd*<br/>
[in] 호스팅에 사용 되는 창 핸들입니다.

*pStream*<br/>
[in] 컨트롤에 대 한 초기화 데이터를 포함 하는 스트림에 대 한 인터페이스 포인터입니다. NULL 일 수 있습니다.

*ppUnk*<br/>
[out] 수신할 포인터의 주소는 `IUnknown` 만든된 컨트롤의 인터페이스입니다. NULL 일 수 있습니다.

*riidAdvise*<br/>
[in] 포함된 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다. Can be IID_NULL.

*punkAdvise*<br/>
[in] 에 대 한 포인터를 `IUnknown` 으로 지정 된 포함된 된 개체의 연결 지점에 연결 되어 싱크 개체의 인터페이스가 `iidSink`합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

와 달리 합니다 `CreateControl` 메서드를 `CreateControlEx` 새로 만든된 컨트롤에 대 한 인터페이스 포인터를 수신 하 고 컨트롤에서 발생 하는 이벤트를 수신 하는 이벤트 싱크 설정 할 수도 있습니다.

사용이 허가 된 ActiveX 컨트롤을 참조 하세요 [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)합니다.

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

호스팅된 컨트롤에서 제공 된 인터페이스 포인터를 반환 합니다.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
[in] 요청 된 컨트롤에 인터페이스의 ID입니다.

*ppvObject*<br/>
[out] 만든된 컨트롤의 지정된 된 인터페이스를 수신할 포인터의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch

통해 포함 된 컨트롤에 사용할 수 있는 외부 dispinterface를 설정 합니다 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) 메서드.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
[in] 에 대 한 포인터는 `IDispatch` 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler

외부를 설정 하려면이 함수를 호출 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 에 대 한 인터페이스를 `CAxWindow` 개체입니다.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
[in] 에 대 한 포인터는 `IDocHostUIHandlerDispatch` 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수에 대 한 호스트의 사이트를 쿼리 하는 (예: 웹 브라우저 컨트롤) 컨트롤에서 사용 되는 `IDocHostUIHandlerDispatch` 인터페이스입니다.

##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic

사용이 허가 된 컨트롤을 만들고, 초기화 및 구분 창에 호스팅합니다 `hWnd`합니다.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>매개 변수

*bstrLic*<br/>
[in] 컨트롤에 대 한 라이선스 키를 포함 하는 BSTR입니다.

### <a name="remarks"></a>설명

참조 [IAxWinHostWindow::CreateControl](#createcontrol) 나머지 매개 변수 및 반환 값에 대 한 합니다.

이 메서드를 호출 하는 것 [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `IAxWinHostWindowLic::CreateControlLic`합니다.

##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx

사용이 허가 된 ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [IAxWinHostWindow::CreateControl](#createcontrol)합니다.

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>매개 변수

*bstrLic*<br/>
[in] 컨트롤에 대 한 라이선스 키를 포함 하는 BSTR입니다.

### <a name="remarks"></a>설명

참조 [IAxWinHostWindow::CreateControlEx](#createcontrolex) 나머지 매개 변수 및 반환 값에 대 한 합니다.

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `IAxWinHostWindowLic::CreateControlLicEx`합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

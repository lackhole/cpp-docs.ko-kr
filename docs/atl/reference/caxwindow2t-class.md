---
title: CAxWindow2T 클래스
ms.date: 11/04/2016
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
ms.openlocfilehash: 0d5991dcbf79d1c2415594636a09908586d1dc2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260030"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T 클래스

이 클래스는 사용이 허가 된 ActiveX 컨트롤 호스팅에 대 한 지원 역시를 ActiveX 컨트롤을 호스트 하는 창 조작 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>매개 변수

*TBase*<br/>
클래스 `CAxWindowT` 파생 됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAxWindow2T::Create](#create)|호스트 창을 만듭니다.|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만듭니다, 그리고 초기화, 지정 된 창에서 호스트 및 컨트롤에서 인터페이스 포인터를 (또는 포인터)를 검색 합니다.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|창 클래스의 이름을 검색 하는 정적 메서드.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAxWindow2T::operator =](#operator_eq)|기존 HWND 할당 `CAxWindow2T` 개체입니다.|

## <a name="remarks"></a>설명

`CAxWindow2T` ActiveX 컨트롤을 호스팅하는 창 조작에 대 한 메서드를 제공 합니다. `CAxWindow2T` 사용이 허가 된 ActiveX 컨트롤 호스팅에 대 한 지원이 있습니다. 제공 하는 호스트 하는 " **AtlAxWinLic80**"에 의해 래핑되는 `CAxWindow2T`합니다.

클래스 `CAxWindow2` 의 특수화로 구현 되는 `CAxWindow2T` 클래스입니다. 이 특수화로 선언 됩니다.

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` 멤버에서 나와 [CAxWindow](../../atl/reference/caxwindow-class.md)합니다.

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 이 클래스의 멤버를 사용 하는 샘플에 대 한 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="caxwindow2t"></a>  CAxWindow2T::CAxWindow2T

`CAxWindow2T` 개체를 생성합니다.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
기존 창 핸들입니다.

##  <a name="create"></a>  CAxWindow2T::Create

호스트 창을 만듭니다.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="remarks"></a>설명

`CAxWindow2T::Create` 호출 [CWindow::Create](../../atl/reference/cwindow-class.md#create) LPCTSTR을 사용 하 여 *lpstrWndClass* 컨트롤 호스팅을 제공 하는 창 클래스에 매개 변수 설정 (`AtlAxWinLic80`).

참조 `CWindow::Create` 매개 변수 및 반환 값에 대 한 합니다.

**참고** 0 값으로 사용 되는 경우는 *MenuOrID* 매개 변수를 0U로 지정 되어야 합니다 (기본값) 컴파일러 오류를 방지 하려면.

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CAxWindow2T::Create`합니다.

##  <a name="createcontrollic"></a>  CAxWindow2T::CreateControlLic

사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>매개 변수

*bstrLicKey*<br/>
컨트롤에 대 한 라이선스 키 라이센스가 없는 컨트롤을 만드는 경우 NULL입니다.

### <a name="remarks"></a>설명

참조 [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) 나머지 매개 변수 및 반환 값에 대 한 합니다.

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CAxWindow2T::CreateControlLic`합니다.

##  <a name="createcontrollicex"></a>  CAxWindow2T::CreateControlLicEx

사용이 허가 된 ActiveX 컨트롤을 만듭니다, 그리고 초기화, 지정 된 창에서 호스트 및 컨트롤에서 인터페이스 포인터를 (또는 포인터)를 검색 합니다.

```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```

### <a name="parameters"></a>매개 변수

*bstrLicKey*<br/>
컨트롤에 대 한 라이선스 키 라이센스가 없는 컨트롤을 만드는 경우 NULL입니다.

### <a name="remarks"></a>설명

참조 [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) 나머지 매개 변수 및 반환 값에 대 한 합니다.

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CAxWindow2T::CreateControlLicEx`합니다.

##  <a name="getwndclassname"></a>  CAxWindow2T::GetWndClassName

창 클래스의 이름을 검색합니다.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>반환 값

창 클래스의 이름을 포함 하는 문자열에 대 한 포인터 (`AtlAxWinLic80`)는 사용이 허가 된 및 라이센스가 없는 ActiveX 컨트롤을 호스트할 수 있습니다.

##  <a name="operator_eq"></a>  CAxWindow2T::operator =

기존 HWND 할당 `CAxWindow2T` 개체입니다.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
기존 창 핸들입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)

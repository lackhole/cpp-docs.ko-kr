---
title: CBindStatusCallback 클래스
ms.date: 11/04/2016
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
ms.openlocfilehash: 6e5e55a23ee678bbedf76f608bc4fdf562cc1822
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259718"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback 클래스

이 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
데이터를 수신할 때 호출 되는 함수를 포함 하 여 클래스입니다.

*nBindFlags*<br/>
반환 되는 바인딩 플래그를 지정 [GetBindInfo](#getbindinfo)합니다. 기본 구현에서는 비동기가 되도록 바인딩을 설정 하 고, 최신 버전의 데이터/개체를 검색, 디스크 캐시에서 검색된 된 데이터를 저장 하지 않습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|생성자입니다.|
|[CBindStatusCallback::~CBindStatusCallback](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CBindStatusCallback::Download](#download)|다운로드 프로세스를 시작 하는 정적 메서드를 만듭니다는 `CBindStatusCallback` 개체와 호출 `StartAsyncDownload`합니다.|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|만들려는 바인딩 종류에 대 한 요청 정보를 비동기 모니커에서 호출 됩니다.|
|[CBindStatusCallback::GetPriority](#getpriority)|비동기 모니커 바인딩 작업의 우선 순위를 가져오려고에서 호출 됩니다. ATL 구현은 `E_NOTIMPL`합니다.|
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|사용할 수 있는 응용 프로그램에 데이터를 제공 하기 위해 호출 합니다. 데이터를 읽는 다음 데이터를 사용 하기 위해 전달 함수를 호출 합니다.|
|[CBindStatusCallback::OnLowResource](#onlowresource)|리소스가 부족 한지 때 호출 됩니다. ATL 구현은 S_OK를 반환 합니다.|
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|비동기 모니커 개체 인터페이스 포인터를 응용 프로그램에 전달 하 여 호출 됩니다. ATL 구현은 S_OK를 반환 합니다.|
|[CBindStatusCallback::OnProgress](#onprogress)|데이터 다운로드 프로세스의 진행률을 표시 하기 위해 호출 됩니다. ATL 구현은 S_OK를 반환 합니다.|
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|바인딩 시작 될 때 호출 됩니다.|
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|비동기 데이터 전송이 중지 될 때 호출 됩니다.|
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|사용할 수 있는 바이트를 초기화 하 고 URL 및 호출에서 푸시 유형 스트림 개체를 만듭니다를 0으로 읽은 바이트 수 `OnDataAvailable` 될 때마다 데이터를 사용할 수 있습니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|읽을 수 있는 바이트 수입니다.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|총 읽은 바이트입니다.|
|[CBindStatusCallback::m_pFunc](#m_pfunc)|함수에 대 한 포인터에는 데이터를 사용할 때 호출 됩니다.|
|[CBindStatusCallback::m_pT](#m_pt)|비동기 데이터 전송 요청 하는 개체에 대 한 포인터입니다.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|에 대 한 포인터를 [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) 현재 바인딩 작업에 대 한 인터페이스입니다.|
|[CBindStatusCallback::m_spBinding](#m_spbinding)|에 대 한 포인터를 `IBinding` 현재 바인딩 작업에 대 한 인터페이스입니다.|
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|에 대 한 포인터를 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) 사용할 URL에 대 한 인터페이스입니다.|
|[CBindStatusCallback::m_spStream](#m_spstream)|에 대 한 포인터를 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 데이터 전송에 대 한 인터페이스입니다.|

## <a name="remarks"></a>설명

`CBindStatusCallback` 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다. `IBindStatusCallback` 비동기 데이터 전송에서 알림을 받을 수 있도록 응용 프로그램에 의해 구현 되어야 합니다. 시스템에서 제공 하는 비동기 모니커를 사용 하 여 `IBindStatusCallback` 비동기 데이터에 대 한 정보를 수신 하는 메서드를 개체에서 전송 합니다.

일반적으로 `CBindStatusCallback` 개체가 특정 바인딩 작업을 사용 하 여 연결 합니다. 예를 들어, 합니다 [비동기](../../overview/visual-cpp-samples.md) 샘플에서는 URL 속성을 설정할 때 만듭니다를 `CBindStatusCallback` 개체에 대 한 호출에서 `Download`:

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

콜백 함수를 사용 하 여 비동기 모니커 `OnData` 데이터가 있는 경우 응용 프로그램을 호출 합니다. 비동기 모니커 시스템에서 제공 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="cbindstatuscallback"></a>  CBindStatusCallback::CBindStatusCallback

생성자입니다.

```
CBindStatusCallback();
```

### <a name="remarks"></a>설명

비동기 데이터 전송에 관한 알림을 받을 개체를 만듭니다. 일반적으로 하나의 개체는 각 바인딩 작업에 대해 생성 됩니다.

또한 생성자 [m_pT](#m_pt) 하 고 [m_pFunc](#m_pfunc) NULL로 합니다.

##  <a name="dtor"></a>  CBindStatusCallback::~CBindStatusCallback

소멸자입니다.

```
~CBindStatusCallback();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="download"></a>  CBindStatusCallback::Download

만듭니다는 `CBindStatusCallback` 개체와 호출 `StartAsyncDownload` 지정된 된 URL에서 데이터를 비동기적으로 다운로드를 시작 합니다.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>매개 변수

*pT*<br/>
[in] 비동기 데이터 전송 요청 하는 개체에 대 한 포인터입니다. `CBindStatusCallback` 개체는이 개체의이 클래스에 템플릿 화 됩니다.

*pFunc*<br/>
[in] 읽을 수 있는 데이터를 수신 하는 함수에 대 한 포인터입니다. 함수 형식의 개체의 클래스의 멤버인 `T`합니다. 참조 [StartAsyncDownload](#startasyncdownload) 구문 및 예제입니다.

*bstrURL*<br/>
[in] 데이터를 가져올 URL입니다. 모든 유효한 URL 또는 파일 이름일 수 있습니다. NULL일 수 없습니다. 예를 들어:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[in] `IUnknown` 컨테이너입니다. 기본적으로 NULL입니다.

*bRelative*<br/>
[in] 상대 또는 절대 URL이 있는지 여부를 나타내는 플래그입니다. 절대 URL 즉 기본적으로 FALSE가입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

통해 개체에 전송 된 데이터를 사용할 때마다 `OnDataAvailable`합니다. `OnDataAvailable` 데이터를 읽고에서 가리키는 함수 호출 *pFunc* (예: 데이터를 저장 하거나 화면에 인쇄).

##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo

모니커에 바인딩하는 방법을 설명 하기 위해 호출 됩니다.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>매개 변수

*pgrfBSCF*<br/>
[out] 바인딩 작업이 발생 해야 하는 방법을 나타내는 BINDF 열거형 값에 대 한 포인터입니다. 기본적으로 다음 열거형 값으로 설정 합니다.

BINDF_ASYNCHRONOUS 비동기 다운로드 합니다.

BINDF_ASYNCSTORAGE `OnDataAvailable` 데이터 아직 사용할 수 없을 때 데이터를 사용할 때까지 차단 하는 대신 E_PENDING을 반환 합니다.

BINDF_GETNEWESTVERSION 바인딩 작업 데이터의 최신 버전을 검색 해야 합니다.

디스크 캐시에서 데이터를 검색 하는 BINDF_NOWRITECACHE 바인딩 작업을 저장 하지 마십시오.

*pbindinfo*<br/>
[out에서] 에 대 한 포인터를 `BINDINFO` 구조 개체 바인딩 되려면 하려고 하는 방법에 대 한 자세한 정보를 제공 합니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

기본 구현은 바인딩을 비동기적 데이터 푸시 모델을 사용 하도록 설정 합니다. 데이터 푸시 모델에서는 모니커 비동기 바인딩 작업을 구동 하 고 지속적으로 새 데이터를 사용할 때마다 클라이언트를에 알립니다.

##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority

비동기 모니커 바인딩 작업의 우선 순위를 가져오려고에서 호출 됩니다.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>매개 변수

*pnPriority*<br/>
[out] 주소를 **긴** 성공 하면 우선 순위를 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead

읽을 수 있는 바이트 수를 저장할 수 있습니다.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>설명

0으로 초기화 `StartAsyncDownload`합니다.

##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead

비동기 데이터 전송에 바이트의 누적 합계가 읽습니다.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>설명

증가 될 때마다 `OnDataAvailable` 실제로 읽는 바이트 수에 의해 호출 됩니다. 0으로 초기화 `StartAsyncDownload`합니다.

##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc

함수에서 가리키는 `m_pFunc` 호출한 `OnDataAvailable` (예: 데이터를 저장 하거나 화면에 인쇄) 사용 가능한 데이터를 읽고 나면 합니다.

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>설명

가리키는 함수 `m_pFunc` 개체의 클래스의 멤버 이며에 다음 구문이 있습니다.

```
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

##  <a name="m_pt"></a>  CBindStatusCallback::m_pT

비동기 데이터 전송 요청 하는 개체에 대 한 포인터입니다.

```
T* m_pT;
```

### <a name="remarks"></a>설명

`CBindStatusCallback` 개체는이 개체의이 클래스에 템플릿 화 됩니다.

##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx

에 대 한 포인터를 [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) 바인드 컨텍스트에 (특정 모니커 바인딩 작업에 대 한 정보를 저장 하는 개체)에 대 한 액세스를 제공 하는 인터페이스입니다.

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>설명

초기화 `StartAsyncDownload`합니다.

##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding

에 대 한 포인터를 `IBinding` 현재 바인딩 작업의 인터페이스입니다.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>설명

초기화 `OnStartBinding` 에 출시 하 고 `OnStopBinding`입니다.

##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker

에 대 한 포인터를 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) 사용할 URL에 대 한 인터페이스입니다.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>설명

초기화 `StartAsyncDownload`합니다.

##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream

에 대 한 포인터를 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 현재 바인딩 작업의 인터페이스입니다.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>설명

초기화 `OnDataAvailable` 에서 `STGMEDIUM` BCSF 플래그 BCSF_FIRSTDATANOTIFICATION 이며 BCSF 플래그 BCSF_LASTDATANOTIFICATION 때 해제 하는 경우 구조체입니다.

##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable

비동기 모니커 시스템 제공 호출 `OnDataAvailable` 를 사용할 수 있는 개체에 데이터를 제공 합니다.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>매개 변수

*grfBSCF*<br/>
[in] BSCF 열거형 값입니다. 하나 이상의 중: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION, 또는 BSCF_LASTDATANOTIFICATION 합니다.

*dwSize*<br/>
[in] 바인딩의 사용할 수 있는 데이터의 누적 양 (메가바이트)입니다. 데이터의 양을 관련 되지 않거나 특정 양이 없는 나왔을 있는지를 나타내는 0이 될 수 있습니다.

*pformatetc*<br/>
[in] 에 대 한 포인터를 [FORMATETC](/windows/desktop/com/the-formatetc-structure) 사용 가능한 데이터의 형식을 포함 하는 구조입니다. 형식이 없습니다, 경우에 CF_NULL 수 있습니다.

*pstgmed*<br/>
[in] 에 대 한 포인터를 [STGMEDIUM](/windows/desktop/com/the-stgmedium-structure) 이제 사용 가능한 실제 데이터를 보유 하는 구조입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`OnDataAvailable` 데이터를 읽는 다음 (예: 데이터를 저장 하거나 화면에 인쇄) 개체의 클래스의 메서드를 호출 합니다. 참조 [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) 세부 정보에 대 한 합니다.

##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource

리소스가 부족 한지 때 호출 됩니다.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
예약됨.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable

비동기 모니커 개체 인터페이스 포인터를 응용 프로그램에 전달 하 여 호출 됩니다.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
요청된 된 인터페이스의 인터페이스 식별자입니다. 사용되지 않습니다.

*punk*<br/>
IUnknown 인터페이스 주소입니다. 사용되지 않습니다.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress

데이터 다운로드 프로세스의 진행률을 표시 하기 위해 호출 됩니다.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>매개 변수

*ulProgress*<br/>
부호 없는 정수 (long)입니다. 사용되지 않습니다.

*ulProgressMax*<br/>
부호 없는 정수 (long) 사용 안 함.

*ulStatusCode*<br/>
부호 없는 정수 (long)입니다. 사용되지 않습니다.

*szStatusText*<br/>
문자열 값의 주소입니다. 사용되지 않습니다.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding

데이터 멤버를 설정 [m_spBinding](#m_spbinding) 에 `IBinding` 포인터 *pBinding*합니다.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
나중에 사용하기 위해 예약되어 있습니다.

*pBinding*<br/>
[in] 현재 IBinding 인터페이스의 주소는 작업을 바인딩합니다. 두 일 수 없습니다. 클라이언트는 바인딩 개체에 대 한 참조를 유지 하려면이 포인터에서 AddRef를 호출 해야 합니다.

##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding

릴리스를 `IBinding` 데이터 멤버에 대 한 포인터 [m_spBinding](#m_spbinding)합니다.

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>매개 변수

*hresult*<br/>
바인딩 작업에서 반환 되는 상태 코드입니다.

*szError*<br/>
문자열 값의 주소입니다. 사용되지 않습니다.

### <a name="remarks"></a>설명

바인딩 작업의 끝을 나타내는 시스템 제공 비동기 모니커에서 호출 됩니다.

##  <a name="startasyncdownload"></a>  CBindStatusCallback::StartAsyncDownload

지정된 된 URL에서 데이터를 비동기적으로 다운로드를 시작 합니다.

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>매개 변수

*pT*<br/>
[in] 비동기 데이터 전송 요청 하는 개체에 대 한 포인터입니다. `CBindStatusCallback` 개체는이 개체의이 클래스에 템플릿 화 됩니다.

*pFunc*<br/>
[in] 읽을 데이터를 수신 하는 함수에 대 한 포인터입니다. 함수 형식의 개체의 클래스의 멤버인 `T`합니다. 참조 **주의** 구문 및 예제입니다.

*bstrURL*<br/>
[in] 데이터를 가져올 URL입니다. 모든 유효한 URL 또는 파일 이름일 수 있습니다. NULL일 수 없습니다. 예를 들어:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[in] `IUnknown` 컨테이너입니다. 기본적으로 NULL입니다.

*bRelative*<br/>
[in] 상대 또는 절대 URL이 있는지 여부를 나타내는 플래그입니다. 절대 URL 즉 기본적으로 FALSE가입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

통해 개체에 전송 된 데이터를 사용할 때마다 `OnDataAvailable`합니다. `OnDataAvailable` 데이터를 읽고에서 가리키는 함수 호출 *pFunc* (예: 데이터를 저장 하거나 화면에 인쇄).

가리키는 함수 *pFunc* 개체의 클래스의 멤버 이며에 다음 구문이 있습니다.

```
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

다음 예제에서 (에서 가져온 합니다 [비동기](../../overview/visual-cpp-samples.md) 샘플)를 함수 `OnData` 입력란에 수신된 된 데이터를 씁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

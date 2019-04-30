---
title: ISupportErrorInfoImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: f7e300e30ff0f14b56d2a1bae86b00e090674679
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274767"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl 클래스

이 클래스의 기본 구현을 제공 합니다 [ISupportErrorInfo 인터페이스](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) 는 단일 인터페이스만 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

#### <a name="parameters"></a>매개 변수

*piid*<br/>
지 원하는 인터페이스의 IID에 대 한 포인터 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|인터페이스를 구분 하는지 여부를 나타냅니다 `riid` 지원 합니다 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스입니다.|

## <a name="remarks"></a>설명

합니다 [ISupportErrorInfo 인터페이스](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) 하면 클라이언트에 오류 정보를 반환할 수 있습니다. 사용 하는 개체 `IErrorInfo` 구현 해야 `ISupportErrorInfo`합니다.

클래스 `ISupportErrorInfoImpl` 의 기본 구현을 제공 `ISupportErrorInfo` 는 단일 인터페이스만 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

인터페이스를 구분 하는지 여부를 나타냅니다 `riid` 지원 합니다 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스입니다.

```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>설명

참조 [ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) Windows SDK에에서 있습니다.

##  <a name="getsize"></a>  IThreadPoolConfig::GetSize

풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>매개 변수

*pnNumThreads*<br/>
[out] 성공 하면 풀의 스레드 수를 수신 하는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]

##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout

스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>매개 변수

*pdwMaxWait*<br/>
[out] 성공 하면 스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 수신 하는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="example"></a>예제

참조 [IThreadPoolConfig::GetSize](#getsize)합니다.

##  <a name="setsize"></a>  IThreadPoolConfig::SetSize

풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>매개 변수

*nNumThreads*<br/>
스레드 풀의 요청된 수입니다.

하는 경우 *nNumThreads* 가 음수 이면 절대 값에 곱합니다 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수입니다.

하는 경우 *nNumThreads* 가 0 이면 ATLS_DEFAULT_THREADSPERPROC 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수를 곱한 수 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="example"></a>예제

참조 [IThreadPoolConfig::GetSize](#getsize)합니다.

##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout

스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>매개 변수

*dwMaxWait*<br/>
스레드 풀 스레드 종료를 대기할 시간 (밀리초) 요청 된 최대 시간입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="example"></a>예제

참조 [IThreadPoolConfig::GetSize](#getsize)합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

---
title: IDataObjectImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: 80b5dfacd5f0c8b0deb8455a59d3f71b73a35ba0
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739566"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl 클래스

이 클래스는 Uniform Data Transfer을 지원 하 고 연결을 관리 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 `IDataObjectImpl`파생 된 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|데이터 개체와 advise 싱크 간의 연결을 설정 합니다. 이를 통해 advise 싱크에서 개체의 변경 내용에 대 한 알림을 받을 수 있습니다.|
|[IDataObjectImpl::DUnadvise](#dunadvise)|이전에를 통해 `DAdvise`설정 된 연결을 종료 합니다.|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|현재 advise 연결을 반복 하는 열거자를 만듭니다.|
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|데이터 개체에서 지 원하는 구조체를 `FORMATETC` 반복 하는 열거자를 만듭니다. ATL 구현은 E_NOTIMPL을 반환 합니다.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|각 advise 싱크로 변경 알림을 다시 보냅니다.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|논리적으로 동일한 `FORMATETC` 구조를 검색 하 여 더 복잡 한 구조를 가져옵니다. ATL 구현은 E_NOTIMPL을 반환 합니다.|
|[IDataObjectImpl::GetData](#getdata)|데이터 개체에서 클라이언트로 데이터를 전송 합니다. 데이터는 `FORMATETC` 구조로 설명 되며 구조를 `STGMEDIUM` 통해 전송 됩니다.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|와 유사 합니다. 단 `STGMEDIUM` ,클라이언트는구조를할당해야합니다.`GetData` ATL 구현은 E_NOTIMPL을 반환 합니다.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|데이터 개체에서 데이터를 전송 하기 위한 `FORMATETC` 특정 구조를 지원 하는지 여부를 확인 합니다. ATL 구현은 E_NOTIMPL을 반환 합니다.|
|[IDataObjectImpl::SetData](#setdata)|클라이언트에서 데이터 개체로 데이터를 전송 합니다. ATL 구현은 E_NOTIMPL을 반환 합니다.|

## <a name="remarks"></a>설명

[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) 인터페이스는 Uniform Data Transfer을 지 원하는 메서드를 제공 합니다. `IDataObject`[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 및 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 표준 형식 구조를 사용 하 여 데이터를 검색 하 고 저장 합니다.

`IDataObject`는 데이터 변경 알림을 처리 하는 싱크를 알리기 위한 연결도 관리 합니다. 클라이언트에서 데이터 개체의 데이터 변경 알림을 수신 하려면 클라이언트는 advise 싱크 라는 개체에서 [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) 인터페이스를 구현 해야 합니다. 클라이언트는를 호출할 `IDataObject::DAdvise`때 데이터 개체와 advise 싱크 간에 연결이 설정 됩니다.

클래스 `IDataObjectImpl` 는의 `IDataObject` 기본 구현을 제공 하 고 `IUnknown` 디버그 빌드에서 정보를 덤프 장치로 전송 하 여를 구현 합니다.

**관련 문서** Atl [자습서](../../atl/active-template-library-atl-tutorial.md), [atl 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** 없음 ctl. h

##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise

데이터 개체와 advise 싱크 간의 연결을 설정 합니다.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

이를 통해 advise 싱크에서 개체의 변경 내용에 대 한 알림을 받을 수 있습니다.

연결을 종료 하려면 [DUnadvise](#dunadvise)를 호출 합니다.

Windows SDK [IDataObject::D advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) 를 참조 하세요.

##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise

이전에 지정한 연결을 ' d a 3에서 [종료 합니다.](#dadvise)

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>설명

Windows SDK [IDataObject::D unadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) 를 참조 하세요.

##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise

현재 advise 연결을 반복 하는 열거자를 만듭니다.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

Windows SDK [IDataObject:: Enumd advise](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) 를 참조 하세요.

##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc

데이터 개체에서 지 원하는 구조체를 `FORMATETC` 반복 하는 열거자를 만듭니다.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>설명

Windows SDK에서 [IDataObject:: enumformatetc 메서드의](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) 를 참조 하세요.

### <a name="return-value"></a>반환 값

E_NOTIMPL을 반환 합니다.

##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange

현재 관리 중인 각 advise 싱크로 변경 알림을 다시 보냅니다.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc

논리적으로 동일한 `FORMATETC` 구조를 검색 하 여 더 복잡 한 구조를 가져옵니다.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL을 반환 합니다.

### <a name="remarks"></a>설명

Windows SDK에서 [IDataObject:: GetCanonicalFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) 를 참조 하세요.

##  <a name="getdata"></a>  IDataObjectImpl::GetData

데이터 개체에서 클라이언트로 데이터를 전송 합니다.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>설명

*Pformatetcin* 매개 변수는 TYMED_MFPICT의 저장소 매체 유형을 지정 해야 합니다.

Windows SDK [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 를 참조 하세요.

##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere

와 유사 합니다. 단 `STGMEDIUM` ,클라이언트는구조를할당해야합니다.`GetData`

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL을 반환 합니다.

### <a name="remarks"></a>설명

Windows SDK에서 [IDataObject:: GetDataHere](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) 를 참조 하세요.

##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData

데이터 개체에서 데이터를 전송 하기 위한 `FORMATETC` 특정 구조를 지원 하는지 여부를 확인 합니다.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL을 반환 합니다.

### <a name="remarks"></a>설명

Windows SDK [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) 를 참조 하세요.

##  <a name="setdata"></a>  IDataObjectImpl::SetData

클라이언트에서 데이터 개체로 데이터를 전송 합니다.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL을 반환 합니다.

### <a name="remarks"></a>설명

Windows SDK [IDataObject:: SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

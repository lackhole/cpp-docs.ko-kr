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
ms.openlocfilehash: b73cfe83075b9595bc98ca05ab2ec2e1771a038d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275466"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl 클래스

이 클래스는 균일 한 데이터 전송 지원 하 고 연결을 관리 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IDataObjectImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|데이터 개체와 advise 싱크 간의 연결을 설정합니다. 따라서 advise 싱크에 개체의 변경 내용 알림을 받을 수 있습니다.|
|[IDataObjectImpl::DUnadvise](#dunadvise)|연결을 통해 이전에 종료 `DAdvise`합니다.|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|현재 자문 연결을 통해 반복 하는 열거자를 만듭니다.|
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|반복 하는 열거자를 만듭니다는 `FORMATETC` 데이터 개체에 의해 지원 되는 구조입니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|각 advise 싱크 변경 알림을 다시 보냅니다.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|논리적으로 동일한 검색 `FORMATETC` 복잡 하 게 연결 되는 구조입니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IDataObjectImpl::GetData](#getdata)|클라이언트에 데이터 개체에서 데이터를 전송합니다. 데이터에 설명 되어는 `FORMATETC` 구조체와 통해 전송 되는 `STGMEDIUM` 구조입니다.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|비슷합니다 `GetData`클라이언트를 할당 해야 제외 하 고는 `STGMEDIUM` 구조입니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|데이터 개체에 특정 지원 하는지 여부를 결정 `FORMATETC` 구조 데이터를 전송 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IDataObjectImpl::SetData](#setdata)|데이터 개체에는 클라이언트에서 데이터를 전송합니다. ATL 구현 E_NOTIMPL을 반환합니다.|

## <a name="remarks"></a>설명

합니다 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) 인터페이스 단일형 데이터 전송 지원 하기 위해 메서드를 제공 합니다. `IDataObject` 표준 형식 구조를 사용 하 여 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 하 고 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 검색 하 고 데이터를 저장 합니다.

`IDataObject` 또한 싱크 데이터 변경 알림을 처리 하는 것이 좋습니다에 대 한 연결을 관리 합니다. 데이터 개체에서 데이터 변경 알림을 수신 하려면 클라이언트에서 클라이언트 구현 해야 합니다는 [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) advise 싱크 라는 개체에 대 한 인터페이스입니다. 클라이언트가 다음 호출 하면 `IDataObject::DAdvise`, 데이터 개체와 advise 싱크 간의 연결입니다.

클래스 `IDataObjectImpl` 의 기본 구현을 제공 `IDataObject` 구현 및 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise

데이터 개체와 advise 싱크 간의 연결을 설정합니다.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

따라서 advise 싱크에 개체의 변경 내용 알림을 받을 수 있습니다.

연결을 종료 하려면 호출 [DUnadvise](#dunadvise)합니다.

참조 [IDataObject::DAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise) Windows SDK에에서 있습니다.

##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise

연결을 통해 이전에 종료 [DAdvise](#dadvise)합니다.

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>설명

참조 [IDataObject::DUnadvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dunadvise) Windows SDK에에서 있습니다.

##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise

현재 자문 연결을 통해 반복 하는 열거자를 만듭니다.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

참조 [IDataObject::EnumDAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-enumdadvise) Windows SDK에에서 있습니다.

##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc

반복 하는 열거자를 만듭니다는 `FORMATETC` 데이터 개체에 의해 지원 되는 구조입니다.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>설명

참조 [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) Windows SDK에에서 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange

현재 관리 되는 각 advise 싱크 변경 알림을 다시 보냅니다.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc

논리적으로 동일한 검색 `FORMATETC` 복잡 하 게 연결 되는 구조입니다.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IDataObject::GetCanonicalFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) Windows SDK에에서 있습니다.

##  <a name="getdata"></a>  IDataObjectImpl::GetData

클라이언트에 데이터 개체에서 데이터를 전송합니다.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>설명

합니다 *pformatetcIn* 매개 변수는 TYMED_MFPICT의 저장소 매체 형식 지정 해야 합니다.

참조 [있음](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK에에서 있습니다.

##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere

비슷합니다 `GetData`클라이언트를 할당 해야 제외 하 고는 `STGMEDIUM` 구조입니다.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IDataObject::GetDataHere](/windows/desktop/api/objidl/nf-objidl-idataobject-getdatahere) Windows SDK에에서 있습니다.

##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData

데이터 개체에 특정 지원 하는지 여부를 결정 `FORMATETC` 구조 데이터를 전송 합니다.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) Windows SDK에에서 있습니다.

##  <a name="setdata"></a>  IDataObjectImpl::SetData

데이터 개체에는 클라이언트에서 데이터를 전송합니다.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IDataObject::SetData](/windows/desktop/api/objidl/nf-objidl-idataobject-setdata) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

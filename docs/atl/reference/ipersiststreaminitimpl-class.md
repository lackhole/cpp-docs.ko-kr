---
title: IPersistStreamInitImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: b5ab433ed08b150e6c344d65657a910542856e77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197621"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl 클래스

이 클래스는 구현 `IUnknown` 의 기본 구현을 제공 합니다 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IPersistStreamInitImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|개체의 데이터를 저장 하는 데 필요한 스트림의 크기를 검색 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IPersistStreamInitImpl::InitNew](#initnew)|새로 만든된 개체를 초기화합니다.|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|개체의 데이터를 마지막으로 저장 된 이후 변경 되었는지 여부를 확인 합니다.|
|[IPersistStreamInitImpl::Load](#load)|지정 된 스트림에서 개체의 속성을 로드합니다.|
|[IPersistStreamInitImpl::Save](#save)|지정 된 스트림에 개체의 속성을 저장합니다.|

## <a name="remarks"></a>설명

합니다 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스에는 클라이언트가 요청 개체를 로드 하 고 자체 영구 데이터를 단일 스트림으로 저장 하는 데 사용 합니다. 클래스 `IPersistStreamInitImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID

개체의 CLSID를 검색합니다.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>설명

참조 [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK에에서 있습니다.

##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax

개체의 데이터를 저장 하는 데 필요한 스트림의 크기를 검색 합니다.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IPersistStreamInit::GetSizeMax](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) Windows SDK에에서 있습니다.

##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew

새로 만든된 개체를 초기화합니다.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>설명

참조 [IPersistStreamInit::InitNew](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) Windows SDK에에서 있습니다.

##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty

개체의 데이터를 마지막으로 저장 된 이후 변경 되었는지 여부를 확인 합니다.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>설명

참조 [IPersistStreamInit::IsDirty](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) Windows SDK에에서 있습니다.

##  <a name="load"></a>  IPersistStreamInitImpl::Load

지정 된 스트림에서 개체의 속성을 로드합니다.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>설명

ATL 개체의 속성 맵에 사용 하 여이 정보를 검색 합니다.

참조 [IPersistStreamInit::Load](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-load) Windows SDK에에서 있습니다.

##  <a name="save"></a>  IPersistStreamInitImpl::Save

지정 된 스트림에 개체의 속성을 저장합니다.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>설명

ATL 개체의 속성 맵에 사용 하 여이 정보를 저장 합니다.

참조 [IPersistStreamInit::Save](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-save) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[저장소 및 스트림](/windows/desktop/Stg/storages-and-streams)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

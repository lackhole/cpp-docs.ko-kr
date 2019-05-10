---
title: IPersistStorageImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
ms.openlocfilehash: 3239ed22e37ff694c9f399b05e765d63e97e99ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276148"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl 클래스

이 클래스에서 구현 된 [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage) 인터페이스입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IPersistStorageImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IPersistStorageImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|모든 저장소 개체를 해제 하 고 HandsOff 모드 입력 개체에 지시 합니다. ATL 구현은 S_OK를 반환 합니다.|
|[IPersistStorageImpl::InitNew](#initnew)|새 저장소를 초기화합니다.|
|[IPersistStorageImpl::IsDirty](#isdirty)|개체의 데이터를 마지막으로 저장 된 이후 변경 되었는지 여부를 확인 합니다.|
|[IPersistStorageImpl::Load](#load)|지정한 저장소에서 개체의 속성을 로드합니다.|
|[IPersistStorageImpl::Save](#save)|지정 된 저장소 개체의 속성을 저장합니다.|
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|해당 저장소 개체에 쓸 수 있는 표준 모드를 반환할 수 있는 개체를 알립니다. ATL 구현은 S_OK를 반환 합니다.|

## <a name="remarks"></a>설명

`IPersistStorageImpl` 구현 된 [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage) 개체 부하 클라이언트가 요청을 하는 데 사용 하는 인터페이스 및 저장소를 사용 하 여 영구 데이터를 저장 합니다.

이 클래스의 구현 클래스에 필요 `T` 를 구현 하기 위해 합니다 `IPersistStreamInit` 인터페이스를 통해 사용할 수 있는 `QueryInterface`합니다. 클래스 즉, 일반적으로 `T` 에서 파생 되어야 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)에 대 한 진입점을 제공 `IPersistStreamInit` 에 [COM 맵에](com-map-macros.md)를 사용 하 여를 [속성 맵에](property-map-macros.md) 클래스의 영구 데이터를 설명 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID

개체의 CLSID를 검색합니다.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>설명

참조 [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK에에서 있습니다.

##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage

모든 저장소 개체를 해제 하 고 HandsOff 모드 입력 개체에 지시 합니다.

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IPersistStorage::HandsOffStorage](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) Windows SDK에에서 있습니다.

##  <a name="initnew"></a>  IPersistStorageImpl::InitNew

새 저장소를 초기화합니다.

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>설명

ATL 구현에 위임 합니다 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스입니다.

참조 [IPersistStorage:InitNew](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-initnew) Windows SDK에에서 있습니다.

##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty

개체의 데이터를 마지막으로 저장 된 이후 변경 되었는지 여부를 확인 합니다.

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>설명

ATL 구현에 위임 합니다 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스입니다.

참조 [IPersistStorage:IsDirty](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-isdirty) Windows SDK에에서 있습니다.

##  <a name="load"></a>  IPersistStorageImpl::Load

지정한 저장소에서 개체의 속성을 로드합니다.

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>설명

ATL 구현에 위임 합니다 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스입니다. `Load` "콘텐츠" 라는 스트림이 사용 하 여 개체의 데이터를 검색 합니다. 합니다 [저장할](#save) 메서드는 원래이 스트림을 만듭니다.

참조 [IPersistStorage:Load](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-load) Windows SDK에에서 있습니다.

##  <a name="save"></a>  IPersistStorageImpl::Save

지정 된 저장소 개체의 속성을 저장합니다.

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>설명

ATL 구현에 위임 합니다 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스입니다. 때 `Save` 처음 지정한 저장소에서 "콘텐츠" 라는 스트림이 생성 호출입니다. 이 스트림에 대 한 이후 호출에 사용 됩니다 `Save` 호출 [부하](#load)합니다.

참조 [IPersistStorage:Save](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-save) Windows SDK에에서 있습니다.

##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted

해당 저장소 개체에 쓸 수 있는 표준 모드를 반환할 수 있는 개체를 알립니다.

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IPersistStorage:SaveCompleted](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[저장소 및 스트림](/windows/desktop/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl 클래스](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl 클래스](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

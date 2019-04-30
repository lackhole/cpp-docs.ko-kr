---
title: ISessionPropertiesImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
ms.openlocfilehash: ed8b7a271bc6ac234fc9276d6c88d26848da24f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390687"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl 클래스

구현을 제공 합니다 [ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties, 
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `ISessionPropertiesImpl`합니다.

*PropClass*<br/>
기본적으로 사용자 정의 가능한 속성 클래스 *T*합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[GetProperties](#getproperties)|현재 세션에 설정 된 세션 속성 그룹의 속성 목록을 반환 합니다.|
|[SetProperties](#setproperties)|세션 속성 그룹의 속성을 설정합니다.|

## <a name="remarks"></a>설명

세션에서 필수 인터페이스입니다. 이 클래스는 정의 된 정적 함수를 호출 하 여 세션 속성을 구현 합니다 [속성 집합 맵](../../data/oledb/begin-propset-map.md)합니다. 세션 클래스의 속성 집합 지도 지정 해야 합니다.

## <a name="getproperties"></a> ISessionPropertiesImpl::GetProperties

속성의 목록을 반환 합니다 `DBPROPSET_SESSION` 현재 세션에 설정 된 속성 그룹입니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>매개 변수

참조 [ISessionProperties::GetProperties](/previous-versions/windows/desktop/ms723643(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="setproperties"></a> ISessionPropertiesImpl::SetProperties

속성을 설정 합니다 `DBPROPSET_SESSION` 속성 그룹입니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>매개 변수

참조 [ISessionProperties::SetProperties](/previous-versions/windows/desktop/ms714405(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
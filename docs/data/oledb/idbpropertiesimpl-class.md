---
title: IDBPropertiesImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: 807cdf55a5a2fa6e0cc063c22b1685d8156c41a5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031341"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl 클래스

에 대 한 구현을 제공 합니다 `IDBProperties` 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IDBPropertiesImpl`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[GetProperties](#getproperties)|데이터 원본 개체의 초기화 속성 그룹에 현재 설정 된 속성의 값에 현재 설정 되어 있는 데이터 원본과 데이터 원본 정보를 초기화 속성 그룹의 속성 값을 반환 합니다 열거자입니다.|
|[GetPropertyInfo](#getpropertyinfo)|공급자가 지 원하는 모든 속성에 대 한 정보를 반환 합니다.|
|[SetProperties](#setproperties)|열거자에 대 한 데이터 원본 개체에 대 한 데이터 원본 및 초기화 속성 그룹 또는 초기화 속성 그룹의 속성을 설정합니다.|

## <a name="remarks"></a>설명

[IDBProperties](/previous-versions/windows/desktop/ms719607(v=vs.85)) 는 데이터 원본 개체에 대 한 필수 인터페이스 및 열거자에 대 한 선택적 인터페이스입니다. 그러나 열거자를 노출 하는 경우 [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85))를 노출 해야 `IDBProperties`합니다. `IDBPropertiesImpl` 구현 `IDBProperties` 정의 된 정적 함수를 사용 하 여 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)합니다.

## <a name="getproperties"></a> IDBPropertiesImpl::GetProperties

데이터 원본 개체의 초기화 속성 그룹에 현재 설정 된 속성의 값에 현재 설정 되어 있는 데이터 원본과 데이터 원본 정보를 초기화 속성 그룹의 속성 값을 반환 합니다 열거자입니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>매개 변수

참조 [idbproperties:: Getproperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 `IDBProperties::GetProperties`:

|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|
|*pcProperties*|*pcPropertySets*|
|*prgProperties*|*prgPropertySets*|

### <a name="remarks"></a>설명

이 메서드는 DBPROPSET_DATASOURCE DBPROPSET_DATASOURCEINFO, 속성의 값을 반환 공급자가 초기화 하는 경우 데이터 원본 개체의 현재 설정 되어 있는 DBPROPSET_DBINIT 속성 그룹입니다. 공급자 초기화 되지 않은 경우에 DBPROPSET_DBINIT 그룹 속성만 반환 합니다.

## <a name="getpropertyinfo"></a> IDBPropertiesImpl::GetPropertyInfo

데이터 원본에서 지 원하는 속성 정보를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcPropertyInfoSets,
   DBPROPINFOSET ** prgPropertyInfoSets,
   OLECHAR ** ppDescBuffer);
```

#### <a name="parameters"></a>매개 변수

참조 [idbproperties:: Getpropertyinfo](/previous-versions/windows/desktop/ms718175(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 `IDBProperties::GetPropertyInfo`:

|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|

### <a name="remarks"></a>설명

사용 하 여 [idbinitializeimpl:: M_pcutlpropinfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) 이 기능을 구현 합니다.

## <a name="setproperties"></a> IDBPropertiesImpl::SetProperties

열거자에 대 한 데이터 원본 개체에 대 한 데이터 원본 및 초기화 속성 그룹 또는 초기화 속성 그룹의 속성을 설정합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>매개 변수

참조 [idbproperties:: Setproperties](/previous-versions/windows/desktop/ms723049(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

이 메서드는 DBPROPSET_DATASOURCE DBPROPSET_DATASOURCEINFO에 속성의 값을 설정 공급자가 초기화 하는 경우 데이터 원본 개체에 대 한 DBPROPSET_DBINIT 속성 그룹입니다. 공급자 초기화 되지 않은 경우에 DBPROPSET_DBINIT 그룹 속성만 설정 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
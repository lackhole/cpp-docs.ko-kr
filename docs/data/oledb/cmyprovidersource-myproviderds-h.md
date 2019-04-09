---
title: CCustomSource (CustomDS.H)
ms.date: 10/22/2018
f1_keywords:
- myproviderds.h
- cmyprovidersource
- customds.h
- ccustomsource
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
- CCustomSource class in CustomDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
ms.openlocfilehash: 296e7848b1d756fe0aba6156be2501db45bb092b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028602"
---
# <a name="ccustomsource-customdsh"></a>CCustomSource (CustomDS.h)

공급자 클래스는 다중 상속을 사용 합니다. 다음 코드는 데이터 원본 개체의 상속 체인을 보여 줍니다.

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

모든 COM 구성 요소에서 파생 `CComObjectRootEx` 고 `CComCoClass`입니다. `CComObjectRootEx` 모든 구현 된 `IUnknown` 인터페이스입니다. 스레딩 모델을 처리할 수 있습니다. `CComCoClass` 필요한 모든 오류 지원을 처리 합니다. 클라이언트에 자세한 오류 정보를 전송 하려는 경우 일부의 오류가 Api 사용할 수 있습니다에 `CComCoClass`입니다.

데이터 원본 개체는 또한 여러 'Impl' 클래스에서 상속 됩니다. 각 클래스는 인터페이스에 대 한 구현을 제공합니다. 데이터 원본 개체를 `IPersist`, `IDBProperties`를 `IDBInitialize`, 및 `IDBCreateSession` 인터페이스입니다. 각 인터페이스 OLE DB 데이터 원본 개체를 구현 하려면 필요 합니다. 상속 하거나 이러한 'Impl' 클래스 중 하나에서 상속 하지 않도록 하 여 특정 기능을 지원 하지 또는 지원 하도록 선택할 수 있습니다. 지원 하려는 경우는 `IDBDataSourceAdmin` 에서 상속 하는 인터페이스는 `IDBDataSourceAdminImpl` 필요한 기능을 활용 하려면 클래스입니다.

## <a name="com-map"></a>COM 맵

클라이언트가 호출할 때마다 `QueryInterface` 데이터 원본에서 인터페이스의 경우 다음 COM 맵을 통해 이동 합니다.

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource : 
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

모든 COM 구성 요소에서 파생 `CComObjectRootEx` 고 `CComCoClass`입니다. `CComObjectRootEx` 모든 구현 된 `IUnknown` 인터페이스입니다. 스레딩 모델을 처리할 수 있습니다. `CComCoClass` 필요한 모든 오류 지원을 처리 합니다. 클라이언트에 자세한 오류 정보를 전송 하려는 경우 일부의 오류가 Api 사용할 수 있습니다에 `CComCoClass`입니다.

데이터 원본 개체는 또한 여러 'Impl' 클래스에서 상속 됩니다. 각 클래스는 인터페이스에 대 한 구현을 제공합니다. 데이터 원본 개체를 `IPersist`, `IDBProperties`를 `IDBInitialize`, 및 `IDBCreateSession` 인터페이스입니다. 각 인터페이스 OLE DB 데이터 원본 개체를 구현 하려면 필요 합니다. 상속 하거나 이러한 'Impl' 클래스 중 하나에서 상속 하지 않도록 하 여 특정 기능을 지원 하지 또는 지원 하도록 선택할 수 있습니다. 지원 하려는 경우는 `IDBDataSourceAdmin` 에서 상속 하는 인터페이스는 `IDBDataSourceAdminImpl` 필요한 기능을 활용 하려면 클래스입니다.

## <a name="com-map"></a>COM 맵

클라이언트가 호출할 때마다 `QueryInterface` 데이터 원본에서 인터페이스의 경우 다음 COM 맵을 통해 이동 합니다.

```cpp
BEGIN_COM_MAP(CCustomSource)
   COM_INTERFACE_ENTRY(IDBCreateSession)
   COM_INTERFACE_ENTRY(IDBInitialize)
   COM_INTERFACE_ENTRY(IDBProperties)
   COM_INTERFACE_ENTRY(IPersist)
   COM_INTERFACE_ENTRY(IInternalConnection)
END_COM_MAP()
```

COM_INTERFACE_ENTRY 매크로 ATL에서 고 구현의 `QueryInterface` 에서 `CComObjectRootEx` 적절 한 인터페이스를 반환 합니다.

## <a name="property-map"></a>속성 맵

속성 맵 공급자에 의해 할당 된 모든 속성을 지정 합니다.

```cpp
BEGIN_PROPSET_MAP(CCustomSource)
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)
      PROPERTY_INFO_ENTRY(CATALOGTERM)
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)
      PROPERTY_INFO_ENTRY(DATASOURCENAME)
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)
      PROPERTY_INFO_ENTRY(DBMSNAME)
      PROPERTY_INFO_ENTRY(DBMSVER)
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)
      PROPERTY_INFO_ENTRY(GROUPBY)
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)
      PROPERTY_INFO_ENTRY(MAXROWSIZE)
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)
      PROPERTY_INFO_ENTRY(NULLCOLLATION)
      PROPERTY_INFO_ENTRY(OLEOBJECTS)
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)
      PROPERTY_INFO_ENTRY(PROCEDURETERM)
      PROPERTY_INFO_ENTRY(PROVIDERNAME)
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)
      PROPERTY_INFO_ENTRY(PROVIDERVER)
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)
      PROPERTY_INFO_ENTRY(SCHEMATERM)
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)
      PROPERTY_INFO_ENTRY(SUBQUERIES)
      PROPERTY_INFO_ENTRY(TABLETERM)
      PROPERTY_INFO_ENTRY(USERNAME)
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)
      PROPERTY_INFO_ENTRY(AUTH_USERID)
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)
      PROPERTY_INFO_ENTRY(INIT_HWND)
      PROPERTY_INFO_ENTRY(INIT_LCID)
      PROPERTY_INFO_ENTRY(INIT_LOCATION)
      PROPERTY_INFO_ENTRY(INIT_MODE)
      PROPERTY_INFO_ENTRY(INIT_PROMPT)
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)
   END_PROPERTY_SET(DBPROPSET_DBINIT)
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)
   CHAIN_PROPERTY_SET(CCustomSession)
END_PROPSET_MAP()
```

OLE db에서 속성 그룹화 됩니다. 데이터 원본 개체에 속성의 두 그룹이:는 DBPROPSET_DATASOURCEINFO에 대 한 설정 및는 DBPROPSET_DBINIT 설정 합니다. DBPROPSET_DATASOURCEINFO 집합 공급자와 해당 데이터 소스에 대 한 속성에 해당합니다. DBPROPSET_DBINIT 집합 초기화 시 사용 되는 속성에 해당 합니다. OLE DB 공급자 템플릿 PROPERTY_SET 매크로 사용 하 여 이러한 집합을 처리 합니다. 매크로 속성의 배열을 포함 하는 블록을 만듭니다. 클라이언트가 호출할 때마다는 `IDBProperties` 인터페이스, 공급자는 속성 맵을 사용 합니다.

사양에 모든 속성을 구현할 필요가 없습니다. 하지만 필요한 속성을 지원 해야, 자세한 내용은 0 수준 규칙 사양을 참조 하십시오. 속성을 지원 하지 않으려는 경우에 map에서 제거할 수 있습니다. 속성을 지원 하려는 맵에 PROPERTY_INFO_ENTRY 매크로 사용 하 여 추가 합니다. 에 해당 하는 매크로 `UPROPINFO` 다음 코드와 같이 구조체:

```cpp
struct UPROPINFO
{
   DBPROPID    dwPropId;
   ULONG       ulIDS;
   VARTYPE     VarType;
   DBPROPFLAGS dwFlags;
   union
   {
      DWORD dwVal;
      LPOLESTR szVal;
   };
   DBPROPOPTIONS dwOption;
};
```

구조의 각 요소는 속성을 처리 하는 정보를 나타냅니다. 포함 된 `DBPROPID` 속성에 대 한 GUID 및 ID를 확인 하려면. 또한 형식 및 속성의 값을 결정 하는 항목을 포함 합니다.

(참고 소비자가 언제 든 지 쓰기 가능한 속성의 값을 변경할 수는) 속성의 기본값을 변경 하려는 경우 PROPERTY_INFO_ENTRY_VALUE 또는 PROPERTY_INFO_ENTRY_EX 매크로 사용할 수 있습니다. 이러한 매크로 사용 하면 해당 속성에 대 한 값을 지정할 수 있습니다. PROPERTY_INFO_ENTRY_VALUE 매크로 값을 변경할 수 있는 단축 표기법입니다. PROPERTY_INFO_ENTRY_VALUE 매크로 PROPERTY_INFO_ENTRY_EX 매크로 호출 합니다. 이 매크로 사용 하면 추가 하거나 모든 특성을 변경 하는 `UPROPINFO` 구조입니다.

고유한 속성 집합을 정의 하려는 경우는 추가 BEGIN_PROPSET_MAP/END_PROPSET_MAP 조합 하 여 추가할 수 있습니다. 속성 집합의 GUID를 정의 하 고 사용자 고유의 속성을 정의 합니다. 공급자별 속성에 있는 경우 기존 계정을 사용 하는 대신 설정 된 새 속성을 추가 합니다. 이렇게 하면 OLE DB의 이후 버전에서 문제가 없습니다.

## <a name="user-defined-property-sets"></a>사용자 정의 속성 집합

Visual c + + 사용자 정의 속성 집합을 지원합니다. 재정의할 필요가 `GetProperties` 또는 `GetPropertyInfo`합니다. 대신 템플릿을 모든 사용자 정의 속성 집합을 검색 및 적절 한 개체에 추가 합니다.

초기화 시 사용할 수 있어야 하는 사용자 정의 속성 집합이 있는 경우 (소비자를 호출 하기 전에, `IDBInitialize::Initialize`), BEGIN_PROPERTY_SET_EX 매크로 함께 UPROPSET_USERINIT 플래그를 사용 하 여이 지정할 수 있습니다. 속성 집합 (OLE DB 사양에 필요) 하는 대로 작동 하도록이 데이터 원본 개체에 있어야 합니다. 예를 들어:

```cpp
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)
```

## <a name="see-also"></a>참고자료

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)<br/>

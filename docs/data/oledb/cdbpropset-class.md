---
title: CDBPropSet 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
- CDBPropSet.operator=
- ATL::CDBPropSet::operator=
- ATL.CDBPropSet.operator=
- CDBPropSet::operator=
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
helpviewer_keywords:
- CDBPropSet class
- AddProperty method
- CDBPropSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
- AddProperty method
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
ms.openlocfilehash: b58c0262d361ede37bc3db68784177ec4c29f3a4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034250"
---
# <a name="cdbpropset-class"></a>CDBPropSet 클래스

상속 되는 `DBPROPSET` 구조체 및 키 필드를 초기화 하는 생성자를 추가 `AddProperty` 메서드에 액세스 합니다.

## <a name="syntax"></a>구문

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddProperty](#addproperty)|속성 집합에는 속성을 추가합니다.|
|[CDBPropSet](#cdbpropset)|생성자입니다.|
|[SetGUID](#setguid)|집합의 `guidPropertySet` 필드는 `DBPROPSET` 구조입니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](#op_equal)|하나의 속성이 다른 설정의 콘텐츠를 할당 합니다.|

## <a name="remarks"></a>설명

OLE DB 공급자와 소비자가 사용 하 여 `DBPROPSET` 배열을 전달 하는 구조 `DBPROP` 구조입니다. 각 `DBPROP` 구조 설정할 수 있는 단일 속성을 나타냅니다.

## <a name="addproperty"></a> CDBPropSet::AddProperty

속성 집합에는 속성을 추가합니다.

### <a name="syntax"></a>구문

```cpp
bool AddProperty(DWORD dwPropertyID,
   constVARIANT& var,
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();
```

#### <a name="parameters"></a>매개 변수

*dwPropertyID*<br/>
[in] 추가할 속성의 ID입니다. 초기화 하는 데 사용 합니다 `dwPropertyID` 의 `DBPROP` 구조 속성 집합에 추가 합니다.

*var*<br/>
[in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 variant를 `DBPROP` 구조 속성 집합에 추가 합니다.

*szValue*<br/>
[in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 문자열을 `DBPROP` 구조 속성 집합에 추가 합니다.

*bValue*<br/>
[in] A `BYTE` 또는 부울 값에 대 한 속성 값을 초기화 하는 데는 `DBPROP` 구조 속성 집합에 추가 합니다.

*nValue*<br/>
[in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 정수 값을 `DBPROP` 구조 속성 집합에 추가 합니다.

*fltValue*<br/>
[in] 부동 소수점 값에 대 한 속성 값을 초기화 하는 데는 `DBPROP` 구조 속성 집합에 추가 합니다.

*dblValue*<br/>
[in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 배정밀도 부동 소수점 값을 `DBPROP` 구조 속성 집합에 추가 합니다.

*cyValue*<br/>
[in] CY 통화 값에 대 한 속성 값을 초기화 하는 데는 `DBPROP` 구조 속성 집합에 추가 합니다.

### <a name="return-value"></a>반환 값

**true** 경우 속성이 추가 되었습니다. 그렇지 않으면 **false**합니다.

## <a name="cdbpropset"></a> CDBPropSet::CDBPropSet

생성자입니다. 초기화 합니다 `rgProperties`, `cProperties`, 및 `guidPropertySet` 의 필드를 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조입니다.

### <a name="syntax"></a>구문

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>매개 변수

*guid*<br/>
[in] GUID를 초기화 하는 데는 `guidPropertySet` 필드입니다.

*propset*<br/>
[in] 복사 생성을 위한 다른 `CDBPropSet` 개체입니다.

## <a name="setguid"></a> CDBPropSet::SetGUID

집합의 `guidPropertySet` 필드에 `DBPROPSET` 구조입니다.

### <a name="syntax"></a>구문

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>매개 변수

*guid*<br/>
[in] 설정 하는 데 GUID를 `guidPropertySet` 필드를 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조입니다.

### <a name="remarks"></a>설명

이 필드에서 설정할 수는 [생성자](../../data/oledb/cdbpropset-cdbpropset.md) 도 합니다.

## <a name="op_equal"></a> CDBPropSet::operator =

콘텐츠를 다른 속성 집합에 두 속성을 할당 합니다.

### <a name="syntax"></a>구문

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet 클래스](../../data/oledb/cdbpropidset-class.md)<br/>
[DBPROPSET 구조](/previous-versions/windows/desktop/ms714367(v=vs.85))
[DBPROP 구조](/previous-versions/windows/desktop/ms717970(v=vs.85))
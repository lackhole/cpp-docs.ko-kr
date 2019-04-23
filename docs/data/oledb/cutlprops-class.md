---
title: CUtlProps 클래스
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- CUtlProps
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 3f1af90bcf454a3651dd8de65bbee7cb6b5960ca
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037622"
---
# <a name="cutlprops-class"></a>CUtlProps 클래스

다양 한 OLE DB 속성 인터페이스에 대 한 속성을 구현 (예를 들어 `IDBProperties`, `IDBProperties`, 및 `IRowsetInfo`).

## <a name="syntax"></a>구문

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>매개 변수

*T*<br/>
포함 하는 클래스는 `BEGIN_PROPSET_MAP`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[GetPropValue](#getpropvalue)|속성 집합에서 속성을 가져옵니다.|
|[IsValidValue](#isvalidvalue)|값 속성을 설정 하기 전에 유효성을 검사 하는 데 사용 합니다.|
|[OnInterfaceRequested](#oninterfacerequested)|소비자 개체 생성 인터페이스에서 메서드를 호출할 때 선택적 인터페이스에 대 한 요청을 처리 합니다.|
|[OnPropertyChanged](#onpropertychanged)|연결 된 속성을 처리 하는 속성을 설정한 후 호출 됩니다.|
|[SetPropValue](#setpropvalue)|속성 집합의 속성을 설정합니다.|

## <a name="remarks"></a>설명

대부분의이 클래스는 구현 세부 정보입니다.

`CUtlProps` 내부적으로 속성을 설정 하기 위한 두 명의 멤버가 있습니다. [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) 하 고 [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)합니다.

속성 집합 구조에 사용 되는 매크로에 대 한 자세한 내용은 참조 하세요. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) 하 고 [END_PROPSET_MAP](../../data/oledb/end-propset-map.md)합니다.

## <a name="getpropvalue"></a> CUtlProps::GetPropValue

속성 집합에서 속성을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>매개 변수

*pguidPropSet*<br/>
[in] 속성 집합에 대 한 GUID입니다.

*dwPropId*<br/>
[in] 속성 인덱스입니다.

*pvValue*<br/>
[out] 새 속성 값을 포함 하는 variant에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

`Failure` 오류에 성공 하면 S_OK입니다.

## <a name="isvalidvalue"></a> CUtlProps::IsValidValue

값 속성을 설정 하기 전에 유효성을 검사 하는 데 사용 합니다.

### <a name="syntax"></a>구문

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>매개 변수

*iCurSet*<br/>
속성 집합 배열로; 인덱스 하나의 속성 집합이 있는 경우 0입니다.

*pDBProp*<br/>
속성 ID와 새 값을 [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) 구조입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다. 기본 반환 값에는 S_OK입니다.

### <a name="remarks"></a>설명

모든 유효성 검사 루틴을 사용 하 여 속성을 설정 하려고 하는 값에서 실행 하려는 경우이 함수를 재정의 해야 합니다. 예를 들어, 유효한 값을 결정 하려면 암호 테이블에 대해 DBPROP_AUTH_PASSWORD를 확인할 수 있습니다.

## <a name="oninterfacerequested"></a> CUtlProps::OnInterfaceRequested

소비자 메서드를 호출할 때 개체 중 하나에서 만들 인터페이스는 선택적 인터페이스에 대 한 요청을 처리 합니다.

### <a name="syntax"></a>구문

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>매개 변수

*riid*<br/>
[in] 요청된 된 인터페이스에 대 한 IID입니다. 대 한 자세한 내용은 설명을 참조는 *riid* 의 매개 변수 `ICommand::Execute` 에 *OLE DB Programmer's Reference* (에 *MDAC SDK*).

### <a name="remarks"></a>설명

`OnInterfaceRequested` 소비자 메서드를 호출할 때 개체 중 하나에서 만들 인터페이스는 선택적 인터페이스에 대 한 소비자의 요청 처리 (같은 `IDBCreateSession`, `IDBCreateCommand`를 `IOpenRowset`, 또는 `ICommand`). 요청된 된 인터페이스에 대 한 해당 OLE DB 속성을 설정 합니다. 예를 들어 소비자 요청 `IID_IRowsetLocate`, `OnInterfaceRequested` 설정 된 `DBPROP_IRowsetLocate` 인터페이스입니다. 이렇게 행 집합 생성 중 올바른 상태를 유지 관리 합니다.

이 메서드는 소비자를 호출할 때 `IOpenRowset::OpenRowset` 또는 `ICommand::Execute`합니다.

소비자 개체를 엽니다 하는 선택적 인터페이스를 요청 하는 경우 공급자를 variant_true로 해당 인터페이스를 사용 하 여 연결 된 속성을 설정 해야 합니다. 속성별 처리를 허용 하도록 `OnInterfaceRequested` 공급자의 이전에 호출 됩니다 `Execute` 메서드가 호출 됩니다. 기본적으로 `OnInterfaceRequested` 다음 인터페이스를 처리 합니다.

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

다른 인터페이스를 처리 하려는 경우 프로세스 함수에 데이터 원본, 세션, 명령 또는 행 집합 클래스에서이 함수를 재정의 합니다. 재정의 모든 연결 된 속성을 설정도 속성을 설정 하도록 기본 설정 및 가져오기 속성 인터페이스를 통해 이동 해야 합니다 (참조 [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).

## <a name="onpropertychanged"></a> CUtlProps::OnPropertyChanged

연결 된 속성을 처리 하는 속성을 설정한 후 호출 됩니다.

### <a name="syntax"></a>구문

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>매개 변수

*iCurSet*<br/>
속성 집합 배열로; 인덱스 하나의 속성 집합이 있는 경우 0입니다.

*pDBProp*<br/>
속성 ID와 새 값을 [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) 구조입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다. 기본 반환 값에는 S_OK입니다.

### <a name="remarks"></a>설명

책갈피 값을 가진 다른 속성의 값에 따라 다릅니다. 업데이트 등의 연결 된 속성을 처리 하려는 경우이 함수를 재정의 해야 합니다.

### <a name="example"></a>예제

이 함수를 사용자에서 속성 ID를 가져옵니다는 `DBPROP*` 매개 변수입니다. 이제 연결할 속성에 대 한 ID와 비교 하는 것이 같습니다. 속성이 있으면 `SetProperties` 이제 다른 속성과 함께에서 설정 될 속성을 사용 하 여 호출 됩니다. 이 경우 하나를 가져옵니다 합니다 `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, 또는 `DBPROP_ORDEREDBOOKMARKS` 속성을 하나 설정할 수 있습니다는 `DBPROP_BOOKMARKS` 속성입니다.

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="setpropvalue"></a> CUtlProps::SetPropValue

속성 집합의 속성을 설정합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>매개 변수

*pguidPropSet*<br/>
[in] 속성 집합에 대 한 GUID입니다.

*dwPropId*<br/>
[in] 속성 인덱스입니다.

*pvValue*<br/>
[in] 새 속성 값을 포함 하는 variant에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

`Failure` 오류에 성공 하면 S_OK입니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
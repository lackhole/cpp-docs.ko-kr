---
title: CAccessorBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
ms.openlocfilehash: 34c92f9057f2273d57b69bdb42c49a81923c3d2a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034954"
---
# <a name="caccessorbase-class"></a>CAccessorBase 클래스

OLE DB 템플릿의 모든 접근자가이 클래스에서 파생 됩니다. `CAccessorBase` 여러 접근자를 관리 하는 하나의 행 집합을 허용 합니다. 또한 매개 변수 및 출력 열에 대 한 바인딩을 제공합니다.

## <a name="syntax"></a>구문

```cpp
// Replace with syntax
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[닫기](#close)|접근자를 닫습니다.|
|[GetHAccessor](#geth)|접근자 핸들을 검색합니다.|
|[GetNumAccessors](#getnum)|클래스에 의해 생성 되는 접근자의 수를 검색 합니다.|
|[IsAutoAccessor](#isauto)|지정 된 접근자가 자동 있는지 테스트 합니다.|
|[ReleaseAccessors](#release)|접근자를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="close"></a> Caccessorbase:: Close

접근자를 닫습니다.

### <a name="syntax"></a>구문

```cpp
void Close();
```

### <a name="remarks"></a>설명

호출 해야 합니다 [ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md) 첫 번째입니다.

## <a name="geth"></a> CAccessorBase::GetHAccessor

지정된 접근자의 접근자 핸들을 검색합니다.

### <a name="syntax"></a>구문

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>매개 변수

*nAccessor*<br/>
[in] 접근자에 대한 0 오프셋의 수입니다.

### <a name="return-value"></a>반환 값

접근자 핸들입니다.

## <a name="getnum"></a> CAccessorBase::GetNumAccessors

클래스에 의해 생성 되는 접근자의 수를 검색 합니다.

### <a name="syntax"></a>구문

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>반환 값

클래스에 의해 생성 되는 접근자 수입니다.

## <a name="isauto"></a> CAccessorBase::IsAutoAccessor

이동 작업 중 접근자에 대 한 데이터는 자동으로 검색 하는 경우 true를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>매개 변수

*nAccessor*<br/>
[in] 접근자에 대한 0 오프셋의 수입니다.

### <a name="return-value"></a>반환 값

반환 **true** 접근자가 자동 하는 경우. 그렇지 않으면 **false**를 반환합니다.

## <a name="release"></a> CAccessorBase::ReleaseAccessors

클래스에 의해 만들어진 접근자를 해제 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터는 `IUnknown` 접근자 생성 된 COM 개체에 대 한 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

호출할 [caccessorrowset:: Close](../../data/oledb/caccessorrowset-close.md)합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase 클래스](../../data/oledb/caccessorbase-class.md)
---
title: CComSafeArrayBound 클래스
ms.date: 05/06/2019
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: 6d4650273661c0ce40558a37ef02bb2a3ff81809
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221145"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound 클래스

이 클래스는에 대 한 래퍼를 [SAFEARRAYBOUND](/windows/desktop/api/oaidl/ns-oaidl-tagsafearraybound) 구조입니다.

## <a name="syntax"></a>구문

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|생성자입니다.|
|[GetCount](#getcount)|요소 수를 반환 하려면이 메서드를 호출 합니다.|
|[GetLowerBound](#getlowerbound)|하한값을 반환 하려면이 메서드를 호출 합니다.|
|[GetUpperBound](#getupperbound)|상한 값을 반환 하려면이 메서드를 호출 합니다.|
|[SetCount](#setcount)|요소 수를 설정 하려면이 메서드를 호출 합니다.|
|[SetLowerBound](#setlowerbound)|하한값을 설정 하려면이 메서드를 호출 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](#operator_eq)|집합의 `CComSafeArrayBound` 를 새 값입니다.|

## <a name="remarks"></a>설명

이 클래스에 대 한 래퍼인 합니다 `SAFEARRAYBOUND` 사용 되는 구조 [CComSafeArray](../../atl/reference/ccomsafearray-class.md)합니다. 쿼리하고 단일 차원의 상한 및 하 한 범위를 설정 하기 위한 메서드를 제공 하는 `CComSafeArray` 개체 및 포함 된 요소 수입니다. 다차원 `CComSafeArray` 개체의 배열을 사용 하 여 `CComSafeArrayBound` 개체, 각 차원에 대 한 합니다. 따라서 같은 메서드를 사용 하는 경우 [GetCount](#getcount),이 메서드 다차원 배열에서 요소의 총 수를 반환 하지는 알고 있어야 합니다.

**헤더:** atlsafe.h

## <a name="requirements"></a>요구 사항

**헤더:** atlsafe.h

##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound

생성자입니다.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>매개 변수

*ulCount*<br/>
배열의 요소 수입니다.

*lLowerBound*<br/>
하한값에서 배열 번호가 지정 됩니다.

### <a name="remarks"></a>설명

배열에서 액세스 하는 경우는 C++ 프로그램인 것이 좋습니다 하한값은 0으로 정의 합니다. Visual Basic과 같은 다른 언어와 함께 사용 될 경우 다른 하 한 값을 사용 하는 것이 좋습니다 수도 있습니다.

##  <a name="getcount"></a>  CComSafeArrayBound::GetCount

요소 수를 반환 하려면이 메서드를 호출 합니다.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>반환 값

요소 수를 반환합니다.

### <a name="remarks"></a>설명

하는 경우 연결 된 `CComSafeArray` 개체가 나타내는 다차원 배열,이 메서드는 오른쪽에 있는 차원에 있는 요소의 총 수를 반환만 합니다. 사용 하 여 [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) 요소의 총 수를 가져오려고 합니다.

##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound

하한값을 반환 하려면이 메서드를 호출 합니다.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>반환 값

하한값을 반환 합니다 `CComSafeArrayBound` 개체입니다.

##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound

상한 값을 반환 하려면이 메서드를 호출 합니다.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>반환 값

상한을 반환 된 `CComSafeArrayBound` 개체입니다.

### <a name="remarks"></a>설명

상한 값은 요소 및 하한값 값의 수에 따라 달라 집니다. 예를 들어, 하 한은 0 이며 요소 수가 10에 상한 값은 9로 자동으로 설정 됩니다.

##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =

집합의 `CComSafeArrayBound` 를 새 값입니다.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>매개 변수

*bound*<br/>
`CComSafeArrayBound` 개체입니다.

*ulCount*<br/>
요소의 수입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 `CComSafeArrayBound` 개체입니다.

### <a name="remarks"></a>설명

합니다 `CComSafeArrayBound` 기존 사용 하 여 개체를 할당할 수 있습니다 `CComSafeArrayBound`, 또는 기본적으로 한 경우 0으로 설정 된 요소 수를 제공 하 여 합니다.

##  <a name="setcount"></a>  CComSafeArrayBound::SetCount

요소 수를 설정 하려면이 메서드를 호출 합니다.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>매개 변수

*ulCount*<br/>
요소의 수입니다.

### <a name="return-value"></a>반환 값

요소 수를 반환 합니다 `CComSafeArrayBound` 개체입니다.

##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound

하한값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>매개 변수

*lLowerBound*<br/>
하 한.

### <a name="return-value"></a>반환 값

새 하한값을 반환 합니다 `CComSafeArrayBound` 개체입니다.

### <a name="remarks"></a>설명

배열에서 시각적 개체에 액세스할 수 있으면 C++ 프로그램인 것이 좋습니다 하한값은 0으로 정의 합니다. Visual Basic과 같은 다른 언어와 함께 사용 될 경우 다른 하 한 값을 사용 하는 것이 좋습니다 수도 있습니다.

상한 값은 요소 및 하한값 값의 수에 따라 달라 집니다. 예를 들어, 하 한은 0 이며 요소 수가 10에 상한 값은 9로 자동으로 설정 됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

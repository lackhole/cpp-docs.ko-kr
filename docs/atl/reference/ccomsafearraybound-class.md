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
ms.openlocfilehash: bd77c2a788e769c74518d73b45c3c05ff27b3f58
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496905"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound 클래스

이 클래스는 [Safearraybound](/windows/win32/api/oaidl/ns-oaidl-tagsafearraybound) 구조체에 대 한 래퍼입니다.

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
|[GetUpperBound](#getupperbound)|상한을 반환 하려면이 메서드를 호출 합니다.|
|[SetCount](#setcount)|요소 수를 설정 하려면이 메서드를 호출 합니다.|
|[SetLowerBound](#setlowerbound)|하 한을 설정 하려면이 메서드를 호출 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](#operator_eq)|를 새 값으로 설정 합니다. `CComSafeArrayBound`|

## <a name="remarks"></a>설명

이 클래스는 [CComSafeArray](../../atl/reference/ccomsafearray-class.md)에서 사용 하 `SAFEARRAYBOUND` 는 구조체에 대 한 래퍼입니다. `CComSafeArray` 개체의 단일 차원에 대 한 상한 및 하 한 범위와 여기에 포함 된 요소 수를 쿼리하고 설정 하기 위한 메서드를 제공 합니다. 다차원 `CComSafeArray` 개체는 각 차원에 대해 `CComSafeArrayBound` 하나씩 개체 배열을 사용 합니다. 따라서 [Getcount](#getcount)와 같은 메서드를 사용 하는 경우이 메서드는 다차원 배열의 총 요소 수를 반환 하지 않습니다.

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
배열의 번호가 매겨진 하한값입니다.

### <a name="remarks"></a>설명

C++ 프로그램에서 배열을 액세스 하려면 하 한을 0으로 정의 하는 것이 좋습니다. 배열이 다른 언어 (예: Visual Basic)와 함께 사용 될 경우에는 다른 하 한 값을 사용 하는 것이 더 적합할 수 있습니다.

##  <a name="getcount"></a>  CComSafeArrayBound::GetCount

요소 수를 반환 하려면이 메서드를 호출 합니다.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>반환 값

요소 수를 반환 합니다.

### <a name="remarks"></a>설명

연결 `CComSafeArray` 된 개체가 다차원 배열을 나타내는 경우이 메서드는 가장 오른쪽 차원의 총 요소 수만 반환 합니다. [CComSafeArray:: GetCount](../../atl/reference/ccomsafearray-class.md#getcount) 를 사용 하 여 총 요소 수를 가져옵니다.

##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound

하한값을 반환 하려면이 메서드를 호출 합니다.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>반환 값

`CComSafeArrayBound` 개체의 하 한을 반환 합니다.

##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound

상한을 반환 하려면이 메서드를 호출 합니다.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>반환 값

`CComSafeArrayBound` 개체의 상한을 반환 합니다.

### <a name="remarks"></a>설명

상한을 요소 수 및 하 한 값에 따라 다릅니다. 예를 들어 하 한이 0이 고 요소 수가 10 이면 상한이 자동으로 9로 설정 됩니다.

##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =

를 새 값으로 설정 합니다. `CComSafeArrayBound`

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

`CComSafeArrayBound` 개체에 대 한 포인터를 반환 합니다.

### <a name="remarks"></a>설명

개체 `CComSafeArrayBound` 는 기존 `CComSafeArrayBound`을 사용 하 여 할당 하거나 요소 수를 제공 하 여 할당할 수 있습니다 .이 경우에는 기본적으로 하 한이 0으로 설정 됩니다.

##  <a name="setcount"></a>  CComSafeArrayBound::SetCount

요소 수를 설정 하려면이 메서드를 호출 합니다.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>매개 변수

*ulCount*<br/>
요소의 수입니다.

### <a name="return-value"></a>반환 값

`CComSafeArrayBound` 개체의 요소 수를 반환 합니다.

##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound

하 한을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>매개 변수

*lLowerBound*<br/>
하 한입니다.

### <a name="return-value"></a>반환 값

`CComSafeArrayBound` 개체의 새 하 한을 반환 합니다.

### <a name="remarks"></a>설명

시각적 C++ 프로그램에서 배열에 액세스 하는 경우 하 한을 0으로 정의 하는 것이 좋습니다. 배열이 다른 언어 (예: Visual Basic)와 함께 사용 될 경우에는 다른 하 한 값을 사용 하는 것이 더 적합할 수 있습니다.

상한을 요소 수 및 하 한 값에 따라 다릅니다. 예를 들어 하 한이 0이 고 요소 수가 10 이면 상한이 자동으로 9로 설정 됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

---
title: ATL 연산자
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 6f1bd4f88b8d3a37f051a208a887c5264f61955a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260911"
---
# <a name="atl-operators"></a>ATL 연산자

이 섹션에서는 ATL 전역 연산자에 대 한 참조 항목을 포함합니다.

|연산자|설명|
|--------------|-----------------|
|[operator ==](#operator_eq_eq)|두 `CSid` 개체 또는 `SID` 구조체가 같은지 여부.|
|[operator !=](#operator_neq)|두 `CSid` 개체 또는 `SID` 구조체가 다른 지 합니다.|
|[operator <](#operator_lt)|테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조는 보다 작은 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 호환성 표준 라이브러리).|
|[operator >](#operator_gt)|테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조 보다 큽니다. 합니다 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 표준 라이브러리 호환성).|
|[operator <=](#operator_lt__eq)|테스트를 `CSid` 개체 또는 `SID` 보다 작거나 같음 연산자의 좌 변에 있는 구조는 합니다 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 표준 라이브러리 호환성).|
|[operator >=](#operator_gt__eq)|테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조체 보다 크거나 같음 합니다 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 표준 라이브러리 호환성).|

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h 합니다.

##  <a name="operator_eq_eq"></a>  operator ==

비교 `CSid` 개체 또는 `SID` 같은지 (보안 식별자) 구조입니다.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

*rhs*<br/>
두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

### <a name="return-value"></a>반환 값

개체가 같은지 여부를 FALSE 동일 하지 않은 경우 TRUE를 반환 합니다.

##  <a name="operator_neq"></a>  operator !=

비교 `CSid` 개체 또는 `SID` 구조체가 다른 지 (보안 식별자)입니다.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

*rhs*<br/>
두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

### <a name="return-value"></a>반환 값

개체가 없는 경우 같음, 같지 않으면 FALSE입니다. TRUE를 반환 합니다.

##  <a name="operator_lt"></a>  operator <

테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조는 보다 작은 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 호환성 표준 라이브러리).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

*rhs*<br/>
두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

### <a name="return-value"></a>반환 값

경우 TRUE를 반환 합니다.의 주소를 *lhs* 개체의 주소 보다 작습니다 합니다 *rhs* 개체 FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 호환성을 제공 하기 위해 구현 됩니다 C++ 표준 라이브러리 컬렉션 클래스입니다.

##  <a name="operator_gt"></a>  operator >

테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조 보다 큽니다. 합니다 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 표준 라이브러리 호환성).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

*rhs*<br/>
두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

### <a name="return-value"></a>반환 값

경우 TRUE를 반환 합니다.의 주소를 *lhs* 주소 보다 큰를 *rhs*이 고, FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 호환성을 제공 하기 위해 구현 됩니다 C++ 표준 라이브러리 컬렉션 클래스입니다.

##  <a name="operator_lt__eq"></a>  operator <=

테스트를 `CSid` 개체 또는 `SID` 보다 작거나 같음 연산자의 좌 변에 있는 구조는 합니다 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 표준 라이브러리 호환성).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

*rhs*<br/>
두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

### <a name="return-value"></a>반환 값

경우 TRUE를 반환의 주소를 *lhs* 주소 보다 작거나 같으면 합니다 *rhs*이 고, FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 호환성을 제공 하기 위해 구현 됩니다 C++ 표준 라이브러리 컬렉션 클래스입니다.

##  <a name="operator_gt__eq"></a>  operator >=

테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조체 보다 크거나 같음 합니다 `CSid` 개체 또는 `SID` 오른쪽에 있는 구조 (에 대 한 C++ 표준 라이브러리 호환성).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

*rhs*<br/>
두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.

### <a name="return-value"></a>반환 값

경우 TRUE를 반환 합니다.의 주소를 *lhs* 주소의 이상이 되는 *rhs*이 고, FALSE이 고, 그렇지.

### <a name="remarks"></a>설명

이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 호환성을 제공 하기 위해 구현 됩니다 C++ 표준 라이브러리 컬렉션 클래스입니다.

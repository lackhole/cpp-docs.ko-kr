---
title: CFileTimeSpan 클래스
ms.date: 10/18/2018
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: f9bb42ba4c142f671a83dcfa7e99cff940fff047
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491288"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan 클래스

이 클래스는 파일과 연결 된 상대 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CFileTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|`CFileTimeSpan` 개체에서 시간 범위를 검색 하려면이 메서드를 호출 합니다.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|`CFileTimeSpan` 개체의 시간 범위를 설정 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CFileTimeSpan::operator -](#operator_-)|`CFileTimeSpan` 개체에서 빼기를 수행 합니다.|
|[CFileTimeSpan::operator !=](#operator_neq)|두 `CFileTimeSpan` 개체가 다른지 비교합니다.|
|[CFileTimeSpan:: operator +](#operator_add)|`CFileTimeSpan` 개체에 대해 더하기를 수행 합니다.|
|[CFileTimeSpan:: operator + =](#operator_add_eq)|`CFileTimeSpan` 개체에 대해 더하기를 수행 하 고 결과를 현재 개체에 할당 합니다.|
|[CFileTimeSpan::operator &lt;](#operator_lt)|두 `CFileTimeSpan` 개체를 비교 하 여 더 작은를 확인 합니다.|
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|두 `CFileTimeSpan` 개체를 비교 하 여 같은지 또는 더 낮은 지 확인 합니다.|
|[CFileTimeSpan::operator =](#operator_eq)|할당 연산자입니다.|
|[CFileTimeSpan::operator -=](#operator_-_eq)|`CFileTimeSpan` 개체에 대해 빼기를 수행 하 고 결과를 현재 개체에 할당 합니다.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|두 `CFileTimeSpan` 개체가 같은지 비교합니다.|
|[CFileTimeSpan::operator &gt;](#operator_gt)|두 `CFileTimeSpan` 개체를 비교 하 여 더 큰를 확인 합니다.|
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|두 `CFileTimeSpan` 개체를 비교 하 여 같은지 또는 더 큰지 확인 합니다.|

## <a name="remarks"></a>설명

이 클래스는 파일을 만든 시간, 마지막으로 액세스 한 날짜 또는 마지막으로 수정한 날짜와 관련 된 작업을 수행할 때 자주 발생 하는 상대적 기간을 관리 하기 위한 메서드를 제공 합니다 이 클래스의 메서드는 [Cfiletime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md) 개체와 함께 자주 사용 됩니다.

## <a name="example"></a>예제

[Cfiletime:: 밀리초](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:** 고 지 시간. h

##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan

생성자입니다.

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
기존 `CFileTimeSpan` 개체입니다.

*nSpan*<br/>
시간 (밀리초)입니다.

### <a name="remarks"></a>설명

개체 `CFileTimeSpan` 는 기존 `CFileTimeSpan` 개체를 사용 하 여 만들거나 64 비트 값으로 표현 될 수 있습니다. 기본 생성자는 시간 범위를 0으로 설정 합니다.

##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan

`CFileTimeSpan` 개체에서 시간 범위를 검색 하려면이 메서드를 호출 합니다.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>반환 값

시간 범위 (밀리초)를 반환 합니다.

##  <a name="operator_-"></a>  CFileTimeSpan::operator -

`CFileTimeSpan` 개체에서 빼기를 수행 합니다.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

두 시간 `CFileTimeSpan` 범위의 차에 대 한 결과를 나타내는 개체를 반환 합니다.

##  <a name="operator_neq"></a>  CFileTimeSpan::operator !=

두 `CFileTimeSpan` 개체가 다른지 비교합니다.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

비교할 항목이 `CFileTimeSpan` 개체와 같지 않으면 TRUE를 반환 하 고, 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="operator_add"></a>  CFileTimeSpan::operator +

`CFileTimeSpan` 개체에 대해 더하기를 수행 합니다.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

두 시간 `CFileTimeSpan` 범위의 합계를 포함 하는 개체를 반환 합니다.

##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator +=

`CFileTimeSpan` 개체에 대해 더하기를 수행 하 고 결과를 현재 개체에 할당 합니다.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

두 시간 범위의 `CFileTimeSpan` 합계를 포함 하는 업데이트 된 개체를 반환 합니다.

##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;

두 `CFileTimeSpan` 개체를 비교 하 여 더 작은를 확인 합니다.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 두 번째 개체 보다 작은 경우 (즉, 더 짧은 기간을 나타냄) TRUE를 반환 하 고, 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=

두 `CFileTimeSpan` 개체를 비교 하 여 같은지 또는 더 낮은 지 확인 합니다.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 보다 작은 경우 (즉, 더 짧은 기간을 나타냄) TRUE를 반환 하 고, 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="operator_eq"></a>  CFileTimeSpan::operator =

할당 연산자입니다.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 `CFileTimeSpan` 된 개체를 반환 합니다.

##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator -=

`CFileTimeSpan` 개체에 대해 빼기를 수행 하 고 결과를 현재 개체에 할당 합니다.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 `CFileTimeSpan` 된 개체를 반환 합니다.

##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator ==

두 `CFileTimeSpan` 개체가 같은지 비교합니다.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

개체가 같으면 TRUE, 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;

두 `CFileTimeSpan` 개체를 비교 하 여 더 큰를 확인 합니다.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 두 번째 개체 보다 크면 TRUE, 그렇지 않으면 FALSE를 반환 하 고, 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=

두 `CFileTimeSpan` 개체를 비교 하 여 같은지 또는 더 큰지 확인 합니다.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 보다 크거나 (즉, 더 긴 기간을 나타냄), 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan

`CFileTimeSpan` 개체의 시간 범위를 설정 하려면이 메서드를 호출 합니다.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>매개 변수

*nSpan*<br/>
시간 범위의 새 값 (밀리초)입니다.

## <a name="see-also"></a>참고자료

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)

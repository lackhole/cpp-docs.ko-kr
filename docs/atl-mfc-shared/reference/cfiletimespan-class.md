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
ms.openlocfilehash: 001e6ddc78a41e118949e9b750b78609f3ff9e92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235304"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan 클래스

이 클래스는 상대 날짜 및 시간 값을 파일에 연결 된 관리 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CFileTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|시간 범위를 검색 하려면이 메서드는 `CFileTimeSpan` 개체입니다.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|시간 범위를 설정 하려면이 메서드를 호출 합니다 `CFileTimeSpan` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CFileTimeSpan::operator -](#operator_-)|에 대해 빼기를 수행는 `CFileTimeSpan` 개체입니다.|
|[CFileTimeSpan::operator !=](#operator_neq)|두 `CFileTimeSpan` 개체가 다른지 비교합니다.|
|[CFileTimeSpan::operator +](#operator_add)|에 더하기를 수행는 `CFileTimeSpan` 개체입니다.|
|[CFileTimeSpan::operator +=](#operator_add_eq)|에 더하기를 수행는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.|
|[CFileTimeSpan::operator &lt;](#operator_lt)|두 `CFileTimeSpan` 더 작은 값을 결정 하는 개체입니다.|
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|두 `CFileTimeSpan` 같음 또는 더 작은 값을 확인 하는 개체입니다.|
|[CFileTimeSpan::operator =](#operator_eq)|대입 연산자입니다.|
|[CFileTimeSpan::operator -=](#operator_-_eq)|에 대해 빼기를 수행는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|두 `CFileTimeSpan` 개체가 같은지 비교합니다.|
|[CFileTimeSpan::operator &gt;](#operator_gt)|두 `CFileTimeSpan` 더 큰 숫자를 확인 하는 개체입니다.|
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|두 `CFileTimeSpan` 크거나 같은 값을 확인 하는 개체입니다.|

## <a name="remarks"></a>설명

이 클래스는 상대 기간을 관리 하기 위한 메서드 제공 시기와 관련 된 작업을 수행할 때 자주 발생 하는 시간을 파일을, 마지막으로 액세스 만들거나 마지막으로 수정 합니다. 이 클래스의 메서드 함께에서 자주 [CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md) 개체입니다.

## <a name="example"></a>예제

예를 참조 하세요 [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atltime.h

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
기간 시간 (밀리초)입니다.

### <a name="remarks"></a>설명

합니다 `CFileTimeSpan` 기존 사용 하 여 개체를 만들 수 있습니다 `CFileTimeSpan` 개체 또는 64 비트 값으로 표현 합니다. 기본 생성자를 시간 범위를 0으로 설정 합니다.

##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan

시간 범위를 검색 하려면이 메서드는 `CFileTimeSpan` 개체입니다.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>반환 값

밀리초 단위의 시간 범위를 반환합니다.

##  <a name="operator_-"></a>  CFileTimeSpan::operator -

에 대해 빼기를 수행는 `CFileTimeSpan` 개체입니다.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

반환 된 `CFileTimeSpan` 결과 두 시간 범위 간의 차이 나타내는 개체입니다.

##  <a name="operator_neq"></a>  CFileTimeSpan::operator !=

두 `CFileTimeSpan` 개체가 다른지 비교합니다.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

비교할 항목 같지 않은 경우 TRUE를 반환 합니다 `CFileTimeSpan` 개체; 그렇지 않으면 FALSE입니다.

##  <a name="operator_add"></a>  CFileTimeSpan::operator +

에 더하기를 수행는 `CFileTimeSpan` 개체입니다.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

반환 된 `CFileTimeSpan` 에 걸쳐 총 두 시간이 들어 있는 개체입니다.

##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator +=

에 더하기를 수행는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CFileTimeSpan` 에 걸쳐 총 두 시간이 들어 있는 개체입니다.

##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;

두 `CFileTimeSpan` 더 작은 값을 결정 하는 개체입니다.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 작으면 TRUE를 반환 합니다 (즉, 더 짧은 기간을 나타냄), 두 번째 인스턴스보다 그렇지 않으면 FALSE입니다.

##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=

두 `CFileTimeSpan` 같음 또는 더 작은 값을 확인 하는 개체입니다.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체 보다 작은 경우 (즉, 더 짧은 기간을 나타냄) TRUE 또는 두 번째를 반환 합니다. 그렇지 않으면 FALSE입니다.

##  <a name="operator_eq"></a>  CFileTimeSpan::operator =

대입 연산자입니다.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CFileTimeSpan` 개체입니다.

##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator -=

에 대해 빼기를 수행는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CFileTimeSpan` 개체입니다.

##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator ==

두 `CFileTimeSpan` 개체가 같은지 비교합니다.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

개체가 같으면이 고, 그렇지 않으면 FALSE 경우 TRUE를 반환 합니다.

##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;

두 `CFileTimeSpan` 더 큰 숫자를 확인 하는 개체입니다.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체 보다 크면 TRUE를 반환 합니다 (즉, 더 긴 기간을 나타냄), 두 번째 인스턴스보다 그렇지 않으면 FALSE입니다.

##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=

두 `CFileTimeSpan` 크거나 같은 값을 확인 하는 개체입니다.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체 보다 크면 TRUE를 반환 합니다 (즉, 더 긴 기간을 나타냄) 또는 두 번째, 그렇지 않으면 FALSE입니다.

##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan

시간 범위를 설정 하려면이 메서드를 호출 합니다 `CFileTimeSpan` 개체입니다.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>매개 변수

*nSpan*<br/>
밀리초 단위의 시간 범위에 대 한 새 값입니다.

## <a name="see-also"></a>참고자료

[FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)

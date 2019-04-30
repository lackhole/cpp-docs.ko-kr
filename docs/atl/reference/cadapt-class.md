---
title: CAdapt 클래스
ms.date: 11/04/2016
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
ms.openlocfilehash: 39184e952475fa0f05a6fc25c433191ea22b5c16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260742"
---
# <a name="cadapt-class"></a>CAdapt 클래스

이 템플릿은 개체 주소 이외의 주소를 반환하도록 연산자 주소를 다시 정의하는 클래스를 래핑하는 데 사용됩니다.

## <a name="syntax"></a>구문

```
template <class T>
class CAdapt
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
조정된 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAdapt::CAdapt](#cadapt)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAdapt::operator const T &](#operator_const_t_amp)|반환 된 **상수** 에 대 한 참조 `m_T`합니다.|
|[CAdapt::operator T &](#operator_t_amp)|`m_T`에 대한 참조를 반환합니다.|
|[CAdapt::operator <](#operator_lt)|조정된 형식의 개체를 `m_T`와 비교합니다.|
|[CAdapt::operator =](#operator_eq)|조정된 형식의 개체를 `m_T`에 할당합니다.|
|[CAdapt::operator ==](#operator_eq_eq)|조정된 형식의 개체를 `m_T`와 비교합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAdapt::m_T](#m_t)|조정되는 데이터입니다.|

## <a name="remarks"></a>설명

`CAdapt`는 개체의 주소 이외의 주소를 반환하도록 연산자의 주소(`operator &`)를 다시 정의하는 클래스를 래핑하는 데 사용되는 간단한 템플릿입니다. 이러한 클래스의 예로 ATL의 `CComBSTR`, `CComPtr`, `CComQIPtr` 클래스 및 컴파일러 COM 지원 클래스인 `_com_ptr_t`가 있습니다. 이러한 클래스는 모두 해당 데이터 멤버 중 하나의 주소를 반환 주소 연산자를 다시 정의 (의 경우 BSTR `CComBSTR`, 및 다른 클래스의 경우 인터페이스 포인터).

`CAdapt`기본 역할은 클래스에 의해 정의 된 주소 연산자를 숨기려면 *T*적용할된 클래스의 특징을 유지 합니다. `CAdapt` 공용 멤버를 보유 하 여이 역할을 수행 [m_T](#m_t), 형식의 *T*, 및 변환 연산자, 비교 연산자 및 복사 생성자의 특수화를 허용 하도록 정의 하 여 `CAdapt` 되도록 형식의 개체 처럼 처리 *T*합니다.

어댑터 클래스 `CAdapt`는 일부 컨테이너 스타일 클래스가 연산자 주소를 사용하여 포함된 개체의 주소를 가져올 수 있기 때문에 유용합니다. 연산자의 주소를 다시 정의하면 일반적으로 컴파일 오류가 발생하고 "작동"해야 하는 클래스에서 조정되지 않은 형식이 사용되지 않아 이 요구 사항에 맞지 않게 됩니다. `CAdapt`가 이러한 문제에 대한 해결 방법을 제공합니다.

일반적으로 컨테이너 스타일 클래스에 `CAdapt`, `CComBSTR`, `CComPtr` 또는 `CComQIPtr` 개체를 저장하려는 경우 `_com_ptr_t`를 사용합니다. 이는 C++11 표준이 지원되기 전에 C++ 표준 라이브러리 컨테이너에 대해 가장 일반적으로 필요했지만, 이제 C++11 표준 라이브러리 컨테이너가 `operator&()`를 오버로드한 형식으로 자동으로 작동합니다. 표준 라이브러리는이 내부적으로 사용 하 여 달성 [std::addressof](../../standard-library/memory-functions.md#addressof) 개체의 실제 주소를 가져오려고 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

##  <a name="cadapt"></a>  CAdapt::CAdapt

생성자는 어댑터 개체를 생성, 조정 된 형식의 개체에서 복사 또는 다른 어댑터 개체에서 복사한 기본 수를 허용 합니다.

```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
새로 생성 된 어댑터 개체를 복사할 수를 조정 하는 형식의 변수입니다.

*rSrCA*<br/>
포함 된 데이터는 복사 (또는 이동) 새로 생성 된 어댑터 개체에는 어댑터 개체입니다.

##  <a name="m_t"></a>  CAdapt::m_T

조정 되는 데이터를 보유 합니다.

```
T m_T;
```

### <a name="remarks"></a>설명

이 **공개** 데이터 멤버와에 직접 또는 간접적으로 액세스할 수 [연산자 const T &](#operator_const_t_amp) 하 고 [연산자 T &](#operator_t_amp)합니다.

##  <a name="operator_const_t_amp"></a>  CAdapt::operator const T&amp;

반환을 **const** 에 대 한 참조를 [m_T](#m_t) 멤버, 어댑터 개체 형식의 개체 처럼 처리 되도록 허용 *T*합니다.

```
operator const T&() const;
```

### <a name="return-value"></a>반환 값

A **상수** 에 대 한 참조 `m_T`합니다.

##  <a name="operator_t_amp"></a>  CAdapt::operator T&amp;

에 대 한 참조를 반환 합니다 [m_T](#m_t) 어댑터 개체 형식의 개체 처럼 처리 되도록 허용 멤버 *T*.

```
operator T&();
```

### <a name="return-value"></a>반환 값

`m_T`에 대한 참조입니다.

##  <a name="operator_lt"></a>  CAdapt::operator &lt;

사용 하 여 조정 된 형식의 개체를 비교 [m_T](#m_t)합니다.

```
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
비교할 개체 참조입니다.

### <a name="return-value"></a>반환 값

비교 결과인 `m_T` 하 고 *rSrc*합니다.

##  <a name="operator_eq"></a>  CAdapt::operator =

대입 연산자는 인수를 할당 *rSrc*를 데이터 멤버로 [m_T](#m_t) 현재 어댑터 개체를 반환 합니다.

```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
복사할 조정 된 형식의 개체에 대 한 참조입니다.

*rSrCA*<br/>
이동할 개체에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

현재 개체에 대 한 참조입니다.

##  <a name="operator_eq_eq"></a>  CAdapt::operator ==

사용 하 여 조정 된 형식의 개체를 비교 [m_T](#m_t)합니다.

```
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
비교할 개체 참조입니다.

### <a name="return-value"></a>반환 값

비교 결과인 *m_T* 하 고 *rSrc*합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

---
title: Platform::Guid 값 클래스
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 64c70b619380d7c2ed4aaaecad3ee01a1d0f79c7
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743814"
---
# <a name="platformguid-value-class"></a>Platform::Guid 값 클래스

Windows 런타임 형식 시스템의 [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) 형식을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
public value struct Guid
```

### <a name="members"></a>멤버

`Platform::Guid` 에 `Equals()`, `GetHashCode()`, 및 `ToString()` 에서 파생 된 메서드를 [platform:: object 클래스](../cppcx/platform-object-class.md), 및 `GetTypeCode()` 에서 파생 된 메서드를 [platform:: type 클래스](../cppcx/platform-type-class.md)합니다. `Platform::Guid` 다음과 같은 멤버도 있습니다.

|멤버|설명|
|------------|-----------------|
|[Guid](#ctor)|`Platform::Guid`의 새 인스턴스를 초기화합니다.|
|[연산자==](#operator-equality)|Equals 연산자입니다.|
|[operator!=](#operator-inequality)|Not equals 연산자입니다.|
|[operator&lt;](#operator-less)|보다 작음 연산자입니다.|
|[operator()](#operator-call)|`Platform::Guid` 를 `GUID`로 변환합니다.|

### <a name="remarks"></a>설명

생성할 새 `Platform::Guid`를 사용 합니다 [Windows::Foundation::GuidHelper::CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) 정적 메서드.

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** 플랫폼

**메타데이터:** platform.winmd

## <a name="ctor"></a> Guid:: guid 생성자

`Platform::Guid`의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>매개 변수

*a*<br/>
처음 4 바이트를 `GUID`입니다.

*b*<br/>
다음 2 바이트는 `GUID`합니다.

*c*<br/>
다음 2 바이트는 `GUID`합니다.

*d*<br/>
다음 바이트를 `GUID`입니다.

*e*<br/>
다음 바이트를 `GUID`입니다.

*f*<br/>
다음 바이트를 `GUID`입니다.

*g*<br/>
다음 바이트를 `GUID`입니다.

*h*<br/>
다음 바이트를 `GUID`입니다.

*i*<br/>
다음 바이트를 `GUID`입니다.

*j*<br/>
다음 바이트를 `GUID`입니다.

*k*<br/>
다음 바이트를 `GUID`입니다.

*m*<br/>
A `GUID` 형태로 [GUID 구조체](https://msdn.microsoft.com/library/windows/desktop/aa373931)합니다.

*n*<br/>
나머지 8 바이트는 `GUID`합니다.

## <a name="operator-equality"></a> Guid::operator = = 연산자

두 `Platform::Guid` 인스턴스가 같은지 비교합니다.

### <a name="syntax"></a>구문

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>매개 변수

*guid1*<br/>
비교할 첫 번째 `Platform::Guid`입니다.

*guid2*<br/>
비교할 두 번째 `Platform::Guid`입니다.

### <a name="return-value"></a>반환 값

True 이면 두 `Platform::Guid` 인스턴스는 서로 같습니다.

### <a name="remarks"></a>설명

사용을 선호 합니다 `==` 연산자 대신 합니다 [Windows::Foundation::GuidHelper::Equals](/uwp/api/windows.foundation.guidhelper.equals) 정적 메서드.

## <a name="operator-inequality"></a> Guid::operator! = 연산자

두 `Platform::Guid` 인스턴스가 같지 않은지 합니다.

### <a name="syntax"></a>구문

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>매개 변수

*guid1*<br/>
비교할 첫 번째 `Platform::Guid`입니다.

*guid2*<br/>
비교할 두 번째 `Platform::Guid`입니다.

### <a name="return-value"></a>반환 값

True 이면 두 `Platform::Guid` 인스턴스 같지 않습니다.

## <a name="operator-less"></a> Guid::operator&lt; 연산자

두 `Platform::Guid` 인스턴스 순서를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>매개 변수

*guid1*<br/>
비교할 첫 번째 `Platform::Guid`입니다.

*guid2*<br/>
비교할 두 번째 `Platform::Guid`입니다.

### <a name="return-value"></a>반환 값

True 이면 *guid1* 앞에 정렬 되 *guid2*합니다. 각 처리 후 사전적 순서는 `Platform::Guid` 네 개의 32 비트 부호 없는 값의 배열을 말 이죠. 이 SQL Server 또는.NET Framework에서 사용 하는 정렬 되지 않으며 동일 해당 문자열 표현으로 사전순으로 정렬.

이 연산자가 제공 되도록 `Guid` c + + 표준 라이브러리에서 개체를 보다 쉽게 사용할 수 있습니다.

## <a name="operator-call"></a> Guid::operator() Operator

암시적으로 변환 합니다는 `Platform::Guid` 에 [GUID 구조체](https://msdn.microsoft.com/library/windows/desktop/aa373931)합니다.

### <a name="syntax"></a>구문

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>반환 값

A [GUID 구조체](https://msdn.microsoft.com/library/windows/desktop/aa373931)합니다.

## <a name="see-also"></a>참고자료

[Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md)

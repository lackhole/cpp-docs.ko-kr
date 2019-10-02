---
title: Platform::Guid 값 클래스
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: f63b2bb4fd5f809861622a4f6b255ee3725564b6
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816586"
---
# <a name="platformguid-value-class"></a>Platform::Guid 값 클래스

Windows 런타임 형식 시스템의 [GUID](/previous-versions/cc317743(v%3dmsdn.10)) 형식을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
public value struct Guid
```

### <a name="members"></a>멤버

`Platform::Guid`에는 [platform:: Object 클래스](../cppcx/platform-object-class.md)에서 파생 된 @no__t 1, `GetHashCode()` 및 `ToString()` 메서드와 [Platform:: Type 클래스](../cppcx/platform-type-class.md)에서 파생 된 `GetTypeCode()` 메서드가 있습니다. `Platform::Guid`에도 다음 멤버가 있습니다.

|멤버|설명|
|------------|-----------------|
|[Guid](#ctor)|`Platform::Guid`의 새 인스턴스를 초기화합니다.|
|[연산자==](#operator-equality)|Equals 연산자입니다.|
|[operator!=](#operator-inequality)|Not equals 연산자입니다.|
|[operator&lt;](#operator-less)|보다 작음 연산자입니다.|
|[operator()](#operator-call)|`Platform::Guid` 를 `GUID`로 변환합니다.|

### <a name="remarks"></a>설명

새 `Platform::Guid`을 생성 하려면 [Windows:: Foundation:: GuidHelper:: CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) 정적 메서드를 사용 합니다.

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** 플랫폼

**메타데이터:** platform.winmd

## <a name="ctor"></a>Guid:: Guid 생성자

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
@No__t의 처음 4 바이트는-0입니다.

*b*<br/>
@No__t의 다음 2 바이트입니다.

*c*<br/>
@No__t의 다음 2 바이트입니다.

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
에서 `GUID`은 [GUID 구조체](/previous-versions/cc317743(v%3dmsdn.10))를 형성 합니다.

*n*<br/>
@No__t의 나머지 8 바이트는-0입니다.

## <a name="operator-equality"></a>Guid:: operator = = 연산자

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

두 `Platform::Guid` 인스턴스가 같으면 True입니다.

### <a name="remarks"></a>설명

[Windows:: Foundation:: GuidHelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals) 정적 메서드 대신 `==` 연산자를 사용 하는 것이 좋습니다.

## <a name="operator-inequality"></a>Guid:: operator! = 연산자

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

두 `Platform::Guid` 인스턴스가 같지 않으면 True입니다.

## <a name="operator-less"></a>Guid:: operator @ no__t-1 연산자

두 `Platform::Guid` 인스턴스를 비교 하 여 정렬 합니다.

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

*Guid1* 가 *guid2*앞에 정렬 되 면 True입니다. 사전적는 4 32 비트 부호 없는 값의 배열인 것 처럼 각 `Platform::Guid`을 처리 한 후 정렬 됩니다. 이는 SQL Server 또는 .NET Framework에서 사용 되는 순서가 아니라 문자열 표현에 따라 사전순으로 정렬 하는 것과 동일 하지 않습니다.

이 연산자는 `Guid` 개체를 C++ 표준 라이브러리에서 보다 쉽게 사용할 수 있도록 제공 됩니다.

## <a name="operator-call"></a>Guid:: operator () 연산자

@No__t-0을 [GUID 구조체로](/previous-versions/cc317743(v%3dmsdn.10))암시적으로 변환 합니다.

### <a name="syntax"></a>구문

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>반환 값

[GUID 구조체](/previous-versions/cc317743(v%3dmsdn.10))입니다.

## <a name="see-also"></a>참조

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)

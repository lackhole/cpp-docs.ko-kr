---
title: RoInitializeWrapper 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: b43d5bb2f553d298584ab2ae497c22637d3beb0d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784751"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper 클래스

Windows 런타임을 초기화합니다.

## <a name="syntax"></a>구문

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>설명

`RoInitializeWrapper` Windows 런타임을 초기화 작업이 성공 했는지 여부를 나타내는 HRESULT를 반환 하는 편리 합니다. 클래스 소멸자를 호출 하므로 `::Windows::Foundation::Uninitialize`, 인스턴스의 `RoInitializeWrapper` 전역 또는 최상위 범위에서 선언 되어야 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                                    | 설명
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper::RoInitializeWrapper](#roinitializewrapper)        | `RoInitializeWrapper` 클래스의 새 인스턴스를 초기화합니다.
[RoInitializeWrapper::~RoInitializeWrapper](#tilde-roinitializewrapper) | 현재 인스턴스를 제거 합니다 `RoInitializeWrapper` 클래스입니다.

### <a name="public-operators"></a>Public 연산자

이름                                       | 설명
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper::HRESULT()](#hresult) | 검색에서 생성 된 HRESULT를 `RoInitializeWrapper` 생성자입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`RoInitializeWrapper`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers

## <a name="hresult"></a>RoInitializeWrapper::HRESULT()

마지막으로 생성 된 HRESULT 값을 검색 `RoInitializeWrapper` 생성자입니다.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapper"></a>RoInitializeWrapper::RoInitializeWrapper

`RoInitializeWrapper` 클래스의 새 인스턴스를 초기화합니다.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>매개 변수

*flags*<br/>
Windows 런타임에서 제공 하는 지원을 지정 하는 RO_INIT_TYPE 열거형 중 하나입니다.

### <a name="remarks"></a>설명

합니다 `RoInitializeWrapper` 클래스를 호출 `Windows::Foundation::Initialize(flags)`합니다.

## <a name="tilde-roinitializewrapper"></a>RoInitializeWrapper::~RoInitializeWrapper

Windows 런타임 초기화를 취소 합니다.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>설명

합니다 `RoInitializeWrapper` 클래스를 호출 `Windows::Foundation::Uninitialize()`합니다.

---
title: 이벤트 클래스 (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 2d36b4fa3d1824f43e0cfafe55c439a6bdeccb6f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785572"
---
# <a name="event-class-wrl"></a>이벤트 클래스 (WRL)

이벤트를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                   | 설명
---------------------- | ------------------------------------------------
[Event::Event](#event) | `Event` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-operators"></a>Public 연산자

이름                                 | 설명
------------------------------------ | ------------------------------------------------------------------------
[Event::operator=](#operator-assign) | 지정 된 할당 `Event` 현재 참조 `Event` 인스턴스.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HandleT`

`Event`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers

## <a name="event"></a>Event::Event

`Event` 클래스의 새 인스턴스를 초기화합니다.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
이벤트에 대한 핸들. 기본적으로 *h* 으로 초기화 됩니다 `nullptr`합니다.

## <a name="operator-assign"></a>Event::operator=

지정 된 할당 `Event` 현재 참조 `Event` 인스턴스.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
rvalue 참조는 `Event` 인스턴스.

### <a name="return-value"></a>반환 값

현재 포인터 `Event` 인스턴스.

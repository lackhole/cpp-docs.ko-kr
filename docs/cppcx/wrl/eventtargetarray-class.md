---
title: EventTargetArray 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: 1f3f8e299dba1f4b6ae5a5767f11989dc2fe8370
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784807"
---
# <a name="eventtargetarray-class"></a>EventTargetArray 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>설명

이벤트 처리기의 배열을 나타냅니다.

연관 된 이벤트 처리기는 [EventSource](eventsource-class.md) 개체는 저장의 보호 된 `EventTargetArray` 데이터 멤버입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                           | 설명
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray::EventTargetArray](#eventtargetarray)        | `EventTargetArray` 클래스의 새 인스턴스를 초기화합니다.
[EventTargetArray::~EventTargetArray](#tilde-eventtargetarray) | 현재 초기화 취소 `EventTargetArray` 클래스입니다.

### <a name="public-methods"></a>Public 메서드

이름                                  | 설명
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray::AddTail](#addtail) | 이벤트 처리기의 내부 배열의 끝에 지정된 된 이벤트 처리기를 추가합니다.
[EventTargetArray::Begin](#begin)     | 이벤트 처리기의 내부 배열에서 첫 번째 요소의 주소를 가져옵니다.
[EventTargetArray::End](#end)         | 이벤트 처리기의 내부 배열에서 마지막 요소의 주소를 가져옵니다.
[EventTargetArray::Length](#length)   | 이벤트 처리기의 내부 배열에 현재 요소 수를 가져옵니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`EventTargetArray`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="tilde-eventtargetarray"></a>EventTargetArray::~EventTargetArray

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>설명

현재 초기화 취소 `EventTargetArray` 클래스입니다.

## <a name="addtail"></a>EventTargetArray::AddTail

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>매개 변수

*element*<br/>
추가할 이벤트 처리기에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열의 끝에 지정된 된 이벤트 처리기를 추가합니다.

`AddTail()` 만 내부적으로 사용할 수는 `EventSource` 클래스입니다.

## <a name="begin"></a>EventTargetArray::Begin

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>반환 값

이벤트 처리기의 내부 배열에서 첫 번째 요소의 주소입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열에서 첫 번째 요소의 주소를 가져옵니다.

## <a name="end"></a>EventTargetArray::End

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>반환 값

이벤트 처리기의 내부 배열에서 마지막 요소의 주소입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열에서 마지막 요소의 주소를 가져옵니다.

## <a name="eventtargetarray"></a>EventTargetArray::EventTargetArray

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>매개 변수

*hr*<br/>
이 생성자 작업을 수행한 후 매개 변수 *hr* 배열 할당 성공 또는 실패 여부를 나타냅니다. 다음 목록에 대 한 가능한 값을 보여 줍니다 *hr*합니다.

+   S_OK<br/>
    작업에 성공했습니다.

+   E_OUTOFMEMORY<br/>
    배열에 대 한 메모리를 할당할 수 없습니다.

+   S_FALSE<br/>
    매개 변수 *항목* 0 보다 작거나 같음.

*items*<br/>
할당할 배열의 요소 수입니다.

### <a name="remarks"></a>설명

`EventTargetArray` 클래스의 새 인스턴스를 초기화합니다.

`EventTargetArray` 이벤트 처리기의 배열을 유지 하는 데 사용 되는 `EventSource` 개체입니다.

## <a name="length"></a>EventTargetArray::Length

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
size_t Length();
```

### <a name="return-value"></a>반환 값

현재 이벤트 처리기의 내부 배열의 요소 개수입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열에 현재 요소 수를 가져옵니다.

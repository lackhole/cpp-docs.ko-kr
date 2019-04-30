---
title: EventSource 클래스
ms.date: 09/12/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
ms.openlocfilehash: e9070fe756410e3e1bb1e5840eb3f06e29c2f46b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398513"
---
# <a name="eventsource-class"></a>EventSource 클래스

Agile이 아닌 이벤트를 나타냅니다. `EventSource` 멤버 함수는 이벤트 처리기를 추가, 삭제 및 호출합니다. Agile 이벤트를 사용 하 여 [AgileEventSource](agileeventsource-class.md)합니다.

## <a name="syntax"></a>구문

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>매개 변수

*TDelegateInterface*<br/>
인터페이스 이벤트 처리기를 나타내는 대리자입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

| 이름                                     | 설명                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource::EventSource](#eventsource) | `EventSource` 클래스의 새 인스턴스를 초기화합니다. |

### <a name="public-methods"></a>Public 메서드

| 이름                                 | 설명                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::Add](#add)             | 현재 이벤트 처리기 집합에 지정 된 대리자를 인터페이스에 의해 표시 되는 이벤트 처리기 추가 `EventSource` 개체입니다.                     |
| [EventSource::GetSize](#getsize)     | 현재 연결 된 이벤트 처리기의 수를 검색 `EventSource` 개체입니다.                                                                         |
| [EventSource::InvokeAll](#invokeall) | 현재 연결 된 각 이벤트 처리기가 호출 `EventSource` 지정 된 인수 형식 및 인수를 사용 하 여 개체입니다.                                      |
| [EventSource::Remove](#remove)       | 현재 연결 된 이벤트 처리기 집합에서 지정 된 이벤트 등록 토큰을 나타내는 이벤트 처리기를 삭제 합니다. `EventSource` 개체입니다. |

### <a name="protected-data-members"></a>보호된 데이터 멤버

| 이름                                                    | 설명                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::addRemoveLock_](#addremovelock)           | 에 대 한 액세스를 동기화 합니다 [targets_](#targets) 배열을 추가 하는 경우, 제거 또는 이벤트 처리기를 호출 합니다.                          |
| [EventSource::targets_](#targets)                       | 하나 이상의 이벤트 처리기 배열입니다.                                                                                           |
| [EventSource::targetsPointerLock_](#targetspointerlock) | 이 EventSource의 이벤트 처리기를 추가, 삭제 또는 호출하는 동안에도 내부 데이터 멤버에 대한 액세스를 동기화합니다. |

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`EventSource`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL

## <a name="add"></a>EventSource::Add

현재 이벤트 처리기 집합에 지정 된 대리자를 인터페이스에 의해 표시 되는 이벤트 처리기 추가 `EventSource` 개체입니다.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>매개 변수

*delegateInterface*<br/>
이벤트 처리기를 나타내는 대리자 개체에 대 한 인터페이스입니다.

*token*<br/>
이 작업이 완료 될 때 이벤트를 나타내는 핸들입니다. 이 토큰에 대 한 매개 변수로 사용 합니다 [remove ()](#remove) 이벤트 처리기를 삭제 하는 방법입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="addremovelock"></a>EventSource::addRemoveLock_

에 대 한 액세스를 동기화 합니다 [targets_](#targets) 배열을 추가 하는 경우, 제거 또는 이벤트 처리기를 호출 합니다.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsource"></a>EventSource::EventSource

`EventSource` 클래스의 새 인스턴스를 초기화합니다.

```cpp
EventSource();
```

## <a name="getsize"></a>EventSource::GetSize

현재 연결 된 이벤트 처리기의 수를 검색 `EventSource` 개체입니다.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>반환 값

이벤트 처리기의 수가 [targets_](#targets)합니다.

## <a name="invokeall"></a>EventSource::InvokeAll

현재 연결 된 각 이벤트 처리기가 호출 `EventSource` 지정 된 인수 형식 및 인수를 사용 하 여 개체입니다.

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>매개 변수

*T0*<br/>
0번째 이벤트 처리기 인수 형식입니다.

*T1*<br/>
첫 번째 이벤트 처리기 인수 형식입니다.

*T2*<br/>
두 번째 이벤트 처리기 인수 형식입니다.

*T3*<br/>
세 번째 이벤트 처리기 인수 형식입니다.

*T4*<br/>
네 번째 이벤트 처리기 인수 형식입니다.

*T5*<br/>
다섯 번째 이벤트 처리기 인수 형식입니다.

*T6*<br/>
여섯 번째 이벤트 처리기 인수 형식입니다.

*T7*<br/>
일곱 번째 이벤트 처리기 인수 형식입니다.

*T8*<br/>
여덟 번째 이벤트 처리기 인수 형식입니다.

*T9*<br/>
아홉 번째 이벤트 처리기 인수 형식입니다.

*arg0*<br/>
0번째 이벤트 처리기 인수입니다.

*arg1*<br/>
첫 번째 이벤트 처리기 인수입니다.

*arg2*<br/>
두 번째 이벤트 처리기 인수입니다.

*arg3*<br/>
세 번째 이벤트 처리기 인수입니다.

*arg4*<br/>
네 번째 이벤트 처리기 인수입니다.

*arg5*<br/>
다섯 번째 이벤트 처리기 인수입니다.

*arg6*<br/>
여섯 번째 이벤트 처리기 인수입니다.

*arg7*<br/>
일곱 번째 이벤트 처리기 인수입니다.

*arg8*<br/>
여덟 번째 이벤트 처리기 인수입니다.

*arg9*<br/>
아홉 번째 이벤트 처리기 인수입니다.

## <a name="remove"></a>EventSource::Remove

현재 연결 된 이벤트 처리기 집합에서 지정 된 이벤트 등록 토큰을 나타내는 이벤트 처리기를 삭제 합니다. `EventSource` 개체입니다.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>매개 변수

*token*<br/>
이벤트 처리기를 나타내는 핸들입니다. 이 토큰은 이벤트 처리기를 등록 된 경우 반환 된 합니다 [add ()](#add) 메서드.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

에 대 한 자세한 내용은 `EventRegistrationToken` 구조체를 참조 하세요를 **Windows::Foundation::EventRegistrationToken 구조** 항목에는 **Windows 런타임** 설명서를 참조 합니다.

## <a name="targets"></a>EventSource::targets_

하나 이상의 이벤트 처리기 배열입니다.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>설명

때 현재 표시 되는 이벤트 `EventSource` 발생 하는 개체, 이벤트 처리기가 호출 됩니다.

## <a name="targetspointerlock"></a>EventSource::targetsPointerLock_

이 대 한 이벤트 처리기는 동안에 내부 데이터 멤버에 대 한 액세스를 동기화 `EventSource` 추가, 제거 또는 호출 합니다.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```

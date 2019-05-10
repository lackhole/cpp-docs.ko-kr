---
title: task_continuation_context 클래스
ms.date: 11/04/2016
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
ms.openlocfilehash: 5d7d92fcd1bb00513b9e05030afa56726e87183b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212859"
---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context 클래스

`task_continuation_context` 클래스를 사용하면 연속 실행 위치를 지정할 수 있습니다. 만 Windows 런타임 앱에서이 클래스를 사용 하는 것이 유용 합니다. 비-Windows 런타임 앱에 대 한 작업 연속의 실행 컨텍스트는 런타임에 의해 결정 및 구성할 수 없습니다.

## <a name="syntax"></a>구문

```
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|현재 winrt 스레드 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환 합니다.|
|[use_arbitrary](#use_arbitrary)|런타임이 연속에 대한 실행 컨텍스트를 선택할 수 있는 작업 연속 컨텍스트를 만듭니다.|
|[use_current](#use_current)|현재 실행 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환합니다.|
|[use_default](#use_default)|기본 작업 연속 컨텍스트를 만듭니다.|
|[use_synchronous_execution](#use_synchronous_execution)|동기 실행 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>요구 사항

**헤더:** ppltasks.h

**네임스페이스:** 동시성

## <a name="get_current_winrt_context"></a> get_current_winrt_context

현재 WinRT 스레드 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환 합니다.

## <a name="syntax"></a>구문

```
static task_continuation_context get_current_winrt_context();
```

## <a name="return-value"></a>반환 값

현재 Windows 런타임 스레드 컨텍스트입니다. Windows 런타임 이외의 컨텍스트에서 호출 되는 경우에 빈 task_continuation_context를 반환 합니다.

## <a name="remarks"></a>설명

`get_current_winrt_context` 메서드 호출자의 Windows 런타임 스레드 컨텍스트를 캡처합니다. 빈 컨텍스트에 비-Windows Runtime 호출자에 게 반환합니다.

반환한 값 `get_current_winrt_context` 선행 작업이 아파트를 인식 하는지 여부에 관계 없이 캡처된 컨텍스트 (STA 및 MTA)의 아파트 모델에서 연속 작업을 실행 해야 런타임에 나타내는 데 사용할 수 있습니다. 아파트 인식 작업에는 Windows 런타임의 래핑을 해제 하는 작업은 `IAsyncInfo` 인터페이스 또는 그러한 작업의 하위 작업을 합니다.

이 메서드는 비슷합니다는 `use_current` 메서드를 하지만 네이티브를 사용할 수도 있습니다. C++ 없이 코드 C++/CX 확장 지원 합니다. 사용 하 여 고급 사용자가 작성 한 것은 C++native와 Windows 런타임 호출자에 대 한 /CX-agnostic 라이브러리 코드입니다. 이 기능이 필요 하지 않는 한 것이 좋습니다 합니다 `use_current` 메서드를 사용할 수 있는 C++/CX 클라이언트입니다.

##  <a name="use_arbitrary"></a> use_arbitrary

런타임이 연속에 대한 실행 컨텍스트를 선택할 수 있는 작업 연속 컨텍스트를 만듭니다.

```
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>반환 값

임의의 위치를 나타내는 작업 연속 컨텍스트.

### <a name="remarks"></a>설명

이 연속 컨텍스트를 사용 하는 경우 연속은 선행 작업이 아파트를 인식 하는 경우에 런타임은 컨텍스트에서 실행 됩니다.

`use_arbitrary` STA.에서 만든 아파트 인식 작업에서 연속 된 작업에 대 한 기본 동작을 해제할 수 있습니다.

이 메서드는 Windows 런타임 앱에 사용할 수만 있습니다.

##  <a name="use_current"></a> use_current

현재 실행 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환합니다.

```
static task_continuation_context use_current();
```

### <a name="return-value"></a>반환 값

현재 실행 컨텍스트입니다.

### <a name="remarks"></a>설명

이 메서드는 연속 오른쪽 아파트에서 실행 될 수 있도록 호출자의 Windows 런타임 컨텍스트를 캡처합니다.

반환한 값 `use_current` 연속이 선행 작업이 아파트를 인식 여부에 관계 없이 캡처된 컨텍스트 (STA 및 MTA)에서 실행 되어야 런타임에 나타내는 데 사용할 수 있습니다. 아파트 인식 작업에는 Windows 런타임의 래핑을 해제 하는 작업은 `IAsyncInfo` 인터페이스 또는 그러한 작업의 하위 작업을 합니다.

이 메서드는 Windows 런타임 앱에 사용할 수만 있습니다.

##  <a name="use_default"></a> use_default

기본 작업 연속 컨텍스트를 만듭니다.

```
static task_continuation_context use_default();
```

### <a name="return-value"></a>반환 값

기본 연속 컨텍스트입니다.

### <a name="remarks"></a>설명

기본 컨텍스트를 지정 하지 않으면 연속 컨텍스트를 호출할 때 사용 되는 `then` 메서드. Windows 7 이하의 Windows 응용 프로그램 및 데스크톱 응용 프로그램과 Windows 8 이상, 런타임은 연속 작업은 실행할 위치 결정 합니다. 그러나 Windows 런타임 앱에서 아파트 인식 작업에서 연속 된 작업에 대 한 기본 연속 컨텍스트 됩니다 여기서 `then` 가 호출 됩니다.

아파트 인식 작업에는 Windows 런타임의 래핑을 해제 하는 작업은 `IAsyncInfo` 인터페이스 또는 그러한 작업의 하위 작업을 합니다. 따라서 Windows 런타임 STA에서 아파트 인식 작업에서 연속 된 작업을 예약 하는 경우 연속 작업은 해당 STA에서 실행

비 아파트 인식 작업에서 연속 런타임은 컨텍스트에서 실행 됩니다.

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution

동기 실행 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환 합니다.

## <a name="syntax"></a>구문

```
static task_continuation_context use_synchronous_execution();
```

## <a name="return-value"></a>반환 값

동기 실행 컨텍스트입니다.

## <a name="remarks"></a>설명

`use_synchronous_execution` 메서드를 사용 하면 연속 작업이 선행 작업의 완료를 일으키는 컨텍스트에서 동기적으로 실행 되도록 합니다.

선행 작업이 이미 완료 연속 연결 될 때 연속 작업 연속을 연결 하는 컨텍스트에서 동기적으로 실행 됩니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)

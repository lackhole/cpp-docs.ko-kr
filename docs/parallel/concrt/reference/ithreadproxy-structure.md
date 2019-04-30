---
title: IThreadProxy 구조체
ms.date: 11/04/2016
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
ms.openlocfilehash: 906b05800711e89592e5230bec7fa0fe1640379f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346232"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy 구조체

실행 스레드에 대한 추상화입니다. 직접 만든 스케줄러의 `SchedulerType` 정책 키에 따라 리소스 관리자는 일반 Win32 스레드 또는 UMS(사용자 모드 예약 가능) 스레드 중 하나에서 지원되는 스레드 프록시를 부여합니다. UMS 스레드는 Windows 7 이상 버전의 64비트 운영 체제에서 지원됩니다.

## <a name="syntax"></a>구문

```
struct IThreadProxy;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IThreadProxy::GetId](#getid)|스레드 프록시에 대 한 고유 식별자를 반환합니다.|
|[IThreadProxy::SwitchOut](#switchout)|내부 가상 프로세서 루트에서 컨텍스트의 연결을 끊습니다.|
|[IThreadProxy::SwitchTo](#switchto)|현재 실행 컨텍스트를 다른 페이지로 협조적 컨텍스트 전환을 수행합니다.|
|[IThreadProxy::YieldToSystem](#yieldtosystem)|호출 스레드가 현재 프로세서에서 실행할 준비가 되어 있는 다른 스레드에 실행 명령을 내리도록 합니다. 운영 체제를 실행 하는 다음 스레드에서 선택 합니다.|

## <a name="remarks"></a>설명

스레드 프록시는 인터페이스에 의해 표시 되는 실행 컨텍스트를 결합 되어 `IExecutionContext` 작업 디스패치 하는 것입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IThreadProxy`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="getid"></a>  Ithreadproxy:: Getid 메서드

스레드 프록시에 대 한 고유 식별자를 반환합니다.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>반환 값

고유 정수 식별자입니다.

##  <a name="switchout"></a>  Ithreadproxy:: Switchout 메서드

내부 가상 프로세서 루트에서 컨텍스트의 연결을 끊습니다.

```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>매개 변수

*switchState*<br/>
스위치를 실행 하는 스레드 프록시의 상태를 나타냅니다. 이 매개 변수는 형식 `SwitchingProxyState`합니다.

### <a name="remarks"></a>설명

어떠한 이유로든 실행 중인 가상 프로세서 루트에서 컨텍스트 연결을 끊어야 할 경우 `SwitchOut`을 사용합니다. `switchState` 매개변수에 전달하는 값에 따라 그리고 가상 프로세서 루트에서 실행하는지 여부에 따라 이 호출은 해당 컨텍스트와 연결된 스레드 프록시를 즉시 반환하거나 차단합니다. 매개 변수를 `SwitchOut`로 설정하여 `Idle`을 호출하면 오류가 발생합니다. 이렇게 하면 프로그램 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외입니다.

`SwitchOut`은 리소스 관리자의 지시에 따라 또는 일시적으로 초과 구독된 가상 프로세서 루트를 요청했는데 그러한 요청이 처리되어 스케줄러의 가상 프로세서 루트 수를 줄이고자 할 때 유용합니다. 메서드를 호출 해야 하는 예제의 [IVirtualProcessorRoot::Remove](iexecutionresource-structure.md#remove) 가상 프로세서 루트를 호출 하기 전에 `SwitchOut` 매개 변수를 사용 하 여 `switchState` 로 `Blocking`합니다. 이렇게 하면 스레드 프록시가 차단되고, 스케줄러의 다른 가상 프로세서 루트에서 실행할 수 있을 때 실행이 다시 시작됩니다. 함수를 호출 하 여 차단 스레드 프록시를 다시 시작할 수 있습니다 `SwitchTo` 이 스레드 프록시가 실행 컨텍스트를 전환할 수 있습니다. 또한 가상 프로세서 루트를 활성화 하려면 해당 연결 된 컨텍스트를 사용 하 여 스레드 프록시를 다시 시작할 수 있습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate)합니다.

또한 `SwitchOut`은 스레드 프록시를 차단하거나, 스레드 프록시가 실행 중인 가상 프로세서 루트와 스레드 프록시를 디스패칭하는 스케줄러에서 일시적으로 연결을 끊는 동안 나중에 활성화될 수 있도록 가상 프로세서를 다시 초기화하려 할 때도 사용할 수 있습니다. 스레드 프록시를 차단하려는 경우 `SwitchOut` 매개 변수를 `switchState`으로 설정하여 `Blocking`을 사용합니다. 위에서 언급했듯이 `SwitchTo` 또는 `IVirtualProcessorRoot::Activate`을 사용하여 나중에 다시 시작할 수 있습니다. 이 스레드 프록시가 실행 중인 가상 프로세서 루트 및 가상 프로세서가 연결된 스케줄러에서 일시적으로 스레드 프록시의 연결을 끊으려면 매개 변수를 `SwitchOut`으로 설정하여 `Nesting`을 사용합니다. 가상 프로세서 루트에서 실행 중일 때 `SwitchOut` 매개 변수를 `switchState`으로 설정하여 `Nesting`을 호출하면 루트가 다시 초기화되고 현재 스레드 프록시가 다른 루트를 필요로 하지 않고 계속 실행됩니다. 스레드 프록시 호출 될 때까지 스케줄러에 남아 있는 것으로 간주 됩니다 합니다 [ithreadproxy::](#switchout) 메서드를 `Blocking` 나중 시간에서입니다. 매개 변수를 `SwitchOut`으로 설정하여 `Blocking`을 두 번째로 호출하는 목적은, 컨텍스트를 차단된 상태로 돌려서 `SwitchTo` 또는 컨텍스트 연결을 끊은 스케줄러의 `IVirtualProcessorRoot::Activate`에 의해 다시 시작될 수 있도록 하는 것입니다. 컨텍스트는 가상 프로세서 루트에서 실행되고 있지 않았기 때문에 다시 초기화가 수행되지 않습니다.

다시 초기화된 가상 프로세서 루트는 리소스 관리자가 스케줄러를 부여한 새로운 가상 프로세서 루트와 차이가 없습니다. 이는 `IVirtualProcessorRoot::Activate`를 사용하여 실행 컨텍스트로 가상 프로세서 루트를 활성화함으로써 실행하는 데 사용할 수 있습니다.

`SwitchOut` 호출 해야 합니다 `IThreadProxy` 현재 실행 중인 스레드 또는 결과 나타내는 인터페이스 정의 되지 않습니다.

Visual Studio 2010과 함께 제공된 헤더 및 라이브러리에서 이 메서드는 매개 변수를 사용하지 않으며 가상 프로세서 루트를 다시 초기화하지 않습니다. 이전 동작을 유지하기 위해 `Blocking`의 기본 매개 변수 값이 제공됩니다.

##  <a name="switchto"></a>  Ithreadproxy:: Switchto 메서드

현재 실행 컨텍스트를 다른 페이지로 협조적 컨텍스트 전환을 수행합니다.

```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
협조적으로 전환 하려면 실행 컨텍스트입니다.

*switchState*<br/>
스위치를 실행 하는 스레드 프록시의 상태를 나타냅니다. 이 매개 변수는 형식 `SwitchingProxyState`합니다.

### <a name="remarks"></a>설명

하나의 실행 컨텍스트에서 간에 전환 하려면이 메서드를 사용 합니다 [iexecutioncontext:: Dispatch](iexecutioncontext-structure.md#dispatch) 첫 번째 실행 컨텍스트의 메서드. 메서드 실행 컨텍스트 연결 `pContext` 아직 하나를 사용 하 여 연결 되지 않은 경우 스레드 프록시를 사용 하 여 합니다. 현재 스레드 프록시가의 소유권에 대해 지정한 값으로 결정 됩니다는 `switchState` 인수입니다.

값을 사용 하 여 `Idle` Resource Manager에는 현재 실행 중인 스레드 프록시를 반환 하려는 경우. 호출 `SwitchTo` 매개 변수를 사용 하 여 `switchState` 로 설정 `Idle` 실행 컨텍스트 하면 `pContext` 기본 실행 리소스에서 실행을 시작 합니다. 이 스레드 프록시의 소유권에는 Resource Manager로 전송 되 고 실행 컨텍스트를 반환 해야 하는 `Dispatch` 메서드 직후 `SwitchTo` 전송을 완료 하기 위해 반환 합니다. 스레드 프록시를에서 스레드 프록시가 디스패치는 실행 컨텍스트를 분리 하며 스케줄러를 다시 사용 하거나 필요할 때 삭제 무료입니다.

값을 사용 하 여 `Blocking` 이 스레드 프록시가 차단 된 상태로 전환 하려는 경우. 호출 `SwitchTo` 매개 변수와 함께 `switchState` 로 설정 `Blocking` 실행 컨텍스트 하면 `pContext` 실행을 시작 하 여 다시 시작할 때까지 현재 스레드 프록시가 차단 합니다. 스케줄러 스레드 프록시의 경우 스레드 프록시의 소유권을 보유 합니다 `Blocking` 상태입니다. 함수를 호출 하 여 차단 스레드 프록시를 다시 시작할 수 있습니다 `SwitchTo` 이 스레드 프록시가 실행 컨텍스트를 전환할 수 있습니다. 또한 가상 프로세서 루트를 활성화 하려면 해당 연결 된 컨텍스트를 사용 하 여 스레드 프록시를 다시 시작할 수 있습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate)합니다.

값을 사용 하 여 `Nesting` 이 스레드 프록시가 실행 중인 가상 프로세서 루트에서 일시적으로 분리 하려는 시점과 스케줄러 작업을 디스패치 됩니다. 호출 `SwitchTo` 매개 변수와 함께 `switchState` 로 설정 `Nesting` 실행 컨텍스트 하면 `pContext` 를 실행 하 고 현재 시작 스레드 프록시도 계속 가상 프로세서 루트에 대 한 필요 없이 실행 합니다. 스레드 프록시 호출 될 때까지 스케줄러에 남아 있는 것으로 간주 됩니다 합니다 [ithreadproxy::](#switchout) 나중 시간에서 메서드. `IThreadProxy::SwitchOut` 메서드는 가상 프로세서 루트를 재조정할 수 있을 때까지 스레드 프록시를 차단할 수 있습니다.

`SwitchTo` 호출 해야 합니다 `IThreadProxy` 현재 실행 중인 스레드 또는 결과 나타내는 인터페이스 정의 되지 않습니다. 함수가 throw `invalid_argument` 하는 경우 매개 변수 `pContext` 로 설정 된 `NULL`합니다.

##  <a name="yieldtosystem"></a>  IThreadProxy::YieldToSystem Method

호출 스레드가 현재 프로세서에서 실행할 준비가 되어 있는 다른 스레드에 실행 명령을 내리도록 합니다. 운영 체제를 실행 하는 다음 스레드에서 선택 합니다.

```
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>설명

일반 Windows 스레드를 지 원하는 스레드 프록시를 호출할 때 `YieldToSystem` Windows 함수를 정확 하 게 처럼 `SwitchToThread`합니다. 하지만 사용자 모드 예약 가능 (UMS) 스레드를 호출 하는 경우는 `SwitchToThread` 함수는 운영 체제가 아닌 사용자 모드 스케줄러를 실행 하는 다음 스레드에서 선택 하는 작업을 위임 합니다. 시스템에서 준비 다른 스레드로 전환의 원하는 효과 달성 하려면 사용 `YieldToSystem`합니다.

`YieldToSystem` 호출 해야 합니다 `IThreadProxy` 현재 실행 중인 스레드 또는 결과 나타내는 인터페이스 정의 되지 않습니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IExecutionContext 구조체](iexecutioncontext-structure.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)

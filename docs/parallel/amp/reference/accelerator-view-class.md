---
title: accelerator_view 클래스
ms.date: 03/27/2019
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view::accelerator_view
- AMPRT/Concurrency::accelerator_view::create_marker
- AMPRT/Concurrency::accelerator_view::flush
- AMPRT/Concurrency::accelerator_view::get_accelerator
- AMPRT/Concurrency::accelerator_view::get_is_auto_selection
- AMPRT/Concurrency::accelerator_view::get_is_debug
- AMPRT/Concurrency::accelerator_view::get_queuing_mode
- AMPRT/Concurrency::accelerator_view::get_version
- AMPRT/Concurrency::accelerator_view::wait
- AMPRT/Concurrency::accelerator_view::accelerator
- AMPRT/Concurrency::accelerator_view::is_auto_selection
- AMPRT/Concurrency::accelerator_view::is_debug
- AMPRT/Concurrency::accelerator_view::queuing_mode
- AMPRT/Concurrency::accelerator_view::version
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
ms.openlocfilehash: 4075051ec07fc1331d815534a715c0411160fe14
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58566028"
---
# <a name="acceleratorview-class"></a>accelerator_view 클래스

C + + AMP 데이터 병렬 가속기에서 가상 장치 추상화를 나타냅니다.

### <a name="syntax"></a>구문

```
class accelerator_view;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[accelerator_view 생성자](#ctor)|`accelerator_view` 클래스의 새 인스턴스를 초기화합니다.|
|[~ accelerator_view 소멸자](#dtor)|제거 된 `accelerator_view` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[create_marker](#create_marker)|지금이 전송 된 모든 명령의 완료를 추적 하는 future를 반환 `accelerator_view` 개체입니다.|
|[flush](#flush)|전송 큐에 대기 중인 모든 보류 중인 명령은 `accelerator_view` 개체 실행에 대 한 액셀러레이터 키입니다.|
|[get_accelerator](#get_accelerator)|`accelerator` 개체의 `accelerator_view` 개체를 반환합니다.|
|[get_is_auto_selection](#get_is_auto_selection)|런타임에서 적절 한 액셀러레이터를 자동으로 선택 됩니다 있는지 여부를 나타내는 부울 값을 반환 때 합니다 `accelerator_view` 개체를 전달 하는 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.|
|[get_is_debug](#get_is_debug)|나타내는 부울 값을 반환 하는지 여부를 `accelerator_view` 개체를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고에 있습니다.|
|[get_queuing_mode](#get_queuing_mode)|큐 모드를 반환 합니다 `accelerator_view` 개체입니다.|
|[get_version](#get_version)|버전을 반환 합니다 `accelerator_view`합니다.|
|[wait](#wait)|에 제출 된 모든 명령에 대 한 대기를 `accelerator_view` 개체가 완료 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator!=](#operator_neq)|비교 `accelerator_view` 다른 개체를 반환 합니다 **false** 같으면 경우 그렇지 않으면 반환 **true**합니다.|
|[operator=](#operator_eq)|지정 된 내용을 복사 `accelerator_view` 을 여기에 개체입니다.|
|[연산자==](#operator_eq_eq)|비교 `accelerator_view` 다른 개체를 반환 합니다 **true** 같으면 경우 그렇지 않으면 반환 **false**합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[accelerator](#accelerator)|`accelerator` 개체에 대한 `accelerator_view` 개체를 가져옵니다.|
|[is_auto_selection](#is_auto_selection)|런타임에서 적절 한 액셀러레이터를 자동으로 선택 됩니다 있는지 여부를 나타내는 부울 값을 가져옵니다 때 합니다 `accelerator_view` 개체를 전달 하는 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.|
|[is_debug](#is_debug)|나타내는 부울 값을 가져옵니다 여부는 `accelerator_view` 개체를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고에 합니다.|
|[queuing_mode](#queuing_mode)|큐 모드를 가져옵니다는 `accelerator_view` 개체입니다.|
|[version](#version)|액셀러레이터 키의 버전을 가져옵니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`accelerator_view`

### <a name="remarks"></a>설명

`accelerator_view` 개체는 액셀러레이터 키의 논리적이 고 격리 된 뷰를 나타냅니다. 하나의 실제 계산 장치를 논리적이 고 격리 된 여러 있습니다 `accelerator_view` 개체입니다. 각 가속기에는 기본 `accelerator_view` 개체입니다. 추가 `accelerator_view` 개체를 만들 수 있습니다.

물리적 장치는 많은 클라이언트 스레드 간에 공유할 수 있습니다. 클라이언트 스레드 협조적으로 사용 된 동일한 `accelerator_view` 개체는 액셀러레이터 또는 각 클라이언트의 독립적인 통해 계산 장치와 통신할 수 `accelerator_view` 에서 다른 클라이언트 스레드와 격리에 대 한 개체입니다.

`accelerator_view` 개체는 두 가지 중 하나일 수 있습니다 [queuing_mode 열거형](concurrency-namespace-enums-amp.md#queuing_mode) 상태입니다. 큐 모드가 `immediate`와 같은 명령도 `copy` 고 `parallel_for_each` 호출자에 게 반환 되는 즉시 해당 가속기 장치로 보내집니다. 큐 모드가 `deferred`, 이러한 명령에 해당 하는 명령 큐에 대기 되며는 `accelerator_view` 개체입니다. 명령을까지 장치로 실제 전송 되지 않습니다 `flush()` 라고 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**네임스페이스:** 동시성

## <a name="accelerator"></a> 액셀러레이터 키

Accelerator_view 개체에 대 한 액셀러레이터 키 개체를 가져옵니다.

### <a name="syntax"></a>구문

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="ctor"></a> accelerator_view

기존 복사 하 여 accelerator_view 클래스의 새 인스턴스를 초기화 `accelerator_view` 개체입니다.

### <a name="syntax"></a>구문

```
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>매개 변수

*other*<br/>
`accelerator_view` 복사할 개체입니다.

## <a name="createmarker"></a>create_marker

지금이 전송 된 모든 명령의 완료를 추적 하는 future를 반환 `accelerator_view` 개체입니다.

### <a name="syntax"></a>구문

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>반환 값

지금이 전송 된 모든 명령의 완료를 추적 하는 미래 `accelerator_view` 개체입니다.

## <a name="flush"></a>flush

Accelerator_view 개체 실행의 액셀러레이터에 대기 중인 모든 보류 중인 명령을 제출 합니다.

### <a name="syntax"></a>구문

```
void flush();
```

### <a name="return-value"></a>반환 값

`void`를 반환합니다.

## <a name="getaccelerator"></a>get_accelerator

Accelerator_view 개체에 대 한 액셀러레이터 개체를 반환합니다.
### <a name="syntax"></a>구문

```
accelerator get_accelerator() const;
```

### <a name="return-value"></a>반환 값

Accelerator_view 개체에 대 한 액셀러레이터 키 개체입니다.

## <a name="getisautoselection"></a>get_is_auto_selection

선택할지 여부를 자동으로 적절 한 액셀러레이터 accelerator_view 전달 될 때를 나타내는 부울 값을 반환 된 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.

### <a name="syntax"></a>구문

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 런타임에서 자동으로 적절 한 액셀러레이터;를 선택 하는 경우이 고, 그렇지 **false**합니다.

## <a name="getisdebug"></a>get_is_debug

Accelerator_view 개체를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고에 있는지 여부를 나타내는 부울 값을 반환 합니다.

### <a name="syntax"></a>구문

```
bool get_is_debug() const;
```

### <a name="return-value"></a>반환 값

`accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값입니다.

## <a name="getqueuingmode"></a>get_queuing_mode

Accelerator_view 개체에 대 한 큐 모드를 반환합니다.

### <a name="syntax"></a>구문

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>반환 값

`accelerator_view` 개체의 큐 모드입니다.

## <a name="getversion"></a>get_version

Accelerator_view의 버전을 반환 합니다.

### <a name="syntax"></a>구문

```
unsigned int get_version() const;
```

### <a name="return-value"></a>반환 값

버전을 `accelerator_view`입니다.

## <a name="isautoselection"></a>is_auto_selection

선택할지 여부를 자동으로 적절 한 액셀러레이터 accelerator_view 전달 될 때를 나타내는 부울 값을 가져옵니다를 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.

### <a name="syntax"></a>구문

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="isdebug"></a>is_debug

Accelerator_view 개체를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고에 있는지 여부를 나타내는 부울 값을 가져옵니다.

### <a name="syntax"></a>구문

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator_neq"></a> operator!=

다른이 accelerator_view 개체를 비교 하 고 반환 **false** 같으면 경우 반환이 고, 그렇지 **true**합니다.

### <a name="syntax"></a>구문

```
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>매개 변수

*other*<br/>
이것과 비교할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>반환 값

**false** 두 개체가 동일 하면이 고, 그렇지 **true**합니다.

## <a name="operator_eq"></a> operator=

지정 된 accelerator_view 개체의 내용을 여기로 복사합니다.

### <a name="syntax"></a>구문

```
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>매개 변수

*other*<br/>
`accelerator_view` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

수정된 `accelerator_view` 개체에 대한 참조입니다.

## <a name="operator_eq_eq"></a> operator==

다른이 accelerator_view 개체를 비교 하 고 반환 **true** 같으면 경우 반환이 고, 그렇지 **false**합니다.

### <a name="syntax"></a>구문

```
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>매개 변수

*other*<br/>
이것과 비교할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>반환 값

**true 이면** 두 개체가 동일 하면이 고, 그렇지 **false**합니다.

## <a name="queuingmode"></a>queuing_mode

Accelerator_view 개체에 대 한 큐 모드를 가져옵니다.

### <a name="syntax"></a>구문

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>버전

Accelerator_view의 버전을 가져옵니다.

### <a name="syntax"></a>구문

```
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>대기

완료를 위한 모든 명령이 accelerator_view 개체에 제출 될 때까지 기다립니다.

### <a name="syntax"></a>구문

```
void wait();
```

### <a name="return-value"></a>반환 값

`void`를 반환합니다.

### <a name="remarks"></a>설명

경우는 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) 는 `immediate`,이 메서드는 블로킹 없이 즉시 반환 합니다.

##  <a name="dtor"></a> ~accelerator_view

Accelerator_view 개체를 제거합니다.

### <a name="syntax"></a>구문

```
~accelerator_view();
```

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)

---
title: task_handle 클래스
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 8528bc212603484be9325ed967e9475e4faa1348
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346152"
---
# <a name="taskhandle-class"></a>task_handle 클래스

`task_handle` 클래스는 개별 병렬 작업 항목을 나타냅니다. 작업을 실행하는 데 필요한 지침 및 데이터를 캡슐화합니다.

## <a name="syntax"></a>구문

```
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

#### <a name="parameters"></a>매개 변수

*_Function*<br/>
표현 되는 작업을 실행 하기 위해 호출 될 함수 개체의 형식은 `task_handle` 개체입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[task_handle](#task_handle)|새 `task_handle` 개체를 생성합니다. 태스크의 작업은 생성자에 매개 변수로 지정 된 함수를 호출 하 여 수행 됩니다.|
|[~ task_handle 소멸자](#dtor)|제거 된 `task_handle` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator()](#task_handle__operator_call)|작업 핸들의 작업을 수행 하는 런타임 호출 하는 함수 호출 연산자입니다.|

## <a name="remarks"></a>설명

`task_handle` 개체와 함께에서 사용할 수는 `structured_task_group` 또는 보다 일반적인 `task_group` 개체, 작업을 병렬 작업으로 분해 합니다. 자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.

작성자는 `task_handle` 개체가 만들어진의 수명 동안 유지 관리를 담당 `task_handle` 동시성 런타임에서 더 이상는 필요할 때까지 개체입니다. 즉 일반적으로 `task_handle` 될 때까지 개체 소멸 되지 해야 합니다는 `wait` 또는 `run_and_wait` 메서드를 `task_group` 또는 `structured_task_group` 대기 하는 호출 된 합니다.

`task_handle` 개체는 일반적으로 함께에서 사용 됩니다 C++ 람다 식입니다. 람다 식에서의 true 형식을 확인할 수 없는 때문에 [make_task](concurrency-namespace-functions.md#make_task) 함수는 만드는 데 일반적으로 `task_handle` 개체.

런타임에서 작업 함수에 전달 하는 복사본을 만듭니다는 `task_handle` 개체입니다. 따라서 함수에서 발생 하는 모든 상태 변경 내용을 개체에 전달 해야 하는 `task_handle` 개체는 함수 개체의 복사본에 나타나지 것입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`task_handle`

## <a name="requirements"></a>요구 사항

**헤더:** ppl.h

**네임스페이스:** 동시성

##  <a name="task_handle__operator_call"></a> operator()

작업 핸들의 작업을 수행 하는 런타임 호출 하는 함수 호출 연산자입니다.

```
void operator()() const;
```

## <a name="taskhandle"></a>task_handle

새 `task_handle` 개체를 생성합니다. 태스크의 작업은 생성자에 매개 변수로 지정 된 함수를 호출 하 여 수행 됩니다.

```
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>매개 변수

*_Func*<br/>
표현 되는 작업을 실행 하기 위해 호출 될 함수를 `task_handle` 개체입니다. 이 람다 함수, 함수에 대 한 포인터 이거나 서명 사용 하 여 함수 호출 연산자의 버전을 지 원하는 모든 개체 `void operator()()`합니다.

### <a name="remarks"></a>설명

런타임에서는 생성자에 전달 하는 작업 함수의 복사본을 만듭니다. 따라서 함수에서 발생 하는 모든 상태 변경 내용을 개체에 전달 해야 하는 `task_handle` 개체는 함수 개체의 복사본에 나타나지 것입니다.

##  <a name="dtor"></a> ~task_handle

제거 된 `task_handle` 개체입니다.

```
~task_handle();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[task_group 클래스](task-group-class.md)<br/>
[structured_task_group 클래스](structured-task-group-class.md)

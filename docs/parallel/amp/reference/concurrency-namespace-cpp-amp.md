---
title: Concurrency 네임스페이스(C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: e0870eb046f1cec091a72d49c94a2fea41484340
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346041"
---
# <a name="concurrency-namespace-c-amp"></a>Concurrency 네임스페이스(C++ AMP)

클래스와 함수 실행을 가속화 하는 C++ 데이터 병렬 하드웨어의 코드입니다. 자세한 내용은 [ C++ AMP 개요](../cpp-amp-overview.md)

## <a name="syntax"></a>구문

```
namespace Concurrency;
```

## <a name="members"></a>멤버

### <a name="namespaces"></a>네임스페이스

|이름|설명|
|----------|-----------------|
|[Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)|D3D 상호 운용성을 지 원하는 함수를 제공 합니다. AMP 코드에서 계산을 위해 D3D 리소스를 원활 하 게 사용 및 중복 된 임시 사본을 만들지 않고도 AMP D3D 코드에서 만든 리소스의 사용 가능 합니다. 사용할 수 있습니다 C++ AMP 계산에서 생성 된 AMP가 증분 DirectX 응용 프로그램의 계산 집중적인 가속화 하 고 데이터에 D3D API를 사용 합니다.|
|[Concurrency::fast_math 네임스페이스](concurrency-fast-math-namespace.md)|함수는 `fast_math` 네임 스페이스는 C99 규격이 아닙니다. 각 함수의 단 정밀도 버전에만 제공 됩니다. 이러한 함수에서 해당 함수 보다 빠르며 DirectX 내장 함수를 사용 합니다 `precise_math` 네임 스페이스 및 액셀러레이터에 대해 확장 된 배정밀도 지원 하지 않아도 되지만 덜 정확 합니다. 두 가지 버전의 C99 코드를 사용 하 여 소스 수준 호환성을 위해 각 함수 버전을 모두 수행 하 고 단 정밀도 값을 반환 합니다.|
|[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)|그래픽 프로그래밍에 대 한 형식 및 설계 된 함수를 제공 합니다.|
|[Concurrency::precise_math 네임스페이스](concurrency-precise-math-namespace.md)|함수는 `precise_math` 네임 스페이스는 C99 규격입니다. 각 함수의 단 정밀도 및 배정밀도 버전이 포함 됩니다. 이러한 함수-여기에 단 정밀도 함수-액셀러레이터에서 확장 된 배정밀도 지원이 필요 합니다.|

### <a name="classes"></a>클래스

|이름|설명|
|----------|-----------------|
|[accelerator 클래스](accelerator-class.md)|실제 DP 최적화 계산 노드의 추상화를 나타냅니다.|
|[accelerator_view 클래스](accelerator-view-class.md)|가상 장치 추상화를 나타냅니다는 C++ AMP 데이터 병렬 가속기입니다.|
|[accelerator_view_removed 클래스](accelerator-view-removed-class.md)|Windows 시간 초과 검색-및 복구 메커니즘으로 인해 내부 DirectX 호출이 실패할 때 throw 되는 예외입니다.|
|[array 클래스](array-class.md)|집계 데이터는 `accelerator_view` 표 도메인에 있습니다. 표 도메인의 각 요소에 대 한 변수 컬렉션입니다. 일부에 해당 하는 값을 보유 하는 각 변수 C++ 형식입니다.|
|[array_view 클래스](array-view-class.md)|배열에서 데이터에 대 한 보기를 나타내는\<T, N >.|
|[completion_future 클래스](completion-future-class.md)|에 해당 하는 미래 나타냅니다는 C++ AMP 비동기 작업입니다.|
|[extent 클래스](extent-class.md)|원점이 0 N 차원 공간의 경계를 지정 하는 N 정수 값의 벡터를 나타냅니다. 좌표 벡터에서 값은 최상위에서 최하위 정렬 됩니다. 예를 들어, 데카르트 3 차원 공간에서 벡터 (7,5,3)는 0에서 7로 y 좌표 범위가 0 ~ 5, 범위는 z 좌표 및 x 좌표 0에서 3 사이의 공간을 나타냅니다.|
|[index 클래스](index-class.md)|N 차원 인덱스 포인트를 정의합니다.|
|[invalid_compute_domain 클래스](invalid-compute-domain-class.md)|런타임에서에서 지정 된 계산 도메인을 사용 하 여 커널을 시작할 수 없는 경우 throw 되는 예외는 `parallel_for_each` 호출 사이트입니다.|
|[out_of_memory 클래스](out-of-memory-class.md)|장치 또는 시스템 메모리 부족으로 인해 메서드가 실패할 때 throw 되는 예외입니다.|
|[runtime_exception 클래스](runtime-exception-class.md)|예외에 대 한 기본 형식 합니다 C++ AMP 라이브러리입니다.|
|[tile_barrier 클래스](tile-barrier-class.md)|시스템에서 만들 수 있는 전용 이며에 전달 되는 기능 클래스 바둑판식 `parallel_for_each` 의 일부로 람다는 `tiled_index` 매개 변수입니다. 한 가지 방법은 제공 `wait()`, 스레드 그룹 (타일)에서 실행 되는 스레드의 실행을 동기화 하는 합니다.|
|[tiled_extent 클래스](tiled-extent-class.md)|A `tiled_extent` 개체는 `extent` 공간을 1 차원, 2 차원 또는 3 차원 타일로 세분 하는 1 ~ 3 차원 개체입니다.|
|[tiled_index 클래스](tiled-index-class.md)|인덱스를 제공 된 `tiled_grid` 개체입니다. 이 클래스에는 로컬 타일 원본에 상대적인 및 전역 원본과 요소에 액세스 하는 속성에 있습니다.|
|[uninitialized_object 클래스](uninitialized-object-class.md)|초기화 되지 않은 개체를 사용 하는 경우 throw 되는 예외입니다.|
|[unsupported_feature 클래스](unsupported-feature-class.md)|지원 되지 않는 기능을 사용 하는 경우 throw 되는 예외입니다.|

### <a name="enumerations"></a>열거형

|이름|설명|
|----------|-----------------|
|[access_type 열거형](concurrency-namespace-enums-amp.md#access_type)|데이터 액세스 형식을 지정합니다.|
|[queuing_mode 열거형](concurrency-namespace-enums-amp.md#queuing_mode)|액셀러레이터 키에서 지원 되는 큐 모드를 지정 합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|--------------|-----------------|
|[연산자 = = 연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|지정된 된 데이터 구조가 같은지 여부를 결정 합니다.|
|[연산자! = 연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|지정된 된 데이터 구조가 같지 않은지 확인 합니다.|
|[operator + 연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|지정한 인수의 구성 요소별 합을 계산합니다.|
|[operator-연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|지정된 된 인수 사이의 구성 요소별 차이 계산합니다.|
|[operator * 연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|지정한 인수의 구성 요소별 곱을 계산합니다.|
|[operator / 연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|지정한 인수의 구성 요소별 몫을 계산합니다.|
|[operator % 연산자 (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|지정 된 두 번째 인수에 의해 지정 된 첫 번째 인수의 모듈러스를 계산 합니다.|

### <a name="functions"></a>함수

|이름|설명|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|모든 메모리 액세스가 완료 될 때까지 타일에서 모든 스레드의 실행을 차단 합니다.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|초기화를 취소 합니다 C++ AMP 런타임이 합니다.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|오버로드됨. 지정된 된 위치에 저장 된 값을 비교 하 여 첫 번째 지정 된 값과 같은 경우 지정된 된 두 번째 값은 원자 단위 연산으로 같은 위치에 저장 됩니다.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|오버로드됨. 원자 단위 연산으로 지정된 된 값으로 지정된 된 위치에 저장 된 값을 설정 합니다.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|오버로드됨. 원자 단위 연산으로 지정된 된 값과 값의 합계를 지정된 된 위치에 저장 된 값을 설정 합니다.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|오버로드됨. 비트 지정된 된 위치에 저장 된 값을 설정 하는 `and` 해당 값을 원자 단위 연산으로 지정 된 값입니다.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|오버로드됨. 감소 값을 지정된 된 위치에 저장 하 고 원자 단위 연산으로 같은 위치에 결과 저장 합니다.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|오버로드됨. 지정된 된 위치에 저장 된 값이 증가 하 고 원자 단위 연산으로 같은 위치에 결과 저장 합니다.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|오버로드됨. 더 큰 숫자 지정된 된 위치에 저장 된 값을 설정 하는 값을 원자 단위 연산으로 지정 된 값입니다.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|오버로드됨. 작은 값으로 지정된 된 위치에 저장 된 값을 설정 하는 값을 원자 단위 연산으로 지정 된 값입니다.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|오버로드됨. 비트 지정된 된 위치에 저장 된 값을 설정 하는 `or` 해당 값을 원자 단위 연산으로 지정 된 값입니다.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|오버로드됨. 원자 단위 연산으로 지정 된 값과의 차이 지정된 된 위치에 저장 된 값을 설정 합니다.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|오버로드됨. 비트 지정된 된 위치에 저장 된 값을 설정 하는 `xor` 해당 값을 원자 단위 연산으로 지정 된 값입니다.|
|[copy](concurrency-namespace-functions-amp.md#copy)|복사본을 C++ AMP 개체입니다. 모든 동기 데이터 전송 요구 사항이 충족 됩니다. 코드가 액셀러레이터 키에서 코드를 실행 하는 경우 데이터를 복사할 수 없습니다. 이 함수의 일반 형식은 `copy(src, dest)`합니다.|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|복사본을 C++ AMP 개체를 반환 합니다 [completion_future](completion-future-class.md) 는 대기할 수 있습니다. 액셀러레이터에서 코드를 실행 하는 경우 데이터를 복사할 수 없습니다. 이 함수의 일반 형식은 `copy(src, dest)`합니다.|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|에 함수의 실행을 중단 합니다 `restrict(amp)` 제한 절.|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Visual Studio로 서식이 지정 된 문자열을 출력 **출력** 창과 발생 한 [runtime_exception](runtime-exception-class.md) 예외는 동일한 서식을 갖습니다 하는 문자열입니다.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Visual Studio로 서식이 지정 된 문자열을 출력 **출력** 창입니다. 포함 된 함수에서 호출 되는 `restrict(amp)` 제한 절.|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|모든 전역 메모리 액세스가 때까지 타일에서 모든 스레드의 실행을 차단 완료 되었습니다.|
|[parallel_for_each 함수 (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|계산 도메인에서 함수를 실행 합니다.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|될 때까지 타일에서 모든 스레드의 실행을 차단 `tile_static` 메모리 액세스가 완료 되었습니다.|

## <a name="constants"></a>상수

|이름|설명|
|----------|-----------------|
|[HLSL_MAX_NUM_BUFFERS 상수](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Directx 로부터 허용 되는 버퍼의 최대 수입니다.|
|[MODULENAME_MAX_LENGTH 상수](concurrency-namespace-constants-amp.md#modulename_max_length)|모듈 이름의 최대 길이 저장합니다. 이 값은 컴파일러와 런타임에서 동일 해야 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

## <a name="see-also"></a>참고자료

[참조(C++ AMP)](reference-cpp-amp.md)

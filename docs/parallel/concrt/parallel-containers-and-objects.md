---
title: 병렬 컨테이너 및 개체
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: bcf3ead9fe945ecb2246fdb28b7f67cd51b1238b
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565950"
---
# <a name="parallel-containers-and-objects"></a>병렬 컨테이너 및 개체

병렬 패턴 라이브러리 (PPL) 여러 컨테이너 및 해당 요소에 스레드로부터 안전한 액세스를 제공 하는 개체를 포함 합니다.

A *동시 컨테이너* 가장 중요 한 작업에 대 한 동시성 으로부터 안전한 액세스를 제공 합니다. 이러한 컨테이너의 기능에는 c + + 표준 라이브러리에서 제공 되는 유사 합니다. 예를 들어,를 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스와 유사 합니다 [std:: vector](../../standard-library/vector-class.md) 는 점을 제외 하면 클래스를 `concurrent_vector` 클래스를 사용 하면 요소를에서 추가 합니다. 읽기와 동일한 컨테이너에 대 한 쓰기 액세스를 필요로 하는 병렬 코드를 해야 하는 경우 동시 컨테이너를 사용 합니다.

A *동시 개체* 동시에 구성 요소 간에 공유 됩니다. 병렬로 동시 개체의 상태를 계산 하는 프로세스는 동일한 상태를 순차적으로 계산 하는 다른 프로세스와 동일한 결과 생성 합니다. 합니다 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스는 동시 개체 형식의 한 가지 예입니다. `combinable` 클래스를 사용 하면 병렬에서 계산을 수행 하 고 그런 다음 이러한 계산을 최종 결과로 결합 합니다. 그렇지 않은 경우 예를 들어, 뮤텍스 동기화 메커니즘을 공유 변수 또는 리소스에 대 한 액세스를 동기화 하는 데 사용 하는 경우 동시 개체를 사용 합니다.

##  <a name="top"></a> 섹션

이 항목에서는 다음 병렬 컨테이너 및 개체를 자세히 설명 합니다.

동시 컨테이너:

- [concurrent_vector 클래스](#vector)

   - [Concurrent_vector 차이점 및 벡터](#vector-differences)

   - [동시성 으로부터 안전한 작업](#vector-safety)

   - [예외 안전성](#vector-exceptions)

- [concurrent_queue 클래스](#queue)

   - [Concurrent_queue 차이점 및 큐](#queue-differences)

   - [동시성 으로부터 안전한 작업](#queue-safety)

   - [반복기 지원](#queue-iterators)

- [concurrent_unordered_map 클래스](#unordered_map)

   - [Concurrent_unordered_map 차이점 및 unordered_map](#map-differences)

   - [동시성 으로부터 안전한 작업](#map-safety)

- [concurrent_unordered_multimap 클래스](#unordered_multimap)

- [concurrent_unordered_set 클래스](#unordered_set)

- [concurrent_unordered_multiset 클래스](#unordered_multiset)

동시 개체:

- [combinable 클래스](#combinable)

   - [메서드 및 기능](#combinable-features)

   - [예제](#combinable-examples)

##  <a name="vector"></a> concurrent_vector 클래스

합니다 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스는 마찬가지로 하는 시퀀스 컨테이너 클래스는 [std:: vector](../../standard-library/vector-class.md) 클래스, 해당 요소에 임의로 액세스할 수 있습니다. `concurrent_vector` 클래스를 사용 하면 동시성 으로부터 안전한 추가 및 요소 작업에 액세스 합니다. 추가 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 반복기 액세스 및 순회 작업 동시성 으로부터 안전한도 합니다.

###  <a name="vector-differences"></a> Concurrent_vector 차이점 및 벡터

합니다 `concurrent_vector` 유사 합니다 `vector` 클래스입니다. 추가, 요소 액세스 및 반복기 액세스 작업의 복잡성을 `concurrent_vector` 개체와 동일을 `vector` 개체입니다. 다음 사항에 대 한 설명입니다 `concurrent_vector` 에서 다른 `vector`:

- 추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업을 `concurrent_vector` 개체는 동시성 으로부터 안전한 합니다.

- 요소 끝에만 추가할 수 있습니다는 `concurrent_vector` 개체입니다. 합니다 `concurrent_vector` 클래스를 제공 하지 않습니다는 `insert` 메서드.

- A `concurrent_vector` 개체를 사용 하지 않는 [의미 체계 이동](../../cpp/rvalue-reference-declarator-amp-amp.md) 에 추가 하는 경우.

- 합니다 `concurrent_vector` 클래스를 제공 하지 않습니다 합니다 `erase` 또는 `pop_back` 메서드. 와 마찬가지로 `vector`를 사용 합니다 [의 선택을 취소](reference/concurrent-vector-class.md#clear) 에서 모든 요소를 제거 하는 방법을 `concurrent_vector` 개체.

- `concurrent_vector` 클래스 메모리의 해당 요소를 연속적으로 저장 하지는 않습니다. 따라서 사용할 수 없습니다는 `concurrent_vector` 배열을 사용할 수 있는 모든 방식에서 클래스. 명명 된 변수에 대 한 예를 들어 `v` 형식의 `concurrent_vector`, 식 `&v[0]+2` 정의 되지 않은 동작이 발생 합니다.

- `concurrent_vector` 클래스를 정의 합니다 [grow_by](reference/concurrent-vector-class.md#grow_by) 하 고 [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) 메서드. 이러한 메서드 유사 합니다 [크기 조정](reference/concurrent-vector-class.md#resize) 메서드를 동시성 으로부터 안전한은 점을 제외 하 고 합니다.

- `concurrent_vector` 를 추가 하거나 크기를 조정 하는 경우 개체는 해당 요소 옮기지 않습니다. 이렇게 하면 기존 포인터 및 반복기 동시 작업 하는 동안 유효 하도록 합니다.

- 런타임에서의 특수 버전을 정의 하지 않습니다 `concurrent_vector` 형식에 대 한 `bool`합니다.

###  <a name="vector-safety"></a> 동시성 으로부터 안전한 작업

크기를 늘리거나에 추가 하는 모든 메서드를 `concurrent_vector` 개체 또는 요소에 액세스를 `concurrent_vector` 개체, 동시성 으로부터 안전한 됩니다. 이 규칙의 예외는 `resize` 메서드.

다음 표에서 일반적인 `concurrent_vector` 메서드 및 연산자는 동시성이 보장 됩니다.

||||
|-|-|-|
|[at](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[begin](reference/concurrent-vector-class.md#begin)|[front](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[back](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[capacity](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[size](reference/concurrent-vector-class.md#size)|

예를 들어, 런타임에 c + + 표준 라이브러리를 사용 하 여 호환성을 위해 제공 하는 작업 `reserve`, 동시성 안전 하지 않습니다. 다음 표에서 일반 메서드 및 동시성이 보장 되지 않는 연산자를 보여 줍니다.

|||
|-|-|
|[assign](reference/concurrent-vector-class.md#assign)|[reserve](reference/concurrent-vector-class.md#reserve)|
|[clear](reference/concurrent-vector-class.md#clear)|[resize](reference/concurrent-vector-class.md#resize)|
|[operator=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

기존 요소의 값을 수정 하는 동시성 으로부터 안전한 않습니다. 와 같은 동기화 개체를 사용 하 여는 [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 개체 동기화 동시 읽기 및 쓰기 작업을 동일한 데이터 요소입니다. 동기화 개체에 대 한 자세한 내용은 참조 하십시오 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)합니다.

사용 하는 기존 코드를 변환 하는 경우 `vector` 데 `concurrent_vector`, 동시 작업 변경 하려면 응용 프로그램의 동작을 발생할 수 있습니다. 예를 들어 동시에 두 가지 작업을 수행 하는 다음 프로그램을 `concurrent_vector` 개체입니다. 첫 번째 작업에 요소를 추가 `concurrent_vector` 개체입니다. 두 번째 작업은 동일한 개체에 있는 모든 요소의 합계를 계산합니다.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

하지만 `end` 메서드는 동시성 으로부터 안전한 동시 호출을 [push_back](reference/concurrent-vector-class.md#push_back) 메서드를 사용 하면 반환 되는 값 `end` 변경 하려면. 반복기에서 트래버스하는 요소의 수를 확정적이 지 않습니다. 따라서이 프로그램 다른 결과 실행할 때마다 생성할 수 있습니다.

###  <a name="vector-exceptions"></a> 예외 안전성

증가 또는 할당 작업의 상태 예외를 throw 하는 경우는 `concurrent_vector` 개체는 무효가 됩니다. 동작을 `concurrent_vector` 달리 명시 하지 않는 한 잘못 된 상태에 있는 개체 정의 되지 않습니다. 그러나 소멸자가 항상 메모리를 해제 개체 할당 하는 개체가 잘못 된 상태인 경우에 합니다.

벡터 요소의 데이터 형식을 `T`, 다음 요구 사항을 충족 해야 합니다. 이 고, 그렇지의 동작을 `concurrent_vector` 클래스 정의 되지 않습니다.

- 소멸자가 throw 하면 안 됩니다.

- 기본 또는 복사 생성자에서 throw를 사용 하 여 소멸자가 선언 되지 않아야 합니다 `virtual` 키워드 하며 0으로 초기화 하는 메모리를 사용 하 여 제대로 작동 해야 합니다.

[[맨 위로 이동](#top)]

##  <a name="queue"></a> concurrent_queue 클래스

합니다 [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 클래스와 동일 하 게 합니다 [std::queue](../../standard-library/queue-class.md) 클래스를 사용 하면 앞면이 액세스 하 고 요소를 다시 합니다. `concurrent_queue` 클래스 하면 동시성 으로부터 안전한 큐에 넣기 및 큐에서 제거 작업 합니다. `concurrent_queue` 클래스 동시성 안전 하지 않은 반복기 지원도 제공 합니다.

###  <a name="queue-differences"></a> Concurrent_queue 차이점 및 큐

합니다 `concurrent_queue` 유사 합니다 `queue` 클래스입니다. 다음 사항에 대 한 설명입니다 `concurrent_queue` 에서 다른 `queue`:

- 큐에 넣기 및 큐에서 제거 작업에는 `concurrent_queue` 개체는 동시성 으로부터 안전한 합니다.

- `concurrent_queue` 클래스는 동시성 으로부터 안전한 하지 않은 반복기 지원을 제공 합니다.

- 합니다 `concurrent_queue` 클래스를 제공 하지 않습니다 합니다 `front` 또는 `pop` 메서드. 합니다 `concurrent_queue` 클래스를 정의 하 여 이러한 메서드를 대체 합니다 [try_pop](reference/concurrent-queue-class.md#try_pop) 메서드.

- 합니다 `concurrent_queue` 클래스를 제공 하지 않습니다는 `back` 메서드. 따라서 큐의 끝을 참조할 수 없습니다.

- 합니다 `concurrent_queue` 클래스를 제공 합니다 [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) 메서드 대신는 `size` 메서드. `unsafe_size` 메서드는 동시성이 보장 되지 않습니다.

###  <a name="queue-safety"></a> 동시성 으로부터 안전한 작업

모든 메서드를 해당 큐에 넣기 또는에서 큐에서 제거를 `concurrent_queue` 개체는 동시성 으로부터 안전한 합니다.

다음 표에서 일반적인 `concurrent_queue` 메서드 및 연산자는 동시성이 보장 됩니다.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

하지만 합니다 `empty` 메서드는 동시성 으로부터 안전한, 동시 작업을 수행 하기 전에 늘리거나 큐 않을 수 있습니다는 `empty` 메서드 반환 합니다.

다음 표에서 일반 메서드 및 동시성이 보장 되지 않는 연산자를 보여 줍니다.

|||
|-|-|
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

###  <a name="queue-iterators"></a> 반복기 지원

`concurrent_queue` 동시성 안전 하지 않은 반복기를 제공 합니다. 이러한 반복기 디버깅 용도로 사용 하는 것이 좋습니다.

`concurrent_queue` 반복기만 앞쪽으로 요소를 통과 합니다. 다음 표에서 각 반복기 지 연산자를 보여 줍니다.

|연산자|설명|
|--------------|-----------------|
|`operator++`|큐의 다음 항목으로 이동 합니다. 이 연산자는 사전 증가 및 사후 증가 모두 의미 체계를 제공 하도록 오버 로드 합니다.|
|`operator*`|현재 항목에 대 한 참조를 검색합니다.|
|`operator->`|현재 항목에 대 한 포인터를 검색합니다.|

[[맨 위로 이동](#top)]

##  <a name="unordered_map"></a> concurrent_unordered_map 클래스

합니다 [concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) 클래스는 마찬가지로 하는 결합형 컨테이너 클래스는 [std:: unordered_map](../../standard-library/unordered-map-class.md) 클래스, 다양 한 길이의 형식의요소시퀀스를제어[std:: pair\<const Key, Ty >](../../standard-library/pair-structure.md)합니다. 에 키 / 값 쌍을 추가 하거나 키로 값을 조회할 수 있는 사전으로 순서가 지정 되지 않은 맵의 생각 합니다. 이 클래스는 여러 스레드 또는 동시에 공유 컨테이너에 액세스, 삽입, 또는 업데이트 하는 작업이 있는 경우에 유용 합니다.

다음 예제에서는 사용에 대 한 기본 구조를 보여 줍니다. `concurrent_unordered_map`합니다. 이 예제에서는 ['a', ' i'] 범위의 문자 키를 삽입 합니다. 작업의 순서를 알 수 없는 때문에 각 키에 대 한 최종 값은도 결정 합니다. 그러나 동시에 삽입 하는 데 안전 합니다.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

사용 하는 예로 `concurrent_unordered_map` 를 매핑 수행 및 줄이기 병렬로 작업을 참조 하세요. [방법: 매핑 수행 및 병렬 작업 줄이기](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)합니다.

###  <a name="map-differences"></a> Concurrent_unordered_map 차이점 및 unordered_map

합니다 `concurrent_unordered_map` 유사 합니다 `unordered_map` 클래스입니다. 다음 사항에 대 한 설명입니다 `concurrent_unordered_map` 에서 다른 `unordered_map`:

- `erase`, `bucket`, `bucket_count`, 및 `bucket_size` 메서드 이름은 `unsafe_erase`를 `unsafe_bucket`를 `unsafe_bucket_count`, 및 `unsafe_bucket_size`각각. `unsafe_` 명명 규칙 이러한 메서드는 동시성 으로부터 안전한 나타냅니다. 동시성 안전에 대 한 자세한 내용은 참조 하세요. [동시성 으로부터 안전한 작업](#map-safety)합니다.

- 삽입 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다 또는 지도에 이미 있는 항목의 순서 변경 수행 합니다. 삽입 및 이동 작업을 동시에 발생할 수 있습니다.

- `concurrent_unordered_map` 지 원하는 반복만 전달합니다.

- 삽입을 무효화 하지 않거나 업데이트에 의해 반환 된 반복기 `equal_range`합니다. 삽입 범위의 끝에 같지 않은 항목을 추가할 수 있습니다. 시작 하는 반복기는 같은 항목을 가리킵니다.

없는 메서드의 교착 상태가 발생 하지 않도록 하려면 `concurrent_unordered_map` 메모리 할당자, 해시 함수 또는 다른 사용자 정의 코드를 호출할 때 잠금을 보유 합니다. 또한 동일한 값으로 동일한 키에 해시 함수는 항상 평가 해야 합니다. 가장 좋은 해시 함수 키 해시 코드 공간에서 균일 하 게 배포.

###  <a name="map-safety"></a> 동시성 으로부터 안전한 작업

`concurrent_unordered_map` 클래스 동시성 으로부터 안전한 insert 및 요소 액세스 작업을 실행할 수 있습니다. 삽입 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 반복기 액세스 및 순회 작업 동시성 으로부터 안전한도 합니다. 다음 표에서 일반적으로 사용 되는 `concurrent_unordered_map` 메서드 및 연산자는 동시성이 보장 됩니다.

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|

하지만 `count` 스레드를 동시에 실행 메서드를 안전 하 게 호출할 수 있습니다, 다른 스레드는 새 값을 삽입 하는 동시에 컨테이너로 경우 다른 결과 받을 수 있습니다.

다음 표에서 자주 사용 되는 메서드 및 동시성이 보장 되지 않는 연산자를 보여 줍니다.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq)

이러한 방법 외에도 모든 메서드는 시작 `unsafe_` 동시성 으로부터 안전한 하지 이기도 합니다.

[[맨 위로 이동](#top)]

##  <a name="unordered_multimap"></a> concurrent_unordered_multimap 클래스

[concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) 유사 합니다 `concurrent_unordered_map` 제외 하 고 여러 값을 동일한 키에 매핑할 수 있도록 클래스입니다. 또한에서 다른 `concurrent_unordered_map` 다음과 같은 방법으로:

- 합니다 [concurrent_unordered_multimap:: insert](reference/concurrent-unordered-multimap-class.md#insert) 대신 반복기를 반환 하는 메서드 `std::pair<iterator, bool>`합니다.

- 합니다 `concurrent_unordered_multimap` 클래스를 제공 하지 않습니다 `operator[]` 또는 `at` 메서드.

다음 예제에서는 사용에 대 한 기본 구조를 보여 줍니다. `concurrent_unordered_multimap`합니다. 이 예제에서는 ['a', ' i'] 범위의 문자 키를 삽입 합니다. `concurrent_unordered_multimap` 여러 값이 있는 키를 사용 하도록 설정 합니다.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[맨 위로 이동](#top)]

##  <a name="unordered_set"></a> concurrent_unordered_set 클래스

[concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) 유사 합니다 `concurrent_unordered_map` 키 / 값 쌍이 아닌 값을 관리 한다는 클래스입니다. 합니다 `concurrent_unordered_set` 클래스를 제공 하지 않습니다 `operator[]` 또는 `at` 메서드.

다음 예제에서는 사용에 대 한 기본 구조를 보여 줍니다. `concurrent_unordered_set`합니다. 이 예제에서는 ['a', ' i'] 범위의 문자 값을 삽입 합니다. 병렬에서 삽입을 수행 해도 됩니다.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[맨 위로 이동](#top)]

##  <a name="unordered_multiset"></a> concurrent_unordered_multiset 클래스

합니다 [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) 유사 합니다 `concurrent_unordered_set` 중복 값을 허용 하는 점을 제외 하 고 클래스입니다. 또한에서 다른 `concurrent_unordered_set` 다음과 같은 방법으로:

- 합니다 [concurrent_unordered_multiset:: insert](reference/concurrent-unordered-multiset-class.md#insert) 대신 반복기를 반환 하는 메서드 `std::pair<iterator, bool>`합니다.

- 합니다 `concurrent_unordered_multiset` 클래스를 제공 하지 않습니다 `operator[]` 또는 `at` 메서드.

다음 예제에서는 사용에 대 한 기본 구조를 보여 줍니다. `concurrent_unordered_multiset`합니다. 이 예제에서는 ['a', ' i'] 범위의 문자 값을 삽입 합니다. `concurrent_unordered_multiset` 값을을 여러 번 발생할 수 있습니다.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[맨 위로 이동](#top)]

##  <a name="combinable"></a> combinable 클래스

합니다 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스는 세분화 된 계산을 수행 하 고 이러한 계산을 최종 결과로 병합할 수 있는 재사용 가능한, 스레드 로컬 저장소를 제공 합니다. `combinable` 개체는 환산(reduction) 변수로 간주될 수 있습니다.

`combinable` 클래스는 여러 스레드 또는 작업 간에 공유 되는 리소스가 있는 경우에 유용 합니다. `combinable` 클래스를 사용 하면 잠금 해제 하는 방식으로 공유 리소스에 대 한 액세스를 제공 하 여 공유 상태를 제거 합니다. 따라서이 클래스는 예를 들어, 뮤텍스 동기화 메커니즘을 사용 하 여 여러 스레드에서 공유 데이터에 대 한 액세스를 동기화 하는 대신을 제공 합니다.

###  <a name="combinable-features"></a> 메서드 및 기능

다음 표에의 중요 한 메서드 중 일부는 `combinable` 클래스입니다. 모든 대 한 자세한 내용은 합니다 `combinable` 클래스 메서드를 참조 하십시오 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)합니다.

|메서드|설명|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|현재 스레드 컨텍스트를 사용 하 여 연결 된 로컬 변수에 대 한 참조를 검색 합니다.|
|[clear](reference/combinable-class.md#clear)|모든 스레드 지역 변수를 제거 합니다 `combinable` 개체입니다.|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|제공 된 결합 함수를 사용 하 여 모든 스레드 로컬 계산 집합에서 마지막 값을 생성 합니다.|

`combinable` 클래스는 병합 된 최종 결과 대해 매개 변수가 있는 템플릿 클래스입니다. 기본 생성자를 호출 하는 경우는 `T` 템플릿 매개 변수 형식 기본 생성자 및 복사 생성자가 있어야 합니다. 경우는 `T` 템플릿 매개 변수 형식이 없는 기본 생성자에서 초기화 함수를 매개 변수로 사용 하는 생성자의 오버 로드 된 버전을 호출 합니다.

추가 데이터를 저장할 수는 `combinable` 호출한 후 개체를 [결합](reference/combinable-class.md#combine) 또는 [combine_each](reference/combinable-class.md#combine_each) 메서드. 호출할 수도 있습니다는 `combine` 고 `combine_each` 메서드를 여러 번입니다. 경우 로컬 값을 `combinable` 변경 내용을 개체를 `combine` 및 `combine_each` 메서드 호출 될 때마다 동일한 결과 생성 합니다.

###  <a name="combinable-examples"></a> 예제

사용 하는 방법에 대 한 예제는 `combinable` 클래스에 다음 항목을 참조 하십시오.

- [방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [방법: combinable을 사용하여 세트 결합](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[맨 위로 이동](#top)]

## <a name="related-topics"></a>관련 항목

[방법: 병렬 컨테이너를 사용하여 효율성 향상](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
병렬 컨테이너를 효율적으로 저장 하 고 데이터를 병렬로 액세스를 사용 하는 방법을 보여 줍니다.

[방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
사용 하는 방법을 보여 줍니다는 `combinable` 클래스 공유 상태를 제거 하 고 성능을 향상 시키는 합니다.

[방법: combinable을 사용하여 세트 결합](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
사용 하는 방법을 보여 줍니다는 `combine` 스레드 로컬 데이터 집합을 병합 하는 함수입니다.

[PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
동시 응용 프로그램을 개발 하기 위한 사용 편의성과 확장성을 높이 명령적 프로그래밍 모델을 제공 하는 PPL에 설명 합니다.

## <a name="reference"></a>참조

[concurrent_vector 클래스](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue 클래스](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map 클래스](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap 클래스](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set 클래스](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset 클래스](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable 클래스](../../parallel/concrt/reference/combinable-class.md)

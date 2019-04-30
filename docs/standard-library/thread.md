---
title: '&lt;thread&gt;'
ms.date: 11/04/2016
f1_keywords:
- <thread>
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
ms.openlocfilehash: 43fb79ceda6de7409e6f93797ce2f4ff213c43ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411983"
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

표준 헤더 포함 \<스레드 > 클래스를 정의 하 **스레드** 및 다양 한 지원 기능입니다.

## <a name="syntax"></a>구문

```cpp
#include <thread>
```

## <a name="remarks"></a>설명

> [!NOTE]
> 코드를 사용 하 여 컴파일된 **/clr**,이 헤더가 차단 됩니다.

`__STDCPP_THREADS__` 매크로가 스레드가이 헤더에 의해 지원 되는 표시에 0이 아닌 값으로 정의 됩니다.

## <a name="members"></a>멤버

### <a name="public-classes"></a>public 클래스

|이름|설명|
|----------|-----------------|
|[thread 클래스](../standard-library/thread-class.md)|관찰 하 고 응용 프로그램의 실행 스레드를 관리 하는 데 사용 되는 개체를 정의 합니다.|

### <a name="public-structures"></a>공용 구조체

|이름|설명|
|----------|-----------------|
|[hash 구조체(C++ 표준 라이브러리)](../standard-library/hash-structure-stl.md)|고유 하 게 결정 되는 값을 반환 하는 멤버 함수는 `thread::id`합니다. 멤버 함수 정의 [해시](../standard-library/hash-class.md) 매핑 값 형식에 적합 한 함수 `thread::id` 인덱스 값의 분포에 있습니다.|

### <a name="public-functions"></a>공용 함수

|이름|설명|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|현재 실행 스레드를 고유하게 식별합니다.|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|호출 스레드를 차단합니다.|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|최소한 지정된 시간까지 호출 스레드를 차단합니다.|
|[swap](../standard-library/thread-functions.md#swap)|두 개의 상태 교환 **스레드** 개체입니다.|
|[yield](../standard-library/thread-functions.md#yield)|정상적인 경우라면 현재 스레드가 계속 실행되더라도 운영 체제에 다른 스레드를 실행할 것을 알립니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[연산자 > = 연산자](../standard-library/thread-operators.md#op_gt_eq)|하나의 `thread::id` 개체가 다른 개체보다 크거나 같은지를 확인합니다.|
|[연산자 > 연산자](../standard-library/thread-operators.md#op_gt)|하나의 `thread::id` 개체가 다른 개체보다 큰지를 확인합니다.|
|[연산자 < = 연산자](../standard-library/thread-operators.md#op_lt_eq)|하나의 `thread::id` 개체가 다른 개체보다 작거나 같은지를 확인합니다.|
|[연산자 < 연산자](../standard-library/thread-operators.md#op_lt)|하나의 `thread::id` 개체가 다른 개체보다 작은지를 확인합니다.|
|[연산자! = 연산자](../standard-library/thread-operators.md#op_neq)|두 `thread::id` 개체가 다른지 비교합니다.|
|[연산자 = = 연산자](../standard-library/thread-operators.md#op_eq_eq)|두 `thread::id` 개체가 같은지 비교합니다.|
|[연산자 << 연산자](../standard-library/thread-operators.md#op_lt_lt)|`thread::id` 개체의 텍스트 표현을 스트림에 삽입합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

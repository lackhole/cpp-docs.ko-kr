---
title: tile_barrier 클래스
ms.date: 03/27/2019
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
ms.openlocfilehash: f0e742a0cc1a0809fc08b3862cadb7e3deb36fa8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351510"
---
# <a name="tilebarrier-class"></a>tile_barrier 클래스

사용 하 여 스레드 그룹 (타일)에서 실행 되는 스레드의 동기화 `wait` 메서드. 런타임만이 클래스를 인스턴스화할 수 있습니다.

### <a name="syntax"></a>구문

```
class tile_barrier;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[tile_barrier 생성자](#ctor)|`tile_barrier` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[wait](#wait)|있는 모든 스레드가 스레드 그룹 (타일) 타일에 있는 모든 스레드가 대기를 완료할 때까지 실행을 중지 하도록 지시 합니다.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|모든 메모리 액세스가 완료 될 때까지 타일에 있는 모든 스레드가 및 타일에서 모든 스레드의 실행을 차단에는이 호출에 도달 했습니다.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|타일에 있는 모든 스레드가이 호출에 도달한 모든 전역 메모리 액세스가 완료 될 때까지 타일에서 모든 스레드의 실행을 차단 합니다.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|모든 타일에서 모든 스레드의 실행을 차단 `tile_static` 메모리 액세스가 완료 되 고 타일에 있는 모든 스레드가이 호출에 도달 했습니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tile_barrier`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="ctor"></a>  tile_barrier 생성자

기존 항목을 복사 하 여 클래스의 새 인스턴스를 초기화 합니다.

### <a name="syntax"></a>구문

```
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`tile_barrier` 복사할 개체입니다.

## <a name="wait"></a>대기

타일에 있는 모든 스레드가 대기를 완료할 때까지 스레드 그룹(타일)에 있는 모든 스레드의 실행을 중지하도록 지시합니다.

### <a name="syntax"></a>구문

```
void wait() const restrict(amp);
```

## <a name="waitwithallmemoryfence"></a>wait_with_all_memory_fence

타일의 모든 스레드가이 호출에 도달 될 때까지 타일에서 모든 스레드의 실행을 차단 합니다. 이렇게 하면 모든 메모리 액세스가 스레드 타일의 다른 스레드에 표시 되며 프로그램 순서로 실행 되었습니다.

### <a name="syntax"></a>구문

```
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="waitwithglobalmemoryfence"></a>wait_with_global_memory_fence

타일의 모든 스레드가이 호출에 도달 될 때까지 타일에서 모든 스레드의 실행을 차단 합니다. 이렇게 하면 모든 전역 메모리 액세스가 스레드 타일의 다른 스레드에 표시 되며 프로그램 순서로 실행 되었습니다.

### <a name="syntax"></a>구문

```
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="waitwithtilestaticmemoryfence"></a>wait_with_tile_static_memory_fence

타일의 모든 스레드가이 호출에 도달 될 때까지 타일에서 모든 스레드의 실행을 차단 합니다. 이렇게 하면 `tile_static` 메모리 액세스가 스레드 타일의 다른 스레드에 표시 되며 프로그램 순서로 실행 되었습니다.

### <a name="syntax"></a>구문

```
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)

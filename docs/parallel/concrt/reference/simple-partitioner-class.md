---
title: simple_partitioner 클래스
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 372773926903da32f1690904b34cd143a04940dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337247"
---
# <a name="simplepartitioner-class"></a>simple_partitioner 클래스

`simple_partitioner` 클래스는 `parallel_for`에서 반복하는 범위의 정적 분할을 나타냅니다. 파티셔너는 각 청크에 적어도 청크 크기로 지정된 개수의 반복이 있도록 범위를 청크로 나눕니다.

## <a name="syntax"></a>구문

```
class simple_partitioner;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[simple_partitioner](#ctor)|`simple_partitioner` 개체를 생성합니다.|
|[~ simple_partitioner 소멸자](#dtor)|`simple_partitioner` 개체를 제거합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`simple_partitioner`

## <a name="requirements"></a>요구 사항

**헤더:** ppl.h

**네임스페이스:** 동시성

##  <a name="dtor"></a> ~simple_partitioner

`simple_partitioner` 개체를 제거합니다.

```
~simple_partitioner();
```

##  <a name="ctor"></a> simple_partitioner

`simple_partitioner` 개체를 생성합니다.

```
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>매개 변수

*_Chunk_size*<br/>
최소 파티션 크기입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)

---
title: scoped_d3d_access_lock 클래스
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: e36c3c2cfa9d1b617e377a7e340f98875457bdf1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352873"
---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock 클래스

Accelerator_view 개체에 대 한 D3D 액세스 잠금에 대 한 RAII 래퍼.

### <a name="syntax"></a>구문

```
class scoped_d3d_access_lock;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[scoped_d3d_access_lock 생성자](#ctor)|오버로드됨. `scoped_d3d_access_lock` 개체를 생성합니다. 이 개체가 범위를 벗어날 때 잠금이 해제 됩니다.|
|[~ scoped_d3d_access_lock 소멸자](#dtor)|연결 된 D3D 액세스 잠금을 해제 `accelerator_view` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator=](#operator_eq)|다른 잠금 소유권 `scoped_d3d_access_lock`합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`scoped_d3d_access_lock`

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**Namespace:** concurrency::direct3d

##  <a name="ctor"></a> scoped_d3d_access_lock

`scoped_d3d_access_lock` 개체를 생성합니다. 이 개체가 범위를 벗어날 때 잠금이 해제 됩니다.

```
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>매개 변수

*_Av*<br/>
`accelerator_view` 잠금을 채택할 수에 대 한 합니다.

*_T*<br/>
`adopt_d3d_access_lock_t` 개체

*_Other*<br/>
`scoped_d3d_access_lock` 기존 잠금으로 이동할 수 있는 개체입니다.

## <a name="construction"></a>생성

[1] 생성자에서 D3D 액세스 잠금을 획득는 주어진 [accelerator_view](accelerator-view-class.md) 개체입니다. 잠금을 가져올 때까지 요소를 생성 합니다.

[2] 생성자에서 D3D 액세스 잠금을 채택는 주어진 [accelerator_view](accelerator-view-class.md) 개체입니다.

[3] 이동 생성자 간에 기존 D3D 액세스 잠금을 `scoped_d3d_access_lock` 개체입니다. 생성을 차단 하지 않습니다.

##  <a name="dtor"></a> ~scoped_d3d_access_lock

연결 된 D3D 액세스 잠금을 해제 `accelerator_view` 개체입니다.

```
~scoped_d3d_access_lock();
```

## <a name="operator_eq"></a> operator=

다른 D3D 액세스 잠금 소유권 `scoped_d3d_access_lock` 개체에서 이전 잠금을 해제 합니다.

```
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
D3D 액세스 잠금을 이동할 수 있는 accelerator_view입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `scoped_accelerator_view_lock`합니다.

## <a name="see-also"></a>참고자료

[Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)

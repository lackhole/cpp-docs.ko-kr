---
title: unorm 클래스
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: 059cd3a388d67e540a91146f2a287c375fb02bd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405432"
---
# <a name="unorm-class"></a>unorm 클래스

Unorm 수를 나타냅니다. 각 요소는 부동 소수점 [0.0f, 1.0f] 범위의 숫자입니다.

## <a name="syntax"></a>구문

```
class unorm;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[unorm 생성자](#ctor)|오버로드됨. 기본 생성자입니다. 0.0f로 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|unorm::operator--||
|unorm::operator float|변환 연산자입니다. Unorm 번호 변환 부동 소수점 값입니다.|
|unorm::operator*=||
|unorm::operator/=||
|unorm::operator++||
|unorm::operator+=||
|unorm::operator=||
|unorm::operator-=||

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`unorm`

## <a name="requirements"></a>요구 사항

**헤더:** amp_short_vectors.h

**네임스페이스:** Concurrency:: graphics

##  <a name="ctor"></a> unorm

기본 생성자입니다. 0.0f로 초기화합니다.

```
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>매개 변수

*_V*<br/>
초기화할 때 사용되는 값입니다.

*_Other*<br/>
초기화하는 데 사용되는 일반 개체입니다.

## <a name="see-also"></a>참고자료

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)

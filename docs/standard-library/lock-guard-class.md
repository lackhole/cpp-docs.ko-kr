---
title: lock_guard 클래스
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: 45a01c5fdd431bcfad1eeb5ab0531c11c89e9767
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413140"
---
# <a name="lockguard-class"></a>lock_guard 클래스

소멸자가 `mutex`의 잠금을 해제하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>설명

템플릿 인수 `Mutex`는 *뮤텍스 형식*의 이름을 지정해야 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`lock_guard::mutex_type`|템플릿 인수 `Mutex`에 대한 동의어입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[lock_guard](#lock_guard)|`lock_guard` 개체를 생성합니다.|
|[lock_guard::~lock_guard 소멸자](#dtorlock_guard_destructor)|생성자에 전달된 `mutex`를 잠금 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<뮤텍스 >

**네임스페이스:** std

## <a name="lock_guard"></a>  lock_guard::lock_guard 생성자

`lock_guard` 개체를 생성합니다.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>매개 변수

*Mtx*<br/>
*뮤텍스 형식* 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 형식의 개체를 생성 `lock_guard` 및 잠금 *Mtx*합니다. 하는 경우 *Mtx* 재귀 뮤텍스가 없는 잠금 해제 해야이 생성자를 호출할 때.

두 번째 생성자는 잠그지 않음 *Mtx*합니다. *Mtx* 이 생성자를 호출할 때 잠겨 있어야 합니다. 생성자는 예외를 throw하지 않습니다.

## <a name="dtorlock_guard_destructor"></a>  lock_guard::~lock_guard 소멸자

생성자에 전달된 `mutex`를 잠금 해제합니다.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>설명

소멸자가 실행될 때 `mutex`가 없으면 동작이 정의되지 않습니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>

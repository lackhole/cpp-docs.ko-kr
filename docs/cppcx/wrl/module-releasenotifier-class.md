---
title: Module::ReleaseNotifier 클래스
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: 5fc1b8965bf8bf2f86dd30f2195fa825f85f6d7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403258"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier 클래스

모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다.

## <a name="syntax"></a>구문

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                                                | 설명
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module::ReleaseNotifier::~ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | 현재 인스턴스를 초기화 해제는 `Module::ReleaseNotifier` 클래스입니다.
[Module::ReleaseNotifier::ReleaseNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                                                         | 설명
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module::ReleaseNotifier::Invoke](#releasenotifier-invoke)   | 구현될 때 모듈의 마지막 개체가 해제되면 이벤트 처리기를 호출합니다.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | 현재 삭제 `Module::ReleaseNotifier` 개체의 매개 변수를 사용 하 여 생성 된 개체 **true**합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ReleaseNotifier`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module::ReleaseNotifier::~ReleaseNotifier

현재 인스턴스를 초기화 해제는 `Module::ReleaseNotifier` 클래스입니다.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module::ReleaseNotifier::Invoke

구현될 때 모듈의 마지막 개체가 해제되면 이벤트 처리기를 호출합니다.

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Module::ReleaseNotifier::Release

현재 삭제 `Module::ReleaseNotifier` 개체의 매개 변수를 사용 하 여 생성 된 개체 **true**합니다.

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Module::ReleaseNotifier::ReleaseNotifier

`Module::ReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>매개 변수

*release*<br/>
`true` 삭제 하려면이 인스턴스에 `Release` 메서드 호출 됩니다. `false` 이 인스턴스를 삭제 하지 않도록 합니다.

---
title: ClassFactory 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: ccc1c43e8c68053a773883c25704cdea086bd0b1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784834"
---
# <a name="classfactory-class"></a>ClassFactory 클래스

`IClassFactory` 인터페이스의 기본 기능을 구현합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
0 번째 인터페이스입니다.

*I1*<br/>
첫 번째 인터페이스입니다.

*I2*<br/>
두 번째 인터페이스입니다.

## <a name="remarks"></a>설명

활용 `ClassFactory` 는 사용자 정의 팩터리 구현을 제공 합니다.

프로그래밍 패턴을 사용 하는 방법에 설명 합니다 [구현](implements-structure.md) 클래스 팩터리 세 개 이상의 인터페이스를 지정 하는 구조입니다.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                        | 설명
------------------------------------------- | -----------
[ClassFactory::ClassFactory](#classfactory) |

### <a name="public-methods"></a>Public 메서드

이름                                            | 설명
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory::AddRef](#addref)                 | 현재 참조 횟수를 증가 시킵니다 `ClassFactory` 개체입니다.
[ClassFactory::LockServer](#lockserver)         | 증가 또는 감소 시킵니다 현재 추적 되는 개체의 기본 수 `ClassFactory` 개체입니다.
[ClassFactory::QueryInterface](#queryinterface) | 매개 변수에 의해 지정 된 인터페이스에 대 한 포인터를 검색 합니다.
[ClassFactory::Release](#release)               | 현재 참조 횟수를 감소 `ClassFactory` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ClassFactory`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="addref"></a>ClassFactory::AddRef

현재 참조 횟수를 증가 시킵니다 `ClassFactory` 개체입니다.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="classfactory"></a>ClassFactory::ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="lockserver"></a>ClassFactory::LockServer

증가 또는 감소 시킵니다 현재 추적 되는 개체의 기본 수 `ClassFactory` 개체입니다.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>매개 변수

*fLock*<br/>
**true** 추적 된 개체 수가 증가 합니다. **false** 추적 된 개체 수가 감소 합니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 E_FAIL입니다.

### <a name="remarks"></a>설명

`ClassFactory` 개체의 기본 인스턴스에서 추적 합니다 [모듈](module-class.md) 클래스입니다.

## <a name="queryinterface"></a>ClassFactory::QueryInterface

매개 변수에 의해 지정 된 인터페이스에 대 한 포인터를 검색 합니다.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 완료 될 때를 매개 변수로 지정 된 인터페이스에 대 한 포인터 *riid*합니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="release"></a>ClassFactory::Release

현재 참조 횟수를 감소 `ClassFactory` 개체입니다.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

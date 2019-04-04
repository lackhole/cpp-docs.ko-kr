---
title: WeakReference 클래스
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::Resolve
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
- implements/Microsoft::WRL::Details::WeakReference::~WeakReference
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
helpviewer_keywords:
- Microsoft::WRL::Details::WeakReference class
- Microsoft::WRL::Details::WeakReference::DecrementStrongReference method
- Microsoft::WRL::Details::WeakReference::IncrementStrongReference method
- Microsoft::WRL::Details::WeakReference::Resolve method
- Microsoft::WRL::Details::WeakReference::SetUnknown method
- Microsoft::WRL::Details::WeakReference::~WeakReference, destructor
- Microsoft::WRL::Details::WeakReference::WeakReference, constructor
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
ms.openlocfilehash: a3372a176a158dd9c89eb888c8deb0244eef9a84
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785749"
---
# <a name="weakreference-class"></a>WeakReference 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
class WeakReference;
```

## <a name="remarks"></a>설명

나타냅니다는 *약한 참조* Windows 런타임 또는 클래식 COM.를 사용 하 여 사용할 수 있는 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.

A `WeakReference` 개체를 유지 관리를 *강력한 참조*, 개체에 대 한 포인터는 및 *강력한 참조 횟수*에서 배포한는 강력한 참조의 복사본 수 인 `Resolve()` 메서드. 강력한 참조 횟수가 0이 아닌 이지만, 강력한 참조가 유효 하며 개체 액세스할 수 있습니다. 강력한 참조 횟수가 0 인 경우 강력한 참조가 올바르지 않습니다. 및 개체에 액세스할 수 없습니다.

`WeakReference` 개체는 일반적으로 외부 스레드나 응용 프로그램에서 제어 하는 개체를 나타내는 데 사용 됩니다. 예를 들어, 생성 된 `WeakReference` 파일 개체에 대 한 참조에서 개체입니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.

`WeakReference` 메서드는 스레드로부터 안전 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                  | 설명
----------------------------------------------------- | ---------------------------------------------------------------------------
[WeakReference::WeakReference](#weakreference)        | `WeakReference` 클래스의 새 인스턴스를 초기화합니다.
[WeakReference::~WeakReference](#tilde-weakreference) | 초기화 취소 (삭제)의 현재 인스턴스는 `WeakReference` 클래스입니다.

### <a name="public-methods"></a>Public 메서드

이름                                                                 | 설명
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference::DecrementStrongReference](#decrementstrongreference) | 현재는 강력한 참조 횟수를 감소 시킵니다 `WeakReference` 개체입니다.
[WeakReference::IncrementStrongReference](#incrementstrongreference) | 현재 강력한 참조 횟수를 증가 시킵니다 `WeakReference` 개체입니다.
[WeakReference::Resolve](#resolve)                                   | 강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조 값으로 지정된 된 포인터를 설정 합니다.
[WeakReference::SetUnknown](#setunknown)                             | 현재는 강력한 참조를 설정 `WeakReference` 개체를 지정 된 인터페이스 포인터입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`WeakReference`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="tilde-weakreference"></a>WeakReference::~WeakReference

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

현재 인스턴스를 초기화 해제는 `WeakReference` 클래스입니다.

## <a name="decrementstrongreference"></a>WeakReference::DecrementStrongReference

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>설명

현재는 강력한 참조 횟수를 감소 시킵니다 `WeakReference` 개체입니다.

강력한 참조 횟수가 0이 되 면 강력한 참조로 설정 됩니다 `nullptr`합니다.

### <a name="return-value"></a>반환 값

감소 된 강력한 참조 수입니다.

## <a name="incrementstrongreference"></a>WeakReference::IncrementStrongReference

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>반환 값

증가 된 강력한 참조 수입니다.

### <a name="remarks"></a>설명

현재 강력한 참조 횟수를 증가 시킵니다 `WeakReference` 개체입니다.

## <a name="resolve"></a>WeakReference::Resolve

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 완료 될 때 강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조의 복사본입니다.

### <a name="return-value"></a>반환 값

- 이 작업에 성공 하면 S_OK와 강력한 참조 횟수는 0입니다. 합니다 *ppvObject* 매개 변수는 설정 `nullptr`합니다.

- 이 작업은 성공 하 고 강력한 참조 횟수가 0이 아닌 경우 S_OK입니다. 합니다 *ppvObject* 매개 변수는 강력한 참조를 설정 합니다.

- 그렇지 않은 경우 이유를 나타내는 HRESULT이이 작업이 실패 했습니다.

### <a name="remarks"></a>설명

강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조 값으로 지정된 된 포인터를 설정 합니다.

## <a name="setunknown"></a>WeakReference::SetUnknown

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>매개 변수

*unk*<br/>
에 대 한 포인터를 `IUnknown` 개체의 인터페이스입니다.

### <a name="remarks"></a>설명

현재는 강력한 참조를 설정 `WeakReference` 개체를 지정 된 인터페이스 포인터입니다.

## <a name="weakreference"></a>WeakReference::WeakReference

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
WeakReference();
```

### <a name="remarks"></a>설명

`WeakReference` 클래스의 새 인스턴스를 초기화합니다.

에 대 한 강력한 참조 포인터를 `WeakReference` 개체에 초기화 됩니다 `nullptr`, 및 강력한 참조 횟수를 1로 초기화 됩니다.

---
title: CreateActivationFactory 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: 07bc0dceb8066faf9c1beab64d48245d8735aa64
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785604"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory 함수

Windows 런타임으로 활성화할 수 있는 지정된 클래스의 인스턴스를 생성하는 팩터리를 만듭니다.

## <a name="syntax"></a>구문

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>매개 변수

*flags*<br/>
하나 이상의 조합 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거형 값입니다.

*entry*<br/>
에 대 한 포인터를 [CreatorMap](creatormap-structure.md) 매개 변수에 대 한 초기화 및 등록 정보를 포함 하는 *riid*합니다.

*riid*<br/>
인터페이스 ID에 대 한 참조

*ppFactory*<br/>
이 작업이 완료 되 면 성공적으로 활성화 팩터리에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

어설션 오류가 발생 하는 경우에 내보내집니다 템플릿 매개 변수 *팩터리* 인터페이스에서 파생 되지 `IActivationFactory`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Wrappers::Details 네임스페이스](microsoft-wrl-wrappers-details-namespace.md)
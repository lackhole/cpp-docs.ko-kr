---
title: GetActivationFactory 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: 3e138eee9e5bc02971cd1eb34c78f2be4ad5c9a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398422"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 함수

템플릿 매개 변수로 지정 된 형식에 대 한 활성화 팩터리를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
활성화 팩터리 형식을 지정 하는 템플릿 매개 변수입니다.

*activatableClassId*<br/>
활성화 팩터리를 생성할 수 있는 클래스의 이름입니다.

*factory*<br/>
이 작업이 완료 되 면 형식에 대 한 활성화 팩터리에 대 한 참조가 *T*합니다.

## <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않은 경우이 작업이 실패 한 이유를 나타내는 HRESULT 오류가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Windows::Foundation

## <a name="see-also"></a>참고자료

[Windows::Foundation 네임스페이스](windows-foundation-namespace.md)
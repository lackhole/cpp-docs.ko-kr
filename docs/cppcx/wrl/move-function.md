---
title: Move 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 1a03216197462090f38d3bc2065fe227f0667919
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785318"
---
# <a name="move-function"></a>Move 함수

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인수 형식입니다.

*arg*<br/>
이동 하는 인수입니다.

## <a name="return-value"></a>반환 값

매개 변수 *arg* 참조 또는 rvalue 참조 특성 후 있으면 제거 되었습니다.

## <a name="remarks"></a>설명

다른 곳에서 지정 된 인수를 이동합니다.

자세한 내용은 참조는 **이동 의미 체계** 부분 [Rvalue 참조 선언 자: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** internal.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
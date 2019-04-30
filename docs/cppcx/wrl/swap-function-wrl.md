---
title: Swap 함수 (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Swap
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
ms.openlocfilehash: 97d24f1f4453e948c621651e029254db1b0de712
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398149"
---
# <a name="swap-function-wrl"></a>Swap 함수 (WRL)

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
WRL_NOTHROW inline void Swap(
   _Inout_ T& left,
   _Inout_ T& right
);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
첫 번째 인수입니다.

*right*<br/>
두 번째 인수입니다.

## <a name="return-value"></a>반환 값

## <a name="remarks"></a>설명

두 개의 지정 된 인수 값을 교환 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** internal.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고자료

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
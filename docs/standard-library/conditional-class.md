---
title: conditional 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: b8f0f69cc1e4f6966bc9ccb63fe529436295badd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457316"
---
# <a name="conditional-class"></a>conditional 클래스

지정된 조건에 따라 두 가지 형식 중 하나를 선택합니다.

## <a name="syntax"></a>구문

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>매개 변수

*B*\
선택된 형식을 확인하는 값입니다.

*들은*\
B가 true인 경우의 형식 결과입니다.

*T*\
B가 false인 경우의 형식 결과입니다.

## <a name="remarks"></a>설명

*B* 가 **true**로 `conditional<B, T1, T2>::type` 평가 되 면 템플릿 멤버 typedef가 *T1* 로 평가 되 고 *b* 가 **false**로 평가 되 면 *T2* 로 계산 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)

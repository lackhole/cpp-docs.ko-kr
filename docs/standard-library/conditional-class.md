---
title: conditional 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: be81a1bc32f2f86f1d79970868933bddb8dc3620
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212107"
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

*B*<br/>
선택된 형식을 확인하는 값입니다.

*T1*<br/>
B가 true인 경우의 형식 결과입니다.

*T2*<br/>
B가 false인 경우의 형식 결과입니다.

## <a name="remarks"></a>설명

템플릿 멤버 typedef `conditional<B, T1, T2>::type` 로 평가 *T1* 때 *B* 로 **true**를 계산 하 고 *T2* 때  *B* 로 평가 **false**합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>

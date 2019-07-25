---
title: is_final 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_final
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
ms.openlocfilehash: 14efbeb33193cc674c6e766b880e89d9b76d140a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452649"
---
# <a name="isfinal-class"></a>is_final 클래스

형식이 `final`로 표시된 클래스 형식인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>매개 변수

*트*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *T* 형식이로 표시 `final`된 클래스 형식인 경우 true이 고, 그렇지 않으면 false입니다. *T* 가 클래스 형식이 면 완전 한 형식 이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[final 지정자](../cpp/final-specifier.md)

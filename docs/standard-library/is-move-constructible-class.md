---
title: is_move_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 1b1e450338a123c51b80f40f2369207c8b987cd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383635"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible 클래스

형식에 이동 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
평가할 형식입니다.

## <a name="remarks"></a>설명

형식 경우 true로 계산 되는 형식 조건자 *T* 이동 작업을 사용 하 여 생성할 수 있습니다. 이 조건자는 `is_constructible<T, T&&>`과 같습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>

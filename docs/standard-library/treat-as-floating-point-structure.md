---
title: treat_as_floating_point 구조체
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 1b7b58983032ee74ed3d88feb7325cd537e1cc2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411944"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point 구조체

`Rep`가 부동 소수점 형식으로 처리될 수 있는지를 지정합니다.

## <a name="syntax"></a>구문

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>설명

특수화 `treat_as_floating_point<Rep>`가 [true_type](../standard-library/type-traits-typedefs.md#true_type)에서 파생되는 경우에만 `Rep`를 부동 소수점 형식으로 처리할 수 있습니다. 사용자 형식 정의에 대해 템플릿 클래스를 특수화할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<chrono >

**네임스페이스:** std::chrono

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>

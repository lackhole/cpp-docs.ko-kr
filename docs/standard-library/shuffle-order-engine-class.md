---
title: shuffle_order_engine 클래스
ms.date: 11/04/2016
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
ms.openlocfilehash: bf767c12a19e4ae47c34a8f01e1b1a2f1e028eb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399436"
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine 클래스

기본 엔진에서 반환된 값을 다시 정렬하여 임의의 시퀀스를 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>매개 변수

*엔진*<br/>
기본 엔진 유형입니다.

*K*<br/>
**테이블 크기**. 버퍼(테이블)에 있는 요소의 수입니다. **사전 조건**: `0 < K`

## <a name="members"></a>멤버

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

엔진 구성원에 대한 자세한 내용은 [\<random>](../standard-library/random.md)을 참조하세요.

## <a name="remarks"></a>설명

이 템플릿 클래스는 기본 엔진에서 반환하는 값을 다시 정렬하여 값을 생성하는 *엔진 어댑터*에 대해 설명합니다. 각 생성자는 사용 하 여 내부 테이블을 채우는 *K* 기본 엔진에서 반환 된 값 및 값 요청 될 때 테이블에서 임의 요소가 선택 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<random>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<random>](../standard-library/random.md)<br/>

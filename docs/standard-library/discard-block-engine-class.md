---
title: discard_block_engine 클래스
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: eb00945084affb2be9299953e5ca9352c56d3b32
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688101"
---
# <a name="discard_block_engine-class"></a>discard_block_engine 클래스

기본 엔진에서 반환된 값을 버려 임의의 시퀀스를 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>매개 변수

*엔진* \
기본 엔진 유형입니다.

*P* \
**블록 크기**입니다. 각 블록에 있는 값의 수입니다.

*R*\
**사용된 블록**입니다. 사용된 각 블록에 있는 값의 수입니다. 나머지는 삭제 됩니다 (`P`  -  `R`). **사전 조건**: `0 < R ≤ P`

## <a name="members"></a>멤버

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

엔진 구성원에 대한 자세한 내용은 [\<random>](../standard-library/random.md)을 참조하세요.

## <a name="remarks"></a>주의

이 클래스 템플릿은 기본 엔진에서 반환 하는 일부 값을 삭제 하 여 값을 생성 하는 엔진 어댑터에 대해 설명 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<random>

**네임스페이스:** std

## <a name="see-also"></a>참조

[\<random>](../standard-library/random.md)

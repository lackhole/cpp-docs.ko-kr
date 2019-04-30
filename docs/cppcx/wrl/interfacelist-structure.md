---
title: InterfaceList 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 745348e81888b5a87c57fbb99d397fcd423c3ee1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398214"
---
# <a name="interfacelist-structure"></a>InterfaceList 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인터페이스 이름이; 재귀 목록의 첫 번째 인터페이스입니다.

*U*<br/>
인터페이스 이름이; 재귀 목록의 나머지 인터페이스입니다.

## <a name="remarks"></a>설명

인터페이스의 재귀 목록을 만드는 데 사용 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`FirstT`|템플릿 매개 변수에 대 한 동의어 *T*합니다.|
|`RestT`|템플릿 매개 변수에 대 한 동의어 *U*합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InterfaceList`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고자료

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
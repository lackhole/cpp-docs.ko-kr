---
title: CSimpleArrayEqualHelper 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: 8b7e32ddab5b2f0667b17b0f127ac2e7e5d9a426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277996"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper 클래스

이 클래스는에 대 한 도우미는 [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스입니다.

## <a name="syntax"></a>구문

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
파생된 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(정적) 두 개의 테스트 `CSimpleArray` 개체 같음에 대 한 요소입니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 보완을 `CSimpleArray` 클래스입니다. 에 저장 된 두 요소를 비교에 대 한 메서드를 제공 하는 `CSimpleArray` 개체입니다. 사용 하는 요소를 비교 하는 기본적으로 **operator=()**, 배열 자체 같음 연산자를 없는 복잡 한 데이터 형식에 있으면이 클래스를 재정의 해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual

두 개의 테스트 `CSimpleArray` 개체 같음에 대 한 요소입니다.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>매개 변수

*t1*<br/>
형식은 T 형식 개체

*t2*<br/>
형식은 T 형식 개체

### <a name="return-value"></a>반환 값

요소가 같으면 false이 고, 그렇지 true를 반환 합니다.

## <a name="see-also"></a>참고자료

[CSimpleArray 클래스](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse 클래스](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

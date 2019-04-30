---
title: CSimpleMapEqualHelperFalse 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: 9c4241049ad323047f06c0b29f946521f2c02167
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277905"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse 클래스

이 클래스는에 대 한 도우미는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스입니다.

## <a name="syntax"></a>구문

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(정적) 두 키가 같은지 테스트합니다.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(정적) False를 반환 합니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 보완을 `CSimpleMap` 클래스입니다. 에 포함 된 두 요소를 비교 하는 방법을 제공 합니다 `CSimpleMap` 개체, 특히 두 값 요소 또는 두 가지 주요 요소입니다.

값 비교는 항상 false를 반환 하 고 호출 뿐만 `ATLASSERT` 참조 적이 없으면 false의 인수와 함께 합니다. 이 클래스를 대부분의 메서드에 대해 제대로 작동 하지만 실패와 같은 비교에 의존 하는 방법에 대 한 잘 정의 된 방식으로 키/값 쌍을 포함 하는 맵을 사용 하면 여기서 같음 테스트 정의 되지 않은 충분히 경우 [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey

두 키가 같은지 테스트합니다.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>매개 변수

*k1*<br/>
첫 번째 키입니다.

*k2*<br/>
두 번째 키입니다.

### <a name="return-value"></a>반환 값

키가 같으면 false이 고, 그렇지 true를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)합니다.

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue

false를 반환합니다.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>반환 값

false를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 항상 false를 반환 하며 호출 `ATLASSERT` 참조 적이 없으면 false의 인수와 함께 합니다. 목적은 `CSimpleMapEqualHelperFalse::IsEqualValue` 메서드 비교를 사용 하 여 같음 테스트 적절 하 게 정의 하지 않은 경우에 잘 정의 된 방식으로 실패 하는 것입니다.

## <a name="see-also"></a>참고자료

[CSimpleMapEqualHelper 클래스](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

---
title: CSimpleMapEqualHelper 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: c614cbb11376c5ae338762c0feaa54c8f1bb3e27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277933"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper 클래스

이 클래스는에 대 한 도우미는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스입니다.

## <a name="syntax"></a>구문

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>매개 변수

*TKey*<br/>
주요 요소입니다.

*TVal*<br/>
값 요소입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(정적) 두 키가 같은지 테스트합니다.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(정적) 두 값이 같은지를 테스트합니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 보완을 `CSimpleMap` 클래스입니다. 두 비교 하기 위한 메서드를 제공 `CSimpleMap` 개체 같음에 대 한 요소 (특히, 키 및 값 구성 요소). 기본적으로 키와 값 비교에 사용할 **operator==()**, 없지만 지도 자체 같음 연산자를 없는 복잡 한 데이터 형식에 있으면 필요한 추가 기능을 제공 하기이 클래스를 재정의할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey

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

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue

두 값이 같은지를 테스트합니다.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>매개 변수

*v1*<br/>
첫 번째 값입니다.

*v2*<br/>
두 번째 값입니다.

### <a name="return-value"></a>반환 값

값이 같으면 false이 고, 그렇지 true를 반환 합니다.

## <a name="see-also"></a>참고자료

[CSimpleMapEqualHelperFalse 클래스](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

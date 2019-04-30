---
title: CDefaultHashTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: a51b4460d7fcdf778fce24b6e404b75190f598f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245835"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits 클래스

이 클래스는 해시 값을 계산 하기 위한 정적 함수를 제공 합니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDefaultHashTraits::Hash](#hash)|(정적) 지정된 된 요소에 대 한 해시 값을 계산 하려면이 함수를 호출 합니다.|

## <a name="remarks"></a>설명

이 클래스는 지정된 된 요소에 대 한 해시 값을 반환 하는 단일 정적 함수를 포함 합니다. 이 클래스에서 사용 되는 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="hash"></a>  CDefaultHashTraits::Hash

지정된 된 요소에 대 한 해시 값을 계산 하려면이 함수를 호출 합니다.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>매개 변수

*element*<br/>
요소입니다.

### <a name="return-value"></a>반환 값

해시 값을 반환 합니다.

### <a name="remarks"></a>설명

기본 해싱 알고리즘은 매우 간단 합니다: 반환 값 요소입니다. 더 복잡 한 알고리즘을 필요한 경우이 함수를 재정의 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

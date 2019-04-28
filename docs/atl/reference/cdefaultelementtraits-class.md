---
title: CDefaultElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: 0ee076af5fc4a1c2145162ac510b3a4460e251e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245936"
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits 클래스

이 클래스는 컬렉션 클래스에 대 한 기본 메서드 및 함수를 제공 합니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터의 형식입니다.

## <a name="remarks"></a>설명

이 클래스는 이동, 복사, 비교 및 컬렉션 클래스 개체에 저장 된 해시 요소에 대 한 기본 정적 함수 및 메서드를 제공 합니다. 해당 함수 및 메서드를이 클래스가 파생 되 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)를 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), 및 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)에 활용 되 고 [ CElementTraits](../../atl/reference/celementtraits-class.md)하십시오 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), 및 [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)

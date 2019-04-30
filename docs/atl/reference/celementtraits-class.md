---
title: CElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 646b445aed93c9041932c60442f61792f5e1a7e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245770"
---
# <a name="celementtraits-class"></a>CElementTraits 클래스

이 클래스는 복사, 이동, 비교 및 해시 작업에 대 한 메서드 및 함수를 제공 하려면 컬렉션 클래스에 의해 사용 됩니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터의 형식입니다.

## <a name="remarks"></a>설명

이 클래스는 이동, 복사, 비교 및 컬렉션 클래스 개체에 저장 된 해시 요소에 대 한 기본 정적 함수 및 메서드를 제공 합니다. `CElementTraits` 컬렉션 클래스에서 이러한 작업의 기본 공급자로 지정 [CAtlArray](../../atl/reference/catlarray-class.md)를 [CAtlList](../../atl/reference/catllist-class.md)합니다 [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), 및 [CRBTree](../../atl/reference/crbtree-class.md)합니다.

단순 데이터 형식에 대 한 기본 구현을 만으로도 충분 하지만 함수 및 메서드를 더 복잡 한 개체를 저장할 컬렉션 클래스를 사용 하는 경우 사용자가 제공한 구현을를 재정의 해야 합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

## <a name="see-also"></a>참고자료

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

---
title: CHeapPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: e535afb3a49a5720c8394cc1ab9186c360527fea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258925"
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits 클래스

이 클래스 힙에 대 한 포인터의 컬렉션을 만들 때 정적 함수 메서드와 유용한 형식 정의 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션 클래스에 저장할 개체 형식입니다.

*Allocator*<br/>
사용 하는 메모리 할당 클래스입니다. 기본값은 [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 힙 포인터를 포함 하는 컬렉션 클래스 개체를 만드는 데에 대 한 메서드, 정적 함수 및 형식 정의 제공 합니다. 클래스 `CHeapPtrList` 에서 파생 `CHeapPtrElementTraits`합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="inargtype"></a>  CHeapPtrElementTraits::INARGTYPE

컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

##  <a name="outargtype"></a>  CHeapPtrElementTraits::OUTARGTYPE

컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>참고자료

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

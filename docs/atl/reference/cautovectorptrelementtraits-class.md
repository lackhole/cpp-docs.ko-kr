---
title: CAutoVectorPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 168670709470d7b7fdd77edb3c29d5a9f4049ca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260086"
---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits 클래스

이 클래스는 정적 함수 메서드와 새 벡터를 사용 하 여 스마트 포인터의 컬렉션을 만들고 운영자를 삭제할 때 유용한 형식 정의 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 스마트 포인터를 포함 하는 컬렉션 클래스 개체를 만드는 데에 대 한 메서드, 정적 함수 및 형식 정의 제공 합니다. 와 달리 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)이 클래스는 벡터 new 및 delete 연산자입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="inargtype"></a>  CAutoVectorPtrElementTraits::INARGTYPE

컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoVectorPtrElementTraits::OUTARGTYPE

컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>참고자료

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CAutoVectorPtr 클래스](../../atl/reference/cautovectorptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

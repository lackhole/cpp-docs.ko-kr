---
title: CAutoPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: d217441048403b0ff5361f8049b76367174812f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246743"
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits 클래스

이 클래스의 스마트 포인터 컬렉션을 만들 때 정적 함수 메서드와 유용한 형식 정의 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 스마트 포인터를 포함 하는 컬렉션 클래스 개체를 만드는 데에 대 한 메서드, 정적 함수 및 형식 정의 제공 합니다. 클래스 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 하 고 [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 에서 파생 `CAutoPtrElementTraits`합니다. 벡터 new 및 delete 연산자에 필요한는 스마트 포인터의 컬렉션을 작성 하는 경우 사용 하 여 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 대신 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="inargtype"></a>  CAutoPtrElementTraits::INARGTYPE

컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef CAutoPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoPtrElementTraits::OUTARGTYPE

컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>참고자료

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

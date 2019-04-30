---
title: CComQIPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 42662a971f5d293cff404ca1eda161a3b87b13b9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246170"
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits 클래스

이 클래스 COM 인터페이스 포인터의 컬렉션을 만들 때 정적 함수 메서드와 유용한 형식 정의 제공 합니다.

## <a name="syntax"></a>구문

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>매개 변수

*I*<br/>
저장에 대 한 포인터의 형식을 지정 하는 COM 인터페이스입니다.

*piid*<br/>
에 대 한 포인터의 IID *있습니까*합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 메서드를 파생 하 고의 컬렉션 클래스를 만들 때 유용한 형식 정의 제공 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터 개체입니다. 둘 다에서이 클래스를 사용 합니다 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 하 고 [CInterfaceList](../../atl/reference/cinterfacelist-class.md) 클래스입니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE

컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>참고자료

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

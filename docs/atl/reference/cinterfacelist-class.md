---
title: CInterfaceList 클래스
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: e740d891e279bb29eeef898de52698dc3f04fc67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258639"
---
# <a name="cinterfacelist-class"></a>CInterfaceList 클래스

이 클래스는 COM 인터페이스 포인터의 목록을 구성할 때 유용한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>매개 변수

*I*<br/>
저장에 대 한 포인터의 형식을 지정 하는 COM 인터페이스입니다.

*piid*<br/>
에 대 한 포인터의 IID *있습니까*합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CInterfaceList::CInterfaceList](#cinterfacelist)|인터페이스 목록에 대 한 생성자입니다.|

## <a name="remarks"></a>설명

이 클래스는 생성자 및 COM 인터페이스 포인터의 목록을 작성 하는 것에 대 한 파생된 메서드를 제공 합니다. 사용 하 여 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 배열이 필요 합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList

인터페이스 목록에 대 한 생성자입니다.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
기본값은 10 사용 하 여 블록 크기입니다.

### <a name="remarks"></a>설명

블록 크기는 새 요소가 필요한 경우 할당 된 메모리의 크기를 측정 합니다. 블록 크기가 클수록 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 합니다.

## <a name="see-also"></a>참고자료

[CAtlList 클래스](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr 클래스](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

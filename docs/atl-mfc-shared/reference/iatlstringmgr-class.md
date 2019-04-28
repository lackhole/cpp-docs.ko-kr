---
title: IAtlStringMgr 클래스
ms.date: 10/18/2018
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
ms.openlocfilehash: 978d33c719b9cb8c2708dc97fa78874534dfd748
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62199829"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr 클래스

이 클래스에 인터페이스를 나타냅니다는 `CStringT` 메모리 관리자입니다.

## <a name="syntax"></a>구문

```
__interface IAtlStringMgr
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Allocate](#allocate)|새 문자열 데이터 구조를 할당 하려면이 메서드를 호출 합니다.|
|[Clone](#clone)|새 문자열 관리자의 다른 인스턴스 사용에 대 한 포인터를 반환 하려면이 메서드를 호출 `CSimpleStringT`합니다.|
|[무료](#free)|이 메서드는 문자열 데이터 구조를 호출 합니다.|
|[GetNilString](#getnilstring)|에 대 한 포인터를 반환 합니다 `CStringData` 빈 문자열 개체에서 사용 되는 개체입니다.|
|[Reallocate](#reallocate)|문자열 데이터 구조를 다시 할당 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 MFC에 독립적인 문자열 클래스를 사용 하는 메모리 관리 와 같은 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)하십시오 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), 및 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)합니다.

또한 사용자 지정 문자열 클래스에 대 한 사용자 지정 메모리 관리자를 구현 하려면이 클래스를 사용할 수 있습니다. 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpstr.h

##  <a name="allocate"></a>  IAtlStringMgr::Allocate

새 문자열 데이터 구조를 할당합니다.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>매개 변수

*nAllocLength*<br/>
새 메모리 블록에 있는 문자의 수입니다.

*nCharSize*<br/>
크기 (바이트) 문자열 관리자에서 사용 하는 문자 형식입니다.

### <a name="return-value"></a>반환 값

새로 할당된 메모리 블록에 대한 포인터를 반환합니다.

> [!NOTE]
>  예외를 throw 하 여 할당에 실패를 알리지 않습니다. 대신 NULL을 반환 하 여 할당에 실패를 알릴 수 해야 합니다.

### <a name="remarks"></a>설명

호출 [IAtlStringMgr::Free](#free) 하거나 [IAtlStringMgr::ReAllocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

> [!NOTE]
>  사용 예제를 보려면 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

##  <a name="clone"></a>  IAtlStringMgr::Clone

새 문자열 관리자의 다른 인스턴스 사용에 대 한 포인터를 반환 합니다. `CSimpleStringT`합니다.

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>반환 값

복사본을 반환 합니다 `IAtlStringMgr` 개체입니다.

### <a name="remarks"></a>설명

일반적으로 문자열 관리자는 새 문자열에 필요할 때 프레임 워크에서 호출 합니다. 대부분의 경우에는 **이** 포인터가 반환 됩니다.

그러나 메모리 관리자의 여러 인스턴스에서 사용 되 고 지원 하지 않는 경우 `CSimpleStringT`를 공유할 수 있는 문자열 관리자에 대 한 포인터를 반환 합니다.

> [!NOTE]
>  사용 예제를 보려면 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

##  <a name="free"></a>  IAtlStringMgr::Free

문자열 데이터 구조를 해제합니다.

```
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>매개 변수

*pData*<br/>
해제할 메모리 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이전에 의해 할당 된 메모리 블록의 해제 [Allocate](#allocate) 또는 [다시 할당](../../atl/reference/iatlmemmgr-class.md#reallocate)합니다.

> [!NOTE]
>  사용 예제를 보려면 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString

빈 문자열에 대 한 문자열 데이터 구조에 대 한 포인터를 반환합니다.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CStringData` 을 빈 문자열을 나타내는 개체입니다.

### <a name="remarks"></a>설명

빈 문자열 표현을 반환 하려면이 함수를 호출 합니다.

> [!NOTE]
> 사용자 지정 문자열 관리자 구현 하는 경우이 함수는 실패 하지 해야 합니다. 인스턴스를 포함 하 여이 확실히 `CNilStringData` 문자열 manager 클래스 및 해당 인스턴스에 대 한 포인터를 반환 합니다.

> [!NOTE]
> 사용 예제를 보려면 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

## <a name="reallocate"></a>  IAtlStringMgr::Reallocate

문자열 데이터 구조를 다시 할당합니다.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>매개 변수

*pData*<br/>
이 메모리 관리자에 의해 이전에 할당 된 메모리에 대 한 포인터입니다.

*nAllocLength*<br/>
새 메모리 블록에 있는 문자의 수입니다.

*nCharSize*<br/>
크기 (바이트) 문자열 관리자에서 사용 하는 문자 형식입니다.

### <a name="return-value"></a>반환 값

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

으로 지정 된 기존 메모리 블록의 크기를 조정 하려면이 함수를 호출 *pData*합니다.

호출 [IAtlStringMgr::Free](#free) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

> [!NOTE]
> 사용 예제를 보려면 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)

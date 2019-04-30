---
title: CComHeap 클래스
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: 1a8618bd5146f2906f18cfbaa33894d34598776a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259380"
---
# <a name="ccomheap-class"></a>CComHeap 클래스

이 클래스는 구현 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM 메모리 할당 함수를 사용 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComHeap::Allocate](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[CComHeap::Free](#free)|이 메모리 관리자에 의해 할당 된 메모리 블록을 해제 하려면이 메서드를 호출 합니다.|
|[CComHeap::GetSize](#getsize)|이 메모리 관리자에 의해 할당 된 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.|
|[CComHeap::Reallocate](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CComHeap` 메모리 할당 함수를 비롯 한 COM 할당 함수를 사용 하 여 구현 [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree)를 [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize), 및 [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)합니다. 할당 될 수 있는 메모리의 최대 크기는 INT_MAX (2147483647) 바이트와 같습니다.

## <a name="example"></a>예제

예를 참조 하세요 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>요구 사항

**헤더:** ATLComMem.h

##  <a name="allocate"></a>  CComHeap::Allocate

메모리 블록을 할당하려면 이 메서드를 호출합니다.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*nBytes*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>반환 값

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

호출 [ccomheap:: Free](#free) 하거나 [ccomheap:: Reallocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

사용 하 여 구현 [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc)합니다.

##  <a name="free"></a>  CComHeap::Free

이 메모리 관리자에 의해 할당 된 메모리 블록을 해제 하려면이 메서드를 호출 합니다.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL 유효한 값 이며 아무 작업도 수행 합니다.

### <a name="remarks"></a>설명

사용 하 여 구현 [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree)합니다.

##  <a name="getsize"></a>  CComHeap::GetSize

이 메모리 관리자에 의해 할당 된 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

할당된 된 메모리 블록의 크기 (바이트)를 반환합니다.

### <a name="remarks"></a>설명

사용 하 여 구현 [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize)합니다.

##  <a name="reallocate"></a>  CComHeap::Reallocate

이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

*nBytes*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>반환 값

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

호출 [ccomheap::](#free) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

사용 하 여 구현 [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)합니다.

## <a name="see-also"></a>참고자료

[DynamicConsumer 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap 클래스](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)

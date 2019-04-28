---
title: CCRTHeap 클래스
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: 3c5030b9cfbfd636a783d27bcc8f9469f8348acb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246064"
---
# <a name="ccrtheap-class"></a>CCRTHeap 클래스

이 클래스는 구현 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT 힙 함수를 사용 하 여 합니다.

## <a name="syntax"></a>구문

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCRTHeap::Allocate](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[CCRTHeap::Free](#free)|이 메모리 관리자에 의해 할당 된 메모리 블록을 해제 하려면이 메서드를 호출 합니다.|
|[CCRTHeap::GetSize](#getsize)|이 메모리 관리자에 의해 할당 된 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.|
|[CCRTHeap::Reallocate](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CCRTHeap` 메모리 할당 함수 CRT를 사용 하 여 힙 함수를 포함 하 여 구현 [malloc](../../c-runtime-library/reference/malloc.md), [무료](../../c-runtime-library/reference/free.md)합니다 [realloc](../../c-runtime-library/reference/realloc.md), 및 [_msize](../../c-runtime-library/reference/msize.md)합니다.

## <a name="example"></a>예제

예를 참조 하세요 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>요구 사항

**헤더:** atlmem.h

##  <a name="allocate"></a>  CCRTHeap::Allocate

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

호출 [ccrtheap:: Free](#free) 하거나 [ccrtheap:: Reallocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

사용 하 여 구현 [malloc](../../c-runtime-library/reference/malloc.md)합니다.

##  <a name="free"></a>  CCRTHeap::Free

이 메모리 관리자에 의해 할당 된 메모리 블록을 해제 하려면이 메서드를 호출 합니다.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL 유효한 값 이며 아무 작업도 수행 합니다.

### <a name="remarks"></a>설명

사용 하 여 구현 [무료](../../c-runtime-library/reference/free.md)합니다.

##  <a name="getsize"></a>  CCRTHeap::GetSize

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

사용 하 여 구현 [_msize](../../c-runtime-library/reference/msize.md)합니다.

##  <a name="reallocate"></a>  CCRTHeap::Reallocate

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

호출 [ccrtheap::](#free) 이 메서드에 의해 할당 된 메모리를 해제 합니다. 사용 하 여 구현 [realloc](../../c-runtime-library/reference/realloc.md)합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComHeap 클래스](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)

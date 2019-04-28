---
title: CHeapPtrBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: 558c9bd78257a06e123d47a0110375e7f448f90d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245610"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase 클래스

이 클래스는 몇 가지 힙 스마트 포인터 클래스의 기본을 형성합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
힙에 저장 될 개체 형식입니다.

*Allocator*<br/>
사용 하는 메모리 할당 클래스입니다. 기본적으로 CRT 루틴은 할당 및 메모리를 확보를 위해 사용 됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CHeapPtrBase::~CHeapPtrBase](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|메모리를 할당 하려면이 메서드를 호출 합니다.|
|[CHeapPtrBase::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|
|[CHeapPtrBase::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|
|[CHeapPtrBase::Free](#free)|가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CHeapPtrBase`합니다.|
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|메모리를 다시 할당 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CHeapPtrBase::operator T*](#operator_t_star)|캐스트 연산자입니다.|
|[CHeapPtrBase::operator &](#operator_amp)|& 연산자입니다.|
|[CHeapPtrBase::operator ->](#operator_ptr)|멤버 포인터 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스는 몇 가지 힙 스마트 포인터 클래스의 기본을 형성합니다. 예를 들어 파생된 클래스 [CHeapPtr](../../atl/reference/cheapptr-class.md) 하 고 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), 자체 생성자 및 연산자를 추가 합니다. 구현 예제에 대 한 이러한 클래스를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes

메모리를 할당 하려면이 메서드를 호출 합니다.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*nBytes*<br/>
할당할 메모리의 바이트 수입니다.

### <a name="return-value"></a>반환 값

메모리 되 면 true를 반환 합니다 할당 false 그렇지 않은 경우.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우는 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수는 현재 기존 값을 가리킵니다; null은, 합니다.

##  <a name="attach"></a>  CHeapPtrBase::Attach

이 메서드는 기존 포인터의 소유권을 호출 합니다.

```
void Attach(T* pData) throw();
```

### <a name="parameters"></a>매개 변수

*pData*<br/>
`CHeapPtrBase` 개체 this이 포인터의 소유권을 갖게 됩니다.

### <a name="remarks"></a>설명

경우는 `CHeapPtrBase` 자동으로 삭제 됩니다 포인터 및 할당 된 데이터 범위를 벗어날 때, 개체에 대 한 포인터의 소유권을 갖습니다.

디버그 빌드에서 어설션 오류가 발생 하는 경우는 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수는 현재 기존 값을 가리킵니다; null은, 합니다.

##  <a name="dtor"></a>  CHeapPtrBase::~CHeapPtrBase

소멸자입니다.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="detach"></a>  CHeapPtrBase::Detach

포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>반환 값

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제, 설정 된 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수를 NULL 포인터의 복사본을 반환 합니다.

##  <a name="free"></a>  CHeapPtrBase::Free

가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CHeapPtrBase`합니다.

```
void Free() throw();
```

### <a name="remarks"></a>설명

가리키는 개체를 `CHeapPtrBase` 해제 되 면 하며 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수를 NULL로 설정 합니다.

##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData

포인터 데이터 멤버 변수입니다.

```
T* m_pData;
```

### <a name="remarks"></a>설명

이 멤버 변수가 포인터 정보를 보유합니다.

##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;

& 연산자입니다.

```
T** operator&() throw();
```

### <a name="return-value"></a>반환 값

가리키는 개체의 주소를 반환 합니다 `CHeapPtrBase` 개체입니다.

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator -&gt;

멤버 포인터 연산자입니다.

```
T* operator->() const throw();
```

### <a name="return-value"></a>반환 값

값을 반환 합니다 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수입니다.

### <a name="remarks"></a>설명

이 연산자가 가리키는 클래스의 메서드를 호출 하는 데는 `CHeapPtrBase` 개체입니다. 디버그 빌드에서 어설션 오류가 발생 하는 경우는 `CHeapPtrBase` NULL을 가리킵니다.

##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T*

캐스트 연산자입니다.

```
operator T*() const throw();
```

### <a name="remarks"></a>설명

반환 [CHeapPtrBase::m_pData](#m_pdata)합니다.

##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes

메모리를 다시 할당 하려면이 메서드를 호출 합니다.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*nBytes*<br/>
새 바이트에 할당할 메모리 양입니다.

### <a name="return-value"></a>반환 값

메모리 되 면 true를 반환 합니다 할당 false 그렇지 않은 경우.

## <a name="see-also"></a>참고자료

[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

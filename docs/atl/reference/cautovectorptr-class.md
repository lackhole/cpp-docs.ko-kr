---
title: CAutoVectorPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: f614318125f3c6bce4003fee5fb4a945c7c88129
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260385"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr 클래스

이 클래스는 새 벡터를 사용 하 여 스마트 포인터 개체를 나타내는 및 delete 연산자입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|생성자입니다.|
|[CAutoVectorPtr::~CAutoVectorPtr](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAutoVectorPtr::Allocate](#allocate)|이 메서드를 가리키는 개체의 배열에 필요한 메모리를 할당할 `CAutoVectorPtr`합니다.|
|[CAutoVectorPtr::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|
|[CAutoVectorPtr::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|
|[CAutoVectorPtr::Free](#free)|가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoVectorPtr`합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAutoVectorPtr::operator T *](#operator_t__star)|캐스트 연산자입니다.|
|[CAutoVectorPtr::operator =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAutoVectorPtr::m_p](#m_p)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스를 만들고 범위를 벗어나는 경우 자동으로 리소스를 해제 하 여 메모리 누수를 방지 하는 데 도움이 됩니다 하는 스마트 포인터를 관리 하기 위한 메서드를 제공 합니다. `CAutoVectorPtr` 비슷합니다 `CAutoPtr`, 유일한 차이점은는 `CAutoVectorPtr` 사용 하 여 [벡터 new&#91; &#93; ](../../standard-library/new-operators.md#op_new_arr) 및 [벡터 delete&#91; &#93; ](../../standard-library/new-operators.md#op_delete_arr) 할당 및 메모리를 해제 합니다. 대신는 C++ **새** 하 고 **삭제** 연산자입니다. 참조 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 하는 경우의 컬렉션 클래스 `CAutoVectorPtr` 필요 합니다.

참조 [CAutoPtr](../../atl/reference/cautoptr-class.md) 스마트 포인터 클래스를 사용 하는 예입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="allocate"></a>  CAutoVectorPtr::Allocate

이 메서드를 가리키는 개체의 배열에 필요한 메모리를 할당할 `CAutoVectorPtr`합니다.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>매개 변수

*nElements*<br/>
배열의 요소 수입니다.

### <a name="return-value"></a>반환 값

메모리 되 면 true를 반환 합니다 할당에 실패 하면 false를 합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우는 [CAutoVectorPtr::m_p](#m_p) 멤버 변수는 현재 기존 값을 가리킵니다; null은, 합니다.

##  <a name="attach"></a>  CAutoVectorPtr::Attach

이 메서드는 기존 포인터의 소유권을 호출 합니다.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
`CAutoVectorPtr` 개체 this이 포인터의 소유권을 갖게 됩니다.

### <a name="remarks"></a>설명

경우는 `CAutoVectorPtr` 자동으로 삭제 됩니다 포인터 및 할당 된 데이터 범위를 벗어날 때, 개체에 대 한 포인터의 소유권을 갖습니다. 하는 경우 [CAutoVectorPtr::Detach](#detach) 는 호출 프로그래머가 다시 모든 해제에 대 한 책임 지정 된 리소스가 할당 됩니다.

디버그 빌드에서 어설션 오류가 발생 하는 경우는 [CAutoVectorPtr::m_p](#m_p) 멤버 변수는 현재 기존 값을 가리킵니다; null은, 합니다.

##  <a name="cautovectorptr"></a>  CAutoVectorPtr::CAutoVectorPtr

생성자입니다.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
기존 포인터입니다.

### <a name="remarks"></a>설명

`CAutoVectorPtr` 포인터의 소유권 전송 하는 경우, 기존 포인터를 사용 하 여 개체를 만들 수 있습니다.

##  <a name="dtor"></a>  CAutoVectorPtr::~CAutoVectorPtr

소멸자입니다.

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>설명

할당 된 리소스를 해제 합니다. 호출 [CAutoVectorPtr::Free](#free)합니다.

##  <a name="detach"></a>  CAutoVectorPtr::Detach

포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>반환 값

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제, 설정 된 [CAutoVectorPtr::m_p](#m_p) 멤버 변수를 NULL 포인터의 복사본을 반환 합니다. 호출한 후 `Detach`, 해당 해제 하는 프로그래머의 몫 동안 할당 되는 리소스는는 `CAutoVectorPtr` 개체 수 있는 이전에 추정한 책임.

##  <a name="free"></a>  CAutoVectorPtr::Free

가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoVectorPtr`합니다.

```
void Free() throw();
```

### <a name="remarks"></a>설명

가리키는 개체를 `CAutoVectorPtr` 해제 되 면 하며 [CAutoVectorPtr::m_p](#m_p) 멤버 변수를 NULL로 설정 합니다.

##  <a name="m_p"></a>  CAutoVectorPtr::m_p

포인터 데이터 멤버 변수입니다.

```
T* m_p;
```

### <a name="remarks"></a>설명

이 멤버 변수가 포인터 정보를 보유합니다.

##  <a name="operator_eq"></a>  CAutoVectorPtr::operator =

대입 연산자입니다.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
포인터입니다.

### <a name="return-value"></a>반환 값

에 대 한 참조를 반환 합니다는 **CAutoVectorPtr\< T >** 합니다.

### <a name="remarks"></a>설명

대입 연산자를 분리 합니다 `CAutoVectorPtr` 개체에서 모든 현재 포인터 새 포인터에 연결 *p*, 해당 위치에.

##  <a name="operator_t__star"></a>  CAutoVectorPtr::operator T *

캐스트 연산자입니다.

```
operator T*() const throw();
```

### <a name="remarks"></a>설명

클래스 템플릿에 정의 된 개체 데이터 형식에 대 한 포인터를 반환 합니다.

## <a name="see-also"></a>참고자료

[CAutoPtr 클래스](../../atl/reference/cautoptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

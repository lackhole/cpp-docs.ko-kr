---
title: CAutoPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
ms.openlocfilehash: 7f4f446aa97f2bf3843b830bd7fb4c4a5d74ffdb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260164"
---
# <a name="cautoptr-class"></a>CAutoPtr 클래스

이 클래스에는 스마트 포인터 개체를 나타냅니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CAutoPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAutoPtr::CAutoPtr](#cautoptr)|생성자입니다.|
|[CAutoPtr::~CAutoPtr](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAutoPtr::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|
|[CAutoPtr::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|
|[CAutoPtr::Free](#free)|가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoPtr`합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAutoPtr::operator T*](#operator_t_star)|캐스트 연산자입니다.|
|[CAutoPtr::operator =](#operator_eq)|대입 연산자입니다.|
|[CAutoPtr::operator ->](#operator_ptr)|멤버 포인터 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAutoPtr::m_p](#m_p)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스를 만들고 범위를 벗어나는 경우 자동으로 리소스를 해제 하 여 메모리 누수를 방지 하는 데 도움이 됩니다 하는 스마트 포인터를 관리 하기 위한 메서드를 제공 합니다.

또한 `CAutoPtr`의 복사 생성자 및 대입 연산자 전송 소유권 포인터의 대상 포인터에 대 한 원본 포인터를 복사 하 고 원본 포인터를 NULL로 설정 합니다. 따라서 둘 수 없는 `CAutoPtr` 같은 포인터를 저장 하는 각 개체 및이 동일한 마우스 포인터를 두 번 삭제 가능성을 줄여줍니다.

`CAutoPtr` 또한 포인터 컬렉션 만들기를 간소화합니다. 컬렉션 클래스를 파생 하 고 소멸자를 재정의 하는 대신 간단 하 게의 컬렉션을 만드는 것 `CAutoPtr` 개체입니다. 컬렉션 삭제 되 면를 `CAutoPtr` 개체는 범위를 벗어나 자동으로 자체를 삭제 합니다.

[CHeapPtr](../../atl/reference/cheapptr-class.md) 변형으로 동일한 방식으로 작동 하 고 `CAutoPtr`한다는 점을 제외 하는 할당 하 고 대신 다른 힙 함수를 사용 하 여 메모리를 해제 합니다 C++ **새** 하 고 **삭제** 연산자입니다. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) 비슷합니다 `CAutoPtr`, 유일한 차이점은 사용 한다는 **벡터 new** 하 고 **벡터 delete** 할당 및 메모리를 해제 합니다.

참고 항목 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 하 고 [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 배열 또는 스마트 포인터 목록을 필요한 경우.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

##  <a name="attach"></a>  CAutoPtr::Attach

이 메서드는 기존 포인터의 소유권을 호출 합니다.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
`CAutoPtr` 개체 this이 포인터의 소유권을 갖게 됩니다.

### <a name="remarks"></a>설명

경우는 `CAutoPtr` 자동으로 삭제 됩니다 포인터 및 할당 된 데이터 범위를 벗어날 때, 개체에 대 한 포인터의 소유권을 갖습니다. 하는 경우 [CAutoPtr::Detach](#detach) 는 호출 프로그래머가 다시 모든 해제에 대 한 책임 지정 된 리소스가 할당 됩니다.

디버그 빌드에서 어설션 오류가 발생 하는 경우는 [CAutoPtr::m_p](#m_p) 데이터 멤버는 현재 기존 값을 가리킵니다; null은, 합니다.

### <a name="example"></a>예제

예제를 참조 합니다 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.

##  <a name="cautoptr"></a>  CAutoPtr::CAutoPtr

생성자입니다.

```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
기존 포인터입니다.

*TSrc*<br/>
다른 관리 되는 형식 `CAutoPtr`현재 개체를 초기화 하는 데 사용 합니다.

### <a name="remarks"></a>설명

`CAutoPtr` 포인터의 소유권 전송 하는 경우, 기존 포인터를 사용 하 여 개체를 만들 수 있습니다.

### <a name="example"></a>예제

예제를 참조 합니다 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.

##  <a name="dtor"></a>  CAutoPtr::~CAutoPtr

소멸자입니다.

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>설명

할당 된 리소스를 해제 합니다. 호출 [CAutoPtr::Free](#free)합니다.

##  <a name="detach"></a>  CAutoPtr::Detach

포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>반환 값

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제, 설정 된 [CAutoPtr::m_p](#m_p) 데이터 멤버 변수를 NULL 포인터의 복사본을 반환 합니다. 호출한 후 `Detach`, 해당 해제 하는 프로그래머의 몫 동안 할당 되는 리소스는는 `CAutoPtr` 개체 수 있는 이전에 추정한 reponsibility.

### <a name="example"></a>예제

예제를 참조 합니다 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.

##  <a name="free"></a>  CAutoPtr::Free

가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoPtr`합니다.

```
void Free() throw();
```

### <a name="remarks"></a>설명

가리키는 개체를 `CAutoPtr` 해제 되 면 하며 [CAutoPtr::m_p](#m_p) 데이터 멤버 변수를 NULL로 설정 합니다.

##  <a name="m_p"></a>  CAutoPtr::m_p

포인터 데이터 멤버 변수입니다.

```
T* m_p;
```

### <a name="remarks"></a>설명

이 멤버 변수가 포인터 정보를 보유합니다.

##  <a name="operator_eq"></a>  CAutoPtr::operator =

대입 연산자입니다.

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>매개 변수

*p*<br/>
포인터입니다.

*TSrc*<br/>
클래스 형식입니다.

### <a name="return-value"></a>반환 값

에 대 한 참조를 반환 합니다는 **CAutoPtr\< T >** 합니다.

### <a name="remarks"></a>설명

대입 연산자를 분리 합니다 `CAutoPtr` 개체에서 모든 현재 포인터 새 포인터에 연결 *p*, 해당 위치에.

### <a name="example"></a>예제

예제를 참조 합니다 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.

##  <a name="operator_ptr"></a>  CAutoPtr::operator -&gt;

멤버 포인터 연산자입니다.

```
T* operator->() const throw();
```

### <a name="return-value"></a>반환 값

값을 반환 합니다 [CAutoPtr::m_p](#m_p) 데이터 멤버 변수입니다.

### <a name="remarks"></a>설명

이 연산자가 가리키는 클래스의 메서드를 호출 하는 데는 `CAutoPtr` 개체입니다. 디버그 빌드에서 어설션 오류가 발생 하는 경우는 `CAutoPtr` NULL을 가리킵니다.

### <a name="example"></a>예제

예제를 참조 합니다 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.

##  <a name="operator_t_star"></a>  CAutoPtr::operator T*

캐스트 연산자입니다.

```
operator T* () const throw();
```

### <a name="return-value"></a>반환 값

클래스 템플릿에 정의 된 개체 데이터 형식에 대 한 포인터를 반환 합니다.

### <a name="example"></a>예제

예제를 참조 합니다 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.

## <a name="see-also"></a>참고자료

[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr 클래스](../../atl/reference/cautovectorptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

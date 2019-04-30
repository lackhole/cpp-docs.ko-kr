---
title: CComQIPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: 64716d945ffbc6802ec23fb47523464246065192
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258912"
---
# <a name="ccomqiptr-class"></a>CComQIPtr 클래스

COM 인터페이스 포인터를 관리 하는 것에 대 한 스마트 포인터 클래스입니다.

## <a name="syntax"></a>구문

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
저장에 대 한 포인터의 형식을 지정 하는 COM 인터페이스입니다.

*piid*<br/>
에 대 한 포인터의 IID *T*합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComQIPtr::CComQIPtr](#ccomqiptr)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CComQIPtr::operator =](#operator_eq)|멤버 포인터에 대 한 포인터를 할당합니다.|

## <a name="remarks"></a>설명

다음을 사용 하 여 ATL `CComQIPtr` 하 고 [CComPtr](../../atl/reference/ccomptr-class.md) COM 인터페이스 포인터를 관리 하려면 둘 다에서 파생 되 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)합니다. 두 클래스 모두 자동 참조에 대 한 호출을 통해 계산을 수행할 `AddRef` 고 `Release`입니다. 오버 로드 된 연산자는 포인터 연산을 처리합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

##  <a name="ccomqiptr"></a>  CComQIPtr::CComQIPtr

생성자입니다.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>매개 변수

*lp*<br/>
인터페이스 포인터를 초기화 하는 데 사용 합니다.

*T*<br/>
COM 인터페이스입니다.

*piid*<br/>
에 대 한 포인터의 IID *T*합니다.

##  <a name="operator_eq"></a>  CComQIPtr::operator =

대입 연산자입니다.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>매개 변수

*lp*<br/>
인터페이스 포인터를 초기화 하는 데 사용 합니다.

*T*<br/>
COM 인터페이스입니다.

*piid*<br/>
에 대 한 포인터의 IID *T*합니다.

### <a name="return-value"></a>반환 값

업데이트에 대 한 포인터를 반환 합니다 `CComQIPtr` 개체입니다.

## <a name="see-also"></a>참고자료

[CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr::CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase 클래스](../../atl/reference/ccomptrbase-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)

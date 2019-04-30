---
title: CComPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 5e3e510291daa50ddcf5d63451edef0428d66ed1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259107"
---
# <a name="ccomptr-class"></a>CComPtr 클래스

COM 인터페이스 포인터를 관리 하는 것에 대 한 스마트 포인터 클래스입니다.

## <a name="syntax"></a>구문

```
template<class T>
class CComPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
저장에 대 한 포인터의 형식을 지정 하는 COM 인터페이스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComPtr::CComPtr](#ccomptr)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CComPtr::operator =](#operator_eq)|멤버 포인터에 대 한 포인터를 할당합니다.|

## <a name="remarks"></a>설명

ATL 사용 `CComPtr` 하 고 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터를 관리할 수 있습니다. 파생 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)를 둘 다 자동 참조 계산을 수행 합니다.

합니다 `CComPtr` 하 고 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 클래스 자동 참조 계산을 수행 하 여 메모리 누수를 제거할 수 있습니다.  다음 함수 모두 수행 하는 동일한 논리 작업 그러나 어떻게 두 번째 버전 수 적으며 오류 발생률를 사용 하 여는 `CComPtr` 클래스:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

디버그 빌드에서 atlsd.lib 코드 추적에 대 한 연결 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="ccomptr"></a>  CComPtr::CComPtr

생성자입니다.

```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>매개 변수

*lp*<br/>
인터페이스 포인터를 초기화 하는 데 사용 합니다.

*T*<br/>
COM 인터페이스입니다.

##  <a name="operator_eq"></a>  CComPtr::operator =

대입 연산자입니다.

```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>반환 값

업데이트에 대 한 포인터를 반환 합니다 `CComPtr` 개체

### <a name="remarks"></a>설명

이 작업 AddRefs 새 개체 및 릴리스 기존 개체를 하나 존재 합니다.

## <a name="see-also"></a>참고자료

[CComPtr::CComPtr](#ccomptr)<br/>
[CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 42953c92e4cf31b5ccd02dd51811fc1fdeedbcaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399280"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft 전용**

호출 된 **QueryInterface** 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.

## <a name="syntax"></a>구문

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>매개 변수

*iid*<br/>
`IID` 인터페이스 포인터입니다.

*p*<br/>
원시 인터페이스 포인터입니다.

## <a name="remarks"></a>설명

호출 `IUnknown::QueryInterface` 지정 된 캡슐화 된 인터페이스 포인터에 대 한 `IID` 결과 원시 인터페이스 포인터를 반환 하 고 *p*합니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
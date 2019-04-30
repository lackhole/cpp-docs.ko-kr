---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: cf4cea35386d1f781d6d2946c1730ba2e18dacea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399228"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release

**Microsoft 전용**

호출 된 **릴리스** 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.

## <a name="syntax"></a>구문

```
void Release( );
```

## <a name="remarks"></a>설명

호출 `IUnknown::Release` 캡슐화 된 인터페이스 포인터에 대 한 발생을 `E_POINTER` 이 인터페이스 포인터가 null 인 경우 오류가 발생 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
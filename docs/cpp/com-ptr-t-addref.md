---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 7408b5c174f76673b56caffd56aaa87895bd08d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154944"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef

**Microsoft 전용**

호출 된 `AddRef` 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.

## <a name="syntax"></a>구문

```
void AddRef( );
```

## <a name="remarks"></a>설명

호출 `IUnknown::AddRef` 캡슐화 된 인터페이스 포인터에 대 한 발생을 `E_POINTER` 포인터가 null 인 경우 오류가 발생 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 4b4b7a21d12cc645c486dd93d555510c1e716563
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154892"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach

**Microsoft 전용**

이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.

## <a name="syntax"></a>구문

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>매개 변수

*pInterface*<br/>
원시 인터페이스 포인터입니다.

*fAddRef*<br/>
그런 다음 해당가 TRUE 인 경우 `AddRef` 라고 합니다. FALSE 이면 합니다 `_com_ptr_t` 개체를 호출 하지 않고 원시 인터페이스 포인터의 소유권 `AddRef`합니다.

## <a name="remarks"></a>설명

- **연결 (***pInterface***)** `AddRef` 호출 되지 않습니다. 인터페이스 소유권이 이 `_com_ptr_t` 개체에 전달됩니다. `Release` 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다.

- **연결 (***pInterface* **하십시오***fAddRef***)** 경우 *fAddRef* 가 TRUE 인 `AddRef`캡슐화 된 인터페이스 포인터에 대 한 참조 횟수를 증가 하기 위해 호출 됩니다. 하는 경우 *fAddRef* 은 FALSE이 `_com_ptr_t` 개체를 호출 하지 않고 원시 인터페이스 포인터의 소유권 `AddRef`합니다. `Release` 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
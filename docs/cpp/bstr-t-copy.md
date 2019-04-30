---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 13ddf57e0bdbdbcc0c5b487e879e14b000de3ad0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393937"
---
# <a name="bstrtcopy"></a>_bstr_t::copy

**Microsoft 전용**

캡슐화된 `BSTR`의 복사본을 구성합니다.

## <a name="syntax"></a>구문

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>매개 변수

*fCopy*<br/>
TRUE 이면 **복사본** 포함된 된 복사본을 반환 합니다 `BSTR`고, 그렇지 않으면 **복사** 는 실제 BSTR을 반환 합니다.

## <a name="remarks"></a>설명

캡슐화된 `BSTR` 개체에 새로 할당된 복사본을 반환합니다.

## <a name="example"></a>예제

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)
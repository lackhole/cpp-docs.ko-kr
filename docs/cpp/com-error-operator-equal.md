---
title: _com_error::operator =
ms.date: 11/04/2016
f1_keywords:
- _com_error::operator=
helpviewer_keywords:
- _com_error [C++]
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
ms.openlocfilehash: 1c68d10c8f82f5d5ed7f6286ba15437941c0ac6b
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222502"
---
# <a name="comerroroperator-"></a>_com_error::operator =

**Microsoft 전용**

기존 `_com_error` 개체를 다른 개체에 할당합니다.

## <a name="syntax"></a>구문

```
_com_error& operator = (
   const _com_error& that
) throw ( );
```

#### <a name="parameters"></a>매개 변수

*that*<br/>
`_com_error` 개체입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
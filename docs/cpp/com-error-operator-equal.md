---
title: _com_error::operator =
ms.date: 11/04/2016
f1_keywords:
- _com_error::operator=
helpviewer_keywords:
- operator= _com_error objects
- = operator [C++], with specific Visual C++ objects
- operator = _com_error objects
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
ms.openlocfilehash: 68eb486ec109d98890ebf3adc0c086368380142b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154996"
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
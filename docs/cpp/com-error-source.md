---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 682070877f269967405677d027b20707c8366f61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154963"
---
# <a name="comerrorsource"></a>_com_error::Source

**Microsoft 전용**

호출 `IErrorInfo::GetSource` 함수입니다.

## <a name="syntax"></a>구문

```
_bstr_t Source() const;
```

## <a name="return-value"></a>반환 값

결과 반환 합니다 `IErrorInfo::GetSource` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다. 없으면 `IErrorInfo` 는 빈 반환 기록 `_bstr_t`합니다.

## <a name="remarks"></a>설명

호출 하는 동안 모든 오류를 `IErrorInfo::GetSource` 메서드는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
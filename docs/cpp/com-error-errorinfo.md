---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 59ada8a7e098e57cca5641a439365851bbae2485
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155074"
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 전용**

검색 된 `IErrorInfo` 개체 생성자에 전달 합니다.

## <a name="syntax"></a>구문

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>반환 값

생성자에 전달된 원시 `IErrorInfo` 항목입니다.

## <a name="remarks"></a>설명

캡슐화 된 검색 `IErrorInfo` 항목에 `_com_error` 개체 또는 없으면 NULL `IErrorInfo` 항목 기록 됩니다. 호출자에 게 호출 해야 `Release` 완료 되 면 반환된 된 개체에이 사용 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
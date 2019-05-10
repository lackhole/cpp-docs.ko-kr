---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: a421a7fd7fa0817c74dac66946e28928b2ad82dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155087"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext

**Microsoft 전용**

호출 `IErrorInfo::GetHelpContext` 함수입니다.

## <a name="syntax"></a>구문

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>반환 값

결과 반환 합니다 `IErrorInfo::GetHelpContext` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 없으면 `IErrorInfo` 개체는 기록, 0을 반환 합니다.

## <a name="remarks"></a>설명

호출 하는 동안 모든 오류를 `IErrorInfo::GetHelpContext` 메서드는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 905b67577a65b81be0b4d18c7513652dd8c5f055
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155061"
---
# <a name="comerrorguid"></a>_com_error::GUID

**Microsoft 전용**

호출 `IErrorInfo::GetGUID` 함수입니다.

## <a name="syntax"></a>구문

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>반환 값

결과 반환 합니다 `IErrorInfo::GetGUID` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 없으면 `IErrorInfo` 반환 개체는 기록 `GUID_NULL`합니다.

## <a name="remarks"></a>설명

호출 하는 동안 모든 오류를 `IErrorInfo::GetGUID` 메서드는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
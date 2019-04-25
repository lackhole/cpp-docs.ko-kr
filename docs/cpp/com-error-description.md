---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: a517c40e9adfbda2d790ce41a48ccf8658bcd3e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155113"
---
# <a name="comerrordescription"></a>_com_error::Description

**Microsoft 전용**

호출 `IErrorInfo::GetDescription` 함수입니다.

## <a name="syntax"></a>구문

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>반환 값

결과 반환 합니다 `IErrorInfo::GetDescription` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다. 없으면 `IErrorInfo` 는 빈 반환 기록 `_bstr_t`합니다.

## <a name="remarks"></a>설명

호출 된 `IErrorInfo::GetDescription` 함수와 검색 `IErrorInfo` 내에 기록 된는 `_com_error` 개체입니다. 호출 하는 동안 모든 오류를 `IErrorInfo::GetDescription` 메서드는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 826ac53f001355127f16b7ad2a7583a0f8800de7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155035"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile

**Microsoft 전용**

호출 `IErrorInfo::GetHelpFile` 함수입니다.

## <a name="syntax"></a>구문

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>반환 값

결과 반환 합니다 `IErrorInfo::GetHelpFile` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다. 없으면 `IErrorInfo` 는 빈 반환 기록 `_bstr_t`합니다.

## <a name="remarks"></a>설명

호출 하는 동안 모든 오류를 `IErrorInfo::GetHelpFile` 메서드는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
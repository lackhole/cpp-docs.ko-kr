---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: 44fc9755cd69050ea82145636f01614258943794
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500590"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft 전용**

`_com_error` 개체에 저장 된 HRESULT에 대 한 문자열 메시지를 검색 합니다.

## <a name="syntax"></a>구문

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>반환 값

`_com_error` 개체 내에 기록 된 HRESULT에 대 한 문자열 메시지를 반환 합니다. HRESULT가 매핑된 16 비트 [wcode](../cpp/com-error-wcode.md)이면 일반 메시지 "`IDispatch error #<wCode>`"가 반환 됩니다. 메시지가 발견되지 않으면 일반 메시지 "`Unknown error #<hresult>`"가 반환됩니다. 반환 되는 문자열은 _UNICODE 매크로의 상태에 따라 유니코드 또는 멀티 바이트 문자열입니다.

## <a name="remarks"></a>설명

`_com_error` 개체 내에 기록 된 HRESULT에 대 한 적절 한 시스템 메시지 텍스트를 검색 합니다. Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) 함수를 호출 하 여 시스템 메시지 텍스트를 가져옵니다. 반환된 문자열은 `FormatMessage` API에 의해 할당되고, `_com_error` 개체가 제거될 때 해제됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2fc84be53d95754d21c30eaea8dd981447453d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154931"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft 전용**

16 비트 매핑합니다 *wCode* 32 비트 hresult입니다.

## <a name="syntax"></a>구문

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>매개 변수

*wCode*<br/>
16 비트 *wCode* 32 비트 HRESULT에 매핑됩니다.

## <a name="return-value"></a>반환 값

16 비트에서 매핑된 32 비트 HRESULT *wCode*합니다.

## <a name="remarks"></a>설명

참조 된 [WCode](../cpp/com-error-wcode.md) 멤버 함수입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error 클래스](../cpp/com-error-class.md)
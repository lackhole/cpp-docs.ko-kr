---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: d89503e822d92bf6a1fcb2b6bb658d532af32c5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155048"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 전용**

16 비트에서 32 비트 HRESULT 매핑됩니다 `wCode`합니다.

## <a name="syntax"></a>구문

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>매개 변수

*hr*<br/>
16 비트와 매핑되어야 32 비트 HRESULT `wCode`합니다.

## <a name="return-value"></a>반환 값

16 비트 `wCode` 32 비트 HRESULT에서 매핑됩니다.

## <a name="remarks"></a>설명

참조 [_com_error:: wcode](../cpp/com-error-wcode.md) 자세한 내용은 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error 클래스](../cpp/com-error-class.md)
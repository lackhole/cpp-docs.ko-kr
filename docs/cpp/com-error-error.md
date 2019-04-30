---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 606f553060e71ece18b3d48159ec40133be28965
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155100"
---
# <a name="comerrorerror"></a>_com_error::Error

**Microsoft 전용**

생성자에 전달 된 HRESULT를 검색 합니다.

## <a name="syntax"></a>구문

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>반환 값

원시 HRESULT 항목 생성자에 전달 합니다.

## <a name="remarks"></a>설명

캡슐화 된 HRESULT 항목 검색을 `_com_error` 개체입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_error 클래스](../cpp/com-error-class.md)
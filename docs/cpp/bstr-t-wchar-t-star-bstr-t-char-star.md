---
title: _bstr_t::wchar_t *, _bstr_t::char*
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
ms.openlocfilehash: bfc149b0f0688bed567bf202fddb4ab2c3102630
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345147"
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t\*, _bstr_t::char\*

**Microsoft 전용**

BSTR 문자는 좁거나 넓은 문자 배열로 반환됩니다.

## <a name="syntax"></a>구문

```
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>설명

이러한 연산자는 `BSTR` 개체로 캡슐화된 문자 데이터를 추출하는 데 사용될 수 있습니다. 반환된 포인터에 새 값을 할당하면 원래 BSTR 데이터는 수정되지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)
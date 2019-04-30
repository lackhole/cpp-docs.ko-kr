---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: d07e995be0ecd99974356a7516e7c4deee677637
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403271"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Microsoft 전용**

이 `_variant_t` 개체에 문자열을 할당합니다.

## <a name="syntax"></a>구문

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>매개 변수

*pSrc*<br/>
문자열에 대한 포인터입니다.

## <a name="remarks"></a>설명

ANSI 문자열을 유니코드 `BSTR` 문자열로 변환하고 이 `_variant_t` 개체에 할당합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)
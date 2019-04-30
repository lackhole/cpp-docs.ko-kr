---
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: 510267c7ab00fe22a93dc01342def5fc262ddb04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166220"
---
# <a name="varianttattach"></a>_variant_t::Attach

**Microsoft 전용**

연결 된 `VARIANT` 개체를 **_variant_t** 개체.

## <a name="syntax"></a>구문

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
A `VARIANT` 이 연결할 개체 **_variant_t** 개체입니다.

## <a name="remarks"></a>설명

소유권을 `VARIANT` 캡슐화 하 여 그 합니다. 이 멤버 함수는 캡슐화 된 기존 릴리스 `VARIANT`, 다음 제공 된 복사 `VARIANT`를 설정 하 고 해당 `VARTYPE` 값을 vt_empty로 되도록 해당 리소스 에서만 해제할 수 있습니다는 **_variant_t** 소멸자입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)
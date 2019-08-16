---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 8426c80af04b2c0906af150ea3e91304335e9f69
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500553"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 전용**

캡슐화 `VARIANT` 된 개체를이 `_variant_t` 개체에서 분리 합니다.

## <a name="syntax"></a>구문

```
VARIANT Detach( );
```

## <a name="return-value"></a>반환 값

캡슐화 `VARIANT`된입니다.

## <a name="remarks"></a>설명

캡슐화 `VARIANT`된를 추출 하 여 반환한 다음이 `_variant_t` 개체를 삭제 하지 않고 지웁니다. 이 멤버 함수는 캡슐화 `VARIANT` 에서을 제거 하 고 `VARTYPE` 이 `_variant_t` 개체의를 VT_EMPTY로 설정 합니다. `VARIANT` [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) 함수를 호출 하 여 반환 된를 해제할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)
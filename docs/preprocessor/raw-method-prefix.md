---
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: b1bc536507716e5c117718ec825bf7fe76c84b61
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216150"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++컴퓨터별**

이름 충돌을 방지하기 위해 다른 접두사를 지정합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **raw_method_prefix (** "*prefix*" **)**

### <a name="parameters"></a>매개 변수

*접두사*\
사용할 접두사입니다.

## <a name="remarks"></a>설명

상위 수준 오류 처리 멤버 함수와의 이름 충돌을 방지 하기 위해 기본 접두사 **raw_** 을 사용 하 여 라는 멤버 함수에서 하위 수준 속성 및 메서드를 노출 합니다.

> [!NOTE]
> **Raw_method_prefix** 특성의 효과는 [raw_interfaces_only](raw-interfaces-only.md) 특성이 있는지 여부에 따라 변경 되지 않습니다. **Raw_method_prefix** 는 항상 접두사를 지정 `raw_interfaces_only` 하는 것 보다 우선적으로 적용 됩니다. 동일한 `#import` 문에서 두 특성을 모두 사용 하는 경우 **raw_method_prefix** 특성으로 지정 된 접두사가 사용 됩니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)

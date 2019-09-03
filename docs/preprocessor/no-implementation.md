---
title: no_implementation import 특성
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 8f0a7454fdbedc1959b665ccb2a23748d21c342d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220778"
---
# <a name="no_implementation-import-attribute"></a>no_implementation import 특성

**C++컴퓨터별**

래퍼 멤버 함수의 구현을 포함 `.tli` 하는 헤더 생성을 억제 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **no_implementation**

## <a name="remarks"></a>설명

이 특성을 지정 `.tlh` 하면 `.tli` 헤더 파일을 포함 하는 `#include` 문을 사용 하지 않고 헤더에 형식 라이브러리 항목을 표시할 선언이 생성 됩니다.

이 특성은 [implementation_only](../preprocessor/implementation-only.md)와 함께 사용 됩니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)

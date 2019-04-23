---
title: include()
ms.date: 10/18/2018
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 1208f14a9f6b3724dd5353df57213baa3910d07f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040929"
---
# <a name="include"></a>include()

**C++특정**

자동 제외를 사용하지 않도록 설정합니다.

## <a name="syntax"></a>구문

```
include("Name1"[,"Name2", ...])
```

### <a name="parameters"></a>매개 변수

*Name1*<br/>
강제로 포함할 첫 번째 항목입니다.

*Name2*<br/>
필요할 경우 강제로 포함할 두 번째 항목입니다.

## <a name="remarks"></a>설명

형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다. `#import`는 다양한 정의 오류를 자동으로 제외하여 해당 오류를 방지하려고 합니다. 항목 제외 되는, 명시 된 경우 [컴파일러 경고 (수준 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), 하지 않아야 하는 고 된 자동 제외를 사용 하지 않도록 설정 하려면이 특성을 사용할 수 있습니다. 이 특성은 각각 포함할 형식 라이브러리 항목의 이름이 될 인수 몇 개를 가질 수 있습니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)
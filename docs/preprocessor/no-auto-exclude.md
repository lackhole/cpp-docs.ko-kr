---
title: no_auto_exclude
ms.date: 11/04/2016
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 06bde7535bd181057750ab9dd4c3999321b4990c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038944"
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++ 전용**

자동 제외를 사용하지 않도록 설정합니다.

## <a name="syntax"></a>구문

```
no_auto_exclude
```

## <a name="remarks"></a>설명

형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다. `#import` 자동으로 이러한 항목을 제외 하 여 여러 정의 오류를 방지 하려고 합니다. 이 작업을 마치면 [컴파일러 경고 (수준 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) 제외할 각 항목에 대해 발생 합니다. 이 특성을 사용하여 자동 제외를 사용하지 않도록 설정할 수 있습니다.

**C++ 전용 종료**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
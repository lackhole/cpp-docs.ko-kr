---
title: implementation_only
ms.date: 11/04/2016
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: c1435ca74ac2b5a73c308592b1affe6fca097d1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383960"
---
# <a name="implementationonly"></a>implementation_only
**C++특정**

.tlh 헤더 파일(기본 헤더 파일)을 생성하지 않습니다.

## <a name="syntax"></a>구문

```
implementation_only
```

## <a name="remarks"></a>설명

이 파일에는 형식 라이브러리 내용을 노출하는 데 사용되는 모든 선언이 포함되어 있습니다. .tli 헤더 파일이 래퍼 멤버 함수의 구현과 함께 생성되어 컴파일에 포함됩니다.

이 특성이 지정되면 .tli 헤더의 내용이 .tlh 헤더에서 일반적으로 사용되는 동일한 네임스페이스에 있습니다. 또한 멤버 함수가 인라인으로 선언되지 않습니다.

**implementation_only** 와 함께에서 사용 하기 위한 특성을 [no_implementation](../preprocessor/no-implementation.md) 미리 컴파일된 헤더 (PCH) 파일에서 구현을 유지 하는 방법으로 특성입니다. `#import` 특성이 포함된 `no_implementation` 문은 PCH를 만드는 데 사용되는 소스 영역에 배치됩니다. 생성된 PCH는 많은 소스 파일에서 사용됩니다. `#import` 사용 하 여 문을 합니다 **implementation_only** PCH 영역 외부 특성에서 사용 됩니다. 소스 파일 중 하나에서 한 번만 이 문을 사용해야 합니다. 이 문을 사용하면 각 소스 파일을 추가로 다시 컴파일할 필요 없이 필요한 래퍼 멤버 함수가 모두 생성됩니다.

> [!NOTE]
> **implementation_only** 특성 하나 `#import` 문을 다른와 함께 사용 해야 합니다. `#import` 문에서 동일한 형식 라이브러리를 사용 하 여를 `no_implementation` 특성입니다. 이렇게 하지 않으면 컴파일러 오류가 생성됩니다. 래퍼 클래스 정의에서 생성 되므로이 `#import` 문을 사용 하 여를 `no_implementation` 특성으로 생성 된 구현을 컴파일하는 데 필요 합니다 **implementation_only** 특성.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)
---
title: implementation_only import 특성
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 08144b3c815350acfe6a856b36d2d88085d1c04d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218978"
---
# <a name="implementation_only-import-attribute"></a>implementation_only import 특성

**C++컴퓨터별**

`.tlh` 기본 형식 라이브러리 헤더 파일의 생성을 억제 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **implementation_only**

## <a name="remarks"></a>설명

이 파일에는 형식 라이브러리 내용을 노출하는 데 사용되는 모든 선언이 포함되어 있습니다. 래퍼 멤버 함수의 구현이 포함 된 헤더파일이생성되고컴파일에포함됩니다.`.tli`

이 특성을 지정 하면 헤더의 내용이 `.tli` `.tlh` 헤더에서 일반적으로 사용 되는 네임 스페이스와 동일한 네임 스페이스에 있습니다. 또한 멤버 함수가 인라인으로 선언되지 않습니다.

**Implementation_only** 특성은 미리 컴파일된 헤더 (PCH) 파일의 구현을 유지 하는 방법으로 [no_implementation](../preprocessor/no-implementation.md) 특성과 함께 사용 하기 위한 것입니다. `#import` 특성이 포함된 `no_implementation` 문은 PCH를 만드는 데 사용되는 소스 영역에 배치됩니다. 생성된 PCH는 많은 소스 파일에서 사용됩니다. 그런 다음 **implementation_only** 특성이 있는 문이PCH영역외부에서사용됩니다.`#import` 이 문은 소스 파일 중 하나에서 한 번만 사용 해야 합니다. 각 소스 파일에 대 한 추가 재컴파일을 하지 않고 필요한 모든 래퍼 멤버 함수를 생성 합니다.

> [!NOTE]
> `#import` `no_implementation` 한 `#import` 문의 implementation_only 특성은 특성을 사용 하 여 동일한 형식 라이브러리의 다른 문과 함께 사용 해야 합니다. 그렇지 않으면 컴파일러 오류가 생성 됩니다. 이는 **implementation_only** 특성에 의해 생성 된 구현을 `#import` 컴파일하기 위해 `no_implementation` 특성을 사용 하 여 문에서 생성 된 래퍼 클래스 정의가 필요 하기 때문입니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)

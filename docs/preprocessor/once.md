---
title: once
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
ms.openlocfilehash: 6061fe77960aa64e2dcb39db05897ef0e7fb5f2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326343"
---
# <a name="once"></a>once
소스 코드 파일을 컴파일할 때 컴파일러에서 파일을 한 번만 포함하도록(열도록) 지정합니다.

## <a name="syntax"></a>구문

```
#pragma once
```

## <a name="remarks"></a>설명

사용 `#pragma once` 와 컴파일러는 없습니다 연 후 첫 번째 파일을 읽을 빌드 시간을 줄일 수 있습니다 `#include` 변환 단위에 있는 파일의 합니다. 이 이라고 *다중 포함 최적화*합니다. 비슷합니다는 영향을 주지는 `#include guard` 관용구를 사용 하 여 전처리기 매크로 정의 파일 콘텐츠의 다중 포함을 방지 합니다. 또한 위반을 방지 하기 위해 이렇게 합니다 *단일 정의 규칙*-모든 템플릿, 형식, 함수 및 개체 코드에 둘 이상의 정의가 있는 요구 사항.

예를 들어:

```
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

`#pragma once` 지시문은 전처리기 기호를 사용하여 전역 네임스페이스가 잘못되는 것을 방지하기 때문에 새 코드에 사용하는 것이 좋습니다. 입력 작업이 필요 없고, 산만하지 않으며, 기호 충돌(여러 헤더 파일에서 가드 값과 동일한 전처리기 기호를 사용하는 경우에 발생하는 오류)을 일으킬 수 없습니다. C++ 표준의 일부는 아니지만 여러 일반 컴파일러에서 이식 가능한 방식으로 구현됩니다.

#include 가드 관용구와 `#pragma once`를 같은 파일에서 함께 사용할 경우의 이점은 없습니다. 컴파일러는 #include 가드 관용구를 인식하여 표준 형식의 관용구 앞 또는 뒤에 오는 주석이 아닌 코드 또는 전처리기 지시문이 없는 경우 `#pragma once` 지시문과 동일한 방식으로 다중 포함 최적화를 구현합니다.

```
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

것이 좋습니다는 `#include guard` 관용구 코드를 구현 하지 않는 컴파일러로 해야 하는 경우는 `#pragma once` 지시문을 기존 코드를 사용 하 여 일관성을 유지 하 때나를 다중 포함 최적화가 불가능 합니다. 이는 복잡한 프로젝트에서 파일 시스템 별칭 또는 별칭이 지정된 포함 경로로 인해 컴파일러가 정규 경로로 동일한 포함 파일을 식별하지 못하는 경우에 발생할 수 있습니다.

사용 하지 않도록 주의 하십시오 `#pragma once` 또는 `#include guard` 관용구를 여러 번 포함 되어야 하도록 설계 된 전처리기 기호를 사용 하 여 해당 효과 제어 하는 헤더 파일에 있습니다. 이 디자인의 예 참조는 \<r t. h > 헤더 파일입니다. 또한 관리 하기 위해 주의 무효화 될 수 있는 포함된 파일에 여러 경로 만들지 못하도록 포함 경로 다중 포함 최적화 둘 다에 대해 `#include guard`s 및 `#pragma once`합니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
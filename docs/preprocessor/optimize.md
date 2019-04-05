---
title: optimize
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 9f5240fc59f59a71ddb3d18b67fadf3463a0d1ea
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035402"
---
# <a name="optimize"></a>optimize

함수별로 수행할 최적화를 지정합니다.

## <a name="syntax"></a>구문

```
#pragma optimize( "[optimization-list]", {on | off} )
```

## <a name="remarks"></a>설명

합니다 **최적화** pragma는 함수 외부에 나타나야 하며, pragma가 표시 한 후 정의 된 첫 번째 함수에 적용 됩니다. *에* 및 *해제* 인수에 지정 된 옵션을 설정 합니다 *최적화 목록* 또는 해제 합니다.

합니다 *최적화 목록* 다음 표에 나와 있는 매개 변수를 0 개 이상의 될 수 있습니다.

### <a name="parameters-of-the-optimize-pragma"></a>optimize Pragma의 매개 변수

|매개 변수|최적화 형식|
|--------------------|--------------------------|
|*g*|전역 최적화를 활성화합니다.|
|*s* 또는 *t*|짧거나 빠른 기계어 코드 시퀀스를 지정합니다.|
|*y*|프로그램 스택에서 프레임 포인터를 생성합니다.|

이 동일한 문자 사용 합니다 [/O](../build/reference/o-options-optimize-code.md) 컴파일러 옵션입니다. 예를 들어 다음 pragma는 `/Os` 컴파일러 옵션과 동일합니다.

```
#pragma optimize( "ts", on )
```

사용 하는 **최적화** pragma를 빈 문자열 (**""**)는 특별 한 형태의 지시문:

사용 하는 경우는 *해제* 매개 변수를 모든 최적화 *g*를 *s*를 *t*, 및 *y*, 해제 합니다.

사용 하는 경우는 *에* 매개 변수를 다시 설정 최적화를 사용 하 여 지정한 것을 [/O](../build/reference/o-options-optimize-code.md) 컴파일러 옵션입니다.

```
#pragma optimize( "", off )
.
.
.
#pragma optimize( "", on )
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)